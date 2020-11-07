---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-event?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Event
ms.openlocfilehash: 0ab2c32fe81f2e5ffa6c292ce0fd00e05685bd2a
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347696"
---
# <span data-ttu-id="a8663-103">Get-Event</span><span class="sxs-lookup"><span data-stu-id="a8663-103">Get-Event</span></span>

## <span data-ttu-id="a8663-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="a8663-104">SYNOPSIS</span></span>
<span data-ttu-id="a8663-105">Obtém os eventos na fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="a8663-105">Gets the events in the event queue.</span></span>

## <span data-ttu-id="a8663-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a8663-106">SYNTAX</span></span>

### <span data-ttu-id="a8663-107">BySource (padrão)</span><span class="sxs-lookup"><span data-stu-id="a8663-107">BySource (Default)</span></span>

```
Get-Event [[-SourceIdentifier] <String>] [<CommonParameters>]
```

### <span data-ttu-id="a8663-108">ById</span><span class="sxs-lookup"><span data-stu-id="a8663-108">ById</span></span>

```
Get-Event [-EventIdentifier] <Int32> [<CommonParameters>]
```

## <span data-ttu-id="a8663-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a8663-109">DESCRIPTION</span></span>

<span data-ttu-id="a8663-110">O `Get-Event` cmdlet obtém eventos na fila de eventos do PowerShell para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="a8663-110">The `Get-Event` cmdlet gets events in the PowerShell event queue for the current session.</span></span> <span data-ttu-id="a8663-111">Você pode obter todos os eventos ou usar o parâmetro **EventIdentifier** ou **SourceIdentifier** para especificar os eventos.</span><span class="sxs-lookup"><span data-stu-id="a8663-111">You can get all events or use the **EventIdentifier** or **SourceIdentifier** parameter to specify the events.</span></span>

<span data-ttu-id="a8663-112">Quando ocorre um evento, ele é adicionado à fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="a8663-112">When an event occurs, it is added to the event queue.</span></span> <span data-ttu-id="a8663-113">A fila de eventos inclui eventos para os quais você registrou, eventos criados usando o `New-Event` cmdlet e o evento que é gerado quando o PowerShell é encerrado.</span><span class="sxs-lookup"><span data-stu-id="a8663-113">The event queue includes events for which you have registered, events created by using the `New-Event` cmdlet, and the event that is raised when PowerShell exits.</span></span> <span data-ttu-id="a8663-114">Você pode usar `Get-Event` ou `Wait-Event` para obter os eventos.</span><span class="sxs-lookup"><span data-stu-id="a8663-114">You can use `Get-Event` or `Wait-Event` to get the events.</span></span>

<span data-ttu-id="a8663-115">Esse cmdlet não recebe eventos dos logs do Event Viewer.</span><span class="sxs-lookup"><span data-stu-id="a8663-115">This cmdlet does not get events from the Event Viewer logs.</span></span> <span data-ttu-id="a8663-116">Para obter esses eventos, use `Get-WinEvent` ou `Get-EventLog` .</span><span class="sxs-lookup"><span data-stu-id="a8663-116">To get those events, use `Get-WinEvent` or `Get-EventLog`.</span></span>

## <span data-ttu-id="a8663-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="a8663-117">EXAMPLES</span></span>

### <span data-ttu-id="a8663-118">Exemplo 1: obter todos os eventos</span><span class="sxs-lookup"><span data-stu-id="a8663-118">Example 1: Get all events</span></span>

```
PS C:\> Get-Event
```

<span data-ttu-id="a8663-119">Esse comando obtém todos os eventos na fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="a8663-119">This command gets all events in the event queue.</span></span>

### <span data-ttu-id="a8663-120">Exemplo 2: obter eventos por identificador de origem</span><span class="sxs-lookup"><span data-stu-id="a8663-120">Example 2: Get events by source identifier</span></span>

```
PS C:\> Get-Event -SourceIdentifier "PowerShell.ProcessCreated"
```

<span data-ttu-id="a8663-121">Esse comando obtém os eventos nos quais o valor da propriedade SourceIdentifier é PowerShell. ProcessCreated.</span><span class="sxs-lookup"><span data-stu-id="a8663-121">This command gets events in which the value of the SourceIdentifier property is PowerShell.ProcessCreated.</span></span>

### <span data-ttu-id="a8663-122">Exemplo 3: obter um evento com base na hora em que foi gerado</span><span class="sxs-lookup"><span data-stu-id="a8663-122">Example 3: Get an event based on the time it was generated</span></span>

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

<span data-ttu-id="a8663-123">Este exemplo mostra como obter eventos usando propriedades que não sejam SourceIdentifier.</span><span class="sxs-lookup"><span data-stu-id="a8663-123">This example shows how to get events by using properties other than SourceIdentifier.</span></span>

<span data-ttu-id="a8663-124">O primeiro comando obtém todos os eventos na fila de eventos e os salva na `$Events` variável.</span><span class="sxs-lookup"><span data-stu-id="a8663-124">The first command gets all events in the event queue and saves them in the `$Events` variable.</span></span>

<span data-ttu-id="a8663-125">O segundo comando usa a notação de matriz para obter o primeiro evento (0-index) na matriz na `$Events` variável.</span><span class="sxs-lookup"><span data-stu-id="a8663-125">The second command uses array notation to get the first (0-index) event in the array in the `$Events` variable.</span></span> <span data-ttu-id="a8663-126">O comando usa um operador de pipeline ( `|` ) para enviar o evento para o `Format-List` comando, que exibe todas as propriedades do evento em uma lista.</span><span class="sxs-lookup"><span data-stu-id="a8663-126">The command uses a pipeline operator (`|`) to send the event to the `Format-List` command, which displays all properties of the event in a list.</span></span> <span data-ttu-id="a8663-127">Isso permite que você examine as propriedades do objeto de evento.</span><span class="sxs-lookup"><span data-stu-id="a8663-127">This allows you to examine the properties of the event object.</span></span>

<span data-ttu-id="a8663-128">O terceiro comando mostra como usar o `Where-Object` cmdlet para obter um evento com base no horário em que foi gerado.</span><span class="sxs-lookup"><span data-stu-id="a8663-128">The third command shows how to use the `Where-Object` cmdlet to get an event based on the time that it was generated.</span></span>

### <span data-ttu-id="a8663-129">Exemplo 4: obter um evento por seu identificador</span><span class="sxs-lookup"><span data-stu-id="a8663-129">Example 4: Get an event by its identifier</span></span>

```
PS C:\> Get-Event -EventIdentifier 2
```

<span data-ttu-id="a8663-130">Esse comando obtém o evento com um identificador de evento de 2.</span><span class="sxs-lookup"><span data-stu-id="a8663-130">This command gets the event with an event identifier of 2.</span></span>

## <span data-ttu-id="a8663-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a8663-131">PARAMETERS</span></span>

### <span data-ttu-id="a8663-132">-EventIdentifier</span><span class="sxs-lookup"><span data-stu-id="a8663-132">-EventIdentifier</span></span>

<span data-ttu-id="a8663-133">Especifica os identificadores de eventos para os quais esse cmdlet obtém eventos.</span><span class="sxs-lookup"><span data-stu-id="a8663-133">Specifies the event identifiers for which this cmdlet gets events.</span></span>

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

### <span data-ttu-id="a8663-134">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="a8663-134">-SourceIdentifier</span></span>

<span data-ttu-id="a8663-135">Especifica identificadores de origem para os quais este cmdlet obtém eventos.</span><span class="sxs-lookup"><span data-stu-id="a8663-135">Specifies source identifiers for which this cmdlet gets events.</span></span> <span data-ttu-id="a8663-136">O padrão é todos os eventos da fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="a8663-136">The default is all events in the event queue.</span></span> <span data-ttu-id="a8663-137">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="a8663-137">Wildcards are not permitted.</span></span>

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

### <span data-ttu-id="a8663-138">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a8663-138">CommonParameters</span></span>

<span data-ttu-id="a8663-139">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a8663-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a8663-140">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a8663-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a8663-141">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="a8663-141">INPUTS</span></span>

### <span data-ttu-id="a8663-142">Nenhum</span><span class="sxs-lookup"><span data-stu-id="a8663-142">None</span></span>

<span data-ttu-id="a8663-143">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a8663-143">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="a8663-144">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="a8663-144">OUTPUTS</span></span>

### <span data-ttu-id="a8663-145">System. Management. Automation. PSEventArgs</span><span class="sxs-lookup"><span data-stu-id="a8663-145">System.Management.Automation.PSEventArgs</span></span>

<span data-ttu-id="a8663-146">`Get-Event` Retorna um objeto **PSEventArgs** para cada evento.</span><span class="sxs-lookup"><span data-stu-id="a8663-146">`Get-Event` returns a **PSEventArgs** object for each event.</span></span> <span data-ttu-id="a8663-147">Para ver uma descrição desse objeto, digite `Get-Help Get-Event -Full` e veja a seção observações do tópico da ajuda.</span><span class="sxs-lookup"><span data-stu-id="a8663-147">To see a description of this object, type `Get-Help Get-Event -Full` and see the Notes section of the help topic.</span></span>

## <span data-ttu-id="a8663-148">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="a8663-148">NOTES</span></span>

<span data-ttu-id="a8663-149">Nenhuma fonte de eventos disponível nas plataformas Linux ou macOS.</span><span class="sxs-lookup"><span data-stu-id="a8663-149">No event sources available on the Linux or macOS platforms.</span></span>

<span data-ttu-id="a8663-150">Eventos, assinaturas de evento e a fila de eventos existem apenas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="a8663-150">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="a8663-151">Se você fechar a sessão atual, a fila de eventos será descartada e a inscrição do evento será cancelada.</span><span class="sxs-lookup"><span data-stu-id="a8663-151">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

<span data-ttu-id="a8663-152">O `Get-Event` cmdlet retorna um objeto **PSEventArgs** ( **System. Management. Automation. PSEventArgs** ) com as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="a8663-152">The `Get-Event` cmdlet returns a **PSEventArgs** object ( **System.Management.Automation.PSEventArgs** ) with the following properties:</span></span>

- <span data-ttu-id="a8663-153">ComputerName.</span><span class="sxs-lookup"><span data-stu-id="a8663-153">ComputerName.</span></span> <span data-ttu-id="a8663-154">O nome do computador no qual o evento ocorreu.</span><span class="sxs-lookup"><span data-stu-id="a8663-154">The name of the computer on which the event occurred.</span></span> <span data-ttu-id="a8663-155">Esse valor de propriedade é preenchido somente quando o evento é encaminhado de um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="a8663-155">This property value is populated only when the event is forwarded from a remote computer.</span></span>

- <span data-ttu-id="a8663-156">RunspaceId.</span><span class="sxs-lookup"><span data-stu-id="a8663-156">RunspaceId.</span></span> <span data-ttu-id="a8663-157">Um GUID que identifica exclusivamente a sessão na qual o evento ocorreu.</span><span class="sxs-lookup"><span data-stu-id="a8663-157">A GUID that uniquely identifies the session in which the event occurred.</span></span> <span data-ttu-id="a8663-158">Esse valor de propriedade é preenchido somente quando o evento é encaminhado de um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="a8663-158">This property value is populated only when the event is forwarded from a remote computer.</span></span>

- <span data-ttu-id="a8663-159">EventIdentifier.</span><span class="sxs-lookup"><span data-stu-id="a8663-159">EventIdentifier.</span></span> <span data-ttu-id="a8663-160">Um inteiro (Int32) que identifica exclusivamente a notificação de eventos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="a8663-160">An integer (Int32) that uniquely identifies the event notification in the current session.</span></span>

- <span data-ttu-id="a8663-161">Sender.</span><span class="sxs-lookup"><span data-stu-id="a8663-161">Sender.</span></span> <span data-ttu-id="a8663-162">O objeto que gerou o evento.</span><span class="sxs-lookup"><span data-stu-id="a8663-162">The object that generated the event.</span></span> <span data-ttu-id="a8663-163">No valor do parâmetro **Action** , a `$Sender` variável automática contém o objeto Sender.</span><span class="sxs-lookup"><span data-stu-id="a8663-163">In the value of the **Action** parameter, the `$Sender` automatic variable contains the sender object.</span></span>

- <span data-ttu-id="a8663-164">Origemeventargs.</span><span class="sxs-lookup"><span data-stu-id="a8663-164">SourceEventArgs.</span></span> <span data-ttu-id="a8663-165">O primeiro parâmetro deriva de EventArgs, se ele existir.</span><span class="sxs-lookup"><span data-stu-id="a8663-165">The first parameter that derives from EventArgs, if it exists.</span></span> <span data-ttu-id="a8663-166">Por exemplo, em um evento decorrido de temporizador no qual a assinatura tem o formulário object sender, **Timers. ElapsedEventArgs** e, a propriedade **SourceEventArgs** conterá os **Timers. ElapsedEventArgs**.</span><span class="sxs-lookup"><span data-stu-id="a8663-166">For example, in a timer elapsed event in which the signature has the form Object sender, **Timers.ElapsedEventArgs** e, the **SourceEventArgs** property would contain the **Timers.ElapsedEventArgs**.</span></span> <span data-ttu-id="a8663-167">No valor do parâmetro **Action** , a `$EventArgs` variável automática contém esse valor.</span><span class="sxs-lookup"><span data-stu-id="a8663-167">In the value of the **Action** parameter, the `$EventArgs` automatic variable contains this value.</span></span>

- <span data-ttu-id="a8663-168">SourceArgs.</span><span class="sxs-lookup"><span data-stu-id="a8663-168">SourceArgs.</span></span> <span data-ttu-id="a8663-169">Todos os parâmetros da assinatura do evento original.</span><span class="sxs-lookup"><span data-stu-id="a8663-169">All parameters of the original event signature.</span></span> <span data-ttu-id="a8663-170">Para uma assinatura de evento padrão, `$Args[0]` representa o remetente e `$Args[1]` representa a **origemeventargs**.</span><span class="sxs-lookup"><span data-stu-id="a8663-170">For a standard event signature, `$Args[0]` represents the sender, and `$Args[1]` represents the **SourceEventArgs**.</span></span> <span data-ttu-id="a8663-171">No valor do parâmetro **Action** , a `$Args` variável automática contém esse valor.</span><span class="sxs-lookup"><span data-stu-id="a8663-171">In the value of the **Action** parameter, the `$Args` automatic variable contains this value.</span></span>

- <span data-ttu-id="a8663-172">SourceIdentifier.</span><span class="sxs-lookup"><span data-stu-id="a8663-172">SourceIdentifier.</span></span> <span data-ttu-id="a8663-173">Uma cadeia de caracteres que identifica a inscrição do evento.</span><span class="sxs-lookup"><span data-stu-id="a8663-173">A string that identifies the event subscription.</span></span> <span data-ttu-id="a8663-174">No valor do parâmetro **Action** , a propriedade **SourceIdentifier** da `$Event` variável Automatic contém esse valor.</span><span class="sxs-lookup"><span data-stu-id="a8663-174">In the value of the **Action** parameter, the **SourceIdentifier** property of the `$Event` automatic variable contains this value.</span></span>

- <span data-ttu-id="a8663-175">TimeGenerated.</span><span class="sxs-lookup"><span data-stu-id="a8663-175">TimeGenerated.</span></span> <span data-ttu-id="a8663-176">Um objeto **DateTime** que representa a hora em que o evento foi gerado.</span><span class="sxs-lookup"><span data-stu-id="a8663-176">A **DateTime** object that represents the time at which the event was generated.</span></span>
  <span data-ttu-id="a8663-177">No valor do parâmetro **Action** , a propriedade **TimeGenerated** da `$Event` variável Automatic contém esse valor.</span><span class="sxs-lookup"><span data-stu-id="a8663-177">In the value of the **Action** parameter, the **TimeGenerated** property of the `$Event` automatic variable contains this value.</span></span>

- <span data-ttu-id="a8663-178">MessageData.</span><span class="sxs-lookup"><span data-stu-id="a8663-178">MessageData.</span></span> <span data-ttu-id="a8663-179">Dados associados a inscrição do evento.</span><span class="sxs-lookup"><span data-stu-id="a8663-179">Data associated with the event subscription.</span></span> <span data-ttu-id="a8663-180">Os usuários especificam esses dados quando registram um evento.</span><span class="sxs-lookup"><span data-stu-id="a8663-180">Users specify this data when they register an event.</span></span> <span data-ttu-id="a8663-181">No valor do parâmetro **Action** , a propriedade **MessageData** da `$Event` variável Automatic contém esse valor.</span><span class="sxs-lookup"><span data-stu-id="a8663-181">In the value of the **Action** parameter, the **MessageData** property of the `$Event` automatic variable contains this value.</span></span>

## <span data-ttu-id="a8663-182">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="a8663-182">RELATED LINKS</span></span>

[<span data-ttu-id="a8663-183">New-Event</span><span class="sxs-lookup"><span data-stu-id="a8663-183">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="a8663-184">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="a8663-184">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="a8663-185">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="a8663-185">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="a8663-186">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="a8663-186">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="a8663-187">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="a8663-187">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="a8663-188">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="a8663-188">Wait-Event</span></span>](Wait-Event.md)
