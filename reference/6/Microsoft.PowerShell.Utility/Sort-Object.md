---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/20/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/sort-object?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Sort-Object
ms.openlocfilehash: 3eef18677c8f81b560354303c2d685abfc44601c
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2020
ms.locfileid: "93195180"
---
# <span data-ttu-id="583bf-103">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="583bf-103">Sort-Object</span></span>

## <span data-ttu-id="583bf-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="583bf-104">SYNOPSIS</span></span>
<span data-ttu-id="583bf-105">Classifica os objetos por valores de propriedade.</span><span class="sxs-lookup"><span data-stu-id="583bf-105">Sorts objects by property values.</span></span>

## <span data-ttu-id="583bf-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="583bf-106">SYNTAX</span></span>

### <span data-ttu-id="583bf-107">Padrão (padrão)</span><span class="sxs-lookup"><span data-stu-id="583bf-107">Default (Default)</span></span>

```
Sort-Object [-Stable] [-Descending] [-Unique] [-InputObject <PSObject>] [[-Property] <Object[]>]
 [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

### <span data-ttu-id="583bf-108">Superior</span><span class="sxs-lookup"><span data-stu-id="583bf-108">Top</span></span>

```
Sort-Object [-Descending] [-Unique] -Top <Int32> [-InputObject <PSObject>] [[-Property] <Object[]>]
 [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

### <span data-ttu-id="583bf-109">Inferior</span><span class="sxs-lookup"><span data-stu-id="583bf-109">Bottom</span></span>

```
Sort-Object [-Descending] [-Unique] -Bottom <Int32> [-InputObject <PSObject>] [[-Property] <Object[]>]
 [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

## <span data-ttu-id="583bf-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="583bf-110">DESCRIPTION</span></span>

<span data-ttu-id="583bf-111">O `Sort-Object` cmdlet classifica os objetos em ordem crescente ou decrescente com base em valores de propriedade de objeto.</span><span class="sxs-lookup"><span data-stu-id="583bf-111">The `Sort-Object` cmdlet sorts objects in ascending or descending order based on object property values.</span></span> <span data-ttu-id="583bf-112">Se as propriedades de classificação não forem incluídas em um comando, o PowerShell usará as propriedades de classificação padrão do primeiro objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="583bf-112">If sort properties are not included in a command, PowerShell uses default sort properties of the first input object.</span></span> <span data-ttu-id="583bf-113">Se o tipo do objeto de entrada não tiver nenhuma propriedade de classificação padrão, o PowerShell tentará comparar os próprios objetos.</span><span class="sxs-lookup"><span data-stu-id="583bf-113">If the type of the input object has no default sort properties, PowerShell attempts to compare the objects themselves.</span></span> <span data-ttu-id="583bf-114">Para obter mais informações, consulte a seção [observações](#notes) .</span><span class="sxs-lookup"><span data-stu-id="583bf-114">For more information, see the [Notes](#notes) section.</span></span>

<span data-ttu-id="583bf-115">Você pode classificar objetos por uma única propriedade ou várias propriedades.</span><span class="sxs-lookup"><span data-stu-id="583bf-115">You can sort objects by a single property or multiple properties.</span></span> <span data-ttu-id="583bf-116">Várias propriedades usam tabelas de hash para classificar em ordem crescente, ordem decrescente ou uma combinação de ordens de classificação.</span><span class="sxs-lookup"><span data-stu-id="583bf-116">Multiple properties use hash tables to sort in ascending order, descending order, or a combination of sort orders.</span></span> <span data-ttu-id="583bf-117">As propriedades são classificadas como diferencia maiúsculas de minúsculas ou não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="583bf-117">Properties are sorted as case-sensitive or case-insensitive.</span></span> <span data-ttu-id="583bf-118">Use o parâmetro **exclusivo** para eliminar duplicatas da saída.</span><span class="sxs-lookup"><span data-stu-id="583bf-118">Use the **Unique** parameter to eliminate duplicates from the output.</span></span>

## <span data-ttu-id="583bf-119">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="583bf-119">EXAMPLES</span></span>

### <span data-ttu-id="583bf-120">Exemplo 1: classificar o diretório atual por nome</span><span class="sxs-lookup"><span data-stu-id="583bf-120">Example 1: Sort the current directory by name</span></span>

<span data-ttu-id="583bf-121">Este exemplo classifica os arquivos e subdiretórios em um diretório.</span><span class="sxs-lookup"><span data-stu-id="583bf-121">This example sorts the files and subdirectories in a directory.</span></span>

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

<span data-ttu-id="583bf-122">O `Get-ChildItem` cmdlet obtém os arquivos e subdiretórios do diretório especificado pelo parâmetro **Path** , **C:\test** .</span><span class="sxs-lookup"><span data-stu-id="583bf-122">The `Get-ChildItem` cmdlet gets the files and subdirectories from the directory specified by the **Path** parameter, **C:\Test** .</span></span> <span data-ttu-id="583bf-123">Os objetos são enviados para o pipeline para o `Sort-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="583bf-123">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span>
<span data-ttu-id="583bf-124">`Sort-Object` não especifica uma propriedade para que a saída seja classificada pela propriedade de classificação padrão, **Name** .</span><span class="sxs-lookup"><span data-stu-id="583bf-124">`Sort-Object` does not specify a property so the output is sorted by the default sort property, **Name** .</span></span>

### <span data-ttu-id="583bf-125">Exemplo 2: classificar o diretório atual por comprimento do arquivo</span><span class="sxs-lookup"><span data-stu-id="583bf-125">Example 2: Sort the current directory by file length</span></span>

<span data-ttu-id="583bf-126">Esse comando exibe os arquivos no diretório atual por comprimento em ordem crescente.</span><span class="sxs-lookup"><span data-stu-id="583bf-126">This command displays the files in the current directory by length in ascending order.</span></span>

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

<span data-ttu-id="583bf-127">O `Get-ChildItem` cmdlet obtém os arquivos do diretório especificado pelo parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="583bf-127">The `Get-ChildItem` cmdlet gets the files from the directory specified by the **Path** parameter.</span></span>
<span data-ttu-id="583bf-128">O parâmetro **File** especifica que `Get-ChildItem` somente Obtém os objetos de arquivo.</span><span class="sxs-lookup"><span data-stu-id="583bf-128">The **File** parameter specifies that `Get-ChildItem` only gets file objects.</span></span> <span data-ttu-id="583bf-129">Os objetos são enviados para o pipeline para o `Sort-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="583bf-129">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="583bf-130">`Sort-Object` usa o parâmetro **Length** para classificar os arquivos por comprimento em ordem crescente.</span><span class="sxs-lookup"><span data-stu-id="583bf-130">`Sort-Object` uses the **Length** parameter to sort the files by length in ascending order.</span></span>

### <span data-ttu-id="583bf-131">Exemplo 3: classificar processos por uso de memória</span><span class="sxs-lookup"><span data-stu-id="583bf-131">Example 3: Sort processes by memory usage</span></span>

<span data-ttu-id="583bf-132">Este exemplo exibe processos com o maior uso de memória com base em seu tamanho de conjunto de trabalho (WS).</span><span class="sxs-lookup"><span data-stu-id="583bf-132">This example displays processes with the highest memory usage based on their working set (WS) size.</span></span>

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

<span data-ttu-id="583bf-133">O `Get-Process` cmdlet obtém a lista de processos em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="583bf-133">The `Get-Process` cmdlet gets the list of processes running on the computer.</span></span> <span data-ttu-id="583bf-134">Os objetos de processo são enviados por meio do pipeline para o `Sort-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="583bf-134">The process objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="583bf-135">`Sort-Object` usa o parâmetro **Property** para classificar os objetos por **WS** .</span><span class="sxs-lookup"><span data-stu-id="583bf-135">`Sort-Object` uses the **Property** parameter to sort the objects by **WS** .</span></span> <span data-ttu-id="583bf-136">Os objetos são enviados para o pipeline para o `Select-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="583bf-136">The objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span>
<span data-ttu-id="583bf-137">`Select-Object` usa o **último** parâmetro para especificar os últimos cinco objetos, que são os objetos com o maior uso do **WS** .</span><span class="sxs-lookup"><span data-stu-id="583bf-137">`Select-Object` uses the **Last** parameter to specify the last five objects, which are the objects with the highest **WS** usage.</span></span>

<span data-ttu-id="583bf-138">No PowerShell 6, a `Sort-Object` **parte inferior** do parâmetro é uma alternativa para `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="583bf-138">In PowerShell 6, the `Sort-Object` parameter **Bottom** is an alternative to `Select-Object`.</span></span> <span data-ttu-id="583bf-139">Por exemplo, `Get-Process | Sort-Object -Property WS -Bottom 5`.</span><span class="sxs-lookup"><span data-stu-id="583bf-139">For example, `Get-Process | Sort-Object -Property WS -Bottom 5`.</span></span>

### <span data-ttu-id="583bf-140">Exemplo 4: classificar objetos HistoryInfo por ID</span><span class="sxs-lookup"><span data-stu-id="583bf-140">Example 4: Sort HistoryInfo objects by Id</span></span>

<span data-ttu-id="583bf-141">Esse comando classifica os objetos **HistoryInfo** da sessão do PowerShell usando a propriedade **ID** .</span><span class="sxs-lookup"><span data-stu-id="583bf-141">This command sorts the PowerShell session's **HistoryInfo** objects using the **Id** property.</span></span> <span data-ttu-id="583bf-142">Cada sessão do PowerShell tem seu próprio histórico de comandos.</span><span class="sxs-lookup"><span data-stu-id="583bf-142">Each PowerShell session has its own command history.</span></span>

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

<span data-ttu-id="583bf-143">O `Get-History` cmdlet obtém os objetos de histórico da sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="583bf-143">The `Get-History` cmdlet gets the history objects from the current PowerShell session.</span></span> <span data-ttu-id="583bf-144">Os objetos são enviados para o pipeline para o `Sort-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="583bf-144">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="583bf-145">`Sort-Object` usa o parâmetro **Property** para classificar os objetos por **ID** . O parâmetro **decrescente** classifica o histórico de comandos do mais recente para o mais antigo.</span><span class="sxs-lookup"><span data-stu-id="583bf-145">`Sort-Object` uses the **Property** parameter to sort the objects by **Id** . The **Descending** parameter sorts the command history from newest to oldest.</span></span>

### <span data-ttu-id="583bf-146">Exemplo 5: usar uma tabela de hash para classificar Propriedades em ordem crescente e decrescente</span><span class="sxs-lookup"><span data-stu-id="583bf-146">Example 5: Use a hash table to sort properties in ascending and descending order</span></span>

<span data-ttu-id="583bf-147">Este exemplo usa duas propriedades para classificar os objetos, **status** e **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="583bf-147">This example uses two properties to sort the objects, **Status** and **DisplayName** .</span></span> <span data-ttu-id="583bf-148">O **status** é classificado em ordem decrescente e **DisplayName** é classificado em ordem crescente.</span><span class="sxs-lookup"><span data-stu-id="583bf-148">**Status** is sorted in descending order and **DisplayName** is sorted in ascending order.</span></span>

<span data-ttu-id="583bf-149">Uma tabela de hash é usada para especificar o valor do parâmetro de **Propriedade** .</span><span class="sxs-lookup"><span data-stu-id="583bf-149">A hash table is used to specify the **Property** parameter's value.</span></span> <span data-ttu-id="583bf-150">A tabela de hash usa uma expressão para especificar os nomes de propriedade e as ordens de classificação.</span><span class="sxs-lookup"><span data-stu-id="583bf-150">The hash table uses an expression to specify the property names and sort orders.</span></span> <span data-ttu-id="583bf-151">Para obter informações sobre tabelas de hash, confira [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span><span class="sxs-lookup"><span data-stu-id="583bf-151">For more information about hash tables, see [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span></span>

<span data-ttu-id="583bf-152">A propriedade de **status** usada na tabela de hash é uma propriedade enumerada.</span><span class="sxs-lookup"><span data-stu-id="583bf-152">The **Status** property used in the hash table is an enumerated property.</span></span>
<span data-ttu-id="583bf-153">Para obter mais informações, consulte [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span><span class="sxs-lookup"><span data-stu-id="583bf-153">For more information, see [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span></span>

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

<span data-ttu-id="583bf-154">O `Get-Service` cmdlet obtém a lista de serviços no computador.</span><span class="sxs-lookup"><span data-stu-id="583bf-154">The `Get-Service` cmdlet gets the list of services on the computer.</span></span> <span data-ttu-id="583bf-155">Os objetos de serviço são enviados pelo pipeline para o `Sort-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="583bf-155">The service objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="583bf-156">`Sort-Object` usa o parâmetro **Property** com uma tabela de hash para especificar os nomes de propriedade e as ordens de classificação.</span><span class="sxs-lookup"><span data-stu-id="583bf-156">`Sort-Object` uses the **Property** parameter with a hash table to specify the property names and sort orders.</span></span> <span data-ttu-id="583bf-157">O parâmetro **Property** é classificado por duas propriedades, **status** em ordem decrescente e **DisplayName** em ordem crescente.</span><span class="sxs-lookup"><span data-stu-id="583bf-157">The **Property** parameter is sorted by two properties, **Status** in descending order and **DisplayName** in ascending order.</span></span>

<span data-ttu-id="583bf-158">O **status** é uma propriedade enumerada.</span><span class="sxs-lookup"><span data-stu-id="583bf-158">**Status** is an enumerated property.</span></span> <span data-ttu-id="583bf-159">**Stopped** tem um valor de **1** e **em execução** tem um valor de **4** .</span><span class="sxs-lookup"><span data-stu-id="583bf-159">**Stopped** has a value of **1** and **Running** has a value of **4** .</span></span> <span data-ttu-id="583bf-160">O parâmetro **decrescente** é definido como para `$True` que os processos **em execução** sejam exibidos antes dos processos **interrompidos** .</span><span class="sxs-lookup"><span data-stu-id="583bf-160">The **Descending** parameter is set to `$True` so that **Running** processes are displayed before **Stopped** processes.</span></span> <span data-ttu-id="583bf-161">**DisplayName** define o parâmetro **decrescente** como `$False` para classificar os nomes de exibição em ordem alfabética.</span><span class="sxs-lookup"><span data-stu-id="583bf-161">**DisplayName** sets the **Descending** parameter to `$False` to sort the display names in alphabetical order.</span></span>

### <span data-ttu-id="583bf-162">Exemplo 6: classificar arquivos de texto por período de tempo</span><span class="sxs-lookup"><span data-stu-id="583bf-162">Example 6: Sort text files by time span</span></span>

<span data-ttu-id="583bf-163">Esse comando classifica os arquivos de texto em ordem decrescente pelo período de tempo entre **CreationTime** e **LastWriteTime** .</span><span class="sxs-lookup"><span data-stu-id="583bf-163">This command sorts text files in descending order by the time span between **CreationTime** and **LastWriteTime** .</span></span>

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

<span data-ttu-id="583bf-164">O `Get-ChildItem` cmdlet usa o parâmetro **Path** para especificar o diretório **C:\test** e todos os `*.txt` arquivos.</span><span class="sxs-lookup"><span data-stu-id="583bf-164">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory **C:\Test** and all of the `*.txt` files.</span></span> <span data-ttu-id="583bf-165">Os objetos são enviados para o pipeline para o `Sort-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="583bf-165">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span>
<span data-ttu-id="583bf-166">`Sort-Object` usa o parâmetro **Property** com uma tabela de hash para determinar cada intervalo de tempo dos arquivos entre **CreationTime** e **LastWriteTime** .</span><span class="sxs-lookup"><span data-stu-id="583bf-166">`Sort-Object` uses the **Property** parameter with a hash table to determine each files time span between **CreationTime** and **LastWriteTime** .</span></span> <span data-ttu-id="583bf-167">O parâmetro **decrescente** é definido como `$False` para classificar na ordem de mais longo do que o intervalo de tempo mais curto.</span><span class="sxs-lookup"><span data-stu-id="583bf-167">The **Descending** parameter is set to `$False` to sort in the order of longest to shortest time span.</span></span>

### <span data-ttu-id="583bf-168">Exemplo 7: classificar nomes em um arquivo de texto</span><span class="sxs-lookup"><span data-stu-id="583bf-168">Example 7: Sort names in a text file</span></span>

<span data-ttu-id="583bf-169">Este exemplo mostra como classificar uma lista de um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="583bf-169">This example shows how to sort a list from a text file.</span></span> <span data-ttu-id="583bf-170">O arquivo original é exibido como uma lista não classificada.</span><span class="sxs-lookup"><span data-stu-id="583bf-170">The original file is displayed as an unsorted list.</span></span> <span data-ttu-id="583bf-171">`Sort-Object` classifica o conteúdo e, em seguida, classifica o conteúdo com o parâmetro **exclusivo** que remove duplicatas.</span><span class="sxs-lookup"><span data-stu-id="583bf-171">`Sort-Object` sorts the contents and then sorts the contents with the **Unique** parameter that removes duplicates.</span></span>

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

<span data-ttu-id="583bf-172">O `Get-Content` cmdlet usa o parâmetro **Path** para especificar o diretório e o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="583bf-172">The `Get-Content` cmdlet uses the **Path** parameter to specify the directory and file name.</span></span> <span data-ttu-id="583bf-173">O arquivo **ServerNames.txt** contém uma lista não classificada de nomes de computador.</span><span class="sxs-lookup"><span data-stu-id="583bf-173">The file **ServerNames.txt** contains an unsorted list of computer names.</span></span>

<span data-ttu-id="583bf-174">O `Get-Content` cmdlet usa o parâmetro **Path** para especificar o diretório e o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="583bf-174">The `Get-Content` cmdlet uses the **Path** parameter to specify the directory and file name.</span></span> <span data-ttu-id="583bf-175">O arquivo **ServerNames.txt** contém uma lista não classificada de nomes de computador.</span><span class="sxs-lookup"><span data-stu-id="583bf-175">The file **ServerNames.txt** contains an unsorted list of computer names.</span></span> <span data-ttu-id="583bf-176">Os objetos são enviados para o pipeline para o `Sort-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="583bf-176">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="583bf-177">`Sort-Object` classifica a lista na ordem padrão, crescente.</span><span class="sxs-lookup"><span data-stu-id="583bf-177">`Sort-Object` sorts the list in the default order, ascending.</span></span>

<span data-ttu-id="583bf-178">O `Get-Content` cmdlet usa o parâmetro **Path** para especificar o diretório e o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="583bf-178">The `Get-Content` cmdlet uses the **Path** parameter to specify the directory and file name.</span></span> <span data-ttu-id="583bf-179">O arquivo **ServerNames.txt** contém uma lista não classificada de nomes de computador.</span><span class="sxs-lookup"><span data-stu-id="583bf-179">The file **ServerNames.txt** contains an unsorted list of computer names.</span></span> <span data-ttu-id="583bf-180">Os objetos são enviados para o pipeline para o `Sort-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="583bf-180">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="583bf-181">`Sort-Object` usa o parâmetro **exclusivo** para remover nomes de computadores duplicados.</span><span class="sxs-lookup"><span data-stu-id="583bf-181">`Sort-Object` uses the **Unique** parameter to remove duplicate computer names.</span></span> <span data-ttu-id="583bf-182">A lista é classificada na ordem padrão, crescente.</span><span class="sxs-lookup"><span data-stu-id="583bf-182">The list is sorted in the default order, ascending.</span></span>

### <span data-ttu-id="583bf-183">Exemplo 8: classificar uma cadeia de caracteres como um número inteiro</span><span class="sxs-lookup"><span data-stu-id="583bf-183">Example 8: Sort a string as an integer</span></span>

<span data-ttu-id="583bf-184">Este exemplo mostra como classificar um arquivo de texto que contém objetos de cadeia de caracteres como inteiros.</span><span class="sxs-lookup"><span data-stu-id="583bf-184">This example shows how to sort a text file that contains string objects as integers.</span></span> <span data-ttu-id="583bf-185">Você pode enviar cada comando para baixo do pipeline para `Get-Member` e verificar se os objetos são cadeias de caracteres em vez de inteiros.</span><span class="sxs-lookup"><span data-stu-id="583bf-185">You can send each command down the pipeline to `Get-Member` and verify that the objects are strings instead of integers.</span></span> <span data-ttu-id="583bf-186">Para esses exemplos, o `ProductId.txt` arquivo contém uma lista não classificada de números de produtos.</span><span class="sxs-lookup"><span data-stu-id="583bf-186">For these examples, the `ProductId.txt` file contains an unsorted list of product numbers.</span></span>

<span data-ttu-id="583bf-187">No primeiro exemplo, `Get-Content` Obtém o conteúdo do arquivo e as linhas de pipes para o `Sort-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="583bf-187">In the first example, `Get-Content` gets the contents of the file and pipes lines to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="583bf-188">`Sort-Object` classifica os objetos de cadeia de caracteres em ordem crescente.</span><span class="sxs-lookup"><span data-stu-id="583bf-188">`Sort-Object` sorts the string objects in ascending order.</span></span>

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

<span data-ttu-id="583bf-189">No segundo exemplo, `Get-Content` Obtém o conteúdo do arquivo e as linhas de pipes para o `Sort-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="583bf-189">In the second example, `Get-Content` gets the contents of the file and pipes lines to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="583bf-190">`Sort-Object` usa um bloco de script para converter as cadeias de caracteres em números inteiros.</span><span class="sxs-lookup"><span data-stu-id="583bf-190">`Sort-Object` uses a script block to convert the strings to integers.</span></span> <span data-ttu-id="583bf-191">No código de exemplo, `[int]` converte a cadeia de caracteres em um número inteiro e `$_` representa cada cadeia de caracteres à medida que ela é exibida no pipeline.</span><span class="sxs-lookup"><span data-stu-id="583bf-191">In the sample code, `[int]` converts the string to an integer and `$_` represents each string as it comes down the pipeline.</span></span> <span data-ttu-id="583bf-192">Os objetos Integer são enviados ao pipeline para o `Sort-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="583bf-192">The integer objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span>
<span data-ttu-id="583bf-193">`Sort-Object` classifica os objetos de inteiro em ordem numérica.</span><span class="sxs-lookup"><span data-stu-id="583bf-193">`Sort-Object` sorts the integer objects in numeric order.</span></span>

### <span data-ttu-id="583bf-194">Exemplo 9: usando classificações estáveis</span><span class="sxs-lookup"><span data-stu-id="583bf-194">Example 9: Using stable sorts</span></span>

<span data-ttu-id="583bf-195">Quando você usa os parâmetros **superior** , **inferior** ou **estável** , os objetos classificados são entregues na ordem em que foram recebidos `Sort-Object` quando os critérios de classificação são iguais.</span><span class="sxs-lookup"><span data-stu-id="583bf-195">When you use the **Top** , **Bottom** , or **Stable** parameters, the sorted objects are delivered in the order they were received by `Sort-Object` when the sort criteria are equal.</span></span> <span data-ttu-id="583bf-196">Neste exemplo, estamos classificando os números um a 20 pelo valor ' módulo 3 '.</span><span class="sxs-lookup"><span data-stu-id="583bf-196">In this example, we are sorting the numbers one through 20 by the their value 'modulo 3'.</span></span> <span data-ttu-id="583bf-197">O valor do módulo varia de zero a dois.</span><span class="sxs-lookup"><span data-stu-id="583bf-197">The modulo value ranges from zero to two.</span></span>

```powershell
PS> 1..20 |Sort-Object {$_ % 3}
18
3
15
6
12
9
1
16
13
10
7
4
19
11
8
14
5
17
2
20

PS> 1..20 |Sort-Object {$_ % 3} -Stable
3
6
9
12
15
18
1
4
7
10
13
16
19
2
5
8
11
14
17
20
```

<span data-ttu-id="583bf-198">A saída da primeira classificação é agrupada corretamente pelo valor de módulo, mas os itens individuais não são classificados dentro do intervalo de módulos.</span><span class="sxs-lookup"><span data-stu-id="583bf-198">The output from the first sort is correctly grouped by the modulus value but the individual items are not sorted within the modulus range.</span></span> <span data-ttu-id="583bf-199">A segunda classificação usa a opção **estável** para retornar uma classificação estável.</span><span class="sxs-lookup"><span data-stu-id="583bf-199">The second sort uses the **Stable** option to return a stable sort.</span></span>

## <span data-ttu-id="583bf-200">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="583bf-200">PARAMETERS</span></span>

### <span data-ttu-id="583bf-201">-Inferior</span><span class="sxs-lookup"><span data-stu-id="583bf-201">-Bottom</span></span>

<span data-ttu-id="583bf-202">Especifica o número de objetos a serem obtidos do final de uma matriz de objetos classificados.</span><span class="sxs-lookup"><span data-stu-id="583bf-202">Specifies the number of objects to get from the end of a sorted object array.</span></span> <span data-ttu-id="583bf-203">Isso resulta em uma classificação estável.</span><span class="sxs-lookup"><span data-stu-id="583bf-203">This results in a stable sort.</span></span>

<span data-ttu-id="583bf-204">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="583bf-204">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Bottom
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="583bf-205">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="583bf-205">-CaseSensitive</span></span>

<span data-ttu-id="583bf-206">Indica que a classificação diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="583bf-206">Indicates that the sort is case-sensitive.</span></span> <span data-ttu-id="583bf-207">Por padrão, as classificações não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="583bf-207">By default, sorts are not case-sensitive.</span></span>

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

### <span data-ttu-id="583bf-208">-Culture</span><span class="sxs-lookup"><span data-stu-id="583bf-208">-Culture</span></span>

<span data-ttu-id="583bf-209">Especifica a configuração cultural a ser usada para classificações.</span><span class="sxs-lookup"><span data-stu-id="583bf-209">Specifies the cultural configuration to use for sorts.</span></span> <span data-ttu-id="583bf-210">Use `Get-Culture` para exibir a configuração de cultura do sistema.</span><span class="sxs-lookup"><span data-stu-id="583bf-210">Use `Get-Culture` to display the system's culture configuration.</span></span>

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

### <span data-ttu-id="583bf-211">-Decrescente</span><span class="sxs-lookup"><span data-stu-id="583bf-211">-Descending</span></span>

<span data-ttu-id="583bf-212">Indica que `Sort-Object` o classifica os objetos em ordem decrescente.</span><span class="sxs-lookup"><span data-stu-id="583bf-212">Indicates that `Sort-Object` sorts the objects in descending order.</span></span> <span data-ttu-id="583bf-213">O padrão é a ordem crescente.</span><span class="sxs-lookup"><span data-stu-id="583bf-213">The default is ascending order.</span></span>

<span data-ttu-id="583bf-214">Para classificar várias propriedades com diferentes ordens de classificação, use uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="583bf-214">To sort multiple properties with different sort orders, use a hash table.</span></span> <span data-ttu-id="583bf-215">Por exemplo, com uma tabela de hash, você pode classificar uma propriedade em ordem crescente e outra propriedade em ordem decrescente.</span><span class="sxs-lookup"><span data-stu-id="583bf-215">For example, with a hash table you can sort one property in ascending order and another property in descending order.</span></span>

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

### <span data-ttu-id="583bf-216">-InputObject</span><span class="sxs-lookup"><span data-stu-id="583bf-216">-InputObject</span></span>

<span data-ttu-id="583bf-217">Para classificar objetos, envie-os para o pipeline para `Sort-Object` .</span><span class="sxs-lookup"><span data-stu-id="583bf-217">To sort objects, send them down the pipeline to `Sort-Object`.</span></span> <span data-ttu-id="583bf-218">Se você usar o parâmetro **InputObject** para enviar uma coleção de itens, o `Sort-Object` receberá um objeto que representa a coleção.</span><span class="sxs-lookup"><span data-stu-id="583bf-218">If you use the **InputObject** parameter to submit a collection of items, `Sort-Object` receives one object that represents the collection.</span></span> <span data-ttu-id="583bf-219">Como um objeto não pode ser classificado, `Sort-Object` o retorna a coleção inteira inalterada.</span><span class="sxs-lookup"><span data-stu-id="583bf-219">Because one object cannot be sorted, `Sort-Object` returns the entire collection unchanged.</span></span>

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

### <span data-ttu-id="583bf-220">-Propriedade</span><span class="sxs-lookup"><span data-stu-id="583bf-220">-Property</span></span>

<span data-ttu-id="583bf-221">Especifica os nomes de propriedade que `Sort-Object` o usa para classificar os objetos.</span><span class="sxs-lookup"><span data-stu-id="583bf-221">Specifies the property names that `Sort-Object` uses to sort the objects.</span></span> <span data-ttu-id="583bf-222">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="583bf-222">Wildcards are permitted.</span></span>
<span data-ttu-id="583bf-223">Os objetos são classificados com base nos valores de propriedade.</span><span class="sxs-lookup"><span data-stu-id="583bf-223">Objects are sorted based on the property values.</span></span> <span data-ttu-id="583bf-224">Se você não especificar uma propriedade, `Sort-Object` o classificará com base nas propriedades padrão do tipo de objeto ou dos próprios objetos.</span><span class="sxs-lookup"><span data-stu-id="583bf-224">If you do not specify a property, `Sort-Object` sorts based on default properties for the object type or the objects themselves.</span></span>

<span data-ttu-id="583bf-225">Várias propriedades podem ser classificadas em ordem crescente, ordem decrescente ou uma combinação de ordens de classificação.</span><span class="sxs-lookup"><span data-stu-id="583bf-225">Multiple properties can be sorted in ascending order, descending order, or a combination of sort orders.</span></span> <span data-ttu-id="583bf-226">Quando você especifica várias propriedades, os objetos são classificados pela primeira propriedade.</span><span class="sxs-lookup"><span data-stu-id="583bf-226">When you specify multiple properties, the objects are sorted by the first property.</span></span> <span data-ttu-id="583bf-227">Se vários objetos tiverem o mesmo valor para a primeira propriedade, esses objetos serão classificados pela segunda propriedade.</span><span class="sxs-lookup"><span data-stu-id="583bf-227">If multiple objects have the same value for the first property, those objects are sorted by the second property.</span></span> <span data-ttu-id="583bf-228">Esse processo continua até que não hajam mais propriedades especificadas ou grupos de objetos.</span><span class="sxs-lookup"><span data-stu-id="583bf-228">This process continues until there are no more specified properties or no groups of objects.</span></span>

<span data-ttu-id="583bf-229">O valor do parâmetro de **Propriedade** pode ser uma propriedade calculada.</span><span class="sxs-lookup"><span data-stu-id="583bf-229">The **Property** parameter's value can be a calculated property.</span></span> <span data-ttu-id="583bf-230">Para criar uma propriedade calculada, use uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="583bf-230">To create a calculated property, use a hash table.</span></span>

<span data-ttu-id="583bf-231">As chaves válidas para uma tabela de hash são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="583bf-231">Valid keys for a hash table are as follows:</span></span>

- <span data-ttu-id="583bf-232">`expression` - `<string>` ou `<script block>`</span><span class="sxs-lookup"><span data-stu-id="583bf-232">`expression` - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="583bf-233">`ascending` or `descending` - `<boolean>`</span><span class="sxs-lookup"><span data-stu-id="583bf-233">`ascending` or `descending` - `<boolean>`</span></span>

<span data-ttu-id="583bf-234">Para obter mais informações, consulte [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="583bf-234">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="583bf-235">-Superior</span><span class="sxs-lookup"><span data-stu-id="583bf-235">-Top</span></span>

<span data-ttu-id="583bf-236">Especifica o número de objetos a serem obtidos do início de uma matriz de objetos classificados.</span><span class="sxs-lookup"><span data-stu-id="583bf-236">Specifies the number of objects to get from the start of a sorted object array.</span></span> <span data-ttu-id="583bf-237">Isso resulta em uma classificação estável.</span><span class="sxs-lookup"><span data-stu-id="583bf-237">This results in a stable sort.</span></span>

<span data-ttu-id="583bf-238">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="583bf-238">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Top
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="583bf-239">-Exclusivo</span><span class="sxs-lookup"><span data-stu-id="583bf-239">-Unique</span></span>

<span data-ttu-id="583bf-240">Indica que o `Sort-Object` elimina duplicatas e retorna somente os membros exclusivos da coleção.</span><span class="sxs-lookup"><span data-stu-id="583bf-240">Indicates that `Sort-Object` eliminates duplicates and returns only the unique members of the collection.</span></span> <span data-ttu-id="583bf-241">A primeira instância de um valor exclusivo é incluída na saída classificada.</span><span class="sxs-lookup"><span data-stu-id="583bf-241">The first instance of a unique value is included in the sorted output.</span></span>

<span data-ttu-id="583bf-242">**Exclusivo** não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="583bf-242">**Unique** is case-insensitive.</span></span> <span data-ttu-id="583bf-243">Cadeias de caracteres que diferem apenas por maiúsculas e minúsculas são consideradas iguais.</span><span class="sxs-lookup"><span data-stu-id="583bf-243">Strings that only differ by character case are considered the same.</span></span>
<span data-ttu-id="583bf-244">Por exemplo, caractere e caractere.</span><span class="sxs-lookup"><span data-stu-id="583bf-244">For example, character and CHARACTER.</span></span>

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

### <span data-ttu-id="583bf-245">-Estável</span><span class="sxs-lookup"><span data-stu-id="583bf-245">-Stable</span></span>

<span data-ttu-id="583bf-246">Os objetos classificados são entregues na ordem em que foram recebidos quando os critérios de classificação são iguais.</span><span class="sxs-lookup"><span data-stu-id="583bf-246">The sorted objects are delivered in the order they were received when the sort criteria are equal.</span></span>

<span data-ttu-id="583bf-247">Esse parâmetro foi adicionado no PowerShell v 6.2.0.</span><span class="sxs-lookup"><span data-stu-id="583bf-247">This parameter was added in PowerShell v6.2.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="583bf-248">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="583bf-248">CommonParameters</span></span>

<span data-ttu-id="583bf-249">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="583bf-249">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="583bf-250">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="583bf-250">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="583bf-251">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="583bf-251">INPUTS</span></span>

### <span data-ttu-id="583bf-252">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="583bf-252">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="583bf-253">Você pode canalizar os objetos a serem classificados `Sort-Object` .</span><span class="sxs-lookup"><span data-stu-id="583bf-253">You can pipe the objects to be sorted to `Sort-Object`.</span></span>

## <span data-ttu-id="583bf-254">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="583bf-254">OUTPUTS</span></span>

### <span data-ttu-id="583bf-255">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="583bf-255">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="583bf-256">`Sort-Object` Retorna os objetos classificados.</span><span class="sxs-lookup"><span data-stu-id="583bf-256">`Sort-Object` returns the sorted objects.</span></span>

## <span data-ttu-id="583bf-257">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="583bf-257">NOTES</span></span>

<span data-ttu-id="583bf-258">O `Sort-Object` cmdlet classifica objetos com base nas propriedades especificadas no comando ou nas propriedades de classificação padrão para o tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="583bf-258">The `Sort-Object` cmdlet sorts objects based on properties specified in the command or the default sort properties for the object type.</span></span> <span data-ttu-id="583bf-259">As propriedades de classificação padrão são definidas usando o `PropertySet` nome `DefaultKeyPropertySet` em um `types.ps1xml` arquivo.</span><span class="sxs-lookup"><span data-stu-id="583bf-259">Default sort properties are defined using the `PropertySet` named `DefaultKeyPropertySet` in a `types.ps1xml` file.</span></span> <span data-ttu-id="583bf-260">Para obter mais informações, consulte [about_Types.ps1XML](/powershell/module/Microsoft.PowerShell.Core/About/about_Types.ps1xml).</span><span class="sxs-lookup"><span data-stu-id="583bf-260">For more information, see [about_Types.ps1xml](/powershell/module/Microsoft.PowerShell.Core/About/about_Types.ps1xml).</span></span>

<span data-ttu-id="583bf-261">Se um objeto não tiver uma das propriedades especificadas, o valor da propriedade desse objeto será interpretado `Sort-Object` como **nulo** e colocado no final da ordem de classificação.</span><span class="sxs-lookup"><span data-stu-id="583bf-261">If an object does not have one of the specified properties, the property value for that object is interpreted by `Sort-Object` as **Null** and placed at the end of the sort order.</span></span>

<span data-ttu-id="583bf-262">Quando nenhuma propriedade de classificação estiver disponível, o PowerShell tentará comparar os próprios objetos.</span><span class="sxs-lookup"><span data-stu-id="583bf-262">When no sort properties are available, PowerShell attempts to compare the objects themselves.</span></span>
<span data-ttu-id="583bf-263">`Sort-Object` usa o método **Compare** para cada propriedade.</span><span class="sxs-lookup"><span data-stu-id="583bf-263">`Sort-Object` uses the **Compare** method for each property.</span></span> <span data-ttu-id="583bf-264">Se uma propriedade não implementar **IComparable** , o cmdlet converterá o valor da propriedade em uma cadeia de caracteres e usará o método **Compare** para **System. String** .</span><span class="sxs-lookup"><span data-stu-id="583bf-264">If a property does not implement **IComparable** , the cmdlet converts the property value to a string and uses the **Compare** method for **System.String** .</span></span> <span data-ttu-id="583bf-265">Para obter mais informações, consulte o [método PSObject. CompareTo (Object)](/dotnet/api/system.management.automation.psobject.compareto).</span><span class="sxs-lookup"><span data-stu-id="583bf-265">For more information, see [PSObject.CompareTo(Object) Method](/dotnet/api/system.management.automation.psobject.compareto).</span></span>

<span data-ttu-id="583bf-266">Se você classificar em uma propriedade enumerada, como **status** , `Sort-Object` classifica os valores de enumeração.</span><span class="sxs-lookup"><span data-stu-id="583bf-266">If you sort on an enumerated property such as **Status** , `Sort-Object` sorts by the enumeration values.</span></span> <span data-ttu-id="583bf-267">Para serviços do Windows, **parado** tem um valor de **1** e **em execução** tem um valor de **4** .</span><span class="sxs-lookup"><span data-stu-id="583bf-267">For Windows services, **Stopped** has a value of **1** and **Running** has a value of **4** .</span></span>
<span data-ttu-id="583bf-268">**Parado** é classificado antes da **execução** devido aos valores enumerados.</span><span class="sxs-lookup"><span data-stu-id="583bf-268">**Stopped** is sorted before **Running** because of the enumerated values.</span></span> <span data-ttu-id="583bf-269">Para obter mais informações, consulte [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span><span class="sxs-lookup"><span data-stu-id="583bf-269">For more information, see [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span></span>

<span data-ttu-id="583bf-270">O desempenho do algoritmo de classificação é mais lento ao fazer uma classificação estável.</span><span class="sxs-lookup"><span data-stu-id="583bf-270">The performance of the sorting algorithm is slower when doing a stable sort.</span></span>

## <span data-ttu-id="583bf-271">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="583bf-271">RELATED LINKS</span></span>

[<span data-ttu-id="583bf-272">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="583bf-272">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="583bf-273">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="583bf-273">about_Hash_Tables</span></span>](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[<span data-ttu-id="583bf-274">about_Types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="583bf-274">about_Types.ps1xml</span></span>](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)

[<span data-ttu-id="583bf-275">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="583bf-275">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="583bf-276">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="583bf-276">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="583bf-277">Group-Object</span><span class="sxs-lookup"><span data-stu-id="583bf-277">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="583bf-278">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="583bf-278">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="583bf-279">New-Object</span><span class="sxs-lookup"><span data-stu-id="583bf-279">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="583bf-280">Select-Object</span><span class="sxs-lookup"><span data-stu-id="583bf-280">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="583bf-281">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="583bf-281">Tee-Object</span></span>](Tee-Object.md)
