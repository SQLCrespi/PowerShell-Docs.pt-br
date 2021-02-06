---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/24/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-psbreakpoint?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSBreakpoint
ms.openlocfilehash: 5e2bdf435bf7cb9da3f31712c346beff29a11baf
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603777"
---
# <span data-ttu-id="cad6b-102">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="cad6b-102">Set-PSBreakpoint</span></span>

## <span data-ttu-id="cad6b-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="cad6b-103">SYNOPSIS</span></span>
<span data-ttu-id="cad6b-104">Define um ponto de interrupção em uma linha, um comando ou uma variável.</span><span class="sxs-lookup"><span data-stu-id="cad6b-104">Sets a breakpoint on a line, command, or variable.</span></span>

## <span data-ttu-id="cad6b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cad6b-105">SYNTAX</span></span>

### <span data-ttu-id="cad6b-106">Linha (padrão)</span><span class="sxs-lookup"><span data-stu-id="cad6b-106">Line (Default)</span></span>

```
Set-PSBreakpoint [-Action <ScriptBlock>] [[-Column] <Int32>] [-Line] <Int32[]> [-Script] <String[]>
 [<CommonParameters>]
```

### <span data-ttu-id="cad6b-107">Comando</span><span class="sxs-lookup"><span data-stu-id="cad6b-107">Command</span></span>

```
Set-PSBreakpoint [-Action <ScriptBlock>] -Command <String[]> [[-Script] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="cad6b-108">Variável</span><span class="sxs-lookup"><span data-stu-id="cad6b-108">Variable</span></span>

```
Set-PSBreakpoint [-Action <ScriptBlock>] [[-Script] <String[]>] -Variable <String[]>
 [-Mode <VariableAccessMode>] [<CommonParameters>]
```

## <span data-ttu-id="cad6b-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cad6b-109">DESCRIPTION</span></span>

<span data-ttu-id="cad6b-110">O `Set-PSBreakpoint` cmdlet define um ponto de interrupção em um script ou em qualquer comando executado na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="cad6b-110">The `Set-PSBreakpoint` cmdlet sets a breakpoint in a script or in any command run in the current session.</span></span> <span data-ttu-id="cad6b-111">Você pode usar `Set-PSBreakpoint` para definir um ponto de interrupção antes de executar um script ou executar um comando, ou durante a depuração, quando interrompido em outro ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="cad6b-111">You can use `Set-PSBreakpoint` to set a breakpoint before executing a script or running a command, or during debugging, when stopped at another breakpoint.</span></span>

<span data-ttu-id="cad6b-112">`Set-PSBreakpoint` Não é possível definir um ponto de interrupção em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="cad6b-112">`Set-PSBreakpoint` cannot set a breakpoint on a remote computer.</span></span> <span data-ttu-id="cad6b-113">Para depurar um script em um computador remoto, copie o script para o computador local e o depure localmente.</span><span class="sxs-lookup"><span data-stu-id="cad6b-113">To debug a script on a remote computer, copy the script to the local computer and then debug it locally.</span></span>

<span data-ttu-id="cad6b-114">Cada `Set-PSBreakpoint` comando cria um dos três tipos de pontos de interrupção a seguir:</span><span class="sxs-lookup"><span data-stu-id="cad6b-114">Each `Set-PSBreakpoint` command creates one of the following three types of breakpoints:</span></span>

- <span data-ttu-id="cad6b-115">Ponto de interrupção de linha – define os pontos de interrupção em coordenadas de linha e coluna específicas.</span><span class="sxs-lookup"><span data-stu-id="cad6b-115">Line breakpoint - Sets breakpoints at particular line and column coordinates.</span></span>
- <span data-ttu-id="cad6b-116">Ponto de interrupção do comando – define pontos de interrupção em comandos e funções.</span><span class="sxs-lookup"><span data-stu-id="cad6b-116">Command breakpoint - Sets breakpoints on commands and functions.</span></span>
- <span data-ttu-id="cad6b-117">Ponto de interrupção da variável – define pontos de interrupção em variáveis.</span><span class="sxs-lookup"><span data-stu-id="cad6b-117">Variable breakpoint - Sets breakpoints on variables.</span></span>

<span data-ttu-id="cad6b-118">Você pode definir um ponto de interrupção em várias linhas, comandos ou variáveis em um único `Set-PSBreakpoint` comando, mas cada `Set-PSBreakpoint` comando define apenas um tipo de ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="cad6b-118">You can set a breakpoint on multiple lines, commands, or variables in a single `Set-PSBreakpoint` command, but each `Set-PSBreakpoint` command sets only one type of breakpoint.</span></span>

<span data-ttu-id="cad6b-119">Em um ponto de interrupção, o PowerShell interrompe temporariamente a execução e dá controle ao depurador.</span><span class="sxs-lookup"><span data-stu-id="cad6b-119">At a breakpoint, PowerShell temporarily stops executing and gives control to the debugger.</span></span> <span data-ttu-id="cad6b-120">O prompt de comando muda para `DBG\>` e um conjunto de comandos do depurador se torna disponível para uso.</span><span class="sxs-lookup"><span data-stu-id="cad6b-120">The command prompt changes to `DBG\>`, and a set of debugger commands become available for use.</span></span> <span data-ttu-id="cad6b-121">No entanto, você pode usar o parâmetro **Action** para especificar uma resposta alternativa, como condições para o ponto de interrupção ou instruções para executar tarefas adicionais, como log ou diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="cad6b-121">However, you can use the **Action** parameter to specify an alternate response, such as conditions for the breakpoint or instructions to perform additional tasks such as logging or diagnostics.</span></span>

<span data-ttu-id="cad6b-122">O `Set-PSBreakpoint` cmdlet é um dos vários cmdlets projetados para depurar scripts do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cad6b-122">The `Set-PSBreakpoint` cmdlet is one of several cmdlets designed for debugging PowerShell scripts.</span></span>
<span data-ttu-id="cad6b-123">Para obter mais informações sobre o depurador do PowerShell, consulte [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).</span><span class="sxs-lookup"><span data-stu-id="cad6b-123">For more information about the PowerShell debugger, see [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).</span></span>

## <span data-ttu-id="cad6b-124">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="cad6b-124">EXAMPLES</span></span>

### <span data-ttu-id="cad6b-125">Exemplo 1: definir um ponto de interrupção em uma linha</span><span class="sxs-lookup"><span data-stu-id="cad6b-125">Example 1: Set a breakpoint on a line</span></span>

<span data-ttu-id="cad6b-126">Este exemplo define um ponto de interrupção na linha 5 no script Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="cad6b-126">This example sets a breakpoint at line 5 in the Sample.ps1 script.</span></span> <span data-ttu-id="cad6b-127">Quando o script é executado, a execução é interrompida imediatamente antes que a linha 5 seja executada.</span><span class="sxs-lookup"><span data-stu-id="cad6b-127">When the script runs, execution stops immediately before line 5 would execute.</span></span>

```powershell
Set-PSBreakpoint -Script "sample.ps1" -Line 5
```

```output
Column     : 0
Line       : 5
Action     :
Enabled    : True
HitCount   : 0
Id         : 0
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

<span data-ttu-id="cad6b-128">Quando você define um novo ponto de interrupção por número de linha, o `Set-PSBreakpoint` cmdlet gera um objeto de ponto de interrupção de linha (**System. Management. Automation. LineBreakpoint**) que inclui a ID de ponto de interrupção e a contagem de acesso.</span><span class="sxs-lookup"><span data-stu-id="cad6b-128">When you set a new breakpoint by line number, the `Set-PSBreakpoint` cmdlet generates a line breakpoint object (**System.Management.Automation.LineBreakpoint**) that includes the breakpoint ID and hit count.</span></span>

### <span data-ttu-id="cad6b-129">Exemplo 2: definir um ponto de interrupção em uma função</span><span class="sxs-lookup"><span data-stu-id="cad6b-129">Example 2: Set a breakpoint on a function</span></span>

<span data-ttu-id="cad6b-130">Este exemplo cria um ponto de interrupção de comando na `Increment` função no cmdlet Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="cad6b-130">This example creates a command breakpoint on the `Increment` function in the Sample.ps1 cmdlet.</span></span> <span data-ttu-id="cad6b-131">O script para de executar imediatamente antes de cada chamada para a função especificada.</span><span class="sxs-lookup"><span data-stu-id="cad6b-131">The script stops executing immediately before each call to the specified function.</span></span>

```powershell
Set-PSBreakpoint -Command "Increment" -Script "sample.ps1"
```

```Output
Command    : Increment
Action     :
Enabled    : True
HitCount   : 0
Id         : 1
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

<span data-ttu-id="cad6b-132">O resultado é um objeto de ponto de interrupção do comando.</span><span class="sxs-lookup"><span data-stu-id="cad6b-132">The result is a command breakpoint object.</span></span> <span data-ttu-id="cad6b-133">Antes de o script ser executado, o valor da propriedade **contagem** é 0.</span><span class="sxs-lookup"><span data-stu-id="cad6b-133">Before the script runs, the value of the **HitCount** property is 0.</span></span>

### <span data-ttu-id="cad6b-134">Exemplo 3: definir um ponto de interrupção em uma variável</span><span class="sxs-lookup"><span data-stu-id="cad6b-134">Example 3: Set a breakpoint on a variable</span></span>

<span data-ttu-id="cad6b-135">Este exemplo define um ponto de interrupção na variável de **servidor** no script Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="cad6b-135">This example sets a breakpoint on the **Server** variable in the Sample.ps1 script.</span></span> <span data-ttu-id="cad6b-136">Ele usa o parâmetro **Mode** com um valor de **ReadWrite** para interromper a execução quando o valor da variável é lido e pouco antes de o valor ser alterado.</span><span class="sxs-lookup"><span data-stu-id="cad6b-136">It uses the **Mode** parameter with a value of **ReadWrite** to stop execution when the value of the variable is read and just before the value changes.</span></span>

```powershell
Set-PSBreakpoint -Script "sample.ps1" -Variable "Server" -Mode ReadWrite
```

### <span data-ttu-id="cad6b-137">Exemplo 4: definir um ponto de interrupção em cada comando que começa com o texto especificado</span><span class="sxs-lookup"><span data-stu-id="cad6b-137">Example 4: Set a breakpoint on every command that begins with specified text</span></span>

<span data-ttu-id="cad6b-138">Este exemplo define um ponto de interrupção em cada comando no script de Sample.ps1 que começa com "Write", como `Write-Host` .</span><span class="sxs-lookup"><span data-stu-id="cad6b-138">This example sets a breakpoint on every command in the Sample.ps1 script that begins with "write", such as `Write-Host`.</span></span>

```powershell
Set-PSBreakpoint -Script Sample.ps1 -Command "write*"
```

### <span data-ttu-id="cad6b-139">Exemplo 5: definir um ponto de interrupção dependendo do valor de uma variável</span><span class="sxs-lookup"><span data-stu-id="cad6b-139">Example 5: Set a breakpoint depending on the value of a variable</span></span>

<span data-ttu-id="cad6b-140">Este exemplo interrompe a execução na `DiskTest` função no script Test.ps1 somente quando o valor da `$Disk` variável é maior que 2.</span><span class="sxs-lookup"><span data-stu-id="cad6b-140">This example stops execution at the `DiskTest` function in the Test.ps1 script only when the value of the `$Disk` variable is greater than 2.</span></span>

```powershell
Set-PSBreakpoint -Script "test.ps1" -Command "DiskTest" -Action { if ($Disk -gt 2) { break } }
```

<span data-ttu-id="cad6b-141">O valor da **ação** é um bloco de script que testa o valor da `$Disk` variável na função.</span><span class="sxs-lookup"><span data-stu-id="cad6b-141">The value of the **Action** is a script block that tests the value of the `$Disk` variable in the function.</span></span>

<span data-ttu-id="cad6b-142">A ação usará a `break` palavra-chave para interromper a execução se a condição for atendida.</span><span class="sxs-lookup"><span data-stu-id="cad6b-142">The action uses the `break` keyword to stop execution if the condition is met.</span></span> <span data-ttu-id="cad6b-143">A alternativa (e o padrão) é **continuar**.</span><span class="sxs-lookup"><span data-stu-id="cad6b-143">The alternative (and the default) is **Continue**.</span></span>

### <span data-ttu-id="cad6b-144">Exemplo 6: definir um ponto de interrupção em uma função</span><span class="sxs-lookup"><span data-stu-id="cad6b-144">Example 6: Set a breakpoint on a function</span></span>

<span data-ttu-id="cad6b-145">Este exemplo define um ponto de interrupção na `CheckLog` função.</span><span class="sxs-lookup"><span data-stu-id="cad6b-145">This example sets a breakpoint on the `CheckLog` function.</span></span> <span data-ttu-id="cad6b-146">Como o comando não especifica um script, o ponto de interrupção é definido em qualquer coisa que seja executada na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="cad6b-146">Because the command does not specify a script, the breakpoint is set on anything that runs in the current session.</span></span> <span data-ttu-id="cad6b-147">O depurador interrompe quando a função é chamada, não quando é declarada.</span><span class="sxs-lookup"><span data-stu-id="cad6b-147">The debugger breaks when the function is called, not when it is declared.</span></span>

```
PS> Set-PSBreakpoint -Command "checklog"
Id       : 0
Command  : checklog
Enabled  : True
HitCount : 0
Action   :

function CheckLog {
>> get-eventlog -log Application |
>> where {($_.source -like "TestApp") -and ($_.Message -like "*failed*")}
>>}
>>
PS> Checklog
DEBUG: Hit breakpoint(s)
DEBUG:  Function breakpoint on 'prompt:Checklog'
```

### <span data-ttu-id="cad6b-148">Exemplo 7: definir pontos de interrupção em várias linhas</span><span class="sxs-lookup"><span data-stu-id="cad6b-148">Example 7: Set breakpoints on multiple lines</span></span>

<span data-ttu-id="cad6b-149">Este exemplo define três pontos de interrupção de linha no script de Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="cad6b-149">This example sets three line breakpoints in the Sample.ps1 script.</span></span> <span data-ttu-id="cad6b-150">Ele define um ponto de interrupção na coluna 2 para cada uma das linhas especificada no script.</span><span class="sxs-lookup"><span data-stu-id="cad6b-150">It sets one breakpoint at column 2 on each of the lines specified in the script.</span></span> <span data-ttu-id="cad6b-151">A ação especificada no parâmetro **Action** aplica-se a todos os pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="cad6b-151">The action specified in the **Action** parameter applies to all breakpoints.</span></span>

```powershell
PS C:\> Set-PSBreakpoint -Script "sample.ps1" -Line 1, 14, 19 -Column 2 -Action {&(log.ps1)}
```

```Output
Column     : 2
Line       : 1
Action     :
Enabled    : True
HitCount   : 0
Id         : 6
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1


Column     : 2
Line       : 14
Action     :
Enabled    : True
HitCount   : 0
Id         : 7
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1


Column     : 2
Line       : 19
Action     :
Enabled    : True
HitCount   : 0
Id         : 8
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

## <span data-ttu-id="cad6b-152">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cad6b-152">PARAMETERS</span></span>

### <span data-ttu-id="cad6b-153">-Action</span><span class="sxs-lookup"><span data-stu-id="cad6b-153">-Action</span></span>

<span data-ttu-id="cad6b-154">Especifica comandos que são executados em cada ponto de interrupção em vez de interromper.</span><span class="sxs-lookup"><span data-stu-id="cad6b-154">Specifies commands that run at each breakpoint instead of breaking.</span></span> <span data-ttu-id="cad6b-155">Insira um bloco de script que contenha os comandos.</span><span class="sxs-lookup"><span data-stu-id="cad6b-155">Enter a script block that contains the commands.</span></span> <span data-ttu-id="cad6b-156">Você pode usar esse parâmetro para definir pontos de interrupção condicionais ou realizar outras tarefas, como teste ou registro em log.</span><span class="sxs-lookup"><span data-stu-id="cad6b-156">You can use this parameter to set conditional breakpoints or to perform other tasks, such as testing or logging.</span></span>

<span data-ttu-id="cad6b-157">Se este parâmetro é omitido, ou nenhuma ação é especificada, a execução para no ponto de interrupção e o depurador é iniciado.</span><span class="sxs-lookup"><span data-stu-id="cad6b-157">If this parameter is omitted, or no action is specified, execution stops at the breakpoint, and the debugger starts.</span></span>

<span data-ttu-id="cad6b-158">Quando o parâmetro **Action** é usado, o bloco de script Action é executado em cada ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="cad6b-158">When the **Action** parameter is used, the Action script block runs at each breakpoint.</span></span> <span data-ttu-id="cad6b-159">A execução não é interrompida a menos que o bloco de script inclua a palavra-chave Break.</span><span class="sxs-lookup"><span data-stu-id="cad6b-159">Execution does not stop unless the script block includes the Break keyword.</span></span> <span data-ttu-id="cad6b-160">Se você usar a palavra-chave Continue no bloco de script, a execução continua até o próximo ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="cad6b-160">If you use the Continue keyword in the script block, execution resumes until the next breakpoint.</span></span>

<span data-ttu-id="cad6b-161">Para obter mais informações, consulte [about_Script_Blocks](../Microsoft.PowerShell.Core/About/about_Script_Blocks.md), [about_Break](../Microsoft.PowerShell.Core/About/about_Break.md)e [about_Continue](../Microsoft.PowerShell.Core/About/about_Continue.md).</span><span class="sxs-lookup"><span data-stu-id="cad6b-161">For more information, see [about_Script_Blocks](../Microsoft.PowerShell.Core/About/about_Script_Blocks.md), [about_Break](../Microsoft.PowerShell.Core/About/about_Break.md), and [about_Continue](../Microsoft.PowerShell.Core/About/about_Continue.md).</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cad6b-162">-Coluna</span><span class="sxs-lookup"><span data-stu-id="cad6b-162">-Column</span></span>

<span data-ttu-id="cad6b-163">Especifica o número de coluna da coluna no arquivo de script em que a execução é interrompida.</span><span class="sxs-lookup"><span data-stu-id="cad6b-163">Specifies the column number of the column in the script file on which execution stops.</span></span> <span data-ttu-id="cad6b-164">Insira apenas um número de coluna.</span><span class="sxs-lookup"><span data-stu-id="cad6b-164">Enter only one column number.</span></span> <span data-ttu-id="cad6b-165">O padrão é a coluna 1.</span><span class="sxs-lookup"><span data-stu-id="cad6b-165">The default is column 1.</span></span>

<span data-ttu-id="cad6b-166">O valor da coluna é usado com o valor do parâmetro **line** para especificar o ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="cad6b-166">The Column value is used with the value of the **Line** parameter to specify the breakpoint.</span></span> <span data-ttu-id="cad6b-167">Se o parâmetro de **linha** especificar várias linhas, o parâmetro de **coluna** definirá um ponto de interrupção na coluna especificada em cada uma das linhas especificadas.</span><span class="sxs-lookup"><span data-stu-id="cad6b-167">If the **Line** parameter specifies multiple lines, the **Column** parameter sets a breakpoint at the specified column on each of the specified lines.</span></span> <span data-ttu-id="cad6b-168">O PowerShell para de executar antes da instrução ou expressão que inclui o caractere na linha especificada e na posição da coluna.</span><span class="sxs-lookup"><span data-stu-id="cad6b-168">PowerShell stops executing before the statement or expression that includes the character at the specified line and column position.</span></span>

<span data-ttu-id="cad6b-169">Colunas são contadas a partir da margem superior esquerda começando pela coluna número 1 (não a 0).</span><span class="sxs-lookup"><span data-stu-id="cad6b-169">Columns are counted from the top left margin beginning with column number 1 (not 0).</span></span> <span data-ttu-id="cad6b-170">Se especificar uma coluna que não existe no script, um erro não é declarado, mas o ponto de interrupção não é executado.</span><span class="sxs-lookup"><span data-stu-id="cad6b-170">If you specify a column that does not exist in the script, an error is not declared, but the breakpoint is never executed.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Line
Aliases:

Required: False
Position: 2
Default value: 1
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cad6b-171">-Command</span><span class="sxs-lookup"><span data-stu-id="cad6b-171">-Command</span></span>

<span data-ttu-id="cad6b-172">Define um ponto de interrupção do comando.</span><span class="sxs-lookup"><span data-stu-id="cad6b-172">Sets a command breakpoint.</span></span> <span data-ttu-id="cad6b-173">Insira nomes de cmdlet, como `Get-Process` ou nomes de função.</span><span class="sxs-lookup"><span data-stu-id="cad6b-173">Enter cmdlet names, such as `Get-Process`, or function names.</span></span> <span data-ttu-id="cad6b-174">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="cad6b-174">Wildcards are permitted.</span></span>

<span data-ttu-id="cad6b-175">A execução para antes que cada instância de cada comando seja executada.</span><span class="sxs-lookup"><span data-stu-id="cad6b-175">Execution stops just before each instance of each command is executed.</span></span> <span data-ttu-id="cad6b-176">Se o comando for uma função, a execução é interrompida toda vez que a função é chamada e a cada seção BEGIN, PROCESS e END.</span><span class="sxs-lookup"><span data-stu-id="cad6b-176">If the command is a function, execution stops each time the function is called and at each BEGIN, PROCESS, and END section.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Command
Aliases: C

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="cad6b-177">-Linha</span><span class="sxs-lookup"><span data-stu-id="cad6b-177">-Line</span></span>

<span data-ttu-id="cad6b-178">Define um ponto de interrupção em um script.</span><span class="sxs-lookup"><span data-stu-id="cad6b-178">Sets a line breakpoint in a script.</span></span> <span data-ttu-id="cad6b-179">Insira um ou mais números de linha, separados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="cad6b-179">Enter one or more line numbers, separated by commas.</span></span> <span data-ttu-id="cad6b-180">O PowerShell para imediatamente antes de executar a instrução que começa em cada uma das linhas especificadas.</span><span class="sxs-lookup"><span data-stu-id="cad6b-180">PowerShell stops immediately before executing the statement that begins on each of the specified lines.</span></span>

<span data-ttu-id="cad6b-181">Linhas são contadas a partir da margem superior esquerda do arquivo de script começando pela linha número 1 (não a 0).</span><span class="sxs-lookup"><span data-stu-id="cad6b-181">Lines are counted from the top left margin of the script file beginning with line number 1 (not 0).</span></span>
<span data-ttu-id="cad6b-182">Se especificar uma linha em branco, a execução para antes da próxima linha que não estiver em branco.</span><span class="sxs-lookup"><span data-stu-id="cad6b-182">If you specify a blank line, execution stops before the next non-blank line.</span></span> <span data-ttu-id="cad6b-183">Se a linha está fora do intervalo, o ponto de interrupção nunca é atingido.</span><span class="sxs-lookup"><span data-stu-id="cad6b-183">If the line is out of range, the breakpoint is never hit.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Line
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cad6b-184">-Mode</span><span class="sxs-lookup"><span data-stu-id="cad6b-184">-Mode</span></span>

<span data-ttu-id="cad6b-185">Especifica o modo de acesso que dispara pontos de interrupção de variável.</span><span class="sxs-lookup"><span data-stu-id="cad6b-185">Specifies the mode of access that triggers variable breakpoints.</span></span> <span data-ttu-id="cad6b-186">O padrão é **gravação**.</span><span class="sxs-lookup"><span data-stu-id="cad6b-186">The default is **Write**.</span></span>

<span data-ttu-id="cad6b-187">Esse parâmetro é válido somente quando o parâmetro **Variable** é usado no comando.</span><span class="sxs-lookup"><span data-stu-id="cad6b-187">This parameter is valid only when the **Variable** parameter is used in the command.</span></span> <span data-ttu-id="cad6b-188">O modo se aplica a todos os pontos de interrupção definidos no comando.</span><span class="sxs-lookup"><span data-stu-id="cad6b-188">The mode applies to all breakpoints set in the command.</span></span> <span data-ttu-id="cad6b-189">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="cad6b-189">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="cad6b-190">**Write** -interrompe a execução imediatamente antes que um novo valor seja gravado na variável.</span><span class="sxs-lookup"><span data-stu-id="cad6b-190">**Write** - Stops execution immediately before a new value is written to the variable.</span></span>
- <span data-ttu-id="cad6b-191">**Read** -interrompe a execução quando a variável é lida, ou seja, quando seu valor é acessado, seja para ser atribuído, exibido ou usado.</span><span class="sxs-lookup"><span data-stu-id="cad6b-191">**Read** - Stops execution when the variable is read, that is, when its value is accessed, either to be assigned, displayed, or used.</span></span> <span data-ttu-id="cad6b-192">No modo de leitura, a execução não é interrompida quando o valor da variável é alterado.</span><span class="sxs-lookup"><span data-stu-id="cad6b-192">In read mode, execution does not stop when the value of the variable changes.</span></span>
- <span data-ttu-id="cad6b-193">**ReadWrite** – interrompe a execução quando a variável é lida ou gravada.</span><span class="sxs-lookup"><span data-stu-id="cad6b-193">**ReadWrite** - Stops execution when the variable is read or written.</span></span>

```yaml
Type: System.Management.Automation.VariableAccessMode
Parameter Sets: Variable
Aliases:
Accepted values: Read, Write, ReadWrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cad6b-194">-Script</span><span class="sxs-lookup"><span data-stu-id="cad6b-194">-Script</span></span>

<span data-ttu-id="cad6b-195">Especifica uma matriz de arquivos de script em que este cmdlet define um ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="cad6b-195">Specifies an array of script files that this cmdlet sets a breakpoint in.</span></span> <span data-ttu-id="cad6b-196">Insira os caminhos e nomes de arquivo de um ou mais arquivos de script.</span><span class="sxs-lookup"><span data-stu-id="cad6b-196">Enter the paths and file names of one or more script files.</span></span> <span data-ttu-id="cad6b-197">Se os arquivos estão no diretório atual, você pode omitir o caminho.</span><span class="sxs-lookup"><span data-stu-id="cad6b-197">If the files are in the current directory, you can omit the path.</span></span>
<span data-ttu-id="cad6b-198">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="cad6b-198">Wildcards are permitted.</span></span>

<span data-ttu-id="cad6b-199">Por padrão, os pontos de interrupção variáveis e os pontos de interrupção de comando são definidos em qualquer comando executado na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="cad6b-199">By default, variable breakpoints and command breakpoints are set on any command that runs in the current session.</span></span> <span data-ttu-id="cad6b-200">Esse parâmetro é necessário somente ao definir um ponto de interrupção de linha.</span><span class="sxs-lookup"><span data-stu-id="cad6b-200">This parameter is required only when setting a line breakpoint.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Line, Command, Variable
Aliases:

Required: True (Line), False (Command, Variable)
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cad6b-201">-Variable</span><span class="sxs-lookup"><span data-stu-id="cad6b-201">-Variable</span></span>

<span data-ttu-id="cad6b-202">Especifica uma matriz de variáveis em que este cmdlet define os pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="cad6b-202">Specifies an array of variables that this cmdlet sets breakpoints on.</span></span> <span data-ttu-id="cad6b-203">Insira uma lista separada por vírgulas de variáveis sem sinais de dólar ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="cad6b-203">Enter a comma-separated list of variables without dollar signs (`$`).</span></span>

<span data-ttu-id="cad6b-204">Use o parâmetro **Mode** para determinar o modo de acesso que dispara os pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="cad6b-204">Use the **Mode** parameter to determine the mode of access that triggers the breakpoints.</span></span> <span data-ttu-id="cad6b-205">O modo padrão, Write, para a execução imediatamente antes de um novo valor ser gravado na variável.</span><span class="sxs-lookup"><span data-stu-id="cad6b-205">The default mode, Write, stops execution just before a new value is written to the variable.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Variable
Aliases: V

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cad6b-206">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="cad6b-206">CommonParameters</span></span>

<span data-ttu-id="cad6b-207">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="cad6b-207">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cad6b-208">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="cad6b-208">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cad6b-209">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="cad6b-209">INPUTS</span></span>

### <span data-ttu-id="cad6b-210">Nenhum</span><span class="sxs-lookup"><span data-stu-id="cad6b-210">None</span></span>
<span data-ttu-id="cad6b-211">Não é possível canalizar a entrada para `Set-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="cad6b-211">You cannot pipe input to `Set-PSBreakpoint`.</span></span>

## <span data-ttu-id="cad6b-212">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="cad6b-212">OUTPUTS</span></span>

### <span data-ttu-id="cad6b-213">Objeto de ponto de interrupção (System. Management. Automation. LineBreakpoint, System. Management. Automation. VariableBreakpoint, System. Management. Automation. CommandBreakpoint)</span><span class="sxs-lookup"><span data-stu-id="cad6b-213">Breakpoint object (System.Management.Automation.LineBreakpoint, System.Management.Automation.VariableBreakpoint, System.Management.Automation.CommandBreakpoint)</span></span>

<span data-ttu-id="cad6b-214">`Set-PSBreakpoint` Retorna um objeto que representa cada ponto de interrupção que ele define.</span><span class="sxs-lookup"><span data-stu-id="cad6b-214">`Set-PSBreakpoint` returns an object that represents each breakpoint that it sets.</span></span>

## <span data-ttu-id="cad6b-215">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="cad6b-215">NOTES</span></span>

- <span data-ttu-id="cad6b-216">`Set-PSBreakpoint` Não é possível definir um ponto de interrupção em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="cad6b-216">`Set-PSBreakpoint` cannot set a breakpoint on a remote computer.</span></span> <span data-ttu-id="cad6b-217">Para depurar um script em um computador remoto, copie o script para o computador local e o depure localmente.</span><span class="sxs-lookup"><span data-stu-id="cad6b-217">To debug a script on a remote computer, copy the script to the local computer and then debug it locally.</span></span>
- <span data-ttu-id="cad6b-218">Quando você define um ponto de interrupção em mais de uma linha, comando ou variável, `Set-PSBreakpoint` o gera um objeto de ponto de interrupção para cada entrada.</span><span class="sxs-lookup"><span data-stu-id="cad6b-218">When you set a breakpoint on more than one line, command, or variable, `Set-PSBreakpoint` generates a breakpoint object for each entry.</span></span>
- <span data-ttu-id="cad6b-219">Ao definir um ponto de interrupção em uma função ou variável no prompt de comando, você pode definir o ponto de interrupção antes ou depois de criar uma função ou variável.</span><span class="sxs-lookup"><span data-stu-id="cad6b-219">When setting a breakpoint on a function or variable at the command prompt, you can set the breakpoint before or after you create the function or variable.</span></span>

## <span data-ttu-id="cad6b-220">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="cad6b-220">RELATED LINKS</span></span>

[<span data-ttu-id="cad6b-221">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="cad6b-221">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="cad6b-222">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="cad6b-222">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="cad6b-223">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="cad6b-223">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="cad6b-224">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="cad6b-224">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="cad6b-225">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="cad6b-225">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

