---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/new-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-JobTrigger
ms.openlocfilehash: de49ab937c6f3a8187f5aecd6aafc81425b8cd00
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193672"
---
# New-JobTrigger

## SINOPSE
Cria um disparador de trabalho para um trabalho agendado.

## SYNTAX

### Uma vez (padrão)

```
New-JobTrigger [-RandomDelay <TimeSpan>] -At <DateTime> [-Once] [-RepetitionInterval <TimeSpan>]
 [-RepetitionDuration <TimeSpan>] [-RepeatIndefinitely] [<CommonParameters>]
```

### Diário

```
New-JobTrigger [-DaysInterval <Int32>] [-RandomDelay <TimeSpan>] -At <DateTime> [-Daily] [<CommonParameters>]
```

### Semanal

```
New-JobTrigger [-WeeksInterval <Int32>] [-RandomDelay <TimeSpan>] -At <DateTime> -DaysOfWeek <DayOfWeek[]>
 [-Weekly] [<CommonParameters>]
```

### AtStartup

```
New-JobTrigger [-RandomDelay <TimeSpan>] [-AtStartup] [<CommonParameters>]
```

### AtLogon

```
New-JobTrigger [-RandomDelay <TimeSpan>] [-User <String>] [-AtLogOn] [<CommonParameters>]
```

## DESCRIPTION
O cmdlet **New-JobTrigger** cria um gatilho de trabalho que inicia um trabalho agendado em um agendamento de uso único ou recorrente ou quando ocorre um evento.

Você pode usar o objeto **ScheduledJobTrigger** que retorna **New-JobTrigger** para definir um gatilho de trabalho para um trabalho agendado novo ou existente.
Você também pode criar um gatilho de trabalho usando o cmdlet Get-JobTrigger para obter o gatilho de trabalho de um trabalho agendado existente ou usando um valor de tabela de hash para representar um gatilho de trabalho.

Ao criar um gatilho de trabalho, examine os valores padrão das opções especificadas pelo cmdlet New-ScheduledJobOption.
Essas opções, que têm os mesmos valores válido e padrão das opções correspondentes no **Task Scheduler** , afetam o agendamento e o intervalo dos trabalhos agendados.

**New-JobTrigger** é um de uma coleção de cmdlets de agendamento de trabalho no módulo PSScheduledJob que está incluído no Windows PowerShell.

Para obter mais informações sobre trabalhos agendados, consulte os tópicos sobre o módulo PSScheduledJob.
Importe o módulo PSScheduledJob e, em seguida, digite: `Get-Help about_Scheduled*` ou consulte about_Scheduled_Jobs.

Este cmdlet foi introduzido no Windows PowerShell 3.0.

## EXEMPLOS

### Exemplo 1: uma vez agenda

```
PS C:\> New-JobTrigger -Once -At "1/20/2012 3:00 AM"
```

Este comando usa o cmdlet **New-JobTrigger** para criar um gatilho de trabalho que inicia um trabalho agendado apenas uma vez.
O valor do parâmetro *At* é uma cadeia de caracteres que o Windows PowerShell converte em um objeto **DateTime** .
O valor de parâmetro *At* inclui uma data explícita, não apenas uma vez.
Se a data foi omitida, o gatilho seria criado com a data atual e hora de 3h, que é provável que represente uma hora no passado.

### Exemplo 2: agendamento diário

```
PS C:\> New-JobTrigger -Daily -At "4:15 AM" -DaysInterval 3
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
0          Daily           9/21/2012 4:15:00 AM                           True
```

Este comando cria um gatilho de trabalho que inicia um trabalho agendado a cada três dias às 4h15.

Como o valor do parâmetro *At* não inclui uma data, a data atual será usada como valor de data do objeto **DateTime** .
Se a data e a hora estiverem no passado, a tarefa agendada é iniciada na próxima ocorrência, que é 3 dias depois do valor de parâmetro *At* .

### Exemplo 3: agendamento semanal

```
PS C:\> New-JobTrigger -Weekly -DaysOfWeek Monday, Wednesday, Friday -At "23:00" -WeeksInterval 4
Id Frequency Time                  DaysOfWeek                  Enabled
-- --------- ----                  ----------                  -------
0  Weekly    9/21/2012 11:00:00 PM {Monday, Wednesday, Friday} True
```

Este comando cria um gatilho de trabalho que inicia um trabalho agendado a cada 4 semanas na segunda-feira, quarta-feira e sexta-feira às 23 horas (11:00 PM).

Você também pode inserir o valor do parâmetro *DaysOfWeek* em inteiros, como `-DaysOfWeek 1, 5` .

### Exemplo 4: agendamento de logon

```
PS C:\> New-JobTrigger -AtLogOn -User Domain01\Admin01
```

Este comando cria um gatilho de trabalho que inicia um trabalho agendado, sempre que o administrador do domínio faz logon no computador.

### Exemplo 5: usando um atraso aleatório

```
PS C:\> New-JobTrigger -Daily -At 1:00 -RandomDelay 00:20:00
```

Este comando cria um gatilho de trabalho que inicia um trabalho agendado diariamente à 1h da manhã.
O comando usa o parâmetro *RandomDelay* para definir o atraso máximo para 20 minutos.
Como resultado, o trabalho é executado diariamente entre 1h e 1h20, com o intervalo variando pseudo aleatoriamente.

Você pode usar um atraso aleatório para amostragem, balanceamento de carga e outras tarefas administrativas.
Ao definir o valor de atraso, examine os valores efetivo e padrão do cmdlet New-ScheduledJobOption e coordene o atraso com as configurações de opção.

### Exemplo 6: criar um gatilho de trabalho para um novo trabalho agendado

```
The first command uses the **New-JobTrigger** cmdlet to create a job trigger that starts a job every Monday, Wednesday, and Friday at 12:01 AM. The command saves the job trigger in the $T variable.
PS C:\> $T = New-JobTrigger -Weekly -DaysOfWeek 1,3,5 -At 12:01AM


The second command uses the Register-ScheduledJob cmdlet to create a scheduled job that starts a job every Monday, Wednesday, and Friday at 12:01 AM. The value of the *Trigger* parameter is the trigger that is stored in the $T variable.
PS C:\> Register-ScheduledJob -Name Test-HelpFiles -FilePath C:\Scripts\Test-HelpFiles.ps1 -Trigger $T
```

Esses comandos usam um gatilho de trabalho para criar um novo trabalho agendado.

### Exemplo 7: adicionar um gatilho de trabalho a um trabalho agendado

```
PS C:\> Add-JobTrigger -Name SynchronizeApps -Trigger (New-JobTrigger -Daily -At 3:10AM)
```

Este exemplo mostra como adicionar um gatilho de trabalho a um trabalho agendado existente.
Você pode adicionar vários gatilhos de trabalho a qualquer trabalho agendado.

O comando usa o cmdlet Add-JobTrigger para adicionar o gatilho de trabalho ao trabalho agendado SynchronizeApps.
O valor do parâmetro *Trigger* é um comando **New-JobTrigger** que executa o trabalho todos os dias às 3h10.

Quando o comando é concluído, o SynchronizeApps é um trabalho agendado que é executado nos horários especificados pelo gatilho do trabalho.

### Exemplo 8: criar um gatilho de trabalho repetido

```
PS C:\> New-JobTrigger -Once -At "09/12/2013 1:00:00" -RepetitionInterval (New-TimeSpan -Hours 1) -RepetitionDuration (New-Timespan -Hours 48)
```

Este comando cria um gatilho de trabalho que executa um trabalho a cada 60 minutos por 48 horas, começando em 12 de setembro de 2013 às 1:00.

### Exemplo 9: parar um gatilho de trabalho repetido

```
PS C:\> Get-JobTrigger -Name SecurityCheck | Set-JobTrigger -RepetitionInterval 0:00 -RepetitionDuration 0:00
```

Esse comando interrompe forçosamente o trabalho SecurityCheck, que é disparado para ser executado a cada 60 minutos até que seu gatilho de trabalho expire.

Para impedir que o trabalho seja repetido, o comando usa o Get-JobTrigger para obter o gatilho de trabalho do trabalho SecurityCheck e o cmdlet Set-JobTrigger para alterar o intervalo de repetição e a duração da repetição do gatilho de trabalho para zero (0).

### Exemplo 10: criar um gatilho de trabalho por hora

```
PS C:\> New-JobTrigger -Once -At "9/21/2012 0am" -RepetitionInterval (New-TimeSpan -Hour 12) -RepetitionDuration ([TimeSpan]::MaxValue)
```

O comando a seguir cria um gatilho de trabalho que executa um trabalho agendado a cada 12 horas, por um período indefinido de tempo.
A agenda começa amanhã (21/9/2012) à meia-noite (0:00 AM).

## PARAMETERS

### -Em
Inicia o trabalho em determinada data e hora.
Insira um objeto **DateTime** , como um que o cmdlet Get-Date retorna, ou uma cadeia de caracteres que pode ser convertida em uma data e hora, como "19 de abril de 2012 15:00", "12/31" ou "3am".
Se você não especificar um elemento de data, como o ano, a data no gatilho tem o elemento correspondente a partir da data atual.

Ao usar o parâmetro *Once* , defina o valor do parâmetro *At* para uma data e hora futura.
Como a data padrão em um objeto **DateTime** é a data atual, se você especificar uma hora antes da hora atual sem uma data explícita, o gatilho do trabalho será criado para uma hora no passado.

Os objetos **DateTime** e as cadeias de caracteres que são convertidos em objetos **DateTime** são automaticamente ajustados para serem compatíveis com os formatos de data e hora selecionados para o computador local em região e idioma no painel de controle.

```yaml
Type: System.DateTime
Parameter Sets: Once, Daily, Weekly
Aliases:

Required: True
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
Parameter Sets: AtLogon
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AtStartup
Inicia o trabalho agendado quando o Windows inicia.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AtStartup
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Diário
Especifica uma agenda recorrente de trabalho diário.
Use os outros parâmetros no conjunto de parâmetros *diário* para especificar os detalhes da agenda.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Daily
Aliases:

Required: True
Position: 0
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
Parameter Sets: Daily
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DaysOfWeek
Especifica os dias da semana em que um trabalho agendado semanalmente é executado.
Insira os nomes dos dias, como "segunda-feira" ou números inteiros de 0 a 6, onde 0 representa o domingo.
Este parâmetro é necessário no conjunto de parâmetros Semanal.

Nomes de dias são convertidos em seus valores inteiros no gatilho de trabalho.
Quando você coloca os nomes de dias entre aspas em um comando, coloque o nome de cada dia em aspas separadas, como "Segunda-feira", "Terça-feira".
Se você colocar vários nomes de dias em um par de aspas simples, os valores inteiros correspondentes são somados.
Por exemplo, "Segunda-feira, Terça-feira" (1, 2) resulta em um valor de "Quarta-feira" (3).

```yaml
Type: System.DayOfWeek[]
Parameter Sets: Weekly
Aliases:
Accepted values: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Uma vez
Especifica uma agenda personalizada de repetição ou não recorrente (única).
Para criar uma agenda de repetição, use o parâmetro *Once* com os parâmetros *RepetitionDuration* e *RepetitionInterval* .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Once
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RandomDelay
Permite um atraso aleatório que começa na hora de início agendada e define o valor de tempo de espera máximo.
O tempo de atraso é definido pseudoaleatoriamente para cada início e varia de nenhum atraso até a hora especificada pelo valor desse parâmetro.
O valor padrão, zero (00:00:00), desabilita o atraso aleatório.

Insira um objeto TimeSpan, como um retornado pelo cmdlet New-TimeSpan, ou insira um valor em \<hours\> : \<minutes\> : \<seconds\> Format, que é automaticamente convertido em um objeto **TimeSpan** .

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
Parameter Sets: Once
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
Por exemplo, se o valor de **RepetitionInterval** for 5 minutos e o valor de **RepetitionDuration** for de 2 horas, o trabalho será acionado a cada cinco minutos por duas horas.

Insira um objeto TimeSpan, como um que o cmdlet New-TimeSpan retorna ou uma cadeia de caracteres que pode ser convertida em um objeto TimeSpan, como "1:05:30".

Para executar um trabalho indefinidamente, adicione o parâmetro *RepeatIndefinitely* em vez disso.

Para interromper um trabalho antes que a duração da repetição do gatilho de trabalho expire, use o cmdlet Set-JobTrigger para definir o valor de *RepetitionDuration* como zero (0).

Esse parâmetro é válido somente quando os parâmetros *Once* , *At* e *RepetitionInterval* são utilizados no comando.

```yaml
Type: System.TimeSpan
Parameter Sets: Once
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

Esse parâmetro é válido somente quando os parâmetros *Once* , *At* e *RepetitionDuration* são utilizados no comando.

```yaml
Type: System.TimeSpan
Parameter Sets: Once
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
Parameter Sets: AtLogon
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Semanal
Especifica uma agenda recorrente de trabalho semanal.
Use os outros parâmetros no conjunto de parâmetros Semanal para especificar os detalhes da agenda.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Weekly
Aliases:

Required: True
Position: 0
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
Parameter Sets: Weekly
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

### Microsoft. PowerShell. ScheduledJob. ScheduledJobTrigger

## OBSERVAÇÕES

* Gatilhos de trabalho não são salvos em disco. No entanto, os trabalhos agendados são salvos em disco e você pode usar o Get-JobTrigger para obter o gatilho de trabalho de qualquer trabalho agendado.
* **New-JobTrigger** não impede a criação de um gatilho de trabalho que não executará um trabalho agendado, como um gatilho de tempo único para uma data no passado.
* O cmdlet Register-ScheduledJob aceita um objeto ScheduledJobTrigger, como um retornado pelos cmdlets **New-JobTrigger** ou Get-JobTrigger, ou uma tabela de hash com valores de gatilho.

  Para enviar uma tabela de hash, use as seguintes chaves.

  `@{Frequency="Once" (or Daily, Weekly, AtStartup, AtLogon);At="3am"` (ou qualquer cadeia de hora válida); `DaysOfWeek="Monday", "Wednesday"` (ou qualquer combinação de nomes de dias); `Interval=2` (ou qualquer intervalo de frequência válido); `RandomDelay="30minutes"` (ou qualquer cadeia de caracteres TimeSpan válida); `User="Domain1\User01` (ou qualquer usuário válido; usado somente com o valor de frequência *AtLogon* )}

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
