---
ms.date: 06/12/2017
contributor: JKeithB
keywords: galeria,powershell,cmdlet,psgallery
title: Introdução à Galeria do PowerShell
ms.openlocfilehash: c8beba3009e462ce52cdecd34fc0313d9234f289
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62084752"
---
# <a name="getting-started-with-the-powershell-gallery"></a><span data-ttu-id="79ff3-103">Introdução à Galeria do PowerShell</span><span class="sxs-lookup"><span data-stu-id="79ff3-103">Getting Started with the PowerShell Gallery</span></span>

<span data-ttu-id="79ff3-104">A Galeria do PowerShell é um repositório de pacotes contendo scripts, módulos e recursos DSC que você pode baixar e utilizar.</span><span class="sxs-lookup"><span data-stu-id="79ff3-104">The PowerShell Gallery is a package repository containing scripts, modules, and DSC resources you can download and leverage.</span></span> <span data-ttu-id="79ff3-105">Use os cmdlets no módulo do [PowerShell](/powershell/module/powershellget) para instalar os pacotes da Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="79ff3-105">You use the cmdlets in the [PowerShellGet](/powershell/module/powershellget) module to install packages from the PowerShell Gallery.</span></span> <span data-ttu-id="79ff3-106">Não é necessário entrar para baixar itens da Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="79ff3-106">You do not need to sign in to download items from the PowerShell Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="79ff3-107">É possível baixar o pacote diretamente da Galeria do PowerShell, mas essa não é uma abordagem recomendada.</span><span class="sxs-lookup"><span data-stu-id="79ff3-107">It is possible to download a package from the PowerShell Gallery directly, but this is not a recommended approach.</span></span>
> <span data-ttu-id="79ff3-108">Para saber mais detalhes, confira [Download manual do pacote](/powershell/gallery/how-to/working-with-packages/manual-download).</span><span class="sxs-lookup"><span data-stu-id="79ff3-108">For more details, see [Manual Package Download](/powershell/gallery/how-to/working-with-packages/manual-download).</span></span>

## <a name="discovering-packages-from-the-powershell-gallery"></a><span data-ttu-id="79ff3-109">Descobrir pacotes da Galeria do PowerShell</span><span class="sxs-lookup"><span data-stu-id="79ff3-109">Discovering packages from the PowerShell Gallery</span></span>

<span data-ttu-id="79ff3-110">É possível encontrar pacotes na Galeria do PowerShell usando o controle **Pesquisar** na [página inicial](https://www.powershellgallery.com) da Galeria do PowerShell ou navegando pelos Módulos e Scripts na [página Pacotes](https://www.powershellgallery.com/packages).</span><span class="sxs-lookup"><span data-stu-id="79ff3-110">You can find packages in the PowerShell Gallery by using the **Search** control on the PowerShell Gallery's [home page](https://www.powershellgallery.com), or by browsing through the Modules and Scripts from the [Packages page](https://www.powershellgallery.com/packages).</span></span> <span data-ttu-id="79ff3-111">Você pode também encontrar pacotes da Galeria do PowerShell executando os cmdlets [Find-Module][], [Find-DscResource] e [Find-Script][], dependendo do tipo de pacote, com `-Repository PSGallery`.</span><span class="sxs-lookup"><span data-stu-id="79ff3-111">You can also find packages from the PowerShell Gallery by running the [Find-Module][], [Find-DscResource], and [Find-Script][] cmdlets, depending on the package type, with `-Repository PSGallery`.</span></span>

<span data-ttu-id="79ff3-112">É possível filtrar os resultados da Galeria usando os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="79ff3-112">You can filter results from the Gallery by using the following parameters:</span></span>

- <span data-ttu-id="79ff3-113">Nome</span><span class="sxs-lookup"><span data-stu-id="79ff3-113">Name</span></span>
- <span data-ttu-id="79ff3-114">AllVersions</span><span class="sxs-lookup"><span data-stu-id="79ff3-114">AllVersions</span></span>
- <span data-ttu-id="79ff3-115">MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="79ff3-115">MinimumVersion</span></span>
- <span data-ttu-id="79ff3-116">RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="79ff3-116">RequiredVersion</span></span>
- <span data-ttu-id="79ff3-117">Tag</span><span class="sxs-lookup"><span data-stu-id="79ff3-117">Tag</span></span>
- <span data-ttu-id="79ff3-118">Includes</span><span class="sxs-lookup"><span data-stu-id="79ff3-118">Includes</span></span>
- <span data-ttu-id="79ff3-119">DscResource</span><span class="sxs-lookup"><span data-stu-id="79ff3-119">DscResource</span></span>
- <span data-ttu-id="79ff3-120">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="79ff3-120">RoleCapability</span></span>
- <span data-ttu-id="79ff3-121">Comando</span><span class="sxs-lookup"><span data-stu-id="79ff3-121">Command</span></span>
- <span data-ttu-id="79ff3-122">Filtro</span><span class="sxs-lookup"><span data-stu-id="79ff3-122">Filter</span></span>

<span data-ttu-id="79ff3-123">Caso tenha interesse apenas em descobrir recursos DSC específicos na Galeria, execute o cmdlet [Find-DscResource].</span><span class="sxs-lookup"><span data-stu-id="79ff3-123">If you're only interested in discovering specific DSC resources in the Gallery, you can run the [Find-DscResource] cmdlet.</span></span> <span data-ttu-id="79ff3-124">Find-DscResource retorna dados em recursos DSC contidos na Galeria.</span><span class="sxs-lookup"><span data-stu-id="79ff3-124">Find-DscResource returns data on DSC resources contained in the Gallery.</span></span>
<span data-ttu-id="79ff3-125">Como os recursos DSC sempre são fornecidos como parte de um módulo, você ainda precisa executar [Install-Module][] para instalar esses recursos.</span><span class="sxs-lookup"><span data-stu-id="79ff3-125">Because DSC resources are always delivered as part of a module, you still need to run [Install-Module][] to install those DSC resources.</span></span>

## <a name="learning-about-packages-in-the-powershell-gallery"></a><span data-ttu-id="79ff3-126">Aprender sobre itens na Galeria do PowerShell</span><span class="sxs-lookup"><span data-stu-id="79ff3-126">Learning about packages in the PowerShell Gallery</span></span>

<span data-ttu-id="79ff3-127">Depois de identificar um pacote no qual tem interesse, talvez você queira aprender mais sobre ele.</span><span class="sxs-lookup"><span data-stu-id="79ff3-127">Once you've identified a package that you're interested in, you may want to learn more about it.</span></span> <span data-ttu-id="79ff3-128">Você pode fazer isso examinando a página específica do pacote na Galeria.</span><span class="sxs-lookup"><span data-stu-id="79ff3-128">You can do this by examining that package's specific page on the Gallery.</span></span> <span data-ttu-id="79ff3-129">Nessa página, você poderá ver todos os metadados carregados com o pacote.</span><span class="sxs-lookup"><span data-stu-id="79ff3-129">On that page, you'll be able to see all of the metadata uploaded with the package.</span></span> <span data-ttu-id="79ff3-130">Esses metadados do pacote são fornecidos pelo autor dele e não são verificados pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="79ff3-130">This metadata is provided by the package's author, and is not verified by Microsoft.</span></span> <span data-ttu-id="79ff3-131">O Proprietário do pacote está intimamente ligado à conta da Galeria usada para publicar o pacote e é mais confiável do que o campo Autor.</span><span class="sxs-lookup"><span data-stu-id="79ff3-131">The Owner of the package is strongly tied to the Gallery account used to publish the package, and is more trustworthy than the Author field.</span></span>

<span data-ttu-id="79ff3-132">Se você descobrir que um pacote que acredita que não tenha sido publicado de boa fé, clique em **Relatar Abuso** na página do pacote.</span><span class="sxs-lookup"><span data-stu-id="79ff3-132">If you discover a package that you feel is not published in good faith, click **Report Abuse** on that package's page.</span></span>

<span data-ttu-id="79ff3-133">Se estiver executando [Find-Module][] ou [Find-Script][], você poderá exibir esses dados no objeto PSGetModuleInfo retornado.</span><span class="sxs-lookup"><span data-stu-id="79ff3-133">If you're running [Find-Module][] or [Find-Script][], you can view this data in the returned PSGetModuleInfo object.</span></span> <span data-ttu-id="79ff3-134">Por exemplo, executar `Find-Module -Name PSReadLine -Repository PSGallery |Get-Member`</span><span class="sxs-lookup"><span data-stu-id="79ff3-134">For example, running `Find-Module -Name PSReadLine -Repository PSGallery |Get-Member`</span></span>
<span data-ttu-id="79ff3-135">retorna dados sobre o módulo PSReadLine na Galeria.</span><span class="sxs-lookup"><span data-stu-id="79ff3-135">returns data on the PSReadLine module in the Gallery.</span></span>

## <a name="downloading-packages-from-the-powershell-gallery"></a><span data-ttu-id="79ff3-136">Baixar pacotes da Galeria do PowerShell</span><span class="sxs-lookup"><span data-stu-id="79ff3-136">Downloading packages from the PowerShell Gallery</span></span>

<span data-ttu-id="79ff3-137">Recomendamos o processo a seguir para baixar pacotes da Galeria do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="79ff3-137">We encourage the following process when downloading packages from the PowerShell Gallery:</span></span>

### <a name="inspect"></a><span data-ttu-id="79ff3-138">Inspecionar</span><span class="sxs-lookup"><span data-stu-id="79ff3-138">Inspect</span></span>

<span data-ttu-id="79ff3-139">Para baixar um pacote da Galeria para inspeção, execute o cmdlet [Save-Module][] ou [Save-Script][], dependendo do tipo de pacote.</span><span class="sxs-lookup"><span data-stu-id="79ff3-139">To download a package from the Gallery for inspection, run either the [Save-Module][] or [Save-Script][] cmdlet, depending on the package type.</span></span> <span data-ttu-id="79ff3-140">Isso permite que você salve o pacote localmente sem instalá-lo e inspecione o conteúdo do pacote.</span><span class="sxs-lookup"><span data-stu-id="79ff3-140">This lets you save the package locally without installing it, and inspect the package contents.</span></span> <span data-ttu-id="79ff3-141">Lembre-se de excluir o pacote salvo manualmente.</span><span class="sxs-lookup"><span data-stu-id="79ff3-141">Remember to delete the saved package manually.</span></span>

<span data-ttu-id="79ff3-142">Alguns desses pacotes são criados pela Microsoft e outros são criados pela comunidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="79ff3-142">Some of these packages are authored by Microsoft, and others are authored by the PowerShell community.</span></span>
<span data-ttu-id="79ff3-143">A Microsoft recomenda que você examine o conteúdo e o código dos pacotes nesta galeria antes da instalação.</span><span class="sxs-lookup"><span data-stu-id="79ff3-143">Microsoft recommends that you review the contents and code of packages on this gallery prior to installation.</span></span>

<span data-ttu-id="79ff3-144">Se você descobrir que um pacote que acredita que não tenha sido publicado de boa fé, clique em **Relatar Abuso** na página do pacote.</span><span class="sxs-lookup"><span data-stu-id="79ff3-144">If you discover a package that you feel is not published in good faith, click **Report Abuse** on that package's page.</span></span>

### <a name="install"></a><span data-ttu-id="79ff3-145">Instalar</span><span class="sxs-lookup"><span data-stu-id="79ff3-145">Install</span></span>

<span data-ttu-id="79ff3-146">Para instalar um pacote da Galeria para uso, execute o cmdlet [Install-Module][] ou [Install-Script][], dependendo do tipo de pacote.</span><span class="sxs-lookup"><span data-stu-id="79ff3-146">To install a package from the Gallery for use, run either the [Install-Module][] or [Install-Script][] cmdlet, depending on the package type.</span></span>

<span data-ttu-id="79ff3-147">[Install-Module][] instala o módulo em `$env:ProgramFiles\WindowsPowerShell\Modules` por padrão.</span><span class="sxs-lookup"><span data-stu-id="79ff3-147">[Install-Module][] installs the module to `$env:ProgramFiles\WindowsPowerShell\Modules` by default.</span></span>
<span data-ttu-id="79ff3-148">Isso requer uma conta de administrador.</span><span class="sxs-lookup"><span data-stu-id="79ff3-148">This requires an administrator account.</span></span> <span data-ttu-id="79ff3-149">Se você adicionar o parâmetro `-Scope CurrentUser`, o módulo será instalado em `$env:USERPROFILE\Documents\WindowsPowerShell\Modules`.</span><span class="sxs-lookup"><span data-stu-id="79ff3-149">If you add the `-Scope CurrentUser` parameter, the module is installed to `$env:USERPROFILE\Documents\WindowsPowerShell\Modules` .</span></span>

<span data-ttu-id="79ff3-150">[Install-Script][] instala o script em `$env:ProgramFiles\WindowsPowerShell\Scripts` por padrão.</span><span class="sxs-lookup"><span data-stu-id="79ff3-150">[Install-Script][] installs the script to `$env:ProgramFiles\WindowsPowerShell\Scripts` by default.</span></span>
<span data-ttu-id="79ff3-151">Isso requer uma conta de administrador.</span><span class="sxs-lookup"><span data-stu-id="79ff3-151">This requires an administrator account.</span></span> <span data-ttu-id="79ff3-152">Se você adicionar o parâmetro `-Scope CurrentUser`, o script será instalado em `$env:USERPROFILE\Documents\WindowsPowerShell\Scripts`.</span><span class="sxs-lookup"><span data-stu-id="79ff3-152">If you add the `-Scope CurrentUser` parameter, the script is installed to `$env:USERPROFILE\Documents\WindowsPowerShell\Scripts` .</span></span>

<span data-ttu-id="79ff3-153">Por padrão, [Install-Module][] e [Install-Script][] instalam a versão mais recente de um pacote.</span><span class="sxs-lookup"><span data-stu-id="79ff3-153">By default, [Install-Module][] and [Install-Script][] installs the most current version of a package.</span></span>
<span data-ttu-id="79ff3-154">Para instalar uma versão mais antiga do pacote, adicione o parâmetro `-RequiredVersion`.</span><span class="sxs-lookup"><span data-stu-id="79ff3-154">To install an older version of the package, add the `-RequiredVersion` parameter.</span></span>

### <a name="deploy"></a><span data-ttu-id="79ff3-155">Implantar</span><span class="sxs-lookup"><span data-stu-id="79ff3-155">Deploy</span></span>

<span data-ttu-id="79ff3-156">Para implantar um pacote da Galeria do PowerShell na Automação do Azure, clique em **Automação do Azure** e, em seguida, em **Implantar na Automação do Azure** na página de detalhes do pacote.</span><span class="sxs-lookup"><span data-stu-id="79ff3-156">To deploy a package from the PowerShell Gallery to Azure Automation, click **Azure Automation**, then click **Deploy to Azure Automation** on the package details page.</span></span> <span data-ttu-id="79ff3-157">Você é redirecionado ao Portal de Gerenciamento do Azure, onde entra usando suas credenciais da conta do Azure.</span><span class="sxs-lookup"><span data-stu-id="79ff3-157">You are redirected to the Azure Management Portal where you sign in by using your Azure account credentials.</span></span> <span data-ttu-id="79ff3-158">Observe que implantar pacotes com dependências implanta todas as dependências da Automação do Azure.</span><span class="sxs-lookup"><span data-stu-id="79ff3-158">Note that deploying packages with dependencies deploys all the dependencies to Azure Automation.</span></span> <span data-ttu-id="79ff3-159">O botão "Implantar na Automação do Azure" pode ser desabilitado adicionando a marca **AzureAutomationNotSupported** aos metadados do pacote.</span><span class="sxs-lookup"><span data-stu-id="79ff3-159">The 'Deploy to Azure Automation' button can be disabled by adding the **AzureAutomationNotSupported** tag to your package metadata.</span></span>

<span data-ttu-id="79ff3-160">Para saber mais sobre a Automação do Azure, confira a documentação da [Automação do Azure](/azure/automation).</span><span class="sxs-lookup"><span data-stu-id="79ff3-160">To learn more about Azure Automation, see the [Azure Automation](/azure/automation) documentation.</span></span>

## <a name="updating-packages-from-the-powershell-gallery"></a><span data-ttu-id="79ff3-161">Atualizar pacotes da Galeria do PowerShell</span><span class="sxs-lookup"><span data-stu-id="79ff3-161">Updating packages from the PowerShell Gallery</span></span>

<span data-ttu-id="79ff3-162">Para atualizar pacotes instalados usando a Galeria do PowerShell, execute o cmdlet [Update-Module][] ou [Update-Script][].</span><span class="sxs-lookup"><span data-stu-id="79ff3-162">To update packages installed from the PowerShell Gallery, run either the [Update-Module][] or [Update-Script][] cmdlet.</span></span> <span data-ttu-id="79ff3-163">Quando executado sem parâmetros adicionais, [Update-Module][] tenta atualizar todos os módulos instalados executando [Install-Module][].</span><span class="sxs-lookup"><span data-stu-id="79ff3-163">When run without any additional parameters, [Update-Module][] attempts to update all modules installed by running [Install-Module][].</span></span> <span data-ttu-id="79ff3-164">Para atualizar os módulos seletivamente, adicione o parâmetro `-Name`.</span><span class="sxs-lookup"><span data-stu-id="79ff3-164">To selectively update modules, add the `-Name` parameter.</span></span> 

<span data-ttu-id="79ff3-165">Da mesma forma, quando executado sem parâmetros adicionais, [Update-Script][] também tenta atualizar todos os scripts instalados executando [Install-Script][].</span><span class="sxs-lookup"><span data-stu-id="79ff3-165">Similarly, when run without any additional parameters, [Update-Script][] also attempts to update all scripts installed by running [Install-Script][].</span></span> <span data-ttu-id="79ff3-166">Para atualizar os scripts seletivamente, adicione o parâmetro `-Name`.</span><span class="sxs-lookup"><span data-stu-id="79ff3-166">To selectively update scripts, add the `-Name` parameter.</span></span>

## <a name="list-packages-that-you-have-installed-from-the-powershell-gallery"></a><span data-ttu-id="79ff3-167">Listar pacotes que você instalou da Galeria do PowerShell</span><span class="sxs-lookup"><span data-stu-id="79ff3-167">List packages that you have installed from the PowerShell Gallery</span></span>

<span data-ttu-id="79ff3-168">Para descobrir quais módulos você instalou da Galeria do PowerShell, execute o cmdlet [Get-InstalledModule][].</span><span class="sxs-lookup"><span data-stu-id="79ff3-168">To find out which modules you have installed from the PowerShell Gallery, run the [Get-InstalledModule][] cmdlet.</span></span> <span data-ttu-id="79ff3-169">Esse comando lista todos os módulos no seu sistema que foram instalados diretamente da Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="79ff3-169">This command lists all of the modules you have on your system that were installed directly from the PowerShell Gallery.</span></span>

<span data-ttu-id="79ff3-170">De forma semelhante, para descobrir quais scripts você instalou da Galeria do PowerShell, execute o cmdlet [Get-InstalledScript][].</span><span class="sxs-lookup"><span data-stu-id="79ff3-170">Similarly, to find out which scripts you have installed from the PowerShell Gallery, run the [Get-InstalledScript][] cmdlet.</span></span> <span data-ttu-id="79ff3-171">Esse comando lista todos os scripts no seu sistema que foram instalados diretamente da Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="79ff3-171">This command lists all of the scripts you have on your system that were installed directly from the PowerShell Gallery.</span></span>

[Find-DscResource]: /powershell/module/powershellget/Find-DscResource
[Find-Module]: /powershell/module/powershellget/Find-Module
[Find-Script]: /powershell/module/powershellget/Find-Script
[Get-InstalledModule]: /powershell/module/powershellget/Get-InstalledModule
[Get-InstalledScript]: /powershell/module/powershellget/Get-InstalledScript
[Install-Module]: /powershell/module/powershellget/Install-Module
[Install-Script]: /powershell/module/powershellget/Install-Script
[Publish-Module]: /powershell/module/powershellget/Publish-Module
[Publish-Script]: /powershell/module/powershellget/Publish-Script
[Register-PSRepository]: /powershell/module/powershellget/Register-Repository
[Save-Module]: /powershell/module/powershellget/Save-Module
[Save-Script]: /powershell/module/powershellget/Save-Script
