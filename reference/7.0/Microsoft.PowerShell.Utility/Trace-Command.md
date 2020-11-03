---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/trace-command?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Trace-Command
ms.openlocfilehash: f3f9e47ac6d969dc08518bf97bb87699fb04ade8
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192943"
---
# <span data-ttu-id="85e79-103">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="85e79-103">Trace-Command</span></span>

## <span data-ttu-id="85e79-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="85e79-104">SYNOPSIS</span></span>
<span data-ttu-id="85e79-105">Configura e inicia um rastreamento da expressão ou comando especificado.</span><span class="sxs-lookup"><span data-stu-id="85e79-105">Configures and starts a trace of the specified expression or command.</span></span>

## <span data-ttu-id="85e79-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="85e79-106">SYNTAX</span></span>

### <span data-ttu-id="85e79-107">expressionset (padrão)</span><span class="sxs-lookup"><span data-stu-id="85e79-107">expressionSet (Default)</span></span>

```
Trace-Command [-InputObject <PSObject>] [-Name] <String[]> [[-Option] <PSTraceSourceOptions>]
 [-Expression] <ScriptBlock> [-ListenerOption <TraceOptions>] [-FilePath <String>] [-Force] [-Debugger]
 [-PSHost] [<CommonParameters>]
```

### <span data-ttu-id="85e79-108">commandSet</span><span class="sxs-lookup"><span data-stu-id="85e79-108">commandSet</span></span>

```
Trace-Command [-InputObject <PSObject>] [-Name] <String[]> [[-Option] <PSTraceSourceOptions>]
 [-Command] <String> [-ArgumentList <Object[]>] [-ListenerOption <TraceOptions>] [-FilePath <String>] [-Force]
 [-Debugger] [-PSHost] [<CommonParameters>]
```

## <span data-ttu-id="85e79-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="85e79-109">DESCRIPTION</span></span>
<span data-ttu-id="85e79-110">O `Trace-Command` cmdlet configura e inicia um rastreamento da expressão ou do comando especificado.</span><span class="sxs-lookup"><span data-stu-id="85e79-110">The `Trace-Command` cmdlet configures and starts a trace of the specified expression or command.</span></span>
<span data-ttu-id="85e79-111">Ele funciona como Set-TraceSource, exceto que se aplica apenas ao comando especificado.</span><span class="sxs-lookup"><span data-stu-id="85e79-111">It works like Set-TraceSource, except that it applies only to the specified command.</span></span>

## <span data-ttu-id="85e79-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="85e79-112">EXAMPLES</span></span>

### <span data-ttu-id="85e79-113">Exemplo 1: rastrear o processamento de metadados, a associação de parâmetro e uma expressão</span><span class="sxs-lookup"><span data-stu-id="85e79-113">Example 1: Trace metadata processing, parameter binding, and an expression</span></span>

<span data-ttu-id="85e79-114">Este exemplo inicia um rastreamento de processamento de metadados, associação de parâmetro e criação de cmdlet e destruição da `Get-Process Notepad` expressão.</span><span class="sxs-lookup"><span data-stu-id="85e79-114">This example starts a trace of metadata processing, parameter binding, and cmdlet creation and destruction of the `Get-Process Notepad` expression.</span></span>

```powershell
Trace-Command -Name metadata,parameterbinding,cmdlet -Expression {Get-Process Notepad} -PSHost
```

<span data-ttu-id="85e79-115">Ele usa o parâmetro **Name** para especificar as fontes de rastreamento, o parâmetro **expression** para especificar o comando e o parâmetro **PSHost** para enviar a saída para o console.</span><span class="sxs-lookup"><span data-stu-id="85e79-115">It uses the **Name** parameter to specify the trace sources, the **Expression** parameter to specify the command, and the **PSHost** parameter to send the output to the console.</span></span> <span data-ttu-id="85e79-116">Como não especifica nenhuma opção de rastreamento ou opções de ouvinte, o comando usa os padrões:</span><span class="sxs-lookup"><span data-stu-id="85e79-116">Because it does not specify any tracing options or listener options, the command uses the defaults:</span></span>

- <span data-ttu-id="85e79-117">Tudo para as opções de rastreamento</span><span class="sxs-lookup"><span data-stu-id="85e79-117">All for the tracing options</span></span>
- <span data-ttu-id="85e79-118">Nenhuma para as opções de ouvinte</span><span class="sxs-lookup"><span data-stu-id="85e79-118">None for the listener options</span></span>

### <span data-ttu-id="85e79-119">Exemplo 2: rastrear as ações de operações de parâmetros</span><span class="sxs-lookup"><span data-stu-id="85e79-119">Example 2: Trace the actions of ParameterBinding operations</span></span>

<span data-ttu-id="85e79-120">Este exemplo rastreia as ações das operações de **ParameterBinding** do PowerShell enquanto processa uma `Get-Alias` expressão que usa a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="85e79-120">This example traces the actions of the **ParameterBinding** operations of PowerShell while it processes a `Get-Alias` expression that takes input from the pipeline.</span></span>

```powershell
$A = "i*"
Trace-Command ParameterBinding {Get-Alias $Input} -PSHost -InputObject $A
```

<span data-ttu-id="85e79-121">No `Trace-Command` , o parâmetro **InputObject** passa um objeto para a expressão que está sendo processada durante o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="85e79-121">In `Trace-Command`, the **InputObject** parameter passes an object to the expression that is being processed during the trace.</span></span>

<span data-ttu-id="85e79-122">O primeiro comando armazena a cadeia de caracteres `i*` na `$A` variável.</span><span class="sxs-lookup"><span data-stu-id="85e79-122">The first command stores the string `i*` in the `$A` variable.</span></span> <span data-ttu-id="85e79-123">O segundo comando usa o `Trace-Command` cmdlet com a origem de rastreamento de ParameterBinding.</span><span class="sxs-lookup"><span data-stu-id="85e79-123">The second command uses the `Trace-Command` cmdlet with the ParameterBinding trace source.</span></span> <span data-ttu-id="85e79-124">O parâmetro **PSHost** envia a saída para o console.</span><span class="sxs-lookup"><span data-stu-id="85e79-124">The **PSHost** parameter sends the output to the console.</span></span>

<span data-ttu-id="85e79-125">A expressão que está sendo processada é `Get-Alias $Input` , em que a `$Input` variável é associada ao parâmetro **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="85e79-125">The expression being processed is `Get-Alias $Input`, where the `$Input` variable is associated with the **InputObject** parameter.</span></span> <span data-ttu-id="85e79-126">O parâmetro **InputObject** passa a variável `$A` para a expressão.</span><span class="sxs-lookup"><span data-stu-id="85e79-126">The **InputObject** parameter passes the variable `$A` to the expression.</span></span> <span data-ttu-id="85e79-127">Na verdade, o comando que está sendo processado durante o rastreamento é `Get-Alias -InputObject $A" or "$A | Get-Alias` .</span><span class="sxs-lookup"><span data-stu-id="85e79-127">In effect, the command being processed during the trace is `Get-Alias -InputObject $A" or "$A | Get-Alias`.</span></span>

## <span data-ttu-id="85e79-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="85e79-128">PARAMETERS</span></span>

### <span data-ttu-id="85e79-129">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="85e79-129">-ArgumentList</span></span>

<span data-ttu-id="85e79-130">Especifica os parâmetros e valores de parâmetro para o comando que está sendo rastreado.</span><span class="sxs-lookup"><span data-stu-id="85e79-130">Specifies the parameters and parameter values for the command being traced.</span></span> <span data-ttu-id="85e79-131">O alias para **ArgumentList** é **Args** .</span><span class="sxs-lookup"><span data-stu-id="85e79-131">The alias for **ArgumentList** is **Args** .</span></span> <span data-ttu-id="85e79-132">Esse recurso é especialmente útil para depuração parâmetros dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="85e79-132">This feature is especially useful for debugging dynamic parameters.</span></span>

<span data-ttu-id="85e79-133">Para obter mais informações sobre o comportamento de **ArgumentList** , consulte [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="85e79-133">For more information about the behavior of **ArgumentList** , see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).</span></span>

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

### <span data-ttu-id="85e79-134">-Command</span><span class="sxs-lookup"><span data-stu-id="85e79-134">-Command</span></span>

<span data-ttu-id="85e79-135">Especifica um comando que está sendo processado durante o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="85e79-135">Specifies a command that is being processed during the trace.</span></span>

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

### <span data-ttu-id="85e79-136">-Depurador</span><span class="sxs-lookup"><span data-stu-id="85e79-136">-Debugger</span></span>

<span data-ttu-id="85e79-137">Indica que o cmdlet envia a saída de rastreamento para o depurador.</span><span class="sxs-lookup"><span data-stu-id="85e79-137">Indicates that the cmdlet sends the trace output to the debugger.</span></span> <span data-ttu-id="85e79-138">Você pode exibir a saída em qualquer modo de usuário ou depurador do modo kernel, ou ainda no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="85e79-138">You can view the output in any user-mode or kernel mode debugger or in Visual Studio.</span></span> <span data-ttu-id="85e79-139">Esse parâmetro também seleciona o ouvinte de rastreamento padrão.</span><span class="sxs-lookup"><span data-stu-id="85e79-139">This parameter also selects the default trace listener.</span></span>

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

### <span data-ttu-id="85e79-140">-Expressão</span><span class="sxs-lookup"><span data-stu-id="85e79-140">-Expression</span></span>

<span data-ttu-id="85e79-141">Especifica a expressão que está sendo processada durante o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="85e79-141">Specifies the expression that is being processed during the trace.</span></span> <span data-ttu-id="85e79-142">Coloque a expressão entre chaves ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="85e79-142">Enclose the expression in braces (`{}`).</span></span>

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

### <span data-ttu-id="85e79-143">-FilePath</span><span class="sxs-lookup"><span data-stu-id="85e79-143">-FilePath</span></span>

<span data-ttu-id="85e79-144">Especifica um arquivo para o qual o cmdlet envia a saída de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="85e79-144">Specifies a file that the cmdlet sends the trace output to.</span></span> <span data-ttu-id="85e79-145">Esse parâmetro também seleciona o ouvinte de rastreamento do arquivo.</span><span class="sxs-lookup"><span data-stu-id="85e79-145">This parameter also selects the file trace listener.</span></span>

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

### <span data-ttu-id="85e79-146">-Force</span><span class="sxs-lookup"><span data-stu-id="85e79-146">-Force</span></span>

<span data-ttu-id="85e79-147">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="85e79-147">Forces the command to run without asking for user confirmation.</span></span> <span data-ttu-id="85e79-148">Usado com o parâmetro **FilePath** .</span><span class="sxs-lookup"><span data-stu-id="85e79-148">Used with the **FilePath** parameter.</span></span> <span data-ttu-id="85e79-149">Mesmo usando o parâmetro **Force** , o cmdlet não pode substituir as restrições de segurança.</span><span class="sxs-lookup"><span data-stu-id="85e79-149">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

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

### <span data-ttu-id="85e79-150">-InputObject</span><span class="sxs-lookup"><span data-stu-id="85e79-150">-InputObject</span></span>

<span data-ttu-id="85e79-151">Especifica a entrada para a expressão que está sendo processada durante o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="85e79-151">Specifies input to the expression that is being processed during the trace.</span></span> <span data-ttu-id="85e79-152">Você pode inserir uma variável que representa a entrada que aceita a expressão ou passar um objeto por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="85e79-152">You can enter a variable that represents the input that the expression accepts, or pass an object through the pipeline.</span></span>

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

### <span data-ttu-id="85e79-153">-ListenerOption</span><span class="sxs-lookup"><span data-stu-id="85e79-153">-ListenerOption</span></span>

<span data-ttu-id="85e79-154">Especifica dados opcionais para o prefixo de cada mensagem de rastreamento na saída.</span><span class="sxs-lookup"><span data-stu-id="85e79-154">Specifies optional data to the prefix of each trace message in the output.</span></span> <span data-ttu-id="85e79-155">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="85e79-155">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="85e79-156">Nenhum</span><span class="sxs-lookup"><span data-stu-id="85e79-156">None</span></span>
- <span data-ttu-id="85e79-157">LogicalOperationStack</span><span class="sxs-lookup"><span data-stu-id="85e79-157">LogicalOperationStack</span></span>
- <span data-ttu-id="85e79-158">Datetime</span><span class="sxs-lookup"><span data-stu-id="85e79-158">DateTime</span></span>
- <span data-ttu-id="85e79-159">Timestamp</span><span class="sxs-lookup"><span data-stu-id="85e79-159">Timestamp</span></span>
- <span data-ttu-id="85e79-160">ProcessId</span><span class="sxs-lookup"><span data-stu-id="85e79-160">ProcessId</span></span>
- <span data-ttu-id="85e79-161">ThreadId</span><span class="sxs-lookup"><span data-stu-id="85e79-161">ThreadId</span></span>
- <span data-ttu-id="85e79-162">Chamadas</span><span class="sxs-lookup"><span data-stu-id="85e79-162">Callstack</span></span>

<span data-ttu-id="85e79-163">**None** é o padrão.</span><span class="sxs-lookup"><span data-stu-id="85e79-163">**None** is the default.</span></span>

<span data-ttu-id="85e79-164">Para especificar várias opções, separe-as com vírgulas, mas sem espaços, e coloque-as entre aspas, como "ProcessID ThreadID".</span><span class="sxs-lookup"><span data-stu-id="85e79-164">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "ProcessID,ThreadID".</span></span>

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

### <span data-ttu-id="85e79-165">-Name</span><span class="sxs-lookup"><span data-stu-id="85e79-165">-Name</span></span>

<span data-ttu-id="85e79-166">Especifica uma matriz de componentes do PowerShell que são rastreados.</span><span class="sxs-lookup"><span data-stu-id="85e79-166">Specifies an array of PowerShell components that are traced.</span></span> <span data-ttu-id="85e79-167">Insira o nome da origem de rastreamento de cada componente.</span><span class="sxs-lookup"><span data-stu-id="85e79-167">Enter the name of the trace source of each component.</span></span> <span data-ttu-id="85e79-168">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="85e79-168">Wildcards are permitted.</span></span> <span data-ttu-id="85e79-169">Para localizar as fontes de rastreamento no seu computador, digite `Get-TraceSource` .</span><span class="sxs-lookup"><span data-stu-id="85e79-169">To find the trace sources on your computer, type `Get-TraceSource`.</span></span>

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

### <span data-ttu-id="85e79-170">-Opção</span><span class="sxs-lookup"><span data-stu-id="85e79-170">-Option</span></span>

<span data-ttu-id="85e79-171">Determina o tipo de eventos que são rastreados.</span><span class="sxs-lookup"><span data-stu-id="85e79-171">Determines the type of events that are traced.</span></span> <span data-ttu-id="85e79-172">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="85e79-172">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="85e79-173">Nenhum</span><span class="sxs-lookup"><span data-stu-id="85e79-173">None</span></span>
- <span data-ttu-id="85e79-174">Construtor</span><span class="sxs-lookup"><span data-stu-id="85e79-174">Constructor</span></span>
- <span data-ttu-id="85e79-175">Dispose</span><span class="sxs-lookup"><span data-stu-id="85e79-175">Dispose</span></span>
- <span data-ttu-id="85e79-176">Finalizer</span><span class="sxs-lookup"><span data-stu-id="85e79-176">Finalizer</span></span>
- <span data-ttu-id="85e79-177">Método</span><span class="sxs-lookup"><span data-stu-id="85e79-177">Method</span></span>
- <span data-ttu-id="85e79-178">Propriedade</span><span class="sxs-lookup"><span data-stu-id="85e79-178">Property</span></span>
- <span data-ttu-id="85e79-179">Delegados</span><span class="sxs-lookup"><span data-stu-id="85e79-179">Delegates</span></span>
- <span data-ttu-id="85e79-180">Eventos</span><span class="sxs-lookup"><span data-stu-id="85e79-180">Events</span></span>
- <span data-ttu-id="85e79-181">Exceção</span><span class="sxs-lookup"><span data-stu-id="85e79-181">Exception</span></span>
- <span data-ttu-id="85e79-182">Bloqueio</span><span class="sxs-lookup"><span data-stu-id="85e79-182">Lock</span></span>
- <span data-ttu-id="85e79-183">Erro</span><span class="sxs-lookup"><span data-stu-id="85e79-183">Error</span></span>
- <span data-ttu-id="85e79-184">Errors</span><span class="sxs-lookup"><span data-stu-id="85e79-184">Errors</span></span>
- <span data-ttu-id="85e79-185">Aviso</span><span class="sxs-lookup"><span data-stu-id="85e79-185">Warning</span></span>
- <span data-ttu-id="85e79-186">Detalhado</span><span class="sxs-lookup"><span data-stu-id="85e79-186">Verbose</span></span>
- <span data-ttu-id="85e79-187">WriteLine</span><span class="sxs-lookup"><span data-stu-id="85e79-187">WriteLine</span></span>
- <span data-ttu-id="85e79-188">Dados</span><span class="sxs-lookup"><span data-stu-id="85e79-188">Data</span></span>
- <span data-ttu-id="85e79-189">Escopo</span><span class="sxs-lookup"><span data-stu-id="85e79-189">Scope</span></span>
- <span data-ttu-id="85e79-190">ExecutionFlow</span><span class="sxs-lookup"><span data-stu-id="85e79-190">ExecutionFlow</span></span>
- <span data-ttu-id="85e79-191">Assert</span><span class="sxs-lookup"><span data-stu-id="85e79-191">Assert</span></span>
- <span data-ttu-id="85e79-192">Tudo</span><span class="sxs-lookup"><span data-stu-id="85e79-192">All</span></span>

<span data-ttu-id="85e79-193">All é o padrão.</span><span class="sxs-lookup"><span data-stu-id="85e79-193">All is the default.</span></span>

<span data-ttu-id="85e79-194">Os seguintes valores são combinações de outros valores:</span><span class="sxs-lookup"><span data-stu-id="85e79-194">The following values are combinations of other values:</span></span>

- <span data-ttu-id="85e79-195">ExecutionFlow: (Construtor, descarte, finalizador, método, delegados, eventos e escopo)</span><span class="sxs-lookup"><span data-stu-id="85e79-195">ExecutionFlow: (Constructor, Dispose, Finalizer, Method, Delegates, Events, and Scope)</span></span>
- <span data-ttu-id="85e79-196">Dados: (constructor, Dispose, Finalizer, Property, Verbose e WriteLine)</span><span class="sxs-lookup"><span data-stu-id="85e79-196">Data: (Constructor, Dispose, Finalizer, Property, Verbose, and WriteLine)</span></span>
- <span data-ttu-id="85e79-197">Erros: (erro e exceção).</span><span class="sxs-lookup"><span data-stu-id="85e79-197">Errors: (Error and Exception).</span></span>

<span data-ttu-id="85e79-198">Para especificar várias opções, separe-as com vírgulas, mas sem espaços, e coloque-as entre aspas, como "Constructor, Dispose".</span><span class="sxs-lookup"><span data-stu-id="85e79-198">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "Constructor,Dispose".</span></span>

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

### <span data-ttu-id="85e79-199">-PSHost</span><span class="sxs-lookup"><span data-stu-id="85e79-199">-PSHost</span></span>

<span data-ttu-id="85e79-200">Indica que o cmdlet envia a saída de rastreamento para o host do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="85e79-200">Indicates that the cmdlet sends the trace output to the PowerShell host.</span></span> <span data-ttu-id="85e79-201">Esse parâmetro também seleciona o ouvinte de rastreamento PSHost.</span><span class="sxs-lookup"><span data-stu-id="85e79-201">This parameter also selects the PSHost trace listener.</span></span>

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

### <span data-ttu-id="85e79-202">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="85e79-202">CommonParameters</span></span>

<span data-ttu-id="85e79-203">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="85e79-203">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="85e79-204">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="85e79-204">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="85e79-205">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="85e79-205">INPUTS</span></span>

### <span data-ttu-id="85e79-206">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="85e79-206">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="85e79-207">É possível canalizar objetos que representam a entrada para a expressão para `Trace-Command` .</span><span class="sxs-lookup"><span data-stu-id="85e79-207">You can pipe objects that represent input to the expression to `Trace-Command`.</span></span>

## <span data-ttu-id="85e79-208">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="85e79-208">OUTPUTS</span></span>

### <span data-ttu-id="85e79-209">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="85e79-209">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="85e79-210">Retorna o rastreamento de comando no fluxo de depuração.</span><span class="sxs-lookup"><span data-stu-id="85e79-210">Returns the command trace in the debug stream.</span></span>

## <span data-ttu-id="85e79-211">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="85e79-211">NOTES</span></span>

- <span data-ttu-id="85e79-212">O rastreamento é um método utilizado pelos desenvolvedores para depurar e aprimorar os programas.</span><span class="sxs-lookup"><span data-stu-id="85e79-212">Tracing is a method that developers use to debug and refine programs.</span></span> <span data-ttu-id="85e79-213">Ao realizar o rastreamento, o componente gera mensagens detalhadas sobre cada etapa no seu processamento interno.</span><span class="sxs-lookup"><span data-stu-id="85e79-213">When tracing, the program generates detailed messages about each step in its internal processing.</span></span>

- <span data-ttu-id="85e79-214">Os cmdlets de rastreamento do PowerShell são projetados para ajudar os desenvolvedores do PowerShell, mas estão disponíveis para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="85e79-214">The PowerShell tracing cmdlets are designed to help PowerShell developers, but they are available to all users.</span></span> <span data-ttu-id="85e79-215">Eles permitem monitorar quase todos os aspectos da funcionalidade do shell.</span><span class="sxs-lookup"><span data-stu-id="85e79-215">They let you monitor nearly every aspect of the functionality of the shell.</span></span>

- <span data-ttu-id="85e79-216">Para localizar os componentes do PowerShell que estão habilitados para rastreamento, digite `Get-Help Get-TraceSource` .</span><span class="sxs-lookup"><span data-stu-id="85e79-216">To find the PowerShell components that are enabled for tracing, type `Get-Help Get-TraceSource`.</span></span>

  <span data-ttu-id="85e79-217">Uma origem de rastreamento é a parte de cada componente do PowerShell que gerencia o rastreamento e gera mensagens de rastreamento para o componente.</span><span class="sxs-lookup"><span data-stu-id="85e79-217">A trace source is the part of each PowerShell component that manages tracing and generates trace messages for the component.</span></span> <span data-ttu-id="85e79-218">Para rastrear um componente, você deve identificar sua origem de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="85e79-218">To trace a component, you identify its trace source.</span></span>

  <span data-ttu-id="85e79-219">Um ouvinte de rastreamento recebe a saída do rastreamento e o exibe para o usuário.</span><span class="sxs-lookup"><span data-stu-id="85e79-219">A trace listener receives the output of the trace and displays it to the user.</span></span> <span data-ttu-id="85e79-220">Você pode optar por enviar os dados de rastreamento para um modo de usuário ou depurador de modo kernel, para o host ou console, para um arquivo ou para um ouvinte personalizado derivado da classe **System. Diagnostics. TraceListener** .</span><span class="sxs-lookup"><span data-stu-id="85e79-220">You can elect to send the trace data to a user-mode or kernel-mode debugger, to the host or console, to a file, or to a custom listener derived from the **System.Diagnostics.TraceListener** class.</span></span>

- <span data-ttu-id="85e79-221">Quando você usa o conjunto de parâmetros commandSet, o PowerShell processa o comando da mesma forma que seria processado em um pipeline.</span><span class="sxs-lookup"><span data-stu-id="85e79-221">When you use the commandSet parameter set, PowerShell processes the command just as it would be processed in a pipeline.</span></span> <span data-ttu-id="85e79-222">Por exemplo, a descoberta de comando não é repetida para cada objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="85e79-222">For example, command discovery is not repeated for each incoming object.</span></span>

- <span data-ttu-id="85e79-223">Os nomes dos parâmetros **Name** , **expression** , **Option** e **Command** são opcionais.</span><span class="sxs-lookup"><span data-stu-id="85e79-223">The names of the **Name** , **Expression** , **Option** , and **Command** parameters are optional.</span></span> <span data-ttu-id="85e79-224">Se você omitir os nomes de parâmetro, os valores de parâmetro não nomeados deverão aparecer nesta ordem: **nome** , **expressão** , **opção** ou **nome** , **comando** , **opção** .</span><span class="sxs-lookup"><span data-stu-id="85e79-224">If you omit the parameter names, the unnamed parameter values must appear in this order: **Name** , **Expression** , **Option** or **Name** , **Command** , **Option** .</span></span> <span data-ttu-id="85e79-225">Se você incluir os nomes dos parâmetros, os parâmetros podem aparecer em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="85e79-225">If you include the parameter names, the parameters can appear in any order.</span></span>

## <span data-ttu-id="85e79-226">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="85e79-226">RELATED LINKS</span></span>

[<span data-ttu-id="85e79-227">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="85e79-227">Get-TraceSource</span></span>](Get-TraceSource.md)

[<span data-ttu-id="85e79-228">Measure-Command</span><span class="sxs-lookup"><span data-stu-id="85e79-228">Measure-Command</span></span>](Measure-Command.md)

[<span data-ttu-id="85e79-229">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="85e79-229">Set-TraceSource</span></span>](Set-TraceSource.md)
