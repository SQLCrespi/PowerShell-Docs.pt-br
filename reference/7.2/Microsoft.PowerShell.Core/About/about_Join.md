---
description: Descreve como o operador de junção (-join) combina várias cadeias de caracteres em uma única cadeia.
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_join?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Join
ms.openlocfilehash: d76e95aaeca1b5b94bb1a2216576a985ffb209c0
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597599"
---
# <a name="about-join"></a><span data-ttu-id="9b742-103">Sobre a junção</span><span class="sxs-lookup"><span data-stu-id="9b742-103">About join</span></span>

## <a name="short-description"></a><span data-ttu-id="9b742-104">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="9b742-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="9b742-105">Descreve como o operador de junção (-join) combina várias cadeias de caracteres em uma única cadeia.</span><span class="sxs-lookup"><span data-stu-id="9b742-105">Describes how the join operator (-join) combines multiple strings into a single string.</span></span>

## <a name="long-description"></a><span data-ttu-id="9b742-106">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="9b742-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="9b742-107">O operador Join concatena um conjunto de cadeias de caracteres em uma única cadeia.</span><span class="sxs-lookup"><span data-stu-id="9b742-107">The join operator concatenates a set of strings into a single string.</span></span> <span data-ttu-id="9b742-108">As cadeias são anexadas à cadeia de caracteres resultante na ordem em que aparecem no comando.</span><span class="sxs-lookup"><span data-stu-id="9b742-108">The strings are appended to the resulting string in the order that they appear in the command.</span></span>

### <a name="syntax"></a><span data-ttu-id="9b742-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b742-109">Syntax</span></span>

<span data-ttu-id="9b742-110">O diagrama a seguir mostra a sintaxe para o operador join.</span><span class="sxs-lookup"><span data-stu-id="9b742-110">The following diagram shows the syntax for the join operator.</span></span>

```powershell
-Join <String[]>
<String[]> -Join <Delimiter>
```

#### <a name="parameters"></a><span data-ttu-id="9b742-111">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="9b742-111">Parameters</span></span>

<span data-ttu-id="9b742-112">String [] – Especifica uma ou mais cadeias de caracteres a serem unidas.</span><span class="sxs-lookup"><span data-stu-id="9b742-112">String[] - Specifies one or more strings to be joined.</span></span>

<span data-ttu-id="9b742-113">Delimitador-especifica um ou mais caracteres colocados entre as cadeias concatenadas.</span><span class="sxs-lookup"><span data-stu-id="9b742-113">Delimiter - Specifies one or more characters placed between the concatenated strings.</span></span> <span data-ttu-id="9b742-114">O padrão é nenhum delimitador ("").</span><span class="sxs-lookup"><span data-stu-id="9b742-114">The default is no delimiter ("").</span></span>

<span data-ttu-id="9b742-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="9b742-115">Remarks</span></span>

<span data-ttu-id="9b742-116">O operador de junção unário (-Join <String [] >) tem precedência maior do que uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="9b742-116">The unary join operator (-join <string[]>) has higher precedence than a comma.</span></span> <span data-ttu-id="9b742-117">Como resultado, se você enviar uma lista separada por vírgulas de cadeias de caracteres para o operador unário, somente a primeira cadeia de caracteres (antes da primeira vírgula) será enviada ao operador join.</span><span class="sxs-lookup"><span data-stu-id="9b742-117">As a result, if you submit a comma-separated list of strings to the unary join operator, only the first string (before the first comma) is submitted to the join operator.</span></span>

<span data-ttu-id="9b742-118">Para usar o operador unário Join, coloque as cadeias de caracteres entre parênteses ou armazene as cadeias de caracteres em uma variável e, em seguida, envie a variável para join.</span><span class="sxs-lookup"><span data-stu-id="9b742-118">To use the unary join operator, enclose the strings in parentheses, or store the strings in a variable, and then submit the variable to join.</span></span>

<span data-ttu-id="9b742-119">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9b742-119">For example:</span></span>

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

### <a name="examples"></a><span data-ttu-id="9b742-120">Exemplos</span><span class="sxs-lookup"><span data-stu-id="9b742-120">Examples</span></span>

<span data-ttu-id="9b742-121">A instrução a seguir une três cadeias de caracteres:</span><span class="sxs-lookup"><span data-stu-id="9b742-121">The following statement joins three strings:</span></span>

```powershell
-join ("Windows", "PowerShell", "2.0")
WindowsPowerShell2.0
```

<span data-ttu-id="9b742-122">A instrução a seguir une três cadeias de caracteres delimitadas por um espaço:</span><span class="sxs-lookup"><span data-stu-id="9b742-122">The following statement joins three strings delimited by a space:</span></span>

```powershell
"Windows", "PowerShell", "2.0" -join " "
Windows PowerShell 2.0
```

<span data-ttu-id="9b742-123">As instruções a seguir usam um delimitador de vários caracteres para unir três cadeias:</span><span class="sxs-lookup"><span data-stu-id="9b742-123">The following statements use a multiple-character delimiter to join three strings:</span></span>

```powershell
$a = "WIND", "S P", "ERSHELL"
$a -join "OW"
WINDOWS POWERSHELL
```

<span data-ttu-id="9b742-124">A instrução a seguir une as linhas em uma cadeia de caracteres here em uma única cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9b742-124">The following statement joins the lines in a here-string into a single string.</span></span> <span data-ttu-id="9b742-125">Como uma cadeia de caracteres here é uma cadeia de caracteres, as linhas na cadeia de caracteres here devem ser divididas antes que possam ser Unidas.</span><span class="sxs-lookup"><span data-stu-id="9b742-125">Because a here-string is one string, the lines in the here-string must be split before they can be joined.</span></span> <span data-ttu-id="9b742-126">Você pode usar esse método para reassociar as cadeias de caracteres em um arquivo XML que foi salvo em uma cadeia de caracteres aqui:</span><span class="sxs-lookup"><span data-stu-id="9b742-126">You can use this method to rejoin the strings in an XML file that has been saved in a here-string:</span></span>

```powershell
$a = @'
a
b
c
'@

(-split $a) -join " "
a b c
```

## <a name="see-also"></a><span data-ttu-id="9b742-127">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="9b742-127">SEE ALSO</span></span>

[<span data-ttu-id="9b742-128">about_Operators</span><span class="sxs-lookup"><span data-stu-id="9b742-128">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="9b742-129">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="9b742-129">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="9b742-130">about_Split</span><span class="sxs-lookup"><span data-stu-id="9b742-130">about_Split</span></span>](about_Split.md)

