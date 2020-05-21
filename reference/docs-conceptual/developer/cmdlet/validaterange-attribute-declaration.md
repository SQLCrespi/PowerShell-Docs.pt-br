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
ms.openlocfilehash: 560fa105ac3f93ae6334df0112f5290dfa20576c
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692019"
---
# <a name="validaterange-attribute-declaration"></a>Declaração de atributo ValidateRange

O atributo ValidateRange especifica os valores mínimo e máximo (o intervalo) para o argumento de parâmetro cmdlet. Esse atributo também pode ser usado pelas funções do Windows PowerShell.

## <a name="syntax"></a>Sintaxe

```csharp
[ValidateRange(object minRange, object maxRange)]
```

#### <a name="parameters"></a>Parâmetros

`MinRange`([System. Object](/dotnet/api/system.object)) necessário. Especifica o valor mínimo permitido.

`MaxRange`([System. Object](/dotnet/api/system.object)) necessário. Especifica o valor máximo permitido.

## <a name="remarks"></a>Comentários

- O tempo de execução do Windows PowerShell gera um erro de construção quando o valor do `MinRange` parâmetro é maior que o valor do `MaxRange` parâmetro.

- O tempo de execução do Windows PowerShell gera um erro de validação nas seguintes condições:

  - Quando o valor do argumento é menor que o `MinRange` limite ou maior que o `MaxRange` limite.

  - Quando o argumento não é do mesmo tipo que os `MinRange` `MaxRange` parâmetros e.

- O atributo ValidateRange é definido pela classe [System. Management. Automation. Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) .

## <a name="see-also"></a>Consulte Também

[System. Management. Automation. Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
