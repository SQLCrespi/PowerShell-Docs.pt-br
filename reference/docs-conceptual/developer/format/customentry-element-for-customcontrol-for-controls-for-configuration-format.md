---
title: Elemento CustomEntry para CustomControl para controles para configuração (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 8b9d18bbb1abce8135f4c27418ad54a1736eb5a6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785924"
---
# <a name="customentry-element-for-customcontrol-for-controls-for-configuration-format"></a><span data-ttu-id="51c51-102">Elemento CustomEntry para CustomControl para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="51c51-102">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>

<span data-ttu-id="51c51-103">Fornece uma definição do controle comum.</span><span class="sxs-lookup"><span data-stu-id="51c51-103">Provides a definition of the common control.</span></span> <span data-ttu-id="51c51-104">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="51c51-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="51c51-105">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para o elemento de configuração (Format) CustomEntry para CustomControl para controles para a configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="51c51-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="51c51-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="51c51-106">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="51c51-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="51c51-107">Attributes and Elements</span></span>

<span data-ttu-id="51c51-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomEntry` elemento.</span><span class="sxs-lookup"><span data-stu-id="51c51-108">The following sections describe attributes, child elements, and the parent element of the `CustomEntry` element.</span></span> <span data-ttu-id="51c51-109">Você deve especificar os itens exibidos pela definição.</span><span class="sxs-lookup"><span data-stu-id="51c51-109">You must specify the items displayed by the definition.</span></span>

### <a name="attributes"></a><span data-ttu-id="51c51-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="51c51-110">Attributes</span></span>

<span data-ttu-id="51c51-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="51c51-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="51c51-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="51c51-112">Child Elements</span></span>

|<span data-ttu-id="51c51-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="51c51-113">Element</span></span>|<span data-ttu-id="51c51-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="51c51-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="51c51-115">Elemento EntrySelectedBy para CustomEntry para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="51c51-115">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="51c51-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="51c51-116">Optional element.</span></span><br /><br /> <span data-ttu-id="51c51-117">Define os tipos .NET que usam a definição do controle comum ou a condição que deve existir para que esse controle seja usado.</span><span class="sxs-lookup"><span data-stu-id="51c51-117">Defines the .NET types that use the definition of the common control or the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="51c51-118">Elemento CustomItem para CustomEntry para controles de configuração</span><span class="sxs-lookup"><span data-stu-id="51c51-118">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="51c51-119">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="51c51-119">Required element.</span></span><br /><br /> <span data-ttu-id="51c51-120">Define quais dados são exibidos pelo controle e como eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="51c51-120">Defines what data is displayed by the control and how it is displayed.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="51c51-121">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="51c51-121">Parent Elements</span></span>

|<span data-ttu-id="51c51-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="51c51-122">Element</span></span>|<span data-ttu-id="51c51-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="51c51-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="51c51-124">Elemento CustomEntries para CustomControl para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="51c51-124">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="51c51-125">Fornece as definições do controle comum.</span><span class="sxs-lookup"><span data-stu-id="51c51-125">Provides the definitions of the common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="51c51-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="51c51-126">Remarks</span></span>

<span data-ttu-id="51c51-127">Na maioria dos casos, apenas uma definição é necessária para cada controle personalizado comum, mas é possível ter várias definições se você quiser usar o mesmo controle para exibir diferentes objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="51c51-127">In most cases, only one definition is required for each common custom control, but it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="51c51-128">Nesses casos, você pode fornecer uma definição separada para cada objeto ou conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="51c51-128">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="51c51-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="51c51-129">See Also</span></span>

[<span data-ttu-id="51c51-130">Elemento CustomEntries para CustomControl para configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="51c51-130">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="51c51-131">Elemento CustomItem para CustomEntry para controles de configuração</span><span class="sxs-lookup"><span data-stu-id="51c51-131">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="51c51-132">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="51c51-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
