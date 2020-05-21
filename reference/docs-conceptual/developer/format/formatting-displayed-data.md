---
title: Formatando dados exibidos | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 38971643-2a3d-4f5b-a1fa-6334c162b8ed
caps.latest.revision: 4
ms.openlocfilehash: 9f3a3176ae16ac7c014cadce6b4e856f9bd3b5da
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560382"
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
