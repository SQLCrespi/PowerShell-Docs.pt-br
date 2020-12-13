---
ms.date: 09/13/2016
ms.topic: reference
title: Como validar o tamanho do argumento
description: Como validar o tamanho do argumento
ms.openlocfilehash: 460aedbe6847033f976cb7bf70b6c77ac5a3a3c9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652637"
---
# <a name="how-to-validate-the-argument-length"></a>Como validar o tamanho do argumento

Este exemplo mostra como especificar uma regra de validação que o tempo de execução do Windows PowerShell pode usar para verificar o número de caracteres (o comprimento) do argumento de parâmetro antes de o cmdlet ser executado. Você define essa regra de validação declarando o atributo ValidateLength.

> [!NOTE]
> Para obter mais informações sobre a classe que define esse atributo, consulte [System. Management. Automation. Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute).

## <a name="to-validate-the-argument-length"></a>Para validar o comprimento do argumento

- Adicione o atributo Validate conforme mostrado no código a seguir. Este exemplo especifica que o comprimento do argumento deve ter um comprimento de 0 a 10 caracteres.

    ```csharp
    [ValidateLength(0, 10)]
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

Para obter mais informações sobre como declarar esse atributo, consulte [declaração de atributo ValidateLength](./validatelength-attribute-declaration.md).

## <a name="see-also"></a>Consulte Também

[Declaração de atributo ValidateLength](./validatelength-attribute-declaration.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
