---
ms.date: 06/05/2017
keywords: powershell, cmdlet
title: O ISESnippetObject
ms.openlocfilehash: f810e6b26f0ded04be15bdc37f336d7890e29dad
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "83809572"
---
# <a name="the-isesnippetobject"></a><span data-ttu-id="6051c-103">O ISESnippetObject</span><span class="sxs-lookup"><span data-stu-id="6051c-103">The ISESnippetObject</span></span>

<span data-ttu-id="6051c-104">Um objeto **ISESnippet** é uma instância da classe Microsoft.PowerShell.Host.ISE.ISESnippet.</span><span class="sxs-lookup"><span data-stu-id="6051c-104">An **ISESnippet** object is an instance of the Microsoft.PowerShell.Host.ISE.ISESnippet class.</span></span> <span data-ttu-id="6051c-105">Os membros da coleção `$psISE.CurrentPowerShellTab.Snippets` são exemplos de objetos **ISESnippet**.</span><span class="sxs-lookup"><span data-stu-id="6051c-105">The members of the `$psISE.CurrentPowerShellTab.Snippets` collection are all examples of **ISESnippet** objects.</span></span> <span data-ttu-id="6051c-106">A maneira mais fácil de criar um snippet é por meio do cmdlet [New-IseSnippet](/powershell/module/ISE/New-IseSnippet).</span><span class="sxs-lookup"><span data-stu-id="6051c-106">The easiest way to create a snippet is to use the [New-IseSnippet](/powershell/module/ISE/New-IseSnippet) cmdlet.</span></span>

## <a name="properties"></a><span data-ttu-id="6051c-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="6051c-107">Properties</span></span>

### <a name="author"></a><span data-ttu-id="6051c-108">Autor</span><span class="sxs-lookup"><span data-stu-id="6051c-108">Author</span></span>

<span data-ttu-id="6051c-109">Com suporte no Windows PowerShell ISE 3.0 e posterior, não está presente em versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="6051c-109">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="6051c-110">A propriedade somente leitura que recebe o nome do autor do snippet.</span><span class="sxs-lookup"><span data-stu-id="6051c-110">The read-only property that gets the name of the author of the snippet.</span></span>

```powershell
# Get the author of the first snippet item
$psISE.CurrentPowerShellTab.Snippets.Item(0).Author
```

### <a name="codefragment"></a><span data-ttu-id="6051c-111">CodeFragment</span><span class="sxs-lookup"><span data-stu-id="6051c-111">CodeFragment</span></span>

<span data-ttu-id="6051c-112">Com suporte no Windows PowerShell ISE 3.0 e posterior, não está presente em versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="6051c-112">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="6051c-113">A propriedade somente leitura que obtém o fragmento de código a ser inserido no editor.</span><span class="sxs-lookup"><span data-stu-id="6051c-113">The read-only property that gets the code fragment to be inserted into the editor.</span></span>

```powershell
# Get the code fragment associated with the first snippet item.
$psISE.CurrentPowerShellTab.Snippets.Item(0).CodeFragment
```

### <a name="shortcut"></a><span data-ttu-id="6051c-114">Atalho</span><span class="sxs-lookup"><span data-stu-id="6051c-114">Shortcut</span></span>

<span data-ttu-id="6051c-115">Com suporte no Windows PowerShell ISE 3.0 e posterior, não está presente em versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="6051c-115">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="6051c-116">A propriedade somente leitura que obtém o atalho de teclado do Windows do item de menu.</span><span class="sxs-lookup"><span data-stu-id="6051c-116">The read-only property that gets the Windows keyboard shortcut for the menu item.</span></span>

```powershell
# Get the shortcut for the first submenu item.
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Shortcut
```

## <a name="see-also"></a><span data-ttu-id="6051c-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6051c-117">See Also</span></span>

- [<span data-ttu-id="6051c-118">O objeto ISESnippetCollection</span><span class="sxs-lookup"><span data-stu-id="6051c-118">The ISESnippetCollection Object</span></span>](The-ISESnippetCollection-Object.md)
- [<span data-ttu-id="6051c-119">Objetivo do modelo de objeto de script do ISE do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6051c-119">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](purpose-of-the-windows-powershell-ise-scripting-object-model.md)
- [<span data-ttu-id="6051c-120">A hierarquia de modelo de objeto do ISE</span><span class="sxs-lookup"><span data-stu-id="6051c-120">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
