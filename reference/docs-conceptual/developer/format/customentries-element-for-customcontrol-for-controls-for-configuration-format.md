---
title: Elemento CustomEntries para CustomControl para controles para configuração (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: b1f494cf1a254d71362830ba9eb0f4905a2a484d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785975"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-configuration-format"></a><span data-ttu-id="5ba44-102">Elemento CustomEntries para CustomControl para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="5ba44-102">CustomEntries Element for CustomControl for Controls for Configuration (Format)</span></span>

<span data-ttu-id="5ba44-103">Fornece as definições de um controle comum.</span><span class="sxs-lookup"><span data-stu-id="5ba44-103">Provides the definitions of a common control.</span></span> <span data-ttu-id="5ba44-104">Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="5ba44-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="5ba44-105">Elemento de configuração (Format) controla o elemento de controle de configuração (formato) para controles para o elemento de configuração (Format) CustomControl para controle para o elemento de configuração (Format) CustomEntries para CustomControl para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="5ba44-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5ba44-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5ba44-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="5ba44-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="5ba44-107">Attributes and Elements</span></span>

<span data-ttu-id="5ba44-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `CustomEntries` elemento.</span><span class="sxs-lookup"><span data-stu-id="5ba44-108">The following sections describe attributes, child elements, and the parent element of the `CustomEntries` element.</span></span> <span data-ttu-id="5ba44-109">Você deve especificar um ou mais elementos filho.</span><span class="sxs-lookup"><span data-stu-id="5ba44-109">You must specify one or more child elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="5ba44-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="5ba44-110">Attributes</span></span>

<span data-ttu-id="5ba44-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="5ba44-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5ba44-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="5ba44-112">Child Elements</span></span>

|<span data-ttu-id="5ba44-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="5ba44-113">Element</span></span>|<span data-ttu-id="5ba44-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="5ba44-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5ba44-115">Elemento CustomEntry para CustomControl para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="5ba44-115">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="5ba44-116">Fornece uma definição do controle comum.</span><span class="sxs-lookup"><span data-stu-id="5ba44-116">Provides a definition of the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5ba44-117">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="5ba44-117">Parent Elements</span></span>

|<span data-ttu-id="5ba44-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="5ba44-118">Element</span></span>|<span data-ttu-id="5ba44-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="5ba44-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5ba44-120">Elemento CustomControl para controle de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="5ba44-120">CustomControl Element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="5ba44-121">Define um controle comum.</span><span class="sxs-lookup"><span data-stu-id="5ba44-121">Defines a common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5ba44-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="5ba44-122">Remarks</span></span>

<span data-ttu-id="5ba44-123">Na maioria dos casos, um controle tem apenas uma definição, que é definida em um único `CustomEntry` elemento.</span><span class="sxs-lookup"><span data-stu-id="5ba44-123">In most cases, a control has only one definition, which is defined in a single `CustomEntry` element.</span></span> <span data-ttu-id="5ba44-124">No entanto, é possível ter várias definições se você quiser usar o mesmo controle para exibir diferentes objetos .NET.</span><span class="sxs-lookup"><span data-stu-id="5ba44-124">However it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="5ba44-125">Nesses casos, você pode definir um `CustomEntry` elemento para cada objeto ou conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="5ba44-125">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ba44-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5ba44-126">See Also</span></span>

[<span data-ttu-id="5ba44-127">Elemento CustomControl para controle de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="5ba44-127">CustomControl Element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="5ba44-128">Elemento CustomEntry para CustomControl para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="5ba44-128">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="5ba44-129">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ba44-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
