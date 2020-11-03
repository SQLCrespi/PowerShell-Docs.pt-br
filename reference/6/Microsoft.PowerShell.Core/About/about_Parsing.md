---
description: Descreve como o PowerShell analisa os comandos.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 09/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_parsing?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parsing
ms.openlocfilehash: 200a3aa7aac6477a2b2d3660167621132514c333
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195682"
---
# <a name="about-parsing"></a><span data-ttu-id="90d6e-104">Sobre a análise</span><span class="sxs-lookup"><span data-stu-id="90d6e-104">About Parsing</span></span>

## <a name="short-description"></a><span data-ttu-id="90d6e-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="90d6e-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="90d6e-106">Descreve como o PowerShell analisa os comandos.</span><span class="sxs-lookup"><span data-stu-id="90d6e-106">Describes how PowerShell parses commands.</span></span>

## <a name="long-description"></a><span data-ttu-id="90d6e-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="90d6e-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="90d6e-108">Quando você insere um comando no prompt de comando, o PowerShell quebra o texto do comando em uma série de segmentos chamados _tokens_ e, em seguida, determina como interpretar cada token.</span><span class="sxs-lookup"><span data-stu-id="90d6e-108">When you enter a command at the command prompt, PowerShell breaks the command text into a series of segments called _tokens_ and then determines how to interpret each token.</span></span>

<span data-ttu-id="90d6e-109">Por exemplo, se você digitar:</span><span class="sxs-lookup"><span data-stu-id="90d6e-109">For example, if you type:</span></span>

```powershell
Write-Host book
```

<span data-ttu-id="90d6e-110">O PowerShell quebra o comando em dois tokens `Write-Host` e, em seguida `book` , interpreta cada token independentemente usando um dos dois modos de análise principais: modo de expressão e modo de argumento.</span><span class="sxs-lookup"><span data-stu-id="90d6e-110">PowerShell breaks the command into two tokens, `Write-Host` and `book`, and interprets each token independently using one of two major parsing modes: expression mode and argument mode.</span></span>

> [!NOTE]
> <span data-ttu-id="90d6e-111">Como o PowerShell analisa a entrada de comando, ele tenta resolver os nomes de comando para cmdlets ou executáveis nativos.</span><span class="sxs-lookup"><span data-stu-id="90d6e-111">As PowerShell parses command input it tries to resolve the command names to cmdlets or native executables.</span></span> <span data-ttu-id="90d6e-112">Se um nome de comando não tiver uma correspondência exata, o PowerShell precederá `Get-` o comando como um verbo padrão.</span><span class="sxs-lookup"><span data-stu-id="90d6e-112">If a command name does not have an exact match, PowerShell prepends `Get-` to the command as a default verb.</span></span> <span data-ttu-id="90d6e-113">Por exemplo, o PowerShell analisa `Process` como `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="90d6e-113">For example, PowerShell parses `Process` as `Get-Process`.</span></span> <span data-ttu-id="90d6e-114">Não é recomendável usar esse recurso pelos seguintes motivos:</span><span class="sxs-lookup"><span data-stu-id="90d6e-114">It's not recommended to use this feature for the following reasons:</span></span>
>
> - <span data-ttu-id="90d6e-115">Ele é ineficiente.</span><span class="sxs-lookup"><span data-stu-id="90d6e-115">It's inefficient.</span></span> <span data-ttu-id="90d6e-116">Isso faz com que o PowerShell pesquise várias vezes.</span><span class="sxs-lookup"><span data-stu-id="90d6e-116">This causes PowerShell to search multiple times.</span></span>
> - <span data-ttu-id="90d6e-117">Programas externos com o mesmo nome são resolvidos primeiro, portanto, você não pode executar o cmdlet pretendido.</span><span class="sxs-lookup"><span data-stu-id="90d6e-117">External programs with the same name are resolved first, so you may not execute intended cmdlet.</span></span>
> - <span data-ttu-id="90d6e-118">`Get-Help` e `Get-Command` não reconhecem nomes sem verbos.</span><span class="sxs-lookup"><span data-stu-id="90d6e-118">`Get-Help` and `Get-Command` don't recognize verb-less names.</span></span>

### <a name="expression-mode"></a><span data-ttu-id="90d6e-119">Modo de expressão</span><span class="sxs-lookup"><span data-stu-id="90d6e-119">Expression mode</span></span>

<span data-ttu-id="90d6e-120">O modo de expressão destina-se à combinação de expressões, necessário para manipulação de valor em uma linguagem de script.</span><span class="sxs-lookup"><span data-stu-id="90d6e-120">Expression mode is intended for combining expressions, required for value manipulation in a scripting language.</span></span> <span data-ttu-id="90d6e-121">As expressões são representações de valores na sintaxe do PowerShell e podem ser simples ou compostas, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="90d6e-121">Expressions are representations of values in PowerShell syntax, and can be simple or composite, for example:</span></span>

<span data-ttu-id="90d6e-122">As expressões literais são representações diretas de seus valores:</span><span class="sxs-lookup"><span data-stu-id="90d6e-122">Literal expressions are direct representations of their values:</span></span> 

```powershell
'hello', 32
```

<span data-ttu-id="90d6e-123">Expressões variáveis carregam o valor da variável à qual fazem referência:</span><span class="sxs-lookup"><span data-stu-id="90d6e-123">Variable expressions carry the value of the variable they reference:</span></span> 

```powershell
$x, $script:path
```
<span data-ttu-id="90d6e-124">Os operadores combinam outras expressões para avaliação:</span><span class="sxs-lookup"><span data-stu-id="90d6e-124">Operators combine other expressions for evaluation:</span></span> 

```powershell
- 12, -not $Quiet, 3 + 7, $input.Length -gt 1
```

- <span data-ttu-id="90d6e-125">Os _literais de cadeia de caracteres_ devem estar entre aspas.</span><span class="sxs-lookup"><span data-stu-id="90d6e-125">_Character string literals_ must be contained in quotation marks.</span></span>
- <span data-ttu-id="90d6e-126">Os _números_ são tratados como valores numéricos em vez de uma série de caracteres (a menos que tenham escape).</span><span class="sxs-lookup"><span data-stu-id="90d6e-126">_Numbers_ are treated as numerical values rather than as a series of characters (unless escaped).</span></span>
- <span data-ttu-id="90d6e-127">_Operadores_ , incluindo operadores unários como `-` e `-not` e operadores binários como `+` e `-gt` , são interpretados como operadores e aplicam suas respectivas operações em seus argumentos (operandos).</span><span class="sxs-lookup"><span data-stu-id="90d6e-127">_Operators_ , including unary operators like `-` and `-not` and binary operators like `+` and `-gt`, are interpreted as operators and apply their respective operations on their arguments (operands).</span></span>
- <span data-ttu-id="90d6e-128">As _expressões de atributo e de conversão_ são analisadas como expressões e aplicadas a expressões subordinadas, por exemplo, `[int] '7'` .</span><span class="sxs-lookup"><span data-stu-id="90d6e-128">_Attribute and conversion expressions_ are parsed as expressions and applied to subordinate expressions, e.g. `[int] '7'`.</span></span>
- <span data-ttu-id="90d6e-129">_Referências de variáveis_ são avaliadas para seus valores, mas _nivelamento_ (ou seja, colar conjuntos de parâmetros predefinidos) é proibido e causa um erro de analisador.</span><span class="sxs-lookup"><span data-stu-id="90d6e-129">_Variable references_ are evaluated to their values but _splatting_ (i.e. pasting prefilled parameter sets) is forbidden and causes a parser error.</span></span>
- <span data-ttu-id="90d6e-130">Qualquer outra coisa será tratada como um comando a ser invocado.</span><span class="sxs-lookup"><span data-stu-id="90d6e-130">Anything else will be treated as a command to be invoked.</span></span>

### <a name="argument-mode"></a><span data-ttu-id="90d6e-131">Modo de argumento</span><span class="sxs-lookup"><span data-stu-id="90d6e-131">Argument mode</span></span>

<span data-ttu-id="90d6e-132">Durante a análise, o PowerShell primeiro procura interpretar a entrada como uma expressão.</span><span class="sxs-lookup"><span data-stu-id="90d6e-132">When parsing, PowerShell first looks to interpret input as an expression.</span></span> <span data-ttu-id="90d6e-133">Mas quando uma invocação de comando é encontrada, a análise continua no modo de argumento.</span><span class="sxs-lookup"><span data-stu-id="90d6e-133">But when a command invocation is encountered, parsing continues in argument mode.</span></span>

<span data-ttu-id="90d6e-134">O modo de argumento é projetado para a análise de argumentos e parâmetros para comandos em um ambiente de Shell.</span><span class="sxs-lookup"><span data-stu-id="90d6e-134">Argument mode is designed for parsing arguments and parameters for commands in a shell environment.</span></span> <span data-ttu-id="90d6e-135">Toda a entrada é tratada como uma cadeia de caracteres expansível, a menos que use uma das seguintes sintaxes:</span><span class="sxs-lookup"><span data-stu-id="90d6e-135">All input is treated as an expandable string unless it uses one of the following syntaxes:</span></span>

- <span data-ttu-id="90d6e-136">Cifrão ( `$` ) inicia uma referência de variável (somente se ela for seguida por um nome de variável válido, caso contrário, ela será interpretada como parte da cadeia de caracteres expansível).</span><span class="sxs-lookup"><span data-stu-id="90d6e-136">Dollar sign (`$`) begins a variable reference (only if it is followed by a valid variable name, otherwise it is interpreted as part of the expandable string).</span></span>
- <span data-ttu-id="90d6e-137">Aspas ( `'` e `"` ) iniciar valores de cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="90d6e-137">Quotation marks (`'` and `"`) begin string values</span></span>
- <span data-ttu-id="90d6e-138">Parênteses ( `(` e `)` ) demarcam novas expressões.</span><span class="sxs-lookup"><span data-stu-id="90d6e-138">Parentheses (`(` and `)`) demarcate new expressions.</span></span>
- <span data-ttu-id="90d6e-139">Expressões inseridas de operador de subexpressão ( `$(` ... `)` ) demarcates.</span><span class="sxs-lookup"><span data-stu-id="90d6e-139">Subexpression operator (`$(`…`)`) demarcates embedded expressions.</span></span>
- <span data-ttu-id="90d6e-140">Chaves ( `{` e `}` ) demarcar novos blocos de script.</span><span class="sxs-lookup"><span data-stu-id="90d6e-140">Braces (`{` and `}`) demarcate new script blocks.</span></span>
- <span data-ttu-id="90d6e-141">O sinal de arroba inicial ( `@` ) inicia as sintaxes de expressão, como nivelamento ( `@args` ), matrizes ( `@(1,2,3)` ) e tabelas de hash ( `@{a=1;b=2}` ).</span><span class="sxs-lookup"><span data-stu-id="90d6e-141">Initial at sign (`@`) begins expression syntaxes such as splatting (`@args`), arrays (`@(1,2,3)`) and hash tables (`@{a=1;b=2}`).</span></span>
- <span data-ttu-id="90d6e-142">Vírgulas ( `,` ) introduzem listas passadas como matrizes, exceto quando o comando a ser chamado é um aplicativo nativo; nesse caso, eles são interpretados como parte da cadeia de caracteres expansível.</span><span class="sxs-lookup"><span data-stu-id="90d6e-142">Commas (`,`) introduce lists passed as arrays, except when the command to be called is a native application, in which case they are interpreted as part of the expandable string.</span></span> <span data-ttu-id="90d6e-143">Não há suporte para vírgulas iniciais, consecutivas ou à direita.</span><span class="sxs-lookup"><span data-stu-id="90d6e-143">Initial, consecutive or trailing commas are not supported.</span></span>

<span data-ttu-id="90d6e-144">Os valores das expressões inseridas são convertidos em cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="90d6e-144">Values of embedded expressions are converted to strings.</span></span>

<span data-ttu-id="90d6e-145">A tabela a seguir fornece vários exemplos de valores processados no modo de expressão e no modo de argumento e na avaliação desses valores.</span><span class="sxs-lookup"><span data-stu-id="90d6e-145">The following table provides several examples of values processed in expression mode and argument mode and the evaluation of those values.</span></span> <span data-ttu-id="90d6e-146">Supomos que o valor da variável `a` é `4` .</span><span class="sxs-lookup"><span data-stu-id="90d6e-146">We assume that the value of the variable `a` is `4`.</span></span>

|       <span data-ttu-id="90d6e-147">Exemplo</span><span class="sxs-lookup"><span data-stu-id="90d6e-147">Example</span></span>        |    <span data-ttu-id="90d6e-148">Modo</span><span class="sxs-lookup"><span data-stu-id="90d6e-148">Mode</span></span>    |      <span data-ttu-id="90d6e-149">Result</span><span class="sxs-lookup"><span data-stu-id="90d6e-149">Result</span></span>       |
| -------------------- | ---------- | ----------------- |
| `2`                  | <span data-ttu-id="90d6e-150">Expression</span><span class="sxs-lookup"><span data-stu-id="90d6e-150">Expression</span></span> | <span data-ttu-id="90d6e-151">2 (inteiro)</span><span class="sxs-lookup"><span data-stu-id="90d6e-151">2 (integer)</span></span>       |
| `` `2``              | <span data-ttu-id="90d6e-152">Expression</span><span class="sxs-lookup"><span data-stu-id="90d6e-152">Expression</span></span> | <span data-ttu-id="90d6e-153">"2" (comando)</span><span class="sxs-lookup"><span data-stu-id="90d6e-153">"2" (command)</span></span>     |
| `echo 2`             | <span data-ttu-id="90d6e-154">Expression</span><span class="sxs-lookup"><span data-stu-id="90d6e-154">Expression</span></span> | <span data-ttu-id="90d6e-155">2 (inteiro)</span><span class="sxs-lookup"><span data-stu-id="90d6e-155">2 (integer)</span></span>       |
| `2+2`                | <span data-ttu-id="90d6e-156">Expression</span><span class="sxs-lookup"><span data-stu-id="90d6e-156">Expression</span></span> | <span data-ttu-id="90d6e-157">4 (inteiro)</span><span class="sxs-lookup"><span data-stu-id="90d6e-157">4 (integer)</span></span>       |
| `echo 2+2`           | <span data-ttu-id="90d6e-158">Argumento</span><span class="sxs-lookup"><span data-stu-id="90d6e-158">Argument</span></span>   | <span data-ttu-id="90d6e-159">"2 + 2" (cadeia de caracteres)</span><span class="sxs-lookup"><span data-stu-id="90d6e-159">"2+2" (string)</span></span>    |
| `echo(2+2)`          | <span data-ttu-id="90d6e-160">Expression</span><span class="sxs-lookup"><span data-stu-id="90d6e-160">Expression</span></span> | <span data-ttu-id="90d6e-161">4 (inteiro)</span><span class="sxs-lookup"><span data-stu-id="90d6e-161">4 (integer)</span></span>       |
| `$a`                 | <span data-ttu-id="90d6e-162">Expression</span><span class="sxs-lookup"><span data-stu-id="90d6e-162">Expression</span></span> | <span data-ttu-id="90d6e-163">4 (inteiro)</span><span class="sxs-lookup"><span data-stu-id="90d6e-163">4 (integer)</span></span>       |
| `echo $a`            | <span data-ttu-id="90d6e-164">Expression</span><span class="sxs-lookup"><span data-stu-id="90d6e-164">Expression</span></span> | <span data-ttu-id="90d6e-165">4 (inteiro)</span><span class="sxs-lookup"><span data-stu-id="90d6e-165">4 (integer)</span></span>       |
| `$a+2`               | <span data-ttu-id="90d6e-166">Expression</span><span class="sxs-lookup"><span data-stu-id="90d6e-166">Expression</span></span> | <span data-ttu-id="90d6e-167">6 (inteiro)</span><span class="sxs-lookup"><span data-stu-id="90d6e-167">6 (integer)</span></span>       |
| `echo $a+2`          | <span data-ttu-id="90d6e-168">Argumento</span><span class="sxs-lookup"><span data-stu-id="90d6e-168">Argument</span></span>   | <span data-ttu-id="90d6e-169">4 + 2 (cadeia de caracteres)</span><span class="sxs-lookup"><span data-stu-id="90d6e-169">4+2 (string)</span></span>      |
| `$-`                 | <span data-ttu-id="90d6e-170">Argumento</span><span class="sxs-lookup"><span data-stu-id="90d6e-170">Argument</span></span>   | <span data-ttu-id="90d6e-171">"$-" (comando)</span><span class="sxs-lookup"><span data-stu-id="90d6e-171">"$-" (command)</span></span>    |
| `echo $-`            | <span data-ttu-id="90d6e-172">Argumento</span><span class="sxs-lookup"><span data-stu-id="90d6e-172">Argument</span></span>   | <span data-ttu-id="90d6e-173">"$-" (cadeia de caracteres)</span><span class="sxs-lookup"><span data-stu-id="90d6e-173">"$-" (string)</span></span>     |
| `a$a`                | <span data-ttu-id="90d6e-174">Expression</span><span class="sxs-lookup"><span data-stu-id="90d6e-174">Expression</span></span> | <span data-ttu-id="90d6e-175">"a $ a" (comando)</span><span class="sxs-lookup"><span data-stu-id="90d6e-175">"a$a" (command)</span></span>   |
| `echo a$a`           | <span data-ttu-id="90d6e-176">Argumento</span><span class="sxs-lookup"><span data-stu-id="90d6e-176">Argument</span></span>   | <span data-ttu-id="90d6e-177">"A4" (cadeia de caracteres)</span><span class="sxs-lookup"><span data-stu-id="90d6e-177">"a4" (string)</span></span>     |
| `a'$a'`              | <span data-ttu-id="90d6e-178">Expression</span><span class="sxs-lookup"><span data-stu-id="90d6e-178">Expression</span></span> | <span data-ttu-id="90d6e-179">"a $ a" (comando)</span><span class="sxs-lookup"><span data-stu-id="90d6e-179">"a$a" (command)</span></span>   |
| `echo a'$a'`         | <span data-ttu-id="90d6e-180">Argumento</span><span class="sxs-lookup"><span data-stu-id="90d6e-180">Argument</span></span>   | <span data-ttu-id="90d6e-181">"a $ a" (cadeia de caracteres)</span><span class="sxs-lookup"><span data-stu-id="90d6e-181">"a$a" (string)</span></span>    |
| `a"$a"`              | <span data-ttu-id="90d6e-182">Expression</span><span class="sxs-lookup"><span data-stu-id="90d6e-182">Expression</span></span> | <span data-ttu-id="90d6e-183">"a $ a" (comando)</span><span class="sxs-lookup"><span data-stu-id="90d6e-183">"a$a" (command)</span></span>   |
| `echo a"$a"`         | <span data-ttu-id="90d6e-184">Argumento</span><span class="sxs-lookup"><span data-stu-id="90d6e-184">Argument</span></span>   | <span data-ttu-id="90d6e-185">"A4" (cadeia de caracteres)</span><span class="sxs-lookup"><span data-stu-id="90d6e-185">"a4" (string)</span></span>     |
| `a$(2)`              | <span data-ttu-id="90d6e-186">Expression</span><span class="sxs-lookup"><span data-stu-id="90d6e-186">Expression</span></span> | <span data-ttu-id="90d6e-187">"a $ (2)" (comando)</span><span class="sxs-lookup"><span data-stu-id="90d6e-187">"a$(2)" (command)</span></span> |
| `echo a$(2)`         | <span data-ttu-id="90d6e-188">Argumento</span><span class="sxs-lookup"><span data-stu-id="90d6e-188">Argument</span></span>   | <span data-ttu-id="90d6e-189">"a2" (cadeia de caracteres)</span><span class="sxs-lookup"><span data-stu-id="90d6e-189">"a2" (string)</span></span>     |

<span data-ttu-id="90d6e-190">Cada token pode ser interpretado como um tipo de objeto, como booliano ou cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="90d6e-190">Every token can be interpreted as some kind of object type, such as Boolean or string.</span></span> <span data-ttu-id="90d6e-191">O PowerShell tenta determinar o tipo de objeto a partir da expressão.</span><span class="sxs-lookup"><span data-stu-id="90d6e-191">PowerShell attempts to determine the object type from the expression.</span></span>
<span data-ttu-id="90d6e-192">O tipo de objeto depende do tipo de parâmetro esperado por um comando e se o PowerShell sabe como converter o argumento para o tipo correto.</span><span class="sxs-lookup"><span data-stu-id="90d6e-192">The object type depends on the type of parameter a command expects and on whether PowerShell knows how to convert the argument to the correct type.</span></span> <span data-ttu-id="90d6e-193">A tabela a seguir mostra vários exemplos dos tipos atribuídos aos valores retornados pelas expressões.</span><span class="sxs-lookup"><span data-stu-id="90d6e-193">The following table shows several examples of the types assigned to values returned by the expressions.</span></span>

|       <span data-ttu-id="90d6e-194">Exemplo</span><span class="sxs-lookup"><span data-stu-id="90d6e-194">Example</span></span>          |    <span data-ttu-id="90d6e-195">Modo</span><span class="sxs-lookup"><span data-stu-id="90d6e-195">Mode</span></span>    |     <span data-ttu-id="90d6e-196">Resultado</span><span class="sxs-lookup"><span data-stu-id="90d6e-196">Result</span></span>      |
| ---------------------- | ---------- | --------------- |
| `Write-Output !1`      | <span data-ttu-id="90d6e-197">argumento</span><span class="sxs-lookup"><span data-stu-id="90d6e-197">argument</span></span>   | <span data-ttu-id="90d6e-198">"! 1" (cadeia de caracteres)</span><span class="sxs-lookup"><span data-stu-id="90d6e-198">"!1" (string)</span></span>   |
| `Write-Output (!1)`    | <span data-ttu-id="90d6e-199">expressão</span><span class="sxs-lookup"><span data-stu-id="90d6e-199">expression</span></span> | <span data-ttu-id="90d6e-200">Falso (booliano)</span><span class="sxs-lookup"><span data-stu-id="90d6e-200">False (Boolean)</span></span> |
| `Write-Output (2)`     | <span data-ttu-id="90d6e-201">expressão</span><span class="sxs-lookup"><span data-stu-id="90d6e-201">expression</span></span> | <span data-ttu-id="90d6e-202">2 (inteiro)</span><span class="sxs-lookup"><span data-stu-id="90d6e-202">2 (integer)</span></span>     |
| `Set-Variable AB A,B`  | <span data-ttu-id="90d6e-203">argumento</span><span class="sxs-lookup"><span data-stu-id="90d6e-203">argument</span></span>   | <span data-ttu-id="90d6e-204">' A ', ' B ' (matriz)</span><span class="sxs-lookup"><span data-stu-id="90d6e-204">'A','B' (array)</span></span> |
| `CMD /CECHO A,B`       | <span data-ttu-id="90d6e-205">argumento</span><span class="sxs-lookup"><span data-stu-id="90d6e-205">argument</span></span>   | <span data-ttu-id="90d6e-206">' A, B ' (cadeia de caracteres)</span><span class="sxs-lookup"><span data-stu-id="90d6e-206">'A,B' (string)</span></span>  |
| `CMD /CECHO $AB`       | <span data-ttu-id="90d6e-207">expressão</span><span class="sxs-lookup"><span data-stu-id="90d6e-207">expression</span></span> | <span data-ttu-id="90d6e-208">' A ', ' B ' (matriz)</span><span class="sxs-lookup"><span data-stu-id="90d6e-208">'A','B' (array)</span></span> |
| `CMD /CECHO :$AB`      | <span data-ttu-id="90d6e-209">argumento</span><span class="sxs-lookup"><span data-stu-id="90d6e-209">argument</span></span>   | <span data-ttu-id="90d6e-210">': A B ' (cadeia de caracteres)</span><span class="sxs-lookup"><span data-stu-id="90d6e-210">':A B' (string)</span></span> |

<span data-ttu-id="90d6e-211">O símbolo de análise de parada ( `--%` ), introduzido no powershell 3,0, direciona o PowerShell para evitar a interpretação de entrada como comandos ou expressões do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90d6e-211">The stop-parsing symbol (`--%`), introduced in PowerShell 3.0, directs PowerShell to refrain from interpreting input as PowerShell commands or expressions.</span></span>

<span data-ttu-id="90d6e-212">Ao chamar um programa executável no PowerShell, coloque o símbolo de interrupção de análise antes dos argumentos do programa.</span><span class="sxs-lookup"><span data-stu-id="90d6e-212">When calling an executable program in PowerShell, place the stop-parsing symbol before the program arguments.</span></span> <span data-ttu-id="90d6e-213">Essa técnica é muito mais fácil do que usar caracteres de escape para evitar a interpretação indiferente.</span><span class="sxs-lookup"><span data-stu-id="90d6e-213">This technique is much easier than using escape characters to prevent misinterpretation.</span></span>

<span data-ttu-id="90d6e-214">Quando ele encontra um símbolo de análise de parada, o PowerShell trata os caracteres restantes na linha como um literal.</span><span class="sxs-lookup"><span data-stu-id="90d6e-214">When it encounters a stop-parsing symbol, PowerShell treats the remaining characters in the line as a literal.</span></span> <span data-ttu-id="90d6e-215">A única interpretação que ele executa é substituir valores de variáveis de ambiente que usam notação padrão do Windows, como `%USERPROFILE%` .</span><span class="sxs-lookup"><span data-stu-id="90d6e-215">The only interpretation it performs is to substitute values for environment variables that use standard Windows notation, such as `%USERPROFILE%`.</span></span>

<span data-ttu-id="90d6e-216">O símbolo de interrupção de análise entra em vigor somente até o próximo caractere de nova linha ou de pipeline.</span><span class="sxs-lookup"><span data-stu-id="90d6e-216">The stop-parsing symbol is effective only until the next newline or pipeline character.</span></span> <span data-ttu-id="90d6e-217">Você não pode usar um caractere de continuação ( `` ` `` ) para estender seu efeito ou usar um delimitador de comando ( `;` ) para encerrar seu efeito.</span><span class="sxs-lookup"><span data-stu-id="90d6e-217">You cannot use a continuation character (`` ` ``) to extend its effect or use a command delimiter (`;`) to terminate its effect.</span></span>

<span data-ttu-id="90d6e-218">Por exemplo, o comando a seguir chama o programa **icacls** .</span><span class="sxs-lookup"><span data-stu-id="90d6e-218">For example, the following command calls the **Icacls** program.</span></span>

```powershell
icacls X:\VMS /grant Dom\HVAdmin:(CI)(OI)F
```

<span data-ttu-id="90d6e-219">Para executar esse comando no PowerShell 2,0, você deve usar caracteres de escape para impedir que o PowerShell interprete incorretamente os parênteses.</span><span class="sxs-lookup"><span data-stu-id="90d6e-219">To run this command in PowerShell 2.0, you must use escape characters to prevent PowerShell from misinterpreting the parentheses.</span></span>

```powershell
icacls X:\VMS /grant Dom\HVAdmin:`(CI`)`(OI`)F
```

<span data-ttu-id="90d6e-220">A partir do PowerShell 3,0, você pode usar o símbolo de interrupção de análise.</span><span class="sxs-lookup"><span data-stu-id="90d6e-220">Beginning in PowerShell 3.0, you can use the stop-parsing symbol.</span></span>

```powershell
icacls X:\VMS --% /grant Dom\HVAdmin:(CI)(OI)F
```

<span data-ttu-id="90d6e-221">O PowerShell envia a seguinte cadeia de caracteres de comando para o programa **icacls** :</span><span class="sxs-lookup"><span data-stu-id="90d6e-221">PowerShell sends the following command string to the **Icacls** program:</span></span>

`X:\VMS /grant Dom\HVAdmin:(CI)(OI)F`

> [!NOTE]
> <span data-ttu-id="90d6e-222">O símbolo de análise de parada destina-se somente ao uso em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="90d6e-222">The stop-parsing symbol only intended for use on Windows platforms.</span></span>

## <a name="see-also"></a><span data-ttu-id="90d6e-223">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="90d6e-223">SEE ALSO</span></span>

[<span data-ttu-id="90d6e-224">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="90d6e-224">about_Command_Syntax</span></span>](about_Command_Syntax.md)
