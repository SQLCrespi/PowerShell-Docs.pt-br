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
ms.openlocfilehash: 1a21af4b48a414d9c9fee57871eacb0a39c9ab11
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67734901"
---
# <a name="runspace09-code-sample"></a>Exemplo de código RunSpace09

Aqui está o código-fonte para o exemplo Runspace09 descrito [criação de um Console do aplicativo que invoca um Pipeline de forma assíncrona](https://msdn.microsoft.com/en-us/198c1c94-2a06-457e-93ce-c0d910618e47). Este aplicativo de exemplo cria e abre um espaço de execução, cria e invoca um pipeline de forma assíncrona e, em seguida, usa eventos para processar o script de forma assíncrona do pipeline. O script que é executado por esse aplicativo cria os inteiros de 1 a 10 em intervalos de 0,5 segundo (500 ms).

## <a name="code-sample"></a>Exemplo de código

[!code-csharp[Runspace09.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace09/Runspace09.cs#L11-L113 "Runspace09.cs")]

## <a name="see-also"></a>Consulte Também

[SDK do Windows PowerShell](../windows-powershell-reference.md)