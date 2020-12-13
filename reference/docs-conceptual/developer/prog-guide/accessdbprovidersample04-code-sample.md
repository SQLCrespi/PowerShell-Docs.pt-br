---
ms.date: 09/13/2016
ms.topic: reference
title: Exemplo de código AccessDbProviderSample04
description: Exemplo de código AccessDbProviderSample04
ms.openlocfilehash: bb70ce9f1b1c94349c354a8771fedf7fcb1bb320
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647567"
---
# <a name="accessdbprovidersample04-code-sample"></a>Exemplo de código AccessDbProviderSample04

O código a seguir mostra a implementação do provedor do Windows PowerShell descrito em [criando um provedor de contêiner do Windows PowerShell](./creating-a-windows-powershell-container-provider.md).
Esse provedor funciona em armazenamentos de dados de várias camadas. Para esse tipo de armazenamento de dados, o nível superior do repositório contém os itens raiz e cada nível subsequente é referido como um nó de itens filho. Ao permitir que o usuário trabalhe nesses nós filho, um usuário pode interagir hierarquicamente por meio do armazenamento de dados.

## <a name="code-sample"></a>Exemplo de código

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="11-1635":::

## <a name="see-also"></a>Consulte Também

[SDK do Windows PowerShell](../windows-powershell-reference.md)
