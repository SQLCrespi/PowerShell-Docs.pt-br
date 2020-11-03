---
description: O PowerShell fornece a capacidade de adicionar dinamicamente novas propriedades e alterar a formatação da saída de objetos para o pipeline.
Locale: en-US
ms.date: 08/07/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_calculated_properties?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Calculated_Properties
ms.openlocfilehash: 1ecc621d05cb340f6792481df483249095ed63a2
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196370"
---
# <a name="about-calculated-properties"></a>Sobre as propriedades calculadas

## <a name="short-description"></a>Descrição breve

O PowerShell fornece a capacidade de adicionar dinamicamente novas propriedades e alterar a formatação da saída de objetos para o pipeline.

## <a name="long-description"></a>Descrição longa

Um número de cmdlets do PowerShell transformar, agregar ou processar objetos de entrada em objetos de saída usando parâmetros que permitem a adição de novas propriedades a esses objetos de saída. Esses parâmetros podem ser usados para gerar Propriedades novas e calculadas em objetos de saída com base nos valores de objetos de entrada.
A propriedade calculada é definida por uma [tabela de hash](about_hash_tables.md) que contém pares chave-valor que especificam o nome da nova propriedade, uma expressão para calcular o valor e informações de formatação opcionais.

## <a name="supported-cmdlets"></a>cmdlets compatíveis

Os cmdlets a seguir dão suporte a valores de propriedade calculada para o parâmetro **Property** . Os `Format-*` cmdlets também oferecem suporte a valores calculados para o parâmetro **GroupBy** .

A lista a seguir relaciona os cmdlets que dão suporte a Propriedades calculadas e os pares chave-valor que são suportados por cada cmdlet.

- `Compare-Object`
  - `expression`

- `ConvertTo-Html`
  - `name`/`label` -opcional (adicionado no PowerShell 6. x)
  - `expression`
  - `width` -opcional
  - `alignment` -opcional

- `Format-Custom`
  - `expression`
  - `depth` -opcional

- `Format-List`
  - `name`/`label` -opcional
  - `expression`
  - `formatstring` -opcional

  Esse mesmo conjunto de pares chave-valor também se aplica aos valores de propriedade calculados passados para o parâmetro **GroupBy** para todos os `Format-*` cmdlets.

- `Format-Table`
  - `name`/`label` -opcional
  - `expression`
  - `formatstring` -opcional
  - `width` -opcional
  - `alignment` -opcional

- `Format-Wide`
  - `expression`
  - `formatstring` -opcional

- `Group-Object`
  - `expression`

- `Measure-Object`
  - Dá suporte apenas a um bloco de script para a expressão, não para uma tabela de hash.
  - Sem suporte no PowerShell 5,1 e mais antigo.

- `Select-Object`
  - `name`/`label` -opcional
  - `expression`

- `Sort-Object`
  - `expression`
  - `ascending`/`descending` -opcional

> [!NOTE]
> O valor de `expression` pode ser um bloco de script em vez de uma tabela de hash. Para obter mais informações, consulte a seção [observações](#notes) .

## <a name="hashtable-key-definitions"></a>Definições de chave de Hashtable

- `name`/`label` -Especifica o nome da propriedade que está sendo criada. Você pode usar `name` o ou seu alias, `label` , de forma intercambiável.
- `expression` -Um bloco de script usado para calcular o valor da nova propriedade.
- `alignment` -Usado por cmdlets que produzem saída tabular para definir como os valores são exibidos em uma coluna. O valor deve ser `'left'` , `'center'` ou `'right'` .
- `formatstring` -Especifica uma cadeia de caracteres de formato que define como o valor é formatado para saída. Para obter mais informações sobre cadeias de caracteres de formato, consulte [tipos de formato no .net](/dotnet/standard/base-types/formatting-types).
- `width` -Especifica a coluna de largura máxima em uma tabela quando o valor é exibido. O valor deve ser maior que `0` .
- `depth` -O parâmetro **Depth** de `Format-Custom` especifica a profundidade de expansão para todas as propriedades. A `depth` chave permite que você especifique a profundidade da expansão por propriedade.
- `ascending` / `descending` -Permite que você especifique a ordem de classificação para uma ou mais propriedades. Esses são valores Boolianos.

As chaves de tabela de hash não precisam ser escritas enquanto o prefixo do nome especificado não for ambíguo. Por exemplo, `n` pode ser usado no lugar de `Name` e `e` pode ser usado no lugar de `Expression` .

## <a name="examples"></a>Exemplos

### <a name="compare-object"></a>Compare-Object

Com as propriedades calculadas, você pode controlar como as propriedades dos objetos de entrada são comparadas. Neste exemplo, em vez de comparar os valores diretamente, os valores são comparados com o resultado da operação aritmética (módulo de 2).

```powershell
Compare-Object @{p=1} @{p=2} -property @{ Expression = { $_.p % 2 } }
```

```Output
 $_.p % 2  SideIndicator
---------- -------------
         0 =>
         1 <=
```

### <a name="convertto-html"></a>ConvertTo-Html

`ConvertTo-Html` pode converter uma coleção de objetos em uma tabela HTML.
As propriedades calculadas permitem que você controle como a tabela é apresentada.

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

Este exemplo cria uma tabela HTML contendo uma lista de aliases do PowerShell e os parâmetros numéricos para cada comando com alias. Os valores da coluna **parameterCount** são centralizados.

### <a name="format-custom"></a>Format-Custom

`Format-Custom` fornece uma exibição personalizada de um objeto em um formato semelhante a uma definição de classe. Objetos mais complexos podem conter membros profundamente aninhados com tipos complexos. O parâmetro **Depth** de `Format-Custom` especifica a profundidade de expansão para todas as propriedades. A `depth` chave permite que você especifique a profundidade da expansão por propriedade.

Neste exemplo, a `depth` chave simplifica a saída personalizada para o `Get-Date` cmdlet. `Get-Date` Retorna um objeto **DateTime** . A propriedade **Date** desse objeto também é um objeto **DateTime** , portanto, o objeto é aninhado.

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

### <a name="format-list"></a>Format-List

Neste exemplo, usamos Propriedades calculadas para alterar o nome e o formato da saída de `Get-ChildItem` .

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

### <a name="format-table"></a>Format-Table

Neste exemplo, a propriedade calculada adiciona uma propriedade **Type** usada para classificar os arquivos pelo tipo de conteúdo.

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

### <a name="format-wide"></a>Format-Wide

O `Format-Wide` cmdlet permite que você exiba o valor de uma propriedade para objetos em uma coleção como uma lista de várias colunas.

Para este exemplo, queremos ver o nome de arquivo e o tamanho (em kilobytes) como uma listagem ampla. Como `Format-Wide` o não exibe mais de uma propriedade, usamos uma propriedade calculada para combinar o valor de duas propriedades em um único valor.

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

### <a name="group-object"></a>Group-Object

O `Group-Object` cmdlet exibe objetos em grupos com base no valor de uma propriedade especificada. Neste exemplo, a propriedade calculada conta o número de arquivos de cada tipo de conteúdo.

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

### <a name="measure-object"></a>Measure-Object

O `Measure-Object` cmdlet calcula as propriedades numéricas de objetos. Neste exemplo, usamos uma propriedade calculada para obter a contagem ( **sum** ) dos números, entre 1 e 10, que são igualmente divisíveis por 3.

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
> Ao contrário dos outros cmdlets, o não `Measure-Object` aceita uma tabela de hash para propriedades calculadas. Você deve usar um bloco de script.

### <a name="select-object"></a>Select-Object

Você pode usar Propriedades calculadas para adicionar membros adicionais à saída de objetos com o `Select-Object` cmdlet. Neste exemplo, estamos listando os aliases do PowerShell que começam com a letra `C` . Usando `Select-Object` , geramos o alias, o cmdlet para o qual ele está mapeado e uma contagem para o número de parâmetros definidos para o cmdlet. Usando uma propriedade calculada, podemos criar a propriedade **parameterCount** .

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

### <a name="sort-object"></a>Sort-Object

Usando as propriedades calculadas, você pode classificar dados em ordens diferentes por propriedade. Este exemplo classifica dados de um arquivo CSV em ordem crescente por **Data** . Mas, dentro de cada data, ele classifica as linhas em ordem decrescente por **UnitsSold** .

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

## <a name="notes"></a>Observações

- Você pode especificar o bloco de script de expressão _diretamente_ , como um argumento, em vez de especificá-lo como a `Expression` entrada em uma tabela de hash. Por exemplo:

  ```powershell
  '1', '10', '2' | Sort-Object { [int] $_ }
  ```

  Este exemplo é conveniente para cmdlets que não exigem (ou dão suporte) nomear uma propriedade por meio da `Name` chave, como `Sort-Object` , `Group-Object` e `Measure-Object` .

  Para cmdlets que dão suporte à nomeação da propriedade, o bloco de script é convertido em uma cadeia de caracteres e usado como o nome da propriedade na saída.

- `Expression` blocos de script são executados em escopos _filho_ , o que significa que as variáveis do chamador não podem ser modificadas diretamente.

- A lógica do pipeline é aplicada à saída de `Expression` blocos de script. Isso significa que a saída de uma matriz de elemento único faz com que essa matriz seja desempacotada.

- Para a maioria dos cmdlets, os erros dentro de blocos de script de expressão são ignorados silenciosamente.
  Para `Sort-Object` , os erros de encerramento de instrução e de encerramento de script são _gerados_ , mas não encerram a instrução.

## <a name="see-also"></a>Consulte Também

[about_Hash_Tables](about_hash_tables.md)

[Compare-Object](xref:Microsoft.PowerShell.Utility.Compare-Object)

[ConvertTo-Html](xref:Microsoft.PowerShell.Utility.ConvertTo-Html)

[Format-Custom](xref:Microsoft.PowerShell.Utility.Format-Custom)

[Format-List](xref:Microsoft.PowerShell.Utility.Format-List)

[Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table)

[Format-Wide](xref:Microsoft.PowerShell.Utility.Format-Wide)

[Group-Object](xref:Microsoft.PowerShell.Utility.Group-Object)

[Measure-Object](xref:Microsoft.PowerShell.Utility.Measure-Object)

[Select-Object](xref:Microsoft.PowerShell.Utility.Select-Object)

[Sort-Object](xref:Microsoft.PowerShell.Utility.Sort-Object)

[Tipos de formato no .NET](/dotnet/standard/base-types/formatting-types)
