---
ms.date: 09/13/2016
ms.topic: reference
title: Declaração de atributo ValidateCount
description: Declaração de atributo ValidateCount
ms.openlocfilehash: 6acdd02a10ecc1bc2be0e6be88cf2f42a3673eb8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646278"
---
# <a name="validatecount-attribute-declaration"></a>Declaração de atributo ValidateCount

O atributo ValidateCount especifica o número mínimo e máximo de argumentos permitidos para um parâmetro de cmdlet.

## <a name="syntax"></a>Sintaxe

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a>Parâmetros

`MinLength` ([System. Int32][]) necessário. Especifica o número mínimo de argumentos.

`MaxLength`([System. Int32][]) necessário. Especifica o número máximo de argumentos.

## <a name="remarks"></a>Comentários

- Para obter mais informações sobre como declarar esse atributo, consulte [como validar uma contagem de argumentos][].

- Quando esse atributo não é invocado, o parâmetro de cmdlet correspondente pode ter qualquer número de argumentos.

- O tempo de execução do Windows PowerShell gera um erro nas seguintes condições:

  - Os `MinLength` `MaxLength` parâmetros de atributo e não são do tipo [System. Int32][].

  - O valor do `MaxLength` parâmetro de atributo é menor que o valor do `MinLength` parâmetro de atributo.

- O atributo ValidateCount é definido pela classe [System. Management. Automation. ValidateCountAttribute][] .

## <a name="see-also"></a>Consulte Também

[System. Management. Automation. ValidateCountAttribute][]

[Como validar uma contagem de argumentos][]

[Writing a Windows PowerShell Cmdlet][] (Escrevendo um Cmdlet do Windows PowerShell)

[Como validar uma contagem de argumentos]: how-to-validate-an-argument-count.md
[Writing a Windows PowerShell Cmdlet]: writing-a-windows-powershell-cmdlet.md (Escrevendo um Cmdlet do Windows PowerShell)

[System.Int32]: /dotnet/api/System.Int32
[System. Management. Automation. ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
