---
title: Ciclo de vida de suporte do PowerShell Core
description: Políticas que regem o suporte ao PowerShell Core
ms.date: 08/06/2018
ms.openlocfilehash: b8dd4891ecf245b87c3fe2fa61cd241a12209b57
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65854370"
---
# <a name="powershell-core-support-lifecycle"></a><span data-ttu-id="c2346-103">Ciclo de vida de suporte do PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="c2346-103">PowerShell Core Support Lifecycle</span></span>

<span data-ttu-id="c2346-104">O PowerShell Core é um conjunto distinto de ferramentas e componentes que é enviado, instalado e configurado separadamente do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c2346-104">PowerShell Core is a distinct set of tools and components that is shipped, installed, and configured separately from Windows PowerShell.</span></span>
<span data-ttu-id="c2346-105">Portanto, o PowerShell Core não está incluído nos contratos de licenciamento do Windows 7/8.1/10 ou Windows Server.</span><span class="sxs-lookup"><span data-stu-id="c2346-105">So, PowerShell Core is not included in the Windows 7/8.1/10 or Windows Server licensing agreements.</span></span>

<span data-ttu-id="c2346-106">No entanto, o PowerShell Core é aceito pelos tradicionais contratos de suporte da Microsoft, incluindo [Premier][], [Microsoft Enterprise Agreement][enterprise-agreement] e [Microsoft Software Assurance][assurance].</span><span class="sxs-lookup"><span data-stu-id="c2346-106">However, PowerShell Core is supported under traditional Microsoft support agreements, including [Premier][], [Microsoft Enterprise Agreements][enterprise-agreement], and [Microsoft Software Assurance][assurance].</span></span>
<span data-ttu-id="c2346-107">Você também pode pagar por [suporte assistido][] do PowerShell Core preenchendo uma solicitação de suporte para o seu problema.</span><span class="sxs-lookup"><span data-stu-id="c2346-107">You can also pay for [assisted support][] for PowerShell Core by filing a support request for your problem.</span></span>

## <a name="community-support"></a><span data-ttu-id="c2346-108">Suporte da comunidade</span><span class="sxs-lookup"><span data-stu-id="c2346-108">Community Support</span></span>

<span data-ttu-id="c2346-109">Oferecemos também [suporte da comunidade][] no GitHub, no qual você pode registrar um problema, um bug ou uma solicitação de recurso.</span><span class="sxs-lookup"><span data-stu-id="c2346-109">We also offer [community support][] on GitHub where you can file an issue, bug, or feature request.</span></span>
<span data-ttu-id="c2346-110">Além disso, você pode encontrar ajuda de outros membros da comunidade na [Microsoft Community][] geral ou na Microsoft [Comunidade tecnológica do PowerShell][].</span><span class="sxs-lookup"><span data-stu-id="c2346-110">Also, you may find help from other members of the community on the general [Microsoft Community][] or the Microsoft [PowerShell Tech Community][].</span></span>
<span data-ttu-id="c2346-111">Não oferecemos nenhuma garantia de que a comunidade atenderá ou resolverá seu problema de maneira oportuna.</span><span class="sxs-lookup"><span data-stu-id="c2346-111">We offer no guarantee there that the community will address or resolve your issue in a timely manner.</span></span>
<span data-ttu-id="c2346-112">Se você tiver um problema que requer atenção imediata, use as opções tradicionais de suporte pago.</span><span class="sxs-lookup"><span data-stu-id="c2346-112">If you have a problem that requires immediate attention, you should use the traditional, paid support options.</span></span>

## <a name="lifecycle-of-powershell-core"></a><span data-ttu-id="c2346-113">Ciclo de vida do PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="c2346-113">Lifecycle of PowerShell Core</span></span>

<span data-ttu-id="c2346-114">O PowerShell Core está adotando a [política de ciclo de vida moderna da Microsoft][modern].</span><span class="sxs-lookup"><span data-stu-id="c2346-114">PowerShell Core is adopting the [Microsoft Modern Lifecycle Policy][modern].</span></span>
<span data-ttu-id="c2346-115">Esse ciclo de vida do suporte destina-se a manter os clientes atualizados com as versões mais recentes.</span><span class="sxs-lookup"><span data-stu-id="c2346-115">This support lifecycle is intended to keep customers up-to-date with the latest versions.</span></span>

<span data-ttu-id="c2346-116">A ramificação da versão 6.x do PowerShell Core será atualizada aproximadamente a cada seis meses (por exemplo: 6.0, 6.1, 6.2 etc.)</span><span class="sxs-lookup"><span data-stu-id="c2346-116">The version 6.x branch of PowerShell Core will be updated approximately once every six months (examples: 6.0, 6.1, 6.2, etc.)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c2346-117">Você deve atualizar em seis meses após cada novo lançamento de versão secundária para continuar a receber suporte.</span><span class="sxs-lookup"><span data-stu-id="c2346-117">You must update within six months after each new minor version release to continue receiving support.</span></span>

<span data-ttu-id="c2346-118">Por exemplo, se o PowerShell Core 6.1 for liberado em 1º de julho de 2018, espera-se que você atualize para o PowerShell Core 6.1 até 1º de janeiro de 2019 para manter o suporte.</span><span class="sxs-lookup"><span data-stu-id="c2346-118">For example, if PowerShell Core 6.1 is released on July 1, 2018, you would be expected to update to PowerShell Core 6.1 by January 1, 2019 to maintain support.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c2346-119">Você deve atualizar em 30 dias após cada novo lançamento de versão de patch para continuar a receber suporte.</span><span class="sxs-lookup"><span data-stu-id="c2346-119">You must update within 30 days after each new patch version release to continue receiving support.</span></span>

<span data-ttu-id="c2346-120">Por exemplo, se você estiver executando o PowerShell Core 6.1 e o 6.1.3 foi lançado em 19 de fevereiro de 2019, é esperado que você atualize para o PowerShell Core 6.1.3 até 21 de março de 2019, que é 30 dias após o lançamento para manter o suporte.</span><span class="sxs-lookup"><span data-stu-id="c2346-120">For example, If you are running PowerShell Core 6.1 and 6.1.3 was released on February 19, 2019, you would be expected to update to PowerShell Core 6.1.3 by March 21, 2019, which is 30 days after the release to maintain support.</span></span>
<span data-ttu-id="c2346-121">Se qualquer correção for considerada necessária, ela será lançada na nossa próxima atualização cumulativa.</span><span class="sxs-lookup"><span data-stu-id="c2346-121">If any fixes are found to be required, the fixes will be released in our next cumulative update.</span></span>

<span data-ttu-id="c2346-122">A política de ciclo de vida moderna também requer que a Microsoft forneça aos clientes um aviso 12 meses antes de interromper o suporte para um produto (ou seja, o PowerShell Core).</span><span class="sxs-lookup"><span data-stu-id="c2346-122">The Modern Lifecycle Policy also requires that Microsoft give customers 12 months notice before discontinuing support for a product (that is, PowerShell Core).</span></span>

<span data-ttu-id="c2346-123">Por fim, esperamos que o PowerShell Core adote a abordagem de "manutenção de longo prazo".</span><span class="sxs-lookup"><span data-stu-id="c2346-123">Eventually, we expect PowerShell Core will adopt the "long-term servicing" approach.</span></span>
<span data-ttu-id="c2346-124">Nessa abordagem de manutenção, exigiríamos apenas que as atualizações de serviço e segurança permanecessem em suporte em um branch/versão específica do 6.x.</span><span class="sxs-lookup"><span data-stu-id="c2346-124">In this servicing approach, we would require only servicing and security updates to stay in support on a specific branch/version of 6.x.</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="c2346-125">Plataformas com suporte</span><span class="sxs-lookup"><span data-stu-id="c2346-125">Supported platforms</span></span>

<span data-ttu-id="c2346-126">Na tabela a seguir, veja qual plataforma da versão do PowerShell Core que você está usando tem suporte oficial.</span><span class="sxs-lookup"><span data-stu-id="c2346-126">The following table to see what platform the version of PowerShell Core you are using is officially supported.</span></span>

<span data-ttu-id="c2346-127">Nossa comunidade também contribuiu com pacotes para algumas plataformas, mas eles não têm suporte oficial.</span><span class="sxs-lookup"><span data-stu-id="c2346-127">Our community has also contributed packages for some platforms, but they are not officially supported.</span></span>
<span data-ttu-id="c2346-128">Esses pacotes são marcados como `Community` na tabela.</span><span class="sxs-lookup"><span data-stu-id="c2346-128">These packages are marked as `Community` in the table.</span></span>

<span data-ttu-id="c2346-129">As plataformas listadas como `Experimental` não têm suporte oficialmente, mas estão disponíveis para experimentação e comentários.</span><span class="sxs-lookup"><span data-stu-id="c2346-129">Platforms listed as `Experimental` are not officially supported, but are available for experimentation and feedback.</span></span>

|                                                   | <span data-ttu-id="c2346-130">6.1</span><span class="sxs-lookup"><span data-stu-id="c2346-130">6.1</span></span>         | <span data-ttu-id="c2346-131">6.2</span><span class="sxs-lookup"><span data-stu-id="c2346-131">6.2</span></span>         |
|---------------------------------------------------|:-----------:|:-----------:|
| <span data-ttu-id="c2346-132">Windows 7, 8.1 e 10</span><span class="sxs-lookup"><span data-stu-id="c2346-132">Windows 7, 8.1, and 10</span></span>                            | <span data-ttu-id="c2346-133">Suportado</span><span class="sxs-lookup"><span data-stu-id="c2346-133">Supported</span></span>   | <span data-ttu-id="c2346-134">Suportado</span><span class="sxs-lookup"><span data-stu-id="c2346-134">Supported</span></span>   |
| <span data-ttu-id="c2346-135">Windows Server 2008 R2, 2012 R2, 2016</span><span class="sxs-lookup"><span data-stu-id="c2346-135">Windows Server 2008 R2, 2012 R2, 2016</span></span>             | <span data-ttu-id="c2346-136">Suportado</span><span class="sxs-lookup"><span data-stu-id="c2346-136">Supported</span></span>   | <span data-ttu-id="c2346-137">Suportado</span><span class="sxs-lookup"><span data-stu-id="c2346-137">Supported</span></span>   |
| <span data-ttu-id="c2346-138">[Windows Server Canal Semestral][semi-annual]</span><span class="sxs-lookup"><span data-stu-id="c2346-138">[Windows Server Semi-Annual Channel][semi-annual]</span></span> | <span data-ttu-id="c2346-139">Suportado</span><span class="sxs-lookup"><span data-stu-id="c2346-139">Supported</span></span>   | <span data-ttu-id="c2346-140">Suportado</span><span class="sxs-lookup"><span data-stu-id="c2346-140">Supported</span></span>   |
| <span data-ttu-id="c2346-141">Ubuntu 16.04 e 18.04</span><span class="sxs-lookup"><span data-stu-id="c2346-141">Ubuntu 16.04 and 18.04</span></span>                            | <span data-ttu-id="c2346-142">Suportado</span><span class="sxs-lookup"><span data-stu-id="c2346-142">Supported</span></span>   | <span data-ttu-id="c2346-143">Suportado</span><span class="sxs-lookup"><span data-stu-id="c2346-143">Supported</span></span>   |
| <span data-ttu-id="c2346-144">Ubuntu 18.10 (por meio do pacote Snap)</span><span class="sxs-lookup"><span data-stu-id="c2346-144">Ubuntu 18.10 (via Snap Package)</span></span>                   | <span data-ttu-id="c2346-145">Comunidade</span><span class="sxs-lookup"><span data-stu-id="c2346-145">Community</span></span>   | <span data-ttu-id="c2346-146">Comunidade</span><span class="sxs-lookup"><span data-stu-id="c2346-146">Community</span></span>   |
| <span data-ttu-id="c2346-147">Debian 9</span><span class="sxs-lookup"><span data-stu-id="c2346-147">Debian 9</span></span>                                          | <span data-ttu-id="c2346-148">Suportado</span><span class="sxs-lookup"><span data-stu-id="c2346-148">Supported</span></span>   | <span data-ttu-id="c2346-149">Suportado</span><span class="sxs-lookup"><span data-stu-id="c2346-149">Supported</span></span>   |
| <span data-ttu-id="c2346-150">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="c2346-150">CentOS 7</span></span>                                          | <span data-ttu-id="c2346-151">Suportado</span><span class="sxs-lookup"><span data-stu-id="c2346-151">Supported</span></span>   | <span data-ttu-id="c2346-152">Suportado</span><span class="sxs-lookup"><span data-stu-id="c2346-152">Supported</span></span>   |
| <span data-ttu-id="c2346-153">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="c2346-153">Red Hat Enterprise Linux 7</span></span>                        | <span data-ttu-id="c2346-154">Suportado</span><span class="sxs-lookup"><span data-stu-id="c2346-154">Supported</span></span>   | <span data-ttu-id="c2346-155">Suportado</span><span class="sxs-lookup"><span data-stu-id="c2346-155">Supported</span></span>   |
| <span data-ttu-id="c2346-156">OpenSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="c2346-156">openSUSE 42.3</span></span>                                     | <span data-ttu-id="c2346-157">Suportado</span><span class="sxs-lookup"><span data-stu-id="c2346-157">Supported</span></span>   | <span data-ttu-id="c2346-158">Suportado</span><span class="sxs-lookup"><span data-stu-id="c2346-158">Supported</span></span>   |
| <span data-ttu-id="c2346-159">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="c2346-159">Fedora 28</span></span>                                         | <span data-ttu-id="c2346-160">Suportado</span><span class="sxs-lookup"><span data-stu-id="c2346-160">Supported</span></span>   | <span data-ttu-id="c2346-161">Suportado</span><span class="sxs-lookup"><span data-stu-id="c2346-161">Supported</span></span>   |
| <span data-ttu-id="c2346-162">macOS 10.12+</span><span class="sxs-lookup"><span data-stu-id="c2346-162">macOS 10.12+</span></span>                                      | <span data-ttu-id="c2346-163">Suportado</span><span class="sxs-lookup"><span data-stu-id="c2346-163">Supported</span></span>   | <span data-ttu-id="c2346-164">Suportado</span><span class="sxs-lookup"><span data-stu-id="c2346-164">Supported</span></span>   |
| <span data-ttu-id="c2346-165">Arch</span><span class="sxs-lookup"><span data-stu-id="c2346-165">Arch</span></span>                                              | <span data-ttu-id="c2346-166">Comunidade</span><span class="sxs-lookup"><span data-stu-id="c2346-166">Community</span></span>   | <span data-ttu-id="c2346-167">Comunidade</span><span class="sxs-lookup"><span data-stu-id="c2346-167">Community</span></span>   |
| <span data-ttu-id="c2346-168">Raspbian</span><span class="sxs-lookup"><span data-stu-id="c2346-168">Raspbian</span></span>                                          | <span data-ttu-id="c2346-169">Comunidade</span><span class="sxs-lookup"><span data-stu-id="c2346-169">Community</span></span>   | <span data-ttu-id="c2346-170">Comunidade</span><span class="sxs-lookup"><span data-stu-id="c2346-170">Community</span></span>   |
| <span data-ttu-id="c2346-171">Kali</span><span class="sxs-lookup"><span data-stu-id="c2346-171">Kali</span></span>                                              | <span data-ttu-id="c2346-172">Comunidade</span><span class="sxs-lookup"><span data-stu-id="c2346-172">Community</span></span>   | <span data-ttu-id="c2346-173">Comunidade</span><span class="sxs-lookup"><span data-stu-id="c2346-173">Community</span></span>   |
| <span data-ttu-id="c2346-174">AppImage (funciona em várias plataformas Linux)</span><span class="sxs-lookup"><span data-stu-id="c2346-174">AppImage  (works on multiple Linux platforms)</span></span>     | <span data-ttu-id="c2346-175">Comunidade</span><span class="sxs-lookup"><span data-stu-id="c2346-175">Community</span></span>   | <span data-ttu-id="c2346-176">Comunidade</span><span class="sxs-lookup"><span data-stu-id="c2346-176">Community</span></span>   |
| [<span data-ttu-id="c2346-177">Pacote Snap</span><span class="sxs-lookup"><span data-stu-id="c2346-177">Snap Package</span></span>](https://snapcraft.io/powershell)   | <span data-ttu-id="c2346-178">Consultar a observação</span><span class="sxs-lookup"><span data-stu-id="c2346-178">See note</span></span>    | <span data-ttu-id="c2346-179">Consultar a observação</span><span class="sxs-lookup"><span data-stu-id="c2346-179">See note</span></span>    |

> [!NOTE]
> <span data-ttu-id="c2346-180">Os pacotes de ajustes tem suporte da mesma forma que a distribuição na qual você está executando o pacote.</span><span class="sxs-lookup"><span data-stu-id="c2346-180">Snap packages are supported the same as the distribution you are running the package on.</span></span>

## <a name="powershell-release-end-of-life"></a><span data-ttu-id="c2346-181">Fim da vida útil da versão do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2346-181">PowerShell release end of life</span></span>

<span data-ttu-id="c2346-182">Com base no [Ciclo de vida do PowerShell Core](#lifecycle-of-powershell-core), a tabela a seguir lista as datas em que várias versões não terão mais suporte.</span><span class="sxs-lookup"><span data-stu-id="c2346-182">Based on [Lifecycle of PowerShell Core](#lifecycle-of-powershell-core), the following table lists the dates when various release will no longer be supported.</span></span>

| <span data-ttu-id="c2346-183">Versão</span><span class="sxs-lookup"><span data-stu-id="c2346-183">Version</span></span> | <span data-ttu-id="c2346-184">Fim da vida útil</span><span class="sxs-lookup"><span data-stu-id="c2346-184">End Of Life</span></span>                   |
|---------|-------------------------------|
| <span data-ttu-id="c2346-185">6.0</span><span class="sxs-lookup"><span data-stu-id="c2346-185">6.0</span></span>     | <span data-ttu-id="c2346-186">13 de fevereiro de 2019</span><span class="sxs-lookup"><span data-stu-id="c2346-186">February 13, 2019</span></span>             |
| <span data-ttu-id="c2346-187">6.1</span><span class="sxs-lookup"><span data-stu-id="c2346-187">6.1</span></span>     | <span data-ttu-id="c2346-188">28 de setembro de 2019</span><span class="sxs-lookup"><span data-stu-id="c2346-188">September 28, 2019</span></span>            |
| <span data-ttu-id="c2346-189">6.2</span><span class="sxs-lookup"><span data-stu-id="c2346-189">6.2</span></span>     | <span data-ttu-id="c2346-190">6 meses após 7 lançamentos</span><span class="sxs-lookup"><span data-stu-id="c2346-190">6 months after 7 releases</span></span>     |

## <a name="platforms-which-are-out-of-support"></a><span data-ttu-id="c2346-191">Plataformas que estão sem suporte</span><span class="sxs-lookup"><span data-stu-id="c2346-191">Platforms, which are out of support</span></span>

<span data-ttu-id="c2346-192">Quando uma versão de plataforma atingir o final da vida, conforme definido pelo proprietário da plataforma, o PowerShell Core também encerrará o suporte dessa versão de plataforma.</span><span class="sxs-lookup"><span data-stu-id="c2346-192">When a platform version reaches end-of-life as defined by the platform owner, PowerShell Core will also cease to support that platform version.</span></span>
<span data-ttu-id="c2346-193">Os pacotes liberados anteriormente continuarão disponíveis para clientes que precisam de acesso, mas suporte formal e atualizações de qualquer tipo não serão fornecidos.</span><span class="sxs-lookup"><span data-stu-id="c2346-193">Previously released packages will remain available for customers needing access but formal support and updates of any kind will no longer be provided.</span></span>

<span data-ttu-id="c2346-194">Portanto, os proprietários de distribuição finalizaram o suporte para as versões a seguir e não são suportadas.</span><span class="sxs-lookup"><span data-stu-id="c2346-194">So, the distribution owners ended support for the following versions and are not supported.</span></span>

| <span data-ttu-id="c2346-195">SO</span><span class="sxs-lookup"><span data-stu-id="c2346-195">OS</span></span>       | <span data-ttu-id="c2346-196">Versão</span><span class="sxs-lookup"><span data-stu-id="c2346-196">Version</span></span> | <span data-ttu-id="c2346-197">Fim de vida</span><span class="sxs-lookup"><span data-stu-id="c2346-197">End of Life</span></span>                                                                                 |
|----------|---------|---------------------------------------------------------------------------------------------|
| <span data-ttu-id="c2346-198">Fedora</span><span class="sxs-lookup"><span data-stu-id="c2346-198">Fedora</span></span>   | <span data-ttu-id="c2346-199">24</span><span class="sxs-lookup"><span data-stu-id="c2346-199">24</span></span>      | [<span data-ttu-id="c2346-200">Agosto de 2017</span><span class="sxs-lookup"><span data-stu-id="c2346-200">August 2017</span></span>](https://fedoramagazine.org/fedora-24-eol/)                                    |
| <span data-ttu-id="c2346-201">Fedora</span><span class="sxs-lookup"><span data-stu-id="c2346-201">Fedora</span></span>   | <span data-ttu-id="c2346-202">25</span><span class="sxs-lookup"><span data-stu-id="c2346-202">25</span></span>      | [<span data-ttu-id="c2346-203">Dezembro de 2017</span><span class="sxs-lookup"><span data-stu-id="c2346-203">December 2017</span></span>](https://fedoramagazine.org/fedora-25-end-life/)                             |
| <span data-ttu-id="c2346-204">Fedora</span><span class="sxs-lookup"><span data-stu-id="c2346-204">Fedora</span></span>   | <span data-ttu-id="c2346-205">26</span><span class="sxs-lookup"><span data-stu-id="c2346-205">26</span></span>      | [<span data-ttu-id="c2346-206">Maio de 2018</span><span class="sxs-lookup"><span data-stu-id="c2346-206">May 2018</span></span>](https://fedoramagazine.org/fedora-26-end-life/)                                  |
| <span data-ttu-id="c2346-207">openSUSE</span><span class="sxs-lookup"><span data-stu-id="c2346-207">openSUSE</span></span> | <span data-ttu-id="c2346-208">42.1</span><span class="sxs-lookup"><span data-stu-id="c2346-208">42.1</span></span>    | [<span data-ttu-id="c2346-209">Maio de 2017</span><span class="sxs-lookup"><span data-stu-id="c2346-209">May 2017</span></span>](https://lists.opensuse.org/opensuse-security-announce/2017-05/msg00053.html)     |
| <span data-ttu-id="c2346-210">openSUSE</span><span class="sxs-lookup"><span data-stu-id="c2346-210">openSUSE</span></span> | <span data-ttu-id="c2346-211">42.2</span><span class="sxs-lookup"><span data-stu-id="c2346-211">42.2</span></span>    | [<span data-ttu-id="c2346-212">Janeiro de 2018</span><span class="sxs-lookup"><span data-stu-id="c2346-212">January 2018</span></span>](https://lists.opensuse.org/opensuse-security-announce/2017-11/msg00066.html) |
| <span data-ttu-id="c2346-213">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="c2346-213">Ubuntu</span></span>   | <span data-ttu-id="c2346-214">16.10</span><span class="sxs-lookup"><span data-stu-id="c2346-214">16.10</span></span>   | [<span data-ttu-id="c2346-215">Julho de 2017</span><span class="sxs-lookup"><span data-stu-id="c2346-215">July 2017</span></span>](https://lists.ubuntu.com/archives/ubuntu-announce/2017-July/000223.html)        |
| <span data-ttu-id="c2346-216">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="c2346-216">Ubuntu</span></span>   | <span data-ttu-id="c2346-217">17.04</span><span class="sxs-lookup"><span data-stu-id="c2346-217">17.04</span></span>   | [<span data-ttu-id="c2346-218">Janeiro de 2018</span><span class="sxs-lookup"><span data-stu-id="c2346-218">January 2018</span></span>](https://lists.ubuntu.com/archives/ubuntu-announce/2018-January.txt)          |
| <span data-ttu-id="c2346-219">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="c2346-219">Ubuntu</span></span>   | <span data-ttu-id="c2346-220">17.10</span><span class="sxs-lookup"><span data-stu-id="c2346-220">17.10</span></span>   | [<span data-ttu-id="c2346-221">Julho de 2018</span><span class="sxs-lookup"><span data-stu-id="c2346-221">July 2018</span></span>](https://lists.ubuntu.com/archives/ubuntu-announce/2018-July/000232.html)        |
| <span data-ttu-id="c2346-222">Debian</span><span class="sxs-lookup"><span data-stu-id="c2346-222">Debian</span></span>   | <span data-ttu-id="c2346-223">8</span><span class="sxs-lookup"><span data-stu-id="c2346-223">8</span></span>       | [<span data-ttu-id="c2346-224">Junho de 2018</span><span class="sxs-lookup"><span data-stu-id="c2346-224">June 2018</span></span>](https://lists.debian.org/debian-security-announce/2018/msg00132.html)           |
| <span data-ttu-id="c2346-225">Fedora</span><span class="sxs-lookup"><span data-stu-id="c2346-225">Fedora</span></span>   | <span data-ttu-id="c2346-226">27</span><span class="sxs-lookup"><span data-stu-id="c2346-226">27</span></span>      | [<span data-ttu-id="c2346-227">Novembro de 2018</span><span class="sxs-lookup"><span data-stu-id="c2346-227">November 2018</span></span>](https://fedoramagazine.org/fedora-27-end-of-life/)                          |
| <span data-ttu-id="c2346-228">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="c2346-228">Ubuntu</span></span>   | <span data-ttu-id="c2346-229">14.04</span><span class="sxs-lookup"><span data-stu-id="c2346-229">14.04</span></span>   | [<span data-ttu-id="c2346-230">Abril de 2019</span><span class="sxs-lookup"><span data-stu-id="c2346-230">April 2019</span></span>](https://wiki.ubuntu.com/Releases)                                              |

## <a name="notes-on-licensing"></a><span data-ttu-id="c2346-231">Observações sobre o licenciamento</span><span class="sxs-lookup"><span data-stu-id="c2346-231">Notes on licensing</span></span>

<span data-ttu-id="c2346-232">O PowerShell Core foi lançado sob a [licença MIT][].</span><span class="sxs-lookup"><span data-stu-id="c2346-232">PowerShell Core is released under the [MIT license][].</span></span>
<span data-ttu-id="c2346-233">Sob essa licença e sem um contrato de suporte pago, os usuários estão limitados ao [suporte da comunidade][].</span><span class="sxs-lookup"><span data-stu-id="c2346-233">Under this license, and without a paid support agreement, users are limited to [community support][].</span></span>
<span data-ttu-id="c2346-234">Com o suporte da comunidade, a Microsoft não faz nenhuma garantia de capacidade de resposta ou correções.</span><span class="sxs-lookup"><span data-stu-id="c2346-234">With community support, Microsoft makes no guarantees of responsiveness or fixes.</span></span>

## <a name="windows-powershell-module"></a><span data-ttu-id="c2346-235">Módulo do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2346-235">Windows PowerShell Module</span></span>

<span data-ttu-id="c2346-236">O suporte para o PowerShell Core não inclui módulos do produto, a menos que esses módulos deem suporte explicitamente ao PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="c2346-236">Support for PowerShell Core does not include product modules, unless those modules explicitly support PowerShell Core.</span></span>
<span data-ttu-id="c2346-237">Por exemplo, usar o módulo `ActiveDirectory` fornecido como parte do Windows Server é um cenário sem suporte.</span><span class="sxs-lookup"><span data-stu-id="c2346-237">For example, using the `ActiveDirectory` module that ships as part of Windows Server is an unsupported scenario.</span></span>

<span data-ttu-id="c2346-238">No entanto, os módulos que não dão suporte explicitamente ao PowerShell Core podem ser compatíveis em alguns casos.</span><span class="sxs-lookup"><span data-stu-id="c2346-238">However, modules that do not explicitly support PowerShell Core may be compatible in some cases.</span></span>
<span data-ttu-id="c2346-239">Instalando o módulo [`WindowsPSModulePath`][], você pode adicionar o Windows PowerShell `PSModulePath` ao PowerShell Core `PSModulePath`.</span><span class="sxs-lookup"><span data-stu-id="c2346-239">By installing the [`WindowsPSModulePath`][] module, you can add the Windows PowerShell `PSModulePath` to your PowerShell Core `PSModulePath`.</span></span>

<span data-ttu-id="c2346-240">Primeiro, instale o módulo `WindowsPSModulePath` na Galeria do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c2346-240">First, install the `WindowsPSModulePath` module from the PowerShell Gallery:</span></span>

```powershell
# Add `-Scope CurrentUser` if you're installing as non-admin
Install-Module WindowsPSModulePath -Force
```

<span data-ttu-id="c2346-241">Depois de instalar esse módulo, execute o cmdlet `Add-WindowsPSModulePath` para adicionar o Windows PowerShell `PSModulePath` ao PowerShell Core:</span><span class="sxs-lookup"><span data-stu-id="c2346-241">After installing this module, run the `Add-WindowsPSModulePath` cmdlet to add the Windows PowerShell `PSModulePath` to PowerShell Core:</span></span>

```powershell
# Add this line to your profile if you always want Windows PowerShell PSModulePath
Add-WindowsPSModulePath
```

## <a name="experimental-features"></a><span data-ttu-id="c2346-242">Recursos experimentais</span><span class="sxs-lookup"><span data-stu-id="c2346-242">Experimental features</span></span>

<span data-ttu-id="c2346-243">Os [recursos experimentais][] estão limitados ao [suporte da comunidade](#community-support).</span><span class="sxs-lookup"><span data-stu-id="c2346-243">[Experimental features][] are limited to [community support](#community-support).</span></span>

[Premier]: https://www.microsoft.com/en-us/microsoftservices/support.aspx
[enterprise-agreement]: https://www.microsoft.com/en-us/licensing/licensing-programs/enterprise.aspx
[assurance]: https://www.microsoft.com/en-us/licensing/licensing-programs/software-assurance-default.aspx
[suporte da comunidade]: https://github.com/powershell/powershell/issues
[community support]: https://github.com/powershell/powershell/issues
[Microsoft Community]: https://answers.microsoft.com/
[Comunidade tecnológica do PowerShell]: https://techcommunity.microsoft.com/t5/PowerShell/ct-p/WindowsPowerShell
[PowerShell Tech Community]: https://techcommunity.microsoft.com/t5/PowerShell/ct-p/WindowsPowerShell
[suporte assistido]: https://support.microsoft.com/assistedsupportproducts
[assisted support]: https://support.microsoft.com/assistedsupportproducts
[modern]: https://support.microsoft.com/help/30881/modern-lifecycle-policy
[lifecycle-chart]: ./images/modern-lifecycle.png
[semi-annual]: https://docs.microsoft.com/windows-server/get-started/semi-annual-channel-overview
[licença MIT]: https://github.com/PowerShell/PowerShell/blob/master/LICENSE.txt
[MIT license]: https://github.com/PowerShell/PowerShell/blob/master/LICENSE.txt
[`WindowsPSModulePath`]: https://www.powershellgallery.com/packages/WindowsPSModulePath/
[Recursos experimentais]: /powershell/module/microsoft.powershell.core/about/about_powershell_config?view=powershell-6#experimentalfeatures
[Experimental features]: /powershell/module/microsoft.powershell.core/about/about_powershell_config?view=powershell-6#experimentalfeatures
