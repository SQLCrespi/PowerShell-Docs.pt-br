---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 1/7/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-csv?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Csv
ms.openlocfilehash: cb58276c8582f9cd1f88a114baae2ce5d0039f45
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93193078"
---
# <span data-ttu-id="1e6d0-103">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="1e6d0-103">Export-Csv</span></span>

## <span data-ttu-id="1e6d0-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="1e6d0-104">SYNOPSIS</span></span>
<span data-ttu-id="1e6d0-105">Converte objetos em uma série de cadeias de caracteres de valores separados por vírgulas (CSV) e salva as cadeias de caracteres em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-105">Converts objects into a series of comma-separated value (CSV) strings and saves the strings to a file.</span></span>

## <span data-ttu-id="1e6d0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1e6d0-106">SYNTAX</span></span>

### <span data-ttu-id="1e6d0-107">Delimitador (padrão)</span><span class="sxs-lookup"><span data-stu-id="1e6d0-107">Delimiter (Default)</span></span>

```
Export-Csv -InputObject <PSObject> [[-Path] <String>] [-LiteralPath <String>] [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-Append] [[-Delimiter] <Char>] [-IncludeTypeInformation]
 [-NoTypeInformation] [-QuoteFields <String[]>] [-UseQuotes <QuoteKind>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="1e6d0-108">parâmetro</span><span class="sxs-lookup"><span data-stu-id="1e6d0-108">UseCulture</span></span>

```
Export-Csv -InputObject <PSObject> [[-Path] <String>] [-LiteralPath <String>] [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-Append] [-UseCulture] [-IncludeTypeInformation] [-NoTypeInformation]
 [-QuoteFields <String[]>] [-UseQuotes <QuoteKind>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="1e6d0-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1e6d0-109">DESCRIPTION</span></span>

<span data-ttu-id="1e6d0-110">O `Export-CSV` cmdlet cria um arquivo CSV dos objetos que você envia.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-110">The `Export-CSV` cmdlet creates a CSV file of the objects that you submit.</span></span> <span data-ttu-id="1e6d0-111">Cada objeto é uma linha que inclui uma lista separada por vírgulas dos valores de Propriedade do objeto.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-111">Each object is a row that includes a comma-separated list of the object's property values.</span></span> <span data-ttu-id="1e6d0-112">Você pode usar o `Export-CSV` cmdlet para criar planilhas e compartilhar dados com programas que aceitam arquivos CSV como entrada.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-112">You can use the `Export-CSV` cmdlet to create spreadsheets and share data with programs that accept CSV files as input.</span></span>

<span data-ttu-id="1e6d0-113">Não formate objetos antes de enviá-los para o `Export-CSV` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-113">Do not format objects before sending them to the `Export-CSV` cmdlet.</span></span> <span data-ttu-id="1e6d0-114">Se `Export-CSV` o receber objetos formatados, o arquivo CSV conterá as propriedades de formato em vez das propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-114">If `Export-CSV` receives formatted objects the CSV file contains the format properties rather than the object properties.</span></span> <span data-ttu-id="1e6d0-115">Para exportar apenas as propriedades selecionadas de um objeto, use o `Select-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-115">To export only selected properties of an object, use the `Select-Object` cmdlet.</span></span>

## <span data-ttu-id="1e6d0-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="1e6d0-116">EXAMPLES</span></span>

### <span data-ttu-id="1e6d0-117">Exemplo 1: exportar Propriedades do processo para um arquivo CSV</span><span class="sxs-lookup"><span data-stu-id="1e6d0-117">Example 1: Export process properties to a CSV file</span></span>

<span data-ttu-id="1e6d0-118">Este exemplo seleciona objetos de **processo** com propriedades específicas, exporta os objetos para um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-118">This example selects **Process** objects with specific properties, exports the objects to a CSV file.</span></span>

```powershell
Get-Process -Name WmiPrvSE | Select-Object -Property BasePriority,Id,SessionId,WorkingSet |
  Export-Csv -Path .\WmiData.csv -NoTypeInformation
Import-Csv -Path .\WmiData.csv
```

```Output
BasePriority Id    SessionId WorkingSet
------------ --    --------- ----------
8            976   0         20267008
8            2292  0         36786176
8            3816  0         30351360
8            8604  0         15011840
8            10008 0         8830976
8            11764 0         14237696
8            54632 0         9502720
```

<span data-ttu-id="1e6d0-119">O `Get-Process` cmdlet obtém os objetos de **processo** .</span><span class="sxs-lookup"><span data-stu-id="1e6d0-119">The `Get-Process` cmdlet gets the **Process** objects.</span></span> <span data-ttu-id="1e6d0-120">O parâmetro **Name** filtra a saída para incluir apenas os objetos de processo do WmiPrvSE.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-120">The **Name** parameter filters the output to include only the WmiPrvSE process objects.</span></span> <span data-ttu-id="1e6d0-121">Os objetos de processo são enviados por meio do pipeline para o `Select-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-121">The process objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="1e6d0-122">`Select-Object` usa o parâmetro **Property** para selecionar um subconjunto das propriedades do objeto de processo.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-122">`Select-Object` uses the **Property** parameter to select a subset of process object properties.</span></span> <span data-ttu-id="1e6d0-123">Os objetos de processo são enviados por meio do pipeline para o `Export-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-123">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="1e6d0-124">`Export-Csv` Converte os objetos de processo em uma série de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-124">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="1e6d0-125">O parâmetro **path** especifica que o arquivo de WmiData.csv é salvo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-125">The **Path** parameter specifies that the WmiData.csv file is saved in the current directory.</span></span> <span data-ttu-id="1e6d0-126">O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-126">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="1e6d0-127">O `Import-Csv` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-127">The `Import-Csv` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="1e6d0-128">Exemplo 2: exportar processos para um arquivo delimitado por vírgula</span><span class="sxs-lookup"><span data-stu-id="1e6d0-128">Example 2: Export processes to a comma-delimited file</span></span>

<span data-ttu-id="1e6d0-129">Este exemplo obtém objetos de **processo** e exporta os objetos para um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-129">This example gets **Process** objects and exports the objects to a CSV file.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","511","2203597099008","35364864","21979136","30048", ...
```

<span data-ttu-id="1e6d0-130">O `Get-Process` cmdlet obtém objetos de **processo** .</span><span class="sxs-lookup"><span data-stu-id="1e6d0-130">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="1e6d0-131">Os objetos de processo são enviados por meio do pipeline para o `Export-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-131">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="1e6d0-132">`Export-Csv` Converte os objetos de processo em uma série de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-132">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="1e6d0-133">O parâmetro **path** especifica que o arquivo de Processes.csv é salvo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-133">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="1e6d0-134">O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-134">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="1e6d0-135">O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-135">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="1e6d0-136">Exemplo 3: exportar processos para um arquivo delimitado por ponto e vírgula</span><span class="sxs-lookup"><span data-stu-id="1e6d0-136">Example 3: Export processes to a semicolon delimited file</span></span>

<span data-ttu-id="1e6d0-137">Este exemplo obtém objetos de **processo** e exporta os objetos para um arquivo com um delimitador de ponto-e-vírgula.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-137">This example gets **Process** objects and exports the objects to a file with a semicolon delimiter.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -Delimiter ';' -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name";"SI";"Handles";"VM";"WS";"PM";"NPM";"Path";"Parent";"Company";"CPU";"FileVersion"; ...
"ApplicationFrameHost";"4";"509";"2203595321344";"34807808";"21770240";"29504"; ...
```

<span data-ttu-id="1e6d0-138">O `Get-Process` cmdlet obtém objetos de **processo** .</span><span class="sxs-lookup"><span data-stu-id="1e6d0-138">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="1e6d0-139">Os objetos de processo são enviados por meio do pipeline para o `Export-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-139">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="1e6d0-140">`Export-Csv` Converte os objetos de processo em uma série de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-140">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="1e6d0-141">O parâmetro **path** especifica que o arquivo de Processes.csv é salvo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-141">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="1e6d0-142">O parâmetro **delimitador** especifica um ponto e vírgula para separar os valores da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-142">The **Delimiter** parameter specifies a semicolon to separate the string values.</span></span> <span data-ttu-id="1e6d0-143">O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-143">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="1e6d0-144">O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-144">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="1e6d0-145">Exemplo 4: exportar processos usando o separador de lista da cultura atual</span><span class="sxs-lookup"><span data-stu-id="1e6d0-145">Example 4: Export processes using the current culture's list separator</span></span>

<span data-ttu-id="1e6d0-146">Este exemplo obtém objetos de **processo** e exporta os objetos para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-146">This example gets **Process** objects and exports the objects to a file.</span></span> <span data-ttu-id="1e6d0-147">O delimitador é o separador de lista da cultura atual.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-147">The delimiter is the current culture's list separator.</span></span>

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-Process | Export-Csv -Path .\Processes.csv -UseCulture -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","511","2203597099008","35364864","21979136","30048", ...
```

<span data-ttu-id="1e6d0-148">O `Get-Culture` cmdlet usa as propriedades aninhadas **TextInfo** e **ListSeparator** e exibe o separador de lista padrão da cultura atual.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-148">The `Get-Culture` cmdlet uses the nested properties **TextInfo** and **ListSeparator** and displays the current culture's default list separator.</span></span> <span data-ttu-id="1e6d0-149">O `Get-Process` cmdlet obtém objetos de **processo** .</span><span class="sxs-lookup"><span data-stu-id="1e6d0-149">The `Get-Process` cmdlet gets **Process** objects.</span></span>
<span data-ttu-id="1e6d0-150">Os objetos de processo são enviados por meio do pipeline para o `Export-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-150">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="1e6d0-151">`Export-Csv` Converte os objetos de processo em uma série de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-151">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="1e6d0-152">O parâmetro **path** especifica que o arquivo de Processes.csv é salvo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-152">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="1e6d0-153">O parâmetro **UseCulture** usa o separador de lista padrão da cultura atual como o delimitador.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-153">The **UseCulture** parameter uses the current culture's default list separator as the delimiter.</span></span> <span data-ttu-id="1e6d0-154">O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-154">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="1e6d0-155">O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-155">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="1e6d0-156">Exemplo 5: exportar processos com informações de tipo</span><span class="sxs-lookup"><span data-stu-id="1e6d0-156">Example 5: Export processes with type information</span></span>

<span data-ttu-id="1e6d0-157">Este exemplo explica como incluir as informações de cabeçalho de **#TYPE** em um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-157">This example explains how to include the **#TYPE** header information in a CSV file.</span></span> <span data-ttu-id="1e6d0-158">O cabeçalho de **#TYPE** é o padrão nas versões anteriores ao PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-158">The **#TYPE** header is the default in versions prior to PowerShell 6.0.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -IncludeTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
#TYPE System.Diagnostics.Process
"Name","SI","Handles","VM","WS","PM","NPM","Path","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","507","2203595001856","35139584","20934656","29504", ...
```

<span data-ttu-id="1e6d0-159">O `Get-Process` cmdlet obtém objetos de **processo** .</span><span class="sxs-lookup"><span data-stu-id="1e6d0-159">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="1e6d0-160">Os objetos de processo são enviados por meio do pipeline para o `Export-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-160">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="1e6d0-161">`Export-Csv` Converte os objetos de processo em uma série de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-161">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="1e6d0-162">O parâmetro **path** especifica que o arquivo de Processes.csv é salvo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-162">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="1e6d0-163">O **IncludeTypeInformation** inclui o cabeçalho de informações **#TYPE** na saída CSV.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-163">The **IncludeTypeInformation** includes the **#TYPE** information header in the CSV output.</span></span> <span data-ttu-id="1e6d0-164">O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-164">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="1e6d0-165">Exemplo 6: exportar e acrescentar objetos a um arquivo CSV</span><span class="sxs-lookup"><span data-stu-id="1e6d0-165">Example 6: Export and append objects to a CSV file</span></span>

<span data-ttu-id="1e6d0-166">Este exemplo descreve como exportar objetos para um arquivo CSV e usar o parâmetro **Append** para adicionar objetos a um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-166">This example describes how to export objects to a CSV file and use the **Append** parameter to add objects to an existing file.</span></span>

```powershell
$AppService = (Get-Service -DisplayName *Application* | Select-Object -Property DisplayName, Status)
$AppService | Export-Csv -Path .\Services.Csv -NoTypeInformation
Get-Content -Path .\Services.Csv
$WinService = (Get-Service -DisplayName *Windows* | Select-Object -Property DisplayName, Status)
$WinService | Export-Csv -Path ./Services.csv -NoTypeInformation -Append
Get-Content -Path .\Services.Csv
```

```Output
"DisplayName","Status"
"Application Layer Gateway Service","Stopped"
"Application Identity","Running"
"Windows Audio Endpoint Builder","Running"
"Windows Audio","Running"
"Windows Event Log","Running"
```

<span data-ttu-id="1e6d0-167">O `Get-Service` cmdlet obtém os objetos de serviço.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-167">The `Get-Service` cmdlet gets service objects.</span></span> <span data-ttu-id="1e6d0-168">O parâmetro **DisplayName** retorna serviços que contêm o aplicativo Word.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-168">The **DisplayName** parameter returns services that contain the word Application.</span></span> <span data-ttu-id="1e6d0-169">Os objetos de serviço são enviados pelo pipeline para o `Select-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-169">The service objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="1e6d0-170">`Select-Object` usa o parâmetro **Property** para especificar as propriedades **DisplayName** e **status** .</span><span class="sxs-lookup"><span data-stu-id="1e6d0-170">`Select-Object` uses the **Property** parameter to specify the **DisplayName** and **Status** properties.</span></span> <span data-ttu-id="1e6d0-171">A `$AppService` variável armazena os objetos.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-171">The `$AppService` variable stores the objects.</span></span>

<span data-ttu-id="1e6d0-172">Os `$AppService` objetos são enviados para o pipeline para o `Export-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-172">The `$AppService` objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="1e6d0-173">`Export-Csv` Converte os objetos de serviço em uma série de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-173">`Export-Csv` converts the service objects to a series of CSV strings.</span></span> <span data-ttu-id="1e6d0-174">O parâmetro **path** especifica que o arquivo de Services.csv é salvo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-174">The **Path** parameter specifies that the Services.csv file is saved in the current directory.</span></span> <span data-ttu-id="1e6d0-175">O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-175">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="1e6d0-176">O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-176">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

<span data-ttu-id="1e6d0-177">Os `Get-Service` `Select-Object` cmdlets e são repetidos para serviços que contêm a palavra Windows.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-177">The `Get-Service` and `Select-Object` cmdlets are repeated for services that contain the word Windows.</span></span> <span data-ttu-id="1e6d0-178">A `$WinService` variável armazena os objetos de serviço.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-178">The `$WinService` variable stores the service objects.</span></span> <span data-ttu-id="1e6d0-179">O `Export-Csv` cmdlet usa o parâmetro **Append** para especificar que os `$WinService` objetos sejam adicionados ao arquivo de Services.csv existente.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-179">The `Export-Csv` cmdlet uses the **Append** parameter to specify that the `$WinService` objects are added to the existing Services.csv file.</span></span> <span data-ttu-id="1e6d0-180">O `Get-Content` cmdlet é repetido para exibir o arquivo atualizado que inclui os dados acrescentados.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-180">The `Get-Content` cmdlet is repeated to display the updated file that includes the appended data.</span></span>

### <span data-ttu-id="1e6d0-181">Exemplo 7: o cmdlet Format dentro de um pipeline cria resultados inesperados</span><span class="sxs-lookup"><span data-stu-id="1e6d0-181">Example 7: Format cmdlet within a pipeline creates unexpected results</span></span>

<span data-ttu-id="1e6d0-182">Este exemplo mostra por que é importante não usar um cmdlet de formato em um pipeline.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-182">This example shows why it is important not to use a format cmdlet within a pipeline.</span></span> <span data-ttu-id="1e6d0-183">Quando a saída inesperada for recebida, solucione o problema da sintaxe do pipeline.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-183">When unexpected output is received, troubleshoot the pipeline syntax.</span></span>

```powershell
Get-Date | Select-Object -Property DateTime, Day, DayOfWeek, DayOfYear |
 Export-Csv -Path .\DateTime.csv -NoTypeInformation
Get-Content -Path .\DateTime.csv
```

```Output
"DateTime","Day","DayOfWeek","DayOfYear"
"Wednesday, January 2, 2019 14:59:34","2","Wednesday","2"
```

```powershell
Get-Date | Format-Table -Property DateTime, Day, DayOfWeek, DayOfYear |
 Export-Csv -Path .\FTDateTime.csv -NoTypeInformation
Get-Content -Path .\FTDateTime.csv
```

```Output
"ClassId2e4f51ef21dd47e99d3c952918aff9cd","pageHeaderEntry","pageFooterEntry","autosizeInfo", ...
"033ecb2bc07a4d43b5ef94ed5a35d280",,,,"Microsoft.PowerShell.Commands.Internal.Format. ...
"9e210fe47d09416682b841769c78b8a3",,,,,
"27c87ef9bbda4f709f6b4002fa4af63c",,,,,
"4ec4f0187cb04f4cb6973460dfe252df",,,,,
"cf522b78d86c486691226b40aa69e95c",,,,,
```

<span data-ttu-id="1e6d0-184">O `Get-Date` cmdlet obtém o objeto **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="1e6d0-184">The `Get-Date` cmdlet gets the **DateTime** object.</span></span> <span data-ttu-id="1e6d0-185">O objeto é enviado ao pipeline para o `Select-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-185">The object is sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="1e6d0-186">`Select-Object` usa o parâmetro **Property** para selecionar um subconjunto das propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-186">`Select-Object` uses the **Property** parameter to select a subset of object properties.</span></span> <span data-ttu-id="1e6d0-187">O objeto é enviado ao pipeline para o `Export-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-187">The object is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="1e6d0-188">`Export-Csv` Converte o objeto em um formato CSV.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-188">`Export-Csv` converts the object to a CSV format.</span></span> <span data-ttu-id="1e6d0-189">O parâmetro **path** especifica que o arquivo de DateTime.csv é salvo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-189">The **Path** parameter specifies that the DateTime.csv file is saved in the current directory.</span></span> <span data-ttu-id="1e6d0-190">O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-190">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="1e6d0-191">O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o arquivo CSV localizado no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-191">The `Get-Content` cmdlet uses the **Path** parameter to display the CSV file located in the current directory.</span></span>

<span data-ttu-id="1e6d0-192">Quando o `Format-Table` cmdlet é usado no pipeline para selecionar propriedades, resultados inesperados são recebidos.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-192">When the `Format-Table` cmdlet is used within the pipeline to select properties unexpected results are received.</span></span> <span data-ttu-id="1e6d0-193">`Format-Table` envia objetos de formato de tabela por meio do pipeline para o `Export-Csv` cmdlet, em vez do objeto **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="1e6d0-193">`Format-Table` sends table format objects down the pipeline to the `Export-Csv` cmdlet rather than the **DateTime** object.</span></span> <span data-ttu-id="1e6d0-194">`Export-Csv` Converte os objetos de formato de tabela em uma série de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-194">`Export-Csv` converts the table format objects to a series of CSV strings.</span></span> <span data-ttu-id="1e6d0-195">O `Get-Content` cmdlet exibe o arquivo CSV que contém os objetos de formato de tabela.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-195">The `Get-Content` cmdlet displays the CSV file which contains the table format objects.</span></span>

### <span data-ttu-id="1e6d0-196">Exemplo 8: usando o parâmetro Force para substituir arquivos somente leitura</span><span class="sxs-lookup"><span data-stu-id="1e6d0-196">Example 8: Using the Force parameter to overwrite read-only files</span></span>

<span data-ttu-id="1e6d0-197">Este exemplo cria um arquivo somente leitura vazio e usa o parâmetro **Force** para atualizar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-197">This example creates an empty, read-only file and uses the **Force** parameter to update the file.</span></span>

```powershell
New-Item -Path .\ReadOnly.csv -ItemType File
Set-ItemProperty -Path .\ReadOnly.csv -Name IsReadOnly -Value $true
Get-Process | Export-Csv -Path .\ReadOnly.csv -NoTypeInformation
```

```Output
Export-Csv : Access to the path 'C:\ReadOnly.csv' is denied.
At line:1 char:15
+ Get-Process | Export-Csv -Path .\ReadOnly.csv -NoTypeInformation
+               ~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : OpenError: (:) [Export-Csv], UnauthorizedAccessException
+ FullyQualifiedErrorId : FileOpenFailure,Microsoft.PowerShell.Commands.ExportCsvCommand
```

```powershell
Get-Process | Export-Csv -Path .\ReadOnly.csv -NoTypeInformation -Force
Get-Content -Path .\ReadOnly.csv
```

```Output
"Name";"SI";"Handles";"VM";"WS";"PM";"NPM";"Path";"Parent";"Company";"CPU";"FileVersion"; ...
"ApplicationFrameHost";"4";"509";"2203595321344";"34807808";"21770240";"29504"; ...
```

<span data-ttu-id="1e6d0-198">O `New-Item` cmdlet usa os parâmetros **Path** e **ItemType** para criar o arquivo de ReadOnly.csv no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-198">The `New-Item` cmdlet uses the **Path** and **ItemType** parameters to create the ReadOnly.csv file in the current directory.</span></span> <span data-ttu-id="1e6d0-199">O `Set-ItemProperty` cmdlet usa os parâmetros **Name** e **Value** para alterar a propriedade **IsReadOnly** do arquivo para true.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-199">The `Set-ItemProperty` cmdlet uses the **Name** and **Value** parameters to change the file's **IsReadOnly** property to true.</span></span> <span data-ttu-id="1e6d0-200">O `Get-Process` cmdlet obtém objetos de **processo** .</span><span class="sxs-lookup"><span data-stu-id="1e6d0-200">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="1e6d0-201">Os objetos de processo são enviados por meio do pipeline para o `Export-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-201">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="1e6d0-202">`Export-Csv` Converte os objetos de processo em uma série de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-202">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="1e6d0-203">O parâmetro **path** especifica que o arquivo de ReadOnly.csv é salvo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-203">The **Path** parameter specifies that the ReadOnly.csv file is saved in the current directory.</span></span> <span data-ttu-id="1e6d0-204">O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-204">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="1e6d0-205">A saída mostra que o arquivo não foi gravado porque o acesso foi negado.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-205">The output shows that the file is not written because access is denied.</span></span>

<span data-ttu-id="1e6d0-206">O parâmetro **Force** é adicionado ao `Export-Csv` cmdlet para forçar a exportação a gravar no arquivo.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-206">The **Force** parameter is added to the `Export-Csv` cmdlet to force the export to write to the file.</span></span> <span data-ttu-id="1e6d0-207">O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-207">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="1e6d0-208">Exemplo 9: usando o parâmetro Force com Append</span><span class="sxs-lookup"><span data-stu-id="1e6d0-208">Example 9: Using the Force parameter with Append</span></span>

<span data-ttu-id="1e6d0-209">Este exemplo mostra como usar os parâmetros **Force** e **Append** .</span><span class="sxs-lookup"><span data-stu-id="1e6d0-209">This example shows how to use the **Force** and **Append** parameters.</span></span> <span data-ttu-id="1e6d0-210">Quando esses parâmetros são combinados, as propriedades de objeto incompatíveis podem ser gravadas em um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-210">When these parameters are combined, mismatched object properties can be written to a CSV file.</span></span>

```powershell
$Content = [PSCustomObject]@{Name = 'PowerShell Core'; Version = '6.0'}
$Content | Export-Csv -Path .\ParmFile.csv -NoTypeInformation
$AdditionalContent = [PSCustomObject]@{Name = 'Windows PowerShell'; Edition = 'Desktop'}
$AdditionalContent | Export-Csv -Path .\ParmFile.csv -NoTypeInformation -Append
```

```Output
Export-Csv : Cannot append CSV content to the following file: ParmFile.csv.
The appended object does not have a property that corresponds to the following column:
Version. To continue with mismatched properties, add the -Force parameter, and then retry
 the command.
At line:1 char:22
+ $AdditionalContent | Export-Csv -Path .\ParmFile.csv -NoTypeInformation -Append
+                      ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : InvalidData: (Version:String) [Export-Csv], InvalidOperationException
+ FullyQualifiedErrorId : CannotAppendCsvWithMismatchedPropertyNames,Microsoft.PowerShell. ...
```

```powershell
$AdditionalContent | Export-Csv -Path .\ParmFile.csv -NoTypeInformation -Append -Force
Import-Csv -Path .\ParmFile.csv
```

```Output
Name               Version
----               -------
PowerShell Core    6.0
Windows PowerShell
```

<span data-ttu-id="1e6d0-211">Uma expressão cria o **PSCustomObject** com propriedades **Name** e **version** .</span><span class="sxs-lookup"><span data-stu-id="1e6d0-211">An expression creates the **PSCustomObject** with **Name** and **Version** properties.</span></span> <span data-ttu-id="1e6d0-212">Os valores são armazenados na `$Content` variável.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-212">The values are stored in the `$Content` variable.</span></span> <span data-ttu-id="1e6d0-213">A `$Content` variável é enviada ao pipeline para o `Export-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-213">The `$Content` variable is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="1e6d0-214">`Export-Csv` usa o parâmetro **path** e salva o arquivo ParmFile.csv no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-214">`Export-Csv` uses the **Path** parameter and saves the ParmFile.csv file in the current directory.</span></span> <span data-ttu-id="1e6d0-215">O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-215">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

<span data-ttu-id="1e6d0-216">Outra expressão cria um **PSCustomObject** com as propriedades **Name** e **Edition** .</span><span class="sxs-lookup"><span data-stu-id="1e6d0-216">Another expression creates a **PSCustomObject** with the **Name** and **Edition** properties.</span></span> <span data-ttu-id="1e6d0-217">Os valores são armazenados na `$AdditionalContent` variável.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-217">The values are stored in the `$AdditionalContent` variable.</span></span> <span data-ttu-id="1e6d0-218">A `$AdditionalContent` variável é enviada ao pipeline para o `Export-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-218">The `$AdditionalContent` variable is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="1e6d0-219">O parâmetro **Append** é usado para adicionar os dados ao arquivo.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-219">The **Append** parameter is used to add the data to the file.</span></span> <span data-ttu-id="1e6d0-220">O acréscimo falha porque há uma incompatibilidade de nome de propriedade entre a **versão** e a **edição** .</span><span class="sxs-lookup"><span data-stu-id="1e6d0-220">The append fails because there is a property name mismatch between **Version** and **Edition** .</span></span>

<span data-ttu-id="1e6d0-221">O `Export-Csv` parâmetro **Force** do cmdlet é usado para forçar a exportação a gravar no arquivo.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-221">The `Export-Csv` cmdlet **Force** parameter is used to force the export to write to the file.</span></span> <span data-ttu-id="1e6d0-222">A propriedade de **edição** é descartada.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-222">The **Edition** property is discarded.</span></span> <span data-ttu-id="1e6d0-223">O `Import-Csv` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-223">The `Import-Csv` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="1e6d0-224">Exemplo 10: exportar para CSV com aspas em cerca de duas colunas</span><span class="sxs-lookup"><span data-stu-id="1e6d0-224">Example 10: Export to CSV with quotes around two columns</span></span>

<span data-ttu-id="1e6d0-225">Este exemplo converte um objeto **DateTime** em uma cadeia de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-225">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
Get-Date | Export-Csv  -QuoteFields "DateTime","Date" -Path .\FTDateTime.csv
Get-Content -Path .\FTDateTime.csv
```

```Output
DisplayHint,"DateTime","Date",Day,DayOfWeek,DayOfYear,Hour,Kind,Millisecond,Minute,Month,Second,Ticks,TimeOfDay,Year
DateTime,"Thursday, August 22, 2019 11:27:34 AM","8/22/2019 12:00:00 AM",22,Thursday,234,11,Local,569,27,8,34,637020700545699784,11:27:34.5699784,2019
```

### <span data-ttu-id="1e6d0-226">Exemplo 11: exportar para CSV com aspas somente quando necessário</span><span class="sxs-lookup"><span data-stu-id="1e6d0-226">Example 11: Export to CSV with quotes only when needed</span></span>

<span data-ttu-id="1e6d0-227">Este exemplo converte um objeto **DateTime** em uma cadeia de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-227">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
Get-Date | Export-Csv  -UseQuotes AsNeeded -Path .\FTDateTime.csv
Get-Content -Path .\FTDateTime.csv
```

```Output
DisplayHint,DateTime,Date,Day,DayOfWeek,DayOfYear,Hour,Kind,Millisecond,Minute,Month,Second,Ticks,TimeOfDay,Year
DateTime,"Thursday, August 22, 2019 11:31:00 AM",8/22/2019 12:00:00 AM,22,Thursday,234,11,Local,713,31,8,0,637020702607132640,11:31:00.7132640,2019
```

## <span data-ttu-id="1e6d0-228">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1e6d0-228">PARAMETERS</span></span>

### <span data-ttu-id="1e6d0-229">-Acrescentar</span><span class="sxs-lookup"><span data-stu-id="1e6d0-229">-Append</span></span>

<span data-ttu-id="1e6d0-230">Use esse parâmetro para que `Export-CSV` o adicione a saída de CSV ao final do arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-230">Use this parameter so that `Export-CSV` adds CSV output to the end of the specified file.</span></span> <span data-ttu-id="1e6d0-231">Sem esse parâmetro, `Export-CSV` o substitui o conteúdo do arquivo sem aviso.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-231">Without this parameter, `Export-CSV` replaces the file contents without warning.</span></span>

<span data-ttu-id="1e6d0-232">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-232">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="1e6d0-233">-Delimitador</span><span class="sxs-lookup"><span data-stu-id="1e6d0-233">-Delimiter</span></span>

<span data-ttu-id="1e6d0-234">Especifica um delimitador para separar os valores da propriedade.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-234">Specifies a delimiter to separate the property values.</span></span> <span data-ttu-id="1e6d0-235">O padrão é uma vírgula ( `,` ).</span><span class="sxs-lookup"><span data-stu-id="1e6d0-235">The default is a comma (`,`).</span></span> <span data-ttu-id="1e6d0-236">Insira um caractere, como dois-pontos ( `:` ).</span><span class="sxs-lookup"><span data-stu-id="1e6d0-236">Enter a character, such as a colon (`:`).</span></span> <span data-ttu-id="1e6d0-237">Para especificar um ponto e vírgula ( `;` ), coloque-o entre aspas.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-237">To specify a semicolon (`;`), enclose it in quotation marks.</span></span>

```yaml
Type: System.Char
Parameter Sets: Delimiter
Aliases:

Required: False
Position: 1
Default value: comma (,)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1e6d0-238">-Codificação</span><span class="sxs-lookup"><span data-stu-id="1e6d0-238">-Encoding</span></span>

<span data-ttu-id="1e6d0-239">Especifica a codificação do arquivo CSV exportado.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-239">Specifies the encoding for the exported CSV file.</span></span> <span data-ttu-id="1e6d0-240">O valor padrão é `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-240">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="1e6d0-241">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="1e6d0-241">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="1e6d0-242">`ascii`: Usa a codificação para o conjunto de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="1e6d0-242">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="1e6d0-243">`bigendianunicode`: Codifica no formato UTF-16 usando a ordem de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-243">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="1e6d0-244">`oem`: Usa a codificação padrão para MS-DOS e programas de console.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-244">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="1e6d0-245">`unicode`: Codifica no formato UTF-16 usando a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-245">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="1e6d0-246">`utf7`: Codifica em formato UTF-7.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-246">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="1e6d0-247">`utf8`: Codifica em formato UTF-8.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-247">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="1e6d0-248">`utf8BOM`: Codifica em formato UTF-8 com marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="1e6d0-248">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="1e6d0-249">`utf8NoBOM`: Codifica em formato UTF-8 sem marca de ordem de byte (BOM)</span><span class="sxs-lookup"><span data-stu-id="1e6d0-249">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="1e6d0-250">`utf32`: Codifica no formato UTF-32.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-250">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="1e6d0-251">A partir do PowerShell 6,2, o parâmetro de **codificação** também permite IDs numéricas de páginas de código registradas (como `-Encoding 1251` ) ou nomes de cadeia de caracteres de páginas de código registradas (como `-Encoding "windows-1251"` ).</span><span class="sxs-lookup"><span data-stu-id="1e6d0-251">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="1e6d0-252">Para obter mais informações, consulte a documentação do .NET para [Encoding. CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="1e6d0-252">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1e6d0-253">-Force</span><span class="sxs-lookup"><span data-stu-id="1e6d0-253">-Force</span></span>

<span data-ttu-id="1e6d0-254">Esse parâmetro permite `Export-Csv` substituir arquivos pelo atributo **somente leitura** .</span><span class="sxs-lookup"><span data-stu-id="1e6d0-254">This parameter allows `Export-Csv` to overwrite files with the **Read Only** attribute.</span></span>

<span data-ttu-id="1e6d0-255">Quando os parâmetros **Force** e **Append** são combinados, os objetos que contêm propriedades incompatíveis podem ser gravados em um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-255">When **Force** and **Append** parameters are combined, objects that contain mismatched properties can be written to a CSV file.</span></span> <span data-ttu-id="1e6d0-256">Somente as propriedades que correspondem são gravadas no arquivo.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-256">Only the properties that match are written to the file.</span></span> <span data-ttu-id="1e6d0-257">As propriedades incompatíveis são descartadas.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-257">The mismatched properties are discarded.</span></span>

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

### <span data-ttu-id="1e6d0-258">-IncludeTypeInformation</span><span class="sxs-lookup"><span data-stu-id="1e6d0-258">-IncludeTypeInformation</span></span>

<span data-ttu-id="1e6d0-259">Quando esse parâmetro é usado, a primeira linha da saída CSV contém **#TYPE** seguido pelo nome totalmente qualificado do tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-259">When this parameter is used the first line of the CSV output contains **#TYPE** followed by the fully qualified name of the object type.</span></span> <span data-ttu-id="1e6d0-260">Por exemplo, **#TYPE System. Diagnostics. Process** .</span><span class="sxs-lookup"><span data-stu-id="1e6d0-260">For example, **#TYPE System.Diagnostics.Process** .</span></span>

<span data-ttu-id="1e6d0-261">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-261">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ITI

Required: False
Position: Named
Default value: #TYPE <Object>
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1e6d0-262">-InputObject</span><span class="sxs-lookup"><span data-stu-id="1e6d0-262">-InputObject</span></span>

<span data-ttu-id="1e6d0-263">Especifica os objetos a exportar como cadeias CSV.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-263">Specifies the objects to export as CSV strings.</span></span> <span data-ttu-id="1e6d0-264">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-264">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="1e6d0-265">Você também pode canalizar objetos para `Export-CSV` .</span><span class="sxs-lookup"><span data-stu-id="1e6d0-265">You can also pipe objects to `Export-CSV`.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="1e6d0-266">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="1e6d0-266">-LiteralPath</span></span>

<span data-ttu-id="1e6d0-267">Especifica o caminho para o arquivo de saída CSV.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-267">Specifies the path to the CSV output file.</span></span> <span data-ttu-id="1e6d0-268">Ao contrário de **Path** , o valor do parâmetro **LiteralPath** é usado exatamente como foi digitado.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-268">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="1e6d0-269">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-269">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="1e6d0-270">Se o caminho incluir caracteres de escape, use aspas simples.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-270">If the path includes escape characters, use single quotation marks.</span></span> <span data-ttu-id="1e6d0-271">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-271">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath, LP

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1e6d0-272">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="1e6d0-272">-NoClobber</span></span>

<span data-ttu-id="1e6d0-273">Use esse parâmetro para que `Export-CSV` o não substitua um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-273">Use this parameter so that `Export-CSV` does not overwrite an existing file.</span></span> <span data-ttu-id="1e6d0-274">Por padrão, se o arquivo existir no caminho especificado, `Export-CSV` o substituirá o arquivo sem aviso.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-274">By default, if the file exists in the specified path, `Export-CSV` overwrites the file without warning.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1e6d0-275">-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="1e6d0-275">-NoTypeInformation</span></span>

<span data-ttu-id="1e6d0-276">Remove o cabeçalho de informações **#TYPE** da saída.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-276">Removes the **#TYPE** information header from the output.</span></span> <span data-ttu-id="1e6d0-277">Esse parâmetro se tornou o padrão no PowerShell 6,0 e está incluído para compatibilidade com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-277">This parameter became the default in PowerShell 6.0 and is included for backwards compatibility.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NTI

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1e6d0-278">-Path</span><span class="sxs-lookup"><span data-stu-id="1e6d0-278">-Path</span></span>

<span data-ttu-id="1e6d0-279">Um parâmetro necessário que especifica o local para salvar o arquivo de saída CSV.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-279">A required parameter that specifies the location to save the CSV output file.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1e6d0-280">-UseCulture</span><span class="sxs-lookup"><span data-stu-id="1e6d0-280">-UseCulture</span></span>

<span data-ttu-id="1e6d0-281">Usa o separador de lista para a cultura atual como o delimitador de item.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-281">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="1e6d0-282">Para localizar o separador de lista para uma cultura, use o seguinte comando: `(Get-Culture).TextInfo.ListSeparator` .</span><span class="sxs-lookup"><span data-stu-id="1e6d0-282">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UseCulture
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1e6d0-283">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1e6d0-283">-Confirm</span></span>

<span data-ttu-id="1e6d0-284">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-284">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1e6d0-285">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1e6d0-285">-WhatIf</span></span>

<span data-ttu-id="1e6d0-286">Impede que o cmdlet seja processado ou faça alterações.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-286">Prevents the cmdlet from being processed or making changes.</span></span> <span data-ttu-id="1e6d0-287">A saída mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-287">The output shows what would happen if the cmdlet were run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1e6d0-288">-QuoteFields</span><span class="sxs-lookup"><span data-stu-id="1e6d0-288">-QuoteFields</span></span>

<span data-ttu-id="1e6d0-289">Especifica os nomes das colunas que devem ser entre aspas.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-289">Specifies the names of the columns that should be quoted.</span></span> <span data-ttu-id="1e6d0-290">Quando esse parâmetro é usado, somente as colunas especificadas são citadas.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-290">When this parameter is used, only the specified columns are quoted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: QF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1e6d0-291">-UseQuotes</span><span class="sxs-lookup"><span data-stu-id="1e6d0-291">-UseQuotes</span></span>

<span data-ttu-id="1e6d0-292">Especifica quando as aspas são usadas nos arquivos CSV.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-292">Specifies when quotes are used in the CSV files.</span></span> <span data-ttu-id="1e6d0-293">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="1e6d0-293">Possible values are:</span></span>

- <span data-ttu-id="1e6d0-294">Nunca-não citar nada</span><span class="sxs-lookup"><span data-stu-id="1e6d0-294">Never - don't quote anything</span></span>
- <span data-ttu-id="1e6d0-295">Sempre-cotação de tudo (comportamento padrão)</span><span class="sxs-lookup"><span data-stu-id="1e6d0-295">Always - quote everything (default behavior)</span></span>
- <span data-ttu-id="1e6d0-296">Apenas campos de cotação necessários que contêm um caractere delimitador</span><span class="sxs-lookup"><span data-stu-id="1e6d0-296">AsNeeded - only quote fields that contain a delimiter character</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.BaseCsvWritingCommand+QuoteKind
Parameter Sets: (All)
Aliases: UQ

Required: False
Position: Named
Default value: Always
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1e6d0-297">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1e6d0-297">CommonParameters</span></span>

<span data-ttu-id="1e6d0-298">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-298">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1e6d0-299">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1e6d0-299">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1e6d0-300">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="1e6d0-300">INPUTS</span></span>

### <span data-ttu-id="1e6d0-301">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="1e6d0-301">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="1e6d0-302">É possível canalizar qualquer objeto com um adaptador de sistema de tipo estendido (ETS) para o `Export-CSV` .</span><span class="sxs-lookup"><span data-stu-id="1e6d0-302">You can pipe any object with an Extended Type System (ETS) adapter to `Export-CSV`.</span></span>

## <span data-ttu-id="1e6d0-303">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="1e6d0-303">OUTPUTS</span></span>

### <span data-ttu-id="1e6d0-304">System.String</span><span class="sxs-lookup"><span data-stu-id="1e6d0-304">System.String</span></span>

<span data-ttu-id="1e6d0-305">A lista CSV é enviada para o arquivo designado no parâmetro Path.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-305">The CSV list is sent to the file designated in the Path parameter.</span></span>

## <span data-ttu-id="1e6d0-306">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="1e6d0-306">NOTES</span></span>

<span data-ttu-id="1e6d0-307">O `Export-CSV` cmdlet converte os objetos que você envia em uma série de cadeias de caracteres CSV e salva-os no arquivo de texto especificado.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-307">The `Export-CSV` cmdlet converts the objects that you submit into a series of CSV strings and saves them in the specified text file.</span></span> <span data-ttu-id="1e6d0-308">Você pode usar `Export-CSV -IncludeTypeInformation` o para salvar objetos em um arquivo CSV e, em seguida, usar o `Import-Csv` cmdlet para criar objetos a partir do texto no arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-308">You can use `Export-CSV -IncludeTypeInformation` to save objects in a CSV file and then use the `Import-Csv` cmdlet to create objects from the text in the CSV file.</span></span>

<span data-ttu-id="1e6d0-309">No arquivo CSV, cada objeto é representado por uma lista separada por vírgulas dos valores de propriedade do objeto.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-309">In the CSV file, each object is represented by a comma-separated list of the property values of the object.</span></span> <span data-ttu-id="1e6d0-310">Os valores de propriedade são convertidos em cadeias de caracteres usando o método **ToString ()** .</span><span class="sxs-lookup"><span data-stu-id="1e6d0-310">The property values are converted to strings using the **ToString()** method.</span></span> <span data-ttu-id="1e6d0-311">As cadeias de caracteres são representadas pelo nome do valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-311">The strings are represented by the property value name.</span></span> <span data-ttu-id="1e6d0-312">`Export-CSV -IncludeTypeInformation` não exporta os métodos do objeto.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-312">`Export-CSV -IncludeTypeInformation` does not export the methods of the object.</span></span>

<span data-ttu-id="1e6d0-313">As cadeias de caracteres CSV são saídas da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="1e6d0-313">The CSV strings are output as follows:</span></span>

- <span data-ttu-id="1e6d0-314">Se **IncludeTypeInformation** for usado, a primeira cadeia de caracteres conterá o cabeçalho de informações **#TYPE** seguido pelo nome totalmente qualificado do tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-314">If **IncludeTypeInformation** is used, the first string contains the **#TYPE** information header followed by the object type's fully qualified name.</span></span>
  <span data-ttu-id="1e6d0-315">Por exemplo, **#TYPE System. Diagnostics. Process** .</span><span class="sxs-lookup"><span data-stu-id="1e6d0-315">For example, **#TYPE System.Diagnostics.Process** .</span></span>
- <span data-ttu-id="1e6d0-316">Se **IncludeTypeInformation** não for usado, a primeira cadeia de caracteres incluirá os cabeçalhos de coluna.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-316">If **IncludeTypeInformation** is not used the first string includes the column headers.</span></span> <span data-ttu-id="1e6d0-317">Os cabeçalhos contêm os nomes de Propriedade do primeiro objeto como uma lista separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-317">The headers contain the first object's property names as a comma-separated list.</span></span>
- <span data-ttu-id="1e6d0-318">As cadeias de caracteres restantes contêm listas separadas por vírgulas dos valores de propriedade de cada objeto.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-318">The remaining strings contain comma-separated lists of each object's property values.</span></span>

<span data-ttu-id="1e6d0-319">A partir do PowerShell 6,0, o comportamento padrão de `Export-CSV` é não incluir as informações de **#TYPE** no CSV e **NoTypeInformation** é implícito.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-319">Beginning with PowerShell 6.0 the default behavior of `Export-CSV` is to not include the **#TYPE** information in the CSV and **NoTypeInformation** is implied.</span></span> <span data-ttu-id="1e6d0-320">**IncludeTypeInformation** pode ser usado para incluir as informações de **#TYPE** e emular o comportamento padrão de `Export-CSV` antes do PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-320">**IncludeTypeInformation** can be used to include the **#TYPE** Information and emulate the default behavior of `Export-CSV` prior to PowerShell 6.0.</span></span>

<span data-ttu-id="1e6d0-321">Quando você envia vários objetos ao `Export-CSV` , `Export-CSV` o organiza o arquivo com base nas propriedades do primeiro objeto que você envia.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-321">When you submit multiple objects to `Export-CSV`, `Export-CSV` organizes the file based on the properties of the first object that you submit.</span></span> <span data-ttu-id="1e6d0-322">Se os objetos restantes não tiverem uma das propriedades especificadas, o valor da propriedade desse primeiro objeto será nulo, condição esta representada por duas vírgulas consecutivas.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-322">If the remaining objects do not have one of the specified properties, the property value of that object is null, as represented by two consecutive commas.</span></span> <span data-ttu-id="1e6d0-323">Se os objetos restantes têm propriedades adicionais, os valores de propriedade não são incluídos no arquivo.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-323">If the remaining objects have additional properties, those property values are not included in the file.</span></span>

<span data-ttu-id="1e6d0-324">Você pode usar o `Import-Csv` cmdlet para recriar objetos a partir de cadeias de caracteres CSV nos arquivos.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-324">You can use the `Import-Csv` cmdlet to recreate objects from the CSV strings in the files.</span></span> <span data-ttu-id="1e6d0-325">Os objetos resultantes são versões em CSV dos objetos originais, que consistem em representações dos valores das propriedades em cadeia, sem métodos.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-325">The resulting objects are CSV versions of the original objects that consist of string representations of the property values and no methods.</span></span>

<span data-ttu-id="1e6d0-326">Os `ConvertTo-Csv` `ConvertFrom-Csv` cmdlets e convertem objetos em cadeias de caracteres CSV e de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-326">The `ConvertTo-Csv` and `ConvertFrom-Csv` cmdlets convert objects to CSV strings and from CSV strings.</span></span> <span data-ttu-id="1e6d0-327">`Export-CSV` é o mesmo `ConvertTo-CSV` que, exceto pelo fato de salvar as cadeias de caracteres CSV em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-327">`Export-CSV` is the same as `ConvertTo-CSV`, except that it saves the CSV strings in a file.</span></span>

## <span data-ttu-id="1e6d0-328">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="1e6d0-328">RELATED LINKS</span></span>

[<span data-ttu-id="1e6d0-329">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="1e6d0-329">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="1e6d0-330">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="1e6d0-330">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="1e6d0-331">Format-Table</span><span class="sxs-lookup"><span data-stu-id="1e6d0-331">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="1e6d0-332">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="1e6d0-332">Import-Csv</span></span>](Import-Csv.md)

[<span data-ttu-id="1e6d0-333">Select-Object</span><span class="sxs-lookup"><span data-stu-id="1e6d0-333">Select-Object</span></span>](Select-Object.md)
