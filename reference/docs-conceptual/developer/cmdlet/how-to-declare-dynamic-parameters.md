---
title: Como declarar parâmetros dinâmicos | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db04f1df-def5-4456-8869-336024cda723
caps.latest.revision: 8
ms.openlocfilehash: a9c530cdc66302eb6b3d9d2b284eeb486c3b2ba9
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364415"
---
# <a name="how-to-declare-dynamic-parameters"></a><span data-ttu-id="f0b36-102">Como declarar parâmetros dinâmicos</span><span class="sxs-lookup"><span data-stu-id="f0b36-102">How to Declare Dynamic Parameters</span></span>

<span data-ttu-id="f0b36-103">Este exemplo mostra como definir parâmetros dinâmicos que são adicionados ao cmdlet em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="f0b36-103">This example shows how to define dynamic parameters that are added to the cmdlet at runtime.</span></span> <span data-ttu-id="f0b36-104">Neste exemplo, o parâmetro `Department` é adicionado ao cmdlet sempre que o usuário especifica o parâmetro de opção `Employee`.</span><span class="sxs-lookup"><span data-stu-id="f0b36-104">In this example, the `Department` parameter is added to the cmdlet whenever the user specifies the `Employee` switch parameter.</span></span> <span data-ttu-id="f0b36-105">Para obter mais informações sobre parâmetros dinâmicos, consulte [parâmetros dinâmicos de cmdlet](./cmdlet-dynamic-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="f0b36-105">For more information about dynamic parameters, see [Cmdlet Dynamic Parameters](./cmdlet-dynamic-parameters.md).</span></span>

## <a name="to-define-dynamic-parameters"></a><span data-ttu-id="f0b36-106">Para definir parâmetros dinâmicos</span><span class="sxs-lookup"><span data-stu-id="f0b36-106">To define dynamic parameters</span></span>

1. <span data-ttu-id="f0b36-107">Na declaração de classe de cmdlet, adicione a interface [System. Management. Automation. Idynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters) , conforme mostrado.</span><span class="sxs-lookup"><span data-stu-id="f0b36-107">In the cmdlet class declaration, add the [System.Management.Automation.Idynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters) interface as shown.</span></span>

   ```csharp
   public class SendGreetingCommand : Cmdlet, IDynamicParameters
   ```

2. <span data-ttu-id="f0b36-108">Chame o método [System. Management. Automation. Idynamicparameters. getdynamicparameters \*](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters) , que retorna o objeto no qual os parâmetros dinâmicos são definidos.</span><span class="sxs-lookup"><span data-stu-id="f0b36-108">Call the [System.Management.Automation.Idynamicparameters.Getdynamicparameters\*](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters) method, which returns the object in which the dynamic parameters are defined.</span></span> <span data-ttu-id="f0b36-109">Neste exemplo, o método é chamado quando o parâmetro `Employee` é especificado.</span><span class="sxs-lookup"><span data-stu-id="f0b36-109">In this example, the method is called when the `Employee` parameter is specified.</span></span>

   ```csharp
   public object GetDynamicParameters()
   {
       if (employee)
       {
         context= new SendGreetingCommandDynamicParameters();
         return context;
       }
       return null;
   }
   private SendGreetingCommandDynamicParameters context;
   ```

3. <span data-ttu-id="f0b36-110">Declare uma classe que define os parâmetros dinâmicos a serem adicionados.</span><span class="sxs-lookup"><span data-stu-id="f0b36-110">Declare a class that defines the dynamic parameters to be added.</span></span> <span data-ttu-id="f0b36-111">Você pode usar os atributos que usou para declarar os parâmetros de cmdlet estáticos para declarar os parâmetros dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="f0b36-111">You can use the attributes that you used to declare the static cmdlet parameters to declare the dynamic parameters.</span></span>

   ```csharp
   public class SendGreetingCommandDynamicParameters
   {
     [Parameter]
     [ValidateSet ("Marketing", "Sales", "Development")]
     public string Department
     {
       get { return department; }
       set { department = value; }
     }
     private string department;
   }
   ```

## <a name="example"></a><span data-ttu-id="f0b36-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f0b36-112">Example</span></span>

<span data-ttu-id="f0b36-113">Neste exemplo, o parâmetro `Department` é adicionado sempre que o usuário especifica o parâmetro `Employee`.</span><span class="sxs-lookup"><span data-stu-id="f0b36-113">In this example, the `Department` parameter is added whenever the user specifies the `Employee` parameter.</span></span> <span data-ttu-id="f0b36-114">O parâmetro `Department` é um parâmetro opcional, e o atributo ValidateSet é usado para especificar os argumentos permitidos.</span><span class="sxs-lookup"><span data-stu-id="f0b36-114">The `Department` parameter is an optional parameter, and the ValidateSet attribute is used to specify the allowed arguments.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Management.Automation;     // PowerShell assembly.

namespace SendGreeting
{
  // Declare the cmdlet class that supports the
  // IDynamicParameters interface.
  [Cmdlet(VerbsCommunications.Send, "Greeting")]
  public class SendGreetingCommand : Cmdlet, IDynamicParameters
  {
    // Declare the parameters for the cmdlet.
    [Parameter(Mandatory = true)]
    public string Name
    {
      get { return name; }
      set { name = value; }
    }
    private string name;

    [Parameter]
    [Alias ("FTE")]
    public SwitchParameter Employee
    {
      get { return employee; }
      set { employee = value; }
    }
    private Boolean employee;

    // Implement GetDynamicParameters to
    // retrieve the dynamic parameter.
    public object GetDynamicParameters()
    {
      if (employee)
      {
        context= new SendGreetingCommandDynamicParameters();
        return context;
      }
      return null;
   }
   private SendGreetingCommandDynamicParameters context;

    // Overide the ProcessRecord method to process the
    // supplied user name and write out a greeting to
    // the user by calling the WriteObject method.
    protected override void ProcessRecord()
    {
      WriteObject("Hello " + name + "! ");
      if (employee)
      {
        WriteObject("Department: " + context.Department);
      }
    }
  }

  // Define the dynamic parameters to be added
  public class SendGreetingCommandDynamicParameters
  {
    [Parameter]
    [ValidateSet ("Marketing", "Sales", "Development")]
    public string Department
    {
      get { return department; }
      set { department = value; }
    }
    private string department;
  }
}
```

## <a name="see-also"></a><span data-ttu-id="f0b36-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f0b36-115">See Also</span></span>

[<span data-ttu-id="f0b36-116">System. Management. Automation. Runtimedefinedparameterdictionary</span><span class="sxs-lookup"><span data-stu-id="f0b36-116">System.Management.Automation.Runtimedefinedparameterdictionary</span></span>](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)

[<span data-ttu-id="f0b36-117">System. Management. Automation. Idynamicparameters. getdynamicparameters \*</span><span class="sxs-lookup"><span data-stu-id="f0b36-117">System.Management.Automation.Idynamicparameters.Getdynamicparameters\*</span></span>](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)

[<span data-ttu-id="f0b36-118">Parâmetros dinâmicos de cmdlet</span><span class="sxs-lookup"><span data-stu-id="f0b36-118">Cmdlet Dynamic Parameters</span></span>](./cmdlet-dynamic-parameters.md)

[<span data-ttu-id="f0b36-119">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0b36-119">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)