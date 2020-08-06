---
title: Elemento PropertyName para WideItem para WideControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 7728f960a67faa99eaafb4a4934674e119b8af27
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780467"
---
# <a name="propertyname-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="1f537-102">Elemento PropertyName para WideItem para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="1f537-102">PropertyName Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="1f537-103">Especifica a propriedade do objeto cujo valor é exibido na exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="1f537-103">Specifies the property of the object whose value is displayed in the wide view.</span></span>

<span data-ttu-id="1f537-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) WideControl elemento (Format) WideEntries Element (Format) WideEntry elemento (Format) elemento WideItem Element (Format) NomeDaPropriedade Element for WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="1f537-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format) PropertyName Element for WideItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1f537-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1f537-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1f537-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="1f537-106">Attributes and Elements</span></span>

<span data-ttu-id="1f537-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `PropertyName` elemento.</span><span class="sxs-lookup"><span data-stu-id="1f537-107">The following sections describe the attributes, child elements, and parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1f537-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="1f537-108">Attributes</span></span>

<span data-ttu-id="1f537-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="1f537-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1f537-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="1f537-110">Child Elements</span></span>

<span data-ttu-id="1f537-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="1f537-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1f537-112">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="1f537-112">Parent Elements</span></span>

|<span data-ttu-id="1f537-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="1f537-113">Element</span></span>|<span data-ttu-id="1f537-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="1f537-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1f537-115">Elemento WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="1f537-115">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="1f537-116">Define a propriedade ou o script cujo valor é exibido na exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="1f537-116">Defines the property or script whose value is displayed in the wide view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1f537-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="1f537-117">Text Value</span></span>

<span data-ttu-id="1f537-118">Especifique o nome da propriedade cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="1f537-118">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="1f537-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="1f537-119">Remarks</span></span>

<span data-ttu-id="1f537-120">Para obter mais informações sobre os componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="1f537-120">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="1f537-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="1f537-121">Example</span></span>

<span data-ttu-id="1f537-122">Este exemplo mostra uma exibição ampla que exibe o valor da propriedade ProcessName do objeto [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="1f537-122">This example shows a wide view that displays the value of the ProcessName property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="1f537-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1f537-123">See Also</span></span>

[<span data-ttu-id="1f537-124">Elemento WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="1f537-124">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="1f537-125">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="1f537-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="1f537-126">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f537-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
