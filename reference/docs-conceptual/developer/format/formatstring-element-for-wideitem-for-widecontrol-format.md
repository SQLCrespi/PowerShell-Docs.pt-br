---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento FormatString para WideItem para WideControl (formato)
description: Elemento FormatString para WideItem para WideControl (formato)
ms.openlocfilehash: f67a18e3ec4f1323e7f9be8904db518c679d53e5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667871"
---
# <a name="formatstring-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="8521f-103">Elemento FormatString para WideItem para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="8521f-103">FormatString Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="8521f-104">Especifica um padrão de formato que define como o valor de propriedade ou script é exibido na exibição.</span><span class="sxs-lookup"><span data-stu-id="8521f-104">Specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>

<span data-ttu-id="8521f-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) WideControl elemento (Format) WideEntries Element (Format) WideEntry elemento para WideControl (Format) WideItem Element para WideControl (Format) FormatString Element for WideItem for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="8521f-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element for WideControl (Format) WideItem Element for WideControl (Format) FormatString Element for WideItem for WideControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8521f-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8521f-106">Syntax</span></span>

```xml
<FormatString>PropertyPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8521f-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="8521f-107">Attributes and Elements</span></span>

<span data-ttu-id="8521f-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `FormatString` elemento.</span><span class="sxs-lookup"><span data-stu-id="8521f-108">The following sections describe the attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8521f-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="8521f-109">Attributes</span></span>

<span data-ttu-id="8521f-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="8521f-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8521f-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="8521f-111">Child Elements</span></span>

<span data-ttu-id="8521f-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="8521f-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8521f-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="8521f-113">Parent Elements</span></span>

|<span data-ttu-id="8521f-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="8521f-114">Element</span></span>|<span data-ttu-id="8521f-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="8521f-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8521f-116">Elemento WideItem para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="8521f-116">WideItem Element for WideControl (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="8521f-117">Define a propriedade ou o script cujo valor é exibido em uma linha da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="8521f-117">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="8521f-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="8521f-118">Text Value</span></span>

<span data-ttu-id="8521f-119">Especifique o padrão usado para formatar os dados.</span><span class="sxs-lookup"><span data-stu-id="8521f-119">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="8521f-120">Por exemplo, você pode usar esse padrão para formatar o valor de qualquer propriedade que seja do tipo [System. TimeSpan](/dotnet/api/System.TimeSpan): {0: mmm} {0: dd} {0: hh}: {0: mm}.</span><span class="sxs-lookup"><span data-stu-id="8521f-120">For example, you can use this pattern to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="8521f-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="8521f-121">Remarks</span></span>

<span data-ttu-id="8521f-122">Cadeias de caracteres de formato podem ser usadas ao criar exibições de tabela, exibições de lista, exibições amplas ou exibições personalizadas.</span><span class="sxs-lookup"><span data-stu-id="8521f-122">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="8521f-123">Para obter mais informações sobre como formatar um valor exibido em uma exibição, consulte [Formatando dados exibidos](./formatting-displayed-data.md).</span><span class="sxs-lookup"><span data-stu-id="8521f-123">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="8521f-124">Para obter mais informações sobre como usar cadeias de caracteres de formato em exibições amplas, consulte [criando uma exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="8521f-124">For more information about using format strings in wide views, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="8521f-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8521f-125">Example</span></span>

<span data-ttu-id="8521f-126">O exemplo a seguir mostra como definir uma cadeia de caracteres de formatação para o valor da `StartTime` propriedade.</span><span class="sxs-lookup"><span data-stu-id="8521f-126">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<WideItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</WideItem>
```

## <a name="see-also"></a><span data-ttu-id="8521f-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8521f-127">See Also</span></span>

[<span data-ttu-id="8521f-128">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="8521f-128">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="8521f-129">Elemento WideItem para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="8521f-129">WideItem Element for WideControl (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="8521f-130">Escrevendo um arquivo de tipos e formatação do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8521f-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
