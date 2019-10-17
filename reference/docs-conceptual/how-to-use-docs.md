---
ms.date: 09/25/2019
keywords: powershell, cmdlet
title: Como usar a documentação do PowerShell
ms.openlocfilehash: 9e3d5828d6bdb4ef14701994f146354a041efaea
ms.sourcegitcommit: a80bb79b85deab8ae3c21de56d1ee432fdd92628
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/11/2019
ms.locfileid: "72281643"
---
# <a name="how-to-use-the-powershell-documentation"></a><span data-ttu-id="11f0e-103">Como usar a documentação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="11f0e-103">How to use the PowerShell documentation</span></span>

<span data-ttu-id="11f0e-104">Bem-vindo à documentação online do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11f0e-104">Welcome to the PowerShell online documentation.</span></span> <span data-ttu-id="11f0e-105">Este site contém a referência de cmdlet para as seguintes versões do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="11f0e-105">This site contains cmdlet reference for the following versions of PowerShell:</span></span>

- <span data-ttu-id="11f0e-106">PowerShell 7 (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="11f0e-106">PowerShell 7 (preview)</span></span>
- <span data-ttu-id="11f0e-107">PowerShell 6</span><span class="sxs-lookup"><span data-stu-id="11f0e-107">PowerShell 6</span></span>
- <span data-ttu-id="11f0e-108">PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="11f0e-108">PowerShell 5.1</span></span>
- <span data-ttu-id="11f0e-109">PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="11f0e-109">PowerShell 5.0</span></span>
- <span data-ttu-id="11f0e-110">PowerShell 4.0</span><span class="sxs-lookup"><span data-stu-id="11f0e-110">PowerShell 4.0</span></span>
- <span data-ttu-id="11f0e-111">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="11f0e-111">PowerShell 3.0</span></span>

## <a name="selecting-your-version"></a><span data-ttu-id="11f0e-112">Selecionar a versão</span><span class="sxs-lookup"><span data-stu-id="11f0e-112">Selecting your version</span></span>

<span data-ttu-id="11f0e-113">Por padrão, o site exibe a documentação da última versão lançada do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11f0e-113">By default, this site displays documentation for the latest released version of PowerShell.</span></span> <span data-ttu-id="11f0e-114">Alguns cmdlets funcionam de modo diferente em várias versões do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11f0e-114">Some cmdlets work differently in various versions of PowerShell.</span></span> <span data-ttu-id="11f0e-115">Verifique se você está visualizando a documentação da versão do PowerShell que está usando.</span><span class="sxs-lookup"><span data-stu-id="11f0e-115">Be sure you are viewing the documentation for the version of PowerShell you are using.</span></span>

<span data-ttu-id="11f0e-116">Use o seletor de versão na parte superior da página para selecionar a versão desejada do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11f0e-116">Use the version picker at the top of the page to select the version of PowerShell you want.</span></span>

![seletor de versão](images/how-to-use-docs/picker-vall.gif)

<span data-ttu-id="11f0e-118">Para verificar a versão do PowerShell que você está usando, inspecione o valor `$PSversionTable.PSVersion`.</span><span class="sxs-lookup"><span data-stu-id="11f0e-118">You can verify the version of PowerShell you are using by inspecting the `$PSversionTable.PSVersion` value.</span></span> <span data-ttu-id="11f0e-119">O exemplo a seguir mostra a saída do Windows PowerShell v5.1.</span><span class="sxs-lookup"><span data-stu-id="11f0e-119">The following example shows the output for Windows PowerShell v5.1.</span></span>

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      18362  145
```

## <a name="searching-for-articles"></a><span data-ttu-id="11f0e-120">Pesquisar artigos</span><span class="sxs-lookup"><span data-stu-id="11f0e-120">Searching for articles</span></span>

<span data-ttu-id="11f0e-121">Há duas maneiras de pesquisar conteúdo nos docs. A mais simples é usar a caixa de filtro abaixo do seletor de versão.</span><span class="sxs-lookup"><span data-stu-id="11f0e-121">There are two ways to search for content in Docs. The simplest way is to use the filter box under the version selector.</span></span> <span data-ttu-id="11f0e-122">Basta inserir uma palavra que aparece no título de um artigo.</span><span class="sxs-lookup"><span data-stu-id="11f0e-122">Just enter a word that appears in the title of an article.</span></span> <span data-ttu-id="11f0e-123">A página exibe uma lista de artigos correspondentes.</span><span class="sxs-lookup"><span data-stu-id="11f0e-123">The page displays a list of matching articles.</span></span> <span data-ttu-id="11f0e-124">Também é possível selecionar a opção de pesquisar todo o site com base nessa lista.</span><span class="sxs-lookup"><span data-stu-id="11f0e-124">You can also select the option to search the entire site from that list.</span></span>

![caixa de filtro](images/how-to-use-docs/filter-search.gif)
