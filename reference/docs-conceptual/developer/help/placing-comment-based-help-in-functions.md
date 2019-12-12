---
title: Colocando a ajuda baseada em comentários no functions | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ec7159e-e4e9-4b21-95df-94244432f679
caps.latest.revision: 5
ms.openlocfilehash: a663bd69be7825b1685f64ff8d3068bdd8ca3265
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367775"
---
# <a name="placing-comment-based-help-in-functions"></a>Colocar a ajuda baseada em comentários em funções

Este tópico explica onde posicionar a ajuda baseada em comentários para uma função, de modo que o cmdlet `Get-Help` associa o tópico de ajuda baseado em comentário à função correta.

## <a name="where-to-place-comment-based-help-for-a-function"></a>Onde posicionar a ajuda baseada em comentários para uma função

- No início do corpo da função.

- No final do corpo da função.

- Antes da palavra-chave `Function`. Quando a função está em um módulo script ou script, não pode haver mais de uma linha em branco entre a última linha da ajuda baseada em comentários e a palavra-chave `Function`. Caso contrário, o `Get-Help` associa a ajuda ao script, não com a função.

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