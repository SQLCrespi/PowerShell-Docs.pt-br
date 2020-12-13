---
ms.date: 09/13/2016
ms.topic: reference
title: Como declarar parâmetros dinâmicos
description: Como declarar parâmetros dinâmicos
ms.openlocfilehash: 0f5a8f249b414663aa9702a908ea5c8ca24755ff
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667072"
---
# <a name="how-to-declare-dynamic-parameters"></a><span data-ttu-id="073bd-103">Como declarar parâmetros dinâmicos</span><span class="sxs-lookup"><span data-stu-id="073bd-103">How to Declare Dynamic Parameters</span></span>

<span data-ttu-id="073bd-104">Este exemplo mostra como definir parâmetros dinâmicos que são adicionados ao cmdlet em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="073bd-104">This example shows how to define dynamic parameters that are added to the cmdlet at runtime.</span></span> <span data-ttu-id="073bd-105">Neste exemplo, o `Department` parâmetro é adicionado ao cmdlet sempre que o usuário especifica o `Employee` parâmetro de opção.</span><span class="sxs-lookup"><span data-stu-id="073bd-105">In this example, the `Department` parameter is added to the cmdlet whenever the user specifies the `Employee` switch parameter.</span></span> <span data-ttu-id="073bd-106">Para obter mais informações sobre parâmetros dinâmicos, consulte [parâmetros dinâmicos de cmdlet](./cmdlet-dynamic-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="073bd-106">For more information about dynamic parameters, see [Cmdlet Dynamic Parameters](./cmdlet-dynamic-parameters.md).</span></span>

## <a name="to-define-dynamic-parameters"></a><span data-ttu-id="073bd-107">Para definir parâmetros dinâmicos</span><span class="sxs-lookup"><span data-stu-id="073bd-107">To define dynamic parameters</span></span>

1. <span data-ttu-id="073bd-108">Na declaração de classe de cmdlet, adicione a interface [System. Management. Automation. Idynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters) , conforme mostrado.</span><span class="sxs-lookup"><span data-stu-id="073bd-108">In the cmdlet class declaration, add the [System.Management.Automation.Idynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters) interface as shown.</span></span>

   ```csharp
   public class SendGreetingCommand : Cmdlet, IDynamicParameters
   ```

2. <span data-ttu-id="073bd-109">Chame o método [System. Management. Automation. Idynamicparameters. getdynamicparameters \*](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters) , que retorna o objeto no qual os parâmetros dinâmicos são definidos.</span><span class="sxs-lookup"><span data-stu-id="073bd-109">Call the [System.Management.Automation.Idynamicparameters.Getdynamicparameters\*](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters) method, which returns the object in which the dynamic parameters are defined.</span></span> <span data-ttu-id="073bd-110">Neste exemplo, o método é chamado quando o `Employee` parâmetro é especificado.</span><span class="sxs-lookup"><span data-stu-id="073bd-110">In this example, the method is called when the `Employee` parameter is specified.</span></span>

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

3. <span data-ttu-id="073bd-111">Declare uma classe que define os parâmetros dinâmicos a serem adicionados.</span><span class="sxs-lookup"><span data-stu-id="073bd-111">Declare a class that defines the dynamic parameters to be added.</span></span> <span data-ttu-id="073bd-112">Você pode usar os atributos que usou para declarar os parâmetros de cmdlet estáticos para declarar os parâmetros dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="073bd-112">You can use the attributes that you used to declare the static cmdlet parameters to declare the dynamic parameters.</span></span>

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

## <a name="example"></a><span data-ttu-id="073bd-113">Exemplo</span><span class="sxs-lookup"><span data-stu-id="073bd-113">Example</span></span>

<span data-ttu-id="073bd-114">Neste exemplo, o `Department` parâmetro é adicionado sempre que o usuário especifica o `Employee` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="073bd-114">In this example, the `Department` parameter is added whenever the user specifies the `Employee` parameter.</span></span> <span data-ttu-id="073bd-115">O `Department` parâmetro é um parâmetro opcional, e o atributo ValidateSet é usado para especificar os argumentos permitidos.</span><span class="sxs-lookup"><span data-stu-id="073bd-115">The `Department` parameter is an optional parameter, and the ValidateSet attribute is used to specify the allowed arguments.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="073bd-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="073bd-116">See Also</span></span>

[<span data-ttu-id="073bd-117">System. Management. Automation. Runtimedefinedparameterdictionary</span><span class="sxs-lookup"><span data-stu-id="073bd-117">System.Management.Automation.Runtimedefinedparameterdictionary</span></span>](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)

[<span data-ttu-id="073bd-118">System. Management. Automation. Idynamicparameters. getdynamicparameters \*</span><span class="sxs-lookup"><span data-stu-id="073bd-118">System.Management.Automation.Idynamicparameters.Getdynamicparameters\*</span></span>](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)

[<span data-ttu-id="073bd-119">Parâmetros dinâmicos de cmdlet</span><span class="sxs-lookup"><span data-stu-id="073bd-119">Cmdlet Dynamic Parameters</span></span>](./cmdlet-dynamic-parameters.md)

[<span data-ttu-id="073bd-120">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="073bd-120">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
