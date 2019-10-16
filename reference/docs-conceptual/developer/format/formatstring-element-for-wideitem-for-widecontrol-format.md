---
title: Elemento FormatString para WideItem para WideControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5bc6ea26-3ca6-4bab-8a13-29189821ba15
caps.latest.revision: 7
ms.openlocfilehash: a1dc145864a6904fd4af6c3b9187819c49e224b0
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363025"
---
# <a name="formatstring-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="b5aa5-102">Elemento FormatString para WideItem para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="b5aa5-102">FormatString Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="b5aa5-103">Especifica um padrão de formato que define como o valor de propriedade ou script é exibido na exibição.</span><span class="sxs-lookup"><span data-stu-id="b5aa5-103">Specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>

<span data-ttu-id="b5aa5-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) WideControl elemento (Format) WideEntries Element (Format) WideEntry elemento do elemento WideControl (Format) WideItem para o elemento WideControl (Format) FormatString para WideItem para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="b5aa5-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element for WideControl (Format) WideItem Element for WideControl (Format) FormatString Element for WideItem for WideControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b5aa5-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b5aa5-105">Syntax</span></span>

```xml
<FormatString>PropertyPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b5aa5-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="b5aa5-106">Attributes and Elements</span></span>

<span data-ttu-id="b5aa5-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `FormatString`.</span><span class="sxs-lookup"><span data-stu-id="b5aa5-107">The following sections describe the attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b5aa5-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="b5aa5-108">Attributes</span></span>

<span data-ttu-id="b5aa5-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="b5aa5-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b5aa5-110">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="b5aa5-110">Child Elements</span></span>

<span data-ttu-id="b5aa5-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="b5aa5-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b5aa5-112">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="b5aa5-112">Parent Elements</span></span>

|<span data-ttu-id="b5aa5-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="b5aa5-113">Element</span></span>|<span data-ttu-id="b5aa5-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="b5aa5-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b5aa5-115">Elemento WideItem para WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="b5aa5-115">WideItem Element for WideControl (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="b5aa5-116">Define a propriedade ou o script cujo valor é exibido em uma linha da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="b5aa5-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b5aa5-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="b5aa5-117">Text Value</span></span>

<span data-ttu-id="b5aa5-118">Especifique o padrão usado para formatar os dados.</span><span class="sxs-lookup"><span data-stu-id="b5aa5-118">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="b5aa5-119">Por exemplo, você pode usar esse padrão para formatar o valor de qualquer propriedade que seja do tipo [System. TimeSpan](/dotnet/api/System.TimeSpan): {0: mmm} {0: dd} {0: hh}: {0: mm}.</span><span class="sxs-lookup"><span data-stu-id="b5aa5-119">For example, you can use this pattern to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="b5aa5-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="b5aa5-120">Remarks</span></span>

<span data-ttu-id="b5aa5-121">Cadeias de caracteres de formato podem ser usadas ao criar exibições de tabela, exibições de lista, exibições amplas ou exibições personalizadas.</span><span class="sxs-lookup"><span data-stu-id="b5aa5-121">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="b5aa5-122">Para obter mais informações sobre como formatar um valor exibido em uma exibição, consulte [Formatando dados exibidos](./formatting-displayed-data.md).</span><span class="sxs-lookup"><span data-stu-id="b5aa5-122">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="b5aa5-123">Para obter mais informações sobre como usar cadeias de caracteres de formato em exibições amplas, consulte [criando uma exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="b5aa5-123">For more information about using format strings in wide views, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="b5aa5-124">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b5aa5-124">Example</span></span>

<span data-ttu-id="b5aa5-125">O exemplo a seguir mostra como definir uma cadeia de caracteres de formatação para o valor da propriedade `StartTime`.</span><span class="sxs-lookup"><span data-stu-id="b5aa5-125">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<WideItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</WideItem>
```

## <a name="see-also"></a><span data-ttu-id="b5aa5-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b5aa5-126">See Also</span></span>

[<span data-ttu-id="b5aa5-127">Criando uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="b5aa5-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="b5aa5-128">Elemento WideItem para WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="b5aa5-128">WideItem Element for WideControl (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="b5aa5-129">Escrevendo um arquivo de tipos e formatação do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5aa5-129">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
