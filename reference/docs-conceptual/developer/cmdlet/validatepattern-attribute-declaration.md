---
title: Declaração de atributo ValidatePattern | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes, ValidatePattern
- ValidatePattern attribute, described
- ValidatePattern attribute
ms.assetid: 87b811be-6d93-4e7d-b9d0-c567a19bb0ef
caps.latest.revision: 13
ms.openlocfilehash: 5edcb65a6fbe1cb2fe2d0efe3f763fb84628b049
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369155"
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

- Você pode usar o parâmetro `Option` do atributo para definir ainda mais o padrão. Por exemplo, você pode tornar o padrão diferenciar maiúsculas de minúsculas.

- Se esse atributo for aplicado a uma coleção, cada elemento na coleção deverá corresponder ao padrão.

- O atributo ValidatePattern é definido pela classe [System. Management. Automation. Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute) .

## <a name="see-also"></a>Consulte Também

[System. Management. Automation. Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
