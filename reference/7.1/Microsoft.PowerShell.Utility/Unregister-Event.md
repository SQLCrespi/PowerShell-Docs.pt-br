---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unregister-event?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-Event
ms.openlocfilehash: 748ef22203f59090be6f5491ea76b50d54930a95
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194725"
---
# Unregister-Event

## SINOPSE
Cancela uma assinatura para um evento.

## SYNTAX

### BySource (padrão)

```
Unregister-Event [-SourceIdentifier] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ById

```
Unregister-Event [-SubscriptionId] <Int32> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
O cmdlet cancelar **registro-evento** cancela uma assinatura de evento que foi criada usando o cmdlet Register-EngineEvent, Register-ObjectEvent ou Register-WmiEvent.

Quando uma assinatura para um evento é cancelada, o assinante do evento é excluído da sessão e os eventos assinados deixam de ser adicionados à fila de eventos.
Quando você cancela uma assinatura para um evento criado usando o cmdlet New-Event, o novo evento também é excluído da sessão.

O **cancelamento do registro – evento** não exclui eventos da fila de eventos.
Para excluir eventos, use o cmdlet Remove-Event.

## EXEMPLOS

### Exemplo 1: cancelar uma assinatura de evento por identificador de origem

```
PS C:\> Unregister-Event -SourceIdentifier "ProcessStarted"
```

Este comando cancela a assinatura de evento que tem um identificador de origem de ProcessStarted.

Para localizar o identificador da origem de um evento, use o cmdlet Get-Event.
Para localizar o identificador de origem de uma assinatura de evento, use o cmdlet **Get-EventSubscriber** .

### Exemplo 2: cancelar uma assinatura de evento por identificador de assinatura

```
PS C:\> Unregister-Event -SubscriptionId 2
```

Este comando cancela a assinatura de evento que tem um identificador de assinatura igual a 2.

Para localizar o identificador de assinatura de uma assinatura de evento, use o cmdlet **Get-EventSubscriber** .

### Exemplo 3: cancelar todas as assinaturas de evento

```
PS C:\> Get-EventSubscriber -Force | Unregister-Event -Force
```

Este comando cancela todas as assinaturas de evento presentes na sessão.

O comando usa o cmdlet **Get-EventSubscriber** para obter todos os objetos do assinante de evento na sessão, incluindo os assinantes que estão ocultos usando o parâmetro *SupportEvent* dos cmdlets de registro de eventos.

Ele usa um operador de pipeline (|) para enviar os objetos do assinante para o **cancelamento do registro-evento** , que os exclui da sessão.
Para concluir a tarefa, o parâmetro *Force* também é necessário no **Unregister-Event** .

## PARAMETERS

### -Force
Cancela todas as assinaturas de evento, incluindo as assinaturas que foram ocultadas usando o parâmetro *SupportEvent* de **Register-ObjectEvent** , **Register-WmiEvent** e **Register-EngineEvent** .

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

### -SourceIdentifier
Especifica um identificador de origem que esse cmdlet cancela assinaturas de evento.

Um parâmetro *SourceIdentifier* ou *SubscriptionId* deve ser incluído em cada comando.

```yaml
Type: System.String
Parameter Sets: BySource
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubscriptionId
Especifica uma ID de identificador de origem que esse cmdlet cancela assinaturas de evento.

Um parâmetro *SourceIdentifier* ou *SubscriptionId* deve ser incluído em cada comando.

```yaml
Type: System.Int32
Parameter Sets: ById
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Mostra o que aconteceria se o cmdlet fosse executado.
O cmdlet não é executado.

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

### System. Management. Automation. PSEventSubscriber
Você pode canalizar a saída de Get-EventSubscriber para **cancelar o registro-Event** .

## SAÍDAS

### Nenhum
Este cmdlet não retorna nenhuma saída.

## OBSERVAÇÕES

* Eventos, assinaturas de evento e a fila de eventos existem apenas na sessão atual. Se você fechar a sessão atual, a fila de eventos será descartada e a inscrição do evento será cancelada.

  O **cancelamento do registro – o evento** não pode excluir eventos criados usando o cmdlet New-Event, a menos que você tenha assinado o evento usando o cmdlet **Register-EngineEvent** .
Para excluir um evento personalizado da sessão, você deve removê-lo programaticamente ou fechar a sessão.

*

## LINKS RELACIONADOS

[Get-Event](Get-Event.md)

[Get-EventSubscriber](Get-EventSubscriber.md)

[New-Event](New-Event.md)

[Register-EngineEvent](Register-EngineEvent.md)

[Register-ObjectEvent](Register-ObjectEvent.md)

[Remove-Event](Remove-Event.md)

[Unregister-Event](Unregister-Event.md)

[Wait-Event](Wait-Event.md)

