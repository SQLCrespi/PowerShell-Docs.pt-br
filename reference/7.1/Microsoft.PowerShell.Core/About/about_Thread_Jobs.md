---
description: Fornece informações sobre os trabalhos baseados em thread do PowerShell. Um trabalho de thread é um tipo de trabalho em segundo plano que executa um comando ou expressão em um thread separado dentro do processo de sessão atual.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/16/2020
online version: 1.0.0
schema: 2.0.0
title: about_Thread_Jobs
ms.openlocfilehash: d3f7c2754a2e54bc1b6f9fb95d1cf6ce2fed5b9b
ms.sourcegitcommit: 108686b166672cc08817c637dd93eb1ad830511d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "93196482"
---
# <a name="about-thread-jobs"></a>Sobre os trabalhos de thread

## <a name="short-description"></a>Descrição breve

Fornece informações sobre os trabalhos baseados em thread do PowerShell. Um trabalho de thread é um tipo de trabalho em segundo plano que executa um comando ou expressão em um thread separado dentro do processo de sessão atual.

## <a name="long-description"></a>Descrição longa

Este artigo explica como executar trabalhos de thread no PowerShell em um computador local.
Para obter informações sobre como executar trabalhos em segundo plano em um computador local, consulte [about_Jobs](about_Jobs.md).

Você pode iniciar um trabalho de thread de uma das duas maneiras.

A primeira maneira é com o `Start-ThreadJob` cmdlet. Esse cmdlet está disponível no módulo **ThreadJob** que acompanha o PowerShell. `Start-ThreadJob` Retorna um único objeto de trabalho que encapsula o comando ou script em execução e pode ser usado com todos os cmdlets de manipulação de trabalho do PowerShell.

A segunda maneira é com o `ForEach-Object` cmdlet, com o `-Parallel` argumento de bloco de script de parâmetro junto com a `-AsJob` opção de parâmetro. Esse cmdlet retorna um único objeto de trabalho (pai) que contém um trabalho filho para cada entrada canalizada para o cmdlet. Cada trabalho filho executa o script em um thread separado com um `-ThrottleLimit` limite () para o número de trabalhos filho executados em um determinado momento.

## <a name="the-job-cmdlets"></a>OS CMDLETS DE TRABALHO

|Cmdlet           |Descrição                                            |
|-----------------|-------------------------------------------------------|
|`Start-ThreadJob`|Inicia um trabalho de thread em um computador local.               |
|`ForEach-Object` |Inicia trabalhos de thread para cada objeto de entrada canalizado, quando   |
|                 |usado com parâmetros-Parallel e-AsJob.             |
|`Get-Job`        |Obtém os trabalhos que foram iniciados na sessão atual.|
|`Receive-Job`    |Obtém os resultados dos trabalhos.                              |
|`Stop-Job`       |Interrompe um trabalho em execução.                                   |
|`Wait-Job`       |Suprime o prompt de comando até que um ou todos os trabalhos sejam|
|                 |concluí.                                              |
|`Remove-Job`     |Exclui um trabalho.                                         |

## <a name="how-to-start-a-thread-job-on-the-local-computer"></a>Como iniciar um trabalho de thread no computador local

Para iniciar um trabalho de thread no computador local, use o `Start-ThreadJob` cmdlet.

Para gravar um `Start-ThreadJob` comando, coloque o comando ou o script que o trabalho executa entre chaves ( `{ }` ).

O comando a seguir inicia um trabalho de thread que executa um `Get-Process` comando no computador local.

```powershell
Start-ThreadJob -ScriptBlock { Get-Process }
```

O `Start-ThreadJob` comando retorna um `ThreadJob` objeto que representa o trabalho em execução. O objeto de trabalho contém informações úteis sobre o trabalho, incluindo seu status de execução atual. Ele coleta os resultados do trabalho à medida que os resultados são gerados.

Para gravar um `ForEach-Object -Parallel` comando, redirecione os dados para o comando e coloque o comando ou o script que o trabalho executa entre chaves ( `{}` ). Use a `-AsJob` opção de parâmetro para que um objeto de trabalho seja retornado.

O comando a seguir inicia um trabalho que contém trabalhos filho para cada valor de entrada canalizado para o comando. Cada trabalho filho executa o `Write-Output` comando com um valor de entrada canalizado como o argumento.

```powershell
1..5 | ForEach-Object -Parallel { Write-Output $_ } -AsJob
```

O `ForEach-Object -Parallel` comando retorna um `PSTaskJob` objeto que contém trabalhos filho para cada valor de entrada canalizado. O objeto de trabalho contém informações úteis sobre o status de execução de trabalhos filho. Ele coleta os resultados dos trabalhos filho à medida que os resultados são gerados.

## <a name="how-to-wait-for-a-job-to-complete-and-retrieve-job-results"></a>Como aguardar a conclusão de um trabalho e recuperar os resultados do trabalho

Você pode usar os cmdlets de trabalho do PowerShell, como `Wait-Job` e `Receive-Job` para aguardar a conclusão de um trabalho e, em seguida, retornar todos os resultados gerados pelo trabalho.

O comando a seguir inicia um trabalho de thread que executa um `Get-Process` comando, aguarda até que o comando seja concluído e, finalmente, retorna todos os resultados de dados gerados pelo comando.

```powershell
Start-ThreadJob -ScriptBlock { Get-Process } | Wait-Job | Receive-Job
```

O comando a seguir inicia um trabalho que executa um `Write-Output` comando para cada entrada canalizada, aguarda que todos os trabalhos filho sejam concluídos e, finalmente, retorna todos os resultados de dados gerados pelos trabalhos filho.

```powershell
1..5 | ForEach-Object -Parallel { Write-Output $_ } -AsJob | Wait-Job | Receive-Job
```

O `Receive-Job` cmdlet retorna os resultados dos trabalhos filho.

```powershell
1
3
2
4
5
```

Como cada trabalho filho é executado em paralelo, a ordem dos resultados gerados não é garantida.

## <a name="powershell-concurrency-and-jobs"></a>Simultaneidade e trabalhos do PowerShell

O PowerShell executa comandos e scripts simultaneamente por meio de trabalhos. Há três soluções baseadas em trabalhos fornecidas pelo PowerShell para dar suporte à simultaneidade.

|Trabalho            |Descrição                                                  |
|---------------|-------------------------------------------------------------|
|`RemoteJob`    |O comando e o script são executados em um computador remoto.                 |
|`BackgroundJob`|O comando e o script são executados em um processo separado no local    |
|               |Tradução.                                                     |
|`ThreadJob`    |O comando e o script são executados em um thread separado dentro do mesmo  |
|               |processo no computador local.                                |

Cada tipo de trabalho tem benefícios e desvantagens. Executar o script remotamente em um computador separado ou em um processo separado tem grande isolamento. Quaisquer erros não afetarão outros trabalhos em execução ou o cliente que iniciou o trabalho. Mas a camada de comunicação remota adiciona sobrecarga, incluindo a serialização de objeto. Todos os objetos passados para e da sessão remota devem ser serializados e, em seguida, desserializados conforme passam entre o cliente e a sessão de destino. A operação de serialização pode usar muitos recursos de computação e memória para grandes objetos de dados complexos.

## <a name="powershell-thread-based-jobs"></a>Trabalhos baseados em thread do PowerShell

Os trabalhos baseados em thread não são tão robustos quanto os trabalhos remotos e em segundo plano, pois eles são executados no mesmo processo em threads diferentes. Se um trabalho tiver um erro crítico que falha no processo, todos os outros trabalhos no processo também falharão.

No entanto, os trabalhos baseados em thread têm muito menos sobrecarga. Eles não precisam usar a camada ou a serialização de comunicação remota. O resultado é que os trabalhos baseados em thread tendem a ser executados muito mais rapidamente e usam muito menos recursos do que os outros tipos de trabalho.

## <a name="thread-job-performance"></a>Desempenho do trabalho de thread

Os trabalhos de thread são mais rápidos e mais leves do que outros tipos de trabalhos. Mas ainda têm sobrecarga que pode ser grande quando comparada ao trabalho que o trabalho está fazendo.

O PowerShell executa comandos e script em uma sessão. Somente um comando ou script pode ser executado por vez em uma sessão. Assim, ao executar vários trabalhos, cada trabalho é executado em uma sessão separada. Cada sessão contribui para a sobrecarga.

Os trabalhos de thread fornecem o melhor desempenho quando o trabalho executado é maior do que a sobrecarga da sessão usada para executar o trabalho. Há dois casos para atender a esses critérios.

- O trabalho é de computação intensiva – executar um script em vários trabalhos de thread pode tirar proveito de vários núcleos de processador e ser concluído com mais rapidez.

- O trabalho consiste em uma espera significativa – um script que passa tempo aguardando os resultados de e/s ou de chamada remota. A execução em paralelo geralmente é concluída mais rapidamente do que se executado em sequência.

```powershell
(Measure-Command {
    1..1000 | ForEach { Start-ThreadJob { Write-Output "Hello $using:_" } } | Receive-Job -Wait
}).TotalMilliseconds
10457.962


(Measure-Command {
    1..1000 | ForEach-Object { "Hello: $_" }
}).TotalMilliseconds
24.9277
```

O primeiro exemplo acima mostra um loop foreach que cria trabalhos de thread de 1000 para fazer uma simples gravação de cadeia de caracteres. Devido à sobrecarga do trabalho, levará mais de 33 segundos para ser concluído.

O segundo exemplo executa o `ForEach` cmdlet para realizar as mesmas operações de 1000 e cada gravação de cadeia de caracteres é executada sequencialmente sem qualquer sobrecarga de trabalho. Ele é concluído em um mero 25 milissegundos.

```powershell
$logNames.count
10

Measure-Command {
    $logs = $logNames | ForEach {
        Start-ThreadJob {
            Get-WinEvent -LogName $using:_ -MaxEvents 5000 2>$null
        } -ThrottleLimit 10
    } | Wait-Job | Receive-Job
}

TotalMilliseconds : 115994.3 (1 minute 56 seconds)
$logs.Count
50000
```

No exemplo acima, até 5000 entradas são coletadas para 10 logs de sistema separados. Como o script envolve a leitura de um número de logs, faz sentido fazer as operações em paralelo. E o trabalho é concluído com duas vezes mais rápido quando o script é executado em sequência.

```powershell
Measure-Command {
    $logs = $logNames | ForEach-Object {
        Get-WinEvent -LogName $_ -MaxEvents 5000 2>$null
    }
}

TotalMilliseconds : 252398.4321 (4 minutes 12 seconds)
$logs.Count
50000
```

## <a name="thread-jobs-and-variables"></a>Trabalhos de thread e variáveis

As variáveis são passadas para trabalhos de thread de várias maneiras.

`Start-ThreadJob` pode aceitar variáveis que são canalizadas para o cmdlet, transmitidas para o bloco de script por meio da `$using` palavra-chave, ou transmitidas por meio do parâmetro **ArgumentList** .

```powershell
$msg = "Hello"

$msg | Start-ThreadJob { $input | Write-Output } | Wait-Job | Receive-Job

Start-ThreadJob { Write-Output $using:msg } | Wait-Job | Receive-Job

Start-ThreadJob { param ([string] $message) Write-Output $message } -ArgumentList @($msg) |
  Wait-Job | Receive-Job

`ForEach-Object -Parallel` accepts piped in variables, and variables passed
directly to the script block via the `$using` keyword.

```powershell
$msg = "Hello"

$msg | ForEach-Object -Parallel { Write-Output $_ } -AsJob | Wait-Job | Receive-Job

1..1 | ForEach-Object -Parallel { Write-Output $using:msg } -AsJob | Wait-Job | Receive-Job
```

Como os trabalhos de thread são executados no mesmo processo, qualquer tipo de referência de variável passado para o trabalho deve ser tratado com cuidado. Se não for um objeto de thread seguro, ele nunca deve ser atribuído, e o método e as propriedades nunca devem ser invocados nele.

```powershell
$threadSafeDictionary = [System.Collections.Concurrent.ConcurrentDictionary[string,object]]::new()
$jobs = Get-Process | ForEach {
    Start-ThreadJob {
        $proc = $using:_
        $dict = $using:threadSafeDictionary
        $dict.TryAdd($proc.ProcessName, $proc)
    }
}
$jobs | Wait-Job | Receive-Job

$threadSafeDictionary.Count
96

$threadSafeDictionary["pwsh"]

NPM(K)  PM(M)   WS(M) CPU(s)    Id SI ProcessName
------  -----   ----- ------    -- -- -----------
  112  108.25  124.43  69.75 16272  1 pwsh
```

O exemplo acima passa um objeto dotNet seguro de thread `ConcurrentDictionary` para todos os trabalhos filho para coletar objetos de processo nomeados exclusivamente. Como se trata de um objeto de thread seguro, ele pode ser usado com segurança enquanto os trabalhos são executados simultaneamente no processo.

## <a name="see-also"></a>Confira também

- [about_Remote_Jobs](about_Remote_Jobs.md)
- [about_Thread_Jobs](about_Thread_Jobs.md)
- [about_Job_Details](about_Job_Details.md)
- [about_Remote](about_Remote.md)
- [about_PSSessions](about_PSSessions.md)
- [Start-Job](xref:Microsoft.PowerShell.Core.Start-Job)
- [Get-Job](xref:Microsoft.PowerShell.Core.Get-Job)
- [Receive-Job](xref:Microsoft.PowerShell.Core.Receive-Job)
- [Stop-Job](xref:Microsoft.PowerShell.Core.Stop-Job)
- [Wait-Job](xref:Microsoft.PowerShell.Core.Wait-Job)
- [Remove-Job](xref:Microsoft.PowerShell.Core.Remove-Job)
