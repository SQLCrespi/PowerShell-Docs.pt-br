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
# <a name="how-to-validate-an-argument-set"></a><span data-ttu-id="22e31-102">Como validar um conjunto de argumentos</span><span class="sxs-lookup"><span data-stu-id="22e31-102">How to Validate an Argument Set</span></span>

<span data-ttu-id="22e31-103">Este exemplo mostra como especificar uma regra de validação que o tempo de execução do Windows PowerShell pode usar para verificar o argumento de parâmetro antes da execução do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="22e31-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="22e31-104">Essa regra de validação fornece um conjunto de valores válidos para o argumento de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="22e31-104">This validation rule provides a set of the valid values for the parameter argument.</span></span>

> [!NOTE]
> <span data-ttu-id="22e31-105">Para obter mais informações sobre a classe que define esse atributo, consulte [System. Management. Automation. Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute).</span><span class="sxs-lookup"><span data-stu-id="22e31-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute).</span></span>

## <a name="to-validate-an-argument-set"></a><span data-ttu-id="22e31-106">Para validar um conjunto de argumentos</span><span class="sxs-lookup"><span data-stu-id="22e31-106">To validate an argument set</span></span>

- <span data-ttu-id="22e31-107">Adicione o atributo ValidateSet, conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="22e31-107">Add the ValidateSet attribute as shown in the following code.</span></span> <span data-ttu-id="22e31-108">Este exemplo especifica um conjunto de três valores possíveis para o `UserName` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="22e31-108">This example specifies a set of three possible values for the `UserName` parameter.</span></span>

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

<span data-ttu-id="22e31-109">Para obter mais informações sobre como declarar esse atributo, consulte [declaração de atributo ValidateSet](./validateset-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="22e31-109">For more information about how to declare this attribute, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="22e31-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="22e31-110">See Also</span></span>

[<span data-ttu-id="22e31-111">System. Management. Automation. Validatesetattribute</span><span class="sxs-lookup"><span data-stu-id="22e31-111">System.Management.Automation.Validatesetattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[<span data-ttu-id="22e31-112">Declaração de atributo ValidateSet</span><span class="sxs-lookup"><span data-stu-id="22e31-112">ValidateSet Attribute Declaration</span></span>](./validateset-attribute-declaration.md)

[<span data-ttu-id="22e31-113">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="22e31-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
