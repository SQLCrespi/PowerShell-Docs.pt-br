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
# <a name="how-to-validate-an-argument-count"></a><span data-ttu-id="51ae8-103">Como validar uma contagem de argumentos</span><span class="sxs-lookup"><span data-stu-id="51ae8-103">How to Validate an Argument Count</span></span>

<span data-ttu-id="51ae8-104">Este exemplo mostra como especificar uma regra de validação que o tempo de execução do Windows PowerShell pode usar para verificar o número de argumentos (a contagem) que um parâmetro aceita antes de o cmdlet ser executado.</span><span class="sxs-lookup"><span data-stu-id="51ae8-104">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the number of arguments (the count) that a parameter accepts before the cmdlet is run.</span></span> <span data-ttu-id="51ae8-105">Você define essa regra de validação declarando o atributo ValidateCount.</span><span class="sxs-lookup"><span data-stu-id="51ae8-105">You set this validation rule by declaring the ValidateCount attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="51ae8-106">Para obter mais informações sobre a classe que define esse atributo, consulte [System. Management. Automation. Validatecountattribute](/dotnet/api/System.Management.Automation.ValidateCountAttribute).</span><span class="sxs-lookup"><span data-stu-id="51ae8-106">For more information about the class that defines this attribute, see [System.Management.Automation.Validatecountattribute](/dotnet/api/System.Management.Automation.ValidateCountAttribute).</span></span>

## <a name="to-validate-an-argument-count"></a><span data-ttu-id="51ae8-107">Para validar uma contagem de argumentos</span><span class="sxs-lookup"><span data-stu-id="51ae8-107">To validate an argument count</span></span>

- <span data-ttu-id="51ae8-108">Adicione o atributo Validate conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="51ae8-108">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="51ae8-109">Este exemplo especifica que o parâmetro aceitará um argumento ou até três argumentos.</span><span class="sxs-lookup"><span data-stu-id="51ae8-109">This example specifies that the parameter will accept one argument or as many as three arguments.</span></span>

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

<span data-ttu-id="51ae8-110">Para obter mais informações sobre como declarar esse atributo, consulte [declaração de atributo ValidateCount](./validatecount-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="51ae8-110">For more information about how to declare this attribute, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="51ae8-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="51ae8-111">See Also</span></span>

[<span data-ttu-id="51ae8-112">Declaração de atributo ValidateCount</span><span class="sxs-lookup"><span data-stu-id="51ae8-112">ValidateCount Attribute Declaration</span></span>](./validatecount-attribute-declaration.md)

<span data-ttu-id="51ae8-113">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="51ae8-113">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
