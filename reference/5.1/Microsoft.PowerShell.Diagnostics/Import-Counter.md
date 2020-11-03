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
# <span data-ttu-id="9902e-103">Import-Counter</span><span class="sxs-lookup"><span data-stu-id="9902e-103">Import-Counter</span></span>

## <span data-ttu-id="9902e-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="9902e-104">SYNOPSIS</span></span>
<span data-ttu-id="9902e-105">Importa os arquivos de log do contador de desempenho e cria os objetos que representam cada exemplo de contador no log.</span><span class="sxs-lookup"><span data-stu-id="9902e-105">Imports performance counter log files and creates the objects that represent each counter sample in the log.</span></span>

## <span data-ttu-id="9902e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9902e-106">SYNTAX</span></span>

### <span data-ttu-id="9902e-107">Getcounterset (padrão)</span><span class="sxs-lookup"><span data-stu-id="9902e-107">GetCounterSet (Default)</span></span>

```
Import-Counter [-Path] <String[]> [-StartTime <DateTime>] [-EndTime <DateTime>] [-Counter <String[]>]
 [-MaxSamples <Int64>] [<CommonParameters>]
```

### <span data-ttu-id="9902e-108">ListSetSet</span><span class="sxs-lookup"><span data-stu-id="9902e-108">ListSetSet</span></span>

```
Import-Counter [-Path] <String[]> -ListSet <String[]> [<CommonParameters>]
```

### <span data-ttu-id="9902e-109">Resumo</span><span class="sxs-lookup"><span data-stu-id="9902e-109">SummarySet</span></span>

```
Import-Counter [-Path] <String[]> [-Summary] [<CommonParameters>]
```

## <span data-ttu-id="9902e-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9902e-110">DESCRIPTION</span></span>

<span data-ttu-id="9902e-111">O cmdlet **Import-Counter** importa dados do contador de desempenho dos arquivos de log do contador de desempenho e cria objetos para cada exemplo de contador no arquivo.</span><span class="sxs-lookup"><span data-stu-id="9902e-111">The **Import-Counter** cmdlet imports performance counter data from performance counter log files and creates objects for each counter sample in the file.</span></span>
<span data-ttu-id="9902e-112">Os objetos **PerformanceCounterSampleSet** que ele cria são idênticos aos objetos que **Get-Counter** retorna quando coleta dados do contador de desempenho.</span><span class="sxs-lookup"><span data-stu-id="9902e-112">The **PerformanceCounterSampleSet** objects that it creates are identical to the objects that **Get-Counter** returns when it collects performance counter data.</span></span>

<span data-ttu-id="9902e-113">Você pode importar dados de arquivos de log de desempenho com formato de valores separados por vírgulas (.csv), valores separados por tabulações (.tsv) e log de desempenho binário (.blg).</span><span class="sxs-lookup"><span data-stu-id="9902e-113">You can import data from comma-separated value (.csv), tab-separated value ( .tsv), and binary performance log (.blg) performance log files.</span></span>
<span data-ttu-id="9902e-114">Se você estiver usando arquivos. blg, poderá importar até 32 arquivos em cada comando.</span><span class="sxs-lookup"><span data-stu-id="9902e-114">If you are using .blg files, you can import up to 32 files in each command.</span></span>
<span data-ttu-id="9902e-115">Você pode usar os parâmetros de **Import-Counter** para filtrar os dados importados.</span><span class="sxs-lookup"><span data-stu-id="9902e-115">You can use the parameters of **Import-Counter** to filter the data that you import.</span></span>

<span data-ttu-id="9902e-116">Junto com os cmdlets Get-Counter e Export-Counter, esse recurso permite coletar, exportar, importar, combinar, filtrar, manipular e reexportar dados do contador de desempenho no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9902e-116">Along with the Get-Counter and Export-Counter cmdlets, this feature lets you collect, export, import, combine, filter, manipulate, and re-export performance counter data within Windows PowerShell.</span></span>

## <span data-ttu-id="9902e-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="9902e-117">EXAMPLES</span></span>

### <span data-ttu-id="9902e-118">Exemplo 1: importar todos os dados do contador de um arquivo</span><span class="sxs-lookup"><span data-stu-id="9902e-118">Example 1: Import all counter data from a file</span></span>

```powershell
$Data = Import-Counter -Path ProcessorData.csv
```

<span data-ttu-id="9902e-119">Esse comando importa todos os dados do contador do arquivo de ProcessorData.csv para a variável $Data.</span><span class="sxs-lookup"><span data-stu-id="9902e-119">This command imports all counter data from the ProcessorData.csv file into the $Data variable.</span></span>

### <span data-ttu-id="9902e-120">Exemplo 2: importar dados de contador específicos de um arquivo</span><span class="sxs-lookup"><span data-stu-id="9902e-120">Example 2: Import specific counter data from a file</span></span>

```
PS C:\> $I = Import-Counter -Path "ProcessorData.blg" -Counter "\\SERVER01\Processor(_Total)\Interrupts/sec"
```

<span data-ttu-id="9902e-121">Esse comando importa apenas os dados do contador **"Processor (_total) \ Interrupções/s"** do arquivo ProcessorData. blg para a variável $I.</span><span class="sxs-lookup"><span data-stu-id="9902e-121">This command imports only the **"Processor(_total)\Interrupts/sec"** counter data from the ProcessorData.blg file into the $I variable.</span></span>

### <span data-ttu-id="9902e-122">Exemplo 3: selecionar dados de um contador de desempenho e, em seguida, exportá-los para um arquivo</span><span class="sxs-lookup"><span data-stu-id="9902e-122">Example 3: Select data from a performance counter then export it to a file</span></span>

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

<span data-ttu-id="9902e-123">Este exemplo mostra como selecionar dados de um arquivo de log do contador de desempenho (.blg) e, em seguida, exportar os dados selecionados para um arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="9902e-123">This example shows how to select data from a performance counter log file (.blg) and then export the selected data to a .csv file.</span></span>
<span data-ttu-id="9902e-124">Os primeiros quatro comandos obtêm os caminhos do contador do arquivo e os salvam na variável chamada $Data.</span><span class="sxs-lookup"><span data-stu-id="9902e-124">The first four commands get the counter paths from the file and save them in the variable named $Data.</span></span>
<span data-ttu-id="9902e-125">Os dois últimos comandos importam dados selecionados e, em seguida, exportam somente os dados selecionados.</span><span class="sxs-lookup"><span data-stu-id="9902e-125">The last two commands import selected data and then export only the selected data.</span></span>

### <span data-ttu-id="9902e-126">Exemplo 4: exibir todos os caminhos de contador em um grupo de conjuntos de contadores importados</span><span class="sxs-lookup"><span data-stu-id="9902e-126">Example 4: Display all counter paths in a group of imported counter sets</span></span>

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

<span data-ttu-id="9902e-127">Este exemplo mostra como exibir todos os caminhos de contador em um grupo de conjuntos de contadores importados.</span><span class="sxs-lookup"><span data-stu-id="9902e-127">This example shows how to display all the counter paths in a group of imported counter sets.</span></span>

### <span data-ttu-id="9902e-128">Exemplo 5: importar dados do contador de um intervalo de carimbos de data/hora</span><span class="sxs-lookup"><span data-stu-id="9902e-128">Example 5: Import counter data from a range of time stamps</span></span>

```
The first command lists in a table the time stamps of all of the data in the ProcessorData.blg file.
PS C:\> Import-Counter -Path ".\disk.blg" | Format-Table -Property Timestamp

The second command saves particular time stamps in the $Start and $End variables. The strings are cast to **DateTime** objects.
PS C:\> $Start = [datetime]"7/9/2008 3:47:00 PM"; $End = [datetime]"7/9/2008 3:47:59 PM"

The third command uses the **Import-Counter** cmdlet to get only counter data that has a time stamp between the start and end times (inclusive). The command uses the *StartTime* and *EndTime* parameters of **Import-Counter** to specify the range.
PS C:\> Import-Counter -Path Disk.blg -StartTime $start -EndTime $end
```

<span data-ttu-id="9902e-129">Este exemplo importa somente os dados do contador que tem um carimbo de data/hora dentro dos intervalos inicial e final especificados no comando.</span><span class="sxs-lookup"><span data-stu-id="9902e-129">This example imports only the counter data that has a time stamp between the starting an ending ranges specified in the command.</span></span>

### <span data-ttu-id="9902e-130">Exemplo 6: importar um número especificado de amostras mais antigas de um arquivo de log do contador de desempenho</span><span class="sxs-lookup"><span data-stu-id="9902e-130">Example 6: Import a specified number of the oldest samples from a performance counter log file</span></span>

```
The first command uses the **Import-Counter** cmdlet to import the first (oldest) five samples from the Disk.blg file. The command uses the *MaxSamples* parameter to limit the import to five counter samples.
PS C:\> Import-Counter -Path "Disk.blg" -MaxSamples 5

The second command uses array notation and the Windows PowerShell range operator (..) to get the last five counter samples from the file. These are the five newest samples.
PS C:\> (Import-Counter -Path Disk.blg)[-1 .. -5]
```

<span data-ttu-id="9902e-131">Este exemplo mostra como importar as cinco amostras mais antigas e mais recentes de um arquivo de log do contador de desempenho.</span><span class="sxs-lookup"><span data-stu-id="9902e-131">This example shows how to import the five oldest and five newest samples from a performance counter log file.</span></span>

### <span data-ttu-id="9902e-132">Exemplo 7: obter um resumo dos dados do contador de um arquivo</span><span class="sxs-lookup"><span data-stu-id="9902e-132">Example 7: Get a summary of counter data from a file</span></span>

```
PS C:\> Import-Counter "D:\Samples\Memory.blg" -Summary

OldestRecord            NewestRecord            SampleCount
------------            ------------            -----------
7/10/2008 2:59:18 PM    7/10/2008 3:00:27 PM    1000
```

<span data-ttu-id="9902e-133">Este comando usa o parâmetro *Summary* do cmdlet **Import-Counter** para obter um resumo dos dados do contador no arquivo Memory.blg.</span><span class="sxs-lookup"><span data-stu-id="9902e-133">This command uses the *Summary* parameter of the **Import-Counter** cmdlet to get a summary of the counter data in the Memory.blg file.</span></span>

### <span data-ttu-id="9902e-134">Exemplo 8: atualizar um arquivo de log do contador de desempenho</span><span class="sxs-lookup"><span data-stu-id="9902e-134">Example 8: Update a performance counter log file</span></span>

```
The first command uses the *ListSet* parameter of **Import-Counter** to get the counters in OldData.blg, an existing counter log file. The command uses a pipeline operator (|) to send the data to a ForEach-Object command that gets only the values of the **PathsWithInstances** property of each object
PS C:\> $Counters = Import-Counter OldData.blg -ListSet * | ForEach-Object {$_.PathsWithInstances}

The second command gets updated data for the counters in the $Counters variable. It uses the Get-Counter cmdlet to get a current sample, and then export the results to the NewData.blg file.
PS C:\> Get-Counter -Counter $Counters -MaxSamples 20 | Export-Counter C:\Logs\NewData.blg
```

<span data-ttu-id="9902e-135">Este exemplo atualiza um arquivo de log de contador de desempenho.</span><span class="sxs-lookup"><span data-stu-id="9902e-135">This example updates a performance counter log file.</span></span>

### <span data-ttu-id="9902e-136">Exemplo 9: importar dados de log de desempenho de vários arquivos e, em seguida, salvá-los</span><span class="sxs-lookup"><span data-stu-id="9902e-136">Example 9: Import performance log data from multiple files and then save it</span></span>

```
PS C:\> $Counters = "D:\test\pdata.blg", "D:\samples\netlog.blg" | Import-Counter
```

<span data-ttu-id="9902e-137">Esse comando importa dados de log de desempenho de dois logs e salva os dados na variável $Counters.</span><span class="sxs-lookup"><span data-stu-id="9902e-137">This command imports performance log data from two logs and saves the data in the $Counters variable.</span></span>
<span data-ttu-id="9902e-138">O comando usa um operador de pipeline para enviar os caminhos do log de desempenho para Import-Counter, que importa os dados dos caminhos especificados.</span><span class="sxs-lookup"><span data-stu-id="9902e-138">The command uses a pipeline operator to send the performance log paths to Import-Counter, which imports the data from the specified paths.</span></span>

<span data-ttu-id="9902e-139">Observe que cada caminho é colocado entre aspas e que os caminhos são separados uns dos outros por uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="9902e-139">Notice that each path is enclosed in quotation marks and that the paths are separated from each other by a comma.</span></span>

## <span data-ttu-id="9902e-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9902e-140">PARAMETERS</span></span>

### <span data-ttu-id="9902e-141">-Contador</span><span class="sxs-lookup"><span data-stu-id="9902e-141">-Counter</span></span>

<span data-ttu-id="9902e-142">Especifica, como uma matriz de cadeia de caracteres, os contadores de desempenho.</span><span class="sxs-lookup"><span data-stu-id="9902e-142">Specifies, as a string array, the performance counters.</span></span>
<span data-ttu-id="9902e-143">Por padrão, **Import-Counter** importa todos os dados de todos os contadores nos arquivos de entrada.</span><span class="sxs-lookup"><span data-stu-id="9902e-143">By default, **Import-Counter** imports all data from all counters in the input files.</span></span>
<span data-ttu-id="9902e-144">Insira um ou mais caminhos de contador.</span><span class="sxs-lookup"><span data-stu-id="9902e-144">Enter one or more counter paths.</span></span>
<span data-ttu-id="9902e-145">Caracteres curinga são permitidos na parte de Instância do caminho.</span><span class="sxs-lookup"><span data-stu-id="9902e-145">Wildcards are permitted in the Instance part of the path.</span></span>

<span data-ttu-id="9902e-146">Cada caminho de contador tem o seguinte formato.</span><span class="sxs-lookup"><span data-stu-id="9902e-146">Each counter path has the following format.</span></span>
<span data-ttu-id="9902e-147">O valor ComputerName é necessário no caminho.</span><span class="sxs-lookup"><span data-stu-id="9902e-147">The ComputerName value is required in the path.</span></span>
<span data-ttu-id="9902e-148">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9902e-148">For instance:</span></span>

- `\\<ComputerName>\<CounterSet>(<Instance>)\<CounterName>`

<span data-ttu-id="9902e-149">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9902e-149">For example:</span></span>

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

### <span data-ttu-id="9902e-150">-EndTime</span><span class="sxs-lookup"><span data-stu-id="9902e-150">-EndTime</span></span>

<span data-ttu-id="9902e-151">Especifica uma data e hora de término que este cmdlet importa dados de contador entre os carimbos de hora de *início* e este parâmetro.</span><span class="sxs-lookup"><span data-stu-id="9902e-151">Specifies an end date and time that this cmdlet imports counter data between the *StartTime* and this parameter timestamps.</span></span>
<span data-ttu-id="9902e-152">Insira um objeto **DateTime** , como um criado pelo cmdlet Get-Date.</span><span class="sxs-lookup"><span data-stu-id="9902e-152">Enter a **DateTime** object, such as one created by the Get-Date cmdlet.</span></span>
<span data-ttu-id="9902e-153">Por padrão, **Import-Counter** importa todos os dados do contador nos arquivos especificados pelo parâmetro *Path* .</span><span class="sxs-lookup"><span data-stu-id="9902e-153">By default, **Import-Counter** imports all counter data in the files specified by the *Path* parameter.</span></span>

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

### <span data-ttu-id="9902e-154">-ListSet</span><span class="sxs-lookup"><span data-stu-id="9902e-154">-ListSet</span></span>

<span data-ttu-id="9902e-155">Especifica os conjuntos de contadores de desempenho que são representados nos arquivos exportados.</span><span class="sxs-lookup"><span data-stu-id="9902e-155">Specifies the performance counter sets that are represented in the exported files.</span></span>
<span data-ttu-id="9902e-156">Comandos com esse parâmetro não importam dados.</span><span class="sxs-lookup"><span data-stu-id="9902e-156">Commands with this parameter do not import any data.</span></span>

<span data-ttu-id="9902e-157">Insira um ou mais nomes de pilha de locais.</span><span class="sxs-lookup"><span data-stu-id="9902e-157">Enter one or more counter set names.</span></span>
<span data-ttu-id="9902e-158">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="9902e-158">Wildcards are permitted.</span></span>
<span data-ttu-id="9902e-159">Para obter todos os conjuntos de contadores no arquivo, digite `Import-Counter -ListSet *` .</span><span class="sxs-lookup"><span data-stu-id="9902e-159">To get all counter sets in the file, type `Import-Counter -ListSet *`.</span></span>

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

### <span data-ttu-id="9902e-160">-MaxSamples</span><span class="sxs-lookup"><span data-stu-id="9902e-160">-MaxSamples</span></span>

<span data-ttu-id="9902e-161">Especifica o número máximo de amostras a serem importadas por cada contador.</span><span class="sxs-lookup"><span data-stu-id="9902e-161">Specifies the maximum number of samples of each counter to import.</span></span>
<span data-ttu-id="9902e-162">Por padrão, o **Get-Counter** importa todos os dados nos arquivos especificados pelo parâmetro *Path* .</span><span class="sxs-lookup"><span data-stu-id="9902e-162">By default, **Get-Counter** imports all of the data in the files specified by the *Path* parameter.</span></span>

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

### <span data-ttu-id="9902e-163">-Path</span><span class="sxs-lookup"><span data-stu-id="9902e-163">-Path</span></span>

<span data-ttu-id="9902e-164">Especifica os caminhos de arquivo dos arquivos a serem importados.</span><span class="sxs-lookup"><span data-stu-id="9902e-164">Specifies the file paths of the files to be imported.</span></span>
<span data-ttu-id="9902e-165">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="9902e-165">This parameter is required.</span></span>

<span data-ttu-id="9902e-166">Insira o caminho e o nome de arquivo de um arquivo,. csv,,. tsv ou. blg que você exportou usando o cmdlet **Export-Counter** .</span><span class="sxs-lookup"><span data-stu-id="9902e-166">Enter the path and file name of a, .csv,, .tsv, or .blg file that you exported by using the **Export-Counter** cmdlet.</span></span>
<span data-ttu-id="9902e-167">Você pode especificar somente um arquivo .csv ou .tsv, mas pode especificar vários arquivos .blg (até 32) em cada comando.</span><span class="sxs-lookup"><span data-stu-id="9902e-167">You can specify only one .csv or .tsv file, but you can specify multiple .blg files (up to 32) in each command.</span></span>
<span data-ttu-id="9902e-168">Você também pode canalizar cadeias de caracteres de caminho de arquivo (entre aspas) para **Import-Counter** .</span><span class="sxs-lookup"><span data-stu-id="9902e-168">You can also pipe file path strings (in quotation marks) to **Import-Counter** .</span></span>

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

### <span data-ttu-id="9902e-169">-StartTime</span><span class="sxs-lookup"><span data-stu-id="9902e-169">-StartTime</span></span>

<span data-ttu-id="9902e-170">Especifica a data e a hora de início em que esse cmdlet obtém dados do contador.</span><span class="sxs-lookup"><span data-stu-id="9902e-170">Specifies the start date and time in which this cmdlet gets counter data.</span></span>
<span data-ttu-id="9902e-171">Insira um objeto **DateTime** , como um criado pelo cmdlet **Get-Date** .</span><span class="sxs-lookup"><span data-stu-id="9902e-171">Enter a **DateTime** object, such as one created by the **Get-Date** cmdlet.</span></span>
<span data-ttu-id="9902e-172">Por padrão, **Import-Counter** importa todos os dados do contador nos arquivos especificados pelo parâmetro *Path* .</span><span class="sxs-lookup"><span data-stu-id="9902e-172">By default, **Import-Counter** imports all counter data in the files specified by the *Path* parameter.</span></span>

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

### <span data-ttu-id="9902e-173">-Resumo</span><span class="sxs-lookup"><span data-stu-id="9902e-173">-Summary</span></span>

<span data-ttu-id="9902e-174">Indica que esse cmdlet obtém um resumo dos dados importados, em vez de obter amostras de dados de contador individuais.</span><span class="sxs-lookup"><span data-stu-id="9902e-174">Indicates that this cmdlet gets a summary of the imported data, instead of getting individual counter data samples.</span></span>

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

### <span data-ttu-id="9902e-175">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9902e-175">CommonParameters</span></span>

<span data-ttu-id="9902e-176">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9902e-176">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9902e-177">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9902e-177">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9902e-178">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="9902e-178">INPUTS</span></span>

### <span data-ttu-id="9902e-179">System.String</span><span class="sxs-lookup"><span data-stu-id="9902e-179">System.String</span></span>

<span data-ttu-id="9902e-180">Você pode canalizar caminhos de log do contador de desempenho para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9902e-180">You can pipe performance counter log paths to this cmdlet.</span></span>

## <span data-ttu-id="9902e-181">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="9902e-181">OUTPUTS</span></span>

### <span data-ttu-id="9902e-182">Microsoft. PowerShell. Commands. getcounterer. PerformanceCounterSampleSet, Microsoft. PowerShell. Commands. getcounterer. contador, Microsoft. PowerShell. Commands. getcounterer. prefileinfo</span><span class="sxs-lookup"><span data-stu-id="9902e-182">Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet, Microsoft.PowerShell.Commands.GetCounter.CounterSet, Microsoft.PowerShell.Commands.GetCounter.CounterFileInfo</span></span>

<span data-ttu-id="9902e-183">Esse cmdlet retorna um **Microsoft. PowerShell. Commands. Getcounterer. PerformanceCounterSampleSet** .</span><span class="sxs-lookup"><span data-stu-id="9902e-183">This cmdlet returns a **Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet** .</span></span>
<span data-ttu-id="9902e-184">Se você usar o parâmetro *ListSet* , esse cmdlet retornará um objeto **Microsoft. PowerShell. Commands. getcounterer. contadorset** .</span><span class="sxs-lookup"><span data-stu-id="9902e-184">If you use the *ListSet* parameter, this cmdlet returns a **Microsoft.PowerShell.Commands.GetCounter.CounterSet** object.</span></span>
<span data-ttu-id="9902e-185">Se você usar o parâmetro *Summary* , esse cmdlet retornará um objeto **Microsoft. PowerShell. Commands. getcounterer. Counter FileInfo** .</span><span class="sxs-lookup"><span data-stu-id="9902e-185">If you use the *Summary* parameter, this cmdlet returns a **Microsoft.PowerShell.Commands.GetCounter.CounterFileInfo** object.</span></span>

## <span data-ttu-id="9902e-186">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="9902e-186">NOTES</span></span>

* <span data-ttu-id="9902e-187">Este cmdlet não tem um parâmetro *ComputerName* .</span><span class="sxs-lookup"><span data-stu-id="9902e-187">This cmdlet does not have a *ComputerName* parameter.</span></span> <span data-ttu-id="9902e-188">No entanto, se o computador estiver configurado para comunicação remota do Windows PowerShell, você poderá usar o cmdlet Invoke-Command para executar um comando **Import-Counter** em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="9902e-188">However, if the computer is configured for Windows PowerShell remoting, you can use the Invoke-Command cmdlet to run an **Import-Counter** command on a remote computer.</span></span>

## <span data-ttu-id="9902e-189">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="9902e-189">RELATED LINKS</span></span>

[<span data-ttu-id="9902e-190">Export-Counter</span><span class="sxs-lookup"><span data-stu-id="9902e-190">Export-Counter</span></span>](Export-Counter.md)

[<span data-ttu-id="9902e-191">Get-Counter</span><span class="sxs-lookup"><span data-stu-id="9902e-191">Get-Counter</span></span>](Get-Counter.md)
