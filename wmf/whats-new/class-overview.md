---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
title: Criando tipos personalizados usando classes do PowerShell
ms.openlocfilehash: c2c50fb65ce4931fcf6ae529b4146df391c831c4
ms.sourcegitcommit: bc42c9166857147a1ecf9924b718d4a48eb901e3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2019
ms.locfileid: "66470942"
---
# <a name="creating-custom-types-using-powershell-classes"></a><span data-ttu-id="4d373-103">Criando tipos personalizados usando classes do PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d373-103">Creating Custom Types using PowerShell Classes</span></span>

<span data-ttu-id="4d373-104">O PowerShell 5.0 trouxe a capacidade de definir classes e outros tipos definidos pelo usuário usando uma sintaxe formal e semântica que são semelhantes a outras linguagens de programação orientadas ao objeto.</span><span class="sxs-lookup"><span data-stu-id="4d373-104">PowerShell 5.0 added the ability to define classes and other user-defined types using formal syntax and semantics like other object-oriented programming languages.</span></span> <span data-ttu-id="4d373-105">O objetivo é permitir que desenvolvedores e profissionais de TI adotem o PowerShell para uma grande variedade de casos de uso, simplificar o desenvolvimento de artefatos do PowerShell (como recursos DSC) e acelerar a cobertura de superfícies de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="4d373-105">The goal is to enable developers and IT professionals to embrace PowerShell for a wider range of use cases, simplify development of PowerShell artifacts (such as DSC resources), and accelerate coverage of management surfaces.</span></span>

## <a name="supported-scenarios-in-this-release"></a><span data-ttu-id="4d373-106">Cenários com suporte nesta versão</span><span class="sxs-lookup"><span data-stu-id="4d373-106">Supported scenarios in this release</span></span>

- <span data-ttu-id="4d373-107">Definir recursos DSC e os tipos associados usando a linguagem do PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d373-107">Define DSC resources and their associated types by using the PowerShell language</span></span>
- <span data-ttu-id="4d373-108">Definir tipos personalizados no PowerShell usando constructos de programação orientada a objeto conhecidos, como classes, propriedades, métodos, etc.</span><span class="sxs-lookup"><span data-stu-id="4d373-108">Define custom types in PowerShell by using familiar object-oriented programming constructs, such as classes, properties, methods, etc.</span></span>
- <span data-ttu-id="4d373-109">Suporte à herança com classe no PowerShell e no recurso DSC de classe base</span><span class="sxs-lookup"><span data-stu-id="4d373-109">Inheritance support with class in PowerShell and class base DSC resource</span></span>
- <span data-ttu-id="4d373-110">Depurar tipos usando a linguagem do PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d373-110">Debug types by using the PowerShell language</span></span>
- <span data-ttu-id="4d373-111">Gerar e manipular exceções usando mecanismos formais e no nível certo</span><span class="sxs-lookup"><span data-stu-id="4d373-111">Generate and handle exceptions by using formal mechanisms, and at the right level</span></span>

## <a name="declare-base-class"></a><span data-ttu-id="4d373-112">Declarar a classe base</span><span class="sxs-lookup"><span data-stu-id="4d373-112">Declare Base Class</span></span>

<span data-ttu-id="4d373-113">É possível declarar uma classe do PowerShell como um tipo base para outra classe do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d373-113">You can declare a PowerShell class as a base type for another PowerShell class.</span></span>

```powershell
class bar
{
   [int]foo()
       {
           return 100500
       }
}

class baz : bar {}

[baz]::new().foo() # return 100500
```

<span data-ttu-id="4d373-114">Também é possível usar os tipos existentes do .NET Framework como classes base:</span><span class="sxs-lookup"><span data-stu-id="4d373-114">You can also use existing .NET Framework types as base classes:</span></span>

```powershell
class MyIntList : system.collections.generic.list[int]
{

}

$list = [MyIntList]::new()

$list.Add(100)

$list[0] # return 100
```

### <a name="call-base-class-constructor"></a><span data-ttu-id="4d373-115">Chamar o construtor de classe base</span><span class="sxs-lookup"><span data-stu-id="4d373-115">Call Base Class Constructor</span></span>

<span data-ttu-id="4d373-116">Para chamar um construtor de classe base desde uma subclasse, use a palavra-chave **base**:</span><span class="sxs-lookup"><span data-stu-id="4d373-116">To call a base class constructor from a subclass, use the keyword **base**:</span></span>

```powershell
class A
{
    [int]$a

    A([int]$a)
    {
        $this.a = $a
    }
}

class B : A
{
    B() : base(103) {}
}

[B]::new().a # return 103
```

<span data-ttu-id="4d373-117">Se uma classe base tiver um construtor padrão (sem parâmetros), será possível omitir uma chamada explícita de construtor:</span><span class="sxs-lookup"><span data-stu-id="4d373-117">If a base class has a default (no parameter) constructor, you can omit an explicit constructor call:</span></span>

```powershell
class C : B
{
    C([int]$c) {}
}
```

### <a name="call-base-class-method"></a><span data-ttu-id="4d373-118">Chamar o método de classe base</span><span class="sxs-lookup"><span data-stu-id="4d373-118">Call Base Class Method</span></span>

<span data-ttu-id="4d373-119">É possível substituir os métodos existentes nas subclasses.</span><span class="sxs-lookup"><span data-stu-id="4d373-119">You can override existing methods in subclasses.</span></span> <span data-ttu-id="4d373-120">Para fazer isso, declare métodos usando o mesmo nome e a mesma assinatura:</span><span class="sxs-lookup"><span data-stu-id="4d373-120">To do this, declare methods by using the same name and signature:</span></span>

```powershell
class baseClass
{
    [int]foo() {return 100500}
}

class childClass1 : baseClass
{
    [int]foo() {return 200600}
}

[childClass1]::new().foo() # return 200600
```

<span data-ttu-id="4d373-121">Para chamar métodos de classe base a partir de implementações substituídas, transmita para a classe base (`[baseClass]$this`) na chamada:</span><span class="sxs-lookup"><span data-stu-id="4d373-121">To call base class methods from overridden implementations, cast to the base class (`[baseClass]$this`) on invocation:</span></span>

```powershell
class childClass2 : baseClass
{
    [int]foo()
    {
        return 3 * ([baseClass]$this).foo()
    }
}

[childClass2]::new().foo() # return 301500
```

<span data-ttu-id="4d373-122">Todos os métodos do PowerShell são virtuais.</span><span class="sxs-lookup"><span data-stu-id="4d373-122">All PowerShell methods are virtual.</span></span> <span data-ttu-id="4d373-123">É possível ocultar métodos não virtuais do .NET em uma subclasse usando a mesma sintaxe que você usaria para uma substituição declarando os métodos com o mesmo nome e a mesma assinatura.</span><span class="sxs-lookup"><span data-stu-id="4d373-123">You can hide non-virtual .NET methods in a subclass by using the same syntax as you do for an override, by declaring methods with same name and signature.</span></span>

```powershell
class MyIntList : system.collections.generic.list[int]
{
    # Add is final in system.collections.generic.list
    [void] Add([int]$arg)
    {
        ([system.collections.generic.list[int]]$this).Add($arg * 2)
    }
}

$list = [MyIntList]::new()
$list.Add(100)
$list[0] # return 200
```

### <a name="declare-implemented-interface"></a><span data-ttu-id="4d373-124">Declarar a interface implementada</span><span class="sxs-lookup"><span data-stu-id="4d373-124">Declare Implemented Interface</span></span>

<span data-ttu-id="4d373-125">Será possível declarar interfaces implementadas após tipos base, ou imediatamente após dois-pontos (:), se não houver nenhum tipo base especificado.</span><span class="sxs-lookup"><span data-stu-id="4d373-125">You can declare implemented interfaces after base types, or immediately after a colon (:), if there is no base type specified.</span></span> <span data-ttu-id="4d373-126">Separe todos os nomes de tipo usando vírgulas.</span><span class="sxs-lookup"><span data-stu-id="4d373-126">Separate all type names by using commas.</span></span> <span data-ttu-id="4d373-127">Isso é semelhante à sintaxe do C#.</span><span class="sxs-lookup"><span data-stu-id="4d373-127">It's similar to C# syntax.</span></span>

```powershell
class MyComparable : system.IComparable
{
    [int] CompareTo([object] $obj)
    {
        return 0;
    }
}

class MyComparableBar : bar, system.IComparable
{
    [int] CompareTo([object] $obj)
    {
        return 0;
    }
}
```

## <a name="new-language-features-in-powershell-50"></a><span data-ttu-id="4d373-128">Novos recursos de linguagem no PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="4d373-128">New language features in PowerShell 5.0</span></span>

<span data-ttu-id="4d373-129">O PowerShell 5.0 introduz os seguintes novos elementos de linguagem:</span><span class="sxs-lookup"><span data-stu-id="4d373-129">PowerShell 5.0 introduces the following new language elements in PowerShell:</span></span>

### <a name="class-keyword"></a><span data-ttu-id="4d373-130">Palavra-chave class</span><span class="sxs-lookup"><span data-stu-id="4d373-130">Class keyword</span></span>

<span data-ttu-id="4d373-131">A palavra-chave `class` define uma nova classe.</span><span class="sxs-lookup"><span data-stu-id="4d373-131">The `class` keyword defines a new class.</span></span> <span data-ttu-id="4d373-132">Este é um tipo real do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4d373-132">This is a true .NET Framework type.</span></span> <span data-ttu-id="4d373-133">Membros de classe são públicos, mas somente públicos dentro do escopo do módulo.</span><span class="sxs-lookup"><span data-stu-id="4d373-133">Class members are public, but only public within the module scope.</span></span> <span data-ttu-id="4d373-134">Não é possível se referir ao nome de tipo como uma cadeia de caracteres (por exemplo, `New-Object` não funciona), e nesta versão não é possível usar um literal de tipo (por exemplo, `[MyClass]`) fora do arquivo de script ou módulo no qual a classe é definida.</span><span class="sxs-lookup"><span data-stu-id="4d373-134">You can't refer to the type name as a string (for example, `New-Object` doesn't work), and in this release, you can't use a type literal (for example, `[MyClass]`) outside the script or module file in which the class is defined.</span></span>

```powershell
class MyClass
{
    ...
}
```

### <a name="enum-keyword-and-enumerations"></a><span data-ttu-id="4d373-135">Palavra-chave Enum e enumerações</span><span class="sxs-lookup"><span data-stu-id="4d373-135">Enum keyword and enumerations</span></span>

<span data-ttu-id="4d373-136">O suporte à palavra-chave `enum` foi adicionado e usa uma nova linha como o delimitador.</span><span class="sxs-lookup"><span data-stu-id="4d373-136">Support for the `enum` keyword has been added, which uses newline as the delimiter.</span></span> <span data-ttu-id="4d373-137">No momento, não é possível definir um enumerador em relação a si mesmo.</span><span class="sxs-lookup"><span data-stu-id="4d373-137">Currently, you cannot define an enumerator in terms of itself.</span></span> <span data-ttu-id="4d373-138">No entanto, é possível iniciar uma enumeração em relação a outra enumeração, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="4d373-138">However, you can initialize an enum in terms of another enum, as shown in the following example.</span></span> <span data-ttu-id="4d373-139">Além disso, o tipo base não pode ser especificado; ele é sempre `[int]`.</span><span class="sxs-lookup"><span data-stu-id="4d373-139">Also, the base type cannot be specified; it is always `[int]`.</span></span>

```powershell
enum Color2
{
    Yellow = [Color]::Blue
}
```

<span data-ttu-id="4d373-140">Um valor de enumeração deve ser uma constante de tempo de análise.</span><span class="sxs-lookup"><span data-stu-id="4d373-140">An enumerator value must be a parse time constant.</span></span> <span data-ttu-id="4d373-141">Não é possível defini-lo como o resultado de um comando chamado.</span><span class="sxs-lookup"><span data-stu-id="4d373-141">You cannot set it to the result of an invoked command.</span></span>

```powershell
enum MyEnum
{
    Enum1
    Enum2
    Enum3 = 42
    Enum4 = [int]::MaxValue
}
```

<span data-ttu-id="4d373-142">Enums dão suporte a operações aritméticas, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="4d373-142">Enums support arithmetic operations, as shown in the following example.</span></span>

```powershell
enum SomeEnum { Max = 42 }
enum OtherEnum { Max = [SomeEnum]::Max + 1 }
```

### <a name="import-dscresource"></a><span data-ttu-id="4d373-143">Import-DscResource</span><span class="sxs-lookup"><span data-stu-id="4d373-143">Import-DscResource</span></span>

<span data-ttu-id="4d373-144">`Import-DscResource` agora é uma palavra-chave dinâmica real.</span><span class="sxs-lookup"><span data-stu-id="4d373-144">`Import-DscResource` is now a true dynamic keyword.</span></span> <span data-ttu-id="4d373-145">O PowerShell analisa o módulo raiz do módulo especificado pesquisando classes que contêm o atributo **DscResource**.</span><span class="sxs-lookup"><span data-stu-id="4d373-145">PowerShell parses the specified module's root module, searching for classes that contain the **DscResource** attribute.</span></span>

### <a name="implementingassembly"></a><span data-ttu-id="4d373-146">ImplementingAssembly</span><span class="sxs-lookup"><span data-stu-id="4d373-146">ImplementingAssembly</span></span>

<span data-ttu-id="4d373-147">Um novo campo, **ImplementingAssembly**, foi adicionado a **ModuleInfo**.</span><span class="sxs-lookup"><span data-stu-id="4d373-147">A new field, **ImplementingAssembly**, has been added to **ModuleInfo**.</span></span> <span data-ttu-id="4d373-148">Ele é definido como o assembly dinâmico criado para um módulo de script, caso o script defina classes, ou como o assembly carregado para módulos binários.</span><span class="sxs-lookup"><span data-stu-id="4d373-148">It is set to the dynamic assembly created for a script module if the script defines classes, or the loaded assembly for binary modules.</span></span> <span data-ttu-id="4d373-149">Ele não é definido quando **ModuleType** é **Manifest**.</span><span class="sxs-lookup"><span data-stu-id="4d373-149">It is not set when **ModuleType** is **Manifest**.</span></span>

<span data-ttu-id="4d373-150">A reflexão sobre o campo **ImplementingAssembly** descobre recursos em um módulo.</span><span class="sxs-lookup"><span data-stu-id="4d373-150">Reflection on the **ImplementingAssembly** field discovers resources in a module.</span></span> <span data-ttu-id="4d373-151">Isso significa que é possível descobrir recursos escritos no PowerShell ou em outras linguagens gerenciadas.</span><span class="sxs-lookup"><span data-stu-id="4d373-151">This means you can discover resources written in either PowerShell or other managed languages.</span></span>

<span data-ttu-id="4d373-152">Campos com inicializadores:</span><span class="sxs-lookup"><span data-stu-id="4d373-152">Fields with initializers:</span></span>

```powershell
[int] $i = 5
```

<span data-ttu-id="4d373-153">`Static` é compatível.</span><span class="sxs-lookup"><span data-stu-id="4d373-153">`Static` is supported.</span></span> <span data-ttu-id="4d373-154">Ele funciona como um atributo, como as restrições de tipo.</span><span class="sxs-lookup"><span data-stu-id="4d373-154">It works like an attribute, as do the type constraints.</span></span> <span data-ttu-id="4d373-155">Pode ser especificado em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="4d373-155">It can be specified in any order.</span></span>

```powershell
static [int] $count = 0
```

<span data-ttu-id="4d373-156">Um tipo é opcional.</span><span class="sxs-lookup"><span data-stu-id="4d373-156">A type is optional.</span></span>

```powershell
$s = "hello"
```

<span data-ttu-id="4d373-157">Todos os membros são públicos.</span><span class="sxs-lookup"><span data-stu-id="4d373-157">All members are public.</span></span>

### <a name="constructors-and-instantiation"></a><span data-ttu-id="4d373-158">Construtores e instanciação</span><span class="sxs-lookup"><span data-stu-id="4d373-158">Constructors and instantiation</span></span>

<span data-ttu-id="4d373-159">As classes do PowerShell podem ter construtores.</span><span class="sxs-lookup"><span data-stu-id="4d373-159">PowerShell classes can have constructors.</span></span> <span data-ttu-id="4d373-160">Elas têm o mesmo nome que sua classe.</span><span class="sxs-lookup"><span data-stu-id="4d373-160">They have the same name as their class.</span></span> <span data-ttu-id="4d373-161">Os construtores podem ser sobrecarregados.</span><span class="sxs-lookup"><span data-stu-id="4d373-161">Constructors can be overloaded.</span></span> <span data-ttu-id="4d373-162">Há suporte para construtores estáticos.</span><span class="sxs-lookup"><span data-stu-id="4d373-162">Static constructors are supported.</span></span> <span data-ttu-id="4d373-163">As propriedades com expressões de inicialização são inicializadas antes da execução de qualquer código em um construtor.</span><span class="sxs-lookup"><span data-stu-id="4d373-163">Properties with initialization expressions are initialized before running any code in a constructor.</span></span> <span data-ttu-id="4d373-164">As propriedades estáticas são inicializadas antes do corpo de um construtor estático, e as propriedades de instância são inicializadas antes do corpo do construtor não estático.</span><span class="sxs-lookup"><span data-stu-id="4d373-164">Static properties are initialized before the body of a static constructor, and instance properties are initialized before the body of the non-static constructor.</span></span> <span data-ttu-id="4d373-165">Atualmente, não há nenhuma sintaxe para chamar um construtor de outro construtor [como a sintaxe do C\# ": this()"].</span><span class="sxs-lookup"><span data-stu-id="4d373-165">Currently, there is no syntax for calling a constructor from another constructor (like the C\# syntax ": this()").</span></span> <span data-ttu-id="4d373-166">A solução alternativa é definir um método `Init()` comum.</span><span class="sxs-lookup"><span data-stu-id="4d373-166">The workaround is to define a common `Init()` method.</span></span>

#### <a name="creating-instances"></a><span data-ttu-id="4d373-167">Criando instâncias</span><span class="sxs-lookup"><span data-stu-id="4d373-167">Creating instances</span></span>

> [!NOTE]
> <span data-ttu-id="4d373-168">No PowerShell 5.0, `New-Object` não funciona com classes definidas no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d373-168">In PowerShell 5.0, `New-Object` does not work with classes defined in PowerShell.</span></span> <span data-ttu-id="4d373-169">Além disso, o nome de tipo é visível apenas lexicalmente, o que significa que ele não é visível fora do módulo ou do script que define a classe.</span><span class="sxs-lookup"><span data-stu-id="4d373-169">Also, the type name is only visible lexically, meaning it is not visible outside of the module or script that defines the class.</span></span> <span data-ttu-id="4d373-170">As funções podem retornar instâncias de uma classe definida no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d373-170">Functions can return instances of a class defined in PowerShell.</span></span> <span data-ttu-id="4d373-171">Essas instâncias funcionam fora do módulo ou script.</span><span class="sxs-lookup"><span data-stu-id="4d373-171">Those instances work outside of the module or script.</span></span>

1. <span data-ttu-id="4d373-172">Criando uma instância usando o construtor padrão.</span><span class="sxs-lookup"><span data-stu-id="4d373-172">Instantiating by using the default constructor.</span></span>

   ```powershell
   $a = [MyClass]::new()
   ```

1. <span data-ttu-id="4d373-173">Chamando um construtor com um parâmetro</span><span class="sxs-lookup"><span data-stu-id="4d373-173">Calling a constructor with a parameter</span></span>

   ```powershell
   $b = [MyClass]::new(42)
   ```

1. <span data-ttu-id="4d373-174">Transmitir uma matriz para um construtor com vários parâmetros.</span><span class="sxs-lookup"><span data-stu-id="4d373-174">Passing an array to a constructor with multiple parameters.</span></span>

   ```powershell
   $c = [MyClass]::new(@(42,43,44), "Hello")
   ```

<span data-ttu-id="4d373-175">O método pseudoestático chamado `new()` funciona com tipos do .NET, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="4d373-175">The pseudo-static method `new()` works with .NET types, as shown in the following example.</span></span>

```powershell
[hashtable]::new()
```

#### <a name="discovering-constructors"></a><span data-ttu-id="4d373-176">Descobrindo construtores</span><span class="sxs-lookup"><span data-stu-id="4d373-176">Discovering constructors</span></span>

<span data-ttu-id="4d373-177">Agora você pode ver as sobrecargas do construtor com `Get-Member` ou conforme mostrado neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="4d373-177">You can now see constructor overloads with `Get-Member`, or as shown in this example:</span></span>

```powershell
PS> [hashtable]::new
OverloadDefinitions
-------------------
hashtable new()
hashtable new(int capacity)
hashtable new(int capacity, float loadFactor)
```

<span data-ttu-id="4d373-178">`Get-Member -Static` lista os construtores, para que seja possível exibir sobrecargas como qualquer outro método.</span><span class="sxs-lookup"><span data-stu-id="4d373-178">`Get-Member -Static` lists constructors, so you can view overloads like any other method.</span></span> <span data-ttu-id="4d373-179">O desempenho dessa sintaxe também é consideravelmente mais rápido do que o de `New-Object`.</span><span class="sxs-lookup"><span data-stu-id="4d373-179">The performance of this syntax is also considerably faster than `New-Object`.</span></span>

### <a name="methods"></a><span data-ttu-id="4d373-180">Métodos</span><span class="sxs-lookup"><span data-stu-id="4d373-180">Methods</span></span>

<span data-ttu-id="4d373-181">Um método de classe do PowerShell é implementado como um **ScriptBlock** que tem apenas um bloco end.</span><span class="sxs-lookup"><span data-stu-id="4d373-181">A PowerShell class method is implemented as a **ScriptBlock** that has only an end block.</span></span> <span data-ttu-id="4d373-182">Todos os métodos são públicos.</span><span class="sxs-lookup"><span data-stu-id="4d373-182">All methods are public.</span></span> <span data-ttu-id="4d373-183">Veja a seguir um exemplo de definição de um método chamado **DoSomething**.</span><span class="sxs-lookup"><span data-stu-id="4d373-183">The following shows an example of defining a method named **DoSomething**.</span></span>

```powershell
class MyClass
{
    DoSomething($x)
    {
        $this._doSomething($x) # method syntax
    }
    private _doSomething($a) {}
}
```

<span data-ttu-id="4d373-184">Invocação de método:</span><span class="sxs-lookup"><span data-stu-id="4d373-184">Method invocation:</span></span>

```powershell
$b = [MyClass]::new()
$b.DoSomething(42)
```

<span data-ttu-id="4d373-185">Também há suporte para métodos sobrecarregados.</span><span class="sxs-lookup"><span data-stu-id="4d373-185">Overloaded methods are also supported.</span></span>

### <a name="properties"></a><span data-ttu-id="4d373-186">Propriedades</span><span class="sxs-lookup"><span data-stu-id="4d373-186">Properties</span></span>

<span data-ttu-id="4d373-187">Todas as propriedades são públicas.</span><span class="sxs-lookup"><span data-stu-id="4d373-187">All properties are public.</span></span> <span data-ttu-id="4d373-188">As propriedades exigem uma nova linha ou um ponto-e-vírgula.</span><span class="sxs-lookup"><span data-stu-id="4d373-188">Properties require either a newline or semicolon.</span></span> <span data-ttu-id="4d373-189">Se nenhum tipo de objeto for especificado, o tipo de propriedade será o objeto.</span><span class="sxs-lookup"><span data-stu-id="4d373-189">If no object type is specified, the property type is object.</span></span>

<span data-ttu-id="4d373-190">As propriedades que usam atributos de validação ou atributos de transformação de argumento (como, `[ValidateSet("aaa")]`) funcionam como esperado.</span><span class="sxs-lookup"><span data-stu-id="4d373-190">Properties that use validation or argument transformation attributes (like `[ValidateSet("aaa")]`) work as expected.</span></span>

### <a name="hidden"></a><span data-ttu-id="4d373-191">Hidden</span><span class="sxs-lookup"><span data-stu-id="4d373-191">Hidden</span></span>

<span data-ttu-id="4d373-192">Uma nova palavra-chave, `Hidden`, foi adicionada.</span><span class="sxs-lookup"><span data-stu-id="4d373-192">A new keyword, `Hidden`, has been added.</span></span> <span data-ttu-id="4d373-193">`Hidden` pode ser aplicado a propriedades e métodos (incluindo construtores).</span><span class="sxs-lookup"><span data-stu-id="4d373-193">`Hidden` can be applied to properties and methods (including constructors).</span></span>

<span data-ttu-id="4d373-194">Os membros ocultos são públicos, mas não aparecem na saída de `Get-Member`, a menos que o parâmetro `-Force` seja adicionado.</span><span class="sxs-lookup"><span data-stu-id="4d373-194">Hidden members are public, but do not appear in the output of `Get-Member` unless the `-Force` parameter is added.</span></span> <span data-ttu-id="4d373-195">Membros ocultos não são incluídos durante o preenchimento de tabulação ou uso do IntelliSense, a menos que o preenchimento ocorra na classe que define o membro oculto.</span><span class="sxs-lookup"><span data-stu-id="4d373-195">Hidden members are not included when tab completing or using Intellisense unless the completion occurs in the class defining the hidden member.</span></span>

<span data-ttu-id="4d373-196">Um novo atributo, **System.Management.Automation.HiddenAttribute**, foi adicionado para que o código do C\# possa ter a mesma semântica dentro do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d373-196">A new attribute, **System.Management.Automation.HiddenAttribute** has been added so that C\# code can have the same semantics within PowerShell.</span></span>

### <a name="return-types"></a><span data-ttu-id="4d373-197">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="4d373-197">Return types</span></span>

<span data-ttu-id="4d373-198">O tipo de retorno é um contrato.</span><span class="sxs-lookup"><span data-stu-id="4d373-198">Return type is a contract.</span></span> <span data-ttu-id="4d373-199">O valor retornado é convertido para o tipo esperado.</span><span class="sxs-lookup"><span data-stu-id="4d373-199">The return value is converted to the expected type.</span></span> <span data-ttu-id="4d373-200">Se nenhum tipo de retorno for especificado, o tipo de retorno será **nulo**.</span><span class="sxs-lookup"><span data-stu-id="4d373-200">If no return type is specified, the return type is **void**.</span></span> <span data-ttu-id="4d373-201">Não há transmissão de objetos.</span><span class="sxs-lookup"><span data-stu-id="4d373-201">There is no streaming of objects.</span></span> <span data-ttu-id="4d373-202">Os objetos não podem ser gravados no pipeline, seja intencionalmente ou por engano.</span><span class="sxs-lookup"><span data-stu-id="4d373-202">Objects cannot be written to the pipeline either intentionally or by accident.</span></span>

### <a name="attributes"></a><span data-ttu-id="4d373-203">Atributos</span><span class="sxs-lookup"><span data-stu-id="4d373-203">Attributes</span></span>

<span data-ttu-id="4d373-204">Dois novos atributos, **DscResource** e **DscProperty** foram adicionados.</span><span class="sxs-lookup"><span data-stu-id="4d373-204">Two new attributes, **DscResource** and **DscProperty** have been added.</span></span>

### <a name="lexical-scoping-of-variables"></a><span data-ttu-id="4d373-205">Escopo léxico de variáveis</span><span class="sxs-lookup"><span data-stu-id="4d373-205">Lexical scoping of variables</span></span>

<span data-ttu-id="4d373-206">Apresentamos a seguir um exemplo de como o escopo léxico funciona nesta versão.</span><span class="sxs-lookup"><span data-stu-id="4d373-206">The following shows an example of how lexical scoping works in this release.</span></span>

```powershell
$d = 42 # Script scope

function bar
{
    $d = 0 # Function scope
    [MyClass]::DoSomething()
}

class MyClass
{
    static [object] DoSomething()
    {
        return $d # error, not found dynamically
        return $script:d # no error
        $d = $script:d
        return $d # no error, found lexically
    }
}

$v = bar
$v -eq $d # true
```

## <a name="end-to-end-example"></a><span data-ttu-id="4d373-207">Exemplo de ponta a ponta</span><span class="sxs-lookup"><span data-stu-id="4d373-207">End-to-End Example</span></span>

<span data-ttu-id="4d373-208">O exemplo a seguir cria algumas classes personalizadas para implementar uma DSL (linguagem de folha de estilos dinâmica) em HTML.</span><span class="sxs-lookup"><span data-stu-id="4d373-208">The following example creates some custom classes to implement an HTML dynamic style sheet language (DSL).</span></span> <span data-ttu-id="4d373-209">Em seguida, o exemplo adiciona funções auxiliares para criar tipos específicos de elementos como parte da classe de elemento, como estilos de título e tabelas, já que os tipos não podem ser usados fora do escopo de um módulo.</span><span class="sxs-lookup"><span data-stu-id="4d373-209">Then, the example adds helper functions to create specific element types as part of the element class, such as heading styles and tables, because types cannot be used outside the scope of a module.</span></span>

```powershell
# Classes that define the structure of the document
#
class Html
{
    [string] $docType
    [HtmlHead] $Head
    [Element[]] $Body

    [string] Render()
    {
        $text = "<html>`n<head>`n"
        $text += $this.Head
        $text += "`n</head>`n<body>`n"
        $text += $this.Body -join "`n" # Render all of the body elements
        $text += "</body>`n</html>"
        return $text
    }
    [string] ToString() { return $this.Render() }
}

class HtmlHead
{
    $Title
    $Base
    $Link
    $Style
    $Meta
    $Script
    [string] Render() { return "<title>$($this.Title)</title>" }
    [string] ToString() { return $this.Render() }
}

class Element
{
    [string] $Tag
    [string] $Text
    [hashtable] $Attributes
    [string] Render() {
        $attributesText= ""
        if ($this.Attributes)
        {
            foreach ($attr in $this.Attributes.Keys)
            {
                #BUGBUG - need to validate keys against attribute
                $attributesText += " $attr=`"$($this.Attributes[$attr])\`""
            }
        }
        return "<$($this.tag)${attributesText}>$($this.text)</$($this.tag)>`n"
    }
[string] ToString() { return $this.Render() }
}

#
# Helper functions for creating specific element types on top of the classes.
# These are required because types aren't visible outside of the module.
#

function H1 { [Element] @{ Tag = "H1" ; Text = $args.foreach{$_} -join " " }}
function H2 { [Element] @{ Tag = "H2" ; Text = $args.foreach{$_} -join " " }}
function H3 { [Element] @{ Tag = "H3" ; Text = $args.foreach{$_} -join " " }}
function P { [Element] @{ Tag = "P" ; Text = $args.foreach{$_} -join " " }}
function B { [Element] @{ Tag = "B" ; Text = $args.foreach{$_} -join " " }}
function I { [Element] @{ Tag = "I" ; Text = $args.foreach{$_} -join " " }}
function HREF
{
    param (
        $Name,
        $Link
    )
    return [Element] @{
        Tag = "A"
        Attributes = @{ HREF = $link }
        Text = $name
    }
}
function Table
{
    param (
    [Parameter(Mandatory)]
    [object[]]
        $Data,
    [Parameter()]
    [string[]]
        $Properties = "*",
    [Parameter()]
    [hashtable]
        $Attributes = @{ border=2; cellpadding=2; cellspacing=2 }
    )
$bodyText = ""
# Add the header tags
$bodyText += $Properties.foreach{TH $_}
# Add the rows
$bodyText += foreach ($row in $Data)
    {
        TR (-join $Properties.Foreach{ TD ($row.$_) } )
    }

    $table = [Element] @{
        Tag = "Table"
        Attributes = $Attributes
        Text = $bodyText
    }
$table
}
function TH { ([Element] @{ Tag = "TH" ; Text = $args.foreach{$_} -join " " }) }
function TR { ([Element] @{ Tag = "TR" ; Text = $args.foreach{$_} -join " " }) }
function TD { ([Element] @{ Tag = "TD" ; Text = $args.foreach{$_} -join " " }) }
function Style

{
    return [Element] @{
        Tag = "style"
        Text = "$args"
    }
}

# Takes a hash table, casts it to and HTML document
# and then returns the resulting type.
#
function Html ([HTML] $doc) { return $doc }
```
