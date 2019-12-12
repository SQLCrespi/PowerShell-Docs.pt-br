---
title: Parâmetros de quantidade | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8c0bd8a9-1749-4885-ab24-38c0a4d9f2cb
caps.latest.revision: 6
ms.openlocfilehash: 7a3efc60fcc8729d833f6de070016cfd08cc9b88
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369555"
---
# <a name="quantity-parameters"></a>Parâmetros de quantidade

A tabela a seguir lista os nomes recomendados e a funcionalidade para parâmetros de quantidade.

|Parâmetro|Funcionalidade|
|---|---|
|**Todos**<br>Tipo de dados: booliano|Implemente esse parâmetro para que `true` indique que todos os recursos devem ser tratados em vez de um subconjunto padrão de recursos. Implemente esse parâmetro para que `false` indique um subconjunto dos recursos.|
|**Alocação**<br>Tipo de dados: Int32|Implemente esse parâmetro para que o usuário possa especificar o número de itens a serem alocados.|
|**BlockCount**<br>Tipo de dados: Int64|Implemente esse parâmetro para que o usuário possa especificar a contagem de blocos.|
|**Count**<br>Tipo de dados: Int64|Implemente esse parâmetro para que o usuário possa especificar a contagem.|
|**Escopo**<br>Tipo de dados: palavra-chave|Implemente esse parâmetro para que o usuário possa especificar o escopo no qual operar.|

## <a name="see-also"></a>Consulte Também

[Parâmetros de cmdlet](./cmdlet-parameters.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
