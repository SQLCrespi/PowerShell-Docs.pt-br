---
ms.date: 09/13/2016
ms.topic: reference
title: Exemplo de código RunSpace08
description: Exemplo de código RunSpace08
ms.openlocfilehash: f8d08e5b6bbd98d0901abe5b05c8b9ee682b8e04
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654221"
---
# <a name="runspace08-code-sample"></a>Exemplo de código RunSpace08

Aqui está o código-fonte para o exemplo de Runspace08 descrito em [criando um aplicativo de console que adiciona parâmetros a um comando](https://msdn.microsoft.com/848b2b46-60f1-4a86-b448-cfc7c0cccfba).
Esse aplicativo de exemplo cria um runspace, cria um pipeline, adiciona dois comandos ao pipeline, adiciona dois parâmetros ao segundo comando e, em seguida, executa o pipeline. Os comandos que são adicionados ao pipeline são os `Get-Process` `Sort-Object` cmdlets e.

## <a name="code-sample"></a>Exemplo de código

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace08/Runspace08.cs" range="11-86":::

## <a name="see-also"></a>Consulte Também

[SDK do Windows PowerShell](../windows-powershell-reference.md)
