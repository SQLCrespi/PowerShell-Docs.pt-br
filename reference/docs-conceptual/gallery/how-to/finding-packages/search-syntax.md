---
ms.date: 06/12/2017
contributor: JKeithB
keywords: galeria,powershell,cmdlet,psgallery
title: Sintaxe de pesquisa da Galeria
ms.openlocfilehash: aabcaa1f1b5b641ab5033c9ba2e358477c84a23b
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "71328447"
---
# <a name="gallery-search-syntax"></a><span data-ttu-id="3fd4f-103">Sintaxe de pesquisa da Galeria</span><span class="sxs-lookup"><span data-stu-id="3fd4f-103">Gallery Search Syntax</span></span>

<span data-ttu-id="3fd4f-104">Você pode pesquisar a Galeria do PowerShell usando o [site da Galeria do PowerShell](https://www.powershellgallery.com/).</span><span class="sxs-lookup"><span data-stu-id="3fd4f-104">You can search the PowerShell Gallery using the [PowerShell Gallery's web site](https://www.powershellgallery.com/).</span></span>
<span data-ttu-id="3fd4f-105">O site da Galeria do PowerShell oferece uma caixa de pesquisa de texto em que você pode usar palavras, frases e expressões de palavra-chave para refinar os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="3fd4f-105">PowerShell Gallery web site offers a text searchbox where you can use words, phrases and keyword expressions to narrow down search results.</span></span>

## <a name="search-by-keywords"></a><span data-ttu-id="3fd4f-106">Pesquisa com palavras-chave</span><span class="sxs-lookup"><span data-stu-id="3fd4f-106">Search by Keywords</span></span>

    dsc azure sql

<span data-ttu-id="3fd4f-107">A pesquisa tenta encontrar documentos relevantes contendo as três palavras-chave e retorna os documentos correspondentes.</span><span class="sxs-lookup"><span data-stu-id="3fd4f-107">Search attempts to find relevant documents containing all 3 keywords, and return matching documents.</span></span>

## <a name="search-using-phrases-and-keywords"></a><span data-ttu-id="3fd4f-108">Pesquisa usando frases e palavras-chave</span><span class="sxs-lookup"><span data-stu-id="3fd4f-108">Search using Phrases and keywords</span></span>

    "azure sql" deployment

<span data-ttu-id="3fd4f-109">Inserir uma frase entre aspas ("") altera a pesquisa para procurar pela frase específica, em vez de palavras-chave separadas.</span><span class="sxs-lookup"><span data-stu-id="3fd4f-109">Entering a phrase between quotation marks ("") change the search to look for the particular phrase instead of separate keywords.</span></span>
<span data-ttu-id="3fd4f-110">Documentos correspondentes normalmente devem conter exatamente a frase "azure sql", incluindo variações nas maiúsculas e minúsculas, como "Azure SQL" e geralmente também contêm a palavra “deployment".</span><span class="sxs-lookup"><span data-stu-id="3fd4f-110">Matching documents should usually contain the exact phrase "azure sql", including variations on capitalization e.g. "Azure SQL", and also usually contain the word 'deployment'.</span></span>

## <a name="filtering-on-fields"></a><span data-ttu-id="3fd4f-111">Filtrando pelos campos</span><span class="sxs-lookup"><span data-stu-id="3fd4f-111">Filtering on fields</span></span>

<span data-ttu-id="3fd4f-112">Você pode pesquisar pela ID de um pacote específico (ou "Id" ou "id") ou por alguns outros campos, prefixando os termos de pesquisa com o nome do campo.</span><span class="sxs-lookup"><span data-stu-id="3fd4f-112">You can search for a specific package ID (or 'Id' or 'id'), or certain other fields by prefixing search terms with the field name.</span></span>

<span data-ttu-id="3fd4f-113">Atualmente, os campos pesquisáveis são "Id", "Version", "Tags", "Author", "Owner", "Functions", "Cmdlets", "DscResources" e "PowerShellVersion".</span><span class="sxs-lookup"><span data-stu-id="3fd4f-113">Currently the searchable fields are 'Id', 'Version', 'Tags', 'Author', 'Owner', 'Functions', 'Cmdlets', 'DscResources' and 'PowerShellVersion'.</span></span>

<span data-ttu-id="3fd4f-114">[Qual é a diferença entre o título e a ID?</span><span class="sxs-lookup"><span data-stu-id="3fd4f-114">[What's the difference between ID and Title?</span></span> <span data-ttu-id="3fd4f-115">ID é o nome que você usa no console.</span><span class="sxs-lookup"><span data-stu-id="3fd4f-115">ID is the name you use in the console.</span></span> <span data-ttu-id="3fd4f-116">O título é mostrado na parte superior da página do pacote nos resultados da pesquisa.]</span><span class="sxs-lookup"><span data-stu-id="3fd4f-116">Title is what is shown at the top of the package page in search results.]</span></span>

## <a name="examples"></a><span data-ttu-id="3fd4f-117">Exemplos</span><span class="sxs-lookup"><span data-stu-id="3fd4f-117">Examples</span></span>

    ID:PSReadline
    
<span data-ttu-id="3fd4f-118">Localiza pacotes com uma ID que contém "PSReadline".</span><span class="sxs-lookup"><span data-stu-id="3fd4f-118">finds packages with an ID containing "PSReadline".</span></span>

    Id:"AzureRM.Profile"

<span data-ttu-id="3fd4f-119">é outra maneira de localizar pacotes com "AzureRM.Profile" no campo de ID.</span><span class="sxs-lookup"><span data-stu-id="3fd4f-119">is another way to find packages with "AzureRM.Profile" in their ID field.</span></span>

<span data-ttu-id="3fd4f-120">O filtro "Id" é correspondente a uma subcadeia, de modo que se pesquisar pelo seguinte:</span><span class="sxs-lookup"><span data-stu-id="3fd4f-120">The 'Id' filter is a substring match, so if you search for the following:</span></span>

    Id:"azure"

<span data-ttu-id="3fd4f-121">Isso fornece resultados que incluem 'AzureRM.Profile' e 'Azure.Storage'.</span><span class="sxs-lookup"><span data-stu-id="3fd4f-121">This provides results that include AzureRM.Profile' and 'Azure.Storage'.</span></span>

<span data-ttu-id="3fd4f-122">Você também pode pesquisar por várias palavras-chave em um único campo.</span><span class="sxs-lookup"><span data-stu-id="3fd4f-122">You can also search for multiple keywords in a single field.</span></span> 

    id:azure tags:intellisense

<span data-ttu-id="3fd4f-123">E você pode fazer pesquisas por frase usando aspas duplas:</span><span class="sxs-lookup"><span data-stu-id="3fd4f-123">And you can perform phrase searches using double quotes:</span></span>

    id:"azure.storage"

<span data-ttu-id="3fd4f-124">Para pesquisar todos os pacotes com a marca DSC.</span><span class="sxs-lookup"><span data-stu-id="3fd4f-124">To search all packages with DSC tag.</span></span>

    Tags:DSC

<span data-ttu-id="3fd4f-125">Para pesquisar todos os pacotes com a função especificada.</span><span class="sxs-lookup"><span data-stu-id="3fd4f-125">To search all packages with the specified function.</span></span>

    Functions:Get-TreeSize

<span data-ttu-id="3fd4f-126">Para pesquisar todos os pacotes com o cmdlet especificado.</span><span class="sxs-lookup"><span data-stu-id="3fd4f-126">To search all packages with the specified cmdlet.</span></span>

    Cmdlets:Get-AzureRmEnvironment

<span data-ttu-id="3fd4f-127">Para pesquisar todos os pacotes com o nome do Recurso de DSC especificado.</span><span class="sxs-lookup"><span data-stu-id="3fd4f-127">To search all packages with the specified DSC Resource name.</span></span>

    DscResources:xArchive

<span data-ttu-id="3fd4f-128">Para pesquisar todos os pacotes com o PowerShellVersion especificado</span><span class="sxs-lookup"><span data-stu-id="3fd4f-128">To search all packages with the specified PowerShellVersion</span></span>

    PowerShellVersion:2.0

<span data-ttu-id="3fd4f-129">Por fim, se você usar um campo para o qual não há suporte, como "commands", vamos ignorá-lo e pesquisar em todos os campos.</span><span class="sxs-lookup"><span data-stu-id="3fd4f-129">Finally, if you use a field we don't support, such as 'commands', we'll just ignore it and search all the fields.</span></span> <span data-ttu-id="3fd4f-130">Sendo assim, a seguinte consulta</span><span class="sxs-lookup"><span data-stu-id="3fd4f-130">So the following query</span></span>

    commands:blobs storage

<span data-ttu-id="3fd4f-131">É interpretada exatamente como esta consulta:</span><span class="sxs-lookup"><span data-stu-id="3fd4f-131">Is interpreted exactly the same as this query:</span></span>

    blobs storage
