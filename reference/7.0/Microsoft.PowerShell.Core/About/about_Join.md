---
description: Descreve como o operador de junção (-join) combina várias cadeias de caracteres em uma única cadeia.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_join?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Join
ms.openlocfilehash: d89b9066ef34e814c0e546246c7b50cfc73bcb38
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195897"
---
# <a name="about-join"></a><span data-ttu-id="0467f-104">Sobre a junção</span><span class="sxs-lookup"><span data-stu-id="0467f-104">About join</span></span>

## <a name="short-description"></a><span data-ttu-id="0467f-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="0467f-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="0467f-106">Descreve como o operador de junção (-join) combina várias cadeias de caracteres em uma única cadeia.</span><span class="sxs-lookup"><span data-stu-id="0467f-106">Describes how the join operator (-join) combines multiple strings into a single string.</span></span>

## <a name="long-description"></a><span data-ttu-id="0467f-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="0467f-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="0467f-108">O operador Join concatena um conjunto de cadeias de caracteres em uma única cadeia.</span><span class="sxs-lookup"><span data-stu-id="0467f-108">The join operator concatenates a set of strings into a single string.</span></span> <span data-ttu-id="0467f-109">As cadeias são anexadas à cadeia de caracteres resultante na ordem em que aparecem no comando.</span><span class="sxs-lookup"><span data-stu-id="0467f-109">The strings are appended to the resulting string in the order that they appear in the command.</span></span>

### <a name="syntax"></a><span data-ttu-id="0467f-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="0467f-110">Syntax</span></span>

<span data-ttu-id="0467f-111">O diagrama a seguir mostra a sintaxe para o operador join.</span><span class="sxs-lookup"><span data-stu-id="0467f-111">The following diagram shows the syntax for the join operator.</span></span>

```powershell
-Join <String[]>
<String[]> -Join <Delimiter>
```

#### <a name="parameters"></a><span data-ttu-id="0467f-112">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="0467f-112">Parameters</span></span>

<span data-ttu-id="0467f-113">String [] – Especifica uma ou mais cadeias de caracteres a serem unidas.</span><span class="sxs-lookup"><span data-stu-id="0467f-113">String[] - Specifies one or more strings to be joined.</span></span>

<span data-ttu-id="0467f-114">Delimitador-especifica um ou mais caracteres colocados entre as cadeias concatenadas.</span><span class="sxs-lookup"><span data-stu-id="0467f-114">Delimiter - Specifies one or more characters placed between the concatenated strings.</span></span> <span data-ttu-id="0467f-115">O padrão é nenhum delimitador ("").</span><span class="sxs-lookup"><span data-stu-id="0467f-115">The default is no delimiter ("").</span></span>

<span data-ttu-id="0467f-116">Comentários</span><span class="sxs-lookup"><span data-stu-id="0467f-116">Remarks</span></span>

<span data-ttu-id="0467f-117">O operador de junção unário (-Join <String [] >) tem precedência maior do que uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="0467f-117">The unary join operator (-join <string[]>) has higher precedence than a comma.</span></span> <span data-ttu-id="0467f-118">Como resultado, se você enviar uma lista separada por vírgulas de cadeias de caracteres para o operador unário, somente a primeira cadeia de caracteres (antes da primeira vírgula) será enviada ao operador join.</span><span class="sxs-lookup"><span data-stu-id="0467f-118">As a result, if you submit a comma-separated list of strings to the unary join operator, only the first string (before the first comma) is submitted to the join operator.</span></span>

<span data-ttu-id="0467f-119">Para usar o operador unário Join, coloque as cadeias de caracteres entre parênteses ou armazene as cadeias de caracteres em uma variável e, em seguida, envie a variável para join.</span><span class="sxs-lookup"><span data-stu-id="0467f-119">To use the unary join operator, enclose the strings in parentheses, or store the strings in a variable, and then submit the variable to join.</span></span>

<span data-ttu-id="0467f-120">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0467f-120">For example:</span></span>

```powershell
-join "a", "b", "c"
a
b
c

-join ("a", "b", "c")
abc

$z = "a", "b", "c"
-join $z
abc
```

### <a name="examples"></a><span data-ttu-id="0467f-121">Exemplos</span><span class="sxs-lookup"><span data-stu-id="0467f-121">Examples</span></span>

<span data-ttu-id="0467f-122">A instrução a seguir une três cadeias de caracteres:</span><span class="sxs-lookup"><span data-stu-id="0467f-122">The following statement joins three strings:</span></span>

```powershell
-join ("Windows", "PowerShell", "2.0")
WindowsPowerShell2.0
```

<span data-ttu-id="0467f-123">A instrução a seguir une três cadeias de caracteres delimitadas por um espaço:</span><span class="sxs-lookup"><span data-stu-id="0467f-123">The following statement joins three strings delimited by a space:</span></span>

```powershell
"Windows", "PowerShell", "2.0" -join " "
Windows PowerShell 2.0
```

<span data-ttu-id="0467f-124">As instruções a seguir usam um delimitador de vários caracteres para unir três cadeias:</span><span class="sxs-lookup"><span data-stu-id="0467f-124">The following statements use a multiple-character delimiter to join three strings:</span></span>

```powershell
$a = "WIND", "S P", "ERSHELL"
$a -join "OW"
WINDOWS POWERSHELL
```

<span data-ttu-id="0467f-125">A instrução a seguir une as linhas em uma cadeia de caracteres here em uma única cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="0467f-125">The following statement joins the lines in a here-string into a single string.</span></span> <span data-ttu-id="0467f-126">Como uma cadeia de caracteres here é uma cadeia de caracteres, as linhas na cadeia de caracteres here devem ser divididas antes que possam ser Unidas.</span><span class="sxs-lookup"><span data-stu-id="0467f-126">Because a here-string is one string, the lines in the here-string must be split before they can be joined.</span></span> <span data-ttu-id="0467f-127">Você pode usar esse método para reassociar as cadeias de caracteres em um arquivo XML que foi salvo em uma cadeia de caracteres aqui:</span><span class="sxs-lookup"><span data-stu-id="0467f-127">You can use this method to rejoin the strings in an XML file that has been saved in a here-string:</span></span>

```powershell
$a = @'
a
b
c
'@

(-split $a) -join " "
a b c
```

## <a name="see-also"></a><span data-ttu-id="0467f-128">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="0467f-128">SEE ALSO</span></span>

[<span data-ttu-id="0467f-129">about_Operators</span><span class="sxs-lookup"><span data-stu-id="0467f-129">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="0467f-130">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="0467f-130">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="0467f-131">about_Split</span><span class="sxs-lookup"><span data-stu-id="0467f-131">about_Split</span></span>](about_Split.md)
