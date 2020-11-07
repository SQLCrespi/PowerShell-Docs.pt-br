---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/24/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pssessionconfigurationfile?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSSessionConfigurationFile
ms.openlocfilehash: e393916f00e3670cd1ed3b5772bf165c43cc3a2f
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94343939"
---
# New-PSSessionConfigurationFile

## SINOPSE
Cria um arquivo que define uma configuração de sessão.

## SYNTAX

```
New-PSSessionConfigurationFile [-Path] <String> [-SchemaVersion <Version>] [-Guid <Guid>]
 [-Author <String>] [-Description <String>] [-CompanyName <String>] [-Copyright <String>]
 [-SessionType <SessionType>] [-TranscriptDirectory <String>] [-RunAsVirtualAccount]
 [-RunAsVirtualAccountGroups <String[]>] [-MountUserDrive] [-UserDriveMaximumSize <Int64>]
 [-GroupManagedServiceAccount <String>] [-ScriptsToProcess <String[]>]
 [-RoleDefinitions <IDictionary>] [-RequiredGroups <IDictionary>] [-LanguageMode <PSLanguageMode>]
 [-ExecutionPolicy <ExecutionPolicy>] [-PowerShellVersion <Version>] [-ModulesToImport <Object[]>]
 [-VisibleAliases <String[]>] [-VisibleCmdlets <Object[]>] [-VisibleFunctions <Object[]>]
 [-VisibleExternalCommands <String[]>] [-VisibleProviders <String[]>]
 [-AliasDefinitions <IDictionary[]>] [-FunctionDefinitions <IDictionary[]>]
 [-VariableDefinitions <Object>] [-EnvironmentVariables <IDictionary>] [-TypesToProcess <String[]>]
 [-FormatsToProcess <String[]>] [-AssembliesToLoad <String[]>] [-Full] [<CommonParameters>]
```

## DESCRIPTION

O `New-PSSessionConfigurationFile` cmdlet cria um arquivo de configurações que definem uma configuração de sessão e o ambiente de sessões que são criadas usando a configuração de sessão.
Para usar o arquivo em uma configuração de sessão, use o parâmetro **path** dos `Register-PSSessionConfiguration` `Set-PSSessionConfiguration` cmdlets ou.

O arquivo de configuração de sessão que o `New-PSSessionConfigurationFile` cria é um arquivo de texto legível que contém uma tabela de hash de valores e propriedades de configuração de sessão. O arquivo tem uma `.pssc` extensão de nome de arquivo.

Todos os parâmetros de `New-PSSessionConfigurationFile` são opcionais, exceto o parâmetro **Path** .
Se um parâmetro for omitido, a chave correspondente no arquivo de configuração de sessão é comentada, exceto onde observado na descrição do parâmetro.

Uma configuração de sessão, também conhecida como um ponto de extremidade, é uma coleção de configurações no computador local que definem o ambiente para sessões do PowerShell ( **PSSessions** ) que se conectam ao computador. Todas as **PSSessions** usam uma configuração de sessão. Para especificar uma configuração de sessão específica, use o parâmetro **ConfigurationName** de cmdlets que criam uma sessão, como o `New-PSSession` cmdlet.

Um session configuration file torna mais fácil definir uma configuração de sessão sem scripts complexos ou assemblies de código. As configurações no arquivo são usadas com o script de inicialização opcional e quaisquer assemblies na configuração de sessão.

Para obter mais informações sobre configurações de sessão e arquivos de configuração de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md) e [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).

Esse cmdlet foi introduzido no PowerShell 3,0.

## EXEMPLOS

### Exemplo 1: Criando e usando uma sessão nolanguage

Este exemplo mostra como criar e os efeitos do uso de uma sessão sem idioma.

As etapas são as seguintes:

1. Crie um novo arquivo de configuração.
1. Registre a configuração.
1. Crie uma nova sessão que usa a configuração.
1. Execute comandos nessa nova sessão.

Para executar os comandos neste exemplo, inicie o PowerShell usando a opção Executar como administrador. Essa opção é necessária para executar o `Register-PSSessionConfiguration` cmdlet.

```powershell
New-PSSessionConfigurationFile -Path .\NoLanguage.pssc -LanguageMode NoLanguage
Register-PSSessionConfiguration -Path .\NoLanguage.pssc -Name NoLanguage -Force
$NoLanguageSession = New-PSSession -ComputerName Srv01 -ConfigurationName NoLanguage
Invoke-Command -Session $NoLanguageSession -ScriptBlock {
  if ((Get-Date) -lt '1January2099') {'Before'} else {'After'}
}
```

```Output
The syntax is not supported by this runspace. This might be because it is in no-language mode.
    + CategoryInfo          : ParserError: (if ((Get-Date) ...') {'Before'}  :String) [], ParseException
    + FullyQualifiedErrorId : ScriptsNotAllowed
    + PSComputerName        : localhost
```

Neste exemplo, a `Invoke-Command` falha porque **languagemode** está definido como **nolanguage**.

### Exemplo 2: Criando e usando uma sessão RestrictedLanguage

Este exemplo mostra como criar e os efeitos do uso de uma sessão sem idioma.

As etapas são as seguintes:

1. Crie um novo arquivo de configuração.
1. Registre a configuração.
1. Crie uma nova sessão que usa a configuração.
1. Execute comandos nessa nova sessão.

Para executar os comandos neste exemplo, inicie o PowerShell usando a opção Executar como administrador. Essa opção é necessária para executar o `Register-PSSessionConfiguration` cmdlet.

```powershell
New-PSSessionConfigurationFile -Path .\NoLanguage.pssc -LanguageMode RestrictedLanguage
Register-PSSessionConfiguration -Path .\NoLanguage.pssc -Name RestrictedLanguage -Force
$RestrictedSession = New-PSSession -ComputerName Srv01 -ConfigurationName RestrictedLanguage
Invoke-Command -Session $RestrictedSession -ScriptBlock {
  if ((Get-Date) -lt '1January2099') {'Before'} else {'After'}
}
```

```Output
Before
```

Neste exemplo, o é com `Invoke-Command` sucesso porque o **languagemode** está definido como **RestrictedLanguage**.

### Exemplo 3: alterando um arquivo de configuração de sessão

Este exemplo mostra como alterar o arquivo de configuração de sessão que é usado em uma sessão existente chamada "ITTasks". Anteriormente, essas sessões tinham apenas os módulos principais e um módulo **ITTasks** interno. O administrador deseja adicionar o módulo **PSScheduledJob** às sessões criadas usando a configuração de sessão ITTasks.

```powershell
New-PSSessionConfigurationFile -Path .\New-ITTasks.pssc -ModulesToImport Microsoft*, ITTasks, PSScheduledJob
Set-PSSessionConfiguration -Name ITTasks -Path .\New-ITTasks.pssc
```

O `New-PSSessionConfigurationFile` cmdlet para criar um arquivo de configuração de sessão que importa os módulos necessários. O `Set-PSSessionConfiguration` cmdlet substitui o arquivo de configuração atual pelo novo. Essa nova configuração afeta apenas as novas sessões criadas após a alteração.
As sessões "ITTasks" existentes não são afetadas.

### Exemplo 4: editando um arquivo de configuração de sessão

Este exemplo mostra como alterar uma configuração de sessão editando a cópia da configuração de sessão ativa do arquivo de configuração. Para modificar a cópia de configuração de sessão do arquivo de configuração, você deve ter acesso de controle total ao arquivo. Isso pode exigir que você altere as permissões no arquivo.

Nesse cenário, queremos adicionar um novo alias para o `Select-String` cmdlet editando o arquivo de configuração ativa.

O código de exemplo a seguir executa as seguintes etapas para fazer essa alteração:

1. Obtenha o caminho do arquivo de configuração para a sessão ITConfig.
1. O usuário edita o arquivo de configuração usando **Notepad.exe** para alterar o valor de **AliasDefinitions** da seguinte maneira: `AliasDefinitions = @(@{Name='slst';Value='Select-String'})` .
1. Teste o arquivo de configuração atualizado.

```powershell
$ITConfig = Get-PSSessionConfiguration -Name ITConfig
notepad.exe $ITConfig.ConfigFilePath
Test-PSSessionConfigurationFile -Path $ITConfig.ConfigFilePath
```

```Output
True
```

Use o parâmetro **Verbose** com `Test-PSSessionConfigurationFile` para exibir todos os erros detectados. O cmdlet retorna `$True` se nenhum erro for detectado no arquivo.

### Exemplo 5: criar um arquivo de configuração de exemplo

Este exemplo mostra um `New-PSSessionConfigurationFile` comando que usa todos os parâmetros de cmdlet.
Ele é fornecido para mostrar o formato correto de entrada para cada parâmetro.

O SampleFile.pssc resultante é exibido na saída.

```powershell
$configSettings = @{
    Path = '.\SampleFile.pssc'
    SchemaVersion = '1.0.0.0'
    Author = 'User01'
    Copyright = '(c) Fabrikam Corporation. All rights reserved.'
    CompanyName = 'Fabrikam Corporation'
    Description = 'This is a sample file.'
    ExecutionPolicy = 'AllSigned'
    PowerShellVersion = '3.0'
    LanguageMode = 'FullLanguage'
    SessionType = 'Default'
    EnvironmentVariables = @{TESTSHARE='\\Test2\Test'}
    ModulesToImport = @{ModuleName='PSScheduledJob'; ModuleVersion='1.0.0.0'; GUID='50cdb55f-5ab7-489f-9e94-4ec21ff51e59'},'PSDiagnostics'
    AssembliesToLoad = 'System.Web.Services','FSharp.Compiler.CodeDom.dll'
    TypesToProcess = 'Types1.ps1xml','Types2.ps1xml'
    FormatsToProcess = 'CustomFormats.ps1xml'
    ScriptsToProcess = 'Get-Inputs.ps1'
    AliasDefinitions = @{Name='hlp';Value='Get-Help';Description='Gets help.';Options='AllScope'},
        @{Name='Update';Value='Update-Help';Description='Updates help';Options='ReadOnly'}
    FunctionDefinitions = @{Name='Get-Function';ScriptBlock={Get-Command -CommandType Function};Options='ReadOnly'}
    VariableDefinitions = @{Name='WarningPreference';Value='SilentlyContinue'}
    VisibleAliases = 'c*','g*','i*','s*'
    VisibleCmdlets = 'Get*'
    VisibleFunctions = 'Get*'
    VisibleProviders = 'FileSystem','Function','Variable'
    RunAsVirtualAccount = $true
    RunAsVirtualAccountGroups = 'Backup Operators'
}
New-PSSessionConfigurationFile @configSettings
Get-Content SampleFile.pssc
```

```Output
@{

# Version number of the schema used for this document
SchemaVersion = '1.0.0.0'

# ID used to uniquely identify this document
GUID = '1caeff7f-27ca-4360-97cf-37846f594235'

# Author of this document
Author = 'User01'

# Description of the functionality provided by these settings
Description = 'This is a sample file.'

# Company associated with this document
CompanyName = 'Fabrikam Corporation'

# Copyright statement for this document
Copyright = '(c) Fabrikam Corporation. All rights reserved.'

# Session type defaults to apply for this session configuration. Can be 'RestrictedRemoteServer' (recommended), 'Empty', or 'Default'
SessionType = 'Default'

# Directory to place session transcripts for this session configuration
# TranscriptDirectory = 'C:\Transcripts\'

# Whether to run this session configuration as the machine's (virtual) administrator account
RunAsVirtualAccount = $true

# Groups associated with machine's (virtual) administrator account
RunAsVirtualAccountGroups = 'Backup Operators'

# Scripts to run when applied to a session
ScriptsToProcess = 'Get-Inputs.ps1'

# User roles (security groups), and the role capabilities that should be applied to them when applied to a session
# RoleDefinitions = @{ 'CONTOSO\SqlAdmins' = @{ RoleCapabilities = 'SqlAdministration' }; 'CONTOSO\SqlManaged' = @{ RoleCapabilityFiles = 'C:\RoleCapability\SqlManaged.psrc' }; 'CONTOSO\ServerMonitors' = @{ VisibleCmdlets = 'Get-Process' } }

# Language mode to apply when applied to a session. Can be 'NoLanguage' (recommended), 'RestrictedLanguage', 'ConstrainedLanguage', or 'FullLanguage'
LanguageMode = 'FullLanguage'

# Execution policy to apply when applied to a session
ExecutionPolicy = 'AllSigned'

# Version of the PowerShell engine to use when applied to a session
PowerShellVersion = '3.0'

# Modules to import when applied to a session
ModulesToImport = @{
    'GUID' = '50cdb55f-5ab7-489f-9e94-4ec21ff51e59'
    'ModuleName' = 'PSScheduledJob'
    'ModuleVersion' = '1.0.0.0' }, 'PSDiagnostics'

# Aliases to make visible when applied to a session
VisibleAliases = 'c*', 'g*', 'i*', 's*'

# Cmdlets to make visible when applied to a session
VisibleCmdlets = 'Get*'

# Functions to make visible when applied to a session
VisibleFunctions = 'Get*'

# Providers to make visible when applied to a session
VisibleProviders = 'FileSystem', 'Function', 'Variable'

# Aliases to be defined when applied to a session
AliasDefinitions = @{
    'Description' = 'Gets help.'
    'Name' = 'hlp'
    'Options' = 'AllScope'
    'Value' = 'Get-Help' }, @{
    'Description' = 'Updates help'
    'Name' = 'Update'
    'Options' = 'ReadOnly'
    'Value' = 'Update-Help' }

# Functions to define when applied to a session
FunctionDefinitions = @{
    'Name' = 'Get-Function'
    'Options' = 'ReadOnly'
    'ScriptBlock' = {Get-Command -CommandType Function} }

# Variables to define when applied to a session
VariableDefinitions = @{
    'Name' = 'WarningPreference'
    'Value' = 'SilentlyContinue' }

# Environment variables to define when applied to a session
EnvironmentVariables = @{
    'TESTSHARE' = '\\Test2\Test' }

# Type files (.ps1xml) to load when applied to a session
TypesToProcess = 'Types1.ps1xml', 'Types2.ps1xml'

# Format files (.ps1xml) to load when applied to a session
FormatsToProcess = 'CustomFormats.ps1xml'

# Assemblies to load when applied to a session
AssembliesToLoad = 'System.Web.Services', 'FSharp.Compiler.CodeDom.dll'

}
```

## PARAMETERS

### -AliasDefinitions

Adiciona os aliases especificados às sessões que usam a configuração de sessão. Insira uma tabela de hash com as seguintes chaves:

- Nome-nome do alias. Essa chave é necessária.
- Value-o comando que o alias representa. Essa chave é necessária.
- Descrição-uma cadeia de texto que descreve o alias. Essa chave é opcional.
- Opções-opções de alias. Essa chave é opcional. O valor padrão é **None**. Os valores aceitáveis para esse parâmetro são: None, ReadOnly, Constant, Private ou alscope.

Por exemplo: `@{Name='hlp';Value='Get-Help';Description='Gets help';Options='ReadOnly'}`

```yaml
Type: System.Collections.IDictionary[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AssembliesToLoad

Especifica os assemblies para carregar nas sessões que usam a configuração de sessão.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Autor

Especifica o autor da configuração de sessão ou o arquivo de configuração. O padrão é o usuário atual. O valor desse parâmetro é visível no arquivo de configuração de sessão, mas não é uma propriedade do objeto de configuração da sessão.

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

### -CompanyName

Especifica a empresa que criou a configuração de sessão ou o arquivo de configuração. O valor padrão é **Desconhecido**. O valor desse parâmetro é visível no arquivo de configuração de sessão, mas não é uma propriedade do objeto de configuração da sessão.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Unknown
Accept pipeline input: False
Accept wildcard characters: False
```

### -Direitos autorais

Especifica um direito autoral do arquivo de configuração de sessão. O valor desse parâmetro é visível no arquivo de configuração de sessão, mas não é uma propriedade do objeto de configuração da sessão.

Se você omitir esse parâmetro, o `New-PSSessionConfigurationFile` gerará uma declaração de direitos autorais usando o valor do parâmetro **Author** .

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

### -Description

Especifica uma descrição da configuração de sessão ou do arquivo de configuração de sessão. O valor desse parâmetro é visível no arquivo de configuração de sessão, mas não é uma propriedade do objeto de configuração da sessão.

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

### -EnvironmentVariables

Adiciona variáveis de ambiente à sessão. Insira uma tabela de hash na qual as chaves são nomes de variáveis de ambiente e os valores são valores de variáveis de ambiente.

Por exemplo: `EnvironmentVariables=@{TestShare='\\Server01\TestShare'}`

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExecutionPolicy

Especifica a política de execução de sessões que usam a configuração de sessão. Se você omitir esse parâmetro, o valor da chave **ExecutionPolicy** no arquivo de configuração de sessão será **restrito**. Para obter informações sobre as políticas de execução no PowerShell, consulte [about_Execution_Policies](about/about_Execution_Policies.md).

```yaml
Type: Microsoft.PowerShell.ExecutionPolicy
Parameter Sets: (All)
Aliases:
Accepted values: Unrestricted, RemoteSigned, AllSigned, Restricted, Default, Bypass, Undefined

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FormatsToProcess

Especifica os arquivos de formatação (.ps1xml) executados em sessões que usam a configuração de sessão.
O valor desse parâmetro deve ser um caminho completo ou absoluto dos arquivos de formatação.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Full

Indica que essa operação inclui todas as propriedades de configuração possíveis no arquivo de configuração de sessão.

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

### -FunctionDefinitions

Adiciona as funções especificadas às sessões que usam a configuração de sessão. Insira uma tabela de hash com as seguintes chaves:

- Nome-nome da função. Essa chave é necessária.
- ScriptBlock-corpo da função. Insira um bloco de script. Essa chave é necessária.
- Opções-opções de função. Essa chave é opcional. O valor padrão é **None**. Os valores aceitáveis para esse parâmetro são: None, ReadOnly, Constant, Private ou alscope.

Por exemplo: `@{Name='Get-PowerShellProcess';ScriptBlock={Get-Process PowerShell};Options='AllScope'}`

```yaml
Type: System.Collections.IDictionary[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupManagedServiceAccount

Configura sessões usando essa configuração de sessão para execução no contexto da conta de serviço gerenciado de grupo especificada. O computador em que essa configuração de sessão está registrada deve ter permissão para solicitar a senha gMSA para que as sessões sejam criadas com êxito. Este campo não pode ser usado com o parâmetro **RunAsVirtualAccount** .

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

### -GUID

Especifica um identificador exclusivo para o arquivo de configuração de sessão. Se você omitir esse parâmetro, o `New-PSSessionConfigurationFile` gerará um GUID para o arquivo. Para criar um novo GUID no PowerShell, digite `New-Guid` .

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Languagemode

Determina quais elementos da linguagem do PowerShell são permitidos em sessões que usam essa configuração de sessão. Você pode usar esse parâmetro para restringir os comandos que usuários específicos podem executar no computador.

Os valores aceitáveis para esse parâmetro são:

- FullLanguage-todos os elementos de linguagem são permitidos.
- ConstrainedLanguage-os comandos que contêm scripts a serem avaliados não são permitidos. O modo ConstrainedLanguage restringe o acesso do usuário a tipos, objetos ou métodos do Microsoft .NET Framework.
- Nolanguage-os usuários podem executar cmdlets e funções, mas não têm permissão para usar nenhum elemento de linguagem, como blocos de script, variáveis ou operadores.
- RestrictedLanguage-os usuários podem executar cmdlets e funções, mas não têm permissão para usar os blocos de script ou variáveis, exceto as seguintes variáveis permitidas:,,, `$PSCulture` `$PSUICulture` `$True` `$False` e `$Null` . Os usuários podem usar apenas os operadores de comparação básicos ( `-eq` , `-gt` , `-lt` ). Não são permitidas instruções de atribuição, referências de propriedade e chamadas de método.

O valor padrão do parâmetro **LanguageMode** depende do valor do parâmetro **SessionType**.

- Vazio – não idioma
- RestrictedRemoteServer-nolanguage
- Padrão-FullLanguage

```yaml
Type: System.Management.Automation.PSLanguageMode
Parameter Sets: (All)
Aliases:
Accepted values: FullLanguage, RestrictedLanguage, NoLanguage, ConstrainedLanguage

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ModulesToImport

Especifica os módulos e snap-ins que são importados automaticamente nas sessões que usam a configuração de sessão.

Por padrão, somente o snap-in **Microsoft. PowerShell. Core** é importado para sessões remotas, mas a menos que os cmdlets sejam excluídos, os usuários podem usar os `Import-Module` `Add-PSSnapin` cmdlets e para adicionar módulos e snap-ins à sessão.

Cada módulo ou o snap-in no valor desse parâmetro pode ser representado por uma cadeia de caracteres ou como uma tabela de hash. Uma cadeia de caracteres de módulo consiste apenas no nome do módulo ou snap-in. Uma tabela de hash de módulo pode incluir as chaves **ModuleName** , **ModuleVersion** e **GUID** . Somente a chave **ModuleName** é necessária.

Por exemplo, o seguinte valor consiste em uma cadeia de caracteres e uma tabela de hash. Qualquer combinação de cadeias de caracteres e tabelas de hash, em qualquer ordem, é válida.

`'TroubleshootingPack', @{ModuleName='PSDiagnostics'; ModuleVersion='1.0.0.0';GUID='c61d6278-02a3-4618-ae37-a524d40a7f44'}`

O valor do parâmetro **ModulesToImport** do `Register-PSSessionConfiguration` cmdlet tem precedência sobre o valor da chave **ModulesToImport** no arquivo de configuração de sessão.

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MountUserDrive

Configura as sessões que usam essa configuração de sessão para expor a `User:` PSDrive. As unidades de usuário são exclusivas para cada usuário conectado e permitem que os usuários copiem dados de e para pontos de extremidade do PowerShell, mesmo que o provedor do sistema de arquivos não esteja exposto. As raízes da unidade do usuário são criadas em `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\DriveRoots\` . Para cada usuário que se conecta ao ponto de extremidade, uma pasta é criada com o nome `$env:USERDOMAIN_$env:USERNAME`.

O conteúdo na unidade de usuário persiste entre as sessões do usuário e não é removido automaticamente. Por padrão, os usuários só podem armazenar até 50 MB de dados na unidade do usuário. Isso pode ser personalizado com o parâmetro **UserDriveMaximumSize** .

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

Especifica o caminho e o nome do arquivo de configuração de sessão. O arquivo deve ter uma `.pssc` extensão de nome de arquivo.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PowerShellVersion

Especifica a versão do mecanismo do PowerShell em sessões que usam a configuração de sessão. Os valores aceitáveis para esse parâmetro são: 2,0 e 3,0. Se você omitir esse parâmetro, a chave **PowerShellVersion** será comentada e a versão mais recente do PowerShell será executada na sessão.

O valor do parâmetro **psversion** do `Register-PSSessionConfiguration` cmdlet tem precedência sobre o valor da chave **PowerShellVersion** no arquivo de configuração de sessão.

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequiredGroups

Especifica regras de acesso condicional para usuários que se conectam a sessões que usam essa configuração de sessão.

Insira uma tabela de hash para compor sua lista de regras usando apenas uma chave por Hashtable, ' and ' ou ' or ', e defina o valor como uma matriz de nomes de grupos de segurança ou Hashtables adicionais.

Exemplo que exige a conexão de usuários para serem membros de um único grupo: `@{ And = 'MyRequiredGroup' }`

Exemplo que exigem que os usuários pertençam ao grupo A ou aos dois grupos B e C para acessar o ponto de extremidade: `@{ Or = 'GroupA', @{ And = 'GroupB', 'GroupC' } }`

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RoleDefinitions

Especifica o mapeamento entre grupos de segurança (ou usuários) e recursos de função. Os usuários receberão acesso a todos os recursos de função que se aplicam à sua associação de grupo no momento em que a sessão é criada.

Insira uma tabela de hash na qual as chaves são o nome do grupo de segurança e os valores são tabelas de hash que contêm uma lista de recursos de função que devem ser disponibilizados para o grupo de segurança.

Por exemplo: `@{'Contoso\Level 2 Helpdesk Users' = @{ RoleCapabilities = 'Maintenance', 'ADHelpDesk' }}`

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsVirtualAccount

Configura sessões que usam essa configuração de sessão para serem executadas como a conta de administrador do computador (virtual). Este campo não pode ser usado com o parâmetro **GroupManagedServiceAccount** .

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

### -RunAsVirtualAccountGroups

Especifica os grupos de segurança a serem associados à conta virtual quando uma sessão que usa a configuração de sessão é executada como uma conta virtual. Se omitido, a conta virtual pertence a administradores de domínio em controladores de domínio e administradores em todos os outros computadores.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SchemaVersion

Especifica a versão do esquema de arquivo de configuração de sessão. O valor padrão é "1.0.0.0".

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptsToProcess

Adiciona os scripts especificados às sessões que usam a configuração de sessão. Digite os nomes de arquivo e caminho dos scripts. O valor desse parâmetro deve ser um caminho completo ou absoluto de nomes de arquivo de script.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SessionType

Especifica o tipo de sessão que é criada usando a configuração da sessão. O valor padrão é Default. Os valores aceitáveis para esse parâmetro são:

- Empty-nenhum módulo é adicionado à sessão por padrão. Use os parâmetros desse cmdlet para adicionar módulos, funções, scripts e outros recursos à sessão. Essa opção foi projetada para que você crie sessões personalizadas adicionando comandos selecionados. Se não adicionar comandos a uma sessão vazia, a sessão é limitada a expressões e não pode ser utilizada.
- Padrão-adiciona o módulo Microsoft. PowerShell. Core à sessão. Esse módulo inclui o `Import-Module` cmdlet que os usuários podem usar para importar outros módulos, a menos que você proíba explicitamente esse cmdlet.
- RestrictedRemoteServer. Inclui apenas as seguintes funções de proxy:,,,,, `Exit-PSSession` `Get-Command` `Get-FormatData` `Get-Help` `Measure-Object` `Out-Default` e `Select-Object` .
  Use os parâmetros desse cmdlet para adicionar módulos, funções, scripts e outros recursos à sessão.

```yaml
Type: System.Management.Automation.Remoting.SessionType
Parameter Sets: (All)
Aliases:
Accepted values: Empty, RestrictedRemoteServer, Default

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TranscriptDirectory

Especifica o diretório para posicionar transcrições de sessão para sessões usando essa configuração de sessão.

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

### -TypesToProcess

Adiciona os `.ps1xml` arquivos de tipo especificados às sessões que usam a configuração de sessão. Insira os nomes de filetype. O valor desse parâmetro deve ser um caminho completo ou absoluto para digitar os nomes de texto.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserDriveMaximumSize

Especifica o tamanho máximo para unidades de usuário expostas em sessões que usam essa configuração de sessão.
Quando omitido, o tamanho padrão de cada `User:` unidade raiz é 50 MB.

Esse parâmetro deve ser usado com **MountUserDrive**.

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VariableDefinitions

Adiciona as variáveis especificadas às sessões que usam a configuração de sessão. Insira uma tabela de hash com as seguintes chaves:

- Nome-nome da variável. Essa chave é necessária.
- Valor-variável de valor. Essa chave é necessária.
- Opções – opções de variáveis. Essa chave é opcional. O valor padrão é **None**. Os valores aceitáveis para esse parâmetro são: None, ReadOnly, Constant, Private ou alscope.

Por exemplo: `@{Name='WarningPreference';Value='SilentlyContinue';Options='AllScope'}`

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VisibleAliases

Limita os aliases na sessão aos especificados no valor desse parâmetro, além de todos os aliases definidos no parâmetro **AliasDefinition**. Há suporte para caracteres curinga. Por padrão, todos os aliases que são definidos pelo mecanismo do PowerShell e todos os aliases que os módulos exportam são visíveis na sessão.

Por exemplo: `VisibleAliases='gcm', 'gp'`

Quando qualquer parâmetro **visível** é incluído no arquivo de configuração de sessão, o PowerShell remove o `Import-Module` cmdlet e seu alias ipmo da sessão.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -VisibleCmdlets

Limita os cmdlets na sessão para aquelas especificadas no valor desse parâmetro. Há suporte para caracteres curinga e nomes qualificados de módulo.

Por padrão, todos os cmdlets que os módulos na sessão exportam são visíveis na sessão. Use os parâmetros **SessionType** e **ModulesToImport** para determinar quais módulos e snap-ins são importados para a sessão. Se nenhum módulo no **ModulesToImport** expor o cmdlet, o módulo apropriado tentará ser carregado de forma autocarregada.

Quando qualquer parâmetro **visível** é incluído no arquivo de configuração de sessão, o PowerShell remove o `Import-Module` cmdlet e seu alias ipmo da sessão.

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VisibleExternalCommands

Limita os binários, scripts e comandos externos que podem ser executados na sessão para aqueles especificados no valor desse parâmetro. Há suporte para caracteres curinga.

Por padrão, nenhum comando externo é visível na sessão.

Quando qualquer parâmetro **visível** é incluído no arquivo de configuração de sessão, o PowerShell remove o `Import-Module` cmdlet e seu alias ipmo da sessão.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -VisibleFunctions

Limita as funções na sessão às especificadas no valor desse parâmetro, além de todas as funções que você define no parâmetro **FunctionDefinition**. Há suporte para caracteres curinga.

Por padrão, todos as funções que os módulos na sessão exportam são visíveis na sessão. Use os parâmetros **SessionType** e **ModulesToImport** para determinar quais módulos e snap-ins são importados para a sessão.

Quando qualquer parâmetro **visível** é incluído no arquivo de configuração de sessão, o PowerShell remove o `Import-Module` cmdlet e seu alias ipmo da sessão.

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -VisibleProviders

Limita os provedores do PowerShell na sessão para aqueles especificados no valor desse parâmetro.
Há suporte para caracteres curinga.

Por padrão, todos os provedores que os módulos na sessão exportam são visíveis na sessão. Use os parâmetros **SessionType** e **ModulesToImport** para determinar quais módulos serão importados para a sessão.

Quando qualquer parâmetro **visível** é incluído no arquivo de configuração de sessão, o PowerShell remove o `Import-Module` cmdlet e seu `ipmo` alias da sessão.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Não é possível canalizar nenhum objeto para este cmdlet.

## SAÍDAS

### Nenhum

Este cmdlet não gera saída.

## OBSERVAÇÕES

Esse cmdlet só está disponível em plataformas Windows.

- Os parâmetros, como **VisibleCmdlets** e **VisibleProviders** , não importam itens para a sessão. Em vez disso, eles selecionam entre os itens importados para a sessão. Por exemplo, se o valor do parâmetro **VisibleProviders** for o provedor de certificado, mas o parâmetro **ModulesToImport** não especificar o módulo **Microsoft. PowerShell. Security** que contém o provedor de certificado, o provedor de certificado não estará visível na sessão.
- `New-PSSessionConfigurationFile` Cria um arquivo de configuração de sessão que tem uma extensão de nome de arquivo. PSSC no caminho que você especificar no parâmetro **path** . Quando você usa o arquivo de configuração de sessão para criar uma configuração de sessão, o `Register-PSSessionConfiguration` cmdlet copia o arquivo de configuração e salva uma cópia ativa do arquivo no subdiretório **SessionConfig** do `$PSHOME` diretório.

  A propriedade **ConfigFilePath** da configuração de sessão contém o caminho totalmente qualificado do arquivo de configuração de sessão ativa. Você pode modificar o arquivo de configuração ativo no `$PSHOME` diretório a qualquer momento usando qualquer editor de texto. As alterações feitas afetam todas as novas sessões que usam a configuração de sessão, mas sessões não existentes.

  Antes de usar um arquivo de configuração de sessão editado, use o `Test-PSSessionConfigurationFile` cmdlet para verificar se as entradas do arquivo de configuração são válidas.

## LINKS RELACIONADOS

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Disable-PSSessionConfiguration](Enable-PSSessionConfiguration.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Test-PSSessionConfigurationFile](Test-PSSessionConfigurationFile.md)

[Unregister-PSSessionConfiguration](Unregister-PSSessionConfiguration.md)

[Provedor WSMan](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[about_Session_Configurations](About/about_Session_Configurations.md)

[about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)
