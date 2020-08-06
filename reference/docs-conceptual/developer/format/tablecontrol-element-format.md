---
title: Elemento TableControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 34e20006a7501650f2a22f71a3d7e999fb8b2337
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785125"
---
# <a name="tablecontrol-element-format"></a><span data-ttu-id="5a586-102">Elemento TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="5a586-102">TableControl Element (Format)</span></span>

<span data-ttu-id="5a586-103">Define um formato de tabela para uma exibição.</span><span class="sxs-lookup"><span data-stu-id="5a586-103">Defines a table format for a view.</span></span>

<span data-ttu-id="5a586-104">Elemento ViewDefinitions (Format) View element (Format) TableControl elemento (Format)</span><span class="sxs-lookup"><span data-stu-id="5a586-104">ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5a586-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5a586-105">Syntax</span></span>

```xml
<TableControl>
  <AutoSize/>
  <HideTableHeaders/>
  <TableHeaders>...</TableHeaders>
  <TableRowEntries>...</TableRowEntries>
</TableControl>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="5a586-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="5a586-106">Attributes and Elements</span></span>

<span data-ttu-id="5a586-107">As seções a seguir descrevem atributos, elementos filho e elemento pai do `TableControl` elemento.</span><span class="sxs-lookup"><span data-stu-id="5a586-107">The following sections describe attributes, child elements, and parent element of the `TableControl` element.</span></span> <span data-ttu-id="5a586-108">Você deve especificar as linhas da tabela.</span><span class="sxs-lookup"><span data-stu-id="5a586-108">You must specify the rows of the table.</span></span> <span data-ttu-id="5a586-109">Todos os outros elementos filho são opcionais.</span><span class="sxs-lookup"><span data-stu-id="5a586-109">All other child elements are optional.</span></span>

### <a name="attributes"></a><span data-ttu-id="5a586-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="5a586-110">Attributes</span></span>

<span data-ttu-id="5a586-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="5a586-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5a586-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="5a586-112">Child Elements</span></span>

|<span data-ttu-id="5a586-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="5a586-113">Element</span></span>|<span data-ttu-id="5a586-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="5a586-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5a586-115">Elemento AutoSize para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="5a586-115">AutoSize Element for TableControl (Format)</span></span>](./autosize-element-for-tablecontrol-format.md)|<span data-ttu-id="5a586-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="5a586-116">Optional element.</span></span><br /><br /> <span data-ttu-id="5a586-117">Especifica se o tamanho da coluna e o número de colunas são ajustados com base no tamanho dos dados.</span><span class="sxs-lookup"><span data-stu-id="5a586-117">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>|
|[<span data-ttu-id="5a586-118">Elemento HideTableHeaders para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="5a586-118">HideTableHeaders Element for TableControl (Format)</span></span>](./hidetableheaders-element-format.md)|<span data-ttu-id="5a586-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="5a586-119">Optional element.</span></span><br /><br /> <span data-ttu-id="5a586-120">Indica se o cabeçalho da tabela não é exibido.</span><span class="sxs-lookup"><span data-stu-id="5a586-120">Indicates whether the header of the table is not displayed.</span></span>|
|[<span data-ttu-id="5a586-121">Elemento TableHeaders para TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="5a586-121">TableHeaders Element for TableControl (Format)</span></span>](./tableheaders-element-format.md)|<span data-ttu-id="5a586-122">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="5a586-122">Required element.</span></span><br /><br /> <span data-ttu-id="5a586-123">Define os rótulos, as larguras e o alinhamento dos dados para as colunas da exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="5a586-123">Defines the labels, the widths, and the alignment of the data for the columns of the table view.</span></span>|
|[<span data-ttu-id="5a586-124">Elemento TableRowEntries para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="5a586-124">TableRowEntries Element for TableControl (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)|<span data-ttu-id="5a586-125">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="5a586-125">Optional element.</span></span><br /><br /> <span data-ttu-id="5a586-126">Fornece as definições do modo de exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="5a586-126">Provides the definitions of the table view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5a586-127">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="5a586-127">Parent Elements</span></span>

|<span data-ttu-id="5a586-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="5a586-128">Element</span></span>|<span data-ttu-id="5a586-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="5a586-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5a586-130">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="5a586-130">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="5a586-131">Define uma exibição que é usada para exibir os membros de um ou mais objetos.</span><span class="sxs-lookup"><span data-stu-id="5a586-131">Defines a view that is used to display the members of one or more objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5a586-132">Comentários</span><span class="sxs-lookup"><span data-stu-id="5a586-132">Remarks</span></span>

<span data-ttu-id="5a586-133">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="5a586-133">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="5a586-134">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5a586-134">Example</span></span>

<span data-ttu-id="5a586-135">Este exemplo mostra um `TableControl` elemento que é usado para exibir as propriedades do objeto [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="5a586-135">This example shows a `TableControl` element that is used to display the properties of the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="5a586-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5a586-136">See Also</span></span>

[<span data-ttu-id="5a586-137">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="5a586-137">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="5a586-138">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="5a586-138">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="5a586-139">Elemento AutoSize para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="5a586-139">AutoSize Element for TableControl (Format)</span></span>](./autosize-element-for-tablecontrol-format.md)

[<span data-ttu-id="5a586-140">Elemento HideTableHeaders (formato)</span><span class="sxs-lookup"><span data-stu-id="5a586-140">HideTableHeaders Element (Format)</span></span>](./hidetableheaders-element-format.md)

[<span data-ttu-id="5a586-141">Elemento TableHeaders (formato)</span><span class="sxs-lookup"><span data-stu-id="5a586-141">TableHeaders Element (Format)</span></span>](./tableheaders-element-format.md)

[<span data-ttu-id="5a586-142">Elemento TableRowEntries (Format)</span><span class="sxs-lookup"><span data-stu-id="5a586-142">TableRowEntries Element (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)

[<span data-ttu-id="5a586-143">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a586-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
