---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-event?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Event
ms.openlocfilehash: cf7236d31ccd248701a0464c84e94d0d910cc26f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194330"
---
# <span data-ttu-id="5f8f3-103">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="5f8f3-103">Remove-Event</span></span>

## <span data-ttu-id="5f8f3-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="5f8f3-104">SYNOPSIS</span></span>
<span data-ttu-id="5f8f3-105">Exclui eventos da fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="5f8f3-105">Deletes events from the event queue.</span></span>

## <span data-ttu-id="5f8f3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5f8f3-106">SYNTAX</span></span>

### <span data-ttu-id="5f8f3-107">BySource (padrão)</span><span class="sxs-lookup"><span data-stu-id="5f8f3-107">BySource (Default)</span></span>

```
Remove-Event [-SourceIdentifier] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5f8f3-108">ByIdentifier</span><span class="sxs-lookup"><span data-stu-id="5f8f3-108">ByIdentifier</span></span>

```
Remove-Event [-EventIdentifier] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="5f8f3-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5f8f3-109">DESCRIPTION</span></span>
<span data-ttu-id="5f8f3-110">O cmdlet **Remove-Event** exclui eventos da fila de eventos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="5f8f3-110">The **Remove-Event** cmdlet deletes events from the event queue in the current session.</span></span>

<span data-ttu-id="5f8f3-111">Este cmdlet exclui somente os eventos atualmente na fila.</span><span class="sxs-lookup"><span data-stu-id="5f8f3-111">This cmdlet deletes only the events currently in the queue.</span></span>
<span data-ttu-id="5f8f3-112">Para cancelar inscrições de evento ou cancelar a assinatura, use o cmdlet Unregister-Event.</span><span class="sxs-lookup"><span data-stu-id="5f8f3-112">To cancel event registrations or unsubscribe, use the Unregister-Event cmdlet.</span></span>

## <span data-ttu-id="5f8f3-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="5f8f3-113">EXAMPLES</span></span>

### <span data-ttu-id="5f8f3-114">Exemplo 1: remover um evento por identificador de origem</span><span class="sxs-lookup"><span data-stu-id="5f8f3-114">Example 1: Remove an event by source identifier</span></span>

```
PS C:\> Remove-Event -SourceIdentifier "ProcessStarted"
```

<span data-ttu-id="5f8f3-115">Esse comando exclui eventos com um identificador de origem do processo iniciado na fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="5f8f3-115">This command deletes events with a source identifier of Process Started from the event queue.</span></span>

### <span data-ttu-id="5f8f3-116">Exemplo 2: remover um evento por identificador de evento</span><span class="sxs-lookup"><span data-stu-id="5f8f3-116">Example 2: Remove an event by event identifier</span></span>

```
PS C:\> Remove-Event -EventIdentifier 30
```

<span data-ttu-id="5f8f3-117">Esse comando exclui o evento com uma ID de evento 30 da fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="5f8f3-117">This command deletes the event with an event ID of 30 from the event queue.</span></span>

### <span data-ttu-id="5f8f3-118">Exemplo 3: remover todos os eventos</span><span class="sxs-lookup"><span data-stu-id="5f8f3-118">Example 3: Remove all events</span></span>

```
PS C:\> Get-Event | Remove-Event
```

<span data-ttu-id="5f8f3-119">Esse comando exclui todos os eventos da fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="5f8f3-119">This command deletes all events from the event queue.</span></span>

## <span data-ttu-id="5f8f3-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5f8f3-120">PARAMETERS</span></span>

### <span data-ttu-id="5f8f3-121">-EventIdentifier</span><span class="sxs-lookup"><span data-stu-id="5f8f3-121">-EventIdentifier</span></span>
<span data-ttu-id="5f8f3-122">Especifica o identificador de evento para o qual o cmdlet exclui.</span><span class="sxs-lookup"><span data-stu-id="5f8f3-122">Specifies the event identifier for which the cmdlet deletes.</span></span>
<span data-ttu-id="5f8f3-123">Um parâmetro *EventIdentifier* ou *SourceIdentifier* é necessário em todos os comandos.</span><span class="sxs-lookup"><span data-stu-id="5f8f3-123">An *EventIdentifier* or *SourceIdentifier* parameter is required in every command.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ByIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="5f8f3-124">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="5f8f3-124">-SourceIdentifier</span></span>
<span data-ttu-id="5f8f3-125">Especifica o identificador de origem para o qual este cmdlet exclui eventos.</span><span class="sxs-lookup"><span data-stu-id="5f8f3-125">Specifies the source identifier for which this cmdlet deletes events from.</span></span>
<span data-ttu-id="5f8f3-126">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="5f8f3-126">Wildcards are not permitted.</span></span>
<span data-ttu-id="5f8f3-127">Um parâmetro *EventIdentifier* ou *SourceIdentifier* é necessário em todos os comandos.</span><span class="sxs-lookup"><span data-stu-id="5f8f3-127">An *EventIdentifier* or *SourceIdentifier* parameter is required in every command.</span></span>

```yaml
Type: System.String
Parameter Sets: BySource
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5f8f3-128">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5f8f3-128">-Confirm</span></span>
<span data-ttu-id="5f8f3-129">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5f8f3-129">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="5f8f3-130">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5f8f3-130">-WhatIf</span></span>
<span data-ttu-id="5f8f3-131">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="5f8f3-131">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="5f8f3-132">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="5f8f3-132">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="5f8f3-133">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5f8f3-133">CommonParameters</span></span>
<span data-ttu-id="5f8f3-134">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5f8f3-134">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5f8f3-135">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5f8f3-135">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5f8f3-136">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="5f8f3-136">INPUTS</span></span>

### <span data-ttu-id="5f8f3-137">System. Management. Automation. PSEventArgs</span><span class="sxs-lookup"><span data-stu-id="5f8f3-137">System.Management.Automation.PSEventArgs</span></span>
<span data-ttu-id="5f8f3-138">É possível canalizar eventos de Get-Event para **Remove-Event** .</span><span class="sxs-lookup"><span data-stu-id="5f8f3-138">You can pipe events from Get-Event to **Remove-Event** .</span></span>

## <span data-ttu-id="5f8f3-139">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="5f8f3-139">OUTPUTS</span></span>

### <span data-ttu-id="5f8f3-140">Nenhum</span><span class="sxs-lookup"><span data-stu-id="5f8f3-140">None</span></span>
<span data-ttu-id="5f8f3-141">O cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="5f8f3-141">The cmdlet does not generate any output.</span></span>

## <span data-ttu-id="5f8f3-142">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="5f8f3-142">NOTES</span></span>

* <span data-ttu-id="5f8f3-143">Eventos, assinaturas de evento e a fila de eventos existem apenas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="5f8f3-143">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="5f8f3-144">Se você fechar a sessão atual, a fila de eventos será descartada e a inscrição do evento será cancelada.</span><span class="sxs-lookup"><span data-stu-id="5f8f3-144">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

*

## <span data-ttu-id="5f8f3-145">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="5f8f3-145">RELATED LINKS</span></span>

[<span data-ttu-id="5f8f3-146">Get-Event</span><span class="sxs-lookup"><span data-stu-id="5f8f3-146">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="5f8f3-147">New-Event</span><span class="sxs-lookup"><span data-stu-id="5f8f3-147">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="5f8f3-148">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="5f8f3-148">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="5f8f3-149">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="5f8f3-149">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="5f8f3-150">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="5f8f3-150">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="5f8f3-151">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="5f8f3-151">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="5f8f3-152">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="5f8f3-152">Wait-Event</span></span>](Wait-Event.md)
