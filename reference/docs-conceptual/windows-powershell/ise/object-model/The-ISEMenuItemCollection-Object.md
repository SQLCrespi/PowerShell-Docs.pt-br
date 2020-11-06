---
ms.date: 12/31/2019
title: O objeto ISEMenuItemCollection
description: Um objeto ISEMenuItemCollection é uma coleção de objetos ISEMenuItem.
ms.openlocfilehash: cd86768d13b1326a8f35c44f0391ab60669cee4f
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92656001"
---
# <a name="the-isemenuitemcollection-object"></a><span data-ttu-id="0ca0a-103">O objeto ISEMenuItemCollection</span><span class="sxs-lookup"><span data-stu-id="0ca0a-103">The ISEMenuItemCollection Object</span></span>

<span data-ttu-id="0ca0a-104">Um objeto **ISEMenuItemCollection** é uma coleção de objetos **ISEMenuItem**.</span><span class="sxs-lookup"><span data-stu-id="0ca0a-104">An **ISEMenuItemCollection** object is a collection of **ISEMenuItem** objects.</span></span> <span data-ttu-id="0ca0a-105">É uma instância da classe **Microsoft.PowerShell.Host.ISE.ISEMenuItemCollection**.</span><span class="sxs-lookup"><span data-stu-id="0ca0a-105">It is an instance of the **Microsoft.PowerShell.Host.ISE.ISEMenuItemCollection** class.</span></span> <span data-ttu-id="0ca0a-106">Um exemplo é o objeto `$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus`, que é usado para personalizar o menu **Complemento** no ISE (Ambiente de Script Integrado) do Windows PowerShell&reg;.</span><span class="sxs-lookup"><span data-stu-id="0ca0a-106">An example is the `$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus` object that is used to customize the **Add-On** menu in Windows PowerShell&reg; Integrated Scripting Environment (ISE).</span></span>

## <a name="method"></a><span data-ttu-id="0ca0a-107">Método</span><span class="sxs-lookup"><span data-stu-id="0ca0a-107">Method</span></span>

### <a name="addstring-displayname-systemmanagementautomationscriptblock-action-systemwindowsinputkeygesture-shortcut-"></a><span data-ttu-id="0ca0a-108">Add\(string DisplayName, System.Management.Automation.ScriptBlock Action, System.Windows.Input.KeyGesture Shortcut \)</span><span class="sxs-lookup"><span data-stu-id="0ca0a-108">Add\(string DisplayName, System.Management.Automation.ScriptBlock Action, System.Windows.Input.KeyGesture Shortcut \)</span></span>

<span data-ttu-id="0ca0a-109">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="0ca0a-109">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="0ca0a-110">Adiciona um item de menu à coleção.</span><span class="sxs-lookup"><span data-stu-id="0ca0a-110">Adds a menu item to the collection.</span></span>

<span data-ttu-id="0ca0a-111">**DisplayName** O nome de exibição do menu a ser adicionado.</span><span class="sxs-lookup"><span data-stu-id="0ca0a-111">**DisplayName** The display name of the menu to be added.</span></span>

<span data-ttu-id="0ca0a-112">**Action** O objeto **System.Management.Automation.ScriptBlock** que especifica a ação associada a este item de menu.</span><span class="sxs-lookup"><span data-stu-id="0ca0a-112">**Action** The **System.Management.Automation.ScriptBlock** object that specifies the action that is associated with this menu item.</span></span>

<span data-ttu-id="0ca0a-113">**Shortcut** O atalho de teclado desta ação.</span><span class="sxs-lookup"><span data-stu-id="0ca0a-113">**Shortcut** The keyboard shortcut for the action.</span></span>

<span data-ttu-id="0ca0a-114">**Returns** O objeto **ISEMenuItem** que acabou de ser adicionado.</span><span class="sxs-lookup"><span data-stu-id="0ca0a-114">**Returns** The **ISEMenuItem** object that was just added.</span></span>

```powershell
# Create an Add-ons menu with an fast access key and a shortcut.
# Note the use of "_"  as opposed to the "&" for mapping to the fast access key letter for the menu item.
$menuAdded = $psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
```

### <a name="clear"></a><span data-ttu-id="0ca0a-115">Clear\(\)</span><span class="sxs-lookup"><span data-stu-id="0ca0a-115">Clear\(\)</span></span>

<span data-ttu-id="0ca0a-116">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="0ca0a-116">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="0ca0a-117">Remove todos os submenus do item de menu.</span><span class="sxs-lookup"><span data-stu-id="0ca0a-117">Removes all submenus from the menu item.</span></span>

```powershell
# Remove all custom submenu items from the AddOns menu
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
```

## <a name="see-also"></a><span data-ttu-id="0ca0a-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0ca0a-118">See Also</span></span>

- [<span data-ttu-id="0ca0a-119">O objeto ISEMenuItem</span><span class="sxs-lookup"><span data-stu-id="0ca0a-119">The ISEMenuItem Object</span></span>](The-ISEMenuItem-Object.md)
- [<span data-ttu-id="0ca0a-120">Objetivo do modelo de objeto de script do ISE do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0ca0a-120">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="0ca0a-121">A hierarquia de modelo de objeto do ISE</span><span class="sxs-lookup"><span data-stu-id="0ca0a-121">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
