---
title: Como adicionar exemplos a um tópico de ajuda do cmdlet
ms.date: 09/12/2016
ms.openlocfilehash: 33a1726f9d52b5a368d5df7962cc17ba9c45246a
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893434"
---
# <a name="how-to-add-examples-to-a-cmdlet-help-topic"></a><span data-ttu-id="93214-102">Como adicionar exemplos a um tópico de ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="93214-102">How to Add Examples to a Cmdlet Help Topic</span></span>

## <a name="things-to-know-about-examples-in-cmdlet-help"></a><span data-ttu-id="93214-103">Coisas que você precisa saber sobre exemplos na ajuda do cmdlet</span><span class="sxs-lookup"><span data-stu-id="93214-103">Things to Know about Examples in Cmdlet Help</span></span>

- <span data-ttu-id="93214-104">Lista todos os nomes de parâmetro no comando, mesmo quando os nomes de parâmetro são opcionais.</span><span class="sxs-lookup"><span data-stu-id="93214-104">List all of the parameter names in the command, even when the parameter names are optional.</span></span> <span data-ttu-id="93214-105">Isso ajuda o usuário a interpretar o comando facilmente.</span><span class="sxs-lookup"><span data-stu-id="93214-105">This helps the user to interpret the command easily.</span></span>

- <span data-ttu-id="93214-106">Evite aliases e nomes de parâmetros parciais, embora eles funcionem no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93214-106">Avoid aliases and partial parameter names, even though they work in PowerShell.</span></span>

- <span data-ttu-id="93214-107">Na descrição do exemplo, explique o racional da construção do comando.</span><span class="sxs-lookup"><span data-stu-id="93214-107">In the example description, explain the rational for the construction of the command.</span></span> <span data-ttu-id="93214-108">Explique por que você escolheu parâmetros e valores específicos e como você usa variáveis.</span><span class="sxs-lookup"><span data-stu-id="93214-108">Explain why you chose particular parameters and values, and how you use variables.</span></span>

- <span data-ttu-id="93214-109">Se o comando usar expressões, explique-as em detalhes.</span><span class="sxs-lookup"><span data-stu-id="93214-109">If the command uses expressions, explain them in detail.</span></span>

- <span data-ttu-id="93214-110">Se o comando usar propriedades e métodos de objetos, especialmente propriedades que não aparecem na exibição padrão, use o exemplo como uma oportunidade para informar ao usuário sobre o objeto.</span><span class="sxs-lookup"><span data-stu-id="93214-110">If the command uses properties and methods of objects, especially properties that do not appear in the default display, use the example as an opportunity tell the user about the object.</span></span>

## <a name="help-views-that-display-examples"></a><span data-ttu-id="93214-111">Exibições de ajuda que exibem exemplos</span><span class="sxs-lookup"><span data-stu-id="93214-111">Help Views that Display Examples</span></span>

<span data-ttu-id="93214-112">Os exemplos aparecem apenas nas exibições detalhadas e completas da ajuda do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="93214-112">Examples appear only in the Detailed and Full views of cmdlet Help.</span></span>

## <a name="adding-an-examples-node"></a><span data-ttu-id="93214-113">Adicionando um nó de exemplos</span><span class="sxs-lookup"><span data-stu-id="93214-113">Adding an Examples Node</span></span>

<span data-ttu-id="93214-114">O XML a seguir mostra como adicionar um nó de **exemplos** que contém um único nó de **exemplo** .</span><span class="sxs-lookup"><span data-stu-id="93214-114">The following XML shows how to add an **Examples** node that contains a single **Example** node.</span></span> <span data-ttu-id="93214-115">Adicione nós de exemplo adicionais para cada um dos exemplos que você deseja incluir no tópico.</span><span class="sxs-lookup"><span data-stu-id="93214-115">Add additional example nodes for each examples you want to include in the topic.</span></span>

```xml
<command:examples>
  <command:example>
  </command:example>
</command:examples>
```

## <a name="adding-an-example-title"></a><span data-ttu-id="93214-116">Adicionando um título de exemplo</span><span class="sxs-lookup"><span data-stu-id="93214-116">Adding an Example Title</span></span>

<span data-ttu-id="93214-117">O XML a seguir mostra como adicionar um **título** para o exemplo.</span><span class="sxs-lookup"><span data-stu-id="93214-117">The following XML shows how to add a **title** for the example.</span></span> <span data-ttu-id="93214-118">O **título** é usado para definir o exemplo de separação de outros exemplos.</span><span class="sxs-lookup"><span data-stu-id="93214-118">The **title** is used to set the example apart from other examples.</span></span> <span data-ttu-id="93214-119">O PowerShell usa um cabeçalho padrão que inclui um número de exemplo sequencial.</span><span class="sxs-lookup"><span data-stu-id="93214-119">PowerShell uses a standard header that includes a sequential example number.</span></span>

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
  </command:example>
</command:examples>
```

## <a name="adding-preceding-characters"></a><span data-ttu-id="93214-120">Adicionando caracteres precedentes</span><span class="sxs-lookup"><span data-stu-id="93214-120">Adding Preceding Characters</span></span>

<span data-ttu-id="93214-121">O XML a seguir mostra como adicionar caracteres, como o prompt do Windows PowerShell, que são exibidos imediatamente antes do comando de exemplo (sem nenhum espaço intermediário).</span><span class="sxs-lookup"><span data-stu-id="93214-121">The following XML shows how to add characters, such as the Windows PowerShell prompt, that are displayed immediately before the example command (without any intervening spaces).</span></span> <span data-ttu-id="93214-122">O PowerShell usa o prompt do Windows PowerShell: `C:\PS>` .</span><span class="sxs-lookup"><span data-stu-id="93214-122">PowerShell uses the Windows PowerShell prompt: `C:\PS>`.</span></span>

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
    <maml:Introduction>
      <maml:paragraph>C:\PS></maml:paragraph>
    </maml:Introduction>
</command:example>
</command:examples>
```

## <a name="adding-the-command"></a><span data-ttu-id="93214-123">Adicionando o comando</span><span class="sxs-lookup"><span data-stu-id="93214-123">Adding the Command</span></span>

<span data-ttu-id="93214-124">O XML a seguir mostra como adicionar o comando real do exemplo.</span><span class="sxs-lookup"><span data-stu-id="93214-124">The following XML shows how to add the actual command of the example.</span></span> <span data-ttu-id="93214-125">Ao adicionar o comando, digite o nome completo (não use alias) de cmdlets e parâmetros.</span><span class="sxs-lookup"><span data-stu-id="93214-125">When adding the command, type the entire name (do not use alias) of cmdlets and parameters.</span></span> <span data-ttu-id="93214-126">Além disso, use caracteres minúsculos sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="93214-126">Also, use lowercase characters whenever possible.</span></span>

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
    <maml:Introduction>
      <maml:paragraph>C:\PS></maml:paragraph>
    </maml:Introduction>
    <dev:code> command </dev:code>
</command:example>
</command:examples>
```

## <a name="adding-a-description"></a><span data-ttu-id="93214-127">Adicionando uma descrição</span><span class="sxs-lookup"><span data-stu-id="93214-127">Adding a Description</span></span>

<span data-ttu-id="93214-128">O XML a seguir mostra como adicionar uma descrição para o exemplo.</span><span class="sxs-lookup"><span data-stu-id="93214-128">The following XML shows how to add a description for the example.</span></span> <span data-ttu-id="93214-129">O PowerShell usa um único conjunto de `<maml:para>` marcas para a descrição, embora várias `<maml:para>` marcas possam ser usadas.</span><span class="sxs-lookup"><span data-stu-id="93214-129">PowerShell uses a single set of `<maml:para>` tags for the description, even though multiple `<maml:para>` tags can be used.</span></span>

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
    <maml:Introduction>
      <maml:paragraph>C:\PS></maml:paragraph>
    </maml:Introduction>
    <dev:code> command </dev:code>
    <dev:remarks>
      <maml:para> command description </maml:para>
    </dev:remarks>
</command:example>
</command:examples>
```

## <a name="adding-example-output"></a><span data-ttu-id="93214-130">Adicionando saída de exemplo</span><span class="sxs-lookup"><span data-stu-id="93214-130">Adding Example Output</span></span>

<span data-ttu-id="93214-131">O XML a seguir mostra como adicionar a saída do comando.</span><span class="sxs-lookup"><span data-stu-id="93214-131">The following XML shows how to add the output of the command.</span></span> <span data-ttu-id="93214-132">As informações dos resultados do comando são opcionais, mas, em alguns casos, é útil demonstrar o efeito de usar parâmetros específicos.</span><span class="sxs-lookup"><span data-stu-id="93214-132">The command results information is optional, but in some cases it is helpful to demonstrate the effect of using specific parameters.</span></span>
<span data-ttu-id="93214-133">O PowerShell usa dois conjuntos de `<maml:para>` marcas em branco para separar a saída do comando do comando.</span><span class="sxs-lookup"><span data-stu-id="93214-133">PowerShell uses two sets of blank `<maml:para>` tags to separate the command output from the command.</span></span>

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
    <maml:Introduction>
      <maml:paragraph>C:\PS></maml:paragraph>
    </maml:Introduction>
    <dev:code> command </dev:code>
    <dev:remarks>
      <maml:para> command description </maml:para>
      <maml:para></maml:para>
      <maml:para></maml:para>
      <maml:para> command output </maml:para>
</dev:remarks>
</command:example>
</command:examples>
```
