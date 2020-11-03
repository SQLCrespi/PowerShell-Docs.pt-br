---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/24/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-psbreakpoint?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSBreakpoint
ms.openlocfilehash: 5968c51f04199d59d3514cdc85ba3f15d02475a4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193742"
---
# <span data-ttu-id="fb88a-103">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="fb88a-103">Set-PSBreakpoint</span></span>

## <span data-ttu-id="fb88a-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="fb88a-104">SYNOPSIS</span></span>
<span data-ttu-id="fb88a-105">Define um ponto de interrupção em uma linha, um comando ou uma variável.</span><span class="sxs-lookup"><span data-stu-id="fb88a-105">Sets a breakpoint on a line, command, or variable.</span></span>

## <span data-ttu-id="fb88a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fb88a-106">SYNTAX</span></span>

### <span data-ttu-id="fb88a-107">Linha (padrão)</span><span class="sxs-lookup"><span data-stu-id="fb88a-107">Line (Default)</span></span>

```
Set-PSBreakpoint [-Action <ScriptBlock>] [[-Column] <Int32>] [-Line] <Int32[]> [-Script] <String[]>
 [<CommonParameters>]
```

### <span data-ttu-id="fb88a-108">Comando</span><span class="sxs-lookup"><span data-stu-id="fb88a-108">Command</span></span>

```
Set-PSBreakpoint [-Action <ScriptBlock>] -Command <String[]> [[-Script] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="fb88a-109">Variável</span><span class="sxs-lookup"><span data-stu-id="fb88a-109">Variable</span></span>

```
Set-PSBreakpoint [-Action <ScriptBlock>] [[-Script] <String[]>] -Variable <String[]>
 [-Mode <VariableAccessMode>] [<CommonParameters>]
```

## <span data-ttu-id="fb88a-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fb88a-110">DESCRIPTION</span></span>

<span data-ttu-id="fb88a-111">O `Set-PSBreakpoint` cmdlet define um ponto de interrupção em um script ou em qualquer comando executado na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="fb88a-111">The `Set-PSBreakpoint` cmdlet sets a breakpoint in a script or in any command run in the current session.</span></span> <span data-ttu-id="fb88a-112">Você pode usar `Set-PSBreakpoint` para definir um ponto de interrupção antes de executar um script ou executar um comando, ou durante a depuração, quando interrompido em outro ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="fb88a-112">You can use `Set-PSBreakpoint` to set a breakpoint before executing a script or running a command, or during debugging, when stopped at another breakpoint.</span></span>

<span data-ttu-id="fb88a-113">`Set-PSBreakpoint` Não é possível definir um ponto de interrupção em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="fb88a-113">`Set-PSBreakpoint` cannot set a breakpoint on a remote computer.</span></span> <span data-ttu-id="fb88a-114">Para depurar um script em um computador remoto, copie o script para o computador local e o depure localmente.</span><span class="sxs-lookup"><span data-stu-id="fb88a-114">To debug a script on a remote computer, copy the script to the local computer and then debug it locally.</span></span>

<span data-ttu-id="fb88a-115">Cada `Set-PSBreakpoint` comando cria um dos três tipos de pontos de interrupção a seguir:</span><span class="sxs-lookup"><span data-stu-id="fb88a-115">Each `Set-PSBreakpoint` command creates one of the following three types of breakpoints:</span></span>

- <span data-ttu-id="fb88a-116">Ponto de interrupção de linha – define os pontos de interrupção em coordenadas de linha e coluna específicas.</span><span class="sxs-lookup"><span data-stu-id="fb88a-116">Line breakpoint - Sets breakpoints at particular line and column coordinates.</span></span>
- <span data-ttu-id="fb88a-117">Ponto de interrupção do comando – define pontos de interrupção em comandos e funções.</span><span class="sxs-lookup"><span data-stu-id="fb88a-117">Command breakpoint - Sets breakpoints on commands and functions.</span></span>
- <span data-ttu-id="fb88a-118">Ponto de interrupção da variável – define pontos de interrupção em variáveis.</span><span class="sxs-lookup"><span data-stu-id="fb88a-118">Variable breakpoint - Sets breakpoints on variables.</span></span>

<span data-ttu-id="fb88a-119">Você pode definir um ponto de interrupção em várias linhas, comandos ou variáveis em um único `Set-PSBreakpoint` comando, mas cada `Set-PSBreakpoint` comando define apenas um tipo de ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="fb88a-119">You can set a breakpoint on multiple lines, commands, or variables in a single `Set-PSBreakpoint` command, but each `Set-PSBreakpoint` command sets only one type of breakpoint.</span></span>

<span data-ttu-id="fb88a-120">Em um ponto de interrupção, o PowerShell interrompe temporariamente a execução e dá controle ao depurador.</span><span class="sxs-lookup"><span data-stu-id="fb88a-120">At a breakpoint, PowerShell temporarily stops executing and gives control to the debugger.</span></span> <span data-ttu-id="fb88a-121">O prompt de comando muda para `DBG\>` e um conjunto de comandos do depurador se torna disponível para uso.</span><span class="sxs-lookup"><span data-stu-id="fb88a-121">The command prompt changes to `DBG\>`, and a set of debugger commands become available for use.</span></span> <span data-ttu-id="fb88a-122">No entanto, você pode usar o parâmetro **Action** para especificar uma resposta alternativa, como condições para o ponto de interrupção ou instruções para executar tarefas adicionais, como log ou diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="fb88a-122">However, you can use the **Action** parameter to specify an alternate response, such as conditions for the breakpoint or instructions to perform additional tasks such as logging or diagnostics.</span></span>

<span data-ttu-id="fb88a-123">O `Set-PSBreakpoint` cmdlet é um dos vários cmdlets projetados para depurar scripts do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fb88a-123">The `Set-PSBreakpoint` cmdlet is one of several cmdlets designed for debugging PowerShell scripts.</span></span>
<span data-ttu-id="fb88a-124">Para obter mais informações sobre o depurador do PowerShell, consulte [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).</span><span class="sxs-lookup"><span data-stu-id="fb88a-124">For more information about the PowerShell debugger, see [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).</span></span>

## <span data-ttu-id="fb88a-125">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="fb88a-125">EXAMPLES</span></span>

### <span data-ttu-id="fb88a-126">Exemplo 1: definir um ponto de interrupção em uma linha</span><span class="sxs-lookup"><span data-stu-id="fb88a-126">Example 1: Set a breakpoint on a line</span></span>

<span data-ttu-id="fb88a-127">Este exemplo define um ponto de interrupção na linha 5 no script Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="fb88a-127">This example sets a breakpoint at line 5 in the Sample.ps1 script.</span></span> <span data-ttu-id="fb88a-128">Quando o script é executado, a execução é interrompida imediatamente antes que a linha 5 seja executada.</span><span class="sxs-lookup"><span data-stu-id="fb88a-128">When the script runs, execution stops immediately before line 5 would execute.</span></span>

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

<span data-ttu-id="fb88a-129">Quando você define um novo ponto de interrupção por número de linha, o `Set-PSBreakpoint` cmdlet gera um objeto de ponto de interrupção de linha ( **System. Management. Automation. LineBreakpoint** ) que inclui a ID de ponto de interrupção e a contagem de acesso.</span><span class="sxs-lookup"><span data-stu-id="fb88a-129">When you set a new breakpoint by line number, the `Set-PSBreakpoint` cmdlet generates a line breakpoint object ( **System.Management.Automation.LineBreakpoint** ) that includes the breakpoint ID and hit count.</span></span>

### <span data-ttu-id="fb88a-130">Exemplo 2: definir um ponto de interrupção em uma função</span><span class="sxs-lookup"><span data-stu-id="fb88a-130">Example 2: Set a breakpoint on a function</span></span>

<span data-ttu-id="fb88a-131">Este exemplo cria um ponto de interrupção de comando na `Increment` função no cmdlet Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="fb88a-131">This example creates a command breakpoint on the `Increment` function in the Sample.ps1 cmdlet.</span></span> <span data-ttu-id="fb88a-132">O script para de executar imediatamente antes de cada chamada para a função especificada.</span><span class="sxs-lookup"><span data-stu-id="fb88a-132">The script stops executing immediately before each call to the specified function.</span></span>

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

<span data-ttu-id="fb88a-133">O resultado é um objeto de ponto de interrupção do comando.</span><span class="sxs-lookup"><span data-stu-id="fb88a-133">The result is a command breakpoint object.</span></span> <span data-ttu-id="fb88a-134">Antes de o script ser executado, o valor da propriedade **contagem** é 0.</span><span class="sxs-lookup"><span data-stu-id="fb88a-134">Before the script runs, the value of the **HitCount** property is 0.</span></span>

### <span data-ttu-id="fb88a-135">Exemplo 3: definir um ponto de interrupção em uma variável</span><span class="sxs-lookup"><span data-stu-id="fb88a-135">Example 3: Set a breakpoint on a variable</span></span>

<span data-ttu-id="fb88a-136">Este exemplo define um ponto de interrupção na variável de **servidor** no script Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="fb88a-136">This example sets a breakpoint on the **Server** variable in the Sample.ps1 script.</span></span> <span data-ttu-id="fb88a-137">Ele usa o parâmetro **Mode** com um valor de **ReadWrite** para interromper a execução quando o valor da variável é lido e pouco antes de o valor ser alterado.</span><span class="sxs-lookup"><span data-stu-id="fb88a-137">It uses the **Mode** parameter with a value of **ReadWrite** to stop execution when the value of the variable is read and just before the value changes.</span></span>

```powershell
Set-PSBreakpoint -Script "sample.ps1" -Variable "Server" -Mode ReadWrite
```

### <span data-ttu-id="fb88a-138">Exemplo 4: definir um ponto de interrupção em cada comando que começa com o texto especificado</span><span class="sxs-lookup"><span data-stu-id="fb88a-138">Example 4: Set a breakpoint on every command that begins with specified text</span></span>

<span data-ttu-id="fb88a-139">Este exemplo define um ponto de interrupção em cada comando no script de Sample.ps1 que começa com "Write", como `Write-Host` .</span><span class="sxs-lookup"><span data-stu-id="fb88a-139">This example sets a breakpoint on every command in the Sample.ps1 script that begins with "write", such as `Write-Host`.</span></span>

```powershell
Set-PSBreakpoint -Script Sample.ps1 -Command "write*"
```

### <span data-ttu-id="fb88a-140">Exemplo 5: definir um ponto de interrupção dependendo do valor de uma variável</span><span class="sxs-lookup"><span data-stu-id="fb88a-140">Example 5: Set a breakpoint depending on the value of a variable</span></span>

<span data-ttu-id="fb88a-141">Este exemplo interrompe a execução na `DiskTest` função no script Test.ps1 somente quando o valor da `$Disk` variável é maior que 2.</span><span class="sxs-lookup"><span data-stu-id="fb88a-141">This example stops execution at the `DiskTest` function in the Test.ps1 script only when the value of the `$Disk` variable is greater than 2.</span></span>

```powershell
Set-PSBreakpoint -Script "test.ps1" -Command "DiskTest" -Action { if ($Disk -gt 2) { break } }
```

<span data-ttu-id="fb88a-142">O valor da **ação** é um bloco de script que testa o valor da `$Disk` variável na função.</span><span class="sxs-lookup"><span data-stu-id="fb88a-142">The value of the **Action** is a script block that tests the value of the `$Disk` variable in the function.</span></span>

<span data-ttu-id="fb88a-143">A ação usará a `break` palavra-chave para interromper a execução se a condição for atendida.</span><span class="sxs-lookup"><span data-stu-id="fb88a-143">The action uses the `break` keyword to stop execution if the condition is met.</span></span> <span data-ttu-id="fb88a-144">A alternativa (e o padrão) é **continuar** .</span><span class="sxs-lookup"><span data-stu-id="fb88a-144">The alternative (and the default) is **Continue** .</span></span>

### <span data-ttu-id="fb88a-145">Exemplo 6: definir um ponto de interrupção em uma função</span><span class="sxs-lookup"><span data-stu-id="fb88a-145">Example 6: Set a breakpoint on a function</span></span>

<span data-ttu-id="fb88a-146">Este exemplo define um ponto de interrupção na `CheckLog` função.</span><span class="sxs-lookup"><span data-stu-id="fb88a-146">This example sets a breakpoint on the `CheckLog` function.</span></span> <span data-ttu-id="fb88a-147">Como o comando não especifica um script, o ponto de interrupção é definido em qualquer coisa que seja executada na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="fb88a-147">Because the command does not specify a script, the breakpoint is set on anything that runs in the current session.</span></span> <span data-ttu-id="fb88a-148">O depurador interrompe quando a função é chamada, não quando é declarada.</span><span class="sxs-lookup"><span data-stu-id="fb88a-148">The debugger breaks when the function is called, not when it is declared.</span></span>

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

### <span data-ttu-id="fb88a-149">Exemplo 7: definir pontos de interrupção em várias linhas</span><span class="sxs-lookup"><span data-stu-id="fb88a-149">Example 7: Set breakpoints on multiple lines</span></span>

<span data-ttu-id="fb88a-150">Este exemplo define três pontos de interrupção de linha no script de Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="fb88a-150">This example sets three line breakpoints in the Sample.ps1 script.</span></span> <span data-ttu-id="fb88a-151">Ele define um ponto de interrupção na coluna 2 para cada uma das linhas especificada no script.</span><span class="sxs-lookup"><span data-stu-id="fb88a-151">It sets one breakpoint at column 2 on each of the lines specified in the script.</span></span> <span data-ttu-id="fb88a-152">A ação especificada no parâmetro **Action** aplica-se a todos os pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="fb88a-152">The action specified in the **Action** parameter applies to all breakpoints.</span></span>

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

## <span data-ttu-id="fb88a-153">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fb88a-153">PARAMETERS</span></span>

### <span data-ttu-id="fb88a-154">-Action</span><span class="sxs-lookup"><span data-stu-id="fb88a-154">-Action</span></span>

<span data-ttu-id="fb88a-155">Especifica comandos que são executados em cada ponto de interrupção em vez de interromper.</span><span class="sxs-lookup"><span data-stu-id="fb88a-155">Specifies commands that run at each breakpoint instead of breaking.</span></span> <span data-ttu-id="fb88a-156">Insira um bloco de script que contenha os comandos.</span><span class="sxs-lookup"><span data-stu-id="fb88a-156">Enter a script block that contains the commands.</span></span> <span data-ttu-id="fb88a-157">Você pode usar esse parâmetro para definir pontos de interrupção condicionais ou realizar outras tarefas, como teste ou registro em log.</span><span class="sxs-lookup"><span data-stu-id="fb88a-157">You can use this parameter to set conditional breakpoints or to perform other tasks, such as testing or logging.</span></span>

<span data-ttu-id="fb88a-158">Se este parâmetro é omitido, ou nenhuma ação é especificada, a execução para no ponto de interrupção e o depurador é iniciado.</span><span class="sxs-lookup"><span data-stu-id="fb88a-158">If this parameter is omitted, or no action is specified, execution stops at the breakpoint, and the debugger starts.</span></span>

<span data-ttu-id="fb88a-159">Quando o parâmetro **Action** é usado, o bloco de script Action é executado em cada ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="fb88a-159">When the **Action** parameter is used, the Action script block runs at each breakpoint.</span></span> <span data-ttu-id="fb88a-160">A execução não é interrompida a menos que o bloco de script inclua a palavra-chave Break.</span><span class="sxs-lookup"><span data-stu-id="fb88a-160">Execution does not stop unless the script block includes the Break keyword.</span></span> <span data-ttu-id="fb88a-161">Se você usar a palavra-chave Continue no bloco de script, a execução continua até o próximo ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="fb88a-161">If you use the Continue keyword in the script block, execution resumes until the next breakpoint.</span></span>

<span data-ttu-id="fb88a-162">Para obter mais informações, consulte [about_Script_Blocks](../Microsoft.PowerShell.Core/About/about_Script_Blocks.md), [about_Break](../Microsoft.PowerShell.Core/About/about_Break.md)e [about_Continue](../Microsoft.PowerShell.Core/About/about_Continue.md).</span><span class="sxs-lookup"><span data-stu-id="fb88a-162">For more information, see [about_Script_Blocks](../Microsoft.PowerShell.Core/About/about_Script_Blocks.md), [about_Break](../Microsoft.PowerShell.Core/About/about_Break.md), and [about_Continue](../Microsoft.PowerShell.Core/About/about_Continue.md).</span></span>

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

### <span data-ttu-id="fb88a-163">-Coluna</span><span class="sxs-lookup"><span data-stu-id="fb88a-163">-Column</span></span>

<span data-ttu-id="fb88a-164">Especifica o número de coluna da coluna no arquivo de script em que a execução é interrompida.</span><span class="sxs-lookup"><span data-stu-id="fb88a-164">Specifies the column number of the column in the script file on which execution stops.</span></span> <span data-ttu-id="fb88a-165">Insira apenas um número de coluna.</span><span class="sxs-lookup"><span data-stu-id="fb88a-165">Enter only one column number.</span></span> <span data-ttu-id="fb88a-166">O padrão é a coluna 1.</span><span class="sxs-lookup"><span data-stu-id="fb88a-166">The default is column 1.</span></span>

<span data-ttu-id="fb88a-167">O valor da coluna é usado com o valor do parâmetro **line** para especificar o ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="fb88a-167">The Column value is used with the value of the **Line** parameter to specify the breakpoint.</span></span> <span data-ttu-id="fb88a-168">Se o parâmetro de **linha** especificar várias linhas, o parâmetro de **coluna** definirá um ponto de interrupção na coluna especificada em cada uma das linhas especificadas.</span><span class="sxs-lookup"><span data-stu-id="fb88a-168">If the **Line** parameter specifies multiple lines, the **Column** parameter sets a breakpoint at the specified column on each of the specified lines.</span></span> <span data-ttu-id="fb88a-169">O PowerShell para de executar antes da instrução ou expressão que inclui o caractere na linha especificada e na posição da coluna.</span><span class="sxs-lookup"><span data-stu-id="fb88a-169">PowerShell stops executing before the statement or expression that includes the character at the specified line and column position.</span></span>

<span data-ttu-id="fb88a-170">Colunas são contadas a partir da margem superior esquerda começando pela coluna número 1 (não a 0).</span><span class="sxs-lookup"><span data-stu-id="fb88a-170">Columns are counted from the top left margin beginning with column number 1 (not 0).</span></span> <span data-ttu-id="fb88a-171">Se especificar uma coluna que não existe no script, um erro não é declarado, mas o ponto de interrupção não é executado.</span><span class="sxs-lookup"><span data-stu-id="fb88a-171">If you specify a column that does not exist in the script, an error is not declared, but the breakpoint is never executed.</span></span>

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

### <span data-ttu-id="fb88a-172">-Command</span><span class="sxs-lookup"><span data-stu-id="fb88a-172">-Command</span></span>

<span data-ttu-id="fb88a-173">Define um ponto de interrupção do comando.</span><span class="sxs-lookup"><span data-stu-id="fb88a-173">Sets a command breakpoint.</span></span> <span data-ttu-id="fb88a-174">Insira nomes de cmdlet, como `Get-Process` ou nomes de função.</span><span class="sxs-lookup"><span data-stu-id="fb88a-174">Enter cmdlet names, such as `Get-Process`, or function names.</span></span> <span data-ttu-id="fb88a-175">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="fb88a-175">Wildcards are permitted.</span></span>

<span data-ttu-id="fb88a-176">A execução para antes que cada instância de cada comando seja executada.</span><span class="sxs-lookup"><span data-stu-id="fb88a-176">Execution stops just before each instance of each command is executed.</span></span> <span data-ttu-id="fb88a-177">Se o comando for uma função, a execução é interrompida toda vez que a função é chamada e a cada seção BEGIN, PROCESS e END.</span><span class="sxs-lookup"><span data-stu-id="fb88a-177">If the command is a function, execution stops each time the function is called and at each BEGIN, PROCESS, and END section.</span></span>

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

### <span data-ttu-id="fb88a-178">-Linha</span><span class="sxs-lookup"><span data-stu-id="fb88a-178">-Line</span></span>

<span data-ttu-id="fb88a-179">Define um ponto de interrupção em um script.</span><span class="sxs-lookup"><span data-stu-id="fb88a-179">Sets a line breakpoint in a script.</span></span> <span data-ttu-id="fb88a-180">Insira um ou mais números de linha, separados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="fb88a-180">Enter one or more line numbers, separated by commas.</span></span> <span data-ttu-id="fb88a-181">O PowerShell para imediatamente antes de executar a instrução que começa em cada uma das linhas especificadas.</span><span class="sxs-lookup"><span data-stu-id="fb88a-181">PowerShell stops immediately before executing the statement that begins on each of the specified lines.</span></span>

<span data-ttu-id="fb88a-182">Linhas são contadas a partir da margem superior esquerda do arquivo de script começando pela linha número 1 (não a 0).</span><span class="sxs-lookup"><span data-stu-id="fb88a-182">Lines are counted from the top left margin of the script file beginning with line number 1 (not 0).</span></span>
<span data-ttu-id="fb88a-183">Se especificar uma linha em branco, a execução para antes da próxima linha que não estiver em branco.</span><span class="sxs-lookup"><span data-stu-id="fb88a-183">If you specify a blank line, execution stops before the next non-blank line.</span></span> <span data-ttu-id="fb88a-184">Se a linha está fora do intervalo, o ponto de interrupção nunca é atingido.</span><span class="sxs-lookup"><span data-stu-id="fb88a-184">If the line is out of range, the breakpoint is never hit.</span></span>

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

### <span data-ttu-id="fb88a-185">-Mode</span><span class="sxs-lookup"><span data-stu-id="fb88a-185">-Mode</span></span>

<span data-ttu-id="fb88a-186">Especifica o modo de acesso que dispara pontos de interrupção de variável.</span><span class="sxs-lookup"><span data-stu-id="fb88a-186">Specifies the mode of access that triggers variable breakpoints.</span></span> <span data-ttu-id="fb88a-187">O padrão é **gravação** .</span><span class="sxs-lookup"><span data-stu-id="fb88a-187">The default is **Write** .</span></span>

<span data-ttu-id="fb88a-188">Esse parâmetro é válido somente quando o parâmetro **Variable** é usado no comando.</span><span class="sxs-lookup"><span data-stu-id="fb88a-188">This parameter is valid only when the **Variable** parameter is used in the command.</span></span> <span data-ttu-id="fb88a-189">O modo se aplica a todos os pontos de interrupção definidos no comando.</span><span class="sxs-lookup"><span data-stu-id="fb88a-189">The mode applies to all breakpoints set in the command.</span></span> <span data-ttu-id="fb88a-190">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="fb88a-190">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="fb88a-191">**Write** -interrompe a execução imediatamente antes que um novo valor seja gravado na variável.</span><span class="sxs-lookup"><span data-stu-id="fb88a-191">**Write** - Stops execution immediately before a new value is written to the variable.</span></span>
- <span data-ttu-id="fb88a-192">**Read** -interrompe a execução quando a variável é lida, ou seja, quando seu valor é acessado, seja para ser atribuído, exibido ou usado.</span><span class="sxs-lookup"><span data-stu-id="fb88a-192">**Read** - Stops execution when the variable is read, that is, when its value is accessed, either to be assigned, displayed, or used.</span></span> <span data-ttu-id="fb88a-193">No modo de leitura, a execução não é interrompida quando o valor da variável é alterado.</span><span class="sxs-lookup"><span data-stu-id="fb88a-193">In read mode, execution does not stop when the value of the variable changes.</span></span>
- <span data-ttu-id="fb88a-194">**ReadWrite** – interrompe a execução quando a variável é lida ou gravada.</span><span class="sxs-lookup"><span data-stu-id="fb88a-194">**ReadWrite** - Stops execution when the variable is read or written.</span></span>

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

### <span data-ttu-id="fb88a-195">-Script</span><span class="sxs-lookup"><span data-stu-id="fb88a-195">-Script</span></span>

<span data-ttu-id="fb88a-196">Especifica uma matriz de arquivos de script em que este cmdlet define um ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="fb88a-196">Specifies an array of script files that this cmdlet sets a breakpoint in.</span></span> <span data-ttu-id="fb88a-197">Insira os caminhos e nomes de arquivo de um ou mais arquivos de script.</span><span class="sxs-lookup"><span data-stu-id="fb88a-197">Enter the paths and file names of one or more script files.</span></span> <span data-ttu-id="fb88a-198">Se os arquivos estão no diretório atual, você pode omitir o caminho.</span><span class="sxs-lookup"><span data-stu-id="fb88a-198">If the files are in the current directory, you can omit the path.</span></span>
<span data-ttu-id="fb88a-199">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="fb88a-199">Wildcards are permitted.</span></span>

<span data-ttu-id="fb88a-200">Por padrão, os pontos de interrupção variáveis e os pontos de interrupção de comando são definidos em qualquer comando executado na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="fb88a-200">By default, variable breakpoints and command breakpoints are set on any command that runs in the current session.</span></span> <span data-ttu-id="fb88a-201">Esse parâmetro é necessário somente ao definir um ponto de interrupção de linha.</span><span class="sxs-lookup"><span data-stu-id="fb88a-201">This parameter is required only when setting a line breakpoint.</span></span>

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

### <span data-ttu-id="fb88a-202">-Variable</span><span class="sxs-lookup"><span data-stu-id="fb88a-202">-Variable</span></span>

<span data-ttu-id="fb88a-203">Especifica uma matriz de variáveis em que este cmdlet define os pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="fb88a-203">Specifies an array of variables that this cmdlet sets breakpoints on.</span></span> <span data-ttu-id="fb88a-204">Insira uma lista separada por vírgulas de variáveis sem sinais de dólar ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="fb88a-204">Enter a comma-separated list of variables without dollar signs (`$`).</span></span>

<span data-ttu-id="fb88a-205">Use o parâmetro **Mode** para determinar o modo de acesso que dispara os pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="fb88a-205">Use the **Mode** parameter to determine the mode of access that triggers the breakpoints.</span></span> <span data-ttu-id="fb88a-206">O modo padrão, Write, para a execução imediatamente antes de um novo valor ser gravado na variável.</span><span class="sxs-lookup"><span data-stu-id="fb88a-206">The default mode, Write, stops execution just before a new value is written to the variable.</span></span>

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

### <span data-ttu-id="fb88a-207">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fb88a-207">CommonParameters</span></span>

<span data-ttu-id="fb88a-208">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fb88a-208">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fb88a-209">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fb88a-209">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fb88a-210">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="fb88a-210">INPUTS</span></span>

### <span data-ttu-id="fb88a-211">Nenhum</span><span class="sxs-lookup"><span data-stu-id="fb88a-211">None</span></span>
<span data-ttu-id="fb88a-212">Não é possível canalizar a entrada para `Set-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="fb88a-212">You cannot pipe input to `Set-PSBreakpoint`.</span></span>

## <span data-ttu-id="fb88a-213">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="fb88a-213">OUTPUTS</span></span>

### <span data-ttu-id="fb88a-214">Objeto de ponto de interrupção (System. Management. Automation. LineBreakpoint, System. Management. Automation. VariableBreakpoint, System. Management. Automation. CommandBreakpoint)</span><span class="sxs-lookup"><span data-stu-id="fb88a-214">Breakpoint object (System.Management.Automation.LineBreakpoint, System.Management.Automation.VariableBreakpoint, System.Management.Automation.CommandBreakpoint)</span></span>

<span data-ttu-id="fb88a-215">`Set-PSBreakpoint` Retorna um objeto que representa cada ponto de interrupção que ele define.</span><span class="sxs-lookup"><span data-stu-id="fb88a-215">`Set-PSBreakpoint` returns an object that represents each breakpoint that it sets.</span></span>

## <span data-ttu-id="fb88a-216">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="fb88a-216">NOTES</span></span>

- <span data-ttu-id="fb88a-217">`Set-PSBreakpoint` Não é possível definir um ponto de interrupção em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="fb88a-217">`Set-PSBreakpoint` cannot set a breakpoint on a remote computer.</span></span> <span data-ttu-id="fb88a-218">Para depurar um script em um computador remoto, copie o script para o computador local e o depure localmente.</span><span class="sxs-lookup"><span data-stu-id="fb88a-218">To debug a script on a remote computer, copy the script to the local computer and then debug it locally.</span></span>
- <span data-ttu-id="fb88a-219">Quando você define um ponto de interrupção em mais de uma linha, comando ou variável, `Set-PSBreakpoint` o gera um objeto de ponto de interrupção para cada entrada.</span><span class="sxs-lookup"><span data-stu-id="fb88a-219">When you set a breakpoint on more than one line, command, or variable, `Set-PSBreakpoint` generates a breakpoint object for each entry.</span></span>
- <span data-ttu-id="fb88a-220">Ao definir um ponto de interrupção em uma função ou variável no prompt de comando, você pode definir o ponto de interrupção antes ou depois de criar uma função ou variável.</span><span class="sxs-lookup"><span data-stu-id="fb88a-220">When setting a breakpoint on a function or variable at the command prompt, you can set the breakpoint before or after you create the function or variable.</span></span>

## <span data-ttu-id="fb88a-221">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="fb88a-221">RELATED LINKS</span></span>

[<span data-ttu-id="fb88a-222">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="fb88a-222">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="fb88a-223">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="fb88a-223">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="fb88a-224">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="fb88a-224">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="fb88a-225">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="fb88a-225">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="fb88a-226">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="fb88a-226">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)
