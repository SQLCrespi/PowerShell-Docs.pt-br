---
title: Usuários solicitando confirmação | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 6f0effb35a110f33248a582fab874e3ab95c7df4
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786332"
---
# <a name="users-requesting-confirmation"></a>Usuários que solicitam confirmação

Quando você especifica um valor de `true` para o `SupportsShouldProcess` parâmetro da declaração de atributo do cmdlet, os usuários podem especificar o `Confirm` parâmetro no prompt de comando.

No ambiente padrão, os usuários podem especificar o `Confirm` parâmetro ou `"-Confirm:$true` , portanto, a confirmação é solicitada quando o método [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) é chamado. Isso ignora as solicitações de confirmação de [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , mesmo para operações de alto impacto.

Se `Confirm` não for especificado, a chamada [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) solicitará a confirmação se a `$ConfirmPreference` variável de preferência for igual ou maior que a `ConfirmImpact` configuração do cmdlet ou do provedor. A configuração padrão de `$ConfirmPreference` é alta. Portanto, no ambiente padrão, somente os cmdlets e provedores que especificam uma confirmação de solicitação de ação de alto impacto.

Se `Confirm` for false ou se `"-Confirm:$false` for especificado, a chamada [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) solicitará a confirmação do usuário e a `$ConfirmPreference` variável de shell será ignorada.

## <a name="remarks"></a>Comentários

- Para cmdlets e provedores que especificam `SupportsShouldProcess` , mas não `ConfirmImpact` , essas ações são manipuladas como ações de "impacto médio" e não serão solicitadas por padrão. Seu nível de impacto é menor que a configuração padrão da `$ConfirmPreference` variável de preferência.

- Se o usuário especificar o `Verbose` parâmetro, ele será notificado sobre a operação mesmo que não seja solicitada a confirmação.

## <a name="see-also"></a>Consulte Também

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
