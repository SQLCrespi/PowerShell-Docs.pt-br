---
description: O PowerShell fornece a capacidade de adicionar dinamicamente novas propriedades e alterar a formatação da saída de objetos para o pipeline.
Locale: en-US
ms.date: 08/07/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_calculated_properties?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Calculated_Properties
ms.openlocfilehash: f51f1565db013c452d7d8dfc1975720ec2a1e3d0
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195779"
---
# <a name="about-calculated-properties"></a><span data-ttu-id="61d9b-103">Sobre as propriedades calculadas</span><span class="sxs-lookup"><span data-stu-id="61d9b-103">About calculated properties</span></span>

## <a name="short-description"></a><span data-ttu-id="61d9b-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="61d9b-104">Short Description</span></span>

<span data-ttu-id="61d9b-105">O PowerShell fornece a capacidade de adicionar dinamicamente novas propriedades e alterar a formatação da saída de objetos para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="61d9b-105">PowerShell provides the ability to dynamically add new properties and alter the formatting of objects output to the pipeline.</span></span>

## <a name="long-description"></a><span data-ttu-id="61d9b-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="61d9b-106">Long Description</span></span>

<span data-ttu-id="61d9b-107">Um número de cmdlets do PowerShell transformar, agregar ou processar objetos de entrada em objetos de saída usando parâmetros que permitem a adição de novas propriedades a esses objetos de saída.</span><span class="sxs-lookup"><span data-stu-id="61d9b-107">A number of PowerShell cmdlets transform, aggregate, or process input objects into output objects using parameters that allow the addition of new properties to those output objects.</span></span> <span data-ttu-id="61d9b-108">Esses parâmetros podem ser usados para gerar Propriedades novas e calculadas em objetos de saída com base nos valores de objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="61d9b-108">These parameters can be used to generate new, calculated properties on output objects based on the values of input objects.</span></span>
<span data-ttu-id="61d9b-109">A propriedade calculada é definida por uma [tabela de hash](about_hash_tables.md) que contém pares chave-valor que especificam o nome da nova propriedade, uma expressão para calcular o valor e informações de formatação opcionais.</span><span class="sxs-lookup"><span data-stu-id="61d9b-109">The calculated property is defined by a [hashtable](about_hash_tables.md) containing key-value pairs that specify the name of the new property, an expression to calculate the value, and optional formatting information.</span></span>

## <a name="supported-cmdlets"></a><span data-ttu-id="61d9b-110">cmdlets compatíveis</span><span class="sxs-lookup"><span data-stu-id="61d9b-110">Supported cmdlets</span></span>

<span data-ttu-id="61d9b-111">Os cmdlets a seguir dão suporte a valores de propriedade calculada para o parâmetro **Property** .</span><span class="sxs-lookup"><span data-stu-id="61d9b-111">The following cmdlets support calculated property values for the **Property** parameter.</span></span> <span data-ttu-id="61d9b-112">Os `Format-*` cmdlets também oferecem suporte a valores calculados para o parâmetro **GroupBy** .</span><span class="sxs-lookup"><span data-stu-id="61d9b-112">The `Format-*` cmdlets also support calculated values for the **GroupBy** parameter.</span></span>

<span data-ttu-id="61d9b-113">A lista a seguir relaciona os cmdlets que dão suporte a Propriedades calculadas e os pares chave-valor que são suportados por cada cmdlet.</span><span class="sxs-lookup"><span data-stu-id="61d9b-113">The following list itemizes the cmdlets that support calculated properties and the key-value pairs that are supported by each cmdlet.</span></span>

- `Compare-Object`
  - `expression`

- `ConvertTo-Html`
  - <span data-ttu-id="61d9b-114">`name`/`label` -opcional (adicionado no PowerShell 6. x)</span><span class="sxs-lookup"><span data-stu-id="61d9b-114">`name`/`label` - optional (added in PowerShell 6.x)</span></span>
  - `expression`
  - <span data-ttu-id="61d9b-115">`width` -opcional</span><span class="sxs-lookup"><span data-stu-id="61d9b-115">`width` - optional</span></span>
  - <span data-ttu-id="61d9b-116">`alignment` -opcional</span><span class="sxs-lookup"><span data-stu-id="61d9b-116">`alignment` - optional</span></span>

- `Format-Custom`
  - `expression`
  - <span data-ttu-id="61d9b-117">`depth` -opcional</span><span class="sxs-lookup"><span data-stu-id="61d9b-117">`depth` - optional</span></span>

- `Format-List`
  - <span data-ttu-id="61d9b-118">`name`/`label` -opcional</span><span class="sxs-lookup"><span data-stu-id="61d9b-118">`name`/`label` - optional</span></span>
  - `expression`
  - <span data-ttu-id="61d9b-119">`formatstring` -opcional</span><span class="sxs-lookup"><span data-stu-id="61d9b-119">`formatstring` - optional</span></span>

  <span data-ttu-id="61d9b-120">Esse mesmo conjunto de pares chave-valor também se aplica aos valores de propriedade calculados passados para o parâmetro **GroupBy** para todos os `Format-*` cmdlets.</span><span class="sxs-lookup"><span data-stu-id="61d9b-120">This same set of key-value pairs also apply to calculated property values passed to the **GroupBy** parameter for all `Format-*` cmdlets.</span></span>

- `Format-Table`
  - <span data-ttu-id="61d9b-121">`name`/`label` -opcional</span><span class="sxs-lookup"><span data-stu-id="61d9b-121">`name`/`label` - optional</span></span>
  - `expression`
  - <span data-ttu-id="61d9b-122">`formatstring` -opcional</span><span class="sxs-lookup"><span data-stu-id="61d9b-122">`formatstring` - optional</span></span>
  - <span data-ttu-id="61d9b-123">`width` -opcional</span><span class="sxs-lookup"><span data-stu-id="61d9b-123">`width` - optional</span></span>
  - <span data-ttu-id="61d9b-124">`alignment` -opcional</span><span class="sxs-lookup"><span data-stu-id="61d9b-124">`alignment` - optional</span></span>

- `Format-Wide`
  - `expression`
  - <span data-ttu-id="61d9b-125">`formatstring` -opcional</span><span class="sxs-lookup"><span data-stu-id="61d9b-125">`formatstring` - optional</span></span>

- `Group-Object`
  - `expression`

- `Measure-Object`
  - <span data-ttu-id="61d9b-126">Dá suporte apenas a um bloco de script para a expressão, não para uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="61d9b-126">Only supports a script block for the expression, not a hashtable.</span></span>
  - <span data-ttu-id="61d9b-127">Sem suporte no PowerShell 5,1 e mais antigo.</span><span class="sxs-lookup"><span data-stu-id="61d9b-127">Not supported in PowerShell 5.1 and older.</span></span>

- `Select-Object`
  - <span data-ttu-id="61d9b-128">`name`/`label` -opcional</span><span class="sxs-lookup"><span data-stu-id="61d9b-128">`name`/`label` - optional</span></span>
  - `expression`

- `Sort-Object`
  - `expression`
  - <span data-ttu-id="61d9b-129">`ascending`/`descending` -opcional</span><span class="sxs-lookup"><span data-stu-id="61d9b-129">`ascending`/`descending` - optional</span></span>

> [!NOTE]
> <span data-ttu-id="61d9b-130">O valor de `expression` pode ser um bloco de script em vez de uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="61d9b-130">The value of the `expression` can be a script block instead of a hashtable.</span></span> <span data-ttu-id="61d9b-131">Para obter mais informações, consulte a seção [observações](#notes) .</span><span class="sxs-lookup"><span data-stu-id="61d9b-131">For more information, see the [Notes](#notes) section.</span></span>

## <a name="hashtable-key-definitions"></a><span data-ttu-id="61d9b-132">Definições de chave de Hashtable</span><span class="sxs-lookup"><span data-stu-id="61d9b-132">Hashtable key definitions</span></span>

- <span data-ttu-id="61d9b-133">`name`/`label` -Especifica o nome da propriedade que está sendo criada.</span><span class="sxs-lookup"><span data-stu-id="61d9b-133">`name`/`label` - Specifies the name of the property being created.</span></span> <span data-ttu-id="61d9b-134">Você pode usar `name` o ou seu alias, `label` , de forma intercambiável.</span><span class="sxs-lookup"><span data-stu-id="61d9b-134">You can use `name` or its alias, `label`, interchangeably.</span></span>
- <span data-ttu-id="61d9b-135">`expression` -Um bloco de script usado para calcular o valor da nova propriedade.</span><span class="sxs-lookup"><span data-stu-id="61d9b-135">`expression` - A script block used to calculate the value of the new property.</span></span>
- <span data-ttu-id="61d9b-136">`alignment` -Usado por cmdlets que produzem saída tabular para definir como os valores são exibidos em uma coluna.</span><span class="sxs-lookup"><span data-stu-id="61d9b-136">`alignment` - Used by cmdlets that produce tabular output to define how the values are displayed in a column.</span></span> <span data-ttu-id="61d9b-137">O valor deve ser `'left'` , `'center'` ou `'right'` .</span><span class="sxs-lookup"><span data-stu-id="61d9b-137">The value must be `'left'`, `'center'`, or `'right'`.</span></span>
- <span data-ttu-id="61d9b-138">`formatstring` -Especifica uma cadeia de caracteres de formato que define como o valor é formatado para saída.</span><span class="sxs-lookup"><span data-stu-id="61d9b-138">`formatstring` - Specifies a format string that defines how the value is formatted for output.</span></span> <span data-ttu-id="61d9b-139">Para obter mais informações sobre cadeias de caracteres de formato, consulte [tipos de formato no .net](/dotnet/standard/base-types/formatting-types).</span><span class="sxs-lookup"><span data-stu-id="61d9b-139">For more information about format strings, see [Format types in .NET](/dotnet/standard/base-types/formatting-types).</span></span>
- <span data-ttu-id="61d9b-140">`width` -Especifica a coluna de largura máxima em uma tabela quando o valor é exibido.</span><span class="sxs-lookup"><span data-stu-id="61d9b-140">`width` - Specifies the maximum width column in a table when the value is displayed.</span></span> <span data-ttu-id="61d9b-141">O valor deve ser maior que `0` .</span><span class="sxs-lookup"><span data-stu-id="61d9b-141">The value must be greater than `0`.</span></span>
- <span data-ttu-id="61d9b-142">`depth` -O parâmetro **Depth** de `Format-Custom` especifica a profundidade de expansão para todas as propriedades.</span><span class="sxs-lookup"><span data-stu-id="61d9b-142">`depth` - The **Depth** parameter of `Format-Custom` specifies the depth of expansion for all properties.</span></span> <span data-ttu-id="61d9b-143">A `depth` chave permite que você especifique a profundidade da expansão por propriedade.</span><span class="sxs-lookup"><span data-stu-id="61d9b-143">The `depth` key allows you to specify the depth of expansion per property.</span></span>
- <span data-ttu-id="61d9b-144">`ascending` / `descending` -Permite que você especifique a ordem de classificação para uma ou mais propriedades.</span><span class="sxs-lookup"><span data-stu-id="61d9b-144">`ascending` / `descending` - Allows you to specify the order of sorting for one or more properties.</span></span> <span data-ttu-id="61d9b-145">Esses são valores Boolianos.</span><span class="sxs-lookup"><span data-stu-id="61d9b-145">These are boolean values.</span></span>

<span data-ttu-id="61d9b-146">As chaves de tabela de hash não precisam ser escritas enquanto o prefixo do nome especificado não for ambíguo.</span><span class="sxs-lookup"><span data-stu-id="61d9b-146">The hashtable keys need not be spelled out as long as the specified name prefix is unambiguous.</span></span> <span data-ttu-id="61d9b-147">Por exemplo, `n` pode ser usado no lugar de `Name` e `e` pode ser usado no lugar de `Expression` .</span><span class="sxs-lookup"><span data-stu-id="61d9b-147">For example, `n` can be used in lieu of `Name` and `e` can be used in lieu of `Expression`.</span></span>

## <a name="examples"></a><span data-ttu-id="61d9b-148">Exemplos</span><span class="sxs-lookup"><span data-stu-id="61d9b-148">Examples</span></span>

### <a name="compare-object"></a><span data-ttu-id="61d9b-149">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="61d9b-149">Compare-Object</span></span>

<span data-ttu-id="61d9b-150">Com as propriedades calculadas, você pode controlar como as propriedades dos objetos de entrada são comparadas.</span><span class="sxs-lookup"><span data-stu-id="61d9b-150">With calculated properties, you can control how the properties of the input objects are compared.</span></span> <span data-ttu-id="61d9b-151">Neste exemplo, em vez de comparar os valores diretamente, os valores são comparados com o resultado da operação aritmética (módulo de 2).</span><span class="sxs-lookup"><span data-stu-id="61d9b-151">In this example, rather than comparing the values directly, the values are compared to the result of the arithmetic operation (modulus of 2).</span></span>

```powershell
Compare-Object @{p=1} @{p=2} -property @{ Expression = { $_.p % 2 } }
```

```Output
 $_.p % 2  SideIndicator
---------- -------------
         0 =>
         1 <=
```

### <a name="convertto-html"></a><span data-ttu-id="61d9b-152">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="61d9b-152">ConvertTo-Html</span></span>

<span data-ttu-id="61d9b-153">`ConvertTo-Html` pode converter uma coleção de objetos em uma tabela HTML.</span><span class="sxs-lookup"><span data-stu-id="61d9b-153">`ConvertTo-Html` can convert a collection of objects to an HTML table.</span></span>
<span data-ttu-id="61d9b-154">As propriedades calculadas permitem que você controle como a tabela é apresentada.</span><span class="sxs-lookup"><span data-stu-id="61d9b-154">Calculated properties allow you to control how the table is presented.</span></span>

```powershell
Get-Alias |
  ConvertTo-Html Name,
                 Definition,
                 @{
                    name='ParameterCount'
                    expr={$_.Parameters.Keys.Count}
                    align='center'
                 } |
    Out-File .\aliases.htm -Force
```

<span data-ttu-id="61d9b-155">Este exemplo cria uma tabela HTML contendo uma lista de aliases do PowerShell e os parâmetros numéricos para cada comando com alias.</span><span class="sxs-lookup"><span data-stu-id="61d9b-155">This example creates an HTML table containing a list of PowerShell aliases and the number parameters for each aliased command.</span></span> <span data-ttu-id="61d9b-156">Os valores da coluna **parameterCount** são centralizados.</span><span class="sxs-lookup"><span data-stu-id="61d9b-156">The values of **ParameterCount** column are centered.</span></span>

### <a name="format-custom"></a><span data-ttu-id="61d9b-157">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="61d9b-157">Format-Custom</span></span>

<span data-ttu-id="61d9b-158">`Format-Custom` fornece uma exibição personalizada de um objeto em um formato semelhante a uma definição de classe.</span><span class="sxs-lookup"><span data-stu-id="61d9b-158">`Format-Custom` provides a custom view of an object in a format similar to a class definition.</span></span> <span data-ttu-id="61d9b-159">Objetos mais complexos podem conter membros profundamente aninhados com tipos complexos.</span><span class="sxs-lookup"><span data-stu-id="61d9b-159">More complex objects can contain members that are deeply nested with complex types.</span></span> <span data-ttu-id="61d9b-160">O parâmetro **Depth** de `Format-Custom` especifica a profundidade de expansão para todas as propriedades.</span><span class="sxs-lookup"><span data-stu-id="61d9b-160">The **Depth** parameter of `Format-Custom` specifies the depth of expansion for all properties.</span></span> <span data-ttu-id="61d9b-161">A `depth` chave permite que você especifique a profundidade da expansão por propriedade.</span><span class="sxs-lookup"><span data-stu-id="61d9b-161">The `depth` key allows you to specify the depth of expansion per property.</span></span>

<span data-ttu-id="61d9b-162">Neste exemplo, a `depth` chave simplifica a saída personalizada para o `Get-Date` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="61d9b-162">In this example, the `depth` key simplifies the custom output for the `Get-Date` cmdlet.</span></span> <span data-ttu-id="61d9b-163">`Get-Date` Retorna um objeto **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="61d9b-163">`Get-Date` returns a **DateTime** object.</span></span> <span data-ttu-id="61d9b-164">A propriedade **Date** desse objeto também é um objeto **DateTime** , portanto, o objeto é aninhado.</span><span class="sxs-lookup"><span data-stu-id="61d9b-164">The **Date** property of this object is also a **DateTime** object, so the object is nested.</span></span>

```powershell
Get-Date | Format-Custom @{expr={$_.Date};depth=1},TimeOfDay
```

```Output
class DateTime
{
  $_.Date =
    class DateTime
    {
      Date = 8/7/2020 12:00:00 AM
      Day = 7
      DayOfWeek = Friday
      DayOfYear = 220
      Hour = 0
      Kind = Local
      Millisecond = 0
      Minute = 0
      Month = 8
      Second = 0
      Ticks = 637323552000000000
      TimeOfDay = 00:00:00
      Year = 2020
      DateTime = Friday, August 07, 2020 12:00:00 AM
    }
  TimeOfDay =
    class TimeSpan
    {
      Ticks = 435031592302
      Days = 0
      Hours = 12
      Milliseconds = 159
      Minutes = 5
      Seconds = 3
      TotalDays = 0.503508787386574
      TotalHours = 12.0842108972778
      TotalMilliseconds = 43503159.2302
      TotalMinutes = 725.052653836667
      TotalSeconds = 43503.1592302
    }
}
```

### <a name="format-list"></a><span data-ttu-id="61d9b-165">Format-List</span><span class="sxs-lookup"><span data-stu-id="61d9b-165">Format-List</span></span>

<span data-ttu-id="61d9b-166">Neste exemplo, usamos Propriedades calculadas para alterar o nome e o formato da saída de `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="61d9b-166">In this example, we use calculated properties to change the name and format of the output from `Get-ChildItem`.</span></span>

```powershell
Get-ChildItem *.json -File |
  Format-List Fullname,
              @{
                 name='Modified'
                 expression={$_.LastWriteTime}
                 formatstring='O'
              },
              @{
                 name='Size'
                 expression={$_.Length/1KB}
                 formatstring='N2'
              }
```

```Output
FullName : C:\Git\PS-Docs\PowerShell-Docs\.markdownlint.json
Modified : 2020-07-23T10:26:28.4092457-07:00
Size     : 2.40

FullName : C:\Git\PS-Docs\PowerShell-Docs\.openpublishing.publish.config.json
Modified : 2020-07-23T10:26:28.4092457-07:00
Size     : 2.25

FullName : C:\Git\PS-Docs\PowerShell-Docs\.openpublishing.redirection.json
Modified : 2020-07-27T13:05:24.3887629-07:00
Size     : 324.60
```

### <a name="format-table"></a><span data-ttu-id="61d9b-167">Format-Table</span><span class="sxs-lookup"><span data-stu-id="61d9b-167">Format-Table</span></span>

<span data-ttu-id="61d9b-168">Neste exemplo, a propriedade calculada adiciona uma propriedade **Type** usada para classificar os arquivos pelo tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="61d9b-168">In this example, the calculated property adds a **Type** property used to classify the files by the content type.</span></span>

```powershell
Get-ChildItem -File |
  Sort-Object extension |
    Format-Table Name, Length -GroupBy @{
      name='Type'
      expression={
        switch ($_.extension) {
          '.md'   {'Content'}
          ''      {'Metacontent'}
          '.ps1'  {'Automation'}
          '.yml'  {'Automation'}
          default {'Configuration'}
        }
      }
    }
```

```Output
   Type: Metacontent

Name              Length
----              ------
ThirdPartyNotices   1229
LICENSE-CODE        1106
LICENSE            19047

   Type: Configuration

Name                                Length
----                                ------
.editorconfig                          183
.gitattributes                         419
.gitignore                             228
.markdownlint.json                    2456
.openpublishing.publish.config.json   2306
.openpublishing.redirection.json    332394
.localization-config                   232

   Type: Content

Name            Length
----            ------
README.md         3355
CONTRIBUTING.md    247

   Type: Automation

Name                      Length
----                      ------
.openpublishing.build.ps1    796
build.ps1                   7495
ci.yml                       645
ci-steps.yml                2035
daily.yml                   1271
```

### <a name="format-wide"></a><span data-ttu-id="61d9b-169">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="61d9b-169">Format-Wide</span></span>

<span data-ttu-id="61d9b-170">O `Format-Wide` cmdlet permite que você exiba o valor de uma propriedade para objetos em uma coleção como uma lista de várias colunas.</span><span class="sxs-lookup"><span data-stu-id="61d9b-170">The `Format-Wide` cmdlet allows you to display the value of one property for objects in a collection as a multi-column list.</span></span>

<span data-ttu-id="61d9b-171">Para este exemplo, queremos ver o nome de arquivo e o tamanho (em kilobytes) como uma listagem ampla.</span><span class="sxs-lookup"><span data-stu-id="61d9b-171">For this example, we want to see the filename and the size (in kilobytes) as a wide listing.</span></span> <span data-ttu-id="61d9b-172">Como `Format-Wide` o não exibe mais de uma propriedade, usamos uma propriedade calculada para combinar o valor de duas propriedades em um único valor.</span><span class="sxs-lookup"><span data-stu-id="61d9b-172">Since `Format-Wide` does not display more than one property, we use a calculated property to combine the value of two properties into a single value.</span></span>

```powershell
Get-ChildItem -File |
  Format-Wide -Property @{e={'{0} ({1:N2}kb)' -f $_.name,($_.length/1kb)}}
```

```Output
.editorconfig (0.18kb)                          .gitattributes (0.41kb)
.gitignore (0.22kb)                             .localization-config (0.23kb)
.markdownlint.json (2.40kb)                     .openpublishing.build.ps1 (0.78kb)
.openpublishing.publish.config.json (2.25kb)    .openpublishing.redirection.json (324.60kb)
build.ps1 (7.32kb)                              ci.yml (0.63kb)
ci-steps.yml (1.99kb)                           CONTRIBUTING.md (0.24kb)
daily.yml (1.24kb)                              LICENSE (18.60kb)
LICENSE-CODE (1.08kb)                           README.md (3.28kb)
ThirdPartyNotices (1.20kb)
```

### <a name="group-object"></a><span data-ttu-id="61d9b-173">Group-Object</span><span class="sxs-lookup"><span data-stu-id="61d9b-173">Group-Object</span></span>

<span data-ttu-id="61d9b-174">O `Group-Object` cmdlet exibe objetos em grupos com base no valor de uma propriedade especificada.</span><span class="sxs-lookup"><span data-stu-id="61d9b-174">The `Group-Object` cmdlet displays objects in groups based on the value of a specified property.</span></span> <span data-ttu-id="61d9b-175">Neste exemplo, a propriedade calculada conta o número de arquivos de cada tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="61d9b-175">In this example, the calculated property counts the number of files of each content type.</span></span>

```powershell
Get-ChildItem -File |
  Sort-Object extension |
    Group-Object -NoElement -Property @{
      expression={
        switch ($_.extension) {
          '.md'   {'Content'}
          ''      {'Metacontent'}
          '.ps1'  {'Automation'}
          '.yml'  {'Automation'}
          default {'Configuration'}
        }
      }
    }
```

```Output
Count Name
----- ----
    5 Automation
    7 Configuration
    2 Content
    3 Metacontent
```

### <a name="measure-object"></a><span data-ttu-id="61d9b-176">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="61d9b-176">Measure-Object</span></span>

<span data-ttu-id="61d9b-177">O `Measure-Object` cmdlet calcula as propriedades numéricas de objetos.</span><span class="sxs-lookup"><span data-stu-id="61d9b-177">The `Measure-Object` cmdlet calculates the numeric properties of objects.</span></span> <span data-ttu-id="61d9b-178">Neste exemplo, usamos uma propriedade calculada para obter a contagem ( **sum** ) dos números, entre 1 e 10, que são igualmente divisíveis por 3.</span><span class="sxs-lookup"><span data-stu-id="61d9b-178">In this example, we use a calculated property to get the count ( **Sum** ) of the numbers, between 1 and 10, that are evenly divisible by 3.</span></span>

```powershell
1..10 | Measure-Object -Property {($_ % 3) -eq 0} -Sum
```

```Output
Count             : 10
Average           :
Sum               : 3
Maximum           :
Minimum           :
StandardDeviation :
Property          : ($_ % 3) -eq 0
```

> [!NOTE]
> <span data-ttu-id="61d9b-179">Ao contrário dos outros cmdlets, o não `Measure-Object` aceita uma tabela de hash para propriedades calculadas.</span><span class="sxs-lookup"><span data-stu-id="61d9b-179">Unlike the other cmdlets, `Measure-Object` does not accept a hashtable for calculated properties.</span></span> <span data-ttu-id="61d9b-180">Você deve usar um bloco de script.</span><span class="sxs-lookup"><span data-stu-id="61d9b-180">You must use a script block.</span></span>

### <a name="select-object"></a><span data-ttu-id="61d9b-181">Select-Object</span><span class="sxs-lookup"><span data-stu-id="61d9b-181">Select-Object</span></span>

<span data-ttu-id="61d9b-182">Você pode usar Propriedades calculadas para adicionar membros adicionais à saída de objetos com o `Select-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="61d9b-182">You can use calculated properties to add additional members to the objects output with the `Select-Object` cmdlet.</span></span> <span data-ttu-id="61d9b-183">Neste exemplo, estamos listando os aliases do PowerShell que começam com a letra `C` .</span><span class="sxs-lookup"><span data-stu-id="61d9b-183">In this example, we are listing the PowerShell aliases that begin with the letter `C`.</span></span> <span data-ttu-id="61d9b-184">Usando `Select-Object` , geramos o alias, o cmdlet para o qual ele está mapeado e uma contagem para o número de parâmetros definidos para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="61d9b-184">Using `Select-Object`, we output the alias, the cmdlet it's mapped to, and a count for the number of parameters defined for the cmdlet.</span></span> <span data-ttu-id="61d9b-185">Usando uma propriedade calculada, podemos criar a propriedade **parameterCount** .</span><span class="sxs-lookup"><span data-stu-id="61d9b-185">Using a calculated property, we can create the **ParameterCount** property.</span></span>

```powershell
$aliases = Get-Alias c* |
  Select-Object Name,
                Definition,
                @{
                    name='ParameterCount'
                    expr={$_.Parameters.Keys.Count}
                }
$aliases | Get-Member
$aliases
```

```Output
   TypeName: Selected.System.Management.Automation.AliasInfo

Name           MemberType   Definition
----           ----------   ----------
Equals         Method       bool Equals(System.Object obj)
GetHashCode    Method       int GetHashCode()
GetType        Method       type GetType()
ToString       Method       string ToString()
Definition     NoteProperty string Definition=Get-Content
Name           NoteProperty string Name=cat
ParameterCount NoteProperty System.Int32 ParameterCount=21

Name    Definition         ParameterCount
----    ----------         --------------
cat     Get-Content                    21
cd      Set-Location                   15
cdd     Push-MyLocation                 1
chdir   Set-Location                   15
clc     Clear-Content                  20
clear   Clear-Host                      0
clhy    Clear-History                  17
cli     Clear-Item                     20
clp     Clear-ItemProperty             22
cls     Clear-Host                      0
clv     Clear-Variable                 19
cnsn    Connect-PSSession              29
compare Compare-Object                 20
copy    Copy-Item                      24
cp      Copy-Item                      24
cpi     Copy-Item                      24
cpp     Copy-ItemProperty              23
cvpa    Convert-Path                   13
```

### <a name="sort-object"></a><span data-ttu-id="61d9b-186">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="61d9b-186">Sort-Object</span></span>

<span data-ttu-id="61d9b-187">Usando as propriedades calculadas, você pode classificar dados em ordens diferentes por propriedade.</span><span class="sxs-lookup"><span data-stu-id="61d9b-187">Using the calculated properties, you can sort data in different orders per property.</span></span> <span data-ttu-id="61d9b-188">Este exemplo classifica dados de um arquivo CSV em ordem crescente por **Data** .</span><span class="sxs-lookup"><span data-stu-id="61d9b-188">This example sorts data from a CSV file in ascending order by **Date** .</span></span> <span data-ttu-id="61d9b-189">Mas, dentro de cada data, ele classifica as linhas em ordem decrescente por **UnitsSold** .</span><span class="sxs-lookup"><span data-stu-id="61d9b-189">But within each date, it sorts the rows in descending order by **UnitsSold** .</span></span>

```powershell
Import-Csv C:\temp\sales-data.csv |
  Sort-Object Date, @{expr={$_.UnitsSold}; desc=$true}, Salesperson  |
    Select-Object Date, Salesperson, UnitsSold
```

```Output
Date       Salesperson UnitsSold
----       ----------- ---------
2020-08-01 Sally       3
2020-08-01 Anne        2
2020-08-01 Fred        1
2020-08-02 Anne        6
2020-08-02 Fred        2
2020-08-02 Sally       0
2020-08-03 Anne        5
2020-08-03 Sally       3
2020-08-03 Fred        1
2020-08-04 Anne        2
2020-08-04 Fred        2
2020-08-04 Sally       2
```

## <a name="notes"></a><span data-ttu-id="61d9b-190">Observações</span><span class="sxs-lookup"><span data-stu-id="61d9b-190">Notes</span></span>

- <span data-ttu-id="61d9b-191">Você pode especificar o bloco de script de expressão _diretamente_ , como um argumento, em vez de especificá-lo como a `Expression` entrada em uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="61d9b-191">You may specify the expression script block _directly_ , as an argument, rather than specifying it as the `Expression` entry in a hashtable.</span></span> <span data-ttu-id="61d9b-192">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="61d9b-192">For example:</span></span>

  ```powershell
  '1', '10', '2' | Sort-Object { [int] $_ }
  ```

  <span data-ttu-id="61d9b-193">Este exemplo é conveniente para cmdlets que não exigem (ou dão suporte) nomear uma propriedade por meio da `Name` chave, como `Sort-Object` , `Group-Object` e `Measure-Object` .</span><span class="sxs-lookup"><span data-stu-id="61d9b-193">This example is convenient for cmdlets that do not require (or support) naming a property via the `Name` key, such as `Sort-Object`, `Group-Object`, and `Measure-Object`.</span></span>

  <span data-ttu-id="61d9b-194">Para cmdlets que dão suporte à nomeação da propriedade, o bloco de script é convertido em uma cadeia de caracteres e usado como o nome da propriedade na saída.</span><span class="sxs-lookup"><span data-stu-id="61d9b-194">For cmdlets that support naming the property, the script block is converted to a string and used as the name of the property in the output.</span></span>

- <span data-ttu-id="61d9b-195">`Expression` blocos de script são executados em escopos _filho_ , o que significa que as variáveis do chamador não podem ser modificadas diretamente.</span><span class="sxs-lookup"><span data-stu-id="61d9b-195">`Expression` script blocks run in _child_ scopes, meaning that the caller's variables cannot be directly modified.</span></span>

- <span data-ttu-id="61d9b-196">A lógica do pipeline é aplicada à saída de `Expression` blocos de script.</span><span class="sxs-lookup"><span data-stu-id="61d9b-196">Pipeline logic is applied to the output from `Expression` script blocks.</span></span> <span data-ttu-id="61d9b-197">Isso significa que a saída de uma matriz de elemento único faz com que essa matriz seja desempacotada.</span><span class="sxs-lookup"><span data-stu-id="61d9b-197">This means that outputting a single-element array causes that array to be unwrapped.</span></span>

- <span data-ttu-id="61d9b-198">Para a maioria dos cmdlets, os erros dentro de blocos de script de expressão são ignorados silenciosamente.</span><span class="sxs-lookup"><span data-stu-id="61d9b-198">For most cmdlets, errors inside expression script blocks are quietly ignored.</span></span>
  <span data-ttu-id="61d9b-199">Para `Sort-Object` , os erros de encerramento de instrução e de encerramento de script são _gerados_ , mas não encerram a instrução.</span><span class="sxs-lookup"><span data-stu-id="61d9b-199">For `Sort-Object`, statement-terminating and script-terminating errors are _output_ but they do not terminate the statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="61d9b-200">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="61d9b-200">See Also</span></span>

[<span data-ttu-id="61d9b-201">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="61d9b-201">about_Hash_Tables</span></span>](about_hash_tables.md)

[<span data-ttu-id="61d9b-202">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="61d9b-202">Compare-Object</span></span>](xref:Microsoft.PowerShell.Utility.Compare-Object)

[<span data-ttu-id="61d9b-203">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="61d9b-203">ConvertTo-Html</span></span>](xref:Microsoft.PowerShell.Utility.ConvertTo-Html)

[<span data-ttu-id="61d9b-204">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="61d9b-204">Format-Custom</span></span>](xref:Microsoft.PowerShell.Utility.Format-Custom)

[<span data-ttu-id="61d9b-205">Format-List</span><span class="sxs-lookup"><span data-stu-id="61d9b-205">Format-List</span></span>](xref:Microsoft.PowerShell.Utility.Format-List)

[<span data-ttu-id="61d9b-206">Format-Table</span><span class="sxs-lookup"><span data-stu-id="61d9b-206">Format-Table</span></span>](xref:Microsoft.PowerShell.Utility.Format-Table)

[<span data-ttu-id="61d9b-207">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="61d9b-207">Format-Wide</span></span>](xref:Microsoft.PowerShell.Utility.Format-Wide)

[<span data-ttu-id="61d9b-208">Group-Object</span><span class="sxs-lookup"><span data-stu-id="61d9b-208">Group-Object</span></span>](xref:Microsoft.PowerShell.Utility.Group-Object)

[<span data-ttu-id="61d9b-209">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="61d9b-209">Measure-Object</span></span>](xref:Microsoft.PowerShell.Utility.Measure-Object)

[<span data-ttu-id="61d9b-210">Select-Object</span><span class="sxs-lookup"><span data-stu-id="61d9b-210">Select-Object</span></span>](xref:Microsoft.PowerShell.Utility.Select-Object)

[<span data-ttu-id="61d9b-211">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="61d9b-211">Sort-Object</span></span>](xref:Microsoft.PowerShell.Utility.Sort-Object)

[<span data-ttu-id="61d9b-212">Tipos de formato no .NET</span><span class="sxs-lookup"><span data-stu-id="61d9b-212">Format types in .NET</span></span>](/dotnet/standard/base-types/formatting-types)
