---
description: Fornece informações sobre como os trabalhos em segundo plano do PowerShell executam um comando ou expressão em segundo plano sem interagir com a sessão atual.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 03/26/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_jobs?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Jobs
ms.openlocfilehash: cd0274edabdaf8d859b1bf5bfe65c38f7b88ed74
ms.sourcegitcommit: ca5a89977913bad9efec6bcc23a792d113ec0396
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2021
ms.locfileid: "105630942"
---
# <a name="about-jobs"></a>Sobre trabalhos

## <a name="short-description"></a>Descrição breve
Fornece informações sobre como os trabalhos em segundo plano do PowerShell executam um comando ou expressão em segundo plano sem interagir com a sessão atual.

## <a name="long-description"></a>Descrição longa

O PowerShell executa comandos e scripts simultaneamente por meio de trabalhos. Há três tipos de trabalhos fornecidos pelo PowerShell para dar suporte à simultaneidade.

- `RemoteJob` -Comandos e scripts executados em uma sessão remota. Para obter informações, consulte [about_Remote_Jobs](about_Remote_Jobs.md).
- `BackgroundJob` -Comandos e scripts são executados em um processo separado no computador local.
- `PSTaskJob` ou `ThreadJob` -comandos e scripts são executados em um thread separado dentro do mesmo processo no computador local. Para obter mais informações, consulte [about_Thread_Jobs](/powershell/module/microsoft.powershell.core/about/about_thread_jobs).

Executar scripts remotamente, em um computador separado ou em um processo separado, fornece um excelente isolamento. Os erros que ocorrem no trabalho remoto não afetam outros trabalhos em execução ou a sessão pai que iniciou o trabalho. No entanto, a camada de comunicação remota adiciona sobrecarga, incluindo a serialização de objeto. Todos os objetos são serializados e desserializados à medida que são passados entre a sessão pai e a sessão remota (trabalho). A serialização de grandes objetos de dados complexos pode consumir grandes quantidades de recursos de computação e memória e transferir grandes quantidades de dados pela rede.

Os trabalhos baseados em thread não são tão robustos quanto os trabalhos remotos e em segundo plano, pois eles são executados no mesmo processo em threads diferentes. Se um trabalho tiver um erro crítico que falha no processo, todos os outros trabalhos no processo serão encerrados.

No entanto, os trabalhos baseados em thread exigem menos sobrecarga. Eles não usam a camada ou serialização de comunicação remota. Os objetos de resultado são retornados como referências a objetos dinâmicos na sessão atual. Sem essa sobrecarga, os trabalhos baseados em threads são executados mais rapidamente e usam menos recursos do que os outros tipos de trabalho.

> [!IMPORTANT]
> A sessão pai que criou o trabalho também monitora o status do trabalho e coleta dados do pipeline. O processo filho do trabalho é encerrado pelo processo pai quando o trabalho atinge um estado concluído. Se a sessão pai for encerrada, todos os trabalhos filho em execução serão encerrados junto com seus processos filho.

Há duas maneiras de solucionar essa situação:

1. Use `Invoke-Command` para criar trabalhos que são executados em sessões desconectadas. Para obter mais informações, consulte [about_Remote_Jobs](about_Remote_Jobs.md).
1. Use `Start-Process` para criar um novo processo em vez de um trabalho. Para obter mais informações, consulte [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).

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

Quando você inicia um trabalho em segundo plano, o prompt de comando retorna imediatamente, mesmo se o trabalho levar um tempo estendido para ser concluído. É possível continuar a trabalhar na sessão sem interrupção enquanto o trabalho é executado.

O `Start-Job` comando retorna um objeto que representa o trabalho. O objeto de trabalho contém informações úteis sobre o trabalho, mas não contém os resultados deste.

Você pode salvar o objeto de trabalho em uma variável e, em seguida, usá-lo com outros cmdlets de **trabalho** para gerenciar o trabalho em segundo plano. O comando a seguir inicia um objeto de trabalho e salva o objeto de trabalho resultante na `$job` variável.

```powershell
$job = Start-Job -ScriptBlock {Get-Process}
```

## <a name="getting-job-objects"></a>Obtendo objetos de trabalho

O `Get-Job` cmdlet retorna objetos que representam os trabalhos em segundo plano que foram iniciados na sessão atual. Sem parâmetros, `Get-Job` retorna todos os trabalhos que foram iniciados na sessão atual.

```powershell
Get-Job
```

O objeto de trabalho contém o estado do trabalho, que indica se o trabalho foi concluído. Um trabalho concluído tem um estado de **concluído** ou **com falha**. Um trabalho também pode ser **bloqueado** ou **em execução**.

```Output
Id  Name  PSJobTypeName State      HasMoreData  Location   Command
--  ----  ------------- -----      -----------  --------   -------
1   Job1  BackgroundJob Complete   True         localhost  Get-Process
```

Você pode salvar o objeto de trabalho em uma variável e usá-lo para representar o trabalho em um comando posterior. O comando a seguir obtém o trabalho com a ID 1 e salva-o na `$job` variável.

```powershell
$job = Get-Job -Id 1
```

## <a name="getting-the-results-of-a-job"></a>Obtendo os resultados de um trabalho

Quando você executa um trabalho em segundo plano, os resultados não aparecem imediatamente. Para obter os resultados de um trabalho em segundo plano, use o `Receive-Job` cmdlet.

O exemplo a seguir, o `Receive-Job` cmdlet obtém os resultados do trabalho usando o objeto de trabalho na `$job` variável.

```powershell
Receive-Job -Job $job
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)    Id ProcessName
-------  ------    -----      ----- -----   ------    -- -----------
    103       4    11328       9692    56           1176 audiodg
    804      14    12228      14108   100   101.74  1740 CcmExec
    668       7     2672       6168   104    32.26   488 csrss
...
```

Você pode salvar os resultados de um trabalho em uma variável. O comando a seguir salva os resultados do trabalho na `$job` variável para a `$results` variável.

```powershell
$results = Receive-Job -Job $job
```

### <a name="getting-and-keeping-partial-job-results"></a>Obtendo e mantendo resultados parciais do trabalho

O `Receive-Job` cmdlet obtém os resultados de um trabalho em segundo plano. Se o trabalho estiver concluído, `Receive-Job` Obtém todos os resultados do trabalho. Se o trabalho ainda estiver em execução, `Receive-Job` o obterá os resultados gerados até o momento. Você pode executar `Receive-Job` comandos novamente para obter os resultados restantes.

Por padrão, `Receive-Job` o exclui os resultados do cache onde os resultados do trabalho são armazenados. Ao executar `Receive-Job` novamente, você obtém apenas os novos resultados que chegaram após a primeira execução.

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

Use o parâmetro **Keep** para impedir `Receive-Job` a exclusão dos resultados do trabalho que são retornados. Os comandos a seguir mostram o efeito de usar o parâmetro **Keep** em um trabalho que ainda não está concluído.

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

### <a name="waiting-for-the-results"></a>Aguardando os resultados

Se você executar um comando que leva muito tempo para ser concluído, poderá usar as propriedades do objeto de trabalho para determinar quando o trabalho foi concluído. O comando a seguir usa o `Get-Job` objeto para obter todos os trabalhos em segundo plano na sessão atual.

```powershell
Get-Job
```

Os resultados aparecem em uma tabela. O status do trabalho é exibido na coluna **estado** .

```Output
Id Name  PSJobTypeName State    HasMoreData Location  Command
-- ----  ------------- -----    ----------- --------  -------
1  Job1  BackgroundJob Complete True        localhost Get-Process
2  Job2  BackgroundJob Running  True        localhost Get-EventLog -Log ...
3  Job3  BackgroundJob Complete True        localhost dir -Path C:\* -Re...
```

Nesse caso, a propriedade **State** revela que o trabalho 2 ainda está em execução. Se você usar o `Receive-Job` cmdlet para obter os resultados do trabalho agora, os resultados ficarão incompletos. Você pode usar o `Receive-Job` cmdlet repetidamente para obter todos os resultados. Use a propriedade **State** para determinar quando o trabalho foi concluído.

Você também pode usar o parâmetro **Wait** do `Receive-Job` cmdlet. Quando usar esse parâmetro, o cmdlet não retorna o prompt de comando até que o trabalho seja concluído e todos os resultados estejam disponíveis.

Você também pode usar o `Wait-Job` cmdlet para aguardar qualquer ou todos os resultados do trabalho. `Wait-Job` permite que você aguarde um ou mais trabalhos específicos ou todos eles.
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

Os trabalhos podem falhar por vários motivos. o objeto de trabalho contém uma propriedade **Reason** que contém informações sobre a causa da falha.

O exemplo a seguir inicia um trabalho sem as credenciais necessárias.

```powershell
$job = Start-Job -ScriptBlock {New-Item -Path HKLM:\Software\MyCompany}
Get-Job $job

Id Name  PSJobTypeName State  HasMoreData  Location  Command
-- ----  ------------- -----  -----------  --------  -------
1  Job1  BackgroundJob Failed False        localhost New-Item -Path HKLM:...
```

Inspecione a propriedade **Reason** para localizar o erro que causou a falha do trabalho.

```powershell
$job.ChildJobs[0].JobStateInfo.Reason
```

Nesse caso, o trabalho falhou porque o computador remoto exigia credenciais explícitas para executar o comando. A propriedade **Reason** contém a seguinte mensagem:

> Falha ao conectar-se ao servidor remoto com a seguinte mensagem de erro: "acesso negado".

## <a name="see-also"></a>Consulte também

- [about_Remote_Jobs](about_Remote_Jobs.md)
- [about_Thread_Jobs](/powershell/module/microsoft.powershell.core/about/about_Thread_Jobs)
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
