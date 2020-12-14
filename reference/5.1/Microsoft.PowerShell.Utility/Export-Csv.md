---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-csv?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Csv
ms.openlocfilehash: 17c3ef3046ba8f0cca9a85cf41aaf683212a58e9
ms.sourcegitcommit: 560a9f3c3148acab4655e91e8b07745ab74d5d26
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "96913334"
---
# <span data-ttu-id="2ad7c-102">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="2ad7c-102">Export-Csv</span></span>

## <span data-ttu-id="2ad7c-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="2ad7c-103">SYNOPSIS</span></span>
<span data-ttu-id="2ad7c-104">Converte objetos em uma série de cadeias de caracteres de valores separados por vírgulas (CSV) e salva as cadeias de caracteres em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-104">Converts objects into a series of comma-separated value (CSV) strings and saves the strings to a file.</span></span>

## <span data-ttu-id="2ad7c-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2ad7c-105">SYNTAX</span></span>

### <span data-ttu-id="2ad7c-106">Delimitador (padrão)</span><span class="sxs-lookup"><span data-stu-id="2ad7c-106">Delimiter (Default)</span></span>

```
Export-Csv [[-Path] <string>] [[-Delimiter] <char>] -InputObject <psobject> [-LiteralPath <string>]
 [-Force] [-NoClobber] [-Encoding <string>] [-Append] [-NoTypeInformation] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="2ad7c-107">parâmetro</span><span class="sxs-lookup"><span data-stu-id="2ad7c-107">UseCulture</span></span>

```
Export-Csv [[-Path] <string>] -InputObject <psobject> [-LiteralPath <string>] [-Force] [-NoClobber]
 [-Encoding <string>] [-Append] [-UseCulture] [-NoTypeInformation] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="2ad7c-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2ad7c-108">DESCRIPTION</span></span>

<span data-ttu-id="2ad7c-109">O `Export-CSV` cmdlet cria um arquivo CSV dos objetos que você envia.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-109">The `Export-CSV` cmdlet creates a CSV file of the objects that you submit.</span></span> <span data-ttu-id="2ad7c-110">Cada objeto é uma linha que inclui uma lista separada por vírgulas dos valores de Propriedade do objeto.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-110">Each object is a row that includes a comma-separated list of the object's property values.</span></span> <span data-ttu-id="2ad7c-111">Você pode usar o `Export-CSV` cmdlet para criar planilhas e compartilhar dados com programas que aceitam arquivos CSV como entrada.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-111">You can use the `Export-CSV` cmdlet to create spreadsheets and share data with programs that accept CSV files as input.</span></span>

<span data-ttu-id="2ad7c-112">Não formate objetos antes de enviá-los para o `Export-CSV` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-112">Do not format objects before sending them to the `Export-CSV` cmdlet.</span></span> <span data-ttu-id="2ad7c-113">Se `Export-CSV` o receber objetos formatados, o arquivo CSV conterá as propriedades de formato em vez das propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-113">If `Export-CSV` receives formatted objects the CSV file contains the format properties rather than the object properties.</span></span> <span data-ttu-id="2ad7c-114">Para exportar apenas as propriedades selecionadas de um objeto, use o `Select-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-114">To export only selected properties of an object, use the `Select-Object` cmdlet.</span></span>

## <span data-ttu-id="2ad7c-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="2ad7c-115">EXAMPLES</span></span>

### <span data-ttu-id="2ad7c-116">Exemplo 1: exportar Propriedades do processo para um arquivo CSV</span><span class="sxs-lookup"><span data-stu-id="2ad7c-116">Example 1: Export process properties to a CSV file</span></span>

<span data-ttu-id="2ad7c-117">Este exemplo seleciona objetos de **processo** com propriedades específicas, exporta os objetos para um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-117">This example selects **Process** objects with specific properties, exports the objects to a CSV file.</span></span>

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

<span data-ttu-id="2ad7c-118">O `Get-Process` cmdlet obtém os objetos de **processo** .</span><span class="sxs-lookup"><span data-stu-id="2ad7c-118">The `Get-Process` cmdlet gets the **Process** objects.</span></span> <span data-ttu-id="2ad7c-119">O parâmetro **Name** filtra a saída para incluir apenas os objetos de processo do WmiPrvSE.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-119">The **Name** parameter filters the output to include only the WmiPrvSE process objects.</span></span> <span data-ttu-id="2ad7c-120">Os objetos de processo são enviados por meio do pipeline para o `Select-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-120">The process objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="2ad7c-121">`Select-Object` usa o parâmetro **Property** para selecionar um subconjunto das propriedades do objeto de processo.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-121">`Select-Object` uses the **Property** parameter to select a subset of process object properties.</span></span> <span data-ttu-id="2ad7c-122">Os objetos de processo são enviados por meio do pipeline para o `Export-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-122">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="2ad7c-123">`Export-Csv` Converte os objetos de processo em uma série de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-123">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="2ad7c-124">O parâmetro **path** especifica que o arquivo de WmiData.csv é salvo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-124">The **Path** parameter specifies that the WmiData.csv file is saved in the current directory.</span></span> <span data-ttu-id="2ad7c-125">O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-125">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="2ad7c-126">O `Import-Csv` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-126">The `Import-Csv` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="2ad7c-127">Exemplo 2: exportar processos para um arquivo delimitado por vírgula</span><span class="sxs-lookup"><span data-stu-id="2ad7c-127">Example 2: Export processes to a comma-delimited file</span></span>

<span data-ttu-id="2ad7c-128">Este exemplo obtém objetos de **processo** e exporta os objetos para um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-128">This example gets **Process** objects and exports the objects to a CSV file.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","511","2203597099008","35364864","21979136","30048", ...
```

<span data-ttu-id="2ad7c-129">O `Get-Process` cmdlet obtém objetos de **processo** .</span><span class="sxs-lookup"><span data-stu-id="2ad7c-129">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="2ad7c-130">Os objetos de processo são enviados por meio do pipeline para o `Export-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-130">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="2ad7c-131">`Export-Csv` Converte os objetos de processo em uma série de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-131">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="2ad7c-132">O parâmetro **path** especifica que o arquivo de Processes.csv é salvo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-132">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="2ad7c-133">O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-133">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="2ad7c-134">O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-134">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="2ad7c-135">Exemplo 3: exportar processos para um arquivo delimitado por ponto e vírgula</span><span class="sxs-lookup"><span data-stu-id="2ad7c-135">Example 3: Export processes to a semicolon delimited file</span></span>

<span data-ttu-id="2ad7c-136">Este exemplo obtém objetos de **processo** e exporta os objetos para um arquivo com um delimitador de ponto-e-vírgula.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-136">This example gets **Process** objects and exports the objects to a file with a semicolon delimiter.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -Delimiter ';' -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name";"SI";"Handles";"VM";"WS";"PM";"NPM";"Path";"Parent";"Company";"CPU";"FileVersion"; ...
"ApplicationFrameHost";"4";"509";"2203595321344";"34807808";"21770240";"29504"; ...
```

<span data-ttu-id="2ad7c-137">O `Get-Process` cmdlet obtém objetos de **processo** .</span><span class="sxs-lookup"><span data-stu-id="2ad7c-137">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="2ad7c-138">Os objetos de processo são enviados por meio do pipeline para o `Export-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-138">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="2ad7c-139">`Export-Csv` Converte os objetos de processo em uma série de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-139">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="2ad7c-140">O parâmetro **path** especifica que o arquivo de Processes.csv é salvo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-140">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="2ad7c-141">O parâmetro **delimitador** especifica um ponto e vírgula para separar os valores da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-141">The **Delimiter** parameter specifies a semicolon to separate the string values.</span></span> <span data-ttu-id="2ad7c-142">O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-142">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="2ad7c-143">O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-143">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="2ad7c-144">Exemplo 4: exportar processos usando o separador de lista da cultura atual</span><span class="sxs-lookup"><span data-stu-id="2ad7c-144">Example 4: Export processes using the current culture's list separator</span></span>

<span data-ttu-id="2ad7c-145">Este exemplo obtém objetos de **processo** e exporta os objetos para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-145">This example gets **Process** objects and exports the objects to a file.</span></span> <span data-ttu-id="2ad7c-146">O delimitador é o separador de lista da cultura atual.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-146">The delimiter is the current culture's list separator.</span></span>

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-Process | Export-Csv -Path .\Processes.csv -UseCulture -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","511","2203597099008","35364864","21979136","30048", ...
```

<span data-ttu-id="2ad7c-147">O `Get-Culture` cmdlet usa as propriedades aninhadas **TextInfo** e **ListSeparator** e exibe o separador de lista padrão da cultura atual.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-147">The `Get-Culture` cmdlet uses the nested properties **TextInfo** and **ListSeparator** and displays the current culture's default list separator.</span></span> <span data-ttu-id="2ad7c-148">O `Get-Process` cmdlet obtém objetos de **processo** .</span><span class="sxs-lookup"><span data-stu-id="2ad7c-148">The `Get-Process` cmdlet gets **Process** objects.</span></span>
<span data-ttu-id="2ad7c-149">Os objetos de processo são enviados por meio do pipeline para o `Export-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-149">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="2ad7c-150">`Export-Csv` Converte os objetos de processo em uma série de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-150">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="2ad7c-151">O parâmetro **path** especifica que o arquivo de Processes.csv é salvo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-151">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="2ad7c-152">O parâmetro **UseCulture** usa o separador de lista padrão da cultura atual como o delimitador.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-152">The **UseCulture** parameter uses the current culture's default list separator as the delimiter.</span></span> <span data-ttu-id="2ad7c-153">O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-153">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="2ad7c-154">O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-154">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="2ad7c-155">Exemplo 5: exportar processos com informações de tipo</span><span class="sxs-lookup"><span data-stu-id="2ad7c-155">Example 5: Export processes with type information</span></span>

<span data-ttu-id="2ad7c-156">Este exemplo explica como incluir as informações de cabeçalho de **#TYPE** em um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-156">This example explains how to include the **#TYPE** header information in a CSV file.</span></span> <span data-ttu-id="2ad7c-157">O cabeçalho de **#TYPE** é o padrão nas versões anteriores ao PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-157">The **#TYPE** header is the default in versions prior to PowerShell 6.0.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv
Get-Content -Path .\Processes.csv
```

```Output
#TYPE System.Diagnostics.Process
"Name","SI","Handles","VM","WS","PM","NPM","Path","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","507","2203595001856","35139584","20934656","29504", ...
```

<span data-ttu-id="2ad7c-158">O `Get-Process` cmdlet obtém objetos de **processo** .</span><span class="sxs-lookup"><span data-stu-id="2ad7c-158">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="2ad7c-159">Os objetos de processo são enviados por meio do pipeline para o `Export-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-159">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="2ad7c-160">`Export-Csv` Converte os objetos de processo em uma série de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-160">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="2ad7c-161">O parâmetro **path** especifica que o arquivo de Processes.csv é salvo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-161">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="2ad7c-162">O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-162">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="2ad7c-163">Exemplo 6: exportar e acrescentar objetos a um arquivo CSV</span><span class="sxs-lookup"><span data-stu-id="2ad7c-163">Example 6: Export and append objects to a CSV file</span></span>

<span data-ttu-id="2ad7c-164">Este exemplo descreve como exportar objetos para um arquivo CSV e usar o parâmetro **Append** para adicionar objetos a um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-164">This example describes how to export objects to a CSV file and use the **Append** parameter to add objects to an existing file.</span></span>

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

<span data-ttu-id="2ad7c-165">O `Get-Service` cmdlet obtém os objetos de serviço.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-165">The `Get-Service` cmdlet gets service objects.</span></span> <span data-ttu-id="2ad7c-166">O parâmetro **DisplayName** retorna serviços que contêm o aplicativo Word.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-166">The **DisplayName** parameter returns services that contain the word Application.</span></span> <span data-ttu-id="2ad7c-167">Os objetos de serviço são enviados pelo pipeline para o `Select-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-167">The service objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="2ad7c-168">`Select-Object` usa o parâmetro **Property** para especificar as propriedades **DisplayName** e **status** .</span><span class="sxs-lookup"><span data-stu-id="2ad7c-168">`Select-Object` uses the **Property** parameter to specify the **DisplayName** and **Status** properties.</span></span> <span data-ttu-id="2ad7c-169">A `$AppService` variável armazena os objetos.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-169">The `$AppService` variable stores the objects.</span></span>

<span data-ttu-id="2ad7c-170">Os `$AppService` objetos são enviados para o pipeline para o `Export-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-170">The `$AppService` objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="2ad7c-171">`Export-Csv` Converte os objetos de serviço em uma série de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-171">`Export-Csv` converts the service objects to a series of CSV strings.</span></span> <span data-ttu-id="2ad7c-172">O parâmetro **path** especifica que o arquivo de Services.csv é salvo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-172">The **Path** parameter specifies that the Services.csv file is saved in the current directory.</span></span> <span data-ttu-id="2ad7c-173">O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-173">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="2ad7c-174">O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-174">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

<span data-ttu-id="2ad7c-175">Os `Get-Service` `Select-Object` cmdlets e são repetidos para serviços que contêm a palavra Windows.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-175">The `Get-Service` and `Select-Object` cmdlets are repeated for services that contain the word Windows.</span></span> <span data-ttu-id="2ad7c-176">A `$WinService` variável armazena os objetos de serviço.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-176">The `$WinService` variable stores the service objects.</span></span> <span data-ttu-id="2ad7c-177">O `Export-Csv` cmdlet usa o parâmetro **Append** para especificar que os `$WinService` objetos sejam adicionados ao arquivo de Services.csv existente.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-177">The `Export-Csv` cmdlet uses the **Append** parameter to specify that the `$WinService` objects are added to the existing Services.csv file.</span></span> <span data-ttu-id="2ad7c-178">O `Get-Content` cmdlet é repetido para exibir o arquivo atualizado que inclui os dados acrescentados.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-178">The `Get-Content` cmdlet is repeated to display the updated file that includes the appended data.</span></span>

### <span data-ttu-id="2ad7c-179">Exemplo 7: o cmdlet Format dentro de um pipeline cria resultados inesperados</span><span class="sxs-lookup"><span data-stu-id="2ad7c-179">Example 7: Format cmdlet within a pipeline creates unexpected results</span></span>

<span data-ttu-id="2ad7c-180">Este exemplo mostra por que é importante não usar um cmdlet de formato em um pipeline.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-180">This example shows why it is important not to use a format cmdlet within a pipeline.</span></span> <span data-ttu-id="2ad7c-181">Quando a saída inesperada for recebida, solucione o problema da sintaxe do pipeline.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-181">When unexpected output is received, troubleshoot the pipeline syntax.</span></span>

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

<span data-ttu-id="2ad7c-182">O `Get-Date` cmdlet obtém o objeto **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="2ad7c-182">The `Get-Date` cmdlet gets the **DateTime** object.</span></span> <span data-ttu-id="2ad7c-183">O objeto é enviado ao pipeline para o `Select-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-183">The object is sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="2ad7c-184">`Select-Object` usa o parâmetro **Property** para selecionar um subconjunto das propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-184">`Select-Object` uses the **Property** parameter to select a subset of object properties.</span></span> <span data-ttu-id="2ad7c-185">O objeto é enviado ao pipeline para o `Export-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-185">The object is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="2ad7c-186">`Export-Csv` Converte o objeto em um formato CSV.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-186">`Export-Csv` converts the object to a CSV format.</span></span> <span data-ttu-id="2ad7c-187">O parâmetro **path** especifica que o arquivo de DateTime.csv é salvo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-187">The **Path** parameter specifies that the DateTime.csv file is saved in the current directory.</span></span> <span data-ttu-id="2ad7c-188">O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-188">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="2ad7c-189">O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o arquivo CSV localizado no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-189">The `Get-Content` cmdlet uses the **Path** parameter to display the CSV file located in the current directory.</span></span>

<span data-ttu-id="2ad7c-190">Quando o `Format-Table` cmdlet é usado no pipeline para selecionar propriedades, resultados inesperados são recebidos.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-190">When the `Format-Table` cmdlet is used within the pipeline to select properties unexpected results are received.</span></span> <span data-ttu-id="2ad7c-191">`Format-Table` envia objetos de formato de tabela por meio do pipeline para o `Export-Csv` cmdlet, em vez do objeto **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="2ad7c-191">`Format-Table` sends table format objects down the pipeline to the `Export-Csv` cmdlet rather than the **DateTime** object.</span></span> <span data-ttu-id="2ad7c-192">`Export-Csv` Converte os objetos de formato de tabela em uma série de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-192">`Export-Csv` converts the table format objects to a series of CSV strings.</span></span> <span data-ttu-id="2ad7c-193">O `Get-Content` cmdlet exibe o arquivo CSV que contém os objetos de formato de tabela.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-193">The `Get-Content` cmdlet displays the CSV file which contains the table format objects.</span></span>

### <span data-ttu-id="2ad7c-194">Exemplo 8: usando o parâmetro Force para substituir arquivos somente leitura</span><span class="sxs-lookup"><span data-stu-id="2ad7c-194">Example 8: Using the Force parameter to overwrite read-only files</span></span>

<span data-ttu-id="2ad7c-195">Este exemplo cria um arquivo somente leitura vazio e usa o parâmetro **Force** para atualizar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-195">This example creates an empty, read-only file and uses the **Force** parameter to update the file.</span></span>

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

<span data-ttu-id="2ad7c-196">O `New-Item` cmdlet usa os parâmetros **Path** e **ItemType** para criar o arquivo de ReadOnly.csv no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-196">The `New-Item` cmdlet uses the **Path** and **ItemType** parameters to create the ReadOnly.csv file in the current directory.</span></span> <span data-ttu-id="2ad7c-197">O `Set-ItemProperty` cmdlet usa os parâmetros **Name** e **Value** para alterar a propriedade **IsReadOnly** do arquivo para true.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-197">The `Set-ItemProperty` cmdlet uses the **Name** and **Value** parameters to change the file's **IsReadOnly** property to true.</span></span> <span data-ttu-id="2ad7c-198">O `Get-Process` cmdlet obtém objetos de **processo** .</span><span class="sxs-lookup"><span data-stu-id="2ad7c-198">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="2ad7c-199">Os objetos de processo são enviados por meio do pipeline para o `Export-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-199">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="2ad7c-200">`Export-Csv` Converte os objetos de processo em uma série de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-200">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="2ad7c-201">O parâmetro **path** especifica que o arquivo de ReadOnly.csv é salvo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-201">The **Path** parameter specifies that the ReadOnly.csv file is saved in the current directory.</span></span> <span data-ttu-id="2ad7c-202">O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-202">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="2ad7c-203">A saída mostra que o arquivo não foi gravado porque o acesso foi negado.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-203">The output shows that the file is not written because access is denied.</span></span>

<span data-ttu-id="2ad7c-204">O parâmetro **Force** é adicionado ao `Export-Csv` cmdlet para forçar a exportação a gravar no arquivo.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-204">The **Force** parameter is added to the `Export-Csv` cmdlet to force the export to write to the file.</span></span> <span data-ttu-id="2ad7c-205">O `Get-Content` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-205">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="2ad7c-206">Exemplo 9: usando o parâmetro Force com Append</span><span class="sxs-lookup"><span data-stu-id="2ad7c-206">Example 9: Using the Force parameter with Append</span></span>

<span data-ttu-id="2ad7c-207">Este exemplo mostra como usar os parâmetros **Force** e **Append** .</span><span class="sxs-lookup"><span data-stu-id="2ad7c-207">This example shows how to use the **Force** and **Append** parameters.</span></span> <span data-ttu-id="2ad7c-208">Quando esses parâmetros são combinados, as propriedades de objeto incompatíveis podem ser gravadas em um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-208">When these parameters are combined, mismatched object properties can be written to a CSV file.</span></span>

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

<span data-ttu-id="2ad7c-209">Uma expressão cria o **PSCustomObject** com propriedades **Name** e **version** .</span><span class="sxs-lookup"><span data-stu-id="2ad7c-209">An expression creates the **PSCustomObject** with **Name** and **Version** properties.</span></span> <span data-ttu-id="2ad7c-210">Os valores são armazenados na `$Content` variável.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-210">The values are stored in the `$Content` variable.</span></span> <span data-ttu-id="2ad7c-211">A `$Content` variável é enviada ao pipeline para o `Export-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-211">The `$Content` variable is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="2ad7c-212">`Export-Csv` usa o parâmetro **path** e salva o arquivo ParmFile.csv no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-212">`Export-Csv` uses the **Path** parameter and saves the ParmFile.csv file in the current directory.</span></span> <span data-ttu-id="2ad7c-213">O parâmetro **NoTypeInformation** remove o cabeçalho de informações **#TYPE** da saída CSV e não é necessário no PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-213">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

<span data-ttu-id="2ad7c-214">Outra expressão cria um **PSCustomObject** com as propriedades **Name** e **Edition** .</span><span class="sxs-lookup"><span data-stu-id="2ad7c-214">Another expression creates a **PSCustomObject** with the **Name** and **Edition** properties.</span></span> <span data-ttu-id="2ad7c-215">Os valores são armazenados na `$AdditionalContent` variável.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-215">The values are stored in the `$AdditionalContent` variable.</span></span> <span data-ttu-id="2ad7c-216">A `$AdditionalContent` variável é enviada ao pipeline para o `Export-Csv` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-216">The `$AdditionalContent` variable is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="2ad7c-217">O parâmetro **Append** é usado para adicionar os dados ao arquivo.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-217">The **Append** parameter is used to add the data to the file.</span></span> <span data-ttu-id="2ad7c-218">O acréscimo falha porque há uma incompatibilidade de nome de propriedade entre a **versão** e a **edição**.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-218">The append fails because there is a property name mismatch between **Version** and **Edition**.</span></span>

<span data-ttu-id="2ad7c-219">O `Export-Csv` parâmetro **Force** do cmdlet é usado para forçar a exportação a gravar no arquivo.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-219">The `Export-Csv` cmdlet **Force** parameter is used to force the export to write to the file.</span></span> <span data-ttu-id="2ad7c-220">A propriedade de **edição** é descartada.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-220">The **Edition** property is discarded.</span></span> <span data-ttu-id="2ad7c-221">O `Import-Csv` cmdlet usa o parâmetro **Path** para exibir o arquivo localizado no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-221">The `Import-Csv` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

## <span data-ttu-id="2ad7c-222">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2ad7c-222">PARAMETERS</span></span>

### <span data-ttu-id="2ad7c-223">-Acrescentar</span><span class="sxs-lookup"><span data-stu-id="2ad7c-223">-Append</span></span>

<span data-ttu-id="2ad7c-224">Use esse parâmetro para que `Export-CSV` o adicione a saída de CSV ao final do arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-224">Use this parameter so that `Export-CSV` adds CSV output to the end of the specified file.</span></span> <span data-ttu-id="2ad7c-225">Sem esse parâmetro, `Export-CSV` o substitui o conteúdo do arquivo sem aviso.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-225">Without this parameter, `Export-CSV` replaces the file contents without warning.</span></span>

<span data-ttu-id="2ad7c-226">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-226">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="2ad7c-227">-Delimitador</span><span class="sxs-lookup"><span data-stu-id="2ad7c-227">-Delimiter</span></span>

<span data-ttu-id="2ad7c-228">Especifica um delimitador para separar os valores da propriedade.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-228">Specifies a delimiter to separate the property values.</span></span> <span data-ttu-id="2ad7c-229">O padrão é uma vírgula ( `,` ).</span><span class="sxs-lookup"><span data-stu-id="2ad7c-229">The default is a comma (`,`).</span></span> <span data-ttu-id="2ad7c-230">Insira um caractere, como dois-pontos ( `:` ).</span><span class="sxs-lookup"><span data-stu-id="2ad7c-230">Enter a character, such as a colon (`:`).</span></span> <span data-ttu-id="2ad7c-231">Para especificar um ponto e vírgula ( `;` ), coloque-o entre aspas.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-231">To specify a semicolon (`;`), enclose it in quotation marks.</span></span>

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

### <span data-ttu-id="2ad7c-232">-Codificação</span><span class="sxs-lookup"><span data-stu-id="2ad7c-232">-Encoding</span></span>

<span data-ttu-id="2ad7c-233">Especifica o tipo de codificação para o arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-233">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="2ad7c-234">O valor padrão é `ASCII`.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-234">The default value is `ASCII`.</span></span>

<span data-ttu-id="2ad7c-235">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="2ad7c-235">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="2ad7c-236">`ASCII` Usa conjunto de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="2ad7c-236">`ASCII` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="2ad7c-237">`BigEndianUnicode` Usa UTF-16 com a ordem de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-237">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="2ad7c-238">`Default` Usa a codificação que corresponde à página de código ativa do sistema (geralmente ANSI).</span><span class="sxs-lookup"><span data-stu-id="2ad7c-238">`Default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="2ad7c-239">`OEM` Usa a codificação que corresponde à página de código OEM atual do sistema.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-239">`OEM` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="2ad7c-240">`Unicode` Usa UTF-16 com a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-240">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="2ad7c-241">`UTF7` Usa UTF-7.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-241">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="2ad7c-242">`UTF8` Usa UTF-8.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-242">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="2ad7c-243">`UTF32` Usa UTF-32 com a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-243">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

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

### <span data-ttu-id="2ad7c-244">-Force</span><span class="sxs-lookup"><span data-stu-id="2ad7c-244">-Force</span></span>

<span data-ttu-id="2ad7c-245">Esse parâmetro permite `Export-Csv` substituir arquivos pelo atributo **somente leitura** .</span><span class="sxs-lookup"><span data-stu-id="2ad7c-245">This parameter allows `Export-Csv` to overwrite files with the **Read Only** attribute.</span></span>

<span data-ttu-id="2ad7c-246">Quando os parâmetros **Force** e **Append** são combinados, os objetos que contêm propriedades incompatíveis podem ser gravados em um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-246">When **Force** and **Append** parameters are combined, objects that contain mismatched properties can be written to a CSV file.</span></span> <span data-ttu-id="2ad7c-247">Somente as propriedades que correspondem são gravadas no arquivo.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-247">Only the properties that match are written to the file.</span></span> <span data-ttu-id="2ad7c-248">As propriedades incompatíveis são descartadas.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-248">The mismatched properties are discarded.</span></span>

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

### <span data-ttu-id="2ad7c-249">-InputObject</span><span class="sxs-lookup"><span data-stu-id="2ad7c-249">-InputObject</span></span>

<span data-ttu-id="2ad7c-250">Especifica os objetos a exportar como cadeias CSV.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-250">Specifies the objects to export as CSV strings.</span></span> <span data-ttu-id="2ad7c-251">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-251">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="2ad7c-252">Você também pode canalizar objetos para `Export-CSV` .</span><span class="sxs-lookup"><span data-stu-id="2ad7c-252">You can also pipe objects to `Export-CSV`.</span></span>

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

### <span data-ttu-id="2ad7c-253">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="2ad7c-253">-LiteralPath</span></span>

<span data-ttu-id="2ad7c-254">Especifica o caminho para o arquivo de saída CSV.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-254">Specifies the path to the CSV output file.</span></span> <span data-ttu-id="2ad7c-255">Ao contrário de **Path**, o valor do parâmetro **LiteralPath** é usado exatamente como foi digitado.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-255">Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="2ad7c-256">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-256">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="2ad7c-257">Se o caminho incluir caracteres de escape, use aspas simples.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-257">If the path includes escape characters, use single quotation marks.</span></span> <span data-ttu-id="2ad7c-258">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-258">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="2ad7c-259">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="2ad7c-259">-NoClobber</span></span>

<span data-ttu-id="2ad7c-260">Use esse parâmetro para que `Export-CSV` o não substitua um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-260">Use this parameter so that `Export-CSV` does not overwrite an existing file.</span></span> <span data-ttu-id="2ad7c-261">Por padrão, se o arquivo existir no caminho especificado, `Export-CSV` o substituirá o arquivo sem aviso.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-261">By default, if the file exists in the specified path, `Export-CSV` overwrites the file without warning.</span></span>

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

### <span data-ttu-id="2ad7c-262">-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="2ad7c-262">-NoTypeInformation</span></span>

<span data-ttu-id="2ad7c-263">Remove o cabeçalho de informações **#TYPE** da saída.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-263">Removes the **#TYPE** information header from the output.</span></span> <span data-ttu-id="2ad7c-264">Esse parâmetro se tornou o padrão no PowerShell 6,0 e está incluído para compatibilidade com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-264">This parameter became the default in PowerShell 6.0 and is included for backwards compatibility.</span></span>

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

### <span data-ttu-id="2ad7c-265">-Path</span><span class="sxs-lookup"><span data-stu-id="2ad7c-265">-Path</span></span>

<span data-ttu-id="2ad7c-266">Um parâmetro necessário que especifica o local para salvar o arquivo de saída CSV.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-266">A required parameter that specifies the location to save the CSV output file.</span></span>

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

### <span data-ttu-id="2ad7c-267">-UseCulture</span><span class="sxs-lookup"><span data-stu-id="2ad7c-267">-UseCulture</span></span>

<span data-ttu-id="2ad7c-268">Usa o separador de lista para a cultura atual como o delimitador de item.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-268">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="2ad7c-269">Para localizar o separador de lista para uma cultura, use o seguinte comando: `(Get-Culture).TextInfo.ListSeparator` .</span><span class="sxs-lookup"><span data-stu-id="2ad7c-269">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

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

### <span data-ttu-id="2ad7c-270">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2ad7c-270">-Confirm</span></span>

<span data-ttu-id="2ad7c-271">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-271">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2ad7c-272">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2ad7c-272">-WhatIf</span></span>

<span data-ttu-id="2ad7c-273">Impede que o cmdlet seja processado ou faça alterações.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-273">Prevents the cmdlet from being processed or making changes.</span></span> <span data-ttu-id="2ad7c-274">A saída mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-274">The output shows what would happen if the cmdlet were run.</span></span>

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

### <span data-ttu-id="2ad7c-275">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2ad7c-275">CommonParameters</span></span>

<span data-ttu-id="2ad7c-276">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-276">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2ad7c-277">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2ad7c-277">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2ad7c-278">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="2ad7c-278">INPUTS</span></span>

### <span data-ttu-id="2ad7c-279">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="2ad7c-279">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="2ad7c-280">É possível canalizar qualquer objeto com um adaptador de sistema de tipo estendido (ETS) para o `Export-CSV` .</span><span class="sxs-lookup"><span data-stu-id="2ad7c-280">You can pipe any object with an Extended Type System (ETS) adapter to `Export-CSV`.</span></span>

## <span data-ttu-id="2ad7c-281">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="2ad7c-281">OUTPUTS</span></span>

### <span data-ttu-id="2ad7c-282">System.String</span><span class="sxs-lookup"><span data-stu-id="2ad7c-282">System.String</span></span>

<span data-ttu-id="2ad7c-283">A lista CSV é enviada para o arquivo designado no parâmetro Path.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-283">The CSV list is sent to the file designated in the Path parameter.</span></span>

## <span data-ttu-id="2ad7c-284">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="2ad7c-284">NOTES</span></span>

<span data-ttu-id="2ad7c-285">O `Export-CSV` cmdlet converte os objetos que você envia em uma série de cadeias de caracteres CSV e salva-os no arquivo de texto especificado.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-285">The `Export-CSV` cmdlet converts the objects that you submit into a series of CSV strings and saves them in the specified text file.</span></span> <span data-ttu-id="2ad7c-286">Você pode usar `Export-CSV` o para salvar objetos em um arquivo CSV e, em seguida, usar o `Import-Csv` cmdlet para criar objetos a partir do arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-286">You can use `Export-CSV` to save objects in a CSV file and then use the `Import-Csv` cmdlet to create objects from the CSV file.</span></span>

<span data-ttu-id="2ad7c-287">No arquivo CSV, cada objeto é representado por uma lista separada por vírgulas dos valores de propriedade do objeto.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-287">In the CSV file, each object is represented by a comma-separated list of the property values of the object.</span></span> <span data-ttu-id="2ad7c-288">Os valores de propriedade são convertidos em cadeias de caracteres usando o método **ToString ()** .</span><span class="sxs-lookup"><span data-stu-id="2ad7c-288">The property values are converted to strings using the **ToString()** method.</span></span> <span data-ttu-id="2ad7c-289">As cadeias de caracteres são representadas pelo nome do valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-289">The strings are represented by the property value name.</span></span> <span data-ttu-id="2ad7c-290">' Export-CSV não exporta os métodos do objeto.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-290">\`Export-CSV does not export the methods of the object.</span></span>

<span data-ttu-id="2ad7c-291">As cadeias de caracteres CSV são saídas da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="2ad7c-291">The CSV strings are output as follows:</span></span>

- <span data-ttu-id="2ad7c-292">Por padrão, a primeira cadeia de caracteres contém o cabeçalho de informações **#TYPE** seguido pelo nome totalmente qualificado do tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-292">By default the first string contains the **#TYPE** information header followed by the object type's fully qualified name.</span></span> <span data-ttu-id="2ad7c-293">Por exemplo, **#TYPE System. Diagnostics. Process**.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-293">For example, **#TYPE System.Diagnostics.Process**.</span></span>
- <span data-ttu-id="2ad7c-294">Se **NoTypeInformation** for usado, a primeira cadeia de caracteres incluirá os cabeçalhos de coluna.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-294">If **NoTypeInformation** is used the first string includes the column headers.</span></span> <span data-ttu-id="2ad7c-295">Os cabeçalhos contêm os nomes de Propriedade do primeiro objeto como uma lista separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-295">The headers contain the first object's property names as a comma-separated list.</span></span>
- <span data-ttu-id="2ad7c-296">As cadeias de caracteres restantes contêm listas separadas por vírgulas dos valores de propriedade de cada objeto.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-296">The remaining strings contain comma-separated lists of each object's property values.</span></span>

<span data-ttu-id="2ad7c-297">Quando você envia vários objetos ao `Export-CSV` , `Export-CSV` o organiza o arquivo com base nas propriedades do primeiro objeto que você envia.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-297">When you submit multiple objects to `Export-CSV`, `Export-CSV` organizes the file based on the properties of the first object that you submit.</span></span> <span data-ttu-id="2ad7c-298">Se os objetos restantes não tiverem uma das propriedades especificadas, o valor da propriedade desse primeiro objeto será nulo, condição esta representada por duas vírgulas consecutivas.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-298">If the remaining objects do not have one of the specified properties, the property value of that object is null, as represented by two consecutive commas.</span></span> <span data-ttu-id="2ad7c-299">Se os objetos restantes têm propriedades adicionais, os valores de propriedade não são incluídos no arquivo.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-299">If the remaining objects have additional properties, those property values are not included in the file.</span></span>

<span data-ttu-id="2ad7c-300">Você pode usar o `Import-Csv` cmdlet para recriar objetos a partir de cadeias de caracteres CSV nos arquivos.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-300">You can use the `Import-Csv` cmdlet to recreate objects from the CSV strings in the files.</span></span> <span data-ttu-id="2ad7c-301">Os objetos resultantes são versões em CSV dos objetos originais, que consistem em representações dos valores das propriedades em cadeia, sem métodos.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-301">The resulting objects are CSV versions of the original objects that consist of string representations of the property values and no methods.</span></span>

<span data-ttu-id="2ad7c-302">Os `ConvertTo-Csv` `ConvertFrom-Csv` cmdlets e convertem objetos em cadeias de caracteres CSV e de cadeias de caracteres CSV.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-302">The `ConvertTo-Csv` and `ConvertFrom-Csv` cmdlets convert objects to CSV strings and from CSV strings.</span></span> <span data-ttu-id="2ad7c-303">`Export-CSV` é o mesmo `ConvertTo-CSV` que, exceto pelo fato de salvar as cadeias de caracteres CSV em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="2ad7c-303">`Export-CSV` is the same as `ConvertTo-CSV`, except that it saves the CSV strings in a file.</span></span>

## <span data-ttu-id="2ad7c-304">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="2ad7c-304">RELATED LINKS</span></span>

[<span data-ttu-id="2ad7c-305">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="2ad7c-305">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="2ad7c-306">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="2ad7c-306">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="2ad7c-307">Format-Table</span><span class="sxs-lookup"><span data-stu-id="2ad7c-307">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="2ad7c-308">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="2ad7c-308">Import-Csv</span></span>](Import-Csv.md)

[<span data-ttu-id="2ad7c-309">Select-Object</span><span class="sxs-lookup"><span data-stu-id="2ad7c-309">Select-Object</span></span>](Select-Object.md)
