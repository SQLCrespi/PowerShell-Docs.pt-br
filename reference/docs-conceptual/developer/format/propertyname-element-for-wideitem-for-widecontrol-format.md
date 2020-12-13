---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento PropertyName para WideItem para WideControl (formato)
description: Elemento PropertyName para WideItem para WideControl (formato)
ms.openlocfilehash: 1d4d5eaf7708dfbd7997122fac156a36487538ea
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665610"
---
# <a name="propertyname-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="1e3b4-103">Elemento PropertyName para WideItem para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="1e3b4-103">PropertyName Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="1e3b4-104">Especifica a propriedade do objeto cujo valor é exibido na exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="1e3b4-104">Specifies the property of the object whose value is displayed in the wide view.</span></span>

<span data-ttu-id="1e3b4-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) WideControl elemento (Format) WideEntries Element (Format) WideEntry elemento (Format) elemento WideItem Element (Format) NomeDaPropriedade Element for WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="1e3b4-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format) PropertyName Element for WideItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1e3b4-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1e3b4-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1e3b4-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="1e3b4-107">Attributes and Elements</span></span>

<span data-ttu-id="1e3b4-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `PropertyName` elemento.</span><span class="sxs-lookup"><span data-stu-id="1e3b4-108">The following sections describe the attributes, child elements, and parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1e3b4-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="1e3b4-109">Attributes</span></span>

<span data-ttu-id="1e3b4-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="1e3b4-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1e3b4-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="1e3b4-111">Child Elements</span></span>

<span data-ttu-id="1e3b4-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="1e3b4-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1e3b4-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="1e3b4-113">Parent Elements</span></span>

|<span data-ttu-id="1e3b4-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="1e3b4-114">Element</span></span>|<span data-ttu-id="1e3b4-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="1e3b4-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1e3b4-116">Elemento WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="1e3b4-116">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="1e3b4-117">Define a propriedade ou o script cujo valor é exibido na exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="1e3b4-117">Defines the property or script whose value is displayed in the wide view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1e3b4-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="1e3b4-118">Text Value</span></span>

<span data-ttu-id="1e3b4-119">Especifique o nome da propriedade cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="1e3b4-119">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="1e3b4-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="1e3b4-120">Remarks</span></span>

<span data-ttu-id="1e3b4-121">Para obter mais informações sobre os componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="1e3b4-121">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="1e3b4-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="1e3b4-122">Example</span></span>

<span data-ttu-id="1e3b4-123">Este exemplo mostra uma exibição ampla que exibe o valor da propriedade ProcessName do objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="1e3b4-123">This example shows a wide view that displays the value of the ProcessName property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>
    <WideEntries>
      <WideEntry>
        <WideItem>
          <PropertyName>ProcessName</PropertyName>
        </WideItem>
      </WideEntry>
    </WideEntries>
  </WideControl>
</View>

```

## <a name="see-also"></a><span data-ttu-id="1e3b4-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1e3b4-124">See Also</span></span>

[<span data-ttu-id="1e3b4-125">Elemento WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="1e3b4-125">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="1e3b4-126">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="1e3b4-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="1e3b4-127">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e3b4-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
