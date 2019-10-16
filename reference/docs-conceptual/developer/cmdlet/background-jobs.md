---
title: Trabalhos em segundo plano | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0ef5ac9-8254-4832-ace8-84b356c10f08
caps.latest.revision: 13
ms.openlocfilehash: ff4fe159eedc47fc69f4d783cd90d2b0e888c0d5
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363555"
---
# <a name="background-jobs"></a><span data-ttu-id="ee674-102">Trabalhos em segundo plano</span><span class="sxs-lookup"><span data-stu-id="ee674-102">Background Jobs</span></span>

<span data-ttu-id="ee674-103">Os cmdlets podem executar suas ações internamente ou como um*trabalho em segundo plano*do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee674-103">Cmdlets can perform their action internally or as a Windows PowerShell*background job*.</span></span> <span data-ttu-id="ee674-104">Quando um cmdlet é executado como um trabalho em segundo plano, o trabalho é feito de forma assíncrona em seu próprio thread separado do thread de pipeline que o cmdlet está usando.</span><span class="sxs-lookup"><span data-stu-id="ee674-104">When a cmdlet runs as a background job, the work is done asynchronously in its own thread separate from the pipeline thread that the cmdlet is using.</span></span> <span data-ttu-id="ee674-105">Da perspectiva do usuário, quando um cmdlet é executado como um trabalho em segundo plano, o prompt de comando retorna imediatamente, mesmo se o trabalho demorar um longo período de tempo para ser concluído, e o usuário poderá continuar sem interrupções enquanto o trabalho for executado.</span><span class="sxs-lookup"><span data-stu-id="ee674-105">From the user perspective, when a cmdlet runs as a background job, the command prompt returns immediately even if the job takes an extended amount of time to complete, and the user can continue without interruption while the job runs.</span></span>

## <a name="background-jobs-child-jobs-and-the-job-repository"></a><span data-ttu-id="ee674-106">Trabalhos em segundo plano, trabalhos filho e o repositório de trabalhos</span><span class="sxs-lookup"><span data-stu-id="ee674-106">Background Jobs, Child Jobs, and the Job Repository</span></span>

<span data-ttu-id="ee674-107">O objeto de trabalho que é retornado pelos cmdlets que oferecem suporte a trabalhos em segundo plano define o trabalho.</span><span class="sxs-lookup"><span data-stu-id="ee674-107">The job object that is returned by the cmdlets that support background jobs defines the job.</span></span> <span data-ttu-id="ee674-108">(O cmdlet [Start-Job](/powershell/module/Microsoft.PowerShell.Core/Start-Job) também retorna um objeto de trabalho.) O nome do trabalho, um identificador que é usado para especificar o trabalho, as informações de estado e os trabalhos filho são incluídos nessa definição.</span><span class="sxs-lookup"><span data-stu-id="ee674-108">(The [Start-Job](/powershell/module/Microsoft.PowerShell.Core/Start-Job) cmdlet also returns a job object.) The name of the job, an identifier that is used to specify the job, the state information, and the child jobs are included in this definition.</span></span> <span data-ttu-id="ee674-109">O trabalho não executa nenhum trabalho.</span><span class="sxs-lookup"><span data-stu-id="ee674-109">The job does not perform any of the work.</span></span> <span data-ttu-id="ee674-110">Cada trabalho em segundo plano tem pelo menos um trabalho filho porque o trabalho filho executa o trabalho real.</span><span class="sxs-lookup"><span data-stu-id="ee674-110">Each background job has at least one child job because the child job performs the actual work.</span></span> <span data-ttu-id="ee674-111">Quando você executa um cmdlet para que o trabalho seja executado como um trabalho em segundo plano, o cmdlet deve adicionar o trabalho e os trabalhos filho a um repositório comum, chamado de *repositório de trabalhos*.</span><span class="sxs-lookup"><span data-stu-id="ee674-111">When you run a cmdlet so that the work is performed as a background job, the cmdlet must add the job and the child jobs to a common repository, referred to as the *job repository*.</span></span>

<span data-ttu-id="ee674-112">Para obter mais informações sobre como os trabalhos em segundo plano são tratados na linha de comando, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ee674-112">For more information about how background jobs are handled at the command line, see the following:</span></span>

- [<span data-ttu-id="ee674-113">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="ee674-113">about_Jobs</span></span>](/powershell/module/microsoft.powershell.core/about/about_jobs)

- [<span data-ttu-id="ee674-114">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="ee674-114">about_Job_Details</span></span>](/powershell/module/microsoft.powershell.core/about/about_job_details)

- [<span data-ttu-id="ee674-115">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="ee674-115">about_Remote_Jobs</span></span>](/powershell/module/microsoft.powershell.core/about/about_remote_jobs)

## <a name="writing-a-cmdlet-that-runs-as-a-background-job"></a><span data-ttu-id="ee674-116">Escrevendo um cmdlet que é executado como um trabalho em segundo plano</span><span class="sxs-lookup"><span data-stu-id="ee674-116">Writing a Cmdlet That Runs as a Background Job</span></span>

<span data-ttu-id="ee674-117">Para gravar um cmdlet que pode ser executado como um trabalho em segundo plano, você deve concluir as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="ee674-117">To write a cmdlet that can be run as a background job, you must complete the following tasks:</span></span>

- <span data-ttu-id="ee674-118">Defina um parâmetro de opção `asJob` para que o usuário possa decidir se deseja executar o cmdlet como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="ee674-118">Define an `asJob` switch parameter so that the user can decide whether to run the cmdlet as a background job.</span></span>

- <span data-ttu-id="ee674-119">Crie um objeto derivado da classe [System. Management. Automation. Job](/dotnet/api/System.Management.Automation.Job) .</span><span class="sxs-lookup"><span data-stu-id="ee674-119">Create an object that derives from the [System.Management.Automation.Job](/dotnet/api/System.Management.Automation.Job) class.</span></span> <span data-ttu-id="ee674-120">Esse objeto pode ser um objeto de trabalho personalizado ou um objeto de trabalho fornecido pelo Windows PowerShell, como um objeto [System. Management. Automation. PSEventJob](/dotnet/api/System.Management.Automation.PSEventJob) .</span><span class="sxs-lookup"><span data-stu-id="ee674-120">This object can be a custom job object or a job object provided by Windows PowerShell, such as a [System.Management.Automation.Pseventjob](/dotnet/api/System.Management.Automation.PSEventJob) object.</span></span>

- <span data-ttu-id="ee674-121">Em um método de processamento de registros, adicione uma instrução `if` que detecta se o cmdlet deve ser executado como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="ee674-121">In a record processing method, add an `if` statement that detects whether the cmdlet should run as a background job.</span></span>

- <span data-ttu-id="ee674-122">Para objetos de trabalho personalizados, implemente a classe Job.</span><span class="sxs-lookup"><span data-stu-id="ee674-122">For custom job objects, implement the job class.</span></span>

- <span data-ttu-id="ee674-123">Retorne os objetos apropriados, dependendo se o cmdlet é executado como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="ee674-123">Return the appropriate objects, depending on whether the cmdlet is run as a background job.</span></span>

<span data-ttu-id="ee674-124">Para obter um exemplo de código, consulte [como dar suporte a trabalhos](./how-to-support-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="ee674-124">For a code example, see [How to Support Jobs](./how-to-support-jobs.md).</span></span>

## <a name="background-job-related-apis"></a><span data-ttu-id="ee674-125">APIs relacionadas a trabalho em segundo plano</span><span class="sxs-lookup"><span data-stu-id="ee674-125">Background Job-Related APIs</span></span>

<span data-ttu-id="ee674-126">As APIs a seguir são fornecidas pelo Windows PowerShell para gerenciar trabalhos em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="ee674-126">The following APIs are provided by Windows PowerShell to manage background jobs.</span></span>

<span data-ttu-id="ee674-127">[System. Management. Automation. Job](/dotnet/api/System.Management.Automation.Job) deriva objetos de trabalho personalizados.</span><span class="sxs-lookup"><span data-stu-id="ee674-127">[System.Management.Automation.Job](/dotnet/api/System.Management.Automation.Job) Derives custom job objects.</span></span> <span data-ttu-id="ee674-128">Essa é uma classe abstrata.</span><span class="sxs-lookup"><span data-stu-id="ee674-128">This is an abstract class.</span></span>

<span data-ttu-id="ee674-129">[System. Management. Automation. Jobrepository](/dotnet/api/System.Management.Automation.JobRepository) gerencia e fornece informações sobre os trabalhos em segundo plano ativos atuais.</span><span class="sxs-lookup"><span data-stu-id="ee674-129">[System.Management.Automation.Jobrepository](/dotnet/api/System.Management.Automation.JobRepository) Manages and provides information about the current active background jobs.</span></span>

<span data-ttu-id="ee674-130">[System. Management. Automation. JobState](/dotnet/api/System.Management.Automation.JobState) define o estado do trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="ee674-130">[System.Management.Automation.Jobstate](/dotnet/api/System.Management.Automation.JobState) Defines the state of the background job.</span></span> <span data-ttu-id="ee674-131">Os Estados incluem iniciado, em execução e parados.</span><span class="sxs-lookup"><span data-stu-id="ee674-131">States include Started, Running, and Stopped.</span></span>

<span data-ttu-id="ee674-132">[System. Management. Automation. JobStateInfo](/dotnet/api/System.Management.Automation.JobStateInfo) fornece informações sobre o estado de um trabalho em segundo plano e, se a última alteração de estado foi causada por um erro, o motivo pelo qual o trabalho entrou em seu estado atual.</span><span class="sxs-lookup"><span data-stu-id="ee674-132">[System.Management.Automation.Jobstateinfo](/dotnet/api/System.Management.Automation.JobStateInfo) Provides information about the state of a background job and, if the last state change was caused by an error, the reason the job entered its current state.</span></span>

<span data-ttu-id="ee674-133">[System. Management. Automation. Jobstateeventargs](/dotnet/api/System.Management.Automation.JobStateEventArgs) fornece os argumentos para um evento que é gerado quando um trabalho em segundo plano muda de estado.</span><span class="sxs-lookup"><span data-stu-id="ee674-133">[System.Management.Automation.Jobstateeventargs](/dotnet/api/System.Management.Automation.JobStateEventArgs) Provides the arguments for an event that is raised when a background job changes state.</span></span>

## <a name="windows-powershell-job-cmdlets"></a><span data-ttu-id="ee674-134">Cmdlets de trabalho do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee674-134">Windows PowerShell Job Cmdlets</span></span>

<span data-ttu-id="ee674-135">Os cmdlets a seguir são fornecidos pelo Windows PowerShell para gerenciar trabalhos em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="ee674-135">The following cmdlets are provided by Windows PowerShell to manage background jobs.</span></span>

[<span data-ttu-id="ee674-136">Get-Job</span><span class="sxs-lookup"><span data-stu-id="ee674-136">Get-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Get-Job)

<span data-ttu-id="ee674-137">Obtém trabalhos em segundo plano do Windows PowerShell que estão em execução na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="ee674-137">Gets Windows PowerShell background jobs that are running in the current session.</span></span>

[<span data-ttu-id="ee674-138">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="ee674-138">Receive-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Receive-Job)

<span data-ttu-id="ee674-139">Obtém os resultados dos trabalhos de plano de fundo do Windows PowerShell na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="ee674-139">Gets the results of the Windows PowerShell background jobs in the current session.</span></span>

[<span data-ttu-id="ee674-140">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="ee674-140">Remove-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Remove-Job)

<span data-ttu-id="ee674-141">Exclui um trabalho em plano de fundo do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee674-141">Deletes a Windows PowerShell background job.</span></span>

[<span data-ttu-id="ee674-142">Start-Job</span><span class="sxs-lookup"><span data-stu-id="ee674-142">Start-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Start-Job)

<span data-ttu-id="ee674-143">Inicia um trabalho em segundo plano do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee674-143">Starts a Windows PowerShell background job.</span></span>

[<span data-ttu-id="ee674-144">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="ee674-144">Stop-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Stop-Job)

<span data-ttu-id="ee674-145">Interrompe um trabalho em plano de fundo do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee674-145">Stops a Windows PowerShell background job.</span></span>

[<span data-ttu-id="ee674-146">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="ee674-146">Wait-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Wait-Job)

<span data-ttu-id="ee674-147">Suprime o prompt de comando até que um ou todos os trabalhos em segundo plano do Windows PowerShell executados na sessão sejam concluídos.</span><span class="sxs-lookup"><span data-stu-id="ee674-147">Suppresses the command prompt until one or all of the Windows PowerShell background jobs running in the session are complete.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee674-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ee674-148">See Also</span></span>

<span data-ttu-id="ee674-149">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="ee674-149">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
