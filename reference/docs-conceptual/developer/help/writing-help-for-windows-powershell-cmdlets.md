---
ms.date: 09/13/2016
ms.topic: reference
title: Escrever tópicos de ajuda para cmdlets do PowerShell
description: Escrever tópicos de ajuda para cmdlets do PowerShell
ms.openlocfilehash: b1deaa5998dbc54add93764db785d57afcc0a779
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658103"
---
# <a name="writing-help-for-powershell-cmdlets"></a><span data-ttu-id="6593a-103">Escrever tópicos de ajuda para cmdlets do PowerShell</span><span class="sxs-lookup"><span data-stu-id="6593a-103">Writing Help for PowerShell Cmdlets</span></span>

<span data-ttu-id="6593a-104">Os cmdlets do PowerShell podem ser úteis, mas a menos que os tópicos da ajuda expliquem claramente o que o cmdlet faz e como usá-lo, o cmdlet pode não ser usado ou, ainda pior, pode frustrar os usuários.</span><span class="sxs-lookup"><span data-stu-id="6593a-104">PowerShell cmdlets can be useful, but unless your Help topics clearly explain what the cmdlet does and how to use it, the cmdlet may not get used or, even worse, it might frustrate users.</span></span> <span data-ttu-id="6593a-105">O formato de arquivo de ajuda do cmdlet baseado em XML aprimora a consistência, mas a grande ajuda requer muito mais.</span><span class="sxs-lookup"><span data-stu-id="6593a-105">The XML-based cmdlet Help file format enhances consistency, but great help requires much more.</span></span>

<span data-ttu-id="6593a-106">Se você nunca escreveu a ajuda do cmdlet, examine as diretrizes a seguir.</span><span class="sxs-lookup"><span data-stu-id="6593a-106">If you have never written cmdlet Help, review the following guidelines.</span></span> <span data-ttu-id="6593a-107">O esquema XML necessário para criar o tópico de ajuda do cmdlet é descrito na seção a seguir.</span><span class="sxs-lookup"><span data-stu-id="6593a-107">The XML schema required to author the cmdlet Help topic is described in the following section.</span></span> <span data-ttu-id="6593a-108">Comece com [a criação do arquivo de ajuda do cmdlet](./how-to-create-the-cmdlet-help-file.md).</span><span class="sxs-lookup"><span data-stu-id="6593a-108">Start with [Creating the Cmdlet Help File](./how-to-create-the-cmdlet-help-file.md).</span></span> <span data-ttu-id="6593a-109">Esse tópico inclui uma descrição dos nós XML de nível superior.</span><span class="sxs-lookup"><span data-stu-id="6593a-109">That topic includes a description of the top-level XML nodes.</span></span>

## <a name="writing-guidelines-for-cmdlet-help"></a><span data-ttu-id="6593a-110">Diretrizes de escrita para a ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="6593a-110">Writing Guidelines for Cmdlet Help</span></span>

### <a name="write-well"></a><span data-ttu-id="6593a-111">Gravar bem</span><span class="sxs-lookup"><span data-stu-id="6593a-111">Write well</span></span>

<span data-ttu-id="6593a-112">Nada substitui um tópico bem escrito.</span><span class="sxs-lookup"><span data-stu-id="6593a-112">Nothing replaces a well-written topic.</span></span> <span data-ttu-id="6593a-113">Se você não for um escritor profissional, encontre um gravador ou editor para ajudá-lo.</span><span class="sxs-lookup"><span data-stu-id="6593a-113">If you are not a professional writer, find a writer or editor to help you.</span></span> <span data-ttu-id="6593a-114">Outra alternativa é copiar o texto de ajuda para o Microsoft Word e usar as verificações gramaticais e ortográficas para melhorar seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="6593a-114">Another alternative is to copy your Help text into Microsoft Word and use the grammar and spelling checks to improve your work.</span></span>

### <a name="write-simply"></a><span data-ttu-id="6593a-115">Escrever simplesmente</span><span class="sxs-lookup"><span data-stu-id="6593a-115">Write simply</span></span>

<span data-ttu-id="6593a-116">Use palavras e frases simples.</span><span class="sxs-lookup"><span data-stu-id="6593a-116">Use simple words and phrases.</span></span> <span data-ttu-id="6593a-117">Evite jargões.</span><span class="sxs-lookup"><span data-stu-id="6593a-117">Avoid jargon.</span></span> <span data-ttu-id="6593a-118">Considere que muitos leitores estão equipados apenas com um dicionário de idioma estrangeiro e o tópico da ajuda.</span><span class="sxs-lookup"><span data-stu-id="6593a-118">Consider that many readers are equipped only with a foreign-language dictionary and your Help topic.</span></span>

### <a name="write-consistently"></a><span data-ttu-id="6593a-119">Escreva de forma consistente</span><span class="sxs-lookup"><span data-stu-id="6593a-119">Write consistently</span></span>

<span data-ttu-id="6593a-120">A ajuda para os cmdlets relacionados deve ser semelhante (por exemplo, Get-x e Set-x).</span><span class="sxs-lookup"><span data-stu-id="6593a-120">Help for related cmdlets should be similar (for example, get-x and set-x).</span></span> <span data-ttu-id="6593a-121">Use as descrições padrão para parâmetros padrão, como **Force** e **InputObject**.</span><span class="sxs-lookup"><span data-stu-id="6593a-121">Use the standard descriptions for standard parameters, like **Force** and **InputObject**.</span></span> <span data-ttu-id="6593a-122">(Copie-os da ajuda para os cmdlets principais.) Use os termos padrão.</span><span class="sxs-lookup"><span data-stu-id="6593a-122">(Copy them from Help for the core cmdlets.) Use standard terms.</span></span> <span data-ttu-id="6593a-123">Por exemplo, use "Parameter", não "Argument" e use "cmdlet", não "Command" ou "command-let".</span><span class="sxs-lookup"><span data-stu-id="6593a-123">For example, use "parameter", not "argument", and use "cmdlet" not "command" or "command-let."</span></span>

### <a name="start-the-synopsis-with-a-verb"></a><span data-ttu-id="6593a-124">Iniciar o resumo com um verbo</span><span class="sxs-lookup"><span data-stu-id="6593a-124">Start the synopsis with a verb</span></span>

<span data-ttu-id="6593a-125">O campo Sinopse informa ao usuário o que o cmdlet faz, não o que é ou como ele funciona.</span><span class="sxs-lookup"><span data-stu-id="6593a-125">The synopsis field informs the user what the cmdlet does, not what it is or how it works.</span></span> <span data-ttu-id="6593a-126">Os verbos criam uma instrução baseada em tarefa que informa os usuários se esse cmdlet atende aos seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="6593a-126">Verbs create a task-based statement that informs users if this cmdlet meets their requirements.</span></span> <span data-ttu-id="6593a-127">Use verbos simples, como "Get", "Create" e "Change".</span><span class="sxs-lookup"><span data-stu-id="6593a-127">Use simple verbs like "get", "create", and "change."</span></span> <span data-ttu-id="6593a-128">Evite "set", que podem ser palavras vagas e sofisticadas como "Modify".</span><span class="sxs-lookup"><span data-stu-id="6593a-128">Avoid "set", which can be vague and fancy words like "modify".</span></span>

### <a name="focus-on-objects"></a><span data-ttu-id="6593a-129">Foco em objetos</span><span class="sxs-lookup"><span data-stu-id="6593a-129">Focus on objects</span></span>

<span data-ttu-id="6593a-130">A maioria dos cmdlets de "Get" exibe algo, mas sua função principal é obter um objeto.</span><span class="sxs-lookup"><span data-stu-id="6593a-130">Most "get" cmdlets display something, but their primary function is to get an object.</span></span> <span data-ttu-id="6593a-131">Em sua ajuda, concentre-se no objeto, para que os usuários entendam que a exibição padrão é uma das muitas e que eles podem usar os métodos e as propriedades do objeto que você recuperou para eles de maneiras diferentes.</span><span class="sxs-lookup"><span data-stu-id="6593a-131">In your Help, focus on the object, so that users understand that the default display is one of many, and that they can use the methods and properties of the object that you retrieved for them in different ways.</span></span>

### <a name="write-detailed-descriptions"></a><span data-ttu-id="6593a-132">Escrever descrições detalhadas</span><span class="sxs-lookup"><span data-stu-id="6593a-132">Write detailed descriptions</span></span>

<span data-ttu-id="6593a-133">Liste rapidamente tudo o que o cmdlet pode fazer na descrição detalhada.</span><span class="sxs-lookup"><span data-stu-id="6593a-133">Briefly list everything that the cmdlet can do in the detailed description.</span></span> <span data-ttu-id="6593a-134">Se a função main for alterar uma propriedade, mas o cmdlet puder alterar todas as propriedades, liste-a na descrição detalhada.</span><span class="sxs-lookup"><span data-stu-id="6593a-134">If the main function is to change one property, but the cmdlet can change all properties, list this in the detailed description.</span></span>

### <a name="use-conventional-syntax"></a><span data-ttu-id="6593a-135">Usar sintaxe convencional</span><span class="sxs-lookup"><span data-stu-id="6593a-135">Use conventional syntax</span></span>

<span data-ttu-id="6593a-136">Use o formato de Backus-Naur padrão, que é comum para a ajuda de linha de comando do UNIX e do Windows.</span><span class="sxs-lookup"><span data-stu-id="6593a-136">Use the standard Backus-Naur format which is common for Windows and UNIX command-line Help.</span></span>

### <a name="use-microsoft-net-types-for-parameter-values"></a><span data-ttu-id="6593a-137">Usar tipos de Microsoft .NET para valores de parâmetro</span><span class="sxs-lookup"><span data-stu-id="6593a-137">Use Microsoft .NET types for parameter values</span></span>

<span data-ttu-id="6593a-138">Os espaços reservados para valores de parâmetro (nas descrições de sintaxe e parâmetro) mostram os tipos de .NET Framework dos objetos que o parâmetro aceitará.</span><span class="sxs-lookup"><span data-stu-id="6593a-138">The placeholders for parameter values (in the syntax and parameter descriptions) show the .NET Framework types of the objects that the parameter will accept.</span></span> <span data-ttu-id="6593a-139">A equipe do PowerShell desenvolveu essa Convenção para ajudar a ensinar os usuários sobre o .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6593a-139">The PowerShell team developed this convention to help teach users about the .NET Framework.</span></span>

### <a name="write-complete-parameter-descriptions"></a><span data-ttu-id="6593a-140">Gravar descrições de parâmetros completas</span><span class="sxs-lookup"><span data-stu-id="6593a-140">Write complete parameter descriptions</span></span>

<span data-ttu-id="6593a-141">As descrições de parâmetro devem informar os usuários de duas coisas: o que o parâmetro faz (seu efeito) e o que eles devem digitar para os valores de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="6593a-141">Parameter descriptions must inform users of two things: what the parameter does (its effect) and what they must type for the parameter values.</span></span>

### <a name="write-practical-examples"></a><span data-ttu-id="6593a-142">Escrever exemplos práticos</span><span class="sxs-lookup"><span data-stu-id="6593a-142">Write practical examples</span></span>

<span data-ttu-id="6593a-143">Os exemplos devem mostrar como usar todos os parâmetros, mas a coisa mais importante é mostrar como usar o cmdlet em tarefas do mundo real.</span><span class="sxs-lookup"><span data-stu-id="6593a-143">The examples should show how to use all of the parameters, but the most important thing is to show how to use the cmdlet in real-world tasks.</span></span> <span data-ttu-id="6593a-144">Comece com um exemplo simples e escreva exemplos cada vez mais complexos.</span><span class="sxs-lookup"><span data-stu-id="6593a-144">Start with a simple example and write increasingly complex examples.</span></span> <span data-ttu-id="6593a-145">No exemplo final, mostre como usar o cmdlet em um pipeline.</span><span class="sxs-lookup"><span data-stu-id="6593a-145">In the final example, show how to use the cmdlet in a pipeline.</span></span>

### <a name="use-the-notes-field"></a><span data-ttu-id="6593a-146">Usar o campo observações</span><span class="sxs-lookup"><span data-stu-id="6593a-146">Use the Notes field</span></span>

<span data-ttu-id="6593a-147">Use o campo observações para explicar os conceitos que os usuários precisam para entender o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6593a-147">Use the Notes field to explain concepts that users need to understand the cmdlet.</span></span> <span data-ttu-id="6593a-148">Você também pode usar observações para ajudar os usuários a evitar erros comuns.</span><span class="sxs-lookup"><span data-stu-id="6593a-148">You can also use notes to help users avoid common errors.</span></span> <span data-ttu-id="6593a-149">Evite URLs à medida que elas forem alteradas.</span><span class="sxs-lookup"><span data-stu-id="6593a-149">Avoid URLs as they change.</span></span> <span data-ttu-id="6593a-150">Em vez disso, forneça aos usuários os termos para pesquisar.</span><span class="sxs-lookup"><span data-stu-id="6593a-150">Instead, provide users terms to search for.</span></span>

### <a name="test-your-help"></a><span data-ttu-id="6593a-151">Teste sua ajuda</span><span class="sxs-lookup"><span data-stu-id="6593a-151">Test your Help</span></span>

<span data-ttu-id="6593a-152">Teste a ajuda exatamente como você testa seu código.</span><span class="sxs-lookup"><span data-stu-id="6593a-152">Test the Help just like you test your code.</span></span> <span data-ttu-id="6593a-153">Faça com que amigos e colegas leiam o conteúdo da ajuda e forneçam comentários.</span><span class="sxs-lookup"><span data-stu-id="6593a-153">Have friends and colleagues read your Help content and provide feedback.</span></span> <span data-ttu-id="6593a-154">Você também pode solicitar comentários de grupos de notícias.</span><span class="sxs-lookup"><span data-stu-id="6593a-154">You can also solicit feedback from newsgroups.</span></span>

## <a name="see-also"></a><span data-ttu-id="6593a-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6593a-155">See Also</span></span>

 [<span data-ttu-id="6593a-156">Como criar o arquivo de ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="6593a-156">How to Create the Cmdlet Help File</span></span>](./how-to-create-the-cmdlet-help-file.md)

 [<span data-ttu-id="6593a-157">Como adicionar a sinopse e o nome do cmdlet a um tópico de ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="6593a-157">How to Add the Cmdlet Name and Synopsis to a Cmdlet Help Topic</span></span>](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="6593a-158">Como adicionar a descrição detalhada a um tópico de ajuda de cmdlet</span><span class="sxs-lookup"><span data-stu-id="6593a-158">How to Add the Detailed Description to a Cmdlet Help Topic</span></span>](./how-to-add-a-cmdlet-description.md)

 [<span data-ttu-id="6593a-159">Como adicionar sintaxe a um tópico de ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="6593a-159">How to Add Syntax to a Cmdlet Help Topic</span></span>](./how-to-add-syntax-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="6593a-160">Como adicionar parâmetros a um tópico de ajuda de cmdlet</span><span class="sxs-lookup"><span data-stu-id="6593a-160">How to Add Parameters to a Cmdlet Help Topic</span></span>](./how-to-add-parameter-information.md)

 [<span data-ttu-id="6593a-161">Como adicionar tipos de entrada a um tópico de ajuda de cmdlet</span><span class="sxs-lookup"><span data-stu-id="6593a-161">How to add Input Types to a Cmdlet Help Topic</span></span>](./how-to-add-input-types-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="6593a-162">Como adicionar valores retornados a um tópico de ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="6593a-162">How to Add Return Values to a Cmdlet Help Topic</span></span>](./how-to-add-return-values-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="6593a-163">Como adicionar notas a um tópico de ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="6593a-163">How to Add Notes to a Cmdlet Help Topic</span></span>](./how-to-add-notes-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="6593a-164">Como adicionar exemplos a um tópico de ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="6593a-164">How to Add Examples to a Cmdlet Help Topic</span></span>](./how-to-add-examples-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="6593a-165">Como adicionar links relacionados a um tópico de ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="6593a-165">How to Add Related Links to a Cmdlet Help Topic</span></span>](./how-to-add-related-links-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="6593a-166">SDK do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6593a-166">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
