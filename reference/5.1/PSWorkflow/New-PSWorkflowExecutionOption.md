---
external help file: Microsoft.Powershell.Workflow.ServiceCore.dll-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSWorkflow
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/new-psworkflowexecutionoption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSWorkflowExecutionOption
ms.openlocfilehash: db5d19396f555a41ad14552823c57f3b11c79321
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93194906"
---
# <span data-ttu-id="53a6a-103">New-PSWorkflowExecutionOption</span><span class="sxs-lookup"><span data-stu-id="53a6a-103">New-PSWorkflowExecutionOption</span></span>

## <span data-ttu-id="53a6a-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="53a6a-104">SYNOPSIS</span></span>

<span data-ttu-id="53a6a-105">Cria um objeto que contém opções de configuração de sessão para sessões de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="53a6a-105">Creates an object that contains session configuration options for workflow sessions.</span></span>

## <span data-ttu-id="53a6a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="53a6a-106">SYNTAX</span></span>

```
New-PSWorkflowExecutionOption [-PersistencePath <String>] [-MaxPersistenceStoreSizeGB <Int64>]
 [-PersistWithEncryption] [-MaxRunningWorkflows <Int32>] [-AllowedActivity <String[]>]
 [-OutOfProcessActivity <String[]>] [-EnableValidation] [-MaxDisconnectedSessions <Int32>]
 [-MaxConnectedSessions <Int32>] [-MaxSessionsPerWorkflow <Int32>] [-MaxSessionsPerRemoteNode <Int32>]
 [-MaxActivityProcesses <Int32>] [-ActivityProcessIdleTimeoutSec <Int32>]
 [-RemoteNodeSessionIdleTimeoutSec <Int32>] [-SessionThrottleLimit <Int32>]
 [-WorkflowShutdownTimeoutMSec <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="53a6a-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="53a6a-107">DESCRIPTION</span></span>

<span data-ttu-id="53a6a-108">O `New-PSWorkflowExecutionOption` cmdlet cria um objeto que contém opções avançadas para configurações de sessão de fluxo de trabalho, que são as configurações de sessão criadas para executar fluxos de trabalho de fluxo de trabalho do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="53a6a-108">The `New-PSWorkflowExecutionOption` cmdlet creates an object that contains advanced options for workflow session configurations, that is session configurations designed to run Windows PowerShell Workflow workflows.</span></span>

<span data-ttu-id="53a6a-109">Você pode usar o objeto **PSWorkflowExecutionOption** que `New-PSWorkflowExecutionOption` gera como o valor do parâmetro **SessionTypeOption** de cmdlets que criam ou alteram uma configuração de sessão, como os `Register-PSSessionConfiguration` `Set-PSSessionConfiguration` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="53a6a-109">You can use the **PSWorkflowExecutionOption** object that `New-PSWorkflowExecutionOption` generates as the value of the **SessionTypeOption** parameter of cmdlets that create or change a session configuration, such as the `Register-PSSessionConfiguration` and `Set-PSSessionConfiguration` cmdlets.</span></span>

<span data-ttu-id="53a6a-110">Cada parâmetro do `New-PSWorkflowExecutionOption` cmdlet representa uma propriedade do objeto de opção de configuração de sessão de fluxo de trabalho que o cmdlet retorna.</span><span class="sxs-lookup"><span data-stu-id="53a6a-110">Each parameter of the `New-PSWorkflowExecutionOption` cmdlet represents a property of the workflow session configuration option object that the cmdlet returns.</span></span> <span data-ttu-id="53a6a-111">Se um parâmetro for omitido, o cmdlet cria o objeto com um valor padrão para a propriedade.</span><span class="sxs-lookup"><span data-stu-id="53a6a-111">If you omit a parameter, the cmdlet creates the object with a default value for the property.</span></span>

<span data-ttu-id="53a6a-112">O `New-PSWorkflowExecutionOption` cmdlet faz parte do recurso de fluxo de trabalho do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="53a6a-112">The `New-PSWorkflowExecutionOption` cmdlet is part of the Windows PowerShell Workflow feature.</span></span>

<span data-ttu-id="53a6a-113">Também é possível adicionar parâmetros comuns de fluxo de trabalho para esse comando.</span><span class="sxs-lookup"><span data-stu-id="53a6a-113">You can also add workflow common parameters to this command.</span></span> <span data-ttu-id="53a6a-114">Para obter mais informações sobre parâmetros comuns de fluxo de trabalho, consulte [about_WorkflowCommonParameters](About/about_WorkflowCommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="53a6a-114">For more information about workflow common parameters, see [about_WorkflowCommonParameters](About/about_WorkflowCommonParameters.md).</span></span>

<span data-ttu-id="53a6a-115">Este cmdlet é introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="53a6a-115">This cmdlet is introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="53a6a-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="53a6a-116">EXAMPLES</span></span>

### <span data-ttu-id="53a6a-117">Exemplo 1: criar um objeto de opções de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="53a6a-117">Example 1: Create a Workflow Options Object</span></span>

```powershell
New-PSWorkflowExecutionOption -MaxSessionsPerWorkflow 10 -MaxDisconnectedSessions 200
```

```Output
SessionThrottleLimit                       : 100
PersistencePath                            : C:\Users\User01\AppData\Local\Microsoft\Windows\PowerShell\WF\PS
MaxPersistenceStoreSizeGB                  : 10
PersistWithEncryption                      : False
MaxRunningWorkflows                        : 30
AllowedActivity                            : {PSDefaultActivities}
OutOfProcessActivity                       : {InlineScript}
EnableValidation                           : True
MaxDisconnectedSessions                    : 200
MaxConnectedSessions                       : 100
MaxSessionsPerWorkflow                     : 10
MaxSessionsPerRemoteNode                   : 5
MaxActivityProcesses                       : 5
ActivityProcessIdleTimeoutSec              : 60
RemoteNodeSessionIdleTimeoutSec            : 60
WorkflowShutdownTimeoutMSec                : 500
```

<span data-ttu-id="53a6a-118">Esse comando usa o `New-PSWorkflowExecutionOption` cmdlet para aumentar o valor de **MaxSessionsPerWorkflow** para 10 e diminuir o valor de **MaxDisconnectedSessions** para 200.</span><span class="sxs-lookup"><span data-stu-id="53a6a-118">This command uses the `New-PSWorkflowExecutionOption` cmdlet to increase the **MaxSessionsPerWorkflow** value to 10 and decrease the **MaxDisconnectedSessions** value to 200.</span></span>

<span data-ttu-id="53a6a-119">A saída mostra o objeto que o cmdlet retorna.</span><span class="sxs-lookup"><span data-stu-id="53a6a-119">The output shows the object that the cmdlet returns.</span></span>

### <span data-ttu-id="53a6a-120">Exemplo 2: usando um objeto de opções de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="53a6a-120">Example 2: Using a Workflow Options Object</span></span>

```powershell
# Create a Workflow Options object and save it in a variable
$wo = New-PSWorkflowExecutionOption -MaxSessionsPerWorkflow 10 -MaxDisconnectedSessions 200
# Create the ITWorkflow session configuration
Register-PSSessionConfiguration -Name ITWorkflows -SessionTypeOption $wo -Force
```

```Output
    WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin

Type            Keys                                Name
----            ----                                ----
Container       {Name=ITWorkflows}                  ITWorkflows
```

```powershell
Get-PSSessionConfiguration ITWorkflows | Format-List -Property *
```

```Output
Architecture                  : 64
Filename                      : %windir%\system32\pwrshplugin.dll
ResourceUri                   : http://schemas.microsoft.com/powershell/ITWorkflows
MaxConcurrentCommandsPerShell : 1000
allowedactivity               : PSDefaultActivities
UseSharedProcess              : false
ProcessIdleTimeoutSec         : 0
xmlns                         : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
MaxConcurrentUsers            : 5
maxsessionsperworkflow        : 10
lang                          : en-US
sessionconfigurationdata      : <SessionConfigurationData>
                                    <Param Name='PrivateData'>
                                        <PrivateData>
                                            <ParamName='enablevalidation' Value='True'/>
                                            <Param Name='allowedactivity'Value='PSDefaultActivities' />
                                            <Param Name='outofprocessactivity' Value='InlineScript'/>
                                            <Param Name='maxdisconnectedsessions' Value='200' />
                                            <ParamName='maxsessionsperworkflow' Value='10'/>
                                        </PrivateData>
                                    </Param>
                                </SessionConfigurationData>
SupportsOptions               : true
ExactMatch                    : true
RunAsUser                     :
IdleTimeoutms                 : 7200000
PSVersion                     : 3.0
OutputBufferingMode           : Block
AutoRestart                   : false
MaxShells                     : 25
MaxMemoryPerShellMB           : 1024
MaxIdleTimeoutms              : 43200000
outofprocessactivity          : InlineScript
SDKVersion                    : 2
Name                          : ITWorkflows
XmlRenderingType              : text
Capability                    : {Shell}
RunAsPassword                 :
MaxProcessesPerShell          : 15
enablevalidation              : True
Enabled                       : True
maxdisconnectedsessions       : 200
MaxShellsPerUser              : 25
Permission                    :
```

<span data-ttu-id="53a6a-121">Os dois primeiros comandos criam um novo objeto de configuração de sessão e o registra.</span><span class="sxs-lookup"><span data-stu-id="53a6a-121">The first two commands create a new session configuration object and registers it.</span></span>

<span data-ttu-id="53a6a-122">O terceiro comando usa o `Get-PSSessionConfiguration` cmdlet para obter a configuração de sessão ITWorkflows e o `Format-List` para exibir todas as propriedades da configuração de sessão em uma lista. A saída mostra que as opções de fluxo de trabalho na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="53a6a-122">The third command uses the `Get-PSSessionConfiguration` cmdlet to the get the ITWorkflows session configuration and the `Format-List` to display all properties of the session configuration in a list.The output shows that the workflow options in the session configuration.</span></span> <span data-ttu-id="53a6a-123">Especificamente, a configuração de sessão tem uma propriedade **MaxSessionsPerWorkflow** com um valor de 10 e uma propriedade **MaxDisconnectedSessions** com um valor de 200.</span><span class="sxs-lookup"><span data-stu-id="53a6a-123">Specifically, the session configuration has a **MaxSessionsPerWorkflow** property with a value of 10 and a **MaxDisconnectedSessions** property with a value of 200.</span></span>

## <span data-ttu-id="53a6a-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="53a6a-124">PARAMETERS</span></span>

### <span data-ttu-id="53a6a-125">-ActivityProcessIdleTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="53a6a-125">-ActivityProcessIdleTimeoutSec</span></span>

<span data-ttu-id="53a6a-126">Determina por quanto tempo cada processo do host de atividade é mantido depois que o processo se torna ocioso.</span><span class="sxs-lookup"><span data-stu-id="53a6a-126">Determines how long each activity host process is maintained after the process becomes idle.</span></span> <span data-ttu-id="53a6a-127">Quando o intervalo expira, o processo é encerrado.</span><span class="sxs-lookup"><span data-stu-id="53a6a-127">When the interval expires, the process closes.</span></span>

<span data-ttu-id="53a6a-128">Insira um valor em segundos.</span><span class="sxs-lookup"><span data-stu-id="53a6a-128">Enter a value in seconds.</span></span> <span data-ttu-id="53a6a-129">O valor padrão é 60.</span><span class="sxs-lookup"><span data-stu-id="53a6a-129">The default value is 60.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 60
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="53a6a-130">-AllowedActivity</span><span class="sxs-lookup"><span data-stu-id="53a6a-130">-AllowedActivity</span></span>

<span data-ttu-id="53a6a-131">Especifica as atividades que têm permissão para serem executadas na sessão.</span><span class="sxs-lookup"><span data-stu-id="53a6a-131">Specifies the activities that are permitted to run in the session.</span></span>

<span data-ttu-id="53a6a-132">Insira nomes de atividades qualificadas para namespace, como `Microsoft.Powershell.HyperV.Activities.*` .</span><span class="sxs-lookup"><span data-stu-id="53a6a-132">Enter namespace-qualified activity names, such as `Microsoft.Powershell.HyperV.Activities.*`.</span></span>
<span data-ttu-id="53a6a-133">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="53a6a-133">Wildcard characters are supported.</span></span> <span data-ttu-id="53a6a-134">O valor padrão, **PSDefaultActivities** , inclui as atividades internas do Windows Workflow Foundation e as atividades que representam os cmdlets do Windows PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="53a6a-134">The default value, **PSDefaultActivities** , includes the built-in Windows Workflow Foundation activities and the activities that represent the Windows PowerShell Core cmdlets.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: PSDefaultActivities
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="53a6a-135">-EnableValidation</span><span class="sxs-lookup"><span data-stu-id="53a6a-135">-EnableValidation</span></span>

<span data-ttu-id="53a6a-136">Verifica se todas as atividades de fluxo de trabalho na sessão estão incluídas na lista de atividades permitidas.</span><span class="sxs-lookup"><span data-stu-id="53a6a-136">Verifies that all workflow activities in the session are included in the allowed activities list.</span></span>

<span data-ttu-id="53a6a-137">O valor padrão é True.</span><span class="sxs-lookup"><span data-stu-id="53a6a-137">The default value is True.</span></span> <span data-ttu-id="53a6a-138">Para desabilitar a validação, use o seguinte formato de comando: `-EnableValidation:$false` .</span><span class="sxs-lookup"><span data-stu-id="53a6a-138">To disable validation, use the following command format: `-EnableValidation:$false`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="53a6a-139">-MaxActivityProcesses</span><span class="sxs-lookup"><span data-stu-id="53a6a-139">-MaxActivityProcesses</span></span>

<span data-ttu-id="53a6a-140">Especifica o número máximo de processos que podem ser criados na sessão para oferecer suporte a atividades de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="53a6a-140">Specifies the maximum number of processes that can be created in the session to support workflow activities.</span></span> <span data-ttu-id="53a6a-141">O valor padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="53a6a-141">The default value is 5.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="53a6a-142">-MaxConnectedSessions</span><span class="sxs-lookup"><span data-stu-id="53a6a-142">-MaxConnectedSessions</span></span>

<span data-ttu-id="53a6a-143">Especifica o número máximo de sessões remotas que estão em um estado operacional.</span><span class="sxs-lookup"><span data-stu-id="53a6a-143">Specifies the maximum number of remote sessions that are in an operational state.</span></span> <span data-ttu-id="53a6a-144">Essa cota é aplicada as sessões conectadas a todos os nós remotos (computadores de destino).</span><span class="sxs-lookup"><span data-stu-id="53a6a-144">This quota is applied to sessions connected to all remote nodes (target computers).</span></span> <span data-ttu-id="53a6a-145">O valor padrão é 100.</span><span class="sxs-lookup"><span data-stu-id="53a6a-145">The default value is 100.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="53a6a-146">-MaxDisconnectedSessions</span><span class="sxs-lookup"><span data-stu-id="53a6a-146">-MaxDisconnectedSessions</span></span>

<span data-ttu-id="53a6a-147">Especifica o número máximo de sessões remotas que estão em um estado desconectado.</span><span class="sxs-lookup"><span data-stu-id="53a6a-147">Specifies the maximum number of remote sessions that are in a disconnected state.</span></span> <span data-ttu-id="53a6a-148">Essa cota é aplicada as sessões conectadas a todos os nós remotos (computadores de destino).</span><span class="sxs-lookup"><span data-stu-id="53a6a-148">This quota is applied to sessions connected to all remote nodes (target computers).</span></span> <span data-ttu-id="53a6a-149">O valor padrão é 1000.</span><span class="sxs-lookup"><span data-stu-id="53a6a-149">The default value is 1000.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1000
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="53a6a-150">-MaxPersistenceStoreSizeGB</span><span class="sxs-lookup"><span data-stu-id="53a6a-150">-MaxPersistenceStoreSizeGB</span></span>

<span data-ttu-id="53a6a-151">Especifica o tamanho máximo, em gigabytes, do repositório de persistência alocada para fluxos de trabalho executados na sessão.</span><span class="sxs-lookup"><span data-stu-id="53a6a-151">Specifies the maximum size, in gigabytes, of the persistence store allocated to workflows that run in the session.</span></span> <span data-ttu-id="53a6a-152">Quando o tamanho for excedido, o repositório de persistência é expandido para salvar todos os dados persistentes, mas um aviso é exibido e uma mensagem é gravada no log de eventos do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="53a6a-152">When the size is exceeded, the persistence store is expanded to save all persisted data, but a warning is displayed and a message is written to the workflow event log.</span></span> <span data-ttu-id="53a6a-153">O valor padrão é 10.</span><span class="sxs-lookup"><span data-stu-id="53a6a-153">The default value is 10.</span></span>

<span data-ttu-id="53a6a-154">O repositório de persistência contém dados para todos os trabalhos de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="53a6a-154">The persistence store contains data for all workflow jobs.</span></span> <span data-ttu-id="53a6a-155">A capacidade de armazenar dados permite que os trabalhos continue sem perder o estado.</span><span class="sxs-lookup"><span data-stu-id="53a6a-155">The ability to store data allows the jobs to resume without losing state.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 10
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="53a6a-156">-MaxRunningWorkflows</span><span class="sxs-lookup"><span data-stu-id="53a6a-156">-MaxRunningWorkflows</span></span>

<span data-ttu-id="53a6a-157">Especifica o número máximo de fluxos de trabalho que podem ser executados na sessão simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="53a6a-157">Specifies that maximum number of workflows that can run in the session concurrently.</span></span>
<span data-ttu-id="53a6a-158">O valor padrão é 30.</span><span class="sxs-lookup"><span data-stu-id="53a6a-158">The default value is 30.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 30
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="53a6a-159">-MaxSessionsPerRemoteNode</span><span class="sxs-lookup"><span data-stu-id="53a6a-159">-MaxSessionsPerRemoteNode</span></span>

<span data-ttu-id="53a6a-160">Especifica o número máximo de sessões que podem ser conectados a cada nó remoto (computador de destino).</span><span class="sxs-lookup"><span data-stu-id="53a6a-160">Specifies the maximum number of sessions that can be connected to each remote node (target computer).</span></span> <span data-ttu-id="53a6a-161">O valor padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="53a6a-161">The default value is 5.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="53a6a-162">-MaxSessionsPerWorkflow</span><span class="sxs-lookup"><span data-stu-id="53a6a-162">-MaxSessionsPerWorkflow</span></span>

<span data-ttu-id="53a6a-163">Especifica o número máximo de sessões que podem ser criadas para oferecer suporte a cada fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="53a6a-163">Specifies the maximum number of session that can be created to support each workflow.</span></span> <span data-ttu-id="53a6a-164">O valor padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="53a6a-164">The default value is 5.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="53a6a-165">-OutOfProcessActivity</span><span class="sxs-lookup"><span data-stu-id="53a6a-165">-OutOfProcessActivity</span></span>

<span data-ttu-id="53a6a-166">Determina quais atividades têm permissão (especificadas pelo parâmetro **AllowedActivities** ) para serem executadas fora do processo.</span><span class="sxs-lookup"><span data-stu-id="53a6a-166">Determines which allowed activities (specified by the **AllowedActivities** parameter) run out-of-process.</span></span> <span data-ttu-id="53a6a-167">O valor padrão é **InlineScript** .</span><span class="sxs-lookup"><span data-stu-id="53a6a-167">The default value is **InlineScript** .</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: InlineScript
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="53a6a-168">-PersistencePath</span><span class="sxs-lookup"><span data-stu-id="53a6a-168">-PersistencePath</span></span>

<span data-ttu-id="53a6a-169">Especifica o local no disco onde o estado de fluxo de trabalho e os dados são armazenados.</span><span class="sxs-lookup"><span data-stu-id="53a6a-169">Specifies the location on disk where workflow state and data are stored.</span></span> <span data-ttu-id="53a6a-170">Armazenar o estado de fluxo de trabalho e dados permite que os fluxos de trabalho sejam suspensos e retomados, e recuperados de interrupções e falhas de rede.</span><span class="sxs-lookup"><span data-stu-id="53a6a-170">Storing the workflow state and data allows workflows to be suspended and resumed, and to recover from interruptions and network failures.</span></span>

<span data-ttu-id="53a6a-171">O valor padrão é `$env:LocalAppData\Microsoft\Windows\PowerShell\WF\PS`.</span><span class="sxs-lookup"><span data-stu-id="53a6a-171">The default value is `$env:LocalAppData\Microsoft\Windows\PowerShell\WF\PS`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="53a6a-172">-PersistWithEncryption</span><span class="sxs-lookup"><span data-stu-id="53a6a-172">-PersistWithEncryption</span></span>

<span data-ttu-id="53a6a-173">Indica que o fluxo de trabalho criptografa os dados no repositório de persistência.</span><span class="sxs-lookup"><span data-stu-id="53a6a-173">Indicates that the workflow encrypts the data in the persistence store.</span></span> <span data-ttu-id="53a6a-174">Considere utilizar esse recurso ao armazenar dados de persistência em um compartilhamento de rede.</span><span class="sxs-lookup"><span data-stu-id="53a6a-174">Consider using this feature when storing persistence data in a network share.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $env:LocalAppData\Microsoft\Windows\PowerShell\WF\PS
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="53a6a-175">-RemoteNodeSessionIdleTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="53a6a-175">-RemoteNodeSessionIdleTimeoutSec</span></span>

<span data-ttu-id="53a6a-176">Especifica quanto tempo uma sessão que está conectada a um nó remoto (computador de destino) é mantida se estiver ociosa.</span><span class="sxs-lookup"><span data-stu-id="53a6a-176">Specifies how long a session that is connected to a remote node (target computer) is maintained if it is idle.</span></span>

<span data-ttu-id="53a6a-177">Insira um valor em segundos.</span><span class="sxs-lookup"><span data-stu-id="53a6a-177">Enter a value in seconds.</span></span> <span data-ttu-id="53a6a-178">O valor padrão é 60.</span><span class="sxs-lookup"><span data-stu-id="53a6a-178">The default value is 60.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 60
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="53a6a-179">-SessionThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="53a6a-179">-SessionThrottleLimit</span></span>

<span data-ttu-id="53a6a-180">Especifica quantas operações são criadas para oferecer suporte a todos os fluxos de trabalho iniciados na sessão.</span><span class="sxs-lookup"><span data-stu-id="53a6a-180">Specifies how many operations are created to support all workflows started in the session.</span></span> <span data-ttu-id="53a6a-181">O valor padrão é 100.</span><span class="sxs-lookup"><span data-stu-id="53a6a-181">The default value is 100.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="53a6a-182">-WorkflowShutdownTimeoutMSec</span><span class="sxs-lookup"><span data-stu-id="53a6a-182">-WorkflowShutdownTimeoutMSec</span></span>

<span data-ttu-id="53a6a-183">Especifica quanto tempo a sessão é mantida depois que todos os fluxos de trabalho na sessão são suspensos à força.</span><span class="sxs-lookup"><span data-stu-id="53a6a-183">Specifies how long the session is maintained after all workflows in the session are forcibly suspended.</span></span> <span data-ttu-id="53a6a-184">Quando o tempo limite expira, o Windows PowerShell encerra a sessão, mesmo que todos os fluxos de trabalho ainda não tenham sido suspensos.</span><span class="sxs-lookup"><span data-stu-id="53a6a-184">When the timeout expires, Windows PowerShell closes the session, even if all workflows are not yet suspended.</span></span>

<span data-ttu-id="53a6a-185">Insira um valor em milissegundos.</span><span class="sxs-lookup"><span data-stu-id="53a6a-185">Enter a value in milliseconds.</span></span>
<span data-ttu-id="53a6a-186">O valor padrão é 500.</span><span class="sxs-lookup"><span data-stu-id="53a6a-186">The default value is 500.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 500
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="53a6a-187">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="53a6a-187">CommonParameters</span></span>

<span data-ttu-id="53a6a-188">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="53a6a-188">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="53a6a-189">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="53a6a-189">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="53a6a-190">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="53a6a-190">INPUTS</span></span>

### <span data-ttu-id="53a6a-191">Nenhum</span><span class="sxs-lookup"><span data-stu-id="53a6a-191">None</span></span>

<span data-ttu-id="53a6a-192">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="53a6a-192">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="53a6a-193">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="53a6a-193">OUTPUTS</span></span>

### <span data-ttu-id="53a6a-194">Microsoft. PowerShell. Commands. PSWorkflowExecutionOption</span><span class="sxs-lookup"><span data-stu-id="53a6a-194">Microsoft.PowerShell.Commands.PSWorkflowExecutionOption</span></span>

## <span data-ttu-id="53a6a-195">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="53a6a-195">NOTES</span></span>

<span data-ttu-id="53a6a-196">Quando o valor máximo definido por uma opção for excedido, o comando para criar outra instância na sessão falha, a menos que esteja indicado na descrição do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="53a6a-196">When the maximum value set by an option is exceeded, the command to create another instance in the session fails, unless noted in the parameter description.</span></span> <span data-ttu-id="53a6a-197">Por exemplo, se o valor de **MaxConnectedSessions** é 100.</span><span class="sxs-lookup"><span data-stu-id="53a6a-197">For example, if the value of **MaxConnectedSessions** is 100.</span></span> <span data-ttu-id="53a6a-198">Falha no comando para criar a sessão de 101 para um nó remoto (computador de destino).</span><span class="sxs-lookup"><span data-stu-id="53a6a-198">The command to create the 101st session to a remote node (target computer) fails.</span></span>

<span data-ttu-id="53a6a-199">As propriedades de um objeto de configuração de sessão variam de acordo com as opções definidas para a configuração da sessão e os valores dessas opções.</span><span class="sxs-lookup"><span data-stu-id="53a6a-199">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="53a6a-200">Além disso, as configurações de sessão que usam um arquivo de configuração de sessão têm propriedades adicionais.</span><span class="sxs-lookup"><span data-stu-id="53a6a-200">Also, session configurations that use a session configuration file have additional properties.</span></span>

<span data-ttu-id="53a6a-201">Em particular, as propriedades de configurações de sessão que incluem um objeto **PSWorkflowExecutionOptions** variam de acordo com os valores de opção de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="53a6a-201">In particular, the properties of session configurations that include a **PSWorkflowExecutionOptions** object vary based on the workflow option values.</span></span> <span data-ttu-id="53a6a-202">Por exemplo, se a configuração de sessão inclui um objeto **PSWorkflowExecutionOptions** que define um valor não padrão para a propriedade **SessionThrottleLimit** , a configuração da sessão tem uma propriedade **SessionThrottleLimit** .</span><span class="sxs-lookup"><span data-stu-id="53a6a-202">For example, if the session configuration includes a **PSWorkflowExecutionOptions** object that sets a non-default value for the **SessionThrottleLimit** property, the session configuration has a **SessionThrottleLimit** property.</span></span> <span data-ttu-id="53a6a-203">Caso contrário, isso não acontece.</span><span class="sxs-lookup"><span data-stu-id="53a6a-203">Otherwise, it does not.</span></span>

## <span data-ttu-id="53a6a-204">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="53a6a-204">RELATED LINKS</span></span>

[<span data-ttu-id="53a6a-205">New-PSWorkflowSession</span><span class="sxs-lookup"><span data-stu-id="53a6a-205">New-PSWorkflowSession</span></span>](New-PSWorkflowSession.md)

[<span data-ttu-id="53a6a-206">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="53a6a-206">about_Workflows</span></span>](../PSWorkflow/About/about_Workflows.md)

[<span data-ttu-id="53a6a-207">about_WorkflowCommonParameters</span><span class="sxs-lookup"><span data-stu-id="53a6a-207">about_WorkflowCommonParameters</span></span>](About/about_WorkflowCommonParameters.md)
