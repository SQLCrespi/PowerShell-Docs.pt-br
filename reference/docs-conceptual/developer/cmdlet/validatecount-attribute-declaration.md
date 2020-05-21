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
ms.openlocfilehash: 3cae95fab30a4abe4e544ed5cb7dadc9f4debf02
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692379"
---
# <a name="validatecount-attribute-declaration"></a>Declaração de atributo ValidateCount

O atributo ValidateCount especifica o número mínimo e máximo de argumentos permitidos para um parâmetro de cmdlet.

## <a name="syntax"></a>Sintaxe

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a>Parâmetros

`MinLength`([System. Int32][]) necessário. Especifica o número mínimo de argumentos.

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

[Escrevendo um Cmdlet do Windows PowerShell][]

[Como validar uma contagem de argumentos]: how-to-validate-an-argument-count.md
[Escrevendo um Cmdlet do Windows PowerShell]: writing-a-windows-powershell-cmdlet.md

[System. Int32]: /dotnet/api/System.Int32
[System. Management. Automation. ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
