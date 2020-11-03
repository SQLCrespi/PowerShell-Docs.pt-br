---
description: O Windows PowerShell cria um log de eventos do Windows chamado "Windows PowerShell" para registrar eventos do Windows PowerShell. Você pode exibir esse log em Visualizador de Eventos ou usando cmdlets que obtêm eventos, como o `Get-EventLog` cmdlet. Por padrão, os eventos de mecanismo e provedor do Windows PowerShell são registrados no log de eventos, mas você pode usar as variáveis de preferência do log de eventos para personalizar o log de eventos. Por exemplo, você pode adicionar eventos sobre comandos do Windows PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 11/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_eventlogs?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Eventlogs
ms.openlocfilehash: eb92333c6a6e220e287dcbec1441d2d05aa9275b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196211"
---
# <a name="about-eventlogs"></a><span data-ttu-id="db066-107">Sobre EventLogs</span><span class="sxs-lookup"><span data-stu-id="db066-107">About Eventlogs</span></span>

## <a name="short-description"></a><span data-ttu-id="db066-108">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="db066-108">Short Description</span></span>

<span data-ttu-id="db066-109">O Windows PowerShell cria um log de eventos do Windows chamado "Windows PowerShell" para registrar eventos do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db066-109">Windows PowerShell creates a Windows event log that is named "Windows PowerShell" to record Windows PowerShell events.</span></span> <span data-ttu-id="db066-110">Você pode exibir esse log em Visualizador de Eventos ou usando cmdlets que obtêm eventos, como o `Get-EventLog` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="db066-110">You can view this log in Event Viewer or by using cmdlets that get events, such as the `Get-EventLog` cmdlet.</span></span> <span data-ttu-id="db066-111">Por padrão, os eventos de mecanismo e provedor do Windows PowerShell são registrados no log de eventos, mas você pode usar as variáveis de preferência do log de eventos para personalizar o log de eventos.</span><span class="sxs-lookup"><span data-stu-id="db066-111">By default, Windows PowerShell engine and provider events are recorded in the event log, but you can use the event log preference variables to customize the event log.</span></span> <span data-ttu-id="db066-112">Por exemplo, você pode adicionar eventos sobre comandos do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db066-112">For example, you can add events about Windows PowerShell commands.</span></span>

## <a name="long-description"></a><span data-ttu-id="db066-113">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="db066-113">Long Description</span></span>

<span data-ttu-id="db066-114">O log de eventos do Windows PowerShell registra os detalhes das operações do Windows PowerShell, como iniciar e interromper o mecanismo do programa e iniciar e interromper os provedores do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db066-114">The Windows PowerShell event log records details of Windows PowerShell operations, such as starting and stopping the program engine and starting and stopping the Windows PowerShell providers.</span></span> <span data-ttu-id="db066-115">Você também pode registrar detalhes sobre os comandos do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db066-115">You can also log details about Windows PowerShell commands.</span></span>

<span data-ttu-id="db066-116">O log de eventos do Windows PowerShell está no grupo logs de aplicativos e serviços.</span><span class="sxs-lookup"><span data-stu-id="db066-116">The Windows PowerShell event log is in the Application and Services Logs group.</span></span> <span data-ttu-id="db066-117">O log do Windows PowerShell é um log de eventos clássico que não usa a tecnologia de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="db066-117">The Windows PowerShell log is a classic event log that does not use the Windows Eventing technology.</span></span> <span data-ttu-id="db066-118">Para exibir o log, use os cmdlets projetados para logs de eventos clássicos, como `Get-EventLog` .</span><span class="sxs-lookup"><span data-stu-id="db066-118">To view the log, use the cmdlets designed for classic event logs, such as `Get-EventLog`.</span></span>

## <a name="viewing-the-windows-powershell-event-log"></a><span data-ttu-id="db066-119">Exibindo o log de eventos do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="db066-119">Viewing the Windows PowerShell Event Log</span></span>

<span data-ttu-id="db066-120">Você pode exibir o log de eventos do Windows PowerShell em Visualizador de Eventos ou usando `Get-EventLog` os `Get-WmiObject` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="db066-120">You can view the Windows PowerShell event log in Event Viewer or by using the `Get-EventLog` and `Get-WmiObject` cmdlets.</span></span> <span data-ttu-id="db066-121">Para exibir o conteúdo do log do Windows PowerShell, digite:</span><span class="sxs-lookup"><span data-stu-id="db066-121">To view the contents of the Windows PowerShell log, type:</span></span>

```powershell
Get-EventLog -LogName "Windows PowerShell"
```

<span data-ttu-id="db066-122">Para examinar os eventos e suas propriedades, use o `Sort-Object` cmdlet, o `Group-Object` cmdlet e os cmdlets que contêm o `Format` verbo (os `Format` cmdlets).</span><span class="sxs-lookup"><span data-stu-id="db066-122">To examine the events and their properties, use the `Sort-Object` cmdlet, the `Group-Object` cmdlet, and the cmdlets that contain the `Format` verb (the `Format` cmdlets).</span></span>

<span data-ttu-id="db066-123">Por exemplo, para exibir os eventos no log agrupados pela ID do evento, digite:</span><span class="sxs-lookup"><span data-stu-id="db066-123">For example, to view the events in the log grouped by the event ID, type:</span></span>

```powershell
Get-EventLog "Windows PowerShell" | Format-Table -GroupBy EventID
```

<span data-ttu-id="db066-124">Ou, digite:</span><span class="sxs-lookup"><span data-stu-id="db066-124">Or, type:</span></span>

```powershell
Get-EventLog "Windows PowerShell" |
  Sort-Object EventID |
  Group-Object EventID
```

<span data-ttu-id="db066-125">Para exibir todos os logs de eventos clássicos, digite:</span><span class="sxs-lookup"><span data-stu-id="db066-125">To view all the classic event logs, type:</span></span>

```powershell
Get-EventLog -List
```

<span data-ttu-id="db066-126">Você também pode usar o `Get-WmiObject` cmdlet para usar as classes de instrumentação de gerenciamento do Windows relacionadas a eventos (WMI) para examinar o log de eventos.</span><span class="sxs-lookup"><span data-stu-id="db066-126">You can also use the `Get-WmiObject` cmdlet to use the event-related Windows Management Instrumentation (WMI) classes to examine the event log.</span></span> <span data-ttu-id="db066-127">Por exemplo, para exibir todas as propriedades do arquivo de log de eventos, digite:</span><span class="sxs-lookup"><span data-stu-id="db066-127">For example, to view all the properties of the event log file, type:</span></span>

```powershell
Get-WmiObject Win32_NTEventlogFile |
  where LogFileName -EQ "Windows PowerShell" |
  Format-List -Property *
```

<span data-ttu-id="db066-128">Para localizar as classes WMI relacionadas a eventos do Win32, digite:</span><span class="sxs-lookup"><span data-stu-id="db066-128">To find the Win32 event-related WMI classes, type:</span></span>

```powershell
Get-WmiObject -List | where Name -Like "win32*event*"
```

<span data-ttu-id="db066-129">Para obter mais informações, digite "Get-Help Get-EventLog" e "Get-Help Get-WmiObject".</span><span class="sxs-lookup"><span data-stu-id="db066-129">For more information, type "Get-Help Get-EventLog" and "Get-Help Get-WmiObject".</span></span>

## <a name="selecting-events-for-the-windows-powershell-event-log"></a><span data-ttu-id="db066-130">Selecionando eventos para o log de eventos do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="db066-130">Selecting Events for the Windows PowerShell Event Log</span></span>

<span data-ttu-id="db066-131">Você pode usar as variáveis de preferência do log de eventos para determinar quais eventos são registrados no log de eventos do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db066-131">You can use the event log preference variables to determine which events are recorded in the Windows PowerShell event log.</span></span>

<span data-ttu-id="db066-132">Há seis variáveis de preferência de log de eventos; duas variáveis para cada um dos três componentes de log: o mecanismo (o programa Windows PowerShell), os provedores e os comandos.</span><span class="sxs-lookup"><span data-stu-id="db066-132">There are six event log preference variables; two variables for each of the three logging components: the engine (the Windows PowerShell program), the providers, and the commands.</span></span> <span data-ttu-id="db066-133">As variáveis LifeCycleEvent registram eventos de início e parada normais.</span><span class="sxs-lookup"><span data-stu-id="db066-133">The LifeCycleEvent variables log normal starting and stopping events.</span></span> <span data-ttu-id="db066-134">Os eventos de erro de log das variáveis de integridade.</span><span class="sxs-lookup"><span data-stu-id="db066-134">The Health variables log error events.</span></span>

<span data-ttu-id="db066-135">A tabela a seguir lista as variáveis de preferência de log de eventos.</span><span class="sxs-lookup"><span data-stu-id="db066-135">The following table lists the event log preference variables.</span></span>

|<span data-ttu-id="db066-136">Variável</span><span class="sxs-lookup"><span data-stu-id="db066-136">Variable</span></span>                  |<span data-ttu-id="db066-137">Descrição</span><span class="sxs-lookup"><span data-stu-id="db066-137">Description</span></span>                                    |
|--------------------------|-----------------------------------------------|
|<span data-ttu-id="db066-138">$LogEngineLifeCycleEvent</span><span class="sxs-lookup"><span data-stu-id="db066-138">$LogEngineLifeCycleEvent</span></span>  |<span data-ttu-id="db066-139">Registra o início e a parada do PowerShell</span><span class="sxs-lookup"><span data-stu-id="db066-139">Logs the start and stop of PowerShell</span></span>          |
|<span data-ttu-id="db066-140">$LogEngineHealthEvent</span><span class="sxs-lookup"><span data-stu-id="db066-140">$LogEngineHealthEvent</span></span>     |<span data-ttu-id="db066-141">Registra erros do programa do PowerShell</span><span class="sxs-lookup"><span data-stu-id="db066-141">Logs PowerShell program errors</span></span>                 |
|<span data-ttu-id="db066-142">$LogProviderLifeCycleEvent</span><span class="sxs-lookup"><span data-stu-id="db066-142">$LogProviderLifeCycleEvent</span></span>|<span data-ttu-id="db066-143">Registra o início e a interrupção dos provedores do PowerShell</span><span class="sxs-lookup"><span data-stu-id="db066-143">Logs the start and stop of PowerShell providers</span></span>|
|<span data-ttu-id="db066-144">$LogProviderHealthEvent</span><span class="sxs-lookup"><span data-stu-id="db066-144">$LogProviderHealthEvent</span></span>   |<span data-ttu-id="db066-145">Registra erros do provedor do PowerShell</span><span class="sxs-lookup"><span data-stu-id="db066-145">Logs PowerShell provider errors</span></span>                |
|<span data-ttu-id="db066-146">$LogCommandLifeCycleEvent</span><span class="sxs-lookup"><span data-stu-id="db066-146">$LogCommandLifeCycleEvent</span></span> |<span data-ttu-id="db066-147">Registra o início e a conclusão de comandos</span><span class="sxs-lookup"><span data-stu-id="db066-147">Logs the starting and completion of commands</span></span>   |
|<span data-ttu-id="db066-148">$LogCommandHealthEvent</span><span class="sxs-lookup"><span data-stu-id="db066-148">$LogCommandHealthEvent</span></span>    |<span data-ttu-id="db066-149">Registra erros de comando</span><span class="sxs-lookup"><span data-stu-id="db066-149">Logs command errors</span></span>                            |

<span data-ttu-id="db066-150">(Para obter informações sobre provedores do Windows PowerShell, consulte [about_Providers](about_Providers.md).)</span><span class="sxs-lookup"><span data-stu-id="db066-150">(For information about Windows PowerShell providers, see [about_Providers](about_Providers.md).)</span></span>

<span data-ttu-id="db066-151">Por padrão, somente os seguintes tipos de evento são habilitados:</span><span class="sxs-lookup"><span data-stu-id="db066-151">By default, only the following event types are enabled:</span></span>

* <span data-ttu-id="db066-152">$LogEngineLifeCycleEvent</span><span class="sxs-lookup"><span data-stu-id="db066-152">$LogEngineLifeCycleEvent</span></span>
* <span data-ttu-id="db066-153">$LogEngineHealthEvent</span><span class="sxs-lookup"><span data-stu-id="db066-153">$LogEngineHealthEvent</span></span>
* <span data-ttu-id="db066-154">$LogProviderLifeCycleEvent</span><span class="sxs-lookup"><span data-stu-id="db066-154">$LogProviderLifeCycleEvent</span></span>
* <span data-ttu-id="db066-155">$LogProviderHealthEvent</span><span class="sxs-lookup"><span data-stu-id="db066-155">$LogProviderHealthEvent</span></span>

<span data-ttu-id="db066-156">Para habilitar um tipo de evento, defina a variável de preferência para esse tipo de evento como $true.</span><span class="sxs-lookup"><span data-stu-id="db066-156">To enable an event type, set the preference variable for that event type to $true.</span></span> <span data-ttu-id="db066-157">Por exemplo, para habilitar eventos de ciclo de vida de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="db066-157">For example, to enable command life-cycle events, type:</span></span>

```powershell
$LogCommandLifeCycleEvent
```

<span data-ttu-id="db066-158">Ou, digite:</span><span class="sxs-lookup"><span data-stu-id="db066-158">Or, type:</span></span>

```powershell
$LogCommandLifeCycleEvent = $true
```

<span data-ttu-id="db066-159">Para desabilitar um tipo de evento, defina a variável de preferência para esse tipo de evento como $false.</span><span class="sxs-lookup"><span data-stu-id="db066-159">To disable an event type, set the preference variable for that event type to $false.</span></span> <span data-ttu-id="db066-160">Por exemplo, para desabilitar eventos de ciclo de vida de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="db066-160">For example, to disable command life-cycle events, type:</span></span>

```powershell
$LogProviderLifeCycleEvent = $false
```

<span data-ttu-id="db066-161">Você pode desabilitar qualquer evento, exceto os eventos que indicam que o mecanismo do Windows PowerShell e os provedores principais são iniciados.</span><span class="sxs-lookup"><span data-stu-id="db066-161">You can disable any event, except for the events that indicate that the Windows PowerShell engine and the core providers are started.</span></span> <span data-ttu-id="db066-162">Esses eventos são gerados antes que os perfis do Windows PowerShell sejam executados e antes que o programa host esteja pronto para aceitar comandos.</span><span class="sxs-lookup"><span data-stu-id="db066-162">These events are generated before the Windows PowerShell profiles are run and before the host program is ready to accept commands.</span></span>

<span data-ttu-id="db066-163">As configurações de variável se aplicam somente à sessão atual do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db066-163">The variable settings apply only for the current Windows PowerShell session.</span></span>
<span data-ttu-id="db066-164">Para aplicá-las a todas as sessões do Windows PowerShell, adicione-as ao seu perfil do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db066-164">To apply them to all Windows PowerShell sessions, add them to your Windows PowerShell profile.</span></span>

## <a name="logging-module-events"></a><span data-ttu-id="db066-165">Log de eventos do módulo</span><span class="sxs-lookup"><span data-stu-id="db066-165">Logging Module Events</span></span>

<span data-ttu-id="db066-166">A partir do Windows PowerShell 3,0, você pode registrar eventos de execução para os cmdlets e funções nos módulos e snap-ins do Windows PowerShell definindo a propriedade LogPipelineExecutionDetails de módulos e snap-ins como TRUE.</span><span class="sxs-lookup"><span data-stu-id="db066-166">Beginning in Windows PowerShell 3.0, you can record execution events for the cmdlets and functions in Windows PowerShell modules and snap-ins by setting the LogPipelineExecutionDetails property of modules and snap-ins to TRUE.</span></span> <span data-ttu-id="db066-167">No Windows PowerShell 2,0, esse recurso está disponível apenas para snap-ins.</span><span class="sxs-lookup"><span data-stu-id="db066-167">In Windows PowerShell 2.0, this feature is available only for snap-ins.</span></span>

<span data-ttu-id="db066-168">Quando o valor da propriedade LogPipelineExecutionDetails é TRUE ( `$true` ), o Windows PowerShell grava os eventos de execução de cmdlet e função na sessão para o log do Windows PowerShell em Visualizador de eventos.</span><span class="sxs-lookup"><span data-stu-id="db066-168">When the LogPipelineExecutionDetails property value is TRUE (`$true`), Windows PowerShell writes cmdlet and function execution events in the session to the Windows PowerShell log in Event Viewer.</span></span> <span data-ttu-id="db066-169">A configuração só é eficaz na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="db066-169">The setting is effective only in the current session.</span></span>

<span data-ttu-id="db066-170">Para habilitar o log de eventos de execução de cmdlets e funções em um módulo, use a seguinte sequência de comandos.</span><span class="sxs-lookup"><span data-stu-id="db066-170">To enable logging of execution events of cmdlets and functions in a module, use the following command sequence.</span></span>

```powershell
Import-Module <ModuleName>
$m = Get-Module <ModuleName>
$m.LogPipelineExecutionDetails = $true
```

<span data-ttu-id="db066-171">Para habilitar o log de eventos de execução de cmdlets em um snap-in, use a seguinte sequência de comandos.</span><span class="sxs-lookup"><span data-stu-id="db066-171">To enable logging of execution events of cmdlets in a snap-in, use the following command sequence.</span></span>

```powershell
$m = Get-PSSnapin <SnapInName> [-Registered]
$m.LogPipelineExecutionDetails = $True
```

<span data-ttu-id="db066-172">Para desabilitar o registro em log, use a mesma sequência de comandos para definir o valor da propriedade como FALSE ( `$false` ).</span><span class="sxs-lookup"><span data-stu-id="db066-172">To disable logging, use the same command sequence to set the property value to FALSE (`$false`).</span></span>

<span data-ttu-id="db066-173">Você também pode usar a configuração de Política de Grupo "ativar registro em log de módulo" para habilitar e desabilitar o módulo e o registro em log do snap-in.</span><span class="sxs-lookup"><span data-stu-id="db066-173">You can also use the "Turn on Module Logging" Group Policy setting to enable and disable module and snap-in logging.</span></span> <span data-ttu-id="db066-174">O valor da política inclui uma lista de nomes de módulo e snap-in.</span><span class="sxs-lookup"><span data-stu-id="db066-174">The policy value includes a list of module and snap-in names.</span></span> <span data-ttu-id="db066-175">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="db066-175">Wildcards are supported.</span></span>

<span data-ttu-id="db066-176">Quando "ativar o registro em log de módulo" está definido para um módulo, o valor da propriedade LogPipelineExecutionDetails do módulo é TRUE em todas as sessões e não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="db066-176">When "Turn on Module Logging" is set for a module, the value of the LogPipelineExecutionDetails property of the module is TRUE in all sessions and it cannot be changed.</span></span>

<span data-ttu-id="db066-177">A configuração da política de grupo ativar log de módulo está localizada nos seguintes caminhos de Política de Grupo:</span><span class="sxs-lookup"><span data-stu-id="db066-177">The Turn On Module Logging group policy setting is located in the following Group Policy paths:</span></span>

```
Computer Configuration\
  Administrative Templates\
    Windows Components\
     Windows PowerShell

User Configuration\
  Administrative Templates\
    Windows Components\
      Windows PowerShell
```

<span data-ttu-id="db066-178">A política de configuração de usuário tem precedência sobre a política de configuração do computador e ambas as políticas têm preferência sobre o valor da propriedade LogPipelineExecutionDetails de módulos e snap-ins.</span><span class="sxs-lookup"><span data-stu-id="db066-178">The User Configuration policy takes precedence over the Computer Configuration policy, and both policies take preference over the value of the LogPipelineExecutionDetails property of modules and snap-ins.</span></span>

<span data-ttu-id="db066-179">Para obter mais informações sobre essa configuração de Política de Grupo, consulte [about_Group_Policy_Settings](about_Group_Policy_Settings.md).</span><span class="sxs-lookup"><span data-stu-id="db066-179">For more information about this Group Policy setting, see [about_Group_Policy_Settings](about_Group_Policy_Settings.md).</span></span>

## <a name="security-and-auditing"></a><span data-ttu-id="db066-180">Segurança e auditoria</span><span class="sxs-lookup"><span data-stu-id="db066-180">Security and Auditing</span></span>

<span data-ttu-id="db066-181">O log de eventos do Windows PowerShell foi projetado para indicar a atividade e fornecer detalhes operacionais para solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="db066-181">The Windows PowerShell event log is designed to indicate activity and to provide operational details for troubleshooting.</span></span>

<span data-ttu-id="db066-182">No entanto, como a maioria dos logs de eventos de aplicativo baseados no Windows, o log de eventos do Windows PowerShell não foi projetado para ser seguro.</span><span class="sxs-lookup"><span data-stu-id="db066-182">However, like most Windows-based application event logs, the Windows PowerShell event log is not designed to be secure.</span></span> <span data-ttu-id="db066-183">Ele não deve ser usado para auditar a segurança ou registrar informações confidenciais ou proprietárias.</span><span class="sxs-lookup"><span data-stu-id="db066-183">It should not be used to audit security or to record confidential or proprietary information.</span></span>

<span data-ttu-id="db066-184">Os logs de eventos são projetados para serem lidos e compreendidos pelos usuários.</span><span class="sxs-lookup"><span data-stu-id="db066-184">Event logs are designed to be read and understood by users.</span></span> <span data-ttu-id="db066-185">Os usuários podem ler e gravar no log.</span><span class="sxs-lookup"><span data-stu-id="db066-185">Users can read from and write to the log.</span></span> <span data-ttu-id="db066-186">Um usuário mal-intencionado pode ler um log de eventos em um computador local ou remoto, gravar dados falsos e, em seguida, impedir o registro em log de suas atividades.</span><span class="sxs-lookup"><span data-stu-id="db066-186">A malicious user could read an event log on a local or remote computer, record false data, and then prevent the logging of their activities.</span></span>

## <a name="notes"></a><span data-ttu-id="db066-187">Observações</span><span class="sxs-lookup"><span data-stu-id="db066-187">Notes</span></span>

<span data-ttu-id="db066-188">Os autores de autores de módulo podem adicionar recursos de registro em seus módulos.</span><span class="sxs-lookup"><span data-stu-id="db066-188">Authors of module authors can add logging features to their modules.</span></span> <span data-ttu-id="db066-189">Para obter mais informações, consulte [escrevendo um módulo do Windows PowerShell](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span><span class="sxs-lookup"><span data-stu-id="db066-189">For more information, see [Writing a Windows PowerShell Module](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span></span>

## <a name="see-also"></a><span data-ttu-id="db066-190">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="db066-190">See Also</span></span>

[<span data-ttu-id="db066-191">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="db066-191">Get-EventLog</span></span>](xref:Microsoft.PowerShell.Management.Get-EventLog)

[<span data-ttu-id="db066-192">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="db066-192">Get-WmiObject</span></span>](xref:Microsoft.PowerShell.Management.Get-WmiObject)

[<span data-ttu-id="db066-193">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="db066-193">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="db066-194">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="db066-194">about_Preference_Variables</span></span>](about_Preference_Variables.md)
