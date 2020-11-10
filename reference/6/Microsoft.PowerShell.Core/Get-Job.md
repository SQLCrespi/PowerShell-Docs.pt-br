---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-job?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Job
ms.openlocfilehash: 28fb50118e3a37aa0ee7b84aac356f7e8b6f2578
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94387559"
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

O `Get-Job` cmdlet obtém objetos que representam os trabalhos em segundo plano que foram iniciados na sessão atual. Você pode usar `Get-Job` o para obter trabalhos que foram iniciados usando o `Start-Job` cmdlet ou usando o parâmetro **AsJob** de qualquer cmdlet.

Sem parâmetros, um `Get-Job` comando obtém todos os trabalhos na sessão atual. Você pode usar os parâmetros de `Get-Job` para obter trabalhos específicos.

O objeto de trabalho que `Get-Job` retorna contém informações úteis sobre o trabalho, mas não contém os resultados do trabalho. Para obter os resultados, use o `Receive-Job` cmdlet.

Um trabalho em segundo plano do Windows PowerShell é um comando que é executado em segundo plano sem interagir com a sessão atual. Normalmente, você usa um trabalho em segundo plano para executar um comando complexo que leva muito tempo para ser concluído. Para obter mais informações sobre trabalhos em segundo plano no Windows PowerShell, consulte [about_Jobs](./about/about_Jobs.md).

A partir do Windows PowerShell 3,0, o `Get-Job` cmdlet também obtém tipos de trabalhos personalizados, como trabalhos de fluxo de trabalho e instâncias de trabalhos agendados. Para localizar o tipo de um trabalho, use a propriedade **PSJobTypeName** do trabalho em questão.

Para habilitar o `Get-Job` para obter um tipo de trabalho personalizado, importe o módulo que dá suporte ao tipo de trabalho personalizado na sessão antes de executar um `Get-Job` comando, seja usando o `Import-Module` cmdlet ou obtendo um cmdlet no módulo. Para obter informações sobre um tipo específico de trabalho personalizado, consulte a documentação do recurso de tipo de trabalho personalizado.

## EXEMPLOS

### Exemplo 1: obter todos os trabalhos em segundo plano iniciados na sessão atual

Esse comando obtém todos os trabalhos em segundo plano iniciados na sessão atual. Ele não inclui trabalhos criados em outras sessões, mesmo se os trabalhos forem executados no computador local.

```
PS C:\> Get-Job
```

### Exemplo 2: parar um trabalho usando uma ID de instância

Esses comandos mostram como obter o identificador de instância de um trabalho e, em seguida, usá-lo para interromper esse trabalho. Ao contrário do nome de um determinado trabalho, que não é exclusivo, o identificador da instância é.

O primeiro comando usa o `Get-Job` cmdlet para obter um trabalho. Ele usa o parâmetro **Name** para identificar o trabalho. O comando armazena o objeto de trabalho que `Get-Job` retorna na `$j` variável. Neste exemplo, há apenas um trabalho com o nome especificado. O segundo comando obtém a propriedade **InstanceId** do objeto na `$j` variável e a armazena na `$ID` variável. O terceiro comando exibe o valor da `$ID` variável. O quarto comando usa `Stop-Job` o cmdlet para interromper o trabalho.
Ele usa o parâmetro **InstanceId** para identificar o trabalho e a `$ID` variável para representar a ID da instância do trabalho.

```
PS C:\> $j = Get-Job -Name Job1
PS C:\> $ID = $j.InstanceID
PS C:\> $ID

Guid
----
03c3232e-1d23-453b-a6f4-ed73c9e29d55

PS C:\> Stop-Job -InstanceId $ID
```

### Exemplo 3: obter trabalhos que incluem um comando específico

Esse comando obtém os trabalhos no sistema que incluem um `Get-Process` comando. O comando usa o parâmetro de **comando** de `Get-Job` para limitar os trabalhos recuperados. O comando usa caracteres curinga ( `*` ) para obter trabalhos que incluem um `Get-Process` comando em qualquer lugar na cadeia de caracteres de comando.

```
PS C:\> Get-Job -Command "*get-process*"
```

### Exemplo 4: obter trabalhos que incluem um comando específico usando o pipeline

Como o comando no exemplo anterior, esse comando obtém os trabalhos no sistema que incluem um `Get-Process` comando. O comando usa um operador de pipeline ( `|` ) para enviar uma cadeia de caracteres, entre aspas, para o `Get-Job` cmdlet. Ele é o equivalente do comando anterior.

```
PS C:\> "*get-process*" | Get-Job
```

### Exemplo 5: obter trabalhos que não foram iniciados

Este comando obtém apenas os trabalhos que foram criados, mas ainda não foi iniciados. Isso inclui trabalhos agendados para execução no futuro e aqueles ainda não foram agendados.

```
PS C:\> Get-Job -State NotStarted
```

### Exemplo 6: obter trabalhos que não foram atribuídos a um nome

Esse comando obtém todos os trabalhos que têm nomes de trabalho que começam com o trabalho. Como `job<number>` é o nome padrão de um trabalho, esse comando obtém todos os trabalhos que não têm um nome explicitamente atribuído.

```
PS C:\> Get-Job -Name Job*
```

### Exemplo 7: usar um objeto de trabalho para representar o trabalho em um comando

Este exemplo mostra como usar `Get-Job` o para obter um objeto de trabalho e, em seguida, mostra como usar o objeto de trabalho para representar o trabalho em um comando.

O primeiro comando usa o `Start-Job` cmdlet para iniciar um trabalho em segundo plano que executa um `Get-Process` comando no computador local. O comando usa o parâmetro **Name** de `Start-Job` para atribuir um nome amigável ao trabalho. O segundo comando usa `Get-Job` para obter o trabalho. Ele usa o parâmetro **Name** de `Get-Job` para identificar o trabalho. O comando salva o objeto de trabalho resultante na `$j` variável. O terceiro comando exibe o valor do objeto de trabalho na `$j` variável. O valor da propriedade **State** mostra que o trabalho foi concluído. O valor da propriedade **HasMoreData** mostra que há resultados disponíveis do trabalho que ainda não foram recuperados. O quarto comando usa o `Receive-Job` cmdlet para obter os resultados do trabalho. Ele usa o objeto de trabalho na `$j` variável para representar o trabalho. Você também pode usar um operador de pipeline para enviar um objeto de trabalho para o `Receive-Job` .

```
PS C:\> Start-Job -ScriptBlock {Get-Process} -Name MyJob
PS C:\> $j = Get-Job -Name MyJob
PS C:\> $j
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
6      MyJob           BackgroundJob   Completed     True            localhost            Get-Process

PS C:\> Receive-Job -Job $j
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    124       4    13572      12080    59            1140 audiodg
    783      16    11428      13636   100             548 CcmExec
     96       4     4252       3764    59            3856 ccmsetup
...
```


### Exemplo 8: obter todos os trabalhos, incluindo trabalhos iniciados por um método diferente

Este exemplo demonstra que o `Get-Job` cmdlet pode obter todos os trabalhos que foram iniciados na sessão atual, mesmo que eles tenham sido iniciados usando métodos diferentes.

O primeiro comando usa o `Start-Job` cmdlet para iniciar um trabalho no computador local. O segundo comando usa o parâmetro **AsJob** do `Invoke-Command` cmdlet para iniciar um trabalho no computador S1. Embora os comandos do trabalho sejam executados no computador remoto, o objeto de trabalho é criado no computador local, para que você use comandos locais para gerenciar o trabalho. O terceiro comando usa o `Invoke-Command` cmdlet para executar um `Start-Job` comando no computador S2. Usando esse método, o objeto de trabalho é criado no computador remoto, portanto, você usa comandos remotos para gerenciar o trabalho. O quarto comando usa `Get-Job` para obter os trabalhos armazenados no computador local. A propriedade **PSJobTypeName** dos trabalhos, introduzida no Windows PowerShell 3,0, mostra que o trabalho local iniciado usando o `Start-Job` cmdlet é um trabalho em segundo plano e o trabalho iniciado em uma sessão remota usando o `Invoke-Command` cmdlet é um trabalho remoto. O quinto comando usa `Invoke-Command` para executar um `Get-Job` comando no computador S2. A saída de exemplo mostra os resultados do `Get-Job` comando. No computador S2, o trabalho parece ser um trabalho local. O nome do computador é localhost e o tipo de trabalho é um trabalho em segundo plano. Para obter mais informações sobre como executar trabalhos em segundo plano em computadores remotos, consulte [about_Remote_Jobs](./about/about_Remote_Jobs.md).

```
PS C:\> Start-Job -ScriptBlock {Get-EventLog System}
PS C:\> Invoke-Command -ComputerName S1 -ScriptBlock {Get-EventLog System} -AsJob
PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
PS C:\> Get-Job
Id     Name       PSJobTypeName   State         HasMoreData     Location        Command
--     ----       -------------   -----         -----------     --------        -------
1      Job1       BackgroundJob   Running       True            localhost       Get-EventLog System
2      Job2       RemoteJob       Running       True            S1              Get-EventLog System

PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Id    Name     PSJobTypeName  State      HasMoreData   Location   Command
--    ----     -------------  -----      -----------   -------    -------
4     Job4     BackgroundJob  Running    True          localhost  Get-Eventlog System
```

### Exemplo 9: investigar um trabalho com falha

Este comando mostra como usar o objeto de trabalho que `Get-Job` retorna para investigar por que um trabalho falhou.
Ele também mostra como obter os trabalhos filhos de cada trabalho.

O primeiro comando usa o `Start-Job` cmdlet para iniciar um trabalho no computador local. O objeto de trabalho que `Start-Job` retorna mostra que o trabalho falhou. Falha no valor da propriedade de **estado** .

O segundo comando usa o `Get-Job` cmdlet para obter o trabalho. O segundo comando usa o método de ponto para exibir o valor da propriedade **JobStateInfo** do objeto. Ele usa um operador de pipeline para enviar o objeto na propriedade **JobStateInfo** para o `Format-List` cmdlet, que formata todas as propriedades do objeto ( `*` ) em uma lista. O resultado do `Format-List` comando mostra que o valor da propriedade **Reason** do trabalho está em branco.

O terceiro comando investiga mais. Ele usa um `Get-Job` comando para obter o trabalho e, em seguida, usa um operador de pipeline para enviar todo o objeto de trabalho para o `Format-List` cmdlet, que exibe todas as propriedades do trabalho em uma lista. A exibição de todas as propriedades no objeto de trabalho mostra que o trabalho contém um trabalho filho chamado Job2.

O quarto comando usa `Get-Job` para obter o objeto de trabalho que representa o trabalho filho Job2. Esse é o trabalho no qual o comando foi realmente executado. Ele usa o método dot para obter a propriedade **Reason** da propriedade **JobStateInfo** . O resultado mostra que o trabalho falhou devido a um erro de acesso negado. Nesse caso, o usuário esqueceu de usar a opção Executar como administrador ao iniciar o Windows PowerShell. como os trabalhos em segundo plano usam os recursos de comunicação remota do Windows PowerShell, o computador deve ser configurado para comunicação remota para executar um trabalho, mesmo quando o trabalho é executado no computador local. Para obter informações sobre os requisitos de comunicação remota no Windows PowerShell, consulte [about_Remote_Requirements](./about/about_Remote_Requirements.md). Para obter dicas para solução de problemas, consulte [about_Remote_Troubleshooting](./about/about_Remote_Troubleshooting.md).

```
PS C:\> Start-Job -ScriptBlock {Get-Process}
Id     Name       PSJobTypeName   State       HasMoreData     Location             Command
--     ----       -------------   -----       -----------     --------             -------
1      Job1       BackgroundJob   Failed      False           localhost            Get-Process

PS C:\> (Get-Job).JobStateInfo | Format-List -Property *
State  : Failed
Reason :

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

PS C:\> (Get-Job -Name job2).JobStateInfo.Reason
Connecting to remote server using WSManCreateShellEx api failed. The async callback gave the
following error message: Access is denied.
```

### Exemplo 10: obter resultados filtrados

Este exemplo mostra como usar o parâmetro **Filter** para obter uma tarefa de fluxo de trabalho. O parâmetro **Filter** , introduzido no Windows PowerShell 3.0, é válido somente em tipos de trabalho personalizados, como tarefas de fluxo de trabalho e trabalhos agendados.

O primeiro comando usa a palavra-chave **Workflow** para criar o fluxo de trabalho WFProcess. O segundo comando usa o parâmetro **AsJob** do fluxo de trabalho do amWFProcess para executar o workflow como uma tarefa em segundo plano. Ele usa o parâmetro **JobName** do fluxo de trabalho para especificar um nome para o trabalho e o parâmetro **PSPrivateMetadata** do fluxo de trabalho para especificar um identificador personalizado. O terceiro comando usa o parâmetro **Filter** de `Get-Job` para obter o trabalho por ID personalizada que foi especificado no parâmetro **PSPrivateMetadata** .

```
PS C:\> Workflow WFProcess {Get-Process}
PS C:\> WFProcess -AsJob -JobName WFProcessJob -PSPrivateMetadata @{MyCustomId = 92107}
PS C:\> Get-Job -Filter @{MyCustomId = 92107}
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
1      WFProcessJob    Completed     True            localhost            WFProcess
```

### Exemplo 11: obter informações sobre trabalhos filho

Este exemplo mostra o efeito de usar os parâmetros **IncludeChildJob** e **ChildJobState** do `Get-Job` cmdlet.

O primeiro comando obtém os trabalhos presentes na sessão atual. A saída inclui um trabalho em segundo plano, um trabalho remoto e várias instâncias de um trabalho agendado. O trabalho remoto, Trabalho4, parece ter falhado.
O segundo comando usa o parâmetro **IncludeChildJob** de `Get-Job` . A saída adiciona os trabalhos filho de todos os trabalhos que têm trabalhos filho. Nesse caso, a saída revisada mostra que apenas o trabalho filho Job5 de Job4 falhou. O terceiro comando usa o parâmetro **ChildJobState** com um valor de Failed. a saída inclui todos os trabalhos pai e somente os trabalhos filho que falharam. O quinto comando usa a propriedade **JobStateInfo** de trabalhos e sua propriedade **Reason** para descobrir por que Job5 falhou.

```
PS C:\> Get-Job
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost            .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02   .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

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

PS C:\> (Get-Job -Name Job5).JobStateInfo.Reason
Connecting to remote server Server01 failed with the following error message:
Access is denied.
```

Para obter mais informações, consulte o tópico da ajuda [about_Remote_Troubleshooting](./about/about_Remote_Troubleshooting.md) .

## PARAMETERS

### -Depois de

Obtém os trabalhos concluídos após a data e hora especificadas. Insira um objeto **DateTime** , como um retornado pelo `Get-Date` cmdlet ou uma cadeia de caracteres que possa ser convertida em um objeto **DateTime** , como `Dec 1, 2012 2:00 AM` ou `11/06` .

Este parâmetro funciona somente em tipos de trabalho personalizados, como os de fluxo de trabalho e os trabalhos agendados que têm uma propriedade **EndTime**. Ele não funciona em trabalhos em segundo plano padrão, como aqueles criados usando o `Start-Job` cmdlet. Para obter informações sobre o suporte para este parâmetro, consulte o tópico da Ajuda para o tipo de trabalho em questão.

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

Obtém os trabalhos concluídos antes da data e hora especificadas. Insira um objeto **DateTime** .

Este parâmetro funciona somente em tipos de trabalho personalizados, como os de fluxo de trabalho e os trabalhos agendados que têm uma propriedade **EndTime**. Ele não funciona em trabalhos em segundo plano padrão, como aqueles criados usando o `Start-Job` cmdlet. Para obter informações sobre o suporte para este parâmetro, consulte o tópico da Ajuda para o tipo de trabalho em questão.

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

Obtém somente os trabalhos filhos que apresentam o estado especificado. Os valores aceitáveis para esse parâmetro são:

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

Por padrão, `Get-Job` o não obtém trabalhos filhos. Ao usar o parâmetro **IncludeChildJob** , o `Get-Job` Obtém todos os trabalhos filho. Se você usar o parâmetro **ChildJobState** , o parâmetro **IncludeChildJob** não tem nenhum efeito.

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

Especifica uma matriz de comandos como cadeias de caracteres. Esse cmdlet obtém os trabalhos que incluem os comandos especificados. O padrão é obter todos os trabalhos. Você pode usar caracteres curinga para especificar um padrão de comando.

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

Especifica uma tabela de hash de condições. Esse cmdlet obtém trabalhos que atendem a todas as condições.
Insira uma tabela de hash na qual as chaves são propriedades do trabalho e os valores são valores de propriedade do trabalho.

Este parâmetro funciona somente em tipos de trabalho personalizados, como os de fluxo de trabalho e os trabalhos agendados. Ele não funciona em trabalhos em segundo plano padrão, como aqueles criados usando o `Start-Job` cmdlet. Para obter informações sobre o suporte para este parâmetro, consulte o tópico da Ajuda para o tipo de trabalho em questão.

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
A propriedade **HasMoreData** indica se todos os resultados do trabalho foram recebidos na sessão atual. Para obter trabalhos que têm mais resultados, especifique um valor de `$True` . Para obter trabalhos que não têm mais resultados, especifique um valor de `$False` .

Para obter os resultados de um trabalho, use o `Receive-Job` cmdlet.

Quando você usa o `Receive-Job` cmdlet, ele exclui de seu armazenamento específico da sessão na memória, os resultados retornados por ele. Quando ele retorna todos os resultados do trabalho na sessão atual, ele define o valor da propriedade **HasMoreData** do trabalho como `$False` ) para indicar que ele não tem mais resultados para o trabalho na sessão atual. Use o parâmetro **Keep** de `Receive-Job` para evitar `Receive-Job` a exclusão de resultados e a alteração do valor da propriedade **HasMoreData** .
Para obter mais informações, digite `Get-Help Receive-Job`.

A propriedade **HasMoreData** é específica para a sessão atual. Se os resultados de um tipo de trabalho personalizado forem salvos fora da sessão, como o tipo de trabalho agendado, que salva os resultados do trabalho no disco, você poderá usar o `Receive-Job` cmdlet em uma sessão diferente para obter os resultados do trabalho novamente, mesmo que o valor de **HasMoreData** seja `$False` . Para obter mais informações, consulte os tópicos da ajuda para o tipo de trabalho personalizado.

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

A ID é um inteiro que identifica exclusivamente o trabalho na sessão atual. É mais fácil lembrar e digitar do que a ID da instância, mas só é exclusiva na sessão atual. Você pode digitar uma ou mais IDs separadas por vírgulas. Para localizar a ID de um trabalho, digite `Get-Job` sem parâmetros.

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

Esse parâmetro é especialmente útil para a investigação de trabalhos de fluxo de trabalho, para os quais `Get-Job` retorna um trabalho pai do contêiner e falhas de trabalhos, porque o motivo da falha é salvo em uma propriedade do trabalho filho.

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

Especifica uma matriz de IDs de instância dos trabalhos que esse cmdlet obtém. O padrão é obter todos os trabalhos.

Uma ID de instância é um GUID que identifica exclusivamente o trabalho no computador. Para localizar a ID de instância de um trabalho, use `Get-Job` .

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

Especifica uma matriz de nomes amigáveis de instância dos trabalhos que esse cmdlet obtém. Insira um nome de trabalho, ou então use caracteres curinga para inserir um padrão de nome de trabalho. Por padrão, o `Get-Job` Obtém todos os trabalhos na sessão atual.

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

Especifica um número de trabalhos a serem obtidos. Esse cmdlet obtém os trabalhos que foram encerrados mais recentemente.

O parâmetro **Newest** não classifica nem retorna os trabalhos mais recentes classificados segundo o horário de término. Para classificar a saída, use o `Sort-Object` cmdlet.

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

Especifica um estado de trabalho. Esse cmdlet obtém apenas os trabalhos no estado especificado. Os valores aceitáveis para esse parâmetro são:

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

Por padrão, `Get-Job` o Obtém todos os trabalhos na sessão atual.

Para obter mais informações sobre os Estados de trabalho, consulte [Enumeração JobState](/dotnet/api/system.management.automation.jobstate).

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

A propriedade **PSJobTypeName** dos trabalhos indica o tipo do trabalho em questão. O valor da propriedade é determinado pelo autor do tipo de trabalho. A lista a seguir mostra os tipos de trabalho comuns.

- **BackgroundJob**. Trabalho local iniciado usando `Start-Job` .
- **RemoteJob**. Trabalho iniciado em uma **PSSession** usando o parâmetro **AsJob** do `Invoke-Command` cmdlet.
- **PSWorkflowJob**. Trabalho iniciado usando o parâmetro comum **AsJob** dos fluxos de trabalho.

## LINKS RELACIONADOS

[Invoke-Command](Invoke-Command.md)

[Receive-Job](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job](Stop-Job.md)

[Wait-Job](Wait-Job.md)

[about_Jobs](About/about_Jobs.md)

[about_Job_Details](About/about_Job_Details.md)

[about_Remote_Jobs](About/about_Remote_Jobs.md)
