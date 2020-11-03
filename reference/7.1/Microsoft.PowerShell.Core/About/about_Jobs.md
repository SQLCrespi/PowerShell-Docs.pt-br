---
description: Fornece informações sobre como os trabalhos em segundo plano do PowerShell executam um comando ou expressão em segundo plano sem interagir com a sessão atual.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_jobs?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Jobs
ms.openlocfilehash: b28eb480e3f994696738d6053ea7e2622a743ce5
ms.sourcegitcommit: 108686b166672cc08817c637dd93eb1ad830511d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "93196479"
---
# <a name="about-jobs"></a>Sobre trabalhos

## <a name="short-description"></a>Descrição breve
Fornece informações sobre como os trabalhos em segundo plano do PowerShell executam um comando ou expressão em segundo plano sem interagir com a sessão atual.

## <a name="long-description"></a>Descrição longa

O PowerShell executa comandos e scripts simultaneamente por meio de trabalhos. Há três soluções baseadas em trabalhos fornecidas pelo PowerShell para dar suporte à simultaneidade.

|Trabalho            |Descrição                                                  |
|---------------|-------------------------------------------------------------|
|`RemoteJob`    |O comando e o script são executados em um computador remoto.                 |
|`BackgroundJob`|O comando e o script são executados em um processo separado no local    |
|               |Tradução.                                                     |
|`ThreadJob`    |O comando e o script são executados em um thread separado dentro do mesmo  |
|               |processo no computador local.                                |

Cada tipo de trabalho tem benefícios e desvantagens. Executar o script remotamente em um computador separado ou em um processo separado tem grande isolamento. Quaisquer erros não afetarão outros trabalhos em execução ou o cliente que iniciou o trabalho. Mas a camada de comunicação remota adiciona sobrecarga, incluindo a serialização de objeto. Todos os objetos passados para e da sessão remota devem ser serializados e, em seguida, desserializados conforme passam entre o cliente e a sessão de destino. A operação de serialização pode usar muitos recursos de computação e memória para grandes objetos de dados complexos.

Este tópico explica como executar trabalhos em segundo plano no PowerShell em um computador local. Para obter informações sobre como executar trabalhos em segundo plano em computadores remotos, consulte [about_Remote_Jobs](about_Remote_Jobs.md). Para obter mais informações sobre os trabalhos de thread, consulte [about_Thread_Jobs](about_Thread_Jobs.md).

Quando você inicia um trabalho em segundo plano, o prompt de comando retorna imediatamente, mesmo se o trabalho levar um tempo estendido para ser concluído. É possível continuar a trabalhar na sessão sem interrupção enquanto o trabalho é executado.

## <a name="the-job-cmdlets"></a>Os cmdlets de trabalho

|Cmdlet          |Descrição                                            |
|----------------|-------------------------------------------------------|
|`Start-Job`     |Inicia um trabalho em segundo plano em um computador local.           |
|`Get-Job`       |Obtém os trabalhos em segundo plano que foram iniciados no      |
|                |sessão atual.                                       |
|`Receive-Job`   |Obtém os resultados de trabalhos em segundo plano.                   |
|`Stop-Job`      |Interrompe um trabalho em segundo plano.                                |
|`Wait-Job`      |Suprime o prompt de comando até que um ou todos os trabalhos sejam|
|                |concluí.                                              |
|`Remove-Job`    |Exclui um trabalho em segundo plano.                              |
|`Invoke-Command`|O parâmetro **AsJob** cria um trabalho em segundo plano em um  |
|                |computador remoto. Você pode usar `Invoke-Command` para executar   |
|                |qualquer comando de trabalho remotamente, incluindo `Start-Job` .       |

## <a name="how-to-start-a-job-on-the-local-computer"></a>Como iniciar um trabalho no computador local

Para iniciar um trabalho em segundo plano no computador local, use o `Start-Job` cmdlet.

Para gravar um `Start-Job` comando, coloque o comando que o trabalho executa entre chaves ( `{}` ). Use o parâmetro **scriptblock** para especificar o comando.

O comando a seguir inicia um trabalho em segundo plano que executa um `Get-Process` comando no computador local.

```powershell
Start-Job -ScriptBlock {Get-Process}
```

O `Start-Job` comando retorna um objeto que representa o trabalho. O objeto de trabalho contém informações úteis sobre o trabalho, mas não contém os resultados deste.

Salve o objeto de trabalho em uma variável e, em seguida, use-o com os outros cmdlets de trabalho para gerenciar o trabalho em segundo plano. O comando a seguir inicia um objeto de trabalho e salva o objeto de trabalho resultante na `$job` variável.

```powershell
$job = Start-Job -ScriptBlock {Get-Process}
```

A partir do PowerShell 6,0, você pode usar um amersand ( `&` ) no final de um pipeline para iniciar um trabalho em segundo plano. O comando a seguir é funcionalmente equivalente ao comando acima.

```powershell
$job = Get-Process &
```

O e comercial ( `&` ) é chamado de operador de segundo plano. Para obter mais informações, consulte [background Operator](about_Operators.md#background-operator-).

Você também pode usar o `Get-Job` cmdlet para obter objetos que representam os trabalhos iniciados na sessão atual. `Get-Job` Retorna o mesmo objeto de trabalho que `Start-Job` retorna.

## <a name="getting-job-objects"></a>Obtendo objetos de trabalho

Para obter o objeto que representa os trabalhos em segundo plano que foram iniciados na sessão atual, use o `Get-Job` cmdlet. Sem parâmetros, `Get-Job` retorna todos os trabalhos que foram iniciados na sessão atual.

Por exemplo, o comando a seguir obtém os trabalhos na sessão atual.

```powershell
PS C:> Get-Job

Id  Name  PSJobTypeName State      HasMoreData  Location   Command
--  ----  ------------- -----      -----------  --------   -------
1   Job1  BackgroundJob Running    True         localhost  Get-Process
```

Você também pode salvar o objeto de trabalho em uma variável e usá-lo para representar o trabalho em um comando posterior. O comando a seguir obtém o trabalho com a ID 1 e salva-o na `$job` variável.

```powershell
$job = Get-Job -Id 1
```

O objeto de trabalho contém o estado do trabalho, que indica se o trabalho foi concluído. Um trabalho concluído tem um estado de **concluído** ou **com falha** . Um trabalho também pode ser **bloqueado** ou **em execução** .

```powershell
Get-Job

Id  Name  PSJobTypeName State      HasMoreData  Location   Command
--  ----  ------------- -----      -----------  --------   -------
1   Job1  BackgroundJob Complete   True         localhost  Get-Process
```

## <a name="getting-the-results-of-a-job"></a>Obtendo os resultados de um trabalho

Quando você executa um trabalho em segundo plano, os resultados não aparecem imediatamente. Em vez disso, o `Start-Job` cmdlet retorna um objeto de trabalho que representa o trabalho, mas ele não contém os resultados. Para obter os resultados de um trabalho em segundo plano, use o `Receive-Job` cmdlet.

O comando a seguir usa o `Receive-Job` cmdlet para obter os resultados do trabalho. Ele usa um objeto de trabalho salvo na `$job` variável para identificar o trabalho.

```powershell
Receive-Job -Job $job
```

O `Receive-Job` cmdlet retorna os resultados do trabalho.

```
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)    Id ProcessName
-------  ------    -----      ----- -----   ------    -- -----------
    103       4    11328       9692    56           1176 audiodg
    804      14    12228      14108   100   101.74  1740 CcmExec
    668       7     2672       6168   104    32.26   488 csrss
# ...
```

Você também pode salvar os resultados de um trabalho em uma variável. O comando a seguir salva os resultados do trabalho na `$job` variável para a `$results` variável.

```powershell
$results = Receive-Job -Job $job
```

E você pode salvar os resultados do trabalho em um arquivo usando o operador de redirecionamento ( `>` ) ou o `Out-File` cmdlet. O comando a seguir usa o operador de redirecionamento para salvar os resultados do trabalho na `$job` variável no `Results.txt` arquivo.

```powershell
Receive-Job -Job $job > results.txt
```

## <a name="getting-and-keeping-partial-job-results"></a>Obtendo e mantendo resultados parciais do trabalho

O `Receive-Job` cmdlet obtém os resultados de um trabalho em segundo plano. Se o trabalho estiver concluído, `Receive-Job` Obtém todos os resultados do trabalho. Se o trabalho ainda estiver em execução, `Receive-Job` o obterá os resultados gerados até o momento. Você pode executar `Receive-Job` comandos novamente para obter os resultados restantes.

Quando o `Receive-Job` retorna resultados, por padrão, ele exclui os resultados do cache onde os resultados do trabalho são armazenados. Se você executar outro `Receive-Job` comando, obterá apenas os resultados que ainda não foram recebidos.

Os comandos a seguir mostram os resultados da `Receive-Job` execução de comandos antes que o trabalho seja concluído.

```powershell
C:\PS> Receive-Job -Job $job

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    103       4    11328       9692    56            1176 audiodg
    804      14    12228      14108   100   101.74   1740 CcmExec

C:\PS> Receive-Job -Job $job

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    68       3     2632        664    29     0.36   1388 ccmsetup
   749      22    21468      19940   203   122.13   3644 communicator
   905       7     2980       2628    34   197.97    424 csrss
  1121      25    28408      32940   174   430.14   3048 explorer
```

Para evitar `Receive-Job` a exclusão dos resultados do trabalho que ele retornou, use o parâmetro **Keep** . Como resultado, `Receive-Job` retorna todos os resultados que foram gerados até esse momento.

Os comandos a seguir mostram o efeito de usar o parâmetro **Keep** em um trabalho que ainda não está concluído.

```powershell
C:\PS> Receive-Job -Job $job -Keep

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    103       4    11328       9692    56            1176 audiodg
    804      14    12228      14108   100   101.74   1740 CcmExec

C:\PS> Receive-Job -Job $job -Keep

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    103       4    11328       9692    56            1176 audiodg
    804      14    12228      14108   100   101.74   1740 CcmExec
     68       3     2632        664    29     0.36   1388 ccmsetup
    749      22    21468      19940   203   122.13   3644 communicator
    905       7     2980       2628    34   197.97    424 csrss
   1121      25    28408      32940   174   430.14   3048 explorer
```

## <a name="waiting-for-the-results"></a>Aguardando os resultados

Se você executar um comando que leva muito tempo para ser concluído, poderá usar as propriedades do objeto de trabalho para determinar quando o trabalho foi concluído. O comando a seguir usa o `Get-Job` objeto para obter todos os trabalhos em segundo plano na sessão atual.

```powershell
Get-Job
```

Os resultados aparecem em uma tabela. O status do trabalho é exibido na coluna **estado** .

```
Id Name  PSJobTypeName State    HasMoreData Location  Command
-- ----  ------------- -----    ----------- --------  -------
1  Job1  BackgroundJob Complete True        localhost Get-Process
2  Job2  BackgroundJob Running  True        localhost Get-EventLog -Log ...
3  Job3  BackgroundJob Complete True        localhost dir -Path C:\* -Re...
```

Nesse caso, a propriedade State revela que o trabalho 2 ainda está em execução. Se você usar o `Receive-Job` cmdlet para obter os resultados do trabalho agora, os resultados ficarão incompletos. Você pode usar o `Receive-Job` cmdlet repetidamente para obter todos os resultados. Por padrão, cada vez que você o usa, obtém apenas os resultados que ainda não foram recebidos, mas você pode usar o parâmetro **Keep** do `Receive-Job` cmdlet para manter os resultados, mesmo que eles já tenham sido recebidos.

Você pode gravar os resultados parciais em um arquivo e, em seguida, acrescentar os resultados mais recentes à medida que eles chegam, ou você pode aguardar e verificar o estado do trabalho mais tarde.

Você pode usar o parâmetro **Wait** do `Receive-Job` cmdlet, que não retorna o prompt de comando até que o trabalho seja concluído e que todos os resultados estejam disponíveis.

Você também pode usar o `Wait-Job` cmdlet para aguardar qualquer ou todos os resultados do trabalho. `Wait-Job` permite que você aguarde um trabalho específico, para todos os trabalhos ou para que qualquer um dos trabalhos seja concluído.

O comando a seguir usa o `Wait-Job` cmdlet para aguardar um trabalho com **ID**
10.

```powershell
Wait-Job -ID 10
```

Como resultado, o prompt do PowerShell é suprimido até que o trabalho seja concluído.

Você também pode aguardar um período de tempo predeterminado. Esse comando usa o parâmetro **Timeout** para limitar a espera de 120 segundos. Quando o tempo expira, o prompt de comando retorna, mas o trabalho continua a ser executado em segundo plano.

```powershell
Wait-Job -ID 10 -Timeout 120
```

## <a name="stopping-a-job"></a>Interrompendo um trabalho

Para interromper um trabalho em segundo plano, use o `Stop-Job` cmdlet. O comando a seguir inicia um trabalho para obter todas as entradas no log de eventos do sistema. Ele salva o objeto de trabalho na `$job` variável.

```powershell
$job = Start-Job -ScriptBlock {Get-EventLog -Log System}
```

O comando a seguir interrompe o trabalho. Ele usa um operador de pipeline ( `|` ) para enviar o trabalho na `$job` variável para `Stop-Job` .

```powershell
$job | Stop-Job
```

## <a name="deleting-a-job"></a>Excluindo um trabalho

Para excluir um trabalho em segundo plano, use o `Remove-Job` cmdlet. O comando a seguir exclui o trabalho na `$job` variável.

```powershell
Remove-Job -Job $job
```

## <a name="investigating-a-failed-job"></a>Investigando um trabalho com falha

Para descobrir por que um trabalho falhou, use a propriedade **Reason** do objeto Job.

O comando a seguir inicia um trabalho sem as credenciais necessárias. Ele salva o objeto de trabalho na `$job` variável.

```powershell
$job = Start-Job -ScriptBlock {New-Item -Path HKLM:\Software\MyCompany}

Id Name  PSJobTypeName State  HasMoreData  Location  Command
-- ----  ------------- -----  -----------  --------  -------
1  Job1  BackgroundJob Failed False        localhost New-Item -Path HKLM:...
```

O comando a seguir usa a propriedade Reason para localizar o erro que causou a falha do trabalho.

```powershell
$job.ChildJobs[0].JobStateInfo.Reason
```

Nesse caso, o trabalho falhou porque o computador remoto exigia credenciais explícitas para executar o comando. O valor da propriedade **Reason** é:

Falha ao conectar-se ao servidor remoto com a seguinte mensagem de erro: "acesso negado".

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
- [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)
