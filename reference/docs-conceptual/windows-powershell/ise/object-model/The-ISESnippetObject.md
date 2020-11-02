---
ms.date: 06/05/2017
title: O ISESnippetObject
description: Um objeto ISESnippet é uma instância da classe Microsoft.PowerShell.Host.ISE.ISESnippet.
ms.openlocfilehash: 602b344686cbcfb1e994914d4e26438ff7e4b1de
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92663411"
---
# <a name="the-isesnippetobject"></a><span data-ttu-id="9afa5-103">O ISESnippetObject</span><span class="sxs-lookup"><span data-stu-id="9afa5-103">The ISESnippetObject</span></span>

<span data-ttu-id="9afa5-104">Um objeto **ISESnippet** é uma instância da classe Microsoft.PowerShell.Host.ISE.ISESnippet.</span><span class="sxs-lookup"><span data-stu-id="9afa5-104">An **ISESnippet** object is an instance of the Microsoft.PowerShell.Host.ISE.ISESnippet class.</span></span> <span data-ttu-id="9afa5-105">Os membros da coleção `$psISE.CurrentPowerShellTab.Snippets` são exemplos de objetos **ISESnippet** .</span><span class="sxs-lookup"><span data-stu-id="9afa5-105">The members of the `$psISE.CurrentPowerShellTab.Snippets` collection are all examples of **ISESnippet** objects.</span></span> <span data-ttu-id="9afa5-106">A maneira mais fácil de criar um snippet é por meio do cmdlet [New-IseSnippet](/powershell/module/ISE/New-IseSnippet).</span><span class="sxs-lookup"><span data-stu-id="9afa5-106">The easiest way to create a snippet is to use the [New-IseSnippet](/powershell/module/ISE/New-IseSnippet) cmdlet.</span></span>

## <a name="properties"></a><span data-ttu-id="9afa5-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="9afa5-107">Properties</span></span>

### <a name="author"></a><span data-ttu-id="9afa5-108">Autor</span><span class="sxs-lookup"><span data-stu-id="9afa5-108">Author</span></span>

<span data-ttu-id="9afa5-109">Com suporte no Windows PowerShell ISE 3.0 e posterior, não está presente em versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="9afa5-109">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="9afa5-110">A propriedade somente leitura que recebe o nome do autor do snippet.</span><span class="sxs-lookup"><span data-stu-id="9afa5-110">The read-only property that gets the name of the author of the snippet.</span></span>

```powershell
# Get the author of the first snippet item
$psISE.CurrentPowerShellTab.Snippets.Item(0).Author
```

### <a name="codefragment"></a><span data-ttu-id="9afa5-111">CodeFragment</span><span class="sxs-lookup"><span data-stu-id="9afa5-111">CodeFragment</span></span>

<span data-ttu-id="9afa5-112">Com suporte no Windows PowerShell ISE 3.0 e posterior, não está presente em versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="9afa5-112">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="9afa5-113">A propriedade somente leitura que obtém o fragmento de código a ser inserido no editor.</span><span class="sxs-lookup"><span data-stu-id="9afa5-113">The read-only property that gets the code fragment to be inserted into the editor.</span></span>

```powershell
# Get the code fragment associated with the first snippet item.
$psISE.CurrentPowerShellTab.Snippets.Item(0).CodeFragment
```

### <a name="shortcut"></a><span data-ttu-id="9afa5-114">Atalho</span><span class="sxs-lookup"><span data-stu-id="9afa5-114">Shortcut</span></span>

<span data-ttu-id="9afa5-115">Com suporte no Windows PowerShell ISE 3.0 e posterior, não está presente em versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="9afa5-115">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="9afa5-116">A propriedade somente leitura que obtém o atalho de teclado do Windows do item de menu.</span><span class="sxs-lookup"><span data-stu-id="9afa5-116">The read-only property that gets the Windows keyboard shortcut for the menu item.</span></span>

```powershell
# Get the shortcut for the first submenu item.
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Shortcut
```

## <a name="see-also"></a><span data-ttu-id="9afa5-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9afa5-117">See Also</span></span>

- [<span data-ttu-id="9afa5-118">O objeto ISESnippetCollection</span><span class="sxs-lookup"><span data-stu-id="9afa5-118">The ISESnippetCollection Object</span></span>](The-ISESnippetCollection-Object.md)
- [<span data-ttu-id="9afa5-119">Objetivo do modelo de objeto de script do ISE do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9afa5-119">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](purpose-of-the-windows-powershell-ise-scripting-object-model.md)
- [<span data-ttu-id="9afa5-120">A hierarquia de modelo de objeto do ISE</span><span class="sxs-lookup"><span data-stu-id="9afa5-120">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
