---
title: Tudo o que você queria saber sobre as tabelas de hash
description: As tabelas de hash são muito importantes no PowerShell, portanto, é bom entendê-las bem.
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: e386e2aa2f7b85bee4bf622fd9251ef7642cf16a
ms.sourcegitcommit: 57e577097085dc621bd797ef4a7e2854ea7d4e29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2021
ms.locfileid: "97980494"
---
# <a name="everything-you-wanted-to-know-about-hashtables"></a><span data-ttu-id="938c7-103">Tudo o que você queria saber sobre as tabelas de hash</span><span class="sxs-lookup"><span data-stu-id="938c7-103">Everything you wanted to know about hashtables</span></span>

<span data-ttu-id="938c7-104">Quero voltar um pouco e falar sobre as [tabelas de hash][].</span><span class="sxs-lookup"><span data-stu-id="938c7-104">I want to take a step back and talk about [hashtables][].</span></span> <span data-ttu-id="938c7-105">Eu as utilizo o tempo todo agora.</span><span class="sxs-lookup"><span data-stu-id="938c7-105">I use them all the time now.</span></span> <span data-ttu-id="938c7-106">Eu estava ensinando alguém sobre elas após nossa reunião de grupo de usuários na noite passada e percebi que já tive a mesma dúvida sobre esse assunto.</span><span class="sxs-lookup"><span data-stu-id="938c7-106">I was teaching someone about them after our user group meeting last night and I realized I had the same confusion about them as he had.</span></span> <span data-ttu-id="938c7-107">As tabelas de hash são muito importantes no PowerShell, portanto, é bom entendê-las bem.</span><span class="sxs-lookup"><span data-stu-id="938c7-107">Hashtables are really important in PowerShell so it's good to have a solid understanding of them.</span></span>

> [!NOTE]
> <span data-ttu-id="938c7-108">A [versão original][] deste artigo foi publicada no blog escrito por [@KevinMarquette][].</span><span class="sxs-lookup"><span data-stu-id="938c7-108">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="938c7-109">A equipe do PowerShell agradece a Kevin por compartilhar o conteúdo conosco.</span><span class="sxs-lookup"><span data-stu-id="938c7-109">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="938c7-110">Confira o blog dele em [PowerShellExplained.com][].</span><span class="sxs-lookup"><span data-stu-id="938c7-110">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="hashtable-as-a-collection-of-things"></a><span data-ttu-id="938c7-111">A tabela de hash como uma coleção de coisas</span><span class="sxs-lookup"><span data-stu-id="938c7-111">Hashtable as a collection of things</span></span>

<span data-ttu-id="938c7-112">Primeiro, quero que você enxergue a **tabela de hash** como uma coleção, conforme a definição tradicional desse recurso.</span><span class="sxs-lookup"><span data-stu-id="938c7-112">I want you to first see a **Hashtable** as a collection in the traditional definition of a hashtable.</span></span> <span data-ttu-id="938c7-113">Essa definição proporciona uma compreensão fundamental de como elas funcionam, e isso será muito útil ao empregá-las para coisas mais avançadas no futuro.</span><span class="sxs-lookup"><span data-stu-id="938c7-113">This definition gives you a fundamental understanding of how they work when they get used for more advanced stuff later.</span></span> <span data-ttu-id="938c7-114">Pular essa compreensão fundamental, muitas vezes, pode gerar confusão.</span><span class="sxs-lookup"><span data-stu-id="938c7-114">Skipping this understanding is often a source of confusion.</span></span>

## <a name="what-is-an-array"></a><span data-ttu-id="938c7-115">O que é uma matriz?</span><span class="sxs-lookup"><span data-stu-id="938c7-115">What is an array?</span></span>

<span data-ttu-id="938c7-116">Antes de falar sobre o que é uma **tabela de hash** eu preciso mencionar as [matrizes][].</span><span class="sxs-lookup"><span data-stu-id="938c7-116">Before I jump into what a **Hashtable** is, I need to mention [arrays][] first.</span></span> <span data-ttu-id="938c7-117">No âmbito desta discussão, a matriz é uma lista ou coleção de valores ou objetos.</span><span class="sxs-lookup"><span data-stu-id="938c7-117">For the purpose of this discussion, an array is a list or collection of values or objects.</span></span>

```powershell
$array = @(1,2,3,5,7,11)
```

<span data-ttu-id="938c7-118">Depois de armazenar seus itens em uma matriz, você poderá usar o `foreach` para percorrer cada elemento da matriz sequencialmente ou poderá usar um índice para acessar cada elemento da matriz individualmente.</span><span class="sxs-lookup"><span data-stu-id="938c7-118">Once you have your items into an array, you can either use `foreach` to iterate over the list or use an index to access individual elements in the array.</span></span>

```powershell
foreach($item in $array)
{
    Write-Output $item
}

Write-Output $array[3]
```

<span data-ttu-id="938c7-119">Você também pode atualizar valores usando um índice da mesma maneira.</span><span class="sxs-lookup"><span data-stu-id="938c7-119">You can also update values using an index in the same way.</span></span>

```powershell
$array[2] = 13
```

<span data-ttu-id="938c7-120">Isso é apenas uma breve introdução sobre as matrizes, mas é suficiente para contextualizá-las e permitir que nos aprofundemos nas tabelas de hash.</span><span class="sxs-lookup"><span data-stu-id="938c7-120">I just scratched the surface on arrays but that should put them into the right context as I move onto hashtables.</span></span>

## <a name="what-is-a-hashtable"></a><span data-ttu-id="938c7-121">O que é uma tabela de hash?</span><span class="sxs-lookup"><span data-stu-id="938c7-121">What is a hashtable?</span></span>

<span data-ttu-id="938c7-122">Vamos começar com uma descrição técnica básica do que são as tabelas de hash no sentido geral e depois veremos as outras formas de uso exploradas pelo PowerShell.</span><span class="sxs-lookup"><span data-stu-id="938c7-122">I'm going to start with a basic technical description of what hashtables are, in the general sense, before I shift into the other ways PowerShell uses them.</span></span>

<span data-ttu-id="938c7-123">Uma tabela de hash é uma estrutura de dados muito parecida com uma matriz, exceto pelo fato de que você armazena cada valor (objeto) usando uma chave.</span><span class="sxs-lookup"><span data-stu-id="938c7-123">A hashtable is a data structure, much like an array, except you store each value (object) using a key.</span></span> <span data-ttu-id="938c7-124">Trata-se de um esquema de armazenamento básico de chave/valor.</span><span class="sxs-lookup"><span data-stu-id="938c7-124">It's a basic key/value store.</span></span> <span data-ttu-id="938c7-125">Primeiro, criamos uma tabela de hash vazia.</span><span class="sxs-lookup"><span data-stu-id="938c7-125">First, we create an empty hashtable.</span></span>

```powershell
$ageList = @{}
```

<span data-ttu-id="938c7-126">Observe que usamos chaves, em vez de parênteses, para definir uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="938c7-126">Notice that braces, instead of parentheses, are used to define a hashtable.</span></span> <span data-ttu-id="938c7-127">Em seguida, adicionamos um item usando uma chave, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="938c7-127">Then we add an item using a key like this:</span></span>

```powershell
$key = 'Kevin'
$value = 36
$ageList.add( $key, $value )

$ageList.add( 'Alex', 9 )
```

<span data-ttu-id="938c7-128">O nome da pessoa é a chave e a idade da pessoa é o valor que queremos salvar.</span><span class="sxs-lookup"><span data-stu-id="938c7-128">The person's name is the key and their age is the value that I want to save.</span></span>

## <a name="using-the-brackets-for-access"></a><span data-ttu-id="938c7-129">Usando os colchetes para acesso</span><span class="sxs-lookup"><span data-stu-id="938c7-129">Using the brackets for access</span></span>

<span data-ttu-id="938c7-130">Depois de adicionar os valores desejados à tabela de hash, você poderá acessá-los novamente por meio das mesmas chaves (em vez de usar índices numéricos, como é feito nas matrizes).</span><span class="sxs-lookup"><span data-stu-id="938c7-130">Once you add your values to the hashtable, you can pull them back out using that same key (instead of using a numeric index like you would have for an array).</span></span>

```powershell
$ageList['Kevin']
$ageList['Alex']
```

<span data-ttu-id="938c7-131">Quando queremos recuperar a idade de Kevin, usamos o nome dele para poder acessá-la.</span><span class="sxs-lookup"><span data-stu-id="938c7-131">When I want Kevin's age, I use his name to access it.</span></span> <span data-ttu-id="938c7-132">Também podemos usar essa abordagem para adicionar ou atualizar valores na tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="938c7-132">We can use this approach to add or update values into the hashtable too.</span></span> <span data-ttu-id="938c7-133">Isso é exatamente como usar a função `add()` acima.</span><span class="sxs-lookup"><span data-stu-id="938c7-133">This is just like using the `add()` function above.</span></span>

```powershell
$ageList = @{}

$key = 'Kevin'
$value = 36
$ageList[$key] = $value

$ageList['Alex'] = 9
```

<span data-ttu-id="938c7-134">Há também outra sintaxe que pode ser usada para acessar e atualizar os valores armazenados em uma tabela de hash, mas será abordada em uma seção futura.</span><span class="sxs-lookup"><span data-stu-id="938c7-134">There's another syntax you can use for accessing and updating values that I'll cover in a later section.</span></span> <span data-ttu-id="938c7-135">Se você estiver chegando ao PowerShell após trabalhar com outras linguagens, esses exemplos deverão corresponder à forma como você pode ter usado as tabelas de hash no passado.</span><span class="sxs-lookup"><span data-stu-id="938c7-135">If you're coming to PowerShell from another language, these examples should fit in with how you may have used hashtables before.</span></span>

### <a name="creating-hashtables-with-values"></a><span data-ttu-id="938c7-136">Criando tabelas de hash com valores</span><span class="sxs-lookup"><span data-stu-id="938c7-136">Creating hashtables with values</span></span>

<span data-ttu-id="938c7-137">Até o momento, criamos apenas uma tabela de hash vazia para esses exemplos.</span><span class="sxs-lookup"><span data-stu-id="938c7-137">So far I've created an empty hashtable for these examples.</span></span> <span data-ttu-id="938c7-138">Você pode preencher previamente as chaves e os valores ao criar tabelas de hash.</span><span class="sxs-lookup"><span data-stu-id="938c7-138">You can pre-populate the keys and values when you create them.</span></span>

```powershell
$ageList = @{
    Kevin = 36
    Alex  = 9
}
```

### <a name="as-a-lookup-table"></a><span data-ttu-id="938c7-139">Como uma tabela de pesquisa</span><span class="sxs-lookup"><span data-stu-id="938c7-139">As a lookup table</span></span>

<span data-ttu-id="938c7-140">O grande benefício desse tipo de tabela de hash é que podemos usá-lo como uma tabela de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="938c7-140">The real value of this type of a hashtable is that you can use them as a lookup table.</span></span> <span data-ttu-id="938c7-141">Veja um exemplo simples.</span><span class="sxs-lookup"><span data-stu-id="938c7-141">Here is a simple example.</span></span>

```powershell
$environments = @{
    Prod = 'SrvProd05'
    QA   = 'SrvQA02'
    Dev  = 'SrvDev12'
}

$server = $environments[$env]
```

<span data-ttu-id="938c7-142">Neste exemplo, você especifica um ambiente para a variável `$env` e ela escolherá o servidor correto.</span><span class="sxs-lookup"><span data-stu-id="938c7-142">In this example, you specify an environment for the `$env` variable and it will pick the correct server.</span></span> <span data-ttu-id="938c7-143">Você pode usar uma `switch($env){...}` para esse tipo de seleção, mas a tabela de hash é uma opção interessante.</span><span class="sxs-lookup"><span data-stu-id="938c7-143">You could use a `switch($env){...}` for a selection like this but a hashtable is a nice option.</span></span>

<span data-ttu-id="938c7-144">E fica ainda melhor quando você cria dinamicamente a tabela de pesquisa para uso posterior.</span><span class="sxs-lookup"><span data-stu-id="938c7-144">This gets even better when you dynamically build the lookup table to use it later.</span></span> <span data-ttu-id="938c7-145">Então, pense em usar essa abordagem quando precisar fazer a referência cruzada de algo.</span><span class="sxs-lookup"><span data-stu-id="938c7-145">So think about using this approach when you need to cross reference something.</span></span> <span data-ttu-id="938c7-146">Acho que veríamos ainda mais esse cenário se o PowerShell não fosse tão bom na filtragem no pipe com `Where-Object`.</span><span class="sxs-lookup"><span data-stu-id="938c7-146">I think we would see this even more if PowerShell wasn't so good at filtering on the pipe with `Where-Object`.</span></span> <span data-ttu-id="938c7-147">Se, em algum momento, você se encontrar em uma situação em que o desempenho é importante, essa abordagem deve ser considerada.</span><span class="sxs-lookup"><span data-stu-id="938c7-147">If you're ever in a situation where performance matters, this approach needs to be considered.</span></span>

<span data-ttu-id="938c7-148">Não vou afirmar categoricamente que é mais rápida em todos os casos, mas se encaixa na seguinte regra geral: [Se o desempenho for importante, teste-o][].</span><span class="sxs-lookup"><span data-stu-id="938c7-148">I won't say that it's faster, but it does fit into the rule of [If performance matters, test it][].</span></span>

#### <a name="multiselection"></a><span data-ttu-id="938c7-149">Seleção múltipla</span><span class="sxs-lookup"><span data-stu-id="938c7-149">Multiselection</span></span>

<span data-ttu-id="938c7-150">De modo geral, uma tabela de hash equivale a um conjunto de pares de chave/valor em que você fornece uma chave e obtém um valor.</span><span class="sxs-lookup"><span data-stu-id="938c7-150">Generally, you think of a hashtable as a key/value pair, where you provide one key and get one value.</span></span> <span data-ttu-id="938c7-151">O PowerShell permite que você forneça uma matriz de chaves para obter vários valores.</span><span class="sxs-lookup"><span data-stu-id="938c7-151">PowerShell allows you to provide an array of keys to get multiple values.</span></span>

```powershell
$environments[@('QA','DEV')]
$environments[('QA','DEV')]
$environments['QA','DEV']
```

<span data-ttu-id="938c7-152">Neste exemplo, usamos a mesma tabela de hash de pesquisa acima e fornecemos três estilos de matriz diferentes para obter os valores correspondentes.</span><span class="sxs-lookup"><span data-stu-id="938c7-152">In this example, I use the same lookup hashtable from above and provide three different array styles to get the matches.</span></span> <span data-ttu-id="938c7-153">Essa é uma joia preciosa do PowerShell que a maioria das pessoas não conhece.</span><span class="sxs-lookup"><span data-stu-id="938c7-153">This is a hidden gem in PowerShell that most people aren't aware of.</span></span>

## <a name="iterating-hashtables"></a><span data-ttu-id="938c7-154">Percorrendo os elementos das tabelas de hash</span><span class="sxs-lookup"><span data-stu-id="938c7-154">Iterating hashtables</span></span>

<span data-ttu-id="938c7-155">Como uma tabela de hash é uma coleção de pares de chave/valor, você percorre seus elementos de maneira diferente do que faria com uma matriz ou uma lista normal de itens.</span><span class="sxs-lookup"><span data-stu-id="938c7-155">Because a hashtable is a collection of key/value pairs, you iterate over it differently than you do for an array or a normal list of items.</span></span>

<span data-ttu-id="938c7-156">A primeira coisa a ser observada é que, se você armazenar a tabela de hash em um pipe, ele a tratará como apenas um objeto.</span><span class="sxs-lookup"><span data-stu-id="938c7-156">The first thing to notice is that if you pipe your hashtable, the pipe treats it like one object.</span></span>

```powershell
PS> $ageList | Measure-Object
count : 1
```

<span data-ttu-id="938c7-157">Embora a propriedade `.count` informe quantos valores ela contém.</span><span class="sxs-lookup"><span data-stu-id="938c7-157">Even though the `.count` property tells you how many values it contains.</span></span>

```powershell
PS> $ageList.count
2
```

<span data-ttu-id="938c7-158">Você contorna esse problema usando a propriedade `.values`, se tudo o que você precisa são os valores.</span><span class="sxs-lookup"><span data-stu-id="938c7-158">You get around this issue by using the `.values` property if all you need is just the values.</span></span>

```powershell
PS> $ageList.values | Measure-Object -Average
Count   : 2
Average : 22.5
```

<span data-ttu-id="938c7-159">Em geral, é mais útil enumerar as chaves e usá-las para acessar os valores.</span><span class="sxs-lookup"><span data-stu-id="938c7-159">It's often more useful to enumerate the keys and use them to access the values.</span></span>

```powershell
PS> $ageList.keys | ForEach-Object{
    $message = '{0} is {1} years old!' -f $_, $ageList[$_]
    Write-Output $message
}
Kevin is 36 years old
Alex is 9 years old
```

<span data-ttu-id="938c7-160">Aqui está o mesmo exemplo com um loop do `foreach(){...}`.</span><span class="sxs-lookup"><span data-stu-id="938c7-160">Here is the same example with a `foreach(){...}` loop.</span></span>

```powershell
foreach($key in $ageList.keys)
{
    $message = '{0} is {1} years old' -f $key, $ageList[$key]
    Write-Output $message
}
```

<span data-ttu-id="938c7-161">Estamos percorrendo cada chave da tabela de hash e, em seguida, usando-a para acessar o valor correspondente.</span><span class="sxs-lookup"><span data-stu-id="938c7-161">We are walking each key in the hashtable and then using it to access the value.</span></span> <span data-ttu-id="938c7-162">Esse é um padrão comum ao trabalhar com as tabelas de hash como coleção.</span><span class="sxs-lookup"><span data-stu-id="938c7-162">This is a common pattern when working with hashtables as a collection.</span></span>

### <a name="getenumerator"></a><span data-ttu-id="938c7-163">GetEnumerator()</span><span class="sxs-lookup"><span data-stu-id="938c7-163">GetEnumerator()</span></span>

<span data-ttu-id="938c7-164">Isso nos leva ao `GetEnumerator()` para percorrer os elementos da nossa tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="938c7-164">That brings us to `GetEnumerator()` for iterating over our hashtable.</span></span>

```powershell
$ageList.GetEnumerator() | ForEach-Object{
    $message = '{0} is {1} years old!' -f $_.key, $_.value
    Write-Output $message
}
```

<span data-ttu-id="938c7-165">O enumerador fornece cada par de chave/valor, um após o outro.</span><span class="sxs-lookup"><span data-stu-id="938c7-165">The enumerator gives you each key/value pair one after another.</span></span> <span data-ttu-id="938c7-166">Ele foi projetado especificamente para esse caso de uso.</span><span class="sxs-lookup"><span data-stu-id="938c7-166">It was designed specifically for this use case.</span></span> <span data-ttu-id="938c7-167">Agradeço a [Mark Kraus](https://get-PowerShellblog.blogspot.com) por me lembrar disso.</span><span class="sxs-lookup"><span data-stu-id="938c7-167">Thank you to [Mark Kraus](https://get-PowerShellblog.blogspot.com) for reminding me of this one.</span></span>

### <a name="badenumeration"></a><span data-ttu-id="938c7-168">BadEnumeration</span><span class="sxs-lookup"><span data-stu-id="938c7-168">BadEnumeration</span></span>

<span data-ttu-id="938c7-169">Um detalhe importante é que não podemos modificar uma tabela de hash enquanto ela está sendo enumerada.</span><span class="sxs-lookup"><span data-stu-id="938c7-169">One important detail is that you can't modify a hashtable while it's being enumerated.</span></span> <span data-ttu-id="938c7-170">Se começarmos com nosso exemplo básico do `$environments`:</span><span class="sxs-lookup"><span data-stu-id="938c7-170">If we start with our basic `$environments` example:</span></span>

```powershell
$environments = @{
    Prod = 'SrvProd05'
    QA   = 'SrvQA02'
    Dev  = 'SrvDev12'
}
```

<span data-ttu-id="938c7-171">E a tentativa de definir toda chave ao mesmo valor do servidor não funciona.</span><span class="sxs-lookup"><span data-stu-id="938c7-171">And trying to set every key to the same server value fails.</span></span>

```powershell
$environments.Keys | ForEach-Object {
    $environments[$_] = 'SrvDev03'
}

An error occurred while enumerating through a collection: Collection was modified; enumeration operation may not execute.
+ CategoryInfo          : InvalidOperation: tableEnumerator:HashtableEnumerator) [], RuntimeException
+ FullyQualifiedErrorId : BadEnumeration
```

<span data-ttu-id="938c7-172">Isso também não vai funcionar, embora pareça que não haja problema:</span><span class="sxs-lookup"><span data-stu-id="938c7-172">This will also fail even though it looks like it should also be fine:</span></span>

```powershell
foreach($key in $environments.keys) {
    $environments[$key] = 'SrvDev03'
}

Collection was modified; enumeration operation may not execute.
    + CategoryInfo          : OperationStopped: (:) [], InvalidOperationException
    + FullyQualifiedErrorId : System.InvalidOperationException
```

<span data-ttu-id="938c7-173">O truque para essa situação é clonar as chaves antes de fazer a enumeração.</span><span class="sxs-lookup"><span data-stu-id="938c7-173">The trick to this situation is to clone the keys before doing the enumeration.</span></span>

```powershell
$environments.Keys.Clone() | ForEach-Object {
    $environments[$_] = 'SrvDev03'
}
```

## <a name="hashtable-as-a-collection-of-properties"></a><span data-ttu-id="938c7-174">A tabela de hash como uma coleção de propriedades</span><span class="sxs-lookup"><span data-stu-id="938c7-174">Hashtable as a collection of properties</span></span>

<span data-ttu-id="938c7-175">Até agora, os objetos que colocamos em nossa tabela de hash eram todos do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="938c7-175">So far the type of objects we placed in our hashtable were all the same type of object.</span></span> <span data-ttu-id="938c7-176">Usamos a idade nos exemplos anteriores e a chave era o nome da pessoa.</span><span class="sxs-lookup"><span data-stu-id="938c7-176">I used ages in all those examples and the key was the person's name.</span></span> <span data-ttu-id="938c7-177">Essa é uma excelente abordagem quando cada objeto da coleção em questão tem um nome exclusivo.</span><span class="sxs-lookup"><span data-stu-id="938c7-177">This is a great way to look at it when your collection of objects each have a name.</span></span> <span data-ttu-id="938c7-178">Outra forma comum de usar as tabelas de hash no PowerShell é manter uma coleção de propriedades em que a chave é o nome da propriedade.</span><span class="sxs-lookup"><span data-stu-id="938c7-178">Another common way to use hashtables in PowerShell is to hold a collection of properties where the key is the name of the property.</span></span> <span data-ttu-id="938c7-179">Vamos analisar essa ideia no próximo exemplo.</span><span class="sxs-lookup"><span data-stu-id="938c7-179">I'll step into that idea in this next example.</span></span>

### <a name="property-based-access"></a><span data-ttu-id="938c7-180">Acesso baseado na propriedade</span><span class="sxs-lookup"><span data-stu-id="938c7-180">Property-based access</span></span>

<span data-ttu-id="938c7-181">O uso do acesso baseado na propriedade altera a dinâmica das tabelas de hash e a forma como você pode usá-las no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="938c7-181">The use of property-based access changes the dynamics of hashtables and how you can use them in PowerShell.</span></span> <span data-ttu-id="938c7-182">Aqui está nosso exemplo anterior, mas agora usando as propriedades como chaves.</span><span class="sxs-lookup"><span data-stu-id="938c7-182">Here is our usual example from above treating the keys as properties.</span></span>

```powershell
$ageList = @{}
$ageList.Kevin = 35
$ageList.Alex = 9
```

<span data-ttu-id="938c7-183">Assim como aconteceu nos exemplos acima, aqui também as chaves são adicionadas caso ainda não existam na tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="938c7-183">Just like the examples above, this example adds those keys if they don't exist in the hashtable already.</span></span> <span data-ttu-id="938c7-184">Dependendo da forma como você define suas chaves e de quais são seus valores, essa abordagem pode parecer perfeita ou pode soar um pouco estranha.</span><span class="sxs-lookup"><span data-stu-id="938c7-184">Depending on how you defined your keys and what your values are, this is either a little strange or a perfect fit.</span></span> <span data-ttu-id="938c7-185">O exemplo da lista de idades funcionou muito até esse ponto.</span><span class="sxs-lookup"><span data-stu-id="938c7-185">The age list example has worked great up until this point.</span></span> <span data-ttu-id="938c7-186">Porém, daqui em diante, vamos precisar de um novo exemplo para que as coisas soem mais naturais.</span><span class="sxs-lookup"><span data-stu-id="938c7-186">We need a new example for this to feel right going forward.</span></span>

```powershell
$person = @{
    name = 'Kevin'
    age  = 36
}
```

<span data-ttu-id="938c7-187">E podemos adicionar e acessar atributos no `$person` dessa forma.</span><span class="sxs-lookup"><span data-stu-id="938c7-187">And we can add and access attributes on the `$person` like this.</span></span>

```powershell
$person.city = 'Austin'
$person.state = 'TX'
```

<span data-ttu-id="938c7-188">De repente, essa tabela de hash começa a se parecer e se comportar como um objeto.</span><span class="sxs-lookup"><span data-stu-id="938c7-188">All of a sudden this hashtable starts to feel and act like an object.</span></span> <span data-ttu-id="938c7-189">Ainda é uma coleção de coisas, portanto, todos os exemplos acima ainda se aplicam.</span><span class="sxs-lookup"><span data-stu-id="938c7-189">It's still a collection of things, so all the examples above still apply.</span></span> <span data-ttu-id="938c7-190">Nós apenas a abordamos sob um ponto de vista diferente.</span><span class="sxs-lookup"><span data-stu-id="938c7-190">We just approach it from a different point of view.</span></span>

### <a name="checking-for-keys-and-values"></a><span data-ttu-id="938c7-191">Verificando chaves e valores</span><span class="sxs-lookup"><span data-stu-id="938c7-191">Checking for keys and values</span></span>

<span data-ttu-id="938c7-192">Na maioria dos casos, você pode apenas testar o valor com algo assim:</span><span class="sxs-lookup"><span data-stu-id="938c7-192">In most cases, you can just test for the value with something like this:</span></span>

```powershell
if( $person.age ){...}
```

<span data-ttu-id="938c7-193">É algo simples, mas que já foi a fonte de muitos bugs para mim, pois minha lógica estava ignorando um detalhe importante.</span><span class="sxs-lookup"><span data-stu-id="938c7-193">It's simple but has been the source of many bugs for me because I was overlooking one important detail in my logic.</span></span> <span data-ttu-id="938c7-194">Comecei a usá-lo para testar se uma chave estava presente.</span><span class="sxs-lookup"><span data-stu-id="938c7-194">I started to use it to test if a key was present.</span></span> <span data-ttu-id="938c7-195">Quando o valor era `$false` ou zero, inesperadamente essa instrução retornava `$false`.</span><span class="sxs-lookup"><span data-stu-id="938c7-195">When the value was `$false` or zero, that statement would return `$false` unexpectedly.</span></span>

```powershell
if( $person.age -ne $null ){...}
```

<span data-ttu-id="938c7-196">Isso contorna o problema para valores iguais a zero, mas não para chaves $null vs. não existentes.</span><span class="sxs-lookup"><span data-stu-id="938c7-196">This works around that issue for zero values but not $null vs non-existent keys.</span></span> <span data-ttu-id="938c7-197">Na maioria das vezes você não precisa fazer essa distinção, mas há funções específicas para ajudar nas situações em que você precisa.</span><span class="sxs-lookup"><span data-stu-id="938c7-197">Most of the time you don't need to make that distinction but there are functions for when you do.</span></span>

```powershell
if( $person.ContainsKey('age') ){...}
```

<span data-ttu-id="938c7-198">Também temos um `ContainsValue()` para situações em que você precisa testar um valor sem conhecer a chave ou percorrer a coleção inteira.</span><span class="sxs-lookup"><span data-stu-id="938c7-198">We also have a `ContainsValue()` for the situation where you need to test for a value without knowing the key or iterating the whole collection.</span></span>

### <a name="removing-and-clearing-keys"></a><span data-ttu-id="938c7-199">Removendo e limpando as chaves</span><span class="sxs-lookup"><span data-stu-id="938c7-199">Removing and clearing keys</span></span>

<span data-ttu-id="938c7-200">Você pode remover as chaves com a função `.Remove()`.</span><span class="sxs-lookup"><span data-stu-id="938c7-200">You can remove keys with the `.Remove()` function.</span></span>

```powershell
$person.remove('age')
```

<span data-ttu-id="938c7-201">Atribuir a eles um valor `$null` apenas deixa você com uma chave que tem o valor `$null`.</span><span class="sxs-lookup"><span data-stu-id="938c7-201">Assigning them a `$null` value just leaves you with a key that has a `$null` value.</span></span>

<span data-ttu-id="938c7-202">Uma forma comum de limpar uma tabela de hash é simplesmente inicializá-la como uma tabela de hash vazia.</span><span class="sxs-lookup"><span data-stu-id="938c7-202">A common way to clear a hashtable is to just initialize it to an empty hashtable.</span></span>

```powershell
$person = @{}
```

<span data-ttu-id="938c7-203">Embora esse método funcione, vamos tentar usar a função `clear()` em vez dele.</span><span class="sxs-lookup"><span data-stu-id="938c7-203">While that does work, try to use the `clear()` function instead.</span></span>

```powershell
$person.clear()
```

<span data-ttu-id="938c7-204">Esse é um daqueles casos em que o uso da função cria um código autoexplicativo, que deixa suas intenções muito claras.</span><span class="sxs-lookup"><span data-stu-id="938c7-204">This is one of those instances where using the function creates self-documenting code and it makes the intentions of the code very clean.</span></span>

## <a name="all-the-fun-stuff"></a><span data-ttu-id="938c7-205">Todas as coisas divertidas</span><span class="sxs-lookup"><span data-stu-id="938c7-205">All the fun stuff</span></span>

### <a name="ordered-hashtables"></a><span data-ttu-id="938c7-206">Tabelas de hash ordenadas</span><span class="sxs-lookup"><span data-stu-id="938c7-206">Ordered hashtables</span></span>

<span data-ttu-id="938c7-207">Por padrão, as tabelas de hash não são ordenadas (nem classificadas).</span><span class="sxs-lookup"><span data-stu-id="938c7-207">By default, hashtables aren't ordered (or sorted).</span></span> <span data-ttu-id="938c7-208">No contexto tradicional, a ordem não importa quando sempre usamos uma chave para acessar os valores.</span><span class="sxs-lookup"><span data-stu-id="938c7-208">In the traditional context, the order doesn't matter when you always use a key to access values.</span></span> <span data-ttu-id="938c7-209">Você pode descobrir que deseja manter as propriedades na ordem em que as definiu.</span><span class="sxs-lookup"><span data-stu-id="938c7-209">You may find that you want the properties to stay in the order that you define them.</span></span> <span data-ttu-id="938c7-210">Felizmente, há uma forma de fazer isso com a palavra-chave `ordered`.</span><span class="sxs-lookup"><span data-stu-id="938c7-210">Thankfully, there's a way to do that with the `ordered` keyword.</span></span>

```powershell
$person = [ordered]@{
    name = 'Kevin'
    age  = 36
}
```

<span data-ttu-id="938c7-211">Agora, quando você enumera as chaves e os valores, eles permanecem naquela ordem.</span><span class="sxs-lookup"><span data-stu-id="938c7-211">Now when you enumerate the keys and values, they stay in that order.</span></span>

### <a name="inline-hashtables"></a><span data-ttu-id="938c7-212">Tabelas de hash embutidas</span><span class="sxs-lookup"><span data-stu-id="938c7-212">Inline hashtables</span></span>

<span data-ttu-id="938c7-213">Quando você estiver definindo uma tabela de hash em uma linha, poderá separar os pares de chave/valor com um ponto-e-vírgula.</span><span class="sxs-lookup"><span data-stu-id="938c7-213">When you're defining a hashtable on one line, you can separate the key/value pairs with a semicolon.</span></span>

```powershell
$person = @{ name = 'kevin'; age = 36; }
```

<span data-ttu-id="938c7-214">Isso poderá ser útil se você estiver criando os pares no pipe.</span><span class="sxs-lookup"><span data-stu-id="938c7-214">This will come in handy if you're creating them on the pipe.</span></span>

### <a name="custom-expressions-in-common-pipeline-commands"></a><span data-ttu-id="938c7-215">Expressões personalizadas em comandos de pipeline comuns</span><span class="sxs-lookup"><span data-stu-id="938c7-215">Custom expressions in common pipeline commands</span></span>

<span data-ttu-id="938c7-216">Há alguns cmdlets que dão suporte ao uso de tabelas de hash para criar propriedades personalizadas ou calculadas.</span><span class="sxs-lookup"><span data-stu-id="938c7-216">There are a few cmdlets that support the use of hashtables to create custom or calculated properties.</span></span> <span data-ttu-id="938c7-217">Normalmente vemos isso com `Select-Object` e `Format-Table`.</span><span class="sxs-lookup"><span data-stu-id="938c7-217">You commonly see this with `Select-Object` and `Format-Table`.</span></span> <span data-ttu-id="938c7-218">As tabelas de hash têm uma sintaxe especial parecida com essa quando totalmente expandidas.</span><span class="sxs-lookup"><span data-stu-id="938c7-218">The hashtables have a special syntax that looks like this when fully expanded.</span></span>

```powershell
$property = @{
    name = 'totalSpaceGB'
    expression = { ($_.used + $_.free) / 1GB }
}
```

<span data-ttu-id="938c7-219">`name` é o rótulo que o cmdlet daria para essa coluna.</span><span class="sxs-lookup"><span data-stu-id="938c7-219">The `name` is what the cmdlet would label that column.</span></span> <span data-ttu-id="938c7-220">`expression` é um bloco de script executado, onde `$_` é o valor do objeto no pipe.</span><span class="sxs-lookup"><span data-stu-id="938c7-220">The `expression` is a script block that is executed where `$_` is the value of the object on the pipe.</span></span> <span data-ttu-id="938c7-221">Aqui está esse script em ação:</span><span class="sxs-lookup"><span data-stu-id="938c7-221">Here is that script in action:</span></span>

```powershell
$drives = Get-PSDrive | Where Used
$drives | Select-Object -Properties name, $property

Name     totalSpaceGB
----     ------------
C    238.472652435303
```

<span data-ttu-id="938c7-222">Coloquei em uma variável, mas poderia facilmente ter sido definido embutido e você poderia ter encurtado de `name` para `n` e de `expression` para `e` enquanto estivesse lá.</span><span class="sxs-lookup"><span data-stu-id="938c7-222">I placed that in a variable but it could easily be defined inline and you can shorten `name` to `n` and `expression` to `e` while you're at it.</span></span>

```powershell
$drives | Select-Object -properties name, @{n='totalSpaceGB';e={($_.used + $_.free) / 1GB}}
```

<span data-ttu-id="938c7-223">Particularmente, eu não gosto porque deixa os comandos muito longos e geralmente ocasionam comportamentos indevidos (que prefiro não detalhar aqui).</span><span class="sxs-lookup"><span data-stu-id="938c7-223">I personally don't like how long that makes commands and it often promotes some bad behaviors that I won't get into.</span></span> <span data-ttu-id="938c7-224">É mais provável que eu crie uma nova tabela de hash ou um `pscustomobject` com todos os campos e as propriedades que eu quiser em vez de usar essa abordagem em meus scripts.</span><span class="sxs-lookup"><span data-stu-id="938c7-224">I'm more likely to create a new hashtable or `pscustomobject` with all the fields and properties that I want instead of using this approach in scripts.</span></span> <span data-ttu-id="938c7-225">Mas há muitos códigos por aí que usam isso, então, achei válido mostrar aqui.</span><span class="sxs-lookup"><span data-stu-id="938c7-225">But there's a lot of code out there that does this so I wanted you to be aware of it.</span></span> <span data-ttu-id="938c7-226">Falarei sobre a criação de um `pscustomobject` mais adiante.</span><span class="sxs-lookup"><span data-stu-id="938c7-226">I talk about creating a `pscustomobject` later on.</span></span>

### <a name="custom-sort-expression"></a><span data-ttu-id="938c7-227">Expressão de classificação personalizada</span><span class="sxs-lookup"><span data-stu-id="938c7-227">Custom sort expression</span></span>

<span data-ttu-id="938c7-228">Será fácil classificar uma coleção se os objetos tiverem os dados pelos quais você deseja classificar.</span><span class="sxs-lookup"><span data-stu-id="938c7-228">It's easy to sort a collection if the objects have the data that you want to sort on.</span></span> <span data-ttu-id="938c7-229">Você pode adicionar os dados ao objeto antes de classificá-los ou criar uma expressão personalizada para `Sort-Object`.</span><span class="sxs-lookup"><span data-stu-id="938c7-229">You can either add the data to the object before you sort it or create a custom expression for `Sort-Object`.</span></span>

```powershell
Get-ADUser | Sort-Object -Parameter @{ e={ Get-TotalSales $_.Name } }
```

<span data-ttu-id="938c7-230">Neste exemplo, eu pego uma lista de usuários e uso algum cmdlet personalizado para obter informações adicionais apenas para a classificação.</span><span class="sxs-lookup"><span data-stu-id="938c7-230">In this example I'm taking a list of users and using some custom cmdlet to get additional information just for the sort.</span></span>

#### <a name="sort-a-list-of-hashtables"></a><span data-ttu-id="938c7-231">Classificar uma lista de tabelas de hash</span><span class="sxs-lookup"><span data-stu-id="938c7-231">Sort a list of Hashtables</span></span>

<span data-ttu-id="938c7-232">Se você tiver uma lista de tabelas de hash que deseja classificar, descobrirá que o `Sort-Object` não trata suas chaves como propriedades.</span><span class="sxs-lookup"><span data-stu-id="938c7-232">If you have a list of hashtables that you want to sort, you'll find that the `Sort-Object` doesn't treat your keys as properties.</span></span> <span data-ttu-id="938c7-233">Podemos contornar isso usando uma expressão de classificação personalizada.</span><span class="sxs-lookup"><span data-stu-id="938c7-233">We can get a round that by using a custom sort expression.</span></span>

```powershell
$data = @(
    @{name='a'}
    @{name='c'}
    @{name='e'}
    @{name='f'}
    @{name='d'}
    @{name='b'}
)

$data | Sort-Object -Property @{e={$_.name}}
```

## <a name="splatting-hashtables-at-cmdlets"></a><span data-ttu-id="938c7-234">Fracionando as tabelas de hash em cmdlets</span><span class="sxs-lookup"><span data-stu-id="938c7-234">Splatting hashtables at cmdlets</span></span>

<span data-ttu-id="938c7-235">Essa é uma das coisas que mais gosto nas tabelas de hash e muitas pessoas demoram para descobrir.</span><span class="sxs-lookup"><span data-stu-id="938c7-235">This is one of my favorite things about hashtables that many people don't discover early on.</span></span>
<span data-ttu-id="938c7-236">A ideia é que, em vez de atribuir todas as propriedades a um cmdlet em uma linha, você possa compactá-las em uma tabela de hash primeiro.</span><span class="sxs-lookup"><span data-stu-id="938c7-236">The idea is that instead of providing all the properties to a cmdlet on one line, you can instead pack them into a hashtable first.</span></span> <span data-ttu-id="938c7-237">Então, você pode fornecer a tabela de hash à função de maneira especial.</span><span class="sxs-lookup"><span data-stu-id="938c7-237">Then you can give the hashtable to the function in a special way.</span></span>
<span data-ttu-id="938c7-238">Aqui está um exemplo de como criar um escopo DHCP da maneira normal.</span><span class="sxs-lookup"><span data-stu-id="938c7-238">Here is an example of creating a DHCP scope the normal way.</span></span>

```powershell
Add-DhcpServerv4Scope -Name 'TestNetwork' -StartRange'10.0.0.2' -EndRange '10.0.0.254' -SubnetMask '255.255.255.0' -Description 'Network for testlab A' -LeaseDuration (New-TimeSpan -Days 8) -Type "Both"
```

<span data-ttu-id="938c7-239">Sem usar o [fracionamento][], todas essas coisas precisam ser definidas em uma só linha.</span><span class="sxs-lookup"><span data-stu-id="938c7-239">Without using [splatting][], all those things need to be defined on a single line.</span></span> <span data-ttu-id="938c7-240">Ou as informações rolam para fora da tela ou são quebradas em algum ponto arbitrário.</span><span class="sxs-lookup"><span data-stu-id="938c7-240">It either scrolls off the screen or will wrap where ever it feels like.</span></span> <span data-ttu-id="938c7-241">Agora, compare isso com um comando que usa o fracionamento.</span><span class="sxs-lookup"><span data-stu-id="938c7-241">Now compare that to a command that uses splatting.</span></span>

```powershell
$DHCPScope = @{
    Name        = 'TestNetwork'
    StartRange  = '10.0.0.2'
    EndRange    = '10.0.0.254'
    SubnetMask  = '255.255.255.0'
    Description = 'Network for testlab A'
    LeaseDuration = (New-TimeSpan -Days 8)
    Type = "Both"
}
Add-DhcpServerv4Scope @DHCPScope
```

<span data-ttu-id="938c7-242">O uso do sinal `@` em vez do `$` é o que invoca a operação de fracionamento.</span><span class="sxs-lookup"><span data-stu-id="938c7-242">The use of the `@` sign instead of the `$` is what invokes the splat operation.</span></span>

<span data-ttu-id="938c7-243">Reserve um tempo para contemplar como é fácil ler o exemplo.</span><span class="sxs-lookup"><span data-stu-id="938c7-243">Just take a moment to appreciate how easy that example is to read.</span></span> <span data-ttu-id="938c7-244">São exatamente o mesmo comando, com todos os valores iguais.</span><span class="sxs-lookup"><span data-stu-id="938c7-244">They are the exact same command with all the same values.</span></span> <span data-ttu-id="938c7-245">O segundo é mais fácil de entender e manter no futuro.</span><span class="sxs-lookup"><span data-stu-id="938c7-245">The second one is easier to understand and maintain going forward.</span></span>

<span data-ttu-id="938c7-246">Eu uso o fracionamento sempre que o comando ficar muito longo.</span><span class="sxs-lookup"><span data-stu-id="938c7-246">I use splatting anytime the command gets too long.</span></span> <span data-ttu-id="938c7-247">Eu o considero muito longo quando ultrapassa o limite da janela, sendo necessário rolar a tela para a direita.</span><span class="sxs-lookup"><span data-stu-id="938c7-247">I define too long as causing my window to scroll right.</span></span> <span data-ttu-id="938c7-248">Se eu usar três propriedades por função, é provável que eu a reescreva usando uma tabela de hash com fracionamento.</span><span class="sxs-lookup"><span data-stu-id="938c7-248">If I hit three properties for a function, odds are that I'll rewrite it using a splatted hashtable.</span></span>

### <a name="splatting-for-optional-parameters"></a><span data-ttu-id="938c7-249">Fracionamento para parâmetros opcionais</span><span class="sxs-lookup"><span data-stu-id="938c7-249">Splatting for optional parameters</span></span>

<span data-ttu-id="938c7-250">Uma das maneiras mais comuns de usar o fracionamento é ao lidar com parâmetros opcionais que vêm de algum outro lugar do script.</span><span class="sxs-lookup"><span data-stu-id="938c7-250">One of the most common ways I use splatting is to deal with optional parameters that come from some place else in my script.</span></span> <span data-ttu-id="938c7-251">Vamos supor que eu tenha uma função que quebre a linha de uma chamada de `Get-CIMInstance` com um argumento opcional `$Credential`.</span><span class="sxs-lookup"><span data-stu-id="938c7-251">Let's say I have a function that wraps a `Get-CIMInstance` call that has an optional `$Credential` argument.</span></span>

```powershell
$CIMParams = @{
    ClassName = 'Win32_Bios'
    ComputerName = $ComputerName
}

if($Credential)
{
    $CIMParams.Credential = $Credential
}

Get-CIMInstance @CIMParams
```

<span data-ttu-id="938c7-252">Eu começo criando a tabela de hash com parâmetros comuns.</span><span class="sxs-lookup"><span data-stu-id="938c7-252">I start by creating my hashtable with common parameters.</span></span> <span data-ttu-id="938c7-253">Então, eu adiciono o `$Credential` se ele existe.</span><span class="sxs-lookup"><span data-stu-id="938c7-253">Then I add the `$Credential` if it exists.</span></span>
<span data-ttu-id="938c7-254">Como estou usando o fracionamento aqui, só preciso ter a chamada para `Get-CIMInstance` no meu código uma vez.</span><span class="sxs-lookup"><span data-stu-id="938c7-254">Because I'm using splatting here, I only need to have the call to `Get-CIMInstance` in my code once.</span></span> <span data-ttu-id="938c7-255">Esse padrão de design é muito limpo e pode manipular muitos parâmetros opcionais com facilidade.</span><span class="sxs-lookup"><span data-stu-id="938c7-255">This design pattern is very clean and can handle lots of optional parameters easily.</span></span>

<span data-ttu-id="938c7-256">Para ser justo, você pode gravar seus comandos para permitir `$null` valores como parâmetro.</span><span class="sxs-lookup"><span data-stu-id="938c7-256">To be fair, you could write your commands to allow `$null` values for parameters.</span></span> <span data-ttu-id="938c7-257">Nem sempre você tem controle sobre os outros comandos que está chamando.</span><span class="sxs-lookup"><span data-stu-id="938c7-257">You just don't always have control over the other commands you're calling.</span></span>

### <a name="multiple-splats"></a><span data-ttu-id="938c7-258">Várias frações</span><span class="sxs-lookup"><span data-stu-id="938c7-258">Multiple splats</span></span>

<span data-ttu-id="938c7-259">Você pode fracionar várias tabelas de hash para o mesmo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="938c7-259">You can splat multiple hashtables to the same cmdlet.</span></span> <span data-ttu-id="938c7-260">Se revisitarmos nosso exemplo original de fracionamento:</span><span class="sxs-lookup"><span data-stu-id="938c7-260">If we revisit our original splatting example:</span></span>

```powershell
$Common = @{
    SubnetMask  = '255.255.255.0'
    LeaseDuration = (New-TimeSpan -Days 8)
    Type = "Both"
}

$DHCPScope = @{
    Name        = 'TestNetwork'
    StartRange  = '10.0.0.2'
    EndRange    = '10.0.0.254'
    Description = 'Network for testlab A'
}

Add-DhcpServerv4Scope @DHCPScope @Common
```

<span data-ttu-id="938c7-261">Usarei esse método quando tiver um conjunto comum de parâmetros sendo passados para vários comandos.</span><span class="sxs-lookup"><span data-stu-id="938c7-261">I'll use this method when I have a common set of parameters that I'm passing to lots of commands.</span></span>

### <a name="splatting-for-clean-code"></a><span data-ttu-id="938c7-262">Fracionamento para organização do código</span><span class="sxs-lookup"><span data-stu-id="938c7-262">Splatting for clean code</span></span>

<span data-ttu-id="938c7-263">Não há nada de errado com o fracionamento de um só parâmetro se isso tornar o código mais organizado.</span><span class="sxs-lookup"><span data-stu-id="938c7-263">There's nothing wrong with splatting a single parameter if makes you code cleaner.</span></span>

```powershell
$log = @{Path = '.\logfile.log'}
Add-Content "logging this command" @log
```

### <a name="splatting-executables"></a><span data-ttu-id="938c7-264">Fracionando executáveis</span><span class="sxs-lookup"><span data-stu-id="938c7-264">Splatting executables</span></span>

<span data-ttu-id="938c7-265">O fracionamento também funciona em alguns executáveis que usam a sintaxe `/param:value`.</span><span class="sxs-lookup"><span data-stu-id="938c7-265">Splatting also works on some executables that use a `/param:value` syntax.</span></span> <span data-ttu-id="938c7-266">`Robocopy.exe`, por exemplo, tem alguns parâmetros como esse.</span><span class="sxs-lookup"><span data-stu-id="938c7-266">`Robocopy.exe`, for example, has some parameters like this.</span></span>

```powershell
$robo = @{R=1;W=1;MT=8}
robocopy source destination @robo
```

<span data-ttu-id="938c7-267">Não sei se isso é tão útil, mas achei muito interessante.</span><span class="sxs-lookup"><span data-stu-id="938c7-267">I don't know that this is all that useful, but I found it interesting.</span></span>

## <a name="adding-hashtables"></a><span data-ttu-id="938c7-268">Adicionando tabelas de hash</span><span class="sxs-lookup"><span data-stu-id="938c7-268">Adding hashtables</span></span>

<span data-ttu-id="938c7-269">As tabelas de hash dão suporte ao operador de adição a fim de combinar duas tabelas de hash.</span><span class="sxs-lookup"><span data-stu-id="938c7-269">Hashtables support the addition operator to combine two hashtables.</span></span>

```powershell
$person += @{Zip = '78701'}
```

<span data-ttu-id="938c7-270">Isso só funcionará se as duas tabelas de hash não compartilharem uma mesma chave.</span><span class="sxs-lookup"><span data-stu-id="938c7-270">This only works if the two hashtables don't share a key.</span></span>

## <a name="nested-hashtables"></a><span data-ttu-id="938c7-271">Tabelas de hash aninhadas</span><span class="sxs-lookup"><span data-stu-id="938c7-271">Nested hashtables</span></span>

<span data-ttu-id="938c7-272">Podemos usar tabelas de hash como valores dentro de uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="938c7-272">We can use hashtables as values inside a hashtable.</span></span>

```powershell
$person = @{
    name = 'Kevin'
    age  = 36
}
$person.location = @{}
$person.location.city = 'Austin'
$person.location.state = 'TX'
```

<span data-ttu-id="938c7-273">Começamos com uma tabela de hash básica contendo duas chaves.</span><span class="sxs-lookup"><span data-stu-id="938c7-273">I started with a basic hashtable containing two keys.</span></span> <span data-ttu-id="938c7-274">Adicionamos uma chave chamada `location`, com uma tabela de hash vazia.</span><span class="sxs-lookup"><span data-stu-id="938c7-274">I added a key called `location` with an empty hashtable.</span></span> <span data-ttu-id="938c7-275">Depois, adicionamos os dois últimos itens a essa tabela de hash `location`.</span><span class="sxs-lookup"><span data-stu-id="938c7-275">Then I added the last two items to that `location` hashtable.</span></span> <span data-ttu-id="938c7-276">Também podemos fazer tudo isso de maneira embutida.</span><span class="sxs-lookup"><span data-stu-id="938c7-276">We can do this all inline too.</span></span>

```powershell
$person = @{
    name = 'Kevin'
    age  = 36
    location = @{
        city  = 'Austin'
        state = 'TX'
    }
}
```

<span data-ttu-id="938c7-277">Isso cria a mesma tabela de hash que vimos acima e permite acessar as propriedades da mesma maneira.</span><span class="sxs-lookup"><span data-stu-id="938c7-277">This creates the same hashtable that we saw above and can access the properties the same way.</span></span>

```powershell
$person.location.city
Austin
```

<span data-ttu-id="938c7-278">Há várias maneiras de abordar a estrutura de seus objetos.</span><span class="sxs-lookup"><span data-stu-id="938c7-278">There are many ways to approach the structure of your objects.</span></span> <span data-ttu-id="938c7-279">Aqui está uma segunda maneira de examinar uma tabela de hash aninhada.</span><span class="sxs-lookup"><span data-stu-id="938c7-279">Here is a second way to look at a nested hashtable.</span></span>

```powershell
$people = @{
    Kevin = @{
        age  = 36
        city = 'Austin'
    }
    Alex = @{
        age  = 9
        city = 'Austin'
    }
}
```

<span data-ttu-id="938c7-280">Deste modo, estaríamos combinando o conceito de tabelas de hash como coleção de objetos e como coleção de propriedades.</span><span class="sxs-lookup"><span data-stu-id="938c7-280">This mixes the concept of using hashtables as a collection of objects and a collection of properties.</span></span> <span data-ttu-id="938c7-281">Os valores ainda são fáceis de acessar, mesmo quando são aninhados por meio de qualquer abordagem que você preferir.</span><span class="sxs-lookup"><span data-stu-id="938c7-281">The values are still easy to access even when they're nested using whatever approach you prefer.</span></span>

```powershell
PS> $people.kevin.age
36
PS> $people.kevin['city']
Austin
PS> $people['Alex'].age
9
PS> $people['Alex']['City']
Austin
```

<span data-ttu-id="938c7-282">Eu costumo usar a propriedade do ponto quando estou tratando como uma propriedade.</span><span class="sxs-lookup"><span data-stu-id="938c7-282">I tend to use the dot property when I'm treating it like a property.</span></span> <span data-ttu-id="938c7-283">Normalmente, essas são as coisas que defino estaticamente em meu código e que conheço de cor e salteado.</span><span class="sxs-lookup"><span data-stu-id="938c7-283">Those are generally things I've defined statically in my code and I know them off the top of my head.</span></span> <span data-ttu-id="938c7-284">Se for preciso percorrer a lista ou acessar programaticamente as chaves, usamos os colchetes para fornecer o nome da chave.</span><span class="sxs-lookup"><span data-stu-id="938c7-284">If I need to walk the list or programmatically access the keys, I use the brackets to provide the key name.</span></span>

```powershell
foreach($name in $people.keys)
{
    $person = $people[$name]
    '{0}, age {1}, is in {2}' -f $name, $person.age, $person.city
}
```

<span data-ttu-id="938c7-285">Ter a capacidade de aninhar tabelas de hash oferece muita flexibilidade e opções.</span><span class="sxs-lookup"><span data-stu-id="938c7-285">Having the ability to nest hashtables gives you a lot of flexibility and options.</span></span>

### <a name="looking-at-nested-hashtables"></a><span data-ttu-id="938c7-286">Examinando as tabelas de hash aninhadas</span><span class="sxs-lookup"><span data-stu-id="938c7-286">Looking at nested hashtables</span></span>

<span data-ttu-id="938c7-287">Assim que começar a aninhar tabelas de hash, você precisará de uma forma fácil de examiná-las por meio do console.</span><span class="sxs-lookup"><span data-stu-id="938c7-287">As soon as you start nesting hashtables, you're going to need an easy way to look at them from the console.</span></span> <span data-ttu-id="938c7-288">Se eu executar essa última tabela de hash, receberei uma saída parecida com a seguinte (e essa é a profundidade que ela alcança):</span><span class="sxs-lookup"><span data-stu-id="938c7-288">If I take that last hashtable, I get an output that looks like this and it only goes so deep:</span></span>

```powershell
PS> $people
Name                           Value
----                           -----
Kevin                          {age, city}
Alex                           {age, city}
```

<span data-ttu-id="938c7-289">Meu comando preferido para examinar essas coisas é o `ConvertTo-JSON`, pois ele é muito organizado e, com frequência, uso o JSON para outras coisas.</span><span class="sxs-lookup"><span data-stu-id="938c7-289">My go to command for looking at these things is `ConvertTo-JSON` because it's very clean and I frequently use JSON on other things.</span></span>

```powershell
PS> $people | ConvertTo-Json
{
    "Kevin":  {
                "age":  36,
                "city":  "Austin"
            },
    "Alex":  {
                "age":  9,
                "city":  "Austin"
            }
}
```

<span data-ttu-id="938c7-290">Mesmo que você não conheça o JSON, você deve ser capaz de enxergar o que está procurando.</span><span class="sxs-lookup"><span data-stu-id="938c7-290">Even if you don't know JSON, you should be able to see what you're looking for.</span></span> <span data-ttu-id="938c7-291">Há um comando `Format-Custom` para dados estruturados como estes, mas eu ainda prefiro a exibição do JSON.</span><span class="sxs-lookup"><span data-stu-id="938c7-291">There's a `Format-Custom` command for structured data like this but I still like the JSON view better.</span></span>

## <a name="creating-objects"></a><span data-ttu-id="938c7-292">Criando objetos</span><span class="sxs-lookup"><span data-stu-id="938c7-292">Creating objects</span></span>

<span data-ttu-id="938c7-293">Às vezes, você só precisa ter um objeto e usar uma tabela de hash para armazenar propriedades simplesmente não é o bastante.</span><span class="sxs-lookup"><span data-stu-id="938c7-293">Sometimes you just need to have an object and using a hashtable to hold properties just isn't getting the job done.</span></span> <span data-ttu-id="938c7-294">Normalmente, você deseja ver as chaves como nomes de coluna.</span><span class="sxs-lookup"><span data-stu-id="938c7-294">Most commonly you want to see the keys as column names.</span></span> <span data-ttu-id="938c7-295">Uma `pscustomobject` facilita esse processo.</span><span class="sxs-lookup"><span data-stu-id="938c7-295">A `pscustomobject` makes that easy.</span></span>

```powershell
$person = [pscustomobject]@{
    name = 'Kevin'
    age  = 36
}

$person

name  age
----  ---
Kevin  36
```

<span data-ttu-id="938c7-296">Mesmo que você não a crie como uma `pscustomobject` inicialmente, sempre será possível convertê-la depois, quando necessário.</span><span class="sxs-lookup"><span data-stu-id="938c7-296">Even if you don't create it as a `pscustomobject` initially, you can always cast it later when needed.</span></span>

```powershell
$person = @{
    name = 'Kevin'
    age  = 36
}

[pscustomobject]$person

name  age
----  ---
Kevin  36
```

<span data-ttu-id="938c7-297">Eu tenho um artigo detalhado sobre [pscustomobject][] que você deve ler após o presente documento.</span><span class="sxs-lookup"><span data-stu-id="938c7-297">I already have detailed write-up for [pscustomobject][] that you should go read after this one.</span></span> <span data-ttu-id="938c7-298">Ele se baseia em muitas coisas aprendidas aqui.</span><span class="sxs-lookup"><span data-stu-id="938c7-298">It builds on a lot of the things learned here.</span></span>

## <a name="reading-and-writing-hashtables-to-file"></a><span data-ttu-id="938c7-299">Lendo e gravando tabelas de hash em arquivo</span><span class="sxs-lookup"><span data-stu-id="938c7-299">Reading and writing hashtables to file</span></span>

### <a name="saving-to-csv"></a><span data-ttu-id="938c7-300">Salvando em CSV</span><span class="sxs-lookup"><span data-stu-id="938c7-300">Saving to CSV</span></span>

<span data-ttu-id="938c7-301">A dificuldade de conseguir salvar uma tabela de hash em um arquivo CSV é uma das dificuldades a que me referia acima.</span><span class="sxs-lookup"><span data-stu-id="938c7-301">Struggling with getting a hashtable to save to a CSV is one of the difficulties that I was referring to above.</span></span> <span data-ttu-id="938c7-302">Converta sua tabela de hash em uma `pscustomobject` e ela será salva corretamente em CSV.</span><span class="sxs-lookup"><span data-stu-id="938c7-302">Convert your hashtable to a `pscustomobject` and it will save correctly to CSV.</span></span> <span data-ttu-id="938c7-303">Ajuda se você começar com uma `pscustomobject` para que a ordem das colunas seja preservada.</span><span class="sxs-lookup"><span data-stu-id="938c7-303">It helps if you start with a `pscustomobject` so the column order is preserved.</span></span> <span data-ttu-id="938c7-304">Mas você poderá convertê-la em um `pscustomobject` embutido, se necessário.</span><span class="sxs-lookup"><span data-stu-id="938c7-304">But you can cast it to a `pscustomobject` inline if needed.</span></span>

```powershell
$person | ForEach-Object{ [pscustomobject]$_ } | Export-CSV -Path $path
```

<span data-ttu-id="938c7-305">Novamente, confira meu artigo sobre como usar um [pscustomobject][].</span><span class="sxs-lookup"><span data-stu-id="938c7-305">Again, check out my write-up on using a [pscustomobject][].</span></span>

### <a name="saving-a-nested-hashtable-to-file"></a><span data-ttu-id="938c7-306">Salvando uma tabela de hash aninhada em arquivo</span><span class="sxs-lookup"><span data-stu-id="938c7-306">Saving a nested hashtable to file</span></span>

<span data-ttu-id="938c7-307">Se eu precisar salvar uma tabela de hash aninhada em um arquivo e lê-la novamente, usarei os cmdlets JSON para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="938c7-307">If I need to save a nested hashtable to a file and then read it back in again, I use the JSON cmdlets to do it.</span></span>

```powershell
$people | ConvertTo-JSON | Set-Content -Path $path
$people = Get-Content -Path $path -Raw | ConvertFrom-JSON
```

<span data-ttu-id="938c7-308">Há dois pontos importantes sobre esse método.</span><span class="sxs-lookup"><span data-stu-id="938c7-308">There are two important points about this method.</span></span> <span data-ttu-id="938c7-309">O primeiro é que o JSON é gravado em várias linhas, portanto, preciso usar a opção `-Raw` para lê-lo de volta em uma única cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="938c7-309">First is that the JSON is written out multiline so I need to use the `-Raw` option to read it back into a single string.</span></span> <span data-ttu-id="938c7-310">O segundo é que o objeto importado não é mais uma `[hashtable]`.</span><span class="sxs-lookup"><span data-stu-id="938c7-310">The Second is that the imported object is no longer a `[hashtable]`.</span></span> <span data-ttu-id="938c7-311">Agora é um `[pscustomobject]` e isso poderá causar problemas se você estiver esperando.</span><span class="sxs-lookup"><span data-stu-id="938c7-311">It's now a `[pscustomobject]` and that can cause issues if you don't expect it.</span></span>

<span data-ttu-id="938c7-312">Observe as tabelas de hash profundamente aninhadas.</span><span class="sxs-lookup"><span data-stu-id="938c7-312">Watch for deeply-nested hashtables.</span></span> <span data-ttu-id="938c7-313">Ao convertê-las em JSON, você pode não obter os resultados esperados.</span><span class="sxs-lookup"><span data-stu-id="938c7-313">When you convert it to JSON you might not get the results you expect.</span></span>

```powershell
@{ a = @{ b = @{ c = @{ d = "e" }}}} | ConvertTo-Json

{
  "a": {
    "b": {
      "c": "System.Collections.Hashtable"
    }
  }
}
```

<span data-ttu-id="938c7-314">Use o parâmetro **Depth** para garantir que você expandiu todas as tabelas de hash aninhadas.</span><span class="sxs-lookup"><span data-stu-id="938c7-314">Use **Depth** parameter to ensure that you have expanded all the nested hashtables.</span></span>

```powershell
@{ a = @{ b = @{ c = @{ d = "e" }}}} | ConvertTo-Json -Depth 3

{
  "a": {
    "b": {
      "c": {
        "d": "e"
      }
    }
  }
}
```

<span data-ttu-id="938c7-315">Se precisar que ele seja uma `[hashtable]` na importação, será necessário usar os comandos `Export-CliXml` e `Import-CliXml`.</span><span class="sxs-lookup"><span data-stu-id="938c7-315">If you need it to be a `[hashtable]` on import, then you need to use the `Export-CliXml` and `Import-CliXml` commands.</span></span>

### <a name="converting-json-to-hashtable"></a><span data-ttu-id="938c7-316">Convertendo um JSON em uma tabela de hash</span><span class="sxs-lookup"><span data-stu-id="938c7-316">Converting JSON to Hashtable</span></span>

<span data-ttu-id="938c7-317">Se você precisa converter um JSON em uma `[hashtable]`, eu conheço apenas uma forma de fazer isso com o [JavaScriptSerializer][] no .NET.</span><span class="sxs-lookup"><span data-stu-id="938c7-317">If you need to convert JSON to a `[hashtable]`, there's one way that I know of to do it with the [JavaScriptSerializer][] in .NET.</span></span>

```powershell
[Reflection.Assembly]::LoadWithPartialName("System.Web.Script.Serialization")
$JSSerializer = [System.Web.Script.Serialization.JavaScriptSerializer]::new()
$JSSerializer.Deserialize($json,'Hashtable')
```

<span data-ttu-id="938c7-318">A partir do PowerShell v6, o suporte a JSON usa o NewtonSoft JSON.NET e adiciona suporte à tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="938c7-318">Beginning in PowerShell v6, JSON support uses the NewtonSoft JSON.NET and adds hashtable support.</span></span>

```powershell
'{ "a": "b" }' | ConvertFrom-Json -AsHashtable

Name      Value
----      -----
a         b
```

<span data-ttu-id="938c7-319">O PowerShell 6.2 adicionou o parâmetro **Depth** a `ConvertFrom-Json`.</span><span class="sxs-lookup"><span data-stu-id="938c7-319">PowerShell 6.2 added the **Depth** parameter to `ConvertFrom-Json`.</span></span> <span data-ttu-id="938c7-320">O padrão **Depth** é 1024.</span><span class="sxs-lookup"><span data-stu-id="938c7-320">The default **Depth** is 1024.</span></span>

### <a name="reading-directly-from-a-file"></a><span data-ttu-id="938c7-321">Lendo diretamente de um arquivo</span><span class="sxs-lookup"><span data-stu-id="938c7-321">Reading directly from a file</span></span>

<span data-ttu-id="938c7-322">Se você tem um arquivo que contém uma tabela de hash usando a sintaxe do PowerShell, há uma forma de importá-lo diretamente.</span><span class="sxs-lookup"><span data-stu-id="938c7-322">If you have a file that contains a hashtable using PowerShell syntax, there's a way to import it directly.</span></span>

```powershell
$content = Get-Content -Path $Path -Raw -ErrorAction Stop
$scriptBlock = [scriptblock]::Create( $content )
$scriptBlock.CheckRestrictedLanguage( $allowedCommands, $allowedVariables, $true )
$hashtable = ( & $scriptBlock )
```

<span data-ttu-id="938c7-323">Isso importará o conteúdo do arquivo para um `scriptblock` e, em seguida, verificará se não contém outros comandos do PowerShell antes de executá-lo.</span><span class="sxs-lookup"><span data-stu-id="938c7-323">It imports the contents of the file into a `scriptblock`, then checks to make sure it doesn't have any other PowerShell commands in it before it executes it.</span></span>

<span data-ttu-id="938c7-324">Nessa observação, você sabia que um manifesto de módulo (o arquivo psd1) é apenas uma tabela de hash?</span><span class="sxs-lookup"><span data-stu-id="938c7-324">On that note, did you know that a module manifest (the psd1 file) is just a hashtable?</span></span>

## <a name="keys-can-be-any-object"></a><span data-ttu-id="938c7-325">As chaves podem ser qualquer objeto</span><span class="sxs-lookup"><span data-stu-id="938c7-325">Keys can be any object</span></span>

<span data-ttu-id="938c7-326">Na maioria das vezes, as chaves são apenas cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="938c7-326">Most of the time, the keys are just strings.</span></span> <span data-ttu-id="938c7-327">Podemos colocar qualquer coisa entre aspas e transformar essa coisa em uma chave.</span><span class="sxs-lookup"><span data-stu-id="938c7-327">So we can put quotes around anything and make it a key.</span></span>

```powershell
$person = @{
    'full name' = 'Kevin Marquette'
    '#' = 3978
}
$person['full name']
```

<span data-ttu-id="938c7-328">Você pode fazer algumas coisas estranhas que talvez não soubesse que podia.</span><span class="sxs-lookup"><span data-stu-id="938c7-328">You can do some odd things that you may not have realized you could do.</span></span>

```powershell
$person.'full name'

$key = 'full name'
$person.$key
```

<span data-ttu-id="938c7-329">Só porque você é capaz de fazer algo, isso não significa que você deva fazê-lo.</span><span class="sxs-lookup"><span data-stu-id="938c7-329">Just because you can do something, it doesn't mean that you should.</span></span> <span data-ttu-id="938c7-330">Essa última parece um bug pronto para acontecer e seria facilmente mal interpretada por qualquer pessoa que estivesse lendo seu código.</span><span class="sxs-lookup"><span data-stu-id="938c7-330">That last one just looks like a bug waiting to happen and would be easily misunderstood by anyone reading your code.</span></span>

<span data-ttu-id="938c7-331">Tecnicamente, as chaves não precisam ser cadeias de caracteres, mas é mais fácil pensar nelas se você usar apenas cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="938c7-331">Technically your key doesn't have to be a string but they're easier to think about if you only use strings.</span></span> <span data-ttu-id="938c7-332">No entanto, a indexação não funciona bem com as chaves complexas.</span><span class="sxs-lookup"><span data-stu-id="938c7-332">However, indexing doesn't work well with the complex keys.</span></span>

```powershell
$ht = @{ @(1,2,3) = "a" }
$ht

Name                           Value
----                           -----
{1, 2, 3}                      a
```

<span data-ttu-id="938c7-333">O acesso a um valor na tabela de hash por sua chave nem sempre funciona.</span><span class="sxs-lookup"><span data-stu-id="938c7-333">Accessing a value in the hashtable by its key doesn't always work.</span></span> <span data-ttu-id="938c7-334">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="938c7-334">For example:</span></span>

```powershell
$key = $ht.keys[0]
$ht.$($key)
a
$ht[$key]
a
```

<span data-ttu-id="938c7-335">Quando a chave é uma matriz, você precisa encapsular a variável `$key` em uma subexpressão para que ela possa ser usada com a notação de acesso de membro (`.`).</span><span class="sxs-lookup"><span data-stu-id="938c7-335">When the key is an array, you must wrap the `$key` variable in a subexpression so that it can be used with member access (`.`) notation.</span></span> <span data-ttu-id="938c7-336">Ou, você pode usar a notação de índice de matriz (`[]`).</span><span class="sxs-lookup"><span data-stu-id="938c7-336">Or, you can use array index (`[]`) notation.</span></span>

## <a name="use-in-automatic-variables"></a><span data-ttu-id="938c7-337">Usar em variáveis automáticas</span><span class="sxs-lookup"><span data-stu-id="938c7-337">Use in automatic variables</span></span>

### <a name="psboundparameters"></a><span data-ttu-id="938c7-338">$PSBoundParameters</span><span class="sxs-lookup"><span data-stu-id="938c7-338">$PSBoundParameters</span></span>

<span data-ttu-id="938c7-339">[$PSBoundParameters][] é uma variável automática que existe apenas dentro do contexto de uma função.</span><span class="sxs-lookup"><span data-stu-id="938c7-339">[$PSBoundParameters][] is an automatic variable that only exists inside the context of a function.</span></span>
<span data-ttu-id="938c7-340">Ela contém todos os parâmetros com os quais a função foi chamada.</span><span class="sxs-lookup"><span data-stu-id="938c7-340">It contains all the parameters that the function was called with.</span></span> <span data-ttu-id="938c7-341">Ela não é exatamente uma tabela de hash, mas é parecida o suficiente para que você possa tratá-la como tal.</span><span class="sxs-lookup"><span data-stu-id="938c7-341">This isn't exactly a hashtable but close enough that you can treat it like one.</span></span>

<span data-ttu-id="938c7-342">Isso inclui a remoção de chaves e o fracionamento em outras funções.</span><span class="sxs-lookup"><span data-stu-id="938c7-342">That includes removing keys and splatting it to other functions.</span></span> <span data-ttu-id="938c7-343">Se você estiver escrevendo funções de proxy, dê uma olhada mais de perto neste artigo.</span><span class="sxs-lookup"><span data-stu-id="938c7-343">If you find yourself writing proxy functions, take a closer look at this one.</span></span>

<span data-ttu-id="938c7-344">Confira [about_Automatic_Variables][] para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="938c7-344">See [about_Automatic_Variables][] for more details.</span></span>

### <a name="psboundparameters-gotcha"></a><span data-ttu-id="938c7-345">Armadilha da PSBoundParameters</span><span class="sxs-lookup"><span data-stu-id="938c7-345">PSBoundParameters gotcha</span></span>

<span data-ttu-id="938c7-346">Uma coisa importante a ser lembrada é que essa variável inclui apenas os valores que são passados como parâmetros.</span><span class="sxs-lookup"><span data-stu-id="938c7-346">One important thing to remember is that this only includes the values that are passed in as parameters.</span></span> <span data-ttu-id="938c7-347">Se também houver parâmetros com valores padrão que não forem passados pelo chamador, a `$PSBoundParameters` não incluirá esses valores.</span><span class="sxs-lookup"><span data-stu-id="938c7-347">If you also have parameters with default values but aren't passed in by the caller, `$PSBoundParameters` doesn't contain those values.</span></span> <span data-ttu-id="938c7-348">Normalmente, isso é ignorado.</span><span class="sxs-lookup"><span data-stu-id="938c7-348">This is commonly overlooked.</span></span>

### <a name="psdefaultparametervalues"></a><span data-ttu-id="938c7-349">$PSDefaultParameterValues</span><span class="sxs-lookup"><span data-stu-id="938c7-349">$PSDefaultParameterValues</span></span>

<span data-ttu-id="938c7-350">Essa variável automática permite que você atribua valores padrão a qualquer cmdlet sem alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="938c7-350">This automatic variable lets you assign default values to any cmdlet without changing the cmdlet.</span></span>
<span data-ttu-id="938c7-351">Confira este exemplo.</span><span class="sxs-lookup"><span data-stu-id="938c7-351">Take a look at this example.</span></span>

```powershell
$PSDefaultParameterValues["Out-File:Encoding"] = "UTF8"
```

<span data-ttu-id="938c7-352">Ele adiciona uma entrada à tabela de hash `$PSDefaultParameterValues`, que define `UTF8` como o valor padrão para o parâmetro `Out-File -Encoding`.</span><span class="sxs-lookup"><span data-stu-id="938c7-352">This adds an entry to the `$PSDefaultParameterValues` hashtable that sets `UTF8` as the default value for the `Out-File -Encoding` parameter.</span></span> <span data-ttu-id="938c7-353">É algo específico da sessão, portanto, você deve colocar no `$profile`.</span><span class="sxs-lookup"><span data-stu-id="938c7-353">This is session-specific so you should place it in your `$profile`.</span></span>

<span data-ttu-id="938c7-354">Eu uso isso sempre para atribuir previamente valores que costumo digitar com frequência.</span><span class="sxs-lookup"><span data-stu-id="938c7-354">I use this often to pre-assign values that I type quite often.</span></span>

```powershell
$PSDefaultParameterValues[ "Connect-VIServer:Server" ] = 'VCENTER01.contoso.local'
```

<span data-ttu-id="938c7-355">Ela também aceita curingas para que você possa definir valores em massa.</span><span class="sxs-lookup"><span data-stu-id="938c7-355">This also accepts wildcards so you can set values in bulk.</span></span> <span data-ttu-id="938c7-356">Aqui estão algumas maneiras pelas quais você pode usar isso:</span><span class="sxs-lookup"><span data-stu-id="938c7-356">Here are some ways you can use that:</span></span>

```powershell
$PSDefaultParameterValues[ "Get-*:Verbose" ] = $true
$PSDefaultParameterValues[ "*:Credential" ] = Get-Credential
```

<span data-ttu-id="938c7-357">Para obter um detalhamento mais aprofundado, confira este excelente artigo sobre [Padrões Automáticos][], escrito por [Michael Sorens][].</span><span class="sxs-lookup"><span data-stu-id="938c7-357">For a more in-depth breakdown, see this great article on [Automatic Defaults][] by [Michael Sorens][].</span></span>

## <a name="regex-matches"></a><span data-ttu-id="938c7-358">$Matches de expressão regular</span><span class="sxs-lookup"><span data-stu-id="938c7-358">Regex $Matches</span></span>

<span data-ttu-id="938c7-359">Quando você usa o operador `-match`, uma variável automática chamada `$matches` é criada com os resultados da correspondência.</span><span class="sxs-lookup"><span data-stu-id="938c7-359">When you use the `-match` operator, an automatic variable called `$matches` is created with the results of the match.</span></span> <span data-ttu-id="938c7-360">Se você tiver qualquer subexpressão em sua expressão regular, essas subcorrespondências também serão listadas.</span><span class="sxs-lookup"><span data-stu-id="938c7-360">If you have any sub expressions in your regex, those sub matches are also listed.</span></span>

```powershell
$message = 'My SSN is 123-45-6789.'

$message -match 'My SSN is (.+)\.'
$Matches[0]
$Matches[1]
```

### <a name="named-matches"></a><span data-ttu-id="938c7-361">Correspondências nomeadas</span><span class="sxs-lookup"><span data-stu-id="938c7-361">Named matches</span></span>

<span data-ttu-id="938c7-362">Esse é um dos meus recursos favoritos, que a maioria das pessoas não conhece.</span><span class="sxs-lookup"><span data-stu-id="938c7-362">This is one of my favorite features that most people don't know about.</span></span> <span data-ttu-id="938c7-363">Se você usar uma correspondência de expressão regular nomeada, poderá acessar essa correspondência pelo nome entre as correspondências.</span><span class="sxs-lookup"><span data-stu-id="938c7-363">If you use a named regex match, then you can access that match by name on the matches.</span></span>

```powershell
$message = 'My Name is Kevin and my SSN is 123-45-6789.'

if($message -match 'My Name is (?<Name>.+) and my SSN is (?<SSN>.+)\.')
{
    $Matches.Name
    $Matches.SSN
}
```

<span data-ttu-id="938c7-364">No exemplo acima, `(?<Name>.*)` é uma subexpressão nomeada.</span><span class="sxs-lookup"><span data-stu-id="938c7-364">In the example above, the `(?<Name>.*)` is a named sub expression.</span></span> <span data-ttu-id="938c7-365">Então, esse valor é colocado na propriedade `$Matches.Name`.</span><span class="sxs-lookup"><span data-stu-id="938c7-365">This value is then placed in the `$Matches.Name` property.</span></span>

## <a name="group-object--ashashtable"></a><span data-ttu-id="938c7-366">Group-Object -AsHashtable</span><span class="sxs-lookup"><span data-stu-id="938c7-366">Group-Object -AsHashtable</span></span>

<span data-ttu-id="938c7-367">Um pequeno recurso conhecido do `Group-Object` é que ele pode transformar alguns conjuntos de dados em uma tabela de hash para você.</span><span class="sxs-lookup"><span data-stu-id="938c7-367">One little known feature of `Group-Object` is that it can turn some datasets into a hashtable for you.</span></span>

```powershell
Import-CSV $Path | Group-Object -AsHashtable -Property email
```

<span data-ttu-id="938c7-368">Isso adicionará cada linha a uma tabela de hash e usará a propriedade especificada como a chave para acessá-la.</span><span class="sxs-lookup"><span data-stu-id="938c7-368">This will add each row into a hashtable and use the specified property as the key to access it.</span></span>

## <a name="copying-hashtables"></a><span data-ttu-id="938c7-369">Copiando tabelas de hash</span><span class="sxs-lookup"><span data-stu-id="938c7-369">Copying Hashtables</span></span>

<span data-ttu-id="938c7-370">Uma coisa importante a saber é que as tabelas de hash são objetos.</span><span class="sxs-lookup"><span data-stu-id="938c7-370">One important thing to know is that hashtables are objects.</span></span> <span data-ttu-id="938c7-371">E cada variável é apenas uma referência a um objeto.</span><span class="sxs-lookup"><span data-stu-id="938c7-371">And each variable is just a reference to an object.</span></span> <span data-ttu-id="938c7-372">Isso significa que é necessário mais trabalho para fazer uma cópia válida de uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="938c7-372">This means that it takes more work to make a valid copy of a hashtable.</span></span>

### <a name="assigning-reference-types"></a><span data-ttu-id="938c7-373">Atribuindo tipos de referência</span><span class="sxs-lookup"><span data-stu-id="938c7-373">Assigning reference types</span></span>

<span data-ttu-id="938c7-374">Quando você tem uma tabela de hash e a atribui a uma segunda variável, ambas as variáveis apontam para a mesma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="938c7-374">When you have one hashtable and assign it to a second variable, both variables point to the same hashtable.</span></span>

```powershell
PS> $orig = @{name='orig'}
PS> $copy = $orig
PS> $copy.name = 'copy'
PS> 'Copy: [{0}]' -f $copy.name
PS> 'Orig: [{0}]' -f $orig.name

Copy: [copy]
Orig: [copy]
```

<span data-ttu-id="938c7-375">Algo que realça que elas são a mesma coisa é o fato de que alterar os valores em uma também alterará os valores na outra.</span><span class="sxs-lookup"><span data-stu-id="938c7-375">This highlights that they're the same because altering the values in one will also alter the values in the other.</span></span> <span data-ttu-id="938c7-376">Isso também se aplica ao passar tabelas de hash para outras funções.</span><span class="sxs-lookup"><span data-stu-id="938c7-376">This also applies when passing hashtables into other functions.</span></span> <span data-ttu-id="938c7-377">Se as funções fizerem alterações na tabela de hash passada, a original também será alterada.</span><span class="sxs-lookup"><span data-stu-id="938c7-377">If those functions make changes to that hashtable, your original is also altered.</span></span>

### <a name="shallow-copies-single-level"></a><span data-ttu-id="938c7-378">Cópias superficiais, nível único</span><span class="sxs-lookup"><span data-stu-id="938c7-378">Shallow copies, single level</span></span>

<span data-ttu-id="938c7-379">Se tivermos uma tabela de hash simples, como no exemplo acima, poderemos usar `.Clone()` para fazer uma cópia superficial.</span><span class="sxs-lookup"><span data-stu-id="938c7-379">If we have a simple hashtable like our example above, we can use `.Clone()` to make a shallow copy.</span></span>

```powershell
PS> $orig = @{name='orig'}
PS> $copy = $orig.Clone()
PS> $copy.name = 'copy'
PS> 'Copy: [{0}]' -f $copy.name
PS> 'Orig: [{0}]' -f $orig.name

Copy: [copy]
Orig: [orig]
```

<span data-ttu-id="938c7-380">Isso nos permitirá fazer algumas alterações básicas em uma sem afetar a outra.</span><span class="sxs-lookup"><span data-stu-id="938c7-380">This will allow us to make some basic changes to one that don't impact the other.</span></span>

### <a name="shallow-copies-nested"></a><span data-ttu-id="938c7-381">Cópias superficiais, aninhadas</span><span class="sxs-lookup"><span data-stu-id="938c7-381">Shallow copies, nested</span></span>

<span data-ttu-id="938c7-382">O motivo pelo qual são chamadas de cópias superficiais é o fato de só copiarem as propriedades do nível	de base.</span><span class="sxs-lookup"><span data-stu-id="938c7-382">The reason why it's called a shallow copy is because it only copies the base level properties.</span></span> <span data-ttu-id="938c7-383">Se alguma dessas propriedades for um tipo de referência (como outra tabela de hash), então os objetos aninhados ainda apontarão um para o outro.</span><span class="sxs-lookup"><span data-stu-id="938c7-383">If one of those properties is a reference type (like another hashtable), then those nested objects will still point to each other.</span></span>

```powershell
PS> $orig = @{
        person=@{
            name='orig'
        }
    }
PS> $copy = $orig.Clone()
PS> $copy.person.name = 'copy'
PS> 'Copy: [{0}]' -f $copy.person.name
PS> 'Orig: [{0}]' -f $orig.person.name

Copy: [copy]
Orig: [copy]
```

<span data-ttu-id="938c7-384">Portanto, você pode notar que, embora eu tenha clonado a tabela de hash, a referência a `person` não foi clonada.</span><span class="sxs-lookup"><span data-stu-id="938c7-384">So you can see that even though I cloned the hashtable, the reference to `person` wasn't cloned.</span></span> <span data-ttu-id="938c7-385">Precisamos fazer uma cópia profunda para realmente ter uma segunda tabela de hash que não esteja vinculada à primeira.</span><span class="sxs-lookup"><span data-stu-id="938c7-385">We need to make a deep copy to truly have a second hashtable that isn't linked to the first.</span></span>

### <a name="deep-copies"></a><span data-ttu-id="938c7-386">Cópias profundas</span><span class="sxs-lookup"><span data-stu-id="938c7-386">Deep copies</span></span>

<span data-ttu-id="938c7-387">Existem algumas maneiras de fazer uma cópia em profundidade de uma tabela de hash (e mantê-la como uma tabela de hash).</span><span class="sxs-lookup"><span data-stu-id="938c7-387">There are a couple of ways to make a deep copy of a hashtable (and keep it as a hashtable).</span></span> <span data-ttu-id="938c7-388">Veja uma função que usa o PowerShell para criar recursivamente uma cópia em profundidade:</span><span class="sxs-lookup"><span data-stu-id="938c7-388">Here's a function using PowerShell to recursively create a deep copy:</span></span>

```powershell
function Get-DeepClone
{
    [CmdletBinding()]
    param(
        $InputObject
    )
    process
    {
        if($InputObject -is [hashtable]) {
            $clone = @{}
            foreach($key in $InputObject.keys)
            {
                $clone[$key] = Get-DeepClone $InputObject[$key]
            }
            return $clone
        } else {
            return $InputObject
        }
    }
}
```

<span data-ttu-id="938c7-389">Ele não gerencia nenhum outro tipo de referência ou matrizes, mas é um bom ponto de partida.</span><span class="sxs-lookup"><span data-stu-id="938c7-389">It doesn't handle any other reference types or arrays, but it's a good starting point.</span></span>

<span data-ttu-id="938c7-390">Outra maneira é usar o .Net para desserializá-la usando **CliXml**, como nesta função:</span><span class="sxs-lookup"><span data-stu-id="938c7-390">Another way is to use .Net to deserialize it using **CliXml** like in this function:</span></span>

```powershell
function Get-DeepClone
{
    param(
        $InputObject
    )
    $TempCliXmlString = [System.Management.Automation.PSSerializer]::Serialize($obj, [int32]::MaxValue)
    return [System.Management.Automation.PSSerializer]::Deserialize($TempCliXmlString)
}
```

<span data-ttu-id="938c7-391">Para tabelas de hash muito grandes, a função de desserialização é mais rápida conforme é escalada horizontalmente. No entanto, é preciso considerar alguns fatores ao usar esse método.</span><span class="sxs-lookup"><span data-stu-id="938c7-391">For extremely large hashtables, the deserializing function is faster as it scales out. However, there are some things to consider when using this method.</span></span> <span data-ttu-id="938c7-392">Como usa **CliXml**, o método usa muita memória. Se você estiver clonando tabelas de hash muito grandes, isso pode ser um problema.</span><span class="sxs-lookup"><span data-stu-id="938c7-392">Since it uses **CliXml**, it's memory intensive and if you are cloning huge hashtables, that might be a problem.</span></span> <span data-ttu-id="938c7-393">Outra limitação do **CliXml** é a limitação de profundidade de 48.</span><span class="sxs-lookup"><span data-stu-id="938c7-393">Another limitation of the **CliXml** is there is a depth limitation of 48.</span></span> <span data-ttu-id="938c7-394">Isso significa que se você tem uma tabela de hash com 48 camadas de tabelas de hash aninhadas, a clonagem falhará e nenhuma delas aparecerá na saída.</span><span class="sxs-lookup"><span data-stu-id="938c7-394">Meaning, if you have a hashtable with 48 layers of nested hashtables, the cloning will fail and no hashtable will be output at all.</span></span>

## <a name="anything-else"></a><span data-ttu-id="938c7-395">Algo mais?</span><span class="sxs-lookup"><span data-stu-id="938c7-395">Anything else?</span></span>

<span data-ttu-id="938c7-396">Abordei muitos aspectos de base rapidamente.</span><span class="sxs-lookup"><span data-stu-id="938c7-396">I covered a lot of ground quickly.</span></span> <span data-ttu-id="938c7-397">Minha esperança é que, toda vez que ler o artigo, você saia com uma novidade aprendida ou tendo entendido melhor algo.</span><span class="sxs-lookup"><span data-stu-id="938c7-397">My hope is that you walk away leaning something new or understanding it better every time you read this.</span></span> <span data-ttu-id="938c7-398">Como abordei o espectro completo desse recurso, pode haver aspectos que não se aplicam a você neste momento.</span><span class="sxs-lookup"><span data-stu-id="938c7-398">Because I covered the full spectrum of this feature, there are aspects that just may not apply to you right now.</span></span> <span data-ttu-id="938c7-399">Isso é perfeitamente normal e até esperado, de certo modo, dependendo do seu nível de familiaridade com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="938c7-399">That is perfectly OK and is kind of expected depending on how much you work with PowerShell.</span></span>

<!-- link references -->
[versão original]: https://powershellexplained.com/2016-11-06-powershell-hashtable-everything-you-wanted-to-know-about/
[original version]: https://powershellexplained.com/2016-11-06-powershell-hashtable-everything-you-wanted-to-know-about/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[tabelas de hash]: /powershell/module/microsoft.powershell.core/about/about_hash_tables
[hashtables]: /powershell/module/microsoft.powershell.core/about/about_hash_tables
[matrizes]: /powershell/module/microsoft.powershell.core/about/about_arrays
[arrays]: /powershell/module/microsoft.powershell.core/about/about_arrays
[Se o desempenho for importante, teste-o]: https://github.com/PoshCode/PowerShellPracticeAndStyle/blob/master/Best-Practices/Performance.md
[If performance matters, test it]: https://github.com/PoshCode/PowerShellPracticeAndStyle/blob/master/Best-Practices/Performance.md
[fracionamento]: /powershell/module/microsoft.powershell.core/about/about_splatting
[splatting]: /powershell/module/microsoft.powershell.core/about/about_splatting
[pscustomobject]: everything-about-pscustomobject.md
[JavaScriptSerializer]: /dotnet/api/system.web.script.serialization.javascriptserializer?view=netframework-4.8&preserve-view=true
[PSBoundParameters]: https://tommymaynard.com/the-psboundparameters-automatic-variable-2016/
[about_Automatic_Variables]: /powershell/module/microsoft.powershell.core/about/about_automatic_variables
[Padrões automáticos]: https://www.simple-talk.com/sysadmin/PowerShell/PowerShell-time-saver-automatic-defaults/
[Automatic Defaults]: https://www.simple-talk.com/sysadmin/PowerShell/PowerShell-time-saver-automatic-defaults/
[Michael Sorens]: http://cleancode.sourceforge.net/wwwdoc/about.html
