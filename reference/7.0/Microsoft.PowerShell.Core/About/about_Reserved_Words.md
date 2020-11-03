---
description: Lista as palavras reservadas que não podem ser usadas como identificadores porque elas têm um significado especial no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_reserved_words?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Reserved_Words
ms.openlocfilehash: c4b67a523a40319635d159791b80ab302b9aa3b4
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196267"
---
# <a name="about-reserved-words"></a><span data-ttu-id="9302c-104">Sobre palavras reservadas</span><span class="sxs-lookup"><span data-stu-id="9302c-104">About Reserved Words</span></span>

## <a name="short-description"></a><span data-ttu-id="9302c-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="9302c-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="9302c-106">Lista as palavras reservadas que não podem ser usadas como identificadores porque elas têm um significado especial no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9302c-106">Lists the reserved words that cannot be used as identifiers because they have a special meaning in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="9302c-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="9302c-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="9302c-108">Há certas palavras que têm significado especial no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9302c-108">There are certain words that have special meaning in PowerShell.</span></span> <span data-ttu-id="9302c-109">Quando essas palavras aparecem sem aspas, o PowerShell tenta aplicar seu significado especial em vez de tratá-las como cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="9302c-109">When these words appear without quotation marks, PowerShell attempts to apply their special meaning rather than treating them as character strings.</span></span> <span data-ttu-id="9302c-110">Para usar essas palavras como argumentos de parâmetro em um comando ou script sem invocar seu significado especial, coloque as palavras reservadas entre aspas.</span><span class="sxs-lookup"><span data-stu-id="9302c-110">To use these words as parameter arguments in a command or script without invoking their special meaning, enclose the reserved words in quotation marks.</span></span>

<span data-ttu-id="9302c-111">A seguir estão as palavras reservadas no PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9302c-111">The following are the reserved words in PowerShell:</span></span>

```
assembly         exit            process
base             filter          public
begin            finally         return
break            for             sequence
catch            foreach         static
class            from (*)        switch
command          function        throw
configuration    hidden          trap
continue         if              try
data             in              type
define (*)       inlinescript    until
do               interface       using
dynamicparam     module          var (*)
else             namespace       while
elseif           parallel        workflow
end              param
enum             private

(*) These keywords are reserved for future use.
```

<span data-ttu-id="9302c-112">Várias palavras-chave de linguagem, incluindo `Foreach` ,, `If` `For` e `While` , têm seus próprios artigos de ajuda.</span><span class="sxs-lookup"><span data-stu-id="9302c-112">Several language keywords, including `Foreach`, `If`, `For`, and `While`, have their own help articles.</span></span> <span data-ttu-id="9302c-113">Para exibi-los, digite `Get-Help about_` e adicione a palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="9302c-113">To view them, type `Get-Help about_` and add the keyword.</span></span> <span data-ttu-id="9302c-114">Por exemplo, para obter informações sobre a `Foreach` instrução, digite:</span><span class="sxs-lookup"><span data-stu-id="9302c-114">For example, to get information about the `Foreach` statement, type:</span></span>

```powershell
Get-Help about_ForEach
```

<span data-ttu-id="9302c-115">Para obter informações sobre a `Filter` instrução ou a `Return` sintaxe da instrução, digite:</span><span class="sxs-lookup"><span data-stu-id="9302c-115">For information about the `Filter` statement or the `Return` statement syntax, type:</span></span>

```powershell
Get-Help about_Functions
```

<span data-ttu-id="9302c-116">Para obter informações sobre outras palavras reservadas, digite:</span><span class="sxs-lookup"><span data-stu-id="9302c-116">For information about other reserved words, type:</span></span>

```powershell
Get-Help <Reserved_Word>
```

> [!NOTE]
> <span data-ttu-id="9302c-117">Nem todas as palavras reservadas têm seu próprio artigo de ajuda.</span><span class="sxs-lookup"><span data-stu-id="9302c-117">Not every reserved word has its own help article.</span></span> <span data-ttu-id="9302c-118">Se o `Get-Help` não retornar um artigo, você poderá procurar artigos que falam sobre a palavra reservada usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="9302c-118">If `Get-Help` does not return an article, you can search for articles that talk about the reserved word using the following command:</span></span>
>
> ```powershell
> Get-Help <Reserved_Word> -Category:HelpFile
> ```

## <a name="see-also"></a><span data-ttu-id="9302c-119">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="9302c-119">SEE ALSO</span></span>

- [<span data-ttu-id="9302c-120">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="9302c-120">about_Command_Syntax</span></span>](about_Command_Syntax.md)
- [<span data-ttu-id="9302c-121">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="9302c-121">about_Language_Keywords</span></span>](about_Language_Keywords.md)
- [<span data-ttu-id="9302c-122">about_Parsing</span><span class="sxs-lookup"><span data-stu-id="9302c-122">about_Parsing</span></span>](about_Parsing.md)
- [<span data-ttu-id="9302c-123">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="9302c-123">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)
- [<span data-ttu-id="9302c-124">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="9302c-124">about_Script_Blocks</span></span>](about_Script_Blocks.md)
- [<span data-ttu-id="9302c-125">about_Special_Characters</span><span class="sxs-lookup"><span data-stu-id="9302c-125">about_Special_Characters</span></span>](about_Special_Characters.md)
