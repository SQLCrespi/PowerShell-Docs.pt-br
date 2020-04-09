---
title: Exemplo de código AccessDbProviderSample04 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9374c4a-e499-4516-9eb6-107c59df98d9
caps.latest.revision: 7
ms.openlocfilehash: 60f0ed4e3d39ee93ab63023161d09a6c7b914798
ms.sourcegitcommit: 7f2479edd329dfdc55726afff7019d45e45f9156
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80978569"
---
# <a name="accessdbprovidersample04-code-sample"></a>Exemplo de código AccessDbProviderSample04

O código a seguir mostra a implementação do provedor do Windows PowerShell descrito em [criando um provedor de contêiner do Windows PowerShell](./creating-a-windows-powershell-container-provider.md).
Esse provedor funciona em armazenamentos de dados de várias camadas. Para esse tipo de armazenamento de dados, o nível superior do repositório contém os itens raiz e cada nível subsequente é referido como um nó de itens filho. Ao permitir que o usuário trabalhe nesses nós filho, um usuário pode interagir hierarquicamente por meio do armazenamento de dados.

## <a name="code-sample"></a>Exemplo de código

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="11-1635":::

## <a name="see-also"></a>Consulte Também

[SDK do Windows PowerShell](../windows-powershell-reference.md)
