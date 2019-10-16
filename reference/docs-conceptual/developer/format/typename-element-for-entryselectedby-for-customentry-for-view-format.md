---
title: Elemento TypeName para EntrySelectedBy para CustomEntry para exibição (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76548af7-05bd-4d12-bf71-6fb69c434ef2
caps.latest.revision: 10
ms.openlocfilehash: c3dd761cd9b6c468d4833ea35b897ba5d425f598
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368065"
---
# <a name="typename-element-for-entryselectedby-for-customentry-for-view-format"></a><span data-ttu-id="2002d-102">Elemento TypeName para EntrySelectedBy para Controls para CustomEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="2002d-102">TypeName Element for EntrySelectedBy for CustomEntry for View (Format)</span></span>

<span data-ttu-id="2002d-103">Especifica um tipo .NET que usa essa definição do modo de exibição de controle personalizado.</span><span class="sxs-lookup"><span data-stu-id="2002d-103">Specifies a .NET type that uses this definition of the custom control view.</span></span> <span data-ttu-id="2002d-104">Não há nenhum limite para o número de tipos que podem ser especificados para uma definição.</span><span class="sxs-lookup"><span data-stu-id="2002d-104">There is no limit to the number of types that can be specified for a definition.</span></span>

<span data-ttu-id="2002d-105">Elemento de configuração (Format) elemento ViewDefinitions (Format) View element (Format) CustomControl elemento (Format) CustomEntries Element for CustomControl para View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element para CustomEntry para View (Format) TypeName Element for EntrySelectedBy for CustomEntry para View (Format)</span><span class="sxs-lookup"><span data-stu-id="2002d-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format) TypeName Element for EntrySelectedBy for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2002d-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2002d-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2002d-107">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="2002d-107">Attributes and Elements</span></span>

<span data-ttu-id="2002d-108">As seções a seguir descrevem atributos, elementos filho e o elemento pai do elemento `TypeName`.</span><span class="sxs-lookup"><span data-stu-id="2002d-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2002d-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="2002d-109">Attributes</span></span>

<span data-ttu-id="2002d-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="2002d-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2002d-111">Elementos filhos</span><span class="sxs-lookup"><span data-stu-id="2002d-111">Child Elements</span></span>

<span data-ttu-id="2002d-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="2002d-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2002d-113">Elementos pais</span><span class="sxs-lookup"><span data-stu-id="2002d-113">Parent Elements</span></span>

|<span data-ttu-id="2002d-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="2002d-114">Element</span></span>|<span data-ttu-id="2002d-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="2002d-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2002d-116">Elemento EntrySelectedBy para CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="2002d-116">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="2002d-117">Define os tipos .NET que usam essa definição de exibição de controle personalizado ou a condição que deve existir para que essa definição seja usada.</span><span class="sxs-lookup"><span data-stu-id="2002d-117">Defines the .NET types that use this custom control view definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2002d-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="2002d-118">Text Value</span></span>

<span data-ttu-id="2002d-119">Especifique o nome totalmente qualificado do tipo .NET, como `System.IO.DirectoryInfo`.</span><span class="sxs-lookup"><span data-stu-id="2002d-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2002d-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="2002d-120">Remarks</span></span>

<span data-ttu-id="2002d-121">Cada definição de exibição de controle personalizado deve ter pelo menos um nome de tipo, um conjunto de seleção ou uma condição de seleção definida.</span><span class="sxs-lookup"><span data-stu-id="2002d-121">Each custom control view definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="2002d-122">Para obter mais informações sobre os componentes de um modo de exibição de controle personalizado, consulte [criando controles personalizados](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="2002d-122">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2002d-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2002d-123">See Also</span></span>

[<span data-ttu-id="2002d-124">Criando controles personalizados</span><span class="sxs-lookup"><span data-stu-id="2002d-124">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="2002d-125">Elemento EntrySelectedBy para CustomEntry para exibição (formato)</span><span class="sxs-lookup"><span data-stu-id="2002d-125">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="2002d-126">Gravando um arquivo de formatação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="2002d-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
