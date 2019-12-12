---
title: Elemento Label para ListItem para ListControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c693ff46-d1ad-4dc7-93ac-41ff2fc6c103
caps.latest.revision: 9
ms.openlocfilehash: c1293d5a1f942704ac01388c66bd9009fd340e82
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362885"
---
# <a name="label-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="787f2-102">Elemento Label para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="787f2-102">Label Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="787f2-103">Especifica o rótulo que é exibido à esquerda do valor de propriedade ou script na linha.</span><span class="sxs-lookup"><span data-stu-id="787f2-103">Specifies the label that is displayed to the left of the property or script value in the row.</span></span>

<span data-ttu-id="787f2-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries para ListControl (Format) ListEntry Element para ListControl (Format) ListItems para o elemento ListEntry para ListControl ( Format) ListItem Element para ListItems para o elemento de rótulo ListControl (Format) para ListItem para ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="787f2-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems for ListEntry for ListControl Element (Format) ListItem Element for ListItems for ListControl (Format) Label Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="787f2-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="787f2-105">Syntax</span></span>

```xml
<Label>Label for displayed value</Label>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="787f2-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="787f2-106">Attributes and Elements</span></span>

<span data-ttu-id="787f2-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `Label`.</span><span class="sxs-lookup"><span data-stu-id="787f2-107">The following sections describe the attributes, child elements, and the parent element of the `Label` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="787f2-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="787f2-108">Attributes</span></span>

<span data-ttu-id="787f2-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="787f2-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="787f2-110">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="787f2-110">Child Elements</span></span>

<span data-ttu-id="787f2-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="787f2-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="787f2-112">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="787f2-112">Parent Elements</span></span>

|<span data-ttu-id="787f2-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="787f2-113">Element</span></span>|<span data-ttu-id="787f2-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="787f2-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="787f2-115">Elemento ListItem para ListItems para ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="787f2-115">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="787f2-116">Define a propriedade ou o script cujo valor é exibido em uma linha da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="787f2-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="787f2-117">Valor de Texto</span><span class="sxs-lookup"><span data-stu-id="787f2-117">Text Value</span></span>

<span data-ttu-id="787f2-118">Especifique o rótulo a ser exibido à esquerda do valor da propriedade ou do script.</span><span class="sxs-lookup"><span data-stu-id="787f2-118">Specify the label to be display to the left of the property or script value.</span></span>

## <a name="remarks"></a><span data-ttu-id="787f2-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="787f2-119">Remarks</span></span>

<span data-ttu-id="787f2-120">Se um rótulo não for especificado, o nome da propriedade ou do script será exibido.</span><span class="sxs-lookup"><span data-stu-id="787f2-120">If a label is not specified, the name of the property or the script is displayed.</span></span> <span data-ttu-id="787f2-121">Para obter mais informações sobre como usar rótulos em um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="787f2-121">For more information about using labels in a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="787f2-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="787f2-122">Example</span></span>

<span data-ttu-id="787f2-123">O exemplo a seguir mostra como adicionar um rótulo a uma linha.</span><span class="sxs-lookup"><span data-stu-id="787f2-123">The following example shows how to add a label to a row.</span></span>

```xml
<ListItem>
  <Label>Property1: </Label>
  <PropertyName>DotNetProperty1</PropertyName>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="787f2-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="787f2-124">See Also</span></span>

[<span data-ttu-id="787f2-125">Criando um modo de exibição de lista</span><span class="sxs-lookup"><span data-stu-id="787f2-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="787f2-126">Elemento ListItem (formato)</span><span class="sxs-lookup"><span data-stu-id="787f2-126">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="787f2-127">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="787f2-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
