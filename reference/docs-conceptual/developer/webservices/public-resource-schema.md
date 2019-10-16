---
title: Esquema de recursos públicos | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e67298ee-a773-4402-8afb-d97ad0e030e5
caps.latest.revision: 4
ms.openlocfilehash: c7e20ff0f36e8cab2d414ff2e5924b3359ad9c60
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366265"
---
# <a name="public-resource-schema"></a><span data-ttu-id="fee2f-102">Esquema de recursos públicos</span><span class="sxs-lookup"><span data-stu-id="fee2f-102">Public Resource Schema</span></span>

<span data-ttu-id="fee2f-103">O Management OData usa o MOF para definir recursos e suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="fee2f-103">Management OData uses MOF to define resources and their properties.</span></span> <span data-ttu-id="fee2f-104">As propriedades de uma entidade do Management OData correspondem diretamente às propriedades do tipo gerenciado retornado pelo cmdlet subjacente.</span><span class="sxs-lookup"><span data-stu-id="fee2f-104">The properties of a Management OData entity correspond directly to the properties of the managed type returned by the underlying cmdlet.</span></span>

## <a name="defining-a-resource"></a><span data-ttu-id="fee2f-105">Definindo um recurso</span><span class="sxs-lookup"><span data-stu-id="fee2f-105">Defining a resource</span></span>

<span data-ttu-id="fee2f-106">Cada recurso corresponde a um objeto retornado por um cmdlet do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fee2f-106">Each resource corresponds to an object returned by a Windows PowerShell cmdlet.</span></span> <span data-ttu-id="fee2f-107">No arquivo MOF de recurso público, você define um recurso declarando uma classe.</span><span class="sxs-lookup"><span data-stu-id="fee2f-107">In the public resource MOF file, you define a resource by declaring a class.</span></span> <span data-ttu-id="fee2f-108">A classe consiste em propriedades que correspondem às propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="fee2f-108">The class consists of properties that correspond to the properties of the object.</span></span> <span data-ttu-id="fee2f-109">Por exemplo, no exemplo a seguir, a classe [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) é representada pelo MOF a seguir.</span><span class="sxs-lookup"><span data-stu-id="fee2f-109">For example, in the following example, the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) class is represented by the following MOF.</span></span>

```csharp
class PswsTest_Process
{
    [Key] SInt32 Id;
    [Required] SInt32 BasePriority;
    [Required] SInt32 HandleCount;
    [Required] string MachineName;
    [Required] SInt32 MainWindowHandle;

    ...
};
```

<span data-ttu-id="fee2f-110">Cada nome de propriedade é precedido por um tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="fee2f-110">Each property name is preceded by a data type.</span></span> <span data-ttu-id="fee2f-111">Os tipos de dados neste exemplo correspondem aos tipos de dados CLR primitivos no .NET Framework, mas as propriedades também podem ser referências a outros recursos ou tipos complexos, que são descritos posteriormente.</span><span class="sxs-lookup"><span data-stu-id="fee2f-111">The data types in this example correspond to primitive CLR data types in the .NET Frameworks, but properties can also be references to other resources or complex types, which are both described later.</span></span>

<span data-ttu-id="fee2f-112">O qualificador `Key` indica que uma propriedade é usada para identificar exclusivamente uma instância de recurso.</span><span class="sxs-lookup"><span data-stu-id="fee2f-112">The `Key` qualifier indicates that a property is used to uniquely identify a resource instance.</span></span> <span data-ttu-id="fee2f-113">Um recurso pode ter mais de uma chave.</span><span class="sxs-lookup"><span data-stu-id="fee2f-113">A resource can have more than one key.</span></span>

<span data-ttu-id="fee2f-114">O qualificador `Required` indica que a propriedade é necessária.</span><span class="sxs-lookup"><span data-stu-id="fee2f-114">The `Required` qualifier indicates that the property is required.</span></span> <span data-ttu-id="fee2f-115">Se uma propriedade for rotulada com o qualificador `Key`, ela será considerada necessária e o qualificador de `Required` não será necessário.</span><span class="sxs-lookup"><span data-stu-id="fee2f-115">If a property is labeled with the `Key` qualifier, it is considered to be required, and the `Required` qualifier is not necessary.</span></span>

### <a name="complex-data-types"></a><span data-ttu-id="fee2f-116">Tipos de dados complexos</span><span class="sxs-lookup"><span data-stu-id="fee2f-116">Complex data types</span></span>

<span data-ttu-id="fee2f-117">As propriedades de entidades podem ter tipos de dados complexos.</span><span class="sxs-lookup"><span data-stu-id="fee2f-117">Properties of entities can have complex data types.</span></span> <span data-ttu-id="fee2f-118">Tipos de dados complexos são tipos compostos de outros tipos, semelhantes a structs na linguagem de programação C.</span><span class="sxs-lookup"><span data-stu-id="fee2f-118">Complex data types are types that are made up of other types, similar to structs in the C programming language.</span></span> <span data-ttu-id="fee2f-119">Um tipo complexo é declarado no arquivo MOF como uma classe com o qualificador `ComplexType`, como no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="fee2f-119">A complex type is declared in the MOF file as a class with the `ComplexType` qualifier, as in the following example.</span></span>

```csharp
[ComplexType]
class PswsTest_ProcessModule
{
    String ModuleName;
    String FileName;
};
```

<span data-ttu-id="fee2f-120">Para declarar uma propriedade de entidade como um tipo complexo, declare-a como um tipo `string` com o qualificador `EmbeddedInstance`, incluindo o nome do tipo complexo.</span><span class="sxs-lookup"><span data-stu-id="fee2f-120">To declare an entity property as a complex type, you declare it as a `string` type with the `EmbeddedInstance` qualifier, including the name of the complex type.</span></span> <span data-ttu-id="fee2f-121">O exemplo a seguir mostra a declaração de uma propriedade do tipo `PswsTest_ProcessModule` declarado no exemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="fee2f-121">The following example shows the declaration of a property of the `PswsTest_ProcessModule` type declared in the previous example.</span></span>

```csharp
[Required, EmbeddedInstance("PswsTest_ProcessModule")] String Modules[];
```

### <a name="associating-entities"></a><span data-ttu-id="fee2f-122">Associando entidades</span><span class="sxs-lookup"><span data-stu-id="fee2f-122">Associating entities</span></span>

<span data-ttu-id="fee2f-123">Você pode associar duas entidades usando os qualificadores Association e AssociationClass.</span><span class="sxs-lookup"><span data-stu-id="fee2f-123">You can associate two entities by using the Association and AssociationClass qualifiers.</span></span> <span data-ttu-id="fee2f-124">Para obter mais informações, consulte [associando entidades do Management OData](./associating-management-odata-entities.md).</span><span class="sxs-lookup"><span data-stu-id="fee2f-124">For more information, see [Associating Management OData Entities](./associating-management-odata-entities.md).</span></span>

### <a name="derived-types"></a><span data-ttu-id="fee2f-125">Tipos derivados</span><span class="sxs-lookup"><span data-stu-id="fee2f-125">Derived types</span></span>

<span data-ttu-id="fee2f-126">Você pode derivar um tipo de outro tipo.</span><span class="sxs-lookup"><span data-stu-id="fee2f-126">You can derive a type from another type.</span></span> <span data-ttu-id="fee2f-127">O tipo derivado herda todas as propriedades do tipo do qual deriva, além de quaisquer propriedades explicitamente derivadas.</span><span class="sxs-lookup"><span data-stu-id="fee2f-127">The derived type inherits all of the properties of the type from which it derives in addition to any properties explicitly derived.</span></span> <span data-ttu-id="fee2f-128">O exemplo a seguir mostra uma declaração de tipo e, em seguida, uma declaração de dois tipos derivados desse tipo.</span><span class="sxs-lookup"><span data-stu-id="fee2f-128">The following example shows a type declaration and then a declaration of two types derived from that type.</span></span>

```csharp
Class Product {

    [Key] String ProductName;

};

Class DairyProduct : Product {

    Uint16 PercentFat;
};
Class POPProduct : Product {

    Boolean IsCarbonated;
};
```