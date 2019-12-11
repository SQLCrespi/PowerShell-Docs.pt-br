---
ms.date: 06/05/2017
keywords: powershell, cmdlet
title: O objeto PowerShellTabCollection
ms.openlocfilehash: 5a1318534ddce19c2f5faa0d2013e2b38d8b79e5
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "67030495"
---
# <a name="the-powershelltabcollection-object"></a><span data-ttu-id="b9381-103">O objeto PowerShellTabCollection</span><span class="sxs-lookup"><span data-stu-id="b9381-103">The PowerShellTabCollection Object</span></span>

<span data-ttu-id="b9381-104">O objeto da coleção **PowerShellTab** é uma coleção de objetos **PowerShellTab**.</span><span class="sxs-lookup"><span data-stu-id="b9381-104">The **PowerShellTab** collection object is a collection of **PowerShellTab** objects.</span></span> <span data-ttu-id="b9381-105">Cada objeto **PowerShellTab** funciona como um ambiente de runtime separado.</span><span class="sxs-lookup"><span data-stu-id="b9381-105">Each **PowerShellTab** object functions as a separate runtime environment.</span></span> <span data-ttu-id="b9381-106">Ele é uma instância da classe Microsoft.PowerShell.Host.ISE.PowerShellTabs.</span><span class="sxs-lookup"><span data-stu-id="b9381-106">It is an instance of Microsoft.PowerShell.Host.ISE.PowerShellTabs class.</span></span> <span data-ttu-id="b9381-107">Um exemplo é o objeto **$psISE.PowerShellTabs**.</span><span class="sxs-lookup"><span data-stu-id="b9381-107">An example is the **$psISE.PowerShellTabs** object.</span></span>

## <a name="methods"></a><span data-ttu-id="b9381-108">Métodos</span><span class="sxs-lookup"><span data-stu-id="b9381-108">Methods</span></span>

### <a name="add"></a><span data-ttu-id="b9381-109">Add\(\)</span><span class="sxs-lookup"><span data-stu-id="b9381-109">Add\(\)</span></span>

<span data-ttu-id="b9381-110">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="b9381-110">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="b9381-111">Adiciona uma nova guia do PowerShell à coleção.</span><span class="sxs-lookup"><span data-stu-id="b9381-111">Adds a new PowerShell tab to the collection.</span></span> <span data-ttu-id="b9381-112">Retorna a guia recém-adicionada.</span><span class="sxs-lookup"><span data-stu-id="b9381-112">It returns the newly added tab.</span></span>

```powershell
$newTab = $psISE.PowerShellTabs.Add()
$newTab.DisplayName = 'Brand New Tab'
```

### <a name="removemicrosoftpowershellhostisepowershelltab-pstab"></a><span data-ttu-id="b9381-113">Remove\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span><span class="sxs-lookup"><span data-stu-id="b9381-113">Remove\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span></span>

<span data-ttu-id="b9381-114">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="b9381-114">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="b9381-115">Remove a guia especificada pelo parâmetro **psTab**.</span><span class="sxs-lookup"><span data-stu-id="b9381-115">Removes the tab that is specified by the **psTab** parameter.</span></span>

<span data-ttu-id="b9381-116">**psTab** A guia do PowerShell a ser removida.</span><span class="sxs-lookup"><span data-stu-id="b9381-116">**psTab** The PowerShell tab to remove.</span></span>

```powershell
$newTab = $psISE.PowerShellTabs.Add()
Change the DisplayName of the new PowerShell tab.
$newTab.DisplayName = 'This tab will go away in 5 seconds'
sleep 5
$psISE.PowerShellTabs.Remove($newTab)
```

### <a name="setselectedpowershelltabmicrosoftpowershellhostisepowershelltab-pstab"></a><span data-ttu-id="b9381-117">SetSelectedPowerShellTab\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span><span class="sxs-lookup"><span data-stu-id="b9381-117">SetSelectedPowerShellTab\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span></span>

<span data-ttu-id="b9381-118">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="b9381-118">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="b9381-119">Seleciona a guia do PowerShell que é especificada pelo parâmetro **psTab** para torná-la a guia ativa do PowerShell no momento.</span><span class="sxs-lookup"><span data-stu-id="b9381-119">Selects the PowerShell tab that is specified by the **psTab** parameter to make it the currently active PowerShell tab.</span></span>

<span data-ttu-id="b9381-120">**psTab** A guia do PowerShell a ser selecionada.</span><span class="sxs-lookup"><span data-stu-id="b9381-120">**psTab** The PowerShell tab to select.</span></span>

```powershell
# Save the current tab in a variable and rename it
$oldTab = $psISE.CurrentPowerShellTab
$psISE.CurrentPowerShellTab.DisplayName = 'Old Tab'
# Create a new tab and give it a new display name
$newTab = $psISE.PowerShellTabs.Add()
$newTab.DisplayName = 'Brand New Tab'
# Switch back to the original tab
$psISE.PowerShellTabs.SelectedPowerShellTab = $oldTab
```

## <a name="see-also"></a><span data-ttu-id="b9381-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b9381-121">See Also</span></span>

- [<span data-ttu-id="b9381-122">O objeto PowerShellTab</span><span class="sxs-lookup"><span data-stu-id="b9381-122">The PowerShellTab Object</span></span>](The-PowerShellTab-Object.md)
- [<span data-ttu-id="b9381-123">Objetivo do modelo de objeto de script do ISE do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9381-123">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="b9381-124">A hierarquia de modelo de objeto do ISE</span><span class="sxs-lookup"><span data-stu-id="b9381-124">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
