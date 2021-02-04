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
# <a name="about-classes"></a>Sobre classes

## <a name="short-description"></a>Descrição breve
Descreve como você pode usar classes para criar seus próprios tipos personalizados.

## <a name="long-description"></a>Descrição longa

O PowerShell 5,0 adiciona uma sintaxe formal para definir classes e outros tipos definidos pelo usuário. A adição de classes permite que desenvolvedores e profissionais de ti adotem o PowerShell para uma variedade maior de casos de uso. Ele simplifica o desenvolvimento de artefatos do PowerShell e acelera a cobertura de superfícies de gerenciamento.

Uma declaração de classe é um plano gráfico usado para criar instâncias de objetos em tempo de execução. Quando você define uma classe, o nome da classe é o nome do tipo. Por exemplo, se você declarar uma classe chamada **dispositivo** e inicializar uma variável `$dev` para uma nova instância do **dispositivo**, `$dev` será um objeto ou instância do tipo **dispositivo**. Cada instância do **dispositivo** pode ter valores diferentes em suas propriedades.

## <a name="supported-scenarios"></a>Cenários com suporte

- Defina tipos personalizados no PowerShell usando semântica familiar de programação orientada a objeto, como classes, propriedades, métodos, herança, etc.
- Depurar tipos usando a linguagem do PowerShell.
- Gere e manipule exceções usando mecanismos formais.
- Defina os recursos de DSC e seus tipos associados usando a linguagem do PowerShell.

## <a name="syntax"></a>Sintaxe

As classes são declaradas usando a seguinte sintaxe:

```syntax
class <class-name> [: [<base-class>][,<interface-list]] {
    [[<attribute>] [hidden] [static] <property-definition> ...]
    [<class-name>([<constructor-argument-list>])
      {<constructor-statement-list>} ...]
    [[<attribute>] [hidden] [static] <method-definition> ...]
}
```

As classes são instanciadas usando qualquer uma das seguintes sintaxes:

```syntax
[$<variable-name> =] New-Object -TypeName <class-name> [
  [-ArgumentList] <constructor-argument-list>]
```

```syntax
[$<variable-name> =] [<class-name>]::new([<constructor-argument-list>])
```

> [!NOTE]
> Ao usar a `[<class-name>]::new()` sintaxe, os colchetes em volta do nome da classe são obrigatórios. Os colchetes sinalizam uma definição de tipo para o PowerShell.

### <a name="example-syntax-and-usage"></a>Exemplo de sintaxe e uso

Este exemplo mostra a sintaxe mínima necessária para criar uma classe utilizável.

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

## <a name="class-properties"></a>Propriedades da classe

As propriedades são variáveis declaradas no escopo de classe. Uma propriedade pode ser de qualquer tipo interno ou uma instância de outra classe. As classes não têm nenhuma restrição no número de propriedades que elas têm.

### <a name="example-class-with-simple-properties"></a>Classe de exemplo com propriedades simples

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

### <a name="example-complex-types-in-class-properties"></a>Exemplos de tipos complexos em Propriedades de classe

Este exemplo define uma classe de **rack** vazia usando a classe de **dispositivo** . Os exemplos, a seguir, mostram como adicionar dispositivos ao rack e como começar com um rack pré-carregado.

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

## <a name="class-methods"></a>Métodos de classe

Os métodos definem as ações que uma classe pode executar. Os métodos podem receber parâmetros que fornecem dados de entrada. Os métodos podem retornar a saída. Os dados retornados por um método podem ser qualquer tipo de dados definido.

Ao definir um método para uma classe, você faz referência ao objeto de classe atual usando a `$this` variável automática. Isso permite que você acesse Propriedades e outros métodos definidos na classe atual.

### <a name="example-simple-class-with-properties-and-methods"></a>Exemplo de classe simples com propriedades e métodos

Estendendo a classe **rack** para adicionar e remover dispositivos de ou para ele.

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

## <a name="output-in-class-methods"></a>Saída em métodos de classe

Os métodos devem ter um tipo de retorno definido. Se um método não retornar a saída, o tipo de saída deverá ser `[void]` .

Em métodos de classe, nenhum objeto é enviado para o pipeline, exceto aqueles mencionados na `return` instrução. Não há saída acidental para o pipeline a partir do código.

> [!NOTE]
> Isso é fundamentalmente diferente de como as funções do PowerShell lidam com a saída, onde tudo vai para o pipeline.

Os erros de não finalização gravados no fluxo de erros de dentro de um método de classe não são passados. Você deve usar `throw` o para retonar um erro de encerramento.
Usando os `Write-*` cmdlets, você ainda pode gravar nos fluxos de saída do PowerShell de dentro de um método de classe. No entanto, isso deve ser evitado para que o método emita objetos usando apenas a `return` instrução.

### <a name="method-output"></a>Saída do método

Este exemplo demonstra nenhuma saída acidental para o pipeline a partir de métodos de classe, exceto na `return` instrução.

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

## <a name="constructor"></a>Construtor

Os construtores permitem que você defina valores padrão e valide a lógica do objeto no momento da criação da instância da classe. Os construtores têm o mesmo nome que a classe. Os construtores podem ter argumentos para inicializar os membros de dados do novo objeto.

A classe pode ter zero ou mais construtores definidos. Se nenhum construtor for definido, a classe receberá um construtor sem parâmetros padrão. Esse construtor inicializa todos os membros para seus valores padrão. Os tipos de objeto e cadeias de caracteres recebem valores nulos. Quando você define o construtor, nenhum construtor padrão sem parâmetros é criado. Crie um construtor sem parâmetros se um for necessário.

### <a name="constructor-basic-syntax"></a>Sintaxe básica do Construtor

Neste exemplo, a classe de dispositivo é definida com propriedades e um construtor.
Para usar essa classe, o usuário deve fornecer valores para os parâmetros listados no construtor.

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

### <a name="example-with-multiple-constructors"></a>Exemplo com vários construtores

Neste exemplo, a classe de **dispositivo** é definida com propriedades, um construtor padrão e um construtor para inicializar a instância.

O construtor padrão define a **marca** como **indefinida** e deixa o **modelo** e o **SKU do fornecedor** com valores nulos.

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

## <a name="hidden-attribute"></a>Atributo Hidden

O `hidden` atributo oculta uma propriedade ou um método. A propriedade ou o método ainda é acessível para o usuário e está disponível em todos os escopos nos quais o objeto está disponível. Os membros ocultos são ocultos do `Get-Member` cmdlet e não podem ser exibidos usando o preenchimento com Tab ou o IntelliSense fora da definição de classe.

Para obter mais informações, consulte [About_hidden](About_hidden.md).

### <a name="example-using-hidden-attributes"></a>Exemplo usando atributos ocultos

Quando um objeto de **rack** é criado, o número de Slots para dispositivos é um valor fixo que não deve ser alterado a qualquer momento. Esse valor é conhecido no momento da criação.

O uso do atributo Hidden permite que o desenvolvedor Mantenha o número de Slots ocultos e impede que alterações não intencionais sejam alteradas no tamanho do rack.

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

Observe que a propriedade **Slots** não é mostrada na `$r1` saída. No entanto, o tamanho foi alterado pelo construtor.

## <a name="static-attribute"></a>Atributo estático

O `static` atributo define uma propriedade ou um método que existe na classe e não precisa de nenhuma instância.

Uma propriedade estática está sempre disponível, independentemente da instanciação de classe. Uma propriedade estática é compartilhada entre todas as instâncias da classe. Um método estático está disponível sempre. Todas as propriedades estáticas em tempo real para toda a sessão abrangem.

### <a name="example-using-static-attributes-and-methods"></a>Exemplo usando atributos e métodos estáticos

Suponha que os racks instanciados aqui existam no seu data center. Portanto, você gostaria de acompanhar os racks em seu código.

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

### <a name="testing-static-property-and-method-exist"></a>O teste da propriedade estática e do método existe

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

Observe que o número de racks aumenta cada vez que você executa este exemplo.

## <a name="property-validation-attributes"></a>Atributos de validação de propriedade

Os atributos de validação permitem testar os valores fornecidos às propriedades que atendem aos requisitos definidos. A validação é disparada no momento em que o valor é atribuído. Consulte [about_Functions_Advanced_Parameters](about_functions_advanced_parameters.md).

### <a name="example-using-validation-attributes"></a>Exemplo usando atributos de validação

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

## <a name="inheritance-in-powershell-classes"></a>Herança em classes do PowerShell

Você pode estender uma classe criando uma nova classe que deriva de uma classe existente. A classe derivada herda as propriedades da classe base. Você pode adicionar ou substituir métodos e propriedades conforme necessário.

O PowerShell não dá suporte a várias heranças. Classes não podem herdar de mais de uma classe. No entanto, você pode usar interfaces para essa finalidade.

A implementação de herança é definida pelo `:` operador; o que significa estender essa classe ou implementar essas interfaces. A classe derivada deve estar sempre na extrema esquerda na declaração de classe.

### <a name="example-using-simple-inheritance-syntax"></a>Exemplo usando sintaxe de herança simples

Este exemplo mostra a sintaxe simples de herança de classe do PowerShell.

```powershell
Class Derived : Base {...}
```

Este exemplo mostra a herança com uma declaração de interface chegando após a classe base.

```powershell
Class Derived : Base, Interface {...}
```

### <a name="example-of-simple-inheritance-in-powershell-classes"></a>Exemplo de herança simples em classes do PowerShell

Neste exemplo, as classes de **rack** e **dispositivo** usadas nos exemplos anteriores são mais bem definidas para: evitar repetições de propriedade, alinhar melhor as propriedades comuns e reutilizar a lógica de negócios comum.

A maioria dos objetos na data center são ativos da empresa, o que faz sentido começar a controlá-los como ativos. Os tipos de dispositivo são definidos pela `DeviceType` enumeração, consulte [about_Enum](about_Enum.md) para obter detalhes sobre enumerações.

Em nosso exemplo, estamos apenas definindo `Rack` e `ComputeServer` ; ambas as extensões para a `Device` classe.

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

### <a name="calling-base-class-constructors"></a>Chamando construtores de classe base

Para invocar um construtor de classe base de uma subclasse, adicione a `base` palavra-chave.

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

### <a name="invoke-base-class-methods"></a>Invocar métodos de classe base

Para substituir os métodos existentes em subclasses, declare métodos usando o mesmo nome e assinatura.

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

Para chamar métodos de classe base de implementações substituídas, converta para a classe base ([BaseClass] $this) na invocação.

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

### <a name="inheriting-from-interfaces"></a>Herdando de interfaces

As classes do PowerShell podem implementar uma interface usando a mesma sintaxe de herança usada para estender classes base. Como as interfaces permitem várias heranças, uma classe do PowerShell que implementa uma interface pode herdar de vários tipos, separando os nomes de tipo após os dois-pontos ( `:` ) com vírgulas () `,` . Uma classe do PowerShell que implementa uma interface deve implementar todos os membros dessa interface. Omitir os membros da interface de implementação causa um erro de tempo de análise no script.

> [!NOTE]
> Atualmente, o PowerShell não dá suporte à declaração de novas interfaces no script do PowerShell.

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

## <a name="importing-classes-from-a-powershell-module"></a>Importando classes de um módulo do PowerShell

`Import-Module` e a `#requires` instrução só importa as funções de módulo, aliases e variáveis, conforme definido pelo módulo. As classes não são importadas. A `using module` instrução importa as classes definidas no módulo. Se o módulo não estiver carregado na sessão atual, a `using` instrução falhará. Para obter mais informações sobre a `using` instrução, consulte [about_Using](about_Using.md).

A `using module` instrução importa classes do módulo raiz ( `ModuleToProcess` ) de um módulo de script ou de um módulo binário. Ele não importa consistentemente classes definidas em módulos aninhados ou classes definidas em scripts que são originados no módulo. As classes que você deseja disponibilizar para usuários fora do módulo devem ser definidas no módulo raiz.

## <a name="loading-newly-changed-code-during-development"></a>Carregando código alterado recentemente durante o desenvolvimento

Durante o desenvolvimento de um módulo de script, é comum fazer alterações no código e, em seguida, carregar a nova versão do módulo usando `Import-Module` com o parâmetro **Force** . Isso funciona apenas para alterações nas funções no módulo raiz. `Import-Module` não recarrega nenhum módulo aninhado. Além disso, não há como carregar nenhuma classe atualizada.

Para garantir que você esteja executando a versão mais recente, você deve descarregar o módulo usando o `Remove-Module` cmdlet. `Remove-Module` Remove o módulo raiz, todos os módulos aninhados e todas as classes definidas nos módulos. Em seguida, você pode recarregar o módulo e as classes usando `Import-Module` e a `using module` instrução.

Outra prática de desenvolvimento comum é separar o código em arquivos diferentes. Se você tiver uma função em um arquivo que usa classes definidas em outro módulo, deverá usar a `using module` instrução para garantir que as funções tenham as definições de classe necessárias.

## <a name="the-psreference-type-is-not-supported-with-class-members"></a>Não há suporte para o tipo PSReference com membros de classe

O uso da `[ref]` conversão de tipo com um membro de classe falha silenciosamente. As APIs que usam `[ref]` parâmetros não podem ser usadas com membros de classe. A classe **PSReference** foi projetada para dar suporte a objetos com. Objetos COM têm casos em que você precisa passar um valor por referência.

Para obter mais informações sobre o `[ref]` tipo, consulte [classe PSReference](/dotnet/api/system.management.automation.psreference).

## <a name="see-also"></a>Confira também

- [About_hidden](About_hidden.md)
- [about_Enum](about_Enum.md)
- [about_Language_Keywords](about_language_keywords.md)
- [about_Methods](about_methods.md)
- [about_Using](about_using.md)
