---
title: Elemento PropertyName para WideItem para WideControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d91d0e6-bf18-4587-b651-db66849e5df5
caps.latest.revision: 6
ms.openlocfilehash: 326880834cd82ab826aadc409cd7a8f21cd36824
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364935"
---
# <a name="propertyname-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="86a27-102">Elemento PropertyName para WideItem para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="86a27-102">PropertyName Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="86a27-103">Especifica a propriedade do objeto cujo valor é exibido na exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="86a27-103">Specifies the property of the object whose value is displayed in the wide view.</span></span>

<span data-ttu-id="86a27-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) WideControl elemento (Format) WideEntries Element (Format) WideEntry elemento (Format) elemento WideItem Element (Format) NomeDaPropriedade Element for WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="86a27-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format) PropertyName Element for WideItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="86a27-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="86a27-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="86a27-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="86a27-106">Attributes and Elements</span></span>

<span data-ttu-id="86a27-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `PropertyName`.</span><span class="sxs-lookup"><span data-stu-id="86a27-107">The following sections describe the attributes, child elements, and parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="86a27-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="86a27-108">Attributes</span></span>

<span data-ttu-id="86a27-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="86a27-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="86a27-110">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="86a27-110">Child Elements</span></span>

<span data-ttu-id="86a27-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="86a27-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="86a27-112">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="86a27-112">Parent Elements</span></span>

|<span data-ttu-id="86a27-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="86a27-113">Element</span></span>|<span data-ttu-id="86a27-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="86a27-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="86a27-115">Elemento WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="86a27-115">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="86a27-116">Define a propriedade ou o script cujo valor é exibido na exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="86a27-116">Defines the property or script whose value is displayed in the wide view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="86a27-117">Valor de Texto</span><span class="sxs-lookup"><span data-stu-id="86a27-117">Text Value</span></span>

<span data-ttu-id="86a27-118">Especifique o nome da propriedade cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="86a27-118">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="86a27-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="86a27-119">Remarks</span></span>

<span data-ttu-id="86a27-120">Para obter mais informações sobre os componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="86a27-120">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="86a27-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="86a27-121">Example</span></span>

<span data-ttu-id="86a27-122">Este exemplo mostra uma exibição ampla que exibe o valor da propriedade ProcessName do objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="86a27-122">This example shows a wide view that displays the value of the ProcessName property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="86a27-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="86a27-123">See Also</span></span>

[<span data-ttu-id="86a27-124">Elemento WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="86a27-124">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="86a27-125">Criando uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="86a27-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="86a27-126">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="86a27-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
