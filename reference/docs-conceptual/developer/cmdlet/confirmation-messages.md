---
title: Mensagens de confirmação | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 8f8192f6ed96b1eeb22e3b28ce1366eee8e7c16a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782184"
---
# <a name="confirmation-messages"></a><span data-ttu-id="c576c-102">Mensagens de confirmação</span><span class="sxs-lookup"><span data-stu-id="c576c-102">Confirmation Messages</span></span>

<span data-ttu-id="c576c-103">Aqui estão as diferentes mensagens de confirmação que podem ser exibidas dependendo das variantes dos métodos [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) e [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) que são chamados.</span><span class="sxs-lookup"><span data-stu-id="c576c-103">Here are different confirmation messages that can be displayed depending on the variants of the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods that are called.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c576c-104">Para obter um exemplo de código que mostra como solicitar confirmações, consulte [como solicitar confirmações](./how-to-request-confirmations.md).</span><span class="sxs-lookup"><span data-stu-id="c576c-104">For sample code that shows how to request confirmations, see [How to Request Confirmations](./how-to-request-confirmations.md).</span></span>

## <a name="specifying-the-resource"></a><span data-ttu-id="c576c-105">Especificando o recurso</span><span class="sxs-lookup"><span data-stu-id="c576c-105">Specifying the Resource</span></span>

<span data-ttu-id="c576c-106">Você pode especificar o recurso que está prestes a ser alterado chamando o [System. Management. Automation. cmdlet. ShouldProcess% 2a? Método displayproperty = FullName](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0) .</span><span class="sxs-lookup"><span data-stu-id="c576c-106">You can specify the resource that is about to be changed by calling the [System.Management.Automation.Cmdlet.Shouldprocess%2A?Displayproperty=Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0) method.</span></span> <span data-ttu-id="c576c-107">Nesse caso, você fornece o recurso usando o `target` parâmetro do método e a operação é adicionada pelo Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c576c-107">In this case, you supply the resource by using the `target` parameter of the method, and the operation is added by Windows PowerShell.</span></span> <span data-ttu-id="c576c-108">Na mensagem a seguir, o texto "MyResource" é o recurso acionado e a operação é o nome do comando que faz a chamada.</span><span class="sxs-lookup"><span data-stu-id="c576c-108">In the following message, the text "MyResource" is the resource acted on and the operation is the name of the command that makes the call.</span></span>

```output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="c576c-109">Se o usuário selecionar **Sim** ou **Sim para todos** na solicitação de confirmação (como mostrado no exemplo a seguir), será feita uma chamada para o método [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) , que faz com que uma segunda mensagem de confirmação seja exibida.</span><span class="sxs-lookup"><span data-stu-id="c576c-109">If the user selects **Yes** or **Yes to All** to the confirmation request (as shown in the following example), a call to the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method is made, which causes a second confirmation message to be displayed.</span></span>

```output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y

Confirm
Continue with this operation?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

## <a name="specifying-the-operation-and-resource"></a><span data-ttu-id="c576c-110">Especificando a operação e o recurso</span><span class="sxs-lookup"><span data-stu-id="c576c-110">Specifying the Operation and Resource</span></span>

<span data-ttu-id="c576c-111">Você pode especificar o recurso que está prestes a ser alterado e a operação que o comando está prestes a executar chamando o [System. Management. Automation. cmdlet. ShouldProcess% 2a? Método displayproperty = FullName](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0) .</span><span class="sxs-lookup"><span data-stu-id="c576c-111">You can specify the resource that is about to be changed and the operation that the command is about to perform by calling the [System.Management.Automation.Cmdlet.Shouldprocess%2A?Displayproperty=Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0) method.</span></span> <span data-ttu-id="c576c-112">Nesse caso, você fornece o recurso usando o `target` parâmetro e a operação usando o `target` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="c576c-112">In this case, you supply the resource by using the `target` parameter and the operation by using the `target` parameter.</span></span> <span data-ttu-id="c576c-113">Na mensagem a seguir, o texto "MyResource" é o recurso acionado e "myaction" é a operação a ser executada.</span><span class="sxs-lookup"><span data-stu-id="c576c-113">In the following message, the text "MyResource" is the resource acted on and "MyAction" is the operation to be performed.</span></span>

```output
Confirm
Are you sure you want to perform this action?
Performing operation "MyAction" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="c576c-114">Se o usuário selecionar **Sim** ou **Sim para todos** na mensagem anterior, será feita uma chamada para o método [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) , que faz com que uma segunda mensagem de confirmação seja exibida.</span><span class="sxs-lookup"><span data-stu-id="c576c-114">If the user selects **Yes** or **Yes to All** to the previous message, a call to the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method is made, which causes a second confirmation message to be displayed.</span></span>

```output
Confirm
Are you sure you want to perform this action?
Performing operation "MyAction" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y

Confirm
Continue with this operation?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

## <a name="see-also"></a><span data-ttu-id="c576c-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c576c-115">See Also</span></span>

[<span data-ttu-id="c576c-116">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c576c-116">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
