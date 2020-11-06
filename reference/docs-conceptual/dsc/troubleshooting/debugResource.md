---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Depurando os recursos de DSC
description: Este artigo mostra como habilitar a depuração para configurações DSC.
ms.openlocfilehash: 5dda217e8dc9cc4b8699c82153c1a588d405d99e
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92654121"
---
# <a name="debugging-dsc-resources"></a><span data-ttu-id="36718-104">Depurando os recursos de DSC</span><span class="sxs-lookup"><span data-stu-id="36718-104">Debugging DSC resources</span></span>

> <span data-ttu-id="36718-105">Aplica-se a: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="36718-105">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="36718-106">No PowerShell 5.0, foi introduzido um novo recurso na DSC (Desired State Configuration) que permite depurar um recurso de DSC enquanto uma configuração está sendo aplicada.</span><span class="sxs-lookup"><span data-stu-id="36718-106">In PowerShell 5.0, a new feature was introduced in Desired State Configuration (DSC) that allows you to debug a DSC resource as a configuration is being applied.</span></span>

## <a name="enabling-dsc-debugging"></a><span data-ttu-id="36718-107">Habilitando a depuração de DSC</span><span class="sxs-lookup"><span data-stu-id="36718-107">Enabling DSC debugging</span></span>

<span data-ttu-id="36718-108">Para poder depurar um recurso, é preciso habilitar a depuração chamando o cmdlet [Enable-DscDebug](/powershell/module/PSDesiredStateConfiguration/Enable-DscDebug).</span><span class="sxs-lookup"><span data-stu-id="36718-108">Before you can debug a resource, you have to enable debugging by calling the [Enable-DscDebug](/powershell/module/PSDesiredStateConfiguration/Enable-DscDebug) cmdlet.</span></span> <span data-ttu-id="36718-109">Esse cmdlet usa um parâmetro obrigatório, o **BreakAll**.</span><span class="sxs-lookup"><span data-stu-id="36718-109">This cmdlet takes a mandatory parameter, **BreakAll**.</span></span>

<span data-ttu-id="36718-110">É possível verificar se a depuração foi habilitada analisando o resultado de uma chamada para o [Get-DscLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Get-DscLocalConfigurationManager).</span><span class="sxs-lookup"><span data-stu-id="36718-110">You can verify that debugging has been enabled by looking at the result of a call to [Get-DscLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Get-DscLocalConfigurationManager).</span></span>

<span data-ttu-id="36718-111">A seguinte saída do PowerShell mostra o resultado de habilitar a depuração:</span><span class="sxs-lookup"><span data-stu-id="36718-111">The following PowerShell output shows the result of enabling debugging:</span></span>

```powershell
PS C:\DebugTest> $LCM = Get-DscLocalConfigurationManager

PS C:\DebugTest> $LCM.DebugMode
NONE

PS C:\DebugTest> Enable-DscDebug -BreakAll

PS C:\DebugTest> $LCM = Get-DscLocalConfigurationManager

PS C:\DebugTest> $LCM.DebugMode
ForceModuleImport
ResourceScriptBreakAll

PS C:\DebugTest>
```

## <a name="starting-a-configuration-with-debug-enabled"></a><span data-ttu-id="36718-112">Iniciando uma configuração com a depuração habilitada</span><span class="sxs-lookup"><span data-stu-id="36718-112">Starting a configuration with debug enabled</span></span>

<span data-ttu-id="36718-113">Para depurar um recurso de DSC, inicie uma configuração que chame esse recurso.</span><span class="sxs-lookup"><span data-stu-id="36718-113">To debug a DSC resource, you start a configuration that calls that resource.</span></span> <span data-ttu-id="36718-114">Para este exemplo, analisaremos uma configuração simples que chame o recurso **WindowsFeature** a fim de garantir que o recurso "WindowsPowerShellWebAccess" seja instalado:</span><span class="sxs-lookup"><span data-stu-id="36718-114">For this example, we'll look at a simple configuration that calls the **WindowsFeature** resource to ensure that the "WindowsPowerShellWebAccess" feature is installed:</span></span>

```powershell
Configuration PSWebAccess
    {
    Import-DscResource -ModuleName 'PsDesiredStateConfiguration'
    Node localhost
        {
        WindowsFeature PSWA
            {
            Name = 'WindowsPowerShellWebAccess'
            Ensure = 'Present'
            }
        }
    }
PSWebAccess
```

<span data-ttu-id="36718-115">Depois de compilar a configuração, inicie chamando [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration).</span><span class="sxs-lookup"><span data-stu-id="36718-115">After compiling the configuration, start it by calling [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration).</span></span> <span data-ttu-id="36718-116">A configuração parará quando o LCM (Gerenciador de Configurações Local) chamar o primeiro recurso na configuração.</span><span class="sxs-lookup"><span data-stu-id="36718-116">The configuration will stop when the Local Configuration Manager (LCM) calls into the first resource in the configuration.</span></span> <span data-ttu-id="36718-117">Se você usar os parâmetros `-Verbose` e `-Wait`, a saída exibirá as linhas que você precisa inserir para iniciar a depuração.</span><span class="sxs-lookup"><span data-stu-id="36718-117">If you use the `-Verbose` and `-Wait` parameters, the output displays the lines you need to enter to start debugging.</span></span>

```powershell
Start-DscConfiguration .\PSWebAccess -Wait -Verbose
VERBOSE: Perform operation 'Invoke CimMethod' with following parameters, ''methodName' = SendConfigurationApply,'className' = MSFT_DSCLocalConfiguration
Manager,'namespaceName' = root/Microsoft/Windows/DesiredStateConfiguration'.
VERBOSE: An LCM method call arrived from computer TEST-SRV with user sid S-1-5-21-2127521184-1604012920-1887927527-108583.
VERBOSE: An LCM method call arrived from computer TEST-SRV with user sid S-1-5-21-2127521184-1604012920-1887927527-108583.
VERBOSE: [TEST-SRV]: LCM:  [ Start  Set      ]
WARNING: [TEST-SRV]:                            [DSCEngine] Warning LCM is in Debug 'ResourceScriptBreakAll' mode.  Resource script processing will
be stopped to wait for PowerShell script debugger to attach.
VERBOSE: [TEST-SRV]:                            [DSCEngine] Importing the module C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules\PSDesiredStateCo
nfiguration\DscResources\MSFT_RoleResource\MSFT_RoleResource.psm1 in force mode.
VERBOSE: [TEST-SRV]: LCM:  [ Start  Resource ]  [[WindowsFeature]PSWA]
VERBOSE: [TEST-SRV]: LCM:  [ Start  Test     ]  [[WindowsFeature]PSWA]
VERBOSE: [TEST-SRV]:                            [[WindowsFeature]PSWA] Importing the module MSFT_RoleResource in force mode.
WARNING: [TEST-SRV]:                            [[WindowsFeature]PSWA] Resource is waiting for PowerShell script debugger to attach.
Use the following commands to begin debugging this resource script:
Enter-PSSession -ComputerName TEST-SRV -Credential <credentials>
Enter-PSHostProcess -Id 9000 -AppDomainName DscPsPluginWkr_AppDomain
Debug-Runspace -Id 9
```

<span data-ttu-id="36718-118">Nesse ponto, o LCM chama o recurso e vai até o primeiro ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="36718-118">At this point, the LCM has called the resource, and come to the first break point.</span></span> <span data-ttu-id="36718-119">As três últimas linhas na saída mostram como anexar ao processo e iniciar a depuração do script do recurso.</span><span class="sxs-lookup"><span data-stu-id="36718-119">The last three lines in the output show you how to attach to the process and start debugging the resource script.</span></span>

## <a name="debugging-the-resource-script"></a><span data-ttu-id="36718-120">Depurando o script de recurso</span><span class="sxs-lookup"><span data-stu-id="36718-120">Debugging the resource script</span></span>

<span data-ttu-id="36718-121">Inicie uma nova instância do ISE do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="36718-121">Start a new instance of the PowerShell ISE.</span></span> <span data-ttu-id="36718-122">No painel do console, digite as três últimas linhas da saída `Start-DscConfiguration` como comandos, substituindo `<credentials>` por credenciais de usuário válidas.</span><span class="sxs-lookup"><span data-stu-id="36718-122">In the console pane, enter the last three lines of output from the `Start-DscConfiguration` output as commands, replacing `<credentials>` with valid user credentials.</span></span> <span data-ttu-id="36718-123">Agora você verá um prompt semelhante a:</span><span class="sxs-lookup"><span data-stu-id="36718-123">You should now see a prompt that looks similar to:</span></span>

```powershell
[TEST-SRV]: [DBG]: [Process:9000]: [RemoteHost]: PS C:\DebugTest>>
```

<span data-ttu-id="36718-124">O script de recurso será aberto no painel de script e o depurador será interrompido na primeira linha da função **Test-TargetResource** (o método **Test()** de um recurso baseado em classe).</span><span class="sxs-lookup"><span data-stu-id="36718-124">The resource script will open in the script pane, and the debugger is stopped at the first line of the **Test-TargetResource** function (the **Test()** method of a class-based resource).</span></span> <span data-ttu-id="36718-125">Agora você pode usar os comandos de depuração no ISE para percorrer o script de recurso, examinar os valores das variáveis, exibir a pilha de chamadas e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="36718-125">Now you can use the debug commands in the ISE to step through the resource script, look at variable values, view the call stack, and so on.</span></span> <span data-ttu-id="36718-126">Lembre-se de que toda linha no script de recurso (ou classe) é definida como um ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="36718-126">Remember that every line in the resource script (or class) is set as a break point.</span></span>

## <a name="disabling-dsc-debugging"></a><span data-ttu-id="36718-127">Desabilitando a depuração de DSC</span><span class="sxs-lookup"><span data-stu-id="36718-127">Disabling DSC debugging</span></span>

<span data-ttu-id="36718-128">Depois de chamar [Enable DscDebug](/powershell/module/PSDesiredStateConfiguration/Enable-DscDebug), todas as chamadas a [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) resultarão na interrupção do depurador pela configuração.</span><span class="sxs-lookup"><span data-stu-id="36718-128">After calling [Enable-DscDebug](/powershell/module/PSDesiredStateConfiguration/Enable-DscDebug), all calls to [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) will result in the configuration breaking into the debugger.</span></span> <span data-ttu-id="36718-129">Para permitir que as configurações sejam executadas normalmente, você deve desabilitar a depuração chamando o cmdlet [Disable-DscDebug](/powershell/module/PSDesiredStateConfiguration/Disable-DscDebug).</span><span class="sxs-lookup"><span data-stu-id="36718-129">To allow configurations to run normally, you must disable debugging by calling the [Disable-DscDebug](/powershell/module/PSDesiredStateConfiguration/Disable-DscDebug) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="36718-130">a reinicialização não altera o estado de depuração do LCM.</span><span class="sxs-lookup"><span data-stu-id="36718-130">Rebooting does not change the debug state of the LCM.</span></span> <span data-ttu-id="36718-131">Se a depuração estiver desabilitada, iniciar uma configuração ainda interromperá o depurador após uma reinicialização.</span><span class="sxs-lookup"><span data-stu-id="36718-131">If debugging is enabled, starting a configuration will still break into the debugger after a reboot.</span></span>

## <a name="see-also"></a><span data-ttu-id="36718-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="36718-132">See Also</span></span>

- [<span data-ttu-id="36718-133">Escrevendo um recurso personalizado de DSC com MOF</span><span class="sxs-lookup"><span data-stu-id="36718-133">Writing a custom DSC resource with MOF</span></span>](../resources/authoringResourceMOF.md)
- [<span data-ttu-id="36718-134">Escrevendo um recurso personalizado de DSC com classes do PowerShell</span><span class="sxs-lookup"><span data-stu-id="36718-134">Writing a custom DSC resource with PowerShell classes</span></span>](../resources/authoringResourceClass.md)
