---
description: Descreve como você pode usar classes para criar seus próprios tipos personalizados.
Locale: en-US
ms.date: 01/19/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_classes?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Classes
ms.openlocfilehash: 0f4eb5c67b09cb3ce21f818582fbce3a8c629eec
ms.sourcegitcommit: 94d597c4fb38793bc49ca7610e2c9973b1e577c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "98620207"
---
# <a name="about-classes"></a><span data-ttu-id="b0e6f-103">Sobre classes</span><span class="sxs-lookup"><span data-stu-id="b0e6f-103">About Classes</span></span>

## <a name="short-description"></a><span data-ttu-id="b0e6f-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="b0e6f-104">Short description</span></span>
<span data-ttu-id="b0e6f-105">Descreve como você pode usar classes para criar seus próprios tipos personalizados.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-105">Describes how you can use classes to create your own custom types.</span></span>

## <a name="long-description"></a><span data-ttu-id="b0e6f-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="b0e6f-106">Long description</span></span>

<span data-ttu-id="b0e6f-107">O PowerShell 5,0 adiciona uma sintaxe formal para definir classes e outros tipos definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-107">PowerShell 5.0 adds a formal syntax to define classes and other user-defined types.</span></span> <span data-ttu-id="b0e6f-108">A adição de classes permite que desenvolvedores e profissionais de ti adotem o PowerShell para uma variedade maior de casos de uso.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-108">The addition of classes enables developers and IT professionals to embrace PowerShell for a wider range of use cases.</span></span> <span data-ttu-id="b0e6f-109">Ele simplifica o desenvolvimento de artefatos do PowerShell e acelera a cobertura de superfícies de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-109">It simplifies development of PowerShell artifacts and accelerates coverage of management surfaces.</span></span>

<span data-ttu-id="b0e6f-110">Uma declaração de classe é um plano gráfico usado para criar instâncias de objetos em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-110">A class declaration is a blueprint used to create instances of objects at run time.</span></span> <span data-ttu-id="b0e6f-111">Quando você define uma classe, o nome da classe é o nome do tipo.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-111">When you define a class, the class name is the name of the type.</span></span> <span data-ttu-id="b0e6f-112">Por exemplo, se você declarar uma classe chamada **dispositivo** e inicializar uma variável `$dev` para uma nova instância do **dispositivo**, `$dev` será um objeto ou instância do tipo **dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-112">For example, if you declare a class named **Device** and initialize a variable `$dev` to a new instance of **Device**, `$dev` is an object or instance of type **Device**.</span></span> <span data-ttu-id="b0e6f-113">Cada instância do **dispositivo** pode ter valores diferentes em suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-113">Each instance of **Device** can have different values in its properties.</span></span>

## <a name="supported-scenarios"></a><span data-ttu-id="b0e6f-114">Cenários com suporte</span><span class="sxs-lookup"><span data-stu-id="b0e6f-114">Supported scenarios</span></span>

- <span data-ttu-id="b0e6f-115">Defina tipos personalizados no PowerShell usando semântica familiar de programação orientada a objeto, como classes, propriedades, métodos, herança, etc.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-115">Define custom types in PowerShell using familiar object-oriented programming semantics like classes, properties, methods, inheritance, etc.</span></span>
- <span data-ttu-id="b0e6f-116">Depurar tipos usando a linguagem do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-116">Debug types using the PowerShell language.</span></span>
- <span data-ttu-id="b0e6f-117">Gere e manipule exceções usando mecanismos formais.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-117">Generate and handle exceptions using formal mechanisms.</span></span>
- <span data-ttu-id="b0e6f-118">Defina os recursos de DSC e seus tipos associados usando a linguagem do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-118">Define DSC resources and their associated types by using the PowerShell language.</span></span>

## <a name="syntax"></a><span data-ttu-id="b0e6f-119">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b0e6f-119">Syntax</span></span>

<span data-ttu-id="b0e6f-120">As classes são declaradas usando a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="b0e6f-120">Classes are declared using the following syntax:</span></span>

```syntax
class <class-name> [: [<base-class>][,<interface-list]] {
    [[<attribute>] [hidden] [static] <property-definition> ...]
    [<class-name>([<constructor-argument-list>])
      {<constructor-statement-list>} ...]
    [[<attribute>] [hidden] [static] <method-definition> ...]
}
```

<span data-ttu-id="b0e6f-121">As classes são instanciadas usando qualquer uma das seguintes sintaxes:</span><span class="sxs-lookup"><span data-stu-id="b0e6f-121">Classes are instantiated using either of the following syntaxes:</span></span>

```syntax
[$<variable-name> =] New-Object -TypeName <class-name> [
  [-ArgumentList] <constructor-argument-list>]
```

```syntax
[$<variable-name> =] [<class-name>]::new([<constructor-argument-list>])
```

> [!NOTE]
> <span data-ttu-id="b0e6f-122">Ao usar a `[<class-name>]::new()` sintaxe, os colchetes em volta do nome da classe são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-122">When using the `[<class-name>]::new()` syntax, brackets around the class name are mandatory.</span></span> <span data-ttu-id="b0e6f-123">Os colchetes sinalizam uma definição de tipo para o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-123">The brackets signal a type definition for PowerShell.</span></span>

### <a name="example-syntax-and-usage"></a><span data-ttu-id="b0e6f-124">Exemplo de sintaxe e uso</span><span class="sxs-lookup"><span data-stu-id="b0e6f-124">Example syntax and usage</span></span>

<span data-ttu-id="b0e6f-125">Este exemplo mostra a sintaxe mínima necessária para criar uma classe utilizável.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-125">This example shows the minimum syntax needed to create a usable class.</span></span>

```powershell
class Device {
    [string]$Brand
}

$dev = [Device]::new()
$dev.Brand = "Microsoft"
$dev
```

```Output
Brand
-----
Microsoft
```

## <a name="class-properties"></a><span data-ttu-id="b0e6f-126">Propriedades da classe</span><span class="sxs-lookup"><span data-stu-id="b0e6f-126">Class properties</span></span>

<span data-ttu-id="b0e6f-127">As propriedades são variáveis declaradas no escopo de classe.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-127">Properties are variables declared at class scope.</span></span> <span data-ttu-id="b0e6f-128">Uma propriedade pode ser de qualquer tipo interno ou uma instância de outra classe.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-128">A property may be of any built-in type or an instance of another class.</span></span> <span data-ttu-id="b0e6f-129">As classes não têm nenhuma restrição no número de propriedades que elas têm.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-129">Classes have no restriction in the number of properties they have.</span></span>

### <a name="example-class-with-simple-properties"></a><span data-ttu-id="b0e6f-130">Classe de exemplo com propriedades simples</span><span class="sxs-lookup"><span data-stu-id="b0e6f-130">Example class with simple properties</span></span>

```powershell
class Device {
    [string]$Brand
    [string]$Model
    [string]$VendorSku
}

$device = [Device]::new()
$device.Brand = "Microsoft"
$device.Model = "Surface Pro 4"
$device.VendorSku = "5072641000"

$device
```

```Output
Brand     Model         VendorSku
-----     -----         ---------
Microsoft Surface Pro 4 5072641000
```

### <a name="example-complex-types-in-class-properties"></a><span data-ttu-id="b0e6f-131">Exemplos de tipos complexos em Propriedades de classe</span><span class="sxs-lookup"><span data-stu-id="b0e6f-131">Example complex types in class properties</span></span>

<span data-ttu-id="b0e6f-132">Este exemplo define uma classe de **rack** vazia usando a classe de **dispositivo** .</span><span class="sxs-lookup"><span data-stu-id="b0e6f-132">This example defines an empty **Rack** class using the **Device** class.</span></span> <span data-ttu-id="b0e6f-133">Os exemplos, a seguir, mostram como adicionar dispositivos ao rack e como começar com um rack pré-carregado.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-133">The examples, following this one, show how to add devices to the rack and how to start with a pre-loaded rack.</span></span>

```powershell
class Device {
    [string]$Brand
    [string]$Model
    [string]$VendorSku
}

class Rack {
    [string]$Brand
    [string]$Model
    [string]$VendorSku
    [string]$AssetId
    [Device[]]$Devices = [Device[]]::new(8)

}

$rack = [Rack]::new()

$rack
```

```Output

Brand     :
Model     :
VendorSku :
AssetId   :
Devices   : {$null, $null, $null, $null...}


```

## <a name="class-methods"></a><span data-ttu-id="b0e6f-134">Métodos de classe</span><span class="sxs-lookup"><span data-stu-id="b0e6f-134">Class methods</span></span>

<span data-ttu-id="b0e6f-135">Os métodos definem as ações que uma classe pode executar.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-135">Methods define the actions that a class can perform.</span></span> <span data-ttu-id="b0e6f-136">Os métodos podem receber parâmetros que fornecem dados de entrada.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-136">Methods may take parameters that provide input data.</span></span> <span data-ttu-id="b0e6f-137">Os métodos podem retornar a saída.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-137">Methods can return output.</span></span> <span data-ttu-id="b0e6f-138">Os dados retornados por um método podem ser qualquer tipo de dados definido.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-138">Data returned by a method can be any defined data type.</span></span>

<span data-ttu-id="b0e6f-139">Ao definir um método para uma classe, você faz referência ao objeto de classe atual usando a `$this` variável automática.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-139">When defining a method for a class, you reference the current class object by using the `$this` automatic variable.</span></span> <span data-ttu-id="b0e6f-140">Isso permite que você acesse Propriedades e outros métodos definidos na classe atual.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-140">This allows you to access properties and other methods defined in the current class.</span></span>

### <a name="example-simple-class-with-properties-and-methods"></a><span data-ttu-id="b0e6f-141">Exemplo de classe simples com propriedades e métodos</span><span class="sxs-lookup"><span data-stu-id="b0e6f-141">Example simple class with properties and methods</span></span>

<span data-ttu-id="b0e6f-142">Estendendo a classe **rack** para adicionar e remover dispositivos de ou para ele.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-142">Extending the **Rack** class to add and remove devices to or from it.</span></span>

```powershell
class Device {
    [string]$Brand
    [string]$Model
    [string]$VendorSku

    [string]ToString(){
        return ("{0}|{1}|{2}" -f $this.Brand, $this.Model, $this.VendorSku)
    }
}

class Rack {
    [int]$Slots = 8
    [string]$Brand
    [string]$Model
    [string]$VendorSku
    [string]$AssetId
    [Device[]]$Devices = [Device[]]::new($this.Slots)

    [void] AddDevice([Device]$dev, [int]$slot){
        ## Add argument validation logic here
        $this.Devices[$slot] = $dev
    }

    [void]RemoveDevice([int]$slot){
        ## Add argument validation logic here
        $this.Devices[$slot] = $null
    }

    [int[]] GetAvailableSlots(){
        [int]$i = 0
        return @($this.Devices.foreach{ if($_ -eq $null){$i}; $i++})
    }
}

$rack = [Rack]::new()

$surface = [Device]::new()
$surface.Brand = "Microsoft"
$surface.Model = "Surface Pro 4"
$surface.VendorSku = "5072641000"

$rack.AddDevice($surface, 2)

$rack
$rack.GetAvailableSlots()
```

```Output

Slots     : 8
Brand     :
Model     :
VendorSku :
AssetId   :
Devices   : {$null, $null, Microsoft|Surface Pro 4|5072641000, $null...}

0
1
3
4
5
6
7

```

## <a name="output-in-class-methods"></a><span data-ttu-id="b0e6f-143">Saída em métodos de classe</span><span class="sxs-lookup"><span data-stu-id="b0e6f-143">Output in class methods</span></span>

<span data-ttu-id="b0e6f-144">Os métodos devem ter um tipo de retorno definido.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-144">Methods should have a return type defined.</span></span> <span data-ttu-id="b0e6f-145">Se um método não retornar a saída, o tipo de saída deverá ser `[void]` .</span><span class="sxs-lookup"><span data-stu-id="b0e6f-145">If a method doesn't return output, then the output type should be `[void]`.</span></span>

<span data-ttu-id="b0e6f-146">Em métodos de classe, nenhum objeto é enviado para o pipeline, exceto aqueles mencionados na `return` instrução.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-146">In class methods, no objects get sent to the pipeline except those mentioned in the `return` statement.</span></span> <span data-ttu-id="b0e6f-147">Não há saída acidental para o pipeline a partir do código.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-147">There's no accidental output to the pipeline from the code.</span></span>

> [!NOTE]
> <span data-ttu-id="b0e6f-148">Isso é fundamentalmente diferente de como as funções do PowerShell lidam com a saída, onde tudo vai para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-148">This is fundamentally different from how PowerShell functions handle output, where everything goes to the pipeline.</span></span>

<span data-ttu-id="b0e6f-149">Os erros de não finalização gravados no fluxo de erros de dentro de um método de classe não são passados.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-149">Non-terminating errors written to the error stream from inside a class method are not passed through.</span></span> <span data-ttu-id="b0e6f-150">Você deve usar `throw` o para retonar um erro de encerramento.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-150">You must use `throw` to surface a terminating error.</span></span>
<span data-ttu-id="b0e6f-151">Usando os `Write-*` cmdlets, você ainda pode gravar nos fluxos de saída do PowerShell de dentro de um método de classe.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-151">Using the `Write-*` cmdlets, you can still write to PowerShell's output streams from within a class method.</span></span> <span data-ttu-id="b0e6f-152">No entanto, isso deve ser evitado para que o método emita objetos usando apenas a `return` instrução.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-152">However, this should be avoided so that the method emits objects using only the `return` statement.</span></span>

### <a name="method-output"></a><span data-ttu-id="b0e6f-153">Saída do método</span><span class="sxs-lookup"><span data-stu-id="b0e6f-153">Method output</span></span>

<span data-ttu-id="b0e6f-154">Este exemplo demonstra nenhuma saída acidental para o pipeline a partir de métodos de classe, exceto na `return` instrução.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-154">This example demonstrates no accidental output to the pipeline from class methods, except on the `return` statement.</span></span>

```powershell
class FunWithIntegers
{
    [int[]]$Integers = 0..10

    [int[]]GetOddIntegers(){
        return $this.Integers.Where({ ($_ % 2) })
    }

    [void] GetEvenIntegers(){
        # this following line doesn't go to the pipeline
        $this.Integers.Where({ ($_ % 2) -eq 0})
    }

    [string]SayHello(){
        # this following line doesn't go to the pipeline
        "Good Morning"

        # this line goes to the pipeline
        return "Hello World"
    }
}

$ints = [FunWithIntegers]::new()
$ints.GetOddIntegers()
$ints.GetEvenIntegers()
$ints.SayHello()
```

```Output
1
3
5
7
9
Hello World

```

## <a name="constructor"></a><span data-ttu-id="b0e6f-155">Construtor</span><span class="sxs-lookup"><span data-stu-id="b0e6f-155">Constructor</span></span>

<span data-ttu-id="b0e6f-156">Os construtores permitem que você defina valores padrão e valide a lógica do objeto no momento da criação da instância da classe.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-156">Constructors enable you to set default values and validate object logic at the moment of creating the instance of the class.</span></span> <span data-ttu-id="b0e6f-157">Os construtores têm o mesmo nome que a classe.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-157">Constructors have the same name as the class.</span></span> <span data-ttu-id="b0e6f-158">Os construtores podem ter argumentos para inicializar os membros de dados do novo objeto.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-158">Constructors might have arguments, to initialize the data members of the new object.</span></span>

<span data-ttu-id="b0e6f-159">A classe pode ter zero ou mais construtores definidos.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-159">The class can have zero or more constructors defined.</span></span> <span data-ttu-id="b0e6f-160">Se nenhum construtor for definido, a classe receberá um construtor sem parâmetros padrão.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-160">If no constructor is defined, the class is given a default parameterless constructor.</span></span> <span data-ttu-id="b0e6f-161">Esse construtor inicializa todos os membros para seus valores padrão.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-161">This constructor initializes all members to their default values.</span></span> <span data-ttu-id="b0e6f-162">Os tipos de objeto e cadeias de caracteres recebem valores nulos.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-162">Object types and strings are given null values.</span></span> <span data-ttu-id="b0e6f-163">Quando você define o construtor, nenhum construtor padrão sem parâmetros é criado.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-163">When you define constructor, no default parameterless constructor is created.</span></span> <span data-ttu-id="b0e6f-164">Crie um construtor sem parâmetros se um for necessário.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-164">Create a parameterless constructor if one is needed.</span></span>

### <a name="constructor-basic-syntax"></a><span data-ttu-id="b0e6f-165">Sintaxe básica do Construtor</span><span class="sxs-lookup"><span data-stu-id="b0e6f-165">Constructor basic syntax</span></span>

<span data-ttu-id="b0e6f-166">Neste exemplo, a classe de dispositivo é definida com propriedades e um construtor.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-166">In this example, the Device class is defined with properties and a constructor.</span></span>
<span data-ttu-id="b0e6f-167">Para usar essa classe, o usuário deve fornecer valores para os parâmetros listados no construtor.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-167">To use this class, the user is required to provide values for the parameters listed in the constructor.</span></span>

```powershell
class Device {
    [string]$Brand
    [string]$Model
    [string]$VendorSku

    Device(
        [string]$b,
        [string]$m,
        [string]$vsk
    ){
        $this.Brand = $b
        $this.Model = $m
        $this.VendorSku = $vsk
    }
}

[Device]$surface = [Device]::new("Microsoft", "Surface Pro 4", "5072641000")

$surface
```

```Output
Brand     Model         VendorSku
-----     -----         ---------
Microsoft Surface Pro 4 5072641000
```

### <a name="example-with-multiple-constructors"></a><span data-ttu-id="b0e6f-168">Exemplo com vários construtores</span><span class="sxs-lookup"><span data-stu-id="b0e6f-168">Example with multiple constructors</span></span>

<span data-ttu-id="b0e6f-169">Neste exemplo, a classe de **dispositivo** é definida com propriedades, um construtor padrão e um construtor para inicializar a instância.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-169">In this example, the **Device** class is defined with properties, a default constructor, and a constructor to initialize the instance.</span></span>

<span data-ttu-id="b0e6f-170">O construtor padrão define a **marca** como **indefinida** e deixa o **modelo** e o **SKU do fornecedor** com valores nulos.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-170">The default constructor sets the **brand** to **Undefined**, and leaves **model** and **vendor-sku** with null values.</span></span>

```powershell
class Device {
    [string]$Brand
    [string]$Model
    [string]$VendorSku

    Device(){
        $this.Brand = 'Undefined'
    }

    Device(
        [string]$b,
        [string]$m,
        [string]$vsk
    ){
        $this.Brand = $b
        $this.Model = $m
        $this.VendorSku = $vsk
    }
}

[Device]$somedevice = [Device]::new()
[Device]$surface = [Device]::new("Microsoft", "Surface Pro 4", "5072641000")

$somedevice
$surface
```

```Output
Brand       Model           VendorSku
-----       -----           ---------
Undefined
Microsoft   Surface Pro 4   5072641000
```

## <a name="hidden-attribute"></a><span data-ttu-id="b0e6f-171">Atributo Hidden</span><span class="sxs-lookup"><span data-stu-id="b0e6f-171">Hidden attribute</span></span>

<span data-ttu-id="b0e6f-172">O `hidden` atributo oculta uma propriedade ou um método.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-172">The `hidden` attribute hides a property or method.</span></span> <span data-ttu-id="b0e6f-173">A propriedade ou o método ainda é acessível para o usuário e está disponível em todos os escopos nos quais o objeto está disponível.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-173">The property or method is still accessible to the user and is available in all scopes in which the object is available.</span></span> <span data-ttu-id="b0e6f-174">Os membros ocultos são ocultos do `Get-Member` cmdlet e não podem ser exibidos usando o preenchimento com Tab ou o IntelliSense fora da definição de classe.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-174">Hidden members are hidden from the `Get-Member` cmdlet and can't be displayed using tab completion or IntelliSense outside the class definition.</span></span>

<span data-ttu-id="b0e6f-175">Para obter mais informações, consulte [About_hidden](About_hidden.md).</span><span class="sxs-lookup"><span data-stu-id="b0e6f-175">For more information, see [About_hidden](About_hidden.md).</span></span>

### <a name="example-using-hidden-attributes"></a><span data-ttu-id="b0e6f-176">Exemplo usando atributos ocultos</span><span class="sxs-lookup"><span data-stu-id="b0e6f-176">Example using hidden attributes</span></span>

<span data-ttu-id="b0e6f-177">Quando um objeto de **rack** é criado, o número de Slots para dispositivos é um valor fixo que não deve ser alterado a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-177">When a **Rack** object is created, the number of slots for devices is a fixed value that shouldn't be changed at any time.</span></span> <span data-ttu-id="b0e6f-178">Esse valor é conhecido no momento da criação.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-178">This value is known at creation time.</span></span>

<span data-ttu-id="b0e6f-179">O uso do atributo Hidden permite que o desenvolvedor Mantenha o número de Slots ocultos e impede que alterações não intencionais sejam alteradas no tamanho do rack.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-179">Using the hidden attribute allows the developer to keep the number of slots hidden and prevents unintentional changes the size of the rack.</span></span>

```powershell
class Device {
    [string]$Brand
    [string]$Model
}

class Rack {
    [int] hidden $Slots = 8
    [string]$Brand
    [string]$Model
    [Device[]]$Devices = [Device[]]::new($this.Slots)

    Rack ([string]$b, [string]$m, [int]$capacity){
        ## argument validation here

        $this.Brand = $b
        $this.Model = $m
        $this.Slots = $capacity

        ## reset rack size to new capacity
        $this.Devices = [Device[]]::new($this.Slots)
    }
}

[Rack]$r1 = [Rack]::new("Microsoft", "Surface Pro 4", 16)

$r1
$r1.Devices.Length
$r1.Slots
```

```Output
Brand     Model         Devices
-----     -----         -------
Microsoft Surface Pro 4 {$null, $null, $null, $null...}
16
16
```

<span data-ttu-id="b0e6f-180">Observe que a propriedade **Slots** não é mostrada na `$r1` saída.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-180">Notice **Slots** property isn't shown in `$r1` output.</span></span> <span data-ttu-id="b0e6f-181">No entanto, o tamanho foi alterado pelo construtor.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-181">However, the size was changed by the constructor.</span></span>

## <a name="static-attribute"></a><span data-ttu-id="b0e6f-182">Atributo estático</span><span class="sxs-lookup"><span data-stu-id="b0e6f-182">Static attribute</span></span>

<span data-ttu-id="b0e6f-183">O `static` atributo define uma propriedade ou um método que existe na classe e não precisa de nenhuma instância.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-183">The `static` attribute defines a property or a method that exists in the class and needs no instance.</span></span>

<span data-ttu-id="b0e6f-184">Uma propriedade estática está sempre disponível, independentemente da instanciação de classe.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-184">A static property is always available, independent of class instantiation.</span></span> <span data-ttu-id="b0e6f-185">Uma propriedade estática é compartilhada entre todas as instâncias da classe.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-185">A static property is shared across all instances of the class.</span></span> <span data-ttu-id="b0e6f-186">Um método estático está disponível sempre.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-186">A static method is available always.</span></span> <span data-ttu-id="b0e6f-187">Todas as propriedades estáticas em tempo real para toda a sessão abrangem.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-187">All static properties live for the entire session span.</span></span>

### <a name="example-using-static-attributes-and-methods"></a><span data-ttu-id="b0e6f-188">Exemplo usando atributos e métodos estáticos</span><span class="sxs-lookup"><span data-stu-id="b0e6f-188">Example using static attributes and methods</span></span>

<span data-ttu-id="b0e6f-189">Suponha que os racks instanciados aqui existam no seu data center.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-189">Assume the racks instantiated here exist in your data center.</span></span> <span data-ttu-id="b0e6f-190">Portanto, você gostaria de acompanhar os racks em seu código.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-190">So, you would like to keep track of the racks in your code.</span></span>

```powershell
class Device {
    [string]$Brand
    [string]$Model
}

class Rack {
    hidden [int] $Slots = 8
    static [Rack[]]$InstalledRacks = @()
    [string]$Brand
    [string]$Model
    [string]$AssetId
    [Device[]]$Devices = [Device[]]::new($this.Slots)

    Rack ([string]$b, [string]$m, [string]$id, [int]$capacity){
        ## argument validation here

        $this.Brand = $b
        $this.Model = $m
        $this.AssetId = $id
        $this.Slots = $capacity

        ## reset rack size to new capacity
        $this.Devices = [Device[]]::new($this.Slots)

        ## add rack to installed racks
        [Rack]::InstalledRacks += $this
    }

    static [void]PowerOffRacks(){
        foreach ($rack in [Rack]::InstalledRacks) {
            Write-Warning ("Turning off rack: " + ($rack.AssetId))
        }
    }
}
```

### <a name="testing-static-property-and-method-exist"></a><span data-ttu-id="b0e6f-191">O teste da propriedade estática e do método existe</span><span class="sxs-lookup"><span data-stu-id="b0e6f-191">Testing static property and method exist</span></span>

```
PS> [Rack]::InstalledRacks.Length
0

PS> [Rack]::PowerOffRacks()

PS> (1..10) | ForEach-Object {
>>   [Rack]::new("Adatum Corporation", "Standard-16",
>>     $_.ToString("Std0000"), 16)
>> } > $null

PS> [Rack]::InstalledRacks.Length
10

PS> [Rack]::InstalledRacks[3]
Brand              Model       AssetId Devices
-----              -----       ------- -------
Adatum Corporation Standard-16 Std0004 {$null, $null, $null, $null...}

PS> [Rack]::PowerOffRacks()
WARNING: Turning off rack: Std0001
WARNING: Turning off rack: Std0002
WARNING: Turning off rack: Std0003
WARNING: Turning off rack: Std0004
WARNING: Turning off rack: Std0005
WARNING: Turning off rack: Std0006
WARNING: Turning off rack: Std0007
WARNING: Turning off rack: Std0008
WARNING: Turning off rack: Std0009
WARNING: Turning off rack: Std0010
```

<span data-ttu-id="b0e6f-192">Observe que o número de racks aumenta cada vez que você executa este exemplo.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-192">Notice that the number of racks increases each time you run this example.</span></span>

## <a name="property-validation-attributes"></a><span data-ttu-id="b0e6f-193">Atributos de validação de propriedade</span><span class="sxs-lookup"><span data-stu-id="b0e6f-193">Property validation attributes</span></span>

<span data-ttu-id="b0e6f-194">Os atributos de validação permitem testar os valores fornecidos às propriedades que atendem aos requisitos definidos.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-194">Validation attributes allow you to test that values given to properties meet defined requirements.</span></span> <span data-ttu-id="b0e6f-195">A validação é disparada no momento em que o valor é atribuído.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-195">Validation is triggered the moment that the value is assigned.</span></span> <span data-ttu-id="b0e6f-196">Consulte [about_Functions_Advanced_Parameters](about_functions_advanced_parameters.md).</span><span class="sxs-lookup"><span data-stu-id="b0e6f-196">See [about_functions_advanced_parameters](about_functions_advanced_parameters.md).</span></span>

### <a name="example-using-validation-attributes"></a><span data-ttu-id="b0e6f-197">Exemplo usando atributos de validação</span><span class="sxs-lookup"><span data-stu-id="b0e6f-197">Example using validation attributes</span></span>

```powershell
class Device {
    [ValidateNotNullOrEmpty()][string]$Brand
    [ValidateNotNullOrEmpty()][string]$Model
}

[Device]$dev = [Device]::new()

Write-Output "Testing dev"
$dev

$dev.Brand = ""
```

```Output
Testing dev

Brand Model
----- -----

Exception setting "Brand": "The argument is null or empty. Provide an
argument that is not null or empty, and then try the command again."
At C:\tmp\Untitled-5.ps1:11 char:1
+ $dev.Brand = ""
+ ~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], SetValueInvocationException
    + FullyQualifiedErrorId : ExceptionWhenSetting
```

## <a name="inheritance-in-powershell-classes"></a><span data-ttu-id="b0e6f-198">Herança em classes do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0e6f-198">Inheritance in PowerShell classes</span></span>

<span data-ttu-id="b0e6f-199">Você pode estender uma classe criando uma nova classe que deriva de uma classe existente.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-199">You can extend a class by creating a new class that derives from an existing class.</span></span> <span data-ttu-id="b0e6f-200">A classe derivada herda as propriedades da classe base.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-200">The derived class inherits the properties of the base class.</span></span> <span data-ttu-id="b0e6f-201">Você pode adicionar ou substituir métodos e propriedades conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-201">You can add or override methods and properties as required.</span></span>

<span data-ttu-id="b0e6f-202">O PowerShell não dá suporte a várias heranças.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-202">PowerShell does not support multiple inheritance.</span></span> <span data-ttu-id="b0e6f-203">Classes não podem herdar de mais de uma classe.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-203">Classes cannot inherit from more than one class.</span></span> <span data-ttu-id="b0e6f-204">No entanto, você pode usar interfaces para essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-204">However, you can use interfaces for that purpose.</span></span>

<span data-ttu-id="b0e6f-205">A implementação de herança é definida pelo `:` operador; o que significa estender essa classe ou implementar essas interfaces.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-205">Inheritance implementation is defined by the `:` operator; which means to extend this class or implements these interfaces.</span></span> <span data-ttu-id="b0e6f-206">A classe derivada deve estar sempre na extrema esquerda na declaração de classe.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-206">The derived class should always be leftmost in the class declaration.</span></span>

### <a name="example-using-simple-inheritance-syntax"></a><span data-ttu-id="b0e6f-207">Exemplo usando sintaxe de herança simples</span><span class="sxs-lookup"><span data-stu-id="b0e6f-207">Example using simple inheritance syntax</span></span>

<span data-ttu-id="b0e6f-208">Este exemplo mostra a sintaxe simples de herança de classe do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-208">This example shows the simple PowerShell class inheritance syntax.</span></span>

```powershell
Class Derived : Base {...}
```

<span data-ttu-id="b0e6f-209">Este exemplo mostra a herança com uma declaração de interface chegando após a classe base.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-209">This example shows inheritance with an interface declaration coming after the base class.</span></span>

```powershell
Class Derived : Base, Interface {...}
```

### <a name="example-of-simple-inheritance-in-powershell-classes"></a><span data-ttu-id="b0e6f-210">Exemplo de herança simples em classes do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0e6f-210">Example of simple inheritance in PowerShell classes</span></span>

<span data-ttu-id="b0e6f-211">Neste exemplo, as classes de **rack** e **dispositivo** usadas nos exemplos anteriores são mais bem definidas para: evitar repetições de propriedade, alinhar melhor as propriedades comuns e reutilizar a lógica de negócios comum.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-211">In this example the **Rack** and **Device** classes used in the previous examples are better defined to: avoid property repetitions, better align common properties, and reuse common business logic.</span></span>

<span data-ttu-id="b0e6f-212">A maioria dos objetos na data center são ativos da empresa, o que faz sentido começar a controlá-los como ativos.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-212">Most objects in the data center are company assets, which makes sense to start tracking them as assets.</span></span> <span data-ttu-id="b0e6f-213">Os tipos de dispositivo são definidos pela `DeviceType` enumeração, consulte [about_Enum](about_Enum.md) para obter detalhes sobre enumerações.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-213">Device types are defined by the `DeviceType` enumeration, see [about_Enum](about_Enum.md) for details on enumerations.</span></span>

<span data-ttu-id="b0e6f-214">Em nosso exemplo, estamos apenas definindo `Rack` e `ComputeServer` ; ambas as extensões para a `Device` classe.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-214">In our example, we're only defining `Rack` and `ComputeServer`; both extensions to the `Device` class.</span></span>

```powershell
enum DeviceType {
    Undefined = 0
    Compute = 1
    Storage = 2
    Networking = 4
    Communications = 8
    Power = 16
    Rack = 32
}

class Asset {
    [string]$Brand
    [string]$Model
}

class Device : Asset {
    hidden [DeviceType]$devtype = [DeviceType]::Undefined
    [string]$Status

    [DeviceType] GetDeviceType(){
        return $this.devtype
    }
}

class ComputeServer : Device {
    hidden [DeviceType]$devtype = [DeviceType]::Compute
    [string]$ProcessorIdentifier
    [string]$Hostname
}

class Rack : Device {
    hidden [DeviceType]$devtype = [DeviceType]::Rack
    hidden [int]$Slots = 8

    [string]$Datacenter
    [string]$Location
    [Device[]]$Devices = [Device[]]::new($this.Slots)

    Rack (){
        ## Just create the default rack with 8 slots
    }

    Rack ([int]$s){
        ## Add argument validation logic here
        $this.Devices = [Device[]]::new($s)
    }

    [void] AddDevice([Device]$dev, [int]$slot){
        ## Add argument validation logic here
        $this.Devices[$slot] = $dev
    }

    [void] RemoveDevice([int]$slot){
        ## Add argument validation logic here
        $this.Devices[$slot] = $null
    }
}

$FirstRack = [Rack]::new(16)
$FirstRack.Status = "Operational"
$FirstRack.Datacenter = "PNW"
$FirstRack.Location = "F03R02.J10"

(0..15).ForEach({
    $ComputeServer = [ComputeServer]::new()
    $ComputeServer.Brand = "Fabrikam, Inc."       ## Inherited from Asset
    $ComputeServer.Model = "Fbk5040"              ## Inherited from Asset
    $ComputeServer.Status = "Installed"           ## Inherited from Device
    $ComputeServer.ProcessorIdentifier = "x64"    ## ComputeServer
    $ComputeServer.Hostname = ("r1s" + $_.ToString("000")) ## ComputeServer
    $FirstRack.AddDevice($ComputeServer, $_)
  })

$FirstRack
$FirstRack.Devices
```

```Output
Datacenter : PNW
Location   : F03R02.J10
Devices    : {r1s000, r1s001, r1s002, r1s003...}
Status     : Operational
Brand      :
Model      :

ProcessorIdentifier : x64
Hostname            : r1s000
Status              : Installed
Brand               : Fabrikam, Inc.
Model               : Fbk5040

ProcessorIdentifier : x64
Hostname            : r1s001
Status              : Installed
Brand               : Fabrikam, Inc.
Model               : Fbk5040

<... content truncated here for brevity ...>

ProcessorIdentifier : x64
Hostname            : r1s015
Status              : Installed
Brand               : Fabrikam, Inc.
Model               : Fbk5040
```

### <a name="calling-base-class-constructors"></a><span data-ttu-id="b0e6f-215">Chamando construtores de classe base</span><span class="sxs-lookup"><span data-stu-id="b0e6f-215">Calling base class constructors</span></span>

<span data-ttu-id="b0e6f-216">Para invocar um construtor de classe base de uma subclasse, adicione a `base` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-216">To invoke a base class constructor from a subclass, add the `base` keyword.</span></span>

```powershell
class Person {
    [int]$Age

    Person([int]$a)
    {
        $this.Age = $a
    }
}

class Child : Person
{
    [string]$School

    Child([int]$a, [string]$s ) : base($a) {
        $this.School = $s
    }
}

[Child]$littleone = [Child]::new(10, "Silver Fir Elementary School")

$littleone.Age
```

```Output

10
```

### <a name="invoke-base-class-methods"></a><span data-ttu-id="b0e6f-217">Invocar métodos de classe base</span><span class="sxs-lookup"><span data-stu-id="b0e6f-217">Invoke base class methods</span></span>

<span data-ttu-id="b0e6f-218">Para substituir os métodos existentes em subclasses, declare métodos usando o mesmo nome e assinatura.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-218">To override existing methods in subclasses, declare methods using the same name and signature.</span></span>

```powershell
class BaseClass
{
    [int]days() {return 1}
}
class ChildClass1 : BaseClass
{
    [int]days () {return 2}
}

[ChildClass1]::new().days()
```

```Output

2
```

<span data-ttu-id="b0e6f-219">Para chamar métodos de classe base de implementações substituídas, converta para a classe base ([BaseClass] $this) na invocação.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-219">To call base class methods from overridden implementations, cast to the base class ([baseclass]$this) on invocation.</span></span>

```powershell
class BaseClass
{
    [int]days() {return 1}
}
class ChildClass1 : BaseClass
{
    [int]days () {return 2}
    [int]basedays() {return ([BaseClass]$this).days()}
}

[ChildClass1]::new().days()
[ChildClass1]::new().basedays()
```

```Output

2
1
```

### <a name="inheriting-from-interfaces"></a><span data-ttu-id="b0e6f-220">Herdando de interfaces</span><span class="sxs-lookup"><span data-stu-id="b0e6f-220">Inheriting from interfaces</span></span>

<span data-ttu-id="b0e6f-221">As classes do PowerShell podem implementar uma interface usando a mesma sintaxe de herança usada para estender classes base.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-221">PowerShell classes can implement an interface using the same inheritance syntax used to extend base classes.</span></span> <span data-ttu-id="b0e6f-222">Como as interfaces permitem várias heranças, uma classe do PowerShell que implementa uma interface pode herdar de vários tipos, separando os nomes de tipo após os dois-pontos ( `:` ) com vírgulas () `,` .</span><span class="sxs-lookup"><span data-stu-id="b0e6f-222">Because interfaces allow multiple inheritance, a PowerShell class implementing an interface may inherit from multiple types, by separating the type names after the colon (`:`) with commas (`,`).</span></span> <span data-ttu-id="b0e6f-223">Uma classe do PowerShell que implementa uma interface deve implementar todos os membros dessa interface.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-223">A PowerShell class that implements an interface must implement all the members of that interface.</span></span> <span data-ttu-id="b0e6f-224">Omitir os membros da interface de implementação causa um erro de tempo de análise no script.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-224">Omitting the implemention interface members causes a parse-time error in the script.</span></span>

> [!NOTE]
> <span data-ttu-id="b0e6f-225">Atualmente, o PowerShell não dá suporte à declaração de novas interfaces no script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-225">PowerShell does not currently support declaring new interfaces in PowerShell script.</span></span>

```powershell
class MyComparable : System.IComparable
{
    [int] CompareTo([object] $obj)
    {
        return 0;
    }
}

class MyComparableBar : bar, System.IComparable
{
    [int] CompareTo([object] $obj)
    {
        return 0;
    }
}
```

## <a name="importing-classes-from-a-powershell-module"></a><span data-ttu-id="b0e6f-226">Importando classes de um módulo do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0e6f-226">Importing classes from a PowerShell module</span></span>

<span data-ttu-id="b0e6f-227">`Import-Module` e a `#requires` instrução só importa as funções de módulo, aliases e variáveis, conforme definido pelo módulo.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-227">`Import-Module` and the `#requires` statement only import the module functions, aliases, and variables, as defined by the module.</span></span> <span data-ttu-id="b0e6f-228">As classes não são importadas.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-228">Classes are not imported.</span></span> <span data-ttu-id="b0e6f-229">A `using module` instrução importa as classes definidas no módulo.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-229">The `using module` statement imports the classes defined in the module.</span></span> <span data-ttu-id="b0e6f-230">Se o módulo não estiver carregado na sessão atual, a `using` instrução falhará.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-230">If the module isn't loaded in the current session, the `using` statement fails.</span></span> <span data-ttu-id="b0e6f-231">Para obter mais informações sobre a `using` instrução, consulte [about_Using](about_Using.md).</span><span class="sxs-lookup"><span data-stu-id="b0e6f-231">For more information about the `using` statement, see [about_Using](about_Using.md).</span></span>

<span data-ttu-id="b0e6f-232">A `using module` instrução importa classes do módulo raiz ( `ModuleToProcess` ) de um módulo de script ou de um módulo binário.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-232">The `using module` statement imports classes from the root module (`ModuleToProcess`) of a script module or binary module.</span></span> <span data-ttu-id="b0e6f-233">Ele não importa consistentemente classes definidas em módulos aninhados ou classes definidas em scripts que são originados no módulo.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-233">It does not consistently import classes defined in nested modules or classes defined in scripts that are dot-sourced into the module.</span></span> <span data-ttu-id="b0e6f-234">As classes que você deseja disponibilizar para usuários fora do módulo devem ser definidas no módulo raiz.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-234">Classes that you want to be available to users outside of the module should be defined in the root module.</span></span>

## <a name="loading-newly-changed-code-during-development"></a><span data-ttu-id="b0e6f-235">Carregando código alterado recentemente durante o desenvolvimento</span><span class="sxs-lookup"><span data-stu-id="b0e6f-235">Loading newly changed code during development</span></span>

<span data-ttu-id="b0e6f-236">Durante o desenvolvimento de um módulo de script, é comum fazer alterações no código e, em seguida, carregar a nova versão do módulo usando `Import-Module` com o parâmetro **Force** .</span><span class="sxs-lookup"><span data-stu-id="b0e6f-236">During development of a script module, it is common to make changes to the code then load the new version of the module using `Import-Module` with the **Force** parameter.</span></span> <span data-ttu-id="b0e6f-237">Isso funciona apenas para alterações nas funções no módulo raiz.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-237">This works for changes to functions in the root module only.</span></span> <span data-ttu-id="b0e6f-238">`Import-Module` não recarrega nenhum módulo aninhado.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-238">`Import-Module` does not reload any nested modules.</span></span> <span data-ttu-id="b0e6f-239">Além disso, não há como carregar nenhuma classe atualizada.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-239">Also, there is no way to load any updated classes.</span></span>

<span data-ttu-id="b0e6f-240">Para garantir que você esteja executando a versão mais recente, você deve descarregar o módulo usando o `Remove-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-240">To ensure that you are running the latest version, you must unload the module using the `Remove-Module` cmdlet.</span></span> <span data-ttu-id="b0e6f-241">`Remove-Module` Remove o módulo raiz, todos os módulos aninhados e todas as classes definidas nos módulos.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-241">`Remove-Module` removes the root module, all nested modules, and any classes defined in the modules.</span></span> <span data-ttu-id="b0e6f-242">Em seguida, você pode recarregar o módulo e as classes usando `Import-Module` e a `using module` instrução.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-242">Then you can reload the module and the classes using `Import-Module` and the `using module` statement.</span></span>

<span data-ttu-id="b0e6f-243">Outra prática de desenvolvimento comum é separar o código em arquivos diferentes.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-243">Another common development practice is to separate your code into different files.</span></span> <span data-ttu-id="b0e6f-244">Se você tiver uma função em um arquivo que usa classes definidas em outro módulo, deverá usar a `using module` instrução para garantir que as funções tenham as definições de classe necessárias.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-244">If you have function in one file that use classes defined in another module, you should using the `using module` statement to ensure that the functions have the class definitions that are needed.</span></span>

## <a name="the-psreference-type-is-not-supported-with-class-members"></a><span data-ttu-id="b0e6f-245">Não há suporte para o tipo PSReference com membros de classe</span><span class="sxs-lookup"><span data-stu-id="b0e6f-245">The PSReference type is not supported with class members</span></span>

<span data-ttu-id="b0e6f-246">O uso da `[ref]` conversão de tipo com um membro de classe falha silenciosamente.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-246">Using the `[ref]` type-cast with a class member silently fails.</span></span> <span data-ttu-id="b0e6f-247">As APIs que usam `[ref]` parâmetros não podem ser usadas com membros de classe.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-247">APIs that use `[ref]` parameters cannot be used with class members.</span></span> <span data-ttu-id="b0e6f-248">A classe **PSReference** foi projetada para dar suporte a objetos com.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-248">The **PSReference** class was designed to support COM objects.</span></span> <span data-ttu-id="b0e6f-249">Objetos COM têm casos em que você precisa passar um valor por referência.</span><span class="sxs-lookup"><span data-stu-id="b0e6f-249">COM objects have cases where you need to pass a value in by reference.</span></span>

<span data-ttu-id="b0e6f-250">Para obter mais informações sobre o `[ref]` tipo, consulte [classe PSReference](/dotnet/api/system.management.automation.psreference).</span><span class="sxs-lookup"><span data-stu-id="b0e6f-250">For more information about the `[ref]` type, see [PSReference Class](/dotnet/api/system.management.automation.psreference).</span></span>

## <a name="see-also"></a><span data-ttu-id="b0e6f-251">Confira também</span><span class="sxs-lookup"><span data-stu-id="b0e6f-251">See also</span></span>

- [<span data-ttu-id="b0e6f-252">About_hidden</span><span class="sxs-lookup"><span data-stu-id="b0e6f-252">About_hidden</span></span>](About_hidden.md)
- [<span data-ttu-id="b0e6f-253">about_Enum</span><span class="sxs-lookup"><span data-stu-id="b0e6f-253">about_Enum</span></span>](about_Enum.md)
- [<span data-ttu-id="b0e6f-254">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="b0e6f-254">about_Language_Keywords</span></span>](about_language_keywords.md)
- [<span data-ttu-id="b0e6f-255">about_Methods</span><span class="sxs-lookup"><span data-stu-id="b0e6f-255">about_Methods</span></span>](about_methods.md)
- [<span data-ttu-id="b0e6f-256">about_Using</span><span class="sxs-lookup"><span data-stu-id="b0e6f-256">about_Using</span></span>](about_using.md)
