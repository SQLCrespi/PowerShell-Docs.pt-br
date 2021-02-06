---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/register-objectevent?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-ObjectEvent
ms.openlocfilehash: 89f4d30df0dbc1b74ba28604ed686cad64a3a594
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598612"
---
# Register-ObjectEvent

## SINOPSE
Assina os eventos que são gerados por um objeto do Microsoft .NET Framework.

## SYNTAX

```
Register-ObjectEvent [-InputObject] <PSObject> [-EventName] <String> [[-SourceIdentifier] <String>]
 [[-Action] <ScriptBlock>] [-MessageData <PSObject>] [-SupportEvent] [-Forward] [-MaxTriggerCount <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION

O `Register-ObjectEvent` cmdlet assina eventos gerados por objetos do .net no computador local ou em um computador remoto.

Quando o evento inscrito é gerado, ele é adicionado à fila de eventos em sua sessão. Para obter eventos na fila de eventos, use o `Get-Event` cmdlet.

Você pode usar os parâmetros de `Register-ObjectEvent` para especificar valores de propriedade dos eventos que podem ajudá-lo a identificar o evento na fila. Você também pode usar o parâmetro **Action** para especificar ações a serem tomadas quando um evento assinado for gerado e o parâmetro **Forward** para enviar eventos remotos para a fila de eventos na sessão local.

Quando você se inscreve em um evento, um assinante de evento é adicionado à sua sessão. Para obter os assinantes de evento na sessão, use o `Get-EventSubscriber` cmdlet. Para cancelar a assinatura, use o `Unregister-Event` cmdlet, que exclui o Assinante de evento da sessão.

## EXEMPLOS

### Exemplo 1: assinar eventos quando um novo processo for iniciado

Este exemplo assina eventos gerados quando um novo processo é iniciado.

O comando usa o objeto **ManagementEventWatcher** para obter eventos de **EventArrived** . Um objeto de consulta especifica que os eventos são eventos de criação de instância para a classe **Win32_Process** .

```powershell
$queryParameters = '__InstanceCreationEvent', (New-Object TimeSpan 0,0,1),
    "TargetInstance isa 'Win32_Process'"
$Query = New-Object System.Management.WqlEventQuery -ArgumentList $queryParameters
$ProcessWatcher = New-Object System.Management.ManagementEventWatcher $Query
Register-ObjectEvent -InputObject $ProcessWatcher -EventName "EventArrived"
```

### Exemplo 2: especificar uma ação para responder a um evento

Ao especificar uma ação, eventos que são criados não são adicionados à fila de eventos. Em vez disso, a ação responde ao evento. Neste exemplo, quando um evento de criação de instância é gerado indicando que um novo processo é iniciado, um novo evento **ProcessCreated** é gerado.

```powershell
$queryParameters = '__InstanceCreationEvent', (New-Object TimeSpan 0,0,1),
    "TargetInstance isa 'Win32_Process'"
$Query = New-Object System.Management.WqlEventQuery -ArgumentList $queryParameters
$ProcessWatcher = New-Object System.Management.ManagementEventWatcher $query
$newEventArgs = @{
    SourceIdentifier = 'PowerShell.ProcessCreated'
    Sender = $Sender
    EventArguments = $EventArgs.NewEvent.TargetInstance
}
$Action = { New-Event @newEventArgs }
Register-ObjectEvent -InputObject $ProcessWatcher -EventName "EventArrived" -Action $Action
```

```Output
Id   Name               PSJobTypeName   State       HasMoreData   Location   Command
--   ----               -------------   -----       -----------   --------   -------
 5   3db2d67a-efff-...                 NotStarted   False                    New-Event @newEventArgs
```

A ação usa as `$Sender` `$EventArgs` variáveis automáticas e que são preenchidas somente para ações de evento.

O `Register-ObjectEvent` comando retorna um objeto de trabalho que representa a ação, que é executada como um trabalho em segundo plano. Você pode usar os cmdlets de trabalho, como `Get-Job` e `Receive-Job` , para gerenciar o trabalho em segundo plano. Para obter mais informações, consulte [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md).

### Exemplo 3: assinar eventos de objeto em computadores remotos

Este exemplo mostra como assinar eventos de objetos em computadores remotos. Este exemplo usa a `Enable-ProcessCreationEvent` função que é definida no `ProcessCreationEvent.ps1` arquivo de script. Esse script está disponível para todos os computadores no exemplo.

```powershell
# ProcessCreationEvent.ps1
function  Enable-ProcessCreationEvent {
    $queryParameters = "__InstanceCreationEvent", (New-Object TimeSpan 0,0,1),
        "TargetInstance isa 'Win32_Process'"
    $Query = New-Object System.Management.WqlEventQuery -ArgumentList $queryParameters

    $objectEventArgs = @{
        Input = New-Object System.Management.ManagementEventWatcher $Query
        EventName = 'EventArrived'
        SourceIdentifier = 'WMI.ProcessCreated'
        MessageData = 'Test'
        Forward = $True
    }
    Register-ObjectEvent @objectEventArgs
}

$S = New-PSSession -ComputerName "Server01, Server02"
Invoke-Command -Session $S -FilePath ProcessCreationEvent.ps1
Invoke-Command -Session $S { Enable-ProcessCreationEvent }
```

O primeiro cria **PSSessions** em dois computadores remotos e os salva na `$S` variável. Em seguida, o `Invoke-Command` cmdlet executa o `ProcessCreationEvent.ps1` script em cada uma das PSSessions no `$S` . Essa ação cria a `Enable-ProcessCreationEvent` função nas sessões remotas.
Por fim, executamos a `Enable-ProcessCreationEvent` função nas sessões remotas.

 A função inclui um `Register-ObjectEvent` comando que assina eventos de criação de instância no objeto **Win32_Process** por meio do objeto **ManagementEventWatcher** e seu evento **EventArrived** .

### Exemplo 4: usar o módulo dinâmico no objeto PSEventJob

Este exemplo mostra como usar o módulo dinâmico no objeto **PSEventJob** que é criado quando você inclui uma **ação** em um registro de evento. Primeiro, createand e habilito um objeto Timer e, em seguida, definimos o intervalo do temporizador como 500 (milissegundos). O `Register-ObjectEvent` cmdlet registra o evento **decorrido** do objeto de timer. O objeto **PSEventJob** é salvo na `$Job` variável e também está disponível na propriedade **Action** do assinante de evento. Para obter mais informações, consulte [Get-EventSubscriber](Get-EventSubscriber.md).

Sempre que o intervalo do temporizador expira, um evento é gerado e a ação é executada. Nesse caso, o `Get-Random` cmdlet gera um número aleatório entre 0 e 100 e o salva na `$Random` variável.

```powershell
$Timer = New-Object Timers.Timer
$Timer.Interval = 500
$Timer.Enabled = $True
$objectEventArgs = @{
    InputObject = $Timer
    EventName = 'Elapsed'
    SourceIdentifier = 'Timer.Random'
    Action = {$Random = Get-Random -Min 0 -Max 100}
}
$Job = Register-ObjectEvent @objectEventArgs
$Job | Format-List -Property *
& $Job.module {$Random}
& $Job.module {$Random}
```

```Output
State         : Running
Module        : __DynamicModule_53113769-31f2-42dc-830b-8749325e28d6
StatusMessage :
HasMoreData   : True
Location      :
Command       : $Random = Get-Random -Min 0 -Max 100
JobStateInfo  : Running
Finished      : System.Threading.ManualResetEvent
InstanceId    : 47b5ec9f-bfe3-4605-860a-4674e5d44ca8
Id            : 7
Name          : Timer.Random
ChildJobs     : {}
PSBeginTime   : 6/27/2019 10:19:06 AM
PSEndTime     :
PSJobTypeName :
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
Information   : {}
60
47
```

O **PSEventJob** tem uma propriedade **Module** que contém um módulo de script dinâmico que implementa a ação. Usando o operador Call ( `&` ), invocamos o comando no módulo para exibir o valor da `$Random` variável.

Para obter mais informações sobre módulos, consulte [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).

## PARAMETERS

### -Action

Especifica os comandos para manipular o evento. Os comandos em **Action** são executados quando um evento é gerado, em vez de enviar o evento para a fila de eventos. Coloque os comandos entre chaves ({}) para criar um bloco de script.

O valor do parâmetro **Action** pode incluir as `$Event` `$EventSubscriber` `$Sender` `$EventArgs` variáveis automáticas,,, e `$Args` . Essas variáveis fornecem informações sobre o evento para o bloco de script de **ação** . Para obter mais informações, consulte [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).

Quando você especifica uma ação, `Register-ObjectEvent` o retorna um objeto de trabalho de evento que representa essa ação. É possível utilizar os cmdlets Job para gerenciar o trabalho de eventos.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: 101
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EventName

Especifica o evento que você está assinando.

O valor desse parâmetro deve ser o nome do evento que o objeto .NET expõe. Por exemplo, a classe **ManagementEventWatcher** tem eventos chamados **EventArrived** e **Stopped**. Para localizar o nome do evento de um evento, use o `Get-Member` cmdlet.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Avançar

Indica que o cmdlet envia eventos para essa assinatura para uma sessão remota. Utilize esse parâmetro ao registrar eventos em um computador remoto ou em uma sessão remota.

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

### -InputObject

Especifica o objeto .NET que gera os eventos. Digite uma variável que contém o objeto ou digite um comando ou uma expressão que obtém o objeto.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxTriggerCount

Especifica o número máximo de vezes que um evento pode ser disparado.

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

### -MessageData

Especifica dados adicionais a serem associados essa assinatura do evento. O valor desse parâmetro é exibido na propriedade MessageData de todos os eventos associados a essa assinatura.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceIdentifier

Especifica um nome para a assinatura selecionada. O nome que você selecionar deve ser exclusivo na sessão atual. O valor padrão é o GUID atribuído pelo PowerShell.

O valor desse parâmetro aparece no valor da propriedade **SourceIdentifier** do objeto de assinante e todos os objetos de evento associados a essa assinatura.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 100
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SupportEvent

Indica que o cmdlet oculta a assinatura do evento. Use esse parâmetro quando a assinatura atual fizer parte de um mecanismo de registro de eventos mais complexo e não deve ser descoberta independentemente.

Para exibir ou cancelar uma assinatura que foi criada com o parâmetro **SupportEvent** , use o parâmetro **Force** dos `Get-EventSubscriber` `Unregister-Event` cmdlets e.

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

Não é possível canalizar objetos para `Register-ObjectEvent` .

## SAÍDAS

### Nenhum ou System. Management. Automation. PSEventJob

Quando você usa o parâmetro **Action** , `Register-ObjectEvent` retorna um objeto **System. Management. Automation. PSEventJob** . Caso contrário, ele não gera nenhuma saída.

## OBSERVAÇÕES

Eventos, assinaturas de evento e a fila de eventos existem apenas na sessão atual. Se você fechar a sessão atual, a fila de eventos será descartada e a inscrição do evento será cancelada.

## LINKS RELACIONADOS

[Get-Event](Get-Event.md)

[New-Event](New-Event.md)

[Register-EngineEvent](Register-EngineEvent.md)

[Remove-Event](Remove-Event.md)

[Unregister-Event](Unregister-Event.md)

[Wait-Event](Wait-Event.md)

