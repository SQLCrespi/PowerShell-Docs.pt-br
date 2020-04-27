---
title: Guia de estilo do PowerShell no Docs
description: Este artigo fornece as regras de estilo para escrever a documentação do PowerShell.
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: 90dc93d608440ce7388614b552c0cd873a385cd9
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81624781"
---
# <a name="powershell-docs-style-guide"></a><span data-ttu-id="42375-103">Guia de estilo do PowerShell no Docs</span><span class="sxs-lookup"><span data-stu-id="42375-103">PowerShell-Docs style guide</span></span>

<span data-ttu-id="42375-104">Este artigo fornece orientações de estilo específicas de conteúdo do PowerShell-Docs.</span><span class="sxs-lookup"><span data-stu-id="42375-104">This article provides style guidance specific to the PowerShell-Docs content.</span></span> <span data-ttu-id="42375-105">Ele se baseia nas informações descritas na [Visão geral](overview.md#get-started-writing-docs).</span><span class="sxs-lookup"><span data-stu-id="42375-105">This builds on the information outlined in the [Overview](overview.md#get-started-writing-docs).</span></span>

## <a name="product-terminology"></a><span data-ttu-id="42375-106">Terminologia do produto</span><span class="sxs-lookup"><span data-stu-id="42375-106">Product Terminology</span></span>

<span data-ttu-id="42375-107">O PowerShell tem diversas variantes.</span><span class="sxs-lookup"><span data-stu-id="42375-107">There are several variants of PowerShell.</span></span>

- <span data-ttu-id="42375-108">**PowerShell** – é o termo padrão.</span><span class="sxs-lookup"><span data-stu-id="42375-108">**PowerShell** - This is the default.</span></span> <span data-ttu-id="42375-109">A partir de agora, consideraremos o PowerShell 7 e versões posteriores o verdadeiro PowerShell.</span><span class="sxs-lookup"><span data-stu-id="42375-109">We consider PowerShell 7 and beyond to be the one, true PowerShell going forward.</span></span>
- <span data-ttu-id="42375-110">**PowerShell Core** – PowerShell criado com base no .NET Core.</span><span class="sxs-lookup"><span data-stu-id="42375-110">**PowerShell Core** - PowerShell built on .NET Core.</span></span> <span data-ttu-id="42375-111">O uso do termo **Core** deve se limitar aos casos em que é necessário haver diferenciação do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="42375-111">Usage of the term **Core** should be limited to cases where it is necessary to differentiate it from Windows PowerShell.</span></span>
- <span data-ttu-id="42375-112">**Windows PowerShell** – PowerShell criado no .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="42375-112">**Windows PowerShell** - PowerShell built on .NET Framework.</span></span> <span data-ttu-id="42375-113">O Windows PowerShell é fornecido apenas no Windows e requer o Framework completo.</span><span class="sxs-lookup"><span data-stu-id="42375-113">Windows PowerShell ships only on Windows and requires the complete Framework.</span></span>

  <span data-ttu-id="42375-114">Em geral, as referências ao "Windows PowerShell" na documentação podem ser alteradas para "PowerShell".</span><span class="sxs-lookup"><span data-stu-id="42375-114">In general, references to "Windows PowerShell" in documentation can be changed to "PowerShell".</span></span>
  <span data-ttu-id="42375-115">O "Windows PowerShell" deve ser usado quando o comportamento específico do "Windows PowerShell" está sendo discutido.</span><span class="sxs-lookup"><span data-stu-id="42375-115">"Windows PowerShell" should be used when "Windows PowerShell"-specific behavior is being discussed.</span></span>

<span data-ttu-id="42375-116">Produtos relacionados</span><span class="sxs-lookup"><span data-stu-id="42375-116">Related products</span></span>

- <span data-ttu-id="42375-117">**Visual Studio Code (VS Code)** – este é o editor de software livre gratuito da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="42375-117">**Visual Studio Code (VS Code)** - This is Microsoft's free, open source editor.</span></span> <span data-ttu-id="42375-118">Na primeira menção, o nome completo deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="42375-118">At first mention, the full name should be used.</span></span> <span data-ttu-id="42375-119">Depois disso, você poderá usar o **VS Code**.</span><span class="sxs-lookup"><span data-stu-id="42375-119">After that you may use **VS Code**.</span></span> <span data-ttu-id="42375-120">Não use "VSCode".</span><span class="sxs-lookup"><span data-stu-id="42375-120">Do not use "VSCode".</span></span>
- <span data-ttu-id="42375-121">**Extensão do PowerShell para Visual Studio Code** – a extensão transforma VS Code no IDE preferencial para o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="42375-121">**PowerShell Extension for Visual Studio Code** - The extension turns VS Code into the preferred IDE for PowerShell.</span></span> <span data-ttu-id="42375-122">Na primeira menção, o nome completo deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="42375-122">At first mention, the full name should be used.</span></span> <span data-ttu-id="42375-123">Depois disso, você poderá usar a **extensão do PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="42375-123">After that you may use **PowerShell extension**.</span></span>
- <span data-ttu-id="42375-124">**Azure PowerShell** – é a coleção de módulos do PowerShell usada para gerenciar os serviços do Azure.</span><span class="sxs-lookup"><span data-stu-id="42375-124">**Azure PowerShell** - This is the collection of PowerShell modules used to manage Azure services.</span></span>
- <span data-ttu-id="42375-125">**Azure Stack** do PowerShell – é a coleção de módulos do PowerShell usada para gerenciar a solução de nuvem híbrida da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="42375-125">**Azure Stack PowerShell** - This is the collection of PowerShell modules used to manage Microsoft's hybrid cloud solution.</span></span>

## <a name="markdown-specifics"></a><span data-ttu-id="42375-126">Especificações de Markdown</span><span class="sxs-lookup"><span data-stu-id="42375-126">Markdown specifics</span></span>

<span data-ttu-id="42375-127">O Microsoft OPS (Open Publishing SystemS), que cria nossa documentação, usa [markdig][] para processar os documentos em Markdown.</span><span class="sxs-lookup"><span data-stu-id="42375-127">The Microsoft Open Publishing System (OPS) that builds our documentation uses [markdig][] to process the Markdown documents.</span></span> <span data-ttu-id="42375-128">O markdig analisa os documentos com base nas regras de especificação do [CommonMark][] mais recentes.</span><span class="sxs-lookup"><span data-stu-id="42375-128">Markdig parses the documents based on the rules of the latest [CommonMark][] specification.</span></span>

<span data-ttu-id="42375-129">A nova especificação do CommonMark é muito mais rigorosa quanto à construção de alguns elementos de Markdown.</span><span class="sxs-lookup"><span data-stu-id="42375-129">The new CommonMark spec is much stricter about the construction of some Markdown elements.</span></span> <span data-ttu-id="42375-130">Preste muita atenção aos detalhes fornecidos neste documento.</span><span class="sxs-lookup"><span data-stu-id="42375-130">Pay close attention to the details provided in this document.</span></span>

### <a name="blank-lines-spaces-and-tabs"></a><span data-ttu-id="42375-131">Linhas em branco, espaços e tabulações</span><span class="sxs-lookup"><span data-stu-id="42375-131">Blank lines, spaces, and tabs</span></span>

<span data-ttu-id="42375-132">As linhas em branco também sinalizam o fim de um bloco em Markdown.</span><span class="sxs-lookup"><span data-stu-id="42375-132">Blank lines also signal the end of a block in Markdown.</span></span> <span data-ttu-id="42375-133">Deve haver um espaço em branco único entre os blocos de Markdown de diferentes tipos (por exemplo, entre um parágrafo e uma lista ou cabeçalho).</span><span class="sxs-lookup"><span data-stu-id="42375-133">There should be a single blank between Markdown blocks of different types (for example, between a paragraph and a list or header).</span></span>

<span data-ttu-id="42375-134">Remova linhas em branco duplicadas.</span><span class="sxs-lookup"><span data-stu-id="42375-134">Remove duplicate blank lines.</span></span> <span data-ttu-id="42375-135">Se houver muitas linhas em branco, elas serão processadas como uma única linha em branco no HTML, portanto, não há finalidade para o uso de várias linhas em branco.</span><span class="sxs-lookup"><span data-stu-id="42375-135">Multiple blank lines render as a single blank line in HTML so there is no purpose for multiple blank lines.</span></span> <span data-ttu-id="42375-136">Várias linhas em branco dentro de um bloco de código causarão sua quebra.</span><span class="sxs-lookup"><span data-stu-id="42375-136">Multiple blank lines within a code block break the code block.</span></span>

<span data-ttu-id="42375-137">Remova espaços extras no final das linhas.</span><span class="sxs-lookup"><span data-stu-id="42375-137">Remove extra spaces at the end of lines.</span></span>

> [!NOTE]
> <span data-ttu-id="42375-138">O espaçamento é importante em Markdown.</span><span class="sxs-lookup"><span data-stu-id="42375-138">Spacing is significant in Markdown.</span></span> <span data-ttu-id="42375-139">Use sempre espaços em vez de tabulação.</span><span class="sxs-lookup"><span data-stu-id="42375-139">Always uses spaces instead of hard tabs.</span></span> <span data-ttu-id="42375-140">Os espaços à direita podem mudar a maneira como o Markdown é renderizado.</span><span class="sxs-lookup"><span data-stu-id="42375-140">Trailing spaces can change how Markdown renders.</span></span>

### <a name="titles-and-headings"></a><span data-ttu-id="42375-141">Títulos e cabeçalhos</span><span class="sxs-lookup"><span data-stu-id="42375-141">Titles and headings</span></span>

<span data-ttu-id="42375-142">Use somente [cabeçalhos ATX][atx] (estilo #, em vez de cabeçalhos de estilo `=` ou `-` ).</span><span class="sxs-lookup"><span data-stu-id="42375-142">Only use [ATX headings][atx] (# style, as opposed to `=` or `-` style headers).</span></span>

- <span data-ttu-id="42375-143">Uso de maiúsculas e minúsculas – apenas nomes próprios e a primeira letra de um título ou cabeçalho devem ser escritos em maiúsculas</span><span class="sxs-lookup"><span data-stu-id="42375-143">Use sentence case - only proper nouns and the first letter of a title or header should be capitalized</span></span>
- <span data-ttu-id="42375-144">Deve haver um único espaço entre `#` e a primeira letra do cabeçalho</span><span class="sxs-lookup"><span data-stu-id="42375-144">There must be a single space between the `#` and the first letter of the heading</span></span>
- <span data-ttu-id="42375-145">Os títulos devem estar rodeados por uma única linha em branco</span><span class="sxs-lookup"><span data-stu-id="42375-145">Headings should be surrounded by a single blank line</span></span>
- <span data-ttu-id="42375-146">Apenas um H1 por documento</span><span class="sxs-lookup"><span data-stu-id="42375-146">Only one H1 per document</span></span>
- <span data-ttu-id="42375-147">Os níveis do cabeçalho devem ser incrementados por um.</span><span class="sxs-lookup"><span data-stu-id="42375-147">Header levels should increment by one.</span></span> <span data-ttu-id="42375-148">Não pule os níveis</span><span class="sxs-lookup"><span data-stu-id="42375-148">Do not skip levels</span></span>
- <span data-ttu-id="42375-149">Não use negrito ou outra marcação nos títulos</span><span class="sxs-lookup"><span data-stu-id="42375-149">Do not use bold or other markup in headers</span></span>

### <a name="limit-line-length-to-100-characters"></a><span data-ttu-id="42375-150">Limite o comprimento da linha a 100 caracteres</span><span class="sxs-lookup"><span data-stu-id="42375-150">Limit line length to 100 characters</span></span>

<span data-ttu-id="42375-151">Isso se aplica a artigos conceituais e à referência de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="42375-151">This applies to conceptual articles and cmdlet reference.</span></span> <span data-ttu-id="42375-152">Limitar o comprimento da linha melhora a legibilidade de comparações e histórico de git.</span><span class="sxs-lookup"><span data-stu-id="42375-152">Limiting the line length improves the readability of git diffs and history.</span></span> <span data-ttu-id="42375-153">Também facilita a contribuição de outros escritores.</span><span class="sxs-lookup"><span data-stu-id="42375-153">It also makes it easier for other writers to make contributions.</span></span>

<span data-ttu-id="42375-154">Use a extensão [Reflow Markdown][reflow] no Visual Studio Code para refluir parágrafos com facilidade e ajustar o comprimento da linha prescrita.</span><span class="sxs-lookup"><span data-stu-id="42375-154">Use the [Reflow Markdown][reflow] extension in Visual Studio Code to easily reflow paragraphs to fit the prescribed line length.</span></span>

<span data-ttu-id="42375-155">Os tópicos Sobre são limitados a 80 caracteres.</span><span class="sxs-lookup"><span data-stu-id="42375-155">About_topics are limited to 80 characters.</span></span> <span data-ttu-id="42375-156">Para obter informações mais específicas, confira [Editar artigos de referência](./editing-cmdlet-ref.md#formatting-about_-files).</span><span class="sxs-lookup"><span data-stu-id="42375-156">For more specific information, see [Editing reference articles](./editing-cmdlet-ref.md#formatting-about_-files).</span></span>

### <a name="lists"></a><span data-ttu-id="42375-157">Listas</span><span class="sxs-lookup"><span data-stu-id="42375-157">Lists</span></span>

<span data-ttu-id="42375-158">Caso sua lista contenha várias frases ou parágrafos, considere usar um cabeçalho de subnível, em vez de uma lista.</span><span class="sxs-lookup"><span data-stu-id="42375-158">If your list contains multiple sentences or paragraphs, consider using a sub-level header rather than a list.</span></span>

<span data-ttu-id="42375-159">A lista deve estar rodeada por uma única linha em branco.</span><span class="sxs-lookup"><span data-stu-id="42375-159">List should be surrounded by a single blank line.</span></span>

#### <a name="unordered-lists"></a><span data-ttu-id="42375-160">Listas não ordenadas</span><span class="sxs-lookup"><span data-stu-id="42375-160">Unordered lists</span></span>

<span data-ttu-id="42375-161">Não encerre os itens da lista com um ponto, a menos que eles tenham várias sentenças.</span><span class="sxs-lookup"><span data-stu-id="42375-161">Do not end list items with a period unless they contain multiple sentences.</span></span> <span data-ttu-id="42375-162">Use o caractere de hífen (`-`) para marcadores de itens de lista.</span><span class="sxs-lookup"><span data-stu-id="42375-162">Use the hyphen character (`-`) for list item bullets.</span></span> <span data-ttu-id="42375-163">Isso evita confusão com marcações em negrito ou itálico que usem o asterisco [`*`].</span><span class="sxs-lookup"><span data-stu-id="42375-163">This avoids confusion with bold or italic markup that uses the asterisk [`*`].</span></span> <span data-ttu-id="42375-164">Para incluir um parágrafo ou outros elementos em um item de marcador, insira uma quebra de linha e alinhe o recuo com o primeiro caractere após o marcador.</span><span class="sxs-lookup"><span data-stu-id="42375-164">To include a paragraph or other elements under a bullet item, insert a line break and align indentation with the first character after the bullet.</span></span>

<span data-ttu-id="42375-165">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="42375-165">For example:</span></span>

```markdown
This is a list that contain sub-elements under a bullet item.

- First bullet item

  Sentence explaining the first bullet.

  - Sub-bullet item

    Sentence explaining the sub-bullet.

- Second bullet item
- Third bullet item
```

<span data-ttu-id="42375-166">Esta é uma lista que contém subelementos em um item de marcador.</span><span class="sxs-lookup"><span data-stu-id="42375-166">This is a list that contains sub-elements under a bullet item.</span></span>

- <span data-ttu-id="42375-167">Primeiro item de marcador</span><span class="sxs-lookup"><span data-stu-id="42375-167">First bullet item</span></span>

  <span data-ttu-id="42375-168">Frase explicando o primeiro marcador.</span><span class="sxs-lookup"><span data-stu-id="42375-168">Sentence explaining the first bullet.</span></span>

  - <span data-ttu-id="42375-169">Item de sub-marcador</span><span class="sxs-lookup"><span data-stu-id="42375-169">Sub-bullet item</span></span>

    <span data-ttu-id="42375-170">Frase explicando o submarcador.</span><span class="sxs-lookup"><span data-stu-id="42375-170">Sentence explaining the sub-bullet.</span></span>

- <span data-ttu-id="42375-171">Segundo item de marcador</span><span class="sxs-lookup"><span data-stu-id="42375-171">Second bullet item</span></span>
- <span data-ttu-id="42375-172">Terceiro item de marcador</span><span class="sxs-lookup"><span data-stu-id="42375-172">Third bullet item</span></span>

#### <a name="ordered-lists"></a><span data-ttu-id="42375-173">Listas ordenadas</span><span class="sxs-lookup"><span data-stu-id="42375-173">Ordered lists</span></span>

<span data-ttu-id="42375-174">Para incluir um parágrafo ou outros elementos em um item numerado, alinhe o recuo com o primeiro caractere após o número do item.</span><span class="sxs-lookup"><span data-stu-id="42375-174">To include a paragraph or other elements under a numbered item, align indentation with the first character after the item number.</span></span> <span data-ttu-id="42375-175">Todos os itens em uma lista numerada devem usar o número `1.` em vez de incrementar cada item.</span><span class="sxs-lookup"><span data-stu-id="42375-175">All items in a numbered listed should use the number `1.` rather than incrementing each item.</span></span> <span data-ttu-id="42375-176">A renderização de Markdown incrementa o valor automaticamente.</span><span class="sxs-lookup"><span data-stu-id="42375-176">Markdown rendering increments the value automatically.</span></span> <span data-ttu-id="42375-177">Isso facilita a reorganização dos itens e padroniza o recuo do conteúdo subordinado.</span><span class="sxs-lookup"><span data-stu-id="42375-177">This makes reordering items easier and standardizes the indentation of subordinate content.</span></span>

<span data-ttu-id="42375-178">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="42375-178">For example:</span></span>

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

<span data-ttu-id="42375-179">O Markdown resultante é renderizado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="42375-179">The resulting Markdown is rendered as follows:</span></span>

1. <span data-ttu-id="42375-180">No primeiro elemento, insira um único espaço após o 1.</span><span class="sxs-lookup"><span data-stu-id="42375-180">For the first element, insert a single space after the 1.</span></span> <span data-ttu-id="42375-181">Frases longas devem ser quebradas na próxima linha e devem ser alinhadas com o primeiro caractere após o marcador de lista numerada.</span><span class="sxs-lookup"><span data-stu-id="42375-181">Long sentences should be wrapped to the next line and must line up with the first character after the numbered list marker.</span></span>

   <span data-ttu-id="42375-182">Para incluir um segundo elemento (como este), insira uma quebra de linha após a primeira e alinhe os recuos.</span><span class="sxs-lookup"><span data-stu-id="42375-182">To include a second element (like this one), insert a line break after the first and align indentations.</span></span> <span data-ttu-id="42375-183">O recuo do segundo elemento deve ser alinhado com o primeiro caractere após o marcador de lista numerada.</span><span class="sxs-lookup"><span data-stu-id="42375-183">The indentation of the second element must line up with the first character after the numbered list marker.</span></span> <span data-ttu-id="42375-184">Para itens com dígito único, como este, alinhe o recuo na coluna 4.</span><span class="sxs-lookup"><span data-stu-id="42375-184">For single digit items, like this one, you indent to column 4.</span></span> <span data-ttu-id="42375-185">Para itens com dois dígitos, por exemplo, item número 10, alinhe o recuo na coluna 5.</span><span class="sxs-lookup"><span data-stu-id="42375-185">For double digits items, for example item number 10, you indent to column 5.</span></span>

1. <span data-ttu-id="42375-186">O próximo item numerado começa aqui.</span><span class="sxs-lookup"><span data-stu-id="42375-186">The next numbered item starts here.</span></span>

### <a name="images"></a><span data-ttu-id="42375-187">Imagens</span><span class="sxs-lookup"><span data-stu-id="42375-187">Images</span></span>

<span data-ttu-id="42375-188">A sintaxe que deve ser incluída em uma imagem é:</span><span class="sxs-lookup"><span data-stu-id="42375-188">The syntax to include an image is:</span></span>

```markdown
![[alt text]](<folderPath>)

Example:
![Introduction](./media/overview/Introduction.png)
```

<span data-ttu-id="42375-189">Em que `alt text` é uma breve descrição da imagem, e `<folder path>` é um caminho relativo para a imagem.</span><span class="sxs-lookup"><span data-stu-id="42375-189">Where `alt text` is a brief description of the image and `<folder path>` is a relative path to the image.</span></span> <span data-ttu-id="42375-190">O texto alternativo é obrigatório em leitores de tela para deficientes visuais.</span><span class="sxs-lookup"><span data-stu-id="42375-190">Alternate text is required for screen readers for the visually impaired.</span></span> <span data-ttu-id="42375-191">Ele também é útil em casos de bug no site que faça com que a imagem não seja renderizada.</span><span class="sxs-lookup"><span data-stu-id="42375-191">It is also useful in case there is a site bug where the image cannot be rendered.</span></span>

<span data-ttu-id="42375-192">As imagens devem ser armazenadas em uma pasta `media/<article-name>` dentro de outra pasta que contém o artigo.</span><span class="sxs-lookup"><span data-stu-id="42375-192">Images should be stored in a `media/<article-name>` folder within the folder containing the article.</span></span>
<span data-ttu-id="42375-193">As imagens não devem ser compartilhadas entre os artigos.</span><span class="sxs-lookup"><span data-stu-id="42375-193">Images should not be shared between articles.</span></span> <span data-ttu-id="42375-194">Crie uma pasta que corresponda ao nome de arquivo do artigo na pasta `media`.</span><span class="sxs-lookup"><span data-stu-id="42375-194">Create a folder that matches the filename of your article under the `media` folder.</span></span> <span data-ttu-id="42375-195">Copie as imagens desse artigo para a nova pasta.</span><span class="sxs-lookup"><span data-stu-id="42375-195">Copy the images for that article to that new folder.</span></span> <span data-ttu-id="42375-196">Se uma imagem for usada por vários artigos, cada pasta de imagem deverá ter uma cópia desse arquivo de imagem.</span><span class="sxs-lookup"><span data-stu-id="42375-196">If an image is used by multiple articles, each image folder must have a copy of that image file.</span></span> <span data-ttu-id="42375-197">Essa prática evita que a alteração de uma imagem em um artigo afete outro.</span><span class="sxs-lookup"><span data-stu-id="42375-197">This practice prevents a change to an image in one article affecting another article.</span></span>

<span data-ttu-id="42375-198">Os seguintes tipos de arquivos de imagem são compatíveis: `*.png`, `*.gif`, `*.jpeg`, `*.jpg`, `*.svg`</span><span class="sxs-lookup"><span data-stu-id="42375-198">The following image file types are supported: `*.png`, `*.gif`, `*.jpeg`, `*.jpg`, `*.svg`</span></span>

### <a name="markdown-extensions-supported-by-open-publishing"></a><span data-ttu-id="42375-199">Extensões de Markdown para as quais o Open Publishing dá suporte</span><span class="sxs-lookup"><span data-stu-id="42375-199">Markdown extensions supported by Open Publishing</span></span>

<span data-ttu-id="42375-200">O [Pacote de Criação do Microsoft Docs](/contribute/how-to-write-docs-auth-pack) contém ferramentas que oferecem suporte a recursos exclusivos do nosso sistema de publicação.</span><span class="sxs-lookup"><span data-stu-id="42375-200">The [Microsoft Docs Authoring Pack](/contribute/how-to-write-docs-auth-pack) contains tools that support features unique to our publishing system.</span></span> <span data-ttu-id="42375-201">Os alertas são uma extensão do Markdown para criar citações em bloco que são renderizadas no docs.microsoft.com com cores e ícones que destacam o significado do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="42375-201">Alerts are a Markdown extension to create blockquotes that render on docs.microsoft.com with colors and icons that highlight the significance of the content.</span></span> <span data-ttu-id="42375-202">Há suporte para os seguintes tipos de alerta:</span><span class="sxs-lookup"><span data-stu-id="42375-202">The following alert types are supported:</span></span>

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

<span data-ttu-id="42375-203">Esses alertas ficam da seguinte forma no docs.microsoft.com:</span><span class="sxs-lookup"><span data-stu-id="42375-203">These alerts look like this on docs.microsoft.com:</span></span>

<span data-ttu-id="42375-204">Bloco de notas</span><span class="sxs-lookup"><span data-stu-id="42375-204">Note block</span></span>

> [!NOTE]
> <span data-ttu-id="42375-205">Informações que o usuário deve conseguir notar mesmo que esteja correndo o texto.</span><span class="sxs-lookup"><span data-stu-id="42375-205">Information the user should notice even if skimming.</span></span>

<span data-ttu-id="42375-206">Bloco de dicas</span><span class="sxs-lookup"><span data-stu-id="42375-206">Tip block</span></span>

> [!TIP]
> <span data-ttu-id="42375-207">Informações opcionais para ajudar um usuário a ter mais sucesso.</span><span class="sxs-lookup"><span data-stu-id="42375-207">Optional information to help a user be more successful.</span></span>

<span data-ttu-id="42375-208">Bloco de importância</span><span class="sxs-lookup"><span data-stu-id="42375-208">Important block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="42375-209">Informações essenciais necessárias para o sucesso do usuário.</span><span class="sxs-lookup"><span data-stu-id="42375-209">Essential information required for user success.</span></span>

<span data-ttu-id="42375-210">Bloco de cuidado</span><span class="sxs-lookup"><span data-stu-id="42375-210">Caution block</span></span>

> [!CAUTION]
> <span data-ttu-id="42375-211">Possíveis consequências negativas de uma ação.</span><span class="sxs-lookup"><span data-stu-id="42375-211">Negative potential consequences of an action.</span></span>

<span data-ttu-id="42375-212">Bloco de aviso</span><span class="sxs-lookup"><span data-stu-id="42375-212">Warning block</span></span>

> [!WARNING]
> <span data-ttu-id="42375-213">Consequências perigosas de uma ação.</span><span class="sxs-lookup"><span data-stu-id="42375-213">Dangerous certain consequences of an action.</span></span>

### <a name="hyperlinks"></a><span data-ttu-id="42375-214">Hiperlinks</span><span class="sxs-lookup"><span data-stu-id="42375-214">Hyperlinks</span></span>

- <span data-ttu-id="42375-215">Os hiperlinks devem usar a sintaxe de redução `[friendlyname](url-or-path)`</span><span class="sxs-lookup"><span data-stu-id="42375-215">Hyperlinks must use Markdown syntax `[friendlyname](url-or-path)`</span></span>
- <span data-ttu-id="42375-216">Os links devem ser HTTPS quando possível.</span><span class="sxs-lookup"><span data-stu-id="42375-216">Links should be HTTPS when possible.</span></span>
- <span data-ttu-id="42375-217">Os links devem ter um nome amigável, geralmente o título do tópico vinculado</span><span class="sxs-lookup"><span data-stu-id="42375-217">Links must have a friendly name, usually the title of the linked topic</span></span>
- <span data-ttu-id="42375-218">Todos os itens da seção "links relacionados" na parte inferior devem ser hiperlinks</span><span class="sxs-lookup"><span data-stu-id="42375-218">All items in the "related links" section at the bottom should be hyperlinked</span></span>
- <span data-ttu-id="42375-219">Não use aspas invertidas, negrito ou outra marcação dentro dos colchetes em um hiperlink.</span><span class="sxs-lookup"><span data-stu-id="42375-219">Do not use backticks, bold, or other markup inside the brackets of a hyperlink.</span></span>
- <span data-ttu-id="42375-220">URLs simples podem ser usadas quando há menção a um URI específico.</span><span class="sxs-lookup"><span data-stu-id="42375-220">Bare URLs may be used when you are talking about a specific URI.</span></span> <span data-ttu-id="42375-221">O URI deve ser colocado entre aspas invertidas.</span><span class="sxs-lookup"><span data-stu-id="42375-221">The URI must be enclosed in backticks.</span></span> <span data-ttu-id="42375-222">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="42375-222">For example:</span></span>

  ```markdown
  By default, if you do not specify this parameter, the DMTF standard resource URI
  `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.
  ```

#### <a name="linking-to-other-content"></a><span data-ttu-id="42375-223">Vincular a outros conteúdos</span><span class="sxs-lookup"><span data-stu-id="42375-223">Linking to other content</span></span>

<span data-ttu-id="42375-224">Existem dois tipos de hiperlinks compatíveis com o sistema de publicação:</span><span class="sxs-lookup"><span data-stu-id="42375-224">There are two types of hyperlinks supported by the publishing system:</span></span>

<span data-ttu-id="42375-225">Um **link de URL** pode ser um caminho de URL que é relativo à raiz do docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="42375-225">A **URL link** can be a URL path that is relative to the root of docs.microsoft.com.</span></span> <span data-ttu-id="42375-226">Ou uma URL absoluta que inclua a sintaxe completa da URL.</span><span class="sxs-lookup"><span data-stu-id="42375-226">Or an absolute URL that include the full URL syntax.</span></span> <span data-ttu-id="42375-227">Por exemplo: `https:/github.com/MicrosoftDocs/PowerShell-Docs`</span><span class="sxs-lookup"><span data-stu-id="42375-227">For example: `https:/github.com/MicrosoftDocs/PowerShell-Docs`</span></span>

- <span data-ttu-id="42375-228">Use links de URL ao vincular conteúdo fora do PowerShell-Docs ou entre a referência de cmdlet e artigos conceituais no PowerShell-Docs. A maneira mais simples de criar um link relativo é copiar a URL do seu navegador e remover `https://docs.microsoft.com/en-us` do valor colado no markdown.</span><span class="sxs-lookup"><span data-stu-id="42375-228">Use URL links when linking to content outside of PowerShell-Docs or between cmdlet reference and conceptual articles within PowerShell-docs. The simplest way to create a relative link is to copy the URL from your browser then remove `https://docs.microsoft.com/en-us` from the value you paste into markdown.</span></span>
- <span data-ttu-id="42375-229">Não inclua localidades em URLs nas propriedades da Microsoft (por exemplo:</span><span class="sxs-lookup"><span data-stu-id="42375-229">Do not include locales in URLs on Microsoft properties (eg.</span></span> <span data-ttu-id="42375-230">remova `/en-us` da URL).</span><span class="sxs-lookup"><span data-stu-id="42375-230">remove `/en-us` from URL).</span></span>
- <span data-ttu-id="42375-231">Remova quaisquer parâmetros de consulta desnecessários da URL, a menos que você precise vincular uma versão específica de um artigo.</span><span class="sxs-lookup"><span data-stu-id="42375-231">Remove any unnecessary query parameters from the URL unless you need to link to a specific version of an article.</span></span> <span data-ttu-id="42375-232">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="42375-232">Examples:</span></span>
  - <span data-ttu-id="42375-233">`?view=powershell-5.1` – usado para vincular uma versão específica do PowerShell</span><span class="sxs-lookup"><span data-stu-id="42375-233">`?view=powershell-5.1` - this is used to link to a specific version of PowerShell</span></span>
  - <span data-ttu-id="42375-234">`?redirectedfrom=MSDN` – adicionado à URL quando você é redirecionado de um artigo antigo para seu novo local</span><span class="sxs-lookup"><span data-stu-id="42375-234">`?redirectedfrom=MSDN` - this is added to the URL when you get redirected from an old article to its new location</span></span>
- <span data-ttu-id="42375-235">Todas as URLs para sites externos devem usar HTTPS, a menos que isso não seja válido para o site de destino.</span><span class="sxs-lookup"><span data-stu-id="42375-235">All URLs to external websites should use HTTPS unless that is not valid for the target site.</span></span>

<span data-ttu-id="42375-236">Um **link de arquivo** é usado para vincular um artigo de referência a outro ou um artigo conceitual a outro.</span><span class="sxs-lookup"><span data-stu-id="42375-236">A **file link** is used to link from one reference article to another, or from one conceptual article to another.</span></span> <span data-ttu-id="42375-237">Se você precisar criar um link para um artigo de referência de uma versão específica do PowerShell, use um link de URL.</span><span class="sxs-lookup"><span data-stu-id="42375-237">If you need to link to a reference article for a specific version of PowerShell, then you must use a URL link.</span></span>

- <span data-ttu-id="42375-238">Os links de arquivo contêm um caminho de arquivo relativo (por exemplo: `../folder/file.md`)</span><span class="sxs-lookup"><span data-stu-id="42375-238">File links contain a relative file path (for example: `../folder/file.md`)</span></span>
- <span data-ttu-id="42375-239">Todos os caminhos de arquivo usam caracteres de barra (`/`)</span><span class="sxs-lookup"><span data-stu-id="42375-239">All file paths use forward-slash (`/`) characters</span></span>

<span data-ttu-id="42375-240">A vinculação profunda é permitida em links de URL e de arquivo.</span><span class="sxs-lookup"><span data-stu-id="42375-240">Deep linking is allowed on both URL and file links.</span></span> <span data-ttu-id="42375-241">Adicione a âncora ao final do caminho de destino.</span><span class="sxs-lookup"><span data-stu-id="42375-241">Add the anchor to the end of the target path.</span></span>
<span data-ttu-id="42375-242">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="42375-242">For example:</span></span>

- `[about_Splatting](about_Splatting.md#splatting-with-arrays)`
- `[custom key bindings](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings)`

<span data-ttu-id="42375-243">Para saber mais, confira [Usar links na documentação](https://docs.microsoft.com/contribute/how-to-write-links).</span><span class="sxs-lookup"><span data-stu-id="42375-243">For more information, see [Use links in documentation](https://docs.microsoft.com/contribute/how-to-write-links).</span></span>

## <a name="formatting-command-syntax-elements"></a><span data-ttu-id="42375-244">Formatação de elementos de sintaxe de comando</span><span class="sxs-lookup"><span data-stu-id="42375-244">Formatting command syntax elements</span></span>

- <span data-ttu-id="42375-245">Sempre use o nome completo, sem abreviações, para cmdlets e parâmetros.</span><span class="sxs-lookup"><span data-stu-id="42375-245">Always use the full name for cmdlets and parameters.</span></span> <span data-ttu-id="42375-246">Evite usar aliases, a menos que você esteja demonstrando o alias especificamente.</span><span class="sxs-lookup"><span data-stu-id="42375-246">Avoid using aliases unless you are specifically demonstrating the alias.</span></span>

- <span data-ttu-id="42375-247">Propriedade, parâmetro, objeto, nomes de tipo, nomes de classe, métodos de classe estar em **negrito**.</span><span class="sxs-lookup"><span data-stu-id="42375-247">Property, parameter, object, type names, class names, class methods should be **bold**.</span></span>
  - <span data-ttu-id="42375-248">Os valores de propriedade e de parâmetro devem ser dispostos entre aspas invertidas (`` ` ``).</span><span class="sxs-lookup"><span data-stu-id="42375-248">Property and parameter values should be wrapped in backticks (`` ` ``).</span></span>
  - <span data-ttu-id="42375-249">Ao se referir a tipos que usam o estilo entre colchetes, use aspas invertidas.</span><span class="sxs-lookup"><span data-stu-id="42375-249">When referring to types using the bracketed style, use backticks.</span></span> <span data-ttu-id="42375-250">Por exemplo: `[System.Io.FileInfo]`</span><span class="sxs-lookup"><span data-stu-id="42375-250">For example: `[System.Io.FileInfo]`</span></span>

- <span data-ttu-id="42375-251">Palavras-chave de idioma, nomes de cmdlet, funções, variáveis, EXEs nativos, caminhos de arquivo e exemplos de sintaxe em linha devem ser agrupados em caracteres de aspas invertidas (`` ` ``).</span><span class="sxs-lookup"><span data-stu-id="42375-251">Language keywords, cmdlet names, functions, variables, native EXEs, file paths, and inline syntax examples should be wrapped in backtick (`` ` ``) characters.</span></span>

  <span data-ttu-id="42375-252">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="42375-252">For example:</span></span>

  ~~~markdown
  The following code uses `Get-ChildItem` to list the contents of `C:\Windows` and assigns
  the output to the `$files` variable.

  ```powershell
  $files = Get-ChildItem C:\Windows
  ```
  ~~~

  - <span data-ttu-id="42375-253">Ao se referir a um parâmetro por nome, o nome deve estar em **negrito**.</span><span class="sxs-lookup"><span data-stu-id="42375-253">When referring to a parameter by name, the name should be **bold**.</span></span> <span data-ttu-id="42375-254">Ao ilustrar o uso de um parâmetro com o prefixo de hífen, o parâmetro deve estar entre aspas invertidas.</span><span class="sxs-lookup"><span data-stu-id="42375-254">When illustrating the use of a parameter with the hyphen prefix, the parameter should be wrapped in backticks.</span></span> <span data-ttu-id="42375-255">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="42375-255">For example:</span></span>

    ```markdown
    The parameter's name is **Name**, but it is typed as `-Name` when used on the command
    line as a parameter.
    ```

  - <span data-ttu-id="42375-256">Ao mostrar o exemplo de uso de um comando externo, o exemplo deve estar entre aspas invertidas.</span><span class="sxs-lookup"><span data-stu-id="42375-256">When showing example usage of an external command, the example should be wrapped in backticks.</span></span>
    <span data-ttu-id="42375-257">Sempre inclua a extensão do arquivo no comando nativo.</span><span class="sxs-lookup"><span data-stu-id="42375-257">Always include the file extension in the native command.</span></span> <span data-ttu-id="42375-258">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="42375-258">For example:</span></span>

    ```markdown
    To start the spooler service on a remote computer named DC01, you type `sc.exe \\DC01 start spooler`.
    ```

    <span data-ttu-id="42375-259">A inclusão da extensão do arquivo garante que o comando correto seja executado de acordo com a precedência do comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="42375-259">Including the file extension ensures that the correct command is executed according PowerShell's command precedence.</span></span>

- <span data-ttu-id="42375-260">Ao escrever um artigo conceitual (em vez de um conteúdo de referência), a primeira instância de um nome de cmdlet deve ser vinculada à documentação do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="42375-260">When writing a conceptual article (as opposed to reference content), the first instance of a cmdlet name should be hyperlinked to the cmdlet documentation.</span></span> <span data-ttu-id="42375-261">Não use aspas invertidas, negrito ou outra marcação dentro dos colchetes em um hiperlink.</span><span class="sxs-lookup"><span data-stu-id="42375-261">Do not use backticks, bold, or other markup inside the brackets of a hyperlink.</span></span>

  <span data-ttu-id="42375-262">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="42375-262">For example:</span></span>

  ```markdown
  This [Write-Host](/powershell/module/Microsoft.PowerShell.Utility/Write-Host) cmdlet
  uses the **Object** parameter to ...
  ```

  <span data-ttu-id="42375-263">Para obter mais informações, confira a seção [Hiperlinks](#hyperlinks) deste artigo.</span><span class="sxs-lookup"><span data-stu-id="42375-263">For more information, see [Hyperlinks](#hyperlinks) section of this article.</span></span>

## <a name="markdown-for-code-samples"></a><span data-ttu-id="42375-264">Markdown de exemplos de código</span><span class="sxs-lookup"><span data-stu-id="42375-264">Markdown for code samples</span></span>

<span data-ttu-id="42375-265">O Markdown dá suporte a dois estilos de código diferentes:</span><span class="sxs-lookup"><span data-stu-id="42375-265">Markdown supports two different code styles:</span></span>

- <span data-ttu-id="42375-266">**Extensão de código (embutido)** – marcada por um único caractere de aspas invertidas (`` ` ``).</span><span class="sxs-lookup"><span data-stu-id="42375-266">**Code spans (inline)** - marked by a single backtick (`` ` ``) character.</span></span> <span data-ttu-id="42375-267">Usado dentro de um parágrafo, e não como um bloco independente.</span><span class="sxs-lookup"><span data-stu-id="42375-267">Used within a paragraph rather than as a standalone block.</span></span>
- <span data-ttu-id="42375-268">**Blocos de código** – um bloco de várias linhas cercado por cadeias de caracteres com aspas triplas (`` ``` ``).</span><span class="sxs-lookup"><span data-stu-id="42375-268">**Code blocks** - a multi-line block surrounded by triple-backtick (`` ``` ``) strings.</span></span> <span data-ttu-id="42375-269">Os blocos de código também podem ter um rótulo de linguagem após as aspas invertidas.</span><span class="sxs-lookup"><span data-stu-id="42375-269">Code blocks may also have a language label following the backticks.</span></span> <span data-ttu-id="42375-270">O rótulo de linguagem habilita o destaque da sintaxe para o conteúdo do bloco de código.</span><span class="sxs-lookup"><span data-stu-id="42375-270">The language label enables syntax highlighting for the contents of the code block.</span></span>

<span data-ttu-id="42375-271">Todos os blocos de código devem estar contidos em um limite de códigos.</span><span class="sxs-lookup"><span data-stu-id="42375-271">All code blocks should be contained in a code fence.</span></span> <span data-ttu-id="42375-272">Nunca use recuo para blocos de código.</span><span class="sxs-lookup"><span data-stu-id="42375-272">Never use indentation for code blocks.</span></span> <span data-ttu-id="42375-273">O Markdown permite esse padrão, mas pode gerar problemas e deve ser evitado.</span><span class="sxs-lookup"><span data-stu-id="42375-273">Markdown allows this pattern but it can be problematic and should be avoided.</span></span>

<span data-ttu-id="42375-274">Um bloco de código corresponde a uma ou mais linhas de código limitadas por aspas invertidas triplas (`` ``` ``).</span><span class="sxs-lookup"><span data-stu-id="42375-274">A code block is one or more lines of code surrounded by a triple-backtick (`` ``` ``) code fence.</span></span>
<span data-ttu-id="42375-275">Os marcadores de limite de código devem estar em sua própria linha antes e depois do exemplo de código.</span><span class="sxs-lookup"><span data-stu-id="42375-275">The code fence markers must be on their own line before and after the code sample.</span></span> <span data-ttu-id="42375-276">O marcador no início do bloco de código pode ter um rótulo de linguagem opcional.</span><span class="sxs-lookup"><span data-stu-id="42375-276">The marker at the start of the code block may have an optional language label.</span></span> <span data-ttu-id="42375-277">O OPS (Open Publishing System) da Microsoft usa o rótulo de linguagem para oferecer suporte ao recurso de destaque da sintaxe.</span><span class="sxs-lookup"><span data-stu-id="42375-277">Microsoft's Open Publishing System (OPS) uses the language label to support the syntax highlighting feature.</span></span>

<span data-ttu-id="42375-278">Para obter uma lista completa das marcas de idioma compatíveis, confira [Blocos de código limitados](/contribute/code-in-docs#fenced-code-blocks) no guia do colaborador centralizado.</span><span class="sxs-lookup"><span data-stu-id="42375-278">For a full list of supported language tags, see [Fenced code blocks](/contribute/code-in-docs#fenced-code-blocks) in the centralized contributor guide.</span></span>

<span data-ttu-id="42375-279">O OPS também adiciona um botão **Copiar** que copia o conteúdo do bloco de código para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="42375-279">OPS also adds a **Copy** button that copies the contents of the code block to the clipboard.</span></span> <span data-ttu-id="42375-280">Isso permite que você cole rapidamente o código em um script para testar o exemplo de código.</span><span class="sxs-lookup"><span data-stu-id="42375-280">This allows you to quickly paste the code into a script to test the code sample.</span></span> <span data-ttu-id="42375-281">No entanto, nem todos os exemplos em nossa documentação devem ser executados no estado em que se encontram.</span><span class="sxs-lookup"><span data-stu-id="42375-281">However, not all examples in our documentation are intended to be run as-is.</span></span> <span data-ttu-id="42375-282">Alguns blocos de código são ilustrações simples de um conceito do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="42375-282">Some code blocks are simple illustrations of a PowerShell concept.</span></span>

<span data-ttu-id="42375-283">Existem três tipos de blocos de código usados em nossa documentação:</span><span class="sxs-lookup"><span data-stu-id="42375-283">There are three types code blocks used in our documentation:</span></span>

1. <span data-ttu-id="42375-284">Blocos de sintaxe</span><span class="sxs-lookup"><span data-stu-id="42375-284">Syntax blocks</span></span>
1. <span data-ttu-id="42375-285">Exemplos ilustrativos</span><span class="sxs-lookup"><span data-stu-id="42375-285">Illustrative examples</span></span>
1. <span data-ttu-id="42375-286">Exemplos executáveis</span><span class="sxs-lookup"><span data-stu-id="42375-286">Executable examples</span></span>

### <a name="syntax-code-blocks"></a><span data-ttu-id="42375-287">Blocos de código de sintaxe</span><span class="sxs-lookup"><span data-stu-id="42375-287">Syntax code blocks</span></span>

<span data-ttu-id="42375-288">Os blocos de código de sintaxe são usados para descrever a estrutura sintática de um comando.</span><span class="sxs-lookup"><span data-stu-id="42375-288">Syntax code blocks are used to describe the syntactic structure of a command.</span></span> <span data-ttu-id="42375-289">Não use uma marca de idioma no limite de código.</span><span class="sxs-lookup"><span data-stu-id="42375-289">Do not use a language tag on the code fence.</span></span> <span data-ttu-id="42375-290">Este exemplo ilustra todos os parâmetros possíveis do cmdlet `Get-Command`.</span><span class="sxs-lookup"><span data-stu-id="42375-290">This example illustrates all the possible parameters of the `Get-Command` cmdlet.</span></span>

~~~markdown
```
Get-Command [-Verb <String[]>] [-Noun <String[]>] [-Module <String[]>]
  [-FullyQualifiedModule <ModuleSpecification[]>] [-TotalCount <Int32>] [-Syntax]
  [-ShowCommandInfo] [[-ArgumentList] <Object[]>] [-All] [-ListImported]
  [-ParameterName <String[]>] [-ParameterType <PSTypeName[]>] [<CommonParameters>]
```
~~~

<span data-ttu-id="42375-291">Este exemplo descreve a instrução `for` em termos generalizados:</span><span class="sxs-lookup"><span data-stu-id="42375-291">This example describes the `for` statement in generalized terms:</span></span>

~~~markdown
```
for (<init>; <condition>; <repeat>)
{<statement list>}
```
~~~

### <a name="illustrative-examples"></a><span data-ttu-id="42375-292">Exemplos ilustrativos</span><span class="sxs-lookup"><span data-stu-id="42375-292">Illustrative examples</span></span>

<span data-ttu-id="42375-293">Exemplos ilustrativos são usados para explicar um conceito do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="42375-293">Illustrative examples are used to explain a PowerShell concept.</span></span> <span data-ttu-id="42375-294">Eles não devem ser copiados para a área de transferência a fim de serem executados.</span><span class="sxs-lookup"><span data-stu-id="42375-294">They are not meant to be copied to the clipboard for execution.</span></span> <span data-ttu-id="42375-295">Eles são mais comumente usados em exemplos simples, fáceis de digitar e entender.</span><span class="sxs-lookup"><span data-stu-id="42375-295">These are most commonly used for simple examples that are easy to type and easy to understand.</span></span> <span data-ttu-id="42375-296">O bloco de código pode incluir o prompt do PowerShell e o exemplo de saída.</span><span class="sxs-lookup"><span data-stu-id="42375-296">The code block can include the PowerShell prompt and example output.</span></span>

<span data-ttu-id="42375-297">Confira um exemplo simples que ilustra os operadores de comparação do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="42375-297">Here is a simple example illustrating the PowerShell comparison operators.</span></span> <span data-ttu-id="42375-298">Nesse caso, não pretendemos que o leitor copie nem execute esse exemplo.</span><span class="sxs-lookup"><span data-stu-id="42375-298">In this case, we don't intend the reader to copy and run this example.</span></span>

~~~markdown
```powershell
PS> 2 -eq 2
True

PS> 2 -eq 3
False

PS>  1,2,3 -eq 2
2

PS> "abc" -eq "abc"
True

PS> "abc" -eq "abc", "def"
False

PS> "abc", "def" -eq "abc"
abc
```
~~~

### <a name="executable-examples"></a><span data-ttu-id="42375-299">Exemplos executáveis</span><span class="sxs-lookup"><span data-stu-id="42375-299">Executable examples</span></span>

<span data-ttu-id="42375-300">Exemplos complexos, ou exemplos que devem ser copiados e executados, devem usar a seguinte marcação no estilo de bloco:</span><span class="sxs-lookup"><span data-stu-id="42375-300">Complex examples, or examples that are intended to be copied and executed, should use the following block-style markup:</span></span>

~~~markdown
```powershell
<Your PowerShell code goes here>
```
~~~

<span data-ttu-id="42375-301">A saída exibida pelos comandos do PowerShell deve ser colocadas entre blocos de código de **Saída**, para evitar o destaque da sintaxe.</span><span class="sxs-lookup"><span data-stu-id="42375-301">The output displayed by PowerShell commands should be enclosed in an **Output** code block to prevent syntax highlighting.</span></span> <span data-ttu-id="42375-302">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="42375-302">For example:</span></span>

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

<span data-ttu-id="42375-303">O rótulo do código de **Saída** não é uma "linguagem" oficial à qual o sistema de destaque de sintaxe dá suporte.</span><span class="sxs-lookup"><span data-stu-id="42375-303">The **Output** code label is not an official "language" supported by the syntax highlighting system.</span></span>
<span data-ttu-id="42375-304">No entanto, esse rótulo é útil porque o OPS adiciona o rótulo de "Saída" ao quadro da caixa de código na página da Web.</span><span class="sxs-lookup"><span data-stu-id="42375-304">However, this label is useful because OPS adds the "Output" label to the code box frame on the web page.</span></span> <span data-ttu-id="42375-305">A caixa de código de "Saída" não possui destaque de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="42375-305">The "Output" code box has no syntax highlighting.</span></span>

## <a name="coding-style-rules"></a><span data-ttu-id="42375-306">Regras de estilo de codificação</span><span class="sxs-lookup"><span data-stu-id="42375-306">Coding style rules</span></span>

### <a name="avoid-line-continuation-in-code-samples"></a><span data-ttu-id="42375-307">Evitar a continuação de linha em exemplos de código</span><span class="sxs-lookup"><span data-stu-id="42375-307">Avoid line continuation in code samples</span></span>

<span data-ttu-id="42375-308">Evite usar caracteres de continuação de linha (`` ` ``) nos exemplos de código do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="42375-308">Avoid using line continuation characters (`` ` ``) in PowerShell code examples.</span></span> <span data-ttu-id="42375-309">Eles são difíceis de ver e podem causar problemas caso haja espaços extras no final da linha.</span><span class="sxs-lookup"><span data-stu-id="42375-309">These are hard to see and can cause problems if there are extra spaces at the end of the line.</span></span>

- <span data-ttu-id="42375-310">Use os nivelamento do PowerShell para reduzir o comprimento da linha de cmdlets com muitos parâmetros.</span><span class="sxs-lookup"><span data-stu-id="42375-310">Use PowerShell splatting to reduce line length for cmdlets that have a lot of parameters.</span></span>
- <span data-ttu-id="42375-311">Aproveite as quebras naturais de linha do PowerShell, como caracteres após a barra vertical (`|`), chaves, parênteses e colchetes.</span><span class="sxs-lookup"><span data-stu-id="42375-311">Take advantage of PowerShell's natural line break opportunities, like after pipe (`|`) characters, opening braces, parentheses, and brackets.</span></span>

### <a name="avoid-using-powershell-prompts-in-examples"></a><span data-ttu-id="42375-312">Evitar o uso de prompts do PowerShell em exemplos</span><span class="sxs-lookup"><span data-stu-id="42375-312">Avoid using PowerShell prompts in examples</span></span>

<span data-ttu-id="42375-313">O uso da cadeia de caracteres de prompt é desencorajado e deve ser limitado a cenários que ilustram o uso da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="42375-313">Use of the prompt string is discouraged and should be limited to scenarios that are meant to illustrate command line usage.</span></span> <span data-ttu-id="42375-314">Para a maioria desses exemplos, a cadeia de caracteres de prompt deve ser `PS>`.</span><span class="sxs-lookup"><span data-stu-id="42375-314">For most of these examples, the prompt string should be `PS>`.</span></span> <span data-ttu-id="42375-315">Esse prompt é independente dos indicadores específicos do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="42375-315">This prompt is independent of OS-specific indicators.</span></span>

<span data-ttu-id="42375-316">Os prompts são necessários para dar exemplos ilustrativos dos comandos que os alteram ou quando o caminho exibido é significativo para o cenário que está sendo ilustrado.</span><span class="sxs-lookup"><span data-stu-id="42375-316">Prompts are required for examples that illustrate commands that alter the prompt or when the path displayed is significant to the scenario being illustrated.</span></span> <span data-ttu-id="42375-317">O exemplo a seguir ilustra como o prompt é alterado ao usar o provedor de Registro.</span><span class="sxs-lookup"><span data-stu-id="42375-317">The following example illustrates how the prompt changes when using the Registry provider.</span></span>

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

### <a name="do-not-use-aliases-in-examples"></a><span data-ttu-id="42375-318">Não usar aliases em exemplos</span><span class="sxs-lookup"><span data-stu-id="42375-318">Do not use aliases in examples</span></span>

<span data-ttu-id="42375-319">Use sempre o nome completo de todos os cmdlets e parâmetros, a menos que esteja falando especificamente sobre o alias.</span><span class="sxs-lookup"><span data-stu-id="42375-319">You should always use the full name of all cmdlets and parameters unless you are specifically talking about the alias.</span></span> <span data-ttu-id="42375-320">Os nomes de cmdlets e parâmetros devem usar os nomes apropriados para Pascal.</span><span class="sxs-lookup"><span data-stu-id="42375-320">Cmdlet and parameter names must use the proper Pascal-cased names.</span></span>

### <a name="using-parameters-in-examples"></a><span data-ttu-id="42375-321">Usar parâmetros em exemplos</span><span class="sxs-lookup"><span data-stu-id="42375-321">Using parameters in examples</span></span>

<span data-ttu-id="42375-322">Evite usar parâmetros posicionais.</span><span class="sxs-lookup"><span data-stu-id="42375-322">Avoid using positional parameters.</span></span> <span data-ttu-id="42375-323">De maneira geral, sempre inclua o nome do parâmetro em um exemplo, mesmo que o parâmetro seja posicional.</span><span class="sxs-lookup"><span data-stu-id="42375-323">In general, you should always include the parameter name in an example, even if the parameter is positional.</span></span> <span data-ttu-id="42375-324">Isso reduz a chance de confusão nos seus exemplos.</span><span class="sxs-lookup"><span data-stu-id="42375-324">This reduces the chance of confusion in your examples.</span></span>

## <a name="next-steps"></a><span data-ttu-id="42375-325">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="42375-325">Next steps</span></span>

[<span data-ttu-id="42375-326">Editar a referência de cmdlet</span><span class="sxs-lookup"><span data-stu-id="42375-326">Editing cmdlet reference</span></span>](editing-cmdlet-ref.md)

<!-- External URLs -->
[platyPS]: https://github.com/PowerShell/platyPS
[markdig]: https://github.com/lunet-io/markdig
[CommonMark]: https://spec.commonmark.org/
[atx]: https://github.github.com/gfm/#atx-headings
[pascal-case]: https://en.wikipedia.org/wiki/PascalCase
[reflow]: https://marketplace.visualstudio.com/items?itemName=marvhen.reflow-markdown
