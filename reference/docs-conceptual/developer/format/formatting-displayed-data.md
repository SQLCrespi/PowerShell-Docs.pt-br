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
ms.openlocfilehash: e915ac71feb50cb58cfa9195f0de94763affdb77
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363695"
---
# <a name="formatting-displayed-data"></a><span data-ttu-id="469a3-102">Formatar os dados exibidos</span><span class="sxs-lookup"><span data-stu-id="469a3-102">Formatting Displayed Data</span></span>

<span data-ttu-id="469a3-103">Você pode especificar como os pontos de dados individuais na lista, tabela ou exibição ampla são exibidos.</span><span class="sxs-lookup"><span data-stu-id="469a3-103">You can specify how the individual data points in your List, Table, or Wide view are displayed.</span></span> <span data-ttu-id="469a3-104">Você pode usar o elemento `FormatString` ao definir os itens do modo de exibição ou pode usar o elemento `ScriptBlock` para chamar o método `FormatString` nos dados.</span><span class="sxs-lookup"><span data-stu-id="469a3-104">You can use the `FormatString` element when defining the items of your view, or you can use the `ScriptBlock` element to call the `FormatString` method on the data.</span></span>

## <a name="using-the-formatstring-element"></a><span data-ttu-id="469a3-105">Usando o elemento FormatString</span><span class="sxs-lookup"><span data-stu-id="469a3-105">Using the FormatString Element</span></span>

<span data-ttu-id="469a3-106">No exemplo a seguir, o valor da propriedade `TotalProcessorTime` do objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) é formatado usando o elemento FormatString.</span><span class="sxs-lookup"><span data-stu-id="469a3-106">In the following example the value of the `TotalProcessorTime` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object is formatted using the FormatString element.</span></span> <span data-ttu-id="469a3-107">a propriedade `TotalProcessorTime`</span><span class="sxs-lookup"><span data-stu-id="469a3-107">the `TotalProcessorTime` property</span></span>

```
<TableColumnItem>
  <PropertyName>TotalProcessorTime</PropertyName>
  <FormatString>{0:MMM}{0:dd}{0:HH}:{0:mm}</FormatString>
</TableColumnItem>
```



