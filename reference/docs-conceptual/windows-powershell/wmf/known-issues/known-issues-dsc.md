---
ms.date: 06/12/2017
title: Limitações e problemas conhecidos do DSC (Configuração de Estado Desejado)
description: Limitações e problemas conhecidos da DSC no Windows PowerShell 5.x
ms.openlocfilehash: 1163ed9e130430f6bbca98405a8993bb054dd1a8
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92662044"
---
# <a name="desired-state-configuration-dsc-known-issues-and-limitations"></a><span data-ttu-id="25bad-103">Limitações e problemas conhecidos do DSC (Configuração de Estado Desejado)</span><span class="sxs-lookup"><span data-stu-id="25bad-103">Desired State Configuration (DSC) Known Issues and Limitations</span></span>

## <a name="breaking-change-certificates-used-to-encryptdecrypt-passwords-in-dsc-configurations-may-not-work-after-installing-wmf-50-rtm"></a><span data-ttu-id="25bad-104">Alteração da falha: certificados usados para criptografar/descriptografar senhas em configurações de DSC podem não funcionar após a instalação do WMF 5.0 RTM</span><span class="sxs-lookup"><span data-stu-id="25bad-104">Breaking Change: Certificates used to encrypt/decrypt passwords in DSC configurations may not work after installing WMF 5.0 RTM</span></span>

<span data-ttu-id="25bad-105">Em versões da Preview do WMF 4.0 e 5.0, o DSC não permite que as senhas na configuração tenham um tamanho maior que 121 caracteres.</span><span class="sxs-lookup"><span data-stu-id="25bad-105">In WMF 4.0 and WMF 5.0 Preview releases, DSC would not allow passwords in the configuration to be of length more than 121 characters.</span></span> <span data-ttu-id="25bad-106">O DSC forçava o uso de senhas curtas, mesmo que fosse desejável usar senhas longas e fortes.</span><span class="sxs-lookup"><span data-stu-id="25bad-106">DSC was forcing to use short passwords even if lengthy and strong password was desired.</span></span> <span data-ttu-id="25bad-107">Essa alteração interruptiva permite que as senhas tenham um tamanho arbitrário na configuração DSC.</span><span class="sxs-lookup"><span data-stu-id="25bad-107">This breaking change allows passwords to be of arbitrary length in the DSC configuration.</span></span>

<span data-ttu-id="25bad-108">**Resolução:** crie novamente o certificado com uso da Chave de Codificação de Dados ou de Codificação de Chave, bem como o uso Avançado de Chave de Criptografia de Documento (1.3.6.1.4.1.311.80.1).</span><span class="sxs-lookup"><span data-stu-id="25bad-108">**Resolution:** Re-create the certificate with Data Encipherment or Key Encipherment Key usage, and Document Encryption Enhanced Key usage (1.3.6.1.4.1.311.80.1).</span></span> <span data-ttu-id="25bad-109">Saiba mais em [Protect-CmsMessage](/powershell/module/Microsoft.PowerShell.Security/Protect-CmsMessage).</span><span class="sxs-lookup"><span data-stu-id="25bad-109">For more information, see [Protect-CmsMessage](/powershell/module/Microsoft.PowerShell.Security/Protect-CmsMessage).</span></span>

## <a name="dsc-cmdlets-may-fail-after-installing-wmf-50-rtm"></a><span data-ttu-id="25bad-110">Os cmdlets do DSC poderão falhar após a instalação do WMF 5.0 RTM</span><span class="sxs-lookup"><span data-stu-id="25bad-110">DSC cmdlets may fail after installing WMF 5.0 RTM</span></span>

<span data-ttu-id="25bad-111">Podem ocorrer falhas em `Start-DscConfiguration` e outros cmdlets do DSC após a instalação do WMF 5.0 RTM com o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="25bad-111">`Start-DscConfiguration` and other DSC cmdlets may fail after installing WMF 5.0 RTM with the following error:</span></span>

```Output
LCM failed to retrieve the property PendingJobStep from the object of class dscInternalCache .
+ CategoryInfo : ObjectNotFound: (root/Microsoft/...gurationManager:String) [], CimException
+ FullyQualifiedErrorId : MI RESULT 6
+ PSComputerName : localhost
```

<span data-ttu-id="25bad-112">**Resolução:** exclua DSCEngineCache.mof executando o seguinte comando em uma sessão do PowerShell com privilégios elevados (Executar como Administrador):</span><span class="sxs-lookup"><span data-stu-id="25bad-112">**Resolution:** Delete DSCEngineCache.mof by running the following command in an elevated PowerShell session (Run as Administrator):</span></span>

```powershell
Remove-Item -Path $env:SystemRoot\system32\Configuration\DSCEngineCache.mof
```

## <a name="dsc-cmdlets-may-not-work-if-wmf-50-rtm-is-installed-on-top-of-wmf-50-production-preview"></a><span data-ttu-id="25bad-113">Os cmdlets do DSC poderão não funcionar se o WMF 5.0 RTM estiver instalado, além da Preview de Produção do WMF 5.0</span><span class="sxs-lookup"><span data-stu-id="25bad-113">DSC cmdlets may not work if WMF 5.0 RTM is installed on top of WMF 5.0 Production Preview</span></span>

<span data-ttu-id="25bad-114">**Resolução:** execute o seguinte comando em uma sessão do PowerShell com privilégios elevados (executar como administrador):</span><span class="sxs-lookup"><span data-stu-id="25bad-114">**Resolution:** Run the following command in an elevated PowerShell session (run as administrator):</span></span>

```powershell
mofcomp $env:windir\system32\wbem\DscCoreConfProv.mof
```

## <a name="lcm-can-go-into-an-unstable-state-while-using-get-dscconfiguration-in-debugmode"></a><span data-ttu-id="25bad-115">O LCM pode entrar em um estado instável durante o uso de Get-DscConfiguration em DebugMode</span><span class="sxs-lookup"><span data-stu-id="25bad-115">LCM can go into an unstable state while using Get-DscConfiguration in DebugMode</span></span>

<span data-ttu-id="25bad-116">Se o LCM estiver em DebugMode, pressionar CTRL+C para interromper o processamento de `Get-DscConfiguration` poderá fazer com que o LCM entre em um estado instável, a tal ponto que a maioria dos cmdlets da DSC não funcionará.</span><span class="sxs-lookup"><span data-stu-id="25bad-116">If LCM is in DebugMode, pressing CTRL+C to stop the processing of `Get-DscConfiguration` can cause LCM to go into an unstable state such that majority of DSC cmdlets won't work.</span></span>

<span data-ttu-id="25bad-117">**Resolução:** Não pressione CTRL+C durante a depuração do cmdlet `Get-DscConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="25bad-117">**Resolution:** Don't press CTRL+C while debugging `Get-DscConfiguration` cmdlet.</span></span>

## <a name="stop-dscconfiguration-may-not-respond-in-debugmode"></a><span data-ttu-id="25bad-118">Stop-DscConfiguration poderá não responder em DebugMode</span><span class="sxs-lookup"><span data-stu-id="25bad-118">Stop-DscConfiguration may not respond in DebugMode</span></span>

<span data-ttu-id="25bad-119">Se o LCM estiver em DebugMode, `Stop-DscConfiguration` poderá não responder ao tentar interromper uma operação iniciada por `Get-DscConfiguration`</span><span class="sxs-lookup"><span data-stu-id="25bad-119">If LCM is in DebugMode, `Stop-DscConfiguration` may not respond while trying to stop an operation started by `Get-DscConfiguration`</span></span>

<span data-ttu-id="25bad-120">**Resolução:** conclua a depuração da operação iniciada por `Get-DscConfiguration`, conforme descrito em [Depurando os recursos de DSC](/powershell/scripting/dsc/troubleshooting/debugResource).</span><span class="sxs-lookup"><span data-stu-id="25bad-120">**Resolution:** Finish the debugging of the operation started by `Get-DscConfiguration` as outlined in [Debugging DSC resources](/powershell/scripting/dsc/troubleshooting/debugResource).</span></span>

## <a name="no-verbose-error-messages-are-shown-in-debugmode"></a><span data-ttu-id="25bad-121">Nenhuma mensagem de erro detalhada é mostrada em DebugMode</span><span class="sxs-lookup"><span data-stu-id="25bad-121">No Verbose Error Messages are shown in DebugMode</span></span>

<span data-ttu-id="25bad-122">Se o LCM estiver em **DebugMode** , nenhuma mensagem de erro detalhada será exibida nos recursos de DSC.</span><span class="sxs-lookup"><span data-stu-id="25bad-122">If LCM is in **DebugMode** , no verbose error messages are displayed from DSC Resources.</span></span>

<span data-ttu-id="25bad-123">**Resolução:** desabilite **DebugMode** para ver as mensagens detalhadas no recurso</span><span class="sxs-lookup"><span data-stu-id="25bad-123">**Resolution:** Disable **DebugMode** to see verbose messages from the resource</span></span>

## <a name="invoke-dscresource-operations-cannot-be-retrieved-by-get-dscconfigurationstatus-cmdlet"></a><span data-ttu-id="25bad-124">As operações Invoke-DscResource não podem ser recuperadas pelo cmdlet Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="25bad-124">Invoke-DscResource operations cannot be retrieved by Get-DscConfigurationStatus cmdlet</span></span>

<span data-ttu-id="25bad-125">Depois que o cmdlet `Invoke-DscResource` for usado para chamar diretamente os métodos de um recurso, não será possível recuperar os registros dessa operação por meio de `Get-DscConfigurationStatus`.</span><span class="sxs-lookup"><span data-stu-id="25bad-125">After using `Invoke-DscResource` cmdlet to directly invoke any resource's methods, the records of such operation cannot be retrieved through `Get-DscConfigurationStatus`.</span></span>

<span data-ttu-id="25bad-126">**Resolução:** Nenhum.</span><span class="sxs-lookup"><span data-stu-id="25bad-126">**Resolution:** None.</span></span>

## <a name="get-dscconfigurationstatus-returns-pull-cycle-operations-as-type-consistency"></a><span data-ttu-id="25bad-127">Get-DscConfigurationStatus retorna operações de ciclo de pull como o tipo **Consistência**</span><span class="sxs-lookup"><span data-stu-id="25bad-127">Get-DscConfigurationStatus returns pull cycle operations as type **Consistency**</span></span>

<span data-ttu-id="25bad-128">Quando um nó é definido como o modo de atualização por PULL, para cada operação de pull realizada, o cmdlet `Get-DscConfigurationStatus` relata o tipo de operação como **Consistência** em vez de *Inicial*</span><span class="sxs-lookup"><span data-stu-id="25bad-128">When a node is set to PULL refresh mode, for each pull operation performed, `Get-DscConfigurationStatus` cmdlet reports the operation type as **Consistency** instead of *Initial*</span></span>

<span data-ttu-id="25bad-129">**Resolução:** Nenhum.</span><span class="sxs-lookup"><span data-stu-id="25bad-129">**Resolution:** None.</span></span>

## <a name="invoke-dscresource-cmdlet-does-not-return-message-in-the-order-they-were-produced"></a><span data-ttu-id="25bad-130">O cmdlet Invoke-DscResource não retorna as mensagens na ordem em que foram produzidas</span><span class="sxs-lookup"><span data-stu-id="25bad-130">Invoke-DscResource cmdlet does not return message in the order they were produced</span></span>

<span data-ttu-id="25bad-131">O cmdlet `Invoke-DscResource` não retorna mensagens detalhadas, de aviso nem de erro na ordem em que foram produzidas pelo LCM ou pelo recurso de DSC.</span><span class="sxs-lookup"><span data-stu-id="25bad-131">The `Invoke-DscResource` cmdlet does not return verbose, warning, and error messages in the order they were produced by LCM or the DSC resource.</span></span>

<span data-ttu-id="25bad-132">**Resolução:** Nenhum.</span><span class="sxs-lookup"><span data-stu-id="25bad-132">**Resolution:** None.</span></span>

## <a name="dsc-resources-cannot-be-debugged-easily-when-used-with-invoke-dscresource"></a><span data-ttu-id="25bad-133">Os Recursos DSC não podem ser depurados com facilidade quando usados com Invoke-DscResource</span><span class="sxs-lookup"><span data-stu-id="25bad-133">DSC Resources cannot be debugged easily when used with Invoke-DscResource</span></span>

<span data-ttu-id="25bad-134">Ao executar o LCM no modo de depuração, o cmdlet `Invoke-DscResource` não fornece informações sobre o runspace para se conectar para realizar a depuração.</span><span class="sxs-lookup"><span data-stu-id="25bad-134">When LCM is running in debug mode, `Invoke-DscResource` cmdlet does not give information about runspace to connect to for debugging.</span></span> <span data-ttu-id="25bad-135">Para obter mais informações, veja [Depurando os recursos de DSC](/powershell/scripting/dsc/troubleshooting/debugResource).</span><span class="sxs-lookup"><span data-stu-id="25bad-135">For more information, see [Debugging DSC resources](/powershell/scripting/dsc/troubleshooting/debugResource).</span></span>

<span data-ttu-id="25bad-136">**Resolução:** Descubra e anexe ao runspace usando os cmdlets `Get-PSHostProcessInfo`, `Enter-PSHostProcess` , `Get-Runspace` e `Debug-Runspace` para depurar o recurso de DSC.</span><span class="sxs-lookup"><span data-stu-id="25bad-136">**Resolution:** Discover and attach to the runspace using cmdlets `Get-PSHostProcessInfo`, `Enter-PSHostProcess` , `Get-Runspace` and `Debug-Runspace` to debug the DSC resource.</span></span>

```powershell
# Find all the processes hosting PowerShell
Get-PSHostProcessInfo

ProcessName    ProcessId AppDomainName
-----------    --------- -------------
powershell          3932 DefaultAppDomain
powershell_ise      2304 DefaultAppDomain
WmiPrvSE            3396 DscPsPluginWkr_AppDomain

# Enter the process that is hosting DSC engine (WMI process with DscPsPluginWkr_Appdomain)
Enter-PSHostProcess -Id 3396 -AppDomainName DscPsPluginWkr_AppDomain

# Find all the available rusnspaces in that process
Get-Runspace

Id Name       ComputerName Type  State  Availability
-- ----       ------------ ----  -----  ------------
 2 Runspace2  localhost    Local Opened InBreakpoint
 5 RemoteHost localhost    Local Opened Busy

# Debug the runspace that is in **InBreakpoint** availability state
Debug-Runspace -Id 2
```

## <a name="various-partial-configuration-documents-for-same-node-cannot-have-identical-resource-names"></a><span data-ttu-id="25bad-137">Vários documentos de Configuração Parcial para o mesmo nó não podem ter nomes de recursos idênticos</span><span class="sxs-lookup"><span data-stu-id="25bad-137">Various Partial Configuration documents for same node cannot have identical resource names</span></span>

<span data-ttu-id="25bad-138">Para várias configurações parciais que são implantadas em um único nó, nomes idênticos de recursos causam um erro de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="25bad-138">For several partial configurations that are deployed onto a single node, identical names of resources cause run time error.</span></span>

<span data-ttu-id="25bad-139">**Resolução:** use nomes diferentes até mesmo para os mesmos recursos em configurações parciais diferentes.</span><span class="sxs-lookup"><span data-stu-id="25bad-139">**Resolution:** Use different names for even same resources in different partial configurations.</span></span>

## <a name="start-dscconfiguration-useexisting-does-not-work-with--credential"></a><span data-ttu-id="25bad-140">–UseExisting de Start-DscConfiguration não funciona com –Credential</span><span class="sxs-lookup"><span data-stu-id="25bad-140">Start-DscConfiguration –UseExisting does not work with -Credential</span></span>

<span data-ttu-id="25bad-141">Ao usar `Start-DscConfiguration` com o parâmetro **UseExisting** , o parâmetro **Credential** é ignorado.</span><span class="sxs-lookup"><span data-stu-id="25bad-141">When using `Start-DscConfiguration` with **UseExisting** parameter, the **Credential** parameter is ignored.</span></span> <span data-ttu-id="25bad-142">O DSC usa a identidade de processo padrão para continuar a operação.</span><span class="sxs-lookup"><span data-stu-id="25bad-142">DSC uses default process identity to proceed the operation.</span></span> <span data-ttu-id="25bad-143">Isso causa erros quando uma credencial diferente é necessária para continuar no nó remoto.</span><span class="sxs-lookup"><span data-stu-id="25bad-143">This causes error when a different credential is needed to proceed on remote node.</span></span>

<span data-ttu-id="25bad-144">**Resolução:** use a sessão CIM para operações de DSC remotas:</span><span class="sxs-lookup"><span data-stu-id="25bad-144">**Resolution:** Use CIM session for remote DSC operations:</span></span>

```powershell
$session = New-CimSession -ComputerName $node -Credential $credential
Start-DscConfiguration -UseExisting -CimSession $session
```

## <a name="ipv6-addresses-as-node-names-in-dsc-configurations"></a><span data-ttu-id="25bad-145">Endereços IPv6 como Nomes de Nó em configurações DSC</span><span class="sxs-lookup"><span data-stu-id="25bad-145">IPv6 Addresses as Node Names in DSC configurations</span></span>

<span data-ttu-id="25bad-146">Nesta versão, não há suporte para endereços IPv6 como nomes de nó em scripts de configuração DSC.</span><span class="sxs-lookup"><span data-stu-id="25bad-146">IPv6 addresses as node names in DSC configuration scripts are not supported in this release.</span></span>

<span data-ttu-id="25bad-147">**Resolução:** Nenhum.</span><span class="sxs-lookup"><span data-stu-id="25bad-147">**Resolution:** None.</span></span>

## <a name="debugging-of-class-based-dsc-resources"></a><span data-ttu-id="25bad-148">Depurando os recursos de DSC `Class-Based`</span><span class="sxs-lookup"><span data-stu-id="25bad-148">Debugging of `Class-Based` DSC Resources</span></span>

<span data-ttu-id="25bad-149">Nesta versão, não há suporte para a depuração de recursos DSC baseados em classe.</span><span class="sxs-lookup"><span data-stu-id="25bad-149">Debugging of class-based DSC Resources is not supported in this release.</span></span>

<span data-ttu-id="25bad-150">**Resolução:** Nenhum.</span><span class="sxs-lookup"><span data-stu-id="25bad-150">**Resolution:** None.</span></span>

## <a name="variables-and-functions-defined-in-script-scope-in-dsc-class-based-resource-are-not-preserved-across-multiple-calls-to-a-dsc-resource"></a><span data-ttu-id="25bad-151">As variáveis e funções definidas no escopo de $script no Recurso de DSC Baseado em Classe não são preservadas em várias chamadas para um Recurso de DSC</span><span class="sxs-lookup"><span data-stu-id="25bad-151">Variables and functions defined in $script scope in DSC Class-Based Resource are not preserved across multiple calls to a DSC Resource</span></span>

<span data-ttu-id="25bad-152">Várias chamadas consecutivas para `Start-DSCConfiguration` falharão se a configuração estiver usando qualquer recurso baseado em classe que tenha variáveis ou funções definidas no escopo de `$script`.</span><span class="sxs-lookup"><span data-stu-id="25bad-152">Multiple consecutive calls to `Start-DSCConfiguration` fails if the configuration is using any class-based resource which has variables or functions defined in `$script` scope.</span></span>

<span data-ttu-id="25bad-153">**Resolução:** defina todas as variáveis e funções na própria classe do Recurso DSC.</span><span class="sxs-lookup"><span data-stu-id="25bad-153">**Resolution:** Define all variables and functions in DSC Resource class itself.</span></span> <span data-ttu-id="25bad-154">Nenhuma variável/função do escopo de `$script`.</span><span class="sxs-lookup"><span data-stu-id="25bad-154">No `$script` scope variables/functions.</span></span>

## <a name="dsc-resource-debugging-when-a-resource-is-using-psdscrunascredential"></a><span data-ttu-id="25bad-155">Depuração do Recurso DSC quando um recurso estiver usando PSDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="25bad-155">DSC Resource Debugging when a resource is using PSDscRunAsCredential</span></span>

<span data-ttu-id="25bad-156">Nesta versão, não há suporte para a depuração do Recurso de DSC quando um recurso usa a propriedade **PSDscRunAsCredential** na configuração.</span><span class="sxs-lookup"><span data-stu-id="25bad-156">DSC Resource debugging when a resource is using the **PSDscRunAsCredential** property in the configuration is not supported in this release.</span></span>

<span data-ttu-id="25bad-157">**Resolução:** Nenhum.</span><span class="sxs-lookup"><span data-stu-id="25bad-157">**Resolution:** None.</span></span>

## <a name="psdscrunascredential-is-not-supported-for-dsc-composite-resources"></a><span data-ttu-id="25bad-158">Não há suporte para PsDscRunAsCredential nos recursos de composição DSC</span><span class="sxs-lookup"><span data-stu-id="25bad-158">PsDscRunAsCredential is not supported for DSC Composite Resources</span></span>

<span data-ttu-id="25bad-159">**Resolução:** use a propriedade Credential se estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="25bad-159">**Resolution:** Use Credential property if available.</span></span> <span data-ttu-id="25bad-160">ServiceSet e WindowsFeatureSet de exemplo</span><span class="sxs-lookup"><span data-stu-id="25bad-160">Example ServiceSet and WindowsFeatureSet</span></span>

## <a name="get-dscresource--syntax-does-not-reflect-psdscrunascredential-correctly"></a><span data-ttu-id="25bad-161">Get-DscResource -Syntax não reflete PsDscRunAsCredential corretamente</span><span class="sxs-lookup"><span data-stu-id="25bad-161">Get-DscResource -Syntax does not reflect PsDscRunAsCredential correctly</span></span>

<span data-ttu-id="25bad-162">O parâmetro **Syntax** não reflete **PsDscRunAsCredential** corretamente quando o recurso o marca como obrigatório ou não dá suporte a ele.</span><span class="sxs-lookup"><span data-stu-id="25bad-162">The **Syntax** parameter does not reflect **PsDscRunAsCredential** correctly when resource marks it as mandatory or does not support it.</span></span>

<span data-ttu-id="25bad-163">**Resolução:** Nenhum.</span><span class="sxs-lookup"><span data-stu-id="25bad-163">**Resolution:** None.</span></span> <span data-ttu-id="25bad-164">No entanto, a criação da configuração no ISE reflete metadados corretos sobre a propriedade **PsDscRunAsCredential** ao usar o IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="25bad-164">However, authoring configuration in ISE reflects correct metadata about **PsDscRunAsCredential** property when using IntelliSense.</span></span>

## <a name="windowsoptionalfeature-is-not-available-in-windows-7"></a><span data-ttu-id="25bad-165">WindowsOptionalFeature não está disponível no Windows 7</span><span class="sxs-lookup"><span data-stu-id="25bad-165">WindowsOptionalFeature is not available in Windows 7</span></span>

<span data-ttu-id="25bad-166">O recurso de DSC **WindowsOptionalFeature** não está disponível no Windows 7.</span><span class="sxs-lookup"><span data-stu-id="25bad-166">The **WindowsOptionalFeature** DSC resource is not available in Windows 7.</span></span> <span data-ttu-id="25bad-167">Este recurso exige o módulo DISM e os cmdlets do DISM que estão disponíveis começando do Windows 8 e versões mais recentes do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="25bad-167">This resource requires the DISM module, and DISM cmdlets that are available starting in Windows 8 and newer releases of the Windows operating system.</span></span>

## <a name="for-class-based-dsc-resources-import-dscresource--moduleversion-may-not-work-as-expected"></a><span data-ttu-id="25bad-168">Para obter recursos de DSC baseados em classes, Import-DscResource -ModuleVersion pode não funcionar como esperado</span><span class="sxs-lookup"><span data-stu-id="25bad-168">For Class-based DSC resources, Import-DscResource -ModuleVersion may not work as expected</span></span>

<span data-ttu-id="25bad-169">Se o nó compilação tiver várias versões de um módulo de recurso de DSC baseado em classes, `Import-DscResource -ModuleVersion` não selecionará a versão especificada e isso levará ao seguinte erro de compilação.</span><span class="sxs-lookup"><span data-stu-id="25bad-169">If the compilation node has multiple versions of a class-based DSC resource module, `Import-DscResource -ModuleVersion` does not pick the specified version and results in following compilation error.</span></span>

```Output
ImportClassResourcesFromModule : Exception calling "ImportClassResourcesFromModule" with "3" argument(s):
 "Keyword 'MyTestResource' already defined in the configuration."
At C:\Windows\system32\WindowsPowerShell\v1.0\Modules\PSDesiredStateConfiguration\PSDesiredStateConfiguration.psm1:2035 char:35
+ ... rcesFound = ImportClassResourcesFromModule -Module $mod -Resources $r ...
+                 ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [ImportClassResourcesFromModule], MethodInvocationException
    + FullyQualifiedErrorId : PSInvalidOperationException,ImportClassResourcesFromModule
```

<span data-ttu-id="25bad-170">**Resolução:** importe a versão necessária definindo o objeto **ModuleSpecification** para o parâmetro **ModuleName** com a chave **RequiredVersion** especificada da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="25bad-170">**Resolution:** Import the required version by defining the **ModuleSpecification** object to the **ModuleName** parameter with **RequiredVersion** key specified as follows:</span></span>

```powershell
Import-DscResource -ModuleName @{ModuleName='MyModuleName';RequiredVersion='1.2'}
```

## <a name="some-dsc-resources-like-registry-resource-may-start-to-take-a-long-time-to-process-the-request"></a><span data-ttu-id="25bad-171">Alguns recursos DSC, como recursos de Registro podem começar a levar muito tempo para processar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="25bad-171">Some DSC resources like registry resource may start to take a long time to process the request.</span></span>

<span data-ttu-id="25bad-172">**Resolução 1:** crie uma tarefa agendada que limpa periodicamente a pasta a seguir.</span><span class="sxs-lookup"><span data-stu-id="25bad-172">**Resolution 1:** Create a schedule task that cleans up the following folder periodically.</span></span>

```powershell
$env:windir\system32\config\systemprofile\AppData\Local\Microsoft\Windows\PowerShell\CommandAnalysis
```

<span data-ttu-id="25bad-173">**Resolução 2:** altere a configuração de DSC para limpar a pasta *CommandAnalysis* no final da configuração.</span><span class="sxs-lookup"><span data-stu-id="25bad-173">**Resolution 2:** Change the DSC configuration to clean up the *CommandAnalysis* folder at the end of the configuration.</span></span>

```powershell
Configuration $configName
{

   # User Data
    Registry SetRegisteredOwner
    {
        Ensure = 'Present'
        Force = $True
        Key = $Node.RegisteredKey
        ValueName = $Node.RegisteredOwnerValue
        ValueType = 'String'
        ValueData = $Node.RegisteredOwnerData
    }
    #
    # Script to delete the config
    #
    script DeleteCommandAnalysisCache
    {
        DependsOn = "[Registry]SetRegisteredOwner"
        getscript = "@{}"
        testscript = 'Remove-Item -Path $env:windir\system32\config\systemprofile\AppData\Local\Microsoft\Windows\PowerShell\CommandAnalysis -Force -Recurse -ErrorAction SilentlyContinue -ErrorVariable ev | out-null;$true'
        setscript = '$true'
    }
}
```
