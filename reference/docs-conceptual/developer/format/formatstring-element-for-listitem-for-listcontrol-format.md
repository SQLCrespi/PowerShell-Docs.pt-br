---
title: Elemento FormatString para ListItem para ListControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd2cac66-88bb-449f-9d47-bd2cd4fe1801
caps.latest.revision: 13
ms.openlocfilehash: e6024ec4f7fc490c92408047c8c15c775e45bf9d
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363015"
---
# <a name="formatstring-element-for-listitem-for-listcontrol--format"></a><span data-ttu-id="209ed-102">Elemento FormatString para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="209ed-102">FormatString Element for ListItem for ListControl  (Format)</span></span>

<span data-ttu-id="209ed-103">Especifica um padrão de formato que define como o valor de propriedade ou script é exibido.</span><span class="sxs-lookup"><span data-stu-id="209ed-103">Specifies a format pattern that defines how the property or script value is displayed.</span></span>

<span data-ttu-id="209ed-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries para o elemento ListControl (Format) ListEntry para o elemento ListControl (Format) ListItems para ListControl (Format) Elemento ListItem para o elemento ListControl (Format) FormatString para ListItem para ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="209ed-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format) ListItem Element for ListControl (Format) FormatString Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="209ed-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="209ed-105">Syntax</span></span>

```xml
<FormatString>PropertyPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="209ed-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="209ed-106">Attributes and Elements</span></span>

<span data-ttu-id="209ed-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `FormatString`.</span><span class="sxs-lookup"><span data-stu-id="209ed-107">The following sections describe the attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="209ed-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="209ed-108">Attributes</span></span>

<span data-ttu-id="209ed-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="209ed-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="209ed-110">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="209ed-110">Child Elements</span></span>

<span data-ttu-id="209ed-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="209ed-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="209ed-112">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="209ed-112">Parent Elements</span></span>

|<span data-ttu-id="209ed-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="209ed-113">Element</span></span>|<span data-ttu-id="209ed-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="209ed-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="209ed-115">Elemento ListItem (formato)</span><span class="sxs-lookup"><span data-stu-id="209ed-115">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="209ed-116">Define a propriedade ou o script cujo valor é exibido em uma linha da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="209ed-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="209ed-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="209ed-117">Text Value</span></span>

<span data-ttu-id="209ed-118">Especifique o padrão usado para formatar os dados.</span><span class="sxs-lookup"><span data-stu-id="209ed-118">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="209ed-119">Por exemplo, você pode usar esse padrão para formatar o valor de qualquer propriedade que seja do tipo [System. TimeSpan](/dotnet/api/System.TimeSpan): {0: mmm} {0: dd} {0: hh}: {0: mm}.</span><span class="sxs-lookup"><span data-stu-id="209ed-119">For example, you can use this pattern to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="209ed-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="209ed-120">Remarks</span></span>

<span data-ttu-id="209ed-121">Cadeias de caracteres de formato podem ser usadas ao criar exibições de tabela, exibições de lista, exibições amplas ou exibições personalizadas.</span><span class="sxs-lookup"><span data-stu-id="209ed-121">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="209ed-122">Para obter mais informações sobre como formatar um valor exibido em uma exibição, consulte [Formatando dados exibidos](./formatting-displayed-data.md).</span><span class="sxs-lookup"><span data-stu-id="209ed-122">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="209ed-123">Para obter mais informações sobre como usar cadeias de caracteres de formato em exibições de lista, consulte [criando exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="209ed-123">For more information about using format strings in list views, see [Creating List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="209ed-124">Exemplo</span><span class="sxs-lookup"><span data-stu-id="209ed-124">Example</span></span>

<span data-ttu-id="209ed-125">O exemplo a seguir mostra como definir uma cadeia de caracteres de formatação para o valor da propriedade `StartTime`.</span><span class="sxs-lookup"><span data-stu-id="209ed-125">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<ListItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</ListItem>
```

## <a name="see-also"></a><span data-ttu-id="209ed-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="209ed-126">See Also</span></span>

[<span data-ttu-id="209ed-127">Criando um modo de exibição de lista</span><span class="sxs-lookup"><span data-stu-id="209ed-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="209ed-128">Elemento ListItem (formato)</span><span class="sxs-lookup"><span data-stu-id="209ed-128">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="209ed-129">Escrevendo um arquivo de tipos e formatação do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="209ed-129">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
