---
ms.date: 06/05/2017
keywords: powershell, cmdlet
title: O ISESnippetObject
ms.assetid: 98bc8113-c3cd-4201-bdb9-9d9bdb7e266c
ms.openlocfilehash: f80080f4207cf226fb7466c4842446d08c081347
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62057971"
---
# <a name="the-isesnippetobject"></a><span data-ttu-id="e7a7e-103">O ISESnippetObject</span><span class="sxs-lookup"><span data-stu-id="e7a7e-103">The ISESnippetObject</span></span>

<span data-ttu-id="e7a7e-104">Um objeto **ISESnippet** é uma instância da classe Microsoft.PowerShell.Host.ISE.ISESnippet.</span><span class="sxs-lookup"><span data-stu-id="e7a7e-104">An **ISESnippet** object is an instance of the Microsoft.PowerShell.Host.ISE.ISESnippet class.</span></span> <span data-ttu-id="e7a7e-105">Os membros da coleção **$psISE.CurrentPowerShellTab.Snippets** são exemplos de objetos **ISESnippet**.</span><span class="sxs-lookup"><span data-stu-id="e7a7e-105">The members of the **$psISE.CurrentPowerShellTab.Snippets** collection are all examples of **ISESnippet** objects.</span></span> <span data-ttu-id="e7a7e-106">A maneira mais fácil de criar um snippet é usar o cmdlet [New-IseSnippet&#91;PSITPro5_ISE&#93;](https://technet.microsoft.com/library/0a6339a3-2683-4a8e-8929-90ad9a95c3e0).</span><span class="sxs-lookup"><span data-stu-id="e7a7e-106">The easiest way to create a snippet is to use the [New-IseSnippet&#91;PSITPro5_ISE&#93;](https://technet.microsoft.com/library/0a6339a3-2683-4a8e-8929-90ad9a95c3e0) cmdlet.</span></span>

## <a name="properties"></a><span data-ttu-id="e7a7e-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="e7a7e-107">Properties</span></span>

### <a name="author"></a><span data-ttu-id="e7a7e-108">Autor</span><span class="sxs-lookup"><span data-stu-id="e7a7e-108">Author</span></span>

<span data-ttu-id="e7a7e-109">Com suporte no Windows PowerShell ISE 3.0 e posterior, não está presente em versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="e7a7e-109">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="e7a7e-110">A propriedade somente leitura que recebe o nome do autor do snippet.</span><span class="sxs-lookup"><span data-stu-id="e7a7e-110">The read-only property that gets the name of the author of the snippet.</span></span>

```powershell
# Get the author of the first snippet item
$psISE.CurrentPowerShellTab.Snippets.Item(0).Author
```

### <a name="codefragment"></a><span data-ttu-id="e7a7e-111">CodeFragment</span><span class="sxs-lookup"><span data-stu-id="e7a7e-111">CodeFragment</span></span>

<span data-ttu-id="e7a7e-112">Com suporte no Windows PowerShell ISE 3.0 e posterior, não está presente em versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="e7a7e-112">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="e7a7e-113">A propriedade somente leitura que obtém o fragmento de código a ser inserido no editor.</span><span class="sxs-lookup"><span data-stu-id="e7a7e-113">The read-only property that gets the code fragment to be inserted into the editor.</span></span>

```powershell
# Get the code fragment associated with the first snippet item.
$psISE.CurrentPowerShellTab.Snippets.Item(0).CodeFragment
```

### <a name="shortcut"></a><span data-ttu-id="e7a7e-114">Atalho</span><span class="sxs-lookup"><span data-stu-id="e7a7e-114">Shortcut</span></span>

<span data-ttu-id="e7a7e-115">Com suporte no Windows PowerShell ISE 3.0 e posterior, não está presente em versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="e7a7e-115">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="e7a7e-116">A propriedade somente leitura que obtém o atalho de teclado do Windows do item de menu.</span><span class="sxs-lookup"><span data-stu-id="e7a7e-116">The read-only property that gets the Windows keyboard shortcut for the menu item.</span></span>

```powershell
# Get the shortcut for the first submenu item.
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Shortcut
```

## <a name="see-also"></a><span data-ttu-id="e7a7e-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e7a7e-117">See Also</span></span>

- [<span data-ttu-id="e7a7e-118">O objeto ISESnippetCollection</span><span class="sxs-lookup"><span data-stu-id="e7a7e-118">The ISESnippetCollection Object</span></span>](The-ISESnippetCollection-Object.md)
- [<span data-ttu-id="e7a7e-119">Objetivo do modelo de objeto de script do ISE do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7a7e-119">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](purpose-of-the-windows-powershell-ise-scripting-object-model.md)
- [<span data-ttu-id="e7a7e-120">A hierarquia de modelo de objeto do ISE</span><span class="sxs-lookup"><span data-stu-id="e7a7e-120">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)