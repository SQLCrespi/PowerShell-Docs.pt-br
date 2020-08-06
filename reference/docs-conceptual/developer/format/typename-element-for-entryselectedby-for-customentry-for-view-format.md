---
title: Elemento TypeName para EntrySelectedBy para CustomEntry para exibição (formato) | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: f8dc2c808e6eb3d6a7873cdbddc936b95d94c541
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785091"
---
# <a name="typename-element-for-entryselectedby-for-customentry-for-view-format"></a><span data-ttu-id="905fe-102">Elemento TypeName para EntrySelectedBy para Controls para CustomEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="905fe-102">TypeName Element for EntrySelectedBy for CustomEntry for View (Format)</span></span>

<span data-ttu-id="905fe-103">Especifica um tipo .NET que usa essa definição do modo de exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="905fe-103">Specifies a .NET type that uses this definition of the custom control view.</span></span> <span data-ttu-id="905fe-104">Não há nenhum limite para o número de tipos que podem ser especificados para uma definição.</span><span class="sxs-lookup"><span data-stu-id="905fe-104">There is no limit to the number of types that can be specified for a definition.</span></span>

<span data-ttu-id="905fe-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl elemento (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries para o elemento View (Format) EntrySelectedBy para CustomEntry para o elemento View (Format) TypeName para EntrySelectedBy para CustomEntry para View (Format)</span><span class="sxs-lookup"><span data-stu-id="905fe-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format) TypeName Element for EntrySelectedBy for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="905fe-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="905fe-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="905fe-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="905fe-107">Attributes and Elements</span></span>

<span data-ttu-id="905fe-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do `TypeName` elemento.</span><span class="sxs-lookup"><span data-stu-id="905fe-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="905fe-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="905fe-109">Attributes</span></span>

<span data-ttu-id="905fe-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="905fe-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="905fe-111">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="905fe-111">Child Elements</span></span>

<span data-ttu-id="905fe-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="905fe-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="905fe-113">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="905fe-113">Parent Elements</span></span>

|<span data-ttu-id="905fe-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="905fe-114">Element</span></span>|<span data-ttu-id="905fe-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="905fe-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="905fe-116">Elemento EntrySelectedBy para CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="905fe-116">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="905fe-117">Define os tipos .NET que usam essa definição de exibição de controle personalizado ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="905fe-117">Defines the .NET types that use this custom control view definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="905fe-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="905fe-118">Text Value</span></span>

<span data-ttu-id="905fe-119">Especifique o nome totalmente qualificado do tipo .NET, como `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="905fe-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="905fe-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="905fe-120">Remarks</span></span>

<span data-ttu-id="905fe-121">Cada definição de exibição de controle personalizado deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.</span><span class="sxs-lookup"><span data-stu-id="905fe-121">Each custom control view definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="905fe-122">Para obter mais informações sobre os componentes de um modo de exibição de controle personalizado, consulte [criando controles personalizados](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="905fe-122">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="905fe-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="905fe-123">See Also</span></span>

[<span data-ttu-id="905fe-124">Criar controles personalizados</span><span class="sxs-lookup"><span data-stu-id="905fe-124">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="905fe-125">Elemento EntrySelectedBy para CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="905fe-125">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="905fe-126">Escrever um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="905fe-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
