---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento Configuration (formato)
description: Elemento Configuration (formato)
ms.openlocfilehash: 0524736d40dd7a7acb0b6fb61d1438b75672c240
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655693"
---
# <a name="configuration-element-format"></a><span data-ttu-id="236a7-103">Elemento Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="236a7-103">Configuration Element (Format)</span></span>

<span data-ttu-id="236a7-104">Representa o elemento de nível superior de um arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="236a7-104">Represents the top-level element of a formatting file.</span></span>

<span data-ttu-id="236a7-105">Elemento de configuração</span><span class="sxs-lookup"><span data-stu-id="236a7-105">Configuration Element</span></span>

## <a name="syntax"></a><span data-ttu-id="236a7-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="236a7-106">Syntax</span></span>

```xml
<Configuration>
  <DefaultSettings>...</DefaultSettings>
  <SelectionSets>...</SelectionSets>
  <Controls>...</Controls>
  <ViewDefinitions>...</ViewDefinitions>
</Configuration>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="236a7-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="236a7-107">Attributes and Elements</span></span>

<span data-ttu-id="236a7-108">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `Configuration` elemento.</span><span class="sxs-lookup"><span data-stu-id="236a7-108">The following sections describe the attributes, child elements, and the parent element of the `Configuration` element.</span></span> <span data-ttu-id="236a7-109">Esse elemento deve ser o elemento raiz para cada arquivo de formatação, e esse elemento deve conter pelo menos um elemento filho.</span><span class="sxs-lookup"><span data-stu-id="236a7-109">This element must be the root element for each formatting file, and this element must contain at least one child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="236a7-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="236a7-110">Attributes</span></span>

<span data-ttu-id="236a7-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="236a7-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="236a7-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="236a7-112">Child Elements</span></span>

|<span data-ttu-id="236a7-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="236a7-113">Element</span></span>|<span data-ttu-id="236a7-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="236a7-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="236a7-115">Elemento Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="236a7-115">Controls Element for Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)|<span data-ttu-id="236a7-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="236a7-116">Optional element.</span></span><br /><br /> <span data-ttu-id="236a7-117">Define os controles comuns que podem ser usados por todas as exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="236a7-117">Defines the common controls that can be used by all views of the formatting file.</span></span>|
|[<span data-ttu-id="236a7-118">Elemento DefaultSettings (formato)</span><span class="sxs-lookup"><span data-stu-id="236a7-118">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="236a7-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="236a7-119">Optional element.</span></span><br /><br /> <span data-ttu-id="236a7-120">Define as configurações comuns que se aplicam a todas as exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="236a7-120">Defines common settings that apply to all the views of the formatting file.</span></span>|
|[<span data-ttu-id="236a7-121">Formato do elemento SelectionSets</span><span class="sxs-lookup"><span data-stu-id="236a7-121">SelectionSets Element Format</span></span>](./selectionsets-element-format.md)|<span data-ttu-id="236a7-122">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="236a7-122">Optional element.</span></span><br /><br /> <span data-ttu-id="236a7-123">Define os conjuntos comuns de objetos .NET que podem ser usados por todas as exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="236a7-123">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span>|
|[<span data-ttu-id="236a7-124">Elemento ViewDefinitions (formato)</span><span class="sxs-lookup"><span data-stu-id="236a7-124">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="236a7-125">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="236a7-125">Optional element.</span></span><br /><br /> <span data-ttu-id="236a7-126">Define as exibições usadas para exibir objetos.</span><span class="sxs-lookup"><span data-stu-id="236a7-126">Defines the views used to display objects.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="236a7-127">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="236a7-127">Parent Elements</span></span>

<span data-ttu-id="236a7-128">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="236a7-128">None.</span></span>

## <a name="remarks"></a><span data-ttu-id="236a7-129">Comentários</span><span class="sxs-lookup"><span data-stu-id="236a7-129">Remarks</span></span>

<span data-ttu-id="236a7-130">Arquivos de formatação definem como os objetos são exibidos.</span><span class="sxs-lookup"><span data-stu-id="236a7-130">Formatting files define how objects are displayed.</span></span> <span data-ttu-id="236a7-131">Na maioria dos casos, esse elemento raiz contém um elemento [ViewDefinitions](./viewdefinitions-element-format.md) que define a tabela, a lista e as exibições amplas do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="236a7-131">In most cases, this root element contains a [ViewDefinitions](./viewdefinitions-element-format.md) element that defines the table, list, and wide views of the formatting file.</span></span> <span data-ttu-id="236a7-132">Além das definições de exibição, o arquivo de formatação pode definir conjuntos de seleção, configurações e controles comuns que podem ser usados por essas exibições.</span><span class="sxs-lookup"><span data-stu-id="236a7-132">In addition to the view definitions, the formatting file can define common selection sets, settings, and controls that those views can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="236a7-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="236a7-133">See Also</span></span>

[<span data-ttu-id="236a7-134">Elemento Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="236a7-134">Controls Element for Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)

[<span data-ttu-id="236a7-135">Elemento DefaultSettings (formato)</span><span class="sxs-lookup"><span data-stu-id="236a7-135">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)

[<span data-ttu-id="236a7-136">Elemento SelectionSets (formato)</span><span class="sxs-lookup"><span data-stu-id="236a7-136">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="236a7-137">Elemento ViewDefinitions (formato)</span><span class="sxs-lookup"><span data-stu-id="236a7-137">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="236a7-138">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="236a7-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
