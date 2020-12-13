---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento FormatString para ListItem para ListControl (formato)
description: Elemento FormatString para ListItem para ListControl (formato)
ms.openlocfilehash: 1c16da92928ea632241942f4f2c63390c4fea706
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667905"
---
# <a name="formatstring-element-for-listitem-for-listcontrol--format"></a><span data-ttu-id="2b54e-103">Elemento FormatString para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="2b54e-103">FormatString Element for ListItem for ListControl  (Format)</span></span>

<span data-ttu-id="2b54e-104">Especifica um padrão de formato que define como o valor de propriedade ou script é exibido.</span><span class="sxs-lookup"><span data-stu-id="2b54e-104">Specifies a format pattern that defines how the property or script value is displayed.</span></span>

<span data-ttu-id="2b54e-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries para o elemento ListControl (Format) ListEntry para o elemento ListControl (Format) ListItems para o elemento ListControl (Format) ListItem de ListControl (Format) FormatString para ListItem para ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="2b54e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format) ListItem Element for ListControl (Format) FormatString Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2b54e-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2b54e-106">Syntax</span></span>

```xml
<FormatString>PropertyPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2b54e-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="2b54e-107">Attributes and Elements</span></span>

<span data-ttu-id="2b54e-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `FormatString` elemento.</span><span class="sxs-lookup"><span data-stu-id="2b54e-108">The following sections describe the attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2b54e-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="2b54e-109">Attributes</span></span>

<span data-ttu-id="2b54e-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="2b54e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2b54e-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="2b54e-111">Child Elements</span></span>

<span data-ttu-id="2b54e-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="2b54e-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2b54e-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="2b54e-113">Parent Elements</span></span>

|<span data-ttu-id="2b54e-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="2b54e-114">Element</span></span>|<span data-ttu-id="2b54e-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="2b54e-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2b54e-116">Elemento ListItem (formato)</span><span class="sxs-lookup"><span data-stu-id="2b54e-116">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="2b54e-117">Define a propriedade ou o script cujo valor é exibido em uma linha da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="2b54e-117">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2b54e-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="2b54e-118">Text Value</span></span>

<span data-ttu-id="2b54e-119">Especifique o padrão usado para formatar os dados.</span><span class="sxs-lookup"><span data-stu-id="2b54e-119">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="2b54e-120">Por exemplo, você pode usar esse padrão para formatar o valor de qualquer propriedade que seja do tipo [System. TimeSpan](/dotnet/api/System.TimeSpan): {0: mmm} {0: dd} {0: hh}: {0: mm}.</span><span class="sxs-lookup"><span data-stu-id="2b54e-120">For example, you can use this pattern to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="2b54e-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="2b54e-121">Remarks</span></span>

<span data-ttu-id="2b54e-122">Cadeias de caracteres de formato podem ser usadas ao criar exibições de tabela, exibições de lista, exibições amplas ou exibições personalizadas.</span><span class="sxs-lookup"><span data-stu-id="2b54e-122">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="2b54e-123">Para obter mais informações sobre como formatar um valor exibido em uma exibição, consulte [Formatando dados exibidos](./formatting-displayed-data.md).</span><span class="sxs-lookup"><span data-stu-id="2b54e-123">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="2b54e-124">Para obter mais informações sobre como usar cadeias de caracteres de formato em exibições de lista, consulte [criando exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="2b54e-124">For more information about using format strings in list views, see [Creating List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="2b54e-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="2b54e-125">Example</span></span>

<span data-ttu-id="2b54e-126">O exemplo a seguir mostra como definir uma cadeia de caracteres de formatação para o valor da `StartTime` propriedade.</span><span class="sxs-lookup"><span data-stu-id="2b54e-126">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<ListItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</ListItem>
```

## <a name="see-also"></a><span data-ttu-id="2b54e-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2b54e-127">See Also</span></span>

[<span data-ttu-id="2b54e-128">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="2b54e-128">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="2b54e-129">Elemento ListItem (formato)</span><span class="sxs-lookup"><span data-stu-id="2b54e-129">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="2b54e-130">Escrevendo um arquivo de tipos e formatação do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b54e-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
