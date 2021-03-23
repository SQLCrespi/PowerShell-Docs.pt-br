---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/22/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/receive-job?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Receive-Job
ms.openlocfilehash: a0b8080f5398c1405e933c514ea8afb23476ed55
ms.sourcegitcommit: a0148ef8bf9757f68c788d24f2eaf92792c3979f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2021
ms.locfileid: "104796287"
---
# <span data-ttu-id="13452-103">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="13452-103">Receive-Job</span></span>

## <span data-ttu-id="13452-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="13452-104">SYNOPSIS</span></span>
<span data-ttu-id="13452-105">Obtém os resultados dos trabalhos em segundo plano do PowerShell na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="13452-105">Gets the results of the PowerShell background jobs in the current session.</span></span>

## <span data-ttu-id="13452-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="13452-106">SYNTAX</span></span>

### <span data-ttu-id="13452-107">Local (padrão)</span><span class="sxs-lookup"><span data-stu-id="13452-107">Location (Default)</span></span>

```
Receive-Job [-Job] <Job[]> [[-Location] <String[]>] [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob]
 [-WriteEvents] [-WriteJobInResults] [<CommonParameters>]
```

### <span data-ttu-id="13452-108">ComputerName</span><span class="sxs-lookup"><span data-stu-id="13452-108">ComputerName</span></span>

```
Receive-Job [-Job] <Job[]> [[-ComputerName] <String[]>] [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob]
 [-WriteEvents] [-WriteJobInResults] [<CommonParameters>]
```

### <span data-ttu-id="13452-109">Session</span><span class="sxs-lookup"><span data-stu-id="13452-109">Session</span></span>

```
Receive-Job [-Job] <Job[]> [[-Session] <PSSession[]>] [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob]
 [-WriteEvents] [-WriteJobInResults] [<CommonParameters>]
```

### <span data-ttu-id="13452-110">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="13452-110">NameParameterSet</span></span>

```
Receive-Job [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob] [-WriteEvents] [-WriteJobInResults]
 [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="13452-111">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="13452-111">InstanceIdParameterSet</span></span>

```
Receive-Job [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob] [-WriteEvents] [-WriteJobInResults]
 [-InstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="13452-112">SessionIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="13452-112">SessionIdParameterSet</span></span>

```
Receive-Job [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob] [-WriteEvents] [-WriteJobInResults]
 [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="13452-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="13452-113">DESCRIPTION</span></span>

<span data-ttu-id="13452-114">O `Receive-Job` cmdlet obtém os resultados de trabalhos em segundo plano do PowerShell, como aqueles iniciados usando o `Start-Job` cmdlet ou o parâmetro **AsJob** de qualquer cmdlet.</span><span class="sxs-lookup"><span data-stu-id="13452-114">The `Receive-Job` cmdlet gets the results of PowerShell background jobs, such as those started by using the `Start-Job` cmdlet or the **AsJob** parameter of any cmdlet.</span></span>
<span data-ttu-id="13452-115">Você pode obter os resultados de todos os trabalhos ou identificar trabalhos pelo nome, ID, ID de instância, nome do computador, local ou sessão ou enviando um objeto de trabalho.</span><span class="sxs-lookup"><span data-stu-id="13452-115">You can get the results of all jobs or identify jobs by their name, ID, instance ID, computer name, location, or session, or by submitting a job object.</span></span>

<span data-ttu-id="13452-116">Quando você inicia um trabalho em segundo plano do PowerShell, o trabalho é iniciado, mas os resultados não aparecem imediatamente.</span><span class="sxs-lookup"><span data-stu-id="13452-116">When you start a PowerShell background job, the job starts, but the results do not appear immediately.</span></span> <span data-ttu-id="13452-117">Em vez disso, o comando retorna um objeto que representa o trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="13452-117">Instead, the command returns an object that represents the background job.</span></span>
<span data-ttu-id="13452-118">O objeto de trabalho contém informações úteis sobre o trabalho, mas não contém os resultados.</span><span class="sxs-lookup"><span data-stu-id="13452-118">The job object contains useful information about the job, but it does not contain the results.</span></span>
<span data-ttu-id="13452-119">Esse método permite que você continue a trabalhar na sessão enquanto o trabalho é executado.</span><span class="sxs-lookup"><span data-stu-id="13452-119">This method lets you continue to work in the session while the job runs.</span></span>
<span data-ttu-id="13452-120">Para obter mais informações sobre trabalhos em segundo plano no PowerShell, consulte [about_Jobs](./About/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="13452-120">For more information about background jobs in PowerShell, see [about_Jobs](./About/about_Jobs.md).</span></span>

<span data-ttu-id="13452-121">O `Receive-Job` cmdlet obtém os resultados que foram gerados pela hora em que o `Receive-Job` comando foi enviado.</span><span class="sxs-lookup"><span data-stu-id="13452-121">The `Receive-Job` cmdlet gets the results that have been generated by the time that the `Receive-Job` command is submitted.</span></span>
<span data-ttu-id="13452-122">Se os resultados ainda não estiverem completos, você poderá executar `Receive-Job` comandos adicionais para obter os resultados restantes.</span><span class="sxs-lookup"><span data-stu-id="13452-122">If the results are not yet complete, you can run additional `Receive-Job` commands to get the remaining results.</span></span>

<span data-ttu-id="13452-123">Por padrão, os resultados do trabalho são excluídos do sistema quando são recebidos, mas você pode usar o parâmetro **Keep** para salvar os resultados para poder recebê-los novamente.</span><span class="sxs-lookup"><span data-stu-id="13452-123">By default, job results are deleted from the system when you receive them, but you can use the **Keep** parameter to save the results so that you can receive them again.</span></span>
<span data-ttu-id="13452-124">Para excluir os resultados do trabalho, execute o `Receive-Job` comando novamente sem o parâmetro **Keep** , feche a sessão ou use o `Remove-Job` cmdlet para excluir o trabalho da sessão.</span><span class="sxs-lookup"><span data-stu-id="13452-124">To delete the job results, run the `Receive-Job` command again without the **Keep** parameter, close the session, or use the `Remove-Job` cmdlet to delete the job from the session.</span></span>

<span data-ttu-id="13452-125">A partir do Windows PowerShell 3,0, `Receive-Job` o também obtém os resultados de tipos de trabalho personalizados, como trabalhos de workflow e instâncias de trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="13452-125">Starting in Windows PowerShell 3.0, `Receive-Job` also gets the results of custom job types, such as workflow jobs and instances of scheduled jobs.</span></span>
<span data-ttu-id="13452-126">Para habilitar `Receive-Job` o a fim de obter os resultados de um tipo de trabalho personalizado, importe o módulo que dá suporte ao tipo de trabalho personalizado na sessão antes de executar um `Receive-Job` comando, seja usando o `Import-Module` cmdlet ou obtendo um cmdlet no módulo.</span><span class="sxs-lookup"><span data-stu-id="13452-126">To enable `Receive-Job` to get the results a custom job type, import the module that supports the custom job type into the session before it runs a `Receive-Job` command, either by using the `Import-Module` cmdlet or by using or getting a cmdlet in the module.</span></span>
<span data-ttu-id="13452-127">Para obter informações sobre um tipo específico de trabalho personalizado, consulte a documentação do recurso de tipo de trabalho personalizado.</span><span class="sxs-lookup"><span data-stu-id="13452-127">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="13452-128">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="13452-128">EXAMPLES</span></span>

### <span data-ttu-id="13452-129">Exemplo 1: obter resultados para um trabalho específico</span><span class="sxs-lookup"><span data-stu-id="13452-129">Example 1: Get results for a particular job</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Process}
Receive-Job -Job $job
```

<span data-ttu-id="13452-130">Esses comandos usam o parâmetro de **trabalho** de `Receive-Job` para obter os resultados de um trabalho específico.</span><span class="sxs-lookup"><span data-stu-id="13452-130">These commands use the **Job** parameter of `Receive-Job` to get the results of a particular job.</span></span>

<span data-ttu-id="13452-131">O primeiro comando inicia um trabalho com `Start-Job` e armazena o objeto de trabalho na `$job` variável.</span><span class="sxs-lookup"><span data-stu-id="13452-131">The first command starts a job with `Start-Job` and stores the job object in the `$job` variable.</span></span>

<span data-ttu-id="13452-132">O segundo comando usa o `Receive-Job` cmdlet para obter os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="13452-132">The second command uses the `Receive-Job` cmdlet to get the results of the job.</span></span>
<span data-ttu-id="13452-133">Ele usa o parâmetro **Job** para especificar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="13452-133">It uses the **Job** parameter to specify the job.</span></span>

### <span data-ttu-id="13452-134">Exemplo 2: usar o parâmetro Keep</span><span class="sxs-lookup"><span data-stu-id="13452-134">Example 2: Use the Keep parameter</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Service dhcp, fakeservice}
$job | Receive-Job -Keep
```

```Output
Cannot find any service with service name 'fakeservice'.
    + CategoryInfo          : ObjectNotFound: (fakeservice:String) [Get-Service], ServiceCommandException
    + FullyQualifiedErrorId : NoServiceFoundForGivenName,Microsoft.PowerShell.Commands.GetServiceCommand
    + PSComputerName        : localhost

Status   Name               DisplayName
------   ----               -----------
Running  dhcp               DHCP Client
```

```powershell
$job | Receive-Job -Keep
```

```Output
Cannot find any service with service name 'fakeservice'.
    + CategoryInfo          : ObjectNotFound: (fakeservice:String) [Get-Service], ServiceCommandException
    + FullyQualifiedErrorId : NoServiceFoundForGivenName,Microsoft.PowerShell.Commands.GetServiceCommand
    + PSComputerName        : localhost

Status   Name               DisplayName
------   ----               -----------
Running  dhcp               DHCP Client
```

<span data-ttu-id="13452-135">Este exemplo armazena um trabalho na `$job` variável e canaliza o trabalho para o `Receive-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="13452-135">This example stores a job in the `$job` variable, and pipes the job to the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="13452-136">O `-Keep` parâmetro também é usado para permitir que todos os dados de fluxo agregados sejam recuperados novamente após a primeira exibição.</span><span class="sxs-lookup"><span data-stu-id="13452-136">The `-Keep` parameter is also used to allow all aggregated stream data to be retrieved again after first view.</span></span>

### <span data-ttu-id="13452-137">Exemplo 3: obter resultados de vários trabalhos em segundo plano</span><span class="sxs-lookup"><span data-stu-id="13452-137">Example 3: Get results of several background jobs</span></span>

<span data-ttu-id="13452-138">Quando você usa o parâmetro **AsJob** do `Invoke-Command` para iniciar um trabalho, o objeto de trabalho é criado no computador local, embora o trabalho seja executado nos computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="13452-138">When you use the **AsJob** parameter of `Invoke-Command` to start a job, the job object is created on the local computer, even though the job runs on the remote computers.</span></span>
<span data-ttu-id="13452-139">Como resultado, você deve usar comandos locais para gerenciar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="13452-139">As a result, you use local commands to manage the job.</span></span>

<span data-ttu-id="13452-140">Além disso, quando você usa **AsJob**, o PowerShell retorna um objeto de trabalho que contém um trabalho filho para cada trabalho iniciado.</span><span class="sxs-lookup"><span data-stu-id="13452-140">Also, when you use **AsJob**, PowerShell returns one job object that contains a child job for each job that was started.</span></span> <span data-ttu-id="13452-141">Nesse caso, o objeto de trabalho contém três tarefas filhas, uma para cada trabalho em cada computador remoto.</span><span class="sxs-lookup"><span data-stu-id="13452-141">In this case, the job object contains three child jobs, one for each job on each remote computer.</span></span>

```powershell
# Use the Invoke-Command cmdlet with the -AsJob parameter to start a background job that runs a Get-Service command on three remote computers.
# Store the resulting job object in the $j variable
$j = Invoke-Command -ComputerName Server01, Server02, Server03 -ScriptBlock {Get-Service} -AsJob
# Display the value of the **ChildJobs** property of the job object in $j.
# The display shows that the command created three child jobs, one for the job on each remote computer.
# You could also use the -IncludeChildJobs parameter of the Get-Job cmdlet.
$j.ChildJobs
```

```Output
Id   Name     State      HasMoreData   Location       Command
--   ----     -----      -----------   --------       -------
2    Job2     Completed  True          Server01       Get-Service
3    Job3     Completed  True          Server02       Get-Service
4    Job4     Completed  True          Server03       Get-Service
```

```powershell
# Use the Receive-Job cmdlet to get the results of just the Job3 child job that ran on the Server02 computer.
# Use the *Keep* parameter to allow you to view the aggregated stream data more than once.
Receive-Job -Name Job3 -Keep
```

```Output
Status  Name        DisplayName                        PSComputerName
------  ----------- -----------                        --------------
Running AeLookupSvc Application Experience             Server02
Stopped ALG         Application Layer Gateway Service  Server02
Running Appinfo     Application Information            Server02
Running AppMgmt     Application Management             Server02
```

### <span data-ttu-id="13452-142">Exemplo 4: obter resultados de trabalhos em segundo plano em vários computadores remotos</span><span class="sxs-lookup"><span data-stu-id="13452-142">Example 4: Get results of background jobs on multiple remote computers</span></span>

```powershell
# Use the New-PSSession cmdlet to create three user-managed PSSessions on three servers, and save the sessions in the $s variable.
$s = New-PSSession -ComputerName Server01, Server02, Server03
# Use Invoke-Command run a Start-Job command in each of the PSSessions in the $s variable.
# The creates a new job with a custom name to each server
# The job outputs the datetime from each server
# Save the job objects in the $j variable.
$j = Invoke-Command -Session $s -ScriptBlock {Start-Job -Name $('MyJob-' +$env:COMPUTERNAME) -ScriptBlock {(Get-Date).ToString()}}
# To confirm that these job objects are from the remote machines, run Get-Job to show no local jobs running.
Get-Job
```

```Output

```

```powershell
# Display the three job objects in $j.
# Note that the Localhost location is not the local computer, but instead localhost as it relates to the job on each Server.
$j
```

```Output
Id   Name               State      HasMoreData   Location   Command
--   ----               -----      -----------   --------   -------
1    MyJob-Server01     Completed  True          Localhost  (Get-Date).ToString()
2    MyJob-Server02     Completed  True          Localhost  (Get-Date).ToString()
3    MyJob-Server03     Completed  True          Localhost  (Get-Date).ToString()
```

```powershell
# Use Invoke-Command to run a Receive-Job command in each of the sessions in the $s variable and save the results in the $results variable.
# The Receive-Job command must be run in each session because the jobs were run locally on each server.
$results = Invoke-Command -Session $s -ScriptBlock {Receive-Job -Name $('MyJob-' +$env:COMPUTERNAME)}
```

```Output
3/22/2021 7:41:47 PM
3/22/2021 7:41:47 PM
3/22/2021 9:41:47 PM
```

<span data-ttu-id="13452-143">Este exemplo mostra como obter os resultados de trabalhos em segundo plano executados em três computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="13452-143">This example shows how to get the results of background jobs run on three remote computers.</span></span>
<span data-ttu-id="13452-144">Ao contrário do exemplo anterior, usar `Invoke-Command` para executar o `Start-Job` comando efetivamente iniciou três trabalhos independentes em cada um dos três computadores.</span><span class="sxs-lookup"><span data-stu-id="13452-144">Unlike the previous example, using `Invoke-Command` to run the `Start-Job` command actually started three independent jobs on each of the three computers.</span></span> <span data-ttu-id="13452-145">Como resultado, o comando retornou três objetos de trabalho que representam três trabalhos executados localmente nos três computadores diferentes.</span><span class="sxs-lookup"><span data-stu-id="13452-145">As a result, the command returned three job objects representing three jobs run locally on three different computers.</span></span>

### <span data-ttu-id="13452-146">Exemplo 5: acessar trabalhos filho</span><span class="sxs-lookup"><span data-stu-id="13452-146">Example 5: Access child jobs</span></span>

<span data-ttu-id="13452-147">O `-Keep` parâmetro preserva o estado dos fluxos agregados de um trabalho para que ele possa ser exibido novamente.</span><span class="sxs-lookup"><span data-stu-id="13452-147">The `-Keep` parameter preserves the state of the aggregated streams of a job so that it can be viewed again.</span></span> <span data-ttu-id="13452-148">Sem esse parâmetro, todos os dados de fluxo agregados são apagados quando o trabalho é recebido.</span><span class="sxs-lookup"><span data-stu-id="13452-148">Without this parameter all aggregated stream data is erased when the job is received.</span></span> <span data-ttu-id="13452-149">Para obter mais informações, consulte [about_Job_Details](About/about_Job_Details.md#child-jobs)</span><span class="sxs-lookup"><span data-stu-id="13452-149">For more information, see [about_Job_Details](About/about_Job_Details.md#child-jobs)</span></span>

> [!NOTE]
> <span data-ttu-id="13452-150">Os fluxos agregados incluem os fluxos de todos os trabalhos filho.</span><span class="sxs-lookup"><span data-stu-id="13452-150">The aggregated streams include the streams of all child jobs.</span></span> <span data-ttu-id="13452-151">Você ainda pode acessar os fluxos de dados individuais por meio do objeto de trabalho e dos objetos de trabalho filho.</span><span class="sxs-lookup"><span data-stu-id="13452-151">You can still reach the individual streams of data through the job object and child job objects.</span></span>

```powershell
Start-Job -Name TestJob -ScriptBlock {dir C:\, Z:\}
# Without the Keep parameter, aggregated child job data is displayed once.
# Then destroyed.
Receive-Job -Name TestJob
```

```Output
    Directory: C:\

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-r---        1/24/2019   7:11 AM                Program Files
d-r---        2/13/2019   8:32 AM                Program Files (x86)
d-r---        10/3/2018  11:47 AM                Users
d-----         2/7/2019   1:52 AM                Windows
Cannot find drive. A drive with the name 'Z' does not exist.
    + CategoryInfo          : ObjectNotFound: (Z:String) [Get-ChildItem], DriveNotFoundException
    + FullyQualifiedErrorId : DriveNotFound,Microsoft.PowerShell.Commands.GetChildItemCommand
    + PSComputerName        : localhost
```

```powershell
# It would seem that the child job data is gone.
Receive-Job -Name TestJob
```

```Output

```

```powershell
# Using the object model, you can still retrieve child job data and streams.
$job = Get-Job -Name TestJob
$job.ChildJobs[0].Error
```

```Output
Cannot find drive. A drive with the name 'Z' does not exist.
    + CategoryInfo          : ObjectNotFound: (Z:String) [Get-ChildItem], DriveNotFoundException
    + FullyQualifiedErrorId : DriveNotFound,Microsoft.PowerShell.Commands.GetChildItemCommand
    + PSComputerName        : localhost
```

## <span data-ttu-id="13452-152">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="13452-152">PARAMETERS</span></span>

### <span data-ttu-id="13452-153">-AutoRemoveJob</span><span class="sxs-lookup"><span data-stu-id="13452-153">-AutoRemoveJob</span></span>

<span data-ttu-id="13452-154">Indica que esse cmdlet exclui o trabalho depois de retornar os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="13452-154">Indicates that this cmdlet deletes the job after it returns the job results.</span></span>
<span data-ttu-id="13452-155">Se o trabalho tiver mais resultados, o trabalho ainda será excluído, mas `Receive-Job` exibirá uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="13452-155">If the job has more results, the job is still deleted, but `Receive-Job` displays a message.</span></span>

<span data-ttu-id="13452-156">Esse parâmetro só funciona em tipos de trabalho personalizados.</span><span class="sxs-lookup"><span data-stu-id="13452-156">This parameter works only on custom job types.</span></span>
<span data-ttu-id="13452-157">Ele é projetado para instâncias de tipos de trabalho que salvam o trabalho ou o tipo fora da sessão, como instâncias de trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="13452-157">It is designed for instances of job types that save the job or the type outside of the session, such as instances of scheduled jobs.</span></span>

<span data-ttu-id="13452-158">Esse parâmetro não pode ser usado sem o parâmetro **Wait** .</span><span class="sxs-lookup"><span data-stu-id="13452-158">This parameter cannot be used without the **Wait** parameter.</span></span>

<span data-ttu-id="13452-159">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="13452-159">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="13452-160">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="13452-160">-ComputerName</span></span>

<span data-ttu-id="13452-161">Especifica uma matriz de nomes de computadores.</span><span class="sxs-lookup"><span data-stu-id="13452-161">Specifies an array of names of computers.</span></span>

<span data-ttu-id="13452-162">Esse parâmetro seleciona entre os resultados do trabalho que estão armazenados no computador local.</span><span class="sxs-lookup"><span data-stu-id="13452-162">This parameter selects from among the job results that are stored on the local computer.</span></span>
<span data-ttu-id="13452-163">Ele não obtém dados para trabalhos executados em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="13452-163">It does not get data for jobs run on remote computers.</span></span>
<span data-ttu-id="13452-164">Para obter os resultados do trabalho armazenados em computadores remotos, use o `Invoke-Command` cmdlet para executar um `Receive-Job` comando remotamente.</span><span class="sxs-lookup"><span data-stu-id="13452-164">To get job results that are stored on remote computers, use the `Invoke-Command` cmdlet to run a `Receive-Job` command remotely.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerName
Aliases: Cn

Required: False
Position: 1
Default value: All computers available
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="13452-165">-Force</span><span class="sxs-lookup"><span data-stu-id="13452-165">-Force</span></span>

<span data-ttu-id="13452-166">Indica que esse cmdlet continuará aguardando se os trabalhos estiverem no estado **suspenso** ou **desconectado** .</span><span class="sxs-lookup"><span data-stu-id="13452-166">Indicates that this cmdlet continues waiting if jobs are in the **Suspended** or **Disconnected** state.</span></span> <span data-ttu-id="13452-167">Por padrão, o parâmetro **Wait** de `Receive-Job` retorna ou encerra a espera, quando os trabalhos estão em um dos seguintes Estados:</span><span class="sxs-lookup"><span data-stu-id="13452-167">By default, the **Wait** parameter of `Receive-Job` returns, or terminates the wait, when jobs are in one of the following states:</span></span>

- <span data-ttu-id="13452-168">Concluído</span><span class="sxs-lookup"><span data-stu-id="13452-168">Completed</span></span>
- <span data-ttu-id="13452-169">Falhou</span><span class="sxs-lookup"><span data-stu-id="13452-169">Failed</span></span>
- <span data-ttu-id="13452-170">Parado</span><span class="sxs-lookup"><span data-stu-id="13452-170">Stopped</span></span>
- <span data-ttu-id="13452-171">Suspenso</span><span class="sxs-lookup"><span data-stu-id="13452-171">Suspended</span></span>
- <span data-ttu-id="13452-172">Desconectado</span><span class="sxs-lookup"><span data-stu-id="13452-172">Disconnected.</span></span>

<span data-ttu-id="13452-173">O parâmetro **Force** é válido somente quando o parâmetro **Wait** também é usado no comando.</span><span class="sxs-lookup"><span data-stu-id="13452-173">The **Force** parameter is valid only when the **Wait** parameter is also used in the command.</span></span>

<span data-ttu-id="13452-174">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="13452-174">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="13452-175">-Id</span><span class="sxs-lookup"><span data-stu-id="13452-175">-Id</span></span>

<span data-ttu-id="13452-176">Especifica uma matriz de IDs.</span><span class="sxs-lookup"><span data-stu-id="13452-176">Specifies an array of IDs.</span></span>
<span data-ttu-id="13452-177">Esse cmdlet obtém os resultados de trabalhos com as IDs especificadas.</span><span class="sxs-lookup"><span data-stu-id="13452-177">This cmdlet gets the results of jobs with the specified IDs.</span></span>

<span data-ttu-id="13452-178">A ID é um inteiro que identifica exclusivamente o trabalho na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="13452-178">The ID is an integer that uniquely identifies the job in the current session.</span></span>
<span data-ttu-id="13452-179">É mais fácil lembrar e digitar do que a ID da instância, mas só é exclusiva na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="13452-179">It is easier to remember and type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="13452-180">Você pode digitar uma ou mais IDs separadas por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="13452-180">You can type one or more IDs separated by commas.</span></span>
<span data-ttu-id="13452-181">Para localizar a ID de um trabalho, use `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="13452-181">To find the ID of a job, use `Get-Job`.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="13452-182">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="13452-182">-InstanceId</span></span>

<span data-ttu-id="13452-183">Especifica uma matriz de IDs de instância.</span><span class="sxs-lookup"><span data-stu-id="13452-183">Specifies an array of instance IDs.</span></span>
<span data-ttu-id="13452-184">Esse cmdlet obtém os resultados de trabalhos com as IDs de instância especificadas.</span><span class="sxs-lookup"><span data-stu-id="13452-184">This cmdlet gets the results of jobs with the specified instance IDs.</span></span>

<span data-ttu-id="13452-185">Uma ID de instância é um GUID que identifica exclusivamente o trabalho no computador.</span><span class="sxs-lookup"><span data-stu-id="13452-185">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span>
<span data-ttu-id="13452-186">Para localizar a ID de instância de um trabalho, use o `Get-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="13452-186">To find the instance ID of a job, use the `Get-Job` cmdlet.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: All instances
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="13452-187">-Trabalho</span><span class="sxs-lookup"><span data-stu-id="13452-187">-Job</span></span>

<span data-ttu-id="13452-188">Especifica o trabalho para o qual os resultados estão sendo recuperados.</span><span class="sxs-lookup"><span data-stu-id="13452-188">Specifies the job for which results are being retrieved.</span></span>

<span data-ttu-id="13452-189">Insira uma variável que contenha o trabalho ou um comando que obtenha o trabalho.</span><span class="sxs-lookup"><span data-stu-id="13452-189">Enter a variable that contains the job or a command that gets the job.</span></span>
<span data-ttu-id="13452-190">Também é possível canalizar um objeto de trabalho para `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="13452-190">You can also pipe a job object to `Receive-Job`.</span></span>

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: Location, Session, ComputerName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="13452-191">-Manter</span><span class="sxs-lookup"><span data-stu-id="13452-191">-Keep</span></span>

<span data-ttu-id="13452-192">Indica que esse cmdlet salva os dados de fluxo agregados no sistema, mesmo depois de você tê-los recebido.</span><span class="sxs-lookup"><span data-stu-id="13452-192">Indicates that this cmdlet saves the aggregated stream data in the system, even after you have received them.</span></span> <span data-ttu-id="13452-193">Por padrão, os dados de fluxo agregados são apagados depois de exibidos com `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="13452-193">By default, aggregated stream data is erased after viewed with `Receive-Job`.</span></span>

<span data-ttu-id="13452-194">Fechar a sessão ou remover o trabalho com o `Remove-Job` cmdlet também exclui dados de fluxo agregados.</span><span class="sxs-lookup"><span data-stu-id="13452-194">Closing the session, or removing the job with the `Remove-Job` cmdlet also deletes aggregated stream data.</span></span>

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

### <span data-ttu-id="13452-195">-Local</span><span class="sxs-lookup"><span data-stu-id="13452-195">-Location</span></span>

<span data-ttu-id="13452-196">Especifica uma matriz de locais.</span><span class="sxs-lookup"><span data-stu-id="13452-196">Specifies an array of locations.</span></span>
<span data-ttu-id="13452-197">Esse cmdlet obtém apenas os resultados de trabalhos nos locais especificados.</span><span class="sxs-lookup"><span data-stu-id="13452-197">This cmdlet gets only the results of jobs in the specified locations.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Location
Aliases:

Required: False
Position: 1
Default value: All locations
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="13452-198">-Name</span><span class="sxs-lookup"><span data-stu-id="13452-198">-Name</span></span>

<span data-ttu-id="13452-199">Especifica uma matriz de nomes amigáveis.</span><span class="sxs-lookup"><span data-stu-id="13452-199">Specifies an array of friendly names.</span></span>
<span data-ttu-id="13452-200">Esse cmdlet obtém os resultados de trabalhos que têm os nomes especificados.</span><span class="sxs-lookup"><span data-stu-id="13452-200">This cmdlet gets the results of jobs that have the specified names.</span></span>
<span data-ttu-id="13452-201">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="13452-201">Wildcard characters are supported.</span></span>

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

### <span data-ttu-id="13452-202">-Recorrência</span><span class="sxs-lookup"><span data-stu-id="13452-202">-NoRecurse</span></span>

<span data-ttu-id="13452-203">Indica que esse cmdlet obtém resultados apenas do trabalho especificado.</span><span class="sxs-lookup"><span data-stu-id="13452-203">Indicates that this cmdlet gets results only from the specified job.</span></span>
<span data-ttu-id="13452-204">Por padrão, `Receive-Job` o também obtém os resultados de todos os trabalhos filho do trabalho especificado.</span><span class="sxs-lookup"><span data-stu-id="13452-204">By default, `Receive-Job` also gets the results of all child jobs of the specified job.</span></span>

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

### <span data-ttu-id="13452-205">-Sessão</span><span class="sxs-lookup"><span data-stu-id="13452-205">-Session</span></span>

<span data-ttu-id="13452-206">Especifica uma matriz de sessões.</span><span class="sxs-lookup"><span data-stu-id="13452-206">Specifies an array of sessions.</span></span>
<span data-ttu-id="13452-207">Esse cmdlet obtém os resultados de trabalhos que foram executados na sessão do PowerShell especificada (**PSSession**).</span><span class="sxs-lookup"><span data-stu-id="13452-207">This cmdlet gets the results of jobs that were run in the specified PowerShell session (**PSSession**).</span></span>
<span data-ttu-id="13452-208">Insira uma variável que contém a **PSSession** ou um comando que obtém a **PSSession**, como um `Get-PSSession` comando.</span><span class="sxs-lookup"><span data-stu-id="13452-208">Enter a variable that contains the **PSSession** or a command that gets the **PSSession**, such as a `Get-PSSession` command.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: False
Position: 1
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="13452-209">-Wait</span><span class="sxs-lookup"><span data-stu-id="13452-209">-Wait</span></span>

<span data-ttu-id="13452-210">Indica que esse cmdlet suprime o prompt de comando até que todos os resultados do trabalho sejam recebidos.</span><span class="sxs-lookup"><span data-stu-id="13452-210">Indicates that this cmdlet suppresses the command prompt until all job results are received.</span></span>
<span data-ttu-id="13452-211">Por padrão, `Receive-Job` o retorna imediatamente os resultados disponíveis.</span><span class="sxs-lookup"><span data-stu-id="13452-211">By default, `Receive-Job` immediately returns the available results.</span></span>

<span data-ttu-id="13452-212">Por padrão, o parâmetro **Wait** aguarda até que o trabalho esteja em um dos seguintes estados:</span><span class="sxs-lookup"><span data-stu-id="13452-212">By default, the **Wait** parameter waits until the job is in one of the following states:</span></span>

- <span data-ttu-id="13452-213">Concluído</span><span class="sxs-lookup"><span data-stu-id="13452-213">Completed</span></span>
- <span data-ttu-id="13452-214">Falhou</span><span class="sxs-lookup"><span data-stu-id="13452-214">Failed</span></span>
- <span data-ttu-id="13452-215">Parado</span><span class="sxs-lookup"><span data-stu-id="13452-215">Stopped</span></span>
- <span data-ttu-id="13452-216">Suspenso</span><span class="sxs-lookup"><span data-stu-id="13452-216">Suspended</span></span>
- <span data-ttu-id="13452-217">Desconectado</span><span class="sxs-lookup"><span data-stu-id="13452-217">Disconnected.</span></span>

<span data-ttu-id="13452-218">Para direcionar o parâmetro **Wait** para continuar aguardando se o estado do trabalho for suspenso ou desconectado, use o parâmetro **Force** junto com o parâmetro **Wait** .</span><span class="sxs-lookup"><span data-stu-id="13452-218">To direct the **Wait** parameter to continue waiting if the job state is Suspended or Disconnected, use the **Force** parameter together with the **Wait** parameter.</span></span>

<span data-ttu-id="13452-219">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="13452-219">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="13452-220">-WriteEvents</span><span class="sxs-lookup"><span data-stu-id="13452-220">-WriteEvents</span></span>

<span data-ttu-id="13452-221">Indica que esse cmdlet relata alterações no estado do trabalho enquanto aguarda a conclusão do trabalho.</span><span class="sxs-lookup"><span data-stu-id="13452-221">Indicates that this cmdlet reports changes in the job state while it waits for the job to finish.</span></span>

<span data-ttu-id="13452-222">Esse parâmetro é válido somente quando o parâmetro **Wait** é usado no comando e o parâmetro **Keep** é omitido.</span><span class="sxs-lookup"><span data-stu-id="13452-222">This parameter is valid only when the **Wait** parameter is used in the command and the **Keep** parameter is omitted.</span></span>

<span data-ttu-id="13452-223">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="13452-223">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="13452-224">-WriteJobInResults</span><span class="sxs-lookup"><span data-stu-id="13452-224">-WriteJobInResults</span></span>

<span data-ttu-id="13452-225">Indica que esse cmdlet retorna o objeto de trabalho seguido pelos resultados.</span><span class="sxs-lookup"><span data-stu-id="13452-225">Indicates that this cmdlet returns the job object followed by the results.</span></span>

<span data-ttu-id="13452-226">Esse parâmetro é válido somente quando o parâmetro **Wait** é usado no comando e o parâmetro **Keep** é omitido.</span><span class="sxs-lookup"><span data-stu-id="13452-226">This parameter is valid only when the **Wait** parameter is used in the command and the **Keep** parameter is omitted.</span></span>

<span data-ttu-id="13452-227">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="13452-227">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="13452-228">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="13452-228">CommonParameters</span></span>

<span data-ttu-id="13452-229">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="13452-229">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="13452-230">Para obter mais informações, confira [about_CommonParameters](./About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="13452-230">For more information, see [about_CommonParameters](./About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="13452-231">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="13452-231">INPUTS</span></span>

### <span data-ttu-id="13452-232">System. Management. Automation. Job</span><span class="sxs-lookup"><span data-stu-id="13452-232">System.Management.Automation.Job</span></span>

<span data-ttu-id="13452-233">Você pode canalizar objetos de trabalho para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="13452-233">You can pipe job objects to this cmdlet.</span></span>

## <span data-ttu-id="13452-234">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="13452-234">OUTPUTS</span></span>

### <span data-ttu-id="13452-235">PSObject</span><span class="sxs-lookup"><span data-stu-id="13452-235">PSObject</span></span>

<span data-ttu-id="13452-236">Esse cmdlet retorna os resultados dos comandos no trabalho.</span><span class="sxs-lookup"><span data-stu-id="13452-236">This cmdlet returns the results of the commands in the job.</span></span>

## <span data-ttu-id="13452-237">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="13452-237">NOTES</span></span>

## <span data-ttu-id="13452-238">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="13452-238">RELATED LINKS</span></span>

[<span data-ttu-id="13452-239">Get-Job</span><span class="sxs-lookup"><span data-stu-id="13452-239">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="13452-240">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="13452-240">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="13452-241">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="13452-241">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="13452-242">Start-Job</span><span class="sxs-lookup"><span data-stu-id="13452-242">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="13452-243">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="13452-243">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="13452-244">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="13452-244">Wait-Job</span></span>](Wait-Job.md)
