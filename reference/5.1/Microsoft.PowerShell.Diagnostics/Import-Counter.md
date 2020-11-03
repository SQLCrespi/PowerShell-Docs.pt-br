---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/import-counter?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Counter
ms.openlocfilehash: 837f6b4b3b2869c6f74b3b02904dd43b73f6bcd5
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193484"
---
# Import-Counter

## SINOPSE
Importa os arquivos de log do contador de desempenho e cria os objetos que representam cada exemplo de contador no log.

## SYNTAX

### Getcounterset (padrão)

```
Import-Counter [-Path] <String[]> [-StartTime <DateTime>] [-EndTime <DateTime>] [-Counter <String[]>]
 [-MaxSamples <Int64>] [<CommonParameters>]
```

### ListSetSet

```
Import-Counter [-Path] <String[]> -ListSet <String[]> [<CommonParameters>]
```

### Resumo

```
Import-Counter [-Path] <String[]> [-Summary] [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Import-Counter** importa dados do contador de desempenho dos arquivos de log do contador de desempenho e cria objetos para cada exemplo de contador no arquivo.
Os objetos **PerformanceCounterSampleSet** que ele cria são idênticos aos objetos que **Get-Counter** retorna quando coleta dados do contador de desempenho.

Você pode importar dados de arquivos de log de desempenho com formato de valores separados por vírgulas (.csv), valores separados por tabulações (.tsv) e log de desempenho binário (.blg).
Se você estiver usando arquivos. blg, poderá importar até 32 arquivos em cada comando.
Você pode usar os parâmetros de **Import-Counter** para filtrar os dados importados.

Junto com os cmdlets Get-Counter e Export-Counter, esse recurso permite coletar, exportar, importar, combinar, filtrar, manipular e reexportar dados do contador de desempenho no Windows PowerShell.

## EXEMPLOS

### Exemplo 1: importar todos os dados do contador de um arquivo

```powershell
$Data = Import-Counter -Path ProcessorData.csv
```

Esse comando importa todos os dados do contador do arquivo de ProcessorData.csv para a variável $Data.

### Exemplo 2: importar dados de contador específicos de um arquivo

```
PS C:\> $I = Import-Counter -Path "ProcessorData.blg" -Counter "\\SERVER01\Processor(_Total)\Interrupts/sec"
```

Esse comando importa apenas os dados do contador **"Processor (_total) \ Interrupções/s"** do arquivo ProcessorData. blg para a variável $I.

### Exemplo 3: selecionar dados de um contador de desempenho e, em seguida, exportá-los para um arquivo

```
The first command uses **Import-Counter** to import all of the performance counter data from the ProcessorData.blg files. The command saves the data in the $Data variable.
PS C:\> $Data = Import-Counter .\ProcessorData.blg

The second command displays the counter paths in the $Data variable. To get the display shown in the command output, the example uses the Format-Table cmdlet to format as a table the counter paths of the first counter in the $Data variable.
PS C:\> $Data[0].CounterSamples | Format-Table -Property Path

Path
----
\\SERVER01\Processor(_Total)\DPC Rate
\\SERVER01\Processor(1)\DPC Rate
\\SERVER01\Processor(0)\DPC Rate
\\SERVER01\Processor(_Total)\% Idle Time
\\SERVER01\Processor(1)\% Idle Time
\\SERVER01\Processor(0)\% Idle Time
\\SERVER01\Processor(_Total)\% C3 Time
\\SERVER01\Processor(1)\% C3 Time

The third command gets the counter paths that end in "Interrupts/sec" and saves the paths in the $IntCtrs variable. It uses the Where-Object cmdlet to filter the counter paths and the ForEach-Object cmdlet to get only the value of the **Path** property of each selected path object.
PS C:\> $IntCtrs = $Data[0].Countersamples | Where-Object {$_.Path -like "*Interrupts/sec"} | ForEach-Object {$_.Path}

The fourth command displays the selected counter paths in the $IntCtrs variable.
PS C:\> $IntCtrs

\\SERVER01\Processor(_Total)\Interrupts/sec
\\SERVER01\Processor(1)\Interrupts/sec
\\SERVER01\Processor(0)\Interrupts/sec

The fifth command uses the **Import-Counter** cmdlet to import the data. It uses the $IntCtrs variable as the value of the *Counter* parameter to import only data for the counter paths in $IntCtrs.
PS C:\> $I = Import-Counter -Path .\ProcessorData.blg -Counter $intCtrs

The sixth command uses the Export-Counter cmdlet to export the data to the Interrupts.csv file.
PS C:\> $I | Export-Counter -Path .\Interrupts.csv -Format CSV
```

Este exemplo mostra como selecionar dados de um arquivo de log do contador de desempenho (.blg) e, em seguida, exportar os dados selecionados para um arquivo .csv.
Os primeiros quatro comandos obtêm os caminhos do contador do arquivo e os salvam na variável chamada $Data.
Os dois últimos comandos importam dados selecionados e, em seguida, exportam somente os dados selecionados.

### Exemplo 4: exibir todos os caminhos de contador em um grupo de conjuntos de contadores importados

```
The first command uses the *ListSet* parameter of the **Import-Counter** cmdlet to get all of the counter sets that are represented in a counter data file.
PS C:\> Import-Counter -Path ProcessorData.csv -ListSet *

CounterSetName     : Processor
MachineName        : \\SERVER01
CounterSetType     : MultiInstance
Description        :
Paths              : {\\SERVER01\Processor(*)\DPC Rate, \\SERVER01\Processor(*)\% Idle Time, \\SERVER01
\Processor(*)\% C3 Time, \\SERVER01\Processor(*)\% Interrupt Time...}
PathsWithInstances : {\\SERVER01\Processor(_Total)\DPC Rate, \\SERVER01\Processor(1)\DPC Rate, \\SERVER01
\Processor(0)\DPC Rate, \\SERVER01\Processor(_Total)\% Idle Time...}
Counter            : {\\SERVER01\Processor(*)\DPC Rate, \\SERVER01\Processor(*)\% Idle Time, \\SERVER01
\Processor(*)\% C3 Time, \\SERVER01\Processor(*)\% Interrupt Time...}

The second command gets all of the counter paths from the list set.
PS C:\> Import-Counter -Path ProcessorData.csv -ListSet * | ForEach-Object {$_.Paths}

\\SERVER01\Processor(*)\DPC Rate
\\SERVER01\Processor(*)\% Idle Time
\\SERVER01\Processor(*)\% C3 Time
\\SERVER01\Processor(*)\% Interrupt Time
\\SERVER01\Processor(*)\% C2 Time
\\SERVER01\Processor(*)\% User Time
\\SERVER01\Processor(*)\% C1 Time
\\SERVER01\Processor(*)\% Processor Time
\\SERVER01\Processor(*)\C1 Transitions/sec
\\SERVER01\Processor(*)\% DPC Time
\\SERVER01\Processor(*)\C2 Transitions/sec
\\SERVER01\Processor(*)\% Privileged Time
\\SERVER01\Processor(*)\C3 Transitions/sec
\\SERVER01\Processor(*)\DPCs Queued/sec
\\SERVER01\Processor(*)\Interrupts/sec
```

Este exemplo mostra como exibir todos os caminhos de contador em um grupo de conjuntos de contadores importados.

### Exemplo 5: importar dados do contador de um intervalo de carimbos de data/hora

```
The first command lists in a table the time stamps of all of the data in the ProcessorData.blg file.
PS C:\> Import-Counter -Path ".\disk.blg" | Format-Table -Property Timestamp

The second command saves particular time stamps in the $Start and $End variables. The strings are cast to **DateTime** objects.
PS C:\> $Start = [datetime]"7/9/2008 3:47:00 PM"; $End = [datetime]"7/9/2008 3:47:59 PM"

The third command uses the **Import-Counter** cmdlet to get only counter data that has a time stamp between the start and end times (inclusive). The command uses the *StartTime* and *EndTime* parameters of **Import-Counter** to specify the range.
PS C:\> Import-Counter -Path Disk.blg -StartTime $start -EndTime $end
```

Este exemplo importa somente os dados do contador que tem um carimbo de data/hora dentro dos intervalos inicial e final especificados no comando.

### Exemplo 6: importar um número especificado de amostras mais antigas de um arquivo de log do contador de desempenho

```
The first command uses the **Import-Counter** cmdlet to import the first (oldest) five samples from the Disk.blg file. The command uses the *MaxSamples* parameter to limit the import to five counter samples.
PS C:\> Import-Counter -Path "Disk.blg" -MaxSamples 5

The second command uses array notation and the Windows PowerShell range operator (..) to get the last five counter samples from the file. These are the five newest samples.
PS C:\> (Import-Counter -Path Disk.blg)[-1 .. -5]
```

Este exemplo mostra como importar as cinco amostras mais antigas e mais recentes de um arquivo de log do contador de desempenho.

### Exemplo 7: obter um resumo dos dados do contador de um arquivo

```
PS C:\> Import-Counter "D:\Samples\Memory.blg" -Summary

OldestRecord            NewestRecord            SampleCount
------------            ------------            -----------
7/10/2008 2:59:18 PM    7/10/2008 3:00:27 PM    1000
```

Este comando usa o parâmetro *Summary* do cmdlet **Import-Counter** para obter um resumo dos dados do contador no arquivo Memory.blg.

### Exemplo 8: atualizar um arquivo de log do contador de desempenho

```
The first command uses the *ListSet* parameter of **Import-Counter** to get the counters in OldData.blg, an existing counter log file. The command uses a pipeline operator (|) to send the data to a ForEach-Object command that gets only the values of the **PathsWithInstances** property of each object
PS C:\> $Counters = Import-Counter OldData.blg -ListSet * | ForEach-Object {$_.PathsWithInstances}

The second command gets updated data for the counters in the $Counters variable. It uses the Get-Counter cmdlet to get a current sample, and then export the results to the NewData.blg file.
PS C:\> Get-Counter -Counter $Counters -MaxSamples 20 | Export-Counter C:\Logs\NewData.blg
```

Este exemplo atualiza um arquivo de log de contador de desempenho.

### Exemplo 9: importar dados de log de desempenho de vários arquivos e, em seguida, salvá-los

```
PS C:\> $Counters = "D:\test\pdata.blg", "D:\samples\netlog.blg" | Import-Counter
```

Esse comando importa dados de log de desempenho de dois logs e salva os dados na variável $Counters.
O comando usa um operador de pipeline para enviar os caminhos do log de desempenho para Import-Counter, que importa os dados dos caminhos especificados.

Observe que cada caminho é colocado entre aspas e que os caminhos são separados uns dos outros por uma vírgula.

## PARAMETERS

### -Contador

Especifica, como uma matriz de cadeia de caracteres, os contadores de desempenho.
Por padrão, **Import-Counter** importa todos os dados de todos os contadores nos arquivos de entrada.
Insira um ou mais caminhos de contador.
Caracteres curinga são permitidos na parte de Instância do caminho.

Cada caminho de contador tem o seguinte formato.
O valor ComputerName é necessário no caminho.
Por exemplo:

- `\\<ComputerName>\<CounterSet>(<Instance>)\<CounterName>`

Por exemplo:

- `\\Server01\Processor(2)\% User Time`
- `\\Server01\Processor(*)\% Processor Time`

```yaml
Type: System.String[]
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: All counter
Accept pipeline input: False
Accept wildcard characters: True
```

### -EndTime

Especifica uma data e hora de término que este cmdlet importa dados de contador entre os carimbos de hora de *início* e este parâmetro.
Insira um objeto **DateTime** , como um criado pelo cmdlet Get-Date.
Por padrão, **Import-Counter** importa todos os dados do contador nos arquivos especificados pelo parâmetro *Path* .

```yaml
Type: System.DateTime
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: No end time
Accept pipeline input: False
Accept wildcard characters: False
```

### -ListSet

Especifica os conjuntos de contadores de desempenho que são representados nos arquivos exportados.
Comandos com esse parâmetro não importam dados.

Insira um ou mais nomes de pilha de locais.
Caracteres curinga são permitidos.
Para obter todos os conjuntos de contadores no arquivo, digite `Import-Counter -ListSet *` .

```yaml
Type: System.String[]
Parameter Sets: ListSetSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -MaxSamples

Especifica o número máximo de amostras a serem importadas por cada contador.
Por padrão, o **Get-Counter** importa todos os dados nos arquivos especificados pelo parâmetro *Path* .

```yaml
Type: System.Int64
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: No maximum
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Especifica os caminhos de arquivo dos arquivos a serem importados.
Este parâmetro é necessário.

Insira o caminho e o nome de arquivo de um arquivo,. csv,,. tsv ou. blg que você exportou usando o cmdlet **Export-Counter** .
Você pode especificar somente um arquivo .csv ou .tsv, mas pode especificar vários arquivos .blg (até 32) em cada comando.
Você também pode canalizar cadeias de caracteres de caminho de arquivo (entre aspas) para **Import-Counter** .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -StartTime

Especifica a data e a hora de início em que esse cmdlet obtém dados do contador.
Insira um objeto **DateTime** , como um criado pelo cmdlet **Get-Date** .
Por padrão, **Import-Counter** importa todos os dados do contador nos arquivos especificados pelo parâmetro *Path* .

```yaml
Type: System.DateTime
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: No start time
Accept pipeline input: False
Accept wildcard characters: False
```

### -Resumo

Indica que esse cmdlet obtém um resumo dos dados importados, em vez de obter amostras de dados de contador individuais.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SummarySet
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

Você pode canalizar caminhos de log do contador de desempenho para este cmdlet.

## SAÍDAS

### Microsoft. PowerShell. Commands. getcounterer. PerformanceCounterSampleSet, Microsoft. PowerShell. Commands. getcounterer. contador, Microsoft. PowerShell. Commands. getcounterer. prefileinfo

Esse cmdlet retorna um **Microsoft. PowerShell. Commands. Getcounterer. PerformanceCounterSampleSet** .
Se você usar o parâmetro *ListSet* , esse cmdlet retornará um objeto **Microsoft. PowerShell. Commands. getcounterer. contadorset** .
Se você usar o parâmetro *Summary* , esse cmdlet retornará um objeto **Microsoft. PowerShell. Commands. getcounterer. Counter FileInfo** .

## OBSERVAÇÕES

* Este cmdlet não tem um parâmetro *ComputerName* . No entanto, se o computador estiver configurado para comunicação remota do Windows PowerShell, você poderá usar o cmdlet Invoke-Command para executar um comando **Import-Counter** em um computador remoto.

## LINKS RELACIONADOS

[Export-Counter](Export-Counter.md)

[Get-Counter](Get-Counter.md)
