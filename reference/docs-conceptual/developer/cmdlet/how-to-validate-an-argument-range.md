---
ms.date: 09/13/2016
ms.topic: reference
title: Como validar um intervalo de argumentos
description: Como validar um intervalo de argumentos
ms.openlocfilehash: 1c1c53d43350a38beb2193200de3bd6b689366a4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666918"
---
# <a name="how-to-validate-an-argument-range"></a>Como validar um intervalo de argumentos

Este exemplo mostra como especificar uma regra de validação que o tempo de execução do Windows PowerShell pode usar para verificar os valores mínimo e máximo do argumento de parâmetro antes de o cmdlet ser executado. Você define essa regra de validação declarando o atributo ValidateRange.

> [!NOTE]
> Para obter mais informações sobre a classe que define esse atributo, consulte [System. Management. Automation. Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute).

### <a name="to-validate-an-argument-range"></a>Para validar um intervalo de argumentos

- Adicione o atributo ValidateRange conforme mostrado no código a seguir. Este exemplo especifica um intervalo de 0 a 5 para o `InputData` parâmetro.

    ```csharp
    [ValidateRange(0, 5)]
    [Parameter(Position = 0, Mandatory = true)]
    public int InputData
    {
      get { return inputData; }
      set { inputData = value; }
    }
    private int inputData;
    ```

Para obter mais informações sobre como declarar esse atributo, consulte [declaração de atributo ValidateRange](./validaterange-attribute-declaration.md).

## <a name="see-also"></a>Consulte Também

[Declaração de atributo ValidateRange](./validaterange-attribute-declaration.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
