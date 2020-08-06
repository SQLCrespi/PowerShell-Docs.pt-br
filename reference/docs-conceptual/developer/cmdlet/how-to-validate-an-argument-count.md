---
title: Como validar uma contagem de argumentos | Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateCount attribute, example
ms.openlocfilehash: e7c0eb364a6975cec089b984c2100d476631a12d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782116"
---
# <a name="how-to-validate-an-argument-count"></a>Como validar uma contagem de argumentos

Este exemplo mostra como especificar uma regra de validação que o tempo de execução do Windows PowerShell pode usar para verificar o número de argumentos (a contagem) que um parâmetro aceita antes de o cmdlet ser executado. Você define essa regra de validação declarando o atributo ValidateCount.

> [!NOTE]
> Para obter mais informações sobre a classe que define esse atributo, consulte [System. Management. Automation. Validatecountattribute](/dotnet/api/System.Management.Automation.ValidateCountAttribute).

## <a name="to-validate-an-argument-count"></a>Para validar uma contagem de argumentos

- Adicione o atributo Validate conforme mostrado no código a seguir. Este exemplo especifica que o parâmetro aceitará um argumento ou até três argumentos.

    ```csharp
    [ValidateCount(1, 3)]
    [Parameter(Position = 0, Mandatory = true)]
    public string[] UserNames
    {
      get { return userNames; }
      set { userNames = value; }
    }

    private string[] userNames;
    ```

Para obter mais informações sobre como declarar esse atributo, consulte [declaração de atributo ValidateCount](./validatecount-attribute-declaration.md).

## <a name="see-also"></a>Consulte Também

[Declaração de atributo ValidateCount](./validatecount-attribute-declaration.md)

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
