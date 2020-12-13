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
# <a name="formatting-displayed-data"></a><span data-ttu-id="e8fc7-103">Formatar os dados exibidos</span><span class="sxs-lookup"><span data-stu-id="e8fc7-103">Formatting Displayed Data</span></span>

<span data-ttu-id="e8fc7-104">Você pode especificar como os pontos de dados individuais na lista, tabela ou exibição ampla são exibidos.</span><span class="sxs-lookup"><span data-stu-id="e8fc7-104">You can specify how the individual data points in your List, Table, or Wide view are displayed.</span></span> <span data-ttu-id="e8fc7-105">Você pode usar o `FormatString` elemento ao definir os itens do modo de exibição ou pode usar o `ScriptBlock` elemento para chamar o `FormatString` método nos dados.</span><span class="sxs-lookup"><span data-stu-id="e8fc7-105">You can use the `FormatString` element when defining the items of your view, or you can use the `ScriptBlock` element to call the `FormatString` method on the data.</span></span>

## <a name="using-the-formatstring-element"></a><span data-ttu-id="e8fc7-106">Usando o elemento FormatString</span><span class="sxs-lookup"><span data-stu-id="e8fc7-106">Using the FormatString Element</span></span>

<span data-ttu-id="e8fc7-107">No exemplo a seguir, o valor da `TotalProcessorTime` Propriedade do objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) é formatado usando o elemento FormatString.</span><span class="sxs-lookup"><span data-stu-id="e8fc7-107">In the following example the value of the `TotalProcessorTime` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object is formatted using the FormatString element.</span></span> <span data-ttu-id="e8fc7-108">a `TotalProcessorTime` Propriedade</span><span class="sxs-lookup"><span data-stu-id="e8fc7-108">the `TotalProcessorTime` property</span></span>

```
<TableColumnItem>
  <PropertyName>TotalProcessorTime</PropertyName>
  <FormatString>{0:MMM}{0:dd}{0:HH}:{0:mm}</FormatString>
</TableColumnItem>
```
