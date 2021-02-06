---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 11/06/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/get-counter?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Counter
ms.openlocfilehash: 4aed8db557b2d623aba4cd7218524af9957674c9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598007"
---
# <span data-ttu-id="99f17-102">Get-Counter</span><span class="sxs-lookup"><span data-stu-id="99f17-102">Get-Counter</span></span>

## <span data-ttu-id="99f17-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="99f17-103">SYNOPSIS</span></span>
<span data-ttu-id="99f17-104">Obtém os dados do contador de desempenho de computadores locais e remotos.</span><span class="sxs-lookup"><span data-stu-id="99f17-104">Gets performance counter data from local and remote computers.</span></span>

## <span data-ttu-id="99f17-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="99f17-105">SYNTAX</span></span>

### <span data-ttu-id="99f17-106">Getcounterset (padrão)</span><span class="sxs-lookup"><span data-stu-id="99f17-106">GetCounterSet (Default)</span></span>

```
Get-Counter [[-Counter] <String[]>] [-SampleInterval <Int32>] [-MaxSamples <Int64>] [-Continuous]
 [-ComputerName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="99f17-107">ListSetSet</span><span class="sxs-lookup"><span data-stu-id="99f17-107">ListSetSet</span></span>

```
Get-Counter [-ListSet] <String[]> [-ComputerName <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="99f17-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="99f17-108">DESCRIPTION</span></span>

<span data-ttu-id="99f17-109">O `Get-Counter` cmdlet obtém dados do contador de desempenho diretamente da instrumentação de monitoramento de desempenho na família de sistemas operacionais Windows.</span><span class="sxs-lookup"><span data-stu-id="99f17-109">The `Get-Counter` cmdlet gets performance counter data directly from the performance monitoring instrumentation in the Windows family of operating systems.</span></span> <span data-ttu-id="99f17-110">`Get-Counter` Obtém dados de desempenho de um computador local ou de computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="99f17-110">`Get-Counter` gets performance data from a local computer or remote computers.</span></span>

<span data-ttu-id="99f17-111">Você pode usar os `Get-Counter` parâmetros para especificar um ou mais computadores, listar os conjuntos de contadores de desempenho e as instâncias que eles contêm, definir os intervalos de exemplo e especificar o número máximo de amostras.</span><span class="sxs-lookup"><span data-stu-id="99f17-111">You can use the `Get-Counter` parameters to specify one or more computers, list the performance counter sets and the instances they contain, set the sample intervals, and specify the maximum number of samples.</span></span> <span data-ttu-id="99f17-112">Sem parâmetros, `Get-Counter` obtém dados do contador de desempenho para um conjunto de contadores do sistema.</span><span class="sxs-lookup"><span data-stu-id="99f17-112">Without parameters, `Get-Counter` gets performance counter data for a set of system counters.</span></span>

<span data-ttu-id="99f17-113">Muitos conjuntos de contadores são protegidos por listas de controle de acesso (ACL).</span><span class="sxs-lookup"><span data-stu-id="99f17-113">Many counter sets are protected by access control lists (ACL).</span></span> <span data-ttu-id="99f17-114">Para ver todos os conjuntos de contadores, abra o PowerShell com a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="99f17-114">To see all counter sets, open PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="99f17-115">Esse cmdlet foi reintroduzido no PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="99f17-115">This cmdlet was reintroduced in PowerShell 7.</span></span>

## <span data-ttu-id="99f17-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="99f17-116">EXAMPLES</span></span>

### <span data-ttu-id="99f17-117">Exemplo 1: obter a lista de conjuntos de contadores</span><span class="sxs-lookup"><span data-stu-id="99f17-117">Example 1: Get the counter set list</span></span>

<span data-ttu-id="99f17-118">Este exemplo obtém a lista de conjuntos de contadores do computador local.</span><span class="sxs-lookup"><span data-stu-id="99f17-118">This example gets the local computer's list of counter sets.</span></span>

```powershell
Get-Counter -ListSet *
```

```Output
CounterSetName     : Processor
MachineName        : .
CounterSetType     : MultiInstance
Description        : The Processor performance object consists of counters that measure aspects ...
                     computer that performs arithmetic and logical computations, initiates ...
                     computer can have multiple processors.  The processor object represents ...
Paths              : {\Processor(*)\% Processor Time, \Processor(*)\% User Time, ...
PathsWithInstances : {\Processor(0)\% Processor Time, \Processor(1)\% Processor Time, ...
Counter            : {\Processor(*)\% Processor Time, \Processor(*)\% User Time, ...
```

<span data-ttu-id="99f17-119">`Get-Counter` usa o parâmetro **ListSet** com um asterisco ( `*` ) para obter a lista de conjuntos de contadores.</span><span class="sxs-lookup"><span data-stu-id="99f17-119">`Get-Counter` uses the **ListSet** parameter with an asterisk (`*`) to get the list of counter sets.</span></span>
<span data-ttu-id="99f17-120">O ponto ( `.` ) na coluna **MachineName** representa o computador local.</span><span class="sxs-lookup"><span data-stu-id="99f17-120">The dot (`.`) in the **MachineName** column represents the local computer.</span></span>

### <span data-ttu-id="99f17-121">Exemplo 2: especificar SampleInterval e MaxSamples</span><span class="sxs-lookup"><span data-stu-id="99f17-121">Example 2: Specify the SampleInterval and MaxSamples</span></span>

<span data-ttu-id="99f17-122">Este exemplo obtém os dados do contador para todos os processadores no computador local.</span><span class="sxs-lookup"><span data-stu-id="99f17-122">This examples gets the counter data for all processors on the local computer.</span></span> <span data-ttu-id="99f17-123">Os dados são coletados em intervalos de dois segundos até que haja três amostras.</span><span class="sxs-lookup"><span data-stu-id="99f17-123">Data is collected at two-second intervals until there are three samples.</span></span>

```powershell
Get-Counter -Counter "\Processor(_Total)\% Processor Time" -SampleInterval 2 -MaxSamples 3
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/18/2019 14:39:56        \\Computer01\processor(_total)\% processor time :
                          20.7144271584086

6/18/2019 14:39:58        \\Computer01\processor(_total)\% processor time :
                          10.4391790575511

6/18/2019 14:40:01        \\Computer01\processor(_total)\% processor time :
                          37.5968799396998
```

<span data-ttu-id="99f17-124">`Get-Counter` usa o parâmetro **Counter** para especificar o caminho do contador `\Processor(_Total)\% Processor Time` .</span><span class="sxs-lookup"><span data-stu-id="99f17-124">`Get-Counter` uses the **Counter** parameter to specify the counter path `\Processor(_Total)\% Processor Time`.</span></span> <span data-ttu-id="99f17-125">O parâmetro **SampleInterval** define um intervalo de dois segundos para verificar o contador.</span><span class="sxs-lookup"><span data-stu-id="99f17-125">The **SampleInterval** parameter sets a two-second interval to check the counter.</span></span> <span data-ttu-id="99f17-126">**MaxSamples** determina que três é o número máximo de vezes para verificar o contador.</span><span class="sxs-lookup"><span data-stu-id="99f17-126">**MaxSamples** determines that three is the maximum number of times to check the counter.</span></span>

### <span data-ttu-id="99f17-127">Exemplo 3: obter amostras contínuas de um contador</span><span class="sxs-lookup"><span data-stu-id="99f17-127">Example 3: Get continuous samples of a counter</span></span>

<span data-ttu-id="99f17-128">Este exemplo obtém amostras contínuas para um contador a cada segundo.</span><span class="sxs-lookup"><span data-stu-id="99f17-128">This examples gets continuous samples for a counter every second.</span></span> <span data-ttu-id="99f17-129">Para interromper o comando, pressione <kbd>Ctrl</kbd> + <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="99f17-129">To stop the command, press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span> <span data-ttu-id="99f17-130">Para especificar um intervalo mais longo entre amostras, use o parâmetro **SampleInterval** .</span><span class="sxs-lookup"><span data-stu-id="99f17-130">To specify a longer interval between samples, use the **SampleInterval** parameter.</span></span>

```powershell
Get-Counter -Counter "\Processor(_Total)\% Processor Time" -Continuous
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/19/2019 15:35:03        \\Computer01\processor(_total)\% processor time :
                          43.8522842937022

6/19/2019 15:35:04        \\Computer01\processor(_total)\% processor time :
                          29.7896844697383

6/19/2019 15:35:05        \\Computer01\processor(_total)\% processor time :
                          29.4962645638135

6/19/2019 15:35:06        \\Computer01\processor(_total)\% processor time :
                          25.5901500127408
```

<span data-ttu-id="99f17-131">`Get-Counter` usa o parâmetro **Counter** para especificar o `\Processor\% Processor Time` contador.</span><span class="sxs-lookup"><span data-stu-id="99f17-131">`Get-Counter` uses the **Counter** parameter to specify the `\Processor\% Processor Time` counter.</span></span>
<span data-ttu-id="99f17-132">O parâmetro **Continuous** especifica para obter amostras a cada segundo até que o comando seja interrompido com <kbd>Ctrl</kbd> + <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="99f17-132">The **Continuous** parameter specifies to get samples every second until the command is stopped with <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span>

### <span data-ttu-id="99f17-133">Exemplo 4: lista alfabética de conjuntos de contadores</span><span class="sxs-lookup"><span data-stu-id="99f17-133">Example 4: Alphabetical list of counter sets</span></span>

<span data-ttu-id="99f17-134">Este exemplo usa o pipeline para obter a lista de contadores definida e, em seguida, classificar a lista em ordem alfabética.</span><span class="sxs-lookup"><span data-stu-id="99f17-134">This example uses the pipeline to get the counter list set and then sort the list in alphabetical order.</span></span>

```powershell
Get-Counter -ListSet * |
  Sort-Object -Property CounterSetName |
    Format-Table CounterSetName, CounterSetType -AutoSize
```

```Output
CounterSetName                        CounterSetType
--------------                        --------------
.NET CLR Data                         SingleInstance
.NET Data Provider for SqlServer      SingleInstance
AppV Client Streamed Data Percentage  SingleInstance
Authorization Manager Applications    SingleInstance
BitLocker                             MultiInstance
Bluetooth Device                      SingleInstance
Cache                                 SingleInstance
Client Side Caching                   SingleInstance
```

<span data-ttu-id="99f17-135">`Get-Counter` usa o parâmetro **ListSet** com um asterisco ( `*` ) para obter uma lista completa de conjuntos de contadores.</span><span class="sxs-lookup"><span data-stu-id="99f17-135">`Get-Counter` uses the **ListSet** parameter with an asterisk (`*`) to get a complete list of counter sets.</span></span> <span data-ttu-id="99f17-136">Os objetos **CounterSet** são enviados pelo pipeline.</span><span class="sxs-lookup"><span data-stu-id="99f17-136">The **CounterSet** objects are sent down the pipeline.</span></span> <span data-ttu-id="99f17-137">`Sort-Object` usa o parâmetro **Property** para especificar que os objetos são classificados por **CounterSetName**.</span><span class="sxs-lookup"><span data-stu-id="99f17-137">`Sort-Object` uses the **Property** parameter to specify that the objects are sorted by **CounterSetName**.</span></span> <span data-ttu-id="99f17-138">Os objetos são enviados ao pipeline para `Format-Table` .</span><span class="sxs-lookup"><span data-stu-id="99f17-138">The objects are sent down the pipeline to `Format-Table`.</span></span> <span data-ttu-id="99f17-139">O parâmetro **AutoSize** ajusta as larguras das colunas para minimizar o truncamento.</span><span class="sxs-lookup"><span data-stu-id="99f17-139">The **AutoSize** parameter adjusts the column widths to minimize truncation.</span></span>

<span data-ttu-id="99f17-140">O ponto ( `.` ) na coluna **MachineName** representa o computador local.</span><span class="sxs-lookup"><span data-stu-id="99f17-140">The dot (`.`) in the **MachineName** column represents the local computer.</span></span>

### <span data-ttu-id="99f17-141">Exemplo 5: executar um trabalho em segundo plano para obter dados do contador</span><span class="sxs-lookup"><span data-stu-id="99f17-141">Example 5: Run a background job to get counter data</span></span>

<span data-ttu-id="99f17-142">Neste exemplo, `Start-Job` executa um `Get-Counter` comando como um trabalho em segundo plano no computador local.</span><span class="sxs-lookup"><span data-stu-id="99f17-142">In this example, `Start-Job` runs a `Get-Counter` command as a background job on the local computer.</span></span>
<span data-ttu-id="99f17-143">Para exibir a saída do contador de desempenho do trabalho, use o `Receive-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="99f17-143">To view the performance counter output from the job, use the `Receive-Job` cmdlet.</span></span>

```powershell
Start-Job -ScriptBlock {Get-Counter -Counter "\LogicalDisk(_Total)\% Free Space" -MaxSamples 1000}
```

```Output
Id     Name  PSJobTypeName   State    HasMoreData  Location   Command
--     ----  -------------   -----    -----------  --------   -------
1      Job1  BackgroundJob   Running  True         localhost  Get-Counter -Counter
```

<span data-ttu-id="99f17-144">`Start-Job` usa o parâmetro **scriptblock** para executar um `Get-Counter` comando.</span><span class="sxs-lookup"><span data-stu-id="99f17-144">`Start-Job` uses the **ScriptBlock** parameter to run a `Get-Counter` command.</span></span> <span data-ttu-id="99f17-145">`Get-Counter` usa o parâmetro **Counter** para especificar o caminho do contador `\LogicalDisk(_Total)\% Free Space` .</span><span class="sxs-lookup"><span data-stu-id="99f17-145">`Get-Counter` uses the **Counter** parameter to specify the counter path `\LogicalDisk(_Total)\% Free Space`.</span></span> <span data-ttu-id="99f17-146">O parâmetro **MaxSamples** especifica a obtenção de exemplos de 1000 do contador.</span><span class="sxs-lookup"><span data-stu-id="99f17-146">The **MaxSamples** parameter specifies to get 1000 samples of the counter.</span></span>

### <span data-ttu-id="99f17-147">Exemplo 6: obter dados do contador de vários computadores</span><span class="sxs-lookup"><span data-stu-id="99f17-147">Example 6: Get counter data from multiple computers</span></span>

<span data-ttu-id="99f17-148">Este exemplo usa uma variável para obter dados do contador de desempenho de dois computadores.</span><span class="sxs-lookup"><span data-stu-id="99f17-148">This example uses a variable to get performance counter data from two computers.</span></span>

```powershell
$DiskReads = "\LogicalDisk(C:)\Disk Reads/sec"
$DiskReads | Get-Counter -ComputerName Server01, Server02 -MaxSamples 10
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/21/2019 10:51:04        \\Server01\logicaldisk(c:)\disk reads/sec :
                          0

                          \\Server02\logicaldisk(c:)\disk reads/sec :
                          0.983050344269146
```

<span data-ttu-id="99f17-149">A `$DiskReads` variável armazena o `\LogicalDisk(C:)\Disk Reads/sec` caminho do contador.</span><span class="sxs-lookup"><span data-stu-id="99f17-149">The `$DiskReads` variable stores the `\LogicalDisk(C:)\Disk Reads/sec` counter path.</span></span> <span data-ttu-id="99f17-150">A `$DiskReads` variável é enviada ao pipeline para `Get-Counter` .</span><span class="sxs-lookup"><span data-stu-id="99f17-150">The `$DiskReads` variable is sent down the pipeline to `Get-Counter`.</span></span> <span data-ttu-id="99f17-151">**Counter** é o primeiro parâmetro de posição e aceita o caminho armazenado em `$DiskReads` .</span><span class="sxs-lookup"><span data-stu-id="99f17-151">**Counter** is the first position parameter and accepts the path stored in `$DiskReads`.</span></span> <span data-ttu-id="99f17-152">**ComputerName** especifica os dois computadores e **MaxSamples** especifica para obter 10 amostras de cada computador.</span><span class="sxs-lookup"><span data-stu-id="99f17-152">**ComputerName** specifies the two computers and **MaxSamples** specifies to get 10 samples from each computer.</span></span>

### <span data-ttu-id="99f17-153">Exemplo 7: obter os valores de instância de um contador de vários computadores aleatórios</span><span class="sxs-lookup"><span data-stu-id="99f17-153">Example 7: Get a counter's instance values from multiple random computers</span></span>

<span data-ttu-id="99f17-154">Este exemplo obtém o valor de um contador de desempenho em 50 computadores remotos aleatórios na empresa.</span><span class="sxs-lookup"><span data-stu-id="99f17-154">This example gets the value of a performance counter on 50 random, remote computers in the enterprise.</span></span> <span data-ttu-id="99f17-155">O parâmetro **ComputerName** usa nomes de computador aleatórios armazenados em uma variável.</span><span class="sxs-lookup"><span data-stu-id="99f17-155">The **ComputerName** parameter uses random computer names stored in a variable.</span></span> <span data-ttu-id="99f17-156">Para atualizar os nomes dos computadores na variável, recrie a variável.</span><span class="sxs-lookup"><span data-stu-id="99f17-156">To update the computer names in the variable, recreate the variable.</span></span>

<span data-ttu-id="99f17-157">Uma alternativa para os nomes de servidor no parâmetro **ComputerName** é usar um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="99f17-157">An alternative for the server names in the **ComputerName** parameter is to use a text file.</span></span> <span data-ttu-id="99f17-158">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="99f17-158">For example:</span></span>

`-ComputerName (Get-Random (Get-Content -Path C:\Servers.txt) -Count 50)`

<span data-ttu-id="99f17-159">O caminho do contador inclui um asterisco ( `*` ) no nome da instância para obter os dados para cada um dos processadores do computador remoto.</span><span class="sxs-lookup"><span data-stu-id="99f17-159">The counter path includes an asterisk (`*`) in the instance name to get the data for each of the remote computer's processors.</span></span>

```powershell
$Servers = Get-Random (Get-Content -Path C:\Servers.txt) -Count 50
$Counter = "\Processor(*)\% Processor Time"
Get-Counter -Counter $Counter -ComputerName $Servers
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/20/2019 12:20:35        \\Server01\processor(0)\% processor time :
                          6.52610319637854

                          \\Server01\processor(1)\% processor time :
                          3.41030663625782

                          \\Server01\processor(2)\% processor time :
                          9.64189975649925

                          \\Server01\processor(3)\% processor time :
                          1.85240835619747

                          \\Server01\processor(_total)\% processor time :
                          5.35768447160776
```

<span data-ttu-id="99f17-160">O `Get-Random` cmdlet usa `Get-Content` para selecionar 50 nomes de computador aleatórios do `Servers.txt` arquivo.</span><span class="sxs-lookup"><span data-stu-id="99f17-160">The `Get-Random` cmdlet uses `Get-Content` to select 50 random computer names from the `Servers.txt` file.</span></span> <span data-ttu-id="99f17-161">Os nomes dos computadores remotos são armazenados na `$Servers` variável.</span><span class="sxs-lookup"><span data-stu-id="99f17-161">The remote computer names are stored in the `$Servers` variable.</span></span> <span data-ttu-id="99f17-162">O `\Processor(*)\% Processor Time` caminho do contador é armazenado na `$Counter` variável.</span><span class="sxs-lookup"><span data-stu-id="99f17-162">The `\Processor(*)\% Processor Time` counter's path is stored in the `$Counter` variable.</span></span> <span data-ttu-id="99f17-163">`Get-Counter` usa o parâmetro **Counter** para especificar os contadores na `$Counter` variável.</span><span class="sxs-lookup"><span data-stu-id="99f17-163">`Get-Counter` uses the **Counter** parameter to specify the counters in the `$Counter` variable.</span></span> <span data-ttu-id="99f17-164">O parâmetro **ComputerName** especifica os nomes de computador na `$Servers` variável.</span><span class="sxs-lookup"><span data-stu-id="99f17-164">The **ComputerName** parameter specifies the computer names in the `$Servers` variable.</span></span>

### <span data-ttu-id="99f17-165">Exemplo 8: usar a propriedade Path para obter nomes de caminho formatados</span><span class="sxs-lookup"><span data-stu-id="99f17-165">Example 8: Use the Path property to get formatted path names</span></span>

<span data-ttu-id="99f17-166">Este exemplo usa a propriedade **path** de um conjunto de contadores para localizar os nomes de caminho formatados para os contadores de desempenho.</span><span class="sxs-lookup"><span data-stu-id="99f17-166">This example uses the **Path** property of a counter set to find the formatted path names for the performance counters.</span></span>

<span data-ttu-id="99f17-167">O pipeline é usado com o `Where-Object` cmdlet para localizar um subconjunto dos nomes de caminho.</span><span class="sxs-lookup"><span data-stu-id="99f17-167">The pipeline is used with the `Where-Object` cmdlet to find a subset of the path names.</span></span> <span data-ttu-id="99f17-168">Para localizar um contador define uma lista completa de caminhos de contador, remova o pipeline ( `|` ) e o `Where-Object` comando.</span><span class="sxs-lookup"><span data-stu-id="99f17-168">To find a counter sets complete list of counter paths, remove the pipeline (`|`) and `Where-Object` command.</span></span>

<span data-ttu-id="99f17-169">O `$_` é uma variável automática para o objeto atual no pipeline.</span><span class="sxs-lookup"><span data-stu-id="99f17-169">The `$_` is an automatic variable for the current object in the pipeline.</span></span>
<span data-ttu-id="99f17-170">Para obter mais informações, consulte [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="99f17-170">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

```powershell
(Get-Counter -ListSet Memory).Paths | Where-Object { $_ -like "*Cache*" }
```

```Output
\Memory\Cache Faults/sec
\Memory\Cache Bytes
\Memory\Cache Bytes Peak
\Memory\System Cache Resident Bytes
\Memory\Standby Cache Reserve Bytes
\Memory\Standby Cache Normal Priority Bytes
\Memory\Standby Cache Core Bytes
\Memory\Long-Term Average Standby Cache Lifetime (s)
```

<span data-ttu-id="99f17-171">`Get-Counter` usa o parâmetro **ListSet** para especificar o conjunto de contadores de **memória** .</span><span class="sxs-lookup"><span data-stu-id="99f17-171">`Get-Counter` uses the **ListSet** parameter to specify the **Memory** counter set.</span></span> <span data-ttu-id="99f17-172">O comando é colocado entre parênteses para que a propriedade **Paths** retorne cada caminho como uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="99f17-172">The command is enclosed in parentheses so that the **Paths** property returns each path as a string.</span></span> <span data-ttu-id="99f17-173">Os objetos são enviados ao pipeline para `Where-Object` .</span><span class="sxs-lookup"><span data-stu-id="99f17-173">The objects are sent down the pipeline to `Where-Object`.</span></span> <span data-ttu-id="99f17-174">`Where-Object` usa a variável `$_` para processar cada objeto e usa o `-like` operador para localizar correspondências para a cadeia de caracteres `*Cache*` .</span><span class="sxs-lookup"><span data-stu-id="99f17-174">`Where-Object` uses the variable `$_` to process each object and uses the `-like` operator to find matches for the string `*Cache*`.</span></span> <span data-ttu-id="99f17-175">Os asteriscos ( `*` ) são curingas para quaisquer caracteres.</span><span class="sxs-lookup"><span data-stu-id="99f17-175">The asterisks (`*`) are wildcards for any characters.</span></span>

### <span data-ttu-id="99f17-176">Exemplo 9: usar a propriedade PathsWithInstances para obter nomes de caminho formatados</span><span class="sxs-lookup"><span data-stu-id="99f17-176">Example 9: Use the PathsWithInstances property to get formatted path names</span></span>

<span data-ttu-id="99f17-177">Este exemplo obtém os nomes de caminho formatados que incluem as instâncias para os contadores de desempenho do **disco físico** .</span><span class="sxs-lookup"><span data-stu-id="99f17-177">This example gets the formatted path names that include the instances for the **PhysicalDisk** performance counters.</span></span>

```powershell
(Get-Counter -ListSet PhysicalDisk).PathsWithInstances
```

```Output
\PhysicalDisk(0 C:)\Current Disk Queue Length
\PhysicalDisk(_Total)\Current Disk Queue Length
\PhysicalDisk(0 C:)\% Disk Time
\PhysicalDisk(_Total)\% Disk Time
\PhysicalDisk(0 C:)\Avg. Disk Queue Length
\PhysicalDisk(_Total)\Avg. Disk Queue Length
\PhysicalDisk(0 C:)\% Disk Read Time
\PhysicalDisk(_Total)\% Disk Read Time
```

<span data-ttu-id="99f17-178">`Get-Counter` usa o parâmetro **ListSet** para especificar o conjunto de contadores de **PhysicalDisk** .</span><span class="sxs-lookup"><span data-stu-id="99f17-178">`Get-Counter` uses the **ListSet** parameter to specify the **PhysicalDisk** counter set.</span></span> <span data-ttu-id="99f17-179">O comando é colocado entre parênteses para que a propriedade **PathsWithInstances** retorne cada instância de caminho como uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="99f17-179">The command is enclosed in parentheses so that the **PathsWithInstances** property returns each path instance as a string.</span></span>

### <span data-ttu-id="99f17-180">Exemplo 10: obter um único valor para cada contador em um conjunto de contadores</span><span class="sxs-lookup"><span data-stu-id="99f17-180">Example 10: Get a single value for each counter in a counter set</span></span>

<span data-ttu-id="99f17-181">Neste exemplo, um único valor é retornado para cada contador de desempenho no conjunto de contadores de **memória** do computador local.</span><span class="sxs-lookup"><span data-stu-id="99f17-181">In this example, a single value is returned for each performance counter in the local computer's **Memory** counter set.</span></span>

```powershell
$MemCounters = (Get-Counter -ListSet Memory).Paths
Get-Counter -Counter $MemCounters
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/19/2019 12:05:00        \\Computer01\memory\page faults/sec :
                          868.772077545597

                          \\Computer01\memory\available bytes :
                          9031176192

                          \\Computer01\memory\committed bytes :
                          8242982912

                          \\Computer01\memory\commit limit :
                          19603333120
```

<span data-ttu-id="99f17-182">`Get-Counter` usa o parâmetro **ListSet** para especificar o conjunto de contadores de **memória** .</span><span class="sxs-lookup"><span data-stu-id="99f17-182">`Get-Counter` uses the **ListSet** parameter to specify the **Memory** counter set.</span></span> <span data-ttu-id="99f17-183">O comando é colocado entre parênteses para que a propriedade **Paths** retorne cada caminho como uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="99f17-183">The command is enclosed in parentheses so that the **Paths** property returns each path as a string.</span></span> <span data-ttu-id="99f17-184">Os caminhos são armazenados na `$MemCounters` variável.</span><span class="sxs-lookup"><span data-stu-id="99f17-184">The paths are stored in the `$MemCounters` variable.</span></span> <span data-ttu-id="99f17-185">`Get-Counter` usa o parâmetro **Counter** para especificar os caminhos do contador na `$MemCounters` variável.</span><span class="sxs-lookup"><span data-stu-id="99f17-185">`Get-Counter` uses the **Counter** parameter to specify the counter paths in the `$MemCounters` variable.</span></span>

### <span data-ttu-id="99f17-186">Exemplo 11: exibir os valores de propriedade de um objeto</span><span class="sxs-lookup"><span data-stu-id="99f17-186">Example 11: Display an object's property values</span></span>

<span data-ttu-id="99f17-187">Os valores de propriedade no objeto **PerformanceCounterSample** representam cada amostra de dados.</span><span class="sxs-lookup"><span data-stu-id="99f17-187">The property values in the **PerformanceCounterSample** object represent each data sample.</span></span> <span data-ttu-id="99f17-188">Neste exemplo, usamos as propriedades do objeto de **Contraamostrações** para examinar, selecionar, classificar e agrupar os dados.</span><span class="sxs-lookup"><span data-stu-id="99f17-188">In this example we use the properties of the **CounterSamples** object to examine, select, sort, and group the data.</span></span>

```powershell
$Counter = "\\Server01\Process(Idle)\% Processor Time"
$Data = Get-Counter $Counter
$Data.CounterSamples | Format-List -Property *
```

```Output
Path             : \\Server01\process(idle)\% processor time
InstanceName     : idle
CookedValue      : 198.467899571389
RawValue         : 14329160321003
SecondValue      : 128606459528326201
MultipleCount    : 1
CounterType      : Timer100Ns
Timestamp        : 6/19/2019 12:20:49
Timestamp100NSec : 128606207528320000
Status           : 0
DefaultScale     : 0
TimeBase         : 10000000
```

<span data-ttu-id="99f17-189">O caminho do contador é armazenado na `$Counter` variável.</span><span class="sxs-lookup"><span data-stu-id="99f17-189">The counter path is stored in the `$Counter` variable.</span></span> <span data-ttu-id="99f17-190">`Get-Counter` Obtém uma amostra dos valores do contador e armazena os resultados na `$Data` variável.</span><span class="sxs-lookup"><span data-stu-id="99f17-190">`Get-Counter` gets one sample of the counter values and stores the results in the `$Data` variable.</span></span> <span data-ttu-id="99f17-191">A `$Data` variável usa a propriedade de **contraamostrações** para obter as propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="99f17-191">The `$Data` variable uses the **CounterSamples** property to get the object's properties.</span></span> <span data-ttu-id="99f17-192">O objeto é enviado ao pipeline para `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="99f17-192">The object is sent down the pipeline to `Format-List`.</span></span> <span data-ttu-id="99f17-193">O parâmetro **Property** usa um curinga asterisco ( `*` ) para selecionar todas as propriedades.</span><span class="sxs-lookup"><span data-stu-id="99f17-193">The **Property** parameter uses an asterisk (`*`) wildcard to select all the properties.</span></span>

### <span data-ttu-id="99f17-194">Exemplo 12: valores de matriz do contador de desempenho</span><span class="sxs-lookup"><span data-stu-id="99f17-194">Example 12: Performance counter array values</span></span>

<span data-ttu-id="99f17-195">Neste exemplo, uma variável armazena cada contador de desempenho.</span><span class="sxs-lookup"><span data-stu-id="99f17-195">In this example, a variable stores each performance counter.</span></span> <span data-ttu-id="99f17-196">A propriedade de **Metaamostras** é uma matriz que pode exibir valores de contador específicos.</span><span class="sxs-lookup"><span data-stu-id="99f17-196">The **CounterSamples** property is an array that can display specific counter values.</span></span>

<span data-ttu-id="99f17-197">Para exibir cada exemplo de contador, use `$Counter.CounterSamples` .</span><span class="sxs-lookup"><span data-stu-id="99f17-197">To display each counter sample, use `$Counter.CounterSamples`.</span></span>

```powershell
$Counter = Get-Counter -Counter "\Processor(*)\% Processor Time"
$Counter.CounterSamples[0]
```

```Output
Path                                         InstanceName        CookedValue
----                                         ------------        -----------
\\Computer01\processor(0)\% processor time   0              1.33997091699662
```

<span data-ttu-id="99f17-198">`Get-Counter` usa o parâmetro **Counter** para especificar o contador `\Processor(*)\% Processor Time` .</span><span class="sxs-lookup"><span data-stu-id="99f17-198">`Get-Counter` uses the **Counter** parameter to specify the counter `\Processor(*)\% Processor Time`.</span></span> <span data-ttu-id="99f17-199">Os valores são armazenados na `$Counter` variável.</span><span class="sxs-lookup"><span data-stu-id="99f17-199">The values are stored in the `$Counter` variable.</span></span>
<span data-ttu-id="99f17-200">`$Counter.CounterSamples[0]` exibe o valor da matriz para o primeiro valor do contador.</span><span class="sxs-lookup"><span data-stu-id="99f17-200">`$Counter.CounterSamples[0]` displays the array value for the first counter value.</span></span>

### <span data-ttu-id="99f17-201">Exemplo 13: comparar valores de contadores de desempenho</span><span class="sxs-lookup"><span data-stu-id="99f17-201">Example 13: Compare performance counter values</span></span>

<span data-ttu-id="99f17-202">Este exemplo localiza a quantidade de tempo do processador usada por cada processador no computador local.</span><span class="sxs-lookup"><span data-stu-id="99f17-202">This example finds the amount of processor time used by each processor on the local computer.</span></span> <span data-ttu-id="99f17-203">A propriedade **Comsamples** é usada para comparar os dados do contador com um valor especificado.</span><span class="sxs-lookup"><span data-stu-id="99f17-203">The **CounterSamples** property is used to compare the counter data against a specified value.</span></span>

<span data-ttu-id="99f17-204">Para exibir cada exemplo de contador, use `$Counter.CounterSamples` .</span><span class="sxs-lookup"><span data-stu-id="99f17-204">To display each counter sample, use `$Counter.CounterSamples`.</span></span>

```powershell
$Counter = Get-Counter -Counter "\Processor(*)\% Processor Time"
$Counter.CounterSamples | Where-Object { $_.CookedValue -lt "20" }
```

```Output
Path                                         InstanceName        CookedValue
----                                         ------------        -----------
\\Computer01\processor(0)\% processor time   0              12.6398025240208
\\Computer01\processor(1)\% processor time   1              15.7598095767344
```

<span data-ttu-id="99f17-205">`Get-Counter` usa o parâmetro **Counter** para especificar o contador `\Processor(*)\% Processor Time` .</span><span class="sxs-lookup"><span data-stu-id="99f17-205">`Get-Counter` uses the **Counter** parameter to specify the counter `\Processor(*)\% Processor Time`.</span></span> <span data-ttu-id="99f17-206">Os valores são armazenados na `$Counter` variável.</span><span class="sxs-lookup"><span data-stu-id="99f17-206">The values are stored in the `$Counter` variable.</span></span> <span data-ttu-id="99f17-207">Os objetos armazenados no `$Counter.CounterSamples` são enviados pelo pipeline.</span><span class="sxs-lookup"><span data-stu-id="99f17-207">The objects stored in `$Counter.CounterSamples` are sent down the pipeline.</span></span> <span data-ttu-id="99f17-208">`Where-Object` usa um bloco de script para comparar cada valor de objeto com um valor especificado de 20.</span><span class="sxs-lookup"><span data-stu-id="99f17-208">`Where-Object` uses a script block to compare each objects value against a specified value of 20.</span></span> <span data-ttu-id="99f17-209">O `$_.CookedValue` é uma variável para o objeto atual no pipeline.</span><span class="sxs-lookup"><span data-stu-id="99f17-209">The `$_.CookedValue` is a variable for the current object in the pipeline.</span></span> <span data-ttu-id="99f17-210">Os contadores com um **CookedValue** que é inferior a 20 são exibidos.</span><span class="sxs-lookup"><span data-stu-id="99f17-210">Counters with a **CookedValue** that is less than 20 are displayed.</span></span>

### <span data-ttu-id="99f17-211">Exemplo 14: classificar dados do contador de desempenho</span><span class="sxs-lookup"><span data-stu-id="99f17-211">Example 14: Sort performance counter data</span></span>

<span data-ttu-id="99f17-212">Este exemplo mostra como classificar dados do contador de desempenho.</span><span class="sxs-lookup"><span data-stu-id="99f17-212">This example shows how to sort performance counter data.</span></span> <span data-ttu-id="99f17-213">O exemplo localiza os processos no computador que estão usando a maior parte do tempo do processador durante o exemplo.</span><span class="sxs-lookup"><span data-stu-id="99f17-213">The example finds the processes on the computer that are using the most processor time during the sample.</span></span>

```powershell
$Procs = Get-Counter -Counter "\Process(*)\% Processor Time"
$Procs.CounterSamples | Sort-Object -Property CookedValue -Descending |
   Format-Table -Property Path, InstanceName, CookedValue -AutoSize
```

```Output
Path                                                         InstanceName             CookedValue
----                                                         ------------             -----------
\\Computer01\process(_total)\% processor time                _total              395.464129650573
\\Computer01\process(idle)\% processor time                  idle                389.356575524695
\\Computer01\process(mssense)\% processor time               mssense             3.05377706293879
\\Computer01\process(csrss#1)\% processor time               csrss               1.52688853146939
\\Computer01\process(microsoftedgecp#10)\% processor time    microsoftedgecp     1.52688853146939
\\Computer01\process(runtimebroker#5)\% processor time       runtimebroker                      0
\\Computer01\process(settingsynchost)\% processor time       settingsynchost                    0
\\Computer01\process(microsoftedgecp#16)\% processor time    microsoftedgecp                    0
```

<span data-ttu-id="99f17-214">`Get-Counter` usa o parâmetro **Counter** para especificar o `\Process(*)\% Processor Time` contador para todos os processos no computador local.</span><span class="sxs-lookup"><span data-stu-id="99f17-214">`Get-Counter` uses the **Counter** parameter to specify the `\Process(*)\% Processor Time` counter for all the processes on the local computer.</span></span> <span data-ttu-id="99f17-215">O resultado é armazenado na `$Procs` variável.</span><span class="sxs-lookup"><span data-stu-id="99f17-215">The result is stored in the `$Procs` variable.</span></span> <span data-ttu-id="99f17-216">A `$Procs` variável com a propriedade **comsamples** envia os objetos **PerformanceCounterSample** para baixo do pipeline.</span><span class="sxs-lookup"><span data-stu-id="99f17-216">The `$Procs` variable with the **CounterSamples** property sends the **PerformanceCounterSample** objects down the pipeline.</span></span> <span data-ttu-id="99f17-217">`Sort-Object` usa o parâmetro **Property** para classificar os objetos por **CookedValue** em ordem **decrescente** .</span><span class="sxs-lookup"><span data-stu-id="99f17-217">`Sort-Object` uses the **Property** parameter to sort the objects by **CookedValue** in **Descending** order.</span></span> <span data-ttu-id="99f17-218">`Format-Table` usa o parâmetro **Property** para selecionar as colunas para a saída.</span><span class="sxs-lookup"><span data-stu-id="99f17-218">`Format-Table` uses the **Property** parameter to select the columns for the output.</span></span> <span data-ttu-id="99f17-219">O parâmetro **AutoSize** ajusta as larguras das colunas para minimizar o truncamento.</span><span class="sxs-lookup"><span data-stu-id="99f17-219">The **AutoSize** parameter adjusts the column widths to minimize truncation.</span></span>

## <span data-ttu-id="99f17-220">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="99f17-220">PARAMETERS</span></span>

### <span data-ttu-id="99f17-221">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="99f17-221">-ComputerName</span></span>

<span data-ttu-id="99f17-222">Especifica um nome de computador ou uma matriz separada por vírgulas de nomes de computadores **remotos** .</span><span class="sxs-lookup"><span data-stu-id="99f17-222">Specifies one computer name or a comma-separated array of **remote** computer names.</span></span> <span data-ttu-id="99f17-223">Use o nome NetBIOS, um endereço IP ou o nome de domínio totalmente qualificado do computador.</span><span class="sxs-lookup"><span data-stu-id="99f17-223">Use the NetBIOS name, an IP address, or the computer's fully qualified domain name.</span></span>

<span data-ttu-id="99f17-224">Para obter dados do contador de desempenho do computador **local** , exclua o parâmetro **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="99f17-224">To get performance counter data from the **local** computer, exclude the **ComputerName** parameter.</span></span>
<span data-ttu-id="99f17-225">Para saída como um **ListSet** que contém a coluna **MachineName** , um ponto ( `.` ) indica o computador local.</span><span class="sxs-lookup"><span data-stu-id="99f17-225">For output such as a **ListSet** that contains the **MachineName** column, a dot (`.`) indicates the local computer.</span></span>

<span data-ttu-id="99f17-226">`Get-Counter` Não depende da comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99f17-226">`Get-Counter` doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="99f17-227">Você pode usar o parâmetro **ComputerName** mesmo que o computador não esteja configurado para executar comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="99f17-227">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99f17-228">-Continuous</span><span class="sxs-lookup"><span data-stu-id="99f17-228">-Continuous</span></span>

<span data-ttu-id="99f17-229">Quando o **contínuo** for especificado, `Get-Counter` Obtém amostras até que você pressione <kbd>Ctrl</kbd> + <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="99f17-229">When the **Continuous** is specified, `Get-Counter` gets samples until you press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span> <span data-ttu-id="99f17-230">Os exemplos são obtidos a cada segundo para cada contador de desempenho especificado.</span><span class="sxs-lookup"><span data-stu-id="99f17-230">Samples are obtained every second for each specified performance counter.</span></span> <span data-ttu-id="99f17-231">Use o parâmetro **SampleInterval** para aumentar o intervalo entre amostras contínuas.</span><span class="sxs-lookup"><span data-stu-id="99f17-231">Use the **SampleInterval** parameter to increase the interval between continuous samples.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99f17-232">-Contador</span><span class="sxs-lookup"><span data-stu-id="99f17-232">-Counter</span></span>

<span data-ttu-id="99f17-233">Especifica o caminho para um ou mais caminhos de contador.</span><span class="sxs-lookup"><span data-stu-id="99f17-233">Specifies the path to one or more counter paths.</span></span> <span data-ttu-id="99f17-234">Os caminhos são inseridos como uma matriz separada por vírgula, uma variável ou valores de um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="99f17-234">Paths are input as a comma-separated array, a variable, or values from a text file.</span></span> <span data-ttu-id="99f17-235">Você pode enviar cadeias de caracteres de caminho do contador para baixo no pipeline para `Get-Counter` .</span><span class="sxs-lookup"><span data-stu-id="99f17-235">You can send counter path strings down the pipeline to `Get-Counter`.</span></span>

<span data-ttu-id="99f17-236">Os caminhos de contador usam a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="99f17-236">Counter paths use the following syntax:</span></span>

`\\ComputerName\CounterSet(Instance)\CounterName`

`\CounterSet(Instance)\CounterName`

<span data-ttu-id="99f17-237">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="99f17-237">For example:</span></span>

`\\Server01\Processor(*)\% User Time`

`\Processor(*)\% User Time`

<span data-ttu-id="99f17-238">O `\\ComputerName` é opcional em um caminho de contador de desempenho.</span><span class="sxs-lookup"><span data-stu-id="99f17-238">The `\\ComputerName` is optional in a performance counter path.</span></span> <span data-ttu-id="99f17-239">Se o caminho do contador não incluir o nome do computador, o `Get-Counter` usará o computador local.</span><span class="sxs-lookup"><span data-stu-id="99f17-239">If the counter path doesn't include the computer name, `Get-Counter` uses the local computer.</span></span>

<span data-ttu-id="99f17-240">Um asterisco ( `*` ) na instância é um caractere curinga para obter todas as instâncias do contador.</span><span class="sxs-lookup"><span data-stu-id="99f17-240">An asterisk (`*`) in the instance is a wildcard character to get all instances of the counter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="99f17-241">-ListSet</span><span class="sxs-lookup"><span data-stu-id="99f17-241">-ListSet</span></span>

<span data-ttu-id="99f17-242">Lista os conjuntos de contadores de desempenho nos computadores.</span><span class="sxs-lookup"><span data-stu-id="99f17-242">Lists the performance counter sets on the computers.</span></span> <span data-ttu-id="99f17-243">Use um asterisco ( `*` ) para especificar todos os conjuntos de contadores.</span><span class="sxs-lookup"><span data-stu-id="99f17-243">Use an asterisk (`*`) to specify all counter sets.</span></span> <span data-ttu-id="99f17-244">Insira um nome ou uma cadeia de caracteres separada por vírgulas de nomes de conjuntos de contadores.</span><span class="sxs-lookup"><span data-stu-id="99f17-244">Enter one name or a comma-separated string of counter set names.</span></span> <span data-ttu-id="99f17-245">Você pode enviar nomes de conjuntos de contadores para baixo do pipeline.</span><span class="sxs-lookup"><span data-stu-id="99f17-245">You can send counter set names down the pipeline.</span></span>

<span data-ttu-id="99f17-246">Para obter um contador, defina os caminhos de contador formatados, use o parâmetro **ListSet** .</span><span class="sxs-lookup"><span data-stu-id="99f17-246">To get a counter sets formatted counter paths, use the **ListSet** parameter.</span></span> <span data-ttu-id="99f17-247">Os **caminhos** e as propriedades **PathsWithInstances** de cada conjunto de contadores contêm os caminhos de contador individuais formatados como uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="99f17-247">The **Paths** and **PathsWithInstances** properties of each counter set contain the individual counter paths formatted as a string.</span></span>

<span data-ttu-id="99f17-248">Você pode salvar as cadeias de caminho do contador em uma variável ou usar o pipeline para enviar a cadeia de caracteres para outro `Get-Counter` comando.</span><span class="sxs-lookup"><span data-stu-id="99f17-248">You can save the counter path strings in a variable or use the pipeline to send the string to another `Get-Counter` command.</span></span>

<span data-ttu-id="99f17-249">Por exemplo, para enviar cada caminho do contador de **processador** para `Get-Counter` :</span><span class="sxs-lookup"><span data-stu-id="99f17-249">For example to send each **Processor** counter path to `Get-Counter`:</span></span>

`Get-Counter -ListSet Processor | Get-Counter`

> [!NOTE]
> <span data-ttu-id="99f17-250">No PowerShell 7, `Get-Counter` o não pode recuperar a propriedade **Description** do conjunto de contadores.</span><span class="sxs-lookup"><span data-stu-id="99f17-250">In PowerShell 7, `Get-Counter` can't retrieve the **Description** property of the counter set.</span></span> <span data-ttu-id="99f17-251">A **Descrição** é definida como `$null` .</span><span class="sxs-lookup"><span data-stu-id="99f17-251">The **Description** is set to `$null`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ListSetSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="99f17-252">-MaxSamples</span><span class="sxs-lookup"><span data-stu-id="99f17-252">-MaxSamples</span></span>

<span data-ttu-id="99f17-253">Especifica o número de amostras para obter de cada contador de desempenho especificado.</span><span class="sxs-lookup"><span data-stu-id="99f17-253">Specifies the number of samples to get from each specified performance counter.</span></span> <span data-ttu-id="99f17-254">Para obter um fluxo constante de exemplos, use o parâmetro **Continuous** .</span><span class="sxs-lookup"><span data-stu-id="99f17-254">To get a constant stream of samples, use the **Continuous** parameter.</span></span>

<span data-ttu-id="99f17-255">Se o parâmetro **MaxSamples** não for especificado, apenas obterá `Get-Counter` um exemplo para cada contador especificado.</span><span class="sxs-lookup"><span data-stu-id="99f17-255">If the **MaxSamples** parameter isn't specified, `Get-Counter` only gets one sample for each specified counter.</span></span>

<span data-ttu-id="99f17-256">Para coletar um grande conjunto de dados, execute `Get-Counter` como um trabalho em segundo plano do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99f17-256">To collect a large data set, run `Get-Counter` as a PowerShell background job.</span></span> <span data-ttu-id="99f17-257">Para obter mais informações, consulte [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="99f17-257">For more information, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md).</span></span>

```yaml
Type: System.Int64
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99f17-258">-SampleInterval</span><span class="sxs-lookup"><span data-stu-id="99f17-258">-SampleInterval</span></span>

<span data-ttu-id="99f17-259">Especifica o número de segundos entre as amostras para cada contador de desempenho especificado.</span><span class="sxs-lookup"><span data-stu-id="99f17-259">Specifies the number of seconds between samples for each specified performance counter.</span></span> <span data-ttu-id="99f17-260">Se o parâmetro **SampleInterval** não for especificado, o `Get-Counter` usará um intervalo de um segundo.</span><span class="sxs-lookup"><span data-stu-id="99f17-260">If the **SampleInterval** parameter isn't specified, `Get-Counter` uses a one-second interval.</span></span>

```yaml
Type: System.Int32
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99f17-261">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="99f17-261">CommonParameters</span></span>

<span data-ttu-id="99f17-262">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="99f17-262">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="99f17-263">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="99f17-263">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="99f17-264">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="99f17-264">INPUTS</span></span>

### <span data-ttu-id="99f17-265">System.String[]</span><span class="sxs-lookup"><span data-stu-id="99f17-265">System.String[]</span></span>

<span data-ttu-id="99f17-266">`Get-Counter` aceita a entrada de pipeline para caminhos de contador e nomes de conjuntos de contadores.</span><span class="sxs-lookup"><span data-stu-id="99f17-266">`Get-Counter` accepts pipeline input for counter paths and counter set names.</span></span>

## <span data-ttu-id="99f17-267">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="99f17-267">OUTPUTS</span></span>

### <span data-ttu-id="99f17-268">Microsoft. PowerShell. Commands. getcontador. CounterSet, Microsoft. PowerShell. Commands. getcounterer. PerformanceCounterSampleSet, Microsoft. PowerShell. Commands. GetCounter. PerformanceCounterSample</span><span class="sxs-lookup"><span data-stu-id="99f17-268">Microsoft.PowerShell.Commands.GetCounter.CounterSet, Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet, Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSample</span></span>

<span data-ttu-id="99f17-269">Para exibir as propriedades de um objeto, envie a saída para baixo do pipeline para `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="99f17-269">To view an object's properties, send the output down the pipeline to `Get-Member`.</span></span> <span data-ttu-id="99f17-270">Os tipos de objeto que são saída são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="99f17-270">The object types that are output are as follows:</span></span>

<span data-ttu-id="99f17-271">Parâmetro **ListSet** : **Microsoft. PowerShell. Commands. GetCounter**</span><span class="sxs-lookup"><span data-stu-id="99f17-271">**ListSet** parameter: **Microsoft.PowerShell.Commands.GetCounter.CounterSet**</span></span>

<span data-ttu-id="99f17-272">Parâmetro do **contador** : **Microsoft. PowerShell. Commands. GetCounter. PerformanceCounterSampleSet**</span><span class="sxs-lookup"><span data-stu-id="99f17-272">**Counter** parameter: **Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet**</span></span>

<span data-ttu-id="99f17-273">Propriedade de **Contraamostrações** : **Microsoft. PowerShell. Commands. getcounterer. PerformanceCounterSample**</span><span class="sxs-lookup"><span data-stu-id="99f17-273">**CounterSamples** property: **Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSample**</span></span>

## <span data-ttu-id="99f17-274">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="99f17-274">NOTES</span></span>

<span data-ttu-id="99f17-275">Se nenhum parâmetro for especificado, `Get-Counter` Obtém um exemplo para cada contador de desempenho especificado.</span><span class="sxs-lookup"><span data-stu-id="99f17-275">If no parameters are specified, `Get-Counter` gets one sample for each specified performance counter.</span></span> <span data-ttu-id="99f17-276">Use os parâmetros **MaxSamples** e **Continuous** para obter mais exemplos.</span><span class="sxs-lookup"><span data-stu-id="99f17-276">Use the **MaxSamples** and **Continuous** parameters to get more samples.</span></span>

<span data-ttu-id="99f17-277">`Get-Counter` usa um intervalo de um segundo entre exemplos.</span><span class="sxs-lookup"><span data-stu-id="99f17-277">`Get-Counter` uses a one-second interval between samples.</span></span> <span data-ttu-id="99f17-278">Use o parâmetro **SampleInterval** para aumentar o intervalo.</span><span class="sxs-lookup"><span data-stu-id="99f17-278">Use the **SampleInterval** parameter to increase the interval.</span></span>

<span data-ttu-id="99f17-279">Os valores **MaxSamples** e **SampleInterval** se aplicam a todos os contadores em cada computador no comando.</span><span class="sxs-lookup"><span data-stu-id="99f17-279">The **MaxSamples** and **SampleInterval** values apply to all the counters on each computer in the command.</span></span> <span data-ttu-id="99f17-280">Para definir valores diferentes para contadores diferentes, insira `Get-Counter` comandos separados.</span><span class="sxs-lookup"><span data-stu-id="99f17-280">To set different values for different counters, enter separate `Get-Counter` commands.</span></span>

<span data-ttu-id="99f17-281">No PowerShell 7, ao usar o parâmetro **ListSet** , `Get-Counter` o não pode recuperar a propriedade **Description** do conjunto de contadores.</span><span class="sxs-lookup"><span data-stu-id="99f17-281">In PowerShell 7, when using the **ListSet** parameter, `Get-Counter` can't retrieve the **Description** property of the counter set.</span></span> <span data-ttu-id="99f17-282">A **Descrição** é definida como `$null` .</span><span class="sxs-lookup"><span data-stu-id="99f17-282">The **Description** is set to `$null`.</span></span>

## <span data-ttu-id="99f17-283">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="99f17-283">RELATED LINKS</span></span>

[<span data-ttu-id="99f17-284">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="99f17-284">about_Automatic_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="99f17-285">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="99f17-285">about_Jobs</span></span>](../Microsoft.PowerShell.Core/About/about_Jobs.md)

[<span data-ttu-id="99f17-286">Format-List</span><span class="sxs-lookup"><span data-stu-id="99f17-286">Format-List</span></span>](../Microsoft.PowerShell.Utility/Format-List.md)

[<span data-ttu-id="99f17-287">Format-Table</span><span class="sxs-lookup"><span data-stu-id="99f17-287">Format-Table</span></span>](../Microsoft.PowerShell.Utility/Format-Table.md)

[<span data-ttu-id="99f17-288">Get-Member</span><span class="sxs-lookup"><span data-stu-id="99f17-288">Get-Member</span></span>](../Microsoft.PowerShell.Utility/Get-Member.md)

[<span data-ttu-id="99f17-289">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="99f17-289">Receive-Job</span></span>](../Microsoft.PowerShell.Core/Receive-Job.md)

[<span data-ttu-id="99f17-290">Start-Job</span><span class="sxs-lookup"><span data-stu-id="99f17-290">Start-Job</span></span>](../Microsoft.PowerShell.Core/Start-Job.md)

[<span data-ttu-id="99f17-291">Where-Object</span><span class="sxs-lookup"><span data-stu-id="99f17-291">Where-Object</span></span>](..//Microsoft.PowerShell.Core/Where-Object.md)

