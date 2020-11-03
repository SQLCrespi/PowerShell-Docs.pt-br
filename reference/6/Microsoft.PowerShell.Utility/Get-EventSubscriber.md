---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-eventsubscriber?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-EventSubscriber
ms.openlocfilehash: 8f36d2af0fe03685e44070a0b0db86b8a276c4ca
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194483"
---
# Get-EventSubscriber

## SINOPSE
Obtém os assinantes do evento na sessão atual.

## SYNTAX

### BySource (padrão)

```
Get-EventSubscriber [[-SourceIdentifier] <String>] [-Force] [<CommonParameters>]
```

### ById

```
Get-EventSubscriber [-SubscriptionId] <Int32> [-Force] [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Get-EventSubscriber** Obtém os assinantes de eventos na sessão atual.

Quando você assina um evento usando um cmdlet registrar evento, um assinante de evento é adicionado à sua sessão do PowerShell e os eventos nos quais você assinou são adicionados à sua fila de eventos sempre que eles são gerados.
Para cancelar uma inscrição de evento, exclua o assinante de evento usando o cmdlet Unregister-Event.

## EXEMPLOS

### Exemplo 1: obter o Assinante de evento para um evento de timer

```
PS C:\> $Timer = New-Object Timers.Timer
PS C:\> $Timer | Get-Member -Type Event
PS C:\> Register-ObjectEvent -InputObject $Timer -EventName Elapsed -SourceIdentifier Timer.Elapsed
PS C:\> Get-EventSubscriber
PS C:\> $Timer = New-Object Timers.Timer
PS C:\> $Timer | Get-Member -Type Event
TypeName: System.Timers.Timer
Name     MemberType Definition
----     ---------- ----------
Disposed Event      System.EventHandler Disposed(System.Object, System.EventArgs)
Elapsed  Event      System.Timers.ElapsedEventHandler Elapsed(System.Object, System.Timers.ElapsedEventArgs) PS C:\> Register-ObjectEvent -InputObject $Timer -EventName Elapsed -SourceIdentifier Timer.Elapsed
PS C:\> Get-EventSubscriber
SubscriptionId   : 4
SourceObject     : System.Timers.Timer
EventName        : Elapsed
SourceIdentifier : Timer.Elapsed
Action           :
HandlerDelegate  :
SupportEvent     : False
ForwardEvent     : False
```

Este exemplo usa um comando **Get-EventSubscriber** para obter o Assinante de evento para um evento de timer.

O primeiro comando utiliza o cmdlet New-Object para criar uma instância de um objeto temporizador.
Ele salva o novo objeto de timer na variável $Timer.

O segundo comando usa o cmdlet Get-Member para exibir os eventos que estão disponíveis para objetos de temporizador.
O comando usa o parâmetro de tipo do cmdlet **Get-Member** com um valor de Event.

O terceiro comando utiliza o cmdlet Register-ObjectEvent para registrar o evento Elapsed no objeto de temporizador.

O quarto comando usa o cmdlet **Get-EventSubscriber** para obter o assinante do evento decorrido.

### Exemplo 2: usar o módulo dinâmico no PSEventJob na propriedade Action do assinante de evento

```
PS C:\> $Timer = New-Object Timers.Timer
PS C:\> $Timer.Interval = 500
PS C:\> Register-ObjectEvent -InputObject $Timer -EventName Elapsed -SourceIdentifier Timer.Random -Action { $Random = Get-Random -Min 0 -Max 100 }

Id  Name           State      HasMoreData  Location  Command
--  ----           -----      -----------  --------  -------
3   Timer.Random   NotStarted False                  $Random = Get-Random ...

PS C:\> $Timer.Enabled = $True
PS C:\> $Subscriber = Get-EventSubscriber -SourceIdentifier Timer.Random
PS C:\> ($Subscriber.action).gettype().fullname
System.Management.Automation.PSEventJob
PS C:\> $Subscriber.action | Format-List -Property *

State         : Running
Module        : __DynamicModule_6b5cbe82-d634-41d1-ae5e-ad7fe8d57fe0
StatusMessage :
HasMoreData   : True
Location      :
Command       : $random = Get-Random -Min 0 -Max 100
JobStateInfo  : Running
Finished      : System.Threading.ManualResetEvent
InstanceId    : 88944290-133d-4b44-8752-f901bd8012e2
Id            : 1
Name          : Timer.Random
ChildJobs     : {}
...

PS C:\> & $Subscriber.action.module {$Random}
96
PS C:\> & $Subscriber.action.module {$Random}
23
```

Este exemplo mostra como usar o módulo dinâmico no objeto **PSEventJob** na propriedade Action do assinante de evento.

O primeiro comando utiliza o cmdlet New-Object para criar um objeto de timer.
O segundo comando define o intervalo do temporizador para 500 (milissegundos).

O terceiro comando utiliza o cmdlet ObjectEvent Register para registrar o evento decorrido do objeto de timer.
O comando inclui uma ação que manipula o evento.
Sempre que o intervalo de timer expira, um evento é gerado e executar os comandos na ação.
Nesse caso, o cmdlet Get-Random gera um número aleatório entre 0 e 100 e o salva na variável $Random.
O identificador de origem do evento é Timer.Random.

Quando você usa um parâmetro de *ação* em um comando **Register-ObjectEvent** , o comando retorna um objeto **PSEventJob** que representa a ação.

O quarto comando habilita o temporizador.

O quinto comando usa o cmdlet **Get-EventSubscriber** para obter o assinante do evento timer. Random.
Ele salva o objeto de assinante de evento na variável $Subscriber.

O sexto comando mostra que a propriedade Action do objeto de assinante de evento contém um objeto **PSEventJob** .
Na verdade, ele contém o mesmo objeto **PSEventJob** retornado pelo comando **Register-ObjectEvent** .

O sétimo comando usa o cmdlet Format-List para exibir todas as propriedades do objeto **PSEventJob** na propriedade Action em uma lista.
O resultado revela que o objeto **PSEventJob** tem uma Propriedade Module que contém um módulo de script dinâmico que implementa a ação.

Os comandos restantes usam o operador de chamada (&) para invocar o comando no módulo e exibir o valor da variável $Random.
É possível utilizar o operador de chamada para invocar qualquer comando em um módulo, incluindo comandos que não são exportados.
Nesse caso, os comandos mostram o número aleatório que está sendo gerado quando ocorre o evento Elapsed (decorrido).

Para obter mais informações sobre módulos, consulte [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).

## PARAMETERS

### -Force

Indica que esse cmdlet obtém todos os assinantes de evento, incluindo assinantes de eventos que são ocultos usando o parâmetro *SupportEvent* de Register-ObjectEvent, Register-WmiEvent e Register-EngineEvent.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceIdentifier

Especifica o valor da propriedade **SourceIdentifier** que obtém somente os assinantes do evento.
Por padrão, o **Get-EventSubscriber** Obtém todos os assinantes de evento na sessão.
Caracteres curinga não são permitidos.
Este parâmetro diferencia maiúsculas e minúsculas.

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

### -SubscriptionId

Especifica o identificador de assinatura que esse cmdlet obtém.
Por padrão, o **Get-EventSubscriber** Obtém todos os assinantes de evento na sessão.

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### System. Management. Automation. PSEventSubscriber

**Get-EventSubscriber** retorna um objeto que representa cada Assinante de evento.

## OBSERVAÇÕES

* O cmdlet New-Event, que cria um evento personalizado, não gera um assinante. Portanto, o cmdlet **Get-EventSubscriber** não encontrará um objeto de assinante para esses eventos. No entanto, se você usar o cmdlet Register-EngineEvent para assinar um evento personalizado (para encaminhar o evento ou para especificar uma ação), o **Get-EventSubscriber** encontrará o assinante gerado pelo **Register-EngineEvent** .

  Eventos, assinaturas de evento e a fila de eventos existem apenas na sessão atual.
Se você fechar a sessão atual, a fila de eventos será descartada e a inscrição do evento será cancelada.

*

## LINKS RELACIONADOS

[Get-Event](Get-Event.md)

[New-Event](New-Event.md)

[Register-EngineEvent](Register-EngineEvent.md)

[Register-ObjectEvent](Register-ObjectEvent.md)

[Remove-Event](Remove-Event.md)

[Unregister-Event](Unregister-Event.md)

[Wait-Event](Wait-Event.md)
