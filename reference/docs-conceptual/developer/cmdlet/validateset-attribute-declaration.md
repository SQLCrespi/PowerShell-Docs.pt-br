---
title: Declaração de atributo ValidateSet | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes, ValidateSet
- ValidateSet attribute, described
- ValidateSet attribute
ms.assetid: 4a6f97ab-45b2-4f3d-84d4-30acf8e074d0
caps.latest.revision: 12
ms.openlocfilehash: b036f39cd01ffe4b4ce7db9627cb6da0d5327190
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364275"
---
# <a name="validateset-attribute-declaration"></a>Declaração de atributo ValidateSet

O atributo ValidateSetAttribute especifica um conjunto de valores possíveis para um argumento de parâmetro de cmdlet. Esse atributo também pode ser usado pelas funções do Windows PowerShell.

Quando esse atributo é especificado, o tempo de execução do Windows PowerShell determina se o argumento fornecido para o parâmetro de cmdlet corresponde a um elemento no conjunto de elementos fornecido. O cmdlet será executado somente se o argumento de parâmetro corresponder a um elemento no conjunto. Se nenhuma correspondência for encontrada, um erro será gerado pelo tempo de execução do Windows PowerShell.

## <a name="syntax"></a>Sintaxe

```csharp
[ValidateSetAttribute(params string[] validValues)]
[ValidateSetAttribute(params string[] validValues, Named Parameters)]
```

#### <a name="parameters"></a>Parâmetros

`ValidValues` ([System. String](/dotnet/api/System.String)) necessário. Especifica os valores de elemento de parâmetro válidos. O exemplo a seguir mostra como especificar um elemento ou vários elementos.

```csharp
[ValidateSetAttribute("Steve")]
[ValidateSetAttribute("Steve","Mary")]
```

`IgnoreCase` ([System. Boolean](/dotnet/api/System.Boolean)) parâmetro nomeado opcional. O valor padrão de `true` indica que o caso é ignorado. Um valor de `false` torna o cmdlet diferencia maiúsculas de minúsculas.

## <a name="remarks"></a>Comentários

- Esse atributo pode ser usado apenas uma vez por parâmetro.

- Se o valor do parâmetro for uma matriz, cada elemento da matriz deverá corresponder a um elemento do conjunto de atributos.

- O atributo ValidateSetAttribute é definido pela classe [System. Management. Automation. ValidateSetAttribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute) .

## <a name="see-also"></a>Consulte Também

[System. Management. Automation. Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
