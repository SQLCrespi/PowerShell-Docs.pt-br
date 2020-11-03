---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-event?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Event
ms.openlocfilehash: 81244e9c32ca1f1d4824bdb8559607b44222c7bd
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193590"
---
# <span data-ttu-id="7ea12-103">Get-Event</span><span class="sxs-lookup"><span data-stu-id="7ea12-103">Get-Event</span></span>

## <span data-ttu-id="7ea12-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="7ea12-104">SYNOPSIS</span></span>
<span data-ttu-id="7ea12-105">Obtém os eventos na fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="7ea12-105">Gets the events in the event queue.</span></span>

## <span data-ttu-id="7ea12-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7ea12-106">SYNTAX</span></span>

### <span data-ttu-id="7ea12-107">BySource (padrão)</span><span class="sxs-lookup"><span data-stu-id="7ea12-107">BySource (Default)</span></span>

```
Get-Event [[-SourceIdentifier] <String>] [<CommonParameters>]
```

### <span data-ttu-id="7ea12-108">ById</span><span class="sxs-lookup"><span data-stu-id="7ea12-108">ById</span></span>

```
Get-Event [-EventIdentifier] <Int32> [<CommonParameters>]
```

## <span data-ttu-id="7ea12-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7ea12-109">DESCRIPTION</span></span>

<span data-ttu-id="7ea12-110">O cmdlet **Get-Event** obtém eventos na fila de eventos do PowerShell para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="7ea12-110">The **Get-Event** cmdlet gets events in the PowerShell event queue for the current session.</span></span>
<span data-ttu-id="7ea12-111">Você pode obter todos os eventos ou usar o parâmetro *EventIdentifier* ou *SourceIdentifier* para especificar os eventos.</span><span class="sxs-lookup"><span data-stu-id="7ea12-111">You can get all events or use the *EventIdentifier* or *SourceIdentifier* parameter to specify the events.</span></span>

<span data-ttu-id="7ea12-112">Quando ocorre um evento, ele é adicionado à fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="7ea12-112">When an event occurs, it is added to the event queue.</span></span>
<span data-ttu-id="7ea12-113">A fila de eventos inclui eventos para os quais você registrou, eventos criados usando o cmdlet New-Event e o evento que é gerado quando o PowerShell é encerrado.</span><span class="sxs-lookup"><span data-stu-id="7ea12-113">The event queue includes events for which you have registered, events created by using the New-Event cmdlet, and the event that is raised when PowerShell exits.</span></span>
<span data-ttu-id="7ea12-114">Você pode usar **Get-Event** ou Wait-Event para obter os eventos.</span><span class="sxs-lookup"><span data-stu-id="7ea12-114">You can use **Get-Event** or Wait-Event to get the events.</span></span>

<span data-ttu-id="7ea12-115">Esse cmdlet não recebe eventos dos logs do Event Viewer.</span><span class="sxs-lookup"><span data-stu-id="7ea12-115">This cmdlet does not get events from the Event Viewer logs.</span></span>
<span data-ttu-id="7ea12-116">Para obter esses eventos, use Get-WinEvent ou Get-EventLog.</span><span class="sxs-lookup"><span data-stu-id="7ea12-116">To get those events, use Get-WinEvent or Get-EventLog.</span></span>

## <span data-ttu-id="7ea12-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="7ea12-117">EXAMPLES</span></span>

### <span data-ttu-id="7ea12-118">Exemplo 1: obter todos os eventos</span><span class="sxs-lookup"><span data-stu-id="7ea12-118">Example 1: Get all events</span></span>

```
PS C:\> Get-Event
```

<span data-ttu-id="7ea12-119">Esse comando obtém todos os eventos na fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="7ea12-119">This command gets all events in the event queue.</span></span>

### <span data-ttu-id="7ea12-120">Exemplo 2: obter eventos por identificador de origem</span><span class="sxs-lookup"><span data-stu-id="7ea12-120">Example 2: Get events by source identifier</span></span>

```
PS C:\> Get-Event -SourceIdentifier "PowerShell.ProcessCreated"
```

<span data-ttu-id="7ea12-121">Esse comando obtém os eventos nos quais o valor da propriedade SourceIdentifier é PowerShell. ProcessCreated.</span><span class="sxs-lookup"><span data-stu-id="7ea12-121">This command gets events in which the value of the SourceIdentifier property is PowerShell.ProcessCreated.</span></span>

### <span data-ttu-id="7ea12-122">Exemplo 3: obter um evento com base na hora em que foi gerado</span><span class="sxs-lookup"><span data-stu-id="7ea12-122">Example 3: Get an event based on the time it was generated</span></span>

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

<span data-ttu-id="7ea12-123">Este exemplo mostra como obter eventos usando propriedades que não sejam SourceIdentifier.</span><span class="sxs-lookup"><span data-stu-id="7ea12-123">This example shows how to get events by using properties other than SourceIdentifier.</span></span>

<span data-ttu-id="7ea12-124">O primeiro comando obtém todos os eventos na fila de eventos e os salva na variável $Events.</span><span class="sxs-lookup"><span data-stu-id="7ea12-124">The first command gets all events in the event queue and saves them in the $Events variable.</span></span>

<span data-ttu-id="7ea12-125">O segundo comando usa a notação de matriz para obter o primeiro evento (0-index) na matriz na variável $Events.</span><span class="sxs-lookup"><span data-stu-id="7ea12-125">The second command uses array notation to get the first (0-index) event in the array in the $Events variable.</span></span>
<span data-ttu-id="7ea12-126">O comando usa um operador de pipeline (|) para enviar o evento para o comando Format-List, que exibe todas as propriedades do evento em uma lista.</span><span class="sxs-lookup"><span data-stu-id="7ea12-126">The command uses a pipeline operator (|) to send the event to the Format-List command, which displays all properties of the event in a list.</span></span>
<span data-ttu-id="7ea12-127">Isso permite que você examine as propriedades do objeto de evento.</span><span class="sxs-lookup"><span data-stu-id="7ea12-127">This allows you to examine the properties of the event object.</span></span>

<span data-ttu-id="7ea12-128">O terceiro comando mostra como usar o cmdlet Where-Object para obter um evento com base no horário em que foi gerado.</span><span class="sxs-lookup"><span data-stu-id="7ea12-128">The third command shows how to use the Where-Object cmdlet to get an event based on the time that it was generated.</span></span>

### <span data-ttu-id="7ea12-129">Exemplo 4: obter um evento por seu identificador</span><span class="sxs-lookup"><span data-stu-id="7ea12-129">Example 4: Get an event by its identifier</span></span>

```
PS C:\> Get-Event -EventIdentifier 2
```

<span data-ttu-id="7ea12-130">Esse comando obtém o evento com um identificador de evento de 2.</span><span class="sxs-lookup"><span data-stu-id="7ea12-130">This command gets the event with an event identifier of 2.</span></span>

## <span data-ttu-id="7ea12-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7ea12-131">PARAMETERS</span></span>

### <span data-ttu-id="7ea12-132">-EventIdentifier</span><span class="sxs-lookup"><span data-stu-id="7ea12-132">-EventIdentifier</span></span>

<span data-ttu-id="7ea12-133">Especifica os identificadores de eventos para os quais esse cmdlet obtém eventos.</span><span class="sxs-lookup"><span data-stu-id="7ea12-133">Specifies the event identifiers for which this cmdlet gets events.</span></span>

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

### <span data-ttu-id="7ea12-134">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="7ea12-134">-SourceIdentifier</span></span>

<span data-ttu-id="7ea12-135">Especifica identificadores de origem para os quais este cmdlet obtém eventos.</span><span class="sxs-lookup"><span data-stu-id="7ea12-135">Specifies source identifiers for which this cmdlet gets events.</span></span>
<span data-ttu-id="7ea12-136">O padrão é todos os eventos da fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="7ea12-136">The default is all events in the event queue.</span></span>
<span data-ttu-id="7ea12-137">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="7ea12-137">Wildcards are not permitted.</span></span>

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

### <span data-ttu-id="7ea12-138">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7ea12-138">CommonParameters</span></span>

<span data-ttu-id="7ea12-139">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7ea12-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7ea12-140">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7ea12-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7ea12-141">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="7ea12-141">INPUTS</span></span>

### <span data-ttu-id="7ea12-142">Nenhum</span><span class="sxs-lookup"><span data-stu-id="7ea12-142">None</span></span>

<span data-ttu-id="7ea12-143">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7ea12-143">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="7ea12-144">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="7ea12-144">OUTPUTS</span></span>

### <span data-ttu-id="7ea12-145">System. Management. Automation. PSEventArgs</span><span class="sxs-lookup"><span data-stu-id="7ea12-145">System.Management.Automation.PSEventArgs</span></span>

<span data-ttu-id="7ea12-146">O **Get-Event** retorna um objeto **PSEventArgs** para cada evento.</span><span class="sxs-lookup"><span data-stu-id="7ea12-146">**Get-Event** returns a **PSEventArgs** object for each event.</span></span>
<span data-ttu-id="7ea12-147">Para ver uma descrição desse objeto, digite `Get-Help Get-Event -Full` e veja a seção observações do tópico da ajuda.</span><span class="sxs-lookup"><span data-stu-id="7ea12-147">To see a description of this object, type `Get-Help Get-Event -Full` and see the Notes section of the help topic.</span></span>

## <span data-ttu-id="7ea12-148">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="7ea12-148">NOTES</span></span>

* <span data-ttu-id="7ea12-149">Eventos, assinaturas de evento e a fila de eventos existem apenas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="7ea12-149">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="7ea12-150">Se você fechar a sessão atual, a fila de eventos será descartada e a inscrição do evento será cancelada.</span><span class="sxs-lookup"><span data-stu-id="7ea12-150">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

  <span data-ttu-id="7ea12-151">O cmdlet **Get-Event** retorna um objeto **PSEventArgs** ( **System. Management. Automation. PSEventArgs** ) com as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="7ea12-151">The **Get-Event** cmdlet returns a **PSEventArgs** object ( **System.Management.Automation.PSEventArgs** ) with the following properties:</span></span>

  - <span data-ttu-id="7ea12-152">ComputerName.</span><span class="sxs-lookup"><span data-stu-id="7ea12-152">ComputerName.</span></span>
<span data-ttu-id="7ea12-153">O nome do computador no qual o evento ocorreu.</span><span class="sxs-lookup"><span data-stu-id="7ea12-153">The name of the computer on which the event occurred.</span></span>
<span data-ttu-id="7ea12-154">Esse valor de propriedade é preenchido somente quando o evento é encaminhado de um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="7ea12-154">This property value is populated only when the event is forwarded from a remote computer.</span></span>

  - <span data-ttu-id="7ea12-155">RunspaceId.</span><span class="sxs-lookup"><span data-stu-id="7ea12-155">RunspaceId.</span></span>
<span data-ttu-id="7ea12-156">Um GUID que identifica exclusivamente a sessão na qual o evento ocorreu.</span><span class="sxs-lookup"><span data-stu-id="7ea12-156">A GUID that uniquely identifies the session in which the event occurred.</span></span>
<span data-ttu-id="7ea12-157">Esse valor de propriedade é preenchido somente quando o evento é encaminhado de um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="7ea12-157">This property value is populated only when the event is forwarded from a remote computer.</span></span>

  - <span data-ttu-id="7ea12-158">EventIdentifier.</span><span class="sxs-lookup"><span data-stu-id="7ea12-158">EventIdentifier.</span></span>
<span data-ttu-id="7ea12-159">Um inteiro (Int32) que identifica exclusivamente a notificação de eventos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="7ea12-159">An integer (Int32) that uniquely identifies the event notification in the current session.</span></span>

  - <span data-ttu-id="7ea12-160">Sender.</span><span class="sxs-lookup"><span data-stu-id="7ea12-160">Sender.</span></span>
<span data-ttu-id="7ea12-161">O objeto que gerou o evento.</span><span class="sxs-lookup"><span data-stu-id="7ea12-161">The object that generated the event.</span></span>
<span data-ttu-id="7ea12-162">No valor do parâmetro *Action* , a variável automática $Sender contém o objeto Sender.</span><span class="sxs-lookup"><span data-stu-id="7ea12-162">In the value of the *Action* parameter, the $Sender automatic variable contains the sender object.</span></span>

  - <span data-ttu-id="7ea12-163">Origemeventargs.</span><span class="sxs-lookup"><span data-stu-id="7ea12-163">SourceEventArgs.</span></span>
<span data-ttu-id="7ea12-164">O primeiro parâmetro deriva de EventArgs, se ele existir.</span><span class="sxs-lookup"><span data-stu-id="7ea12-164">The first parameter that derives from EventArgs, if it exists.</span></span>
<span data-ttu-id="7ea12-165">Por exemplo, em um evento decorrido de temporizador no qual a assinatura tem o formulário object sender, Timers. ElapsedEventArgs e, a propriedade SourceEventArgs conterá os timers. ElapsedEventArgs.</span><span class="sxs-lookup"><span data-stu-id="7ea12-165">For example, in a timer elapsed event in which the signature has the form Object sender, Timers.ElapsedEventArgs e, the SourceEventArgs property would contain the Timers.ElapsedEventArgs.</span></span>
<span data-ttu-id="7ea12-166">No valor do parâmetro *Action* , a variável automática $EventArgs contém esse valor.</span><span class="sxs-lookup"><span data-stu-id="7ea12-166">In the value of the *Action* parameter, the $EventArgs automatic variable contains this value.</span></span>

  - <span data-ttu-id="7ea12-167">SourceArgs.</span><span class="sxs-lookup"><span data-stu-id="7ea12-167">SourceArgs.</span></span>
<span data-ttu-id="7ea12-168">Todos os parâmetros da assinatura do evento original.</span><span class="sxs-lookup"><span data-stu-id="7ea12-168">All parameters of the original event signature.</span></span>
<span data-ttu-id="7ea12-169">Para uma assinatura de evento padrão, $Args \[ 0 \] representa o remetente e $args \[ 1 \] representa a origemeventargs.</span><span class="sxs-lookup"><span data-stu-id="7ea12-169">For a standard event signature, $Args\[0\] represents the sender, and $Args\[1\] represents the SourceEventArgs.</span></span>
<span data-ttu-id="7ea12-170">No valor do parâmetro *Action* , a variável automática $args contém esse valor.</span><span class="sxs-lookup"><span data-stu-id="7ea12-170">In the value of the *Action* parameter, the $Args automatic variable contains this value.</span></span>

  - <span data-ttu-id="7ea12-171">SourceIdentifier.</span><span class="sxs-lookup"><span data-stu-id="7ea12-171">SourceIdentifier.</span></span>
<span data-ttu-id="7ea12-172">Uma cadeia de caracteres que identifica a inscrição do evento.</span><span class="sxs-lookup"><span data-stu-id="7ea12-172">A string that identifies the event subscription.</span></span>
<span data-ttu-id="7ea12-173">No valor do parâmetro *Action* , a propriedade SourceIdentifier da variável automática $Event contém esse valor.</span><span class="sxs-lookup"><span data-stu-id="7ea12-173">In the value of the *Action* parameter, the SourceIdentifier property of the $Event automatic variable contains this value.</span></span>

  - <span data-ttu-id="7ea12-174">TimeGenerated.</span><span class="sxs-lookup"><span data-stu-id="7ea12-174">TimeGenerated.</span></span>
<span data-ttu-id="7ea12-175">Um objeto **DateTime** que representa a hora em que o evento foi gerado.</span><span class="sxs-lookup"><span data-stu-id="7ea12-175">A **DateTime** object that represents the time at which the event was generated.</span></span>
<span data-ttu-id="7ea12-176">No valor do parâmetro *Action* , a Propriedade TimeGenerated da variável automática $Event contém esse valor.</span><span class="sxs-lookup"><span data-stu-id="7ea12-176">In the value of the *Action* parameter, the TimeGenerated property of the $Event automatic variable contains this value.</span></span>

  - <span data-ttu-id="7ea12-177">MessageData.</span><span class="sxs-lookup"><span data-stu-id="7ea12-177">MessageData.</span></span>
<span data-ttu-id="7ea12-178">Dados associados a inscrição do evento.</span><span class="sxs-lookup"><span data-stu-id="7ea12-178">Data associated with the event subscription.</span></span>
<span data-ttu-id="7ea12-179">Os usuários especificam esses dados quando registram um evento.</span><span class="sxs-lookup"><span data-stu-id="7ea12-179">Users specify this data when they register an event.</span></span>
<span data-ttu-id="7ea12-180">No valor do parâmetro *Action* , a propriedade MessageData da variável automática $Event contém esse valor.</span><span class="sxs-lookup"><span data-stu-id="7ea12-180">In the value of the *Action* parameter, the MessageData property of the $Event automatic variable contains this value.</span></span>

## <span data-ttu-id="7ea12-181">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="7ea12-181">RELATED LINKS</span></span>

[<span data-ttu-id="7ea12-182">New-Event</span><span class="sxs-lookup"><span data-stu-id="7ea12-182">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="7ea12-183">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="7ea12-183">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="7ea12-184">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="7ea12-184">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="7ea12-185">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="7ea12-185">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="7ea12-186">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="7ea12-186">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="7ea12-187">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="7ea12-187">Wait-Event</span></span>](Wait-Event.md)

