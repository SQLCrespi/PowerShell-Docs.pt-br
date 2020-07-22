---
title: Colocar a ajuda baseada em comentários em funções
ms.date: 09/12/2016
ms.openlocfilehash: c7a8f8db6c71fa2ef12aaa4df0f78815626ec8d6
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893196"
---
# <a name="placing-comment-based-help-in-functions"></a>Colocar a ajuda baseada em comentários em funções

Este tópico explica onde posicionar a ajuda baseada em comentários para uma função, de modo que o `Get-Help` cmdlet associe o tópico de ajuda baseado em comentário com a função correta.

## <a name="where-to-place-comment-based-help-for-a-function"></a>Onde posicionar a ajuda baseada em comentários para uma função

- No início do corpo da função.

- No final do corpo da função.

- Antes da `Function` palavra-chave. Quando a função está em um módulo de script ou script, não pode haver mais de uma linha em branco entre a última linha da ajuda baseada em comentários e a `Function` palavra-chave. Caso contrário, `Get-Help` o associa a ajuda ao script, não com a função.

## <a name="examples-of-help-placement-in-a-function"></a>Exemplos de posicionamento de ajuda em uma função

Os exemplos a seguir mostram cada uma das três opções de posicionamento para a ajuda baseada em comentários para uma função.

### <a name="help-at-the-beginning-of-a-function-body"></a>Ajuda no início de um corpo de função

O exemplo a seguir mostra o comentário baseado no início de um corpo de função.

```powershell
function MyProcess
{
    <#
       .Description
       The MyProcess function gets the Windows PowerShell process.
    #>

    Get-Process powershell
}
```

### <a name="help-at-the-end-of-a-function-body"></a>Ajuda no final de um corpo de função

 O exemplo a seguir mostra o comentário baseado no final de um corpo de função.

```powershell
function MyFunction
{
    Get-Process powershell

    <#
       .Description
       The MyProcess function gets the Windows PowerShell process.
    #>
}
```

### <a name="help-before-the-function-keyword"></a>Ajuda antes da palavra-chave Function

 Os exemplos a seguir mostram o comentário baseado na linha antes da palavra-chave Function.

```powershell
<#
    .Description
    The MyProcess function gets the Windows PowerShell process.
#>
function MyFunction { Get-Process powershell}
```
