---
ms.date: 09/13/2016
ms.topic: reference
title: Amostra Windows PowerShell02
description: Amostra Windows PowerShell02
ms.openlocfilehash: 61dedd72d93d4000edf9a12f12bbb49fbaeb9f3c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657361"
---
# <a name="windows-powershell02-sample"></a>Amostra Windows PowerShell02

Este exemplo mostra como executar comandos de forma assíncrona usando os Runspaces de um pool de runspace. O exemplo gera uma lista de comandos e, em seguida, executa esses comandos enquanto o mecanismo do Windows PowerShell abre um runspace do pool quando necessário.

## <a name="requirements"></a>Requisitos

- Este exemplo requer o Windows PowerShell 2,0.

## <a name="demonstrates"></a>Demonstra

Este exemplo demonstra o seguinte:

- A criação de um objeto RunspacePool com um número mínimo e máximo de espaços de uso podem ser abertos ao mesmo tempo.
- Criando uma lista de comandos.
- Executar os comandos de forma assíncrona.
- Chamando o método [System. Management. Automation. Runspaces. Runspacepool. Getavailablerunspaces *](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces) para ver quantos espaços de execução são gratuitos.
- Capturando a saída do comando com o método [System. Management. Automation. PowerShell. EndInvoke *](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) .

## <a name="example"></a>Exemplo

Este exemplo mostra como abrir os Runspaces de um pool de runspace e como executar comandos de forma assíncrona nesses espaços de execução.

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/PowerShell02/PowerShell02.cs" range="11-96":::

## <a name="see-also"></a>Consulte Também

[Escrever um aplicativo host do Windows PowerShell](./writing-a-windows-powershell-host-application.md)
