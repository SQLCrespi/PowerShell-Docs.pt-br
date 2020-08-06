---
title: Declaração de atributo ValidateSet | Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- attributes, ValidateSet
- ValidateSet attribute, described
- ValidateSet attribute
ms.openlocfilehash: 0b6833efb0ce8e9474e9d91049fd201fc845cbea
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787760"
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

`ValidValues`([System. String](/dotnet/api/System.String)) necessário. Especifica os valores de elemento de parâmetro válidos. O exemplo a seguir mostra como especificar um elemento ou vários elementos.

```csharp
[ValidateSetAttribute("Steve")]
[ValidateSetAttribute("Steve","Mary")]
```

`IgnoreCase`([System. Boolean](/dotnet/api/System.Boolean)) parâmetro nomeado opcional. O valor padrão de `true` indica que o caso é ignorado. Um valor `false` torna o cmdlet diferencia maiúsculas de minúsculas.

## <a name="remarks"></a>Comentários

- Esse atributo pode ser usado apenas uma vez por parâmetro.

- Se o valor do parâmetro for uma matriz, cada elemento da matriz deverá corresponder a um elemento do conjunto de atributos.

- O atributo ValidateSetAttribute é definido pela classe [System. Management. Automation. ValidateSetAttribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute) .

## <a name="see-also"></a>Consulte Também

[System. Management. Automation. Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
