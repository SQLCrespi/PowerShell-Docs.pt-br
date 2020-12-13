---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento DisplayError (formato)
description: Elemento DisplayError (formato)
ms.openlocfilehash: fb54df86a3558263687a8c417870495b7066f563
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649922"
---
# <a name="displayerror-element-format"></a><span data-ttu-id="90fc8-103">Elemento DisplayError (formato)</span><span class="sxs-lookup"><span data-stu-id="90fc8-103">DisplayError Element (Format)</span></span>

<span data-ttu-id="90fc8-104">Especifica que a cadeia de caracteres #ERR é exibida quando ocorre um erro exibindo uma parte dos dados.</span><span class="sxs-lookup"><span data-stu-id="90fc8-104">Specifies that the string #ERR is displayed when an error occurs displaying a piece of data.</span></span>

<span data-ttu-id="90fc8-105">Elemento de configuração (Format) DefaultSettings Element (Format) elemento DisplayError (Format)</span><span class="sxs-lookup"><span data-stu-id="90fc8-105">Configuration Element (Format) DefaultSettings Element (Format) DisplayError Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="90fc8-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="90fc8-106">Syntax</span></span>

```xml
<DisplayError/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="90fc8-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="90fc8-107">Attributes and Elements</span></span>

<span data-ttu-id="90fc8-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `DisplayError` elemento.</span><span class="sxs-lookup"><span data-stu-id="90fc8-108">The following sections describe attributes, child elements, and the parent element of the `DisplayError` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="90fc8-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="90fc8-109">Attributes</span></span>

<span data-ttu-id="90fc8-110">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="90fc8-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="90fc8-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="90fc8-111">Child Elements</span></span>

<span data-ttu-id="90fc8-112">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="90fc8-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="90fc8-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="90fc8-113">Parent Elements</span></span>

|<span data-ttu-id="90fc8-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="90fc8-114">Element</span></span>|<span data-ttu-id="90fc8-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="90fc8-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="90fc8-116">Elemento DefaultSettings (formato)</span><span class="sxs-lookup"><span data-stu-id="90fc8-116">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="90fc8-117">Define as configurações comuns que se aplicam a todas as exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="90fc8-117">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="90fc8-118">Comentários</span><span class="sxs-lookup"><span data-stu-id="90fc8-118">Remarks</span></span>

<span data-ttu-id="90fc8-119">Por padrão, quando ocorre um erro durante a tentativa de exibir um dado, o local dos dados é deixado em branco.</span><span class="sxs-lookup"><span data-stu-id="90fc8-119">By default, when an error occurs while trying to display a piece of data, the location of the data is left blank.</span></span> <span data-ttu-id="90fc8-120">Quando esse elemento é definido como true, a cadeia de caracteres #ERR será exibida.</span><span class="sxs-lookup"><span data-stu-id="90fc8-120">When this element is set to true, the #ERR string will be displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="90fc8-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="90fc8-121">See Also</span></span>

[<span data-ttu-id="90fc8-122">Elemento DefaultSettings (formato)</span><span class="sxs-lookup"><span data-stu-id="90fc8-122">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)

[<span data-ttu-id="90fc8-123">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="90fc8-123">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
