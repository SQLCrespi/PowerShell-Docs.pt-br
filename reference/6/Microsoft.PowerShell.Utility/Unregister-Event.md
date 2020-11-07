---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unregister-event?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-Event
ms.openlocfilehash: 7aff17c29c8105c79d9bb3955552c75a3a05f752
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94344705"
---
# <span data-ttu-id="a7502-103">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="a7502-103">Unregister-Event</span></span>

## <span data-ttu-id="a7502-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="a7502-104">SYNOPSIS</span></span>
<span data-ttu-id="a7502-105">Cancela uma assinatura para um evento.</span><span class="sxs-lookup"><span data-stu-id="a7502-105">Cancels an event subscription.</span></span>

## <span data-ttu-id="a7502-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a7502-106">SYNTAX</span></span>

### <span data-ttu-id="a7502-107">BySource (padrão)</span><span class="sxs-lookup"><span data-stu-id="a7502-107">BySource (Default)</span></span>

```
Unregister-Event [-SourceIdentifier] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a7502-108">ById</span><span class="sxs-lookup"><span data-stu-id="a7502-108">ById</span></span>

```
Unregister-Event [-SubscriptionId] <Int32> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a7502-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a7502-109">DESCRIPTION</span></span>

<span data-ttu-id="a7502-110">O `Unregister-Event` cmdlet cancela uma assinatura de evento que foi criada usando o `Register-EngineEvent` cmdlet, `Register-ObjectEvent` ou `Register-WmiEvent` .</span><span class="sxs-lookup"><span data-stu-id="a7502-110">The `Unregister-Event` cmdlet cancels an event subscription that was created by using the `Register-EngineEvent`, `Register-ObjectEvent`, or `Register-WmiEvent` cmdlet.</span></span>

<span data-ttu-id="a7502-111">Quando uma assinatura para um evento é cancelada, o assinante do evento é excluído da sessão e os eventos assinados deixam de ser adicionados à fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="a7502-111">When an event subscription is canceled, the event subscriber is deleted from the session and the subscribed events are no longer added to the event queue.</span></span> <span data-ttu-id="a7502-112">Quando você cancela uma assinatura para um evento criado usando o `New-Event` cmdlet, o novo evento também é excluído da sessão.</span><span class="sxs-lookup"><span data-stu-id="a7502-112">When you cancel a subscription to an event created by using the `New-Event` cmdlet, the new event is also deleted from the session.</span></span>

<span data-ttu-id="a7502-113">`Unregister-Event` não exclui eventos da fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="a7502-113">`Unregister-Event` does not delete events from the event queue.</span></span> <span data-ttu-id="a7502-114">Para excluir eventos, use o `Remove-Event` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a7502-114">To delete events, use the `Remove-Event` cmdlet.</span></span>

## <span data-ttu-id="a7502-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="a7502-115">EXAMPLES</span></span>

### <span data-ttu-id="a7502-116">Exemplo 1: cancelar uma assinatura de evento por identificador de origem</span><span class="sxs-lookup"><span data-stu-id="a7502-116">Example 1: Cancel an event subscription by source identifier</span></span>

```
PS C:\> Unregister-Event -SourceIdentifier "ProcessStarted"
```

<span data-ttu-id="a7502-117">Este comando cancela a assinatura de evento que tem um identificador de origem de ProcessStarted.</span><span class="sxs-lookup"><span data-stu-id="a7502-117">This command cancels the event subscription that has a source identifier of ProcessStarted.</span></span>

<span data-ttu-id="a7502-118">Para localizar o identificador de origem de um evento, use o `Get-Event` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a7502-118">To find the source identifier of an event, use the `Get-Event` cmdlet.</span></span> <span data-ttu-id="a7502-119">Para localizar o identificador de origem de uma assinatura de evento, use o `Get-EventSubscriber` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a7502-119">To find the source identifier of an event subscription, use the `Get-EventSubscriber` cmdlet.</span></span>

### <span data-ttu-id="a7502-120">Exemplo 2: cancelar uma assinatura de evento por identificador de assinatura</span><span class="sxs-lookup"><span data-stu-id="a7502-120">Example 2: Cancel an event subscription by subscription identifier</span></span>

```
PS C:\> Unregister-Event -SubscriptionId 2
```

<span data-ttu-id="a7502-121">Este comando cancela a assinatura de evento que tem um identificador de assinatura igual a 2.</span><span class="sxs-lookup"><span data-stu-id="a7502-121">This command cancels the event subscription that has a subscription identifier of 2.</span></span>

<span data-ttu-id="a7502-122">Para localizar o identificador de assinatura de uma assinatura de evento, use o `Get-EventSubscriber` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a7502-122">To find the subscription identifier of an event subscription, use the `Get-EventSubscriber` cmdlet.</span></span>

### <span data-ttu-id="a7502-123">Exemplo 3: cancelar todas as assinaturas de evento</span><span class="sxs-lookup"><span data-stu-id="a7502-123">Example 3: Cancel all event subscriptions</span></span>

```
PS C:\> Get-EventSubscriber -Force | Unregister-Event -Force
```

<span data-ttu-id="a7502-124">Este comando cancela todas as assinaturas de evento presentes na sessão.</span><span class="sxs-lookup"><span data-stu-id="a7502-124">This command cancels all event subscriptions in the session.</span></span>

<span data-ttu-id="a7502-125">O comando usa o `Get-EventSubscriber` cmdlet para obter todos os objetos do assinante de evento na sessão, incluindo os assinantes que estão ocultos usando o parâmetro **SupportEvent** dos cmdlets de registro de evento.</span><span class="sxs-lookup"><span data-stu-id="a7502-125">The command uses the `Get-EventSubscriber` cmdlet to get all event subscriber objects in the session, including the subscribers that are hidden by using the **SupportEvent** parameter of the event registration cmdlets.</span></span>

<span data-ttu-id="a7502-126">Ele usa um operador de pipeline ( `|` ) para enviar os objetos de assinante para o `Unregister-Event` , que os exclui da sessão.</span><span class="sxs-lookup"><span data-stu-id="a7502-126">It uses a pipeline operator (`|`) to send the subscriber objects to `Unregister-Event`, which deletes them from the session.</span></span> <span data-ttu-id="a7502-127">Para concluir a tarefa, o parâmetro **Force** também é necessário em `Unregister-Event` .</span><span class="sxs-lookup"><span data-stu-id="a7502-127">To complete the task, the **Force** parameter is also required on `Unregister-Event`.</span></span>

## <span data-ttu-id="a7502-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a7502-128">PARAMETERS</span></span>

### <span data-ttu-id="a7502-129">-Force</span><span class="sxs-lookup"><span data-stu-id="a7502-129">-Force</span></span>

<span data-ttu-id="a7502-130">Cancela todas as assinaturas de evento, incluindo assinaturas que estavam ocultas usando o parâmetro **SupportEvent** de `Register-ObjectEvent` , `Register-WmiEvent` e `Register-EngineEvent` .</span><span class="sxs-lookup"><span data-stu-id="a7502-130">Cancels all event subscriptions, including subscriptions that were hidden by using the **SupportEvent** parameter of `Register-ObjectEvent`, `Register-WmiEvent`, and `Register-EngineEvent`.</span></span>

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

### <span data-ttu-id="a7502-131">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="a7502-131">-SourceIdentifier</span></span>

<span data-ttu-id="a7502-132">Especifica um identificador de origem que esse cmdlet cancela assinaturas de evento.</span><span class="sxs-lookup"><span data-stu-id="a7502-132">Specifies a source identifier that this cmdlet cancels event subscriptions.</span></span>

<span data-ttu-id="a7502-133">Um parâmetro **SourceIdentifier** ou **SubscriptionId** deve ser incluído em cada comando.</span><span class="sxs-lookup"><span data-stu-id="a7502-133">A **SourceIdentifier** or **SubscriptionId** parameter must be included in every command.</span></span>

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

### <span data-ttu-id="a7502-134">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="a7502-134">-SubscriptionId</span></span>

<span data-ttu-id="a7502-135">Especifica uma ID de identificador de origem que esse cmdlet cancela assinaturas de evento.</span><span class="sxs-lookup"><span data-stu-id="a7502-135">Specifies a source identifier ID that this cmdlet cancels event subscriptions.</span></span>

<span data-ttu-id="a7502-136">Um parâmetro **SourceIdentifier** ou **SubscriptionId** deve ser incluído em cada comando.</span><span class="sxs-lookup"><span data-stu-id="a7502-136">A **SourceIdentifier** or **SubscriptionId** parameter must be included in every command.</span></span>

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

### <span data-ttu-id="a7502-137">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a7502-137">-Confirm</span></span>

<span data-ttu-id="a7502-138">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a7502-138">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a7502-139">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a7502-139">-WhatIf</span></span>

<span data-ttu-id="a7502-140">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="a7502-140">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="a7502-141">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="a7502-141">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a7502-142">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a7502-142">CommonParameters</span></span>

<span data-ttu-id="a7502-143">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a7502-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a7502-144">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a7502-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a7502-145">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="a7502-145">INPUTS</span></span>

### <span data-ttu-id="a7502-146">System. Management. Automation. PSEventSubscriber</span><span class="sxs-lookup"><span data-stu-id="a7502-146">System.Management.Automation.PSEventSubscriber</span></span>

<span data-ttu-id="a7502-147">Você pode canalizar a saída de `Get-EventSubscriber` para `Unregister-Event` .</span><span class="sxs-lookup"><span data-stu-id="a7502-147">You can pipe the output from `Get-EventSubscriber` to `Unregister-Event`.</span></span>

## <span data-ttu-id="a7502-148">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="a7502-148">OUTPUTS</span></span>

### <span data-ttu-id="a7502-149">Nenhum</span><span class="sxs-lookup"><span data-stu-id="a7502-149">None</span></span>

<span data-ttu-id="a7502-150">Este cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="a7502-150">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="a7502-151">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="a7502-151">NOTES</span></span>

<span data-ttu-id="a7502-152">Nenhuma fonte de eventos disponível nas plataformas Linux ou macOS.</span><span class="sxs-lookup"><span data-stu-id="a7502-152">No event sources available on the Linux or macOS platforms.</span></span>

<span data-ttu-id="a7502-153">Eventos, assinaturas de evento e a fila de eventos existem apenas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="a7502-153">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="a7502-154">Se você fechar a sessão atual, a fila de eventos será descartada e a inscrição do evento será cancelada.</span><span class="sxs-lookup"><span data-stu-id="a7502-154">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

<span data-ttu-id="a7502-155">`Unregister-Event` Não é possível excluir eventos criados usando o `New-Event` cmdlet, a menos que você tenha assinado o evento usando o `Register-EngineEvent` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a7502-155">`Unregister-Event` cannot delete events created by using the `New-Event` cmdlet unless you have subscribed to the event by using the `Register-EngineEvent` cmdlet.</span></span> <span data-ttu-id="a7502-156">Para excluir um evento personalizado da sessão, você deve removê-lo programaticamente ou fechar a sessão.</span><span class="sxs-lookup"><span data-stu-id="a7502-156">To delete a custom event from the session, you must remove it programmatically or close the session.</span></span>

## <span data-ttu-id="a7502-157">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="a7502-157">RELATED LINKS</span></span>

[<span data-ttu-id="a7502-158">Get-Event</span><span class="sxs-lookup"><span data-stu-id="a7502-158">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="a7502-159">Get-EventSubscriber</span><span class="sxs-lookup"><span data-stu-id="a7502-159">Get-EventSubscriber</span></span>](Get-EventSubscriber.md)

[<span data-ttu-id="a7502-160">New-Event</span><span class="sxs-lookup"><span data-stu-id="a7502-160">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="a7502-161">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="a7502-161">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="a7502-162">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="a7502-162">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="a7502-163">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="a7502-163">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="a7502-164">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="a7502-164">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="a7502-165">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="a7502-165">Wait-Event</span></span>](Wait-Event.md)
