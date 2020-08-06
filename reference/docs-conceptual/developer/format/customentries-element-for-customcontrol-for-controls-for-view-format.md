---
title: Elemento CustomEntries para CustomControl para controles para View (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: a52bd2368044c34a0b73da331785d55597e30260
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783697"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-view-format"></a><span data-ttu-id="e8c73-102">Elemento CustomEntries para CustomControl para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="e8c73-102">CustomEntries Element for CustomControl for Controls for View (Format)</span></span>

<span data-ttu-id="e8c73-103">Fornece as definições para o controle.</span><span class="sxs-lookup"><span data-stu-id="e8c73-103">Provides the definitions for the control.</span></span> <span data-ttu-id="e8c73-104">Esse elemento é usado ao definir controles que podem ser usados por uma exibição.</span><span class="sxs-lookup"><span data-stu-id="e8c73-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="e8c73-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elementos de controle (Format) elemento Control para controles para o elemento View (Format) CustomControl para Control para controles para View (Format) CustomEntries Element for CustomControl para Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e8c73-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e8c73-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e8c73-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e8c73-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="e8c73-107">Attributes and Elements</span></span>

<span data-ttu-id="e8c73-108">As seções a seguir descrevem atributos, elementos filho e elementos pai do `CustomEntries` elemento.</span><span class="sxs-lookup"><span data-stu-id="e8c73-108">The following sections describe attributes, child elements, and parent elements of the `CustomEntries` element.</span></span> <span data-ttu-id="e8c73-109">Não há nenhum limite máximo para o número de elementos filho que podem ser especificados.</span><span class="sxs-lookup"><span data-stu-id="e8c73-109">There is no maximum limit to the number of child elements that can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="e8c73-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="e8c73-110">Attributes</span></span>

<span data-ttu-id="e8c73-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="e8c73-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e8c73-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="e8c73-112">Child Elements</span></span>

|<span data-ttu-id="e8c73-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="e8c73-113">Element</span></span>|<span data-ttu-id="e8c73-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="e8c73-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e8c73-115">Elemento CustomEntry para CustomEntries para Controls para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="e8c73-115">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="e8c73-116">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="e8c73-116">Required element.</span></span><br /><br /> <span data-ttu-id="e8c73-117">Fornece uma definição do controle.</span><span class="sxs-lookup"><span data-stu-id="e8c73-117">Provides a definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e8c73-118">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="e8c73-118">Parent Elements</span></span>

|<span data-ttu-id="e8c73-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="e8c73-119">Element</span></span>|<span data-ttu-id="e8c73-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="e8c73-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e8c73-121">Elemento CustomControl para Control para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="e8c73-121">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="e8c73-122">Define o controle usado pela exibição.</span><span class="sxs-lookup"><span data-stu-id="e8c73-122">Defines the control used by the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e8c73-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="e8c73-123">Remarks</span></span>

<span data-ttu-id="e8c73-124">Na maioria dos casos, um controle tem apenas uma definição, que é especificada em um único `CustomEntry` elemento.</span><span class="sxs-lookup"><span data-stu-id="e8c73-124">In most cases, a control has only one definition, which is specified in a single `CustomEntry` element.</span></span> <span data-ttu-id="e8c73-125">No entanto, é possível fornecer várias definições se você quiser usar o mesmo controle para exibir diferentes objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="e8c73-125">However, it is possible to provide multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="e8c73-126">Nesses casos, você pode definir um `CustomEntry` elemento para cada objeto ou conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="e8c73-126">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8c73-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e8c73-127">See Also</span></span>

[<span data-ttu-id="e8c73-128">Elemento CustomEntry para CustomEntries para Controls para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="e8c73-128">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="e8c73-129">Elemento CustomControl para Control para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="e8c73-129">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="e8c73-130">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8c73-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
