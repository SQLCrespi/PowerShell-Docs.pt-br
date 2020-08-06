---
title: Tipos de atributo | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 96fdd38ba10eb748ab0762f0c910463dd472494d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782371"
---
# <a name="attribute-types"></a>Tipos de atributo

Os atributos de cmdlet podem ser agrupados por funcionalidade.
As seções a seguir descrevem os atributos disponíveis e descrevem o que o tempo de execução faz quando o atributo é invocado.

## <a name="cmdlet-attributes"></a>Atributos de cmdlet

### <a name="cmdlet"></a>Cmdlet

Identifica uma classe de .NET Framework como um cmdlet.
Esse é o atributo base obrigatório.
Para obter mais informações, consulte [declaração de atributo de cmdlet](./cmdlet-attribute-declaration.md).

## <a name="parameter-attributes"></a>Atributos de parâmetro

### <a name="parameter"></a>Parâmetro

Identifica uma propriedade pública na classe cmdlet como um parâmetro de cmdlet.
Para obter mais informações, consulte [declaração de atributo de parâmetro](./parameter-attribute-declaration.md).

### <a name="alias"></a>Alias

Especifica um ou mais aliases para um parâmetro.
Para obter mais informações, consulte [declaração de atributo de alias](./alias-attribute-declaration.md).

## <a name="argument-validation-attributes"></a>Atributos de validação de argumento

### <a name="validatecount"></a>ValidateCount

Especifica o número mínimo e máximo de argumentos permitidos para um parâmetro de cmdlet.
Para obter mais informações, consulte [declaração de atributo ValidateCount](./validatecount-attribute-declaration.md).

### <a name="validatelength"></a>ValidateLength

Especifica um número mínimo e máximo de caracteres para um argumento de parâmetro de cmdlet.
Para obter mais informações, consulte [declaração de atributo ValidateLength](./validatelength-attribute-declaration.md).

### <a name="validatepattern"></a>ValidatePattern

Especifica um padrão de expressão regular que o argumento do parâmetro cmdlet deve corresponder.
Para obter mais informações, consulte [declaração de atributo ValidatePattern](./validatepattern-attribute-declaration.md).

### <a name="validaterange"></a>ValidateRange

Especifica os valores mínimo e máximo para um argumento de parâmetro de cmdlet.
Para obter mais informações, consulte [declaração de atributo ValidateRange](./validaterange-attribute-declaration.md).

### <a name="validateset"></a>ValidateSet

Especifica um conjunto de valores válidos para o argumento de parâmetro cmdlet.
Para obter mais informações, consulte [declaração de atributo ValidateSet](./validateset-attribute-declaration.md).

## <a name="see-also"></a>Consulte Também

[SDK do Windows PowerShell](../windows-powershell-reference.md)
