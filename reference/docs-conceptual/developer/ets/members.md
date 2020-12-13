---
ms.date: 07/09/2020
ms.topic: reference
title: Membros da classe do sistema de tipo estendido
description: Membros da classe do sistema de tipo estendido
ms.openlocfilehash: 06488ce423f363a285ab53b21ab45989654346dc
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666834"
---
# <a name="extended-type-system-class-members"></a><span data-ttu-id="10a46-103">Membros da classe do sistema de tipo estendido</span><span class="sxs-lookup"><span data-stu-id="10a46-103">Extended Type System class members</span></span>

<span data-ttu-id="10a46-104">O ETS refere-se a vários tipos diferentes de membros cujos tipos são definidos pela enumeração **PSMemberTypes** .</span><span class="sxs-lookup"><span data-stu-id="10a46-104">ETS refers to a number of different kinds of members whose types are defined by the **PSMemberTypes** enumeration.</span></span> <span data-ttu-id="10a46-105">Esses tipos de membro incluem propriedades, métodos, membros e conjuntos de membros que são definidos por seu próprio tipo CLR.</span><span class="sxs-lookup"><span data-stu-id="10a46-105">These member types include properties, methods, members, and member sets that are each defined by their own CLR type.</span></span> <span data-ttu-id="10a46-106">Por exemplo, uma **NoteProperty** é definida por seu próprio tipo **PSNoteProperty** .</span><span class="sxs-lookup"><span data-stu-id="10a46-106">For example, a **NoteProperty** is defined by its own **PSNoteProperty** type.</span></span> <span data-ttu-id="10a46-107">Esses tipos CLR individuais têm suas próprias propriedades exclusivas e propriedades comuns que são herdadas da [classe PSMemberInfo](/dotnet/api/system.management.automation.psmemberinfo).</span><span class="sxs-lookup"><span data-stu-id="10a46-107">These individual CLR types have both their own unique properties and common properties that are inherited from the [PSMemberInfo class](/dotnet/api/system.management.automation.psmemberinfo).</span></span>

## <a name="the-psmemberinfo-class"></a><span data-ttu-id="10a46-108">A classe PSMemberInfo</span><span class="sxs-lookup"><span data-stu-id="10a46-108">The PSMemberInfo class</span></span>

<span data-ttu-id="10a46-109">A classe **PSMemberInfo** serve como uma classe base para todos os tipos de membro do ETS.</span><span class="sxs-lookup"><span data-stu-id="10a46-109">The **PSMemberInfo** class serves as a base class for all ETS member types.</span></span> <span data-ttu-id="10a46-110">Essa classe fornece as seguintes propriedades de base para todos os tipos CLR de membro.</span><span class="sxs-lookup"><span data-stu-id="10a46-110">This class provides the following base properties to all member CLR types.</span></span>

- <span data-ttu-id="10a46-111">Propriedade **Name** : o nome do membro.</span><span class="sxs-lookup"><span data-stu-id="10a46-111">**Name** property: The name of the member.</span></span> <span data-ttu-id="10a46-112">Esse nome pode ser definido pelo objeto base ou definido pelo PowerShell quando Membros adaptados ou membros estendidos são expostos.</span><span class="sxs-lookup"><span data-stu-id="10a46-112">This name can be defined by the base-object or defined by PowerShell when adapted members or extended members are exposed.</span></span>
- <span data-ttu-id="10a46-113">Propriedade **Value** : o valor retornado do membro específico.</span><span class="sxs-lookup"><span data-stu-id="10a46-113">**Value** property: The value returned from the particular member.</span></span> <span data-ttu-id="10a46-114">Cada tipo de membro define como ele manipula seu valor de membro.</span><span class="sxs-lookup"><span data-stu-id="10a46-114">Each member type defines how it handles its member value.</span></span>
- <span data-ttu-id="10a46-115">Propriedade **TypeNameOfValue** : esse é o nome do tipo CLR do valor que é retornado pela propriedade Value.</span><span class="sxs-lookup"><span data-stu-id="10a46-115">**TypeNameOfValue** property: This is the name of the CLR type of the value that is returned by the Value property.</span></span>

## <a name="accessing-members"></a><span data-ttu-id="10a46-116">Acessando membros</span><span class="sxs-lookup"><span data-stu-id="10a46-116">Accessing members</span></span>

<span data-ttu-id="10a46-117">As coleções de membros podem ser acessadas por meio das propriedades **Members**, **Methods** e **Properties** do objeto **PSObject** .</span><span class="sxs-lookup"><span data-stu-id="10a46-117">Collections of members can be accessed through the **Members**, **Methods**, and **Properties** properties of the **PSObject** object.</span></span>

## <a name="ets-properties"></a><span data-ttu-id="10a46-118">Propriedades do ETS</span><span class="sxs-lookup"><span data-stu-id="10a46-118">ETS properties</span></span>

<span data-ttu-id="10a46-119">As propriedades do ETS são membros que podem ser tratados como uma propriedade.</span><span class="sxs-lookup"><span data-stu-id="10a46-119">ETS properties are members that can be treated as a property.</span></span> <span data-ttu-id="10a46-120">Essencialmente, eles podem aparecer no lado esquerdo de uma expressão.</span><span class="sxs-lookup"><span data-stu-id="10a46-120">Essentially, they can appear on the left-hand side of an expression.</span></span> <span data-ttu-id="10a46-121">Eles incluem propriedades de alias, propriedades de código, propriedades do PowerShell, propriedades de observação e propriedades de script.</span><span class="sxs-lookup"><span data-stu-id="10a46-121">They include alias properties, code properties, PowerShell properties, note properties, and script properties.</span></span> <span data-ttu-id="10a46-122">Para obter mais informações sobre esses tipos de propriedades, consulte [Propriedades do ETS](properties.md).</span><span class="sxs-lookup"><span data-stu-id="10a46-122">For more information about these types of properties, see [ETS properties](properties.md).</span></span>

## <a name="ets-methods"></a><span data-ttu-id="10a46-123">Métodos do ETS</span><span class="sxs-lookup"><span data-stu-id="10a46-123">ETS methods</span></span>

<span data-ttu-id="10a46-124">Os métodos ETS são membros que podem receber argumentos, podem retornar resultados e não podem aparecer no lado esquerdo de uma expressão.</span><span class="sxs-lookup"><span data-stu-id="10a46-124">ETS methods are members that can take arguments, may return results, and cannot appear on the left-hand side of an expression.</span></span> <span data-ttu-id="10a46-125">Eles incluem métodos de código, métodos do PowerShell e métodos de script.</span><span class="sxs-lookup"><span data-stu-id="10a46-125">They include code methods, PowerShell methods, and script methods.</span></span>
<span data-ttu-id="10a46-126">Para obter mais informações sobre esses tipos de métodos, consulte [métodos do ETS](methods.md).</span><span class="sxs-lookup"><span data-stu-id="10a46-126">For more information about these types of methods, see [ETS methods](methods.md).</span></span>
