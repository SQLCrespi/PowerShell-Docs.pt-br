---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Label para ListItem para ListControl (formato)
description: Elemento Label para ListItem para ListControl (formato)
ms.openlocfilehash: 01ff34c4129abe2c76a0a21794e756b77bff12bf
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666647"
---
# <a name="label-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="9be73-103">Elemento Label para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="9be73-103">Label Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="9be73-104">Especifica o rótulo que é exibido à esquerda do valor de propriedade ou script na linha.</span><span class="sxs-lookup"><span data-stu-id="9be73-104">Specifies the label that is displayed to the left of the property or script value in the row.</span></span>

<span data-ttu-id="9be73-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries para ListControl (Format) ListEntry Element para ListControl (Format) ListItems para ListEntry para ListControl Element (Format) ListItem elemento para ListItems para o elemento de rótulo ListControl (Format) para ListItem para ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="9be73-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems for ListEntry for ListControl Element (Format) ListItem Element for ListItems for ListControl (Format) Label Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9be73-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9be73-106">Syntax</span></span>

```xml
<Label>Label for displayed value</Label>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9be73-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="9be73-107">Attributes and Elements</span></span>

<span data-ttu-id="9be73-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `Label` elemento.</span><span class="sxs-lookup"><span data-stu-id="9be73-108">The following sections describe the attributes, child elements, and the parent element of the `Label` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9be73-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="9be73-109">Attributes</span></span>

<span data-ttu-id="9be73-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="9be73-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9be73-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="9be73-111">Child Elements</span></span>

<span data-ttu-id="9be73-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="9be73-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9be73-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="9be73-113">Parent Elements</span></span>

|<span data-ttu-id="9be73-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="9be73-114">Element</span></span>|<span data-ttu-id="9be73-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="9be73-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9be73-116">Elemento ListItem para ListItems para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="9be73-116">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="9be73-117">Define a propriedade ou o script cujo valor é exibido em uma linha da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="9be73-117">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9be73-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="9be73-118">Text Value</span></span>

<span data-ttu-id="9be73-119">Especifique o rótulo a ser exibido à esquerda do valor da propriedade ou do script.</span><span class="sxs-lookup"><span data-stu-id="9be73-119">Specify the label to be display to the left of the property or script value.</span></span>

## <a name="remarks"></a><span data-ttu-id="9be73-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="9be73-120">Remarks</span></span>

<span data-ttu-id="9be73-121">Se um rótulo não for especificado, o nome da propriedade ou do script será exibido.</span><span class="sxs-lookup"><span data-stu-id="9be73-121">If a label is not specified, the name of the property or the script is displayed.</span></span> <span data-ttu-id="9be73-122">Para obter mais informações sobre como usar rótulos em um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="9be73-122">For more information about using labels in a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="9be73-123">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9be73-123">Example</span></span>

<span data-ttu-id="9be73-124">O exemplo a seguir mostra como adicionar um rótulo a uma linha.</span><span class="sxs-lookup"><span data-stu-id="9be73-124">The following example shows how to add a label to a row.</span></span>

```xml
<ListItem>
  <Label>Property1: </Label>
  <PropertyName>DotNetProperty1</PropertyName>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="9be73-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9be73-125">See Also</span></span>

[<span data-ttu-id="9be73-126">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="9be73-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="9be73-127">Elemento ListItem (formato)</span><span class="sxs-lookup"><span data-stu-id="9be73-127">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="9be73-128">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="9be73-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
