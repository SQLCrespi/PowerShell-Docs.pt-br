---
ms.date: 06/12/2017
keywords: wmf,powershell,instalação
title: Criando tipos personalizados usando classes do PowerShell
ms.openlocfilehash: c2c50fb65ce4931fcf6ae529b4146df391c831c4
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "71147836"
---
# <a name="creating-custom-types-using-powershell-classes"></a>Criando tipos personalizados usando classes do PowerShell

O PowerShell 5.0 trouxe a capacidade de definir classes e outros tipos definidos pelo usuário usando uma sintaxe formal e semântica que são semelhantes a outras linguagens de programação orientadas ao objeto. O objetivo é permitir que desenvolvedores e profissionais de TI adotem o PowerShell para uma grande variedade de casos de uso, simplificar o desenvolvimento de artefatos do PowerShell (como recursos DSC) e acelerar a cobertura de superfícies de gerenciamento.

## <a name="supported-scenarios-in-this-release"></a>Cenários com suporte nesta versão

- Definir recursos DSC e os tipos associados usando a linguagem do PowerShell
- Definir tipos personalizados no PowerShell usando constructos de programação orientada a objeto conhecidos, como classes, propriedades, métodos, etc.
- Suporte à herança com classe no PowerShell e no recurso DSC de classe base
- Depurar tipos usando a linguagem do PowerShell
- Gerar e manipular exceções usando mecanismos formais e no nível certo

## <a name="declare-base-class"></a>Declarar a classe base

É possível declarar uma classe do PowerShell como um tipo base para outra classe do PowerShell.

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

Também é possível usar os tipos existentes do .NET Framework como classes base:

```powershell
class MyIntList : system.collections.generic.list[int]
{

}

$list = [MyIntList]::new()

$list.Add(100)

$list[0] # return 100
```

### <a name="call-base-class-constructor"></a>Chamar o construtor de classe base

Para chamar um construtor de classe base desde uma subclasse, use a palavra-chave **base**:

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

Se uma classe base tiver um construtor padrão (sem parâmetros), será possível omitir uma chamada explícita de construtor:

```powershell
class C : B
{
    C([int]$c) {}
}
```

### <a name="call-base-class-method"></a>Chamar o método de classe base

É possível substituir os métodos existentes nas subclasses. Para fazer isso, declare métodos usando o mesmo nome e a mesma assinatura:

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

Para chamar métodos de classe base a partir de implementações substituídas, transmita para a classe base (`[baseClass]$this`) na chamada:

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

Todos os métodos do PowerShell são virtuais. É possível ocultar métodos não virtuais do .NET em uma subclasse usando a mesma sintaxe que você usaria para uma substituição declarando os métodos com o mesmo nome e a mesma assinatura.

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

### <a name="declare-implemented-interface"></a>Declarar a interface implementada

Será possível declarar interfaces implementadas após tipos base, ou imediatamente após dois-pontos (:), se não houver nenhum tipo base especificado. Separe todos os nomes de tipo usando vírgulas. Isso é semelhante à sintaxe do C#.

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

## <a name="new-language-features-in-powershell-50"></a>Novos recursos de linguagem no PowerShell 5.0

O PowerShell 5.0 introduz os seguintes novos elementos de linguagem:

### <a name="class-keyword"></a>Palavra-chave class

A palavra-chave `class` define uma nova classe. Este é um tipo real do .NET Framework. Membros de classe são públicos, mas somente públicos dentro do escopo do módulo. Não é possível se referir ao nome de tipo como uma cadeia de caracteres (por exemplo, `New-Object` não funciona), e nesta versão não é possível usar um literal de tipo (por exemplo, `[MyClass]`) fora do arquivo de script ou módulo no qual a classe é definida.

```powershell
class MyClass
{
    ...
}
```

### <a name="enum-keyword-and-enumerations"></a>Palavra-chave Enum e enumerações

O suporte à palavra-chave `enum` foi adicionado e usa uma nova linha como o delimitador. No momento, não é possível definir um enumerador em relação a si mesmo. No entanto, é possível iniciar uma enumeração em relação a outra enumeração, conforme mostrado no exemplo a seguir. Além disso, o tipo base não pode ser especificado; ele é sempre `[int]`.

```powershell
enum Color2
{
    Yellow = [Color]::Blue
}
```

Um valor de enumeração deve ser uma constante de tempo de análise. Não é possível defini-lo como o resultado de um comando chamado.

```powershell
enum MyEnum
{
    Enum1
    Enum2
    Enum3 = 42
    Enum4 = [int]::MaxValue
}
```

Enums dão suporte a operações aritméticas, conforme mostrado no exemplo a seguir.

```powershell
enum SomeEnum { Max = 42 }
enum OtherEnum { Max = [SomeEnum]::Max + 1 }
```

### <a name="import-dscresource"></a>Import-DscResource

`Import-DscResource` agora é uma palavra-chave dinâmica real. O PowerShell analisa o módulo raiz do módulo especificado pesquisando classes que contêm o atributo **DscResource**.

### <a name="implementingassembly"></a>ImplementingAssembly

Um novo campo, **ImplementingAssembly**, foi adicionado a **ModuleInfo**. Ele é definido como o assembly dinâmico criado para um módulo de script, caso o script defina classes, ou como o assembly carregado para módulos binários. Ele não é definido quando **ModuleType** é **Manifest**.

A reflexão sobre o campo **ImplementingAssembly** descobre recursos em um módulo. Isso significa que é possível descobrir recursos escritos no PowerShell ou em outras linguagens gerenciadas.

Campos com inicializadores:

```powershell
[int] $i = 5
```

`Static` é compatível. Ele funciona como um atributo, como as restrições de tipo. Pode ser especificado em qualquer ordem.

```powershell
static [int] $count = 0
```

Um tipo é opcional.

```powershell
$s = "hello"
```

Todos os membros são públicos.

### <a name="constructors-and-instantiation"></a>Construtores e instanciação

As classes do PowerShell podem ter construtores. Elas têm o mesmo nome que sua classe. Os construtores podem ser sobrecarregados. Há suporte para construtores estáticos. As propriedades com expressões de inicialização são inicializadas antes da execução de qualquer código em um construtor. As propriedades estáticas são inicializadas antes do corpo de um construtor estático, e as propriedades de instância são inicializadas antes do corpo do construtor não estático. Atualmente, não há nenhuma sintaxe para chamar um construtor de outro construtor [como a sintaxe do C\# ": this()"]. A solução alternativa é definir um método `Init()` comum.

#### <a name="creating-instances"></a>Criando instâncias

> [!NOTE]
> No PowerShell 5.0, `New-Object` não funciona com classes definidas no PowerShell. Além disso, o nome de tipo é visível apenas lexicalmente, o que significa que ele não é visível fora do módulo ou do script que define a classe. As funções podem retornar instâncias de uma classe definida no PowerShell. Essas instâncias funcionam fora do módulo ou script.

1. Criando uma instância usando o construtor padrão.

   ```powershell
   $a = [MyClass]::new()
   ```

1. Chamando um construtor com um parâmetro

   ```powershell
   $b = [MyClass]::new(42)
   ```

1. Transmitir uma matriz para um construtor com vários parâmetros.

   ```powershell
   $c = [MyClass]::new(@(42,43,44), "Hello")
   ```

O método pseudoestático chamado `new()` funciona com tipos do .NET, conforme mostrado no exemplo a seguir.

```powershell
[hashtable]::new()
```

#### <a name="discovering-constructors"></a>Descobrindo construtores

Agora você pode ver as sobrecargas do construtor com `Get-Member` ou conforme mostrado neste exemplo:

```powershell
PS> [hashtable]::new
OverloadDefinitions
-------------------
hashtable new()
hashtable new(int capacity)
hashtable new(int capacity, float loadFactor)
```

`Get-Member -Static` lista os construtores, para que seja possível exibir sobrecargas como qualquer outro método. O desempenho dessa sintaxe também é consideravelmente mais rápido do que o de `New-Object`.

### <a name="methods"></a>Métodos

Um método de classe do PowerShell é implementado como um **ScriptBlock** que tem apenas um bloco end. Todos os métodos são públicos. Veja a seguir um exemplo de definição de um método chamado **DoSomething**.

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

Invocação de método:

```powershell
$b = [MyClass]::new()
$b.DoSomething(42)
```

Também há suporte para métodos sobrecarregados.

### <a name="properties"></a>Propriedades

Todas as propriedades são públicas. As propriedades exigem uma nova linha ou um ponto-e-vírgula. Se nenhum tipo de objeto for especificado, o tipo de propriedade será o objeto.

As propriedades que usam atributos de validação ou atributos de transformação de argumento (como, `[ValidateSet("aaa")]`) funcionam como esperado.

### <a name="hidden"></a>Hidden

Uma nova palavra-chave, `Hidden`, foi adicionada. `Hidden` pode ser aplicado a propriedades e métodos (incluindo construtores).

Os membros ocultos são públicos, mas não aparecem na saída de `Get-Member`, a menos que o parâmetro `-Force` seja adicionado. Membros ocultos não são incluídos durante o preenchimento de tabulação ou uso do IntelliSense, a menos que o preenchimento ocorra na classe que define o membro oculto.

Um novo atributo, **System.Management.Automation.HiddenAttribute**, foi adicionado para que o código do C\# possa ter a mesma semântica dentro do PowerShell.

### <a name="return-types"></a>Tipos de retorno

O tipo de retorno é um contrato. O valor retornado é convertido para o tipo esperado. Se nenhum tipo de retorno for especificado, o tipo de retorno será **nulo**. Não há transmissão de objetos. Os objetos não podem ser gravados no pipeline, seja intencionalmente ou por engano.

### <a name="attributes"></a>Atributos

Dois novos atributos, **DscResource** e **DscProperty** foram adicionados.

### <a name="lexical-scoping-of-variables"></a>Escopo léxico de variáveis

Apresentamos a seguir um exemplo de como o escopo léxico funciona nesta versão.

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

## <a name="end-to-end-example"></a>Exemplo de ponta a ponta

O exemplo a seguir cria algumas classes personalizadas para implementar uma DSL (linguagem de folha de estilos dinâmica) em HTML. Em seguida, o exemplo adiciona funções auxiliares para criar tipos específicos de elementos como parte da classe de elemento, como estilos de título e tabelas, já que os tipos não podem ser usados fora do escopo de um módulo.

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
