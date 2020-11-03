---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/wait-event?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Event
ms.openlocfilehash: fd617cd145c4f36ceede9898de93cbad33cb4bf3
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192828"
---
# <span data-ttu-id="6a9e9-103">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="6a9e9-103">Wait-Event</span></span>

## <span data-ttu-id="6a9e9-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="6a9e9-104">SYNOPSIS</span></span>
<span data-ttu-id="6a9e9-105">Aguarda até que um determinado evento seja gerado antes de continuar a executar.</span><span class="sxs-lookup"><span data-stu-id="6a9e9-105">Waits until a particular event is raised before continuing to run.</span></span>

## <span data-ttu-id="6a9e9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6a9e9-106">SYNTAX</span></span>

```
Wait-Event [[-SourceIdentifier] <String>] [-Timeout <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="6a9e9-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6a9e9-107">DESCRIPTION</span></span>

<span data-ttu-id="6a9e9-108">O `Wait-Event` cmdlet suspende a execução de um script ou função até que um evento específico seja gerado.</span><span class="sxs-lookup"><span data-stu-id="6a9e9-108">The `Wait-Event` cmdlet suspends execution of a script or function until a particular event is raised.</span></span> <span data-ttu-id="6a9e9-109">A execução é retomada quando o evento é detectado.</span><span class="sxs-lookup"><span data-stu-id="6a9e9-109">Execution resumes when the event is detected.</span></span> <span data-ttu-id="6a9e9-110">Para cancelar a espera, pressione <kbd>Ctrl</kbd> + <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="6a9e9-110">To cancel the wait, press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span>

<span data-ttu-id="6a9e9-111">Esse recurso fornece uma alternativa às sondagens de evento.</span><span class="sxs-lookup"><span data-stu-id="6a9e9-111">This feature provides an alternative to polling for an event.</span></span> <span data-ttu-id="6a9e9-112">Ele também permite que você determine a resposta a um evento de duas maneiras diferentes:</span><span class="sxs-lookup"><span data-stu-id="6a9e9-112">It also allows you to determine the response to an event in two different ways:</span></span>

- <span data-ttu-id="6a9e9-113">usando o parâmetro **Action** da assinatura do evento</span><span class="sxs-lookup"><span data-stu-id="6a9e9-113">using the **Action** parameter of the event subscription</span></span>
- <span data-ttu-id="6a9e9-114">aguardando um evento retornar e, em seguida, responder com uma ação</span><span class="sxs-lookup"><span data-stu-id="6a9e9-114">waiting for an event to return and then respond with an action</span></span>

## <span data-ttu-id="6a9e9-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="6a9e9-115">EXAMPLES</span></span>

### <span data-ttu-id="6a9e9-116">Exemplo 1: aguardar o próximo evento</span><span class="sxs-lookup"><span data-stu-id="6a9e9-116">Example 1: Wait for the next event</span></span>

<span data-ttu-id="6a9e9-117">Este exemplo aguarda o próximo evento que é gerado.</span><span class="sxs-lookup"><span data-stu-id="6a9e9-117">This example waits for the next event that is raised.</span></span>

```powershell
Wait-Event
```

### <span data-ttu-id="6a9e9-118">Exemplo 2: aguardar um evento com um identificador de origem especificado</span><span class="sxs-lookup"><span data-stu-id="6a9e9-118">Example 2: Wait for an event with a specified source identifier</span></span>

<span data-ttu-id="6a9e9-119">Este exemplo aguarda o próximo evento que é gerado e que tem um identificador de origem de ProcessStarted.</span><span class="sxs-lookup"><span data-stu-id="6a9e9-119">This example waits for the next event that is raised and that has a source identifier of ProcessStarted.</span></span>

```powershell
Wait-Event -SourceIdentifier "ProcessStarted"
```

### <span data-ttu-id="6a9e9-120">Exemplo 3: aguardar um evento decorrido do temporizador</span><span class="sxs-lookup"><span data-stu-id="6a9e9-120">Example 3: Wait for a timer elapsed event</span></span>

<span data-ttu-id="6a9e9-121">Este exemplo usa o `Wait-Event` cmdlet para aguardar um evento de temporizador em um temporizador definido para 2000 milissegundos.</span><span class="sxs-lookup"><span data-stu-id="6a9e9-121">This example uses the `Wait-Event` cmdlet to wait for a timer event on a timer that is set for 2000 milliseconds.</span></span>

```powershell
$Timer = New-Object Timers.Timer
$objectEventArgs = @{
    InputObject = $Timer
    EventName = 'Elapsed'
    SourceIdentifier = 'Timer.Elapsed'
}
Register-ObjectEvent @objectEventArgs
$Timer.Interval = 2000
$Timer.Autoreset = $False
$Timer.Enabled = $True
Wait-Event Timer.Elapsed
```

```Output
ComputerName     :
RunspaceId       : bb560b14-ff43-48d4-b801-5adc31bbc6fb
EventIdentifier  : 1
Sender           : System.Timers.Timer
SourceEventArgs  : System.Timers.ElapsedEventArgs
SourceArgs       : {System.Timers.Timer, System.Timers.ElapsedEventArgs}
SourceIdentifier : Timer.Elapsed
TimeGenerated    : 4/23/2020 2:30:37 PM
MessageData      :
```

### <span data-ttu-id="6a9e9-122">Exemplo 4: aguardar um evento após um tempo limite especificado</span><span class="sxs-lookup"><span data-stu-id="6a9e9-122">Example 4: Wait for an event after a specified timeout</span></span>

<span data-ttu-id="6a9e9-123">Este exemplo aguarda até 90 segundos para o próximo evento que é gerado e que tem um identificador de origem de **ProcessStarted** .</span><span class="sxs-lookup"><span data-stu-id="6a9e9-123">This example waits up to 90 seconds for the next event that is raised and that has a source identifier of **ProcessStarted** .</span></span> <span data-ttu-id="6a9e9-124">Se o tempo especificado expirar, a espera terminará.</span><span class="sxs-lookup"><span data-stu-id="6a9e9-124">If the specified time expires, the wait ends.</span></span>

```powershell
Wait-Event -SourceIdentifier "ProcessStarted" -Timeout 90
```

## <span data-ttu-id="6a9e9-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6a9e9-125">PARAMETERS</span></span>

### <span data-ttu-id="6a9e9-126">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="6a9e9-126">-SourceIdentifier</span></span>

<span data-ttu-id="6a9e9-127">Especifica o identificador de origem que esse cmdlet espera por eventos.</span><span class="sxs-lookup"><span data-stu-id="6a9e9-127">Specifies the source identifier that this cmdlet waits for events.</span></span>
<span data-ttu-id="6a9e9-128">Por padrão, o `Wait-Event` aguarda qualquer evento.</span><span class="sxs-lookup"><span data-stu-id="6a9e9-128">By default, `Wait-Event` waits for any event.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6a9e9-129">-Tempo limite</span><span class="sxs-lookup"><span data-stu-id="6a9e9-129">-Timeout</span></span>

<span data-ttu-id="6a9e9-130">Especifica o tempo máximo, em segundos, que `Wait-Event` aguarda a ocorrência do evento.</span><span class="sxs-lookup"><span data-stu-id="6a9e9-130">Specifies the maximum time, in seconds, that `Wait-Event` waits for the event to occur.</span></span> <span data-ttu-id="6a9e9-131">O padrão, -1, aguarda indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="6a9e9-131">The default, -1, waits indefinitely.</span></span> <span data-ttu-id="6a9e9-132">O tempo começa quando você envia o `Wait-Event` comando.</span><span class="sxs-lookup"><span data-stu-id="6a9e9-132">The timing starts when you submit the `Wait-Event` command.</span></span>

<span data-ttu-id="6a9e9-133">Se o tempo especificado for ultrapassado, a espera terminará e o prompt de comando retornará, ainda que o evento não tenha sido ativado.</span><span class="sxs-lookup"><span data-stu-id="6a9e9-133">If the specified time is exceeded, the wait ends and the command prompt returns, even if the event has not been raised.</span></span> <span data-ttu-id="6a9e9-134">Nenhuma mensagem de erro é exibida.</span><span class="sxs-lookup"><span data-stu-id="6a9e9-134">No error message is displayed.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutSec

Required: False
Position: Named
Default value: -1
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6a9e9-135">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6a9e9-135">CommonParameters</span></span>

<span data-ttu-id="6a9e9-136">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6a9e9-136">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6a9e9-137">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6a9e9-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6a9e9-138">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="6a9e9-138">INPUTS</span></span>

### <span data-ttu-id="6a9e9-139">System.String</span><span class="sxs-lookup"><span data-stu-id="6a9e9-139">System.String</span></span>

## <span data-ttu-id="6a9e9-140">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="6a9e9-140">OUTPUTS</span></span>

### <span data-ttu-id="6a9e9-141">System. Management. Automation. PSEventArgs</span><span class="sxs-lookup"><span data-stu-id="6a9e9-141">System.Management.Automation.PSEventArgs</span></span>

## <span data-ttu-id="6a9e9-142">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="6a9e9-142">NOTES</span></span>

<span data-ttu-id="6a9e9-143">Eventos, assinaturas de evento e a fila de eventos existem apenas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="6a9e9-143">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="6a9e9-144">Se você fechar a sessão atual, a fila de eventos será descartada e a inscrição do evento será cancelada.</span><span class="sxs-lookup"><span data-stu-id="6a9e9-144">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

## <span data-ttu-id="6a9e9-145">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="6a9e9-145">RELATED LINKS</span></span>

[<span data-ttu-id="6a9e9-146">Get-Event</span><span class="sxs-lookup"><span data-stu-id="6a9e9-146">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="6a9e9-147">Get-EventSubscriber</span><span class="sxs-lookup"><span data-stu-id="6a9e9-147">Get-EventSubscriber</span></span>](Get-EventSubscriber.md)

[<span data-ttu-id="6a9e9-148">New-Event</span><span class="sxs-lookup"><span data-stu-id="6a9e9-148">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="6a9e9-149">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="6a9e9-149">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="6a9e9-150">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="6a9e9-150">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="6a9e9-151">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="6a9e9-151">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="6a9e9-152">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="6a9e9-152">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="6a9e9-153">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="6a9e9-153">Wait-Event</span></span>](Wait-Event.md)
