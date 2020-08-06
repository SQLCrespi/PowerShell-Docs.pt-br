---
title: Como validar um intervalo de argumentos | Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateRange attribute, example
ms.openlocfilehash: b48b1b87425add51e855c48ec700c78c3ae296c1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782065"
---
# <a name="how-to-validate-an-argument-range"></a><span data-ttu-id="2770d-102">Como validar um intervalo de argumentos</span><span class="sxs-lookup"><span data-stu-id="2770d-102">How to Validate an Argument Range</span></span>

<span data-ttu-id="2770d-103">Este exemplo mostra como especificar uma regra de validação que o tempo de execução do Windows PowerShell pode usar para verificar os valores mínimo e máximo do argumento de parâmetro antes de o cmdlet ser executado.</span><span class="sxs-lookup"><span data-stu-id="2770d-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the minimum and maximum values of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="2770d-104">Você define essa regra de validação declarando o atributo ValidateRange.</span><span class="sxs-lookup"><span data-stu-id="2770d-104">You set this validation rule by declaring the ValidateRange attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="2770d-105">Para obter mais informações sobre a classe que define esse atributo, consulte [System. Management. Automation. Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute).</span><span class="sxs-lookup"><span data-stu-id="2770d-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute).</span></span>

### <a name="to-validate-an-argument-range"></a><span data-ttu-id="2770d-106">Para validar um intervalo de argumentos</span><span class="sxs-lookup"><span data-stu-id="2770d-106">To validate an argument range</span></span>

- <span data-ttu-id="2770d-107">Adicione o atributo ValidateRange conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="2770d-107">Add the ValidateRange attribute as shown in the following code.</span></span> <span data-ttu-id="2770d-108">Este exemplo especifica um intervalo de 0 a 5 para o `InputData` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="2770d-108">This example specifies a range of 0 to 5 for the `InputData` parameter.</span></span>

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

<span data-ttu-id="2770d-109">Para obter mais informações sobre como declarar esse atributo, consulte [declaração de atributo ValidateRange](./validaterange-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="2770d-109">For more information about how to declare this attribute, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2770d-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2770d-110">See Also</span></span>

[<span data-ttu-id="2770d-111">Declaração de atributo ValidateRange</span><span class="sxs-lookup"><span data-stu-id="2770d-111">ValidateRange Attribute Declaration</span></span>](./validaterange-attribute-declaration.md)

[<span data-ttu-id="2770d-112">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2770d-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
