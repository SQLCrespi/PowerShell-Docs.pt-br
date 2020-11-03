---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 07/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/register-wmievent?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-WmiEvent
ms.openlocfilehash: be29ce6376dea7686c0c063cc5528fbc7d840a9d
ms.sourcegitcommit: 41b072f0b6046d619b0e7f758982783fb648a3d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/31/2020
ms.locfileid: "93195096"
---
# <span data-ttu-id="d8b9b-103">Register-WmiEvent</span><span class="sxs-lookup"><span data-stu-id="d8b9b-103">Register-WmiEvent</span></span>

## <span data-ttu-id="d8b9b-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="d8b9b-104">SYNOPSIS</span></span>
<span data-ttu-id="d8b9b-105">Assina um evento de WMI (Instrumentação de Gerenciamento do Windows).</span><span class="sxs-lookup"><span data-stu-id="d8b9b-105">Subscribes to a Windows Management Instrumentation (WMI) event.</span></span>

## <span data-ttu-id="d8b9b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d8b9b-106">SYNTAX</span></span>

### <span data-ttu-id="d8b9b-107">classe (padrão)</span><span class="sxs-lookup"><span data-stu-id="d8b9b-107">class (Default)</span></span>

```
Register-WmiEvent [-Namespace <String>] [-Credential <PSCredential>] [-ComputerName <String>] [-Class] <String>
 [-Timeout <Int64>] [[-SourceIdentifier] <String>] [[-Action] <ScriptBlock>] [-MessageData <PSObject>]
 [-SupportEvent] [-Forward] [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="d8b9b-108">Consulta</span><span class="sxs-lookup"><span data-stu-id="d8b9b-108">query</span></span>

```
Register-WmiEvent [-Namespace <String>] [-Credential <PSCredential>] [-ComputerName <String>] [-Query] <String>
 [-Timeout <Int64>] [[-SourceIdentifier] <String>] [[-Action] <ScriptBlock>] [-MessageData <PSObject>]
 [-SupportEvent] [-Forward] [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="d8b9b-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d8b9b-109">DESCRIPTION</span></span>

<span data-ttu-id="d8b9b-110">O `Register-WmiEvent` cmdlet assina os eventos de instrumentação de gerenciamento do Windows (WMI) no computador local ou em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-110">The `Register-WmiEvent` cmdlet subscribes to Windows Management Instrumentation (WMI) events on the local computer or on a remote computer.</span></span>

<span data-ttu-id="d8b9b-111">Quando o evento WMI assinado é gerado, ele é adicionado à fila de eventos de sua sessão local, mesmo se o evento ocorrer em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-111">When the subscribed WMI event is raised, it is added to the event queue in your local session even if the event occurs on a remote computer.</span></span> <span data-ttu-id="d8b9b-112">Para obter eventos na fila de eventos, use o `Get-Event` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-112">To get events in the event queue, use the `Get-Event` cmdlet.</span></span>

<span data-ttu-id="d8b9b-113">Você pode usar os parâmetros de `Register-WmiEvent` para assinar eventos em computadores remotos e especificar os valores de propriedade dos eventos que podem ajudá-lo a identificar o evento na fila.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-113">You can use the parameters of `Register-WmiEvent` to subscribe to events on remote computers and to specify the property values of the events that can help you identify the event in the queue.</span></span> <span data-ttu-id="d8b9b-114">Você também pode usar o parâmetro **Action** para especificar ações a serem tomadas quando um evento assinado for gerado.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-114">You can also use the **Action** parameter to specify actions to take when a subscribed event is raised.</span></span>

<span data-ttu-id="d8b9b-115">Quando você se inscreve em um evento, um assinante de evento é adicionado à sua sessão.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-115">When you subscribe to an event, an event subscriber is added to your session.</span></span> <span data-ttu-id="d8b9b-116">Para obter os assinantes de evento na sessão, use o `Get-EventSubscriber` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-116">To get the event subscribers in the session, use the `Get-EventSubscriber` cmdlet.</span></span> <span data-ttu-id="d8b9b-117">Para cancelar a assinatura, use o `Unregister-Event` cmdlet, que exclui o Assinante de evento da sessão.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-117">To cancel the subscription, use the `Unregister-Event` cmdlet, which deletes the event subscriber from the session.</span></span>

<span data-ttu-id="d8b9b-118">Novos cmdlets do CIM (modelo CIM), introduzidos no Windows PowerShell 3,0, executam as mesmas tarefas que os cmdlets do WMI.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-118">New Common Information Model (CIM) cmdlets, introduced Windows PowerShell 3.0, perform the same tasks as the WMI cmdlets.</span></span> <span data-ttu-id="d8b9b-119">Os cmdlets do CIM estão em conformidade com os padrões do WSMan (WS-Management) e com o padrão CIM, que permite que os cmdlets usem as mesmas técnicas para gerenciar computadores que executam o sistema operacional Windows e aqueles que executam outros sistemas operacionais.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-119">The CIM cmdlets comply with WS-Management (WSMan) standards and with the CIM standard, which enables the cmdlets to use the same techniques to manage computers that run the Windows operating system and those that run other operating systems.</span></span> <span data-ttu-id="d8b9b-120">Em vez de usar `Register-WmiEvent` , considere usar o cmdlet [Register-CimIndicationEvent](../cimcmdlets/register-cimindicationevent.md) .</span><span class="sxs-lookup"><span data-stu-id="d8b9b-120">Instead of using `Register-WmiEvent`, consider using the [Register-CimIndicationEvent](../cimcmdlets/register-cimindicationevent.md) cmdlet.</span></span>

## <span data-ttu-id="d8b9b-121">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="d8b9b-121">EXAMPLES</span></span>

### <span data-ttu-id="d8b9b-122">Exemplo 1: assinar eventos gerados por uma classe</span><span class="sxs-lookup"><span data-stu-id="d8b9b-122">Example 1: Subscribe to events generated by a class</span></span>

<span data-ttu-id="d8b9b-123">Esse comando assina os eventos gerados pela classe **Win32_ProcessStartTrace** .</span><span class="sxs-lookup"><span data-stu-id="d8b9b-123">This command subscribes to the events generated by the **Win32_ProcessStartTrace** class.</span></span> <span data-ttu-id="d8b9b-124">Esta classe dispara um evento sempre que um processo é iniciado.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-124">This class raises an event whenever a process starts.</span></span>

```powershell
Register-WmiEvent -Class 'Win32_ProcessStartTrace' -SourceIdentifier "ProcessStarted"
```

### <span data-ttu-id="d8b9b-125">Exemplo 2: assinar eventos de criação para um processo</span><span class="sxs-lookup"><span data-stu-id="d8b9b-125">Example 2: Subscribe to creation events for a process</span></span>

<span data-ttu-id="d8b9b-126">Esse comando usa uma consulta para assinar eventos de criação de instância Win32_process.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-126">This command uses a query to subscribe to Win32_process instance creation events.</span></span>

```powershell
$wmiParameters = @{
  Query = "select * from __instancecreationevent within 5 where targetinstance isa 'win32_process'"
  SourceIdentifier = "WMIProcess"
  MessageData = "Test 01"
  TimeOut = 500
}
Register-WmiEvent @wmiParameters
```

### <span data-ttu-id="d8b9b-127">Exemplo 3: usar uma ação para responder a um evento</span><span class="sxs-lookup"><span data-stu-id="d8b9b-127">Example 3: Use an action to respond to an event</span></span>

<span data-ttu-id="d8b9b-128">Este exemplo mostra como usar uma ação para responder a um evento.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-128">This example shows how to use an action to respond to an event.</span></span> <span data-ttu-id="d8b9b-129">Nesse caso, quando um processo é iniciado, todos os `Start-Process` comandos na sessão atual são gravados em um arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-129">In this case, when a process starts, any `Start-Process` commands in the current session are written to an XML file.</span></span>

```powershell
$action = { Get-History | where { $_.commandline -like "*start-process*" } | export-cliXml "commandHistory.clixml" }
Register-WmiEvent -Class 'Win32_ProcessStartTrace' -SourceIdentifier "ProcessStarted" -Action $action
```

```Output
Id    Name            State      HasMoreData   Location  Command
--    ----            -----      -----------   --------  -------
1     ProcessStarted  NotStarted False                   get-history | where {...
```

<span data-ttu-id="d8b9b-130">Quando você usa o parâmetro **Action** , o `Register-WmiEvent` retorna um trabalho em segundo plano que representa a ação do evento.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-130">When you use the **Action** parameter, `Register-WmiEvent` returns a background job that represents the event action.</span></span> <span data-ttu-id="d8b9b-131">Você pode usar os cmdlets de **trabalho** , como `Get-Job` e `Receive-Job` , para gerenciar o trabalho de evento.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-131">You can use the **Job** cmdlets, such as `Get-Job` and `Receive-Job`, to manage the event job.</span></span>

<span data-ttu-id="d8b9b-132">Para obter mais informações, consulte about_Jobs.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-132">For more information, see about_Jobs.</span></span>

### <span data-ttu-id="d8b9b-133">Exemplo 4: registrar-se para eventos em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="d8b9b-133">Example 4: Register for events on a remote computer</span></span>

<span data-ttu-id="d8b9b-134">Este exemplo registra eventos no computador remoto Server01.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-134">This example registers for events on the Server01 remote computer.</span></span>

```powershell
Register-WmiEvent -Class 'Win32_ProcessStartTrace' -SourceIdentifier "Start" -Computername Server01
Get-Event -SourceIdentifier "Start"
```

<span data-ttu-id="d8b9b-135">WMI retorna os eventos ao computador local e os armazena na fila de eventos da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-135">WMI returns the events to the local computer and stores them in the event queue in the current session.</span></span> <span data-ttu-id="d8b9b-136">Para recuperar os eventos, execute um `Get-Event` comando local.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-136">To retrieve the events, run a local `Get-Event` command.</span></span>

## <span data-ttu-id="d8b9b-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d8b9b-137">PARAMETERS</span></span>

### <span data-ttu-id="d8b9b-138">-Action</span><span class="sxs-lookup"><span data-stu-id="d8b9b-138">-Action</span></span>

<span data-ttu-id="d8b9b-139">Especifica comandos que lidam com os eventos.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-139">Specifies commands that handle the events.</span></span> <span data-ttu-id="d8b9b-140">Os comandos no parâmetro **Action** são executados quando um evento é gerado em vez de enviar o evento para a fila de eventos.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-140">The commands in the **Action** parameter run when an event is raised instead of sending the event to the event queue.</span></span> <span data-ttu-id="d8b9b-141">Coloque os comandos entre chaves ( `{}` ) para criar um bloco de script.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-141">Enclose the commands in braces (`{}`) to create a script block.</span></span>

<span data-ttu-id="d8b9b-142">O valor da **ação** pode incluir as `$Event` `$EventSubscriber` `$Sender` `$EventArgs` variáveis automáticas,,, e `$Args` , que fornecem informações sobre o evento para o bloco de script de **ação** .</span><span class="sxs-lookup"><span data-stu-id="d8b9b-142">The value of **Action** can include the `$Event`, `$EventSubscriber`, `$Sender`, `$EventArgs`, and `$Args` automatic variables, which provide information about the event to the **Action** script block.</span></span> <span data-ttu-id="d8b9b-143">Para obter mais informações, consulte about_Automatic_Variables.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-143">For more information, see about_Automatic_Variables.</span></span>

<span data-ttu-id="d8b9b-144">Quando você especifica uma ação, `Register-WmiEvent` o retorna um objeto de trabalho de evento que representa essa ação.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-144">When you specify an action, `Register-WmiEvent` returns an event job object that represents that action.</span></span> <span data-ttu-id="d8b9b-145">Você pode usar os cmdlets que contêm o substantivo do **trabalho** (os cmdlets de **trabalho** ) para gerenciar o trabalho de evento.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-145">You can use the cmdlets that contain the **Job** noun (the **Job** cmdlets) to manage the event job.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: 101
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d8b9b-146">-Classe</span><span class="sxs-lookup"><span data-stu-id="d8b9b-146">-Class</span></span>

<span data-ttu-id="d8b9b-147">Especifica o evento que você está assinando.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-147">Specifies the event to which you are subscribing.</span></span> <span data-ttu-id="d8b9b-148">Insira a classe WMI que gera os eventos.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-148">Enter the WMI class that generates the events.</span></span> <span data-ttu-id="d8b9b-149">Um parâmetro de **classe** ou de **consulta** é necessário em cada comando.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-149">A **Class** or **Query** parameter is required in every command.</span></span>

```yaml
Type: System.String
Parameter Sets: class
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d8b9b-150">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="d8b9b-150">-ComputerName</span></span>

<span data-ttu-id="d8b9b-151">Especifica o nome do computador no qual o comando é executado.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-151">Specifies the name of the computer on which the command runs.</span></span> <span data-ttu-id="d8b9b-152">O padrão é o computador local.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-152">The default is the local computer.</span></span>

<span data-ttu-id="d8b9b-153">Digite o nome da NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado do computador.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-153">Type the NetBIOS name, an IP address, or a fully qualified domain name of the computer.</span></span> <span data-ttu-id="d8b9b-154">Para especificar o computador local, digite o nome do computador, um ponto ( `.` ) ou localhost.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-154">To specify the local computer, type the computer name, a dot (`.`), or localhost.</span></span>

<span data-ttu-id="d8b9b-155">Esse parâmetro não depende da comunicação remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-155">This parameter does not rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="d8b9b-156">Você pode usar o parâmetro **ComputerName** , mesmo que seu computador não esteja configurado para executar comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-156">You can use the **ComputerName** parameter even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d8b9b-157">-Credential</span><span class="sxs-lookup"><span data-stu-id="d8b9b-157">-Credential</span></span>

<span data-ttu-id="d8b9b-158">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-158">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="d8b9b-159">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-159">The default is the current user.</span></span>

<span data-ttu-id="d8b9b-160">Digite um nome de usuário, como User01 ou Domínio01 \ Usuário01, ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-160">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="d8b9b-161">Se você digitar um nome de usuário, esse cmdlet solicitará uma senha.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-161">If you type a user name, this cmdlet prompts you for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d8b9b-162">-Avançar</span><span class="sxs-lookup"><span data-stu-id="d8b9b-162">-Forward</span></span>

<span data-ttu-id="d8b9b-163">Indica que esse cmdlet envia eventos para essa assinatura para a sessão no computador local.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-163">Indicates that this cmdlet sends events for this subscription to the session on the local computer.</span></span>
<span data-ttu-id="d8b9b-164">Utilize esse parâmetro ao registrar eventos em um computador remoto ou em uma sessão remota.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-164">Use this parameter when you are registering for events on a remote computer or in a remote session.</span></span>

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

### <span data-ttu-id="d8b9b-165">-MaxTriggerCount</span><span class="sxs-lookup"><span data-stu-id="d8b9b-165">-MaxTriggerCount</span></span>

<span data-ttu-id="d8b9b-166">Especifica a contagem máxima de gatilhos.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-166">Specifies the maximum trigger count.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d8b9b-167">-MessageData</span><span class="sxs-lookup"><span data-stu-id="d8b9b-167">-MessageData</span></span>

<span data-ttu-id="d8b9b-168">Especifica dados adicionais a serem associados essa assinatura do evento.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-168">Specifies any additional data to be associated with this event subscription.</span></span> <span data-ttu-id="d8b9b-169">O valor desse parâmetro é exibido na propriedade **MessageData** de todos os eventos associados a essa assinatura.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-169">The value of this parameter appears in the **MessageData** property of all events associated with this subscription.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d8b9b-170">-Namespace</span><span class="sxs-lookup"><span data-stu-id="d8b9b-170">-Namespace</span></span>

<span data-ttu-id="d8b9b-171">Especifica o namespace da classe de WMI.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-171">Specifies the namespace of the WMI class.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d8b9b-172">-Query</span><span class="sxs-lookup"><span data-stu-id="d8b9b-172">-Query</span></span>

<span data-ttu-id="d8b9b-173">Especifica uma consulta em linguagem WQL (WQL) que identifica a classe de evento WMI, como: `select * from __InstanceDeletionEvent` .</span><span class="sxs-lookup"><span data-stu-id="d8b9b-173">Specifies a query in WMI Query Language (WQL) that identifies the WMI event class, such as: `select * from __InstanceDeletionEvent`.</span></span>

```yaml
Type: System.String
Parameter Sets: query
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d8b9b-174">-SourceIdentifier</span><span class="sxs-lookup"><span data-stu-id="d8b9b-174">-SourceIdentifier</span></span>

<span data-ttu-id="d8b9b-175">Especifica um nome para a assinatura selecionada.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-175">Specifies a name that you select for the subscription.</span></span> <span data-ttu-id="d8b9b-176">O nome que você selecionar deve ser exclusivo na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-176">The name that you select must be unique in the current session.</span></span> <span data-ttu-id="d8b9b-177">O valor padrão é o GUID que o Windows PowerShell atribui.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-177">The default value is the GUID that Windows PowerShell assigns.</span></span>

<span data-ttu-id="d8b9b-178">O valor desse parâmetro aparece no valor da propriedade **SourceIdentifier** do objeto assinante e de todos os objetos de evento associados a esta assinatura.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-178">The value of this parameter appears in the value of the **SourceIdentifier** property of the subscriber object and of all event objects associated with this subscription.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 100
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d8b9b-179">-SupportEvent</span><span class="sxs-lookup"><span data-stu-id="d8b9b-179">-SupportEvent</span></span>

<span data-ttu-id="d8b9b-180">Indica que esse cmdlet oculta a assinatura do evento.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-180">Indicates that this cmdlet hides the event subscription.</span></span> <span data-ttu-id="d8b9b-181">Utilize esse parâmetro quando a assinatura atual faz parte de um mecanismo de registro de evento mais complexo e não deve ser descoberto independentemente.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-181">Use this parameter when the current subscription is part of a more complex event registration mechanism and it should not be discovered independently.</span></span>

<span data-ttu-id="d8b9b-182">Para exibir ou cancelar uma assinatura que foi criada usando o parâmetro **SupportEvent** , especifique o parâmetro **Force** dos `Get-EventSubscriber` `Unregister-Event` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-182">To view or cancel a subscription that was created by using the **SupportEvent** parameter, specify the **Force** parameter of the `Get-EventSubscriber` and `Unregister-Event` cmdlets.</span></span>

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

### <span data-ttu-id="d8b9b-183">-Tempo limite</span><span class="sxs-lookup"><span data-stu-id="d8b9b-183">-Timeout</span></span>

<span data-ttu-id="d8b9b-184">Especifica por quanto tempo o Windows PowerShell aguarda até que esse comando seja concluído.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-184">Specifies how long Windows PowerShell waits for this command to finish.</span></span>

<span data-ttu-id="d8b9b-185">O valor padrão, 0 (zero), significa que não há nenhum tempo limite, e faz com que o Windows PowerShell aguarde indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-185">The default value, 0 (zero), means that there is no time-out, and it causes Windows PowerShell to wait indefinitely.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases: TimeoutMSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d8b9b-186">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d8b9b-186">CommonParameters</span></span>

<span data-ttu-id="d8b9b-187">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d8b9b-188">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d8b9b-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d8b9b-189">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="d8b9b-189">INPUTS</span></span>

### <span data-ttu-id="d8b9b-190">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d8b9b-190">None</span></span>

<span data-ttu-id="d8b9b-191">Não é possível transferir objetos para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-191">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="d8b9b-192">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="d8b9b-192">OUTPUTS</span></span>

### <span data-ttu-id="d8b9b-193">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d8b9b-193">None</span></span>

<span data-ttu-id="d8b9b-194">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-194">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="d8b9b-195">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="d8b9b-195">NOTES</span></span>

<span data-ttu-id="d8b9b-196">Para usar esse cmdlet no Windows Vista ou em uma versão posterior do sistema operacional Windows, inicie o Windows PowerShell usando a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-196">To use this cmdlet in Windows Vista or a later version of the Windows operating system, start Windows PowerShell by using the Run as administrator option.</span></span>

<span data-ttu-id="d8b9b-197">Eventos, assinaturas de evento e a fila de eventos existem apenas na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-197">Events, event subscriptions, and the event queue exist only in the current session.</span></span> <span data-ttu-id="d8b9b-198">Se você fechar a sessão atual, a fila de eventos será descartada e a inscrição do evento será cancelada.</span><span class="sxs-lookup"><span data-stu-id="d8b9b-198">If you close the current session, the event queue is discarded and the event subscription is canceled.</span></span>

## <span data-ttu-id="d8b9b-199">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="d8b9b-199">RELATED LINKS</span></span>
