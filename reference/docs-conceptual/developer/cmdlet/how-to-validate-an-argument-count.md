---
ms.date: 09/13/2016
ms.topic: reference
title: Como validar uma contagem de argumentos
description: Como validar uma contagem de argumentos
ms.openlocfilehash: 46a32d61138fb50bceea98171f76749c9d96734d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666936"
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

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
