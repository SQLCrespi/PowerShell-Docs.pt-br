---
title: Novidades no PowerShell 7.1
description: Novos recursos e alterações lançados no PowerShell 7.1
ms.date: 12/15/2020
ms.openlocfilehash: 6bbeccd07dd696ee019828bdcd68ce3f6ee627e3
ms.sourcegitcommit: 1628fd2a1f50aec2f31ffb1c451a3ce77c08983c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "97577200"
---
# <a name="whats-new-in-powershell-71"></a><span data-ttu-id="f0b32-103">Novidades no PowerShell 7.1</span><span class="sxs-lookup"><span data-stu-id="f0b32-103">What's New in PowerShell 7.1</span></span>

<span data-ttu-id="f0b32-104">Em 11 de novembro de 2020, [anunciamos](https://devblogs.microsoft.com/powershell/announcing-powershell-7-1/) a disponibilidade geral do PowerShell 7.1.</span><span class="sxs-lookup"><span data-stu-id="f0b32-104">On November 11, 2020 we [announced](https://devblogs.microsoft.com/powershell/announcing-powershell-7-1/) the general availability of PowerShell 7.1.</span></span> <span data-ttu-id="f0b32-105">Aproveitando a base estabelecida no PowerShell 7.0, nossos esforços se concentram nos problemas da comunidade e incluem vários aprimoramentos e correções.</span><span class="sxs-lookup"><span data-stu-id="f0b32-105">Building on the foundation established in PowerShell 7.0, our efforts focused on community issues and include a number of improvements and fixes.</span></span> <span data-ttu-id="f0b32-106">Estamos comprometidos em garantir que o PowerShell continue sendo uma plataforma estável e de alto desempenho.</span><span class="sxs-lookup"><span data-stu-id="f0b32-106">We are committed to ensuring that PowerShell remains a stable and performant platform.</span></span>

<span data-ttu-id="f0b32-107">O PowerShell 7.1 inclui os recursos, as atualizações e as alterações interruptivas a seguir.</span><span class="sxs-lookup"><span data-stu-id="f0b32-107">PowerShell 7.1 includes the following features, updates, and breaking changes.</span></span>

- <span data-ttu-id="f0b32-108">PSReadLine 2.1.0, que inclui o Predictive IntelliSense</span><span class="sxs-lookup"><span data-stu-id="f0b32-108">PSReadLine 2.1.0, which includes Predictive IntelliSense</span></span>
- <span data-ttu-id="f0b32-109">O PowerShell 7.1 foi publicado na Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="f0b32-109">PowerShell 7.1 has been published to the Microsoft Store</span></span>
- <span data-ttu-id="f0b32-110">Pacotes do instalador atualizados para novas versões do sistema operacional compatíveis com ARM64</span><span class="sxs-lookup"><span data-stu-id="f0b32-110">Installer packages updated for new OS versions with support for ARM64</span></span>
- <span data-ttu-id="f0b32-111">Quatro novos recursos experimentais e dois recursos experimentais promovidos para o básico</span><span class="sxs-lookup"><span data-stu-id="f0b32-111">4 new experimental features and 2 experimental features promoted to mainstream</span></span>
- <span data-ttu-id="f0b32-112">Várias alterações interruptivas para melhorar a usabilidade</span><span class="sxs-lookup"><span data-stu-id="f0b32-112">Several breaking changes to improve usability</span></span>

<span data-ttu-id="f0b32-113">Para ver uma lista completa das alterações, confira o [LOG DE MUDANÇAS](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG/7.1.md) no repositório do GitHub.</span><span class="sxs-lookup"><span data-stu-id="f0b32-113">For a complete list of changes, see the [CHANGELOG](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG/7.1.md) in the GitHub repository.</span></span>

## <a name="psreadline-210"></a><span data-ttu-id="f0b32-114">PSReadLine 2.1.0</span><span class="sxs-lookup"><span data-stu-id="f0b32-114">PSReadLine 2.1.0</span></span>

<span data-ttu-id="f0b32-115">O PowerShell 7.1 também inclui PSReadLine 2.1.0.</span><span class="sxs-lookup"><span data-stu-id="f0b32-115">PowerShell 7.1 also include PSReadLine 2.1.0.</span></span> <span data-ttu-id="f0b32-116">Essa versão inclui o Predictive IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="f0b32-116">This version includes Predictive IntelliSense.</span></span> <span data-ttu-id="f0b32-117">Para obter mais informações sobre o recurso Predictive IntelliSense, confira o[anúncio](https://devblogs.microsoft.com/powershell/announcing-psreadline-2-1-with-predictive-intellisense/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0b32-117">For more information about the Predictive IntelliSense feature, see the [announcement](https://devblogs.microsoft.com/powershell/announcing-psreadline-2-1-with-predictive-intellisense/) in the PowerShell blog.</span></span>

## <a name="microsoft-store-installer-package"></a><span data-ttu-id="f0b32-118">Pacote do instalador da Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="f0b32-118">Microsoft Store installer package</span></span>

<span data-ttu-id="f0b32-119">O PowerShell 7.1 foi publicado na Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="f0b32-119">PowerShell 7.1 has been published to the Microsoft Store.</span></span> <span data-ttu-id="f0b32-120">Você pode encontrar a versão do PowerShell no site da [Microsoft Store](https://www.microsoft.com/store/apps/9MZ1SNWT0N5D) ou no aplicativo da Store no Windows.</span><span class="sxs-lookup"><span data-stu-id="f0b32-120">You can find the PowerShell release on the [Microsoft Store](https://www.microsoft.com/store/apps/9MZ1SNWT0N5D) website or in the Store application in Windows.</span></span>

<span data-ttu-id="f0b32-121">Benefícios do pacote da Microsoft Store:</span><span class="sxs-lookup"><span data-stu-id="f0b32-121">Benefits of the Microsoft Store package:</span></span>

- <span data-ttu-id="f0b32-122">Atualizações automáticas integradas diretamente no Windows 10</span><span class="sxs-lookup"><span data-stu-id="f0b32-122">Automatic updates built right into Windows 10</span></span>
- <span data-ttu-id="f0b32-123">Integra-se a outros mecanismos de distribuição de software, como Intune e SCCM</span><span class="sxs-lookup"><span data-stu-id="f0b32-123">Integrates with other software distribution mechanisms like Intune and SCCM</span></span>

> [!NOTE]
> <span data-ttu-id="f0b32-124">Nenhuma definição de configuração no nível do sistema armazenada em `$PSHOME` pode ser modificada.</span><span class="sxs-lookup"><span data-stu-id="f0b32-124">Any system-level configuration settings stored in `$PSHOME` cannot be modified.</span></span> <span data-ttu-id="f0b32-125">Isso inclui a configuração do WSMAN.</span><span class="sxs-lookup"><span data-stu-id="f0b32-125">This includes the WSMAN configuration.</span></span> <span data-ttu-id="f0b32-126">Isso impede que as sessões remotas se conectem a instalações baseadas na Store do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0b32-126">This prevents remote sessions from connecting to Store-based installs of PowerShell.</span></span> <span data-ttu-id="f0b32-127">Há suporte para configurações no nível do usuário e para comunicação remota SSH.</span><span class="sxs-lookup"><span data-stu-id="f0b32-127">User-level configurations and SSH remoting are supported.</span></span>

## <a name="other-installers"></a><span data-ttu-id="f0b32-128">Outros instaladores</span><span class="sxs-lookup"><span data-stu-id="f0b32-128">Other installers</span></span>

<span data-ttu-id="f0b32-129">Para obter informações mais atualizadas sobre os sistemas operacionais com suporte e o ciclo de vida de suporte, confira o [Ciclo de vida de suporte do PowerShell](/powershell/scripting/powershell-support-lifecycle).</span><span class="sxs-lookup"><span data-stu-id="f0b32-129">For more up-to-date information about supported operating systems and support lifecycle, see the [PowerShell Support Lifecycle](/powershell/scripting/powershell-support-lifecycle).</span></span>

<span data-ttu-id="f0b32-130">Confira as instruções de instalação do seu sistema operacional preferido:</span><span class="sxs-lookup"><span data-stu-id="f0b32-130">Check the installation instructions for your preferred operating system:</span></span>

- [<span data-ttu-id="f0b32-131">Windows</span><span class="sxs-lookup"><span data-stu-id="f0b32-131">Windows</span></span>](/powershell/scripting/install/installing-powershell-core-on-windows)
- [<span data-ttu-id="f0b32-132">macOS</span><span class="sxs-lookup"><span data-stu-id="f0b32-132">macOS</span></span>](/powershell/scripting/install/installing-powershell-core-on-macos)
- [<span data-ttu-id="f0b32-133">Linux</span><span class="sxs-lookup"><span data-stu-id="f0b32-133">Linux</span></span>](/powershell/scripting/install/installing-powershell-core-on-linux)

<span data-ttu-id="f0b32-134">Além disso, o PowerShell 7.1 dá suporte às variantes ARM32 e ARM64 do Debian, Ubuntu e ARM64 Alpine Linux.</span><span class="sxs-lookup"><span data-stu-id="f0b32-134">Additionally, PowerShell 7.1 supports ARM32 and ARM64 flavors of Debian, Ubuntu, and ARM64 Alpine Linux.</span></span>

<span data-ttu-id="f0b32-135">Embora não tenha suporte oficial, a comunidade também forneceu pacotes para o [Arch](https://aur.archlinux.org/packages/powershell/) e o Kali Linux.</span><span class="sxs-lookup"><span data-stu-id="f0b32-135">While not officially supported, the community has also provided packages for [Arch](https://aur.archlinux.org/packages/powershell/) and Kali Linux.</span></span>

> [!NOTE]
> <span data-ttu-id="f0b32-136">Atualmente, o Debian 10+, CentOS 8+, Ubuntu 20.04, Alpine e Arm não dão suporte à comunicação remota do WinRM.</span><span class="sxs-lookup"><span data-stu-id="f0b32-136">Debian 10+, CentOS 8+, Ubuntu 20.04, Alpine and Arm currently do not support WinRM remoting.</span></span> <span data-ttu-id="f0b32-137">Para obter detalhes sobre como configurar a comunicação remota baseada em SSH, confira [Comunicação remota do PowerShell por SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span><span class="sxs-lookup"><span data-stu-id="f0b32-137">For details on setting up SSH-based remoting, see [PowerShell Remoting over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

## <a name="experimental-features"></a><span data-ttu-id="f0b32-138">Recursos experimentais</span><span class="sxs-lookup"><span data-stu-id="f0b32-138">Experimental Features</span></span>

<span data-ttu-id="f0b32-139">Para obter mais informações sobre os recursos experimentais, confira [Usar recursos experimentais](../learn/experimental-features.md).</span><span class="sxs-lookup"><span data-stu-id="f0b32-139">For more information about the Experimental Features, see [Using Experimental Features](../learn/experimental-features.md).</span></span>

<span data-ttu-id="f0b32-140">Estes recursos experimentais agora são recursos básicos nesta versão:</span><span class="sxs-lookup"><span data-stu-id="f0b32-140">The following experimental features are now mainstream features in this release:</span></span>

- [<span data-ttu-id="f0b32-141">PSNullConditionalOperators</span><span class="sxs-lookup"><span data-stu-id="f0b32-141">PSNullConditionalOperators</span></span>](../learn/experimental-features.md#psnullconditionaloperators)
- [<span data-ttu-id="f0b32-142">PSUnixFileStat</span><span class="sxs-lookup"><span data-stu-id="f0b32-142">PSUnixFileStat</span></span>](../learn/experimental-features.md#psunixfilestat)

<span data-ttu-id="f0b32-143">Estes recursos experimentais foram adicionados a esta versão:</span><span class="sxs-lookup"><span data-stu-id="f0b32-143">The following experimental features were added in this release:</span></span>

- [<span data-ttu-id="f0b32-144">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span><span class="sxs-lookup"><span data-stu-id="f0b32-144">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span></span>](../learn/experimental-features.md#microsoftpowershellutilitypsmanagebreakpointsinrunspace)
  - <span data-ttu-id="f0b32-145">O PowerShell 7.1 estende este recurso experimental para adicionar o parâmetro **Runspace** a todos os cmdlets `*-PSBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="f0b32-145">PowerShell 7.1 extends this experimental feature to add the **Runspace** parameter to all `*-PSBreakpoint` cmdlets.</span></span> <span data-ttu-id="f0b32-146">O parâmetro **Runspace** especifica um objeto **Runspace** para interagir com pontos de interrupção no runspace especificado.</span><span class="sxs-lookup"><span data-stu-id="f0b32-146">The **Runspace** parameter specifies a **Runspace** object to interact with breakpoints in the specified runspace.</span></span>

- <span data-ttu-id="f0b32-147">[PSNativePSPathResolution](../learn/experimental-features.md#psnativepspathresolution) – Permite passar caminhos do provedor do PowerShell para comandos nativos incompatíveis com a sintaxe de caminho do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0b32-147">[PSNativePSPathResolution](../learn/experimental-features.md#psnativepspathresolution) - This feature allows you to pass PowerShell provider paths to native commands that don't support PowerShell path syntax.</span></span>

- <span data-ttu-id="f0b32-148">[PSCultureInvariantReplaceOperator](../learn/experimental-features.md#pscultureinvariantreplaceoperator) – Quando o operando à esquerda em uma instrução do operador `-replace` não for uma cadeia de caracteres, esse operando será convertido em uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f0b32-148">[PSCultureInvariantReplaceOperator](../learn/experimental-features.md#pscultureinvariantreplaceoperator) - When the left-hand operand in a `-replace` operator statement is not a string, that operand is converted to a string.</span></span> <span data-ttu-id="f0b32-149">Com o recurso habilitado, as configurações de cultura não são usadas na conversão em cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f0b32-149">With the feature enabled, the conversion does not use Culture settings for string conversion.</span></span>

- <span data-ttu-id="f0b32-150">[PSSubsystemPluginModel](../learn/experimental-features.md#pssubsystempluginmodel) – Estabelece a base para dar suporte a futuros plug-ins do Predictive IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="f0b32-150">[PSSubsystemPluginModel](../learn/experimental-features.md#pssubsystempluginmodel) lays the groundwork to support future Predictive IntelliSense plug-ins.</span></span>

## <a name="breaking-changes-and-improvements"></a><span data-ttu-id="f0b32-151">Alterações de falha e melhorias</span><span class="sxs-lookup"><span data-stu-id="f0b32-151">Breaking Changes and Improvements</span></span>

- <span data-ttu-id="f0b32-152">Corrigir `$?` para não ser `$false` quando o comando nativo for gravado em `stderr` ([nº 13395](https://github.com/PowerShell/PowerShell/pull/13395))</span><span class="sxs-lookup"><span data-stu-id="f0b32-152">Fix `$?` to not be `$false` when native command writes to `stderr` ([#13395](https://github.com/PowerShell/PowerShell/pull/13395))</span></span>

  <span data-ttu-id="f0b32-153">É comum que comandos nativos gravem em `stderr` sem a intenção de indicar uma falha.</span><span class="sxs-lookup"><span data-stu-id="f0b32-153">It is common for native commands to write to `stderr` without intending to indicate a failure.</span></span>
  <span data-ttu-id="f0b32-154">Com essa alteração, `$?` será definido como `$false` somente quando o comando nativo também tiver um código de saída diferente de zero.</span><span class="sxs-lookup"><span data-stu-id="f0b32-154">With this change `$?` is set to `$false` only when the native command also has a non-zero exit code.</span></span> <span data-ttu-id="f0b32-155">Essa alteração não tem relação com o recurso experimental `PSNotApplyErrorActionToStderr`.</span><span class="sxs-lookup"><span data-stu-id="f0b32-155">This change is unrelated to the experimental feature `PSNotApplyErrorActionToStderr`.</span></span>

- <span data-ttu-id="f0b32-156">Fazer `$ErrorActionPreference` não afetar a saída `stderr` de comandos nativos ([nº 13361](https://github.com/PowerShell/PowerShell/pull/13361))</span><span class="sxs-lookup"><span data-stu-id="f0b32-156">Make `$ErrorActionPreference` not affect `stderr` output of native commands ([#13361](https://github.com/PowerShell/PowerShell/pull/13361))</span></span>

  <span data-ttu-id="f0b32-157">É comum que comandos nativos gravem em `stderr` sem a intenção de indicar uma falha.</span><span class="sxs-lookup"><span data-stu-id="f0b32-157">It is common for native commands to write to `stderr` without intending to indicate a failure.</span></span>
  <span data-ttu-id="f0b32-158">Com essa alteração, a saída `stderr` ainda será capturada em objetos **ErrorRecord**, mas o runtime não aplicará `$ErrorActionPreference` se o **ErrorRecord** vier de um comando nativo.</span><span class="sxs-lookup"><span data-stu-id="f0b32-158">With this change, `stderr` output is still captured in **ErrorRecord** objects, but the runtime no longer applies `$ErrorActionPreference` if the **ErrorRecord** comes from a native command.</span></span>

- <span data-ttu-id="f0b32-159">Renomear `-FromUnixTime` para `-UnixTimeSeconds` no `Get-Date` para permitir a entrada de horário do Unix ([nº 13084](https://github.com/PowerShell/PowerShell/pull/13084)) (Obrigado, @aetos382!)</span><span class="sxs-lookup"><span data-stu-id="f0b32-159">Rename `-FromUnixTime` to `-UnixTimeSeconds` on `Get-Date` to allow Unix time input ([#13084](https://github.com/PowerShell/PowerShell/pull/13084)) (Thanks @aetos382!)</span></span>

  <span data-ttu-id="f0b32-160">O parâmetro `-FromUnixTime` foi adicionado durante a 7.1 – versão prévia 2.</span><span class="sxs-lookup"><span data-stu-id="f0b32-160">The `-FromUnixTime` parameter was added during 7.1-preview.2.</span></span> <span data-ttu-id="f0b32-161">O parâmetro foi renomeado para corresponder melhor ao tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="f0b32-161">The parameter was renamed to better match the data type.</span></span> <span data-ttu-id="f0b32-162">Esse parâmetro usa um valor inteiro que representa em segundos desde 1º de janeiro de 1970, 0:00:00.</span><span class="sxs-lookup"><span data-stu-id="f0b32-162">This parameter takes an integer value that represents in seconds since January 1, 1970, 0:00:00.</span></span>

  <span data-ttu-id="f0b32-163">Esse exemplo converte o horário do Unix (representado pelo número de segundos desde 1970-01-01 0:00:00) para DateTime.</span><span class="sxs-lookup"><span data-stu-id="f0b32-163">This example converts a Unix time (represented by the number of seconds since 1970-01-01 0:00:00) to DateTime.</span></span>

  ```powershell
  Get-Date -UnixTimeSeconds 1577836800

  Wednesday, January 01, 2020 12:00:00 AM
  ```

- <span data-ttu-id="f0b32-164">Permitir que o parâmetro nomeado especificado explicitamente substitua o mesmo no nivelamento de tabela de hash (nº 13162)</span><span class="sxs-lookup"><span data-stu-id="f0b32-164">Allow explicitly specified named parameter to supersede the same one from hashtable splatting (#13162)</span></span>

  <span data-ttu-id="f0b32-165">Com essa alteração, os parâmetros nomeados do nivelamento são movidos para o final da lista de parâmetros. Dessa maneira, eles ficam associados após todos os parâmetros nomeados especificados serem explicitamente associados.</span><span class="sxs-lookup"><span data-stu-id="f0b32-165">With this change, the named parameters from splatting are moved to the end of the parameter list so that they are bound after all explicitly specified named parameters are bound.</span></span> <span data-ttu-id="f0b32-166">A associação de parâmetros para funções simples não gera erros quando um parâmetro nomeado especificado não pode ser encontrado.</span><span class="sxs-lookup"><span data-stu-id="f0b32-166">Parameter binding for simple functions doesn't throw an error when a specified named parameter cannot be found.</span></span> <span data-ttu-id="f0b32-167">Parâmetros nomeados desconhecidos são associados ao parâmetro `$args` da função simples.</span><span class="sxs-lookup"><span data-stu-id="f0b32-167">Unknown named parameters are bound to the `$args` parameter of the simple function.</span></span> <span data-ttu-id="f0b32-168">Mover o nivelamento para o final da lista de argumentos altera a ordem em que os parâmetros aparecem em `$args`.</span><span class="sxs-lookup"><span data-stu-id="f0b32-168">Moving splatting to the end of the argument list changes the order the parameters appears in `$args`.</span></span>

  <span data-ttu-id="f0b32-169">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f0b32-169">For example:</span></span>

  ```powershell
  function SimpleTest {
      param(
          $Name,
          $Path
      )
      "Name: $Name; Path: $Path; Args: $args"
  }
  ```

  <span data-ttu-id="f0b32-170">No comportamento anterior, **MyPath** não está associado a `-Path` porque está em terceiro na lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="f0b32-170">In the previous behavior, **MyPath** is not bound to `-Path` because it's the third argument in the argument list.</span></span> <span data-ttu-id="f0b32-171">## Por isso, é colocado em '$args' junto com `Blah = "World"`.</span><span class="sxs-lookup"><span data-stu-id="f0b32-171">## So it ends up being stuffed into '$args' along with `Blah = "World"`</span></span>

  ```powershell
  PS> $hash = @{ Name = "Hello"; Blah = "World" }
  PS> SimpleTest @hash "MyPath"
  Name: Hello; Path: ; Args: -Blah: World MyPath
  ```

  <span data-ttu-id="f0b32-172">Com essa alteração, os argumentos de `@hash` são movidos para o final da lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="f0b32-172">With this change, the arguments from `@hash` are moved to the end of the argument list.</span></span> <span data-ttu-id="f0b32-173">**MyPath** se torna o primeiro argumento na lista, portanto, associado a `-Path`.</span><span class="sxs-lookup"><span data-stu-id="f0b32-173">**MyPath** becomes the first argument in the list, so it is bound to `-Path`.</span></span>

  ```powershell
  PS> SimpleTest @hash "MyPath"
  Name: Hello; Path: MyPath; Args: -Blah: World
  ```

- <span data-ttu-id="f0b32-174">Tornar o parâmetro de opção `-Qualifier` não posicional para `Split-Path` ([nº 12960](https://github.com/PowerShell/PowerShell/pull/12960)) (Obrigado, @yecril71pl!)</span><span class="sxs-lookup"><span data-stu-id="f0b32-174">Make the switch parameter `-Qualifier` not positional for `Split-Path` ([#12960](https://github.com/PowerShell/PowerShell/pull/12960)) (Thanks @yecril71pl!)</span></span>

- <span data-ttu-id="f0b32-175">Resolver o diretório de trabalho como caminho literal para `Start-Process` quando ele não é especificado ([nº 11946](https://github.com/PowerShell/PowerShell/pull/11946)) (Obrigado, @NoMoreFood!)</span><span class="sxs-lookup"><span data-stu-id="f0b32-175">Resolve the working directory as literal path for `Start-Process` when it's not specified ([#11946](https://github.com/PowerShell/PowerShell/pull/11946)) (Thanks @NoMoreFood!)</span></span>

- <span data-ttu-id="f0b32-176">Fazer o parâmetro `-OutFile` nos cmdlets da Web funcionar como `-LiteralPath` ([nº 11701](https://github.com/PowerShell/PowerShell/pull/11701)) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="f0b32-176">Make `-OutFile` parameter in web cmdlets to work like `-LiteralPath` ([#11701](https://github.com/PowerShell/PowerShell/pull/11701)) (Thanks @iSazonov!)</span></span>

- <span data-ttu-id="f0b32-177">Corrigir a associação de parâmetro de cadeia de caracteres para literais numéricos `BigInteger` ([nº 11634](https://github.com/PowerShell/PowerShell/pull/11634)) (Obrigado, @vexx32!)</span><span class="sxs-lookup"><span data-stu-id="f0b32-177">Fix string parameter binding for `BigInteger` numeric literals ([#11634](https://github.com/PowerShell/PowerShell/pull/11634)) (Thanks @vexx32!)</span></span>

- <span data-ttu-id="f0b32-178">No Windows, `Start-Process` cria um ambiente de processo com todas as variáveis de ambiente da sessão atual. Usar `-UseNewEnvironment` cria um ambiente de processo padrão ([nº 10830](https://github.com/PowerShell/PowerShell/pull/10830)) (Obrigado, @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="f0b32-178">On Windows, `Start-Process` creates a process environment with all the environment variables from current session, using `-UseNewEnvironment` creates a new default process environment ([#10830](https://github.com/PowerShell/PowerShell/pull/10830)) (Thanks @iSazonov!)</span></span>

- <span data-ttu-id="f0b32-179">Não encapsular o resultado de retorno para `PSObject` ao converter `ScriptBlock` para um delegado ([nº 10619](https://github.com/PowerShell/PowerShell/pull/10619))</span><span class="sxs-lookup"><span data-stu-id="f0b32-179">Do not wrap return result in `PSObject` when converting a `ScriptBlock` to a delegate ([#10619](https://github.com/PowerShell/PowerShell/pull/10619))</span></span>

  <span data-ttu-id="f0b32-180">Quando um `ScriptBlock` é convertido em um tipo delegado a ser usado no contexto de C#, encapsulando o resultado em um `PSObject`, gera problemas desnecessários:</span><span class="sxs-lookup"><span data-stu-id="f0b32-180">When a `ScriptBlock` is converted to a delegate type to be used in C# context, wrapping the result in a `PSObject` brings unneeded troubles:</span></span>

  - <span data-ttu-id="f0b32-181">Quando o valor é convertido no tipo de retorno delegado, o `PSObject` é essencialmente desencapsulado.</span><span class="sxs-lookup"><span data-stu-id="f0b32-181">When the value is converted to the delegate return type, the `PSObject` essentially gets unwrapped.</span></span> <span data-ttu-id="f0b32-182">Portanto, o `PSObject` é desnecessário.</span><span class="sxs-lookup"><span data-stu-id="f0b32-182">So the `PSObject` is unneeded.</span></span>
  - <span data-ttu-id="f0b32-183">Quando o tipo de retorno delegado é `object`, é encapsulado em um `PSObject`, tornando difícil trabalhar com ele em código C#.</span><span class="sxs-lookup"><span data-stu-id="f0b32-183">When the delegate return type is `object`, it gets wrapped in a `PSObject` making it hard to work with in C# code.</span></span>

  <span data-ttu-id="f0b32-184">Após essa alteração, o objeto retornado será o objeto subjacente.</span><span class="sxs-lookup"><span data-stu-id="f0b32-184">After this change, the returned object is the underlying object.</span></span>
