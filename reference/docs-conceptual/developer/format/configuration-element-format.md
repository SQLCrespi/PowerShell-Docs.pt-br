---
title: Elemento Configuration (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 90be02f8e27c0bd391e01da1a08ecd8eeb29b84c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783833"
---
# <a name="configuration-element-format"></a><span data-ttu-id="8b71b-102">Elemento Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="8b71b-102">Configuration Element (Format)</span></span>

<span data-ttu-id="8b71b-103">Representa o elemento de nível superior de um arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="8b71b-103">Represents the top-level element of a formatting file.</span></span>

<span data-ttu-id="8b71b-104">Elemento de configuração</span><span class="sxs-lookup"><span data-stu-id="8b71b-104">Configuration Element</span></span>

## <a name="syntax"></a><span data-ttu-id="8b71b-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8b71b-105">Syntax</span></span>

```xml
<Configuration>
  <DefaultSettings>...</DefaultSettings>
  <SelectionSets>...</SelectionSets>
  <Controls>...</Controls>
  <ViewDefinitions>...</ViewDefinitions>
</Configuration>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="8b71b-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="8b71b-106">Attributes and Elements</span></span>

<span data-ttu-id="8b71b-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `Configuration` elemento.</span><span class="sxs-lookup"><span data-stu-id="8b71b-107">The following sections describe the attributes, child elements, and the parent element of the `Configuration` element.</span></span> <span data-ttu-id="8b71b-108">Esse elemento deve ser o elemento raiz para cada arquivo de formatação, e esse elemento deve conter pelo menos um elemento filho.</span><span class="sxs-lookup"><span data-stu-id="8b71b-108">This element must be the root element for each formatting file, and this element must contain at least one child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8b71b-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="8b71b-109">Attributes</span></span>

<span data-ttu-id="8b71b-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="8b71b-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8b71b-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="8b71b-111">Child Elements</span></span>

|<span data-ttu-id="8b71b-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="8b71b-112">Element</span></span>|<span data-ttu-id="8b71b-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="8b71b-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8b71b-114">Elemento Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="8b71b-114">Controls Element for Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)|<span data-ttu-id="8b71b-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="8b71b-115">Optional element.</span></span><br /><br /> <span data-ttu-id="8b71b-116">Define os controles comuns que podem ser usados por todas as exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="8b71b-116">Defines the common controls that can be used by all views of the formatting file.</span></span>|
|[<span data-ttu-id="8b71b-117">Elemento DefaultSettings (formato)</span><span class="sxs-lookup"><span data-stu-id="8b71b-117">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="8b71b-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="8b71b-118">Optional element.</span></span><br /><br /> <span data-ttu-id="8b71b-119">Define as configurações comuns que se aplicam a todas as exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="8b71b-119">Defines common settings that apply to all the views of the formatting file.</span></span>|
|[<span data-ttu-id="8b71b-120">Formato do elemento SelectionSets</span><span class="sxs-lookup"><span data-stu-id="8b71b-120">SelectionSets Element Format</span></span>](./selectionsets-element-format.md)|<span data-ttu-id="8b71b-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="8b71b-121">Optional element.</span></span><br /><br /> <span data-ttu-id="8b71b-122">Define os conjuntos comuns de objetos .NET que podem ser usados por todas as exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="8b71b-122">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span>|
|[<span data-ttu-id="8b71b-123">Elemento ViewDefinitions (formato)</span><span class="sxs-lookup"><span data-stu-id="8b71b-123">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="8b71b-124">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="8b71b-124">Optional element.</span></span><br /><br /> <span data-ttu-id="8b71b-125">Define as exibições usadas para exibir objetos.</span><span class="sxs-lookup"><span data-stu-id="8b71b-125">Defines the views used to display objects.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="8b71b-126">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="8b71b-126">Parent Elements</span></span>

<span data-ttu-id="8b71b-127">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="8b71b-127">None.</span></span>

## <a name="remarks"></a><span data-ttu-id="8b71b-128">Comentários</span><span class="sxs-lookup"><span data-stu-id="8b71b-128">Remarks</span></span>

<span data-ttu-id="8b71b-129">Arquivos de formatação definem como os objetos são exibidos.</span><span class="sxs-lookup"><span data-stu-id="8b71b-129">Formatting files define how objects are displayed.</span></span> <span data-ttu-id="8b71b-130">Na maioria dos casos, esse elemento raiz contém um elemento [ViewDefinitions](./viewdefinitions-element-format.md) que define a tabela, a lista e as exibições amplas do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="8b71b-130">In most cases, this root element contains a [ViewDefinitions](./viewdefinitions-element-format.md) element that defines the table, list, and wide views of the formatting file.</span></span> <span data-ttu-id="8b71b-131">Além das definições de exibição, o arquivo de formatação pode definir conjuntos de seleção, configurações e controles comuns que podem ser usados por essas exibições.</span><span class="sxs-lookup"><span data-stu-id="8b71b-131">In addition to the view definitions, the formatting file can define common selection sets, settings, and controls that those views can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="8b71b-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8b71b-132">See Also</span></span>

[<span data-ttu-id="8b71b-133">Elemento Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="8b71b-133">Controls Element for Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)

[<span data-ttu-id="8b71b-134">Elemento DefaultSettings (formato)</span><span class="sxs-lookup"><span data-stu-id="8b71b-134">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)

[<span data-ttu-id="8b71b-135">Elemento SelectionSets (formato)</span><span class="sxs-lookup"><span data-stu-id="8b71b-135">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="8b71b-136">Elemento ViewDefinitions (formato)</span><span class="sxs-lookup"><span data-stu-id="8b71b-136">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="8b71b-137">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="8b71b-137">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
