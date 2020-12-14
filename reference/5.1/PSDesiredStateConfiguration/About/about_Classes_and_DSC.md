---
description: Descreve como você pode usar classes para desenvolver no PowerShell com a DSC (configuração de estado desejado).
keywords: powershell, cmdlet
Locale: en-US
ms.date: 1/11/2019
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Classes_and_DSC
ms.openlocfilehash: 21a013bb817367dd2a11cc0826263d0f3203796b
ms.sourcegitcommit: cc72c40315fd2981d3009b335accbfa52d57640c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/30/2020
ms.locfileid: "96349817"
---
# <a name="about-classes-and-desired-state-configuration"></a>Sobre classes e configuração de estado desejado

## <a name="short-description"></a>Descrição breve

Descreve como você pode usar classes para desenvolver no PowerShell com a DSC (configuração de estado desejado).

## <a name="long-description"></a>Descrição longa

A partir do Windows PowerShell 5,0, o idioma foi adicionado para definir classes e outros tipos definidos pelo usuário, usando sintaxe formal e semântica que são semelhantes a outras linguagens de programação orientadas a objeto. O objetivo é permitir que desenvolvedores e profissionais de ti adotem o Windows PowerShell para uma variedade maior de casos de uso, simplifiquem o desenvolvimento de artefatos do PowerShell, como recursos de DSC, e acelerem a cobertura de superfícies de gerenciamento.

## <a name="supported-scenarios"></a>Cenários com suporte

Os cenários a seguir têm suporte:

- Defina os recursos de DSC e seus tipos associados usando a linguagem do PowerShell.
- Defina tipos personalizados no PowerShell usando construções de programação orientada a objeto familiares, como classes, propriedades, métodos e herança.
- Tipos de depuração usando a linguagem do PowerShell.
- Gere e manipule exceções usando mecanismos formais e no nível certo.

## <a name="define-dsc-resources-with-classes"></a>Definir recursos de DSC com classes

Além das alterações de sintaxe, as principais diferenças entre um recurso de DSC definido por classe e um provedor de recursos de DSC de cmdlet são os seguintes itens:

- Um arquivo MOF (Management Object Format) não é necessário.
- Uma subpasta DSCResource na pasta do módulo não é necessária.
- Um arquivo de módulo do PowerShell pode conter várias classes de recursos DSC.

## <a name="create-a-class-defined-dsc-resource-provider"></a>Criar um provedor de recursos DSC definido pela classe

O exemplo a seguir é um provedor de recursos DSC definido pela classe que é salvo como um módulo, MyDSCResource. psm1. Você sempre deve incluir uma propriedade de chave em um provedor de recursos de DSC definido pela classe.

```powershell
enum Ensure
{
    Absent
    Present
}

<#
    This resource manages the file in a specific path.
    [DscResource()] indicates the class is a DSC resource
#>

[DscResource()]
class FileResource
{
    <#
        This property is the fully qualified path to the file that is
        expected to be present or absent.

        The [DscProperty(Key)] attribute indicates the property is a
        key and its value uniquely identifies a resource instance.
        Defining this attribute also means the property is required
        and DSC will ensure a value is set before calling the resource.

        A DSC resource must define at least one key property.
    #>
    [DscProperty(Key)]
    [string]$Path

    <#
        This property indicates if the settings should be present or absent
        on the system. For present, the resource ensures the file pointed
        to by $Path exists. For absent, it ensures the file point to by
        $Path does not exist.

        The [DscProperty(Mandatory)] attribute indicates the property is
        required and DSC will guarantee it is set.

        If Mandatory is not specified or if it is defined as
        Mandatory=$false, the value is not guaranteed to be set when DSC
        calls the resource.  This is appropriate for optional properties.
    #>
    [DscProperty(Mandatory)]
    [Ensure] $Ensure

    <#
        This property defines the fully qualified path to a file that will
        be placed on the system if $Ensure = Present and $Path does not
        exist.

        NOTE: This property is required because [DscProperty(Mandatory)] is
        set.
    #>
    [DscProperty(Mandatory)]
    [string] $SourcePath

    <#
        This property reports the file's create timestamp.

        [DscProperty(NotConfigurable)] attribute indicates the property is
        not configurable in DSC configuration.  Properties marked this way
        are populated by the Get() method to report additional details
        about the resource when it is present.

    #>
    [DscProperty(NotConfigurable)]
    [Nullable[datetime]] $CreationTime

    <#
        This method is equivalent of the Set-TargetResource script function.
        It sets the resource to the desired state.
    #>
    [void] Set()
    {
        $fileExists = $this.TestFilePath($this.Path)
        if($this.ensure -eq [Ensure]::Present)
        {
            if(-not $fileExists)
            {
                $this.CopyFile()
            }
        }
        else
        {
            if($fileExists)
            {
                Write-Verbose -Message "Deleting the file $($this.Path)"
                Remove-Item -LiteralPath $this.Path -Force
            }
        }
    }

    <#

        This method is equivalent of the Test-TargetResource script
        function. It should return True or False, showing whether the
        resource is in a desired state.
    #>
    [bool] Test()
    {
        $present = $this.TestFilePath($this.Path)

        if($this.Ensure -eq [Ensure]::Present)
        {
            return $present
        }
        else
{
            return -not $present
        }
    }

    <#
        This method is equivalent of the Get-TargetResource script function.
        The implementation should use the keys to find appropriate
        resources. This method returns an instance of this class with the
        updated key properties.
    #>
    [FileResource] Get()
    {
        $present = $this.TestFilePath($this.Path)

        if ($present)
        {
            $file = Get-ChildItem -LiteralPath $this.Path
            $this.CreationTime = $file.CreationTime
            $this.Ensure = [Ensure]::Present
        }
        else
        {
            $this.CreationTime = $null
            $this.Ensure = [Ensure]::Absent
        }
        return $this
    }

    <#
        Helper method to check if the file exists and it is correct file
    #>
    [bool] TestFilePath([string] $location)
    {
        $present = $true

        $item = Get-ChildItem -LiteralPath $location -ea Ignore
        if ($null -eq $item)
        {
            $present = $false
        }
        elseif( $item.PSProvider.Name -ne "FileSystem")
        {
            throw "Path $($location) is not a file path."
        }
        elseif($item.PSIsContainer)
        {
            throw "Path $($location) is a directory path."
        }
        return $present
    }

    <#
        Helper method to copy file from source to path
    #>
    [void] CopyFile()
    {
        if(-not $this.TestFilePath($this.SourcePath))
        {
            throw "SourcePath $($this.SourcePath) is not found."
        }

        [System.IO.FileInfo]
        $destFileInfo = new-object System.IO.FileInfo($this.Path)

        if (-not $destFileInfo.Directory.Exists)
        {
            $FullName = $destFileInfo.Directory.FullName
            $Message = "Creating directory $FullName"

            Write-Verbose -Message $Message

            #use CreateDirectory instead of New-Item to avoid code
            # to handle the non-terminating error
            [System.IO.Directory]::CreateDirectory($FullName)
        }

        if(Test-Path -LiteralPath $this.Path -PathType Container)
        {
            throw "Path $($this.Path) is a directory path"
        }

        Write-Verbose -Message "Copying $this.SourcePath to $this.Path"

        #DSC engine catches and reports any error that occurs
        Copy-Item -Path $this.SourcePath -Destination $this.Path -Force
    }
}
```

## <a name="create-a-module-manifest"></a>Criar um manifesto de módulo

Depois de criar o provedor de recursos DSC definido por classe e salvá-lo como um módulo, crie um manifesto de módulo para o módulo. Para disponibilizar um recurso baseado em classes para o mecanismo de DSC, você precisa incluir uma declaração `DscResourcesToExport` no arquivo de manifesto que instrui o módulo para exportar recursos. Neste exemplo, o manifesto de módulo a seguir é salvo como MyDscResource.psd1.

```powershell
@{

# Script module or binary module file associated with this manifest.
RootModule = 'MyDscResource.psm1'

DscResourcesToExport = 'FileResource'

# Version number of this module.
ModuleVersion = '1.0'

# ID used to uniquely identify this module
GUID = '81624038-5e71-40f8-8905-b1a87afe22d7'

# Author of this module
Author = 'Microsoft Corporation'

# Company or vendor of this module
CompanyName = 'Microsoft Corporation'

# Copyright statement for this module
Copyright = '(c) 2014 Microsoft. All rights reserved.'

# Description of the functionality provided by this module
# Description = ''

# Minimum version of the PowerShell engine required by this module
PowerShellVersion = '5.0'

# Name of the PowerShell host required by this module
# PowerShellHostName = ''

}
```

## <a name="deploy-a-dsc-resource-provider"></a>Implantar um provedor de recursos de DSC

Implante o novo provedor de recursos de DSC criando uma pasta MyDscResource no `$pshome\Modules` ou no `$env:SystemDrive\ProgramFiles\WindowsPowerShell\Modules` .

Não é necessário criar uma subpasta DSCResource. Faça uma cópia do módulo e dos arquivos de manifesto de módulo (MyDscResource.psm1 e MyDscResource.psd1) e cole-os na pasta MyDscResource.

Desse ponto em diante, você cria e executa um script de configuração como faria com qualquer recurso DSC.

## <a name="create-a-dsc-configuration-script"></a>Criar um script de configuração da DSC

Depois de salvar a classe e os arquivos de manifesto na estrutura de pastas, conforme descrito anteriormente, você pode criar uma configuração que use o novo recurso. A configuração a seguir faz referência ao módulo MyDSCResource. Salve a configuração como um script MyResource.ps1.

Para obter informações sobre como executar uma configuração DSC, consulte [visão geral da configuração de estado desejado do Windows PowerShell](/powershell/scripting/dsc/overview/dscforengineers).

Antes de executar a configuração, crie `C:\test.txt` . A configuração verifica se o arquivo existe em `c:\test\test.txt` . Se o arquivo não existir, a configuração copiará o arquivo de `C:\test.txt` .

```powershell
Configuration Test
{
    Import-DSCResource -module MyDscResource
    FileResource file
    {
        Path = "C:\test\test.txt"
        SourcePath = "C:\test.txt"
        Ensure = "Present"
    }
}
Test
Start-DscConfiguration -Wait -Force Test
```

Execute esse script como faria com qualquer script de configuração DSC. Para iniciar a configuração, em um console do PowerShell com privilégios elevados, execute o seguinte:

`PS C:\test> .\MyResource.ps1`

## <a name="inheritance-in-powershell-classes"></a>Herança em classes do PowerShell

### <a name="declare-base-classes-for-powershell-classes"></a>Declarar classes base para classes do PowerShell

Você pode declarar uma classe do PowerShell como um tipo base para outra classe do PowerShell, conforme mostrado no exemplo a seguir, em que **fruta** é um tipo base para a **Apple**.

```powershell
class fruit
{
    [int]sold() {return 100500}
}

class apple : fruit {}
    [apple]::new().sold() # return 100500
```

### <a name="declare-implemented-interfaces-for-powershell-classes"></a>Declarar interfaces implementadas para classes do PowerShell

Você pode declarar interfaces implementadas após os tipos base, ou imediatamente após dois-pontos ( `:` ) se não houver nenhum tipo base especificado. Separe todos os nomes de tipo usando vírgulas. Isso é semelhante à sintaxe C#.

```powershell
class MyComparable : system.IComparable
{
    [int] CompareTo([object] $obj)
    {
        return 0;
    }
}

class MyComparableTest : test, system.IComparable
{
    [int] CompareTo([object] $obj)
    {
        return 0;
    }
}
```

### <a name="call-base-class-constructors"></a>Chamar construtores de classe base

Para chamar um construtor de classe base de uma subclasse, adicione a `base` palavra-chave, conforme mostrado no exemplo a seguir:

```powershell
class A {
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

Se uma classe base tiver um construtor padrão (sem parâmetros), você poderá omitir uma chamada de Construtor explícita, conforme mostrado.

```powershell
class C : B
{
    C([int]$c) {}
}
```

### <a name="call-base-class-methods"></a>Chamar métodos de classe base

É possível substituir os métodos existentes nas subclasses. Para fazer a substituição, declare métodos usando o mesmo nome e assinatura.

```powershell
class baseClass
{
    [int]days() {return 100500}
}
class childClass1 : baseClass
{
    [int]days () {return 200600}
}

    [childClass1]::new().days() # return 200600
```

Para chamar métodos de classe base de implementações substituídas, converta para a classe base `([baseclass]$this)` na invocação.

```powershell
class childClass2 : baseClass
{
    [int]days()
    {
        return 3 * ([baseClass]$this).days()
    }
}

    [childClass2]::new().days() # return 301500
```

Todos os métodos do PowerShell são virtuais. Você pode ocultar métodos não virtuais do .NET em uma subclasse usando a mesma sintaxe que você faz para uma substituição: declare métodos com o mesmo nome e assinatura.

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

### <a name="current-limitations-with-class-inheritance"></a>Limitações atuais com herança de classe

Uma limitação com herança de classe é que não há nenhuma sintaxe para declarar interfaces no PowerShell.

## <a name="defining-custom-types-in-powershell"></a>Definindo tipos personalizados no PowerShell

O Windows PowerShell 5,0 introduziu vários elementos de linguagem.

### <a name="class-keyword"></a>Palavra-chave class

Define uma nova classe.
A `class` palavra-chave é um tipo true .NET Framework.
Os membros da classe são públicos.

```powershell
class MyClass
{
}
```

### <a name="enum-keyword-and-enumerations"></a>Palavra-chave Enum e enumerações

O suporte para a `enum` palavra-chave foi adicionado e é uma alteração significativa. O `enum` delimitador é atualmente uma nova linha. Uma solução alternativa para aqueles que já estão usando `enum` é inserir um e comercial ( `&` ) antes da palavra. Limitações atuais: não é possível definir um enumerador em termos de si mesmo, mas você pode inicializar `enum` em termos de outro `enum` , conforme mostrado no exemplo a seguir:

O tipo base não pode ser especificado no momento. O tipo base é sempre [int].

```powershell
enum Color2
{
    Yellow = [Color]::Blue
}
```

Um valor de enumeração deve ser uma constante de tempo de análise. O valor do enumerador não pode ser definido como o resultado de um comando invocado.

```powershell
enum MyEnum
{
    Enum1
    Enum2
    Enum3 = 42
    Enum4 = [int]::MaxValue
}
```

`Enum` dá suporte a operações aritméticas, conforme mostrado no exemplo a seguir:

```powershell
enum SomeEnum { Max = 42 }
enum OtherEnum { Max = [SomeEnum]::Max + 1 }
```

### <a name="hidden-keyword"></a>Palavra-chave Hidden

A `hidden` palavra-chave, introduzida no Windows PowerShell 5,0, oculta os membros da classe dos `Get-Member` resultados padrão. Especifique a Propriedade Hidden, conforme mostrado na seguinte linha:

```powershell
hidden [type] $classmember = <value>
```

Os membros ocultos não são exibidos usando o preenchimento com Tab ou o IntelliSense, a menos que a conclusão ocorra na classe que define o membro oculto.

Um novo atributo, **System. Management. Automation. hiddenattribute**, foi adicionado, para que o código C# possa ter a mesma semântica no PowerShell.

Para obter mais informações, consulte [about_Hidden](../../Microsoft.PowerShell.Core/About/about_hidden.md).

### <a name="import-dscresource"></a>Import-DscResource

`Import-DscResource` agora é uma palavra-chave dinâmica real. O PowerShell analisa o módulo raiz do módulo especificado pesquisando classes que contêm o atributo DscResource.

### <a name="properties"></a>Propriedades

Um novo campo, `ImplementingAssembly` , foi adicionado a `ModuleInfo` . Se o script definir classes ou se o assembly carregado para módulos binários `ImplementingAssembly` for definido como o assembly dinâmico criado para um módulo de script. Ele não é definido quando ModuleType = Manifest.

A reflexão no `ImplementingAssembly` campo descobre os recursos em um módulo. Isso significa que é possível descobrir recursos escritos no PowerShell ou em outras linguagens gerenciadas.

Campos com inicializadores.

`[int] $i = 5`

Static tem suporte e funciona como um atributo, semelhante às restrições de tipo, para que possa ser especificado em qualquer ordem.

`static [int] $count = 0`

Um tipo é opcional.

`$s = "hello"`

Todos os membros são públicos. As propriedades exigem uma nova linha ou um ponto-e-vírgula. Se nenhum tipo de objeto for especificado, o tipo de propriedade será **objeto**.

### <a name="constructors-and-instantiation"></a>Construtores e instanciação

As classes do PowerShell podem ter construtores que têm o mesmo nome de sua classe. Os construtores podem ser sobrecarregados. Há suporte para construtores estáticos.
As propriedades com expressões de inicialização são inicializadas antes da execução de qualquer código em um construtor. As propriedades estáticas são inicializadas antes do corpo de um construtor estático, e as propriedades de instância são inicializadas antes do corpo do construtor não estático. Atualmente, não há nenhuma sintaxe para chamar um construtor de outro construtor, como a sintaxe C#: `": this()")` . A solução alternativa é definir um método comum de Init.

Veja a seguir as maneiras de instanciar classes:

- Criando uma instância usando o construtor padrão. Observe que `New-Object` o não tem suporte nesta versão.

  `$a = [MyClass]::new()`

- Chamando um construtor com um parâmetro.

  `$b = [MyClass]::new(42)`

- Passando uma matriz para um construtor com vários parâmetros

  `$c = [MyClass]::new(@(42,43,44), "Hello")`

Para esta versão, o nome do tipo só é visível lexicalmente, o que significa que ele não é visível fora do módulo ou script que define a classe. As funções podem retornar instâncias de uma classe definida no PowerShell, e as instâncias funcionam bem fora do módulo ou script.

O `Get-Member` parâmetro **estático** lista construtores, para que você possa exibir sobrecargas como qualquer outro método. O desempenho dessa sintaxe também é consideravelmente mais rápido do que o de `New-Object`.

O método pseudoestático chamado **new** funciona com tipos do .NET, conforme mostrado no exemplo a seguir. `[hashtable]::new()`

Agora você pode ver as sobrecargas do construtor com `Get-Member` ou conforme mostrado neste exemplo:

```powershell
[hashtable]::new
OverloadDefinitions
-------------------
hashtable new()
hashtable new(int capacity)
hashtable new(int capacity, float loadFactor)
```

### <a name="methods"></a>Métodos

Um método de classe do PowerShell é implementado como um **ScriptBlock** que tem apenas um bloco end. Todos os métodos são públicos. Veja a seguir um exemplo de definição de um método chamado **DoSomething**.

```powershell
class MyClass
{
    DoSomething($x)
    {
        $this._doSomething($x)       # method syntax
    }
    private _doSomething($a) {}
}
```

### <a name="method-invocation"></a>Invocação de método

Há suporte para métodos sobrecarregados. Os métodos sobrecarregados são nomeados da mesma forma que um método existente, mas diferenciados pelos valores especificados.

```powershell
$b = [MyClass]::new()
$b.DoSomething(42)
```

### <a name="invocation"></a>Invocação

Consulte [invocação de método](#method-invocation).

### <a name="attributes"></a>Atributos

Três novos atributos foram adicionados: `DscResource` , `DscResourceKey` e `DscResourceMandatory` .

### <a name="return-types"></a>Tipos de retorno

O tipo de retorno é um contrato. O valor retornado é convertido para o tipo esperado.
Se nenhum tipo de retorno for especificado, o tipo de retorno será nulo. Não há nenhum streaming de objetos e os objetos não podem ser gravados no pipeline intencionalmente ou por acidente.

### <a name="lexical-scoping-of-variables"></a>Escopo léxico de variáveis

Apresentamos a seguir um exemplo de como o escopo léxico funciona nesta versão.

```powershell
$d = 42  # Script scope

function bar
{
    $d = 0  # Function scope
    [MyClass]::DoSomething()
}

class MyClass
{
    static [object] DoSomething()
    {
        return $d  # error, not found dynamically
        return $script:d # no error

        $d = $script:d
        return $d # no error, found lexically
    }
}

$v = bar
$v -eq $d # true
```

## <a name="example-create-custom-classes"></a>Exemplo: criar classes personalizadas

O exemplo a seguir cria várias classes personalizadas novas para implementar uma DSL (linguagem de folha de estilos dinâmica) HTML. O exemplo adiciona funções auxiliares para criar tipos de elementos específicos como parte da classe de elemento, como estilos de título e tabelas, porque os tipos não podem ser usados fora do escopo de um módulo.

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
        $text += $Head
        $text += "`n</head>`n<body>`n"
        $text += $Body -join "`n" # Render all of the body elements
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
    [string] Render() { return "<title>$Title</title>" }
    [string] ToString() { return $this.Render() }
}

class Element
{
    [string] $Tag
    [string] $Text
    [hashtable] $Attributes
    [string] Render() {
        $attributesText= ""
        if ($Attributes)
        {
            foreach ($attr in $Attributes.Keys)
            {
                $attributesText = " $attr=`"$($Attributes[$attr])`""
            }
        }

        return "<${tag}${attributesText}>$text</$tag>`n"
    }
    [string] ToString() { return $this.Render() }
}

#
# Helper functions for creating specific element types on top of the classes.
# These are required because types aren't visible outside of the module.
#
function H1 {[Element] @{Tag = "H1"; Text = $args.foreach{$_} -join " "}}
function H2 {[Element] @{Tag = "H2"; Text = $args.foreach{$_} -join " "}}
function H3 {[Element] @{Tag = "H3"; Text = $args.foreach{$_} -join " "}}
function P  {[Element] @{Tag = "P" ; Text = $args.foreach{$_} -join " "}}
function B  {[Element] @{Tag = "B" ; Text = $args.foreach{$_} -join " "}}
function I  {[Element] @{Tag = "I" ; Text = $args.foreach{$_} -join " "}}
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
    $bodyText +=  $Properties.foreach{TH $_}
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
function TH  {([Element] @{Tag="TH"; Text=$args.foreach{$_} -join " "})}
function TR  {([Element] @{Tag="TR"; Text=$args.foreach{$_} -join " "})}
function TD  {([Element] @{Tag="TD"; Text=$args.foreach{$_} -join " "})}

function Style
{
    return  [Element]  @{
        Tag = "style"
        Text = "$args"
    }
}

# Takes a hash table, casts it to and HTML document
# and then returns the resulting type.
#
function Html ([HTML] $doc) { return $doc }
```

## <a name="see-also"></a>Veja também

[about_DesiredStateConfiguration](../../Microsoft.PowerShell.Core/About/about_desiredstateconfiguration.md)

[about_Enum](../../Microsoft.PowerShell.Core/About/about_Enum.md)

[about_Hidden](../../Microsoft.PowerShell.Core/About/about_hidden.md)

[about_Language_Keywords](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[about_Methods](../../Microsoft.PowerShell.Core/About/about_Methods.md)

[Criar recursos personalizados de configuração de estado desejado do Windows PowerShell](/powershell/scripting/dsc/resources/authoringResource)
