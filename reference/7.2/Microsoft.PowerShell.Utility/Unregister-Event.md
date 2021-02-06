---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unregister-event?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-Event
ms.openlocfilehash: 863dbba4c106f1f57c9396823692620bb358b646
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597619"
---
# <span data-ttu-id="e5184-102">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="e5184-102">Unregister-Event</span></span>

## <span data-ttu-id="e5184-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="e5184-103">SYNOPSIS</span></span>
<span data-ttu-id="e5184-104">Cancela uma assinatura para um evento.</span><span class="sxs-lookup"><span data-stu-id="e5184-104">Cancels an event subscription.</span></span>

## <span data-ttu-id="e5184-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e5184-105">SYNTAX</span></span>

### <span data-ttu-id="e5184-106">BySource (padrão)</span><span class="sxs-lookup"><span data-stu-id="e5184-106">BySource (Default)</span></span>

```
Unregister-Event [-SourceIdentifier] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e5184-107">ById</span><span class="sxs-lookup"><span data-stu-id="e5184-107">ById</span></span>

```
Unregister-Event [-SubscriptionId] <Int32> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e5184-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e5184-108">DESCRIPTION</span></span>

<span data-ttu-id="e5184-109">O `Unregister-Event` cmdlet cancela uma assinatura de evento que foi criada usando o `Register-EngineEvent` cmdlet, `Register-ObjectEvent` ou `Register-WmiEvent` .</span><span class="sxs-lookup"><span data-stu-id="e5184-109">The `Unregister-Event` cmdlet cancels an event subscription that was created by using the `Register-EngineEvent`, `Register-ObjectEvent`, or `Register-WmiEvent` cmdlet.</span></span>

<span data-ttu-id="e5184-110">Quando uma assinatura para um evento é cancelada, o assinante do evento é excluído da sessão e os eventos assinados deixam de ser adicionados à fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="e5184-110">When an event subscription is canceled, the event subscriber is deleted from the session and the subscribed events are no longer added to the event queue.</span></span> <span data-ttu-id="e5184-111">Quando você cancela uma assinatura para um evento criado usando o `New-Event` cmdlet, o novo evento também é excluído da sessão.</span><span class="sxs-lookup"><span data-stu-id="e5184-111">When you cancel a subscription to an event created by using the `New-Event` cmdlet, the new event is also deleted from the session.</span></span>

<span data-ttu-id="e5184-112">`Unregister-Event` não exclui eventos da fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="e5184-112">`Unregister-Event` does not delete events from the event queue.</span></span> <span data-ttu-id="e5184-113">Para excluir eventos, use o `Remove-Event` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e5184-113">To delete events, use the `Remove-Event` cmdlet.</span></span>

## <span data-ttu-id="e5184-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="e5184-114">EXAMPLES</span></span>

### <span data-ttu-id="e5184-115">Exemplo 1: cancelar uma assinatura de evento por identificador de origem</span><span class="sxs-lookup"><span data-stu-id="e5184-115">Example 1: Cancel an event subscription by source identifier</span></span>

```
PS C:\> Unregister-Event -SourceIdentifier "ProcessStarted"
```

<span data-ttu-id="e5184-116">Este comando cancela a assinatura de evento que tem um identificador de origem de ProcessStarted.</span><span class="sxs-lookup"><span data-stu-id="e5184-116">This command cancels the event subscription that has a source identifier of ProcessStarted.</span></span>

<span data-ttu-id="e5184-117">Para localizar o identificador de origem de um evento, use o `Get-Event` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e5184-117">To find the source identifier of an event, use the `Get-Event` cmdlet.</span></span> <span data-ttu-id="e5184-118">Para localizar o identificador de origem de uma assinatura de evento, use o `Get-EventSubscriber` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e5184-118">To find the source identifier of an event subscription, use the `Get-EventSubscriber` cmdlet.</span></span>

### <span data-ttu-id="e5184-119">Exemplo 2: cancelar uma assinatura de evento por identificador de assinatura</span><span class="sxs-lookup"><span data-stu-id="e5184-119">Example 2: Cancel an event subscription by subscription identifier</span></span>

```
PS C:\> Unregister-Event -SubscriptionId 2
```

<span data-ttu-id="e5184-120">Este comando cancela a assinatura de evento que tem um identificador de assinatura igual a 2.</span><span class="sxs-lookup"><span data-stu-id="e5184-120">This command cancels the event subscription that has a subscription identifier of 2.</span></span>

<span data-ttu-id="e5184-121">Para localizar o identificador de assinatura de uma assinatura de evento, use o `Get-EventSubscriber` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e5184-121">To find the subscription identifier of an event subscription, use the `Get-EventSubscriber` cmdlet.</span></span>

### <span data-ttu-id="e5184-122">Exemplo 3: cancelar todas as assinaturas de evento</span><span class="sxs-lookup"><span data-stu-id="e5184-122">Example 3: Cancel all event subscriptions</span></span>

```
PS C:\> Get-EventSubscriber -Force | Unregister-Event -Force
```

<span data-ttu-id="e5184-123">Este comando cancela todas as assinaturas de evento presentes na sessão.</span><span class="sxs-lookup"><span data-stu-id="e5184-123">This command cancels all event subscriptions in the session.</span></span>

<span data-ttu-id="e5184-124">O comando usa o `Get-EventSubscriber` cmdlet para obter todos os objetos do assinante de evento na sessão, incluindo os assinantes que estão ocultos usando o parâmetro **SupportEvent** dos cmdlets de registro de evento.</span><span class="sxs-lookup"><span data-stu-id="e5184-124">The command uses the `Get-EventSubscriber` cmdlet to get all event subscriber objects in the session, including the subscribers that are hidden by using the **SupportEvent** parameter of the event registration cmdlets.</span></span>

<span data-ttu-id="e5184-125">Ele usa um operador de pipeline ( `|` ) para enviar os objetos de assinante para o `Unregister-Event` , que os exclui da sessão.</span><span class="sxs-lookup"><span data-stu-id="e5184-125">It uses a pipeline operator (`|`) to send the subscriber objects to `Unregister-Event`, which deletes them from the session.</span></span> <span data-ttu-id="e5184-126">Para concluir a tarefa, o parâmetro **Force** também é necessário em `Unregister-Event` .</span><span class="sxs-lookup"><span data-stu-id="e5184-126">To complete the task, the **Force** parameter is also required on `Unregister-Event`.</span></span>

## <span data-ttu-id="e5184-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e5184-127">PARAMETERS</span></span>

### <span data-ttu-id="e5184-128">-Force</span><span class="sxs-lookup"><span data-stu-id="e5184-128">-Force</span></span>

<span data-ttu-id="e5184-129">Cancela todas as assinaturas de evento, incluindo assinaturas que estavam ocultas usando o parâmetro **SupportEvent** de `Register-ObjectEvent` , `Register-WmiEvent` e `Register-EngineEvent` .</span><span class="sxs-lookup"><span data-stu-id="e5184-129">Cancels all event subscriptions, including subscriptions that were hidden by using the **SupportEvent** parameter of `Register-ObjectEvent`, `Register-WmiEvent`, and `Register-EngineEvent`.</span></span>

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

### <span data-ttu-id="e5184-130">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="e5184-130">-SourceIdentifier</span></span>

<span data-ttu-id="e5184-131">Especifica um identificador de origem que esse cmdlet cancela assinaturas de evento.</span><span class="sxs-lookup"><span data-stu-id="e5184-131">Specifies a source identifier that this cmdlet cancels event subscriptions.</span></span>

<span data-ttu-id="e5184-132">Um parâmetro **SourceIdentifier** ou **SubscriptionId** deve ser incluído em cada comando.</span><span class="sxs-lookup"><span data-stu-id="e5184-132">A **SourceIdentifier** or **SubscriptionId** parameter must be included in every command.</span></span>

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

### <span data-ttu-id="e5184-133">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="e5184-133">-SubscriptionId</span></span>

<span data-ttu-id="e5184-134">Especifica uma ID de identificador de origem que esse cmdlet cancela assinaturas de evento.</span><span class="sxs-lookup"><span data-stu-id="e5184-134">Specifies a source identifier ID that this cmdlet cancels event subscriptions.</span></span>

<span data-ttu-id="e5184-135">Um parâmetro **SourceIdentifier** ou **SubscriptionId** deve ser incluído em cada comando.</span><span class="sxs-lookup"><span data-stu-id="e5184-135">A **SourceIdentifier** or **SubscriptionId** parameter must be included in every command.</span></span>

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

### <span data-ttu-id="e5184-136">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e5184-136">-Confirm</span></span>

<span data-ttu-id="e5184-137">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e5184-137">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e5184-138">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e5184-138">-WhatIf</span></span>

<span data-ttu-id="e5184-139">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="e5184-139">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="e5184-140">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="e5184-140">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e5184-141">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e5184-141">CommonParameters</span></span>

<span data-ttu-id="e5184-142">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e5184-142">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e5184-143">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e5184-143">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e5184-144">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="e5184-144">INPUTS</span></span>

### <span data-ttu-id="e5184-145">System. Management. Automation. PSEventSubscriber</span><span class="sxs-lookup"><span data-stu-id="e5184-145">System.Management.Automation.PSEventSubscriber</span></span>

<span data-ttu-id="e5184-146">Você pode canalizar a saída de `Get-EventSubscriber` para `Unregister-Event` .</span><span class="sxs-lookup"><span data-stu-id="e5184-146">You can pipe the output from `Get-EventSubscriber` to `Unregister-Event`.</span></span>

## <span data-ttu-id="e5184-147">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="e5184-147">OUTPUTS</span></span>

### <span data-ttu-id="e5184-148">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e5184-148">None</span></span>

<span data-ttu-id="e5184-149">Este cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="e5184-149">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="e5184-150">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="e5184-150">NOTES</span></span>

<span data-ttu-id="e5184-151">Nenhuma fonte de eventos disponível nas plataformas Linux ou macOS.</span><span class="sxs-lookup"><span data-stu-id="e5184-151">No event sources available on the Linux or macOS platforms.</span></span>

<span data-ttu-id="e5184-152">Eventos, assinaturas de evento e a fila de eventos existem apenas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="e5184-152">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="e5184-153">Se você fechar a sessão atual, a fila de eventos será descartada e a inscrição do evento será cancelada.</span><span class="sxs-lookup"><span data-stu-id="e5184-153">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

<span data-ttu-id="e5184-154">`Unregister-Event` Não é possível excluir eventos criados usando o `New-Event` cmdlet, a menos que você tenha assinado o evento usando o `Register-EngineEvent` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e5184-154">`Unregister-Event` cannot delete events created by using the `New-Event` cmdlet unless you have subscribed to the event by using the `Register-EngineEvent` cmdlet.</span></span> <span data-ttu-id="e5184-155">Para excluir um evento personalizado da sessão, você deve removê-lo programaticamente ou fechar a sessão.</span><span class="sxs-lookup"><span data-stu-id="e5184-155">To delete a custom event from the session, you must remove it programmatically or close the session.</span></span>

## <span data-ttu-id="e5184-156">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="e5184-156">RELATED LINKS</span></span>

[<span data-ttu-id="e5184-157">Get-Event</span><span class="sxs-lookup"><span data-stu-id="e5184-157">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="e5184-158">Get-EventSubscriber</span><span class="sxs-lookup"><span data-stu-id="e5184-158">Get-EventSubscriber</span></span>](Get-EventSubscriber.md)

[<span data-ttu-id="e5184-159">New-Event</span><span class="sxs-lookup"><span data-stu-id="e5184-159">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="e5184-160">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="e5184-160">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="e5184-161">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="e5184-161">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="e5184-162">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="e5184-162">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="e5184-163">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="e5184-163">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="e5184-164">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="e5184-164">Wait-Event</span></span>](Wait-Event.md)
