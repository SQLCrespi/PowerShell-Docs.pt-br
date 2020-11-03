---
description: Descreve maneiras mais fáceis e mais naturais de scripts de filtros para coleções de objetos.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_simplified_syntax?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Simplified_Syntax
ms.openlocfilehash: 9c9587a2030abeb892115c5e604b4cac921c5a99
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195481"
---
# <a name="about_simplified_syntax"></a>about_Simplified_Syntax

## <a name="short-description"></a>DESCRIÇÃO BREVE
Descreve maneiras mais fáceis e mais naturais de scripts de filtros para coleções de objetos.

## <a name="long-description"></a>DESCRIÇÃO LONGA

A sintaxe simplificada, introduzida no Windows PowerShell 3,0, permite que você crie alguns comandos de filtro sem usar blocos de script. A sintaxe simplificada se assemelha mais à linguagem natural e é principalmente útil com coleções de objetos que são canalizados para comandos `Where-Object` e `ForEach-Object` seus aliases correspondentes `where` e `foreach` .

Você pode usar um método nos membros de uma coleção (mais comumente, uma matriz) sem referir-se à variável automática `$_` dentro de um bloco de script.

Considere as duas invocações a seguir:

### <a name="standard-syntax"></a>Sintaxe padrão

```powershell
dir Cert:\LocalMachine\Root | where { $_.FriendlyName -eq 'Verisign' }
dir Cert:\ -Recurse | foreach { $_.GetKeyAlgorithm() }```

### Simplified syntax

Under the simplified syntax, comparison operators that work on members of objects in a
collection are treated as parameters. You can invoke a method on objects in a
collection without referring to the automatic variable `$_` inside a script block.
Compare the following two invocations to those of the previous example:

```powershell
dir Cert:\LocalMachine\Root | where FriendlyName -eq 'Verisign'
dir Cert:\ -Recurse | foreach GetKeyAlgorithm
```

Embora ambas as sintaxes funcionem, a sintaxe simplificada retorna resultados sem fazer referência à variável automática `$_` dentro de um bloco de script.
O nome do método `GetKeyAlgorithm` é tratado como um parâmetro de `ForEach-Object` .
O segundo comando retorna os mesmos resultados, mas sem erros, porque a sintaxe simplificada não tenta retornar resultados para itens para os quais o argumento especificado não se aplica.

Neste exemplo, a `Process` propriedade `Description` é passada como o parâmetro de nome de membro para o `ForEach-Object` comando. Os resultados são descrições de processos ativos.

```powershell
Get-Process | foreach Description
```

Neste exemplo, o `DirectoryInfo` método `GetFiles` é passado como o parâmetro de nome de membro do `ForEach-Object` comando.  
O método é chamado com o parâmetro de padrão de pesquisa `.*` .  
Os resultados são `FileInfo` registros para todos os arquivos ocultos em estilo UNIX em diretórios base do usuário.

```powershell
Get-ChildItem /home -Directory | foreach GetFiles .*
```

## <a name="see-also"></a>CONSULTE TAMBÉM

- [about_Comparison_Operators](about_Comparison_Operators.md)
- [about_Foreach](about_Foreach.md)
- [Where-Object](xref:Microsoft.PowerShell.Core.Where-Object)
- [ForEach-Object](xref:Microsoft.PowerShell.Core.ForEach-Object)
