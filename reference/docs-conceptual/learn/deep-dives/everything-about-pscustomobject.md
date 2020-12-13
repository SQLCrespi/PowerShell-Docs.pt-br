---
title: Tudo o que você queria saber sobre o PSCustomObject
description: O PSCustomObject é um jeito simples de criar dados estruturados.
ms.date: 10/05/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: ccbdcdae5ad38f555233dffbed7e8a6ec2b0726b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "91772313"
---
# <a name="everything-you-wanted-to-know-about-pscustomobject"></a><span data-ttu-id="5703a-103">Tudo o que você queria saber sobre o PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="5703a-103">Everything you wanted to know about PSCustomObject</span></span>

<span data-ttu-id="5703a-104">`PSCustomObject`s são uma excelente ferramenta para adicionar ao conjunto de ferramentas do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5703a-104">`PSCustomObject`s are a great tool to add into your PowerShell tool belt.</span></span> <span data-ttu-id="5703a-105">Vamos começar com os conceitos básicos e progredir para os recursos mais avançados.</span><span class="sxs-lookup"><span data-stu-id="5703a-105">Let's start with the basics and work our way into the more advanced features.</span></span> <span data-ttu-id="5703a-106">A ideia por trás de usar um `PSCustomObject` é ter um jeito simples de criar dados estruturados.</span><span class="sxs-lookup"><span data-stu-id="5703a-106">The idea behind using a `PSCustomObject` is to have a simple way to create structured data.</span></span> <span data-ttu-id="5703a-107">Dê uma olhada no primeiro exemplo e você entenderá melhor o que isso significa.</span><span class="sxs-lookup"><span data-stu-id="5703a-107">Take a look at the first example and you'll have a better idea of what that means.</span></span>

> [!NOTE]
> <span data-ttu-id="5703a-108">A [versão original][] deste artigo foi publicada no blog escrito por [@KevinMarquette][].</span><span class="sxs-lookup"><span data-stu-id="5703a-108">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="5703a-109">A equipe do PowerShell agradece a Kevin por compartilhar o conteúdo conosco.</span><span class="sxs-lookup"><span data-stu-id="5703a-109">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="5703a-110">Confira o blog dele em [PowerShellExplained.com][].</span><span class="sxs-lookup"><span data-stu-id="5703a-110">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="creating-a-pscustomobject"></a><span data-ttu-id="5703a-111">Como criar um PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="5703a-111">Creating a PSCustomObject</span></span>

<span data-ttu-id="5703a-112">Eu adoro usar `[PSCustomObject]` no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5703a-112">I love using `[PSCustomObject]` in PowerShell.</span></span> <span data-ttu-id="5703a-113">Nunca foi tão fácil criar um objeto utilizável.</span><span class="sxs-lookup"><span data-stu-id="5703a-113">Creating a usable object has never been easier.</span></span>
<span data-ttu-id="5703a-114">Por isso, vou ignorar todas as outras maneiras de criar um objeto, mas é preciso notar que a maioria desses exemplos são do PowerShell v3.0 ou mais recentes.</span><span class="sxs-lookup"><span data-stu-id="5703a-114">Because of that, I'm going to skip over all the other ways you can create an object but I need to mention that most of these examples are PowerShell v3.0 and newer.</span></span>

```powershell
$myObject = [PSCustomObject]@{
    Name     = 'Kevin'
    Language = 'PowerShell'
    State    = 'Texas'
}
```

<span data-ttu-id="5703a-115">Esse método funciona bem para mim porque uso tabelas de hash para praticamente tudo.</span><span class="sxs-lookup"><span data-stu-id="5703a-115">This method works well for me because I use hashtables for just about everything.</span></span> <span data-ttu-id="5703a-116">Mas, às vezes, eu gostaria que o PowerShell tratasse as tabelas de hash mais como objetos.</span><span class="sxs-lookup"><span data-stu-id="5703a-116">But there are times when I would like PowerShell to treat hashtables more like an object.</span></span> <span data-ttu-id="5703a-117">O primeiro lugar em que é possível perceber a diferença é quando queremos usar `Format-Table` ou `Export-CSV` e percebemos que uma tabela de hash é apenas uma coleção de pares chave/valor.</span><span class="sxs-lookup"><span data-stu-id="5703a-117">The first place you notice the difference is when you want to use `Format-Table` or `Export-CSV` and you realize that a hashtable is just a collection of key/value pairs.</span></span>

<span data-ttu-id="5703a-118">Então, é possível acessar e usar os valores como faria com um objeto normal.</span><span class="sxs-lookup"><span data-stu-id="5703a-118">You can then access and use the values like you would a normal object.</span></span>

```powershell
$myObject.Name
```

### <a name="converting-a-hashtable"></a><span data-ttu-id="5703a-119">Como converter uma tabela de hash</span><span class="sxs-lookup"><span data-stu-id="5703a-119">Converting a hashtable</span></span>

<span data-ttu-id="5703a-120">Já que toquei no assunto, você sabia que é possível fazer isso:</span><span class="sxs-lookup"><span data-stu-id="5703a-120">While I am on the topic, did you know you could do this:</span></span>

```powershell
$myHashtable = @{
    Name     = 'Kevin'
    Language = 'PowerShell'
    State    = 'Texas'
}
$myObject = [pscustomobject]$myHashtable
```

<span data-ttu-id="5703a-121">Eu prefiro criar o objeto desde o início, mas às vezes é preciso trabalhar com uma tabela de hash primeiro.</span><span class="sxs-lookup"><span data-stu-id="5703a-121">I do prefer to create the object from the start but there are times you have to work with a hashtable first.</span></span> <span data-ttu-id="5703a-122">Esse exemplo funciona porque o construtor usa uma tabela de hash para as propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="5703a-122">This example works because the constructor takes a hashtable for the object properties.</span></span> <span data-ttu-id="5703a-123">É importante notar que, embora esse método funcione, ele não é um equivalente exato.</span><span class="sxs-lookup"><span data-stu-id="5703a-123">One important note is that while this method works, it isn't an exact equivalent.</span></span> <span data-ttu-id="5703a-124">A principal diferença é que a ordem das propriedades não é preservada.</span><span class="sxs-lookup"><span data-stu-id="5703a-124">The biggest difference is that the order of the properties isn't preserved.</span></span>

### <a name="legacy-approach"></a><span data-ttu-id="5703a-125">Abordagem herdada</span><span class="sxs-lookup"><span data-stu-id="5703a-125">Legacy approach</span></span>

<span data-ttu-id="5703a-126">Talvez você tenha visto pessoas usarem `New-Object` para criar objetos personalizados.</span><span class="sxs-lookup"><span data-stu-id="5703a-126">You may have seen people use `New-Object` to create custom objects.</span></span>

```powershell
$myHashtable = @{
    Name     = 'Kevin'
    Language = 'PowerShell'
    State    = 'Texas'
}

$myObject = New-Object -TypeName PSObject -Property $myHashtable
```

<span data-ttu-id="5703a-127">É um jeito um pouco mais lento, mas talvez seja a melhor opção em versões anteriores do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5703a-127">This way is quite a bit slower but it may be your best option on early versions of PowerShell.</span></span>

### <a name="saving-to-a-file"></a><span data-ttu-id="5703a-128">Como salvar em uma pasta</span><span class="sxs-lookup"><span data-stu-id="5703a-128">Saving to a file</span></span>

<span data-ttu-id="5703a-129">Na minha opinião, a melhor maneira de salvar uma tabela de hash em um arquivo é salvá-la como JSON.</span><span class="sxs-lookup"><span data-stu-id="5703a-129">I find the best way to save a hashtable to a file is to save it as JSON.</span></span> <span data-ttu-id="5703a-130">Assim, será possível importá-la de volta para um `[PSCustomObject]`</span><span class="sxs-lookup"><span data-stu-id="5703a-130">You can import it back into a `[PSCustomObject]`</span></span>

```powershell
$myObject | ConvertTo-Json -depth 1- | Set-Content -Path $Path
$myObject = Get-Content -Path $Path | ConvertFrom-Json
```

<span data-ttu-id="5703a-131">Eu abordei mais maneiras de salvar objetos em um arquivo em meu artigo sobre [As várias maneiras de ler e gravar em arquivos][].</span><span class="sxs-lookup"><span data-stu-id="5703a-131">I cover more ways to save objects to a file in my article on [The many ways to read and write to files][].</span></span>

## <a name="working-with-properties"></a><span data-ttu-id="5703a-132">Como trabalhar com propriedades</span><span class="sxs-lookup"><span data-stu-id="5703a-132">Working with properties</span></span>

### <a name="adding-properties"></a><span data-ttu-id="5703a-133">Adicionando propriedades</span><span class="sxs-lookup"><span data-stu-id="5703a-133">Adding properties</span></span>

<span data-ttu-id="5703a-134">Você ainda pode adicionar novas propriedades ao `PSCustomObject` com `Add-Member`.</span><span class="sxs-lookup"><span data-stu-id="5703a-134">You can still add new properties to your `PSCustomObject` with `Add-Member`.</span></span>

```powershell
$myObject | Add-Member -MemberType NoteProperty -Name `ID` -Value 'KevinMarquette'

$myObject.ID
```

### <a name="remove-properties"></a><span data-ttu-id="5703a-135">Como remover propriedades</span><span class="sxs-lookup"><span data-stu-id="5703a-135">Remove properties</span></span>

<span data-ttu-id="5703a-136">Você também pode remover as propriedades de um objeto.</span><span class="sxs-lookup"><span data-stu-id="5703a-136">You can also remove properties off of an object.</span></span>

```powershell
$myObject.psobject.properties.remove('ID')
```

<span data-ttu-id="5703a-137">O `psobject` é uma propriedade oculta que fornece acesso aos metadados do objeto base.</span><span class="sxs-lookup"><span data-stu-id="5703a-137">The `psobject` is a hidden property that gives you access to base object metadata.</span></span>

### <a name="enumerating-property-names"></a><span data-ttu-id="5703a-138">Como enumerar nomes de propriedade</span><span class="sxs-lookup"><span data-stu-id="5703a-138">Enumerating property names</span></span>

<span data-ttu-id="5703a-139">Às vezes, precisamos de uma lista de todos os nomes de propriedade em um objeto.</span><span class="sxs-lookup"><span data-stu-id="5703a-139">Sometimes you need a list of all the property names on an object.</span></span>

```powershell
$myObject | Get-Member -MemberType NoteProperty | Select -ExpandProperty Name
```

<span data-ttu-id="5703a-140">Também podemos obter essa mesma lista por meio da propriedade `psobject`.</span><span class="sxs-lookup"><span data-stu-id="5703a-140">We can get this same list off of the `psobject` property too.</span></span>

```powershell
$myobject.psobject.properties.name
```

### <a name="dynamically-accessing-properties"></a><span data-ttu-id="5703a-141">Como acessar propriedades dinamicamente</span><span class="sxs-lookup"><span data-stu-id="5703a-141">Dynamically accessing properties</span></span>

<span data-ttu-id="5703a-142">Já comentei que podemos acessar diretamente os valores de propriedade.</span><span class="sxs-lookup"><span data-stu-id="5703a-142">I already mentioned that you can access property values directly.</span></span>

```powershell
$myObject.Name
```

<span data-ttu-id="5703a-143">Podemos usar uma cadeia de caracteres para o nome da propriedade e ela funcionará mesmo assim.</span><span class="sxs-lookup"><span data-stu-id="5703a-143">You can use a string for the property name and it will still work.</span></span>

```powershell
$myObject.'Name'
```

<span data-ttu-id="5703a-144">Podemos ir um pouco mais longe e usar uma variável para o nome da propriedade.</span><span class="sxs-lookup"><span data-stu-id="5703a-144">We can take this one more step and use a variable for the property name.</span></span>

```powershell
$property = 'Name'
$myObject.$property
```

<span data-ttu-id="5703a-145">Eu sei que parece estranho, mas funciona.</span><span class="sxs-lookup"><span data-stu-id="5703a-145">I know that looks strange, but it works.</span></span>

### <a name="convert-pscustomobject-into-a-hashtable"></a><span data-ttu-id="5703a-146">Converter PSCustomObject em uma tabela de hash</span><span class="sxs-lookup"><span data-stu-id="5703a-146">Convert PSCustomObject into a hashtable</span></span>

<span data-ttu-id="5703a-147">Para continuar de onde paramos na última seção, podemos percorrer dinamicamente as propriedades e criar uma tabela de hash delas.</span><span class="sxs-lookup"><span data-stu-id="5703a-147">To continue on from the last section, you can dynamically walk the properties and create a hashtable from them.</span></span>

```powershell
$hashtable = @{}
foreach( $property in $myobject.psobject.properties.name )
{
    $hashtable[$property] = $myObject.$property
}
```

### <a name="testing-for-properties"></a><span data-ttu-id="5703a-148">Como testar as propriedades</span><span class="sxs-lookup"><span data-stu-id="5703a-148">Testing for properties</span></span>

<span data-ttu-id="5703a-149">Caso você precise saber se uma propriedade existe, basta verificar se essa propriedade tem um valor.</span><span class="sxs-lookup"><span data-stu-id="5703a-149">If you need to know if a property exists, you could just check for that property to have a value.</span></span>

```powershell
if( $null -ne $myObject.ID )
```

<span data-ttu-id="5703a-150">No entanto, se o valor puder ser `$null`, você poderá verificar se ele existe procurando-o em `psobject.properties`.</span><span class="sxs-lookup"><span data-stu-id="5703a-150">But if the value could be `$null` you can check to see if it exists by checking the `psobject.properties` for it.</span></span>

```powershell
if( $myobject.psobject.properties.match('ID').Count )
```

## <a name="adding-object-methods"></a><span data-ttu-id="5703a-151">Como adicionar métodos de objeto</span><span class="sxs-lookup"><span data-stu-id="5703a-151">Adding object methods</span></span>

<span data-ttu-id="5703a-152">Caso você precise adicionar um método de script a um objeto, é possível fazê-lo com um `Add-Member` e um `ScriptBlock`.</span><span class="sxs-lookup"><span data-stu-id="5703a-152">If you need to add a script method to an object, you can do it with `Add-Member` and a `ScriptBlock`.</span></span> <span data-ttu-id="5703a-153">Precisamos usar a referência automática de variável `this` no objeto atual.</span><span class="sxs-lookup"><span data-stu-id="5703a-153">You have to use the `this` automatic variable reference the current object.</span></span> <span data-ttu-id="5703a-154">Aqui está um `scriptblock` para transformar um objeto em uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="5703a-154">Here is a `scriptblock` to turn an object into a hashtable.</span></span> <span data-ttu-id="5703a-155">(mesma forma de código do último exemplo)</span><span class="sxs-lookup"><span data-stu-id="5703a-155">(same code form the last example)</span></span>

```powershell
$ScriptBlock = {
    $hashtable = @{}
    foreach( $property in $this.psobject.properties.name )
    {
        $hashtable[$property] = $this.$property
    }
    return $hashtable
}
```

<span data-ttu-id="5703a-156">Em seguida, o adicionamos ao objeto como uma propriedade de script.</span><span class="sxs-lookup"><span data-stu-id="5703a-156">Then we add it to our object as a script property.</span></span>

```powershell
$memberParam = @{
    MemberType = "ScriptMethod"
    InputObject = $myobject
    Name = "ToHashtable"
    Value = $scriptBlock
}
Add-Member @memberParam
```

<span data-ttu-id="5703a-157">Então, poderemos chamar nossa função assim:</span><span class="sxs-lookup"><span data-stu-id="5703a-157">Then we can call our function like this:</span></span>

```powershell
$myObject.ToHashtable()
```

### <a name="objects-vs-value-types"></a><span data-ttu-id="5703a-158">Objetos vs. Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="5703a-158">Objects vs Value types</span></span>

<span data-ttu-id="5703a-159">Objetos e tipos de valor não tratam das atribuições de variáveis do mesmo jeito.</span><span class="sxs-lookup"><span data-stu-id="5703a-159">Objects and value types don't handle variable assignments the same way.</span></span> <span data-ttu-id="5703a-160">Se você atribuir tipos de valor uns aos outros, somente o valor será copiado para a nova variável.</span><span class="sxs-lookup"><span data-stu-id="5703a-160">If you assign value types to each other, only the value get copied to the new variable.</span></span>

```powershell
$first = 1
$second = $first
$second = 2
```

<span data-ttu-id="5703a-161">Nesse caso, `$first` é 1 e `$second` é 2.</span><span class="sxs-lookup"><span data-stu-id="5703a-161">In this case, `$first` is 1 and `$second` is 2.</span></span>

<span data-ttu-id="5703a-162">As variáveis de objeto contêm referências ao objeto real.</span><span class="sxs-lookup"><span data-stu-id="5703a-162">Object variables hold a reference to the actual object.</span></span> <span data-ttu-id="5703a-163">Quando atribuímos um objeto a uma nova variável, elas ainda fazem referência ao mesmo objeto.</span><span class="sxs-lookup"><span data-stu-id="5703a-163">When you assign one object to a new variable, they still reference the same object.</span></span>

```powershell
$third = [PSCustomObject]@{Key=3}
$fourth = $third
$fourth.Key = 4
```

<span data-ttu-id="5703a-164">Como `$third` e `$fourth` referenciam a mesma instância de um objeto, tanto `$third.key`, como `$fourth.Key` são 4.</span><span class="sxs-lookup"><span data-stu-id="5703a-164">Because `$third` and `$fourth` reference the same instance of an object, both `$third.key` and `$fourth.Key` are 4.</span></span>

### <a name="psobjectcopy"></a><span data-ttu-id="5703a-165">psobject.copy()</span><span class="sxs-lookup"><span data-stu-id="5703a-165">psobject.copy()</span></span>

<span data-ttu-id="5703a-166">Caso você precise de uma cópia verdadeira de um objeto, poderá cloná-lo.</span><span class="sxs-lookup"><span data-stu-id="5703a-166">If you need a true copy of an object, you can clone it.</span></span>

```powershell
$third = [PSCustomObject]@{Key=3}
$fourth = $third.psobject.copy()
$fourth.Key = 4
```

<span data-ttu-id="5703a-167">Clonar cria uma cópia superficial do objeto.</span><span class="sxs-lookup"><span data-stu-id="5703a-167">Clone creates a shallow copy of the object.</span></span> <span data-ttu-id="5703a-168">Eles têm instâncias diferentes agora e `$third.key` é 3 e `$fourth.Key` é 4, neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="5703a-168">They have different instances now and `$third.key` is 3 and `$fourth.Key` is 4 in this example.</span></span>

<span data-ttu-id="5703a-169">Eu chamo isso de cópia superficial porque, se você tiver objetos aninhados</span><span class="sxs-lookup"><span data-stu-id="5703a-169">I call this a shallow copy because if you have nested objects.</span></span> <span data-ttu-id="5703a-170">(em que as propriedades contêm outros objetos),</span><span class="sxs-lookup"><span data-stu-id="5703a-170">(where the properties contain other objects).</span></span> <span data-ttu-id="5703a-171">somente os valores de nível superior serão copiados.</span><span class="sxs-lookup"><span data-stu-id="5703a-171">Only the top-level values are copied.</span></span> <span data-ttu-id="5703a-172">Os objetos filho se referenciarão entre si.</span><span class="sxs-lookup"><span data-stu-id="5703a-172">The child objects will reference each other.</span></span>

### <a name="pstypename-for-custom-object-types"></a><span data-ttu-id="5703a-173">PSTypeName para tipos de objeto personalizados</span><span class="sxs-lookup"><span data-stu-id="5703a-173">PSTypeName for custom object types</span></span>

<span data-ttu-id="5703a-174">Agora que temos um objeto, podemos fazer coisas bem menos óbvias com ele.</span><span class="sxs-lookup"><span data-stu-id="5703a-174">Now that we have an object, there are a few more things we can do with it that may not be nearly as obvious.</span></span> <span data-ttu-id="5703a-175">Antes de tudo, precisamos dar um `PSTypeName` a ele.</span><span class="sxs-lookup"><span data-stu-id="5703a-175">First thing we need to do is give it a `PSTypeName`.</span></span> <span data-ttu-id="5703a-176">Eu geralmente vejo isso ser feito dessa maneira:</span><span class="sxs-lookup"><span data-stu-id="5703a-176">This is the most common way I see people do it:</span></span>

```powershell
$myObject.PSObject.TypeNames.Insert(0,"My.Object")
```

<span data-ttu-id="5703a-177">Recentemente, descobri que outra maneira de fazer isso, ao ler essa [postagem de /u/markekraus][].</span><span class="sxs-lookup"><span data-stu-id="5703a-177">I recently discovered another way to do this from this [post by /u/markekraus][].</span></span> <span data-ttu-id="5703a-178">Continuei pesquisando e encontrei mais postagens sobre o assunto de [Adam Bertram][] e [Mike Shepard][], em que eles falam sobre essa abordagem que permite defini-lo como embutido.</span><span class="sxs-lookup"><span data-stu-id="5703a-178">I did a little digging and more posts about the idea from [Adam Bertram][] and [Mike Shepard][] where they talk about this approach that allows you to define it inline.</span></span>

```powershell
$myObject = [PSCustomObject]@{
    PSTypeName = 'My.Object'
    Name       = 'Kevin'
    Language   = 'PowerShell'
    State      = 'Texas'
}
```

<span data-ttu-id="5703a-179">Eu gosto muito dessa abordagem pela compatibilidade que ela tem com a linguagem.</span><span class="sxs-lookup"><span data-stu-id="5703a-179">I love how nicely this just fits into the language.</span></span> <span data-ttu-id="5703a-180">Agora que temos um objeto com um nome de tipo adequado, podemos fazer mais algumas coisas.</span><span class="sxs-lookup"><span data-stu-id="5703a-180">Now that we have an object with a proper type name, we can do some more things.</span></span>

> [!NOTE]
> <span data-ttu-id="5703a-181">Você também pode criar tipos personalizados do PowerShell usando classes do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5703a-181">You can also create custom PowerShell types using PowerShell classes.</span></span> <span data-ttu-id="5703a-182">Para obter mais informações, confira [Visão geral da classe do PowerShell](/powershell/module/Microsoft.PowerShell.Core/About/about_Classes).</span><span class="sxs-lookup"><span data-stu-id="5703a-182">For more information, see [PowerShell Class Overview](/powershell/module/Microsoft.PowerShell.Core/About/about_Classes).</span></span>

## <a name="using-defaultpropertyset-the-long-way"></a><span data-ttu-id="5703a-183">Como usar DefaultPropertySet (a maneira mais longa)</span><span class="sxs-lookup"><span data-stu-id="5703a-183">Using DefaultPropertySet (the long way)</span></span>

<span data-ttu-id="5703a-184">O PowerShell decide para nós quais propriedades exibir por padrão.</span><span class="sxs-lookup"><span data-stu-id="5703a-184">PowerShell decides for us what properties to display by default.</span></span> <span data-ttu-id="5703a-185">Muitos dos comandos nativos têm um [arquivo de formatação][] `.ps1xml` que faz todo o trabalho pesado.</span><span class="sxs-lookup"><span data-stu-id="5703a-185">A lot of the native commands have a `.ps1xml` [formatting file][] that does all the heavy lifting.</span></span> <span data-ttu-id="5703a-186">Nesta [postagem de Boe Prox][], há outra maneira de fazer isso em nosso objeto personalizado usando apenas o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5703a-186">From this [post by Boe Prox][], there's another way for us to do this on our custom object using just PowerShell.</span></span> <span data-ttu-id="5703a-187">Podemos dá-lo um `MemberSet` para que use.</span><span class="sxs-lookup"><span data-stu-id="5703a-187">We can give it a `MemberSet` for it to use.</span></span>

```powershell
$defaultDisplaySet = 'Name','Language'
$defaultDisplayPropertySet = New-Object System.Management.Automation.PSPropertySet('DefaultDisplayPropertySet',[string[]]$defaultDisplaySet)
$PSStandardMembers = [System.Management.Automation.PSMemberInfo[]]@($defaultDisplayPropertySet)
$MyObject | Add-Member MemberSet PSStandardMembers $PSStandardMembers
```

<span data-ttu-id="5703a-188">Agora, quando o meu objeto simplesmente cair para o Shell, ele mostrará apenas essas propriedades por padrão.</span><span class="sxs-lookup"><span data-stu-id="5703a-188">Now when my object just falls to the shell, it will only show those properties by default.</span></span>

### <a name="update-typedata-with-defaultpropertyset"></a><span data-ttu-id="5703a-189">Update-TypeData com DefaultPropertySet</span><span class="sxs-lookup"><span data-stu-id="5703a-189">Update-TypeData with DefaultPropertySet</span></span>

<span data-ttu-id="5703a-190">É uma abordagem legal, mas encontrei recentemente um jeito melhor ao assistir a [PowerShell Unplugged 2016 com Jeffrey Snover e Don Jones][psunplugged].</span><span class="sxs-lookup"><span data-stu-id="5703a-190">This is nice but I recently saw a better way when watching [PowerShell unplugged 2016 with Jeffrey Snover & Don Jones][psunplugged].</span></span> <span data-ttu-id="5703a-191">Jeffrey estava usando o [Update-TypeData][] para especificar as propriedades padrão.</span><span class="sxs-lookup"><span data-stu-id="5703a-191">Jeffrey was using [Update-TypeData][] to specify the default properties.</span></span>

```powershell
$TypeData = @{
    TypeName = 'My.Object'
    DefaultDisplayPropertySet = 'Name','Language'
}
Update-TypeData @TypeData
```

<span data-ttu-id="5703a-192">Essa maneira é tão simples que eu teria me lembrado dela se eu não tivesse essa postagem como referência rápida.</span><span class="sxs-lookup"><span data-stu-id="5703a-192">That is simple enough that I could almost remember it if I didn't have this post as a quick reference.</span></span> <span data-ttu-id="5703a-193">Agora, eu posso criar facilmente objetos com muitas propriedades e ainda dar a eles uma ótima exibição ao olhá-lo no Shell.</span><span class="sxs-lookup"><span data-stu-id="5703a-193">Now I can easily create objects with lots of properties and still give it a nice clean view when looking at it from the shell.</span></span> <span data-ttu-id="5703a-194">Caso precise, posso acessar ou ver as outras propriedades, elas ainda estão lá.</span><span class="sxs-lookup"><span data-stu-id="5703a-194">If I need to access or see those other properties, they're still there.</span></span>

```powershell
$myObject | Format-List *
```

### <a name="update-typedata-with-scriptproperty"></a><span data-ttu-id="5703a-195">Update-TypeData com ScriptProperty</span><span class="sxs-lookup"><span data-stu-id="5703a-195">Update-TypeData with ScriptProperty</span></span>

<span data-ttu-id="5703a-196">Outra coisa aprendi nesse vídeo foi criar propriedades de script para os objetos.</span><span class="sxs-lookup"><span data-stu-id="5703a-196">Something else I got out of that video was creating script properties for your objects.</span></span> <span data-ttu-id="5703a-197">Aproveito para destacar que isso funciona para objetos existentes também.</span><span class="sxs-lookup"><span data-stu-id="5703a-197">This would be a good time to point out that this works for existing objects too.</span></span>

```powershell
$TypeData = @{
    TypeName = 'My.Object'
    MemberType = 'ScriptProperty'
    MemberName = 'UpperCaseName'
    Value = {$this.Name.toUpper()}
}
Update-TypeData @TypeData
```

<span data-ttu-id="5703a-198">Podemos fazer isso antes ou depois que o objeto for criado e ainda funcionará.</span><span class="sxs-lookup"><span data-stu-id="5703a-198">You can do this before your object is created or after and it will still work.</span></span> <span data-ttu-id="5703a-199">É nesse ponto que essa abordagem difere de usar `Add-Member` com uma propriedade de script.</span><span class="sxs-lookup"><span data-stu-id="5703a-199">This is what makes this different then using `Add-Member` with a script property.</span></span> <span data-ttu-id="5703a-200">Quando usamos `Add-Member` do jeito que mencionei antes, ele só existe nessa instância específica do objeto.</span><span class="sxs-lookup"><span data-stu-id="5703a-200">When you use `Add-Member` the way I referenced earlier, it only exists on that specific instance of the object.</span></span> <span data-ttu-id="5703a-201">Já essa outra abordagem se aplica a todos os objetos com esse `TypeName`.</span><span class="sxs-lookup"><span data-stu-id="5703a-201">This one applies to all objects with this `TypeName`.</span></span>

## <a name="function-parameters"></a><span data-ttu-id="5703a-202">Parâmetros de função</span><span class="sxs-lookup"><span data-stu-id="5703a-202">Function parameters</span></span>

<span data-ttu-id="5703a-203">Agora, podemos usar todos esses tipos personalizados para parâmetros em nossas funções e scripts.</span><span class="sxs-lookup"><span data-stu-id="5703a-203">You can now use these custom types for parameters in your functions and scripts.</span></span> <span data-ttu-id="5703a-204">Podemos usar uma função para criar esses objetos personalizados e, então, passá-los para outras funções.</span><span class="sxs-lookup"><span data-stu-id="5703a-204">You can have one function create these custom objects and then pass them into other functions.</span></span>

```powershell
param( [PSTypeName('My.Object')]$Data )
```

<span data-ttu-id="5703a-205">O PowerShell requer que o objeto seja do tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="5703a-205">PowerShell requires that the object is the type you specified.</span></span> <span data-ttu-id="5703a-206">Caso o tipo não corresponda automaticamente, ele gerará um erro de validação para evitar que você o teste em seu código.</span><span class="sxs-lookup"><span data-stu-id="5703a-206">It throws a validation error if the type doesn't match automatically to save you the step of testing for it in your code.</span></span> <span data-ttu-id="5703a-207">Um ótimo exemplo de como deixar que o PowerShell faça o que faz melhor.</span><span class="sxs-lookup"><span data-stu-id="5703a-207">A great example of letting PowerShell do what it does best.</span></span>

### <a name="function-outputtype"></a><span data-ttu-id="5703a-208">OutputType da Função</span><span class="sxs-lookup"><span data-stu-id="5703a-208">Function OutputType</span></span>

<span data-ttu-id="5703a-209">Também podemos definir um `OutputType` para as funções avançadas.</span><span class="sxs-lookup"><span data-stu-id="5703a-209">You can also define an `OutputType` for your advanced functions.</span></span>

```powershell
function Get-MyObject
{
    [OutputType('My.Object')]
    [CmdletBinding()]
        param
        (
            ...
```

<span data-ttu-id="5703a-210">O valor do atributo **OutputType** é apenas uma observação de documentação.</span><span class="sxs-lookup"><span data-stu-id="5703a-210">The **OutputType** attribute value is only a documentation note.</span></span> <span data-ttu-id="5703a-211">Ele não é derivado do código de função ou comparado à saída real da função.</span><span class="sxs-lookup"><span data-stu-id="5703a-211">It isn't derived from the function code or compared to the actual function output.</span></span>

<span data-ttu-id="5703a-212">O principal motivo para usar um tipo de saída é para que as informações meta da função reflitam suas intenções.</span><span class="sxs-lookup"><span data-stu-id="5703a-212">The main reason you would use an output type is so that meta information about your function reflects your intentions.</span></span> <span data-ttu-id="5703a-213">Coisas como `Get-Command` e `Get-Help` que o seu ambiente de desenvolvimento pode aproveitar.</span><span class="sxs-lookup"><span data-stu-id="5703a-213">Things like `Get-Command` and `Get-Help` that your development environment can take advantage of.</span></span> <span data-ttu-id="5703a-214">Se deseja mais informações, dê uma olhada na ajuda sobre o assunto: [about_Functions_OutputTypeAttribute][].</span><span class="sxs-lookup"><span data-stu-id="5703a-214">If you want more information, then take a look at the help for it: [about_Functions_OutputTypeAttribute][].</span></span>

<span data-ttu-id="5703a-215">Dito isso, caso esteja usando Pester para executar o teste de unidade nas funções, é melhor validar os objetos de saída que correspondam ao **OutputType**.</span><span class="sxs-lookup"><span data-stu-id="5703a-215">With that said, if you're using Pester to unit test your functions then it would be a good idea to validate the output objects match your **OutputType**.</span></span> <span data-ttu-id="5703a-216">Isso pode capturar variáveis que se enquadram no pipe quando não deveriam.</span><span class="sxs-lookup"><span data-stu-id="5703a-216">This could catch variables that just fall to the pipe when they shouldn't.</span></span>

## <a name="closing-thoughts"></a><span data-ttu-id="5703a-217">Considerações finais</span><span class="sxs-lookup"><span data-stu-id="5703a-217">Closing thoughts</span></span>

<span data-ttu-id="5703a-218">Tratamos do contexto do `[PSCustomObject]`, mas muitas dessas informações se aplicam a objetos em geral.</span><span class="sxs-lookup"><span data-stu-id="5703a-218">The context of this was all about `[PSCustomObject]`, but a lot of this information applies to objects in general.</span></span>

<span data-ttu-id="5703a-219">Já vi a maioria desses recursos de maneira avulsa antes, mas nunca os vi apresentados em uma coleção de informações sobre `PSCustomObject`.</span><span class="sxs-lookup"><span data-stu-id="5703a-219">I have seen most of these features in passing before but never saw them presented as a collection of information on `PSCustomObject`.</span></span> <span data-ttu-id="5703a-220">Foi só nesta última semana que me deparei com outra e fiquei surpreso por não ter visto antes.</span><span class="sxs-lookup"><span data-stu-id="5703a-220">Just this last week I stumbled upon another one and was surprised that I had not seen it before.</span></span> <span data-ttu-id="5703a-221">Eu queria reunir todas essas ideias para que você pudesse ter acesso ao panorama geral e estivesse ciente delas quando a oportunidade de usá-las surgir.</span><span class="sxs-lookup"><span data-stu-id="5703a-221">I wanted to pull all these ideas together so you can hopefully see the bigger picture and be aware of them when you have an opportunity to use them.</span></span> <span data-ttu-id="5703a-222">Espero que você tenha aprendido algo útil e possa encontrar um jeito de usar esse conhecimento em seus scripts.</span><span class="sxs-lookup"><span data-stu-id="5703a-222">I hope you learned something and can find a way to work this into your scripts.</span></span>

<!-- link references -->
[versão original]: https://powershellexplained.com/2016-10-28-powershell-everything-you-wanted-to-know-about-pscustomobject/
[original version]: https://powershellexplained.com/2016-10-28-powershell-everything-you-wanted-to-know-about-pscustomobject/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[postagem de Boe Prox]: https://learn-PowerShell.net/2013/08/03/quick-hits-set-the-default-property-display-in-PowerShell-on-custom-objects/
[post by Boe Prox]: https://learn-PowerShell.net/2013/08/03/quick-hits-set-the-default-property-display-in-PowerShell-on-custom-objects/
[arquivo de formatação]: https://mcpmag.com/articles/2014/05/13/PowerShell-properties-part-3.aspx
[formatting file]: https://mcpmag.com/articles/2014/05/13/PowerShell-properties-part-3.aspx
[about_Functions_OutputTypeAttribute]: /powershell/module/microsoft.powershell.core/about/about_functions_outputtypeattribute
[As várias maneiras de ler e gravar em arquivos]: https://powershellexplained.com/2017-03-18-Powershell-reading-and-saving-data-to-files
[The many ways to read and write to files]: https://powershellexplained.com/2017-03-18-Powershell-reading-and-saving-data-to-files
[postagem de /u/markekraus]: https://www.reddit.com/r/PowerShell/comments/590awc/is_it_possible_to_initialize_a_pscustoobject_with/
[post by /u/markekraus]: https://www.reddit.com/r/PowerShell/comments/590awc/is_it_possible_to_initialize_a_pscustoobject_with/
[Adam Bertram]: http://www.adamtheautomator.com/building-custom-object-types-PowerShell-pstypename/
[Mike Shepard]: https://powershellstation.com/2016/05/22/custom-objects-and-pstypename/
[psunplugged]: https://www.youtube.com/watch?v=Ab46gHXNm8Q
[Update-TypeData]: /powershell/module/microsoft.powershell.utility/update-typedata
