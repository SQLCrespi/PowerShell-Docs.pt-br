---
title: Elemento DefaultSettings (formato) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 7da7948fc0814e38a8f3910596e223470ec27d75
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787726"
---
# <a name="defaultsettings-element-format"></a><span data-ttu-id="ff165-102">Elemento DefaultSettings (formato)</span><span class="sxs-lookup"><span data-stu-id="ff165-102">DefaultSettings Element (Format)</span></span>

<span data-ttu-id="ff165-103">Define as configurações comuns que se aplicam a todas as exibições do arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="ff165-103">Defines common settings that apply to all the views of the formatting file.</span></span> <span data-ttu-id="ff165-104">As configurações comuns incluem a exibição de erros, o encapsulamento de texto em tabelas, a definição de como as coleções são expandidas e muito mais.</span><span class="sxs-lookup"><span data-stu-id="ff165-104">Common settings include displaying errors, wrapping text in tables, defining how collections are expanded, and more.</span></span>

<span data-ttu-id="ff165-105">Elemento Configuration (formato) DefaultSettings Element (Format)</span><span class="sxs-lookup"><span data-stu-id="ff165-105">Configuration Element (Format) DefaultSettings Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ff165-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ff165-106">Syntax</span></span>

```xml
<DefaultSettings>
  <ShowError/>
  <DisplayError/>
 <PropertyCountForTable>NumberOfProperties</PropertyCountFortable>
  <WrapTables/>
  <EnumerableExpansions>...</EnumerableExpansions>
</DefaultSettings>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ff165-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="ff165-107">Attributes and Elements</span></span>

<span data-ttu-id="ff165-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `DefaultSettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="ff165-108">The following sections describe attributes, child elements, and the parent element of the `DefaultSettings` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ff165-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="ff165-109">Attributes</span></span>

<span data-ttu-id="ff165-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="ff165-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ff165-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="ff165-111">Child Elements</span></span>

|<span data-ttu-id="ff165-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="ff165-112">Element</span></span>|<span data-ttu-id="ff165-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="ff165-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ff165-114">Elemento DisplayError (formato)</span><span class="sxs-lookup"><span data-stu-id="ff165-114">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)|<span data-ttu-id="ff165-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="ff165-115">Optional element.</span></span><br /><br /> <span data-ttu-id="ff165-116">Especifica que a cadeia de caracteres #ERR é exibida quando ocorre um erro durante a exibição de um dado.</span><span class="sxs-lookup"><span data-stu-id="ff165-116">Specifies that the string #ERR is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="ff165-117">Elemento EnumerableExpansions (formato)</span><span class="sxs-lookup"><span data-stu-id="ff165-117">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="ff165-118">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="ff165-118">Optional element.</span></span><br /><br /> <span data-ttu-id="ff165-119">Define as diferentes maneiras como os objetos .NET são expandidos quando são exibidos em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="ff165-119">Defines the different ways that .NET objects are expanded when they are displayed in a view.</span></span>|
|[<span data-ttu-id="ff165-120">PropertyCountForTable (formato)</span><span class="sxs-lookup"><span data-stu-id="ff165-120">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)|<span data-ttu-id="ff165-121">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="ff165-121">Optional element.</span></span><br /><br /> <span data-ttu-id="ff165-122">Especifica o número mínimo de propriedades que um objeto deve ter para exibir o objeto em uma exibição de tabela.</span><span class="sxs-lookup"><span data-stu-id="ff165-122">Specifies the minimum number of properties that an object must have to display the object in a table view.</span></span>|
|[<span data-ttu-id="ff165-123">Elemento ShowError (formato)</span><span class="sxs-lookup"><span data-stu-id="ff165-123">ShowError Element (Format)</span></span>](./showerror-element-format.md)|<span data-ttu-id="ff165-124">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="ff165-124">Optional element.</span></span><br /><br /> <span data-ttu-id="ff165-125">Especifica que o registro de erro completo é exibido quando ocorre um erro durante a exibição de um dado.</span><span class="sxs-lookup"><span data-stu-id="ff165-125">Specifies that the full error record is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="ff165-126">Elemento WrapTables (formato)</span><span class="sxs-lookup"><span data-stu-id="ff165-126">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)|<span data-ttu-id="ff165-127">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="ff165-127">Optional element.</span></span><br /><br /> <span data-ttu-id="ff165-128">Especifica que os dados em uma tabela serão movidos para a próxima linha se não couberem na largura da coluna.</span><span class="sxs-lookup"><span data-stu-id="ff165-128">Specifies that data in a table is moved to the next line if it does not fit into the width of the column.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ff165-129">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="ff165-129">Parent Elements</span></span>

|<span data-ttu-id="ff165-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="ff165-130">Element</span></span>|<span data-ttu-id="ff165-131">Descrição</span><span class="sxs-lookup"><span data-stu-id="ff165-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ff165-132">Elemento de configuração</span><span class="sxs-lookup"><span data-stu-id="ff165-132">Configuration Element</span></span>](./configuration-element-format.md)|<span data-ttu-id="ff165-133">Representa o elemento de nível superior de um arquivo de formatação.</span><span class="sxs-lookup"><span data-stu-id="ff165-133">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ff165-134">Comentários</span><span class="sxs-lookup"><span data-stu-id="ff165-134">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="ff165-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ff165-135">See Also</span></span>

[<span data-ttu-id="ff165-136">Elemento de configuração</span><span class="sxs-lookup"><span data-stu-id="ff165-136">Configuration Element</span></span>](./configuration-element-format.md)

[<span data-ttu-id="ff165-137">Elemento DisplayError (formato)</span><span class="sxs-lookup"><span data-stu-id="ff165-137">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)

[<span data-ttu-id="ff165-138">Elemento EnumerableExpansions (formato)</span><span class="sxs-lookup"><span data-stu-id="ff165-138">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)

[<span data-ttu-id="ff165-139">PropertyCountForTable (formato)</span><span class="sxs-lookup"><span data-stu-id="ff165-139">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)

[<span data-ttu-id="ff165-140">Elemento ShowError (formato)</span><span class="sxs-lookup"><span data-stu-id="ff165-140">ShowError Element (Format)</span></span>](./showerror-element-format.md)

[<span data-ttu-id="ff165-141">Elemento WrapTables (formato)</span><span class="sxs-lookup"><span data-stu-id="ff165-141">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)

[<span data-ttu-id="ff165-142">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="ff165-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
