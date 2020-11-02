---
ms.date: 06/05/2017
title: O ISESnippetObject
description: Um objeto ISESnippet é uma instância da classe Microsoft.PowerShell.Host.ISE.ISESnippet.
ms.openlocfilehash: 602b344686cbcfb1e994914d4e26438ff7e4b1de
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92663411"
---
# <a name="the-isesnippetobject"></a>O ISESnippetObject

Um objeto **ISESnippet** é uma instância da classe Microsoft.PowerShell.Host.ISE.ISESnippet. Os membros da coleção `$psISE.CurrentPowerShellTab.Snippets` são exemplos de objetos **ISESnippet** . A maneira mais fácil de criar um snippet é por meio do cmdlet [New-IseSnippet](/powershell/module/ISE/New-IseSnippet).

## <a name="properties"></a>Propriedades

### <a name="author"></a>Autor

Com suporte no Windows PowerShell ISE 3.0 e posterior, não está presente em versões anteriores.

A propriedade somente leitura que recebe o nome do autor do snippet.

```powershell
# Get the author of the first snippet item
$psISE.CurrentPowerShellTab.Snippets.Item(0).Author
```

### <a name="codefragment"></a>CodeFragment

Com suporte no Windows PowerShell ISE 3.0 e posterior, não está presente em versões anteriores.

A propriedade somente leitura que obtém o fragmento de código a ser inserido no editor.

```powershell
# Get the code fragment associated with the first snippet item.
$psISE.CurrentPowerShellTab.Snippets.Item(0).CodeFragment
```

### <a name="shortcut"></a>Atalho

Com suporte no Windows PowerShell ISE 3.0 e posterior, não está presente em versões anteriores.

A propriedade somente leitura que obtém o atalho de teclado do Windows do item de menu.

```powershell
# Get the shortcut for the first submenu item.
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Shortcut
```

## <a name="see-also"></a>Consulte Também

- [O objeto ISESnippetCollection](The-ISESnippetCollection-Object.md)
- [Objetivo do modelo de objeto de script do ISE do Windows PowerShell](purpose-of-the-windows-powershell-ise-scripting-object-model.md)
- [A hierarquia de modelo de objeto do ISE](The-ISE-Object-Model-Hierarchy.md)
