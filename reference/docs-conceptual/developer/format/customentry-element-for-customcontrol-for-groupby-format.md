---
title: Elemento CustomEntry para CustomControl para GroupBy (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 4df8e5b96868b3814c6d84fa329950bb5345ef6e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785907"
---
# <a name="customentry-element-for-customcontrol-for-groupby-format"></a><span data-ttu-id="9f929-102">Elemento CustomEntry para CustomControl para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="9f929-102">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>

<span data-ttu-id="9f929-103">Fornece uma definição do controle.</span><span class="sxs-lookup"><span data-stu-id="9f929-103">Provides a definition of the control.</span></span> <span data-ttu-id="9f929-104">Esse elemento é usado ao definir como um novo grupo de objetos é exibido.</span><span class="sxs-lookup"><span data-stu-id="9f929-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="9f929-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para View (Format) CustomControl Element para GroupBy (Format) CustomEntries Element for CustomControl para GroupBy (Format) CustomEntry Element para CustomControl para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="9f929-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9f929-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9f929-106">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9f929-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="9f929-107">Attributes and Elements</span></span>

<span data-ttu-id="9f929-108">As seções a seguir descrevem atributos, elementos filho e os elementos pai do `CustomEntry` elemento.</span><span class="sxs-lookup"><span data-stu-id="9f929-108">The following sections describe attributes, child elements, and the parent elements of the `CustomEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9f929-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="9f929-109">Attributes</span></span>

<span data-ttu-id="9f929-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="9f929-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9f929-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="9f929-111">Child Elements</span></span>

|<span data-ttu-id="9f929-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="9f929-112">Element</span></span>|<span data-ttu-id="9f929-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="9f929-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9f929-114">Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="9f929-114">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="9f929-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="9f929-115">Optional element.</span></span><br /><br /> <span data-ttu-id="9f929-116">Define os tipos .NET que usam essa definição de controle ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="9f929-116">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="9f929-117">Elemento CustomItem para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="9f929-117">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="9f929-118">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="9f929-118">Required element.</span></span><br /><br /> <span data-ttu-id="9f929-119">Define como o controle exibe os dados.</span><span class="sxs-lookup"><span data-stu-id="9f929-119">Defines how the control displays the data.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9f929-120">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="9f929-120">Parent Elements</span></span>

|<span data-ttu-id="9f929-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="9f929-121">Element</span></span>|<span data-ttu-id="9f929-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="9f929-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9f929-123">Elemento CustomEntries para CustomControl para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="9f929-123">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>](./customentries-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="9f929-124">Fornece as definições para o controle.</span><span class="sxs-lookup"><span data-stu-id="9f929-124">Provides the definitions for the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9f929-125">Comentários</span><span class="sxs-lookup"><span data-stu-id="9f929-125">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="9f929-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9f929-126">See Also</span></span>

[<span data-ttu-id="9f929-127">Elemento EntrySelectedBy para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="9f929-127">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="9f929-128">Elemento CustomItem para CustomEntry para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="9f929-128">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="9f929-129">Elemento CustomEntries para CustomControl para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="9f929-129">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>](./customentries-element-for-customcontrol-for-groupby-format.md)

[<span data-ttu-id="9f929-130">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="9f929-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
