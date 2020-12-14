---
ms.date: 02/03/2020
keywords: powershell,core
title: Alterações da falha no PowerShell Core 6.0
description: Este artigo resume as diferenças entre o Windows PowerShell 5.1 e o PowerShell 6.0.
ms.openlocfilehash: b53365ee72e6a6e85faa56125a8aa7961d3ecc7f
ms.sourcegitcommit: f9d855dd73b916559a22e337672dea3fbb11c634
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/07/2020
ms.locfileid: "96833741"
---
# <a name="breaking-changes-for-powershell-6x"></a><span data-ttu-id="09447-104">Alterações da falha no PowerShell 6.x</span><span class="sxs-lookup"><span data-stu-id="09447-104">Breaking Changes for PowerShell 6.x</span></span>

## <a name="features-no-longer-available-in-powershell-core"></a><span data-ttu-id="09447-105">Recursos não mais disponíveis no PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="09447-105">Features no longer available in PowerShell Core</span></span>

### <a name="modules-not-shipped-for-powershell-6x"></a><span data-ttu-id="09447-106">Módulos não enviados para o PowerShell 6.x</span><span class="sxs-lookup"><span data-stu-id="09447-106">Modules not shipped for PowerShell 6.x</span></span>

<span data-ttu-id="09447-107">Por vários motivos de compatibilidade, os seguintes módulos não estão incluídos no PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="09447-107">For various compatibility reasons, the following modules are not included in PowerShell 6.</span></span>

- <span data-ttu-id="09447-108">ISE</span><span class="sxs-lookup"><span data-stu-id="09447-108">ISE</span></span>
- <span data-ttu-id="09447-109">Microsoft.PowerShell.LocalAccounts</span><span class="sxs-lookup"><span data-stu-id="09447-109">Microsoft.PowerShell.LocalAccounts</span></span>
- <span data-ttu-id="09447-110">Microsoft.PowerShell.ODataUtils</span><span class="sxs-lookup"><span data-stu-id="09447-110">Microsoft.PowerShell.ODataUtils</span></span>
- <span data-ttu-id="09447-111">Microsoft.PowerShell.Operation.Validation</span><span class="sxs-lookup"><span data-stu-id="09447-111">Microsoft.PowerShell.Operation.Validation</span></span>
- <span data-ttu-id="09447-112">PSScheduledJob</span><span class="sxs-lookup"><span data-stu-id="09447-112">PSScheduledJob</span></span>
- <span data-ttu-id="09447-113">PSWorkflow</span><span class="sxs-lookup"><span data-stu-id="09447-113">PSWorkflow</span></span>
- <span data-ttu-id="09447-114">PSWorkflowUtility</span><span class="sxs-lookup"><span data-stu-id="09447-114">PSWorkflowUtility</span></span>

### <a name="powershell-workflow"></a><span data-ttu-id="09447-115">Fluxo de trabalho do PowerShell</span><span class="sxs-lookup"><span data-stu-id="09447-115">PowerShell Workflow</span></span>

<span data-ttu-id="09447-116">[Fluxo de Trabalho do PowerShell][workflow] é um recurso no Windows PowerShell baseado no [Windows Workflow Foundation (WF)][workflow-foundation] que permite a criação de runbooks robustos para tarefas em paralelo ou de longa duração.</span><span class="sxs-lookup"><span data-stu-id="09447-116">[PowerShell Workflow][workflow] is a feature in Windows PowerShell that builds on top of [Windows Workflow Foundation (WF)][workflow-foundation] that enables the creation of robust runbooks for long-running or parallelized tasks.</span></span>

<span data-ttu-id="09447-117">Devido à falta de suporte a Windows Workflow Foundation no .NET Core, não damos suporte ao Fluxo de Trabalho do PowerShell no PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="09447-117">Due to the lack of support for Windows Workflow Foundation in .NET Core, we are not supporting PowerShell Workflow in PowerShell Core.</span></span>

<span data-ttu-id="09447-118">Futuramente, gostaríamos de habilitar o paralelismo/simultaneidade nativa na linguagem do PowerShell sem a necessidade do Fluxo de Trabalho do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09447-118">In the future, we would like to enable native parallelism/concurrency in the PowerShell language without the need for PowerShell Workflow.</span></span>

<span data-ttu-id="09447-119">Se houver a necessidade de usar pontos de verificação para retomar um script após a reinicialização do sistema operacional, recomendamos o uso de Agendador de Tarefas para executar um script na inicialização do sistema, mas o script precisaria manter o próprio estado (como mantê-lo em um arquivo).</span><span class="sxs-lookup"><span data-stu-id="09447-119">If there is a need to use checkpoints to resume a script after the OS restarts, we recommend using Task Scheduler to run a script on OS startup, but the script would need to maintain its own state (like persisting it to a file).</span></span>

[workflow]: /previous-versions/powershell/scripting/components/workflows-guide
[workflow-foundation]: /dotnet/framework/windows-workflow-foundation/

### <a name="custom-snap-ins"></a><span data-ttu-id="09447-120">Snap-ins personalizados</span><span class="sxs-lookup"><span data-stu-id="09447-120">Custom snap-ins</span></span>

<span data-ttu-id="09447-121">[Snap-ins do PowerShell][snapin] são um predecessor dos módulos do PowerShell que não têm ampla adoção da comunidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09447-121">[PowerShell snap-ins][snapin] are a predecessor to PowerShell modules that do not have widespread adoption in the PowerShell community.</span></span>

<span data-ttu-id="09447-122">Devido à complexidade do suporte aos snap-ins e à falta de uso da comunidade, não oferecemos mais suporte a snap-ins personalizados no PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="09447-122">Due to the complexity of supporting snap-ins and their lack of usage in the community, we no longer support custom snap-ins in PowerShell Core.</span></span>

<span data-ttu-id="09447-123">Hoje, isso causa a falha dos módulos `ActiveDirectory` e `DnsClient` no Windows e no Windows Server.</span><span class="sxs-lookup"><span data-stu-id="09447-123">Today, this breaks the `ActiveDirectory` and `DnsClient` modules in Windows and Windows Server.</span></span>

[snapin]: /powershell/module/microsoft.powershell.core/about/about_pssnapins

### <a name="wmi-v1-cmdlets"></a><span data-ttu-id="09447-124">Cmdlets do WMI v1</span><span class="sxs-lookup"><span data-stu-id="09447-124">WMI v1 cmdlets</span></span>

<span data-ttu-id="09447-125">Devido à complexidade do suporte a dois conjuntos de módulos baseados em WMI, removemos os cmdlets WMI v1 do PowerShell Core:</span><span class="sxs-lookup"><span data-stu-id="09447-125">Due to the complexity of supporting two sets of WMI-based modules, we removed the WMI v1 cmdlets from PowerShell Core:</span></span>

- `Register-WmiEvent`
- `Set-WmiInstance`
- `Invoke-WmiMethod`
- `Get-WmiObject`
- `Remove-WmiObject`

<span data-ttu-id="09447-126">Em vez disso, recomendamos que você use os cmdlets do CIM (também conhecidos como WMI v2), que fornecem a mesma funcionalidade e uma sintaxe reprojetada:</span><span class="sxs-lookup"><span data-stu-id="09447-126">Instead, we recommend that you the use the CIM (aka WMI v2) cmdlets which provide the same functionality with new functionality and a redesigned syntax:</span></span>

- `Get-CimAssociatedInstance`
- `Get-CimClass`
- `Get-CimInstance`
- `Get-CimSession`
- `Invoke-CimMethod`
- `New-CimInstance`
- `New-CimSession`
- `New-CimSessionOption`
- `Register-CimIndicationEvent`
- `Remove-CimInstance`
- `Remove-CimSession`
- `Set-CimInstance`

### <a name="microsoftpowershelllocalaccounts"></a><span data-ttu-id="09447-127">Microsoft.PowerShell.LocalAccounts</span><span class="sxs-lookup"><span data-stu-id="09447-127">Microsoft.PowerShell.LocalAccounts</span></span>

<span data-ttu-id="09447-128">Devido ao uso de APIs sem suporte, removemos `Microsoft.PowerShell.LocalAccounts` do PowerShell Core até encontrarmos uma solução melhor.</span><span class="sxs-lookup"><span data-stu-id="09447-128">Due to the use of unsupported APIs, `Microsoft.PowerShell.LocalAccounts` has been removed from PowerShell Core until a better solution is found.</span></span>

### <a name="new-webserviceproxy-cmdlet-removed"></a><span data-ttu-id="09447-129">cmdlet `New-WebServiceProxy` removido</span><span class="sxs-lookup"><span data-stu-id="09447-129">`New-WebServiceProxy` cmdlet removed</span></span>

<span data-ttu-id="09447-130">O .NET Core não dá suporte ao Windows Communication Framework, que fornece serviços para o uso do protocolo SOAP.</span><span class="sxs-lookup"><span data-stu-id="09447-130">.NET Core does not support the Windows Communication Framework, which provide services for using the SOAP protocol.</span></span> <span data-ttu-id="09447-131">Esse cmdlet foi removido porque requer o SOAP.</span><span class="sxs-lookup"><span data-stu-id="09447-131">This cmdlet was removed because it requires SOAP.</span></span>

### <a name="-transaction-cmdlets-removed"></a><span data-ttu-id="09447-132">Cmdlets `*-Transaction` removidos</span><span class="sxs-lookup"><span data-stu-id="09447-132">`*-Transaction` cmdlets removed</span></span>

<span data-ttu-id="09447-133">Esses cmdlets tinham uso muito limitado.</span><span class="sxs-lookup"><span data-stu-id="09447-133">These cmdlets had very limited usage.</span></span> <span data-ttu-id="09447-134">A decisão foi tomada para descontinuar o suporte para eles.</span><span class="sxs-lookup"><span data-stu-id="09447-134">The decision was made to discontinue support for them.</span></span>

- `Complete-Transaction`
- `Get-Transaction`
- `Start-Transaction`
- `Undo-Transaction`
- `Use-Transaction`

### <a name="security-cmdlets-not-available-on-non-windows-platforms"></a><span data-ttu-id="09447-135">Cmdlets de segurança não disponíveis em plataformas não Windows</span><span class="sxs-lookup"><span data-stu-id="09447-135">Security cmdlets not available on non-Windows platforms</span></span>

- `Get-Acl`
- `Set-Acl`
- `Get-AuthenticodeSignature`
- `Set-AuthenticodeSignature`
- `Get-CmsMessage`
- `Protect-CmsMessage`
- `Unprotect-CmsMessage`
- `New-FileCatalog`
- `Test-FileCatalog`

### <a name="-computerand-other-windows-specific-cmdlets"></a><span data-ttu-id="09447-136">`*-Computer`e outros cmdlets específicos do Windows</span><span class="sxs-lookup"><span data-stu-id="09447-136">`*-Computer`and other Windows-specific cmdlets</span></span>

<span data-ttu-id="09447-137">Devido ao uso de APIs sem suporte, os seguintes cmdlets foram removidos do PowerShell Core até encontrarmos uma solução melhor.</span><span class="sxs-lookup"><span data-stu-id="09447-137">Due to the use of unsupported APIs, the following cmdlets have been removed from PowerShell Core until a better solution is found.</span></span>

- `Get-Clipboard`
- `Set-Clipboard`
- `Add-Computer`
- `Checkpoint-Computer`
- `Remove-Computer`
- `Restore-Computer`
- `Reset-ComputerMachinePassword`
- `Disable-ComputerRestore`
- `Enable-ComputerRestore`
- `Get-ComputerRestorePoint`
- `Test-ComputerSecureChannel`
- `Get-ControlPanelItem`
- `Show-ControlPanelItem`
- `Get-HotFix`
- `Clear-RecycleBin`
- `Update-List`
- `Out-Printer`
- `ConvertFrom-String`
- `Convert-String`

### <a name="-counter-cmdlets"></a><span data-ttu-id="09447-138">Cmdlets de `*-Counter`</span><span class="sxs-lookup"><span data-stu-id="09447-138">`*-Counter` cmdlets</span></span>

<span data-ttu-id="09447-139">Devido ao uso de APIs sem suporte, removemos `*-Counter` do PowerShell Core até encontrarmos uma solução melhor.</span><span class="sxs-lookup"><span data-stu-id="09447-139">Due to the use of unsupported APIs, the `*-Counter` has been removed from PowerShell Core until a better solution is found.</span></span>

### <a name="-eventlog-cmdlets"></a><span data-ttu-id="09447-140">Cmdlets de `*-EventLog`</span><span class="sxs-lookup"><span data-stu-id="09447-140">`*-EventLog` cmdlets</span></span>

<span data-ttu-id="09447-141">Devido ao uso de APIs sem suporte, `*-EventLog` foi removido do PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="09447-141">Due to the use of unsupported APIs, the `*-EventLog` has been removed from PowerShell Core.</span></span> <span data-ttu-id="09447-142">até encontrarmos uma solução melhor.</span><span class="sxs-lookup"><span data-stu-id="09447-142">until a better solution is found.</span></span> <span data-ttu-id="09447-143">`Get-WinEvent` e `New-WinEvent` estão disponíveis para obter e criar eventos no Windows.</span><span class="sxs-lookup"><span data-stu-id="09447-143">`Get-WinEvent` and `New-WinEvent` are available to get and create events on Windows.</span></span>

### <a name="cmdlets-that-use-wpf-removed"></a><span data-ttu-id="09447-144">Cmdlets que usam WPF removidos</span><span class="sxs-lookup"><span data-stu-id="09447-144">Cmdlets that use WPF removed</span></span>

<span data-ttu-id="09447-145">Não há suporte para o Windows Presentation Framework no CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="09447-145">The Windows Presentation Framework is not supported on CoreCLR.</span></span> <span data-ttu-id="09447-146">Os seguintes cmdlets foram afetados:</span><span class="sxs-lookup"><span data-stu-id="09447-146">The following cmdlets are affected:</span></span>

- `Show-Command`
- `Out-GridView`
- <span data-ttu-id="09447-147">O parâmetro **showwindow** de `Get-Help`</span><span class="sxs-lookup"><span data-stu-id="09447-147">The **showwindow** parameter of `Get-Help`</span></span>

### <a name="some-dsc-cmdlets-removed"></a><span data-ttu-id="09447-148">Alguns cmdlets DSC removidos</span><span class="sxs-lookup"><span data-stu-id="09447-148">Some DSC cmdlets removed</span></span>

- `Get-DscConfiguration`
- `Publish-DscConfiguration`
- `Restore-DscConfiguration`
- `Start-DscConfiguration`
- `Stop-DscConfiguration`
- `Test-DscConfiguration`
- `Update-DscConfiguration`
- `Remove-DscConfigurationDocument`
- `Get-DscConfigurationStatus`
- `Disable-DscDebug`
- `Enable-DscDebug`
- `Get-DscLocalConfigurationManager`
- `Set-DscLocalConfigurationManager`
- `Invoke-DscResource`

## <a name="enginelanguage-changes"></a><span data-ttu-id="09447-149">Alterações de mecanismo/linguagem</span><span class="sxs-lookup"><span data-stu-id="09447-149">Engine/language changes</span></span>

### <a name="rename-powershellexe-to-pwshexe-5101"></a><span data-ttu-id="09447-150">`powershell.exe` renomeado para `pwsh.exe` [#5101](https://github.com/PowerShell/PowerShell/issues/5101)</span><span class="sxs-lookup"><span data-stu-id="09447-150">Rename `powershell.exe` to `pwsh.exe` [#5101](https://github.com/PowerShell/PowerShell/issues/5101)</span></span>

<span data-ttu-id="09447-151">Para dar aos usuários uma maneira determinística de chamar o PowerShell Core no Windows (e não no Windows PowerShell), o binário do PowerShell Core foi alterado para `pwsh.exe` no Windows e para `pwsh` em outras plataformas.</span><span class="sxs-lookup"><span data-stu-id="09447-151">In order to give users a deterministic way to call PowerShell Core on Windows (as opposed to Windows PowerShell), the PowerShell Core binary was changed to `pwsh.exe` on Windows and `pwsh` on non-Windows platforms.</span></span>

<span data-ttu-id="09447-152">O nome abreviado também é consistente com a nomenclatura dos shells em plataformas não Windows.</span><span class="sxs-lookup"><span data-stu-id="09447-152">The shortened name is also consistent with naming of shells on non-Windows platforms.</span></span>

### <a name="dont-insert-line-breaks-to-output-except-for-tables-5193"></a><span data-ttu-id="09447-153">Não insira quebras de linha na saída (exceto para tabelas) [#5193](https://github.com/PowerShell/PowerShell/issues/5193)</span><span class="sxs-lookup"><span data-stu-id="09447-153">Don't insert line breaks to output (except for tables) [#5193](https://github.com/PowerShell/PowerShell/issues/5193)</span></span>

<span data-ttu-id="09447-154">Antes, a saída era alinhada à largura do console, e quebras de linha eram adicionadas à largura final do console, ou seja, a saída não era reformatada conforme o esperado se o terminal não fosse redimensionado.</span><span class="sxs-lookup"><span data-stu-id="09447-154">Previously, output was aligned to the width of the console and line breaks were added at the end width of the console, meaning the output didn't get reformatted as expected if the terminal was resized.</span></span> <span data-ttu-id="09447-155">Essa alteração não foi aplicada às tabelas, pois elas precisam das quebras de linha para manter as colunas alinhadas.</span><span class="sxs-lookup"><span data-stu-id="09447-155">This change was not applied to tables, as the line breaks are necessary to keep the columns aligned.</span></span>

### <a name="skip-null-element-check-for-collections-with-a-value-type-element-type-5432"></a><span data-ttu-id="09447-156">Ignore a verificação de elemento nulo para coleções com um tipo de elemento de tipo de valor [#5432](https://github.com/PowerShell/PowerShell/issues/5432)</span><span class="sxs-lookup"><span data-stu-id="09447-156">Skip null-element check for collections with a value-type element type [#5432](https://github.com/PowerShell/PowerShell/issues/5432)</span></span>

<span data-ttu-id="09447-157">Para o parâmetro `Mandatory` e os atributos `ValidateNotNull` e `ValidateNotNullOrEmpty`, ignore a verificação de elemento nulo se o tipo de elemento da coleção for um tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="09447-157">For the `Mandatory` parameter and `ValidateNotNull` and `ValidateNotNullOrEmpty` attributes, skip the null-element check if the collection's element type is value type.</span></span>

### <a name="change-outputencoding-to-use-utf-8-nobom-encoding-rather-than-ascii-5369"></a><span data-ttu-id="09447-158">Altere o `$OutputEncoding` para usar codificação `UTF-8 NoBOM` em vez de ASCII [#5369](https://github.com/PowerShell/PowerShell/issues/5369)</span><span class="sxs-lookup"><span data-stu-id="09447-158">Change `$OutputEncoding` to use `UTF-8 NoBOM` encoding rather than ASCII [#5369](https://github.com/PowerShell/PowerShell/issues/5369)</span></span>

<span data-ttu-id="09447-159">A codificação anterior, ASCII (7 bits), resultaria em alteração incorreta da saída em alguns casos.</span><span class="sxs-lookup"><span data-stu-id="09447-159">The previous encoding, ASCII (7-bit), would result in incorrect alteration of the output in some cases.</span></span> <span data-ttu-id="09447-160">Essa alteração é para tornar o `UTF-8 NoBOM` padrão, o que preserva a saída Unicode com uma codificação com suporte da maioria das ferramentas e sistemas operacionais.</span><span class="sxs-lookup"><span data-stu-id="09447-160">This change is to make `UTF-8 NoBOM` default, which preserves Unicode output with an encoding supported by most tools and operating systems.</span></span>

### <a name="remove-allscope-from-most-default-aliases-5268"></a><span data-ttu-id="09447-161">Remoção de `AllScope` da maioria dos aliases padrão [#5268](https://github.com/PowerShell/PowerShell/issues/5268)</span><span class="sxs-lookup"><span data-stu-id="09447-161">Remove `AllScope` from most default aliases [#5268](https://github.com/PowerShell/PowerShell/issues/5268)</span></span>

<span data-ttu-id="09447-162">Para acelerar a criação de escopo, `AllScope` foi removido da maioria dos aliases padrão.</span><span class="sxs-lookup"><span data-stu-id="09447-162">To speed up scope creation, `AllScope` was removed from most default aliases.</span></span> <span data-ttu-id="09447-163">`AllScope` foi deixado por alguns aliases usados com frequência nos quais a pesquisa foi mais rápida.</span><span class="sxs-lookup"><span data-stu-id="09447-163">`AllScope` was left for a few frequently used aliases where the lookup was faster.</span></span>

### <a name="-verbose-and--debug-no-longer-overrides-erroractionpreference-5113"></a><span data-ttu-id="09447-164">`-Verbose` e `-Debug` já não substituem `$ErrorActionPreference` [#5113](https://github.com/PowerShell/PowerShell/issues/5113)</span><span class="sxs-lookup"><span data-stu-id="09447-164">`-Verbose` and `-Debug` no longer overrides `$ErrorActionPreference` [#5113](https://github.com/PowerShell/PowerShell/issues/5113)</span></span>

<span data-ttu-id="09447-165">Antes, se `-Verbose` ou `-Debug` fosse especificado, substituiria o comportamento de `$ErrorActionPreference`.</span><span class="sxs-lookup"><span data-stu-id="09447-165">Previously, if `-Verbose` or `-Debug` were specified, it overrode the behavior of `$ErrorActionPreference`.</span></span> <span data-ttu-id="09447-166">Com essa alteração, `-Verbose` e `-Debug` não afetam mais o comportamento de `$ErrorActionPreference`.</span><span class="sxs-lookup"><span data-stu-id="09447-166">With this change, `-Verbose` and `-Debug` no longer affect the behavior of `$ErrorActionPreference`.</span></span>

## <a name="cmdlet-changes"></a><span data-ttu-id="09447-167">Alterações de cmdlet</span><span class="sxs-lookup"><span data-stu-id="09447-167">Cmdlet changes</span></span>

### <a name="invoke-restmethod-doesnt-return-useful-info-when-no-data-is-returned-5320"></a><span data-ttu-id="09447-168">Invoke-RestMethod não retorna informações úteis quando nenhum dado retorna.</span><span class="sxs-lookup"><span data-stu-id="09447-168">Invoke-RestMethod doesn't return useful info when no data is returned.</span></span> [<span data-ttu-id="09447-169">#5320</span><span class="sxs-lookup"><span data-stu-id="09447-169">#5320</span></span>](https://github.com/PowerShell/PowerShell/issues/5320)

<span data-ttu-id="09447-170">Quando uma API retorna apenas `null`, Invoke-RestMethod serializava isso como a cadeia de caracteres `"null"` em vez de `$null`.</span><span class="sxs-lookup"><span data-stu-id="09447-170">When an API returns just `null`, Invoke-RestMethod was serializing this as the string `"null"` instead of `$null`.</span></span> <span data-ttu-id="09447-171">Essa alteração corrige a lógica em `Invoke-RestMethod` para serializar apropriadamente um JSON `null` literal de valor único como `$null`.</span><span class="sxs-lookup"><span data-stu-id="09447-171">This change fixes the logic in `Invoke-RestMethod` to properly serialize a valid single value JSON `null` literal as `$null`.</span></span>

### <a name="remove--protocol-from--computer-cmdlets-5277"></a><span data-ttu-id="09447-172">Remoção de `-Protocol` dos cmdlets `*-Computer`[#5277](https://github.com/PowerShell/PowerShell/issues/5277)</span><span class="sxs-lookup"><span data-stu-id="09447-172">Remove `-Protocol` from `*-Computer` cmdlets [#5277](https://github.com/PowerShell/PowerShell/issues/5277)</span></span>

<span data-ttu-id="09447-173">Devido a problemas com a comunicação remota do RPC no CoreFX (principalmente em plataformas diferentes do Windows), e para garantir uma experiência de comunicação remota consistente no PowerShell, o parâmetro `-Protocol` foi removido dos cmdlets `\*-Computer`.</span><span class="sxs-lookup"><span data-stu-id="09447-173">Due to issues with RPC remoting in CoreFX (particularly on non-Windows platforms) and ensuring a consistent remoting experience in PowerShell, the `-Protocol` parameter was removed from the `\*-Computer` cmdlets.</span></span> <span data-ttu-id="09447-174">O DCOM não é compatível na comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="09447-174">DCOM is no longer supported for remoting.</span></span> <span data-ttu-id="09447-175">Os seguintes cmdlets só dão suporte à comunicação remota do WSMAN:</span><span class="sxs-lookup"><span data-stu-id="09447-175">The following cmdlets only support WSMAN remoting:</span></span>

- <span data-ttu-id="09447-176">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="09447-176">Rename-Computer</span></span>
- <span data-ttu-id="09447-177">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="09447-177">Restart-Computer</span></span>
- <span data-ttu-id="09447-178">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="09447-178">Stop-Computer</span></span>

### <a name="remove--computername-from--service-cmdlets-5090"></a><span data-ttu-id="09447-179">Remoção de `-ComputerName` dos cmdlets `*-Service`[#5090](https://github.com/PowerShell/PowerShell/issues/5094)</span><span class="sxs-lookup"><span data-stu-id="09447-179">Remove `-ComputerName` from `*-Service` cmdlets [#5090](https://github.com/PowerShell/PowerShell/issues/5094)</span></span>

<span data-ttu-id="09447-180">Para incentivar a consistência no uso de PSRP, o parâmetro `-ComputerName` foi removido dos cmdlets `*-Service`.</span><span class="sxs-lookup"><span data-stu-id="09447-180">In order to encourage the consistent use of PSRP, the `-ComputerName` parameter was removed from `*-Service` cmdlets.</span></span>

### <a name="fix-get-item--literalpath-ab-if-ab-doesnt-actually-exist-to-return-error-5197"></a><span data-ttu-id="09447-181">Correção de `Get-Item -LiteralPath a*b` se `a*b` não existir, a fim de retornar um erro [#5197](https://github.com/PowerShell/PowerShell/issues/5197)</span><span class="sxs-lookup"><span data-stu-id="09447-181">Fix `Get-Item -LiteralPath a*b` if `a*b` doesn't actually exist to return error [#5197](https://github.com/PowerShell/PowerShell/issues/5197)</span></span>

<span data-ttu-id="09447-182">Antes, se `-LiteralPath` recebesse um caractere curinga, o trataria da mesma forma que `-Path`, e se o caractere curinga não encontrasse arquivos, sairia silenciosamente.</span><span class="sxs-lookup"><span data-stu-id="09447-182">Previously, `-LiteralPath` given a wildcard would treat it the same as `-Path` and if the wildcard found no files, it would silently exit.</span></span> <span data-ttu-id="09447-183">O comportamento correto deveria ser um `-LiteralPath` literal, para que se o arquivo não existir, ele cause um erro.</span><span class="sxs-lookup"><span data-stu-id="09447-183">Correct behavior should be that `-LiteralPath` is literal so if the file doesn't exist, it should error.</span></span> <span data-ttu-id="09447-184">A mudança é tratar os curingas usados com `-Literal` como literal.</span><span class="sxs-lookup"><span data-stu-id="09447-184">Change is to treat wildcards used with `-Literal` as literal.</span></span>

### <a name="import-csv-should-apply-pstypenames-upon-import-when-type-information-is-present-in-the-csv-5134"></a><span data-ttu-id="09447-185">`Import-Csv` deve aplicar `PSTypeNames` na importação quando houver informações de tipo no CSV [#5134](https://github.com/PowerShell/PowerShell/issues/5134)</span><span class="sxs-lookup"><span data-stu-id="09447-185">`Import-Csv` should apply `PSTypeNames` upon import when type information is present in the CSV [#5134](https://github.com/PowerShell/PowerShell/issues/5134)</span></span>

<span data-ttu-id="09447-186">Antes, os objetos exportados usando `Export-CSV` com `TypeInformation` importado com `ConvertFrom-Csv` não estavam retendo as informações de tipo.</span><span class="sxs-lookup"><span data-stu-id="09447-186">Previously, objects exported using `Export-CSV` with `TypeInformation` imported with `ConvertFrom-Csv` were not retaining the type information.</span></span> <span data-ttu-id="09447-187">Esta mudança adiciona as informações de tipo ao membro `PSTypeNames`, se estiverem disponíveis no arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="09447-187">This change adds the type information to `PSTypeNames` member if available from the CSV file.</span></span>

### <a name="-notypeinformation-should-be-default-on-export-csv-5131"></a><span data-ttu-id="09447-188">`-NoTypeInformation` deve ser o padrão em `Export-Csv` [#5131](https://github.com/PowerShell/PowerShell/issues/5131)</span><span class="sxs-lookup"><span data-stu-id="09447-188">`-NoTypeInformation` should be default on `Export-Csv` [#5131](https://github.com/PowerShell/PowerShell/issues/5131)</span></span>

<span data-ttu-id="09447-189">Essa alteração foi feita para atender aos comentários de clientes sobre o comportamento padrão de inclusão de informações de tipo no `Export-CSV`.</span><span class="sxs-lookup"><span data-stu-id="09447-189">This change was made to address customer feedback on the default behavior of `Export-CSV` to include type information.</span></span>

<span data-ttu-id="09447-190">Antes, o cmdlet geraria um comentário na primeira linha contendo o nome do tipo do objeto.</span><span class="sxs-lookup"><span data-stu-id="09447-190">Previously, the cmdlet would output a comment as the first line containing the type name of the object.</span></span> <span data-ttu-id="09447-191">A alteração serve para suprimir isso por padrão, pois é algo que não é compreendido pela maioria das ferramentas.</span><span class="sxs-lookup"><span data-stu-id="09447-191">The change is to suppress this by default as it's not understood by most tools.</span></span> <span data-ttu-id="09447-192">Use `-IncludeTypeInformation` para reter o comportamento anterior.</span><span class="sxs-lookup"><span data-stu-id="09447-192">Use `-IncludeTypeInformation` to retain the previous behavior.</span></span>

### <a name="web-cmdlets-should-warn-when--credential-is-sent-over-unencrypted-connections-5112"></a><span data-ttu-id="09447-193">Os cmdlets da Web devem avisar quando `-Credential` for enviado por conexões não criptografadas [#5112](https://github.com/PowerShell/PowerShell/issues/5112)</span><span class="sxs-lookup"><span data-stu-id="09447-193">Web Cmdlets should warn when `-Credential` is sent over unencrypted connections [#5112](https://github.com/PowerShell/PowerShell/issues/5112)</span></span>

<span data-ttu-id="09447-194">Ao usar HTTP, todo conteúdo, incluindo senhas, é enviado como texto não criptografado.</span><span class="sxs-lookup"><span data-stu-id="09447-194">When using HTTP, content including passwords are sent as clear-text.</span></span> <span data-ttu-id="09447-195">Essa alteração serve para não permitir isso por padrão, e retornar um erro se as credenciais estiverem sendo passadas de maneira insegura.</span><span class="sxs-lookup"><span data-stu-id="09447-195">This change is to not allow this by default and return an error if credentials are being passed in an insecure manner.</span></span> <span data-ttu-id="09447-196">Os usuários podem ignorar isso usando a opção `-AllowUnencryptedAuthentication`.</span><span class="sxs-lookup"><span data-stu-id="09447-196">Users can bypass this by using the `-AllowUnencryptedAuthentication` switch.</span></span>

## <a name="api-changes"></a><span data-ttu-id="09447-197">Alterações de API</span><span class="sxs-lookup"><span data-stu-id="09447-197">API changes</span></span>

### <a name="remove-addtypecommandbase-class-5407"></a><span data-ttu-id="09447-198">Remoção da classe `AddTypeCommandBase`[#5407](https://github.com/PowerShell/PowerShell/issues/5407)</span><span class="sxs-lookup"><span data-stu-id="09447-198">Remove `AddTypeCommandBase` class [#5407](https://github.com/PowerShell/PowerShell/issues/5407)</span></span>

<span data-ttu-id="09447-199">A classe `AddTypeCommandBase` foi removida de `Add-Type` para melhorar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="09447-199">The `AddTypeCommandBase` class was removed from `Add-Type` to improve performance.</span></span> <span data-ttu-id="09447-200">Essa classe é usada apenas pelo cmdlet Add-Type e não deve afetar os usuários.</span><span class="sxs-lookup"><span data-stu-id="09447-200">This class is only used by the Add-Type cmdlet and should not impact users.</span></span>

### <a name="unify-cmdlets-with-parameter--encoding-to-be-of-type-systemtextencoding-5080"></a><span data-ttu-id="09447-201">Unificação dos cmdlets com o parâmetro `-Encoding` para o tipo `System.Text.Encoding` [#5080](https://github.com/PowerShell/PowerShell/issues/5080)</span><span class="sxs-lookup"><span data-stu-id="09447-201">Unify cmdlets with parameter `-Encoding` to be of type `System.Text.Encoding` [#5080](https://github.com/PowerShell/PowerShell/issues/5080)</span></span>

<span data-ttu-id="09447-202">O valor de `-Encoding`, `Byte`, foi removido dos cmdlets do provedor do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="09447-202">The `-Encoding` value `Byte` has been removed from the filesystem provider cmdlets.</span></span> <span data-ttu-id="09447-203">Agora, um novo parâmetro, `-AsByteStream`, é usado para especificar a exigência de um fluxo de bytes como entrada, ou que a saída seja um fluxo de bytes.</span><span class="sxs-lookup"><span data-stu-id="09447-203">A new parameter, `-AsByteStream`, is now used to specify that a byte stream is required as input or that the output is a stream of bytes.</span></span>

### <a name="add-better-error-message-for-empty-and-null--uformat-parameter-5055"></a><span data-ttu-id="09447-204">Adição de um mensagem de erro melhor para o parâmetro `-UFormat` vazio ou nulo [#5055](https://github.com/PowerShell/PowerShell/issues/5055)</span><span class="sxs-lookup"><span data-stu-id="09447-204">Add better error message for empty and null `-UFormat` parameter [#5055](https://github.com/PowerShell/PowerShell/issues/5055)</span></span>

<span data-ttu-id="09447-205">Antes, ao passar uma cadeia de caracteres de formato vazio para `-UFormat`, uma mensagem de erro inútil era exibida.</span><span class="sxs-lookup"><span data-stu-id="09447-205">Previously, when passing an empty format string to `-UFormat`, an unhelpful error message would appear.</span></span> <span data-ttu-id="09447-206">Um erro mais descritivo foi adicionado.</span><span class="sxs-lookup"><span data-stu-id="09447-206">A more descriptive error has been added.</span></span>

### <a name="clean-up-console-code-4995"></a><span data-ttu-id="09447-207">Limpeza do código de console [#4995](https://github.com/PowerShell/PowerShell/issues/4995)</span><span class="sxs-lookup"><span data-stu-id="09447-207">Clean up console code [#4995](https://github.com/PowerShell/PowerShell/issues/4995)</span></span>

<span data-ttu-id="09447-208">Os seguintes recursos foram removidos, pois eles não têm suporte no PowerShell Core, e não há planos para adicionar suporte, já que eles existem por motivos de herança para o Windows PowerShell: opção `-psconsolefile` e o código, opção `-importsystemmodules` e o código e código de alteração de fonte.</span><span class="sxs-lookup"><span data-stu-id="09447-208">The following features were removed as they are not supported in PowerShell Core, and there are no plans to add support as they exist for legacy reasons for Windows PowerShell: `-psconsolefile` switch and code, `-importsystemmodules` switch and code, and font changing code.</span></span>

### <a name="removed-runspaceconfiguration-support-4942"></a><span data-ttu-id="09447-209">Remoção do suporte a `RunspaceConfiguration`[#4942](https://github.com/PowerShell/PowerShell/issues/4942)</span><span class="sxs-lookup"><span data-stu-id="09447-209">Removed `RunspaceConfiguration` support [#4942](https://github.com/PowerShell/PowerShell/issues/4942)</span></span>

<span data-ttu-id="09447-210">Antes, ao criar um runspace do PowerShell de forma programática usando a API, era possível usar o [`RunspaceConfiguration`][runspaceconfig] herdado ou o [`InitialSessionState`][iss] mais recente.</span><span class="sxs-lookup"><span data-stu-id="09447-210">Previously, when creating a PowerShell runspace programmatically using the API you could use the legacy [`RunspaceConfiguration`][runspaceconfig] or the newer [`InitialSessionState`][iss].</span></span> <span data-ttu-id="09447-211">Essa alteração removeu o suporte a `RunspaceConfiguration`, e só dá suporte a `InitialSessionState`.</span><span class="sxs-lookup"><span data-stu-id="09447-211">This change removed support for `RunspaceConfiguration` and only supports `InitialSessionState`.</span></span>

[runspaceconfig]: /dotnet/api/system.management.automation.runspaces.runspaceconfiguration
[iss]: /dotnet/api/system.management.automation.runspaces.initialsessionstate

### <a name="commandinvocationintrinsicsinvokescript-bind-arguments-to-input-instead-of-args-4923"></a><span data-ttu-id="09447-212">`CommandInvocationIntrinsics.InvokeScript` associa argumentos a `$input`, em vez de `$args` [#4923](https://github.com/PowerShell/PowerShell/issues/4923)</span><span class="sxs-lookup"><span data-stu-id="09447-212">`CommandInvocationIntrinsics.InvokeScript` bind arguments to `$input` instead of `$args` [#4923](https://github.com/PowerShell/PowerShell/issues/4923)</span></span>

<span data-ttu-id="09447-213">Uma posição incorreta de um parâmetro resultou na passagem de argumentos como entrada, e não como argumentos.</span><span class="sxs-lookup"><span data-stu-id="09447-213">An incorrect position of a parameter resulted in the args passed as input instead of as args.</span></span>

### <a name="remove-unsupported--showwindow-switch-from-get-help-4903"></a><span data-ttu-id="09447-214">Remoção da opção `-showwindow` sem suporte do `Get-Help` [#4903](https://github.com/PowerShell/PowerShell/issues/4903)</span><span class="sxs-lookup"><span data-stu-id="09447-214">Remove unsupported `-showwindow` switch from `Get-Help` [#4903](https://github.com/PowerShell/PowerShell/issues/4903)</span></span>

<span data-ttu-id="09447-215">`-showwindow` depende do WPF, para o qual não há suporte no CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="09447-215">`-showwindow` relies on WPF, which is not supported on CoreCLR.</span></span>

### <a name="allow--to-be-used-in-registry-path-for-remove-item-4866"></a><span data-ttu-id="09447-216">Permissão para que \* seja usado no caminho do registro para `Remove-Item` [#4866](https://github.com/PowerShell/PowerShell/issues/4866)</span><span class="sxs-lookup"><span data-stu-id="09447-216">Allow \* to be used in registry path for `Remove-Item` [#4866](https://github.com/PowerShell/PowerShell/issues/4866)</span></span>

<span data-ttu-id="09447-217">Antes, se `-LiteralPath` recebesse um caractere curinga, o trataria da mesma forma que `-Path`, e se o caractere curinga não encontrasse arquivos, sairia silenciosamente.</span><span class="sxs-lookup"><span data-stu-id="09447-217">Previously, `-LiteralPath` given a wildcard would treat it the same as `-Path` and if the wildcard found no files, it would silently exit.</span></span> <span data-ttu-id="09447-218">O comportamento correto deveria ser um `-LiteralPath` literal, para que se o arquivo não existir, ele cause um erro.</span><span class="sxs-lookup"><span data-stu-id="09447-218">Correct behavior should be that `-LiteralPath` is literal so if the file doesn't exist, it should error.</span></span> <span data-ttu-id="09447-219">A mudança é tratar os curingas usados com `-Literal` como literal.</span><span class="sxs-lookup"><span data-stu-id="09447-219">Change is to treat wildcards used with `-Literal` as literal.</span></span>

### <a name="fix-set-service-failing-test-4802"></a><span data-ttu-id="09447-220">Correção do teste de falha de `Set-Service`[#4802](https://github.com/PowerShell/PowerShell/issues/4802)</span><span class="sxs-lookup"><span data-stu-id="09447-220">Fix `Set-Service` failing test [#4802](https://github.com/PowerShell/PowerShell/issues/4802)</span></span>

<span data-ttu-id="09447-221">Antes, se `New-Service -StartupType foo` fosse usado, `foo` era ignorado e o serviço era criado com algum tipo de inicialização padrão.</span><span class="sxs-lookup"><span data-stu-id="09447-221">Previously, if `New-Service -StartupType foo` was used, `foo` was ignored and the service was created with some default startup type.</span></span> <span data-ttu-id="09447-222">Essa alteração serve para lançar explicitamente um erro para um tipo de inicialização inválida.</span><span class="sxs-lookup"><span data-stu-id="09447-222">This change is to explicitly throw an error for an invalid startup type.</span></span>

### <a name="rename-isosx-to-ismacos-4700"></a><span data-ttu-id="09447-223">`$IsOSX` renomeado para `$IsMacOS` [#4700](https://github.com/PowerShell/PowerShell/issues/4700)</span><span class="sxs-lookup"><span data-stu-id="09447-223">Rename `$IsOSX` to `$IsMacOS` [#4700](https://github.com/PowerShell/PowerShell/issues/4700)</span></span>

<span data-ttu-id="09447-224">A nomenclatura no PowerShell deve ser consistente com nossa nomenclatura e estar de acordo com o uso da Apple do macOS, em vez de OSX.</span><span class="sxs-lookup"><span data-stu-id="09447-224">The naming in PowerShell should be consistent with our naming and conform to Apple's use of macOS instead of OSX.</span></span> <span data-ttu-id="09447-225">No entanto, para facilitar a leitura e manter a consistência, permaneceremos com o uso de maiúsculas e minúsculas do padrão Pascal.</span><span class="sxs-lookup"><span data-stu-id="09447-225">However, for readability and consistently we are staying with Pascal casing.</span></span>

### <a name="make-error-message-consistent-when-invalid-script-is-passed-to--file-better-error-when-passed-ambiguous-argument-4573"></a><span data-ttu-id="09447-226">Mensagem de erro consistente quando um script inválido é passado para -File, erro mais claro ao receber argumentos ambíguos [#4573](https://github.com/PowerShell/PowerShell/issues/4573)</span><span class="sxs-lookup"><span data-stu-id="09447-226">Make error message consistent when invalid script is passed to -File, better error when passed ambiguous argument [#4573](https://github.com/PowerShell/PowerShell/issues/4573)</span></span>

<span data-ttu-id="09447-227">Altera os códigos de saída de `pwsh.exe` para alinhar com as convenções Unix</span><span class="sxs-lookup"><span data-stu-id="09447-227">Change the exit codes of `pwsh.exe` to align with Unix conventions</span></span>

### <a name="removal-of-localaccount-and-cmdlets-from--diagnostics-modules-4302-4303"></a><span data-ttu-id="09447-228">Remoção de `LocalAccount` e de cmdlets dos módulos `Diagnostics`.</span><span class="sxs-lookup"><span data-stu-id="09447-228">Removal of `LocalAccount` and cmdlets from  `Diagnostics` modules.</span></span> <span data-ttu-id="09447-229">[#4302](https://github.com/PowerShell/PowerShell/issues/4302) [#4303](https://github.com/PowerShell/PowerShell/issues/4303)</span><span class="sxs-lookup"><span data-stu-id="09447-229">[#4302](https://github.com/PowerShell/PowerShell/issues/4302) [#4303](https://github.com/PowerShell/PowerShell/issues/4303)</span></span>

<span data-ttu-id="09447-230">Devido à falta de suporte às APIs, o módulo `LocalAccounts` e os cmdlets `Counter` no módulo `Diagnostics` foram removidos até encontrarmos uma solução melhor.</span><span class="sxs-lookup"><span data-stu-id="09447-230">Due to unsupported APIs, the `LocalAccounts` module and the `Counter` cmdlets in the `Diagnostics` module were removed until a better solution is found.</span></span>

### <a name="executing-powershell-script-with-bool-parameter-does-not-work-4036"></a><span data-ttu-id="09447-231">A execução de script do PowerShell com o parâmetro bool não funciona [#4036](https://github.com/PowerShell/PowerShell/issues/4036)</span><span class="sxs-lookup"><span data-stu-id="09447-231">Executing PowerShell script with bool parameter does not work [#4036](https://github.com/PowerShell/PowerShell/issues/4036)</span></span>

<span data-ttu-id="09447-232">Antes, usar **powershell.exe** (agora **pwsh.exe**) para executar um script do PowerShell usando `-File` não fornecia uma maneira de passar `$true`/`$false` como valores de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="09447-232">Previously, using **powershell.exe** (now **pwsh.exe**) to execute a PowerShell script using `-File` provided no way to pass `$true`/`$false` as parameter values.</span></span> <span data-ttu-id="09447-233">Adicionamos suporte para `$true`/`$false` como valores analisados para parâmetros.</span><span class="sxs-lookup"><span data-stu-id="09447-233">Support for `$true`/`$false` as parsed values to parameters was added.</span></span> <span data-ttu-id="09447-234">Também há suporte para valores de opção, pois a sintaxe documentada no momento não funciona.</span><span class="sxs-lookup"><span data-stu-id="09447-234">Switch values are also supported as currently documented syntax doesn't work.</span></span>

### <a name="remove-clrversion-property-from-psversiontable-4027"></a><span data-ttu-id="09447-235">Remoção da propriedade `ClrVersion` de `$PSVersionTable` [#4027](https://github.com/PowerShell/PowerShell/issues/4027)</span><span class="sxs-lookup"><span data-stu-id="09447-235">Remove `ClrVersion` property from `$PSVersionTable` [#4027](https://github.com/PowerShell/PowerShell/issues/4027)</span></span>

<span data-ttu-id="09447-236">A propriedade `ClrVersion` de `$PSVersionTable` não é útil com CoreCLR, os usuários finais não devem usar esse valor para determinar a compatibilidade.</span><span class="sxs-lookup"><span data-stu-id="09447-236">The `ClrVersion` property of `$PSVersionTable` is not useful with CoreCLR, end users should not be using that value to determine compatibility.</span></span>

### <a name="change-positional-parameter-for-powershellexe-from--command-to--file-4019"></a><span data-ttu-id="09447-237">Alteração do parâmetro posicional para `powershell.exe` de `-Command` para `-File` [#4019](https://github.com/PowerShell/PowerShell/issues/4019)</span><span class="sxs-lookup"><span data-stu-id="09447-237">Change positional parameter for `powershell.exe` from `-Command` to `-File` [#4019](https://github.com/PowerShell/PowerShell/issues/4019)</span></span>

<span data-ttu-id="09447-238">Habilitação geral do uso do PowerShell em plataformas diferentes do Windows.</span><span class="sxs-lookup"><span data-stu-id="09447-238">Enable shebang use of PowerShell on non-Windows platforms.</span></span> <span data-ttu-id="09447-239">Isso significa que, em sistemas baseados em Unix, você pode tornar um script executável para invocar o PowerShell automaticamente, em vez de invocar explicitamente `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="09447-239">This means on Unix based systems, you can make a script executable that would invoke PowerShell automatically rather than explicitly invoking `pwsh`.</span></span> <span data-ttu-id="09447-240">Isso também significa que agora você pode fazer coisas como `powershell foo.ps1` ou `powershell fooScript` sem especificar `-File`.</span><span class="sxs-lookup"><span data-stu-id="09447-240">This also means that you can now do things like `powershell foo.ps1` or `powershell fooScript` without specifying `-File`.</span></span> <span data-ttu-id="09447-241">No entanto, essa alteração agora exige que você especifique explicitamente `-c` ou `-Command` ao tentar fazer coisas como `powershell.exe Get-Command`.</span><span class="sxs-lookup"><span data-stu-id="09447-241">However, this change now requires that you explicitly specify `-c` or `-Command` when trying to do things like `powershell.exe Get-Command`.</span></span>

### <a name="implement-unicode-escape-parsing-3958"></a><span data-ttu-id="09447-242">Implementação da análise de escape de Unicode [#3958](https://github.com/PowerShell/PowerShell/issues/3958)</span><span class="sxs-lookup"><span data-stu-id="09447-242">Implement Unicode escape parsing [#3958](https://github.com/PowerShell/PowerShell/issues/3958)</span></span>

<span data-ttu-id="09447-243">`` `u####`` ou `` `u{####}`` é convertido no caractere Unicode correspondente.</span><span class="sxs-lookup"><span data-stu-id="09447-243">`` `u####`` or `` `u{####}`` is converted to the corresponding Unicode character.</span></span> <span data-ttu-id="09447-244">Para gerar um `` `u`` literal, escape o acento grave: ``` ``u```.</span><span class="sxs-lookup"><span data-stu-id="09447-244">To output a literal `` `u``, escape the backtick: ``` ``u```.</span></span>

### <a name="change-new-modulemanifest-encoding-to-utf8nobom-on-non-windows-platforms-3940"></a><span data-ttu-id="09447-245">Altere a codificação `New-ModuleManifest` para `UTF8NoBOM` em plataformas que não são o Windows [#3940](https://github.com/PowerShell/PowerShell/issues/3940)</span><span class="sxs-lookup"><span data-stu-id="09447-245">Change `New-ModuleManifest` encoding to `UTF8NoBOM` on non-Windows platforms [#3940](https://github.com/PowerShell/PowerShell/issues/3940)</span></span>

<span data-ttu-id="09447-246">Antes, `New-ModuleManifest` criava manifestos psd1 em UTF-16 com BOM, criando um problema para as ferramentas do Linux.</span><span class="sxs-lookup"><span data-stu-id="09447-246">Previously, `New-ModuleManifest` creates psd1 manifests in UTF-16 with BOM, creating a problem for Linux tools.</span></span> <span data-ttu-id="09447-247">Essa alteração da falha altera a codificação de `New-ModuleManifest` para UTF (sem BOM) em plataformas que não são Windows.</span><span class="sxs-lookup"><span data-stu-id="09447-247">This breaking change changes the encoding of `New-ModuleManifest` to be UTF (no BOM) in non-Windows platforms.</span></span>

### <a name="prevent-get-childitem-from-recursing-into-symlinks-1875-3780"></a><span data-ttu-id="09447-248">Impedir que `Get-ChildItem` faça a recursão em links simbólicos (#1875).</span><span class="sxs-lookup"><span data-stu-id="09447-248">Prevent `Get-ChildItem` from recursing into symlinks (#1875).</span></span> [<span data-ttu-id="09447-249">#3780</span><span class="sxs-lookup"><span data-stu-id="09447-249">#3780</span></span>](https://github.com/PowerShell/PowerShell/issues/3780)

<span data-ttu-id="09447-250">Essa alteração alinha mais `Get-ChildItem` ao Unix `ls -r` e aos comandos nativos `dir /s` do Windows.</span><span class="sxs-lookup"><span data-stu-id="09447-250">This change brings `Get-ChildItem` more in line with the Unix `ls -r` and the Windows `dir /s` native commands.</span></span> <span data-ttu-id="09447-251">Como os comandos mencionados, o cmdlet exibe links simbólicos para diretórios encontrados durante a recursão, mas não faz a recursão neles.</span><span class="sxs-lookup"><span data-stu-id="09447-251">Like the mentioned commands, the cmdlet displays symbolic links to directories found during recursion, but does not recurse into them.</span></span>

### <a name="fix-get-content--delimiter-to-not-include-the-delimiter-in-the-returned-lines-3706"></a><span data-ttu-id="09447-252">Correção de `Get-Content -Delimiter` para não incluir o delimitador nas linhas retornadas [#3706](https://github.com/PowerShell/PowerShell/issues/3706)</span><span class="sxs-lookup"><span data-stu-id="09447-252">Fix `Get-Content -Delimiter` to not include the delimiter in the returned lines [#3706](https://github.com/PowerShell/PowerShell/issues/3706)</span></span>

<span data-ttu-id="09447-253">Antes, a saída durante o uso de `Get-Content -Delimiter` era inconsistente e inconveniente, pois exigia mais processamento dos dados para remover o delimitador.</span><span class="sxs-lookup"><span data-stu-id="09447-253">Previously, the output while using `Get-Content -Delimiter` was inconsistent and inconvenient as it required further processing of the data to remove the delimiter.</span></span> <span data-ttu-id="09447-254">Essa alteração remove o delimitador das linhas retornadas.</span><span class="sxs-lookup"><span data-stu-id="09447-254">This change removes the delimiter in returned lines.</span></span>

### <a name="implement-format-hex-in-c-3320"></a><span data-ttu-id="09447-255">Implementação do Format-Hex em C# [#3320](https://github.com/PowerShell/PowerShell/issues/3320)</span><span class="sxs-lookup"><span data-stu-id="09447-255">Implement Format-Hex in C# [#3320](https://github.com/PowerShell/PowerShell/issues/3320)</span></span>

<span data-ttu-id="09447-256">O parâmetro `-Raw` agora é "não operacional" (ou seja, não faz nada).</span><span class="sxs-lookup"><span data-stu-id="09447-256">The `-Raw` parameter is now a "no-op" (in that it does nothing).</span></span> <span data-ttu-id="09447-257">A partir de agora, toda a saída será exibida com uma representação verdadeira de números que incluem todos os bytes de seu tipo (o que o parâmetro `-Raw` fazia antes dessa alteração).</span><span class="sxs-lookup"><span data-stu-id="09447-257">Going forward all of the output will be displayed with a true representation of numbers that includes all of the bytes for its type (what the `-Raw` parameter was formally doing prior to this change).</span></span>

### <a name="powershell-as-a-default-shell-doesnt-work-with-script-command-3319"></a><span data-ttu-id="09447-258">O PowerShell como um shell padrão não funciona com o comando de script [#3319](https://github.com/PowerShell/PowerShell/issues/3319)</span><span class="sxs-lookup"><span data-stu-id="09447-258">PowerShell as a default shell doesn't work with script command [#3319](https://github.com/PowerShell/PowerShell/issues/3319)</span></span>

<span data-ttu-id="09447-259">Em Unix, é padrão dos shells aceitar `-i` para um shell interativo, e muitas ferramentas esperam esse comportamento (`script` por exemplo e ao configurar o PowerShell como o shell padrão) e chama o shell com a opção `-i`.</span><span class="sxs-lookup"><span data-stu-id="09447-259">On Unix, it is a convention for shells to accept `-i` for an interactive shell and many tools expect this behavior (`script` for example, and when setting PowerShell as the default shell) and calls the shell with the `-i` switch.</span></span> <span data-ttu-id="09447-260">Essa alteração causa falhas, pois, antes, `-i` podia ser usado como uma síntese disponível para corresponder `-inputformat`, e agora precisa ser `-in`.</span><span class="sxs-lookup"><span data-stu-id="09447-260">This change is breaking in that `-i` previously could be used as short hand to match `-inputformat`, which now needs to be `-in`.</span></span>

### <a name="typo-fix-in-get-computerinfo-property-name-3167"></a><span data-ttu-id="09447-261">Correção de erro de digitação no nome da propriedade Get-ComputerInfo [#3167](https://github.com/PowerShell/PowerShell/issues/3167)</span><span class="sxs-lookup"><span data-stu-id="09447-261">Typo fix in Get-ComputerInfo property name [#3167](https://github.com/PowerShell/PowerShell/issues/3167)</span></span>

<span data-ttu-id="09447-262">`BiosSerialNumber` foi digitado incorretamente como `BiosSeralNumber` e foi alterado para a ortografia correta.</span><span class="sxs-lookup"><span data-stu-id="09447-262">`BiosSerialNumber` was misspelled as `BiosSeralNumber` and has been changed to the correct spelling.</span></span>

### <a name="add-get-stringhash-and-get-filehash-cmdlets-3024"></a><span data-ttu-id="09447-263">Adição dos cmdlets `Get-StringHash` e `Get-FileHash`[#3024](https://github.com/PowerShell/PowerShell/issues/3024)</span><span class="sxs-lookup"><span data-stu-id="09447-263">Add `Get-StringHash` and `Get-FileHash` cmdlets [#3024](https://github.com/PowerShell/PowerShell/issues/3024)</span></span>

<span data-ttu-id="09447-264">A mudança é que alguns algoritmos de hash não têm suporte do CoreFX, portanto, não estão mais disponíveis:</span><span class="sxs-lookup"><span data-stu-id="09447-264">This change is that some hash algorithms are not supported by CoreFX, therefore they are no longer available:</span></span>

- `MACTripleDES`
- `RIPEMD160`

### <a name="add-validation-on-get--cmdlets-where-passing-null-returns-all-objects-instead-of-error-2672"></a><span data-ttu-id="09447-265">Adição de validação em cmdlets `Get-*`, em que passar $null retorna todos os objetos em vez do erro [#2672](https://github.com/PowerShell/PowerShell/issues/2672)</span><span class="sxs-lookup"><span data-stu-id="09447-265">Add validation on `Get-*` cmdlets where passing $null returns all objects instead of error [#2672](https://github.com/PowerShell/PowerShell/issues/2672)</span></span>

<span data-ttu-id="09447-266">Agora, passar `$null` para qualquer uma das seguintes opções gera um erro:</span><span class="sxs-lookup"><span data-stu-id="09447-266">Passing `$null` to any of the following now throws an error:</span></span>

- `Get-Credential -UserName`
- `Get-Event -SourceIdentifier`
- `Get-EventSubscriber -SourceIdentifier`
- `Get-Help -Name`
- `Get-PSBreakpoint -Script`
- `Get-PSProvider -PSProvider`
- `Get-PSSessionConfiguration -Name`
- `Get-PSSnapin -Name`
- `Get-Runspace -Name`
- `Get-RunspaceDebug -RunspaceName`
- `Get-Service -Name`
- `Get-TraceSource -Name`
- `Get-Variable -Name`
- `Get-WmiObject -Class`
- `Get-WmiObject -Property`

### <a name="add-support-w3c-extended-log-file-format-in-import-csv-2482"></a><span data-ttu-id="09447-267">Adição de suporte ao Formato de Arquivo de Log Estendido do W3C em `Import-Csv` [#2482](https://github.com/PowerShell/PowerShell/issues/2482)</span><span class="sxs-lookup"><span data-stu-id="09447-267">Add support W3C Extended Log File Format in `Import-Csv` [#2482](https://github.com/PowerShell/PowerShell/issues/2482)</span></span>

<span data-ttu-id="09447-268">Antes, o cmdlet `Import-Csv` não podia ser usado para importar diretamente os arquivos de log no formato de log estendido do W3C e uma ação adicional seria necessária.</span><span class="sxs-lookup"><span data-stu-id="09447-268">Previously, the `Import-Csv` cmdlet cannot be used to directly import the log files in W3C extended log format and additional action would be required.</span></span> <span data-ttu-id="09447-269">Com essa alteração, há suporte para o formato de log estendido W3C.</span><span class="sxs-lookup"><span data-stu-id="09447-269">With this change, W3C extended log format is supported.</span></span>

### <a name="parameter-binding-problem-with-valuefromremainingarguments-in-ps-functions-2035"></a><span data-ttu-id="09447-270">Problema de associação de parâmetro com `ValueFromRemainingArguments` nas funções de PS [#2035](https://github.com/PowerShell/PowerShell/issues/2035)</span><span class="sxs-lookup"><span data-stu-id="09447-270">Parameter binding problem with `ValueFromRemainingArguments` in PS functions [#2035](https://github.com/PowerShell/PowerShell/issues/2035)</span></span>

<span data-ttu-id="09447-271">Agora, `ValueFromRemainingArguments` retorna os valores como uma matriz em vez de um único valor que é uma matriz.</span><span class="sxs-lookup"><span data-stu-id="09447-271">`ValueFromRemainingArguments` now returns the values as an array instead of a single value which itself is an array.</span></span>

### <a name="buildversion-is-removed-from-psversiontable-1415"></a><span data-ttu-id="09447-272">`BuildVersion` foi removido de `$PSVersionTable` [#1415](https://github.com/PowerShell/PowerShell/issues/1415)</span><span class="sxs-lookup"><span data-stu-id="09447-272">`BuildVersion` is removed from `$PSVersionTable` [#1415](https://github.com/PowerShell/PowerShell/issues/1415)</span></span>

<span data-ttu-id="09447-273">Remoção da propriedade `BuildVersion` de `$PSVersionTable`.</span><span class="sxs-lookup"><span data-stu-id="09447-273">Remove the `BuildVersion` property from `$PSVersionTable`.</span></span> <span data-ttu-id="09447-274">Essa propriedade foi vinculada à versão de build do Windows.</span><span class="sxs-lookup"><span data-stu-id="09447-274">This property was tied to the Windows build version.</span></span> <span data-ttu-id="09447-275">Em vez disso, recomendamos que você use `GitCommitId` para recuperar a versão de build exata do PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="09447-275">Instead, we recommend that you use `GitCommitId` to retrieve the exact build version of PowerShell Core.</span></span>

### <a name="changes-to-web-cmdlets"></a><span data-ttu-id="09447-276">Alterações nos cmdlets da Web</span><span class="sxs-lookup"><span data-stu-id="09447-276">Changes to Web Cmdlets</span></span>

<span data-ttu-id="09447-277">A API do .NET subjacente dos cmdlets Web foi alterada para `System.Net.Http.HttpClient`.</span><span class="sxs-lookup"><span data-stu-id="09447-277">The underlying .NET API of the Web Cmdlets has been changed to `System.Net.Http.HttpClient`.</span></span> <span data-ttu-id="09447-278">Essa alteração fornece muitos benefícios.</span><span class="sxs-lookup"><span data-stu-id="09447-278">This change provides many benefits.</span></span> <span data-ttu-id="09447-279">No entanto, essa alteração, junto com a falta de interoperabilidade com o Internet Explorer, resultou em várias alterações com falha em `Invoke-WebRequest` e `Invoke-RestMethod`.</span><span class="sxs-lookup"><span data-stu-id="09447-279">However, this change along with a lack of interoperability with Internet Explorer have resulted in several breaking changes within `Invoke-WebRequest` and `Invoke-RestMethod`.</span></span>

- <span data-ttu-id="09447-280">Agora, `Invoke-WebRequest` dá suporte apenas à Análise de HTML básica.</span><span class="sxs-lookup"><span data-stu-id="09447-280">`Invoke-WebRequest` now supports basic HTML Parsing only.</span></span> <span data-ttu-id="09447-281">`Invoke-WebRequest` sempre retorna um objeto `BasicHtmlWebResponseObject`.</span><span class="sxs-lookup"><span data-stu-id="09447-281">`Invoke-WebRequest` always returns a `BasicHtmlWebResponseObject` object.</span></span> <span data-ttu-id="09447-282">As propriedades `ParsedHtml` e `Forms` foram removidas.</span><span class="sxs-lookup"><span data-stu-id="09447-282">The `ParsedHtml` and `Forms` properties have been removed.</span></span>
- <span data-ttu-id="09447-283">Agora, os valores de `BasicHtmlWebResponseObject.Headers` são `String[]`, em vez de `String`.</span><span class="sxs-lookup"><span data-stu-id="09447-283">`BasicHtmlWebResponseObject.Headers` values are now `String[]` instead of `String`.</span></span>
- <span data-ttu-id="09447-284">Agora, `BasicHtmlWebResponseObject.BaseResponse` é um objeto de `System.Net.Http.HttpResponseMessage`.</span><span class="sxs-lookup"><span data-stu-id="09447-284">`BasicHtmlWebResponseObject.BaseResponse` is now a `System.Net.Http.HttpResponseMessage` object.</span></span>
- <span data-ttu-id="09447-285">A propriedade `Response` nas exceções do cmdlet da Web agora é um objeto `System.Net.Http.HttpResponseMessage`.</span><span class="sxs-lookup"><span data-stu-id="09447-285">The `Response` property on Web Cmdlet exceptions is now a `System.Net.Http.HttpResponseMessage` object.</span></span>
- <span data-ttu-id="09447-286">Agora, a análise de cabeçalho RFC estrita é padrão para o parâmetro `-Headers` e `-UserAgent`.</span><span class="sxs-lookup"><span data-stu-id="09447-286">Strict RFC header parsing is now default for the `-Headers` and `-UserAgent` parameter.</span></span> <span data-ttu-id="09447-287">Isso pode ser ignorado com `-SkipHeaderValidation`.</span><span class="sxs-lookup"><span data-stu-id="09447-287">This can be bypassed with `-SkipHeaderValidation`.</span></span>
- <span data-ttu-id="09447-288">Os esquemas de URI `file://` e `ftp://` não têm mais suporte.</span><span class="sxs-lookup"><span data-stu-id="09447-288">`file://` and `ftp://` URI schemes are no longer supported.</span></span>
- <span data-ttu-id="09447-289">As configurações de `System.Net.ServicePointManager` não são mais cumpridas.</span><span class="sxs-lookup"><span data-stu-id="09447-289">`System.Net.ServicePointManager` settings are no longer honored.</span></span>
- <span data-ttu-id="09447-290">No momento, não há uma autenticação baseada em certificado disponível no macOS.</span><span class="sxs-lookup"><span data-stu-id="09447-290">There is currently no certificate based authentication available on macOS.</span></span>
- <span data-ttu-id="09447-291">O uso de `-Credential` sobre uma URI `http://` resultará em erro.</span><span class="sxs-lookup"><span data-stu-id="09447-291">Use of `-Credential` over an `http://` URI will result in an error.</span></span> <span data-ttu-id="09447-292">Use um URI `https://` ou forneça o parâmetro `-AllowUnencryptedAuthentication` para suprimir o erro.</span><span class="sxs-lookup"><span data-stu-id="09447-292">Use an `https://` URI or supply the `-AllowUnencryptedAuthentication` parameter to suppress the error.</span></span>
- <span data-ttu-id="09447-293">Agora, `-MaximumRedirection` produz um erro de encerramento quando as tentativas de redirecionamento excedem o limite fornecido em vez de retornar os resultados do último redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="09447-293">`-MaximumRedirection` now produces a terminating error when redirection attempts exceed the provided limit instead of returning the results of the last redirection.</span></span>
- <span data-ttu-id="09447-294">No PowerShell 6.2, foi feita uma alteração no padrão da codificação UTF-8 para respostas JSON.</span><span class="sxs-lookup"><span data-stu-id="09447-294">In PowerShell 6.2, a change was made to default to UTF-8 encoding for JSON responses.</span></span> <span data-ttu-id="09447-295">Quando um conjunto de caracteres não é fornecido para uma resposta JSON, a codificação padrão deve ser UTF-8 conforme RFC 8259.</span><span class="sxs-lookup"><span data-stu-id="09447-295">When a charset is not supplied for a JSON response, the default encoding should be UTF-8 per RFC 8259.</span></span>
