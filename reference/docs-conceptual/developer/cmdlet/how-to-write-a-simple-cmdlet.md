---
ms.date: 01/15/2019
ms.topic: reference
title: Como gravar um cmdlet simples
description: Como gravar um cmdlet simples
ms.openlocfilehash: 59dce5d797f80647e0b70a1f80faf67198652082
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646485"
---
# <a name="how-to-write-a-cmdlet"></a><span data-ttu-id="d6dbc-103">Como escrever um cmdlet</span><span class="sxs-lookup"><span data-stu-id="d6dbc-103">How to write a cmdlet</span></span>

<span data-ttu-id="d6dbc-104">Este artigo mostra como escrever um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-104">This article shows how to write a cmdlet.</span></span> <span data-ttu-id="d6dbc-105">O `Send-Greeting` cmdlet usa um único nome de usuário como entrada e, em seguida, grava uma saudação para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-105">The `Send-Greeting` cmdlet takes a single user name as input and then writes a greeting to that user.</span></span> <span data-ttu-id="d6dbc-106">Embora o cmdlet não faça muito trabalho, este exemplo demonstra as principais seções de um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-106">Although the cmdlet does not do much work, this example demonstrates the major sections of a cmdlet.</span></span>

## <a name="steps-to-write-a-cmdlet"></a><span data-ttu-id="d6dbc-107">Etapas para gravar um cmdlet</span><span class="sxs-lookup"><span data-stu-id="d6dbc-107">Steps to write a cmdlet</span></span>

1. <span data-ttu-id="d6dbc-108">Para declarar a classe como um cmdlet, use o atributo **cmdlet** .</span><span class="sxs-lookup"><span data-stu-id="d6dbc-108">To declare the class as a cmdlet, use the **Cmdlet** attribute.</span></span> <span data-ttu-id="d6dbc-109">O atributo **cmdlet** especifica o verbo e o substantivo para o nome do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-109">The **Cmdlet** attribute specifies the verb and the noun for the cmdlet name.</span></span>

   <span data-ttu-id="d6dbc-110">Para obter mais informações sobre o atributo de **cmdlet** , consulte [declaração de CmdletAttribute](cmdlet-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="d6dbc-110">For more information about the **Cmdlet** attribute, see [CmdletAttribute Declaration](cmdlet-attribute-declaration.md).</span></span>

2. <span data-ttu-id="d6dbc-111">Especifique o nome da classe.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-111">Specify the name of the class.</span></span>

3. <span data-ttu-id="d6dbc-112">Especifique que o cmdlet deriva de qualquer uma das seguintes classes:</span><span class="sxs-lookup"><span data-stu-id="d6dbc-112">Specify that the cmdlet derives from either of the following classes:</span></span>

   * [<span data-ttu-id="d6dbc-113">System. Management. Automation. cmdlet</span><span class="sxs-lookup"><span data-stu-id="d6dbc-113">System.Management.Automation.Cmdlet</span></span>](/dotnet/api/System.Management.Automation.Cmdlet)
   * [<span data-ttu-id="d6dbc-114">System. Management. Automation. PSCmdlet</span><span class="sxs-lookup"><span data-stu-id="d6dbc-114">System.Management.Automation.PSCmdlet</span></span>](/dotnet/api/System.Management.Automation.PSCmdlet)

4. <span data-ttu-id="d6dbc-115">Para definir os parâmetros para o cmdlet, use o atributo **Parameter** .</span><span class="sxs-lookup"><span data-stu-id="d6dbc-115">To define the parameters for the cmdlet, use the **Parameter** attribute.</span></span> <span data-ttu-id="d6dbc-116">Nesse caso, apenas um parâmetro obrigatório é especificado.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-116">In this case, only one required parameter is specified.</span></span>

   <span data-ttu-id="d6dbc-117">Para obter mais informações sobre o atributo **Parameter** , consulte a [declaração ParameterAttribute](parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="d6dbc-117">For more information about the **Parameter** attribute, see [ParameterAttribute Declaration](parameter-attribute-declaration.md).</span></span>

5. <span data-ttu-id="d6dbc-118">Substitua o método de processamento de entrada que processa a entrada.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-118">Override the input processing method that processes the input.</span></span> <span data-ttu-id="d6dbc-119">Nesse caso, o método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) é substituído.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-119">In this case, the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method is overridden.</span></span>

6. <span data-ttu-id="d6dbc-120">Para gravar a saudação, use o método [System. Management. Automation. cmdlet. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject).</span><span class="sxs-lookup"><span data-stu-id="d6dbc-120">To write the greeting, use the method [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject).</span></span>
   <span data-ttu-id="d6dbc-121">A saudação é exibida no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="d6dbc-121">The greeting is displayed in the following format:</span></span>

   ```Output
   Hello <UserName>!
   ```

## <a name="example"></a><span data-ttu-id="d6dbc-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d6dbc-122">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="d6dbc-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="d6dbc-123">See also</span></span>

[<span data-ttu-id="d6dbc-124">System. Management. Automation. cmdlet</span><span class="sxs-lookup"><span data-stu-id="d6dbc-124">System.Management.Automation.Cmdlet</span></span>](/dotnet/api/System.Management.Automation.Cmdlet)

[<span data-ttu-id="d6dbc-125">System. Management. Automation. PSCmdlet</span><span class="sxs-lookup"><span data-stu-id="d6dbc-125">System.Management.Automation.PSCmdlet</span></span>](/dotnet/api/System.Management.Automation.PSCmdlet)

[<span data-ttu-id="d6dbc-126">System. Management. Automation. cmdlet. ProcessRecord</span><span class="sxs-lookup"><span data-stu-id="d6dbc-126">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="d6dbc-127">System. Management. Automation. cmdlet. WriteObject</span><span class="sxs-lookup"><span data-stu-id="d6dbc-127">System.Management.Automation.Cmdlet.WriteObject</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)

[<span data-ttu-id="d6dbc-128">Declaração de CmdletAttribute</span><span class="sxs-lookup"><span data-stu-id="d6dbc-128">CmdletAttribute Declaration</span></span>](cmdlet-attribute-declaration.md)

[<span data-ttu-id="d6dbc-129">Declaração de ParameterAttribute</span><span class="sxs-lookup"><span data-stu-id="d6dbc-129">ParameterAttribute Declaration</span></span>](parameter-attribute-declaration.md)

<span data-ttu-id="d6dbc-130">[Writing a Windows PowerShell Cmdlet](writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="d6dbc-130">[Writing a Windows PowerShell Cmdlet](writing-a-windows-powershell-cmdlet.md)</span></span>
