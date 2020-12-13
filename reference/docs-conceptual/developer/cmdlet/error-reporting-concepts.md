---
ms.date: 09/13/2016
ms.topic: reference
title: Conceitos de relatórios de erro
description: Conceitos de relatórios de erro
ms.openlocfilehash: 353e628c63667a2db010556b2ed9169809b742f4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653034"
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

[Registros de erros do Windows PowerShell](./windows-powershell-error-records.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)
