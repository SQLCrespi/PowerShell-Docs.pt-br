---
title: Elemento ScriptBlock para GroupBy (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e761e02a7910cd598449d564e827889162da9f25
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787675"
---
# <a name="scriptblock-element-for-groupby-format"></a><span data-ttu-id="158f6-102">Elemento ScriptBlock para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="158f6-102">ScriptBlock Element for GroupBy (Format)</span></span>

<span data-ttu-id="158f6-103">Especifica o script que inicia um novo grupo sempre que seu valor é alterado.</span><span class="sxs-lookup"><span data-stu-id="158f6-103">Specifies the script that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="158f6-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) exibir elemento (Format) elemento GroupBy para o elemento View (Format) ScriptBlock para GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="158f6-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) ScriptBlock Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="158f6-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="158f6-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="158f6-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="158f6-106">Attributes and Elements</span></span>

<span data-ttu-id="158f6-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="158f6-107">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="158f6-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="158f6-108">Attributes</span></span>

<span data-ttu-id="158f6-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="158f6-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="158f6-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="158f6-110">Child Elements</span></span>

<span data-ttu-id="158f6-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="158f6-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="158f6-112">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="158f6-112">Parent Elements</span></span>

|<span data-ttu-id="158f6-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="158f6-113">Element</span></span>|<span data-ttu-id="158f6-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="158f6-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="158f6-115">Elemento GroupBy para View (formato)</span><span class="sxs-lookup"><span data-stu-id="158f6-115">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="158f6-116">Define como um grupo de objetos .NET é exibido.</span><span class="sxs-lookup"><span data-stu-id="158f6-116">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="158f6-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="158f6-117">Text Value</span></span>

<span data-ttu-id="158f6-118">Especifique o script que é avaliado.</span><span class="sxs-lookup"><span data-stu-id="158f6-118">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="158f6-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="158f6-119">Remarks</span></span>

<span data-ttu-id="158f6-120">O PowerShell inicia um novo grupo sempre que o valor desse script é alterado.</span><span class="sxs-lookup"><span data-stu-id="158f6-120">PowerShell starts a new group whenever the value of this script changes.</span></span>

<span data-ttu-id="158f6-121">Quando esse elemento é especificado, você não pode especificar o elemento [PropertyName](propertyname-element-for-groupby-format.md) para iniciar um novo grupo.</span><span class="sxs-lookup"><span data-stu-id="158f6-121">When this element is specified, you cannot specify the [PropertyName](propertyname-element-for-groupby-format.md) element to start a new group.</span></span>

## <a name="see-also"></a><span data-ttu-id="158f6-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="158f6-122">See Also</span></span>

[<span data-ttu-id="158f6-123">Elemento PropertyName para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="158f6-123">PropertyName Element for GroupBy (Format)</span></span>](propertyname-element-for-groupby-format.md)

[<span data-ttu-id="158f6-124">Elemento GroupBy para View (formato)</span><span class="sxs-lookup"><span data-stu-id="158f6-124">GroupBy Element for View (Format)</span></span>](groupby-element-for-view-format.md)

[<span data-ttu-id="158f6-125">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="158f6-125">Writing a PowerShell Formatting File</span></span>](writing-a-powershell-formatting-file.md)
