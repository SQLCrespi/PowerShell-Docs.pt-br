---
ms.date: 09/13/2016
ms.topic: reference
title: Declaração de atributo ValidateRange
description: Declaração de atributo ValidateRange
ms.openlocfilehash: 1fec9d1bd36cd21b7f0f23bf6d72338d276dce91
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660605"
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

- O tempo de execução do Windows PowerShell gera um erro de construção quando o valor do `MinRange` parâmetro é maior que o valor do `MaxRange` parâmetro.

- O tempo de execução do Windows PowerShell gera um erro de validação nas seguintes condições:

  - Quando o valor do argumento é menor que o `MinRange` limite ou maior que o `MaxRange` limite.

  - Quando o argumento não é do mesmo tipo que os `MinRange` `MaxRange` parâmetros e.

- O atributo ValidateRange é definido pela classe [System. Management. Automation. Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) .

## <a name="see-also"></a>Consulte Também

[System. Management. Automation. Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
