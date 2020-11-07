---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-event?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Event
ms.openlocfilehash: 0dd55280d2d010a151945065d0fcf4f032c980ad
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94346744"
---
# <span data-ttu-id="0581e-103">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="0581e-103">Remove-Event</span></span>

## <span data-ttu-id="0581e-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="0581e-104">SYNOPSIS</span></span>
<span data-ttu-id="0581e-105">Exclui eventos da fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="0581e-105">Deletes events from the event queue.</span></span>

## <span data-ttu-id="0581e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0581e-106">SYNTAX</span></span>

### <span data-ttu-id="0581e-107">BySource (padrão)</span><span class="sxs-lookup"><span data-stu-id="0581e-107">BySource (Default)</span></span>

```
Remove-Event [-SourceIdentifier] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0581e-108">ByIdentifier</span><span class="sxs-lookup"><span data-stu-id="0581e-108">ByIdentifier</span></span>

```
Remove-Event [-EventIdentifier] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0581e-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0581e-109">DESCRIPTION</span></span>

<span data-ttu-id="0581e-110">O `Remove-Event` cmdlet exclui eventos da fila de eventos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="0581e-110">The `Remove-Event` cmdlet deletes events from the event queue in the current session.</span></span>

<span data-ttu-id="0581e-111">Este cmdlet exclui somente os eventos atualmente na fila.</span><span class="sxs-lookup"><span data-stu-id="0581e-111">This cmdlet deletes only the events currently in the queue.</span></span> <span data-ttu-id="0581e-112">Para cancelar os registros de eventos ou cancelar a assinatura, use o `Unregister-Event` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0581e-112">To cancel event registrations or unsubscribe, use the `Unregister-Event` cmdlet.</span></span>

## <span data-ttu-id="0581e-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="0581e-113">EXAMPLES</span></span>

### <span data-ttu-id="0581e-114">Exemplo 1: remover um evento por identificador de origem</span><span class="sxs-lookup"><span data-stu-id="0581e-114">Example 1: Remove an event by source identifier</span></span>

```
PS C:\> Remove-Event -SourceIdentifier "ProcessStarted"
```

<span data-ttu-id="0581e-115">Esse comando exclui eventos com um identificador de origem do processo iniciado na fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="0581e-115">This command deletes events with a source identifier of Process Started from the event queue.</span></span>

### <span data-ttu-id="0581e-116">Exemplo 2: remover um evento por identificador de evento</span><span class="sxs-lookup"><span data-stu-id="0581e-116">Example 2: Remove an event by event identifier</span></span>

```
PS C:\> Remove-Event -EventIdentifier 30
```

<span data-ttu-id="0581e-117">Esse comando exclui o evento com uma ID de evento 30 da fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="0581e-117">This command deletes the event with an event ID of 30 from the event queue.</span></span>

### <span data-ttu-id="0581e-118">Exemplo 3: remover todos os eventos</span><span class="sxs-lookup"><span data-stu-id="0581e-118">Example 3: Remove all events</span></span>

```
PS C:\> Get-Event | Remove-Event
```

<span data-ttu-id="0581e-119">Esse comando exclui todos os eventos da fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="0581e-119">This command deletes all events from the event queue.</span></span>

## <span data-ttu-id="0581e-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0581e-120">PARAMETERS</span></span>

### <span data-ttu-id="0581e-121">-EventIdentifier</span><span class="sxs-lookup"><span data-stu-id="0581e-121">-EventIdentifier</span></span>

<span data-ttu-id="0581e-122">Especifica o identificador de evento para o qual o cmdlet exclui.</span><span class="sxs-lookup"><span data-stu-id="0581e-122">Specifies the event identifier for which the cmdlet deletes.</span></span> <span data-ttu-id="0581e-123">Um parâmetro **EventIdentifier** ou **SourceIdentifier** é necessário em todos os comandos.</span><span class="sxs-lookup"><span data-stu-id="0581e-123">An **EventIdentifier** or **SourceIdentifier** parameter is required in every command.</span></span>

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

### <span data-ttu-id="0581e-124">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="0581e-124">-SourceIdentifier</span></span>

<span data-ttu-id="0581e-125">Especifica o identificador de origem para o qual este cmdlet exclui eventos.</span><span class="sxs-lookup"><span data-stu-id="0581e-125">Specifies the source identifier for which this cmdlet deletes events from.</span></span> <span data-ttu-id="0581e-126">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="0581e-126">Wildcards are not permitted.</span></span> <span data-ttu-id="0581e-127">Um parâmetro **EventIdentifier** ou **SourceIdentifier** é necessário em todos os comandos.</span><span class="sxs-lookup"><span data-stu-id="0581e-127">An **EventIdentifier** or **SourceIdentifier** parameter is required in every command.</span></span>

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

### <span data-ttu-id="0581e-128">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0581e-128">-Confirm</span></span>

<span data-ttu-id="0581e-129">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0581e-129">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0581e-130">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0581e-130">-WhatIf</span></span>

<span data-ttu-id="0581e-131">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="0581e-131">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="0581e-132">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="0581e-132">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0581e-133">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0581e-133">CommonParameters</span></span>

<span data-ttu-id="0581e-134">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0581e-134">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0581e-135">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0581e-135">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0581e-136">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="0581e-136">INPUTS</span></span>

### <span data-ttu-id="0581e-137">System. Management. Automation. PSEventArgs</span><span class="sxs-lookup"><span data-stu-id="0581e-137">System.Management.Automation.PSEventArgs</span></span>

<span data-ttu-id="0581e-138">Você pode canalizar eventos de `Get-Event` para `Remove-Event` .</span><span class="sxs-lookup"><span data-stu-id="0581e-138">You can pipe events from `Get-Event` to `Remove-Event`.</span></span>

## <span data-ttu-id="0581e-139">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="0581e-139">OUTPUTS</span></span>

### <span data-ttu-id="0581e-140">Nenhum</span><span class="sxs-lookup"><span data-stu-id="0581e-140">None</span></span>

<span data-ttu-id="0581e-141">O cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="0581e-141">The cmdlet does not generate any output.</span></span>

## <span data-ttu-id="0581e-142">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="0581e-142">NOTES</span></span>

<span data-ttu-id="0581e-143">Nenhuma fonte de eventos disponível nas plataformas Linux ou macOS.</span><span class="sxs-lookup"><span data-stu-id="0581e-143">No event sources available on the Linux or macOS platforms.</span></span>

<span data-ttu-id="0581e-144">Eventos, assinaturas de evento e a fila de eventos existem apenas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="0581e-144">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="0581e-145">Se você fechar a sessão atual, a fila de eventos será descartada e a inscrição do evento será cancelada.</span><span class="sxs-lookup"><span data-stu-id="0581e-145">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

## <span data-ttu-id="0581e-146">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="0581e-146">RELATED LINKS</span></span>

[<span data-ttu-id="0581e-147">Get-Event</span><span class="sxs-lookup"><span data-stu-id="0581e-147">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="0581e-148">New-Event</span><span class="sxs-lookup"><span data-stu-id="0581e-148">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="0581e-149">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="0581e-149">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="0581e-150">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="0581e-150">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="0581e-151">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="0581e-151">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="0581e-152">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="0581e-152">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="0581e-153">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="0581e-153">Wait-Event</span></span>](Wait-Event.md)
