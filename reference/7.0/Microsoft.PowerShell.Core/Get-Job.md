---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-job?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Job
ms.openlocfilehash: e93a46d863fb560c70d9257270af1e6f43d3f248
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94391180"
---
# <span data-ttu-id="40654-103">Get-Job</span><span class="sxs-lookup"><span data-stu-id="40654-103">Get-Job</span></span>

## <span data-ttu-id="40654-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="40654-104">SYNOPSIS</span></span>
<span data-ttu-id="40654-105">Obtém trabalhos em segundo plano do PowerShell que estão em execução na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="40654-105">Gets PowerShell background jobs that are running in the current session.</span></span>

## <span data-ttu-id="40654-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="40654-106">SYNTAX</span></span>

### <span data-ttu-id="40654-107">SessionIdParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="40654-107">SessionIdParameterSet (Default)</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [[-Id] <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="40654-108">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="40654-108">InstanceIdParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="40654-109">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="40654-109">NameParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="40654-110">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="40654-110">StateParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-State] <JobState> [<CommonParameters>]
```

### <span data-ttu-id="40654-111">CommandParameterSet</span><span class="sxs-lookup"><span data-stu-id="40654-111">CommandParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Command <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="40654-112">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="40654-112">FilterParameterSet</span></span>

```
Get-Job [-Filter] <Hashtable> [<CommonParameters>]
```

## <span data-ttu-id="40654-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="40654-113">DESCRIPTION</span></span>

<span data-ttu-id="40654-114">O `Get-Job` cmdlet obtém objetos que representam os trabalhos em segundo plano que foram iniciados na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="40654-114">The `Get-Job` cmdlet gets objects that represent the background jobs that were started in the current session.</span></span> <span data-ttu-id="40654-115">Você pode usar `Get-Job` o para obter trabalhos que foram iniciados usando o `Start-Job` cmdlet ou usando o parâmetro **AsJob** de qualquer cmdlet.</span><span class="sxs-lookup"><span data-stu-id="40654-115">You can use `Get-Job` to get jobs that were started by using the `Start-Job` cmdlet, or by using the **AsJob** parameter of any cmdlet.</span></span>

<span data-ttu-id="40654-116">Sem parâmetros, um `Get-Job` comando obtém todos os trabalhos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="40654-116">Without parameters, a `Get-Job` command gets all jobs in the current session.</span></span> <span data-ttu-id="40654-117">Você pode usar os parâmetros de `Get-Job` para obter trabalhos específicos.</span><span class="sxs-lookup"><span data-stu-id="40654-117">You can use the parameters of `Get-Job` to get particular jobs.</span></span>

<span data-ttu-id="40654-118">O objeto de trabalho que `Get-Job` retorna contém informações úteis sobre o trabalho, mas não contém os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="40654-118">The job object that `Get-Job` returns contains useful information about the job, but it does not contain the job results.</span></span> <span data-ttu-id="40654-119">Para obter os resultados, use o `Receive-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="40654-119">To get the results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="40654-120">Um trabalho em segundo plano do Windows PowerShell é um comando que é executado em segundo plano sem interagir com a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="40654-120">A Windows PowerShell background job is a command that runs in the background without interacting with the current session.</span></span> <span data-ttu-id="40654-121">Normalmente, você usa um trabalho em segundo plano para executar um comando complexo que leva muito tempo para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="40654-121">Typically, you use a background job to run a complex command that takes a long time to finish.</span></span> <span data-ttu-id="40654-122">Para obter mais informações sobre trabalhos em segundo plano no Windows PowerShell, consulte [about_Jobs](./about/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="40654-122">For more information about background jobs in Windows PowerShell, see [about_Jobs](./about/about_Jobs.md).</span></span>

<span data-ttu-id="40654-123">A partir do Windows PowerShell 3,0, o `Get-Job` cmdlet também obtém tipos de trabalhos personalizados, como trabalhos de fluxo de trabalho e instâncias de trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="40654-123">Beginning in Windows PowerShell 3.0, the `Get-Job` cmdlet also gets custom job types, such as workflow jobs and instances of scheduled jobs.</span></span> <span data-ttu-id="40654-124">Para localizar o tipo de um trabalho, use a propriedade **PSJobTypeName** do trabalho em questão.</span><span class="sxs-lookup"><span data-stu-id="40654-124">To find the job type of a job, use the **PSJobTypeName** property of the job.</span></span>

<span data-ttu-id="40654-125">Para habilitar o `Get-Job` para obter um tipo de trabalho personalizado, importe o módulo que dá suporte ao tipo de trabalho personalizado na sessão antes de executar um `Get-Job` comando, seja usando o `Import-Module` cmdlet ou obtendo um cmdlet no módulo.</span><span class="sxs-lookup"><span data-stu-id="40654-125">To enable `Get-Job` to get a custom job type, import the module that supports the custom job type into the session before you run a `Get-Job` command, either by using the `Import-Module` cmdlet or by using or getting a cmdlet in the module.</span></span> <span data-ttu-id="40654-126">Para obter informações sobre um tipo específico de trabalho personalizado, consulte a documentação do recurso de tipo de trabalho personalizado.</span><span class="sxs-lookup"><span data-stu-id="40654-126">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="40654-127">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="40654-127">EXAMPLES</span></span>

### <span data-ttu-id="40654-128">Exemplo 1: obter todos os trabalhos em segundo plano iniciados na sessão atual</span><span class="sxs-lookup"><span data-stu-id="40654-128">Example 1: Get all background jobs started in the current session</span></span>

<span data-ttu-id="40654-129">Esse comando obtém todos os trabalhos em segundo plano iniciados na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="40654-129">This command gets all background jobs started in the current session.</span></span> <span data-ttu-id="40654-130">Ele não inclui trabalhos criados em outras sessões, mesmo se os trabalhos forem executados no computador local.</span><span class="sxs-lookup"><span data-stu-id="40654-130">It does not include jobs created in other sessions, even if the jobs run on the local computer.</span></span>

```
PS C:\> Get-Job
```

### <span data-ttu-id="40654-131">Exemplo 2: parar um trabalho usando uma ID de instância</span><span class="sxs-lookup"><span data-stu-id="40654-131">Example 2: Stop a job by using an instance ID</span></span>

<span data-ttu-id="40654-132">Esses comandos mostram como obter o identificador de instância de um trabalho e, em seguida, usá-lo para interromper esse trabalho.</span><span class="sxs-lookup"><span data-stu-id="40654-132">These commands show how to get the instance ID of a job and then use it to stop a job.</span></span> <span data-ttu-id="40654-133">Ao contrário do nome de um determinado trabalho, que não é exclusivo, o identificador da instância é.</span><span class="sxs-lookup"><span data-stu-id="40654-133">Unlike the name of a job, which is not unique, the instance ID is unique.</span></span>

<span data-ttu-id="40654-134">O primeiro comando usa o `Get-Job` cmdlet para obter um trabalho.</span><span class="sxs-lookup"><span data-stu-id="40654-134">The first command uses the `Get-Job` cmdlet to get a job.</span></span> <span data-ttu-id="40654-135">Ele usa o parâmetro **Name** para identificar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="40654-135">It uses the **Name** parameter to identify the job.</span></span> <span data-ttu-id="40654-136">O comando armazena o objeto de trabalho que `Get-Job` retorna na `$j` variável.</span><span class="sxs-lookup"><span data-stu-id="40654-136">The command stores the job object that `Get-Job` returns in the `$j` variable.</span></span> <span data-ttu-id="40654-137">Neste exemplo, há apenas um trabalho com o nome especificado.</span><span class="sxs-lookup"><span data-stu-id="40654-137">In this example, there is only one job with the specified name.</span></span> <span data-ttu-id="40654-138">O segundo comando obtém a propriedade **InstanceId** do objeto na `$j` variável e a armazena na `$ID` variável.</span><span class="sxs-lookup"><span data-stu-id="40654-138">The second command gets the **InstanceId** property of the object in the `$j` variable and stores it in the `$ID` variable.</span></span> <span data-ttu-id="40654-139">O terceiro comando exibe o valor da `$ID` variável.</span><span class="sxs-lookup"><span data-stu-id="40654-139">The third command displays the value of the `$ID` variable.</span></span> <span data-ttu-id="40654-140">O quarto comando usa `Stop-Job` o cmdlet para interromper o trabalho.</span><span class="sxs-lookup"><span data-stu-id="40654-140">The fourth command uses `Stop-Job` cmdlet to stop the job.</span></span>
<span data-ttu-id="40654-141">Ele usa o parâmetro **InstanceId** para identificar o trabalho e a `$ID` variável para representar a ID da instância do trabalho.</span><span class="sxs-lookup"><span data-stu-id="40654-141">It uses the **InstanceId** parameter to identify the job and `$ID` variable to represent the instance ID of the job.</span></span>

```
PS C:\> $j = Get-Job -Name Job1
PS C:\> $ID = $j.InstanceID
PS C:\> $ID

Guid
----
03c3232e-1d23-453b-a6f4-ed73c9e29d55

PS C:\> Stop-Job -InstanceId $ID
```

### <span data-ttu-id="40654-142">Exemplo 3: obter trabalhos que incluem um comando específico</span><span class="sxs-lookup"><span data-stu-id="40654-142">Example 3: Get jobs that include a specific command</span></span>

<span data-ttu-id="40654-143">Esse comando obtém os trabalhos no sistema que incluem um `Get-Process` comando.</span><span class="sxs-lookup"><span data-stu-id="40654-143">This command gets the jobs on the system that include a `Get-Process` command.</span></span> <span data-ttu-id="40654-144">O comando usa o parâmetro de **comando** de `Get-Job` para limitar os trabalhos recuperados.</span><span class="sxs-lookup"><span data-stu-id="40654-144">The command uses the **Command** parameter of `Get-Job` to limit the jobs retrieved.</span></span> <span data-ttu-id="40654-145">O comando usa caracteres curinga ( `*` ) para obter trabalhos que incluem um `Get-Process` comando em qualquer lugar na cadeia de caracteres de comando.</span><span class="sxs-lookup"><span data-stu-id="40654-145">The command uses wildcard characters (`*`) to get jobs that include a `Get-Process` command anywhere in the command string.</span></span>

```
PS C:\> Get-Job -Command "*get-process*"
```

### <span data-ttu-id="40654-146">Exemplo 4: obter trabalhos que incluem um comando específico usando o pipeline</span><span class="sxs-lookup"><span data-stu-id="40654-146">Example 4: Get jobs that include a specific command by using the pipeline</span></span>

<span data-ttu-id="40654-147">Como o comando no exemplo anterior, esse comando obtém os trabalhos no sistema que incluem um `Get-Process` comando.</span><span class="sxs-lookup"><span data-stu-id="40654-147">Like the command in the previous example, this command gets the jobs on the system that include a `Get-Process` command.</span></span> <span data-ttu-id="40654-148">O comando usa um operador de pipeline ( `|` ) para enviar uma cadeia de caracteres, entre aspas, para o `Get-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="40654-148">The command uses a pipeline operator (`|`) to send a string, in quotation marks, to the `Get-Job` cmdlet.</span></span> <span data-ttu-id="40654-149">Ele é o equivalente do comando anterior.</span><span class="sxs-lookup"><span data-stu-id="40654-149">It is the equivalent of the previous command.</span></span>

```
PS C:\> "*get-process*" | Get-Job
```

### <span data-ttu-id="40654-150">Exemplo 5: obter trabalhos que não foram iniciados</span><span class="sxs-lookup"><span data-stu-id="40654-150">Example 5: Get jobs that have not been started</span></span>

<span data-ttu-id="40654-151">Este comando obtém apenas os trabalhos que foram criados, mas ainda não foi iniciados.</span><span class="sxs-lookup"><span data-stu-id="40654-151">This command gets only those jobs that have been created but have not yet been started.</span></span> <span data-ttu-id="40654-152">Isso inclui trabalhos agendados para execução no futuro e aqueles ainda não foram agendados.</span><span class="sxs-lookup"><span data-stu-id="40654-152">This includes jobs that are scheduled to run in the future and those not yet scheduled.</span></span>

```
PS C:\> Get-Job -State NotStarted
```

### <span data-ttu-id="40654-153">Exemplo 6: obter trabalhos que não foram atribuídos a um nome</span><span class="sxs-lookup"><span data-stu-id="40654-153">Example 6: Get jobs that have not been assigned a name</span></span>

<span data-ttu-id="40654-154">Esse comando obtém todos os trabalhos que têm nomes de trabalho que começam com o trabalho.</span><span class="sxs-lookup"><span data-stu-id="40654-154">This command gets all jobs that have job names that begin with job.</span></span> <span data-ttu-id="40654-155">Como `job<number>` é o nome padrão de um trabalho, esse comando obtém todos os trabalhos que não têm um nome explicitamente atribuído.</span><span class="sxs-lookup"><span data-stu-id="40654-155">Because `job<number>` is the default name for a job, this command gets all jobs that do not have an explicitly assigned name.</span></span>

```
PS C:\> Get-Job -Name Job*
```

### <span data-ttu-id="40654-156">Exemplo 7: usar um objeto de trabalho para representar o trabalho em um comando</span><span class="sxs-lookup"><span data-stu-id="40654-156">Example 7: Use a job object to represent the job in a command</span></span>

<span data-ttu-id="40654-157">Este exemplo mostra como usar `Get-Job` o para obter um objeto de trabalho e, em seguida, mostra como usar o objeto de trabalho para representar o trabalho em um comando.</span><span class="sxs-lookup"><span data-stu-id="40654-157">This example shows how to use `Get-Job` to get a job object, and then it shows how to use the job object to represent the job in a command.</span></span>

<span data-ttu-id="40654-158">O primeiro comando usa o `Start-Job` cmdlet para iniciar um trabalho em segundo plano que executa um `Get-Process` comando no computador local.</span><span class="sxs-lookup"><span data-stu-id="40654-158">The first command uses the `Start-Job` cmdlet to start a background job that runs a `Get-Process` command on the local computer.</span></span> <span data-ttu-id="40654-159">O comando usa o parâmetro **Name** de `Start-Job` para atribuir um nome amigável ao trabalho.</span><span class="sxs-lookup"><span data-stu-id="40654-159">The command uses the **Name** parameter of `Start-Job` to assign a friendly name to the job.</span></span> <span data-ttu-id="40654-160">O segundo comando usa `Get-Job` para obter o trabalho.</span><span class="sxs-lookup"><span data-stu-id="40654-160">The second command uses `Get-Job` to get the job.</span></span> <span data-ttu-id="40654-161">Ele usa o parâmetro **Name** de `Get-Job` para identificar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="40654-161">It uses the **Name** parameter of `Get-Job` to identify the job.</span></span> <span data-ttu-id="40654-162">O comando salva o objeto de trabalho resultante na `$j` variável.</span><span class="sxs-lookup"><span data-stu-id="40654-162">The command saves the resulting job object in the `$j` variable.</span></span> <span data-ttu-id="40654-163">O terceiro comando exibe o valor do objeto de trabalho na `$j` variável.</span><span class="sxs-lookup"><span data-stu-id="40654-163">The third command displays the value of the job object in the `$j` variable.</span></span> <span data-ttu-id="40654-164">O valor da propriedade **State** mostra que o trabalho foi concluído.</span><span class="sxs-lookup"><span data-stu-id="40654-164">The value of the **State** property shows that the job is completed.</span></span> <span data-ttu-id="40654-165">O valor da propriedade **HasMoreData** mostra que há resultados disponíveis do trabalho que ainda não foram recuperados.</span><span class="sxs-lookup"><span data-stu-id="40654-165">The value of the **HasMoreData** property shows that there are results available from the job that have not yet been retrieved.</span></span> <span data-ttu-id="40654-166">O quarto comando usa o `Receive-Job` cmdlet para obter os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="40654-166">The fourth command uses the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="40654-167">Ele usa o objeto de trabalho na `$j` variável para representar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="40654-167">It uses the job object in the `$j` variable to represent the job.</span></span> <span data-ttu-id="40654-168">Você também pode usar um operador de pipeline para enviar um objeto de trabalho para o `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="40654-168">You can also use a pipeline operator to send a job object to `Receive-Job`.</span></span>

```
PS C:\> Start-Job -ScriptBlock {Get-Process} -Name MyJob
PS C:\> $j = Get-Job -Name MyJob
PS C:\> $j
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
6      MyJob           BackgroundJob   Completed     True            localhost            Get-Process

PS C:\> Receive-Job -Job $j
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    124       4    13572      12080    59            1140 audiodg
    783      16    11428      13636   100             548 CcmExec
     96       4     4252       3764    59            3856 ccmsetup
...
```


### <span data-ttu-id="40654-169">Exemplo 8: obter todos os trabalhos, incluindo trabalhos iniciados por um método diferente</span><span class="sxs-lookup"><span data-stu-id="40654-169">Example 8: Get all jobs including jobs started by a different method</span></span>

<span data-ttu-id="40654-170">Este exemplo demonstra que o `Get-Job` cmdlet pode obter todos os trabalhos que foram iniciados na sessão atual, mesmo que eles tenham sido iniciados usando métodos diferentes.</span><span class="sxs-lookup"><span data-stu-id="40654-170">This example demonstrates that the `Get-Job` cmdlet can get all of the jobs that were started in the current session, even if they were started by using different methods.</span></span>

<span data-ttu-id="40654-171">O primeiro comando usa o `Start-Job` cmdlet para iniciar um trabalho no computador local.</span><span class="sxs-lookup"><span data-stu-id="40654-171">The first command uses the `Start-Job` cmdlet to start a job on the local computer.</span></span> <span data-ttu-id="40654-172">O segundo comando usa o parâmetro **AsJob** do `Invoke-Command` cmdlet para iniciar um trabalho no computador S1.</span><span class="sxs-lookup"><span data-stu-id="40654-172">The second command uses the **AsJob** parameter of the `Invoke-Command` cmdlet to start a job on the S1 computer.</span></span> <span data-ttu-id="40654-173">Embora os comandos do trabalho sejam executados no computador remoto, o objeto de trabalho é criado no computador local, para que você use comandos locais para gerenciar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="40654-173">Even though the commands in the job run on the remote computer, the job object is created on the local computer, so you use local commands to manage the job.</span></span> <span data-ttu-id="40654-174">O terceiro comando usa o `Invoke-Command` cmdlet para executar um `Start-Job` comando no computador S2.</span><span class="sxs-lookup"><span data-stu-id="40654-174">The third command uses the `Invoke-Command` cmdlet to run a `Start-Job` command on the S2 computer.</span></span> <span data-ttu-id="40654-175">Usando esse método, o objeto de trabalho é criado no computador remoto, portanto, você usa comandos remotos para gerenciar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="40654-175">By using this method, the job object is created on the remote computer, so you use remote commands to manage the job.</span></span> <span data-ttu-id="40654-176">O quarto comando usa `Get-Job` para obter os trabalhos armazenados no computador local.</span><span class="sxs-lookup"><span data-stu-id="40654-176">The fourth command uses `Get-Job` to get the jobs stored on the local computer.</span></span> <span data-ttu-id="40654-177">A propriedade **PSJobTypeName** dos trabalhos, introduzida no Windows PowerShell 3,0, mostra que o trabalho local iniciado usando o `Start-Job` cmdlet é um trabalho em segundo plano e o trabalho iniciado em uma sessão remota usando o `Invoke-Command` cmdlet é um trabalho remoto.</span><span class="sxs-lookup"><span data-stu-id="40654-177">The **PSJobTypeName** property of jobs, introduced in Windows PowerShell 3.0, shows that the local job started by using the `Start-Job` cmdlet is a background job and the job started in a remote session by using the `Invoke-Command` cmdlet is a remote job.</span></span> <span data-ttu-id="40654-178">O quinto comando usa `Invoke-Command` para executar um `Get-Job` comando no computador S2. A saída de exemplo mostra os resultados do `Get-Job` comando.</span><span class="sxs-lookup"><span data-stu-id="40654-178">The fifth command uses `Invoke-Command` to run a `Get-Job` command on the S2 computer.The sample output shows the results of the `Get-Job` command.</span></span> <span data-ttu-id="40654-179">No computador S2, o trabalho parece ser um trabalho local.</span><span class="sxs-lookup"><span data-stu-id="40654-179">On the S2 computer, the job appears to be a local job.</span></span> <span data-ttu-id="40654-180">O nome do computador é localhost e o tipo de trabalho é um trabalho em segundo plano. Para obter mais informações sobre como executar trabalhos em segundo plano em computadores remotos, consulte [about_Remote_Jobs](./about/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="40654-180">The computer name is localhost and the job type is a background job.For more information about how to run background jobs on remote computers, see [about_Remote_Jobs](./about/about_Remote_Jobs.md).</span></span>

```
PS C:\> Start-Job -ScriptBlock {Get-EventLog System}
PS C:\> Invoke-Command -ComputerName S1 -ScriptBlock {Get-EventLog System} -AsJob
PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
PS C:\> Get-Job
Id     Name       PSJobTypeName   State         HasMoreData     Location        Command
--     ----       -------------   -----         -----------     --------        -------
1      Job1       BackgroundJob   Running       True            localhost       Get-EventLog System
2      Job2       RemoteJob       Running       True            S1              Get-EventLog System

PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Id    Name     PSJobTypeName  State      HasMoreData   Location   Command
--    ----     -------------  -----      -----------   -------    -------
4     Job4     BackgroundJob  Running    True          localhost  Get-Eventlog System
```

### <span data-ttu-id="40654-181">Exemplo 9: investigar um trabalho com falha</span><span class="sxs-lookup"><span data-stu-id="40654-181">Example 9: Investigate a failed job</span></span>

<span data-ttu-id="40654-182">Este comando mostra como usar o objeto de trabalho que `Get-Job` retorna para investigar por que um trabalho falhou.</span><span class="sxs-lookup"><span data-stu-id="40654-182">This command shows how to use the job object that `Get-Job` returns to investigate why a job failed.</span></span>
<span data-ttu-id="40654-183">Ele também mostra como obter os trabalhos filhos de cada trabalho.</span><span class="sxs-lookup"><span data-stu-id="40654-183">It also shows how to get the child jobs of each job.</span></span>

<span data-ttu-id="40654-184">O primeiro comando usa o `Start-Job` cmdlet para iniciar um trabalho no computador local.</span><span class="sxs-lookup"><span data-stu-id="40654-184">The first command uses the `Start-Job` cmdlet to start a job on the local computer.</span></span> <span data-ttu-id="40654-185">O objeto de trabalho que `Start-Job` retorna mostra que o trabalho falhou.</span><span class="sxs-lookup"><span data-stu-id="40654-185">The job object that `Start-Job` returns shows that the job failed.</span></span> <span data-ttu-id="40654-186">Falha no valor da propriedade de **estado** .</span><span class="sxs-lookup"><span data-stu-id="40654-186">The value of the **State** property is Failed.</span></span>

<span data-ttu-id="40654-187">O segundo comando usa o `Get-Job` cmdlet para obter o trabalho.</span><span class="sxs-lookup"><span data-stu-id="40654-187">The second command uses the `Get-Job` cmdlet to get the job.</span></span> <span data-ttu-id="40654-188">O segundo comando usa o método de ponto para exibir o valor da propriedade **JobStateInfo** do objeto.</span><span class="sxs-lookup"><span data-stu-id="40654-188">The command uses the dot method to get the value of the **JobStateInfo** property of the object.</span></span> <span data-ttu-id="40654-189">Ele usa um operador de pipeline para enviar o objeto na propriedade **JobStateInfo** para o `Format-List` cmdlet, que formata todas as propriedades do objeto ( `*` ) em uma lista. O resultado do `Format-List` comando mostra que o valor da propriedade **Reason** do trabalho está em branco.</span><span class="sxs-lookup"><span data-stu-id="40654-189">It uses a pipeline operator to send the object in the **JobStateInfo** property to the `Format-List` cmdlet, which formats all of the properties of the object (`*`) in a list.The result of the `Format-List` command shows that the value of the **Reason** property of the job is blank.</span></span>

<span data-ttu-id="40654-190">O terceiro comando investiga mais.</span><span class="sxs-lookup"><span data-stu-id="40654-190">The third command investigates more.</span></span> <span data-ttu-id="40654-191">Ele usa um `Get-Job` comando para obter o trabalho e, em seguida, usa um operador de pipeline para enviar todo o objeto de trabalho para o `Format-List` cmdlet, que exibe todas as propriedades do trabalho em uma lista. A exibição de todas as propriedades no objeto de trabalho mostra que o trabalho contém um trabalho filho chamado Job2.</span><span class="sxs-lookup"><span data-stu-id="40654-191">It uses a `Get-Job` command to get the job and then uses a pipeline operator to send the whole job object to the `Format-List` cmdlet, which displays all of the properties of the job in a list.The display of all properties in the job object shows that the job contains a child job named Job2.</span></span>

<span data-ttu-id="40654-192">O quarto comando usa `Get-Job` para obter o objeto de trabalho que representa o trabalho filho Job2.</span><span class="sxs-lookup"><span data-stu-id="40654-192">The fourth command uses `Get-Job` to get the job object that represents the Job2 child job.</span></span> <span data-ttu-id="40654-193">Esse é o trabalho no qual o comando foi realmente executado.</span><span class="sxs-lookup"><span data-stu-id="40654-193">This is the job in which the command actually ran.</span></span> <span data-ttu-id="40654-194">Ele usa o método dot para obter a propriedade **Reason** da propriedade **JobStateInfo** . O resultado mostra que o trabalho falhou devido a um erro de acesso negado.</span><span class="sxs-lookup"><span data-stu-id="40654-194">It uses the dot method to get the **Reason** property of the **JobStateInfo** property.The result shows that the job failed because of an Access Denied error.</span></span> <span data-ttu-id="40654-195">Nesse caso, o usuário esqueceu de usar a opção Executar como administrador ao iniciar o Windows PowerShell. como os trabalhos em segundo plano usam os recursos de comunicação remota do Windows PowerShell, o computador deve ser configurado para comunicação remota para executar um trabalho, mesmo quando o trabalho é executado no computador local. Para obter informações sobre os requisitos de comunicação remota no Windows PowerShell, consulte [about_Remote_Requirements](./about/about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40654-195">In this case, the user forgot to use the Run as administrator option when starting Windows PowerShell.Because background jobs use the remoting features of Windows PowerShell, the computer must be configured for remoting to run a job, even when the job runs on the local computer.For information about requirements for remoting in Windows PowerShell, see [about_Remote_Requirements](./about/about_Remote_Requirements.md).</span></span> <span data-ttu-id="40654-196">Para obter dicas para solução de problemas, consulte [about_Remote_Troubleshooting](./about/about_Remote_Troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="40654-196">For troubleshooting tips, see [about_Remote_Troubleshooting](./about/about_Remote_Troubleshooting.md).</span></span>

```
PS C:\> Start-Job -ScriptBlock {Get-Process}
Id     Name       PSJobTypeName   State       HasMoreData     Location             Command
--     ----       -------------   -----       -----------     --------             -------
1      Job1       BackgroundJob   Failed      False           localhost            Get-Process

PS C:\> (Get-Job).JobStateInfo | Format-List -Property *
State  : Failed
Reason :

PS C:\> Get-Job | Format-List -Property *
HasMoreData   : False
StatusMessage :
Location      : localhost
Command       : get-process
JobStateInfo  : Failed
Finished      : System.Threading.ManualReset
EventInstanceId    : fb792295-1318-4f5d-8ac8-8a89c5261507
Id            : 1
Name          : Job1
ChildJobs     : {Job2}
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
StateChanged  :

PS C:\> (Get-Job -Name job2).JobStateInfo.Reason
Connecting to remote server using WSManCreateShellEx api failed. The async callback gave the
following error message: Access is denied.
```

### <span data-ttu-id="40654-197">Exemplo 10: obter resultados filtrados</span><span class="sxs-lookup"><span data-stu-id="40654-197">Example 10: Get filtered results</span></span>

<span data-ttu-id="40654-198">Este exemplo mostra como usar o parâmetro **Filter** para obter uma tarefa de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="40654-198">This example shows how to use the **Filter** parameter to get a workflow job.</span></span> <span data-ttu-id="40654-199">O parâmetro **Filter** , introduzido no Windows PowerShell 3.0, é válido somente em tipos de trabalho personalizados, como tarefas de fluxo de trabalho e trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="40654-199">The **Filter** parameter, introduced in Windows PowerShell 3.0 is valid only on custom job types, such as workflow jobs and scheduled jobs.</span></span>

<span data-ttu-id="40654-200">O primeiro comando usa a palavra-chave **Workflow** para criar o fluxo de trabalho WFProcess.</span><span class="sxs-lookup"><span data-stu-id="40654-200">The first command uses the **Workflow** keyword to create the WFProcess workflow.</span></span> <span data-ttu-id="40654-201">O segundo comando usa o parâmetro **AsJob** do fluxo de trabalho do amWFProcess para executar o workflow como uma tarefa em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="40654-201">The second command uses the **AsJob** parameter of the WFProcess workflow to run the workflow as a background job.</span></span> <span data-ttu-id="40654-202">Ele usa o parâmetro **JobName** do fluxo de trabalho para especificar um nome para o trabalho e o parâmetro **PSPrivateMetadata** do fluxo de trabalho para especificar um identificador personalizado.</span><span class="sxs-lookup"><span data-stu-id="40654-202">It uses the **JobName** parameter of the workflow to specify a name for the job, and the **PSPrivateMetadata** parameter of the workflow to specify a custom ID.</span></span> <span data-ttu-id="40654-203">O terceiro comando usa o parâmetro **Filter** de `Get-Job` para obter o trabalho por ID personalizada que foi especificado no parâmetro **PSPrivateMetadata** .</span><span class="sxs-lookup"><span data-stu-id="40654-203">The third command uses the **Filter** parameter of `Get-Job` to get the job by custom ID that was specified in the **PSPrivateMetadata** parameter.</span></span>

```
PS C:\> Workflow WFProcess {Get-Process}
PS C:\> WFProcess -AsJob -JobName WFProcessJob -PSPrivateMetadata @{MyCustomId = 92107}
PS C:\> Get-Job -Filter @{MyCustomId = 92107}
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
1      WFProcessJob    Completed     True            localhost            WFProcess
```

### <span data-ttu-id="40654-204">Exemplo 11: obter informações sobre trabalhos filho</span><span class="sxs-lookup"><span data-stu-id="40654-204">Example 11: Get information about child jobs</span></span>

<span data-ttu-id="40654-205">Este exemplo mostra o efeito de usar os parâmetros **IncludeChildJob** e **ChildJobState** do `Get-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="40654-205">This example shows the effect of using the **IncludeChildJob** and **ChildJobState** parameters of the `Get-Job` cmdlet.</span></span>

<span data-ttu-id="40654-206">O primeiro comando obtém os trabalhos presentes na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="40654-206">The first command gets the jobs in the current session.</span></span> <span data-ttu-id="40654-207">A saída inclui um trabalho em segundo plano, um trabalho remoto e várias instâncias de um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="40654-207">The output includes a background job, a remote job and several instances of a scheduled job.</span></span> <span data-ttu-id="40654-208">O trabalho remoto, Trabalho4, parece ter falhado.</span><span class="sxs-lookup"><span data-stu-id="40654-208">The remote job, Job4, appears to have failed.</span></span>
<span data-ttu-id="40654-209">O segundo comando usa o parâmetro **IncludeChildJob** de `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="40654-209">The second command uses the **IncludeChildJob** parameter of `Get-Job`.</span></span> <span data-ttu-id="40654-210">A saída adiciona os trabalhos filho de todos os trabalhos que têm trabalhos filho. Nesse caso, a saída revisada mostra que apenas o trabalho filho Job5 de Job4 falhou.</span><span class="sxs-lookup"><span data-stu-id="40654-210">The output adds the child jobs of all jobs that have child jobs.In this case, the revised output shows that only the Job5 child job of Job4 failed.</span></span> <span data-ttu-id="40654-211">O terceiro comando usa o parâmetro **ChildJobState** com um valor de Failed. a saída inclui todos os trabalhos pai e somente os trabalhos filho que falharam.</span><span class="sxs-lookup"><span data-stu-id="40654-211">The third command uses the **ChildJobState** parameter with a value of Failed.The output includes all parent jobs and only the child jobs that failed.</span></span> <span data-ttu-id="40654-212">O quinto comando usa a propriedade **JobStateInfo** de trabalhos e sua propriedade **Reason** para descobrir por que Job5 falhou.</span><span class="sxs-lookup"><span data-stu-id="40654-212">The fifth command uses the **JobStateInfo** property of jobs and its **Reason** property to discover why Job5 failed.</span></span>

```
PS C:\> Get-Job
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost            .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02   .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

PS C:\> Get-Job -IncludeChildJob
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost           .\Get-Archive.ps1
3      Job3                            Completed     True            localhost           .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02  .\Get-Archive.ps1
5      Job5                            Failed        False           Server01            .\Get-Archive.ps1
6      Job6                            Completed     True            Server02            .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

PS C:\> Get-Job -Name Job4 -ChildJobState Failed
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost           .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02  .\Get-Archive.ps1
5      Job5                            Failed        False           Server01            .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

PS C:\> (Get-Job -Name Job5).JobStateInfo.Reason
Connecting to remote server Server01 failed with the following error message:
Access is denied.
```

<span data-ttu-id="40654-213">Para obter mais informações, consulte o tópico da ajuda [about_Remote_Troubleshooting](./about/about_Remote_Troubleshooting.md) .</span><span class="sxs-lookup"><span data-stu-id="40654-213">For more information, see the [about_Remote_Troubleshooting](./about/about_Remote_Troubleshooting.md) Help topic.</span></span>

## <span data-ttu-id="40654-214">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="40654-214">PARAMETERS</span></span>

### <span data-ttu-id="40654-215">-Depois de</span><span class="sxs-lookup"><span data-stu-id="40654-215">-After</span></span>

<span data-ttu-id="40654-216">Obtém os trabalhos concluídos após a data e hora especificadas.</span><span class="sxs-lookup"><span data-stu-id="40654-216">Gets completed jobs that ended after the specified date and time.</span></span> <span data-ttu-id="40654-217">Insira um objeto **DateTime** , como um retornado pelo `Get-Date` cmdlet ou uma cadeia de caracteres que possa ser convertida em um objeto **DateTime** , como `Dec 1, 2012 2:00 AM` ou `11/06` .</span><span class="sxs-lookup"><span data-stu-id="40654-217">Enter a **DateTime** object, such as one returned by the `Get-Date` cmdlet or a string that can be converted to a **DateTime** object, such as `Dec 1, 2012 2:00 AM` or `11/06`.</span></span>

<span data-ttu-id="40654-218">Este parâmetro funciona somente em tipos de trabalho personalizados, como os de fluxo de trabalho e os trabalhos agendados que têm uma propriedade **EndTime**.</span><span class="sxs-lookup"><span data-stu-id="40654-218">This parameter works only on custom job types, such as workflow jobs and scheduled jobs, that have an **EndTime** property.</span></span> <span data-ttu-id="40654-219">Ele não funciona em trabalhos em segundo plano padrão, como aqueles criados usando o `Start-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="40654-219">It does not work on standard background jobs, such as those created by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="40654-220">Para obter informações sobre o suporte para este parâmetro, consulte o tópico da Ajuda para o tipo de trabalho em questão.</span><span class="sxs-lookup"><span data-stu-id="40654-220">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="40654-221">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="40654-221">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="40654-222">-Antes de</span><span class="sxs-lookup"><span data-stu-id="40654-222">-Before</span></span>

<span data-ttu-id="40654-223">Obtém os trabalhos concluídos antes da data e hora especificadas.</span><span class="sxs-lookup"><span data-stu-id="40654-223">Gets completed jobs that ended before the specified date and time.</span></span> <span data-ttu-id="40654-224">Insira um objeto **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="40654-224">Enter a **DateTime** object.</span></span>

<span data-ttu-id="40654-225">Este parâmetro funciona somente em tipos de trabalho personalizados, como os de fluxo de trabalho e os trabalhos agendados que têm uma propriedade **EndTime**.</span><span class="sxs-lookup"><span data-stu-id="40654-225">This parameter works only on custom job types, such as workflow jobs and scheduled jobs, that have an **EndTime** property.</span></span> <span data-ttu-id="40654-226">Ele não funciona em trabalhos em segundo plano padrão, como aqueles criados usando o `Start-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="40654-226">It does not work on standard background jobs, such as those created by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="40654-227">Para obter informações sobre o suporte para este parâmetro, consulte o tópico da Ajuda para o tipo de trabalho em questão.</span><span class="sxs-lookup"><span data-stu-id="40654-227">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="40654-228">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="40654-228">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="40654-229">-ChildJobState</span><span class="sxs-lookup"><span data-stu-id="40654-229">-ChildJobState</span></span>

<span data-ttu-id="40654-230">Obtém somente os trabalhos filhos que apresentam o estado especificado.</span><span class="sxs-lookup"><span data-stu-id="40654-230">Gets only the child jobs that have the specified state.</span></span> <span data-ttu-id="40654-231">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="40654-231">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="40654-232">NotStarted</span><span class="sxs-lookup"><span data-stu-id="40654-232">NotStarted</span></span>
- <span data-ttu-id="40654-233">Executando</span><span class="sxs-lookup"><span data-stu-id="40654-233">Running</span></span>
- <span data-ttu-id="40654-234">Concluído</span><span class="sxs-lookup"><span data-stu-id="40654-234">Completed</span></span>
- <span data-ttu-id="40654-235">Falhou</span><span class="sxs-lookup"><span data-stu-id="40654-235">Failed</span></span>
- <span data-ttu-id="40654-236">Parado</span><span class="sxs-lookup"><span data-stu-id="40654-236">Stopped</span></span>
- <span data-ttu-id="40654-237">Bloqueado</span><span class="sxs-lookup"><span data-stu-id="40654-237">Blocked</span></span>
- <span data-ttu-id="40654-238">Suspenso</span><span class="sxs-lookup"><span data-stu-id="40654-238">Suspended</span></span>
- <span data-ttu-id="40654-239">Desconectado</span><span class="sxs-lookup"><span data-stu-id="40654-239">Disconnected</span></span>
- <span data-ttu-id="40654-240">Suspensão</span><span class="sxs-lookup"><span data-stu-id="40654-240">Suspending</span></span>
- <span data-ttu-id="40654-241">Parando</span><span class="sxs-lookup"><span data-stu-id="40654-241">Stopping</span></span>

<span data-ttu-id="40654-242">Por padrão, `Get-Job` o não obtém trabalhos filhos.</span><span class="sxs-lookup"><span data-stu-id="40654-242">By default, `Get-Job` does not get child jobs.</span></span> <span data-ttu-id="40654-243">Ao usar o parâmetro **IncludeChildJob** , o `Get-Job` Obtém todos os trabalhos filho.</span><span class="sxs-lookup"><span data-stu-id="40654-243">By using the **IncludeChildJob** parameter, `Get-Job` gets all child jobs.</span></span> <span data-ttu-id="40654-244">Se você usar o parâmetro **ChildJobState** , o parâmetro **IncludeChildJob** não tem nenhum efeito.</span><span class="sxs-lookup"><span data-stu-id="40654-244">If you use the **ChildJobState** parameter, the **IncludeChildJob** parameter has no effect.</span></span>

<span data-ttu-id="40654-245">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="40654-245">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="40654-246">-Command</span><span class="sxs-lookup"><span data-stu-id="40654-246">-Command</span></span>

<span data-ttu-id="40654-247">Especifica uma matriz de comandos como cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="40654-247">Specifies an array of commands as strings.</span></span> <span data-ttu-id="40654-248">Esse cmdlet obtém os trabalhos que incluem os comandos especificados.</span><span class="sxs-lookup"><span data-stu-id="40654-248">This cmdlet gets the jobs that include the specified commands.</span></span> <span data-ttu-id="40654-249">O padrão é obter todos os trabalhos.</span><span class="sxs-lookup"><span data-stu-id="40654-249">The default is all jobs.</span></span> <span data-ttu-id="40654-250">Você pode usar caracteres curinga para especificar um padrão de comando.</span><span class="sxs-lookup"><span data-stu-id="40654-250">You can use wildcard characters to specify a command pattern.</span></span>

```yaml
Type: System.String[]
Parameter Sets: CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="40654-251">-Filter</span><span class="sxs-lookup"><span data-stu-id="40654-251">-Filter</span></span>

<span data-ttu-id="40654-252">Especifica uma tabela de hash de condições.</span><span class="sxs-lookup"><span data-stu-id="40654-252">Specifies a hash table of conditions.</span></span> <span data-ttu-id="40654-253">Esse cmdlet obtém trabalhos que atendem a todas as condições.</span><span class="sxs-lookup"><span data-stu-id="40654-253">This cmdlet gets jobs that satisfy all of the conditions.</span></span>
<span data-ttu-id="40654-254">Insira uma tabela de hash na qual as chaves são propriedades do trabalho e os valores são valores de propriedade do trabalho.</span><span class="sxs-lookup"><span data-stu-id="40654-254">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="40654-255">Este parâmetro funciona somente em tipos de trabalho personalizados, como os de fluxo de trabalho e os trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="40654-255">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span> <span data-ttu-id="40654-256">Ele não funciona em trabalhos em segundo plano padrão, como aqueles criados usando o `Start-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="40654-256">It does not work on standard background jobs, such as those created by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="40654-257">Para obter informações sobre o suporte para este parâmetro, consulte o tópico da Ajuda para o tipo de trabalho em questão.</span><span class="sxs-lookup"><span data-stu-id="40654-257">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="40654-258">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="40654-258">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: FilterParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="40654-259">-HasMoreData</span><span class="sxs-lookup"><span data-stu-id="40654-259">-HasMoreData</span></span>

<span data-ttu-id="40654-260">Indica se este cmdlet obtém apenas os trabalhos que têm o valor da propriedade **HasMoreData** especificado.</span><span class="sxs-lookup"><span data-stu-id="40654-260">Indicates whether this cmdlet gets only jobs that have the specified **HasMoreData** property value.</span></span>
<span data-ttu-id="40654-261">A propriedade **HasMoreData** indica se todos os resultados do trabalho foram recebidos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="40654-261">The **HasMoreData** property indicates whether all job results have been received in the current session.</span></span> <span data-ttu-id="40654-262">Para obter trabalhos que têm mais resultados, especifique um valor de `$True` .</span><span class="sxs-lookup"><span data-stu-id="40654-262">To get jobs that have more results, specify a value of `$True`.</span></span> <span data-ttu-id="40654-263">Para obter trabalhos que não têm mais resultados, especifique um valor de `$False` .</span><span class="sxs-lookup"><span data-stu-id="40654-263">To get jobs that do not have more results, specify a value of `$False`.</span></span>

<span data-ttu-id="40654-264">Para obter os resultados de um trabalho, use o `Receive-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="40654-264">To get the results of a job, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="40654-265">Quando você usa o `Receive-Job` cmdlet, ele exclui de seu armazenamento específico da sessão na memória, os resultados retornados por ele.</span><span class="sxs-lookup"><span data-stu-id="40654-265">When you use the `Receive-Job` cmdlet, it deletes from its in-memory, session-specific storage the results that it returned.</span></span> <span data-ttu-id="40654-266">Quando ele retorna todos os resultados do trabalho na sessão atual, ele define o valor da propriedade **HasMoreData** do trabalho como `$False` ) para indicar que ele não tem mais resultados para o trabalho na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="40654-266">When it has returned all results of the job in the current session, it sets the value of the **HasMoreData** property of the job to `$False`) to indicate that it has no more results for the job in the current session.</span></span> <span data-ttu-id="40654-267">Use o parâmetro **Keep** de `Receive-Job` para evitar `Receive-Job` a exclusão de resultados e a alteração do valor da propriedade **HasMoreData** .</span><span class="sxs-lookup"><span data-stu-id="40654-267">Use the **Keep** parameter of `Receive-Job` to prevent `Receive-Job` from deleting results and changing the value of the **HasMoreData** property.</span></span>
<span data-ttu-id="40654-268">Para obter mais informações, digite `Get-Help Receive-Job`.</span><span class="sxs-lookup"><span data-stu-id="40654-268">For more information, type `Get-Help Receive-Job`.</span></span>

<span data-ttu-id="40654-269">A propriedade **HasMoreData** é específica para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="40654-269">The **HasMoreData** property is specific to the current session.</span></span> <span data-ttu-id="40654-270">Se os resultados de um tipo de trabalho personalizado forem salvos fora da sessão, como o tipo de trabalho agendado, que salva os resultados do trabalho no disco, você poderá usar o `Receive-Job` cmdlet em uma sessão diferente para obter os resultados do trabalho novamente, mesmo que o valor de **HasMoreData** seja `$False` .</span><span class="sxs-lookup"><span data-stu-id="40654-270">If results for a custom job type are saved outside of the session, such as the scheduled job type, which saves job results on disk, you can use the `Receive-Job` cmdlet in a different session to get the job results again, even if the value of **HasMoreData** is `$False`.</span></span> <span data-ttu-id="40654-271">Para obter mais informações, consulte os tópicos da ajuda para o tipo de trabalho personalizado.</span><span class="sxs-lookup"><span data-stu-id="40654-271">For more information, see the help topics for the custom job type.</span></span>

<span data-ttu-id="40654-272">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="40654-272">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Boolean
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="40654-273">-Id</span><span class="sxs-lookup"><span data-stu-id="40654-273">-Id</span></span>

<span data-ttu-id="40654-274">Especifica uma matriz de IDs de trabalhos que esse cmdlet obtém.</span><span class="sxs-lookup"><span data-stu-id="40654-274">Specifies an array of IDs of jobs that this cmdlet gets.</span></span>

<span data-ttu-id="40654-275">A ID é um inteiro que identifica exclusivamente o trabalho na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="40654-275">The ID is an integer that uniquely identifies the job in the current session.</span></span> <span data-ttu-id="40654-276">É mais fácil lembrar e digitar do que a ID da instância, mas só é exclusiva na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="40654-276">It is easier to remember and to type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="40654-277">Você pode digitar uma ou mais IDs separadas por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="40654-277">You can type one or more IDs separated by commas.</span></span> <span data-ttu-id="40654-278">Para localizar a ID de um trabalho, digite `Get-Job` sem parâmetros.</span><span class="sxs-lookup"><span data-stu-id="40654-278">To find the ID of a job, type `Get-Job` without parameters.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="40654-279">-IncludeChildJob</span><span class="sxs-lookup"><span data-stu-id="40654-279">-IncludeChildJob</span></span>

<span data-ttu-id="40654-280">Indica que esse cmdlet retorna trabalhos filho, além de trabalhos pai.</span><span class="sxs-lookup"><span data-stu-id="40654-280">Indicates that this cmdlet returns child jobs, in addition to parent jobs.</span></span>

<span data-ttu-id="40654-281">Esse parâmetro é especialmente útil para a investigação de trabalhos de fluxo de trabalho, para os quais `Get-Job` retorna um trabalho pai do contêiner e falhas de trabalhos, porque o motivo da falha é salvo em uma propriedade do trabalho filho.</span><span class="sxs-lookup"><span data-stu-id="40654-281">This parameter is especially useful for investigating workflow jobs, for which `Get-Job` returns a container parent job, and job failures, because the reason for the failure is saved in a property of the child job.</span></span>

<span data-ttu-id="40654-282">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="40654-282">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="40654-283">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="40654-283">-InstanceId</span></span>

<span data-ttu-id="40654-284">Especifica uma matriz de IDs de instância dos trabalhos que esse cmdlet obtém.</span><span class="sxs-lookup"><span data-stu-id="40654-284">Specifies an array of instance IDs of jobs that this cmdlet gets.</span></span> <span data-ttu-id="40654-285">O padrão é obter todos os trabalhos.</span><span class="sxs-lookup"><span data-stu-id="40654-285">The default is all jobs.</span></span>

<span data-ttu-id="40654-286">Uma ID de instância é um GUID que identifica exclusivamente o trabalho no computador.</span><span class="sxs-lookup"><span data-stu-id="40654-286">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span> <span data-ttu-id="40654-287">Para localizar a ID de instância de um trabalho, use `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="40654-287">To find the instance ID of a job, use `Get-Job`.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="40654-288">-Name</span><span class="sxs-lookup"><span data-stu-id="40654-288">-Name</span></span>

<span data-ttu-id="40654-289">Especifica uma matriz de nomes amigáveis de instância dos trabalhos que esse cmdlet obtém.</span><span class="sxs-lookup"><span data-stu-id="40654-289">Specifies an array of instance friendly names of jobs that this cmdlet gets.</span></span> <span data-ttu-id="40654-290">Insira um nome de trabalho, ou então use caracteres curinga para inserir um padrão de nome de trabalho.</span><span class="sxs-lookup"><span data-stu-id="40654-290">Enter a job name, or use wildcard characters to enter a job name pattern.</span></span> <span data-ttu-id="40654-291">Por padrão, o `Get-Job` Obtém todos os trabalhos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="40654-291">By default, `Get-Job` gets all jobs in the current session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="40654-292">-Mais recente</span><span class="sxs-lookup"><span data-stu-id="40654-292">-Newest</span></span>

<span data-ttu-id="40654-293">Especifica um número de trabalhos a serem obtidos.</span><span class="sxs-lookup"><span data-stu-id="40654-293">Specifies a number of jobs to get.</span></span> <span data-ttu-id="40654-294">Esse cmdlet obtém os trabalhos que foram encerrados mais recentemente.</span><span class="sxs-lookup"><span data-stu-id="40654-294">This cmdlet gets the jobs that ended most recently.</span></span>

<span data-ttu-id="40654-295">O parâmetro **Newest** não classifica nem retorna os trabalhos mais recentes classificados segundo o horário de término.</span><span class="sxs-lookup"><span data-stu-id="40654-295">The **Newest** parameter does not sort or return the newest jobs in end-time order.</span></span> <span data-ttu-id="40654-296">Para classificar a saída, use o `Sort-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="40654-296">To sort the output, use the `Sort-Object` cmdlet.</span></span>

<span data-ttu-id="40654-297">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="40654-297">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="40654-298">-Estado</span><span class="sxs-lookup"><span data-stu-id="40654-298">-State</span></span>

<span data-ttu-id="40654-299">Especifica um estado de trabalho.</span><span class="sxs-lookup"><span data-stu-id="40654-299">Specifies a job state.</span></span> <span data-ttu-id="40654-300">Esse cmdlet obtém apenas os trabalhos no estado especificado.</span><span class="sxs-lookup"><span data-stu-id="40654-300">This cmdlet gets only jobs in the specified state.</span></span> <span data-ttu-id="40654-301">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="40654-301">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="40654-302">NotStarted</span><span class="sxs-lookup"><span data-stu-id="40654-302">NotStarted</span></span>
- <span data-ttu-id="40654-303">Executando</span><span class="sxs-lookup"><span data-stu-id="40654-303">Running</span></span>
- <span data-ttu-id="40654-304">Concluído</span><span class="sxs-lookup"><span data-stu-id="40654-304">Completed</span></span>
- <span data-ttu-id="40654-305">Falhou</span><span class="sxs-lookup"><span data-stu-id="40654-305">Failed</span></span>
- <span data-ttu-id="40654-306">Parado</span><span class="sxs-lookup"><span data-stu-id="40654-306">Stopped</span></span>
- <span data-ttu-id="40654-307">Bloqueado</span><span class="sxs-lookup"><span data-stu-id="40654-307">Blocked</span></span>
- <span data-ttu-id="40654-308">Suspenso</span><span class="sxs-lookup"><span data-stu-id="40654-308">Suspended</span></span>
- <span data-ttu-id="40654-309">Desconectado</span><span class="sxs-lookup"><span data-stu-id="40654-309">Disconnected</span></span>
- <span data-ttu-id="40654-310">Suspensão</span><span class="sxs-lookup"><span data-stu-id="40654-310">Suspending</span></span>
- <span data-ttu-id="40654-311">Parando</span><span class="sxs-lookup"><span data-stu-id="40654-311">Stopping</span></span>

<span data-ttu-id="40654-312">Por padrão, `Get-Job` o Obtém todos os trabalhos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="40654-312">By default, `Get-Job` gets all the jobs in the current session.</span></span>

<span data-ttu-id="40654-313">Para obter mais informações sobre os Estados de trabalho, consulte [Enumeração JobState](/dotnet/api/system.management.automation.jobstate).</span><span class="sxs-lookup"><span data-stu-id="40654-313">For more information about job states, see [JobState Enumeration](/dotnet/api/system.management.automation.jobstate).</span></span>

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="40654-314">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="40654-314">CommonParameters</span></span>

<span data-ttu-id="40654-315">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="40654-315">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="40654-316">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="40654-316">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="40654-317">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="40654-317">INPUTS</span></span>

### <span data-ttu-id="40654-318">Nenhum</span><span class="sxs-lookup"><span data-stu-id="40654-318">None</span></span>

<span data-ttu-id="40654-319">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="40654-319">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="40654-320">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="40654-320">OUTPUTS</span></span>

### <span data-ttu-id="40654-321">System. Management. Automation. RemotingJob</span><span class="sxs-lookup"><span data-stu-id="40654-321">System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="40654-322">Esse cmdlet retorna objetos que representam os trabalhos na sessão.</span><span class="sxs-lookup"><span data-stu-id="40654-322">This cmdlet returns objects that represent the jobs in the session.</span></span>

## <span data-ttu-id="40654-323">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="40654-323">NOTES</span></span>

<span data-ttu-id="40654-324">A propriedade **PSJobTypeName** dos trabalhos indica o tipo do trabalho em questão.</span><span class="sxs-lookup"><span data-stu-id="40654-324">The **PSJobTypeName** property of jobs indicates the job type of the job.</span></span> <span data-ttu-id="40654-325">O valor da propriedade é determinado pelo autor do tipo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="40654-325">The property value is determined by the job type author.</span></span> <span data-ttu-id="40654-326">A lista a seguir mostra os tipos de trabalho comuns.</span><span class="sxs-lookup"><span data-stu-id="40654-326">The following list shows common job types.</span></span>

- <span data-ttu-id="40654-327">**BackgroundJob**.</span><span class="sxs-lookup"><span data-stu-id="40654-327">**BackgroundJob**.</span></span> <span data-ttu-id="40654-328">Trabalho local iniciado usando `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="40654-328">Local job started by using `Start-Job`.</span></span>
- <span data-ttu-id="40654-329">**RemoteJob**.</span><span class="sxs-lookup"><span data-stu-id="40654-329">**RemoteJob**.</span></span> <span data-ttu-id="40654-330">Trabalho iniciado em uma **PSSession** usando o parâmetro **AsJob** do `Invoke-Command` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="40654-330">Job started in a **PSSession** by using the **AsJob** parameter of the `Invoke-Command` cmdlet.</span></span>
- <span data-ttu-id="40654-331">**PSWorkflowJob**.</span><span class="sxs-lookup"><span data-stu-id="40654-331">**PSWorkflowJob**.</span></span> <span data-ttu-id="40654-332">Trabalho iniciado usando o parâmetro comum **AsJob** dos fluxos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="40654-332">Job started by using the **AsJob** common parameter of workflows.</span></span>

## <span data-ttu-id="40654-333">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="40654-333">RELATED LINKS</span></span>

[<span data-ttu-id="40654-334">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="40654-334">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="40654-335">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="40654-335">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="40654-336">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="40654-336">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="40654-337">Start-Job</span><span class="sxs-lookup"><span data-stu-id="40654-337">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="40654-338">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="40654-338">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="40654-339">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="40654-339">Wait-Job</span></span>](Wait-Job.md)

[<span data-ttu-id="40654-340">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="40654-340">about_Jobs</span></span>](About/about_Jobs.md)

[<span data-ttu-id="40654-341">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="40654-341">about_Job_Details</span></span>](About/about_Job_Details.md)

[<span data-ttu-id="40654-342">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="40654-342">about_Remote_Jobs</span></span>](About/about_Remote_Jobs.md)
