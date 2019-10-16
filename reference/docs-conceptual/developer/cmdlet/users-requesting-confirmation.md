---
title: Usuários solicitando confirmação | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f337498-c534-40ed-968a-09d4d9ca3849
caps.latest.revision: 8
ms.openlocfilehash: ed9ff9fc1668a89e1ac0ceac8f0800a15b349226
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369245"
---
# <a name="users-requesting-confirmation"></a><span data-ttu-id="b983a-102">Usuários que solicitam confirmação</span><span class="sxs-lookup"><span data-stu-id="b983a-102">Users Requesting Confirmation</span></span>

<span data-ttu-id="b983a-103">Quando você especifica um valor de `true` para o parâmetro `SupportsShouldProcess` da declaração de atributo cmdlet, os usuários podem especificar o parâmetro `Confirm` no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="b983a-103">When you specify a value of `true` for the `SupportsShouldProcess` parameter of the Cmdlet attribute declaration, users can specify the `Confirm` parameter at the command prompt.</span></span>

<span data-ttu-id="b983a-104">No ambiente padrão, os usuários podem especificar o parâmetro `Confirm` ou o `"-Confirm:$true` para que a confirmação seja solicitada quando o método [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) for chamado.</span><span class="sxs-lookup"><span data-stu-id="b983a-104">In the default environment, users can specify the `Confirm` parameter or `"-Confirm:$true` so that confirmation is requested when the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method is called.</span></span> <span data-ttu-id="b983a-105">Isso ignora as solicitações de confirmação de [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , mesmo para operações de alto impacto.</span><span class="sxs-lookup"><span data-stu-id="b983a-105">This bypasses [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) confirmation requests, even for high-impact operations.</span></span>

<span data-ttu-id="b983a-106">Se `Confirm` não for especificado, a chamada [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) solicitará a confirmação se a variável de preferência `$ConfirmPreference` for igual ou maior que a configuração `ConfirmImpact` do cmdlet ou do provedor.</span><span class="sxs-lookup"><span data-stu-id="b983a-106">If `Confirm` is not specified, the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call requests confirmation if the `$ConfirmPreference` preference variable is equal to or greater than the `ConfirmImpact` setting of the cmdlet or provider.</span></span> <span data-ttu-id="b983a-107">A configuração padrão de `$ConfirmPreference` é alta.</span><span class="sxs-lookup"><span data-stu-id="b983a-107">The default setting of `$ConfirmPreference` is High.</span></span> <span data-ttu-id="b983a-108">Portanto, no ambiente padrão, somente os cmdlets e provedores que especificam uma confirmação de solicitação de ação de alto impacto.</span><span class="sxs-lookup"><span data-stu-id="b983a-108">Therefore, in the default environment, only cmdlets and providers that specify a high-impact action request confirmation.</span></span>

<span data-ttu-id="b983a-109">Se `Confirm` for false ou se `"-Confirm:$false` for especificado, a chamada [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) solicitará a confirmação do usuário e a variável de shell `$ConfirmPreference` será ignorada.</span><span class="sxs-lookup"><span data-stu-id="b983a-109">If `Confirm` is false or if `"-Confirm:$false` is specified, the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call requests confirmation from the user, and the `$ConfirmPreference` shell variable is ignored.</span></span>

## <a name="remarks"></a><span data-ttu-id="b983a-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="b983a-110">Remarks</span></span>

- <span data-ttu-id="b983a-111">Para cmdlets e provedores que especificam `SupportsShouldProcess`, mas não `ConfirmImpact`, essas ações são tratadas como ações de "impacto médio" e não serão solicitadas por padrão.</span><span class="sxs-lookup"><span data-stu-id="b983a-111">For cmdlets and providers that specify `SupportsShouldProcess`, but not `ConfirmImpact`, those actions are handled as "medium impact" actions, and they will not prompt by default.</span></span> <span data-ttu-id="b983a-112">Seu nível de impacto é menor que a configuração padrão da variável de preferência `$ConfirmPreference`.</span><span class="sxs-lookup"><span data-stu-id="b983a-112">Their impact level is less than the default setting of the `$ConfirmPreference` preference variable.</span></span>

- <span data-ttu-id="b983a-113">Se o usuário especificar o parâmetro `Verbose`, ele será notificado da operação mesmo que não seja solicitada a confirmação.</span><span class="sxs-lookup"><span data-stu-id="b983a-113">If the user specifies the `Verbose` parameter, they will be notified of the operation even if they are not prompted for confirmation.</span></span>

## <a name="see-also"></a><span data-ttu-id="b983a-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b983a-114">See Also</span></span>

<span data-ttu-id="b983a-115">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)</span><span class="sxs-lookup"><span data-stu-id="b983a-115">[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)</span></span>
