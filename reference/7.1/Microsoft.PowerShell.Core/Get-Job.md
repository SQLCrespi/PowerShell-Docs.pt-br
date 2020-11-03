---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-job?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Job
ms.openlocfilehash: 8a92e07746e86d4b0b84049f1f479a82c85e5e6f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194762"
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

### CommandParameterSet

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Command <String[]>] [<CommonParameters>]
```

### FilterParameterSet

```
Get-Job [-Filter] <Hashtable> [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Get-Job** obtém os objetos que representam os trabalhos em segundo plano que foram iniciados na sessão atual. Você pode usar **Get-Job** para obter trabalhos que foram iniciados usando o cmdlet Start-Job ou usando o parâmetro *AsJob* de qualquer cmdlet.

Sem parâmetros, um comando **Get-Job** Obtém todos os trabalhos na sessão atual.
Você pode usar os parâmetros de **Get-Job** para obter trabalhos específicos.

O objeto de trabalho que o cmdlet **Get-Job** retorna contém informações úteis sobre o trabalho, mas não contém os resultados deste. Para obter os resultados, use o cmdlet Receive-Job.

Um trabalho em segundo plano do PowerShell é um comando que é executado em segundo plano sem interagir com a sessão atual. Normalmente, você usa um trabalho em segundo plano para executar um comando complexo que leva muito tempo para ser concluído. Para obter mais informações sobre trabalhos em segundo plano no PowerShell, consulte about_Jobs.

A partir do Windows PowerShell 3.0, o cmdlet **Get-Job** também obtém os tipos de trabalho personalizados, como trabalhos do fluxo de trabalho e instâncias dos trabalhos agendados. Para localizar o tipo de um trabalho, use a propriedade **PSJobTypeName** do trabalho em questão.

Para habilitar o **Get-Job** para obter um tipo de trabalho personalizado, importe o módulo que dá suporte ao tipo de trabalho personalizado na sessão antes de executar um comando **Get-Job** , seja usando o cmdlet Import-Module ou usando ou obtendo um cmdlet no módulo. Para obter informações sobre um tipo específico de trabalho personalizado, consulte a documentação do recurso de tipo de trabalho personalizado.

## EXEMPLOS

### Exemplo 1: obter todos os trabalhos em segundo plano iniciados na sessão atual

```powershell
Get-Job
```

Esse comando obtém todos os trabalhos em segundo plano iniciados na sessão atual.
Ele não inclui trabalhos criados em outras sessões, mesmo se os trabalhos forem executados no computador local.

### Exemplo 2: parar um trabalho usando uma ID de instância

Esses comandos mostram como obter o identificador de instância de um trabalho e, em seguida, usá-lo para interromper esse trabalho.
Ao contrário do nome de um determinado trabalho, que não é exclusivo, o identificador da instância é.

```powershell
$j = Get-Job -Name Job1
$ID = $j.InstanceID
$ID
```

```Output
Guid
----
03c3232e-1d23-453b-a6f4-ed73c9e29d55
```

```powershell
Stop-Job -InstanceId $ID
```

O primeiro comando usa o cmdlet **Get-Job** para obter um trabalho. Ele usa o parâmetro *Name* para identificar o trabalho. O comando armazena o objeto de trabalho que o **Get-Job** retorna na variável $j. Neste exemplo, há apenas um trabalho com o nome especificado.

O segundo comando obtém a propriedade **InstanceId** do objeto na variável $j e o armazena na variável $ID.

O terceiro comando exibe o valor da variável $ID.

O quarto comando usa Stop-Job cmdlet para parar o trabalho. Ele usa o parâmetro *InstanceId* para identificar o trabalho e a variável $ID para representar o identificador da instância do trabalho.

### Exemplo 3: obter trabalhos que incluem um comando específico

```powershell
Get-Job -Command "*get-process*"
```

Esse comando obtém os trabalhos no sistema que incluem um comando Get-Process. O comando usa o parâmetro *Command* do **Get-Job** para limitar os trabalhos recuperados. O comando usa caracteres curinga (*) para obter trabalhos que incluem um comando **Get-Process** em qualquer lugar na cadeia de caracteres de comando.

### Exemplo 4: obter trabalhos que incluem um comando específico usando o pipeline

```powershell
"*get-process*" | Get-Job
```

Como o comando no exemplo anterior, esse comando obtém os trabalhos no sistema que incluem um comando **Get-Process** . O comando usa um operador de pipeline (|) para enviar uma cadeia de caracteres, entre aspas, para o cmdlet **Get-Job** . Ele é o equivalente do comando anterior.

### Exemplo 5: obter trabalhos que não foram iniciados

```powershell
Get-Job -State NotStarted
```

Este comando obtém apenas os trabalhos que foram criados, mas ainda não foi iniciados.
Isso inclui trabalhos agendados para execução no futuro e aqueles ainda não foram agendados.

### Exemplo 6: obter trabalhos que não foram atribuídos a um nome

```powershell
Get-Job -Name Job*
```

Esse comando obtém todos os trabalhos que têm nomes de trabalho que começam com o trabalho.
Como \<number\> o trabalho é o nome padrão de um trabalho, esse comando obtém todos os trabalhos que não têm um nome explicitamente atribuído.

### Exemplo 7: usar um objeto de trabalho para representar o trabalho em um comando

Este exemplo mostra como usar o **Get-Job** para obter um objeto de trabalho e, em seguida, ele mostra como usar o objeto de trabalho para representar esse trabalho em um comando.

```powershell
Start-Job -ScriptBlock {Get-Process} -Name MyJob
$j = Get-Job -Name MyJob
$j
```

```Output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
6      MyJob           BackgroundJob   Completed     True            localhost            Get-Process
```

```powershell
Receive-Job -Job $j
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    124       4    13572      12080    59            1140 audiodg
    783      16    11428      13636   100             548 CcmExec
     96       4     4252       3764    59            3856 ccmsetup
...
```

O primeiro comando usa o cmdlet **Start-Job** para iniciar um trabalho em segundo plano que executa um comando **Get-Process** no computador local. O comando usa o parâmetro *Name* do **Start-Job** para atribuir um nome amigável para o trabalho.

O segundo comando usa o Get-Job para obter o trabalho. Ele usa o parâmetro *Name* do **Get-Job** para identificar o trabalho. O comando salva o objeto de trabalho resultante na variável $j.

O terceiro comando exibe o valor do objeto de trabalho na variável $j. O valor da propriedade **State** mostra que o trabalho foi concluído. O valor da propriedade **HasMoreData** mostra que há resultados disponíveis do trabalho que ainda não foram recuperados.

O quarto comando usa o cmdlet **Receive-Job** para obter os resultados do trabalho. Ele usa o objeto de trabalho na variável $j para representar o trabalho. Você também pode usar um operador de pipeline para enviar um objeto de trabalho para **Receive-Job** .

### Exemplo 8: obter todos os trabalhos, incluindo trabalhos iniciados por um método diferente

Este exemplo demonstra que o cmdlet **Get-Job** pode obter todos os trabalhos que foram iniciados na sessão atual, mesmo que eles tenham sido iniciados usando métodos diferentes.

```powershell
Start-Job -ScriptBlock {Get-EventLog System}
Invoke-Command -ComputerName S1 -ScriptBlock {Get-EventLog System} -AsJob
Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Get-Job
```

```Output
Id     Name       PSJobTypeName   State         HasMoreData     Location        Command
--     ----       -------------   -----         -----------     --------        -------
1      Job1       BackgroundJob   Running       True            localhost       Get-EventLog System
2      Job2       RemoteJob       Running       True            S1              Get-EventLog System
```

```powershell
Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
```

```Output
Id    Name     PSJobTypeName  State      HasMoreData   Location   Command
--    ----     -------------  -----      -----------   -------    -------
4     Job4     BackgroundJob  Running    True          localhost  Get-Eventlog System
```

O primeiro comando usa o cmdlet **Start-Job** para iniciar um trabalho no computador local.

O segundo comando usa o parâmetro *AsJob* do cmdlet **Invoke-Command** para iniciar um trabalho no computador S1. Embora os comandos do trabalho sejam executados no computador remoto, o objeto de trabalho é criado no computador local, para que você use comandos locais para gerenciar o trabalho.

O terceiro comando usa o cmdlet **Invoke-Command** para executar um comando **Start-Job** no computador S2. Usando esse método, o objeto de trabalho é criado no computador remoto, portanto, você usa comandos remotos para gerenciar o trabalho.

O quarto comando usa o **Get-Job** para obter os trabalhos armazenados no computador local. A propriedade **PSJobTypeName** dos trabalhos, apresentada no Windows PowerShell 3,0, mostra que o trabalho local iniciado usando o cmdlet **Start-Job** é um trabalho em segundo plano e o trabalho iniciado em uma sessão remota usando o cmdlet **Invoke-Command** é um trabalho remoto.

O quinto comando usa **Invoke-Command** para executar um comando **Get-Job** no computador S2. A saída de exemplo mostra os resultados do comando Get-Job. No computador S2, o trabalho parece ser um trabalho local. O nome do computador é localhost e o tipo de trabalho é um trabalho em segundo plano.

Para obter mais informações sobre como executar trabalhos em segundo plano em computadores remotos, consulte about_Remote_Jobs.

### Exemplo 9: investigar um trabalho com falha

```powershell
Start-Job -ScriptBlock {Get-Process}
```

```Output
Id     Name       PSJobTypeName   State       HasMoreData     Location             Command
--     ----       -------------   -----       -----------     --------             -------
1      Job1       BackgroundJob   Failed      False           localhost            Get-Process
```

```powershell
(Get-Job).JobStateInfo | Format-List -Property *
```

```Output
State  : Failed
Reason :
```

```powershell
Get-Job | Format-List -Property *
```

```Output
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
```

```powershell
(Get-Job -Name job2).JobStateInfo.Reason
```

```Output
Connecting to remote server using WSManCreateShellEx api failed. The async callback gave the following error message: Access is denied.

For information about requirements for remoting in PowerShell, see about_Remote_Requirements. For
troubleshooting tips, see about_Remote_Troubleshooting.
```

Este comando mostra como usar o objeto de trabalho que o **Get-Job** retorna para investigar por que um trabalho falhou.
Ele também mostra como obter os trabalhos filhos de cada trabalho.

O primeiro comando usa o cmdlet **Start-Job** para iniciar um trabalho no computador local. O objeto de trabalho que o **Start-Job** retorna mostra que o trabalho falhou. Falha no valor da propriedade de **estado** .

O segundo comando usa o cmdlet **Get-Job** para obter o trabalho. O segundo comando usa o método de ponto para exibir o valor da propriedade **JobStateInfo** do objeto. Ele usa um operador de pipeline para enviar o objeto na propriedade **JobStateInfo** para o cmdlet Format-List, que formata todas as propriedades do objeto (*) em uma lista. O resultado do comando **Format-List** mostra que o valor da propriedade **Reason** do trabalho está em branco.

O terceiro comando investiga mais. Ele usa um comando **Get-Job** para obter o trabalho e, em seguida, usa um operador de pipeline para enviar todo o objeto de trabalho para o cmdlet **Format-List** , que exibe todas as propriedades do trabalho em uma lista. A exibição de todas as propriedades no objeto de trabalho mostra que o trabalho contém um trabalho filho chamado Job2.

O quarto comando usa o **Get-Job** para obter o objeto de trabalho que representa o trabalho filho Trabalho2. Esse é o trabalho no qual o comando foi realmente executado. Ele usa o método dot para obter a propriedade **Reason** da propriedade **JobStateInfo** . O resultado mostra que o trabalho falhou devido a um erro de acesso negado. Nesse caso, o usuário esqueceu de usar a opção Executar como administrador ao iniciar o PowerShell. como os trabalhos em segundo plano usam os recursos de comunicação remota do PowerShell, o computador deve ser configurado para comunicação remota para executar um trabalho, mesmo quando o trabalho é executado no computador local.

### Exemplo 10: obter resultados filtrados

Este exemplo mostra como usar o parâmetro *Filter* para obter uma tarefa de fluxo de trabalho.
O parâmetro *Filter* , introduzido no Windows PowerShell 3.0, é válido somente em tipos de trabalho personalizados, como tarefas de fluxo de trabalho e trabalhos agendados.

```powershell
Workflow WFProcess {Get-Process}
WFProcess -AsJob -JobName WFProcessJob -PSPrivateMetadata @{MyCustomId = 92107}
Get-Job -Filter @{MyCustomId = 92107}
```

```Output
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
1      WFProcessJob    Completed     True            localhost            WFProcess
```

O primeiro comando usa a palavra-chave **Workflow** para criar o fluxo de trabalho WFProcess.

O segundo comando usa o parâmetro *AsJob* do fluxo de trabalho do amWFProcess para executar o workflow como uma tarefa em segundo plano. Ele usa o parâmetro *JobName* do fluxo de trabalho para especificar um nome para o trabalho e o parâmetro *PSPrivateMetadata* do fluxo de trabalho para especificar um identificador personalizado.

O terceiro comando usa o parâmetro *Filter* do cmdlet **Get-Job** para obter o trabalho usando o identificador personalizado que foi especificado no parâmetro *PSPrivateMetadata* .

### Exemplo 11: obter informações sobre trabalhos filho

Este exemplo mostra o efeito do uso dos parâmetros *IncludeChildJob* e *ChildJobState* do cmdlet **Get-Job** .

```powershell
Get-Job
```

```Output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost            .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02   .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
```

```powershell
Get-Job -IncludeChildJob
```

```Output
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
```

```powershell
Get-Job -Name Job4 -ChildJobState Failed
```

```Output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost           .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02  .\Get-Archive.ps1
5      Job5                            Failed        False           Server01            .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
```

```powershell
(Get-Job -Name Job5).JobStateInfo.Reason
```

```Output
Connecting to remote server Server01 failed with the following error message:
Access is denied.
For more information, see the about_Remote_Troubleshooting Help topic.
```

O primeiro comando obtém os trabalhos presentes na sessão atual. A saída inclui um trabalho em segundo plano, um trabalho remoto e várias instâncias de um trabalho agendado. O trabalho remoto, Trabalho4, parece ter falhado.

O segundo comando usa o parâmetro *IncludeChildJob* do cmdlet **Get-Job** . A saída adiciona os trabalhos filho de todos os trabalhos que têm trabalhos filho. Nesse caso, a saída revisada mostra que apenas o trabalho filho Job5 de Job4 falhou.

O terceiro comando usa o parâmetro *ChildJobState* com um valor de Failed. a saída inclui todos os trabalhos pai e somente os trabalhos filho que falharam.

O quarto comando usa a propriedade **JobStateInfo** de trabalhos e sua propriedade **Reason** para descobrir por que Job5 falhou.

## PARAMETERS

### -Depois de

Obtém os trabalhos concluídos após a data e hora especificadas. Insira um objeto **DateTime** , como um retornado pelo cmdlet Get-Date ou uma cadeia de caracteres que possa ser convertida em um objeto **DateTime** , como `Dec 1, 2012 2:00 AM` ou `11/06` .

Este parâmetro funciona somente em tipos de trabalho personalizados, como os de fluxo de trabalho e os trabalhos agendados que têm uma propriedade **EndTime** . Ele não funciona em trabalhos em segundo plano padrão, como aqueles criados usando o cmdlet **Start-Job** . Para obter informações sobre o suporte para este parâmetro, consulte o tópico da Ajuda para o tipo de trabalho em questão.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
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

Este parâmetro funciona somente em tipos de trabalho personalizados, como os de fluxo de trabalho e os trabalhos agendados que têm uma propriedade **EndTime** . Ele não funciona em trabalhos em segundo plano padrão, como aqueles criados usando o cmdlet **Start-Job** . Para obter informações sobre o suporte para este parâmetro, consulte o tópico da Ajuda para o tipo de trabalho em questão.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
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
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
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

Quando você usa o cmdlet **Receive-Job** , ele exclui de seu armazenamento específico da sessão na memória, os resultados retornados por ele. Quando ele retorna todos os resultados do trabalho na sessão atual, ele define o valor da propriedade **HasMoreData** do trabalho como $false) para indicar que ele não tem mais resultados para o trabalho na sessão atual. Use o parâmetro *Keep* de **Receive-Job** para evitar que o **Receive-Job** exclua resultados ou altere o valor da propriedade **HasMoreData** . Para obter mais informações, digite `Get-Help Receive-Job`.

A propriedade **HasMoreData** é específica para a sessão atual. Se os resultados de um tipo de trabalho personalizado forem salvos fora da sessão, como o tipo de trabalho agendado, que salva os resultados do trabalho no disco, você poderá usar o cmdlet **Receive-Job** em uma sessão diferente para obter os resultados do trabalho novamente, mesmo que o valor de **HasMoreData** seja $false. Para obter mais informações, consulte os tópicos da ajuda para o tipo de trabalho personalizado.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Boolean
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
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
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
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
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
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

[Start-Job](Start-Job.md)

[Stop-Job](Stop-Job.md)

[Wait-Job](Wait-Job.md)

