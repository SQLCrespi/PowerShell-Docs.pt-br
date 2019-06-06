---
ms.date: 11/13/2018
keywords: powershell, cmdlet
title: Decodificar um comando do PowerShell por meio de um processo em execução
author: randomnote1
ms.openlocfilehash: a6c01d8edf67aba6c47350a97cc0ceec4801ad29
ms.sourcegitcommit: bc42c9166857147a1ecf9924b718d4a48eb901e3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2019
ms.locfileid: "66470972"
---
# <a name="decode-a-powershell-command-from-a-running-process"></a><span data-ttu-id="2692f-103">Decodificar um comando do PowerShell por meio de um processo em execução</span><span class="sxs-lookup"><span data-stu-id="2692f-103">Decode a PowerShell command from a running process</span></span>

<span data-ttu-id="2692f-104">Às vezes você pode ter um processo em execução que ocupa uma grande quantidade de recursos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2692f-104">At times, you may have a PowerShell process running that is taking up a large amount of resources.</span></span>
<span data-ttu-id="2692f-105">Esse processo pode ser executado no contexto de um trabalho do [Agendador de Tarefas][] ou do [SQL Server Agent][].</span><span class="sxs-lookup"><span data-stu-id="2692f-105">This process could be running in the context of a [Task Scheduler][] job or a [SQL Server Agent][] job.</span></span> <span data-ttu-id="2692f-106">Pode ser difícil descobrir qual processo representa o problema se houver vários processos do PowerShell em execução.</span><span class="sxs-lookup"><span data-stu-id="2692f-106">Where there are multiple PowerShell processes running, it can be difficult to know which process represents the problem.</span></span> <span data-ttu-id="2692f-107">Este artigo mostra como decodificar um bloco de script que um processo do PowerShell está executando no momento.</span><span class="sxs-lookup"><span data-stu-id="2692f-107">This article shows how to decode a script block that a PowerShell process is currently running.</span></span>

## <a name="create-a-long-running-process"></a><span data-ttu-id="2692f-108">Criar um processo de execução prolongada</span><span class="sxs-lookup"><span data-stu-id="2692f-108">Create a long running process</span></span>

<span data-ttu-id="2692f-109">Para demonstrar esse cenário, abra uma nova janela do PowerShell e execute o código a seguir.</span><span class="sxs-lookup"><span data-stu-id="2692f-109">To demonstrate this scenario, open a new PowerShell window and run the following code.</span></span> <span data-ttu-id="2692f-110">Ele executa um comando do PowerShell que gera um número a cada minuto por 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="2692f-110">It executes a PowerShell command that outputs a number every minute for 10 minutes.</span></span>

```powershell
powershell.exe -Command {
    $i = 1
    while ( $i -le 10 )
    {
        Write-Output -InputObject $i
        Start-Sleep -Seconds 60
        $i++
    }
}
```

## <a name="view-the-process"></a><span data-ttu-id="2692f-111">Exibir o processo</span><span class="sxs-lookup"><span data-stu-id="2692f-111">View the process</span></span>

<span data-ttu-id="2692f-112">O corpo do comando que o PowerShell está executando é armazenado na propriedade **CommandLine** da classe [Win32_Process][].</span><span class="sxs-lookup"><span data-stu-id="2692f-112">The body of the command which PowerShell is executing is stored in the **CommandLine** property of the [Win32_Process][] class.</span></span> <span data-ttu-id="2692f-113">Se o comando for um comando codificado, a propriedade **CommandLine** conterá a cadeia de caracteres "EncodedCommand".</span><span class="sxs-lookup"><span data-stu-id="2692f-113">If the command is an encoded command, the **CommandLine** property contains the string "EncodedCommand".</span></span> <span data-ttu-id="2692f-114">Usando essas informações, o comando codificado pode ser revelado por meio do processo a seguir.</span><span class="sxs-lookup"><span data-stu-id="2692f-114">Using this information, the encoded command can be de-obfuscated via the following process.</span></span>

<span data-ttu-id="2692f-115">Inicie o PowerShell como Administrador.</span><span class="sxs-lookup"><span data-stu-id="2692f-115">Start PowerShell as Administrator.</span></span> <span data-ttu-id="2692f-116">É essencial que o PowerShell esteja em execução como administrador, caso contrário, nenhum resultado será retornado ao consultar os processos em execução.</span><span class="sxs-lookup"><span data-stu-id="2692f-116">It is vital that PowerShell is running as administrator, otherwise no results are returned when querying the running processes.</span></span>

<span data-ttu-id="2692f-117">Execute o comando a seguir para obter todos os processos do PowerShell que têm um comando codificado:</span><span class="sxs-lookup"><span data-stu-id="2692f-117">Execute the following command to get all of the PowerShell processes that have an encoded command:</span></span>

```powershell
$powerShellProcesses = Get-CimInstance -ClassName Win32_Process -Filter 'CommandLine LIKE "%EncodedCommand%"'
```

<span data-ttu-id="2692f-118">O comando a seguir cria um objeto personalizado do PowerShell que contém a ID de processo e o comando codificado.</span><span class="sxs-lookup"><span data-stu-id="2692f-118">The following command creates a custom PowerShell object that contains the process ID and the encoded command.</span></span>

```powershell
$commandDetails = $powerShellProcesses | Select-Object -Property ProcessId,
@{
    name       = 'EncodedCommand'
    expression = {
        if ( $_.CommandLine -match 'encodedCommand (.*) -inputFormat' )
        {
            return $matches[1]
        }
    }
}
```

<span data-ttu-id="2692f-119">Agora o comando codificado pode ser decodificado.</span><span class="sxs-lookup"><span data-stu-id="2692f-119">Now the encoded command can be decoded.</span></span> <span data-ttu-id="2692f-120">O snippet a seguir efetua iterações sobre o objeto de detalhes do comando, decodifica o comando codificado e adiciona o comando decodificado de volta ao objeto para uma investigação adicional.</span><span class="sxs-lookup"><span data-stu-id="2692f-120">The following snippet iterates over the command details object, decodes the encoded command, and adds the decoded command back to the object for further investigation.</span></span>

```powershell
$commandDetails | ForEach-Object -Process {
    # Get the current process
    $currentProcess = $_

    # Convert the Base 64 string to a Byte Array
    $commandBytes = [System.Convert]::FromBase64String($currentProcess.EncodedCommand)

    # Convert the Byte Array to a string
    $decodedCommand = [System.Text.Encoding]::Unicode.GetString($commandBytes)

    # Add the decoded command back to the object
    $commandDetails |
        Where-Object -FilterScript { $_.ProcessId -eq $_.ProcessId } |
        Add-Member -MemberType NoteProperty -Name DecodedCommand -Value $decodedCommand
}
$commandDetails[0]
```

<span data-ttu-id="2692f-121">Agora o comando decodificado pode ser analisado selecionando a propriedade do comando decodificado.</span><span class="sxs-lookup"><span data-stu-id="2692f-121">The decoded command can now be reviewed by selecting the decoded command property.</span></span>

```output
ProcessId      : 8752
EncodedCommand : IAAKAAoACgAgAAoAIAAgACAAIAAkAGkAIAA9ACAAMQAgAAoACgAKACAACgAgACAAIAAgAHcAaABpAGwAZQAgACgAIAAkAGkAIAAtAG
                 wAZQAgADEAMAAgACkAIAAKAAoACgAgAAoAIAAgACAAIAB7ACAACgAKAAoAIAAKACAAIAAgACAAIAAgACAAIABXAHIAaQB0AGUALQBP
                 AHUAdABwAHUAdAAgAC0ASQBuAHAAdQB0AE8AYgBqAGUAYwB0ACAAJABpACAACgAKAAoAIAAKACAAIAAgACAAIAAgACAAIABTAHQAYQ
                 ByAHQALQBTAGwAZQBlAHAAIAAtAFMAZQBjAG8AbgBkAHMAIAA2ADAAIAAKAAoACgAgAAoAIAAgACAAIAAgACAAIAAgACQAaQArACsA
                 IAAKAAoACgAgAAoAIAAgACAAIAB9ACAACgAKAAoAIAAKAA==
DecodedCommand :
                     $i = 1

                     while ( $i -le 10 )

                     {

                         Write-Output -InputObject $i

                         Start-Sleep -Seconds 60

                         $i++

                     }
```

[Agendador de Tarefas]: /windows/desktop/TaskSchd/task-scheduler-start-page
[Task Scheduler]: /windows/desktop/TaskSchd/task-scheduler-start-page
[SQL Server Agent]: /sql/ssms/agent/sql-server-agent
[Win32_Process]: /windows/desktop/CIMWin32Prov/win32-process
