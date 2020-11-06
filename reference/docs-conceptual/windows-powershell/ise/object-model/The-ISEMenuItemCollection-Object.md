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
# <a name="the-isemenuitemcollection-object"></a>O objeto ISEMenuItemCollection

Um objeto **ISEMenuItemCollection** é uma coleção de objetos **ISEMenuItem**. É uma instância da classe **Microsoft.PowerShell.Host.ISE.ISEMenuItemCollection**. Um exemplo é o objeto `$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus`, que é usado para personalizar o menu **Complemento** no ISE (Ambiente de Script Integrado) do Windows PowerShell&reg;.

## <a name="method"></a>Método

### <a name="addstring-displayname-systemmanagementautomationscriptblock-action-systemwindowsinputkeygesture-shortcut-"></a>Add\(string DisplayName, System.Management.Automation.ScriptBlock Action, System.Windows.Input.KeyGesture Shortcut \)

Suportado no Windows PowerShell ISE 2.0 e posteriores.

Adiciona um item de menu à coleção.

**DisplayName** O nome de exibição do menu a ser adicionado.

**Action** O objeto **System.Management.Automation.ScriptBlock** que especifica a ação associada a este item de menu.

**Shortcut** O atalho de teclado desta ação.

**Returns** O objeto **ISEMenuItem** que acabou de ser adicionado.

```powershell
# Create an Add-ons menu with an fast access key and a shortcut.
# Note the use of "_"  as opposed to the "&" for mapping to the fast access key letter for the menu item.
$menuAdded = $psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
```

### <a name="clear"></a>Clear\(\)

Suportado no Windows PowerShell ISE 2.0 e posteriores.

Remove todos os submenus do item de menu.

```powershell
# Remove all custom submenu items from the AddOns menu
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
```

## <a name="see-also"></a>Consulte Também

- [O objeto ISEMenuItem](The-ISEMenuItem-Object.md)
- [Objetivo do modelo de objeto de script do ISE do Windows PowerShell](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [A hierarquia de modelo de objeto do ISE](The-ISE-Object-Model-Hierarchy.md)
