---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-expression?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Expression
ms.openlocfilehash: 65ccc37b1c9122d54f3caf85f4546e1381558ca9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597605"
---
# <span data-ttu-id="dfd22-102">Invoke-Expression</span><span class="sxs-lookup"><span data-stu-id="dfd22-102">Invoke-Expression</span></span>

## <span data-ttu-id="dfd22-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="dfd22-103">SYNOPSIS</span></span>
<span data-ttu-id="dfd22-104">Executa comandos ou expressões no computador local.</span><span class="sxs-lookup"><span data-stu-id="dfd22-104">Runs commands or expressions on the local computer.</span></span>

## <span data-ttu-id="dfd22-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dfd22-105">SYNTAX</span></span>

```
Invoke-Expression [-Command] <String> [<CommonParameters>]
```

## <span data-ttu-id="dfd22-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="dfd22-106">DESCRIPTION</span></span>

<span data-ttu-id="dfd22-107">O `Invoke-Expression` cmdlet avalia ou executa uma cadeia de caracteres especificada como um comando e retorna os resultados da expressão ou do comando.</span><span class="sxs-lookup"><span data-stu-id="dfd22-107">The `Invoke-Expression` cmdlet evaluates or runs a specified string as a command and returns the results of the expression or command.</span></span> <span data-ttu-id="dfd22-108">Sem `Invoke-Expression` , uma cadeia de caracteres enviada na linha de comando é retornada (ecoada) inalterada.</span><span class="sxs-lookup"><span data-stu-id="dfd22-108">Without `Invoke-Expression`, a string submitted at the command line is returned (echoed) unchanged.</span></span>

<span data-ttu-id="dfd22-109">As expressões são avaliadas e executadas no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="dfd22-109">Expressions are evaluated and run in the current scope.</span></span> <span data-ttu-id="dfd22-110">Para obter mais informações, consulte [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="dfd22-110">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

> [!CAUTION]
> <span data-ttu-id="dfd22-111">Tome precauções razoáveis ao usar o `Invoke-Expression` cmdlet em scripts.</span><span class="sxs-lookup"><span data-stu-id="dfd22-111">Take reasonable precautions when using the `Invoke-Expression` cmdlet in scripts.</span></span> <span data-ttu-id="dfd22-112">Ao usar `Invoke-Expression` o para executar um comando que o usuário insere, verifique se o comando é seguro para ser executado antes de executá-lo.</span><span class="sxs-lookup"><span data-stu-id="dfd22-112">When using `Invoke-Expression` to run a command that the user enters, verify that the command is safe to run before running it.</span></span> <span data-ttu-id="dfd22-113">Em geral, é melhor criar seu script com opções predefinidas de entrada, em vez de permitir a entrada de forma livre.</span><span class="sxs-lookup"><span data-stu-id="dfd22-113">In general, it is best to design your script with predefined input options, rather than allowing freeform input.</span></span>

## <span data-ttu-id="dfd22-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="dfd22-114">EXAMPLES</span></span>

### <span data-ttu-id="dfd22-115">Exemplo 1: avaliar uma expressão</span><span class="sxs-lookup"><span data-stu-id="dfd22-115">Example 1: Evaluate an expression</span></span>

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

<span data-ttu-id="dfd22-116">Este exemplo demonstra o uso de `Invoke-Expression` para avaliar uma expressão.</span><span class="sxs-lookup"><span data-stu-id="dfd22-116">This example demonstrates the use of `Invoke-Expression` to evaluate an expression.</span></span> <span data-ttu-id="dfd22-117">Sem `Invoke-Expression` , a expressão é impressa, mas não avaliada.</span><span class="sxs-lookup"><span data-stu-id="dfd22-117">Without `Invoke-Expression`, the expression is printed, but not evaluated.</span></span>

<span data-ttu-id="dfd22-118">O primeiro comando atribui um valor de `Get-Process` (uma cadeia de caracteres) à `$Command` variável.</span><span class="sxs-lookup"><span data-stu-id="dfd22-118">The first command assigns a value of `Get-Process` (a string) to the `$Command` variable.</span></span>

<span data-ttu-id="dfd22-119">O segundo comando mostra o efeito de digitar o nome da variável na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="dfd22-119">The second command shows the effect of typing the variable name at the command line.</span></span> <span data-ttu-id="dfd22-120">O PowerShell ecoa a cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="dfd22-120">PowerShell echoes the string.</span></span>

<span data-ttu-id="dfd22-121">O terceiro comando usa `Invoke-Expression` para avaliar a cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="dfd22-121">The third command uses `Invoke-Expression` to evaluate the string.</span></span>

### <span data-ttu-id="dfd22-122">Exemplo 2: executar um script no computador local</span><span class="sxs-lookup"><span data-stu-id="dfd22-122">Example 2: Run a script on the local computer</span></span>

```powershell
Invoke-Expression -Command "C:\ps-test\testscript.ps1"
"C:\ps-test\testscript.ps1" | Invoke-Expression
```

<span data-ttu-id="dfd22-123">Esses comandos usam `Invoke-Expression` para executar um script, TestScript.ps1, no computador local.</span><span class="sxs-lookup"><span data-stu-id="dfd22-123">These commands use `Invoke-Expression` to run a script, TestScript.ps1, on the local computer.</span></span> <span data-ttu-id="dfd22-124">Os dois comandos são equivalentes.</span><span class="sxs-lookup"><span data-stu-id="dfd22-124">The two commands are equivalent.</span></span> <span data-ttu-id="dfd22-125">O primeiro usa o parâmetro **Command** para especificar o comando a ser executado.</span><span class="sxs-lookup"><span data-stu-id="dfd22-125">The first uses the **Command** parameter to specify the command to run.</span></span>
<span data-ttu-id="dfd22-126">O segundo usa um operador de pipeline ( `|` ) para enviar a cadeia de caracteres de comando para `Invoke-Expression` .</span><span class="sxs-lookup"><span data-stu-id="dfd22-126">The second uses a pipeline operator (`|`) to send the command string to `Invoke-Expression`.</span></span>

### <span data-ttu-id="dfd22-127">Exemplo 3: executar um comando em uma variável</span><span class="sxs-lookup"><span data-stu-id="dfd22-127">Example 3: Run a command in a variable</span></span>

```powershell
$Command = 'Get-Process | where {$_.cpu -gt 1000}'
Invoke-Expression $Command
```

<span data-ttu-id="dfd22-128">Este exemplo executa uma cadeia de caracteres de comando que é salva na `$Command` variável.</span><span class="sxs-lookup"><span data-stu-id="dfd22-128">This example runs a command string that is saved in the `$Command` variable.</span></span>

<span data-ttu-id="dfd22-129">A cadeia de caracteres de comando é colocada entre aspas simples porque inclui uma variável, `$_` , que representa o objeto atual.</span><span class="sxs-lookup"><span data-stu-id="dfd22-129">The command string is enclosed in single quotation marks because it includes a variable, `$_`, which represents the current object.</span></span> <span data-ttu-id="dfd22-130">Se ele fosse colocado entre aspas duplas, a `$_` variável seria substituída por seu valor antes de ser salva na `$Command` variável.</span><span class="sxs-lookup"><span data-stu-id="dfd22-130">If it were enclosed in double quotation marks, the `$_` variable would be replaced by its value before it was saved in the `$Command` variable.</span></span>

### <span data-ttu-id="dfd22-131">Exemplo 4: obter e executar um exemplo de ajuda de cmdlet</span><span class="sxs-lookup"><span data-stu-id="dfd22-131">Example 4: Get and run a cmdlet Help example</span></span>

```powershell
$Cmdlet_name = "Get-EventLog"
$Example_number = 1
$Example_code = (Get-Help $Cmdlet_name).examples.example[($Example_number-1)].code
Invoke-Expression $Example_code
```

<span data-ttu-id="dfd22-132">Esse comando recupera e executa o primeiro exemplo no `Get-EventLog` tópico de ajuda do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="dfd22-132">This command retrieves and runs the first example in the `Get-EventLog` cmdlet Help topic.</span></span>

<span data-ttu-id="dfd22-133">Para executar um exemplo de um cmdlet diferente, altere o valor da `$Cmdlet_name` variável para o nome do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="dfd22-133">To run an example of a different cmdlet, change the value of the `$Cmdlet_name` variable to the name of the cmdlet.</span></span> <span data-ttu-id="dfd22-134">E altere a `$Example_number` variável para o número de exemplo que você deseja executar.</span><span class="sxs-lookup"><span data-stu-id="dfd22-134">And, change the `$Example_number` variable to the example number you want to run.</span></span> <span data-ttu-id="dfd22-135">O comando falhará se o número de exemplo não for válido.</span><span class="sxs-lookup"><span data-stu-id="dfd22-135">The command fails if the example number is not valid.</span></span>

## <span data-ttu-id="dfd22-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dfd22-136">PARAMETERS</span></span>

### <span data-ttu-id="dfd22-137">-Command</span><span class="sxs-lookup"><span data-stu-id="dfd22-137">-Command</span></span>

<span data-ttu-id="dfd22-138">Especifica o comando ou expressão a executar.</span><span class="sxs-lookup"><span data-stu-id="dfd22-138">Specifies the command or expression to run.</span></span> <span data-ttu-id="dfd22-139">Digite o comando ou expressão ou insira uma variável que contenha o comando ou expressão.</span><span class="sxs-lookup"><span data-stu-id="dfd22-139">Type the command or expression or enter a variable that contains the command or expression.</span></span> <span data-ttu-id="dfd22-140">O parâmetro **Command** é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="dfd22-140">The **Command** parameter is required.</span></span>

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

### <span data-ttu-id="dfd22-141">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="dfd22-141">CommonParameters</span></span>

<span data-ttu-id="dfd22-142">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="dfd22-142">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dfd22-143">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="dfd22-143">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="dfd22-144">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="dfd22-144">INPUTS</span></span>

### <span data-ttu-id="dfd22-145">System. String ou PSObject</span><span class="sxs-lookup"><span data-stu-id="dfd22-145">System.String or PSObject</span></span>

<span data-ttu-id="dfd22-146">É possível canalizar um objeto que representa o comando para `Invoke-Expression` .</span><span class="sxs-lookup"><span data-stu-id="dfd22-146">You can pipe an object that represents the command to `Invoke-Expression`.</span></span>
<span data-ttu-id="dfd22-147">Use a `$Input` variável automática para representar os objetos de entrada no comando.</span><span class="sxs-lookup"><span data-stu-id="dfd22-147">Use the `$Input` automatic variable to represent the input objects in the command.</span></span>

## <span data-ttu-id="dfd22-148">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="dfd22-148">OUTPUTS</span></span>

### <span data-ttu-id="dfd22-149">PSObject</span><span class="sxs-lookup"><span data-stu-id="dfd22-149">PSObject</span></span>

<span data-ttu-id="dfd22-150">Retorna a saída gerada pelo comando invocado (o valor do parâmetro de **comando** ).</span><span class="sxs-lookup"><span data-stu-id="dfd22-150">Returns the output that is generated by the invoked command (the value of the **Command** parameter).</span></span>

## <span data-ttu-id="dfd22-151">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="dfd22-151">NOTES</span></span>

<span data-ttu-id="dfd22-152">Na maioria dos casos, você invoca expressões usando o operador de chamada do PowerShell e obtém os mesmos resultados.</span><span class="sxs-lookup"><span data-stu-id="dfd22-152">In most cases, you invoke expressions using PowerShell's call operator and achieve the same results.</span></span>
<span data-ttu-id="dfd22-153">O operador de chamada é um método mais seguro.</span><span class="sxs-lookup"><span data-stu-id="dfd22-153">The call operator is a safer method.</span></span> <span data-ttu-id="dfd22-154">Para obter mais informações, consulte [about_Operators](../microsoft.powershell.core/about/about_operators.md#call-operator-).</span><span class="sxs-lookup"><span data-stu-id="dfd22-154">For more information, see [about_Operators](../microsoft.powershell.core/about/about_operators.md#call-operator-).</span></span>

## <span data-ttu-id="dfd22-155">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="dfd22-155">RELATED LINKS</span></span>

[<span data-ttu-id="dfd22-156">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="dfd22-156">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="dfd22-157">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="dfd22-157">about_Scopes</span></span>](../Microsoft.PowerShell.Core/About/about_Scopes.md)

