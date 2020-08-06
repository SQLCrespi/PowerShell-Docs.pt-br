---
title: Elemento PropertyName de ListItem para ListControl (formato) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 9ee466d7f73e53b129f8d46f49a21549683bb32c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780824"
---
# <a name="propertyname-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="46c90-102">Elemento PropertyName para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="46c90-102">PropertyName Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="46c90-103">Especifica a propriedade .NET cujo valor é exibido na lista.</span><span class="sxs-lookup"><span data-stu-id="46c90-103">Specifies the .NET property whose value is displayed in the list.</span></span>

<span data-ttu-id="46c90-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) ListControl elemento (Format) ListEntries Element (Format) o elemento ListEntry Element (Format) ListItems Element (Format) ListItem Element (Format) NomeDaPropriedade Element for ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="46c90-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) ListItems Element (Format) ListItem Element (Format) PropertyName Element for ListItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="46c90-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="46c90-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="46c90-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="46c90-106">Attributes and Elements</span></span>

<span data-ttu-id="46c90-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `PropertyName` elemento.</span><span class="sxs-lookup"><span data-stu-id="46c90-107">The following sections describe the attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="46c90-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="46c90-108">Attributes</span></span>

<span data-ttu-id="46c90-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="46c90-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="46c90-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="46c90-110">Child Elements</span></span>

<span data-ttu-id="46c90-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="46c90-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="46c90-112">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="46c90-112">Parent Elements</span></span>

|<span data-ttu-id="46c90-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="46c90-113">Element</span></span>|<span data-ttu-id="46c90-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="46c90-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="46c90-115">Elemento ListItem (formato)</span><span class="sxs-lookup"><span data-stu-id="46c90-115">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="46c90-116">Define a propriedade ou o script cujo valor é exibido na linha da exibição de lista.</span><span class="sxs-lookup"><span data-stu-id="46c90-116">Defines the property or script whose value is displayed in the row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="46c90-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="46c90-117">Text Value</span></span>

<span data-ttu-id="46c90-118">Especifique o nome da propriedade cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="46c90-118">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="46c90-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="46c90-119">Remarks</span></span>

<span data-ttu-id="46c90-120">Quando esse elemento é especificado, você não pode especificar o elemento [scriptblock](./scriptblock-element-for-listitem-for-listcontrol-format.md) .</span><span class="sxs-lookup"><span data-stu-id="46c90-120">When this element is specified, you cannot specify the [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element.</span></span>

<span data-ttu-id="46c90-121">Além de exibir o valor da propriedade, você também pode especificar um rótulo para o valor ou uma cadeia de caracteres de formato que possa ser usada para alterar a exibição do valor.</span><span class="sxs-lookup"><span data-stu-id="46c90-121">In addition to displaying the property value, you can also specify a label for the value or a format string that can be used to change the display of the value.</span></span> <span data-ttu-id="46c90-122">Para obter mais informações sobre como especificar dados em um modo de exibição de lista, consulte [criando uma exibição de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="46c90-122">For more information about specifying data in a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="46c90-123">Exemplo</span><span class="sxs-lookup"><span data-stu-id="46c90-123">Example</span></span>

<span data-ttu-id="46c90-124">O exemplo a seguir mostra como especificar o rótulo e a propriedade cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="46c90-124">The following example shows how to specify the label and property whose value is displayed.</span></span>

```xml
ListItem>
  <Label>NameOfProperty</Label>
  <PropertyName>.NetTypeProperty</PropertyName>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="46c90-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="46c90-125">See Also</span></span>

[<span data-ttu-id="46c90-126">Elemento ScriptBlock para ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="46c90-126">ScriptBlock Element for ListItem for ListControl (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="46c90-127">Criar uma exibição de lista</span><span class="sxs-lookup"><span data-stu-id="46c90-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="46c90-128">Elemento ListItem para ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="46c90-128">ListItem Element for ListControl(Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="46c90-129">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="46c90-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
