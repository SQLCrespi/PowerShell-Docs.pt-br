---
description: Descreve um comando de linguagem que você pode usar para percorrer todos os itens em uma coleção de itens.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 2/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_foreach?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Foreach
ms.openlocfilehash: 87d4b78df35c8944bdd95a478be4ea0b8d6fbe49
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195562"
---
# <a name="about-foreach"></a>Sobre ForEach

## <a name="short-description"></a>Descrição breve
Descreve um comando de linguagem que você pode usar para percorrer todos os itens em uma coleção de itens.

## <a name="long-description"></a>Descrição longa

A `Foreach` instrução (também conhecida como `Foreach` loop) é uma construção de linguagem para percorrer (Iterando) uma série de valores em uma coleção de itens.

O tipo mais simples e típico de coleção para percorrer é uma matriz.
Dentro de um `Foreach` loop, é comum executar um ou mais comandos em cada item de uma matriz.

## <a name="syntax"></a>Syntax

Veja a seguir a `ForEach` sintaxe:

```
foreach ($<item> in $<collection>){<statement list>}
```

A parte da `ForEach` instrução entre parênteses representa uma variável e uma coleção para iteração. O PowerShell cria a variável `$<item>` automaticamente quando o `Foreach` loop é executado. Antes de cada iteração por meio do loop, a variável é definida como um valor na coleção.
O bloco após uma `Foreach` instrução `{<statement list>}` contém um conjunto de comandos para executar em cada item de uma coleção.

### <a name="examples"></a>Exemplos

Por exemplo, o `Foreach` loop no exemplo a seguir exibe os valores na `$letterArray` matriz.

```powershell
$letterArray = "a","b","c","d"
foreach ($letter in $letterArray)
{
  Write-Host $letter
}
```

Neste exemplo, a `$letterArray` matriz é criada e inicializada com os valores de cadeia de caracteres `"a"` , `"b"` , `"c"` e `"d"` . Na primeira vez em que a `Foreach` instrução é executada, ela define a `$letter` variável igual ao primeiro item em `$letterArray` ( `"a"` ). Em seguida, ele usa o `Write-Host` cmdlet para exibir a letra a. Na próxima vez que o loop for executado, `$letter` será definido como `"b"` e assim por diante. Depois que o `Foreach` loop exibe a letra d, o PowerShell sai do loop.

A `Foreach` instrução inteira deve aparecer em uma única linha para executá-la como um comando no prompt de comando do PowerShell. A instrução inteira não `Foreach` precisará aparecer em uma única linha se você inserir o comando em um arquivo de script. ps1 em vez disso.

`Foreach` as instruções também podem ser usadas junto com cmdlets que retornam uma coleção de itens. No exemplo a seguir, a instrução foreach percorre a lista de itens retornada pelo `Get-ChildItem` cmdlet.

```powershell
foreach ($file in Get-ChildItem)
{
  Write-Host $file
}
```

Você pode refinar o exemplo usando uma `If` instrução para limitar os resultados retornados. No exemplo a seguir, a `Foreach` instrução executa a mesma operação de loop do exemplo anterior, mas adiciona uma `If` instrução para limitar os resultados a arquivos que são maiores que 100 quilobytes (KB):

```powershell
foreach ($file in Get-ChildItem)
{
  if ($file.length -gt 100KB)
  {
    Write-Host $file
  }
}
```

Neste exemplo, o `Foreach` loop usa uma propriedade da `$file` variável para executar uma operação de comparação ( `$file.length -gt 100KB` ). A `$file` variável contém todas as propriedades no objeto que é retornado pelo `Get-ChildItem` cmdlet. Portanto, você pode retornar mais do que apenas um nome de arquivo.
No próximo exemplo, o PowerShell retorna o comprimento e o último tempo de acesso dentro da lista de instruções:

```powershell
foreach ($file in Get-ChildItem)
{
  if ($file.length -gt 100KB)
  {
    Write-Host $file
    Write-Host $file.length
    Write-Host $file.lastaccesstime
  }
}
```

Neste exemplo, você não está limitado a executar um único comando em uma lista de instruções.

Você também pode usar uma variável fora de um `Foreach` loop e incrementar a variável dentro do loop. O exemplo a seguir conta os arquivos com mais de 100 KB de tamanho:

```powershell
$i = 0
foreach ($file in Get-ChildItem) {
  if ($file.length -gt 100KB) {
    Write-Host $file "file size:" ($file.length / 1024).ToString("F0") KB
    $i = $i + 1
  }
}

if ($i -ne 0) {
  Write-Host
  Write-Host $i " file(s) over 100 KB in the current directory."
}
else {
  Write-Host "No files greater than 100 KB in the current directory."
}
```

No exemplo anterior, a `$i` variável é definida como `0` fora do loop e a variável é incrementada dentro do loop para cada arquivo que é maior que 100 KB. Quando o loop é encerrado, uma `If` instrução avalia o valor de `$i` para exibir uma contagem de todos os arquivos em 100 KB. Ou, ele exibe uma mensagem informando que nenhum arquivo em 100 KB foi encontrado.

O exemplo anterior também demonstra como formatar os resultados de comprimento do arquivo:

```powershell
($file.length / 1024).ToString("F0")
```

O valor é dividido por 1.024 para mostrar os resultados em quilobytes em vez de bytes, e o valor resultante é então formatado usando o especificador de formato de ponto fixo para remover quaisquer valores decimais do resultado. O 0 faz com que o especificador de formato não mostre casas decimais.

No exemplo a seguir, a função definida analisa scripts do PowerShell e módulos de script e retorna o local das funções contidas no. O exemplo demonstra como usar o `MoveNext` método (que funciona de forma semelhante a `skip X` em um `For` loop) e a `Current` propriedade da `$foreach` variável dentro de um bloco de script foreach. A função de exemplo pode encontrar funções em um script, mesmo se houver definições de função com espaçamento incomum ou inconsistentes que abranjam várias linhas.

Para obter mais informações, consulte [usando enumeradores](about_Automatic_Variables.md#using-enumerators).

```powershell
function Get-FunctionPosition {
  [CmdletBinding()]
  [OutputType('FunctionPosition')]
  param(
    [Parameter(Position = 0, Mandatory,
      ValueFromPipeline, ValueFromPipelineByPropertyName)]
    [ValidateNotNullOrEmpty()]
    [Alias('PSPath')]
    [System.String[]]
    $Path
  )

  process {
    try {
      $filesToProcess = if ($_ -is [System.IO.FileSystemInfo]) {
        $_
      } else {
        $filesToProcess = Get-Item -Path $Path
      }
      $parser = [System.Management.Automation.Language.Parser]
      foreach ($item in $filesToProcess) {
        if ($item.PSIsContainer -or
            $item.Extension -notin @('.ps1', '.psm1')) {
          continue
        }
        $tokens = $errors = $null
        $ast = $parser::ParseFile($item.FullName, ([REF]$tokens),
          ([REF]$errors))
        if ($errors) {
          $msg = "File '{0}' has {1} parser errors." -f $item.FullName,
            $errors.Count
          Write-Warning $msg
        }
        :tokenLoop foreach ($token in $tokens) {
          if ($token.Kind -ne 'Function') {
            continue
          }
          $position = $token.Extent.StartLineNumber
          do {
            if (-not $foreach.MoveNext()) {
              break tokenLoop
            }
            $token = $foreach.Current
          } until ($token.Kind -in @('Generic', 'Identifier'))
          $functionPosition = [pscustomobject]@{
            Name       = $token.Text
            LineNumber = $position
            Path       = $item.FullName
          }
          Add-Member -InputObject $functionPosition `
            -TypeName FunctionPosition -PassThru
        }
      }
    }
    catch {
      throw
    }
  }
}
```

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_Automatic_Variables](about_Automatic_Variables.md)

[about_If](about_If.md)

[ForEach-Object](xref:Microsoft.PowerShell.Core.ForEach-Object)

