---
ms.date: 06/05/2017
keywords: powershell, cmdlet
title: O objeto PowerShellTabCollection
ms.assetid: 81f4bf4a-83bf-415e-8378-1703792fbb58
ms.openlocfilehash: d9088b26de35360b8258d3f15924b3010a986d15
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62086605"
---
# <a name="the-powershelltabcollection-object"></a><span data-ttu-id="3cb73-103">O objeto PowerShellTabCollection</span><span class="sxs-lookup"><span data-stu-id="3cb73-103">The PowerShellTabCollection Object</span></span>

<span data-ttu-id="3cb73-104">O objeto da coleção **PowerShellTab** é uma coleção de objetos **PowerShellTab**.</span><span class="sxs-lookup"><span data-stu-id="3cb73-104">The **PowerShellTab** collection object is a collection of **PowerShellTab** objects.</span></span> <span data-ttu-id="3cb73-105">Cada objeto **PowerShellTab** funciona como um ambiente de tempo de execução separado.</span><span class="sxs-lookup"><span data-stu-id="3cb73-105">Each **PowerShellTab** object functions as a separate runtime environment.</span></span> <span data-ttu-id="3cb73-106">Ele é uma instância da classe Microsoft.PowerShell.Host.ISE.PowerShellTabs.</span><span class="sxs-lookup"><span data-stu-id="3cb73-106">It is an instance of Microsoft.PowerShell.Host.ISE.PowerShellTabs class.</span></span> <span data-ttu-id="3cb73-107">Um exemplo é o objeto **$psISE.PowerShellTabs**.</span><span class="sxs-lookup"><span data-stu-id="3cb73-107">An example is the **$psISE.PowerShellTabs** object.</span></span>

## <a name="methods"></a><span data-ttu-id="3cb73-108">Métodos</span><span class="sxs-lookup"><span data-stu-id="3cb73-108">Methods</span></span>

### <a name="add"></a><span data-ttu-id="3cb73-109">Add\(\)</span><span class="sxs-lookup"><span data-stu-id="3cb73-109">Add\(\)</span></span>

<span data-ttu-id="3cb73-110">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="3cb73-110">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="3cb73-111">Adiciona uma nova guia do PowerShell à coleção.</span><span class="sxs-lookup"><span data-stu-id="3cb73-111">Adds a new PowerShell tab to the collection.</span></span> <span data-ttu-id="3cb73-112">Retorna a guia recém-adicionada.</span><span class="sxs-lookup"><span data-stu-id="3cb73-112">It returns the newly added tab.</span></span>

```powershell
$newTab = $psISE.PowerShellTabs.Add()
$newTab.DisplayName = 'Brand New Tab'
```

### <a name="removemicrosoftpowershellhostisepowershelltab-pstab"></a><span data-ttu-id="3cb73-113">Remove\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span><span class="sxs-lookup"><span data-stu-id="3cb73-113">Remove\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span></span>

<span data-ttu-id="3cb73-114">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="3cb73-114">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="3cb73-115">Remove a guia especificada pelo parâmetro **psTab**.</span><span class="sxs-lookup"><span data-stu-id="3cb73-115">Removes the tab that is specified by the **psTab** parameter.</span></span>

<span data-ttu-id="3cb73-116">**psTab** A guia do PowerShell a ser removida.</span><span class="sxs-lookup"><span data-stu-id="3cb73-116">**psTab** The PowerShell tab to remove.</span></span>

```powershell
$newTab = $psISE.PowerShellTabs.Add()
Change the DisplayName of the new PowerShell tab.
$newTab.DisplayName = 'This tab will go away in 5 seconds'
sleep 5
$psISE.PowerShellTabs.Remove($newTab)
```

### <a name="setselectedpowershelltabmicrosoftpowershellhostisepowershelltab-pstab"></a><span data-ttu-id="3cb73-117">SetSelectedPowerShellTab\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span><span class="sxs-lookup"><span data-stu-id="3cb73-117">SetSelectedPowerShellTab\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span></span>

<span data-ttu-id="3cb73-118">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="3cb73-118">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="3cb73-119">Seleciona a guia do PowerShell que é especificada pelo parâmetro **psTab** para torná-la a guia ativa do PowerShell no momento.</span><span class="sxs-lookup"><span data-stu-id="3cb73-119">Selects the PowerShell tab that is specified by the **psTab** parameter to make it the currently active PowerShell tab.</span></span>

<span data-ttu-id="3cb73-120">**psTab** A guia do PowerShell a ser selecionada.</span><span class="sxs-lookup"><span data-stu-id="3cb73-120">**psTab** The PowerShell tab to select.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="3cb73-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3cb73-121">See Also</span></span>

- [<span data-ttu-id="3cb73-122">O objeto PowerShellTab</span><span class="sxs-lookup"><span data-stu-id="3cb73-122">The PowerShellTab Object</span></span>](The-PowerShellTab-Object.md)
- [<span data-ttu-id="3cb73-123">Objetivo do modelo de objeto de script do ISE do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3cb73-123">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="3cb73-124">A hierarquia de modelo de objeto do ISE</span><span class="sxs-lookup"><span data-stu-id="3cb73-124">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)