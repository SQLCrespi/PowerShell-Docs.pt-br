---
ms.date: 09/13/2016
ms.topic: reference
title: Parâmetros de quantidade
description: Parâmetros de quantidade
ms.openlocfilehash: 3f7c23eec34a709b1f2d59f611c93909b20f4124
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92650306"
---
# <a name="quantity-parameters"></a>Parâmetros de quantidade

A tabela a seguir lista os nomes recomendados e a funcionalidade para parâmetros de quantidade.

|Parâmetro|Funcionalidade|
|---|---|
|**Todos**<br>Tipo de dados: booliano|Implemente esse parâmetro para que ele `true` indique que todos os recursos devem ser afetados em vez de um subconjunto padrão de recursos. Implemente esse parâmetro para que `false` indique um subconjunto dos recursos.|
|**Alocação**<br>Tipo de dados: Int32|Implemente esse parâmetro para que o usuário possa especificar o número de itens a serem alocados.|
|**BlockCount**<br>Tipo de dados: Int64|Implemente esse parâmetro para que o usuário possa especificar a contagem de blocos.|
|**Count**<br>Tipo de dados: Int64|Implemente esse parâmetro para que o usuário possa especificar a contagem.|
|**Escopo**<br>Tipo de dados: palavra-chave|Implemente esse parâmetro para que o usuário possa especificar o escopo no qual operar.|

## <a name="see-also"></a>Consulte Também

[Parâmetros de cmdlets](./cmdlet-parameters.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
