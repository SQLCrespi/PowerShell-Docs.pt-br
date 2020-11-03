---
description: Descreve como escrever tópicos de ajuda baseados em comentários para funções e scripts.
keywords: powershell, cmdlet
ms.date: 06/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comment_based_help?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comment_Based_Help
ms.openlocfilehash: eaf1ea3eaacf944e9489292ea46822d655f2068b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196033"
---
# <a name="about-comment-based-help"></a><span data-ttu-id="75758-104">Sobre a ajuda baseada em comentários</span><span class="sxs-lookup"><span data-stu-id="75758-104">About Comment-based Help</span></span>

## <a name="short-description"></a><span data-ttu-id="75758-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="75758-105">Short description</span></span>
<span data-ttu-id="75758-106">Descreve como escrever tópicos de ajuda baseados em comentários para funções e scripts.</span><span class="sxs-lookup"><span data-stu-id="75758-106">Describes how to write comment-based help topics for functions and scripts.</span></span>

## <a name="long-description"></a><span data-ttu-id="75758-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="75758-107">Long description</span></span>

<span data-ttu-id="75758-108">Você pode escrever tópicos de ajuda baseados em comentários para funções e scripts usando palavras-chave de comentário de ajuda especial.</span><span class="sxs-lookup"><span data-stu-id="75758-108">You can write comment-based help topics for functions and scripts by using special help comment keywords.</span></span>

<span data-ttu-id="75758-109">O cmdlet [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) exibe a ajuda baseada em comentários no mesmo formato em que ele exibe os tópicos de ajuda do cmdlet que são gerados a partir de arquivos XML.</span><span class="sxs-lookup"><span data-stu-id="75758-109">The [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) cmdlet displays comment-based help in the same format in which it displays the cmdlet help topics that are generated from XML files.</span></span> <span data-ttu-id="75758-110">Os usuários podem usar todos os parâmetros do `Get-Help` , como **detalhado** , **completo** , **exemplos** e **online** , para exibir o conteúdo da ajuda baseada em comentários.</span><span class="sxs-lookup"><span data-stu-id="75758-110">Users can use all of the parameters of `Get-Help`, such as **Detailed** , **Full** , **Examples** , and **Online** , to display the contents of comment-based help.</span></span>

<span data-ttu-id="75758-111">Você também pode gravar arquivos de ajuda baseados em XML para funções e scripts.</span><span class="sxs-lookup"><span data-stu-id="75758-111">You can also write XML-based help files for functions and scripts.</span></span> <span data-ttu-id="75758-112">Para habilitar o `Get-Help` cmdlet para localizar o arquivo de ajuda baseado em XML para uma função ou um script, use a `.ExternalHelp` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="75758-112">To enable the `Get-Help` cmdlet to find the XML-based help file for a function or script, use the `.ExternalHelp` keyword.</span></span> <span data-ttu-id="75758-113">Sem essa palavra-chave, `Get-Help` não é possível encontrar tópicos de ajuda baseados em XML para funções ou scripts.</span><span class="sxs-lookup"><span data-stu-id="75758-113">Without this keyword, `Get-Help` cannot find XML-based help topics for functions or scripts.</span></span>

<span data-ttu-id="75758-114">Este tópico explica como escrever tópicos de ajuda para funções e scripts.</span><span class="sxs-lookup"><span data-stu-id="75758-114">This topic explains how to write help topics for functions and scripts.</span></span> <span data-ttu-id="75758-115">Para obter informações sobre como exibir tópicos da ajuda para funções e scripts, consulte [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help).</span><span class="sxs-lookup"><span data-stu-id="75758-115">For information about how to display help topics for functions and scripts, see [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help).</span></span>

<span data-ttu-id="75758-116">Os cmdlets [Update-Help](xref:Microsoft.PowerShell.Core.Update-Help) e [Save-Help](xref:Microsoft.PowerShell.Core.Save-Help) funcionam apenas em arquivos XML.</span><span class="sxs-lookup"><span data-stu-id="75758-116">The [Update-Help](xref:Microsoft.PowerShell.Core.Update-Help) and [Save-Help](xref:Microsoft.PowerShell.Core.Save-Help) cmdlets work only on XML files.</span></span> <span data-ttu-id="75758-117">A ajuda atualizável não oferece suporte a tópicos de ajuda baseados em comentários.</span><span class="sxs-lookup"><span data-stu-id="75758-117">Updatable Help does not support comment-based help topics.</span></span>

## <a name="syntax-for-comment-based-help"></a><span data-ttu-id="75758-118">Sintaxe para ajuda baseada em comentários</span><span class="sxs-lookup"><span data-stu-id="75758-118">Syntax for comment-based help</span></span>

<span data-ttu-id="75758-119">A sintaxe da ajuda baseada em comentários é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="75758-119">The syntax for comment-based help is as follows:</span></span>

```
# .<help keyword>
# <help content>
```

<span data-ttu-id="75758-120">ou</span><span class="sxs-lookup"><span data-stu-id="75758-120">or</span></span>

```
<#
.<help keyword>
<help content>
#>
```

<span data-ttu-id="75758-121">A ajuda baseada em comentários é escrita como uma série de comentários.</span><span class="sxs-lookup"><span data-stu-id="75758-121">Comment-based help is written as a series of comments.</span></span> <span data-ttu-id="75758-122">Você pode digitar um símbolo de comentário `#` antes de cada linha de comentários ou pode usar os `<#` `#>` símbolos e para criar um bloco de comentários.</span><span class="sxs-lookup"><span data-stu-id="75758-122">You can type a comment symbol `#` before each line of comments, or you can use the `<#` and `#>` symbols to create a comment block.</span></span> <span data-ttu-id="75758-123">Todas as linhas dentro do bloco de comentários são interpretadas como comentários.</span><span class="sxs-lookup"><span data-stu-id="75758-123">All the lines within the comment block are interpreted as comments.</span></span>

<span data-ttu-id="75758-124">Todas as linhas em um tópico de ajuda com base em comentários devem ser contíguas.</span><span class="sxs-lookup"><span data-stu-id="75758-124">All of the lines in a comment-based help topic must be contiguous.</span></span> <span data-ttu-id="75758-125">Se um tópico de ajuda baseado em comentário seguir um comentário que não faz parte do tópico da ajuda, deve haver pelo menos uma linha em branco entre a última linha de comentário de não ajuda e o início da ajuda baseada em comentários.</span><span class="sxs-lookup"><span data-stu-id="75758-125">If a comment-based help topic follows a comment that is not part of the help topic, there must be at least one blank line between the last non-help comment line and the beginning of the comment-based help.</span></span>

<span data-ttu-id="75758-126">As palavras-chave definem cada seção da ajuda baseada em comentários.</span><span class="sxs-lookup"><span data-stu-id="75758-126">Keywords define each section of comment-based help.</span></span> <span data-ttu-id="75758-127">Cada palavra-chave de ajuda baseada em comentários é precedida por um ponto `.` .</span><span class="sxs-lookup"><span data-stu-id="75758-127">Each comment-based help keyword is preceded by a dot `.`.</span></span> <span data-ttu-id="75758-128">As palavras-chave podem aparecer em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="75758-128">The keywords can appear in any order.</span></span> <span data-ttu-id="75758-129">Os nomes de palavra-chave não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="75758-129">The keyword names are not case-sensitive.</span></span>

<span data-ttu-id="75758-130">Por exemplo, a `.Description` palavra-chave precede uma descrição de uma função ou script.</span><span class="sxs-lookup"><span data-stu-id="75758-130">For example, the `.Description` keyword precedes a description of a function or script.</span></span>

```
<#
.Description
Get-Function displays the name and syntax of all functions in the session.
#>
```

<span data-ttu-id="75758-131">O bloco de comentário deve conter pelo menos uma palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="75758-131">The comment block must contain at least one keyword.</span></span> <span data-ttu-id="75758-132">Algumas das palavras-chave, como `.EXAMPLE` , podem aparecer muitas vezes no mesmo bloco de comentário.</span><span class="sxs-lookup"><span data-stu-id="75758-132">Some of the keywords, such as `.EXAMPLE`, can appear many times in the same comment block.</span></span> <span data-ttu-id="75758-133">O conteúdo da ajuda para cada palavra-chave começa na linha após a palavra-chave e pode abranger várias linhas.</span><span class="sxs-lookup"><span data-stu-id="75758-133">The help content for each keyword begins on the line after the keyword and can span multiple lines.</span></span>

## <a name="syntax-for-comment-based-help-in-functions"></a><span data-ttu-id="75758-134">Sintaxe para ajuda baseada em comentários em funções</span><span class="sxs-lookup"><span data-stu-id="75758-134">Syntax for comment-based help in functions</span></span>

<span data-ttu-id="75758-135">A ajuda baseada em comentários para uma função pode aparecer em um dos três locais:</span><span class="sxs-lookup"><span data-stu-id="75758-135">Comment-based help for a function can appear in one of three locations:</span></span>

- <span data-ttu-id="75758-136">No início do corpo da função.</span><span class="sxs-lookup"><span data-stu-id="75758-136">At the beginning of the function body.</span></span>
- <span data-ttu-id="75758-137">No final do corpo da função.</span><span class="sxs-lookup"><span data-stu-id="75758-137">At the end of the function body.</span></span>
- <span data-ttu-id="75758-138">Antes da `function` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="75758-138">Before the `function` keyword.</span></span> <span data-ttu-id="75758-139">Não pode haver mais de uma linha em branco entre a última linha da ajuda da função e a `function` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="75758-139">There cannot be more than one blank line between the last line of the function help and the `function` keyword.</span></span>

<span data-ttu-id="75758-140">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="75758-140">For example:</span></span>

```powershell
function Get-Function
{
<#
.<help keyword>
<help content>
#>

  # function logic
}
```

<span data-ttu-id="75758-141">ou</span><span class="sxs-lookup"><span data-stu-id="75758-141">or</span></span>

```powershell
function Get-Function
{
   # function logic

<#
.<help keyword>
<help content>
#>
}
```

<span data-ttu-id="75758-142">ou</span><span class="sxs-lookup"><span data-stu-id="75758-142">or</span></span>

```powershell
<#
.<help keyword>
<help content>
#>
function Get-Function { }
```

## <a name="syntax-for-comment-based-help-in-scripts"></a><span data-ttu-id="75758-143">Sintaxe para ajuda baseada em comentários em scripts</span><span class="sxs-lookup"><span data-stu-id="75758-143">Syntax for comment-based help in scripts</span></span>

<span data-ttu-id="75758-144">A ajuda baseada em comentários para um script pode aparecer em um dos dois locais a seguir no script.</span><span class="sxs-lookup"><span data-stu-id="75758-144">Comment-based help for a script can appear in one of the following two locations in the script.</span></span>

- <span data-ttu-id="75758-145">No início do arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="75758-145">At the beginning of the script file.</span></span> <span data-ttu-id="75758-146">A ajuda do script pode ser precedida no script somente por comentários e linhas em branco.</span><span class="sxs-lookup"><span data-stu-id="75758-146">Script help can be preceded in the script only by comments and blank lines.</span></span>

  <span data-ttu-id="75758-147">Se o primeiro item no corpo do script (após a ajuda) for uma declaração de função, deve haver pelo menos duas linhas em branco entre o final da ajuda do script e a declaração da função.</span><span class="sxs-lookup"><span data-stu-id="75758-147">If the first item in the script body (after the help) is a function declaration, there must be at least two blank lines between the end of the script help and the function declaration.</span></span> <span data-ttu-id="75758-148">Caso contrário, a ajuda será interpretada como sendo ajuda para a função, não ajuda para o script.</span><span class="sxs-lookup"><span data-stu-id="75758-148">Otherwise, the help is interpreted as being help for the function, not help for the script.</span></span>

- <span data-ttu-id="75758-149">No final do arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="75758-149">At the end of the script file.</span></span> <span data-ttu-id="75758-150">No entanto, se o script for assinado, coloque a ajuda baseada em comentários no início do arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="75758-150">However, if the script is signed, place Comment-based help at the beginning of the script file.</span></span> <span data-ttu-id="75758-151">O final do script é ocupado pelo bloco de assinatura.</span><span class="sxs-lookup"><span data-stu-id="75758-151">The end of the script is occupied by the signature block.</span></span>

<span data-ttu-id="75758-152">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="75758-152">For example:</span></span>

```powershell
<#
.<help keyword>
<help content>
#>


function Get-Function { }
```

<span data-ttu-id="75758-153">ou</span><span class="sxs-lookup"><span data-stu-id="75758-153">or</span></span>

```powershell
function Get-Function { }

<#
.<help keyword>
<help content>
#>
```

## <a name="syntax-for-comment-based-help-in-script-modules"></a><span data-ttu-id="75758-154">Sintaxe para ajuda baseada em comentários em módulos de script</span><span class="sxs-lookup"><span data-stu-id="75758-154">Syntax for comment-based help in script modules</span></span>

<span data-ttu-id="75758-155">Em um módulo de script `.psm1` , a ajuda baseada em comentários usa a sintaxe para funções, não a sintaxe para scripts.</span><span class="sxs-lookup"><span data-stu-id="75758-155">In a script module `.psm1`, comment-based help uses the syntax for functions, not the syntax for scripts.</span></span> <span data-ttu-id="75758-156">Você não pode usar a sintaxe de script para fornecer ajuda para todas as funções definidas em um módulo de script.</span><span class="sxs-lookup"><span data-stu-id="75758-156">You cannot use the script syntax to provide help for all functions defined in a script module.</span></span>

<span data-ttu-id="75758-157">Por exemplo, se você estiver usando a `.ExternalHelp` palavra-chave para identificar os arquivos de ajuda baseados em XML para as funções em um módulo de script, deverá adicionar um `.ExternalHelp` comentário a cada função.</span><span class="sxs-lookup"><span data-stu-id="75758-157">For example, if you are using the `.ExternalHelp` keyword to identify the XML-based help files for the functions in a script module, you must add an `.ExternalHelp` comment to each function.</span></span>

```powershell
# .ExternalHelp <XML-file-name>
function <function-name>
{
  ...
}
```

## <a name="comment-based-help-keywords"></a><span data-ttu-id="75758-158">Palavras-chave de ajuda com base em comentários</span><span class="sxs-lookup"><span data-stu-id="75758-158">Comment-based help keywords</span></span>

<span data-ttu-id="75758-159">Veja a seguir as palavras-chave de ajuda com base em comentários válidas.</span><span class="sxs-lookup"><span data-stu-id="75758-159">The following are valid comment-based help keywords.</span></span> <span data-ttu-id="75758-160">Eles são listados na ordem em que normalmente aparecem em um tópico da ajuda junto com o uso pretendido.</span><span class="sxs-lookup"><span data-stu-id="75758-160">They are listed in the order in which they typically appear in a help topic along with their intended use.</span></span> <span data-ttu-id="75758-161">Essas palavras-chave podem aparecer em qualquer ordem na Ajuda baseada em comentários e não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="75758-161">These keywords can appear in any order in the comment-based help, and they are not case-sensitive.</span></span>

### <a name="synopsis"></a><span data-ttu-id="75758-162">. Resumo</span><span class="sxs-lookup"><span data-stu-id="75758-162">.SYNOPSIS</span></span>

<span data-ttu-id="75758-163">Uma breve descrição da função ou do script.</span><span class="sxs-lookup"><span data-stu-id="75758-163">A brief description of the function or script.</span></span> <span data-ttu-id="75758-164">Essa palavra-chave pode ser usada apenas uma vez em cada tópico.</span><span class="sxs-lookup"><span data-stu-id="75758-164">This keyword can be used only once in each topic.</span></span>

### <a name="description"></a><span data-ttu-id="75758-165">. NDESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="75758-165">.DESCRIPTION</span></span>

<span data-ttu-id="75758-166">Uma descrição detalhada da função ou do script.</span><span class="sxs-lookup"><span data-stu-id="75758-166">A detailed description of the function or script.</span></span> <span data-ttu-id="75758-167">Essa palavra-chave pode ser usada apenas uma vez em cada tópico.</span><span class="sxs-lookup"><span data-stu-id="75758-167">This keyword can be used only once in each topic.</span></span>

### <a name="parameter"></a><span data-ttu-id="75758-168">. METER</span><span class="sxs-lookup"><span data-stu-id="75758-168">.PARAMETER</span></span>

<span data-ttu-id="75758-169">A descrição de um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="75758-169">The description of a parameter.</span></span> <span data-ttu-id="75758-170">Adicione uma `.PARAMETER` palavra-chave para cada parâmetro na sintaxe da função ou do script.</span><span class="sxs-lookup"><span data-stu-id="75758-170">Add a `.PARAMETER` keyword for each parameter in the function or script syntax.</span></span>

<span data-ttu-id="75758-171">Digite o nome do parâmetro na mesma linha que a `.PARAMETER` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="75758-171">Type the parameter name on the same line as the `.PARAMETER` keyword.</span></span> <span data-ttu-id="75758-172">Digite a descrição do parâmetro nas linhas que seguem a `.PARAMETER` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="75758-172">Type the parameter description on the lines following the `.PARAMETER` keyword.</span></span> <span data-ttu-id="75758-173">O Windows PowerShell interpreta todo o texto entre a `.PARAMETER` linha e a palavra-chave Next ou o final do bloco de comentários como parte da descrição do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="75758-173">Windows PowerShell interprets all text between the `.PARAMETER` line and the next keyword or the end of the comment block as part of the parameter description.</span></span>
<span data-ttu-id="75758-174">A descrição pode incluir quebras de parágrafo.</span><span class="sxs-lookup"><span data-stu-id="75758-174">The description can include paragraph breaks.</span></span>

```
.PARAMETER  <Parameter-Name>
```

<span data-ttu-id="75758-175">As palavras-chave do parâmetro podem aparecer em qualquer ordem no bloco de comentários, mas a sintaxe da função ou do script determina a ordem na qual os parâmetros (e suas descrições) aparecem no tópico da ajuda.</span><span class="sxs-lookup"><span data-stu-id="75758-175">The Parameter keywords can appear in any order in the comment block, but the function or script syntax determines the order in which the parameters (and their descriptions) appear in help topic.</span></span> <span data-ttu-id="75758-176">Para alterar a ordem, altere a sintaxe.</span><span class="sxs-lookup"><span data-stu-id="75758-176">To change the order, change the syntax.</span></span>

<span data-ttu-id="75758-177">Você também pode especificar uma descrição de parâmetro colocando um comentário na sintaxe da função ou do script imediatamente antes do nome da variável de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="75758-177">You can also specify a parameter description by placing a comment in the function or script syntax immediately before the parameter variable name.</span></span> <span data-ttu-id="75758-178">Para que isso funcione, você também deve ter um bloco de comentário com pelo menos uma palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="75758-178">For this to work, you must also have a comment block with at least one keyword.</span></span>

<span data-ttu-id="75758-179">Se você usar um comentário de sintaxe e uma `.PARAMETER` palavra-chave, a descrição associada à `.PARAMETER` palavra-chave será usada e o comentário de sintaxe será ignorado.</span><span class="sxs-lookup"><span data-stu-id="75758-179">If you use both a syntax comment and a `.PARAMETER` keyword, the description associated with the `.PARAMETER` keyword is used, and the syntax comment is ignored.</span></span>

```powershell
<#
.SYNOPSIS
    Short description here
#>
function Verb-Noun {
    [CmdletBinding()]
    param (
        # This is the same as .Parameter
        [string]$Computername
    )
    # Verb the Noun on the computer
}
```

### <a name="example"></a><span data-ttu-id="75758-180">. EXEMPLO</span><span class="sxs-lookup"><span data-stu-id="75758-180">.EXAMPLE</span></span>

<span data-ttu-id="75758-181">Um comando de exemplo que usa a função ou o script, opcionalmente seguido por saída de exemplo e uma descrição.</span><span class="sxs-lookup"><span data-stu-id="75758-181">A sample command that uses the function or script, optionally followed by sample output and a description.</span></span> <span data-ttu-id="75758-182">Repita essa palavra-chave para cada exemplo.</span><span class="sxs-lookup"><span data-stu-id="75758-182">Repeat this keyword for each example.</span></span>

### <a name="inputs"></a><span data-ttu-id="75758-183">. INFORMAÇÕES</span><span class="sxs-lookup"><span data-stu-id="75758-183">.INPUTS</span></span>

<span data-ttu-id="75758-184">Os tipos .NET de objetos que podem ser canalizados para a função ou o script.</span><span class="sxs-lookup"><span data-stu-id="75758-184">The .NET types of objects that can be piped to the function or script.</span></span> <span data-ttu-id="75758-185">Você também pode incluir uma descrição dos objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="75758-185">You can also include a description of the input objects.</span></span>

### <a name="outputs"></a><span data-ttu-id="75758-186">. PRODUZ</span><span class="sxs-lookup"><span data-stu-id="75758-186">.OUTPUTS</span></span>

<span data-ttu-id="75758-187">O tipo .NET dos objetos que o cmdlet retorna.</span><span class="sxs-lookup"><span data-stu-id="75758-187">The .NET type of the objects that the cmdlet returns.</span></span> <span data-ttu-id="75758-188">Você também pode incluir uma descrição dos objetos retornados.</span><span class="sxs-lookup"><span data-stu-id="75758-188">You can also include a description of the returned objects.</span></span>

### <a name="notes"></a><span data-ttu-id="75758-189">. REGISTRA</span><span class="sxs-lookup"><span data-stu-id="75758-189">.NOTES</span></span>

<span data-ttu-id="75758-190">Informações adicionais sobre a função ou o script.</span><span class="sxs-lookup"><span data-stu-id="75758-190">Additional information about the function or script.</span></span>

### <a name="link"></a><span data-ttu-id="75758-191">. CRIAR</span><span class="sxs-lookup"><span data-stu-id="75758-191">.LINK</span></span>

<span data-ttu-id="75758-192">O nome de um tópico relacionado.</span><span class="sxs-lookup"><span data-stu-id="75758-192">The name of a related topic.</span></span> <span data-ttu-id="75758-193">O valor aparece na linha abaixo da ". LINK "palavra-chave e deve ser precedido por um símbolo de comentário `#` ou incluído no bloco de comentários.</span><span class="sxs-lookup"><span data-stu-id="75758-193">The value appears on the line below the ".LINK" keyword and must be preceded by a comment symbol `#` or included in the comment block.</span></span>

<span data-ttu-id="75758-194">Repita a `.LINK` palavra-chave para cada tópico relacionado.</span><span class="sxs-lookup"><span data-stu-id="75758-194">Repeat the `.LINK` keyword for each related topic.</span></span>

<span data-ttu-id="75758-195">Esse conteúdo aparece na seção links relacionados do tópico da ajuda.</span><span class="sxs-lookup"><span data-stu-id="75758-195">This content appears in the Related Links section of the help topic.</span></span>

<span data-ttu-id="75758-196">O `.Link` conteúdo da palavra-chave também pode incluir um URI (Uniform Resource Identifier) em uma versão online do mesmo tópico da ajuda.</span><span class="sxs-lookup"><span data-stu-id="75758-196">The `.Link` keyword content can also include a Uniform Resource Identifier (URI) to an online version of the same help topic.</span></span> <span data-ttu-id="75758-197">A versão online é aberta quando você usa o parâmetro **online** do `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="75758-197">The online version opens when you use the **Online** parameter of `Get-Help`.</span></span> <span data-ttu-id="75758-198">O URI deve começar com "http" ou "https".</span><span class="sxs-lookup"><span data-stu-id="75758-198">The URI must begin with "http" or "https".</span></span>

### <a name="component"></a><span data-ttu-id="75758-199">. COMPONENTE</span><span class="sxs-lookup"><span data-stu-id="75758-199">.COMPONENT</span></span>

<span data-ttu-id="75758-200">O nome da tecnologia ou do recurso que a função ou o script usa, ou ao qual ele está relacionado.</span><span class="sxs-lookup"><span data-stu-id="75758-200">The name of the technology or feature that the function or script uses, or to which it is related.</span></span> <span data-ttu-id="75758-201">O parâmetro de **componente** do `Get-Help` usa esse valor para filtrar os resultados da pesquisa retornados por `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="75758-201">The **Component** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

### <a name="role"></a><span data-ttu-id="75758-202">. CARGO</span><span class="sxs-lookup"><span data-stu-id="75758-202">.ROLE</span></span>

<span data-ttu-id="75758-203">O nome da função de usuário para o tópico da ajuda.</span><span class="sxs-lookup"><span data-stu-id="75758-203">The name of the user role for the help topic.</span></span> <span data-ttu-id="75758-204">O parâmetro de **função** de `Get-Help` usa esse valor para filtrar os resultados de pesquisa retornados por `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="75758-204">The **Role** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

### <a name="functionality"></a><span data-ttu-id="75758-205">. FUNÇÃO</span><span class="sxs-lookup"><span data-stu-id="75758-205">.FUNCTIONALITY</span></span>

<span data-ttu-id="75758-206">As palavras-chave que descrevem o uso pretendido da função.</span><span class="sxs-lookup"><span data-stu-id="75758-206">The keywords that describe the intended use of the function.</span></span> <span data-ttu-id="75758-207">O parâmetro de **funcionalidade** do `Get-Help` usa esse valor para filtrar os resultados da pesquisa retornados por `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="75758-207">The **Functionality** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

### <a name="forwardhelptargetname"></a><span data-ttu-id="75758-208">. FORWARDHELPTARGETNAME</span><span class="sxs-lookup"><span data-stu-id="75758-208">.FORWARDHELPTARGETNAME</span></span>

<span data-ttu-id="75758-209">Redireciona para o tópico da ajuda para o comando especificado.</span><span class="sxs-lookup"><span data-stu-id="75758-209">Redirects to the help topic for the specified command.</span></span> <span data-ttu-id="75758-210">Você pode redirecionar os usuários para qualquer tópico da ajuda, incluindo tópicos de ajuda para uma função, script, cmdlet ou provedor.</span><span class="sxs-lookup"><span data-stu-id="75758-210">You can redirect users to any help topic, including help topics for a function, script, cmdlet, or provider.</span></span>

```powershell
# .FORWARDHELPTARGETNAME <Command-Name>
```

### <a name="forwardhelpcategory"></a><span data-ttu-id="75758-211">. FORWARDHELPCATEGORY</span><span class="sxs-lookup"><span data-stu-id="75758-211">.FORWARDHELPCATEGORY</span></span>

<span data-ttu-id="75758-212">Especifica a categoria de ajuda do item no `.ForwardHelpTargetName` .</span><span class="sxs-lookup"><span data-stu-id="75758-212">Specifies the help category of the item in `.ForwardHelpTargetName`.</span></span> <span data-ttu-id="75758-213">Os valores válidos são,,,,,,, `Alias` `Cmdlet` `HelpFile` `Function` `Provider` `General` `FAQ` `Glossary` , `ScriptCommand` , `ExternalScript` , `Filter` ou `All` .</span><span class="sxs-lookup"><span data-stu-id="75758-213">Valid values are `Alias`, `Cmdlet`, `HelpFile`, `Function`, `Provider`, `General`, `FAQ`, `Glossary`, `ScriptCommand`, `ExternalScript`, `Filter`, or `All`.</span></span> <span data-ttu-id="75758-214">Use essa palavra-chave para evitar conflitos quando houver comandos com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="75758-214">Use this keyword to avoid conflicts when there are commands with the same name.</span></span>

```powershell
# .FORWARDHELPCATEGORY <Category>
```

### <a name="remotehelprunspace"></a><span data-ttu-id="75758-215">. REMOTEHELPRUNSPACE</span><span class="sxs-lookup"><span data-stu-id="75758-215">.REMOTEHELPRUNSPACE</span></span>

<span data-ttu-id="75758-216">Especifica uma sessão que contém o tópico da ajuda.</span><span class="sxs-lookup"><span data-stu-id="75758-216">Specifies a session that contains the help topic.</span></span> <span data-ttu-id="75758-217">Insira uma variável que contenha um objeto **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="75758-217">Enter a variable that contains a **PSSession** object.</span></span> <span data-ttu-id="75758-218">Essa palavra-chave é usada pelo cmdlet [Export-PSSession](xref:Microsoft.PowerShell.Utility.Export-PSSession) para localizar os tópicos da ajuda para os comandos exportados.</span><span class="sxs-lookup"><span data-stu-id="75758-218">This keyword is used by the [Export-PSSession](xref:Microsoft.PowerShell.Utility.Export-PSSession) cmdlet to find the help topics for the exported commands.</span></span>

```powershell
# .REMOTEHELPRUNSPACE <PSSession-variable>
```

### <a name="externalhelp"></a><span data-ttu-id="75758-219">. EXTERNALHELP</span><span class="sxs-lookup"><span data-stu-id="75758-219">.EXTERNALHELP</span></span>

<span data-ttu-id="75758-220">Especifica um arquivo de ajuda baseado em XML para o script ou função.</span><span class="sxs-lookup"><span data-stu-id="75758-220">Specifies an XML-based help file for the script or function.</span></span>

```powershell
# .EXTERNALHELP <XML Help File>
```

<span data-ttu-id="75758-221">A `.ExternalHelp` palavra-chave é necessária quando uma função ou script é documentado em arquivos XML.</span><span class="sxs-lookup"><span data-stu-id="75758-221">The `.ExternalHelp` keyword is required when a function or script is documented in XML files.</span></span> <span data-ttu-id="75758-222">Sem essa palavra-chave, `Get-Help` não é possível encontrar o arquivo de ajuda baseado em XML para a função ou o script.</span><span class="sxs-lookup"><span data-stu-id="75758-222">Without this keyword, `Get-Help` cannot find the XML-based help file for the function or script.</span></span>

<span data-ttu-id="75758-223">A `.ExternalHelp` palavra-chave tem precedência sobre outras palavras-chaves de ajuda baseadas em comentários.</span><span class="sxs-lookup"><span data-stu-id="75758-223">The `.ExternalHelp` keyword takes precedence over other comment-based help keywords.</span></span> <span data-ttu-id="75758-224">Se `.ExternalHelp` estiver presente, `Get-Help` o não exibirá a ajuda baseada em comentários, mesmo que ele não encontre um tópico de ajuda que corresponda ao valor da `.ExternalHelp` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="75758-224">If `.ExternalHelp` is present, `Get-Help` does not display comment-based help, even if it cannot find a help topic that matches the value of the `.ExternalHelp` keyword.</span></span>

<span data-ttu-id="75758-225">Se a função for exportada por um módulo, defina o valor da `.ExternalHelp` palavra-chave como um nome de arquivo sem um caminho.</span><span class="sxs-lookup"><span data-stu-id="75758-225">If the function is exported by a module, set the value of the `.ExternalHelp` keyword to a filename without a path.</span></span> <span data-ttu-id="75758-226">`Get-Help` procura o nome de arquivo especificado em um subdiretório específico do idioma do diretório do módulo.</span><span class="sxs-lookup"><span data-stu-id="75758-226">`Get-Help` looks for the specified file name in a language-specific subdirectory of the module directory.</span></span> <span data-ttu-id="75758-227">Não há requisitos para o nome do arquivo de ajuda baseado em XML para uma função, mas uma prática recomendada é usar o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="75758-227">There are no requirements for the name of the XML-based help file for a function, but a best practice is to use the following format:</span></span>

```
<ScriptModule.psm1>-help.xml
```

<span data-ttu-id="75758-228">Se a função não estiver incluída em um módulo, inclua um caminho para o arquivo de ajuda baseado em XML.</span><span class="sxs-lookup"><span data-stu-id="75758-228">If the function is not included in a module, include a path to the XML-based help file.</span></span> <span data-ttu-id="75758-229">Se o valor incluir um caminho e o caminho contiver subdiretórios específicos da cultura da interface do usuário, `Get-Help` o pesquisará os subdiretórios recursivamente para um arquivo XML com o nome do script ou função de acordo com os padrões de fallback de idioma estabelecidos para o Windows, assim como em um diretório de módulo.</span><span class="sxs-lookup"><span data-stu-id="75758-229">If the value includes a path and the path contains UI-culture-specific subdirectories, `Get-Help` searches the subdirectories recursively for an XML file with the name of the script or function in accordance with the language fallback standards established for Windows, just as it does in a module directory.</span></span>

<span data-ttu-id="75758-230">Para obter mais informações sobre o formato de arquivo de ajuda baseado em XML da ajuda do cmdlet, consulte [como gravar a ajuda do cmdlet](https://go.microsoft.com/fwlink/?LinkID=123415) na biblioteca do MSDN.</span><span class="sxs-lookup"><span data-stu-id="75758-230">For more information about the cmdlet help XML-based help file format, see [How to Write Cmdlet Help](https://go.microsoft.com/fwlink/?LinkID=123415) in the MSDN library.</span></span>

## <a name="autogenerated-content"></a><span data-ttu-id="75758-231">Conteúdo gerado automaticamente</span><span class="sxs-lookup"><span data-stu-id="75758-231">Autogenerated content</span></span>

<span data-ttu-id="75758-232">O nome, a sintaxe, a lista de parâmetros, a tabela de atributo de parâmetro, os parâmetros comuns e os comentários são gerados automaticamente pelo `Get-Help` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="75758-232">The name, syntax, parameter list, parameter attribute table, common parameters, and remarks are automatically generated by the `Get-Help` cmdlet.</span></span>

### <a name="name"></a><span data-ttu-id="75758-233">Name</span><span class="sxs-lookup"><span data-stu-id="75758-233">Name</span></span>

<span data-ttu-id="75758-234">A seção **nome** de um tópico da ajuda da função é extraída do nome da função na sintaxe da função.</span><span class="sxs-lookup"><span data-stu-id="75758-234">The **Name** section of a function help topic is taken from the function name in the function syntax.</span></span> <span data-ttu-id="75758-235">O **nome** de um tópico de ajuda de script é obtido do nome de arquivo do script.</span><span class="sxs-lookup"><span data-stu-id="75758-235">The **Name** of a script help topic is taken from the script filename.</span></span> <span data-ttu-id="75758-236">Para alterar o nome ou sua capitalização, altere a sintaxe da função ou o nome de arquivo do script.</span><span class="sxs-lookup"><span data-stu-id="75758-236">To change the name or its capitalization, change the function syntax or the script filename.</span></span>

### <a name="syntax"></a><span data-ttu-id="75758-237">Syntax</span><span class="sxs-lookup"><span data-stu-id="75758-237">Syntax</span></span>

<span data-ttu-id="75758-238">A seção de **sintaxe** do tópico da ajuda é gerada a partir da sintaxe da função ou do script.</span><span class="sxs-lookup"><span data-stu-id="75758-238">The **Syntax** section of the help topic is generated from the function or script syntax.</span></span> <span data-ttu-id="75758-239">Para adicionar detalhes à sintaxe do tópico da ajuda, como o tipo .NET de um parâmetro, adicione os detalhes à sintaxe.</span><span class="sxs-lookup"><span data-stu-id="75758-239">To add detail to the help topic syntax, such as the .NET type of a parameter, add the detail to the syntax.</span></span> <span data-ttu-id="75758-240">Se você não especificar um tipo de parâmetro, o tipo de **objeto** será inserido como o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="75758-240">If you do not specify a parameter type, the **Object** type is inserted as the default value.</span></span>

### <a name="parameter-list"></a><span data-ttu-id="75758-241">Lista de parâmetros</span><span class="sxs-lookup"><span data-stu-id="75758-241">Parameter List</span></span>

<span data-ttu-id="75758-242">A lista de parâmetros no tópico da ajuda é gerada a partir da sintaxe da função ou do script e das descrições que você adiciona usando a `.Parameter` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="75758-242">The parameter list in the help topic is generated from the function or script syntax and from the descriptions that you add by using the `.Parameter` keyword.</span></span> <span data-ttu-id="75758-243">Os parâmetros de função aparecem na seção de **parâmetros** do tópico da ajuda na mesma ordem em que aparecem na sintaxe da função ou do script.</span><span class="sxs-lookup"><span data-stu-id="75758-243">The function parameters appear in the **Parameters** section of the help topic in the same order that they appear in the function or script syntax.</span></span> <span data-ttu-id="75758-244">A grafia e a capitalização dos nomes de parâmetro também são extraídas da sintaxe.</span><span class="sxs-lookup"><span data-stu-id="75758-244">The spelling and capitalization of parameter names is also taken from the syntax.</span></span> <span data-ttu-id="75758-245">Ele não é afetado pelo nome do parâmetro especificado pela `.Parameter` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="75758-245">It is not affected by the parameter name specified by the `.Parameter` keyword.</span></span>

### <a name="common-parameters"></a><span data-ttu-id="75758-246">Parâmetros comuns</span><span class="sxs-lookup"><span data-stu-id="75758-246">Common Parameters</span></span>

<span data-ttu-id="75758-247">Os **parâmetros comuns** são adicionados à sintaxe e à lista de parâmetros do tópico da ajuda, mesmo que eles não tenham efeito.</span><span class="sxs-lookup"><span data-stu-id="75758-247">The **Common parameters** are added to the syntax and parameter list of the help topic, even if they have no effect.</span></span> <span data-ttu-id="75758-248">Para obter mais informações sobre os parâmetros comuns, consulte [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="75758-248">For more information about the common parameters, see [about_CommonParameters](about_CommonParameters.md).</span></span>

### <a name="parameter-attribute-table"></a><span data-ttu-id="75758-249">Tabela de atributos de parâmetro</span><span class="sxs-lookup"><span data-stu-id="75758-249">Parameter Attribute Table</span></span>

<span data-ttu-id="75758-250">`Get-Help` gera a tabela de atributos de parâmetro que aparece quando você usa o parâmetro **Full** **ou Parameter** de `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="75758-250">`Get-Help` generates the table of parameter attributes that appears when you use the **Full** or **Parameter** parameter of `Get-Help`.</span></span> <span data-ttu-id="75758-251">O valor dos atributos **obrigatório** , **posição** e valor **padrão** é obtido da sintaxe da função ou do script.</span><span class="sxs-lookup"><span data-stu-id="75758-251">The value of the **Required** , **Position** , and **Default** value attributes is taken from the function or script syntax.</span></span>

<span data-ttu-id="75758-252">Os valores padrão e um valor para **aceitar caracteres curinga** não aparecem na tabela de atributos de parâmetro mesmo quando eles são definidos na função ou script.</span><span class="sxs-lookup"><span data-stu-id="75758-252">Default values and a value for **Accept Wildcard characters** do not appear in the parameter attribute table even when they are defined in the function or script.</span></span> <span data-ttu-id="75758-253">Para ajudar os usuários, forneça essas informações na descrição do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="75758-253">To help users, provide this information in the parameter description.</span></span>

### <a name="remarks"></a><span data-ttu-id="75758-254">Comentários</span><span class="sxs-lookup"><span data-stu-id="75758-254">Remarks</span></span>

<span data-ttu-id="75758-255">A seção **comentários** do tópico da ajuda é gerada automaticamente a partir do nome da função ou do script.</span><span class="sxs-lookup"><span data-stu-id="75758-255">The **Remarks** section of the help topic is automatically generated from the function or script name.</span></span> <span data-ttu-id="75758-256">Você não pode alterar ou afetar seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="75758-256">You cannot change or affect its content.</span></span>

## <a name="examples"></a><span data-ttu-id="75758-257">Exemplos</span><span class="sxs-lookup"><span data-stu-id="75758-257">Examples</span></span>

### <a name="comment-based-help-for-a-function"></a><span data-ttu-id="75758-258">Ajuda baseada em comentários para uma função</span><span class="sxs-lookup"><span data-stu-id="75758-258">Comment-based Help for a Function</span></span>

<span data-ttu-id="75758-259">A seguinte função de exemplo inclui ajuda baseada em comentários:</span><span class="sxs-lookup"><span data-stu-id="75758-259">The following sample function includes comment-based help:</span></span>

```powershell
function Add-Extension
{
param ([string]$Name,[string]$Extension = "txt")
$name = $name + "." + $extension
$name

<#
.SYNOPSIS

Adds a file name extension to a supplied name.

.DESCRIPTION

Adds a file name extension to a supplied name.
Takes any strings for the file name or extension.

.PARAMETER Name
Specifies the file name.

.PARAMETER Extension
Specifies the extension. "Txt" is the default.

.INPUTS

None. You cannot pipe objects to Add-Extension.

.OUTPUTS

System.String. Add-Extension returns a string with the extension
or file name.

.EXAMPLE

PS> extension -name "File"
File.txt

.EXAMPLE

PS> extension -name "File" -extension "doc"
File.doc

.EXAMPLE

PS> extension "File" "doc"
File.doc

.LINK

http://www.fabrikam.com/extension.html

.LINK

Set-Item
#>
}
```

<span data-ttu-id="75758-260">Os resultados são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="75758-260">The results are as follows:</span></span>

```powershell
Get-Help -Name "Add-Extension" -Full
```

```Output
NAME

Add-Extension

SYNOPSIS

Adds a file name extension to a supplied name.

SYNTAX

Add-Extension [[-Name] <String>] [[-Extension] <String>]
[<CommonParameters>]

DESCRIPTION

Adds a file name extension to a supplied name. Takes any strings for the
file name or extension.

PARAMETERS

-Name
Specifies the file name.

Required?                    false
Position?                    0
Default value
Accept pipeline input?       false
Accept wildcard characters?

-Extension
Specifies the extension. "Txt" is the default.

Required?                    false
Position?                    1
Default value
Accept pipeline input?       false
Accept wildcard characters?

<CommonParameters>
This cmdlet supports the common parameters: -Verbose, -Debug,
-ErrorAction, -ErrorVariable, -WarningAction, -WarningVariable,
-OutBuffer and -OutVariable. For more information, type
"get-help about_commonparameters".

INPUTS
None. You cannot pipe objects to Add-Extension.

OUTPUTS

System.String. Add-Extension returns a string with the extension or
file name.

Example 1

PS> extension -name "File"
File.txt

Example 2

PS> extension -name "File" -extension "doc"
File.doc

Example 3

PS> extension "File" "doc"
File.doc

RELATED LINKS

http://www.fabrikam.com/extension.html
Set-Item
```

### <a name="parameter-descriptions-in-function-syntax"></a><span data-ttu-id="75758-261">Descrições de parâmetro na sintaxe de função</span><span class="sxs-lookup"><span data-stu-id="75758-261">Parameter Descriptions in Function Syntax</span></span>

<span data-ttu-id="75758-262">Este exemplo é o mesmo que o anterior, exceto que as descrições de parâmetro são inseridas na sintaxe da função.</span><span class="sxs-lookup"><span data-stu-id="75758-262">This example is the same as the previous one, except that the parameter descriptions are inserted in the function syntax.</span></span> <span data-ttu-id="75758-263">Esse formato é mais útil quando as descrições são breves.</span><span class="sxs-lookup"><span data-stu-id="75758-263">This format is most useful when the descriptions are brief.</span></span>

```powershell
function Add-Extension
{
param
(

[string]
#Specifies the file name.
$name,

[string]
#Specifies the file name extension. "Txt" is the default.
$extension = "txt"
)

$name = $name + "." + $extension
$name

<#
.SYNOPSIS

Adds a file name extension to a supplied name.

.DESCRIPTION

Adds a file name extension to a supplied name. Takes any strings for the
file name or extension.

.INPUTS

None. You cannot pipe objects to Add-Extension.

.OUTPUTS

System.String. Add-Extension returns a string with the extension or
file name.

.EXAMPLE

PS> extension -name "File"
File.txt

.EXAMPLE

PS> extension -name "File" -extension "doc"
File.doc

.EXAMPLE

PS> extension "File" "doc"
File.doc

.LINK

http://www.fabrikam.com/extension.html

.LINK

Set-Item
#>
}
```

### <a name="comment-based-help-for-a-script"></a><span data-ttu-id="75758-264">Ajuda baseada em comentários para um script</span><span class="sxs-lookup"><span data-stu-id="75758-264">Comment-based Help for a Script</span></span>

<span data-ttu-id="75758-265">O script de exemplo a seguir inclui ajuda baseada em comentários.</span><span class="sxs-lookup"><span data-stu-id="75758-265">The following sample script includes comment-based help.</span></span> <span data-ttu-id="75758-266">Observe as linhas em branco entre o fechamento `#>` e a `Param` instrução.</span><span class="sxs-lookup"><span data-stu-id="75758-266">Notice the blank lines between the closing `#>` and the `Param` statement.</span></span> <span data-ttu-id="75758-267">Em um script que não tem uma `Param` instrução, deve haver pelo menos duas linhas em branco entre o comentário final no tópico da ajuda e a primeira declaração da função.</span><span class="sxs-lookup"><span data-stu-id="75758-267">In a script that does not have a `Param` statement, there must be at least two blank lines between the final comment in the help topic and the first function declaration.</span></span> <span data-ttu-id="75758-268">Sem essas linhas em branco, `Get-Help` o associa o tópico da ajuda à função, não ao script.</span><span class="sxs-lookup"><span data-stu-id="75758-268">Without these blank lines, `Get-Help` associates the help topic with the function, not the script.</span></span>

```powershell
<#
.SYNOPSIS

Performs monthly data updates.

.DESCRIPTION

The Update-Month.ps1 script updates the registry with new data generated
during the past month and generates a report.

.PARAMETER InputPath
Specifies the path to the CSV-based input file.

.PARAMETER OutputPath
Specifies the name and path for the CSV-based output file. By default,
MonthlyUpdates.ps1 generates a name from the date and time it runs, and
saves the output in the local directory.

.INPUTS

None. You cannot pipe objects to Update-Month.ps1.

.OUTPUTS

None. Update-Month.ps1 does not generate any output.

.EXAMPLE

PS> .\Update-Month.ps1

.EXAMPLE

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv

.EXAMPLE

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv -outputPath `
C:\Reports\2009\January.csv
#>

param ([string]$InputPath, [string]$OutPutPath)

function Get-Data { }
...
```

<span data-ttu-id="75758-269">O comando a seguir obtém a ajuda do script.</span><span class="sxs-lookup"><span data-stu-id="75758-269">The following command gets the script help.</span></span> <span data-ttu-id="75758-270">Como o script não está em um diretório listado na `$env:Path` variável de ambiente, o `Get-Help` comando que obtém a ajuda do script deve especificar o caminho do script.</span><span class="sxs-lookup"><span data-stu-id="75758-270">Because the script is not in a directory that is listed in the `$env:Path` environment variable, the `Get-Help` command that gets the script help must specify the script path.</span></span>

```powershell
Get-Help -Path .\update-month.ps1 -Full
```

```Output
# NAME

C:\ps-test\Update-Month.ps1

# SYNOPSIS

Performs monthly data updates.

# SYNTAX

C:\ps-test\Update-Month.ps1 [-InputPath] <String> [[-OutputPath]
<String>] [<CommonParameters>]

# DESCRIPTION

The Update-Month.ps1 script updates the registry with new data
generated during the past month and generates a report.

# PARAMETERS

-InputPath
Specifies the path to the CSV-based input file.

Required?                    true
Position?                    0
Default value
Accept pipeline input?       false
Accept wildcard characters?

-OutputPath
Specifies the name and path for the CSV-based output file. By
default, MonthlyUpdates.ps1 generates a name from the date
and time it runs, and saves the output in the local directory.

Required?                    false
Position?                    1
Default value
Accept pipeline input?       false
Accept wildcard characters?

<CommonParameters>
This cmdlet supports the common parameters: -Verbose, -Debug,
-ErrorAction, -ErrorVariable, -WarningAction, -WarningVariable,
-OutBuffer and -OutVariable. For more information, type,
"get-help about_commonparameters".

# INPUTS

None. You cannot pipe objects to Update-Month.ps1.

# OUTPUTS

None. Update-Month.ps1 does not generate any output.

Example 1

PS> .\Update-Month.ps1

Example 2

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv

Example 3

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv -outputPath
C:\Reports\2009\January.csv

# RELATED LINKS
```

### <a name="redirecting-to-an-xml-file"></a><span data-ttu-id="75758-271">Redirecionando para um arquivo XML</span><span class="sxs-lookup"><span data-stu-id="75758-271">Redirecting to an XML File</span></span>

<span data-ttu-id="75758-272">Você pode escrever tópicos de ajuda baseados em XML para funções e scripts.</span><span class="sxs-lookup"><span data-stu-id="75758-272">You can write XML-based help topics for functions and scripts.</span></span> <span data-ttu-id="75758-273">Embora a ajuda baseada em comentários seja mais fácil de implementar, a ajuda baseada em XML é necessária para a ajuda atualizável e para fornecer tópicos de ajuda em vários idiomas.</span><span class="sxs-lookup"><span data-stu-id="75758-273">Although comment-based help is easier to implement, XML-based help is required for Updatable Help and to provide help topics in multiple languages.</span></span>

<span data-ttu-id="75758-274">O exemplo a seguir mostra as primeiras linhas do script de Update-Month.ps1.</span><span class="sxs-lookup"><span data-stu-id="75758-274">The following example shows the first few lines of the Update-Month.ps1 script.</span></span>
<span data-ttu-id="75758-275">O script usa a `.ExternalHelp` palavra-chave para especificar o caminho para um tópico de ajuda baseado em XML para o script.</span><span class="sxs-lookup"><span data-stu-id="75758-275">The script uses the `.ExternalHelp` keyword to specify the path to an XML-based help topic for the script.</span></span>

<span data-ttu-id="75758-276">Observe que o valor da `.ExternalHelp` palavra-chave é exibido na mesma linha que a palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="75758-276">Note that the value of the `.ExternalHelp` keyword appears on the same line as the keyword.</span></span> <span data-ttu-id="75758-277">Qualquer outro posicionamento é ineficaz.</span><span class="sxs-lookup"><span data-stu-id="75758-277">Any other placement is ineffective.</span></span>

```powershell
# .ExternalHelp C:\MyScripts\Update-Month-Help.xml

param ([string]$InputPath, [string]$OutPutPath)
function Get-Data { }
...
```

<span data-ttu-id="75758-278">Os exemplos a seguir mostram três posicionamentos válidos da `.ExternalHelp` palavra-chave em uma função.</span><span class="sxs-lookup"><span data-stu-id="75758-278">The following examples show three valid placements of the `.ExternalHelp` keyword in a function.</span></span>

```powershell
function Add-Extension
{
# .ExternalHelp C:\ps-test\Add-Extension.xml

param ([string] $name, [string]$extension = "txt")
$name = $name + "." + $extension
$name
}
```

```powershell
function Add-Extension
{
param ([string] $name, [string]$extension = "txt")
$name = $name + "." + $extension
$name

# .ExternalHelp C:\ps-test\Add-Extension.xml
}
```

```powershell
# .ExternalHelp C:\ps-test\Add-Extension.xml
function Add-Extension
{
param ([string] $name, [string]$extension = "txt")
$name = $name + "." + $extension
$name
}
```

### <a name="redirecting-to-a-different-help-topic"></a><span data-ttu-id="75758-279">Redirecionando para um tópico de ajuda diferente</span><span class="sxs-lookup"><span data-stu-id="75758-279">Redirecting to a Different Help Topic</span></span>

<span data-ttu-id="75758-280">O código a seguir é um trecho do início da função de ajuda interna no PowerShell, que exibe uma tela de texto de ajuda de cada vez.</span><span class="sxs-lookup"><span data-stu-id="75758-280">The following code is an excerpt from the beginning of the built-in help function in PowerShell, which displays one screen of help text at a time.</span></span>
<span data-ttu-id="75758-281">Como o tópico da ajuda para o `Get-Help` cmdlet descreve a função de ajuda, a função de ajuda usa as `.ForwardHelpTargetName` `.ForwardHelpCategory` palavras-chave e para redirecionar o usuário para o `Get-Help` tópico de ajuda do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="75758-281">Because the help topic for the `Get-Help` cmdlet describes the help function, the help function uses the `.ForwardHelpTargetName` and `.ForwardHelpCategory` keywords to redirect the user to the `Get-Help` cmdlet help topic.</span></span>

```powershell
function help
{

<#
.FORWARDHELPTARGETNAME Get-Help
.FORWARDHELPCATEGORY Cmdlet
#>
[CmdletBinding(DefaultParameterSetName='AllUsersView')]
param(
[Parameter(Position=0, ValueFromPipelineByPropertyName=$true)]
[System.String]
${Name},
...
```

<span data-ttu-id="75758-282">O comando a seguir usa esse recurso:</span><span class="sxs-lookup"><span data-stu-id="75758-282">The following command uses this feature:</span></span>

```powershell
Get-Help -Name help
```

```Output
NAME

Get-Help

SYNOPSIS

Displays information about PowerShell cmdlets and concepts.
...
```

## <a name="see-also"></a><span data-ttu-id="75758-283">Confira também</span><span class="sxs-lookup"><span data-stu-id="75758-283">See also</span></span>

[<span data-ttu-id="75758-284">about_Functions</span><span class="sxs-lookup"><span data-stu-id="75758-284">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="75758-285">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="75758-285">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="75758-286">about_Scripts</span><span class="sxs-lookup"><span data-stu-id="75758-286">about_Scripts</span></span>](about_Scripts.md)

[<span data-ttu-id="75758-287">Como escrever ajuda de cmdlet</span><span class="sxs-lookup"><span data-stu-id="75758-287">How to Write Cmdlet Help</span></span>](https://go.microsoft.com/fwlink/?LinkID=123415)
