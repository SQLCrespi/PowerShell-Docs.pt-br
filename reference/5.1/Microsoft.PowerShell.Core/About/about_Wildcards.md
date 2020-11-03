---
description: Descreve como usar caracteres curinga no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 3/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wildcards?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Wildcards
ms.openlocfilehash: 4656266107a29e4f57c5e273788d382a477a2428
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196128"
---
# <a name="about-wildcards"></a>Sobre curingas

## <a name="short-description"></a>DESCRIÇÃO BREVE

Descreve como usar caracteres curinga no PowerShell.

## <a name="long-description"></a>DESCRIÇÃO LONGA

Os caracteres curinga representam um ou vários caracteres. Você pode usá-los para criar padrões do Word em comandos. Por exemplo, para obter todos os arquivos no `C:\Techdocs` diretório com uma `.ppt` extensão de nome de arquivo, digite:

```powershell
Get-ChildItem C:\Techdocs\*.ppt
```

Nesse caso, o `*` caractere curinga asterisco () representa todos os caracteres que aparecem antes da `.ppt` extensão de nome de arquivo.

O PowerShell dá suporte aos seguintes caracteres curinga:

|Curinga|Descrição               |Exemplo |Corresponder a        |Sem correspondência|
|--------|--------------------------|--------|-------------|--------|
|\*      |Corresponder zero ou mais caracteres | um\*  | aA, AG, Apple | banana |
|?       |Corresponder um caractere nessa posição | ? n | um, em, em | executa |
|\[ \]   |Corresponder a um intervalo de caracteres | \[a-l \] ook | livro, Cook, look | eram |
|\[ \]   |Corresponder caracteres específicos | \[ook de BC \] | livro, Cook | fixação |

Você pode incluir vários caracteres curinga no mesmo padrão de palavra. Por exemplo, para localizar arquivos de texto com nomes que começam com as **letras a** a **l** , digite:

```powershell
Get-ChildItem C:\Techdocs\[a-l]*.txt
```

Muitos cmdlets aceitam caracteres curinga em valores de parâmetro. O tópico da ajuda para cada cmdlet descreve quais parâmetros aceitam caracteres curinga. Para parâmetros que aceitam caracteres curinga, seu uso não diferencia maiúsculas de minúsculas.

Você pode usar caracteres curinga em comandos e blocos de script, como para criar um padrão de palavra que representa valores de propriedade. Por exemplo, o comando a seguir obtém os serviços nos quais o valor da propriedade **ServiceType** inclui **interativo** .

```powershell
Get-Service | Where-Object {$_.ServiceType -Like "*Interactive*"}
```

No exemplo a seguir, a `If` instrução inclui uma condição que usa caracteres curinga para localizar valores de propriedade. Se a **Descrição** do ponto de restauração incluir o **PowerShell** , o comando adicionará o valor da propriedade **CreationTime** do ponto de restauração a um arquivo de log.

```powershell
$p = Get-ComputerRestorePoint
foreach ($point in $p) {
  if ($point.description -like "*PowerShell*") {
    Add-Content -Path C:\TechDocs\RestoreLog.txt "$($point.CreationTime)"
  }
}
```

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_Language_Keywords](about_Language_Keywords.md)

[about_If](about_If.md)

[about_Script_Blocks](about_Script_Blocks.md)
