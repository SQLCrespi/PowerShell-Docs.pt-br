---
description: Fornece detalhes sobre trabalhos em segundo plano em computadores locais e remotos.
Locale: en-US
ms.date: 10/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_job_details?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Job_Details
ms.openlocfilehash: 1ceb0be9cc140b69afdebaaf336dad75e482aa22
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597839"
---
# <a name="about-job-details"></a>Sobre os detalhes do trabalho

## <a name="short-description"></a>Descrição breve
Fornece detalhes sobre trabalhos em segundo plano em computadores locais e remotos.

## <a name="detailed-description"></a>Descrição detalhada

Este tópico explica o conceito de um trabalho em segundo plano e fornece informações técnicas sobre como trabalhos em segundo plano funcionam no PowerShell.

Este tópico é um suplemento para os tópicos [about_Jobs](about_Jobs.md), [about_Thread_Jobs](about_Thread_Jobs.md)e [about_Remote_Jobs](about_Remote_Jobs.md) .

### <a name="about-background-jobs"></a>Sobre trabalhos em segundo plano

Um trabalho em segundo plano executa um comando ou expressão de forma assíncrona. Ele pode executar um cmdlet, uma função, um script ou qualquer outra tarefa baseada em comando. Ele foi projetado para executar comandos que usam um longo período de tempo, mas você pode usá-lo para executar qualquer comando em segundo plano.

Quando um comando síncrono é executado, o prompt de comando do PowerShell é suprimido até que o comando seja concluído. Mas um trabalho em segundo plano não suprime o prompt do PowerShell. Um comando para iniciar um trabalho em segundo plano retorna um objeto de trabalho.
O prompt retorna imediatamente para que você possa trabalhar em outras tarefas enquanto o trabalho em segundo plano é executado.

No entanto, ao iniciar um trabalho em segundo plano, você não obtém os resultados imediatamente, mesmo que o trabalho seja executado muito rapidamente. O objeto de trabalho retornado contém informações úteis sobre o trabalho, mas não contém os resultados do trabalho. Você deve executar um comando separado para obter os resultados do trabalho. Você também pode executar comandos para interromper o trabalho, aguardar a conclusão do trabalho e excluir o trabalho.

Para tornar o tempo de um trabalho em segundo plano independente de outros comandos, cada trabalho em segundo plano é executado em sua própria sessão do PowerShell. No entanto, essa pode ser uma conexão temporária que é criada somente para executar o trabalho e, em seguida, destruída, ou pode ser uma **PSSession** persistente que você pode usar para executar vários trabalhos ou comandos relacionados.

### <a name="using-the-job-cmdlets"></a>Usando os cmdlets de trabalho

Use um `Start-Job` comando para iniciar um trabalho em segundo plano em um computador local.
`Start-Job` Retorna um objeto de trabalho. Você também pode obter objetos que representam os trabalhos que foram iniciados no computador local usando o `Get-Job` cmdlet.

Para obter os resultados do trabalho, use um `Receive-Job` comando. Se o trabalho não estiver concluído, o `Receive-Job` retornará resultados parciais. Você também pode usar o `Wait-Job` cmdlet para suprimir o prompt de comando até que um ou todos os trabalhos iniciados na sessão sejam concluídos.

Para interromper um trabalho em segundo plano, use o `Stop-Job` cmdlet. Para excluir um trabalho, use o `Remove-Job` cmdlet.

Para obter mais informações sobre como os cmdlets funcionam, consulte o tópico da ajuda para cada cmdlet e consulte [about_Jobs](about_Jobs.md).

### <a name="starting-background-jobs-on-remote-computers"></a>Iniciando trabalhos em segundo plano em computadores remotos

Você pode criar e gerenciar trabalhos em segundo plano em um computador local ou remoto. Para executar um trabalho em segundo plano remotamente, use o parâmetro **AsJob** de um cmdlet `Invoke-Command` , como, ou use o `Invoke-Command` cmdlet para executar um `Start-Job` comando remotamente. Você também pode iniciar um trabalho em segundo plano em uma sessão interativa.

Para obter mais informações sobre trabalhos em segundo plano remotos, consulte [about_Remote_Jobs](about_Remote_Jobs.md).

### <a name="child-jobs"></a>Trabalhos filho

Cada trabalho em segundo plano consiste em um trabalho pai e um ou mais trabalhos filho. Em trabalhos iniciados usando `Start-Job` o ou o parâmetro **AsJob** de `Invoke-Command` , o trabalho pai é um executivo. Ele não executa nenhum comando nem retorna nenhum resultado. Os comandos são realmente executados pelos trabalhos filho. Os trabalhos iniciados usando outros cmdlets podem funcionar de maneira diferente.

Os trabalhos filho são armazenados na propriedade **ChildJobs** do objeto de trabalho pai. A propriedade **ChildJobs** pode conter um ou vários objetos de trabalho filho.
Os objetos de trabalho filho têm um **nome**, **ID** e **InstanceId** que diferem do trabalho pai para que você possa gerenciar os trabalhos pai e filho individualmente ou como uma unidade.

Para obter os trabalhos pai e filho de um trabalho, use o parâmetro **IncludeChildJobs** do `Get-Job` cmdlet. O parâmetro **IncludeChildJob** foi introduzido no Windows PowerShell 3,0.

```powershell
PS> Get-Job -IncludeChildJob

Id Name   PSJobTypeName State      HasMoreData   Location    Command
-- ----   ------------- -----      -----------   --------    -------
1  Job1   RemoteJob     Failed     True          localhost   Get-Process
2  Job2                 Completed  True          Server01    Get-Process
3  Job3                 Failed     False         localhost   Get-Process
```

Para obter o trabalho pai e apenas os trabalhos filho com um valor de **estado** específico, use o parâmetro **ChildJobState** do `Get-Job` cmdlet. O parâmetro **ChildJobState** foi introduzido no Windows PowerShell 3,0.

```powershell
PS> Get-Job -ChildJobState Failed

Id Name   PSJobTypeName State      HasMoreData   Location    Command
-- ----   ------------- -----      -----------   --------    -------
1  Job1   RemoteJob     Failed     True          localhost   Get-Process
3  Job3                 Failed     False         localhost   Get-Process
```

Para obter os trabalhos filho de um trabalho em todas as versões do PowerShell, use a propriedade **ChildJob** do trabalho pai.

```powershell
PS> (Get-Job Job1).ChildJobs

Id Name   PSJobTypeName State      HasMoreData   Location    Command
-- ----   ------------- -----      -----------   --------    -------
2  Job2                 Completed  True          Server01    Get-Process
3  Job3                 Failed     False         localhost   Get-Process
```

Você também pode usar um `Get-Job` comando no trabalho filho, conforme mostrado no seguinte comando:

```powershell
PS> Get-Job Job3

Id Name   PSJobTypeName State      HasMoreData   Location    Command
-- ----   ------------- -----      -----------   --------    -------
3  Job3                 Failed     False         localhost   Get-Process
```

A configuração do trabalho filho depende do comando que você usa para iniciar o trabalho.

- Quando você usa `Start-Job` o para iniciar um trabalho em um computador local, o trabalho consiste em um trabalho pai executivo e um trabalho filho que executa o comando.

- Quando você usa o parâmetro **AsJob** do `Invoke-Command` para iniciar um trabalho em um ou mais computadores, o trabalho consiste em um trabalho pai executivo e um trabalho filho para cada trabalho executado em cada computador.

- Quando você usa o `Invoke-Command` para executar um `Start-Job` comando em um ou mais computadores remotos, o resultado é o mesmo que um comando local executado em cada computador remoto. O comando retorna um objeto de trabalho para cada computador. O objeto de trabalho consiste em um trabalho pai executivo e um trabalho filho que executa o comando.

O trabalho pai representa todos os trabalhos filho. Ao gerenciar um trabalho pai, você também gerencia os trabalhos filho associados. Por exemplo, se você parar um trabalho pai, todos os trabalhos filho serão interrompidos. Se você obtiver os resultados de um trabalho pai, obterá os resultados de todos os trabalhos filho.

No entanto, você também pode gerenciar trabalhos filhos individualmente. Isso é mais útil quando você deseja investigar um problema com um trabalho ou obter os resultados de apenas um dos vários trabalhos filho iniciado usando o parâmetro **AsJob** de `Invoke-Command` .

O comando a seguir usa o parâmetro **AsJob** do `Invoke-Command` para iniciar trabalhos em segundo plano no computador local e em dois computadores remotos. O comando salva o trabalho na `$j` variável.

```powershell
PS> $j = Invoke-Command -ComputerName localhost, Server01, Server02 `
-Command {Get-Date} -AsJob
```

Quando você exibe as propriedades Name e **ChildJob** do trabalho no `$j` , ele mostra que o comando retornou um objeto de trabalho com três trabalhos filho, um para cada computador.

```powershell
PS> $j | Format-List Name, ChildJobs

Name      : Job3
ChildJobs : {Job4, Job5, Job6}
```

Quando você exibe o trabalho pai, ele mostra que o trabalho falhou.

```powershell
PS> $j

Id Name   PSJobTypeName State      HasMoreData   Location
-- ----   ------------- -----      -----------   --------
3  Job3   RemotingJob   Failed     False         localhost,Server...
```

Mas quando você executa um `Get-Job` comando que obtém os trabalhos filho, a saída mostra que apenas um trabalho filho falhou.

```powershell
PS> Get-Job -IncludeChildJobs

Id  Name   PSJobTypeName State      HasMoreData   Location    Command
--  ----   ------------- -----      -----------   --------    -------
3   Job3   RemotingJob   Failed     False         localhost,Server...
4   Job4                 Completed  True          localhost   Get-Date
5   Job5                 Failed     False         Server01    Get-Date
6   Job6                 Completed  True          Server02    Get-Date
```

Para obter os resultados de todos os trabalhos filho, use o `Receive-Job` cmdlet para obter os resultados do trabalho pai. Mas você também pode obter os resultados de um trabalho filho específico, conforme mostrado no comando a seguir.

```powershell
PS> Receive-Job -Name Job6 -Keep | Format-Table ComputerName,
>> DateTime -AutoSize
ComputerName DateTime
------------ --------
Server02     Thursday, March 13, 2008 4:16:03 PM
```

O recurso de trabalhos filho de trabalhos em segundo plano do PowerShell oferece mais controle sobre os trabalhos que você executa.

### <a name="job-types"></a>Tipos de trabalho

O PowerShell dá suporte a diferentes tipos de trabalhos para tarefas diferentes. A partir do Windows PowerShell 3,0, os desenvolvedores podem escrever "adaptadores de origem do trabalho" que adicionam novos tipos de trabalho ao PowerShell e incluem os adaptadores de origem do trabalho em módulos.
Ao importar o módulo, você pode usar o novo tipo de trabalho em sua sessão.

Por exemplo, o módulo PSScheduledJob adiciona trabalhos agendados e o módulo PSWorkflow adiciona trabalhos de fluxo de trabalho.

Os tipos de trabalhos personalizados podem diferir significativamente dos trabalhos em segundo plano padrão do PowerShell. Por exemplo, os trabalhos agendados são salvos em disco; Eles não existem somente em uma sessão específica. Os trabalhos de fluxo de trabalho podem ser suspensos e retomados.

Os cmdlets que você usa para gerenciar trabalhos personalizados dependem do tipo de trabalho. Para alguns, você usa os cmdlets de trabalho padrão, como `Get-Job` e `Start-Job` . Outras são fornecidas com cmdlets especializados que gerenciam apenas um determinado tipo de trabalho. Para obter informações detalhadas sobre tipos de trabalho personalizados, consulte os tópicos da ajuda sobre o tipo de trabalho.

Para localizar o tipo de trabalho de um trabalho, use o `Get-Job` cmdlet. `Get-Job` retorna objetos de trabalho diferentes para diferentes tipos de trabalhos. O valor da propriedade **PSJobTypeName** dos objetos de trabalho que `Get-Job` retornam indica o tipo de trabalho.

A tabela a seguir lista os tipos de trabalho que vêm com o PowerShell.

|    Tipo de Trabalho    |                       Descrição                        |
| -------------- | -------------------------------------------------------- |
| BackgroundJob  | Iniciado usando o `Start-Job` cmdlet.                    |
| RemoteJob      | Iniciado usando o parâmetro **AsJob** do             |
|                | cmdlet `Invoke-Command`.                                 |
| PSWorkflowJob  | Iniciado usando o parâmetro **AsJob** de um fluxo de trabalho.     |
| PSScheduledJob | Uma instância de um trabalho agendado iniciado por um gatilho de trabalho. |
| CIMJob         | Iniciado usando o parâmetro **AsJob** de um cmdlet a partir de um |
|                | Módulo CDXML.                                            |
| WMIJob         | Iniciado usando o parâmetro **AsJob** de um cmdlet a partir de um |
|                | Módulo WMI.                                              |
| PSEventJob     | Criado usando `Register-ObjectEvent` e especificando um    |
|                | ação com o parâmetro **Action** .                    |

Observação: antes de usar o `Get-Job` cmdlet para obter trabalhos de um tipo específico, verifique se o módulo que adiciona o tipo de trabalho é importado para a sessão atual.
Caso contrário, `Get-Job` o não obterá trabalhos desse tipo.

## <a name="examples"></a>Exemplos

Os comandos a seguir criam um trabalho em segundo plano local, um trabalho de segundo plano remoto, um trabalho de fluxo e um trabalho agendado. Em seguida, ele usa o `Get-Job` cmdlet para obter os trabalhos. `Get-Job` Não Obtém o trabalho agendado, mas obtém todas as instâncias iniciadas do trabalho agendado.

Inicie um trabalho em segundo plano no computador local.

```powershell
PS> Start-Job -Name LocalData {Get-Process}

Id Name        PSJobTypeName   State   HasMoreData   Location   Command
-- ----        -------------   -----   -----------   --------   -------
2  LocalData   BackgroundJob   Running        True   localhost  Get-Process
```

Iniciar um trabalho em segundo plano executado em um computador remoto.

```powershell
PS> Invoke-Command -ComputerName Server01 {Get-Process} `
-AsJob -JobName RemoteData

Id  Name        PSJobTypeName  State   HasMoreData   Location   Command
--  ----        -------------  -----   -----------   --------   -------
2   RemoteData  RemoteJob      Running        True   Server01   Get-Process
```

Crie um trabalho agendado

```powershell
PS>  Register-ScheduledJob -Name ScheduledJob -ScriptBlock `
 {Get-Process} -Trigger (New-JobTrigger -Once -At "3 PM")

Id         Name            JobTriggers     Command       Enabled
--         ----            -----------     -------       -------
1          ScheduledJob    1               Get-Process   True
```

Crie um fluxo de trabalho.

```powershell
PS> workflow Test-Workflow {Get-Process}
```

Execute o fluxo de trabalho como uma tarefa.

```powershell

PS> Test-Workflow -AsJob -JobName TestWFJob

Id  Name       PSJobTypeName   State   HasMoreData   Location   Command
--  ----       -------------   -----   -----------   --------   -------
2   TestWFJob  PSWorkflowJob   NotStarted     True   localhost  Get-Process
```

Obter os trabalhos. O `Get-Job` comando não obtém trabalhos agendados, mas obtém instâncias do trabalho agendado que são iniciados.

```powershell
PS> Get-Job

Id  Name         PSJobTypeName  State     HasMoreData  Location  Command
--  ----         -------------  -----     -----------  --------  -------
2   LocalData    BackgroundJob  Completed True         localhost Get-Process
4   RemoteData   RemoteJob      Completed True         Server01  Get-Process
6   TestWFJob    PSWorkflowJob  Completed True         localhost WorkflowJob
8   ScheduledJob PSScheduledJob Completed True         localhost Get-Process
```

Para obter trabalhos agendados, use o `Get-ScheduledJob` cmdlet.

```powershell
PS> Get-ScheduledJob

Id         Name            JobTriggers     Command       Enabled
--         ----            -----------     -------       -------
1          ScheduledJob    1               Get-Process   True
```

## <a name="see-also"></a>Consulte também

- [about_Jobs](about_Jobs.md)
- [about_Remote_Jobs](about_Remote_Jobs.md)
- [about_Thread_Jobs](about_Thread_Jobs.md)
- [about_Remote](about_Remote.md)
- [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)
- [Start-Job](xref:Microsoft.PowerShell.Core.Start-Job)
- [Get-Job](xref:Microsoft.PowerShell.Core.Get-Job)
- [Wait-Job](xref:Microsoft.PowerShell.Core.Wait-Job)
- [Stop-Job](xref:Microsoft.PowerShell.Core.Stop-Job)
- [Remove-Job](xref:Microsoft.PowerShell.Core.Remove-Job)
- [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)
- [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)
- [Exit-PSSession](xref:Microsoft.PowerShell.Core.Exit-PSSession)
