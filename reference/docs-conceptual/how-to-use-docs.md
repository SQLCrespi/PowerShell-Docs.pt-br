---
ms.date: 07/29/2020
keywords: powershell, cmdlet
title: Como usar a documentação do PowerShell
ms.openlocfilehash: 1cfeb9eea564e7618062e1b8ada4948bd9e22969
ms.sourcegitcommit: 9f9eb95bc859e9e0fed48101327a602b2ced351d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87821522"
---
# <a name="how-to-use-the-powershell-documentation"></a><span data-ttu-id="434f1-103">Como usar a documentação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="434f1-103">How to use the PowerShell documentation</span></span>

<span data-ttu-id="434f1-104">Bem-vindo à documentação online do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="434f1-104">Welcome to the PowerShell online documentation.</span></span> <span data-ttu-id="434f1-105">Este site contém a referência de cmdlet para as seguintes versões do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="434f1-105">This site contains cmdlet reference for the following versions of PowerShell:</span></span>

- <span data-ttu-id="434f1-106">PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="434f1-106">PowerShell 7</span></span>
- <span data-ttu-id="434f1-107">PowerShell 6</span><span class="sxs-lookup"><span data-stu-id="434f1-107">PowerShell 6</span></span>
- <span data-ttu-id="434f1-108">PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="434f1-108">PowerShell 5.1</span></span>

## <a name="finding-articles-and-selecting-a-version"></a><span data-ttu-id="434f1-109">Localizar artigos e selecionar uma versão</span><span class="sxs-lookup"><span data-stu-id="434f1-109">Finding articles and selecting a version</span></span>

<span data-ttu-id="434f1-110">Há duas maneiras de pesquisar conteúdo nos docs. A mais simples é usar a caixa de filtro abaixo do seletor de versão.</span><span class="sxs-lookup"><span data-stu-id="434f1-110">There are two ways to search for content in Docs. The simplest way is to use the filter box under the version selector.</span></span> <span data-ttu-id="434f1-111">Basta inserir uma palavra que aparece no título de um artigo.</span><span class="sxs-lookup"><span data-stu-id="434f1-111">Just enter a word that appears in the title of an article.</span></span> <span data-ttu-id="434f1-112">A página exibe uma lista de artigos correspondentes.</span><span class="sxs-lookup"><span data-stu-id="434f1-112">The page displays a list of matching articles.</span></span> <span data-ttu-id="434f1-113">Também é possível selecionar a opção de pesquisar todo o site com base nessa lista.</span><span class="sxs-lookup"><span data-stu-id="434f1-113">You can also select the option to search the entire site from that list.</span></span>

<span data-ttu-id="434f1-114">Por padrão, o site exibe a documentação da última versão lançada do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="434f1-114">By default, this site displays documentation for the latest released version of PowerShell.</span></span> <span data-ttu-id="434f1-115">Alguns cmdlets funcionam de modo diferente em várias versões do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="434f1-115">Some cmdlets work differently in various versions of PowerShell.</span></span> <span data-ttu-id="434f1-116">Verifique se você está visualizando a documentação da versão do PowerShell que está usando.</span><span class="sxs-lookup"><span data-stu-id="434f1-116">Be sure you are viewing the documentation for the version of PowerShell you are using.</span></span>

<span data-ttu-id="434f1-117">Use o seletor de versão na parte superior da página para selecionar a versão desejada do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="434f1-117">Use the version picker at the top of the page to select the version of PowerShell you want.</span></span>

![Usar o seletor de versão](media/how-to-use-docs/version-search.gif)

<span data-ttu-id="434f1-119">Para verificar a versão do PowerShell que você está usando, inspecione o valor `$PSversionTable.PSVersion`.</span><span class="sxs-lookup"><span data-stu-id="434f1-119">You can verify the version of PowerShell you are using by inspecting the `$PSversionTable.PSVersion` value.</span></span> <span data-ttu-id="434f1-120">O exemplo a seguir mostra a saída do Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="434f1-120">The following example shows the output for Windows PowerShell 5.1.</span></span>

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      19041  1
```

<span data-ttu-id="434f1-121">Se você for iniciante no PowerShell e precisar de ajuda para entender a sintaxe do comando, confira [about_Command_Syntax](/powershell/module/microsoft.powershell.core/about/about_command_syntax).</span><span class="sxs-lookup"><span data-stu-id="434f1-121">If you are new to PowerShell and need help understanding the command syntax, see [about_Command_Syntax](/powershell/module/microsoft.powershell.core/about/about_command_syntax).</span></span>

## <a name="finding-articles-for-previous-versions"></a><span data-ttu-id="434f1-122">Localizar artigos de versões anteriores</span><span class="sxs-lookup"><span data-stu-id="434f1-122">Finding articles for previous versions</span></span>

<span data-ttu-id="434f1-123">A documentação de versões mais antigas do PowerShell foi arquivada em nosso site [Versões anteriores](https://aka.ms/PSLegacyDocs).</span><span class="sxs-lookup"><span data-stu-id="434f1-123">Documentation for older versions of PowerShell has been archived in our [Previous Versions](https://aka.ms/PSLegacyDocs) site.</span></span>

<span data-ttu-id="434f1-124">Ele contém a documentação dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="434f1-124">This site contains documentation for the following topics:</span></span>

- <span data-ttu-id="434f1-125">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="434f1-125">PowerShell 3.0</span></span>
- <span data-ttu-id="434f1-126">PowerShell 4.0</span><span class="sxs-lookup"><span data-stu-id="434f1-126">PowerShell 4.0</span></span>
- <span data-ttu-id="434f1-127">PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="434f1-127">PowerShell 5.0</span></span>
- <span data-ttu-id="434f1-128">Fluxo de Trabalho do PowerShell</span><span class="sxs-lookup"><span data-stu-id="434f1-128">PowerShell Workflows</span></span>
- <span data-ttu-id="434f1-129">Windows PowerShell Web Access</span><span class="sxs-lookup"><span data-stu-id="434f1-129">PowerShell Web Access</span></span>
