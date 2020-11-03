---
description: Sai do escopo atual, que pode ser uma função, um script ou um bloco de script.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_return?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Return
ms.openlocfilehash: a2603f24b562ecc1bdafe49f5703a75661b1124d
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195973"
---
# <a name="about-return"></a>Sobre o retorno

## <a name="short-description"></a>Descrição breve

Sai do escopo atual, que pode ser uma função, um script ou um bloco de script.

## <a name="long-description"></a>Descrição longa

A `return` palavra-chave sai de uma função, script ou bloco de script. Ele pode ser usado para sair de um escopo em um ponto específico, para retornar um valor ou para indicar que o final do escopo foi atingido.

Os usuários que estão familiarizados com linguagens como C ou C \# podem querer usar a `return` palavra-chave para tornar a lógica de deixar um escopo explícito.

No PowerShell, os resultados de cada instrução são retornados como saída, mesmo sem uma instrução que contenha a palavra-chave Return. Linguagens como C ou C \# retornam apenas o valor ou valores que são especificados pela `return` palavra-chave.

> [!NOTE]
> A partir do PowerShell 5,0, o PowerShell adicionou o idioma para definir classes, usando a sintaxe formal.  No contexto de uma classe do PowerShell, nada é a saída de um método, exceto o que você especifica usando uma `return` instrução. Você pode ler mais sobre classes do PowerShell no [about_Classes](about_Classes.md).

### <a name="syntax"></a>Syntax

A sintaxe para a `return` palavra-chave é a seguinte:

```
return [<expression>]
```

A `return` palavra-chave pode aparecer sozinha ou pode ser seguida por um valor ou expressão, da seguinte maneira:

```powershell
return
return $a
return (2 + $a)
```

### <a name="examples"></a>Exemplos

O exemplo a seguir usa a `return` palavra-chave para sair de uma função em um ponto específico se uma condicional for atendida. Números ímpares não são multiplicados porque a instrução de retorno é encerrada antes que essa instrução possa ser executada.

```powershell
function MultiplyEven
{
    param($number)

    if ($number % 2) { return "$number is not even" }
    $number * 2
}

1..10 | ForEach-Object {MultiplyEven -Number $_}
```

```output
1 is not even
4
3 is not even
8
5 is not even
12
7 is not even
16
9 is not even
20
```

No PowerShell, os valores podem ser retornados mesmo se a `return` palavra-chave não for usada.
Os resultados de cada instrução são retornados. Por exemplo, as instruções a seguir retornam o valor da `$a` variável:

```powershell
$a
return
```

A instrução a seguir também retorna o valor de `$a` :

```powershell
return $a
```

O exemplo a seguir inclui uma instrução destinada a permitir que o usuário saiba que a função está executando um cálculo:

```powershell
function calculation {
    param ($value)

    "Please wait. Working on calculation..."
    $value += 73
    return $value
}

$a = calculation 14
```

O "Aguarde. Trabalhando no cálculo... " a cadeia de caracteres não é exibida. Em vez disso, ele é atribuído à `$a` variável, como no exemplo a seguir:

```
PS> $a
Please wait. Working on calculation...
87
```

A cadeia de caracteres informativa e o resultado do cálculo são retornados pela função e atribuídos à `$a` variável.

Se você quiser exibir uma mensagem em sua função, a partir do PowerShell 5,0, poderá usar o `Information` fluxo. O código a seguir corrige o exemplo acima usando o `Write-Information` cmdlet com um `InformationAction` de **continue** .

```powershell
function calculation {
    param ($value)

    Write-Information "Please wait. Working on calculation..." -InformationAction Continue
    $value += 73
    return $value
}

$a = calculation 14
```

```output
Please wait. Working on calculation...
C:\PS> $a
87
```

### <a name="return-values-and-the-pipeline"></a>Valores de retorno e o pipeline

Quando você retorna uma coleção de seu bloco de script ou função, o PowerShell automaticamente desacumula os membros e os transmite um por vez por meio do pipeline. Isso ocorre devido ao processamento de uma vez por tempo do PowerShell. Para obter mais informações, consulte [about_Pipelines](about_pipelines.md).

Esse conceito é ilustrado pela seguinte função de exemplo que retorna uma matriz de números. A saída da função é canalizada para o `Measure-Object` cmdlet que conta o número de objetos no pipeline.

```powershell
function Test-Return
{
    $array = 1,2,3
    return $array
}
Test-Return | Measure-Object
```

```Output
Count    : 3
Average  :
Sum      :
Maximum  :
Minimum  :
Property :
```

Para forçar um bloco de script ou uma função a retornar a coleção como um único objeto para o pipeline, use um dos dois métodos a seguir:

- Expressão de matriz unário

  Utilizando uma expressão unário, você pode enviar o valor de retorno para baixo no pipeline como um único objeto, conforme ilustrado pelo exemplo a seguir.

  ```powershell
  function Test-Return
  {
      $array = 1,2,3
      return (, $array)
  }
  Test-Return | Measure-Object
  ```

  ```Output
  Count    : 1
  Average  :
  Sum      :
  Maximum  :
  Minimum  :
  Property :
  ```

- `Write-Output` com o parâmetro **Noenumerate** .

  Você também pode usar o `Write-Output` cmdlet com o parâmetro **noenumerate** . O exemplo a seguir usa o `Measure-Object` cmdlet para contar os objetos enviados ao pipeline da função de exemplo pela `return` palavra-chave.

  ```powershell
  function Test-Return
  {
      $array = 1, 2, 3
      return Write-Output -NoEnumerate $array
  }

  Test-Return | Measure-Object
  ```

  ```Output
  Count    : 1
  Average  :
  Sum      :
  Maximum  :
  Minimum  :
  Property :
  ```

## <a name="see-also"></a>Confira também

[about_Language_Keywords](about_Language_Keywords.md)

[about_Functions](about_Functions.md)

[about_Scopes](about_Scopes.md)

[about_Classes](about_Classes.md)

[Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information)

[about_Script_Blocks](about_Script_Blocks.md)
