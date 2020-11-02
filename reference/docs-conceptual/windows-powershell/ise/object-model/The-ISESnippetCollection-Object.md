---
ms.date: 12/31/2019
title: O objeto ISESnippetCollection
description: O objeto ISESnippetCollection é uma coleção de objetos ISESnippet. A coleção de arquivos associada a um objeto PowerShellTab é um membro dessa classe.
ms.openlocfilehash: e6170ddf72d5ead840aa3015d4de1dcb21dbfeff
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92655983"
---
# <a name="the-isesnippetcollection-object"></a><span data-ttu-id="09577-104">O objeto ISESnippetCollection</span><span class="sxs-lookup"><span data-stu-id="09577-104">The ISESnippetCollection Object</span></span>

<span data-ttu-id="09577-105">O objeto **ISESnippetCollection** é uma coleção de objetos **ISESnippet** .</span><span class="sxs-lookup"><span data-stu-id="09577-105">The **ISESnippetCollection** object is a collection of **ISESnippet** objects.</span></span> <span data-ttu-id="09577-106">A coleção de arquivos associada a um objeto **PowerShellTab** é um membro dessa classe.</span><span class="sxs-lookup"><span data-stu-id="09577-106">The files collection that is associated with a **PowerShellTab** object is a member of this class.</span></span> <span data-ttu-id="09577-107">Um exemplo é a coleção `$psISE.CurrentPowerShellTab.Files`.</span><span class="sxs-lookup"><span data-stu-id="09577-107">An example is the `$psISE.CurrentPowerShellTab.Files` collection.</span></span>

## <a name="methods"></a><span data-ttu-id="09577-108">Métodos</span><span class="sxs-lookup"><span data-stu-id="09577-108">Methods</span></span>

### <a name="load-filepathname-"></a><span data-ttu-id="09577-109">Load\( FilePathName \)</span><span class="sxs-lookup"><span data-stu-id="09577-109">Load\( FilePathName \)</span></span>

<span data-ttu-id="09577-110">Com suporte no Windows PowerShell ISE 3.0 e posterior, não está presente em versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="09577-110">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="09577-111">Carrega um arquivo `.snippets.ps1xml` que contém os snippets definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="09577-111">Loads a `.snippets.ps1xml` file that contains user-defined snippets.</span></span> <span data-ttu-id="09577-112">A maneira mais fácil de criar snippets é usar o novo cmdlet `New-IseSnippet`, que os armazena automaticamente em sua pasta de perfil para que sejam carregados sempre que você iniciar o ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09577-112">The easiest way to create snippets is to use the `New-IseSnippet` cmdlet, which automatically stores them in your profile folder so that they are loaded every time that you start Windows PowerShell ISE.</span></span>

<span data-ttu-id="09577-113">**FilePathName** – a cadeia de caracteres, o caminho e o nome de arquivo para um arquivo .snippets.ps1xml que contém definições de snippet.</span><span class="sxs-lookup"><span data-stu-id="09577-113">**FilePathName** - String The path and file name to a .snippets.ps1xml file that contains snippet definitions.</span></span>

```powershell
# Loads a custom snippet file into the current PowerShell tab.
$SnipFile = Join-Path ( Split-Path $profile) 'Snippets\MySnips.snippets.ps1xml' $psISE.CurrentPowerShellTab.Snippets.Add($SnipPath)
```

## <a name="see-also"></a><span data-ttu-id="09577-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="09577-114">See Also</span></span>

- [<span data-ttu-id="09577-115">O ISESnippetObject</span><span class="sxs-lookup"><span data-stu-id="09577-115">The ISESnippetObject</span></span>](The-ISESnippetObject.md)
- [<span data-ttu-id="09577-116">Objetivo do modelo de objeto de script do ISE do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="09577-116">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="09577-117">A hierarquia de modelo de objeto do ISE</span><span class="sxs-lookup"><span data-stu-id="09577-117">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
