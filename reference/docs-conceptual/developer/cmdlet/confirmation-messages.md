---
ms.date: 09/13/2016
ms.topic: reference
title: Mensagens de confirmação
description: Mensagens de confirmação
ms.openlocfilehash: 76302b2f8d8ca6dcdfe1b3c36f71aad23a53f7cf
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355180"
---
# <a name="confirmation-messages"></a><span data-ttu-id="44893-103">Mensagens de confirmação</span><span class="sxs-lookup"><span data-stu-id="44893-103">Confirmation Messages</span></span>

<span data-ttu-id="44893-104">Aqui estão as diferentes mensagens de confirmação que podem ser exibidas dependendo das variantes dos métodos [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) e [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) que são chamados.</span><span class="sxs-lookup"><span data-stu-id="44893-104">Here are different confirmation messages that can be displayed depending on the variants of the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods that are called.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="44893-105">Para obter um exemplo de código que mostra como solicitar confirmações, consulte [como solicitar confirmações](./how-to-request-confirmations.md).</span><span class="sxs-lookup"><span data-stu-id="44893-105">For sample code that shows how to request confirmations, see [How to Request Confirmations](./how-to-request-confirmations.md).</span></span>

## <a name="specifying-the-resource"></a><span data-ttu-id="44893-106">Especificando o recurso</span><span class="sxs-lookup"><span data-stu-id="44893-106">Specifying the Resource</span></span>

<span data-ttu-id="44893-107">Você pode especificar o recurso que está prestes a ser alterado chamando o [System. Management. Automation. cmdlet. ShouldProcess% 2a? Método displayproperty = FullName](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) .</span><span class="sxs-lookup"><span data-stu-id="44893-107">You can specify the resource that is about to be changed by calling the [System.Management.Automation.Cmdlet.Shouldprocess%2A?Displayproperty=Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method.</span></span> <span data-ttu-id="44893-108">Nesse caso, você fornece o recurso usando o `target` parâmetro do método e a operação é adicionada pelo Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44893-108">In this case, you supply the resource by using the `target` parameter of the method, and the operation is added by Windows PowerShell.</span></span> <span data-ttu-id="44893-109">Na mensagem a seguir, o texto "MyResource" é o recurso acionado e a operação é o nome do comando que faz a chamada.</span><span class="sxs-lookup"><span data-stu-id="44893-109">In the following message, the text "MyResource" is the resource acted on and the operation is the name of the command that makes the call.</span></span>

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="44893-110">Se o usuário selecionar **Sim** ou **Sim para todos** na solicitação de confirmação (como mostrado no exemplo a seguir), será feita uma chamada para o método [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) , que faz com que uma segunda mensagem de confirmação seja exibida.</span><span class="sxs-lookup"><span data-stu-id="44893-110">If the user selects **Yes** or **Yes to All** to the confirmation request (as shown in the following example), a call to the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method is made, which causes a second confirmation message to be displayed.</span></span>

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y

Confirm
Continue with this operation?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

## <a name="specifying-the-operation-and-resource"></a><span data-ttu-id="44893-111">Especificando a operação e o recurso</span><span class="sxs-lookup"><span data-stu-id="44893-111">Specifying the Operation and Resource</span></span>

<span data-ttu-id="44893-112">Você pode especificar o recurso que está prestes a ser alterado e a operação que o comando está prestes a executar chamando o [System. Management. Automation. cmdlet. ShouldProcess% 2a? Método displayproperty = FullName](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) .</span><span class="sxs-lookup"><span data-stu-id="44893-112">You can specify the resource that is about to be changed and the operation that the command is about to perform by calling the [System.Management.Automation.Cmdlet.Shouldprocess%2A?Displayproperty=Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method.</span></span> <span data-ttu-id="44893-113">Nesse caso, você fornece o recurso usando o `target` parâmetro e a operação usando o `target` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="44893-113">In this case, you supply the resource by using the `target` parameter and the operation by using the `target` parameter.</span></span> <span data-ttu-id="44893-114">Na mensagem a seguir, o texto "MyResource" é o recurso acionado e "myaction" é a operação a ser executada.</span><span class="sxs-lookup"><span data-stu-id="44893-114">In the following message, the text "MyResource" is the resource acted on and "MyAction" is the operation to be performed.</span></span>

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "MyAction" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="44893-115">Se o usuário selecionar **Sim** ou **Sim para todos** na mensagem anterior, será feita uma chamada para o método [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) , que faz com que uma segunda mensagem de confirmação seja exibida.</span><span class="sxs-lookup"><span data-stu-id="44893-115">If the user selects **Yes** or **Yes to All** to the previous message, a call to the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method is made, which causes a second confirmation message to be displayed.</span></span>

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "MyAction" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y

Confirm
Continue with this operation?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

## <a name="see-also"></a><span data-ttu-id="44893-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="44893-116">See Also</span></span>

[<span data-ttu-id="44893-117">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="44893-117">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
