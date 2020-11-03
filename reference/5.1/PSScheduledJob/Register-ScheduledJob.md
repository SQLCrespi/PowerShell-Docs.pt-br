---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/register-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-ScheduledJob
ms.openlocfilehash: 89887474142490a71d372577576fb0059b4ff12e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193670"
---
# <span data-ttu-id="0506a-103">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0506a-103">Register-ScheduledJob</span></span>

## <span data-ttu-id="0506a-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="0506a-104">SYNOPSIS</span></span>
<span data-ttu-id="0506a-105">Cria um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="0506a-105">Creates a scheduled job.</span></span>

## <span data-ttu-id="0506a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0506a-106">SYNTAX</span></span>

### <span data-ttu-id="0506a-107">ScriptBlock (padrão)</span><span class="sxs-lookup"><span data-stu-id="0506a-107">ScriptBlock (Default)</span></span>

```
Register-ScheduledJob [-ScriptBlock] <ScriptBlock> [-Name] <String>
 [-Trigger <ScheduledJobTrigger[]>] [-InitializationScript <ScriptBlock>] [-RunAs32]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-ScheduledJobOption <ScheduledJobOptions>] [-ArgumentList <Object[]>] [-MaxResultCount <Int32>]
 [-RunNow] [-RunEvery <TimeSpan>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0506a-108">FilePath</span><span class="sxs-lookup"><span data-stu-id="0506a-108">FilePath</span></span>

```
Register-ScheduledJob [-FilePath] <String> [-Name] <String> [-Trigger <ScheduledJobTrigger[]>]
 [-InitializationScript <ScriptBlock>] [-RunAs32] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-ScheduledJobOption <ScheduledJobOptions>]
 [-ArgumentList <Object[]>] [-MaxResultCount <Int32>] [-RunNow] [-RunEvery <TimeSpan>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0506a-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0506a-109">DESCRIPTION</span></span>

<span data-ttu-id="0506a-110">O `Register-ScheduledJob` cmdlet cria trabalhos agendados no computador local.</span><span class="sxs-lookup"><span data-stu-id="0506a-110">The `Register-ScheduledJob` cmdlet creates scheduled jobs on the local computer.</span></span>

<span data-ttu-id="0506a-111">Um trabalho agendado é um trabalho em segundo plano do Windows PowerShell que pode ser iniciado automaticamente em um agendamento de uso único ou recorrente.</span><span class="sxs-lookup"><span data-stu-id="0506a-111">A scheduled job is a Windows PowerShell background job that can be started automatically on a one-time or recurring schedule.</span></span> <span data-ttu-id="0506a-112">Os trabalhos agendados são armazenados em disco e registrados em Agendador de Tarefas.</span><span class="sxs-lookup"><span data-stu-id="0506a-112">Scheduled jobs are stored on disk and registered in Task Scheduler.</span></span>
<span data-ttu-id="0506a-113">Os trabalhos podem ser gerenciados em Agendador de Tarefas ou usando os cmdlets de trabalho agendado no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0506a-113">The jobs can be managed in Task Scheduler or by using the Scheduled Job cmdlets in Windows PowerShell.</span></span>

<span data-ttu-id="0506a-114">Quando um trabalho agendado é iniciado, ele cria uma instância do trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="0506a-114">When a scheduled job starts, it creates an instance of the scheduled job.</span></span> <span data-ttu-id="0506a-115">Instâncias de trabalho agendado são idênticas aos trabalhos em segundo plano do Windows PowerShell, exceto que os resultados são salvos em disco.</span><span class="sxs-lookup"><span data-stu-id="0506a-115">Scheduled job instances are identical to Windows PowerShell background jobs, except that the results are saved on disk.</span></span> <span data-ttu-id="0506a-116">Use os cmdlets de trabalho, como `Start-Job` , `Get-Job` e `Receive-Job` para iniciar, exibir e obter os resultados das instâncias de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0506a-116">Use the Job cmdlets, such as `Start-Job`, `Get-Job`, and `Receive-Job` to start, view, and get the results of the job instances.</span></span>

<span data-ttu-id="0506a-117">Use `Register-ScheduledJob` para criar um novo trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="0506a-117">Use `Register-ScheduledJob` to create a new scheduled job.</span></span> <span data-ttu-id="0506a-118">Para especificar os comandos que o trabalho agendado executa, use o parâmetro **scriptblock** .</span><span class="sxs-lookup"><span data-stu-id="0506a-118">To specify the commands that the scheduled job runs, use the **ScriptBlock** parameter.</span></span> <span data-ttu-id="0506a-119">Para especificar um script que o trabalho executa, use o parâmetro **FilePath** .</span><span class="sxs-lookup"><span data-stu-id="0506a-119">To specify a script that the job runs, use the **FilePath** parameter.</span></span>

<span data-ttu-id="0506a-120">Windows PowerShell-os trabalhos agendados usam os mesmos gatilhos de trabalho e opções de trabalho que o Agendador de Tarefas usa para as tarefas agendadas.</span><span class="sxs-lookup"><span data-stu-id="0506a-120">Windows PowerShell-scheduled jobs use the same job triggers and job options that Task Scheduler uses for scheduled tasks.</span></span>

<span data-ttu-id="0506a-121">O parâmetro **Trigger** de `Register-ScheduledJob` adiciona um ou mais gatilhos de trabalho que iniciam o trabalho.</span><span class="sxs-lookup"><span data-stu-id="0506a-121">The **Trigger** parameter of `Register-ScheduledJob` adds one or more job triggers that start the job.</span></span> <span data-ttu-id="0506a-122">O parâmetro **Trigger** é opcional, de modo que você pode adicionar gatilhos ao criar o trabalho agendado, adicionar gatilhos de trabalho mais tarde, adicionar o parâmetro **RunNow** para iniciar o trabalho imediatamente, usar o `Start-Job` cmdlet para iniciar o trabalho imediatamente a qualquer momento ou salvar o trabalho agendado não disparado como um modelo para outros trabalhos.</span><span class="sxs-lookup"><span data-stu-id="0506a-122">The **Trigger** parameter is optional, so you can add triggers when you create the scheduled job, add job triggers later, add the **RunNow** parameter to start the job immediately, use the `Start-Job` cmdlet to start the job immediately at any time, or save the untriggered scheduled job as a template for other jobs.</span></span>

<span data-ttu-id="0506a-123">O parâmetro **Options** permite que você personalize as configurações de opções do trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="0506a-123">The **Options** parameter lets you customize the options settings for the scheduled job.</span></span> <span data-ttu-id="0506a-124">O parâmetro **Options** é opcional, de modo que você pode definir opções de trabalho ao criar o trabalho agendado ou alterá-los a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="0506a-124">The **Options** parameter is optional, so you can set job options when you create the scheduled job or change them at any time.</span></span> <span data-ttu-id="0506a-125">Como as configurações de opção de trabalho podem impedir o trabalho agendado de ser executado, examine as opções de trabalho e as defina com cuidado.</span><span class="sxs-lookup"><span data-stu-id="0506a-125">Because job option settings can prevent the scheduled job from running, review the job options and set them carefully.</span></span>

<span data-ttu-id="0506a-126">`Register-ScheduledJob` é um de uma coleção de cmdlets de agendamento de trabalho no módulo **PSScheduledJob** que está incluído no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0506a-126">`Register-ScheduledJob` is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="0506a-127">Para obter mais informações sobre trabalhos agendados, consulte os artigos about no módulo **PSScheduledJob** .</span><span class="sxs-lookup"><span data-stu-id="0506a-127">For more information about Scheduled Jobs, see the About articles in the **PSScheduledJob** module.</span></span>
<span data-ttu-id="0506a-128">Importe o módulo **PSScheduledJob** e, em seguida, digite: `Get-Help about_Scheduled*` ou consulte [about_Scheduled_Jobs](./about/about_scheduled_jobs.md).</span><span class="sxs-lookup"><span data-stu-id="0506a-128">Import the **PSScheduledJob** module and then type: `Get-Help about_Scheduled*` or see [about_Scheduled_Jobs](./about/about_scheduled_jobs.md).</span></span>

<span data-ttu-id="0506a-129">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0506a-129">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="0506a-130">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="0506a-130">EXAMPLES</span></span>

### <span data-ttu-id="0506a-131">Exemplo 1: criar um trabalho agendado</span><span class="sxs-lookup"><span data-stu-id="0506a-131">Example 1: Create a scheduled job</span></span>

<span data-ttu-id="0506a-132">Este exemplo cria um trabalho agendado no computador local.</span><span class="sxs-lookup"><span data-stu-id="0506a-132">This example creates a scheduled job on the local computer.</span></span>

```powershell
Register-ScheduledJob -Name "Archive-Scripts" -ScriptBlock {
  Get-ChildItem $home\*.ps1 -Recurse |
    Copy-Item -Destination "\\Server\Share\PSScriptArchive"
}
```

<span data-ttu-id="0506a-133">`Register-ScheduledJob` usa o parâmetro **Name** para criar o trabalho agendado de **scripts de arquivo** .</span><span class="sxs-lookup"><span data-stu-id="0506a-133">`Register-ScheduledJob` uses the **Name** parameter to create the **Archive-Scripts** scheduled job.</span></span>
<span data-ttu-id="0506a-134">O parâmetro **scriptblock** executa `Get-ChildItem` que pesquisa o `$home` diretório recursivamente para `.ps1` arquivos.</span><span class="sxs-lookup"><span data-stu-id="0506a-134">The **ScriptBlock** parameter runs `Get-ChildItem` that searches the `$home` directory recursively for `.ps1` files.</span></span> <span data-ttu-id="0506a-135">O `Copy-Item` cmdlet copia os arquivos para um diretório especificado pelo parâmetro de **destino** .</span><span class="sxs-lookup"><span data-stu-id="0506a-135">The `Copy-Item` cmdlet copies the files to a directory specified by the **Destination** parameter.</span></span>

<span data-ttu-id="0506a-136">Como o trabalho agendado não contém um gatilho, ele não é iniciado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0506a-136">Because the scheduled job doesn't contain a trigger, it's not started automatically.</span></span> <span data-ttu-id="0506a-137">Você pode adicionar gatilhos de trabalho com `Add-JobTrigger` o, usar o `Start-Job` cmdlet para iniciar o trabalho sob demanda ou usar o trabalho agendado como um modelo para outros trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="0506a-137">You can add job triggers with `Add-JobTrigger`, use the `Start-Job` cmdlet to start the job on demand, or use the scheduled job as a template for other scheduled jobs.</span></span>

### <span data-ttu-id="0506a-138">Exemplo 2: criar um trabalho agendado com gatilhos e opções personalizadas</span><span class="sxs-lookup"><span data-stu-id="0506a-138">Example 2: Create a scheduled job with triggers and custom options</span></span>

<span data-ttu-id="0506a-139">Este exemplo mostra como criar um trabalho agendado com um gatilho de trabalho e opções de trabalho personalizadas.</span><span class="sxs-lookup"><span data-stu-id="0506a-139">This example shows how to create a scheduled job that has a job trigger and custom job options.</span></span>

```powershell
$O = New-ScheduledJobOption -WakeToRun -StartIfIdle -MultipleInstancePolicy Queue
$T = New-JobTrigger -Weekly -At "9:00 PM" -DaysOfWeek Monday -WeeksInterval 2
$path = "\\Srv01\Scripts\UpdateVersion.ps1"
Register-ScheduledJob -Name "UpdateVersion" -FilePath $path -ScheduledJobOption $O -Trigger $T
```

<span data-ttu-id="0506a-140">A `$O` variável armazena o objeto de opção de trabalho que o `New-ScheduledJobOption` cmdlet criou.</span><span class="sxs-lookup"><span data-stu-id="0506a-140">The `$O` variable stores the job option object that the `New-ScheduledJobOption` cmdlet created.</span></span> <span data-ttu-id="0506a-141">As opções iniciam o trabalho agendado mesmo que o computador não esteja ocioso, ativa o computador para executar o trabalho, se necessário, e permite que várias instâncias do trabalho sejam executadas em uma série.</span><span class="sxs-lookup"><span data-stu-id="0506a-141">The options start the scheduled job even if the computer isn't idle, wakes the computer to run the job, if necessary, and allows multiple instances of the job to run in a series.</span></span>

<span data-ttu-id="0506a-142">A `$T` variável armazena o resultado do `New-JobTrigger` cmdlet para criar um gatilho de trabalho que inicia um trabalho a cada segunda-feira às 9:00 PM.</span><span class="sxs-lookup"><span data-stu-id="0506a-142">The `$T` variable stores the result from the `New-JobTrigger` cmdlet to create job trigger that starts a job every other Monday at 9:00 PM.</span></span>

<span data-ttu-id="0506a-143">A `$path` variável armazena o caminho para o `UpdateVersion.ps1` arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="0506a-143">The `$path` variable stores the path to the `UpdateVersion.ps1` script file.</span></span>

<span data-ttu-id="0506a-144">`Register-ScheduledJob` usa o parâmetro de **nome** para criar o trabalho agendado do **UpdateVersion** .</span><span class="sxs-lookup"><span data-stu-id="0506a-144">`Register-ScheduledJob` uses the **Name** paramter to create the **UpdateVersion** scheduled job.</span></span>
<span data-ttu-id="0506a-145">O parâmetro **FilePath** usa `$path` para especificar o script que o trabalho executa.</span><span class="sxs-lookup"><span data-stu-id="0506a-145">The **FilePath** parameter uses `$path` to specify the script that the job runs.</span></span> <span data-ttu-id="0506a-146">O parâmetro **ScheduledJobOption** usa as opções de trabalho armazenadas em `$O` .</span><span class="sxs-lookup"><span data-stu-id="0506a-146">The **ScheduledJobOption** parameter uses the job options stored in `$O`.</span></span> <span data-ttu-id="0506a-147">O parâmetro **Trigger** usa os gatilhos de trabalho armazenados no `$T` .</span><span class="sxs-lookup"><span data-stu-id="0506a-147">The **Trigger** parameter uses the job triggers stored in `$T`.</span></span>

### <span data-ttu-id="0506a-148">Exemplo 3: usar tabelas de hash para especificar um gatilho e opções de trabalho agendado</span><span class="sxs-lookup"><span data-stu-id="0506a-148">Example 3: Use hash tables to specify a trigger and scheduled job options</span></span>

<span data-ttu-id="0506a-149">Este exemplo tem o mesmo efeito que o comando no exemplo 2.</span><span class="sxs-lookup"><span data-stu-id="0506a-149">This example has the same effect as the command in Example 2.</span></span> <span data-ttu-id="0506a-150">Ele cria um trabalho agendado, usando tabelas de hash para especificar os valores dos parâmetros **Trigger** e **ScheduledJobOption** .</span><span class="sxs-lookup"><span data-stu-id="0506a-150">It creates a scheduled job, using hash tables to specify the values of the **Trigger** and **ScheduledJobOption** parameters.</span></span> <span data-ttu-id="0506a-151">As `$O` `$T` variáveis e definidas no exemplo 2 são substituídas por tabelas de hash.</span><span class="sxs-lookup"><span data-stu-id="0506a-151">The `$O` and `$T`variables defined in Example 2 are replaced with hash tables.</span></span>

```powershell
$T = @{
  Frequency="Weekly"
  At="9:00PM"
  DaysOfWeek="Monday"
  Interval=2
}
$O = @{
  WakeToRun=$true
  StartIfNotIdle=$false
  MultipleInstancePolicy="Queue"
}
Register-ScheduledJob -Trigger $T -ScheduledJobOption $O -Name UpdateVersion -FilePath "\\Srv01\Scripts\Update-Version.ps1"
```

### <span data-ttu-id="0506a-152">Exemplo 4: criar trabalhos agendados em computadores remotos</span><span class="sxs-lookup"><span data-stu-id="0506a-152">Example 4: Create scheduled jobs on remote computers</span></span>

<span data-ttu-id="0506a-153">Neste exemplo, o trabalho agendado **EnergyData** é criado em vários computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="0506a-153">In this example, the **EnergyData** scheduled job is created on multiple remote computers.</span></span> <span data-ttu-id="0506a-154">O trabalho agendado executa um script que reúne dados brutos e os salva em um log em execução no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="0506a-154">The scheduled job runs a script that gathers raw data and saves it in a running log on the remote computer.</span></span>

```powershell
$Cred = Get-Credential
$O = New-ScheduledJobOption -WakeToRun -StartIfIdle -MultipleInstancePolicy Queue
$T = New-JobTrigger -Weekly -At "9:00 PM" -DaysOfWeek Monday -WeeksInterval 2
Invoke-Command -ComputerName (Get-Content Servers.txt) -Credential $Cred -ScriptBlock {
  $params = @{
      Name = "Get-EnergyData"
      FilePath = "\\Srv01\Scripts\Get-EnergyData.ps1"
      ScheduledJobOption = $using:O
      Trigger = $using:T
  }
  Register-ScheduledJob @params
}
```

<span data-ttu-id="0506a-155">A `$Cred` variável armazena as credenciais em um objeto **PSCredential** para um usuário com permissões para criar trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="0506a-155">The `$Cred` variable stores credentials in a **PSCredential** object for a user with permissions to create scheduled jobs.</span></span> <span data-ttu-id="0506a-156">A `$O` variável armazena as opções de trabalho criadas com `New-ScheduledJobOption` .</span><span class="sxs-lookup"><span data-stu-id="0506a-156">The `$O` variable stores the job options created with `New-ScheduledJobOption`.</span></span> <span data-ttu-id="0506a-157">A `$T` variável armazena os gatilhos de trabalho criados com `New-JobTrigger` .</span><span class="sxs-lookup"><span data-stu-id="0506a-157">The `$T` variable stores the job triggers created with `New-JobTrigger`.</span></span>

<span data-ttu-id="0506a-158">O `Invoke-Command` cmdlet usa o parâmetro **ComputerName** para obter uma lista de nomes de servidor do `Servers.txt` arquivo.</span><span class="sxs-lookup"><span data-stu-id="0506a-158">The `Invoke-Command` cmdlet uses the **ComputerName** parameter to get a list of server names from the `Servers.txt` file.</span></span> <span data-ttu-id="0506a-159">O parâmetro **Credential** Obtém o objeto de credencial armazenado no `$Cred` .</span><span class="sxs-lookup"><span data-stu-id="0506a-159">The **Credential** parameter gets the credential object stored in `$Cred`.</span></span>
<span data-ttu-id="0506a-160">O parâmetro **scriptblock** executa um `Register-ScheduledJob` comando nos computadores do `Servers.txt` arquivo.</span><span class="sxs-lookup"><span data-stu-id="0506a-160">The **ScriptBlock** parameter runs a `Register-ScheduledJob` command on the computers in the `Servers.txt` file.</span></span>

<span data-ttu-id="0506a-161">Os parâmetros para `Register-ScheduledJob` são definidos por `$params` .</span><span class="sxs-lookup"><span data-stu-id="0506a-161">The parameters for `Register-ScheduledJob` are defined by `$params`.</span></span> <span data-ttu-id="0506a-162">Os parâmetros de **nome** especificam que o trabalho é denominado **Get-EnergyData** em cada computador remoto.</span><span class="sxs-lookup"><span data-stu-id="0506a-162">The **Name** parameters specifies the job is named **Get-EnergyData** on each remote computer.</span></span> <span data-ttu-id="0506a-163">**FilePath** fornece o local do `EnergyData.ps1` script.</span><span class="sxs-lookup"><span data-stu-id="0506a-163">**FilePath** provides the location of the `EnergyData.ps1` script.</span></span> <span data-ttu-id="0506a-164">O script está localizado em um servidor de arquivos que está disponível para todos os computadores participantes. O trabalho é executado no agendamento especificado pelos disparadores de trabalho no `$T` e nas opções de trabalho no `$O` .</span><span class="sxs-lookup"><span data-stu-id="0506a-164">The script is located on a file server that is available to all participating computers.The job runs on the schedule specified by the job triggers in `$T` and the job options in `$O`.</span></span>

<span data-ttu-id="0506a-165">O `Register-ScheduledJob @params` comando cria o trabalho agendado com os parâmetros do bloco de script.</span><span class="sxs-lookup"><span data-stu-id="0506a-165">The `Register-ScheduledJob @params` command creates the scheduled job with the parameters from the script block.</span></span>

### <span data-ttu-id="0506a-166">Exemplo 5: criar um trabalho agendado que executa um script em computadores remotos</span><span class="sxs-lookup"><span data-stu-id="0506a-166">Example 5: Create a scheduled job that runs a script on remote computers</span></span>

<span data-ttu-id="0506a-167">Este exemplo cria o trabalho agendado do **CollectEnergyData** no computador local.</span><span class="sxs-lookup"><span data-stu-id="0506a-167">This example creates the **CollectEnergyData** scheduled job on the local computer.</span></span> <span data-ttu-id="0506a-168">O trabalho é executado em vários computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="0506a-168">The job runs on multiple remote computers.</span></span>

```powershell
$Admin = Get-Credential
$T = New-JobTrigger -Weekly -At "9:00 PM" -DaysOfWeek Monday -WeeksInterval 2
Register-ScheduledJob -Name "CollectEnergyData" -Trigger $T -MaxResultCount 99 -ScriptBlock {
  $params = @{
    AsJob = $true
    ComputerName = (Get-Content Servers.txt)
    FilePath = '\\Srv01\Scripts\Get-EnergyData.ps1'
    Credential = $using:Admin
    Authentication = 'CredSSP'
  }
  Invoke-Command @params
}
```

<span data-ttu-id="0506a-169">A `$Admin` variável armazena as credenciais de um usuário com permissões para executar os comandos em um objeto **PSCredential** .</span><span class="sxs-lookup"><span data-stu-id="0506a-169">The `$Admin` variable stores credentials for a user with permissions to run the commands in a **PSCredential** object.</span></span> <span data-ttu-id="0506a-170">A `$T` variável armazena os gatilhos de trabalho criados com `New-JobTrigger` .</span><span class="sxs-lookup"><span data-stu-id="0506a-170">The `$T` variable stores the job triggers created with `New-JobTrigger`.</span></span>

<span data-ttu-id="0506a-171">O `Register-ScheduledJob` cmdlet usa o parâmetro **Name** para criar o trabalho agendado do **CollectEnergyData** no computador local.</span><span class="sxs-lookup"><span data-stu-id="0506a-171">The `Register-ScheduledJob` cmdlet uses the **Name** parameter to create the **CollectEnergyData** scheduled job on the local computer.</span></span> <span data-ttu-id="0506a-172">O parâmetro **Trigger** especifica os gatilhos de trabalho no `$T` e o parâmetro **MaxResultCount** aumenta o número de resultados salvos em 99.</span><span class="sxs-lookup"><span data-stu-id="0506a-172">The **Trigger** parameter specifies the job triggers in `$T` and the **MaxResultCount** parameter increases the number of saved results to 99.</span></span>

<span data-ttu-id="0506a-173">O parâmetro **scriptblock** define os `Invoke-Command` parâmetros com `$params` .</span><span class="sxs-lookup"><span data-stu-id="0506a-173">The **ScriptBlock** parameter defines the `Invoke-Command` parameters with `$params`.</span></span> <span data-ttu-id="0506a-174">O parâmetro **AsJob** cria o objeto de trabalho em segundo plano no computador local, embora o `Energydata.ps1` script seja executado nos computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="0506a-174">The **AsJob** parameter creates the background job object on the local computer, even though the `Energydata.ps1` script runs on the remote computers.</span></span> <span data-ttu-id="0506a-175">O parâmetro **ComputerName** Obtém uma lista de nomes de servidor do `Servers.txt` arquivo.</span><span class="sxs-lookup"><span data-stu-id="0506a-175">The **ComputerName** parameter gets a list of server names from the `Servers.txt` file.</span></span> <span data-ttu-id="0506a-176">O parâmetro **Credential** especifica uma conta de usuário que tem permissão para executar scripts nos computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="0506a-176">The **Credential** parameter specifies a user account that has permission to run scripts on the remote computers.</span></span> <span data-ttu-id="0506a-177">E, o parâmetro de **autenticação** especifica um valor de **CredSSP** para permitir credenciais delegadas.</span><span class="sxs-lookup"><span data-stu-id="0506a-177">And, the **Authentication** parameter specifies a value of **CredSSP** to allow delegated credentials.</span></span>

<span data-ttu-id="0506a-178">O `Invoke-Command @params` executa o comando com os parâmetros do bloco de script.</span><span class="sxs-lookup"><span data-stu-id="0506a-178">The `Invoke-Command @params` runs the command with the parameters from the script block.</span></span>

## <span data-ttu-id="0506a-179">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0506a-179">PARAMETERS</span></span>

### <span data-ttu-id="0506a-180">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="0506a-180">-ArgumentList</span></span>

<span data-ttu-id="0506a-181">Especifica valores para os parâmetros do script especificados pelo parâmetro **FilePath** ou para o comando especificado pelo parâmetro **ScriptBlock** .</span><span class="sxs-lookup"><span data-stu-id="0506a-181">Specifies values for the parameters of the script that is specified by the **FilePath** parameter or for the command that is specified by the **ScriptBlock** parameter.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0506a-182">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="0506a-182">-Authentication</span></span>

<span data-ttu-id="0506a-183">Especifica o mecanismo usado para autenticar as credenciais do usuário.</span><span class="sxs-lookup"><span data-stu-id="0506a-183">Specifies the mechanism that is used to authenticate the user's credentials.</span></span> <span data-ttu-id="0506a-184">O valor padrão é Default.</span><span class="sxs-lookup"><span data-stu-id="0506a-184">The default value is Default.</span></span>

<span data-ttu-id="0506a-185">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="0506a-185">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="0506a-186">Padrão</span><span class="sxs-lookup"><span data-stu-id="0506a-186">Default</span></span>
- <span data-ttu-id="0506a-187">Básico</span><span class="sxs-lookup"><span data-stu-id="0506a-187">Basic</span></span>
- <span data-ttu-id="0506a-188">CredSSP</span><span class="sxs-lookup"><span data-stu-id="0506a-188">Credssp</span></span>
- <span data-ttu-id="0506a-189">Digest</span><span class="sxs-lookup"><span data-stu-id="0506a-189">Digest</span></span>
- <span data-ttu-id="0506a-190">Kerberos</span><span class="sxs-lookup"><span data-stu-id="0506a-190">Kerberos</span></span>
- <span data-ttu-id="0506a-191">Negotiate</span><span class="sxs-lookup"><span data-stu-id="0506a-191">Negotiate</span></span>
- <span data-ttu-id="0506a-192">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="0506a-192">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="0506a-193">Para obter mais informações sobre os valores desse parâmetro, consulte [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="0506a-193">For more information about the values of this parameter, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="0506a-194">A autenticação CredSSP (Credencial Security Service Provider), na qual as credenciais do usuário são transmitidas a um computador remoto para autenticação, foi projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remota.</span><span class="sxs-lookup"><span data-stu-id="0506a-194">Credential Security Service Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="0506a-195">Esse mecanismo aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="0506a-195">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="0506a-196">Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="0506a-196">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0506a-197">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0506a-197">-Confirm</span></span>

<span data-ttu-id="0506a-198">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0506a-198">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0506a-199">-Credential</span><span class="sxs-lookup"><span data-stu-id="0506a-199">-Credential</span></span>

<span data-ttu-id="0506a-200">Especifica uma conta de usuário que tenha permissão para executar o trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="0506a-200">Specifies a user account that has permission to run the scheduled job.</span></span> <span data-ttu-id="0506a-201">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="0506a-201">The default is the current user.</span></span>

<span data-ttu-id="0506a-202">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** , como um do `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0506a-202">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object, such as one from the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="0506a-203">Se você inserir apenas um nome de usuário, você será solicitado a fornecer uma senha.</span><span class="sxs-lookup"><span data-stu-id="0506a-203">If you enter only a user name, you're prompted for a password.</span></span>

<span data-ttu-id="0506a-204">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="0506a-204">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="0506a-205">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="0506a-205">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0506a-206">-FilePath</span><span class="sxs-lookup"><span data-stu-id="0506a-206">-FilePath</span></span>

<span data-ttu-id="0506a-207">Especifica um script que o trabalho agendado executa.</span><span class="sxs-lookup"><span data-stu-id="0506a-207">Specifies a script that the scheduled job runs.</span></span> <span data-ttu-id="0506a-208">Insira o caminho para um `.ps1` arquivo no computador local.</span><span class="sxs-lookup"><span data-stu-id="0506a-208">Enter the path to a `.ps1` file on the local computer.</span></span> <span data-ttu-id="0506a-209">Para especificar valores padrão para os parâmetros de script, use o parâmetro **ArgumentList** .</span><span class="sxs-lookup"><span data-stu-id="0506a-209">To specify default values for the script parameters, use the **ArgumentList** parameter.</span></span>
<span data-ttu-id="0506a-210">Cada `Register-ScheduledJob` comando deve usar os parâmetros **scriptblock** ou **FilePath** .</span><span class="sxs-lookup"><span data-stu-id="0506a-210">Every `Register-ScheduledJob` command must use either the **ScriptBlock** or **FilePath** parameters.</span></span>

```yaml
Type: System.String
Parameter Sets: FilePath
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0506a-211">-InitializationScript</span><span class="sxs-lookup"><span data-stu-id="0506a-211">-InitializationScript</span></span>

<span data-ttu-id="0506a-212">Especifica o caminho totalmente qualificado para um script do Windows PowerShell ( `.ps1` ).</span><span class="sxs-lookup"><span data-stu-id="0506a-212">Specifies the fully qualified path to a Windows PowerShell script (`.ps1`).</span></span> <span data-ttu-id="0506a-213">O script de inicialização é executado na sessão criada para o trabalho em segundo plano antes dos comandos especificados pelo parâmetro **ScriptBlock** ou pelo script especificado pelo parâmetro **FilePath** .</span><span class="sxs-lookup"><span data-stu-id="0506a-213">The initialization script runs in the session that is created for the background job before the commands that are specified by the **ScriptBlock** parameter or the script that is specified by the **FilePath** parameter.</span></span> <span data-ttu-id="0506a-214">Você pode usar o script de inicialização para configurar a sessão, adicionando arquivos, funções ou aliases, criando diretórios ou verificando pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="0506a-214">You can use the initialization script to configure the session, such as adding files, functions, or aliases, creating directories, or checking for prerequisites.</span></span>

<span data-ttu-id="0506a-215">Para especificar um script que execute os comandos de trabalho principal, use o parâmetro **FilePath** .</span><span class="sxs-lookup"><span data-stu-id="0506a-215">To specify a script that runs the primary job commands, use the **FilePath** parameter.</span></span>

<span data-ttu-id="0506a-216">Se o script de inicialização gerar um erro, mesmo um erro de não encerramento, a instância atual do trabalho agendado não será executada e seu status **falhará** .</span><span class="sxs-lookup"><span data-stu-id="0506a-216">If the initialization script generates an error, even a non-terminating error, the current instance of the scheduled job doesn't run and its status is **Failed** .</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0506a-217">-MaxResultCount</span><span class="sxs-lookup"><span data-stu-id="0506a-217">-MaxResultCount</span></span>

<span data-ttu-id="0506a-218">Especifica quantas entradas de resultado do trabalho são mantidas para o trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="0506a-218">Specifies how many job result entries are maintained for the scheduled job.</span></span> <span data-ttu-id="0506a-219">O valor padrão é 32.</span><span class="sxs-lookup"><span data-stu-id="0506a-219">The default value is 32.</span></span>

<span data-ttu-id="0506a-220">O Windows PowerShell salva o histórico de execução e os resultados de cada instância disparada do trabalho agendado no disco.</span><span class="sxs-lookup"><span data-stu-id="0506a-220">Windows PowerShell saves the execution history and results of each triggered instance of the scheduled job on disk.</span></span> <span data-ttu-id="0506a-221">O valor desse parâmetro determina o número de resultados de instância de trabalho que são salvas para essa tarefa agendada.</span><span class="sxs-lookup"><span data-stu-id="0506a-221">The value of this parameter determines the number of job instance results that are saved for this scheduled job.</span></span> <span data-ttu-id="0506a-222">Quando o número de resultados de instância de trabalho excede esse valor, o Windows PowerShell exclui os resultados da instância de trabalho mais antiga para abrir espaço para os resultados da instância de trabalho mais recente.</span><span class="sxs-lookup"><span data-stu-id="0506a-222">When the number of job instance results exceeds this value, Windows PowerShell deletes the results of the oldest job instance to make room for the results of the newest job instance.</span></span>

<span data-ttu-id="0506a-223">O histórico de execução do trabalho e os resultados do trabalho são salvos no `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs\<JobName>\Output\<Timestamp>`</span><span class="sxs-lookup"><span data-stu-id="0506a-223">The job execution history and job results are saved in the `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs\<JobName>\Output\<Timestamp>`</span></span>
<span data-ttu-id="0506a-224">diretórios no computador no qual o trabalho é criado.</span><span class="sxs-lookup"><span data-stu-id="0506a-224">directories on the computer on which the job is created.</span></span> <span data-ttu-id="0506a-225">Para ver o histórico de execução, use o `Get-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0506a-225">To see the execution history, use the `Get-Job` cmdlet.</span></span> <span data-ttu-id="0506a-226">Para obter os resultados do trabalho, use o `Receive-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0506a-226">To get the job results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="0506a-227">O parâmetro **MaxResultCount** define o valor da propriedade ExecutionHistoryLength do trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="0506a-227">The **MaxResultCount** parameter sets the value of the ExecutionHistoryLength property of the scheduled job.</span></span>

<span data-ttu-id="0506a-228">Para excluir o histórico de execução atual e os resultados do trabalho, use o parâmetro **ClearExecutionHistory** do `Set-ScheduledJob` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0506a-228">To delete the current execution history and job results, use the **ClearExecutionHistory** parameter of the `Set-ScheduledJob` cmdlet.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0506a-229">-Name</span><span class="sxs-lookup"><span data-stu-id="0506a-229">-Name</span></span>

<span data-ttu-id="0506a-230">Especifica um nome para o trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="0506a-230">Specifies a name for the scheduled job.</span></span> <span data-ttu-id="0506a-231">O nome também é usado para todas as instâncias de trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="0506a-231">The name is also used for all started instances of the scheduled job.</span></span> <span data-ttu-id="0506a-232">O nome deve ser exclusivo no computador.</span><span class="sxs-lookup"><span data-stu-id="0506a-232">The name must be unique on the computer.</span></span> <span data-ttu-id="0506a-233">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="0506a-233">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0506a-234">-RunAs32</span><span class="sxs-lookup"><span data-stu-id="0506a-234">-RunAs32</span></span>

<span data-ttu-id="0506a-235">Executa o trabalho agendado em um processo de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="0506a-235">Runs the scheduled job in a 32-bit process.</span></span>

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

### <span data-ttu-id="0506a-236">-RunEvery</span><span class="sxs-lookup"><span data-stu-id="0506a-236">-RunEvery</span></span>

<span data-ttu-id="0506a-237">Usado para especificar a frequência de execução do trabalho.</span><span class="sxs-lookup"><span data-stu-id="0506a-237">Used to specify how often to run the job.</span></span> <span data-ttu-id="0506a-238">Por exemplo, use esta opção para executar um trabalho a cada 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="0506a-238">For example, use this option to run a job every 15 minutes.</span></span>

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0506a-239">-RunNow</span><span class="sxs-lookup"><span data-stu-id="0506a-239">-RunNow</span></span>

<span data-ttu-id="0506a-240">Inicia um trabalho imediatamente, assim que o `Register-ScheduledJob` cmdlet é executado.</span><span class="sxs-lookup"><span data-stu-id="0506a-240">Starts a job immediately, as soon as the `Register-ScheduledJob` cmdlet is run.</span></span> <span data-ttu-id="0506a-241">Esse parâmetro elimina a necessidade de disparar Agendador de Tarefas para executar um script do Windows PowerShell imediatamente após o registro e não exige que os usuários criem um gatilho que especifique uma data e hora de início.</span><span class="sxs-lookup"><span data-stu-id="0506a-241">This parameter eliminates the need to trigger Task Scheduler to run a Windows PowerShell script immediately after registration, and doesn't require users to create a trigger that specifies a starting date and time.</span></span>

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

### <span data-ttu-id="0506a-242">-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="0506a-242">-ScheduledJobOption</span></span>

<span data-ttu-id="0506a-243">Define opções para o trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="0506a-243">Sets options for the scheduled job.</span></span> <span data-ttu-id="0506a-244">Insira um objeto **ScheduledJobOptions** , como um que você cria usando o `New-ScheduledJobOption` cmdlet ou um valor de tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="0506a-244">Enter a **ScheduledJobOptions** object, such as one that you create by using the `New-ScheduledJobOption` cmdlet, or a hash table value.</span></span>

<span data-ttu-id="0506a-245">Você pode definir opções para um trabalho agendado ao registrar o trabalho de agendamento ou usar `Set-ScheduledJobOption` os `Set-ScheduledJob` cmdlets ou para alterar as opções.</span><span class="sxs-lookup"><span data-stu-id="0506a-245">You can set options for a scheduled job when you register the schedule job or use the `Set-ScheduledJobOption` or `Set-ScheduledJob` cmdlets to change the options.</span></span>

<span data-ttu-id="0506a-246">Muitas das opções e seus valores padrão determinam se e quando um trabalho agendado será executado.</span><span class="sxs-lookup"><span data-stu-id="0506a-246">Many of the options and their default values determine whether and when a scheduled job runs.</span></span> <span data-ttu-id="0506a-247">Certifique-se de examinar essas opções antes de agendar um trabalho.</span><span class="sxs-lookup"><span data-stu-id="0506a-247">Be sure to review these options before scheduling a job.</span></span> <span data-ttu-id="0506a-248">Para obter uma descrição das opções de trabalho agendado, incluindo os valores padrão, consulte `New-ScheduledJobOption` .</span><span class="sxs-lookup"><span data-stu-id="0506a-248">For a description of the scheduled job options, including the default values, see `New-ScheduledJobOption`.</span></span>

<span data-ttu-id="0506a-249">Para enviar uma tabela de hash, use as seguintes chaves.</span><span class="sxs-lookup"><span data-stu-id="0506a-249">To submit a hash table, use the following keys.</span></span> <span data-ttu-id="0506a-250">Na tabela de hash a seguir, as chaves são exibidas com seus valores padrão.</span><span class="sxs-lookup"><span data-stu-id="0506a-250">In the following hash table, the keys are shown with their default values.</span></span>

`@{StartIfOnBattery=$False; StopIfGoingOnBattery=$True; WakeToRun=$False; StartIfNotIdle=$False; IdleDuration="00:10:00"; IdleTimeout="01:00:00"; StopIfGoingOffIdle=$True; RestartOnIdleResume=$False; ShowInTaskScheduler=$True; RunElevated=$False; RunWithoutNetwork=$False; DoNotAllowDemandStart=$False; MultipleInstancePolicy="IgnoreNew"}`

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0506a-251">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="0506a-251">-ScriptBlock</span></span>

<span data-ttu-id="0506a-252">Especifica os comandos que o trabalho agendado executa.</span><span class="sxs-lookup"><span data-stu-id="0506a-252">Specifies the commands that the scheduled job runs.</span></span> <span data-ttu-id="0506a-253">Coloque os comandos entre chaves ( `{}` ) para criar um bloco de script.</span><span class="sxs-lookup"><span data-stu-id="0506a-253">Enclose the commands in curly braces (`{}`) to create a script block.</span></span> <span data-ttu-id="0506a-254">Para especificar valores padrão para os parâmetros de comando, use o parâmetro **ArgumentList** .</span><span class="sxs-lookup"><span data-stu-id="0506a-254">To specify default values for command parameters, use the **ArgumentList** parameter.</span></span>

<span data-ttu-id="0506a-255">Cada `Register-ScheduledJob` comando deve usar os parâmetros **scriptblock** ou **FilePath** .</span><span class="sxs-lookup"><span data-stu-id="0506a-255">Every `Register-ScheduledJob` command must use either the **ScriptBlock** or **FilePath** parameters.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0506a-256">-Gatilho</span><span class="sxs-lookup"><span data-stu-id="0506a-256">-Trigger</span></span>

<span data-ttu-id="0506a-257">Especifica os gatilhos para o trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="0506a-257">Specifies the triggers for the scheduled job.</span></span> <span data-ttu-id="0506a-258">Insira um ou mais objetos **ScheduledJobTrigger** , como os objetos que o `New-JobTrigger` cmdlet retorna ou uma tabela de hash de chaves e valores de gatilho de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0506a-258">Enter one or more **ScheduledJobTrigger** objects, such as the objects that the `New-JobTrigger` cmdlet returns, or a hash table of job trigger keys and values.</span></span>

<span data-ttu-id="0506a-259">Um gatilho de trabalho inicia o trabalho de agendamento.</span><span class="sxs-lookup"><span data-stu-id="0506a-259">A job trigger starts the schedule job.</span></span> <span data-ttu-id="0506a-260">O gatilho pode especificar um agendamento único ou recorrente ou um evento, como quando um usuário faz logon ou o Windows é iniciado.</span><span class="sxs-lookup"><span data-stu-id="0506a-260">The trigger can specify a one-time or recurring scheduled or an event, such as when a user logs on or Windows starts.</span></span>

<span data-ttu-id="0506a-261">O parâmetro **Trigger** é opcional.</span><span class="sxs-lookup"><span data-stu-id="0506a-261">The **Trigger** parameter is optional.</span></span> <span data-ttu-id="0506a-262">Você pode adicionar um gatilho ao criar o trabalho agendado, usar os `Add-JobTrigger` `Set-JobTrigger` `Set-ScheduledJob` cmdlets, ou para adicionar ou alterar gatilhos de trabalho mais tarde, ou usar o `Start-Job` cmdlet para iniciar o trabalho agendado imediatamente.</span><span class="sxs-lookup"><span data-stu-id="0506a-262">You can add a trigger when you create the scheduled job, use the `Add-JobTrigger`, `Set-JobTrigger`, or `Set-ScheduledJob` cmdlets to add or change job triggers later, or use the `Start-Job` cmdlet to start the scheduled job immediately.</span></span> <span data-ttu-id="0506a-263">Você também pode criar e manter um trabalho agendado sem um gatilho que é usado como modelo.</span><span class="sxs-lookup"><span data-stu-id="0506a-263">You can also create and maintain a scheduled job without a trigger that is used as a template.</span></span>

<span data-ttu-id="0506a-264">Para enviar uma tabela de hash, use as seguintes chaves:</span><span class="sxs-lookup"><span data-stu-id="0506a-264">To submit a hash table, use the following keys:</span></span>

- <span data-ttu-id="0506a-265">**Frequência** : diária, semanal, AtStartup, AtLogon</span><span class="sxs-lookup"><span data-stu-id="0506a-265">**Frequency** : Daily, Weekly, AtStartup, AtLogon</span></span>
- <span data-ttu-id="0506a-266">**Em** : qualquer cadeia de caracteres de tempo válida</span><span class="sxs-lookup"><span data-stu-id="0506a-266">**At** : Any valid time string</span></span>
- <span data-ttu-id="0506a-267">**DaysOfWeek** -qualquer combinação de nomes de dias</span><span class="sxs-lookup"><span data-stu-id="0506a-267">**DaysOfWeek** - Any combination of day names</span></span>
- <span data-ttu-id="0506a-268">**Intervalo** -qualquer intervalo de frequência válido</span><span class="sxs-lookup"><span data-stu-id="0506a-268">**Interval** - Any valid frequency interval</span></span>
- <span data-ttu-id="0506a-269">**RandomDelay** : qualquer cadeia de TimeSpan válida</span><span class="sxs-lookup"><span data-stu-id="0506a-269">**RandomDelay** : Any valid timespan string</span></span>
- <span data-ttu-id="0506a-270">**Usuário** : qualquer usuário válido.</span><span class="sxs-lookup"><span data-stu-id="0506a-270">**User** : Any valid user.</span></span> <span data-ttu-id="0506a-271">Usado somente com o valor de frequência AtLogon</span><span class="sxs-lookup"><span data-stu-id="0506a-271">Used only with the AtLogon frequency value</span></span>

<span data-ttu-id="0506a-272">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0506a-272">For example:</span></span>

`@{Frequency="Once"; At="3am"; DaysOfWeek="Monday", "Wednesday"; Interval=2; RandomDelay="30minutes"; User="Domain1\User01"}`

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0506a-273">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0506a-273">-WhatIf</span></span>

<span data-ttu-id="0506a-274">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="0506a-274">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="0506a-275">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="0506a-275">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="0506a-276">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0506a-276">CommonParameters</span></span>

<span data-ttu-id="0506a-277">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0506a-277">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0506a-278">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0506a-278">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0506a-279">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="0506a-279">INPUTS</span></span>

### <span data-ttu-id="0506a-280">Nenhum</span><span class="sxs-lookup"><span data-stu-id="0506a-280">None</span></span>

<span data-ttu-id="0506a-281">Você não pode enviar a entrada do pipeline para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0506a-281">You can't send input down the pipeline to this cmdlet.</span></span>

## <span data-ttu-id="0506a-282">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="0506a-282">OUTPUTS</span></span>

### <span data-ttu-id="0506a-283">Microsoft. PowerShell. ScheduledJob. ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="0506a-283">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>

## <span data-ttu-id="0506a-284">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="0506a-284">NOTES</span></span>

<span data-ttu-id="0506a-285">Cada trabalho agendado é salvo em um subdiretório do `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` diretório no computador local.</span><span class="sxs-lookup"><span data-stu-id="0506a-285">Each scheduled job is saved in a subdirectory of the `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` directory on the local computer.</span></span>
<span data-ttu-id="0506a-286">O subdiretório é nomeado para o trabalho agendado e contém um arquivo XML para o trabalho agendado e registros de seu histórico de execução.</span><span class="sxs-lookup"><span data-stu-id="0506a-286">The subdirectory is named for the scheduled job and contains an XML file for the scheduled job and records of its execution history.</span></span> <span data-ttu-id="0506a-287">Para obter mais informações sobre os trabalhos agendados no disco, consulte [about_Scheduled_Jobs_Advanced](./about/about_scheduled_jobs_advanced.md).</span><span class="sxs-lookup"><span data-stu-id="0506a-287">For more information about scheduled jobs on disk, see [about_Scheduled_Jobs_Advanced](./about/about_scheduled_jobs_advanced.md).</span></span>

<span data-ttu-id="0506a-288">Os trabalhos agendados que você cria no Windows PowerShell aparecem no Agendador de Tarefas na `Library\Microsoft\Windows\PowerShell\ScheduledJobs` pasta Agendador de tarefas.</span><span class="sxs-lookup"><span data-stu-id="0506a-288">Scheduled jobs that you create in Windows PowerShell appear in Task Scheduler in the Task Scheduler `Library\Microsoft\Windows\PowerShell\ScheduledJobs` folder.</span></span> <span data-ttu-id="0506a-289">Você pode usar o Agendador de tarefas para exibir e editar o trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="0506a-289">You can use Task Scheduler to view and edit the scheduled job.</span></span>

<span data-ttu-id="0506a-290">Você pode usar Agendador de Tarefas, a ferramenta de linha de comando **schtasks.exe** e os cmdlets Agendador de tarefas para gerenciar os trabalhos agendados que você cria com os cmdlets de trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="0506a-290">You can use Task Scheduler, the **schtasks.exe** command-line tool, and the Task Scheduler cmdlets to manage scheduled jobs that you create with the Scheduled Job cmdlets.</span></span> <span data-ttu-id="0506a-291">No entanto, você não pode usar os cmdlets do trabalho agendado para gerenciar tarefas que você cria no Agendador de Tarefas.</span><span class="sxs-lookup"><span data-stu-id="0506a-291">However, you can't use the Scheduled Job cmdlets to manage tasks that you create in Task Scheduler.</span></span>

<span data-ttu-id="0506a-292">Se um comando de trabalho agendado falha, o Windows PowerShell retorna uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="0506a-292">If a scheduled job command fails, Windows PowerShell returns an error message.</span></span> <span data-ttu-id="0506a-293">No entanto, se o trabalho falhar quando Agendador de Tarefas tentar executá-lo, o erro não estará disponível para o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0506a-293">However, if the job fails when Task Scheduler tries to run it, the error isn't available to Windows PowerShell.</span></span>

<span data-ttu-id="0506a-294">Se um trabalho agendado não for executado, use os seguintes métodos para encontrar o motivo:</span><span class="sxs-lookup"><span data-stu-id="0506a-294">If a scheduled job doesn't run, use the following methods to find the reason:</span></span>

- <span data-ttu-id="0506a-295">Verifique se o gatilho do trabalho está definido corretamente.</span><span class="sxs-lookup"><span data-stu-id="0506a-295">Verify that the job trigger is set properly.</span></span>
  - <span data-ttu-id="0506a-296">Verifique se as condições definidas nas opções de trabalho estão satisfeitas.</span><span class="sxs-lookup"><span data-stu-id="0506a-296">Verify that the conditions set in the job options are satisfied.</span></span>
- <span data-ttu-id="0506a-297">Verifique se a conta de usuário sob a qual o trabalho é executado tem permissão para executar os comandos ou scripts no trabalho.</span><span class="sxs-lookup"><span data-stu-id="0506a-297">Verify that the user account under which the job runs has permission to run the commands or scripts in the job.</span></span>
- <span data-ttu-id="0506a-298">Verifique se há erros no histórico de Agendador de Tarefas.</span><span class="sxs-lookup"><span data-stu-id="0506a-298">Check the Task Scheduler history for errors.</span></span>
- <span data-ttu-id="0506a-299">Verifique se há erros na Agendador de Tarefas log de eventos.</span><span class="sxs-lookup"><span data-stu-id="0506a-299">Check the Task Scheduler event log for errors.</span></span>

<span data-ttu-id="0506a-300">Para obter mais informações, consulte [about_Scheduled_Jobs_Troubleshooting](./about/about_scheduled_jobs_troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="0506a-300">For more information, see [about_Scheduled_Jobs_Troubleshooting](./about/about_scheduled_jobs_troubleshooting.md).</span></span>

## <span data-ttu-id="0506a-301">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="0506a-301">RELATED LINKS</span></span>

[<span data-ttu-id="0506a-302">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0506a-302">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="0506a-303">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0506a-303">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="0506a-304">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0506a-304">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="0506a-305">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0506a-305">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="0506a-306">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0506a-306">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="0506a-307">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0506a-307">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="0506a-308">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0506a-308">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="0506a-309">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="0506a-309">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="0506a-310">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0506a-310">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="0506a-311">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="0506a-311">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="0506a-312">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0506a-312">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="0506a-313">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0506a-313">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="0506a-314">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="0506a-314">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="0506a-315">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0506a-315">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="0506a-316">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="0506a-316">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="0506a-317">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="0506a-317">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
