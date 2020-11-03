---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-process?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Process
ms.openlocfilehash: 543c2b683ca3631e2e05f57d9c70ff4455071e4b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194717"
---
# <span data-ttu-id="d5f3e-103">Get-Process</span><span class="sxs-lookup"><span data-stu-id="d5f3e-103">Get-Process</span></span>

## <span data-ttu-id="d5f3e-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="d5f3e-104">SYNOPSIS</span></span>
<span data-ttu-id="d5f3e-105">Obtém os processos em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-105">Gets the processes that are running on the local computer.</span></span>

## <span data-ttu-id="d5f3e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d5f3e-106">SYNTAX</span></span>

### <span data-ttu-id="d5f3e-107">Nome (padrão)</span><span class="sxs-lookup"><span data-stu-id="d5f3e-107">Name (Default)</span></span>

```
Get-Process [[-Name] <String[]>] [-Module] [-FileVersionInfo] [<CommonParameters>]
```

### <span data-ttu-id="d5f3e-108">NameWithUserName</span><span class="sxs-lookup"><span data-stu-id="d5f3e-108">NameWithUserName</span></span>

```
Get-Process [[-Name] <String[]>] -IncludeUserName [<CommonParameters>]
```

### <span data-ttu-id="d5f3e-109">ID</span><span class="sxs-lookup"><span data-stu-id="d5f3e-109">Id</span></span>

```
Get-Process -Id <Int32[]> [-Module] [-FileVersionInfo] [<CommonParameters>]
```

### <span data-ttu-id="d5f3e-110">IdWithUserName</span><span class="sxs-lookup"><span data-stu-id="d5f3e-110">IdWithUserName</span></span>

```
Get-Process -Id <Int32[]> -IncludeUserName [<CommonParameters>]
```

### <span data-ttu-id="d5f3e-111">InputObject</span><span class="sxs-lookup"><span data-stu-id="d5f3e-111">InputObject</span></span>

```
Get-Process -InputObject <Process[]> [-Module] [-FileVersionInfo] [<CommonParameters>]
```

### <span data-ttu-id="d5f3e-112">InputObjectWithUserName</span><span class="sxs-lookup"><span data-stu-id="d5f3e-112">InputObjectWithUserName</span></span>

```
Get-Process -InputObject <Process[]> -IncludeUserName [<CommonParameters>]
```

## <span data-ttu-id="d5f3e-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d5f3e-113">DESCRIPTION</span></span>

<span data-ttu-id="d5f3e-114">O `Get-Process` cmdlet obtém os processos em um computador local.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-114">The `Get-Process` cmdlet gets the processes on a local computer.</span></span>

<span data-ttu-id="d5f3e-115">Sem parâmetros, esse cmdlet obtém todos os processos no computador local.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-115">Without parameters, this cmdlet gets all of the processes on the local computer.</span></span>
<span data-ttu-id="d5f3e-116">Você também pode especificar um processo específico por nome do processo ou ID do processo (PID) ou passar um objeto de processo por meio do pipeline para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-116">You can also specify a particular process by process name or process ID (PID) or pass a process object through the pipeline to this cmdlet.</span></span>

<span data-ttu-id="d5f3e-117">Por padrão, esse cmdlet retorna um objeto de processo que tem informações detalhadas sobre o processo e dá suporte a métodos que permitem iniciar e parar o processo.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-117">By default, this cmdlet returns a process object that has detailed information about the process and supports methods that let you start and stop the process.</span></span>
<span data-ttu-id="d5f3e-118">Você também pode usar os parâmetros do `Get-Process` cmdlet para obter informações de versão de arquivo para o programa que é executado no processo e para obter os módulos carregados pelo processo.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-118">You can also use the parameters of the `Get-Process` cmdlet to get file version information for the program that runs in the process and to get the modules that the process loaded.</span></span>

## <span data-ttu-id="d5f3e-119">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="d5f3e-119">EXAMPLES</span></span>

### <span data-ttu-id="d5f3e-120">Exemplo 1: obter uma lista de todos os processos ativos no computador local</span><span class="sxs-lookup"><span data-stu-id="d5f3e-120">Example 1: Get a list of all active processes on the local computer</span></span>

```powershell
Get-Process
```

<span data-ttu-id="d5f3e-121">Esse comando obtém uma lista de todos os processos ativos em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-121">This command gets a list of all active processes running on the local computer.</span></span>
<span data-ttu-id="d5f3e-122">Para obter uma definição de cada coluna, consulte a seção [observações](#notes) .</span><span class="sxs-lookup"><span data-stu-id="d5f3e-122">For a definition of each column, see the [Notes](#notes) section.</span></span>

### <span data-ttu-id="d5f3e-123">Exemplo 2: obter todos os dados disponíveis sobre um ou mais processos</span><span class="sxs-lookup"><span data-stu-id="d5f3e-123">Example 2: Get all available data about one or more processes</span></span>

```powershell
Get-Process winword, explorer | Format-List *
```

<span data-ttu-id="d5f3e-124">Esse comando obtém todos os dados disponíveis sobre os processos Winword e Explorer no computador.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-124">This command gets all available data about the Winword and Explorer processes on the computer.</span></span>
<span data-ttu-id="d5f3e-125">Ele usa o parâmetro **Name** para especificar os processos, mas omite o nome de parâmetro opcional.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-125">It uses the **Name** parameter to specify the processes, but it omits the optional parameter name.</span></span>
<span data-ttu-id="d5f3e-126">O operador de pipeline `|` passa os dados para o `Format-List` cmdlet, que exibe todas as propriedades disponíveis `*` dos objetos de processo do Winword e do Explorer.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-126">The pipeline operator `|` passes the data to the `Format-List` cmdlet, which displays all available properties `*` of the Winword and Explorer process objects.</span></span>

<span data-ttu-id="d5f3e-127">Você também pode identificar os processos pelas suas IDs.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-127">You can also identify the processes by their process IDs.</span></span>
<span data-ttu-id="d5f3e-128">Por exemplo, `Get-Process -Id 664, 2060` .</span><span class="sxs-lookup"><span data-stu-id="d5f3e-128">For instance, `Get-Process -Id 664, 2060`.</span></span>

### <span data-ttu-id="d5f3e-129">Exemplo 3: obter todos os processos com um conjunto de trabalho maior que um tamanho especificado</span><span class="sxs-lookup"><span data-stu-id="d5f3e-129">Example 3: Get all processes with a working set greater than a specified size</span></span>

```powershell
Get-Process | Where-Object {$_.WorkingSet -gt 20000000}
```

<span data-ttu-id="d5f3e-130">Esse comando obtém todos os processos que têm um conjunto de trabalho de mais de 20 MB.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-130">This command gets all processes that have a working set greater than 20 MB.</span></span>
<span data-ttu-id="d5f3e-131">Ele usa o `Get-Process`  cmdlet para obter todos os processos em execução.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-131">It uses the `Get-Process`  cmdlet to get all running processes.</span></span>
<span data-ttu-id="d5f3e-132">O operador de pipeline `|` passa os objetos de processo para o `Where-Object` cmdlet, que seleciona apenas o objeto com um valor maior que 20 milhões bytes para a propriedade **WorkingSet** .</span><span class="sxs-lookup"><span data-stu-id="d5f3e-132">The pipeline operator `|` passes the process objects to the `Where-Object` cmdlet, which selects only the object with a value greater than 20,000,000 bytes for the **WorkingSet** property.</span></span>

<span data-ttu-id="d5f3e-133">O **WorkingSet** é uma das muitas propriedades de objetos de processo.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-133">**WorkingSet** is one of many properties of process objects.</span></span>
<span data-ttu-id="d5f3e-134">Para ver todas as propriedades, digite `Get-Process | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="d5f3e-134">To see all of the properties, type `Get-Process | Get-Member`.</span></span>
<span data-ttu-id="d5f3e-135">Por padrão, os valores de todas as propriedades de quantidade são em bytes, ainda que a exibição padrão as liste em quilobytes e megabytes.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-135">By default, the values of all amount properties are in bytes, even though the default display lists them in kilobytes and megabytes.</span></span>

### <span data-ttu-id="d5f3e-136">Exemplo 4: listar processos no computador em grupos com base na prioridade</span><span class="sxs-lookup"><span data-stu-id="d5f3e-136">Example 4: List processes on the computer in groups based on priority</span></span>

```powershell
$A = Get-Process
$A | Get-Process | Format-Table -View priority
```

<span data-ttu-id="d5f3e-137">Esses comandos listam os processos no computador em grupos com base em sua classe de prioridade.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-137">These commands list the processes on the computer in groups based on their priority class.</span></span>
<span data-ttu-id="d5f3e-138">O primeiro comando obtém todos os processos no computador e os armazena na `$A` variável.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-138">The first command gets all the processes on the computer and then stores them in the `$A` variable.</span></span>

<span data-ttu-id="d5f3e-139">O segundo comando canaliza o objeto de **processo** armazenado na `$A` variável para o `Get-Process` cmdlet e, em seguida, para o `Format-Table` cmdlet, que formata os processos usando a exibição de **prioridade** .</span><span class="sxs-lookup"><span data-stu-id="d5f3e-139">The second command pipes the **Process** object stored in the `$A` variable to the `Get-Process` cmdlet, then to the `Format-Table` cmdlet, which formats the processes by using the **Priority** view.</span></span>

<span data-ttu-id="d5f3e-140">A exibição de **prioridade** e outras exibições são definidas nos arquivos de formato ps1xml no diretório base do PowerShell ( `$pshome` ).</span><span class="sxs-lookup"><span data-stu-id="d5f3e-140">The **Priority** view, and other views, are defined in the PS1XML format files in the PowerShell home directory (`$pshome`).</span></span>

### <span data-ttu-id="d5f3e-141">Exemplo 5: adicionar uma propriedade à exibição de saída de Get-Process padrão</span><span class="sxs-lookup"><span data-stu-id="d5f3e-141">Example 5: Add a property to the standard Get-Process output display</span></span>

```powershell
Get-Process pwsh | Format-Table `
    @{Label = "NPM(K)"; Expression = {[int]($_.NPM / 1024)}},
    @{Label = "PM(K)"; Expression = {[int]($_.PM / 1024)}},
    @{Label = "WS(K)"; Expression = {[int]($_.WS / 1024)}},
    @{Label = "VM(M)"; Expression = {[int]($_.VM / 1MB)}},
    @{Label = "CPU(s)"; Expression = {if ($_.CPU) {$_.CPU.ToString("N")}}},
    Id, MachineName, ProcessName -AutoSize
```

```Output
NPM(K) PM(K) WS(K) VM(M) CPU(s)   Id MachineName ProcessName
------ ----- ----- ----- ------   -- ----------- -----------
     6 23500 31340   142 1.70   1980 .           pwsh
     6 23500 31348   142 2.75   4016 .           pwsh
    27 54572 54520   576 5.52   4428 .           pwsh
```

<span data-ttu-id="d5f3e-142">Este exemplo fornece um `Format-Table` comando que adiciona a propriedade **MachineName** à exibição de `Get-Process` saída padrão.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-142">This example provides a `Format-Table` command that adds the **MachineName** property to the standard `Get-Process` output display.</span></span>

### <span data-ttu-id="d5f3e-143">Exemplo 6: obter informações de versão para um processo</span><span class="sxs-lookup"><span data-stu-id="d5f3e-143">Example 6: Get version information for a process</span></span>

```powershell
Get-Process pwsh -FileVersionInfo
```

```Output
ProductVersion   FileVersion      FileName
--------------   -----------      --------
6.1.2            6.1.2            C:\Program Files\PowerShell\6\pwsh.exe
```

<span data-ttu-id="d5f3e-144">Esse comando usa o parâmetro **FileVersionInfo** para obter as informações de versão para o arquivo de pwsh.exe que é o módulo principal para o processo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-144">This command uses the **FileVersionInfo** parameter to get the version information for the pwsh.exe file that is the main module for the PowerShell process.</span></span>

<span data-ttu-id="d5f3e-145">Para executar esse comando com processos que não são de sua propriedade no Windows Vista e em versões posteriores do Windows, você deve abrir o PowerShell com a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-145">To run this command with processes that you do not own on Windows Vista and later versions of Windows, you must open PowerShell with the Run as administrator option.</span></span>

### <span data-ttu-id="d5f3e-146">Exemplo 7: obter módulos carregados com o processo especificado</span><span class="sxs-lookup"><span data-stu-id="d5f3e-146">Example 7: Get modules loaded with the specified process</span></span>

```powershell
Get-Process SQL* -Module
```

<span data-ttu-id="d5f3e-147">Esse comando usa o parâmetro **Module** para obter os módulos que foram carregados pelo processo.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-147">This command uses the **Module** parameter to get the modules that have been loaded by the process.</span></span>
<span data-ttu-id="d5f3e-148">Esse comando obtém os módulos para os processos que têm nomes que começam com SQL.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-148">This command gets the modules for the processes that have names that begin with SQL.</span></span>

<span data-ttu-id="d5f3e-149">Para executar esse comando no Windows Vista e em versões posteriores do Windows com processos que você não possui, você deve iniciar o PowerShell com a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-149">To run this command on Windows Vista and later versions of Windows with processes that you do not own, you must start PowerShell with the Run as administrator option.</span></span>

### <span data-ttu-id="d5f3e-150">Exemplo 8: localizar o proprietário de um processo</span><span class="sxs-lookup"><span data-stu-id="d5f3e-150">Example 8: Find the owner of a process</span></span>

```powershell
Get-Process pwsh -IncludeUserName
```

```Output
Handles      WS(K)   CPU(s)     Id UserName            ProcessName
-------      -----   ------     -- --------            -----------
    782     132080     2.08   2188 DOMAIN01\user01     pwsh
```

<span data-ttu-id="d5f3e-151">Este comando mostra como localizar o proprietário de um processo.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-151">This command shows how to find the owner of a process.</span></span>
<span data-ttu-id="d5f3e-152">No Windows, o parâmetro **IncludeUserName** requer direitos de usuário elevados (executar como administrador).</span><span class="sxs-lookup"><span data-stu-id="d5f3e-152">On Windows, the **IncludeUserName** parameter requires elevated user rights (Run as Administrator).</span></span>
<span data-ttu-id="d5f3e-153">A saída revela que o proprietário é Domain01\user01.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-153">The output reveals that the owner is Domain01\user01.</span></span>

### <span data-ttu-id="d5f3e-154">Exemplo 9: usar uma variável automática para identificar o processo que hospeda a sessão atual</span><span class="sxs-lookup"><span data-stu-id="d5f3e-154">Example 9: Use an automatic variable to identify the process hosting the current session</span></span>

```powershell
Get-Process pwsh
```

```Output
NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
------    -----      -----     ------      --  -- -----------
    83    96.21     105.95       4.33    1192  10 pwsh
    79    83.81     117.61       2.16   10580  10 pwsh
```

```powershell
Get-Process -Id $PID
```

```Output
NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
------    -----      -----     ------      --  -- -----------
    83    96.21      77.53       4.39    1192  10 pwsh
```

<span data-ttu-id="d5f3e-155">Esses comandos mostram como usar a `$PID` variável automática para identificar o processo que está hospedando a sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-155">These commands show how to use the `$PID` automatic variable to identify the process that is hosting the current PowerShell session.</span></span>
<span data-ttu-id="d5f3e-156">Você pode usar esse método para distinguir o processo de host de outros processos do PowerShell que talvez você queira parar ou fechar.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-156">You can use this method to distinguish the host process from other PowerShell processes that you might want to stop or close.</span></span>

<span data-ttu-id="d5f3e-157">O primeiro comando obtém todos os processos do PowerShell na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-157">The first command gets all of the PowerShell processes in the current session.</span></span>

<span data-ttu-id="d5f3e-158">O segundo comando obtém o processo do PowerShell que está hospedando a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-158">The second command gets the PowerShell process that is hosting the current session.</span></span>

### <span data-ttu-id="d5f3e-159">Exemplo 10: obter todos os processos que têm um título de janela principal e exibi-los em uma tabela</span><span class="sxs-lookup"><span data-stu-id="d5f3e-159">Example 10: Get all processes that have a main window title and display them in a table</span></span>

```powershell
Get-Process | Where-Object {$_.mainWindowTitle} | Format-Table Id, Name, mainWindowtitle -AutoSize
```

<span data-ttu-id="d5f3e-160">Esse comando obtém todos os processos que têm um título de janela principal e os exibe em uma tabela com a ID de processo e o nome do processo.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-160">This command gets all the processes that have a main window title, and it displays them in a table with the process ID and the process name.</span></span>

<span data-ttu-id="d5f3e-161">A propriedade **mainWindowTitle** é apenas uma das muitas propriedades úteis do objeto de **processo** que o `Get-Process` retorna.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-161">The **mainWindowTitle** property is just one of many useful properties of the **Process** object that `Get-Process` returns.</span></span>
<span data-ttu-id="d5f3e-162">Para exibir todas as propriedades, redirecione os resultados de um `Get-Process` comando para o `Get-Member` cmdlet `Get-Process | Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="d5f3e-162">To view all of the properties, pipe the results of a `Get-Process` command to the `Get-Member` cmdlet `Get-Process | Get-Member`.</span></span>

## <span data-ttu-id="d5f3e-163">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d5f3e-163">PARAMETERS</span></span>

### <span data-ttu-id="d5f3e-164">-FileVersionInfo</span><span class="sxs-lookup"><span data-stu-id="d5f3e-164">-FileVersionInfo</span></span>

<span data-ttu-id="d5f3e-165">Indica que esse cmdlet obtém as informações de versão de arquivo para o programa que é executado no processo.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-165">Indicates that this cmdlet gets the file version information for the program that runs in the process.</span></span>

<span data-ttu-id="d5f3e-166">No Windows Vista e versões posteriores do Windows, você deve abrir o PowerShell com a opção Executar como administrador para usar esse parâmetro em processos que não são de sua propriedade.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-166">On Windows Vista and later versions of Windows, you must open PowerShell with the Run as administrator option to use this parameter on processes that you do not own.</span></span>

<span data-ttu-id="d5f3e-167">Para obter informações de versão do arquivo para um processo em um computador remoto, use o `Invoke-Command` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-167">To get file version information for a process on a remote computer, use the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="d5f3e-168">O uso desse parâmetro é equivalente a obter a propriedade **MainModule. FileVersionInfo** de cada objeto de processo.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-168">Using this parameter is equivalent to getting the **MainModule.FileVersionInfo** property of each process object.</span></span>
<span data-ttu-id="d5f3e-169">Quando você usa esse parâmetro, `Get-Process` retorna um **FileVersionInfo** objeto FileVersionInfo **System. Diagnostics. FileVersionInfo** , não um objeto de processo.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-169">When you use this parameter, `Get-Process` returns a **FileVersionInfo** object **System.Diagnostics.FileVersionInfo** , not a process object.</span></span>
<span data-ttu-id="d5f3e-170">Portanto, não é possível canalizar a saída do comando para um cmdlet que espera um objeto de processo, como `Stop-Process` .</span><span class="sxs-lookup"><span data-stu-id="d5f3e-170">So, you cannot pipe the output of the command to a cmdlet that expects a process object, such as `Stop-Process`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Name, Id, InputObject
Aliases: FV, FVI

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5f3e-171">-Id</span><span class="sxs-lookup"><span data-stu-id="d5f3e-171">-Id</span></span>

<span data-ttu-id="d5f3e-172">Especifica um ou mais processos pela ID do processo (PID).</span><span class="sxs-lookup"><span data-stu-id="d5f3e-172">Specifies one or more processes by process ID (PID).</span></span>
<span data-ttu-id="d5f3e-173">Para especificar IDs múltiplas, use vírgulas para separá-las.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-173">To specify multiple IDs, use commas to separate the IDs.</span></span>
<span data-ttu-id="d5f3e-174">Para localizar o PID de um processo, digite `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="d5f3e-174">To find the PID of a process, type `Get-Process`.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id, IdWithUserName
Aliases: PID

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d5f3e-175">-IncludeUserName</span><span class="sxs-lookup"><span data-stu-id="d5f3e-175">-IncludeUserName</span></span>

<span data-ttu-id="d5f3e-176">Indica que o valor de nome de usuário do objeto de **processo** é retornado com os resultados do comando.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-176">Indicates that the UserName value of the **Process** object is returned with results of the command.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameWithUserName, IdWithUserName, InputObjectWithUserName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5f3e-177">-InputObject</span><span class="sxs-lookup"><span data-stu-id="d5f3e-177">-InputObject</span></span>

<span data-ttu-id="d5f3e-178">Especifica um ou mais objetos de processo.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-178">Specifies one or more process objects.</span></span>
<span data-ttu-id="d5f3e-179">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-179">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: InputObject, InputObjectWithUserName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d5f3e-180">-Módulo</span><span class="sxs-lookup"><span data-stu-id="d5f3e-180">-Module</span></span>

<span data-ttu-id="d5f3e-181">Indica que esse cmdlet obtém os módulos que foram carregados pelos processos.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-181">Indicates that this cmdlet gets the modules that have been loaded by the processes.</span></span>

<span data-ttu-id="d5f3e-182">No Windows Vista e versões posteriores do Windows, você deve abrir o PowerShell com a opção Executar como administrador para usar esse parâmetro em processos que não são de sua propriedade.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-182">On Windows Vista and later versions of Windows, you must open PowerShell with the Run as administrator option to use this parameter on processes that you do not own.</span></span>

<span data-ttu-id="d5f3e-183">Para obter os módulos que foram carregados por um processo em um computador remoto, use o `Invoke-Command` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-183">To get the modules that have been loaded by a process on a remote computer, use the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="d5f3e-184">Esse parâmetro é equivalente a obter a propriedade **modules** de cada objeto de processo.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-184">This parameter is equivalent to getting the **Modules** property of each process object.</span></span>
<span data-ttu-id="d5f3e-185">Quando você usa esse parâmetro, esse cmdlet retorna um **ProcessModule** objeto ProcessModule **System. Diagnostics. ProcessModule** , não um objeto de processo.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-185">When you use this parameter, this cmdlet returns a **ProcessModule** object **System.Diagnostics.ProcessModule** , not a process object.</span></span>
<span data-ttu-id="d5f3e-186">Portanto, não é possível canalizar a saída do comando para um cmdlet que espera um objeto de processo, como `Stop-Process` .</span><span class="sxs-lookup"><span data-stu-id="d5f3e-186">So, you cannot pipe the output of the command to a cmdlet that expects a process object, such as `Stop-Process`.</span></span>

<span data-ttu-id="d5f3e-187">Quando você usa os parâmetros *Module* e **FileVersionInfo** no mesmo comando, esse cmdlet retorna um objeto **FileVersionInfo** com informações sobre a versão do arquivo de todos os módulos.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-187">When you use both the *Module* and **FileVersionInfo** parameters in the same command, this cmdlet returns a **FileVersionInfo** object with information about the file version of all modules.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Name, Id, InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d5f3e-188">-Name</span><span class="sxs-lookup"><span data-stu-id="d5f3e-188">-Name</span></span>

<span data-ttu-id="d5f3e-189">Especifica um ou mais processos pelo nome do processo.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-189">Specifies one or more processes by process name.</span></span>
<span data-ttu-id="d5f3e-190">Você pode digitar vários nomes de processo (separados por vírgulas) e usar caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-190">You can type multiple process names (separated by commas) and use wildcard characters.</span></span>
<span data-ttu-id="d5f3e-191">O nome do parâmetro ("Name") é opcional.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-191">The parameter name ("Name") is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name, NameWithUserName
Aliases: ProcessName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="d5f3e-192">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d5f3e-192">CommonParameters</span></span>

<span data-ttu-id="d5f3e-193">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-193">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d5f3e-194">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="d5f3e-194">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="d5f3e-195">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="d5f3e-195">INPUTS</span></span>

### <span data-ttu-id="d5f3e-196">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="d5f3e-196">System.Diagnostics.Process</span></span>

<span data-ttu-id="d5f3e-197">É possível canalizar um objeto de processo para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-197">You can pipe a process object to this cmdlet.</span></span>

## <span data-ttu-id="d5f3e-198">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="d5f3e-198">OUTPUTS</span></span>

### <span data-ttu-id="d5f3e-199">System. Diagnostics. Process, System. Diagnostics. FileVersionInfo, System. Diagnostics. ProcessModule</span><span class="sxs-lookup"><span data-stu-id="d5f3e-199">System.Diagnostics.Process, System.Diagnostics.FileVersionInfo, System.Diagnostics.ProcessModule</span></span>

<span data-ttu-id="d5f3e-200">Por padrão, esse cmdlet retorna um objeto **System. Diagnostics. Process** .</span><span class="sxs-lookup"><span data-stu-id="d5f3e-200">By default, this cmdlet returns a **System.Diagnostics.Process** object.</span></span>
<span data-ttu-id="d5f3e-201">Se você usar o parâmetro **FileVersionInfo** , ele retornará um objeto **System. Diagnostics. FileVersionInfo** .</span><span class="sxs-lookup"><span data-stu-id="d5f3e-201">If you use the **FileVersionInfo** parameter, it returns a **System.Diagnostics.FileVersionInfo** object.</span></span>
<span data-ttu-id="d5f3e-202">Se você usar o parâmetro **Module** , sem o parâmetro **FileVersionInfo** , ele retornará um objeto **System. Diagnostics. ProcessModule** .</span><span class="sxs-lookup"><span data-stu-id="d5f3e-202">If you use the **Module** parameter, without the **FileVersionInfo** parameter, it returns a **System.Diagnostics.ProcessModule** object.</span></span>

## <span data-ttu-id="d5f3e-203">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="d5f3e-203">NOTES</span></span>

- <span data-ttu-id="d5f3e-204">Você também pode se referir a esse cmdlet por seus aliases internos, PS e GPS.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-204">You can also refer to this cmdlet by its built-in aliases, ps and gps.</span></span> <span data-ttu-id="d5f3e-205">Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="d5f3e-205">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="d5f3e-206">Em computadores que executam uma versão de 64 bits do Windows, a versão de 64 bits do PowerShell obtém apenas módulos de processo de 64 bits e a versão de 32 bits do PowerShell obtém apenas módulos de processo de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-206">On computers that are running a 64-bit version of Windows, the 64-bit version of PowerShell gets only 64-bit process modules and the 32-bit version of PowerShell gets only 32-bit process modules.</span></span>
- <span data-ttu-id="d5f3e-207">Você pode usar as propriedades e métodos do objeto Instrumentação de Gerenciamento do Windows (WMI) Win32_Process no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-207">You can use the properties and methods of the Windows Management Instrumentation (WMI) Win32_Process object in PowerShell.</span></span> <span data-ttu-id="d5f3e-208">Para obter informações, consulte `Get-WmiObject` e o SDK do WMI.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-208">For information, see `Get-WmiObject` and the WMI SDK.</span></span>
- <span data-ttu-id="d5f3e-209">A exibição padrão de um processo é uma tabela que inclui as colunas a seguir.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-209">The default display of a process is a table that includes the following columns.</span></span> <span data-ttu-id="d5f3e-210">Para obter uma descrição de todas as propriedades de objetos de processo, consulte [Propriedades do processo](/dotnet/api/system.diagnostics.process) na biblioteca MSDN.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-210">For a description of all of the properties of process objects, see [Process Properties](/dotnet/api/system.diagnostics.process) in the MSDN library.</span></span>
  - <span data-ttu-id="d5f3e-211">Handles: o número de identificadores que o processo abriu.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-211">Handles: The number of handles that the process has opened.</span></span>
  - <span data-ttu-id="d5f3e-212">NPM (K): a quantidade de memória não paginável que o processo está usando, em quilobytes.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-212">NPM(K): The amount of non-paged memory that the process is using, in kilobytes.</span></span>
  - <span data-ttu-id="d5f3e-213">PM (K): a quantidade de memória paginável que o processo está usando, em quilobytes.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-213">PM(K): The amount of pageable memory that the process is using, in kilobytes.</span></span>
  - <span data-ttu-id="d5f3e-214">WS (K): o tamanho do conjunto de trabalho do processo, em quilobytes.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-214">WS(K): The size of the working set of the process, in kilobytes.</span></span>
    <span data-ttu-id="d5f3e-215">O conjunto de trabalho consiste de páginas de memória que foram referenciadas recentemente pelo processo.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-215">The working set consists of the pages of memory that were recently referenced by the process.</span></span>
  - <span data-ttu-id="d5f3e-216">VM (M): a quantidade de memória virtual que o processo está usando, em megabytes.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-216">VM(M): The amount of virtual memory that the process is using, in megabytes.</span></span>
    <span data-ttu-id="d5f3e-217">Memória virtual inclui armazenamento nos arquivos de paginação em disco.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-217">Virtual memory includes storage in the paging files on disk.</span></span>
  - <span data-ttu-id="d5f3e-218">CPU (s): a quantidade de tempo do processador que o processo usou em todos os processadores, em segundos.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-218">CPU(s): The amount of processor time that the process has used on all processors, in seconds.</span></span>
  - <span data-ttu-id="d5f3e-219">ID: a ID do processo (PID) do processo.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-219">ID: The process ID (PID) of the process.</span></span>
  - <span data-ttu-id="d5f3e-220">ProcessName: o nome do processo.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-220">ProcessName: The name of the process.</span></span>
    <span data-ttu-id="d5f3e-221">Para obter explicações sobre os conceitos relacionados aos processos, consulte o Glossário na Ajuda e no Centro de Suporte e a Ajuda do Gerenciador de Tarefas.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-221">For explanations of the concepts related to processes, see the Glossary in Help and Support Center and the Help for Task Manager.</span></span>
- <span data-ttu-id="d5f3e-222">Você também pode usar as exibições alternativas internas dos processos disponíveis com, como `Format-Table` **StartTime** e **Priority** , e pode criar suas próprias exibições.</span><span class="sxs-lookup"><span data-stu-id="d5f3e-222">You can also use the built-in alternate views of the processes available with `Format-Table`, such as **StartTime** and **Priority** , and you can design your own views.</span></span>

## <span data-ttu-id="d5f3e-223">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="d5f3e-223">RELATED LINKS</span></span>

[<span data-ttu-id="d5f3e-224">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="d5f3e-224">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="d5f3e-225">Get-Process</span><span class="sxs-lookup"><span data-stu-id="d5f3e-225">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="d5f3e-226">Start-Process</span><span class="sxs-lookup"><span data-stu-id="d5f3e-226">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="d5f3e-227">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="d5f3e-227">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="d5f3e-228">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="d5f3e-228">Wait-Process</span></span>](Wait-Process.md)

