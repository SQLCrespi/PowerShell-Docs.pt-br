---
ms.date: 12/23/2019
keywords: powershell, cmdlet
title: Removendo objetos do pipeline Where-Object
ms.openlocfilehash: 370e7745341b70c0794352a690d5750d21f53ac2
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "75737178"
---
# <a name="removing-objects-from-the-pipeline-where-object"></a><span data-ttu-id="0f43b-103">Removendo objetos do pipeline (Where-Object)</span><span class="sxs-lookup"><span data-stu-id="0f43b-103">Removing Objects from the Pipeline (Where-Object)</span></span>

<span data-ttu-id="0f43b-104">No PowerShell, você muitas vezes gera e passa mais objetos para um pipeline do que deseja.</span><span class="sxs-lookup"><span data-stu-id="0f43b-104">In PowerShell, you often generate and pass along more objects to a pipeline than you want.</span></span> <span data-ttu-id="0f43b-105">É possível especificar as propriedades de determinados objetos para exibição usando os cmdlets `Format-*`, mas isso não ajuda em problemas de remoção de objetos inteiros da exibição.</span><span class="sxs-lookup"><span data-stu-id="0f43b-105">You can specify the properties of particular objects to display by using the `Format-*` cmdlets, but this does not help with the problem of removing entire objects from the display.</span></span> <span data-ttu-id="0f43b-106">Talvez você queira filtrar objetos antes do final de um pipeline para poder executar ações em apenas um subconjunto dos objetos gerados inicialmente.</span><span class="sxs-lookup"><span data-stu-id="0f43b-106">You may want to filter objects before the end of a pipeline, so you can perform actions on only a subset of the initially-generated objects.</span></span>

<span data-ttu-id="0f43b-107">O PowerShell inclui um cmdlet `Where-Object` que permite testar cada objeto no pipeline e apenas passá-lo pelo pipeline caso ele atenda a determinada condição de teste.</span><span class="sxs-lookup"><span data-stu-id="0f43b-107">PowerShell includes a `Where-Object` cmdlet that allows you to test each object in the pipeline and only pass it along the pipeline if it meets a particular test condition.</span></span> <span data-ttu-id="0f43b-108">Objetos que não passarem no teste são removidos do pipeline.</span><span class="sxs-lookup"><span data-stu-id="0f43b-108">Objects that do not pass the test are removed from the pipeline.</span></span> <span data-ttu-id="0f43b-109">Forneça a condição de teste como o valor do parâmetro **FilterScript**.</span><span class="sxs-lookup"><span data-stu-id="0f43b-109">You supply the test condition as the value of the **FilterScript** parameter.</span></span>

## <a name="performing-simple-tests-with-where-object"></a><span data-ttu-id="0f43b-110">Executando testes simples com Where-Object</span><span class="sxs-lookup"><span data-stu-id="0f43b-110">Performing Simple Tests with Where-Object</span></span>

<span data-ttu-id="0f43b-111">O valor de **FilterScript** é um *bloco de script* – um ou mais comandos do PowerShell entre chaves (`{}`) – que é avaliado como verdadeiro ou falso.</span><span class="sxs-lookup"><span data-stu-id="0f43b-111">The value of **FilterScript** is a *script block* - one or more PowerShell commands surrounded by braces (`{}`) - that evaluates to true or false.</span></span> <span data-ttu-id="0f43b-112">Esses blocos de script podem ser muito simples, mas criá-los requer conhecimento sobre outro conceito do PowerShell, os operadores de comparação.</span><span class="sxs-lookup"><span data-stu-id="0f43b-112">These script blocks can be very simple, but creating them requires knowing about another PowerShell concept, comparison operators.</span></span> <span data-ttu-id="0f43b-113">Um operador de comparação compara os itens que aparecem em cada lado dela.</span><span class="sxs-lookup"><span data-stu-id="0f43b-113">A comparison operator compares the items that appear on each side of it.</span></span> <span data-ttu-id="0f43b-114">Os operadores de comparação começam com um caractere de hífen (`-`) e são seguidos por um nome.</span><span class="sxs-lookup"><span data-stu-id="0f43b-114">Comparison operators begin with a hyphen character (`-`) and are followed by a name.</span></span> <span data-ttu-id="0f43b-115">Operadores de comparação básicos funcionam em praticamente qualquer tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="0f43b-115">Basic comparison operators work on almost any kind of object.</span></span> <span data-ttu-id="0f43b-116">Os operadores de comparação mais avançados podem funcionar apenas em texto ou matrizes.</span><span class="sxs-lookup"><span data-stu-id="0f43b-116">The more advanced comparison operators might only work on text or arrays.</span></span>

> [!NOTE]
> <span data-ttu-id="0f43b-117">Por padrão, ao trabalhar com texto, os operadores de comparação do PowerShell não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="0f43b-117">By default, when working with text, PowerShell comparison operators are case-insensitive.</span></span>

<span data-ttu-id="0f43b-118">Devido a considerações de análise, símbolos como `<`,`>` e `=` não são usados como operadores de comparação.</span><span class="sxs-lookup"><span data-stu-id="0f43b-118">Due to parsing considerations, symbols such as `<`,`>`, and `=` are not used as comparison operators.</span></span> <span data-ttu-id="0f43b-119">Em vez disso, os operadores de comparação são compostos por letras.</span><span class="sxs-lookup"><span data-stu-id="0f43b-119">Instead, comparison operators are comprised of letters.</span></span> <span data-ttu-id="0f43b-120">Os operadores de comparação básicos estão listados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="0f43b-120">The basic comparison operators are listed in the following table.</span></span>

| <span data-ttu-id="0f43b-121">Operador de Comparação</span><span class="sxs-lookup"><span data-stu-id="0f43b-121">Comparison Operator</span></span> |                  <span data-ttu-id="0f43b-122">Significado</span><span class="sxs-lookup"><span data-stu-id="0f43b-122">Meaning</span></span>                   |    <span data-ttu-id="0f43b-123">Exemplo (returna true)</span><span class="sxs-lookup"><span data-stu-id="0f43b-123">Example (returns true)</span></span>    |
| ------------------- | ------------------------------------------ | ---------------------------- |
| <span data-ttu-id="0f43b-124">-eq</span><span class="sxs-lookup"><span data-stu-id="0f43b-124">-eq</span></span>                 | <span data-ttu-id="0f43b-125">é igual a</span><span class="sxs-lookup"><span data-stu-id="0f43b-125">is equal to</span></span>                                | <span data-ttu-id="0f43b-126">1 -eq 1</span><span class="sxs-lookup"><span data-stu-id="0f43b-126">1 -eq 1</span></span>                      |
| <span data-ttu-id="0f43b-127">-ne</span><span class="sxs-lookup"><span data-stu-id="0f43b-127">-ne</span></span>                 | <span data-ttu-id="0f43b-128">Não é igual a</span><span class="sxs-lookup"><span data-stu-id="0f43b-128">Is not equal to</span></span>                            | <span data-ttu-id="0f43b-129">1 -ne 2</span><span class="sxs-lookup"><span data-stu-id="0f43b-129">1 -ne 2</span></span>                      |
| <span data-ttu-id="0f43b-130">-lt</span><span class="sxs-lookup"><span data-stu-id="0f43b-130">-lt</span></span>                 | <span data-ttu-id="0f43b-131">É menor que</span><span class="sxs-lookup"><span data-stu-id="0f43b-131">Is less than</span></span>                               | <span data-ttu-id="0f43b-132">1 -lt 2</span><span class="sxs-lookup"><span data-stu-id="0f43b-132">1 -lt 2</span></span>                      |
| <span data-ttu-id="0f43b-133">-le</span><span class="sxs-lookup"><span data-stu-id="0f43b-133">-le</span></span>                 | <span data-ttu-id="0f43b-134">É menor ou igual a</span><span class="sxs-lookup"><span data-stu-id="0f43b-134">Is less than or equal to</span></span>                   | <span data-ttu-id="0f43b-135">1 -le 2</span><span class="sxs-lookup"><span data-stu-id="0f43b-135">1 -le 2</span></span>                      |
| <span data-ttu-id="0f43b-136">-gt</span><span class="sxs-lookup"><span data-stu-id="0f43b-136">-gt</span></span>                 | <span data-ttu-id="0f43b-137">É maior que</span><span class="sxs-lookup"><span data-stu-id="0f43b-137">Is greater than</span></span>                            | <span data-ttu-id="0f43b-138">2 -gt 1</span><span class="sxs-lookup"><span data-stu-id="0f43b-138">2 -gt 1</span></span>                      |
| <span data-ttu-id="0f43b-139">-ge</span><span class="sxs-lookup"><span data-stu-id="0f43b-139">-ge</span></span>                 | <span data-ttu-id="0f43b-140">É maior ou igual a</span><span class="sxs-lookup"><span data-stu-id="0f43b-140">Is greater than or equal to</span></span>                | <span data-ttu-id="0f43b-141">2 -ge 1</span><span class="sxs-lookup"><span data-stu-id="0f43b-141">2 -ge 1</span></span>                      |
| <span data-ttu-id="0f43b-142">-like</span><span class="sxs-lookup"><span data-stu-id="0f43b-142">-like</span></span>               | <span data-ttu-id="0f43b-143">É como (curinga de comparação para texto)</span><span class="sxs-lookup"><span data-stu-id="0f43b-143">Is like (wildcard comparison for text)</span></span>     | <span data-ttu-id="0f43b-144">"file.doc" -like "f\*.do?"</span><span class="sxs-lookup"><span data-stu-id="0f43b-144">"file.doc" -like "f\*.do?"</span></span>    |
| <span data-ttu-id="0f43b-145">-notlike</span><span class="sxs-lookup"><span data-stu-id="0f43b-145">-notlike</span></span>            | <span data-ttu-id="0f43b-146">Não é como (curinga de comparação para texto)</span><span class="sxs-lookup"><span data-stu-id="0f43b-146">Is not like (wildcard comparison for text)</span></span> | <span data-ttu-id="0f43b-147">"file.doc" -notlike "p\*.doc"</span><span class="sxs-lookup"><span data-stu-id="0f43b-147">"file.doc" -notlike "p\*.doc"</span></span> |
| <span data-ttu-id="0f43b-148">-contains</span><span class="sxs-lookup"><span data-stu-id="0f43b-148">-contains</span></span>           | <span data-ttu-id="0f43b-149">Contém</span><span class="sxs-lookup"><span data-stu-id="0f43b-149">Contains</span></span>                                   | <span data-ttu-id="0f43b-150">1,2,3 -contains 1</span><span class="sxs-lookup"><span data-stu-id="0f43b-150">1,2,3 -contains 1</span></span>            |
| <span data-ttu-id="0f43b-151">-notcontains</span><span class="sxs-lookup"><span data-stu-id="0f43b-151">-notcontains</span></span>        | <span data-ttu-id="0f43b-152">Não contém</span><span class="sxs-lookup"><span data-stu-id="0f43b-152">Does not contain</span></span>                           | <span data-ttu-id="0f43b-153">1,2,3 -notcontains 4</span><span class="sxs-lookup"><span data-stu-id="0f43b-153">1,2,3 -notcontains 4</span></span>         |

<span data-ttu-id="0f43b-154">Os blocos de script de `Where-Object` usam a variável especial `$_` para fazer referência ao objeto atual no pipeline.</span><span class="sxs-lookup"><span data-stu-id="0f43b-154">`Where-Object` script blocks use the special variable `$_` to refer to the current object in the pipeline.</span></span> <span data-ttu-id="0f43b-155">Veja um exemplo de como isso funciona.</span><span class="sxs-lookup"><span data-stu-id="0f43b-155">Here is an example of how it works.</span></span> <span data-ttu-id="0f43b-156">Se você tiver uma lista de números e quiser retornar apenas os inferiores a três, poderá usar `Where-Object` para filtrar os números digitando:</span><span class="sxs-lookup"><span data-stu-id="0f43b-156">If you have a list of numbers, and only want to return the ones that are less than 3, you can use `Where-Object` to filter the numbers by typing:</span></span>

```
1,2,3,4 | Where-Object {$_ -lt 3}
1
2
```

## <a name="filtering-based-on-object-properties"></a><span data-ttu-id="0f43b-157">Filtragem com base nas propriedades de objeto</span><span class="sxs-lookup"><span data-stu-id="0f43b-157">Filtering Based on Object Properties</span></span>

<span data-ttu-id="0f43b-158">Como `$_` se refere ao objeto atual no pipeline, podemos acessar suas propriedades para nossos testes.</span><span class="sxs-lookup"><span data-stu-id="0f43b-158">Since `$_` refers to the current pipeline object, we can access its properties for our tests.</span></span>

<span data-ttu-id="0f43b-159">Por exemplo, podemos ver a classe **Win32_SystemDriver** no WMI.</span><span class="sxs-lookup"><span data-stu-id="0f43b-159">As an example, we can look at the **Win32_SystemDriver** class in WMI.</span></span> <span data-ttu-id="0f43b-160">Pode haver centenas de drivers do sistema em um determinado sistema, mas você pode só estar interessado em um determinado conjunto de drivers do sistema, como aqueles que estão sendo executados.</span><span class="sxs-lookup"><span data-stu-id="0f43b-160">There might be hundreds of system drivers on a particular system, but you might only be interested in a particular set of the system drivers, such as those which are currently running.</span></span> <span data-ttu-id="0f43b-161">Para a classe **Win32_SystemDriver**, a propriedade relevante é **State**.</span><span class="sxs-lookup"><span data-stu-id="0f43b-161">For the **Win32_SystemDriver** class the relevant property is **State**.</span></span> <span data-ttu-id="0f43b-162">Você pode filtrar os drivers do sistema selecionando apenas aqueles em execução digitando:</span><span class="sxs-lookup"><span data-stu-id="0f43b-162">You can filter the system drivers, selecting only the running ones by typing:</span></span>

```powershell
Get-CimInstance -Class Win32_SystemDriver |
  Where-Object {$_.State -eq 'Running'}
```

<span data-ttu-id="0f43b-163">Isso ainda produz uma longa lista.</span><span class="sxs-lookup"><span data-stu-id="0f43b-163">This still produces a long list.</span></span> <span data-ttu-id="0f43b-164">Você pode filtrar para escolher apenas os drivers definidos para iniciar automaticamente testando também o valor de **StartMode**:</span><span class="sxs-lookup"><span data-stu-id="0f43b-164">You may want to filter to only select the drivers set to start automatically by testing the **StartMode** value as well:</span></span>

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

<span data-ttu-id="0f43b-165">Isso nos fornece muitas informações que já não precisamos mais porque sabemos que os drivers estão sendo executados.</span><span class="sxs-lookup"><span data-stu-id="0f43b-165">This gives us a lot of information we no longer need because we know that the drivers are running.</span></span>
<span data-ttu-id="0f43b-166">Na verdade, a única informação que é provavelmente precisamos neste ponto é o nome e o nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="0f43b-166">In fact, the only information we probably need at this point are the name and the display name.</span></span> <span data-ttu-id="0f43b-167">O comando a seguir inclui somente essas duas propriedades, resultando em uma saída muito mais simples:</span><span class="sxs-lookup"><span data-stu-id="0f43b-167">The following command includes only those two properties, resulting in much simpler output:</span></span>

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

<span data-ttu-id="0f43b-168">Há dois elementos `Where-Object` no comando acima, mas eles podem ser expressados em um único elemento `Where-Object` usando o operador lógico `-and`, desta forma:</span><span class="sxs-lookup"><span data-stu-id="0f43b-168">There are two `Where-Object` elements in the above command, but they can be expressed in a single `Where-Object` element by using the `-and` logical operator, like this:</span></span>

```powershell
Get-CimInstance -Class Win32_SystemDriver |
  Where-Object {($_.State -eq 'Running') -and ($_.StartMode -eq 'Manual')} |
    Format-Table -Property Name,DisplayName
```

<span data-ttu-id="0f43b-169">Os operadores lógicos padrão são listados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="0f43b-169">The standard logical operators are listed in the following table.</span></span>

| <span data-ttu-id="0f43b-170">Operador Lógico</span><span class="sxs-lookup"><span data-stu-id="0f43b-170">Logical Operator</span></span> |                 <span data-ttu-id="0f43b-171">Significado</span><span class="sxs-lookup"><span data-stu-id="0f43b-171">Meaning</span></span>                  |  <span data-ttu-id="0f43b-172">Exemplo (returna true)</span><span class="sxs-lookup"><span data-stu-id="0f43b-172">Example (returns true)</span></span>  |
| ---------------- | ---------------------------------------- | ------------------------ |
| <span data-ttu-id="0f43b-173">-and</span><span class="sxs-lookup"><span data-stu-id="0f43b-173">-and</span></span>             | <span data-ttu-id="0f43b-174">E lógico; verdadeiro se ambos os lados forem verdadeiros</span><span class="sxs-lookup"><span data-stu-id="0f43b-174">Logical and; true if both sides are true</span></span> | <span data-ttu-id="0f43b-175">(1 -eq 1) -and (2 -eq 2)</span><span class="sxs-lookup"><span data-stu-id="0f43b-175">(1 -eq 1) -and (2 -eq 2)</span></span> |
| <span data-ttu-id="0f43b-176">-or</span><span class="sxs-lookup"><span data-stu-id="0f43b-176">-or</span></span>              | <span data-ttu-id="0f43b-177">Ou lógico; verdadeiro se um dos lados for verdadeiro</span><span class="sxs-lookup"><span data-stu-id="0f43b-177">Logical or; true if either side is true</span></span>  | <span data-ttu-id="0f43b-178">(1 -eq 1) -or (1 -eq 2)</span><span class="sxs-lookup"><span data-stu-id="0f43b-178">(1 -eq 1) -or (1 -eq 2)</span></span>  |
| <span data-ttu-id="0f43b-179">-not</span><span class="sxs-lookup"><span data-stu-id="0f43b-179">-not</span></span>             | <span data-ttu-id="0f43b-180">Não lógico; inverte o verdadeiro e o falso</span><span class="sxs-lookup"><span data-stu-id="0f43b-180">Logical not; reverses true and false</span></span>     | <span data-ttu-id="0f43b-181">-not (1 -eq 2)</span><span class="sxs-lookup"><span data-stu-id="0f43b-181">-not (1 -eq 2)</span></span>           |
| \!               | <span data-ttu-id="0f43b-182">Não lógico; inverte o verdadeiro e o falso</span><span class="sxs-lookup"><span data-stu-id="0f43b-182">Logical not; reverses true and false</span></span>     | <span data-ttu-id="0f43b-183">\!(1 -eq 2)</span><span class="sxs-lookup"><span data-stu-id="0f43b-183">\!(1 -eq 2)</span></span>              |
