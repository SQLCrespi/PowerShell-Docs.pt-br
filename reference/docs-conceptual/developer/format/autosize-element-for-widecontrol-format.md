---
title: Elemento AutoSize para WideControl (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: def37479-7b6e-40cf-bc81-0f7cbc651b31
caps.latest.revision: 11
ms.openlocfilehash: 6dbaef5886a0600bd9fe96dbc8d21f00a674dfcf
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369045"
---
# <a name="autosize-element-for-widecontrol-format"></a><span data-ttu-id="83326-102">Elemento AutoSize para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="83326-102">AutoSize Element for WideControl (Format)</span></span>

<span data-ttu-id="83326-103">Especifica se o tamanho da coluna e o número de colunas são ajustados com base no tamanho dos dados.</span><span class="sxs-lookup"><span data-stu-id="83326-103">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>

<span data-ttu-id="83326-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) WideControl elemento (Format) AutoSize Element para WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="83326-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) Autosize Element for WideControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="83326-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="83326-105">Syntax</span></span>

```xml
<AutoSize/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="83326-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="83326-106">Attributes and Elements</span></span>

<span data-ttu-id="83326-107">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `AutoSize`.</span><span class="sxs-lookup"><span data-stu-id="83326-107">The following sections describe attributes, child elements, and the parent element of the `AutoSize` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="83326-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="83326-108">Attributes</span></span>

<span data-ttu-id="83326-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="83326-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="83326-110">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="83326-110">Child Elements</span></span>

<span data-ttu-id="83326-111">Não</span><span class="sxs-lookup"><span data-stu-id="83326-111">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="83326-112">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="83326-112">Parent Elements</span></span>

|<span data-ttu-id="83326-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="83326-113">Element</span></span>|<span data-ttu-id="83326-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="83326-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="83326-115">Elemento WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="83326-115">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="83326-116">Define um formato de lista largo (valor único) para a exibição.</span><span class="sxs-lookup"><span data-stu-id="83326-116">Defines a wide (single value) list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="83326-117">Comentários</span><span class="sxs-lookup"><span data-stu-id="83326-117">Remarks</span></span>

<span data-ttu-id="83326-118">Ao definir uma exibição ampla, você pode adicionar o elemento `AutoSize` ou o elemento [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) , mas não pode adicionar ambos.</span><span class="sxs-lookup"><span data-stu-id="83326-118">When defining a wide view, you can add the `AutoSize` element or the [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) element, but you cannot add both.</span></span>

<span data-ttu-id="83326-119">Para obter mais informações sobre os componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="83326-119">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

<span data-ttu-id="83326-120">Para obter um exemplo de uma exibição ampla, consulte [Wide View (básica)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="83326-120">For an example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="83326-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="83326-121">See Also</span></span>

[<span data-ttu-id="83326-122">Elemento ColumnNumber para WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="83326-122">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)

[<span data-ttu-id="83326-123">Criando uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="83326-123">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="83326-124">Elemento WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="83326-124">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="83326-125">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="83326-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
