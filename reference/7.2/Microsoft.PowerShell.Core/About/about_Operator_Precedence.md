---
description: Lista os operadores do PowerShell em ordem de precedência.
Locale: en-US
ms.date: 11/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_operator_precedence?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Operator_Precedence
ms.openlocfilehash: d4031a9d9a67340470d5418a9c2d3e33c5caed13
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596790"
---
# <a name="about-operator-precedence"></a><span data-ttu-id="cd1ed-103">Sobre a precedência de operador</span><span class="sxs-lookup"><span data-stu-id="cd1ed-103">About Operator Precedence</span></span>

## <a name="short-description"></a><span data-ttu-id="cd1ed-104">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="cd1ed-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="cd1ed-105">Lista os operadores do PowerShell em ordem de precedência.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-105">Lists the PowerShell operators in precedence order.</span></span>

## <a name="long-description"></a><span data-ttu-id="cd1ed-106">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="cd1ed-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="cd1ed-107">Os operadores do PowerShell permitem construir expressões simples, mas poderosas.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-107">PowerShell operators let you construct simple, but powerful expressions.</span></span> <span data-ttu-id="cd1ed-108">Este tópico lista os operadores em ordem de precedência.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-108">This topic lists the operators in precedence order.</span></span> <span data-ttu-id="cd1ed-109">Ordem de precedência é a ordem na qual o PowerShell avalia os operadores quando vários operadores aparecem na mesma expressão.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-109">Precedence order is the order in which PowerShell evaluates the operators when multiple operators appear in the same expression.</span></span>

<span data-ttu-id="cd1ed-110">Quando os operadores têm precedência igual, o PowerShell os avalia da esquerda para a direita, conforme aparecem dentro da expressão.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-110">When operators have equal precedence, PowerShell evaluates them from left to right as they appear within the expression.</span></span> <span data-ttu-id="cd1ed-111">As exceções são os operadores de atribuição, os operadores de conversão e os operadores de negação ( `!` , `-not` , `-bnot` ), que são avaliados da direita para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-111">The exceptions are the assignment operators, the cast operators, and the negation operators (`!`, `-not`, `-bnot`), which are evaluated from right to left.</span></span>

<span data-ttu-id="cd1ed-112">Você pode usar os compartimentos, como parênteses, para substituir a ordem de precedência padrão e forçar o PowerShell a avaliar a parte inclusa de uma expressão antes de uma parte não colocada.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-112">You can use enclosures, such as parentheses, to override the standard precedence order and force PowerShell to evaluate the enclosed part of an expression before an unenclosed part.</span></span>

<span data-ttu-id="cd1ed-113">Na lista a seguir, os operadores são listados na ordem em que são avaliados.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-113">In the following list, operators are listed in the order that they are evaluated.</span></span> <span data-ttu-id="cd1ed-114">Os operadores na mesma linha ou no mesmo grupo têm precedência igual.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-114">Operators on the same line, or in the same group, have equal precedence.</span></span>

<span data-ttu-id="cd1ed-115">A coluna operador lista os operadores.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-115">The Operator column lists the operators.</span></span> <span data-ttu-id="cd1ed-116">A coluna referência lista o tópico de ajuda do PowerShell no qual o operador é descrito.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-116">The Reference column lists the PowerShell Help topic in which the operator is described.</span></span> <span data-ttu-id="cd1ed-117">Para exibir o tópico, digite `get-help <topic-name>` .</span><span class="sxs-lookup"><span data-stu-id="cd1ed-117">To display the topic, type `get-help <topic-name>`.</span></span>

|         <span data-ttu-id="cd1ed-118">OPERATOR</span><span class="sxs-lookup"><span data-stu-id="cd1ed-118">OPERATOR</span></span>         |           <span data-ttu-id="cd1ed-119">REFERÊNCIA</span><span class="sxs-lookup"><span data-stu-id="cd1ed-119">REFERENCE</span></span>            |
| ------------------------ | ------------------------------ |
| `$() @() () @{}`         | <span data-ttu-id="cd1ed-120">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-120">[about_Operators][]</span></span>            |
| <span data-ttu-id="cd1ed-121">`. ?.` (acesso de membro)</span><span class="sxs-lookup"><span data-stu-id="cd1ed-121">`. ?.` (member access)</span></span>   | <span data-ttu-id="cd1ed-122">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-122">[about_Operators][]</span></span>            |
| <span data-ttu-id="cd1ed-123">`::` auto-estática</span><span class="sxs-lookup"><span data-stu-id="cd1ed-123">`::` (static)</span></span>            | <span data-ttu-id="cd1ed-124">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-124">[about_Operators][]</span></span>            |
| <span data-ttu-id="cd1ed-125">`[0] ?[0]` (operador de índice)</span><span class="sxs-lookup"><span data-stu-id="cd1ed-125">`[0] ?[0]` (index operator)</span></span> | <span data-ttu-id="cd1ed-126">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-126">[about_Operators][]</span></span>         |
| <span data-ttu-id="cd1ed-127">`[int]` (operadores de conversão)</span><span class="sxs-lookup"><span data-stu-id="cd1ed-127">`[int]` (cast operators)</span></span> | <span data-ttu-id="cd1ed-128">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-128">[about_Operators][]</span></span>            |
| <span data-ttu-id="cd1ed-129">`-split` unário</span><span class="sxs-lookup"><span data-stu-id="cd1ed-129">`-split` (unary)</span></span>         | <span data-ttu-id="cd1ed-130">[about_Split][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-130">[about_Split][]</span></span>                |
| <span data-ttu-id="cd1ed-131">`-join` unário</span><span class="sxs-lookup"><span data-stu-id="cd1ed-131">`-join` (unary)</span></span>          | <span data-ttu-id="cd1ed-132">[about_Join][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-132">[about_Join][]</span></span>                 |
| <span data-ttu-id="cd1ed-133">`,` (operador de vírgula)</span><span class="sxs-lookup"><span data-stu-id="cd1ed-133">`,` (comma operator)</span></span>     | <span data-ttu-id="cd1ed-134">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-134">[about_Operators][]</span></span>            |
| `++ --`                  | <span data-ttu-id="cd1ed-135">[about_Assignment_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-135">[about_Assignment_Operators][]</span></span> |
| `! -not`                 | <span data-ttu-id="cd1ed-136">[about_Logical_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-136">[about_Logical_Operators][]</span></span>    |
| <span data-ttu-id="cd1ed-137">`..` (operador de intervalo)</span><span class="sxs-lookup"><span data-stu-id="cd1ed-137">`..` (range operator)</span></span>    | <span data-ttu-id="cd1ed-138">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-138">[about_Operators][]</span></span>            |
| <span data-ttu-id="cd1ed-139">`-f` (operador Format)</span><span class="sxs-lookup"><span data-stu-id="cd1ed-139">`-f` (format operator)</span></span>   | <span data-ttu-id="cd1ed-140">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-140">[about_Operators][]</span></span>            |
| <span data-ttu-id="cd1ed-141">`-` (unário/negativo)</span><span class="sxs-lookup"><span data-stu-id="cd1ed-141">`-` (unary/negative)</span></span>     | <span data-ttu-id="cd1ed-142">[about_Arithmetic_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-142">[about_Arithmetic_Operators][]</span></span> |
| `* / %`                  | <span data-ttu-id="cd1ed-143">[about_Arithmetic_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-143">[about_Arithmetic_Operators][]</span></span> |
| `+ -`                    | <span data-ttu-id="cd1ed-144">[about_Arithmetic_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-144">[about_Arithmetic_Operators][]</span></span> |

<span data-ttu-id="cd1ed-145">O grupo de operadores a seguir tem precedência igual.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-145">The following group of operators have equal precedence.</span></span> <span data-ttu-id="cd1ed-146">Suas variantes que diferenciam maiúsculas de minúsculas e explicitamente não diferenciam maiúsculas de minúsculas têm a mesma precedência.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-146">Their case-sensitive and explicitly case-insensitive variants have the same precedence.</span></span>

|         <span data-ttu-id="cd1ed-147">OPERATOR</span><span class="sxs-lookup"><span data-stu-id="cd1ed-147">OPERATOR</span></span>          |           <span data-ttu-id="cd1ed-148">REFERÊNCIA</span><span class="sxs-lookup"><span data-stu-id="cd1ed-148">REFERENCE</span></span>            |
| ------------------------- | ------------------------------ |
| <span data-ttu-id="cd1ed-149">`-split` binário</span><span class="sxs-lookup"><span data-stu-id="cd1ed-149">`-split` (binary)</span></span>         | <span data-ttu-id="cd1ed-150">[about_Split][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-150">[about_Split][]</span></span>                |
| <span data-ttu-id="cd1ed-151">`-join` binário</span><span class="sxs-lookup"><span data-stu-id="cd1ed-151">`-join` (binary)</span></span>          | <span data-ttu-id="cd1ed-152">[about_Join][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-152">[about_Join][]</span></span>                 |
| `-is -isnot -as`          | <span data-ttu-id="cd1ed-153">[about_Type_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-153">[about_Type_Operators][]</span></span>       |
| `-eq -ne -gt -gt -lt -le` | <span data-ttu-id="cd1ed-154">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-154">[about_Comparison_Operators][]</span></span> |
| `-like -notlike`          | <span data-ttu-id="cd1ed-155">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-155">[about_Comparison_Operators][]</span></span> |
| `-match -notmatch`        | <span data-ttu-id="cd1ed-156">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-156">[about_Comparison_Operators][]</span></span> |
| `-in -notIn`              | <span data-ttu-id="cd1ed-157">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-157">[about_Comparison_Operators][]</span></span> |
| `-contains -notContains`  | <span data-ttu-id="cd1ed-158">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-158">[about_Comparison_Operators][]</span></span> |
| `-replace`                | <span data-ttu-id="cd1ed-159">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-159">[about_Comparison_Operators][]</span></span> |

<span data-ttu-id="cd1ed-160">A lista é retomada aqui com os seguintes operadores na ordem de precedência:</span><span class="sxs-lookup"><span data-stu-id="cd1ed-160">The list resumes here with the following operators in precedence order:</span></span>

|                <span data-ttu-id="cd1ed-161">OPERATOR</span><span class="sxs-lookup"><span data-stu-id="cd1ed-161">OPERATOR</span></span>                 |           <span data-ttu-id="cd1ed-162">REFERÊNCIA</span><span class="sxs-lookup"><span data-stu-id="cd1ed-162">REFERENCE</span></span>            |
| --------------------------------------- | ------------------------------ |
| `-band -bnot -bor -bxor -shr -shl`      | <span data-ttu-id="cd1ed-163">[about_Arithmetic_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-163">[about_Arithmetic_Operators][]</span></span> |
| `-and -or -xor`                         | <span data-ttu-id="cd1ed-164">[about_Logical_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-164">[about_Logical_Operators][]</span></span>    |

<span data-ttu-id="cd1ed-165">Os itens a seguir não são operadores verdadeiros.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-165">The following items are not true operators.</span></span> <span data-ttu-id="cd1ed-166">Eles fazem parte da sintaxe de comando do PowerShell, não da sintaxe de expressão.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-166">They are part of PowerShell's command syntax, not expression syntax.</span></span> <span data-ttu-id="cd1ed-167">A atribuição é sempre a última ação que acontece.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-167">Assignment is always the last action that happens.</span></span>

|                <span data-ttu-id="cd1ed-168">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cd1ed-168">SYNTAX</span></span>                   |           <span data-ttu-id="cd1ed-169">REFERÊNCIA</span><span class="sxs-lookup"><span data-stu-id="cd1ed-169">REFERENCE</span></span>            |
| --------------------------------------- | ------------------------------ |
| <span data-ttu-id="cd1ed-170">`.` (ponto-fonte)</span><span class="sxs-lookup"><span data-stu-id="cd1ed-170">`.` (dot-source)</span></span>                        | <span data-ttu-id="cd1ed-171">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-171">[about_Operators][]</span></span>            |
| <span data-ttu-id="cd1ed-172">`&` ligação</span><span class="sxs-lookup"><span data-stu-id="cd1ed-172">`&` (call)</span></span>                              | <span data-ttu-id="cd1ed-173">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-173">[about_Operators][]</span></span>            |
| <span data-ttu-id="cd1ed-174">`? <if-true> : <if-false>` (Operador ternário)</span><span class="sxs-lookup"><span data-stu-id="cd1ed-174">`? <if-true> : <if-false>` (Ternary operator)</span></span> | <span data-ttu-id="cd1ed-175">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-175">[about_Operators][]</span></span>      |
| <span data-ttu-id="cd1ed-176">`??` (operador NULL-)</span><span class="sxs-lookup"><span data-stu-id="cd1ed-176">`??` (null-coalese operator)</span></span>            | <span data-ttu-id="cd1ed-177">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-177">[about_Operators][]</span></span>            |
| <span data-ttu-id="cd1ed-178"><code>&#124;</code> (operador de pipeline)</span><span class="sxs-lookup"><span data-stu-id="cd1ed-178"><code>&#124;</code> (pipeline operator)</span></span> | <span data-ttu-id="cd1ed-179">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-179">[about_Operators][]</span></span>            |
| `> >> 2> 2>> 2>&1`                      | <span data-ttu-id="cd1ed-180">[about_Redirection][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-180">[about_Redirection][]</span></span>          |
| <span data-ttu-id="cd1ed-181"><code>&& &#124;&#124;</code> (operadores de cadeia de pipeline)</span><span class="sxs-lookup"><span data-stu-id="cd1ed-181"><code>&& &#124;&#124;</code> (pipeline chain operators)</span></span> | <span data-ttu-id="cd1ed-182">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-182">[about_Operators][]</span></span> |
| `= += -= *= /= %= ??=`                  | <span data-ttu-id="cd1ed-183">[about_Assignment_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-183">[about_Assignment_Operators][]</span></span> |

## <a name="examples"></a><span data-ttu-id="cd1ed-184">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="cd1ed-184">EXAMPLES</span></span>

<span data-ttu-id="cd1ed-185">Os dois comandos a seguir mostram os operadores aritméticos e o efeito de usar parênteses para forçar o PowerShell a avaliar a parte incluída da expressão primeiro.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-185">The following two commands show the arithmetic operators and the effect of using parentheses to force PowerShell to evaluate the enclosed part of the expression first.</span></span>

```powershell
PS> 2 + 3 * 4
14

PS> (2 + 3) * 4
20
```

<span data-ttu-id="cd1ed-186">O exemplo a seguir obtém os arquivos de texto somente leitura do diretório local e os salva na `$read_only` variável.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-186">The following example gets the read-only text files from the local directory and saves them in the `$read_only` variable.</span></span>

```powershell
$read_only = Get-ChildItem *.txt | Where-Object {$_.isReadOnly}
```

<span data-ttu-id="cd1ed-187">É equivalente ao exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-187">It is equivalent to the following example.</span></span>

```powershell
$read_only = ( Get-ChildItem *.txt | Where-Object {$_.isReadOnly} )
```

<span data-ttu-id="cd1ed-188">Como o operador de pipeline ( `|` ) tem uma precedência mais alta do que o operador de atribuição ( `=` ), os arquivos que o `Get-ChildItem` cmdlet obtém são enviados para o `Where-Object` cmdlet para filtragem antes de serem atribuídos à `$read_only` variável.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-188">Because the pipeline operator (`|`) has a higher precedence than the assignment operator (`=`), the files that the `Get-ChildItem` cmdlet gets are sent to the `Where-Object` cmdlet for filtering before they are assigned to the `$read_only` variable.</span></span>

<span data-ttu-id="cd1ed-189">O exemplo a seguir demonstra que o operador de índice tem precedência sobre o operador cast.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-189">The following example demonstrates that the index operator takes precedence over the cast operator.</span></span>

<span data-ttu-id="cd1ed-190">Essa expressão cria uma matriz de três cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-190">This expression creates an array of three strings.</span></span> <span data-ttu-id="cd1ed-191">Em seguida, ele usa o operador de índice com um valor de 0 para selecionar o primeiro objeto na matriz, que é a primeira cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-191">Then, it uses the index operator with a value of 0 to select the first object in the array, which is the first string.</span></span> <span data-ttu-id="cd1ed-192">Por fim, ele converte o objeto selecionado como uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-192">Finally, it casts the selected object as a string.</span></span> <span data-ttu-id="cd1ed-193">Nesse caso, a conversão não tem nenhum efeito.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-193">In this case, the cast has no effect.</span></span>

```powershell
PS> [string]@('Windows','PowerShell','2.0')[0]
Windows
```

<span data-ttu-id="cd1ed-194">Essa expressão usa parênteses para forçar a operação de conversão a ocorrer antes da seleção de índice.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-194">This expression uses parentheses to force the cast operation to occur before the index selection.</span></span> <span data-ttu-id="cd1ed-195">Como resultado, toda a matriz é convertida como uma cadeia de caracteres (única).</span><span class="sxs-lookup"><span data-stu-id="cd1ed-195">As a result, the entire array is cast as a (single) string.</span></span> <span data-ttu-id="cd1ed-196">Em seguida, o operador de índice seleciona o primeiro item na matriz de cadeia de caracteres, que é o primeiro caractere.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-196">Then, the index operator selects the first item in the string array, which is the first character.</span></span>

```powershell
PS> ([string]@('Windows','PowerShell','2.0'))[0]
W
```

<span data-ttu-id="cd1ed-197">No exemplo a seguir, como o `-gt` operador (maior que) tem uma precedência mais alta do que o `-and` operador (and lógico), o resultado da expressão é false.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-197">In the following example, because the `-gt` (greater-than) operator has a higher precedence than the `-and` (logical AND) operator, the result of the expression is FALSE.</span></span>

```powershell
PS> 2 -gt 4 -and 1
False
```

<span data-ttu-id="cd1ed-198">É equivalente à expressão a seguir.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-198">It is equivalent to the following expression.</span></span>

```powershell
PS> (2 -gt 4) -and 1
False
```

<span data-ttu-id="cd1ed-199">Se o operador and tiver precedência mais alta, a resposta seria TRUE.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-199">If the -and operator had higher precedence, the answer would be TRUE.</span></span>

```powershell
PS> 2 -gt (4 -and 1)
True
```

<span data-ttu-id="cd1ed-200">No entanto, este exemplo demonstra um princípio importante do gerenciamento de precedência de operador.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-200">However, this example demonstrates an important principle of managing operator precedence.</span></span> <span data-ttu-id="cd1ed-201">Quando uma expressão é difícil para as pessoas interpretarem, use parênteses para forçar a ordem de avaliação, mesmo quando ela força a precedência de operador padrão.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-201">When an expression is difficult for people to interpret, use parentheses to force the evaluation order, even when it forces the default operator precedence.</span></span> <span data-ttu-id="cd1ed-202">Os parênteses tornam suas intenções claras para as pessoas que estão lendo e mantendo seus scripts.</span><span class="sxs-lookup"><span data-stu-id="cd1ed-202">The parentheses make your intentions clear to people who are reading and maintaining your scripts.</span></span>

## <a name="see-also"></a><span data-ttu-id="cd1ed-203">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="cd1ed-203">SEE ALSO</span></span>

<span data-ttu-id="cd1ed-204">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-204">[about_Operators][]</span></span>

<span data-ttu-id="cd1ed-205">[about_Assignment_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-205">[about_Assignment_Operators][]</span></span>

<span data-ttu-id="cd1ed-206">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-206">[about_Comparison_Operators][]</span></span>

<span data-ttu-id="cd1ed-207">[about_Arithmetic_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-207">[about_Arithmetic_Operators][]</span></span>

<span data-ttu-id="cd1ed-208">[about_Join][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-208">[about_Join][]</span></span>

<span data-ttu-id="cd1ed-209">[about_Redirection][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-209">[about_Redirection][]</span></span>

<span data-ttu-id="cd1ed-210">[about_Scopes][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-210">[about_Scopes][]</span></span>

<span data-ttu-id="cd1ed-211">[about_Split][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-211">[about_Split][]</span></span>

<span data-ttu-id="cd1ed-212">[about_Type_Operators][]</span><span class="sxs-lookup"><span data-stu-id="cd1ed-212">[about_Type_Operators][]</span></span>

<!-- reference links -->
[about_Arithmetic_Operators]: about_Arithmetic_Operators.md
[about_Assignment_Operators]: about_Assignment_Operators.md
[about_Comparison_Operators]: about_Comparison_Operators.md
[about_Join]: about_Join.md
[about_Logical_Operators]: about_logical_operators.md
[about_Operators]: about_Operators.md
[about_Redirection]: about_Redirection.md
[about_Scopes]: about_Scopes.md
[about_Split]: about_Split.md
[about_Type_Operators]: about_Type_Operators.md
