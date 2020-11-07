---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-event?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Event
ms.openlocfilehash: 35d5d75cad2855753504549262abd2e14af200c0
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94344483"
---
# <span data-ttu-id="512af-103">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="512af-103">Remove-Event</span></span>

## <span data-ttu-id="512af-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="512af-104">SYNOPSIS</span></span>
<span data-ttu-id="512af-105">Exclui eventos da fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="512af-105">Deletes events from the event queue.</span></span>

## <span data-ttu-id="512af-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="512af-106">SYNTAX</span></span>

### <span data-ttu-id="512af-107">BySource (padrão)</span><span class="sxs-lookup"><span data-stu-id="512af-107">BySource (Default)</span></span>

```
Remove-Event [-SourceIdentifier] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="512af-108">ByIdentifier</span><span class="sxs-lookup"><span data-stu-id="512af-108">ByIdentifier</span></span>

```
Remove-Event [-EventIdentifier] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="512af-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="512af-109">DESCRIPTION</span></span>

<span data-ttu-id="512af-110">O `Remove-Event` cmdlet exclui eventos da fila de eventos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="512af-110">The `Remove-Event` cmdlet deletes events from the event queue in the current session.</span></span>

<span data-ttu-id="512af-111">Este cmdlet exclui somente os eventos atualmente na fila.</span><span class="sxs-lookup"><span data-stu-id="512af-111">This cmdlet deletes only the events currently in the queue.</span></span> <span data-ttu-id="512af-112">Para cancelar os registros de eventos ou cancelar a assinatura, use o `Unregister-Event` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="512af-112">To cancel event registrations or unsubscribe, use the `Unregister-Event` cmdlet.</span></span>

## <span data-ttu-id="512af-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="512af-113">EXAMPLES</span></span>

### <span data-ttu-id="512af-114">Exemplo 1: remover um evento por identificador de origem</span><span class="sxs-lookup"><span data-stu-id="512af-114">Example 1: Remove an event by source identifier</span></span>

```
PS C:\> Remove-Event -SourceIdentifier "ProcessStarted"
```

<span data-ttu-id="512af-115">Esse comando exclui eventos com um identificador de origem do processo iniciado na fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="512af-115">This command deletes events with a source identifier of Process Started from the event queue.</span></span>

### <span data-ttu-id="512af-116">Exemplo 2: remover um evento por identificador de evento</span><span class="sxs-lookup"><span data-stu-id="512af-116">Example 2: Remove an event by event identifier</span></span>

```
PS C:\> Remove-Event -EventIdentifier 30
```

<span data-ttu-id="512af-117">Esse comando exclui o evento com uma ID de evento 30 da fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="512af-117">This command deletes the event with an event ID of 30 from the event queue.</span></span>

### <span data-ttu-id="512af-118">Exemplo 3: remover todos os eventos</span><span class="sxs-lookup"><span data-stu-id="512af-118">Example 3: Remove all events</span></span>

```
PS C:\> Get-Event | Remove-Event
```

<span data-ttu-id="512af-119">Esse comando exclui todos os eventos da fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="512af-119">This command deletes all events from the event queue.</span></span>

## <span data-ttu-id="512af-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="512af-120">PARAMETERS</span></span>

### <span data-ttu-id="512af-121">-EventIdentifier</span><span class="sxs-lookup"><span data-stu-id="512af-121">-EventIdentifier</span></span>

<span data-ttu-id="512af-122">Especifica o identificador de evento para o qual o cmdlet exclui.</span><span class="sxs-lookup"><span data-stu-id="512af-122">Specifies the event identifier for which the cmdlet deletes.</span></span> <span data-ttu-id="512af-123">Um parâmetro **EventIdentifier** ou **SourceIdentifier** é necessário em todos os comandos.</span><span class="sxs-lookup"><span data-stu-id="512af-123">An **EventIdentifier** or **SourceIdentifier** parameter is required in every command.</span></span>

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

### <span data-ttu-id="512af-124">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="512af-124">-SourceIdentifier</span></span>

<span data-ttu-id="512af-125">Especifica o identificador de origem para o qual este cmdlet exclui eventos.</span><span class="sxs-lookup"><span data-stu-id="512af-125">Specifies the source identifier for which this cmdlet deletes events from.</span></span> <span data-ttu-id="512af-126">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="512af-126">Wildcards are not permitted.</span></span> <span data-ttu-id="512af-127">Um parâmetro **EventIdentifier** ou **SourceIdentifier** é necessário em todos os comandos.</span><span class="sxs-lookup"><span data-stu-id="512af-127">An **EventIdentifier** or **SourceIdentifier** parameter is required in every command.</span></span>

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

### <span data-ttu-id="512af-128">-Confirm</span><span class="sxs-lookup"><span data-stu-id="512af-128">-Confirm</span></span>

<span data-ttu-id="512af-129">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="512af-129">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="512af-130">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="512af-130">-WhatIf</span></span>

<span data-ttu-id="512af-131">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="512af-131">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="512af-132">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="512af-132">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="512af-133">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="512af-133">CommonParameters</span></span>

<span data-ttu-id="512af-134">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="512af-134">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="512af-135">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="512af-135">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="512af-136">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="512af-136">INPUTS</span></span>

### <span data-ttu-id="512af-137">System. Management. Automation. PSEventArgs</span><span class="sxs-lookup"><span data-stu-id="512af-137">System.Management.Automation.PSEventArgs</span></span>

<span data-ttu-id="512af-138">Você pode canalizar eventos de `Get-Event` para `Remove-Event` .</span><span class="sxs-lookup"><span data-stu-id="512af-138">You can pipe events from `Get-Event` to `Remove-Event`.</span></span>

## <span data-ttu-id="512af-139">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="512af-139">OUTPUTS</span></span>

### <span data-ttu-id="512af-140">Nenhum</span><span class="sxs-lookup"><span data-stu-id="512af-140">None</span></span>

<span data-ttu-id="512af-141">O cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="512af-141">The cmdlet does not generate any output.</span></span>

## <span data-ttu-id="512af-142">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="512af-142">NOTES</span></span>

<span data-ttu-id="512af-143">Eventos, assinaturas de evento e a fila de eventos existem apenas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="512af-143">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="512af-144">Se você fechar a sessão atual, a fila de eventos será descartada e a inscrição do evento será cancelada.</span><span class="sxs-lookup"><span data-stu-id="512af-144">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

## <span data-ttu-id="512af-145">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="512af-145">RELATED LINKS</span></span>

[<span data-ttu-id="512af-146">Get-Event</span><span class="sxs-lookup"><span data-stu-id="512af-146">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="512af-147">New-Event</span><span class="sxs-lookup"><span data-stu-id="512af-147">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="512af-148">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="512af-148">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="512af-149">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="512af-149">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="512af-150">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="512af-150">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="512af-151">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="512af-151">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="512af-152">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="512af-152">Wait-Event</span></span>](Wait-Event.md)
