---
description: Descreve como solucionar problemas de operações remotas no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Troubleshooting
ms.openlocfilehash: b78f3004e316b6d4de1082b914970d3c8b56f955
ms.sourcegitcommit: c1e4739f5d52282fb05a8cff92b0f5d10e2edac1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/29/2020
ms.locfileid: "93196659"
---
# <a name="about-remote-troubleshooting"></a>Sobre a solução de problemas remoto

## <a name="short-description"></a>Descrição breve
Descreve como solucionar problemas de operações remotas no PowerShell.

## <a name="long-description"></a>Descrição longa

Esta seção descreve alguns dos problemas que você pode encontrar ao usar os recursos de comunicação remota do PowerShell baseados em tecnologia de WS-Management e ele sugere soluções para esses problemas.

Antes de usar a comunicação remota do PowerShell, consulte [about_Remote](about_remote.md) e [about_Remote_Requirements](about_Remote_Requirements.md) para obter diretrizes sobre a configuração e o uso básico. Além disso, os tópicos de ajuda para cada um dos cmdlets de comunicação remota, especialmente as descrições de parâmetro, têm informações úteis que são projetadas para ajudá-lo a evitar problemas.

> [!NOTE]
> Para exibir ou alterar as configurações do computador local na unidade WSMan:, incluindo alterações nas configurações de sessão, hosts confiáveis, portas ou ouvintes, inicie o PowerShell com a opção **Executar como administrador** .

## <a name="troubleshooting-permission-and-authentication-issues"></a>Solucionando problemas de permissão e autenticação

Esta seção aborda problemas de comunicação remota relacionados a permissões de usuário e computador e a requisitos de comunicação remota.

### <a name="how-to-run-as-administrator"></a>Como executar como administrador

```
ERROR: Access is denied. You need to run this cmdlet from an elevated
process.
```

Para iniciar uma sessão remota no computador local ou para exibir ou alterar as configurações do computador local na unidade WSMan:, incluindo alterações nas configurações de sessão, hosts confiáveis, portas ou ouvintes, inicie o Windows PowerShell com a opção **Executar como administrador** .

Para iniciar o Windows PowerShell com a opção **Executar como administrador** :

- Clique com o botão direito do mouse em um ícone do Windows PowerShell (ou ISE do Windows PowerShell) e clique em **Executar como administrador** .

  Para iniciar o Windows PowerShell com a opção **Executar como administrador** no Windows 7 e no windows Server 2008 R2.

- Na barra de tarefas do Windows, clique com o botão direito do mouse no ícone do Windows PowerShell e clique em **Executar como administrador** .

  No Windows Server 2008 R2, o ícone do Windows PowerShell é fixado na barra de tarefas por padrão.

### <a name="how-to-enable-remoting"></a>Como habilitar a comunicação remota

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to
listen for requests on the correct port and HTTP URL.
```

Nenhuma configuração é necessária para permitir que um computador envie comandos remotos.
No entanto, para receber comandos remotos, a comunicação remota do PowerShell deve estar habilitada no computador. A habilitação inclui a inicialização do serviço WinRM, a definição do tipo de inicialização para o serviço WinRM como automático, a criação de ouvintes para conexões HTTP e HTTPS e a criação de configurações de sessão padrão.

A comunicação remota do Windows PowerShell está habilitada no Windows Server 2012 e em versões mais recentes do Windows Server por padrão. Em todos os outros sistemas, execute o `Enable-PSRemoting` cmdlet para habilitar a comunicação remota. Também é possível executar o `Enable-PSRemoting` cmdlet para reabilitar a comunicação remota no Windows server 2012 e versões mais recentes do Windows Server se a comunicação remota estiver desabilitada.

Para configurar um computador para receber comandos remotos, use o `Enable-PSRemoting` cmdlet. O comando a seguir habilita todas as configurações remotas necessárias, habilita as configurações de sessão e reinicia o serviço WinRM para que as alterações entrem em vigor.

`Enable-PSRemoting`

Para suprimir todos os prompts de usuário, digite:

`Enable-PSRemoting -Force`

Para obter mais informações, consulte [Enable-PSRemoting](xref:Microsoft.PowerShell.Core.Enable-PSRemoting).

### <a name="how-to-enable-remoting-in-an-enterprise"></a>Como habilitar a comunicação remota em uma empresa

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

Para permitir que um único computador receba comandos remotos do PowerShell e aceite conexões, use o `Enable-PSRemoting` cmdlet.

Para habilitar a comunicação remota para vários computadores em uma empresa, você pode usar as seguintes opções de escala.

- Para configurar ouvintes para comunicação remota, habilite a política **de grupo permitir configuração automática de ouvintes** .

- Para definir o tipo de inicialização do Gerenciamento Remoto do Windows (WinRM) como automático em vários computadores, use o `Set-Service` cmdlet.

- Para habilitar uma exceção de firewall, use a política de grupo **Firewall do Windows: permitir exceções de porta local** .

### <a name="how-to-enable-listeners-by-using-a-group-policy"></a>Como habilitar ouvintes usando uma política de grupo

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

Para configurar os ouvintes para todos os computadores em um domínio, habilite a política **permitir configuração automática de ouvintes** no seguinte caminho de política de Grupo:

```
Computer Configuration\Administrative Templates\Windows Components
    \Windows Remote Management (WinRM)\WinRM service
```

Habilite a política e especifique os filtros IPv4 e IPv6. Caracteres curinga ( `*` ) são permitidos.

### <a name="how-to-enable-remoting-on-public-networks"></a>Como habilitar a comunicação remota em redes públicas

```
ERROR:  Unable to check the status of the firewall
```

O `Enable-PSRemoting` cmdlet retorna esse erro quando a rede local é pública e o parâmetro **SkipNetworkProfileCheck** não é usado no comando.

Em versões de servidor do Windows, o tem `Enable-PSRemoting` sucesso em todos os tipos de local de rede. Ele cria regras de firewall que permitem acesso remoto a redes privadas e de domínio ("página inicial" e "trabalho"). Para redes públicas, ele cria regras de firewall que permitem o acesso remoto da mesma sub-rede local.

Nas versões cliente do Windows, o é `Enable-PSRemoting` bem sucedido em redes privadas e de domínio. Por padrão, ele falha em redes públicas, mas se você usar o parâmetro **SkipNetworkProfileCheck** , o `Enable-PSRemoting` terá êxito e criará uma regra de firewall que permite o tráfego da mesma sub-rede local.

Para remover a restrição de sub-rede local em redes públicas e permitir o acesso remoto de qualquer local, execute o seguinte comando:

```powershell
Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any
```

O `Set-NetFirewallRule` cmdlet é exportado pelo módulo NetSecurity.

> [!NOTE]
> No Windows PowerShell 2,0, em computadores que executam versões de servidor do Windows, o `Enable-PSRemoting` cria regras de firewall que permitem o acesso remoto em redes privadas, de domínio e públicas. Em computadores que executam versões cliente do Windows, o `Enable-PSRemoting` cria regras de firewall que permitem o acesso remoto somente em redes privadas e de domínio.

### <a name="how-to-enable-a-firewall-exception-by-using-a-group-policy"></a>Como habilitar uma exceção de firewall usando uma política de grupo

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

Para habilitar uma exceção de firewall para o em todos os computadores em um domínio, habilite a política **Firewall do Windows: permitir exceções de porta local** no seguinte caminho de política de Grupo:

```
Computer Configuration\Administrative Templates\Network
    \Network Connections\Windows Firewall\Domain Profile
```

Essa política permite que os membros do grupo Administradores no computador usem o **Firewall do Windows** no **painel de controle** para criar uma exceção de firewall para o serviço de gerenciamento remoto do Windows.

Se a configuração da política estiver incorreta, você poderá receber o seguinte erro:

```
The client cannot connect to the destination specified in the request. Verify
that the service on the destination is running and is accepting requests.
```

Um erro de configuração na política resulta em um valor vazio para a propriedade **listening** . Use o comando a seguir para verificar o valor.

```powershell
PS> Get-WSManInstance winrm/config/listener -Enumerate

cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
Source                : GPO
lang                  : en-US
Address               : *
Transport             : HTTP
Port                  : 5985
Hostname              :
Enabled               : true
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {}
```

### <a name="how-to-set-the-startup-type-of-the-winrm-service"></a>Como definir o tipo de inicialização do serviço WinRM

```
ERROR:  ACCESS IS DENIED
```

A comunicação remota do PowerShell depende do serviço de Gerenciamento Remoto do Windows (WinRM).
O serviço deve estar em execução para dar suporte a comandos remotos.

Nas versões de servidor do Windows, o tipo de inicialização do serviço de Gerenciamento Remoto do Windows (WinRM) é automático.

No entanto, nas versões cliente do Windows, o serviço WinRM é desabilitado por padrão.

Para definir o tipo de inicialização de um serviço em um computador remoto, use o `Set-Service` cmdlet.

Para executar o comando em vários computadores, você pode criar um arquivo de texto ou arquivo CSV dos nomes dos computadores.

Por exemplo, os comandos a seguir obtêm uma lista de nomes de computador do `Servers.txt` arquivo e, em seguida, definem o tipo de inicialização do serviço WinRM em todos os computadores como **automáticos** .

```powershell
$servers = Get-Content servers.txt
Set-Service WinRM -ComputerName $servers -startuptype Automatic
```

Para ver os resultados, use o `Get-WMIObject` cmdlet com o objeto **Win32_Service** . Para obter mais informações, consulte [Set-Service](xref:Microsoft.PowerShell.Management.Set-Service).

### <a name="how-to-recreate-the-default-session-configurations"></a>Como recriar as configurações de sessão padrão

```
ERROR:  ACCESS IS DENIED
```

Para se conectar ao computador local e executar comandos remotamente, o computador local deve incluir configurações de sessão para comandos remotos.

Quando você usa `Enable-PSRemoting` o, ele cria configurações de sessão padrão no computador local. Os usuários remotos usam essas configurações de sessão sempre que um comando remoto não inclui o parâmetro **ConfigurationName** .

Se as configurações padrão em um computador tiverem o registro cancelado ou excluído, use o `Enable-PSRemoting` cmdlet para recriá-las. Você pode usar esse cmdlet repetidamente. Ele não gerará erros se um recurso já estiver configurado.

Se você alterar as configurações de sessão padrão e quiser restaurar as configurações de sessão padrão originais, use o `Unregister-PSSessionConfiguration` cmdlet para excluir as configurações de sessão alteradas e, em seguida, use o `Enable-PSRemoting` cmdlet para restaurá-las.
`Enable-PSRemoting` Não altera as configurações de sessão existentes.

> [!NOTE]
> Quando `Enable-PSRemoting` o restaura a configuração de sessão padrão, ele não cria descritores de segurança explícitos para as configurações. Em vez disso, as configurações herdam o descritor de segurança do RootSDDL, que é seguro por padrão.

Para ver o descritor de segurança RootSDDL, digite:

```powershell
Get-Item wsman:\localhost\Service\RootSDDL
```

Para alterar o RootSDDL, use o `Set-Item` cmdlet na unidade WSMan:. Para alterar o descritor de segurança de uma configuração de sessão, use o `Set-PSSessionConfiguration` cmdlet com os parâmetros **SecurityDescriptorSDDL** ou **ShowSecurityDescriptorUI dos** .

Para obter mais informações sobre a unidade WSMan:, consulte o tópico da ajuda para o provedor WSMan ("get-help WSMan").

### <a name="how-to-provide-administrator-credentials"></a>Como fornecer credenciais de administrador

```
ERROR:  ACCESS IS DENIED
```

Para criar uma PSSession ou executar comandos em um computador remoto, por padrão, o usuário atual deve ser um membro do grupo Administradores no computador remoto. Às vezes, as credenciais são necessárias mesmo quando o usuário atual está conectado a uma conta que seja membro do grupo Administradores.

Se o usuário atual for um membro do grupo Administradores no computador remoto, ou puder fornecer as credenciais de um membro do grupo Administradores, use o parâmetro **Credential** dos `New-PSSession` `Enter-PSSession` `Invoke-Command` cmdlets ou para se conectar remotamente.

Por exemplo, o comando a seguir fornece as credenciais de um administrador.

```powershell
Invoke-Command -ComputerName Server01 -Credential Domain01\Admin01
```

Para obter mais informações sobre o parâmetro **Credential** , consulte [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession) ou [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command).

### <a name="how-to-enable-remoting-for-non-administrative-users"></a>Como habilitar a comunicação remota para usuários não administrativos

```
ERROR:  ACCESS IS DENIED
```

Para estabelecer uma PSSession ou executar um comando em um computador remoto, o usuário deve ter permissão para usar as configurações de sessão no computador remoto.

Por padrão, somente os membros do grupo Administradores em um computador têm permissão para usar as configurações de sessão padrão. Portanto, somente os membros do grupo Administradores podem se conectar ao computador remotamente.

Para permitir que outros usuários se conectem ao computador local, dê ao usuário permissões de execução para as configurações de sessão padrão no computador local.

O comando a seguir abre uma folha de propriedades que permite alterar o descritor de segurança da configuração de sessão padrão do Microsoft. PowerShell no computador local.

```powershell
Set-PSSessionConfiguration Microsoft.PowerShell -ShowSecurityDescriptorUI
```

Para obter mais informações, consulte [about_Session_Configurations](about_Session_Configurations.md).

### <a name="how-to-enable-remoting-for-administrators-in-other-domains"></a>Como habilitar a comunicação remota para administradores em outros domínios

```
ERROR:  ACCESS IS DENIED
```

Quando um usuário em outro domínio é membro do grupo Administradores no computador local, o usuário não pode se conectar ao computador local remotamente com privilégios de administrador. Por padrão, conexões remotas de outros domínios são executadas somente com tokens de privilégio de usuário padrão.

No entanto, você pode usar a entrada do registro **LocalAccountTokenFilterPolicy** para alterar o comportamento padrão e permitir que usuários remotos que sejam membros do grupo Administradores sejam executados com privilégios de administrador.

> [!CAUTION]
> A entrada **LocalAccountTokenFilterPolicy** desabilita as restrições remotas do UAC (controle de conta de usuário) para todos os usuários de todos os computadores afetados. Considere as implicações dessa configuração cuidadosamente antes de alterar a política.

Para alterar a política, use o comando a seguir para definir o valor da entrada do registro **LocalAccountTokenFilterPolicy** como 1.

```powershell
New-ItemProperty -Name LocalAccountTokenFilterPolicy `
  -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System `
  -PropertyType DWord -Value 1
```

### <a name="how-to-use-an-ip-address-in-a-remote-command"></a>Como usar um endereço IP em um comando remoto

```
ERROR: The WinRM client cannot process the request. If the authentication
scheme is different from Kerberos, or if the client computer is not joined to a
domain, then HTTPS transport must be used or the destination machine must be
added to the TrustedHosts configuration setting.
```

O parâmetro **ComputerName** dos `New-PSSession` `Enter-PSSession` `Invoke-Command` cmdlets e aceita um endereço IP como um valor válido. No entanto, como a autenticação Kerberos não dá suporte a endereços IP, a autenticação NTLM é usada por padrão sempre que você especifica um endereço IP.

Ao usar a autenticação NTLM, o procedimento a seguir é necessário para comunicação remota.

1. Configure o computador para transporte HTTPS ou adicione os endereços IP dos computadores remotos à lista TrustedHosts no computador local.

1. Use o parâmetro **Credential** em todos os comandos remotos.

   Isso é necessário mesmo quando você está enviando as credenciais do usuário atual.

### <a name="how-to-connect-remotely-from-a-workgroup-based-computer"></a>Como se conectar remotamente de um computador baseado em grupo de trabalho

```
ERROR: The WinRM client cannot process the request. If the authentication
scheme is different from Kerberos, or if the client computer is not joined to a
domain, then HTTPS transport must be used or the destination machine must be
added to the TrustedHosts configuration setting.
```

Quando o computador local não está em um domínio, o procedimento a seguir é necessário para comunicação remota.

1. Configure o computador para transporte HTTPS ou adicione os nomes dos computadores remotos à lista TrustedHosts no computador local.

1. Verifique se uma senha está definida no computador baseado em grupo de trabalho. Se uma senha não estiver definida ou o valor da senha estiver vazio, você não poderá executar comandos remotos.

   Para definir a senha para sua conta de usuário, use contas de usuário no painel de controle.

1. Use o parâmetro **Credential** em todos os comandos remotos.

   Isso é necessário mesmo quando você está enviando as credenciais do usuário atual.

### <a name="how-to-add-a-computer-to-the-trusted-hosts-list"></a>Como adicionar um computador à lista de hosts confiáveis

O item TrustedHosts pode conter uma lista separada por vírgulas de nomes de computador, endereços IP e nomes de domínio totalmente qualificados. Caracteres curinga são permitidos.

Para exibir ou alterar a lista de hosts confiáveis, use a unidade WSMan:. O item TrustedHost está no `WSMan:\localhost\Client` nó.

Somente os membros do grupo Administradores no computador têm permissão para alterar a lista de hosts confiáveis no computador.

Cuidado: o valor que você define para o item TrustedHosts afeta todos os usuários do computador.

Para exibir a lista de hosts confiáveis, use o seguinte comando:

```powershell
Get-Item wsman:\localhost\Client\TrustedHosts
```

Você também pode usar o `Set-Location` cmdlet (alias = CD) para navegar por meio da unidade WSMan: para o local. Por exemplo:

```powershell
cd WSMan:\localhost\Client; dir
```

Para adicionar todos os computadores à lista de hosts confiáveis, use o comando a seguir, que coloca um valor de * (All) no ComputerName

```powershell
Set-Item wsman:localhost\client\trustedhosts -Value *
```

Você também pode usar um caractere curinga ( `*` ) para adicionar todos os computadores em um domínio específico à lista de hosts confiáveis. Por exemplo, o comando a seguir adiciona todos os computadores do domínio fabrikam à lista de hosts confiáveis.

```powershell
Set-Item wsman:localhost\client\trustedhosts *.fabrikam.com
```

Para adicionar os nomes de computadores específicos à lista de hosts confiáveis, use o seguinte formato de comando:

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value <ComputerName>
```

onde cada valor `<ComputerName>` deve ter o seguinte formato:

```
<Computer>.<Domain>.<Company>.<top-level-domain>
```

Por exemplo:

```powershell
$server = 'Server01.Domain01.Fabrikam.com'
Set-Item wsman:\localhost\Client\TrustedHosts -Value $server
```

Para adicionar um nome de computador a uma lista existente de hosts confiáveis, primeiro salve o valor atual em uma variável e, em seguida, defina o valor para uma lista separada por vírgulas que inclui os valores atuais e novos.

Por exemplo, para adicionar o computador Server01 a uma lista de hosts confiáveis existente, use o seguinte comando:

```powershell
$curValue = (Get-Item wsman:\localhost\Client\TrustedHosts).value

Set-Item wsman:\localhost\Client\TrustedHosts -Value `
  "$curValue, Server01.Domain01.Fabrikam.com"
```

Para adicionar os endereços IP de determinados computadores à lista de hosts confiáveis, use o seguinte formato de comando:

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value <IP Address>
```

Por exemplo:

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value 172.16.0.0
```

Para adicionar um computador à lista TrustedHosts de um computador remoto, use o `Connect-WSMan` cmdlet para adicionar um nó do computador remoto à unidade WSMan: no computador local. Em seguida, use um `Set-Item` comando para adicionar o computador.

Para obter mais informações sobre o `Connect-WSMan` cmdlet, consulte [Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan).

## <a name="troubleshooting-computer-configuration-issues"></a>Solucionando problemas de configuração do computador

Esta seção aborda problemas de comunicação remota relacionados a configurações específicas de um computador, domínio ou empresa.

### <a name="how-to-configure-remoting-on-alternate-ports"></a>Como configurar a comunicação remota em portas alternativas

```
ERROR: The connection to the specified remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

A comunicação remota do PowerShell usa a porta 80 para o transporte HTTP por padrão. A porta padrão é usada sempre que o usuário não especificar os parâmetros de **porta** ou **conexãouri** em um comando remoto.

Para alterar a porta padrão usada pelo PowerShell, use `Set-Item` o cmdlet na unidade WSMan: para alterar o valor da porta no nó folha do ouvinte.

Por exemplo, o comando a seguir altera a porta padrão para 8080.

```powershell
Set-Item wsman:\localhost\listener\listener*\port -Value 8080
```

### <a name="how-to-configure-remoting-with-a-proxy-server"></a>Como configurar a comunicação remota com um servidor proxy

```
ERROR: The client cannot connect to the destination specified in the request.
Verify that the service on the destination is running and is accepting
requests.
```

Como a comunicação remota do PowerShell usa o protocolo HTTP, ela é afetada pelas configurações de proxy HTTP. Em empresas que têm servidores proxy, os usuários não podem acessar um computador remoto do PowerShell diretamente.

Para resolver esse problema, use as opções de configuração de proxy no comando remoto. As seguintes configurações estão disponíveis:

- ProxyAccessType
- ProxyAuthentication
- ProxyCredential

Para definir essas opções para um comando específico, use o seguinte procedimento:

1. Use os parâmetros **ProxyAccessType** , **ProxyAuthentication** e **ProxyCredential** do `New-PSSessionOption` cmdlet para criar um objeto de opção de sessão com as configurações de proxy para sua empresa. Salvar o objeto de opção é uma variável.

1. Use a variável que contém o objeto Option como o valor do parâmetro **SessionOption** de um `New-PSSession` comando, `Enter-PSSession` ou `Invoke-Command` .

Por exemplo, o comando a seguir cria um objeto de opção de sessão com opções de sessão de proxy e, em seguida, usa o objeto para criar uma sessão remota.

```powershell
$SessionOption = New-PSSessionOption -ProxyAccessType IEConfig `
-ProxyAuthentication Negotiate -ProxyCredential Domain01\User01

New-PSSession -ConnectionURI https://www.fabrikam.com
```

Para obter mais informações sobre o `New-PSSessionOption` cmdlet, consulte [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).

Para definir essas opções para todos os comandos remotos na sessão atual, use o objeto Option que `New-PSSessionOption` cria no valor da `$PSSessionOption` variável de preferência. Para obter mais informações, consulte [about_Preference_Variables](about_Preference_Variables.md).

Para definir essas opções para todos os comandos remotos todas as sessões do PowerShell no computador local, adicione a `$PSSessionOption` variável de preferência ao seu perfil do PowerShell. Para obter mais informações sobre perfis do PowerShell, consulte [about_Profiles](about_Profiles.md).

### <a name="how-to-detect-a-32-bit-session-on-a-64-bit-computer"></a>Como detectar uma sessão de 32 bits em um computador de 64 bits

```
ERROR: The term "<tool-Name>" is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

Se o computador remoto estiver executando uma versão de 64 bits do Windows, e o comando remoto estiver usando uma configuração de sessão de 32 bits, como Microsoft. PowerShell32, o Gerenciamento Remoto do Windows (WinRM) carregará um processo WOW64 e o Windows redirecionará automaticamente todas as referências ao `$env:Windir\System32` diretório para o `$env:Windir\SysWOW64` diretório.

Como resultado, se você tentar usar as ferramentas no diretório system32 que não têm contrapartes no diretório SysWow64, como `Defrag.exe` , as ferramentas não podem ser encontradas no diretório.

Para localizar a arquitetura do processador que está sendo usada na sessão, use o valor da variável de ambiente **PROCESSOR_ARCHITECTURE** . O comando a seguir localiza a arquitetura do processador da sessão na `$s` variável.

```powershell
$s = New-PSSession -ComputerName Server01 -ConfigurationName CustomShell
Invoke-Command -Session $s {$env:PROCESSOR_ARCHITECTURE}
```

```Output
x86
```

Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](about_Session_Configurations.md).

## <a name="troubleshooting-policy-and-preference-issues"></a>Solucionando problemas de política e problemas de preferência

Esta seção aborda problemas de comunicação remota relacionados a políticas e preferências definidas nos computadores locais e remotos.

### <a name="how-to-change-the-execution-policy-for-import-pssession-and-import-module"></a>Como alterar a política de execução para Import-PSSession e Import-Module

```
ERROR: Import-Module: File <filename> cannot be loaded because the
execution of scripts is disabled on this system.
```

Os `Import-PSSession` `Export-PSSession` cmdlets e criam módulos que contêm arquivos de script não assinados e arquivos de formatação.

Para importar os módulos criados por esses cmdlets, usando `Import-PSSession` `Import-Module` o ou o, a política de execução na sessão atual não pode ser restrita ou AllSigned. Para obter informações sobre as políticas de execução do PowerShell, consulte [about_Execution_Policies](about_Execution_Policies.md).

Para importar os módulos sem alterar a política de execução para o computador local definido no registro, use o parâmetro **Scope** de `Set-ExecutionPolicy` para definir uma política de execução menos restritiva para um único processo.

Por exemplo, o comando a seguir inicia um processo com a `RemoteSigned` política de execução. A alteração da política de execução afeta apenas o processo atual e não altera a configuração do registro **ExecutionPolicy** do PowerShell.

```powershell
Set-ExecutionPolicy -Scope process -ExecutionPolicy RemoteSigned
```

Você também pode usar o parâmetro **ExecutionPolicy** do `PowerShell.exe` para iniciar uma única sessão com uma política de execução menos restritiva.

```powershell
PowerShell.exe -ExecutionPolicy RemoteSigned
```

Para obter mais informações sobre políticas de execução, consulte [about_Execution_Policies](about_Execution_Policies.md). Para obter mais informações, digite `PowerShell.exe -?`.

### <a name="how-to-set-and-change-quotas"></a>Como definir e alterar cotas

```
ERROR: The total data received from the remote client exceeded allowed
maximum.
```

Você pode usar cotas para proteger o computador local e o computador remoto contra o uso excessivo de recursos, acidental e mal-intencionado.

As cotas a seguir estão disponíveis na configuração básica.

- O provedor WSMan (WSMan:) fornece várias configurações de cota, como as configurações de **MaxEnvelopeSizeKB** e **MaxProviderRequests** no `WSMan:<ComputerName>` nó e as configurações de **MaxConcurrentOperations** , **MaxConcurrentOperationsPerUser** e **MaxConnections** no `WSMan:<ComputerName>\Service` nó.

- Você pode proteger o computador local usando os parâmetros **MaximumReceivedDataSizePerCommand** e **MaximumReceivedObjectSize** do `New-PSSessionOption` cmdlet e a variável de `$PSSessionOption` preferência.

- Você pode proteger o computador remoto adicionando restrições às configurações de sessão, como usando os parâmetros **MaximumReceivedDataSizePerCommandMB** e **MaximumReceivedObjectSizeMB** do `Register-PSSessionConfiguration` cmdlet.

Quando as cotas entram em conflito com um comando, o PowerShell gera um erro.

Para resolver o erro, altere o comando remoto para que ele esteja em conformidade com a cota. Ou determine a origem da cota e, em seguida, aumente a cota para permitir que o comando seja concluído.

Por exemplo, o comando a seguir aumenta a cota de tamanho do objeto na configuração de sessão do Microsoft. PowerShell no computador remoto de 10 MB (o valor padrão) para 11 MB.

```powershell
Set-PSSessionConfiguration -Name microsoft.PowerShell `
  -MaximumReceivedObjectSizeMB 11 -Force
```

Para obter mais informações sobre o `New-PSSessionOption` cmdlet, consulte `New-PSSessionOption` .

Para obter mais informações sobre as cotas de WS-Management, consulte [about_WSMan_Provider](../../Microsoft.WsMan.Management/About/about_WSMan_Provider.md).

### <a name="how-to-resolve-timeout-errors"></a>Como resolver erros de tempo limite

```
ERROR: The WS-Management service cannot complete the operation within
the time specified in OperationTimeout.
```

Você pode usar tempos limite para proteger o computador local e o computador remoto contra o uso excessivo de recursos, acidental e mal-intencionado. Quando os tempos limite são definidos no computador local e remoto, o PowerShell usa as configurações de tempo limite mais curtas.

Os tempos limite a seguir estão disponíveis na configuração básica.

- O provedor WSMan (WSMan:) fornece várias configurações do lado do cliente e do tempo limite do lado do serviço, como a configuração **MaxTimeoutms** no `WSMan:<ComputerName>` nó e as configurações **EnumerationTimeoutms** e **MaxPacketRetrievalTimeSeconds** no `WSMan:<ComputerName>\Service` nó.

- Você pode proteger o computador local usando os parâmetros **CancelTimeout** , **IdleTimeout** , **OpenTimeout** e **OperationTimeout** do `New-PSSessionOption` cmdlet e a `$PSSessionOption` variável de preferência.

- Você também pode proteger o computador remoto definindo valores de tempo limite programaticamente na configuração de sessão para a sessão.

Quando um valor de tempo limite não permite que uma operação seja concluída, o PowerShell encerra a operação e gera um erro.

Para resolver o erro, altere o comando para concluir dentro do intervalo de tempo limite ou determine a origem do limite de tempo limite e aumente o intervalo de tempo limite para permitir que o comando seja concluído.

Por exemplo, os comandos a seguir usam o `New-PSSessionOption` cmdlet para criar um objeto de opção de sessão com um valor de **OperationTimeout** de 4 minutos (em MS) e, em seguida, usar o objeto de opção de sessão para criar uma sessão remota.

```powershell
$pso = New-PSSessionoption -OperationTimeout 240000

New-PSSession -ComputerName Server01 -sessionOption $pso
```

Para obter mais informações sobre o tempo limite do WS-Management, consulte o tópico da ajuda para o provedor WSMan (tipo `Get-Help WSMan` ).

Para obter mais informações sobre o `New-PSSessionOption` cmdlet, consulte [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).

## <a name="troubleshooting-unresponsive-behavior"></a>Solucionando problemas de comportamento sem resposta

Esta seção aborda problemas de comunicação remota que impedem que um comando conclua e impeça ou atrase o retorno do prompt do PowerShell.

### <a name="how-to-interrupt-a-command"></a>Como interromper um comando

Alguns programas nativos do Windows, como programas com uma interface do usuário, aplicativos de console que solicitam entrada e aplicativos de console que usam a API do console Win32, não funcionam corretamente no host remoto do PowerShell.

Ao usar esses programas, você poderá ver um comportamento inesperado, como nenhuma saída, saída parcial ou um comando remoto que não é concluído.

Para encerrar um programa sem resposta, digite <kbd>Ctrl</kbd> + <kbd>C</kbd>. Para exibir os erros que podem ter sido relatados, digite `$error` o host local e a sessão remota.

## <a name="how-to-recover-from-an-operation-failure"></a>Como recuperar-se de uma falha de operação

```
ERROR: The I/O operation has been aborted because of either a thread exit
or an  application request.
```

Esse erro é retornado quando uma operação é encerrada antes de ser concluída.
Normalmente, ocorre quando o serviço WinRM para ou é reiniciado enquanto outras operações do WinRM estão em andamento.

Para resolver esse problema, verifique se o serviço WinRM está em execução e tente o comando novamente.

1. Inicie o PowerShell com a opção **Executar como administrador** .
1. Execute o seguinte comando:

   `Start-Service WinRM`

1. Execute novamente o comando que gerou o erro.

## <a name="linux-and-macos-limitations"></a>Limitações do Linux e do macOS

### <a name="authentication"></a>Autenticação

Somente a autenticação básica funciona no macOS e a tentativa de usar outros esquemas de autenticação pode resultar na falha do processo.

Consulte as instruções de [autenticação do OMI](https://github.com/PowerShell/psl-omi-provider#connecting-from-linux-to-windows) .

## <a name="see-also"></a>CONSULTE TAMBÉM

[Import-PSSession](xref:Microsoft.PowerShell.Utility.Import-PSSession)

[Export-PSSession](xref:Microsoft.PowerShell.Utility.Export-PSSession)

[Import-Module](xref:Microsoft.PowerShell.Core.Import-Module)

[about_Remote](about_Remote.md)

[about_Remote_Requirements](about_Remote_Requirements.md)

[about_Remote_Variables](about_Remote_Variables.md)
