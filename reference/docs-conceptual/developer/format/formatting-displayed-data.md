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
# <a name="formatting-displayed-data"></a><span data-ttu-id="f0103-102">Formatar os dados exibidos</span><span class="sxs-lookup"><span data-stu-id="f0103-102">Formatting Displayed Data</span></span>

<span data-ttu-id="f0103-103">Você pode especificar como os pontos de dados individuais na lista, tabela ou exibição ampla são exibidos.</span><span class="sxs-lookup"><span data-stu-id="f0103-103">You can specify how the individual data points in your List, Table, or Wide view are displayed.</span></span> <span data-ttu-id="f0103-104">Você pode usar o `FormatString` elemento ao definir os itens do modo de exibição ou pode usar o `ScriptBlock` elemento para chamar o `FormatString` método nos dados.</span><span class="sxs-lookup"><span data-stu-id="f0103-104">You can use the `FormatString` element when defining the items of your view, or you can use the `ScriptBlock` element to call the `FormatString` method on the data.</span></span>

## <a name="using-the-formatstring-element"></a><span data-ttu-id="f0103-105">Usando o elemento FormatString</span><span class="sxs-lookup"><span data-stu-id="f0103-105">Using the FormatString Element</span></span>

<span data-ttu-id="f0103-106">No exemplo a seguir, o valor da `TotalProcessorTime` Propriedade do objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) é formatado usando o elemento FormatString.</span><span class="sxs-lookup"><span data-stu-id="f0103-106">In the following example the value of the `TotalProcessorTime` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object is formatted using the FormatString element.</span></span> <span data-ttu-id="f0103-107">a `TotalProcessorTime` Propriedade</span><span class="sxs-lookup"><span data-stu-id="f0103-107">the `TotalProcessorTime` property</span></span>

```
<TableColumnItem>
  <PropertyName>TotalProcessorTime</PropertyName>
  <FormatString>{0:MMM}{0:dd}{0:HH}:{0:mm}</FormatString>
</TableColumnItem>
```
