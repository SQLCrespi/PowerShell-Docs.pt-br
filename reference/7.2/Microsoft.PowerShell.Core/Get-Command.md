---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/05/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-command?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Command
ms.openlocfilehash: 092b7bff345340a8e2d30136517537c375074df1
ms.sourcegitcommit: d95a7255f6775b2973aa9473611185a5583881ff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/07/2021
ms.locfileid: "106555450"
---
# Get-Command

## Sinopse
Obtém todos os comandos.

## Syntax

### CmdletSet (padrão)

```
Get-Command [-Verb <String[]>] [-Noun <String[]>] [-Module <String[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [-TotalCount <Int32>] [-Syntax] [-ShowCommandInfo]
 [[-ArgumentList] <Object[]>] [-All] [-ListImported] [-ParameterName <String[]>]
 [-ParameterType <PSTypeName[]>] [<CommonParameters>]
```

### Setcommandset

```
Get-Command [[-Name] <String[]>] [-Module <String[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [-CommandType <CommandTypes>] [-TotalCount <Int32>]
 [-Syntax] [-ShowCommandInfo] [[-ArgumentList] <Object[]>] [-All] [-ListImported]
 [-ParameterName <String[]>] [-ParameterType <PSTypeName[]>] [-UseFuzzyMatching]
 [-UseAbbreviationExpansion] [<CommonParameters>]
```

## Descrição

O `Get-Command` cmdlet obtém todos os comandos que estão instalados no computador, incluindo cmdlets, aliases, funções, filtros, scripts e aplicativos. `Get-Command` Obtém os comandos de módulos e comandos do PowerShell que foram importados de outras sessões. Para obter somente comandos que foram importados para a sessão atual, use o parâmetro **ListImported**.

Sem parâmetros, `Get-Command` Obtém todos os cmdlets, funções e aliases instalados no computador. `Get-Command *` Obtém todos os tipos de comandos, incluindo todos os arquivos que não são do PowerShell na variável de ambiente Path ( `$env:Path` ), que é listada no tipo de comando Application.

`Get-Command` que usa o nome exato do comando, sem caracteres curinga, importa automaticamente o módulo que contém o comando para que você possa usar o comando imediatamente. Para habilitar, desabilitar e configurar a importação automática de módulos, use a `$PSModuleAutoLoadingPreference` variável de preferência. Para obter mais informações, consulte [about_Preference_Variables](About/about_Preference_Variables.md).

`Get-Command` Obtém seus dados diretamente do código de comando, ao contrário de `Get-Help` , que obtém suas informações dos tópicos da ajuda.

A partir do Windows PowerShell 5,0, os resultados do `Get-Command` cmdlet exibem uma coluna de **versão** por padrão. Uma nova propriedade **version** foi adicionada à classe **CommandInfo** .

## Exemplos

### Exemplo 1: obter cmdlets, funções e aliases

Esse comando obtém os cmdlets, as funções e os aliases do PowerShell instalados no computador.

```powershell
Get-Command
```

### Exemplo 2: obter comandos na sessão atual

Este comando usa o parâmetro **ListImported** para obter apenas os comandos da sessão atual.

```powershell
Get-Command -ListImported
```

### Exemplo 3: obter cmdlets e exibi-los na ordem

Esse comando obtém todos os cmdlets, os classifica em ordem alfabética pelo substantivo no nome do cmdlet e, em seguida, os exibe em grupos baseados no substantivo. Essa exibição pode ajudar a localizar os cmdlets para uma tarefa.

```powershell
Get-Command -Type Cmdlet | Sort-Object -Property Noun | Format-Table -GroupBy Noun
```

### Exemplo 4: obter comandos em um módulo

Esse comando usa o parâmetro **Module** para obter os comandos nos módulos Microsoft. PowerShell. Security e Microsoft. PowerShell. Utility.

```powershell
Get-Command -Module Microsoft.PowerShell.Security, Microsoft.PowerShell.Utility
```

### Exemplo 5: obter informações sobre um cmdlet

Esse comando obtém informações sobre o `Get-AppLockerPolicy` cmdlet. Ele também importa o módulo **AppLocker**, que adiciona todos os comandos no módulo **AppLocker** à sessão atual.

```powershell
Get-Command Get-AppLockerPolicy
```

Quando um módulo é importado automaticamente, o efeito é o mesmo que usar o cmdlet Import-Module.
O módulo pode adicionar comandos, tipos e arquivos de formatação e executar scripts na sessão. Para habilitar, desabilitar e configurar a importação automática de módulos, use a `$PSModuleAutoLoadingPreference` variável de preferência. Para obter mais informações, consulte [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).

### Exemplo 6: obter a sintaxe de um cmdlet

Esse comando usa os parâmetros **ArgumentList** e **Syntax** para obter a sintaxe do `Get-ChildItem` cmdlet quando ele é usado na unidade CERT:. A unidade CERT: é uma unidade do PowerShell que o provedor de certificado adiciona à sessão.

```powershell
Get-Command  -Name Get-Childitem -Args Cert: -Syntax
```

Ao comparar a sintaxe exibida na saída com a sintaxe que é exibida quando você omite o parâmetro **args** (**ArgumentList**), você verá que o **provedor de certificado** adiciona um parâmetro dinâmico, **CodeSigningCert**, ao `Get-ChildItem` cmdlet.

Para obter mais informações sobre o provedor de certificados, consulte [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).

### Exemplo 7: obter parâmetros dinâmicos

O comando no exemplo usa a `Get-DynamicParameters` função para obter os parâmetros dinâmicos que o provedor de certificado adiciona ao `Get-ChildItem` cmdlet quando ele é usado na unidade CERT:.

```powershell
function Get-DynamicParameters
{
    param ($Cmdlet, $PSDrive)
    (Get-Command -Name $Cmdlet -ArgumentList $PSDrive).ParameterSets | 
      ForEach-Object {$_.Parameters} | 
        Where-Object { $_.IsDynamic } | 
          Select-Object -Property Name -Unique
}
Get-DynamicParameters -Cmdlet Get-ChildItem -PSDrive Cert:
```

```Output
Name
----
CodeSigningCert
```

A `Get-DynamicParameters` função neste exemplo obtém os parâmetros dinâmicos de um cmdlet. Essa é uma alternativa ao método usado no exemplo anterior. O parâmetro dinâmico pode ser adicionado a um cmdlet por outro cmdlet ou por um provedor.

### Exemplo 8: obter todos os comandos de todos os tipos

Esse comando obtém todos os comandos de todos os tipos no computador local, incluindo arquivos executáveis nos caminhos da variável de ambiente **path** ( `$env:path` ).

```powershell
Get-Command *
```

Ele retorna um objeto **ApplicationInfo** (System.Management.Automation.ApplicationInfo) para cada arquivo e não um objeto **FileInfo** (System.IO.FileInfo).

### Exemplo 9: obter cmdlets usando um nome de parâmetro e tipo

Esse comando obtém os cmdlets que têm um parâmetro cujo nome inclui autenticação e cujo tipo é **AuthenticationMechanism**.

```powershell
Get-Command -ParameterName *Auth* -ParameterType AuthenticationMechanism
```

É possível usar um comando como este para localizar cmdlets que permitem que você especifique o método usado para autenticar o usuário.

O parâmetro **ParameterType** distingue parâmetros que usam um valor **AuthenticationMechanism** dos que usam um parâmetro **AuthenticationLevel**, mesmo quando tiverem nomes semelhantes.

### Exemplo 10: obter um alias

Este exemplo mostra como usar o `Get-Command` cmdlet com um alias.

```powershell
Get-Command -Name dir
```

```Output
CommandType     Name                                               ModuleName
-----------     ----                                               ----------
Alias           dir -> Get-ChildItem
```

Embora normalmente seja usado em cmdlets e funções, o `Get-Command` também obtém scripts, funções, aliases e arquivos executáveis.

A saída do comando mostra o modo de exibição especial do valor de propriedade **Name** para aliases. O modo de exibição mostra o alias e o nome completo do comando.

### Exemplo 11: obter a sintaxe de um alias

Este exemplo mostra como obter a sintaxe junto com o nome padrão de um alias.

A saída do comando mostra o alias rotulado com o nome padrão, seguido pela sintaxe.

```powershell
Get-Command -Name dir -Syntax
```

```Output
dir (alias) -> Get-ChildItem

dir [[-Path] <string[]>] [[-Filter] <string>] [-Include <string[]>] [-Exclude <string[]>] [-Recurse] [-Depth <uint>] [-Force] [-Name] [-Attributes <FlagsExpression[FileAttributes]>] [-FollowSymlink] [-Directory] [-File] [-Hidden] [-ReadOnly] [-System] [<CommonParameters>]

dir [[-Filter] <string>] -LiteralPath <string[]> [-Include <string[]>] [-Exclude <string[]>] [-Recurse] [-Depth <uint>] [-Force] [-Name] [-Attributes <FlagsExpression[FileAttributes]>] [-FollowSymlink] [-Directory] [-File] [-Hidden] [-ReadOnly] [-System] [<CommonParameters>]
```

### Exemplo 12: obter todas as instâncias do comando do bloco de notas

Este exemplo usa o parâmetro **All** do `Get-Command` cmdlet para mostrar todas as instâncias do `Notepad` comando no computador local.

```powershell
Get-Command Notepad -All | Format-Table CommandType, Name, Definition
```

```Output
CommandType     Name           Definition
-----------     ----           ----------
Application     notepad.exe    C:\WINDOWS\system32\notepad.exe
Application     NOTEPAD.EXE    C:\WINDOWS\NOTEPAD.EXE
```

O parâmetro **All** é útil quando há mais de um comando com o mesmo nome na sessão.

A partir do Windows PowerShell 3,0, por padrão, quando a sessão inclui vários comandos com o mesmo nome, `Get-Command` obtém apenas o comando que é executado quando você digita o nome do comando. Com o parâmetro **All** , `Get-Command` Obtém todos os comandos com o nome especificado e os retorna na ordem de precedência de execução. Para executar um comando que não seja o primeiro da lista, digite o caminho totalmente qualificado para o comando.

Para obter mais informações sobre a precedência de comando, consulte [about_Command_Precedence](About/about_Command_Precedence.md).

### Exemplo 13: obter o nome de um módulo que contém um cmdlet

Esse comando obtém o nome do módulo no qual o `Get-Date` cmdlet foi originado.
O comando usa a propriedade **ModuleName** de todos os comandos.

```powershell
(Get-Command Get-Date).ModuleName
```

```Output
Microsoft.PowerShell.Utility
```

Esse formato de comando funciona em comandos em módulos do PowerShell, mesmo que eles não sejam importados para a sessão.

### Exemplo 14: obter cmdlets e funções que têm um tipo de saída

```powershell
Get-Command -Type Cmdlet | Where-Object OutputType | Format-List -Property Name, OutputType
```

Esse comando obtém os cmdlets e funções que têm um tipo de saída e os tipos de objetos que eles retornam.

A primeira parte do comando obtém todos os cmdlets. Um operador de pipeline ( `|` ) envia os cmdlets para o `Where-Object` cmdlet, que seleciona apenas aqueles nos quais a propriedade **OutputType** é populada. Outro operador de pipeline envia os objetos de cmdlet selecionados para o `Format-List` cmdlet, que exibe o nome e o tipo de saída de cada cmdlet em uma lista.

A propriedade **OutputType** de um objeto **CommandInfo** tem um valor não nulo somente quando o código do cmdlet define o atributo **OutputType** para o cmdlet.

### Exemplo 15: obter cmdlets que usam um tipo de objeto específico como entrada

```powershell
Get-Command -ParameterType (((Get-NetAdapter)[0]).PSTypeNames)
```

```Output
CommandType     Name                                               ModuleName
-----------     ----                                               ----------
Function        Disable-NetAdapter                                 NetAdapter
Function        Enable-NetAdapter                                  NetAdapter
Function        Rename-NetAdapter                                  NetAdapter
Function        Restart-NetAdapter                                 NetAdapter
Function        Set-NetAdapter                                     NetAdapter
```

Este comando localiza cmdlets que usam objetos de adaptador de rede como entrada. Você pode usar esse formato de comando para localizar os cmdlets que aceitam o tipo de objeto que qualquer comando retorna.

O comando usa a propriedade intrínseca **PSTypeNames** de todos os objetos, que obtém os tipos que descrevem o objeto. Para obter a propriedades **PSTypeNames** de um adaptador de rede e não a propriedade **PSTypeNames** de uma coleção de adaptadores de rede, o comando usa a notação de matriz para obter o primeiro adaptador de rede que o cmdlet retorna.

### Exemplo 16: obter comandos usando uma correspondência difusa

Neste exemplo, o nome do comando deliberadamente tem um tipográfico como ' Get-commnd '.
Usando a `-UseFuzzyMatching` opção, o cmdlet determinou que a melhor correspondência foi `Get-Command` seguida por outros comandos nativos no sistema que eram uma correspondência semelhante.

```powershell
Get-Command get-commnd -UseFuzzyMatching
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Get-Command                                        6.2.0.0    Microsoft.PowerShell.Core
Application     getconf                                            0.0.0.0    /usr/bin/getconf
Application     command                                            0.0.0.0    /usr/bin/command
```

## Parâmetros

### -All

Indica que este cmdlet obtém todos os comandos, incluindo comandos do mesmo tipo que têm o mesmo nome. Por padrão, `Get-Command` o obtém apenas os comandos que são executados quando você digita o nome do comando.

Para obter mais informações sobre o método que o PowerShell usa para selecionar o comando a ser executado quando vários comandos têm o mesmo nome, consulte [about_Command_Precedence](About/about_Command_Precedence.md).
Para obter informações sobre nomes de comando qualificados por módulo e comandos em execução que não são executados por padrão devido a um conflito de nome, consulte [about_Modules](About/about_Modules.md).

Este parâmetro foi introduzido no Windows PowerShell 3.0.

No Windows PowerShell 2,0, o `Get-Command` Obtém todos os comandos por padrão.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ArgumentList

Especifica uma matriz de argumentos. Esse cmdlet obtém informações sobre um cmdlet ou uma função quando ele é usado com os parâmetros especificados ("Arguments"). O alias para **ArgumentList** é **Args**.

Para detectar parâmetros dinâmicos que estão disponíveis somente quando determinados outros parâmetros são usados, defina o valor de **ArgumentList** para os parâmetros que disparam os parâmetros dinâmicos.

Para detectar os parâmetros dinâmicos que um provedor adiciona a um cmdlet, defina o valor do parâmetro **ArgumentList** como um caminho na unidade do provedor, como WSMan:, HKLM: ou CERT:. Quando o comando for um cmdlet do provedor do PowerShell, digite apenas um caminho em cada comando. Os cmdlets do provedor retornam apenas os parâmetros dinâmicos do primeiro caminho para o valor de **ArgumentList**. Para obter informações sobre os cmdlets do provedor, consulte [about_Providers](About/about_Providers.md).

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CommandType

Especifica os tipos de comandos que esse cmdlet obtém. Insira um ou mais tipos de comando. Use o **CommandType** ou seu alias, **Type**. Por padrão, o `Get-Command` Obtém todos os cmdlets, funções e aliases.

Os valores aceitáveis para esse parâmetro são:

- `Alias`: Obtém os aliases de todos os comandos do PowerShell. Para obter mais informações, consulte [about_Aliases](About/about_Aliases.md).
- `All`: Obtém todos os tipos de comando. Esse valor de parâmetro é o equivalente de `Get-Command *` .
- `Application`: Obtém arquivos que não são do PowerShell em caminhos listados na variável de ambiente **path** ( `$env:path` ), incluindo arquivos. txt,. exe e. dll. Para obter mais informações sobre a variável de ambiente **Path**, consulte [about_Environment_Variables](About/about_Environment_Variables.md).
- `Cmdlet`: Obtém todos os cmdlets.
- `ExternalScript`: Obtém todos os arquivos. ps1 nos caminhos listados na variável de ambiente **path** ( `$env:path` ).
- `Filter` e `Function` : Obtém todas as funções e os filtros avançados e simples do PowerShell.
- `Script`: Obtém todos os blocos de script. Para obter scripts do PowerShell (arquivos. ps1), use o `ExternalScript` valor.

Esses valores são definidos como uma enumeração baseada em sinalizador. Você pode combinar vários valores juntos para definir vários sinalizadores usando esse parâmetro. Os valores podem ser passados para o parâmetro **CommandType** como uma matriz de valores ou como uma cadeia de caracteres separada por vírgulas desses valores. O cmdlet combinará os valores usando uma operação binary ou. Passar valores como uma matriz é a opção mais simples e também permite que você use a conclusão de tabulação nos valores.

```yaml
Type: System.Management.Automation.CommandTypes
Parameter Sets: AllCommandSet
Aliases: Type
Accepted values: Alias, Function, Filter, Cmdlet, ExternalScript, Application, Script, Workflow, Configuration, All

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FullyQualifiedModule

Especifica os módulos com nomes que são especificados na forma de objetos **ModuleSpecification** , descritos na seção **comentários** do [Construtor ModuleSpecification (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).
Por exemplo, o parâmetro **FullyQualifiedModule** aceita um nome de módulo que é especificado em um dos seguintes formatos:

- `@{ModuleName = "modulename"; ModuleVersion = "version_number"}`
- `@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

**ModuleName** e **ModuleVersion** são obrigatórios, mas **Guid** é opcional.

Você não pode especificar o parâmetro **FullyQualifiedModule** no mesmo comando que um parâmetro de **módulo** . Os dois parâmetros são mutuamente exclusivos.

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ListImported

Indica que esse cmdlet obtém apenas os comandos na sessão atual.

A partir do PowerShell 3,0, por padrão, `Get-Command` o Obtém todos os comandos instalados, incluindo, entre outros, os comandos na sessão atual. No PowerShell 2,0, ele obtém apenas os comandos na sessão atual.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Módulo

Especifica uma matriz de módulos. Esse cmdlet obtém os comandos que vieram dos módulos especificados.
Insira os nomes dos módulos ou objetos de módulo.

Esse parâmetro usa valores de cadeia de caracteres, mas o valor desse parâmetro também pode ser um objeto **PSModuleInfo** , como os objetos `Get-Module` retornados pelos `Import-PSSession` cmdlets e.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSSnapin

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Name

Especifica uma matriz de nomes. Esse cmdlet obtém apenas os comandos que têm o nome especificado. Digite um nome ou padrão de nome. Caracteres curinga são permitidos.

Para obter comandos com o mesmo nome, use o parâmetro **All**. Quando dois comandos têm o mesmo nome, por padrão, `Get-Command` Obtém o comando que é executado quando você digita o nome do comando.

```yaml
Type: System.String[]
Parameter Sets: AllCommandSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Substantivo

Especifica uma matriz de substantivos de comando. Esse cmdlet obtém comandos, que incluem cmdlets, funções e aliases, que têm nomes que incluem o substantivo especificado. Insira um ou mais substantivos ou padrões de substantivo. Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: CmdletSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -ParameterName

Especifica uma matriz de nomes de parâmetro. Esse cmdlet obtém os comandos na sessão que têm os parâmetros especificados. Insira os nomes de parâmetro ou os aliases de parâmetro. Há suporte para caracteres curinga.

Os parâmetros **ParameterName** e **ParameterType** pesquisam somente comandos da sessão atual.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

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

### -ParameterType

Especifica uma matriz de nomes de parâmetro. Esse cmdlet obtém comandos na sessão que têm parâmetros do tipo especificado. Digite o nome completo ou parcial de um tipo de parâmetro. Há suporte para caracteres curinga.

Os parâmetros **ParameterName** e **ParameterType** pesquisam somente comandos da sessão atual.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.PSTypeName[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -ShowCommandInfo

Indica que este cmdlet exibe informações de comando.

Esse parâmetro foi introduzido no Windows PowerShell 5,0.

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

### -Sintaxe

Indica que este cmdlet obtém apenas os seguintes dados especificados sobre o comando:

- Aliases. Obtém o nome padrão e a sintaxe.
- Cmdlets. Obtém a sintaxe.
- Funções e filtros. Obtém a definição da função.
- Scripts e aplicativos ou arquivos. Obtém o caminho e o nome do arquivo.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TotalCount

Especifica o número de comandos a serem obtidos. Você pode usar esse parâmetro para limitar a saída de um comando.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UseAbbreviationExpansion

Indica o uso da correspondência dos caracteres no comando para localizar com caracteres maiúsculos em um comando. Por exemplo, `i-psdf` corresponderia `Import-PowerShellDataFile` como cada um dos caracteres a serem encontrados corresponde a um caractere maiúsculo no resultado. Ao usar esse tipo de correspondência, qualquer caractere curinga resultará em nenhuma correspondência.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AllCommandSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UseFuzzyMatching

Indica o uso de um algoritmo de correspondência difusa ao localizar comandos. A ordem da saída é de correspondência mais próxima à correspondência menos provável. Curingas não devem ser usados com correspondência difusa, pois ele tentará corresponder a comandos que podem conter esses caracteres curinga.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AllCommandSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Verbo

Especifica uma matriz de verbos de comando. Esse cmdlet obtém comandos, que incluem cmdlets, funções e aliases, que têm nomes que incluem o verbo especificado. Insira um ou mais verbos ou padrões de verbos. Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: CmdletSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](About/about_CommonParameters.md).

## Entradas

### System.String

Você pode canalizar nomes de comando para este cmdlet.

## Saídas

### System. Management. Automation. CommandInfo

Esse cmdlet retorna objetos derivados da classe **CommandInfo** . O tipo de objeto retornado depende do tipo de comando que `Get-Command` obtém.

### System. Management. Automation. AliasInfo

Representa aliases.

### System. Management. Automation. ApplicationInfo

Representa aplicativos e arquivos.

### System. Management. Automation. CmdletInfo

Representa cmdlets.

### System. Management. Automation. FunctionInfo

Representa funções e filtros.

## Observações

- Quando mais de um comando com o mesmo nome está disponível para a sessão, `Get-Command` o retorna o comando que é executado quando você digita o nome do comando. Para obter comandos com o mesmo nome, listados em ordem de execução, use o parâmetro **All** . Para obter mais informações, confira [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md).
- Quando um módulo é importado automaticamente, o efeito é o mesmo que usar o `Import-Module` cmdlet. O módulo pode adicionar comandos, tipos e arquivos de formatação e executar scripts na sessão.
  Para habilitar, desabilitar e configurar a importação automática de módulos, use a `$PSModuleAutoLoadingPreference` variável de preferência. Para obter mais informações, consulte [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).

## Links Relacionados

[Export-PSSession](../Microsoft.PowerShell.Utility/Export-PSSession.md)

[Get-Help](Get-Help.md)

[Get-Member](../Microsoft.PowerShell.Utility/Get-Member.md)

[Get-PSDrive](../Microsoft.PowerShell.Management/Get-PSDrive.md)

[Import-PSSession](../Microsoft.PowerShell.Utility/Import-PSSession.md)

[about_Command_Precedence](About/about_Command_Precedence.md)
