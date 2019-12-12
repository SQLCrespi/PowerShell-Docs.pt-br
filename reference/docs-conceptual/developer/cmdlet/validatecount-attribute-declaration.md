---
title: Declaração de atributo ValidateCount | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes, ValidateCount
- ValidateCount attribute, described
- ValidateCount attribute
ms.assetid: 516af1ef-2c2e-408d-84bc-865f5bccf761
caps.latest.revision: 11
ms.openlocfilehash: ffc45f6b80a2b7ed22f27d083d042b1de7f353f6
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369225"
---
# <a name="validatecount-attribute-declaration"></a>Declaração de atributo ValidateCount

O atributo ValidateCount especifica o número mínimo e máximo de argumentos permitidos para um parâmetro de cmdlet.

## <a name="syntax"></a>Sintaxe

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a>Parâmetros

`MinLength` ([System.Int32][]) necessário. Especifica o número mínimo de argumentos.

`MaxLength`([System.Int32][]) necessário. Especifica o número máximo de argumentos.

## <a name="remarks"></a>Comentários

- Para obter mais informações sobre como declarar esse atributo, consulte [como validar uma contagem de argumentos][].

- Quando esse atributo não é invocado, o parâmetro de cmdlet correspondente pode ter qualquer número de argumentos.

- O tempo de execução do Windows PowerShell gera um erro nas seguintes condições:

    - Os parâmetros de atributo `MinLength` e `MaxLength` não são do tipo [System.Int32][].

    - O valor do parâmetro de atributo `MaxLength` é menor que o valor do parâmetro de atributo `MinLength`.

- O atributo ValidateCount é definido pela classe [System. Management. Automation. ValidateCountAttribute][] .

## <a name="see-also"></a>Consulte Também

[System. Management. Automation. ValidateCountAttribute][]

[Como validar uma contagem de argumentos][]

[Writing a Windows PowerShell Cmdlet][] (Escrevendo um Cmdlet do Windows PowerShell)

[Como validar uma contagem de argumentos]: how-to-validate-an-argument-count.md
[Writing a Windows PowerShell Cmdlet]: writing-a-windows-powershell-cmdlet.md (Escrevendo um Cmdlet do Windows PowerShell)

[System.Int32]: /dotnet/api/System.Int32
[System. Management. Automation. ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
