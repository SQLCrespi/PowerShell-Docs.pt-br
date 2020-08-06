---
title: Elemento Controls para configuração (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 44b9db0d3523e5e9086da9911882b258a2a54ca6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783782"
---
# <a name="controls-element-for-configuration-format"></a><span data-ttu-id="6976c-102">Elemento Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="6976c-102">Controls Element for Configuration (Format)</span></span>

<span data-ttu-id="6976c-103">Define os controles comuns que podem ser usados por todas as exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="6976c-103">Defines the common controls that can be used by all views of the formatting file.</span></span>

<span data-ttu-id="6976c-104">Elemento de configuração (Format) controla o elemento de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="6976c-104">Configuration Element (Format) Controls Element of Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6976c-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6976c-105">Syntax</span></span>

```xml
<Controls>
  <Control>...</Control>
</Controls>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6976c-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="6976c-106">Attributes and Elements</span></span>

<span data-ttu-id="6976c-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `Controls` elemento.</span><span class="sxs-lookup"><span data-stu-id="6976c-107">The following sections describe the attributes, child elements, and the parent element of the `Controls` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6976c-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="6976c-108">Attributes</span></span>

<span data-ttu-id="6976c-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="6976c-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6976c-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="6976c-110">Child Elements</span></span>

|<span data-ttu-id="6976c-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="6976c-111">Element</span></span>|<span data-ttu-id="6976c-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="6976c-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6976c-113">Elemento Control para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="6976c-113">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)|<span data-ttu-id="6976c-114">Elemento necessário.</span><span class="sxs-lookup"><span data-stu-id="6976c-114">Required element.</span></span><br /><br /> <span data-ttu-id="6976c-115">Define um controle comum que pode ser usado por todas as exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="6976c-115">Defines a common control that can be used by all views of the formatting file.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="6976c-116">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="6976c-116">Parent Elements</span></span>

|<span data-ttu-id="6976c-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="6976c-117">Element</span></span>|<span data-ttu-id="6976c-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="6976c-118">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6976c-119">Elemento Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="6976c-119">Configuration Element (Format)</span></span>](./configuration-element-format.md)|<span data-ttu-id="6976c-120">Representa o elemento de nível superior de um arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="6976c-120">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6976c-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="6976c-121">Remarks</span></span>

<span data-ttu-id="6976c-122">Você pode criar qualquer número de controles comuns.</span><span class="sxs-lookup"><span data-stu-id="6976c-122">You can create any number of common controls.</span></span> <span data-ttu-id="6976c-123">Para cada controle, você deve especificar o nome que é usado para referenciar o controle e os componentes do controle.</span><span class="sxs-lookup"><span data-stu-id="6976c-123">For each control, you must specify the name that is used to reference the control and the components of the control.</span></span>

## <a name="see-also"></a><span data-ttu-id="6976c-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6976c-124">See Also</span></span>

[<span data-ttu-id="6976c-125">Elemento Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="6976c-125">Configuration Element (Format)</span></span>](./configuration-element-format.md)

[<span data-ttu-id="6976c-126">Elemento Control para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="6976c-126">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)

[<span data-ttu-id="6976c-127">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="6976c-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
