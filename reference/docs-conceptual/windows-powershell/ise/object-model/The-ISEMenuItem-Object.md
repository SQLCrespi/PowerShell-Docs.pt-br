---
ms.date: 12/31/2019
title: O objeto ISEMenuItem
description: Um objeto ISEMenuItem é uma instância da classe Microsoft.PowerShell.Host.ISE.ISEMenuItem. Todos os objetos do menu **Complementos** são instâncias da classe ISEMenuItem.
ms.openlocfilehash: 15036e3551687a21dfbe50834a89247c80949656
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92663448"
---
# <a name="the-isemenuitem-object"></a><span data-ttu-id="8bc5d-104">O objeto ISEMenuItem</span><span class="sxs-lookup"><span data-stu-id="8bc5d-104">The ISEMenuItem Object</span></span>

<span data-ttu-id="8bc5d-105">Um objeto **ISEMenuItem** é uma instância da classe **Microsoft.PowerShell.Host.ISE.ISEMenuItem**.</span><span class="sxs-lookup"><span data-stu-id="8bc5d-105">An **ISEMenuItem** object is an instance of the **Microsoft.PowerShell.Host.ISE.ISEMenuItem** class.</span></span>
<span data-ttu-id="8bc5d-106">Todos os objetos de menu **Complementos** são instância da classe **Microsoft.PowerShell.Host.ISE.ISEMenuItem**.</span><span class="sxs-lookup"><span data-stu-id="8bc5d-106">All menu objects on the **Add-ons** menu are instances of the **Microsoft.PowerShell.Host.ISE.ISEMenuItem** class.</span></span>

## <a name="properties"></a><span data-ttu-id="8bc5d-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="8bc5d-107">Properties</span></span>

### <a name="displayname"></a><span data-ttu-id="8bc5d-108">DisplayName</span><span class="sxs-lookup"><span data-stu-id="8bc5d-108">DisplayName</span></span>

<span data-ttu-id="8bc5d-109">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="8bc5d-109">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="8bc5d-110">A propriedade somente leitura que obtém o nome de exibição do item de menu.</span><span class="sxs-lookup"><span data-stu-id="8bc5d-110">The read-only property that gets the display name of the menu item.</span></span>

```powershell
# Get the display name of the Add-ons menu item
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.DisplayName
```

### <a name="action"></a><span data-ttu-id="8bc5d-111">Ação</span><span class="sxs-lookup"><span data-stu-id="8bc5d-111">Action</span></span>

<span data-ttu-id="8bc5d-112">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="8bc5d-112">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="8bc5d-113">A propriedade somente leitura que obtém o bloco de script.</span><span class="sxs-lookup"><span data-stu-id="8bc5d-113">The read-only property that gets the block of script.</span></span> <span data-ttu-id="8bc5d-114">Quando você clicar no item de menu, ele chama a ação.</span><span class="sxs-lookup"><span data-stu-id="8bc5d-114">It invokes the action when you click the menu item.</span></span>

```powershell
# Get the action associated with the first submenu item.
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Action

# Invoke the script associated with the first submenu item
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Action.Invoke()
```

### <a name="shortcut"></a><span data-ttu-id="8bc5d-115">Atalho</span><span class="sxs-lookup"><span data-stu-id="8bc5d-115">Shortcut</span></span>

<span data-ttu-id="8bc5d-116">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="8bc5d-116">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="8bc5d-117">A propriedade somente leitura que obtém o atalho de teclado de entrada do Windows do item de menu.</span><span class="sxs-lookup"><span data-stu-id="8bc5d-117">The read-only property that gets the Windows input keyboard shortcut for the menu item.</span></span>

```powershell
# Get the shortcut for the first submenu item.
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Shortcut
```

### <a name="submenus"></a><span data-ttu-id="8bc5d-118">Submenus</span><span class="sxs-lookup"><span data-stu-id="8bc5d-118">Submenus</span></span>

<span data-ttu-id="8bc5d-119">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="8bc5d-119">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="8bc5d-120">A propriedade somente leitura que obtém a [lista de submenus](The-ISEMenuItemCollection-Object.md) do item de menu.</span><span class="sxs-lookup"><span data-stu-id="8bc5d-120">The read-only property that gets the [list of submenus](The-ISEMenuItemCollection-Object.md) of the menu item.</span></span>

```powershell
# List the submenus of the Add-ons menu
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus
```

## <a name="scripting-example"></a><span data-ttu-id="8bc5d-121">Exemplo de script</span><span class="sxs-lookup"><span data-stu-id="8bc5d-121">Scripting example</span></span>

<span data-ttu-id="8bc5d-122">Para entender melhor o uso do menu Complementos e suas propriedades programáveis, leia o exemplo de script a seguir.</span><span class="sxs-lookup"><span data-stu-id="8bc5d-122">To better understand the use of the Add-ons menu and its scriptable properties, read through the following scripting example.</span></span>

```powershell
# This is a scripting example that shows the use of the Add-ons menu.
# Clear the Add-ons menu if any entries currently exist
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()

# Add an Add-ons menu item with an shortcut and fast access key.
# Note the use of "_"  as opposed to the "&" for mapping to the fast access key letter for the menu item.
$menuAdded = $psISE.CurrentPowerShellTab.AddOnsMenu.SubMenus.Add('_Process', {Get-Process}, 'Alt+P')
# Add a nested menu - a parent and a child submenu item.
$parentAdded = $psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('Parent', $null, $null)
$parentAdded.SubMenus.Add('_Dir', {dir}, 'Alt+D')
```

## <a name="see-also"></a><span data-ttu-id="8bc5d-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8bc5d-123">See Also</span></span>

- [<span data-ttu-id="8bc5d-124">O objeto ISEMenuItemCollection</span><span class="sxs-lookup"><span data-stu-id="8bc5d-124">The ISEMenuItemCollection Object</span></span>](The-ISEMenuItemCollection-Object.md)
- [<span data-ttu-id="8bc5d-125">Objetivo do modelo de objeto de script do ISE do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8bc5d-125">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="8bc5d-126">A hierarquia de modelo de objeto do ISE</span><span class="sxs-lookup"><span data-stu-id="8bc5d-126">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
