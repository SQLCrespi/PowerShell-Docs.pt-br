---
ms.date: 09/13/2016
ms.topic: reference
title: Como invocar um cmdlet de dentro de um cmdlet
description: Como invocar um cmdlet de dentro de um cmdlet
ms.openlocfilehash: d137ac895f66000329de76a2c16a74b02c0e82ca
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667038"
---
# <a name="how-to-invoke-a-cmdlet-from-within-a-cmdlet"></a><span data-ttu-id="b0bc4-103">Como invocar um cmdlet de dentro de um cmdlet</span><span class="sxs-lookup"><span data-stu-id="b0bc4-103">How to Invoke a Cmdlet from Within a Cmdlet</span></span>

<span data-ttu-id="b0bc4-104">Este exemplo mostra como invocar um cmdlet de dentro de outro cmdlet, que permite adicionar a funcionalidade do cmdlet invocado ao cmdlet que você está desenvolvendo.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-104">This example shows how to invoke a cmdlet from within another cmdlet, which allows you to add the functionality of the invoked cmdlet to the cmdlet you are developing.</span></span> <span data-ttu-id="b0bc4-105">Neste exemplo, o `Get-Process` cmdlet é invocado para obter os processos em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-105">In this example, the `Get-Process` cmdlet is invoked to get the processes that are running on the local computer.</span></span> <span data-ttu-id="b0bc4-106">A chamada para o `Get-Process` cmdlet é equivalente ao comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-106">The call to the `Get-Process` cmdlet is equivalent to the following command.</span></span> <span data-ttu-id="b0bc4-107">Esse comando recupera todos os processos cujos nomes começam com os caracteres "a" por meio de "t".</span><span class="sxs-lookup"><span data-stu-id="b0bc4-107">This command retrieves all the processes whose names start with the characters "a" through "t".</span></span>

```powershell
Get-Process -name [a-t]
```

> [!IMPORTANT]
> <span data-ttu-id="b0bc4-108">Você pode invocar somente os cmdlets que derivam diretamente da classe [System. Management. Automation. cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) .</span><span class="sxs-lookup"><span data-stu-id="b0bc4-108">You can invoke only those cmdlets that derive directly from the [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) class.</span></span> <span data-ttu-id="b0bc4-109">Não é possível invocar um cmdlet derivado da classe [System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) .</span><span class="sxs-lookup"><span data-stu-id="b0bc4-109">You cannot invoke a cmdlet that derives from the [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) class.</span></span>

## <a name="to-invoke-a-cmdlet-from-within-a-cmdlet"></a><span data-ttu-id="b0bc4-110">Para invocar um cmdlet de dentro de um cmdlet</span><span class="sxs-lookup"><span data-stu-id="b0bc4-110">To invoke a cmdlet from within a cmdlet</span></span>

1. <span data-ttu-id="b0bc4-111">Verifique se o assembly que define o cmdlet a ser invocado é referenciado e se a `using` instrução apropriada foi adicionada.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-111">Ensure that the assembly that defines the cmdlet to be invoked is referenced and that the appropriate `using` statement is added.</span></span> <span data-ttu-id="b0bc4-112">Neste exemplo, os namespaces a seguir são adicionados.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-112">In this example, the following namespaces are added.</span></span>

    ```csharp
    using System.Diagnostics;
    using System.Management.Automation;   // Windows PowerShell assembly.
    using Microsoft.PowerShell.Commands;  // Windows PowerShell assembly.
    ```

2. <span data-ttu-id="b0bc4-113">No método de processamento de entrada do cmdlet, crie uma nova instância do cmdlet a ser invocada.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-113">In the input processing method of the cmdlet, create a new instance of the cmdlet to be invoked.</span></span> <span data-ttu-id="b0bc4-114">Neste exemplo, um objeto do tipo [Microsoft. PowerShell. Commands. Getprocesscommand](/dotnet/api/Microsoft.PowerShell.Commands.GetProcessCommand) é criado junto com a cadeia de caracteres que contém os argumentos que são usados quando o cmdlet é invocado.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-114">In this example, an object of type [Microsoft.PowerShell.Commands.Getprocesscommand](/dotnet/api/Microsoft.PowerShell.Commands.GetProcessCommand) is created along with the string that contains the arguments that are used when the cmdlet is invoked.</span></span>

    ```csharp
    GetProcessCommand gp = new GetProcessCommand();
    gp.Name = new string[] { "[a-t]*" };
    ```

3. <span data-ttu-id="b0bc4-115">Chame o método [System. Management. Automation. cmdlet. Invoke \*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) para invocar o `Get-Process` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-115">Call the [System.Management.Automation.Cmdlet.Invoke\*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) method to invoke the `Get-Process` cmdlet.</span></span>

    ```csharp
      foreach (Process p in gp.Invoke<Process>())
      {
        Console.WriteLine(p.ToString());
      }
    }
    ```

## <a name="example"></a><span data-ttu-id="b0bc4-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b0bc4-116">Example</span></span>

<span data-ttu-id="b0bc4-117">Neste exemplo, o `Get-Process` cmdlet é invocado de dentro do método [System. Management. Automation. cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) de um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b0bc4-117">In this example, the `Get-Process` cmdlet is invoked from within the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method of a cmdlet.</span></span>

```csharp
using System;
using System.Diagnostics;
using System.Management.Automation;   // Windows PowerShell assembly.
using Microsoft.PowerShell.Commands;  // Windows PowerShell assembly.

namespace SendGreeting
{
  // Declare the class as a cmdlet and specify an
  // appropriate verb and noun for the cmdlet name.
  [Cmdlet(VerbsCommunications.Send, "GreetingInvoke")]
  public class SendGreetingInvokeCommand : Cmdlet
  {
    // Declare the parameters for the cmdlet.
    [Parameter(Mandatory = true)]
    public string Name
    {
      get { return name; }
      set { name = value; }
    }
    private string name;

    // Override the BeginProcessing method to invoke
    // the Get-Process cmdlet.
    protected override void BeginProcessing()
    {
      GetProcessCommand gp = new GetProcessCommand();
      gp.Name = new string[] { "[a-t]*" };
      foreach (Process p in gp.Invoke<Process>())
      {
        Console.WriteLine(p.ToString());
      }
    }

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

## <a name="see-also"></a><span data-ttu-id="b0bc4-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b0bc4-118">See Also</span></span>

[<span data-ttu-id="b0bc4-119">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0bc4-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
