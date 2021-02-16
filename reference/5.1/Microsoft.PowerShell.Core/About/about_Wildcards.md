---
description: Descreve como usar caracteres curinga no PowerShell.
Locale: en-US
ms.date: 02/13/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wildcards?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Wildcards
ms.openlocfilehash: 189bff70783b9277f242e8c4ca1c227ae68bae62
ms.sourcegitcommit: 9777152e026c47ba8d319593051416054cb62246
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/16/2021
ms.locfileid: "100529950"
---
# <a name="about-wildcards"></a><span data-ttu-id="9bd87-103">Sobre curingas</span><span class="sxs-lookup"><span data-stu-id="9bd87-103">About Wildcards</span></span>

## <a name="short-description"></a><span data-ttu-id="9bd87-104">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="9bd87-104">SHORT DESCRIPTION</span></span>

<span data-ttu-id="9bd87-105">Descreve como usar caracteres curinga no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9bd87-105">Describes how to use wildcard characters in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="9bd87-106">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="9bd87-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="9bd87-107">Os caracteres curinga representam um ou vários caracteres.</span><span class="sxs-lookup"><span data-stu-id="9bd87-107">Wildcard characters represent one or many characters.</span></span> <span data-ttu-id="9bd87-108">Você pode usá-los para criar padrões do Word em comandos.</span><span class="sxs-lookup"><span data-stu-id="9bd87-108">You can use them to create word patterns in commands.</span></span> <span data-ttu-id="9bd87-109">As expressões curinga são usadas com o `-like` operador ou com qualquer parâmetro que aceita caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="9bd87-109">Wildcard expressions are used with the `-like` operator or with any parameter that accepts wildcards.</span></span>

<span data-ttu-id="9bd87-110">Por exemplo, para corresponder a todos os arquivos no `C:\Techdocs` diretório com uma `.ppt` extensão de nome de arquivo, digite:</span><span class="sxs-lookup"><span data-stu-id="9bd87-110">For example, to match all the files in the `C:\Techdocs` directory with a `.ppt` file name extension, type:</span></span>

```powershell
Get-ChildItem C:\Techdocs\*.ppt
```

<span data-ttu-id="9bd87-111">Nesse caso, o `*` caractere curinga asterisco () representa todos os caracteres que aparecem antes da `.ppt` extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="9bd87-111">In this case, the asterisk (`*`) wildcard character represents any characters that appear before the `.ppt` file name extension.</span></span>

<span data-ttu-id="9bd87-112">As expressões curinga são mais simples do que expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="9bd87-112">Wildcard expressions are simpler than regular expressions.</span></span> <span data-ttu-id="9bd87-113">Para obter mais informações, consulte [about_Regular_Expressions](./about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="9bd87-113">For more information, see [about_Regular_Expressions](./about_Regular_Expressions.md).</span></span>

<span data-ttu-id="9bd87-114">O PowerShell dá suporte aos seguintes caracteres curinga:</span><span class="sxs-lookup"><span data-stu-id="9bd87-114">PowerShell supports the following wildcard characters:</span></span>

|<span data-ttu-id="9bd87-115">Curinga</span><span class="sxs-lookup"><span data-stu-id="9bd87-115">Wildcard</span></span>|<span data-ttu-id="9bd87-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="9bd87-116">Description</span></span>               |<span data-ttu-id="9bd87-117">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9bd87-117">Example</span></span> |<span data-ttu-id="9bd87-118">Correspondência</span><span class="sxs-lookup"><span data-stu-id="9bd87-118">Match</span></span>        |<span data-ttu-id="9bd87-119">Sem correspondência</span><span class="sxs-lookup"><span data-stu-id="9bd87-119">No Match</span></span>|
|--------|--------------------------|--------|-------------|--------|
|\*      |<span data-ttu-id="9bd87-120">Corresponder zero ou mais caracteres</span><span class="sxs-lookup"><span data-stu-id="9bd87-120">Match zero or more characters</span></span> | <span data-ttu-id="9bd87-121">um\*</span><span class="sxs-lookup"><span data-stu-id="9bd87-121">a\*</span></span>  | <span data-ttu-id="9bd87-122">aA, AG, Apple</span><span class="sxs-lookup"><span data-stu-id="9bd87-122">aA, ag, Apple</span></span> | <span data-ttu-id="9bd87-123">banana</span><span class="sxs-lookup"><span data-stu-id="9bd87-123">banana</span></span> |
|<span data-ttu-id="9bd87-124">?</span><span class="sxs-lookup"><span data-stu-id="9bd87-124">?</span></span>       |<span data-ttu-id="9bd87-125">Corresponder um caractere nessa posição</span><span class="sxs-lookup"><span data-stu-id="9bd87-125">Match one character in that position</span></span> | <span data-ttu-id="9bd87-126">? n</span><span class="sxs-lookup"><span data-stu-id="9bd87-126">?n</span></span> | <span data-ttu-id="9bd87-127">um, em, em</span><span class="sxs-lookup"><span data-stu-id="9bd87-127">an, in, on</span></span> | <span data-ttu-id="9bd87-128">executa</span><span class="sxs-lookup"><span data-stu-id="9bd87-128">ran</span></span> |
|<span data-ttu-id="9bd87-129">\[ \]</span><span class="sxs-lookup"><span data-stu-id="9bd87-129">\[ \]</span></span>   |<span data-ttu-id="9bd87-130">Corresponder a um intervalo de caracteres</span><span class="sxs-lookup"><span data-stu-id="9bd87-130">Match a range of characters</span></span> | <span data-ttu-id="9bd87-131">\[a-l \] ook</span><span class="sxs-lookup"><span data-stu-id="9bd87-131">\[a-l\]ook</span></span> | <span data-ttu-id="9bd87-132">livro, Cook, look</span><span class="sxs-lookup"><span data-stu-id="9bd87-132">book, cook, look</span></span> | <span data-ttu-id="9bd87-133">eram</span><span class="sxs-lookup"><span data-stu-id="9bd87-133">took</span></span> |
|<span data-ttu-id="9bd87-134">\[ \]</span><span class="sxs-lookup"><span data-stu-id="9bd87-134">\[ \]</span></span>   |<span data-ttu-id="9bd87-135">Corresponder caracteres específicos</span><span class="sxs-lookup"><span data-stu-id="9bd87-135">Match specific characters</span></span> | <span data-ttu-id="9bd87-136">\[ook de BC \]</span><span class="sxs-lookup"><span data-stu-id="9bd87-136">\[bc\]ook</span></span> | <span data-ttu-id="9bd87-137">livro, Cook</span><span class="sxs-lookup"><span data-stu-id="9bd87-137">book, cook</span></span> | <span data-ttu-id="9bd87-138">fixação</span><span class="sxs-lookup"><span data-stu-id="9bd87-138">hook</span></span> |

<span data-ttu-id="9bd87-139">Você pode incluir vários caracteres curinga no mesmo padrão de palavra.</span><span class="sxs-lookup"><span data-stu-id="9bd87-139">You can include multiple wildcard characters in the same word pattern.</span></span> <span data-ttu-id="9bd87-140">Por exemplo, para localizar arquivos de texto com nomes que começam com as **letras a** a **l**, digite:</span><span class="sxs-lookup"><span data-stu-id="9bd87-140">For example, to find text files with names that begin with the letters **a** through **l**, type:</span></span>

```powershell
Get-ChildItem C:\Techdocs\[a-l]*.txt
```

<span data-ttu-id="9bd87-141">Muitos cmdlets aceitam caracteres curinga em valores de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="9bd87-141">Many cmdlets accept wildcard characters in parameter values.</span></span> <span data-ttu-id="9bd87-142">O tópico da ajuda para cada cmdlet descreve quais parâmetros aceitam caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="9bd87-142">The Help topic for each cmdlet describes which parameters accept wildcard characters.</span></span> <span data-ttu-id="9bd87-143">Para parâmetros que aceitam caracteres curinga, seu uso não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="9bd87-143">For parameters that accept wildcard characters, their use is case-insensitive.</span></span>

<span data-ttu-id="9bd87-144">Você pode usar caracteres curinga em comandos e blocos de script, como para criar um padrão de palavra que representa valores de propriedade.</span><span class="sxs-lookup"><span data-stu-id="9bd87-144">You can use wildcard characters in commands and script blocks, such as to create a word pattern that represents property values.</span></span> <span data-ttu-id="9bd87-145">Por exemplo, o comando a seguir obtém os serviços nos quais o valor da propriedade **ServiceType** inclui **interativo**.</span><span class="sxs-lookup"><span data-stu-id="9bd87-145">For example, the following command gets services in which the **ServiceType** property value includes **Interactive**.</span></span>

```powershell
Get-Service | Where-Object {$_.ServiceType -Like "*Interactive*"}
```

<span data-ttu-id="9bd87-146">No exemplo a seguir, a `If` instrução inclui uma condição que usa caracteres curinga para localizar valores de propriedade.</span><span class="sxs-lookup"><span data-stu-id="9bd87-146">In the following example, the `If` statement includes a condition that uses wildcard characters to find property values.</span></span> <span data-ttu-id="9bd87-147">Se a **Descrição** do ponto de restauração incluir o **PowerShell**, o comando adicionará o valor da propriedade **CreationTime** do ponto de restauração a um arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="9bd87-147">If the restore point's **Description** includes **PowerShell**, the command adds the value of the restore point's **CreationTime** property to a log file.</span></span>

```powershell
$p = Get-ComputerRestorePoint
foreach ($point in $p) {
  if ($point.description -like "*PowerShell*") {
    Add-Content -Path C:\TechDocs\RestoreLog.txt "$($point.CreationTime)"
  }
}
```

## <a name="see-also"></a><span data-ttu-id="9bd87-148">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="9bd87-148">SEE ALSO</span></span>

[<span data-ttu-id="9bd87-149">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="9bd87-149">about_Language_Keywords</span></span>](about_Language_Keywords.md)

[<span data-ttu-id="9bd87-150">about_If</span><span class="sxs-lookup"><span data-stu-id="9bd87-150">about_If</span></span>](about_If.md)

[<span data-ttu-id="9bd87-151">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="9bd87-151">about_Script_Blocks</span></span>](about_Script_Blocks.md)
