---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Job
ms.openlocfilehash: 0b9c76ca1e26adaa244473366c2eabdaaa28452c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193324"
---
# Get-Job

## SINOPSE
Obtém trabalhos em segundo plano do PowerShell que estão em execução na sessão atual.

## SYNTAX

### SessionIdParameterSet (padrão)

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [[-Id] <Int32[]>] [<CommonParameters>]
```

### CommandParameterSet

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Command <String[]>] [<CommonParameters>]
```

### InstanceIdParameterSet

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### NameParameterSet

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Name] <String[]> [<CommonParameters>]
```

### StateParameterSet

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-State] <JobState> [<CommonParameters>]
```

### FilterParameterSet

```
Get-Job [-Filter] <Hashtable> [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Get-Job** obtém os objetos que representam os trabalhos em segundo plano que foram iniciados na sessão atual.
Você pode usar **Get-Job** para obter trabalhos que foram iniciados usando o cmdlet Start-Job ou usando o parâmetro *AsJob* de qualquer cmdlet.

Sem parâmetros, um comando **Get-Job** Obtém todos os trabalhos na sessão atual.
Você pode usar os parâmetros de **Get-Job** para obter trabalhos específicos.

O objeto de trabalho que o cmdlet **Get-Job** retorna contém informações úteis sobre o trabalho, mas não contém os resultados deste.
Para obter os resultados, use o cmdlet Receive-Job.

Um trabalho em segundo plano do Windows PowerShell é um comando que é executado em segundo plano sem interagir com a sessão atual.
Normalmente, você usa um trabalho em segundo plano para executar um comando complexo que leva muito tempo para ser concluído.
Para obter mais informações sobre trabalhos em segundo plano no Windows PowerShell, consulte about_Jobs.

A partir do Windows PowerShell 3.0, o cmdlet **Get-Job** também obtém os tipos de trabalho personalizados, como trabalhos do fluxo de trabalho e instâncias dos trabalhos agendados.
Para localizar o tipo de um trabalho, use a propriedade **PSJobTypeName** do trabalho em questão.

Para habilitar o **Get-Job** para obter um tipo de trabalho personalizado, importe o módulo que dá suporte ao tipo de trabalho personalizado na sessão antes de executar um comando **Get-Job** , seja usando o cmdlet Import-Module ou usando ou obtendo um cmdlet no módulo.
Para obter informações sobre um tipo específico de trabalho personalizado, consulte a documentação do recurso de tipo de trabalho personalizado.

## EXEMPLOS

### Exemplo 1: obter todos os trabalhos em segundo plano iniciados na sessão atual

```
PS C:\> Get-Job
```

Esse comando obtém todos os trabalhos em segundo plano iniciados na sessão atual.
Ele não inclui trabalhos criados em outras sessões, mesmo se os trabalhos forem executados no computador local.

### Exemplo 2: parar um trabalho usando uma ID de instância

```
The first command uses the **Get-Job** cmdlet to get a job. It uses the *Name* parameter to identify the job. The command stores the job object that **Get-Job** returns in the $j variable. In this example, there is only one job with the specified name.
PS C:\> $j = Get-Job -Name Job1

The second command gets the **InstanceId** property of the object in the $j variable and stores it in the $ID variable.
PS C:\> $ID = $j.InstanceID

The third command displays the value of the $ID variable.
PS C:\> $ID

Guid
----
03c3232e-1d23-453b-a6f4-ed73c9e29d55

The fourth command uses Stop-Job cmdlet to stop the job. It uses the *InstanceId* parameter to identify the job and $ID variable to represent the instance ID of the job.
PS C:\> Stop-Job -InstanceId $ID
```

Esses comandos mostram como obter o identificador de instância de um trabalho e, em seguida, usá-lo para interromper esse trabalho.
Ao contrário do nome de um determinado trabalho, que não é exclusivo, o identificador da instância é.

### Exemplo 3: obter trabalhos que incluem um comando específico

```
PS C:\> Get-Job -Command "*get-process*"
```

Esse comando obtém os trabalhos no sistema que incluem um comando Get-Process.
O comando usa o parâmetro *Command* do **Get-Job** para limitar os trabalhos recuperados.
O comando usa caracteres curinga (*) para obter trabalhos que incluem um comando **Get-Process** em qualquer lugar na cadeia de caracteres de comando.

### Exemplo 4: obter trabalhos que incluem um comando específico usando o pipeline

```
PS C:\> "*get-process*" | Get-Job
```

Como o comando no exemplo anterior, esse comando obtém os trabalhos no sistema que incluem um comando **Get-Process** .
O comando usa um operador de pipeline (|) para enviar uma cadeia de caracteres, entre aspas, para o cmdlet **Get-Job** .
Ele é o equivalente do comando anterior.

### Exemplo 5: obter trabalhos que não foram iniciados

```
PS C:\> Get-Job -State NotStarted
```

Este comando obtém apenas os trabalhos que foram criados, mas ainda não foi iniciados.
Isso inclui trabalhos agendados para execução no futuro e aqueles ainda não foram agendados.

### Exemplo 6: obter trabalhos que não foram atribuídos a um nome

```
PS C:\> Get-Job -Name Job*
```

Esse comando obtém todos os trabalhos que têm nomes de trabalho que começam com o trabalho.
Como \<number\> o trabalho é o nome padrão de um trabalho, esse comando obtém todos os trabalhos que não têm um nome explicitamente atribuído.

### Exemplo 7: usar um objeto de trabalho para representar o trabalho em um comando

```
The first command uses the **Start-Job** cmdlet to start a background job that runs a **Get-Process** command on the local computer. The command uses the *Name* parameter of **Start-Job** to assign a friendly name to the job.
PS C:\> Start-Job -ScriptBlock {Get-Process} -Name MyJob

The second command uses Get-Job to get the job. It uses the *Name* parameter of **Get-Job** to identify the job. The command saves the resulting job object in the $j variable.
PS C:\> $j = Get-Job -Name MyJob

The third command displays the value of the job object in the $j variable. The value of the **State** property shows that the job is completed. The value of the **HasMoreData** property shows that there are results available from the job that have not yet been retrieved.
PS C:\> $j
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
6      MyJob           BackgroundJob   Completed     True            localhost            Get-Process

The fourth command uses the **Receive-Job** cmdlet to get the results of the job. It uses the job object in the $j variable to represent the job. You can also use a pipeline operator to send a job object to **Receive-Job**.
PS C:\> Receive-Job -Job $j
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    124       4    13572      12080    59            1140 audiodg
    783      16    11428      13636   100             548 CcmExec
     96       4     4252       3764    59            3856 ccmsetup
...
```

Este exemplo mostra como usar o **Get-Job** para obter um objeto de trabalho e, em seguida, ele mostra como usar o objeto de trabalho para representar esse trabalho em um comando.

### Exemplo 8: obter todos os trabalhos, incluindo trabalhos iniciados por um método diferente

```
The first command uses the **Start-Job** cmdlet to start a job on the local computer.
PS C:\> Start-Job -ScriptBlock {Get-EventLog System}

The second command uses the *AsJob* parameter of the **Invoke-Command** cmdlet to start a job on the S1 computer. Even though the commands in the job run on the remote computer, the job object is created on the local computer, so you use local commands to manage the job.
PS C:\> Invoke-Command -ComputerName S1 -ScriptBlock {Get-EventLog System} -AsJob

The third command uses the **Invoke-Command** cmdlet to run a **Start-Job** command on the S2 computer. By using this method, the job object is created on the remote computer, so you use remote commands to manage the job.
PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}

The fourth command uses **Get-Job** to get the jobs stored on the local computer. The **PSJobTypeName** property of jobs, introduced in Windows PowerShell 3.0, shows that the local job started by using the **Start-Job** cmdlet is a background job and the job started in a remote session by using the **Invoke-Command** cmdlet is a remote job.
PS C:\> Get-Job
Id     Name       PSJobTypeName   State         HasMoreData     Location        Command
--     ----       -------------   -----         -----------     --------        -------
1      Job1       BackgroundJob   Running       True            localhost       Get-EventLog System
2      Job2       RemoteJob       Running       True            S1              Get-EventLog System

The fifth command uses **Invoke-Command** to run a **Get-Job** command on the S2 computer.The sample output shows the results of the Get-Job command. On the S2 computer, the job appears to be a local job. The computer name is localhost and the job type is a background job.For more information about how to run background jobs on remote computers, see about_Remote_Jobs.
PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Id    Name     PSJobTypeName  State      HasMoreData   Location   Command
--    ----     -------------  -----      -----------   -------    -------
4     Job4     BackgroundJob  Running    True          localhost  Get-Eventlog System
```

Este exemplo demonstra que o cmdlet **Get-Job** pode obter todos os trabalhos que foram iniciados na sessão atual, mesmo que eles tenham sido iniciados usando métodos diferentes.

### Exemplo 9: investigar um trabalho com falha

```
The first command uses the **Start-Job** cmdlet to start a job on the local computer. The job object that **Start-Job** returns shows that the job failed. The value of the **State** property is Failed.
PS C:\> Start-Job -ScriptBlock {Get-Process}
Id     Name       PSJobTypeName   State       HasMoreData     Location             Command
--     ----       -------------   -----       -----------     --------             -------
1      Job1       BackgroundJob   Failed      False           localhost            Get-Process

The second command uses the **Get-Job** cmdlet to get the job. The command uses the dot method to get the value of the **JobStateInfo** property of the object. It uses a pipeline operator to send the object in the **JobStateInfo** property to the Format-List cmdlet, which formats all of the properties of the object (*) in a list.The result of the **Format-List** command shows that the value of the **Reason** property of the job is blank.
PS C:\> (Get-Job).JobStateInfo | Format-List -Property *
State  : Failed
Reason :

The third command investigates more. It uses a **Get-Job** command to get the job and then uses a pipeline operator to send the whole job object to the **Format-List** cmdlet, which displays all of the properties of the job in a list.The display of all properties in the job object shows that the job contains a child job named Job2.
PS C:\> Get-Job | Format-List -Property *
HasMoreData   : False
StatusMessage :
Location      : localhost
Command       : get-process
JobStateInfo  : Failed
Finished      : System.Threading.ManualReset
EventInstanceId    : fb792295-1318-4f5d-8ac8-8a89c5261507
Id            : 1
Name          : Job1
ChildJobs     : {Job2}
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
StateChanged  :

The fourth command uses **Get-Job** to get the job object that represents the Job2 child job. This is the job in which the command actually ran. It uses the dot method to get the **Reason** property of the **JobStateInfo** property.The result shows that the job failed because of an Access Denied error. In this case, the user forgot to use the Run as administrator option when starting Windows PowerShell.Because background jobs use the remoting features of Windows PowerShell, the computer must be configured for remoting to run a job, even when the job runs on the local computer.For information about requirements for remoting in Windows PowerShell, see about_Remote_Requirements. For troubleshooting tips, see about_Remote_Troubleshooting.
PS C:\> (Get-Job -Name job2).JobStateInfo.Reason
Connecting to remote server using WSManCreateShellEx api failed. The async callback gave the following error message: Access is denied.
```

Este comando mostra como usar o objeto de trabalho que o **Get-Job** retorna para investigar por que um trabalho falhou.
Ele também mostra como obter os trabalhos filhos de cada trabalho.

### Exemplo 10: obter resultados filtrados

```
The first command uses the **Workflow** keyword to create the WFProcess workflow.
PS C:\> Workflow WFProcess {Get-Process}

The second command uses the *AsJob* parameter of the WFProcess workflow to run the workflow as a background job. It uses the *JobName* parameter of the workflow to specify a name for the job, and the *PSPrivateMetadata* parameter of the workflow to specify a custom ID.
PS C:\> WFProcess -AsJob -JobName WFProcessJob -PSPrivateMetadata @{MyCustomId = 92107}

The third command uses the *Filter* parameter of **Get-Job** to get the job by custom ID that was specified in the *PSPrivateMetadata* parameter.
PS C:\> Get-Job -Filter @{MyCustomId = 92107}
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
1      WFProcessJob    Completed     True            localhost            WFProcess
```

Este exemplo mostra como usar o parâmetro *Filter* para obter uma tarefa de fluxo de trabalho.
O parâmetro *Filter* , introduzido no Windows PowerShell 3.0, é válido somente em tipos de trabalho personalizados, como tarefas de fluxo de trabalho e trabalhos agendados.

### Exemplo 11: obter informações sobre trabalhos filho

```
The first command gets the jobs in the current session. The output includes a background job, a remote job and several instances of a scheduled job. The remote job, Job4, appears to have failed.
PS C:\> Get-Job
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost            .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02   .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

The second command uses the *IncludeChildJob* parameter of **Get-Job**. The output adds the child jobs of all jobs that have child jobs.In this case, the revised output shows that only the Job5 child job of Job4 failed.
PS C:\> Get-Job -IncludeChildJob
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost           .\Get-Archive.ps1
3      Job3                            Completed     True            localhost           .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02  .\Get-Archive.ps1
5      Job5                            Failed        False           Server01            .\Get-Archive.ps1
6      Job6                            Completed     True            Server02            .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

The third command uses the *ChildJobState* parameter with a value of Failed.The output includes all parent jobs and only the child jobs that failed.
PS C:\> Get-Job -Name Job4 -ChildJobState Failed
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost           .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02  .\Get-Archive.ps1
5      Job5                            Failed        False           Server01            .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

The fifth command uses the **JobStateInfo** property of jobs and its **Reason** property to discover why Job5 failed.
PS C:\> (Get-Job -Name Job5).JobStateInfo.Reason
Connecting to remote server Server01 failed with the following error message:
Access is denied.
For more information, see the about_Remote_Troubleshooting Help topic.
```

Este exemplo mostra o efeito do uso dos parâmetros *IncludeChildJob* e *ChildJobState* do cmdlet **Get-Job** .

## PARAMETERS

### -Depois de

Obtém os trabalhos concluídos após a data e hora especificadas.
Insira um objeto **DateTime** , como um retornado pelo cmdlet Get-Date ou uma cadeia de caracteres que possa ser convertida em um objeto **DateTime** , como `Dec 1, 2012 2:00 AM` ou `11/06` .

Este parâmetro funciona somente em tipos de trabalho personalizados, como os de fluxo de trabalho e os trabalhos agendados que têm uma propriedade **EndTime** .
Ele não funciona em trabalhos em segundo plano padrão, como aqueles criados usando o cmdlet **Start-Job** .
Para obter informações sobre o suporte para este parâmetro, consulte o tópico da Ajuda para o tipo de trabalho em questão.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Antes de

Obtém os trabalhos concluídos antes da data e hora especificadas.
Insira um objeto **DateTime** .

Este parâmetro funciona somente em tipos de trabalho personalizados, como os de fluxo de trabalho e os trabalhos agendados que têm uma propriedade **EndTime** .
Ele não funciona em trabalhos em segundo plano padrão, como aqueles criados usando o cmdlet **Start-Job** .
Para obter informações sobre o suporte para este parâmetro, consulte o tópico da Ajuda para o tipo de trabalho em questão.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ChildJobState

Obtém somente os trabalhos filhos que apresentam o estado especificado.
Os valores aceitáveis para esse parâmetro são:

- NotStarted
- Executando
- Concluído
- Falhou
- Parado
- Bloqueado
- Suspenso
- Desconectado
- Suspensão
- Parando

Por padrão, o **Get-Job** não obtém nenhum trabalho filho.
Usando o parâmetro *IncludeChildJob* , **Get-Job** Obtém todos os trabalhos filho.
Se você usar o parâmetro *ChildJobState* , o parâmetro *IncludeChildJob* não tem nenhum efeito.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Command

Especifica uma matriz de comandos como cadeias de caracteres.
Esse cmdlet obtém os trabalhos que incluem os comandos especificados.
O padrão é obter todos os trabalhos.
Você pode usar caracteres curinga para especificar um padrão de comando.

```yaml
Type: System.String[]
Parameter Sets: CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Filter

Especifica uma tabela de hash de condições.
Esse cmdlet obtém trabalhos que atendem a todas as condições.
Insira uma tabela de hash na qual as chaves são propriedades do trabalho e os valores são valores de propriedade do trabalho.

Este parâmetro funciona somente em tipos de trabalho personalizados, como os de fluxo de trabalho e os trabalhos agendados.
Ele não funciona em trabalhos em segundo plano padrão, como aqueles criados usando o cmdlet **Start-Job** .
Para obter informações sobre o suporte para este parâmetro, consulte o tópico da Ajuda para o tipo de trabalho em questão.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: FilterParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HasMoreData

Indica se este cmdlet obtém apenas os trabalhos que têm o valor da propriedade **HasMoreData** especificado.
A propriedade **HasMoreData** indica se todos os resultados do trabalho foram recebidos na sessão atual.
Para obter trabalhos que têm mais resultados, especifique um valor de $True.
Para obter trabalhos que não têm mais resultados, especifique um valor de $False.

Para obter os resultados de um trabalho, use o cmdlet Receive-Job.

Quando você usa o cmdlet **Receive-Job** , ele exclui de seu armazenamento específico da sessão na memória, os resultados retornados por ele.
Quando ele retorna todos os resultados do trabalho na sessão atual, ele define o valor da propriedade **HasMoreData** do trabalho como $false) para indicar que ele não tem mais resultados para o trabalho na sessão atual.
Use o parâmetro *Keep* de **Receive-Job** para evitar que o **Receive-Job** exclua resultados ou altere o valor da propriedade **HasMoreData** .
Para obter mais informações, digite `Get-Help Receive-Job`.

A propriedade **HasMoreData** é específica para a sessão atual.
Se os resultados de um tipo de trabalho personalizado forem salvos fora da sessão, como o tipo de trabalho agendado, que salva os resultados do trabalho no disco, você poderá usar o cmdlet **Receive-Job** em uma sessão diferente para obter os resultados do trabalho novamente, mesmo que o valor de **HasMoreData** seja $false.
Para obter mais informações, consulte os tópicos da ajuda para o tipo de trabalho personalizado.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Boolean
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Especifica uma matriz de IDs de trabalhos que esse cmdlet obtém.

A ID é um inteiro que identifica exclusivamente o trabalho na sessão atual.
É mais fácil lembrar e digitar do que a ID da instância, mas só é exclusiva na sessão atual.
Você pode digitar uma ou mais IDs separadas por vírgulas.
Para localizar a ID de um trabalho, digite `Get-Job` sem parâmetros.

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IncludeChildJob

Indica que esse cmdlet retorna trabalhos filho, além de trabalhos pai.

Esse parâmetro é especialmente útil para a investigação de trabalhos de fluxo de trabalho, para os quais o **Get-Job** retorna um trabalho pai do contêiner, e falhas de trabalhos, porque o motivo da falha é salvo em uma propriedade do trabalho filho.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceId

Especifica uma matriz de IDs de instância dos trabalhos que esse cmdlet obtém.
O padrão é obter todos os trabalhos.

Uma ID de instância é um GUID que identifica exclusivamente o trabalho no computador.
Para localizar o identificador da instância de um trabalho, use o cmdlet **Get-Job** .

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Especifica uma matriz de nomes amigáveis de instância dos trabalhos que esse cmdlet obtém.
Insira um nome de trabalho, ou então use caracteres curinga para inserir um padrão de nome de trabalho.
Por padrão, o **Get-Job** obtém todos os trabalhos existentes na sessão atual.

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Mais recente

Especifica um número de trabalhos a serem obtidos.
Esse cmdlet obtém os trabalhos que foram encerrados mais recentemente.

O parâmetro *Newest* não classifica nem retorna os trabalhos mais recentes classificados segundo o horário de término.
Para classificar a saída, use o cmdlet Sort-Object.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Int32
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Estado

Especifica um estado de trabalho.
Esse cmdlet obtém apenas os trabalhos no estado especificado.
Os valores aceitáveis para esse parâmetro são:

- NotStarted
- Executando
- Concluído
- Falhou
- Parado
- Bloqueado
- Suspenso
- Desconectado
- Suspensão
- Parando

Por padrão, o **Get-Job** obtém todos os trabalhos existentes na sessão atual.

Para obter mais informações sobre os Estados de trabalho, consulte [Enumeração JobState](https://msdn.microsoft.com/library/system.management.automation.jobstate) na biblioteca MSDN.

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### System. Management. Automation. RemotingJob

Esse cmdlet retorna objetos que representam os trabalhos na sessão.

## OBSERVAÇÕES

* A propriedade **PSJobTypeName** dos trabalhos indica o tipo do trabalho em questão. O valor da propriedade é determinado pelo autor do tipo de trabalho. A lista a seguir mostra os tipos de trabalho comuns.

  - **BackgroundJob** .
Trabalho local iniciado usando **Start-Job** .

  - **RemoteJob** .
Trabalho iniciado em uma **PSSession** usando o parâmetro *AsJob* do cmdlet Invoke-Command.

  - **PSWorkflowJob** .
Trabalho iniciado usando o parâmetro comum *AsJob* dos fluxos de trabalho.

## LINKS RELACIONADOS

[Invoke-Command](Invoke-Command.md)

[Receive-Job](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Resume-Job](Resume-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job](Stop-Job.md)

[Suspend-Job](Suspend-Job.md)

[Wait-Job](Wait-Job.md)

[about_Jobs](About/about_Jobs.md)

[about_Job_Details](About/about_Job_Details.md)

[about_Remote_Jobs](About/about_Remote_Jobs.md)

[about_Scheduled_Jobs](../PSScheduledJob/About/about_Scheduled_Jobs.md)
