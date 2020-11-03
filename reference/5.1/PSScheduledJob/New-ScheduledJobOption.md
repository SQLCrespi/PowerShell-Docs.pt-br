---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/new-scheduledjoboption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ScheduledJobOption
ms.openlocfilehash: 35ada8d5aaa6a6c1fdc74a089308aefe13598b10
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193671"
---
# New-ScheduledJobOption

## SINOPSE
Cria um objeto que contém as opções avançadas para um trabalho agendado.

## SYNTAX

```
New-ScheduledJobOption [-RunElevated] [-HideInTaskScheduler] [-RestartOnIdleResume]
 [-MultipleInstancePolicy <TaskMultipleInstancePolicy>] [-DoNotAllowDemandStart] [-RequireNetwork]
 [-StopIfGoingOffIdle] [-WakeToRun] [-ContinueIfGoingOnBattery] [-StartIfOnBattery] [-IdleTimeout <TimeSpan>]
 [-IdleDuration <TimeSpan>] [-StartIfIdle] [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **New-ScheduledJobOption** cria um objeto que contém as opções avançadas para um trabalho agendado.

Você pode usar o objeto **ScheduledJobOptions** que retorna **New-ScheduledJobOption** para definir opções de trabalho para um trabalho agendado novo ou existente.
Como alternativa, você pode definir as opções de trabalho usando o cmdlet Get-ScheduledJobOption para obter as opções de trabalho de um trabalho agendado existente ou usando um valor de tabela de hash para representar as opções de trabalho.

Sem parâmetros, **New-ScheduledJobOption** gera um objeto que contém os valores padrão para todas as opções.
Como todas as propriedades, exceto a propriedade JobDefinition, podem ser editadas, é possível usar o objeto resultante como um modelo e criar objetos de opção padrão para a sua empresa.

Ao criar trabalhos agendados e definir opções de trabalho agendado, examine os valores padrões de todas as opções de trabalho agendado.
Executar somente quando todas as condições definidas para a execução de trabalhos agendados forem atendidas.

**New-ScheduledJobOption** é um de uma coleção de cmdlets de agendamento de trabalho no módulo PSScheduledJob que está incluído no Windows PowerShell.

Para obter mais informações sobre trabalhos agendados, consulte os tópicos sobre o módulo PSScheduledJob.
Importe o módulo PSScheduledJob e, em seguida, digite: `Get-Help about_Scheduled*` ou consulte about_Scheduled_Jobs.

Este cmdlet foi introduzido no Windows PowerShell 3.0.

## EXEMPLOS

### Exemplo 1: criar um objeto de opção de trabalho agendado com valores padrão

```
PS C:\> New-ScheduledJobOption
StartIfOnBatteries     : False
StopIfGoingOnBatteries : True
WakeToRun              : False
StartIfNotIdle         : True
StopIfGoingOffIdle     : False
RestartOnIdleResume    : False
IdleDuration           : 00:10:00
IdleTimeout            : 01:00:00
ShowInTaskScheduler    : True
RunElevated            : False
RunWithoutNetwork      : True
DoNotAllowDemandStart  : False
MultipleInstancePolicy : Ignore
NewJobDefinition       :
```

Este comando cria um objeto de opção de trabalho agendado que tem todos os valores padrões.

### Exemplo 2: criar um objeto de opção de trabalho agendado com valores personalizados

```
PS C:\> New-ScheduledJobOption -RequireNetwork -StartIfOnBattery
StartIfOnBatteries     : True
StopIfGoingOnBatteries : True
WakeToRun              : False
StartIfNotIdle         : True
StopIfGoingOffIdle     : False
RestartOnIdleResume    : False
IdleDuration           : 00:10:00
IdleTimeout            : 01:00:00
ShowInTaskScheduler    : True
RunElevated            : False
RunWithoutNetwork      : False
DoNotAllowDemandStart  : False
MultipleInstancePolicy : Ignore
NewJobDefinition       :
```

O comando a seguir cria um objeto de trabalho agendado que requer a rede e executa o trabalho agendado, mesmo que o computador não esteja conectado à corrente alternada.

A saída mostra que o parâmetro *RequireNetwork* alterou o valor da propriedade RunWithoutNetwork para $false e o parâmetro *StartIfOnBattery* alterou o valor da propriedade StartIfOnBatteries para $true.

### Exemplo 3: definir opções para um novo trabalho agendado

```
The first command creates a **ScheduledJobOptions** object with the *RunElevated* parameter. It saves the object in the $RunAsAdmin variable.
PS C:\> $RunAsAdmin = New-ScheduledJobOption -RunElevated

The second command uses the Register-ScheduledJob cmdlet to create a new scheduled job. The value of the *ScheduledJobOption* parameter is the option object in the value of the $RunAsAdmin variable.
PS C:\> Register-ScheduledJob -Name Backup -FilePath D:\Scripts\Backup.ps1 -Trigger $Mondays -ScheduledJobOption $RunAsAdmin

The third command uses the Get-ScheduledJobOption cmdlet to get the job options of the Backup scheduled job.The cmdlet output shows that the RunElevated property is set to $True and the JobDefinition property of the job option object is now populated with the scheduled job object for the Backup scheduled job.
PS C:\> Get-ScheduledJobOption -Name Backup
StartIfOnBatteries     : False
StopIfGoingOnBatteries : True
WakeToRun              : False
StartIfNotIdle         : True
StopIfGoingOffIdle     : False
RestartOnIdleResume    : False
IdleDuration           : 00:10:00
IdleTimeout            : 01:00:00
ShowInTaskScheduler    : True
RunElevated            : True
RunWithoutNetwork      : True
DoNotAllowDemandStart  : False
MultipleInstancePolicy : IgnoreNew
JobDefinition          : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

Este exemplo mostra como usar o objeto **ScheduledJobOptions** que retorna **New-ScheduledJobOption** para definir as opções para um novo trabalho agendado.

### Exemplo 4: classificar as propriedades de um objeto de opção de trabalho agendado

```
PS C:\> $Options = New-ScheduledJobOption -WakeToRun
PS C:\> $Options.PSObject.Properties | Sort-Object -Property Name | Format-Table -Property Name, Value -Autosize
Name                       Value
----                       -----
DoNotAllowDemandStart      False
IdleDuration            00:10:00
IdleTimeout             01:00:00
JobDefinition
MultipleInstancePolicy IgnoreNew
RestartOnIdleResume        False
RunElevated                False
RunWithoutNetwork           True
ShowInTaskScheduler         True
StartIfNotIdle              True
StartIfOnBatteries         False
StopIfGoingOffIdle         False
StopIfGoingOnBatteries      True
WakeToRun                   True
```

Este exemplo mostra como classificar as propriedades de um objeto **ScheduledJobOptions** em ordem alfabética para facilitar a leitura.

O primeiro comando usa o cmdlet **New-ScheduledJobOption** para criar um objeto **ScheduledJobOptions** .
O comando usa o parâmetro *WakeToRun* e salva o objeto resultante na variável $Options.

Para obter as propriedades de $Options como objetos, o segundo comando usa a propriedade **PSObject** de todos os objetos do Windows PowerShell e sua propriedade Properties.
Em seguida, o comando canaliza os objetos de propriedade para o cmdlet Sort-Object, que classifica as propriedades em ordem alfabética por nome e, em seguida, para o cmdlet Format-Table, que exibe os nomes e valores das propriedades em uma tabela.

Esse formato torna muito mais fácil localizar a propriedade WakeToRun do objeto **ScheduledJobOptions** no $Options e verificar se seu valor foi alterado de $False para $true.

## PARAMETERS

### -ContinueIfGoingOnBattery
Não interrompa a tarefa se o computador alternar para a energia da bateria (desconectado da corrente alternada) enquanto o trabalho estiver em execução.
Por padrão, os trabalhos agendados param quando o computador é desconectado da corrente alternada.

O parâmetro *ContinueIfGoingOnBattery* define o valor da propriedade StopIfGoingOnBatteries de trabalhos agendados para $true.

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

### -DoNotAllowDemandStart
Inicie o trabalho somente quando ele é acionado.
Os usuários não podem iniciar o trabalho manualmente, como usando a execução de recursos no Agendador de tarefas.

Este parâmetro afeta somente o Agendador de tarefas.
Ele não impede que os usuários usem o cmdlet Start-Job para iniciar o trabalho.

O parâmetro *DoNotAllowDemandStart* define o valor da propriedade DoNotAllowDemandStart de trabalhos agendados para $true.

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

### -HideInTaskScheduler
Não exiba o trabalho no Agendador de tarefas.
Esse valor afeta somente o computador no qual o trabalho é executado.
Por padrão, as tarefas agendadas são exibidas no Agendador de tarefas.

Mesmo que uma tarefa esteja oculta, os usuários podem exibir a tarefa selecionando a opção Mostrar tarefas ocultas modo de exibição no Agendador de Tarefas.

O parâmetro *HideInTaskScheduler* define o valor da propriedade ShowInTaskScheduler de trabalhos agendados para $false.

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

### -IdleDuration
Especifica quanto tempo o computador deve permanecer ocioso antes de iniciar o trabalho.
O valor padrão é 10 minutos.
Se o computador não estiver ocioso durante o tempo especificado antes do valor de *IdleTimeout* expirar, o trabalho agendado não será executado até que a próxima execução agendada, se houver.

Insira um objeto **TimeSpan** , como um gerado pelo cmdlet New-TimeSpan, ou insira um valor em \<hours\> : \<minutes\> : \<seconds\> Format que é convertido automaticamente em um objeto **TimeSpan** .

Para habilitar esse valor, use o parâmetro *StartIfIdle* .
Por padrão, a propriedade StartIfNotIdle dos trabalhos agendados é definida como $True e o Windows PowerShell ignora os valores *IdleDuration* e *IdleTimeout* .

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdleTimeout
Especifica quanto tempo a tarefa aguarda o computador ficar ocioso.
Se esse tempo limite expirar antes que o computador permaneça ocioso durante um período de tempo especificado pelo parâmetro *IdleDuration* , o trabalho não será executado até a próxima execução agendada, se houver alguma.
O valor padrão é uma hora.

Insira um objeto **TimeSpan** , como um gerado pelo cmdlet New-TimeSpan, ou insira um valor em \<hours\> : \<minutes\> : \<seconds\> Format que é convertido automaticamente em um objeto **TimeSpan** .

Para habilitar esse valor, use o parâmetro *StartIfIdle* .
Por padrão, a propriedade StartIfNotIdle dos trabalhos agendados é definida como $True e o Windows PowerShell ignora os valores *IdleDuration* e *IdleTimeout* .

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MultipleInstancePolicy
Determina como o sistema responde a uma solicitação para iniciar uma instância de um trabalho agendado, enquanto outra instância de trabalho está em execução.
O valor padrão é IgnoreNew.
Os valores aceitáveis para esse parâmetro são:

- IgnoreNew.
A nova instância de trabalho será ignorada.
- Paralelo.
A nova instância de trabalho será iniciada imediatamente.
- Fila.
A nova instância de trabalho começa assim que a instância atual for concluída.
- StopExisting.
A instância atual do trabalho é interrompida e a nova instância é iniciada.

Para executar o trabalho, todas as condições da agenda de trabalho devem ser atendidas.
Por exemplo, se as condições definidas pelos parâmetros *RequireNetwork* , *IdleDuration* e *IdleTimeout* não forem satisfeitas, a instância de trabalho não será iniciada, independentemente do valor desse parâmetro.

```yaml
Type: Microsoft.PowerShell.ScheduledJob.TaskMultipleInstancePolicy
Parameter Sets: (All)
Aliases:
Accepted values: None, IgnoreNew, Parallel, Queue, StopExisting

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequireNetwork
Executa a tarefa agendada somente quando conexões de rede estão disponíveis.

Se você especificar esse parâmetro e a rede não estiver disponível na hora de início agendada, o trabalho não será executado até a próxima hora de início agendada, se houver alguma.

O parâmetro *RequireNetwork* define o valor da propriedade RunWithoutNetwork de trabalhos agendados para $false.

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

### -RestartOnIdleResume
Reinicia um trabalho agendado quando o computador ficar ocioso.
Esse parâmetro funciona com o parâmetro *StopIfGoingOffIdle* , que suspende um trabalho agendado em execução se o computador se torna ativo (deixe o estado ocioso).

O parâmetro *RestartOnIdleResume* define o valor da propriedade RestartOnIdleResume de trabalhos agendados para $true.

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

### -RunElevated
Executa o trabalho agendado com as permissões de um membro do grupo Administradores no computador no qual o trabalho é executado.

Para permitir que um trabalho agendado seja executado com permissões de administrador, use o parâmetro *Credential* de Register-ScheduledJob para fornecer credenciais explícitas para o trabalho.

O parâmetro *RunElevated* define o valor da propriedade RunElevated de trabalhos agendados para $true.

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

### -StartIfIdle
Inicia o trabalho agendado, se o computador estiver ocioso durante o tempo especificado pelo parâmetro *IdleDuration* antes da hora especificada pelo parâmetro *IdleTimeout* expirar.

Por padrão, os parâmetros *IdleDuration* e *IdleTimeout* serão ignorados e o trabalho será iniciado na hora de início agendada, mesmo se o computador estiver ocupado.

Se você especificar esse parâmetro e o computador estiver ocupado (não ocioso) na hora de início agendada, o trabalho não será executado até a próxima hora de início agendada se houver.

O parâmetro *StartIfIdle* define o valor da propriedade StartIfNotIdle de trabalhos agendados para $false.

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

### -StartIfOnBattery
Inicia o trabalho agendado, mesmo se o computador estiver usando baterias na hora de início agendada.
O valor padrão é $False.

O parâmetro *StartIfOnBattery* define o valor da propriedade StartIfOnBatteries de trabalhos agendados para $true.

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

### -StopIfGoingOffIdle
Suspende um trabalho agendado em execução se o computador se torna ativo (não ocioso) enquanto o trabalho está em execução.

Por padrão, um trabalho agendado é suspenso quando o computador se torna ativo e retomado quando o computador tornar-se ocioso novamente.
Para alterar esse comportamento padrão, utilize o parâmetro *RestartOnIdleResume* .

O parâmetro *StopIfGoingOffIdle* define o valor da propriedade StopIfGoingOffIdle de trabalhos agendados para $true.

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

### -WakeToRun
Desperta o computador de um estado de suspensão ou de hibernação na hora de início agendada para que possa executar o trabalho.
Por padrão, se o computador está em um estado de suspensão ou de hibernação na hora de início agendada, o trabalho não será executado.

O parâmetro *WakeToRun* define o valor da propriedade WakeToRun de trabalhos agendados para $true.

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

### CommonParameters
Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum
Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### Microsoft. PowerShell. ScheduledJob. ScheduledJobOptions

## OBSERVAÇÕES

* Você pode usar o objeto **ScheduledJobOptions** que **New-ScheduledJobOption** cria como o valor do parâmetro *ScheduledJobOption* do cmdlet Register-ScheduledJob. No entanto, o parâmetro *ScheduledJobOption* também pode pegar um valor de tabela de hash que especifica as propriedades do objeto **ScheduledJobOptions** e seus valores, como:

  `@{ShowInTaskScheduler=$False; RunElevated=$True; IdleDuration="00:05"}`

## LINKS RELACIONADOS

[Add-JobTrigger](Add-JobTrigger.md)

[Disable-JobTrigger](Disable-JobTrigger.md)

[Disable-ScheduledJob](Disable-ScheduledJob.md)

[Enable-JobTrigger](Enable-JobTrigger.md)

[Enable-ScheduledJob](Enable-ScheduledJob.md)

[Get-JobTrigger](Get-JobTrigger.md)

[Get-ScheduledJob](Get-ScheduledJob.md)

[Get-ScheduledJobOption](Get-ScheduledJobOption.md)

[New-JobTrigger](New-JobTrigger.md)

[New-ScheduledJobOption](New-ScheduledJobOption.md)

[Register-ScheduledJob](Register-ScheduledJob.md)

[Remove-JobTrigger](Remove-JobTrigger.md)

[Set-JobTrigger](Set-JobTrigger.md)

[Set-ScheduledJob](Set-ScheduledJob.md)

[Set-ScheduledJobOption](Set-ScheduledJobOption.md)

[Unregister-ScheduledJob](Unregister-ScheduledJob.md)
