---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/sort-object?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Sort-Object
ms.openlocfilehash: 1d27641f94d82b85bab694b392c0f09bb3265517
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2020
ms.locfileid: "93195143"
---
# <span data-ttu-id="3ba1e-103">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="3ba1e-103">Sort-Object</span></span>

## <span data-ttu-id="3ba1e-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="3ba1e-104">SYNOPSIS</span></span>
<span data-ttu-id="3ba1e-105">Classifica os objetos por valores de propriedade.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-105">Sorts objects by property values.</span></span>

## <span data-ttu-id="3ba1e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3ba1e-106">SYNTAX</span></span>

### <span data-ttu-id="3ba1e-107">Padrão (padrão)</span><span class="sxs-lookup"><span data-stu-id="3ba1e-107">Default (Default)</span></span>

```
Sort-Object [[-Property] <Object[]>] [-Descending] [-Unique] [-InputObject <psobject>]
 [-Culture <string>] [-CaseSensitive] [<CommonParameters>]
```

## <span data-ttu-id="3ba1e-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3ba1e-108">DESCRIPTION</span></span>

<span data-ttu-id="3ba1e-109">O `Sort-Object` cmdlet classifica os objetos em ordem crescente ou decrescente com base em valores de propriedade de objeto.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-109">The `Sort-Object` cmdlet sorts objects in ascending or descending order based on object property values.</span></span> <span data-ttu-id="3ba1e-110">Se as propriedades de classificação não forem incluídas em um comando, o PowerShell usará as propriedades de classificação padrão do primeiro objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-110">If sort properties are not included in a command, PowerShell uses default sort properties of the first input object.</span></span> <span data-ttu-id="3ba1e-111">Se o tipo do objeto de entrada não tiver nenhuma propriedade de classificação padrão, o PowerShell tentará comparar os próprios objetos.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-111">If the type of the input object has no default sort properties, PowerShell attempts to compare the objects themselves.</span></span> <span data-ttu-id="3ba1e-112">Para obter mais informações, consulte a seção [observações](#notes) .</span><span class="sxs-lookup"><span data-stu-id="3ba1e-112">For more information, see the [Notes](#notes) section.</span></span>

<span data-ttu-id="3ba1e-113">Você pode classificar objetos por uma única propriedade ou várias propriedades.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-113">You can sort objects by a single property or multiple properties.</span></span> <span data-ttu-id="3ba1e-114">Várias propriedades usam tabelas de hash para classificar em ordem crescente, ordem decrescente ou uma combinação de ordens de classificação.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-114">Multiple properties use hash tables to sort in ascending order, descending order, or a combination of sort orders.</span></span> <span data-ttu-id="3ba1e-115">As propriedades são classificadas como diferencia maiúsculas de minúsculas ou não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-115">Properties are sorted as case-sensitive or case-insensitive.</span></span> <span data-ttu-id="3ba1e-116">Use o parâmetro **exclusivo** para eliminar duplicatas da saída.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-116">Use the **Unique** parameter to eliminate duplicates from the output.</span></span>

## <span data-ttu-id="3ba1e-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="3ba1e-117">EXAMPLES</span></span>

### <span data-ttu-id="3ba1e-118">Exemplo 1: classificar o diretório atual por nome</span><span class="sxs-lookup"><span data-stu-id="3ba1e-118">Example 1: Sort the current directory by name</span></span>

<span data-ttu-id="3ba1e-119">Esse comando classifica os arquivos e subdiretórios em um diretório.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-119">This command sorts the files and subdirectories in a directory.</span></span>

```
PS> Get-ChildItem -Path C:\Test | Sort-Object

    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/13/2019     13:26             20 Bfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-a----         2/1/2019     08:43            183 CreateTestFile.ps1
d-----        2/25/2019     18:25                Files
d-----        2/25/2019     18:24                Logs
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
-a----        2/12/2019     16:24             23 Zsystemlog.log
```

<span data-ttu-id="3ba1e-120">O `Get-ChildItem` cmdlet obtém os arquivos e subdiretórios do diretório especificado pelo parâmetro **Path** , **C:\test** .</span><span class="sxs-lookup"><span data-stu-id="3ba1e-120">The `Get-ChildItem` cmdlet gets the files and subdirectories from the directory specified by the **Path** parameter, **C:\Test** .</span></span> <span data-ttu-id="3ba1e-121">Os objetos são enviados para o pipeline para o `Sort-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-121">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span>
<span data-ttu-id="3ba1e-122">`Sort-Object` não especifica uma propriedade para que a saída seja classificada pela propriedade de classificação padrão, **Name** .</span><span class="sxs-lookup"><span data-stu-id="3ba1e-122">`Sort-Object` does not specify a property so the output is sorted by the default sort property, **Name** .</span></span>

### <span data-ttu-id="3ba1e-123">Exemplo 2: classificar o diretório atual por comprimento do arquivo</span><span class="sxs-lookup"><span data-stu-id="3ba1e-123">Example 2: Sort the current directory by file length</span></span>

<span data-ttu-id="3ba1e-124">Esse comando exibe os arquivos no diretório atual por comprimento em ordem crescente.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-124">This command displays the files in the current directory by length in ascending order.</span></span>

```
PS> Get-ChildItem -Path C:\Test -File | Sort-Object -Property Length

    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     13:26             20 Bfile.txt
-a----        2/12/2019     16:24             23 Zsystemlog.log
-a----        2/13/2019     08:55             26 anotherfile.txt
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
-a----         2/1/2019     08:43            183 CreateTestFile.ps1
-a----        2/12/2019     15:40         118014 Command.txt
```

<span data-ttu-id="3ba1e-125">O `Get-ChildItem` cmdlet obtém os arquivos do diretório especificado pelo parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="3ba1e-125">The `Get-ChildItem` cmdlet gets the files from the directory specified by the **Path** parameter.</span></span>
<span data-ttu-id="3ba1e-126">O parâmetro **File** especifica que `Get-ChildItem` somente Obtém os objetos de arquivo.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-126">The **File** parameter specifies that `Get-ChildItem` only gets file objects.</span></span> <span data-ttu-id="3ba1e-127">Os objetos são enviados para o pipeline para o `Sort-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-127">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="3ba1e-128">`Sort-Object` usa o parâmetro **Length** para classificar os arquivos por comprimento em ordem crescente.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-128">`Sort-Object` uses the **Length** parameter to sort the files by length in ascending order.</span></span>

### <span data-ttu-id="3ba1e-129">Exemplo 3: classificar processos por uso de memória</span><span class="sxs-lookup"><span data-stu-id="3ba1e-129">Example 3: Sort processes by memory usage</span></span>

<span data-ttu-id="3ba1e-130">Este exemplo exibe processos com o maior uso de memória com base em seu tamanho de conjunto de trabalho (WS).</span><span class="sxs-lookup"><span data-stu-id="3ba1e-130">This example displays processes with the highest memory usage based on their working set (WS) size.</span></span>

```
PS> Get-Process | Sort-Object -Property WS | Select-Object -Last 5

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    136   193.92     217.11     889.16   87492   8 OUTLOOK
    112   347.73     297.02      95.19  106908   8 Teams
    206   266.54     323.71      37.17   60620   8 MicrosoftEdgeCP
     35   552.19     549.94     131.66    6552   8 Code
      0     1.43     595.12       0.00    2780   0 Memory Compression
```

<span data-ttu-id="3ba1e-131">O `Get-Process` cmdlet obtém a lista de processos em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-131">The `Get-Process` cmdlet gets the list of processes running on the computer.</span></span> <span data-ttu-id="3ba1e-132">Os objetos de processo são enviados por meio do pipeline para o `Sort-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-132">The process objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="3ba1e-133">`Sort-Object` usa o parâmetro **Property** para classificar os objetos por **WS** .</span><span class="sxs-lookup"><span data-stu-id="3ba1e-133">`Sort-Object` uses the **Property** parameter to sort the objects by **WS** .</span></span> <span data-ttu-id="3ba1e-134">Os objetos são enviados para o pipeline para o `Select-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-134">The objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span>
<span data-ttu-id="3ba1e-135">`Select-Object` usa o **último** parâmetro para especificar os últimos cinco objetos, que são os objetos com o maior uso do **WS** .</span><span class="sxs-lookup"><span data-stu-id="3ba1e-135">`Select-Object` uses the **Last** parameter to specify the last five objects, which are the objects with the highest **WS** usage.</span></span>

### <span data-ttu-id="3ba1e-136">Exemplo 4: classificar objetos HistoryInfo por ID</span><span class="sxs-lookup"><span data-stu-id="3ba1e-136">Example 4: Sort HistoryInfo objects by Id</span></span>

<span data-ttu-id="3ba1e-137">Esse comando classifica os objetos **HistoryInfo** da sessão do PowerShell usando a propriedade **ID** .</span><span class="sxs-lookup"><span data-stu-id="3ba1e-137">This command sorts the PowerShell session's **HistoryInfo** objects using the **Id** property.</span></span> <span data-ttu-id="3ba1e-138">Cada sessão do PowerShell tem seu próprio histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-138">Each PowerShell session has its own command history.</span></span>

```
PS> Get-History | Sort-Object -Property Id -Descending

  Id CommandLine
  -- -----------
  10 Get-Command Sort-Object -Syntax
   9 $PSVersionTable
   8 Get-Command Sort-Object -Syntax
   7 Get-Command Sort-Object -ShowCommandInfo
   6 Get-ChildItem -Path C:\Test | Sort-Object -Property Length
   5 Get-Help Clear-History -online
   4 Get-Help Clear-History -full
   3 Get-ChildItem | Get-Member
   2 Get-Command Sort-Object -Syntax
   1 Set-Location C:\Test\
```

<span data-ttu-id="3ba1e-139">O `Get-History` cmdlet obtém os objetos de histórico da sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-139">The `Get-History` cmdlet gets the history objects from the current PowerShell session.</span></span> <span data-ttu-id="3ba1e-140">Os objetos são enviados para o pipeline para o `Sort-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-140">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="3ba1e-141">`Sort-Object` usa o parâmetro **Property** para classificar os objetos por **ID** . O parâmetro **decrescente** classifica o histórico de comandos do mais recente para o mais antigo.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-141">`Sort-Object` uses the **Property** parameter to sort the objects by **Id** . The **Descending** parameter sorts the command history from newest to oldest.</span></span>

### <span data-ttu-id="3ba1e-142">Exemplo 5: usar uma tabela de hash para classificar Propriedades em ordem crescente e decrescente</span><span class="sxs-lookup"><span data-stu-id="3ba1e-142">Example 5: Use a hash table to sort properties in ascending and descending order</span></span>

<span data-ttu-id="3ba1e-143">Esse comando usa duas propriedades para classificar os objetos, **status** e **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="3ba1e-143">This command uses two properties to sort the objects, **Status** and **DisplayName** .</span></span> <span data-ttu-id="3ba1e-144">O **status** é classificado em ordem decrescente e **DisplayName** é classificado em ordem crescente.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-144">**Status** is sorted in descending order and **DisplayName** is sorted in ascending order.</span></span>

<span data-ttu-id="3ba1e-145">Uma tabela de hash é usada para especificar o valor do parâmetro de **Propriedade** .</span><span class="sxs-lookup"><span data-stu-id="3ba1e-145">A hash table is used to specify the **Property** parameter's value.</span></span> <span data-ttu-id="3ba1e-146">A tabela de hash usa uma expressão para especificar os nomes de propriedade e as ordens de classificação.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-146">The hash table uses an expression to specify the property names and sort orders.</span></span> <span data-ttu-id="3ba1e-147">Para obter informações sobre tabelas de hash, confira [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span><span class="sxs-lookup"><span data-stu-id="3ba1e-147">For more information about hash tables, see [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span></span>

<span data-ttu-id="3ba1e-148">A propriedade de **status** usada na tabela de hash é uma propriedade enumerada.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-148">The **Status** property used in the hash table is an enumerated property.</span></span>
<span data-ttu-id="3ba1e-149">Para obter mais informações, consulte [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span><span class="sxs-lookup"><span data-stu-id="3ba1e-149">For more information, see [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span></span>

```
PS C:\> Get-Service | Sort-Object -Property @{Expression = "Status"; Descending = $True}, @{Expression = "DisplayName"; Descending = $False}

Status   Name               DisplayName
------   ----               -----------
Running  Appinfo            Application Information
Running  BthAvctpSvc        AVCTP service
Running  BrokerInfrastru... Background Tasks Infrastructure Ser...
Running  BDESVC             BitLocker Drive Encryption Service
Running  CoreMessagingRe... CoreMessaging
Running  VaultSvc           Credential Manager
Running  DsSvc              Data Sharing Service
Running  Dhcp               DHCP Client
...
Stopped  ALG                Application Layer Gateway Service
Stopped  AppMgmt            Application Management
Stopped  BITS               Background Intelligent Transfer Ser...
Stopped  wbengine           Block Level Backup Engine Service
Stopped  BluetoothUserSe... Bluetooth User Support Service_14fb...
Stopped  COMSysApp          COM+ System Application
Stopped  smstsmgr           ConfigMgr Task Sequence Agent
Stopped  DeviceInstall      Device Install Service
Stopped  MSDTC              Distributed Transaction Coordinator
```

<span data-ttu-id="3ba1e-150">O `Get-Service` cmdlet obtém a lista de serviços no computador.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-150">The `Get-Service` cmdlet gets the list of services on the computer.</span></span> <span data-ttu-id="3ba1e-151">Os objetos de serviço são enviados pelo pipeline para o `Sort-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-151">The service objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="3ba1e-152">`Sort-Object` usa o parâmetro **Property** com uma tabela de hash para especificar os nomes de propriedade e as ordens de classificação.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-152">`Sort-Object` uses the **Property** parameter with a hash table to specify the property names and sort orders.</span></span> <span data-ttu-id="3ba1e-153">O parâmetro **Property** é classificado por duas propriedades, **status** em ordem decrescente e **DisplayName** em ordem crescente.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-153">The **Property** parameter is sorted by two properties, **Status** in descending order and **DisplayName** in ascending order.</span></span>

<span data-ttu-id="3ba1e-154">O **status** é uma propriedade enumerada.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-154">**Status** is an enumerated property.</span></span> <span data-ttu-id="3ba1e-155">**Stopped** tem um valor de **1** e **em execução** tem um valor de **4** .</span><span class="sxs-lookup"><span data-stu-id="3ba1e-155">**Stopped** has a value of **1** and **Running** has a value of **4** .</span></span> <span data-ttu-id="3ba1e-156">O parâmetro **decrescente** é definido como para `$True` que os processos **em execução** sejam exibidos antes dos processos **interrompidos** .</span><span class="sxs-lookup"><span data-stu-id="3ba1e-156">The **Descending** parameter is set to `$True` so that **Running** processes are displayed before **Stopped** processes.</span></span> <span data-ttu-id="3ba1e-157">**DisplayName** define o parâmetro **decrescente** como `$False` para classificar os nomes de exibição em ordem alfabética.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-157">**DisplayName** sets the **Descending** parameter to `$False` to sort the display names in alphabetical order.</span></span>

### <span data-ttu-id="3ba1e-158">Exemplo 6: classificar arquivos de texto por período de tempo</span><span class="sxs-lookup"><span data-stu-id="3ba1e-158">Example 6: Sort text files by time span</span></span>

<span data-ttu-id="3ba1e-159">Esse comando classifica os arquivos de texto em ordem decrescente pelo período de tempo entre **CreationTime** e **LastWriteTime** .</span><span class="sxs-lookup"><span data-stu-id="3ba1e-159">This command sorts text files in descending order by the time span between **CreationTime** and **LastWriteTime** .</span></span>

```
PS> Get-ChildItem -Path C:\Test\*.txt | Sort-Object -Property @{Expression = {$_.CreationTime - $_.LastWriteTime}; Descending = $False} | Format-Table CreationTime, LastWriteTime, FullName

CreationTime          LastWriteTime        FullName
------------          -------------        --------
11/21/2018 12:39:01   2/26/2019 08:59:36   C:\Test\test2.txt
12/4/2018 08:29:41    2/26/2019 08:57:05   C:\Test\powershell_list.txt
2/20/2019 08:15:59    2/26/2019 12:09:43   C:\Test\CreateTestFile.txt
2/20/2019 08:15:59    2/26/2019 12:07:41   C:\Test\Command.txt
2/20/2019 08:15:59    2/26/2019 08:57:52   C:\Test\ReadOnlyFile.txt
11/29/2018 15:16:50   12/4/2018 16:16:24   C:\Test\LogData.txt
2/25/2019 18:25:11    2/26/2019 12:08:47   C:\Test\Zsystemlog.txt
2/25/2019 18:25:11    2/26/2019 08:55:33   C:\Test\Bfile.txt
2/26/2019 08:46:59    2/26/2019 12:12:19   C:\Test\LogFile3.txt

```

<span data-ttu-id="3ba1e-160">O `Get-ChildItem` cmdlet usa o parâmetro **Path** para especificar o diretório **C:\test** e todos os `*.txt` arquivos.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-160">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory **C:\Test** and all of the `*.txt` files.</span></span> <span data-ttu-id="3ba1e-161">Os objetos são enviados para o pipeline para o `Sort-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-161">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span>
<span data-ttu-id="3ba1e-162">`Sort-Object` usa o parâmetro **Property** com uma tabela de hash para determinar cada intervalo de tempo dos arquivos entre **CreationTime** e **LastWriteTime** .</span><span class="sxs-lookup"><span data-stu-id="3ba1e-162">`Sort-Object` uses the **Property** parameter with a hash table to determine each files time span between **CreationTime** and **LastWriteTime** .</span></span> <span data-ttu-id="3ba1e-163">O parâmetro **decrescente** é definido como `$False` para classificar na ordem de mais longo do que o intervalo de tempo mais curto.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-163">The **Descending** parameter is set to `$False` to sort in the order of longest to shortest time span.</span></span>

### <span data-ttu-id="3ba1e-164">Exemplo 7: classificar nomes em um arquivo de texto</span><span class="sxs-lookup"><span data-stu-id="3ba1e-164">Example 7: Sort names in a text file</span></span>

<span data-ttu-id="3ba1e-165">Este exemplo mostra como classificar uma lista de um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-165">This example shows how to sort a list from a text file.</span></span> <span data-ttu-id="3ba1e-166">O arquivo original é exibido como uma lista não classificada.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-166">The original file is displayed as an unsorted list.</span></span> <span data-ttu-id="3ba1e-167">`Sort-Object` classifica o conteúdo e, em seguida, classifica o conteúdo com o parâmetro **exclusivo** que remove duplicatas.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-167">`Sort-Object` sorts the contents and then sorts the contents with the **Unique** parameter that removes duplicates.</span></span>

```
PS> Get-Content -Path C:\Test\ServerNames.txt
localhost
server01
server25
LOCALHOST
Server19
server3
localhost

PS> Get-Content -Path C:\Test\ServerNames.txt | Sort-Object
localhost
LOCALHOST
localhost
server01
Server19
server25
server3

PS> Get-Content -Path C:\Test\ServerNames.txt | Sort-Object -Unique
localhost
server01
Server19
server25
server3
```

<span data-ttu-id="3ba1e-168">O `Get-Content` cmdlet usa o parâmetro **Path** para especificar o diretório e o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-168">The `Get-Content` cmdlet uses the **Path** parameter to specify the directory and file name.</span></span> <span data-ttu-id="3ba1e-169">O arquivo **ServerNames.txt** contém uma lista não classificada de nomes de computador.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-169">The file **ServerNames.txt** contains an unsorted list of computer names.</span></span>

<span data-ttu-id="3ba1e-170">O `Get-Content` cmdlet usa o parâmetro **Path** para especificar o diretório e o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-170">The `Get-Content` cmdlet uses the **Path** parameter to specify the directory and file name.</span></span> <span data-ttu-id="3ba1e-171">O arquivo **ServerNames.txt** contém uma lista não classificada de nomes de computador.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-171">The file **ServerNames.txt** contains an unsorted list of computer names.</span></span> <span data-ttu-id="3ba1e-172">Os objetos são enviados para o pipeline para o `Sort-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-172">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="3ba1e-173">`Sort-Object` classifica a lista na ordem padrão, crescente.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-173">`Sort-Object` sorts the list in the default order, ascending.</span></span>

<span data-ttu-id="3ba1e-174">O `Get-Content` cmdlet usa o parâmetro **Path** para especificar o diretório e o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-174">The `Get-Content` cmdlet uses the **Path** parameter to specify the directory and file name.</span></span> <span data-ttu-id="3ba1e-175">O arquivo **ServerNames.txt** contém uma lista não classificada de nomes de computador.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-175">The file **ServerNames.txt** contains an unsorted list of computer names.</span></span> <span data-ttu-id="3ba1e-176">Os objetos são enviados para o pipeline para o `Sort-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-176">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="3ba1e-177">`Sort-Object` usa o parâmetro **exclusivo** para remover nomes de computadores duplicados.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-177">`Sort-Object` uses the **Unique** parameter to remove duplicate computer names.</span></span> <span data-ttu-id="3ba1e-178">A lista é classificada na ordem padrão, crescente.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-178">The list is sorted in the default order, ascending.</span></span>

### <span data-ttu-id="3ba1e-179">Exemplo 8: classificar uma cadeia de caracteres como um número inteiro</span><span class="sxs-lookup"><span data-stu-id="3ba1e-179">Example 8: Sort a string as an integer</span></span>

<span data-ttu-id="3ba1e-180">Este exemplo mostra como classificar um arquivo de texto que contém objetos de cadeia de caracteres como inteiros.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-180">This example shows how to sort a text file that contains string objects as integers.</span></span> <span data-ttu-id="3ba1e-181">Você pode enviar cada comando para baixo do pipeline para `Get-Member` e verificar se os objetos são cadeias de caracteres em vez de inteiros.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-181">You can send each command down the pipeline to `Get-Member` and verify that the objects are strings instead of integers.</span></span> <span data-ttu-id="3ba1e-182">Para esses exemplos, o `ProductId.txt` arquivo contém uma lista não classificada de números de produtos.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-182">For these examples, the `ProductId.txt` file contains an unsorted list of product numbers.</span></span>

<span data-ttu-id="3ba1e-183">No primeiro exemplo, `Get-Content` Obtém o conteúdo do arquivo e as linhas de pipes para o `Sort-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-183">In the first example, `Get-Content` gets the contents of the file and pipes lines to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="3ba1e-184">`Sort-Object` classifica os objetos de cadeia de caracteres em ordem crescente.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-184">`Sort-Object` sorts the string objects in ascending order.</span></span>

```
PS> Get-Content -Path C:\Test\ProductId.txt | Sort-Object
0
1
12345
1500
2
2800
3500
4100
500
6200
77
88
99999

PS> Get-Content -Path C:\Test\ProductId.txt | Sort-Object {[int]$_}
0
1
2
77
88
500
1500
2800
3500
4100
6200
12345
99999
```

<span data-ttu-id="3ba1e-185">No segundo exemplo, `Get-Content` Obtém o conteúdo do arquivo e as linhas de pipes para o `Sort-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-185">In the second example, `Get-Content` gets the contents of the file and pipes lines to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="3ba1e-186">`Sort-Object` usa um bloco de script para converter as cadeias de caracteres em números inteiros.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-186">`Sort-Object` uses a script block to convert the strings to integers.</span></span> <span data-ttu-id="3ba1e-187">No código de exemplo, `[int]` converte a cadeia de caracteres em um número inteiro e `$_` representa cada cadeia de caracteres à medida que ela é exibida no pipeline.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-187">In the sample code, `[int]` converts the string to an integer and `$_` represents each string as it comes down the pipeline.</span></span> <span data-ttu-id="3ba1e-188">Os objetos Integer são enviados ao pipeline para o `Sort-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-188">The integer objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span>
<span data-ttu-id="3ba1e-189">`Sort-Object` classifica os objetos de inteiro em ordem numérica.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-189">`Sort-Object` sorts the integer objects in numeric order.</span></span>

<span data-ttu-id="3ba1e-190">O `Get-Content` cmdlet usa o parâmetro **Path** para especificar o diretório e o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-190">The `Get-Content` cmdlet uses the **Path** parameter to specify the directory and file name.</span></span> <span data-ttu-id="3ba1e-191">O arquivo **ProductId.txt** contém uma lista não classificada de números de produtos.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-191">The file **ProductId.txt** contains an unsorted list of product numbers.</span></span> <span data-ttu-id="3ba1e-192">Os objetos de cadeia de caracteres são enviados para o pipeline para o `ForEach-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-192">The string objects are sent down the pipeline to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="3ba1e-193">`ForEach-Object` usa um bloco de script para converter as cadeias de caracteres em números inteiros.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-193">`ForEach-Object` uses a script block to convert the strings to integers.</span></span> <span data-ttu-id="3ba1e-194">No código de exemplo, `[int]` converte a cadeia de caracteres em um número inteiro e `$_` representa cada cadeia de caracteres à medida que ela é exibida no pipeline.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-194">In the sample code, `[int]` converts the string to an integer and `$_` represents each string as it comes down the pipeline.</span></span> <span data-ttu-id="3ba1e-195">Os objetos Integer são enviados ao pipeline para o `Sort-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-195">The integer objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="3ba1e-196">`Sort-Object` classifica os objetos de inteiro em ordem numérica.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-196">`Sort-Object` sorts the integer objects in numeric order.</span></span>
## <span data-ttu-id="3ba1e-197">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3ba1e-197">PARAMETERS</span></span>

### <span data-ttu-id="3ba1e-198">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="3ba1e-198">-CaseSensitive</span></span>

<span data-ttu-id="3ba1e-199">Indica que a classificação diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-199">Indicates that the sort is case-sensitive.</span></span> <span data-ttu-id="3ba1e-200">Por padrão, as classificações não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-200">By default, sorts are not case-sensitive.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Case-insensitive
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3ba1e-201">-Culture</span><span class="sxs-lookup"><span data-stu-id="3ba1e-201">-Culture</span></span>

<span data-ttu-id="3ba1e-202">Especifica a configuração cultural a ser usada para classificações.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-202">Specifies the cultural configuration to use for sorts.</span></span> <span data-ttu-id="3ba1e-203">Use `Get-Culture` para exibir a configuração de cultura do sistema.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-203">Use `Get-Culture` to display the system's culture configuration.</span></span>

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

### <span data-ttu-id="3ba1e-204">-Decrescente</span><span class="sxs-lookup"><span data-stu-id="3ba1e-204">-Descending</span></span>

<span data-ttu-id="3ba1e-205">Indica que `Sort-Object` o classifica os objetos em ordem decrescente.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-205">Indicates that `Sort-Object` sorts the objects in descending order.</span></span> <span data-ttu-id="3ba1e-206">O padrão é a ordem crescente.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-206">The default is ascending order.</span></span>

<span data-ttu-id="3ba1e-207">Para classificar várias propriedades com diferentes ordens de classificação, use uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-207">To sort multiple properties with different sort orders, use a hash table.</span></span> <span data-ttu-id="3ba1e-208">Por exemplo, com uma tabela de hash, você pode classificar uma propriedade em ordem crescente e outra propriedade em ordem decrescente.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-208">For example, with a hash table you can sort one property in ascending order and another property in descending order.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Ascending
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3ba1e-209">-InputObject</span><span class="sxs-lookup"><span data-stu-id="3ba1e-209">-InputObject</span></span>

<span data-ttu-id="3ba1e-210">Para classificar objetos, envie-os para o pipeline para `Sort-Object` .</span><span class="sxs-lookup"><span data-stu-id="3ba1e-210">To sort objects, send them down the pipeline to `Sort-Object`.</span></span> <span data-ttu-id="3ba1e-211">Se você usar o parâmetro **InputObject** para enviar uma coleção de itens, o `Sort-Object` receberá um objeto que representa a coleção.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-211">If you use the **InputObject** parameter to submit a collection of items, `Sort-Object` receives one object that represents the collection.</span></span> <span data-ttu-id="3ba1e-212">Como um objeto não pode ser classificado, `Sort-Object` o retorna a coleção inteira inalterada.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-212">Because one object cannot be sorted, `Sort-Object` returns the entire collection unchanged.</span></span>

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

### <span data-ttu-id="3ba1e-213">-Propriedade</span><span class="sxs-lookup"><span data-stu-id="3ba1e-213">-Property</span></span>

<span data-ttu-id="3ba1e-214">Especifica os nomes de propriedade que `Sort-Object` o usa para classificar os objetos.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-214">Specifies the property names that `Sort-Object` uses to sort the objects.</span></span> <span data-ttu-id="3ba1e-215">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-215">Wildcards are permitted.</span></span>
<span data-ttu-id="3ba1e-216">Os objetos são classificados com base nos valores de propriedade.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-216">Objects are sorted based on the property values.</span></span> <span data-ttu-id="3ba1e-217">Se você não especificar uma propriedade, `Sort-Object` o classificará com base nas propriedades padrão do tipo de objeto ou dos próprios objetos.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-217">If you do not specify a property, `Sort-Object` sorts based on default properties for the object type or the objects themselves.</span></span>

<span data-ttu-id="3ba1e-218">Várias propriedades podem ser classificadas em ordem crescente, ordem decrescente ou uma combinação de ordens de classificação.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-218">Multiple properties can be sorted in ascending order, descending order, or a combination of sort orders.</span></span> <span data-ttu-id="3ba1e-219">Quando você especifica várias propriedades, os objetos são classificados pela primeira propriedade.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-219">When you specify multiple properties, the objects are sorted by the first property.</span></span> <span data-ttu-id="3ba1e-220">Se vários objetos tiverem o mesmo valor para a primeira propriedade, esses objetos serão classificados pela segunda propriedade.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-220">If multiple objects have the same value for the first property, those objects are sorted by the second property.</span></span> <span data-ttu-id="3ba1e-221">Esse processo continua até que não hajam mais propriedades especificadas ou grupos de objetos.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-221">This process continues until there are no more specified properties or no groups of objects.</span></span>

<span data-ttu-id="3ba1e-222">O valor do parâmetro de **Propriedade** pode ser uma propriedade calculada.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-222">The **Property** parameter's value can be a calculated property.</span></span> <span data-ttu-id="3ba1e-223">Para criar uma propriedade calculada, use uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-223">To create a calculated property, use a hash table.</span></span>

<span data-ttu-id="3ba1e-224">As chaves válidas para uma tabela de hash são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="3ba1e-224">Valid keys for a hash table are as follows:</span></span>

- <span data-ttu-id="3ba1e-225">`expression` - `<string>` ou `<script block>`</span><span class="sxs-lookup"><span data-stu-id="3ba1e-225">`expression` - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="3ba1e-226">`ascending` or `descending` - `<boolean>`</span><span class="sxs-lookup"><span data-stu-id="3ba1e-226">`ascending` or `descending` - `<boolean>`</span></span>

<span data-ttu-id="3ba1e-227">Para obter mais informações, consulte [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="3ba1e-227">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: Default properties
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="3ba1e-228">-Exclusivo</span><span class="sxs-lookup"><span data-stu-id="3ba1e-228">-Unique</span></span>

<span data-ttu-id="3ba1e-229">Indica que o `Sort-Object` elimina duplicatas e retorna somente os membros exclusivos da coleção.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-229">Indicates that `Sort-Object` eliminates duplicates and returns only the unique members of the collection.</span></span> <span data-ttu-id="3ba1e-230">A primeira instância de um valor exclusivo é incluída na saída classificada.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-230">The first instance of a unique value is included in the sorted output.</span></span>

<span data-ttu-id="3ba1e-231">**Exclusivo** não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-231">**Unique** is case-insensitive.</span></span> <span data-ttu-id="3ba1e-232">Cadeias de caracteres que diferem apenas por maiúsculas e minúsculas são consideradas iguais.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-232">Strings that only differ by character case are considered the same.</span></span>
<span data-ttu-id="3ba1e-233">Por exemplo, caractere e caractere.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-233">For example, character and CHARACTER.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: All
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3ba1e-234">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3ba1e-234">CommonParameters</span></span>

<span data-ttu-id="3ba1e-235">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-235">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3ba1e-236">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3ba1e-236">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3ba1e-237">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="3ba1e-237">INPUTS</span></span>

### <span data-ttu-id="3ba1e-238">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="3ba1e-238">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="3ba1e-239">Você pode canalizar os objetos a serem classificados `Sort-Object` .</span><span class="sxs-lookup"><span data-stu-id="3ba1e-239">You can pipe the objects to be sorted to `Sort-Object`.</span></span>

## <span data-ttu-id="3ba1e-240">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="3ba1e-240">OUTPUTS</span></span>

### <span data-ttu-id="3ba1e-241">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="3ba1e-241">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="3ba1e-242">`Sort-Object` Retorna os objetos classificados.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-242">`Sort-Object` returns the sorted objects.</span></span>

## <span data-ttu-id="3ba1e-243">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="3ba1e-243">NOTES</span></span>

<span data-ttu-id="3ba1e-244">O `Sort-Object` cmdlet classifica objetos com base nas propriedades especificadas no comando ou nas propriedades de classificação padrão para o tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-244">The `Sort-Object` cmdlet sorts objects based on properties specified in the command or the default sort properties for the object type.</span></span> <span data-ttu-id="3ba1e-245">As propriedades de classificação padrão são definidas usando o `PropertySet` nome `DefaultKeyPropertySet` em um `types.ps1xml` arquivo.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-245">Default sort properties are defined using the `PropertySet` named `DefaultKeyPropertySet` in a `types.ps1xml` file.</span></span> <span data-ttu-id="3ba1e-246">Para obter mais informações, consulte [about_Types.ps1XML](/powershell/module/Microsoft.PowerShell.Core/About/about_Types.ps1xml).</span><span class="sxs-lookup"><span data-stu-id="3ba1e-246">For more information, see [about_Types.ps1xml](/powershell/module/Microsoft.PowerShell.Core/About/about_Types.ps1xml).</span></span>

<span data-ttu-id="3ba1e-247">Se um objeto não tiver uma das propriedades especificadas, o valor da propriedade desse objeto será interpretado `Sort-Object` como **nulo** e colocado no final da ordem de classificação.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-247">If an object does not have one of the specified properties, the property value for that object is interpreted by `Sort-Object` as **Null** and placed at the end of the sort order.</span></span>

<span data-ttu-id="3ba1e-248">Quando nenhuma propriedade de classificação estiver disponível, o PowerShell tentará comparar os próprios objetos.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-248">When no sort properties are available, PowerShell attempts to compare the objects themselves.</span></span>
<span data-ttu-id="3ba1e-249">`Sort-Object` usa o método **Compare** para cada propriedade.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-249">`Sort-Object` uses the **Compare** method for each property.</span></span> <span data-ttu-id="3ba1e-250">Se uma propriedade não implementar **IComparable** , o cmdlet converterá o valor da propriedade em uma cadeia de caracteres e usará o método **Compare** para **System. String** .</span><span class="sxs-lookup"><span data-stu-id="3ba1e-250">If a property does not implement **IComparable** , the cmdlet converts the property value to a string and uses the **Compare** method for **System.String** .</span></span> <span data-ttu-id="3ba1e-251">Para obter mais informações, consulte o [método PSObject. CompareTo (Object)](/dotnet/api/system.management.automation.psobject.compareto).</span><span class="sxs-lookup"><span data-stu-id="3ba1e-251">For more information, see [PSObject.CompareTo(Object) Method](/dotnet/api/system.management.automation.psobject.compareto).</span></span>

<span data-ttu-id="3ba1e-252">Se você classificar em uma propriedade enumerada, como **status** , `Sort-Object` classifica os valores de enumeração.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-252">If you sort on an enumerated property such as **Status** , `Sort-Object` sorts by the enumeration values.</span></span> <span data-ttu-id="3ba1e-253">Para serviços do Windows, **parado** tem um valor de **1** e **em execução** tem um valor de **4** .</span><span class="sxs-lookup"><span data-stu-id="3ba1e-253">For Windows services, **Stopped** has a value of **1** and **Running** has a value of **4** .</span></span>
<span data-ttu-id="3ba1e-254">**Parado** é classificado antes da **execução** devido aos valores enumerados.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-254">**Stopped** is sorted before **Running** because of the enumerated values.</span></span> <span data-ttu-id="3ba1e-255">Para obter mais informações, consulte [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span><span class="sxs-lookup"><span data-stu-id="3ba1e-255">For more information, see [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span></span>

## <span data-ttu-id="3ba1e-256">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="3ba1e-256">RELATED LINKS</span></span>

[<span data-ttu-id="3ba1e-257">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="3ba1e-257">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="3ba1e-258">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="3ba1e-258">about_Hash_Tables</span></span>](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[<span data-ttu-id="3ba1e-259">about_Types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="3ba1e-259">about_Types.ps1xml</span></span>](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)

[<span data-ttu-id="3ba1e-260">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="3ba1e-260">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="3ba1e-261">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="3ba1e-261">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="3ba1e-262">Group-Object</span><span class="sxs-lookup"><span data-stu-id="3ba1e-262">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="3ba1e-263">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="3ba1e-263">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="3ba1e-264">New-Object</span><span class="sxs-lookup"><span data-stu-id="3ba1e-264">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="3ba1e-265">Select-Object</span><span class="sxs-lookup"><span data-stu-id="3ba1e-265">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="3ba1e-266">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="3ba1e-266">Tee-Object</span></span>](Tee-Object.md)
