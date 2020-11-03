---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 02/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/register-engineevent?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-EngineEvent
ms.openlocfilehash: 2adcbcc9e3c933e5c28521f26ec3ae2db03e50f7
ms.sourcegitcommit: f58e4a04240e3419772f9eaa031b626800b615d7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/28/2020
ms.locfileid: "93195094"
---
# Register-EngineEvent

## SINOPSE
Assina eventos que são gerados pelo mecanismo do PowerShell e pelo `New-Event` cmdlet.

## SYNTAX

```
Register-EngineEvent [-SourceIdentifier] <String> [[-Action] <ScriptBlock>] [-MessageData <PSObject>]
 [-SupportEvent] [-Forward] [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

## DESCRIPTION

O `Register-EngineEvent` cmdlet assina eventos que são gerados pelo mecanismo do PowerShell e o `New-Event` cmdlet. Use o parâmetro **SourceIdentifier** para especificar o evento.

Você pode usar este cmdlet para assinar o evento de mecanismo **existente** e eventos gerados pelo `New-Event` cmdlet. Esses eventos são adicionados automaticamente à fila de eventos em sua sessão sem assinatura. No entanto, inscrever-se permite encaminhar eventos, especificar uma ação para responder aos eventos e cancelar a assinatura.

Quando o evento inscrito é gerado, ele é adicionado à fila de eventos em sua sessão. Para obter eventos na fila de eventos, use o `Get-Event` cmdlet.

Quando você assina um evento, um assinante de evento é adicionado à sua sessão. Para obter os assinantes de evento na sessão, use o `Get-EventSubscriber` cmdlet. Para cancelar a assinatura, use o `Unregister-Event` cmdlet, que exclui o Assinante de evento da sessão.

## EXEMPLOS

### Exemplo 1: registrar um evento do mecanismo do PowerShell em computadores remotos

Este exemplo registra um evento do mecanismo do PowerShell em dois computadores remotos.

```powershell
$S = New-PSSession -ComputerName "Server01, Server02"
Invoke-Command -Session $S {
Register-EngineEvent -SourceIdentifier ([System.Management.Automation.PsEngineEvent]::Exiting) -Forward
}
```

`New-PSSession` Cria uma sessão gerenciada pelo usuário (PSSession) em cada um dos computadores remotos. O `Invoke-Command` cmdlet executa o `Register-EngineEvent` comando nas sessões remotas.
`Register-EngineEvent` usa o parâmetro **SourceIdentifier** para identificar o evento. O parâmetro de **encaminhamento** informa ao mecanismo para encaminhar os eventos da sessão remota para a sessão local.

### Exemplo 2: tomar uma ação especificada quando ocorrer o evento de saída

Este exemplo mostra como executar `Register-EngineEvent` para tomar uma ação específica quando ocorre o evento **PowerShell. saindo** .

```powershell
Register-EngineEvent -SourceIdentifier PowerShell.Exiting -SupportEvent -Action {
    Get-History | Export-Clixml $Home\history.clixml
}
```

O parâmetro **SupportEvent** é adicionado para ocultar a assinatura do evento. Quando o PowerShell sai, nesse caso, o histórico de comandos da sessão de saída é exportado um arquivo XML no diretório do usuário `$Home` .

### Exemplo 3: criar e assinar um evento definido pelo usuário

Este exemplo cria uma assinatura para eventos da fonte **Myeventname** . Essa é uma fonte arbitrária que vamos usar para monitorar o progresso de um trabalho. `Register-EngineEvent` é usado para criar a assinatura. O bloco de script para o parâmetro **Action** registra os dados de evento em um arquivo de texto.

```powershell
Register-EngineEvent -SourceIdentifier MyEventSource -Action {
    "Event: {0}" -f $event.messagedata | Out-File c:\temp\MyEvents.txt -Append
}

Start-Job -Name TestJob -ScriptBlock {
    While ($True) {
        Register-EngineEvent -SourceIdentifier MyEventSource -Forward
        Start-Sleep -seconds 2
        "Doing some work..."
        New-Event -SourceIdentifier MyEventSource -Message ("{0} -  Work done..." -f (Get-Date))
    }
}
Start-Sleep -seconds 4
Get-EventSubscriber
Get-Job
```

```Output
SubscriptionId   : 12
SourceObject     :
EventName        :
SourceIdentifier : MyEventSource
Action           : System.Management.Automation.PSEventJob
HandlerDelegate  :
SupportEvent     : False
ForwardEvent     : False

Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
18     MyEventSource                   Running       True                                 …
19     TestJob         BackgroundJob   Running       True            localhost            …
```

`Register-EngineEvent` ID de trabalho criada 18. `Start-Job` ID de trabalho criada 19. No exemplo #4, removemos a assinatura do evento e os trabalhos e, em seguida, inspecionamos o arquivo de log.

### Exemplo 4: cancelar o registro de eventos e limpar trabalhos

Esta é uma continuação do exemplo 3. Neste exemplo, aguardamos 10 segundos para permitir que vários eventos ocorram. Em seguida, cancelamos o registro da assinatura de evento.

```powershell
PS> Start-Sleep -seconds 10
PS> Get-EventSubscriber | Unregister-Event
PS> Get-Job

Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
18     MyEventSource                   Stopped       False                                …
19     TestJob         BackgroundJob   Running       True            localhost            …

PS> Stop-Job -Id 19
PS> Get-Job | Remove-Job
PS> Get-Content C:\temp\MyEvents.txt
Event: 2/18/2020 2:36:19 PM -  Work done...
Event: 2/18/2020 2:36:21 PM -  Work done...
Event: 2/18/2020 2:36:23 PM -  Work done...
Event: 2/18/2020 2:36:25 PM -  Work done...
Event: 2/18/2020 2:36:27 PM -  Work done...
Event: 2/18/2020 2:36:29 PM -  Work done...
Event: 2/18/2020 2:36:31 PM -  Work done...
```

O `Unregister-Event` cmdlet interrompe o trabalho associado à assinatura do evento (ID do trabalho 18). A ID de trabalho 19 ainda está em execução e criando novos eventos. Usamos os cmdlets de **trabalho** param parar o trabalho e remover os objetos de trabalho desnecessários. `Get-Content` exibe o conteúdo do arquivo de log.

## PARAMETERS

### -Action

Especifica os comandos para manipular os eventos. Os comandos em **Action** são executados quando um evento é gerado, em vez de enviar o evento para a fila de eventos. Coloque os comandos entre chaves ({}) para criar um bloco de script.

O valor do parâmetro **Action** pode incluir as `$Event` `$EventSubscriber` `$Sender` `$EventArgs` variáveis automáticas,,, e `$Args` , que fornecem informações sobre o evento para o bloco de script de **ação** . Para obter mais informações, consulte [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).

Quando você especifica uma ação, `Register-EngineEvent` o retorna um objeto de trabalho de evento que representa essa ação. É possível utilizar os cmdlets Job para gerenciar o trabalho de eventos.

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

### -Avançar

Indica que o cmdlet envia eventos para essa assinatura para a sessão no computador local.
Utilize esse parâmetro ao registrar eventos em um computador remoto ou em uma sessão remota.

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

### -MaxTriggerCount

Especifica o número máximo de vezes que a ação será executada para a assinatura do evento.

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

Especifica os dados adicionais associados ao evento. O valor desse parâmetro é exibido na propriedade **MessageData** do objeto de evento.

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

Especifica o identificador de origem do evento ao qual você está se inscrevendo. O identificador de origem deve ser exclusivo na sessão atual. Este parâmetro é necessário.

O valor desse parâmetro aparece no valor da propriedade **SourceIdentifier** do objeto assinante e de todos os objetos de evento associados a esta assinatura.

O valor é específico para a origem do evento. Esse pode ser um valor arbitrário que você criou para usar com o `New-Event` cmdlet. O mecanismo do PowerShell dá suporte aos valores de **EngineEvent** **PowerShell. saindo** e **PowerShell. OnIdle** .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 100
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SupportEvent

Indica que o cmdlet oculta a assinatura do evento. Adicione esse parâmetro quando a assinatura atual fizer parte de um mecanismo de registro de eventos mais complexo e ela não deve ser descoberta independentemente.

Para exibir ou cancelar uma assinatura que foi criada com o parâmetro **SupportEvent** , adicione o parâmetro **Force** aos `Get-EventSubscriber` `Unregister-Event` cmdlets ou.

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

Não é possível canalizar a entrada para `Register-EngineEvent` .

## SAÍDAS

### Nenhum ou System. Management. Automation. PSEventJob

Se você usar o parâmetro **Action** , `Register-EngineEvent` retornará um objeto **System. Management. Automation. PSEventJob** . Caso contrário, ele não gera nenhuma saída.

## OBSERVAÇÕES

Eventos, assinaturas de evento e a fila de eventos existem apenas na sessão atual. Se você fechar a sessão atual, a fila de eventos será descartada e a inscrição do evento será cancelada.

## LINKS RELACIONADOS

[Get-Event](Get-Event.md)

[New-Event](New-Event.md)

[Register-ObjectEvent](Register-ObjectEvent.md)

[Remove-Event](Remove-Event.md)

[Unregister-Event](Unregister-Event.md)

[Wait-Event](Wait-Event.md)

