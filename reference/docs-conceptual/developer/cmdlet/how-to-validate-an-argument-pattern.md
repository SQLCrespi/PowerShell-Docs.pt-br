---
ms.date: 09/13/2016
ms.topic: reference
title: Como validar um padrão de argumentos
description: Como validar um padrão de argumentos
ms.openlocfilehash: ab5777c918a53c0a3900f87c52e7f14f9cb9b726
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666902"
---
# <a name="how-to-validate-an-argument-pattern"></a><span data-ttu-id="1d314-103">Como validar um padrão de argumentos</span><span class="sxs-lookup"><span data-stu-id="1d314-103">How to Validate an Argument Pattern</span></span>

<span data-ttu-id="1d314-104">Este exemplo mostra como especificar uma regra de validação que o tempo de execução do Windows PowerShell pode usar para verificar o padrão de caractere do argumento de parâmetro antes de o cmdlet ser executado.</span><span class="sxs-lookup"><span data-stu-id="1d314-104">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the character pattern of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="1d314-105">Você define essa regra de validação declarando o atributo ValidatePattern.</span><span class="sxs-lookup"><span data-stu-id="1d314-105">You set this validation rule by declaring the ValidatePattern attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="1d314-106">Para obter mais informações sobre a classe que define esse atributo, consulte [System. Management. Automation. Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute).</span><span class="sxs-lookup"><span data-stu-id="1d314-106">For more information about the class that defines this attribute, see [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute).</span></span>

## <a name="to-validate-an-argument-pattern"></a><span data-ttu-id="1d314-107">Para validar um padrão de argumento</span><span class="sxs-lookup"><span data-stu-id="1d314-107">To validate an argument pattern</span></span>

- <span data-ttu-id="1d314-108">Adicione o atributo Validate conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="1d314-108">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="1d314-109">Este exemplo especifica um padrão de quatro dígitos, onde cada dígito tem um valor de 0 a 9.</span><span class="sxs-lookup"><span data-stu-id="1d314-109">This example specifies a pattern of four digits, where each digit has a value of 0 through 9.</span></span>

    ```csharp
    [ValidatePattern("[0-9][0-9][0-9][0-9]")]
    [Parameter(Position = 0, Mandatory = true)]
    public int InputData
    {
      get { return inputData; }
      set { inputData = value; }
    }

    private int inputData;
    ```

<span data-ttu-id="1d314-110">Para obter mais informações sobre como declarar esse atributo, consulte [declaração de atributo ValidatePattern](./validatepattern-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="1d314-110">For more information about how to declare this attribute, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1d314-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1d314-111">See Also</span></span>

[<span data-ttu-id="1d314-112">Declaração de atributo ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="1d314-112">ValidatePattern Attribute Declaration</span></span>](./validatepattern-attribute-declaration.md)

<span data-ttu-id="1d314-113">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="1d314-113">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
