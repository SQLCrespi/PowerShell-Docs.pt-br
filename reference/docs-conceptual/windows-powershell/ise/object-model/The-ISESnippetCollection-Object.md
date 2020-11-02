---
ms.date: 12/31/2019
title: O objeto ISESnippetCollection
description: O objeto ISESnippetCollection é uma coleção de objetos ISESnippet. A coleção de arquivos associada a um objeto PowerShellTab é um membro dessa classe.
ms.openlocfilehash: e6170ddf72d5ead840aa3015d4de1dcb21dbfeff
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92655983"
---
# <a name="the-isesnippetcollection-object"></a>O objeto ISESnippetCollection

O objeto **ISESnippetCollection** é uma coleção de objetos **ISESnippet** . A coleção de arquivos associada a um objeto **PowerShellTab** é um membro dessa classe. Um exemplo é a coleção `$psISE.CurrentPowerShellTab.Files`.

## <a name="methods"></a>Métodos

### <a name="load-filepathname-"></a>Load\( FilePathName \)

Com suporte no Windows PowerShell ISE 3.0 e posterior, não está presente em versões anteriores.

Carrega um arquivo `.snippets.ps1xml` que contém os snippets definidos pelo usuário. A maneira mais fácil de criar snippets é usar o novo cmdlet `New-IseSnippet`, que os armazena automaticamente em sua pasta de perfil para que sejam carregados sempre que você iniciar o ISE do Windows PowerShell.

**FilePathName** – a cadeia de caracteres, o caminho e o nome de arquivo para um arquivo .snippets.ps1xml que contém definições de snippet.

```powershell
# Loads a custom snippet file into the current PowerShell tab.
$SnipFile = Join-Path ( Split-Path $profile) 'Snippets\MySnips.snippets.ps1xml' $psISE.CurrentPowerShellTab.Snippets.Add($SnipPath)
```

## <a name="see-also"></a>Consulte Também

- [O ISESnippetObject](The-ISESnippetObject.md)
- [Objetivo do modelo de objeto de script do ISE do Windows PowerShell](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [A hierarquia de modelo de objeto do ISE](The-ISE-Object-Model-Hierarchy.md)
