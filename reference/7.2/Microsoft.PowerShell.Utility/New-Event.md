---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-event?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Event
ms.openlocfilehash: 86a4370caccb43edf62af75337afb15f3fb63d7c
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597409"
---
# New-Event

## SINOPSE
Cria um novo evento.

## SYNTAX

```
New-Event [-SourceIdentifier] <String> [[-Sender] <PSObject>] [[-EventArguments] <PSObject[]>]
 [[-MessageData] <PSObject>] [<CommonParameters>]
```

## DESCRIPTION

O `New-Event` cmdlet cria um novo evento personalizado.

Você pode usar eventos personalizados para notificar os usuários sobre as alterações de estado em seu programa e qualquer alteração que seu programa puder detectar, incluindo hardware ou condições do sistema, status de aplicativos, status do disco, status da rede ou a conclusão de um trabalho em segundo plano.

Eventos personalizados são adicionados automaticamente à fila de eventos na sessão sempre que são gerados. Você não precisa se inscrever neles. No entanto, se você quiser encaminhar um evento para a sessão local ou especificar uma ação para responder ao evento, use o `Register-EngineEvent` cmdlet para assinar o evento personalizado.

Quando você se inscreve em um evento personalizado, o assinante do evento é adicionado à sua sessão. Se você cancelar a assinatura de evento usando o `Unregister-Event` cmdlet, o Assinante de evento e o evento personalizado serão excluídos da sessão. Se você não assinar o evento personalizado, para excluir o evento, será necessário alterar as condições do programa ou fechar a sessão do PowerShell.

## EXEMPLOS

### Exemplo 1: criar um novo evento na fila de eventos

```
PS C:\> New-Event -SourceIdentifier Timer -Sender windows.timer -MessageData "Test"
```

Esse comando cria um novo evento na fila de eventos do PowerShell. Ele usa um objeto **Windows. Timer** para enviar o evento.

### Exemplo 2: gerar um evento em resposta a outro evento

```
PS C:\> function Enable-ProcessCreationEvent
{
   $Query = New-Object System.Management.WqlEventQuery "__InstanceCreationEvent", (New-Object TimeSpan 0,0,1), "TargetInstance isa 'Win32_Process'"
   $ProcessWatcher = New-Object System.Management.ManagementEventWatcher $Query
   $Identifier = "WMI.ProcessCreated"
   Register-ObjectEvent $ProcessWatcher "EventArrived" -SupportEvent $Identifier -Action
   {
      [void] (New-Event -SourceID "PowerShell.ProcessCreated" -Sender $Args[0] -EventArguments $Args[1].SourceEventArgs.NewEvent.TargetInstance)
   }
}
```

Esta função de exemplo usa o `New-Event` cmdlet para gerar um evento em resposta a outro evento. O comando usa o `Register-ObjectEvent` cmdlet para assinar o evento Instrumentação de gerenciamento do Windows (WMI) que é gerado quando um novo processo é criado. O comando usa o parâmetro **Action** do cmdlet para chamar o `New-Event` cmdlet, que cria o novo evento.

Como os eventos que `New-Event` geram são automaticamente adicionados à fila de eventos do PowerShell, você não precisa se registrar para esse evento.

## PARAMETERS

### -EventArguments

Especifica um objeto que contém opções para o evento.

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MessageData

Especifica os dados adicionais associados ao evento. O valor desse parâmetro é exibido na propriedade **MessageData** do objeto de evento.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Remetente

Especifica o objeto que gera o evento. O padrão é o mecanismo do PowerShell.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceIdentifier

Especifica um nome para o novo evento. Este parâmetro é obrigatório e deve ser exclusivo na sessão.

O valor desse parâmetro é exibido na propriedade **SourceIdentifier** dos eventos.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
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

### System. Management. Automation. PSEventArgs

## OBSERVAÇÕES

Nenhuma fonte de eventos disponível nas plataformas Linux ou macOS.

O novo evento personalizado, a inscrição do evento e a fila de eventos existem apenas na sessão atual.
Se você fechar a sessão atual, a fila de eventos será descartada e a inscrição do evento será cancelada.

## LINKS RELACIONADOS

[Get-Event](Get-Event.md)

[Register-EngineEvent](Register-EngineEvent.md)

[Register-ObjectEvent](Register-ObjectEvent.md)

[Remove-Event](Remove-Event.md)

[Unregister-Event](Unregister-Event.md)

[Wait-Event](Wait-Event.md)
