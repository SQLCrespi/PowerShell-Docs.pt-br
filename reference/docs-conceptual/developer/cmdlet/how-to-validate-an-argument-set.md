---
title: Como validar um conjunto de argumentos | Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateSet attribute, example
ms.openlocfilehash: 6173f1380583f5b27e2b188990a5ea041f447c57
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781997"
---
# <a name="how-to-validate-an-argument-set"></a>Como validar um conjunto de argumentos

Este exemplo mostra como especificar uma regra de validação que o tempo de execução do Windows PowerShell pode usar para verificar o argumento de parâmetro antes da execução do cmdlet. Essa regra de validação fornece um conjunto de valores válidos para o argumento de parâmetro.

> [!NOTE]
> Para obter mais informações sobre a classe que define esse atributo, consulte [System. Management. Automation. Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute).

## <a name="to-validate-an-argument-set"></a>Para validar um conjunto de argumentos

- Adicione o atributo ValidateSet, conforme mostrado no código a seguir. Este exemplo especifica um conjunto de três valores possíveis para o `UserName` parâmetro.

    ```csharp
    [ValidateSet("Steve", "Mary", "Carl", IgnoreCase = true)]
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }

    private string userName;
    ```

Para obter mais informações sobre como declarar esse atributo, consulte [declaração de atributo ValidateSet](./validateset-attribute-declaration.md).

## <a name="see-also"></a>Consulte Também

[System. Management. Automation. Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[Declaração de atributo ValidateSet](./validateset-attribute-declaration.md)

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
