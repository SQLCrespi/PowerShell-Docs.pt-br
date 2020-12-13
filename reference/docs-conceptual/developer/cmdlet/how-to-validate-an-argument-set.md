---
ms.date: 09/13/2016
ms.topic: reference
title: Como validar um conjunto de argumentos
description: Como validar um conjunto de argumentos
ms.openlocfilehash: 50ec0a48277893584d896e14ad6aa843682a28cc
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92650376"
---
# <a name="how-to-validate-an-argument-set"></a><span data-ttu-id="8a25b-103">Como validar um conjunto de argumentos</span><span class="sxs-lookup"><span data-stu-id="8a25b-103">How to Validate an Argument Set</span></span>

<span data-ttu-id="8a25b-104">Este exemplo mostra como especificar uma regra de validação que o tempo de execução do Windows PowerShell pode usar para verificar o argumento de parâmetro antes da execução do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8a25b-104">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="8a25b-105">Essa regra de validação fornece um conjunto de valores válidos para o argumento de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8a25b-105">This validation rule provides a set of the valid values for the parameter argument.</span></span>

> [!NOTE]
> <span data-ttu-id="8a25b-106">Para obter mais informações sobre a classe que define esse atributo, consulte [System. Management. Automation. Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute).</span><span class="sxs-lookup"><span data-stu-id="8a25b-106">For more information about the class that defines this attribute, see [System.Management.Automation.Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute).</span></span>

## <a name="to-validate-an-argument-set"></a><span data-ttu-id="8a25b-107">Para validar um conjunto de argumentos</span><span class="sxs-lookup"><span data-stu-id="8a25b-107">To validate an argument set</span></span>

- <span data-ttu-id="8a25b-108">Adicione o atributo ValidateSet, conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="8a25b-108">Add the ValidateSet attribute as shown in the following code.</span></span> <span data-ttu-id="8a25b-109">Este exemplo especifica um conjunto de três valores possíveis para o `UserName` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8a25b-109">This example specifies a set of three possible values for the `UserName` parameter.</span></span>

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

<span data-ttu-id="8a25b-110">Para obter mais informações sobre como declarar esse atributo, consulte [declaração de atributo ValidateSet](./validateset-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="8a25b-110">For more information about how to declare this attribute, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8a25b-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8a25b-111">See Also</span></span>

[<span data-ttu-id="8a25b-112">System. Management. Automation. Validatesetattribute</span><span class="sxs-lookup"><span data-stu-id="8a25b-112">System.Management.Automation.Validatesetattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[<span data-ttu-id="8a25b-113">Declaração de atributo ValidateSet</span><span class="sxs-lookup"><span data-stu-id="8a25b-113">ValidateSet Attribute Declaration</span></span>](./validateset-attribute-declaration.md)

<span data-ttu-id="8a25b-114">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="8a25b-114">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
