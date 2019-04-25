---
title: Elemento FormatString para WideItem para WideControl (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5bc6ea26-3ca6-4bab-8a13-29189821ba15
caps.latest.revision: 7
ms.openlocfilehash: a1dc145864a6904fd4af6c3b9187819c49e224b0
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065675"
---
# <a name="formatstring-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="cc544-102">Elemento FormatString para WideItem para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="cc544-102">FormatString Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="cc544-103">Especifica um padrão de formato que define como o valor da propriedade ou o script é exibido no modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="cc544-103">Specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>

<span data-ttu-id="cc544-104">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento elemento WideControl (formato) elemento WideEntries (formato) WideEntry elemento de configuração para WideControl (formato) WideItem elemento para o elemento de FormatString WideControl (formato) para WideItem para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="cc544-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element for WideControl (Format) WideItem Element for WideControl (Format) FormatString Element for WideItem for WideControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cc544-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cc544-105">Syntax</span></span>

```xml
<FormatString>PropertyPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cc544-106">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="cc544-106">Attributes and Elements</span></span>

<span data-ttu-id="cc544-107">As seções a seguir descrevem os atributos, elementos filho e o elemento pai do `FormatString` elemento.</span><span class="sxs-lookup"><span data-stu-id="cc544-107">The following sections describe the attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="cc544-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="cc544-108">Attributes</span></span>

<span data-ttu-id="cc544-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="cc544-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cc544-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="cc544-110">Child Elements</span></span>

<span data-ttu-id="cc544-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="cc544-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="cc544-112">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="cc544-112">Parent Elements</span></span>

|<span data-ttu-id="cc544-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="cc544-113">Element</span></span>|<span data-ttu-id="cc544-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="cc544-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cc544-115">Elemento WideItem para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="cc544-115">WideItem Element for WideControl (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="cc544-116">Define a propriedade ou o script cujo valor é exibido em uma linha da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="cc544-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="cc544-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="cc544-117">Text Value</span></span>

<span data-ttu-id="cc544-118">Especifique o padrão que é usado para formatar os dados.</span><span class="sxs-lookup"><span data-stu-id="cc544-118">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="cc544-119">Por exemplo, você pode usar esse padrão para formatar o valor de qualquer propriedade que é do tipo [System. TimeSpan](/dotnet/api/System.TimeSpan): {0: MMM} {0:dd} {{0:hh}: {0:mm}.</span><span class="sxs-lookup"><span data-stu-id="cc544-119">For example, you can use this pattern to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="cc544-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="cc544-120">Remarks</span></span>

<span data-ttu-id="cc544-121">Cadeias de caracteres de formato podem ser usadas ao criar modos de exibição de tabela, exibições de lista, modos de exibição amplos ou modos de exibição personalizados.</span><span class="sxs-lookup"><span data-stu-id="cc544-121">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="cc544-122">Para obter mais informações sobre como formatar um valor exibido em uma exibição, consulte [formatação exibidos dados](./formatting-displayed-data.md).</span><span class="sxs-lookup"><span data-stu-id="cc544-122">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="cc544-123">Para obter mais informações sobre como usar cadeias de caracteres de formato em modos de exibição amplos, consulte [criando uma exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="cc544-123">For more information about using format strings in wide views, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="cc544-124">Exemplo</span><span class="sxs-lookup"><span data-stu-id="cc544-124">Example</span></span>

<span data-ttu-id="cc544-125">O exemplo a seguir mostra como definir uma cadeia de caracteres de formatação para o valor da `StartTime` propriedade.</span><span class="sxs-lookup"><span data-stu-id="cc544-125">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<WideItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</WideItem>
```

## <a name="see-also"></a><span data-ttu-id="cc544-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cc544-126">See Also</span></span>

[<span data-ttu-id="cc544-127">Criando uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="cc544-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="cc544-128">Elemento WideItem para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="cc544-128">WideItem Element for WideControl (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="cc544-129">Escrevendo um formatação do Windows PowerShell e tipos de arquivo</span><span class="sxs-lookup"><span data-stu-id="cc544-129">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
