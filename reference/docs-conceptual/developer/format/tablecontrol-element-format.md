---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento TableControl (formato)
description: Elemento TableControl (formato)
ms.openlocfilehash: 93e05e22d61504d7781b6f3c07f9a3fd0b3c9e8a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651456"
---
# <a name="tablecontrol-element-format"></a><span data-ttu-id="8d848-103">Elemento TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="8d848-103">TableControl Element (Format)</span></span>

<span data-ttu-id="8d848-104">Define um formato de tabela para uma exibição.</span><span class="sxs-lookup"><span data-stu-id="8d848-104">Defines a table format for a view.</span></span>

<span data-ttu-id="8d848-105">Elemento ViewDefinitions (Format) View element (Format) TableControl elemento (Format)</span><span class="sxs-lookup"><span data-stu-id="8d848-105">ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8d848-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8d848-106">Syntax</span></span>

```xml
<TableControl>
  <AutoSize/>
  <HideTableHeaders/>
  <TableHeaders>...</TableHeaders>
  <TableRowEntries>...</TableRowEntries>
</TableControl>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="8d848-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="8d848-107">Attributes and Elements</span></span>

<span data-ttu-id="8d848-108">As seções a seguir descrevem atributos, elementos filho e elemento pai do `TableControl` elemento.</span><span class="sxs-lookup"><span data-stu-id="8d848-108">The following sections describe attributes, child elements, and parent element of the `TableControl` element.</span></span> <span data-ttu-id="8d848-109">Você deve especificar as linhas da tabela.</span><span class="sxs-lookup"><span data-stu-id="8d848-109">You must specify the rows of the table.</span></span> <span data-ttu-id="8d848-110">Todos os outros elementos filho são opcionais.</span><span class="sxs-lookup"><span data-stu-id="8d848-110">All other child elements are optional.</span></span>

### <a name="attributes"></a><span data-ttu-id="8d848-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="8d848-111">Attributes</span></span>

<span data-ttu-id="8d848-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="8d848-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8d848-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="8d848-113">Child Elements</span></span>

|<span data-ttu-id="8d848-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="8d848-114">Element</span></span>|<span data-ttu-id="8d848-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="8d848-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8d848-116">Elemento AutoSize para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="8d848-116">AutoSize Element for TableControl (Format)</span></span>](./autosize-element-for-tablecontrol-format.md)|<span data-ttu-id="8d848-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="8d848-117">Optional element.</span></span><br /><br /> <span data-ttu-id="8d848-118">Especifica se o tamanho da coluna e o número de colunas são ajustados com base no tamanho dos dados.</span><span class="sxs-lookup"><span data-stu-id="8d848-118">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>|
|[<span data-ttu-id="8d848-119">Elemento HideTableHeaders para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="8d848-119">HideTableHeaders Element for TableControl (Format)</span></span>](./hidetableheaders-element-format.md)|<span data-ttu-id="8d848-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="8d848-120">Optional element.</span></span><br /><br /> <span data-ttu-id="8d848-121">Indica se o cabeçalho da tabela não é exibido.</span><span class="sxs-lookup"><span data-stu-id="8d848-121">Indicates whether the header of the table is not displayed.</span></span>|
|[<span data-ttu-id="8d848-122">Elemento TableHeaders para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="8d848-122">TableHeaders Element for TableControl (Format)</span></span>](./tableheaders-element-format.md)|<span data-ttu-id="8d848-123">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="8d848-123">Required element.</span></span><br /><br /> <span data-ttu-id="8d848-124">Define os rótulos, as larguras e o alinhamento dos dados para as colunas da exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="8d848-124">Defines the labels, the widths, and the alignment of the data for the columns of the table view.</span></span>|
|[<span data-ttu-id="8d848-125">Elemento TableRowEntries para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="8d848-125">TableRowEntries Element for TableControl (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)|<span data-ttu-id="8d848-126">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="8d848-126">Optional element.</span></span><br /><br /> <span data-ttu-id="8d848-127">Fornece as definições do modo de exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="8d848-127">Provides the definitions of the table view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="8d848-128">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="8d848-128">Parent Elements</span></span>

|<span data-ttu-id="8d848-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="8d848-129">Element</span></span>|<span data-ttu-id="8d848-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="8d848-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8d848-131">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="8d848-131">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="8d848-132">Define uma exibição que é usada para exibir os membros de um ou mais objetos.</span><span class="sxs-lookup"><span data-stu-id="8d848-132">Defines a view that is used to display the members of one or more objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8d848-133">Comentários</span><span class="sxs-lookup"><span data-stu-id="8d848-133">Remarks</span></span>

<span data-ttu-id="8d848-134">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="8d848-134">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="8d848-135">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8d848-135">Example</span></span>

<span data-ttu-id="8d848-136">Este exemplo mostra um `TableControl` elemento que é usado para exibir as propriedades do objeto [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="8d848-136">This example shows a `TableControl` element that is used to display the properties of the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>
    <TableHeaders>...</TableHeaders>
    <TableRowEntries>...</TableRowEntries>
  </TableControl>
</View>

```

## <a name="see-also"></a><span data-ttu-id="8d848-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8d848-137">See Also</span></span>

[<span data-ttu-id="8d848-138">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="8d848-138">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="8d848-139">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="8d848-139">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="8d848-140">Elemento AutoSize para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="8d848-140">AutoSize Element for TableControl (Format)</span></span>](./autosize-element-for-tablecontrol-format.md)

[<span data-ttu-id="8d848-141">Elemento HideTableHeaders (formato)</span><span class="sxs-lookup"><span data-stu-id="8d848-141">HideTableHeaders Element (Format)</span></span>](./hidetableheaders-element-format.md)

[<span data-ttu-id="8d848-142">Elemento TableHeaders (formato)</span><span class="sxs-lookup"><span data-stu-id="8d848-142">TableHeaders Element (Format)</span></span>](./tableheaders-element-format.md)

[<span data-ttu-id="8d848-143">Elemento TableRowEntries (Format)</span><span class="sxs-lookup"><span data-stu-id="8d848-143">TableRowEntries Element (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)

[<span data-ttu-id="8d848-144">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d848-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
