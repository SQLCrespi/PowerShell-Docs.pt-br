---
ms.date: 06/05/2017
keywords: powershell, cmdlet
title: O ISESnippetObject
ms.openlocfilehash: 62d470569deb051fca80005235d4c492319cf5ec
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "67028892"
---
# <a name="the-isesnippetobject"></a><span data-ttu-id="ae85a-103">O ISESnippetObject</span><span class="sxs-lookup"><span data-stu-id="ae85a-103">The ISESnippetObject</span></span>

<span data-ttu-id="ae85a-104">Um objeto **ISESnippet** é uma instância da classe Microsoft.PowerShell.Host.ISE.ISESnippet.</span><span class="sxs-lookup"><span data-stu-id="ae85a-104">An **ISESnippet** object is an instance of the Microsoft.PowerShell.Host.ISE.ISESnippet class.</span></span> <span data-ttu-id="ae85a-105">Os membros da coleção **$psISE.CurrentPowerShellTab.Snippets** são exemplos de objetos **ISESnippet**.</span><span class="sxs-lookup"><span data-stu-id="ae85a-105">The members of the **$psISE.CurrentPowerShellTab.Snippets** collection are all examples of **ISESnippet** objects.</span></span> <span data-ttu-id="ae85a-106">A maneira mais fácil de criar um snippet é usar o cmdlet [New-IseSnippet&#91;PSITPro5_ISE&#93;](https://technet.microsoft.com/library/0a6339a3-2683-4a8e-8929-90ad9a95c3e0).</span><span class="sxs-lookup"><span data-stu-id="ae85a-106">The easiest way to create a snippet is to use the [New-IseSnippet&#91;PSITPro5_ISE&#93;](https://technet.microsoft.com/library/0a6339a3-2683-4a8e-8929-90ad9a95c3e0) cmdlet.</span></span>

## <a name="properties"></a><span data-ttu-id="ae85a-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="ae85a-107">Properties</span></span>

### <a name="author"></a><span data-ttu-id="ae85a-108">Autor</span><span class="sxs-lookup"><span data-stu-id="ae85a-108">Author</span></span>

<span data-ttu-id="ae85a-109">Com suporte no Windows PowerShell ISE 3.0 e posterior, não está presente em versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="ae85a-109">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="ae85a-110">A propriedade somente leitura que recebe o nome do autor do snippet.</span><span class="sxs-lookup"><span data-stu-id="ae85a-110">The read-only property that gets the name of the author of the snippet.</span></span>

```powershell
# Get the author of the first snippet item
$psISE.CurrentPowerShellTab.Snippets.Item(0).Author
```

### <a name="codefragment"></a><span data-ttu-id="ae85a-111">CodeFragment</span><span class="sxs-lookup"><span data-stu-id="ae85a-111">CodeFragment</span></span>

<span data-ttu-id="ae85a-112">Com suporte no Windows PowerShell ISE 3.0 e posterior, não está presente em versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="ae85a-112">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="ae85a-113">A propriedade somente leitura que obtém o fragmento de código a ser inserido no editor.</span><span class="sxs-lookup"><span data-stu-id="ae85a-113">The read-only property that gets the code fragment to be inserted into the editor.</span></span>

```powershell
# Get the code fragment associated with the first snippet item.
$psISE.CurrentPowerShellTab.Snippets.Item(0).CodeFragment
```

### <a name="shortcut"></a><span data-ttu-id="ae85a-114">Atalho</span><span class="sxs-lookup"><span data-stu-id="ae85a-114">Shortcut</span></span>

<span data-ttu-id="ae85a-115">Com suporte no Windows PowerShell ISE 3.0 e posterior, não está presente em versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="ae85a-115">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="ae85a-116">A propriedade somente leitura que obtém o atalho de teclado do Windows do item de menu.</span><span class="sxs-lookup"><span data-stu-id="ae85a-116">The read-only property that gets the Windows keyboard shortcut for the menu item.</span></span>

```powershell
# Get the shortcut for the first submenu item.
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Shortcut
```

## <a name="see-also"></a><span data-ttu-id="ae85a-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ae85a-117">See Also</span></span>

- [<span data-ttu-id="ae85a-118">O objeto ISESnippetCollection</span><span class="sxs-lookup"><span data-stu-id="ae85a-118">The ISESnippetCollection Object</span></span>](The-ISESnippetCollection-Object.md)
- [<span data-ttu-id="ae85a-119">Objetivo do modelo de objeto de script do ISE do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae85a-119">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](purpose-of-the-windows-powershell-ise-scripting-object-model.md)
- [<span data-ttu-id="ae85a-120">A hierarquia de modelo de objeto do ISE</span><span class="sxs-lookup"><span data-stu-id="ae85a-120">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
