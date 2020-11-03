---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-table?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Table
ms.openlocfilehash: 4880e4adc9b4ebc339eb44a114e8e6d8bea398a6
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2020
ms.locfileid: "93195140"
---
# <span data-ttu-id="89a0f-103">Format-Table</span><span class="sxs-lookup"><span data-stu-id="89a0f-103">Format-Table</span></span>

## <span data-ttu-id="89a0f-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="89a0f-104">SYNOPSIS</span></span>
<span data-ttu-id="89a0f-105">Formata a saída como uma tabela.</span><span class="sxs-lookup"><span data-stu-id="89a0f-105">Formats the output as a table.</span></span>

## <span data-ttu-id="89a0f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="89a0f-106">SYNTAX</span></span>

### <span data-ttu-id="89a0f-107">Tudo</span><span class="sxs-lookup"><span data-stu-id="89a0f-107">All</span></span>

```
Format-Table [-AutoSize] [-RepeatHeader] [-HideTableHeaders] [-Wrap] [[-Property] <Object[]>]
 [-GroupBy <Object>] [-View <String>] [-ShowError] [-DisplayError] [-Force] [-Expand <String>]
 [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="89a0f-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="89a0f-108">DESCRIPTION</span></span>

<span data-ttu-id="89a0f-109">O `Format-Table` cmdlet formata a saída de um comando como uma tabela com as propriedades selecionadas do objeto em cada coluna.</span><span class="sxs-lookup"><span data-stu-id="89a0f-109">The `Format-Table` cmdlet formats the output of a command as a table with the selected properties of the object in each column.</span></span> <span data-ttu-id="89a0f-110">O tipo de objeto determina o layout padrão e as propriedades que são exibidas em cada coluna.</span><span class="sxs-lookup"><span data-stu-id="89a0f-110">The object type determines the default layout and properties that are displayed in each column.</span></span> <span data-ttu-id="89a0f-111">Você pode usar o parâmetro **Property** para selecionar as propriedades que deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="89a0f-111">You can use the **Property** parameter to select the properties that you want to display.</span></span>

<span data-ttu-id="89a0f-112">O PowerShell usa os formatadores padrão para definir como os tipos de objeto são exibidos.</span><span class="sxs-lookup"><span data-stu-id="89a0f-112">PowerShell uses default formatters to define how object types are displayed.</span></span> <span data-ttu-id="89a0f-113">Você pode usar `.ps1xml` arquivos para criar modos de exibição personalizados que exibem uma tabela de saída com propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="89a0f-113">You can use `.ps1xml` files to create custom views that display an output table with specified properties.</span></span> <span data-ttu-id="89a0f-114">Depois que um modo de exibição personalizado for criado, use o parâmetro **View** para exibir a tabela com o modo de exibição personalizado.</span><span class="sxs-lookup"><span data-stu-id="89a0f-114">After a custom view is created, use the **View** parameter to display the table with your custom view.</span></span> <span data-ttu-id="89a0f-115">Para obter mais informações sobre exibições, consulte [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="89a0f-115">For more information about views, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span></span>

<span data-ttu-id="89a0f-116">Você pode usar uma tabela de hash para adicionar propriedades calculadas a um objeto antes de exibi-lo e especificar os títulos de coluna na tabela.</span><span class="sxs-lookup"><span data-stu-id="89a0f-116">You can use a hash table to add calculated properties to an object before displaying it and to specify the column headings in the table.</span></span> <span data-ttu-id="89a0f-117">Para adicionar uma propriedade calculada, use o parâmetro **Property** ou **GroupBy** .</span><span class="sxs-lookup"><span data-stu-id="89a0f-117">To add a calculated property, use the **Property** or **GroupBy** parameter.</span></span> <span data-ttu-id="89a0f-118">Para obter informações sobre tabelas de hash, confira [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span><span class="sxs-lookup"><span data-stu-id="89a0f-118">For more information about hash tables, see [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span></span>

## <span data-ttu-id="89a0f-119">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="89a0f-119">EXAMPLES</span></span>

### <span data-ttu-id="89a0f-120">Exemplo 1: Formatar host do PowerShell</span><span class="sxs-lookup"><span data-stu-id="89a0f-120">Example 1: Format PowerShell host</span></span>

<span data-ttu-id="89a0f-121">Este exemplo exibe informações sobre o programa host para o PowerShell em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="89a0f-121">This example displays information about the host program for PowerShell in a table.</span></span>

```powershell
Get-Host | Format-Table -AutoSize
```

<span data-ttu-id="89a0f-122">O `Get-Host` cmdlet obtém objetos **System. Management. Automation. Internal. host. InternalHost** que representam o host.</span><span class="sxs-lookup"><span data-stu-id="89a0f-122">The `Get-Host` cmdlet gets **System.Management.Automation.Internal.Host.InternalHost** objects that represent the host.</span></span> <span data-ttu-id="89a0f-123">Os objetos são enviados do pipeline para o `Format-Table` e exibidos em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="89a0f-123">The objects are sent down the pipeline to `Format-Table` and displayed in a table.</span></span> <span data-ttu-id="89a0f-124">O parâmetro **AutoSize** ajusta as larguras das colunas para minimizar o truncamento.</span><span class="sxs-lookup"><span data-stu-id="89a0f-124">The **AutoSize** parameter adjusts the column widths to minimize truncation.</span></span>

### <span data-ttu-id="89a0f-125">Exemplo 2: Formatar processos por BasePriority</span><span class="sxs-lookup"><span data-stu-id="89a0f-125">Example 2: Format processes by BasePriority</span></span>

<span data-ttu-id="89a0f-126">Neste exemplo, os processos são exibidos em grupos que têm a mesma propriedade **BasePriority** .</span><span class="sxs-lookup"><span data-stu-id="89a0f-126">In this example, processes are displayed in groups that have the same **BasePriority** property.</span></span>

```powershell
Get-Process | Sort-Object -Property BasePriority | Format-Table -GroupBy BasePriority -Wrap
```

<span data-ttu-id="89a0f-127">O `Get-Process` cmdlet obtém objetos que representam cada processo no computador e os envia para o pipeline `Sort-Object` .</span><span class="sxs-lookup"><span data-stu-id="89a0f-127">The `Get-Process` cmdlet gets objects that represent each process on the computer and sends them down the pipeline to `Sort-Object`.</span></span> <span data-ttu-id="89a0f-128">Os objetos são classificados na ordem de sua propriedade **BasePriority** .</span><span class="sxs-lookup"><span data-stu-id="89a0f-128">The objects are sorted in the order of their **BasePriority** property.</span></span>

<span data-ttu-id="89a0f-129">Os objetos classificados são enviados do pipeline para o `Format-Table` .</span><span class="sxs-lookup"><span data-stu-id="89a0f-129">The sorted objects are sent down the pipeline to `Format-Table`.</span></span> <span data-ttu-id="89a0f-130">O parâmetro **GroupBy** organiza os dados de processo em grupos com base no valor da propriedade **BasePriority** .</span><span class="sxs-lookup"><span data-stu-id="89a0f-130">The **GroupBy** parameter arranges the process data into groups based on their **BasePriority** property's value.</span></span> <span data-ttu-id="89a0f-131">O parâmetro **Wrap** garante que os dados não sejam truncados.</span><span class="sxs-lookup"><span data-stu-id="89a0f-131">The **Wrap** parameter ensures that data isn't truncated.</span></span>

### <span data-ttu-id="89a0f-132">Exemplo 3: Formatar processos por data de início</span><span class="sxs-lookup"><span data-stu-id="89a0f-132">Example 3: Format processes by start date</span></span>

<span data-ttu-id="89a0f-133">Este exemplo exibe informações sobre os processos em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="89a0f-133">This example displays information about the processes running on the computer.</span></span> <span data-ttu-id="89a0f-134">Os objetos são classificados e `Format-Table` usam uma exibição para agrupar os objetos pela data de início.</span><span class="sxs-lookup"><span data-stu-id="89a0f-134">The objects are sorted and `Format-Table` uses a view to group the objects by their start date.</span></span>

```powershell
Get-Process | Sort-Object StartTime | Format-Table -View StartTime
```

<span data-ttu-id="89a0f-135">`Get-Process` Obtém os objetos **System. Diagnostics. Process** que representam os processos em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="89a0f-135">`Get-Process` gets the **System.Diagnostics.Process** objects that represent the processes running on the computer.</span></span> <span data-ttu-id="89a0f-136">Os objetos são enviados ao pipeline para `Sort-Object` e são classificados com base na propriedade **StartTime** .</span><span class="sxs-lookup"><span data-stu-id="89a0f-136">The objects are sent down the pipeline to `Sort-Object`, and are sorted based on the **StartTime** property.</span></span>

<span data-ttu-id="89a0f-137">Os objetos classificados são enviados do pipeline para o `Format-Table` .</span><span class="sxs-lookup"><span data-stu-id="89a0f-137">The sorted objects are sent down the pipeline to `Format-Table`.</span></span> <span data-ttu-id="89a0f-138">O parâmetro **View** especifica a exibição **StartTime** que é definida no arquivo do PowerShell `DotNetTypes.format.ps1xml` para **objetos System. Diagnostics. Process** .</span><span class="sxs-lookup"><span data-stu-id="89a0f-138">The **View** parameter specifies the **StartTime** view that's defined in the PowerShell `DotNetTypes.format.ps1xml` file for **System.Diagnostics.Process** objects.</span></span> <span data-ttu-id="89a0f-139">A exibição **StartTime** converte cada hora de início dos processos em uma data abreviada e, em seguida, agrupa os processos pela data de início.</span><span class="sxs-lookup"><span data-stu-id="89a0f-139">The **StartTime** view converts each processes start time to a short date and then groups the processes by the start date.</span></span>

<span data-ttu-id="89a0f-140">O `DotNetTypes.format.ps1xml` arquivo contém uma exibição de **prioridade** para processos.</span><span class="sxs-lookup"><span data-stu-id="89a0f-140">The `DotNetTypes.format.ps1xml` file contains a **Priority** view for processes.</span></span> <span data-ttu-id="89a0f-141">Você pode criar seus próprios `format.ps1xml` arquivos com exibições personalizadas.</span><span class="sxs-lookup"><span data-stu-id="89a0f-141">You can create your own `format.ps1xml` files with customized views.</span></span>

### <span data-ttu-id="89a0f-142">Exemplo 4: usar uma exibição personalizada para a saída da tabela</span><span class="sxs-lookup"><span data-stu-id="89a0f-142">Example 4: Use a custom view for table output</span></span>

<span data-ttu-id="89a0f-143">Neste exemplo, uma exibição personalizada exibe o conteúdo de um diretório.</span><span class="sxs-lookup"><span data-stu-id="89a0f-143">In this example, a custom view displays a directory's contents.</span></span> <span data-ttu-id="89a0f-144">A exibição personalizada adiciona a coluna **CreationTime** à saída da tabela para objetos **System. IO. DirectoryInfo** e **System. IO. FileInfo** criados pelo `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="89a0f-144">The custom view adds the **CreationTime** column to the table output for **System.IO.DirectoryInfo** and **System.IO.FileInfo** objects created by `Get-ChildItem`.</span></span>

<span data-ttu-id="89a0f-145">O modo de exibição personalizado neste exemplo foi criado a partir do modo de exibição definido no código-fonte do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89a0f-145">The custom view in this example was created from the view defined in PowerShell source code.</span></span> <span data-ttu-id="89a0f-146">Para obter mais informações sobre exibições e o código usado para criar essa exibição de exemplo, consulte [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md#sample-xml-for-a-format-table-custom-view).</span><span class="sxs-lookup"><span data-stu-id="89a0f-146">For more information about views and the code used to create this example's view, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md#sample-xml-for-a-format-table-custom-view).</span></span>

```powershell
Get-ChildItem  -Path C:\Test | Format-Table -View mygciview
```

```Output
    Directory: C:\Test

Mode                LastWriteTime              CreationTime         Length Name
----                -------------              ------------         ------ ----
d-----        11/4/2019     15:54       9/24/2019     15:54                Archives
d-----        8/27/2019     14:22       8/27/2019     14:22                Drawings
d-----       10/23/2019     09:38       2/25/2019     09:38                Files
-a----        11/7/2019     11:07       11/7/2019     11:07          11345 Alias.txt
-a----        2/27/2019     15:15       2/27/2019     15:15            258 alias_out.txt
-a----        2/27/2019     15:16       2/27/2019     15:16            258 alias_out2.txt
```

<span data-ttu-id="89a0f-147">`Get-ChildItem` Obtém o conteúdo do diretório atual, `C:\Test` .</span><span class="sxs-lookup"><span data-stu-id="89a0f-147">`Get-ChildItem` gets the contents of the current directory, `C:\Test`.</span></span> <span data-ttu-id="89a0f-148">Os objetos **System. IO. DirectoryInfo** e **System. IO. FileInfo** são enviados pelo pipeline.</span><span class="sxs-lookup"><span data-stu-id="89a0f-148">The **System.IO.DirectoryInfo** and **System.IO.FileInfo** objects are sent down the pipeline.</span></span>
<span data-ttu-id="89a0f-149">`Format-Table` usa o parâmetro **View** para especificar a exibição personalizada **mygciview** que inclui a coluna **CreationTime** .</span><span class="sxs-lookup"><span data-stu-id="89a0f-149">`Format-Table` uses the **View** parameter to specify the custom view **mygciview** that includes the **CreationTime** column.</span></span>

<span data-ttu-id="89a0f-150">A `Format-Table` saída padrão para `Get-ChildItem` não inclui a coluna **CreationTime** .</span><span class="sxs-lookup"><span data-stu-id="89a0f-150">The default `Format-Table` output for `Get-ChildItem` doesn't include the **CreationTime** column.</span></span>

### <span data-ttu-id="89a0f-151">Exemplo 5: usar propriedades para saída de tabela</span><span class="sxs-lookup"><span data-stu-id="89a0f-151">Example 5: Use properties for table output</span></span>

<span data-ttu-id="89a0f-152">Este exemplo usa o parâmetro **Property** para exibir todos os serviços do computador em uma tabela de duas colunas que mostra o **nome** das propriedades e **DependentServices** .</span><span class="sxs-lookup"><span data-stu-id="89a0f-152">This example uses the **Property** parameter to display all the computer's services in a two-column table that shows the properties **Name** and **DependentServices** .</span></span>

```powershell
Get-Service | Format-Table -Property Name, DependentServices
```

<span data-ttu-id="89a0f-153">`Get-Service` Obtém todos os serviços no computador e envia os objetos **System. ServiceProcess. ServiceController** para baixo do pipeline.</span><span class="sxs-lookup"><span data-stu-id="89a0f-153">`Get-Service` gets all the services on the computer and sends the **System.ServiceProcess.ServiceController** objects down the pipeline.</span></span> <span data-ttu-id="89a0f-154">`Format-Table` usa o parâmetro **Property** para especificar que as propriedades **Name** e **dependservices** são exibidas na tabela.</span><span class="sxs-lookup"><span data-stu-id="89a0f-154">`Format-Table` uses the **Property** parameter to specify that the **Name** and **DependentServices** properties are displayed in the table.</span></span>

<span data-ttu-id="89a0f-155">**Name** e **DependentServices** são duas das propriedades do tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="89a0f-155">**Name** and **DependentServices** are two of the object type's properties.</span></span> <span data-ttu-id="89a0f-156">Para exibir todas as propriedades: `Get-Service | Get-Member -MemberType Properties` .</span><span class="sxs-lookup"><span data-stu-id="89a0f-156">To view all the properties: `Get-Service | Get-Member -MemberType Properties`.</span></span>

### <span data-ttu-id="89a0f-157">Exemplo 6: Formatar um processo e calcular seu tempo de execução</span><span class="sxs-lookup"><span data-stu-id="89a0f-157">Example 6: Format a process and calculate its running time</span></span>

<span data-ttu-id="89a0f-158">Este exemplo exibe uma tabela com o nome do processo e o tempo total de execução para os processos do **bloco de notas** do computador local.</span><span class="sxs-lookup"><span data-stu-id="89a0f-158">This example displays a table with the process name and total running time for the local computer's **notepad** processes.</span></span> <span data-ttu-id="89a0f-159">O tempo de execução total é calculado subtraindo-se a hora de início de cada processo da hora atual.</span><span class="sxs-lookup"><span data-stu-id="89a0f-159">The total running time is calculated by subtracting the start time of each process from the current time.</span></span>

```powershell
Get-Process notepad |
  Format-Table ProcessName, @{Label="TotalRunningTime"; Expression={(Get-Date) - $_.StartTime}}
```

```Output
ProcessName TotalRunningTime
----------- ----------------
notepad     03:20:00.2751767
notepad     00:00:16.7710520
```

<span data-ttu-id="89a0f-160">`Get-Process` Obtém todos os processos do **bloco de notas** do computador local e envia os objetos por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="89a0f-160">`Get-Process` gets all the local computer's **notepad** processes and sends the objects down the pipeline.</span></span> <span data-ttu-id="89a0f-161">`Format-Table` exibe uma tabela com duas colunas: **ProcessName** , uma `Get-Process` propriedade e **TotalRunningTime** , uma propriedade calculada.</span><span class="sxs-lookup"><span data-stu-id="89a0f-161">`Format-Table` displays a table with two columns: **ProcessName** , a `Get-Process` property, and **TotalRunningTime** , a calculated property.</span></span>

<span data-ttu-id="89a0f-162">A propriedade **TotalRunningTime** é especificada por uma tabela de hash com duas chaves, **rótulo** e **expressão** .</span><span class="sxs-lookup"><span data-stu-id="89a0f-162">The **TotalRunningTime** property is specified by a hash table with two keys, **Label** and **Expression** .</span></span> <span data-ttu-id="89a0f-163">A chave de **rótulo** especifica o nome da propriedade.</span><span class="sxs-lookup"><span data-stu-id="89a0f-163">The **Label** key specifies the property name.</span></span> <span data-ttu-id="89a0f-164">A chave de **expressão** especifica o cálculo.</span><span class="sxs-lookup"><span data-stu-id="89a0f-164">The **Expression** key specifies the calculation.</span></span> <span data-ttu-id="89a0f-165">A expressão Obtém a propriedade **StartTime** de cada objeto de processo e a subtrai do resultado de um `Get-Date` comando, que obtém a data e a hora atuais.</span><span class="sxs-lookup"><span data-stu-id="89a0f-165">The expression gets the **StartTime** property of each process object and subtracts it from the result of a `Get-Date` command, which gets the current date and time.</span></span>

### <span data-ttu-id="89a0f-166">Exemplo 7: Formatar processos do bloco de notas</span><span class="sxs-lookup"><span data-stu-id="89a0f-166">Example 7: Format Notepad processes</span></span>

<span data-ttu-id="89a0f-167">Este exemplo usa `Get-CimInstance` para obter o tempo de execução para todos os processos do **bloco de notas** no computador local.</span><span class="sxs-lookup"><span data-stu-id="89a0f-167">This example uses `Get-CimInstance` to get the running time for all **notepad** processes on the local computer.</span></span> <span data-ttu-id="89a0f-168">Você pode usar `Get-CimInstance` com o parâmetro **ComputerName** para obter informações de computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="89a0f-168">You can use `Get-CimInstance` with the **ComputerName** parameter to get information from remote computers.</span></span>

```powershell
$Processes = Get-CimInstance -Class win32_process -Filter "name='notepad.exe'"
$Processes | Format-Table ProcessName, @{ Label = "Total Running Time"; Expression={(Get-Date) - $_.CreationDate}}
```

```Output
ProcessName Total Running Time
----------- ------------------
notepad.exe 03:39:39.6260693
notepad.exe 00:19:56.1376922
```

<span data-ttu-id="89a0f-169">`Get-CimInstance` Obtém as instâncias da classe WMI **Win32_Process** que descreve todos os processos do computador local chamados **notepad.exe** .</span><span class="sxs-lookup"><span data-stu-id="89a0f-169">`Get-CimInstance` gets instances of the WMI **Win32_Process** class that describes all the local computer's processes named **notepad.exe** .</span></span> <span data-ttu-id="89a0f-170">Os objetos de processo são armazenados na `$Processes` variável.</span><span class="sxs-lookup"><span data-stu-id="89a0f-170">The process objects are stored in the `$Processes` variable.</span></span>

<span data-ttu-id="89a0f-171">Os objetos de processo na `$Processes` variável são enviados ao pipeline para `Format-Table` , que exibe a propriedade **ProcessName** e uma nova propriedade calculada, **tempo total de execução** .</span><span class="sxs-lookup"><span data-stu-id="89a0f-171">The process objects in the `$Processes` variable are sent down the pipeline to `Format-Table`, which displays the **ProcessName** property and a new calculated property, **Total Running Time** .</span></span>

<span data-ttu-id="89a0f-172">O comando atribui o nome da nova propriedade calculada, **tempo total de execução** , à chave do **rótulo** .</span><span class="sxs-lookup"><span data-stu-id="89a0f-172">The command assigns the name of the new calculated property, **Total Running Time** , to the **Label** key.</span></span> <span data-ttu-id="89a0f-173">O bloco de script da chave de **expressão** calcula quanto tempo o processo está em execução subtraindo a data de criação dos processos a partir da data atual.</span><span class="sxs-lookup"><span data-stu-id="89a0f-173">The **Expression** key's script block calculates how long the process has been running by subtracting the processes creation date from the current date.</span></span> <span data-ttu-id="89a0f-174">O `Get-Date` cmdlet obtém a data atual.</span><span class="sxs-lookup"><span data-stu-id="89a0f-174">The `Get-Date` cmdlet gets the current date.</span></span> <span data-ttu-id="89a0f-175">A data de criação é subtraída da data atual.</span><span class="sxs-lookup"><span data-stu-id="89a0f-175">The creation date is subtracted from the current date.</span></span> <span data-ttu-id="89a0f-176">O resultado é o valor do **tempo total de execução** .</span><span class="sxs-lookup"><span data-stu-id="89a0f-176">The result is the value of **Total Running Time** .</span></span>

### <span data-ttu-id="89a0f-177">Exemplo 8: erros de formato de solução de problemas</span><span class="sxs-lookup"><span data-stu-id="89a0f-177">Example 8: Troubleshooting format errors</span></span>

<span data-ttu-id="89a0f-178">Os exemplos a seguir mostram os resultados da adição dos parâmetros **DisplayError** ou **exerror** com uma expressão.</span><span class="sxs-lookup"><span data-stu-id="89a0f-178">The following examples show the results of adding the **DisplayError** or **ShowError** parameters with an expression.</span></span>

```powershell
Get-Date | Format-Table DayOfWeek,{ $_ / $null } -DisplayError
```

```Output
DayOfWeek  $_ / $null
--------- ------------
Wednesday #ERR
```

```powershell
Get-Date | Format-Table DayOfWeek,{ $_ / $null } -ShowError
```

```Output
DayOfWeek  $_ / $null
--------- ------------
Wednesday
Failed to evaluate expression " $_ / $null ".
    + CategoryInfo          : InvalidArgument: (11/27/2019 12:53:41:PSObject) [], RuntimeException
    + FullyQualifiedErrorId : mshExpressionError
```

## <span data-ttu-id="89a0f-179">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="89a0f-179">PARAMETERS</span></span>

### <span data-ttu-id="89a0f-180">-AutoSize</span><span class="sxs-lookup"><span data-stu-id="89a0f-180">-AutoSize</span></span>

<span data-ttu-id="89a0f-181">Indica que o cmdlet ajusta o tamanho da coluna e o número de colunas com base na largura dos dados.</span><span class="sxs-lookup"><span data-stu-id="89a0f-181">Indicates that the cmdlet adjusts the column size and number of columns based on the width of the data.</span></span> <span data-ttu-id="89a0f-182">Por padrão, o número de colunas e seu tamanho são determinados pelo modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="89a0f-182">By default, the column size and number are determined by the view.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="89a0f-183">-DisplayError</span><span class="sxs-lookup"><span data-stu-id="89a0f-183">-DisplayError</span></span>

<span data-ttu-id="89a0f-184">Indica que o cmdlet exibe erros na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="89a0f-184">Indicates that the cmdlet displays errors on the command line.</span></span> <span data-ttu-id="89a0f-185">Esse parâmetro pode ser usado como um auxílio de depuração quando você estiver Formatando expressões em um `Format-Table` comando e precisar solucionar problemas das expressões.</span><span class="sxs-lookup"><span data-stu-id="89a0f-185">This parameter can be used as a debugging aid when you're formatting expressions in a `Format-Table` command and need to troubleshoot the expressions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="89a0f-186">-Expandir</span><span class="sxs-lookup"><span data-stu-id="89a0f-186">-Expand</span></span>

<span data-ttu-id="89a0f-187">Especifica o formato do objeto de coleção e os objetos na coleção.</span><span class="sxs-lookup"><span data-stu-id="89a0f-187">Specifies the format of the collection object and the objects in the collection.</span></span> <span data-ttu-id="89a0f-188">Esse parâmetro é projetado para formatar objetos que dão suporte à interface [ICollection](/dotnet/api/system.collections.icollection) ([System. Collections](/dotnet/api/system.collections)).</span><span class="sxs-lookup"><span data-stu-id="89a0f-188">This parameter is designed to format objects that support the [ICollection](/dotnet/api/system.collections.icollection) ([System.Collections](/dotnet/api/system.collections)) interface.</span></span> <span data-ttu-id="89a0f-189">O valor padrão é **EnumOnly** .</span><span class="sxs-lookup"><span data-stu-id="89a0f-189">The default value is **EnumOnly** .</span></span>
<span data-ttu-id="89a0f-190">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="89a0f-190">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="89a0f-191">**EnumOnly** : exibe as propriedades dos objetos na coleção.</span><span class="sxs-lookup"><span data-stu-id="89a0f-191">**EnumOnly** : Displays the properties of the objects in the collection.</span></span>
- <span data-ttu-id="89a0f-192">**CoreOnly** : exibe as propriedades do objeto de coleção.</span><span class="sxs-lookup"><span data-stu-id="89a0f-192">**CoreOnly** : Displays the properties of the collection object.</span></span>
- <span data-ttu-id="89a0f-193">**Ambos** : exibe as propriedades do objeto de coleção e as propriedades de objetos na coleção.</span><span class="sxs-lookup"><span data-stu-id="89a0f-193">**Both** : Displays the properties of the collection object and the properties of objects in the collection.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CoreOnly, EnumOnly, Both

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="89a0f-194">-Force</span><span class="sxs-lookup"><span data-stu-id="89a0f-194">-Force</span></span>

<span data-ttu-id="89a0f-195">Indica que o cmdlet direciona o cmdlet para exibir todas as informações de erro.</span><span class="sxs-lookup"><span data-stu-id="89a0f-195">Indicates that the cmdlet directs the cmdlet to display all the error information.</span></span> <span data-ttu-id="89a0f-196">Use com o parâmetro **DisplayError** ou **exerror** .</span><span class="sxs-lookup"><span data-stu-id="89a0f-196">Use with the **DisplayError** or **ShowError** parameter.</span></span> <span data-ttu-id="89a0f-197">Por padrão, quando um objeto de erro é gravado para os fluxos de erro ou de exibição, apenas algumas das informações de erro são exibidas.</span><span class="sxs-lookup"><span data-stu-id="89a0f-197">By default, when an error object is written to the error or display streams, only some of the error information is displayed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="89a0f-198">-GroupBy</span><span class="sxs-lookup"><span data-stu-id="89a0f-198">-GroupBy</span></span>

<span data-ttu-id="89a0f-199">Especifica a saída classificada em tabelas separadas com base em um valor de propriedade.</span><span class="sxs-lookup"><span data-stu-id="89a0f-199">Specifies sorted output in separate tables based on a property value.</span></span> <span data-ttu-id="89a0f-200">Por exemplo, você pode usar **GroupBy** para listar os serviços em tabelas separadas com base em seu status.</span><span class="sxs-lookup"><span data-stu-id="89a0f-200">For example, you can use **GroupBy** to list services in separate tables based on their status.</span></span>

<span data-ttu-id="89a0f-201">Insira uma expressão ou uma propriedade.</span><span class="sxs-lookup"><span data-stu-id="89a0f-201">Enter an expression or a property.</span></span> <span data-ttu-id="89a0f-202">O parâmetro **GroupBy** espera que os objetos sejam classificados.</span><span class="sxs-lookup"><span data-stu-id="89a0f-202">The **GroupBy** parameter expects that the objects are sorted.</span></span>
<span data-ttu-id="89a0f-203">Use o `Sort-Object` cmdlet antes de usar o `Format-Table` para agrupar os objetos.</span><span class="sxs-lookup"><span data-stu-id="89a0f-203">Use the `Sort-Object` cmdlet before using `Format-Table` to group the objects.</span></span>

<span data-ttu-id="89a0f-204">O valor do parâmetro **GroupBy** pode ser uma nova propriedade calculada.</span><span class="sxs-lookup"><span data-stu-id="89a0f-204">The value of the **GroupBy** parameter can be a new calculated property.</span></span> <span data-ttu-id="89a0f-205">A propriedade calculada pode ser um bloco de script ou uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="89a0f-205">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="89a0f-206">Os pares de chave-valor válidos são:</span><span class="sxs-lookup"><span data-stu-id="89a0f-206">Valid key-value pairs are:</span></span>

- <span data-ttu-id="89a0f-207">Nome (ou rótulo)- `<string>`</span><span class="sxs-lookup"><span data-stu-id="89a0f-207">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="89a0f-208">Expressão- `<string>` ou `<script block>`</span><span class="sxs-lookup"><span data-stu-id="89a0f-208">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="89a0f-209">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="89a0f-209">FormatString - `<string>`</span></span>

<span data-ttu-id="89a0f-210">Para obter mais informações, consulte [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="89a0f-210">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="89a0f-211">-HideTableHeaders</span><span class="sxs-lookup"><span data-stu-id="89a0f-211">-HideTableHeaders</span></span>

<span data-ttu-id="89a0f-212">Omite os cabeçalhos de coluna da tabela.</span><span class="sxs-lookup"><span data-stu-id="89a0f-212">Omits the column headings from the table.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="89a0f-213">-InputObject</span><span class="sxs-lookup"><span data-stu-id="89a0f-213">-InputObject</span></span>

<span data-ttu-id="89a0f-214">Especifica os objetos a serem formatados.</span><span class="sxs-lookup"><span data-stu-id="89a0f-214">Specifies the objects to format.</span></span> <span data-ttu-id="89a0f-215">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="89a0f-215">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="89a0f-216">-Propriedade</span><span class="sxs-lookup"><span data-stu-id="89a0f-216">-Property</span></span>

<span data-ttu-id="89a0f-217">Especifica as propriedades do objeto que aparecem na exibição e a ordem em que aparecem.</span><span class="sxs-lookup"><span data-stu-id="89a0f-217">Specifies the object properties that appear in the display and the order in which they appear.</span></span> <span data-ttu-id="89a0f-218">Digite um ou mais nomes de propriedade, separados por vírgulas, ou use uma tabela de hash para exibir uma propriedade calculada.</span><span class="sxs-lookup"><span data-stu-id="89a0f-218">Type one or more property names, separated by commas, or use a hash table to display a calculated property.</span></span> <span data-ttu-id="89a0f-219">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="89a0f-219">Wildcards are permitted.</span></span>

<span data-ttu-id="89a0f-220">Se você omitir esse parâmetro, as propriedades exibidas na exibição dependerão das propriedades do primeiro objeto.</span><span class="sxs-lookup"><span data-stu-id="89a0f-220">If you omit this parameter, the properties that appear in the display depend on the first object's properties.</span></span> <span data-ttu-id="89a0f-221">Por exemplo, se o primeiro objeto tiver **propertya** e **PropertyB** , mas os objetos subsequentes tiverem **propertya** , **PropertyB** e **PropertyC** , somente os cabeçalhos **propertya** e **PropertyB** serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="89a0f-221">For example, if the first object has **PropertyA** and **PropertyB** but subsequent objects have **PropertyA** , **PropertyB** , and **PropertyC** , then only the **PropertyA** and **PropertyB** headers will display.</span></span>

<span data-ttu-id="89a0f-222">O parâmetro **Property** é opcional.</span><span class="sxs-lookup"><span data-stu-id="89a0f-222">The **Property** parameter is optional.</span></span> <span data-ttu-id="89a0f-223">Você não pode usar os parâmetros **Property** e **View** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="89a0f-223">You can't use the **Property** and **View** parameters in the same command.</span></span>

<span data-ttu-id="89a0f-224">O valor do parâmetro **Property** pode ser uma nova propriedade calculada.</span><span class="sxs-lookup"><span data-stu-id="89a0f-224">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="89a0f-225">A propriedade calculada pode ser um bloco de script ou uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="89a0f-225">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="89a0f-226">Os pares de chave-valor válidos são:</span><span class="sxs-lookup"><span data-stu-id="89a0f-226">Valid key-value pairs are:</span></span>

- <span data-ttu-id="89a0f-227">Nome (ou rótulo) `<string>`</span><span class="sxs-lookup"><span data-stu-id="89a0f-227">Name (or Label) `<string>`</span></span>
- <span data-ttu-id="89a0f-228">Expressão- `<string>` ou `<script block>`</span><span class="sxs-lookup"><span data-stu-id="89a0f-228">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="89a0f-229">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="89a0f-229">FormatString - `<string>`</span></span>
- <span data-ttu-id="89a0f-230">Largura- `<int32>` -deve ser maior que `0`</span><span class="sxs-lookup"><span data-stu-id="89a0f-230">Width - `<int32>` - must be greater than `0`</span></span>
- <span data-ttu-id="89a0f-231">Alinhamento-o valor pode ser `Left` , `Center` ou `Right`</span><span class="sxs-lookup"><span data-stu-id="89a0f-231">Alignment - value can be `Left`, `Center`, or `Right`</span></span>

<span data-ttu-id="89a0f-232">Para obter mais informações, consulte [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="89a0f-232">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="89a0f-233">-RepeatHeader</span><span class="sxs-lookup"><span data-stu-id="89a0f-233">-RepeatHeader</span></span>

<span data-ttu-id="89a0f-234">Repete a exibição do cabeçalho de uma tabela depois de cada tela cheia.</span><span class="sxs-lookup"><span data-stu-id="89a0f-234">Repeats displaying the header of a table after every screen full.</span></span> <span data-ttu-id="89a0f-235">O cabeçalho repetido é útil quando a saída é canalizada para um pager, como `less` ou `more` ou paginação com um leitor de tela.</span><span class="sxs-lookup"><span data-stu-id="89a0f-235">The repeated header is useful when the output is piped to a pager such as `less` or `more` or paging with a screen reader.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="89a0f-236">-Erro</span><span class="sxs-lookup"><span data-stu-id="89a0f-236">-ShowError</span></span>

<span data-ttu-id="89a0f-237">Esse parâmetro envia erros por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="89a0f-237">This parameter sends errors through the pipeline.</span></span> <span data-ttu-id="89a0f-238">Esse parâmetro pode ser usado como um auxílio de depuração quando você estiver Formatando expressões em um `Format-Table` comando e precisar solucionar problemas das expressões.</span><span class="sxs-lookup"><span data-stu-id="89a0f-238">This parameter can be used as a debugging aid when you're formatting expressions in a `Format-Table` command and need to troubleshoot the expressions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="89a0f-239">-Exibição</span><span class="sxs-lookup"><span data-stu-id="89a0f-239">-View</span></span>

<span data-ttu-id="89a0f-240">No PowerShell 5,1 e versões anteriores, as exibições padrão são definidas em `*.format.ps1xml` arquivos armazenados em `$PSHOME` .</span><span class="sxs-lookup"><span data-stu-id="89a0f-240">In PowerShell 5.1 and earlier versions, the default views are defined in `*.format.ps1xml` files stored in `$PSHOME`.</span></span>

<span data-ttu-id="89a0f-241">O parâmetro **View** permite especificar um formato alternativo ou uma exibição personalizada para a tabela.</span><span class="sxs-lookup"><span data-stu-id="89a0f-241">The **View** parameter lets you specify an alternate format or custom view for the table.</span></span> <span data-ttu-id="89a0f-242">Você pode usar os modos de exibição padrão do PowerShell ou criar modos de exibição personalizados.</span><span class="sxs-lookup"><span data-stu-id="89a0f-242">You can use the default PowerShell views or create custom views.</span></span> <span data-ttu-id="89a0f-243">Para obter mais informações sobre como criar uma exibição personalizada, consulte [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="89a0f-243">For more information about how to create a custom view, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span></span>

<span data-ttu-id="89a0f-244">As exibições alternativas e personalizadas para o parâmetro de **exibição** devem usar o formato de tabela, caso contrário, `Format-Table` falhará.</span><span class="sxs-lookup"><span data-stu-id="89a0f-244">The alternate and custom views for the **View** parameter must use the table format, otherwise, `Format-Table` fails.</span></span> <span data-ttu-id="89a0f-245">Se a exibição alternativa for uma lista, use o `Format-List` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="89a0f-245">If the alternate view is a list, use the `Format-List` cmdlet.</span></span> <span data-ttu-id="89a0f-246">Se a exibição alternativa não for uma lista ou uma tabela, use o `Format-Custom` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="89a0f-246">If the alternate view isn't a list or a table, use the `Format-Custom` cmdlet.</span></span>

<span data-ttu-id="89a0f-247">Você não pode usar os parâmetros **Property** e **View** no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="89a0f-247">You can't use the **Property** and **View** parameters in the same command.</span></span>

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

### <span data-ttu-id="89a0f-248">-Encapsulamento</span><span class="sxs-lookup"><span data-stu-id="89a0f-248">-Wrap</span></span>

<span data-ttu-id="89a0f-249">Exibe na linha seguinte o texto que excede a largura da coluna.</span><span class="sxs-lookup"><span data-stu-id="89a0f-249">Displays text that exceeds the column width on the next line.</span></span> <span data-ttu-id="89a0f-250">Por padrão, o texto que excede a largura da coluna é truncado.</span><span class="sxs-lookup"><span data-stu-id="89a0f-250">By default, text that exceeds the column width is truncated.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="89a0f-251">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="89a0f-251">CommonParameters</span></span>

<span data-ttu-id="89a0f-252">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="89a0f-252">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="89a0f-253">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="89a0f-253">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="89a0f-254">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="89a0f-254">INPUTS</span></span>

### <span data-ttu-id="89a0f-255">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="89a0f-255">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="89a0f-256">Você pode enviar qualquer objeto para baixo do pipeline para `Format-Table` .</span><span class="sxs-lookup"><span data-stu-id="89a0f-256">You can send any object down the pipeline to `Format-Table`.</span></span>

## <span data-ttu-id="89a0f-257">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="89a0f-257">OUTPUTS</span></span>

### <span data-ttu-id="89a0f-258">Microsoft. PowerShell. Commands. Internal. Format</span><span class="sxs-lookup"><span data-stu-id="89a0f-258">Microsoft.PowerShell.Commands.Internal.Format</span></span>

<span data-ttu-id="89a0f-259">`Format-Table` retorna objetos de formato que representam a tabela.</span><span class="sxs-lookup"><span data-stu-id="89a0f-259">`Format-Table` returns format objects that represent the table.</span></span>

## <span data-ttu-id="89a0f-260">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="89a0f-260">NOTES</span></span>

## <span data-ttu-id="89a0f-261">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="89a0f-261">RELATED LINKS</span></span>

[<span data-ttu-id="89a0f-262">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="89a0f-262">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="89a0f-263">about_Format.ps1xml</span><span class="sxs-lookup"><span data-stu-id="89a0f-263">about_Format.ps1xml</span></span>](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md)

[<span data-ttu-id="89a0f-264">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="89a0f-264">about_Hash_Tables</span></span>](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[<span data-ttu-id="89a0f-265">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="89a0f-265">Export-FormatData</span></span>](Export-FormatData.md)

[<span data-ttu-id="89a0f-266">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="89a0f-266">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="89a0f-267">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="89a0f-267">Format-Hex</span></span>](Format-Hex.md)

[<span data-ttu-id="89a0f-268">Format-List</span><span class="sxs-lookup"><span data-stu-id="89a0f-268">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="89a0f-269">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="89a0f-269">Format-Wide</span></span>](Format-Wide.md)

[<span data-ttu-id="89a0f-270">Get-FormatData</span><span class="sxs-lookup"><span data-stu-id="89a0f-270">Get-FormatData</span></span>](Get-FormatData.md)

[<span data-ttu-id="89a0f-271">Get-Member</span><span class="sxs-lookup"><span data-stu-id="89a0f-271">Get-Member</span></span>](Get-Member.md)

[<span data-ttu-id="89a0f-272">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="89a0f-272">Get-CimInstance</span></span>](../CimCmdlets/Get-CimInstance.md)

[<span data-ttu-id="89a0f-273">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="89a0f-273">Update-FormatData</span></span>](Update-FormatData.md)
