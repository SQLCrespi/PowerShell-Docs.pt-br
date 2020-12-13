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
# <a name="how-to-validate-the-argument-length"></a><span data-ttu-id="a381d-103">Como validar o tamanho do argumento</span><span class="sxs-lookup"><span data-stu-id="a381d-103">How to Validate the Argument Length</span></span>

<span data-ttu-id="a381d-104">Este exemplo mostra como especificar uma regra de validação que o tempo de execução do Windows PowerShell pode usar para verificar o número de caracteres (o comprimento) do argumento de parâmetro antes de o cmdlet ser executado.</span><span class="sxs-lookup"><span data-stu-id="a381d-104">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the number of characters (the length) of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="a381d-105">Você define essa regra de validação declarando o atributo ValidateLength.</span><span class="sxs-lookup"><span data-stu-id="a381d-105">You set this validation rule by declaring the ValidateLength attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="a381d-106">Para obter mais informações sobre a classe que define esse atributo, consulte [System. Management. Automation. Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute).</span><span class="sxs-lookup"><span data-stu-id="a381d-106">For more information about the class that defines this attribute, see [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute).</span></span>

## <a name="to-validate-the-argument-length"></a><span data-ttu-id="a381d-107">Para validar o comprimento do argumento</span><span class="sxs-lookup"><span data-stu-id="a381d-107">To validate the argument length</span></span>

- <span data-ttu-id="a381d-108">Adicione o atributo Validate conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="a381d-108">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="a381d-109">Este exemplo especifica que o comprimento do argumento deve ter um comprimento de 0 a 10 caracteres.</span><span class="sxs-lookup"><span data-stu-id="a381d-109">This example specifies that the length of the argument should have a length of 0 to 10 characters.</span></span>

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

<span data-ttu-id="a381d-110">Para obter mais informações sobre como declarar esse atributo, consulte [declaração de atributo ValidateLength](./validatelength-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="a381d-110">For more information about how to declare this attribute, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a381d-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a381d-111">See Also</span></span>

[<span data-ttu-id="a381d-112">Declaração de atributo ValidateLength</span><span class="sxs-lookup"><span data-stu-id="a381d-112">ValidateLength Attribute Declaration</span></span>](./validatelength-attribute-declaration.md)

<span data-ttu-id="a381d-113">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="a381d-113">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
