---
title: Declaração de atributo ValidatePattern | Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- attributes, ValidatePattern
- ValidatePattern attribute, described
- ValidatePattern attribute
ms.openlocfilehash: 713fa7a46a8eeefdbfd679a5e8436285fac085f8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787794"
---
# <a name="validatepattern-attribute-declaration"></a>Declaração de atributo ValidatePattern

O atributo ValidatePattern especifica um padrão de expressão regular que valida o argumento de um parâmetro de cmdlet. Esse atributo também pode ser usado pelas funções do Windows PowerShell.

Quando ValidatePattern é invocado em um cmdlet, o tempo de execução do Windows PowerShell converte o argumento do parâmetro cmdlet em uma cadeia de caracteres e, em seguida, compara essa cadeia de caracteres com o padrão fornecido pelo atributo ValidatePattern. O cmdlet será executado somente se a representação de cadeia de caracteres convertida do argumento e a correspondência de padrão fornecida. Se eles não corresponderem, um erro será gerado pelo tempo de execução do Windows PowerShell.

## <a name="syntax"></a>Sintaxe

```csharp
[ValidatePattern(string regexString)]
[ValidatePattern(string regexString, Named Parameters)]
```

#### <a name="parameters"></a>Parâmetros

`RegexString`([System. String](/dotnet/api/System.String)) necessário. Especifica uma expressão regular que valida o argumento do parâmetro.

Opções ([System. Text. RegularExpressions. RegexOptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) parâmetro nomeado opcional. Especifica uma combinação de bits-bit que indica os sinalizadores [System. Text. RegularExpressions. RegexOptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions) que especificam opções de expressão regular.

## <a name="remarks"></a>Comentários

- Esse atributo pode ser usado apenas uma vez por parâmetro.

- Você pode usar o `Option` parâmetro do atributo para definir ainda mais o padrão. Por exemplo, você pode tornar o padrão diferenciar maiúsculas de minúsculas.

- Se esse atributo for aplicado a uma coleção, cada elemento na coleção deverá corresponder ao padrão.

- O atributo ValidatePattern é definido pela classe [System. Management. Automation. Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute) .

## <a name="see-also"></a>Consulte Também

[System. Management. Automation. Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
