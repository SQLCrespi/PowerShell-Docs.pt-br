---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/19/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-list?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-List
ms.openlocfilehash: 7817384f077c58b46aed1dba552f89ac431891f0
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2020
ms.locfileid: "93195160"
---
# Format-List

## SINOPSE
Formata a saída como uma lista de propriedades na qual cada propriedade aparece em uma nova linha.

## SYNTAX

```
Format-List [[-Property] <Object[]>] [-GroupBy <Object>] [-View <string>] [-ShowError]
[-DisplayError] [-Force] [-Expand <string>] [-InputObject <psobject>] [<CommonParameters>]
```

## DESCRIPTION

O `Format-List` cmdlet formata a saída de um comando como uma lista de propriedades nas quais cada propriedade é exibida em uma linha separada. Você pode usar `Format-List` para formatar e exibir todas as propriedades ou de um objeto selecionado como uma lista (Format-List *).

Como mais espaço está disponível para cada item em uma lista do que em uma tabela, o PowerShell exibe mais propriedades do objeto na lista e os valores de propriedade são menos prováveis de serem truncados.

## EXEMPLOS

### Exemplo 1: Formatar serviços de computador

```powershell
Get-Service | Format-List
```

Esse comando formata informações sobre os serviços no computador como uma lista. Por padrão, os serviços são formatados como uma tabela. O `Get-Service` cmdlet obtém os objetos que representam os serviços no computador. O operador de pipeline (|) passa os resultados por meio do pipeline para `Format-List` .
Em seguida, o `Format-List` comando formata as informações de serviço em uma lista e as envia para o cmdlet de saída padrão para exibição.

### Exemplo 2: Formatar arquivos PS1XML

Esses comandos exibem informações sobre os arquivos PS1XML no diretório do PowerShell como uma lista.

```powershell
$A = Get-ChildItem $pshome\*.ps1xml
Format-List -InputObject $A
```

O primeiro comando obtém os objetos que representam os arquivos e os armazena na `$A` variável.

O segundo comando usa `Format-List` para formatar informações sobre objetos armazenados no `$A` . Esse comando usa o parâmetro **InputObject** para passar a variável para `Format-List` , que envia a saída formatada para o cmdlet de saída padrão para exibição.

### Exemplo 3: Formatar Propriedades do processo por nome

Este comando exibe o nome, a prioridade básica e a classe de prioridade de cada processo no computador.

```powershell
Get-Process | Format-List -Property name, basepriority, priorityclass
```

Ele usa o `Get-Process` cmdlet para obter um objeto que representa cada processo. O operador de pipeline (|) passa os objetos de processo por meio do pipeline para `Format-List` . `Format-List` formata os processos como uma lista das propriedades especificadas. O nome do parâmetro de *Propriedade* é opcional, portanto, você pode omiti-lo.

### Exemplo 4: Formatar todas as propriedades de um processo

Esse comando exibe todas as propriedades do processo Winlogon.

```powershell
Get-Process winlogon | Format-List -Property *
```

Ele usa o cmdlet Get-Process para obter um objeto que representa o processo do Winlogon. O operador de pipeline (|) passa o objeto de processo do Winlogon por meio do pipeline para `Format-List` . O comando usa o parâmetro *Property* para especificar as propriedades e o \* para indicar todas as propriedades.
Como o nome do parâmetro de *Propriedade* é opcional, você pode omiti-lo e digitar o comando como `Format-List *` . `Format-List` envia automaticamente os resultados para o cmdlet de saída padrão para exibição.

### Exemplo 5: erros de formato de solução de problemas

Os exemplos a seguir mostram os resultados da adição dos parâmetros **DisplayError** ou **exerror** com uma expressão.

```powershell
PC /> Get-Date | Format-List DayOfWeek,{ $_ / $null } -DisplayError

DayOfWeek    : Friday
 $_ / $null  : #ERR

PC /> Get-Date | Format-List DayOfWeek,{ $_ / $null } -ShowError

DayOfWeek    : Friday
 $_ / $null  :

Failed to evaluate expression " $_ / $null ".
+ CategoryInfo          : InvalidArgument: (12/21/2018 7:59:23 AM:PSObject) [], RuntimeException
+ FullyQualifiedErrorId : PSPropertyExpressionError
```

## PARAMETERS

### -DisplayError

Indica que esse cmdlet exibe erros na linha de comando. Esse parâmetro raramente é usado, mas pode ser usado como um auxílio de depuração quando você estiver Formatando expressões em um `Format-List` comando e as expressões não parecerem estar funcionando.

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

### -Expandir

Especifica o objeto de coleção formatado, bem como os objetos na coleção. Este parâmetro é projetado para formatar objetos que dão suporte à interface ICollection (System. Collections). O valor padrão é EnumOnly. Os valores aceitáveis para esse parâmetro são:

- EnumOnly. Exibe as propriedades dos objetos contidos na coleção.
- CoreOnly. Exibe as propriedades do objeto da coleção.
- Both: Exibe as propriedades do objeto da coleção e também as propriedades dos objetos contidos na coleção.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CoreOnly, EnumOnly, Both

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Indica que esse cmdlet exibe todas as informações de erro. Use com o parâmetro **DisplayError** ou **exerror** . Por padrão, quando um objeto de erro é gravado para os fluxos de erro ou de exibição, apenas algumas das informações de erro são exibidas.

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

### -GroupBy

Especifica a saída em grupos com base em um valor ou propriedade compartilhada. Insira uma expressão ou uma propriedade da saída.

O valor do parâmetro **GroupBy** pode ser uma nova propriedade calculada. A propriedade calculada pode ser um bloco de script ou uma tabela de hash. Os pares de chave-valor válidos são:

- Nome (ou rótulo)- `<string>`
- Expressão- `<string>` ou `<script block>`
- FormatString `<string>`

Para obter mais informações, consulte [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).

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

### -InputObject

Especifica os objetos a serem formatados. Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.

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

### -Propriedade

Especifica as propriedades do objeto que aparecem na exibição e a ordem em que aparecem.
Caracteres curinga são permitidos.

Se você omitir esse parâmetro, as propriedades a serem exibidas dependerão do objeto sendo exibido. O nome do parâmetro "Property" é opcional. Você não pode usar os parâmetros **Property** e **View** no mesmo comando.

O valor do parâmetro **Property** pode ser uma nova propriedade calculada. A propriedade calculada pode ser um bloco de script ou uma tabela de hash. Os pares de chave-valor válidos são:

- Nome (ou rótulo)- `<string>`
- Expressão- `<string>` ou `<script block>`
- FormatString `<string>`

Para obter mais informações, consulte [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Erro

Indica que o cmdlet envia erros por meio do pipeline. Esse parâmetro raramente é usado, mas pode ser usado como um auxílio de depuração quando você estiver Formatando expressões em um `Format-List` comando e as expressões não parecerem estar funcionando.

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

### -Exibição

Especifica o nome de um formato de lista ou exibição alternativa. Você não pode usar os parâmetros **Property** e **View** no mesmo comando.

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Management. Automation. PSObject

Você pode canalizar qualquer objeto para `Format-List` .

## SAÍDAS

### Microsoft. PowerShell. Commands. Internal. Format

`Format-List` Retorna os objetos de formato que representam a lista.

## OBSERVAÇÕES

Você também pode se referir a Format-List por seu alias interno, FL. Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

Os cmdlets de formato, como `Format-List` , organizam os dados a serem exibidos, mas não os exibem.
Os dados são exibidos pelos recursos de saída do PowerShell e pelos cmdlets que contêm o verbo out (os cmdlets Out), como `Out-Host` ou `Out-File` .

Se você não usar um cmdlet de formato, o PowerShell aplicará esse formato padrão a cada objeto exibido.

O parâmetro **GroupBy** pressupõe que os objetos são classificados. Use Sort-Object antes `Format-List` de usar para agrupar os objetos.

O parâmetro **View** permite especificar um formato alternativo para a tabela. Você pode usar os modos de exibição definidos nos `*.format.PS1XML` arquivos no diretório do PowerShell ou pode criar seus próprios modos de exibição em novos arquivos ps1xml e usar o cmdlet Update-FormatData para incluí-los no PowerShell.

O modo de exibição alternativo para o parâmetro de **exibição** deve usar o formato de lista, caso contrário, o comando falhará. Se a exibição alternativa for uma tabela, use `Format-Table` . Se a exibição alternativa não for uma lista ou uma tabela, use `Format-Custom` .

## LINKS RELACIONADOS

[about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[Format-Custom](Format-Custom.md)

[Format-Hex](Format-Hex.md)

[Format-Table](Format-Table.md)

[Format-Wide](Format-Wide.md)
