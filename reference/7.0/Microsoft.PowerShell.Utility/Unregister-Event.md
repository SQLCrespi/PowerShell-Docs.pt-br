---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unregister-event?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-Event
ms.openlocfilehash: b7aab2ef1e97ae1cc19d42b07145bd7a057f33fc
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347747"
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

O `Unregister-Event` cmdlet cancela uma assinatura de evento que foi criada usando o `Register-EngineEvent` cmdlet, `Register-ObjectEvent` ou `Register-WmiEvent` .

Quando uma assinatura para um evento é cancelada, o assinante do evento é excluído da sessão e os eventos assinados deixam de ser adicionados à fila de eventos. Quando você cancela uma assinatura para um evento criado usando o `New-Event` cmdlet, o novo evento também é excluído da sessão.

`Unregister-Event` não exclui eventos da fila de eventos. Para excluir eventos, use o `Remove-Event` cmdlet.

## EXEMPLOS

### Exemplo 1: cancelar uma assinatura de evento por identificador de origem

```
PS C:\> Unregister-Event -SourceIdentifier "ProcessStarted"
```

Este comando cancela a assinatura de evento que tem um identificador de origem de ProcessStarted.

Para localizar o identificador de origem de um evento, use o `Get-Event` cmdlet. Para localizar o identificador de origem de uma assinatura de evento, use o `Get-EventSubscriber` cmdlet.

### Exemplo 2: cancelar uma assinatura de evento por identificador de assinatura

```
PS C:\> Unregister-Event -SubscriptionId 2
```

Este comando cancela a assinatura de evento que tem um identificador de assinatura igual a 2.

Para localizar o identificador de assinatura de uma assinatura de evento, use o `Get-EventSubscriber` cmdlet.

### Exemplo 3: cancelar todas as assinaturas de evento

```
PS C:\> Get-EventSubscriber -Force | Unregister-Event -Force
```

Este comando cancela todas as assinaturas de evento presentes na sessão.

O comando usa o `Get-EventSubscriber` cmdlet para obter todos os objetos do assinante de evento na sessão, incluindo os assinantes que estão ocultos usando o parâmetro **SupportEvent** dos cmdlets de registro de evento.

Ele usa um operador de pipeline ( `|` ) para enviar os objetos de assinante para o `Unregister-Event` , que os exclui da sessão. Para concluir a tarefa, o parâmetro **Force** também é necessário em `Unregister-Event` .

## PARAMETERS

### -Force

Cancela todas as assinaturas de evento, incluindo assinaturas que estavam ocultas usando o parâmetro **SupportEvent** de `Register-ObjectEvent` , `Register-WmiEvent` e `Register-EngineEvent` .

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

Um parâmetro **SourceIdentifier** ou **SubscriptionId** deve ser incluído em cada comando.

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

Um parâmetro **SourceIdentifier** ou **SubscriptionId** deve ser incluído em cada comando.

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

### System. Management. Automation. PSEventSubscriber

Você pode canalizar a saída de `Get-EventSubscriber` para `Unregister-Event` .

## SAÍDAS

### Nenhum

Este cmdlet não retorna nenhuma saída.

## OBSERVAÇÕES

Nenhuma fonte de eventos disponível nas plataformas Linux ou macOS.

Eventos, assinaturas de evento e a fila de eventos existem apenas na sessão atual. Se você fechar a sessão atual, a fila de eventos será descartada e a inscrição do evento será cancelada.

`Unregister-Event` Não é possível excluir eventos criados usando o `New-Event` cmdlet, a menos que você tenha assinado o evento usando o `Register-EngineEvent` cmdlet. Para excluir um evento personalizado da sessão, você deve removê-lo programaticamente ou fechar a sessão.

## LINKS RELACIONADOS

[Get-Event](Get-Event.md)

[Get-EventSubscriber](Get-EventSubscriber.md)

[New-Event](New-Event.md)

[Register-EngineEvent](Register-EngineEvent.md)

[Register-ObjectEvent](Register-ObjectEvent.md)

[Remove-Event](Remove-Event.md)

[Unregister-Event](Unregister-Event.md)

[Wait-Event](Wait-Event.md)
