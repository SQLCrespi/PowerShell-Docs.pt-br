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
# <a name="the-isemenuitem-object"></a>O objeto ISEMenuItem

Um objeto **ISEMenuItem** é uma instância da classe **Microsoft.PowerShell.Host.ISE.ISEMenuItem**.
Todos os objetos de menu **Complementos** são instância da classe **Microsoft.PowerShell.Host.ISE.ISEMenuItem**.

## <a name="properties"></a>Propriedades

### <a name="displayname"></a>DisplayName

Suportado no Windows PowerShell ISE 2.0 e posteriores.

A propriedade somente leitura que obtém o nome de exibição do item de menu.

```powershell
# Get the display name of the Add-ons menu item
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.DisplayName
```

### <a name="action"></a>Ação

Suportado no Windows PowerShell ISE 2.0 e posteriores.

A propriedade somente leitura que obtém o bloco de script. Quando você clicar no item de menu, ele chama a ação.

```powershell
# Get the action associated with the first submenu item.
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Action

# Invoke the script associated with the first submenu item
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Action.Invoke()
```

### <a name="shortcut"></a>Atalho

Suportado no Windows PowerShell ISE 2.0 e posteriores.

A propriedade somente leitura que obtém o atalho de teclado de entrada do Windows do item de menu.

```powershell
# Get the shortcut for the first submenu item.
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Shortcut
```

### <a name="submenus"></a>Submenus

Suportado no Windows PowerShell ISE 2.0 e posteriores.

A propriedade somente leitura que obtém a [lista de submenus](The-ISEMenuItemCollection-Object.md) do item de menu.

```powershell
# List the submenus of the Add-ons menu
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus
```

## <a name="scripting-example"></a>Exemplo de script

Para entender melhor o uso do menu Complementos e suas propriedades programáveis, leia o exemplo de script a seguir.

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

## <a name="see-also"></a>Consulte Também

- [O objeto ISEMenuItemCollection](The-ISEMenuItemCollection-Object.md)
- [Objetivo do modelo de objeto de script do ISE do Windows PowerShell](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [A hierarquia de modelo de objeto do ISE](The-ISE-Object-Model-Hierarchy.md)
