---
title: Elemento PropertyName para WideItem para WideControl (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d91d0e6-bf18-4587-b651-db66849e5df5
caps.latest.revision: 6
ms.openlocfilehash: 326880834cd82ab826aadc409cd7a8f21cd36824
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064638"
---
# <a name="propertyname-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="f60f3-102">Elemento PropertyName para WideItem para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="f60f3-102">PropertyName Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="f60f3-103">Especifica a propriedade do objeto cujo valor é exibido no modo de exibição amplo.</span><span class="sxs-lookup"><span data-stu-id="f60f3-103">Specifies the property of the object whose value is displayed in the wide view.</span></span>

<span data-ttu-id="f60f3-104">Elemento (formato) elemento ViewDefinitions (formato) modo de exibição (formato) do elemento elemento WideControl (formato) elemento WideEntries (formato) elemento WideEntry (formato) elemento WideItem (formato) PropertyName elemento de configuração para WideItem (formato)</span><span class="sxs-lookup"><span data-stu-id="f60f3-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format) PropertyName Element for WideItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f60f3-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f60f3-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f60f3-106">Elementos e atributos</span><span class="sxs-lookup"><span data-stu-id="f60f3-106">Attributes and Elements</span></span>

<span data-ttu-id="f60f3-107">As seções a seguir descrevem os atributos, elementos filho e o elemento pai do `PropertyName` elemento.</span><span class="sxs-lookup"><span data-stu-id="f60f3-107">The following sections describe the attributes, child elements, and parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f60f3-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="f60f3-108">Attributes</span></span>

<span data-ttu-id="f60f3-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="f60f3-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f60f3-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="f60f3-110">Child Elements</span></span>

<span data-ttu-id="f60f3-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="f60f3-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f60f3-112">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="f60f3-112">Parent Elements</span></span>

|<span data-ttu-id="f60f3-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="f60f3-113">Element</span></span>|<span data-ttu-id="f60f3-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="f60f3-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f60f3-115">Elemento WideItem (formato)</span><span class="sxs-lookup"><span data-stu-id="f60f3-115">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="f60f3-116">Define a propriedade ou cujo valor é exibido no modo de exibição amplo de script.</span><span class="sxs-lookup"><span data-stu-id="f60f3-116">Defines the property or script whose value is displayed in the wide view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f60f3-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="f60f3-117">Text Value</span></span>

<span data-ttu-id="f60f3-118">Especifique o nome da propriedade cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="f60f3-118">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="f60f3-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="f60f3-119">Remarks</span></span>

<span data-ttu-id="f60f3-120">Para obter mais informações sobre os componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="f60f3-120">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="f60f3-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f60f3-121">Example</span></span>

<span data-ttu-id="f60f3-122">Este exemplo mostra uma exibição ampla que exibe o valor da propriedade ProcessName do [Diagnostics](/dotnet/api/System.Diagnostics.Process) objeto.</span><span class="sxs-lookup"><span data-stu-id="f60f3-122">This example shows a wide view that displays the value of the ProcessName property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f60f3-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f60f3-123">See Also</span></span>

[<span data-ttu-id="f60f3-124">Elemento WideItem (formato)</span><span class="sxs-lookup"><span data-stu-id="f60f3-124">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="f60f3-125">Criando uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="f60f3-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="f60f3-126">Gravar um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="f60f3-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
