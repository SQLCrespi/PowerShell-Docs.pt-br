---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/start-job?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Job
ms.openlocfilehash: 7875419bed68251628b072a35d6c220e75b78c24
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193434"
---
# <span data-ttu-id="92d08-103">Start-Job</span><span class="sxs-lookup"><span data-stu-id="92d08-103">Start-Job</span></span>

## <span data-ttu-id="92d08-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="92d08-104">SYNOPSIS</span></span>
<span data-ttu-id="92d08-105">Inicia um trabalho em segundo plano do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="92d08-105">Starts a PowerShell background job.</span></span>

## <span data-ttu-id="92d08-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="92d08-106">SYNTAX</span></span>

### <span data-ttu-id="92d08-107">ComputerName (padrão)</span><span class="sxs-lookup"><span data-stu-id="92d08-107">ComputerName (Default)</span></span>

```
Start-Job [-Name <String>] [-ScriptBlock] <ScriptBlock> [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>]
 [-WorkingDirectory <String>] [-RunAs32] [-PSVersion <Version>] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="92d08-108">Definitionname</span><span class="sxs-lookup"><span data-stu-id="92d08-108">DefinitionName</span></span>

```
Start-Job [-DefinitionName] <String> [[-DefinitionPath] <String>] [[-Type] <String>]
 [-WorkingDirectory <String>] [<CommonParameters>]
```

### <span data-ttu-id="92d08-109">FilePathComputerName</span><span class="sxs-lookup"><span data-stu-id="92d08-109">FilePathComputerName</span></span>

```
Start-Job [-Name <String>] [-Credential <PSCredential>] [-FilePath] <String>
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>]
 [-WorkingDirectory <String>] [-RunAs32] [-PSVersion <Version>] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="92d08-110">LiteralFilePathComputerName</span><span class="sxs-lookup"><span data-stu-id="92d08-110">LiteralFilePathComputerName</span></span>

```
Start-Job [-Name <String>] [-Credential <PSCredential>] -LiteralPath <String>
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>]
 [-WorkingDirectory <String>] [-RunAs32] [-PSVersion <Version>] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

## <span data-ttu-id="92d08-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="92d08-111">DESCRIPTION</span></span>

<span data-ttu-id="92d08-112">O `Start-Job` cmdlet inicia um trabalho em segundo plano do PowerShell no computador local.</span><span class="sxs-lookup"><span data-stu-id="92d08-112">The `Start-Job` cmdlet starts a PowerShell background job on the local computer.</span></span>

<span data-ttu-id="92d08-113">Um trabalho em segundo plano do PowerShell executa um comando sem interagir com a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="92d08-113">A PowerShell background job runs a command without interacting with the current session.</span></span> <span data-ttu-id="92d08-114">Quando você inicia um trabalho em segundo plano, um objeto de trabalho retorna imediatamente, mesmo se o trabalho levar um tempo estendido para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="92d08-114">When you start a background job, a job object returns immediately, even if the job takes an extended time to finish.</span></span> <span data-ttu-id="92d08-115">É possível continuar a trabalhar na sessão sem interrupção enquanto o trabalho é executado.</span><span class="sxs-lookup"><span data-stu-id="92d08-115">You can continue to work in the session without interruption while the job runs.</span></span>

<span data-ttu-id="92d08-116">O objeto de trabalho contém informações úteis sobre o trabalho, mas não contém os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="92d08-116">The job object contains useful information about the job, but it doesn't contain the job results.</span></span>
<span data-ttu-id="92d08-117">Quando o trabalho for concluído, use o `Receive-Job` cmdlet para obter os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="92d08-117">When the job finishes, use the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="92d08-118">Para obter mais informações sobre trabalhos em segundo plano, consulte [about_Jobs](./About/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="92d08-118">For more information about background jobs, see [about_Jobs](./About/about_Jobs.md).</span></span>

<span data-ttu-id="92d08-119">Para executar um trabalho em segundo plano em um computador remoto, use o parâmetro **AsJob** que está disponível em muitos cmdlets ou use o `Invoke-Command` cmdlet para executar um `Start-Job` comando no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="92d08-119">To run a background job on a remote computer, use the **AsJob** parameter that is available on many cmdlets, or use the `Invoke-Command` cmdlet to run a `Start-Job` command on the remote computer.</span></span> <span data-ttu-id="92d08-120">Para obter mais informações, consulte [about_Remote_Jobs](./About/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="92d08-120">For more information, see [about_Remote_Jobs](./About/about_Remote_Jobs.md).</span></span>

<span data-ttu-id="92d08-121">A partir do PowerShell 3,0, `Start-Job` o pode iniciar instâncias de tipos de trabalho personalizados, como trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="92d08-121">Starting in PowerShell 3.0, `Start-Job` can start instances of custom job types, such as scheduled jobs.</span></span> <span data-ttu-id="92d08-122">Para obter informações sobre como usar `Start-Job` o para iniciar trabalhos com tipos personalizados, consulte os documentos de ajuda para o recurso tipo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="92d08-122">For information about how to use `Start-Job` to start jobs with custom types, see the help documents for the job type feature.</span></span>

<span data-ttu-id="92d08-123">A partir do PowerShell 6,0, você pode iniciar trabalhos usando o operador de plano de fundo e comercial ( `&` ).</span><span class="sxs-lookup"><span data-stu-id="92d08-123">Beginning in PowerShell 6.0, you can start jobs using the ampersand (`&`) background operator.</span></span> <span data-ttu-id="92d08-124">A funcionalidade do operador de segundo plano é semelhante a `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="92d08-124">The functionality of the background operator is similar to `Start-Job`.</span></span> <span data-ttu-id="92d08-125">Os dois métodos para iniciar um trabalho criam um objeto de trabalho **PSRemotingJob** .</span><span class="sxs-lookup"><span data-stu-id="92d08-125">Both methods to start a job create a **PSRemotingJob** job object.</span></span> <span data-ttu-id="92d08-126">Para obter mais informações sobre como usar o e comercial ( `&` ), consulte [about_Operators](./about/about_operators.md#background-operator-).</span><span class="sxs-lookup"><span data-stu-id="92d08-126">For more information about using the ampersand (`&`), see [about_Operators](./about/about_operators.md#background-operator-).</span></span>

<span data-ttu-id="92d08-127">O PowerShell 7 introduziu o parâmetro **WorkingDirectory** que especifica o diretório de trabalho inicial de um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="92d08-127">PowerShell 7 introduced the **WorkingDirectory** parameter that specifies a background job's initial working directory.</span></span> <span data-ttu-id="92d08-128">Se o parâmetro não for especificado, `Start-Job` o padrão será o diretório de trabalho atual do chamador que iniciou o trabalho.</span><span class="sxs-lookup"><span data-stu-id="92d08-128">If the parameter isn't specified, `Start-Job` defaults to the current working directory of the caller that started the job.</span></span>

> [!NOTE]
> <span data-ttu-id="92d08-129">Não há suporte para a criação de um trabalho em segundo plano fora do processo `Start-Job` no cenário em que o PowerShell está sendo hospedado em outros aplicativos, como o Azure Functions do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="92d08-129">Creating an out-of-process background job with `Start-Job` is not supported in the scenario where PowerShell is being hosted in other applications, such as the PowerShell Azure Functions.</span></span>
>
> <span data-ttu-id="92d08-130">Isso ocorre por design porque `Start-Job` depende do `pwsh` executável a estar disponível em `$PSHOME` para iniciar um trabalho em segundo plano fora do processo, mas quando um aplicativo está hospedando o PowerShell, ele está diretamente usando os pacotes do SDK do NuGet do PowerShell e não será `pwsh` enviado junto.</span><span class="sxs-lookup"><span data-stu-id="92d08-130">This is by design because `Start-Job` depends on the `pwsh` executable to be available under `$PSHOME` to start an out-of-process background job, but when an application is hosting PowerShell, it's directly using the PowerShell NuGet SDK packages and won't have `pwsh` shipped along.</span></span>
>
> <span data-ttu-id="92d08-131">O substituto nesse cenário é `Start-ThreadJob` do módulo **[ThreadJob](https://www.powershellgallery.com/packages/ThreadJob)** .</span><span class="sxs-lookup"><span data-stu-id="92d08-131">The substitute in that scenario is `Start-ThreadJob` from the module **[ThreadJob](https://www.powershellgallery.com/packages/ThreadJob)** .</span></span>

## <span data-ttu-id="92d08-132">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="92d08-132">EXAMPLES</span></span>

### <span data-ttu-id="92d08-133">Exemplo 1: iniciar um trabalho em segundo plano</span><span class="sxs-lookup"><span data-stu-id="92d08-133">Example 1: Start a background job</span></span>

<span data-ttu-id="92d08-134">Este exemplo inicia um trabalho em segundo plano que é executado no computador local.</span><span class="sxs-lookup"><span data-stu-id="92d08-134">This example starts a background job that runs on the local computer.</span></span>

```powershell
Start-Job -ScriptBlock { Get-Process -Name pwsh }
```

```Output
Id  Name   PSJobTypeName   State     HasMoreData   Location    Command
--  ----   -------------   -----     -----------   --------    -------
1   Job1   BackgroundJob   Running   True          localhost   Get-Process -Name pwsh
```

<span data-ttu-id="92d08-135">`Start-Job` usa o parâmetro **scriptblock** para executar `Get-Process` como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="92d08-135">`Start-Job` uses the **ScriptBlock** parameter to run `Get-Process` as a background job.</span></span> <span data-ttu-id="92d08-136">O parâmetro **Name** especifica a localização de processos do PowerShell, `pwsh` .</span><span class="sxs-lookup"><span data-stu-id="92d08-136">The **Name** parameter specifies to find PowerShell processes, `pwsh`.</span></span> <span data-ttu-id="92d08-137">As informações do trabalho são exibidas e o PowerShell retorna a um prompt enquanto o trabalho é executado em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="92d08-137">The job information is displayed and PowerShell returns to a prompt while the job runs in the background.</span></span>

<span data-ttu-id="92d08-138">Para exibir a saída do trabalho, use o `Receive-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="92d08-138">To view the job's output, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="92d08-139">Por exemplo, `Receive-Job -Id 1`.</span><span class="sxs-lookup"><span data-stu-id="92d08-139">For example, `Receive-Job -Id 1`.</span></span>

### <span data-ttu-id="92d08-140">Exemplo 2: usar o operador em segundo plano para iniciar um trabalho em segundo plano</span><span class="sxs-lookup"><span data-stu-id="92d08-140">Example 2: Use the background operator to start a background job</span></span>

<span data-ttu-id="92d08-141">Este exemplo usa o operador de segundo e comercial ( `&` ) para iniciar um trabalho em segundo plano no computador local.</span><span class="sxs-lookup"><span data-stu-id="92d08-141">This example uses the ampersand (`&`) background operator to start a background job on the local computer.</span></span> <span data-ttu-id="92d08-142">O trabalho Obtém o mesmo resultado que `Start-Job` no exemplo 1.</span><span class="sxs-lookup"><span data-stu-id="92d08-142">The job gets the same result as `Start-Job` in Example 1.</span></span>

```powershell
Get-Process -Name pwsh &
```

```Output
Id    Name   PSJobTypeName   State       HasMoreData     Location      Command
--    ----   -------------   -----       -----------     --------      -------
5     Job5   BackgroundJob   Running     True            localhost     Microsoft.PowerShell.Man...
```

<span data-ttu-id="92d08-143">`Get-Process` usa o parâmetro **Name** para especificar processos do PowerShell, `pwsh` .</span><span class="sxs-lookup"><span data-stu-id="92d08-143">`Get-Process` uses the **Name** parameter to specify PowerShell processes, `pwsh`.</span></span> <span data-ttu-id="92d08-144">O e comercial ( `&` ) executa o comando como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="92d08-144">The ampersand (`&`) runs the command as a background job.</span></span> <span data-ttu-id="92d08-145">As informações do trabalho são exibidas e o PowerShell retorna a um prompt enquanto o trabalho é executado em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="92d08-145">The job information is displayed and PowerShell returns to a prompt while the job runs in the background.</span></span>

<span data-ttu-id="92d08-146">Para exibir a saída do trabalho, use o `Receive-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="92d08-146">To view the job's output, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="92d08-147">Por exemplo, `Receive-Job -Id 5`.</span><span class="sxs-lookup"><span data-stu-id="92d08-147">For example, `Receive-Job -Id 5`.</span></span>

### <span data-ttu-id="92d08-148">Exemplo 3: iniciar um trabalho usando Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="92d08-148">Example 3: Start a job using Invoke-Command</span></span>

<span data-ttu-id="92d08-149">Este exemplo executa um trabalho em vários computadores.</span><span class="sxs-lookup"><span data-stu-id="92d08-149">This example runs a job on multiple computers.</span></span> <span data-ttu-id="92d08-150">O trabalho é armazenado em uma variável e é executado usando o nome da variável na linha de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="92d08-150">The job is stored in a variable and is executed by using the variable name on the PowerShell command line.</span></span>

```powershell
$jobWRM = Invoke-Command -ComputerName (Get-Content -Path C:\Servers.txt) -ScriptBlock {
   Get-Service -Name WinRM } -JobName WinRM -ThrottleLimit 16 -AsJob
```

<span data-ttu-id="92d08-151">Um trabalho que usa `Invoke-Command` é criado e armazenado na `$jobWRM` variável.</span><span class="sxs-lookup"><span data-stu-id="92d08-151">A job that uses `Invoke-Command` is created and stored in the `$jobWRM` variable.</span></span> <span data-ttu-id="92d08-152">`Invoke-Command` usa o parâmetro **ComputerName** para especificar os computadores em que o trabalho é executado.</span><span class="sxs-lookup"><span data-stu-id="92d08-152">`Invoke-Command` uses the **ComputerName** parameter to specify the computers where the job runs.</span></span> <span data-ttu-id="92d08-153">`Get-Content` Obtém os nomes de servidor do `C:\Servers.txt` arquivo.</span><span class="sxs-lookup"><span data-stu-id="92d08-153">`Get-Content` gets the server names from the `C:\Servers.txt` file.</span></span>

<span data-ttu-id="92d08-154">O parâmetro **scriptblock** especifica um comando que `Get-Service` Obtém o serviço **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="92d08-154">The **ScriptBlock** parameter specifies a command that `Get-Service` gets the **WinRM** service.</span></span> <span data-ttu-id="92d08-155">O parâmetro **JobName** especifica um nome amigável para o trabalho, **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="92d08-155">The **JobName** parameter specifies a friendly name for the job, **WinRM** .</span></span> <span data-ttu-id="92d08-156">O parâmetro **ThrottleLimit** limita o número de comandos simultâneos a 16.</span><span class="sxs-lookup"><span data-stu-id="92d08-156">The **ThrottleLimit** parameter limits the number of concurrent commands to 16.</span></span> <span data-ttu-id="92d08-157">O parâmetro **AsJob** inicia um trabalho em segundo plano que executa o comando nos servidores.</span><span class="sxs-lookup"><span data-stu-id="92d08-157">The **AsJob** parameter starts a background job that runs the command on the servers.</span></span>

### <span data-ttu-id="92d08-158">Exemplo 4: obter informações do trabalho</span><span class="sxs-lookup"><span data-stu-id="92d08-158">Example 4: Get job information</span></span>

<span data-ttu-id="92d08-159">Este exemplo obtém informações sobre um trabalho e exibe os resultados de um trabalho concluído que foi executado no computador local.</span><span class="sxs-lookup"><span data-stu-id="92d08-159">This example gets information about a job and displays the results of a completed job that was run on the local computer.</span></span>

```powershell
$j = Start-Job -ScriptBlock { Get-WinEvent -Log System } -Credential Domain01\User01
$j | Select-Object -Property *
```

```Output
State         : Completed
HasMoreData   : True
StatusMessage :
Location      : localhost
Command       : Get-WinEvent -Log System
JobStateInfo  : Completed
Finished      : System.Threading.ManualResetEvent
InstanceId    : 27ce3fd9-40ed-488a-99e5-679cd91b9dd3
Id            : 18
Name          : Job18
ChildJobs     : {Job19}
PSBeginTime   : 8/8/2019 14:41:57
PSEndTime     : 8/8/2019 14:42:07
PSJobTypeName : BackgroundJob
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
Information   : {}
```

<span data-ttu-id="92d08-160">`Start-Job` usa o parâmetro **scriptblock** para executar um comando que especifica `Get-WinEvent` para obter o log do **sistema** .</span><span class="sxs-lookup"><span data-stu-id="92d08-160">`Start-Job` uses the **ScriptBlock** parameter to run a command that specifies `Get-WinEvent` to get the **System** log.</span></span> <span data-ttu-id="92d08-161">O parâmetro **Credential** especifica uma conta de usuário de domínio com permissão para executar o trabalho no computador.</span><span class="sxs-lookup"><span data-stu-id="92d08-161">The **Credential** parameter specifies a domain user account with permission to run the job on the computer.</span></span> <span data-ttu-id="92d08-162">O objeto de trabalho é armazenado na `$j` variável.</span><span class="sxs-lookup"><span data-stu-id="92d08-162">The job object is stored in the `$j` variable.</span></span>

<span data-ttu-id="92d08-163">O objeto na `$j` variável é enviado ao pipeline para `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="92d08-163">The object in the `$j` variable is sent down the pipeline to `Select-Object`.</span></span> <span data-ttu-id="92d08-164">O parâmetro **Property** especifica um asterisco ( `*` ) para exibir todas as propriedades do objeto de trabalho.</span><span class="sxs-lookup"><span data-stu-id="92d08-164">The **Property** parameter specifies an asterisk (`*`) to display all the job object's properties.</span></span>

### <span data-ttu-id="92d08-165">Exemplo 5: executar um script como um trabalho em segundo plano</span><span class="sxs-lookup"><span data-stu-id="92d08-165">Example 5: Run a script as a background job</span></span>

<span data-ttu-id="92d08-166">Neste exemplo, um script no computador local é executado como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="92d08-166">In this example, a script on the local computer is run as a background job.</span></span>

```powershell
Start-Job -FilePath C:\Scripts\Sample.ps1
```

<span data-ttu-id="92d08-167">`Start-Job` usa o parâmetro **FilePath** para especificar um arquivo de script armazenado no computador local.</span><span class="sxs-lookup"><span data-stu-id="92d08-167">`Start-Job` uses the **FilePath** parameter to specify a script file that's stored on the local computer.</span></span>

### <span data-ttu-id="92d08-168">Exemplo 6: obter um processo usando um trabalho em segundo plano</span><span class="sxs-lookup"><span data-stu-id="92d08-168">Example 6: Get a process using a background job</span></span>

<span data-ttu-id="92d08-169">Este exemplo usa um trabalho em segundo plano para obter um processo especificado por nome.</span><span class="sxs-lookup"><span data-stu-id="92d08-169">This example uses a background job to get a specified process by name.</span></span>

```powershell
Start-Job -Name PShellJob -ScriptBlock { Get-Process -Name PowerShell }
```

<span data-ttu-id="92d08-170">`Start-Job` usa o parâmetro **Name** para especificar um nome de trabalho amigável, **PShellJob** .</span><span class="sxs-lookup"><span data-stu-id="92d08-170">`Start-Job` uses the **Name** parameter to specify a friendly job name, **PShellJob** .</span></span> <span data-ttu-id="92d08-171">O parâmetro **scriptblock** especifica `Get-Process` para obter processos com o nome **PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="92d08-171">The **ScriptBlock** parameter specifies `Get-Process` to get processes with the name **PowerShell** .</span></span>

### <span data-ttu-id="92d08-172">Exemplo 7: coletar e salvar dados usando um trabalho em segundo plano</span><span class="sxs-lookup"><span data-stu-id="92d08-172">Example 7: Collect and save data by using a background job</span></span>

<span data-ttu-id="92d08-173">Este exemplo inicia um trabalho que coleta uma grande quantidade de dados de mapa e, em seguida, salva-o em um `.tif` arquivo.</span><span class="sxs-lookup"><span data-stu-id="92d08-173">This example starts a job that collects a large amount of map data and then saves it in a `.tif` file.</span></span>

```powershell
Start-Job -Name GetMappingFiles -InitializationScript {Import-Module MapFunctions} -ScriptBlock {
   Get-Map -Name * | Set-Content -Path D:\Maps.tif }
```

<span data-ttu-id="92d08-174">`Start-Job` usa o parâmetro **Name** para especificar um nome de trabalho amigável, **GetMappingFiles** .</span><span class="sxs-lookup"><span data-stu-id="92d08-174">`Start-Job` uses the **Name** parameter to specify a friendly job name, **GetMappingFiles** .</span></span> <span data-ttu-id="92d08-175">O parâmetro **initializationScript** executa um bloco de script que importa o módulo **MapFunctions** .</span><span class="sxs-lookup"><span data-stu-id="92d08-175">The **InitializationScript** parameter runs a script block that imports the **MapFunctions** module.</span></span> <span data-ttu-id="92d08-176">O parâmetro **scriptblock** executa `Get-Map` e `Set-Content` salva os dados no local especificado pelo parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="92d08-176">The **ScriptBlock** parameter runs `Get-Map` and `Set-Content` saves the data in the location specified by the **Path** parameter.</span></span>

### <span data-ttu-id="92d08-177">Exemplo 8: passar entrada para um trabalho em segundo plano</span><span class="sxs-lookup"><span data-stu-id="92d08-177">Example 8: Pass input to a background job</span></span>

<span data-ttu-id="92d08-178">Este exemplo usa a `$input` variável automática para processar um objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="92d08-178">This example uses the `$input` automatic variable to process an input object.</span></span> <span data-ttu-id="92d08-179">Use `Receive-Job` para exibir a saída do trabalho.</span><span class="sxs-lookup"><span data-stu-id="92d08-179">Use `Receive-Job` to view the job's output.</span></span>

```powershell
Start-Job -ScriptBlock { Get-Content $input } -InputObject "C:\Servers.txt"
Receive-Job -Name Job45 -Keep
```

```Output
Server01
Server02
Server03
Server04
```

<span data-ttu-id="92d08-180">`Start-Job` usa o parâmetro **scriptblock** para executar `Get-Content` com a `$input` variável automática.</span><span class="sxs-lookup"><span data-stu-id="92d08-180">`Start-Job` uses the **ScriptBlock** parameter to run `Get-Content` with the `$input` automatic variable.</span></span> <span data-ttu-id="92d08-181">A `$input` variável obtém objetos do parâmetro **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="92d08-181">The `$input` variable gets objects from the **InputObject** parameter.</span></span> <span data-ttu-id="92d08-182">`Receive-Job` usa o parâmetro **Name** para especificar o trabalho e gera os resultados.</span><span class="sxs-lookup"><span data-stu-id="92d08-182">`Receive-Job` uses the **Name** parameter to specify the job and outputs the results.</span></span> <span data-ttu-id="92d08-183">O parâmetro **Keep** salva a saída do trabalho para que possa ser exibido novamente durante a sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="92d08-183">The **Keep** parameter saves the job output so it can be viewed again during the PowerShell session.</span></span>

### <span data-ttu-id="92d08-184">Exemplo 9: definir o diretório de trabalho para um trabalho em segundo plano</span><span class="sxs-lookup"><span data-stu-id="92d08-184">Example 9: Set the working directory for a background job</span></span>

<span data-ttu-id="92d08-185">O **WorkingDirectory** permite que você especifique um diretório alternativo para um trabalho do qual você pode executar scripts ou abrir arquivos.</span><span class="sxs-lookup"><span data-stu-id="92d08-185">The **WorkingDirectory** allows you to specify an alternate directory for a job from which you can run scripts or open files.</span></span> <span data-ttu-id="92d08-186">Neste exemplo, o trabalho em segundo plano especifica um diretório de trabalho diferente do local do diretório atual.</span><span class="sxs-lookup"><span data-stu-id="92d08-186">In this example, the background job specifies a working directory that's different than the current directory location.</span></span>

```
PS C:\Test> Start-Job -WorkingDirectory C:\Test\Scripts { $PWD } | Receive-Job -AutoRemoveJob -Wait

Path
----
C:\Test\Scripts
```

<span data-ttu-id="92d08-187">O diretório de trabalho atual deste exemplo é `C:\Test` .</span><span class="sxs-lookup"><span data-stu-id="92d08-187">This example's current working directory is `C:\Test`.</span></span> <span data-ttu-id="92d08-188">`Start-Job` usa o parâmetro **WorkingDirectory** para especificar o diretório de trabalho do trabalho.</span><span class="sxs-lookup"><span data-stu-id="92d08-188">`Start-Job` uses the **WorkingDirectory** parameter to specify the job's working directory.</span></span> <span data-ttu-id="92d08-189">O parâmetro **scriptblock** usa `$PWD` para exibir o diretório de trabalho do trabalho.</span><span class="sxs-lookup"><span data-stu-id="92d08-189">The **ScriptBlock** parameter uses `$PWD` to display the job's working directory.</span></span> <span data-ttu-id="92d08-190">`Receive-Job` exibe a saída do trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="92d08-190">`Receive-Job` displays the background job's output.</span></span>
<span data-ttu-id="92d08-191">**AutoRemoveJob** exclui o trabalho e **Wait** suprime o prompt de comando até que todos os resultados sejam recebidos.</span><span class="sxs-lookup"><span data-stu-id="92d08-191">**AutoRemoveJob** deletes the job and **Wait** suppresses the command prompt until all results are received.</span></span>

### <span data-ttu-id="92d08-192">Exemplo 10: usar o parâmetro ArgumentList para especificar uma matriz</span><span class="sxs-lookup"><span data-stu-id="92d08-192">Example 10: Use the ArgumentList parameter to specify an array</span></span>

<span data-ttu-id="92d08-193">Este exemplo usa o parâmetro **ArgumentList** para especificar uma matriz de argumentos.</span><span class="sxs-lookup"><span data-stu-id="92d08-193">This example uses the **ArgumentList** parameter to specify an array of arguments.</span></span> <span data-ttu-id="92d08-194">A matriz é uma lista separada por vírgulas de nomes de processo.</span><span class="sxs-lookup"><span data-stu-id="92d08-194">The array is a comma-separated list of process names.</span></span>

```powershell
Start-Job -ScriptBlock { Get-Process -Name $args } -ArgumentList powershell, pwsh, notepad
```

```Output
Id     Name      PSJobTypeName   State       HasMoreData     Location     Command
--     ----      -------------   -----       -----------     --------     -------
1      Job1      BackgroundJob   Running     True            localhost    Get-Process -Name $args
```

<span data-ttu-id="92d08-195">O `Start-Job` cmdlet usa o parâmetro **scriptblock** para executar um comando.</span><span class="sxs-lookup"><span data-stu-id="92d08-195">The `Start-Job` cmdlet uses the **ScriptBlock** parameter to run a command.</span></span> <span data-ttu-id="92d08-196">`Get-Process` usa o parâmetro **Name** para especificar a variável automática `$args` .</span><span class="sxs-lookup"><span data-stu-id="92d08-196">`Get-Process` uses the **Name** parameter to specify the automatic variable `$args`.</span></span> <span data-ttu-id="92d08-197">O parâmetro **ArgumentList** passa a matriz de nomes de processo para `$args` .</span><span class="sxs-lookup"><span data-stu-id="92d08-197">The **ArgumentList** parameter passes the array of process names to `$args`.</span></span> <span data-ttu-id="92d08-198">Os nomes de processo PowerShell, pwsh e Notepad são processos em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="92d08-198">The process names powershell, pwsh, and notepad are processes running on the local computer.</span></span>

<span data-ttu-id="92d08-199">Para exibir a saída do trabalho, use o `Receive-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="92d08-199">To view the job's output, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="92d08-200">Por exemplo, `Receive-Job -Id 1`.</span><span class="sxs-lookup"><span data-stu-id="92d08-200">For example, `Receive-Job -Id 1`.</span></span>

### <span data-ttu-id="92d08-201">Exemplo 11: executar o trabalho em um Windows PowerShell 5,1</span><span class="sxs-lookup"><span data-stu-id="92d08-201">Example 11: Run job in a Windows PowerShell 5.1</span></span>

<span data-ttu-id="92d08-202">Este exemplo usa o parâmetro **psversion** com o valor **5,1** para executar o trabalho em uma sessão do Windows PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="92d08-202">This example uses the **PSVersion** parameter with value **5.1** to run job in a Windows PowerShell 5.1 session.</span></span>

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Patch  PreReleaseLabel BuildLabel
-----  -----  -----  --------------- ----------
7      0      0      rc.1
```

```powershell
$job = Start-Job { $PSVersionTable.PSVersion } -PSVersion 5.1
Receive-Job $job
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      14393  3383
```

## <span data-ttu-id="92d08-203">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="92d08-203">PARAMETERS</span></span>

### <span data-ttu-id="92d08-204">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="92d08-204">-ArgumentList</span></span>

<span data-ttu-id="92d08-205">Especifica uma matriz de argumentos, ou valores de parâmetro, para o script que é especificado pelo parâmetro **FilePath** ou um comando especificado com o parâmetro **scriptblock** .</span><span class="sxs-lookup"><span data-stu-id="92d08-205">Specifies an array of arguments, or parameter values, for the script that is specified by the **FilePath** parameter or a command specified with the **ScriptBlock** parameter.</span></span>

<span data-ttu-id="92d08-206">Os argumentos devem ser passados para **ArgumentList** como argumento de matriz de dimensão única.</span><span class="sxs-lookup"><span data-stu-id="92d08-206">Arguments must be passed to **ArgumentList** as single-dimension array argument.</span></span> <span data-ttu-id="92d08-207">Por exemplo, uma lista separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="92d08-207">For example, a comma-separated list.</span></span> <span data-ttu-id="92d08-208">Para obter mais informações sobre o comportamento de **ArgumentList** , consulte [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="92d08-208">For more information about the behavior of **ArgumentList** , see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="92d08-209">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="92d08-209">-Authentication</span></span>

<span data-ttu-id="92d08-210">Especifica o mecanismo usado para autenticar as credenciais do usuário.</span><span class="sxs-lookup"><span data-stu-id="92d08-210">Specifies the mechanism that is used to authenticate user credentials.</span></span>

<span data-ttu-id="92d08-211">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="92d08-211">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="92d08-212">Padrão</span><span class="sxs-lookup"><span data-stu-id="92d08-212">Default</span></span>
- <span data-ttu-id="92d08-213">Básico</span><span class="sxs-lookup"><span data-stu-id="92d08-213">Basic</span></span>
- <span data-ttu-id="92d08-214">CredSSP</span><span class="sxs-lookup"><span data-stu-id="92d08-214">Credssp</span></span>
- <span data-ttu-id="92d08-215">Digest</span><span class="sxs-lookup"><span data-stu-id="92d08-215">Digest</span></span>
- <span data-ttu-id="92d08-216">Kerberos</span><span class="sxs-lookup"><span data-stu-id="92d08-216">Kerberos</span></span>
- <span data-ttu-id="92d08-217">Negotiate</span><span class="sxs-lookup"><span data-stu-id="92d08-217">Negotiate</span></span>
- <span data-ttu-id="92d08-218">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="92d08-218">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="92d08-219">O valor padrão é Default.</span><span class="sxs-lookup"><span data-stu-id="92d08-219">The default value is Default.</span></span>

<span data-ttu-id="92d08-220">A autenticação CredSSP está disponível somente no Windows Vista, no Windows Server 2008 e em versões posteriores do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="92d08-220">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="92d08-221">Para obter mais informações sobre os valores desse parâmetro, consulte [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="92d08-221">For more information about the values of this parameter, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="92d08-222">A autenticação CredSSP (Credencial Security Support Provider), na qual as credenciais do usuário são passadas a um computador remoto para autenticação, foi projetada para comandos que exijam autenticação em mais de um recurso, como acessar um compartilhamento de rede remota.</span><span class="sxs-lookup"><span data-stu-id="92d08-222">Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="92d08-223">Esse mecanismo aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="92d08-223">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="92d08-224">Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="92d08-224">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="92d08-225">-Credential</span><span class="sxs-lookup"><span data-stu-id="92d08-225">-Credential</span></span>

<span data-ttu-id="92d08-226">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="92d08-226">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="92d08-227">Se o parâmetro **Credential** não for especificado, o comando usará as credenciais do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="92d08-227">If the **Credential** parameter isn't specified, the command uses the current user's credentials.</span></span>

<span data-ttu-id="92d08-228">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="92d08-228">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="92d08-229">Se você digitar um nome de usuário, você será solicitado a inserir a senha.</span><span class="sxs-lookup"><span data-stu-id="92d08-229">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="92d08-230">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="92d08-230">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="92d08-231">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="92d08-231">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="92d08-232">-Definitionname</span><span class="sxs-lookup"><span data-stu-id="92d08-232">-DefinitionName</span></span>

<span data-ttu-id="92d08-233">Especifica o nome da definição do trabalho que este cmdlet inicia.</span><span class="sxs-lookup"><span data-stu-id="92d08-233">Specifies the definition name of the job that this cmdlet starts.</span></span> <span data-ttu-id="92d08-234">Use este parâmetro para iniciar tipos de trabalho personalizados que têm um nome de definição, como trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="92d08-234">Use this parameter to start custom job types that have a definition name, such as scheduled jobs.</span></span>

<span data-ttu-id="92d08-235">Quando você usa `Start-Job` o para iniciar uma instância de um trabalho agendado, o trabalho é iniciado imediatamente, independentemente dos gatilhos de trabalho ou das opções de trabalho.</span><span class="sxs-lookup"><span data-stu-id="92d08-235">When you use `Start-Job` to start an instance of a scheduled job, the job starts immediately, regardless of job triggers or job options.</span></span> <span data-ttu-id="92d08-236">A instância de trabalho resultante é um trabalho agendado, mas não é salva em disco, como trabalhos agendados disparados.</span><span class="sxs-lookup"><span data-stu-id="92d08-236">The resulting job instance is a scheduled job, but it isn't saved to disk like triggered scheduled jobs.</span></span> <span data-ttu-id="92d08-237">Você não pode usar o parâmetro **ArgumentList** de `Start-Job` para fornecer valores para parâmetros de scripts que são executados em um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="92d08-237">You can't use the **ArgumentList** parameter of `Start-Job` to provide values for parameters of scripts that run in a scheduled job.</span></span>

<span data-ttu-id="92d08-238">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="92d08-238">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="92d08-239">-DefinitionPath</span><span class="sxs-lookup"><span data-stu-id="92d08-239">-DefinitionPath</span></span>

<span data-ttu-id="92d08-240">Especifica o caminho da definição para o trabalho que este cmdlet inicia.</span><span class="sxs-lookup"><span data-stu-id="92d08-240">Specifies path of the definition for the job that this cmdlet starts.</span></span> <span data-ttu-id="92d08-241">Insira o caminho de definição.</span><span class="sxs-lookup"><span data-stu-id="92d08-241">Enter the definition path.</span></span> <span data-ttu-id="92d08-242">A concatenação dos valores dos parâmetros **DefinitionPath** e **definitionname** é o caminho totalmente qualificado da definição de trabalho.</span><span class="sxs-lookup"><span data-stu-id="92d08-242">The concatenation of the values of the **DefinitionPath** and **DefinitionName** parameters is the fully qualified path of the job definition.</span></span> <span data-ttu-id="92d08-243">Use este parâmetro para iniciar tipos de trabalho personalizados que têm um caminho de definição, como trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="92d08-243">Use this parameter to start custom job types that have a definition path, such as scheduled jobs.</span></span>

<span data-ttu-id="92d08-244">Para trabalhos agendados, o valor do parâmetro **DefinitionPath** é `$home\AppData\Local\Windows\PowerShell\ScheduledJob` .</span><span class="sxs-lookup"><span data-stu-id="92d08-244">For scheduled jobs, the value of the **DefinitionPath** parameter is `$home\AppData\Local\Windows\PowerShell\ScheduledJob`.</span></span>

<span data-ttu-id="92d08-245">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="92d08-245">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DefinitionName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="92d08-246">-FilePath</span><span class="sxs-lookup"><span data-stu-id="92d08-246">-FilePath</span></span>

<span data-ttu-id="92d08-247">Especifica um script local que `Start-Job` é executado como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="92d08-247">Specifies a local script that `Start-Job` runs as a background job.</span></span> <span data-ttu-id="92d08-248">Insira o caminho e o nome de arquivo do script ou use o pipeline para o qual enviar um caminho de script `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="92d08-248">Enter the path and file name of the script or use the pipeline to send a script path to `Start-Job`.</span></span> <span data-ttu-id="92d08-249">O script deve estar no computador local ou em uma pasta que o computador local possa acessar.</span><span class="sxs-lookup"><span data-stu-id="92d08-249">The script must be on the local computer or in a folder that the local computer can access.</span></span>

<span data-ttu-id="92d08-250">Quando você usa esse parâmetro, o PowerShell converte o conteúdo do arquivo de script especificado em um bloco de script e executa o bloco de script como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="92d08-250">When you use this parameter, PowerShell converts the contents of the specified script file to a script block and runs the script block as a background job.</span></span>

```yaml
Type: System.String
Parameter Sets: FilePathComputerName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="92d08-251">-InitializationScript</span><span class="sxs-lookup"><span data-stu-id="92d08-251">-InitializationScript</span></span>

<span data-ttu-id="92d08-252">Especifica os comandos que são executados antes do trabalho ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="92d08-252">Specifies commands that run before the job starts.</span></span> <span data-ttu-id="92d08-253">Para criar um bloco de script, coloque os comandos entre chaves ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="92d08-253">To create a script block, enclose the commands in curly braces (`{}`).</span></span>

<span data-ttu-id="92d08-254">Use esse parâmetro para preparar a sessão na qual o trabalho é executado.</span><span class="sxs-lookup"><span data-stu-id="92d08-254">Use this parameter to prepare the session in which the job runs.</span></span> <span data-ttu-id="92d08-255">Por exemplo, você pode usá-lo para adicionar funções, snap-ins e módulos à sessão.</span><span class="sxs-lookup"><span data-stu-id="92d08-255">For example, you can use it to add functions, snap-ins, and modules to the session.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="92d08-256">-InputObject</span><span class="sxs-lookup"><span data-stu-id="92d08-256">-InputObject</span></span>

<span data-ttu-id="92d08-257">Especifica a entrada para o comando.</span><span class="sxs-lookup"><span data-stu-id="92d08-257">Specifies input to the command.</span></span> <span data-ttu-id="92d08-258">Insira uma variável que contenha os objetos ou digite um comando ou uma expressão que gere os objetos.</span><span class="sxs-lookup"><span data-stu-id="92d08-258">Enter a variable that contains the objects, or type a command or expression that generates the objects.</span></span>

<span data-ttu-id="92d08-259">No valor do parâmetro **scriptblock** , use a `$input` variável automática para representar os objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="92d08-259">In the value of the **ScriptBlock** parameter, use the `$input` automatic variable to represent the input objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="92d08-260">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="92d08-260">-LiteralPath</span></span>

<span data-ttu-id="92d08-261">Especifica um script local que este cmdlet executa como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="92d08-261">Specifies a local script that this cmdlet runs as a background job.</span></span> <span data-ttu-id="92d08-262">Insira o caminho de um script no computador local.</span><span class="sxs-lookup"><span data-stu-id="92d08-262">Enter the path of a script on the local computer.</span></span>

<span data-ttu-id="92d08-263">`Start-Job` usa o valor do parâmetro **LiteralPath** exatamente como ele é digitado.</span><span class="sxs-lookup"><span data-stu-id="92d08-263">`Start-Job` uses the value of the **LiteralPath** parameter exactly as it's typed.</span></span> <span data-ttu-id="92d08-264">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="92d08-264">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="92d08-265">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="92d08-265">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="92d08-266">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="92d08-266">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralFilePathComputerName
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="92d08-267">-Name</span><span class="sxs-lookup"><span data-stu-id="92d08-267">-Name</span></span>

<span data-ttu-id="92d08-268">Especifica um nome amigável para o novo trabalho.</span><span class="sxs-lookup"><span data-stu-id="92d08-268">Specifies a friendly name for the new job.</span></span> <span data-ttu-id="92d08-269">Você pode usar o nome para identificar o trabalho para outros cmdlets de trabalho, como o `Stop-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="92d08-269">You can use the name to identify the job to other job cmdlets, such as the `Stop-Job` cmdlet.</span></span>

<span data-ttu-id="92d08-270">O nome amigável padrão é `Job#` , em que `#` é um número ordinal que é incrementado para cada trabalho.</span><span class="sxs-lookup"><span data-stu-id="92d08-270">The default friendly name is `Job#`, where `#` is an ordinal number that is incremented for each job.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="92d08-271">-PSVersion</span><span class="sxs-lookup"><span data-stu-id="92d08-271">-PSVersion</span></span>

<span data-ttu-id="92d08-272">Especifica uma versão do PowerShell a ser usada para executar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="92d08-272">Specifies a version of PowerShell to use for running the job.</span></span>
<span data-ttu-id="92d08-273">Quando o valor de **psversion** é **5,1** , o trabalho é executado em uma sessão do Windows PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="92d08-273">When the value of **PSVersion** is **5.1** The job is run in a Windows PowerShell 5.1 session.</span></span>
<span data-ttu-id="92d08-274">Para qualquer outro valor, o trabalho é executado usando a versão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="92d08-274">For any other value, the job is run using the current version of PowerShell.</span></span>

<span data-ttu-id="92d08-275">Esse parâmetro foi adicionado no PowerShell 7 e funciona apenas no Windows.</span><span class="sxs-lookup"><span data-stu-id="92d08-275">This parameter was added in PowerShell 7 and only works on Windows.</span></span>

```yaml
Type: System.Version
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="92d08-276">-RunAs32</span><span class="sxs-lookup"><span data-stu-id="92d08-276">-RunAs32</span></span>

<span data-ttu-id="92d08-277">A partir do PowerShell 7, o parâmetro **RunAs32** não funciona no powershell de 64 bits ( `pwsh` ).</span><span class="sxs-lookup"><span data-stu-id="92d08-277">Beginning with PowerShell 7, the **RunAs32** parameter doesn't work on 64-bit PowerShell (`pwsh`).</span></span>
<span data-ttu-id="92d08-278">Se **RunAs32** for especificado no PowerShell de 64 bits, `Start-Job` o lançará um erro de exceção de encerramento.</span><span class="sxs-lookup"><span data-stu-id="92d08-278">If **RunAs32** is specified in 64-bit PowerShell, `Start-Job` throws a terminating exception error.</span></span>
<span data-ttu-id="92d08-279">Para iniciar um processo do PowerShell () de 32 bits `pwsh` com o **RunAs32** , você precisa ter o PowerShell de 32 bits instalado.</span><span class="sxs-lookup"><span data-stu-id="92d08-279">To start a 32-bit PowerShell (`pwsh`) process with **RunAs32** , you need to have the 32-bit PowerShell installed.</span></span>

<span data-ttu-id="92d08-280">No PowerShell de 32 bits, o **RunAs32** força o trabalho a ser executado em um processo de 32 bits, mesmo em um sistema operacional de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="92d08-280">In 32-bit PowerShell, **RunAs32** forces the job to run in a 32-bit process, even on a 64-bit operating system.</span></span>

<span data-ttu-id="92d08-281">Nas versões de 64 bits do Windows 7 e do Windows Server 2008 R2, quando o `Start-Job` comando inclui o parâmetro **RunAs32** , você não pode usar o parâmetro **Credential** para especificar as credenciais de outro usuário.</span><span class="sxs-lookup"><span data-stu-id="92d08-281">On 64-bit versions of Windows 7 and Windows Server 2008 R2, when the `Start-Job` command includes the **RunAs32** parameter, you can't use the **Credential** parameter to specify the credentials of another user.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="92d08-282">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="92d08-282">-ScriptBlock</span></span>

<span data-ttu-id="92d08-283">Especifica os comandos a executar no trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="92d08-283">Specifies the commands to run in the background job.</span></span> <span data-ttu-id="92d08-284">Para criar um bloco de script, coloque os comandos entre chaves ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="92d08-284">To create a script block, enclose the commands in curly braces (`{}`).</span></span> <span data-ttu-id="92d08-285">Use a `$input` variável automática para acessar o valor do parâmetro **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="92d08-285">Use the `$input` automatic variable to access the value of the **InputObject** parameter.</span></span> <span data-ttu-id="92d08-286">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="92d08-286">This parameter is required.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ComputerName
Aliases: Command

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="92d08-287">-Type</span><span class="sxs-lookup"><span data-stu-id="92d08-287">-Type</span></span>

<span data-ttu-id="92d08-288">Especifica o tipo personalizado para trabalhos iniciados por `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="92d08-288">Specifies the custom type for jobs started by `Start-Job`.</span></span> <span data-ttu-id="92d08-289">Insira um nome de tipo de trabalho personalizado como PSScheduledJob para trabalhos agendados, ou PSWorkflowJob para tarefas de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="92d08-289">Enter a custom job type name, such as PSScheduledJob for scheduled jobs or PSWorkflowJob for workflows jobs.</span></span> <span data-ttu-id="92d08-290">Esse parâmetro não é válido para trabalhos em segundo plano padrão.</span><span class="sxs-lookup"><span data-stu-id="92d08-290">This parameter isn't valid for standard background jobs.</span></span>

<span data-ttu-id="92d08-291">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="92d08-291">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DefinitionName
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="92d08-292">-WorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="92d08-292">-WorkingDirectory</span></span>

<span data-ttu-id="92d08-293">Especifica o diretório de trabalho inicial do trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="92d08-293">Specifies the initial working directory of the background job.</span></span> <span data-ttu-id="92d08-294">Se o parâmetro não for especificado, o trabalho será executado a partir do local padrão.</span><span class="sxs-lookup"><span data-stu-id="92d08-294">If the parameter isn't specified, the job runs from the default location.</span></span> <span data-ttu-id="92d08-295">O local padrão é o diretório de trabalho atual do chamador que iniciou o trabalho.</span><span class="sxs-lookup"><span data-stu-id="92d08-295">The default location is the current working directory of the caller that started the job.</span></span>

<span data-ttu-id="92d08-296">Esse parâmetro foi introduzido no PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="92d08-296">This parameter was introduced in PowerShell 7.</span></span>

```yaml
Type: System.String
Parameter Sets: All
Aliases:

Required: False
Position: Named
Default value: $HOME on Unix (macOS, Linux) and $HOME\Documents on Windows
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="92d08-297">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="92d08-297">CommonParameters</span></span>

<span data-ttu-id="92d08-298">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="92d08-298">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="92d08-299">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="92d08-299">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="92d08-300">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="92d08-300">INPUTS</span></span>

### <span data-ttu-id="92d08-301">System.String</span><span class="sxs-lookup"><span data-stu-id="92d08-301">System.String</span></span>

<span data-ttu-id="92d08-302">Você pode usar o pipeline para enviar um objeto com a propriedade **Name** para o parâmetro **Name** .</span><span class="sxs-lookup"><span data-stu-id="92d08-302">You can use the pipeline to send an object with the **Name** property to the **Name** parameter.</span></span> <span data-ttu-id="92d08-303">Por exemplo, você pode canalizar um objeto **FileInfo** de `Get-ChildItem` para `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="92d08-303">For example, you can pipeline a **FileInfo** object from `Get-ChildItem` to `Start-Job`.</span></span>

## <span data-ttu-id="92d08-304">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="92d08-304">OUTPUTS</span></span>

### <span data-ttu-id="92d08-305">System. Management. Automation. PSRemotingJob</span><span class="sxs-lookup"><span data-stu-id="92d08-305">System.Management.Automation.PSRemotingJob</span></span>

<span data-ttu-id="92d08-306">`Start-Job` Retorna um objeto **PSRemotingJob** que representa o trabalho que ele iniciou.</span><span class="sxs-lookup"><span data-stu-id="92d08-306">`Start-Job` returns a **PSRemotingJob** object that represents the job that it started.</span></span>

## <span data-ttu-id="92d08-307">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="92d08-307">NOTES</span></span>

<span data-ttu-id="92d08-308">Para ser executado em segundo plano, `Start-Job` o é executado em sua própria sessão na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="92d08-308">To run in the background, `Start-Job` runs in its own session in the current session.</span></span> <span data-ttu-id="92d08-309">Quando você usa o `Invoke-Command` cmdlet para executar um `Start-Job` comando em uma sessão em um computador remoto, `Start-Job` o é executado em uma sessão na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="92d08-309">When you use the `Invoke-Command` cmdlet to run a `Start-Job` command in a session on a remote computer, `Start-Job` runs in a session in the remote session.</span></span>

## <span data-ttu-id="92d08-310">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="92d08-310">RELATED LINKS</span></span>

[<span data-ttu-id="92d08-311">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="92d08-311">about_Arrays</span></span>](./about/about_arrays.md)

[<span data-ttu-id="92d08-312">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="92d08-312">about_Automatic_Variables</span></span>](./about/about_automatic_variables.md)

[<span data-ttu-id="92d08-313">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="92d08-313">about_Jobs</span></span>](./About/about_Jobs.md)

[<span data-ttu-id="92d08-314">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="92d08-314">about_Job_Details</span></span>](./About/about_Job_Details.md)

[<span data-ttu-id="92d08-315">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="92d08-315">about_Remote_Jobs</span></span>](./About/about_Remote_Jobs.md)

[<span data-ttu-id="92d08-316">Get-Job</span><span class="sxs-lookup"><span data-stu-id="92d08-316">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="92d08-317">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="92d08-317">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="92d08-318">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="92d08-318">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="92d08-319">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="92d08-319">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="92d08-320">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="92d08-320">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="92d08-321">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="92d08-321">Wait-Job</span></span>](Wait-Job.md)
