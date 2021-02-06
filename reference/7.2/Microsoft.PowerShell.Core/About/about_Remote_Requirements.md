---
description: Descreve os requisitos de sistema e os requisitos de configuração para executar comandos remotos no PowerShell.
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_requirements?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Requirements
ms.openlocfilehash: 4a994ded51195e5932af7bb4af0b2e6fb3a67857
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596574"
---
# <a name="about-remote-requirements"></a>Sobre requisitos remotos

## <a name="short-description"></a>DESCRIÇÃO BREVE
Descreve os requisitos de sistema e os requisitos de configuração para executar comandos remotos no PowerShell.

## <a name="long-description"></a>DESCRIÇÃO LONGA

Este tópico descreve os requisitos de sistema, os requisitos de usuário e os requisitos de recursos para estabelecer conexões remotas e executar comandos remotos no PowerShell. Ele também fornece instruções para configurar operações remotas.

Observação: muitos cmdlets (incluindo o Get-Service, o Get-Process, o Get-WMIObject, o Get-EventLog e os cmdlets Get-WinEvent) obtêm objetos de computadores remotos usando métodos de Microsoft .NET Framework para recuperar os objetos. Eles não usam a infraestrutura de comunicação remota do PowerShell. Os requisitos deste documento não se aplicam a esses cmdlets.

Para localizar os cmdlets que têm um parâmetro ComputerName, mas não usam a comunicação remota do PowerShell, leia a descrição do parâmetro ComputerName dos cmdlets.

## <a name="system-requirements"></a>REQUISITOS DO SISTEMA

Para executar sessões remotas no Windows PowerShell 3,0, os computadores locais e remotos devem ter o seguinte:

- Windows PowerShell 3,0 ou posterior
- O Microsoft .NET Framework 4 ou posterior
- Gerenciamento Remoto do Windows 3,0

Para executar sessões remotas no Windows PowerShell 2,0, os computadores locais e remotos devem ter o seguinte:

- Windows PowerShell 2,0 ou posterior
- O Microsoft .NET Framework 2,0 ou posterior
- Gerenciamento Remoto do Windows 2,0

Você pode criar sessões remotas entre computadores que executam o Windows PowerShell 2,0 e o Windows PowerShell 3,0. No entanto, os recursos que são executados somente no Windows PowerShell 3,0, como a capacidade de desconectar e reconectar-se a sessões, estão disponíveis somente quando ambos os computadores executam o Windows PowerShell 3,0.

Para localizar o número de versão de uma versão instalada do PowerShell, use a variável automática $PSVersionTable.

Gerenciamento Remoto do Windows (WinRM) 3,0 e Microsoft .NET Framework 4 estão incluídos no Windows 8, no Windows Server 2012 e em versões mais recentes do sistema operacional Windows. O WinRM 3,0 está incluído no Windows Management Framework 3,0 para sistemas operacionais mais antigos. Se o computador não tiver a versão necessária do WinRM ou a estrutura de Microsoft .NET, a instalação falhará.

## <a name="user-permissions"></a>PERMISSÕES DO USUÁRIO

Para criar sessões remotas e executar comandos remotos, por padrão, o usuário atual deve ser um membro do grupo Administradores no computador remoto ou fornecer as credenciais de um administrador. Caso contrário, o comando falhará.

As permissões necessárias para criar sessões e executar comandos em um computador remoto (ou em uma sessão remota no computador local) são estabelecidas pela configuração de sessão (também conhecida como "ponto de extremidade") no computador remoto ao qual a sessão se conecta. Especificamente, o descritor de segurança na configuração da sessão determina quem tem acesso à configuração de sessão e quem pode usá-la para se conectar.

Os descritores de segurança nas configurações de sessão padrão, Microsoft. PowerShell, Microsoft. PowerShell32 e Microsoft. PowerShell. Workflow, permitem acesso somente aos membros do grupo Administradores.

Se o usuário atual não tiver permissão para usar a configuração de sessão, o comando para executar um comando (que usa uma sessão temporária) ou criar uma sessão persistente no computador remoto falhará. O usuário pode usar o parâmetro ConfigurationName de cmdlets que criam sessões para selecionar uma configuração de sessão diferente, se houver uma disponível.

Os membros do grupo Administradores em um computador podem determinar quem tem permissão para se conectar ao computador remotamente, alterando os descritores de segurança nas configurações de sessão padrão e criando novas configurações de sessão com descritores de segurança diferentes.

Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](about_Session_Configurations.md).

## <a name="windows-network-locations"></a>LOCAIS DE REDE DO WINDOWS

A partir do Windows PowerShell 3,0, o cmdlet Enable-PSRemoting pode habilitar a comunicação remota em versões de cliente e servidor do Windows em redes privadas, de domínio e públicas.

Em versões de servidor do Windows com redes privadas e de domínio, o cmdlet Enable-PSRemoting cria regras de firewall que permitem acesso remoto irrestrito. Ele também cria uma regra de firewall para redes públicas que permite o acesso remoto somente de computadores na mesma sub-rede local. Essa regra de firewall de sub-rede local é habilitada por padrão nas versões de servidor do Windows em redes públicas, mas Enable-PSRemoting reaplica a regra caso ela tenha sido alterada ou excluída.

Em versões de cliente do Windows com redes privadas e de domínio, por padrão, o cmdlet Enable-PSRemoting cria regras de firewall que permitem acesso remoto irrestrito.

Para habilitar a comunicação remota em versões de cliente do Windows com redes públicas, use o parâmetro SkipNetworkProfileCheck do cmdlet Enable-PSRemoting. Ele cria uma regra de firewall que permite o acesso remoto somente de computadores na mesma sub-rede local.

Para remover a restrição de sub-rede local em redes públicas e permitir o acesso remoto de todos os locais nas versões de cliente e servidor do Windows, use o cmdlet Set-NetFirewallRule no módulo NetSecurity. Execute o comando a seguir:

```powershell
Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any
```

No Windows PowerShell 2,0, em versões de servidor do Windows, Enable-PSRemoting cria regras de firewall que permitem o acesso remoto em todas as redes.

No Windows PowerShell 2,0, em versões de cliente do Windows, Enable-PSRemoting cria regras de firewall somente em redes privadas e de domínio. Se o local de rede for público, Enable-PSRemoting falhará.

## <a name="run-as-administrator"></a>EXECUTAR COMO ADMINISTRADOR

São necessários privilégios de administrador para as seguintes operações de comunicação remota:

- Estabelecendo uma conexão remota com o computador local. Isso é normalmente conhecido como um cenário de "Loopback".

- Gerenciamento de configurações de sessão no computador local.

- Exibir e alterar as configurações de WS-Management no computador local. Essas são as configurações no nó LocalHost da unidade WSMAN:.

Para executar essas tarefas, você deve iniciar o PowerShell com a opção "executar como administrador", mesmo se você for um membro do grupo de administradores no computador local.

No Windows 7 e no Windows Server 2008 R2, para iniciar o Windows PowerShell com a opção "executar como administrador":

1. Clique em Iniciar, em todos os programas, em acessórios e, em seguida, clique na pasta Windows PowerShell.
2. Clique com o botão direito do mouse em Windows PowerShell e clique em "executar como administrador".

Para iniciar o Windows PowerShell com a opção "executar como administrador":

1. Clique em Iniciar, todos os programas e, em seguida, clique na pasta Windows PowerShell.
2. Clique com o botão direito do mouse em Windows PowerShell e clique em "executar como administrador".

A opção "executar como administrador" também está disponível em outras entradas do Windows Explorer para o Windows PowerShell, incluindo atalhos. Basta clicar com o botão direito do mouse no item e clicar em "executar como administrador".

Quando você inicia o Windows PowerShell de outro programa, como Cmd.exe, use a opção "executar como administrador" para iniciar o programa.

## <a name="how-to-configure-your-computer-for-remoting"></a>COMO CONFIGURAR SEU COMPUTADOR PARA COMUNICAÇÃO REMOTA

Os computadores que executam todas as versões com suporte do Windows podem estabelecer conexões remotas e executar comandos remotos no PowerShell sem nenhuma configuração. No entanto, para receber conexões e permitir que os usuários criem sessões locais e remotas do PowerShell gerenciadas pelo usuário ("PSSessions") e executem comandos no computador local, você deve habilitar a comunicação remota do PowerShell no computador.

O Windows Server 2012 e versões mais recentes do Windows Server são habilitados para a comunicação remota do PowerShell por padrão. Se as configurações forem alteradas, você poderá restaurar as configurações padrão executando o cmdlet Enable-PSRemoting.

Em todas as outras versões com suporte do Windows, você precisa executar o cmdlet Enable-PSRemoting para habilitar a comunicação remota do PowerShell.

Os recursos de comunicação remota do PowerShell têm suporte do serviço WinRM, que é a implementação da Microsoft do protocolo WS-Management (Web Services for Management). Ao habilitar a comunicação remota do PowerShell, você altera a configuração padrão de WS-Management e adiciona a configuração do sistema que permite que os usuários se conectem ao WS-Management.

Para configurar o PowerShell para receber comandos remotos:

1. Inicie o PowerShell com a opção "executar como administrador".
2. No prompt de comando, digite: `Enable-PSRemoting`

Para verificar se a comunicação remota está configurada corretamente, execute um comando de teste, como o comando a seguir, que cria uma sessão remota no computador local.

```powershell
New-PSSession
```

Se a comunicação remota estiver configurada corretamente, o comando criará uma sessão no computador local e retornará um objeto que representa a sessão. A saída deve se parecer com a seguinte saída de exemplo:

```output
Id Name        ComputerName    State    ConfigurationName
-- ----        ------------    -----    -----
1  Session1    localhost       Opened   Microsoft.PowerShell
```

Se o comando falhar, para obter assistência, consulte [about_Remote_Troubleshooting](about_Remote_Troubleshooting.md).

## <a name="understand-policies"></a>ENTENDER AS POLÍTICAS

Quando você trabalha remotamente, usa duas instâncias do PowerShell, uma no computador local e outra no computador remoto. Como resultado, seu trabalho é afetado pelas políticas do Windows e pelas políticas do PowerShell nos computadores locais e remotos.

Em geral, antes de se conectar e enquanto você estiver estabelecendo a conexão, as políticas no computador local estarão em vigor. Quando você estiver usando a conexão, as políticas no computador remoto estarão em vigor.

## <a name="basic-authentication-limitations-on-linux-and-macos"></a>Limitações de autenticação básica no Linux e no macOS

Ao conectar-se de um sistema Linux ou macOS ao Windows, não há suporte para a autenticação básica sobre HTTP. A autenticação básica pode ser usada em HTTPS por meio da instalação de um certificado no servidor de destino. O certificado deve ter um nome CN que corresponda ao nome de host, não expirado ou revogado. Um certificado autoassinado pode ser usado para fins de teste.

Consulte [como: configurar o WinRM para https](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https) para obter detalhes adicionais.

O comando a seguir, executado em um prompt de comando com privilégios elevados, configurará o ouvinte HTTPS no Windows com o certificado instalado.

```powershell
$hostinfo = '@{Hostname="<DNS_NAME>"; CertificateThumbprint="<THUMBPRINT>"}'
winrm create winrm/config/Listener?Address=*+Transport=HTTPS $hostinfo
```

No lado do Linux ou do macOS, selecione básico para autenticação e-UseSSl.

> Observação: a autenticação básica não pode ser usada com contas de domínio; uma conta local é necessária e a conta deve estar no grupo Administradores.

```powershell
# The specified local user must have administrator rights on the target machine.
# Specify the unqualified username.
$cred = Get-Credential username
$session = New-PSSession -Computer <hostname> -Credential $cred `
  -Authentication Basic -UseSSL
```

Uma alternativa à autenticação básica por HTTPS é Negotiate. Isso resulta na autenticação NTLM entre o cliente e o servidor e a carga é criptografada por HTTP.

O seguinte ilustra o uso de Negotiate com New-PSSession:

```powershell
# The specified user must have administrator rights on the target machine.
$cred = Get-Credential username@hostname
$session = New-PSSession -Computer <hostname> -Credential $cred `
  -Authentication Negotiate
```

> [!NOTE]
> O Windows Server requer uma configuração de registro adicional para permitir que os administradores, além do administrador interno, se conectem usando NTLM.
> Consulte a configuração do Registro LocalAccountTokenFilterPolicy em negociar autenticação em [autenticação para conexões remotas](/windows/win32/winrm/authentication-for-remote-connections)

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_Remote](about_Remote.md)

[about_Remote_Variables](about_Remote_Variables.md)

[about_PSSessions](about_PSSessions.md)

[Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)

[Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)

