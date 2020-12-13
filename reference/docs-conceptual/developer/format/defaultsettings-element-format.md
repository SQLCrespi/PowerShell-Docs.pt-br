---
ms.date: 09/13/2016
ms.topic: reference
title: Elemento DefaultSettings (formato)
description: Elemento DefaultSettings (formato)
ms.openlocfilehash: 1c2055b38a416fe2d75fa20c6c87e92d9eed4285
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666715"
---
# <a name="defaultsettings-element-format"></a><span data-ttu-id="59cf0-103">Elemento DefaultSettings (formato)</span><span class="sxs-lookup"><span data-stu-id="59cf0-103">DefaultSettings Element (Format)</span></span>

<span data-ttu-id="59cf0-104">Define as configurações comuns que se aplicam a todas as exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="59cf0-104">Defines common settings that apply to all the views of the formatting file.</span></span> <span data-ttu-id="59cf0-105">As configurações comuns incluem a exibição de erros, o encapsulamento de texto em tabelas, a definição de como as coleções são expandidas e muito mais.</span><span class="sxs-lookup"><span data-stu-id="59cf0-105">Common settings include displaying errors, wrapping text in tables, defining how collections are expanded, and more.</span></span>

<span data-ttu-id="59cf0-106">Elemento Configuration (formato) DefaultSettings Element (Format)</span><span class="sxs-lookup"><span data-stu-id="59cf0-106">Configuration Element (Format) DefaultSettings Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="59cf0-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="59cf0-107">Syntax</span></span>

```xml
<DefaultSettings>
  <ShowError/>
  <DisplayError/>
 <PropertyCountForTable>NumberOfProperties</PropertyCountFortable>
  <WrapTables/>
  <EnumerableExpansions>...</EnumerableExpansions>
</DefaultSettings>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="59cf0-108">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="59cf0-108">Attributes and Elements</span></span>

<span data-ttu-id="59cf0-109">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `DefaultSettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="59cf0-109">The following sections describe attributes, child elements, and the parent element of the `DefaultSettings` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="59cf0-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="59cf0-110">Attributes</span></span>

<span data-ttu-id="59cf0-111">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="59cf0-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="59cf0-112">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="59cf0-112">Child Elements</span></span>

|<span data-ttu-id="59cf0-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="59cf0-113">Element</span></span>|<span data-ttu-id="59cf0-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="59cf0-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="59cf0-115">Elemento DisplayError (formato)</span><span class="sxs-lookup"><span data-stu-id="59cf0-115">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)|<span data-ttu-id="59cf0-116">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="59cf0-116">Optional element.</span></span><br /><br /> <span data-ttu-id="59cf0-117">Especifica que a cadeia de caracteres #ERR é exibida quando ocorre um erro durante a exibição de um dado.</span><span class="sxs-lookup"><span data-stu-id="59cf0-117">Specifies that the string #ERR is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="59cf0-118">Elemento EnumerableExpansions (formato)</span><span class="sxs-lookup"><span data-stu-id="59cf0-118">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="59cf0-119">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="59cf0-119">Optional element.</span></span><br /><br /> <span data-ttu-id="59cf0-120">Define as diferentes maneiras como os objetos .NET são expandidos quando são exibidos em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="59cf0-120">Defines the different ways that .NET objects are expanded when they are displayed in a view.</span></span>|
|[<span data-ttu-id="59cf0-121">PropertyCountForTable (formato)</span><span class="sxs-lookup"><span data-stu-id="59cf0-121">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)|<span data-ttu-id="59cf0-122">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="59cf0-122">Optional element.</span></span><br /><br /> <span data-ttu-id="59cf0-123">Especifica o número mínimo de propriedades que um objeto deve ter para exibir o objeto em uma exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="59cf0-123">Specifies the minimum number of properties that an object must have to display the object in a table view.</span></span>|
|[<span data-ttu-id="59cf0-124">Elemento ShowError (formato)</span><span class="sxs-lookup"><span data-stu-id="59cf0-124">ShowError Element (Format)</span></span>](./showerror-element-format.md)|<span data-ttu-id="59cf0-125">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="59cf0-125">Optional element.</span></span><br /><br /> <span data-ttu-id="59cf0-126">Especifica que o registro de erro completo é exibido quando ocorre um erro durante a exibição de um dado.</span><span class="sxs-lookup"><span data-stu-id="59cf0-126">Specifies that the full error record is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="59cf0-127">Elemento WrapTables (formato)</span><span class="sxs-lookup"><span data-stu-id="59cf0-127">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)|<span data-ttu-id="59cf0-128">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="59cf0-128">Optional element.</span></span><br /><br /> <span data-ttu-id="59cf0-129">Especifica que os dados em uma tabela serão movidos para a próxima linha se não couberem na largura da coluna.</span><span class="sxs-lookup"><span data-stu-id="59cf0-129">Specifies that data in a table is moved to the next line if it does not fit into the width of the column.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="59cf0-130">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="59cf0-130">Parent Elements</span></span>

|<span data-ttu-id="59cf0-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="59cf0-131">Element</span></span>|<span data-ttu-id="59cf0-132">Descrição</span><span class="sxs-lookup"><span data-stu-id="59cf0-132">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="59cf0-133">Elemento de configuração</span><span class="sxs-lookup"><span data-stu-id="59cf0-133">Configuration Element</span></span>](./configuration-element-format.md)|<span data-ttu-id="59cf0-134">Representa o elemento de nível superior de um arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="59cf0-134">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="59cf0-135">Comentários</span><span class="sxs-lookup"><span data-stu-id="59cf0-135">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="59cf0-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="59cf0-136">See Also</span></span>

[<span data-ttu-id="59cf0-137">Elemento de configuração</span><span class="sxs-lookup"><span data-stu-id="59cf0-137">Configuration Element</span></span>](./configuration-element-format.md)

[<span data-ttu-id="59cf0-138">Elemento DisplayError (formato)</span><span class="sxs-lookup"><span data-stu-id="59cf0-138">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)

[<span data-ttu-id="59cf0-139">Elemento EnumerableExpansions (formato)</span><span class="sxs-lookup"><span data-stu-id="59cf0-139">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)

[<span data-ttu-id="59cf0-140">PropertyCountForTable (formato)</span><span class="sxs-lookup"><span data-stu-id="59cf0-140">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)

[<span data-ttu-id="59cf0-141">Elemento ShowError (formato)</span><span class="sxs-lookup"><span data-stu-id="59cf0-141">ShowError Element (Format)</span></span>](./showerror-element-format.md)

[<span data-ttu-id="59cf0-142">Elemento WrapTables (formato)</span><span class="sxs-lookup"><span data-stu-id="59cf0-142">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)

[<span data-ttu-id="59cf0-143">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="59cf0-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
