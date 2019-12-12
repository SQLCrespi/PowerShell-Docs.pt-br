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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369245"
---
# <a name="users-requesting-confirmation"></a>Usuários que solicitam confirmação

Quando você especifica um valor de `true` para o parâmetro `SupportsShouldProcess` da declaração de atributo cmdlet, os usuários podem especificar o parâmetro `Confirm` no prompt de comando.

No ambiente padrão, os usuários podem especificar o parâmetro `Confirm` ou `"-Confirm:$true` para que a confirmação seja solicitada quando o método [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) for chamado. Isso ignora as solicitações de confirmação de [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) , mesmo para operações de alto impacto.

Se `Confirm` não for especificado, a chamada [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) solicitará a confirmação se a variável de preferência `$ConfirmPreference` for igual ou maior que a configuração `ConfirmImpact` do cmdlet ou do provedor. A configuração padrão de `$ConfirmPreference` é alta. Portanto, no ambiente padrão, somente os cmdlets e provedores que especificam uma confirmação de solicitação de ação de alto impacto.

Se `Confirm` for false ou se `"-Confirm:$false` for especificado, a chamada [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) solicitará a confirmação do usuário e a variável de shell `$ConfirmPreference` será ignorada.

## <a name="remarks"></a>Comentários

- Para cmdlets e provedores que especificam `SupportsShouldProcess`, mas não `ConfirmImpact`, essas ações são tratadas como ações de "impacto médio" e não serão solicitadas por padrão. Seu nível de impacto é menor que a configuração padrão da variável de preferência de `$ConfirmPreference`.

- Se o usuário especificar o parâmetro `Verbose`, ele será notificado da operação mesmo que não seja solicitada a confirmação.

## <a name="see-also"></a>Consulte Também

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
