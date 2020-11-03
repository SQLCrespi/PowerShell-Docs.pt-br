---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/set-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-JobTrigger
ms.openlocfilehash: 8d1b12b67ccf695e1c4b948e6eeecf292c588af4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193666"
---
# Set-JobTrigger

## SINOPSE
Altera o disparador do trabalho de um trabalho agendado.

## SYNTAX

```
Set-JobTrigger [-InputObject] <ScheduledJobTrigger[]> [-DaysInterval <Int32>] [-WeeksInterval <Int32>]
 [-RandomDelay <TimeSpan>] [-At <DateTime>] [-User <String>] [-DaysOfWeek <DayOfWeek[]>] [-AtStartup]
 [-AtLogOn] [-Once] [-RepetitionInterval <TimeSpan>] [-RepetitionDuration <TimeSpan>] [-RepeatIndefinitely]
 [-Daily] [-Weekly] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **Set-JobTrigger** altera as propriedades dos disparadores de trabalho dos trabalhos agendados.
Você pode usá-lo para alterar o tempo ou a frequência em que os trabalhos iniciam ou mudar de um agendamento com base no tempo para agendas que são disparadas por um logon ou na inicialização.

Um gatilho de trabalho define uma agenda recorrente ou condições para iniciar um trabalho agendado.
Embora disparadores de trabalho não sejam salvos em disco, você pode alterar os disparos de trabalho dos trabalhos agendados, que são salvos em disco.

Para alterar um gatilho de trabalho de um trabalho agendado, comece usando o cmdlet Get-JobTrigger para obter o gatilho de trabalho de um trabalho agendado.
Em seguida, canalize o disparador para **Set-JobTrigger** ou salve-o em uma variável e use o parâmetro *InputObject* do cmdlet **Set-JobTrigger** para identificar o disparador.
Use os parâmetros restantes do **Set-JobTrigger** para alterar o disparador de trabalho.

Quando você altera o tipo de um gatilho de trabalho, como alterar um gatilho de trabalho de um gatilho diário ou semanal para um gatilho *AtLogon* , as propriedades originais do gatilho são excluídas.
No entanto, se você alterar os valores do disparador, mas não seu tipo, como alterar os dias em um disparador semanal, somente as propriedades que você especificar serão alteradas.
Todas as outras propriedades originais do disparador de trabalho são mantidas.

**Set-JobTrigger** é um de uma coleção de cmdlets de agendamento de trabalho no módulo PSScheduledJob que está incluído no Windows PowerShell.

Para obter mais informações sobre trabalhos agendados, consulte os tópicos sobre o módulo PSScheduledJob.
Importe o módulo PSScheduledJob e, em seguida, digite: `Get-Help about_Scheduled*`  ou consulte about_Scheduled_Jobs.

Este cmdlet foi introduzido no Windows PowerShell 3.0.

## EXEMPLOS

### Exemplo 1: alterar os dias em um gatilho de trabalho

```
PS C:\> Get-JobTrigger -Name "DeployPackage"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Weekly          9/29/2011 12:00:00 AM  {Wednesday, Saturday}   True

The second command uses the Get-JobTrigger cmdlet to get the job trigger of the DeployPackage scheduled job. A pipeline operator (|) sends the trigger to the **Set-JobTrigger** cmdlet, which changes the job trigger so that it starts the DeployPackage job on Wednesdays and Sundays. The command uses the *Passthru* parameter to return the trigger after the change.
PS C:\> Get-JobTrigger -Name "DeployPackage" | Set-JobTrigger -DaysOfWeek "Wednesday", "Sunday" -Passthru
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Weekly          9/29/2011 12:00:00 AM  {Wednesday, Sunday}     True
```

Este exemplo mostra como alterar os dias em um disparador de trabalho semanal.

O primeiro comando usa o cmdlet Get-JobTrigger para obter o gatilho de trabalho do trabalho agendado DeployPackage.
A saída mostra que o disparador inicia o trabalho à meia-noite nas quartas-feiras e sábados.

Este comando não é obrigatório. Ele está incluído apenas para mostrar o efeito da alteração do disparador.

### Exemplo 2: alterar o tipo de gatilho do trabalho

```
PS C:\> Get-JobTrigger -Name "Inventory"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Daily           9/27/2011 11:00:00 PM                          True
2          AtStartup                                                      True

The second command uses the **Get-JobTrigger** cmdlet to get the *AtStartup* job trigger of the Inventory job. The command uses the *TriggerID* parameter to identify the job trigger. A pipeline operator (|) sends the job trigger to the **Set-JobTrigger** cmdlet, which changes it to a weekly job trigger that runs every four weeks on Monday at midnight. The command uses the *Passthru* parameter to return the trigger after the change.
PS C:\> Get-JobTrigger -Name "Inventory" -TriggerID 2 | Set-JobTrigger -Weekly -WeeksInterval 4 -DaysOfWeek Monday -At "12:00 AM"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Daily           9/27/2011 11:00:00 PM                          True
2          Weekly          10/31/2011 12:00:00 AM {Monday}                True
```

Este exemplo mostra como alterar o tipo de disparador de trabalho que inicia um trabalho.
Os comandos neste exemplo substituem um disparador de trabalho AtStartup com um disparador semanal.

O primeiro comando usa o cmdlet Get-JobTrigger para obter o gatilho de trabalho do trabalho agendado de inventário.
A saída mostra que o trabalho tem dois disparadores um gatilho diário e um gatilho *AtStartup* .

Este comando não é obrigatório. Ele está incluído apenas para mostrar o efeito da alteração do disparador.

### Exemplo 3: alterar o usuário em um gatilho de trabalho remoto

```
PS C:\> Invoke-Command -ComputerName "Server01" -ScriptBlock {Get-ScheduledJob | Get-JobTrigger | Where-Object {$_.User} | Set-JobTrigger -User "Domain01/Admin02"}
```

Esse comando altera o usuário em todos os gatilhos de trabalho do *AtLogon* dos trabalhos agendados no computador Server01.

O comando usa o cmdlet Invoke-Command para executar um comando no computador Server01.

O comando remoto começa com um comando Get-ScheduledJob que obtém todos os trabalhos agendados no computador.
Os trabalhos agendados são canalizados para o cmdlet Get-JobTrigger, que obtém os disparadores de trabalho dos trabalhos agendados.
Cada disparador de trabalho contém uma propriedade JobDefinition que contém o trabalho agendado, por isso o disparador permanece associado ao trabalho agendado, mesmo quando alterado.

Os gatilhos de trabalho são canalizados para o cmdlet Where-Object, que obtém gatilhos de trabalho que têm a propriedade User.
Os disparadores de trabalho selecionados serão canalizados para o cmdlet **Set-JobTrigger** , que altera o usuário para Domain01\Admin02.

### Exemplo 4: alterar um dos vários gatilhos de trabalho

```
PS C:\> Get-JobTrigger -Name "SecurityCheck"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Daily           4/24/2013 3:00:00 AM                           True
2          Weekly          4/24/2013 4:00:00 PM   {Sunday}                True
3          Once            4/24/2013 4:00:00 PM                           True

The second command uses the **TriggerID** parameter of the **Get-JobTrigger** cmdlet to get the *Once* trigger of the SecurityCheck scheduled job. The command pipes the trigger to the Format-List cmdlet, which displays all of the properties of the *Once* job trigger.The output shows that the trigger starts the job once every hour (RepetitionInterval = 1 hour) for one day (RepetitionDuration = 1 day).
PS C:\> Get-JobTrigger -Name "SecurityCheck" -TriggerID 3 | Format-List -Property *
At                 : 4/24/2012 4:00:00 PM
DaysOfWeek         :
Interval           : 1
Frequency          : Once
RandomDelay        : 00:00:00
RepetitionInterval : 01:00:00
RepetitionDuration : 1.00:00:00
User               :
Id                 : 3
Enabled            : True
JobDefinition      : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition

The third command changes the repetition interval of the job trigger from one hour to 90 minutes. The command does not return any output.
PS C:\> Get-JobTrigger -Name "SecurityCheck" -TriggerId 3 | Set-JobTrigger -RepetitionInterval (New-TimeSpan -Minutes 90)

The fourth command displays the effect of the change.The output shows that the trigger starts the job once every 90 minutes (RepetitionInterval = 1 hour, 30 minutes) for one day (RepetitionDuration = 1 day).
PS C:\> Get-JobTrigger -Name "SecurityCheck" -TriggerID 3 | Format-List -Property *
At                 : 4/24/2012 4:00:00 PM
DaysOfWeek         :
Interval           : 1
Frequency          : Once
RandomDelay        : 00:00:00
RepetitionInterval : 01:30:00
RepetitionDuration : 1.00:00:00
User               :
Id                 : 3
Enabled            : True
JobDefinition      : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

Os comandos neste exemplo alteram o intervalo de repetição do disparador de trabalho *Once* do trabalho agendado SecurityCheck de cada 60 minutos para cada 90 minutos.
O trabalho agendado SecurityCheck tem três gatilhos de trabalho, portanto, os comandos usam o parâmetro *triggerid* do cmdlet Get-JobTrigger para identificar o gatilho de trabalho que está sendo alterado.

O primeiro comando usa o cmdlet **Get-JobTrigger** para obter todos os disparadores de trabalho do trabalho agendado SecurityCheck.
O resultado, que exibe as IDs dos disparadores de trabalho, revela que o disparador de trabalho *Once* tem uma ID de 3.

## PARAMETERS

### -Em
Inicia o trabalho em determinada data e hora.
Insira um objeto **DateTime** , como um que o cmdlet Get-Date retorna, ou uma cadeia de caracteres que pode ser convertida em uma hora, como "19 de abril de 2012 15:00", "12/31/2013 9:00 PM" ou "3am".

Se você não especificar um elemento do objeto **DateTime** , como segundos, esse elemento do gatilho do trabalho não será alterado.
Se o gatilho do trabalho original não incluir um objeto **DateTime** e você omitir um elemento, o gatilho do trabalho será criado com o elemento correspondente da data e hora atuais.

Ao usar o parâmetro *Once* , defina o valor do parâmetro *At* para uma determinada data e hora.
Como a data padrão em um objeto **DateTime** é a data atual, definir uma hora antes da hora atual sem uma data explícita resultará em um disparador de trabalho para uma hora no passado.

Os objetos **DateTime** e as cadeias de caracteres que são convertidos em objetos **DateTime** são automaticamente ajustados para serem compatíveis com os formatos de data e hora selecionados para o computador local em região e idioma no painel de controle.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AtLogOn
Inicia o trabalho agendado quando os usuários especificados fazem logon no computador.
Para especificar um usuário, use o parâmetro *User* .

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

### -AtStartup
Inicia o trabalho agendado quando o Windows inicia.

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

### -Diário
Especifica uma agenda recorrente de trabalho diário.
Use os outros parâmetros no conjunto de parâmetros *diário* para especificar os detalhes da agenda.

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

### -DaysInterval
Especifica o número de dias entre ocorrências em uma agenda diária.
Por exemplo, um valor de 3 inicia o trabalho agendado nos dias 1, 4, 7 e assim por diante.
O valor padrão é 1.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DaysOfWeek
Especifica os dias da semana em que um trabalho agendado semanalmente é executado.
Insira nomes de dias, como segunda-feira, quinta-feira, inteiros 0-6, em que 0 representa domingo ou um asterisco ( \* ) para representar todos os dias.
Este parâmetro é necessário no conjunto de parâmetros Semanal.

Nomes de dias são convertidos em seus valores inteiros no gatilho de trabalho.
Quando você coloca os nomes de dias entre aspas em um comando, coloque o nome de cada dia em aspas separadas, como "Segunda-feira", "Terça-feira".
Se você colocar vários nomes de dias em um par de aspas simples, os valores inteiros correspondentes são somados.
Por exemplo, "Segunda-feira, Terça-feira" (1, 2) resulta em um valor de "Quarta-feira" (3).

```yaml
Type: System.DayOfWeek[]
Parameter Sets: (All)
Aliases:
Accepted values: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Especifica os disparadores de trabalho.
Insira uma variável que contenha objetos **ScheduledJobTrigger** ou digite um comando ou uma expressão que obtenha objetos **ScheduledJobTrigger** , como um comando Get-JobTrigger.
Você também pode canalizar um objeto **ScheduledJobTrigger** para **set-JobTrigger** .

Se você especificar vários disparadores de trabalho, o **Set-JobTrigger** realiza as mesmas alterações em todos os disparadores de trabalho.

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Uma vez
Especifica uma agenda não recorrente (uma vez).

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

### -PassThru
Retorna os disparadores de trabalho que foram alterados.
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

### -RandomDelay
Permite um atraso aleatório que começa na hora de início agendada e define o valor de tempo de espera máximo.
O tempo de atraso é definido pseudoaleatoriamente para cada início e varia de nenhum atraso até a hora especificada pelo valor desse parâmetro.
O valor padrão, zero (00:00:00), desabilita o atraso aleatório.

Insira um objeto TimeSpan, como um retornado pelo cmdlet New-TimeSpan, ou insira um valor em \<hours\> : \<minutes\> : \<seconds\> Format, que é automaticamente convertido em um objeto TimeSpan.

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

### -RepeatIndefinitely
Esse parâmetro, disponível a partir do Windows PowerShell 4.0, elimina a necessidade de especificar um valor **TimeSpan.MaxValue** para o parâmetro *RepetitionDuration* para executar um trabalho agendado repetidamente, por um período indefinido.

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

### -RepetitionDuration
Repete o trabalho até o tempo especificado expirar.
A frequência de repetição é determinada pelo valor do parâmetro *RepetitionInterval* .
Por exemplo, se o valor de **RepetitionInterval** for 5 minutos e o valor de *RepetitionDuration* for de 2 horas, o trabalho será acionado a cada cinco minutos por duas horas.

Insira um objeto TimeSpan, como um que o cmdlet New-TimeSpan retorna ou uma cadeia de caracteres que pode ser convertida em um objeto TimeSpan, como "1:05:30".

Para executar um trabalho indefinidamente, adicione o parâmetro *RepeatIndefinitely* em vez disso.

Para interromper um trabalho antes que a duração de repetição do disparador trabalho expire, defina o valor **RepetitionDuration** para zero (0).

Para alterar a duração de repetição ou o intervalo de repetição de um disparador de trabalho *Once* , o comando deve incluir o parâmetro **RepetitionInterval** e **RepetitionDuration** .
Para alterar a duração da repetição ou intervalos de repetição de outros tipos de disparadores de trabalho, o comando deve incluir os parâmetros *Once* , *At* , *RepetitionInterval* e *RepetitionDuration* .

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

### -RepetitionInterval
Repete o trabalho no tempo especificado.
Por exemplo, se o valor desse parâmetro é de 2 horas, o trabalho será acionado a cada duas horas.
O valor padrão, 0, não repete o trabalho.

Insira um objeto TimeSpan, como um que o cmdlet New-TimeSpan retorna ou uma cadeia de caracteres que pode ser convertida em um objeto TimeSpan, como "1:05:30".

Para alterar a duração de repetição ou o intervalo de repetição de um disparador de trabalho **Once** , o comando deve incluir o parâmetro **RepetitionInterval** e **RepetitionDuration** .
Para alterar a duração da repetição ou intervalos de repetição de outros tipos de disparadores de trabalho, o comando deve incluir os parâmetros **Once** , **At** , **RepetitionInterval** e **RepetitionDuration** .

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

### -User
Especifica os usuários que disparam um *AtLogon* no início de um trabalho agendado.
Insira o nome de um usuário no \<UserName\> ou \<Domain\Username\> formate ou insira um asterisco ( \* ) para representar todos os usuários.
O valor padrão é todos os usuários.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Semanal
Especifica uma agenda recorrente de trabalho semanal.
Use os outros parâmetros no parâmetro *semanal* definido para especificar os detalhes da agenda.

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

### -WeeksInterval
Especifica o número de semanas entre ocorrências em uma agenda semanal.
Por exemplo, um valor de 3 inicia o trabalho agendado nas semanas 1, 4, 7 e assim por diante.
O valor padrão é 1.

```yaml
Type: System.Int32
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

### Microsoft. PowerShell. ScheduledJob. ScheduledJobTrigger
É possível canalizar vários gatilhos de trabalho para **set-JobTrigger** .

## SAÍDAS

### Nenhum ou Microsoft. PowerShell. ScheduledJob. ScheduledJobTrigger
Ao usar o parâmetro *Passthru* , o **Set-JobTrigger** retorna os disparadores de trabalho que foram alterados.
Caso contrário, este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

* Disparadores de trabalho têm uma propriedade JobDefintion que os associa com o trabalho agendado. Quando você altera o disparador de trabalho de um trabalho agendado, o trabalho é alterado. Você não precisa usar um comando Set-ScheduledJob para aplicar o gatilho alterado ao trabalho agendado.

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
