---
description: Fornece informações sobre os trabalhos baseados em thread do PowerShell. Um trabalho de thread é um tipo de trabalho em segundo plano que executa um comando ou expressão em um thread separado dentro do processo de sessão atual.
Locale: en-US
ms.date: 11/11/2020
schema: 2.0.0
title: about_Thread_Jobs
ms.openlocfilehash: 67f3fc585a8c2d1c3ca98c7336a7e367ed6c66c7
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "103193969"
---
# <a name="about-thread-jobs"></a>Sobre os trabalhos de thread

## <a name="short-description"></a>Descrição breve

Fornece informações sobre os trabalhos baseados em thread do PowerShell. Um trabalho de thread é um tipo de trabalho em segundo plano que executa um comando ou expressão em um thread separado dentro do processo de sessão atual.

## <a name="long-description"></a>Descrição longa

O PowerShell executa comandos e scripts simultaneamente por meio de trabalhos. Há três tipos de trabalhos fornecidos pelo PowerShell para dar suporte à simultaneidade.

- `RemoteJob` -Comandos e scripts executados em uma sessão remota. Para obter informações, consulte [about_Remote_Jobs](about_Remote_Jobs.md).
- `BackgroundJob` -Comandos e scripts são executados em um processo separado no computador local. Para obter mais informações, consulte [about_Jobs](about_Jobs.md).
- `PSTaskJob` ou `ThreadJob` -comandos e scripts são executados em um thread separado dentro do mesmo processo no computador local.

Os trabalhos baseados em thread não são tão robustos quanto os trabalhos remotos e em segundo plano, pois eles são executados no mesmo processo em threads diferentes. Se um trabalho tiver um erro crítico que falha no processo, todos os outros trabalhos no processo serão encerrados.

No entanto, os trabalhos baseados em thread exigem menos sobrecarga. Eles não usam a camada ou serialização de comunicação remota. Os objetos de resultado são retornados como referências a objetos dinâmicos na sessão atual. Sem essa sobrecarga, os trabalhos baseados em threads são executados mais rapidamente e usam menos recursos do que os outros tipos de trabalho.

> [!IMPORTANT]
> A sessão pai que criou o trabalho também monitora o status do trabalho e coleta dados do pipeline. O processo filho do trabalho é encerrado pelo processo pai quando o trabalho atinge um estado concluído. Se a sessão pai for encerrada, todos os trabalhos filho em execução serão encerrados junto com seus processos filho.

Há duas maneiras de solucionar essa situação:

1. Use `Invoke-Command` para criar trabalhos que são executados em sessões desconectadas. Para obter mais informações, consulte [about_Remote_Jobs](about_Remote_Jobs.md).
1. Use `Start-Process` para criar um novo processo em vez de um trabalho. Para obter mais informações, consulte [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).

## <a name="how-to-start-and-manage-thread-based-jobs"></a>Como iniciar e gerenciar trabalhos baseados em thread

Há duas maneiras de iniciar trabalhos baseados em thread:

- `Start-ThreadJob`-do módulo **ThreadJob**
- `ForEach-Object -Parallel -AsJob` -o recurso paralelo foi adicionado no PowerShell 7,0

Use os mesmos cmdlets de **trabalho** descritos em [about_Jobs](about_Jobs.md) para gerenciar trabalhos baseados em thread.

### <a name="using-start-threadjob"></a>Usando `Start-ThreadJob`

O módulo **ThreadJob** foi enviado pela primeira vez com o PowerShell 6. Ele também pode ser instalado do Galeria do PowerShell para o Windows PowerShell 5,1.

Para iniciar um trabalho de thread no computador local, use o `Start-ThreadJob` cmdlet com um comando ou script entre chaves ( `{ }` ).

O exemplo a seguir inicia um trabalho de thread que executa um `Get-Process` comando no computador local.

```powershell
Start-ThreadJob -ScriptBlock { Get-Process }
```

O `Start-ThreadJob` comando retorna um `ThreadJob` objeto que representa o trabalho em execução. O objeto de trabalho contém informações úteis sobre o trabalho, incluindo seu status de execução atual. Ele coleta os resultados do trabalho à medida que os resultados são gerados.

### <a name="using-foreach-object--parallel--asjob"></a>Usando `ForEach-Object -Parallel -AsJob`

O PowerShell 7,0 adicionou um novo parâmetro definido para o `ForEach-Object` cmdlet. Os novos parâmetros permitem executar blocos de script em threads paralelos como trabalhos do PowerShell.

Você pode canalizar dados para o `ForEach-Object -Parallel` . Os dados são passados para o bloco de script que é executado em paralelo. O `-AsJob` parâmetro cria objetos de trabalhos para cada um dos threads paralelos.

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
36860.8226

(Measure-Command {
    1..1000 | ForEach-Object { "Hello: $_" }
}).TotalMilliseconds
7.1975
```

O primeiro exemplo acima mostra um loop foreach que cria trabalhos de thread de 1000 para fazer uma simples gravação de cadeia de caracteres. Devido à sobrecarga do trabalho, levará mais de 36 segundos para ser concluído.

O segundo exemplo executa o `ForEach` cmdlet para realizar as mesmas operações de 1000.
Desta vez, `ForEach-Object` é executado em sequência, em um único thread, sem nenhuma sobrecarga de trabalho. Ele é concluído em um mero 7 milissegundos.

No exemplo a seguir, até 5000 entradas são coletadas para 10 logs de sistema separados. Como o script envolve a leitura de um número de logs, faz sentido fazer as operações em paralelo.

```powershell
$logNames.count
10

Measure-Command {
    $logs = $logNames | ForEach-Object {
        Get-WinEvent -LogName $_ -MaxEvents 5000 2>$null
    }
}

TotalMilliseconds : 252398.4321 (4 minutes 12 seconds)
$logs.Count
50000
```

O script é concluído na metade do tempo em que os trabalhos são executados em paralelo.

```powershell
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

## <a name="thread-jobs-and-variables"></a>Trabalhos de thread e variáveis

Há várias maneiras de passar valores para os trabalhos baseados em thread.

`Start-ThreadJob` pode aceitar variáveis que são canalizadas para o cmdlet, transmitidas para o bloco de script por meio da `$using` palavra-chave, ou transmitidas por meio do parâmetro **ArgumentList** .

```powershell
$msg = "Hello"

$msg | Start-ThreadJob { $input | Write-Output } | Wait-Job | Receive-Job

Start-ThreadJob { Write-Output $using:msg } | Wait-Job | Receive-Job

Start-ThreadJob { param ([string] $message) Write-Output $message } -ArgumentList @($msg) |
  Wait-Job | Receive-Job
```

`ForEach-Object -Parallel` aceita o piped em variáveis e variáveis passadas diretamente para o bloco de script por meio da `$using` palavra-chave.

```powershell
$msg = "Hello"

$msg | ForEach-Object -Parallel { Write-Output $_ } -AsJob | Wait-Job | Receive-Job

1..1 | ForEach-Object -Parallel { Write-Output $using:msg } -AsJob | Wait-Job | Receive-Job
```

Como os trabalhos de thread são executados no mesmo processo, qualquer tipo de referência de variável passado para o trabalho deve ser tratado com cuidado. Se não for um objeto de thread seguro, ele nunca deve ser atribuído, e o método e as propriedades nunca devem ser invocados nele.

O exemplo a seguir passa um objeto .NET thread-safe `ConcurrentDictionary` para todos os trabalhos filho para coletar objetos de processo nomeados exclusivamente. Como se trata de um objeto de thread seguro, ele pode ser usado com segurança enquanto os trabalhos são executados simultaneamente no processo.

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
