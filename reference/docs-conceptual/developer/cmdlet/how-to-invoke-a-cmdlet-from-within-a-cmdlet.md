---
title: Como invocar um cmdlet de dentro de um cmdlet | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: efa4dc9c-ddee-46a3-978a-9dbb61e9bb6f
caps.latest.revision: 12
ms.openlocfilehash: 57543a88d04eb66c9d109249a99ddd272b02ef9d
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365545"
---
# <a name="how-to-invoke-a-cmdlet-from-within-a-cmdlet"></a><span data-ttu-id="c3b70-102">Como invocar um cmdlet de dentro de um cmdlet</span><span class="sxs-lookup"><span data-stu-id="c3b70-102">How to Invoke a Cmdlet from Within a Cmdlet</span></span>

<span data-ttu-id="c3b70-103">Este exemplo mostra como invocar um cmdlet de dentro de outro cmdlet, que permite adicionar a funcionalidade do cmdlet invocado ao cmdlet que você está desenvolvendo.</span><span class="sxs-lookup"><span data-stu-id="c3b70-103">This example shows how to invoke a cmdlet from within another cmdlet, which allows you to add the functionality of the invoked cmdlet to the cmdlet you are developing.</span></span> <span data-ttu-id="c3b70-104">Neste exemplo, o cmdlet `Get-Process` é invocado para obter os processos em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="c3b70-104">In this example, the `Get-Process` cmdlet is invoked to get the processes that are running on the local computer.</span></span> <span data-ttu-id="c3b70-105">A chamada para o cmdlet `Get-Process` é equivalente ao comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="c3b70-105">The call to the `Get-Process` cmdlet is equivalent to the following command.</span></span> <span data-ttu-id="c3b70-106">Esse comando recupera todos os processos cujos nomes começam com os caracteres "a" por meio de "t".</span><span class="sxs-lookup"><span data-stu-id="c3b70-106">This command retrieves all the processes whose names start with the characters "a" through "t".</span></span>

```powershell
Get-Process -name [a-t]
```

> [!IMPORTANT]
> <span data-ttu-id="c3b70-107">Você pode invocar somente os cmdlets que derivam diretamente da classe [System. Management. Automation. cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) .</span><span class="sxs-lookup"><span data-stu-id="c3b70-107">You can invoke only those cmdlets that derive directly from the [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) class.</span></span> <span data-ttu-id="c3b70-108">Não é possível invocar um cmdlet derivado da classe [System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) .</span><span class="sxs-lookup"><span data-stu-id="c3b70-108">You cannot invoke a cmdlet that derives from the [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) class.</span></span>

## <a name="to-invoke-a-cmdlet-from-within-a-cmdlet"></a><span data-ttu-id="c3b70-109">Para invocar um cmdlet de dentro de um cmdlet</span><span class="sxs-lookup"><span data-stu-id="c3b70-109">To invoke a cmdlet from within a cmdlet</span></span>

1. <span data-ttu-id="c3b70-110">Verifique se o assembly que define o cmdlet a ser invocado é referenciado e se a instrução de `using` apropriada foi adicionada.</span><span class="sxs-lookup"><span data-stu-id="c3b70-110">Ensure that the assembly that defines the cmdlet to be invoked is referenced and that the appropriate `using` statement is added.</span></span> <span data-ttu-id="c3b70-111">Neste exemplo, os namespaces a seguir são adicionados.</span><span class="sxs-lookup"><span data-stu-id="c3b70-111">In this example, the following namespaces are added.</span></span>

    ```csharp
    using System.Diagnostics;
    using System.Management.Automation;   // Windows PowerShell assembly.
    using Microsoft.PowerShell.Commands;  // Windows PowerShell assembly.
    ```

2. <span data-ttu-id="c3b70-112">No método de processamento de entrada do cmdlet, crie uma nova instância do cmdlet a ser invocada.</span><span class="sxs-lookup"><span data-stu-id="c3b70-112">In the input processing method of the cmdlet, create a new instance of the cmdlet to be invoked.</span></span> <span data-ttu-id="c3b70-113">Neste exemplo, um objeto do tipo [Microsoft. PowerShell. Commands. Getprocesscommand](/dotnet/api/Microsoft.PowerShell.Commands.GetProcessCommand) é criado junto com a cadeia de caracteres que contém os argumentos que são usados quando o cmdlet é invocado.</span><span class="sxs-lookup"><span data-stu-id="c3b70-113">In this example, an object of type [Microsoft.PowerShell.Commands.Getprocesscommand](/dotnet/api/Microsoft.PowerShell.Commands.GetProcessCommand) is created along with the string that contains the arguments that are used when the cmdlet is invoked.</span></span>

    ```csharp
    GetProcessCommand gp = new GetProcessCommand();
    gp.Name = new string[] { "[a-t]*" };
    ```

3. <span data-ttu-id="c3b70-114">Chame o método [System. Management. Automation. cmdlet. Invoke \*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) para invocar o cmdlet `Get-Process`.</span><span class="sxs-lookup"><span data-stu-id="c3b70-114">Call the [System.Management.Automation.Cmdlet.Invoke\*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) method to invoke the `Get-Process` cmdlet.</span></span>

    ```csharp
      foreach (Process p in gp.Invoke<Process>())
      {
        Console.WriteLine(p.ToString());
      }
    }
    ```

## <a name="example"></a><span data-ttu-id="c3b70-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c3b70-115">Example</span></span>

<span data-ttu-id="c3b70-116">Neste exemplo, o cmdlet `Get-Process` é invocado de dentro do método [System. Management. Automation. cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) de um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c3b70-116">In this example, the `Get-Process` cmdlet is invoked from within the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method of a cmdlet.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="c3b70-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c3b70-117">See Also</span></span>

<span data-ttu-id="c3b70-118">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="c3b70-118">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
