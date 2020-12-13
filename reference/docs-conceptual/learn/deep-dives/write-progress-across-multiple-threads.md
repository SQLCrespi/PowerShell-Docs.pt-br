---
title: Mostrar o progresso durante o multi-threading
description: Como usar Write-Progress em vários threads com Foreach-Object -Parallel
ms.date: 08/02/2020
ms.openlocfilehash: 909fc1bbdeded8845b1955e3384fb55db7173030
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "89410835"
---
# <a name="writing-progress-across-multiple-threads-with-foreach-parallel"></a><span data-ttu-id="83132-103">Writing Progress em vários threads com Foreach Parallel</span><span class="sxs-lookup"><span data-stu-id="83132-103">Writing Progress across multiple threads with Foreach Parallel</span></span>

<span data-ttu-id="83132-104">A partir do PowerShell 7.0, é possível trabalhar em vários threads simultaneamente usando o parâmetro **Parallel** no cmdlet [ForEach-Object](/powershell/module/Microsoft.PowerShell.Core/Foreach-Object).</span><span class="sxs-lookup"><span data-stu-id="83132-104">Starting in PowerShell 7.0, the ability to work in multiple threads simultaneously is possible using the **Parallel** parameter in the [Foreach-Object](/powershell/module/Microsoft.PowerShell.Core/Foreach-Object) cmdlet.</span></span> <span data-ttu-id="83132-105">No entanto, monitorar o progresso desses threads pode ser um desafio.</span><span class="sxs-lookup"><span data-stu-id="83132-105">Monitoring the progress of these threads can be a challenge though.</span></span> <span data-ttu-id="83132-106">Normalmente, você pode monitorar o progresso de um processo usando [Write-Progress](/powershell/module/Microsoft.PowerShell.Utility/Write-Progress).</span><span class="sxs-lookup"><span data-stu-id="83132-106">Normally, you can monitor the progress of a process using [Write-Progress](/powershell/module/Microsoft.PowerShell.Utility/Write-Progress).</span></span>
<span data-ttu-id="83132-107">No entanto, como o PowerShell usa um runspace separado para cada thread ao usar **Parallel**, enviar o progresso de volta ao host não é tão simples quanto o uso normal de `Write-Progress`.</span><span class="sxs-lookup"><span data-stu-id="83132-107">However, since PowerShell uses a separate runspace for each thread when using **Parallel**, reporting the progress back to the host isn't as straight forward as normal use of `Write-Progress`.</span></span>

## <a name="using-a-synced-hashtable-to-track-progress"></a><span data-ttu-id="83132-108">Usar uma tabela de hash sincronizada para acompanhar o progresso</span><span class="sxs-lookup"><span data-stu-id="83132-108">Using a synced hashtable to track progress</span></span>

<span data-ttu-id="83132-109">Ao gravar o progresso de vários threads, o controle torna-se difícil porque, ao executar processos paralelos no PowerShell, cada processo tem seu próprio runspace.</span><span class="sxs-lookup"><span data-stu-id="83132-109">When writing the progress from multiple threads, tracking becomes difficult because when running parallel processes in PowerShell, each process has it's own runspace.</span></span> <span data-ttu-id="83132-110">Para contornar isso, você pode usar uma [tabela de hash sincronizada](/dotnet/api/system.collections.hashtable.synchronized).</span><span class="sxs-lookup"><span data-stu-id="83132-110">To get around this, you can use a [synchronized hashtable](/dotnet/api/system.collections.hashtable.synchronized).</span></span> <span data-ttu-id="83132-111">Uma tabela de hash sincronizada é uma estrutura de dados thread-safe que pode ser modificada por vários threads simultaneamente, sem gerar um erro.</span><span class="sxs-lookup"><span data-stu-id="83132-111">A synced hashtable is a thread safe data structure that can be modified by multiple threads simultaneously without throwing an error.</span></span>

### <a name="set-up"></a><span data-ttu-id="83132-112">Configuração</span><span class="sxs-lookup"><span data-stu-id="83132-112">Set up</span></span>

<span data-ttu-id="83132-113">Uma das desvantagens dessa abordagem é a configuração complexa, de certa forma, para garantir que tudo seja executado sem erros.</span><span class="sxs-lookup"><span data-stu-id="83132-113">One of the downsides to this approach is it takes a, somewhat, complex set up to ensure everything runs without error.</span></span>

```powershell
$dataset = @(
    @{
        Id   = 1
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 2
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 3
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 4
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 5
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
)

# Create a hashtable for process.
# Keys should be ID's of the processes
$origin = @{}
$dataset | Foreach-Object {$origin.($_.id) = @{}}

# Create synced hashtable
$sync = [System.Collections.Hashtable]::Synchronized($origin)
```

<span data-ttu-id="83132-114">Esta seção cria três estruturas de dados diferentes, para três finalidades diferentes.</span><span class="sxs-lookup"><span data-stu-id="83132-114">This section creates three different data structures, for three different purposes.</span></span>

<span data-ttu-id="83132-115">A variável `$dataSet` armazena uma matriz de tabelas de hash usada para coordenar as próximas etapas sem o risco de modificação.</span><span class="sxs-lookup"><span data-stu-id="83132-115">The `$dataSet` variable stores an array of hashtables that is used to coordinate the next steps without the risk of being modified.</span></span> <span data-ttu-id="83132-116">Se uma coleção de objetos for modificada durante a iteração pela coleção, o PowerShell vai gerar um erro.</span><span class="sxs-lookup"><span data-stu-id="83132-116">If an object collection is modified while iterating through the collection, PowerShell throws an error.</span></span> <span data-ttu-id="83132-117">Você deve manter a coleção de objetos no loop, separada dos objetos que estão sendo modificados.</span><span class="sxs-lookup"><span data-stu-id="83132-117">You must keep the object collection in the loop separate from the objects being modified.</span></span> <span data-ttu-id="83132-118">A chave `Id` em cada tabela de hash é o identificador de um processo de simulação.</span><span class="sxs-lookup"><span data-stu-id="83132-118">The `Id` key in each hashtable is the identifier for a mock process.</span></span> <span data-ttu-id="83132-119">A chave `Wait` simula a carga de trabalho de cada processo de simulação que está sendo rastreado.</span><span class="sxs-lookup"><span data-stu-id="83132-119">The `Wait` key simulates the workload of each mock process being tracked.</span></span>

<span data-ttu-id="83132-120">A variável `$origin` armazena uma tabela de hash aninhada com cada chave sendo uma das IDs do processo de simulação.</span><span class="sxs-lookup"><span data-stu-id="83132-120">The `$origin` variable stores a nested hashtable with each key being one of the mock process id's.</span></span>
<span data-ttu-id="83132-121">Em seguida, ela é usada para hidratar a tabela de hash sincronizada armazenada na variável `$sync`.</span><span class="sxs-lookup"><span data-stu-id="83132-121">Then, it is used to hydrate the synchronized hashtable stored in the `$sync` variable.</span></span> <span data-ttu-id="83132-122">A variável `$sync` é responsável por relatar o progresso para o runspace pai, que exibe o progresso.</span><span class="sxs-lookup"><span data-stu-id="83132-122">The `$sync` variable is responsible for reporting the progress back to the parent runspace, which displays the progress.</span></span>

### <a name="running-the-processes"></a><span data-ttu-id="83132-123">Executar os processos</span><span class="sxs-lookup"><span data-stu-id="83132-123">Running the processes</span></span>

<span data-ttu-id="83132-124">Esta seção executa os processos de várias threads e cria algumas das saídas usadas para exibir o progresso.</span><span class="sxs-lookup"><span data-stu-id="83132-124">This section runs the multi-threaded processes and creates some of the output used to display progress.</span></span>

```powershell
$job = $dataset | Foreach-Object -ThrottleLimit 3 -AsJob -Parallel {
    $syncCopy = $using:sync
    $process = $syncCopy.$($PSItem.Id)

    $process.Id = $PSItem.Id
    $process.Activity = "Id $($PSItem.Id) starting"
    $process.Status = "Processing"

    # Fake workload start up that takes x amount of time to complete
    start-sleep -Milliseconds ($PSItem.wait*5)

    # Process. update activity
    $process.Activity = "Id $($PSItem.id) processing"
    foreach ($percent in 1..100)
    {
        # Update process on status
        $process.Status = "Handling $percent/100"
        $process.PercentComplete = (($percent / 100) * 100)

        # Fake workload that takes x amount of time to complete
        Start-Sleep -Milliseconds $PSItem.Wait
    }

    # Mark process as completed
    $process.Completed = $true
}
```

<span data-ttu-id="83132-125">Os processos de simulação são enviados para `Foreach-Object` e iniciados como trabalhos.</span><span class="sxs-lookup"><span data-stu-id="83132-125">The mock processes are sent to `Foreach-Object` and started as jobs.</span></span> <span data-ttu-id="83132-126">O **ThrottleLimit** é definido como **3** para realçar a execução de vários processos em uma fila.</span><span class="sxs-lookup"><span data-stu-id="83132-126">The **ThrottleLimit** is set to **3** to highlight running multiple processes in a queue.</span></span> <span data-ttu-id="83132-127">Os trabalhos são armazenados na variável `$job` e nos permitem saber quando todos os processos foram concluídos posteriormente.</span><span class="sxs-lookup"><span data-stu-id="83132-127">The jobs are stored in the `$job` variable and allows us to know when all the processes have finished later on.</span></span>

<span data-ttu-id="83132-128">Ao usar a instrução `using:` para fazer referência a uma variável de escopo pai no PowerShell, você não pode usar expressões para torná-la dinâmica.</span><span class="sxs-lookup"><span data-stu-id="83132-128">When using the `using:` statement to reference a parent scope variable in PowerShell, you can't use expressions to make it dynamic.</span></span> <span data-ttu-id="83132-129">Por exemplo, se você tentou criar a variável `$process` como essa, `$process = $using:sync.$($PSItem.id)`, você receberia um erro informando que não pode usar expressões ali.</span><span class="sxs-lookup"><span data-stu-id="83132-129">For example, if you tried to create the `$process` variable like this, `$process = $using:sync.$($PSItem.id)`, you would get an error stating you can't use expressions there.</span></span> <span data-ttu-id="83132-130">Portanto, criamos a variável `$syncCopy` para referenciar e modificar a variável `$sync` sem o risco de falhar.</span><span class="sxs-lookup"><span data-stu-id="83132-130">So, we create the `$syncCopy` variable to be able to reference and modify the `$sync` variable without the risk of it failing.</span></span>

<span data-ttu-id="83132-131">Em seguida, criamos uma tabela de hash para representar o progresso do processo atualmente no loop usando a variável `$process` referenciando as chaves de tabela de hash sincronizadas.</span><span class="sxs-lookup"><span data-stu-id="83132-131">Next, we build out a hashtable to represent the progress of the process currently in the loop using the `$process` variable by referencing the synchronized hashtable keys.</span></span> <span data-ttu-id="83132-132">As chaves **Activity** e **Status** são usadas como valores de parâmetro para `Write-Progress` exibir o status de um processo de simulação específico na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="83132-132">The **Activity** and the **Status** keys are used as parameter values for `Write-Progress` to display the status of a given mock process in the next section.</span></span>

<span data-ttu-id="83132-133">O loop `foreach` é apenas uma forma de simular o funcionamento do processo e é aleatório com base no atributo `$dataSet` **Wait** para definir `Start-Sleep` usando milissegundos.</span><span class="sxs-lookup"><span data-stu-id="83132-133">The `foreach` loop is just a way to simulate the process working and is randomized based on the `$dataSet` **Wait** attribute to set `Start-Sleep` using milliseconds.</span></span> <span data-ttu-id="83132-134">A forma como você calcula o progresso do processo pode variar.</span><span class="sxs-lookup"><span data-stu-id="83132-134">How you calculate the progress of your process may vary.</span></span>

### <a name="displaying-the-progress-of-multiple-processes"></a><span data-ttu-id="83132-135">Exibir o progresso de vários processos</span><span class="sxs-lookup"><span data-stu-id="83132-135">Displaying the progress of multiple processes</span></span>

<span data-ttu-id="83132-136">Agora que os processos de simulação estão sendo executados como trabalhos, podemos começar a gravar o progresso dos processos na janela do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="83132-136">Now that the mock processes are running as jobs, we can start to write the processes progress to the PowerShell window.</span></span>

```powershell
while($job.State -eq 'Running')
{
    $sync.Keys | Foreach-Object {
        # If key is not defined, ignore
        if(![string]::IsNullOrEmpty($sync.$_.keys))
        {
            # Create parameter hashtable to splat
            $param = $sync.$_

            # Execute Write-Progress
            Write-Progress @param
        }
    }

    # Wait to refresh to not overload gui
    Start-Sleep -Seconds 0.1
}
```

<span data-ttu-id="83132-137">A variável `$job` contém o trabalho **pai** e tem um trabalho **filho** para cada um dos processos de simulação.</span><span class="sxs-lookup"><span data-stu-id="83132-137">The `$job` variable contains the parent **job** and has a child **job** for each of the mock processes.</span></span> <span data-ttu-id="83132-138">Embora qualquer um dos trabalhos filho ainda esteja em execução, o trabalho pai **State** permanecerá "Em execução".</span><span class="sxs-lookup"><span data-stu-id="83132-138">While any of the child jobs are still running, the parent job **State** will remain "Running".</span></span> <span data-ttu-id="83132-139">Isso permite usar o loop `while` para atualizar continuamente o progresso de cada processo até que todos sejam concluídos.</span><span class="sxs-lookup"><span data-stu-id="83132-139">This allows us to use the `while` loop to continually update the progress of every process until all processes are finished.</span></span>

<span data-ttu-id="83132-140">Dentro do loop while, fazemos um loop em cada uma das chaves na variável `$sync`.</span><span class="sxs-lookup"><span data-stu-id="83132-140">Within the while loop, we loop through each of the keys in the `$sync` variable.</span></span> <span data-ttu-id="83132-141">Como essa é uma tabela de hash sincronizada, ela é constantemente atualizada, mas ainda pode ser acessada sem gerar erros.</span><span class="sxs-lookup"><span data-stu-id="83132-141">Since this is a synchronized hashtable, it is constantly updated but can still be accessed without throwing any errors.</span></span>

<span data-ttu-id="83132-142">Há uma verificação para garantir que o processo relatado esteja realmente em execução com o método `IsNullOrEmpty()`.</span><span class="sxs-lookup"><span data-stu-id="83132-142">There is a check to ensure that the process being reported is actually running using the `IsNullOrEmpty()` method.</span></span> <span data-ttu-id="83132-143">Se o processo não tiver sido iniciado, o loop não o relatará e passará para o próximo até chegar a um processo que foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="83132-143">If the process hasn't been started, the loop won't report on it and move on to the next until it gets to a process that has been started.</span></span> <span data-ttu-id="83132-144">Se o processo for iniciado, a tabela de hash da chave atual será usada para fragmentar os parâmetros para `Write-Progress`.</span><span class="sxs-lookup"><span data-stu-id="83132-144">If the process is started, the hashtable from the current key is used to splat the parameters to `Write-Progress`.</span></span>

### <a name="full-example"></a><span data-ttu-id="83132-145">Exemplo completo</span><span class="sxs-lookup"><span data-stu-id="83132-145">Full example</span></span>

```powershell
# Example workload
$dataset = @(
    @{
        Id   = 1
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 2
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 3
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 4
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 5
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
)

# Create a hashtable for process.
# Keys should be ID's of the processes
$origin = @{}
$dataset | Foreach-Object {$origin.($_.id) = @{}}

# Create synced hashtable
$sync = [System.Collections.Hashtable]::Synchronized($origin)

$job = $dataset | Foreach-Object -ThrottleLimit 3 -AsJob -Parallel {
    $syncCopy = $using:sync
    $process = $syncCopy.$($PSItem.Id)

    $process.Id = $PSItem.Id
    $process.Activity = "Id $($PSItem.Id) starting"
    $process.Status = "Processing"

    # Fake workload start up that takes x amount of time to complete
    start-sleep -Milliseconds ($PSItem.wait*5)

    # Process. update activity
    $process.Activity = "Id $($PSItem.id) processing"
    foreach ($percent in 1..100)
    {
        # Update process on status
        $process.Status = "Handling $percent/100"
        $process.PercentComplete = (($percent / 100) * 100)

        # Fake workload that takes x amount of time to complete
        Start-Sleep -Milliseconds $PSItem.Wait
    }

    # Mark process as completed
    $process.Completed = $true
}

while($job.State -eq 'Running')
{
    $sync.Keys | Foreach-Object {
        # If key is not defined, ignore
        if(![string]::IsNullOrEmpty($sync.$_.keys))
        {
            # Create parameter hashtable to splat
            $param = $sync.$_

            # Execute Write-Progress
            Write-Progress @param
        }
    }

    # Wait to refresh to not overload gui
    Start-Sleep -Seconds 0.1
}
```

## <a name="related-links"></a><span data-ttu-id="83132-146">Links Relacionados</span><span class="sxs-lookup"><span data-stu-id="83132-146">Related Links</span></span>

- [<span data-ttu-id="83132-147">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="83132-147">about_Jobs</span></span>](/powershell/module/Microsoft.PowerShell.Core/About/about_Jobs)
- [<span data-ttu-id="83132-148">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="83132-148">about_Scopes</span></span>](/powershell/module/Microsoft.PowerShell.Core/About/about_Scopes)
- [<span data-ttu-id="83132-149">about_Splatting</span><span class="sxs-lookup"><span data-stu-id="83132-149">about_Splatting</span></span>](/powershell/module/Microsoft.PowerShell.Core/About/about_Splatting)
