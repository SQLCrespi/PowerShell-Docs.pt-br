---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssessionconfiguration?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSessionConfiguration
ms.openlocfilehash: 4cb9c5537673642b74bd8ae03e9f66caf1e873b1
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93194944"
---
# Get-PSSessionConfiguration

## SINOPSE
Obtém as configurações de sessão registradas no computador.

## SYNTAX

```
Get-PSSessionConfiguration [[-Name] <String[]>] [-Force] [<CommonParameters>]
```

## DESCRIPTION

O `Get-PSSessionConfiguration` cmdlet obtém as configurações de sessão que foram registradas no computador local. Esse é um cmdlet avançado projetado para ser utilizado por administradores de sistema a fim de gerenciar configurações de sessão personalizadas para seus usuários.

A partir do PowerShell 3,0, você pode definir as propriedades de uma configuração de sessão usando um arquivo de configuração de sessão (. PSSC). Esse recurso permite criar sessões restritas e personalizadas sem escrever um programa de computador. Para obter mais informações sobre como criar arquivos de configuração, confira [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).

Além disso, a partir do PowerShell 3,0, novas propriedades de observação foram adicionadas ao objeto de configuração de sessão que `Get-PSSessionConfiguration` retorna. Essas propriedades facilitam para os usuários e autores de configuração de sessão examinarem e compararem as configurações de sessão.

Para criar e registrar uma configuração de sessão, use o `Register-PSSessionConfiguration` cmdlet.
Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).

## EXEMPLOS

### Exemplo 1-obter configurações de sessão no computador local

```powershell
Get-PSSessionConfiguration
```

### Exemplo 2-obter as duas configurações de sessão padrão

O comando usa o parâmetro **Name** de `Get-PSSessionConfiguration` para obter apenas as configurações de sessão com nomes que começam com "Microsoft".

```powershell
Get-PSSessionConfiguration -Name Microsoft*
```

```Output
Name                      PSVersion  StartupScript        Permission
----                      ---------  -------------        ----------
microsoft.powershell      5.1                             BUILTIN\Administrators AccessAll...
microsoft.powershell32    5.1                             BUILTIN\Administrators AccessAll...
```

### Exemplo 3-obter as propriedades e os valores de uma configuração de sessão

Este exemplo mostra as propriedades e os valores de propriedade de uma configuração de sessão que foi criada utilizando um arquivo de configuração de sessão.

```powershell
Get-PSSessionConfiguration -Name Full  | Format-List -Property *
```

```Output
Copyright                     : (c) 2011 User01. All rights reserved.
AliasDefinitions              : {System.Collections.Hashtable}
SessionType                   : Default
CompanyName                   : Unknown
GUID                          : 1e9cb265-dae0-4bd3-89a9-8338a47698a1
Author                        : User01
ExecutionPolicy               : Restricted
SchemaVersion                 : 1.0.0.0
LanguageMode                  : FullLanguage
Architecture                  : 64
Filename                      : %windir%\system32\pwrshplugin.dll
ResourceUri                   : http://schemas.microsoft.com/powershell/Full
MaxConcurrentCommandsPerShell : 1500
UseSharedProcess              : false
ProcessIdleTimeoutSec         : 0
xmlns                         : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
MaxConcurrentUsers            : 10
lang                          : en-US
SupportsOptions               : true
ExactMatch                    : true
configfilepath                : C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\Full_1e9cb265-dae0-4bd3-89a9-8338a47698a1.pssc
RunAsUser                     :
IdleTimeoutms                 : 7200000
PSVersion                     : 3.0
OutputBufferingMode           : Block
AutoRestart                   : false
MaxShells                     : 300
MaxMemoryPerShellMB           : 1024
MaxIdleTimeoutms              : 43200000
SDKVersion                    : 1
Name                          : Full
XmlRenderingType              : text
Capability                    : {Shell}
RunAsPassword                 :
MaxProcessesPerShell          : 25
Enabled                       : True
MaxShellsPerUser              : 30
Permission                    :
```

O exemplo usa o `Get-PSSessionConfiguration` cmdlet para obter a configuração de sessão completa. Um operador de pipeline envia a configuração de sessão completa para o `Format-List` cmdlet. O parâmetro **Property** com um valor de `*` (All) direciona `Format-List` para exibir todas as propriedades e valores do objeto em uma lista.

A saída inclui informações úteis, incluindo o autor da configuração de sessão, o tipo de sessão, o modo de linguagem e a política de execução de sessões criadas com essa configuração de sessão, cotas de sessão e o caminho completo para o arquivo de configuração de sessão.

Este modo de exibição de uma configuração de sessão é utilizado para sessões que incluem um arquivo de configuração de sessão.
Para obter mais informações sobre como criar arquivos de configuração, confira [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).

### Exemplo 4-outra maneira de examinar as configurações de sessão

Este exemplo usa o `Get-ChildItem` cmdlet (alias `dir` ) na unidade WSMan: Provider para examinar o conteúdo do nó plugin. Essa é outra maneira para examinar as configurações de sessão no computador.

```powershell
dir wsman:\localhost\plugin
```

```Output
Type            Keys                                Name
----            ----                                ----
Container       {Name=Event Forwarding Plugin}      Event Forwarding Plugin
Container       {Name=Full}                         Full
Container       {Name=microsoft.powershell}         microsoft.powershell
Container       {Name=microsoft.powershell.workf... microsoft.powershell.workflow
Container       {Name=microsoft.powershell32}       microsoft.powershell32
Container       {Name=microsoft.ServerManager}      microsoft.ServerManager
Container       {Name=WMI Provider}                 WMI Provider
```

O nó **plugin** contém objetos **ContainerElement** (Microsoft. WSMan. Management. WSManConfigContainerElement) que representam as configurações de sessão do PowerShell registradas, juntamente com outros plug-ins para WS-Management.

### Exemplo 6-exibir configurações de sessão em um computador remoto

Este exemplo mostra como utilizar o provedor WSMan para exibir as configurações de sessão em um computador remoto. Esse método não fornece tantas informações quanto um `Get-PSSessionConfiguration` comando, mas o usuário não precisa ser um membro do grupo de administradores para executar esse cmdlet.

```powershell
Connect-WSMan -ComputerName Server01
dir WSMan:\Server01\Plugin
```

```Output
   WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin

Type            Keys                                Name
----            ----                                ----
Container       {Name=Empty}                        Empty
Container       {Name=Event Forwarding Plugin}      Event Forwarding Plugin
Container       {Name=Full}                         Full
Container       {Name=microsoft.powershell}         microsoft.powershell
Container       {Name=microsoft.powershell.workf... microsoft.powershell.workflow
Container       {Name=microsoft.powershell32}       microsoft.powershell32
Container       {Name=microsoft.ServerManager}      microsoft.ServerManager
Container       {Name=NoLanguage}                   NoLanguage
Container       {Name=RestrictedLang}               RestrictedLang
Container       {Name=RRS}                          RRS
Container       {Name=SEL Plugin}                   SEL Plugin
Container       {Name=WithProfile}                  WithProfile
Container       {Name=WMI Provider}                 WMI Provider
```

O `Connect-WSMan` cmdlet se conecta ao serviço WinRM no computador remoto Server01. O `Get-ChildItem` cmdlet (alias `dir` ) da unidade WSMan: Obtém os itens no caminho **Server01\Plugin** . A saída mostra os itens no diretório de plug-in no computador Server01. Os itens incluem as configurações de sessão, que são um tipo de plug-in, junto com outros tipos de plug-ins no computador WSMan.

### Exemplo 7-obter configurações de sessão detalhadas de um computador remoto

Este exemplo mostra como executar um `Get-PSSessionConfiguration` comando em um computador remoto. O comando requer que a delegação CredSSP esteja habilitada nas configurações do cliente no computador local e as configurações de serviço no computador remoto.

Para executar os comandos neste exemplo, você deve ser um membro do grupo Administradores nos computadores locais e remotos, e você deve iniciar o PowerShell com a opção **Executar como administrador** .

```powershell
Enable-WSManCredSSP -Delegate Server02
Connect-WSMan Server02
Set-Item WSMan:\Server02*\Service\Auth\CredSSP -Value $true
Invoke-Command -ScriptBlock {Get-PSSessionConfiguration} -ComputerName Server02 -Authentication CredSSP -Credential Domain01\Admin01
```

```Output
Name                      PSVersion  StartupScript        Permission                          PSComputerName
----                      ---------  -------------        ----------                          --------------
microsoft.powershell      5.1                             BUILTIN\Administrators AccessAll... server02.corp.fabrikam.com
microsoft.powershell32    5.1                             BUILTIN\Administrators AccessAll... server02.corp.fabrikam.com
MyX86Shell                5.1        c:\test\x86Shell.ps1 BUILTIN\Administrators AccessAll... server02.corp.fabrikam.com
```

O `Enable-WSManCredSSP` cmdlet habilita a delegação **CredSSP** em Server01, o computador local. O `Connect-WSMan` cmdlet se conecta ao computador Server02. Essa ação adiciona um nó para Server02 à unidade WSMan: no computador local, permitindo que você exiba e altere as configurações de WS-Management no computador Server02. O `Set-Item` cmdlet altera o valor do item **CredSSP** no nó de serviço do computador Server02 para **true** . Isso define as configurações de serviço no computador remoto. O `Invoke-Command` cmdlet executa o `Get-PSSessionConfiguration` comando no computador Server02. O comando utiliza os parâmetros **Credential** e **Authentication** com um valor **CredSSP** . A saída mostra as configurações de sessão no computador remoto Server02.

### Exemplo 8-obter o URI de recurso de uma configuração de sessão

Este exemplo é útil para definir o valor da `$PSSessionConfigurationName` variável de preferência, que usa um URI de recurso.

```powershell
(Get-PSSessionConfiguration -Name CustomShell).resourceURI
```

```Output
http://schemas.microsoft.com/powershell/microsoft.CustomShell
```

A `$PSSessionConfigurationName` variável especifica a configuração padrão que é usada quando você cria uma sessão. Essa variável é definida no computador local, mas ela especifica uma configuração no computador remoto. Para obter mais informações sobre a `$PSSessionConfiguration` variável, consulte [about_Preference_Variables](About/about_Preference_Variables.md).

## PARAMETERS

### -Force

Suprime o prompt para reiniciar o serviço WinRM, se o serviço não estiver sendo executado.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Obtém somente as configurações de sessão com o nome especificado ou o nome padrão. Insira um ou mais nomes de configuração de sessão. Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: All session configurations on the local computer
Accept pipeline input: False
Accept wildcard characters: True
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](./About/about_CommonParameters.md).

## ENTRADAS

### Nenhum

Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### Microsoft. PowerShell. Commands. PSSessionConfigurationCommands # PSSessionConfiguration

## OBSERVAÇÕES

- Para executar esse cmdlet, inicie o PowerShell com a opção **Executar como administrador** .

- Para exibir as configurações de sessão no computador, você deve ser um membro do grupo Administradores no computador.

- Para executar um `Get-PSSessionConfiguration` comando em um computador remoto, a autenticação de CredSSP (provedor de serviços de segurança de credencial) deve ser habilitada nas configurações do cliente no computador local (usando o `Enable-WSManCredSSP` cmdlet) e nas configurações de serviço no computador remoto. Além disso, você deve usar o valor **CredSSP** do parâmetro de **autenticação** ao estabelecer a sessão remota. Caso contrário, o acesso é negado.

- As propriedades de observação do objeto que `Get-PSSessionConfiguration` retorna aparecem no objeto somente quando eles têm um valor. Somente as configurações de sessão que foram criadas usando um arquivo de configuração de sessão têm todas as propriedades definidas.

- As propriedades de um objeto de configuração de sessão variam de acordo com as opções definidas para a configuração da sessão e os valores dessas opções. Além disso, as configurações de sessão que usam um arquivo de configuração de sessão têm propriedades adicionais.

- É possível utilizar comandos na unidade WSMan: para alterar as propriedades das configurações de sessão.
  No entanto, você não pode usar a unidade WSMan: no PowerShell 2,0 para alterar as propriedades de configuração de sessão introduzidas no PowerShell 3,0, como **OutputBufferingMode** . Os comandos do PowerShell 2,0 não geram um erro, mas eles são ineficazes. Para alterar as propriedades introduzidas no PowerShell 3,0, use a unidade WSMan: no PowerShell 3,0.

## LINKS RELACIONADOS

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Disable-PSSessionConfiguration](Enable-PSSessionConfiguration.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSessionConfigurationFile](New-PSSessionConfigurationFile.md)

[New-PSSessionOption](New-PSSessionOption.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Test-PSSessionConfigurationFile](Test-PSSessionConfigurationFile.md)

[Unregister-PSSessionConfiguration](Unregister-PSSessionConfiguration.md)

[Provedor WSMan](../microsoft.wsman.management/about/about_WSMan_Provider.md)

[about_Session_Configurations](About/about_Session_Configurations.md)

[about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)
