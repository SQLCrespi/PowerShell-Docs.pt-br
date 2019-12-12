---
title: Declaração de atributo ValidateRange | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateRange, described
- ValidateRange attribute
- attributes, ValidateRange
ms.assetid: 1f8066e6-e5d3-4f4e-8948-a90af5dace82
caps.latest.revision: 11
ms.openlocfilehash: 155a406b9855c435041fe175ac7d983a4b4eb8b7
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369125"
---
# <a name="validaterange-attribute-declaration"></a>Declaração de atributo ValidateRange

O atributo ValidateRange especifica os valores mínimo e máximo (o intervalo) para o argumento de parâmetro cmdlet. Esse atributo também pode ser usado pelas funções do Windows PowerShell.

## <a name="syntax"></a>Sintaxe

```csharp
[ValidateRange(object minRange, object maxRange)]
```

#### <a name="parameters"></a>Parâmetros

`MinRange` ([System. Object](/dotnet/api/system.object)) necessário. Especifica o valor mínimo permitido.

`MaxRange` ([System. Object](/dotnet/api/system.object)) necessário. Especifica o valor máximo permitido.

## <a name="remarks"></a>Comentários

- O tempo de execução do Windows PowerShell gera um erro de construção quando o valor do parâmetro `MinRange` é maior que o valor do parâmetro `MaxRange`.

- O tempo de execução do Windows PowerShell gera um erro de validação nas seguintes condições:

    - Quando o valor do argumento é menor que o limite de `MinRange` ou maior que o limite de `MaxRange`.

    - Quando o argumento não é do mesmo tipo que o `MinRange` e os parâmetros de `MaxRange`.

- O atributo ValidateRange é definido pela classe [System. Management. Automation. Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) .

## <a name="see-also"></a>Consulte Também

[System. Management. Automation. Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
