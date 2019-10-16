---
title: Elemento PropertyName de ListItem para ListControl (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01ae8cbe-acdc-4043-bd6e-1118a5691a55
caps.latest.revision: 12
ms.openlocfilehash: 405184f7bdbf1955f1df7766bf2723c244dcc27f
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362375"
---
# <a name="propertyname-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="7d797-102">Elemento PropertyName para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="7d797-102">PropertyName Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="7d797-103">Especifica a propriedade .NET cujo valor é exibido na lista.</span><span class="sxs-lookup"><span data-stu-id="7d797-103">Specifies the .NET property whose value is displayed in the list.</span></span>

<span data-ttu-id="7d797-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl elemento (Format) ListEntries Element (Format) o elemento ListEntry Element (Format) ListItem elemento (Format) ListItem Element (Format) o elemento PropertyName para ListItem (formato)</span><span class="sxs-lookup"><span data-stu-id="7d797-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) ListItems Element (Format) ListItem Element (Format) PropertyName Element for ListItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7d797-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7d797-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7d797-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="7d797-106">Attributes and Elements</span></span>

<span data-ttu-id="7d797-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `PropertyName`.</span><span class="sxs-lookup"><span data-stu-id="7d797-107">The following sections describe the attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7d797-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="7d797-108">Attributes</span></span>

<span data-ttu-id="7d797-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="7d797-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7d797-110">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="7d797-110">Child Elements</span></span>

<span data-ttu-id="7d797-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="7d797-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7d797-112">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="7d797-112">Parent Elements</span></span>

|<span data-ttu-id="7d797-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="7d797-113">Element</span></span>|<span data-ttu-id="7d797-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="7d797-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7d797-115">Elemento ListItem (formato)</span><span class="sxs-lookup"><span data-stu-id="7d797-115">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="7d797-116">Define a propriedade ou o script cujo valor é exibido na linha da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="7d797-116">Defines the property or script whose value is displayed in the row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7d797-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="7d797-117">Text Value</span></span>

<span data-ttu-id="7d797-118">Especifique o nome da propriedade cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="7d797-118">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="7d797-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="7d797-119">Remarks</span></span>

<span data-ttu-id="7d797-120">Quando esse elemento é especificado, você não pode especificar o elemento [scriptblock](./scriptblock-element-for-listitem-for-listcontrol-format.md) .</span><span class="sxs-lookup"><span data-stu-id="7d797-120">When this element is specified, you cannot specify the [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element.</span></span>

<span data-ttu-id="7d797-121">Além de exibir o valor da propriedade, você também pode especificar um rótulo para o valor ou uma cadeia de caracteres de formato que possa ser usada para alterar a exibição do valor.</span><span class="sxs-lookup"><span data-stu-id="7d797-121">In addition to displaying the property value, you can also specify a label for the value or a format string that can be used to change the display of the value.</span></span> <span data-ttu-id="7d797-122">Para obter mais informações sobre como especificar dados em um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="7d797-122">For more information about specifying data in a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="7d797-123">Exemplo</span><span class="sxs-lookup"><span data-stu-id="7d797-123">Example</span></span>

<span data-ttu-id="7d797-124">O exemplo a seguir mostra como especificar o rótulo e a propriedade cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="7d797-124">The following example shows how to specify the label and property whose value is displayed.</span></span>

```xml
ListItem>
  <Label>NameOfProperty</Label>
  <PropertyName>.NetTypeProperty</PropertyName>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="7d797-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7d797-125">See Also</span></span>

[<span data-ttu-id="7d797-126">Elemento ScriptBlock para ListItem para ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="7d797-126">ScriptBlock Element for ListItem for ListControl (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="7d797-127">Criando um modo de exibição de lista</span><span class="sxs-lookup"><span data-stu-id="7d797-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="7d797-128">Elemento ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="7d797-128">ListItem Element for ListControl(Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="7d797-129">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="7d797-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
