---
title: Editar artigos de referência
description: Este artigo explica os requisitos específicos para edição de referências de cmdlet e os tópicos Sobre na documentação do PowerShell.
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: e135f6cc81ba7537a535a08421e1ca9b2b2af573
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81624764"
---
# <a name="editing-reference-articles"></a><span data-ttu-id="41767-103">Editar artigos de referência</span><span class="sxs-lookup"><span data-stu-id="41767-103">Editing reference articles</span></span>

<span data-ttu-id="41767-104">Os artigos de referência de cmdlet têm uma estrutura específica.</span><span class="sxs-lookup"><span data-stu-id="41767-104">Cmdlet reference articles have a specific structure.</span></span> <span data-ttu-id="41767-105">Ela é definida por [PlatyPS][].</span><span class="sxs-lookup"><span data-stu-id="41767-105">This structure is defined by [PlatyPS][].</span></span>
<span data-ttu-id="41767-106">O PlatyPS gera a ajuda de cmdlets para os módulos do PowerShell no Markdown.</span><span class="sxs-lookup"><span data-stu-id="41767-106">PlatyPS generates the cmdlet help for PowerShell modules in Markdown.</span></span> <span data-ttu-id="41767-107">Depois de editar os arquivos Markdown, o PlatyPS é usado para criar os arquivos de ajuda do MAML usados pelo cmdlet `Get-Help`.</span><span class="sxs-lookup"><span data-stu-id="41767-107">After editing the Markdown files, PlatyPS is used create the MAML help files used by the `Get-Help` cmdlet.</span></span>

<span data-ttu-id="41767-108">O PlatyPS tem um esquema embutido em código para a referência de cmdlet que é gravado no código.</span><span class="sxs-lookup"><span data-stu-id="41767-108">PlatyPS has a hard-coded schema for cmdlet reference that is written into the code.</span></span> <span data-ttu-id="41767-109">O documento [platyPS.schema.md][] tenta descrever essa estrutura.</span><span class="sxs-lookup"><span data-stu-id="41767-109">The [platyPS.schema.md][] document attempts to describe this structure.</span></span> <span data-ttu-id="41767-110">As violações de esquema causam erros de build que precisam ser corrigidos antes que possamos aceitar sua contribuição.</span><span class="sxs-lookup"><span data-stu-id="41767-110">Schema violations cause build errors that must be fixed before we can accept your contribution.</span></span>

## <a name="general-guidelines"></a><span data-ttu-id="41767-111">Diretrizes gerais</span><span class="sxs-lookup"><span data-stu-id="41767-111">General guidelines</span></span>

- <span data-ttu-id="41767-112">Não remova nenhuma das estruturas de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="41767-112">Do not remove any of the header structures.</span></span> <span data-ttu-id="41767-113">O PlatyPS espera um conjunto específico de cabeçalhos.</span><span class="sxs-lookup"><span data-stu-id="41767-113">PlatyPS expects a specific set of headers.</span></span>
- <span data-ttu-id="41767-114">Os cabeçalhos **Tipo de entrada** e **Tipo de saída** precisam ter um tipo.</span><span class="sxs-lookup"><span data-stu-id="41767-114">The **Input type** and **Output type** headers must have a type.</span></span> <span data-ttu-id="41767-115">Se o cmdlet não usar uma entrada nem retornar um valor, use o valor `None`.</span><span class="sxs-lookup"><span data-stu-id="41767-115">If the cmdlet does not take input or return a value then use the value `None`.</span></span>
- <span data-ttu-id="41767-116">Os blocos de código isolados são permitidos somente na seção [Exemplos](#structuring-examples).</span><span class="sxs-lookup"><span data-stu-id="41767-116">Fenced code blocks are only allowed in the [Examples](#structuring-examples) section.</span></span>
- <span data-ttu-id="41767-117">As extensões de código embutido podem ser usadas em qualquer parágrafo.</span><span class="sxs-lookup"><span data-stu-id="41767-117">Inline code spans can be used in any paragraph.</span></span>

## <a name="formatting-about_-files"></a><span data-ttu-id="41767-118">Formatar arquivos About_</span><span class="sxs-lookup"><span data-stu-id="41767-118">Formatting About_ files</span></span>

<span data-ttu-id="41767-119">Os arquivos `About_*` são escritos em Markdown, mas são enviados como arquivos de texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="41767-119">`About_*` files are written in Markdown but are shipped as plain text files.</span></span> <span data-ttu-id="41767-120">Usamos [Pandoc][] para converter a redução em texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="41767-120">We use [Pandoc][] to convert the Markdown to plain text.</span></span> <span data-ttu-id="41767-121">Os arquivos `About_*` são formatados para oferecer a melhor compatibilidade com todas as versões do PowerShell e com as ferramentas de publicação.</span><span class="sxs-lookup"><span data-stu-id="41767-121">`About_*` files are formatted for the best compatibility across all versions of PowerShell and with the publishing tools.</span></span>

<span data-ttu-id="41767-122">Diretrizes básicas de formatação:</span><span class="sxs-lookup"><span data-stu-id="41767-122">Basic formatting guidelines:</span></span>

- <span data-ttu-id="41767-123">Limite as linhas a 80 caracteres.</span><span class="sxs-lookup"><span data-stu-id="41767-123">Limit lines to 80 characters.</span></span> <span data-ttu-id="41767-124">O Pandoc recua alguns blocos de redução, portanto, esses blocos devem ser ajustados.</span><span class="sxs-lookup"><span data-stu-id="41767-124">Pandoc indents some Markdown blocks so those block must be adjusted.</span></span>
  - <span data-ttu-id="41767-125">Os blocos de código são limitados a 76 caracteres</span><span class="sxs-lookup"><span data-stu-id="41767-125">Code blocks are limited to 76 characters</span></span>
  - <span data-ttu-id="41767-126">As tabelas são limitadas a 76 caracteres</span><span class="sxs-lookup"><span data-stu-id="41767-126">Tables are limited 76 characters</span></span>
  - <span data-ttu-id="41767-127">Os blocos de citações (e alertas) são limitados a 78 caracteres</span><span class="sxs-lookup"><span data-stu-id="41767-127">Blockquotes (and Alerts) are limited 78 characters</span></span>

- <span data-ttu-id="41767-128">Usar os metacaracteres especiais de Pandoc `\`, `$` e `<`</span><span class="sxs-lookup"><span data-stu-id="41767-128">Using Pandoc's special meta-characters `\`,`$`, and `<`</span></span>
  - <span data-ttu-id="41767-129">Em um cabeçalho – esses caracteres devem ter escape usando um caractere `\` inicial ou colocados em intervalos de código usando aspas invertidas (`` ` ``)</span><span class="sxs-lookup"><span data-stu-id="41767-129">Within a header - these characters must be escaped using a leading `\` character or enclosed in code spans using backticks (`` ` ``)</span></span>
  - <span data-ttu-id="41767-130">Em um parágrafo – esses caracteres devem ser colocados em extensões de código.</span><span class="sxs-lookup"><span data-stu-id="41767-130">Within a paragraph, these characters should be put into code spans.</span></span> <span data-ttu-id="41767-131">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="41767-131">For example:</span></span>

    ~~~markdown
    ### The purpose of the \$foo variable

    The `$foo` variable is used to store ...
    ~~~

- <span data-ttu-id="41767-132">As tabelas precisam se ajustar a 76 caracteres</span><span class="sxs-lookup"><span data-stu-id="41767-132">Tables need to fit within 76 characters</span></span>
  - <span data-ttu-id="41767-133">Quebre manualmente o conteúdo das células em várias linhas</span><span class="sxs-lookup"><span data-stu-id="41767-133">Manually wrap contents of cells across multiple lines</span></span>
  - <span data-ttu-id="41767-134">Use caracteres de abertura e fechamento `|` em cada linha</span><span class="sxs-lookup"><span data-stu-id="41767-134">Use opening and closing `|` characters on each line</span></span>
  - <span data-ttu-id="41767-135">O exemplo a seguir ilustra como construir corretamente uma tabela contendo informações com quebra de linha em várias linhas dentro de uma célula.</span><span class="sxs-lookup"><span data-stu-id="41767-135">The following example illustrates how to properly construct a table that contains information that wraps on multiple lines within a cell.</span></span>

    ~~~markdown
    ```
    |Operator|Description                |Example                          |
    |--------|---------------------------|---------------------------------|
    |`-is`   |Returns TRUE when the input|`(get-date) -is [DateTime]`      |
    |        |is an instance of the      |`True`                           |
    |        |specified .NET type.       |                                 |
    |`-isNot`|Returns TRUE when the input|`(get-date) -isNot [DateTime]`   |
    |        |not an instance of the     |`False`                          |
    |        |specified.NET type.        |                                 |
    |`-as`   |Converts the input to the  |`"5/7/07" -as [DateTime]`        |
    |        |specified .NET type.       |`Monday, May 7, 2007 12:00:00 AM`|
    ```
    ~~~

    > [!NOTE]
    > <span data-ttu-id="41767-136">A limitação de 76 colunas aplica-se apenas aos tópicos `About_*`.</span><span class="sxs-lookup"><span data-stu-id="41767-136">The 76-column limitation applies only to `About_*` topics.</span></span> <span data-ttu-id="41767-137">Você pode usar colunas largas em artigos conceituais ou de referência de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="41767-137">You can use wide columns in conceptual or cmdlet reference articles.</span></span>

## <a name="structuring-examples"></a><span data-ttu-id="41767-138">Estruturar exemplos</span><span class="sxs-lookup"><span data-stu-id="41767-138">Structuring examples</span></span>

<span data-ttu-id="41767-139">No esquema do PlatyPS, o cabeçalho **EXAMPLES** é um cabeçalho H2, e cada exemplo é um cabeçalho H3.</span><span class="sxs-lookup"><span data-stu-id="41767-139">In the PlatyPS schema, the **EXAMPLES** header is an H2 header and each example is an H3 header.</span></span>

<span data-ttu-id="41767-140">Em um exemplo, o esquema não permite que os blocos de código sejam separados por parágrafos.</span><span class="sxs-lookup"><span data-stu-id="41767-140">Within an example, the schema does not allow code blocks to be separated by paragraphs.</span></span> <span data-ttu-id="41767-141">O esquema válido é:</span><span class="sxs-lookup"><span data-stu-id="41767-141">The supported schema is:</span></span>

```
### Example #X title

0 or more paragraphs
1 or more code blocks
0 or more paragraphs.
```

<span data-ttu-id="41767-142">Enumere cada exemplo e adicione um breve título.</span><span class="sxs-lookup"><span data-stu-id="41767-142">Number each example and add a brief title.</span></span>

<span data-ttu-id="41767-143">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="41767-143">For example:</span></span>

### <a name="example-1-get-cmdlets-functions-and-aliases"></a><span data-ttu-id="41767-144">Exemplo 1: obter cmdlets, funções e aliases</span><span class="sxs-lookup"><span data-stu-id="41767-144">Example 1: Get cmdlets, functions, and aliases</span></span>

<span data-ttu-id="41767-145">Esse comando obtém os cmdlets, funções e aliases do PowerShell instalados no computador.</span><span class="sxs-lookup"><span data-stu-id="41767-145">This command gets the PowerShell cmdlets, functions, and aliases that are installed on the computer.</span></span>

```powershell
Get-Command
```

### <a name="example-2-get-commands-in-the-current-session"></a><span data-ttu-id="41767-146">Exemplo 2: obter comandos na sessão atual</span><span class="sxs-lookup"><span data-stu-id="41767-146">Example 2: Get commands in the current session</span></span>

```powershell
Get-Command -ListImported
```

## <a name="next-steps"></a><span data-ttu-id="41767-147">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="41767-147">Next steps</span></span>

[<span data-ttu-id="41767-148">Lista de verificação editorial</span><span class="sxs-lookup"><span data-stu-id="41767-148">Editorial checklist</span></span>](editorial-checklist.md)

<!-- link references -->
[PlatyPS]: https://github.com/powershell/platyps
[platyPS.schema.md]: https://github.com/PowerShell/platyPS/blob/master/platyPS.schema.md
[issue1806]: https://github.com/MicrosoftDocs/PowerShell-Docs/issues/1806
[about-example]: /PowerShell/module/Microsoft.PowerShell.Core/About/about_Comparison_Operators
[Pandoc]: https://pandoc.org
