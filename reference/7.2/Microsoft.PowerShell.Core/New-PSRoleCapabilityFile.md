---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 09/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-psrolecapabilityfile?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSRoleCapabilityFile
ms.openlocfilehash: 3ef54618e065a5fca3d52415897b3042d6ba4c65
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598848"
---
# New-PSRoleCapabilityFile

## SINOPSE
Cria um arquivo que define um conjunto de recursos a serem expostos por meio de uma configuração de sessão.

## SYNTAX

```
New-PSRoleCapabilityFile [-Path] <String> [-Guid <Guid>] [-Author <String>] [-Description <String>]
 [-CompanyName <String>] [-Copyright <String>] [-ModulesToImport <Object[]>] [-VisibleAliases <String[]>]
 [-VisibleCmdlets <Object[]>] [-VisibleFunctions <Object[]>] [-VisibleExternalCommands <String[]>]
 [-VisibleProviders <String[]>] [-ScriptsToProcess <String[]>] [-AliasDefinitions <IDictionary[]>]
 [-FunctionDefinitions <IDictionary[]>] [-VariableDefinitions <Object>] [-EnvironmentVariables <IDictionary>]
 [-TypesToProcess <String[]>] [-FormatsToProcess <String[]>] [-AssembliesToLoad <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION

O `New-PSRoleCapabilityFile` cmdlet cria um arquivo que define um conjunto de recursos de usuário que pode ser exposto por meio de arquivos de configuração de sessão. Isso inclui determinar quais cmdlets, funções e scripts estão disponíveis para os usuários. O arquivo de capacidade é um arquivo de texto legível que contém uma tabela de hash de valores e propriedades de configuração de sessão. O arquivo tem uma extensão de nome de arquivo. pSrc e pode ser usado por mais de uma configuração de sessão.

Todos os parâmetros de `New-PSRoleCapabilityFile` são opcionais, exceto o parâmetro **Path** , que especifica o caminho do arquivo para o arquivo. Se você não incluir um parâmetro ao executar o cmdlet, a chave correspondente no arquivo de configuração de sessão será comentada, exceto quando indicado na descrição do parâmetro. Por exemplo, se você não incluir o parâmetro **AssembliesToLoad** , essa seção do arquivo de configuração de sessão será comentada.

Para usar o arquivo de capacidade de função em uma configuração de sessão, primeiro coloque o arquivo em uma subpasta **RoleCapabilities** de uma pasta de módulo do PowerShell válida. Em seguida, referencie o arquivo pelo nome no campo **RoleDefinitions** em um arquivo de configuração de sessão do PowerShell (. PSSC).

Esse cmdlet foi introduzido no Windows PowerShell 5,0.

## EXEMPLOS

### Exemplo 1: criar um arquivo de capacidade de função em branco

Este exemplo cria um novo arquivo de capacidade de função que usa os valores padrão (em branco). O arquivo pode ser editado posteriormente em um editor de texto para alterar essas definições de configuração.

```powershell
New-PSRoleCapabilityFile -Path ".\ExampleFile.psrc"
```

### Exemplo 2: criar um arquivo de capacidade de função permitindo que os usuários reiniciem serviços e qualquer computador VDI

Este exemplo cria um arquivo de capacidade de função de exemplo que permite que os usuários reiniciem serviços e computadores que correspondam a um padrão de nome específico. A filtragem de nomes é definida pela definição do parâmetro **ValidatePattern** para a expressão regular `VDI\d+` .

```powershell
$roleParameters = @{
    Path = ".\Maintenance.psrc"
    Author = "User01"
    CompanyName = "Fabrikam Corporation"
    Description = "This role enables users to restart any service and restart any VDI computer."
    ModulesToImport = "Microsoft.PowerShell.Core"
    VisibleCmdlets = "Restart-Service", @{
                      Name = "Restart-Computer"
                      Parameters = @{ Name = "ComputerName"; ValidatePattern = "VDI\d+" }
    }
}
New-PSRoleCapabilityFile @roleParameters
```

## PARAMETERS

### -AliasDefinitions

Adiciona os aliases especificados a sessões que usam o arquivo de capacidade de função. Insira uma tabela de hash com as seguintes chaves:

- Nome. Nome do alias. Essa chave é necessária.
- Value. O comando que o alias representa. Essa chave é necessária.
- Descrição. Uma cadeia de caracteres de texto que descreve o alias. Essa chave é opcional.
- Opções. Opções de alias. Essa chave é opcional. O valor padrão é Nenhum. Os valores aceitáveis para esse parâmetro são: None, ReadOnly, Constant, Private ou alscope.

Por exemplo: `@{Name="hlp";Value="Get-Help";Description="Gets help";Options="ReadOnly"}`

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

Especifica os assemblies a serem carregados nas sessões que usam o arquivo de capacidade de função.

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

Especifica o usuário que criou o arquivo de capacidade de função.

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

Identifica a empresa que criou o arquivo de capacidade de função.
O valor padrão é Desconhecido.

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

### -Direitos autorais

Especifica um direito autoral para o arquivo de capacidade de função. Se você omitir esse parâmetro, o `New-PSRoleCapabilityFile` gerará uma declaração de direitos autorais usando o valor do parâmetro **Author** .

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

Especifica uma descrição para o arquivo de capacidade de função.

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

Especifica as variáveis de ambiente para sessões que expõem esse arquivo de capacidade de função. Insira uma tabela de hash na qual as chaves são nomes de variáveis de ambiente e os valores são valores de variáveis de ambiente.

Por exemplo: `EnvironmentVariables=@{TestShare="\\\\Server01\TestShare"}`

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

### -FormatsToProcess

Especifica os arquivos de formatação (. ps1xml) que são executados em sessões que usam o arquivo de capacidade de função. O valor desse parâmetro deve ser um caminho completo ou absoluto dos arquivos de formatação.

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

### -FunctionDefinitions

Adiciona as funções especificadas às sessões que expõem a capacidade de função. Insira uma tabela de hash com as seguintes chaves:

- Nome. Nome da função. Essa chave é necessária.
- ScriptBlock. Corpo da função. Insira um bloco de script. Essa chave é necessária.
- Opções. Opções de função. Essa chave é opcional. O valor padrão é Nenhum. Os valores aceitáveis para esse parâmetro são: None, ReadOnly, Constant, Private ou alscope.

Por exemplo:

`@{Name="Get-PowerShellProcess";ScriptBlock={Get-Process PowerShell};Options="AllScope"}`

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

### -GUID

Especifica um identificador exclusivo para o arquivo de capacidade de função. Se você omitir esse parâmetro, o `New-PSRoleCapabilityFile` gerará um GUID para o arquivo. Para criar um novo GUID no PowerShell, digite `[guid]::NewGuid()` .

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

### -ModulesToImport

Especifica os módulos que são automaticamente importados para sessões que usam o arquivo de capacidade de função. Por padrão, todos os comandos nos módulos listados são visíveis. Quando usado com **VisibleCmdlets** ou **VisibleFunctions**, os comandos visíveis dos módulos especificados podem ser restritos.

Cada módulo usado no valor desse parâmetro pode ser representado por uma cadeia de caracteres ou por uma tabela de hash. Uma cadeia de caracteres de módulo consiste apenas no nome do módulo. Uma tabela de hash de módulo pode incluir as chaves **ModuleName**, **ModuleVersion** e **GUID** . Somente a chave **ModuleName** é necessária.

Por exemplo, o seguinte valor consiste em uma cadeia de caracteres e uma tabela de hash. Qualquer combinação de cadeias de caracteres e tabelas de hash, em qualquer ordem, é válida.

`"TroubleshootingPack", @{ModuleName="PSDiagnostics"; ModuleVersion="1.0.0.0";GUID="c61d6278-02a3-4618-ae37-a524d40a7f44"}`

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

### -Path

Especifica o caminho e o nome do arquivo de capacidade de função. O arquivo deve ter uma `.psrc` extensão de nome de arquivo.

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

### -ScriptsToProcess

Especifica os scripts a serem adicionados às sessões que usam o arquivo de capacidade de função. Digite os nomes de arquivo e caminho dos scripts. O valor desse parâmetro deve ser um caminho completo ou absoluto dos nomes de arquivo de script.

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

### -TypesToProcess

Especifica os arquivos de tipo (. ps1xml) a serem adicionados às sessões que usam o arquivo de capacidade de função. Insira os nomes de filetype. O valor desse parâmetro deve ser um caminho completo ou absoluto do tipo nomes de texto.

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

### -VariableDefinitions

Especifica as variáveis a serem adicionadas às sessões que usam o arquivo de capacidade de função. Insira uma tabela de hash com as seguintes chaves:

- Nome. Nome da variável. Essa chave é necessária.
- Value. Valor da variável. Essa chave é necessária.
- Opções. Opções de variáveis. Essa chave é opcional. O valor padrão é Nenhum. Os valores aceitáveis para esse parâmetro são: None, ReadOnly, Constant, Private ou alscope.

Por exemplo: `@{Name="WarningPreference";Value="SilentlyContinue";Options="AllScope"}`

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

Limita os aliases na sessão para os aliases especificados no valor desse parâmetro, além de todos os aliases que você definir no parâmetro **AliasDefinition** . Há suporte para caracteres curinga.
Por padrão, todos os aliases que são definidos pelo mecanismo do PowerShell e todos os aliases que os módulos exportam são visíveis na sessão.

Por exemplo, para limitar os aliases disponíveis para o GM e o gcm, use esta sintaxe: `VisibleAliases="gcm", "gp"`

Quando qualquer parâmetro **visível** é incluído no arquivo de capacidade de função, o PowerShell remove o `Import-Module` cmdlet e seu `ipmo` alias da sessão.

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

Por padrão, todos os cmdlets que os módulos na sessão exportam são visíveis na sessão. Use os parâmetros **SessionType** e **ModulesToImport** para determinar quais módulos e snap-ins são importados para a sessão. Se nenhum módulo no **ModulesToImport** expor o cmdlet, o `New-PSRoleCapabilityFile` tentará carregar o módulo apropriado.

Quando qualquer parâmetro **visível** é incluído no arquivo de configuração de sessão, o PowerShell remove o `Import-Module` cmdlet e seu `ipmo` alias da sessão.

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

### -VisibleExternalCommands

Limita os binários, os scripts e os comandos externos que podem ser executados na sessão para aqueles especificados no valor desse parâmetro.

Por padrão, nenhum comando externo é visível nesta sessão.

Quando qualquer parâmetro **visível** é incluído no arquivo de configuração de sessão, o PowerShell remove o `Import-Module` cmdlet e seu `ipmo` alias da sessão.

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

### -VisibleFunctions

Limita as funções na sessão àqueles especificados no valor desse parâmetro, além de qualquer função que você definir no parâmetro **FunctionDefinitions** . Há suporte para caracteres curinga.

Por padrão, todas as funções exportadas por módulos na sessão ficam visíveis nessa sessão. Use os parâmetros **SessionType** e **ModulesToImport** para determinar quais módulos serão importados para a sessão.

Quando qualquer parâmetro **visível** é incluído no arquivo de configuração de sessão, o PowerShell remove o `Import-Module` cmdlet e seu `ipmo` alias da sessão.

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

Por padrão, todos os provedores exportados por um módulo na sessão ficam visíveis na sessão. Use os parâmetros **SessionType** e **ModulesToImport** para determinar quais módulos serão importados para a sessão.

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

## SAÍDAS

## OBSERVAÇÕES

## LINKS RELACIONADOS

[New-PSSessionConfigurationFile](New-PSSessionConfigurationFile.md)

[Get-PSSessionCapability](Get-PSSessionCapability.md)

