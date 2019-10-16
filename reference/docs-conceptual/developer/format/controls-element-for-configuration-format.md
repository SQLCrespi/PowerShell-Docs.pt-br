---
title: Elemento Controls para configuração (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d4ef63d-5866-4319-ba00-7ed96de26821
caps.latest.revision: 18
ms.openlocfilehash: ac9f7ff08f6e87ef83b5a2fe23fc58ee2651566d
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368995"
---
# <a name="controls-element-for-configuration-format"></a><span data-ttu-id="600f9-102">Elemento Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="600f9-102">Controls Element for Configuration (Format)</span></span>

<span data-ttu-id="600f9-103">Define os controles comuns que podem ser usados por todas as exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="600f9-103">Defines the common controls that can be used by all views of the formatting file.</span></span>

<span data-ttu-id="600f9-104">Elemento de configuração (Format) controla o elemento de configuração (formato)</span><span class="sxs-lookup"><span data-stu-id="600f9-104">Configuration Element (Format) Controls Element of Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="600f9-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="600f9-105">Syntax</span></span>

```xml
<Controls>
  <Control>...</Control>
</Controls>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="600f9-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="600f9-106">Attributes and Elements</span></span>

<span data-ttu-id="600f9-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do elemento `Controls`.</span><span class="sxs-lookup"><span data-stu-id="600f9-107">The following sections describe the attributes, child elements, and the parent element of the `Controls` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="600f9-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="600f9-108">Attributes</span></span>

<span data-ttu-id="600f9-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="600f9-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="600f9-110">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="600f9-110">Child Elements</span></span>

|<span data-ttu-id="600f9-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="600f9-111">Element</span></span>|<span data-ttu-id="600f9-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="600f9-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="600f9-113">Elemento Control para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="600f9-113">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)|<span data-ttu-id="600f9-114">Elemento obrigatório.</span><span class="sxs-lookup"><span data-stu-id="600f9-114">Required element.</span></span><br /><br /> <span data-ttu-id="600f9-115">Define um controle comum que pode ser usado por todas as exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="600f9-115">Defines a common control that can be used by all views of the formatting file.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="600f9-116">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="600f9-116">Parent Elements</span></span>

|<span data-ttu-id="600f9-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="600f9-117">Element</span></span>|<span data-ttu-id="600f9-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="600f9-118">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="600f9-119">Elemento Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="600f9-119">Configuration Element (Format)</span></span>](./configuration-element-format.md)|<span data-ttu-id="600f9-120">Representa o elemento de nível superior de um arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="600f9-120">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="600f9-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="600f9-121">Remarks</span></span>

<span data-ttu-id="600f9-122">Você pode criar qualquer número de controles comuns.</span><span class="sxs-lookup"><span data-stu-id="600f9-122">You can create any number of common controls.</span></span> <span data-ttu-id="600f9-123">Para cada controle, você deve especificar o nome que é usado para referenciar o controle e os componentes do controle.</span><span class="sxs-lookup"><span data-stu-id="600f9-123">For each control, you must specify the name that is used to reference the control and the components of the control.</span></span>

## <a name="see-also"></a><span data-ttu-id="600f9-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="600f9-124">See Also</span></span>

[<span data-ttu-id="600f9-125">Elemento Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="600f9-125">Configuration Element (Format)</span></span>](./configuration-element-format.md)

[<span data-ttu-id="600f9-126">Elemento Control para controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="600f9-126">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)

[<span data-ttu-id="600f9-127">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="600f9-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
