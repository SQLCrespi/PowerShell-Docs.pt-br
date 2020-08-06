---
title: Formatando dados exibidos | Microsoft Docs
ms.date: 09/12/2016
ms.openlocfilehash: 97d23b3079b2779e518b6b6d2f2ac0c5e9d1f3a3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781504"
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
