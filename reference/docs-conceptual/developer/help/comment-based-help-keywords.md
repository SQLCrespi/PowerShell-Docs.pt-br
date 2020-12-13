---
ms.date: 06/09/2020
ms.topic: reference
title: Palavras-chave de ajuda baseada em comentários
description: Palavras-chave de ajuda baseada em comentários
ms.openlocfilehash: d87dde8700813767f6c09cfce70ed06c7964ebc7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645479"
---
# <a name="comment-based-help-keywords"></a><span data-ttu-id="cb760-103">Palavras-chave de ajuda baseada em comentários</span><span class="sxs-lookup"><span data-stu-id="cb760-103">Comment-Based Help Keywords</span></span>

<span data-ttu-id="cb760-104">Este tópico lista e descreve as palavras-chave na Ajuda baseada em comentários.</span><span class="sxs-lookup"><span data-stu-id="cb760-104">This topic lists and describes the keywords in comment-based help.</span></span>

## <a name="keywords-in-comment-based-help"></a><span data-ttu-id="cb760-105">Palavras-chave na ajuda Comment-Based</span><span class="sxs-lookup"><span data-stu-id="cb760-105">Keywords in Comment-Based Help</span></span>

<span data-ttu-id="cb760-106">Veja a seguir as palavras-chave de ajuda com base em comentários válidas.</span><span class="sxs-lookup"><span data-stu-id="cb760-106">The following are valid comment-based Help keywords.</span></span> <span data-ttu-id="cb760-107">Eles são listados na ordem em que normalmente aparecem em um tópico da ajuda junto com o uso pretendido.</span><span class="sxs-lookup"><span data-stu-id="cb760-107">They are listed in the order in which they typically appear in a Help topic along with their intended use.</span></span> <span data-ttu-id="cb760-108">Essas palavras-chave podem aparecer em qualquer ordem na Ajuda baseada em comentários e não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="cb760-108">These keywords can appear in any order in the comment-based Help, and they are not case-sensitive.</span></span>

<span data-ttu-id="cb760-109">Observe que a `.EXTERNALHELP` palavra-chave tem precedência sobre todas as outras palavras-chaves de ajuda baseadas em comentários.</span><span class="sxs-lookup"><span data-stu-id="cb760-109">Note that the `.EXTERNALHELP` keyword takes precedence over all other comment-based help keywords.</span></span>
<span data-ttu-id="cb760-110">Quando `.EXTERNALHELP` o estiver presente, o cmdlet [Microsoft. PowerShell. Commands. GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) não exibirá ajuda baseada em comentários, mesmo quando ele não encontrar um arquivo de ajuda que corresponda ao valor da palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="cb760-110">When `.EXTERNALHELP` is present, the [Microsoft.PowerShell.Commands.GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet does not display comment-based help, even when it cannot find a help file that matches the value of the keyword.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cb760-111">. Resumo</span><span class="sxs-lookup"><span data-stu-id="cb760-111">.SYNOPSIS</span></span>

<span data-ttu-id="cb760-112">Uma breve descrição da função ou do script.</span><span class="sxs-lookup"><span data-stu-id="cb760-112">A brief description of the function or script.</span></span> <span data-ttu-id="cb760-113">Essa palavra-chave pode ser usada apenas uma vez em cada tópico.</span><span class="sxs-lookup"><span data-stu-id="cb760-113">This keyword can be used only once in each topic.</span></span>

## <a name="description"></a><span data-ttu-id="cb760-114">. NDESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="cb760-114">.DESCRIPTION</span></span>

<span data-ttu-id="cb760-115">Uma descrição detalhada da função ou do script.</span><span class="sxs-lookup"><span data-stu-id="cb760-115">A detailed description of the function or script.</span></span> <span data-ttu-id="cb760-116">Essa palavra-chave pode ser usada apenas uma vez em cada tópico.</span><span class="sxs-lookup"><span data-stu-id="cb760-116">This keyword can be used only once in each topic.</span></span>

## <a name="parameter-parameter-name"></a><span data-ttu-id="cb760-117">. METER \<Parameter-Name></span><span class="sxs-lookup"><span data-stu-id="cb760-117">.PARAMETER \<Parameter-Name></span></span>

<span data-ttu-id="cb760-118">A descrição de um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="cb760-118">The description of a parameter.</span></span> <span data-ttu-id="cb760-119">Você pode incluir uma `.PARAMETER` palavra-chave para cada parâmetro na função ou script.</span><span class="sxs-lookup"><span data-stu-id="cb760-119">You can include a `.PARAMETER` keyword for each parameter in the function or script.</span></span>

<span data-ttu-id="cb760-120">As `.PARAMETER` palavras-chave podem aparecer em qualquer ordem no bloco de comentários, mas a ordem na qual os parâmetros aparecem na `Param` instrução ou declaração de função determina a ordem na qual os parâmetros aparecem no tópico da ajuda.</span><span class="sxs-lookup"><span data-stu-id="cb760-120">The `.PARAMETER` keywords can appear in any order in the comment block, but the order in which the parameters appear in the `Param` statement or function declaration determines the order in which the parameters appear in Help topic.</span></span> <span data-ttu-id="cb760-121">Para alterar a ordem dos parâmetros no tópico da ajuda, altere a ordem dos parâmetros na `Param` instrução ou na declaração da função.</span><span class="sxs-lookup"><span data-stu-id="cb760-121">To change the order of parameters in the Help topic, change the order of the parameters in the `Param` statement or function declaration.</span></span>

<span data-ttu-id="cb760-122">Você também pode especificar uma descrição de parâmetro colocando um comentário na `Param` instrução imediatamente antes do nome da variável de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="cb760-122">You can also specify a parameter description by placing a comment in the `Param` statement immediately before the parameter variable name.</span></span> <span data-ttu-id="cb760-123">Se você usar um `Param` Comentário de instrução e uma `.PARAMETER` palavra-chave, a descrição associada à `.PARAMETER` palavra-chave será usada e o `Param` Comentário da instrução será ignorado.</span><span class="sxs-lookup"><span data-stu-id="cb760-123">If you use both a `Param` statement comment and a `.PARAMETER` keyword, the description associated with the `.PARAMETER` keyword is used, and the `Param` statement comment is ignored.</span></span>

## <a name="example"></a><span data-ttu-id="cb760-124">. EXEMPLO</span><span class="sxs-lookup"><span data-stu-id="cb760-124">.EXAMPLE</span></span>

<span data-ttu-id="cb760-125">Um comando de exemplo que usa a função ou o script, opcionalmente seguido por saída de exemplo e uma descrição.</span><span class="sxs-lookup"><span data-stu-id="cb760-125">A sample command that uses the function or script, optionally followed by sample output and a description.</span></span> <span data-ttu-id="cb760-126">Repita essa palavra-chave para cada exemplo.</span><span class="sxs-lookup"><span data-stu-id="cb760-126">Repeat this keyword for each example.</span></span>

## <a name="inputs"></a><span data-ttu-id="cb760-127">. INFORMAÇÕES</span><span class="sxs-lookup"><span data-stu-id="cb760-127">.INPUTS</span></span>

<span data-ttu-id="cb760-128">Os tipos de Microsoft .NET Framework de objetos que podem ser canalizados para a função ou o script.</span><span class="sxs-lookup"><span data-stu-id="cb760-128">The Microsoft .NET Framework types of objects that can be piped to the function or script.</span></span> <span data-ttu-id="cb760-129">Você também pode incluir uma descrição dos objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="cb760-129">You can also include a description of the input objects.</span></span>

## <a name="outputs"></a><span data-ttu-id="cb760-130">. PRODUZ</span><span class="sxs-lookup"><span data-stu-id="cb760-130">.OUTPUTS</span></span>

<span data-ttu-id="cb760-131">O tipo de .NET Framework dos objetos que o cmdlet retorna.</span><span class="sxs-lookup"><span data-stu-id="cb760-131">The .NET Framework type of the objects that the cmdlet returns.</span></span> <span data-ttu-id="cb760-132">Você também pode incluir uma descrição dos objetos retornados.</span><span class="sxs-lookup"><span data-stu-id="cb760-132">You can also include a description of the returned objects.</span></span>

## <a name="notes"></a><span data-ttu-id="cb760-133">. REGISTRA</span><span class="sxs-lookup"><span data-stu-id="cb760-133">.NOTES</span></span>

<span data-ttu-id="cb760-134">Informações adicionais sobre a função ou o script.</span><span class="sxs-lookup"><span data-stu-id="cb760-134">Additional information about the function or script.</span></span>

## <a name="link"></a><span data-ttu-id="cb760-135">. CRIAR</span><span class="sxs-lookup"><span data-stu-id="cb760-135">.LINK</span></span>

<span data-ttu-id="cb760-136">O nome de um tópico relacionado.</span><span class="sxs-lookup"><span data-stu-id="cb760-136">The name of a related topic.</span></span> <span data-ttu-id="cb760-137">Repita essa palavra-chave para cada tópico relacionado.</span><span class="sxs-lookup"><span data-stu-id="cb760-137">Repeat this keyword for each related topic.</span></span> <span data-ttu-id="cb760-138">Esse conteúdo aparece na seção links relacionados do tópico da ajuda.</span><span class="sxs-lookup"><span data-stu-id="cb760-138">This content appears in the Related Links section of the Help topic.</span></span>

<span data-ttu-id="cb760-139">O `.LINK` conteúdo da palavra-chave também pode incluir um URI (Uniform Resource Identifier) em uma versão online do mesmo tópico da ajuda.</span><span class="sxs-lookup"><span data-stu-id="cb760-139">The `.LINK` keyword content can also include a Uniform Resource Identifier (URI) to an online version of the same Help topic.</span></span> <span data-ttu-id="cb760-140">A versão online é aberta quando você usa o `Online` parâmetro de `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="cb760-140">The online version opens when you use the `Online` parameter of `Get-Help`.</span></span> <span data-ttu-id="cb760-141">O URI deve começar com "http" ou "https".</span><span class="sxs-lookup"><span data-stu-id="cb760-141">The URI must begin with "http" or "https".</span></span>

## <a name="component"></a><span data-ttu-id="cb760-142">. COMPONENTE</span><span class="sxs-lookup"><span data-stu-id="cb760-142">.COMPONENT</span></span>

<span data-ttu-id="cb760-143">O nome da tecnologia ou do recurso que a função ou o script usa, ou ao qual ele está relacionado.</span><span class="sxs-lookup"><span data-stu-id="cb760-143">The name of the technology or feature that the function or script uses, or to which it is related.</span></span>
<span data-ttu-id="cb760-144">O parâmetro de **componente** do `Get-Help` usa esse valor para filtrar os resultados da pesquisa retornados por `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="cb760-144">The **Component** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

## <a name="role"></a><span data-ttu-id="cb760-145">. Cargo</span><span class="sxs-lookup"><span data-stu-id="cb760-145">.Role</span></span>

<span data-ttu-id="cb760-146">O nome da função de usuário para o tópico da ajuda.</span><span class="sxs-lookup"><span data-stu-id="cb760-146">The name of the user role for the help topic.</span></span> <span data-ttu-id="cb760-147">O parâmetro de **função** de `Get-Help` usa esse valor para filtrar os resultados de pesquisa retornados por `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="cb760-147">The **Role** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

## <a name="functionality"></a><span data-ttu-id="cb760-148">. FUNÇÃO</span><span class="sxs-lookup"><span data-stu-id="cb760-148">.FUNCTIONALITY</span></span>

<span data-ttu-id="cb760-149">As palavras-chave que descrevem o uso pretendido da função.</span><span class="sxs-lookup"><span data-stu-id="cb760-149">The keywords that describe the intended use of the function.</span></span> <span data-ttu-id="cb760-150">O parâmetro de **funcionalidade** do `Get-Help` usa esse valor para filtrar os resultados da pesquisa retornados por `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="cb760-150">The **Functionality** parameter of `Get-Help` uses this value to filter the search results returned by `Get-Help`.</span></span>

## <a name="forwardhelptargetname-command-name"></a><span data-ttu-id="cb760-151">. FORWARDHELPTARGETNAME \<Command-Name></span><span class="sxs-lookup"><span data-stu-id="cb760-151">.FORWARDHELPTARGETNAME \<Command-Name></span></span>

<span data-ttu-id="cb760-152">Redireciona para o tópico da ajuda para o comando especificado.</span><span class="sxs-lookup"><span data-stu-id="cb760-152">Redirects to the Help topic for the specified command.</span></span> <span data-ttu-id="cb760-153">Você pode redirecionar os usuários para qualquer tópico da ajuda, incluindo tópicos de ajuda para uma função, script, cmdlet ou provedor.</span><span class="sxs-lookup"><span data-stu-id="cb760-153">You can redirect users to any Help topic, including Help topics for a function, script, cmdlet, or provider.</span></span>

## <a name="forwardhelpcategory-category"></a><span data-ttu-id="cb760-154">. FORWARDHELPCATEGORY \<Category></span><span class="sxs-lookup"><span data-stu-id="cb760-154">.FORWARDHELPCATEGORY \<Category></span></span>

<span data-ttu-id="cb760-155">Especifica a categoria de ajuda do item no `.FORWARDHELPTARGETNAME` .</span><span class="sxs-lookup"><span data-stu-id="cb760-155">Specifies the Help category of the item in `.FORWARDHELPTARGETNAME`.</span></span> <span data-ttu-id="cb760-156">Use essa palavra-chave para evitar conflitos quando houver comandos com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="cb760-156">Use this keyword to avoid conflicts when there are commands with the same name.</span></span>

<span data-ttu-id="cb760-157">Os valores válidos são:</span><span class="sxs-lookup"><span data-stu-id="cb760-157">Valid values are:</span></span>

- <span data-ttu-id="cb760-158">Alias</span><span class="sxs-lookup"><span data-stu-id="cb760-158">Alias</span></span>
- <span data-ttu-id="cb760-159">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="cb760-159">Cmdlet</span></span>
- <span data-ttu-id="cb760-160">HelpFile</span><span class="sxs-lookup"><span data-stu-id="cb760-160">HelpFile</span></span>
- <span data-ttu-id="cb760-161">Função</span><span class="sxs-lookup"><span data-stu-id="cb760-161">Function</span></span>
- <span data-ttu-id="cb760-162">Provedor</span><span class="sxs-lookup"><span data-stu-id="cb760-162">Provider</span></span>
- <span data-ttu-id="cb760-163">Geral</span><span class="sxs-lookup"><span data-stu-id="cb760-163">General</span></span>
- <span data-ttu-id="cb760-164">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="cb760-164">FAQ</span></span>
- <span data-ttu-id="cb760-165">Glossário</span><span class="sxs-lookup"><span data-stu-id="cb760-165">Glossary</span></span>
- <span data-ttu-id="cb760-166">ScriptCommand</span><span class="sxs-lookup"><span data-stu-id="cb760-166">ScriptCommand</span></span>
- <span data-ttu-id="cb760-167">ExternalScript</span><span class="sxs-lookup"><span data-stu-id="cb760-167">ExternalScript</span></span>
- <span data-ttu-id="cb760-168">Filtrar</span><span class="sxs-lookup"><span data-stu-id="cb760-168">Filter</span></span>
- <span data-ttu-id="cb760-169">Tudo</span><span class="sxs-lookup"><span data-stu-id="cb760-169">All</span></span>

## <a name="remotehelprunspace-pssession-variable"></a><span data-ttu-id="cb760-170">. REMOTEHELPRUNSPACE \<PSSession-variable></span><span class="sxs-lookup"><span data-stu-id="cb760-170">.REMOTEHELPRUNSPACE \<PSSession-variable></span></span>

<span data-ttu-id="cb760-171">Especifica uma sessão que contém o tópico da ajuda.</span><span class="sxs-lookup"><span data-stu-id="cb760-171">Specifies a session that contains the Help topic.</span></span> <span data-ttu-id="cb760-172">Insira uma variável que contenha uma PSSession.</span><span class="sxs-lookup"><span data-stu-id="cb760-172">Enter a variable that contains a PSSession.</span></span> <span data-ttu-id="cb760-173">Essa palavra-chave é usada pelo `Export-PSSession` cmdlet para localizar os tópicos da ajuda para os comandos exportados.</span><span class="sxs-lookup"><span data-stu-id="cb760-173">This keyword is used by the `Export-PSSession` cmdlet to find the Help topics for the exported commands.</span></span>

## <a name="externalhelp-xml-help-file"></a><span data-ttu-id="cb760-174">. EXTERNALHELP \<XML Help File></span><span class="sxs-lookup"><span data-stu-id="cb760-174">.EXTERNALHELP \<XML Help File></span></span>

<span data-ttu-id="cb760-175">Especifica o caminho e/ou o nome de um arquivo de ajuda baseado em XML para o script ou função.</span><span class="sxs-lookup"><span data-stu-id="cb760-175">Specifies the path and/or name of an XML-based Help file for the script or function.</span></span>

<span data-ttu-id="cb760-176">A `.EXTERNALHELP` palavra-chave informa ao cmdlet [Microsoft. PowerShell. Commands. GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) para obter ajuda para o script ou a função em um arquivo baseado em XML.</span><span class="sxs-lookup"><span data-stu-id="cb760-176">The `.EXTERNALHELP` keyword tells the [Microsoft.PowerShell.Commands.GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet to get help for the script or function in an XML-based file.</span></span> <span data-ttu-id="cb760-177">A `.EXTERNALHELP` palavra-chave é necessária ao usar um arquivo de ajuda baseado em XML para um script ou uma função.</span><span class="sxs-lookup"><span data-stu-id="cb760-177">The `.EXTERNALHELP` keyword is required when using an XML-based help file for a script or function.</span></span> <span data-ttu-id="cb760-178">Sem ele, `Get-Help` o não encontrará um arquivo de ajuda para a função ou o script.</span><span class="sxs-lookup"><span data-stu-id="cb760-178">Without it, `Get-Help` will not find a help file for the function or script.</span></span>

<span data-ttu-id="cb760-179">A `.EXTERNALHELP` palavra-chave tem precedência sobre todas as outras palavras-chaves de ajuda baseadas em comentários.</span><span class="sxs-lookup"><span data-stu-id="cb760-179">The `.EXTERNALHELP` keyword takes precedence over all other comment-based help keywords.</span></span> <span data-ttu-id="cb760-180">Quando `.EXTERNALHELP` o estiver presente, o cmdlet [Microsoft. PowerShell. Commands. GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) não exibirá ajuda baseada em comentários, mesmo quando ele não encontrar um arquivo de ajuda que corresponda ao valor da palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="cb760-180">When `.EXTERNALHELP` is present, the [Microsoft.PowerShell.Commands.GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) cmdlet does not display comment-based help, even when it cannot find a help file that matches the value of the keyword.</span></span>

<span data-ttu-id="cb760-181">Quando a função é exportada por um módulo de script, o valor de `.EXTERNALHELP` deve ser um nome de arquivo sem um caminho.</span><span class="sxs-lookup"><span data-stu-id="cb760-181">When the function is exported by a script module, the value of `.EXTERNALHELP` should be a filename without a path.</span></span> <span data-ttu-id="cb760-182">`Get-Help` procura o arquivo em um subdiretório específico da localidade do diretório do módulo.</span><span class="sxs-lookup"><span data-stu-id="cb760-182">`Get-Help` looks for the file in a locale-specific subdirectory of the module directory.</span></span> <span data-ttu-id="cb760-183">Não há requisitos para o nome de arquivo, mas uma prática recomendada é usar o seguinte formato de nome de arquivo: `<ScriptModule>.psm1-help.xml` .</span><span class="sxs-lookup"><span data-stu-id="cb760-183">There are no requirements for the filename, but a best practice is to use the following filename format: `<ScriptModule>.psm1-help.xml`.</span></span>

<span data-ttu-id="cb760-184">Quando a função não estiver associada a um módulo, inclua um caminho e um nome de arquivo no valor da `.EXTERNALHELP` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="cb760-184">When the function is not associated with a module, include a path and filename in the value of the `.EXTERNALHELP` keyword.</span></span> <span data-ttu-id="cb760-185">Se o caminho especificado para o arquivo XML contiver subdiretórios específicos da cultura da interface do usuário, `Get-Help` o pesquisará os subdiretórios recursivamente para um arquivo XML com o nome do script ou da função de acordo com os padrões de fallback de idioma estabelecidos para o Windows, assim como faz para todos os tópicos de ajuda baseados em XML.</span><span class="sxs-lookup"><span data-stu-id="cb760-185">If the specified path to the XML file contains UI-culture-specific subdirectories, `Get-Help` searches the subdirectories recursively for an XML file with the name of the script or function in accordance with the language fallback standards established for Windows, just as it does for all XML-based Help topics.</span></span>

<span data-ttu-id="cb760-186">Para obter mais informações sobre o formato de arquivo de ajuda baseado em XML da ajuda do cmdlet, consulte [a ajuda do cmdlet Writing Windows PowerShell](./writing-help-for-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="cb760-186">For more information about the cmdlet Help XML-based Help file format, see [Writing Windows PowerShell Cmdlet Help](./writing-help-for-windows-powershell-cmdlets.md).</span></span>
