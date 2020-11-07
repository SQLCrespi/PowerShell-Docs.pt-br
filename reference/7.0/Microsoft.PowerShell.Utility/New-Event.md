---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-event?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Event
ms.openlocfilehash: e842aca53947b4dc9e606f2f6b17532c7c9e0cb4
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94346642"
---
# <span data-ttu-id="b3879-103">New-Event</span><span class="sxs-lookup"><span data-stu-id="b3879-103">New-Event</span></span>

## <span data-ttu-id="b3879-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b3879-104">SYNOPSIS</span></span>
<span data-ttu-id="b3879-105">Cria um novo evento.</span><span class="sxs-lookup"><span data-stu-id="b3879-105">Creates a new event.</span></span>

## <span data-ttu-id="b3879-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b3879-106">SYNTAX</span></span>

```
New-Event [-SourceIdentifier] <String> [[-Sender] <PSObject>] [[-EventArguments] <PSObject[]>]
 [[-MessageData] <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="b3879-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b3879-107">DESCRIPTION</span></span>

<span data-ttu-id="b3879-108">O `New-Event` cmdlet cria um novo evento personalizado.</span><span class="sxs-lookup"><span data-stu-id="b3879-108">The `New-Event` cmdlet creates a new custom event.</span></span>

<span data-ttu-id="b3879-109">Você pode usar eventos personalizados para notificar os usuários sobre as alterações de estado em seu programa e qualquer alteração que seu programa puder detectar, incluindo hardware ou condições do sistema, status de aplicativos, status do disco, status da rede ou a conclusão de um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="b3879-109">You can use custom events to notify users about state changes in your program and any change that your program can detect, including hardware or system conditions, application status, disk status, network status, or the completion of a background job.</span></span>

<span data-ttu-id="b3879-110">Eventos personalizados são adicionados automaticamente à fila de eventos na sessão sempre que são gerados. Você não precisa se inscrever neles.</span><span class="sxs-lookup"><span data-stu-id="b3879-110">Custom events are automatically added to the event queue in your session whenever they are raised; you do not need to subscribe to them.</span></span> <span data-ttu-id="b3879-111">No entanto, se você quiser encaminhar um evento para a sessão local ou especificar uma ação para responder ao evento, use o `Register-EngineEvent` cmdlet para assinar o evento personalizado.</span><span class="sxs-lookup"><span data-stu-id="b3879-111">However, if you want to forward an event to the local session or specify an action to respond to the event, use the `Register-EngineEvent` cmdlet to subscribe to the custom event.</span></span>

<span data-ttu-id="b3879-112">Quando você se inscreve em um evento personalizado, o assinante do evento é adicionado à sua sessão.</span><span class="sxs-lookup"><span data-stu-id="b3879-112">When you subscribe to a custom event, the event subscriber is added to your session.</span></span> <span data-ttu-id="b3879-113">Se você cancelar a assinatura de evento usando o `Unregister-Event` cmdlet, o Assinante de evento e o evento personalizado serão excluídos da sessão.</span><span class="sxs-lookup"><span data-stu-id="b3879-113">If you cancel the event subscription by using the `Unregister-Event` cmdlet, the event subscriber and custom event are deleted from the session.</span></span> <span data-ttu-id="b3879-114">Se você não assinar o evento personalizado, para excluir o evento, será necessário alterar as condições do programa ou fechar a sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b3879-114">If you do not subscribe to the custom event, to delete the event, you must change the program conditions or close the PowerShell session.</span></span>

## <span data-ttu-id="b3879-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b3879-115">EXAMPLES</span></span>

### <span data-ttu-id="b3879-116">Exemplo 1: criar um novo evento na fila de eventos</span><span class="sxs-lookup"><span data-stu-id="b3879-116">Example 1: Create a new event in the event queue</span></span>

```
PS C:\> New-Event -SourceIdentifier Timer -Sender windows.timer -MessageData "Test"
```

<span data-ttu-id="b3879-117">Esse comando cria um novo evento na fila de eventos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b3879-117">This command creates a new event in the PowerShell event queue.</span></span> <span data-ttu-id="b3879-118">Ele usa um objeto **Windows. Timer** para enviar o evento.</span><span class="sxs-lookup"><span data-stu-id="b3879-118">It uses a **Windows.Timer** object to send the event.</span></span>

### <span data-ttu-id="b3879-119">Exemplo 2: gerar um evento em resposta a outro evento</span><span class="sxs-lookup"><span data-stu-id="b3879-119">Example 2: Raise an event in response to another event</span></span>

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

<span data-ttu-id="b3879-120">Esta função de exemplo usa o `New-Event` cmdlet para gerar um evento em resposta a outro evento.</span><span class="sxs-lookup"><span data-stu-id="b3879-120">This sample function uses the `New-Event` cmdlet to raise an event in response to another event.</span></span> <span data-ttu-id="b3879-121">O comando usa o `Register-ObjectEvent` cmdlet para assinar o evento Instrumentação de gerenciamento do Windows (WMI) que é gerado quando um novo processo é criado.</span><span class="sxs-lookup"><span data-stu-id="b3879-121">The command uses the `Register-ObjectEvent` cmdlet to subscribe to the Windows Management Instrumentation (WMI) event that is raised when a new process is created.</span></span> <span data-ttu-id="b3879-122">O comando usa o parâmetro **Action** do cmdlet para chamar o `New-Event` cmdlet, que cria o novo evento.</span><span class="sxs-lookup"><span data-stu-id="b3879-122">The command uses the **Action** parameter of the cmdlet to call the `New-Event` cmdlet, which creates the new event.</span></span>

<span data-ttu-id="b3879-123">Como os eventos que `New-Event` geram são automaticamente adicionados à fila de eventos do PowerShell, você não precisa se registrar para esse evento.</span><span class="sxs-lookup"><span data-stu-id="b3879-123">Because the events that `New-Event` raises are automatically added to the PowerShell event queue, you do not need to register for that event.</span></span>

## <span data-ttu-id="b3879-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b3879-124">PARAMETERS</span></span>

### <span data-ttu-id="b3879-125">-EventArguments</span><span class="sxs-lookup"><span data-stu-id="b3879-125">-EventArguments</span></span>

<span data-ttu-id="b3879-126">Especifica um objeto que contém opções para o evento.</span><span class="sxs-lookup"><span data-stu-id="b3879-126">Specifies an object that contains options for the event.</span></span>

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

### <span data-ttu-id="b3879-127">-MessageData</span><span class="sxs-lookup"><span data-stu-id="b3879-127">-MessageData</span></span>

<span data-ttu-id="b3879-128">Especifica os dados adicionais associados ao evento.</span><span class="sxs-lookup"><span data-stu-id="b3879-128">Specifies additional data associated with the event.</span></span> <span data-ttu-id="b3879-129">O valor desse parâmetro é exibido na propriedade **MessageData** do objeto de evento.</span><span class="sxs-lookup"><span data-stu-id="b3879-129">The value of this parameter appears in the **MessageData** property of the event object.</span></span>

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

### <span data-ttu-id="b3879-130">-Remetente</span><span class="sxs-lookup"><span data-stu-id="b3879-130">-Sender</span></span>

<span data-ttu-id="b3879-131">Especifica o objeto que gera o evento.</span><span class="sxs-lookup"><span data-stu-id="b3879-131">Specifies the object that raises the event.</span></span> <span data-ttu-id="b3879-132">O padrão é o mecanismo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b3879-132">The default is the PowerShell engine.</span></span>

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

### <span data-ttu-id="b3879-133">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="b3879-133">-SourceIdentifier</span></span>

<span data-ttu-id="b3879-134">Especifica um nome para o novo evento.</span><span class="sxs-lookup"><span data-stu-id="b3879-134">Specifies a name for the new event.</span></span> <span data-ttu-id="b3879-135">Este parâmetro é obrigatório e deve ser exclusivo na sessão.</span><span class="sxs-lookup"><span data-stu-id="b3879-135">This parameter is required, and it must be unique in the session.</span></span>

<span data-ttu-id="b3879-136">O valor desse parâmetro é exibido na propriedade **SourceIdentifier** dos eventos.</span><span class="sxs-lookup"><span data-stu-id="b3879-136">The value of this parameter appears in the **SourceIdentifier** property of the events.</span></span>

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

### <span data-ttu-id="b3879-137">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b3879-137">CommonParameters</span></span>

<span data-ttu-id="b3879-138">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b3879-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b3879-139">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b3879-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b3879-140">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b3879-140">INPUTS</span></span>

### <span data-ttu-id="b3879-141">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b3879-141">None</span></span>

<span data-ttu-id="b3879-142">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b3879-142">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="b3879-143">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b3879-143">OUTPUTS</span></span>

### <span data-ttu-id="b3879-144">System. Management. Automation. PSEventArgs</span><span class="sxs-lookup"><span data-stu-id="b3879-144">System.Management.Automation.PSEventArgs</span></span>

## <span data-ttu-id="b3879-145">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b3879-145">NOTES</span></span>

<span data-ttu-id="b3879-146">Nenhuma fonte de eventos disponível nas plataformas Linux ou macOS.</span><span class="sxs-lookup"><span data-stu-id="b3879-146">No event sources available on the Linux or macOS platforms.</span></span>

<span data-ttu-id="b3879-147">O novo evento personalizado, a inscrição do evento e a fila de eventos existem apenas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="b3879-147">The new custom event, the event subscription, and the event queue exist only in the current session.</span></span>
<span data-ttu-id="b3879-148">Se você fechar a sessão atual, a fila de eventos será descartada e a inscrição do evento será cancelada.</span><span class="sxs-lookup"><span data-stu-id="b3879-148">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

## <span data-ttu-id="b3879-149">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b3879-149">RELATED LINKS</span></span>

[<span data-ttu-id="b3879-150">Get-Event</span><span class="sxs-lookup"><span data-stu-id="b3879-150">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="b3879-151">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="b3879-151">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="b3879-152">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="b3879-152">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="b3879-153">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="b3879-153">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="b3879-154">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="b3879-154">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="b3879-155">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="b3879-155">Wait-Event</span></span>](Wait-Event.md)
