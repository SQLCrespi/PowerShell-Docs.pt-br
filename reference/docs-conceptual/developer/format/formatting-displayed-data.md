---
ms.date: 09/12/2016
ms.topic: reference
title: Formatar os dados exibidos
description: Formatar os dados exibidos
ms.openlocfilehash: 40f6b3b4fa36062ee0bad3f197ad159f571445c8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667854"
---
# <a name="formatting-displayed-data"></a>Formatar os dados exibidos

Você pode especificar como os pontos de dados individuais na lista, tabela ou exibição ampla são exibidos. Você pode usar o `FormatString` elemento ao definir os itens do modo de exibição ou pode usar o `ScriptBlock` elemento para chamar o `FormatString` método nos dados.

## <a name="using-the-formatstring-element"></a>Usando o elemento FormatString

No exemplo a seguir, o valor da `TotalProcessorTime` Propriedade do objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) é formatado usando o elemento FormatString. a `TotalProcessorTime` Propriedade

```
<TableColumnItem>
  <PropertyName>TotalProcessorTime</PropertyName>
  <FormatString>{0:MMM}{0:dd}{0:HH}:{0:mm}</FormatString>
</TableColumnItem>
```
