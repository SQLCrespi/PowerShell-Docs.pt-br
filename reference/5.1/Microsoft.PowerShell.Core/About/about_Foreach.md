---
description: Descreve um comando de linguagem que você pode usar para percorrer todos os itens em uma coleção de itens.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 2/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_foreach?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Foreach
ms.openlocfilehash: f1f00df8b0f07dd945994860897584d883ef2ce4
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196026"
---
# <a name="about-foreach"></a><span data-ttu-id="67b6a-104">Sobre ForEach</span><span class="sxs-lookup"><span data-stu-id="67b6a-104">About ForEach</span></span>

## <a name="short-description"></a><span data-ttu-id="67b6a-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="67b6a-105">Short description</span></span>
<span data-ttu-id="67b6a-106">Descreve um comando de linguagem que você pode usar para percorrer todos os itens em uma coleção de itens.</span><span class="sxs-lookup"><span data-stu-id="67b6a-106">Describes a language command you can use to traverse all the items in a collection of items.</span></span>

## <a name="long-description"></a><span data-ttu-id="67b6a-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="67b6a-107">Long description</span></span>

<span data-ttu-id="67b6a-108">A `Foreach` instrução (também conhecida como `Foreach` loop) é uma construção de linguagem para percorrer (Iterando) uma série de valores em uma coleção de itens.</span><span class="sxs-lookup"><span data-stu-id="67b6a-108">The `Foreach` statement (also known as a `Foreach` loop) is a language construct for stepping through (iterating) a series of values in a collection of items.</span></span>

<span data-ttu-id="67b6a-109">O tipo mais simples e típico de coleção para percorrer é uma matriz.</span><span class="sxs-lookup"><span data-stu-id="67b6a-109">The simplest and most typical type of collection to traverse is an array.</span></span>
<span data-ttu-id="67b6a-110">Dentro de um `Foreach` loop, é comum executar um ou mais comandos em cada item de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="67b6a-110">Within a `Foreach` loop, it is common to run one or more commands against each item in an array.</span></span>

## <a name="syntax"></a><span data-ttu-id="67b6a-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="67b6a-111">Syntax</span></span>

<span data-ttu-id="67b6a-112">Veja a seguir a `ForEach` sintaxe:</span><span class="sxs-lookup"><span data-stu-id="67b6a-112">The following shows the `ForEach` syntax:</span></span>

```
foreach ($<item> in $<collection>){<statement list>}
```

<span data-ttu-id="67b6a-113">A parte da `ForEach` instrução entre parênteses representa uma variável e uma coleção para iteração.</span><span class="sxs-lookup"><span data-stu-id="67b6a-113">The part of the `ForEach` statement enclosed in parenthesis represents a variable and a collection to iterate.</span></span> <span data-ttu-id="67b6a-114">O PowerShell cria a variável `$<item>` automaticamente quando o `Foreach` loop é executado.</span><span class="sxs-lookup"><span data-stu-id="67b6a-114">PowerShell creates the variable `$<item>` automatically when the `Foreach` loop runs.</span></span> <span data-ttu-id="67b6a-115">Antes de cada iteração por meio do loop, a variável é definida como um valor na coleção.</span><span class="sxs-lookup"><span data-stu-id="67b6a-115">Prior to each iteration through the loop, the variable is set to a value in the collection.</span></span>
<span data-ttu-id="67b6a-116">O bloco após uma `Foreach` instrução `{<statement list>}` contém um conjunto de comandos para executar em cada item de uma coleção.</span><span class="sxs-lookup"><span data-stu-id="67b6a-116">The block following a `Foreach` statement `{<statement list>}` contains a set of commands to execute against each item in a collection.</span></span>

### <a name="examples"></a><span data-ttu-id="67b6a-117">Exemplos</span><span class="sxs-lookup"><span data-stu-id="67b6a-117">Examples</span></span>

<span data-ttu-id="67b6a-118">Por exemplo, o `Foreach` loop no exemplo a seguir exibe os valores na `$letterArray` matriz.</span><span class="sxs-lookup"><span data-stu-id="67b6a-118">For example, the `Foreach` loop in the following example displays the values in the `$letterArray` array.</span></span>

```powershell
$letterArray = "a","b","c","d"
foreach ($letter in $letterArray)
{
  Write-Host $letter
}
```

<span data-ttu-id="67b6a-119">Neste exemplo, a `$letterArray` matriz é criada e inicializada com os valores de cadeia de caracteres `"a"` , `"b"` , `"c"` e `"d"` .</span><span class="sxs-lookup"><span data-stu-id="67b6a-119">In this example, the `$letterArray` array is created and initialized with the string values `"a"`, `"b"`, `"c"`, and `"d"`.</span></span> <span data-ttu-id="67b6a-120">Na primeira vez em que a `Foreach` instrução é executada, ela define a `$letter` variável igual ao primeiro item em `$letterArray` ( `"a"` ).</span><span class="sxs-lookup"><span data-stu-id="67b6a-120">The first time the `Foreach` statement runs, it sets the `$letter` variable equal to the first item in `$letterArray` (`"a"`).</span></span> <span data-ttu-id="67b6a-121">Em seguida, ele usa o `Write-Host` cmdlet para exibir a letra a.</span><span class="sxs-lookup"><span data-stu-id="67b6a-121">Then, it uses the `Write-Host` cmdlet to display the letter a.</span></span> <span data-ttu-id="67b6a-122">Na próxima vez que o loop for executado, `$letter` será definido como `"b"` e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="67b6a-122">The next time through the loop, `$letter` is set to `"b"`, and so on.</span></span> <span data-ttu-id="67b6a-123">Depois que o `Foreach` loop exibe a letra d, o PowerShell sai do loop.</span><span class="sxs-lookup"><span data-stu-id="67b6a-123">After the `Foreach` loop displays the letter d, PowerShell exits the loop.</span></span>

<span data-ttu-id="67b6a-124">A `Foreach` instrução inteira deve aparecer em uma única linha para executá-la como um comando no prompt de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67b6a-124">The entire `Foreach` statement must appear on a single line to run it as a command at the PowerShell command prompt.</span></span> <span data-ttu-id="67b6a-125">A instrução inteira não `Foreach` precisará aparecer em uma única linha se você inserir o comando em um arquivo de script. ps1 em vez disso.</span><span class="sxs-lookup"><span data-stu-id="67b6a-125">The entire `Foreach` statement does not have to appear on a single line if you place the command in a .ps1 script file instead.</span></span>

<span data-ttu-id="67b6a-126">`Foreach` as instruções também podem ser usadas junto com cmdlets que retornam uma coleção de itens.</span><span class="sxs-lookup"><span data-stu-id="67b6a-126">`Foreach` statements can also be used together with cmdlets that return a collection of items.</span></span> <span data-ttu-id="67b6a-127">No exemplo a seguir, a instrução foreach percorre a lista de itens retornada pelo `Get-ChildItem` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="67b6a-127">In the following example, the Foreach statement steps through the list of items that is returned by the `Get-ChildItem` cmdlet.</span></span>

```powershell
foreach ($file in Get-ChildItem)
{
  Write-Host $file
}
```

<span data-ttu-id="67b6a-128">Você pode refinar o exemplo usando uma `If` instrução para limitar os resultados retornados.</span><span class="sxs-lookup"><span data-stu-id="67b6a-128">You can refine the example by using an `If` statement to limit the results that are returned.</span></span> <span data-ttu-id="67b6a-129">No exemplo a seguir, a `Foreach` instrução executa a mesma operação de loop do exemplo anterior, mas adiciona uma `If` instrução para limitar os resultados a arquivos que são maiores que 100 quilobytes (KB):</span><span class="sxs-lookup"><span data-stu-id="67b6a-129">In the following example, the `Foreach` statement performs the same looping operation as the previous example, but it adds an `If` statement to limit the results to files that are greater than 100 kilobytes (KB):</span></span>

```powershell
foreach ($file in Get-ChildItem)
{
  if ($file.length -gt 100KB)
  {
    Write-Host $file
  }
}
```

<span data-ttu-id="67b6a-130">Neste exemplo, o `Foreach` loop usa uma propriedade da `$file` variável para executar uma operação de comparação ( `$file.length -gt 100KB` ).</span><span class="sxs-lookup"><span data-stu-id="67b6a-130">In this example, the `Foreach` loop uses a property of the `$file` variable to perform a comparison operation (`$file.length -gt 100KB`).</span></span> <span data-ttu-id="67b6a-131">A `$file` variável contém todas as propriedades no objeto que é retornado pelo `Get-ChildItem` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="67b6a-131">The `$file` variable contains all the properties in the object that is returned by the `Get-ChildItem` cmdlet.</span></span> <span data-ttu-id="67b6a-132">Portanto, você pode retornar mais do que apenas um nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="67b6a-132">Therefore, you can return more than just a file name.</span></span>
<span data-ttu-id="67b6a-133">No próximo exemplo, o PowerShell retorna o comprimento e o último tempo de acesso dentro da lista de instruções:</span><span class="sxs-lookup"><span data-stu-id="67b6a-133">In the next example, PowerShell returns the length and the last access time inside the statement list:</span></span>

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

<span data-ttu-id="67b6a-134">Neste exemplo, você não está limitado a executar um único comando em uma lista de instruções.</span><span class="sxs-lookup"><span data-stu-id="67b6a-134">In this example, you are not limited to running a single command in a statement list.</span></span>

<span data-ttu-id="67b6a-135">Você também pode usar uma variável fora de um `Foreach` loop e incrementar a variável dentro do loop.</span><span class="sxs-lookup"><span data-stu-id="67b6a-135">You can also use a variable outside a `Foreach` loop and increment the variable inside the loop.</span></span> <span data-ttu-id="67b6a-136">O exemplo a seguir conta os arquivos com mais de 100 KB de tamanho:</span><span class="sxs-lookup"><span data-stu-id="67b6a-136">The following example counts files over 100 KB in size:</span></span>

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

<span data-ttu-id="67b6a-137">No exemplo anterior, a `$i` variável é definida como `0` fora do loop e a variável é incrementada dentro do loop para cada arquivo que é maior que 100 KB.</span><span class="sxs-lookup"><span data-stu-id="67b6a-137">In the preceding example, the `$i` variable is set to `0` outside the loop, and the variable is incremented inside the loop for each file that is found that is larger than 100 KB.</span></span> <span data-ttu-id="67b6a-138">Quando o loop é encerrado, uma `If` instrução avalia o valor de `$i` para exibir uma contagem de todos os arquivos em 100 KB.</span><span class="sxs-lookup"><span data-stu-id="67b6a-138">When the loop exits, an `If` statement evaluates the value of `$i` to display a count of all the files over 100 KB.</span></span> <span data-ttu-id="67b6a-139">Ou, ele exibe uma mensagem informando que nenhum arquivo em 100 KB foi encontrado.</span><span class="sxs-lookup"><span data-stu-id="67b6a-139">Or, it displays a message stating that no files over 100 KB were found.</span></span>

<span data-ttu-id="67b6a-140">O exemplo anterior também demonstra como formatar os resultados de comprimento do arquivo:</span><span class="sxs-lookup"><span data-stu-id="67b6a-140">The previous example also demonstrates how to format the file length results:</span></span>

```powershell
($file.length / 1024).ToString("F0")
```

<span data-ttu-id="67b6a-141">O valor é dividido por 1.024 para mostrar os resultados em quilobytes em vez de bytes, e o valor resultante é então formatado usando o especificador de formato de ponto fixo para remover quaisquer valores decimais do resultado.</span><span class="sxs-lookup"><span data-stu-id="67b6a-141">The value is divided by 1,024 to show the results in kilobytes rather than bytes, and the resulting value is then formatted using the fixed-point format specifier to remove any decimal values from the result.</span></span> <span data-ttu-id="67b6a-142">O 0 faz com que o especificador de formato não mostre casas decimais.</span><span class="sxs-lookup"><span data-stu-id="67b6a-142">The 0 makes the format specifier show no decimal places.</span></span>

<span data-ttu-id="67b6a-143">No exemplo a seguir, a função definida analisa scripts do PowerShell e módulos de script e retorna o local das funções contidas no.</span><span class="sxs-lookup"><span data-stu-id="67b6a-143">In the following example, the function defined parses PowerShell scripts and script modules and returns the location of functions contained within.</span></span> <span data-ttu-id="67b6a-144">O exemplo demonstra como usar o `MoveNext` método (que funciona de forma semelhante a `skip X` em um `For` loop) e a `Current` propriedade da `$foreach` variável dentro de um bloco de script foreach.</span><span class="sxs-lookup"><span data-stu-id="67b6a-144">The example demonstrates how to use the `MoveNext` method (which works similarly to `skip X` on a `For` loop) and the `Current` property of the `$foreach` variable inside of a foreach script block.</span></span> <span data-ttu-id="67b6a-145">A função de exemplo pode encontrar funções em um script, mesmo se houver definições de função com espaçamento incomum ou inconsistentes que abranjam várias linhas.</span><span class="sxs-lookup"><span data-stu-id="67b6a-145">The example function can find functions in a script even if there are unusually- or inconsistently-spaced function definitions that span multiple lines.</span></span>

<span data-ttu-id="67b6a-146">Para obter mais informações, consulte [usando enumeradores](about_Automatic_Variables.md#using-enumerators).</span><span class="sxs-lookup"><span data-stu-id="67b6a-146">For more information, see [Using Enumerators](about_Automatic_Variables.md#using-enumerators).</span></span>

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
        Write-Verbose "From pipeline"
        $_
      } else {
        Write-Verbose "From parameter, $Path"
        Get-Item -Path $Path
      }
      $parser = [System.Management.Automation.Language.Parser]
      Write-Verbose "lets start the foreach loop on `$filesToProcess with $($filesToProcess.count) as count"
      foreach ($item in $filesToProcess) {
        Write-Verbose "$item"
        if ($item.PSIsContainer -or
            $item.Extension -notin @('.ps1', '.psm1')) {
          continue
        }
        $tokens = $errors = $null
        $parser::ParseFile($item.FullName, ([REF]$tokens),
          ([REF]$errors)) | Out-Null
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

## <a name="see-also"></a><span data-ttu-id="67b6a-147">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="67b6a-147">SEE ALSO</span></span>

[<span data-ttu-id="67b6a-148">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="67b6a-148">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="67b6a-149">about_If</span><span class="sxs-lookup"><span data-stu-id="67b6a-149">about_If</span></span>](about_If.md)

[<span data-ttu-id="67b6a-150">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="67b6a-150">ForEach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)
