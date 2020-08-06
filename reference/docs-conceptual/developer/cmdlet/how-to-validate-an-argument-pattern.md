---
title: Como validar um padrão de argumento | Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- ValidatePattern attribute, example
ms.openlocfilehash: 35104e786d4b809a711d97fea52ae0e348dd5ca3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782082"
---
# <a name="how-to-validate-an-argument-pattern"></a><span data-ttu-id="53dd1-102">Como validar um padrão de argumentos</span><span class="sxs-lookup"><span data-stu-id="53dd1-102">How to Validate an Argument Pattern</span></span>

<span data-ttu-id="53dd1-103">Este exemplo mostra como especificar uma regra de validação que o tempo de execução do Windows PowerShell pode usar para verificar o padrão de caractere do argumento de parâmetro antes de o cmdlet ser executado.</span><span class="sxs-lookup"><span data-stu-id="53dd1-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the character pattern of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="53dd1-104">Você define essa regra de validação declarando o atributo ValidatePattern.</span><span class="sxs-lookup"><span data-stu-id="53dd1-104">You set this validation rule by declaring the ValidatePattern attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="53dd1-105">Para obter mais informações sobre a classe que define esse atributo, consulte [System. Management. Automation. Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute).</span><span class="sxs-lookup"><span data-stu-id="53dd1-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute).</span></span>

## <a name="to-validate-an-argument-pattern"></a><span data-ttu-id="53dd1-106">Para validar um padrão de argumento</span><span class="sxs-lookup"><span data-stu-id="53dd1-106">To validate an argument pattern</span></span>

- <span data-ttu-id="53dd1-107">Adicione o atributo Validate conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="53dd1-107">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="53dd1-108">Este exemplo especifica um padrão de quatro dígitos, onde cada dígito tem um valor de 0 a 9.</span><span class="sxs-lookup"><span data-stu-id="53dd1-108">This example specifies a pattern of four digits, where each digit has a value of 0 through 9.</span></span>

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

<span data-ttu-id="53dd1-109">Para obter mais informações sobre como declarar esse atributo, consulte [declaração de atributo ValidatePattern](./validatepattern-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="53dd1-109">For more information about how to declare this attribute, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="53dd1-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="53dd1-110">See Also</span></span>

[<span data-ttu-id="53dd1-111">Declaração de atributo ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="53dd1-111">ValidatePattern Attribute Declaration</span></span>](./validatepattern-attribute-declaration.md)

[<span data-ttu-id="53dd1-112">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="53dd1-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
