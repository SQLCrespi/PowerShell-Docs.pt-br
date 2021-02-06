---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/stop-job?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Job
ms.openlocfilehash: 479c099d2d5daf1cc50c5c645be053ff4ae02bdc
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603763"
---
# <span data-ttu-id="fbba3-102">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="fbba3-102">Stop-Job</span></span>

## <span data-ttu-id="fbba3-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="fbba3-103">SYNOPSIS</span></span>
<span data-ttu-id="fbba3-104">Interrompe um trabalho em segundo plano do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fbba3-104">Stops a PowerShell background job.</span></span>

## <span data-ttu-id="fbba3-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fbba3-105">SYNTAX</span></span>

### <span data-ttu-id="fbba3-106">SessionIdParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="fbba3-106">SessionIdParameterSet (Default)</span></span>

```
Stop-Job [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="fbba3-107">JobParameterSet</span><span class="sxs-lookup"><span data-stu-id="fbba3-107">JobParameterSet</span></span>

```
Stop-Job [-Job] <Job[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="fbba3-108">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="fbba3-108">NameParameterSet</span></span>

```
Stop-Job [-PassThru] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="fbba3-109">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="fbba3-109">InstanceIdParameterSet</span></span>

```
Stop-Job [-PassThru] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="fbba3-110">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="fbba3-110">StateParameterSet</span></span>

```
Stop-Job [-PassThru] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="fbba3-111">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="fbba3-111">FilterParameterSet</span></span>

```
Stop-Job [-PassThru] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="fbba3-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fbba3-112">DESCRIPTION</span></span>

<span data-ttu-id="fbba3-113">O `Stop-Job` cmdlet interrompe os trabalhos em segundo plano do PowerShell que estão em andamento.</span><span class="sxs-lookup"><span data-stu-id="fbba3-113">The `Stop-Job` cmdlet stops PowerShell background jobs that are in progress.</span></span> <span data-ttu-id="fbba3-114">Você pode usar este cmdlet para interromper todos os trabalhos ou parar trabalhos selecionados com base em seu nome, ID, ID de instância ou estado ou passando um objeto de trabalho para `Stop-Job` .</span><span class="sxs-lookup"><span data-stu-id="fbba3-114">You can use this cmdlet to stop all jobs or stop selected jobs based on their name, ID, instance ID, or state, or by passing a job object to `Stop-Job`.</span></span>

<span data-ttu-id="fbba3-115">Você pode usar `Stop-Job` para interromper trabalhos em segundo plano, como aqueles que foram iniciados usando `Start-Job` o cmdlet ou o parâmetro **AsJob** de qualquer cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fbba3-115">You can use `Stop-Job` to stop background jobs, such as those that were started by using the `Start-Job` cmdlet or the **AsJob** parameter of any cmdlet.</span></span> <span data-ttu-id="fbba3-116">Quando você interrompe um trabalho em segundo plano, o PowerShell conclui todas as tarefas que estão pendentes na fila de trabalho e, em seguida, encerra o trabalho.</span><span class="sxs-lookup"><span data-stu-id="fbba3-116">When you stop a background job, PowerShell completes all tasks that are pending in that job queue and then ends the job.</span></span> <span data-ttu-id="fbba3-117">Nenhuma tarefa nova é adicionada à fila depois que esse comando é enviado.</span><span class="sxs-lookup"><span data-stu-id="fbba3-117">No new tasks are added to the queue after this command is submitted.</span></span>

<span data-ttu-id="fbba3-118">Esse cmdlet não exclui os trabalhos em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="fbba3-118">This cmdlet does not delete background jobs.</span></span> <span data-ttu-id="fbba3-119">Para excluir um trabalho, use o `Remove-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fbba3-119">To delete a job, use the `Remove-Job` cmdlet.</span></span>

<span data-ttu-id="fbba3-120">A partir do Windows PowerShell 3,0, `Stop-Job` o também interrompe os tipos de trabalho personalizados, como trabalhos de workflow e instâncias de trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="fbba3-120">Starting in Windows PowerShell 3.0, `Stop-Job` also stops custom job types, such as workflow jobs and instances of scheduled jobs.</span></span> <span data-ttu-id="fbba3-121">Para habilitar o `Stop-Job` para parar um trabalho com o tipo de trabalho personalizado, importe o módulo que dá suporte ao tipo de trabalho personalizado na sessão antes de executar um `Stop-Job` comando, seja usando o `Import-Module` cmdlet ou obtendo um cmdlet no módulo.</span><span class="sxs-lookup"><span data-stu-id="fbba3-121">To enable `Stop-Job` to stop a job with custom job type, import the module that supports the custom job type into the session before you run a `Stop-Job` command, either by using the `Import-Module` cmdlet or by using or getting a cmdlet in the module.</span></span> <span data-ttu-id="fbba3-122">Para obter informações sobre um tipo específico de trabalho personalizado, consulte a documentação do recurso de tipo de trabalho personalizado.</span><span class="sxs-lookup"><span data-stu-id="fbba3-122">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="fbba3-123">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="fbba3-123">EXAMPLES</span></span>

### <span data-ttu-id="fbba3-124">Exemplo 1: parar um trabalho em um computador remoto usando Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="fbba3-124">Example 1: Stop a job on a remote computer by using Invoke-Command</span></span>

```powershell
$s = New-PSSession -ComputerName Server01 -Credential Domain01\Admin02
$j = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Invoke-Command -Session $s -ScriptBlock { Stop-job -Job $Using:j }
```

<span data-ttu-id="fbba3-125">Este exemplo mostra como usar o `Stop-Job` cmdlet para interromper um trabalho que está sendo executado em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="fbba3-125">This example shows how to use the `Stop-Job` cmdlet to stop a job that is running on a remote computer.</span></span>

<span data-ttu-id="fbba3-126">Como o trabalho foi iniciado usando o `Invoke-Command` cmdlet para executar um `Start-Job` comando remotamente, o objeto de trabalho é armazenado no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="fbba3-126">Because the job was started by using the `Invoke-Command` cmdlet to run a `Start-Job` command remotely, the job object is stored on the remote computer.</span></span> <span data-ttu-id="fbba3-127">Você deve usar outro `Invoke-Command` comando para executar um `Stop-Job` comando remotamente.</span><span class="sxs-lookup"><span data-stu-id="fbba3-127">You must use another `Invoke-Command` command to run a `Stop-Job` command remotely.</span></span> <span data-ttu-id="fbba3-128">Para obter mais informações sobre trabalhos remotos em segundo plano, consulte about_Remote_Jobs.</span><span class="sxs-lookup"><span data-stu-id="fbba3-128">For more information about remote background jobs, see about_Remote_Jobs.</span></span>

<span data-ttu-id="fbba3-129">O primeiro comando cria uma sessão do PowerShell (**PSSession**) no computador Server01 e, em seguida, armazena o objeto de sessão na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="fbba3-129">The first command creates a PowerShell session (**PSSession**) on the Server01 computer, and then stores the session object in the `$s` variable.</span></span> <span data-ttu-id="fbba3-130">O comando usa as credenciais de um administrador de domínio.</span><span class="sxs-lookup"><span data-stu-id="fbba3-130">The command uses the credentials of a domain administrator.</span></span>

<span data-ttu-id="fbba3-131">O segundo comando usa o `Invoke-Command` cmdlet para executar um `Start-Job` comando na sessão.</span><span class="sxs-lookup"><span data-stu-id="fbba3-131">The second command uses the `Invoke-Command` cmdlet to run a `Start-Job` command in the session.</span></span> <span data-ttu-id="fbba3-132">O comando no trabalho obtém todos os eventos no log de eventos do Sistema.</span><span class="sxs-lookup"><span data-stu-id="fbba3-132">The command in the job gets all of the events in the System event log.</span></span> <span data-ttu-id="fbba3-133">O objeto de trabalho resultante é armazenado na `$j` variável.</span><span class="sxs-lookup"><span data-stu-id="fbba3-133">The resulting job object is stored in the `$j` variable.</span></span>

<span data-ttu-id="fbba3-134">O terceiro comando interrompe o trabalho.</span><span class="sxs-lookup"><span data-stu-id="fbba3-134">The third command stops the job.</span></span> <span data-ttu-id="fbba3-135">Ele usa o `Invoke-Command` cmdlet para executar um `Stop-Job` comando em **PSSession** no Server01.</span><span class="sxs-lookup"><span data-stu-id="fbba3-135">It uses the `Invoke-Command` cmdlet to run a `Stop-Job` command in the **PSSession** on Server01.</span></span> <span data-ttu-id="fbba3-136">Como os objetos de trabalho são armazenados em `$j` , que é uma variável no computador local, o comando usa o modificador de escopo de uso para identificar `$j` como uma variável local.</span><span class="sxs-lookup"><span data-stu-id="fbba3-136">Because the job objects are stored in `$j`, which is a variable on the local computer, the command uses the Using scope modifier to identify `$j` as a local variable.</span></span>
<span data-ttu-id="fbba3-137">Para obter mais informações sobre o modificador de escopo de uso, consulte [about_Remote_Variables](about/about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="fbba3-137">For more information about the Using scope modifier, see [about_Remote_Variables](about/about_Remote_Variables.md).</span></span>

<span data-ttu-id="fbba3-138">Quando o comando for concluído, o trabalho será interrompido e a **PSSession** no `$s` estará disponível para uso.</span><span class="sxs-lookup"><span data-stu-id="fbba3-138">When the command finishes, the job is stopped and the **PSSession** in `$s` is available for use.</span></span>

### <span data-ttu-id="fbba3-139">Exemplo 2: parar um trabalho em segundo plano</span><span class="sxs-lookup"><span data-stu-id="fbba3-139">Example 2: Stop a background job</span></span>

```powershell
Stop-Job -Name "Job1"
```

<span data-ttu-id="fbba3-140">Esse comando interrompe o trabalho de plano de fundo Job1.</span><span class="sxs-lookup"><span data-stu-id="fbba3-140">This command stops the Job1 background job.</span></span>

### <span data-ttu-id="fbba3-141">Exemplo 3: parar vários trabalhos em segundo plano</span><span class="sxs-lookup"><span data-stu-id="fbba3-141">Example 3: Stop several background jobs</span></span>

```powershell
Stop-Job -Id 1, 3, 4
```

<span data-ttu-id="fbba3-142">Esse comando interrompe três trabalhos.</span><span class="sxs-lookup"><span data-stu-id="fbba3-142">This command stops three jobs.</span></span>
<span data-ttu-id="fbba3-143">Ele os identifica por suas IDs.</span><span class="sxs-lookup"><span data-stu-id="fbba3-143">It identifies them by their IDs.</span></span>

### <span data-ttu-id="fbba3-144">Exemplo 4: parar todos os trabalhos em segundo plano</span><span class="sxs-lookup"><span data-stu-id="fbba3-144">Example 4: Stop all background jobs</span></span>

```powershell
Get-Job | Stop-Job
```

<span data-ttu-id="fbba3-145">Esse comando interrompe todos os trabalhos de segundo plano na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="fbba3-145">This command stops all of the background jobs in the current session.</span></span>

### <span data-ttu-id="fbba3-146">Exemplo 5: parar todos os trabalhos em segundo plano bloqueados</span><span class="sxs-lookup"><span data-stu-id="fbba3-146">Example 5: Stop all blocked background jobs</span></span>

```powershell
Stop-Job -State Blocked
```

<span data-ttu-id="fbba3-147">Esse comando interrompe todos os trabalhos que estão bloqueados.</span><span class="sxs-lookup"><span data-stu-id="fbba3-147">This command stops all the jobs that are blocked.</span></span>

### <span data-ttu-id="fbba3-148">Exemplo 6: parar um trabalho usando uma ID de instância</span><span class="sxs-lookup"><span data-stu-id="fbba3-148">Example 6: Stop a job by using an instance ID</span></span>

```powershell
Get-Job | Format-Table ID, Name, Command, @{Label="State";Expression={$_.JobStateInfo.State}},
InstanceID -Auto
```

```Output
Id Name Command                 State  InstanceId
-- ---- -------                 -----  ----------
1 Job1 start-service schedule Running 05abb67a-2932-4bd5-b331-c0254b8d9146
3 Job3 start-service schedule Running c03cbd45-19f3-4558-ba94-ebe41b68ad03
5 Job5 get-service s*         Blocked e3bbfed1-9c53-401a-a2c3-a8db34336adf
```

```powershell
Stop-Job -InstanceId e3bbfed1-9c53-401a-a2c3-a8db34336adf
```

<span data-ttu-id="fbba3-149">Esses comandos mostram como interromper um trabalho com base em sua ID de instância.</span><span class="sxs-lookup"><span data-stu-id="fbba3-149">These commands show how to stop a job based on its instance ID.</span></span>

<span data-ttu-id="fbba3-150">O primeiro comando usa o `Get-Job` cmdlet para obter os trabalhos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="fbba3-150">The first command uses the `Get-Job` cmdlet to get the jobs in the current session.</span></span> <span data-ttu-id="fbba3-151">O comando usa um operador de pipeline ( `|` ) para enviar os trabalhos para um `Format-Table` comando, que exibe uma tabela das propriedades especificadas de cada trabalho.</span><span class="sxs-lookup"><span data-stu-id="fbba3-151">The command uses a pipeline operator (`|`) to send the jobs to a `Format-Table` command, which displays a table of the specified properties of each job.</span></span> <span data-ttu-id="fbba3-152">A tabela inclui a ID da instância de cada trabalho.</span><span class="sxs-lookup"><span data-stu-id="fbba3-152">The table includes the Instance ID of each job.</span></span> <span data-ttu-id="fbba3-153">Ele usa uma propriedade calculada para exibir o estado do trabalho.</span><span class="sxs-lookup"><span data-stu-id="fbba3-153">It uses a calculated property to display the job state.</span></span>

<span data-ttu-id="fbba3-154">O segundo comando usa um `Stop-Job` comando que tem o parâmetro **InstanceId** para interromper um trabalho selecionado.</span><span class="sxs-lookup"><span data-stu-id="fbba3-154">The second command uses a `Stop-Job` command that has the **InstanceID** parameter to stop a selected job.</span></span>

### <span data-ttu-id="fbba3-155">Exemplo 7: parar um trabalho em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="fbba3-155">Example 7: Stop a job on a remote computer</span></span>

```powershell
$j = Invoke-Command -ComputerName Server01 -ScriptBlock {Get-EventLog System} -AsJob
$j | Stop-Job -PassThru
```

```Output
Id    Name    State      HasMoreData     Location         Command
--    ----    ----       -----------     --------         -------
5     Job5    Stopped    True            user01-tablet    get-eventlog system
```

<span data-ttu-id="fbba3-156">Este exemplo mostra como usar o `Stop-Job` cmdlet para interromper um trabalho que está sendo executado em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="fbba3-156">This example shows how to use the `Stop-Job` cmdlet to stop a job that is running on a remote computer.</span></span>

<span data-ttu-id="fbba3-157">Como o trabalho foi iniciado usando o parâmetro **AsJob** do `Invoke-Command` cmdlet, o objeto de trabalho está localizado no computador local, embora o trabalho seja executado no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="fbba3-157">Because the job was started by using the **AsJob** parameter of the `Invoke-Command` cmdlet, the job object is located on the local computer, even though the job runs on the remote computer.</span></span> <span data-ttu-id="fbba3-158">Portanto, você pode usar um `Stop-Job` comando local para interromper o trabalho.</span><span class="sxs-lookup"><span data-stu-id="fbba3-158">Therefore, you can use a local `Stop-Job` command to stop the job.</span></span>

<span data-ttu-id="fbba3-159">O primeiro comando usa o `Invoke-Command` cmdlet para iniciar um trabalho em segundo plano no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="fbba3-159">The first command uses the `Invoke-Command` cmdlet to start a background job on the Server01 computer.</span></span> <span data-ttu-id="fbba3-160">O comando usa o parâmetro **AsJob** para executar o comando remoto como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="fbba3-160">The command uses the **AsJob** parameter to run the remote command as a background job.</span></span>

<span data-ttu-id="fbba3-161">Esse comando retorna um objeto de trabalho, que é o mesmo objeto de trabalho que o `Start-Job` cmdlet retorna.</span><span class="sxs-lookup"><span data-stu-id="fbba3-161">This command returns a job object, which is the same job object that the `Start-Job` cmdlet returns.</span></span>
<span data-ttu-id="fbba3-162">O comando salva o objeto de trabalho na `$j` variável.</span><span class="sxs-lookup"><span data-stu-id="fbba3-162">The command saves the job object in the `$j` variable.</span></span>

<span data-ttu-id="fbba3-163">O segundo comando usa um operador de pipeline para enviar o trabalho na `$j` variável para `Stop-Job` .</span><span class="sxs-lookup"><span data-stu-id="fbba3-163">The second command uses a pipeline operator to send the job in the `$j` variable to `Stop-Job`.</span></span> <span data-ttu-id="fbba3-164">O comando usa o parâmetro **PassThru** para direcionar `Stop-Job` para retornar um objeto de trabalho.</span><span class="sxs-lookup"><span data-stu-id="fbba3-164">The command uses the **PassThru** parameter to direct `Stop-Job` to return a job object.</span></span> <span data-ttu-id="fbba3-165">A exibição do objeto de trabalho confirma que o estado do trabalho foi interrompido.</span><span class="sxs-lookup"><span data-stu-id="fbba3-165">The job object display confirms that the state of the job is Stopped.</span></span>

<span data-ttu-id="fbba3-166">Para obter mais informações sobre trabalhos remotos em segundo plano, consulte about_Remote_Jobs.</span><span class="sxs-lookup"><span data-stu-id="fbba3-166">For more information about remote background jobs, see about_Remote_Jobs.</span></span>

## <span data-ttu-id="fbba3-167">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fbba3-167">PARAMETERS</span></span>

### <span data-ttu-id="fbba3-168">-Filter</span><span class="sxs-lookup"><span data-stu-id="fbba3-168">-Filter</span></span>

<span data-ttu-id="fbba3-169">Especifica uma tabela de hash de condições.</span><span class="sxs-lookup"><span data-stu-id="fbba3-169">Specifies a hash table of conditions.</span></span> <span data-ttu-id="fbba3-170">Esse cmdlet interrompe os trabalhos que atendem a todas as condições.</span><span class="sxs-lookup"><span data-stu-id="fbba3-170">This cmdlet stops jobs that satisfy all of the conditions.</span></span>
<span data-ttu-id="fbba3-171">Insira uma tabela de hash na qual as chaves são propriedades do trabalho e os valores são valores de propriedade do trabalho.</span><span class="sxs-lookup"><span data-stu-id="fbba3-171">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="fbba3-172">Este parâmetro funciona somente em tipos de trabalho personalizados, como os de fluxo de trabalho e os trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="fbba3-172">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span> <span data-ttu-id="fbba3-173">Ele não funciona em trabalhos em segundo plano padrão, como aqueles criados usando o `Start-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fbba3-173">It does not work on standard background jobs, such as those created by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="fbba3-174">Para obter informações sobre o suporte para este parâmetro, consulte o tópico da Ajuda para o tipo de trabalho em questão.</span><span class="sxs-lookup"><span data-stu-id="fbba3-174">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="fbba3-175">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="fbba3-175">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="fbba3-176">-Id</span><span class="sxs-lookup"><span data-stu-id="fbba3-176">-Id</span></span>

<span data-ttu-id="fbba3-177">Especifica as IDs de trabalhos que este cmdlet interrompe.</span><span class="sxs-lookup"><span data-stu-id="fbba3-177">Specifies the IDs of jobs that this cmdlet stops.</span></span> <span data-ttu-id="fbba3-178">O padrão é todos os trabalhos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="fbba3-178">The default is all jobs in the current session.</span></span>

<span data-ttu-id="fbba3-179">A ID é um inteiro que identifica exclusivamente o trabalho na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="fbba3-179">The ID is an integer that uniquely identifies the job in the current session.</span></span> <span data-ttu-id="fbba3-180">É mais fácil lembrar e digitar do que a ID da instância, mas só é exclusiva na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="fbba3-180">It is easier to remember and type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="fbba3-181">Você pode digitar uma ou mais IDs, separadas por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="fbba3-181">You can type one or more IDs, separated by commas.</span></span> <span data-ttu-id="fbba3-182">Para localizar a ID de um trabalho, digite `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="fbba3-182">To find the ID of a job, type `Get-Job`.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fbba3-183">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="fbba3-183">-InstanceId</span></span>

<span data-ttu-id="fbba3-184">Especifica as IDs de instância dos trabalhos que este cmdlet interrompe.</span><span class="sxs-lookup"><span data-stu-id="fbba3-184">Specifies the instance IDs of jobs that this cmdlet stops.</span></span> <span data-ttu-id="fbba3-185">O padrão é obter todos os trabalhos.</span><span class="sxs-lookup"><span data-stu-id="fbba3-185">The default is all jobs.</span></span>

<span data-ttu-id="fbba3-186">Uma ID de instância é um GUID que identifica exclusivamente o trabalho no computador.</span><span class="sxs-lookup"><span data-stu-id="fbba3-186">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span> <span data-ttu-id="fbba3-187">Para localizar a ID de instância de um trabalho, use `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="fbba3-187">To find the instance ID of a job, use `Get-Job`.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fbba3-188">-Trabalho</span><span class="sxs-lookup"><span data-stu-id="fbba3-188">-Job</span></span>

<span data-ttu-id="fbba3-189">Especifica os trabalhos que este cmdlet interrompe.</span><span class="sxs-lookup"><span data-stu-id="fbba3-189">Specifies the jobs that this cmdlet stops.</span></span> <span data-ttu-id="fbba3-190">Insira uma variável que contenha os trabalhos ou um comando que os obtenha.</span><span class="sxs-lookup"><span data-stu-id="fbba3-190">Enter a variable that contains the jobs or a command that gets the jobs.</span></span> <span data-ttu-id="fbba3-191">Você também pode usar um operador de pipeline para enviar trabalhos para o `Stop-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fbba3-191">You can also use a pipeline operator to submit jobs to the `Stop-Job` cmdlet.</span></span> <span data-ttu-id="fbba3-192">Por padrão, o `Stop-Job` exclui todos os trabalhos que foram iniciados na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="fbba3-192">By default, `Stop-Job` deletes all jobs that were started in the current session.</span></span>

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="fbba3-193">-Name</span><span class="sxs-lookup"><span data-stu-id="fbba3-193">-Name</span></span>

<span data-ttu-id="fbba3-194">Especifica nomes amigáveis de trabalhos que este cmdlet interrompe.</span><span class="sxs-lookup"><span data-stu-id="fbba3-194">Specifies friendly names of jobs that this cmdlet stops.</span></span> <span data-ttu-id="fbba3-195">Digite os nomes de trabalho em uma lista separada por vírgulas ou use caracteres curinga (\*) para inserir um padrão de nome de trabalho.</span><span class="sxs-lookup"><span data-stu-id="fbba3-195">Enter the job names in a comma-separated list or use wildcard characters (\*) to enter a job name pattern.</span></span> <span data-ttu-id="fbba3-196">Por padrão, o `Stop-Job` interrompe todos os trabalhos criados na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="fbba3-196">By default, `Stop-Job` stops all jobs created in the current session.</span></span>

<span data-ttu-id="fbba3-197">Como não há garantia de que o nome amigável seja exclusivo, use os parâmetros **WhatIf** e **Confirm** ao parar trabalhos por nome.</span><span class="sxs-lookup"><span data-stu-id="fbba3-197">Because the friendly name is not guaranteed to be unique, use the **WhatIf** and **Confirm** parameters when stopping jobs by name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="fbba3-198">-PassThru</span><span class="sxs-lookup"><span data-stu-id="fbba3-198">-PassThru</span></span>

<span data-ttu-id="fbba3-199">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="fbba3-199">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="fbba3-200">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="fbba3-200">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="fbba3-201">-Estado</span><span class="sxs-lookup"><span data-stu-id="fbba3-201">-State</span></span>

<span data-ttu-id="fbba3-202">Especifica um estado de trabalho.</span><span class="sxs-lookup"><span data-stu-id="fbba3-202">Specifies a job state.</span></span> <span data-ttu-id="fbba3-203">Este cmdlet interrompe apenas os trabalhos no estado especificado.</span><span class="sxs-lookup"><span data-stu-id="fbba3-203">This cmdlet stops only jobs in the specified state.</span></span> <span data-ttu-id="fbba3-204">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="fbba3-204">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="fbba3-205">NotStarted</span><span class="sxs-lookup"><span data-stu-id="fbba3-205">NotStarted</span></span>
- <span data-ttu-id="fbba3-206">Executando</span><span class="sxs-lookup"><span data-stu-id="fbba3-206">Running</span></span>
- <span data-ttu-id="fbba3-207">Concluído</span><span class="sxs-lookup"><span data-stu-id="fbba3-207">Completed</span></span>
- <span data-ttu-id="fbba3-208">Falhou</span><span class="sxs-lookup"><span data-stu-id="fbba3-208">Failed</span></span>
- <span data-ttu-id="fbba3-209">Parado</span><span class="sxs-lookup"><span data-stu-id="fbba3-209">Stopped</span></span>
- <span data-ttu-id="fbba3-210">Bloqueado</span><span class="sxs-lookup"><span data-stu-id="fbba3-210">Blocked</span></span>
- <span data-ttu-id="fbba3-211">Suspenso</span><span class="sxs-lookup"><span data-stu-id="fbba3-211">Suspended</span></span>
- <span data-ttu-id="fbba3-212">Desconectado</span><span class="sxs-lookup"><span data-stu-id="fbba3-212">Disconnected</span></span>
- <span data-ttu-id="fbba3-213">Suspensão</span><span class="sxs-lookup"><span data-stu-id="fbba3-213">Suspending</span></span>
- <span data-ttu-id="fbba3-214">Parando</span><span class="sxs-lookup"><span data-stu-id="fbba3-214">Stopping</span></span>

<span data-ttu-id="fbba3-215">Para obter mais informações sobre os Estados de trabalho, consulte [Enumeração JobState](/dotnet/api/system.management.automation.jobstate).</span><span class="sxs-lookup"><span data-stu-id="fbba3-215">For more information about job states, see [JobState Enumeration](/dotnet/api/system.management.automation.jobstate).</span></span>

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fbba3-216">-Confirm</span><span class="sxs-lookup"><span data-stu-id="fbba3-216">-Confirm</span></span>

<span data-ttu-id="fbba3-217">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fbba3-217">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="fbba3-218">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="fbba3-218">-WhatIf</span></span>

<span data-ttu-id="fbba3-219">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="fbba3-219">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="fbba3-220">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="fbba3-220">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="fbba3-221">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fbba3-221">CommonParameters</span></span>

<span data-ttu-id="fbba3-222">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fbba3-222">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fbba3-223">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fbba3-223">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fbba3-224">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="fbba3-224">INPUTS</span></span>

### <span data-ttu-id="fbba3-225">System. Management. Automation. RemotingJob</span><span class="sxs-lookup"><span data-stu-id="fbba3-225">System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="fbba3-226">É possível canalizar um objeto de trabalho para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fbba3-226">You can pipe a job object to this cmdlet.</span></span>

## <span data-ttu-id="fbba3-227">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="fbba3-227">OUTPUTS</span></span>

### <span data-ttu-id="fbba3-228">Nenhum, System. Management. Automation. PSRemotingJob</span><span class="sxs-lookup"><span data-stu-id="fbba3-228">None, System.Management.Automation.PSRemotingJob</span></span>

<span data-ttu-id="fbba3-229">Esse cmdlet retorna um objeto de trabalho, se você especificar o parâmetro **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="fbba3-229">This cmdlet returns a job object, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="fbba3-230">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="fbba3-230">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="fbba3-231">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="fbba3-231">NOTES</span></span>

## <span data-ttu-id="fbba3-232">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="fbba3-232">RELATED LINKS</span></span>

[<span data-ttu-id="fbba3-233">Get-Job</span><span class="sxs-lookup"><span data-stu-id="fbba3-233">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="fbba3-234">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="fbba3-234">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="fbba3-235">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="fbba3-235">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="fbba3-236">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="fbba3-236">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="fbba3-237">Start-Job</span><span class="sxs-lookup"><span data-stu-id="fbba3-237">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="fbba3-238">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="fbba3-238">Wait-Job</span></span>](Wait-Job.md)

[<span data-ttu-id="fbba3-239">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="fbba3-239">about_Job_Details</span></span>](About/about_Job_Details.md)

[<span data-ttu-id="fbba3-240">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="fbba3-240">about_Remote_Jobs</span></span>](About/about_Remote_Jobs.md)

[<span data-ttu-id="fbba3-241">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="fbba3-241">about_Remote_Variables</span></span>](About/about_Remote_Variables.md)

[<span data-ttu-id="fbba3-242">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="fbba3-242">about_Jobs</span></span>](About/about_Jobs.md)

[<span data-ttu-id="fbba3-243">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="fbba3-243">about_Scopes</span></span>](About/about_scopes.md)
