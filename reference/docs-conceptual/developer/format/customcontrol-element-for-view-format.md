---
title: Elemento CustomControl para exibição (formato) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 660e8fd6531862790a2af7ab27a82e073c230693
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786043"
---
# <a name="customcontrol-element-for-view-format"></a><span data-ttu-id="c0166-102">Elemento CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="c0166-102">CustomControl Element for View (Format)</span></span>

<span data-ttu-id="c0166-103">Define um formato de controle personalizado para a exibição.</span><span class="sxs-lookup"><span data-stu-id="c0166-103">Defines a custom control format for the view.</span></span>

<span data-ttu-id="c0166-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento CustomControl (Format)</span><span class="sxs-lookup"><span data-stu-id="c0166-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c0166-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c0166-105">Syntax</span></span>

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
</CustomControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c0166-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="c0166-106">Attributes and Elements</span></span>

<span data-ttu-id="c0166-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomControl` elemento.</span><span class="sxs-lookup"><span data-stu-id="c0166-107">The following sections describe attributes, child elements, and the parent element of the `CustomControl` element.</span></span> <span data-ttu-id="c0166-108">Você deve especificar um elemento filho.</span><span class="sxs-lookup"><span data-stu-id="c0166-108">You must specify one child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c0166-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="c0166-109">Attributes</span></span>

<span data-ttu-id="c0166-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="c0166-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c0166-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="c0166-111">Child Elements</span></span>

|<span data-ttu-id="c0166-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="c0166-112">Element</span></span>|<span data-ttu-id="c0166-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="c0166-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c0166-114">Elemento CustomEntries para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="c0166-114">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="c0166-115">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="c0166-115">Required element.</span></span><br /><br /> <span data-ttu-id="c0166-116">Fornece as definições do modo de exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="c0166-116">Provides the definitions of the custom control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="c0166-117">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="c0166-117">Parent Elements</span></span>

|<span data-ttu-id="c0166-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="c0166-118">Element</span></span>|<span data-ttu-id="c0166-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="c0166-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c0166-120">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="c0166-120">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="c0166-121">Define uma exibição usada para exibir um ou mais objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="c0166-121">Defines a view that is used to display one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c0166-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="c0166-122">Remarks</span></span>

<span data-ttu-id="c0166-123">Na maioria dos casos, apenas uma definição é necessária para cada exibição de controle, mas é possível fornecer várias definições se você quiser usar a mesma exibição para exibir objetos .NET diferentes.</span><span class="sxs-lookup"><span data-stu-id="c0166-123">In most cases, only one definition is required for each control view, but it is possible to provide multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="c0166-124">Nesses casos, você pode fornecer uma definição separada para cada objeto ou conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="c0166-124">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="c0166-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c0166-125">See Also</span></span>

[<span data-ttu-id="c0166-126">Elemento CustomEntries para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="c0166-126">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)

[<span data-ttu-id="c0166-127">Elemento View (formato)</span><span class="sxs-lookup"><span data-stu-id="c0166-127">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="c0166-128">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c0166-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
