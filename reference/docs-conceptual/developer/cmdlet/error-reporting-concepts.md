---
title: Conceitos de relatório de erros | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- non-terminating errors [PowerShell SDK]
- errors [PowerShell SDK], described
- terminating errors [PowerShell SDK]
- errors [PowerShell SDK]
ms.assetid: 0dce97c0-bd9a-4691-8ca3-e8d5dea902c5
caps.latest.revision: 11
ms.openlocfilehash: 2f185e415e3effc2cf09a282ca1167e3bcfb7d6a
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364615"
---
# <a name="error-reporting-concepts"></a>Conceitos de relatórios de erro

O Windows PowerShell fornece dois mecanismos para relatar erros: um mecanismo para *encerrar erros* e outro mecanismo para *erros de não encerramento*. É importante que o cmdlet Relate erros corretamente para que o aplicativo host que está executando seus cmdlets possa reagir de maneira apropriada.

O cmdlet deve chamar o método [System. Management. Automation. cmdlet. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) quando ocorrer um erro que não deve ou não permitir que o cmdlet continue a processar seus objetos de entrada. O cmdlet deve chamar o método [System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) para relatar erros de não finalização quando o cmdlet puder continuar processando os objetos de entrada. Os dois métodos fornecem um registro de erro que o aplicativo host pode usar para investigar a causa do erro.

Use as diretrizes a seguir para determinar se um erro é um erro de encerramento ou de não finalização.

- Um erro será um erro de encerramento se ele impedir que o cmdlet continue a processar o objeto atual ou de processar com êxito outros objetos de entrada, independentemente de seu conteúdo.

- Um erro será um erro de encerramento se você não quiser que o cmdlet continue a processar o objeto atual ou quaisquer outros objetos de entrada, independentemente de seu conteúdo.

- Um erro será um erro de encerramento se ocorrer em um cmdlet que não aceita nem retorna um objeto ou se ele ocorrer em um cmdlet que aceita ou retorna apenas um objeto.

- Um erro será um erro de não finalização se você quiser que o cmdlet continue a processar o objeto atual e quaisquer outros objetos de entrada.

- Um erro será um erro de não finalização se ele estiver relacionado a um objeto de entrada ou subconjunto de objetos de entrada específico.

## <a name="see-also"></a>Consulte Também

[System. Management. Automation. cmdlet. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)

[System. Management. Automation. cmdlet. WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[Registros de erro do Windows PowerShell](./windows-powershell-error-records.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
