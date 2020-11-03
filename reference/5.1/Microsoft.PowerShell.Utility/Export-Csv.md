---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-csv?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Csv
ms.openlocfilehash: 5a76f8ec454ad8144f193d8927f913b89a429fec
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193826"
---
# <span data-ttu-id="6aed7-103">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="6aed7-103">Export-Csv</span></span>

## <span data-ttu-id="6aed7-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="6aed7-104">SYNOPSIS</span></span>
<span data-ttu-id="6aed7-105">Converte objetos em uma série de cadeias de caracteres de valores separados por vírgulas (CSV) e salva as cadeias de caracteres em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="6aed7-105">Converts objects into a series of comma-separated value (CSV) strings and saves the strings to a file.</span></span>

## <span data-ttu-id="6aed7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6aed7-106">SYNTAX</span></span>

### <span data-ttu-id="6aed7-107">Delimitador (padrão)</span><span class="sxs-lookup"><span data-stu-id="6aed7-107">Delimiter (Default)</span></span>

```
Export-Csv [[-Path] <string>] [[-Delimiter] <char>] -InputObject <psobject> [-LiteralPath <string>]
 [-Force] [-NoClobber] [-Encoding <string>] [-Append] [-NoTypeInformation] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="6aed7-108">parâmetro</span><span class="sxs-lookup"><span data-stu-id="6aed7-108">UseCulture</span></span>

```
Export-Csv [[-Path] <string>] -InputObject <psobject> [-LiteralPath <string>] [-Force] [-NoClobber]
 [-Encoding <string>] [-Append] [-UseCulture] [-NoTypeInformation] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="6aed7-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6aed7-109">DESCRIPTION</span></span>

<span data-ttu-id="6aed7-110">O `Export-CSV` cmdlet cria um arquivo CSV dos objetos que você envia.</span><span class="sxs-lookup"><span data-stu-id="6aed7-110">The `Export-CSV` cmdlet creates a CSV file of the objects that you submit.</span></span> <span data-ttu-id="6aed7-111">Cada objeto é uma linha que inclui uma lista separada por vírgulas dos valores de Propriedade do objeto.</span><span class="sxs-lookup"><span data-stu-id="6aed7-111">Each object is a row that includes a comma-separated list of the object's property values.</span></span> <span data-ttu-id="6aed7-112">Você pode usar o `Export-CSV` cmdlet para criar planilhas e compartilhar dados com programas que aceitam arquivos CSV como entrada.</span><span class="sxs-lookup"><span data-stu-id="6aed7-112">You can use the `Export-CSV` cmdlet to create spreadsheets and share data with programs that accept CSV files as input.</span></span>

<span data-ttu-id="6aed7-113">Não formate objetos antes de enviá-los para o `Export-CSV` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6aed7-113">Do not format objects before sending them to the `Export-CSV` cmdlet.</span></span> <span data-ttu-id="6aed7-114">Se `Export-CSV` o receber objetos formatados, o arquivo CSV conterá as propriedades de formato em vez das propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="6aed7-114">If `Export-CSV` receives formatted objects the CSV file contains the format properties rather than the object properties.</span></span> <span data-ttu-id="6aed7-115">Para exportar apenas as propriedades selecionadas de um objeto, use o `Select-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6aed7-115">To export only selected properties of an object, use the `Select-Object` cmdlet.</span></span>

## <span data-ttu-id="6aed7-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="6aed7-116">EXAMPLES</span></span>

### <span data-ttu-id="6aed7-117">Exemplo 1: exportar Propriedades do processo para um arquivo CSV</span><span class="sxs-lookup"><span data-stu-id="6aed7-117">Example 1: Export process properties to a CSV file</span></span>

<span data-ttu-id="6aed7-118">Este exemplo seleciona objetos de **processo** com propriedades específicas, exporta os objetos para um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="6aed7-118">This example selects **Process** objects with specific properties, exports the objects to a CSV file.</span></span>

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

<span data-ttu-id="6aed7-119">O `Get-Process` cmdlet obtém os objetos de **processo** .</span><span class="sxs-lookup"><span data-stu-id="6aed7-119">The `Get-Process` cmdlet gets the **Process** objects.</span></span> <span data-ttu-id="6aed7-120">O parâmetro **Name** filtra a saída para incluir apenas os objetos de processo do WmiPrvSE.</span><span class="sxs-lookup"><span data-stu-id="6aed7-120">The **Name** parameter filters the output to include only the WmiPrvSE process objects.</span></span> <span data-ttu-id="6aed7-121">Os objetos de processo são enviados por meio do pipeline para o `Select-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6aed7-121">The process objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="6aed7-122">`Select-Object` usa o parâmetro **Property** para selecionar um subconjunto das propriedades do objeto de processo.</span><span class="sxs-lookup"><span data-stu-id="6aed7-122">`Select-Object` uses the **Property** parameter to select a subset of process object properties.</span></span> <span data-ttu-id="6aed7-123">Os objetos de processo são enviados por meio do pipeline para o `Export-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6aed7-123">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="6aed7-124">`Export-Csv` Converte os objetos de processo em uma série de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="6aed7-124">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="6aed7-125">O parâmetro **path** especifica que o arquivo de WmiData.csv é salvo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="6aed7-125">The **Path** parameter specifies that the WmiData.csv file is saved in the current directory.</span></span> <span data-ttu-id="6aed7-126">O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="6aed7-126">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="6aed7-127">O `Import-Csv` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="6aed7-127">The `Import-Csv` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="6aed7-128">Exemplo 2: exportar processos para um arquivo delimitado por vírgula</span><span class="sxs-lookup"><span data-stu-id="6aed7-128">Example 2: Export processes to a comma-delimited file</span></span>

<span data-ttu-id="6aed7-129">Este exemplo obtém objetos de **processo** e exporta os objetos para um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="6aed7-129">This example gets **Process** objects and exports the objects to a CSV file.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","511","2203597099008","35364864","21979136","30048", ...
```

<span data-ttu-id="6aed7-130">O `Get-Process` cmdlet obtém objetos de **processo** .</span><span class="sxs-lookup"><span data-stu-id="6aed7-130">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="6aed7-131">Os objetos de processo são enviados por meio do pipeline para o `Export-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6aed7-131">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="6aed7-132">`Export-Csv` Converte os objetos de processo em uma série de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="6aed7-132">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="6aed7-133">O parâmetro **path** especifica que o arquivo de Processes.csv é salvo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="6aed7-133">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="6aed7-134">O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="6aed7-134">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="6aed7-135">O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="6aed7-135">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="6aed7-136">Exemplo 3: exportar processos para um arquivo delimitado por ponto e vírgula</span><span class="sxs-lookup"><span data-stu-id="6aed7-136">Example 3: Export processes to a semicolon delimited file</span></span>

<span data-ttu-id="6aed7-137">Este exemplo obtém objetos de **processo** e exporta os objetos para um arquivo com um delimitador de ponto-e-vírgula.</span><span class="sxs-lookup"><span data-stu-id="6aed7-137">This example gets **Process** objects and exports the objects to a file with a semicolon delimiter.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -Delimiter ';' -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name";"SI";"Handles";"VM";"WS";"PM";"NPM";"Path";"Parent";"Company";"CPU";"FileVersion"; ...
"ApplicationFrameHost";"4";"509";"2203595321344";"34807808";"21770240";"29504"; ...
```

<span data-ttu-id="6aed7-138">O `Get-Process` cmdlet obtém objetos de **processo** .</span><span class="sxs-lookup"><span data-stu-id="6aed7-138">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="6aed7-139">Os objetos de processo são enviados por meio do pipeline para o `Export-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6aed7-139">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="6aed7-140">`Export-Csv` Converte os objetos de processo em uma série de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="6aed7-140">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="6aed7-141">O parâmetro **path** especifica que o arquivo de Processes.csv é salvo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="6aed7-141">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="6aed7-142">O parâmetro **delimitador** especifica um ponto e vírgula para separar os valores da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="6aed7-142">The **Delimiter** parameter specifies a semicolon to separate the string values.</span></span> <span data-ttu-id="6aed7-143">O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="6aed7-143">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="6aed7-144">O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="6aed7-144">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="6aed7-145">Exemplo 4: exportar processos usando o separador de lista da cultura atual</span><span class="sxs-lookup"><span data-stu-id="6aed7-145">Example 4: Export processes using the current culture's list separator</span></span>

<span data-ttu-id="6aed7-146">Este exemplo obtém objetos de **processo** e exporta os objetos para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="6aed7-146">This example gets **Process** objects and exports the objects to a file.</span></span> <span data-ttu-id="6aed7-147">O delimitador é o separador de lista da cultura atual.</span><span class="sxs-lookup"><span data-stu-id="6aed7-147">The delimiter is the current culture's list separator.</span></span>

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-Process | Export-Csv -Path .\Processes.csv -UseCulture -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","511","2203597099008","35364864","21979136","30048", ...
```

<span data-ttu-id="6aed7-148">O `Get-Culture` cmdlet usa as propriedades aninhadas **TextInfo** e **ListSeparator** e exibe o separador de lista padrão da cultura atual.</span><span class="sxs-lookup"><span data-stu-id="6aed7-148">The `Get-Culture` cmdlet uses the nested properties **TextInfo** and **ListSeparator** and displays the current culture's default list separator.</span></span> <span data-ttu-id="6aed7-149">O `Get-Process` cmdlet obtém objetos de **processo** .</span><span class="sxs-lookup"><span data-stu-id="6aed7-149">The `Get-Process` cmdlet gets **Process** objects.</span></span>
<span data-ttu-id="6aed7-150">Os objetos de processo são enviados por meio do pipeline para o `Export-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6aed7-150">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="6aed7-151">`Export-Csv` Converte os objetos de processo em uma série de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="6aed7-151">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="6aed7-152">O parâmetro **path** especifica que o arquivo de Processes.csv é salvo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="6aed7-152">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="6aed7-153">O parâmetro **UseCulture** usa o separador de lista padrão da cultura atual como o delimitador.</span><span class="sxs-lookup"><span data-stu-id="6aed7-153">The **UseCulture** parameter uses the current culture's default list separator as the delimiter.</span></span> <span data-ttu-id="6aed7-154">O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="6aed7-154">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="6aed7-155">O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="6aed7-155">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="6aed7-156">Exemplo 5: exportar processos com informações de tipo</span><span class="sxs-lookup"><span data-stu-id="6aed7-156">Example 5: Export processes with type information</span></span>

<span data-ttu-id="6aed7-157">Este exemplo explica como incluir as informações de cabeçalho de **#TYPE** em um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="6aed7-157">This example explains how to include the **#TYPE** header information in a CSV file.</span></span> <span data-ttu-id="6aed7-158">O cabeçalho de **#TYPE** é o padrão nas versões anteriores ao PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="6aed7-158">The **#TYPE** header is the default in versions prior to PowerShell 6.0.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv
Get-Content -Path .\Processes.csv
```

```Output
#TYPE System.Diagnostics.Process
"Name","SI","Handles","VM","WS","PM","NPM","Path","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","507","2203595001856","35139584","20934656","29504", ...
```

<span data-ttu-id="6aed7-159">O `Get-Process` cmdlet obtém objetos de **processo** .</span><span class="sxs-lookup"><span data-stu-id="6aed7-159">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="6aed7-160">Os objetos de processo são enviados por meio do pipeline para o `Export-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6aed7-160">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="6aed7-161">`Export-Csv` Converte os objetos de processo em uma série de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="6aed7-161">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="6aed7-162">O parâmetro **path** especifica que o arquivo de Processes.csv é salvo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="6aed7-162">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="6aed7-163">O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="6aed7-163">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="6aed7-164">Exemplo 6: exportar e acrescentar objetos a um arquivo CSV</span><span class="sxs-lookup"><span data-stu-id="6aed7-164">Example 6: Export and append objects to a CSV file</span></span>

<span data-ttu-id="6aed7-165">Este exemplo descreve como exportar objetos para um arquivo CSV e usar o parâmetro **Append** para adicionar objetos a um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="6aed7-165">This example describes how to export objects to a CSV file and use the **Append** parameter to add objects to an existing file.</span></span>

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

<span data-ttu-id="6aed7-166">O `Get-Service` cmdlet obtém os objetos de serviço.</span><span class="sxs-lookup"><span data-stu-id="6aed7-166">The `Get-Service` cmdlet gets service objects.</span></span> <span data-ttu-id="6aed7-167">O parâmetro **DisplayName** retorna serviços que contêm o aplicativo Word.</span><span class="sxs-lookup"><span data-stu-id="6aed7-167">The **DisplayName** parameter returns services that contain the word Application.</span></span> <span data-ttu-id="6aed7-168">Os objetos de serviço são enviados pelo pipeline para o `Select-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6aed7-168">The service objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="6aed7-169">`Select-Object` usa o parâmetro **Property** para especificar as propriedades **DisplayName** e **status** .</span><span class="sxs-lookup"><span data-stu-id="6aed7-169">`Select-Object` uses the **Property** parameter to specify the **DisplayName** and **Status** properties.</span></span> <span data-ttu-id="6aed7-170">A `$AppService` variável armazena os objetos.</span><span class="sxs-lookup"><span data-stu-id="6aed7-170">The `$AppService` variable stores the objects.</span></span>

<span data-ttu-id="6aed7-171">Os `$AppService` objetos são enviados para o pipeline para o `Export-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6aed7-171">The `$AppService` objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="6aed7-172">`Export-Csv` Converte os objetos de serviço em uma série de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="6aed7-172">`Export-Csv` converts the service objects to a series of CSV strings.</span></span> <span data-ttu-id="6aed7-173">O parâmetro **path** especifica que o arquivo de Services.csv é salvo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="6aed7-173">The **Path** parameter specifies that the Services.csv file is saved in the current directory.</span></span> <span data-ttu-id="6aed7-174">O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="6aed7-174">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="6aed7-175">O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="6aed7-175">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

<span data-ttu-id="6aed7-176">Os `Get-Service` `Select-Object` cmdlets e são repetidos para serviços que contêm a palavra Windows.</span><span class="sxs-lookup"><span data-stu-id="6aed7-176">The `Get-Service` and `Select-Object` cmdlets are repeated for services that contain the word Windows.</span></span> <span data-ttu-id="6aed7-177">A `$WinService` variável armazena os objetos de serviço.</span><span class="sxs-lookup"><span data-stu-id="6aed7-177">The `$WinService` variable stores the service objects.</span></span> <span data-ttu-id="6aed7-178">O `Export-Csv` cmdlet usa o parâmetro **Append** para especificar que os `$WinService` objetos sejam adicionados ao arquivo de Services.csv existente.</span><span class="sxs-lookup"><span data-stu-id="6aed7-178">The `Export-Csv` cmdlet uses the **Append** parameter to specify that the `$WinService` objects are added to the existing Services.csv file.</span></span> <span data-ttu-id="6aed7-179">O `Get-Content` cmdlet é repetido para exibir o arquivo atualizado que inclui os dados acrescentados.</span><span class="sxs-lookup"><span data-stu-id="6aed7-179">The `Get-Content` cmdlet is repeated to display the updated file that includes the appended data.</span></span>

### <span data-ttu-id="6aed7-180">Exemplo 7: o cmdlet Format dentro de um pipeline cria resultados inesperados</span><span class="sxs-lookup"><span data-stu-id="6aed7-180">Example 7: Format cmdlet within a pipeline creates unexpected results</span></span>

<span data-ttu-id="6aed7-181">Este exemplo mostra por que é importante não usar um cmdlet de formato em um pipeline.</span><span class="sxs-lookup"><span data-stu-id="6aed7-181">This example shows why it is important not to use a format cmdlet within a pipeline.</span></span> <span data-ttu-id="6aed7-182">Quando a saída inesperada for recebida, solucione o problema da sintaxe do pipeline.</span><span class="sxs-lookup"><span data-stu-id="6aed7-182">When unexpected output is received, troubleshoot the pipeline syntax.</span></span>

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

<span data-ttu-id="6aed7-183">O `Get-Date` cmdlet obtém o objeto **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="6aed7-183">The `Get-Date` cmdlet gets the **DateTime** object.</span></span> <span data-ttu-id="6aed7-184">O objeto é enviado ao pipeline para o `Select-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6aed7-184">The object is sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="6aed7-185">`Select-Object` usa o parâmetro **Property** para selecionar um subconjunto das propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="6aed7-185">`Select-Object` uses the **Property** parameter to select a subset of object properties.</span></span> <span data-ttu-id="6aed7-186">O objeto é enviado ao pipeline para o `Export-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6aed7-186">The object is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="6aed7-187">`Export-Csv` Converte o objeto em um formato CSV.</span><span class="sxs-lookup"><span data-stu-id="6aed7-187">`Export-Csv` converts the object to a CSV format.</span></span> <span data-ttu-id="6aed7-188">O parâmetro **path** especifica que o arquivo de DateTime.csv é salvo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="6aed7-188">The **Path** parameter specifies that the DateTime.csv file is saved in the current directory.</span></span> <span data-ttu-id="6aed7-189">O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="6aed7-189">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="6aed7-190">O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o arquivo CSV localizado no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="6aed7-190">The `Get-Content` cmdlet uses the **Path** parameter to display the CSV file located in the current directory.</span></span>

<span data-ttu-id="6aed7-191">Quando o `Format-Table` cmdlet é usado no pipeline para selecionar propriedades, resultados inesperados são recebidos.</span><span class="sxs-lookup"><span data-stu-id="6aed7-191">When the `Format-Table` cmdlet is used within the pipeline to select properties unexpected results are received.</span></span> <span data-ttu-id="6aed7-192">`Format-Table` envia objetos de formato de tabela por meio do pipeline para o `Export-Csv` cmdlet, em vez do objeto **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="6aed7-192">`Format-Table` sends table format objects down the pipeline to the `Export-Csv` cmdlet rather than the **DateTime** object.</span></span> <span data-ttu-id="6aed7-193">`Export-Csv` Converte os objetos de formato de tabela em uma série de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="6aed7-193">`Export-Csv` converts the table format objects to a series of CSV strings.</span></span> <span data-ttu-id="6aed7-194">O `Get-Content` cmdlet exibe o arquivo CSV que contém os objetos de formato de tabela.</span><span class="sxs-lookup"><span data-stu-id="6aed7-194">The `Get-Content` cmdlet displays the CSV file which contains the table format objects.</span></span>

### <span data-ttu-id="6aed7-195">Exemplo 8: usando o parâmetro Force para substituir arquivos somente leitura</span><span class="sxs-lookup"><span data-stu-id="6aed7-195">Example 8: Using the Force parameter to overwrite read-only files</span></span>

<span data-ttu-id="6aed7-196">Este exemplo cria um arquivo somente leitura vazio e usa o parâmetro **Force** para atualizar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="6aed7-196">This example creates an empty, read-only file and uses the **Force** parameter to update the file.</span></span>

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

<span data-ttu-id="6aed7-197">O `New-Item` cmdlet usa os parâmetros **Path** e **ItemType** para criar o arquivo de ReadOnly.csv no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="6aed7-197">The `New-Item` cmdlet uses the **Path** and **ItemType** parameters to create the ReadOnly.csv file in the current directory.</span></span> <span data-ttu-id="6aed7-198">O `Set-ItemProperty` cmdlet usa os parâmetros **Name** e **Value** para alterar a propriedade **IsReadOnly** do arquivo para true.</span><span class="sxs-lookup"><span data-stu-id="6aed7-198">The `Set-ItemProperty` cmdlet uses the **Name** and **Value** parameters to change the file's **IsReadOnly** property to true.</span></span> <span data-ttu-id="6aed7-199">O `Get-Process` cmdlet obtém objetos de **processo** .</span><span class="sxs-lookup"><span data-stu-id="6aed7-199">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="6aed7-200">Os objetos de processo são enviados por meio do pipeline para o `Export-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6aed7-200">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="6aed7-201">`Export-Csv` Converte os objetos de processo em uma série de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="6aed7-201">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="6aed7-202">O parâmetro **path** especifica que o arquivo de ReadOnly.csv é salvo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="6aed7-202">The **Path** parameter specifies that the ReadOnly.csv file is saved in the current directory.</span></span> <span data-ttu-id="6aed7-203">O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="6aed7-203">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="6aed7-204">A saída mostra que o arquivo não foi gravado porque o acesso foi negado.</span><span class="sxs-lookup"><span data-stu-id="6aed7-204">The output shows that the file is not written because access is denied.</span></span>

<span data-ttu-id="6aed7-205">O parâmetro **Force** é adicionado ao `Export-Csv` cmdlet para forçar a exportação a gravar no arquivo.</span><span class="sxs-lookup"><span data-stu-id="6aed7-205">The **Force** parameter is added to the `Export-Csv` cmdlet to force the export to write to the file.</span></span> <span data-ttu-id="6aed7-206">O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="6aed7-206">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="6aed7-207">Exemplo 9: usando o parâmetro Force com Append</span><span class="sxs-lookup"><span data-stu-id="6aed7-207">Example 9: Using the Force parameter with Append</span></span>

<span data-ttu-id="6aed7-208">Este exemplo mostra como usar os parâmetros **Force** e **Append** .</span><span class="sxs-lookup"><span data-stu-id="6aed7-208">This example shows how to use the **Force** and **Append** parameters.</span></span> <span data-ttu-id="6aed7-209">Quando esses parâmetros são combinados, as propriedades de objeto incompatíveis podem ser gravadas em um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="6aed7-209">When these parameters are combined, mismatched object properties can be written to a CSV file.</span></span>

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

<span data-ttu-id="6aed7-210">Uma expressão cria o **PSCustomObject** com propriedades **Name** e **version** .</span><span class="sxs-lookup"><span data-stu-id="6aed7-210">An expression creates the **PSCustomObject** with **Name** and **Version** properties.</span></span> <span data-ttu-id="6aed7-211">Os valores são armazenados na `$Content` variável.</span><span class="sxs-lookup"><span data-stu-id="6aed7-211">The values are stored in the `$Content` variable.</span></span> <span data-ttu-id="6aed7-212">A `$Content` variável é enviada ao pipeline para o `Export-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6aed7-212">The `$Content` variable is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="6aed7-213">`Export-Csv` usa o parâmetro **path** e salva o arquivo ParmFile.csv no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="6aed7-213">`Export-Csv` uses the **Path** parameter and saves the ParmFile.csv file in the current directory.</span></span> <span data-ttu-id="6aed7-214">O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="6aed7-214">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

<span data-ttu-id="6aed7-215">Outra expressão cria um **PSCustomObject** com as propriedades **Name** e **Edition** .</span><span class="sxs-lookup"><span data-stu-id="6aed7-215">Another expression creates a **PSCustomObject** with the **Name** and **Edition** properties.</span></span> <span data-ttu-id="6aed7-216">Os valores são armazenados na `$AdditionalContent` variável.</span><span class="sxs-lookup"><span data-stu-id="6aed7-216">The values are stored in the `$AdditionalContent` variable.</span></span> <span data-ttu-id="6aed7-217">A `$AdditionalContent` variável é enviada ao pipeline para o `Export-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6aed7-217">The `$AdditionalContent` variable is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="6aed7-218">O parâmetro **Append** é usado para adicionar os dados ao arquivo.</span><span class="sxs-lookup"><span data-stu-id="6aed7-218">The **Append** parameter is used to add the data to the file.</span></span> <span data-ttu-id="6aed7-219">O acréscimo falha porque há uma incompatibilidade de nome de propriedade entre a **versão** e a **edição** .</span><span class="sxs-lookup"><span data-stu-id="6aed7-219">The append fails because there is a property name mismatch between **Version** and **Edition** .</span></span>

<span data-ttu-id="6aed7-220">O `Export-Csv` parâmetro **Force** do cmdlet é usado para forçar a exportação a gravar no arquivo.</span><span class="sxs-lookup"><span data-stu-id="6aed7-220">The `Export-Csv` cmdlet **Force** parameter is used to force the export to write to the file.</span></span> <span data-ttu-id="6aed7-221">A propriedade de **edição** é descartada.</span><span class="sxs-lookup"><span data-stu-id="6aed7-221">The **Edition** property is discarded.</span></span> <span data-ttu-id="6aed7-222">O `Import-Csv` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="6aed7-222">The `Import-Csv` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

## <span data-ttu-id="6aed7-223">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6aed7-223">PARAMETERS</span></span>

### <span data-ttu-id="6aed7-224">-Acrescentar</span><span class="sxs-lookup"><span data-stu-id="6aed7-224">-Append</span></span>

<span data-ttu-id="6aed7-225">Use esse parâmetro para que `Export-CSV` o adicione a saída de CSV ao final do arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="6aed7-225">Use this parameter so that `Export-CSV` adds CSV output to the end of the specified file.</span></span> <span data-ttu-id="6aed7-226">Sem esse parâmetro, `Export-CSV` o substitui o conteúdo do arquivo sem aviso.</span><span class="sxs-lookup"><span data-stu-id="6aed7-226">Without this parameter, `Export-CSV` replaces the file contents without warning.</span></span>

<span data-ttu-id="6aed7-227">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="6aed7-227">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="6aed7-228">-Delimitador</span><span class="sxs-lookup"><span data-stu-id="6aed7-228">-Delimiter</span></span>

<span data-ttu-id="6aed7-229">Especifica um delimitador para separar os valores da propriedade.</span><span class="sxs-lookup"><span data-stu-id="6aed7-229">Specifies a delimiter to separate the property values.</span></span> <span data-ttu-id="6aed7-230">O padrão é uma vírgula ( `,` ).</span><span class="sxs-lookup"><span data-stu-id="6aed7-230">The default is a comma (`,`).</span></span> <span data-ttu-id="6aed7-231">Insira um caractere, como dois-pontos ( `:` ).</span><span class="sxs-lookup"><span data-stu-id="6aed7-231">Enter a character, such as a colon (`:`).</span></span> <span data-ttu-id="6aed7-232">Para especificar um ponto e vírgula ( `;` ), coloque-o entre aspas.</span><span class="sxs-lookup"><span data-stu-id="6aed7-232">To specify a semicolon (`;`), enclose it in quotation marks.</span></span>

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

### <span data-ttu-id="6aed7-233">-Codificação</span><span class="sxs-lookup"><span data-stu-id="6aed7-233">-Encoding</span></span>

<span data-ttu-id="6aed7-234">Especifica o tipo de codificação para o arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="6aed7-234">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="6aed7-235">O valor padrão é `ASCII`.</span><span class="sxs-lookup"><span data-stu-id="6aed7-235">The default value is `ASCII`.</span></span>

<span data-ttu-id="6aed7-236">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="6aed7-236">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="6aed7-237">`ASCII` Usa conjunto de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="6aed7-237">`ASCII` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="6aed7-238">`BigEndianUnicode` Usa UTF-16 com a ordem de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="6aed7-238">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="6aed7-239">`Default` Usa a codificação que corresponde à página de código ativa do sistema (geralmente ANSI).</span><span class="sxs-lookup"><span data-stu-id="6aed7-239">`Default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="6aed7-240">`OEM` Usa a codificação que corresponde à página de código OEM atual do sistema.</span><span class="sxs-lookup"><span data-stu-id="6aed7-240">`OEM` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="6aed7-241">`Unicode` Usa UTF-16 com a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="6aed7-241">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="6aed7-242">`UTF7` Usa UTF-7.</span><span class="sxs-lookup"><span data-stu-id="6aed7-242">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="6aed7-243">`UTF8` Usa UTF-8.</span><span class="sxs-lookup"><span data-stu-id="6aed7-243">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="6aed7-244">`UTF32` Usa UTF-32 com a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="6aed7-244">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, Default, OEM, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: ASCII
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6aed7-245">-Force</span><span class="sxs-lookup"><span data-stu-id="6aed7-245">-Force</span></span>

<span data-ttu-id="6aed7-246">Esse parâmetro permite `Export-Csv` substituir arquivos pelo atributo **somente leitura** .</span><span class="sxs-lookup"><span data-stu-id="6aed7-246">This parameter allows `Export-Csv` to overwrite files with the **Read Only** attribute.</span></span>

<span data-ttu-id="6aed7-247">Quando os parâmetros **Force** e **Append** são combinados, os objetos que contêm propriedades incompatíveis podem ser gravados em um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="6aed7-247">When **Force** and **Append** parameters are combined, objects that contain mismatched properties can be written to a CSV file.</span></span> <span data-ttu-id="6aed7-248">Somente as propriedades que correspondem são gravadas no arquivo.</span><span class="sxs-lookup"><span data-stu-id="6aed7-248">Only the properties that match are written to the file.</span></span> <span data-ttu-id="6aed7-249">As propriedades incompatíveis são descartadas.</span><span class="sxs-lookup"><span data-stu-id="6aed7-249">The mismatched properties are discarded.</span></span>

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

### <span data-ttu-id="6aed7-250">-InputObject</span><span class="sxs-lookup"><span data-stu-id="6aed7-250">-InputObject</span></span>

<span data-ttu-id="6aed7-251">Especifica os objetos a exportar como cadeias CSV.</span><span class="sxs-lookup"><span data-stu-id="6aed7-251">Specifies the objects to export as CSV strings.</span></span> <span data-ttu-id="6aed7-252">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="6aed7-252">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="6aed7-253">Você também pode canalizar objetos para `Export-CSV` .</span><span class="sxs-lookup"><span data-stu-id="6aed7-253">You can also pipe objects to `Export-CSV`.</span></span>

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

### <span data-ttu-id="6aed7-254">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="6aed7-254">-LiteralPath</span></span>

<span data-ttu-id="6aed7-255">Especifica o caminho para o arquivo de saída CSV.</span><span class="sxs-lookup"><span data-stu-id="6aed7-255">Specifies the path to the CSV output file.</span></span> <span data-ttu-id="6aed7-256">Ao contrário de **Path** , o valor do parâmetro **LiteralPath** é usado exatamente como foi digitado.</span><span class="sxs-lookup"><span data-stu-id="6aed7-256">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="6aed7-257">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="6aed7-257">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="6aed7-258">Se o caminho incluir caracteres de escape, use aspas simples.</span><span class="sxs-lookup"><span data-stu-id="6aed7-258">If the path includes escape characters, use single quotation marks.</span></span> <span data-ttu-id="6aed7-259">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="6aed7-259">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6aed7-260">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="6aed7-260">-NoClobber</span></span>

<span data-ttu-id="6aed7-261">Use esse parâmetro para que `Export-CSV` o não substitua um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="6aed7-261">Use this parameter so that `Export-CSV` does not overwrite an existing file.</span></span> <span data-ttu-id="6aed7-262">Por padrão, se o arquivo existir no caminho especificado, `Export-CSV` o substituirá o arquivo sem aviso.</span><span class="sxs-lookup"><span data-stu-id="6aed7-262">By default, if the file exists in the specified path, `Export-CSV` overwrites the file without warning.</span></span>

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

### <span data-ttu-id="6aed7-263">-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="6aed7-263">-NoTypeInformation</span></span>

<span data-ttu-id="6aed7-264">Remove o cabeçalho de informações **#TYPE** da saída.</span><span class="sxs-lookup"><span data-stu-id="6aed7-264">Removes the **#TYPE** information header from the output.</span></span> <span data-ttu-id="6aed7-265">Esse parâmetro se tornou o padrão no PowerShell 6,0 e está incluído para compatibilidade com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="6aed7-265">This parameter became the default in PowerShell 6.0 and is included for backwards compatibility.</span></span>

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

### <span data-ttu-id="6aed7-266">-Path</span><span class="sxs-lookup"><span data-stu-id="6aed7-266">-Path</span></span>

<span data-ttu-id="6aed7-267">Um parâmetro necessário que especifica o local para salvar o arquivo de saída CSV.</span><span class="sxs-lookup"><span data-stu-id="6aed7-267">A required parameter that specifies the location to save the CSV output file.</span></span>

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

### <span data-ttu-id="6aed7-268">-UseCulture</span><span class="sxs-lookup"><span data-stu-id="6aed7-268">-UseCulture</span></span>

<span data-ttu-id="6aed7-269">Usa o separador de lista para a cultura atual como o delimitador de item.</span><span class="sxs-lookup"><span data-stu-id="6aed7-269">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="6aed7-270">Para localizar o separador de lista para uma cultura, use o seguinte comando: `(Get-Culture).TextInfo.ListSeparator` .</span><span class="sxs-lookup"><span data-stu-id="6aed7-270">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

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

### <span data-ttu-id="6aed7-271">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6aed7-271">-Confirm</span></span>

<span data-ttu-id="6aed7-272">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6aed7-272">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="6aed7-273">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6aed7-273">-WhatIf</span></span>

<span data-ttu-id="6aed7-274">Impede que o cmdlet seja processado ou faça alterações.</span><span class="sxs-lookup"><span data-stu-id="6aed7-274">Prevents the cmdlet from being processed or making changes.</span></span> <span data-ttu-id="6aed7-275">A saída mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="6aed7-275">The output shows what would happen if the cmdlet were run.</span></span>

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

### <span data-ttu-id="6aed7-276">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6aed7-276">CommonParameters</span></span>

<span data-ttu-id="6aed7-277">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6aed7-277">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6aed7-278">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6aed7-278">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6aed7-279">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="6aed7-279">INPUTS</span></span>

### <span data-ttu-id="6aed7-280">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="6aed7-280">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="6aed7-281">É possível canalizar qualquer objeto com um adaptador de sistema de tipo estendido (ETS) para o `Export-CSV` .</span><span class="sxs-lookup"><span data-stu-id="6aed7-281">You can pipe any object with an Extended Type System (ETS) adapter to `Export-CSV`.</span></span>

## <span data-ttu-id="6aed7-282">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="6aed7-282">OUTPUTS</span></span>

### <span data-ttu-id="6aed7-283">System.String</span><span class="sxs-lookup"><span data-stu-id="6aed7-283">System.String</span></span>

<span data-ttu-id="6aed7-284">A lista CSV é enviada para o arquivo designado no parâmetro Path.</span><span class="sxs-lookup"><span data-stu-id="6aed7-284">The CSV list is sent to the file designated in the Path parameter.</span></span>

## <span data-ttu-id="6aed7-285">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="6aed7-285">NOTES</span></span>

<span data-ttu-id="6aed7-286">O `Export-CSV` cmdlet converte os objetos que você envia em uma série de cadeias de caracteres CSV e salva-os no arquivo de texto especificado.</span><span class="sxs-lookup"><span data-stu-id="6aed7-286">The `Export-CSV` cmdlet converts the objects that you submit into a series of CSV strings and saves them in the specified text file.</span></span> <span data-ttu-id="6aed7-287">Você pode usar `Export-CSV` o para salvar objetos em um arquivo CSV e, em seguida, usar o `Import-Csv` cmdlet para criar objetos a partir do arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="6aed7-287">You can use `Export-CSV` to save objects in a CSV file and then use the `Import-Csv` cmdlet to create objects from the CSV file.</span></span>

<span data-ttu-id="6aed7-288">No arquivo CSV, cada objeto é representado por uma lista separada por vírgulas dos valores de propriedade do objeto.</span><span class="sxs-lookup"><span data-stu-id="6aed7-288">In the CSV file, each object is represented by a comma-separated list of the property values of the object.</span></span> <span data-ttu-id="6aed7-289">Os valores de propriedade são convertidos em cadeias de caracteres usando o método **ToString ()** .</span><span class="sxs-lookup"><span data-stu-id="6aed7-289">The property values are converted to strings using the **ToString()** method.</span></span> <span data-ttu-id="6aed7-290">As cadeias de caracteres são representadas pelo nome do valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="6aed7-290">The strings are represented by the property value name.</span></span> <span data-ttu-id="6aed7-291">' Export-CSV não exporta os métodos do objeto.</span><span class="sxs-lookup"><span data-stu-id="6aed7-291">\`Export-CSV does not export the methods of the object.</span></span>

<span data-ttu-id="6aed7-292">As cadeias de caracteres CSV são saídas da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="6aed7-292">The CSV strings are output as follows:</span></span>

- <span data-ttu-id="6aed7-293">Por padrão, a primeira cadeia de caracteres contém o cabeçalho de informações **#TYPE** seguido pelo nome totalmente qualificado do tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="6aed7-293">By default the first string contains the **#TYPE** information header followed by the object type's fully qualified name.</span></span> <span data-ttu-id="6aed7-294">Por exemplo, **#TYPE System. Diagnostics. Process** .</span><span class="sxs-lookup"><span data-stu-id="6aed7-294">For example, **#TYPE System.Diagnostics.Process** .</span></span>
- <span data-ttu-id="6aed7-295">Se **NoTypeInformation** for usado, a primeira cadeia de caracteres incluirá os cabeçalhos de coluna.</span><span class="sxs-lookup"><span data-stu-id="6aed7-295">If **NoTypeInformation** is used the first string includes the column headers.</span></span> <span data-ttu-id="6aed7-296">Os cabeçalhos contêm os nomes de Propriedade do primeiro objeto como uma lista separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="6aed7-296">The headers contain the first object's property names as a comma-separated list.</span></span>
- <span data-ttu-id="6aed7-297">As cadeias de caracteres restantes contêm listas separadas por vírgulas dos valores de propriedade de cada objeto.</span><span class="sxs-lookup"><span data-stu-id="6aed7-297">The remaining strings contain comma-separated lists of each object's property values.</span></span>

<span data-ttu-id="6aed7-298">Quando você envia vários objetos ao `Export-CSV` , `Export-CSV` o organiza o arquivo com base nas propriedades do primeiro objeto que você envia.</span><span class="sxs-lookup"><span data-stu-id="6aed7-298">When you submit multiple objects to `Export-CSV`, `Export-CSV` organizes the file based on the properties of the first object that you submit.</span></span> <span data-ttu-id="6aed7-299">Se os objetos restantes não tiverem uma das propriedades especificadas, o valor da propriedade desse primeiro objeto será nulo, condição esta representada por duas vírgulas consecutivas.</span><span class="sxs-lookup"><span data-stu-id="6aed7-299">If the remaining objects do not have one of the specified properties, the property value of that object is null, as represented by two consecutive commas.</span></span> <span data-ttu-id="6aed7-300">Se os objetos restantes têm propriedades adicionais, os valores de propriedade não são incluídos no arquivo.</span><span class="sxs-lookup"><span data-stu-id="6aed7-300">If the remaining objects have additional properties, those property values are not included in the file.</span></span>

<span data-ttu-id="6aed7-301">Você pode usar o `Import-Csv` cmdlet para recriar objetos a partir de cadeias de caracteres CSV nos arquivos.</span><span class="sxs-lookup"><span data-stu-id="6aed7-301">You can use the `Import-Csv` cmdlet to recreate objects from the CSV strings in the files.</span></span> <span data-ttu-id="6aed7-302">Os objetos resultantes são versões em CSV dos objetos originais, que consistem em representações dos valores das propriedades em cadeia, sem métodos.</span><span class="sxs-lookup"><span data-stu-id="6aed7-302">The resulting objects are CSV versions of the original objects that consist of string representations of the property values and no methods.</span></span>

<span data-ttu-id="6aed7-303">Os `ConvertTo-Csv` `ConvertFrom-Csv` cmdlets e convertem objetos em cadeias de caracteres CSV e de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="6aed7-303">The `ConvertTo-Csv` and `ConvertFrom-Csv` cmdlets convert objects to CSV strings and from CSV strings.</span></span> <span data-ttu-id="6aed7-304">`Export-CSV` é o mesmo `ConvertTo-CSV` que, exceto pelo fato de salvar as cadeias de caracteres CSV em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="6aed7-304">`Export-CSV` is the same as `ConvertTo-CSV`, except that it saves the CSV strings in a file.</span></span>

## <span data-ttu-id="6aed7-305">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="6aed7-305">RELATED LINKS</span></span>

[<span data-ttu-id="6aed7-306">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="6aed7-306">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="6aed7-307">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="6aed7-307">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="6aed7-308">Format-Table</span><span class="sxs-lookup"><span data-stu-id="6aed7-308">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="6aed7-309">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="6aed7-309">Import-Csv</span></span>](Import-Csv.md)

[<span data-ttu-id="6aed7-310">Select-Object</span><span class="sxs-lookup"><span data-stu-id="6aed7-310">Select-Object</span></span>](Select-Object.md)
