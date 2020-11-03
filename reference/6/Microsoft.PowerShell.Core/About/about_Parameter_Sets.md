---
description: Descreve como definir e usar conjuntos de parâmetros em funções avançadas.
title: about_Parameter_Sets
ms.date: 02/11/2020
ms.openlocfilehash: e4cfbc13f981bcc93c8a0a3c799851e83df7746c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195694"
---
# <a name="about-parameter-sets"></a><span data-ttu-id="0db69-103">Sobre conjuntos de parâmetros</span><span class="sxs-lookup"><span data-stu-id="0db69-103">About parameter sets</span></span>

## <a name="short-description"></a><span data-ttu-id="0db69-104">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="0db69-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="0db69-105">Descreve como definir e usar conjuntos de parâmetros em funções avançadas.</span><span class="sxs-lookup"><span data-stu-id="0db69-105">Describes how to define and use parameter sets in advanced functions.</span></span>

## <a name="long-description"></a><span data-ttu-id="0db69-106">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="0db69-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="0db69-107">O PowerShell usa conjuntos de parâmetros para permitir que você escreva uma única função que pode fazer ações diferentes para cenários diferentes.</span><span class="sxs-lookup"><span data-stu-id="0db69-107">PowerShell uses parameter sets to enable you to write a single function that can do different actions for different scenarios.</span></span> <span data-ttu-id="0db69-108">Os conjuntos de parâmetros permitem que você exponha parâmetros diferentes para o usuário.</span><span class="sxs-lookup"><span data-stu-id="0db69-108">Parameter sets enable you to expose different parameters to the user.</span></span> <span data-ttu-id="0db69-109">E, para retornar informações diferentes com base nos parâmetros especificados pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="0db69-109">And, to return different information based on the parameters specified by the user.</span></span>

## <a name="parameter-set-requirements"></a><span data-ttu-id="0db69-110">Requisitos do conjunto de parâmetros</span><span class="sxs-lookup"><span data-stu-id="0db69-110">Parameter set requirements</span></span>

<span data-ttu-id="0db69-111">Os requisitos a seguir se aplicam a todos os conjuntos de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="0db69-111">The following requirements apply to all parameter sets.</span></span>

- <span data-ttu-id="0db69-112">Cada conjunto de parâmetros deve ter pelo menos um parâmetro exclusivo.</span><span class="sxs-lookup"><span data-stu-id="0db69-112">Each parameter set must have at least one unique parameter.</span></span> <span data-ttu-id="0db69-113">Se possível, torne esse parâmetro um parâmetro obrigatório.</span><span class="sxs-lookup"><span data-stu-id="0db69-113">If possible, make this parameter a mandatory parameter.</span></span>

- <span data-ttu-id="0db69-114">Um conjunto de parâmetros que contém vários parâmetros posicionais deve definir posições exclusivas para cada parâmetro.</span><span class="sxs-lookup"><span data-stu-id="0db69-114">A parameter set that contains multiple positional parameters must define unique positions for each parameter.</span></span> <span data-ttu-id="0db69-115">Dois parâmetros posicionais não podem especificar a mesma posição.</span><span class="sxs-lookup"><span data-stu-id="0db69-115">No two positional parameters can specify the same position.</span></span>

- <span data-ttu-id="0db69-116">Somente um parâmetro em um conjunto pode declarar a `ValueFromPipeline` palavra-chave com um valor de `true` .</span><span class="sxs-lookup"><span data-stu-id="0db69-116">Only one parameter in a set can declare the `ValueFromPipeline` keyword with a value of `true`.</span></span> <span data-ttu-id="0db69-117">Vários parâmetros podem definir a `ValueFromPipelineByPropertyName` palavra-chave com um valor de `true` .</span><span class="sxs-lookup"><span data-stu-id="0db69-117">Multiple parameters can define the `ValueFromPipelineByPropertyName` keyword with a value of `true`.</span></span>

- <span data-ttu-id="0db69-118">Se nenhum conjunto de parâmetros for especificado para um parâmetro, o parâmetro pertencerá a todos os conjuntos de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="0db69-118">If no parameter set is specified for a parameter, the parameter belongs to all parameter sets.</span></span>

> [!NOTE]
> <span data-ttu-id="0db69-119">Há um limite de 32 conjuntos de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="0db69-119">There is a limit of 32 parameter sets.</span></span>

## <a name="default-parameter-sets"></a><span data-ttu-id="0db69-120">Conjuntos de parâmetros padrão</span><span class="sxs-lookup"><span data-stu-id="0db69-120">Default parameter sets</span></span>

<span data-ttu-id="0db69-121">Quando vários conjuntos de parâmetros são definidos, a `DefaultParameterSetName` palavra-chave do atributo **CmdletBinding** especifica o conjunto de parâmetros padrão.</span><span class="sxs-lookup"><span data-stu-id="0db69-121">When multiple parameter sets are defined, the `DefaultParameterSetName` keyword of the **CmdletBinding** attribute specifies the default parameter set.</span></span>
<span data-ttu-id="0db69-122">O PowerShell usa o conjunto de parâmetros padrão quando não pode determinar o conjunto de parâmetros a ser usado com base nas informações fornecidas para o comando.</span><span class="sxs-lookup"><span data-stu-id="0db69-122">PowerShell uses the default parameter set when it can't determine the parameter set to use based on the information provided to the command.</span></span> <span data-ttu-id="0db69-123">Para obter mais informações sobre o atributo **CmdletBinding** , consulte [about_Functions_CmdletBindingAttribute](about_functions_cmdletbindingattribute.md).</span><span class="sxs-lookup"><span data-stu-id="0db69-123">For more information about the **CmdletBinding** attribute, see [about_functions_cmdletbindingattribute](about_functions_cmdletbindingattribute.md).</span></span>

## <a name="declaring-parameter-sets"></a><span data-ttu-id="0db69-124">Declarando conjuntos de parâmetros</span><span class="sxs-lookup"><span data-stu-id="0db69-124">Declaring parameter sets</span></span>

<span data-ttu-id="0db69-125">Para criar um conjunto de parâmetros, você deve especificar a `ParameterSetName` palavra-chave do atributo de **parâmetro** para cada parâmetro no conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="0db69-125">To create a parameter set, you must specify the `ParameterSetName` keyword of the **Parameter** attribute for every parameter in the parameter set.</span></span> <span data-ttu-id="0db69-126">Para parâmetros que pertencem a vários conjuntos de parâmetros, adicione um atributo de **parâmetro** para cada conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="0db69-126">For parameters that belong to multiple parameter sets, add a **Parameter** attribute for each parameter set.</span></span>

<span data-ttu-id="0db69-127">O atributo **Parameter** permite que você defina o parâmetro de forma diferente para cada conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="0db69-127">The **Parameter** attribute enables you to define the parameter differently for each parameter set.</span></span> <span data-ttu-id="0db69-128">Por exemplo, você pode definir um parâmetro como obrigatório em um conjunto e opcional em outro.</span><span class="sxs-lookup"><span data-stu-id="0db69-128">For example, you can define a parameter as mandatory in one set and optional in another.</span></span> <span data-ttu-id="0db69-129">No entanto, cada conjunto de parâmetros deve conter pelo menos um parâmetro exclusivo.</span><span class="sxs-lookup"><span data-stu-id="0db69-129">However, each parameter set must contain at least one unique parameter.</span></span>

<span data-ttu-id="0db69-130">Parâmetros que não têm um nome de conjunto de parâmetros atribuído pertencem a todos os conjuntos de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="0db69-130">Parameters that don't have an assigned parameter set name belong to all parameter sets.</span></span>

### <a name="example"></a><span data-ttu-id="0db69-131">Exemplo</span><span class="sxs-lookup"><span data-stu-id="0db69-131">Example</span></span>

<span data-ttu-id="0db69-132">A função de exemplo a seguir conta o número de linhas, caracteres e palavras em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="0db69-132">The following example function counts the number lines, characters, and words in a text file.</span></span> <span data-ttu-id="0db69-133">Usando parâmetros, você pode especificar quais valores você deseja que sejam retornados e quais arquivos deseja medir.</span><span class="sxs-lookup"><span data-stu-id="0db69-133">Using parameters, you can specify which values you want returned and which files you want to measure.</span></span> <span data-ttu-id="0db69-134">Há quatro conjuntos de parâmetros definidos:</span><span class="sxs-lookup"><span data-stu-id="0db69-134">There are four parameter sets defined:</span></span>

- <span data-ttu-id="0db69-135">Caminho</span><span class="sxs-lookup"><span data-stu-id="0db69-135">Path</span></span>
- <span data-ttu-id="0db69-136">PathAll</span><span class="sxs-lookup"><span data-stu-id="0db69-136">PathAll</span></span>
- <span data-ttu-id="0db69-137">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0db69-137">LiteralPath</span></span>
- <span data-ttu-id="0db69-138">LiteralPathAll</span><span class="sxs-lookup"><span data-stu-id="0db69-138">LiteralPathAll</span></span>

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

<span data-ttu-id="0db69-139">Cada conjunto de parâmetros deve ter um parâmetro exclusivo ou uma combinação exclusiva de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="0db69-139">Each parameter set must have a unique parameter or a unique combination of parameters.</span></span> <span data-ttu-id="0db69-140">Os `Path` `PathAll` conjuntos de parâmetros e são muito semelhantes, mas o parâmetro **All** é exclusivo para o `PathAll` conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="0db69-140">The `Path` and `PathAll` parameter sets are very similar but the **All** parameter is unique to the `PathAll` parameter set.</span></span> <span data-ttu-id="0db69-141">O mesmo acontece com os `LiteralPath` conjuntos de `LiteralPathAll` parâmetros e.</span><span class="sxs-lookup"><span data-stu-id="0db69-141">The same is true with the `LiteralPath` and `LiteralPathAll` parameter sets.</span></span> <span data-ttu-id="0db69-142">Embora os `PathAll` conjuntos de `LiteralPathAll` parâmetros e tenham o parâmetro **All** , os parâmetros **Path** e **LiteralPath** os diferenciam.</span><span class="sxs-lookup"><span data-stu-id="0db69-142">Even though the `PathAll` and `LiteralPathAll` parameter sets both have the **All** parameter, the **Path** and **LiteralPath** parameters differentiate them.</span></span>

<span data-ttu-id="0db69-143">Use `Get-Command -Syntax` mostra a sintaxe de cada conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="0db69-143">Use `Get-Command -Syntax` shows you the syntax of each parameter set.</span></span> <span data-ttu-id="0db69-144">No entanto, ele não mostra o nome do conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="0db69-144">However it does not show the name of the parameter set.</span></span> <span data-ttu-id="0db69-145">O exemplo a seguir mostra quais parâmetros podem ser usados em cada conjunto de parâmetros.</span><span class="sxs-lookup"><span data-stu-id="0db69-145">The following example shows which parameters can be used in each parameter set.</span></span>

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

### <a name="parameter-sets-in-action"></a><span data-ttu-id="0db69-146">Conjuntos de parâmetros em ação</span><span class="sxs-lookup"><span data-stu-id="0db69-146">Parameter sets in action</span></span>

<span data-ttu-id="0db69-147">Neste exemplo, estamos usando o conjunto de `PathAll` parâmetros.</span><span class="sxs-lookup"><span data-stu-id="0db69-147">In this example, we are using the `PathAll` parameter set.</span></span>

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
