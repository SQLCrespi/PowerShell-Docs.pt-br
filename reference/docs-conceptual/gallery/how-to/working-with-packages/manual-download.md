---
ms.date: 09/11/2018
contributor: JKeithB
keywords: galeria, powershell, psgallery
title: Download manual do pacote
ms.openlocfilehash: c0a96e866dfd27f9b2170ea540ec6dd0c67701fd
ms.sourcegitcommit: 4a2cf30351620a58ba95ff5d76b247e601907589
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71327887"
---
# <a name="manual-package-download"></a><span data-ttu-id="e70d6-103">Download manual do pacote</span><span class="sxs-lookup"><span data-stu-id="e70d6-103">Manual Package Download</span></span>

<span data-ttu-id="e70d6-104">Na Galeria do PowerShell, é possível baixar um pacote diretamente do site, sem usar os cmdlets PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="e70d6-104">The PowerShell Gallery supports downloading a package from the website directly, without using the PowerShellGet cmdlets.</span></span> <span data-ttu-id="e70d6-105">Você pode baixar qualquer pacote como um arquivo de pacote do NuGet (`.nupkg`), que pode, em seguida, ser copiado para um repositório interno.</span><span class="sxs-lookup"><span data-stu-id="e70d6-105">You can download any package as a NuGet package (`.nupkg`) file, which you can then copy to an internal repository.</span></span>

> [!NOTE]
> <span data-ttu-id="e70d6-106">O download manual do pacote **não** serve para substituir o cmdlet `Install-Module`.</span><span class="sxs-lookup"><span data-stu-id="e70d6-106">Manual package download is **not** intended as a replacement for the `Install-Module` cmdlet.</span></span>
> <span data-ttu-id="e70d6-107">Baixar o pacote não instala o módulo ou script.</span><span class="sxs-lookup"><span data-stu-id="e70d6-107">Downloading the package doesn't install the module or script.</span></span> <span data-ttu-id="e70d6-108">As dependências não estão incluídas no pacote NuGet baixado.</span><span class="sxs-lookup"><span data-stu-id="e70d6-108">Dependencies aren't included in the NuGet package downloaded.</span></span> <span data-ttu-id="e70d6-109">As instruções a seguir são fornecidas apenas para referência.</span><span class="sxs-lookup"><span data-stu-id="e70d6-109">The following instructions are provided for reference purposes only.</span></span>

## <a name="using-manual-download-to-acquire-a-package"></a><span data-ttu-id="e70d6-110">Usar o download manual para adquirir um pacote</span><span class="sxs-lookup"><span data-stu-id="e70d6-110">Using manual download to acquire a package</span></span>

<span data-ttu-id="e70d6-111">Cada página tem um link para Download Manual, conforme mostrado aqui:</span><span class="sxs-lookup"><span data-stu-id="e70d6-111">Each page has a link for Manual Download, as shown here:</span></span>

![Download manual](../../Images/packagedisplaypagewithpseditions.png)

<span data-ttu-id="e70d6-113">Para baixar manualmente, clique em **Baixar o arquivo nupkg bruto**.</span><span class="sxs-lookup"><span data-stu-id="e70d6-113">To download manually, click on **Download the raw nupkg file**.</span></span> <span data-ttu-id="e70d6-114">Uma cópia do pacote é copiada para a pasta de download do navegador com o nome `<name>.<version>.nupkg`.</span><span class="sxs-lookup"><span data-stu-id="e70d6-114">A copy of the package is copied to the download folder for your browser with the name `<name>.<version>.nupkg`.</span></span>

<span data-ttu-id="e70d6-115">Um pacote do NuGet é um arquivo ZIP com os arquivos extras com informações sobre o conteúdo do pacote.</span><span class="sxs-lookup"><span data-stu-id="e70d6-115">A NuGet package is a ZIP archive with extra files containing information about the contents of the package.</span></span> <span data-ttu-id="e70d6-116">Alguns navegadores, como o Internet Explorer, substituem automaticamente a extensão de arquivo `.nupkg` por `.zip`.</span><span class="sxs-lookup"><span data-stu-id="e70d6-116">Some browsers, like Internet Explorer, automatically replace the `.nupkg` file extension with `.zip`.</span></span> <span data-ttu-id="e70d6-117">Para expandir o pacote, renomeie o arquivo `.nupkg` como `.zip`, se necessário. Em seguida, extraia o conteúdo para uma pasta local.</span><span class="sxs-lookup"><span data-stu-id="e70d6-117">To expand the package, rename the `.nupkg` file to `.zip`, if needed, then extract the contents to a local folder.</span></span>

<span data-ttu-id="e70d6-118">Um arquivo de pacote do NuGet inclui os seguintes **elementos específicos do NuGet** que não fazem parte do código original empacotado:</span><span class="sxs-lookup"><span data-stu-id="e70d6-118">A NuGet package file includes the following **NuGet-specific elements** that aren't part of the original packaged code:</span></span>

- <span data-ttu-id="e70d6-119">Uma pasta chamada `_rels`: contém um arquivo `.rels` que lista as dependências</span><span class="sxs-lookup"><span data-stu-id="e70d6-119">A folder named `_rels` - contains a `.rels` file that lists the dependencies</span></span>
- <span data-ttu-id="e70d6-120">Uma pasta chamada `package`: contém os dados específicos do NuGet</span><span class="sxs-lookup"><span data-stu-id="e70d6-120">A folder named `package` - contains the NuGet-specific data</span></span>
- <span data-ttu-id="e70d6-121">Um arquivo chamado `[Content_Types].xml`: descreve como as extensões como PowerShellGet funcionam com o NuGet</span><span class="sxs-lookup"><span data-stu-id="e70d6-121">A file named `[Content_Types].xml` - describes how extensions like PowerShellGet work with NuGet</span></span>
- <span data-ttu-id="e70d6-122">Um arquivo chamado `<name>.nuspec`: contém a maior parte dos metadados</span><span class="sxs-lookup"><span data-stu-id="e70d6-122">A file named `<name>.nuspec` - contains the bulk of the metadata</span></span>

## <a name="installing-powershell-modules-from-a-nuget-package"></a><span data-ttu-id="e70d6-123">Instalar módulos do PowerShell de um pacote do NuGet</span><span class="sxs-lookup"><span data-stu-id="e70d6-123">Installing PowerShell modules from a NuGet package</span></span>

> [!NOTE]
> <span data-ttu-id="e70d6-124">Estas instruções **NÃO** apresentam o mesmo resultado de executar `Install-Module`.</span><span class="sxs-lookup"><span data-stu-id="e70d6-124">These instructions **DO NOT** give the same result as running `Install-Module`.</span></span> <span data-ttu-id="e70d6-125">Estas instruções atendem aos requisitos mínimos.</span><span class="sxs-lookup"><span data-stu-id="e70d6-125">These instructions fulfill the minimum requirements.</span></span> <span data-ttu-id="e70d6-126">Elas não servem como substituição para `Install-Module`.</span><span class="sxs-lookup"><span data-stu-id="e70d6-126">They aren't intended to be a replacement for `Install-Module`.</span></span>
> <span data-ttu-id="e70d6-127">Algumas etapas executadas pelo `Install-Module` não estão incluídas.</span><span class="sxs-lookup"><span data-stu-id="e70d6-127">Some steps performed by `Install-Module` aren't included.</span></span>

<span data-ttu-id="e70d6-128">A abordagem mais fácil é remover os elementos específicos do NuGet da pasta.</span><span class="sxs-lookup"><span data-stu-id="e70d6-128">The easiest approach is to remove the NuGet-specific elements from the folder.</span></span> <span data-ttu-id="e70d6-129">Remover os elementos deixa o código do PowerShell criado pelo autor do pacote.</span><span class="sxs-lookup"><span data-stu-id="e70d6-129">Removing the elements leaves the PowerShell code created by the package author.</span></span>
<span data-ttu-id="e70d6-130">Para obter a lista de elementos específicos do NuGet, confira [Usar o download manual para adquirir um pacote](#using-manual-download-to-acquire-a-package).</span><span class="sxs-lookup"><span data-stu-id="e70d6-130">For the list of NuGet-specific elements, see [Using manual download to acquire a package](#using-manual-download-to-acquire-a-package).</span></span>

<span data-ttu-id="e70d6-131">As etapas são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="e70d6-131">The steps are as follows:</span></span>

1. <span data-ttu-id="e70d6-132">Extrair o conteúdo do pacote do NuGet em uma pasta local.</span><span class="sxs-lookup"><span data-stu-id="e70d6-132">Extract the contents of the NuGet package to a local folder.</span></span>
2. <span data-ttu-id="e70d6-133">Exclua os elementos específicos do NuGet da pasta.</span><span class="sxs-lookup"><span data-stu-id="e70d6-133">Delete the NuGet-specific elements from the folder.</span></span>
3. <span data-ttu-id="e70d6-134">Renomear a pasta.</span><span class="sxs-lookup"><span data-stu-id="e70d6-134">Rename the folder.</span></span> <span data-ttu-id="e70d6-135">Normalmente, o nome de pasta padrão é `<name>.<version>`.</span><span class="sxs-lookup"><span data-stu-id="e70d6-135">The default folder name is usually `<name>.<version>`.</span></span> <span data-ttu-id="e70d6-136">A versão poderá incluir `-prerelease` se o módulo estiver marcado como uma versão de pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="e70d6-136">The version can include `-prerelease` if the module is tagged as a prerelease version.</span></span> <span data-ttu-id="e70d6-137">Renomeie a pasta somente com o nome do módulo.</span><span class="sxs-lookup"><span data-stu-id="e70d6-137">Rename the folder to just the module name.</span></span> <span data-ttu-id="e70d6-138">Por exemplo, `azurerm.storage.5.0.4-preview` torna-se `azurerm.storage`.</span><span class="sxs-lookup"><span data-stu-id="e70d6-138">For example, `azurerm.storage.5.0.4-preview` becomes `azurerm.storage`.</span></span>
4. <span data-ttu-id="e70d6-139">Copie a pasta para uma das pastas no `$env:PSModulePath value`.</span><span class="sxs-lookup"><span data-stu-id="e70d6-139">Copy the folder to one of the folders in the `$env:PSModulePath value`.</span></span> <span data-ttu-id="e70d6-140">`$env:PSModulePath` é um conjunto de caminhos delimitados por ponto e vírgula no qual o PowerShell deve procurar os módulos.</span><span class="sxs-lookup"><span data-stu-id="e70d6-140">`$env:PSModulePath` is a semicolon-delimited set of paths in which PowerShell should look for modules.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e70d6-141">O download manual não inclui nenhuma dependência exigida pelo módulo.</span><span class="sxs-lookup"><span data-stu-id="e70d6-141">The manual download doesn't include any dependencies required by the module.</span></span> <span data-ttu-id="e70d6-142">Se o pacote tiver dependências, elas precisarão ser instaladas no sistema para que esse módulo funcione corretamente.</span><span class="sxs-lookup"><span data-stu-id="e70d6-142">If the package has dependencies, they must be installed on the system for this module to work correctly.</span></span> <span data-ttu-id="e70d6-143">A Galeria do PowerShell mostra todas as dependências exigidas pelo pacote.</span><span class="sxs-lookup"><span data-stu-id="e70d6-143">The PowerShell Gallery shows all dependencies required by the package.</span></span>

## <a name="installing-powershell-scripts-from-a-nuget-package"></a><span data-ttu-id="e70d6-144">Instalar scripts do PowerShell de um pacote do NuGet</span><span class="sxs-lookup"><span data-stu-id="e70d6-144">Installing PowerShell scripts from a NuGet package</span></span>

> [!NOTE]
> <span data-ttu-id="e70d6-145">Estas instruções **NÃO** apresentam o mesmo resultado de executar `Install-Script`.</span><span class="sxs-lookup"><span data-stu-id="e70d6-145">These instructions **DO NOT** give the same result as running `Install-Script`.</span></span> <span data-ttu-id="e70d6-146">Estas instruções atendem aos requisitos mínimos.</span><span class="sxs-lookup"><span data-stu-id="e70d6-146">These instructions fulfill the minimum requirements.</span></span> <span data-ttu-id="e70d6-147">Elas não servem como substituição para `Install-Script`.</span><span class="sxs-lookup"><span data-stu-id="e70d6-147">They aren't intended to be a replacement for `Install-Script`.</span></span>

<span data-ttu-id="e70d6-148">A abordagem mais fácil é extrair o pacote do NuGet e, em seguida, usar o script diretamente.</span><span class="sxs-lookup"><span data-stu-id="e70d6-148">The easiest approach is to extract the NuGet package, then use the script directly.</span></span>

<span data-ttu-id="e70d6-149">As etapas são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="e70d6-149">The steps are as follows:</span></span>

1. <span data-ttu-id="e70d6-150">Extrair o conteúdo do pacote do NuGet.</span><span class="sxs-lookup"><span data-stu-id="e70d6-150">Extract the contents of the NuGet package.</span></span>
2. <span data-ttu-id="e70d6-151">O arquivo `.PS1` na pasta pode ser usado diretamente desse local.</span><span class="sxs-lookup"><span data-stu-id="e70d6-151">The `.PS1` file in the folder can be used directly from this location.</span></span>
3. <span data-ttu-id="e70d6-152">Você pode excluir os elementos específicos do NuGet da pasta.</span><span class="sxs-lookup"><span data-stu-id="e70d6-152">You may delete the NuGet-specific elements in the folder.</span></span>

<span data-ttu-id="e70d6-153">Para obter a lista de elementos específicos do NuGet, confira [Usar o download manual para adquirir um pacote](#using-manual-download-to-acquire-a-package).</span><span class="sxs-lookup"><span data-stu-id="e70d6-153">For the list of NuGet-specific elements, see [Using manual download to acquire a package](#using-manual-download-to-acquire-a-package).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e70d6-154">O download manual não inclui nenhuma dependência exigida pelo módulo.</span><span class="sxs-lookup"><span data-stu-id="e70d6-154">The manual download doesn't include any dependencies required by the module.</span></span> <span data-ttu-id="e70d6-155">Se o pacote tiver dependências, elas precisarão ser instaladas no sistema para que esse módulo funcione corretamente.</span><span class="sxs-lookup"><span data-stu-id="e70d6-155">If the package has dependencies, they must be installed on the system for this module to work correctly.</span></span> <span data-ttu-id="e70d6-156">A Galeria do PowerShell mostra todas as dependências exigidas pelo pacote.</span><span class="sxs-lookup"><span data-stu-id="e70d6-156">The PowerShell Gallery shows all dependencies required by the package.</span></span>
