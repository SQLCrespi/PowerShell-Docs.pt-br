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
# <a name="how-to-validate-an-argument-range"></a><span data-ttu-id="227a7-103">Como validar um intervalo de argumentos</span><span class="sxs-lookup"><span data-stu-id="227a7-103">How to Validate an Argument Range</span></span>

<span data-ttu-id="227a7-104">Este exemplo mostra como especificar uma regra de validação que o tempo de execução do Windows PowerShell pode usar para verificar os valores mínimo e máximo do argumento de parâmetro antes de o cmdlet ser executado.</span><span class="sxs-lookup"><span data-stu-id="227a7-104">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the minimum and maximum values of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="227a7-105">Você define essa regra de validação declarando o atributo ValidateRange.</span><span class="sxs-lookup"><span data-stu-id="227a7-105">You set this validation rule by declaring the ValidateRange attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="227a7-106">Para obter mais informações sobre a classe que define esse atributo, consulte [System. Management. Automation. Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute).</span><span class="sxs-lookup"><span data-stu-id="227a7-106">For more information about the class that defines this attribute, see [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute).</span></span>

### <a name="to-validate-an-argument-range"></a><span data-ttu-id="227a7-107">Para validar um intervalo de argumentos</span><span class="sxs-lookup"><span data-stu-id="227a7-107">To validate an argument range</span></span>

- <span data-ttu-id="227a7-108">Adicione o atributo ValidateRange conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="227a7-108">Add the ValidateRange attribute as shown in the following code.</span></span> <span data-ttu-id="227a7-109">Este exemplo especifica um intervalo de 0 a 5 para o `InputData` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="227a7-109">This example specifies a range of 0 to 5 for the `InputData` parameter.</span></span>

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

<span data-ttu-id="227a7-110">Para obter mais informações sobre como declarar esse atributo, consulte [declaração de atributo ValidateRange](./validaterange-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="227a7-110">For more information about how to declare this attribute, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="227a7-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="227a7-111">See Also</span></span>

[<span data-ttu-id="227a7-112">Declaração de atributo ValidateRange</span><span class="sxs-lookup"><span data-stu-id="227a7-112">ValidateRange Attribute Declaration</span></span>](./validaterange-attribute-declaration.md)

<span data-ttu-id="227a7-113">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="227a7-113">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
