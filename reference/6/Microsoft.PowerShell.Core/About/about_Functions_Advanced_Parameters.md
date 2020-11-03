---
description: Explica como adicionar parâmetros a funções avançadas.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 10/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_advanced_parameters?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_Advanced_Parameters
ms.openlocfilehash: 1d33fcd6ccb665ceae1db91783542385fd49b9cc
ms.sourcegitcommit: 3b1779890f828130a9d73aebf17ebffae511728f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "93196648"
---
# <a name="about-functions-advanced-parameters"></a>Sobre os parâmetros avançados do Functions

## <a name="short-description"></a>Descrição breve

Explica como adicionar parâmetros a funções avançadas.

## <a name="long-description"></a>Descrição longa

Você pode adicionar parâmetros às funções avançadas que escreve e usar atributos de parâmetro e argumentos para limitar os valores de parâmetro que os usuários de função enviam com o parâmetro.

Os parâmetros que você adiciona à função estão disponíveis para os usuários além dos parâmetros comuns que o PowerShell adiciona automaticamente a todos os cmdlets e funções avançadas. Para obter mais informações sobre os parâmetros comuns do PowerShell, consulte [about_CommonParameters](about_CommonParameters.md).

A partir do PowerShell 3,0, você pode usar nivelamento com `@Args` para representar os parâmetros em um comando. Nivelamento é válido em funções simples e avançadas. Para obter mais informações, consulte [about_Functions](about_Functions.md) e [about_Splatting](about_Splatting.md).

## <a name="type-conversion-of-parameter-values"></a>Conversão de tipo de valores de parâmetro

Quando você fornece cadeias de caracteres como argumentos para parâmetros que esperam um tipo diferente, o PowerShell converte implicitamente as cadeias de caracteres no tipo de destino do parâmetro.
As funções avançadas executam a análise invariável de cultura de valores de parâmetro.

Por outro lado, uma conversão sensível à cultura é executada durante a associação de parâmetro para cmdlets compilados.

Neste exemplo, criamos um cmdlet e uma função de script que usam um `[datetime]` parâmetro. A cultura atual é alterada para usar as configurações de alemão.
Uma data formatada em alemão é passada para o parâmetro.

```powershell
# Create a cmdlet that accepts a [datetime] argument.
Add-Type @'
  using System;
  using System.Management.Automation;
  [Cmdlet("Get", "Date_Cmdlet")]
  public class GetFooCmdlet : Cmdlet {

    [Parameter(Position=0)]
    public DateTime Date { get; set; }

    protected override void ProcessRecord() {
      WriteObject(Date);
    }
  }
'@ -PassThru | % Assembly | Import-Module

[cultureinfo]::CurrentCulture = 'de-DE'
$dateStr = '19-06-2018'

Get-Date_Cmdlet $dateStr
```

```Output
Dienstag, 19. Juni 2018 00:00:00
```

Como mostrado acima, os cmdlets usam a análise sensível à cultura para converter a cadeia de caracteres.

```powershell
# Define an equivalent function.
function Get-Date_Func {
  param(
    [DateTime] $Date
  )
  process {
    $Date
  }
}

[cultureinfo]::CurrentCulture = 'de-DE'

# This German-format date string doesn't work with the invariant culture.
# E.g., [datetime] '19-06-2018' breaks.
$dateStr = '19-06-2018'

Get-Date_Func $dateStr
```

As funções avançadas usam a análise de cultura invariável, o que resulta no erro a seguir.

```Output
Get-Date_Func : Cannot process argument transformation on parameter 'Date'. Cannot convert
 value "19-06-2018" to type "System.DateTime". Error: "String was not recognized as a valid
 DateTime."
At line:13 char:15
+ Get-Date_Func $dateStr
+               ~~~~~~~~
    + CategoryInfo          : InvalidData: (:) [Get-Date_Func], ParameterBindingArgumentTransformationException
    + FullyQualifiedErrorId : ParameterArgumentTransformationError,Get-Date_Func
```

## <a name="static-parameters"></a>Parâmetros estáticos

Parâmetros estáticos são parâmetros que estão sempre disponíveis na função.
A maioria dos parâmetros nos cmdlets e scripts do PowerShell são parâmetros estáticos.

O exemplo a seguir mostra a declaração de um parâmetro **ComputerName** que tem as seguintes características:

- É obrigatório (obrigatório).
- Ele usa a entrada do pipeline.
- Ele usa uma matriz de cadeias de caracteres como entrada.

```powershell
Param(
    [Parameter(Mandatory=$true,
    ValueFromPipeline=$true)]
    [String[]]
    $ComputerName
)
```

## <a name="attributes-of-parameters"></a>Atributos de parâmetros

Esta seção descreve os atributos que você pode adicionar a parâmetros de função.

Todos os atributos são opcionais. No entanto, se você omitir o atributo **CmdletBinding** , para ser reconhecido como uma função avançada, a função deverá incluir o atributo **Parameter** .

Você pode adicionar um ou vários atributos em cada declaração de parâmetro. Não há limite para o número de atributos que você pode adicionar a uma declaração de parâmetro.

### <a name="parameter-attribute"></a>Atributo de parâmetro

O atributo de **parâmetro** é usado para declarar os atributos dos parâmetros de função.

O atributo de **parâmetro** é opcional e você pode omiti-lo se nenhum dos parâmetros de suas funções precisarem de atributos. Mas, para ser reconhecido como uma função avançada, em vez de uma função simples, uma função deve ter o atributo **CmdletBinding** ou o atributo de **parâmetro** , ou ambos.

O atributo **Parameter** tem argumentos que definem as características do parâmetro, como se o parâmetro é obrigatório ou opcional.

Use a sintaxe a seguir para declarar o atributo de **parâmetro** , um argumento e um valor de argumento. Os parênteses que delimitam o argumento e seu valor devem seguir o **parâmetro** sem nenhum espaço intermediário.

```powershell
Param(
    [Parameter(Argument=value)]
    $ParameterName
)
```

Use vírgulas para separar os argumentos entre parênteses. Use a sintaxe a seguir para declarar dois argumentos do atributo **Parameter** .

```powershell
Param(
    [Parameter(Argument1=value1,
    Argument2=value2)]
)
```

Os tipos de argumento boolianos do atributo de **parâmetro** são padrão como **false** quando omitidos do atributo de **parâmetro** . Defina o valor do argumento como `$true` ou apenas liste o argumento por nome. Por exemplo, os atributos de **parâmetro** a seguir são equivalentes.

```powershell
Param(
    [Parameter(Mandatory=$true)]
)

# Boolean arguments can be defined using this shorthand syntax

Param(
    [Parameter(Mandatory)]
)
```

Se você usar o atributo **Parameter** sem argumentos, como uma alternativa ao uso do atributo **CmdletBinding** , os parênteses que seguem o nome do atributo ainda serão necessários.

```powershell
Param(
    [Parameter()]
    $ParameterName
)
```

#### <a name="mandatory-argument"></a>Argumento obrigatório

O `Mandatory` argumento indica que o parâmetro é obrigatório. Se esse argumento não for especificado, o parâmetro será opcional.

O exemplo a seguir declara o parâmetro **ComputerName** . Ele usa o `Mandatory` argumento para tornar o parâmetro obrigatório.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [String[]]
    $ComputerName
)
```

#### <a name="position-argument"></a>Argumento de posição

O `Position` argumento determina se o nome do parâmetro é necessário quando o parâmetro é usado em um comando. Quando uma declaração de parâmetro inclui o `Position` argumento, o nome do parâmetro pode ser omitido e o PowerShell identifica o valor do parâmetro sem nome por sua posição, ou ordem, na lista de valores de parâmetro não nomeados no comando.

Se o `Position` argumento não for especificado, o nome do parâmetro ou um alias de nome de parâmetro ou abreviatura, deverá preceder o valor do parâmetro sempre que o parâmetro for usado em um comando.

Por padrão, todos os parâmetros de função são posicionais. O PowerShell atribui números de posição a parâmetros na ordem em que os parâmetros são declarados na função. Para desabilitar esse recurso, defina o valor do `PositionalBinding` argumento do atributo **CmdletBinding** como `$False` . O `Position` argumento tem precedência sobre o valor do `PositionalBinding` argumento do atributo **CmdletBinding** . Para obter mais informações, consulte `PositionalBinding` em [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).

O valor do `Position` argumento é especificado como um inteiro. Um valor de posição de **0** representa a primeira posição no comando, um valor de posição **1** representa a segunda posição no comando e assim por diante.

Se uma função não tiver parâmetros posicionais, o PowerShell atribuirá posições a cada parâmetro com base na ordem em que os parâmetros são declarados.
No entanto, como prática recomendada, não confie nessa atribuição. Quando desejar que os parâmetros sejam posicionais, use o `Position` argumento.

O exemplo a seguir declara o parâmetro **ComputerName** . Ele usa o `Position` argumento com um valor de **0** . Como resultado, quando `-ComputerName` é omitido do comando, seu valor deve ser o primeiro ou apenas o valor de parâmetro não nomeado no comando.

```powershell
Param(
    [Parameter(Position=0)]
    [String[]]
    $ComputerName
)
```

#### <a name="parametersetname-argument"></a>Argumento ParameterSetName

O `ParameterSetName` argumento especifica o conjunto de parâmetros ao qual um parâmetro pertence. Se nenhum conjunto de parâmetros for especificado, o parâmetro pertencerá a todos os conjuntos de parâmetros definidos pela função. Portanto, para ser exclusivo, cada conjunto de parâmetros deve ter pelo menos um parâmetro que não seja membro de nenhum outro conjunto de parâmetros.

> [!NOTE]
> Para um cmdlet ou uma função, há um limite de conjuntos de parâmetros 32.

O exemplo a seguir declara um parâmetro **ComputerName** no conjunto de `Computer` parâmetros, um parâmetro **username** no conjunto de `User` parâmetros e um parâmetro **Summary** em ambos os conjuntos de parâmetros.

```powershell
Param(
    [Parameter(Mandatory=$true,
    ParameterSetName="Computer")]
    [String[]]
    $ComputerName,

    [Parameter(Mandatory=$true,
    ParameterSetName="User")]
    [String[]]
    $UserName,

    [Parameter(Mandatory=$false)]
    [Switch]
    $Summary
)
```

Você pode especificar apenas um `ParameterSetName` valor em cada argumento e apenas um `ParameterSetName` argumento em cada atributo de **parâmetro** . Para indicar que um parâmetro aparece em mais de um conjunto de parâmetros, adicione atributos de **parâmetro** adicionais.

O exemplo a seguir adiciona explicitamente o parâmetro **Summary** aos `Computer` `User` conjuntos de parâmetros e. O parâmetro **Summary** é opcional no `Computer` conjunto de parâmetros e obrigatório no `User` conjunto de parâmetros.

```powershell
Param(
    [Parameter(Mandatory=$true,
    ParameterSetName="Computer")]
    [String[]]
    $ComputerName,

    [Parameter(Mandatory=$true,
    ParameterSetName="User")]
    [String[]]
    $UserName,

    [Parameter(Mandatory=$false, ParameterSetName="Computer")]
    [Parameter(Mandatory=$true, ParameterSetName="User")]
    [Switch]
    $Summary
)
```

Para obter mais informações sobre conjuntos de parâmetros, consulte [sobre conjuntos de parâmetros](about_parameter_sets.md).

#### <a name="valuefrompipeline-argument"></a>Argumento ValueFromPipeline

O `ValueFromPipeline` argumento indica que o parâmetro aceita entrada de um objeto de pipeline. Especifique esse argumento se a função aceitar o objeto inteiro, não apenas uma propriedade do objeto.

O exemplo a seguir declara um parâmetro **ComputerName** que é obrigatório e aceita um objeto que é passado para a função do pipeline.

```powershell
Param(
    [Parameter(Mandatory=$true,
    ValueFromPipeline=$true)]
    [String[]]
    $ComputerName
)
```

#### <a name="valuefrompipelinebypropertyname-argument"></a>Argumento ValueFromPipelineByPropertyName

O `ValueFromPipelineByPropertyName` argumento indica que o parâmetro aceita entrada de uma propriedade de um objeto de pipeline. A propriedade do objeto deve ter o mesmo nome ou alias que o parâmetro.

Por exemplo, se a função tiver um parâmetro **ComputerName** e o objeto piped tiver uma propriedade **ComputerName** , o valor da propriedade **ComputerName** será atribuído ao parâmetro **ComputerName** da função.

O exemplo a seguir declara um parâmetro **ComputerName** que é obrigatório e aceita a entrada da propriedade **ComputerName** do objeto que é passada para a função por meio do pipeline.

```powershell
Param(
    [Parameter(Mandatory=$true,
    ValueFromPipelineByPropertyName=$true)]
    [String[]]
    $ComputerName
)
```

> [!NOTE]
> Um parâmetro tipado que aceita entrada de pipeline ( `by Value` ) ou ( `by PropertyName` ) permite o uso de blocos de script de _ligação de atraso_ no parâmetro.
>
> O bloco de script de _ligação de atraso_ é executado automaticamente durante o **parâmetrobinding** . O resultado é associado ao parâmetro. A associação de atraso não funciona para parâmetros definidos como tipo `ScriptBlock` ou `System.Object` . O bloco de script é passado _sem_ ser invocado.
>
> Você pode ler sobre blocos _de script de ligação de atraso_ aqui [about_Script_Blocks. MD](about_Script_Blocks.md).

#### <a name="valuefromremainingarguments-argument"></a>Argumento ValueFromRemainingArguments

O `ValueFromRemainingArguments` argumento indica que o parâmetro aceita todos os valores do parâmetro no comando que não estão atribuídos a outros parâmetros da função.

O exemplo a seguir declara um parâmetro **Value** que é obrigatório e um parâmetro **remanescente** que aceita todos os valores de parâmetro restantes que são enviados para a função.

```powershell
function Test-Remainder
{
     param(
         [string]
         [Parameter(Mandatory = $true, Position=0)]
         $Value,
         [string[]]
         [Parameter(Position=1, ValueFromRemainingArguments)]
         $Remaining)
     "Found $($Remaining.Count) elements"
     for ($i = 0; $i -lt $Remaining.Count; $i++)
     {
        "${i}: $($Remaining[$i])"
     }
}
Test-Remainder first one,two
```

```Output
Found 2 elements
0: one
1: two
```

> [!NOTE]
> Antes do PowerShell 6,2, a coleção **ValueFromRemainingArguments** foi unida como entidade única sob o índice **0** .

#### <a name="helpmessage-argument"></a>Argumento HelpMessage

O `HelpMessage` argumento especifica uma cadeia de caracteres que contém uma breve descrição do parâmetro ou seu valor. O PowerShell exibe essa mensagem no prompt que aparece quando um valor de parâmetro obrigatório está ausente em um comando. Esse argumento não tem nenhum efeito nos parâmetros opcionais.

O exemplo a seguir declara um parâmetro **ComputerName** obrigatório e uma mensagem de ajuda que explica o valor do parâmetro esperado.

Se não houver outra sintaxe de [Ajuda baseada em comentários](./about_comment_based_help.md) para a função (por exemplo, `.SYNOPSIS` ), essa mensagem também aparecerá na `Get-Help` saída.

```powershell
Param(
    [Parameter(Mandatory=$true,
    HelpMessage="Enter one or more computer names separated by commas.")]
    [String[]]
    $ComputerName
)
```

### <a name="alias-attribute"></a>Atributo de alias

O atributo **alias** estabelece um nome alternativo para o parâmetro.
Não há limite para o número de aliases que você pode atribuir a um parâmetro.

O exemplo a seguir mostra uma declaração de parâmetro que adiciona os aliases **CN** e **MachineName** ao parâmetro **ComputerName** obrigatório.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [Alias("CN","MachineName")]
    [String[]]
    $ComputerName
)
```

### <a name="supportswildcards-attribute"></a>Atributo SupportsWildcards

O atributo **SupportsWildcards** é usado para indicar que o parâmetro aceita valores curinga. O exemplo a seguir mostra uma declaração de parâmetro para um parâmetro de **caminho** obrigatório que dá suporte a valores curinga.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [SupportsWildcards()]
    [String[]]
    $Path
)
```

O uso desse atributo não habilita automaticamente o suporte a curingas. O desenvolvedor do cmdlet deve implementar o código para manipular a entrada curinga. Os curingas com suporte podem variar de acordo com a API subjacente ou o provedor do PowerShell. Para obter mais informações, consulte [about_Wildcards](about_Wildcards.md).

### <a name="parameter-and-variable-validation-attributes"></a>Atributos de validação de parâmetro e variável

Atributos de validação direcionam o PowerShell para testar os valores de parâmetro que os usuários enviam quando chamam a função avançada. Se os valores de parâmetro falharem no teste, um erro será gerado e a função não será chamada. A validação de parâmetro é aplicada somente à entrada fornecida e quaisquer outros valores como valores padrão não são validados.

Você também pode usar os atributos de validação para restringir os valores que os usuários podem especificar para variáveis. Quando você usa um conversor de tipo junto com um atributo de validação, o conversor de tipo precisa ser definido antes do atributo.

```powershell
[int32][AllowNull()] $number = 7
```

### <a name="allownull-validation-attribute"></a>Atributo de validação AllowNull

O atributo **AllowNull** permite que o valor de um parâmetro obrigatório seja `$null` . O exemplo a seguir declara um parâmetro **ComputerInfo** de Hashtable que pode ter um valor **nulo** .

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [AllowNull()]
    [hashtable]
    $ComputerInfo
)
```

> [!NOTE]
> O atributo **AllowNull** não funcionará se o conversor de tipo estiver definido como cadeia de caracteres, pois o tipo de cadeia de caracteres não aceitará um valor nulo. Você pode usar o atributo **AllowEmptyString** para este cenário.

### <a name="allowemptystring-validation-attribute"></a>Atributo de validação AllowEmptyString

O atributo **AllowEmptyString** permite que o valor de um parâmetro obrigatório seja uma cadeia de caracteres vazia ( `""` ). O exemplo a seguir declara um parâmetro **ComputerName** que pode ter um valor de cadeia de caracteres vazio.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [AllowEmptyString()]
    [String]
    $ComputerName
)
```

### <a name="allowemptycollection-validation-attribute"></a>Atributo de validação AllowEmptyCollection

O atributo **AllowEmptyCollection** permite que o valor de um parâmetro obrigatório seja uma coleção vazia `@()` . O exemplo a seguir declara um parâmetro **ComputerName** que pode ter um valor de coleção Vazio.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [AllowEmptyCollection()]
    [String[]]
    $ComputerName
)
```

### <a name="validatecount-validation-attribute"></a>Atributo de validação ValidateCount

O atributo **ValidateCount** especifica o número mínimo e máximo de valores de parâmetro que um parâmetro aceita. O PowerShell gerará um erro se o número de valores de parâmetro no comando que chama a função estiver fora desse intervalo.

A declaração de parâmetro a seguir cria um parâmetro **ComputerName** que usa um para cinco valores de parâmetro.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateCount(1,5)]
    [String[]]
    $ComputerName
)
```

### <a name="validatelength-validation-attribute"></a>Atributo de validação ValidateLength

O atributo **ValidateLength** especifica o número mínimo e máximo de caracteres em um parâmetro ou valor de variável. O PowerShell gerará um erro se o comprimento de um valor especificado para um parâmetro ou uma variável estiver fora do intervalo.

No exemplo a seguir, cada nome de computador deve ter de um a dez caracteres.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateLength(1,10)]
    [String[]]
    $ComputerName
)
```

No exemplo a seguir, o valor da variável `$number` deve ter no mínimo um caractere de comprimento e no máximo dez caracteres.

```powershell
[Int32][ValidateLength(1,10)]$number = '01'
```

> [!NOTE]
> Neste exemplo, o valor de `01` é encapsulado entre aspas simples. O atributo **ValidateLength** não aceitará um número sem ser quebrado entre aspas.

### <a name="validatepattern-validation-attribute"></a>Atributo de validação ValidatePattern

O atributo **ValidatePattern** especifica uma expressão regular que é comparada ao parâmetro ou ao valor da variável. O PowerShell gerará um erro se o valor não corresponder ao padrão de expressão regular.

No exemplo a seguir, o valor do parâmetro deve conter um número de quatro dígitos e cada dígito deve ser um número zero a nove.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidatePattern("[0-9][0-9][0-9][0-9]")]
    [String[]]
    $ComputerName
)
```

No exemplo a seguir, o valor da variável `$number` deve ser exatamente um número de quatro dígitos e cada dígito deve ser um número zero a nove.

```powershell
[Int32][ValidatePattern("^[0-9][0-9][0-9][0-9]$")]$number = 1111
```

### <a name="validaterange-validation-attribute"></a>Atributo de validação ValidateRange

O atributo **ValidateRange** especifica um intervalo numérico ou um valor de enumeração **ValidateRangeKind** para cada parâmetro ou valor de variável.
O PowerShell gerará um erro se qualquer valor estiver fora desse intervalo.

A enumeração **ValidateRangeKind** permite os seguintes valores:

- **Positivo** -um número maior que zero.
- **Negativo** – um número menor que zero.
- Não **positivo** – um número menor ou igual a zero.
- Não **negativo** -um número maior ou igual a zero.

No exemplo a seguir, o valor do parâmetro de **tentativas** deve estar entre zero e dez.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateRange(0,10)]
    [Int]
    $Attempts
)
```

No exemplo a seguir, o valor da variável `$number` deve estar entre zero e dez.

```powershell
[Int32][ValidateRange(0,10)]$number = 5
```

No exemplo a seguir, o valor da variável `$number` deve ser maior que zero.

```powershell
[Int32][ValidateRange("Positive")]$number = 1
```

### <a name="validatescript-validation-attribute"></a>Atributo de validação ValidateScript

O atributo **ValidateScript** especifica um script que é usado para validar um parâmetro ou valor de variável. O PowerShell canaliza o valor para o script e gera um erro se o script retorna `$false` ou se o script gera uma exceção.

Quando você usa o atributo **ValidateScript** , o valor que está sendo validado é mapeado para a `$_` variável. Você pode usar a `$_` variável para fazer referência ao valor no script.

No exemplo a seguir, o valor do parâmetro **EventDate** deve ser maior ou igual à data atual.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateScript({$_ -ge (Get-Date)})]
    [DateTime]
    $EventDate
)
```

No exemplo a seguir, o valor da variável `$date` deve ser maior ou igual à data e hora atuais.

```powershell
[DateTime][ValidateScript({$_ -ge (Get-Date)})]$date = (Get-Date)
```

> [!NOTE]
> Se você usar **ValidateScript** , não será possível passar um `$null` valor para o parâmetro. Quando você passa um valor nulo, **ValidateScript** não pode validar o argumento.

### <a name="validateset-attribute"></a>Atributo ValidateSet

O atributo **ValidateSet** especifica um conjunto de valores válidos para um parâmetro ou variável e habilita o preenchimento com Tab. O PowerShell gerará um erro se um parâmetro ou valor de variável não corresponder a um valor no conjunto. No exemplo a seguir, o valor do parâmetro **Detail** só pode ser baixo, Average ou High.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateSet("Low", "Average", "High")]
    [String[]]
    $Detail
)
```

No exemplo a seguir, o valor da variável `$flavor` deve ser chocolate, morango ou baunilha.

```powershell
[ValidateSet("Chocolate", "Strawberry", "Vanilla")]
[String]$flavor = "Strawberry"
```

A validação ocorre sempre que essa variável é atribuída mesmo dentro do script. Por exemplo, os resultados a seguir resultam em um erro em tempo de execução:

```powershell
Param(
    [ValidateSet("hello", "world")]
    [String]$Message
)

$Message = "bye"
```

#### <a name="dynamic-validateset-values"></a>Valores dinâmicos de ValidateSet

Você pode usar uma **classe** para gerar dinamicamente os valores para **ValidateSet** no tempo de execução. No exemplo a seguir, os valores válidos para a variável `$Sound` são gerados por meio de uma **classe** chamada **soundnames** que verifica três caminhos do sistema de arquivos em busca de arquivos de som disponíveis:

```powershell
Class SoundNames : System.Management.Automation.IValidateSetValuesGenerator {
    [String[]] GetValidValues() {
        $SoundPaths = '/System/Library/Sounds/',
            '/Library/Sounds','~/Library/Sounds'
        $SoundNames = ForEach ($SoundPath in $SoundPaths) {
            If (Test-Path $SoundPath) {
                (Get-ChildItem $SoundPath).BaseName
            }
        }
        return [String[]] $SoundNames
    }
}
```

`[SoundNames]`Em seguida, a classe é implementada como um valor Dynamic **validset** da seguinte maneira:

```powershell
Param(
    [ValidateSet([SoundNames])]
    [String]$Sound
)
```

### <a name="validatenotnull-validation-attribute"></a>Atributo de validação ValidateNotNull

O atributo **ValidateNotNull** especifica que o valor do parâmetro não pode ser `$null` . O PowerShell gerará um erro se o valor do parâmetro for `$null` .

O atributo **ValidateNotNull** é projetado para ser usado quando o parâmetro é opcional e o tipo é indefinido ou tem um conversor de tipo que não pode converter implicitamente um valor nulo como **objeto** . Se você especificar um tipo que irá converter implicitamente um valor nulo, como uma **cadeia de caracteres** , o valor nulo será convertido em uma cadeia de caracteres vazia mesmo ao usar o atributo **ValidateNotNull** . Para este cenário, use o **ValidateNotNullOrEmpty**

No exemplo a seguir, o valor do parâmetro **ID** não pode ser `$null` .

```powershell
Param(
    [Parameter(Mandatory=$false)]
    [ValidateNotNull()]
    $ID
)
```

### <a name="validatenotnullorempty-validation-attribute"></a>Atributo de validação ValidateNotNullOrEmpty

O atributo **ValidateNotNullOrEmpty** especifica que o valor do parâmetro não pode ser `$null` e não pode ser uma cadeia de caracteres vazia ( `""` ). O PowerShell gerará um erro se o parâmetro for usado em uma chamada de função, mas seu valor for `$null` , uma cadeia de caracteres vazia ( `""` ) ou uma matriz vazia `@()` .

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateNotNullOrEmpty()]
    [String[]]
    $UserName
)
```

### <a name="validatedrive-validation-attribute"></a>Atributo de validação ValidateDrive

O atributo **ValidateDrive** especifica que o valor do parâmetro deve representar o caminho, que está se referindo apenas a unidades permitidas. O PowerShell gerará um erro se o valor do parâmetro se referir a unidades diferentes das permitidas. A existência do caminho, exceto para a própria unidade, não é verificada.

Se você usar o caminho relativo, a unidade atual deverá estar na lista unidade permitida.

```powershell
Param(
    [ValidateDrive("C", "D", "Variable", "Function")]
    [String]$Path
)
```

### <a name="validateuserdrive-validation-attribute"></a>Atributo de validação ValidateUserDrive

O atributo **ValidateUserDrive** especifica que o valor do parâmetro deve representar o caminho, que está se referindo à `User` unidade. O PowerShell gerará um erro se o caminho se referir a uma unidade diferente. O atributo de validação só testa a existência da parte da unidade do caminho.

Se você usar o caminho relativo, a unidade atual deverá ser `User` .

```powershell
function Test-UserDrivePath{
    [OutputType([bool])]
    Param(
      [Parameter(Mandatory=, Position=0)][ValidateUserDrive()][String]$Path
      )
    $True
}

Test-UserDrivePath -Path C:\
```

```Output
Test-UserDrivePath: Cannot validate argument on parameter 'Path'. The path
argument drive C does not belong to the set of approved drives: User.
Supply a path argument with an approved drive.
```

```powershell
Test-UserDrivePath -Path 'User:\A_folder_that_does_not_exist'
```

```Output
Test-UserDrivePath: Cannot validate argument on parameter 'Path'. Cannot
find drive. A drive with the name 'User' does not exist.
```

Você pode definir a `User` unidade em configurações de sessão Jea (administração suficiente). Para este exemplo, criamos a unidade User:.

```powershell
New-PSDrive -Name 'User' -PSProvider FileSystem -Root $env:HOMEPATH
```

```Output
Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
User               75.76         24.24 FileSystem    C:\Users\ExampleUser

```powershell
Test-UserDrivePath -Path 'User:\A_folder_that_does_not_exist'
```

```Output
True
```

### <a name="validatetrusteddata-validation-attribute"></a>Atributo de validação ValidateTrustedData

Esse atributo foi adicionado no PowerShell 6.1.1.

Neste momento, o atributo é usado internamente pelo próprio PowerShell e não se destina ao uso externo.

## <a name="dynamic-parameters"></a>Parâmetros dinâmicos

Parâmetros dinâmicos são parâmetros de um cmdlet, uma função ou um script que estão disponíveis somente sob determinadas condições.

Por exemplo, vários cmdlets de provedor têm parâmetros que estão disponíveis somente quando o cmdlet é usado na unidade do provedor ou em um caminho específico da unidade do provedor. Por exemplo, o parâmetro de **codificação** está disponível nos `Add-Content` `Get-Content` `Set-Content` cmdlets, e somente quando ele é usado em uma unidade do sistema de arquivos.

Você também pode criar um parâmetro que aparece somente quando outro parâmetro é usado no comando Function ou quando outro parâmetro tem um determinado valor.

Os parâmetros dinâmicos podem ser úteis, mas são usados somente quando necessário, pois podem ser difíceis para os usuários descobrirem. Para localizar um parâmetro dinâmico, o usuário deve estar no caminho do provedor, usar o parâmetro **ArgumentList** do `Get-Command` cmdlet ou usar o parâmetro **Path** de `Get-Help` .

Para criar um parâmetro dinâmico para uma função ou script, use a `DynamicParam` palavra-chave.

A sintaxe dela é a seguinte:

`DynamicParam {<statement-list>}`

Na lista de instruções, use uma `If` instrução para especificar as condições sob as quais o parâmetro está disponível na função.

Use o `New-Object` cmdlet para criar um objeto **System. Management. Automation. RuntimeDefinedParameter** para representar o parâmetro e especificar seu nome.

Você pode usar um `New-Object` comando para criar um objeto **System. Management. Automation. ParameterAttribute** para representar atributos do parâmetro, como **obrigatório** , **posição** ou **ValueFromPipeline** ou seu conjunto de parâmetros.

O exemplo a seguir mostra uma função de exemplo com parâmetros padrão nomeados **Name** e **Path** , e um parâmetro dinâmico opcional chamado **DP1** . O parâmetro **DP1** está no `PSet1` conjunto de parâmetros e tem um tipo de `Int32` .
O parâmetro **DP1** está disponível na `Get-Sample` função somente quando o valor do parâmetro **Path** começa com `HKLM:` , indicando que ele está sendo usado na `HKEY_LOCAL_MACHINE` unidade do registro.

```powershell
function Get-Sample {
  [CmdletBinding()]
  Param([String]$Name, [String]$Path)

  DynamicParam
  {
    if ($Path.StartsWith("HKLM:"))
    {
      $attributes = New-Object -Type `
        System.Management.Automation.ParameterAttribute
      $attributes.ParameterSetName = "PSet1"
      $attributes.Mandatory = $false
      $attributeCollection = New-Object `
        -Type System.Collections.ObjectModel.Collection[System.Attribute]
      $attributeCollection.Add($attributes)

      $dynParam1 = New-Object -Type `
        System.Management.Automation.RuntimeDefinedParameter("DP1", [Int32],
          $attributeCollection)

      $paramDictionary = New-Object `
        -Type System.Management.Automation.RuntimeDefinedParameterDictionary
      $paramDictionary.Add("DP1", $dynParam1)
      return $paramDictionary
    }
  }
}
```

Para obter mais informações, consulte [RuntimeDefinedParameter](/dotnet/api/system.management.automation.runtimedefinedparameter).

## <a name="switch-parameters"></a>Parâmetros de opção

Parâmetros de switch são parâmetros sem valor de parâmetro. Eles são eficazes somente quando são usados e têm apenas um efeito.

Por exemplo, o parâmetro **NoProfile** de **powershell.exe** é um parâmetro de opção.

Para criar um parâmetro de opção em uma função, especifique o `Switch` tipo na definição de parâmetro.

Por exemplo:

```powershell
Param([Switch]<ParameterName>)
```

Ou você pode usar um outro método:

```powershell
Param(
    [Parameter(Mandatory=$false)]
    [Switch]
    $<ParameterName>
)
```

Parâmetros de comutação são fáceis de usar e são preferenciais sobre parâmetros boolianos, que têm uma sintaxe mais difícil.

Por exemplo, para usar um parâmetro de opção, o usuário digita o parâmetro no comando.

`-IncludeAll`

Para usar um parâmetro booliano, o usuário digita o parâmetro e um valor booliano.

`-IncludeAll:$true`

Ao criar parâmetros de opção, escolha o nome do parâmetro com cuidado. Certifique-se de que o nome do parâmetro comunique o efeito do parâmetro para o usuário.
Evite termos ambíguos, como **filtro** ou **máximo** , que podem implicar que um valor é necessário.

## <a name="argumentcompleter-attribute"></a>Atributo ArgumentCompleter

O atributo **ArgumentCompleter** permite adicionar valores de preenchimento de guia a um parâmetro específico. Um atributo **ArgumentCompleter** deve ser definido para cada parâmetro que precisa de preenchimento com Tab. Semelhante a **DynamicParameters** , os valores disponíveis são calculados em tempo de execução quando o usuário pressiona <kbd>Tab</kbd> após o nome do parâmetro.

Para adicionar um atributo **ArgumentCompleter** , você precisa definir um bloco de script que determina os valores. O bloco de script deve usar os seguintes parâmetros na ordem especificada abaixo. Os nomes dos parâmetros não são importantes, pois os valores são fornecidos de forma posicionada.

A sintaxe dela é a seguinte:

```powershell
Param(
    [Parameter(Mandatory)]
    [ArgumentCompleter({
        param ( $commandName,
                $parameterName,
                $wordToComplete,
                $commandAst,
                $fakeBoundParameters )
        # Perform calculation of tab completed values here.
    })]
)
```

### <a name="argumentcompleter-script-block"></a>Bloco de script ArgumentCompleter

Os parâmetros de bloco de script são definidos com os seguintes valores:

- `$commandName` (Posição 0)-esse parâmetro é definido como o nome do comando para o qual o bloco de script está fornecendo preenchimento com Tab.
- `$parameterName` (Posição 1)-esse parâmetro é definido como o parâmetro cujo valor requer preenchimento com Tab.
- `$wordToComplete` (Posição 2)-esse parâmetro é definido como o valor que o usuário forneceu antes de pressionar a <kbd>tecla Tab</kbd>. O bloco de script deve usar esse valor para determinar valores de preenchimento de guia.
- `$commandAst` (Posição 3)-esse parâmetro é definido como a árvore de sintaxe abstrata (AST) para a linha de entrada atual. Para obter mais informações, consulte [AST Class](/dotnet/api/system.management.automation.language.ast).
- `$fakeBoundParameters` (Posição 4)-esse parâmetro é definido como uma tabela de hash que contém o `$PSBoundParameters` para o cmdlet, antes da <kbd>guia</kbd>ser pressionada pelo usuário. Para obter mais informações, consulte [about_Automatic_Variables](about_Automatic_Variables.md).

O bloco de script **ArgumentCompleter** deve desdistribuir os valores usando o pipeline, como `ForEach-Object` , `Where-Object` ou outro método adequado.
Retornar uma matriz de valores faz com que o PowerShell trate toda a matriz como **um** valor de conclusão de tabulação.

O exemplo a seguir adiciona a conclusão de Tab ao parâmetro **Value** . Se apenas o parâmetro **Value** for especificado, todos os valores possíveis, ou argumentos, para **Value** serão exibidos. Quando o parâmetro de **tipo** é especificado, o parâmetro **Value** exibe apenas os valores possíveis para esse tipo.

Além disso, o `-like` operador garante que, se o usuário digitar o comando a seguir e usar a conclusão de <kbd>Tabulação</kbd> , somente a **Apple** será retornada.

`Test-ArgumentCompleter -Type Fruits -Value A`

```powershell
function Test-ArgumentCompleter {
[CmdletBinding()]
 param (
        [Parameter(Mandatory=$true)]
        [ValidateSet('Fruits', 'Vegetables')]
        $Type,
        [Parameter(Mandatory=$true)]
        [ArgumentCompleter( {
            param ( $commandName,
                    $parameterName,
                    $wordToComplete,
                    $commandAst,
                    $fakeBoundParameters )

            $possibleValues = @{
                Fruits = @('Apple', 'Orange', 'Banana')
                Vegetables = @('Tomato', 'Squash', 'Corn')
            }
            if ($fakeBoundParameters.ContainsKey('Type'))
            {
                $possibleValues[$fakeBoundParameters.Type] | Where-Object {
                    $_ -like "$wordToComplete*"
                }
            }
            else
            {
                $possibleValues.Values | ForEach-Object {$_}
            }
        } )]
        $Value
      )
}
```

## <a name="see-also"></a>Confira também

[about_Automatic_Variables](about_Automatic_Variables.md)

[about_Functions](about_Functions.md)

[about_Functions_Advanced](about_Functions_Advanced.md)

[about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md)

[about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md)

[about_Functions_OutputTypeAttribute](about_Functions_OutputTypeAttribute.md)
