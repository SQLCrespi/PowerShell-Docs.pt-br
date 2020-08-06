---
title: Declaração de atributo ValidateLength | Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateLength attribute, described
- attributes, ValidateLength
- ValidateLength attribute
ms.openlocfilehash: 7145dde55e79eeea6e3ceb91dfc1c93043a8857c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786298"
---
# <a name="validatelength-attribute-declaration"></a>Declaração de atributo ValidateLength

O atributo ValidateLength especifica o número mínimo e máximo de caracteres para um argumento de parâmetro de cmdlet. Esse atributo também pode ser usado pelas funções do Windows PowerShell.

## <a name="syntax"></a>Sintaxe

```csharp
[ValidateLength(int minLength, int maxlength)]
```

#### <a name="parameters"></a>Parâmetros

`MinLength`([System. Int32](/dotnet/api/System.Int32)) necessário. Especifica o número mínimo de caracteres permitidos.

`MaxLength`([System. Int32](/dotnet/api/System.Int32)) necessário. Especifica o número máximo de caracteres permitidos.

## <a name="remarks"></a>Comentários

- Para obter mais informações sobre como declarar esse atributo, consulte [como declarar regras de validação de entrada](./how-to-validate-parameter-input.md).

- Quando esse atributo não é usado, o argumento de parâmetro correspondente pode ter qualquer comprimento.

- O tempo de execução do Windows PowerShell gera um erro nas seguintes condições:

  - Quando o valor do `MaxLength` parâmetro Attribute é menor que o valor do `MinLength` parâmetro Attribute.

  - Quando o `MaxLength` parâmetro de atributo é definido como 0.

  - Quando o argumento não é uma cadeia de caracteres.

- O atributo ValidateLength é definido pela classe [System. Management. Automation. Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) .

## <a name="see-also"></a>Consulte Também

[System. Management. Automation. Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
