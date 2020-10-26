---
ms.date: 08/03/2020
keywords: powershell, cmdlet
title: Apêndice 1 Aliases de compatibilidade
description: O PowerShell tem vários aliases que permitem que os usuários do UNIX e cmd.exe usem comandos conhecidos.
ms.openlocfilehash: 8cbbd5a358de9018fcb5c840e711cd76f7a9a353
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500735"
---
# <a name="appendix-1---compatibility-aliases"></a>Apêndice 1: Alias de compatibilidade

O PowerShell tem vários aliases que permitem que os usuários do **UNIX** e **cmd.exe** usem comandos conhecidos.
Os comandos, seus cmdlets do PowerShell e alias do PowerShell relacionados são mostrados na tabela a seguir:

|            comando cmd.exe            | Comando UNIX | Cmdlet do PowerShell | Alias do PowerShell |
| ------------------------------------- | ------------ | ----------------- | ---------------- |
| **cd** , **chdir**                     | **cd**       | `Set-Location`    | `sl`             |
| **cls**                               | **clear**    | `Clear-Host`      | `cls`            |
| **copy**                              | **cp**       | `Copy-Item`       | `cpi`            |
| **del** , **erase** , **rd** , **rmdir** | **rm**       | `Remove-Item`     | `ri`             |
| **dir**                               | **ls**       | `Get-ChildItem`   | `gci`            |
| **echo**                              | **echo**     | `Write-Output`    | `write`          |
| **md**                                | **mkdir**    | `New-Item`        | `ni`             |
| **move**                              | **mv**       | `Move-Item`       | `mi`             |
| **popd**                              | **popd**     | `Pop-Location`    | `popd`           |
| **pushd**                             | **pushd**    | `Push-Location`   | `pushd`          |
| **ren**                               | **mv**       | `Rename-Item`     | `rni`            |
| **tipo**                              | **cat**      | `Get-Content`     | `gc`             |

Para localizar os aliases do PowerShell, use o cmdlet [Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias). Para exibir os aliases de um cmdlet, use o parâmetro **Definição** e especifique o nome do cmdlet.
Ou, para localizar o nome do cmdlet de um alias, use o parâmetro **Name** e especifique o alias.

```powershell
Get-Alias -Definition Get-ChildItem
```

```Output
CommandType     Name
-----------     ----
Alias           dir -> Get-ChildItem
Alias           gci -> Get-ChildItem
Alias           ls -> Get-ChildItem
```

```powershell
Get-Alias -Name gci
```

```Output
CommandType     Name
-----------     ----
Alias           gci -> Get-ChildItem
```
