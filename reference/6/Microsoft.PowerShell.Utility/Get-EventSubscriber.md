---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-eventsubscriber?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-EventSubscriber
ms.openlocfilehash: 8f36d2af0fe03685e44070a0b0db86b8a276c4ca
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194483"
---
# <span data-ttu-id="9c2e4-103">Get-EventSubscriber</span><span class="sxs-lookup"><span data-stu-id="9c2e4-103">Get-EventSubscriber</span></span>

## <span data-ttu-id="9c2e4-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="9c2e4-104">SYNOPSIS</span></span>
<span data-ttu-id="9c2e4-105">Obtém os assinantes do evento na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-105">Gets the event subscribers in the current session.</span></span>

## <span data-ttu-id="9c2e4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9c2e4-106">SYNTAX</span></span>

### <span data-ttu-id="9c2e4-107">BySource (padrão)</span><span class="sxs-lookup"><span data-stu-id="9c2e4-107">BySource (Default)</span></span>

```
Get-EventSubscriber [[-SourceIdentifier] <String>] [-Force] [<CommonParameters>]
```

### <span data-ttu-id="9c2e4-108">ById</span><span class="sxs-lookup"><span data-stu-id="9c2e4-108">ById</span></span>

```
Get-EventSubscriber [-SubscriptionId] <Int32> [-Force] [<CommonParameters>]
```

## <span data-ttu-id="9c2e4-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9c2e4-109">DESCRIPTION</span></span>

<span data-ttu-id="9c2e4-110">O cmdlet **Get-EventSubscriber** Obtém os assinantes de eventos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-110">The **Get-EventSubscriber** cmdlet gets the event subscribers in the current session.</span></span>

<span data-ttu-id="9c2e4-111">Quando você assina um evento usando um cmdlet registrar evento, um assinante de evento é adicionado à sua sessão do PowerShell e os eventos nos quais você assinou são adicionados à sua fila de eventos sempre que eles são gerados.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-111">When you subscribe to an event by using a Register event cmdlet, an event subscriber is added to your PowerShell session, and the events to which you subscribed are added to your event queue whenever they are raised.</span></span>
<span data-ttu-id="9c2e4-112">Para cancelar uma inscrição de evento, exclua o assinante de evento usando o cmdlet Unregister-Event.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-112">To cancel an event subscription, delete the event subscriber by using the Unregister-Event cmdlet.</span></span>

## <span data-ttu-id="9c2e4-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="9c2e4-113">EXAMPLES</span></span>

### <span data-ttu-id="9c2e4-114">Exemplo 1: obter o Assinante de evento para um evento de timer</span><span class="sxs-lookup"><span data-stu-id="9c2e4-114">Example 1: Get the event subscriber for a timer event</span></span>

```
PS C:\> $Timer = New-Object Timers.Timer
PS C:\> $Timer | Get-Member -Type Event
PS C:\> Register-ObjectEvent -InputObject $Timer -EventName Elapsed -SourceIdentifier Timer.Elapsed
PS C:\> Get-EventSubscriber
PS C:\> $Timer = New-Object Timers.Timer
PS C:\> $Timer | Get-Member -Type Event
TypeName: System.Timers.Timer
Name     MemberType Definition
----     ---------- ----------
Disposed Event      System.EventHandler Disposed(System.Object, System.EventArgs)
Elapsed  Event      System.Timers.ElapsedEventHandler Elapsed(System.Object, System.Timers.ElapsedEventArgs) PS C:\> Register-ObjectEvent -InputObject $Timer -EventName Elapsed -SourceIdentifier Timer.Elapsed
PS C:\> Get-EventSubscriber
SubscriptionId   : 4
SourceObject     : System.Timers.Timer
EventName        : Elapsed
SourceIdentifier : Timer.Elapsed
Action           :
HandlerDelegate  :
SupportEvent     : False
ForwardEvent     : False
```

<span data-ttu-id="9c2e4-115">Este exemplo usa um comando **Get-EventSubscriber** para obter o Assinante de evento para um evento de timer.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-115">This example uses a **Get-EventSubscriber** command to get the event subscriber for a timer event.</span></span>

<span data-ttu-id="9c2e4-116">O primeiro comando utiliza o cmdlet New-Object para criar uma instância de um objeto temporizador.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-116">The first command uses the New-Object cmdlet to create an instance of a timer object.</span></span>
<span data-ttu-id="9c2e4-117">Ele salva o novo objeto de timer na variável $Timer.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-117">It saves the new timer object in the $Timer variable.</span></span>

<span data-ttu-id="9c2e4-118">O segundo comando usa o cmdlet Get-Member para exibir os eventos que estão disponíveis para objetos de temporizador.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-118">The second command uses the Get-Member cmdlet to display the events that are available for timer objects.</span></span>
<span data-ttu-id="9c2e4-119">O comando usa o parâmetro de tipo do cmdlet **Get-Member** com um valor de Event.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-119">The command uses the Type parameter of the **Get-Member** cmdlet with a value of Event.</span></span>

<span data-ttu-id="9c2e4-120">O terceiro comando utiliza o cmdlet Register-ObjectEvent para registrar o evento Elapsed no objeto de temporizador.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-120">The third command uses the Register-ObjectEvent cmdlet to register for the Elapsed event on the timer object.</span></span>

<span data-ttu-id="9c2e4-121">O quarto comando usa o cmdlet **Get-EventSubscriber** para obter o assinante do evento decorrido.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-121">The fourth command uses the **Get-EventSubscriber** cmdlet to get the event subscriber for the Elapsed event.</span></span>

### <span data-ttu-id="9c2e4-122">Exemplo 2: usar o módulo dinâmico no PSEventJob na propriedade Action do assinante de evento</span><span class="sxs-lookup"><span data-stu-id="9c2e4-122">Example 2: Use the dynamic module in PSEventJob in the Action property of the event subscriber</span></span>

```
PS C:\> $Timer = New-Object Timers.Timer
PS C:\> $Timer.Interval = 500
PS C:\> Register-ObjectEvent -InputObject $Timer -EventName Elapsed -SourceIdentifier Timer.Random -Action { $Random = Get-Random -Min 0 -Max 100 }

Id  Name           State      HasMoreData  Location  Command
--  ----           -----      -----------  --------  -------
3   Timer.Random   NotStarted False                  $Random = Get-Random ...

PS C:\> $Timer.Enabled = $True
PS C:\> $Subscriber = Get-EventSubscriber -SourceIdentifier Timer.Random
PS C:\> ($Subscriber.action).gettype().fullname
System.Management.Automation.PSEventJob
PS C:\> $Subscriber.action | Format-List -Property *

State         : Running
Module        : __DynamicModule_6b5cbe82-d634-41d1-ae5e-ad7fe8d57fe0
StatusMessage :
HasMoreData   : True
Location      :
Command       : $random = Get-Random -Min 0 -Max 100
JobStateInfo  : Running
Finished      : System.Threading.ManualResetEvent
InstanceId    : 88944290-133d-4b44-8752-f901bd8012e2
Id            : 1
Name          : Timer.Random
ChildJobs     : {}
...

PS C:\> & $Subscriber.action.module {$Random}
96
PS C:\> & $Subscriber.action.module {$Random}
23
```

<span data-ttu-id="9c2e4-123">Este exemplo mostra como usar o módulo dinâmico no objeto **PSEventJob** na propriedade Action do assinante de evento.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-123">This example shows how to use the dynamic module in the **PSEventJob** object in the Action property of the event subscriber.</span></span>

<span data-ttu-id="9c2e4-124">O primeiro comando utiliza o cmdlet New-Object para criar um objeto de timer.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-124">The first command uses the New-Object cmdlet to create a timer object.</span></span>
<span data-ttu-id="9c2e4-125">O segundo comando define o intervalo do temporizador para 500 (milissegundos).</span><span class="sxs-lookup"><span data-stu-id="9c2e4-125">The second command sets the interval of the timer to 500 (milliseconds).</span></span>

<span data-ttu-id="9c2e4-126">O terceiro comando utiliza o cmdlet ObjectEvent Register para registrar o evento decorrido do objeto de timer.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-126">The third command uses the Register-ObjectEvent cmdlet to register the Elapsed event of the timer object.</span></span>
<span data-ttu-id="9c2e4-127">O comando inclui uma ação que manipula o evento.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-127">The command includes an action that handles the event.</span></span>
<span data-ttu-id="9c2e4-128">Sempre que o intervalo de timer expira, um evento é gerado e executar os comandos na ação.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-128">Whenever the timer interval elapses, an event is raised and the commands in the action run.</span></span>
<span data-ttu-id="9c2e4-129">Nesse caso, o cmdlet Get-Random gera um número aleatório entre 0 e 100 e o salva na variável $Random.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-129">In this case, the Get-Random cmdlet generates a random number between 0 and 100 and saves it in the $Random variable.</span></span>
<span data-ttu-id="9c2e4-130">O identificador de origem do evento é Timer.Random.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-130">The source identifier of the event is Timer.Random.</span></span>

<span data-ttu-id="9c2e4-131">Quando você usa um parâmetro de *ação* em um comando **Register-ObjectEvent** , o comando retorna um objeto **PSEventJob** que representa a ação.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-131">When you use an *Action* parameter in a **Register-ObjectEvent** command, the command returns a **PSEventJob** object that represents the action.</span></span>

<span data-ttu-id="9c2e4-132">O quarto comando habilita o temporizador.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-132">The fourth command enables the timer.</span></span>

<span data-ttu-id="9c2e4-133">O quinto comando usa o cmdlet **Get-EventSubscriber** para obter o assinante do evento timer. Random.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-133">The fifth command uses the **Get-EventSubscriber** cmdlet to get the event subscriber of the Timer.Random event.</span></span>
<span data-ttu-id="9c2e4-134">Ele salva o objeto de assinante de evento na variável $Subscriber.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-134">It saves the event subscriber object in the $Subscriber variable.</span></span>

<span data-ttu-id="9c2e4-135">O sexto comando mostra que a propriedade Action do objeto de assinante de evento contém um objeto **PSEventJob** .</span><span class="sxs-lookup"><span data-stu-id="9c2e4-135">The sixth command shows that the Action property of the event subscriber object contains a **PSEventJob** object.</span></span>
<span data-ttu-id="9c2e4-136">Na verdade, ele contém o mesmo objeto **PSEventJob** retornado pelo comando **Register-ObjectEvent** .</span><span class="sxs-lookup"><span data-stu-id="9c2e4-136">In fact, it contains the same **PSEventJob** object that the **Register-ObjectEvent** command returned.</span></span>

<span data-ttu-id="9c2e4-137">O sétimo comando usa o cmdlet Format-List para exibir todas as propriedades do objeto **PSEventJob** na propriedade Action em uma lista.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-137">The seventh command uses the Format-List cmdlet to display all of the properties of the **PSEventJob** object in the Action property in a list.</span></span>
<span data-ttu-id="9c2e4-138">O resultado revela que o objeto **PSEventJob** tem uma Propriedade Module que contém um módulo de script dinâmico que implementa a ação.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-138">The result reveals that the **PSEventJob** object has a Module property that contains a dynamic script module that implements the action.</span></span>

<span data-ttu-id="9c2e4-139">Os comandos restantes usam o operador de chamada (&) para invocar o comando no módulo e exibir o valor da variável $Random.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-139">The remaining commands use the call operator (&) to invoke the command in the module and display the value of the $Random variable.</span></span>
<span data-ttu-id="9c2e4-140">É possível utilizar o operador de chamada para invocar qualquer comando em um módulo, incluindo comandos que não são exportados.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-140">You can use the call operator to invoke any command in a module, including commands that are not exported.</span></span>
<span data-ttu-id="9c2e4-141">Nesse caso, os comandos mostram o número aleatório que está sendo gerado quando ocorre o evento Elapsed (decorrido).</span><span class="sxs-lookup"><span data-stu-id="9c2e4-141">In this case, the commands show the random number that is being generated when the Elapsed event occurs.</span></span>

<span data-ttu-id="9c2e4-142">Para obter mais informações sobre módulos, consulte [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="9c2e4-142">For more information about modules, see [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span></span>

## <span data-ttu-id="9c2e4-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9c2e4-143">PARAMETERS</span></span>

### <span data-ttu-id="9c2e4-144">-Force</span><span class="sxs-lookup"><span data-stu-id="9c2e4-144">-Force</span></span>

<span data-ttu-id="9c2e4-145">Indica que esse cmdlet obtém todos os assinantes de evento, incluindo assinantes de eventos que são ocultos usando o parâmetro *SupportEvent* de Register-ObjectEvent, Register-WmiEvent e Register-EngineEvent.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-145">Indicates that this cmdlet gets all event subscribers, including subscribers for events that are hidden by using the *SupportEvent* parameter of Register-ObjectEvent, Register-WmiEvent, and Register-EngineEvent.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9c2e4-146">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="9c2e4-146">-SourceIdentifier</span></span>

<span data-ttu-id="9c2e4-147">Especifica o valor da propriedade **SourceIdentifier** que obtém somente os assinantes do evento.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-147">Specifies the **SourceIdentifier** property value that gets only the event subscribers.</span></span>
<span data-ttu-id="9c2e4-148">Por padrão, o **Get-EventSubscriber** Obtém todos os assinantes de evento na sessão.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-148">By default, **Get-EventSubscriber** gets all event subscribers in the session.</span></span>
<span data-ttu-id="9c2e4-149">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-149">Wildcards are not permitted.</span></span>
<span data-ttu-id="9c2e4-150">Este parâmetro diferencia maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-150">This parameter is case-sensitive.</span></span>

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

### <span data-ttu-id="9c2e4-151">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="9c2e4-151">-SubscriptionId</span></span>

<span data-ttu-id="9c2e4-152">Especifica o identificador de assinatura que esse cmdlet obtém.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-152">Specifies the subscription identifier that this cmdlet gets.</span></span>
<span data-ttu-id="9c2e4-153">Por padrão, o **Get-EventSubscriber** Obtém todos os assinantes de evento na sessão.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-153">By default, **Get-EventSubscriber** gets all event subscribers in the session.</span></span>

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

### <span data-ttu-id="9c2e4-154">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9c2e4-154">CommonParameters</span></span>

<span data-ttu-id="9c2e4-155">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9c2e4-156">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9c2e4-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9c2e4-157">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="9c2e4-157">INPUTS</span></span>

### <span data-ttu-id="9c2e4-158">Nenhum</span><span class="sxs-lookup"><span data-stu-id="9c2e4-158">None</span></span>

<span data-ttu-id="9c2e4-159">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-159">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="9c2e4-160">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="9c2e4-160">OUTPUTS</span></span>

### <span data-ttu-id="9c2e4-161">System. Management. Automation. PSEventSubscriber</span><span class="sxs-lookup"><span data-stu-id="9c2e4-161">System.Management.Automation.PSEventSubscriber</span></span>

<span data-ttu-id="9c2e4-162">**Get-EventSubscriber** retorna um objeto que representa cada Assinante de evento.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-162">**Get-EventSubscriber** returns an object that represents each event subscriber.</span></span>

## <span data-ttu-id="9c2e4-163">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="9c2e4-163">NOTES</span></span>

* <span data-ttu-id="9c2e4-164">O cmdlet New-Event, que cria um evento personalizado, não gera um assinante.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-164">The New-Event cmdlet, which creates a custom event, does not generate a subscriber.</span></span> <span data-ttu-id="9c2e4-165">Portanto, o cmdlet **Get-EventSubscriber** não encontrará um objeto de assinante para esses eventos.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-165">Therefore, the **Get-EventSubscriber** cmdlet will not find a subscriber object for these events.</span></span> <span data-ttu-id="9c2e4-166">No entanto, se você usar o cmdlet Register-EngineEvent para assinar um evento personalizado (para encaminhar o evento ou para especificar uma ação), o **Get-EventSubscriber** encontrará o assinante gerado pelo **Register-EngineEvent** .</span><span class="sxs-lookup"><span data-stu-id="9c2e4-166">However, if you use the Register-EngineEvent cmdlet to subscribe to a custom event (in order to forward the event or to specify an action), **Get-EventSubscriber** will find the subscriber that **Register-EngineEvent** generates.</span></span>

  <span data-ttu-id="9c2e4-167">Eventos, assinaturas de evento e a fila de eventos existem apenas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-167">Events, event subscriptions, and the event queue exist only in the current session.</span></span>
<span data-ttu-id="9c2e4-168">Se você fechar a sessão atual, a fila de eventos será descartada e a inscrição do evento será cancelada.</span><span class="sxs-lookup"><span data-stu-id="9c2e4-168">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

*

## <span data-ttu-id="9c2e4-169">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="9c2e4-169">RELATED LINKS</span></span>

[<span data-ttu-id="9c2e4-170">Get-Event</span><span class="sxs-lookup"><span data-stu-id="9c2e4-170">Get-Event</span></span>](Get-Event.md)

[<span data-ttu-id="9c2e4-171">New-Event</span><span class="sxs-lookup"><span data-stu-id="9c2e4-171">New-Event</span></span>](New-Event.md)

[<span data-ttu-id="9c2e4-172">Register-EngineEvent</span><span class="sxs-lookup"><span data-stu-id="9c2e4-172">Register-EngineEvent</span></span>](Register-EngineEvent.md)

[<span data-ttu-id="9c2e4-173">Register-ObjectEvent</span><span class="sxs-lookup"><span data-stu-id="9c2e4-173">Register-ObjectEvent</span></span>](Register-ObjectEvent.md)

[<span data-ttu-id="9c2e4-174">Remove-Event</span><span class="sxs-lookup"><span data-stu-id="9c2e4-174">Remove-Event</span></span>](Remove-Event.md)

[<span data-ttu-id="9c2e4-175">Unregister-Event</span><span class="sxs-lookup"><span data-stu-id="9c2e4-175">Unregister-Event</span></span>](Unregister-Event.md)

[<span data-ttu-id="9c2e4-176">Wait-Event</span><span class="sxs-lookup"><span data-stu-id="9c2e4-176">Wait-Event</span></span>](Wait-Event.md)
