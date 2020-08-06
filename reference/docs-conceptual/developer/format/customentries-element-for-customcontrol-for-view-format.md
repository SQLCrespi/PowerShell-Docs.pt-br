---
title: Elemento CustomEntries para CustomControl para exibição (formato) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c89eb25f6922a92e2c18298d0128c4c2ca93df3d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785958"
---
# <a name="customentries-element-for-customcontrol-for-view-format"></a><span data-ttu-id="0c09d-102">Elemento CustomEntries para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="0c09d-102">CustomEntries Element for CustomControl for View (Format)</span></span>

<span data-ttu-id="0c09d-103">Fornece as definições do modo de exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="0c09d-103">Provides the definitions of the custom control view.</span></span> <span data-ttu-id="0c09d-104">A exibição de controle personalizado deve especificar uma ou mais definições.</span><span class="sxs-lookup"><span data-stu-id="0c09d-104">The custom control view must specify one or more definitions.</span></span>

<span data-ttu-id="0c09d-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento CustomControl Element (Format) CustomEntries elemento para CustomControl para View (Format)</span><span class="sxs-lookup"><span data-stu-id="0c09d-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0c09d-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0c09d-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0c09d-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="0c09d-107">Attributes and Elements</span></span>

<span data-ttu-id="0c09d-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomControlEntries` elemento.</span><span class="sxs-lookup"><span data-stu-id="0c09d-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlEntries` element.</span></span> <span data-ttu-id="0c09d-109">Você deve especificar um ou mais elementos filho.</span><span class="sxs-lookup"><span data-stu-id="0c09d-109">You must specify one or more child elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="0c09d-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="0c09d-110">Attributes</span></span>

<span data-ttu-id="0c09d-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="0c09d-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0c09d-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="0c09d-112">Child Elements</span></span>

|<span data-ttu-id="0c09d-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="0c09d-113">Element</span></span>|<span data-ttu-id="0c09d-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="0c09d-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0c09d-115">Elemento CustomEntry para CustomEntries para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="0c09d-115">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="0c09d-116">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="0c09d-116">Required element.</span></span><br /><br /> <span data-ttu-id="0c09d-117">Fornece uma definição da exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="0c09d-117">Provides a definition of the custom control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="0c09d-118">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="0c09d-118">Parent Elements</span></span>

|<span data-ttu-id="0c09d-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="0c09d-119">Element</span></span>|<span data-ttu-id="0c09d-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="0c09d-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0c09d-121">Elemento CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="0c09d-121">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)|<span data-ttu-id="0c09d-122">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="0c09d-122">Required element.</span></span><br /><br /> <span data-ttu-id="0c09d-123">Define um formato de controle personalizado para a exibição.</span><span class="sxs-lookup"><span data-stu-id="0c09d-123">Defines a custom control format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0c09d-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="0c09d-124">Remarks</span></span>

<span data-ttu-id="0c09d-125">Na maioria dos casos, um controle tem apenas uma definição, que é definida em um único `CustomEntry` elemento.</span><span class="sxs-lookup"><span data-stu-id="0c09d-125">In most cases, a control has only one definition, which is defined in a single `CustomEntry` element.</span></span> <span data-ttu-id="0c09d-126">No entanto, é possível ter várias definições se você quiser usar o mesmo controle para exibir diferentes objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="0c09d-126">However it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="0c09d-127">Nesses casos, você pode definir um `CustomEntry` elemento para cada objeto ou conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="0c09d-127">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="0c09d-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0c09d-128">See Also</span></span>

[<span data-ttu-id="0c09d-129">Elemento CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="0c09d-129">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)

[<span data-ttu-id="0c09d-130">Elemento CustomEntry para CustomEntries para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="0c09d-130">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="0c09d-131">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c09d-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
