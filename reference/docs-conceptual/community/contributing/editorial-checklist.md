---
title: Lista de verificação editorial
description: Esta é uma lista resumida de regras para editar a documentação do PowerShell.
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: b5baf7366239084779d34e23f218e5e6222ed1a3
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81624730"
---
# <a name="editors-checklist"></a><span data-ttu-id="073b4-103">Lista de verificação do editor</span><span class="sxs-lookup"><span data-stu-id="073b4-103">Editor's checklist</span></span>

<span data-ttu-id="073b4-104">Este é um resumo das regras a serem aplicadas ao escrever novos artigos ou atualizar existentes.</span><span class="sxs-lookup"><span data-stu-id="073b4-104">This is a summary of rules to apply when writing new or updating existing articles.</span></span> <span data-ttu-id="073b4-105">Confira outros artigos no Guia do colaborador para obter explicações detalhadas e exemplos dessas regras.</span><span class="sxs-lookup"><span data-stu-id="073b4-105">See other articles in the Contributor's Guide for detailed explanations and examples of these rules.</span></span>

## <a name="metadata"></a><span data-ttu-id="073b4-106">Metadados</span><span class="sxs-lookup"><span data-stu-id="073b4-106">Metadata</span></span>

- <span data-ttu-id="073b4-107">`ms.date`: deve estar no formato **MM/DD/AAAA**</span><span class="sxs-lookup"><span data-stu-id="073b4-107">`ms.date`: must be in the format **MM/DD/YYYY**</span></span>
  - <span data-ttu-id="073b4-108">Alterar a data em que houver uma atualização significativa ou real</span><span class="sxs-lookup"><span data-stu-id="073b4-108">Change the date when there is a significant or factual update</span></span>
    - <span data-ttu-id="073b4-109">Reorganizar o artigo</span><span class="sxs-lookup"><span data-stu-id="073b4-109">Reorganizing the article</span></span>
    - <span data-ttu-id="073b4-110">Corrigir erros reais</span><span class="sxs-lookup"><span data-stu-id="073b4-110">Fixing factual errors</span></span>
    - <span data-ttu-id="073b4-111">Adicionar novas informações</span><span class="sxs-lookup"><span data-stu-id="073b4-111">Adding new information</span></span>
  - <span data-ttu-id="073b4-112">Não altere a data se a atualização não for significativa</span><span class="sxs-lookup"><span data-stu-id="073b4-112">Do not change the date if the update is insignificant</span></span>
    - <span data-ttu-id="073b4-113">Corrigir erros de digitação e formatação</span><span class="sxs-lookup"><span data-stu-id="073b4-113">Fixing typos and formatting</span></span>
- <span data-ttu-id="073b4-114">`title`: sequência única de 43 a 59 caracteres, incluindo espaços</span><span class="sxs-lookup"><span data-stu-id="073b4-114">`title`: unique string of 43-59 chars including spaces</span></span>
  - <span data-ttu-id="073b4-115">Não inclua o identificador do site (ele é gerado automaticamente)</span><span class="sxs-lookup"><span data-stu-id="073b4-115">Do not include site identifier (it is auto-generated)</span></span>
  - <span data-ttu-id="073b4-116">Use maiúsculas e minúsculas - coloque em maiúscula apenas a primeira palavra e quaisquer nomes próprios</span><span class="sxs-lookup"><span data-stu-id="073b4-116">Use sentence case - capitalize only the first word and any proper nouns</span></span>
- <span data-ttu-id="073b4-117">`description`: 115-145 caracteres incluindo espaços - esse resumo é exibido no resultado da pesquisa</span><span class="sxs-lookup"><span data-stu-id="073b4-117">`description`: 115-145 characters including spaces - this abstract displays in the search result</span></span>

## <a name="formatting"></a><span data-ttu-id="073b4-118">Formatação</span><span class="sxs-lookup"><span data-stu-id="073b4-118">Formatting</span></span>

- <span data-ttu-id="073b4-119">Elementos de sintaxe de backtick que aparecem, embutidos, dentro de um parágrafo</span><span class="sxs-lookup"><span data-stu-id="073b4-119">Backtick syntax elements that appear, inline, within a paragraph</span></span>
  - <span data-ttu-id="073b4-120">Nomes dos cmdlets `Verb-Noun`</span><span class="sxs-lookup"><span data-stu-id="073b4-120">Cmdlet names `Verb-Noun`</span></span>
  - <span data-ttu-id="073b4-121">Variável `$counter`</span><span class="sxs-lookup"><span data-stu-id="073b4-121">Variable `$counter`</span></span>
  - <span data-ttu-id="073b4-122">Exemplos sintáticos `Verb-Noun -Parameter`</span><span class="sxs-lookup"><span data-stu-id="073b4-122">Syntactic examples `Verb-Noun -Parameter`</span></span>
  - <span data-ttu-id="073b4-123">Caminhos de arquivo `C:\Program Files\PowerShell`, `/usr/bin/pwsh`</span><span class="sxs-lookup"><span data-stu-id="073b4-123">File paths `C:\Program Files\PowerShell`, `/usr/bin/pwsh`</span></span>
  - <span data-ttu-id="073b4-124">URLs que não devem ser clicáveis no documento</span><span class="sxs-lookup"><span data-stu-id="073b4-124">URLs that are not meant to be clickable in the document</span></span>
  - <span data-ttu-id="073b4-125">Valores de propriedade ou parâmetro</span><span class="sxs-lookup"><span data-stu-id="073b4-125">Property or parameter values</span></span>
- <span data-ttu-id="073b4-126">Use negrito para nomes de: propriedade, parâmetros, classes, módulos, entidades, objetos ou tipos</span><span class="sxs-lookup"><span data-stu-id="073b4-126">Use bold for property names, parameter names, class names, module names, entity names, object or type names</span></span>
  - <span data-ttu-id="073b4-127">Negrito é usado para marcação semântica, não para ênfase</span><span class="sxs-lookup"><span data-stu-id="073b4-127">Bold is used for semantic markup, not emphasis</span></span>
  - <span data-ttu-id="073b4-128">Negrito - use asteriscos `**`</span><span class="sxs-lookup"><span data-stu-id="073b4-128">Bold - use asterisks `**`</span></span>
- <span data-ttu-id="073b4-129">Itálico - use sublinhado `_`</span><span class="sxs-lookup"><span data-stu-id="073b4-129">Italic - use underscore `_`</span></span>
  - <span data-ttu-id="073b4-130">Usado apenas para ênfase, não para marcação semântica</span><span class="sxs-lookup"><span data-stu-id="073b4-130">Only used for emphasis, not for semantic markup</span></span>
- <span data-ttu-id="073b4-131">Quebras de linha em 100 colunas (ou em 80 para **about_Topics**)</span><span class="sxs-lookup"><span data-stu-id="073b4-131">Line breaks at 100 columns (or at 80 for **about_Topics**)</span></span>
- <span data-ttu-id="073b4-132">Sem guias rígidas - use somente espaços</span><span class="sxs-lookup"><span data-stu-id="073b4-132">No hard tabs - use spaces only</span></span>
- <span data-ttu-id="073b4-133">Sem espaços à direita nas linhas</span><span class="sxs-lookup"><span data-stu-id="073b4-133">No trailing spaces on lines</span></span>

### <a name="headers"></a><span data-ttu-id="073b4-134">headers</span><span class="sxs-lookup"><span data-stu-id="073b4-134">Headers</span></span>

- <span data-ttu-id="073b4-135">H1 é o primeiro - apenas um H1 por artigo</span><span class="sxs-lookup"><span data-stu-id="073b4-135">H1 is first - only one H1 per article</span></span>
- <span data-ttu-id="073b4-136">Use apenas [Cabeçalhos ATX](https://github.github.com/gfm/#atx-headings)</span><span class="sxs-lookup"><span data-stu-id="073b4-136">Use [ATX Headers](https://github.github.com/gfm/#atx-headings) only</span></span>
- <span data-ttu-id="073b4-137">Use maiúsculas e minúsculas para todos os cabeçalhos</span><span class="sxs-lookup"><span data-stu-id="073b4-137">Use sentence case for all headers</span></span>
- <span data-ttu-id="073b4-138">Não pule os níveis - sem H3 sem H2</span><span class="sxs-lookup"><span data-stu-id="073b4-138">Do not skip levels - no H3 without an H2</span></span>
- <span data-ttu-id="073b4-139">Profundidade máxima do H3 ou H4</span><span class="sxs-lookup"><span data-stu-id="073b4-139">Max depth of H3 or H4</span></span>
- <span data-ttu-id="073b4-140">Linha em branco antes e depois</span><span class="sxs-lookup"><span data-stu-id="073b4-140">Blank line before and after</span></span>
- <span data-ttu-id="073b4-141">O PlatyPS aplica cabeçalhos específicos em seu esquema - não adicione ou remova cabeçalhos</span><span class="sxs-lookup"><span data-stu-id="073b4-141">PlatyPS enforces specific headers in its schema - do not add or remove headers</span></span>

### <a name="code-blocks"></a><span data-ttu-id="073b4-142">Blocos de código</span><span class="sxs-lookup"><span data-stu-id="073b4-142">Code blocks</span></span>

- <span data-ttu-id="073b4-143">Linha em branco antes e depois</span><span class="sxs-lookup"><span data-stu-id="073b4-143">Blank line before and after</span></span>
- <span data-ttu-id="073b4-144">Usar limites de código marcados -  **powershell**, **Saída** ou outro ID de linguagem apropriado</span><span class="sxs-lookup"><span data-stu-id="073b4-144">Use tagged code fences - **powershell**, **Output**, or other appropriate language ID</span></span>
- <span data-ttu-id="073b4-145">Limite não marcado - blocos de sintaxe ou outros shells</span><span class="sxs-lookup"><span data-stu-id="073b4-145">Untagged fence - syntax blocks or other shells</span></span>
- <span data-ttu-id="073b4-146">Coloque a saída em um bloco de código separado, exceto em exemplos simples, nos quais você não pretende que o leitor use o botão **Copiar**</span><span class="sxs-lookup"><span data-stu-id="073b4-146">Put output in separate code block except for simple examples where you don't intend the for the reader to use the **Copy** button</span></span>
- <span data-ttu-id="073b4-147">Confira uma lista de [linguagens com suporte](/contribute/code-in-docs#supported-languages)</span><span class="sxs-lookup"><span data-stu-id="073b4-147">See list of [supported languages](/contribute/code-in-docs#supported-languages)</span></span>

### <a name="lists"></a><span data-ttu-id="073b4-148">Listas</span><span class="sxs-lookup"><span data-stu-id="073b4-148">Lists</span></span>

- <span data-ttu-id="073b4-149">Recuado corretamente</span><span class="sxs-lookup"><span data-stu-id="073b4-149">Indented properly</span></span>
- <span data-ttu-id="073b4-150">Linha em branco antes do primeiro item e após o último item</span><span class="sxs-lookup"><span data-stu-id="073b4-150">Blank line before first item and after last item</span></span>
- <span data-ttu-id="073b4-151">Marcador - uso de hífen (`-`) não asterisco (`*` )- muito fácil de confundir com ênfase</span><span class="sxs-lookup"><span data-stu-id="073b4-151">Bullet - use hyphen (`-`) not asterisk (`*`) - too easy to confuse with emphasis</span></span>
- <span data-ttu-id="073b4-152">Para listas numeradas, todos os números são "1".</span><span class="sxs-lookup"><span data-stu-id="073b4-152">For numbered lists, all numbers are "1."</span></span>

## <a name="terminology"></a><span data-ttu-id="073b4-153">Terminologia</span><span class="sxs-lookup"><span data-stu-id="073b4-153">Terminology</span></span>

- <span data-ttu-id="073b4-154">PowerShell vs. Windows PowerShell vs. PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="073b4-154">PowerShell vs. Windows PowerShell vs. PowerShell Core</span></span>
- <span data-ttu-id="073b4-155">Confira a [Terminologia do Produto](powershell-style-guide.md#product-terminology)</span><span class="sxs-lookup"><span data-stu-id="073b4-155">See [Product Terminology](powershell-style-guide.md#product-terminology)</span></span>

## <a name="cmdlet-reference-examples"></a><span data-ttu-id="073b4-156">Exemplos de referência de cmdlet</span><span class="sxs-lookup"><span data-stu-id="073b4-156">Cmdlet reference examples</span></span>

- <span data-ttu-id="073b4-157">Deve ter pelo menos um exemplo na referência de cmdlet</span><span class="sxs-lookup"><span data-stu-id="073b4-157">Must have at least one example in cmdlet reference</span></span>
- <span data-ttu-id="073b4-158">Os exemplos devem ser apenas o código suficiente para demonstrar o uso</span><span class="sxs-lookup"><span data-stu-id="073b4-158">Examples should be just enough code to demonstrate the usage</span></span>
- <span data-ttu-id="073b4-159">Sintaxe do PowerShell</span><span class="sxs-lookup"><span data-stu-id="073b4-159">PowerShell syntax</span></span>
  - <span data-ttu-id="073b4-160">Usar nomes completos de cmdlets e parâmetros - sem aliases</span><span class="sxs-lookup"><span data-stu-id="073b4-160">Use full names of cmdlets and parameters - no aliases</span></span>
  - <span data-ttu-id="073b4-161">Use nivelamento para parâmetros quando a linha de comando ficar muito longa</span><span class="sxs-lookup"><span data-stu-id="073b4-161">Use splatting for parameters when the command line gets too long</span></span>
  - <span data-ttu-id="073b4-162">Evite usar backticks de continuação de linha - use somente quando necessário</span><span class="sxs-lookup"><span data-stu-id="073b4-162">Avoid using line continuation backticks - only use when necessary</span></span>
- <span data-ttu-id="073b4-163">Remova ou simplifique o prompt do PowerShell (`PS>`), exceto quando necessário para o exemplo</span><span class="sxs-lookup"><span data-stu-id="073b4-163">Remove or simplify the PowerShell prompt (`PS>`) except where required for the example</span></span>
- <span data-ttu-id="073b4-164">O exemplo de referência de cmdlet deve seguir o seguinte esquema do PlatyPS</span><span class="sxs-lookup"><span data-stu-id="073b4-164">Cmdlet reference example must follow the following PlatyPS schema</span></span>

  ~~~Markdown
  ### Example 1 - Descriptive title

  Zero or more short descriptive paragraphs explaining the context of the example followed by one or
  more code blocks. Recommend at least one and no more than two.

  ```powershell
  ... one or more PowerShell code statements ...
  ```

  ```Output
  Example output of the code above.
  ```

  Zero or more optional follow up paragraphs that explain the details of the code and output.
  ~~~

- <span data-ttu-id="073b4-165">Não insira parágrafos entre os blocos de código.</span><span class="sxs-lookup"><span data-stu-id="073b4-165">Do not put paragraphs between the code blocks.</span></span> <span data-ttu-id="073b4-166">Todo o conteúdo descritivo deve vir antes ou depois dos blocos de código.</span><span class="sxs-lookup"><span data-stu-id="073b4-166">All descriptive content must come before or after the code blocks.</span></span>

## <a name="linking-to-other-documents"></a><span data-ttu-id="073b4-167">Vinculação a outros documentos</span><span class="sxs-lookup"><span data-stu-id="073b4-167">Linking to other documents</span></span>

- <span data-ttu-id="073b4-168">Vinculação fora do docset ou entre conceitos e referência de cmdlet</span><span class="sxs-lookup"><span data-stu-id="073b4-168">Linking outside the docset or between cmdlet reference and conceptual</span></span>
  - <span data-ttu-id="073b4-169">Use URLs relativas ao vincular ao docs.microsoft.com (remova `https://docs.microsoft.com/en-us`)</span><span class="sxs-lookup"><span data-stu-id="073b4-169">Use relative URLs when linking to docs.microsoft.com (remove `https://docs.microsoft.com/en-us`)</span></span>
  - <span data-ttu-id="073b4-170">Não inclua localidades em URLs nas propriedades da Microsoft (por exemplo,</span><span class="sxs-lookup"><span data-stu-id="073b4-170">Do not include locales in URLs on Microsoft properties (eg.</span></span> <span data-ttu-id="073b4-171">remova `/en-us` da URL)</span><span class="sxs-lookup"><span data-stu-id="073b4-171">remove `/en-us` from URL)</span></span>
  - <span data-ttu-id="073b4-172">Todas as URLs para sites externos devem usar HTTPS, a menos que isso não seja válido para o site de destino</span><span class="sxs-lookup"><span data-stu-id="073b4-172">All URLs to external websites should use HTTPS unless that is not valid for the target site</span></span>
- <span data-ttu-id="073b4-173">No docset</span><span class="sxs-lookup"><span data-stu-id="073b4-173">Within docset</span></span>
  - <span data-ttu-id="073b4-174">Link para o caminho do arquivo (por exemplo, `../folder/file.md`)</span><span class="sxs-lookup"><span data-stu-id="073b4-174">Link to file path (e.g. `../folder/file.md`)</span></span>
  - <span data-ttu-id="073b4-175">Todos os caminhos de arquivo usam caracteres de barra (`/`)</span><span class="sxs-lookup"><span data-stu-id="073b4-175">All file paths use forward-slash (`/`) characters</span></span>
- <span data-ttu-id="073b4-176">Links de imagem devem ter texto alt exclusivo</span><span class="sxs-lookup"><span data-stu-id="073b4-176">Image links should have unique alt text</span></span>
