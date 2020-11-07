---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/register-pssessionconfiguration?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-PSSessionConfiguration
ms.openlocfilehash: 6417881880cb7f317e7a42d6749b8b7f2cb712fb
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345469"
---
# Register-PSSessionConfiguration

## SINOPSE
Cria e registra uma nova configuração de sessão.

## SYNTAX

### NameParameterSet (padrão)

```
Register-PSSessionConfiguration [-ProcessorArchitecture <String>] [-SessionType <PSSessionType>]
 [-Name] <String> [-ApplicationBase <String>] [-RunAsCredential <PSCredential>]
 [-ThreadOptions <PSThreadOptions>] [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess]
 [-StartupScript <String>] [-MaximumReceivedDataSizePerCommandMB <Double>]
 [-MaximumReceivedObjectSizeMB <Double>] [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI]
 [-Force] [-NoServiceRestart] [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>]
 [-TransportOption <PSTransportOption>] [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AssemblyNameParameterSet

```
Register-PSSessionConfiguration [-ProcessorArchitecture <String>] [-Name] <String> [-AssemblyName] <String>
 [-ApplicationBase <String>] [-ConfigurationTypeName] <String> [-RunAsCredential <PSCredential>]
 [-ThreadOptions <PSThreadOptions>] [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess]
 [-StartupScript <String>] [-MaximumReceivedDataSizePerCommandMB <Double>]
 [-MaximumReceivedObjectSizeMB <Double>] [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI]
 [-Force] [-NoServiceRestart] [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>]
 [-TransportOption <PSTransportOption>] [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SessionConfigurationFile

```
Register-PSSessionConfiguration [-ProcessorArchitecture <String>] [-Name] <String>
 [-RunAsCredential <PSCredential>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-TransportOption <PSTransportOption>] -Path <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Register-PSSessionConfiguration` cmdlet cria e registra uma nova configuração de sessão no computador local. Esse é um cmdlet avançado que você pode usar para criar sessões personalizadas para usuários remotos.

Cada sessão do PowerShell ( **PSSession** ) usa uma configuração de sessão, também conhecida como um ponto de extremidade.
Quando os usuários criam uma sessão que se conecta ao computador, eles podem selecionar uma configuração de sessão ou usar a configuração de sessão padrão que é registrada quando você habilita a comunicação remota do PowerShell.
Os usuários também podem definir a variável de preferência $PSSessionConfigurationName, que especifica uma configuração padrão para sessões remotas criadas na sessão atual.

A configuração da sessão define o ambiente para a sessão remota. A configuração pode determinar quais comandos e elementos de idioma estão disponíveis na sessão, e pode incluir configurações que protegem o computador, tal como as que limitam a quantidade de dados que a sessão pode receber remotamente em um único objeto ou o comando. O descritor de segurança da configuração de sessão determina quais usuários têm permissão para usar a configuração de sessão.

Você pode definir os elementos de configuração por meio de um assembly que implementa uma nova classe de configuração e usando um script que é executado na sessão. A partir do PowerShell 3,0, você também pode usar um arquivo de configuração de sessão para definir a configuração de sessão.

Para obter informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).
Para obter informações sobre arquivos de configuração de sessão, consulte [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).

## EXEMPLOS

### Exemplo 1: registrar uma configuração de sessão NewShell

Neste exemplo, registramos a configuração de sessão **NewShell** . Os parâmetros **AssemblyName** e **ApplicationBase** especificam o local do arquivo de **MyShell.dll** , que especifica os cmdlets e provedores na configuração da sessão. O parâmetro **ConfigurationTypeName** especifica a classe de configuração a ser usada no assembly.

```powershell
$sessionConfiguration = @{
    Name='NewShell'
    ApplicationBase='c:\MyShells\'
    AssemblyName='MyShell.dll'
    ConfigurationTypeName='MyClass'
}
Register-PSSessionConfiguration @sessionConfiguration
```

Para usar essa configuração, digite `New-PSSession -ConfigurationName newshell` .

### Exemplo 2: registrar uma configuração de sessão MaintenanceShell

Este exemplo registra a configuração de sessão **MaintenanceShell** no computador local. O parâmetro **StartupScript** especifica o `Maintenance.ps1` script.

```powershell
Register-PSSessionConfiguration -Name MaintenanceShell -StartupScript C:\ps-test\Maintenance.ps1
```

Quando um usuário usa um `New-PSSession` comando e seleciona a configuração **MaintenanceShell** , o `Maintenance.ps1` script é executado na nova sessão. O script pode configurar a sessão. Isso inclui a importação de módulos e a definição da política de execução para a sessão. Se o script gerar erros, incluindo erros de não encerramento, o `New-PSSession` comando falhará.

### Exemplo 3: registrar uma configuração de sessão

Este exemplo registra a configuração de sessão **AdminShell** .

A `$sessionParams` variável é uma Hashtable que contém todos os valores de parâmetro. Essa tabela de hash é passada para o cmdlet usando o PowerShell nivelamento. O `Register-PSSessionConfiguration` comando usa o parâmetro **SecurityDescritorSDDL** para especificar o SDDL no valor da `$sddl` variável e o parâmetro **MaximumReceivedObjectSizeMB** para aumentar o limite de tamanho do objeto. Ele também usa o parâmetro **StartupScript** para especificar um script que configura a sessão.

```powershell
$sddl = "O:NSG:BAD:P(A;;GA;;;BA)S:P(AU;FA;GA;;;WD)(AU;FA;SA;GWGX;;WD)"
$sessionParams = @{
    Name="AdminShell"
    SecurityDescriptorSDDL=$sddl
    MaximumReceivedObjectSizeMB=20
    StartupScript="C:\scripts\AdminShell.ps1"
}
Register-PSSessionConfiguration @sessionParams
```

### Exemplo 4: retornar um elemento de contêiner de configuração

Este exemplo mostra como registrar a configuração do **MaintenanceShell** .
`Register-PSSessionConfiguration` Retorna um objeto **WSManConfigContainerElement** armazenado na `$s` variável. `Format-List` exibe todas as propriedades do objeto retornado. A propriedade **PSPath** mostra que o objeto é armazenado em um diretório da unidade WSMan:. `Get-ChildItem` (alias `dir` ) exibe os itens no `WSMan:\LocalHost\PlugIn` caminho. Isso inclui a nova configuração do **MaintenanceShell** e as duas configurações padrão que vêm com o PowerShell.

```powershell
$s = Register-PSSessionConfiguration -Name MaintenanceShell -StartupScript C:\ps-test\Maintenance.ps1
$s | Format-List -Property *
dir WSMan:\LocalHost\Plugin
```

```Output
PSPath            : Microsoft.WSMan.Management\WSMan::localhost\Plugin\MaintenanceShell
PSParentPath      : Microsoft.WSMan.Management\WSMan::localhost\Plugin
PSChildName       : MaintenanceShell
PSDrive           : WSMan
PSProvider        : Microsoft.WSMan.Management\WSMan
PSIsContainer     : True
Keys              : {Name=MaintenanceShell}
Name              : MaintenanceShell
TypeNameOfElement : Container

Name                      Type                 Keys
----                      ----                 ----
MaintenanceShell          Container            {Name=MaintenanceShell}
microsoft.powershell      Container            {Name=microsoft.powershell}
microsoft.powershell32    Container            {Name=microsoft.powershell32}
```

### Exemplo 5: registrar uma configuração de sessão com um script de inicialização

Neste exemplo, criamos e registramos a configuração de sessão **WithProfile** . O parâmetro **StartupScript** direciona o PowerShell para executar o script especificado para qualquer sessão que usa a configuração de sessão.

```powershell
Register-PSSessionConfiguration -Name WithProfile -StartupScript Add-Profile.ps1
```

O script contém um único comando que usa o fornecimento de ponto para executar o perfil do usuário **CurrentUserAllHosts** no escopo da sessão atual.

Para obter mais informações sobre perfis, consulte [about_Profiles](./About/about_Profiles.md). Para obter mais informações sobre como usar fontes de pontos, consulte [about_Scopes](./About/about_Scopes.md).

## PARAMETERS

### -AccessMode

Habilita e desabilita a configuração da sessão e determina se ela pode ser usada para sessões locais ou remotas no computador. Os valores aceitáveis para esse parâmetro são:

- Desabilitado. Desabilita a configuração da sessão. Ele não pode ser usado para acesso remoto ou local no computador.
- Local. Permite que os usuários do computador local usem a configuração de sessão para criar uma sessão de loopback local no mesmo computador, mas nega o acesso a usuários remotos.
- Controle. Permite que os usuários locais e remotos usem a configuração da sessão para criar sessões e executar comandos nesse computador.

O valor padrão é remoto.

Outros cmdlets podem substituir o valor desse parâmetro posteriormente. Por exemplo, o `Enable-PSRemoting` cmdlet permite o acesso remoto a todas as configurações de sessão, o `Enable-PSSessionConfiguration` cmdlet habilita as configurações de sessão e o `Disable-PSRemoting` cmdlet impede o acesso remoto a todas as configurações de sessão.

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

Especifica o caminho do arquivo de assembly ( \* . dll) que é especificado no valor do parâmetro **AssemblyName** . Use esse parâmetro quando o valor do parâmetro **AssemblyName** não incluir um caminho. O padrão é o diretório atual.

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

Especifica o nome de um arquivo de assembly ( \* . dll) no qual o tipo de configuração é definido. Você pode especificar o caminho do. dll nesse parâmetro ou no valor do parâmetro **ApplicationBase** .

Esse parâmetro é necessário quando você especifica o parâmetro **ConfigurationTypeName** .

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

Especifica o nome totalmente qualificado do tipo do Microsoft .NET Framework usado para esta configuração. O tipo especificado deve implementar a casse **System.Management.Automation.Remoting.PSSessionConfiguration**.

Para especificar o arquivo de assembly ( \* . dll) que implementa o tipo de configuração, especifique os parâmetros **AssemblyName** e **ApplicationBase** .

A criação de um tipo permite controlar mais aspectos da configuração de sessão, como expor ou ocultar determinados parâmetros de cmdlets ou definir o tamanho dos dados e limites de tamanho de objeto que os usuários não podem substituir.

Se você omitir esse parâmetro, a classe **DefaultRemotePowerShellConfiguration** é usada para a configuração da sessão.

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

Para evitar uma reinicialização e suprimir o prompt de reinicialização, especifique o parâmetro **NoServiceRestart** .

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

Especifica um limite para a quantidade de dados que podem ser enviados a este computador em qualquer comando remoto único. Insira o tamanho dos dados em megabytes (MB). O valor padrão é 50 MB.

Se um limite de tamanho de dados é definido no tipo de configuração especificado no parâmetro **ConfigurationTypeName** , o limite no tipo de configuração é usado e o valor desse parâmetro é ignorado.

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

Especifica um limite para a quantidade de dados que podem ser enviados para este computador em qualquer objeto único.
Insira o tamanho dos dados em megabytes. O padrão é 10 MB.

Se um limite de tamanho do objeto é definido no tipo de configuração especificado no parâmetro **ConfigurationTypeName** , o limite no tipo de configuração é usado e o valor desse parâmetro é ignorado.

```yaml
Type: System.Nullable`1[System.Double]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 10
Accept pipeline input: False
Accept wildcard characters: False
```

### -ModulesToImport

Especifica os módulos que são automaticamente importados para sessões que usam a configuração de sessão.

Por padrão, somente **o Microsoft. PowerShell. Core** é importado para sessões. A menos que os cmdlets sejam excluídos, você pode usar o `Import-Module` para adicionar módulos à sessão.

Os módulos especificados nesse valor de parâmetro são importados em adições aos módulos que são especificados pelo parâmetro **SessionType** e aqueles listados na chave **ModulesToImport** no arquivo de configuração de sessão ( `New-PSSessionConfigurationFile` ). No entanto, as configurações no arquivo de configuração de sessão podem ocultar os comandos exportados por módulos ou impedir os usuários de utilizá-los.

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

Especifica um nome para a configuração de sessão. Este parâmetro é necessário.

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

Por padrão, quando você executa um `Register-PSSessionConfiguration` comando, é solicitado que você reinicie o serviço **WinRM** para tornar a nova configuração de sessão eficaz. Até que o serviço **WinRM** seja reiniciado, a nova configuração de sessão não será eficaz.

Para reiniciar o serviço **WinRM** sem avisar, especifique o parâmetro **Force** . Para reiniciar o serviço **WinRM** manualmente, use o `Restart-Service` cmdlet.

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

Especifica o caminho e o nome do arquivo de uma configuração de sessão (. PSSC), como um criado por `New-PSSessionConfigurationFile` . Se você omitir o caminho, o padrão será o diretório atual.

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

### -ProcessorArchitecture

Determina se uma versão de 32 bits ou 64 bits do processo do PowerShell é iniciada em sessões que usam essa configuração de sessão. Os valores aceitáveis para esse parâmetro são: x86 (32 bits) e AMD64 (64 bits). O valor padrão é determinado pela arquitetura de processador do computador que hospeda a configuração da sessão.

Você pode usar esse parâmetro para criar uma sessão de 32 bits em um computador de 64 bits. Tentativas de criar um processo de 64 bits em um computador de 32 bits falharão.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PA
Accepted values: x86, amd64

Required: False
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

Especifica uma cadeia de caracteres Security Descriptor Definition Language (SDDL) para a configuração.

Essa cadeia de caracteres determina as permissões que são necessárias para usar a nova configuração de sessão. Para usar uma configuração de sessão em uma sessão, os usuários devem ter, pelo menos, a permissão execute (Invoke) para a configuração.

Se o descritor de segurança for complexo, considere usar o parâmetro **ShowSecurityDescriptorUI** em vez desse parâmetro. Não é possível usar ambos os parâmetros no mesmo comando.

Se você omitir esse parâmetro, o SDDL raiz para o serviço **WinRM** será usado para essa configuração.
Para exibir ou alterar a raiz SDDL, use o provedor de WSMan. Por exemplo, `Get-Item wsman:\localhost\service\rootSDDL`. Para obter mais informações sobre o provedor WSMan, digite `Get-Help wsman` .

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

### -SessionType

Especifica o tipo de sessão que é criada usando a configuração da sessão. Os valores aceitáveis para esse parâmetro são:

- Vazio. Nenhum módulo é adicionado à sessão por padrão. Use os parâmetros desse cmdlet para adicionar módulos, funções, scripts e outros recursos à sessão.
- Padrão. Adiciona o Microsoft. PowerShell. Core à sessão. Esse módulo inclui o `Import-Module` cmdlet que os usuários podem usar para importar outros módulos, a menos que você proíba explicitamente o cmdlet.
- RestrictedRemoteServer. Inclui apenas os seguintes cmdlets:,,,,, `Exit-PSSession` `Get-Command` `Get-FormatData` `Get-Help` `Measure-Object` `Out-Default` e `Select-Object` . Use um script ou assembly, ou então as chaves no arquivo de configuração de sessão, para adicionar módulos, funções, scripts e outros recursos à sessão.

O valor padrão é Default.

O valor desse parâmetro tem precedência sobre o valor da chave **SessionType** no arquivo de configuração de sessão.

Esse parâmetro foi introduzido no PowerShell 3,0.

```yaml
Type: System.Management.Automation.Runspaces.PSSessionType
Parameter Sets: NameParameterSet
Aliases:
Accepted values: DefaultRemoteShell, Workflow

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

Indica que esse cmdlet exibe uma folha de propriedades que ajuda a criar o SDDL para a configuração de sessão. A folha de propriedades aparece depois que você insere o `Register-PSSessionConfiguration` comando e, em seguida, reinicia o serviço **WinRM** .

Ao definir as permissões para a configuração, lembre-se de que os usuários devem ter pelo menos a permissão execute (Invoke) para usar a configuração de sessão em uma sessão.

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

Especifica o caminho totalmente qualificado de um script do PowerShell. O script especificado é executado na nova sessão que usar a configuração de sessão.

Você pode usar o script para configurar também a sessão. Se o script gerar um erro, mesmo um erro de não encerramento, a sessão não será criada e o `New-PSSession` comando falhará.

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

Especifica como os threads são criados e usados quando um comando é executado na sessão. Os valores aceitáveis para esse parâmetro são:

- Padrão
- ReuseThread
- UseCurrentThread
- UseNewThread

O valor padrão é **UseCurrentThread**.

Para obter mais informações, consulte [Enumeração PSThreadOptions](/dotnet/api/system.management.automation.runspaces.psthreadoptions?view=powershellsdk-1.1.0).

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

Especifica a opção de transporte.

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

Mostra o que aconteceria se o cmdlet fosse executado. O cmdlet não é executado.

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### Microsoft. WSMan. Management. WSManConfigContainerElement

## OBSERVAÇÕES

Esse cmdlet só está disponível em plataformas Windows.

Para executar este cmdlet, você deve iniciar o PowerShell usando a opção **Executar como administrador** .

Esse cmdlet gera XML que representa uma configuração de plug-in de serviços Web para gerenciamento (WS-Management) e envia o XML para WS-Management, que registra o plug-in no computador local ( `New-Item wsman:\localhost\plugin` ).

As propriedades de um objeto de configuração de sessão variam de acordo com as opções definidas para a configuração da sessão e os valores dessas opções. Além disso, as configurações de sessão que usam um arquivo de configuração de sessão têm propriedades adicionais.

## LINKS RELACIONADOS

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Disable-PSSessionConfiguration](Enable-PSSessionConfiguration.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSessionConfigurationFile](New-PSSessionConfigurationFile.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Test-PSSessionConfigurationFile](Test-PSSessionConfigurationFile.md)

[Unregister-PSSessionConfiguration](Unregister-PSSessionConfiguration.md)

[Provedor WSMan](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[about_Session_Configurations](About/about_Session_Configurations.md)

[about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)
