---
title: Exemplos de API do Windows PowerShell | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: d7232bb16851f1d568cbdfc4374e287d0875adc8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780161"
---
# <a name="windows-powershell-api-samples"></a>Amostras de API do Windows PowerShell

Esta seção inclui um código de exemplo que mostra como criar espaços de execução que restringem a funcionalidade e como executar comandos de forma assíncrona usando um pool de runspace para fornecer os Runspaces. Você pode usar Microsoft Visual Studio para criar um aplicativo de console e, em seguida, copiar o código dos tópicos nesta seção para seu aplicativo host.

## <a name="in-this-section"></a>Nesta seção

[Exemplo de PowerShell01](./windows-powershell01-sample.md) Este exemplo mostra como usar um objeto [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) para limitar a funcionalidade de um runspace. A saída deste exemplo demonstra como restringir o modo de linguagem do runspace, como marcar um cmdlet como particular, como adicionar e remover cmdlets e provedores, como adicionar um comando de proxy e muito mais.

[Exemplo de PowerShell02](./windows-powershell02-sample.md) Este exemplo mostra como executar comandos de forma assíncrona usando os Runspaces de um pool de runspace. O exemplo gera uma lista de comandos e, em seguida, executa esses comandos enquanto o mecanismo do Windows PowerShell abre um runspace do pool quando necessário.
