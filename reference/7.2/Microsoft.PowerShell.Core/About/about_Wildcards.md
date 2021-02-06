---
description: Descreve como usar caracteres curinga no PowerShell.
Locale: en-US
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wildcards?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Wildcards
ms.openlocfilehash: b5f13fdbfbc24e19e5ad0b1cd6ecc1b99f68914f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598633"
---
# <a name="about-wildcards"></a><span data-ttu-id="4fc2d-103">Sobre curingas</span><span class="sxs-lookup"><span data-stu-id="4fc2d-103">About Wildcards</span></span>

## <a name="short-description"></a><span data-ttu-id="4fc2d-104">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="4fc2d-104">SHORT DESCRIPTION</span></span>

<span data-ttu-id="4fc2d-105">Descreve como usar caracteres curinga no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-105">Describes how to use wildcard characters in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="4fc2d-106">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="4fc2d-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="4fc2d-107">Os caracteres curinga representam um ou vários caracteres.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-107">Wildcard characters represent one or many characters.</span></span> <span data-ttu-id="4fc2d-108">Você pode usá-los para criar padrões do Word em comandos.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-108">You can use them to create word patterns in commands.</span></span> <span data-ttu-id="4fc2d-109">Por exemplo, para obter todos os arquivos no `C:\Techdocs` diretório com uma `.ppt` extensão de nome de arquivo, digite:</span><span class="sxs-lookup"><span data-stu-id="4fc2d-109">For example, to get all the files in the `C:\Techdocs` directory with a `.ppt` file name extension, type:</span></span>

```powershell
Get-ChildItem C:\Techdocs\*.ppt
```

<span data-ttu-id="4fc2d-110">Nesse caso, o `*` caractere curinga asterisco () representa todos os caracteres que aparecem antes da `.ppt` extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-110">In this case, the asterisk (`*`) wildcard character represents any characters that appear before the `.ppt` file name extension.</span></span>

<span data-ttu-id="4fc2d-111">O PowerShell dá suporte aos seguintes caracteres curinga:</span><span class="sxs-lookup"><span data-stu-id="4fc2d-111">PowerShell supports the following wildcard characters:</span></span>

|<span data-ttu-id="4fc2d-112">Curinga</span><span class="sxs-lookup"><span data-stu-id="4fc2d-112">Wildcard</span></span>|<span data-ttu-id="4fc2d-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="4fc2d-113">Description</span></span>               |<span data-ttu-id="4fc2d-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="4fc2d-114">Example</span></span> |<span data-ttu-id="4fc2d-115">Correspondência</span><span class="sxs-lookup"><span data-stu-id="4fc2d-115">Match</span></span>        |<span data-ttu-id="4fc2d-116">Sem correspondência</span><span class="sxs-lookup"><span data-stu-id="4fc2d-116">No Match</span></span>|
|--------|--------------------------|--------|-------------|--------|
|\*      |<span data-ttu-id="4fc2d-117">Corresponder zero ou mais caracteres</span><span class="sxs-lookup"><span data-stu-id="4fc2d-117">Match zero or more characters</span></span> | <span data-ttu-id="4fc2d-118">um\*</span><span class="sxs-lookup"><span data-stu-id="4fc2d-118">a\*</span></span>  | <span data-ttu-id="4fc2d-119">aA, AG, Apple</span><span class="sxs-lookup"><span data-stu-id="4fc2d-119">aA, ag, Apple</span></span> | <span data-ttu-id="4fc2d-120">banana</span><span class="sxs-lookup"><span data-stu-id="4fc2d-120">banana</span></span> |
|<span data-ttu-id="4fc2d-121">?</span><span class="sxs-lookup"><span data-stu-id="4fc2d-121">?</span></span>       |<span data-ttu-id="4fc2d-122">Corresponder um caractere nessa posição</span><span class="sxs-lookup"><span data-stu-id="4fc2d-122">Match one character in that position</span></span> | <span data-ttu-id="4fc2d-123">? n</span><span class="sxs-lookup"><span data-stu-id="4fc2d-123">?n</span></span> | <span data-ttu-id="4fc2d-124">um, em, em</span><span class="sxs-lookup"><span data-stu-id="4fc2d-124">an, in, on</span></span> | <span data-ttu-id="4fc2d-125">executa</span><span class="sxs-lookup"><span data-stu-id="4fc2d-125">ran</span></span> |
|<span data-ttu-id="4fc2d-126">\[ \]</span><span class="sxs-lookup"><span data-stu-id="4fc2d-126">\[ \]</span></span>   |<span data-ttu-id="4fc2d-127">Corresponder a um intervalo de caracteres</span><span class="sxs-lookup"><span data-stu-id="4fc2d-127">Match a range of characters</span></span> | <span data-ttu-id="4fc2d-128">\[a-l \] ook</span><span class="sxs-lookup"><span data-stu-id="4fc2d-128">\[a-l\]ook</span></span> | <span data-ttu-id="4fc2d-129">livro, Cook, look</span><span class="sxs-lookup"><span data-stu-id="4fc2d-129">book, cook, look</span></span> | <span data-ttu-id="4fc2d-130">eram</span><span class="sxs-lookup"><span data-stu-id="4fc2d-130">took</span></span> |
|<span data-ttu-id="4fc2d-131">\[ \]</span><span class="sxs-lookup"><span data-stu-id="4fc2d-131">\[ \]</span></span>   |<span data-ttu-id="4fc2d-132">Corresponder caracteres específicos</span><span class="sxs-lookup"><span data-stu-id="4fc2d-132">Match specific characters</span></span> | <span data-ttu-id="4fc2d-133">\[ook de BC \]</span><span class="sxs-lookup"><span data-stu-id="4fc2d-133">\[bc\]ook</span></span> | <span data-ttu-id="4fc2d-134">livro, Cook</span><span class="sxs-lookup"><span data-stu-id="4fc2d-134">book, cook</span></span> | <span data-ttu-id="4fc2d-135">fixação</span><span class="sxs-lookup"><span data-stu-id="4fc2d-135">hook</span></span> |

<span data-ttu-id="4fc2d-136">Você pode incluir vários caracteres curinga no mesmo padrão de palavra.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-136">You can include multiple wildcard characters in the same word pattern.</span></span> <span data-ttu-id="4fc2d-137">Por exemplo, para localizar arquivos de texto com nomes que começam com as **letras a** a **l**, digite:</span><span class="sxs-lookup"><span data-stu-id="4fc2d-137">For example, to find text files with names that begin with the letters **a** through **l**, type:</span></span>

```powershell
Get-ChildItem C:\Techdocs\[a-l]*.txt
```

<span data-ttu-id="4fc2d-138">Muitos cmdlets aceitam caracteres curinga em valores de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-138">Many cmdlets accept wildcard characters in parameter values.</span></span> <span data-ttu-id="4fc2d-139">O tópico da ajuda para cada cmdlet descreve quais parâmetros aceitam caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-139">The Help topic for each cmdlet describes which parameters accept wildcard characters.</span></span> <span data-ttu-id="4fc2d-140">Para parâmetros que aceitam caracteres curinga, seu uso não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-140">For parameters that accept wildcard characters, their use is case-insensitive.</span></span>

<span data-ttu-id="4fc2d-141">Você pode usar caracteres curinga em comandos e blocos de script, como para criar um padrão de palavra que representa valores de propriedade.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-141">You can use wildcard characters in commands and script blocks, such as to create a word pattern that represents property values.</span></span> <span data-ttu-id="4fc2d-142">Por exemplo, o comando a seguir obtém os serviços nos quais o valor da propriedade **ServiceType** inclui **interativo**.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-142">For example, the following command gets services in which the **ServiceType** property value includes **Interactive**.</span></span>

```powershell
Get-Service | Where-Object {$_.ServiceType -Like "*Interactive*"}
```

<span data-ttu-id="4fc2d-143">No exemplo a seguir, a `If` instrução inclui uma condição que usa caracteres curinga para localizar valores de propriedade.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-143">In the following example, the `If` statement includes a condition that uses wildcard characters to find property values.</span></span> <span data-ttu-id="4fc2d-144">Se a **Descrição** do ponto de restauração incluir o **PowerShell**, o comando adicionará o valor da propriedade **CreationTime** do ponto de restauração a um arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="4fc2d-144">If the restore point's **Description** includes **PowerShell**, the command adds the value of the restore point's **CreationTime** property to a log file.</span></span>

```powershell
$p = Get-ComputerRestorePoint
foreach ($point in $p) {
  if ($point.description -like "*PowerShell*") {
    Add-Content -Path C:\TechDocs\RestoreLog.txt "$($point.CreationTime)"
  }
}
```

## <a name="see-also"></a><span data-ttu-id="4fc2d-145">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="4fc2d-145">SEE ALSO</span></span>

[<span data-ttu-id="4fc2d-146">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="4fc2d-146">about_Language_Keywords</span></span>](about_Language_Keywords.md)

[<span data-ttu-id="4fc2d-147">about_If</span><span class="sxs-lookup"><span data-stu-id="4fc2d-147">about_If</span></span>](about_If.md)

[<span data-ttu-id="4fc2d-148">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="4fc2d-148">about_Script_Blocks</span></span>](about_Script_Blocks.md)

