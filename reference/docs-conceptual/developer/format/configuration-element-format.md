---
title: Elemento Configuration (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d46df0cb-50b7-4b81-82ba-37186a7b7a7f
caps.latest.revision: 28
ms.openlocfilehash: 296c63d0c774a0bf56e90dbaa32f2c221d4c3dbd
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363495"
---
# <a name="configuration-element-format"></a><span data-ttu-id="d1f29-102">Elemento Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="d1f29-102">Configuration Element (Format)</span></span>

<span data-ttu-id="d1f29-103">Representa o elemento de nível superior de um arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="d1f29-103">Represents the top-level element of a formatting file.</span></span>

<span data-ttu-id="d1f29-104">Elemento de configuração</span><span class="sxs-lookup"><span data-stu-id="d1f29-104">Configuration Element</span></span>

## <a name="syntax"></a><span data-ttu-id="d1f29-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d1f29-105">Syntax</span></span>

```xml
<Configuration>
  <DefaultSettings>...</DefaultSettings>
  <SelectionSets>...</SelectionSets>
  <Controls>...</Controls>
  <ViewDefinitions>...</ViewDefinitions>
</Configuration>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="d1f29-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="d1f29-106">Attributes and Elements</span></span>

<span data-ttu-id="d1f29-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="d1f29-107">The following sections describe the attributes, child elements, and the parent element of the `Configuration` element.</span></span> <span data-ttu-id="d1f29-108">Esse elemento deve ser o elemento raiz para cada arquivo de formatação, e esse elemento deve conter pelo menos um elemento filho.</span><span class="sxs-lookup"><span data-stu-id="d1f29-108">This element must be the root element for each formatting file, and this element must contain at least one child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d1f29-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="d1f29-109">Attributes</span></span>

<span data-ttu-id="d1f29-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="d1f29-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d1f29-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="d1f29-111">Child Elements</span></span>

|<span data-ttu-id="d1f29-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="d1f29-112">Element</span></span>|<span data-ttu-id="d1f29-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="d1f29-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d1f29-114">Elemento Controls para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="d1f29-114">Controls Element for Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)|<span data-ttu-id="d1f29-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="d1f29-115">Optional element.</span></span><br /><br /> <span data-ttu-id="d1f29-116">Define os controles comuns que podem ser usados por todas as exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="d1f29-116">Defines the common controls that can be used by all views of the formatting file.</span></span>|
|[<span data-ttu-id="d1f29-117">Elemento DefaultSettings (formato)</span><span class="sxs-lookup"><span data-stu-id="d1f29-117">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="d1f29-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="d1f29-118">Optional element.</span></span><br /><br /> <span data-ttu-id="d1f29-119">Define as configurações comuns que se aplicam a todas as exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="d1f29-119">Defines common settings that apply to all the views of the formatting file.</span></span>|
|[<span data-ttu-id="d1f29-120">Formato do elemento SelectionSets</span><span class="sxs-lookup"><span data-stu-id="d1f29-120">SelectionSets Element Format</span></span>](./selectionsets-element-format.md)|<span data-ttu-id="d1f29-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="d1f29-121">Optional element.</span></span><br /><br /> <span data-ttu-id="d1f29-122">Define os conjuntos comuns de objetos .NET que podem ser usados por todas as exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="d1f29-122">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span>|
|[<span data-ttu-id="d1f29-123">Elemento ViewDefinitions (Format)</span><span class="sxs-lookup"><span data-stu-id="d1f29-123">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="d1f29-124">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="d1f29-124">Optional element.</span></span><br /><br /> <span data-ttu-id="d1f29-125">Define as exibições usadas para exibir objetos.</span><span class="sxs-lookup"><span data-stu-id="d1f29-125">Defines the views used to display objects.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d1f29-126">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="d1f29-126">Parent Elements</span></span>

<span data-ttu-id="d1f29-127">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="d1f29-127">None.</span></span>

## <a name="remarks"></a><span data-ttu-id="d1f29-128">Comentários</span><span class="sxs-lookup"><span data-stu-id="d1f29-128">Remarks</span></span>

<span data-ttu-id="d1f29-129">Arquivos de formatação definem como os objetos são exibidos.</span><span class="sxs-lookup"><span data-stu-id="d1f29-129">Formatting files define how objects are displayed.</span></span> <span data-ttu-id="d1f29-130">Na maioria dos casos, esse elemento raiz contém um elemento [ViewDefinitions](./viewdefinitions-element-format.md) que define a tabela, a lista e as exibições amplas do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="d1f29-130">In most cases, this root element contains a [ViewDefinitions](./viewdefinitions-element-format.md) element that defines the table, list, and wide views of the formatting file.</span></span> <span data-ttu-id="d1f29-131">Além das definições de exibição, o arquivo de formatação pode definir conjuntos de seleção, configurações e controles comuns que podem ser usados por essas exibições.</span><span class="sxs-lookup"><span data-stu-id="d1f29-131">In addition to the view definitions, the formatting file can define common selection sets, settings, and controls that those views can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1f29-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d1f29-132">See Also</span></span>

[<span data-ttu-id="d1f29-133">Elemento Controls para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="d1f29-133">Controls Element for Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)

[<span data-ttu-id="d1f29-134">Elemento DefaultSettings (formato)</span><span class="sxs-lookup"><span data-stu-id="d1f29-134">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)

[<span data-ttu-id="d1f29-135">Elemento SelectionSets (Format)</span><span class="sxs-lookup"><span data-stu-id="d1f29-135">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="d1f29-136">Elemento ViewDefinitions (Format)</span><span class="sxs-lookup"><span data-stu-id="d1f29-136">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="d1f29-137">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1f29-137">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
