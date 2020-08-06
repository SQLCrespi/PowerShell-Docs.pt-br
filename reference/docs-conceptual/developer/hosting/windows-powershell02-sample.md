---
title: Exemplo de PowerShell02 do Windows | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: a82366a88addb08e186eede79e621d90d915c50f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779379"
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
