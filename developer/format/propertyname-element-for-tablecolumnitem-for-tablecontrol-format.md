---
title: Elemento PropertyName para TableColumnItem para TableControl (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb26d72c-2f77-4801-badf-0537ccc55e31
caps.latest.revision: 10
ms.openlocfilehash: 6e86b6a0874b385703121802bc8108a0410442cd
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064590"
---
# <a name="propertyname-element-for-tablecolumnitem-for-tablecontrol-format"></a><span data-ttu-id="6a39b-102">Elemento PropertyName para TableColumnItem para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="6a39b-102">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>

<span data-ttu-id="6a39b-103">Especifica a propriedade cujo valor é exibido na coluna da linha.</span><span class="sxs-lookup"><span data-stu-id="6a39b-103">Specifies the property whose value is displayed in the column of the row.</span></span>

<span data-ttu-id="6a39b-104">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento TableControl elemento (formato) elemento TableRowEntries (formato) elemento TableRowEntry (formato) elemento TableColumnItems (formato) TableColumnItem elemento de configuração (formato) Elemento PropertyName para TableColumnItem (formato)</span><span class="sxs-lookup"><span data-stu-id="6a39b-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) PropertyName Element for TableColumnItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6a39b-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6a39b-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6a39b-106">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="6a39b-106">Attributes and Elements</span></span>

<span data-ttu-id="6a39b-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `PropertyName` elemento.</span><span class="sxs-lookup"><span data-stu-id="6a39b-107">The following sections describe attributes, child elements, and parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6a39b-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="6a39b-108">Attributes</span></span>

<span data-ttu-id="6a39b-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="6a39b-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6a39b-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="6a39b-110">Child Elements</span></span>

<span data-ttu-id="6a39b-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="6a39b-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6a39b-112">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="6a39b-112">Parent Elements</span></span>

|<span data-ttu-id="6a39b-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="6a39b-113">Element</span></span>|<span data-ttu-id="6a39b-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="6a39b-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6a39b-115">Elemento TableColumnItem (formato)</span><span class="sxs-lookup"><span data-stu-id="6a39b-115">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="6a39b-116">Define a propriedade ou cujo valor é exibido na coluna da linha do script.</span><span class="sxs-lookup"><span data-stu-id="6a39b-116">Defines the property or script whose value is displayed in the column of the row.</span></span>|

## <a name="text-value"></a><span data-ttu-id="6a39b-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="6a39b-117">Text Value</span></span>

<span data-ttu-id="6a39b-118">Especifique o nome da propriedade cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="6a39b-118">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="6a39b-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="6a39b-119">Remarks</span></span>

<span data-ttu-id="6a39b-120">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [criando uma exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="6a39b-120">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="6a39b-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="6a39b-121">Example</span></span>

<span data-ttu-id="6a39b-122">Este exemplo mostra uma `TableColumnItem` elemento que especifica a `Status` propriedade da [Diagnostics](/dotnet/api/System.Diagnostics.Process) objeto.</span><span class="sxs-lookup"><span data-stu-id="6a39b-122">This example shows a `TableColumnItem` element that specifies the `Status` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a><span data-ttu-id="6a39b-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6a39b-123">See Also</span></span>

[<span data-ttu-id="6a39b-124">Criando uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="6a39b-124">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="6a39b-125">Elemento TableColumnItem (formato)</span><span class="sxs-lookup"><span data-stu-id="6a39b-125">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="6a39b-126">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a39b-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
