---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-event?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Event
ms.openlocfilehash: 1920d7a834de133b377cdab7e16851c86477c3da
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194494"
---
# Get-Event

## SINOPSE
Obtém os eventos na fila de eventos.

## SYNTAX

### BySource (padrão)

```
Get-Event [[-SourceIdentifier] <String>] [<CommonParameters>]
```

### ById

```
Get-Event [-EventIdentifier] <Int32> [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Get-Event** obtém eventos na fila de eventos do PowerShell para a sessão atual.
Você pode obter todos os eventos ou usar o parâmetro *EventIdentifier* ou *SourceIdentifier* para especificar os eventos.

Quando ocorre um evento, ele é adicionado à fila de eventos.
A fila de eventos inclui eventos para os quais você registrou, eventos criados usando o cmdlet New-Event e o evento que é gerado quando o PowerShell é encerrado.
Você pode usar **Get-Event** ou Wait-Event para obter os eventos.

Esse cmdlet não recebe eventos dos logs do Event Viewer.
Para obter esses eventos, use Get-WinEvent ou Get-EventLog.

## EXEMPLOS

### Exemplo 1: obter todos os eventos

```
PS C:\> Get-Event
```

Esse comando obtém todos os eventos na fila de eventos.

### Exemplo 2: obter eventos por identificador de origem

```
PS C:\> Get-Event -SourceIdentifier "PowerShell.ProcessCreated"
```

Esse comando obtém os eventos nos quais o valor da propriedade SourceIdentifier é PowerShell. ProcessCreated.

### Exemplo 3: obter um evento com base na hora em que foi gerado

```
PS C:\> $Events = Get-Event
PS C:\> $Events[0] | Format-List -Property *
ComputerName     :
RunspaceId       : c2153740-256d-46c0-a57c-b805917d1b7b
EventIdentifier  : 1
Sender           : System.Management.ManagementEventWatcher
SourceEventArgs  : System.Management.EventArrivedEventArgs
SourceArgs       : {System.Management.ManagementEventWatcher, System.Management.EventArrivedEventArgs}
SourceIdentifier : ProcessStarted
TimeGenerated    : 11/13/2008 12:09:32 PM
MessageData      : PS C:\> Get-Event | Where {$_.TimeGenerated -ge "11/13/2008 12:15:00 PM"}
ComputerName     :
RunspaceId       : c2153740-256d-46c0-a57c-b8059325d1a0
EventIdentifier  : 1
Sender           : System.Management.ManagementEventWatcher
SourceEventArgs  : System.Management.EventArrivedEventArgs
SourceArgs       : {System.Management.ManagementEventWatcher, System.Management.EventArrivedEventArgs}
SourceIdentifier : ProcessStarted
TimeGenerated    : 11/13/2008 12:15:00 PM
MessageData      :
```

Este exemplo mostra como obter eventos usando propriedades que não sejam SourceIdentifier.

O primeiro comando obtém todos os eventos na fila de eventos e os salva na variável $Events.

O segundo comando usa a notação de matriz para obter o primeiro evento (0-index) na matriz na variável $Events.
O comando usa um operador de pipeline (|) para enviar o evento para o comando Format-List, que exibe todas as propriedades do evento em uma lista.
Isso permite que você examine as propriedades do objeto de evento.

O terceiro comando mostra como usar o cmdlet Where-Object para obter um evento com base no horário em que foi gerado.

### Exemplo 4: obter um evento por seu identificador

```
PS C:\> Get-Event -EventIdentifier 2
```

Esse comando obtém o evento com um identificador de evento de 2.

## PARAMETERS

### -EventIdentifier

Especifica os identificadores de eventos para os quais esse cmdlet obtém eventos.

```yaml
Type: System.Int32
Parameter Sets: ById
Aliases: Id

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceIdentifier

Especifica identificadores de origem para os quais este cmdlet obtém eventos.
O padrão é todos os eventos da fila de eventos.
Caracteres curinga não são permitidos.

```yaml
Type: System.String
Parameter Sets: BySource
Aliases:

Required: False
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

### System. Management. Automation. PSEventArgs

O **Get-Event** retorna um objeto **PSEventArgs** para cada evento.
Para ver uma descrição desse objeto, digite `Get-Help Get-Event -Full` e veja a seção observações do tópico da ajuda.

## OBSERVAÇÕES

* Eventos, assinaturas de evento e a fila de eventos existem apenas na sessão atual. Se você fechar a sessão atual, a fila de eventos será descartada e a inscrição do evento será cancelada.

  O cmdlet **Get-Event** retorna um objeto **PSEventArgs** ( **System. Management. Automation. PSEventArgs** ) com as seguintes propriedades:

  - ComputerName.
O nome do computador no qual o evento ocorreu.
Esse valor de propriedade é preenchido somente quando o evento é encaminhado de um computador remoto.

  - RunspaceId.
Um GUID que identifica exclusivamente a sessão na qual o evento ocorreu.
Esse valor de propriedade é preenchido somente quando o evento é encaminhado de um computador remoto.

  - EventIdentifier.
Um inteiro (Int32) que identifica exclusivamente a notificação de eventos na sessão atual.

  - Sender.
O objeto que gerou o evento.
No valor do parâmetro *Action* , a variável automática $Sender contém o objeto Sender.

  - Origemeventargs.
O primeiro parâmetro deriva de EventArgs, se ele existir.
Por exemplo, em um evento decorrido de temporizador no qual a assinatura tem o formulário object sender, Timers. ElapsedEventArgs e, a propriedade SourceEventArgs conterá os timers. ElapsedEventArgs.
No valor do parâmetro *Action* , a variável automática $EventArgs contém esse valor.

  - SourceArgs.
Todos os parâmetros da assinatura do evento original.
Para uma assinatura de evento padrão, $Args \[ 0 \] representa o remetente e $args \[ 1 \] representa a origemeventargs.
No valor do parâmetro *Action* , a variável automática $args contém esse valor.

  - SourceIdentifier.
Uma cadeia de caracteres que identifica a inscrição do evento.
No valor do parâmetro *Action* , a propriedade SourceIdentifier da variável automática $Event contém esse valor.

  - TimeGenerated.
Um objeto **DateTime** que representa a hora em que o evento foi gerado.
No valor do parâmetro *Action* , a Propriedade TimeGenerated da variável automática $Event contém esse valor.

  - MessageData.
Dados associados a inscrição do evento.
Os usuários especificam esses dados quando registram um evento.
No valor do parâmetro *Action* , a propriedade MessageData da variável automática $Event contém esse valor.

## LINKS RELACIONADOS

[New-Event](New-Event.md)

[Register-EngineEvent](Register-EngineEvent.md)

[Register-ObjectEvent](Register-ObjectEvent.md)

[Remove-Event](Remove-Event.md)

[Unregister-Event](Unregister-Event.md)

[Wait-Event](Wait-Event.md)
