---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/set-scheduledjoboption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ScheduledJobOption
ms.openlocfilehash: 6647e9ba4e2ee49afa90dd382573d437d2deaee6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193660"
---
# Set-ScheduledJobOption

## SINOPSE
Altera as opções de trabalho de um trabalho agendado.

## SYNTAX

```
Set-ScheduledJobOption [-InputObject] <ScheduledJobOptions> [-PassThru] [-RunElevated] [-HideInTaskScheduler]
 [-RestartOnIdleResume] [-MultipleInstancePolicy <TaskMultipleInstancePolicy>] [-DoNotAllowDemandStart]
 [-RequireNetwork] [-StopIfGoingOffIdle] [-WakeToRun] [-ContinueIfGoingOnBattery] [-StartIfOnBattery]
 [-IdleTimeout <TimeSpan>] [-IdleDuration <TimeSpan>] [-StartIfIdle] [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Set-ScheduledJobOptions** altera as opções de trabalho dos trabalhos agendados.

Para alterar as opções de um trabalho agendado, comece usando o cmdlet Get-ScheduledJobOption para obter as opções de trabalho de um trabalho agendado.
Em seguida, canalize as opções para **Set-ScheduledJobOption** ou salve-o em uma variável e use o parâmetro *InputObject* do cmdlet **Set-ScheduledJobOption** para identificar as opções.
Use os parâmetros restantes do **Set-ScheduledJobOption** para alterar as opções de trabalho.

Para ativar uma opção de trabalho, use o parâmetro que define essa opção.
Para desativar uma opção, digite o nome do parâmetro, dois-pontos (:) e $False.
Por exemplo, para desativar a opção *RunElevated* , digite `-RunElevated:$False` .

Cada objeto de opções de trabalho inclui uma propriedade JobDefinition que contém o trabalho agendado, portanto, a associação com o trabalho agendado é mantida quando as opções de trabalho são alteradas.

As opções de trabalho agendadas determinam como o trabalho é executado quando ele é iniciado pelo Agendador de Tarefas.
Essas opções não se aplicam quando você usa o cmdlet Start-Job para iniciar um trabalho agendado.

**Set-ScheduledJobOption** é um de uma coleção de cmdlets de agendamento de trabalho no módulo PSScheduledJob que está incluído no Windows PowerShell.

Para obter mais informações sobre trabalhos agendados, consulte os tópicos sobre o módulo PSScheduledJob.
Importe o módulo PSScheduledJob e, em seguida, digite: `Get-Help about_Scheduled*` ou consulte about_Scheduled_Jobs.

Este cmdlet foi introduzido no Windows PowerShell 3.0.

## EXEMPLOS

### Exemplo 1: alterar as opções de trabalho

```
PS C:\> Get-ScheduledJobOption -Name "DeployPackage"
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
RunWithoutNetwork      : False
DoNotAllowDemandStart  : False
MultipleInstancePolicy : IgnoreNew
JobDefinition          :

The second command uses the **Set-ScheduledJobOpton** cmdlet to change the job options so the values of the WakeToRun and RunWithoutNetwork properties are $True. The command uses the *Passthru* parameter to return the trigger after the change.
PS C:\> Get-ScheduledJobOption -Name "DeployPackage" | Set-ScheduledJobOption -WakeToRun -RequireNetwork:$False -Passthru
StartIfOnBatteries     : False
StopIfGoingOnBatteries : True
WakeToRun              : True
StartIfNotIdle         : True
StopIfGoingOffIdle     : False
RestartOnIdleResume    : False
IdleDuration           : 00:10:00
IdleTimeout            : 01:00:00
ShowInTaskScheduler    : True
RunElevated            : False
RunWithoutNetwork      : True
DoNotAllowDemandStart  : False
MultipleInstancePolicy : IgnoreNewJobDefinition          :
```

Este exemplo mostra como alterar as opções de uma tarefa agendada no computador local.

O primeiro comando usa o cmdlet Get-ScheduledJobOption para obter as opções de trabalho do trabalho agendado DeployPackage.
A saída mostra que as propriedades WakeToRun e RunElevated são definidas como $False.

Este comando não é obrigatório. Ele está incluído apenas para mostrar o efeito da alteração da opção.

### Exemplo 2: alterar uma opção em todos os trabalhos agendados remotamente

```
PS C:\> Invoke-Command -Computer "Server01" -ScriptBlock {Get-ScheduledJob | Get-ScheduledJobOption | Set-ScheduledJobOption -IdleTimeout 2:00:00}
```

Esse comando altera o valor de *IdleTimeout* de uma hora (o valor padrão) para duas horas em todos os trabalhos agendados no computador Server01.

O comando usa o cmdlet Invoke-Command para executar um comando no computador Server01.

O comando remoto começa com um comando Get-ScheduledJob que obtém todos os trabalhos agendados no computador.
Os trabalhos agendados são canalizados para o cmdlet Get-ScheduledJobOption, que obtém as opções de trabalho dos trabalhos agendados.
Cada objeto de opções de trabalho contém uma propriedade JobDefinition que contém o trabalho agendado, por isso o objeto de opções permaneça associado ao trabalho agendado, mesmo quando alterado.

Os gatilhos de trabalho são canalizados para o cmdlet **set-ScheduledJobOption** , que altera o valor da opção *IdleTimeout* para duas horas (2:00:00).

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

Mesmo que uma tarefa esteja oculta, os usuários podem exibir a tarefa selecionando a opção **Mostrar tarefas ocultas** modo de exibição no Agendador de tarefas.

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

Insira um objeto TimeSpan, como um gerado pelo cmdlet New-TimeSpan, ou insira um valor em \<hours\> : \<minutes\> : \<seconds\> Format que é convertido automaticamente em um objeto **TimeSpan** .

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
Especifica quanto tempo o computador deve permanecer ocioso antes de iniciar o trabalho.
O valor padrão é 10 minutos.
Se o computador não estiver ocioso durante o tempo especificado antes do valor de **IdleTimeout** expirar, o trabalho agendado não será executado até que a próxima execução agendada, se houver.

Insira um objeto TimeSpan, como um gerado pelo cmdlet New-TimeSpan, ou insira um valor em \<hours\> : \<minutes\> : \<seconds\> Format que é convertido automaticamente em um objeto **TimeSpan** .

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

### -InputObject
Especifica as opções de trabalho.
Insira uma variável que contenha objetos **ScheduledJobOptions** ou digite um comando ou uma expressão que obtenha objetos **ScheduledJobOptions** , como um comando Get-ScheduledJobOption.
Você também pode canalizar um objeto **ScheduledJobOptions** para **set-ScheduledJobOption** .

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MultipleInstancePolicy
Determina como o sistema responde a uma solicitação para iniciar uma instância de um trabalho agendado, enquanto outra instância de trabalho está em execução.
Os valores aceitáveis para esse parâmetro são:

- IgnoreNew.
A nova instância de trabalho será ignorada.
Este é o valor padrão.
- Paralelo.
A nova instância de trabalho será iniciada imediatamente.
- Fila.
A nova instância de trabalho começa assim que a instância atual for concluída.
- StopExisting.
A instância atual do trabalho parado e a nova instância foram iniciadas.

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

### -PassThru
Retorna um objeto que representa o item com que você está trabalhando.
Por padrão, este cmdlet não gera saída.

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

O parâmetro **RunElevated** define o valor da propriedade **RunElevated** de trabalhos agendados como true.

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
Inicia o trabalho agendado, se o computador estiver ocioso durante o tempo especificado pelo parâmetro **IdleDuration** antes da hora especificada pelo parâmetro *IdleTimeout* expirar.

Por padrão, os parâmetros *IdleDuration* e *IdleTimeout* serão ignorados e o trabalho será iniciado na hora de início agendada, mesmo se o computador estiver ocupado.

Se você especificar esse parâmetro e o computador estiver ocupado (não ocioso) na hora de início agendada, o trabalho não será executado até a próxima hora de início agendada se houver.

O parâmetro *StartIfIdle* define o valor da propriedade **StartIfNotIdle** de trabalhos agendados como false.

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
O valor padrão é False.

O parâmetro *StartIfOnBattery* define o valor da propriedade **StartIfOnBatteries** de trabalhos agendados para $true.

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

### Microsoft. PowerShell. ScheduledJob. ScheduledJobOptions
Você pode direcionar um objeto de opções de trabalho agendadas para **Set-ScheduledJobOption** .

## SAÍDAS

### Nenhum ou Microsoft. PowerShell. ScheduledJob. ScheduledJobOptions
Ao usar o parâmetro *Passthru* , o **Set-ScheduledJobOption** retorna as opções de trabalho que foram alteradas.
Caso contrário, este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

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
