---
title: Guia de estilo do PowerShell no Docs
description: Este artigo fornece as regras de estilo para escrever a documentação do PowerShell.
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: 964536c5195c3bb8abd98b5996a96fc7b9362489
ms.sourcegitcommit: c97dcf1e00ef540e7464c36c88f841474060044c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2020
ms.locfileid: "79402573"
---
# <a name="powershell-docs-style-guide"></a><span data-ttu-id="7fdc3-103">Guia de estilo do PowerShell no Docs</span><span class="sxs-lookup"><span data-stu-id="7fdc3-103">PowerShell-Docs style guide</span></span>

<span data-ttu-id="7fdc3-104">Este artigo fornece orientações de estilo específicas de conteúdo do PowerShell-Docs.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-104">This article provides style guidance specific to the PowerShell-Docs content.</span></span> <span data-ttu-id="7fdc3-105">Ele se baseia nas informações descritas na [Visão geral](overview.md#get-started-writing-docs).</span><span class="sxs-lookup"><span data-stu-id="7fdc3-105">This builds on the information outlined in the [Overview](overview.md#get-started-writing-docs).</span></span>

## <a name="product-terminology"></a><span data-ttu-id="7fdc3-106">Terminologia do produto</span><span class="sxs-lookup"><span data-stu-id="7fdc3-106">Product Terminology</span></span>

<span data-ttu-id="7fdc3-107">O PowerShell tem diversas variantes.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-107">There are several variants of PowerShell.</span></span>
<span data-ttu-id="7fdc3-108">Esta tabela define alguns dos vários termos usados para definir o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-108">This table defines some of the different terms used to discuss PowerShell.</span></span>

- <span data-ttu-id="7fdc3-109">**PowerShell** – é o termo padrão.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-109">**PowerShell** - This is the default.</span></span> <span data-ttu-id="7fdc3-110">A partir de agora, consideraremos o PowerShell 7 e versões posteriores o verdadeiro PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-110">We consider PowerShell 7 and beyond to be the one, true PowerShell going forward.</span></span>

- <span data-ttu-id="7fdc3-111">**PowerShell Core** – PowerShell criado com base no .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-111">**PowerShell Core** - PowerShell built on .NET Core.</span></span> <span data-ttu-id="7fdc3-112">O uso do termo **Core** deve se limitar aos casos em que é necessário haver diferenciação do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-112">Usage of the term **Core** should be limited to cases where it is necessary to differentiate it from Windows PowerShell.</span></span>

- <span data-ttu-id="7fdc3-113">**Windows PowerShell** – PowerShell criado no .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-113">**Windows PowerShell** - PowerShell built on .NET Framework.</span></span> <span data-ttu-id="7fdc3-114">O Windows PowerShell é fornecido apenas no Windows e requer o Framework completo.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-114">Windows PowerShell ships only on Windows and requires the complete Framework.</span></span>

<span data-ttu-id="7fdc3-115">Em geral, as referências ao "Windows PowerShell" na documentação podem ser alteradas para "PowerShell".</span><span class="sxs-lookup"><span data-stu-id="7fdc3-115">In general, references to "Windows PowerShell" in documentation can be changed to "PowerShell".</span></span>
<span data-ttu-id="7fdc3-116">O "Windows PowerShell" **não** deve ser alterado quando a tecnologia específica do Windows está sendo abordada.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-116">"Windows PowerShell" should **not** be changed when Windows-specific technology is being discussed.</span></span>

## <a name="markdown-specifics"></a><span data-ttu-id="7fdc3-117">Especificações de Markdown</span><span class="sxs-lookup"><span data-stu-id="7fdc3-117">Markdown specifics</span></span>

<span data-ttu-id="7fdc3-118">O Microsoft OPS (Open Publishing SystemS), que cria nossa documentação, usa [markdig][] para processar os documentos em Markdown.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-118">The Microsoft Open Publishing System (OPS) that builds our documentation uses [markdig][] to process the Markdown documents.</span></span> <span data-ttu-id="7fdc3-119">O markdig analisa os documentos com base nas regras de especificação do [CommonMark][] mais recentes.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-119">Markdig parses the documents based on the rules of the latest [CommonMark][] specification.</span></span>

<span data-ttu-id="7fdc3-120">A nova especificação do CommonMark é muito mais rigorosa quanto à construção de alguns elementos de Markdown.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-120">The new CommonMark spec is much stricter about the construction of some Markdown elements.</span></span> <span data-ttu-id="7fdc3-121">Preste muita atenção aos detalhes fornecidos neste documento.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-121">Pay close attention to the details provided in this document.</span></span>

### <a name="blank-lines-spaces-and-tabs"></a><span data-ttu-id="7fdc3-122">Linhas em branco, espaços e tabulações</span><span class="sxs-lookup"><span data-stu-id="7fdc3-122">Blank lines, spaces, and tabs</span></span>

<span data-ttu-id="7fdc3-123">Remova linhas em branco duplicadas.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-123">Remove duplicate blank lines.</span></span> <span data-ttu-id="7fdc3-124">Se houver muitas linhas em branco, elas serão processadas como uma única linha em branco no HTML, portanto, não há finalidade para o uso de várias linhas em branco.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-124">Multiple blank lines render as a single blank line in HTML so there is not purpose for multiple blank lines.</span></span>

<span data-ttu-id="7fdc3-125">As linhas em branco também sinalizam o fim de um bloco em Markdown.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-125">Blank lines also signal the end of a block in Markdown.</span></span> <span data-ttu-id="7fdc3-126">Deve haver um espaço em branco único entre os blocos de Markdown de diferentes tipos (por exemplo, entre um parágrafo e uma lista ou cabeçalho).</span><span class="sxs-lookup"><span data-stu-id="7fdc3-126">There should be a single blank between Markdown blocks of different types (for example, between a paragraph and a list or header).</span></span>

> [!NOTE]
> <span data-ttu-id="7fdc3-127">O espaçamento é importante em Markdown.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-127">Spacing is significant in Markdown.</span></span> <span data-ttu-id="7fdc3-128">Use sempre espaços em vez de tabulação.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-128">Always uses spaces instead of hard tabs.</span></span> <span data-ttu-id="7fdc3-129">Remova espaços extras no final das linhas.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-129">Remove extra spaces at the end of lines.</span></span>

### <a name="titles-and-headings"></a><span data-ttu-id="7fdc3-130">Títulos e cabeçalhos</span><span class="sxs-lookup"><span data-stu-id="7fdc3-130">Titles and headings</span></span>

<span data-ttu-id="7fdc3-131">Use somente [cabeçalhos ATX][atx] (estilo #, em vez de cabeçalhos de estilo `=` ou `-` ).</span><span class="sxs-lookup"><span data-stu-id="7fdc3-131">Only use [ATX headings][atx] (# style, as opposed to `=` or `-` style headers).</span></span>

- <span data-ttu-id="7fdc3-132">Uso de maiúsculas e minúsculas – apenas nomes próprios e a primeira letra de um título ou cabeçalho devem ser escritos em maiúsculas</span><span class="sxs-lookup"><span data-stu-id="7fdc3-132">Use sentence case - only proper nouns and the first letter of a title or header should be capitalized</span></span>
- <span data-ttu-id="7fdc3-133">Deve haver um único espaço entre `#` e a primeira letra do cabeçalho</span><span class="sxs-lookup"><span data-stu-id="7fdc3-133">There must be a single space between the `#` and the first letter of the heading</span></span>
- <span data-ttu-id="7fdc3-134">Os títulos devem estar rodeados por uma única linha em branco</span><span class="sxs-lookup"><span data-stu-id="7fdc3-134">Headings should be surrounded by a single blank line</span></span>
- <span data-ttu-id="7fdc3-135">Apenas um H1 por documento</span><span class="sxs-lookup"><span data-stu-id="7fdc3-135">Only one H1 per document</span></span>
- <span data-ttu-id="7fdc3-136">Os níveis do cabeçalho devem ser incrementados por um.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-136">Header levels should increment by one.</span></span> <span data-ttu-id="7fdc3-137">Não pule os níveis</span><span class="sxs-lookup"><span data-stu-id="7fdc3-137">Do not skip levels</span></span>
- <span data-ttu-id="7fdc3-138">Não use negrito ou outra marcação nos títulos</span><span class="sxs-lookup"><span data-stu-id="7fdc3-138">Do not use bold or other markup in headers</span></span>

### <a name="limit-line-length-to-100-characters"></a><span data-ttu-id="7fdc3-139">Limite o comprimento da linha a 100 caracteres</span><span class="sxs-lookup"><span data-stu-id="7fdc3-139">Limit line length to 100 characters</span></span>

<span data-ttu-id="7fdc3-140">Isso se aplica a artigos conceituais e à referência de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-140">This applies to conceptual articles and cmdlet reference.</span></span> <span data-ttu-id="7fdc3-141">Os tópicos Sobre são limitados a 80 caracteres.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-141">About_topics are limited to 80 characters.</span></span>
<span data-ttu-id="7fdc3-142">Limitar o comprimento da linha melhora a legibilidade de comparações e histórico do git.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-142">Limiting the line length improves the readability git diffs and history.</span></span> <span data-ttu-id="7fdc3-143">Também facilita a contribuição de outros escritores.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-143">It also makes it easier for other writers to make contributions.</span></span>

<span data-ttu-id="7fdc3-144">Use a extensão [Reflow Markdown][reflow] no Visual Studio Code para refluir parágrafos com facilidade e ajustar o comprimento da linha prescrita.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-144">Use the [Reflow Markdown][reflow] extension in Visual Studio Code to easily reflow paragraphs to fit the prescribed line length.</span></span>

### <a name="lists"></a><span data-ttu-id="7fdc3-145">Listas</span><span class="sxs-lookup"><span data-stu-id="7fdc3-145">Lists</span></span>

<span data-ttu-id="7fdc3-146">Caso sua lista contenha várias frases ou parágrafos, considere usar um cabeçalho de subnível, em vez de uma lista.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-146">If your list contains multiple sentences or paragraphs, consider using a sub-level header rather than a list.</span></span>

<span data-ttu-id="7fdc3-147">A lista deve estar rodeada por uma única linha em branco.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-147">List should be surrounded by a single blank line.</span></span>

#### <a name="unordered-lists"></a><span data-ttu-id="7fdc3-148">Listas não ordenadas</span><span class="sxs-lookup"><span data-stu-id="7fdc3-148">Unordered lists</span></span>

<span data-ttu-id="7fdc3-149">Não encerre os itens da lista com um ponto, a menos que eles tenham várias sentenças.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-149">Do not end list items with a period unless they contain multiple sentences.</span></span> <span data-ttu-id="7fdc3-150">Use o caractere de hífen (`-`) para marcadores de itens de lista.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-150">Use the hyphen character (`-`) for list item bullets.</span></span> <span data-ttu-id="7fdc3-151">Isso evita confusão com marcações em negrito ou itálico que usem o asterisco [`*`].</span><span class="sxs-lookup"><span data-stu-id="7fdc3-151">This avoids confusion with bold or italic markup that uses the asterisk [`*`].</span></span> <span data-ttu-id="7fdc3-152">Para incluir um parágrafo ou outros elementos em um item de marcador, insira uma quebra de linha e alinhe o recuo com o primeiro caractere após o marcador.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-152">To include a paragraph or other elements under a bullet item, insert a line break and align indentation with the first character after the bullet.</span></span>

<span data-ttu-id="7fdc3-153">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7fdc3-153">For example:</span></span>

```markdown
This is a list that contain sub-elements under a bullet item.

- First bullet item

  Sentence explaining the first bullet.

  - Sub-bullet item

    Sentence explaining the sub-bullet.

- Second bullet item
- Third bullet item
```

<span data-ttu-id="7fdc3-154">Esta é uma lista que contém subelementos em um item de marcador.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-154">This is a list that contains sub-elements under a bullet item.</span></span>

- <span data-ttu-id="7fdc3-155">Primeiro item de marcador</span><span class="sxs-lookup"><span data-stu-id="7fdc3-155">First bullet item</span></span>

  <span data-ttu-id="7fdc3-156">Frase explicando o primeiro marcador.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-156">Sentence explaining the first bullet.</span></span>

  - <span data-ttu-id="7fdc3-157">Item de sub-marcador</span><span class="sxs-lookup"><span data-stu-id="7fdc3-157">Sub-bullet item</span></span>

    <span data-ttu-id="7fdc3-158">Frase explicando o submarcador.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-158">Sentence explaining the sub-bullet.</span></span>

- <span data-ttu-id="7fdc3-159">Segundo item de marcador</span><span class="sxs-lookup"><span data-stu-id="7fdc3-159">Second bullet item</span></span>
- <span data-ttu-id="7fdc3-160">Terceiro item de marcador</span><span class="sxs-lookup"><span data-stu-id="7fdc3-160">Third bullet item</span></span>

#### <a name="ordered-lists"></a><span data-ttu-id="7fdc3-161">Listas ordenadas</span><span class="sxs-lookup"><span data-stu-id="7fdc3-161">Ordered lists</span></span>

<span data-ttu-id="7fdc3-162">Para incluir um parágrafo ou outros elementos em um item numerado, alinhe o recuo com o primeiro caractere após o número do item.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-162">To include a paragraph or other elements under a numbered item, align indentation with the first character after the item number.</span></span> <span data-ttu-id="7fdc3-163">Todos os itens em uma lista numerada devem usar o número `1.` em vez de incrementar cada item.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-163">All items in a numbered listed should use the number `1.` rather than incrementing each item.</span></span> <span data-ttu-id="7fdc3-164">A renderização de Markdown incrementa o valor automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-164">Markdown rendering increments the value automatically.</span></span> <span data-ttu-id="7fdc3-165">Isso facilita a reorganização dos itens e padroniza o recuo do conteúdo subordinado.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-165">This makes reordering items easier and standardizes the indentation of subordinate content.</span></span>

<span data-ttu-id="7fdc3-166">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7fdc3-166">For example:</span></span>

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

<span data-ttu-id="7fdc3-167">O Markdown resultante é renderizado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="7fdc3-167">The resulting Markdown is rendered as follows:</span></span>

1. <span data-ttu-id="7fdc3-168">No primeiro elemento, insira um único espaço após o 1.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-168">For the first element, insert a single space after the 1.</span></span> <span data-ttu-id="7fdc3-169">Frases longas devem ser quebradas na próxima linha e devem ser alinhadas com o primeiro caractere após o marcador de lista numerada.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-169">Long sentences should be wrapped to the next line and must line up with the first character after the numbered list marker.</span></span>

   <span data-ttu-id="7fdc3-170">Para incluir um segundo elemento (como este), insira uma quebra de linha após a primeira e alinhe os recuos.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-170">To include a second element (like this one), insert a line break after the first and align indentations.</span></span> <span data-ttu-id="7fdc3-171">O recuo do segundo elemento deve ser alinhado com o primeiro caractere após o marcador de lista numerada.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-171">The indentation of the second element must line up with the first character after the numbered list marker.</span></span> <span data-ttu-id="7fdc3-172">Para itens com dígito único, como este, alinhe o recuo na coluna 4.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-172">For single digit items, like this one, you indent to column 4.</span></span> <span data-ttu-id="7fdc3-173">Para itens com dois dígitos, por exemplo, item número 10, alinhe o recuo na coluna 5.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-173">For double digits items, for example item number 10, you indent to column 5.</span></span>

1. <span data-ttu-id="7fdc3-174">O próximo item numerado começa aqui.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-174">The next numbered item starts here.</span></span>

### <a name="formatting-command-syntax-elements"></a><span data-ttu-id="7fdc3-175">Formatação de elementos de sintaxe de comando</span><span class="sxs-lookup"><span data-stu-id="7fdc3-175">Formatting command syntax elements</span></span>

- <span data-ttu-id="7fdc3-176">Sempre use o nome completo, sem abreviações, para cmdlets e parâmetros.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-176">Always use the full name for cmdlets and parameters.</span></span> <span data-ttu-id="7fdc3-177">Evite usar aliases, a menos que você esteja demonstrando o alias especificamente.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-177">Avoid using aliases unless you are specifically demonstrating the alias.</span></span>

- <span data-ttu-id="7fdc3-178">Em um parágrafo, palavras-chave de linguagem, nomes de cmdlet, variáveis e caminhos de arquivo devem ser colocados entre aspas invertidas (`` ` ``).</span><span class="sxs-lookup"><span data-stu-id="7fdc3-178">Within a paragraph, language keywords, cmdlet names, variables, and file paths should be wrapped in backtick (`` ` ``) characters.</span></span> <span data-ttu-id="7fdc3-179">Os nomes de propriedades, parâmetros e classes devem estar em **negrito**.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-179">Property, parameter, and class names should be **bold**.</span></span>

  <span data-ttu-id="7fdc3-180">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7fdc3-180">For example:</span></span>

  ~~~markdown
  The following code uses `Get-ChildItem` to list the contents of `C:\Windows` and assigns
  the output to the `$files` variable.

  ```powershell
  $files = Get-ChildItem C:\Windows
  ```
  ~~~

- <span data-ttu-id="7fdc3-181">Ao se referir a um parâmetro por nome, o nome deve estar em **negrito**.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-181">When referring to a parameter by name, the name should be **bold**.</span></span> <span data-ttu-id="7fdc3-182">Ao ilustrar o uso de um parâmetro com o prefixo de hífen, o parâmetro deve estar entre aspas invertidas.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-182">When illustrating the use of a parameter with the hyphen prefix, the parameter should be wrapped in backticks.</span></span> <span data-ttu-id="7fdc3-183">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7fdc3-183">For example:</span></span>

  ```markdown
  The parameter's name is **Name**, but it is typed as `-Name` when used on the command
  line as a parameter.
  ```

- <span data-ttu-id="7fdc3-184">Ao se referir a comandos externos (EXEs, scripts etc.), o nome do comando deve estar em negrito, em letras minúsculas (ou maiúsculas, se estiver no início de uma frase) e incluir a extensão de arquivo apropriada.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-184">When referring to external commands (EXEs, scripts, etc.), the command name should be bold, all lowercase (or capitalized if at the beginning of a sentence), and include the appropriate file extension.</span></span> <span data-ttu-id="7fdc3-185">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7fdc3-185">For example:</span></span>

  ```markdown
  For example, on Windows systems, you can use the `net start` and `net stop` commands
  to start and stop a service. **Sc.exe** is another service control tool for Windows.
  That name does not fit into the naming pattern for the **net.exe** service commands.
  ```

- <span data-ttu-id="7fdc3-186">Ao mostrar o exemplo de uso de um comando externo, o exemplo deve estar entre aspas invertidas.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-186">When showing example usage of an external command, the example should be wrapped in backticks.</span></span>
  <span data-ttu-id="7fdc3-187">Quando houver uma colisão de nomes com um alias, você deve incluir a extensão do arquivo no exemplo de comando.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-187">When there is a name collisions with an alias you must include the file extension in the command example.</span></span> <span data-ttu-id="7fdc3-188">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7fdc3-188">For example:</span></span>

  ```markdown
  To start the spooler service on a remote computer named DC01, you type `sc.exe \\DC01 start spooler`.
  ```

- <span data-ttu-id="7fdc3-189">Ao escrever um artigo conceitual (em vez de um conteúdo de referência), a primeira instância de um nome de cmdlet deve ser vinculada à documentação do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-189">When writing a conceptual article (as opposed to reference content), the first instance of a cmdlet name should be hyperlinked to the cmdlet documentation.</span></span> <span data-ttu-id="7fdc3-190">Não use aspas invertidas, negrito ou outra marcação dentro dos colchetes em um hiperlink.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-190">Do not use backticks, bold, or other markup inside the brackets of a hyperlink.</span></span>

  <span data-ttu-id="7fdc3-191">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7fdc3-191">For example:</span></span>

  ```markdown
  This [Write-Host](/powershell/module/Microsoft.PowerShell.Utility/Write-Host) cmdlet
  uses the **Object** parameter to ...
  ```

  <span data-ttu-id="7fdc3-192">Para obter mais informações, confira a seção [Hiperlinks](#hyperlinks) deste artigo.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-192">For more information, see [Hyperlinks](#hyperlinks) section of this article.</span></span>

### <a name="images"></a><span data-ttu-id="7fdc3-193">Imagens</span><span class="sxs-lookup"><span data-stu-id="7fdc3-193">Images</span></span>

<span data-ttu-id="7fdc3-194">A sintaxe que deve ser incluída em uma imagem é:</span><span class="sxs-lookup"><span data-stu-id="7fdc3-194">The syntax to include an image is:</span></span>

```markdown
![[alt text]](<folderPath>)

Example:
![Introduction](./media/overview/Introduction.png)
```

<span data-ttu-id="7fdc3-195">Em que `alt text` é uma breve descrição da imagem, e `<folder path>` é um caminho relativo para a imagem.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-195">Where `alt text` is a brief description of the image and `<folder path>` is a relative path to the image.</span></span> <span data-ttu-id="7fdc3-196">O texto alternativo é obrigatório em leitores de tela para deficientes visuais.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-196">Alternate text is required for screen readers for the visually impaired.</span></span> <span data-ttu-id="7fdc3-197">Ele também é útil em casos de bug no site que faça com que a imagem não seja renderizada.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-197">It is also useful in case there is a site bug where the image cannot be rendered.</span></span>

<span data-ttu-id="7fdc3-198">As imagens devem ser armazenadas em uma pasta `media/<article-name>` dentro de outra pasta que contém o artigo.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-198">Images should be stored in a `media/<article-name>` folder within the folder containing the article.</span></span>
<span data-ttu-id="7fdc3-199">As imagens não devem ser compartilhadas entre os artigos.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-199">Images should not be shared between articles.</span></span> <span data-ttu-id="7fdc3-200">Crie uma pasta que corresponda ao nome de arquivo do artigo na pasta `media`.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-200">Create a folder that matches the filename of your article under the `media` folder.</span></span> <span data-ttu-id="7fdc3-201">Copie as imagens desse artigo para a nova pasta.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-201">Copy the images for that article to that new folder.</span></span> <span data-ttu-id="7fdc3-202">Se uma imagem for usada por vários artigos, cada pasta de imagem deverá ter uma cópia desse arquivo de imagem.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-202">If an image is used by multiple articles, each image folder must have a copy of that image file.</span></span> <span data-ttu-id="7fdc3-203">Essa prática evita que a alteração de uma imagem em um artigo afete outro.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-203">This practice prevents a change to an image in one article affecting another article.</span></span>

<span data-ttu-id="7fdc3-204">Os seguintes tipos de arquivos de imagem são compatíveis: `*.png`, `*.gif`, `*.jpeg`, `*.jpg`, `*.svg`</span><span class="sxs-lookup"><span data-stu-id="7fdc3-204">The following image file types are supported: `*.png`, `*.gif`, `*.jpeg`, `*.jpg`, `*.svg`</span></span>

### <a name="markdown-extensions-supported-by-open-publishing"></a><span data-ttu-id="7fdc3-205">Extensões de Markdown para as quais o Open Publishing dá suporte</span><span class="sxs-lookup"><span data-stu-id="7fdc3-205">Markdown extensions supported by Open Publishing</span></span>

<span data-ttu-id="7fdc3-206">O [Pacote de Criação do Microsoft Docs](/contribute/how-to-write-docs-auth-pack) contém ferramentas que oferecem suporte a recursos exclusivos do nosso sistema de publicação.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-206">The [Microsoft Docs Authoring Pack](/contribute/how-to-write-docs-auth-pack) contains tools that support features unique to our publishing system.</span></span> <span data-ttu-id="7fdc3-207">Os alertas são uma extensão do Markdown para criar citações em bloco que são renderizadas no docs.microsoft.com com cores e ícones que indicam o significado do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-207">Alerts are a Markdown extension to create block quotes that render on docs.microsoft.com with colors and icons that indicate the significance of the content.</span></span> <span data-ttu-id="7fdc3-208">Há suporte para os seguintes tipos de alerta:</span><span class="sxs-lookup"><span data-stu-id="7fdc3-208">The following alert types are supported:</span></span>

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

<span data-ttu-id="7fdc3-209">Esses alertas ficam da seguinte forma no docs.microsoft.com:</span><span class="sxs-lookup"><span data-stu-id="7fdc3-209">These alerts look like this on docs.microsoft.com:</span></span>

> [!NOTE]
> <span data-ttu-id="7fdc3-210">Informações que o usuário deve conseguir notar mesmo que esteja correndo o texto.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-210">Information the user should notice even if skimming.</span></span>

> [!TIP]
> <span data-ttu-id="7fdc3-211">Informações opcionais para ajudar um usuário a ter mais sucesso.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-211">Optional information to help a user be more successful.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7fdc3-212">Informações essenciais necessárias para o sucesso do usuário.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-212">Essential information required for user success.</span></span>

> [!CAUTION]
> <span data-ttu-id="7fdc3-213">Possíveis consequências negativas de uma ação.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-213">Negative potential consequences of an action.</span></span>

> [!WARNING]
> <span data-ttu-id="7fdc3-214">Consequências perigosas de uma ação.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-214">Dangerous certain consequences of an action.</span></span>

## <a name="hyperlinks"></a><span data-ttu-id="7fdc3-215">Hiperlinks</span><span class="sxs-lookup"><span data-stu-id="7fdc3-215">Hyperlinks</span></span>

- <span data-ttu-id="7fdc3-216">Evite usar URLs simples.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-216">Avoid using bare URLs.</span></span> <span data-ttu-id="7fdc3-217">Os links devem usar a sintaxe do Markdown `[friendlyname](url-or-path)`</span><span class="sxs-lookup"><span data-stu-id="7fdc3-217">Links should use Markdown syntax `[friendlyname](url-or-path)`</span></span>
- <span data-ttu-id="7fdc3-218">URLs simples podem ser usadas quando necessário, mas devem estar entre aspas invertidas.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-218">Bare URLs may be used when necessary, but should be enclosed in backticks.</span></span> <span data-ttu-id="7fdc3-219">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7fdc3-219">For example:</span></span>

  ```markdown
  By default, if you do not specify this parameter, the DMTF standard resource URI
  `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.
  ```

- <span data-ttu-id="7fdc3-220">Os links de URL devem ser HTTPS quando possível.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-220">URL links should be HTTPS when possible.</span></span>
- <span data-ttu-id="7fdc3-221">Os links devem ter um nome amigável, geralmente o título do tópico vinculado</span><span class="sxs-lookup"><span data-stu-id="7fdc3-221">Links must have a friendly name, usually the title of the linked topic</span></span>
- <span data-ttu-id="7fdc3-222">Todos os itens da seção "links relacionados" na parte inferior devem ser hiperlinks.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-222">All items in the "related links" section at the bottom should be hyperlinked.</span></span>
- <span data-ttu-id="7fdc3-223">Não use aspas invertidas, negrito ou outra marcação dentro dos colchetes em um hiperlink.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-223">Do not use backticks, bold, or other markup inside the brackets of a hyperlink.</span></span>

### <a name="linking-to-other-content"></a><span data-ttu-id="7fdc3-224">Vincular a outros conteúdos</span><span class="sxs-lookup"><span data-stu-id="7fdc3-224">Linking to other content</span></span>

<span data-ttu-id="7fdc3-225">Existem dois tipos de hiperlinks compatíveis com o sistema de publicação: Links de arquivos e URLs.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-225">There are two types of hyperlinks supported by the publishing system: URLs and file links.</span></span>

<span data-ttu-id="7fdc3-226">Um link de URL pode ser um caminho de URL que é relativo à raiz do docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-226">A URL link can be a URL path that is relative to the root of docs.microsoft.com.</span></span> <span data-ttu-id="7fdc3-227">Ou uma URL absoluta que inclua a sintaxe completa da URL.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-227">Or an absolute URL that include the full URL syntax.</span></span> <span data-ttu-id="7fdc3-228">(Por exemplo, `https:/github.com/MicrosoftDocs/PowerShell-Docs`)</span><span class="sxs-lookup"><span data-stu-id="7fdc3-228">(For example: `https:/github.com/MicrosoftDocs/PowerShell-Docs`)</span></span>

- <span data-ttu-id="7fdc3-229">Use links de URL ao vincular conteúdo fora do PowerShell-Docs ou entre a referência de cmdlet e artigos conceituais no PowerShell-Docs.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-229">Use URL links when linking to content outside of PowerShell-Docs or between cmdlet reference and conceptual articles within PowerShell-docs.</span></span>
- <span data-ttu-id="7fdc3-230">A maneira mais simples de criar um link relativo é copiar a URL do seu navegador e remover `https://docs.microsoft.com/en-us` do valor colado no Markdown.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-230">The simplest way to link create a relative link is to copy the URL from your browser then remove `https://docs.microsoft.com/en-us` from the value you paste into markdown.</span></span>
   - <span data-ttu-id="7fdc3-231">Não inclua localidades em URLs nas propriedades da Microsoft (por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7fdc3-231">Do not include locales in URLs on Microsoft properties (eg.</span></span> <span data-ttu-id="7fdc3-232">remova "/en-us" da URL).</span><span class="sxs-lookup"><span data-stu-id="7fdc3-232">remove "/en-us" from URL).</span></span>
- <span data-ttu-id="7fdc3-233">Todas as URLs para sites externos devem usar HTTPS, a menos que isso não seja válido para o site de destino.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-233">All URLs to external websites should use HTTPS unless that is not valid for the target site.</span></span>

<span data-ttu-id="7fdc3-234">Um link de arquivo é usado para vincular um artigo de referência a outro ou um artigo conceitual a outro.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-234">A file link is used to link from one reference article to another, or from one conceptual article to another.</span></span> <span data-ttu-id="7fdc3-235">Se você precisar criar um link para um artigo de referência de uma versão específica do PowerShell, use um link de URL.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-235">If you need to link to a reference article for a specific version of PowerShell, then you need to use a URL link.</span></span>

- <span data-ttu-id="7fdc3-236">Os links de arquivo contêm um caminho de arquivo relativo (por exemplo: `../folder/file.md`)</span><span class="sxs-lookup"><span data-stu-id="7fdc3-236">File links contain a relative file path (for example: `../folder/file.md`)</span></span>
- <span data-ttu-id="7fdc3-237">Todos os caminhos de arquivo usam caracteres de barra (`/`)</span><span class="sxs-lookup"><span data-stu-id="7fdc3-237">All file paths use forward-slash (`/`) characters</span></span>

## <a name="formatting-code-samples"></a><span data-ttu-id="7fdc3-238">Exemplos de código de formatação</span><span class="sxs-lookup"><span data-stu-id="7fdc3-238">Formatting code samples</span></span>

<span data-ttu-id="7fdc3-239">O Markdown dá suporte a dois estilos de código diferentes:</span><span class="sxs-lookup"><span data-stu-id="7fdc3-239">Markdown supports two different code styles:</span></span>

- <span data-ttu-id="7fdc3-240">Extensão de código (embutido) – marcada por um único caractere de aspas invertidas (`` ` ``).</span><span class="sxs-lookup"><span data-stu-id="7fdc3-240">Code spans (inline) - marked by a single backtick (`` ` ``) character.</span></span> <span data-ttu-id="7fdc3-241">Usado dentro de um parágrafo, e não como um bloco independente.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-241">Used within a paragraph rather than as a standalone block.</span></span>
- <span data-ttu-id="7fdc3-242">Blocos de código – um bloco de várias linhas cercado por cadeias de caracteres com aspas triplas (`` ``` ``).</span><span class="sxs-lookup"><span data-stu-id="7fdc3-242">Code blocks - a multi-line block surrounded by triple-backtick (`` ``` ``) strings.</span></span> <span data-ttu-id="7fdc3-243">Os blocos de código também podem ter um rótulo de linguagem após as aspas invertidas.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-243">Code blocks may also have a language label following the backticks.</span></span> <span data-ttu-id="7fdc3-244">O rótulo de linguagem habilita o destaque da sintaxe para o conteúdo do bloco de código.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-244">The language label enables syntax highlighting for the contents of the code block.</span></span>

### <a name="using-code-blocks"></a><span data-ttu-id="7fdc3-245">Usar blocos de código</span><span class="sxs-lookup"><span data-stu-id="7fdc3-245">Using code blocks</span></span>

<span data-ttu-id="7fdc3-246">O Markdown permite que o recuo simbolize um bloco de código, mas esse padrão pode gerar problemas e deve ser evitado.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-246">Markdown allows for indentation to signify a code block, but this pattern can be problematic and should be avoided.</span></span> <span data-ttu-id="7fdc3-247">Todos os blocos de código devem estar contidos em um limite de códigos.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-247">All code blocks should be contained in a code fence.</span></span> <span data-ttu-id="7fdc3-248">Um limite de código é um bloco de código cercado por cadeias de caracteres de aspas triplas (`` ``` ``).</span><span class="sxs-lookup"><span data-stu-id="7fdc3-248">A code fence is a block of code surrounded by triple-backtick (`` ``` ``) strings.</span></span> <span data-ttu-id="7fdc3-249">Os marcadores de limite de código devem estar em sua própria linha antes e depois do exemplo de código.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-249">The code fence markers must be on their own line before and after the code sample.</span></span> <span data-ttu-id="7fdc3-250">O marcador no início do bloco de código pode ter um rótulo de linguagem opcional.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-250">The marker at the start of the code block may have an optional language label.</span></span> <span data-ttu-id="7fdc3-251">O OPS (Open Publishing System) da Microsoft usa o rótulo de linguagem para oferecer suporte ao recurso de destaque da sintaxe.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-251">Microsoft's Open Publishing System (OPS) uses the language label to support the syntax highlighting feature.</span></span>

<span data-ttu-id="7fdc3-252">O OPS também adiciona um botão **Copiar** que copia o conteúdo do bloco de código para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-252">OPS also adds a **Copy** button that copies the contents of the code block to the clipboard.</span></span> <span data-ttu-id="7fdc3-253">Isso permite colar rapidamente o código em um script para testar o exemplo de código.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-253">This allows you to quickly paste the code into a script for testing the code example.</span></span> <span data-ttu-id="7fdc3-254">No entanto, nem todos os exemplos em nossa documentação devem ser executados.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-254">However, not all examples in our documentation are intended to be run.</span></span> <span data-ttu-id="7fdc3-255">Alguns blocos de código são ilustrações simples de um conceito do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-255">Some code blocks are simple illustrations of a PowerShell concept.</span></span>

<span data-ttu-id="7fdc3-256">Existem dois tipos de blocos de código usados em nossa documentação:</span><span class="sxs-lookup"><span data-stu-id="7fdc3-256">There are two types code blocks used in our documentation:</span></span>

1. <span data-ttu-id="7fdc3-257">Exemplos ilustrativos</span><span class="sxs-lookup"><span data-stu-id="7fdc3-257">Illustrative examples</span></span>
2. <span data-ttu-id="7fdc3-258">Exemplos executáveis</span><span class="sxs-lookup"><span data-stu-id="7fdc3-258">Executable examples</span></span>

### <a name="syntax-code-blocks"></a><span data-ttu-id="7fdc3-259">Blocos de código de sintaxe</span><span class="sxs-lookup"><span data-stu-id="7fdc3-259">Syntax code blocks</span></span>

<span data-ttu-id="7fdc3-260">Este exemplo ilustra todos os parâmetros possíveis do cmdlet `Get-Command`.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-260">This example illustrates all the possible parameters of the `Get-Command` cmdlet.</span></span>

~~~markdown
```
Get-Command [-Verb <String[]>] [-Noun <String[]>] [-Module <String[]>]
  [-FullyQualifiedModule <ModuleSpecification[]>] [-TotalCount <Int32>] [-Syntax] [-ShowCommandInfo]
  [[-ArgumentList] <Object[]>] [-All] [-ListImported] [-ParameterName <String[]>]
  [-ParameterType <PSTypeName[]>] [<CommonParameters>]
```
~~~

<span data-ttu-id="7fdc3-261">Este exemplo descreve a instrução `for` em termos generalizados:</span><span class="sxs-lookup"><span data-stu-id="7fdc3-261">This example describes the `for` statement in generalized terms:</span></span>

~~~markdown
```
for (<init>; <condition>; <repeat>)
{<statement list>}
```
~~~

### <a name="illustrative-examples"></a><span data-ttu-id="7fdc3-262">Exemplos ilustrativos</span><span class="sxs-lookup"><span data-stu-id="7fdc3-262">Illustrative examples</span></span>

<span data-ttu-id="7fdc3-263">Exemplos ilustrativos são usados para explicar um conceito do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-263">Illustrative examples are used to explain a PowerShell concept.</span></span> <span data-ttu-id="7fdc3-264">Eles não devem ser copiados para a área de transferência a fim de serem executados.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-264">They are not meant to be copied to the clipboard for execution.</span></span> <span data-ttu-id="7fdc3-265">Eles são mais comumente usados como exemplos simples e fáceis de digitar.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-265">These are most commonly used for simple examples that are easy to type.</span></span>
<span data-ttu-id="7fdc3-266">Também são usados como exemplos de sintaxe em que se está ilustrando a sintaxe de um comando.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-266">They are also used for syntax examples where you are illustrating the syntax of a command.</span></span> <span data-ttu-id="7fdc3-267">O bloco de código pode conter a saída de exemplo do comando que está sendo ilustrado.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-267">The code block may contain example output from the command being illustrated.</span></span>

<span data-ttu-id="7fdc3-268">Confira um exemplo simples que ilustra os operadores de comparação do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7fdc3-268">Here is a simple example illustrating a PowerShell comparison operators:</span></span>

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

<span data-ttu-id="7fdc3-269">Observe que esse exemplo tem o prompt simplificado do PowerShell e mostra a saída resultante.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-269">Note that this example has the simplified PowerShell prompt and shows the resulting output.</span></span> <span data-ttu-id="7fdc3-270">Nesse caso, não pretendemos que o leitor copie nem execute esse exemplo.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-270">In this case, we don't intend the reader to copy and run this example.</span></span>

### <a name="executable-examples"></a><span data-ttu-id="7fdc3-271">Exemplos executáveis</span><span class="sxs-lookup"><span data-stu-id="7fdc3-271">Executable examples</span></span>

<span data-ttu-id="7fdc3-272">Exemplos mais complexos ou que são destinados à cópia e execução devem usar a seguinte marcação no estilo de bloco:</span><span class="sxs-lookup"><span data-stu-id="7fdc3-272">More complex examples or examples that are intended to be useful to copy and execute should use the following block-style markup:</span></span>

~~~markdown
```powershell
<PowerShell code goes here>
```
~~~

<span data-ttu-id="7fdc3-273">A saída exibida pelos comandos do PowerShell deve ser colocadas entre blocos de código de **Saída**, para evitar o destaque da sintaxe.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-273">The output displayed by PowerShell commands should be enclosed in an **Output** code block to prevent syntax highlighting.</span></span> <span data-ttu-id="7fdc3-274">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7fdc3-274">For example:</span></span>

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

<span data-ttu-id="7fdc3-275">O rótulo do código de **Saída** não é uma "linguagem" oficial à qual o sistema de destaque de sintaxe dá suporte.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-275">The **Output** code label is not an official "language" supported by the syntax highlighting system.</span></span>
<span data-ttu-id="7fdc3-276">No entanto, esse rótulo é útil porque o OPS adiciona o rótulo de "Saída" ao quadro da caixa de código na página da Web.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-276">However, this label is useful because OPS adds the "Output" label to the code box frame on the web page.</span></span> <span data-ttu-id="7fdc3-277">A caixa de código de "Saída" não possui destaque de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-277">The "Output" code box has no syntax highlighting.</span></span>

## <a name="coding-style-rules"></a><span data-ttu-id="7fdc3-278">Regras de estilo de codificação</span><span class="sxs-lookup"><span data-stu-id="7fdc3-278">Coding style rules</span></span>

### <a name="avoid-line-continuation-in-code-samples"></a><span data-ttu-id="7fdc3-279">Evitar a continuação de linha em exemplos de código</span><span class="sxs-lookup"><span data-stu-id="7fdc3-279">Avoid line continuation in code samples</span></span>

<span data-ttu-id="7fdc3-280">Evite usar caracteres de continuação de linha (`` ` ``) nos exemplos de código do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-280">Avoid using line continuation characters (`` ` ``) in PowerShell code examples.</span></span> <span data-ttu-id="7fdc3-281">Eles são difíceis de ver e podem causar problemas caso haja espaços extras no final da linha.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-281">These are hard to see and can cause problems if there are extra spaces at the end of the line.</span></span>

- <span data-ttu-id="7fdc3-282">Use os nivelamento do PowerShell para reduzir o comprimento da linha de cmdlets com muitos parâmetros.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-282">Use PowerShell splatting to reduce line length for cmdlets that have a lot of parameters.</span></span>
- <span data-ttu-id="7fdc3-283">Aproveite as quebras naturais de linha do PowerShell, como caracteres após a barra vertical (`|`), chaves, parênteses e colchetes.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-283">Take advantage of PowerShell's natural line break opportunities, like after pipe (`|`) characters, opening braces, parentheses, and brackets.</span></span>

### <a name="avoid-using-powershell-prompts-in-examples"></a><span data-ttu-id="7fdc3-284">Evitar o uso de prompts do PowerShell em exemplos</span><span class="sxs-lookup"><span data-stu-id="7fdc3-284">Avoid using PowerShell prompts in examples</span></span>

<span data-ttu-id="7fdc3-285">O uso da cadeia de caracteres de prompt é desencorajado e deve ser limitado a cenários que ilustram o uso da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-285">Use of the prompt string is discouraged and should be limited to scenarios that are meant to illustrate command line usage.</span></span> <span data-ttu-id="7fdc3-286">Para a maioria desses exemplos, a cadeia de caracteres de prompt deve ser `PS>`.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-286">For most of these examples, the prompt string should be `PS>`.</span></span> <span data-ttu-id="7fdc3-287">Esse prompt é independente dos indicadores específicos do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-287">This prompt is independent of OS-specific indicators.</span></span>

<span data-ttu-id="7fdc3-288">Os prompts são necessários para dar exemplos ilustrativos dos comandos que os alteram ou quando o caminho exibido é significativo para o cenário que está sendo ilustrado.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-288">Prompts are required for examples that illustrate commands that alter the prompt or when the path displayed is significant to the scenario being illustrated.</span></span> <span data-ttu-id="7fdc3-289">O exemplo a seguir ilustra como o prompt é alterado ao usar o provedor de Registro.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-289">The following example illustrates how the prompt changes when using the Registry provider.</span></span>

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

### <a name="do-not-use-aliases-in-examples"></a><span data-ttu-id="7fdc3-290">Não usar aliases em exemplos</span><span class="sxs-lookup"><span data-stu-id="7fdc3-290">Do not use aliases in examples</span></span>

<span data-ttu-id="7fdc3-291">Use sempre o nome completo de todos os cmdlets e parâmetros, a menos que esteja falando especificamente sobre o alias.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-291">You should always use the full name of all cmdlets and parameters unless you are specifically talking about the alias.</span></span> <span data-ttu-id="7fdc3-292">Os nomes de cmdlets e parâmetros devem usar a ortografia adequada definida no código.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-292">Cmdlet and parameter names must use the proper spelling defined in the code.</span></span>

### <a name="using-parameters-in-examples"></a><span data-ttu-id="7fdc3-293">Usar parâmetros em exemplos</span><span class="sxs-lookup"><span data-stu-id="7fdc3-293">Using parameters in examples</span></span>

<span data-ttu-id="7fdc3-294">Evite usar parâmetros posicionais.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-294">Avoid using positional parameters.</span></span> <span data-ttu-id="7fdc3-295">De maneira geral, sempre inclua o nome do parâmetro em um exemplo, mesmo que o parâmetro seja posicional.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-295">In general, you should use always include the parameter name in an example, even if the parameter positional.</span></span> <span data-ttu-id="7fdc3-296">Isso reduz a chance de confusão nos seus exemplos.</span><span class="sxs-lookup"><span data-stu-id="7fdc3-296">This reduces the chance of confusion in your examples.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7fdc3-297">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="7fdc3-297">Next steps</span></span>

[<span data-ttu-id="7fdc3-298">Editar a referência de cmdlet</span><span class="sxs-lookup"><span data-stu-id="7fdc3-298">Editing cmdlet reference</span></span>](editing-cmdlet-ref.md)

<!-- External URLs -->
[platyPS]: https://github.com/PowerShell/platyPS
[markdig]: https://github.com/lunet-io/markdig
[CommonMark]: https://spec.commonmark.org/
[atx]: https://github.github.com/gfm/#atx-headings
[pascal-case]: https://en.wikipedia.org/wiki/PascalCase
[reflow]: https://marketplace.visualstudio.com/items?itemName=marvhen.reflow-markdown
