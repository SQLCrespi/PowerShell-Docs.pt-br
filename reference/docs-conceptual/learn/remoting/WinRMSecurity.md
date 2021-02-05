---
ms.date: 06/11/2020
keywords: powershell, cmdlet
title: Considerações de segurança para comunicação remota do PowerShell usando WinRM
description: Este documento aborda questões, recomendações e práticas recomendadas de segurança ao usar a comunicação remota do PowerShell.
ms.openlocfilehash: 48167bd297905883b3d75caf9a07d06e6a9fc467
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92501466"
---
# <a name="security-considerations-for-powershell-remoting-using-winrm"></a>Considerações de segurança para comunicação remota do PowerShell usando WinRM

Comunicação remota do PowerShell é a maneira recomendada de gerenciar sistemas Windows. A comunicação remota do PowerShell é habilitada por padrão no Windows Server 2012 R2. Este documento aborda questões, recomendações e práticas recomendadas de segurança ao usar a comunicação remota do PowerShell.

## <a name="what-is-powershell-remoting"></a>O que é a comunicação remota do PowerShell?

A comunicação remota do PowerShell usa o [WinRM (Gerenciamento Remoto do Windows)](/windows/win32/winrm/portal), que é a implementação do protocolo [WS-Management (Serviços Web para Gerenciamento)](https://www.dmtf.org/sites/default/files/standards/documents/DSP0226_1.2.0.pdf) da Microsoft, para permitir que os usuários executem comandos do PowerShell em computadores remotos. Você pode encontrar mais informações sobre como usar a comunicação remota do PowerShell em [Executando comandos remotos](running-remote-commands.md).

A comunicação remota do PowerShell não é igual ao parâmetro **ComputerName** de um cmdlet para executá-lo em um computador remoto, que usa RPC (Chamada de Procedimento Remoto) como seu protocolo subjacente.

## <a name="powershell-remoting-default-settings"></a>Configurações padrão de comunicação remota do PowerShell

A comunicação remota do PowerShell (e WinRM) escutam nas seguintes portas:

- HTTP: 5985
- HTTPS: 5986

Por padrão, a comunicação remota do PowerShell só permite conexões de membros do grupo de Administradores.
As sessões são iniciadas no contexto do usuário, de modo que todos os controles de acesso do sistema operacional aplicados a usuários individuais e grupos continuam a serem aplicados enquanto conectados via comunicação remota do PowerShell.

Em redes privadas, a regra de Firewall do Windows padrão para comunicação remota do PowerShell aceita todas as conexões. Em redes públicas, a regra padrão do Firewall do Windows permite as conexões da comunicação remota do PowerShell somente dentro da mesma sub-rede. Você precisa alterar explicitamente a regra para abrir a comunicação remota do PowerShell para todas as conexões em uma rede pública.

> [!Warning]
> a regra de firewall para redes públicas destina-se a proteger o computador contra tentativas de conexão externa potencialmente mal-intencionada. Tenha cuidado ao remover essa regra.

## <a name="process-isolation"></a>Isolamento do processo

A comunicação remota do PowerShell usa o WinRM para a comunicação entre computadores. O WinRM é executado como um serviço na conta de serviço de rede e gera processos isolados executados como contas de usuário para hospedar instâncias do PowerShell. Uma instância do PowerShell em execução como um usuário não tem acesso a um processo que executa uma instância do PowerShell como outro usuário.

## <a name="event-logs-generated-by-powershell-remoting"></a>Logs de eventos gerados pela comunicação remota do PowerShell

O FireEye forneceu um bom resumo dos logs de eventos e outras evidências de segurança gerados pelas sessões remotas do PowerShell, disponíveis no white paper [Investigando ataques ao PowerShell](https://www.fireeye.com/content/dam/fireeye-www/global/en/solutions/pdfs/wp-lazanciyan-investigating-powershell-attacks.pdf).

## <a name="encryption-and-transport-protocols"></a>Protocolos de transporte e criptografia

Vale a pena considerar a segurança de uma conexão de comunicação remota do PowerShell de duas perspectivas: autenticação inicial e comunicação em andamento.

Independentemente do protocolo de transporte usado (HTTP ou HTTPS), o WinRM sempre criptografa toda a comunicação remota do PowerShell após a autenticação inicial.

### <a name="initial-authentication"></a>Autenticação inicial

A autenticação confirma a identidade do cliente para o servidor - e idealmente - do servidor para o cliente.

Quando um cliente se conecta a um servidor de domínio usando o nome do computador dele, o protocolo de autenticação padrão é [Kerberos](/windows/win32/secauthn/microsoft-kerberos). Kerberos garante a identidade do usuário e a identidade do servidor sem enviar qualquer tipo de credencial reutilizável.

Quando um cliente se conecta a um servidor de domínio usando seu endereço IP, ou se conecta a um servidor de grupo de trabalho, a autenticação Kerberos não é possível. Nesse caso, a comunicação remoto do PowerShell depende do [protocolo de autenticação NTLM](/windows/win32/secauthn/microsoft-ntlm). O protocolo de autenticação NTLM garante a identidade do usuário sem enviar qualquer tipo de credencial delegável. Para provar a identidade do usuário, o protocolo NTLM exige que o cliente e o servidor computem uma chave de sessão da senha do usuário sem nunca trocar a senha. O servidor normalmente não sabe a senha do usuário, de modo que ele se comunica com o controlador de domínio, que sabe a senha do usuário e calcula a chave de sessão para o servidor.

No entanto, o protocolo NTLM não assegura a identidade do servidor. Como ocorre com todos os protocolos que usam NTLM para autenticação, um invasor com acesso a uma conta do computador ingressado do domínio pode invocar o controlador de domínio para computar uma chave de sessão NTLM e, assim, representar o servidor.

A autenticação baseada em NTLM está desabilitada por padrão, mas pode ser permitida ao configurar SSL no servidor de destino, ou ao definir a configuração de WinRM TrustedHosts no cliente.

#### <a name="using-ssl-certificates-to-validate-server-identity-during-ntlm-based-connections"></a>Usando certificados SSL para validar a identidade do servidor durante conexões baseadas em NTLM

Como o protocolo de autenticação NTLM não pode garantir a identidade do servidor de destino (somente que ele já sabe sua senha), você pode configurar servidores de destino para usar SSL na comunicação remota do PowerShell.
Atribuir um certificado SSL ao servidor de destino (se emitido por uma autoridade de certificação em que o cliente também confia) permite a autenticação baseada em NTLM, que garante a identidade do usuário e do servidor.

#### <a name="ignoring-ntlm-based-server-identity-errors"></a>Ignorando erros de identidade de servidor baseada em NTLM

Se for inviável implantar um certificado SSL em um servidor para conexões de NTLM, você poderá suprimir os erros de identidade resultantes adicionando o servidor à lista **TrustedHosts** do WinRM. Observe que a adição de um nome do servidor à lista **TrustedHosts** não deve ser considerada uma forma de declaração da confiabilidade dos próprios hosts, pois o protocolo de autenticação NTLM não pode garantir que você realmente esteja se conectando com o host com o qual pretende se conectar. Em vez disso, você deve considerar a configuração TrustedHosts como a lista de hosts para a qual você deseja suprimir o erro gerado por não ter sido capaz de verificar a identidade do servidor.

### <a name="ongoing-communication"></a>Comunicação em andamento

Depois que a autenticação inicial é concluída, o WinRM criptografa a comunicação em andamento. Na conexão por HTTPS, o protocolo TLS é usado para negociar a criptografia usada para transportar dados.
Na conexão por HTTP, a criptografia no nível da mensagem é determinada pelo protocolo de autenticação inicial usado.

- A autenticação básica não fornece nenhuma criptografia.
- A autenticação NTLM usa uma criptografia RC4 com uma chave de 128 bits.
- A criptografia de autenticação Kerberos é determinada pelo `etype` no tíquete TGS. Esse é o AES-256 nos sistemas modernos.
- A criptografia CredSSP usa o conjunto de criptografia TLS que foi negociado no handshake.

## <a name="making-the-second-hop"></a>Dando o segundo salto

Por padrão, a comunicação remota do PowerShell usa o Kerberos (se disponível) ou o NTLM para autenticação. Ambos os protocolos autenticam o computador remoto sem enviar as credenciais para ele. Essa é a maneira mais segura de autenticar, mas como o computador remoto não tem as credenciais do usuário, não é possível acessar outros computadores e serviços em nome do usuário. Isso é conhecido como o "problema do segundo salto".

Há várias maneiras de evitar esse problema. Para obter descrições desses métodos e os prós e contras de cada um, consulte [Dando o segundo salto na Comunicação Remota do PowerShell](PS-remoting-second-hop.md).

## <a name="references"></a>Referências

- [Gerenciamento Remoto do Windows (WinRM)](/windows/win32/winrm/portal)
- [Serviços Web para Gerenciamento (WS-Management)](https://www.dmtf.org/sites/default/files/standards/documents/DSP0226_1.2.0.pdf)
- [2.2.9.1 Tipos de mensagem de criptografia](/openspecs/windows_protocols/ms-wsmv/58421aa4-861a-4410-831a-c999f094cdb7)
- [Kerberos](/windows/win32/secauthn/microsoft-kerberos)
- [Protocolo de autenticação NTLM](/windows/win32/secauthn/microsoft-ntlm)
- [Como investigar os ataques do PowerShell](https://www.fireeye.com/content/dam/fireeye-www/global/en/solutions/pdfs/wp-lazanciyan-investigating-powershell-attacks.pdf)
