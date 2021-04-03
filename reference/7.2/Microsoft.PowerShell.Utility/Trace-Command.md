---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/01/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/trace-command?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Trace-Command
ms.openlocfilehash: 97571023c1428de5db0c2e6e13e285cafe609843
ms.sourcegitcommit: 5b48fe7b2593581b7d4f7dd7c22206d8a45bb8af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "106184402"
---
# <span data-ttu-id="16f5d-102">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="16f5d-102">Trace-Command</span></span>

## <span data-ttu-id="16f5d-103">Sinopse</span><span class="sxs-lookup"><span data-stu-id="16f5d-103">Synopsis</span></span>
<span data-ttu-id="16f5d-104">Configura e inicia um rastreamento da expressão ou comando especificado.</span><span class="sxs-lookup"><span data-stu-id="16f5d-104">Configures and starts a trace of the specified expression or command.</span></span>

## <span data-ttu-id="16f5d-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="16f5d-105">Syntax</span></span>

### <span data-ttu-id="16f5d-106">expressionset (padrão)</span><span class="sxs-lookup"><span data-stu-id="16f5d-106">expressionSet (Default)</span></span>

```
Trace-Command [-InputObject <PSObject>] [-Name] <String[]> [[-Option] <PSTraceSourceOptions>]
 [-Expression] <ScriptBlock> [-ListenerOption <TraceOptions>] [-FilePath <String>] [-Force] [-Debugger]
 [-PSHost] [<CommonParameters>]
```

### <span data-ttu-id="16f5d-107">commandSet</span><span class="sxs-lookup"><span data-stu-id="16f5d-107">commandSet</span></span>

```
Trace-Command [-InputObject <PSObject>] [-Name] <String[]> [[-Option] <PSTraceSourceOptions>]
 [-Command] <String> [-ArgumentList <Object[]>] [-ListenerOption <TraceOptions>] [-FilePath <String>] [-Force]
 [-Debugger] [-PSHost] [<CommonParameters>]
```

## <span data-ttu-id="16f5d-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="16f5d-108">Description</span></span>

<span data-ttu-id="16f5d-109">O `Trace-Command` cmdlet configura e inicia um rastreamento da expressão ou do comando especificado.</span><span class="sxs-lookup"><span data-stu-id="16f5d-109">The `Trace-Command` cmdlet configures and starts a trace of the specified expression or command.</span></span>
<span data-ttu-id="16f5d-110">Ele funciona como Set-TraceSource, exceto que se aplica apenas ao comando especificado.</span><span class="sxs-lookup"><span data-stu-id="16f5d-110">It works like Set-TraceSource, except that it applies only to the specified command.</span></span>

## <span data-ttu-id="16f5d-111">Exemplos</span><span class="sxs-lookup"><span data-stu-id="16f5d-111">Examples</span></span>

### <span data-ttu-id="16f5d-112">Exemplo 1: rastrear o processamento de metadados, a associação de parâmetro e uma expressão</span><span class="sxs-lookup"><span data-stu-id="16f5d-112">Example 1: Trace metadata processing, parameter binding, and an expression</span></span>

<span data-ttu-id="16f5d-113">Este exemplo inicia um rastreamento de processamento de metadados, associação de parâmetro e criação de cmdlet e destruição da `Get-Process Notepad` expressão.</span><span class="sxs-lookup"><span data-stu-id="16f5d-113">This example starts a trace of metadata processing, parameter binding, and cmdlet creation and destruction of the `Get-Process Notepad` expression.</span></span>

```powershell
Trace-Command -Name metadata,parameterbinding,cmdlet -Expression {Get-Process Notepad} -PSHost
```

<span data-ttu-id="16f5d-114">Ele usa o parâmetro **Name** para especificar as fontes de rastreamento, o parâmetro **expression** para especificar o comando e o parâmetro **PSHost** para enviar a saída para o console.</span><span class="sxs-lookup"><span data-stu-id="16f5d-114">It uses the **Name** parameter to specify the trace sources, the **Expression** parameter to specify the command, and the **PSHost** parameter to send the output to the console.</span></span> <span data-ttu-id="16f5d-115">Como não especifica nenhuma opção de rastreamento ou opções de ouvinte, o comando usa os padrões:</span><span class="sxs-lookup"><span data-stu-id="16f5d-115">Because it does not specify any tracing options or listener options, the command uses the defaults:</span></span>

- <span data-ttu-id="16f5d-116">Tudo para as opções de rastreamento</span><span class="sxs-lookup"><span data-stu-id="16f5d-116">All for the tracing options</span></span>
- <span data-ttu-id="16f5d-117">Nenhuma para as opções de ouvinte</span><span class="sxs-lookup"><span data-stu-id="16f5d-117">None for the listener options</span></span>

### <span data-ttu-id="16f5d-118">Exemplo 2: rastrear as ações de operações de parâmetros</span><span class="sxs-lookup"><span data-stu-id="16f5d-118">Example 2: Trace the actions of ParameterBinding operations</span></span>

<span data-ttu-id="16f5d-119">Este exemplo rastreia as ações das operações de **ParameterBinding** do PowerShell enquanto processa uma `Get-Alias` expressão que usa a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="16f5d-119">This example traces the actions of the **ParameterBinding** operations of PowerShell while it processes a `Get-Alias` expression that takes input from the pipeline.</span></span>

```powershell
$A = "i*"
Trace-Command ParameterBinding {Get-Alias $Input} -PSHost -InputObject $A
```

<span data-ttu-id="16f5d-120">No `Trace-Command` , o parâmetro **InputObject** passa um objeto para a expressão que está sendo processada durante o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="16f5d-120">In `Trace-Command`, the **InputObject** parameter passes an object to the expression that is being processed during the trace.</span></span>

<span data-ttu-id="16f5d-121">O primeiro comando armazena a cadeia de caracteres `i*` na `$A` variável.</span><span class="sxs-lookup"><span data-stu-id="16f5d-121">The first command stores the string `i*` in the `$A` variable.</span></span> <span data-ttu-id="16f5d-122">O segundo comando usa o `Trace-Command` cmdlet com a origem de rastreamento de ParameterBinding.</span><span class="sxs-lookup"><span data-stu-id="16f5d-122">The second command uses the `Trace-Command` cmdlet with the ParameterBinding trace source.</span></span> <span data-ttu-id="16f5d-123">O parâmetro **PSHost** envia a saída para o console.</span><span class="sxs-lookup"><span data-stu-id="16f5d-123">The **PSHost** parameter sends the output to the console.</span></span>

<span data-ttu-id="16f5d-124">A expressão que está sendo processada é `Get-Alias $Input` , em que a `$Input` variável é associada ao parâmetro **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="16f5d-124">The expression being processed is `Get-Alias $Input`, where the `$Input` variable is associated with the **InputObject** parameter.</span></span> <span data-ttu-id="16f5d-125">O parâmetro **InputObject** passa a variável `$A` para a expressão.</span><span class="sxs-lookup"><span data-stu-id="16f5d-125">The **InputObject** parameter passes the variable `$A` to the expression.</span></span> <span data-ttu-id="16f5d-126">Na verdade, o comando que está sendo processado durante o rastreamento é `Get-Alias -InputObject $A" or "$A | Get-Alias` .</span><span class="sxs-lookup"><span data-stu-id="16f5d-126">In effect, the command being processed during the trace is `Get-Alias -InputObject $A" or "$A | Get-Alias`.</span></span>

## <span data-ttu-id="16f5d-127">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="16f5d-127">Parameters</span></span>

### <span data-ttu-id="16f5d-128">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="16f5d-128">-ArgumentList</span></span>

<span data-ttu-id="16f5d-129">Especifica os parâmetros e valores de parâmetro para o comando que está sendo rastreado.</span><span class="sxs-lookup"><span data-stu-id="16f5d-129">Specifies the parameters and parameter values for the command being traced.</span></span> <span data-ttu-id="16f5d-130">O alias para **ArgumentList** é **Args**.</span><span class="sxs-lookup"><span data-stu-id="16f5d-130">The alias for **ArgumentList** is **Args**.</span></span> <span data-ttu-id="16f5d-131">Esse recurso é especialmente útil para depuração parâmetros dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="16f5d-131">This feature is especially useful for debugging dynamic parameters.</span></span>

<span data-ttu-id="16f5d-132">Para obter mais informações sobre o comportamento de **ArgumentList**, consulte [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="16f5d-132">For more information about the behavior of **ArgumentList**, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).</span></span>

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

### <span data-ttu-id="16f5d-133">-Command</span><span class="sxs-lookup"><span data-stu-id="16f5d-133">-Command</span></span>

<span data-ttu-id="16f5d-134">Especifica um comando que está sendo processado durante o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="16f5d-134">Specifies a command that is being processed during the trace.</span></span>

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

### <span data-ttu-id="16f5d-135">-Depurador</span><span class="sxs-lookup"><span data-stu-id="16f5d-135">-Debugger</span></span>

<span data-ttu-id="16f5d-136">Indica que o cmdlet envia a saída de rastreamento para o depurador.</span><span class="sxs-lookup"><span data-stu-id="16f5d-136">Indicates that the cmdlet sends the trace output to the debugger.</span></span> <span data-ttu-id="16f5d-137">Você pode exibir a saída em qualquer modo de usuário ou depurador do modo kernel, ou ainda no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="16f5d-137">You can view the output in any user-mode or kernel mode debugger or in Visual Studio.</span></span> <span data-ttu-id="16f5d-138">Esse parâmetro também seleciona o ouvinte de rastreamento padrão.</span><span class="sxs-lookup"><span data-stu-id="16f5d-138">This parameter also selects the default trace listener.</span></span>

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

### <span data-ttu-id="16f5d-139">-Expressão</span><span class="sxs-lookup"><span data-stu-id="16f5d-139">-Expression</span></span>

<span data-ttu-id="16f5d-140">Especifica a expressão que está sendo processada durante o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="16f5d-140">Specifies the expression that is being processed during the trace.</span></span> <span data-ttu-id="16f5d-141">Coloque a expressão entre chaves ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="16f5d-141">Enclose the expression in braces (`{}`).</span></span>

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

### <span data-ttu-id="16f5d-142">-FilePath</span><span class="sxs-lookup"><span data-stu-id="16f5d-142">-FilePath</span></span>

<span data-ttu-id="16f5d-143">Especifica um arquivo para o qual o cmdlet envia a saída de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="16f5d-143">Specifies a file that the cmdlet sends the trace output to.</span></span> <span data-ttu-id="16f5d-144">Esse parâmetro também seleciona o ouvinte de rastreamento do arquivo.</span><span class="sxs-lookup"><span data-stu-id="16f5d-144">This parameter also selects the file trace listener.</span></span>

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

### <span data-ttu-id="16f5d-145">-Force</span><span class="sxs-lookup"><span data-stu-id="16f5d-145">-Force</span></span>

<span data-ttu-id="16f5d-146">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="16f5d-146">Forces the command to run without asking for user confirmation.</span></span> <span data-ttu-id="16f5d-147">Usado com o parâmetro **FilePath** .</span><span class="sxs-lookup"><span data-stu-id="16f5d-147">Used with the **FilePath** parameter.</span></span> <span data-ttu-id="16f5d-148">Mesmo usando o parâmetro **Force** , o cmdlet não pode substituir as restrições de segurança.</span><span class="sxs-lookup"><span data-stu-id="16f5d-148">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

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

### <span data-ttu-id="16f5d-149">-InputObject</span><span class="sxs-lookup"><span data-stu-id="16f5d-149">-InputObject</span></span>

<span data-ttu-id="16f5d-150">Especifica a entrada para a expressão que está sendo processada durante o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="16f5d-150">Specifies input to the expression that is being processed during the trace.</span></span> <span data-ttu-id="16f5d-151">Você pode inserir uma variável que representa a entrada que aceita a expressão ou passar um objeto por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="16f5d-151">You can enter a variable that represents the input that the expression accepts, or pass an object through the pipeline.</span></span>

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

### <span data-ttu-id="16f5d-152">-ListenerOption</span><span class="sxs-lookup"><span data-stu-id="16f5d-152">-ListenerOption</span></span>

<span data-ttu-id="16f5d-153">Especifica dados opcionais para o prefixo de cada mensagem de rastreamento na saída.</span><span class="sxs-lookup"><span data-stu-id="16f5d-153">Specifies optional data to the prefix of each trace message in the output.</span></span> <span data-ttu-id="16f5d-154">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="16f5d-154">The acceptable values for this parameter are:</span></span>

- `None`
- `LogicalOperationStack`
- `DateTime`
- `Timestamp`
- `ProcessId`
- `ThreadId`
- `Callstack`

<span data-ttu-id="16f5d-155">`None` é o padrão.</span><span class="sxs-lookup"><span data-stu-id="16f5d-155">`None` is the default.</span></span>

<span data-ttu-id="16f5d-156">Esses valores são definidos como uma enumeração baseada em sinalizador.</span><span class="sxs-lookup"><span data-stu-id="16f5d-156">These values are defined as a flag-based enumeration.</span></span> <span data-ttu-id="16f5d-157">Você pode combinar vários valores juntos para definir vários sinalizadores usando esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="16f5d-157">You can combine multiple values together to set multiple flags using this parameter.</span></span> <span data-ttu-id="16f5d-158">Os valores podem ser passados para o parâmetro **ListenerOption** como uma matriz de valores ou como uma cadeia de caracteres separada por vírgulas desses valores.</span><span class="sxs-lookup"><span data-stu-id="16f5d-158">The values can be passed to the **ListenerOption** parameter as an array of values or as a comma-separated string of those values.</span></span> <span data-ttu-id="16f5d-159">O cmdlet combinará os valores usando uma operação binary ou.</span><span class="sxs-lookup"><span data-stu-id="16f5d-159">The cmdlet will combine the values using a binary-OR operation.</span></span> <span data-ttu-id="16f5d-160">Passar valores como uma matriz é a opção mais simples e também permite que você use a conclusão de tabulação nos valores.</span><span class="sxs-lookup"><span data-stu-id="16f5d-160">Passing values as an array is the simplest option and also allows you to use tab-completion on the values.</span></span>

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

### <span data-ttu-id="16f5d-161">-Name</span><span class="sxs-lookup"><span data-stu-id="16f5d-161">-Name</span></span>

<span data-ttu-id="16f5d-162">Especifica uma matriz de componentes do PowerShell que são rastreados.</span><span class="sxs-lookup"><span data-stu-id="16f5d-162">Specifies an array of PowerShell components that are traced.</span></span> <span data-ttu-id="16f5d-163">Insira o nome da origem de rastreamento de cada componente.</span><span class="sxs-lookup"><span data-stu-id="16f5d-163">Enter the name of the trace source of each component.</span></span> <span data-ttu-id="16f5d-164">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="16f5d-164">Wildcards are permitted.</span></span> <span data-ttu-id="16f5d-165">Para localizar as fontes de rastreamento no seu computador, digite `Get-TraceSource` .</span><span class="sxs-lookup"><span data-stu-id="16f5d-165">To find the trace sources on your computer, type `Get-TraceSource`.</span></span>

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

### <span data-ttu-id="16f5d-166">-Opção</span><span class="sxs-lookup"><span data-stu-id="16f5d-166">-Option</span></span>

<span data-ttu-id="16f5d-167">Determina o tipo de eventos que são rastreados.</span><span class="sxs-lookup"><span data-stu-id="16f5d-167">Determines the type of events that are traced.</span></span> <span data-ttu-id="16f5d-168">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="16f5d-168">The acceptable values for this parameter are:</span></span>

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

<span data-ttu-id="16f5d-169">`All` é o padrão.</span><span class="sxs-lookup"><span data-stu-id="16f5d-169">`All` is the default.</span></span>

<span data-ttu-id="16f5d-170">Os seguintes valores são combinações de outros valores:</span><span class="sxs-lookup"><span data-stu-id="16f5d-170">The following values are combinations of other values:</span></span>

- <span data-ttu-id="16f5d-171">`ExecutionFlow`: `Constructor`, `Dispose`, `Finalizer`, `Method`, `Delegates`, `Events`, `Scope`</span><span class="sxs-lookup"><span data-stu-id="16f5d-171">`ExecutionFlow`: `Constructor`, `Dispose`, `Finalizer`, `Method`, `Delegates`, `Events`, `Scope`</span></span>
- <span data-ttu-id="16f5d-172">`Data`: `Constructor`, `Dispose`, `Finalizer`, `Property`, `Verbose`, `WriteLine`</span><span class="sxs-lookup"><span data-stu-id="16f5d-172">`Data`: `Constructor`, `Dispose`, `Finalizer`, `Property`, `Verbose`, `WriteLine`</span></span>
- <span data-ttu-id="16f5d-173">`Errors`: `Error`, `Exception`</span><span class="sxs-lookup"><span data-stu-id="16f5d-173">`Errors`: `Error`, `Exception`</span></span>

<span data-ttu-id="16f5d-174">Esses valores são definidos como uma enumeração baseada em sinalizador.</span><span class="sxs-lookup"><span data-stu-id="16f5d-174">These values are defined as a flag-based enumeration.</span></span> <span data-ttu-id="16f5d-175">Você pode combinar vários valores juntos para definir vários sinalizadores usando esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="16f5d-175">You can combine multiple values together to set multiple flags using this parameter.</span></span> <span data-ttu-id="16f5d-176">Os valores podem ser passados para o parâmetro de **opção** como uma matriz de valores ou como uma cadeia de caracteres separada por vírgulas desses valores.</span><span class="sxs-lookup"><span data-stu-id="16f5d-176">The values can be passed to the **Option** parameter as an array of values or as a comma-separated string of those values.</span></span> <span data-ttu-id="16f5d-177">O cmdlet combinará os valores usando uma operação binary ou.</span><span class="sxs-lookup"><span data-stu-id="16f5d-177">The cmdlet will combine the values using a binary-OR operation.</span></span> <span data-ttu-id="16f5d-178">Passar valores como uma matriz é a opção mais simples e também permite que você use a conclusão de tabulação nos valores.</span><span class="sxs-lookup"><span data-stu-id="16f5d-178">Passing values as an array is the simplest option and also allows you to use tab-completion on the values.</span></span>

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

### <span data-ttu-id="16f5d-179">-PSHost</span><span class="sxs-lookup"><span data-stu-id="16f5d-179">-PSHost</span></span>

<span data-ttu-id="16f5d-180">Indica que o cmdlet envia a saída de rastreamento para o host do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16f5d-180">Indicates that the cmdlet sends the trace output to the PowerShell host.</span></span> <span data-ttu-id="16f5d-181">Esse parâmetro também seleciona o ouvinte de rastreamento PSHost.</span><span class="sxs-lookup"><span data-stu-id="16f5d-181">This parameter also selects the PSHost trace listener.</span></span>

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

### <span data-ttu-id="16f5d-182">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="16f5d-182">CommonParameters</span></span>

<span data-ttu-id="16f5d-183">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="16f5d-183">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="16f5d-184">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="16f5d-184">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="16f5d-185">Entradas</span><span class="sxs-lookup"><span data-stu-id="16f5d-185">Inputs</span></span>

### <span data-ttu-id="16f5d-186">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="16f5d-186">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="16f5d-187">É possível canalizar objetos que representam a entrada para a expressão para `Trace-Command` .</span><span class="sxs-lookup"><span data-stu-id="16f5d-187">You can pipe objects that represent input to the expression to `Trace-Command`.</span></span>

## <span data-ttu-id="16f5d-188">Saídas</span><span class="sxs-lookup"><span data-stu-id="16f5d-188">Outputs</span></span>

### <span data-ttu-id="16f5d-189">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="16f5d-189">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="16f5d-190">Retorna o rastreamento de comando no fluxo de depuração.</span><span class="sxs-lookup"><span data-stu-id="16f5d-190">Returns the command trace in the debug stream.</span></span>

## <span data-ttu-id="16f5d-191">Observações</span><span class="sxs-lookup"><span data-stu-id="16f5d-191">Notes</span></span>

- <span data-ttu-id="16f5d-192">O rastreamento é um método utilizado pelos desenvolvedores para depurar e aprimorar os programas.</span><span class="sxs-lookup"><span data-stu-id="16f5d-192">Tracing is a method that developers use to debug and refine programs.</span></span> <span data-ttu-id="16f5d-193">Ao realizar o rastreamento, o componente gera mensagens detalhadas sobre cada etapa no seu processamento interno.</span><span class="sxs-lookup"><span data-stu-id="16f5d-193">When tracing, the program generates detailed messages about each step in its internal processing.</span></span>

- <span data-ttu-id="16f5d-194">Os cmdlets de rastreamento do PowerShell são projetados para ajudar os desenvolvedores do PowerShell, mas estão disponíveis para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="16f5d-194">The PowerShell tracing cmdlets are designed to help PowerShell developers, but they are available to all users.</span></span> <span data-ttu-id="16f5d-195">Eles permitem monitorar quase todos os aspectos da funcionalidade do shell.</span><span class="sxs-lookup"><span data-stu-id="16f5d-195">They let you monitor nearly every aspect of the functionality of the shell.</span></span>

- <span data-ttu-id="16f5d-196">Para localizar os componentes do PowerShell que estão habilitados para rastreamento, digite `Get-Help Get-TraceSource` .</span><span class="sxs-lookup"><span data-stu-id="16f5d-196">To find the PowerShell components that are enabled for tracing, type `Get-Help Get-TraceSource`.</span></span>

  <span data-ttu-id="16f5d-197">Uma origem de rastreamento é a parte de cada componente do PowerShell que gerencia o rastreamento e gera mensagens de rastreamento para o componente.</span><span class="sxs-lookup"><span data-stu-id="16f5d-197">A trace source is the part of each PowerShell component that manages tracing and generates trace messages for the component.</span></span> <span data-ttu-id="16f5d-198">Para rastrear um componente, você deve identificar sua origem de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="16f5d-198">To trace a component, you identify its trace source.</span></span>

  <span data-ttu-id="16f5d-199">Um ouvinte de rastreamento recebe a saída do rastreamento e o exibe para o usuário.</span><span class="sxs-lookup"><span data-stu-id="16f5d-199">A trace listener receives the output of the trace and displays it to the user.</span></span> <span data-ttu-id="16f5d-200">Você pode optar por enviar os dados de rastreamento para um modo de usuário ou depurador de modo kernel, para o host ou console, para um arquivo ou para um ouvinte personalizado derivado da classe **System. Diagnostics. TraceListener** .</span><span class="sxs-lookup"><span data-stu-id="16f5d-200">You can elect to send the trace data to a user-mode or kernel-mode debugger, to the host or console, to a file, or to a custom listener derived from the **System.Diagnostics.TraceListener** class.</span></span>

- <span data-ttu-id="16f5d-201">Quando você usa o conjunto de parâmetros commandSet, o PowerShell processa o comando da mesma forma que seria processado em um pipeline.</span><span class="sxs-lookup"><span data-stu-id="16f5d-201">When you use the commandSet parameter set, PowerShell processes the command just as it would be processed in a pipeline.</span></span> <span data-ttu-id="16f5d-202">Por exemplo, a descoberta de comando não é repetida para cada objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="16f5d-202">For example, command discovery is not repeated for each incoming object.</span></span>

- <span data-ttu-id="16f5d-203">Os nomes dos parâmetros **Name**, **expression**, **Option** e **Command** são opcionais.</span><span class="sxs-lookup"><span data-stu-id="16f5d-203">The names of the **Name**, **Expression**, **Option**, and **Command** parameters are optional.</span></span> <span data-ttu-id="16f5d-204">Se você omitir os nomes de parâmetro, os valores de parâmetro não nomeados deverão aparecer nesta ordem: **nome**, **expressão**, **opção** ou **nome**, **comando**, **opção**.</span><span class="sxs-lookup"><span data-stu-id="16f5d-204">If you omit the parameter names, the unnamed parameter values must appear in this order: **Name**, **Expression**, **Option** or **Name**, **Command**, **Option**.</span></span> <span data-ttu-id="16f5d-205">Se você incluir os nomes dos parâmetros, os parâmetros podem aparecer em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="16f5d-205">If you include the parameter names, the parameters can appear in any order.</span></span>

## <span data-ttu-id="16f5d-206">Links Relacionados</span><span class="sxs-lookup"><span data-stu-id="16f5d-206">Related Links</span></span>

[<span data-ttu-id="16f5d-207">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="16f5d-207">Get-TraceSource</span></span>](Get-TraceSource.md)

[<span data-ttu-id="16f5d-208">Measure-Command</span><span class="sxs-lookup"><span data-stu-id="16f5d-208">Measure-Command</span></span>](Measure-Command.md)

[<span data-ttu-id="16f5d-209">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="16f5d-209">Set-TraceSource</span></span>](Set-TraceSource.md)

