---
ms.date: 07/29/2020
title: Novos recursos de linguagem no PowerShell 5.0
description: O PowerShell 5.0 trouxe a capacidade de definir classes e outros tipos definidos pelo usuário usando uma sintaxe formal e semântica que são semelhantes a outras linguagens de programação orientadas ao objeto.
ms.openlocfilehash: 31ff54ba6f2800a0680c1a2db3832ca97246973d
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92663312"
---
# <a name="new-language-features-in-powershell-50"></a><span data-ttu-id="7316c-103">Novos recursos de linguagem no PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="7316c-103">New language features in PowerShell 5.0</span></span>

<span data-ttu-id="7316c-104">O PowerShell 5.0 trouxe a capacidade de definir classes e outros tipos definidos pelo usuário usando uma sintaxe formal e semântica que são semelhantes a outras linguagens de programação orientadas ao objeto.</span><span class="sxs-lookup"><span data-stu-id="7316c-104">PowerShell 5.0 added the ability to define classes and other user-defined types using formal syntax and semantics like other object-oriented programming languages.</span></span> <span data-ttu-id="7316c-105">O objetivo é permitir que desenvolvedores e profissionais de TI adotem o PowerShell para uma grande variedade de casos de uso, simplificar o desenvolvimento de artefatos do PowerShell (como recursos DSC) e acelerar a cobertura de superfícies de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="7316c-105">The goal is to enable developers and IT professionals to embrace PowerShell for a wider range of use cases, simplify development of PowerShell artifacts (such as DSC resources), and accelerate coverage of management surfaces.</span></span>

<span data-ttu-id="7316c-106">O PowerShell 5.0 introduz os seguintes novos elementos de linguagem:</span><span class="sxs-lookup"><span data-stu-id="7316c-106">PowerShell 5.0 introduces the following new language elements in PowerShell:</span></span>

### <a name="class-keyword"></a><span data-ttu-id="7316c-107">Palavra-chave class</span><span class="sxs-lookup"><span data-stu-id="7316c-107">Class keyword</span></span>

<span data-ttu-id="7316c-108">A palavra-chave `class` define uma nova classe.</span><span class="sxs-lookup"><span data-stu-id="7316c-108">The `class` keyword defines a new class.</span></span> <span data-ttu-id="7316c-109">Este é um tipo real do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7316c-109">This is a true .NET Framework type.</span></span> <span data-ttu-id="7316c-110">Membros de classe são públicos, mas somente públicos dentro do escopo do módulo.</span><span class="sxs-lookup"><span data-stu-id="7316c-110">Class members are public, but only public within the module scope.</span></span> <span data-ttu-id="7316c-111">Não é possível se referir ao nome de tipo como uma cadeia de caracteres (por exemplo, `New-Object` não funciona), e nesta versão não é possível usar um literal de tipo (por exemplo, `[MyClass]`) fora do arquivo de script ou módulo no qual a classe é definida.</span><span class="sxs-lookup"><span data-stu-id="7316c-111">You can't refer to the type name as a string (for example, `New-Object` doesn't work), and in this release, you can't use a type literal (for example, `[MyClass]`) outside the script or module file in which the class is defined.</span></span>

```powershell
class MyClass
{
    ...
}
```

### <a name="enum-keyword-and-enumerations"></a><span data-ttu-id="7316c-112">Palavra-chave Enum e enumerações</span><span class="sxs-lookup"><span data-stu-id="7316c-112">Enum keyword and enumerations</span></span>

<span data-ttu-id="7316c-113">O suporte à palavra-chave `enum` foi adicionado e usa uma nova linha como o delimitador.</span><span class="sxs-lookup"><span data-stu-id="7316c-113">Support for the `enum` keyword has been added, which uses newline as the delimiter.</span></span> <span data-ttu-id="7316c-114">No momento, não é possível definir um enumerador em relação a si mesmo.</span><span class="sxs-lookup"><span data-stu-id="7316c-114">Currently, you cannot define an enumerator in terms of itself.</span></span> <span data-ttu-id="7316c-115">No entanto, é possível iniciar uma enumeração em relação a outra enumeração, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="7316c-115">However, you can initialize an enum in terms of another enum, as shown in the following example.</span></span> <span data-ttu-id="7316c-116">Além disso, o tipo base não pode ser especificado; ele é sempre `[int]`.</span><span class="sxs-lookup"><span data-stu-id="7316c-116">Also, the base type cannot be specified; it is always `[int]`.</span></span>

```powershell
enum Color2
{
    Yellow = [Color]::Blue
}
```

<span data-ttu-id="7316c-117">Um valor de enumeração deve ser uma constante de tempo de análise.</span><span class="sxs-lookup"><span data-stu-id="7316c-117">An enumerator value must be a parse time constant.</span></span> <span data-ttu-id="7316c-118">Não é possível defini-lo como o resultado de um comando chamado.</span><span class="sxs-lookup"><span data-stu-id="7316c-118">You cannot set it to the result of an invoked command.</span></span>

```powershell
enum MyEnum
{
    Enum1
    Enum2
    Enum3 = 42
    Enum4 = [int]::MaxValue
}
```

<span data-ttu-id="7316c-119">Enums dão suporte a operações aritméticas, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="7316c-119">Enums support arithmetic operations, as shown in the following example.</span></span>

```powershell
enum SomeEnum { Max = 42 }
enum OtherEnum { Max = [SomeEnum]::Max + 1 }
```

### <a name="import-dscresource"></a><span data-ttu-id="7316c-120">Import-DscResource</span><span class="sxs-lookup"><span data-stu-id="7316c-120">Import-DscResource</span></span>

<span data-ttu-id="7316c-121">`Import-DscResource` agora é uma palavra-chave dinâmica real.</span><span class="sxs-lookup"><span data-stu-id="7316c-121">`Import-DscResource` is now a true dynamic keyword.</span></span> <span data-ttu-id="7316c-122">O PowerShell analisa o módulo raiz do módulo especificado pesquisando classes que contêm o atributo **DscResource** .</span><span class="sxs-lookup"><span data-stu-id="7316c-122">PowerShell parses the specified module's root module, searching for classes that contain the **DscResource** attribute.</span></span>

### <a name="implementingassembly"></a><span data-ttu-id="7316c-123">ImplementingAssembly</span><span class="sxs-lookup"><span data-stu-id="7316c-123">ImplementingAssembly</span></span>

<span data-ttu-id="7316c-124">Um novo campo, **ImplementingAssembly** , foi adicionado a **ModuleInfo** .</span><span class="sxs-lookup"><span data-stu-id="7316c-124">A new field, **ImplementingAssembly** , has been added to **ModuleInfo** .</span></span> <span data-ttu-id="7316c-125">Ele é definido como o assembly dinâmico criado para um módulo de script, caso o script defina classes, ou como o assembly carregado para módulos binários.</span><span class="sxs-lookup"><span data-stu-id="7316c-125">It is set to the dynamic assembly created for a script module if the script defines classes, or the loaded assembly for binary modules.</span></span> <span data-ttu-id="7316c-126">Ele não é definido quando **ModuleType** é **Manifest** .</span><span class="sxs-lookup"><span data-stu-id="7316c-126">It is not set when **ModuleType** is **Manifest** .</span></span>

<span data-ttu-id="7316c-127">A reflexão sobre o campo **ImplementingAssembly** descobre recursos em um módulo.</span><span class="sxs-lookup"><span data-stu-id="7316c-127">Reflection on the **ImplementingAssembly** field discovers resources in a module.</span></span> <span data-ttu-id="7316c-128">Isso significa que é possível descobrir recursos escritos no PowerShell ou em outras linguagens gerenciadas.</span><span class="sxs-lookup"><span data-stu-id="7316c-128">This means you can discover resources written in either PowerShell or other managed languages.</span></span>

## <a name="further-reading"></a><span data-ttu-id="7316c-129">Leitura adicional</span><span class="sxs-lookup"><span data-stu-id="7316c-129">Further reading</span></span>

- [<span data-ttu-id="7316c-130">about_Classes</span><span class="sxs-lookup"><span data-stu-id="7316c-130">about_Classes</span></span>](/powershell/module/microsoft.powershell.core/about/about_classes)
- [<span data-ttu-id="7316c-131">about_Enum</span><span class="sxs-lookup"><span data-stu-id="7316c-131">about_Enum</span></span>](/powershell/module/microsoft.powershell.core/about/about_enum)
- [<span data-ttu-id="7316c-132">about_Classes_and_DSC</span><span class="sxs-lookup"><span data-stu-id="7316c-132">about_Classes_and_DSC</span></span>](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc)
