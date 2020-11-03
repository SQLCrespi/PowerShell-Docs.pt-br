---
description: Descreve maneiras mais fáceis e mais naturais de scripts de filtros para coleções de objetos.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_simplified_syntax?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Simplified_Syntax
ms.openlocfilehash: d2e603b4d2092d4ba4ed9c1d7253991cc34ddca8
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195622"
---
# <a name="about_simplified_syntax"></a><span data-ttu-id="2f5d8-104">about_Simplified_Syntax</span><span class="sxs-lookup"><span data-stu-id="2f5d8-104">about_Simplified_Syntax</span></span>

## <a name="short-description"></a><span data-ttu-id="2f5d8-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="2f5d8-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="2f5d8-106">Descreve maneiras mais fáceis e mais naturais de scripts de filtros para coleções de objetos.</span><span class="sxs-lookup"><span data-stu-id="2f5d8-106">Describes easier, more natural-language ways of scripting filters for collections of objects.</span></span>

## <a name="long-description"></a><span data-ttu-id="2f5d8-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="2f5d8-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="2f5d8-108">A sintaxe simplificada, introduzida no Windows PowerShell 3,0, permite que você crie alguns comandos de filtro sem usar blocos de script.</span><span class="sxs-lookup"><span data-stu-id="2f5d8-108">Simplified syntax, introduced in Windows PowerShell 3.0, lets you build some filter commands without using script blocks.</span></span> <span data-ttu-id="2f5d8-109">A sintaxe simplificada se assemelha mais à linguagem natural e é principalmente útil com coleções de objetos que são canalizados para comandos `Where-Object` e `ForEach-Object` seus aliases correspondentes `where` e `foreach` .</span><span class="sxs-lookup"><span data-stu-id="2f5d8-109">The simplified syntax more closely resembles natural language, and is primarily useful with collections of objects that get piped into commands `Where-Object` and `ForEach-Object` and their corresponding aliases `where` and `foreach`.</span></span>

<span data-ttu-id="2f5d8-110">Você pode usar um método nos membros de uma coleção (mais comumente, uma matriz) sem referir-se à variável automática `$_` dentro de um bloco de script.</span><span class="sxs-lookup"><span data-stu-id="2f5d8-110">You can use a method on the members of a collection (most commonly, an array) without referring to the automatic variable `$_` inside a script block.</span></span>

<span data-ttu-id="2f5d8-111">Considere as duas invocações a seguir:</span><span class="sxs-lookup"><span data-stu-id="2f5d8-111">Consider the following two invocations:</span></span>

### <a name="standard-syntax"></a><span data-ttu-id="2f5d8-112">Sintaxe padrão</span><span class="sxs-lookup"><span data-stu-id="2f5d8-112">Standard Syntax</span></span>

```powershell
dir Cert:\LocalMachine\Root | where { $_.FriendlyName -eq 'Verisign' }
dir Cert:\ -Recurse | foreach { $_.GetKeyAlgorithm() }
```

### <a name="simplified-syntax"></a><span data-ttu-id="2f5d8-113">Sintaxe simplificada</span><span class="sxs-lookup"><span data-stu-id="2f5d8-113">Simplified syntax</span></span>

<span data-ttu-id="2f5d8-114">Na sintaxe simplificada, os operadores de comparação que funcionam em membros de objetos em uma coleção são tratados como parâmetros.</span><span class="sxs-lookup"><span data-stu-id="2f5d8-114">Under the simplified syntax, comparison operators that work on members of objects in a collection are treated as parameters.</span></span> <span data-ttu-id="2f5d8-115">Você pode invocar um método em objetos em uma coleção sem fazer referência à variável automática `$_` dentro de um bloco de script.</span><span class="sxs-lookup"><span data-stu-id="2f5d8-115">You can invoke a method on objects in a collection without referring to the automatic variable `$_` inside a script block.</span></span>
<span data-ttu-id="2f5d8-116">Compare as duas invocações a seguir para aquelas do exemplo anterior:</span><span class="sxs-lookup"><span data-stu-id="2f5d8-116">Compare the following two invocations to those of the previous example:</span></span>
```powershell
dir Cert:\LocalMachine\Root | where FriendlyName -eq 'Verisign'
dir Cert:\ -Recurse | foreach GetKeyAlgorithm
```

<span data-ttu-id="2f5d8-117">Embora ambas as sintaxes funcionem, a sintaxe simplificada retorna resultados sem fazer referência à variável automática `$_` dentro de um bloco de script.</span><span class="sxs-lookup"><span data-stu-id="2f5d8-117">While both syntaxes work, the simplified syntax returns results without referring to the automatic variable `$_` inside a script block.</span></span>
<span data-ttu-id="2f5d8-118">O nome do método `GetKeyAlgorithm` é tratado como um parâmetro de `ForEach-Object` .</span><span class="sxs-lookup"><span data-stu-id="2f5d8-118">The method name `GetKeyAlgorithm` is treated as a parameter of `ForEach-Object`.</span></span>
<span data-ttu-id="2f5d8-119">O segundo comando retorna os mesmos resultados, mas sem erros, porque a sintaxe simplificada não tenta retornar resultados para itens para os quais o argumento especificado não se aplica.</span><span class="sxs-lookup"><span data-stu-id="2f5d8-119">The second command returns the same results, but without errors, because the simplified syntax does not attempt to return results for items for which the specified argument did not apply.</span></span>

<span data-ttu-id="2f5d8-120">Neste exemplo, a `Process` propriedade `Description` é passada como o parâmetro de nome de membro para o `ForEach-Object` comando.</span><span class="sxs-lookup"><span data-stu-id="2f5d8-120">In this example, the `Process` property `Description` is passed as the member name parameter to the `ForEach-Object` command.</span></span> <span data-ttu-id="2f5d8-121">Os resultados são descrições de processos ativos.</span><span class="sxs-lookup"><span data-stu-id="2f5d8-121">The results are descriptions of active processes.</span></span>

```powershell
Get-Process | foreach Description
```

<span data-ttu-id="2f5d8-122">Neste exemplo, o `DirectoryInfo` método `GetFiles` é passado como o parâmetro de nome de membro do `ForEach-Object` comando.</span><span class="sxs-lookup"><span data-stu-id="2f5d8-122">In this example, the `DirectoryInfo` method `GetFiles` is passed as the member name parameter of the `ForEach-Object` command.</span></span>  
<span data-ttu-id="2f5d8-123">O método é chamado com o parâmetro de padrão de pesquisa `.*` .</span><span class="sxs-lookup"><span data-stu-id="2f5d8-123">The method is called with the search pattern parameter `.*`.</span></span>  
<span data-ttu-id="2f5d8-124">Os resultados são `FileInfo` registros para todos os arquivos ocultos em estilo UNIX em diretórios base do usuário.</span><span class="sxs-lookup"><span data-stu-id="2f5d8-124">The results are `FileInfo` records for all Unix-style hidden files in user home directories.</span></span> 

```powershell
Get-ChildItem /home -Directory | foreach GetFiles .*
```

## <a name="see-also"></a><span data-ttu-id="2f5d8-125">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="2f5d8-125">SEE ALSO</span></span>

- [<span data-ttu-id="2f5d8-126">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="2f5d8-126">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)
- [<span data-ttu-id="2f5d8-127">about_Foreach</span><span class="sxs-lookup"><span data-stu-id="2f5d8-127">about_Foreach</span></span>](about_Foreach.md)
- [<span data-ttu-id="2f5d8-128">Where-Object</span><span class="sxs-lookup"><span data-stu-id="2f5d8-128">Where-Object</span></span>](xref:Microsoft.PowerShell.Core.Where-Object)
- [<span data-ttu-id="2f5d8-129">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="2f5d8-129">Foreach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)
