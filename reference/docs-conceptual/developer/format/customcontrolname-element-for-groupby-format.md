---
title: Elemento CustomControlName para GroupBy (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 4e3102f12cd37fa72a2de1bf1db5d1f82db31222
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783731"
---
# <a name="customcontrolname-element-for-groupby-format"></a><span data-ttu-id="fcc63-102">Elemento CustomControlName para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="fcc63-102">CustomControlName Element for GroupBy (Format)</span></span>

<span data-ttu-id="fcc63-103">Especifica o nome de um controle personalizado que é usado para exibir o novo grupo.</span><span class="sxs-lookup"><span data-stu-id="fcc63-103">Specifies the name of a custom control that is used to display the new group.</span></span> <span data-ttu-id="fcc63-104">Esse elemento é usado ao definir uma tabela, lista, exibição de controle largo ou personalizada.</span><span class="sxs-lookup"><span data-stu-id="fcc63-104">This element is used when defining a table, list, wide or custom control view.</span></span>

<span data-ttu-id="fcc63-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para View (Format) CustomControlName element de GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="fcc63-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControlName Element of GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fcc63-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="fcc63-106">Syntax</span></span>

```xml
<CustomControlName>ControlName</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fcc63-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="fcc63-107">Attributes and Elements</span></span>

<span data-ttu-id="fcc63-108">As seções a seguir descrevem os atributos, os elementos filho e os elementos pai do `CustomControlName` elemento.</span><span class="sxs-lookup"><span data-stu-id="fcc63-108">The following sections describe the attributes, child elements, and parent elements of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="fcc63-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="fcc63-109">Attributes</span></span>

<span data-ttu-id="fcc63-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="fcc63-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fcc63-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="fcc63-111">Child Elements</span></span>

<span data-ttu-id="fcc63-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="fcc63-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fcc63-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="fcc63-113">Parent Elements</span></span>

|<span data-ttu-id="fcc63-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="fcc63-114">Element</span></span>|<span data-ttu-id="fcc63-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="fcc63-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fcc63-116">Elemento GroupBy para View (formato)</span><span class="sxs-lookup"><span data-stu-id="fcc63-116">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="fcc63-117">Define como o Windows PowerShell exibe um novo grupo de objetos.</span><span class="sxs-lookup"><span data-stu-id="fcc63-117">Defines how Windows PowerShell displays a new group of objects.</span></span>|

## <a name="text-value"></a><span data-ttu-id="fcc63-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="fcc63-118">Text Value</span></span>

<span data-ttu-id="fcc63-119">Especifique o nome do controle personalizado usado para exibir um novo grupo.</span><span class="sxs-lookup"><span data-stu-id="fcc63-119">Specify the name of the custom control that is used to display a new group.</span></span>

## <a name="remarks"></a><span data-ttu-id="fcc63-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="fcc63-120">Remarks</span></span>

<span data-ttu-id="fcc63-121">Você pode criar controles comuns que podem ser usados por todas as exibições de um arquivo de formatação e pode criar controles de exibição que podem ser usados por uma exibição específica.</span><span class="sxs-lookup"><span data-stu-id="fcc63-121">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="fcc63-122">Os seguintes elementos especificam os nomes desses controles personalizados:</span><span class="sxs-lookup"><span data-stu-id="fcc63-122">The following elements specify the names of these custom controls:</span></span>

- [<span data-ttu-id="fcc63-123">Elemento Name para Control para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="fcc63-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="fcc63-124">Elemento Name para Control para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="fcc63-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="fcc63-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fcc63-125">See Also</span></span>

[<span data-ttu-id="fcc63-126">Elemento GroupBy para View (formato)</span><span class="sxs-lookup"><span data-stu-id="fcc63-126">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="fcc63-127">Elemento Name para Control para Controls para Configuration (formato)</span><span class="sxs-lookup"><span data-stu-id="fcc63-127">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="fcc63-128">Elemento Name para Control para Controls para View (formato)</span><span class="sxs-lookup"><span data-stu-id="fcc63-128">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="fcc63-129">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="fcc63-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
