---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-event?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Event
ms.openlocfilehash: 4b275d489984f85aea401b781e38c80fbc4b2177
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596997"
---
# <span data-ttu-id="12873-102">Get-Event</span><span class="sxs-lookup"><span data-stu-id="12873-102">Get-Event</span></span>

## <span data-ttu-id="12873-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="12873-103">SYNOPSIS</span></span>
<span data-ttu-id="12873-104">Obtém os eventos na fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="12873-104">Gets the events in the event queue.</span></span>

## <span data-ttu-id="12873-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="12873-105">SYNTAX</span></span>

### <span data-ttu-id="12873-106">BySource (padrão)</span><span class="sxs-lookup"><span data-stu-id="12873-106">BySource (Default)</span></span>

```
Get-Event [[-SourceIdentifier] <String>] [<CommonParameters>]
```

### <span data-ttu-id="12873-107">ById</span><span class="sxs-lookup"><span data-stu-id="12873-107">ById</span></span>

```
Get-Event [-EventIdentifier] <Int32> [<CommonParameters>]
```

## <span data-ttu-id="12873-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="12873-108">DESCRIPTION</span></span>

<span data-ttu-id="12873-109">O `Get-Event` cmdlet obtém eventos na fila de eventos do PowerShell para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="12873-109">The `Get-Event` cmdlet gets events in the PowerShell event queue for the current session.</span></span> <span data-ttu-id="12873-110">Você pode obter todos os eventos ou usar o parâmetro **EventIdentifier** ou **SourceIdentifier** para especificar os eventos.</span><span class="sxs-lookup"><span data-stu-id="12873-110">You can get all events or use the **EventIdentifier** or **SourceIdentifier** parameter to specify the events.</span></span>

<span data-ttu-id="12873-111">Quando ocorre um evento, ele é adicionado à fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="12873-111">When an event occurs, it is added to the event queue.</span></span> <span data-ttu-id="12873-112">A fila de eventos inclui eventos para os quais você registrou, eventos criados usando o `New-Event` cmdlet e o evento que é gerado quando o PowerShell é encerrado.</span><span class="sxs-lookup"><span data-stu-id="12873-112">The event queue includes events for which you have registered, events created by using the `New-Event` cmdlet, and the event that is raised when PowerShell exits.</span></span> <span data-ttu-id="12873-113">Você pode usar `Get-Event` ou `Wait-Event` para obter os eventos.</span><span class="sxs-lookup"><span data-stu-id="12873-113">You can use `Get-Event` or `Wait-Event` to get the events.</span></span>

<span data-ttu-id="12873-114">Esse cmdlet não recebe eventos dos logs do Event Viewer.</span><span class="sxs-lookup"><span data-stu-id="12873-114">This cmdlet does not get events from the Event Viewer logs.</span></span> <span data-ttu-id="12873-115">Para obter esses eventos, use `Get-WinEvent` ou `Get-EventLog` .</span><span class="sxs-lookup"><span data-stu-id="12873-115">To get those events, use `Get-WinEvent` or `Get-EventLog`.</span></span>

## <span data-ttu-id="12873-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="12873-116">EXAMPLES</span></span>

### <span data-ttu-id="12873-117">Exemplo 1: obter todos os eventos</span><span class="sxs-lookup"><span data-stu-id="12873-117">Example 1: Get all events</span></span>

```
PS C:\> Get-Event
```

<span data-ttu-id="12873-118">Esse comando obtém todos os eventos na fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="12873-118">This command gets all events in the event queue.</span></span>

### <span data-ttu-id="12873-119">Exemplo 2: obter eventos por identificador de origem</span><span class="sxs-lookup"><span data-stu-id="12873-119">Example 2: Get events by source identifier</span></span>

```
PS C:\> Get-Event -SourceIdentifier "PowerShell.ProcessCreated"
```

<span data-ttu-id="12873-120">Esse comando obtém os eventos nos quais o valor da propriedade SourceIdentifier é PowerShell. ProcessCreated.</span><span class="sxs-lookup"><span data-stu-id="12873-120">This command gets events in which the value of the SourceIdentifier property is PowerShell.ProcessCreated.</span></span>

### <span data-ttu-id="12873-121">Exemplo 3: obter um evento com base na hora em que foi gerado</span><span class="sxs-lookup"><span data-stu-id="12873-121">Example 3: Get an event based on the time it was generated</span></span>

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

<span data-ttu-id="12873-122">Este exemplo mostra como obter eventos usando propriedades que não sejam SourceIdentifier.</span><span class="sxs-lookup"><span data-stu-id="12873-122">This example shows how to get events by using properties other than SourceIdentifier.</span></span>

<span data-ttu-id="12873-123">O primeiro comando obtém todos os eventos na fila de eventos e os salva na `$Events` variável.</span><span class="sxs-lookup"><span data-stu-id="12873-123">The first command gets all events in the event queue and saves them in the `$Events` variable.</span></span>

<span data-ttu-id="12873-124">O segundo comando usa a notação de matriz para obter o primeiro evento (0-index) na matriz na `$Events` variável.</span><span class="sxs-lookup"><span data-stu-id="12873-124">The second command uses array notation to get the first (0-index) event in the array in the `$Events` variable.</span></span> <span data-ttu-id="12873-125">O comando usa um operador de pipeline ( `|` ) para enviar o evento para o `Format-List` comando, que exibe todas as propriedades do evento em uma lista.</span><span class="sxs-lookup"><span data-stu-id="12873-125">The command uses a pipeline operator (`|`) to send the event to the `Format-List` command, which displays all properties of the event in a list.</span></span> <span data-ttu-id="12873-126">Isso permite que você examine as propriedades do objeto de evento.</span><span class="sxs-lookup"><span data-stu-id="12873-126">This allows you to examine the properties of the event object.</span></span>

<span data-ttu-id="12873-127">O terceiro comando mostra como usar o `Where-Object` cmdlet para obter um evento com base no horário em que foi gerado.</span><span class="sxs-lookup"><span data-stu-id="12873-127">The third command shows how to use the `Where-Object` cmdlet to get an event based on the time that it was generated.</span></span>

### <span data-ttu-id="12873-128">Exemplo 4: obter um evento por seu identificador</span><span class="sxs-lookup"><span data-stu-id="12873-128">Example 4: Get an event by its identifier</span></span>

```
PS C:\> Get-Event -EventIdentifier 2
```

<span data-ttu-id="12873-129">Esse comando obtém o evento com um identificador de evento de 2.</span><span class="sxs-lookup"><span data-stu-id="12873-129">This command gets the event with an event identifier of 2.</span></span>

## <span data-ttu-id="12873-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="12873-130">PARAMETERS</span></span>

### <span data-ttu-id="12873-131">-EventIdentifier</span><span class="sxs-lookup"><span data-stu-id="12873-131">-EventIdentifier</span></span>

<span data-ttu-id="12873-132">Especifica os identificadores de eventos para os quais esse cmdlet obtém eventos.</span><span class="sxs-lookup"><span data-stu-id="12873-132">Specifies the event identifiers for which this cmdlet gets events.</span></span>

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

### <span data-ttu-id="12873-133">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="12873-133">-SourceIdentifier</span></span>

<span data-ttu-id="12873-134">Especifica identificadores de origem para os quais este cmdlet obtém eventos.</span><span class="sxs-lookup"><span data-stu-id="12873-134">Specifies source identifiers for which this cmdlet gets events.</span></span> <span data-ttu-id="12873-135">O padrão é todos os eventos da fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="12873-135">The default is all events in the event queue.</span></span> <span data-ttu-id="12873-136">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="12873-136">Wildcards are not permitted.</span></span>

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

### <span data-ttu-id="12873-137">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="12873-137">CommonParameters</span></span>

<span data-ttu-id="12873-138">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="12873-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="12873-139">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="12873-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="12873-140">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="12873-140">INPUTS</span></span>

### <span data-ttu-id="12873-141">Nenhum</span><span class="sxs-lookup"><span data-stu-id="12873-141">None</span></span>

<span data-ttu-id="12873-142">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="12873-142">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="12873-143">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="12873-143">OUTPUTS</span></span>

### <span data-ttu-id="12873-144">System. Management. Automation. PSEventArgs</span><span class="sxs-lookup"><span data-stu-id="12873-144">System.Management.Automation.PSEventArgs</span></span>

<span data-ttu-id="12873-145">`Get-Event` Retorna um objeto **PSEventArgs** para cada evento.</span><span class="sxs-lookup"><span data-stu-id="12873-145">`Get-Event` returns a **PSEventArgs** object for each event.</span></span> <span data-ttu-id="12873-146">Para ver uma descrição desse objeto, digite `Get-Help Get-Event -Full` e veja a seção observações do tópico da ajuda.</span><span class="sxs-lookup"><span data-stu-id="12873-146">To see a description of this object, type `Get-Help Get-Event -Full` and see the Notes section of the help topic.</span></span>

## <span data-ttu-id="12873-147">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="12873-147">NOTES</span></span>

<span data-ttu-id="12873-148">Nenhuma fonte de eventos disponível nas plataformas Linux ou macOS.</span><span class="sxs-lookup"><span data-stu-id="12873-148">No event sources available on the Linux or macOS platforms.</span></span>

<span data-ttu-id="12873-149">Eventos, assinaturas de evento e a fila de eventos existem apenas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="12873-149">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="12873-150">Se você fechar a sessão atual, a fila de eventos será descartada e a inscrição do evento será cancelada.</span><span class="sxs-lookup"><span data-stu-id="12873-150">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

<span data-ttu-id="12873-151">O `Get-Event` cmdlet retorna um objeto **PSEventArgs** (**System. Management. Automation. PSEventArgs**) com as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="12873-151">The `Get-Event` cmdlet returns a **PSEventArgs** object (**System.Management.Automation.PSEventArgs**) with the following properties:</span></span>

- <span data-ttu-id="12873-152">ComputerName.</span><span class="sxs-lookup"><span data-stu-id="12873-152">ComputerName.</span></span> <span data-ttu-id="12873-153">O nome do computador no qual o evento ocorreu.</span><span class="sxs-lookup"><span data-stu-id="12873-153">The name of the computer on which the event occurred.</span></span> <span data-ttu-id="12873-154">Esse valor de propriedade é preenchido somente quando o evento é encaminhado de um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="12873-154">This property value is populated only when the event is forwarded from a remote computer.</span></span>

- <span data-ttu-id="12873-155">RunspaceId.</span><span class="sxs-lookup"><span data-stu-id="12873-155">RunspaceId.</span></span> <span data-ttu-id="12873-156">Um GUID que identifica exclusivamente a sessão na qual o evento ocorreu.</span><span class="sxs-lookup"><span data-stu-id="12873-156">A GUID that uniquely identifies the session in which the event occurred.</span></span> <span data-ttu-id="12873-157">Esse valor de propriedade é preenchido somente quando o evento é encaminhado de um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="12873-157">This property value is populated only when the event is forwarded from a remote computer.</span></span>

- <span data-ttu-id="12873-158">EventIdentifier.</span><span class="sxs-lookup"><span data-stu-id="12873-158">EventIdentifier.</span></span> <span data-ttu-id="12873-159">Um inteiro (Int32) que identifica exclusivamente a notificação de eventos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="12873-159">An integer (Int32) that uniquely identifies the event notification in the current session.</span></span>

- <span data-ttu-id="12873-160">Sender.</span><span class="sxs-lookup"><span data-stu-id="12873-160">Sender.</span></span> <span data-ttu-id="12873-161">O objeto que gerou o evento.</span><span class="sxs-lookup"><span data-stu-id="12873-161">The object that generated the event.</span></span> <span data-ttu-id="12873-162">No valor do parâmetro **Action** , a `$Sender` variável automática contém o objeto Sender.</span><span class="sxs-lookup"><span data-stu-id="12873-162">In the value of the **Action** parameter, the `$Sender` automatic variable contains the sender object.</span></span>

- <span data-ttu-id="12873-163">Origemeventargs.</span><span class="sxs-lookup"><span data-stu-id="12873-163">SourceEventArgs.</span></span> <span data-ttu-id="12873-164">O primeiro parâmetro deriva de EventArgs, se ele existir.</span><span class="sxs-lookup"><span data-stu-id="12873-164">The first parameter that derives from EventArgs, if it exists.</span></span> <span data-ttu-id="12873-165">Por exemplo, em um evento decorrido de temporizador no qual a assinatura tem o formulário object sender, **Timers. ElapsedEventArgs** e, a propriedade **SourceEventArgs** conterá os **Timers. ElapsedEventArgs**.</span><span class="sxs-lookup"><span data-stu-id="12873-165">For example, in a timer elapsed event in which the signature has the form Object sender, **Timers.ElapsedEventArgs** e, the **SourceEventArgs** property would contain the **Timers.ElapsedEventArgs**.</span></span> <span data-ttu-id="12873-166">No valor do parâmetro **Action** , a `$EventArgs` variável automática contém esse valor.</span><span class="sxs-lookup"><span data-stu-id="12873-166">In the value of the **Action** parameter, the `$EventArgs` automatic variable contains this value.</span></span>

- <span data-ttu-id="12873-167">SourceArgs.</span><span class="sxs-lookup"><span data-stu-id="12873-167">SourceArgs.</span></span> <span data-ttu-id="12873-168">Todos os parâmetros da assinatura do evento original.</span><span class="sxs-lookup"><span data-stu-id="12873-168">All parameters of the original event signature.</span></span> <span data-ttu-id="12873-169">Para uma assinatura de evento padrão, `$Args[0]` representa o remetente e `$Args[1]` representa a **origemeventargs**.</span><span class="sxs-lookup"><span data-stu-id="12873-169">For a standard event signature, `$Args[0]` represents the sender, and `$Args[1]` represents the **SourceEventArgs**.</span></span> <span data-ttu-id="12873-170">No valor do parâmetro **Action** , a `$Args` variável automática contém esse valor.</span><span class="sxs-lookup"><span data-stu-id="12873-170">In the value of the **Action** parameter, the `$Args` automatic variable contains this value.</span></span>

- <span data-ttu-id="12873-171">SourceIdentifier.</span><span class="sxs-lookup"><span data-stu-id="12873-171">SourceIdentifier.</span></span> <span data-ttu-id="12873-172">Uma cadeia de caracteres que identifica a inscrição do evento.</span><span class="sxs-lookup"><span data-stu-id="12873-172">A string that identifies the event subscription.</span></span> <span data-ttu-id="12873-173">No valor do parâmetro **Action** , a propriedade **SourceIdentifier** da `$Event` variável Automatic contém esse valor.</span><span class="sxs-lookup"><span data-stu-id="12873-173">In the value of the **Action** parameter, the **SourceIdentifier** property of the `$Event` automatic variable contains this value.</span></span>

- <span data-ttu-id="12873-174">TimeGenerated.</span><span class="sxs-lookup"><span data-stu-id="12873-174">TimeGenerated.</span></span> <span data-ttu-id="12873-175">Um objeto **DateTime** que representa a hora em que o evento foi gerado.</span><span class="sxs-lookup"><span data-stu-id="12873-175">A **DateTime** object that represents the time at which the event was generated.</span></span>
  <span data-ttu-id="12873-176">No valor do parâmetro **Action** , a propriedade **TimeGenerated** da `$Event` variável Automatic contém esse valor.</span><span class="sxs-lookup"><span data-stu-id="12873-176">In the value of the **Action** parameter, the **TimeGenerated** property of the `$Event` automatic variable contains this value.</span></span>

- <span data-ttu-id="12873-177">MessageData.</span><span class="sxs-lookup"><span data-stu-id="12873-177">MessageData.</span></span> <span data-ttu-id="12873-178">Dados associados a inscrição do evento.</span><span class="sxs-lookup"><span data-stu-id="12873-178">Data associated with the event subscription.</span></span> <span data-ttu-id="12873-179">Os usuários especificam esses dados quando registram um evento.</span><span class="sxs-lookup"><span data-stu-id="12873-179">Users specify this data when they register an event.</span></span> <span data-ttu-id="12873-180">No valor do parâmetro **Action** , a propriedade **MessageData** da `$Event` variável Automatic contém esse valor.</span><span class="sxs-lookup"><span data-stu-id="12873-180">In the value of the **Action** parameter, the **MessageData** property of the `$Event` automatic variable contains this value.</span></span>

## <span data-ttu-id="12873-181">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="12873-181">RELATED LINKS</span></span>

[<span data-ttu-id="12873-182">New-Event</span><span class="sxs-lookup"><span data-stu-id="12873-182">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="12873-183">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="12873-183">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="12873-184">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="12873-184">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="12873-185">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="12873-185">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="12873-186">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="12873-186">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="12873-187">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="12873-187">Wait-Event</span></span>](Wait-Event.md)
