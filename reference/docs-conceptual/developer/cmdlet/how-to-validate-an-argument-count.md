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
# <a name="how-to-validate-an-argument-count"></a><span data-ttu-id="b5cfe-102">Como validar uma contagem de argumentos</span><span class="sxs-lookup"><span data-stu-id="b5cfe-102">How to Validate an Argument Count</span></span>

<span data-ttu-id="b5cfe-103">Este exemplo mostra como especificar uma regra de validação que o tempo de execução do Windows PowerShell pode usar para verificar o número de argumentos (a contagem) que um parâmetro aceita antes de o cmdlet ser executado.</span><span class="sxs-lookup"><span data-stu-id="b5cfe-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the number of arguments (the count) that a parameter accepts before the cmdlet is run.</span></span> <span data-ttu-id="b5cfe-104">Você define essa regra de validação declarando o atributo ValidateCount.</span><span class="sxs-lookup"><span data-stu-id="b5cfe-104">You set this validation rule by declaring the ValidateCount attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="b5cfe-105">Para obter mais informações sobre a classe que define esse atributo, consulte [System. Management. Automation. Validatecountattribute](/dotnet/api/System.Management.Automation.ValidateCountAttribute).</span><span class="sxs-lookup"><span data-stu-id="b5cfe-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validatecountattribute](/dotnet/api/System.Management.Automation.ValidateCountAttribute).</span></span>

## <a name="to-validate-an-argument-count"></a><span data-ttu-id="b5cfe-106">Para validar uma contagem de argumentos</span><span class="sxs-lookup"><span data-stu-id="b5cfe-106">To validate an argument count</span></span>

- <span data-ttu-id="b5cfe-107">Adicione o atributo Validate conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="b5cfe-107">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="b5cfe-108">Este exemplo especifica que o parâmetro aceitará um argumento ou até três argumentos.</span><span class="sxs-lookup"><span data-stu-id="b5cfe-108">This example specifies that the parameter will accept one argument or as many as three arguments.</span></span>

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

<span data-ttu-id="b5cfe-109">Para obter mais informações sobre como declarar esse atributo, consulte [declaração de atributo ValidateCount](./validatecount-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="b5cfe-109">For more information about how to declare this attribute, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b5cfe-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b5cfe-110">See Also</span></span>

[<span data-ttu-id="b5cfe-111">Declaração de atributo ValidateCount</span><span class="sxs-lookup"><span data-stu-id="b5cfe-111">ValidateCount Attribute Declaration</span></span>](./validatecount-attribute-declaration.md)

[<span data-ttu-id="b5cfe-112">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5cfe-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
