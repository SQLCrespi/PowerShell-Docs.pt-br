---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-pssessionconfiguration?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSSessionConfiguration
ms.openlocfilehash: 72ee8c7eebf7d74920fd0d39e3a508841e57b7c5
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347492"
---
# Set-PSSessionConfiguration

## SINOPSE
Altera as propriedades de uma configuração de sessão registrada.

## SYNTAX

### NameParameterSet (padrão)

```
Set-PSSessionConfiguration [-Name] <String> [-ApplicationBase <String>] [-RunAsCredential <PSCredential>]
 [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>] [-TransportOption <PSTransportOption>]
 [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AssemblyNameParameterSet

```
Set-PSSessionConfiguration [-Name] <String> [-AssemblyName] <String> [-ApplicationBase <String>]
 [-ConfigurationTypeName] <String> [-RunAsCredential <PSCredential>] [-ThreadApartmentState <ApartmentState>]
 [-ThreadOptions <PSThreadOptions>] [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess]
 [-StartupScript <String>] [-MaximumReceivedDataSizePerCommandMB <Double>]
 [-MaximumReceivedObjectSizeMB <Double>] [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI]
 [-Force] [-NoServiceRestart] [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>]
 [-TransportOption <PSTransportOption>] [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SessionConfigurationFile

```
Set-PSSessionConfiguration [-Name] <String> [-RunAsCredential <PSCredential>]
 [-ThreadApartmentState <ApartmentState>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-TransportOption <PSTransportOption>] -Path <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Set-PSSessionConfiguration` cmdlet altera as propriedades das configurações de sessão no computador local.

Use o parâmetro **Name** para identificar a configuração da sessão que você deseja alterar. Use os outros parâmetros para especificar novos valores para as propriedades da configuração de sessão. Para excluir um valor de propriedade da configuração e usar o valor padrão, insira uma cadeia de caracteres vazia ("") ou um valor de `$Null` para o parâmetro correspondente.

A partir do PowerShell 3,0, você pode usar um arquivo de configuração de sessão para definir uma configuração de sessão. Esse recurso fornece um método simples e detectável para definir ou alterar as propriedades de sessões que usam a configuração de sessão. Para especificar um arquivo de configuração de sessão, use o parâmetro **path** de `Set-PSSessionConfiguration` . Para obter informações sobre arquivos de configuração de sessão, consulte [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).
Para obter informações sobre como criar e modificar um arquivo de configuração de sessão, consulte o `New-PSSessionConfigurationFile` cmdlet.

As configurações de sessão definem o ambiente de sessões remotas ( **PSSessions** ) que se conectam ao computador local. Cada **PSSession** usa uma configuração de sessão. A configuração de sessão determina os recursos da **PSSession** , como os módulos disponíveis na sessão, os cmdlets que têm permissão para serem executados, o modo de linguagem, as cotas e os tempos limite. O descritor de segurança da configuração de sessão determina quem pode usar a configuração de sessão para se conectar ao computador local. Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).

Para ver as propriedades de uma configuração de sessão, use o `Get-PSSessionConfiguration` cmdlet ou o provedor WSMan. Para obter mais informações sobre o provedor WSMan, digite `Get-Help WSMan` .

## EXEMPLOS

### Exemplo 1: criar e alterar uma configuração de sessão

Este exemplo mostra como adicionar e remover um script de inicialização de uma configuração.

O primeiro comando cria a configuração **AdminShell** . O segundo comando adiciona o `AdminConfig.ps1` script à configuração. A alteração é eficaz quando você reinicia o **WinRM**.
O terceiro comando Remove o `AdminConfig.ps1` script da configuração.

```powershell
Register-PSSessionConfiguration -Name "AdminShell" -AssemblyName "C:\Shells\AdminShell.dll" -ConfigurationTypeName "AdminClass"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript "AdminConfig.ps1"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript $Null
```

### Exemplo 2: exibir resultados

Este exemplo aumenta o valor da propriedade **MaximumReceivedObjectSizeMB** para 20. Esse comando também solicita que você reinicie o serviço **WinRM** . A alteração não será eficaz até que o serviço **WinRM** seja reiniciado.

```powershell
Set-PSSessionConfiguration -Name "IncObj" -MaximumReceivedObjectSizeMB 20
```

```Output
WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin\IncObj\InitializationParameters

ParamName                       ParamValue
---------                       ----------
psmaximumreceivedobjectsizemb   20

"Restart WinRM service"
WinRM service need to be restarted to make the changes effective. Do you want to run the command "restart-service winrm"?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y
```

### Exemplo 3: exibir resultados de diferentes maneiras

Neste exemplo, `Set-PSSessionConfiguration` altera o script de inicialização na configuração de sessão **MaintenanceShell** para `Maintenance.ps1` . A saída mostra a alteração e solicita que você reinicie o serviço **WinRM** . A resposta é "y" (sim).

`Get-PSSessionConfiguration` Obtém a configuração da sessão **MaintenanceShell** . O operador de pipeline (|) envia os resultados do comando para `Format-List` , que exibe todas as propriedades do objeto de configuração em uma lista. Em seguida, usando o provedor WSMan, exibimos os parâmetros de inicialização para a configuração **MaintenanceShell** . `Get-ChildItem` (alias `dir` ) Obtém os itens filho no nó **InitializationParameters** para o plug-in **MaintenanceShell** . Para obter mais informações sobre o provedor WSMan, digite `Get-Help wsman` .

```powershell
Set-PSSessionConfiguration -Name "MaintenanceShell" -StartupScript "C:\ps-test\Maintenance.ps1"
```

```Output
WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin\MaintenanceShell\InitializationParameters

ParamName            ParamValue
---------            ----------
startupscript        c:\ps-test\Mainte...

"Restart WinRM service"
WinRM service need to be restarted to make the changes effective. Do you want to run
the command "restart-service winrm"?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y

```

```powershell
Get-PSSessionConfiguration MaintenanceShell | Format-List -Property *
```

```Output
xmlns            : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
Name             : MaintenanceShell
Filename         : %windir%\system32\pwrshplugin.dll
SDKVersion       : 1
XmlRenderingType : text
lang             : en-US
PSVersion        : 2.0
startupscript    : c:\ps-test\Maintenance.ps1
ResourceUri      : http://schemas.microsoft.com/powershell/MaintenanceShell
SupportsOptions  : true
ExactMatch       : true
Capability       : {Shell}
Permission       :
```

```powershell
dir WSMan:\localhost\Plugin\MaintenanceShell\InitializationParameters
```

```Output
ParamName     ParamValue
---------     ----------
PSVersion     2.0
startupscript c:\ps-test\Maintenance.ps1
```

## PARAMETERS

### -AccessMode

Habilita e desabilita a configuração da sessão e determina se ela pode ser usada para sessões locais ou remotas no computador. Os valores aceitáveis para esse parâmetro são:

- Desabilitado. Desabilita a configuração da sessão. Ele não pode ser usado para acesso remoto ou local no computador. Esse valor define a propriedade **Enabled** da configuração de sessão ( `WSMan:\<ComputerName>\PlugIn\<SessionConfigurationName>\Enabled` ) como **false**.
- Local. Adiciona uma entrada **Network_Deny_All** ao descritor de segurança da configuração de sessão.
  Os usuários do computador local podem usar a configuração de sessão para criar uma sessão de loopback local no mesmo computador, mas os usuários remotos têm o acesso negado.
- Controle. Remove as entradas **Deny_All** e **Network_Deny_All** dos descritores de segurança da configuração de sessão. Usuários de computadores locais e remotos podem usar a configuração da sessão para criar sessões e executar comandos nesse computador.

O valor padrão é **remoto**.

Outros cmdlets podem substituir o valor desse parâmetro posteriormente. Por exemplo, o `Enable-PSRemoting` cmdlet habilita todas as configurações de sessão no computador e permite o acesso remoto a elas, e o `Disable-PSRemoting` cmdlet permite apenas acesso local a todas as configurações de sessão no computador.

Esse parâmetro foi introduzido no PowerShell 3,0.

```yaml
Type: System.Management.Automation.Runspaces.PSSessionConfigurationAccessMode
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Local, Remote

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationBase

Especifica o caminho do arquivo de assembly ( \* . dll) que é especificado no valor do parâmetro **AssemblyName** .

```yaml
Type: System.String
Parameter Sets: NameParameterSet, AssemblyNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AssemblyName

Especifica o nome do assembly. Esse cmdlet cria uma configuração de sessão com base em uma classe que é definida em um assembly.

Insira o nome de arquivo ou caminho completo de um arquivos assembly. dll que define uma configuração de sessão. Se você inserir apenas o nome do arquivo, poderá inserir o caminho no valor do parâmetro **ApplicationBase** .

```yaml
Type: System.String
Parameter Sets: AssemblyNameParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigurationTypeName

Especifica o tipo de configuração de sessão que é definido no assembly no parâmetro **AssemblyName**. O tipo especificado deve implementar a casse **System.Management.Automation.Remoting.PSSessionConfiguration**.

Esse parâmetro é necessário quando você especifica um nome de assembly.

```yaml
Type: System.String
Parameter Sets: AssemblyNameParameterSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Suprime todos os prompts do usuário e reinicia o serviço **WinRM** sem avisar. Reiniciar o serviço faz a com que a alteração da configuração entre em vigor.

Para evitar uma reinicialização e suprimir o prompt de reinicialização, use o parâmetro **NoServiceRestart**.

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

### -MaximumReceivedDataSizePerCommandMB

Especifica o limite da quantidade de dados que podem ser enviados para este computador em qualquer comando remoto único. Insira o tamanho dos dados em megabytes (MB). O valor padrão é 50 MB.

Se um limite de tamanho de dados for definido no tipo de configuração especificado no parâmetro **ConfigurationTypeName** , o limite no tipo de configuração será usado. O valor desse parâmetro é ignorado.

```yaml
Type: System.Nullable`1[System.Double]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumReceivedObjectSizeMB

Especifica os limites na quantidade de dados que podem ser enviados para este computador em qualquer objeto único.
Insira o tamanho dos dados em megabytes. O padrão é 10 MB.

Se um limite de tamanho de objeto for definido no tipo de configuração especificado no parâmetro **ConfigurationTypeName** , o limite no tipo de configuração será usado. O valor desse parâmetro é ignorado.

```yaml
Type: System.Nullable`1[System.Double]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ModulesToImport

Especifica os módulos e snap-ins que são importados automaticamente nas sessões que usam a configuração de sessão. Digite os nomes de módulo e o snap-in.

Por padrão, somente o snap-in **Microsoft. PowerShell. Core** é importado para sessões, mas a menos que os cmdlets sejam excluídos, você pode usar os `Import-Module` cmdlets e Add-PSSnapin para adicionar módulos e snap-ins à sessão.

Os módulos especificados nesse valor de parâmetro são importados em adições aos módulos especificados no arquivo de configuração de sessão ( `New-PSSessionConfigurationFile` ). No entanto, as configurações no arquivo de configuração de sessão podem ocultar os comandos exportados por módulos ou impedir os usuários de utilizá-los.

Os módulos especificados nesse valor de parâmetro substituem a lista de módulos especificados usando o parâmetro **ModulesToImport** do `Register-PSSessionConfiguration` cmdlet.

Esse parâmetro foi introduzido no PowerShell 3,0.

```yaml
Type: System.Object[]
Parameter Sets: NameParameterSet, AssemblyNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Especifica o nome da configuração de sessão que você deseja alterar.

Você não pode usar esse parâmetro para alterar o nome da configuração de sessão.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NoServiceRestart

Não reinicia o serviço **WinRM** e suprime o prompt para reiniciar o serviço.

Por padrão, quando você executa `Set-PSSessionConfiguration` o, é solicitado que você reinicie o serviço **WinRM** para tornar a nova configuração de sessão eficaz. Até que o serviço **WinRM** seja reiniciado, a nova configuração de sessão não será eficaz.

Para reiniciar o serviço **WinRM** sem avisar, use o parâmetro **Force** . Para reiniciar o serviço **WinRM** manualmente, use o `Restart-Service` cmdlet.

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

### -Path

Especifica o caminho de um arquivo de configuração de sessão (. PSSC), como um criado pelo `New-PSSessionConfigurationFile` cmdlet. Se você omitir o caminho, o padrão será o diretório atual.

Para obter informações sobre como modificar um arquivo de configuração de sessão, consulte o tópico da ajuda para o `New-PSSessionConfigurationFile` cmdlet.

Esse parâmetro foi introduzido no PowerShell 3,0.

```yaml
Type: System.String
Parameter Sets: SessionConfigurationFile
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PSVersion

Especifica a versão do PowerShell em sessões que usam essa configuração de sessão.

O valor deste parâmetro tem precedência sobre o valor da chave **PowerShellVersion** no arquivo de configuração de sessão.

Esse parâmetro foi introduzido no PowerShell 3,0.

```yaml
Type: System.Version
Parameter Sets: NameParameterSet, AssemblyNameParameterSet
Aliases: PowerShellVersion

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsCredential

Especifica as credenciais para os comandos na sessão. Por padrão, os comandos são executados com as permissões do usuário atual.

Esse parâmetro foi introduzido no PowerShell 3,0.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecurityDescriptorSddl

Especifica uma cadeia de caracteres SDDL (Security Descriptor Definition Language) diferentes para a configuração.

Essa cadeia de caracteres determina as permissões que são necessárias para usar a nova configuração de sessão. Para usar uma configuração de sessão em uma sessão, os usuários devem ter, pelo menos, a permissão execute (Invoke) para a configuração.

Para usar o descritor de segurança padrão para a configuração, insira uma cadeia de caracteres vazia ("") ou um valor de `$Null` . O padrão é o SDDL raiz na unidade WSMan:.

Se o descritor de segurança for complexo, considere usar o parâmetro **ShowSecurityDescriptorUI dos** em vez deste. Não é possível usar ambos os parâmetros no mesmo comando.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SessionTypeOption

Especifica opções específicas de tipo para a configuração de sessão. Insira um objeto de opções de tipo de sessão, como o objeto **PSWorkflowExecutionOption** que o `New-PSWorkflowExecutionOption` cmdlet retorna.

As opções de sessões que usam a configuração de sessão são determinadas pelos valores das opções de sessão e pelas opções de configuração de sessão. A menos que especificado, as opções definidas na sessão, como usando o `New-PSSessionOption` cmdlet, têm precedência sobre as opções definidas na configuração da sessão. No entanto, valores de opção de sessão não podem ultrapassar os valores máximos definidos na configuração da sessão.

Esse parâmetro foi introduzido no PowerShell 3,0.

```yaml
Type: System.Management.Automation.PSSessionTypeOption
Parameter Sets: NameParameterSet, AssemblyNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShowSecurityDescriptorUI dos

Indica que esse cmdlet é uma folha de propriedades que ajuda a criar uma nova SDDL para a configuração de sessão. A folha de propriedades aparece depois que você executa o `Set-PSSessionConfiguration` comando e, em seguida, reinicia o serviço **WinRM** .

Quando você define permissões para a configuração, lembre-se de que os usuários devem ter pelo menos a permissão execute (Invoke) para usar a configuração de sessão em uma sessão.

Você não pode usar o parâmetro **SecurityDescriptorSDDL** e este parâmetro no mesmo comando.

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

### -StartupScript

Especifica o script de inicialização para a configuração. Insira o caminho totalmente qualificado de um script do PowerShell. O script especificado é executado na nova sessão que usar a configuração de sessão.

Para excluir um script de inicialização de uma configuração de sessão, insira uma cadeia de caracteres vazia ("") ou um valor de `$Null` .

Você pode usar um script de inicialização para configurar ainda mais a sessão do usuário. Se o script gerar um erro, mesmo um erro de não encerramento, a sessão não será criada e o `New-PSSession` comando falhará.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThreadOptions

Especifica a configuração de opções de thread na configuração. Essa configuração define como threads são criados e usados quando um comando é executado na sessão. Os valores aceitáveis para esse parâmetro são:

- Padrão
- ReuseThread
- UseCurrentThread
- UseNewThread

O valor padrão é **UseCurrentThread**.

Para obter mais informações, consulte [Enumeração PSThreadOptions](/dotnet/api/system.management.automation.runspaces.psthreadoptions).

```yaml
Type: System.Management.Automation.Runspaces.PSThreadOptions
Parameter Sets: (All)
Aliases:
Accepted values: Default, UseNewThread, ReuseThread, UseCurrentThread

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TransportOption

Especifica as opções de transporte para a configuração de sessão. Insira um objeto de opções de transporte, como o objeto **WSManConfigurationOption** que o `New-PSTransportOption` cmdlet retorna.

As opções de sessões que usam a configuração de sessão são determinadas pelos valores das opções de sessão e pelas opções de configuração de sessão. A menos que especificado, as opções definidas na sessão, como usando o `New-PSSessionOption` cmdlet, têm precedência sobre as opções definidas na configuração da sessão. No entanto, valores de opção de sessão não podem ultrapassar os valores máximos definidos na configuração da sessão.

Esse parâmetro foi introduzido no PowerShell 3,0.

```yaml
Type: System.Management.Automation.PSTransportOption
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseSharedProcess

Use apenas um processo para hospedar todas as sessões que são iniciadas pelo mesmo usuário e usam a mesma configuração de sessão. Por padrão, cada sessão é hospedada em seu próprio processo.

Esse parâmetro foi introduzido no PowerShell 3,0.

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

### -Confirm

Solicita sua confirmação antes de executar o cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Mostra o que aconteceria se o cmdlet fosse executado.
O cmdlet não é executado.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThreadApartmentState

Especifica o estado de apartment do módulo de Threading a ser usado. Os valores aceitáveis são:

- Desconhecido
- MTA
- STA

```yaml
Type: System.Threading.ApartmentState
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### Microsoft. WSMan. Management. WSManConfigLeafElement

## OBSERVAÇÕES

Esse cmdlet só está disponível em plataformas Windows.

Para executar esse cmdlet, inicie o PowerShell usando a opção Executar como administrador.

O `Set-PSSessionConfiguration` cmdlet não altera o nome da configuração e o provedor **WSMan** não oferece suporte ao `Rename-Item` cmdlet. Para alterar o nome de uma configuração de sessão, use o `Unregister-PSSessionConfiguration` cmdlet para excluir a configuração e, em seguida, use o `Register-PSSessionConfiguration` cmdlet para criar e registrar uma nova configuração de sessão.

Você pode usar o `Set-PSSessionConfiguration` cmdlet para alterar as configurações de sessão padrão Microsoft. PowerShell e Microsoft. powershell32. Elas não são protegidas. Para reverter para a versão original de uma configuração de sessão padrão, use o `Unregister-PSSessionConfiguration` cmdlet para excluir a configuração de sessão padrão e, em seguida, use o `Enable-PSRemoting` cmdlet para restaurá-la.

As propriedades de um objeto de configuração de sessão variam de acordo com as opções definidas para a configuração da sessão e os valores dessas opções. Além disso, as configurações de sessão que usam um arquivo de configuração de sessão têm propriedades adicionais.

É possível utilizar comandos na unidade WSMan: para alterar as propriedades das configurações de sessão.
No entanto, você não pode usar a unidade WSMan: no PowerShell 2,0 para alterar as propriedades de configuração de sessão introduzidas no PowerShell 3,0, como **OutputBufferingMode**. Os comandos do Windows PowerShell 2.0 não geram um erro, mas são ineficazes. Para alterar as propriedades introduzidas no PowerShell 3,0, use a unidade WSMan: no PowerShell 3,0.

## LINKS RELACIONADOS

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Disable-PSSessionConfiguration](Enable-PSSessionConfiguration.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSessionConfigurationFile](New-PSSessionConfigurationFile.md)

[New-PSSessionOption](New-PSSessionOption.md)

[New-PSTransportOption](New-PSTransportOption.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Test-PSSessionConfigurationFile](Test-PSSessionConfigurationFile.md)

[Unregister-PSSessionConfiguration](Unregister-PSSessionConfiguration.md)

[Provedor WSMan](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[about_Session_Configurations](About/about_Session_Configurations.md)

[about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)
