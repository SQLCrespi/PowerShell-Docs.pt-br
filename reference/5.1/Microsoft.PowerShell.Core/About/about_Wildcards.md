---
description: Descreve como usar caracteres curinga no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 3/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wildcards?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Wildcards
ms.openlocfilehash: 4656266107a29e4f57c5e273788d382a477a2428
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196128"
---
# <a name="about-wildcards"></a><span data-ttu-id="7f908-104">Sobre curingas</span><span class="sxs-lookup"><span data-stu-id="7f908-104">About Wildcards</span></span>

## <a name="short-description"></a><span data-ttu-id="7f908-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="7f908-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="7f908-106">Descreve como usar caracteres curinga no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f908-106">Describes how to use wildcard characters in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="7f908-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="7f908-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="7f908-108">Os caracteres curinga representam um ou vários caracteres.</span><span class="sxs-lookup"><span data-stu-id="7f908-108">Wildcard characters represent one or many characters.</span></span> <span data-ttu-id="7f908-109">Você pode usá-los para criar padrões do Word em comandos.</span><span class="sxs-lookup"><span data-stu-id="7f908-109">You can use them to create word patterns in commands.</span></span> <span data-ttu-id="7f908-110">Por exemplo, para obter todos os arquivos no `C:\Techdocs` diretório com uma `.ppt` extensão de nome de arquivo, digite:</span><span class="sxs-lookup"><span data-stu-id="7f908-110">For example, to get all the files in the `C:\Techdocs` directory with a `.ppt` file name extension, type:</span></span>

```powershell
Get-ChildItem C:\Techdocs\*.ppt
```

<span data-ttu-id="7f908-111">Nesse caso, o `*` caractere curinga asterisco () representa todos os caracteres que aparecem antes da `.ppt` extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="7f908-111">In this case, the asterisk (`*`) wildcard character represents any characters that appear before the `.ppt` file name extension.</span></span>

<span data-ttu-id="7f908-112">O PowerShell dá suporte aos seguintes caracteres curinga:</span><span class="sxs-lookup"><span data-stu-id="7f908-112">PowerShell supports the following wildcard characters:</span></span>

|<span data-ttu-id="7f908-113">Curinga</span><span class="sxs-lookup"><span data-stu-id="7f908-113">Wildcard</span></span>|<span data-ttu-id="7f908-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="7f908-114">Description</span></span>               |<span data-ttu-id="7f908-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="7f908-115">Example</span></span> |<span data-ttu-id="7f908-116">Corresponder a</span><span class="sxs-lookup"><span data-stu-id="7f908-116">Match</span></span>        |<span data-ttu-id="7f908-117">Sem correspondência</span><span class="sxs-lookup"><span data-stu-id="7f908-117">No Match</span></span>|
|--------|--------------------------|--------|-------------|--------|
|\*      |<span data-ttu-id="7f908-118">Corresponder zero ou mais caracteres</span><span class="sxs-lookup"><span data-stu-id="7f908-118">Match zero or more characters</span></span> | <span data-ttu-id="7f908-119">um\*</span><span class="sxs-lookup"><span data-stu-id="7f908-119">a\*</span></span>  | <span data-ttu-id="7f908-120">aA, AG, Apple</span><span class="sxs-lookup"><span data-stu-id="7f908-120">aA, ag, Apple</span></span> | <span data-ttu-id="7f908-121">banana</span><span class="sxs-lookup"><span data-stu-id="7f908-121">banana</span></span> |
|<span data-ttu-id="7f908-122">?</span><span class="sxs-lookup"><span data-stu-id="7f908-122">?</span></span>       |<span data-ttu-id="7f908-123">Corresponder um caractere nessa posição</span><span class="sxs-lookup"><span data-stu-id="7f908-123">Match one character in that position</span></span> | <span data-ttu-id="7f908-124">? n</span><span class="sxs-lookup"><span data-stu-id="7f908-124">?n</span></span> | <span data-ttu-id="7f908-125">um, em, em</span><span class="sxs-lookup"><span data-stu-id="7f908-125">an, in, on</span></span> | <span data-ttu-id="7f908-126">executa</span><span class="sxs-lookup"><span data-stu-id="7f908-126">ran</span></span> |
|<span data-ttu-id="7f908-127">\[ \]</span><span class="sxs-lookup"><span data-stu-id="7f908-127">\[ \]</span></span>   |<span data-ttu-id="7f908-128">Corresponder a um intervalo de caracteres</span><span class="sxs-lookup"><span data-stu-id="7f908-128">Match a range of characters</span></span> | <span data-ttu-id="7f908-129">\[a-l \] ook</span><span class="sxs-lookup"><span data-stu-id="7f908-129">\[a-l\]ook</span></span> | <span data-ttu-id="7f908-130">livro, Cook, look</span><span class="sxs-lookup"><span data-stu-id="7f908-130">book, cook, look</span></span> | <span data-ttu-id="7f908-131">eram</span><span class="sxs-lookup"><span data-stu-id="7f908-131">took</span></span> |
|<span data-ttu-id="7f908-132">\[ \]</span><span class="sxs-lookup"><span data-stu-id="7f908-132">\[ \]</span></span>   |<span data-ttu-id="7f908-133">Corresponder caracteres específicos</span><span class="sxs-lookup"><span data-stu-id="7f908-133">Match specific characters</span></span> | <span data-ttu-id="7f908-134">\[ook de BC \]</span><span class="sxs-lookup"><span data-stu-id="7f908-134">\[bc\]ook</span></span> | <span data-ttu-id="7f908-135">livro, Cook</span><span class="sxs-lookup"><span data-stu-id="7f908-135">book, cook</span></span> | <span data-ttu-id="7f908-136">fixação</span><span class="sxs-lookup"><span data-stu-id="7f908-136">hook</span></span> |

<span data-ttu-id="7f908-137">Você pode incluir vários caracteres curinga no mesmo padrão de palavra.</span><span class="sxs-lookup"><span data-stu-id="7f908-137">You can include multiple wildcard characters in the same word pattern.</span></span> <span data-ttu-id="7f908-138">Por exemplo, para localizar arquivos de texto com nomes que começam com as **letras a** a **l** , digite:</span><span class="sxs-lookup"><span data-stu-id="7f908-138">For example, to find text files with names that begin with the letters **a** through **l** , type:</span></span>

```powershell
Get-ChildItem C:\Techdocs\[a-l]*.txt
```

<span data-ttu-id="7f908-139">Muitos cmdlets aceitam caracteres curinga em valores de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="7f908-139">Many cmdlets accept wildcard characters in parameter values.</span></span> <span data-ttu-id="7f908-140">O tópico da ajuda para cada cmdlet descreve quais parâmetros aceitam caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="7f908-140">The Help topic for each cmdlet describes which parameters accept wildcard characters.</span></span> <span data-ttu-id="7f908-141">Para parâmetros que aceitam caracteres curinga, seu uso não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="7f908-141">For parameters that accept wildcard characters, their use is case-insensitive.</span></span>

<span data-ttu-id="7f908-142">Você pode usar caracteres curinga em comandos e blocos de script, como para criar um padrão de palavra que representa valores de propriedade.</span><span class="sxs-lookup"><span data-stu-id="7f908-142">You can use wildcard characters in commands and script blocks, such as to create a word pattern that represents property values.</span></span> <span data-ttu-id="7f908-143">Por exemplo, o comando a seguir obtém os serviços nos quais o valor da propriedade **ServiceType** inclui **interativo** .</span><span class="sxs-lookup"><span data-stu-id="7f908-143">For example, the following command gets services in which the **ServiceType** property value includes **Interactive** .</span></span>

```powershell
Get-Service | Where-Object {$_.ServiceType -Like "*Interactive*"}
```

<span data-ttu-id="7f908-144">No exemplo a seguir, a `If` instrução inclui uma condição que usa caracteres curinga para localizar valores de propriedade.</span><span class="sxs-lookup"><span data-stu-id="7f908-144">In the following example, the `If` statement includes a condition that uses wildcard characters to find property values.</span></span> <span data-ttu-id="7f908-145">Se a **Descrição** do ponto de restauração incluir o **PowerShell** , o comando adicionará o valor da propriedade **CreationTime** do ponto de restauração a um arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="7f908-145">If the restore point's **Description** includes **PowerShell** , the command adds the value of the restore point's **CreationTime** property to a log file.</span></span>

```powershell
$p = Get-ComputerRestorePoint
foreach ($point in $p) {
  if ($point.description -like "*PowerShell*") {
    Add-Content -Path C:\TechDocs\RestoreLog.txt "$($point.CreationTime)"
  }
}
```

## <a name="see-also"></a><span data-ttu-id="7f908-146">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="7f908-146">SEE ALSO</span></span>

[<span data-ttu-id="7f908-147">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="7f908-147">about_Language_Keywords</span></span>](about_Language_Keywords.md)

[<span data-ttu-id="7f908-148">about_If</span><span class="sxs-lookup"><span data-stu-id="7f908-148">about_If</span></span>](about_If.md)

[<span data-ttu-id="7f908-149">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="7f908-149">about_Script_Blocks</span></span>](about_Script_Blocks.md)
