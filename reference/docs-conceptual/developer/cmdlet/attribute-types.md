---
title: Tipos de atributo | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b1026ad-f072-4fca-8052-a2d8eb491c2a
caps.latest.revision: 6
ms.openlocfilehash: 52c75b3ca73706da39029d5b3ead52ff7197a5f1
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364575"
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
