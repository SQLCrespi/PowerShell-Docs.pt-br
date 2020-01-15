---
ms.date: 12/31/2019
keywords: powershell, cmdlet
title: O objeto ISESnippetCollection
ms.openlocfilehash: 6cdc43dd1d82e94f66122d7f7b313c02e755fed7
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "75736038"
---
# <a name="the-isesnippetcollection-object"></a><span data-ttu-id="d2b96-103">O objeto ISESnippetCollection</span><span class="sxs-lookup"><span data-stu-id="d2b96-103">The ISESnippetCollection Object</span></span>

<span data-ttu-id="d2b96-104">O objeto **ISESnippetCollection** é uma coleção de objetos **ISESnippet**.</span><span class="sxs-lookup"><span data-stu-id="d2b96-104">The **ISESnippetCollection** object is a collection of **ISESnippet** objects.</span></span> <span data-ttu-id="d2b96-105">A coleção de arquivos associada a um objeto **PowerShellTab** é um membro dessa classe.</span><span class="sxs-lookup"><span data-stu-id="d2b96-105">The files collection that is associated with a **PowerShellTab** object is a member of this class.</span></span> <span data-ttu-id="d2b96-106">Um exemplo é a coleção `$psISE.CurrentPowerShellTab.Files`.</span><span class="sxs-lookup"><span data-stu-id="d2b96-106">An example is the `$psISE.CurrentPowerShellTab.Files` collection.</span></span>

## <a name="methods"></a><span data-ttu-id="d2b96-107">Métodos</span><span class="sxs-lookup"><span data-stu-id="d2b96-107">Methods</span></span>

### <a name="load-filepathname-"></a><span data-ttu-id="d2b96-108">Load\( FilePathName \)</span><span class="sxs-lookup"><span data-stu-id="d2b96-108">Load\( FilePathName \)</span></span>

<span data-ttu-id="d2b96-109">Com suporte no Windows PowerShell ISE 3.0 e posterior, não está presente em versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="d2b96-109">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="d2b96-110">Carrega um arquivo `.snippets.ps1xml` que contém os snippets definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="d2b96-110">Loads a `.snippets.ps1xml` file that contains user-defined snippets.</span></span> <span data-ttu-id="d2b96-111">A maneira mais fácil de criar snippets é usar o novo cmdlet `New-IseSnippet`, que os armazena automaticamente em sua pasta de perfil para que sejam carregados sempre que você iniciar o ISE do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d2b96-111">The easiest way to create snippets is to use the `New-IseSnippet` cmdlet, which automatically stores them in your profile folder so that they are loaded every time that you start Windows PowerShell ISE.</span></span>

<span data-ttu-id="d2b96-112">**FilePathName** – a cadeia de caracteres, o caminho e o nome de arquivo para um arquivo .snippets.ps1xml que contém definições de snippet.</span><span class="sxs-lookup"><span data-stu-id="d2b96-112">**FilePathName** - String The path and file name to a .snippets.ps1xml file that contains snippet definitions.</span></span>

```powershell
# Loads a custom snippet file into the current PowerShell tab.
$SnipFile = Join-Path ( Split-Path $profile) 'Snippets\MySnips.snippets.ps1xml' $psISE.CurrentPowerShellTab.Snippets.Add($SnipPath)
```

## <a name="see-also"></a><span data-ttu-id="d2b96-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d2b96-113">See Also</span></span>

- [<span data-ttu-id="d2b96-114">O ISESnippetObject</span><span class="sxs-lookup"><span data-stu-id="d2b96-114">The ISESnippetObject</span></span>](The-ISESnippetObject.md)
- [<span data-ttu-id="d2b96-115">Objetivo do modelo de objeto de script do ISE do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d2b96-115">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="d2b96-116">A hierarquia de modelo de objeto do ISE</span><span class="sxs-lookup"><span data-stu-id="d2b96-116">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
