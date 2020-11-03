---
description: Descreve um atributo que informa o tipo de objeto que a função retorna.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_outputtypeattribute?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_OutputTypeAttribute
ms.openlocfilehash: cff471057a656f4c603d058f9db23a1ea003cd2c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196204"
---
# <a name="about-functions-outputtypeattribute"></a>Sobre o Functions OutputTypeAttribute

## <a name="short-description"></a>DESCRIÇÃO BREVE
Descreve um atributo que informa o tipo de objeto que a função retorna.

## <a name="long-description"></a>DESCRIÇÃO LONGA

O atributo OutputType lista os tipos .NET de objetos que as funções retorna. Você pode usar seu parâmetro opcional ParameterSetName para listar diferentes tipos de saída para cada conjunto de parâmetros.

O atributo OutputType tem suporte em funções simples e avançadas. Ele é independente do atributo CmdletBinding.

O atributo OutputType fornece o valor da Propriedade OutputType do objeto **System. Management. Automation. FunctionInfo** que o `Get-Command` cmdlet retorna.

O valor do atributo OutputType é apenas uma observação de documentação. Ele não é derivado do código de função ou comparado à saída real da função. Como tal, o valor pode ser impreciso.

## <a name="syntax"></a>SYNTAX

O atributo OutputType de Functions tem a seguinte sintaxe:

```
[OutputType([<TypeLiteral>], ParameterSetName="<Name>")]
[OutputType("<TypeNameString>", ParameterSetName="<Name>")]
```

O parâmetro **ParameterSetName** é opcional.

Você pode listar vários tipos no atributo OutputType.

```
[OutputType([<Type1>],[<Type2>],[<Type3>])]
```

Você pode usar o parâmetro **ParameterSetName** para indicar que conjuntos de parâmetros diferentes retornam tipos diferentes.

```
[OutputType([<Type1>], ParameterSetName=("<Set1>","<Set2>"))]
[OutputType([<Type2>], ParameterSetName="<Set3>")]
```

Coloque as instruções de atributo OutputType na lista de atributos que precede a `Param` instrução.

O exemplo a seguir mostra o posicionamento do atributo OutputType em uma função simples.

```powershell
function SimpleFunction2
{
  [OutputType([<Type>])]
  Param ($Parameter1)

  <function body>
}
```

O exemplo a seguir mostra o posicionamento do atributo OutputType em funções avançadas.

```powershell
function AdvancedFunction1
{
  [OutputType([<Type>])]
  Param (
    [parameter(Mandatory=$true)]
    [String[]]
    $Parameter1
  )

  <function body>
}

function AdvancedFunction2
{
  [CmdletBinding(SupportsShouldProcess=<Boolean>)]
  [OutputType([<Type>])]
  Param (
    [parameter(Mandatory=$true)]
    [String[]]
    $Parameter1
  )

  <function body>
}
```

## <a name="examples"></a>EXEMPLOS

### <a name="example-1-create-a-function-that-has-the-outputtype-of-string"></a>Exemplo 1: criar uma função que tenha o OutputType da cadeia de caracteres

```powershell
function Send-Greeting
{
  [OutputType([String])]
  Param ($Name)

  "Hello, $Name"
}
```

Para ver a propriedade de tipo de saída resultante, use o `Get-Command` cmdlet.

```powershell
(Get-Command Send-Greeting).OutputType
```

```Output
Name                                               Type
----                                               ----
System.String                                      System.String
```

### <a name="example-2-use-the-output-attribute-to-indicate-dynamic-output-types"></a>Exemplo 2: usar o atributo de saída para indicar tipos de saída dinâmicos

A função avançada a seguir usa o atributo OutputType para indicar que a função retorna tipos diferentes dependendo do conjunto de parâmetros usado no comando Function.

```powershell
function Get-User
{
  [CmdletBinding(DefaultParameterSetName="ID")]

  [OutputType("System.Int32", ParameterSetName="ID")]
  [OutputType([String], ParameterSetName="Name")]

  Param (
    [parameter(Mandatory=$true, ParameterSetName="ID")]
    [Int[]]
    $UserID,

    [parameter(Mandatory=$true, ParameterSetName="Name")]
    [String[]]
    $UserName
  )

  <function body>
}
```

### <a name="example-3-shows-when-an-actual-output-differs-from-the-outputtype"></a>Exemplo 3: mostra quando uma saída real difere do OutputType

O exemplo a seguir demonstra que o valor da propriedade de tipo de saída exibe o valor do atributo OutputType, mesmo quando ele é impreciso.

A `Get-Time` função retorna uma cadeia de caracteres que contém a forma abreviada da hora em qualquer objeto DateTime. No entanto, o atributo OutputType relata que retorna um objeto **System. DateTime** .

```powershell
function Get-Time
{
  [OutputType([DateTime])]
  Param (
    [parameter(Mandatory=$true)]
    [Datetime]$DateTime
  )

  $DateTime.ToShortTimeString()
}
```

O `GetType()` método confirma que a função retorna uma cadeia de caracteres.

```powershell
(Get-Time -DateTime (Get-Date)).GetType().FullName
```

```Output
System.String
```

No entanto, a Propriedade OutputType, que obtém seu valor do atributo OutputType, relata que a função retorna um objeto **DateTime** .

```powershell
(Get-Command Get-Time).OutputType
```

```Output
Name                                      Type
----                                      ----
System.DateTime                           System.DateTime
```

### <a name="example-4-a-function--that-shouldnt-have-output"></a>Exemplo 4: uma função que não deveria ter A saída

O exemplo a seguir mostra uma função personalizada que deve executar e ação, mas não retornar nada.

```powershell
function Invoke-Notepad
{
  [OutputType([System.Void])]
  Param ()
  & notepad.exe | Out-Null
}
```

## <a name="notes"></a>OBSERVAÇÕES

O valor da Propriedade OutputType de um objeto **FunctionInfo** é uma matriz de objetos **System. Management. Automation. PSTypeName** , cada um com propriedades Name e Type.

Para obter apenas o nome de cada tipo de saída, use um comando com o formato a seguir.

```powershell
(Get-Command Get-Time).OutputType | ForEach {$_.Name}
```

O valor da Propriedade OutputType pode ser nulo. Use um valor nulo quando a saída não for um tipo .NET, como um objeto **WMI** ou uma exibição formatada de um objeto.

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_Functions](about_Functions.md)

[about_Functions_Advanced](about_Functions_Advanced.md)

[about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md)

[about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)

[about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md)
