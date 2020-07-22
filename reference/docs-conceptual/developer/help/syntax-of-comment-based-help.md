---
title: Sintaxe de ajuda baseada em comentários
ms.date: 09/12/2016
ms.openlocfilehash: 950afecc39f9d27207f77547679faab700481458
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893213"
---
# <a name="syntax-of-comment-based-help"></a><span data-ttu-id="59726-102">Sintaxe de ajuda baseada em comentários</span><span class="sxs-lookup"><span data-stu-id="59726-102">Syntax of Comment-Based Help</span></span>

<span data-ttu-id="59726-103">Esta seção descreve a sintaxe da ajuda baseada em comentários.</span><span class="sxs-lookup"><span data-stu-id="59726-103">This section describes the syntax of comment-based help.</span></span>

## <a name="syntax-diagram"></a><span data-ttu-id="59726-104">Diagrama de sintaxe</span><span class="sxs-lookup"><span data-stu-id="59726-104">Syntax Diagram</span></span>

 <span data-ttu-id="59726-105">A sintaxe da ajuda baseada em comentários é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="59726-105">The syntax for comment-based Help is as follows:</span></span>

```
# .< help keyword>
# <help content>

-or -

<#
.< help keyword>
< help content>
#>
```

## <a name="syntax-description"></a><span data-ttu-id="59726-106">Descrição da sintaxe</span><span class="sxs-lookup"><span data-stu-id="59726-106">Syntax Description</span></span>

 <span data-ttu-id="59726-107">A ajuda baseada em comentários é escrita como uma série de comentários.</span><span class="sxs-lookup"><span data-stu-id="59726-107">Comment-based Help is written as a series of comments.</span></span> <span data-ttu-id="59726-108">Você pode digitar um símbolo de comentário ( `#` ) antes de cada linha de comentários ou pode usar os `<#` `#>` símbolos e para criar um bloco de comentários.</span><span class="sxs-lookup"><span data-stu-id="59726-108">You can type a comment symbol (`#`) before each line of comments, or you can use the `<#` and `#>` symbols to create a comment block.</span></span> <span data-ttu-id="59726-109">Todas as linhas dentro do bloco de comentários são interpretadas como comentários.</span><span class="sxs-lookup"><span data-stu-id="59726-109">All the lines within the comment block are interpreted as comments.</span></span>

 <span data-ttu-id="59726-110">Cada seção da ajuda baseada em comentários é definida por uma palavra-chave e cada palavra-chave é precedida por um ponto ( `.` ).</span><span class="sxs-lookup"><span data-stu-id="59726-110">Each section of comment-based Help is defined by a keyword and each keyword is preceded by a dot (`.`).</span></span> <span data-ttu-id="59726-111">As palavras-chave podem aparecer em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="59726-111">The keywords can appear in any order.</span></span> <span data-ttu-id="59726-112">Os nomes de palavra-chave não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="59726-112">The keyword names are not case-sensitive.</span></span>

 <span data-ttu-id="59726-113">Um bloco de comentário deve conter pelo menos uma palavra-chave de ajuda.</span><span class="sxs-lookup"><span data-stu-id="59726-113">A comment block must contain at least one help keyword.</span></span> <span data-ttu-id="59726-114">Algumas das palavras-chave, como **example**, podem aparecer muitas vezes no mesmo bloco de comentário.</span><span class="sxs-lookup"><span data-stu-id="59726-114">Some of the keywords, such as **EXAMPLE**, can appear many times in the same comment block.</span></span> <span data-ttu-id="59726-115">O conteúdo da ajuda para cada palavra-chave começa na linha após a palavra-chave e pode abranger várias linhas.</span><span class="sxs-lookup"><span data-stu-id="59726-115">The Help content for each keyword begins on the line after the keyword and can span multiple lines.</span></span>

 <span data-ttu-id="59726-116">Todas as linhas em um tópico de ajuda com base em comentários devem ser contíguas.</span><span class="sxs-lookup"><span data-stu-id="59726-116">All of the lines in a comment-based Help topic must be contiguous.</span></span> <span data-ttu-id="59726-117">Se um tópico de ajuda baseado em comentário seguir um comentário que não faz parte do tópico da ajuda, deve haver pelo menos uma linha em branco entre a última linha de comentário de não ajuda e o início da ajuda baseada em comentários.</span><span class="sxs-lookup"><span data-stu-id="59726-117">If a comment-based Help topic follows a comment that is not part of the Help topic, there must be at least one blank line between the last non-Help comment line and the beginning of the comment-based Help.</span></span>

 <span data-ttu-id="59726-118">Por exemplo, o tópico de ajuda baseado em comentário a seguir contém o. Palavra-chave Description e seu valor, que é uma descrição de uma função ou script.</span><span class="sxs-lookup"><span data-stu-id="59726-118">For example, the following comment-based help topic contains the .Description keyword and its value, which is a description of a function or script.</span></span>

```powershell
<#
    .Description
    The Get-Function function displays the name and syntax of all functions in the session.
#>
```
