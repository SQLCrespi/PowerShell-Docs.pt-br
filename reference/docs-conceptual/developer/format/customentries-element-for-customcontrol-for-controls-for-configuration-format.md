---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento CustomEntries para CustomControl para Controls para Configuration (formato)
description: Elemento CustomEntries para CustomControl para Controls para Configuration (formato)
ms.openlocfilehash: 86c2b517d0d7075a355a3190a14e25d9dd4fe374
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655397"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-configuration-format"></a><span data-ttu-id="6e5cb-103">Elemento CustomEntries para CustomControl para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="6e5cb-103">CustomEntries Element for CustomControl for Controls for Configuration (Format)</span></span>

<span data-ttu-id="6e5cb-104">Fornece as definições de um controle comum.</span><span class="sxs-lookup"><span data-stu-id="6e5cb-104">Provides the definitions of a common control.</span></span> <span data-ttu-id="6e5cb-105">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="6e5cb-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="6e5cb-106">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="6e5cb-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6e5cb-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6e5cb-107">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="6e5cb-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="6e5cb-108">Attributes and Elements</span></span>

<span data-ttu-id="6e5cb-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomEntries` elemento.</span><span class="sxs-lookup"><span data-stu-id="6e5cb-109">The following sections describe attributes, child elements, and the parent element of the `CustomEntries` element.</span></span> <span data-ttu-id="6e5cb-110">Você deve especificar um ou mais elementos filho.</span><span class="sxs-lookup"><span data-stu-id="6e5cb-110">You must specify one or more child elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="6e5cb-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="6e5cb-111">Attributes</span></span>

<span data-ttu-id="6e5cb-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="6e5cb-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6e5cb-113">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="6e5cb-113">Child Elements</span></span>

|<span data-ttu-id="6e5cb-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="6e5cb-114">Element</span></span>|<span data-ttu-id="6e5cb-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="6e5cb-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6e5cb-116">Elemento CustomEntry para CustomControl para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="6e5cb-116">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="6e5cb-117">Fornece uma definição do controle comum.</span><span class="sxs-lookup"><span data-stu-id="6e5cb-117">Provides a definition of the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="6e5cb-118">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="6e5cb-118">Parent Elements</span></span>

|<span data-ttu-id="6e5cb-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="6e5cb-119">Element</span></span>|<span data-ttu-id="6e5cb-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="6e5cb-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6e5cb-121">Elemento CustomControl para controle de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="6e5cb-121">CustomControl Element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="6e5cb-122">Define um controle comum.</span><span class="sxs-lookup"><span data-stu-id="6e5cb-122">Defines a common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6e5cb-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="6e5cb-123">Remarks</span></span>

<span data-ttu-id="6e5cb-124">Na maioria dos casos, um controle tem apenas uma definição, que é definida em um único `CustomEntry` elemento.</span><span class="sxs-lookup"><span data-stu-id="6e5cb-124">In most cases, a control has only one definition, which is defined in a single `CustomEntry` element.</span></span> <span data-ttu-id="6e5cb-125">No entanto, é possível ter várias definições se você quiser usar o mesmo controle para exibir diferentes objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="6e5cb-125">However it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="6e5cb-126">Nesses casos, você pode definir um `CustomEntry` elemento para cada objeto ou conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="6e5cb-126">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e5cb-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6e5cb-127">See Also</span></span>

[<span data-ttu-id="6e5cb-128">Elemento CustomControl para controle de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="6e5cb-128">CustomControl Element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="6e5cb-129">Elemento CustomEntry para CustomControl para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="6e5cb-129">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="6e5cb-130">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e5cb-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
