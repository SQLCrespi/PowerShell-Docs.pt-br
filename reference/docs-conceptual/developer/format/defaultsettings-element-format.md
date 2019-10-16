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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363865"
---
# <a name="defaultsettings-element-format"></a><span data-ttu-id="0c9fb-102">Elemento DefaultSettings (formato)</span><span class="sxs-lookup"><span data-stu-id="0c9fb-102">DefaultSettings Element (Format)</span></span>

<span data-ttu-id="0c9fb-103">Define as configurações comuns que se aplicam a todas as exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="0c9fb-103">Defines common settings that apply to all the views of the formatting file.</span></span> <span data-ttu-id="0c9fb-104">As configurações comuns incluem a exibição de erros, o encapsulamento de texto em tabelas, a definição de como as coleções são expandidas e muito mais.</span><span class="sxs-lookup"><span data-stu-id="0c9fb-104">Common settings include displaying errors, wrapping text in tables, defining how collections are expanded, and more.</span></span>

<span data-ttu-id="0c9fb-105">Elemento Configuration (formato) DefaultSettings Element (Format)</span><span class="sxs-lookup"><span data-stu-id="0c9fb-105">Configuration Element (Format) DefaultSettings Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0c9fb-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0c9fb-106">Syntax</span></span>

```xml
<DefaultSettings>
  <ShowError/>
  <DisplayError/>
 <PropertyCountForTable>NumberOfProperties</PropertyCountFortable>
  <WrapTables/>
  <EnumerableExpansions>...</EnumerableExpansions>
</DefaultSettings>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0c9fb-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="0c9fb-107">Attributes and Elements</span></span>

<span data-ttu-id="0c9fb-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `DefaultSettings`.</span><span class="sxs-lookup"><span data-stu-id="0c9fb-108">The following sections describe attributes, child elements, and the parent element of the `DefaultSettings` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0c9fb-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="0c9fb-109">Attributes</span></span>

<span data-ttu-id="0c9fb-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="0c9fb-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0c9fb-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="0c9fb-111">Child Elements</span></span>

|<span data-ttu-id="0c9fb-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="0c9fb-112">Element</span></span>|<span data-ttu-id="0c9fb-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="0c9fb-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0c9fb-114">Elemento DisplayError (Format)</span><span class="sxs-lookup"><span data-stu-id="0c9fb-114">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)|<span data-ttu-id="0c9fb-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="0c9fb-115">Optional element.</span></span><br /><br /> <span data-ttu-id="0c9fb-116">Especifica que a cadeia de caracteres #ERR é exibida quando ocorre um erro durante a exibição de um dado.</span><span class="sxs-lookup"><span data-stu-id="0c9fb-116">Specifies that the string #ERR is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="0c9fb-117">Elemento EnumerableExpansions (Format)</span><span class="sxs-lookup"><span data-stu-id="0c9fb-117">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="0c9fb-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="0c9fb-118">Optional element.</span></span><br /><br /> <span data-ttu-id="0c9fb-119">Define as diferentes maneiras como os objetos .NET são expandidos quando são exibidos em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="0c9fb-119">Defines the different ways that .NET objects are expanded when they are displayed in a view.</span></span>|
|[<span data-ttu-id="0c9fb-120">PropertyCountForTable (formato)</span><span class="sxs-lookup"><span data-stu-id="0c9fb-120">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)|<span data-ttu-id="0c9fb-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="0c9fb-121">Optional element.</span></span><br /><br /> <span data-ttu-id="0c9fb-122">Especifica o número mínimo de propriedades que um objeto deve ter para exibir o objeto em uma exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="0c9fb-122">Specifies the minimum number of properties that an object must have to display the object in a table view.</span></span>|
|[<span data-ttu-id="0c9fb-123">Elemento TextError (formato)</span><span class="sxs-lookup"><span data-stu-id="0c9fb-123">ShowError Element (Format)</span></span>](./showerror-element-format.md)|<span data-ttu-id="0c9fb-124">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="0c9fb-124">Optional element.</span></span><br /><br /> <span data-ttu-id="0c9fb-125">Especifica que o registro de erro completo é exibido quando ocorre um erro durante a exibição de um dado.</span><span class="sxs-lookup"><span data-stu-id="0c9fb-125">Specifies that the full error record is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="0c9fb-126">Elemento WrapTables (Format)</span><span class="sxs-lookup"><span data-stu-id="0c9fb-126">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)|<span data-ttu-id="0c9fb-127">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="0c9fb-127">Optional element.</span></span><br /><br /> <span data-ttu-id="0c9fb-128">Especifica que os dados em uma tabela serão movidos para a próxima linha se não couberem na largura da coluna.</span><span class="sxs-lookup"><span data-stu-id="0c9fb-128">Specifies that data in a table is moved to the next line if it does not fit into the width of the column.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="0c9fb-129">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="0c9fb-129">Parent Elements</span></span>

|<span data-ttu-id="0c9fb-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="0c9fb-130">Element</span></span>|<span data-ttu-id="0c9fb-131">Descrição</span><span class="sxs-lookup"><span data-stu-id="0c9fb-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0c9fb-132">Elemento de configuração</span><span class="sxs-lookup"><span data-stu-id="0c9fb-132">Configuration Element</span></span>](./configuration-element-format.md)|<span data-ttu-id="0c9fb-133">Representa o elemento de nível superior de um arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="0c9fb-133">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0c9fb-134">Comentários</span><span class="sxs-lookup"><span data-stu-id="0c9fb-134">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="0c9fb-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0c9fb-135">See Also</span></span>

[<span data-ttu-id="0c9fb-136">Elemento de configuração</span><span class="sxs-lookup"><span data-stu-id="0c9fb-136">Configuration Element</span></span>](./configuration-element-format.md)

[<span data-ttu-id="0c9fb-137">Elemento DisplayError (Format)</span><span class="sxs-lookup"><span data-stu-id="0c9fb-137">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)

[<span data-ttu-id="0c9fb-138">Elemento EnumerableExpansions (Format)</span><span class="sxs-lookup"><span data-stu-id="0c9fb-138">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)

[<span data-ttu-id="0c9fb-139">PropertyCountForTable (formato)</span><span class="sxs-lookup"><span data-stu-id="0c9fb-139">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)

[<span data-ttu-id="0c9fb-140">Elemento TextError (formato)</span><span class="sxs-lookup"><span data-stu-id="0c9fb-140">ShowError Element (Format)</span></span>](./showerror-element-format.md)

[<span data-ttu-id="0c9fb-141">Elemento WrapTables (Format)</span><span class="sxs-lookup"><span data-stu-id="0c9fb-141">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)

[<span data-ttu-id="0c9fb-142">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c9fb-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
