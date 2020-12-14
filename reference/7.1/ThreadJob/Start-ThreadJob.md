---
external help file: Microsoft.PowerShell.ThreadJob.dll-Help.xml
Locale: en-US
Module Name: ThreadJob
ms.date: 12/05/2020
online version: https://docs.microsoft.com/powershell/module/threadjob/start-threadjob?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-ThreadJob
ms.openlocfilehash: bced2b87c3843833414ebfd189d003e83af9718f
ms.sourcegitcommit: f9d855dd73b916559a22e337672dea3fbb11c634
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/07/2020
ms.locfileid: "96777740"
---
# <span data-ttu-id="835b9-102">Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="835b9-102">Start-ThreadJob</span></span>

## <span data-ttu-id="835b9-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="835b9-103">SYNOPSIS</span></span>
<span data-ttu-id="835b9-104">Cria trabalhos em segundo plano semelhantes ao `Start-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="835b9-104">Creates background jobs similar to the `Start-Job` cmdlet.</span></span>

## <span data-ttu-id="835b9-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="835b9-105">SYNTAX</span></span>

### <span data-ttu-id="835b9-106">Bloco de script</span><span class="sxs-lookup"><span data-stu-id="835b9-106">ScriptBlock</span></span>

```
Start-ThreadJob [-ScriptBlock] <ScriptBlock> [-Name <String>] [-InitializationScript <ScriptBlock>]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [-ThrottleLimit <Int32>]
 [-StreamingHost <PSHost>] [<CommonParameters>]
```

### <span data-ttu-id="835b9-107">FilePath</span><span class="sxs-lookup"><span data-stu-id="835b9-107">FilePath</span></span>

```
Start-ThreadJob [-FilePath] <String> [-Name <String>] [-InitializationScript <ScriptBlock>]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [-ThrottleLimit <Int32>]
 [-StreamingHost <PSHost>] [<CommonParameters>]
```

## <span data-ttu-id="835b9-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="835b9-108">DESCRIPTION</span></span>

<span data-ttu-id="835b9-109">`Start-ThreadJob` cria trabalhos em segundo plano semelhantes ao `Start-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="835b9-109">`Start-ThreadJob` creates background jobs similar to the `Start-Job` cmdlet.</span></span> <span data-ttu-id="835b9-110">A principal diferença é que os trabalhos criados são executados em threads separados dentro do processo local.</span><span class="sxs-lookup"><span data-stu-id="835b9-110">The main difference is that the jobs which are created run in separate threads within the local process.</span></span> <span data-ttu-id="835b9-111">Por padrão, os trabalhos usam o diretório de trabalho atual do chamador que iniciou o trabalho.</span><span class="sxs-lookup"><span data-stu-id="835b9-111">By default, the jobs use the current working directory of the caller that started the job.</span></span>

<span data-ttu-id="835b9-112">O cmdlet também dá suporte a um parâmetro **ThrottleLimit** para limitar o número de trabalhos em execução ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="835b9-112">The cmdlet also supports a **ThrottleLimit** parameter to limit the number of jobs running at one time.</span></span> <span data-ttu-id="835b9-113">À medida que mais trabalhos são iniciados, eles são enfileirados e aguardam até que o número atual de trabalhos fique abaixo do limite de limitação.</span><span class="sxs-lookup"><span data-stu-id="835b9-113">As more jobs are started, they are queued and wait until the current number of jobs drops below the throttle limit.</span></span>

## <span data-ttu-id="835b9-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="835b9-114">EXAMPLES</span></span>

### <span data-ttu-id="835b9-115">Exemplo 1-criar trabalhos em segundo plano com um limite de thread de 2</span><span class="sxs-lookup"><span data-stu-id="835b9-115">Example 1 - Create background jobs with a thread limit of 2</span></span>

```powershell
Start-ThreadJob -ScriptBlock { 1..100 | % { sleep 1; "Output $_" } } -ThrottleLimit 2
Start-ThreadJob -ScriptBlock { 1..100 | % { sleep 1; "Output $_" } }
Start-ThreadJob -ScriptBlock { 1..100 | % { sleep 1; "Output $_" } }
Get-Job
```

```Output
Id   Name   PSJobTypeName   State        HasMoreData   Location     Command
--   ----   -------------   -----        -----------   --------     -------
1    Job1   ThreadJob       Running      True          PowerShell   1..100 | % { sleep 1;...
2    Job2   ThreadJob       Running      True          PowerShell   1..100 | % { sleep 1;...
3    Job3   ThreadJob       NotStarted   False         PowerShell   1..100 | % { sleep 1;...
```

### <span data-ttu-id="835b9-116">Exemplo 2 – comparar o desempenho de Start-Job e Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="835b9-116">Example 2 - Compare the performance of Start-Job and Start-ThreadJob</span></span>

<span data-ttu-id="835b9-117">Este exemplo mostra a diferença entre `Start-Job` e `Start-ThreadJob` .</span><span class="sxs-lookup"><span data-stu-id="835b9-117">This example shows the difference between `Start-Job` and `Start-ThreadJob`.</span></span> <span data-ttu-id="835b9-118">Os trabalhos executam o `Start-Sleep` cmdlet por 1 segundo.</span><span class="sxs-lookup"><span data-stu-id="835b9-118">The jobs run the `Start-Sleep` cmdlet for 1 second.</span></span> <span data-ttu-id="835b9-119">Como os trabalhos são executados em paralelo, o tempo de execução total é de cerca de 1 segundo, além de qualquer tempo necessário para criar os trabalhos.</span><span class="sxs-lookup"><span data-stu-id="835b9-119">Since the jobs run in parallel, the total execution time is about 1 second, plus any time required to create the jobs.</span></span>

```powershell
# start five background jobs each running 1 second
Measure-Command {1..5 | % {Start-Job {Start-Sleep 1}} | Wait-Job} | Select-Object TotalSeconds
Measure-Command {1..5 | % {Start-ThreadJob {Start-Sleep 1}} | Wait-Job} | Select-Object TotalSeconds
```

```Output
TotalSeconds
------------
   5.7665849
   1.5735008
```

<span data-ttu-id="835b9-120">Depois de subtrair 1 segundo para o tempo de execução, você pode ver que `Start-Job` leva cerca de 4,8 segundos para criar cinco trabalhos.</span><span class="sxs-lookup"><span data-stu-id="835b9-120">After subtracting 1 second for execution time, you can see that `Start-Job` takes about 4.8 seconds to create five jobs.</span></span> <span data-ttu-id="835b9-121">`Start-ThreadJob` é 8 vezes mais rápido, levando cerca de 0,6 segundos para criar cinco trabalhos.</span><span class="sxs-lookup"><span data-stu-id="835b9-121">`Start-ThreadJob` is 8 times faster, taking about 0.6 seconds to create five jobs.</span></span> <span data-ttu-id="835b9-122">Os resultados podem variar em seu ambiente, mas a melhoria relativa deve ser a mesma.</span><span class="sxs-lookup"><span data-stu-id="835b9-122">The results may vary in your environment but the relative improvement should be the same.</span></span>

### <span data-ttu-id="835b9-123">Exemplo 3-criar trabalhos usando InputObject</span><span class="sxs-lookup"><span data-stu-id="835b9-123">Example 3 - Create jobs using InputObject</span></span>

<span data-ttu-id="835b9-124">Neste exemplo, o bloco de script usa a `$input` variável para receber a entrada do parâmetro **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="835b9-124">In this example, the script block uses the `$input` variable to receive input from the **InputObject** parameter.</span></span> <span data-ttu-id="835b9-125">Isso também pode ser feito por meio de objetos de tubulação `Start-ThreadJob` .</span><span class="sxs-lookup"><span data-stu-id="835b9-125">This can also be done by piping objects to `Start-ThreadJob`.</span></span>

```powershell
$j = Start-ThreadJob -InputObject (Get-Process pwsh) -ScriptBlock { $input | Out-String }
$j | Wait-Job | Receive-Job
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     94   145.80     159.02      18.31   18276   1 pwsh
    101   163.30     222.05      29.00   35928   1 pwsh
```

```powershell
$j = Get-Process pwsh | Start-ThreadJob -ScriptBlock { $input | Out-String }
$j | Wait-Job | Receive-Job
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     94   145.80     159.02      18.31   18276   1 pwsh
    101   163.30     222.05      29.00   35928   1 pwsh
```

### <span data-ttu-id="835b9-126">Exemplo 4-fluxo de saída de trabalho para o host pai</span><span class="sxs-lookup"><span data-stu-id="835b9-126">Example 4 - Stream job output to parent host</span></span>

<span data-ttu-id="835b9-127">Usando o parâmetro **StreamingHost** , você pode dizer a um trabalho para direcionar toda a saída do host para um host específico.</span><span class="sxs-lookup"><span data-stu-id="835b9-127">Using the **StreamingHost** parameter you can tell a job to direct all host output to a specific host.</span></span> <span data-ttu-id="835b9-128">Sem esse parâmetro, a saída vai para a coleção de fluxo de dados de trabalho e não aparece em um console de host até que você receba a saída do trabalho.</span><span class="sxs-lookup"><span data-stu-id="835b9-128">Without this parameter the output goes to the job data stream collection and doesn't appear in a host console until you receive the output from the job.</span></span>

<span data-ttu-id="835b9-129">Para este exemplo, o host atual é passado para `Start-ThreadJob` usando a `$Host` variável automática.</span><span class="sxs-lookup"><span data-stu-id="835b9-129">For this example, the current host is passed to `Start-ThreadJob` using the `$Host` automatic variable.</span></span>

```powershell
PS> Start-ThreadJob -ScriptBlock { Read-Host 'Say hello'; Write-Warning 'Warning output' } -StreamingHost $Host

Id   Name   PSJobTypeName   State         HasMoreData     Location      Command
--   ----   -------------   -----         -----------     --------      -------
7    Job7   ThreadJob       NotStarted    False           PowerShell    Read-Host 'Say hello'; �

PS> Say hello: Hello
WARNING: Warning output
PS> Receive-Job -Id 7
Hello
WARNING: Warning output
PS>
```

<span data-ttu-id="835b9-130">Observe que o prompt de `Read-Host` é exibido e você pode digitar a entrada.</span><span class="sxs-lookup"><span data-stu-id="835b9-130">Notice that the prompt from `Read-Host` is displayed and you are able to type input.</span></span> <span data-ttu-id="835b9-131">Em seguida, a mensagem de `Write-Warning` é exibida.</span><span class="sxs-lookup"><span data-stu-id="835b9-131">Then, the message from `Write-Warning` is displayed.</span></span> <span data-ttu-id="835b9-132">O `Receive-Job` cmdlet retorna toda a saída do trabalho.</span><span class="sxs-lookup"><span data-stu-id="835b9-132">The `Receive-Job` cmdlet returns all the output from the job.</span></span>

## <span data-ttu-id="835b9-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="835b9-133">PARAMETERS</span></span>

### <span data-ttu-id="835b9-134">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="835b9-134">-ArgumentList</span></span>

<span data-ttu-id="835b9-135">Especifica uma matriz de argumentos, ou valores de parâmetro, para o script que é especificado pelos parâmetros **FilePath** ou **scriptblock** .</span><span class="sxs-lookup"><span data-stu-id="835b9-135">Specifies an array of arguments, or parameter values, for the script that is specified by the **FilePath** or **ScriptBlock** parameters.</span></span>

<span data-ttu-id="835b9-136">**ArgumentList** deve ser o último parâmetro na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="835b9-136">**ArgumentList** must be the last parameter on the command line.</span></span> <span data-ttu-id="835b9-137">Todos os valores que seguem o nome do parâmetro são valores interpretados na lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="835b9-137">All the values that follow the parameter name are interpreted values in the argument list.</span></span>

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

### <span data-ttu-id="835b9-138">-FilePath</span><span class="sxs-lookup"><span data-stu-id="835b9-138">-FilePath</span></span>

<span data-ttu-id="835b9-139">Especifica um arquivo de script para ser executado como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="835b9-139">Specifies a script file to run as a background job.</span></span> <span data-ttu-id="835b9-140">Insira o caminho e o nome do arquivo do script.</span><span class="sxs-lookup"><span data-stu-id="835b9-140">Enter the path and filename of the script.</span></span> <span data-ttu-id="835b9-141">O script deve estar no computador local ou em uma pasta que o computador local possa acessar.</span><span class="sxs-lookup"><span data-stu-id="835b9-141">The script must be on the local computer or in a folder that the local computer can access.</span></span>

<span data-ttu-id="835b9-142">Quando você usa esse parâmetro, o PowerShell converte o conteúdo do arquivo de script especificado em um bloco de script e executa o bloco de script como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="835b9-142">When you use this parameter, PowerShell converts the contents of the specified script file to a script block and runs the script block as a background job.</span></span>

```yaml
Type: System.String
Parameter Sets: FilePath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="835b9-143">-InitializationScript</span><span class="sxs-lookup"><span data-stu-id="835b9-143">-InitializationScript</span></span>

<span data-ttu-id="835b9-144">Especifica os comandos que são executados antes do trabalho ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="835b9-144">Specifies commands that run before the job starts.</span></span> <span data-ttu-id="835b9-145">Coloque os comandos entre chaves ( `{}` ) para criar um bloco de script.</span><span class="sxs-lookup"><span data-stu-id="835b9-145">Enclose the commands in braces (`{}`) to create a script block.</span></span>

<span data-ttu-id="835b9-146">Use esse parâmetro para preparar a sessão na qual o trabalho é executado.</span><span class="sxs-lookup"><span data-stu-id="835b9-146">Use this parameter to prepare the session in which the job runs.</span></span> <span data-ttu-id="835b9-147">Por exemplo, você pode usá-lo para adicionar funções e módulos à sessão.</span><span class="sxs-lookup"><span data-stu-id="835b9-147">For example, you can use it to add functions and modules to the session.</span></span>

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

### <span data-ttu-id="835b9-148">-InputObject</span><span class="sxs-lookup"><span data-stu-id="835b9-148">-InputObject</span></span>

<span data-ttu-id="835b9-149">Especifica os objetos usados como entrada para o bloco de script.</span><span class="sxs-lookup"><span data-stu-id="835b9-149">Specifies the objects used as input to the script block.</span></span> <span data-ttu-id="835b9-150">Ele também permite a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="835b9-150">It also allows for pipeline input.</span></span> <span data-ttu-id="835b9-151">Use a `$input` variável automática no bloco de script para acessar os objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="835b9-151">Use the `$input` automatic variable in the script block to access the input objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="835b9-152">-Name</span><span class="sxs-lookup"><span data-stu-id="835b9-152">-Name</span></span>

<span data-ttu-id="835b9-153">Especifica um nome amigável para o novo trabalho.</span><span class="sxs-lookup"><span data-stu-id="835b9-153">Specifies a friendly name for the new job.</span></span> <span data-ttu-id="835b9-154">Você pode usar o nome para identificar o trabalho para outros cmdlets de trabalho, como o `Stop-Job` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="835b9-154">You can use the name to identify the job to other job cmdlets, such as the `Stop-Job` cmdlet.</span></span>

<span data-ttu-id="835b9-155">O nome amigável padrão é "Job #", em que "#" é um número ordinal que é incrementado para cada trabalho.</span><span class="sxs-lookup"><span data-stu-id="835b9-155">The default friendly name is "Job#", where "#" is an ordinal number that is incremented for each job.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="835b9-156">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="835b9-156">-ScriptBlock</span></span>

<span data-ttu-id="835b9-157">Especifica os comandos a executar no trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="835b9-157">Specifies the commands to run in the background job.</span></span> <span data-ttu-id="835b9-158">Coloque os comandos entre chaves ( `{}` ) para criar um bloco de script.</span><span class="sxs-lookup"><span data-stu-id="835b9-158">Enclose the commands in braces (`{}`) to create a script block.</span></span> <span data-ttu-id="835b9-159">Use a `$Input` variável automática para acessar o valor do parâmetro **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="835b9-159">Use the `$Input` automatic variable to access the value of the **InputObject** parameter.</span></span> <span data-ttu-id="835b9-160">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="835b9-160">This parameter is required.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="835b9-161">-StreamingHost</span><span class="sxs-lookup"><span data-stu-id="835b9-161">-StreamingHost</span></span>

<span data-ttu-id="835b9-162">Esse parâmetro fornece uma maneira segura de thread para permitir que a `Write-Host` saída vá diretamente para o objeto passado no **PSHost** .</span><span class="sxs-lookup"><span data-stu-id="835b9-162">This parameter provides a thread safe way to allow `Write-Host` output to go directly to the passed in **PSHost** object.</span></span> <span data-ttu-id="835b9-163">Sem ele, a `Write-Host` saída vai para a coleção de fluxo de dados de informações do trabalho e não aparece em um console de host até que os trabalhos terminem de ser executados.</span><span class="sxs-lookup"><span data-stu-id="835b9-163">Without it, `Write-Host` output goes to the job information data stream collection and doesn't appear in a host console until after the jobs finish running.</span></span>

```yaml
Type: System.Management.Automation.Host.PSHost
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="835b9-164">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="835b9-164">-ThrottleLimit</span></span>

<span data-ttu-id="835b9-165">Esse parâmetro limita o número de trabalhos em execução ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="835b9-165">This parameter limits the number of jobs running at one time.</span></span> <span data-ttu-id="835b9-166">À medida que os trabalhos são iniciados, eles são enfileirados e aguardam até que um thread esteja disponível no pool de threads para executar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="835b9-166">As jobs are started, they are queued and wait until a thread is available in the thread pool to run the job.</span></span> <span data-ttu-id="835b9-167">O limite padrão é 5 threads.</span><span class="sxs-lookup"><span data-stu-id="835b9-167">The default limit is 5 threads.</span></span>

<span data-ttu-id="835b9-168">O tamanho do pool de threads é global para a sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="835b9-168">The thread pool size is global to the PowerShell session.</span></span> <span data-ttu-id="835b9-169">A especificação de um **ThrottleLimit** em uma chamada define o limite para chamadas subsequentes na mesma sessão.</span><span class="sxs-lookup"><span data-stu-id="835b9-169">Specifying a **ThrottleLimit** in one call sets the limit for subsequent calls in the same session.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="835b9-170">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="835b9-170">CommonParameters</span></span>

<span data-ttu-id="835b9-171">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="835b9-171">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="835b9-172">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="835b9-172">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="835b9-173">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="835b9-173">INPUTS</span></span>

### <span data-ttu-id="835b9-174">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="835b9-174">System.Management.Automation.PSObject</span></span>

## <span data-ttu-id="835b9-175">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="835b9-175">OUTPUTS</span></span>

### <span data-ttu-id="835b9-176">ThreadJob.ThreadJob</span><span class="sxs-lookup"><span data-stu-id="835b9-176">ThreadJob.ThreadJob</span></span>

## <span data-ttu-id="835b9-177">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="835b9-177">NOTES</span></span>

## <span data-ttu-id="835b9-178">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="835b9-178">RELATED LINKS</span></span>

[<span data-ttu-id="835b9-179">Start-Job</span><span class="sxs-lookup"><span data-stu-id="835b9-179">Start-Job</span></span>](../Microsoft.PowerShell.Core/Start-Job.md)

[<span data-ttu-id="835b9-180">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="835b9-180">Stop-Job</span></span>](../Microsoft.PowerShell.Core/Stop-Job.md)

[<span data-ttu-id="835b9-181">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="835b9-181">Receive-Job</span></span>](../Microsoft.PowerShell.Core/Receive-Job.md)
