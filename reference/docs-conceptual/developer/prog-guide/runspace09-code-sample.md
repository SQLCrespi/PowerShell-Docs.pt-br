---
title: Exemplo de código RunSpace09 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 136e451f-767b-42e0-bd6f-6486693abd5e
caps.latest.revision: 6
ms.openlocfilehash: 122a40dea93d874a7c131774e3d1abb148bcd4fc
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72360125"
---
# <a name="runspace09-code-sample"></a>Exemplo de código RunSpace09

Aqui está o código-fonte para o exemplo de Runspace09 descrito em [criando um aplicativo de console que invoca um pipeline de forma assíncrona](https://msdn.microsoft.com/en-us/198c1c94-2a06-457e-93ce-c0d910618e47). Esse aplicativo de exemplo cria e abre um runspace, cria e invoca de forma assíncrona um pipeline e, em seguida, usa eventos de pipeline para processar o script de forma assíncrona. O script que é executado por esse aplicativo cria os inteiros de 1 a 10 em intervalos de 0,5 segundos (500 MS).

## <a name="code-sample"></a>Exemplo de Código

[!code-csharp[Runspace09.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace09/Runspace09.cs#L11-L113 "Runspace09.cs")]

## <a name="see-also"></a>Consulte Também

[SDK do Windows PowerShell](../windows-powershell-reference.md)
