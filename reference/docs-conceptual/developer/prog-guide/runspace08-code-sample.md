---
title: Exemplo de código RunSpace08 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f286201-8a02-4b00-9a2c-1b833ccdbdbf
caps.latest.revision: 7
ms.openlocfilehash: 20032913969606f722f3768b0433775aeaa8c3a8
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72366475"
---
# <a name="runspace08-code-sample"></a>Exemplo de código RunSpace08

Aqui está o código-fonte para o exemplo de Runspace08 descrito em [criando um aplicativo de console que adiciona parâmetros a um comando](https://msdn.microsoft.com/en-us/848b2b46-60f1-4a86-b448-cfc7c0cccfba). Esse aplicativo de exemplo cria um runspace, cria um pipeline, adiciona dois comandos ao pipeline, adiciona dois parâmetros ao segundo comando e, em seguida, executa o pipeline. Os comandos que são adicionados ao pipeline são os cmdlets `Get-Process` e `Sort-Object`.

## <a name="code-sample"></a>Exemplo de Código

[!code-csharp[Runspace08.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace08/Runspace08.cs#L11-L86 "Runspace08.cs")]

## <a name="see-also"></a>Consulte Também

[SDK do Windows PowerShell](../windows-powershell-reference.md)
