---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/resume-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-Job
ms.openlocfilehash: 6d08d9053e100cb53d37a6e4931d118f90c35a6a
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388528"
---
# Resume-Job

## SINOPSE
Reinicia um trabalho suspenso.

## SYNTAX

### SessionIdParameterSet (padrão)

```
Resume-Job [-Wait] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### JobParameterSet

```
Resume-Job [-Job] <Job[]> [-Wait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### NameParameterSet

```
Resume-Job [-Wait] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InstanceIdParameterSet

```
Resume-Job [-Wait] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### StateParameterSet

```
Resume-Job [-Wait] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FilterParameterSet

```
Resume-Job [-Wait] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Resume-Job` cmdlet retoma uma tarefa de fluxo de trabalho que foi suspensa, por exemplo, usando o `Suspend-Job` cmdlet ou a atividade [about_Suspend-Workflow](../PSWorkflow/about/about_Suspend-Workflow.md) . Quando uma tarefa de fluxo de trabalho é retomada, o mecanismo de trabalho reconstrói o estado, os metadados e a saída de recursos salvos, como pontos de verificação. O trabalho é reiniciado sem qualquer perda de estado ou dados.
O estado do trabalho é alterado de **Suspended** para **Running**.

Use os parâmetros de `Resume-Job` para selecionar trabalhos por nome, ID, ID de instância ou canal de um objeto de trabalho, como um retornado pelo `Get-Job` cmdlet, para `Resume-Job` . Você também pode usar um filtro de propriedade para selecionar um trabalho a ser retomado.

Por padrão, `Resume-Job` retorna imediatamente, embora todos os trabalhos ainda não tenham sido retomados. Para suprimir o prompt de comando até todos os trabalhos especificados serem reiniciados, use o parâmetro **Wait**.

O `Resume-Job` cmdlet funciona apenas em tipos de trabalhos personalizados, como trabalhos de fluxo de trabalho. Ele não funciona em trabalhos em segundo plano padrão, como os que são iniciados usando o `Start-Job` cmdlet. Se você enviar um trabalho de um tipo sem suporte, `Resume-Job` o gerará um erro de encerramento e interromperá a execução.

Para identificar uma tarefa de fluxo de trabalho, procure um valor de **PSWorkflowJob** na propriedade **PSJobTypeName** do trabalho. Para determinar se um determinado tipo de trabalho personalizado dá suporte ao `Resume-Job` cmdlet, consulte os tópicos da ajuda para o tipo de trabalho personalizado.

Antes de usar um cmdlet de trabalho em um tipo de trabalho personalizado, importe o módulo que dá suporte ao tipo de trabalho personalizado, seja usando o `Import-Module` cmdlet ou obtendo ou usando um cmdlet no módulo.

Este cmdlet foi introduzido no Windows PowerShell 3.0.

## EXEMPLOS

### Exemplo 1: retomar um trabalho por ID

Os comandos neste exemplo confirmam que o trabalho é uma tarefa de fluxo de trabalho suspensa e, em seguida, reiniciam o trabalho. O primeiro comando usa o `Get-Job` cmdlet para obter o trabalho. A saída mostra que o trabalho é uma tarefa de fluxo de trabalho suspensa. O segundo comando usa o parâmetro **ID** do `Resume-Job` cmdlet para retomar o trabalho com um valor de **ID** de 4.

```
PS C:\> Get-Job EventJob
Id     Name            PSJobTypeName   State         HasMoreData     Location   Command
--     ----            -------------   -----         -----------     --------   -------
4      EventJob        PSWorkflowJob   Suspended     True            Server01   \\Script\Share\Event.ps1

PS C:\> Resume-Job -Id 4
```

### Exemplo 2: retomar um trabalho por nome

Este comando usa o parâmetro **Name** para retomar vários trabalhos de fluxo de trabalho no computador local.

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest*
```

### Exemplo 3: usar valores de propriedade personalizada

Este comando usa o valor de uma propriedade personalizada para identificar a tarefa de fluxo de trabalho a retomar. Ele usa o parâmetro **Filter** para identificar a tarefa de fluxo de trabalho pela sua propriedade **CustomID**. Ele também usa o parâmetro **State** para verificar se a tarefa de fluxo de trabalho está suspensa, antes de tentar retomá-la.

```
PS C:\> Resume-Job -Filter @{CustomID="T091291"} -State Suspended
```

### Exemplo 4: retomar todos os trabalhos suspensos em um computador remoto

Este comando retoma todos os trabalhos suspensos no computador remoto Srv01.

```
PS C:\> Invoke-Command -ComputerName Srv01 -ScriptBlock {Get-Job -State Suspended | Resume-Job}
```

O comando usa o `Invoke-Command` cmdlet para executar um comando no computador Srv01. O comando remoto usa o parâmetro **State** do `Get-Job` cmdlet para obter todos os trabalhos suspensos no computador. Um operador de pipeline ( `|` ) envia os trabalhos suspensos para o `Resume-Job` cmdlet, que os retoma.

### Exemplo 5: aguardar a retomada dos trabalhos

Esse comando usa o parâmetro **Wait** para direcionar `Resume-Job` para retornar somente depois que todos os trabalhos especificados forem retomados. O parâmetro **Wait** é especialmente útil em scripts que assumem que os trabalhos são retomados antes do script continuar.

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest* -Wait
```

### Exemplo 6: retomar um fluxo de trabalho que se suspende

Este exemplo de código mostra a `Suspend-Workflow` atividade em um fluxo de trabalho.

O `Test-Suspend` fluxo de trabalho no computador Server01. Quando você executa o fluxo de trabalho, o fluxo de trabalho executa a `Get-Date` atividade e armazena o resultado na `$a` variável. Em seguida, ele executa a `Suspend-Workflow` atividade. Em resposta, ele usa um ponto de verificação, suspende o fluxo de trabalho e retorna um objeto de tarefa de fluxo de trabalho. `Suspend-Workflow` Retorna um objeto de trabalho do Workflow, mesmo que ele não seja executado explicitamente como um trabalho.

`Resume-Job` retoma o `Test-Suspend` fluxo de trabalho em Job8. Ele usa o parâmetro **Wait** para adiar o prompt de comando até o trabalho ser retomado.

O `Receive-Job` cmdlet obtém os resultados do `Test-Suspend` fluxo de trabalho. O comando final no fluxo de trabalho retorna um objeto **TimeSpan** que representa o tempo decorrido entre a data e a hora atuais e a data e hora que foram salvas na `$a` variável antes de o fluxo de trabalho ser suspenso.

```
#SampleWorkflow
Workflow Test-Suspend
{
    $a = Get-Date
    Suspend-Workflow
    (Get-Date)- $a
}

PS C:\> Test-Suspend -PSComputerName Server01
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
8      Job8            PSWorkflowJob   Suspended     True            Server01             Test-Suspend

PS C:\> Resume-Job -Name "Job8" -Wait
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
8      Job8            PSWorkflowJob   Running       True            Server01             Test-Suspend

PS C:\> Receive-Job -Name Job8
        Days              : 0
        Hours             : 0
        Minutes           : 0
        Seconds           : 19
        Milliseconds      : 823
        Ticks             : 198230041
        TotalDays         : 0.000229432917824074
        TotalHours        : 0.00550639002777778
        TotalMinutes      : 0.330383401666667
        TotalSeconds      : 19.8230041
        TotalMilliseconds : 19823.0041
        PSComputerName    : Server01
```

O `Resume-Job` cmdlet permite que você retome um trabalho de workflow que foi suspenso usando a `Suspend-Workflow` atividade. Essa atividade suspende um fluxo de trabalho de dentro de um fluxo de trabalho. Isso só é válido em fluxos de trabalho.

Para obter informações sobre o `Suspend-Workflow` , consulte about_Suspend-Workflow] (.. /PSWorkflow/about/about_Suspend-Workflow. MD).

## PARAMETERS

### -Filter

Especifica uma tabela de hash de condições. Esse cmdlet retoma os trabalhos que atendem a todas as condições na tabela de hash. Insira uma tabela de hash na qual as chaves são propriedades do trabalho e os valores são valores de propriedade do trabalho.

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

### -Id

Especifica uma matriz de IDs para trabalhos que esse cmdlet retoma.

A ID é um inteiro que identifica exclusivamente o trabalho na sessão atual. É mais fácil lembrar e digitar do que a ID da instância, mas só é exclusiva na sessão atual. Você pode digitar uma ou mais IDs, separadas por vírgulas. Para localizar a ID de um trabalho, execute `Get-Job` .

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId

Especifica uma matriz de IDs de instância dos trabalhos que esse cmdlet retoma. O padrão é obter todos os trabalhos.

Uma ID de instância é um GUID que identifica exclusivamente o trabalho no computador. Para localizar a ID de instância de um trabalho, execute `Get-Job` .

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

### -Trabalho

Especifica os trabalhos a serem retomados. Insira uma variável que contenha os trabalhos ou um comando que os obtenha. Você também pode canalizar trabalhos para o `Resume-Job` cmdlet.

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name

Especifica uma matriz de nomes amigáveis de trabalhos que esse cmdlet retoma. Insira um ou mais nomes de trabalho.
Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Estado

Especifica o estado dos trabalhos a serem retomados. Os valores aceitáveis para esse parâmetro são:

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

Esse cmdlet retoma apenas os trabalhos no estado **suspenso** .

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

### -Wait

Indica que esse cmdlet suprime o prompt de comando até que todos os resultados do trabalho sejam reiniciados. Por padrão, esse cmdlet retorna imediatamente os resultados disponíveis.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Solicita sua confirmação antes de executar o cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Mostra o que aconteceria se o cmdlet fosse executado. O cmdlet não é executado.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Management. Automation. Job

Você pode canalizar todos os tipos de trabalhos para esse cmdlet. Se `Resume-Job` o obtiver um trabalho de um tipo sem suporte, ele retornará um erro de encerramento.

## SAÍDAS

### Nenhum, System. Management. Automation. Job

Esse cmdlet retorna os trabalhos que ele tenta retomar, se você usar o parâmetro **PassThru** .
Caso contrário, este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

- `Resume-Job` Só é possível retomar os trabalhos que estão suspensos. Se você enviar um trabalho em um estado diferente, `Resume-Job` o executará a operação de retomada no trabalho, mas gerará um aviso para notificá-lo de que o trabalho não pôde ser retomado. Para suprimir o aviso, use o parâmetro de **aviso** comum com um valor de SilentlyContinue.
- Se um trabalho não for de um tipo que dá suporte à retomada, como um trabalho de Workflow ( **PSWorkflowJob** ), `Resume-Job` retornará um erro de encerramento.
- O mecanismo e o local para salvar um trabalho suspenso podem variar, dependendo do tipo do trabalho. Por exemplo, tarefas de fluxo de trabalho suspensas são salvas em um repositório de arquivo simples por padrão, mas também podem ser salvas em um banco de dados SQL.
- Quando você retoma um trabalho, o estado do trabalho muda de **Suspended** para **Running**. Para localizar os trabalhos em execução, incluindo aqueles que foram retomados por esse cmdlet, use o parâmetro **State** do `Get-Job` cmdlet para obter trabalhos no estado **executando** .
- Alguns tipos de trabalho têm opções ou propriedades que impedem que o Windows PowerShell suspenda o trabalho em questão.
  Se as tentativas de suspender o trabalho falharem, verifique se as opções e as propriedades do trabalho permitem a suspensão.

## LINKS RELACIONADOS

[Get-Job](Get-Job.md)

[Receive-Job](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job](Stop-Job.md)

[Suspend-Job](Suspend-Job.md)

[Wait-Job](Wait-Job.md)
