---
title: Como validar um padrão de argumento | Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- ValidatePattern attribute, example
ms.openlocfilehash: 35104e786d4b809a711d97fea52ae0e348dd5ca3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782082"
---
# <a name="how-to-validate-an-argument-pattern"></a>Como validar um padrão de argumentos

Este exemplo mostra como especificar uma regra de validação que o tempo de execução do Windows PowerShell pode usar para verificar o padrão de caractere do argumento de parâmetro antes de o cmdlet ser executado. Você define essa regra de validação declarando o atributo ValidatePattern.

> [!NOTE]
> Para obter mais informações sobre a classe que define esse atributo, consulte [System. Management. Automation. Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute).

## <a name="to-validate-an-argument-pattern"></a>Para validar um padrão de argumento

- Adicione o atributo Validate conforme mostrado no código a seguir. Este exemplo especifica um padrão de quatro dígitos, onde cada dígito tem um valor de 0 a 9.

    ```csharp
    [ValidatePattern("[0-9][0-9][0-9][0-9]")]
    [Parameter(Position = 0, Mandatory = true)]
    public int InputData
    {
      get { return inputData; }
      set { inputData = value; }
    }

    private int inputData;
    ```

Para obter mais informações sobre como declarar esse atributo, consulte [declaração de atributo ValidatePattern](./validatepattern-attribute-declaration.md).

## <a name="see-also"></a>Consulte Também

[Declaração de atributo ValidatePattern](./validatepattern-attribute-declaration.md)

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
