---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-expression?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Expression
ms.openlocfilehash: f915a5741ed5c63206da3c35f5322508515bd566
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193556"
---
# <span data-ttu-id="c3a49-103">Invoke-Expression</span><span class="sxs-lookup"><span data-stu-id="c3a49-103">Invoke-Expression</span></span>

## <span data-ttu-id="c3a49-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="c3a49-104">SYNOPSIS</span></span>
<span data-ttu-id="c3a49-105">Executa comandos ou expressões no computador local.</span><span class="sxs-lookup"><span data-stu-id="c3a49-105">Runs commands or expressions on the local computer.</span></span>

## <span data-ttu-id="c3a49-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c3a49-106">SYNTAX</span></span>

```
Invoke-Expression [-Command] <String> [<CommonParameters>]
```

## <span data-ttu-id="c3a49-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c3a49-107">DESCRIPTION</span></span>

<span data-ttu-id="c3a49-108">O `Invoke-Expression` cmdlet avalia ou executa uma cadeia de caracteres especificada como um comando e retorna os resultados da expressão ou do comando.</span><span class="sxs-lookup"><span data-stu-id="c3a49-108">The `Invoke-Expression` cmdlet evaluates or runs a specified string as a command and returns the results of the expression or command.</span></span> <span data-ttu-id="c3a49-109">Sem `Invoke-Expression` , uma cadeia de caracteres enviada na linha de comando é retornada (ecoada) inalterada.</span><span class="sxs-lookup"><span data-stu-id="c3a49-109">Without `Invoke-Expression`, a string submitted at the command line is returned (echoed) unchanged.</span></span>

<span data-ttu-id="c3a49-110">As expressões são avaliadas e executadas no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="c3a49-110">Expressions are evaluated and run in the current scope.</span></span> <span data-ttu-id="c3a49-111">Para obter mais informações, consulte [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="c3a49-111">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

> [!CAUTION]
> <span data-ttu-id="c3a49-112">Tome precauções razoáveis ao usar o `Invoke-Expression` cmdlet em scripts.</span><span class="sxs-lookup"><span data-stu-id="c3a49-112">Take reasonable precautions when using the `Invoke-Expression` cmdlet in scripts.</span></span> <span data-ttu-id="c3a49-113">Ao usar `Invoke-Expression` o para executar um comando que o usuário insere, verifique se o comando é seguro para ser executado antes de executá-lo.</span><span class="sxs-lookup"><span data-stu-id="c3a49-113">When using `Invoke-Expression` to run a command that the user enters, verify that the command is safe to run before running it.</span></span> <span data-ttu-id="c3a49-114">Em geral, é melhor criar seu script com opções predefinidas de entrada, em vez de permitir a entrada de forma livre.</span><span class="sxs-lookup"><span data-stu-id="c3a49-114">In general, it is best to design your script with predefined input options, rather than allowing freeform input.</span></span>

## <span data-ttu-id="c3a49-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="c3a49-115">EXAMPLES</span></span>

### <span data-ttu-id="c3a49-116">Exemplo 1: avaliar uma expressão</span><span class="sxs-lookup"><span data-stu-id="c3a49-116">Example 1: Evaluate an expression</span></span>

```powershell
$Command = "Get-Process"
$Command
```

```Output
Get-Process
```

```powershell
Invoke-Expression $Command
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id   ProcessName
-------  ------    -----      ----- -----   ------     --   -----------
296       4       1572       1956    20       0.53     1348   AdtAgent
270       6       1328       800     34       0.06     2396   alg
67        2       620        484     20       0.22     716    ati2evxx
1060      15      12904      11840   74       11.48    892    CcmExec
1400      33      25280      37544   223      38.44    2564   communicator
...
```

<span data-ttu-id="c3a49-117">Este exemplo demonstra o uso de `Invoke-Expression` para avaliar uma expressão.</span><span class="sxs-lookup"><span data-stu-id="c3a49-117">This example demonstrates the use of `Invoke-Expression` to evaluate an expression.</span></span> <span data-ttu-id="c3a49-118">Sem `Invoke-Expression` , a expressão é impressa, mas não avaliada.</span><span class="sxs-lookup"><span data-stu-id="c3a49-118">Without `Invoke-Expression`, the expression is printed, but not evaluated.</span></span>

<span data-ttu-id="c3a49-119">O primeiro comando atribui um valor de `Get-Process` (uma cadeia de caracteres) à `$Command` variável.</span><span class="sxs-lookup"><span data-stu-id="c3a49-119">The first command assigns a value of `Get-Process` (a string) to the `$Command` variable.</span></span>

<span data-ttu-id="c3a49-120">O segundo comando mostra o efeito de digitar o nome da variável na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="c3a49-120">The second command shows the effect of typing the variable name at the command line.</span></span> <span data-ttu-id="c3a49-121">O PowerShell ecoa a cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="c3a49-121">PowerShell echoes the string.</span></span>

<span data-ttu-id="c3a49-122">O terceiro comando usa `Invoke-Expression` para avaliar a cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="c3a49-122">The third command uses `Invoke-Expression` to evaluate the string.</span></span>

### <span data-ttu-id="c3a49-123">Exemplo 2: executar um script no computador local</span><span class="sxs-lookup"><span data-stu-id="c3a49-123">Example 2: Run a script on the local computer</span></span>

```powershell
Invoke-Expression -Command "C:\ps-test\testscript.ps1"
"C:\ps-test\testscript.ps1" | Invoke-Expression
```

<span data-ttu-id="c3a49-124">Esses comandos usam `Invoke-Expression` para executar um script, TestScript.ps1, no computador local.</span><span class="sxs-lookup"><span data-stu-id="c3a49-124">These commands use `Invoke-Expression` to run a script, TestScript.ps1, on the local computer.</span></span> <span data-ttu-id="c3a49-125">Os dois comandos são equivalentes.</span><span class="sxs-lookup"><span data-stu-id="c3a49-125">The two commands are equivalent.</span></span> <span data-ttu-id="c3a49-126">O primeiro usa o parâmetro **Command** para especificar o comando a ser executado.</span><span class="sxs-lookup"><span data-stu-id="c3a49-126">The first uses the **Command** parameter to specify the command to run.</span></span>
<span data-ttu-id="c3a49-127">O segundo usa um operador de pipeline ( `|` ) para enviar a cadeia de caracteres de comando para `Invoke-Expression` .</span><span class="sxs-lookup"><span data-stu-id="c3a49-127">The second uses a pipeline operator (`|`) to send the command string to `Invoke-Expression`.</span></span>

### <span data-ttu-id="c3a49-128">Exemplo 3: executar um comando em uma variável</span><span class="sxs-lookup"><span data-stu-id="c3a49-128">Example 3: Run a command in a variable</span></span>

```powershell
$Command = 'Get-Process | where {$_.cpu -gt 1000}'
Invoke-Expression $Command
```

<span data-ttu-id="c3a49-129">Este exemplo executa uma cadeia de caracteres de comando que é salva na `$Command` variável.</span><span class="sxs-lookup"><span data-stu-id="c3a49-129">This example runs a command string that is saved in the `$Command` variable.</span></span>

<span data-ttu-id="c3a49-130">A cadeia de caracteres de comando é colocada entre aspas simples porque inclui uma variável, `$_` , que representa o objeto atual.</span><span class="sxs-lookup"><span data-stu-id="c3a49-130">The command string is enclosed in single quotation marks because it includes a variable, `$_`, which represents the current object.</span></span> <span data-ttu-id="c3a49-131">Se ele fosse colocado entre aspas duplas, a `$_` variável seria substituída por seu valor antes de ser salva na `$Command` variável.</span><span class="sxs-lookup"><span data-stu-id="c3a49-131">If it were enclosed in double quotation marks, the `$_` variable would be replaced by its value before it was saved in the `$Command` variable.</span></span>

### <span data-ttu-id="c3a49-132">Exemplo 4: obter e executar um exemplo de ajuda de cmdlet</span><span class="sxs-lookup"><span data-stu-id="c3a49-132">Example 4: Get and run a cmdlet Help example</span></span>

```powershell
$Cmdlet_name = "Get-EventLog"
$Example_number = 1
$Example_code = (Get-Help $Cmdlet_name).examples.example[($Example_number-1)].code
Invoke-Expression $Example_code
```

<span data-ttu-id="c3a49-133">Esse comando recupera e executa o primeiro exemplo no `Get-EventLog` tópico de ajuda do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c3a49-133">This command retrieves and runs the first example in the `Get-EventLog` cmdlet Help topic.</span></span>

<span data-ttu-id="c3a49-134">Para executar um exemplo de um cmdlet diferente, altere o valor da `$Cmdlet_name` variável para o nome do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c3a49-134">To run an example of a different cmdlet, change the value of the `$Cmdlet_name` variable to the name of the cmdlet.</span></span> <span data-ttu-id="c3a49-135">E altere a `$Example_number` variável para o número de exemplo que você deseja executar.</span><span class="sxs-lookup"><span data-stu-id="c3a49-135">And, change the `$Example_number` variable to the example number you want to run.</span></span> <span data-ttu-id="c3a49-136">O comando falhará se o número de exemplo não for válido.</span><span class="sxs-lookup"><span data-stu-id="c3a49-136">The command fails if the example number is not valid.</span></span>

## <span data-ttu-id="c3a49-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c3a49-137">PARAMETERS</span></span>

### <span data-ttu-id="c3a49-138">-Command</span><span class="sxs-lookup"><span data-stu-id="c3a49-138">-Command</span></span>

<span data-ttu-id="c3a49-139">Especifica o comando ou expressão a executar.</span><span class="sxs-lookup"><span data-stu-id="c3a49-139">Specifies the command or expression to run.</span></span> <span data-ttu-id="c3a49-140">Digite o comando ou expressão ou insira uma variável que contenha o comando ou expressão.</span><span class="sxs-lookup"><span data-stu-id="c3a49-140">Type the command or expression or enter a variable that contains the command or expression.</span></span> <span data-ttu-id="c3a49-141">O parâmetro **Command** é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="c3a49-141">The **Command** parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c3a49-142">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c3a49-142">CommonParameters</span></span>

<span data-ttu-id="c3a49-143">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c3a49-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c3a49-144">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="c3a49-144">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="c3a49-145">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="c3a49-145">INPUTS</span></span>

### <span data-ttu-id="c3a49-146">System. String ou PSObject</span><span class="sxs-lookup"><span data-stu-id="c3a49-146">System.String or PSObject</span></span>

<span data-ttu-id="c3a49-147">É possível canalizar um objeto que representa o comando para `Invoke-Expression` .</span><span class="sxs-lookup"><span data-stu-id="c3a49-147">You can pipe an object that represents the command to `Invoke-Expression`.</span></span>
<span data-ttu-id="c3a49-148">Use a `$Input` variável automática para representar os objetos de entrada no comando.</span><span class="sxs-lookup"><span data-stu-id="c3a49-148">Use the `$Input` automatic variable to represent the input objects in the command.</span></span>

## <span data-ttu-id="c3a49-149">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="c3a49-149">OUTPUTS</span></span>

### <span data-ttu-id="c3a49-150">PSObject</span><span class="sxs-lookup"><span data-stu-id="c3a49-150">PSObject</span></span>

<span data-ttu-id="c3a49-151">Retorna a saída gerada pelo comando invocado (o valor do parâmetro de **comando** ).</span><span class="sxs-lookup"><span data-stu-id="c3a49-151">Returns the output that is generated by the invoked command (the value of the **Command** parameter).</span></span>

## <span data-ttu-id="c3a49-152">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="c3a49-152">NOTES</span></span>

<span data-ttu-id="c3a49-153">Na maioria dos casos, você invoca expressões usando o operador de chamada do PowerShell e obtém os mesmos resultados.</span><span class="sxs-lookup"><span data-stu-id="c3a49-153">In most cases, you invoke expressions using PowerShell's call operator and achieve the same results.</span></span>
<span data-ttu-id="c3a49-154">O operador de chamada é um método mais seguro.</span><span class="sxs-lookup"><span data-stu-id="c3a49-154">The call operator is a safer method.</span></span> <span data-ttu-id="c3a49-155">Para obter mais informações, consulte [about_Operators](../microsoft.powershell.core/about/about_operators.md#call-operator-).</span><span class="sxs-lookup"><span data-stu-id="c3a49-155">For more information, see [about_Operators](../microsoft.powershell.core/about/about_operators.md#call-operator-).</span></span>

## <span data-ttu-id="c3a49-156">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="c3a49-156">RELATED LINKS</span></span>

[<span data-ttu-id="c3a49-157">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="c3a49-157">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="c3a49-158">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="c3a49-158">about_Scopes</span></span>](../Microsoft.PowerShell.Core/About/about_Scopes.md)

