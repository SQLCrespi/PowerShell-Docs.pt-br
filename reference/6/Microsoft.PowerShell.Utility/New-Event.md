---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-event?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Event
ms.openlocfilehash: 6056861bc6b472e389939e446d922d2bc4302294
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194459"
---
# <span data-ttu-id="4dd6b-103">New-Event</span><span class="sxs-lookup"><span data-stu-id="4dd6b-103">New-Event</span></span>

## <span data-ttu-id="4dd6b-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="4dd6b-104">SYNOPSIS</span></span>
<span data-ttu-id="4dd6b-105">Cria um novo evento.</span><span class="sxs-lookup"><span data-stu-id="4dd6b-105">Creates a new event.</span></span>

## <span data-ttu-id="4dd6b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4dd6b-106">SYNTAX</span></span>

```
New-Event [-SourceIdentifier] <String> [[-Sender] <PSObject>] [[-EventArguments] <PSObject[]>]
 [[-MessageData] <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="4dd6b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4dd6b-107">DESCRIPTION</span></span>

<span data-ttu-id="4dd6b-108">O cmdlet **New-Event** cria um novo evento personalizado.</span><span class="sxs-lookup"><span data-stu-id="4dd6b-108">The **New-Event** cmdlet creates a new custom event.</span></span>

<span data-ttu-id="4dd6b-109">Você pode usar eventos personalizados para notificar os usuários sobre as alterações de estado em seu programa e qualquer alteração que seu programa puder detectar, incluindo hardware ou condições do sistema, status de aplicativos, status do disco, status da rede ou a conclusão de um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="4dd6b-109">You can use custom events to notify users about state changes in your program and any change that your program can detect, including hardware or system conditions, application status, disk status, network status, or the completion of a background job.</span></span>

<span data-ttu-id="4dd6b-110">Eventos personalizados são adicionados automaticamente à fila de eventos na sessão sempre que são gerados. Você não precisa se inscrever neles.</span><span class="sxs-lookup"><span data-stu-id="4dd6b-110">Custom events are automatically added to the event queue in your session whenever they are raised; you do not need to subscribe to them.</span></span>
<span data-ttu-id="4dd6b-111">No entanto, se você quiser encaminhar um evento para a sessão local ou especificar uma ação para responder ao evento, use o cmdlet de Register-EngineEvent para inscrever-se no evento personalizado.</span><span class="sxs-lookup"><span data-stu-id="4dd6b-111">However, if you want to forward an event to the local session or specify an action to respond to the event, use the Register-EngineEvent cmdlet to subscribe to the custom event.</span></span>

<span data-ttu-id="4dd6b-112">Quando você se inscreve em um evento personalizado, o assinante do evento é adicionado à sua sessão.</span><span class="sxs-lookup"><span data-stu-id="4dd6b-112">When you subscribe to a custom event, the event subscriber is added to your session.</span></span>
<span data-ttu-id="4dd6b-113">Se você cancelar a inscrição do evento usando o cmdlet Unregister-Event, o assinante do evento e o evento personalizado são excluídos da sessão.</span><span class="sxs-lookup"><span data-stu-id="4dd6b-113">If you cancel the event subscription by using the Unregister-Event cmdlet, the event subscriber and custom event are deleted from the session.</span></span>
<span data-ttu-id="4dd6b-114">Se você não assinar o evento personalizado, para excluir o evento, será necessário alterar as condições do programa ou fechar a sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4dd6b-114">If you do not subscribe to the custom event, to delete the event, you must change the program conditions or close the PowerShell session.</span></span>

## <span data-ttu-id="4dd6b-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="4dd6b-115">EXAMPLES</span></span>

### <span data-ttu-id="4dd6b-116">Exemplo 1: criar um novo evento na fila de eventos</span><span class="sxs-lookup"><span data-stu-id="4dd6b-116">Example 1: Create a new event in the event queue</span></span>

```
PS C:\> New-Event -SourceIdentifier Timer -Sender windows.timer -MessageData "Test"
```

<span data-ttu-id="4dd6b-117">Esse comando cria um novo evento na fila de eventos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4dd6b-117">This command creates a new event in the PowerShell event queue.</span></span>
<span data-ttu-id="4dd6b-118">Ele usa um objeto **Windows. Timer** para enviar o evento.</span><span class="sxs-lookup"><span data-stu-id="4dd6b-118">It uses a **Windows.Timer** object to send the event.</span></span>

### <span data-ttu-id="4dd6b-119">Exemplo 2: gerar um evento em resposta a outro evento</span><span class="sxs-lookup"><span data-stu-id="4dd6b-119">Example 2: Raise an event in response to another event</span></span>

```
PS C:\> function Enable-ProcessCreationEvent
{
   $Query = New-Object System.Management.WqlEventQuery "__InstanceCreationEvent", (New-Object TimeSpan 0,0,1), "TargetInstance isa 'Win32_Process'"
   $ProcessWatcher = New-Object System.Management.ManagementEventWatcher $Query
   $Identifier = "WMI.ProcessCreated"
   Register-ObjectEvent $ProcessWatcher "EventArrived" -SupportEvent $Identifier -Action
   {
      [void] (New-Event -SourceID "PowerShell.ProcessCreated" -Sender $Args[0] -EventArguments $Args[1].SourceEventArgs.NewEvent.TargetInstance)
   }
}
```

<span data-ttu-id="4dd6b-120">Esta função de exemplo usa o cmdlet **New-Event** para gerar um evento em resposta a outro evento.</span><span class="sxs-lookup"><span data-stu-id="4dd6b-120">This sample function uses the **New-Event** cmdlet to raise an event in response to another event.</span></span>
<span data-ttu-id="4dd6b-121">O comando usa o cmdlet Register-ObjectEvent para inscrever-se no evento do Windows Management Instrumentation (WMI) que é gerado quando um novo processo é criado.</span><span class="sxs-lookup"><span data-stu-id="4dd6b-121">The command uses the Register-ObjectEvent cmdlet to subscribe to the Windows Management Instrumentation (WMI) event that is raised when a new process is created.</span></span>
<span data-ttu-id="4dd6b-122">O comando usa o parâmetro *Action* do cmdlet para chamar o cmdlet **New-Event** , que cria o novo evento.</span><span class="sxs-lookup"><span data-stu-id="4dd6b-122">The command uses the *Action* parameter of the cmdlet to call the **New-Event** cmdlet, which creates the new event.</span></span>

<span data-ttu-id="4dd6b-123">Como os eventos que o **novo evento** gera são automaticamente adicionados à fila de eventos do PowerShell, você não precisa se registrar para esse evento.</span><span class="sxs-lookup"><span data-stu-id="4dd6b-123">Because the events that **New-Event** raises are automatically added to the PowerShell event queue, you do not need to register for that event.</span></span>

## <span data-ttu-id="4dd6b-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4dd6b-124">PARAMETERS</span></span>

### <span data-ttu-id="4dd6b-125">-EventArguments</span><span class="sxs-lookup"><span data-stu-id="4dd6b-125">-EventArguments</span></span>

<span data-ttu-id="4dd6b-126">Especifica um objeto que contém opções para o evento.</span><span class="sxs-lookup"><span data-stu-id="4dd6b-126">Specifies an object that contains options for the event.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd6b-127">-MessageData</span><span class="sxs-lookup"><span data-stu-id="4dd6b-127">-MessageData</span></span>

<span data-ttu-id="4dd6b-128">Especifica os dados adicionais associados ao evento.</span><span class="sxs-lookup"><span data-stu-id="4dd6b-128">Specifies additional data associated with the event.</span></span>
<span data-ttu-id="4dd6b-129">O valor desse parâmetro é exibido na propriedade **MessageData** do objeto de evento.</span><span class="sxs-lookup"><span data-stu-id="4dd6b-129">The value of this parameter appears in the **MessageData** property of the event object.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd6b-130">-Remetente</span><span class="sxs-lookup"><span data-stu-id="4dd6b-130">-Sender</span></span>

<span data-ttu-id="4dd6b-131">Especifica o objeto que gera o evento.</span><span class="sxs-lookup"><span data-stu-id="4dd6b-131">Specifies the object that raises the event.</span></span>
<span data-ttu-id="4dd6b-132">O padrão é o mecanismo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4dd6b-132">The default is the PowerShell engine.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd6b-133">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="4dd6b-133">-SourceIdentifier</span></span>

<span data-ttu-id="4dd6b-134">Especifica um nome para o novo evento.</span><span class="sxs-lookup"><span data-stu-id="4dd6b-134">Specifies a name for the new event.</span></span>
<span data-ttu-id="4dd6b-135">Este parâmetro é obrigatório e deve ser exclusivo na sessão.</span><span class="sxs-lookup"><span data-stu-id="4dd6b-135">This parameter is required, and it must be unique in the session.</span></span>

<span data-ttu-id="4dd6b-136">O valor desse parâmetro é exibido na propriedade **SourceIdentifier** dos eventos.</span><span class="sxs-lookup"><span data-stu-id="4dd6b-136">The value of this parameter appears in the **SourceIdentifier** property of the events.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd6b-137">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4dd6b-137">CommonParameters</span></span>

<span data-ttu-id="4dd6b-138">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4dd6b-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4dd6b-139">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4dd6b-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4dd6b-140">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="4dd6b-140">INPUTS</span></span>

### <span data-ttu-id="4dd6b-141">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4dd6b-141">None</span></span>

<span data-ttu-id="4dd6b-142">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4dd6b-142">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="4dd6b-143">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="4dd6b-143">OUTPUTS</span></span>

### <span data-ttu-id="4dd6b-144">System. Management. Automation. PSEventArgs</span><span class="sxs-lookup"><span data-stu-id="4dd6b-144">System.Management.Automation.PSEventArgs</span></span>

## <span data-ttu-id="4dd6b-145">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="4dd6b-145">NOTES</span></span>

<span data-ttu-id="4dd6b-146">O novo evento personalizado, a inscrição do evento e a fila de eventos existem apenas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="4dd6b-146">The new custom event, the event subscription, and the event queue exist only in the current session.</span></span> <span data-ttu-id="4dd6b-147">Se você fechar a sessão atual, a fila de eventos será descartada e a inscrição do evento será cancelada.</span><span class="sxs-lookup"><span data-stu-id="4dd6b-147">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

## <span data-ttu-id="4dd6b-148">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="4dd6b-148">RELATED LINKS</span></span>

[<span data-ttu-id="4dd6b-149">Get-Event</span><span class="sxs-lookup"><span data-stu-id="4dd6b-149">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="4dd6b-150">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="4dd6b-150">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="4dd6b-151">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="4dd6b-151">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="4dd6b-152">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="4dd6b-152">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="4dd6b-153">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="4dd6b-153">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="4dd6b-154">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="4dd6b-154">Wait-Event</span></span>](Wait-Event.md)
