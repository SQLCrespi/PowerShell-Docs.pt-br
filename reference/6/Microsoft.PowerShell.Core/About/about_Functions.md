---
description: Descreve como criar e usar funções no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 2/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions
ms.openlocfilehash: 944cb3fc77406cfbf288655d2740bad6ddcceee4
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94387627"
---
# <a name="about-functions"></a><span data-ttu-id="cf36e-104">Sobre o Functions</span><span class="sxs-lookup"><span data-stu-id="cf36e-104">About Functions</span></span>

## <a name="short-description"></a><span data-ttu-id="cf36e-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="cf36e-105">Short description</span></span>

<span data-ttu-id="cf36e-106">Descreve como criar e usar funções no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf36e-106">Describes how to create and use functions in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="cf36e-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="cf36e-107">Long description</span></span>

<span data-ttu-id="cf36e-108">Uma função é uma lista de instruções do PowerShell que tem um nome que você atribui.</span><span class="sxs-lookup"><span data-stu-id="cf36e-108">A function is a list of PowerShell statements that has a name that you assign.</span></span> <span data-ttu-id="cf36e-109">Ao executar uma função, você digita o nome da função.</span><span class="sxs-lookup"><span data-stu-id="cf36e-109">When you run a function, you type the function name.</span></span> <span data-ttu-id="cf36e-110">As instruções na lista são executadas como se você as tivesse digitado no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="cf36e-110">The statements in the list run as if you had typed them at the command prompt.</span></span>

<span data-ttu-id="cf36e-111">As funções podem ser tão simples quanto:</span><span class="sxs-lookup"><span data-stu-id="cf36e-111">Functions can be as simple as:</span></span>

```powershell
function Get-PowerShellProcess { Get-Process PowerShell }
```

<span data-ttu-id="cf36e-112">Uma função também pode ser tão complexa quanto um cmdlet ou um programa de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="cf36e-112">A function can also be as complex as a cmdlet or an application program.</span></span>

<span data-ttu-id="cf36e-113">Como os cmdlets, as funções podem ter parâmetros.</span><span class="sxs-lookup"><span data-stu-id="cf36e-113">Like cmdlets, functions can have parameters.</span></span> <span data-ttu-id="cf36e-114">Os parâmetros podem ser nomeados, posicionais, switches ou parâmetros dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="cf36e-114">The parameters can be named, positional, switch, or dynamic parameters.</span></span> <span data-ttu-id="cf36e-115">Os parâmetros de função podem ser lidos na linha de comando ou no pipeline.</span><span class="sxs-lookup"><span data-stu-id="cf36e-115">Function parameters can be read from the command line or from the pipeline.</span></span>

<span data-ttu-id="cf36e-116">As funções podem retornar valores que podem ser exibidos, atribuídos a variáveis ou passados para outras funções ou cmdlets.</span><span class="sxs-lookup"><span data-stu-id="cf36e-116">Functions can return values that can be displayed, assigned to variables, or passed to other functions or cmdlets.</span></span> <span data-ttu-id="cf36e-117">Você também pode especificar um valor de retorno usando a `return` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="cf36e-117">You can also specify a return value using the `return` keyword.</span></span> <span data-ttu-id="cf36e-118">A `return` palavra-chave não afeta ou elimina outra saída retornada de sua função.</span><span class="sxs-lookup"><span data-stu-id="cf36e-118">The `return` keyword does not affect or suppress other output returned from your function.</span></span> <span data-ttu-id="cf36e-119">No entanto, a `return` palavra-chave sai da função nessa linha.</span><span class="sxs-lookup"><span data-stu-id="cf36e-119">However, the `return` keyword exits the function at that line.</span></span> <span data-ttu-id="cf36e-120">Para obter mais informações, consulte [about_Return](about_Return.md).</span><span class="sxs-lookup"><span data-stu-id="cf36e-120">For more information, see [about_Return](about_Return.md).</span></span>

<span data-ttu-id="cf36e-121">A lista de instruções da função pode conter tipos diferentes de listas de instruções com as palavras-chave `Begin` , `Process` e `End` .</span><span class="sxs-lookup"><span data-stu-id="cf36e-121">The function's statement list can contain different types of statement lists with the keywords `Begin`, `Process`, and `End`.</span></span> <span data-ttu-id="cf36e-122">Essas instruções listam a entrada do pipeline de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="cf36e-122">These statement lists handle input from the pipeline differently.</span></span>

<span data-ttu-id="cf36e-123">Um filtro é um tipo especial de função que usa a `Filter` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="cf36e-123">A filter is a special kind of function that uses the `Filter` keyword.</span></span>

<span data-ttu-id="cf36e-124">As funções também podem atuar como cmdlets.</span><span class="sxs-lookup"><span data-stu-id="cf36e-124">Functions can also act like cmdlets.</span></span> <span data-ttu-id="cf36e-125">Você pode criar uma função que funciona exatamente como um cmdlet sem usar a `C#` programação.</span><span class="sxs-lookup"><span data-stu-id="cf36e-125">You can create a function that works just like a cmdlet without using `C#` programming.</span></span> <span data-ttu-id="cf36e-126">Para obter mais informações, consulte [about_Functions_Advanced](about_Functions_Advanced.md).</span><span class="sxs-lookup"><span data-stu-id="cf36e-126">For more information, see [about_Functions_Advanced](about_Functions_Advanced.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="cf36e-127">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cf36e-127">Syntax</span></span>

<span data-ttu-id="cf36e-128">Veja a seguir a sintaxe de uma função:</span><span class="sxs-lookup"><span data-stu-id="cf36e-128">The following is the syntax for a function:</span></span>

```
function [<scope:>]<name> [([type]$parameter1[,[type]$parameter2])]
{
  param([type]$parameter1 [,[type]$parameter2])
  dynamicparam {<statement list>}
  begin {<statement list>}
  process {<statement list>}
  end {<statement list>}
}
```

<span data-ttu-id="cf36e-129">Uma função inclui os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="cf36e-129">A function includes the following items:</span></span>

- <span data-ttu-id="cf36e-130">Uma `Function` palavra-chave</span><span class="sxs-lookup"><span data-stu-id="cf36e-130">A `Function` keyword</span></span>
- <span data-ttu-id="cf36e-131">Um escopo (opcional)</span><span class="sxs-lookup"><span data-stu-id="cf36e-131">A scope (optional)</span></span>
- <span data-ttu-id="cf36e-132">Um nome que você seleciona</span><span class="sxs-lookup"><span data-stu-id="cf36e-132">A name that you select</span></span>
- <span data-ttu-id="cf36e-133">Qualquer número de parâmetros nomeados (opcional)</span><span class="sxs-lookup"><span data-stu-id="cf36e-133">Any number of named parameters (optional)</span></span>
- <span data-ttu-id="cf36e-134">Um ou mais comandos do PowerShell entre chaves `{}`</span><span class="sxs-lookup"><span data-stu-id="cf36e-134">One or more PowerShell commands enclosed in braces `{}`</span></span>

<span data-ttu-id="cf36e-135">Para obter mais informações sobre a `Dynamicparam` palavra-chave e os parâmetros dinâmicos em funções, consulte [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="cf36e-135">For more information about the `Dynamicparam` keyword and dynamic parameters in functions, see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

## <a name="simple-functions"></a><span data-ttu-id="cf36e-136">Funções simples</span><span class="sxs-lookup"><span data-stu-id="cf36e-136">Simple Functions</span></span>

<span data-ttu-id="cf36e-137">As funções não precisam ser complicadas para serem úteis.</span><span class="sxs-lookup"><span data-stu-id="cf36e-137">Functions do not have to be complicated to be useful.</span></span> <span data-ttu-id="cf36e-138">As funções mais simples têm o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="cf36e-138">The simplest functions have the following format:</span></span>

```
function <function-name> {statements}
```

<span data-ttu-id="cf36e-139">Por exemplo, a função a seguir inicia o PowerShell com a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="cf36e-139">For example, the following function starts PowerShell with the Run as Administrator option.</span></span>

```powershell
function Start-PSAdmin {Start-Process PowerShell -Verb RunAs}
```

<span data-ttu-id="cf36e-140">Para usar a função, digite: `Start-PSAdmin`</span><span class="sxs-lookup"><span data-stu-id="cf36e-140">To use the function, type: `Start-PSAdmin`</span></span>

<span data-ttu-id="cf36e-141">Para adicionar instruções à função, digite cada instrução em uma linha separada ou use um ponto-e-vírgula `;` para separar as instruções.</span><span class="sxs-lookup"><span data-stu-id="cf36e-141">To add statements to the function, type each statement on a separate line, or use a semi-colon `;` to separate the statements.</span></span>

<span data-ttu-id="cf36e-142">Por exemplo, a função a seguir localiza todos os `.jpg` arquivos nos diretórios do usuário atual que foram alterados após a data de início.</span><span class="sxs-lookup"><span data-stu-id="cf36e-142">For example, the following function finds all `.jpg` files in the current user's directories that were changed after the start date.</span></span>

```powershell
function Get-NewPix
{
  $start = Get-Date -Month 1 -Day 1 -Year 2010
  $allpix = Get-ChildItem -Path $env:UserProfile\*.jpg -Recurse
  $allpix | Where-Object {$_.LastWriteTime -gt $Start}
}
```

<span data-ttu-id="cf36e-143">Você pode criar uma caixa de ferramentas de funções pequenas úteis.</span><span class="sxs-lookup"><span data-stu-id="cf36e-143">You can create a toolbox of useful small functions.</span></span> <span data-ttu-id="cf36e-144">Adicione essas funções ao seu perfil do PowerShell, conforme descrito em [about_Profiles](about_Profiles.md) e posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="cf36e-144">Add these functions to your PowerShell profile, as described in [about_Profiles](about_Profiles.md) and later in this topic.</span></span>

## <a name="function-names"></a><span data-ttu-id="cf36e-145">Nomes de função</span><span class="sxs-lookup"><span data-stu-id="cf36e-145">Function Names</span></span>

<span data-ttu-id="cf36e-146">Você pode atribuir qualquer nome a uma função, mas as funções que você compartilha com outras pessoas devem seguir as regras de nomenclatura que foram estabelecidas para todos os comandos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf36e-146">You can assign any name to a function, but functions that you share with others should follow the naming rules that have been established for all PowerShell commands.</span></span>

<span data-ttu-id="cf36e-147">Os nomes de funções devem consistir em um par verbo-substantivo no qual o verbo identifica a ação que a função executa e o substantivo identifica o item no qual o cmdlet executa sua ação.</span><span class="sxs-lookup"><span data-stu-id="cf36e-147">Functions names should consist of a verb-noun pair in which the verb identifies the action that the function performs and the noun identifies the item on which the cmdlet performs its action.</span></span>

<span data-ttu-id="cf36e-148">As funções devem usar os verbos padrão que foram aprovados para todos os comandos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf36e-148">Functions should use the standard verbs that have been approved for all PowerShell commands.</span></span> <span data-ttu-id="cf36e-149">Esses verbos nos ajudam a manter nossos nomes de comando simples, consistentes e fáceis para os usuários entenderem.</span><span class="sxs-lookup"><span data-stu-id="cf36e-149">These verbs help us to keep our command names simple, consistent, and easy for users to understand.</span></span>

<span data-ttu-id="cf36e-150">Para obter mais informações sobre os verbos padrão do PowerShell, consulte [verbos aprovados](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands) no Microsoft docs.</span><span class="sxs-lookup"><span data-stu-id="cf36e-150">For more information about the standard PowerShell verbs, see [Approved Verbs](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands) in the Microsoft Docs.</span></span>

## <a name="functions-with-parameters"></a><span data-ttu-id="cf36e-151">Funções com parâmetros</span><span class="sxs-lookup"><span data-stu-id="cf36e-151">Functions with Parameters</span></span>

<span data-ttu-id="cf36e-152">Você pode usar parâmetros com funções, incluindo parâmetros nomeados, parâmetros posicionais, parâmetros de switch e parâmetros dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="cf36e-152">You can use parameters with functions, including named parameters, positional parameters, switch parameters, and dynamic parameters.</span></span> <span data-ttu-id="cf36e-153">Para obter mais informações sobre parâmetros dinâmicos em funções, consulte [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="cf36e-153">For more information about dynamic parameters in functions, see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

### <a name="named-parameters"></a><span data-ttu-id="cf36e-154">Parâmetros nomeados</span><span class="sxs-lookup"><span data-stu-id="cf36e-154">Named Parameters</span></span>

<span data-ttu-id="cf36e-155">Você pode definir qualquer número de parâmetros nomeados.</span><span class="sxs-lookup"><span data-stu-id="cf36e-155">You can define any number of named parameters.</span></span> <span data-ttu-id="cf36e-156">Você pode incluir um valor padrão para parâmetros nomeados, conforme descrito posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="cf36e-156">You can include a default value for named parameters, as described later in this topic.</span></span>

<span data-ttu-id="cf36e-157">Você pode definir parâmetros dentro das chaves usando a `Param` palavra-chave, conforme mostrado na seguinte sintaxe de exemplo:</span><span class="sxs-lookup"><span data-stu-id="cf36e-157">You can define parameters inside the braces using the `Param` keyword, as shown in the following sample syntax:</span></span>

```
function <name> {
  param ([type]$parameter1[,[type]$parameter2])
  <statement list>
}
```

<span data-ttu-id="cf36e-158">Você também pode definir parâmetros fora das chaves sem a `Param` palavra-chave, conforme mostrado na seguinte sintaxe de exemplo:</span><span class="sxs-lookup"><span data-stu-id="cf36e-158">You can also define parameters outside the braces without the `Param` keyword, as shown in the following sample syntax:</span></span>

```powershell
function <name> [([type]$parameter1[,[type]$parameter2])] {
  <statement list>
}
```

<span data-ttu-id="cf36e-159">Veja abaixo um exemplo dessa sintaxe alternativa.</span><span class="sxs-lookup"><span data-stu-id="cf36e-159">Below is an example of this alternative syntax.</span></span>

```powershell
Function Add-Numbers($one, $two) {
    $one + $two
}
```

<span data-ttu-id="cf36e-160">Embora o primeiro método seja preferencial, não há nenhuma diferença entre esses dois métodos.</span><span class="sxs-lookup"><span data-stu-id="cf36e-160">While the first method is preferred, there is no difference between these two methods.</span></span>

<span data-ttu-id="cf36e-161">Quando você executa a função, o valor que você fornece para um parâmetro é atribuído a uma variável que contém o nome do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="cf36e-161">When you run the function, the value you supply for a parameter is assigned to a variable that contains the parameter name.</span></span> <span data-ttu-id="cf36e-162">O valor dessa variável pode ser usado na função.</span><span class="sxs-lookup"><span data-stu-id="cf36e-162">The value of that variable can be used in the function.</span></span>

<span data-ttu-id="cf36e-163">O exemplo a seguir é uma função chamada `Get-SmallFiles` .</span><span class="sxs-lookup"><span data-stu-id="cf36e-163">The following example is a function called `Get-SmallFiles`.</span></span> <span data-ttu-id="cf36e-164">Essa função tem um `$Size` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="cf36e-164">This function has a `$Size` parameter.</span></span> <span data-ttu-id="cf36e-165">A função exibe todos os arquivos que são menores do que o valor do `$Size` parâmetro e exclui os diretórios:</span><span class="sxs-lookup"><span data-stu-id="cf36e-165">The function displays all the files that are smaller than the value of the `$Size` parameter, and it excludes directories:</span></span>

```powershell
function Get-SmallFiles {
  Param($Size)
  Get-ChildItem $HOME | Where-Object {
    $_.Length -lt $Size -and !$_.PSIsContainer
  }
}
```

<span data-ttu-id="cf36e-166">Na função, você pode usar a `$Size` variável, que é o nome definido para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="cf36e-166">In the function, you can use the `$Size` variable, which is the name defined for the parameter.</span></span>

<span data-ttu-id="cf36e-167">Para usar essa função, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="cf36e-167">To use this function, type the following command:</span></span>

```powershell
Get-SmallFiles -Size 50
```

<span data-ttu-id="cf36e-168">Você também pode inserir um valor para um parâmetro nomeado sem o nome do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="cf36e-168">You can also enter a value for a named parameter without the parameter name.</span></span>
<span data-ttu-id="cf36e-169">Por exemplo, o comando a seguir fornece o mesmo resultado que um comando que nomeia o parâmetro de **tamanho** :</span><span class="sxs-lookup"><span data-stu-id="cf36e-169">For example, the following command gives the same result as a command that names the **Size** parameter:</span></span>

```powershell
Get-SmallFiles 50
```

<span data-ttu-id="cf36e-170">Para definir um valor padrão para um parâmetro, digite um sinal de igual e o valor após o nome do parâmetro, conforme mostrado na seguinte variação do `Get-SmallFiles` exemplo:</span><span class="sxs-lookup"><span data-stu-id="cf36e-170">To define a default value for a parameter, type an equal sign and the value after the parameter name, as shown in the following variation of the `Get-SmallFiles` example:</span></span>

```powershell
function Get-SmallFiles ($Size = 100) {
  Get-ChildItem $HOME | Where-Object {
    $_.Length -lt $Size -and !$_.PSIsContainer
  }
}
```

<span data-ttu-id="cf36e-171">Se você digitar `Get-SmallFiles` sem um valor, a função atribuirá 100 a `$size` .</span><span class="sxs-lookup"><span data-stu-id="cf36e-171">If you type `Get-SmallFiles` without a value, the function assigns 100 to `$size`.</span></span> <span data-ttu-id="cf36e-172">Se você fornecer um valor, a função usará esse valor.</span><span class="sxs-lookup"><span data-stu-id="cf36e-172">If you provide a value, the function uses that value.</span></span>

<span data-ttu-id="cf36e-173">Opcionalmente, você pode fornecer uma breve cadeia de caracteres de ajuda que descreve o valor padrão do parâmetro, adicionando o atributo **PSDefaultValue** à descrição do parâmetro e especificando a propriedade da **ajuda** de **PSDefaultValue**.</span><span class="sxs-lookup"><span data-stu-id="cf36e-173">Optionally, you can provide a brief help string that describes the default value of your parameter, by adding the **PSDefaultValue** attribute to the description of your parameter, and specifying the **Help** property of **PSDefaultValue**.</span></span> <span data-ttu-id="cf36e-174">Para fornecer uma cadeia de caracteres de ajuda que descreva o valor padrão (100) do parâmetro de **tamanho** na `Get-SmallFiles` função, adicione o atributo **PSDefaultValue** , conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="cf36e-174">To provide a help string that describes the default value (100) of the **Size** parameter in the `Get-SmallFiles` function, add the **PSDefaultValue** attribute as shown in the following example.</span></span>

```powershell
function Get-SmallFiles {
  param (
      [PSDefaultValue(Help = '100')]
      $Size = 100
  )
}
```

<span data-ttu-id="cf36e-175">Para obter mais informações sobre a classe de atributo **PSDefaultValue** , consulte [membros de atributo PSDefaultValue](/dotnet/api/system.management.automation.psdefaultvalueattribute).</span><span class="sxs-lookup"><span data-stu-id="cf36e-175">For more information about the **PSDefaultValue** attribute class, see [PSDefaultValue Attribute Members](/dotnet/api/system.management.automation.psdefaultvalueattribute).</span></span>

### <a name="positional-parameters"></a><span data-ttu-id="cf36e-176">Parâmetros posicionais</span><span class="sxs-lookup"><span data-stu-id="cf36e-176">Positional Parameters</span></span>

<span data-ttu-id="cf36e-177">Um parâmetro posicional é um parâmetro sem um nome de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="cf36e-177">A positional parameter is a parameter without a parameter name.</span></span> <span data-ttu-id="cf36e-178">O PowerShell usa a ordem de valor do parâmetro para associar cada valor de parâmetro a um parâmetro na função.</span><span class="sxs-lookup"><span data-stu-id="cf36e-178">PowerShell uses the parameter value order to associate each parameter value with a parameter in the function.</span></span>

<span data-ttu-id="cf36e-179">Ao usar parâmetros posicionais, digite um ou mais valores após o nome da função.</span><span class="sxs-lookup"><span data-stu-id="cf36e-179">When you use positional parameters, type one or more values after the function name.</span></span> <span data-ttu-id="cf36e-180">Os valores de parâmetros posicionais são atribuídos à `$args` variável de matriz.</span><span class="sxs-lookup"><span data-stu-id="cf36e-180">Positional parameter values are assigned to the `$args` array variable.</span></span>
<span data-ttu-id="cf36e-181">O valor que segue o nome da função é atribuído à primeira posição na `$args` matriz, `$args[0]` .</span><span class="sxs-lookup"><span data-stu-id="cf36e-181">The value that follows the function name is assigned to the first position in the `$args` array, `$args[0]`.</span></span>

<span data-ttu-id="cf36e-182">A função a seguir `Get-Extension` adiciona a `.txt` extensão de nome de arquivo a um nome de arquivo que você fornece:</span><span class="sxs-lookup"><span data-stu-id="cf36e-182">The following `Get-Extension` function adds the `.txt` file name extension to a file name that you supply:</span></span>

```powershell
function Get-Extension {
  $name = $args[0] + ".txt"
  $name
}
```

```powershell
Get-Extension myTextFile
```

```Output
myTextFile.txt
```

### <a name="switch-parameters"></a><span data-ttu-id="cf36e-183">Parâmetros de comutação</span><span class="sxs-lookup"><span data-stu-id="cf36e-183">Switch Parameters</span></span>

<span data-ttu-id="cf36e-184">Uma opção é um parâmetro que não requer um valor.</span><span class="sxs-lookup"><span data-stu-id="cf36e-184">A switch is a parameter that does not require a value.</span></span> <span data-ttu-id="cf36e-185">Em vez disso, digite o nome da função seguido pelo nome do parâmetro de opção.</span><span class="sxs-lookup"><span data-stu-id="cf36e-185">Instead, you type the function name followed by the name of the switch parameter.</span></span>

<span data-ttu-id="cf36e-186">Para definir um parâmetro de opção, especifique o tipo `[switch]` antes do nome do parâmetro, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="cf36e-186">To define a switch parameter, specify the type `[switch]` before the parameter name, as shown in the following example:</span></span>

```powershell
function Switch-Item {
  param ([switch]$on)
  if ($on) { "Switch on" }
  else { "Switch off" }
}
```

<span data-ttu-id="cf36e-187">Quando você digita o `On` parâmetro switch após o nome da função, a função exibe "switch on".</span><span class="sxs-lookup"><span data-stu-id="cf36e-187">When you type the `On` switch parameter after the function name, the function displays "Switch on".</span></span> <span data-ttu-id="cf36e-188">Sem o parâmetro switch, ele exibe "switch off".</span><span class="sxs-lookup"><span data-stu-id="cf36e-188">Without the switch parameter, it displays "Switch off".</span></span>

```powershell
Switch-Item -on
```

```Output
Switch on
```

```powershell
Switch-Item
```

```Output
Switch off
```

<span data-ttu-id="cf36e-189">Você também pode atribuir um valor **booliano** a uma opção ao executar a função, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="cf36e-189">You can also assign a **Boolean** value to a switch when you run the function, as shown in the following example:</span></span>

```powershell
Switch-Item -on:$true
```

```Output
Switch on
```

```powershell
Switch-Item -on:$false
```

```Output
Switch off
```

## <a name="using-splatting-to-represent-command-parameters"></a><span data-ttu-id="cf36e-190">Usando nivelamento para representar parâmetros de comando</span><span class="sxs-lookup"><span data-stu-id="cf36e-190">Using Splatting to Represent Command Parameters</span></span>

<span data-ttu-id="cf36e-191">Você pode usar nivelamento para representar os parâmetros de um comando.</span><span class="sxs-lookup"><span data-stu-id="cf36e-191">You can use splatting to represent the parameters of a command.</span></span> <span data-ttu-id="cf36e-192">Esse recurso é introduzido no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="cf36e-192">This feature is introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="cf36e-193">Use essa técnica em funções que chamam comandos na sessão.</span><span class="sxs-lookup"><span data-stu-id="cf36e-193">Use this technique in functions that call commands in the session.</span></span> <span data-ttu-id="cf36e-194">Você não precisa declarar ou enumerar os parâmetros de comando ou alterar a função quando os parâmetros de comando são alterados.</span><span class="sxs-lookup"><span data-stu-id="cf36e-194">You do not need to declare or enumerate the command parameters, or change the function when command parameters change.</span></span>

<span data-ttu-id="cf36e-195">A função de exemplo a seguir chama o `Get-Command` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="cf36e-195">The following sample function calls the `Get-Command` cmdlet.</span></span> <span data-ttu-id="cf36e-196">O comando usa `@Args` para representar os parâmetros de `Get-Command` .</span><span class="sxs-lookup"><span data-stu-id="cf36e-196">The command uses `@Args` to represent the parameters of `Get-Command`.</span></span>

```powershell
function Get-MyCommand { Get-Command @Args }
```

<span data-ttu-id="cf36e-197">Você pode usar todos os parâmetros de `Get-Command` quando chamar a `Get-MyCommand` função.</span><span class="sxs-lookup"><span data-stu-id="cf36e-197">You can use all of the parameters of `Get-Command` when you call the `Get-MyCommand` function.</span></span> <span data-ttu-id="cf36e-198">Os parâmetros e os valores de parâmetro são passados para o comando usando `@Args` .</span><span class="sxs-lookup"><span data-stu-id="cf36e-198">The parameters and parameter values are passed to the command using `@Args`.</span></span>

```powershell
Get-MyCommand -Name Get-ChildItem
```

```Output
CommandType     Name                ModuleName
-----------     ----                ----------
Cmdlet          Get-ChildItem       Microsoft.PowerShell.Management
```

<span data-ttu-id="cf36e-199">O `@Args` recurso usa o `$Args` parâmetro Automatic, que representa os valores e parâmetros de cmdlet não declarados dos argumentos restantes.</span><span class="sxs-lookup"><span data-stu-id="cf36e-199">The `@Args` feature uses the `$Args` automatic parameter, which represents undeclared cmdlet parameters and values from remaining arguments.</span></span>

<span data-ttu-id="cf36e-200">Para obter mais informações sobre nivelamento, consulte [about_Splatting](about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="cf36e-200">For more information about splatting, see [about_Splatting](about_Splatting.md).</span></span>

## <a name="piping-objects-to-functions"></a><span data-ttu-id="cf36e-201">Direcionando objetos para funções</span><span class="sxs-lookup"><span data-stu-id="cf36e-201">Piping Objects to Functions</span></span>

<span data-ttu-id="cf36e-202">Qualquer função pode receber entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="cf36e-202">Any function can take input from the pipeline.</span></span> <span data-ttu-id="cf36e-203">Você pode controlar como uma função processa a entrada do pipeline usando `Begin` as `Process` `End` palavras-chave, e.</span><span class="sxs-lookup"><span data-stu-id="cf36e-203">You can control how a function processes input from the pipeline using `Begin`, `Process`, and `End` keywords.</span></span> <span data-ttu-id="cf36e-204">A sintaxe de exemplo a seguir mostra as três palavras-chave:</span><span class="sxs-lookup"><span data-stu-id="cf36e-204">The following sample syntax shows the three keywords:</span></span>

```
function <name> {
  begin {<statement list>}
  process {<statement list>}
  end {<statement list>}
}
```

<span data-ttu-id="cf36e-205">A `Begin` lista de instruções é executada apenas uma vez, no início da função.</span><span class="sxs-lookup"><span data-stu-id="cf36e-205">The `Begin` statement list runs one time only, at the beginning of the function.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf36e-206">Se sua função define um `Begin` `Process` bloco, ou `End` , todo o seu código deve residir dentro desses blocos.</span><span class="sxs-lookup"><span data-stu-id="cf36e-206">If your function defines a `Begin`, `Process` or `End` block, all of your code must reside inside those blocks.</span></span> <span data-ttu-id="cf36e-207">Nenhum código será reconhecido fora dos blocos se *qualquer* um dos blocos for definido.</span><span class="sxs-lookup"><span data-stu-id="cf36e-207">No code will be recognized outside the blocks if *any* of the blocks are defined.</span></span>

<span data-ttu-id="cf36e-208">A `Process` lista de instruções é executada uma vez para cada objeto no pipeline.</span><span class="sxs-lookup"><span data-stu-id="cf36e-208">The `Process` statement list runs one time for each object in the pipeline.</span></span>
<span data-ttu-id="cf36e-209">Enquanto o `Process` bloco está em execução, cada objeto de pipeline é atribuído à `$_` variável automática, um objeto de pipeline por vez.</span><span class="sxs-lookup"><span data-stu-id="cf36e-209">While the `Process` block is running, each pipeline object is assigned to the `$_` automatic variable, one pipeline object at a time.</span></span>

<span data-ttu-id="cf36e-210">Depois que a função recebe todos os objetos no pipeline, a `End` lista de instruções é executada uma vez.</span><span class="sxs-lookup"><span data-stu-id="cf36e-210">After the function receives all the objects in the pipeline, the `End` statement list runs one time.</span></span> <span data-ttu-id="cf36e-211">Se nenhuma `Begin` `Process` `End` palavra-chave, ou for usada, todas as instruções serão tratadas como uma `End` lista de instruções.</span><span class="sxs-lookup"><span data-stu-id="cf36e-211">If no `Begin`, `Process`, or `End` keywords are used, all the statements are treated like an `End` statement list.</span></span>

<span data-ttu-id="cf36e-212">A função a seguir usa a `Process` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="cf36e-212">The following function uses the `Process` keyword.</span></span> <span data-ttu-id="cf36e-213">A função exibe exemplos do pipeline:</span><span class="sxs-lookup"><span data-stu-id="cf36e-213">The function displays examples from the pipeline:</span></span>

```powershell
function Get-Pipeline
{
  process {"The value is: $_"}
}
```

<span data-ttu-id="cf36e-214">Para demonstrar essa função, insira uma lista de números separados por vírgulas, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="cf36e-214">To demonstrate this function, enter an list of numbers separated by commas, as shown in the following example:</span></span>

```powershell
1,2,4 | Get-Pipeline
```

```Output
The value is: 1
The value is: 2
The value is: 4
```

<span data-ttu-id="cf36e-215">Quando você usa uma função em um pipeline, os objetos canalizados para a função são atribuídos à `$input` variável automática.</span><span class="sxs-lookup"><span data-stu-id="cf36e-215">When you use a function in a pipeline, the objects piped to the function are assigned to the `$input` automatic variable.</span></span> <span data-ttu-id="cf36e-216">A função executa instruções com a `Begin` palavra-chave antes de qualquer objeto ser proveniente do pipeline.</span><span class="sxs-lookup"><span data-stu-id="cf36e-216">The function runs statements with the `Begin` keyword before any objects come from the pipeline.</span></span> <span data-ttu-id="cf36e-217">A função executa instruções com a `End` palavra-chave após a recebimento de todos os objetos do pipeline.</span><span class="sxs-lookup"><span data-stu-id="cf36e-217">The function runs statements with the `End` keyword after all the objects have been received from the pipeline.</span></span>

<span data-ttu-id="cf36e-218">O exemplo a seguir mostra a `$input` variável automática com `Begin` e `End` palavras-chave.</span><span class="sxs-lookup"><span data-stu-id="cf36e-218">The following example shows the `$input` automatic variable with `Begin` and `End` keywords.</span></span>

```powershell
function Get-PipelineBeginEnd
{
  begin {"Begin: The input is $input"}
  end {"End:   The input is $input" }
}
```

<span data-ttu-id="cf36e-219">Se essa função for executada usando o pipeline, ela exibirá os seguintes resultados:</span><span class="sxs-lookup"><span data-stu-id="cf36e-219">If this function is run by using the pipeline, it displays the following results:</span></span>

```powershell
1,2,4 | Get-PipelineBeginEnd
```

```Output
Begin: The input is
End:   The input is 1 2 4
```

<span data-ttu-id="cf36e-220">Quando a `Begin` instrução é executada, a função não tem a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="cf36e-220">When the `Begin` statement runs, the function does not have the input from the pipeline.</span></span> <span data-ttu-id="cf36e-221">A `End` instrução é executada Depois que a função tem os valores.</span><span class="sxs-lookup"><span data-stu-id="cf36e-221">The `End` statement runs after the function has the values.</span></span>

<span data-ttu-id="cf36e-222">Se a função tiver uma `Process` palavra-chave, cada objeto no `$input` será removido de `$input` e atribuído a `$_` .</span><span class="sxs-lookup"><span data-stu-id="cf36e-222">If the function has a `Process` keyword, each object in `$input` is removed from `$input` and assigned to `$_`.</span></span> <span data-ttu-id="cf36e-223">O exemplo a seguir tem uma `Process` lista de instruções:</span><span class="sxs-lookup"><span data-stu-id="cf36e-223">The following example has a `Process` statement list:</span></span>

```powershell
function Get-PipelineInput
{
  process {"Processing:  $_ " }
  end {"End:   The input is: $input" }
}
```

<span data-ttu-id="cf36e-224">Neste exemplo, cada objeto que é canalizado para a função é enviado para a `Process` lista de instruções.</span><span class="sxs-lookup"><span data-stu-id="cf36e-224">In this example, each object that is piped to the function is sent to the `Process` statement list.</span></span> <span data-ttu-id="cf36e-225">As `Process` instruções são executadas em cada objeto, um objeto por vez.</span><span class="sxs-lookup"><span data-stu-id="cf36e-225">The `Process` statements run on each object, one object at a time.</span></span> <span data-ttu-id="cf36e-226">A `$input` variável automática estará vazia quando a função atingir a `End` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="cf36e-226">The `$input` automatic variable is empty when the function reaches the `End` keyword.</span></span>

```powershell
1,2,4 | Get-PipelineInput
```

```Output
Processing:  1
Processing:  2
Processing:  4
End:   The input is:
```

<span data-ttu-id="cf36e-227">Para obter mais informações, consulte [usando enumeradores](about_Automatic_Variables.md#using-enumerators)</span><span class="sxs-lookup"><span data-stu-id="cf36e-227">For more information, see [Using Enumerators](about_Automatic_Variables.md#using-enumerators)</span></span>

## <a name="filters"></a><span data-ttu-id="cf36e-228">Filtros</span><span class="sxs-lookup"><span data-stu-id="cf36e-228">Filters</span></span>

<span data-ttu-id="cf36e-229">Um filtro é um tipo de função que é executado em cada objeto no pipeline.</span><span class="sxs-lookup"><span data-stu-id="cf36e-229">A filter is a type of function that runs on each object in the pipeline.</span></span> <span data-ttu-id="cf36e-230">Um filtro é semelhante a uma função com todas as suas instruções em um `Process` bloco.</span><span class="sxs-lookup"><span data-stu-id="cf36e-230">A filter resembles a function with all its statements in a `Process` block.</span></span>

<span data-ttu-id="cf36e-231">A sintaxe de um filtro é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="cf36e-231">The syntax of a filter is as follows:</span></span>

```
filter [<scope:>]<name> {<statement list>}
```

<span data-ttu-id="cf36e-232">O filtro a seguir usa entradas de log do pipeline e, em seguida, exibe a entrada inteira ou apenas a parte da mensagem da entrada:</span><span class="sxs-lookup"><span data-stu-id="cf36e-232">The following filter takes log entries from the pipeline and then displays either the whole entry or only the message portion of the entry:</span></span>

```powershell
filter Get-ErrorLog ([switch]$message)
{
  if ($message) { Out-Host -InputObject $_.Message }
  else { $_ }
}
```

## <a name="function-scope"></a><span data-ttu-id="cf36e-233">Escopo da função</span><span class="sxs-lookup"><span data-stu-id="cf36e-233">Function Scope</span></span>

<span data-ttu-id="cf36e-234">Existe uma função no escopo no qual ela foi criada.</span><span class="sxs-lookup"><span data-stu-id="cf36e-234">A function exists in the scope in which it was created.</span></span>

<span data-ttu-id="cf36e-235">Se uma função fizer parte de um script, a função estará disponível para instruções dentro desse script.</span><span class="sxs-lookup"><span data-stu-id="cf36e-235">If a function is part of a script, the function is available to statements within that script.</span></span> <span data-ttu-id="cf36e-236">Por padrão, uma função em um script não está disponível no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="cf36e-236">By default, a function in a script is not available at the command prompt.</span></span>

<span data-ttu-id="cf36e-237">Você pode especificar o escopo de uma função.</span><span class="sxs-lookup"><span data-stu-id="cf36e-237">You can specify the scope of a function.</span></span> <span data-ttu-id="cf36e-238">Por exemplo, a função é adicionada ao escopo global no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="cf36e-238">For example, the function is added to the global scope in the following example:</span></span>

```powershell
function global:Get-DependentSvs {
  Get-Service | Where-Object {$_.DependentServices}
}
```

<span data-ttu-id="cf36e-239">Quando uma função está no escopo global, você pode usar a função em scripts, em funções e na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="cf36e-239">When a function is in the global scope, you can use the function in scripts, in functions, and at the command line.</span></span>

<span data-ttu-id="cf36e-240">Normalmente, o Functions cria um escopo.</span><span class="sxs-lookup"><span data-stu-id="cf36e-240">Functions normally create a scope.</span></span> <span data-ttu-id="cf36e-241">Os itens criados em uma função, como variáveis, existem somente no escopo da função.</span><span class="sxs-lookup"><span data-stu-id="cf36e-241">The items created in a function, such as variables, exist only in the function scope.</span></span>

<span data-ttu-id="cf36e-242">Para obter mais informações sobre o escopo no PowerShell, consulte [about_Scopes](about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="cf36e-242">For more information about scope in PowerShell, see [about_Scopes](about_Scopes.md).</span></span>

## <a name="finding-and-managing-functions-using-the-function-drive"></a><span data-ttu-id="cf36e-243">Localizando e gerenciando funções usando a unidade Function:</span><span class="sxs-lookup"><span data-stu-id="cf36e-243">Finding and Managing Functions Using the Function: Drive</span></span>

<span data-ttu-id="cf36e-244">Todas as funções e filtros no PowerShell são armazenados automaticamente na `Function:` unidade.</span><span class="sxs-lookup"><span data-stu-id="cf36e-244">All the functions and filters in PowerShell are automatically stored in the `Function:` drive.</span></span> <span data-ttu-id="cf36e-245">Essa unidade é exposta pelo provedor de **funções** do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf36e-245">This drive is exposed by the PowerShell **Function** provider.</span></span>

<span data-ttu-id="cf36e-246">Ao fazer referência à `Function:` unidade, digite uma vírgula após a **função** , assim como faria ao referenciar a `C` unidade ou `D` de um computador.</span><span class="sxs-lookup"><span data-stu-id="cf36e-246">When referring to the `Function:` drive, type a colon after **Function** , just as you would do when referencing the `C` or `D` drive of a computer.</span></span>

<span data-ttu-id="cf36e-247">O comando a seguir exibe todas as funções na sessão atual do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="cf36e-247">The following command displays all the functions in the current session of PowerShell:</span></span>

```powershell
Get-ChildItem function:
```

<span data-ttu-id="cf36e-248">Os comandos na função são armazenados como um bloco de script na propriedade Definition da função.</span><span class="sxs-lookup"><span data-stu-id="cf36e-248">The commands in the function are stored as a script block in the definition property of the function.</span></span> <span data-ttu-id="cf36e-249">Por exemplo, para exibir os comandos na função de ajuda que vem com o PowerShell, digite:</span><span class="sxs-lookup"><span data-stu-id="cf36e-249">For example, to display the commands in the Help function that comes with PowerShell, type:</span></span>

```powershell
(Get-ChildItem function:help).Definition
```

<span data-ttu-id="cf36e-250">Você também pode usar a sintaxe a seguir.</span><span class="sxs-lookup"><span data-stu-id="cf36e-250">You can also use the following syntax.</span></span>

```powershell
$function:help
```

<span data-ttu-id="cf36e-251">Para obter mais informações sobre a `Function:` unidade, consulte o tópico da ajuda para o provedor de **funções** .</span><span class="sxs-lookup"><span data-stu-id="cf36e-251">For more information about the `Function:` drive, see the help topic for the **Function** provider.</span></span> <span data-ttu-id="cf36e-252">Digite `Get-Help Function`.</span><span class="sxs-lookup"><span data-stu-id="cf36e-252">Type `Get-Help Function`.</span></span>

## <a name="reusing-functions-in-new-sessions"></a><span data-ttu-id="cf36e-253">Reutilizando funções em novas sessões</span><span class="sxs-lookup"><span data-stu-id="cf36e-253">Reusing Functions in New Sessions</span></span>

<span data-ttu-id="cf36e-254">Quando você digita uma função no prompt de comando do PowerShell, a função se torna parte da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="cf36e-254">When you type a function at the PowerShell command prompt, the function becomes part of the current session.</span></span> <span data-ttu-id="cf36e-255">Ele estará disponível até que a sessão termine.</span><span class="sxs-lookup"><span data-stu-id="cf36e-255">It is available until the session ends.</span></span>

<span data-ttu-id="cf36e-256">Para usar sua função em todas as sessões do PowerShell, adicione a função ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf36e-256">To use your function in all PowerShell sessions, add the function to your PowerShell profile.</span></span> <span data-ttu-id="cf36e-257">Para obter mais informações sobre perfis, consulte [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="cf36e-257">For more information about profiles, see [about_Profiles](about_Profiles.md).</span></span>

<span data-ttu-id="cf36e-258">Você também pode salvar sua função em um arquivo de script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf36e-258">You can also save your function in a PowerShell script file.</span></span> <span data-ttu-id="cf36e-259">Digite sua função em um arquivo de texto e salve o arquivo com a `.ps1` extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="cf36e-259">Type your function in a text file, and then save the file with the `.ps1` file name extension.</span></span>

## <a name="writing-help-for-functions"></a><span data-ttu-id="cf36e-260">Gravando ajuda para funções</span><span class="sxs-lookup"><span data-stu-id="cf36e-260">Writing Help for Functions</span></span>

<span data-ttu-id="cf36e-261">O `Get-Help` cmdlet obtém ajuda para funções, bem como para cmdlets, provedores e scripts.</span><span class="sxs-lookup"><span data-stu-id="cf36e-261">The `Get-Help` cmdlet gets help for functions, as well as for cmdlets, providers, and scripts.</span></span> <span data-ttu-id="cf36e-262">Para obter ajuda para uma função, digite `Get-Help` seguido pelo nome da função.</span><span class="sxs-lookup"><span data-stu-id="cf36e-262">To get help for a function, type `Get-Help` followed by the function name.</span></span>

<span data-ttu-id="cf36e-263">Por exemplo, para obter ajuda para a `Get-MyDisks` função, digite:</span><span class="sxs-lookup"><span data-stu-id="cf36e-263">For example, to get help for the `Get-MyDisks` function, type:</span></span>

```powershell
Get-Help Get-MyDisks
```

<span data-ttu-id="cf36e-264">Você pode escrever ajuda para uma função usando qualquer um dos dois métodos a seguir:</span><span class="sxs-lookup"><span data-stu-id="cf36e-264">You can write help for a function by using either of the two following methods:</span></span>

- <span data-ttu-id="cf36e-265">Comment-Based ajuda para o Functions</span><span class="sxs-lookup"><span data-stu-id="cf36e-265">Comment-Based Help for Functions</span></span>

  <span data-ttu-id="cf36e-266">Crie um tópico da ajuda usando palavras-chave especiais nos comentários.</span><span class="sxs-lookup"><span data-stu-id="cf36e-266">Create a help topic by using special keywords in the comments.</span></span> <span data-ttu-id="cf36e-267">Para criar uma ajuda baseada em comentários para uma função, os comentários devem ser colocados no início ou no final do corpo da função ou nas linhas que antecedem a palavra-chave da função.</span><span class="sxs-lookup"><span data-stu-id="cf36e-267">To create comment-based help for a function, the comments must be placed at the beginning or end of the function body or on the lines preceding the function keyword.</span></span> <span data-ttu-id="cf36e-268">Para obter mais informações sobre a ajuda baseada em comentários, consulte [about_Comment_Based_Help](about_Comment_Based_Help.md).</span><span class="sxs-lookup"><span data-stu-id="cf36e-268">For more information about comment-based help, see [about_Comment_Based_Help](about_Comment_Based_Help.md).</span></span>

- <span data-ttu-id="cf36e-269">XML-Based ajuda para o Functions</span><span class="sxs-lookup"><span data-stu-id="cf36e-269">XML-Based Help for Functions</span></span>

  <span data-ttu-id="cf36e-270">Crie um tópico de ajuda baseado em XML, como o tipo que normalmente é criado para cmdlets.</span><span class="sxs-lookup"><span data-stu-id="cf36e-270">Create an XML-based help topic, such as the type that is typically created for cmdlets.</span></span> <span data-ttu-id="cf36e-271">A ajuda baseada em XML é necessária se você estiver localizando tópicos de ajuda em vários idiomas.</span><span class="sxs-lookup"><span data-stu-id="cf36e-271">XML-based help is required if you are localizing help topics into multiple languages.</span></span>

  <span data-ttu-id="cf36e-272">Para associar a função ao tópico de ajuda baseado em XML, use a `.ExternalHelp` palavra-chave de ajuda baseada em comentários.</span><span class="sxs-lookup"><span data-stu-id="cf36e-272">To associate the function with the XML-based help topic, use the `.ExternalHelp` comment-based help keyword.</span></span> <span data-ttu-id="cf36e-273">Sem essa palavra-chave, `Get-Help` não é possível localizar o tópico de ajuda da função e as chamadas para `Get-Help` para a função retornam apenas a ajuda gerada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="cf36e-273">Without this keyword, `Get-Help` cannot find the function help topic and calls to `Get-Help` for the function return only auto-generated help.</span></span>

  <span data-ttu-id="cf36e-274">Para obter mais informações sobre a `ExternalHelp` palavra-chave, consulte [about_Comment_Based_Help](about_Comment_Based_Help.md).</span><span class="sxs-lookup"><span data-stu-id="cf36e-274">For more information about the `ExternalHelp` keyword, see [about_Comment_Based_Help](about_Comment_Based_Help.md).</span></span> <span data-ttu-id="cf36e-275">Para obter mais informações sobre a ajuda baseada em XML, consulte [como gravar a ajuda do cmdlet](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).</span><span class="sxs-lookup"><span data-stu-id="cf36e-275">For more information about XML-based help, see [How to Write Cmdlet Help](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).</span></span>

## <a name="see-also"></a><span data-ttu-id="cf36e-276">Confira também</span><span class="sxs-lookup"><span data-stu-id="cf36e-276">See also</span></span>

[<span data-ttu-id="cf36e-277">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="cf36e-277">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="cf36e-278">about_Comment_Based_Help</span><span class="sxs-lookup"><span data-stu-id="cf36e-278">about_Comment_Based_Help</span></span>](about_Comment_Based_Help.md)

[<span data-ttu-id="cf36e-279">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="cf36e-279">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="cf36e-280">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="cf36e-280">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="cf36e-281">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="cf36e-281">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="cf36e-282">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="cf36e-282">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="cf36e-283">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="cf36e-283">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)

[<span data-ttu-id="cf36e-284">about_Parameters</span><span class="sxs-lookup"><span data-stu-id="cf36e-284">about_Parameters</span></span>](about_Parameters.md)

[<span data-ttu-id="cf36e-285">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="cf36e-285">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="cf36e-286">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="cf36e-286">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="cf36e-287">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="cf36e-287">about_Script_Blocks</span></span>](about_Script_Blocks.md)

[<span data-ttu-id="cf36e-288">about_Function_provider</span><span class="sxs-lookup"><span data-stu-id="cf36e-288">about_Function_provider</span></span>](about_Function_provider.md)
