---
ms.date: 06/05/2017
keywords: powershell, cmdlet
title: O objeto PowerShellTabCollection
ms.openlocfilehash: 0aad885afd3ba3ae3b00f5c11d2c62a9ff303798
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "83808562"
---
# <a name="the-powershelltabcollection-object"></a><span data-ttu-id="2f26d-103">O objeto PowerShellTabCollection</span><span class="sxs-lookup"><span data-stu-id="2f26d-103">The PowerShellTabCollection Object</span></span>

<span data-ttu-id="2f26d-104">O objeto da coleção **PowerShellTab** é uma coleção de objetos **PowerShellTab**.</span><span class="sxs-lookup"><span data-stu-id="2f26d-104">The **PowerShellTab** collection object is a collection of **PowerShellTab** objects.</span></span> <span data-ttu-id="2f26d-105">Cada objeto **PowerShellTab** funciona como um ambiente de runtime separado.</span><span class="sxs-lookup"><span data-stu-id="2f26d-105">Each **PowerShellTab** object functions as a separate runtime environment.</span></span> <span data-ttu-id="2f26d-106">Ele é uma instância da classe Microsoft.PowerShell.Host.ISE.PowerShellTabs.</span><span class="sxs-lookup"><span data-stu-id="2f26d-106">It is an instance of Microsoft.PowerShell.Host.ISE.PowerShellTabs class.</span></span> <span data-ttu-id="2f26d-107">Um exemplo é o objeto `$psISE.PowerShellTabs`.</span><span class="sxs-lookup"><span data-stu-id="2f26d-107">An example is the `$psISE.PowerShellTabs` object.</span></span>

## <a name="methods"></a><span data-ttu-id="2f26d-108">Métodos</span><span class="sxs-lookup"><span data-stu-id="2f26d-108">Methods</span></span>

### <a name="add"></a><span data-ttu-id="2f26d-109">Add\(\)</span><span class="sxs-lookup"><span data-stu-id="2f26d-109">Add\(\)</span></span>

<span data-ttu-id="2f26d-110">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="2f26d-110">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="2f26d-111">Adiciona uma nova guia do PowerShell à coleção.</span><span class="sxs-lookup"><span data-stu-id="2f26d-111">Adds a new PowerShell tab to the collection.</span></span> <span data-ttu-id="2f26d-112">Retorna a guia recém-adicionada.</span><span class="sxs-lookup"><span data-stu-id="2f26d-112">It returns the newly added tab.</span></span>

```powershell
$newTab = $psISE.PowerShellTabs.Add()
$newTab.DisplayName = 'Brand New Tab'
```

### <a name="removemicrosoftpowershellhostisepowershelltab-pstab"></a><span data-ttu-id="2f26d-113">Remove\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span><span class="sxs-lookup"><span data-stu-id="2f26d-113">Remove\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span></span>

<span data-ttu-id="2f26d-114">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="2f26d-114">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="2f26d-115">Remove a guia especificada pelo parâmetro **psTab**.</span><span class="sxs-lookup"><span data-stu-id="2f26d-115">Removes the tab that is specified by the **psTab** parameter.</span></span>

<span data-ttu-id="2f26d-116">**psTab** A guia do PowerShell a ser removida.</span><span class="sxs-lookup"><span data-stu-id="2f26d-116">**psTab** The PowerShell tab to remove.</span></span>

```powershell
$newTab = $psISE.PowerShellTabs.Add()
Change the DisplayName of the new PowerShell tab.
$newTab.DisplayName = 'This tab will go away in 5 seconds'
sleep 5
$psISE.PowerShellTabs.Remove($newTab)
```

### <a name="setselectedpowershelltabmicrosoftpowershellhostisepowershelltab-pstab"></a><span data-ttu-id="2f26d-117">SetSelectedPowerShellTab\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span><span class="sxs-lookup"><span data-stu-id="2f26d-117">SetSelectedPowerShellTab\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span></span>

<span data-ttu-id="2f26d-118">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="2f26d-118">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="2f26d-119">Seleciona a guia do PowerShell que é especificada pelo parâmetro **psTab** para torná-la a guia ativa do PowerShell no momento.</span><span class="sxs-lookup"><span data-stu-id="2f26d-119">Selects the PowerShell tab that is specified by the **psTab** parameter to make it the currently active PowerShell tab.</span></span>

<span data-ttu-id="2f26d-120">**psTab** A guia do PowerShell a ser selecionada.</span><span class="sxs-lookup"><span data-stu-id="2f26d-120">**psTab** The PowerShell tab to select.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="2f26d-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2f26d-121">See Also</span></span>

- [<span data-ttu-id="2f26d-122">O objeto PowerShellTab</span><span class="sxs-lookup"><span data-stu-id="2f26d-122">The PowerShellTab Object</span></span>](The-PowerShellTab-Object.md)
- [<span data-ttu-id="2f26d-123">Objetivo do modelo de objeto de script do ISE do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f26d-123">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="2f26d-124">A hierarquia de modelo de objeto do ISE</span><span class="sxs-lookup"><span data-stu-id="2f26d-124">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
