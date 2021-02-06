---
title: Guia de estilo do PowerShell no Docs
description: Este artigo fornece as regras de estilo para escrever a documentação do PowerShell.
ms.date: 12/09/2020
ms.topic: conceptual
ms.openlocfilehash: 6f23f63cffc9fed9cbbcf84539875bfaf4247732
ms.sourcegitcommit: 61765d08321623743dc5db5367160f6982fe7857
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "99603321"
---
# <a name="powershell-docs-style-guide"></a><span data-ttu-id="d5379-103">Guia de estilo do PowerShell no Docs</span><span class="sxs-lookup"><span data-stu-id="d5379-103">PowerShell-Docs style guide</span></span>

<span data-ttu-id="d5379-104">Este artigo fornece orientações de estilo específicas de conteúdo do PowerShell-Docs.</span><span class="sxs-lookup"><span data-stu-id="d5379-104">This article provides style guidance specific to the PowerShell-Docs content.</span></span> <span data-ttu-id="d5379-105">Ele se baseia nas informações descritas na [visão geral](overview.md#get-started-writing-docs).</span><span class="sxs-lookup"><span data-stu-id="d5379-105">It builds on the information outlined in the [Overview](overview.md#get-started-writing-docs).</span></span>

## <a name="product-terminology"></a><span data-ttu-id="d5379-106">Terminologia do produto</span><span class="sxs-lookup"><span data-stu-id="d5379-106">Product Terminology</span></span>

<span data-ttu-id="d5379-107">O PowerShell tem diversas variantes.</span><span class="sxs-lookup"><span data-stu-id="d5379-107">There are several variants of PowerShell.</span></span>

- <span data-ttu-id="d5379-108">**PowerShell** – é o termo padrão.</span><span class="sxs-lookup"><span data-stu-id="d5379-108">**PowerShell** - This is the default.</span></span> <span data-ttu-id="d5379-109">Consideramos o PowerShell 7 e superior para ser o verdadeiro PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5379-109">We consider PowerShell 7 and beyond to be the one, true PowerShell.</span></span>
- <span data-ttu-id="d5379-110">**PowerShell Core** – PowerShell criado com base no .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d5379-110">**PowerShell Core** - PowerShell built on .NET Core.</span></span> <span data-ttu-id="d5379-111">O uso do termo **principal** deve ser limitado a casos em que é necessário diferenciá-los do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5379-111">Usage of the term **Core** should be limited to cases where it's necessary to differentiate it from Windows PowerShell.</span></span>
- <span data-ttu-id="d5379-112">**Windows PowerShell** – PowerShell criado no .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d5379-112">**Windows PowerShell** - PowerShell built on .NET Framework.</span></span> <span data-ttu-id="d5379-113">O Windows PowerShell é fornecido apenas no Windows e requer o Framework completo.</span><span class="sxs-lookup"><span data-stu-id="d5379-113">Windows PowerShell ships only on Windows and requires the complete Framework.</span></span>

  <span data-ttu-id="d5379-114">Em geral, as referências a "Windows PowerShell" na documentação podem ser alteradas para o _PowerShell_.</span><span class="sxs-lookup"><span data-stu-id="d5379-114">In general, references to "Windows PowerShell" in documentation can be changed to _PowerShell_.</span></span>
  <span data-ttu-id="d5379-115">"Windows PowerShell" deve ser usado quando o comportamento específico do _Windows PowerShell_ está sendo discutido.</span><span class="sxs-lookup"><span data-stu-id="d5379-115">"Windows PowerShell" should be used when _Windows PowerShell_-specific behavior is being discussed.</span></span>

<span data-ttu-id="d5379-116">Produtos relacionados</span><span class="sxs-lookup"><span data-stu-id="d5379-116">Related products</span></span>

- <span data-ttu-id="d5379-117">**Visual Studio Code (vs Code)** -este é o editor de código aberto gratuito da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d5379-117">**Visual Studio Code (VS Code)** - This is Microsoft's free, open-source editor.</span></span> <span data-ttu-id="d5379-118">Na primeira menção, o nome completo deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="d5379-118">At first mention, the full name should be used.</span></span> <span data-ttu-id="d5379-119">Depois disso, você poderá usar o **VS Code**.</span><span class="sxs-lookup"><span data-stu-id="d5379-119">After that you may use **VS Code**.</span></span> <span data-ttu-id="d5379-120">Não use "VSCode".</span><span class="sxs-lookup"><span data-stu-id="d5379-120">Don't use "VSCode".</span></span>
- <span data-ttu-id="d5379-121">**Extensão do PowerShell para Visual Studio Code** – a extensão transforma VS Code no IDE preferencial para o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5379-121">**PowerShell Extension for Visual Studio Code** - The extension turns VS Code into the preferred IDE for PowerShell.</span></span> <span data-ttu-id="d5379-122">Na primeira menção, o nome completo deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="d5379-122">At first mention, the full name should be used.</span></span> <span data-ttu-id="d5379-123">Depois disso, você poderá usar a **extensão do PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="d5379-123">After that you may use **PowerShell extension**.</span></span>
- <span data-ttu-id="d5379-124">**Azure PowerShell** – é a coleção de módulos do PowerShell usada para gerenciar os serviços do Azure.</span><span class="sxs-lookup"><span data-stu-id="d5379-124">**Azure PowerShell** - This is the collection of PowerShell modules used to manage Azure services.</span></span>
- <span data-ttu-id="d5379-125">**Azure Stack** do PowerShell – é a coleção de módulos do PowerShell usada para gerenciar a solução de nuvem híbrida da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d5379-125">**Azure Stack PowerShell** - This is the collection of PowerShell modules used to manage Microsoft's hybrid cloud solution.</span></span>

## <a name="markdown-specifics"></a><span data-ttu-id="d5379-126">Especificações de Markdown</span><span class="sxs-lookup"><span data-stu-id="d5379-126">Markdown specifics</span></span>

<span data-ttu-id="d5379-127">O Microsoft OPS (Open Publishing SystemS), que cria nossa documentação, usa [markdig][] para processar os documentos em Markdown.</span><span class="sxs-lookup"><span data-stu-id="d5379-127">The Microsoft Open Publishing System (OPS) that builds our documentation uses [markdig][] to process the Markdown documents.</span></span> <span data-ttu-id="d5379-128">O markdig analisa os documentos com base nas regras de especificação do [CommonMark][] mais recentes.</span><span class="sxs-lookup"><span data-stu-id="d5379-128">Markdig parses the documents based on the rules of the latest [CommonMark][] specification.</span></span>

<span data-ttu-id="d5379-129">A nova especificação do CommonMark é muito mais rigorosa quanto à construção de alguns elementos de Markdown.</span><span class="sxs-lookup"><span data-stu-id="d5379-129">The new CommonMark spec is much stricter about the construction of some Markdown elements.</span></span> <span data-ttu-id="d5379-130">Preste muita atenção aos detalhes fornecidos neste documento.</span><span class="sxs-lookup"><span data-stu-id="d5379-130">Pay close attention to the details provided in this document.</span></span>

### <a name="blank-lines-spaces-and-tabs"></a><span data-ttu-id="d5379-131">Linhas em branco, espaços e tabulações</span><span class="sxs-lookup"><span data-stu-id="d5379-131">Blank lines, spaces, and tabs</span></span>

<span data-ttu-id="d5379-132">As linhas em branco também sinalizam o fim de um bloco em Markdown.</span><span class="sxs-lookup"><span data-stu-id="d5379-132">Blank lines also signal the end of a block in Markdown.</span></span> <span data-ttu-id="d5379-133">Deve haver um espaço em branco único entre os blocos de Markdown de diferentes tipos (por exemplo, entre um parágrafo e uma lista ou cabeçalho).</span><span class="sxs-lookup"><span data-stu-id="d5379-133">There should be a single blank between Markdown blocks of different types (for example, between a paragraph and a list or header).</span></span>

<span data-ttu-id="d5379-134">Várias linhas em branco consecutivas são renderizadas como uma única linha em branco em HTML.</span><span class="sxs-lookup"><span data-stu-id="d5379-134">Multiple consecutive blank lines render as a single blank line in HTML.</span></span> <span data-ttu-id="d5379-135">Eles não atendem a nenhuma finalidade.</span><span class="sxs-lookup"><span data-stu-id="d5379-135">They serve no purpose.</span></span>
<span data-ttu-id="d5379-136">Dentro de um bloco de código, linhas em branco consecutivas quebram o bloco de código.</span><span class="sxs-lookup"><span data-stu-id="d5379-136">Within a code block, consecutive blank lines break the code block.</span></span>

<span data-ttu-id="d5379-137">Remova espaços extras no final das linhas.</span><span class="sxs-lookup"><span data-stu-id="d5379-137">Remove extra spaces at the end of lines.</span></span>

> [!NOTE]
> <span data-ttu-id="d5379-138">O espaçamento é importante em Markdown.</span><span class="sxs-lookup"><span data-stu-id="d5379-138">Spacing is significant in Markdown.</span></span> <span data-ttu-id="d5379-139">Use sempre espaços em vez de tabulação.</span><span class="sxs-lookup"><span data-stu-id="d5379-139">Always uses spaces instead of hard tabs.</span></span> <span data-ttu-id="d5379-140">Os espaços à direita podem mudar a maneira como o Markdown é renderizado.</span><span class="sxs-lookup"><span data-stu-id="d5379-140">Trailing spaces can change how Markdown renders.</span></span>

### <a name="titles-and-headings"></a><span data-ttu-id="d5379-141">Títulos e cabeçalhos</span><span class="sxs-lookup"><span data-stu-id="d5379-141">Titles and headings</span></span>

<span data-ttu-id="d5379-142">Use somente [cabeçalhos ATX][atx] (estilo #, em vez de cabeçalhos de estilo `=` ou `-` ).</span><span class="sxs-lookup"><span data-stu-id="d5379-142">Only use [ATX headings][atx] (# style, as opposed to `=` or `-` style headers).</span></span>

- <span data-ttu-id="d5379-143">Uso de maiúsculas e minúsculas – apenas nomes próprios e a primeira letra de um título ou cabeçalho devem ser escritos em maiúsculas</span><span class="sxs-lookup"><span data-stu-id="d5379-143">Use sentence case - only proper nouns and the first letter of a title or header should be capitalized</span></span>
- <span data-ttu-id="d5379-144">Deve haver um único espaço entre `#` e a primeira letra do cabeçalho</span><span class="sxs-lookup"><span data-stu-id="d5379-144">There must be a single space between the `#` and the first letter of the heading</span></span>
- <span data-ttu-id="d5379-145">Os títulos devem estar rodeados por uma única linha em branco</span><span class="sxs-lookup"><span data-stu-id="d5379-145">Headings should be surrounded by a single blank line</span></span>
- <span data-ttu-id="d5379-146">Apenas um H1 por documento</span><span class="sxs-lookup"><span data-stu-id="d5379-146">Only one H1 per document</span></span>
- <span data-ttu-id="d5379-147">Os níveis do cabeçalho devem ser incrementados por um.</span><span class="sxs-lookup"><span data-stu-id="d5379-147">Header levels should increment by one.</span></span> <span data-ttu-id="d5379-148">Não ignorar níveis</span><span class="sxs-lookup"><span data-stu-id="d5379-148">Don't skip levels</span></span>
- <span data-ttu-id="d5379-149">Não usar negrito ou outra marcação nos cabeçalhos</span><span class="sxs-lookup"><span data-stu-id="d5379-149">Don't use bold or other markup in headers</span></span>

### <a name="limit-line-length-to-100-characters"></a><span data-ttu-id="d5379-150">Limite o comprimento da linha a 100 caracteres</span><span class="sxs-lookup"><span data-stu-id="d5379-150">Limit line length to 100 characters</span></span>

<span data-ttu-id="d5379-151">Isso se aplica a artigos conceituais e à referência de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d5379-151">This applies to conceptual articles and cmdlet reference.</span></span> <span data-ttu-id="d5379-152">Limitar o comprimento da linha melhora a legibilidade de comparações e histórico de git.</span><span class="sxs-lookup"><span data-stu-id="d5379-152">Limiting the line length improves the readability of git diffs and history.</span></span> <span data-ttu-id="d5379-153">Também facilita a contribuição de outros escritores.</span><span class="sxs-lookup"><span data-stu-id="d5379-153">It also makes it easier for other writers to make contributions.</span></span>

<span data-ttu-id="d5379-154">Use a extensão [Reflow Markdown][reflow] no Visual Studio Code para refluir parágrafos com facilidade e ajustar o comprimento da linha prescrita.</span><span class="sxs-lookup"><span data-stu-id="d5379-154">Use the [Reflow Markdown][reflow] extension in Visual Studio Code to easily reflow paragraphs to fit the prescribed line length.</span></span>

<span data-ttu-id="d5379-155">Os tópicos Sobre são limitados a 80 caracteres.</span><span class="sxs-lookup"><span data-stu-id="d5379-155">About_topics are limited to 80 characters.</span></span> <span data-ttu-id="d5379-156">Para obter informações mais específicas, consulte [formatando About_ arquivos](#formatting-about_-files).</span><span class="sxs-lookup"><span data-stu-id="d5379-156">For more specific information, see [Formatting About_ files](#formatting-about_-files).</span></span>

### <a name="lists"></a><span data-ttu-id="d5379-157">Listas</span><span class="sxs-lookup"><span data-stu-id="d5379-157">Lists</span></span>

<span data-ttu-id="d5379-158">Se sua lista contiver várias frases ou parágrafos, considere usar um cabeçalho de subnível em vez de uma lista.</span><span class="sxs-lookup"><span data-stu-id="d5379-158">If your list contains multiple sentences or paragraphs, consider using a sublevel header rather than a list.</span></span>

<span data-ttu-id="d5379-159">A lista deve estar rodeada por uma única linha em branco.</span><span class="sxs-lookup"><span data-stu-id="d5379-159">List should be surrounded by a single blank line.</span></span>

#### <a name="unordered-lists"></a><span data-ttu-id="d5379-160">Listas não ordenadas</span><span class="sxs-lookup"><span data-stu-id="d5379-160">Unordered lists</span></span>

<span data-ttu-id="d5379-161">Não Finalize os itens de lista com um período, a menos que eles contenham várias frases.</span><span class="sxs-lookup"><span data-stu-id="d5379-161">Don't end list items with a period unless they contain multiple sentences.</span></span> <span data-ttu-id="d5379-162">Use o caractere de hífen (`-`) para marcadores de itens de lista.</span><span class="sxs-lookup"><span data-stu-id="d5379-162">Use the hyphen character (`-`) for list item bullets.</span></span> <span data-ttu-id="d5379-163">Isso evita confusão com marcações em negrito ou itálico que usem o asterisco [`*`].</span><span class="sxs-lookup"><span data-stu-id="d5379-163">This avoids confusion with bold or italic markup that uses the asterisk [`*`].</span></span> <span data-ttu-id="d5379-164">Para incluir um parágrafo ou outros elementos em um item de marcador, insira uma quebra de linha e alinhe o recuo com o primeiro caractere após o marcador.</span><span class="sxs-lookup"><span data-stu-id="d5379-164">To include a paragraph or other elements under a bullet item, insert a line break and align indentation with the first character after the bullet.</span></span>

<span data-ttu-id="d5379-165">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d5379-165">For example:</span></span>

```markdown
This is a list that contain child elements under a bullet item.

- First bullet item

  Sentence explaining the first bullet.

  - Child bullet item

    Sentence explaining the child bullet.

- Second bullet item
- Third bullet item
```

<span data-ttu-id="d5379-166">Esta é uma lista que contém elementos filho em um item de marcador.</span><span class="sxs-lookup"><span data-stu-id="d5379-166">This is a list that contains child elements under a bullet item.</span></span>

- <span data-ttu-id="d5379-167">Primeiro item de marcador</span><span class="sxs-lookup"><span data-stu-id="d5379-167">First bullet item</span></span>

  <span data-ttu-id="d5379-168">Frase explicando o primeiro marcador.</span><span class="sxs-lookup"><span data-stu-id="d5379-168">Sentence explaining the first bullet.</span></span>

  - <span data-ttu-id="d5379-169">Item de marcador filho</span><span class="sxs-lookup"><span data-stu-id="d5379-169">Child bullet item</span></span>

    <span data-ttu-id="d5379-170">Frase explicando o marcador filho.</span><span class="sxs-lookup"><span data-stu-id="d5379-170">Sentence explaining the child bullet.</span></span>

- <span data-ttu-id="d5379-171">Segundo item de marcador</span><span class="sxs-lookup"><span data-stu-id="d5379-171">Second bullet item</span></span>
- <span data-ttu-id="d5379-172">Terceiro item de marcador</span><span class="sxs-lookup"><span data-stu-id="d5379-172">Third bullet item</span></span>

#### <a name="ordered-lists"></a><span data-ttu-id="d5379-173">Listas ordenadas</span><span class="sxs-lookup"><span data-stu-id="d5379-173">Ordered lists</span></span>

<span data-ttu-id="d5379-174">Para incluir um parágrafo ou outros elementos em um item numerado, alinhe o recuo com o primeiro caractere após o número do item.</span><span class="sxs-lookup"><span data-stu-id="d5379-174">To include a paragraph or other elements under a numbered item, align indentation with the first character after the item number.</span></span> <span data-ttu-id="d5379-175">Todos os itens em uma lista numerada devem usar o número `1.` em vez de incrementar cada item.</span><span class="sxs-lookup"><span data-stu-id="d5379-175">All items in a numbered listed should use the number `1.` rather than incrementing each item.</span></span> <span data-ttu-id="d5379-176">A renderização de Markdown incrementa o valor automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d5379-176">Markdown rendering increments the value automatically.</span></span> <span data-ttu-id="d5379-177">Isso facilita a reorganização dos itens e padroniza o recuo do conteúdo subordinado.</span><span class="sxs-lookup"><span data-stu-id="d5379-177">This makes reordering items easier and standardizes the indentation of subordinate content.</span></span>

<span data-ttu-id="d5379-178">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d5379-178">For example:</span></span>

```markdown
1. For the first element, insert a single space after the 1. Long sentences should be
   wrapped to the next line and must line up with the first character after the numbered
   list marker.

   To include a second element (like this one), insert a line break after the first
   and align indentations. The indentation of the second element must line up with
   the first character after the numbered list marker. For single digit items, like
   this one, you indent to column 4. For double digits items, for example item number
   10, you indent to column 5.

1. The next numbered item starts here.
```

<span data-ttu-id="d5379-179">O Markdown resultante é renderizado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="d5379-179">The resulting Markdown is rendered as follows:</span></span>

1. <span data-ttu-id="d5379-180">No primeiro elemento, insira um único espaço após o 1.</span><span class="sxs-lookup"><span data-stu-id="d5379-180">For the first element, insert a single space after the 1.</span></span> <span data-ttu-id="d5379-181">Frases longas devem ser quebradas na próxima linha e devem ser alinhadas com o primeiro caractere após o marcador de lista numerada.</span><span class="sxs-lookup"><span data-stu-id="d5379-181">Long sentences should be wrapped to the next line and must line up with the first character after the numbered list marker.</span></span>

   <span data-ttu-id="d5379-182">Para incluir um segundo elemento (como este), insira uma quebra de linha após a primeira e alinhe os recuos.</span><span class="sxs-lookup"><span data-stu-id="d5379-182">To include a second element (like this one), insert a line break after the first and align indentations.</span></span> <span data-ttu-id="d5379-183">O recuo do segundo elemento deve ser alinhado com o primeiro caractere após o marcador de lista numerada.</span><span class="sxs-lookup"><span data-stu-id="d5379-183">The indentation of the second element must line up with the first character after the numbered list marker.</span></span> <span data-ttu-id="d5379-184">Para itens com dígito único, como este, alinhe o recuo na coluna 4.</span><span class="sxs-lookup"><span data-stu-id="d5379-184">For single digit items, like this one, you indent to column 4.</span></span> <span data-ttu-id="d5379-185">Para itens com dois dígitos, por exemplo, item número 10, alinhe o recuo na coluna 5.</span><span class="sxs-lookup"><span data-stu-id="d5379-185">For double digits items, for example item number 10, you indent to column 5.</span></span>

1. <span data-ttu-id="d5379-186">O próximo item numerado começa aqui.</span><span class="sxs-lookup"><span data-stu-id="d5379-186">The next numbered item starts here.</span></span>

### <a name="images"></a><span data-ttu-id="d5379-187">Imagens</span><span class="sxs-lookup"><span data-stu-id="d5379-187">Images</span></span>

<span data-ttu-id="d5379-188">A sintaxe que deve ser incluída em uma imagem é:</span><span class="sxs-lookup"><span data-stu-id="d5379-188">The syntax to include an image is:</span></span>

```markdown
![[alt text]](<folderPath>)

Example:
![Introduction](./media/overview/Introduction.png)
```

<span data-ttu-id="d5379-189">Em que `alt text` é uma breve descrição da imagem, e `<folder path>` é um caminho relativo para a imagem.</span><span class="sxs-lookup"><span data-stu-id="d5379-189">Where `alt text` is a brief description of the image and `<folder path>` is a relative path to the image.</span></span> <span data-ttu-id="d5379-190">O texto alternativo é obrigatório em leitores de tela para deficientes visuais.</span><span class="sxs-lookup"><span data-stu-id="d5379-190">Alternate text is required for screen readers for the visually impaired.</span></span>

<span data-ttu-id="d5379-191">As imagens devem ser armazenadas em uma `media/<article-name>` pasta dentro da pasta que contém o artigo.</span><span class="sxs-lookup"><span data-stu-id="d5379-191">Images should be stored in a `media/<article-name>` folder within the folder containing the article.</span></span>
<span data-ttu-id="d5379-192">Não compartilhe imagens entre artigos.</span><span class="sxs-lookup"><span data-stu-id="d5379-192">Don't share images between articles.</span></span> <span data-ttu-id="d5379-193">Crie uma pasta que corresponda ao nome de arquivo do artigo na pasta `media`.</span><span class="sxs-lookup"><span data-stu-id="d5379-193">Create a folder that matches the filename of your article under the `media` folder.</span></span> <span data-ttu-id="d5379-194">Copie as imagens desse artigo para essa nova pasta.</span><span class="sxs-lookup"><span data-stu-id="d5379-194">Copy the images for that article to that new folder.</span></span> <span data-ttu-id="d5379-195">Se uma imagem for usada por vários artigos, cada pasta de imagem precisará ter uma cópia desse arquivo de imagem.</span><span class="sxs-lookup"><span data-stu-id="d5379-195">If an image is used by multiple articles, each image folder must have a copy of that image file.</span></span> <span data-ttu-id="d5379-196">Essa prática impede uma alteração em uma imagem de um artigo que afete outro artigo.</span><span class="sxs-lookup"><span data-stu-id="d5379-196">This practice prevents a change to an image in one article affecting another article.</span></span>

<span data-ttu-id="d5379-197">Há suporte para os seguintes tipos de arquivo de imagem:,,, `*.png` `*.gif` `*.jpeg` `*.jpg` , `*.svg`</span><span class="sxs-lookup"><span data-stu-id="d5379-197">The following image file types are supported: `*.png`, `*.gif`, `*.jpeg`, `*.jpg`, `*.svg`</span></span>

### <a name="markdown-extensions-supported-by-open-publishing"></a><span data-ttu-id="d5379-198">Extensões de Markdown com suporte por Open Publishing</span><span class="sxs-lookup"><span data-stu-id="d5379-198">Markdown extensions supported by Open Publishing</span></span>

<span data-ttu-id="d5379-199">O [pacote de criação do Microsoft docs](/contribute/how-to-write-docs-auth-pack) contém ferramentas que dão suporte a recursos exclusivos do nosso sistema de publicação.</span><span class="sxs-lookup"><span data-stu-id="d5379-199">The [Microsoft Docs Authoring Pack](/contribute/how-to-write-docs-auth-pack) contains tools that support features unique to our publishing system.</span></span> <span data-ttu-id="d5379-200">Alertas são uma extensão de redução para criar Blockquotes que são renderizadas em docs.microsoft.com com cores e ícones que realçam o significado do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="d5379-200">Alerts are a Markdown extension to create blockquotes that render on docs.microsoft.com with colors and icons that highlight the significance of the content.</span></span> <span data-ttu-id="d5379-201">Os seguintes tipos de alerta tem suporte:</span><span class="sxs-lookup"><span data-stu-id="d5379-201">The following alert types are supported:</span></span>

```markdown
> [!NOTE]
> Information the user should notice even if skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]
> Essential information required for user success.

> [!CAUTION]
> Negative potential consequences of an action.

> [!WARNING]
> Dangerous certain consequences of an action.
```

<span data-ttu-id="d5379-202">Esses alertas terão a seguinte aparência no docs.microsoft.com:</span><span class="sxs-lookup"><span data-stu-id="d5379-202">These alerts look like this on docs.microsoft.com:</span></span>

<span data-ttu-id="d5379-203">Bloco de observação</span><span class="sxs-lookup"><span data-stu-id="d5379-203">Note block</span></span>

> [!NOTE]
> <span data-ttu-id="d5379-204">Information the user should notice even if skimming.</span><span class="sxs-lookup"><span data-stu-id="d5379-204">Information the user should notice even if skimming.</span></span>

<span data-ttu-id="d5379-205">Bloco Tip</span><span class="sxs-lookup"><span data-stu-id="d5379-205">Tip block</span></span>

> [!TIP]
> <span data-ttu-id="d5379-206">Optional information to help a user be more successful.</span><span class="sxs-lookup"><span data-stu-id="d5379-206">Optional information to help a user be more successful.</span></span>

<span data-ttu-id="d5379-207">Bloco importante</span><span class="sxs-lookup"><span data-stu-id="d5379-207">Important block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d5379-208">Essential information required for user success.</span><span class="sxs-lookup"><span data-stu-id="d5379-208">Essential information required for user success.</span></span>

<span data-ttu-id="d5379-209">Bloqueio de cuidado</span><span class="sxs-lookup"><span data-stu-id="d5379-209">Caution block</span></span>

> [!CAUTION]
> <span data-ttu-id="d5379-210">Negative potential consequences of an action.</span><span class="sxs-lookup"><span data-stu-id="d5379-210">Negative potential consequences of an action.</span></span>

<span data-ttu-id="d5379-211">Bloco de aviso</span><span class="sxs-lookup"><span data-stu-id="d5379-211">Warning block</span></span>

> [!WARNING]
> <span data-ttu-id="d5379-212">Determinadas consequências perigosas de uma ação.</span><span class="sxs-lookup"><span data-stu-id="d5379-212">Dangerous certain consequences of an action.</span></span>

### <a name="hyperlinks"></a><span data-ttu-id="d5379-213">Hiperlinks</span><span class="sxs-lookup"><span data-stu-id="d5379-213">Hyperlinks</span></span>

- <span data-ttu-id="d5379-214">Os hiperlinks devem usar a sintaxe de redução `[friendlyname](url-or-path)` .</span><span class="sxs-lookup"><span data-stu-id="d5379-214">Hyperlinks must use Markdown syntax `[friendlyname](url-or-path)`.</span></span> <span data-ttu-id="d5379-215">Há suporte para [referências de link][linkref] .</span><span class="sxs-lookup"><span data-stu-id="d5379-215">[Link references][linkref] are supported.</span></span>
- <span data-ttu-id="d5379-216">O sistema de publicação dá suporte a três tipos de links:</span><span class="sxs-lookup"><span data-stu-id="d5379-216">The publishing system supports three types of links:</span></span>
  - <span data-ttu-id="d5379-217">Links de URL</span><span class="sxs-lookup"><span data-stu-id="d5379-217">URL links</span></span>
  - <span data-ttu-id="d5379-218">Links de arquivo</span><span class="sxs-lookup"><span data-stu-id="d5379-218">File links</span></span>
  - <span data-ttu-id="d5379-219">Links de referência cruzada</span><span class="sxs-lookup"><span data-stu-id="d5379-219">Cross-reference links</span></span>
- <span data-ttu-id="d5379-220">Links para outros artigos em docs.microsoft.com devem ser caminhos relativos a sites</span><span class="sxs-lookup"><span data-stu-id="d5379-220">Links to other articles on docs.microsoft.com must be site-relative paths</span></span>
- <span data-ttu-id="d5379-221">Todas as URLs para sites externos devem usar HTTPS, a menos que não seja válido para o site de destino.</span><span class="sxs-lookup"><span data-stu-id="d5379-221">All URLs to external websites should use HTTPS unless that isn't valid for the target site.</span></span>
- <span data-ttu-id="d5379-222">Os links devem ter um nome amigável, geralmente o título do artigo vinculado</span><span class="sxs-lookup"><span data-stu-id="d5379-222">Links must have a friendly name, usually the title of the linked article</span></span>
- <span data-ttu-id="d5379-223">Todos os itens na seção _links relacionados_ na parte inferior devem ser hiperlinks</span><span class="sxs-lookup"><span data-stu-id="d5379-223">All items in the _Related links_ section at the bottom should be hyperlinked</span></span>
- <span data-ttu-id="d5379-224">Não use marcas de escala, negrito ou outra marcação dentro dos colchetes de um hiperlink.</span><span class="sxs-lookup"><span data-stu-id="d5379-224">Don't use backticks, bold, or other markup inside the brackets of a hyperlink.</span></span>
- <span data-ttu-id="d5379-225">URLs Bare podem ser usadas quando você está documentando um URI específico.</span><span class="sxs-lookup"><span data-stu-id="d5379-225">Bare URLs may be used when you're documenting a specific URI.</span></span> <span data-ttu-id="d5379-226">O URI deve ser colocado entre tiques.</span><span class="sxs-lookup"><span data-stu-id="d5379-226">The URI must be enclosed in backticks.</span></span> <span data-ttu-id="d5379-227">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d5379-227">For example:</span></span>

  ```markdown
  By default, if you don't specify this parameter, the DMTF standard resource URI
  `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.
  ```

#### <a name="linking-to-other-content-on-docsmicrosoftcom"></a><span data-ttu-id="d5379-228">Vinculando a outro conteúdo no docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d5379-228">Linking to other content on docs.microsoft.com</span></span>

- <span data-ttu-id="d5379-229">**Links de URL** para outros artigos em docs.Microsoft.com devem ser caminhos relativos a sites.</span><span class="sxs-lookup"><span data-stu-id="d5379-229">**URL links** to other articles on docs.microsoft.com must be site-relative paths.</span></span> <span data-ttu-id="d5379-230">A maneira mais simples de criar um link relativo é copiar a URL do navegador e, em seguida, remover `https://docs.microsoft.com/en-us` do valor que você colar em redução.</span><span class="sxs-lookup"><span data-stu-id="d5379-230">The simplest way to create a relative link is to copy the URL from your browser then remove `https://docs.microsoft.com/en-us` from the value you paste into markdown.</span></span> <span data-ttu-id="d5379-231">Não inclua localidades em URLs nas propriedades da Microsoft (remover `/en-us` da URL).</span><span class="sxs-lookup"><span data-stu-id="d5379-231">Don't include locales in URLs on Microsoft properties (remove `/en-us` from URL).</span></span> <span data-ttu-id="d5379-232">Remova os parâmetros de consulta desnecessários da URL.</span><span class="sxs-lookup"><span data-stu-id="d5379-232">Remove any unnecessary query parameters from the URL.</span></span> <span data-ttu-id="d5379-233">Exemplos que devem ser removidos:</span><span class="sxs-lookup"><span data-stu-id="d5379-233">Examples that should be removed:</span></span>

  - <span data-ttu-id="d5379-234">`?view=powershell-5.1` -usado para vincular a uma versão específica do PowerShell</span><span class="sxs-lookup"><span data-stu-id="d5379-234">`?view=powershell-5.1` - used to link to a specific version of PowerShell</span></span>
  - <span data-ttu-id="d5379-235">`?redirectedfrom=MSDN` -adicionado à URL quando você é Redirecionado de um artigo antigo para seu novo local</span><span class="sxs-lookup"><span data-stu-id="d5379-235">`?redirectedfrom=MSDN` - added to the URL when you get redirected from an old article to its new location</span></span>

  <span data-ttu-id="d5379-236">Se você precisar vincular a uma versão específica de um documento, precisará adicionar o `&preserve_view=true` parâmetro à cadeia de caracteres de consulta.</span><span class="sxs-lookup"><span data-stu-id="d5379-236">If you need to link to a specific version of a document, then you need to add the `&preserve_view=true` parameter to the query string.</span></span> <span data-ttu-id="d5379-237">Por exemplo: `?view=powershell-5.1&preserve_view=true`</span><span class="sxs-lookup"><span data-stu-id="d5379-237">For example: `?view=powershell-5.1&preserve_view=true`</span></span>

- <span data-ttu-id="d5379-238">Um **link de arquivo** é usado para vincular de um artigo de referência a outro, ou de um artigo conceitual para outro.</span><span class="sxs-lookup"><span data-stu-id="d5379-238">A **file link** is used to link from one reference article to another, or from one conceptual article to another.</span></span> <span data-ttu-id="d5379-239">Se você precisar vincular a um artigo de referência para uma versão específica do PowerShell, deverá usar um link de URL.</span><span class="sxs-lookup"><span data-stu-id="d5379-239">If you need to link to a reference article for a specific version of PowerShell, then you must use a URL link.</span></span>

  - <span data-ttu-id="d5379-240">Os links de arquivo contêm um caminho de arquivo relativo (por exemplo: `../folder/file.md` )</span><span class="sxs-lookup"><span data-stu-id="d5379-240">File links contain a relative file path (for example: `../folder/file.md`)</span></span>
  - <span data-ttu-id="d5379-241">Todos os caminhos de arquivo usam caracteres de barra ( `/` )</span><span class="sxs-lookup"><span data-stu-id="d5379-241">All file paths use forward-slash (`/`) characters</span></span>

- <span data-ttu-id="d5379-242">**Links de referência cruzada** são um recurso especial suportado pelo sistema de publicação.</span><span class="sxs-lookup"><span data-stu-id="d5379-242">**Cross-reference links** are a special feature supported by the publishing system.</span></span> <span data-ttu-id="d5379-243">Você pode usar links de referência cruzada em artigos conceituais para vincular a API .NET ou referência de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d5379-243">You can use cross-reference links in conceptual articles to link to .NET API or cmdlet reference.</span></span>

  <span data-ttu-id="d5379-244">Para obter links para a referência da API do .NET, consulte [usar links na documentação](/contribute/how-to-write-links#xref-cross-reference-links) no guia do colaborador central.</span><span class="sxs-lookup"><span data-stu-id="d5379-244">For links to .NET API reference, see [Use links in documentation](/contribute/how-to-write-links#xref-cross-reference-links) in the central Contributor Guide.</span></span>

  <span data-ttu-id="d5379-245">Links para referência de cmdlet têm o seguinte formato: `xref:<module-name>.<cmdlet-name>` .</span><span class="sxs-lookup"><span data-stu-id="d5379-245">Links to cmdlet reference have the following format: `xref:<module-name>.<cmdlet-name>`.</span></span> <span data-ttu-id="d5379-246">Por exemplo, para vincular o `Get-Content` cmdlet no módulo **Microsoft. PowerShell. Management** .</span><span class="sxs-lookup"><span data-stu-id="d5379-246">For example, to link to the `Get-Content` cmdlet in the **Microsoft.PowerShell.Management** module.</span></span>

  `[Get-Content](xref:Microsoft.PowerShell.Management.Get-Content)`

<span data-ttu-id="d5379-247">A vinculação profunda é permitida em links de URL e de arquivo.</span><span class="sxs-lookup"><span data-stu-id="d5379-247">Deep linking is allowed on both URL and file links.</span></span> <span data-ttu-id="d5379-248">Adicione a âncora ao final do caminho de destino.</span><span class="sxs-lookup"><span data-stu-id="d5379-248">Add the anchor to the end of the target path.</span></span>
<span data-ttu-id="d5379-249">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d5379-249">For example:</span></span>

- `[about_Splatting](about_Splatting.md#splatting-with-arrays)`
- `[custom key bindings](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings)`

<span data-ttu-id="d5379-250">Para obter mais informações, consulte [usar links na documentação](/contribute/how-to-write-links).</span><span class="sxs-lookup"><span data-stu-id="d5379-250">For more information, see [Use links in documentation](/contribute/how-to-write-links).</span></span>

## <a name="formatting-command-syntax-elements"></a><span data-ttu-id="d5379-251">Como formatar elementos da sintaxe de comando</span><span class="sxs-lookup"><span data-stu-id="d5379-251">Formatting command syntax elements</span></span>

- <span data-ttu-id="d5379-252">Sempre use o nome completo para cmdlets e parâmetros.</span><span class="sxs-lookup"><span data-stu-id="d5379-252">Always use the full name for cmdlets and parameters.</span></span> <span data-ttu-id="d5379-253">Evite usar aliases, a menos que você esteja demonstrando especificamente o alias.</span><span class="sxs-lookup"><span data-stu-id="d5379-253">Avoid using aliases unless you're specifically demonstrating the alias.</span></span>

- <span data-ttu-id="d5379-254">Propriedade, parâmetro, objeto, nomes de tipo, nomes de classe, métodos de classe devem estar em **negrito**.</span><span class="sxs-lookup"><span data-stu-id="d5379-254">Property, parameter, object, type names, class names, class methods should be **bold**.</span></span>
  - <span data-ttu-id="d5379-255">Os valores de propriedade e parâmetro devem ser encapsulados em acentos ( `` ` `` ).</span><span class="sxs-lookup"><span data-stu-id="d5379-255">Property and parameter values should be wrapped in backticks (`` ` ``).</span></span>
  - <span data-ttu-id="d5379-256">Ao fazer referência a tipos usando o estilo entre colchetes, use marcas de escala.</span><span class="sxs-lookup"><span data-stu-id="d5379-256">When referring to types using the bracketed style, use backticks.</span></span> <span data-ttu-id="d5379-257">Por exemplo: `[System.Io.FileInfo]`</span><span class="sxs-lookup"><span data-stu-id="d5379-257">For example: `[System.Io.FileInfo]`</span></span>

- <span data-ttu-id="d5379-258">Palavras-chave de idioma, nomes de cmdlet, funções, variáveis, EXEs nativos, caminhos de arquivo e exemplos de sintaxe embutida devem ser encapsulados em caracteres de acento grave ( `` ` `` ).</span><span class="sxs-lookup"><span data-stu-id="d5379-258">Language keywords, cmdlet names, functions, variables, native EXEs, file paths, and inline syntax examples should be wrapped in backtick (`` ` ``) characters.</span></span>

  <span data-ttu-id="d5379-259">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d5379-259">For example:</span></span>

  ~~~markdown
  The following code uses `Get-ChildItem` to list the contents of `C:\Windows` and assigns
  the output to the `$files` variable.

  ```powershell
  $files = Get-ChildItem C:\Windows
  ```
  ~~~

  - <span data-ttu-id="d5379-260">Ao referenciar um parâmetro pelo nome, o nome deve estar em **negrito**.</span><span class="sxs-lookup"><span data-stu-id="d5379-260">When referring to a parameter by name, the name should be **bold**.</span></span> <span data-ttu-id="d5379-261">Ao ilustrar o uso de um parâmetro com o prefixo de hífen, o parâmetro deve ser encapsulado em acentos graves.</span><span class="sxs-lookup"><span data-stu-id="d5379-261">When illustrating the use of a parameter with the hyphen prefix, the parameter should be wrapped in backticks.</span></span> <span data-ttu-id="d5379-262">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d5379-262">For example:</span></span>

    ```markdown
    The parameter's name is **Name**, but it's typed as `-Name` when used on the command
    line as a parameter.
    ```

  - <span data-ttu-id="d5379-263">Ao mostrar o uso de exemplo de um comando externo, o exemplo deve ser encapsulado em acentos graves.</span><span class="sxs-lookup"><span data-stu-id="d5379-263">When showing example usage of an external command, the example should be wrapped in backticks.</span></span>
    <span data-ttu-id="d5379-264">Inclua sempre a extensão de arquivo no comando nativo.</span><span class="sxs-lookup"><span data-stu-id="d5379-264">Always include the file extension in the native command.</span></span> <span data-ttu-id="d5379-265">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d5379-265">For example:</span></span>

    ```markdown
    To start the spooler service on a remote computer named DC01, you type `sc.exe \\DC01 start spooler`.
    ```

    <span data-ttu-id="d5379-266">A inclusão da extensão de arquivo garante que o comando correto seja executado de acordo com a precedência de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5379-266">Including the file extension ensures that the correct command is executed according to PowerShell's command precedence.</span></span>

- <span data-ttu-id="d5379-267">Ao redigir um artigo conceitual (em comparação com um conteúdo de referência), a primeira instância de um nome de cmdlet deve ser vinculada à documentação do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d5379-267">When writing a conceptual article (as opposed to reference content), the first instance of a cmdlet name should be hyperlinked to the cmdlet documentation.</span></span> <span data-ttu-id="d5379-268">Não use marcas de escala, negrito ou outra marcação dentro dos colchetes de um hiperlink.</span><span class="sxs-lookup"><span data-stu-id="d5379-268">Don't use backticks, bold, or other markup inside the brackets of a hyperlink.</span></span>

  <span data-ttu-id="d5379-269">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d5379-269">For example:</span></span>

  ```markdown
  This [Write-Host](/powershell/module/Microsoft.PowerShell.Utility/Write-Host) cmdlet
  uses the **Object** parameter to ...
  ```

  <span data-ttu-id="d5379-270">Para obter mais informações, consulte a seção [hiperlinks](#hyperlinks) deste artigo.</span><span class="sxs-lookup"><span data-stu-id="d5379-270">For more information, see [Hyperlinks](#hyperlinks) section of this article.</span></span>

## <a name="markdown-for-code-samples"></a><span data-ttu-id="d5379-271">Redução para exemplos de código</span><span class="sxs-lookup"><span data-stu-id="d5379-271">Markdown for code samples</span></span>

<span data-ttu-id="d5379-272">O Markdown dá suporte a dois estilos de código diferentes:</span><span class="sxs-lookup"><span data-stu-id="d5379-272">Markdown supports two different code styles:</span></span>

- <span data-ttu-id="d5379-273">**Trechos de código (embutidos)** – marcados por um único caractere de acento grave ( `` ` `` ).</span><span class="sxs-lookup"><span data-stu-id="d5379-273">**Code spans (inline)** - marked by a single backtick (`` ` ``) character.</span></span> <span data-ttu-id="d5379-274">Usado em um parágrafo em vez de como um bloco autônomo.</span><span class="sxs-lookup"><span data-stu-id="d5379-274">Used within a paragraph rather than as a standalone block.</span></span>
- <span data-ttu-id="d5379-275">**Blocos de código** : um bloco de várias linhas circundado por cadeias de caracteres de backtick ( `` ``` `` ).</span><span class="sxs-lookup"><span data-stu-id="d5379-275">**Code blocks** - a multi-line block surrounded by triple-backtick (`` ``` ``) strings.</span></span> <span data-ttu-id="d5379-276">Os blocos de código também podem ter um rótulo de idioma após as marcas de fim.</span><span class="sxs-lookup"><span data-stu-id="d5379-276">Code blocks may also have a language label following the backticks.</span></span> <span data-ttu-id="d5379-277">O rótulo de idioma habilita o realce de sintaxe para o conteúdo do bloco de código.</span><span class="sxs-lookup"><span data-stu-id="d5379-277">The language label enables syntax highlighting for the contents of the code block.</span></span>

<span data-ttu-id="d5379-278">Todos os blocos de código devem estar contidos em um limite de código.</span><span class="sxs-lookup"><span data-stu-id="d5379-278">All code blocks should be contained in a code fence.</span></span> <span data-ttu-id="d5379-279">Nunca use recuo para blocos de código.</span><span class="sxs-lookup"><span data-stu-id="d5379-279">Never use indentation for code blocks.</span></span> <span data-ttu-id="d5379-280">A redução permite esse padrão, mas pode ser problemática e deve ser evitada.</span><span class="sxs-lookup"><span data-stu-id="d5379-280">Markdown allows this pattern but it can be problematic and should be avoided.</span></span>

<span data-ttu-id="d5379-281">Um bloco de código é uma ou mais linhas de código circundadas por um limite de código de tiques ( `` ``` `` ) triplo.</span><span class="sxs-lookup"><span data-stu-id="d5379-281">A code block is one or more lines of code surrounded by a triple-backtick (`` ``` ``) code fence.</span></span>
<span data-ttu-id="d5379-282">Os marcadores do limite de código precisam estar em sua própria linha antes e depois do exemplo de código.</span><span class="sxs-lookup"><span data-stu-id="d5379-282">The code fence markers must be on their own line before and after the code sample.</span></span> <span data-ttu-id="d5379-283">O marcador no início do bloco de código pode ter um rótulo de linguagem opcional.</span><span class="sxs-lookup"><span data-stu-id="d5379-283">The marker at the start of the code block may have an optional language label.</span></span> <span data-ttu-id="d5379-284">O OPS (Open Publishing System) da Microsoft usa o rótulo de linguagem para dar suporte ao recurso de realce de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="d5379-284">Microsoft's Open Publishing System (OPS) uses the language label to support the syntax highlighting feature.</span></span>

<span data-ttu-id="d5379-285">Para obter uma lista completa de marcas de idioma com suporte, consulte [blocos de código em grade](/contribute/code-in-docs#fenced-code-blocks) no guia do colaborador centralizado.</span><span class="sxs-lookup"><span data-stu-id="d5379-285">For a full list of supported language tags, see [Fenced code blocks](/contribute/code-in-docs#fenced-code-blocks) in the centralized contributor guide.</span></span>

<span data-ttu-id="d5379-286">O OPS também adiciona um botão **Copiar** que copia o conteúdo do bloco de código para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="d5379-286">OPS also adds a **Copy** button that copies the contents of the code block to the clipboard.</span></span> <span data-ttu-id="d5379-287">Isso permite que você cole rapidamente o código em um script para testar o exemplo de código.</span><span class="sxs-lookup"><span data-stu-id="d5379-287">This allows you to quickly paste the code into a script to test the code sample.</span></span> <span data-ttu-id="d5379-288">No entanto, nem todos os exemplos em nossa documentação devem ser executados no estado em que se encontram.</span><span class="sxs-lookup"><span data-stu-id="d5379-288">However, not all examples in our documentation are intended to be run as-is.</span></span> <span data-ttu-id="d5379-289">Alguns blocos de código são ilustrações simples de um conceito do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5379-289">Some code blocks are simple illustrations of a PowerShell concept.</span></span>

<span data-ttu-id="d5379-290">Há três tipos de blocos de código usados em nossa documentação:</span><span class="sxs-lookup"><span data-stu-id="d5379-290">There are three types code blocks used in our documentation:</span></span>

1. <span data-ttu-id="d5379-291">Blocos de sintaxe</span><span class="sxs-lookup"><span data-stu-id="d5379-291">Syntax blocks</span></span>
1. <span data-ttu-id="d5379-292">Exemplos ilustrativos</span><span class="sxs-lookup"><span data-stu-id="d5379-292">Illustrative examples</span></span>
1. <span data-ttu-id="d5379-293">Exemplos executáveis</span><span class="sxs-lookup"><span data-stu-id="d5379-293">Executable examples</span></span>

### <a name="syntax-code-blocks"></a><span data-ttu-id="d5379-294">Blocos de código de sintaxe</span><span class="sxs-lookup"><span data-stu-id="d5379-294">Syntax code blocks</span></span>

<span data-ttu-id="d5379-295">Os blocos de código de sintaxe são usados para descrever a estrutura sintática de um comando.</span><span class="sxs-lookup"><span data-stu-id="d5379-295">Syntax code blocks are used to describe the syntactic structure of a command.</span></span> <span data-ttu-id="d5379-296">Não use uma marca de idioma no limite de código.</span><span class="sxs-lookup"><span data-stu-id="d5379-296">Don't use a language tag on the code fence.</span></span> <span data-ttu-id="d5379-297">Este exemplo ilustra todos os parâmetros possíveis do cmdlet `Get-Command`.</span><span class="sxs-lookup"><span data-stu-id="d5379-297">This example illustrates all the possible parameters of the `Get-Command` cmdlet.</span></span>

~~~markdown
```
Get-Command [-Verb <String[]>] [-Noun <String[]>] [-Module <String[]>]
  [-FullyQualifiedModule <ModuleSpecification[]>] [-TotalCount <Int32>] [-Syntax]
  [-ShowCommandInfo] [[-ArgumentList] <Object[]>] [-All] [-ListImported]
  [-ParameterName <String[]>] [-ParameterType <PSTypeName[]>] [<CommonParameters>]
```
~~~

<span data-ttu-id="d5379-298">Este exemplo descreve a instrução `for` em termos generalizados:</span><span class="sxs-lookup"><span data-stu-id="d5379-298">This example describes the `for` statement in generalized terms:</span></span>

~~~markdown
```
for (<init>; <condition>; <repeat>)
{<statement list>}
```
~~~

### <a name="illustrative-examples"></a><span data-ttu-id="d5379-299">Exemplos ilustrativos</span><span class="sxs-lookup"><span data-stu-id="d5379-299">Illustrative examples</span></span>

<span data-ttu-id="d5379-300">Os exemplos ilustrativos são usados para explicar um conceito do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5379-300">Illustrative examples are used to explain a PowerShell concept.</span></span> <span data-ttu-id="d5379-301">Eles não devem ser copiados para a área de transferência para execução.</span><span class="sxs-lookup"><span data-stu-id="d5379-301">They aren't meant to be copied to the clipboard for execution.</span></span> <span data-ttu-id="d5379-302">Esses são mais comumente usados para exemplos simples que são fáceis de digitar e fáceis de entender.</span><span class="sxs-lookup"><span data-stu-id="d5379-302">These are most commonly used for simple examples that are easy to type and easy to understand.</span></span> <span data-ttu-id="d5379-303">O bloco de código pode incluir o prompt do PowerShell e o exemplo de saída.</span><span class="sxs-lookup"><span data-stu-id="d5379-303">The code block can include the PowerShell prompt and example output.</span></span>

<span data-ttu-id="d5379-304">Veja um exemplo simples que ilustra os operadores de comparação do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5379-304">Here's a simple example illustrating the PowerShell comparison operators.</span></span> <span data-ttu-id="d5379-305">Nesse caso, não pretendemos que o leitor copie e execute este exemplo.</span><span class="sxs-lookup"><span data-stu-id="d5379-305">In this case, we don't intend the reader to copy and run this example.</span></span>

~~~markdown
```powershell
PS> 2 -eq 2
True

PS> 2 -eq 3
False

PS> 1,2,3 -eq 2
2

PS> "abc" -eq "abc"
True

PS> "abc" -eq "abc", "def"
False

PS> "abc", "def" -eq "abc"
abc
```
~~~

### <a name="executable-examples"></a><span data-ttu-id="d5379-306">Exemplos executáveis</span><span class="sxs-lookup"><span data-stu-id="d5379-306">Executable examples</span></span>

<span data-ttu-id="d5379-307">Exemplos complexos, ou exemplos que devem ser copiados e executados, devem usar a seguinte marcação de estilo de bloco:</span><span class="sxs-lookup"><span data-stu-id="d5379-307">Complex examples, or examples that are intended to be copied and executed, should use the following block-style markup:</span></span>

~~~markdown
```powershell
<Your PowerShell code goes here>
```
~~~

<span data-ttu-id="d5379-308">A saída exibida pelos comandos do PowerShell deve ser colocada em um bloco de código **Saída** para evitar o realce de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="d5379-308">The output displayed by PowerShell commands should be enclosed in an **Output** code block to prevent syntax highlighting.</span></span> <span data-ttu-id="d5379-309">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d5379-309">For example:</span></span>

~~~markdown
```powershell
Get-Command -Module Microsoft.PowerShell.Security
```

```Output
CommandType  Name                        Version    Source
-----------  ----                        -------    ------
Cmdlet       ConvertFrom-SecureString    3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       ConvertTo-SecureString      3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-Acl                     3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-AuthenticodeSignature   3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-CmsMessage              3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-Credential              3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-ExecutionPolicy         3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-PfxCertificate          3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       New-FileCatalog             3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Protect-CmsMessage          3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Set-Acl                     3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Set-AuthenticodeSignature   3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Set-ExecutionPolicy         3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Test-FileCatalog            3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Unprotect-CmsMessage        3.0.0.0    Microsoft.PowerShell.Security
```
~~~

<span data-ttu-id="d5379-310">O rótulo do código de **saída** não é um "idioma" oficial com suporte no sistema de realce de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="d5379-310">The **Output** code label isn't an official "language" supported by the syntax highlighting system.</span></span>
<span data-ttu-id="d5379-311">No entanto, esse rótulo é útil porque o OPS adiciona o rótulo "saída" ao quadro da caixa de código na página da Web.</span><span class="sxs-lookup"><span data-stu-id="d5379-311">However, this label is useful because OPS adds the "Output" label to the code box frame on the web page.</span></span> <span data-ttu-id="d5379-312">A caixa de código "saída" não tem realce de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="d5379-312">The "Output" code box has no syntax highlighting.</span></span>

## <a name="coding-style-rules"></a><span data-ttu-id="d5379-313">Regras de estilo de codificação</span><span class="sxs-lookup"><span data-stu-id="d5379-313">Coding style rules</span></span>

### <a name="avoid-line-continuation-in-code-samples"></a><span data-ttu-id="d5379-314">Evite a continuação de linha em exemplos de código</span><span class="sxs-lookup"><span data-stu-id="d5379-314">Avoid line continuation in code samples</span></span>

<span data-ttu-id="d5379-315">Evite usar caracteres de continuação de linha (`` ` ``) em exemplos de código do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5379-315">Avoid using line continuation characters (`` ` ``) in PowerShell code examples.</span></span> <span data-ttu-id="d5379-316">Eles são difíceis de serem vistos e podem causar problemas se há espaços extras no final da linha.</span><span class="sxs-lookup"><span data-stu-id="d5379-316">These are hard to see and can cause problems if there are extra spaces at the end of the line.</span></span>

- <span data-ttu-id="d5379-317">Use o nivelamento do PowerShell para reduzir o tamanho da linha para cmdlets que têm vários parâmetros.</span><span class="sxs-lookup"><span data-stu-id="d5379-317">Use PowerShell splatting to reduce line length for cmdlets that have several parameters.</span></span>
- <span data-ttu-id="d5379-318">Aproveite as oportunidades de quebra de linha natural do PowerShell, como após os caracteres de pipe ( `|` ), chaves de abertura ( `{` ), parênteses ( `(` ) e colchetes ( `[` ).</span><span class="sxs-lookup"><span data-stu-id="d5379-318">Take advantage of PowerShell's natural line break opportunities, like after pipe (`|`) characters, opening braces (`{`), parentheses (`(`), and brackets (`[`).</span></span>

### <a name="avoid-using-powershell-prompts-in-examples"></a><span data-ttu-id="d5379-319">Evite usar avisos do PowerShell em exemplos</span><span class="sxs-lookup"><span data-stu-id="d5379-319">Avoid using PowerShell prompts in examples</span></span>

<span data-ttu-id="d5379-320">O uso da cadeia de caracteres de prompt é desencorajado e deve ser limitado a cenários que se destinam a ilustrar o uso da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="d5379-320">Use of the prompt string is discouraged and should be limited to scenarios that are meant to illustrate command-line usage.</span></span> <span data-ttu-id="d5379-321">Para a maioria desses exemplos, a cadeia de caracteres do prompt deve ser `PS>` .</span><span class="sxs-lookup"><span data-stu-id="d5379-321">For most of these examples, the prompt string should be `PS>`.</span></span> <span data-ttu-id="d5379-322">Esse aviso é independente dos indicadores específicos do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="d5379-322">This prompt is independent of OS-specific indicators.</span></span>

<span data-ttu-id="d5379-323">Os prompts são necessários em exemplos para ilustrar comandos que alteram o prompt ou quando o caminho exibido é significativo para o cenário.</span><span class="sxs-lookup"><span data-stu-id="d5379-323">Prompts are required in examples to illustrate commands that alter the prompt or when the path displayed is significant to the scenario.</span></span> <span data-ttu-id="d5379-324">O exemplo a seguir ilustra como o aviso é alterado ao usar o provedor do Registro.</span><span class="sxs-lookup"><span data-stu-id="d5379-324">The following example illustrates how the prompt changes when using the Registry provider.</span></span>

```powershell
PS C:\> cd HKCU:\System\
PS HKCU:\System\> dir

    Hive: HKEY_CURRENT_USER\System

Name                   Property
----                   --------
CurrentControlSet
GameConfigStore        GameDVR_Enabled                       : 1
                       GameDVR_FSEBehaviorMode               : 2
                       Win32_AutoGameModeDefaultProfile      : {2, 0, 1, 0...}
                       Win32_GameModeRelatedProcesses        : {1, 0, 1, 0...}
                       GameDVR_HonorUserFSEBehaviorMode      : 0
                       GameDVR_DXGIHonorFSEWindowsCompatible : 0
```

### <a name="dont-use-aliases-in-examples"></a><span data-ttu-id="d5379-325">Não use aliases em exemplos</span><span class="sxs-lookup"><span data-stu-id="d5379-325">Don't use aliases in examples</span></span>

<span data-ttu-id="d5379-326">Use o nome completo de todos os cmdlets e parâmetros, a menos que você esteja documentando especificamente o alias.</span><span class="sxs-lookup"><span data-stu-id="d5379-326">Use the full name of all cmdlets and parameters unless you're specifically documenting the alias.</span></span>
<span data-ttu-id="d5379-327">Os nomes de cmdlet e parâmetro devem usar os nomes de [Pascal-case][] apropriados.</span><span class="sxs-lookup"><span data-stu-id="d5379-327">Cmdlet and parameter names must use the proper [Pascal-cased][] names.</span></span>

### <a name="using-parameters-in-examples"></a><span data-ttu-id="d5379-328">Como usar parâmetros em exemplos</span><span class="sxs-lookup"><span data-stu-id="d5379-328">Using parameters in examples</span></span>

<span data-ttu-id="d5379-329">Evite usar parâmetros posicionais.</span><span class="sxs-lookup"><span data-stu-id="d5379-329">Avoid using positional parameters.</span></span> <span data-ttu-id="d5379-330">Em geral, você deve sempre incluir o nome do parâmetro em um exemplo, mesmo que o parâmetro seja posicional.</span><span class="sxs-lookup"><span data-stu-id="d5379-330">In general, you should always include the parameter name in an example, even if the parameter is positional.</span></span> <span data-ttu-id="d5379-331">Isso reduz a chance de confusão em seus exemplos.</span><span class="sxs-lookup"><span data-stu-id="d5379-331">This reduces the chance of confusion in your examples.</span></span>

## <a name="formatting-cmdlet-reference-articles"></a><span data-ttu-id="d5379-332">Artigos de referência de cmdlets de formatação</span><span class="sxs-lookup"><span data-stu-id="d5379-332">Formatting cmdlet reference articles</span></span>

<span data-ttu-id="d5379-333">Os artigos de referência de cmdlet têm uma estrutura específica.</span><span class="sxs-lookup"><span data-stu-id="d5379-333">Cmdlet reference articles have a specific structure.</span></span> <span data-ttu-id="d5379-334">Essa estrutura é definida pelo [PlatyPS][].</span><span class="sxs-lookup"><span data-stu-id="d5379-334">This structure is defined by [PlatyPS][].</span></span>
<span data-ttu-id="d5379-335">PlatyPS gera a ajuda do cmdlet para módulos do PowerShell em redução.</span><span class="sxs-lookup"><span data-stu-id="d5379-335">PlatyPS generates the cmdlet help for PowerShell modules in Markdown.</span></span> <span data-ttu-id="d5379-336">Depois de editar os arquivos markdown, o PlatyPS é usado para criar os arquivos de ajuda do MAML usados pelo cmdlet `Get-Help`.</span><span class="sxs-lookup"><span data-stu-id="d5379-336">After editing the Markdown files, PlatyPS is used create the MAML help files used by the `Get-Help` cmdlet.</span></span>

<span data-ttu-id="d5379-337">O PlatyPS tem um esquema embutido em código para a referência de cmdlet que é gravado no código.</span><span class="sxs-lookup"><span data-stu-id="d5379-337">PlatyPS has a hard-coded schema for cmdlet reference that is written into the code.</span></span> <span data-ttu-id="d5379-338">O documento [platyPS.schema.md][] tenta descrever essa estrutura.</span><span class="sxs-lookup"><span data-stu-id="d5379-338">The [platyPS.schema.md][] document attempts to describe this structure.</span></span> <span data-ttu-id="d5379-339">As violações de esquema causam erros de build que precisam ser corrigidos antes que possamos aceitar sua contribuição.</span><span class="sxs-lookup"><span data-stu-id="d5379-339">Schema violations cause build errors that must be fixed before we can accept your contribution.</span></span>

- <span data-ttu-id="d5379-340">Não remova nenhuma das estruturas de cabeçalho ATX.</span><span class="sxs-lookup"><span data-stu-id="d5379-340">Don't remove any of the ATX header structures.</span></span> <span data-ttu-id="d5379-341">O PlatyPS espera um conjunto específico de cabeçalhos.</span><span class="sxs-lookup"><span data-stu-id="d5379-341">PlatyPS expects a specific set of headers.</span></span>
- <span data-ttu-id="d5379-342">Os cabeçalhos **Tipo de entrada** e **Tipo de saída** precisam ter um tipo.</span><span class="sxs-lookup"><span data-stu-id="d5379-342">The **Input type** and **Output type** headers must have a type.</span></span> <span data-ttu-id="d5379-343">Se o cmdlet não usar entrada ou retornar um valor, use o valor `None` .</span><span class="sxs-lookup"><span data-stu-id="d5379-343">If the cmdlet doesn't take input or return a value, then use the value `None`.</span></span>
- <span data-ttu-id="d5379-344">As extensões de código embutidas podem ser usadas em qualquer parágrafo.</span><span class="sxs-lookup"><span data-stu-id="d5379-344">Inline code spans can be used in any paragraph.</span></span>
- <span data-ttu-id="d5379-345">Blocos de código isolados são permitidos somente na seção de **exemplos** .</span><span class="sxs-lookup"><span data-stu-id="d5379-345">Fenced code blocks are only allowed in the **EXAMPLES** section.</span></span>

<span data-ttu-id="d5379-346">No esquema PlatyPS, **exemplos** é um cabeçalho H2.</span><span class="sxs-lookup"><span data-stu-id="d5379-346">In the PlatyPS schema, **EXAMPLES** is an H2 header.</span></span> <span data-ttu-id="d5379-347">Cada exemplo é um cabeçalho H3.</span><span class="sxs-lookup"><span data-stu-id="d5379-347">Each example is an H3 header.</span></span> <span data-ttu-id="d5379-348">Em um exemplo, o esquema não permite que os blocos de código sejam separados por parágrafos.</span><span class="sxs-lookup"><span data-stu-id="d5379-348">Within an example, the schema doesn't allow code blocks to be separated by paragraphs.</span></span> <span data-ttu-id="d5379-349">O esquema permite a seguinte estrutura:</span><span class="sxs-lookup"><span data-stu-id="d5379-349">The schema allows the following structure:</span></span>

```
### Example X - Title sentence

0 or more paragraphs
1 or more code blocks
0 or more paragraphs.
```

<span data-ttu-id="d5379-350">Numerar cada exemplo e adicionar um breve título.</span><span class="sxs-lookup"><span data-stu-id="d5379-350">Number each example and add a brief title.</span></span>

<span data-ttu-id="d5379-351">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d5379-351">For example:</span></span>

~~~markdown
### Example 1: Get cmdlets, functions, and aliases

This command gets the PowerShell cmdlets, functions, and aliases that are installed on the
computer.

```powershell
Get-Command
```

### Example 2: Get commands in the current session

```powershell
Get-Command -ListImported
```
~~~

## <a name="formatting-about_-files"></a><span data-ttu-id="d5379-352">Como formatar arquivos About_</span><span class="sxs-lookup"><span data-stu-id="d5379-352">Formatting About_ files</span></span>

<span data-ttu-id="d5379-353">`About_*` os arquivos são escritos em redução, mas são enviados como arquivos de texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="d5379-353">`About_*` files are written in Markdown but are shipped as plain text files.</span></span> <span data-ttu-id="d5379-354">Usamos [Pandoc][] para converter a redução em texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="d5379-354">We use [Pandoc][] to convert the Markdown to plain text.</span></span> <span data-ttu-id="d5379-355">`About_*` os arquivos são formatados para obter a melhor compatibilidade em todas as versões do PowerShell e com as ferramentas de publicação.</span><span class="sxs-lookup"><span data-stu-id="d5379-355">`About_*` files are formatted for the best compatibility across all versions of PowerShell and with the publishing tools.</span></span>

<span data-ttu-id="d5379-356">Diretrizes básicas de formatação:</span><span class="sxs-lookup"><span data-stu-id="d5379-356">Basic formatting guidelines:</span></span>

- <span data-ttu-id="d5379-357">Limitar as linhas normais a 80 caracteres</span><span class="sxs-lookup"><span data-stu-id="d5379-357">Limit normal lines to 80 characters</span></span>
- <span data-ttu-id="d5379-358">Os blocos de código são limitados a 76 caracteres</span><span class="sxs-lookup"><span data-stu-id="d5379-358">Code blocks are limited to 76 characters</span></span>
- <span data-ttu-id="d5379-359">Os Blockquotes (e alertas) têm 78 caracteres limitados</span><span class="sxs-lookup"><span data-stu-id="d5379-359">Blockquotes (and Alerts) are limited 78 characters</span></span>
- <span data-ttu-id="d5379-360">Ao usar esses metacaracteres especiais `\` , `$` e `<` :</span><span class="sxs-lookup"><span data-stu-id="d5379-360">When using these special meta-characters `\`,`$`, and `<`:</span></span>
  - <span data-ttu-id="d5379-361">Dentro de um cabeçalho, esses caracteres devem ser ignorados usando um caractere à esquerda `\` ou colocados em spans de código usando acentos ( `` ` `` )</span><span class="sxs-lookup"><span data-stu-id="d5379-361">Within a header, these characters must be escaped using a leading `\` character or enclosed in code spans using backticks (`` ` ``)</span></span>
  - <span data-ttu-id="d5379-362">Dentro de um parágrafo, esses caracteres devem ser colocados em spans de código.</span><span class="sxs-lookup"><span data-stu-id="d5379-362">Within a paragraph, these characters should be put into code spans.</span></span> <span data-ttu-id="d5379-363">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d5379-363">For example:</span></span>

    ~~~markdown
    ### The purpose of the \$foo variable

    The `$foo` variable is used to store ...
    ~~~

- <span data-ttu-id="d5379-364">As tabelas precisam se ajustar em 76 caracteres</span><span class="sxs-lookup"><span data-stu-id="d5379-364">Tables need to fit within 76 characters</span></span>
  - <span data-ttu-id="d5379-365">Quebre manualmente o conteúdo das células em várias linhas</span><span class="sxs-lookup"><span data-stu-id="d5379-365">Manually wrap contents of cells across multiple lines</span></span>
  - <span data-ttu-id="d5379-366">Use caracteres `|` de abertura e fechamento em cada linha</span><span class="sxs-lookup"><span data-stu-id="d5379-366">Use opening and closing `|` characters on each line</span></span>
  - <span data-ttu-id="d5379-367">O exemplo a seguir ilustra como construir corretamente uma tabela que contém informações que são encapsuladas em várias linhas dentro de uma célula.</span><span class="sxs-lookup"><span data-stu-id="d5379-367">The following example illustrates how to properly construct a table that contains information that wraps on multiple lines within a cell.</span></span>

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
    > <span data-ttu-id="d5379-368">A limitação de 76 colunas aplica-se somente a `About_*` Tópicos.</span><span class="sxs-lookup"><span data-stu-id="d5379-368">The 76-column limitation applies only to `About_*` topics.</span></span> <span data-ttu-id="d5379-369">Você pode usar colunas largas em artigos conceituais ou de referência de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d5379-369">You can use wide columns in conceptual or cmdlet reference articles.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d5379-370">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="d5379-370">Next steps</span></span>

[<span data-ttu-id="d5379-371">Lista de verificação editorial</span><span class="sxs-lookup"><span data-stu-id="d5379-371">Editorial checklist</span></span>](editorial-checklist.md)

<!-- link references -->
[atx]: https://github.github.com/gfm/#atx-headings
[CommonMark]: https://spec.commonmark.org/
[markdig]: https://github.com/lunet-io/markdig
[Pandoc]: https://pandoc.org
[Pascal-case]: https://en.wikipedia.org/wiki/PascalCase
[Pascal-cased]: https://en.wikipedia.org/wiki/PascalCase
[platyPS.schema.md]: https://github.com/PowerShell/platyPS/blob/master/platyPS.schema.md
[PlatyPS]: https://github.com/powershell/platyps
[reflow]: https://marketplace.visualstudio.com/items?itemName=marvhen.reflow-markdown
[linkref]: https://spec.commonmark.org/0.29/#link-reference-definitions
