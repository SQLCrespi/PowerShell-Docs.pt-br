---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Job
ms.openlocfilehash: 0b9c76ca1e26adaa244473366c2eabdaaa28452c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193324"
---
# <span data-ttu-id="7826c-103">Get-Job</span><span class="sxs-lookup"><span data-stu-id="7826c-103">Get-Job</span></span>

## <span data-ttu-id="7826c-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="7826c-104">SYNOPSIS</span></span>
<span data-ttu-id="7826c-105">Obtém trabalhos em segundo plano do PowerShell que estão em execução na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="7826c-105">Gets PowerShell background jobs that are running in the current session.</span></span>

## <span data-ttu-id="7826c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7826c-106">SYNTAX</span></span>

### <span data-ttu-id="7826c-107">SessionIdParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="7826c-107">SessionIdParameterSet (Default)</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [[-Id] <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="7826c-108">CommandParameterSet</span><span class="sxs-lookup"><span data-stu-id="7826c-108">CommandParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Command <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="7826c-109">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="7826c-109">InstanceIdParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="7826c-110">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="7826c-110">NameParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="7826c-111">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="7826c-111">StateParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-State] <JobState> [<CommonParameters>]
```

### <span data-ttu-id="7826c-112">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="7826c-112">FilterParameterSet</span></span>

```
Get-Job [-Filter] <Hashtable> [<CommonParameters>]
```

## <span data-ttu-id="7826c-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7826c-113">DESCRIPTION</span></span>

<span data-ttu-id="7826c-114">O cmdlet **Get-Job** obtém os objetos que representam os trabalhos em segundo plano que foram iniciados na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="7826c-114">The **Get-Job** cmdlet gets objects that represent the background jobs that were started in the current session.</span></span>
<span data-ttu-id="7826c-115">Você pode usar **Get-Job** para obter trabalhos que foram iniciados usando o cmdlet Start-Job ou usando o parâmetro *AsJob* de qualquer cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7826c-115">You can use **Get-Job** to get jobs that were started by using the Start-Job cmdlet, or by using the *AsJob* parameter of any cmdlet.</span></span>

<span data-ttu-id="7826c-116">Sem parâmetros, um comando **Get-Job** Obtém todos os trabalhos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="7826c-116">Without parameters, a **Get-Job** command gets all jobs in the current session.</span></span>
<span data-ttu-id="7826c-117">Você pode usar os parâmetros de **Get-Job** para obter trabalhos específicos.</span><span class="sxs-lookup"><span data-stu-id="7826c-117">You can use the parameters of **Get-Job** to get particular jobs.</span></span>

<span data-ttu-id="7826c-118">O objeto de trabalho que o cmdlet **Get-Job** retorna contém informações úteis sobre o trabalho, mas não contém os resultados deste.</span><span class="sxs-lookup"><span data-stu-id="7826c-118">The job object that **Get-Job** returns contains useful information about the job, but it does not contain the job results.</span></span>
<span data-ttu-id="7826c-119">Para obter os resultados, use o cmdlet Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="7826c-119">To get the results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="7826c-120">Um trabalho em segundo plano do Windows PowerShell é um comando que é executado em segundo plano sem interagir com a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="7826c-120">A Windows PowerShell background job is a command that runs in the background without interacting with the current session.</span></span>
<span data-ttu-id="7826c-121">Normalmente, você usa um trabalho em segundo plano para executar um comando complexo que leva muito tempo para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="7826c-121">Typically, you use a background job to run a complex command that takes a long time to finish.</span></span>
<span data-ttu-id="7826c-122">Para obter mais informações sobre trabalhos em segundo plano no Windows PowerShell, consulte about_Jobs.</span><span class="sxs-lookup"><span data-stu-id="7826c-122">For more information about background jobs in Windows PowerShell, see about_Jobs.</span></span>

<span data-ttu-id="7826c-123">A partir do Windows PowerShell 3.0, o cmdlet **Get-Job** também obtém os tipos de trabalho personalizados, como trabalhos do fluxo de trabalho e instâncias dos trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="7826c-123">Beginning in Windows PowerShell 3.0, the **Get-Job** cmdlet also gets custom job types, such as workflow jobs and instances of scheduled jobs.</span></span>
<span data-ttu-id="7826c-124">Para localizar o tipo de um trabalho, use a propriedade **PSJobTypeName** do trabalho em questão.</span><span class="sxs-lookup"><span data-stu-id="7826c-124">To find the job type of a job, use the **PSJobTypeName** property of the job.</span></span>

<span data-ttu-id="7826c-125">Para habilitar o **Get-Job** para obter um tipo de trabalho personalizado, importe o módulo que dá suporte ao tipo de trabalho personalizado na sessão antes de executar um comando **Get-Job** , seja usando o cmdlet Import-Module ou usando ou obtendo um cmdlet no módulo.</span><span class="sxs-lookup"><span data-stu-id="7826c-125">To enable **Get-Job** to get a custom job type, import the module that supports the custom job type into the session before you run a **Get-Job** command, either by using the Import-Module cmdlet or by using or getting a cmdlet in the module.</span></span>
<span data-ttu-id="7826c-126">Para obter informações sobre um tipo específico de trabalho personalizado, consulte a documentação do recurso de tipo de trabalho personalizado.</span><span class="sxs-lookup"><span data-stu-id="7826c-126">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="7826c-127">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="7826c-127">EXAMPLES</span></span>

### <span data-ttu-id="7826c-128">Exemplo 1: obter todos os trabalhos em segundo plano iniciados na sessão atual</span><span class="sxs-lookup"><span data-stu-id="7826c-128">Example 1: Get all background jobs started in the current session</span></span>

```
PS C:\> Get-Job
```

<span data-ttu-id="7826c-129">Esse comando obtém todos os trabalhos em segundo plano iniciados na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="7826c-129">This command gets all background jobs started in the current session.</span></span>
<span data-ttu-id="7826c-130">Ele não inclui trabalhos criados em outras sessões, mesmo se os trabalhos forem executados no computador local.</span><span class="sxs-lookup"><span data-stu-id="7826c-130">It does not include jobs created in other sessions, even if the jobs run on the local computer.</span></span>

### <span data-ttu-id="7826c-131">Exemplo 2: parar um trabalho usando uma ID de instância</span><span class="sxs-lookup"><span data-stu-id="7826c-131">Example 2: Stop a job by using an instance ID</span></span>

```
The first command uses the **Get-Job** cmdlet to get a job. It uses the *Name* parameter to identify the job. The command stores the job object that **Get-Job** returns in the $j variable. In this example, there is only one job with the specified name.
PS C:\> $j = Get-Job -Name Job1

The second command gets the **InstanceId** property of the object in the $j variable and stores it in the $ID variable.
PS C:\> $ID = $j.InstanceID

The third command displays the value of the $ID variable.
PS C:\> $ID

Guid
----
03c3232e-1d23-453b-a6f4-ed73c9e29d55

The fourth command uses Stop-Job cmdlet to stop the job. It uses the *InstanceId* parameter to identify the job and $ID variable to represent the instance ID of the job.
PS C:\> Stop-Job -InstanceId $ID
```

<span data-ttu-id="7826c-132">Esses comandos mostram como obter o identificador de instância de um trabalho e, em seguida, usá-lo para interromper esse trabalho.</span><span class="sxs-lookup"><span data-stu-id="7826c-132">These commands show how to get the instance ID of a job and then use it to stop a job.</span></span>
<span data-ttu-id="7826c-133">Ao contrário do nome de um determinado trabalho, que não é exclusivo, o identificador da instância é.</span><span class="sxs-lookup"><span data-stu-id="7826c-133">Unlike the name of a job, which is not unique, the instance ID is unique.</span></span>

### <span data-ttu-id="7826c-134">Exemplo 3: obter trabalhos que incluem um comando específico</span><span class="sxs-lookup"><span data-stu-id="7826c-134">Example 3: Get jobs that include a specific command</span></span>

```
PS C:\> Get-Job -Command "*get-process*"
```

<span data-ttu-id="7826c-135">Esse comando obtém os trabalhos no sistema que incluem um comando Get-Process.</span><span class="sxs-lookup"><span data-stu-id="7826c-135">This command gets the jobs on the system that include a Get-Process command.</span></span>
<span data-ttu-id="7826c-136">O comando usa o parâmetro *Command* do **Get-Job** para limitar os trabalhos recuperados.</span><span class="sxs-lookup"><span data-stu-id="7826c-136">The command uses the *Command* parameter of **Get-Job** to limit the jobs retrieved.</span></span>
<span data-ttu-id="7826c-137">O comando usa caracteres curinga (\*) para obter trabalhos que incluem um comando **Get-Process** em qualquer lugar na cadeia de caracteres de comando.</span><span class="sxs-lookup"><span data-stu-id="7826c-137">The command uses wildcard characters (\*) to get jobs that include a **Get-Process** command anywhere in the command string.</span></span>

### <span data-ttu-id="7826c-138">Exemplo 4: obter trabalhos que incluem um comando específico usando o pipeline</span><span class="sxs-lookup"><span data-stu-id="7826c-138">Example 4: Get jobs that include a specific command by using the pipeline</span></span>

```
PS C:\> "*get-process*" | Get-Job
```

<span data-ttu-id="7826c-139">Como o comando no exemplo anterior, esse comando obtém os trabalhos no sistema que incluem um comando **Get-Process** .</span><span class="sxs-lookup"><span data-stu-id="7826c-139">Like the command in the previous example, this command gets the jobs on the system that include a **Get-Process** command.</span></span>
<span data-ttu-id="7826c-140">O comando usa um operador de pipeline (|) para enviar uma cadeia de caracteres, entre aspas, para o cmdlet **Get-Job** .</span><span class="sxs-lookup"><span data-stu-id="7826c-140">The command uses a pipeline operator (|) to send a string, in quotation marks, to the **Get-Job** cmdlet.</span></span>
<span data-ttu-id="7826c-141">Ele é o equivalente do comando anterior.</span><span class="sxs-lookup"><span data-stu-id="7826c-141">It is the equivalent of the previous command.</span></span>

### <span data-ttu-id="7826c-142">Exemplo 5: obter trabalhos que não foram iniciados</span><span class="sxs-lookup"><span data-stu-id="7826c-142">Example 5: Get jobs that have not been started</span></span>

```
PS C:\> Get-Job -State NotStarted
```

<span data-ttu-id="7826c-143">Este comando obtém apenas os trabalhos que foram criados, mas ainda não foi iniciados.</span><span class="sxs-lookup"><span data-stu-id="7826c-143">This command gets only those jobs that have been created but have not yet been started.</span></span>
<span data-ttu-id="7826c-144">Isso inclui trabalhos agendados para execução no futuro e aqueles ainda não foram agendados.</span><span class="sxs-lookup"><span data-stu-id="7826c-144">This includes jobs that are scheduled to run in the future and those not yet scheduled.</span></span>

### <span data-ttu-id="7826c-145">Exemplo 6: obter trabalhos que não foram atribuídos a um nome</span><span class="sxs-lookup"><span data-stu-id="7826c-145">Example 6: Get jobs that have not been assigned a name</span></span>

```
PS C:\> Get-Job -Name Job*
```

<span data-ttu-id="7826c-146">Esse comando obtém todos os trabalhos que têm nomes de trabalho que começam com o trabalho.</span><span class="sxs-lookup"><span data-stu-id="7826c-146">This command gets all jobs that have job names that begin with job.</span></span>
<span data-ttu-id="7826c-147">Como \<number\> o trabalho é o nome padrão de um trabalho, esse comando obtém todos os trabalhos que não têm um nome explicitamente atribuído.</span><span class="sxs-lookup"><span data-stu-id="7826c-147">Because job\<number\> is the default name for a job, this command gets all jobs that do not have an explicitly assigned name.</span></span>

### <span data-ttu-id="7826c-148">Exemplo 7: usar um objeto de trabalho para representar o trabalho em um comando</span><span class="sxs-lookup"><span data-stu-id="7826c-148">Example 7: Use a job object to represent the job in a command</span></span>

```
The first command uses the **Start-Job** cmdlet to start a background job that runs a **Get-Process** command on the local computer. The command uses the *Name* parameter of **Start-Job** to assign a friendly name to the job.
PS C:\> Start-Job -ScriptBlock {Get-Process} -Name MyJob

The second command uses Get-Job to get the job. It uses the *Name* parameter of **Get-Job** to identify the job. The command saves the resulting job object in the $j variable.
PS C:\> $j = Get-Job -Name MyJob

The third command displays the value of the job object in the $j variable. The value of the **State** property shows that the job is completed. The value of the **HasMoreData** property shows that there are results available from the job that have not yet been retrieved.
PS C:\> $j
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
6      MyJob           BackgroundJob   Completed     True            localhost            Get-Process

The fourth command uses the **Receive-Job** cmdlet to get the results of the job. It uses the job object in the $j variable to represent the job. You can also use a pipeline operator to send a job object to **Receive-Job**.
PS C:\> Receive-Job -Job $j
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    124       4    13572      12080    59            1140 audiodg
    783      16    11428      13636   100             548 CcmExec
     96       4     4252       3764    59            3856 ccmsetup
...
```

<span data-ttu-id="7826c-149">Este exemplo mostra como usar o **Get-Job** para obter um objeto de trabalho e, em seguida, ele mostra como usar o objeto de trabalho para representar esse trabalho em um comando.</span><span class="sxs-lookup"><span data-stu-id="7826c-149">This example shows how to use **Get-Job** to get a job object, and then it shows how to use the job object to represent the job in a command.</span></span>

### <span data-ttu-id="7826c-150">Exemplo 8: obter todos os trabalhos, incluindo trabalhos iniciados por um método diferente</span><span class="sxs-lookup"><span data-stu-id="7826c-150">Example 8: Get all jobs including jobs started by a different method</span></span>

```
The first command uses the **Start-Job** cmdlet to start a job on the local computer.
PS C:\> Start-Job -ScriptBlock {Get-EventLog System}

The second command uses the *AsJob* parameter of the **Invoke-Command** cmdlet to start a job on the S1 computer. Even though the commands in the job run on the remote computer, the job object is created on the local computer, so you use local commands to manage the job.
PS C:\> Invoke-Command -ComputerName S1 -ScriptBlock {Get-EventLog System} -AsJob

The third command uses the **Invoke-Command** cmdlet to run a **Start-Job** command on the S2 computer. By using this method, the job object is created on the remote computer, so you use remote commands to manage the job.
PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}

The fourth command uses **Get-Job** to get the jobs stored on the local computer. The **PSJobTypeName** property of jobs, introduced in Windows PowerShell 3.0, shows that the local job started by using the **Start-Job** cmdlet is a background job and the job started in a remote session by using the **Invoke-Command** cmdlet is a remote job.
PS C:\> Get-Job
Id     Name       PSJobTypeName   State         HasMoreData     Location        Command
--     ----       -------------   -----         -----------     --------        -------
1      Job1       BackgroundJob   Running       True            localhost       Get-EventLog System
2      Job2       RemoteJob       Running       True            S1              Get-EventLog System

The fifth command uses **Invoke-Command** to run a **Get-Job** command on the S2 computer.The sample output shows the results of the Get-Job command. On the S2 computer, the job appears to be a local job. The computer name is localhost and the job type is a background job.For more information about how to run background jobs on remote computers, see about_Remote_Jobs.
PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Id    Name     PSJobTypeName  State      HasMoreData   Location   Command
--    ----     -------------  -----      -----------   -------    -------
4     Job4     BackgroundJob  Running    True          localhost  Get-Eventlog System
```

<span data-ttu-id="7826c-151">Este exemplo demonstra que o cmdlet **Get-Job** pode obter todos os trabalhos que foram iniciados na sessão atual, mesmo que eles tenham sido iniciados usando métodos diferentes.</span><span class="sxs-lookup"><span data-stu-id="7826c-151">This example demonstrates that the **Get-Job** cmdlet can get all of the jobs that were started in the current session, even if they were started by using different methods.</span></span>

### <span data-ttu-id="7826c-152">Exemplo 9: investigar um trabalho com falha</span><span class="sxs-lookup"><span data-stu-id="7826c-152">Example 9: Investigate a failed job</span></span>

```
The first command uses the **Start-Job** cmdlet to start a job on the local computer. The job object that **Start-Job** returns shows that the job failed. The value of the **State** property is Failed.
PS C:\> Start-Job -ScriptBlock {Get-Process}
Id     Name       PSJobTypeName   State       HasMoreData     Location             Command
--     ----       -------------   -----       -----------     --------             -------
1      Job1       BackgroundJob   Failed      False           localhost            Get-Process

The second command uses the **Get-Job** cmdlet to get the job. The command uses the dot method to get the value of the **JobStateInfo** property of the object. It uses a pipeline operator to send the object in the **JobStateInfo** property to the Format-List cmdlet, which formats all of the properties of the object (*) in a list.The result of the **Format-List** command shows that the value of the **Reason** property of the job is blank.
PS C:\> (Get-Job).JobStateInfo | Format-List -Property *
State  : Failed
Reason :

The third command investigates more. It uses a **Get-Job** command to get the job and then uses a pipeline operator to send the whole job object to the **Format-List** cmdlet, which displays all of the properties of the job in a list.The display of all properties in the job object shows that the job contains a child job named Job2.
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

The fourth command uses **Get-Job** to get the job object that represents the Job2 child job. This is the job in which the command actually ran. It uses the dot method to get the **Reason** property of the **JobStateInfo** property.The result shows that the job failed because of an Access Denied error. In this case, the user forgot to use the Run as administrator option when starting Windows PowerShell.Because background jobs use the remoting features of Windows PowerShell, the computer must be configured for remoting to run a job, even when the job runs on the local computer.For information about requirements for remoting in Windows PowerShell, see about_Remote_Requirements. For troubleshooting tips, see about_Remote_Troubleshooting.
PS C:\> (Get-Job -Name job2).JobStateInfo.Reason
Connecting to remote server using WSManCreateShellEx api failed. The async callback gave the following error message: Access is denied.
```

<span data-ttu-id="7826c-153">Este comando mostra como usar o objeto de trabalho que o **Get-Job** retorna para investigar por que um trabalho falhou.</span><span class="sxs-lookup"><span data-stu-id="7826c-153">This command shows how to use the job object that **Get-Job** returns to investigate why a job failed.</span></span>
<span data-ttu-id="7826c-154">Ele também mostra como obter os trabalhos filhos de cada trabalho.</span><span class="sxs-lookup"><span data-stu-id="7826c-154">It also shows how to get the child jobs of each job.</span></span>

### <span data-ttu-id="7826c-155">Exemplo 10: obter resultados filtrados</span><span class="sxs-lookup"><span data-stu-id="7826c-155">Example 10: Get filtered results</span></span>

```
The first command uses the **Workflow** keyword to create the WFProcess workflow.
PS C:\> Workflow WFProcess {Get-Process}

The second command uses the *AsJob* parameter of the WFProcess workflow to run the workflow as a background job. It uses the *JobName* parameter of the workflow to specify a name for the job, and the *PSPrivateMetadata* parameter of the workflow to specify a custom ID.
PS C:\> WFProcess -AsJob -JobName WFProcessJob -PSPrivateMetadata @{MyCustomId = 92107}

The third command uses the *Filter* parameter of **Get-Job** to get the job by custom ID that was specified in the *PSPrivateMetadata* parameter.
PS C:\> Get-Job -Filter @{MyCustomId = 92107}
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
1      WFProcessJob    Completed     True            localhost            WFProcess
```

<span data-ttu-id="7826c-156">Este exemplo mostra como usar o parâmetro *Filter* para obter uma tarefa de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="7826c-156">This example shows how to use the *Filter* parameter to get a workflow job.</span></span>
<span data-ttu-id="7826c-157">O parâmetro *Filter* , introduzido no Windows PowerShell 3.0, é válido somente em tipos de trabalho personalizados, como tarefas de fluxo de trabalho e trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="7826c-157">The *Filter* parameter, introduced in Windows PowerShell 3.0 is valid only on custom job types, such as workflow jobs and scheduled jobs.</span></span>

### <span data-ttu-id="7826c-158">Exemplo 11: obter informações sobre trabalhos filho</span><span class="sxs-lookup"><span data-stu-id="7826c-158">Example 11: Get information about child jobs</span></span>

```
The first command gets the jobs in the current session. The output includes a background job, a remote job and several instances of a scheduled job. The remote job, Job4, appears to have failed.
PS C:\> Get-Job
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost            .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02   .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

The second command uses the *IncludeChildJob* parameter of **Get-Job**. The output adds the child jobs of all jobs that have child jobs.In this case, the revised output shows that only the Job5 child job of Job4 failed.
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

The third command uses the *ChildJobState* parameter with a value of Failed.The output includes all parent jobs and only the child jobs that failed.
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

The fifth command uses the **JobStateInfo** property of jobs and its **Reason** property to discover why Job5 failed.
PS C:\> (Get-Job -Name Job5).JobStateInfo.Reason
Connecting to remote server Server01 failed with the following error message:
Access is denied.
For more information, see the about_Remote_Troubleshooting Help topic.
```

<span data-ttu-id="7826c-159">Este exemplo mostra o efeito do uso dos parâmetros *IncludeChildJob* e *ChildJobState* do cmdlet **Get-Job** .</span><span class="sxs-lookup"><span data-stu-id="7826c-159">This example shows the effect of using the *IncludeChildJob* and *ChildJobState* parameters of the **Get-Job** cmdlet.</span></span>

## <span data-ttu-id="7826c-160">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7826c-160">PARAMETERS</span></span>

### <span data-ttu-id="7826c-161">-Depois de</span><span class="sxs-lookup"><span data-stu-id="7826c-161">-After</span></span>

<span data-ttu-id="7826c-162">Obtém os trabalhos concluídos após a data e hora especificadas.</span><span class="sxs-lookup"><span data-stu-id="7826c-162">Gets completed jobs that ended after the specified date and time.</span></span>
<span data-ttu-id="7826c-163">Insira um objeto **DateTime** , como um retornado pelo cmdlet Get-Date ou uma cadeia de caracteres que possa ser convertida em um objeto **DateTime** , como `Dec 1, 2012 2:00 AM` ou `11/06` .</span><span class="sxs-lookup"><span data-stu-id="7826c-163">Enter a **DateTime** object, such as one returned by the Get-Date cmdlet or a string that can be converted to a **DateTime** object, such as `Dec 1, 2012 2:00 AM` or `11/06`.</span></span>

<span data-ttu-id="7826c-164">Este parâmetro funciona somente em tipos de trabalho personalizados, como os de fluxo de trabalho e os trabalhos agendados que têm uma propriedade **EndTime** .</span><span class="sxs-lookup"><span data-stu-id="7826c-164">This parameter works only on custom job types, such as workflow jobs and scheduled jobs, that have an **EndTime** property.</span></span>
<span data-ttu-id="7826c-165">Ele não funciona em trabalhos em segundo plano padrão, como aqueles criados usando o cmdlet **Start-Job** .</span><span class="sxs-lookup"><span data-stu-id="7826c-165">It does not work on standard background jobs, such as those created by using the **Start-Job** cmdlet.</span></span>
<span data-ttu-id="7826c-166">Para obter informações sobre o suporte para este parâmetro, consulte o tópico da Ajuda para o tipo de trabalho em questão.</span><span class="sxs-lookup"><span data-stu-id="7826c-166">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="7826c-167">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="7826c-167">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7826c-168">-Antes de</span><span class="sxs-lookup"><span data-stu-id="7826c-168">-Before</span></span>

<span data-ttu-id="7826c-169">Obtém os trabalhos concluídos antes da data e hora especificadas.</span><span class="sxs-lookup"><span data-stu-id="7826c-169">Gets completed jobs that ended before the specified date and time.</span></span>
<span data-ttu-id="7826c-170">Insira um objeto **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="7826c-170">Enter a **DateTime** object.</span></span>

<span data-ttu-id="7826c-171">Este parâmetro funciona somente em tipos de trabalho personalizados, como os de fluxo de trabalho e os trabalhos agendados que têm uma propriedade **EndTime** .</span><span class="sxs-lookup"><span data-stu-id="7826c-171">This parameter works only on custom job types, such as workflow jobs and scheduled jobs, that have an **EndTime** property.</span></span>
<span data-ttu-id="7826c-172">Ele não funciona em trabalhos em segundo plano padrão, como aqueles criados usando o cmdlet **Start-Job** .</span><span class="sxs-lookup"><span data-stu-id="7826c-172">It does not work on standard background jobs, such as those created by using the **Start-Job** cmdlet.</span></span>
<span data-ttu-id="7826c-173">Para obter informações sobre o suporte para este parâmetro, consulte o tópico da Ajuda para o tipo de trabalho em questão.</span><span class="sxs-lookup"><span data-stu-id="7826c-173">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="7826c-174">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="7826c-174">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7826c-175">-ChildJobState</span><span class="sxs-lookup"><span data-stu-id="7826c-175">-ChildJobState</span></span>

<span data-ttu-id="7826c-176">Obtém somente os trabalhos filhos que apresentam o estado especificado.</span><span class="sxs-lookup"><span data-stu-id="7826c-176">Gets only the child jobs that have the specified state.</span></span>
<span data-ttu-id="7826c-177">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="7826c-177">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="7826c-178">NotStarted</span><span class="sxs-lookup"><span data-stu-id="7826c-178">NotStarted</span></span>
- <span data-ttu-id="7826c-179">Executando</span><span class="sxs-lookup"><span data-stu-id="7826c-179">Running</span></span>
- <span data-ttu-id="7826c-180">Concluído</span><span class="sxs-lookup"><span data-stu-id="7826c-180">Completed</span></span>
- <span data-ttu-id="7826c-181">Falhou</span><span class="sxs-lookup"><span data-stu-id="7826c-181">Failed</span></span>
- <span data-ttu-id="7826c-182">Parado</span><span class="sxs-lookup"><span data-stu-id="7826c-182">Stopped</span></span>
- <span data-ttu-id="7826c-183">Bloqueado</span><span class="sxs-lookup"><span data-stu-id="7826c-183">Blocked</span></span>
- <span data-ttu-id="7826c-184">Suspenso</span><span class="sxs-lookup"><span data-stu-id="7826c-184">Suspended</span></span>
- <span data-ttu-id="7826c-185">Desconectado</span><span class="sxs-lookup"><span data-stu-id="7826c-185">Disconnected</span></span>
- <span data-ttu-id="7826c-186">Suspensão</span><span class="sxs-lookup"><span data-stu-id="7826c-186">Suspending</span></span>
- <span data-ttu-id="7826c-187">Parando</span><span class="sxs-lookup"><span data-stu-id="7826c-187">Stopping</span></span>

<span data-ttu-id="7826c-188">Por padrão, o **Get-Job** não obtém nenhum trabalho filho.</span><span class="sxs-lookup"><span data-stu-id="7826c-188">By default, **Get-Job** does not get child jobs.</span></span>
<span data-ttu-id="7826c-189">Usando o parâmetro *IncludeChildJob* , **Get-Job** Obtém todos os trabalhos filho.</span><span class="sxs-lookup"><span data-stu-id="7826c-189">By using the *IncludeChildJob* parameter, **Get-Job** gets all child jobs.</span></span>
<span data-ttu-id="7826c-190">Se você usar o parâmetro *ChildJobState* , o parâmetro *IncludeChildJob* não tem nenhum efeito.</span><span class="sxs-lookup"><span data-stu-id="7826c-190">If you use the *ChildJobState* parameter, the *IncludeChildJob* parameter has no effect.</span></span>

<span data-ttu-id="7826c-191">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="7826c-191">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7826c-192">-Command</span><span class="sxs-lookup"><span data-stu-id="7826c-192">-Command</span></span>

<span data-ttu-id="7826c-193">Especifica uma matriz de comandos como cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7826c-193">Specifies an array of commands as strings.</span></span>
<span data-ttu-id="7826c-194">Esse cmdlet obtém os trabalhos que incluem os comandos especificados.</span><span class="sxs-lookup"><span data-stu-id="7826c-194">This cmdlet gets the jobs that include the specified commands.</span></span>
<span data-ttu-id="7826c-195">O padrão é obter todos os trabalhos.</span><span class="sxs-lookup"><span data-stu-id="7826c-195">The default is all jobs.</span></span>
<span data-ttu-id="7826c-196">Você pode usar caracteres curinga para especificar um padrão de comando.</span><span class="sxs-lookup"><span data-stu-id="7826c-196">You can use wildcard characters to specify a command pattern.</span></span>

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

### <span data-ttu-id="7826c-197">-Filter</span><span class="sxs-lookup"><span data-stu-id="7826c-197">-Filter</span></span>

<span data-ttu-id="7826c-198">Especifica uma tabela de hash de condições.</span><span class="sxs-lookup"><span data-stu-id="7826c-198">Specifies a hash table of conditions.</span></span>
<span data-ttu-id="7826c-199">Esse cmdlet obtém trabalhos que atendem a todas as condições.</span><span class="sxs-lookup"><span data-stu-id="7826c-199">This cmdlet gets jobs that satisfy all of the conditions.</span></span>
<span data-ttu-id="7826c-200">Insira uma tabela de hash na qual as chaves são propriedades do trabalho e os valores são valores de propriedade do trabalho.</span><span class="sxs-lookup"><span data-stu-id="7826c-200">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="7826c-201">Este parâmetro funciona somente em tipos de trabalho personalizados, como os de fluxo de trabalho e os trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="7826c-201">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span>
<span data-ttu-id="7826c-202">Ele não funciona em trabalhos em segundo plano padrão, como aqueles criados usando o cmdlet **Start-Job** .</span><span class="sxs-lookup"><span data-stu-id="7826c-202">It does not work on standard background jobs, such as those created by using the **Start-Job** cmdlet.</span></span>
<span data-ttu-id="7826c-203">Para obter informações sobre o suporte para este parâmetro, consulte o tópico da Ajuda para o tipo de trabalho em questão.</span><span class="sxs-lookup"><span data-stu-id="7826c-203">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="7826c-204">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="7826c-204">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="7826c-205">-HasMoreData</span><span class="sxs-lookup"><span data-stu-id="7826c-205">-HasMoreData</span></span>

<span data-ttu-id="7826c-206">Indica se este cmdlet obtém apenas os trabalhos que têm o valor da propriedade **HasMoreData** especificado.</span><span class="sxs-lookup"><span data-stu-id="7826c-206">Indicates whether this cmdlet gets only jobs that have the specified **HasMoreData** property value.</span></span>
<span data-ttu-id="7826c-207">A propriedade **HasMoreData** indica se todos os resultados do trabalho foram recebidos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="7826c-207">The **HasMoreData** property indicates whether all job results have been received in the current session.</span></span>
<span data-ttu-id="7826c-208">Para obter trabalhos que têm mais resultados, especifique um valor de $True.</span><span class="sxs-lookup"><span data-stu-id="7826c-208">To get jobs that have more results, specify a value of $True.</span></span>
<span data-ttu-id="7826c-209">Para obter trabalhos que não têm mais resultados, especifique um valor de $False.</span><span class="sxs-lookup"><span data-stu-id="7826c-209">To get jobs that do not have more results, specify a value of $False.</span></span>

<span data-ttu-id="7826c-210">Para obter os resultados de um trabalho, use o cmdlet Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="7826c-210">To get the results of a job, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="7826c-211">Quando você usa o cmdlet **Receive-Job** , ele exclui de seu armazenamento específico da sessão na memória, os resultados retornados por ele.</span><span class="sxs-lookup"><span data-stu-id="7826c-211">When you use the **Receive-Job** cmdlet, it deletes from its in-memory, session-specific storage the results that it returned.</span></span>
<span data-ttu-id="7826c-212">Quando ele retorna todos os resultados do trabalho na sessão atual, ele define o valor da propriedade **HasMoreData** do trabalho como $false) para indicar que ele não tem mais resultados para o trabalho na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="7826c-212">When it has returned all results of the job in the current session, it sets the value of the **HasMoreData** property of the job to $False) to indicate that it has no more results for the job in the current session.</span></span>
<span data-ttu-id="7826c-213">Use o parâmetro *Keep* de **Receive-Job** para evitar que o **Receive-Job** exclua resultados ou altere o valor da propriedade **HasMoreData** .</span><span class="sxs-lookup"><span data-stu-id="7826c-213">Use the *Keep* parameter of **Receive-Job** to prevent **Receive-Job** from deleting results and changing the value of the **HasMoreData** property.</span></span>
<span data-ttu-id="7826c-214">Para obter mais informações, digite `Get-Help Receive-Job`.</span><span class="sxs-lookup"><span data-stu-id="7826c-214">For more information, type `Get-Help Receive-Job`.</span></span>

<span data-ttu-id="7826c-215">A propriedade **HasMoreData** é específica para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="7826c-215">The **HasMoreData** property is specific to the current session.</span></span>
<span data-ttu-id="7826c-216">Se os resultados de um tipo de trabalho personalizado forem salvos fora da sessão, como o tipo de trabalho agendado, que salva os resultados do trabalho no disco, você poderá usar o cmdlet **Receive-Job** em uma sessão diferente para obter os resultados do trabalho novamente, mesmo que o valor de **HasMoreData** seja $false.</span><span class="sxs-lookup"><span data-stu-id="7826c-216">If results for a custom job type are saved outside of the session, such as the scheduled job type, which saves job results on disk, you can use the **Receive-Job** cmdlet in a different session to get the job results again, even if the value of **HasMoreData** is $False.</span></span>
<span data-ttu-id="7826c-217">Para obter mais informações, consulte os tópicos da ajuda para o tipo de trabalho personalizado.</span><span class="sxs-lookup"><span data-stu-id="7826c-217">For more information, see the help topics for the custom job type.</span></span>

<span data-ttu-id="7826c-218">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="7826c-218">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Boolean
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7826c-219">-Id</span><span class="sxs-lookup"><span data-stu-id="7826c-219">-Id</span></span>

<span data-ttu-id="7826c-220">Especifica uma matriz de IDs de trabalhos que esse cmdlet obtém.</span><span class="sxs-lookup"><span data-stu-id="7826c-220">Specifies an array of IDs of jobs that this cmdlet gets.</span></span>

<span data-ttu-id="7826c-221">A ID é um inteiro que identifica exclusivamente o trabalho na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="7826c-221">The ID is an integer that uniquely identifies the job in the current session.</span></span>
<span data-ttu-id="7826c-222">É mais fácil lembrar e digitar do que a ID da instância, mas só é exclusiva na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="7826c-222">It is easier to remember and to type than the instance ID, but it is unique only in the current session.</span></span>
<span data-ttu-id="7826c-223">Você pode digitar uma ou mais IDs separadas por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="7826c-223">You can type one or more IDs separated by commas.</span></span>
<span data-ttu-id="7826c-224">Para localizar a ID de um trabalho, digite `Get-Job` sem parâmetros.</span><span class="sxs-lookup"><span data-stu-id="7826c-224">To find the ID of a job, type `Get-Job` without parameters.</span></span>

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

### <span data-ttu-id="7826c-225">-IncludeChildJob</span><span class="sxs-lookup"><span data-stu-id="7826c-225">-IncludeChildJob</span></span>

<span data-ttu-id="7826c-226">Indica que esse cmdlet retorna trabalhos filho, além de trabalhos pai.</span><span class="sxs-lookup"><span data-stu-id="7826c-226">Indicates that this cmdlet returns child jobs, in addition to parent jobs.</span></span>

<span data-ttu-id="7826c-227">Esse parâmetro é especialmente útil para a investigação de trabalhos de fluxo de trabalho, para os quais o **Get-Job** retorna um trabalho pai do contêiner, e falhas de trabalhos, porque o motivo da falha é salvo em uma propriedade do trabalho filho.</span><span class="sxs-lookup"><span data-stu-id="7826c-227">This parameter is especially useful for investigating workflow jobs, for which **Get-Job** returns a container parent job, and job failures, because the reason for the failure is saved in a property of the child job.</span></span>

<span data-ttu-id="7826c-228">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="7826c-228">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7826c-229">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="7826c-229">-InstanceId</span></span>

<span data-ttu-id="7826c-230">Especifica uma matriz de IDs de instância dos trabalhos que esse cmdlet obtém.</span><span class="sxs-lookup"><span data-stu-id="7826c-230">Specifies an array of instance IDs of jobs that this cmdlet gets.</span></span>
<span data-ttu-id="7826c-231">O padrão é obter todos os trabalhos.</span><span class="sxs-lookup"><span data-stu-id="7826c-231">The default is all jobs.</span></span>

<span data-ttu-id="7826c-232">Uma ID de instância é um GUID que identifica exclusivamente o trabalho no computador.</span><span class="sxs-lookup"><span data-stu-id="7826c-232">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span>
<span data-ttu-id="7826c-233">Para localizar o identificador da instância de um trabalho, use o cmdlet **Get-Job** .</span><span class="sxs-lookup"><span data-stu-id="7826c-233">To find the instance ID of a job, use **Get-Job** .</span></span>

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

### <span data-ttu-id="7826c-234">-Name</span><span class="sxs-lookup"><span data-stu-id="7826c-234">-Name</span></span>

<span data-ttu-id="7826c-235">Especifica uma matriz de nomes amigáveis de instância dos trabalhos que esse cmdlet obtém.</span><span class="sxs-lookup"><span data-stu-id="7826c-235">Specifies an array of instance friendly names of jobs that this cmdlet gets.</span></span>
<span data-ttu-id="7826c-236">Insira um nome de trabalho, ou então use caracteres curinga para inserir um padrão de nome de trabalho.</span><span class="sxs-lookup"><span data-stu-id="7826c-236">Enter a job name, or use wildcard characters to enter a job name pattern.</span></span>
<span data-ttu-id="7826c-237">Por padrão, o **Get-Job** obtém todos os trabalhos existentes na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="7826c-237">By default, **Get-Job** gets all jobs in the current session.</span></span>

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

### <span data-ttu-id="7826c-238">-Mais recente</span><span class="sxs-lookup"><span data-stu-id="7826c-238">-Newest</span></span>

<span data-ttu-id="7826c-239">Especifica um número de trabalhos a serem obtidos.</span><span class="sxs-lookup"><span data-stu-id="7826c-239">Specifies a number of jobs to get.</span></span>
<span data-ttu-id="7826c-240">Esse cmdlet obtém os trabalhos que foram encerrados mais recentemente.</span><span class="sxs-lookup"><span data-stu-id="7826c-240">This cmdlet gets the jobs that ended most recently.</span></span>

<span data-ttu-id="7826c-241">O parâmetro *Newest* não classifica nem retorna os trabalhos mais recentes classificados segundo o horário de término.</span><span class="sxs-lookup"><span data-stu-id="7826c-241">The *Newest* parameter does not sort or return the newest jobs in end-time order.</span></span>
<span data-ttu-id="7826c-242">Para classificar a saída, use o cmdlet Sort-Object.</span><span class="sxs-lookup"><span data-stu-id="7826c-242">To sort the output, use the Sort-Object cmdlet.</span></span>

<span data-ttu-id="7826c-243">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="7826c-243">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7826c-244">-Estado</span><span class="sxs-lookup"><span data-stu-id="7826c-244">-State</span></span>

<span data-ttu-id="7826c-245">Especifica um estado de trabalho.</span><span class="sxs-lookup"><span data-stu-id="7826c-245">Specifies a job state.</span></span>
<span data-ttu-id="7826c-246">Esse cmdlet obtém apenas os trabalhos no estado especificado.</span><span class="sxs-lookup"><span data-stu-id="7826c-246">This cmdlet gets only jobs in the specified state.</span></span>
<span data-ttu-id="7826c-247">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="7826c-247">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="7826c-248">NotStarted</span><span class="sxs-lookup"><span data-stu-id="7826c-248">NotStarted</span></span>
- <span data-ttu-id="7826c-249">Executando</span><span class="sxs-lookup"><span data-stu-id="7826c-249">Running</span></span>
- <span data-ttu-id="7826c-250">Concluído</span><span class="sxs-lookup"><span data-stu-id="7826c-250">Completed</span></span>
- <span data-ttu-id="7826c-251">Falhou</span><span class="sxs-lookup"><span data-stu-id="7826c-251">Failed</span></span>
- <span data-ttu-id="7826c-252">Parado</span><span class="sxs-lookup"><span data-stu-id="7826c-252">Stopped</span></span>
- <span data-ttu-id="7826c-253">Bloqueado</span><span class="sxs-lookup"><span data-stu-id="7826c-253">Blocked</span></span>
- <span data-ttu-id="7826c-254">Suspenso</span><span class="sxs-lookup"><span data-stu-id="7826c-254">Suspended</span></span>
- <span data-ttu-id="7826c-255">Desconectado</span><span class="sxs-lookup"><span data-stu-id="7826c-255">Disconnected</span></span>
- <span data-ttu-id="7826c-256">Suspensão</span><span class="sxs-lookup"><span data-stu-id="7826c-256">Suspending</span></span>
- <span data-ttu-id="7826c-257">Parando</span><span class="sxs-lookup"><span data-stu-id="7826c-257">Stopping</span></span>

<span data-ttu-id="7826c-258">Por padrão, o **Get-Job** obtém todos os trabalhos existentes na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="7826c-258">By default, **Get-Job** gets all the jobs in the current session.</span></span>

<span data-ttu-id="7826c-259">Para obter mais informações sobre os Estados de trabalho, consulte [Enumeração JobState](https://msdn.microsoft.com/library/system.management.automation.jobstate) na biblioteca MSDN.</span><span class="sxs-lookup"><span data-stu-id="7826c-259">For more information about job states, see [JobState Enumeration](https://msdn.microsoft.com/library/system.management.automation.jobstate) in the MSDN library.</span></span>

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

### <span data-ttu-id="7826c-260">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7826c-260">CommonParameters</span></span>

<span data-ttu-id="7826c-261">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7826c-261">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7826c-262">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7826c-262">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7826c-263">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="7826c-263">INPUTS</span></span>

### <span data-ttu-id="7826c-264">Nenhum</span><span class="sxs-lookup"><span data-stu-id="7826c-264">None</span></span>

<span data-ttu-id="7826c-265">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7826c-265">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="7826c-266">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="7826c-266">OUTPUTS</span></span>

### <span data-ttu-id="7826c-267">System. Management. Automation. RemotingJob</span><span class="sxs-lookup"><span data-stu-id="7826c-267">System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="7826c-268">Esse cmdlet retorna objetos que representam os trabalhos na sessão.</span><span class="sxs-lookup"><span data-stu-id="7826c-268">This cmdlet returns objects that represent the jobs in the session.</span></span>

## <span data-ttu-id="7826c-269">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="7826c-269">NOTES</span></span>

* <span data-ttu-id="7826c-270">A propriedade **PSJobTypeName** dos trabalhos indica o tipo do trabalho em questão.</span><span class="sxs-lookup"><span data-stu-id="7826c-270">The **PSJobTypeName** property of jobs indicates the job type of the job.</span></span> <span data-ttu-id="7826c-271">O valor da propriedade é determinado pelo autor do tipo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="7826c-271">The property value is determined by the job type author.</span></span> <span data-ttu-id="7826c-272">A lista a seguir mostra os tipos de trabalho comuns.</span><span class="sxs-lookup"><span data-stu-id="7826c-272">The following list shows common job types.</span></span>

  - <span data-ttu-id="7826c-273">**BackgroundJob** .</span><span class="sxs-lookup"><span data-stu-id="7826c-273">**BackgroundJob** .</span></span>
<span data-ttu-id="7826c-274">Trabalho local iniciado usando **Start-Job** .</span><span class="sxs-lookup"><span data-stu-id="7826c-274">Local job started by using **Start-Job** .</span></span>

  - <span data-ttu-id="7826c-275">**RemoteJob** .</span><span class="sxs-lookup"><span data-stu-id="7826c-275">**RemoteJob** .</span></span>
<span data-ttu-id="7826c-276">Trabalho iniciado em uma **PSSession** usando o parâmetro *AsJob* do cmdlet Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="7826c-276">Job started in a **PSSession** by using the *AsJob* parameter of the Invoke-Command cmdlet.</span></span>

  - <span data-ttu-id="7826c-277">**PSWorkflowJob** .</span><span class="sxs-lookup"><span data-stu-id="7826c-277">**PSWorkflowJob** .</span></span>
<span data-ttu-id="7826c-278">Trabalho iniciado usando o parâmetro comum *AsJob* dos fluxos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="7826c-278">Job started by using the *AsJob* common parameter of workflows.</span></span>

## <span data-ttu-id="7826c-279">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="7826c-279">RELATED LINKS</span></span>

[<span data-ttu-id="7826c-280">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="7826c-280">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="7826c-281">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="7826c-281">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="7826c-282">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="7826c-282">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="7826c-283">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="7826c-283">Resume-Job</span></span>](Resume-Job.md)

[<span data-ttu-id="7826c-284">Start-Job</span><span class="sxs-lookup"><span data-stu-id="7826c-284">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="7826c-285">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="7826c-285">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="7826c-286">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="7826c-286">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="7826c-287">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="7826c-287">Wait-Job</span></span>](Wait-Job.md)

[<span data-ttu-id="7826c-288">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="7826c-288">about_Jobs</span></span>](About/about_Jobs.md)

[<span data-ttu-id="7826c-289">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="7826c-289">about_Job_Details</span></span>](About/about_Job_Details.md)

[<span data-ttu-id="7826c-290">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="7826c-290">about_Remote_Jobs</span></span>](About/about_Remote_Jobs.md)

[<span data-ttu-id="7826c-291">about_Scheduled_Jobs</span><span class="sxs-lookup"><span data-stu-id="7826c-291">about_Scheduled_Jobs</span></span>](../PSScheduledJob/About/about_Scheduled_Jobs.md)
