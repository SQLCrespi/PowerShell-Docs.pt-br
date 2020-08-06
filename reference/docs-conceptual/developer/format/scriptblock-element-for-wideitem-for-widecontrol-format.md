---
title: Elemento ScriptBlock para WideItem para WideControl (Format) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: be649d6de0d2dfa6bad14f2d7476cced9cd6cb6d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787590"
---
# <a name="scriptblock-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="f1ed9-102">Elemento ScriptBlock para WideItem para WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="f1ed9-102">ScriptBlock Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="f1ed9-103">Especifica o script cujo valor é exibido na exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="f1ed9-103">Specifies the script whose value is displayed in the wide view.</span></span>

<span data-ttu-id="f1ed9-104">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) WideControl elemento (Format) WideEntries Element (Format) WideEntry elemento (Format) WideItem Element (Format) @ Element for WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="f1ed9-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format) ScriptBlock Element for WideItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f1ed9-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f1ed9-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToExecute</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f1ed9-106">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="f1ed9-106">Attributes and Elements</span></span>

<span data-ttu-id="f1ed9-107">As seções a seguir descrevem os atributos, os elementos filho e o elemento pai do `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="f1ed9-107">The following sections describe the attributes, child elements, and parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f1ed9-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="f1ed9-108">Attributes</span></span>

<span data-ttu-id="f1ed9-109">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="f1ed9-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f1ed9-110">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="f1ed9-110">Child Elements</span></span>

<span data-ttu-id="f1ed9-111">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="f1ed9-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f1ed9-112">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="f1ed9-112">Parent Elements</span></span>

|<span data-ttu-id="f1ed9-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="f1ed9-113">Element</span></span>|<span data-ttu-id="f1ed9-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="f1ed9-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f1ed9-115">Elemento WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="f1ed9-115">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="f1ed9-116">Define a propriedade ou bloco de script cujo valor é exibido na exibição ampla.</span><span class="sxs-lookup"><span data-stu-id="f1ed9-116">Defines the property or script block whose value is displayed in the wide view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f1ed9-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="f1ed9-117">Text Value</span></span>

<span data-ttu-id="f1ed9-118">Especifique o script cujo valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="f1ed9-118">Specify the script whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="f1ed9-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="f1ed9-119">Remarks</span></span>

<span data-ttu-id="f1ed9-120">Para obter mais informações sobre os componentes de uma exibição ampla, consulte [criando uma exibição ampla](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="f1ed9-120">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="f1ed9-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f1ed9-121">Example</span></span>

<span data-ttu-id="f1ed9-122">Este exemplo mostra um `WideItem` elemento que define um script cujo valor é exibido na exibição.</span><span class="sxs-lookup"><span data-stu-id="f1ed9-122">This example shows a `WideItem` element that defines a script whose value is displayed in the view.</span></span>

```xml
<WideItem>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
</WideItem>
```

## <a name="see-also"></a><span data-ttu-id="f1ed9-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f1ed9-123">See Also</span></span>

[<span data-ttu-id="f1ed9-124">Elemento WideItem (Format)</span><span class="sxs-lookup"><span data-stu-id="f1ed9-124">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="f1ed9-125">Criar uma exibição ampla</span><span class="sxs-lookup"><span data-stu-id="f1ed9-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="f1ed9-126">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1ed9-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
