---
ms.date: 09/13/2016
ms.topic: reference
title: Exemplo de código RunSpace09
description: Exemplo de código RunSpace09
ms.openlocfilehash: 52ebfa5dcfd6c12d2ded78a41a6090caa5087149
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654198"
---
# <a name="runspace09-code-sample"></a>Exemplo de código RunSpace09

Aqui está o código-fonte para o exemplo de Runspace09 descrito em [criando um aplicativo de console que invoca um pipeline de forma assíncrona](https://msdn.microsoft.com/198c1c94-2a06-457e-93ce-c0d910618e47).
Esse aplicativo de exemplo cria e abre um runspace, cria e invoca de forma assíncrona um pipeline e, em seguida, usa eventos de pipeline para processar o script de forma assíncrona. O script que é executado por esse aplicativo cria os inteiros de 1 a 10 em intervalos de 0,5 segundos (500 MS).

## <a name="code-sample"></a>Exemplo de código

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace09/Runspace09.cs" range="11-113":::

## <a name="see-also"></a>Consulte Também

[SDK do Windows PowerShell](../windows-powershell-reference.md)
