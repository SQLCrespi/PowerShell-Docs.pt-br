---
ms.date: 09/13/2016
ms.topic: reference
title: Usuários que solicitam confirmação
description: Usuários que solicitam confirmação
ms.openlocfilehash: 58dbe27635ca38886b728f585fec063645b3597e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646309"
---
# <a name="users-requesting-confirmation"></a><span data-ttu-id="7e001-103">Usuários que solicitam confirmação</span><span class="sxs-lookup"><span data-stu-id="7e001-103">Users Requesting Confirmation</span></span>

<span data-ttu-id="7e001-104">Quando você especifica um valor de `true` para o `SupportsShouldProcess` parâmetro da declaração de atributo do cmdlet, os usuários podem especificar o `Confirm` parâmetro no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="7e001-104">When you specify a value of `true` for the `SupportsShouldProcess` parameter of the Cmdlet attribute declaration, users can specify the `Confirm` parameter at the command prompt.</span></span>

<span data-ttu-id="7e001-105">No ambiente padrão, os usuários podem especificar o `Confirm` parâmetro ou `"-Confirm:$true` , portanto, a confirmação é solicitada quando o método [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) é chamado.</span><span class="sxs-lookup"><span data-stu-id="7e001-105">In the default environment, users can specify the `Confirm` parameter or `"-Confirm:$true` so that confirmation is requested when the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method is called.</span></span> <span data-ttu-id="7e001-106">Isso ignora as solicitações de confirmação de [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , mesmo para operações de alto impacto.</span><span class="sxs-lookup"><span data-stu-id="7e001-106">This bypasses [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) confirmation requests, even for high-impact operations.</span></span>

<span data-ttu-id="7e001-107">Se `Confirm` não for especificado, a chamada [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) solicitará a confirmação se a `$ConfirmPreference` variável de preferência for igual ou maior que a `ConfirmImpact` configuração do cmdlet ou do provedor.</span><span class="sxs-lookup"><span data-stu-id="7e001-107">If `Confirm` is not specified, the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call requests confirmation if the `$ConfirmPreference` preference variable is equal to or greater than the `ConfirmImpact` setting of the cmdlet or provider.</span></span> <span data-ttu-id="7e001-108">A configuração padrão de `$ConfirmPreference` é alta.</span><span class="sxs-lookup"><span data-stu-id="7e001-108">The default setting of `$ConfirmPreference` is High.</span></span> <span data-ttu-id="7e001-109">Portanto, no ambiente padrão, somente os cmdlets e provedores que especificam uma confirmação de solicitação de ação de alto impacto.</span><span class="sxs-lookup"><span data-stu-id="7e001-109">Therefore, in the default environment, only cmdlets and providers that specify a high-impact action request confirmation.</span></span>

<span data-ttu-id="7e001-110">Se `Confirm` for false ou se `"-Confirm:$false` for especificado, a chamada [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) solicitará a confirmação do usuário e a `$ConfirmPreference` variável de shell será ignorada.</span><span class="sxs-lookup"><span data-stu-id="7e001-110">If `Confirm` is false or if `"-Confirm:$false` is specified, the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call requests confirmation from the user, and the `$ConfirmPreference` shell variable is ignored.</span></span>

## <a name="remarks"></a><span data-ttu-id="7e001-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="7e001-111">Remarks</span></span>

- <span data-ttu-id="7e001-112">Para cmdlets e provedores que especificam `SupportsShouldProcess` , mas não `ConfirmImpact` , essas ações são manipuladas como ações de "impacto médio" e não serão solicitadas por padrão.</span><span class="sxs-lookup"><span data-stu-id="7e001-112">For cmdlets and providers that specify `SupportsShouldProcess`, but not `ConfirmImpact`, those actions are handled as "medium impact" actions, and they will not prompt by default.</span></span> <span data-ttu-id="7e001-113">Seu nível de impacto é menor que a configuração padrão da `$ConfirmPreference` variável de preferência.</span><span class="sxs-lookup"><span data-stu-id="7e001-113">Their impact level is less than the default setting of the `$ConfirmPreference` preference variable.</span></span>

- <span data-ttu-id="7e001-114">Se o usuário especificar o `Verbose` parâmetro, ele será notificado sobre a operação mesmo que não seja solicitada a confirmação.</span><span class="sxs-lookup"><span data-stu-id="7e001-114">If the user specifies the `Verbose` parameter, they will be notified of the operation even if they are not prompted for confirmation.</span></span>

## <a name="see-also"></a><span data-ttu-id="7e001-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7e001-115">See Also</span></span>

[<span data-ttu-id="7e001-116">Escrevendo um Cmdlet do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7e001-116">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
