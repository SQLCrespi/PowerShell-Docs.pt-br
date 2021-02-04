---
ms.date: 07/29/2020
keywords: powershell, cmdlet
ms.topic: how-to
title: Como usar a documentação do PowerShell
description: Este artigo explica como usar os recursos deste site, incluindo filtragem de pesquisa e seleção de versão.
ms.openlocfilehash: 4779e6e4b17c461d71e9d613d1184b9ce2e7ab7b
ms.sourcegitcommit: df5e6f032ee2d4b556d50406832732d2f7dc2502
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2021
ms.locfileid: "98216075"
---
# <a name="how-to-use-the-powershell-documentation"></a><span data-ttu-id="ac673-104">Como usar a documentação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac673-104">How to use the PowerShell documentation</span></span>

<span data-ttu-id="ac673-105">Bem-vindo à documentação online do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac673-105">Welcome to the PowerShell online documentation.</span></span> <span data-ttu-id="ac673-106">Este site contém a referência de cmdlet para as seguintes versões do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ac673-106">This site contains cmdlet reference for the following versions of PowerShell:</span></span>

- <span data-ttu-id="ac673-107">PowerShell 7.2 (pré-lançamento)</span><span class="sxs-lookup"><span data-stu-id="ac673-107">PowerShell 7.2 (prerelease)</span></span>
- <span data-ttu-id="ac673-108">PowerShell 7.1 (atual)</span><span class="sxs-lookup"><span data-stu-id="ac673-108">PowerShell 7.1 (current)</span></span>
- <span data-ttu-id="ac673-109">PowerShell 7.0 (LTS)</span><span class="sxs-lookup"><span data-stu-id="ac673-109">PowerShell 7.0 (LTS)</span></span>
- <span data-ttu-id="ac673-110">PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="ac673-110">PowerShell 5.1</span></span>

## <a name="finding-articles-and-selecting-a-version"></a><span data-ttu-id="ac673-111">Localizar artigos e selecionar uma versão</span><span class="sxs-lookup"><span data-stu-id="ac673-111">Finding articles and selecting a version</span></span>

<span data-ttu-id="ac673-112">Há duas maneiras de pesquisar conteúdo nos docs. A mais simples é usar a caixa de filtro abaixo do seletor de versão.</span><span class="sxs-lookup"><span data-stu-id="ac673-112">There are two ways to search for content in Docs. The simplest way is to use the filter box under the version selector.</span></span> <span data-ttu-id="ac673-113">Basta inserir uma palavra que aparece no título de um artigo.</span><span class="sxs-lookup"><span data-stu-id="ac673-113">Just enter a word that appears in the title of an article.</span></span> <span data-ttu-id="ac673-114">A página exibe uma lista de artigos correspondentes.</span><span class="sxs-lookup"><span data-stu-id="ac673-114">The page displays a list of matching articles.</span></span> <span data-ttu-id="ac673-115">Também é possível selecionar a opção de pesquisar todo o site com base nessa lista.</span><span class="sxs-lookup"><span data-stu-id="ac673-115">You can also select the option to search the entire site from that list.</span></span>

<span data-ttu-id="ac673-116">Por padrão, o site exibe a documentação da última versão lançada do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac673-116">By default, this site displays documentation for the latest released version of PowerShell.</span></span> <span data-ttu-id="ac673-117">Alguns cmdlets funcionam de modo diferente em várias versões do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac673-117">Some cmdlets work differently in various versions of PowerShell.</span></span> <span data-ttu-id="ac673-118">Verifique se você está visualizando a documentação da versão do PowerShell que está usando.</span><span class="sxs-lookup"><span data-stu-id="ac673-118">Be sure you are viewing the documentation for the version of PowerShell you are using.</span></span>

<span data-ttu-id="ac673-119">Use o seletor de versão na parte superior da página para selecionar a versão desejada do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac673-119">Use the version picker at the top of the page to select the version of PowerShell you want.</span></span>

![Usar o seletor de versão](media/how-to-use-docs/version-search.gif)

<span data-ttu-id="ac673-121">Para verificar a versão do PowerShell que você está usando, inspecione o valor `$PSversionTable.PSVersion`.</span><span class="sxs-lookup"><span data-stu-id="ac673-121">You can verify the version of PowerShell you are using by inspecting the `$PSversionTable.PSVersion` value.</span></span> <span data-ttu-id="ac673-122">O exemplo a seguir mostra a saída do Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="ac673-122">The following example shows the output for Windows PowerShell 5.1.</span></span>

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      19041  1
```

<span data-ttu-id="ac673-123">Se você for iniciante no PowerShell e precisar de ajuda para entender a sintaxe do comando, confira [about_Command_Syntax](/powershell/module/microsoft.powershell.core/about/about_command_syntax).</span><span class="sxs-lookup"><span data-stu-id="ac673-123">If you are new to PowerShell and need help understanding the command syntax, see [about_Command_Syntax](/powershell/module/microsoft.powershell.core/about/about_command_syntax).</span></span>

## <a name="finding-articles-for-previous-versions"></a><span data-ttu-id="ac673-124">Localizar artigos de versões anteriores</span><span class="sxs-lookup"><span data-stu-id="ac673-124">Finding articles for previous versions</span></span>

<span data-ttu-id="ac673-125">A documentação de versões mais antigas do PowerShell foi arquivada em nosso site [Versões anteriores](https://aka.ms/PSLegacyDocs).</span><span class="sxs-lookup"><span data-stu-id="ac673-125">Documentation for older versions of PowerShell has been archived in our [Previous Versions](https://aka.ms/PSLegacyDocs) site.</span></span>

<span data-ttu-id="ac673-126">Ele contém a documentação dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="ac673-126">This site contains documentation for the following topics:</span></span>

- <span data-ttu-id="ac673-127">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="ac673-127">PowerShell 3.0</span></span>
- <span data-ttu-id="ac673-128">PowerShell 4.0</span><span class="sxs-lookup"><span data-stu-id="ac673-128">PowerShell 4.0</span></span>
- <span data-ttu-id="ac673-129">PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="ac673-129">PowerShell 5.0</span></span>
- <span data-ttu-id="ac673-130">PowerShell 6</span><span class="sxs-lookup"><span data-stu-id="ac673-130">PowerShell 6</span></span>
- <span data-ttu-id="ac673-131">Fluxo de Trabalho do PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac673-131">PowerShell Workflows</span></span>
- <span data-ttu-id="ac673-132">Windows PowerShell Web Access</span><span class="sxs-lookup"><span data-stu-id="ac673-132">PowerShell Web Access</span></span>
