---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/01/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/trace-command?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Trace-Command
ms.openlocfilehash: 744afbdf202f3daa3b82a17a53e4c9570c7cf9d7
ms.sourcegitcommit: 5b48fe7b2593581b7d4f7dd7c22206d8a45bb8af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "106184436"
---
# <span data-ttu-id="348a1-103">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="348a1-103">Trace-Command</span></span>

## <span data-ttu-id="348a1-104">Sinopse</span><span class="sxs-lookup"><span data-stu-id="348a1-104">Synopsis</span></span>
<span data-ttu-id="348a1-105">Configura e inicia um rastreamento da expressão ou comando especificado.</span><span class="sxs-lookup"><span data-stu-id="348a1-105">Configures and starts a trace of the specified expression or command.</span></span>

## <span data-ttu-id="348a1-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="348a1-106">Syntax</span></span>

### <span data-ttu-id="348a1-107">expressionset (padrão)</span><span class="sxs-lookup"><span data-stu-id="348a1-107">expressionSet (Default)</span></span>

```
Trace-Command [-InputObject <PSObject>] [-Name] <String[]> [[-Option] <PSTraceSourceOptions>]
 [-Expression] <ScriptBlock> [-ListenerOption <TraceOptions>] [-FilePath <String>] [-Force] [-Debugger]
 [-PSHost] [<CommonParameters>]
```

### <span data-ttu-id="348a1-108">commandSet</span><span class="sxs-lookup"><span data-stu-id="348a1-108">commandSet</span></span>

```
Trace-Command [-InputObject <PSObject>] [-Name] <String[]> [[-Option] <PSTraceSourceOptions>]
 [-Command] <String> [-ArgumentList <Object[]>] [-ListenerOption <TraceOptions>] [-FilePath <String>] [-Force]
 [-Debugger] [-PSHost] [<CommonParameters>]
```

## <span data-ttu-id="348a1-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="348a1-109">Description</span></span>

<span data-ttu-id="348a1-110">O `Trace-Command` cmdlet configura e inicia um rastreamento da expressão ou do comando especificado.</span><span class="sxs-lookup"><span data-stu-id="348a1-110">The `Trace-Command` cmdlet configures and starts a trace of the specified expression or command.</span></span>
<span data-ttu-id="348a1-111">Ele funciona como Set-TraceSource, exceto que se aplica apenas ao comando especificado.</span><span class="sxs-lookup"><span data-stu-id="348a1-111">It works like Set-TraceSource, except that it applies only to the specified command.</span></span>

## <span data-ttu-id="348a1-112">Exemplos</span><span class="sxs-lookup"><span data-stu-id="348a1-112">Examples</span></span>

### <span data-ttu-id="348a1-113">Exemplo 1: rastrear o processamento de metadados, a associação de parâmetro e uma expressão</span><span class="sxs-lookup"><span data-stu-id="348a1-113">Example 1: Trace metadata processing, parameter binding, and an expression</span></span>

<span data-ttu-id="348a1-114">Este exemplo inicia um rastreamento de processamento de metadados, associação de parâmetro e criação de cmdlet e destruição da `Get-Process Notepad` expressão.</span><span class="sxs-lookup"><span data-stu-id="348a1-114">This example starts a trace of metadata processing, parameter binding, and cmdlet creation and destruction of the `Get-Process Notepad` expression.</span></span>

```powershell
Trace-Command -Name metadata,parameterbinding,cmdlet -Expression {Get-Process Notepad} -PSHost
```

<span data-ttu-id="348a1-115">Ele usa o parâmetro **Name** para especificar as fontes de rastreamento, o parâmetro **expression** para especificar o comando e o parâmetro **PSHost** para enviar a saída para o console.</span><span class="sxs-lookup"><span data-stu-id="348a1-115">It uses the **Name** parameter to specify the trace sources, the **Expression** parameter to specify the command, and the **PSHost** parameter to send the output to the console.</span></span> <span data-ttu-id="348a1-116">Como não especifica nenhuma opção de rastreamento ou opções de ouvinte, o comando usa os padrões:</span><span class="sxs-lookup"><span data-stu-id="348a1-116">Because it does not specify any tracing options or listener options, the command uses the defaults:</span></span>

- <span data-ttu-id="348a1-117">Tudo para as opções de rastreamento</span><span class="sxs-lookup"><span data-stu-id="348a1-117">All for the tracing options</span></span>
- <span data-ttu-id="348a1-118">Nenhuma para as opções de ouvinte</span><span class="sxs-lookup"><span data-stu-id="348a1-118">None for the listener options</span></span>

### <span data-ttu-id="348a1-119">Exemplo 2: rastrear as ações de operações de parâmetros</span><span class="sxs-lookup"><span data-stu-id="348a1-119">Example 2: Trace the actions of ParameterBinding operations</span></span>

<span data-ttu-id="348a1-120">Este exemplo rastreia as ações das operações de **ParameterBinding** do PowerShell enquanto processa uma `Get-Alias` expressão que usa a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="348a1-120">This example traces the actions of the **ParameterBinding** operations of PowerShell while it processes a `Get-Alias` expression that takes input from the pipeline.</span></span>

```powershell
$A = "i*"
Trace-Command ParameterBinding {Get-Alias $Input} -PSHost -InputObject $A
```

<span data-ttu-id="348a1-121">No `Trace-Command` , o parâmetro **InputObject** passa um objeto para a expressão que está sendo processada durante o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="348a1-121">In `Trace-Command`, the **InputObject** parameter passes an object to the expression that is being processed during the trace.</span></span>

<span data-ttu-id="348a1-122">O primeiro comando armazena a cadeia de caracteres `i*` na `$A` variável.</span><span class="sxs-lookup"><span data-stu-id="348a1-122">The first command stores the string `i*` in the `$A` variable.</span></span> <span data-ttu-id="348a1-123">O segundo comando usa o `Trace-Command` cmdlet com a origem de rastreamento de ParameterBinding.</span><span class="sxs-lookup"><span data-stu-id="348a1-123">The second command uses the `Trace-Command` cmdlet with the ParameterBinding trace source.</span></span> <span data-ttu-id="348a1-124">O parâmetro **PSHost** envia a saída para o console.</span><span class="sxs-lookup"><span data-stu-id="348a1-124">The **PSHost** parameter sends the output to the console.</span></span>

<span data-ttu-id="348a1-125">A expressão que está sendo processada é `Get-Alias $Input` , em que a `$Input` variável é associada ao parâmetro **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="348a1-125">The expression being processed is `Get-Alias $Input`, where the `$Input` variable is associated with the **InputObject** parameter.</span></span> <span data-ttu-id="348a1-126">O parâmetro **InputObject** passa a variável `$A` para a expressão.</span><span class="sxs-lookup"><span data-stu-id="348a1-126">The **InputObject** parameter passes the variable `$A` to the expression.</span></span> <span data-ttu-id="348a1-127">Na verdade, o comando que está sendo processado durante o rastreamento é `Get-Alias -InputObject $A" or "$A | Get-Alias` .</span><span class="sxs-lookup"><span data-stu-id="348a1-127">In effect, the command being processed during the trace is `Get-Alias -InputObject $A" or "$A | Get-Alias`.</span></span>

## <span data-ttu-id="348a1-128">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="348a1-128">Parameters</span></span>

### <span data-ttu-id="348a1-129">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="348a1-129">-ArgumentList</span></span>

<span data-ttu-id="348a1-130">Especifica os parâmetros e valores de parâmetro para o comando que está sendo rastreado.</span><span class="sxs-lookup"><span data-stu-id="348a1-130">Specifies the parameters and parameter values for the command being traced.</span></span> <span data-ttu-id="348a1-131">O alias para **ArgumentList** é **Args**.</span><span class="sxs-lookup"><span data-stu-id="348a1-131">The alias for **ArgumentList** is **Args**.</span></span> <span data-ttu-id="348a1-132">Esse recurso é especialmente útil para depuração parâmetros dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="348a1-132">This feature is especially useful for debugging dynamic parameters.</span></span>

<span data-ttu-id="348a1-133">Para obter mais informações sobre o comportamento de **ArgumentList**, consulte [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="348a1-133">For more information about the behavior of **ArgumentList**, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: commandSet
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="348a1-134">-Command</span><span class="sxs-lookup"><span data-stu-id="348a1-134">-Command</span></span>

<span data-ttu-id="348a1-135">Especifica um comando que está sendo processado durante o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="348a1-135">Specifies a command that is being processed during the trace.</span></span>

```yaml
Type: System.String
Parameter Sets: commandSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="348a1-136">-Depurador</span><span class="sxs-lookup"><span data-stu-id="348a1-136">-Debugger</span></span>

<span data-ttu-id="348a1-137">Indica que o cmdlet envia a saída de rastreamento para o depurador.</span><span class="sxs-lookup"><span data-stu-id="348a1-137">Indicates that the cmdlet sends the trace output to the debugger.</span></span> <span data-ttu-id="348a1-138">Você pode exibir a saída em qualquer modo de usuário ou depurador do modo kernel, ou ainda no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="348a1-138">You can view the output in any user-mode or kernel mode debugger or in Visual Studio.</span></span> <span data-ttu-id="348a1-139">Esse parâmetro também seleciona o ouvinte de rastreamento padrão.</span><span class="sxs-lookup"><span data-stu-id="348a1-139">This parameter also selects the default trace listener.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="348a1-140">-Expressão</span><span class="sxs-lookup"><span data-stu-id="348a1-140">-Expression</span></span>

<span data-ttu-id="348a1-141">Especifica a expressão que está sendo processada durante o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="348a1-141">Specifies the expression that is being processed during the trace.</span></span> <span data-ttu-id="348a1-142">Coloque a expressão entre chaves ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="348a1-142">Enclose the expression in braces (`{}`).</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: expressionSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="348a1-143">-FilePath</span><span class="sxs-lookup"><span data-stu-id="348a1-143">-FilePath</span></span>

<span data-ttu-id="348a1-144">Especifica um arquivo para o qual o cmdlet envia a saída de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="348a1-144">Specifies a file that the cmdlet sends the trace output to.</span></span> <span data-ttu-id="348a1-145">Esse parâmetro também seleciona o ouvinte de rastreamento do arquivo.</span><span class="sxs-lookup"><span data-stu-id="348a1-145">This parameter also selects the file trace listener.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath, Path

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="348a1-146">-Force</span><span class="sxs-lookup"><span data-stu-id="348a1-146">-Force</span></span>

<span data-ttu-id="348a1-147">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="348a1-147">Forces the command to run without asking for user confirmation.</span></span> <span data-ttu-id="348a1-148">Usado com o parâmetro **FilePath** .</span><span class="sxs-lookup"><span data-stu-id="348a1-148">Used with the **FilePath** parameter.</span></span> <span data-ttu-id="348a1-149">Mesmo usando o parâmetro **Force** , o cmdlet não pode substituir as restrições de segurança.</span><span class="sxs-lookup"><span data-stu-id="348a1-149">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="348a1-150">-InputObject</span><span class="sxs-lookup"><span data-stu-id="348a1-150">-InputObject</span></span>

<span data-ttu-id="348a1-151">Especifica a entrada para a expressão que está sendo processada durante o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="348a1-151">Specifies input to the expression that is being processed during the trace.</span></span> <span data-ttu-id="348a1-152">Você pode inserir uma variável que representa a entrada que aceita a expressão ou passar um objeto por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="348a1-152">You can enter a variable that represents the input that the expression accepts, or pass an object through the pipeline.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="348a1-153">-ListenerOption</span><span class="sxs-lookup"><span data-stu-id="348a1-153">-ListenerOption</span></span>

<span data-ttu-id="348a1-154">Especifica dados opcionais para o prefixo de cada mensagem de rastreamento na saída.</span><span class="sxs-lookup"><span data-stu-id="348a1-154">Specifies optional data to the prefix of each trace message in the output.</span></span> <span data-ttu-id="348a1-155">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="348a1-155">The acceptable values for this parameter are:</span></span>

- `None`
- `LogicalOperationStack`
- `DateTime`
- `Timestamp`
- `ProcessId`
- `ThreadId`
- `Callstack`

<span data-ttu-id="348a1-156">`None` é o padrão.</span><span class="sxs-lookup"><span data-stu-id="348a1-156">`None` is the default.</span></span>

<span data-ttu-id="348a1-157">Esses valores são definidos como uma enumeração baseada em sinalizador.</span><span class="sxs-lookup"><span data-stu-id="348a1-157">These values are defined as a flag-based enumeration.</span></span> <span data-ttu-id="348a1-158">Você pode combinar vários valores juntos para definir vários sinalizadores usando esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="348a1-158">You can combine multiple values together to set multiple flags using this parameter.</span></span> <span data-ttu-id="348a1-159">Os valores podem ser passados para o parâmetro **ListenerOption** como uma matriz de valores ou como uma cadeia de caracteres separada por vírgulas desses valores.</span><span class="sxs-lookup"><span data-stu-id="348a1-159">The values can be passed to the **ListenerOption** parameter as an array of values or as a comma-separated string of those values.</span></span> <span data-ttu-id="348a1-160">O cmdlet combinará os valores usando uma operação binary ou.</span><span class="sxs-lookup"><span data-stu-id="348a1-160">The cmdlet will combine the values using a binary-OR operation.</span></span> <span data-ttu-id="348a1-161">Passar valores como uma matriz é a opção mais simples e também permite que você use a conclusão de tabulação nos valores.</span><span class="sxs-lookup"><span data-stu-id="348a1-161">Passing values as an array is the simplest option and also allows you to use tab-completion on the values.</span></span>

```yaml
Type: System.Diagnostics.TraceOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="348a1-162">-Name</span><span class="sxs-lookup"><span data-stu-id="348a1-162">-Name</span></span>

<span data-ttu-id="348a1-163">Especifica uma matriz de componentes do PowerShell que são rastreados.</span><span class="sxs-lookup"><span data-stu-id="348a1-163">Specifies an array of PowerShell components that are traced.</span></span> <span data-ttu-id="348a1-164">Insira o nome da origem de rastreamento de cada componente.</span><span class="sxs-lookup"><span data-stu-id="348a1-164">Enter the name of the trace source of each component.</span></span> <span data-ttu-id="348a1-165">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="348a1-165">Wildcards are permitted.</span></span> <span data-ttu-id="348a1-166">Para localizar as fontes de rastreamento no seu computador, digite `Get-TraceSource` .</span><span class="sxs-lookup"><span data-stu-id="348a1-166">To find the trace sources on your computer, type `Get-TraceSource`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="348a1-167">-Opção</span><span class="sxs-lookup"><span data-stu-id="348a1-167">-Option</span></span>

<span data-ttu-id="348a1-168">Determina o tipo de eventos que são rastreados.</span><span class="sxs-lookup"><span data-stu-id="348a1-168">Determines the type of events that are traced.</span></span> <span data-ttu-id="348a1-169">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="348a1-169">The acceptable values for this parameter are:</span></span>

- `None`
- `Constructor`
- `Dispose`
- `Finalizer`
- `Method`
- `Property`
- `Delegates`
- `Events`
- `Exception`
- `Lock`
- `Error`
- `Errors`
- `Warning`
- `Verbose`
- `WriteLine`
- `Data`
- `Scope`
- `ExecutionFlow`
- `Assert`
- `All`

<span data-ttu-id="348a1-170">`All` é o padrão.</span><span class="sxs-lookup"><span data-stu-id="348a1-170">`All` is the default.</span></span>

<span data-ttu-id="348a1-171">Os seguintes valores são combinações de outros valores:</span><span class="sxs-lookup"><span data-stu-id="348a1-171">The following values are combinations of other values:</span></span>

- <span data-ttu-id="348a1-172">`ExecutionFlow`: `Constructor`, `Dispose`, `Finalizer`, `Method`, `Delegates`, `Events`, `Scope`</span><span class="sxs-lookup"><span data-stu-id="348a1-172">`ExecutionFlow`: `Constructor`, `Dispose`, `Finalizer`, `Method`, `Delegates`, `Events`, `Scope`</span></span>
- <span data-ttu-id="348a1-173">`Data`: `Constructor`, `Dispose`, `Finalizer`, `Property`, `Verbose`, `WriteLine`</span><span class="sxs-lookup"><span data-stu-id="348a1-173">`Data`: `Constructor`, `Dispose`, `Finalizer`, `Property`, `Verbose`, `WriteLine`</span></span>
- <span data-ttu-id="348a1-174">`Errors`: `Error`, `Exception`</span><span class="sxs-lookup"><span data-stu-id="348a1-174">`Errors`: `Error`, `Exception`</span></span>

<span data-ttu-id="348a1-175">Esses valores são definidos como uma enumeração baseada em sinalizador.</span><span class="sxs-lookup"><span data-stu-id="348a1-175">These values are defined as a flag-based enumeration.</span></span> <span data-ttu-id="348a1-176">Você pode combinar vários valores juntos para definir vários sinalizadores usando esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="348a1-176">You can combine multiple values together to set multiple flags using this parameter.</span></span> <span data-ttu-id="348a1-177">Os valores podem ser passados para o parâmetro de **opção** como uma matriz de valores ou como uma cadeia de caracteres separada por vírgulas desses valores.</span><span class="sxs-lookup"><span data-stu-id="348a1-177">The values can be passed to the **Option** parameter as an array of values or as a comma-separated string of those values.</span></span> <span data-ttu-id="348a1-178">O cmdlet combinará os valores usando uma operação binary ou.</span><span class="sxs-lookup"><span data-stu-id="348a1-178">The cmdlet will combine the values using a binary-OR operation.</span></span> <span data-ttu-id="348a1-179">Passar valores como uma matriz é a opção mais simples e também permite que você use a conclusão de tabulação nos valores.</span><span class="sxs-lookup"><span data-stu-id="348a1-179">Passing values as an array is the simplest option and also allows you to use tab-completion on the values.</span></span>

```yaml
Type: System.Management.Automation.PSTraceSourceOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, Constructor, Dispose, Finalizer, Method, Property, Delegates, Events, Exception, Lock, Error, Errors, Warning, Verbose, WriteLine, Data, Scope, ExecutionFlow, Assert, All

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="348a1-180">-PSHost</span><span class="sxs-lookup"><span data-stu-id="348a1-180">-PSHost</span></span>

<span data-ttu-id="348a1-181">Indica que o cmdlet envia a saída de rastreamento para o host do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="348a1-181">Indicates that the cmdlet sends the trace output to the PowerShell host.</span></span> <span data-ttu-id="348a1-182">Esse parâmetro também seleciona o ouvinte de rastreamento PSHost.</span><span class="sxs-lookup"><span data-stu-id="348a1-182">This parameter also selects the PSHost trace listener.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="348a1-183">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="348a1-183">CommonParameters</span></span>

<span data-ttu-id="348a1-184">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="348a1-184">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="348a1-185">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="348a1-185">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="348a1-186">Entradas</span><span class="sxs-lookup"><span data-stu-id="348a1-186">Inputs</span></span>

### <span data-ttu-id="348a1-187">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="348a1-187">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="348a1-188">É possível canalizar objetos que representam a entrada para a expressão para `Trace-Command` .</span><span class="sxs-lookup"><span data-stu-id="348a1-188">You can pipe objects that represent input to the expression to `Trace-Command`.</span></span>

## <span data-ttu-id="348a1-189">Saídas</span><span class="sxs-lookup"><span data-stu-id="348a1-189">Outputs</span></span>

### <span data-ttu-id="348a1-190">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="348a1-190">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="348a1-191">Retorna o rastreamento de comando no fluxo de depuração.</span><span class="sxs-lookup"><span data-stu-id="348a1-191">Returns the command trace in the debug stream.</span></span>

## <span data-ttu-id="348a1-192">Observações</span><span class="sxs-lookup"><span data-stu-id="348a1-192">Notes</span></span>

- <span data-ttu-id="348a1-193">O rastreamento é um método utilizado pelos desenvolvedores para depurar e aprimorar os programas.</span><span class="sxs-lookup"><span data-stu-id="348a1-193">Tracing is a method that developers use to debug and refine programs.</span></span> <span data-ttu-id="348a1-194">Ao realizar o rastreamento, o componente gera mensagens detalhadas sobre cada etapa no seu processamento interno.</span><span class="sxs-lookup"><span data-stu-id="348a1-194">When tracing, the program generates detailed messages about each step in its internal processing.</span></span>

- <span data-ttu-id="348a1-195">Os cmdlets de rastreamento do PowerShell são projetados para ajudar os desenvolvedores do PowerShell, mas estão disponíveis para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="348a1-195">The PowerShell tracing cmdlets are designed to help PowerShell developers, but they are available to all users.</span></span> <span data-ttu-id="348a1-196">Eles permitem monitorar quase todos os aspectos da funcionalidade do shell.</span><span class="sxs-lookup"><span data-stu-id="348a1-196">They let you monitor nearly every aspect of the functionality of the shell.</span></span>

- <span data-ttu-id="348a1-197">Para localizar os componentes do PowerShell que estão habilitados para rastreamento, digite `Get-Help Get-TraceSource` .</span><span class="sxs-lookup"><span data-stu-id="348a1-197">To find the PowerShell components that are enabled for tracing, type `Get-Help Get-TraceSource`.</span></span>

  <span data-ttu-id="348a1-198">Uma origem de rastreamento é a parte de cada componente do PowerShell que gerencia o rastreamento e gera mensagens de rastreamento para o componente.</span><span class="sxs-lookup"><span data-stu-id="348a1-198">A trace source is the part of each PowerShell component that manages tracing and generates trace messages for the component.</span></span> <span data-ttu-id="348a1-199">Para rastrear um componente, você deve identificar sua origem de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="348a1-199">To trace a component, you identify its trace source.</span></span>

  <span data-ttu-id="348a1-200">Um ouvinte de rastreamento recebe a saída do rastreamento e o exibe para o usuário.</span><span class="sxs-lookup"><span data-stu-id="348a1-200">A trace listener receives the output of the trace and displays it to the user.</span></span> <span data-ttu-id="348a1-201">Você pode optar por enviar os dados de rastreamento para um modo de usuário ou depurador de modo kernel, para o host ou console, para um arquivo ou para um ouvinte personalizado derivado da classe **System. Diagnostics. TraceListener** .</span><span class="sxs-lookup"><span data-stu-id="348a1-201">You can elect to send the trace data to a user-mode or kernel-mode debugger, to the host or console, to a file, or to a custom listener derived from the **System.Diagnostics.TraceListener** class.</span></span>

- <span data-ttu-id="348a1-202">Quando você usa o conjunto de parâmetros commandSet, o PowerShell processa o comando da mesma forma que seria processado em um pipeline.</span><span class="sxs-lookup"><span data-stu-id="348a1-202">When you use the commandSet parameter set, PowerShell processes the command just as it would be processed in a pipeline.</span></span> <span data-ttu-id="348a1-203">Por exemplo, a descoberta de comando não é repetida para cada objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="348a1-203">For example, command discovery is not repeated for each incoming object.</span></span>

- <span data-ttu-id="348a1-204">Os nomes dos parâmetros **Name**, **expression**, **Option** e **Command** são opcionais.</span><span class="sxs-lookup"><span data-stu-id="348a1-204">The names of the **Name**, **Expression**, **Option**, and **Command** parameters are optional.</span></span> <span data-ttu-id="348a1-205">Se você omitir os nomes de parâmetro, os valores de parâmetro não nomeados deverão aparecer nesta ordem: **nome**, **expressão**, **opção** ou **nome**, **comando**, **opção**.</span><span class="sxs-lookup"><span data-stu-id="348a1-205">If you omit the parameter names, the unnamed parameter values must appear in this order: **Name**, **Expression**, **Option** or **Name**, **Command**, **Option**.</span></span> <span data-ttu-id="348a1-206">Se você incluir os nomes dos parâmetros, os parâmetros podem aparecer em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="348a1-206">If you include the parameter names, the parameters can appear in any order.</span></span>

## <span data-ttu-id="348a1-207">Links Relacionados</span><span class="sxs-lookup"><span data-stu-id="348a1-207">Related Links</span></span>

[<span data-ttu-id="348a1-208">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="348a1-208">Get-TraceSource</span></span>](Get-TraceSource.md)

[<span data-ttu-id="348a1-209">Measure-Command</span><span class="sxs-lookup"><span data-stu-id="348a1-209">Measure-Command</span></span>](Measure-Command.md)

[<span data-ttu-id="348a1-210">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="348a1-210">Set-TraceSource</span></span>](Set-TraceSource.md)

