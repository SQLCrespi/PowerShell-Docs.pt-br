---
title: Elemento DefaultSettings (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41c56499-ee20-4821-830a-478fdcc33f83
caps.latest.revision: 11
ms.openlocfilehash: bc95c62222eb2806f92499257a397c2e4ec5dbab
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363865"
---
# <a name="defaultsettings-element-format"></a><span data-ttu-id="105a5-102">Elemento DefaultSettings (formato)</span><span class="sxs-lookup"><span data-stu-id="105a5-102">DefaultSettings Element (Format)</span></span>

<span data-ttu-id="105a5-103">Define as configurações comuns que se aplicam a todas as exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="105a5-103">Defines common settings that apply to all the views of the formatting file.</span></span> <span data-ttu-id="105a5-104">As configurações comuns incluem a exibição de erros, o encapsulamento de texto em tabelas, a definição de como as coleções são expandidas e muito mais.</span><span class="sxs-lookup"><span data-stu-id="105a5-104">Common settings include displaying errors, wrapping text in tables, defining how collections are expanded, and more.</span></span>

<span data-ttu-id="105a5-105">Elemento Configuration (formato) DefaultSettings Element (Format)</span><span class="sxs-lookup"><span data-stu-id="105a5-105">Configuration Element (Format) DefaultSettings Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="105a5-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="105a5-106">Syntax</span></span>

```xml
<DefaultSettings>
  <ShowError/>
  <DisplayError/>
 <PropertyCountForTable>NumberOfProperties</PropertyCountFortable>
  <WrapTables/>
  <EnumerableExpansions>...</EnumerableExpansions>
</DefaultSettings>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="105a5-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="105a5-107">Attributes and Elements</span></span>

<span data-ttu-id="105a5-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `DefaultSettings`.</span><span class="sxs-lookup"><span data-stu-id="105a5-108">The following sections describe attributes, child elements, and the parent element of the `DefaultSettings` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="105a5-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="105a5-109">Attributes</span></span>

<span data-ttu-id="105a5-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="105a5-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="105a5-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="105a5-111">Child Elements</span></span>

|<span data-ttu-id="105a5-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="105a5-112">Element</span></span>|<span data-ttu-id="105a5-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="105a5-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="105a5-114">Elemento DisplayError (Format)</span><span class="sxs-lookup"><span data-stu-id="105a5-114">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)|<span data-ttu-id="105a5-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="105a5-115">Optional element.</span></span><br /><br /> <span data-ttu-id="105a5-116">Especifica que a cadeia de caracteres #ERR é exibida quando ocorre um erro durante a exibição de um dado.</span><span class="sxs-lookup"><span data-stu-id="105a5-116">Specifies that the string #ERR is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="105a5-117">Elemento EnumerableExpansions (Format)</span><span class="sxs-lookup"><span data-stu-id="105a5-117">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="105a5-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="105a5-118">Optional element.</span></span><br /><br /> <span data-ttu-id="105a5-119">Define as diferentes maneiras como os objetos .NET são expandidos quando são exibidos em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="105a5-119">Defines the different ways that .NET objects are expanded when they are displayed in a view.</span></span>|
|[<span data-ttu-id="105a5-120">PropertyCountForTable (formato)</span><span class="sxs-lookup"><span data-stu-id="105a5-120">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)|<span data-ttu-id="105a5-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="105a5-121">Optional element.</span></span><br /><br /> <span data-ttu-id="105a5-122">Especifica o número mínimo de propriedades que um objeto deve ter para exibir o objeto em uma exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="105a5-122">Specifies the minimum number of properties that an object must have to display the object in a table view.</span></span>|
|[<span data-ttu-id="105a5-123">Elemento TextError (formato)</span><span class="sxs-lookup"><span data-stu-id="105a5-123">ShowError Element (Format)</span></span>](./showerror-element-format.md)|<span data-ttu-id="105a5-124">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="105a5-124">Optional element.</span></span><br /><br /> <span data-ttu-id="105a5-125">Especifica que o registro de erro completo é exibido quando ocorre um erro durante a exibição de um dado.</span><span class="sxs-lookup"><span data-stu-id="105a5-125">Specifies that the full error record is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="105a5-126">Elemento WrapTables (Format)</span><span class="sxs-lookup"><span data-stu-id="105a5-126">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)|<span data-ttu-id="105a5-127">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="105a5-127">Optional element.</span></span><br /><br /> <span data-ttu-id="105a5-128">Especifica que os dados em uma tabela serão movidos para a próxima linha se não couberem na largura da coluna.</span><span class="sxs-lookup"><span data-stu-id="105a5-128">Specifies that data in a table is moved to the next line if it does not fit into the width of the column.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="105a5-129">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="105a5-129">Parent Elements</span></span>

|<span data-ttu-id="105a5-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="105a5-130">Element</span></span>|<span data-ttu-id="105a5-131">Descrição</span><span class="sxs-lookup"><span data-stu-id="105a5-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="105a5-132">Elemento de configuração</span><span class="sxs-lookup"><span data-stu-id="105a5-132">Configuration Element</span></span>](./configuration-element-format.md)|<span data-ttu-id="105a5-133">Representa o elemento de nível superior de um arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="105a5-133">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="105a5-134">Comentários</span><span class="sxs-lookup"><span data-stu-id="105a5-134">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="105a5-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="105a5-135">See Also</span></span>

[<span data-ttu-id="105a5-136">Elemento de configuração</span><span class="sxs-lookup"><span data-stu-id="105a5-136">Configuration Element</span></span>](./configuration-element-format.md)

[<span data-ttu-id="105a5-137">Elemento DisplayError (Format)</span><span class="sxs-lookup"><span data-stu-id="105a5-137">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)

[<span data-ttu-id="105a5-138">Elemento EnumerableExpansions (Format)</span><span class="sxs-lookup"><span data-stu-id="105a5-138">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)

[<span data-ttu-id="105a5-139">PropertyCountForTable (formato)</span><span class="sxs-lookup"><span data-stu-id="105a5-139">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)

[<span data-ttu-id="105a5-140">Elemento TextError (formato)</span><span class="sxs-lookup"><span data-stu-id="105a5-140">ShowError Element (Format)</span></span>](./showerror-element-format.md)

[<span data-ttu-id="105a5-141">Elemento WrapTables (Format)</span><span class="sxs-lookup"><span data-stu-id="105a5-141">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)

[<span data-ttu-id="105a5-142">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="105a5-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
