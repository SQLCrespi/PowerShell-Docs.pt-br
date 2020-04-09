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
ms.openlocfilehash: d7fa39485eea833483682c91c96417a76e5d770f
ms.sourcegitcommit: 7f2479edd329dfdc55726afff7019d45e45f9156
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80977532"
---
# <a name="runspace09-code-sample"></a>Exemplo de código RunSpace09

Aqui está o código-fonte para o exemplo de Runspace09 descrito em [criando um aplicativo de console que invoca um pipeline de forma assíncrona](https://msdn.microsoft.com/198c1c94-2a06-457e-93ce-c0d910618e47).
Esse aplicativo de exemplo cria e abre um runspace, cria e invoca de forma assíncrona um pipeline e, em seguida, usa eventos de pipeline para processar o script de forma assíncrona. O script que é executado por esse aplicativo cria os inteiros de 1 a 10 em intervalos de 0,5 segundos (500 MS).

## <a name="code-sample"></a>Exemplo de código

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace09/Runspace09.cs" range="11-113":::

## <a name="see-also"></a>Consulte Também

[SDK do Windows PowerShell](../windows-powershell-reference.md)
