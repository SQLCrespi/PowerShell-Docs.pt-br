---
title: Como escrever um cmdlet simples | Microsoft Docs
ms.custom: ''
ms.date: 01/15/2019
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 137543d8-0012-4cba-bcd6-98b25aac83bb
caps.latest.revision: 9
ms.openlocfilehash: 9bd72e8f97c194c98adb1049f5a966549113fd12
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83563901"
---
# <a name="how-to-write-a-cmdlet"></a><span data-ttu-id="77fa3-102">Como escrever um cmdlet</span><span class="sxs-lookup"><span data-stu-id="77fa3-102">How to write a cmdlet</span></span>

<span data-ttu-id="77fa3-103">Este artigo mostra como escrever um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="77fa3-103">This article shows how to write a cmdlet.</span></span> <span data-ttu-id="77fa3-104">O `Send-Greeting` cmdlet usa um único nome de usuário como entrada e, em seguida, grava uma saudação para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="77fa3-104">The `Send-Greeting` cmdlet takes a single user name as input and then writes a greeting to that user.</span></span> <span data-ttu-id="77fa3-105">Embora o cmdlet não faça muito trabalho, este exemplo demonstra as principais seções de um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="77fa3-105">Although the cmdlet does not do much work, this example demonstrates the major sections of a cmdlet.</span></span>

## <a name="steps-to-write-a-cmdlet"></a><span data-ttu-id="77fa3-106">Etapas para gravar um cmdlet</span><span class="sxs-lookup"><span data-stu-id="77fa3-106">Steps to write a cmdlet</span></span>

1. <span data-ttu-id="77fa3-107">Para declarar a classe como um cmdlet, use o atributo **cmdlet** .</span><span class="sxs-lookup"><span data-stu-id="77fa3-107">To declare the class as a cmdlet, use the **Cmdlet** attribute.</span></span> <span data-ttu-id="77fa3-108">O atributo **cmdlet** especifica o verbo e o substantivo para o nome do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="77fa3-108">The **Cmdlet** attribute specifies the verb and the noun for the cmdlet name.</span></span>

   <span data-ttu-id="77fa3-109">Para obter mais informações sobre o atributo de **cmdlet** , consulte [declaração de CmdletAttribute](cmdlet-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="77fa3-109">For more information about the **Cmdlet** attribute, see [CmdletAttribute Declaration](cmdlet-attribute-declaration.md).</span></span>

2. <span data-ttu-id="77fa3-110">Especifique o nome da classe.</span><span class="sxs-lookup"><span data-stu-id="77fa3-110">Specify the name of the class.</span></span>

3. <span data-ttu-id="77fa3-111">Especifique que o cmdlet deriva de qualquer uma das seguintes classes:</span><span class="sxs-lookup"><span data-stu-id="77fa3-111">Specify that the cmdlet derives from either of the following classes:</span></span>

   * [<span data-ttu-id="77fa3-112">System. Management. Automation. cmdlet</span><span class="sxs-lookup"><span data-stu-id="77fa3-112">System.Management.Automation.Cmdlet</span></span>](/dotnet/api/System.Management.Automation.Cmdlet)
   * [<span data-ttu-id="77fa3-113">System. Management. Automation. PSCmdlet</span><span class="sxs-lookup"><span data-stu-id="77fa3-113">System.Management.Automation.PSCmdlet</span></span>](/dotnet/api/System.Management.Automation.PSCmdlet)

4. <span data-ttu-id="77fa3-114">Para definir os parâmetros para o cmdlet, use o atributo **Parameter** .</span><span class="sxs-lookup"><span data-stu-id="77fa3-114">To define the parameters for the cmdlet, use the **Parameter** attribute.</span></span> <span data-ttu-id="77fa3-115">Nesse caso, apenas um parâmetro obrigatório é especificado.</span><span class="sxs-lookup"><span data-stu-id="77fa3-115">In this case, only one required parameter is specified.</span></span>

   <span data-ttu-id="77fa3-116">Para obter mais informações sobre o atributo **Parameter** , consulte a [declaração ParameterAttribute](parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="77fa3-116">For more information about the **Parameter** attribute, see [ParameterAttribute Declaration](parameter-attribute-declaration.md).</span></span>

5. <span data-ttu-id="77fa3-117">Substitua o método de processamento de entrada que processa a entrada.</span><span class="sxs-lookup"><span data-stu-id="77fa3-117">Override the input processing method that processes the input.</span></span> <span data-ttu-id="77fa3-118">Nesse caso, o método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) é substituído.</span><span class="sxs-lookup"><span data-stu-id="77fa3-118">In this case, the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method is overridden.</span></span>

6. <span data-ttu-id="77fa3-119">Para gravar a saudação, use o método [System. Management. Automation. cmdlet. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject).</span><span class="sxs-lookup"><span data-stu-id="77fa3-119">To write the greeting, use the method [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject).</span></span>
   <span data-ttu-id="77fa3-120">A saudação é exibida no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="77fa3-120">The greeting is displayed in the following format:</span></span>

   ```Output
   Hello <UserName>!
   ```

## <a name="example"></a><span data-ttu-id="77fa3-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="77fa3-121">Example</span></span>

```csharp
using System.Management.Automation;  // Windows PowerShell assembly.

namespace SendGreeting
{
  // Declare the class as a cmdlet and specify the
  // appropriate verb and noun for the cmdlet name.
  [Cmdlet(VerbsCommunications.Send, "Greeting")]
  public class SendGreetingCommand : Cmdlet
  {
    // Declare the parameters for the cmdlet.
    [Parameter(Mandatory=true)]
    public string Name
    {
      get { return name; }
      set { name = value; }
    }
    private string name;

    // Override the ProcessRecord method to process
    // the supplied user name and write out a
    // greeting to the user by calling the WriteObject
    // method.
    protected override void ProcessRecord()
    {
      WriteObject("Hello " + name + "!");
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="77fa3-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="77fa3-122">See also</span></span>

[<span data-ttu-id="77fa3-123">System. Management. Automation. cmdlet</span><span class="sxs-lookup"><span data-stu-id="77fa3-123">System.Management.Automation.Cmdlet</span></span>](/dotnet/api/System.Management.Automation.Cmdlet)

[<span data-ttu-id="77fa3-124">System. Management. Automation. PSCmdlet</span><span class="sxs-lookup"><span data-stu-id="77fa3-124">System.Management.Automation.PSCmdlet</span></span>](/dotnet/api/System.Management.Automation.PSCmdlet)

[<span data-ttu-id="77fa3-125">System. Management. Automation. cmdlet. ProcessRecord</span><span class="sxs-lookup"><span data-stu-id="77fa3-125">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="77fa3-126">System. Management. Automation. cmdlet. WriteObject</span><span class="sxs-lookup"><span data-stu-id="77fa3-126">System.Management.Automation.Cmdlet.WriteObject</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)

[<span data-ttu-id="77fa3-127">Declaração de CmdletAttribute</span><span class="sxs-lookup"><span data-stu-id="77fa3-127">CmdletAttribute Declaration</span></span>](cmdlet-attribute-declaration.md)

[<span data-ttu-id="77fa3-128">Declaração de ParameterAttribute</span><span class="sxs-lookup"><span data-stu-id="77fa3-128">ParameterAttribute Declaration</span></span>](parameter-attribute-declaration.md)

[<span data-ttu-id="77fa3-129">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="77fa3-129">Writing a Windows PowerShell Cmdlet</span></span>](writing-a-windows-powershell-cmdlet.md)
