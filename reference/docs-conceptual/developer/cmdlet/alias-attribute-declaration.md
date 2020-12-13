---
ms.date: 09/13/2016
ms.topic: reference
title: Declaração de atributo de alias
description: Declaração de atributo de alias
ms.openlocfilehash: f2fe49578da2c795643b1f80fa44deefe1dbff09
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668296"
---
# <a name="alias-attribute-declaration"></a>Declaração de atributo de alias

O atributo alias permite que o usuário especifique nomes diferentes para um parâmetro de cmdlet. Os aliases podem ser usados para fornecer atalhos para um nome de parâmetro ou podem fornecer nomes diferentes que são apropriados para cenários diferentes.

## <a name="syntax"></a>Sintaxe

```csharp
[Alias(aliasNames)]
```

#### <a name="parameters"></a>Parâmetros

`aliasName` (Cadeia de caracteres []) Necessário. Especifica um conjunto de nomes de alias separados por vírgula para o parâmetro de cmdlet.

## <a name="remarks"></a>Comentários

- O atributo alias é usado com o atributo Parameter quando você especifica um parâmetro de cmdlet. Para obter mais informações sobre como declarar esses atributos, consulte [como declarar parâmetros de cmdlet](./how-to-declare-cmdlet-parameters.md).

- Cada nome de alias deve ser exclusivo dentro de um cmdlet. O Windows PowerShell não verifica nomes de alias duplicados.

- O atributo alias é usado uma vez para cada parâmetro em um cmdlet.

- O atributo alias é definido pela classe [System. Management. Automation. AliasAttribute](/dotnet/api/System.Management.Automation.AliasAttribute) .

## <a name="see-also"></a>Consulte Também

[Aliases de parâmetro](./parameter-aliases.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
