---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/24/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/measure-command?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Measure-Command
ms.openlocfilehash: 0c2346dc7177e091c0921cd4775422938305e2be
ms.sourcegitcommit: 165d10405d9db3a68c417a239d3181378fd02b9b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "99595962"
---
# Measure-Command

## SINOPSE
Mede o tempo de execução de cmdlets e blocos de script.

## SYNTAX

```
Measure-Command [-InputObject <PSObject>] [-Expression] <ScriptBlock> [<CommonParameters>]
```

## DESCRIPTION

O `Measure-Command` cmdlet executa um bloco de script ou cmdlet internamente, vezes a execução da operação e retorna o tempo de execução.

> [!NOTE]
> Blocos de script executados por `Measure-Command` execução no escopo atual, não um escopo filho.

## EXEMPLOS

### Exemplo 1: medir um comando

Este exemplo mede o tempo necessário para executar um `Get-EventLog` comando que obtém os eventos no log de eventos do Windows PowerShell.

```powershell
Measure-Command { Get-EventLog "windows powershell" }
```

### Exemplo 2: comparar duas saídas de Measure-Command

O primeiro comando mede o tempo necessário para processar um comando recursivo `Get-ChildItem` que usa o parâmetro **Path** para obter apenas os `.txt` arquivos no `C:\Windows` diretório e seus subdiretórios.

O segundo comando mede o tempo necessário para processar um comando recursivo `Get-ChildItem` que usa o parâmetro ' específico do provedor '.

Esses comandos mostram o valor do uso de um filtro específico do provedor em comandos do PowerShell.

```powershell
Measure-Command { Get-ChildItem -Path C:\Windows\*.txt -Recurse }
```

```Output
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 8
Milliseconds      : 618
Ticks             : 86182763
TotalDays         : 9.9748568287037E-05
TotalHours        : 0.00239396563888889
TotalMinutes      : 0.143637938333333
TotalSeconds      : 8.6182763
TotalMilliseconds : 8618.2763
```

```powershell
Measure-Command {Get-ChildItem C:\Windows -Filter "*.txt" -Recurse}
```

```Output
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 1
Milliseconds      : 140
Ticks             : 11409189
TotalDays         : 1.32050798611111E-05
TotalHours        : 0.000316921916666667
TotalMinutes      : 0.019015315
TotalSeconds      : 1.1409189
TotalMilliseconds : 1140.9189
```

### Exemplo 3: entrada de encanamento para Measure-Command

Os objetos que são canalizados para `Measure-Command` estão disponíveis para o bloco de script que é passado para o parâmetro **expression** . O bloco de script é executado uma vez para cada objeto no pipeline.

```powershell
# Perform a simple operation to demonstrate the InputObject parameter
# Note that no output is displayed.
10, 20, 50 | Measure-Command -Expression { for ($i=0; $i -lt $_; $i++) {$i} }
```

```Output
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 0
Milliseconds      : 12
Ticks             : 122672
TotalDays         : 1.41981481481481E-07
TotalHours        : 3.40755555555556E-06
TotalMinutes      : 0.000204453333333333
TotalSeconds      : 0.0122672
TotalMilliseconds : 12.2672
```

### Exemplo 4: exibindo a saída do comando medido

Para exibir a saída da expressão no `Measure-Command` , você pode usar um pipe para `Out-Default` .

```powershell
# Perform the same operation as above adding Out-Default to every execution.
# This will show that the ScriptBlock is in fact executing for every item.
10, 20, 50 | Measure-Command -Expression {for ($i=0; $i -lt $_; $i++) {$i}; "$($_)" | Out-Default }
```

```Output
10
20
50


Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 0
Milliseconds      : 11
Ticks             : 113745
TotalDays         : 1.31649305555556E-07
TotalHours        : 3.15958333333333E-06
TotalMinutes      : 0.000189575
TotalSeconds      : 0.0113745
TotalMilliseconds : 11.3745
```

### Exemplo 5: medindo a execução em um escopo filho

`Measure-Command` executa o bloco de script no escopo atual, de modo que o bloco de script pode modificar valores no escopo atual. Para evitar alterações no escopo atual, você deve encapsular o bloco de script entre chaves ( `{}` ) e usar o operador de invocação ( `&` ) para executar o bloco em um escopo filho.

```powershell
$foo = 'Value 1'
$null = Measure-Command { $foo = 'Value 2' }
$foo
$null = Measure-Command { & { $foo = 'Value 3' } }
$foo
```

```Output
Value 2
Value 2
```

Para obter mais informações sobre o operador de invocação, consulte [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md#call-operator-).

## PARAMETERS

### -Expressão

Especifica a expressão que está sendo cronometrada. Coloque a expressão entre chaves ( `{}` ).

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Objetos vinculados ao parâmetro **InputObject** são entradas opcionais para o bloco de script passado para o parâmetro **expression** . Dentro do bloco de script, `$_` pode ser usado para referenciar o objeto atual no pipeline.

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Management. Automation. PSObject

É possível canalizar um objeto para `Measure-Command` .

## SAÍDAS

### System.TimeSpan

`Measure-Command` Retorna um objeto de período de tempo que representa o resultado.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)

[Trace-Command](Trace-Command.md)

