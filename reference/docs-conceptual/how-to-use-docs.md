---
ms.date: 10/20/2019
keywords: powershell, cmdlet
title: Como usar a documentação do PowerShell
ms.openlocfilehash: 50b054ddc21d55946969414688306fc0d15a5adf
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "80082828"
---
# <a name="how-to-use-the-powershell-documentation"></a><span data-ttu-id="05e15-103">Como usar a documentação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="05e15-103">How to use the PowerShell documentation</span></span>

<span data-ttu-id="05e15-104">Bem-vindo à documentação online do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="05e15-104">Welcome to the PowerShell online documentation.</span></span> <span data-ttu-id="05e15-105">Este site contém a referência de cmdlet para as seguintes versões do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="05e15-105">This site contains cmdlet reference for the following versions of PowerShell:</span></span>

- <span data-ttu-id="05e15-106">PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="05e15-106">PowerShell 7</span></span>
- <span data-ttu-id="05e15-107">PowerShell 6</span><span class="sxs-lookup"><span data-stu-id="05e15-107">PowerShell 6</span></span>
- <span data-ttu-id="05e15-108">PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="05e15-108">PowerShell 5.1</span></span>

## <a name="finding-articles-and-selecting-a-version"></a><span data-ttu-id="05e15-109">Localizar artigos e selecionar uma versão</span><span class="sxs-lookup"><span data-stu-id="05e15-109">Finding articles and selecting a version</span></span>

<span data-ttu-id="05e15-110">Há duas maneiras de pesquisar conteúdo nos docs. A mais simples é usar a caixa de filtro abaixo do seletor de versão.</span><span class="sxs-lookup"><span data-stu-id="05e15-110">There are two ways to search for content in Docs. The simplest way is to use the filter box under the version selector.</span></span> <span data-ttu-id="05e15-111">Basta inserir uma palavra que aparece no título de um artigo.</span><span class="sxs-lookup"><span data-stu-id="05e15-111">Just enter a word that appears in the title of an article.</span></span> <span data-ttu-id="05e15-112">A página exibe uma lista de artigos correspondentes.</span><span class="sxs-lookup"><span data-stu-id="05e15-112">The page displays a list of matching articles.</span></span> <span data-ttu-id="05e15-113">Também é possível selecionar a opção de pesquisar todo o site com base nessa lista.</span><span class="sxs-lookup"><span data-stu-id="05e15-113">You can also select the option to search the entire site from that list.</span></span>

<span data-ttu-id="05e15-114">Por padrão, o site exibe a documentação da última versão lançada do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="05e15-114">By default, this site displays documentation for the latest released version of PowerShell.</span></span> <span data-ttu-id="05e15-115">Alguns cmdlets funcionam de modo diferente em várias versões do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="05e15-115">Some cmdlets work differently in various versions of PowerShell.</span></span> <span data-ttu-id="05e15-116">Verifique se você está visualizando a documentação da versão do PowerShell que está usando.</span><span class="sxs-lookup"><span data-stu-id="05e15-116">Be sure you are viewing the documentation for the version of PowerShell you are using.</span></span>

<span data-ttu-id="05e15-117">Use o seletor de versão na parte superior da página para selecionar a versão desejada do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="05e15-117">Use the version picker at the top of the page to select the version of PowerShell you want.</span></span>

![seletor de versão](media/how-to-use-docs/version-search.gif)

<span data-ttu-id="05e15-119">Para verificar a versão do PowerShell que você está usando, inspecione o valor `$PSversionTable.PSVersion`.</span><span class="sxs-lookup"><span data-stu-id="05e15-119">You can verify the version of PowerShell you are using by inspecting the `$PSversionTable.PSVersion` value.</span></span> <span data-ttu-id="05e15-120">O exemplo a seguir mostra a saída do Windows PowerShell v5.1.</span><span class="sxs-lookup"><span data-stu-id="05e15-120">The following example shows the output for Windows PowerShell v5.1.</span></span>

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      18362  145
```
