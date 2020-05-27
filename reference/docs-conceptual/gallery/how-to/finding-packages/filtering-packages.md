---
ms.date: 06/12/2017
contributor: JKeithB
keywords: galeria,powershell,cmdlet,psgallery
title: Filtrando resultados da pesquisa
ms.openlocfilehash: 51f8d243cb9b1f4ff7413eec8839697299e8dd52
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83691469"
---
# <a name="filtering-search-results"></a><span data-ttu-id="34543-103">Filtrando resultados da pesquisa</span><span class="sxs-lookup"><span data-stu-id="34543-103">Filtering search results</span></span>

<span data-ttu-id="34543-104">A [guia Pacotes](https://www.powershellgallery.com/packages) exibe todos os pacotes disponíveis na Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34543-104">The [Packages tab](https://www.powershellgallery.com/packages) displays all available packages in the PowerShell Gallery.</span></span>

<span data-ttu-id="34543-105">Há várias maneiras de filtrar, classificar e pesquisar os pacotes.</span><span class="sxs-lookup"><span data-stu-id="34543-105">There are several ways to filter, sort, and search the packages.</span></span>
<span data-ttu-id="34543-106">Para ver mais detalhes sobre um pacote específico, clique nele.</span><span class="sxs-lookup"><span data-stu-id="34543-106">To see more details about a particular package, click the package.</span></span>

## <a name="filter-by"></a><span data-ttu-id="34543-107">Filtrar Por</span><span class="sxs-lookup"><span data-stu-id="34543-107">Filter By</span></span>

<span data-ttu-id="34543-108">O menu suspenso em "Filtrar Por" permite aos usuários filtrar os resultados por:</span><span class="sxs-lookup"><span data-stu-id="34543-108">The drop-down under "Filter By" allows users to filter the results by:</span></span>

- <span data-ttu-id="34543-109">Incluir pré-lançamento</span><span class="sxs-lookup"><span data-stu-id="34543-109">Include Prerelease</span></span>
- <span data-ttu-id="34543-110">Apenas estável</span><span class="sxs-lookup"><span data-stu-id="34543-110">Stable Only</span></span>

<span data-ttu-id="34543-111">Para saber mais sobre itens de "pré-lançamento" e "estáveis", confira o artigo [Prerelease Versioning Added to PowerShellGet and PowerShell Gallery](https://blogs.msdn.microsoft.com/powershell/2017/12/05/prerelease-versioning-added-to-powershellget-and-powershell-gallery/) (Controle de versão de pré-lançamento adicionado ao PowerShellGet e à Galeria do PowerShell), no blog da equipe do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34543-111">For information about "Prerelease" and "Stable", see [Prerelease Versioning Added to PowerShellGet and PowerShell Gallery](https://blogs.msdn.microsoft.com/powershell/2017/12/05/prerelease-versioning-added-to-powershellget-and-powershell-gallery/) in the PowerShell Team Blog.</span></span>

<span data-ttu-id="34543-112">Com as caixas de seleção no menu suspenso, os usuários podem filtrar os resultados por:</span><span class="sxs-lookup"><span data-stu-id="34543-112">The checkboxes under the drop-down allow users to filter the results by:</span></span>

- <span data-ttu-id="34543-113">Tipos de Pacote</span><span class="sxs-lookup"><span data-stu-id="34543-113">Package Types</span></span>
  - <span data-ttu-id="34543-114">Módulo</span><span class="sxs-lookup"><span data-stu-id="34543-114">Module</span></span>
  - <span data-ttu-id="34543-115">Script</span><span class="sxs-lookup"><span data-stu-id="34543-115">Script</span></span>
- <span data-ttu-id="34543-116">Categorias</span><span class="sxs-lookup"><span data-stu-id="34543-116">Categories</span></span>
  - <span data-ttu-id="34543-117">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="34543-117">Cmdlet</span></span>
  - <span data-ttu-id="34543-118">Recurso de DSC</span><span class="sxs-lookup"><span data-stu-id="34543-118">DSC Resource</span></span>
  - <span data-ttu-id="34543-119">Função</span><span class="sxs-lookup"><span data-stu-id="34543-119">Function</span></span>
  - <span data-ttu-id="34543-120">Capacidade da função</span><span class="sxs-lookup"><span data-stu-id="34543-120">Role Capability</span></span>
  - <span data-ttu-id="34543-121">Fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="34543-121">Workflow</span></span>

<span data-ttu-id="34543-122">Para ver somente módulos na Galeria do PowerShell, marque a opção Módulo nos Tipos de Pacote.</span><span class="sxs-lookup"><span data-stu-id="34543-122">To see only modules in the PowerShell Gallery, check Module in the Package Types.</span></span>
<span data-ttu-id="34543-123">Da mesma forma, para ver somente scripts na Galeria do PowerShell, marque a opção Script nos Tipos de Pacote.</span><span class="sxs-lookup"><span data-stu-id="34543-123">Similarly, to see only scripts in the PowerShell Gallery, check Script in the Package Types.</span></span>

> [!NOTE]
> <span data-ttu-id="34543-124">Os filtros são inclusivos.</span><span class="sxs-lookup"><span data-stu-id="34543-124">Filters are inclusive.</span></span>
> <span data-ttu-id="34543-125">Exemplo: um pacote que contém cmdlets e funções será exibido se Cmdlet ou Função (ou ambos) estiverem marcados.</span><span class="sxs-lookup"><span data-stu-id="34543-125">Example: A package containing both cmdlets and functions will appear if either Cmdlet or Function (or both) are checked.</span></span>
> <span data-ttu-id="34543-126">Se nenhum dos dois for selecionado, o pacote não será exibido.</span><span class="sxs-lookup"><span data-stu-id="34543-126">If neither are selected, the package will not appear.</span></span>
> <span data-ttu-id="34543-127">De forma semelhante, se todas as categorias forem selecionadas, apenas pacotes que contêm uma dessas categorias serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="34543-127">Similarly, if all categories are selected, only packages containing one of those categories will appear.</span></span>
> <span data-ttu-id="34543-128">**Pacotes que não pertencem a nenhuma dessas categorias não serão exibidos.**</span><span class="sxs-lookup"><span data-stu-id="34543-128">**Packages that do not belong to any of those categories will not appear.**</span></span>

## <a name="sort-by"></a><span data-ttu-id="34543-129">Classificar Por</span><span class="sxs-lookup"><span data-stu-id="34543-129">Sort By</span></span>

<span data-ttu-id="34543-130">O menu suspenso Classificar Por permite aos usuários classificar os resultados por:</span><span class="sxs-lookup"><span data-stu-id="34543-130">The Sort By drop-down allows users to sort the results by:</span></span>

- <span data-ttu-id="34543-131">Popularidade – a popularidade é determinada pela Contagem de Downloads</span><span class="sxs-lookup"><span data-stu-id="34543-131">Popularity - Popularity is determined by Download Count</span></span>
- <span data-ttu-id="34543-132">A a Z – em ordem alfabética por nome do pacote</span><span class="sxs-lookup"><span data-stu-id="34543-132">A-Z - Alphabetically by package name</span></span>
- <span data-ttu-id="34543-133">Recentes – os pacotes aparecem na ordem da data de publicação</span><span class="sxs-lookup"><span data-stu-id="34543-133">Recent - Packages appear in order of publish date</span></span>

## <a name="search-box"></a><span data-ttu-id="34543-134">Caixa de Pesquisa</span><span class="sxs-lookup"><span data-stu-id="34543-134">Search Box</span></span>

<span data-ttu-id="34543-135">A Caixa de Pesquisa permite que os usuários pesquisem pacotes por palavras-chave.</span><span class="sxs-lookup"><span data-stu-id="34543-135">The Search Box allows users to search the packages on keywords.</span></span>
<span data-ttu-id="34543-136">Para saber mais, confira [Sintaxe de Pesquisa da Galeria](search-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="34543-136">For more information, see [Gallery Search Syntax](search-syntax.md).</span></span>
