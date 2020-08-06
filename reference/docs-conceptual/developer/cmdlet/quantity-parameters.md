---
title: Parâmetros de quantidade | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 7ff6562380bb6336b08879b31d8d9fed47bfb6a7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781810"
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

[Escrevendo um Cmdlet do Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
