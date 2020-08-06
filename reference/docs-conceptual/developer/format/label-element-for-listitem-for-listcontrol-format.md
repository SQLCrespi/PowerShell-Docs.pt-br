---
title: Elemento Label para ListItem para ListControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: ad80cc0478e7567b12d264ab661d843248ba48e1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783629"
---
# <a name="label-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="84e9d-102">Elemento Label para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="84e9d-102">Label Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="84e9d-103">Especifica o rótulo que é exibido à esquerda do valor de propriedade ou script na linha.</span><span class="sxs-lookup"><span data-stu-id="84e9d-103">Specifies the label that is displayed to the left of the property or script value in the row.</span></span>

<span data-ttu-id="84e9d-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl Element (Format) o elemento ListEntries para ListControl (Format) ListEntry Element para ListControl (Format) ListItems para ListEntry para ListControl Element (Format) ListItem elemento para ListItems para o elemento de rótulo ListControl (Format) para ListItem para ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="84e9d-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems for ListEntry for ListControl Element (Format) ListItem Element for ListItems for ListControl (Format) Label Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="84e9d-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="84e9d-105">Syntax</span></span>

```xml
<Label>Label for displayed value</Label>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="84e9d-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="84e9d-106">Attributes and Elements</span></span>

<span data-ttu-id="84e9d-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `Label` elemento.</span><span class="sxs-lookup"><span data-stu-id="84e9d-107">The following sections describe the attributes, child elements, and the parent element of the `Label` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="84e9d-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="84e9d-108">Attributes</span></span>

<span data-ttu-id="84e9d-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="84e9d-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="84e9d-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="84e9d-110">Child Elements</span></span>

<span data-ttu-id="84e9d-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="84e9d-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="84e9d-112">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="84e9d-112">Parent Elements</span></span>

|<span data-ttu-id="84e9d-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="84e9d-113">Element</span></span>|<span data-ttu-id="84e9d-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="84e9d-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="84e9d-115">Elemento ListItem para ListItems para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="84e9d-115">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="84e9d-116">Define a propriedade ou o script cujo valor é exibido em uma linha da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="84e9d-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="84e9d-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="84e9d-117">Text Value</span></span>

<span data-ttu-id="84e9d-118">Especifique o rótulo a ser exibido à esquerda do valor da propriedade ou do script.</span><span class="sxs-lookup"><span data-stu-id="84e9d-118">Specify the label to be display to the left of the property or script value.</span></span>

## <a name="remarks"></a><span data-ttu-id="84e9d-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="84e9d-119">Remarks</span></span>

<span data-ttu-id="84e9d-120">Se um rótulo não for especificado, o nome da propriedade ou do script será exibido.</span><span class="sxs-lookup"><span data-stu-id="84e9d-120">If a label is not specified, the name of the property or the script is displayed.</span></span> <span data-ttu-id="84e9d-121">Para obter mais informações sobre como usar rótulos em um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="84e9d-121">For more information about using labels in a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="84e9d-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="84e9d-122">Example</span></span>

<span data-ttu-id="84e9d-123">O exemplo a seguir mostra como adicionar um rótulo a uma linha.</span><span class="sxs-lookup"><span data-stu-id="84e9d-123">The following example shows how to add a label to a row.</span></span>

```xml
<ListItem>
  <Label>Property1: </Label>
  <PropertyName>DotNetProperty1</PropertyName>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="84e9d-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="84e9d-124">See Also</span></span>

[<span data-ttu-id="84e9d-125">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="84e9d-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="84e9d-126">Elemento ListItem (formato)</span><span class="sxs-lookup"><span data-stu-id="84e9d-126">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="84e9d-127">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="84e9d-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
