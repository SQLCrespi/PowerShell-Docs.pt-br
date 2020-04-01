---
title: Editar artigos de referência
description: Este artigo explica os requisitos específicos para edição de referências de cmdlet e os tópicos Sobre na documentação do PowerShell.
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: 3aed1c14429310c57681397d4877a3a6f48400fd
ms.sourcegitcommit: 30ccbbb32915b551c4cd4c91ef1df96b5b7514c4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2020
ms.locfileid: "80500968"
---
# <a name="editing-reference-articles"></a><span data-ttu-id="fbc1b-103">Editar artigos de referência</span><span class="sxs-lookup"><span data-stu-id="fbc1b-103">Editing reference articles</span></span>

<span data-ttu-id="fbc1b-104">Os artigos de referência de cmdlet têm uma estrutura específica.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-104">Cmdlet reference articles have a specific structure.</span></span> <span data-ttu-id="fbc1b-105">Ela é definida por [PlatyPS][].</span><span class="sxs-lookup"><span data-stu-id="fbc1b-105">This structure is defined by [PlatyPS][].</span></span>
<span data-ttu-id="fbc1b-106">O PlatyPS gera a ajuda de cmdlets para os módulos do PowerShell no Markdown.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-106">PlatyPS generates the cmdlet help for PowerShell modules in Markdown.</span></span> <span data-ttu-id="fbc1b-107">Depois de editar os arquivos Markdown, o PlatyPS é usado para criar os arquivos de ajuda do MAML usados pelo cmdlet `Get-Help`.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-107">After editing the Markdown files, PlatyPS is used create the MAML help files used by the `Get-Help` cmdlet.</span></span>

<span data-ttu-id="fbc1b-108">O PlatyPS tem um esquema embutido em código para a referência de cmdlet que é gravado no código.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-108">PlatyPS has a hard-coded schema for cmdlet reference that is written into the code.</span></span> <span data-ttu-id="fbc1b-109">O documento [platyPS.schema.md][] tenta descrever essa estrutura.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-109">The [platyPS.schema.md][] document attempts to describe this structure.</span></span> <span data-ttu-id="fbc1b-110">As violações de esquema causam erros de build que precisam ser corrigidos antes que possamos aceitar sua contribuição.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-110">Schema violations cause build errors that must be fixed before we can accept your contribution.</span></span>

## <a name="general-guidelines"></a><span data-ttu-id="fbc1b-111">Diretrizes gerais</span><span class="sxs-lookup"><span data-stu-id="fbc1b-111">General guidelines</span></span>

- <span data-ttu-id="fbc1b-112">Não remova nenhuma das estruturas de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-112">Do not remove any of the header structures.</span></span> <span data-ttu-id="fbc1b-113">O PlatyPS espera um conjunto específico de cabeçalhos.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-113">PlatyPS expects a specific set of headers.</span></span>
- <span data-ttu-id="fbc1b-114">Os cabeçalhos **Tipo de entrada** e **Tipo de saída** precisam ter um tipo.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-114">The **Input type** and **Output type** headers must have a type.</span></span> <span data-ttu-id="fbc1b-115">Se o cmdlet não usar uma entrada nem retornar um valor, use o valor `None`.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-115">If the cmdlet does not take input or return a value then use the value `None`.</span></span>
- <span data-ttu-id="fbc1b-116">Os blocos de código isolados são permitidos somente na seção [Exemplos](#structuring-examples).</span><span class="sxs-lookup"><span data-stu-id="fbc1b-116">Fenced code blocks are only allowed in the [Examples](#structuring-examples) section.</span></span>
- <span data-ttu-id="fbc1b-117">As extensões de código embutido podem ser usadas em qualquer parágrafo.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-117">Inline code spans can be used in any paragraph.</span></span>

## <a name="formatting-about_-files"></a><span data-ttu-id="fbc1b-118">Formatar arquivos About_</span><span class="sxs-lookup"><span data-stu-id="fbc1b-118">Formatting About_ files</span></span>

<span data-ttu-id="fbc1b-119">Os arquivos `About_*` agora são processados pelo [Pandoc][], em vez do PlatyPS.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-119">`About_*` files are now processed by [Pandoc][], instead of PlatyPS.</span></span> <span data-ttu-id="fbc1b-120">Os arquivos `About_*` são formatados para oferecer a melhor compatibilidade com todas as versões do PowerShell e com as ferramentas de publicação.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-120">`About_*` files are formatted for the best compatibility across all versions of PowerShell and with the publishing tools.</span></span>

<span data-ttu-id="fbc1b-121">Diretrizes básicas de formatação:</span><span class="sxs-lookup"><span data-stu-id="fbc1b-121">Basic formatting guidelines:</span></span>

- <span data-ttu-id="fbc1b-122">Limite as linhas a 80 caracteres</span><span class="sxs-lookup"><span data-stu-id="fbc1b-122">Limit lines to 80 characters</span></span>
- <span data-ttu-id="fbc1b-123">Os blocos de código e as tabelas são limitados a 76 caracteres, pois o Pandoc os recua em quatro espaços durante a conversão para texto sem formatação</span><span class="sxs-lookup"><span data-stu-id="fbc1b-123">Code blocks and tables are limited to 76 characters because Pandoc indents these by four spaces during conversion to plain text</span></span>
- <span data-ttu-id="fbc1b-124">As tabelas precisam se ajustar a 76 caracteres</span><span class="sxs-lookup"><span data-stu-id="fbc1b-124">Tables need to fit within 76 characters</span></span>
  - <span data-ttu-id="fbc1b-125">Quebre manualmente o conteúdo das células em várias linhas</span><span class="sxs-lookup"><span data-stu-id="fbc1b-125">Manually wrap contents of cells across multiple lines</span></span>
  - <span data-ttu-id="fbc1b-126">Use caracteres de abertura e fechamento `|` em cada linha</span><span class="sxs-lookup"><span data-stu-id="fbc1b-126">Use opening and closing `|` characters on each line</span></span>
  - <span data-ttu-id="fbc1b-127">Confira um exemplo funcional em [about_Comparison_Operators][about-example]</span><span class="sxs-lookup"><span data-stu-id="fbc1b-127">See a working example in [about_Comparison_Operators][about-example]</span></span>
- <span data-ttu-id="fbc1b-128">Use os caracteres especiais do Pandoc `\`, `$` e `<`</span><span class="sxs-lookup"><span data-stu-id="fbc1b-128">Using Pandoc special characters `\`,`$`, and `<`</span></span>
  - <span data-ttu-id="fbc1b-129">Em um cabeçalho – esses caracteres devem ter escape usando um caractere `\` inicial ou entre aspas invertidas (`` ` ``)</span><span class="sxs-lookup"><span data-stu-id="fbc1b-129">Within a header - these characters must be escaped using a leading `\` character or enclosed in backticks (`` ` ``)</span></span>
  - <span data-ttu-id="fbc1b-130">Em um parágrafo – esses caracteres devem ser colocados em extensões de código.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-130">Within a paragraph, these characters should be put into code spans.</span></span> <span data-ttu-id="fbc1b-131">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fbc1b-131">For example:</span></span>

    ~~~markdown
    ### The purpose of the \$foo variable

    The `$foo` variable is used to store ...
    ~~~

## <a name="structuring-examples"></a><span data-ttu-id="fbc1b-132">Estruturar exemplos</span><span class="sxs-lookup"><span data-stu-id="fbc1b-132">Structuring examples</span></span>

<span data-ttu-id="fbc1b-133">No esquema do PlatyPS, o cabeçalho **EXAMPLES** é um cabeçalho H2, e cada exemplo é um cabeçalho H3.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-133">In the PlatyPS schema, the **EXAMPLES** header is an H2 header and each example is an H3 header.</span></span>

<span data-ttu-id="fbc1b-134">Em um exemplo, o esquema não permite que os blocos de código sejam separados por parágrafos.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-134">Within an example, the schema does not allow code blocks to be separated by paragraphs.</span></span> <span data-ttu-id="fbc1b-135">O esquema válido é:</span><span class="sxs-lookup"><span data-stu-id="fbc1b-135">The supported schema is:</span></span>

```
### Example #X title

0 or more paragraphs
1 or more code blocks
0 or more paragraphs.
```

<span data-ttu-id="fbc1b-136">Enumere cada exemplo e adicione um breve título.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-136">Number each example and add a brief title.</span></span>

<span data-ttu-id="fbc1b-137">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fbc1b-137">For example:</span></span>

### <a name="example-1-get-cmdlets-functions-and-aliases"></a><span data-ttu-id="fbc1b-138">Exemplo 1: obter cmdlets, funções e aliases</span><span class="sxs-lookup"><span data-stu-id="fbc1b-138">Example 1: Get cmdlets, functions, and aliases</span></span>

<span data-ttu-id="fbc1b-139">Esse comando obtém os cmdlets, funções e aliases do PowerShell instalados no computador.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-139">This command gets the PowerShell cmdlets, functions, and aliases that are installed on the computer.</span></span>

```powershell
Get-Command
```

### <a name="example-2-get-commands-in-the-current-session"></a><span data-ttu-id="fbc1b-140">Exemplo 2: obter comandos na sessão atual</span><span class="sxs-lookup"><span data-stu-id="fbc1b-140">Example 2: Get commands in the current session</span></span>

```powershell
Get-Command -ListImported
```

## <a name="next-steps"></a><span data-ttu-id="fbc1b-141">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="fbc1b-141">Next steps</span></span>

[<span data-ttu-id="fbc1b-142">Lista de verificação editorial</span><span class="sxs-lookup"><span data-stu-id="fbc1b-142">Editorial checklist</span></span>](editorial-checklist.md)

<!-- link references -->
[PlatyPS]: https://github.com/powershell/platyps
[platyPS.schema.md]: https://github.com/PowerShell/platyPS/blob/master/platyPS.schema.md
[issue1806]: https://github.com/MicrosoftDocs/PowerShell-Docs/issues/1806
[about-example]: /PowerShell/module/Microsoft.PowerShell.Core/About/about_Comparison_Operators
[Pandoc]: https://pandoc.org
