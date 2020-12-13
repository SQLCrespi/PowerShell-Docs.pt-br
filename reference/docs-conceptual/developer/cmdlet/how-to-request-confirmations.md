---
ms.date: 09/13/2016
ms.topic: reference
title: Como solicitar confirmações
description: Como solicitar confirmações
ms.openlocfilehash: 3e29803407bd9fbf13e6db0d0a02239c34e9c4fa
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666987"
---
# <a name="how-to-request-confirmations"></a><span data-ttu-id="759ce-103">Como solicitar confirmações</span><span class="sxs-lookup"><span data-stu-id="759ce-103">How to Request Confirmations</span></span>

<span data-ttu-id="759ce-104">Este exemplo mostra como chamar os métodos [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) e [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) para solicitar confirmações do usuário antes que uma ação seja executada.</span><span class="sxs-lookup"><span data-stu-id="759ce-104">This example shows how to call the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods to request confirmations from the user before an action is taken.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="759ce-105">Para obter mais informações sobre como o Windows PowerShell lida com essas solicitações, consulte [solicitando confirmação](./requesting-confirmation-from-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="759ce-105">For more information about how Windows PowerShell handles these requests, see [Requesting Confirmation](./requesting-confirmation-from-cmdlets.md).</span></span>

## <a name="to-request-confirmation"></a><span data-ttu-id="759ce-106">Para solicitar confirmação</span><span class="sxs-lookup"><span data-stu-id="759ce-106">To request confirmation</span></span>

1. <span data-ttu-id="759ce-107">Verifique se o `SupportsShouldProcess` parâmetro do atributo cmdlet está definido como `true` .</span><span class="sxs-lookup"><span data-stu-id="759ce-107">Ensure that the `SupportsShouldProcess` parameter of the Cmdlet attribute is set to `true`.</span></span> <span data-ttu-id="759ce-108">(Para funções, esse é um parâmetro do atributo CmdletBinding.)</span><span class="sxs-lookup"><span data-stu-id="759ce-108">(For functions this is a parameter of the CmdletBinding attribute.)</span></span>

    ```csharp
    [Cmdlet(VerbsDiagnostic.Test, "RequestConfirmationTemplate1",
            SupportsShouldProcess = true)]
    ```

2. <span data-ttu-id="759ce-109">Adicione um `Force` parâmetro ao cmdlet para que o usuário possa substituir uma solicitação de confirmação.</span><span class="sxs-lookup"><span data-stu-id="759ce-109">Add a `Force` parameter to your cmdlet so that the user can override a confirmation request.</span></span>

    ```csharp
    [Parameter()]
    public SwitchParameter Force
    {
      get { return force; }
      set { force = value; }
    }
    private bool force;
    ```

3. <span data-ttu-id="759ce-110">Adicione uma `if` instrução que usa o valor de retorno do método [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) para determinar se o método [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) é chamado.</span><span class="sxs-lookup"><span data-stu-id="759ce-110">Add an `if` statement that uses the return value of the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method to determine if the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method is called.</span></span>

4. <span data-ttu-id="759ce-111">Adicione uma segunda `if` instrução que usa o valor de retorno do método [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) e o valor do `Force` parâmetro para determinar se a operação deve ser executada.</span><span class="sxs-lookup"><span data-stu-id="759ce-111">Add a second `if` statement that uses the return value of the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method and the value of the `Force` parameter to determine whether the operation should be performed.</span></span>

## <a name="example"></a><span data-ttu-id="759ce-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="759ce-112">Example</span></span>

<span data-ttu-id="759ce-113">No exemplo de código a seguir, os métodos [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) e [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) são chamados de dentro da substituição do método [System. Management. Automation. cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) .</span><span class="sxs-lookup"><span data-stu-id="759ce-113">In the following code example, the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods are called from within the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span> <span data-ttu-id="759ce-114">No entanto, você também pode chamar esses métodos de outros métodos de processamento de entrada.</span><span class="sxs-lookup"><span data-stu-id="759ce-114">However, you can also call these methods from the other input processing methods.</span></span>

```csharp
protected override void ProcessRecord()
{
  if (ShouldProcess("ShouldProcess target"))
  {
    if (Force || ShouldContinue("", ""))
    {
      // Add code that performs the operation.
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="759ce-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="759ce-115">See Also</span></span>

[<span data-ttu-id="759ce-116">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="759ce-116">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
