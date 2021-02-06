---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-event?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Event
ms.openlocfilehash: 3193de9020f2f54795bde9d5cce1bb86c4431ef9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597592"
---
# <span data-ttu-id="2baee-102">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="2baee-102">Remove-Event</span></span>

## <span data-ttu-id="2baee-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="2baee-103">SYNOPSIS</span></span>
<span data-ttu-id="2baee-104">Exclui eventos da fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="2baee-104">Deletes events from the event queue.</span></span>

## <span data-ttu-id="2baee-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2baee-105">SYNTAX</span></span>

### <span data-ttu-id="2baee-106">BySource (padrão)</span><span class="sxs-lookup"><span data-stu-id="2baee-106">BySource (Default)</span></span>

```
Remove-Event [-SourceIdentifier] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2baee-107">ByIdentifier</span><span class="sxs-lookup"><span data-stu-id="2baee-107">ByIdentifier</span></span>

```
Remove-Event [-EventIdentifier] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="2baee-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2baee-108">DESCRIPTION</span></span>

<span data-ttu-id="2baee-109">O `Remove-Event` cmdlet exclui eventos da fila de eventos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="2baee-109">The `Remove-Event` cmdlet deletes events from the event queue in the current session.</span></span>

<span data-ttu-id="2baee-110">Este cmdlet exclui somente os eventos atualmente na fila.</span><span class="sxs-lookup"><span data-stu-id="2baee-110">This cmdlet deletes only the events currently in the queue.</span></span> <span data-ttu-id="2baee-111">Para cancelar os registros de eventos ou cancelar a assinatura, use o `Unregister-Event` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2baee-111">To cancel event registrations or unsubscribe, use the `Unregister-Event` cmdlet.</span></span>

## <span data-ttu-id="2baee-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="2baee-112">EXAMPLES</span></span>

### <span data-ttu-id="2baee-113">Exemplo 1: remover um evento por identificador de origem</span><span class="sxs-lookup"><span data-stu-id="2baee-113">Example 1: Remove an event by source identifier</span></span>

```
PS C:\> Remove-Event -SourceIdentifier "ProcessStarted"
```

<span data-ttu-id="2baee-114">Esse comando exclui eventos com um identificador de origem do processo iniciado na fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="2baee-114">This command deletes events with a source identifier of Process Started from the event queue.</span></span>

### <span data-ttu-id="2baee-115">Exemplo 2: remover um evento por identificador de evento</span><span class="sxs-lookup"><span data-stu-id="2baee-115">Example 2: Remove an event by event identifier</span></span>

```
PS C:\> Remove-Event -EventIdentifier 30
```

<span data-ttu-id="2baee-116">Esse comando exclui o evento com uma ID de evento 30 da fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="2baee-116">This command deletes the event with an event ID of 30 from the event queue.</span></span>

### <span data-ttu-id="2baee-117">Exemplo 3: remover todos os eventos</span><span class="sxs-lookup"><span data-stu-id="2baee-117">Example 3: Remove all events</span></span>

```
PS C:\> Get-Event | Remove-Event
```

<span data-ttu-id="2baee-118">Esse comando exclui todos os eventos da fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="2baee-118">This command deletes all events from the event queue.</span></span>

## <span data-ttu-id="2baee-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2baee-119">PARAMETERS</span></span>

### <span data-ttu-id="2baee-120">-EventIdentifier</span><span class="sxs-lookup"><span data-stu-id="2baee-120">-EventIdentifier</span></span>

<span data-ttu-id="2baee-121">Especifica o identificador de evento para o qual o cmdlet exclui.</span><span class="sxs-lookup"><span data-stu-id="2baee-121">Specifies the event identifier for which the cmdlet deletes.</span></span> <span data-ttu-id="2baee-122">Um parâmetro **EventIdentifier** ou **SourceIdentifier** é necessário em todos os comandos.</span><span class="sxs-lookup"><span data-stu-id="2baee-122">An **EventIdentifier** or **SourceIdentifier** parameter is required in every command.</span></span>

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

### <span data-ttu-id="2baee-123">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="2baee-123">-SourceIdentifier</span></span>

<span data-ttu-id="2baee-124">Especifica o identificador de origem para o qual este cmdlet exclui eventos.</span><span class="sxs-lookup"><span data-stu-id="2baee-124">Specifies the source identifier for which this cmdlet deletes events from.</span></span> <span data-ttu-id="2baee-125">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="2baee-125">Wildcards are not permitted.</span></span> <span data-ttu-id="2baee-126">Um parâmetro **EventIdentifier** ou **SourceIdentifier** é necessário em todos os comandos.</span><span class="sxs-lookup"><span data-stu-id="2baee-126">An **EventIdentifier** or **SourceIdentifier** parameter is required in every command.</span></span>

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

### <span data-ttu-id="2baee-127">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2baee-127">-Confirm</span></span>

<span data-ttu-id="2baee-128">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2baee-128">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2baee-129">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2baee-129">-WhatIf</span></span>

<span data-ttu-id="2baee-130">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="2baee-130">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="2baee-131">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="2baee-131">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2baee-132">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2baee-132">CommonParameters</span></span>

<span data-ttu-id="2baee-133">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2baee-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2baee-134">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2baee-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2baee-135">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="2baee-135">INPUTS</span></span>

### <span data-ttu-id="2baee-136">System. Management. Automation. PSEventArgs</span><span class="sxs-lookup"><span data-stu-id="2baee-136">System.Management.Automation.PSEventArgs</span></span>

<span data-ttu-id="2baee-137">Você pode canalizar eventos de `Get-Event` para `Remove-Event` .</span><span class="sxs-lookup"><span data-stu-id="2baee-137">You can pipe events from `Get-Event` to `Remove-Event`.</span></span>

## <span data-ttu-id="2baee-138">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="2baee-138">OUTPUTS</span></span>

### <span data-ttu-id="2baee-139">Nenhum</span><span class="sxs-lookup"><span data-stu-id="2baee-139">None</span></span>

<span data-ttu-id="2baee-140">O cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="2baee-140">The cmdlet does not generate any output.</span></span>

## <span data-ttu-id="2baee-141">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="2baee-141">NOTES</span></span>

<span data-ttu-id="2baee-142">Nenhuma fonte de eventos disponível nas plataformas Linux ou macOS.</span><span class="sxs-lookup"><span data-stu-id="2baee-142">No event sources available on the Linux or macOS platforms.</span></span>

<span data-ttu-id="2baee-143">Eventos, assinaturas de evento e a fila de eventos existem apenas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="2baee-143">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="2baee-144">Se você fechar a sessão atual, a fila de eventos será descartada e a inscrição do evento será cancelada.</span><span class="sxs-lookup"><span data-stu-id="2baee-144">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

## <span data-ttu-id="2baee-145">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="2baee-145">RELATED LINKS</span></span>

[<span data-ttu-id="2baee-146">Get-Event</span><span class="sxs-lookup"><span data-stu-id="2baee-146">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="2baee-147">New-Event</span><span class="sxs-lookup"><span data-stu-id="2baee-147">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="2baee-148">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="2baee-148">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="2baee-149">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="2baee-149">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="2baee-150">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="2baee-150">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="2baee-151">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="2baee-151">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="2baee-152">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="2baee-152">Wait-Event</span></span>](Wait-Event.md)
