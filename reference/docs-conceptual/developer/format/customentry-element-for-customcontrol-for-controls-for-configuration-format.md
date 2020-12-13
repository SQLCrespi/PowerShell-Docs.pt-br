---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento CustomEntry para CustomControl para Controls para Configuration (formato)
description: Elemento CustomEntry para CustomControl para Controls para Configuration (formato)
ms.openlocfilehash: 3967be86a1d6c12c7215ef19d50bac9fafd5ad6d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648289"
---
# <a name="customentry-element-for-customcontrol-for-controls-for-configuration-format"></a><span data-ttu-id="f1526-103">Elemento CustomEntry para CustomControl para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="f1526-103">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>

<span data-ttu-id="f1526-104">Fornece uma definição do controle comum.</span><span class="sxs-lookup"><span data-stu-id="f1526-104">Provides a definition of the common control.</span></span> <span data-ttu-id="f1526-105">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="f1526-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="f1526-106">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para o elemento de configuração (Format) CustomEntry para CustomControl para controles para a configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="f1526-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f1526-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f1526-107">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="f1526-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="f1526-108">Attributes and Elements</span></span>

<span data-ttu-id="f1526-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomEntry` elemento.</span><span class="sxs-lookup"><span data-stu-id="f1526-109">The following sections describe attributes, child elements, and the parent element of the `CustomEntry` element.</span></span> <span data-ttu-id="f1526-110">Você deve especificar os itens exibidos pela definição.</span><span class="sxs-lookup"><span data-stu-id="f1526-110">You must specify the items displayed by the definition.</span></span>

### <a name="attributes"></a><span data-ttu-id="f1526-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="f1526-111">Attributes</span></span>

<span data-ttu-id="f1526-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="f1526-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f1526-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="f1526-113">Child Elements</span></span>

|<span data-ttu-id="f1526-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="f1526-114">Element</span></span>|<span data-ttu-id="f1526-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="f1526-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f1526-116">Elemento EntrySelectedBy para CustomEntry para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="f1526-116">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="f1526-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="f1526-117">Optional element.</span></span><br /><br /> <span data-ttu-id="f1526-118">Define os tipos .NET que usam a definição do controle comum ou a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="f1526-118">Defines the .NET types that use the definition of the common control or the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="f1526-119">Elemento CustomItem para CustomEntry para controles de configuração</span><span class="sxs-lookup"><span data-stu-id="f1526-119">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="f1526-120">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="f1526-120">Required element.</span></span><br /><br /> <span data-ttu-id="f1526-121">Define quais dados são exibidos pelo controle e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="f1526-121">Defines what data is displayed by the control and how it is displayed.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f1526-122">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="f1526-122">Parent Elements</span></span>

|<span data-ttu-id="f1526-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="f1526-123">Element</span></span>|<span data-ttu-id="f1526-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="f1526-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f1526-125">Elemento CustomEntries para CustomControl para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="f1526-125">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="f1526-126">Fornece as definições do controle comum.</span><span class="sxs-lookup"><span data-stu-id="f1526-126">Provides the definitions of the common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f1526-127">Comentários</span><span class="sxs-lookup"><span data-stu-id="f1526-127">Remarks</span></span>

<span data-ttu-id="f1526-128">Na maioria dos casos, apenas uma definição é necessária para cada controle personalizado comum, mas é possível ter várias definições se você quiser usar o mesmo controle para exibir diferentes objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="f1526-128">In most cases, only one definition is required for each common custom control, but it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="f1526-129">Nesses casos, você pode fornecer uma definição separada para cada objeto ou conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="f1526-129">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1526-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f1526-130">See Also</span></span>

[<span data-ttu-id="f1526-131">Elemento CustomEntries para CustomControl para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="f1526-131">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="f1526-132">Elemento CustomItem para CustomEntry para controles de configuração</span><span class="sxs-lookup"><span data-stu-id="f1526-132">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="f1526-133">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1526-133">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
