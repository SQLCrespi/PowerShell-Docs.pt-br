---
ms.date: 06/05/2017
title: O objeto PowerShellTabCollection
description: O objeto da coleção PowerShellTab é uma coleção de objetos PowerShellTab. Cada objeto PowerShellTab funciona como um ambiente de tempo de execução separado.
ms.openlocfilehash: 60f8001f096b50bd8433a5685f1f70a350f07f61
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92658277"
---
# <a name="the-powershelltabcollection-object"></a><span data-ttu-id="df099-104">O objeto PowerShellTabCollection</span><span class="sxs-lookup"><span data-stu-id="df099-104">The PowerShellTabCollection Object</span></span>

<span data-ttu-id="df099-105">O objeto da coleção **PowerShellTab** é uma coleção de objetos **PowerShellTab** .</span><span class="sxs-lookup"><span data-stu-id="df099-105">The **PowerShellTab** collection object is a collection of **PowerShellTab** objects.</span></span> <span data-ttu-id="df099-106">Cada objeto **PowerShellTab** funciona como um ambiente de runtime separado.</span><span class="sxs-lookup"><span data-stu-id="df099-106">Each **PowerShellTab** object functions as a separate runtime environment.</span></span> <span data-ttu-id="df099-107">Ele é uma instância da classe Microsoft.PowerShell.Host.ISE.PowerShellTabs.</span><span class="sxs-lookup"><span data-stu-id="df099-107">It is an instance of Microsoft.PowerShell.Host.ISE.PowerShellTabs class.</span></span> <span data-ttu-id="df099-108">Um exemplo é o objeto `$psISE.PowerShellTabs`.</span><span class="sxs-lookup"><span data-stu-id="df099-108">An example is the `$psISE.PowerShellTabs` object.</span></span>

## <a name="methods"></a><span data-ttu-id="df099-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="df099-109">Methods</span></span>

### <a name="add"></a><span data-ttu-id="df099-110">Add\(\)</span><span class="sxs-lookup"><span data-stu-id="df099-110">Add\(\)</span></span>

<span data-ttu-id="df099-111">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="df099-111">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="df099-112">Adiciona uma nova guia do PowerShell à coleção.</span><span class="sxs-lookup"><span data-stu-id="df099-112">Adds a new PowerShell tab to the collection.</span></span> <span data-ttu-id="df099-113">Retorna a guia recém-adicionada.</span><span class="sxs-lookup"><span data-stu-id="df099-113">It returns the newly added tab.</span></span>

```powershell
$newTab = $psISE.PowerShellTabs.Add()
$newTab.DisplayName = 'Brand New Tab'
```

### <a name="removemicrosoftpowershellhostisepowershelltab-pstab"></a><span data-ttu-id="df099-114">Remove\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span><span class="sxs-lookup"><span data-stu-id="df099-114">Remove\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span></span>

<span data-ttu-id="df099-115">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="df099-115">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="df099-116">Remove a guia especificada pelo parâmetro **psTab** .</span><span class="sxs-lookup"><span data-stu-id="df099-116">Removes the tab that is specified by the **psTab** parameter.</span></span>

<span data-ttu-id="df099-117">**psTab** A guia do PowerShell a ser removida.</span><span class="sxs-lookup"><span data-stu-id="df099-117">**psTab** The PowerShell tab to remove.</span></span>

```powershell
$newTab = $psISE.PowerShellTabs.Add()
Change the DisplayName of the new PowerShell tab.
$newTab.DisplayName = 'This tab will go away in 5 seconds'
sleep 5
$psISE.PowerShellTabs.Remove($newTab)
```

### <a name="setselectedpowershelltabmicrosoftpowershellhostisepowershelltab-pstab"></a><span data-ttu-id="df099-118">SetSelectedPowerShellTab\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span><span class="sxs-lookup"><span data-stu-id="df099-118">SetSelectedPowerShellTab\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span></span>

<span data-ttu-id="df099-119">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="df099-119">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="df099-120">Seleciona a guia do PowerShell que é especificada pelo parâmetro **psTab** para torná-la a guia ativa do PowerShell no momento.</span><span class="sxs-lookup"><span data-stu-id="df099-120">Selects the PowerShell tab that is specified by the **psTab** parameter to make it the currently active PowerShell tab.</span></span>

<span data-ttu-id="df099-121">**psTab** A guia do PowerShell a ser selecionada.</span><span class="sxs-lookup"><span data-stu-id="df099-121">**psTab** The PowerShell tab to select.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="df099-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="df099-122">See Also</span></span>

- [<span data-ttu-id="df099-123">O objeto PowerShellTab</span><span class="sxs-lookup"><span data-stu-id="df099-123">The PowerShellTab Object</span></span>](The-PowerShellTab-Object.md)
- [<span data-ttu-id="df099-124">Objetivo do modelo de objeto de script do ISE do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="df099-124">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="df099-125">A hierarquia de modelo de objeto do ISE</span><span class="sxs-lookup"><span data-stu-id="df099-125">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
