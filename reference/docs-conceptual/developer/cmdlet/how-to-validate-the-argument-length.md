---
title: Como validar o comprimento do argumento | Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateLength attribute, example
ms.openlocfilehash: aa0545def6d9628f6b41090a425f0c5af25f6ad7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784071"
---
# <a name="how-to-validate-the-argument-length"></a><span data-ttu-id="56a8f-102">Como validar o tamanho do argumento</span><span class="sxs-lookup"><span data-stu-id="56a8f-102">How to Validate the Argument Length</span></span>

<span data-ttu-id="56a8f-103">Este exemplo mostra como especificar uma regra de validação que o tempo de execução do Windows PowerShell pode usar para verificar o número de caracteres (o comprimento) do argumento de parâmetro antes de o cmdlet ser executado.</span><span class="sxs-lookup"><span data-stu-id="56a8f-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the number of characters (the length) of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="56a8f-104">Você define essa regra de validação declarando o atributo ValidateLength.</span><span class="sxs-lookup"><span data-stu-id="56a8f-104">You set this validation rule by declaring the ValidateLength attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="56a8f-105">Para obter mais informações sobre a classe que define esse atributo, consulte [System. Management. Automation. Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute).</span><span class="sxs-lookup"><span data-stu-id="56a8f-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute).</span></span>

## <a name="to-validate-the-argument-length"></a><span data-ttu-id="56a8f-106">Para validar o comprimento do argumento</span><span class="sxs-lookup"><span data-stu-id="56a8f-106">To validate the argument length</span></span>

- <span data-ttu-id="56a8f-107">Adicione o atributo Validate conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="56a8f-107">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="56a8f-108">Este exemplo especifica que o comprimento do argumento deve ter um comprimento de 0 a 10 caracteres.</span><span class="sxs-lookup"><span data-stu-id="56a8f-108">This example specifies that the length of the argument should have a length of 0 to 10 characters.</span></span>

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

<span data-ttu-id="56a8f-109">Para obter mais informações sobre como declarar esse atributo, consulte [declaração de atributo ValidateLength](./validatelength-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="56a8f-109">For more information about how to declare this attribute, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="56a8f-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="56a8f-110">See Also</span></span>

[<span data-ttu-id="56a8f-111">Declaração de atributo ValidateLength</span><span class="sxs-lookup"><span data-stu-id="56a8f-111">ValidateLength Attribute Declaration</span></span>](./validatelength-attribute-declaration.md)

[<span data-ttu-id="56a8f-112">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="56a8f-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
