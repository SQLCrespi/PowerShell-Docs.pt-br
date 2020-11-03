---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/wait-event?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Event
ms.openlocfilehash: 8384cf6a4922bf408f4ac569f651c1a3b584d8af
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194319"
---
# Wait-Event

## SINOPSE
Aguarda até que um determinado evento seja gerado antes de continuar a executar.

## SYNTAX

```
Wait-Event [[-SourceIdentifier] <String>] [-Timeout <Int32>] [<CommonParameters>]
```

## DESCRIPTION

O `Wait-Event` cmdlet suspende a execução de um script ou função até que um evento específico seja gerado. A execução é retomada quando o evento é detectado. Para cancelar a espera, pressione <kbd>Ctrl</kbd> + <kbd>C</kbd>.

Esse recurso fornece uma alternativa às sondagens de evento. Ele também permite que você determine a resposta a um evento de duas maneiras diferentes:

- usando o parâmetro **Action** da assinatura do evento
- aguardando um evento retornar e, em seguida, responder com uma ação

## EXEMPLOS

### Exemplo 1: aguardar o próximo evento

Este exemplo aguarda o próximo evento que é gerado.

```powershell
Wait-Event
```

### Exemplo 2: aguardar um evento com um identificador de origem especificado

Este exemplo aguarda o próximo evento que é gerado e que tem um identificador de origem de ProcessStarted.

```powershell
Wait-Event -SourceIdentifier "ProcessStarted"
```

### Exemplo 3: aguardar um evento decorrido do temporizador

Este exemplo usa o `Wait-Event` cmdlet para aguardar um evento de temporizador em um temporizador definido para 2000 milissegundos.

```powershell
$Timer = New-Object Timers.Timer
$objectEventArgs = @{
    InputObject = $Timer
    EventName = 'Elapsed'
    SourceIdentifier = 'Timer.Elapsed'
}
Register-ObjectEvent @objectEventArgs
$Timer.Interval = 2000
$Timer.Autoreset = $False
$Timer.Enabled = $True
Wait-Event Timer.Elapsed
```

```Output
ComputerName     :
RunspaceId       : bb560b14-ff43-48d4-b801-5adc31bbc6fb
EventIdentifier  : 1
Sender           : System.Timers.Timer
SourceEventArgs  : System.Timers.ElapsedEventArgs
SourceArgs       : {System.Timers.Timer, System.Timers.ElapsedEventArgs}
SourceIdentifier : Timer.Elapsed
TimeGenerated    : 4/23/2020 2:30:37 PM
MessageData      :
```

### Exemplo 4: aguardar um evento após um tempo limite especificado

Este exemplo aguarda até 90 segundos para o próximo evento que é gerado e que tem um identificador de origem de **ProcessStarted** . Se o tempo especificado expirar, a espera terminará.

```powershell
Wait-Event -SourceIdentifier "ProcessStarted" -Timeout 90
```

## PARAMETERS

### -SourceIdentifier

Especifica o identificador de origem que esse cmdlet espera por eventos.
Por padrão, o `Wait-Event` aguarda qualquer evento.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tempo limite

Especifica o tempo máximo, em segundos, que `Wait-Event` aguarda a ocorrência do evento. O padrão, -1, aguarda indefinidamente. O tempo começa quando você envia o `Wait-Event` comando.

Se o tempo especificado for ultrapassado, a espera terminará e o prompt de comando retornará, ainda que o evento não tenha sido ativado. Nenhuma mensagem de erro é exibida.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutSec

Required: False
Position: Named
Default value: -1
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

## SAÍDAS

### System. Management. Automation. PSEventArgs

## OBSERVAÇÕES

Eventos, assinaturas de evento e a fila de eventos existem apenas na sessão atual. Se você fechar a sessão atual, a fila de eventos será descartada e a inscrição do evento será cancelada.

## LINKS RELACIONADOS

[Get-Event](Get-Event.md)

[Get-EventSubscriber](Get-EventSubscriber.md)

[New-Event](New-Event.md)

[Register-EngineEvent](Register-EngineEvent.md)

[Register-ObjectEvent](Register-ObjectEvent.md)

[Remove-Event](Remove-Event.md)

[Unregister-Event](Unregister-Event.md)

[Wait-Event](Wait-Event.md)
