---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/receive-job?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Receive-Job
ms.openlocfilehash: 3a11bdb27f3fe16b7b66e82821a3ffe8fa5f6cfa
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598228"
---
# <span data-ttu-id="78346-102">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="78346-102">Receive-Job</span></span>

## <span data-ttu-id="78346-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="78346-103">SYNOPSIS</span></span>
<span data-ttu-id="78346-104">Obtém os resultados dos trabalhos em segundo plano do PowerShell na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="78346-104">Gets the results of the PowerShell background jobs in the current session.</span></span>

## <span data-ttu-id="78346-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="78346-105">SYNTAX</span></span>

### <span data-ttu-id="78346-106">Local (padrão)</span><span class="sxs-lookup"><span data-stu-id="78346-106">Location (Default)</span></span>

```
Receive-Job [-Job] <Job[]> [[-Location] <String[]>] [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob]
 [-WriteEvents] [-WriteJobInResults] [<CommonParameters>]
```

### <span data-ttu-id="78346-107">ComputerName</span><span class="sxs-lookup"><span data-stu-id="78346-107">ComputerName</span></span>

```
Receive-Job [-Job] <Job[]> [[-ComputerName] <String[]>] [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob]
 [-WriteEvents] [-WriteJobInResults] [<CommonParameters>]
```

### <span data-ttu-id="78346-108">Sessão</span><span class="sxs-lookup"><span data-stu-id="78346-108">Session</span></span>

```
Receive-Job [-Job] <Job[]> [[-Session] <PSSession[]>] [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob]
 [-WriteEvents] [-WriteJobInResults] [<CommonParameters>]
```

### <span data-ttu-id="78346-109">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="78346-109">NameParameterSet</span></span>

```
Receive-Job [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob] [-WriteEvents] [-WriteJobInResults]
 [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="78346-110">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="78346-110">InstanceIdParameterSet</span></span>

```
Receive-Job [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob] [-WriteEvents] [-WriteJobInResults]
 [-InstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="78346-111">SessionIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="78346-111">SessionIdParameterSet</span></span>

```
Receive-Job [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob] [-WriteEvents] [-WriteJobInResults]
 [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="78346-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="78346-112">DESCRIPTION</span></span>

<span data-ttu-id="78346-113">O `Receive-Job` cmdlet obtém os resultados de trabalhos em segundo plano do PowerShell, como aqueles iniciados usando o `Start-Job` cmdlet ou o parâmetro **AsJob** de qualquer cmdlet.</span><span class="sxs-lookup"><span data-stu-id="78346-113">The `Receive-Job` cmdlet gets the results of PowerShell background jobs, such as those started by using the `Start-Job` cmdlet or the **AsJob** parameter of any cmdlet.</span></span>
<span data-ttu-id="78346-114">Você pode obter os resultados de todos os trabalhos ou identificar trabalhos pelo nome, ID, ID de instância, nome do computador, local ou sessão ou enviando um objeto de trabalho.</span><span class="sxs-lookup"><span data-stu-id="78346-114">You can get the results of all jobs or identify jobs by their name, ID, instance ID, computer name, location, or session, or by submitting a job object.</span></span>

<span data-ttu-id="78346-115">Quando você inicia um trabalho em segundo plano do PowerShell, o trabalho é iniciado, mas os resultados não aparecem imediatamente.</span><span class="sxs-lookup"><span data-stu-id="78346-115">When you start a PowerShell background job, the job starts, but the results do not appear immediately.</span></span> <span data-ttu-id="78346-116">Em vez disso, o comando retorna um objeto que representa o trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="78346-116">Instead, the command returns an object that represents the background job.</span></span>
<span data-ttu-id="78346-117">O objeto de trabalho contém informações úteis sobre o trabalho, mas não contém os resultados.</span><span class="sxs-lookup"><span data-stu-id="78346-117">The job object contains useful information about the job, but it does not contain the results.</span></span>
<span data-ttu-id="78346-118">Esse método permite que você continue a trabalhar na sessão enquanto o trabalho é executado.</span><span class="sxs-lookup"><span data-stu-id="78346-118">This method lets you continue to work in the session while the job runs.</span></span>
<span data-ttu-id="78346-119">Para obter mais informações sobre trabalhos em segundo plano no PowerShell, consulte [about_Jobs](./About/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="78346-119">For more information about background jobs in PowerShell, see [about_Jobs](./About/about_Jobs.md).</span></span>

<span data-ttu-id="78346-120">O `Receive-Job` cmdlet obtém os resultados que foram gerados pela hora em que o `Receive-Job` comando foi enviado.</span><span class="sxs-lookup"><span data-stu-id="78346-120">The `Receive-Job` cmdlet gets the results that have been generated by the time that the `Receive-Job` command is submitted.</span></span>
<span data-ttu-id="78346-121">Se os resultados ainda não estiverem completos, você poderá executar `Receive-Job` comandos adicionais para obter os resultados restantes.</span><span class="sxs-lookup"><span data-stu-id="78346-121">If the results are not yet complete, you can run additional `Receive-Job` commands to get the remaining results.</span></span>

<span data-ttu-id="78346-122">Por padrão, os resultados do trabalho são excluídos do sistema quando são recebidos, mas você pode usar o parâmetro **Keep** para salvar os resultados para poder recebê-los novamente.</span><span class="sxs-lookup"><span data-stu-id="78346-122">By default, job results are deleted from the system when you receive them, but you can use the **Keep** parameter to save the results so that you can receive them again.</span></span>
<span data-ttu-id="78346-123">Para excluir os resultados do trabalho, execute o `Receive-Job` comando novamente sem o parâmetro **Keep** , feche a sessão ou use o `Remove-Job` cmdlet para excluir o trabalho da sessão.</span><span class="sxs-lookup"><span data-stu-id="78346-123">To delete the job results, run the `Receive-Job` command again without the **Keep** parameter, close the session, or use the `Remove-Job` cmdlet to delete the job from the session.</span></span>

<span data-ttu-id="78346-124">A partir do Windows PowerShell 3,0, `Receive-Job` o também obtém os resultados de tipos de trabalho personalizados, como trabalhos de workflow e instâncias de trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="78346-124">Starting in Windows PowerShell 3.0, `Receive-Job` also gets the results of custom job types, such as workflow jobs and instances of scheduled jobs.</span></span>
<span data-ttu-id="78346-125">Para habilitar `Receive-Job` o a fim de obter os resultados de um tipo de trabalho personalizado, importe o módulo que dá suporte ao tipo de trabalho personalizado na sessão antes de executar um `Receive-Job` comando, seja usando o `Import-Module` cmdlet ou obtendo um cmdlet no módulo.</span><span class="sxs-lookup"><span data-stu-id="78346-125">To enable `Receive-Job` to get the results a custom job type, import the module that supports the custom job type into the session before it runs a `Receive-Job` command, either by using the `Import-Module` cmdlet or by using or getting a cmdlet in the module.</span></span>
<span data-ttu-id="78346-126">Para obter informações sobre um tipo específico de trabalho personalizado, consulte a documentação do recurso de tipo de trabalho personalizado.</span><span class="sxs-lookup"><span data-stu-id="78346-126">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="78346-127">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="78346-127">EXAMPLES</span></span>

### <span data-ttu-id="78346-128">Exemplo 1: obter resultados para um trabalho específico</span><span class="sxs-lookup"><span data-stu-id="78346-128">Example 1: Get results for a particular job</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Process}
Receive-Job -Job $job
```

<span data-ttu-id="78346-129">Esses comandos usam o parâmetro de **trabalho** de `Receive-Job` para obter os resultados de um trabalho específico.</span><span class="sxs-lookup"><span data-stu-id="78346-129">These commands use the **Job** parameter of `Receive-Job` to get the results of a particular job.</span></span>

<span data-ttu-id="78346-130">O primeiro comando inicia um trabalho com `Start-Job` e armazena o objeto de trabalho na `$job` variável.</span><span class="sxs-lookup"><span data-stu-id="78346-130">The first command starts a job with `Start-Job` and stores the job object in the `$job` variable.</span></span>

<span data-ttu-id="78346-131">O segundo comando usa o `Receive-Job` cmdlet para obter os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="78346-131">The second command uses the `Receive-Job` cmdlet to get the results of the job.</span></span>
<span data-ttu-id="78346-132">Ele usa o parâmetro **Job** para especificar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="78346-132">It uses the **Job** parameter to specify the job.</span></span>

### <span data-ttu-id="78346-133">Exemplo 2: usar o parâmetro Keep</span><span class="sxs-lookup"><span data-stu-id="78346-133">Example 2: Use the Keep parameter</span></span>

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

<span data-ttu-id="78346-134">Este exemplo armazena um trabalho na `$job` variável e canaliza o trabalho para o `Receive-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="78346-134">This example stores a job in the `$job` variable, and pipes the job to the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="78346-135">O `-Keep` parâmetro também é usado para permitir que todos os dados de fluxo agregados sejam recuperados novamente após a primeira exibição.</span><span class="sxs-lookup"><span data-stu-id="78346-135">The `-Keep` parameter is also used to allow all aggregated stream data to be retrieved again after first view.</span></span>

### <span data-ttu-id="78346-136">Exemplo 3: obter resultados de vários trabalhos em segundo plano</span><span class="sxs-lookup"><span data-stu-id="78346-136">Example 3: Get results of several background jobs</span></span>

<span data-ttu-id="78346-137">Quando você usa o parâmetro **AsJob** do `Invoke-Command` para iniciar um trabalho, o objeto de trabalho é criado no computador local, embora o trabalho seja executado nos computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="78346-137">When you use the **AsJob** parameter of `Invoke-Command` to start a job, the job object is created on the local computer, even though the job runs on the remote computers.</span></span>
<span data-ttu-id="78346-138">Como resultado, você deve usar comandos locais para gerenciar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="78346-138">As a result, you use local commands to manage the job.</span></span>

<span data-ttu-id="78346-139">Além disso, quando você usa **AsJob**, o PowerShell retorna um objeto de trabalho que contém um trabalho filho para cada trabalho iniciado.</span><span class="sxs-lookup"><span data-stu-id="78346-139">Also, when you use **AsJob**, PowerShell returns one job object that contains a child job for each job that was started.</span></span> <span data-ttu-id="78346-140">Nesse caso, o objeto de trabalho contém três tarefas filhas, uma para cada trabalho em cada computador remoto.</span><span class="sxs-lookup"><span data-stu-id="78346-140">In this case, the job object contains three child jobs, one for each job on each remote computer.</span></span>

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

### <span data-ttu-id="78346-141">Exemplo 4: obter resultados de trabalhos em segundo plano em vários computadores remotos</span><span class="sxs-lookup"><span data-stu-id="78346-141">Example 4: Get results of background jobs on multiple remote computers</span></span>

```powershell
# Use the New-PSSession cmdlet to create three user-managed PSSessions on three servers, and save the sessions in the $s variable.
$s = New-PSSession -ComputerName Server01, Server02, Server03
# Use Invoke-Command run a Start-Job command in each of the PSSessions in the $s variable.
# The job outputs the ComputerName of each server.
# Save the job objects in the $j variable.
$j = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {$env:COMPUTERNAME}}
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
Id   Name     State      HasMoreData   Location   Command
--   ----     -----      -----------   --------   -------
1    Job1     Completed  True          Localhost  $env:COMPUTERNAME
2    Job2     Completed  True          Localhost  $env:COMPUTERNAME
3    Job3     Completed  True          Localhost  $env:COMPUTERNAME
```

```powershell
# Use Invoke-Command to run a Receive-Job command in each of the sessions in the $s variable and save the results in the $Results variable.
# The Receive-Job command must be run in each session because the jobs were run locally on each server.
$results = Invoke-Command -Session $s -ScriptBlock {Receive-Job -Job $Using:j}
```

```Output
Server01
Server02
Server03
```

<span data-ttu-id="78346-142">Este exemplo mostra como obter os resultados de trabalhos em segundo plano executados em três computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="78346-142">This example shows how to get the results of background jobs run on three remote computers.</span></span>
<span data-ttu-id="78346-143">Ao contrário do exemplo anterior, usar `Invoke-Command` para executar o `Start-Job` comando efetivamente iniciou três trabalhos independentes em cada um dos três computadores.</span><span class="sxs-lookup"><span data-stu-id="78346-143">Unlike the previous example, using `Invoke-Command` to run the `Start-Job` command actually started three independent jobs on each of the three computers.</span></span> <span data-ttu-id="78346-144">Como resultado, o comando retornou três objetos de trabalho que representam três trabalhos executados localmente nos três computadores diferentes.</span><span class="sxs-lookup"><span data-stu-id="78346-144">As a result, the command returned three job objects representing three jobs run locally on three different computers.</span></span>

> [!NOTE]
> <span data-ttu-id="78346-145">No último comando, porque `$j` é uma variável local, o bloco de script usa o modificador de escopo de **uso** para identificar a `$j` variável.</span><span class="sxs-lookup"><span data-stu-id="78346-145">In the last command, because `$j` is a local variable, the script block uses the **Using** scope modifier to identify the `$j` variable.</span></span> <span data-ttu-id="78346-146">Para obter mais informações sobre o modificador de escopo de **uso** , consulte [about_Remote_Variables](./About/about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="78346-146">For more information about the **Using** scope modifier, see [about_Remote_Variables](./About/about_Remote_Variables.md).</span></span>

### <span data-ttu-id="78346-147">Exemplo 5: acessar trabalhos filho</span><span class="sxs-lookup"><span data-stu-id="78346-147">Example 5: Access child jobs</span></span>

<span data-ttu-id="78346-148">O `-Keep` parâmetro preserva o estado dos fluxos agregados de um trabalho para que ele possa ser exibido novamente.</span><span class="sxs-lookup"><span data-stu-id="78346-148">The `-Keep` parameter preserves the state of the aggregated streams of a job so that it can be viewed again.</span></span> <span data-ttu-id="78346-149">Sem esse parâmetro, todos os dados de fluxo agregados são apagados quando o trabalho é recebido.</span><span class="sxs-lookup"><span data-stu-id="78346-149">Without this parameter all aggregated stream data is erased when the job is received.</span></span> <span data-ttu-id="78346-150">Para obter mais informações, consulte [about_Job_Details](About/about_Job_Details.md#child-jobs)</span><span class="sxs-lookup"><span data-stu-id="78346-150">For more information, see [about_Job_Details](About/about_Job_Details.md#child-jobs)</span></span>

> [!NOTE]
> <span data-ttu-id="78346-151">Os fluxos agregados incluem os fluxos de todos os trabalhos filho.</span><span class="sxs-lookup"><span data-stu-id="78346-151">The aggregated streams include the streams of all child jobs.</span></span> <span data-ttu-id="78346-152">Você ainda pode acessar os fluxos de dados individuais por meio do objeto de trabalho e dos objetos de trabalho filho.</span><span class="sxs-lookup"><span data-stu-id="78346-152">You can still reach the individual streams of data through the job object and child job objects.</span></span>

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

## <span data-ttu-id="78346-153">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="78346-153">PARAMETERS</span></span>

### <span data-ttu-id="78346-154">-AutoRemoveJob</span><span class="sxs-lookup"><span data-stu-id="78346-154">-AutoRemoveJob</span></span>

<span data-ttu-id="78346-155">Indica que esse cmdlet exclui o trabalho depois de retornar os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="78346-155">Indicates that this cmdlet deletes the job after it returns the job results.</span></span>
<span data-ttu-id="78346-156">Se o trabalho tiver mais resultados, o trabalho ainda será excluído, mas `Receive-Job` exibirá uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="78346-156">If the job has more results, the job is still deleted, but `Receive-Job` displays a message.</span></span>

<span data-ttu-id="78346-157">Esse parâmetro só funciona em tipos de trabalho personalizados.</span><span class="sxs-lookup"><span data-stu-id="78346-157">This parameter works only on custom job types.</span></span>
<span data-ttu-id="78346-158">Ele é projetado para instâncias de tipos de trabalho que salvam o trabalho ou o tipo fora da sessão, como instâncias de trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="78346-158">It is designed for instances of job types that save the job or the type outside of the session, such as instances of scheduled jobs.</span></span>

<span data-ttu-id="78346-159">Esse parâmetro não pode ser usado sem o parâmetro **Wait** .</span><span class="sxs-lookup"><span data-stu-id="78346-159">This parameter cannot be used without the **Wait** parameter.</span></span>

<span data-ttu-id="78346-160">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="78346-160">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="78346-161">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="78346-161">-ComputerName</span></span>

<span data-ttu-id="78346-162">Especifica uma matriz de nomes de computadores.</span><span class="sxs-lookup"><span data-stu-id="78346-162">Specifies an array of names of computers.</span></span>

<span data-ttu-id="78346-163">Esse parâmetro seleciona entre os resultados do trabalho que estão armazenados no computador local.</span><span class="sxs-lookup"><span data-stu-id="78346-163">This parameter selects from among the job results that are stored on the local computer.</span></span>
<span data-ttu-id="78346-164">Ele não obtém dados para trabalhos executados em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="78346-164">It does not get data for jobs run on remote computers.</span></span>
<span data-ttu-id="78346-165">Para obter os resultados do trabalho armazenados em computadores remotos, use o `Invoke-Command` cmdlet para executar um `Receive-Job` comando remotamente.</span><span class="sxs-lookup"><span data-stu-id="78346-165">To get job results that are stored on remote computers, use the `Invoke-Command` cmdlet to run a `Receive-Job` command remotely.</span></span>

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

### <span data-ttu-id="78346-166">-Force</span><span class="sxs-lookup"><span data-stu-id="78346-166">-Force</span></span>

<span data-ttu-id="78346-167">Indica que esse cmdlet continuará aguardando se os trabalhos estiverem no estado **suspenso** ou **desconectado** .</span><span class="sxs-lookup"><span data-stu-id="78346-167">Indicates that this cmdlet continues waiting if jobs are in the **Suspended** or **Disconnected** state.</span></span> <span data-ttu-id="78346-168">Por padrão, o parâmetro **Wait** de `Receive-Job` retorna ou encerra a espera, quando os trabalhos estão em um dos seguintes Estados:</span><span class="sxs-lookup"><span data-stu-id="78346-168">By default, the **Wait** parameter of `Receive-Job` returns, or terminates the wait, when jobs are in one of the following states:</span></span>

- <span data-ttu-id="78346-169">Concluído</span><span class="sxs-lookup"><span data-stu-id="78346-169">Completed</span></span>
- <span data-ttu-id="78346-170">Falhou</span><span class="sxs-lookup"><span data-stu-id="78346-170">Failed</span></span>
- <span data-ttu-id="78346-171">Parado</span><span class="sxs-lookup"><span data-stu-id="78346-171">Stopped</span></span>
- <span data-ttu-id="78346-172">Suspenso</span><span class="sxs-lookup"><span data-stu-id="78346-172">Suspended</span></span>
- <span data-ttu-id="78346-173">Desconectado</span><span class="sxs-lookup"><span data-stu-id="78346-173">Disconnected.</span></span>

<span data-ttu-id="78346-174">O parâmetro **Force** é válido somente quando o parâmetro **Wait** também é usado no comando.</span><span class="sxs-lookup"><span data-stu-id="78346-174">The **Force** parameter is valid only when the **Wait** parameter is also used in the command.</span></span>

<span data-ttu-id="78346-175">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="78346-175">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="78346-176">-Id</span><span class="sxs-lookup"><span data-stu-id="78346-176">-Id</span></span>

<span data-ttu-id="78346-177">Especifica uma matriz de IDs.</span><span class="sxs-lookup"><span data-stu-id="78346-177">Specifies an array of IDs.</span></span>
<span data-ttu-id="78346-178">Esse cmdlet obtém os resultados de trabalhos com as IDs especificadas.</span><span class="sxs-lookup"><span data-stu-id="78346-178">This cmdlet gets the results of jobs with the specified IDs.</span></span>

<span data-ttu-id="78346-179">A ID é um inteiro que identifica exclusivamente o trabalho na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="78346-179">The ID is an integer that uniquely identifies the job in the current session.</span></span>
<span data-ttu-id="78346-180">É mais fácil lembrar e digitar do que a ID da instância, mas só é exclusiva na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="78346-180">It is easier to remember and type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="78346-181">Você pode digitar uma ou mais IDs separadas por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="78346-181">You can type one or more IDs separated by commas.</span></span>
<span data-ttu-id="78346-182">Para localizar a ID de um trabalho, use `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="78346-182">To find the ID of a job, use `Get-Job`.</span></span>

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

### <span data-ttu-id="78346-183">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="78346-183">-InstanceId</span></span>

<span data-ttu-id="78346-184">Especifica uma matriz de IDs de instância.</span><span class="sxs-lookup"><span data-stu-id="78346-184">Specifies an array of instance IDs.</span></span>
<span data-ttu-id="78346-185">Esse cmdlet obtém os resultados de trabalhos com as IDs de instância especificadas.</span><span class="sxs-lookup"><span data-stu-id="78346-185">This cmdlet gets the results of jobs with the specified instance IDs.</span></span>

<span data-ttu-id="78346-186">Uma ID de instância é um GUID que identifica exclusivamente o trabalho no computador.</span><span class="sxs-lookup"><span data-stu-id="78346-186">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span>
<span data-ttu-id="78346-187">Para localizar a ID de instância de um trabalho, use o `Get-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="78346-187">To find the instance ID of a job, use the `Get-Job` cmdlet.</span></span>

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

### <span data-ttu-id="78346-188">-Trabalho</span><span class="sxs-lookup"><span data-stu-id="78346-188">-Job</span></span>

<span data-ttu-id="78346-189">Especifica o trabalho para o qual os resultados estão sendo recuperados.</span><span class="sxs-lookup"><span data-stu-id="78346-189">Specifies the job for which results are being retrieved.</span></span>

<span data-ttu-id="78346-190">Insira uma variável que contenha o trabalho ou um comando que obtenha o trabalho.</span><span class="sxs-lookup"><span data-stu-id="78346-190">Enter a variable that contains the job or a command that gets the job.</span></span>
<span data-ttu-id="78346-191">Também é possível canalizar um objeto de trabalho para `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="78346-191">You can also pipe a job object to `Receive-Job`.</span></span>

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

### <span data-ttu-id="78346-192">-Manter</span><span class="sxs-lookup"><span data-stu-id="78346-192">-Keep</span></span>

<span data-ttu-id="78346-193">Indica que esse cmdlet salva os dados de fluxo agregados no sistema, mesmo depois de você tê-los recebido.</span><span class="sxs-lookup"><span data-stu-id="78346-193">Indicates that this cmdlet saves the aggregated stream data in the system, even after you have received them.</span></span> <span data-ttu-id="78346-194">Por padrão, os dados de fluxo agregados são apagados depois de exibidos com `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="78346-194">By default, aggregated stream data is erased after viewed with `Receive-Job`.</span></span>

<span data-ttu-id="78346-195">Fechar a sessão ou remover o trabalho com o `Remove-Job` cmdlet também exclui dados de fluxo agregados.</span><span class="sxs-lookup"><span data-stu-id="78346-195">Closing the session, or removing the job with the `Remove-Job` cmdlet also deletes aggregated stream data.</span></span>

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

### <span data-ttu-id="78346-196">-Local</span><span class="sxs-lookup"><span data-stu-id="78346-196">-Location</span></span>

<span data-ttu-id="78346-197">Especifica uma matriz de locais.</span><span class="sxs-lookup"><span data-stu-id="78346-197">Specifies an array of locations.</span></span>
<span data-ttu-id="78346-198">Esse cmdlet obtém apenas os resultados de trabalhos nos locais especificados.</span><span class="sxs-lookup"><span data-stu-id="78346-198">This cmdlet gets only the results of jobs in the specified locations.</span></span>

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

### <span data-ttu-id="78346-199">-Name</span><span class="sxs-lookup"><span data-stu-id="78346-199">-Name</span></span>

<span data-ttu-id="78346-200">Especifica uma matriz de nomes amigáveis.</span><span class="sxs-lookup"><span data-stu-id="78346-200">Specifies an array of friendly names.</span></span>
<span data-ttu-id="78346-201">Esse cmdlet obtém os resultados de trabalhos que têm os nomes especificados.</span><span class="sxs-lookup"><span data-stu-id="78346-201">This cmdlet gets the results of jobs that have the specified names.</span></span>
<span data-ttu-id="78346-202">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="78346-202">Wildcard characters are supported.</span></span>

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

### <span data-ttu-id="78346-203">-Recorrência</span><span class="sxs-lookup"><span data-stu-id="78346-203">-NoRecurse</span></span>

<span data-ttu-id="78346-204">Indica que esse cmdlet obtém resultados apenas do trabalho especificado.</span><span class="sxs-lookup"><span data-stu-id="78346-204">Indicates that this cmdlet gets results only from the specified job.</span></span>
<span data-ttu-id="78346-205">Por padrão, `Receive-Job` o também obtém os resultados de todos os trabalhos filho do trabalho especificado.</span><span class="sxs-lookup"><span data-stu-id="78346-205">By default, `Receive-Job` also gets the results of all child jobs of the specified job.</span></span>

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

### <span data-ttu-id="78346-206">-Sessão</span><span class="sxs-lookup"><span data-stu-id="78346-206">-Session</span></span>

<span data-ttu-id="78346-207">Especifica uma matriz de sessões.</span><span class="sxs-lookup"><span data-stu-id="78346-207">Specifies an array of sessions.</span></span>
<span data-ttu-id="78346-208">Esse cmdlet obtém os resultados de trabalhos que foram executados na sessão do PowerShell especificada (**PSSession**).</span><span class="sxs-lookup"><span data-stu-id="78346-208">This cmdlet gets the results of jobs that were run in the specified PowerShell session (**PSSession**).</span></span>
<span data-ttu-id="78346-209">Insira uma variável que contém a **PSSession** ou um comando que obtém a **PSSession**, como um `Get-PSSession` comando.</span><span class="sxs-lookup"><span data-stu-id="78346-209">Enter a variable that contains the **PSSession** or a command that gets the **PSSession**, such as a `Get-PSSession` command.</span></span>

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

### <span data-ttu-id="78346-210">-Wait</span><span class="sxs-lookup"><span data-stu-id="78346-210">-Wait</span></span>

<span data-ttu-id="78346-211">Indica que esse cmdlet suprime o prompt de comando até que todos os resultados do trabalho sejam recebidos.</span><span class="sxs-lookup"><span data-stu-id="78346-211">Indicates that this cmdlet suppresses the command prompt until all job results are received.</span></span>
<span data-ttu-id="78346-212">Por padrão, `Receive-Job` o retorna imediatamente os resultados disponíveis.</span><span class="sxs-lookup"><span data-stu-id="78346-212">By default, `Receive-Job` immediately returns the available results.</span></span>

<span data-ttu-id="78346-213">Por padrão, o parâmetro **Wait** aguarda até que o trabalho esteja em um dos seguintes estados:</span><span class="sxs-lookup"><span data-stu-id="78346-213">By default, the **Wait** parameter waits until the job is in one of the following states:</span></span>

- <span data-ttu-id="78346-214">Concluído</span><span class="sxs-lookup"><span data-stu-id="78346-214">Completed</span></span>
- <span data-ttu-id="78346-215">Falhou</span><span class="sxs-lookup"><span data-stu-id="78346-215">Failed</span></span>
- <span data-ttu-id="78346-216">Parado</span><span class="sxs-lookup"><span data-stu-id="78346-216">Stopped</span></span>
- <span data-ttu-id="78346-217">Suspenso</span><span class="sxs-lookup"><span data-stu-id="78346-217">Suspended</span></span>
- <span data-ttu-id="78346-218">Desconectado</span><span class="sxs-lookup"><span data-stu-id="78346-218">Disconnected.</span></span>

<span data-ttu-id="78346-219">Para direcionar o parâmetro **Wait** para continuar aguardando se o estado do trabalho for suspenso ou desconectado, use o parâmetro **Force** junto com o parâmetro **Wait** .</span><span class="sxs-lookup"><span data-stu-id="78346-219">To direct the **Wait** parameter to continue waiting if the job state is Suspended or Disconnected, use the **Force** parameter together with the **Wait** parameter.</span></span>

<span data-ttu-id="78346-220">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="78346-220">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="78346-221">-WriteEvents</span><span class="sxs-lookup"><span data-stu-id="78346-221">-WriteEvents</span></span>

<span data-ttu-id="78346-222">Indica que esse cmdlet relata alterações no estado do trabalho enquanto aguarda a conclusão do trabalho.</span><span class="sxs-lookup"><span data-stu-id="78346-222">Indicates that this cmdlet reports changes in the job state while it waits for the job to finish.</span></span>

<span data-ttu-id="78346-223">Esse parâmetro é válido somente quando o parâmetro **Wait** é usado no comando e o parâmetro **Keep** é omitido.</span><span class="sxs-lookup"><span data-stu-id="78346-223">This parameter is valid only when the **Wait** parameter is used in the command and the **Keep** parameter is omitted.</span></span>

<span data-ttu-id="78346-224">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="78346-224">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="78346-225">-WriteJobInResults</span><span class="sxs-lookup"><span data-stu-id="78346-225">-WriteJobInResults</span></span>

<span data-ttu-id="78346-226">Indica que esse cmdlet retorna o objeto de trabalho seguido pelos resultados.</span><span class="sxs-lookup"><span data-stu-id="78346-226">Indicates that this cmdlet returns the job object followed by the results.</span></span>

<span data-ttu-id="78346-227">Esse parâmetro é válido somente quando o parâmetro **Wait** é usado no comando e o parâmetro **Keep** é omitido.</span><span class="sxs-lookup"><span data-stu-id="78346-227">This parameter is valid only when the **Wait** parameter is used in the command and the **Keep** parameter is omitted.</span></span>

<span data-ttu-id="78346-228">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="78346-228">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="78346-229">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="78346-229">CommonParameters</span></span>

<span data-ttu-id="78346-230">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="78346-230">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="78346-231">Para obter mais informações, confira [about_CommonParameters](./About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="78346-231">For more information, see [about_CommonParameters](./About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="78346-232">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="78346-232">INPUTS</span></span>

### <span data-ttu-id="78346-233">System. Management. Automation. Job</span><span class="sxs-lookup"><span data-stu-id="78346-233">System.Management.Automation.Job</span></span>

<span data-ttu-id="78346-234">Você pode canalizar objetos de trabalho para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="78346-234">You can pipe job objects to this cmdlet.</span></span>

## <span data-ttu-id="78346-235">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="78346-235">OUTPUTS</span></span>

### <span data-ttu-id="78346-236">PSObject</span><span class="sxs-lookup"><span data-stu-id="78346-236">PSObject</span></span>

<span data-ttu-id="78346-237">Esse cmdlet retorna os resultados dos comandos no trabalho.</span><span class="sxs-lookup"><span data-stu-id="78346-237">This cmdlet returns the results of the commands in the job.</span></span>

## <span data-ttu-id="78346-238">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="78346-238">NOTES</span></span>

## <span data-ttu-id="78346-239">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="78346-239">RELATED LINKS</span></span>

[<span data-ttu-id="78346-240">Get-Job</span><span class="sxs-lookup"><span data-stu-id="78346-240">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="78346-241">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="78346-241">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="78346-242">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="78346-242">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="78346-243">Start-Job</span><span class="sxs-lookup"><span data-stu-id="78346-243">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="78346-244">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="78346-244">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="78346-245">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="78346-245">Wait-Job</span></span>](Wait-Job.md)

