---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento FormatString para TableColumnItem para TableControl (formato)
description: Elemento FormatString para TableColumnItem para TableControl (formato)
ms.openlocfilehash: 3d386e61ac321c05e0b298019c2298f76b391b21
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667888"
---
# <a name="formatstring-element-for-tablecolumnitem-for-tablecontrol-format"></a><span data-ttu-id="b2e43-103">Elemento FormatString para TableColumnItem para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="b2e43-103">FormatString Element for TableColumnItem for TableControl (Format)</span></span>

<span data-ttu-id="b2e43-104">Especifica um padrão de formato que define como o valor de propriedade ou script da tabela é exibido.</span><span class="sxs-lookup"><span data-stu-id="b2e43-104">Specifies a format pattern that defines how the property or script value of the table is displayed.</span></span>

<span data-ttu-id="b2e43-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibição de elemento (Format) TableControl Element (Format) TableRowEntries elemento (Format) TableRowEntry Element (Format) TableColumnItems elemento (Format) TableColumnItem Element (Format) @ Element for TableColumnItem (Format)</span><span class="sxs-lookup"><span data-stu-id="b2e43-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) FormatString Element for TableColumnItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b2e43-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b2e43-106">Syntax</span></span>

```xml
<FormatString>FormatPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b2e43-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="b2e43-107">Attributes and Elements</span></span>

<span data-ttu-id="b2e43-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `FormatString` elemento.</span><span class="sxs-lookup"><span data-stu-id="b2e43-108">The following sections describe attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b2e43-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="b2e43-109">Attributes</span></span>

<span data-ttu-id="b2e43-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="b2e43-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b2e43-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="b2e43-111">Child Elements</span></span>

<span data-ttu-id="b2e43-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="b2e43-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b2e43-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="b2e43-113">Parent Elements</span></span>

|<span data-ttu-id="b2e43-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="b2e43-114">Element</span></span>|<span data-ttu-id="b2e43-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="b2e43-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b2e43-116">Elemento TableColumnItem (Format)</span><span class="sxs-lookup"><span data-stu-id="b2e43-116">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="b2e43-117">Define a propriedade ou o script cujo valor é exibido na coluna da linha.</span><span class="sxs-lookup"><span data-stu-id="b2e43-117">Defines the property or script whose value is displayed in the column of the row.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b2e43-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="b2e43-118">Text Value</span></span>

<span data-ttu-id="b2e43-119">Especifique o padrão usado para formatar os dados.</span><span class="sxs-lookup"><span data-stu-id="b2e43-119">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="b2e43-120">Por exemplo, esse padrão pode ser usado para formatar o valor de qualquer propriedade que seja do tipo [System. TimeSpan](/dotnet/api/System.TimeSpan): {0: mmm} {0: dd} {0: hh}: {0: mm}.</span><span class="sxs-lookup"><span data-stu-id="b2e43-120">For example, this pattern can be used to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="b2e43-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="b2e43-121">Remarks</span></span>

<span data-ttu-id="b2e43-122">Cadeias de caracteres de formato podem ser usadas ao criar exibições de tabela, exibições de lista, exibições amplas ou exibições personalizadas.</span><span class="sxs-lookup"><span data-stu-id="b2e43-122">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="b2e43-123">Para obter mais informações sobre como formatar um valor exibido em uma exibição, consulte [Formatando dados exibidos](./formatting-displayed-data.md).</span><span class="sxs-lookup"><span data-stu-id="b2e43-123">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="b2e43-124">Para obter mais informações sobre os componentes de uma exibição de tabela, consulte [exibição de tabela](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="b2e43-124">For more information about the components of a table view, see [Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="b2e43-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b2e43-125">Example</span></span>

<span data-ttu-id="b2e43-126">O exemplo a seguir mostra como definir uma cadeia de caracteres de formatação para o valor da `StartTime` propriedade.</span><span class="sxs-lookup"><span data-stu-id="b2e43-126">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<TableColumnItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</TableColumnItem>
```

## <a name="see-also"></a><span data-ttu-id="b2e43-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b2e43-127">See Also</span></span>

[<span data-ttu-id="b2e43-128">Criar uma exibição de tabela</span><span class="sxs-lookup"><span data-stu-id="b2e43-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="b2e43-129">Formatar os dados exibidos</span><span class="sxs-lookup"><span data-stu-id="b2e43-129">Formatting Displayed Data</span></span>](./formatting-displayed-data.md)

[<span data-ttu-id="b2e43-130">Elemento TableColumnItem (Format)</span><span class="sxs-lookup"><span data-stu-id="b2e43-130">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="b2e43-131">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b2e43-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
