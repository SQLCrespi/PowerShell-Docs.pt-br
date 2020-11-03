---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/start-job?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Job
ms.openlocfilehash: 69cebe735e413b226bd40539df075bf3a49bce95
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194607"
---
# <span data-ttu-id="2704c-103">Start-Job</span><span class="sxs-lookup"><span data-stu-id="2704c-103">Start-Job</span></span>

## <span data-ttu-id="2704c-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="2704c-104">SYNOPSIS</span></span>
<span data-ttu-id="2704c-105">Inicia um trabalho em segundo plano do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2704c-105">Starts a PowerShell background job.</span></span>

## <span data-ttu-id="2704c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2704c-106">SYNTAX</span></span>

### <span data-ttu-id="2704c-107">ComputerName (padrão)</span><span class="sxs-lookup"><span data-stu-id="2704c-107">ComputerName (Default)</span></span>

```
Start-Job [-Name <String>] [-ScriptBlock] <ScriptBlock> [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>] [-RunAs32]
 [-PSVersion <Version>] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="2704c-108">Definitionname</span><span class="sxs-lookup"><span data-stu-id="2704c-108">DefinitionName</span></span>

```
Start-Job [-DefinitionName] <String> [[-DefinitionPath] <String>] [[-Type] <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="2704c-109">LiteralFilePathComputerName</span><span class="sxs-lookup"><span data-stu-id="2704c-109">LiteralFilePathComputerName</span></span>

```
Start-Job [-Name <String>] [-Credential <PSCredential>] -LiteralPath <String>
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>] [-RunAs32]
 [-PSVersion <Version>] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="2704c-110">FilePathComputerName</span><span class="sxs-lookup"><span data-stu-id="2704c-110">FilePathComputerName</span></span>

```
Start-Job [-Name <String>] [-Credential <PSCredential>] [-FilePath] <String>
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>] [-RunAs32]
 [-PSVersion <Version>] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

## <span data-ttu-id="2704c-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2704c-111">DESCRIPTION</span></span>

<span data-ttu-id="2704c-112">O `Start-Job` cmdlet inicia um trabalho em segundo plano do PowerShell no computador local.</span><span class="sxs-lookup"><span data-stu-id="2704c-112">The `Start-Job` cmdlet starts a PowerShell background job on the local computer.</span></span>

<span data-ttu-id="2704c-113">Um trabalho em segundo plano do PowerShell executa um comando sem interagir com a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="2704c-113">A PowerShell background job runs a command without interacting with the current session.</span></span> <span data-ttu-id="2704c-114">Quando você inicia um trabalho em segundo plano, um objeto de trabalho retorna imediatamente, mesmo se o trabalho levar um tempo estendido para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="2704c-114">When you start a background job, a job object returns immediately, even if the job takes an extended time to finish.</span></span> <span data-ttu-id="2704c-115">É possível continuar a trabalhar na sessão sem interrupção enquanto o trabalho é executado.</span><span class="sxs-lookup"><span data-stu-id="2704c-115">You can continue to work in the session without interruption while the job runs.</span></span>

<span data-ttu-id="2704c-116">O objeto de trabalho contém informações úteis sobre o trabalho, mas não contém os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="2704c-116">The job object contains useful information about the job, but it doesn't contain the job results.</span></span>
<span data-ttu-id="2704c-117">Quando o trabalho for concluído, use o `Receive-Job` cmdlet para obter os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="2704c-117">When the job finishes, use the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="2704c-118">Para obter mais informações sobre trabalhos em segundo plano, consulte [about_Jobs](./About/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="2704c-118">For more information about background jobs, see [about_Jobs](./About/about_Jobs.md).</span></span>

<span data-ttu-id="2704c-119">Para executar um trabalho em segundo plano em um computador remoto, use o parâmetro **AsJob** que está disponível em muitos cmdlets ou use o `Invoke-Command` cmdlet para executar um `Start-Job` comando no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="2704c-119">To run a background job on a remote computer, use the **AsJob** parameter that is available on many cmdlets, or use the `Invoke-Command` cmdlet to run a `Start-Job` command on the remote computer.</span></span> <span data-ttu-id="2704c-120">Para obter mais informações, consulte [about_Remote_Jobs](./About/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="2704c-120">For more information, see [about_Remote_Jobs](./About/about_Remote_Jobs.md).</span></span>

<span data-ttu-id="2704c-121">A partir do PowerShell 3,0, `Start-Job` o pode iniciar instâncias de tipos de trabalho personalizados, como trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="2704c-121">Starting in PowerShell 3.0, `Start-Job` can start instances of custom job types, such as scheduled jobs.</span></span> <span data-ttu-id="2704c-122">Para obter informações sobre como usar `Start-Job` o para iniciar trabalhos com tipos personalizados, consulte os documentos de ajuda para o recurso tipo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2704c-122">For information about how to use `Start-Job` to start jobs with custom types, see the help documents for the job type feature.</span></span>

<span data-ttu-id="2704c-123">A partir do PowerShell 6,0, você pode iniciar trabalhos usando o operador de plano de fundo e comercial ( `&` ).</span><span class="sxs-lookup"><span data-stu-id="2704c-123">Beginning in PowerShell 6.0, you can start jobs using the ampersand (`&`) background operator.</span></span> <span data-ttu-id="2704c-124">A funcionalidade do operador de segundo plano é semelhante a `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="2704c-124">The functionality of the background operator is similar to `Start-Job`.</span></span> <span data-ttu-id="2704c-125">Os dois métodos para iniciar um trabalho criam um objeto de trabalho **PSRemotingJob** .</span><span class="sxs-lookup"><span data-stu-id="2704c-125">Both methods to start a job create a **PSRemotingJob** job object.</span></span> <span data-ttu-id="2704c-126">Para obter mais informações sobre como usar o e comercial ( `&` ), consulte [about_Operators](./about/about_operators.md#background-operator-).</span><span class="sxs-lookup"><span data-stu-id="2704c-126">For more information about using the ampersand (`&`), see [about_Operators](./about/about_operators.md#background-operator-).</span></span>

<span data-ttu-id="2704c-127">O diretório de trabalho padrão para trabalhos é codificado.</span><span class="sxs-lookup"><span data-stu-id="2704c-127">The default working directory for jobs is hardcoded.</span></span> <span data-ttu-id="2704c-128">O padrão do Windows é `$HOME\Documents` e no Linux ou MacOS o padrão é `$HOME` .</span><span class="sxs-lookup"><span data-stu-id="2704c-128">The Windows default is `$HOME\Documents` and on Linux or macOS the default is `$HOME`.</span></span> <span data-ttu-id="2704c-129">O código de script em execução no trabalho em segundo plano precisa gerenciar o diretório de trabalho conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="2704c-129">The script code running in the background job needs to manage the working directory as needed.</span></span>

> [!NOTE]
> <span data-ttu-id="2704c-130">Não há suporte para a criação de um trabalho em segundo plano fora do processo `Start-Job` no cenário em que o PowerShell está sendo hospedado em outros aplicativos, como o Azure Functions do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2704c-130">Creating an out-of-process background job with `Start-Job` is not supported in the scenario where PowerShell is being hosted in other applications, such as the PowerShell Azure Functions.</span></span>
>
> <span data-ttu-id="2704c-131">Isso ocorre por design porque `Start-Job` depende do `pwsh` executável a estar disponível em `$PSHOME` para iniciar um trabalho em segundo plano fora do processo, mas quando um aplicativo está hospedando o PowerShell, ele está diretamente usando os pacotes do SDK do NuGet do PowerShell e não será `pwsh` enviado junto.</span><span class="sxs-lookup"><span data-stu-id="2704c-131">This is by design because `Start-Job` depends on the `pwsh` executable to be available under `$PSHOME` to start an out-of-process background job, but when an application is hosting PowerShell, it's directly using the PowerShell NuGet SDK packages and won't have `pwsh` shipped along.</span></span>
>
> <span data-ttu-id="2704c-132">O substituto nesse cenário é `Start-ThreadJob` do módulo **[ThreadJob](https://www.powershellgallery.com/packages/ThreadJob)** .</span><span class="sxs-lookup"><span data-stu-id="2704c-132">The substitute in that scenario is `Start-ThreadJob` from the module **[ThreadJob](https://www.powershellgallery.com/packages/ThreadJob)** .</span></span>

## <span data-ttu-id="2704c-133">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="2704c-133">EXAMPLES</span></span>

### <span data-ttu-id="2704c-134">Exemplo 1: iniciar um trabalho em segundo plano</span><span class="sxs-lookup"><span data-stu-id="2704c-134">Example 1: Start a background job</span></span>

<span data-ttu-id="2704c-135">Este exemplo inicia um trabalho em segundo plano que é executado no computador local.</span><span class="sxs-lookup"><span data-stu-id="2704c-135">This example starts a background job that runs on the local computer.</span></span>

```powershell
Start-Job -ScriptBlock { Get-Process -Name pwsh }
```

```Output
Id  Name   PSJobTypeName   State     HasMoreData   Location    Command
--  ----   -------------   -----     -----------   --------    -------
1   Job1   BackgroundJob   Running   True          localhost   Get-Process -Name pwsh
```

<span data-ttu-id="2704c-136">`Start-Job` usa o parâmetro **scriptblock** para executar `Get-Process` como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="2704c-136">`Start-Job` uses the **ScriptBlock** parameter to run `Get-Process` as a background job.</span></span> <span data-ttu-id="2704c-137">O parâmetro **Name** especifica a localização de processos do PowerShell, `pwsh` .</span><span class="sxs-lookup"><span data-stu-id="2704c-137">The **Name** parameter specifies to find PowerShell processes, `pwsh`.</span></span> <span data-ttu-id="2704c-138">As informações do trabalho são exibidas e o PowerShell retorna a um prompt enquanto o trabalho é executado em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="2704c-138">The job information is displayed and PowerShell returns to a prompt while the job runs in the background.</span></span>

<span data-ttu-id="2704c-139">Para exibir a saída do trabalho, use o `Receive-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2704c-139">To view the job's output, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="2704c-140">Por exemplo, `Receive-Job -Id 1`.</span><span class="sxs-lookup"><span data-stu-id="2704c-140">For example, `Receive-Job -Id 1`.</span></span>

### <span data-ttu-id="2704c-141">Exemplo 2: usar o operador em segundo plano para iniciar um trabalho em segundo plano</span><span class="sxs-lookup"><span data-stu-id="2704c-141">Example 2: Use the background operator to start a background job</span></span>

<span data-ttu-id="2704c-142">Este exemplo usa o operador de segundo e comercial ( `&` ) para iniciar um trabalho em segundo plano no computador local.</span><span class="sxs-lookup"><span data-stu-id="2704c-142">This example uses the ampersand (`&`) background operator to start a background job on the local computer.</span></span> <span data-ttu-id="2704c-143">O trabalho Obtém o mesmo resultado que `Start-Job` no exemplo 1.</span><span class="sxs-lookup"><span data-stu-id="2704c-143">The job gets the same result as `Start-Job` in Example 1.</span></span>

```powershell
Get-Process -Name pwsh &
```

```Output
Id    Name   PSJobTypeName   State       HasMoreData     Location      Command
--    ----   -------------   -----       -----------     --------      -------
5     Job5   BackgroundJob   Running     True            localhost     Microsoft.PowerShell.Man...
```

<span data-ttu-id="2704c-144">`Get-Process` usa o parâmetro **Name** para especificar processos do PowerShell, `pwsh` .</span><span class="sxs-lookup"><span data-stu-id="2704c-144">`Get-Process` uses the **Name** parameter to specify PowerShell processes, `pwsh`.</span></span> <span data-ttu-id="2704c-145">O e comercial ( `&` ) executa o comando como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="2704c-145">The ampersand (`&`) runs the command as a background job.</span></span> <span data-ttu-id="2704c-146">As informações do trabalho são exibidas e o PowerShell retorna a um prompt enquanto o trabalho é executado em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="2704c-146">The job information is displayed and PowerShell returns to a prompt while the job runs in the background.</span></span>

<span data-ttu-id="2704c-147">Para exibir a saída do trabalho, use o `Receive-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2704c-147">To view the job's output, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="2704c-148">Por exemplo, `Receive-Job -Id 5`.</span><span class="sxs-lookup"><span data-stu-id="2704c-148">For example, `Receive-Job -Id 5`.</span></span>

### <span data-ttu-id="2704c-149">Exemplo 3: iniciar um trabalho usando Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="2704c-149">Example 3: Start a job using Invoke-Command</span></span>

<span data-ttu-id="2704c-150">Este exemplo executa um trabalho em vários computadores.</span><span class="sxs-lookup"><span data-stu-id="2704c-150">This example runs a job on multiple computers.</span></span> <span data-ttu-id="2704c-151">O trabalho é armazenado em uma variável e é executado usando o nome da variável na linha de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2704c-151">The job is stored in a variable and is executed by using the variable name on the PowerShell command line.</span></span>

```powershell
$jobWRM = Invoke-Command -ComputerName (Get-Content -Path C:\Servers.txt) -ScriptBlock {
   Get-Service -Name WinRM } -JobName WinRM -ThrottleLimit 16 -AsJob
```

<span data-ttu-id="2704c-152">Um trabalho que usa `Invoke-Command` é criado e armazenado na `$jobWRM` variável.</span><span class="sxs-lookup"><span data-stu-id="2704c-152">A job that uses `Invoke-Command` is created and stored in the `$jobWRM` variable.</span></span> <span data-ttu-id="2704c-153">`Invoke-Command` usa o parâmetro **ComputerName** para especificar os computadores em que o trabalho é executado.</span><span class="sxs-lookup"><span data-stu-id="2704c-153">`Invoke-Command` uses the **ComputerName** parameter to specify the computers where the job runs.</span></span> <span data-ttu-id="2704c-154">`Get-Content` Obtém os nomes de servidor do `C:\Servers.txt` arquivo.</span><span class="sxs-lookup"><span data-stu-id="2704c-154">`Get-Content` gets the server names from the `C:\Servers.txt` file.</span></span>

<span data-ttu-id="2704c-155">O parâmetro **scriptblock** especifica um comando que `Get-Service` Obtém o serviço **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="2704c-155">The **ScriptBlock** parameter specifies a command that `Get-Service` gets the **WinRM** service.</span></span> <span data-ttu-id="2704c-156">O parâmetro **JobName** especifica um nome amigável para o trabalho, **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="2704c-156">The **JobName** parameter specifies a friendly name for the job, **WinRM** .</span></span> <span data-ttu-id="2704c-157">O parâmetro **ThrottleLimit** limita o número de comandos simultâneos a 16.</span><span class="sxs-lookup"><span data-stu-id="2704c-157">The **ThrottleLimit** parameter limits the number of concurrent commands to 16.</span></span> <span data-ttu-id="2704c-158">O parâmetro **AsJob** inicia um trabalho em segundo plano que executa o comando nos servidores.</span><span class="sxs-lookup"><span data-stu-id="2704c-158">The **AsJob** parameter starts a background job that runs the command on the servers.</span></span>

### <span data-ttu-id="2704c-159">Exemplo 4: obter informações do trabalho</span><span class="sxs-lookup"><span data-stu-id="2704c-159">Example 4: Get job information</span></span>

<span data-ttu-id="2704c-160">Este exemplo obtém informações sobre um trabalho e exibe os resultados de um trabalho concluído que foi executado no computador local.</span><span class="sxs-lookup"><span data-stu-id="2704c-160">This example gets information about a job and displays the results of a completed job that was run on the local computer.</span></span>

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

<span data-ttu-id="2704c-161">`Start-Job` usa o parâmetro **scriptblock** para executar um comando que especifica `Get-WinEvent` para obter o log do **sistema** .</span><span class="sxs-lookup"><span data-stu-id="2704c-161">`Start-Job` uses the **ScriptBlock** parameter to run a command that specifies `Get-WinEvent` to get the **System** log.</span></span> <span data-ttu-id="2704c-162">O parâmetro **Credential** especifica uma conta de usuário de domínio com permissão para executar o trabalho no computador.</span><span class="sxs-lookup"><span data-stu-id="2704c-162">The **Credential** parameter specifies a domain user account with permission to run the job on the computer.</span></span> <span data-ttu-id="2704c-163">O objeto de trabalho é armazenado na `$j` variável.</span><span class="sxs-lookup"><span data-stu-id="2704c-163">The job object is stored in the `$j` variable.</span></span>

<span data-ttu-id="2704c-164">O objeto na `$j` variável é enviado ao pipeline para `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="2704c-164">The object in the `$j` variable is sent down the pipeline to `Select-Object`.</span></span> <span data-ttu-id="2704c-165">O parâmetro **Property** especifica um asterisco ( `*` ) para exibir todas as propriedades do objeto de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2704c-165">The **Property** parameter specifies an asterisk (`*`) to display all the job object's properties.</span></span>

### <span data-ttu-id="2704c-166">Exemplo 5: executar um script como um trabalho em segundo plano</span><span class="sxs-lookup"><span data-stu-id="2704c-166">Example 5: Run a script as a background job</span></span>

<span data-ttu-id="2704c-167">Neste exemplo, um script no computador local é executado como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="2704c-167">In this example, a script on the local computer is run as a background job.</span></span>

```powershell
Start-Job -FilePath C:\Scripts\Sample.ps1
```

<span data-ttu-id="2704c-168">`Start-Job` usa o parâmetro **FilePath** para especificar um arquivo de script armazenado no computador local.</span><span class="sxs-lookup"><span data-stu-id="2704c-168">`Start-Job` uses the **FilePath** parameter to specify a script file that's stored on the local computer.</span></span>

### <span data-ttu-id="2704c-169">Exemplo 6: obter um processo usando um trabalho em segundo plano</span><span class="sxs-lookup"><span data-stu-id="2704c-169">Example 6: Get a process using a background job</span></span>

<span data-ttu-id="2704c-170">Este exemplo usa um trabalho em segundo plano para obter um processo especificado por nome.</span><span class="sxs-lookup"><span data-stu-id="2704c-170">This example uses a background job to get a specified process by name.</span></span>

```powershell
Start-Job -Name PShellJob -ScriptBlock { Get-Process -Name PowerShell }
```

<span data-ttu-id="2704c-171">`Start-Job` usa o parâmetro **Name** para especificar um nome de trabalho amigável, **PShellJob** .</span><span class="sxs-lookup"><span data-stu-id="2704c-171">`Start-Job` uses the **Name** parameter to specify a friendly job name, **PShellJob** .</span></span> <span data-ttu-id="2704c-172">O parâmetro **scriptblock** especifica `Get-Process` para obter processos com o nome **PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="2704c-172">The **ScriptBlock** parameter specifies `Get-Process` to get processes with the name **PowerShell** .</span></span>

### <span data-ttu-id="2704c-173">Exemplo 7: coletar e salvar dados usando um trabalho em segundo plano</span><span class="sxs-lookup"><span data-stu-id="2704c-173">Example 7: Collect and save data by using a background job</span></span>

<span data-ttu-id="2704c-174">Este exemplo inicia um trabalho que coleta uma grande quantidade de dados de mapa e, em seguida, salva-o em um `.tif` arquivo.</span><span class="sxs-lookup"><span data-stu-id="2704c-174">This example starts a job that collects a large amount of map data and then saves it in a `.tif` file.</span></span>

```powershell
Start-Job -Name GetMappingFiles -InitializationScript {Import-Module MapFunctions} -ScriptBlock {
   Get-Map -Name * | Set-Content -Path D:\Maps.tif } -RunAs32
```

<span data-ttu-id="2704c-175">`Start-Job` usa o parâmetro **Name** para especificar um nome de trabalho amigável, **GetMappingFiles** .</span><span class="sxs-lookup"><span data-stu-id="2704c-175">`Start-Job` uses the **Name** parameter to specify a friendly job name, **GetMappingFiles** .</span></span> <span data-ttu-id="2704c-176">O parâmetro **initializationScript** executa um bloco de script que importa o módulo **MapFunctions** .</span><span class="sxs-lookup"><span data-stu-id="2704c-176">The **InitializationScript** parameter runs a script block that imports the **MapFunctions** module.</span></span> <span data-ttu-id="2704c-177">O parâmetro **scriptblock** executa `Get-Map` e `Set-Content` salva os dados no local especificado pelo parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="2704c-177">The **ScriptBlock** parameter runs `Get-Map` and `Set-Content` saves the data in the location specified by the **Path** parameter.</span></span> <span data-ttu-id="2704c-178">O parâmetro **RunAs32** executa o processo como 32 bits, mesmo em um sistema operacional de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="2704c-178">The **RunAs32** parameter runs the process as 32-bit, even on a 64-bit operating system.</span></span>

### <span data-ttu-id="2704c-179">Exemplo 8: passar entrada para um trabalho em segundo plano</span><span class="sxs-lookup"><span data-stu-id="2704c-179">Example 8: Pass input to a background job</span></span>

<span data-ttu-id="2704c-180">Este exemplo usa a `$input` variável automática para processar um objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="2704c-180">This example uses the `$input` automatic variable to process an input object.</span></span> <span data-ttu-id="2704c-181">Use `Receive-Job` para exibir a saída do trabalho.</span><span class="sxs-lookup"><span data-stu-id="2704c-181">Use `Receive-Job` to view the job's output.</span></span>

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

<span data-ttu-id="2704c-182">`Start-Job` usa o parâmetro **scriptblock** para executar `Get-Content` com a `$input` variável automática.</span><span class="sxs-lookup"><span data-stu-id="2704c-182">`Start-Job` uses the **ScriptBlock** parameter to run `Get-Content` with the `$input` automatic variable.</span></span> <span data-ttu-id="2704c-183">A `$input` variável obtém objetos do parâmetro **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="2704c-183">The `$input` variable gets objects from the **InputObject** parameter.</span></span> <span data-ttu-id="2704c-184">`Receive-Job` usa o parâmetro **Name** para especificar o trabalho e gera os resultados.</span><span class="sxs-lookup"><span data-stu-id="2704c-184">`Receive-Job` uses the **Name** parameter to specify the job and outputs the results.</span></span> <span data-ttu-id="2704c-185">O parâmetro **Keep** salva a saída do trabalho para que possa ser exibido novamente durante a sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2704c-185">The **Keep** parameter saves the job output so it can be viewed again during the PowerShell session.</span></span>

### <span data-ttu-id="2704c-186">Exemplo 9: usar o parâmetro ArgumentList para especificar uma matriz</span><span class="sxs-lookup"><span data-stu-id="2704c-186">Example 9: Use the ArgumentList parameter to specify an array</span></span>

<span data-ttu-id="2704c-187">Este exemplo usa o parâmetro **ArgumentList** para especificar uma matriz de argumentos.</span><span class="sxs-lookup"><span data-stu-id="2704c-187">This example uses the **ArgumentList** parameter to specify an array of arguments.</span></span> <span data-ttu-id="2704c-188">A matriz é uma lista separada por vírgulas de nomes de processo.</span><span class="sxs-lookup"><span data-stu-id="2704c-188">The array is a comma-separated list of process names.</span></span>

```powershell
Start-Job -ScriptBlock { Get-Process -Name $args } -ArgumentList powershell, pwsh, notepad
```

```Output
Id     Name      PSJobTypeName   State       HasMoreData     Location     Command
--     ----      -------------   -----       -----------     --------     -------
1      Job1      BackgroundJob   Running     True            localhost    Get-Process -Name $args
```

<span data-ttu-id="2704c-189">O `Start-Job` cmdlet usa o parâmetro **scriptblock** para executar um comando.</span><span class="sxs-lookup"><span data-stu-id="2704c-189">The `Start-Job` cmdlet uses the **ScriptBlock** parameter to run a command.</span></span> <span data-ttu-id="2704c-190">`Get-Process` usa o parâmetro **Name** para especificar a variável automática `$args` .</span><span class="sxs-lookup"><span data-stu-id="2704c-190">`Get-Process` uses the **Name** parameter to specify the automatic variable `$args`.</span></span> <span data-ttu-id="2704c-191">O parâmetro **ArgumentList** passa a matriz de nomes de processo para `$args` .</span><span class="sxs-lookup"><span data-stu-id="2704c-191">The **ArgumentList** parameter passes the array of process names to `$args`.</span></span> <span data-ttu-id="2704c-192">Os nomes de processo PowerShell, pwsh e Notepad são processos em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="2704c-192">The process names powershell, pwsh, and notepad are processes running on the local computer.</span></span>

<span data-ttu-id="2704c-193">Para exibir a saída do trabalho, use o `Receive-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2704c-193">To view the job's output, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="2704c-194">Por exemplo, `Receive-Job -Id 1`.</span><span class="sxs-lookup"><span data-stu-id="2704c-194">For example, `Receive-Job -Id 1`.</span></span>

## <span data-ttu-id="2704c-195">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2704c-195">PARAMETERS</span></span>

### <span data-ttu-id="2704c-196">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="2704c-196">-ArgumentList</span></span>

<span data-ttu-id="2704c-197">Especifica uma matriz de argumentos, ou valores de parâmetro, para o script que é especificado pelo parâmetro **FilePath** ou um comando especificado com o parâmetro **scriptblock** .</span><span class="sxs-lookup"><span data-stu-id="2704c-197">Specifies an array of arguments, or parameter values, for the script that is specified by the **FilePath** parameter or a command specified with the **ScriptBlock** parameter.</span></span>

<span data-ttu-id="2704c-198">Os argumentos devem ser passados para **ArgumentList** como argumento de matriz de dimensão única.</span><span class="sxs-lookup"><span data-stu-id="2704c-198">Arguments must be passed to **ArgumentList** as single-dimension array argument.</span></span> <span data-ttu-id="2704c-199">Por exemplo, uma lista separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="2704c-199">For example, a comma-separated list.</span></span> <span data-ttu-id="2704c-200">Para obter mais informações sobre o comportamento de **ArgumentList** , consulte [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="2704c-200">For more information about the behavior of **ArgumentList** , see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

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

### <span data-ttu-id="2704c-201">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="2704c-201">-Authentication</span></span>

<span data-ttu-id="2704c-202">Especifica o mecanismo usado para autenticar as credenciais do usuário.</span><span class="sxs-lookup"><span data-stu-id="2704c-202">Specifies the mechanism that is used to authenticate user credentials.</span></span>

<span data-ttu-id="2704c-203">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="2704c-203">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="2704c-204">Padrão</span><span class="sxs-lookup"><span data-stu-id="2704c-204">Default</span></span>
- <span data-ttu-id="2704c-205">Básico</span><span class="sxs-lookup"><span data-stu-id="2704c-205">Basic</span></span>
- <span data-ttu-id="2704c-206">CredSSP</span><span class="sxs-lookup"><span data-stu-id="2704c-206">Credssp</span></span>
- <span data-ttu-id="2704c-207">Digest</span><span class="sxs-lookup"><span data-stu-id="2704c-207">Digest</span></span>
- <span data-ttu-id="2704c-208">Kerberos</span><span class="sxs-lookup"><span data-stu-id="2704c-208">Kerberos</span></span>
- <span data-ttu-id="2704c-209">Negotiate</span><span class="sxs-lookup"><span data-stu-id="2704c-209">Negotiate</span></span>
- <span data-ttu-id="2704c-210">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="2704c-210">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="2704c-211">O valor padrão é Default.</span><span class="sxs-lookup"><span data-stu-id="2704c-211">The default value is Default.</span></span>

<span data-ttu-id="2704c-212">A autenticação CredSSP está disponível somente no Windows Vista, no Windows Server 2008 e em versões posteriores do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="2704c-212">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="2704c-213">Para obter mais informações sobre os valores desse parâmetro, consulte [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="2704c-213">For more information about the values of this parameter, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="2704c-214">A autenticação CredSSP (Credencial Security Support Provider), na qual as credenciais do usuário são passadas a um computador remoto para autenticação, foi projetada para comandos que exijam autenticação em mais de um recurso, como acessar um compartilhamento de rede remota.</span><span class="sxs-lookup"><span data-stu-id="2704c-214">Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="2704c-215">Esse mecanismo aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="2704c-215">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="2704c-216">Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="2704c-216">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

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

### <span data-ttu-id="2704c-217">-Credential</span><span class="sxs-lookup"><span data-stu-id="2704c-217">-Credential</span></span>

<span data-ttu-id="2704c-218">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="2704c-218">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="2704c-219">Se o parâmetro **Credential** não for especificado, o comando usará as credenciais do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="2704c-219">If the **Credential** parameter isn't specified, the command uses the current user's credentials.</span></span>

<span data-ttu-id="2704c-220">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2704c-220">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="2704c-221">Se você digitar um nome de usuário, você será solicitado a inserir a senha.</span><span class="sxs-lookup"><span data-stu-id="2704c-221">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="2704c-222">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="2704c-222">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="2704c-223">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="2704c-223">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="2704c-224">-Definitionname</span><span class="sxs-lookup"><span data-stu-id="2704c-224">-DefinitionName</span></span>

<span data-ttu-id="2704c-225">Especifica o nome da definição do trabalho que este cmdlet inicia.</span><span class="sxs-lookup"><span data-stu-id="2704c-225">Specifies the definition name of the job that this cmdlet starts.</span></span> <span data-ttu-id="2704c-226">Use este parâmetro para iniciar tipos de trabalho personalizados que têm um nome de definição, como trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="2704c-226">Use this parameter to start custom job types that have a definition name, such as scheduled jobs.</span></span>

<span data-ttu-id="2704c-227">Quando você usa `Start-Job` o para iniciar uma instância de um trabalho agendado, o trabalho é iniciado imediatamente, independentemente dos gatilhos de trabalho ou das opções de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2704c-227">When you use `Start-Job` to start an instance of a scheduled job, the job starts immediately, regardless of job triggers or job options.</span></span> <span data-ttu-id="2704c-228">A instância de trabalho resultante é um trabalho agendado, mas não é salva em disco, como trabalhos agendados disparados.</span><span class="sxs-lookup"><span data-stu-id="2704c-228">The resulting job instance is a scheduled job, but it isn't saved to disk like triggered scheduled jobs.</span></span> <span data-ttu-id="2704c-229">Você não pode usar o parâmetro **ArgumentList** de `Start-Job` para fornecer valores para parâmetros de scripts que são executados em um trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="2704c-229">You can't use the **ArgumentList** parameter of `Start-Job` to provide values for parameters of scripts that run in a scheduled job.</span></span>

<span data-ttu-id="2704c-230">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="2704c-230">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="2704c-231">-DefinitionPath</span><span class="sxs-lookup"><span data-stu-id="2704c-231">-DefinitionPath</span></span>

<span data-ttu-id="2704c-232">Especifica o caminho da definição para o trabalho que este cmdlet inicia.</span><span class="sxs-lookup"><span data-stu-id="2704c-232">Specifies path of the definition for the job that this cmdlet starts.</span></span> <span data-ttu-id="2704c-233">Insira o caminho de definição.</span><span class="sxs-lookup"><span data-stu-id="2704c-233">Enter the definition path.</span></span> <span data-ttu-id="2704c-234">A concatenação dos valores dos parâmetros **DefinitionPath** e **definitionname** é o caminho totalmente qualificado da definição de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2704c-234">The concatenation of the values of the **DefinitionPath** and **DefinitionName** parameters is the fully qualified path of the job definition.</span></span> <span data-ttu-id="2704c-235">Use este parâmetro para iniciar tipos de trabalho personalizados que têm um caminho de definição, como trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="2704c-235">Use this parameter to start custom job types that have a definition path, such as scheduled jobs.</span></span>

<span data-ttu-id="2704c-236">Para trabalhos agendados, o valor do parâmetro **DefinitionPath** é `$home\AppData\Local\Windows\PowerShell\ScheduledJob` .</span><span class="sxs-lookup"><span data-stu-id="2704c-236">For scheduled jobs, the value of the **DefinitionPath** parameter is `$home\AppData\Local\Windows\PowerShell\ScheduledJob`.</span></span>

<span data-ttu-id="2704c-237">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="2704c-237">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="2704c-238">-FilePath</span><span class="sxs-lookup"><span data-stu-id="2704c-238">-FilePath</span></span>

<span data-ttu-id="2704c-239">Especifica um script local que `Start-Job` é executado como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="2704c-239">Specifies a local script that `Start-Job` runs as a background job.</span></span> <span data-ttu-id="2704c-240">Insira o caminho e o nome de arquivo do script ou use o pipeline para o qual enviar um caminho de script `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="2704c-240">Enter the path and file name of the script or use the pipeline to send a script path to `Start-Job`.</span></span> <span data-ttu-id="2704c-241">O script deve estar no computador local ou em uma pasta que o computador local possa acessar.</span><span class="sxs-lookup"><span data-stu-id="2704c-241">The script must be on the local computer or in a folder that the local computer can access.</span></span>

<span data-ttu-id="2704c-242">Quando você usa esse parâmetro, o PowerShell converte o conteúdo do arquivo de script especificado em um bloco de script e executa o bloco de script como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="2704c-242">When you use this parameter, PowerShell converts the contents of the specified script file to a script block and runs the script block as a background job.</span></span>

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

### <span data-ttu-id="2704c-243">-InitializationScript</span><span class="sxs-lookup"><span data-stu-id="2704c-243">-InitializationScript</span></span>

<span data-ttu-id="2704c-244">Especifica os comandos que são executados antes do trabalho ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="2704c-244">Specifies commands that run before the job starts.</span></span> <span data-ttu-id="2704c-245">Para criar um bloco de script, coloque os comandos entre chaves ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="2704c-245">To create a script block, enclose the commands in curly braces (`{}`).</span></span>

<span data-ttu-id="2704c-246">Use esse parâmetro para preparar a sessão na qual o trabalho é executado.</span><span class="sxs-lookup"><span data-stu-id="2704c-246">Use this parameter to prepare the session in which the job runs.</span></span> <span data-ttu-id="2704c-247">Por exemplo, você pode usá-lo para adicionar funções, snap-ins e módulos à sessão.</span><span class="sxs-lookup"><span data-stu-id="2704c-247">For example, you can use it to add functions, snap-ins, and modules to the session.</span></span>

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

### <span data-ttu-id="2704c-248">-InputObject</span><span class="sxs-lookup"><span data-stu-id="2704c-248">-InputObject</span></span>

<span data-ttu-id="2704c-249">Especifica a entrada para o comando.</span><span class="sxs-lookup"><span data-stu-id="2704c-249">Specifies input to the command.</span></span> <span data-ttu-id="2704c-250">Insira uma variável que contenha os objetos ou digite um comando ou uma expressão que gere os objetos.</span><span class="sxs-lookup"><span data-stu-id="2704c-250">Enter a variable that contains the objects, or type a command or expression that generates the objects.</span></span>

<span data-ttu-id="2704c-251">No valor do parâmetro **scriptblock** , use a `$input` variável automática para representar os objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="2704c-251">In the value of the **ScriptBlock** parameter, use the `$input` automatic variable to represent the input objects.</span></span>

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

### <span data-ttu-id="2704c-252">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="2704c-252">-LiteralPath</span></span>

<span data-ttu-id="2704c-253">Especifica um script local que este cmdlet executa como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="2704c-253">Specifies a local script that this cmdlet runs as a background job.</span></span> <span data-ttu-id="2704c-254">Insira o caminho de um script no computador local.</span><span class="sxs-lookup"><span data-stu-id="2704c-254">Enter the path of a script on the local computer.</span></span>

<span data-ttu-id="2704c-255">`Start-Job` usa o valor do parâmetro **LiteralPath** exatamente como ele é digitado.</span><span class="sxs-lookup"><span data-stu-id="2704c-255">`Start-Job` uses the value of the **LiteralPath** parameter exactly as it's typed.</span></span> <span data-ttu-id="2704c-256">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="2704c-256">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="2704c-257">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="2704c-257">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="2704c-258">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="2704c-258">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="2704c-259">-Name</span><span class="sxs-lookup"><span data-stu-id="2704c-259">-Name</span></span>

<span data-ttu-id="2704c-260">Especifica um nome amigável para o novo trabalho.</span><span class="sxs-lookup"><span data-stu-id="2704c-260">Specifies a friendly name for the new job.</span></span> <span data-ttu-id="2704c-261">Você pode usar o nome para identificar o trabalho para outros cmdlets de trabalho, como o `Stop-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2704c-261">You can use the name to identify the job to other job cmdlets, such as the `Stop-Job` cmdlet.</span></span>

<span data-ttu-id="2704c-262">O nome amigável padrão é `Job#` , em que `#` é um número ordinal que é incrementado para cada trabalho.</span><span class="sxs-lookup"><span data-stu-id="2704c-262">The default friendly name is `Job#`, where `#` is an ordinal number that is incremented for each job.</span></span>

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

### <span data-ttu-id="2704c-263">-PSVersion</span><span class="sxs-lookup"><span data-stu-id="2704c-263">-PSVersion</span></span>

<span data-ttu-id="2704c-264">Especifica uma versão.</span><span class="sxs-lookup"><span data-stu-id="2704c-264">Specifies a version.</span></span> <span data-ttu-id="2704c-265">`Start-Job` executa o trabalho com a versão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2704c-265">`Start-Job` runs the job with the version of PowerShell.</span></span> <span data-ttu-id="2704c-266">Os valores aceitáveis para esse parâmetro são: `2.0` e `3.0` .</span><span class="sxs-lookup"><span data-stu-id="2704c-266">The acceptable values for this parameter are: `2.0` and `3.0`.</span></span>

<span data-ttu-id="2704c-267">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="2704c-267">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="2704c-268">-RunAs32</span><span class="sxs-lookup"><span data-stu-id="2704c-268">-RunAs32</span></span>

<span data-ttu-id="2704c-269">Indica que `Start-Job` o executa o trabalho em um processo de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="2704c-269">Indicates that `Start-Job` runs the job in a 32-bit process.</span></span> <span data-ttu-id="2704c-270">**RunAs32** força o trabalho a ser executado em um processo de 32 bits, mesmo em um sistema operacional de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="2704c-270">**RunAs32** forces the job to run in a 32-bit process, even on a 64-bit operating system.</span></span>

<span data-ttu-id="2704c-271">Nas versões de 64 bits do Windows 7 e do Windows Server 2008 R2, quando o `Start-Job` comando inclui o parâmetro **RunAs32** , você não pode usar o parâmetro **Credential** para especificar as credenciais de outro usuário.</span><span class="sxs-lookup"><span data-stu-id="2704c-271">On 64-bit versions of Windows 7 and Windows Server 2008 R2, when the `Start-Job` command includes the **RunAs32** parameter, you can't use the **Credential** parameter to specify the credentials of another user.</span></span>

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

### <span data-ttu-id="2704c-272">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="2704c-272">-ScriptBlock</span></span>

<span data-ttu-id="2704c-273">Especifica os comandos a executar no trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="2704c-273">Specifies the commands to run in the background job.</span></span> <span data-ttu-id="2704c-274">Para criar um bloco de script, coloque os comandos entre chaves ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="2704c-274">To create a script block, enclose the commands in curly braces (`{}`).</span></span> <span data-ttu-id="2704c-275">Use a `$input` variável automática para acessar o valor do parâmetro **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="2704c-275">Use the `$input` automatic variable to access the value of the **InputObject** parameter.</span></span> <span data-ttu-id="2704c-276">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="2704c-276">This parameter is required.</span></span>

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

### <span data-ttu-id="2704c-277">-Type</span><span class="sxs-lookup"><span data-stu-id="2704c-277">-Type</span></span>

<span data-ttu-id="2704c-278">Especifica o tipo personalizado para trabalhos iniciados por `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="2704c-278">Specifies the custom type for jobs started by `Start-Job`.</span></span> <span data-ttu-id="2704c-279">Insira um nome de tipo de trabalho personalizado como PSScheduledJob para trabalhos agendados, ou PSWorkflowJob para tarefas de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2704c-279">Enter a custom job type name, such as PSScheduledJob for scheduled jobs or PSWorkflowJob for workflows jobs.</span></span> <span data-ttu-id="2704c-280">Esse parâmetro não é válido para trabalhos em segundo plano padrão.</span><span class="sxs-lookup"><span data-stu-id="2704c-280">This parameter isn't valid for standard background jobs.</span></span>

<span data-ttu-id="2704c-281">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="2704c-281">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="2704c-282">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2704c-282">CommonParameters</span></span>

<span data-ttu-id="2704c-283">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2704c-283">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2704c-284">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2704c-284">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2704c-285">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="2704c-285">INPUTS</span></span>

### <span data-ttu-id="2704c-286">System.String</span><span class="sxs-lookup"><span data-stu-id="2704c-286">System.String</span></span>

<span data-ttu-id="2704c-287">Você pode usar o pipeline para enviar um objeto com a propriedade **Name** para o parâmetro **Name** .</span><span class="sxs-lookup"><span data-stu-id="2704c-287">You can use the pipeline to send an object with the **Name** property to the **Name** parameter.</span></span> <span data-ttu-id="2704c-288">Por exemplo, você pode canalizar um objeto **FileInfo** de `Get-ChildItem` para `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="2704c-288">For example, you can pipeline a **FileInfo** object from `Get-ChildItem` to `Start-Job`.</span></span>

## <span data-ttu-id="2704c-289">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="2704c-289">OUTPUTS</span></span>

### <span data-ttu-id="2704c-290">System. Management. Automation. PSRemotingJob</span><span class="sxs-lookup"><span data-stu-id="2704c-290">System.Management.Automation.PSRemotingJob</span></span>

<span data-ttu-id="2704c-291">`Start-Job` Retorna um objeto **PSRemotingJob** que representa o trabalho que ele iniciou.</span><span class="sxs-lookup"><span data-stu-id="2704c-291">`Start-Job` returns a **PSRemotingJob** object that represents the job that it started.</span></span>

## <span data-ttu-id="2704c-292">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="2704c-292">NOTES</span></span>

<span data-ttu-id="2704c-293">Para ser executado em segundo plano, `Start-Job` o é executado em sua própria sessão na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="2704c-293">To run in the background, `Start-Job` runs in its own session in the current session.</span></span> <span data-ttu-id="2704c-294">Quando você usa o `Invoke-Command` cmdlet para executar um `Start-Job` comando em uma sessão em um computador remoto, `Start-Job` o é executado em uma sessão na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="2704c-294">When you use the `Invoke-Command` cmdlet to run a `Start-Job` command in a session on a remote computer, `Start-Job` runs in a session in the remote session.</span></span>

## <span data-ttu-id="2704c-295">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="2704c-295">RELATED LINKS</span></span>

[<span data-ttu-id="2704c-296">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="2704c-296">about_Arrays</span></span>](./about/about_arrays.md)

[<span data-ttu-id="2704c-297">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="2704c-297">about_Automatic_Variables</span></span>](./about/about_automatic_variables.md)

[<span data-ttu-id="2704c-298">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="2704c-298">about_Jobs</span></span>](./About/about_Jobs.md)

[<span data-ttu-id="2704c-299">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="2704c-299">about_Job_Details</span></span>](./About/about_Job_Details.md)

[<span data-ttu-id="2704c-300">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="2704c-300">about_Remote_Jobs</span></span>](./About/about_Remote_Jobs.md)

[<span data-ttu-id="2704c-301">Get-Job</span><span class="sxs-lookup"><span data-stu-id="2704c-301">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="2704c-302">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="2704c-302">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="2704c-303">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="2704c-303">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="2704c-304">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="2704c-304">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="2704c-305">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="2704c-305">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="2704c-306">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="2704c-306">Wait-Job</span></span>](Wait-Job.md)
