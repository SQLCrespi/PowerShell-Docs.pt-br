---
title: Elemento ScriptBlock para ListItem para ListControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 74e30938-00ef-46fd-84e5-f0a83706a50e
caps.latest.revision: 11
ms.openlocfilehash: 76b600256af3f957f7fe0578f9fef810262aa5d5
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364805"
---
# <a name="scriptblock-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="785f9-102">Elemento ScriptBlock para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="785f9-102">ScriptBlock Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="785f9-103">Especifica o script cujo valor é exibido na linha.</span><span class="sxs-lookup"><span data-stu-id="785f9-103">Specifies the script whose value is displayed in the row.</span></span>

<span data-ttu-id="785f9-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries para o elemento ListControl (Format) ListEntry para ListEntries para o elemento ListControl (Format) ListItems para ListEntry para o elemento ListControl (Format) ListItem para ListItems para o elemento ScriptBlock (Format) elementar para ListItem para ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="785f9-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ScriptBlock Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="785f9-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="785f9-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="785f9-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="785f9-106">Attributes and Elements</span></span>

<span data-ttu-id="785f9-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `ScriptBlock`.</span><span class="sxs-lookup"><span data-stu-id="785f9-107">The following sections describe the attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="785f9-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="785f9-108">Attributes</span></span>

<span data-ttu-id="785f9-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="785f9-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="785f9-110">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="785f9-110">Child Elements</span></span>

<span data-ttu-id="785f9-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="785f9-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="785f9-112">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="785f9-112">Parent Elements</span></span>

|<span data-ttu-id="785f9-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="785f9-113">Element</span></span>|<span data-ttu-id="785f9-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="785f9-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="785f9-115">Elemento ListItem (formato)</span><span class="sxs-lookup"><span data-stu-id="785f9-115">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="785f9-116">Define a propriedade ou o script cujo valor é exibido em uma linha da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="785f9-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="785f9-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="785f9-117">Text Value</span></span>

<span data-ttu-id="785f9-118">Especifique o script cujo valor é exibido na linha.</span><span class="sxs-lookup"><span data-stu-id="785f9-118">Specify the script whose value is displayed in the row.</span></span>

## <a name="remarks"></a><span data-ttu-id="785f9-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="785f9-119">Remarks</span></span>

<span data-ttu-id="785f9-120">Quando esse elemento é especificado, você não pode especificar o elemento [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) .</span><span class="sxs-lookup"><span data-stu-id="785f9-120">When this element is specified, you cannot specify the [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element.</span></span>

<span data-ttu-id="785f9-121">Para obter mais informações sobre como especificar scripts em uma exibição de lista, consulte [exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="785f9-121">For more information about specifying scripts in a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="785f9-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="785f9-122">Example</span></span>

<span data-ttu-id="785f9-123">O exemplo a seguir mostra como especificar a propriedade cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="785f9-123">The following example shows how to specify the property whose value is displayed.</span></span>

```xml
<ListItem>
  <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="785f9-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="785f9-124">See Also</span></span>

[<span data-ttu-id="785f9-125">Elemento PropertyName para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="785f9-125">PropertyName Element for ListItem for ListControl (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="785f9-126">Criando um modo de exibição de lista</span><span class="sxs-lookup"><span data-stu-id="785f9-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="785f9-127">Elemento ListItem para ListItems para ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="785f9-127">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="785f9-128">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="785f9-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
