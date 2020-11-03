---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 10/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/export-counter?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Counter
ms.openlocfilehash: 54498eb504a1d13a5b96a2583b5e5d6e4c08735e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195528"
---
# <span data-ttu-id="33bc2-103">Export-Counter</span><span class="sxs-lookup"><span data-stu-id="33bc2-103">Export-Counter</span></span>

## <span data-ttu-id="33bc2-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="33bc2-104">SYNOPSIS</span></span>
<span data-ttu-id="33bc2-105">Exporta dados do contador de desempenho para arquivos de log.</span><span class="sxs-lookup"><span data-stu-id="33bc2-105">Exports performance counter data to log files.</span></span>

## <span data-ttu-id="33bc2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="33bc2-106">SYNTAX</span></span>

```
Export-Counter [-Path] <String> [-FileFormat <String>] [-MaxSize <UInt32>]
 -InputObject <PerformanceCounterSampleSet[]> [-Force] [-Circular] [<CommonParameters>]
```

## <span data-ttu-id="33bc2-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="33bc2-107">DESCRIPTION</span></span>

<span data-ttu-id="33bc2-108">O `Export-Counter` cmdlet exporta dados do contador de desempenho (objetos PerformanceCounterSampleSet) para arquivos de log em log de desempenho binário (. blg), valores separados por vírgulas (. csv) ou formato de valor separado por tabulação (. tsv).</span><span class="sxs-lookup"><span data-stu-id="33bc2-108">The `Export-Counter` cmdlet exports performance counter data (PerformanceCounterSampleSet objects) to log files in binary performance log (.blg), comma-separated value (.csv), or tab-separated value (.tsv) format.</span></span> <span data-ttu-id="33bc2-109">Você usa este cmdlet para registrar dados do contador de desempenho.</span><span class="sxs-lookup"><span data-stu-id="33bc2-109">You use this cmdlet to log performance counter data.</span></span>

<span data-ttu-id="33bc2-110">O `Export-Counter` cmdlet é projetado para exportar dados que são retornados pelos `Get-Counter` `Import-Counter` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="33bc2-110">The `Export-Counter` cmdlet is designed to export data that is returned by the `Get-Counter` and `Import-Counter` cmdlets.</span></span>

<span data-ttu-id="33bc2-111">Esse cmdlet é executado somente no Windows 7, no Windows Server 2008 R2 e em versões posteriores do Windows.</span><span class="sxs-lookup"><span data-stu-id="33bc2-111">This cmdlet runs only on Windows 7, Windows Server 2008 R2, and later versions of Windows.</span></span>

## <span data-ttu-id="33bc2-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="33bc2-112">EXAMPLES</span></span>

### <span data-ttu-id="33bc2-113">EXEMPLO 1: exportar dados do contador para um arquivo</span><span class="sxs-lookup"><span data-stu-id="33bc2-113">EXAMPLE 1: Export counter data to a file</span></span>

<span data-ttu-id="33bc2-114">Este exemplo exporta os dados do contador para um arquivo BLG.</span><span class="sxs-lookup"><span data-stu-id="33bc2-114">This example exports counter data to a BLG file.</span></span>

```powershell
Get-Counter "\Processor(*)\% Processor Time" | Export-Counter -Path $home\Counters.blg
```

<span data-ttu-id="33bc2-115">O comando usa o `Get-Counter` cmdlet para coletar dados de tempo do processador.</span><span class="sxs-lookup"><span data-stu-id="33bc2-115">The command uses the `Get-Counter` cmdlet to collect processor time data.</span></span> <span data-ttu-id="33bc2-116">Ele usa um operador de pipeline (|) para enviar os dados para o `Export-Counter` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="33bc2-116">It uses a pipeline operator (|) to send the data to the `Export-Counter` cmdlet.</span></span> <span data-ttu-id="33bc2-117">O `Export-Counter` comando usa a variável **Path** para especificar o arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="33bc2-117">The `Export-Counter` command uses the **Path** variable to specify the output file.</span></span>

<span data-ttu-id="33bc2-118">Como o conjunto de dados pode ser muito grande, este exemplo envia os dados para `Export-Counter` por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="33bc2-118">Because the data set might be very large, this example sends the data to `Export-Counter` through the pipeline.</span></span> <span data-ttu-id="33bc2-119">Se os dados foram salvos em uma variável, você pode usar uma quantidade desproporcional de memória.</span><span class="sxs-lookup"><span data-stu-id="33bc2-119">If the data were saved in a variable, you might use a disproportionate amount of memory.</span></span>

### <span data-ttu-id="33bc2-120">Exemplo 2: exportar um arquivo para um formato de arquivo de contador</span><span class="sxs-lookup"><span data-stu-id="33bc2-120">Example 2: Export a file to a counter file format</span></span>

<span data-ttu-id="33bc2-121">Este exemplo converte um arquivo CSV em um formato de BLG de dados de contador.</span><span class="sxs-lookup"><span data-stu-id="33bc2-121">This example converts a CSV file to a counter data BLG format.</span></span>

<span data-ttu-id="33bc2-122">O `Import-Counter` cmdlet importa dados do contador de desempenho do `Threads.csv` arquivo.</span><span class="sxs-lookup"><span data-stu-id="33bc2-122">The `Import-Counter` cmdlet imports performance counter data from the `Threads.csv` file.</span></span> <span data-ttu-id="33bc2-123">O exemplo supõe que esse arquivo foi exportado anteriormente usando o `Export-Counter` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="33bc2-123">The example presumes that this file was previously exported by using the `Export-Counter` cmdlet.</span></span> <span data-ttu-id="33bc2-124">Um operador de pipeline ( `|` ) envia os dados importados para o `Export-Counter` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="33bc2-124">A pipeline operator (`|`) sends the imported data to the `Export-Counter` cmdlet.</span></span> <span data-ttu-id="33bc2-125">O comando usa o parâmetro **Path** para especificar o local do arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="33bc2-125">The command uses the **Path** parameter to specify the location of the output file.</span></span> <span data-ttu-id="33bc2-126">Ele usa os parâmetros **circular** e **MaxSize** para direcionar o `Export-Counter` cmdlet para criar um log circular que encapsula em 1 GB.</span><span class="sxs-lookup"><span data-stu-id="33bc2-126">It uses the **Circular** and **MaxSize** parameters to direct the `Export-Counter` cmdlet to create a circular log that wraps at 1 GB.</span></span> <span data-ttu-id="33bc2-127">O parâmetro **MaxSize** é expresso em megabytes.</span><span class="sxs-lookup"><span data-stu-id="33bc2-127">The **MaxSize** parameter is expressed in megabytes.</span></span>

```powershell
$1GBInMB = 1024 # 1GB = 1024MB
Import-Counter Threads.csv | Export-Counter -Path ThreadTest.blg -Circular -MaxSize $1GBInMB
```

### <span data-ttu-id="33bc2-128">Exemplo 3: obter dados do contador de um computador remoto e salvar os dados em um arquivo</span><span class="sxs-lookup"><span data-stu-id="33bc2-128">Example 3: Get counter data from a remote computer and save the data to a file</span></span>

<span data-ttu-id="33bc2-129">Este exemplo mostra como obter dados do contador de desempenho de um computador remoto e salva os dados em um arquivo no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="33bc2-129">This example shows how to get performance counter data from a remote computer and save the data in a file on the remote computer.</span></span>

<span data-ttu-id="33bc2-130">O primeiro comando usa o `Get-Counter` cmdlet para coletar dados do contador de conjunto de trabalho do Server01, um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="33bc2-130">The first command uses the `Get-Counter` cmdlet to collect working set counter data from Server01, a remote computer.</span></span> <span data-ttu-id="33bc2-131">O comando salva os dados na `$C` variável.</span><span class="sxs-lookup"><span data-stu-id="33bc2-131">The command saves the data in the `$C` variable.</span></span>

<span data-ttu-id="33bc2-132">O segundo comando usa um operador de pipeline ( `|` ) para enviar os dados `$C` para o `Export-Counter` cmdlet, que o salva no `Workingset.blg` arquivo no compartilhamento de desempenho do computador Server01.</span><span class="sxs-lookup"><span data-stu-id="33bc2-132">The second command uses a pipeline operator (`|`) to send the data in `$C` to the `Export-Counter` cmdlet, which saves it in the `Workingset.blg` file in the Perf share of the Server01 computer.</span></span>

```powershell
$C = Get-Counter -ComputerName Server01 -Counter "\Process(*)\Working Set - Private" -MaxSamples $C | Export-Counter -Path \\Server01\Perf\WorkingSet.blg
```

```Output
20
```

### <span data-ttu-id="33bc2-133">Exemplo 4: registrar novamente os dados existentes</span><span class="sxs-lookup"><span data-stu-id="33bc2-133">Example 4: Re-log existing data</span></span>

<span data-ttu-id="33bc2-134">Este exemplo mostra como usar os `Import-Counter` `Export-Counter` cmdlets e para registrar novamente os dados existentes.</span><span class="sxs-lookup"><span data-stu-id="33bc2-134">This example shows how to use the `Import-Counter` and `Export-Counter` cmdlets to re-log existing data.</span></span>

<span data-ttu-id="33bc2-135">O primeiro comando usa o `Import-Counter` cmdlet para importar dados do contador de desempenho do log espaço em disco. blg.</span><span class="sxs-lookup"><span data-stu-id="33bc2-135">The first command uses the `Import-Counter` cmdlet to import performance counter data from the DiskSpace.blg log.</span></span> <span data-ttu-id="33bc2-136">Ele salva os dados na `$All` variável.</span><span class="sxs-lookup"><span data-stu-id="33bc2-136">It saves the data in the `$All` variable.</span></span> <span data-ttu-id="33bc2-137">Esse arquivo contém exemplos do \% contador "espaço livre do LogicalDisk" em mais de 200 computadores remotos na empresa.</span><span class="sxs-lookup"><span data-stu-id="33bc2-137">This file contains samples of the "LogicalDisk\% Free Space" counter on more than 200 remote computers in the enterprise.</span></span>

<span data-ttu-id="33bc2-138">O segundo comando usa o `Where-Object` cmdlet para selecionar objetos com **CookedValue** de menos de 15 (porcentagem).</span><span class="sxs-lookup"><span data-stu-id="33bc2-138">The second command uses the `Where-Object` cmdlet to select objects with **CookedValue** of less than 15 (percent).</span></span> <span data-ttu-id="33bc2-139">O comando salva os resultados na `$LowSpace` variável.</span><span class="sxs-lookup"><span data-stu-id="33bc2-139">The command saves the results in the `$LowSpace` variable.</span></span>

<span data-ttu-id="33bc2-140">O terceiro comando usa um operador de pipeline ( `|` ) para enviar os dados na `$LowSpace` variável para o `Export-Counter` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="33bc2-140">The third command uses a pipeline operator (`|`) to send the data in the `$LowSpace` variable to the `Export-Counter` cmdlet.</span></span> <span data-ttu-id="33bc2-141">O comando usa o parâmetro **Path** para indicar que os dados selecionados devem ser registrados em log no arquivo LowDiskSpace.blg.</span><span class="sxs-lookup"><span data-stu-id="33bc2-141">The command uses the **Path** parameter to indicate that the selected data should be logged in the LowDiskSpace.blg file.</span></span>

```powershell
$All = Import-Counter DiskSpace.blg
$LowSpace = $All | Where-Object {$_.CounterSamples.CookedValue -lt 15}
$LowSpace | Export-Counter -Path LowDiskSpace.blg
```

## <span data-ttu-id="33bc2-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="33bc2-142">PARAMETERS</span></span>

### <span data-ttu-id="33bc2-143">-Circular</span><span class="sxs-lookup"><span data-stu-id="33bc2-143">-Circular</span></span>

<span data-ttu-id="33bc2-144">Indica que o arquivo de saída é um log circular com o formato PEPS (primeiro a entrar, primeiro a sair).</span><span class="sxs-lookup"><span data-stu-id="33bc2-144">Indicates that the output file is a circular log with first in, first out (FIFO) format.</span></span>
<span data-ttu-id="33bc2-145">Ao incluir esse parâmetro, o parâmetro **MaxSize** é necessário.</span><span class="sxs-lookup"><span data-stu-id="33bc2-145">When you include this parameter, the **MaxSize** parameter is required.</span></span>

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

### <span data-ttu-id="33bc2-146">-FileFormat</span><span class="sxs-lookup"><span data-stu-id="33bc2-146">-FileFormat</span></span>

<span data-ttu-id="33bc2-147">Especifica o formato de saída do arquivo de log de saída.</span><span class="sxs-lookup"><span data-stu-id="33bc2-147">Specifies the output format of the output log file.</span></span>

<span data-ttu-id="33bc2-148">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="33bc2-148">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="33bc2-149">CSV</span><span class="sxs-lookup"><span data-stu-id="33bc2-149">CSV</span></span>
- <span data-ttu-id="33bc2-150">TSV</span><span class="sxs-lookup"><span data-stu-id="33bc2-150">TSV</span></span>
- <span data-ttu-id="33bc2-151">BLG</span><span class="sxs-lookup"><span data-stu-id="33bc2-151">BLG</span></span>

<span data-ttu-id="33bc2-152">O valor padrão é BLG.</span><span class="sxs-lookup"><span data-stu-id="33bc2-152">The default value is BLG.</span></span>

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

### <span data-ttu-id="33bc2-153">-Force</span><span class="sxs-lookup"><span data-stu-id="33bc2-153">-Force</span></span>

<span data-ttu-id="33bc2-154">Sobrescreve e substitui um arquivo existente se existir um no local especificado pelo parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="33bc2-154">Overwrites and replaces an existing file if one exists in the location specified by the **Path** parameter.</span></span>

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

### <span data-ttu-id="33bc2-155">-InputObject</span><span class="sxs-lookup"><span data-stu-id="33bc2-155">-InputObject</span></span>

<span data-ttu-id="33bc2-156">Especifica, como uma matriz, os dados do contador a serem exportados.</span><span class="sxs-lookup"><span data-stu-id="33bc2-156">Specifies, as an array, the counter data to export.</span></span> <span data-ttu-id="33bc2-157">Insira uma variável que contém os dados ou um comando que obtém os dados, como o `Get-Counter` cmdlet ou `Import-Counter` .</span><span class="sxs-lookup"><span data-stu-id="33bc2-157">Enter a variable that contains the data or a command that gets the data, such as the `Get-Counter` or `Import-Counter` cmdlet.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="33bc2-158">-MaxSize</span><span class="sxs-lookup"><span data-stu-id="33bc2-158">-MaxSize</span></span>

<span data-ttu-id="33bc2-159">Especifica o tamanho máximo do arquivo de saída em megabytes (MB).</span><span class="sxs-lookup"><span data-stu-id="33bc2-159">Specifies the maximum size of the output file in megabytes (MB).</span></span>

<span data-ttu-id="33bc2-160">Se o parâmetro **circular** for especificado, quando o arquivo de log atingir o tamanho máximo especificado, as entradas mais antigas serão excluídas à medida que mais novas forem adicionadas.</span><span class="sxs-lookup"><span data-stu-id="33bc2-160">If the **Circular** parameter is specified, then when the log file reaches the specified maximum size, the oldest entries are deleted as newer ones are added.</span></span> <span data-ttu-id="33bc2-161">Se o parâmetro **circular** não for especificado, quando o arquivo de log atingir o tamanho máximo especificado, nenhum dado novo será adicionado e o cmdlet gerará um erro de não finalização.</span><span class="sxs-lookup"><span data-stu-id="33bc2-161">If the **Circular** parameter is not specified, then when the log file reaches the specified maximum size, no new data is added and the cmdlet generates a non-terminating error.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="33bc2-162">-Path</span><span class="sxs-lookup"><span data-stu-id="33bc2-162">-Path</span></span>

<span data-ttu-id="33bc2-163">Especifica o caminho e o nome do arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="33bc2-163">Specifies the path and file name of the output file.</span></span> <span data-ttu-id="33bc2-164">Insira um caminho relativo ou absoluto no computador local ou um caminho UNC (Convenção de nomenclatura uniforme) para um computador remoto, como `\\Computer\Share\file.blg` .</span><span class="sxs-lookup"><span data-stu-id="33bc2-164">Enter a relative or absolute path on the local computer, or a Uniform Naming Convention (UNC) path to a remote computer, such as `\\Computer\Share\file.blg`.</span></span> <span data-ttu-id="33bc2-165">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="33bc2-165">This parameter is required.</span></span>

<span data-ttu-id="33bc2-166">O formato de arquivo é determinado pelo valor do parâmetro **FileFormat** , não pela extensão de nome de arquivo no caminho.</span><span class="sxs-lookup"><span data-stu-id="33bc2-166">The file format is determined by the value of the **FileFormat** parameter, not by the file name extension in the path.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="33bc2-167">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="33bc2-167">CommonParameters</span></span>

<span data-ttu-id="33bc2-168">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="33bc2-168">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="33bc2-169">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="33bc2-169">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="33bc2-170">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="33bc2-170">INPUTS</span></span>

### <span data-ttu-id="33bc2-171">Microsoft. PowerShell. Commands. getcounterer. PerformanceCounterSampleSet</span><span class="sxs-lookup"><span data-stu-id="33bc2-171">Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet</span></span>

<span data-ttu-id="33bc2-172">Você pode canalizar dados do contador de desempenho do `Get-Counter` ou `Import-Counter` para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="33bc2-172">You can pipe performance counter data from `Get-Counter` or `Import-Counter` to this cmdlet.</span></span>

## <span data-ttu-id="33bc2-173">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="33bc2-173">OUTPUTS</span></span>

### <span data-ttu-id="33bc2-174">Nenhum</span><span class="sxs-lookup"><span data-stu-id="33bc2-174">None</span></span>

## <span data-ttu-id="33bc2-175">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="33bc2-175">NOTES</span></span>

<span data-ttu-id="33bc2-176">O gerador de arquivo de log espera que todos os objetos de entrada tenham o mesmo caminho de contador e que os objetos sejam organizados em ordem temporal crescente.</span><span class="sxs-lookup"><span data-stu-id="33bc2-176">The log file generator expects that all input objects have the same counter path and that the objects are arranged in ascending time order.</span></span>

<span data-ttu-id="33bc2-177">O caminho e o tipo de contador do primeiro objeto de entrada determina as propriedades registradas no arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="33bc2-177">The counter type and path of the first input object determines the properties recorded in the log file.</span></span> <span data-ttu-id="33bc2-178">Se outros objetos de entrada não tiverem um valor para uma propriedade gravada, o campo de propriedade fica vazio.</span><span class="sxs-lookup"><span data-stu-id="33bc2-178">If other input objects do not have a value for a recorded property, the property field is empty.</span></span> <span data-ttu-id="33bc2-179">Se os objetos têm valores de propriedade não registrados, os valores de propriedade extra são ignorados.</span><span class="sxs-lookup"><span data-stu-id="33bc2-179">If the objects have property values that were not recorded, the extra property values are ignored.</span></span>

<span data-ttu-id="33bc2-180">O monitor de desempenho pode não ser capaz de ler todos os logs `Export-Counter` gerados.</span><span class="sxs-lookup"><span data-stu-id="33bc2-180">Performance Monitor might not be able to read all logs that `Export-Counter` generates.</span></span> <span data-ttu-id="33bc2-181">Por exemplo, o monitor de desempenho requer que todos os objetos tenham o mesmo caminho e que todos os objetos sejam separados pelo mesmo intervalo de tempo.</span><span class="sxs-lookup"><span data-stu-id="33bc2-181">For instance, Performance Monitor requires that all objects have the same path and that all objects are separated by the same time interval.</span></span>

<span data-ttu-id="33bc2-182">O `Import-Counter` cmdlet não tem um parâmetro **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="33bc2-182">The `Import-Counter` cmdlet does not have a **ComputerName** parameter.</span></span> <span data-ttu-id="33bc2-183">No entanto, se o computador estiver configurado para o Windows PowerShell remoto, você poderá usar o `Invoke-Command` cmdlet para executar um `Import-Counter` comando em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="33bc2-183">However, if the computer is configured for remote Windows PowerShell Windows PowerShell, you can use the `Invoke-Command` cmdlet to run an `Import-Counter` command on a remote computer.</span></span>

## <span data-ttu-id="33bc2-184">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="33bc2-184">RELATED LINKS</span></span>

[<span data-ttu-id="33bc2-185">Get-Counter</span><span class="sxs-lookup"><span data-stu-id="33bc2-185">Get-Counter</span></span>](Get-Counter.md)

[<span data-ttu-id="33bc2-186">Import-Counter</span><span class="sxs-lookup"><span data-stu-id="33bc2-186">Import-Counter</span></span>](Import-Counter.md)
