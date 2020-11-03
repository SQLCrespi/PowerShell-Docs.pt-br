---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Where-Object
ms.openlocfilehash: b5f4a64cceffa1f4f9884bb4de3211e129871ba7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194741"
---
# Where-Object

## SINOPSE
Seleciona objetos de uma coleção com base em seus valores de propriedade.

## SYNTAX

### Igualset (padrão)

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-EQ]
 [<CommonParameters>]
```

### ScriptBlockset

```
Where-Object [-InputObject <PSObject>] [-FilterScript] <ScriptBlock> [<CommonParameters>]
```

### Matchset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Match
 [<CommonParameters>]
```

### CaseSensitiveEqualSet

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CEQ
 [<CommonParameters>]
```

### Não Igualset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NE
 [<CommonParameters>]
```

### CaseSensitiveNotEqualSet

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNE
 [<CommonParameters>]
```

### GreaterThanSet

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -GT
 [<CommonParameters>]
```

### CaseSensitiveGreaterThanSet

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CGT
 [<CommonParameters>]
```

### LessThanSet

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -LT
 [<CommonParameters>]
```

### CaseSensitiveLessThanSet

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLT
 [<CommonParameters>]
```

### GreaterOrEqualSet

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -GE
 [<CommonParameters>]
```

### CaseSensitiveGreaterOrEqualSet

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CGE
 [<CommonParameters>]
```

### LessOrEqualSet

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -LE
 [<CommonParameters>]
```

### CaseSensitiveLessOrEqualSet

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLE
 [<CommonParameters>]
```

### Likeset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Like
 [<CommonParameters>]
```

### CaseSensitiveLikeSet

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLike
 [<CommonParameters>]
```

### Não gosto de

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotLike
 [<CommonParameters>]
```

### CaseSensitiveNotLikeSet

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotLike
 [<CommonParameters>]
```

### CaseSensitiveMatchSet

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CMatch
 [<CommonParameters>]
```

### Não Correspondenteset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotMatch
 [<CommonParameters>]
```

### CaseSensitiveNotMatchSet

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotMatch
 [<CommonParameters>]
```

### Contémset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Contains
 [<CommonParameters>]
```

### CaseSensitiveContainsSet

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CContains
 [<CommonParameters>]
```

### Não contém Oset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotContains
 [<CommonParameters>]
```

### CaseSensitiveNotContainsSet

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotContains
 [<CommonParameters>]
```

### Levo

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -In
 [<CommonParameters>]
```

### CaseSensitiveInSet

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CIn
 [<CommonParameters>]
```

### Não inserir

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotIn
 [<CommonParameters>]
```

### CaseSensitiveNotInSet

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotIn
 [<CommonParameters>]
```

### IsSet

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Is
 [<CommonParameters>]
```

### Isnotset

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -IsNot
 [<CommonParameters>]
```

### Not

```
Where-Object [-InputObject <PSObject>] [-Property] <String> -Not [<CommonParameters>]
```

## DESCRIPTION

O `Where-Object` cmdlet seleciona objetos que têm valores de propriedade específicos da coleção de objetos que são passados para ele. Por exemplo, você pode usar o `Where-Object` cmdlet para selecionar os arquivos que foram criados após uma determinada data, eventos com uma ID específica ou computadores que usam uma versão específica do Windows.

A partir do Windows PowerShell 3,0, há duas maneiras diferentes de construir um `Where-Object` comando.

- **Bloco de script** . Você pode usar um bloco de script para especificar o nome da propriedade, um operador de comparação e um valor de propriedade. `Where-Object` Retorna todos os objetos para os quais a instrução de bloco de script é verdadeira.

  Por exemplo, o comando a seguir obtém os processos na classe de prioridade normal, ou seja, processos em que o valor da propriedade **PriorityClass** é igual a normal.

  `Get-Process | Where-Object {$_.PriorityClass -eq "Normal"}`

  Todos os operadores de comparação do PowerShell são válidos no formato de bloco de script. Para obter mais informações sobre operadores de comparação, consulte [about_Comparison_Operators](./About/about_Comparison_Operators.md).

- **Instrução de comparação** . Você também pode escrever uma instrução de comparação, que é muito mais como uma linguagem natural. Instruções de comparação foram introduzidas no Windows PowerShell 3.0.

  Por exemplo, os comandos a seguir também obtêm processos que têm uma classe de prioridade normal. Estes comandos são equivalentes e podem ser usados intercambiavelmente.

  `Get-Process | Where-Object -Property PriorityClass -eq -Value "Normal"`

  `Get-Process | Where-Object PriorityClass -eq "Normal"`

  A partir do Windows PowerShell 3,0, `Where-Object` o adiciona operadores de comparação como parâmetros em um `Where-Object` comando. A menos que especificado, todos os operadores diferenciam maiúsculas de minúsculas. Antes do Windows PowerShell 3,0, os operadores de comparação no idioma do PowerShell poderiam ser usados somente em blocos de script.

Quando você fornece uma única **Propriedade** para `Where-Object` , o valor da propriedade é tratado como uma expressão booliana. Quando o valor de **Length** não for zero, a expressão será avaliada como **true** . Por exemplo: `('hi', '', 'there') | Where-Object Length`

O exemplo anterior é funcionalmente equivalente a:

- `('hi', '', 'there') | Where-Object Length -GT 0`
- `('hi', '', 'there') | Where-Object {$_.Length -gt 0}`

## EXEMPLOS

### Exemplo 1: obter serviços interrompidos

Esses comandos obtêm uma lista de todos os serviços que estão atualmente interrompidos. A `$_` variável automática representa cada objeto que é passado para o `Where-Object` cmdlet.

O primeiro comando usa o formato de bloco de script, o segundo comando usa o formato de instrução de comparação. Os comandos são equivalentes e podem ser usados intercambiavelmente.

```powershell
Get-Service | Where-Object {$_.Status -eq "Stopped"}
Get-Service | where Status -eq "Stopped"
```

### Exemplo 2: obter processos com base no conjunto de trabalho

Esses comandos listam os processos que têm um conjunto de trabalho maior que 250 megabytes (KB). A sintaxe scriptblock e Statement é equivalente e pode ser usada de maneira intercambiável.

```powershell
Get-Process | Where-Object {$_.WorkingSet -GT 250MB}
Get-Process | Where-Object WorkingSet -GT (250MB)
```

### Exemplo 3: obter processos com base no nome do processo

Esses comandos obtêm os processos que têm um valor de propriedade **ProcessName** que começa com a letra `p` . O operador **Match** permite que você use correspondências de expressão regulares.

A sintaxe scriptblock e Statement é equivalente e pode ser usada de maneira intercambiável.

```powershell
Get-Process | Where-Object {$_.ProcessName -Match "^p.*"}
Get-Process | Where-Object ProcessName -Match "^p.*"
```

### Exemplo 4: usar o formato de instrução de comparação

Este exemplo mostra como usar o novo formato de instrução de comparação do `Where-Object` cmdlet.

O primeiro comando usa o formato de instrução de comparação.
Neste comando, nenhum alias é usado e todos os parâmetros incluem o nome do parâmetro.

O segundo comando é o uso mais natural do formato de comando de comparação. O `where` alias é substituído pelo nome do `Where-Object` cmdlet e todos os nomes de parâmetro opcionais são omitidos.

```powershell
Get-Process | Where-Object -Property Handles -GE -Value 1000
Get-Process | where Handles -GE 1000
```

### Exemplo 5: obter comandos com base em Propriedades

Este exemplo mostra como gravar comandos que retornam itens que são verdadeiros ou falsos, ou que tenham qualquer valor de uma propriedade especificada. Cada exemplo mostra os formatos de bloco de script e de instrução de comparação para o comando.

```powershell
# Use Where-Object to get commands that have any value for the OutputType property of the command.
# This omits commands that do not have an OutputType property and those that have an OutputType property, but no property value.
Get-Command | where OutputType
Get-Command | where {$_.OutputType}
```

```powershell
# Use Where-Object to get objects that are containers.
# This gets objects that have the **PSIsContainer** property with a value of $True and excludes all others.
Get-ChildItem | where PSIsContainer
Get-ChildItem | where {$_.PSIsContainer}
```

```powershell
# Finally, use the Not operator (!) to get objects that are not containers.
# This gets objects that do have the **PSIsContainer** property and those that have a value of $False for the **PSIsContainer** property.
Get-ChildItem | where {!$_.PSIsContainer}
# You cannot use the Not operator (!) in the comparison statement format of the command.
Get-ChildItem | where PSIsContainer -eq $False
```

### Exemplo 6: usar várias condições

```powershell
Get-Module -ListAvailable | where {($_.Name -notlike "Microsoft*" -and $_.Name -notlike "PS*") -and $_.HelpInfoUri}
```

Este exemplo mostra como criar um `Where-Object` comando com várias condições.

Esse comando obtém módulos não essenciais que suportam o recurso de Ajuda atualizável. O comando usa o parâmetro **listAvailable** do `Get-Module` cmdlet para obter todos os módulos no computador. Um operador de pipeline ( `|` ) envia os módulos para o `Where-Object` cmdlet, que obtém os módulos cujos nomes não começam com Microsoft ou PS, e têm um valor para a propriedade **HelpInfoURI** , que informa ao PowerShell onde encontrar arquivos de ajuda atualizados para o módulo. As instruções de comparação são conectadas pelo operador lógico **and** .

O exemplo usa o formato de comando de bloco de script. Operadores lógicos, como **e** e **ou** , são válidos somente em blocos de script. Você não pode usá-los no formato de instrução de comparação de um `Where-Object` comando.

- Para obter mais informações sobre operadores lógicos do PowerShell, consulte [about_Logical_Operators](./About/about_logical_operators.md).
- Para obter mais informações sobre o recurso de ajuda atualizável, consulte [about_Updatable_Help](./About/about_Updatable_Help.md).

## PARAMETERS

### -CContains

Indica que esse cmdlet obtém objetos de uma coleção se o valor da Propriedade do objeto for uma correspondência exata para o valor especificado. Esta operação diferencia maiúsculas de minúsculas.

Por exemplo: `Get-Process | where ProcessName -CContains "svchost"`

**CContains** se refere a uma coleção de valores e é true se a coleção contém um item que é uma correspondência exata para o valor especificado. Se a entrada for um único objeto, o PowerShell a converterá em uma coleção de um objeto.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveContainsSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CEQ

Indica que esse cmdlet obtém objetos se o valor da propriedade for igual ao valor especificado.
Esta operação diferencia maiúsculas de minúsculas.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CGE

Indica que esse cmdlet obtém objetos se o valor da propriedade for maior ou igual ao valor especificado. Esta operação diferencia maiúsculas de minúsculas.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveGreaterOrEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CGT

Indica que esse cmdlet obtém objetos se o valor da propriedade for maior que o valor especificado.
Esta operação diferencia maiúsculas de minúsculas.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveGreaterThanSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CIn

Indica que esse cmdlet obtém objetos se o valor da propriedade incluir o valor especificado. Esta operação diferencia maiúsculas de minúsculas.

Por exemplo: `Get-Process | where -Value "svchost" -CIn ProcessName`

**CIN** se assemelha a **CContains** , exceto que as posições de propriedade e valor são revertidas. Por exemplo, as seguintes instruções são ambas verdadeiras.

`"abc", "def" -CContains "abc"`

`"abc" -CIn "abc", "def"`

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveInSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CLE

Indica que esse cmdlet obtém objetos se o valor da propriedade for menor ou igual ao valor especificado. Esta operação diferencia maiúsculas de minúsculas.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveLessOrEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CLike

Indica que esse cmdlet obtém objetos se o valor da propriedade corresponder a um valor que inclui caracteres curinga. Esta operação diferencia maiúsculas de minúsculas.

Por exemplo: `Get-Process | where ProcessName -CLike "*host"`

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveLikeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CLT

Indica que esse cmdlet obtém objetos se o valor da propriedade for menor que o valor especificado. Esta operação diferencia maiúsculas de minúsculas.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveLessThanSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CMatch

Indica que esse cmdlet obtém objetos se o valor da propriedade corresponder à expressão regular especificada. Esta operação diferencia maiúsculas de minúsculas. Quando a entrada é escalar, o valor correspondente é salvo em `$Matches` variável automática.

Por exemplo: `Get-Process | where ProcessName -CMatch "Shell"`

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveMatchSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CNE

Indica que esse cmdlet obtém objetos se o valor da propriedade for diferente do valor especificado.
Esta operação diferencia maiúsculas de minúsculas.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CNotContains

Indica que esse cmdlet obtém objetos se o valor da Propriedade do objeto não for uma correspondência exata para o valor especificado. Esta operação diferencia maiúsculas de minúsculas.

Por exemplo: `Get-Process | where ProcessName -CNotContains "svchost"`

**Iscontains** e **CNotContains** se referem a uma coleção de valores e são verdadeiros quando a coleção não contém nenhum item que seja uma correspondência exata para o valor especificado. Se a entrada for um único objeto, o PowerShell a converterá em uma coleção de um objeto.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotContainsSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CNotIn

Indica que esse cmdlet obtém objetos se o valor da propriedade não for uma correspondência exata para o valor especificado. Esta operação diferencia maiúsculas de minúsculas.

Por exemplo: `Get-Process | where -Value "svchost" -CNotIn -Property ProcessName`

Os operadores **NotIn** e **CNotIn** são semelhantes a **iscontains** e **CNotContains** , exceto que as posições de propriedade e valor são revertidas. Por exemplo, as seguintes instruções são verdadeiras.

`"abc", "def" -CNotContains "Abc"`

`"abc" -CNotIn "Abc", "def"`

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotInSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CNotLike

Indica que esse cmdlet obtém objetos se o valor da propriedade não corresponder a um valor que inclui caracteres curinga. Esta operação diferencia maiúsculas de minúsculas.

Por exemplo: `Get-Process | where ProcessName -CNotLike "*host"`

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotLikeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CNotMatch

Indica que esse cmdlet obtém objetos se o valor da propriedade não corresponder à expressão regular especificada. Esta operação diferencia maiúsculas de minúsculas. Quando a entrada é escalar, o valor correspondente é salvo em `$Matches` variável automática.

Por exemplo: `Get-Process | where ProcessName -CNotMatch "Shell"`

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotMatchSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Contém

Indica que esse cmdlet obtém objetos se qualquer item no valor da Propriedade do objeto for uma correspondência exata para o valor especificado.

Por exemplo: `Get-Process | where ProcessName -Contains "Svchost"`

Se o valor da propriedade contiver um único objeto, o PowerShell o converterá em uma coleção de um objeto.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ContainsSet
Aliases: IContains

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EQ

Indica que esse cmdlet obtém objetos se o valor da propriedade for igual ao valor especificado.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: EqualSet
Aliases: IEQ

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilterScript

Especifica o bloco de script usado para filtrar os objetos. Coloque o bloco de script entre chaves ( `{}` ).

O nome do parâmetro, **filterscript** , é opcional.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlockSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GE

Indica que esse cmdlet obtém objetos se o valor da propriedade for maior ou igual ao valor especificado.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GreaterOrEqualSet
Aliases: IGE

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GT

Indica que esse cmdlet obtém objetos se o valor da propriedade for maior que o valor especificado.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GreaterThanSet
Aliases: IGT

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -In

Indica que esse cmdlet obtém objetos se o valor da propriedade corresponder a qualquer um dos valores especificados.
Por exemplo:

`Get-Process | where -Property ProcessName -in -Value "Svchost", "TaskHost", "WsmProvHost"`

Se o valor do parâmetro **Value** for um único objeto, o PowerShell o converterá em uma coleção de um objeto.

Se o valor da propriedade de um objeto for uma matriz, o PowerShell usará a igualdade de referência para determinar uma correspondência. `Where-Object` Retorna o objeto somente se o valor do parâmetro **Property** e qualquer valor de **Value** forem a mesma instância de um objeto.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: InSet
Aliases: IIn

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Especifica os objetos a serem filtrados. Você também pode canalizar os objetos para `Where-Object` .

Quando você usa o parâmetro **InputObject** com `Where-Object` , em vez de direcionar os resultados de comando para `Where-Object` , o valor **InputObject** é tratado como um único objeto. Isso é verdadeiro mesmo se o valor for uma coleção que é o resultado de um comando, como `-InputObject (Get-Process)` . Como **InputObject** não pode retornar propriedades individuais de uma matriz ou coleção de objetos, recomendamos que, se você usar `Where-Object` o para filtrar uma coleção de objetos para os objetos que têm valores específicos em propriedades definidas, use `Where-Object` no pipeline, conforme mostrado nos exemplos neste tópico.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -É

Indica que esse cmdlet obtém objetos se o valor da propriedade for uma instância do tipo .NET especificado. Inclua o nome do tipo entre colchetes.

Por exemplo, `Get-Process | where StartTime -Is [DateTime]`

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IsSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsNot

Indica que esse cmdlet obtém objetos se o valor da propriedade não for uma instância do tipo .NET especificado.

Por exemplo, `Get-Process | where StartTime -IsNot [DateTime]`

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IsNotSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LE

Indica que esse cmdlet obtém objetos se o valor da propriedade for menor ou igual ao valor especificado.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LessOrEqualSet
Aliases: ILE

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Like

Indica que esse cmdlet obtém objetos se o valor da propriedade corresponder a um valor que inclui caracteres curinga.

Por exemplo: `Get-Process | where ProcessName -Like "*host"`

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LikeSet
Aliases: ILike

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LT

Indica que esse cmdlet obtém objetos se o valor da propriedade for menor que o valor especificado.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LessThanSet
Aliases: ILT

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Correspondência

Indica que esse cmdlet obtém objetos se o valor da propriedade corresponder à expressão regular especificada. Quando a entrada é escalar, o valor correspondente é salvo em `$Matches` variável automática.

Por exemplo: `Get-Process | where ProcessName -Match "shell"`

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: MatchSet
Aliases: IMatch

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NE

Indica que esse cmdlet obtém objetos se o valor da propriedade for diferente do valor especificado.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotEqualSet
Aliases: INE

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Não

Indica que esse cmdlet obtém objetos se a propriedade não existir ou se tiver um valor de NULL ou false.

Por exemplo: `Get-Service | where -Not "DependentServices"`

Esse parâmetro foi introduzido no Windows PowerShell 6,1.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Not
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Não contém

Indica que esse cmdlet obtém objetos se nenhum dos itens no valor da propriedade for uma correspondência exata para o valor especificado.

Por exemplo: `Get-Process | where ProcessName -NotContains "Svchost"`

Não **contém** se refere a uma coleção de valores e será true se a coleção não contiver nenhum item que seja uma correspondência exata para o valor especificado. Se a entrada for um único objeto, o PowerShell a converterá em uma coleção de um objeto.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotContainsSet
Aliases: INotContains

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NotIn

Indica que esse cmdlet obtém objetos se o valor da propriedade não for uma correspondência exata para qualquer um dos valores especificados.

Por exemplo: `Get-Process | where -Value "svchost" -NotIn -Property ProcessName`

Se o valor de **Value** for um objeto único, o PowerShell o converterá em uma coleção de um objeto.

Se o valor da propriedade de um objeto for uma matriz, o PowerShell usará a igualdade de referência para determinar uma correspondência. `Where-Object` Retorna o objeto somente se o valor da **Propriedade** e qualquer valor de **valor** não forem a mesma instância de um objeto.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotInSet
Aliases: INotIn

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Não gosto

Indica que esse cmdlet obtém objetos se o valor da propriedade não corresponder a um valor que inclui caracteres curinga.

Por exemplo: `Get-Process | where ProcessName -NotLike "*host"`

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotLikeSet
Aliases: INotLike

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Não correspondente

Indica que esse cmdlet obtém objetos quando o valor da propriedade não corresponde à expressão regular especificada. Quando a entrada é escalar, o valor correspondente é salvo em `$Matches` variável automática.

Por exemplo: `Get-Process | where ProcessName -NotMatch "PowerShell"`

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotMatchSet
Aliases: INotMatch

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Propriedade

Especifica o nome de uma propriedade de objeto. O nome do parâmetro, **Propriedade** , é opcional.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: EqualSet, LessOrEqualSet, CaseSensitiveEqualSet, NotEqualSet, CaseSensitiveNotEqualSet, GreaterThanSet, CaseSensitiveGreaterThanSet, LessThanSet, CaseSensitiveLessThanSet, GreaterOrEqualSet, CaseSensitiveGreaterOrEqualSet, CaseSensitiveLessOrEqualSet, LikeSet, CaseSensitiveLikeSet, NotLikeSet, CaseSensitiveNotLikeSet, MatchSet, CaseSensitiveMatchSet, NotMatchSet, CaseSensitiveNotMatchSet, ContainsSet, CaseSensitiveContainsSet, NotContainsSet, CaseSensitiveNotContainsSet, InSet, CaseSensitiveInSet, NotInSet, CaseSensitiveNotInSet, IsSet, IsNotSet, Not
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value

Especifica um valor de propriedade. O nome do parâmetro, **Value** , é opcional. Esse parâmetro aceita caracteres curinga quando usados com os seguintes parâmetros de comparação:

- **CLike**
- **CNotLike**
- **Similar**
- **NotLike**

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Object
Parameter Sets: EqualSet, LessOrEqualSet, CaseSensitiveEqualSet, NotEqualSet, CaseSensitiveNotEqualSet, GreaterThanSet, CaseSensitiveGreaterThanSet, LessThanSet, CaseSensitiveLessThanSet, GreaterOrEqualSet, CaseSensitiveGreaterOrEqualSet, CaseSensitiveLessOrEqualSet, LikeSet, CaseSensitiveLikeSet, NotLikeSet, CaseSensitiveNotLikeSet, MatchSet, CaseSensitiveMatchSet, NotMatchSet, CaseSensitiveNotMatchSet, ContainsSet, CaseSensitiveContainsSet, NotContainsSet, CaseSensitiveNotContainsSet, InSet, CaseSensitiveInSet, NotInSet, CaseSensitiveNotInSet, IsSet, IsNotSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Management. Automation. PSObject

É possível canalizar os objetos para esse cmdlet.

## SAÍDAS

### Objeto

Esse cmdlet retorna os itens selecionados do conjunto de objetos de entrada.

## OBSERVAÇÕES

A partir do Windows PowerShell 4,0, `Where` e os `ForEach` métodos foram adicionados para uso com coleções.

Você pode ler mais sobre esses novos métodos aqui [about_arrays](./About/about_Arrays.md)

## LINKS RELACIONADOS

[Compare-Object](../Microsoft.PowerShell.Utility/Compare-Object.md)

[ForEach-Object](ForEach-Object.md)

[Group-Object](../Microsoft.PowerShell.Utility/Group-Object.md)

[Measure-Object](../Microsoft.PowerShell.Utility/Measure-Object.md)

[New-Object](../Microsoft.PowerShell.Utility/New-Object.md)

[Select-Object](../Microsoft.PowerShell.Utility/Select-Object.md)

[Sort-Object](../Microsoft.PowerShell.Utility/Sort-Object.md)

[Tee-Object](../Microsoft.PowerShell.Utility/Tee-Object.md)

