---
title: Elemento CustomControlName para ExpressionBinding para CustomControl para View (Format) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea821e8b-4d65-4263-b7e4-6aeca9f534c2
caps.latest.revision: 9
ms.openlocfilehash: b44ced75bbaac7c0744f347bdc97f87365b8fe39
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364105"
---
# <a name="customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format"></a><span data-ttu-id="53103-102">Elemento CustomControlName para ExpressionBinding para CustomControl para View (formato)</span><span class="sxs-lookup"><span data-stu-id="53103-102">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>

<span data-ttu-id="53103-103">Especifica o nome de um controle comum ou um controle de exibição.</span><span class="sxs-lookup"><span data-stu-id="53103-103">Specifies the name of a common control or a view control.</span></span> <span data-ttu-id="53103-104">Esse elemento é usado ao definir um modo de exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="53103-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="53103-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl Element para View (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Elemento para CustomEntry para o elemento ExpressionBinding View (Format) para o elemento CustomItem (Format) CustomControlName para a associação de expressão para CustomItem (Format)</span><span class="sxs-lookup"><span data-stu-id="53103-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem (Format) CustomControlName Element for Expression Binding for CustomItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="53103-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="53103-106">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="53103-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="53103-107">Attributes and Elements</span></span>

<span data-ttu-id="53103-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `CustomControlName`.</span><span class="sxs-lookup"><span data-stu-id="53103-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="53103-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="53103-109">Attributes</span></span>

<span data-ttu-id="53103-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="53103-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="53103-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="53103-111">Child Elements</span></span>

<span data-ttu-id="53103-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="53103-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="53103-113">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="53103-113">Parent Elements</span></span>

|<span data-ttu-id="53103-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="53103-114">Element</span></span>|<span data-ttu-id="53103-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="53103-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="53103-116">Elemento ExpressionBinding para CustomItem (Format)</span><span class="sxs-lookup"><span data-stu-id="53103-116">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="53103-117">Define os dados que são exibidos pelo controle.</span><span class="sxs-lookup"><span data-stu-id="53103-117">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="53103-118">Valor de Texto</span><span class="sxs-lookup"><span data-stu-id="53103-118">Text Value</span></span>

<span data-ttu-id="53103-119">Especifique o nome do controle.</span><span class="sxs-lookup"><span data-stu-id="53103-119">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="53103-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="53103-120">Remarks</span></span>

<span data-ttu-id="53103-121">Você pode criar controles comuns que podem ser usados por todas as exibições de um arquivo de formatação e pode criar controles de exibição que podem ser usados por uma exibição específica.</span><span class="sxs-lookup"><span data-stu-id="53103-121">You can create common controls that can be used by all the views of a formatting file and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="53103-122">Os nomes desses controles são especificados pelos elementos a seguir.</span><span class="sxs-lookup"><span data-stu-id="53103-122">The names of these controls are specified by the following elements.</span></span>

- [<span data-ttu-id="53103-123">Elemento Name para controle de controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="53103-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="53103-124">Elemento Name para controle de controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="53103-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="53103-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="53103-125">See Also</span></span>

[<span data-ttu-id="53103-126">Elemento Name para controle de controles para configuração (Format)</span><span class="sxs-lookup"><span data-stu-id="53103-126">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="53103-127">Elemento Name para controle de controles para View (Format)</span><span class="sxs-lookup"><span data-stu-id="53103-127">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="53103-128">Elemento ExpressionBinding para CustomItem (Format)</span><span class="sxs-lookup"><span data-stu-id="53103-128">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="53103-129">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="53103-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
