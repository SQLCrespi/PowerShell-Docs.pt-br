---
ms.date: 11/13/2018
keywords: powershell, cmdlet
title: Decodificar um comando do PowerShell por meio de um processo em execução
author: randomnote1
ms.openlocfilehash: a6c01d8edf67aba6c47350a97cc0ceec4801ad29
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "66470972"
---
# <a name="decode-a-powershell-command-from-a-running-process"></a>Decodificar um comando do PowerShell por meio de um processo em execução

Às vezes você pode ter um processo em execução que ocupa uma grande quantidade de recursos do PowerShell.
Esse processo pode ser executado no contexto de um trabalho do [Agendador de Tarefas][] ou do [SQL Server Agent][]. Pode ser difícil descobrir qual processo representa o problema se houver vários processos do PowerShell em execução. Este artigo mostra como decodificar um bloco de script que um processo do PowerShell está executando no momento.

## <a name="create-a-long-running-process"></a>Criar um processo de execução prolongada

Para demonstrar esse cenário, abra uma nova janela do PowerShell e execute o código a seguir. Ele executa um comando do PowerShell que gera um número a cada minuto por 10 minutos.

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

## <a name="view-the-process"></a>Exibir o processo

O corpo do comando que o PowerShell está executando é armazenado na propriedade **CommandLine** da classe [Win32_Process][]. Se o comando for um comando codificado, a propriedade **CommandLine** conterá a cadeia de caracteres "EncodedCommand". Usando essas informações, o comando codificado pode ser revelado por meio do processo a seguir.

Inicie o PowerShell como Administrador. É essencial que o PowerShell esteja em execução como administrador, caso contrário, nenhum resultado será retornado ao consultar os processos em execução.

Execute o comando a seguir para obter todos os processos do PowerShell que têm um comando codificado:

```powershell
$powerShellProcesses = Get-CimInstance -ClassName Win32_Process -Filter 'CommandLine LIKE "%EncodedCommand%"'
```

O comando a seguir cria um objeto personalizado do PowerShell que contém a ID de processo e o comando codificado.

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

Agora o comando codificado pode ser decodificado. O snippet a seguir efetua iterações sobre o objeto de detalhes do comando, decodifica o comando codificado e adiciona o comando decodificado de volta ao objeto para uma investigação adicional.

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

Agora o comando decodificado pode ser analisado selecionando a propriedade do comando decodificado.

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
[SQL Server Agent]: /sql/ssms/agent/sql-server-agent
[Win32_Process]: /windows/desktop/CIMWin32Prov/win32-process
