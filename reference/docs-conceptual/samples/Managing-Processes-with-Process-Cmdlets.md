---
ms.date: 06/05/2017
keywords: powershell, cmdlet
title: Gerenciando processos com os Cmdlets de processo
description: O PowerShell fornece vários cmdlets que ajudam a gerenciar processos em computadores locais e remotos.
ms.openlocfilehash: 977a3459eeac22536341753ccd59357d718745f2
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500429"
---
# <a name="managing-processes-with-process-cmdlets"></a><span data-ttu-id="f1291-104">Gerenciando processos com os Cmdlets de processo</span><span class="sxs-lookup"><span data-stu-id="f1291-104">Managing Processes with Process Cmdlets</span></span>

<span data-ttu-id="f1291-105">Você pode usar os cmdlets de processo do Windows PowerShell para gerenciar processos locais e remotos no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1291-105">You can use the Process cmdlets in Windows PowerShell to manage local and remote processes in Windows PowerShell.</span></span>

## <a name="getting-processes-get-process"></a><span data-ttu-id="f1291-106">Obtendo processos (Get-Process)</span><span class="sxs-lookup"><span data-stu-id="f1291-106">Getting Processes (Get-Process)</span></span>

<span data-ttu-id="f1291-107">Para obter os processos em execução no computador local, execute um **Get-Process** sem parâmetros.</span><span class="sxs-lookup"><span data-stu-id="f1291-107">To get the processes running on the local computer, run a **Get-Process** with no parameters.</span></span>

<span data-ttu-id="f1291-108">Você pode obter processos específicos definindo seus nomes de processo ou IDs de processo.</span><span class="sxs-lookup"><span data-stu-id="f1291-108">You can get particular processes by specifying their process names or process IDs.</span></span> <span data-ttu-id="f1291-109">O comando a seguir obtém o processo Idle:</span><span class="sxs-lookup"><span data-stu-id="f1291-109">The following command gets the Idle process:</span></span>

```
PS> Get-Process -id 0

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
      0       0        0         16     0               0 Idle
```

<span data-ttu-id="f1291-110">Embora seja normal os cmdlets não retornarem dados em algumas situações, quando você especificar um processo por seu ProcessId, **Get-Process** vai gerar um erro se ele não encontrar correspondências, pois o objetivo comum é recuperar um processo em execução conhecido.</span><span class="sxs-lookup"><span data-stu-id="f1291-110">Although it is normal for cmdlets to return no data in some situations, when you specify a process by its ProcessId, **Get-Process** generates an error if it finds no matches, because the usual intent is to retrieve a known running process.</span></span> <span data-ttu-id="f1291-111">Caso não haja nenhum processo com essa ID, é provável que a ID esteja incorreta ou que o processo do seu interesse já tenha terminado:</span><span class="sxs-lookup"><span data-stu-id="f1291-111">If there is no process with that Id, it is likely that the Id is incorrect or that the process of interest has already exited:</span></span>

```
PS> Get-Process -Id 99

Get-Process : No process with process ID 99 was found.
At line:1 char:12
+ Get-Process  <<<< -Id 99
```

<span data-ttu-id="f1291-112">Você pode usar o parâmetro Name do cmdlet Get-Process para especificar um subconjunto de processos com base no nome do processo.</span><span class="sxs-lookup"><span data-stu-id="f1291-112">You can use the Name parameter of the Get-Process cmdlet to specify a subset of processes based on the process name.</span></span> <span data-ttu-id="f1291-113">O parâmetro Name pode ter vários nomes em uma lista separada por vírgula e dá suporte ao uso de curingas para que você possa digitar padrões de nome.</span><span class="sxs-lookup"><span data-stu-id="f1291-113">The Name parameter can take multiple names in a comma-separated list and it supports the use of wildcards, so you can type name patterns.</span></span>

<span data-ttu-id="f1291-114">Por exemplo, o comando a seguir obtém o processo cujos nomes começam com "ex".</span><span class="sxs-lookup"><span data-stu-id="f1291-114">For example, the following command gets process whose names begin with "ex."</span></span>

```
PS> Get-Process -Name ex*

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    234       7     5572      12484   134     2.98   1684 EXCEL
    555      15    34500      12384   134   105.25    728 explorer
```

<span data-ttu-id="f1291-115">Como a classe .NET System.Diagnostics.Process é a base de processos do Windows PowerShell, ele segue algumas as convenções usadas pelo System.Diagnostics.Process.</span><span class="sxs-lookup"><span data-stu-id="f1291-115">Because the .NET System.Diagnostics.Process class is the foundation for Windows PowerShell processes, it follows some of the conventions used by System.Diagnostics.Process.</span></span> <span data-ttu-id="f1291-116">Uma dessas convenções é que o nome do processo para um executável nunca inclui ".exe" ao final do nome do executável.</span><span class="sxs-lookup"><span data-stu-id="f1291-116">One of those conventions is that the process name for an executable never includes the ".exe" at the end of the executable name.</span></span>

<span data-ttu-id="f1291-117">**Get-Process** também aceita vários valores para o parâmetro Name.</span><span class="sxs-lookup"><span data-stu-id="f1291-117">**Get-Process** also accepts multiple values for the Name parameter.</span></span>

```
PS> Get-Process -Name exp*,power*

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    540      15    35172      48148   141    88.44    408 explorer
    605       9    30668      29800   155     7.11   3052 powershell
```

<span data-ttu-id="f1291-118">Você pode usar o parâmetro ComputerName de Get-Process para obter os processos em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="f1291-118">You can use the ComputerName parameter of Get-Process to get processes on remote computers.</span></span> <span data-ttu-id="f1291-119">Por exemplo, o comando a seguir obtém os processos do PowerShell no computador local (representado por "localhost") e em dois computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="f1291-119">For example, the following command gets the PowerShell processes on the local computer (represented by "localhost") and on two remote computers.</span></span>

```
PS> Get-Process -Name PowerShell -ComputerName localhost, Server01, Server02

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    258       8    29772      38636   130            3700 powershell
    398      24    75988      76800   572            5816 powershell
    605       9    30668      29800   155     7.11   3052 powershell
```

<span data-ttu-id="f1291-120">Os nomes de computador não são evidentes nessa exibição, mas eles são armazenados na propriedade MachineName dos objetos de processo retornados por Get-Process.</span><span class="sxs-lookup"><span data-stu-id="f1291-120">The computer names are not evident in this display, but they are stored in the MachineName property of the process objects that Get-Process returns.</span></span> <span data-ttu-id="f1291-121">O comando a seguir usa o cmdlet Format-Table para exibir a ID do processo, as propriedades ProcessName e MachineName (ComputerName) dos objetos de processo.</span><span class="sxs-lookup"><span data-stu-id="f1291-121">The following command uses the Format-Table cmdlet to display the process ID, ProcessName and MachineName (ComputerName) properties of the process objects.</span></span>

```
PS> Get-Process -Name PowerShell -ComputerName localhost, Server01, Server01 |
  Format-Table -Property ID, ProcessName, MachineName

  Id ProcessName MachineName
  -- ----------- -----------
3700 powershell  Server01
3052 powershell  Server02
5816 powershell  localhost
```

<span data-ttu-id="f1291-122">Esse comando mais complexo adiciona a propriedade MachineName à exibição padrão de Get-Process.</span><span class="sxs-lookup"><span data-stu-id="f1291-122">This more complex command adds the MachineName property to the standard Get-Process display.</span></span>

```
PS> Get-Process powershell -ComputerName localhost, Server01, Server02 |
    Format-Table -Property Handles,
        @{Label="NPM(K)";Expression={[int]($_.NPM/1024)}},
        @{Label="PM(K)";Expression={[int]($_.PM/1024)}},
        @{Label="WS(K)";Expression={[int]($_.WS/1024)}},
        @{Label="VM(M)";Expression={[int]($_.VM/1MB)}},
        @{Label="CPU(s)";Expression={if ($_.CPU -ne $()){$_.CPU.ToString("N")}}},
        Id, ProcessName, MachineName -auto

Handles  NPM(K)  PM(K) WS(K) VM(M) CPU(s)  Id ProcessName  MachineName
-------  ------  ----- ----- ----- ------  -- -----------  -----------
    258       8  29772 38636   130         3700 powershell Server01
    398      24  75988 76800   572         5816 powershell localhost
    605       9  30668 29800   155 7.11    3052 powershell Server02
```

## <a name="stopping-processes-stop-process"></a><span data-ttu-id="f1291-123">Parando processos (Stop-Process)</span><span class="sxs-lookup"><span data-stu-id="f1291-123">Stopping Processes (Stop-Process)</span></span>

<span data-ttu-id="f1291-124">O Windows PowerShell oferece flexibilidade para listar processos, mas como podemos interromper um processo?</span><span class="sxs-lookup"><span data-stu-id="f1291-124">Windows PowerShell gives you flexibility for listing processes, but what about stopping a process?</span></span>

<span data-ttu-id="f1291-125">O cmdlet **Stop-Process** obtém um Name ou ID para especificar um processo que você deseja interromper.</span><span class="sxs-lookup"><span data-stu-id="f1291-125">The **Stop-Process** cmdlet takes a Name or Id to specify a process you want to stop.</span></span> <span data-ttu-id="f1291-126">A capacidade de parar os processos depende das suas permissões.</span><span class="sxs-lookup"><span data-stu-id="f1291-126">Your ability to stop processes depends on your permissions.</span></span> <span data-ttu-id="f1291-127">Alguns processos não podem ser interrompidos.</span><span class="sxs-lookup"><span data-stu-id="f1291-127">Some processes cannot be stopped.</span></span> <span data-ttu-id="f1291-128">Por exemplo, se você tentar interromper o processo ocioso, você receberá um erro:</span><span class="sxs-lookup"><span data-stu-id="f1291-128">For example, if you try to stop the idle process, you get an error:</span></span>

```
PS> Stop-Process -Name Idle
Stop-Process : Process 'Idle (0)' cannot be stopped due to the following error:
 Access is denied
At line:1 char:13
+ Stop-Process  <<<< -Name Idle
```

<span data-ttu-id="f1291-129">Você também pode forçar um prompt com o parâmetro **Confirm** .</span><span class="sxs-lookup"><span data-stu-id="f1291-129">You can also force prompting with the **Confirm** parameter.</span></span> <span data-ttu-id="f1291-130">Esse parâmetro será especialmente útil se você usar um caractere curinga ao especificar o nome do processo, pois você poderá corresponder acidentalmente alguns processos que não deseja interromper:</span><span class="sxs-lookup"><span data-stu-id="f1291-130">This parameter is particularly useful if you use a wildcard when specifying the process name, because you may accidentally match some processes you do not want to stop:</span></span>

```
PS> Stop-Process -Name t*,e* -Confirm
Confirm
Are you sure you want to perform this action?
Performing operation "Stop-Process" on Target "explorer (408)".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"):n
Confirm
Are you sure you want to perform this action?
Performing operation "Stop-Process" on Target "taskmgr (4072)".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"):n
```

<span data-ttu-id="f1291-131">A manipulação complexa de processos é possível usando alguns cmdlets de filtragem de objetos.</span><span class="sxs-lookup"><span data-stu-id="f1291-131">Complex process manipulation is possible by using some of the object filtering cmdlets.</span></span> <span data-ttu-id="f1291-132">Como um objeto Process tem uma propriedade Responding que é verdadeira quando ele não está respondendo, você pode interromper todos os aplicativos sem resposta com o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="f1291-132">Because a Process object has a Responding property that is true when it is no longer responding, you can stop all nonresponsive applications with the following command:</span></span>

```powershell
Get-Process | Where-Object -FilterScript {$_.Responding -eq $false} | Stop-Process
```

<span data-ttu-id="f1291-133">Você pode usar a mesma abordagem em outras situações.</span><span class="sxs-lookup"><span data-stu-id="f1291-133">You can use the same approach in other situations.</span></span> <span data-ttu-id="f1291-134">Por exemplo, suponha que um aplicativo de área de notificação secundário é executado automaticamente quando os usuários iniciam o outro aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f1291-134">For example, suppose a secondary notification area application automatically runs when users start another application.</span></span> <span data-ttu-id="f1291-135">Você pode achar que isso não funciona corretamente em sessões de Serviços de Terminal, mas você ainda deseja mantê-lo em sessões que são executadas no console do computador físico.</span><span class="sxs-lookup"><span data-stu-id="f1291-135">You may find that this does not work correctly in Terminal Services sessions, but you still want to keep it in sessions that run on the physical computer console.</span></span> <span data-ttu-id="f1291-136">Sessões conectadas à área de trabalho do computador físico sempre têm uma ID de sessão 0, portanto você pode parar todas as instâncias do processo que estão em outras sessões usando **Where-Object** e o processo, com **SessionId** :</span><span class="sxs-lookup"><span data-stu-id="f1291-136">Sessions connected to the physical computer desktop always have a session ID of 0, so you can stop all instances of the process that are in other sessions by using **Where-Object** and the process, **SessionId** :</span></span>

```powershell
Get-Process -Name BadApp | Where-Object -FilterScript {$_.SessionId -neq 0} | Stop-Process
```

<span data-ttu-id="f1291-137">O cmdlet Stop-Process não tem um parâmetro ComputerName.</span><span class="sxs-lookup"><span data-stu-id="f1291-137">The Stop-Process cmdlet does not have a ComputerName parameter.</span></span> <span data-ttu-id="f1291-138">Portanto, para executar um comando de parada do processo em um computador remoto, você precisa usar o cmdlet Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="f1291-138">Therefore, to run a stop process command on a remote computer, you need to use the Invoke-Command cmdlet.</span></span> <span data-ttu-id="f1291-139">Por exemplo, para parar o processo do PowerShell no computador remoto Server01, digite:</span><span class="sxs-lookup"><span data-stu-id="f1291-139">For example, to stop the PowerShell process on the Server01 remote computer, type:</span></span>

```powershell
Invoke-Command -ComputerName Server01 {Stop-Process Powershell}
```

## <a name="stopping-all-other-windows-powershell-sessions"></a><span data-ttu-id="f1291-140">Parar todas as outras sessões do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1291-140">Stopping All Other Windows PowerShell Sessions</span></span>

<span data-ttu-id="f1291-141">Ocasionalmente, pode ser útil poder parar a execução de todas as sessões do Windows PowerShell que não sejam a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="f1291-141">It may occasionally be useful to be able to stop all running Windows PowerShell sessions other than the current session.</span></span> <span data-ttu-id="f1291-142">Se uma sessão usar muitos recursos ou estiver inacessível (ela pode estar em execução remotamente ou em outra sessão de área de trabalho), poderá não ser possível pará-la diretamente.</span><span class="sxs-lookup"><span data-stu-id="f1291-142">If a session is using too many resources or is inaccessible (it may be running remotely or in another desktop session), you may not be able to directly stop it.</span></span> <span data-ttu-id="f1291-143">Se você tentar interromper todas as sessões, no entanto, a sessão atual talvez seja encerrada.</span><span class="sxs-lookup"><span data-stu-id="f1291-143">If you try to stop all running sessions, however, the current session may be terminated instead.</span></span>

<span data-ttu-id="f1291-144">Cada sessão do Windows PowerShell tem uma variável de ambiente PID que contém a ID do processo do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1291-144">Each Windows PowerShell session has an environment variable PID that contains the Id of the Windows PowerShell process.</span></span> <span data-ttu-id="f1291-145">Você pode verificar o $PID com a ID de cada sessão e encerrar somente sessões do Windows PowerShell que têm uma ID diferente. O comando de pipeline a seguir faz isso e retorna a lista de sessões finalizadas (devido ao uso do parâmetro **PassThru** ):</span><span class="sxs-lookup"><span data-stu-id="f1291-145">You can check the $PID against the Id of each session and terminate only Windows PowerShell sessions that have a different Id. The following pipeline command does this and returns the list of terminated sessions (because of the use of the **PassThru** parameter):</span></span>

```
PS> Get-Process -Name powershell | Where-Object -FilterScript {$_.Id -ne $PID} | Stop-Process -PassThru

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    334       9    23348      29136   143     1.03    388 powershell
    304       9    23152      29040   143     1.03    632 powershell
    302       9    20916      26804   143     1.03   1116 powershell
    335       9    25656      31412   143     1.09   3452 powershell
    303       9    23156      29044   143     1.05   3608 powershell
    287       9    21044      26928   143     1.02   3672 powershell
```

## <a name="starting-debugging-and-waiting-for-processes"></a><span data-ttu-id="f1291-146">Iniciando, depuração e aguardando a processos</span><span class="sxs-lookup"><span data-stu-id="f1291-146">Starting, Debugging, and Waiting for Processes</span></span>

<span data-ttu-id="f1291-147">O Windows PowerShell também inclui cmdlets para iniciar (ou reiniciar), depurar um processo e aguardar a conclusão de um processo antes de executar um comando.</span><span class="sxs-lookup"><span data-stu-id="f1291-147">Windows PowerShell also comes with cmdlets to start (or restart), debug a process, and wait for a process to complete before running a command.</span></span> <span data-ttu-id="f1291-148">Para obter informações sobre esses cmdlets, consulte o tópico de Ajuda do cmdlet para cada cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f1291-148">For information about these cmdlets, see the cmdlet help topic for each cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1291-149">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f1291-149">See Also</span></span>

- [<span data-ttu-id="f1291-150">Get-Process</span><span class="sxs-lookup"><span data-stu-id="f1291-150">Get-Process</span></span>](/powershell/module/Microsoft.PowerShell.Management/Get-Process)
- [<span data-ttu-id="f1291-151">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="f1291-151">Stop-Process</span></span>](/powershell/module/Microsoft.PowerShell.Management/Stop-Process)
- [<span data-ttu-id="f1291-152">Start-Process</span><span class="sxs-lookup"><span data-stu-id="f1291-152">Start-Process</span></span>](/powershell/module/Microsoft.PowerShell.Management/Start-Process)
- [<span data-ttu-id="f1291-153">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="f1291-153">Wait-Process</span></span>](/powershell/module/Microsoft.PowerShell.Management/Wait-Process)
- [<span data-ttu-id="f1291-154">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="f1291-154">Debug-Process</span></span>](/powershell/module/Microsoft.PowerShell.Management/Debug-Process)
- [<span data-ttu-id="f1291-155">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="f1291-155">Invoke-Command</span></span>](/powershell/module/Microsoft.PowerShell.Core/Invoke-Command)
