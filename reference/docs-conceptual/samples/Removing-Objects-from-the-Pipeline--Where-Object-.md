---
ms.date: 12/23/2019
keywords: powershell, cmdlet
title: Removendo objetos do pipeline Where-Object
description: O cmdlet Where-Object permite filtrar objetos passados no pipeline.
ms.openlocfilehash: e744dc671303711f1cbe8cc724a97c3327c1da85
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500106"
---
# <a name="removing-objects-from-the-pipeline-where-object"></a><span data-ttu-id="74375-104">Removendo objetos do pipeline (Where-Object)</span><span class="sxs-lookup"><span data-stu-id="74375-104">Removing Objects from the Pipeline (Where-Object)</span></span>

<span data-ttu-id="74375-105">No PowerShell, você muitas vezes gera e passa mais objetos para um pipeline do que deseja.</span><span class="sxs-lookup"><span data-stu-id="74375-105">In PowerShell, you often generate and pass along more objects to a pipeline than you want.</span></span> <span data-ttu-id="74375-106">É possível especificar as propriedades de determinados objetos para exibição usando os cmdlets `Format-*`, mas isso não ajuda em problemas de remoção de objetos inteiros da exibição.</span><span class="sxs-lookup"><span data-stu-id="74375-106">You can specify the properties of particular objects to display by using the `Format-*` cmdlets, but this does not help with the problem of removing entire objects from the display.</span></span> <span data-ttu-id="74375-107">Talvez você queira filtrar objetos antes do final de um pipeline para poder executar ações em apenas um subconjunto dos objetos gerados inicialmente.</span><span class="sxs-lookup"><span data-stu-id="74375-107">You may want to filter objects before the end of a pipeline, so you can perform actions on only a subset of the initially-generated objects.</span></span>

<span data-ttu-id="74375-108">O PowerShell inclui um cmdlet `Where-Object` que permite testar cada objeto no pipeline e apenas passá-lo pelo pipeline caso ele atenda a determinada condição de teste.</span><span class="sxs-lookup"><span data-stu-id="74375-108">PowerShell includes a `Where-Object` cmdlet that allows you to test each object in the pipeline and only pass it along the pipeline if it meets a particular test condition.</span></span> <span data-ttu-id="74375-109">Objetos que não passarem no teste são removidos do pipeline.</span><span class="sxs-lookup"><span data-stu-id="74375-109">Objects that do not pass the test are removed from the pipeline.</span></span> <span data-ttu-id="74375-110">Forneça a condição de teste como o valor do parâmetro **FilterScript** .</span><span class="sxs-lookup"><span data-stu-id="74375-110">You supply the test condition as the value of the **FilterScript** parameter.</span></span>

## <a name="performing-simple-tests-with-where-object"></a><span data-ttu-id="74375-111">Executando testes simples com Where-Object</span><span class="sxs-lookup"><span data-stu-id="74375-111">Performing Simple Tests with Where-Object</span></span>

<span data-ttu-id="74375-112">O valor de **FilterScript** é um *bloco de script* – um ou mais comandos do PowerShell entre chaves (`{}`) – que é avaliado como verdadeiro ou falso.</span><span class="sxs-lookup"><span data-stu-id="74375-112">The value of **FilterScript** is a *script block* - one or more PowerShell commands surrounded by braces (`{}`) - that evaluates to true or false.</span></span> <span data-ttu-id="74375-113">Esses blocos de script podem ser muito simples, mas criá-los requer conhecimento sobre outro conceito do PowerShell, os operadores de comparação.</span><span class="sxs-lookup"><span data-stu-id="74375-113">These script blocks can be very simple, but creating them requires knowing about another PowerShell concept, comparison operators.</span></span> <span data-ttu-id="74375-114">Um operador de comparação compara os itens que aparecem em cada lado dela.</span><span class="sxs-lookup"><span data-stu-id="74375-114">A comparison operator compares the items that appear on each side of it.</span></span> <span data-ttu-id="74375-115">Os operadores de comparação começam com um caractere de hífen (`-`) e são seguidos por um nome.</span><span class="sxs-lookup"><span data-stu-id="74375-115">Comparison operators begin with a hyphen character (`-`) and are followed by a name.</span></span> <span data-ttu-id="74375-116">Operadores de comparação básicos funcionam em praticamente qualquer tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="74375-116">Basic comparison operators work on almost any kind of object.</span></span> <span data-ttu-id="74375-117">Os operadores de comparação mais avançados podem funcionar apenas em texto ou matrizes.</span><span class="sxs-lookup"><span data-stu-id="74375-117">The more advanced comparison operators might only work on text or arrays.</span></span>

> [!NOTE]
> <span data-ttu-id="74375-118">Por padrão, ao trabalhar com texto, os operadores de comparação do PowerShell não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="74375-118">By default, when working with text, PowerShell comparison operators are case-insensitive.</span></span>

<span data-ttu-id="74375-119">Devido a considerações de análise, símbolos como `<`,`>` e `=` não são usados como operadores de comparação.</span><span class="sxs-lookup"><span data-stu-id="74375-119">Due to parsing considerations, symbols such as `<`,`>`, and `=` are not used as comparison operators.</span></span> <span data-ttu-id="74375-120">Em vez disso, os operadores de comparação são compostos por letras.</span><span class="sxs-lookup"><span data-stu-id="74375-120">Instead, comparison operators are comprised of letters.</span></span> <span data-ttu-id="74375-121">Os operadores de comparação básicos estão listados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="74375-121">The basic comparison operators are listed in the following table.</span></span>

| <span data-ttu-id="74375-122">Operador de Comparação</span><span class="sxs-lookup"><span data-stu-id="74375-122">Comparison Operator</span></span> |                  <span data-ttu-id="74375-123">Significado</span><span class="sxs-lookup"><span data-stu-id="74375-123">Meaning</span></span>                   |    <span data-ttu-id="74375-124">Exemplo (returna true)</span><span class="sxs-lookup"><span data-stu-id="74375-124">Example (returns true)</span></span>    |
| ------------------- | ------------------------------------------ | ---------------------------- |
| <span data-ttu-id="74375-125">-eq</span><span class="sxs-lookup"><span data-stu-id="74375-125">-eq</span></span>                 | <span data-ttu-id="74375-126">é igual a</span><span class="sxs-lookup"><span data-stu-id="74375-126">is equal to</span></span>                                | <span data-ttu-id="74375-127">1 -eq 1</span><span class="sxs-lookup"><span data-stu-id="74375-127">1 -eq 1</span></span>                      |
| <span data-ttu-id="74375-128">-ne</span><span class="sxs-lookup"><span data-stu-id="74375-128">-ne</span></span>                 | <span data-ttu-id="74375-129">Não é igual a</span><span class="sxs-lookup"><span data-stu-id="74375-129">Is not equal to</span></span>                            | <span data-ttu-id="74375-130">1 -ne 2</span><span class="sxs-lookup"><span data-stu-id="74375-130">1 -ne 2</span></span>                      |
| <span data-ttu-id="74375-131">-lt</span><span class="sxs-lookup"><span data-stu-id="74375-131">-lt</span></span>                 | <span data-ttu-id="74375-132">É menor que</span><span class="sxs-lookup"><span data-stu-id="74375-132">Is less than</span></span>                               | <span data-ttu-id="74375-133">1 -lt 2</span><span class="sxs-lookup"><span data-stu-id="74375-133">1 -lt 2</span></span>                      |
| <span data-ttu-id="74375-134">-le</span><span class="sxs-lookup"><span data-stu-id="74375-134">-le</span></span>                 | <span data-ttu-id="74375-135">É menor ou igual a</span><span class="sxs-lookup"><span data-stu-id="74375-135">Is less than or equal to</span></span>                   | <span data-ttu-id="74375-136">1 -le 2</span><span class="sxs-lookup"><span data-stu-id="74375-136">1 -le 2</span></span>                      |
| <span data-ttu-id="74375-137">-gt</span><span class="sxs-lookup"><span data-stu-id="74375-137">-gt</span></span>                 | <span data-ttu-id="74375-138">É maior que</span><span class="sxs-lookup"><span data-stu-id="74375-138">Is greater than</span></span>                            | <span data-ttu-id="74375-139">2 -gt 1</span><span class="sxs-lookup"><span data-stu-id="74375-139">2 -gt 1</span></span>                      |
| <span data-ttu-id="74375-140">-ge</span><span class="sxs-lookup"><span data-stu-id="74375-140">-ge</span></span>                 | <span data-ttu-id="74375-141">É maior ou igual a</span><span class="sxs-lookup"><span data-stu-id="74375-141">Is greater than or equal to</span></span>                | <span data-ttu-id="74375-142">2 -ge 1</span><span class="sxs-lookup"><span data-stu-id="74375-142">2 -ge 1</span></span>                      |
| <span data-ttu-id="74375-143">-like</span><span class="sxs-lookup"><span data-stu-id="74375-143">-like</span></span>               | <span data-ttu-id="74375-144">É como (curinga de comparação para texto)</span><span class="sxs-lookup"><span data-stu-id="74375-144">Is like (wildcard comparison for text)</span></span>     | <span data-ttu-id="74375-145">"file.doc" -like "f\*.do?"</span><span class="sxs-lookup"><span data-stu-id="74375-145">"file.doc" -like "f\*.do?"</span></span>    |
| <span data-ttu-id="74375-146">-notlike</span><span class="sxs-lookup"><span data-stu-id="74375-146">-notlike</span></span>            | <span data-ttu-id="74375-147">Não é como (curinga de comparação para texto)</span><span class="sxs-lookup"><span data-stu-id="74375-147">Is not like (wildcard comparison for text)</span></span> | <span data-ttu-id="74375-148">"file.doc" -notlike "p\*.doc"</span><span class="sxs-lookup"><span data-stu-id="74375-148">"file.doc" -notlike "p\*.doc"</span></span> |
| <span data-ttu-id="74375-149">-contains</span><span class="sxs-lookup"><span data-stu-id="74375-149">-contains</span></span>           | <span data-ttu-id="74375-150">Contém</span><span class="sxs-lookup"><span data-stu-id="74375-150">Contains</span></span>                                   | <span data-ttu-id="74375-151">1,2,3 -contains 1</span><span class="sxs-lookup"><span data-stu-id="74375-151">1,2,3 -contains 1</span></span>            |
| <span data-ttu-id="74375-152">-notcontains</span><span class="sxs-lookup"><span data-stu-id="74375-152">-notcontains</span></span>        | <span data-ttu-id="74375-153">Não contém</span><span class="sxs-lookup"><span data-stu-id="74375-153">Does not contain</span></span>                           | <span data-ttu-id="74375-154">1,2,3 -notcontains 4</span><span class="sxs-lookup"><span data-stu-id="74375-154">1,2,3 -notcontains 4</span></span>         |

<span data-ttu-id="74375-155">Os blocos de script de `Where-Object` usam a variável especial `$_` para fazer referência ao objeto atual no pipeline.</span><span class="sxs-lookup"><span data-stu-id="74375-155">`Where-Object` script blocks use the special variable `$_` to refer to the current object in the pipeline.</span></span> <span data-ttu-id="74375-156">Veja um exemplo de como isso funciona.</span><span class="sxs-lookup"><span data-stu-id="74375-156">Here is an example of how it works.</span></span> <span data-ttu-id="74375-157">Se você tiver uma lista de números e quiser retornar apenas os inferiores a três, poderá usar `Where-Object` para filtrar os números digitando:</span><span class="sxs-lookup"><span data-stu-id="74375-157">If you have a list of numbers, and only want to return the ones that are less than 3, you can use `Where-Object` to filter the numbers by typing:</span></span>

```
1,2,3,4 | Where-Object {$_ -lt 3}
1
2
```

## <a name="filtering-based-on-object-properties"></a><span data-ttu-id="74375-158">Filtragem com base nas propriedades de objeto</span><span class="sxs-lookup"><span data-stu-id="74375-158">Filtering Based on Object Properties</span></span>

<span data-ttu-id="74375-159">Como `$_` se refere ao objeto atual no pipeline, podemos acessar suas propriedades para nossos testes.</span><span class="sxs-lookup"><span data-stu-id="74375-159">Since `$_` refers to the current pipeline object, we can access its properties for our tests.</span></span>

<span data-ttu-id="74375-160">Por exemplo, podemos ver a classe **Win32_SystemDriver** no WMI.</span><span class="sxs-lookup"><span data-stu-id="74375-160">As an example, we can look at the **Win32_SystemDriver** class in WMI.</span></span> <span data-ttu-id="74375-161">Pode haver centenas de drivers do sistema em um determinado sistema, mas você pode só estar interessado em um determinado conjunto de drivers do sistema, como aqueles que estão sendo executados.</span><span class="sxs-lookup"><span data-stu-id="74375-161">There might be hundreds of system drivers on a particular system, but you might only be interested in a particular set of the system drivers, such as those which are currently running.</span></span> <span data-ttu-id="74375-162">Para a classe **Win32_SystemDriver** , a propriedade relevante é **State** .</span><span class="sxs-lookup"><span data-stu-id="74375-162">For the **Win32_SystemDriver** class the relevant property is **State** .</span></span> <span data-ttu-id="74375-163">Você pode filtrar os drivers do sistema selecionando apenas aqueles em execução digitando:</span><span class="sxs-lookup"><span data-stu-id="74375-163">You can filter the system drivers, selecting only the running ones by typing:</span></span>

```powershell
Get-CimInstance -Class Win32_SystemDriver |
  Where-Object {$_.State -eq 'Running'}
```

<span data-ttu-id="74375-164">Isso ainda produz uma longa lista.</span><span class="sxs-lookup"><span data-stu-id="74375-164">This still produces a long list.</span></span> <span data-ttu-id="74375-165">Você pode filtrar para escolher apenas os drivers definidos para iniciar automaticamente testando também o valor de **StartMode** :</span><span class="sxs-lookup"><span data-stu-id="74375-165">You may want to filter to only select the drivers set to start automatically by testing the **StartMode** value as well:</span></span>

```powershell
Get-CimInstance -Class Win32_SystemDriver |
  Where-Object {$_.State -eq "Running"} |
    Where-Object {$_.StartMode -eq "Auto"}
```

```Output
DisplayName : RAS Asynchronous Media Driver
Name        : AsyncMac
State       : Running
Status      : OK
Started     : True

DisplayName : Audio Stub Driver
Name        : audstub
State       : Running
Status      : OK
Started     : True
...
```

<span data-ttu-id="74375-166">Isso nos fornece muitas informações que já não precisamos mais porque sabemos que os drivers estão sendo executados.</span><span class="sxs-lookup"><span data-stu-id="74375-166">This gives us a lot of information we no longer need because we know that the drivers are running.</span></span>
<span data-ttu-id="74375-167">Na verdade, a única informação que é provavelmente precisamos neste ponto é o nome e o nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="74375-167">In fact, the only information we probably need at this point are the name and the display name.</span></span> <span data-ttu-id="74375-168">O comando a seguir inclui somente essas duas propriedades, resultando em uma saída muito mais simples:</span><span class="sxs-lookup"><span data-stu-id="74375-168">The following command includes only those two properties, resulting in much simpler output:</span></span>

```powershell
Get-CimInstance -Class Win32_SystemDriver |
  Where-Object {$_.State -eq "Running"} |
    Where-Object {$_.StartMode -eq "Manual"} |
      Format-Table -Property Name,DisplayName
```

```Output
Name              DisplayName
----              -----------
AsyncMac               RAS Asynchronous Media Driver
bindflt                Windows Bind Filter Driver
bowser                 Browser
CompositeBus           Composite Bus Enumerator Driver
condrv                 Console Driver
HdAudAddService        Microsoft 1.1 UAA Function Driver for High Definition Audio Service
HDAudBus               Microsoft UAA Bus Driver for High Definition Audio
HidUsb                 Microsoft HID Class Driver
HTTP                   HTTP Service
igfx                   igfx
IntcDAud               Intel(R) Display Audio
intelppm               Intel Processor Driver
...
```

<span data-ttu-id="74375-169">Há dois elementos `Where-Object` no comando acima, mas eles podem ser expressados em um único elemento `Where-Object` usando o operador lógico `-and`, desta forma:</span><span class="sxs-lookup"><span data-stu-id="74375-169">There are two `Where-Object` elements in the above command, but they can be expressed in a single `Where-Object` element by using the `-and` logical operator, like this:</span></span>

```powershell
Get-CimInstance -Class Win32_SystemDriver |
  Where-Object {($_.State -eq 'Running') -and ($_.StartMode -eq 'Manual')} |
    Format-Table -Property Name,DisplayName
```

<span data-ttu-id="74375-170">Os operadores lógicos padrão são listados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="74375-170">The standard logical operators are listed in the following table.</span></span>

| <span data-ttu-id="74375-171">Operador Lógico</span><span class="sxs-lookup"><span data-stu-id="74375-171">Logical Operator</span></span> |                 <span data-ttu-id="74375-172">Significado</span><span class="sxs-lookup"><span data-stu-id="74375-172">Meaning</span></span>                  |  <span data-ttu-id="74375-173">Exemplo (returna true)</span><span class="sxs-lookup"><span data-stu-id="74375-173">Example (returns true)</span></span>  |
| ---------------- | ---------------------------------------- | ------------------------ |
| <span data-ttu-id="74375-174">-and</span><span class="sxs-lookup"><span data-stu-id="74375-174">-and</span></span>             | <span data-ttu-id="74375-175">E lógico; verdadeiro se ambos os lados forem verdadeiros</span><span class="sxs-lookup"><span data-stu-id="74375-175">Logical and; true if both sides are true</span></span> | <span data-ttu-id="74375-176">(1 -eq 1) -and (2 -eq 2)</span><span class="sxs-lookup"><span data-stu-id="74375-176">(1 -eq 1) -and (2 -eq 2)</span></span> |
| <span data-ttu-id="74375-177">-or</span><span class="sxs-lookup"><span data-stu-id="74375-177">-or</span></span>              | <span data-ttu-id="74375-178">Ou lógico; verdadeiro se um dos lados for verdadeiro</span><span class="sxs-lookup"><span data-stu-id="74375-178">Logical or; true if either side is true</span></span>  | <span data-ttu-id="74375-179">(1 -eq 1) -or (1 -eq 2)</span><span class="sxs-lookup"><span data-stu-id="74375-179">(1 -eq 1) -or (1 -eq 2)</span></span>  |
| <span data-ttu-id="74375-180">-not</span><span class="sxs-lookup"><span data-stu-id="74375-180">-not</span></span>             | <span data-ttu-id="74375-181">Não lógico; inverte o verdadeiro e o falso</span><span class="sxs-lookup"><span data-stu-id="74375-181">Logical not; reverses true and false</span></span>     | <span data-ttu-id="74375-182">-not (1 -eq 2)</span><span class="sxs-lookup"><span data-stu-id="74375-182">-not (1 -eq 2)</span></span>           |
| \!               | <span data-ttu-id="74375-183">Não lógico; inverte o verdadeiro e o falso</span><span class="sxs-lookup"><span data-stu-id="74375-183">Logical not; reverses true and false</span></span>     | <span data-ttu-id="74375-184">\!(1 -eq 2)</span><span class="sxs-lookup"><span data-stu-id="74375-184">\!(1 -eq 2)</span></span>              |
