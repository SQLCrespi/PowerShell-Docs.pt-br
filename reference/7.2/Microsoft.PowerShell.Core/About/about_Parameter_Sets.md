---
description: Descreve como definir e usar conjuntos de parâmetros em funções avançadas.
ms.date: 02/11/2020
title: about_Parameter_Sets
ms.openlocfilehash: 405ef1c70b49f703f17a9e76f899a9643cc065bc
ms.sourcegitcommit: eb7ad1850550032880f5529b4e4281514cba1673
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "99597610"
---
# <a name="about-parameter-sets"></a>Sobre conjuntos de parâmetros

## <a name="short-description"></a>DESCRIÇÃO BREVE
Descreve como definir e usar conjuntos de parâmetros em funções avançadas.

## <a name="long-description"></a>DESCRIÇÃO LONGA

O PowerShell usa conjuntos de parâmetros para permitir que você escreva uma única função que pode fazer ações diferentes para cenários diferentes. Os conjuntos de parâmetros permitem que você exponha parâmetros diferentes para o usuário. E, para retornar informações diferentes com base nos parâmetros especificados pelo usuário.

## <a name="parameter-set-requirements"></a>Requisitos do conjunto de parâmetros

Os requisitos a seguir se aplicam a todos os conjuntos de parâmetros.

- Cada conjunto de parâmetros deve ter uma combinação exclusiva de parâmetros. Se possível, pelo menos um dos parâmetros exclusivos deve ser um parâmetro obrigatório.

- Um conjunto de parâmetros que contém vários parâmetros posicionais deve definir posições exclusivas para cada parâmetro. Dois parâmetros posicionais não podem especificar a mesma posição.

- Somente um parâmetro em um conjunto pode declarar a `ValueFromPipeline` palavra-chave com um valor de `true` . Vários parâmetros podem definir a `ValueFromPipelineByPropertyName` palavra-chave com um valor de `true` .

- Se nenhum conjunto de parâmetros for especificado para um parâmetro, o parâmetro pertencerá a todos os conjuntos de parâmetros.

> [!NOTE]
> Há um limite de 32 conjuntos de parâmetros.

## <a name="default-parameter-sets"></a>Conjuntos de parâmetros padrão

Quando vários conjuntos de parâmetros são definidos, a `DefaultParameterSetName` palavra-chave do atributo **CmdletBinding** especifica o conjunto de parâmetros padrão.
O PowerShell usa o conjunto de parâmetros padrão quando não pode determinar o conjunto de parâmetros a ser usado com base nas informações fornecidas para o comando. Para obter mais informações sobre o atributo **CmdletBinding** , consulte [about_Functions_CmdletBindingAttribute](about_functions_cmdletbindingattribute.md).

## <a name="declaring-parameter-sets"></a>Declarando conjuntos de parâmetros

Para criar um conjunto de parâmetros, você deve especificar a `ParameterSetName` palavra-chave do atributo de **parâmetro** para cada parâmetro no conjunto de parâmetros. Para parâmetros que pertencem a vários conjuntos de parâmetros, adicione um atributo de **parâmetro** para cada conjunto de parâmetros.

O atributo **Parameter** permite que você defina o parâmetro de forma diferente para cada conjunto de parâmetros. Por exemplo, você pode definir um parâmetro como obrigatório em um conjunto e opcional em outro. No entanto, cada conjunto de parâmetros deve conter pelo menos um parâmetro exclusivo.

Parâmetros que não têm um nome de conjunto de parâmetros atribuído pertencem a todos os conjuntos de parâmetros.

### <a name="example"></a>Exemplo

A função de exemplo a seguir conta o número de linhas, caracteres e palavras em um arquivo de texto. Usando parâmetros, você pode especificar quais valores você deseja que sejam retornados e quais arquivos deseja medir. Há quatro conjuntos de parâmetros definidos:

- Caminho
- PathAll
- LiteralPath
- LiteralPathAll

```powershell
function Measure-Lines {
    [CmdletBinding(DefaultParameterSetName = 'Path')]
    param (
        [Parameter(Mandatory = $true,
            ParameterSetName = 'Path',
            HelpMessage = 'Enter one or more filenames',
            Position = 0)]
        [Parameter(Mandatory = $true,
            ParameterSetName = 'PathAll',
            Position = 0)]
        [string[]]$Path,

        [Parameter(Mandatory = $true, ParameterSetName = 'LiteralPathAll')]
        [Parameter(Mandatory = $true,
            ParameterSetName = 'LiteralPath',
            HelpMessage = 'Enter a single filename',
            ValueFromPipeline = $true)]
        [string]$LiteralPath,

        [Parameter(ParameterSetName = 'Path')]
        [Parameter(ParameterSetName = 'LiteralPath')]
        [switch]$Lines,

        [Parameter(ParameterSetName = 'Path')]
        [Parameter(ParameterSetName = 'LiteralPath')]
        [switch]$Words,

        [Parameter(ParameterSetName = 'Path')]
        [Parameter(ParameterSetName = 'LiteralPath')]
        [switch]$Characters,

        [Parameter(Mandatory = $true, ParameterSetName = 'PathAll')]
        [Parameter(Mandatory = $true, ParameterSetName = 'LiteralPathAll')]
        [switch]$All,

        [Parameter(ParameterSetName = 'Path')]
        [Parameter(ParameterSetName = 'PathAll')]
        [switch]$Recurse
    )

    begin {
        if ($All) {
            $Lines = $Words = $Characters = $true
        }
        elseif (($Words -eq $false) -and ($Characters -eq $false)) {
            $Lines = $true
        }

        if ($Path) {
            $Files = Get-ChildItem -Path $Path -Recurse:$Recurse
        }
        else {
            $Files = Get-ChildItem -LiteralPath $LiteralPath
        }
    }
    process {
        foreach ($file in $Files) {
            $result = [ordered]@{ }
            $result.Add('File', $file.fullname)

            $content = Get-Content -LiteralPath $file.fullname

            if ($Lines) { $result.Add('Lines', $content.Length) }

            if ($Words) {
                $wc = 0
                foreach ($line in $content) { $wc += $line.split(' ').Length }
                $result.Add('Words', $wc)
            }

            if ($Characters) {
                $cc = 0
                foreach ($line in $content) { $cc += $line.Length }
                $result.Add('Characters', $cc)
            }

            New-Object -TypeName psobject -Property $result
        }
    }
}
```

Cada conjunto de parâmetros deve ter um parâmetro exclusivo ou uma combinação exclusiva de parâmetros. Os `Path` `PathAll` conjuntos de parâmetros e são muito semelhantes, mas o parâmetro **All** é exclusivo para o `PathAll` conjunto de parâmetros. O mesmo acontece com os `LiteralPath` conjuntos de `LiteralPathAll` parâmetros e. Embora os `PathAll` conjuntos de `LiteralPathAll` parâmetros e tenham o parâmetro **All** , os parâmetros **Path** e **LiteralPath** os diferenciam.

Use `Get-Command -Syntax` mostra a sintaxe de cada conjunto de parâmetros. No entanto, ele não mostra o nome do conjunto de parâmetros. O exemplo a seguir mostra quais parâmetros podem ser usados em cada conjunto de parâmetros.

```powershell
(Get-Command Measure-Lines).ParameterSets |
  Select-Object -Property @{n='ParameterSetName';e={$_.name}},
    @{n='Parameters';e={$_.ToString()}}
```

```Output
ParameterSetName Parameters
---------------- ----------
Path             [-Path] <string[]> [-Lines] [-Words] [-Characters] [-Recurse] [<CommonParameters>]
PathAll          [-Path] <string[]> -All [-Recurse] [<CommonParameters>]
LiteralPath      -LiteralPath <string> [-Lines] [-Words] [-Characters] [<CommonParameters>]
LiteralPathAll   -LiteralPath <string> -All [<CommonParameters>]
```

### <a name="parameter-sets-in-action"></a>Conjuntos de parâmetros em ação

Neste exemplo, estamos usando o conjunto de `PathAll` parâmetros.

```powershell
Measure-Lines test* -All
```

```Output
File                       Lines Words Characters
----                       ----- ----- ----------
C:\temp\test\test.help.txt    31   562       2059
C:\temp\test\test.md          30  1527       3224
C:\temp\test\test.ps1          3     3         79
C:\temp\test\test[1].txt      31   562       2059
```

