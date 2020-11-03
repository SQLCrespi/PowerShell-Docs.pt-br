---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/wait-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Job
ms.openlocfilehash: acf01415c9722b6da95e70a8db1b558c3e14662b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193494"
---
# <span data-ttu-id="c3757-103">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="c3757-103">Wait-Job</span></span>

## <span data-ttu-id="c3757-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="c3757-104">SYNOPSIS</span></span>
<span data-ttu-id="c3757-105">Suprime o prompt de comando até que um ou todos os trabalhos em segundo plano do Windows PowerShell em execução na sessão sejam concluídos.</span><span class="sxs-lookup"><span data-stu-id="c3757-105">Suppresses the command prompt until one or all of the Windows PowerShell background jobs running in the session are completed.</span></span>

## <span data-ttu-id="c3757-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c3757-106">SYNTAX</span></span>

### <span data-ttu-id="c3757-107">SessionIdParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="c3757-107">SessionIdParameterSet (Default)</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Id] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="c3757-108">JobParameterSet</span><span class="sxs-lookup"><span data-stu-id="c3757-108">JobParameterSet</span></span>

```
Wait-Job [-Job] <Job[]> [-Any] [-Timeout <Int32>] [-Force] [<CommonParameters>]
```

### <span data-ttu-id="c3757-109">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="c3757-109">NameParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="c3757-110">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="c3757-110">InstanceIdParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="c3757-111">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="c3757-111">StateParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-State] <JobState> [<CommonParameters>]
```

### <span data-ttu-id="c3757-112">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="c3757-112">FilterParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Filter] <Hashtable> [<CommonParameters>]
```

## <span data-ttu-id="c3757-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c3757-113">DESCRIPTION</span></span>
<span data-ttu-id="c3757-114">O cmdlet **Wait-Job** aguarda a conclusão dos trabalhos em segundo plano do Windows PowerShell antes de exibir o prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="c3757-114">The **Wait-Job** cmdlet waits for Windows PowerShell background jobs to finish before it displays the command prompt.</span></span>
<span data-ttu-id="c3757-115">Você pode aguardar até que qualquer trabalho em segundo plano seja concluído, ou até que todos os trabalhos em segundo plano sejam concluídos, e pode definir um tempo de espera máximo para o trabalho.</span><span class="sxs-lookup"><span data-stu-id="c3757-115">You can wait until any background job is complete, or until all background jobs are complete, and you can set a maximum wait time for the job.</span></span>

<span data-ttu-id="c3757-116">Quando os comandos no trabalho estiverem concluídos, **Wait-Job** exibirá o prompt de comando e retornará um objeto de trabalho para que você possa redirecioná-lo para outro comando.</span><span class="sxs-lookup"><span data-stu-id="c3757-116">When the commands in the job are complete, **Wait-Job** displays the command prompt and returns a job object so that you can pipe it to another command.</span></span>

<span data-ttu-id="c3757-117">Você pode usar o cmdlet **Wait-Job** para aguardar trabalhos em segundo plano, como aqueles que foram iniciados usando o cmdlet Start-Job ou o parâmetro *AsJob* do cmdlet Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="c3757-117">You can use **Wait-Job** cmdlet to wait for background jobs, such as those that were started by using the Start-Job cmdlet or the *AsJob* parameter of the Invoke-Command cmdlet.</span></span>
<span data-ttu-id="c3757-118">Para obter mais informações sobre trabalhos em segundo plano do Windows PowerShell, consulte about_Jobs.</span><span class="sxs-lookup"><span data-stu-id="c3757-118">For more information about Windows PowerShell background jobs, see about_Jobs.</span></span>

<span data-ttu-id="c3757-119">A partir do Windows PowerShell 3,0, o cmdlet **Wait-Job** também aguarda tipos de trabalhos personalizados, como trabalhos de fluxo de trabalho e instâncias de trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="c3757-119">Starting in Windows PowerShell 3.0, the **Wait-Job** cmdlet also waits for custom job types, such as workflow jobs and instances of scheduled jobs.</span></span>
<span data-ttu-id="c3757-120">Para habilitar o **trabalho de espera** para aguardar trabalhos de um tipo específico, importe o módulo que dá suporte ao tipo de trabalho personalizado na sessão antes de executar o cmdlet Get-Job, seja usando o cmdlet Import-Module ou usando ou obtendo um cmdlet no módulo.</span><span class="sxs-lookup"><span data-stu-id="c3757-120">To enable **Wait-Job** to wait for jobs of a particular type, import the module that supports the custom job type into the session before you run the Get-Job cmdlet, either by using the Import-Module cmdlet or by using or getting a cmdlet in the module.</span></span>
<span data-ttu-id="c3757-121">Para obter informações sobre um tipo específico de trabalho personalizado, consulte a documentação do recurso de tipo de trabalho personalizado.</span><span class="sxs-lookup"><span data-stu-id="c3757-121">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="c3757-122">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="c3757-122">EXAMPLES</span></span>

### <span data-ttu-id="c3757-123">Exemplo 1: aguardar todos os trabalhos</span><span class="sxs-lookup"><span data-stu-id="c3757-123">Example 1: Wait for all jobs</span></span>

```
PS C:\> Get-Job | Wait-Job
```

<span data-ttu-id="c3757-124">Esse comando espera que todos os trabalhos em segundo plano em execução na sessão sejam concluídos.</span><span class="sxs-lookup"><span data-stu-id="c3757-124">This command waits for all of the background jobs running in the session to finish.</span></span>

### <span data-ttu-id="c3757-125">Exemplo 2: aguardar os trabalhos iniciados em computadores remotos usando Start-Job</span><span class="sxs-lookup"><span data-stu-id="c3757-125">Example 2: Wait for jobs started on remote computers by using Start-Job</span></span>

```
PS C:\> $s = New-PSSession Server01, Server02, Server03
PS C:\> Invoke-Command -Session $s -ScriptBlock {Start-Job -Name Date1 -ScriptBlock {Get-Date}}
PS C:\> $done = Invoke-Command -Session $s -Command {Wait-Job -Name Date1}
PS C:\> $done.Count
3
```

<span data-ttu-id="c3757-126">Este exemplo mostra como usar o cmdlet **Wait-Job** com trabalhos iniciados em computadores remotos usando o cmdlet **Start-Job** .</span><span class="sxs-lookup"><span data-stu-id="c3757-126">This example shows how to use the **Wait-Job** cmdlet with jobs started on remote computers by using the **Start-Job** cmdlet.</span></span>
<span data-ttu-id="c3757-127">Os comandos **Start-Job** e **Wait-Job** são enviados para o computador remoto usando o cmdlet **Invoke-Command** .</span><span class="sxs-lookup"><span data-stu-id="c3757-127">Both **Start-Job** and **Wait-Job** commands are submitted to the remote computer by using the **Invoke-Command** cmdlet.</span></span>

<span data-ttu-id="c3757-128">Este exemplo usa **Wait-Job** para determinar se um comando Get-Date em execução como um trabalho em segundo plano em três computadores diferentes foi concluído.</span><span class="sxs-lookup"><span data-stu-id="c3757-128">This example uses **Wait-Job** to determine whether a Get-Date command running as a background job on three different computers is finished.</span></span>

<span data-ttu-id="c3757-129">O primeiro comando cria uma sessão do Windows PowerShell ( **PSSession** ) em cada um dos três computadores remotos e os armazena na variável $s.</span><span class="sxs-lookup"><span data-stu-id="c3757-129">The first command creates a Windows PowerShell session ( **PSSession** ) on each of the three remote computers and stores them in the $s variable.</span></span>

<span data-ttu-id="c3757-130">O segundo comando usa **Invoke-Command** para executar **Start-Job** em cada uma das três sessões no $s.</span><span class="sxs-lookup"><span data-stu-id="c3757-130">The second command uses **Invoke-Command** to run **Start-Job** in each of the three sessions in $s.</span></span>
<span data-ttu-id="c3757-131">Todos os trabalhos são nomeados Data1.</span><span class="sxs-lookup"><span data-stu-id="c3757-131">All of the jobs are named Date1.</span></span>

<span data-ttu-id="c3757-132">O terceiro comando usa **Invoke-Command** para executar o **trabalho de espera** .</span><span class="sxs-lookup"><span data-stu-id="c3757-132">The third command uses **Invoke-Command** to run **Wait-Job** .</span></span>
<span data-ttu-id="c3757-133">Esse comando espera que os trabalhos data1 em cada computador sejam concluídos.</span><span class="sxs-lookup"><span data-stu-id="c3757-133">This command waits for the Date1 jobs on each computer to finish.</span></span>
<span data-ttu-id="c3757-134">Ele armazena a coleção resultante (matriz) dos objetos de trabalho na variável $done.</span><span class="sxs-lookup"><span data-stu-id="c3757-134">It stores the resulting collection (array) of job objects in the $done variable.</span></span>

<span data-ttu-id="c3757-135">O quarto comando usa a propriedade **Count** da matriz de objetos de trabalho na variável $Done para determinar quantos dos trabalhos foram concluídos.</span><span class="sxs-lookup"><span data-stu-id="c3757-135">The fourth command uses the **Count** property of the array of job objects in the $done variable to determine how many of the jobs are finished.</span></span>

### <span data-ttu-id="c3757-136">Exemplo 3: determinar quando o primeiro trabalho em segundo plano é concluído</span><span class="sxs-lookup"><span data-stu-id="c3757-136">Example 3: Determine when the first background job finishes</span></span>

```
PS C:\> $s = New-PSSession (Get-Content Machines.txt)
PS C:\> $c = 'Get-EventLog -LogName System | where {$_.EntryType -eq "error" --and $_.Source -eq "LSASRV"} | Out-File Errors.txt'
PS C:\> Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {$Using:c}
PS C:\> Invoke-Command -Session $s -ScriptBlock {Wait-Job -Any}
```

<span data-ttu-id="c3757-137">Este exemplo usa o parâmetro *any* do **trabalho de espera** para determinar quando o primeiro dos muitos trabalhos em segundo plano em execução na sessão atual são concluídos.</span><span class="sxs-lookup"><span data-stu-id="c3757-137">This example uses the *Any* parameter of **Wait-Job** to determine when the first of many background jobs running in the current session are completed.</span></span>
<span data-ttu-id="c3757-138">Ele também mostra como usar o cmdlet **Wait-Job** para aguardar a conclusão de trabalhos remotos.</span><span class="sxs-lookup"><span data-stu-id="c3757-138">It also shows how to use the **Wait-Job** cmdlet to wait for remote jobs to finish.</span></span>

<span data-ttu-id="c3757-139">O primeiro comando cria uma **PSSession** em cada um dos computadores listados no arquivo de Machines.txt e armazena os objetos **PSSession** na variável $s.</span><span class="sxs-lookup"><span data-stu-id="c3757-139">The first command creates a **PSSession** on each of the computers listed in the Machines.txt file and stores the **PSSession** objects in the $s variable.</span></span>
<span data-ttu-id="c3757-140">O comando usa o cmdlet Get-Content para obter o conteúdo do arquivo.</span><span class="sxs-lookup"><span data-stu-id="c3757-140">The command uses the Get-Content cmdlet to get the contents of the file.</span></span>
<span data-ttu-id="c3757-141">O comando **Get-Content** é colocado entre parênteses para garantir que ele seja executado antes do comando New-PSSession.</span><span class="sxs-lookup"><span data-stu-id="c3757-141">The **Get-Content** command is enclosed in parentheses to make sure that it runs before the New-PSSession command.</span></span>

<span data-ttu-id="c3757-142">O segundo comando armazena uma cadeia de caracteres de comando **Get-EventLog** , entre aspas, na variável $c.</span><span class="sxs-lookup"><span data-stu-id="c3757-142">The second command stores a **Get-EventLog** command string, in quotation marks, in the $c variable.</span></span>

<span data-ttu-id="c3757-143">O terceiro comando usa Invoke-Command cmdlet para executar **Start-Job** em cada uma das sessões no $s.</span><span class="sxs-lookup"><span data-stu-id="c3757-143">The third command uses Invoke-Command cmdlet to run **Start-Job** in each of the sessions in $s.</span></span>
<span data-ttu-id="c3757-144">O comando **Start-Job** inicia um trabalho em segundo plano que executa o comando **Get-EventLog** na variável $c.</span><span class="sxs-lookup"><span data-stu-id="c3757-144">The **Start-Job** command starts a background job that runs the **Get-EventLog** command in the $c variable.</span></span>

<span data-ttu-id="c3757-145">O comando usa o modificador de escopo **Using** para indicar que a variável $c foi definida no computador local.</span><span class="sxs-lookup"><span data-stu-id="c3757-145">The command uses the **Using** scope modifier to indicate that the $c variable was defined on the local computer.</span></span>
<span data-ttu-id="c3757-146">O modificador de escopo **Using** foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c3757-146">The **Using** scope modifier is introduced in Windows PowerShell 3.0.</span></span>
<span data-ttu-id="c3757-147">Para obter mais informações sobre o modificador de escopo de **uso** , consulte about_Remote_Variables ( https://go.microsoft.com/fwlink/?LinkID=252653) .</span><span class="sxs-lookup"><span data-stu-id="c3757-147">For more information about the **Using** scope modifier, see about_Remote_Variables (https://go.microsoft.com/fwlink/?LinkID=252653).</span></span>

<span data-ttu-id="c3757-148">O quarto comando usa **Invoke-Command** para executar um comando **Wait-Job** nas sessões.</span><span class="sxs-lookup"><span data-stu-id="c3757-148">The fourth command uses **Invoke-Command** to run a **Wait-Job** command in the sessions.</span></span>
<span data-ttu-id="c3757-149">Ele usa o parâmetro *any* para aguardar até que o primeiro trabalho nos computadores remotos seja concluído.</span><span class="sxs-lookup"><span data-stu-id="c3757-149">It uses the *Any* parameter to wait until the first job on the remote computers is completed.</span></span>

### <span data-ttu-id="c3757-150">Exemplo 4: definir um tempo de espera para trabalhos em computadores remotos</span><span class="sxs-lookup"><span data-stu-id="c3757-150">Example 4: Set a wait time for jobs on remote computers</span></span>

```
PS C:\> $s = New-PSSession Server01, Server02, Server03
PS C:\> $jobs = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {Get-Date}}
PS C:\> $done = Invoke-Command -Session $s -ScriptBlock {Wait-Job -Timeout 30}
```

<span data-ttu-id="c3757-151">Este exemplo mostra como usar o parâmetro *Timeout* do **trabalho de espera** para definir um tempo de espera máximo para os trabalhos em execução em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="c3757-151">This example shows how to use the *Timeout* parameter of **Wait-Job** to set a maximum wait time for the jobs running on remote computers.</span></span>

<span data-ttu-id="c3757-152">O primeiro comando cria uma **PSSession** em cada um dos três computadores remotos (Server01, Server02 e Server03) e, em seguida, armazena os objetos **PSSession** na variável $s.</span><span class="sxs-lookup"><span data-stu-id="c3757-152">The first command creates a **PSSession** on each of three remote computers (Server01, Server02, and Server03), and then stores the **PSSession** objects in the $s variable.</span></span>

<span data-ttu-id="c3757-153">O segundo comando usa **Invoke-Command** para executar **Start-Job** em cada um dos objetos **PSSession** no $s.</span><span class="sxs-lookup"><span data-stu-id="c3757-153">The second command uses **Invoke-Command** to run **Start-Job** in each of the **PSSession** objects in $s.</span></span>
<span data-ttu-id="c3757-154">Ele armazena os objetos de trabalho resultantes na variável $jobs.</span><span class="sxs-lookup"><span data-stu-id="c3757-154">It stores the resulting job objects in the $jobs variable.</span></span>

<span data-ttu-id="c3757-155">O terceiro comando usa **Invoke-Command** para executar o **trabalho de espera** em cada uma das sessões no $s.</span><span class="sxs-lookup"><span data-stu-id="c3757-155">The third command uses **Invoke-Command** to run **Wait-Job** in each of the sessions in $s.</span></span>
<span data-ttu-id="c3757-156">O comando **Wait-Job** determina se todos os comandos foram concluídos dentro de 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="c3757-156">The **Wait-Job** command determines whether all of the commands have completed within 30 seconds.</span></span>
<span data-ttu-id="c3757-157">Ele usa o parâmetro *Timeout* com um valor de 30 para estabelecer o tempo de espera máximo e, em seguida, armazena os resultados do comando na variável $done.</span><span class="sxs-lookup"><span data-stu-id="c3757-157">It uses the *Timeout* parameter with a value of 30 to establish the maximum wait time, and then stores the results of the command in the $done variable.</span></span>

<span data-ttu-id="c3757-158">Nesse caso, após 30 segundos, apenas o comando no computador Server02 foi concluído.</span><span class="sxs-lookup"><span data-stu-id="c3757-158">In this case, after 30 seconds, only the command on the Server02 computer has completed.</span></span>
<span data-ttu-id="c3757-159">**Wait-Job** encerra a espera, exibe o prompt de comando e retorna o objeto que representa o trabalho que foi concluído.</span><span class="sxs-lookup"><span data-stu-id="c3757-159">**Wait-Job** ends the wait, displays the command prompt, and returns the object that represents the job that was completed.</span></span>

<span data-ttu-id="c3757-160">A variável $done contém um objeto de trabalho que representa o trabalho executado no Server02.</span><span class="sxs-lookup"><span data-stu-id="c3757-160">The $done variable contains a job object that represents the job that ran on Server02.</span></span>

### <span data-ttu-id="c3757-161">Exemplo 5: Aguarde até que um dos vários trabalhos seja concluído</span><span class="sxs-lookup"><span data-stu-id="c3757-161">Example 5: Wait until one of several jobs finishes</span></span>

```
PS C:\> Wait-Job -id 1,2,5 -Any
```

<span data-ttu-id="c3757-162">Esse comando identifica três trabalhos por suas IDs e aguarda até que qualquer um deles seja concluído.</span><span class="sxs-lookup"><span data-stu-id="c3757-162">This command identifies three jobs by their IDs and waits until any one of them are completed.</span></span>
<span data-ttu-id="c3757-163">O prompt de comando retorna quando o primeiro trabalho é concluído.</span><span class="sxs-lookup"><span data-stu-id="c3757-163">The command prompt returns when the first job finishes.</span></span>

### <span data-ttu-id="c3757-164">Exemplo 6: aguardar um período e permitir que o trabalho continue em segundo plano</span><span class="sxs-lookup"><span data-stu-id="c3757-164">Example 6: Wait for a period, then allow job to continue in background</span></span>

```
PS C:\> Wait-Job -Name "DailyLog" -Timeout 120
```

<span data-ttu-id="c3757-165">Esse comando aguarda 120 segundos (dois minutos) para que o trabalho de DailyLog seja concluído.</span><span class="sxs-lookup"><span data-stu-id="c3757-165">This command waits 120 seconds (two minutes) for the DailyLog job to finish.</span></span>
<span data-ttu-id="c3757-166">Se o trabalho não for concluído nos próximos dois minutos, o prompt de comando retornará de qualquer forma e o trabalho continuará a ser executado em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="c3757-166">If the job does not finish in the next two minutes, the command prompt returns anyway, and the job continues to run in the background.</span></span>

### <span data-ttu-id="c3757-167">Exemplo 7: aguardar um trabalho por nome</span><span class="sxs-lookup"><span data-stu-id="c3757-167">Example 7: Wait for a job by name</span></span>

```
PS C:\> Wait-Job -Name "Job3"
```

<span data-ttu-id="c3757-168">Esse comando usa o nome do trabalho para identificar o trabalho a ser aguardado.</span><span class="sxs-lookup"><span data-stu-id="c3757-168">This command uses the job name to identify the job for which to wait.</span></span>

### <span data-ttu-id="c3757-169">Exemplo 8: aguardar trabalhos no computador local iniciados com Start-Job</span><span class="sxs-lookup"><span data-stu-id="c3757-169">Example 8: Wait for jobs on local computer started with Start-Job</span></span>

```
PS C:\> $j = Start-Job -ScriptBlock {Get-ChildItem *.ps1| where {$_lastwritetime -gt ((Get-Date) - (New-TimeSpan -Days 7))}}
PS C:\> $j | Wait-Job
```

<span data-ttu-id="c3757-170">Este exemplo mostra como usar o cmdlet **Wait-Job** com trabalhos iniciados no computador local usando **Start-Job** .</span><span class="sxs-lookup"><span data-stu-id="c3757-170">This example shows how to use the **Wait-Job** cmdlet with jobs started on the local computer by using **Start-Job** .</span></span>

<span data-ttu-id="c3757-171">Esses comandos iniciam um trabalho que obtém os arquivos de script do Windows PowerShell que foram adicionados ou atualizados na última semana.</span><span class="sxs-lookup"><span data-stu-id="c3757-171">These commands start a job that gets the Windows PowerShell script files that were added or updated in the last week.</span></span>

<span data-ttu-id="c3757-172">O primeiro comando usa **Start-Job** para iniciar um trabalho em segundo plano no computador local.</span><span class="sxs-lookup"><span data-stu-id="c3757-172">The first command uses **Start-Job** to start a background job on the local computer.</span></span>
<span data-ttu-id="c3757-173">O trabalho executa um comando Get-ChildItem que obtém todos os arquivos que têm uma extensão de nome de arquivo. ps1 que foram adicionados ou atualizados na última semana.</span><span class="sxs-lookup"><span data-stu-id="c3757-173">The job runs a Get-ChildItem command that gets all of the files that have a .ps1 file name extension that were added or updated in the last week.</span></span>

<span data-ttu-id="c3757-174">O terceiro comando usa **Wait-Job** para aguardar até que o trabalho seja concluído.</span><span class="sxs-lookup"><span data-stu-id="c3757-174">The third command uses **Wait-Job** to wait until the job is completed.</span></span>
<span data-ttu-id="c3757-175">Quando o trabalho for concluído, o comando exibirá o objeto de trabalho, que contém informações sobre o trabalho.</span><span class="sxs-lookup"><span data-stu-id="c3757-175">When the job finishes, the command displays the job object, which contains information about the job.</span></span>

### <span data-ttu-id="c3757-176">Exemplo 9: aguardar trabalhos iniciados em computadores remotos usando Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="c3757-176">Example 9: Wait for jobs started on remote computers by using Invoke-Command</span></span>

```
PS C:\> $s = New-PSSession Server01, Server02, Server03
PS C:\> $j = Invoke-Command -Session $s -ScriptBlock {Get-Process} -AsJob
PS C:\> $j | Wait-Job
```

<span data-ttu-id="c3757-177">Este exemplo mostra como usar o **trabalho de espera** com trabalhos iniciados em computadores remotos usando o parâmetro *AsJob* do **Invoke-Command** .</span><span class="sxs-lookup"><span data-stu-id="c3757-177">This example shows how to use **Wait-Job** with jobs started on remote computers by using the *AsJob* parameter of **Invoke-Command** .</span></span>
<span data-ttu-id="c3757-178">Ao usar *AsJob* , o trabalho é criado no computador local e os resultados são retornados automaticamente para o computador local, mesmo que o trabalho seja executado nos computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="c3757-178">When using *AsJob* , the job is created on the local computer and the results are automatically returned to the local computer, even though the job runs on the remote computers.</span></span>

<span data-ttu-id="c3757-179">Este exemplo usa **Wait-Job** para determinar se um comando **Get-Process** em execução nas sessões em três computadores remotos foi concluído.</span><span class="sxs-lookup"><span data-stu-id="c3757-179">This example uses **Wait-Job** to determine whether a **Get-Process** command running in the sessions on three remote computers is completed.</span></span>

<span data-ttu-id="c3757-180">O primeiro comando cria objetos **PSSession** em três computadores e os armazena na variável $s.</span><span class="sxs-lookup"><span data-stu-id="c3757-180">The first command creates **PSSession** objects on three computers and stores them in the $s variable.</span></span>

<span data-ttu-id="c3757-181">O segundo comando usa **Invoke-Command** para executar o **Get-Process** em cada uma das três sessões no $s.</span><span class="sxs-lookup"><span data-stu-id="c3757-181">The second command uses **Invoke-Command** to run **Get-Process** in each of the three sessions in $s.</span></span>
<span data-ttu-id="c3757-182">O comando usa o parâmetro *AsJob* para executar o comando de forma assíncrona como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="c3757-182">The command uses the *AsJob* parameter to run the command asynchronously as a background job.</span></span>
<span data-ttu-id="c3757-183">O comando retorna um objeto de trabalho, assim como os trabalhos iniciados usando **Start-Job** , e o objeto de trabalho é armazenado na variável $j.</span><span class="sxs-lookup"><span data-stu-id="c3757-183">The command returns a job object, just like the jobs started by using **Start-Job** , and the job object is stored in the $j variable.</span></span>

<span data-ttu-id="c3757-184">O terceiro comando usa um operador de pipeline (|) para enviar o objeto de trabalho em $j para o cmdlet **Wait-Job** .</span><span class="sxs-lookup"><span data-stu-id="c3757-184">The third command uses a pipeline operator (|) to send the job object in $j to the **Wait-Job** cmdlet.</span></span>
<span data-ttu-id="c3757-185">Um comando **Invoke-Command** não é necessário nesse caso, pois o trabalho reside no computador local.</span><span class="sxs-lookup"><span data-stu-id="c3757-185">An **Invoke-Command** command is not required in this case, because the job resides on the local computer.</span></span>

### <span data-ttu-id="c3757-186">Exemplo 10: aguardar um trabalho que tenha uma ID</span><span class="sxs-lookup"><span data-stu-id="c3757-186">Example 10: Wait for a job that has an ID</span></span>

```
PS C:\> Get-Job

Id   Name     State      HasMoreData     Location             Command
--   ----     -----      -----------     --------             -------
1    Job1     Completed  True            localhost,Server01.. get-service
4    Job4     Completed  True            localhost            dir | where

PS C:\> Wait-Job -Id 1
```

<span data-ttu-id="c3757-187">Este comando aguarda o trabalho com um valor de ID de 1.</span><span class="sxs-lookup"><span data-stu-id="c3757-187">This command waits for the job with an ID value of 1.</span></span>

## <span data-ttu-id="c3757-188">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c3757-188">PARAMETERS</span></span>

### <span data-ttu-id="c3757-189">-Qualquer</span><span class="sxs-lookup"><span data-stu-id="c3757-189">-Any</span></span>
<span data-ttu-id="c3757-190">Indica que esse cmdlet exibe o prompt de comando e retorna o objeto de trabalho, quando qualquer trabalho é concluído.</span><span class="sxs-lookup"><span data-stu-id="c3757-190">Indicates that this cmdlet displays the command prompt, and returns the job object, when any job finishes.</span></span>
<span data-ttu-id="c3757-191">Por padrão, **Wait-Job** aguarda até que todos os trabalhos especificados sejam concluídos antes de exibir o prompt.</span><span class="sxs-lookup"><span data-stu-id="c3757-191">By default, **Wait-Job** waits until all of the specified jobs are complete before it displays the prompt.</span></span>

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

### <span data-ttu-id="c3757-192">-Filter</span><span class="sxs-lookup"><span data-stu-id="c3757-192">-Filter</span></span>
<span data-ttu-id="c3757-193">Especifica uma tabela de hash de condições.</span><span class="sxs-lookup"><span data-stu-id="c3757-193">Specifies a hash table of conditions.</span></span>
<span data-ttu-id="c3757-194">Esse cmdlet aguarda trabalhos que atendem a todas as condições na tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="c3757-194">This cmdlet waits for jobs that satisfy all of the conditions in the hash table.</span></span>
<span data-ttu-id="c3757-195">Insira uma tabela de hash na qual as chaves são propriedades do trabalho e os valores são valores de propriedade do trabalho.</span><span class="sxs-lookup"><span data-stu-id="c3757-195">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="c3757-196">Este parâmetro funciona somente em tipos de trabalho personalizados, como os de fluxo de trabalho e os trabalhos agendados.</span><span class="sxs-lookup"><span data-stu-id="c3757-196">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span>
<span data-ttu-id="c3757-197">Ele não funciona em trabalhos em segundo plano padrão, como aqueles criados usando o cmdlet **Start-Job** .</span><span class="sxs-lookup"><span data-stu-id="c3757-197">It does not work on standard background jobs, such as those created by using the **Start-Job** cmdlet.</span></span>
<span data-ttu-id="c3757-198">Para obter informações sobre o suporte para este parâmetro, consulte o tópico da Ajuda para o tipo de trabalho em questão.</span><span class="sxs-lookup"><span data-stu-id="c3757-198">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="c3757-199">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c3757-199">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c3757-200">-Force</span><span class="sxs-lookup"><span data-stu-id="c3757-200">-Force</span></span>
<span data-ttu-id="c3757-201">Indica que esse cmdlet continua aguardando trabalhos no estado suspenso ou desconectado.</span><span class="sxs-lookup"><span data-stu-id="c3757-201">Indicates that this cmdlet continues to wait for jobs in the Suspended or Disconnected state.</span></span>
<span data-ttu-id="c3757-202">Por padrão, **Wait-Job** retorna ou termina a espera, quando os trabalhos estão em um dos seguintes Estados:</span><span class="sxs-lookup"><span data-stu-id="c3757-202">By default, **Wait-Job** returns, or ends  the wait, when jobs are in one of the following states:</span></span>

- <span data-ttu-id="c3757-203">Concluído</span><span class="sxs-lookup"><span data-stu-id="c3757-203">Completed</span></span>
- <span data-ttu-id="c3757-204">Falhou</span><span class="sxs-lookup"><span data-stu-id="c3757-204">Failed</span></span>
- <span data-ttu-id="c3757-205">Parado</span><span class="sxs-lookup"><span data-stu-id="c3757-205">Stopped</span></span>
- <span data-ttu-id="c3757-206">Suspenso</span><span class="sxs-lookup"><span data-stu-id="c3757-206">Suspended</span></span>
- <span data-ttu-id="c3757-207">Desconectado</span><span class="sxs-lookup"><span data-stu-id="c3757-207">Disconnected</span></span>

<span data-ttu-id="c3757-208">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c3757-208">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c3757-209">-Id</span><span class="sxs-lookup"><span data-stu-id="c3757-209">-Id</span></span>
<span data-ttu-id="c3757-210">Especifica uma matriz de IDs de trabalhos para os quais esse cmdlet espera.</span><span class="sxs-lookup"><span data-stu-id="c3757-210">Specifies an array of IDs of jobs for which this cmdlet waits.</span></span>

<span data-ttu-id="c3757-211">A ID é um inteiro que identifica exclusivamente o trabalho na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="c3757-211">The ID is an integer that uniquely identifies the job in the current session.</span></span>
<span data-ttu-id="c3757-212">É mais fácil lembrar e digitar do que a ID da instância, mas só é exclusiva na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="c3757-212">It is easier to remember and type than the instance ID, but it is unique only in the current session.</span></span>
<span data-ttu-id="c3757-213">Você pode digitar uma ou mais IDs, separadas por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="c3757-213">You can type one or more IDs, separated by commas.</span></span>
<span data-ttu-id="c3757-214">Para localizar a ID de um trabalho, digite `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="c3757-214">To find the ID of a job, type `Get-Job`.</span></span>

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

### <span data-ttu-id="c3757-215">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="c3757-215">-InstanceId</span></span>
<span data-ttu-id="c3757-216">Especifica uma matriz de IDs de instância dos trabalhos para os quais esse cmdlet espera.</span><span class="sxs-lookup"><span data-stu-id="c3757-216">Specifies an array of instance IDs of jobs for which this cmdlet waits.</span></span>
<span data-ttu-id="c3757-217">O padrão é obter todos os trabalhos.</span><span class="sxs-lookup"><span data-stu-id="c3757-217">The default is all jobs.</span></span>

<span data-ttu-id="c3757-218">Uma ID de instância é um GUID que identifica exclusivamente o trabalho no computador.</span><span class="sxs-lookup"><span data-stu-id="c3757-218">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span>
<span data-ttu-id="c3757-219">Para localizar o identificador da instância de um trabalho, use o cmdlet **Get-Job** .</span><span class="sxs-lookup"><span data-stu-id="c3757-219">To find the instance ID of a job, use **Get-Job** .</span></span>

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

### <span data-ttu-id="c3757-220">-Trabalho</span><span class="sxs-lookup"><span data-stu-id="c3757-220">-Job</span></span>
<span data-ttu-id="c3757-221">Especifica os trabalhos para os quais esse cmdlet espera.</span><span class="sxs-lookup"><span data-stu-id="c3757-221">Specifies the jobs for which this cmdlet waits.</span></span>
<span data-ttu-id="c3757-222">Insira uma variável que contém os objetos de trabalho ou um comando que obtém os objetos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="c3757-222">Enter a variable that contains the job objects or a command that gets the job objects.</span></span>
<span data-ttu-id="c3757-223">Você também pode usar um operador de pipeline para enviar objetos de trabalho para o cmdlet **Wait-Job** .</span><span class="sxs-lookup"><span data-stu-id="c3757-223">You can also use a pipeline operator to send job objects to the **Wait-Job** cmdlet.</span></span>
<span data-ttu-id="c3757-224">Por padrão, as esperas de **trabalho de espera** para todos os trabalhos criados na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="c3757-224">By default, **Wait-Job** waits for all jobs created in the current session.</span></span>

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c3757-225">-Name</span><span class="sxs-lookup"><span data-stu-id="c3757-225">-Name</span></span>
<span data-ttu-id="c3757-226">Especifica nomes amigáveis de trabalhos para os quais esse cmdlet espera.</span><span class="sxs-lookup"><span data-stu-id="c3757-226">Specifies friendly names of jobs for which this cmdlet waits.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c3757-227">-Estado</span><span class="sxs-lookup"><span data-stu-id="c3757-227">-State</span></span>
<span data-ttu-id="c3757-228">Especifica um estado de trabalho.</span><span class="sxs-lookup"><span data-stu-id="c3757-228">Specifies a job state.</span></span>
<span data-ttu-id="c3757-229">Esse cmdlet aguarda apenas os trabalhos no estado especificado.</span><span class="sxs-lookup"><span data-stu-id="c3757-229">This cmdlet waits only for jobs in the specified state.</span></span>
<span data-ttu-id="c3757-230">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="c3757-230">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="c3757-231">NotStarted</span><span class="sxs-lookup"><span data-stu-id="c3757-231">NotStarted</span></span>
- <span data-ttu-id="c3757-232">Executando</span><span class="sxs-lookup"><span data-stu-id="c3757-232">Running</span></span>
- <span data-ttu-id="c3757-233">Concluído</span><span class="sxs-lookup"><span data-stu-id="c3757-233">Completed</span></span>
- <span data-ttu-id="c3757-234">Falhou</span><span class="sxs-lookup"><span data-stu-id="c3757-234">Failed</span></span>
- <span data-ttu-id="c3757-235">Parado</span><span class="sxs-lookup"><span data-stu-id="c3757-235">Stopped</span></span>
- <span data-ttu-id="c3757-236">Bloqueado</span><span class="sxs-lookup"><span data-stu-id="c3757-236">Blocked</span></span>
- <span data-ttu-id="c3757-237">Suspenso</span><span class="sxs-lookup"><span data-stu-id="c3757-237">Suspended</span></span>
- <span data-ttu-id="c3757-238">Desconectado</span><span class="sxs-lookup"><span data-stu-id="c3757-238">Disconnected</span></span>
- <span data-ttu-id="c3757-239">Suspensão</span><span class="sxs-lookup"><span data-stu-id="c3757-239">Suspending</span></span>
- <span data-ttu-id="c3757-240">Parando</span><span class="sxs-lookup"><span data-stu-id="c3757-240">Stopping</span></span>

<span data-ttu-id="c3757-241">Para obter mais informações sobre os Estados de trabalho, consulte [Enumeração JobState](https://msdn.microsoft.com/library/system.management.automation.jobstate) na biblioteca MSDN.</span><span class="sxs-lookup"><span data-stu-id="c3757-241">For more information about job states, see [JobState Enumeration](https://msdn.microsoft.com/library/system.management.automation.jobstate) in the MSDN library.</span></span>

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

### <span data-ttu-id="c3757-242">-Tempo limite</span><span class="sxs-lookup"><span data-stu-id="c3757-242">-Timeout</span></span>
<span data-ttu-id="c3757-243">Especifica o tempo de espera máximo para cada trabalho em segundo plano, em segundos.</span><span class="sxs-lookup"><span data-stu-id="c3757-243">Specifies the maximum wait time for each background job, in seconds.</span></span>
<span data-ttu-id="c3757-244">O valor padrão,-1, indica que o cmdlet aguarda até que o trabalho seja concluído.</span><span class="sxs-lookup"><span data-stu-id="c3757-244">The default value, -1, indicates that the cmdlet waits until the job finishes.</span></span>
<span data-ttu-id="c3757-245">O tempo começa quando você envia o comando **Wait-Job** , não o comando **Start-Job** .</span><span class="sxs-lookup"><span data-stu-id="c3757-245">The timing starts when you submit the **Wait-Job** command, not the **Start-Job** command.</span></span>

<span data-ttu-id="c3757-246">Se esse tempo for excedido, a espera termina, e o comando prompt retorna, mesmo se o trabalho ainda está em execução.</span><span class="sxs-lookup"><span data-stu-id="c3757-246">If this time is exceeded, the wait ends and the command prompt returns, even if the job is still running.</span></span>
<span data-ttu-id="c3757-247">O comando não exibe nenhuma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="c3757-247">The command does not display any error message.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c3757-248">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c3757-248">CommonParameters</span></span>
<span data-ttu-id="c3757-249">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c3757-249">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c3757-250">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c3757-250">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c3757-251">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="c3757-251">INPUTS</span></span>

### <span data-ttu-id="c3757-252">System. Management. Automation. RemotingJob</span><span class="sxs-lookup"><span data-stu-id="c3757-252">System.Management.Automation.RemotingJob</span></span>
<span data-ttu-id="c3757-253">É possível canalizar um objeto de trabalho para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c3757-253">You can pipe a job object to this cmdlet.</span></span>

## <span data-ttu-id="c3757-254">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="c3757-254">OUTPUTS</span></span>

### <span data-ttu-id="c3757-255">System. Management. Automation. PSRemotingJob</span><span class="sxs-lookup"><span data-stu-id="c3757-255">System.Management.Automation.PSRemotingJob</span></span>
<span data-ttu-id="c3757-256">Esse cmdlet retorna objetos de trabalho que representam os trabalhos concluídos.</span><span class="sxs-lookup"><span data-stu-id="c3757-256">This cmdlet returns job objects that represent the completed jobs.</span></span>
<span data-ttu-id="c3757-257">Se a espera for encerrada porque o valor do parâmetro *Timeout* é excedido, **Wait-Job** não retorna nenhum objeto.</span><span class="sxs-lookup"><span data-stu-id="c3757-257">If the wait ends because the value of the *Timeout* parameter is exceeded, **Wait-Job** does not return any objects.</span></span>

## <span data-ttu-id="c3757-258">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="c3757-258">NOTES</span></span>

* <span data-ttu-id="c3757-259">Por padrão, **Wait-Job** retorna ou termina a espera, quando os trabalhos estão em um dos seguintes Estados:</span><span class="sxs-lookup"><span data-stu-id="c3757-259">By default, **Wait-Job** returns, or ends the wait, when jobs are in one of the following states:</span></span>

- <span data-ttu-id="c3757-260">Concluído</span><span class="sxs-lookup"><span data-stu-id="c3757-260">Completed</span></span>
- <span data-ttu-id="c3757-261">Falhou</span><span class="sxs-lookup"><span data-stu-id="c3757-261">Failed</span></span>
- <span data-ttu-id="c3757-262">Parado</span><span class="sxs-lookup"><span data-stu-id="c3757-262">Stopped</span></span>
- <span data-ttu-id="c3757-263">Suspenso</span><span class="sxs-lookup"><span data-stu-id="c3757-263">Suspended</span></span>
- <span data-ttu-id="c3757-264">Desconectado à **espera direta-o trabalho** para continuar aguardando trabalhos suspensos e desconectados, use o parâmetro *Force* .</span><span class="sxs-lookup"><span data-stu-id="c3757-264">Disconnected To direct **Wait-Job** to continue to wait for Suspended and Disconnected jobs, use the *Force* parameter.</span></span>

## <span data-ttu-id="c3757-265">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="c3757-265">RELATED LINKS</span></span>

[<span data-ttu-id="c3757-266">Get-Job</span><span class="sxs-lookup"><span data-stu-id="c3757-266">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="c3757-267">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="c3757-267">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="c3757-268">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="c3757-268">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="c3757-269">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="c3757-269">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="c3757-270">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="c3757-270">Resume-Job</span></span>](Resume-Job.md)

[<span data-ttu-id="c3757-271">Start-Job</span><span class="sxs-lookup"><span data-stu-id="c3757-271">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="c3757-272">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="c3757-272">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="c3757-273">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="c3757-273">Suspend-Job</span></span>](Suspend-Job.md)
