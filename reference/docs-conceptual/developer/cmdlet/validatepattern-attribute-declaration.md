---
ms.date: 09/13/2016
ms.topic: reference
title: Declaração de atributo ValidatePattern
description: Declaração de atributo ValidatePattern
ms.openlocfilehash: 364f63d2c52563eaefe64bcbb2bbae511bccb074
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646176"
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

`RegexString` ([System. String](/dotnet/api/System.String)) necessário. Especifica uma expressão regular que valida o argumento do parâmetro.

Opções ([System. Text. RegularExpressions. RegexOptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) parâmetro nomeado opcional. Especifica uma combinação de bits-bit que indica os sinalizadores [System. Text. RegularExpressions. RegexOptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions) que especificam opções de expressão regular.

## <a name="remarks"></a>Comentários

- Esse atributo pode ser usado apenas uma vez por parâmetro.

- Você pode usar o `Option` parâmetro do atributo para definir ainda mais o padrão. Por exemplo, você pode tornar o padrão diferenciar maiúsculas de minúsculas.

- Se esse atributo for aplicado a uma coleção, cada elemento na coleção deverá corresponder ao padrão.

- O atributo ValidatePattern é definido pela classe [System. Management. Automation. Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute) .

## <a name="see-also"></a>Consulte Também

[System. Management. Automation. Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
