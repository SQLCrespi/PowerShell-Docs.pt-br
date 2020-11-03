---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-tracesource?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-TraceSource
ms.openlocfilehash: 7a1f7e2879b0eeefe8771a5e5a8bf763e48ff106
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192790"
---
# <span data-ttu-id="af718-103">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="af718-103">Set-TraceSource</span></span>

## <span data-ttu-id="af718-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="af718-104">SYNOPSIS</span></span>
<span data-ttu-id="af718-105">Configura, inicia e para um rastreamento de componentes do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af718-105">Configures, starts, and stops a trace of PowerShell components.</span></span>

## <span data-ttu-id="af718-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="af718-106">SYNTAX</span></span>

### <span data-ttu-id="af718-107">optionsset (padrão)</span><span class="sxs-lookup"><span data-stu-id="af718-107">optionsSet (Default)</span></span>

```
Set-TraceSource [-Name] <String[]> [[-Option] <PSTraceSourceOptions>] [-ListenerOption <TraceOptions>]
 [-FilePath <String>] [-Force] [-Debugger] [-PSHost] [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="af718-108">removeAllListenersSet</span><span class="sxs-lookup"><span data-stu-id="af718-108">removeAllListenersSet</span></span>

```
Set-TraceSource [-Name] <String[]> [-RemoveListener <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="af718-109">removeFileListenersSet</span><span class="sxs-lookup"><span data-stu-id="af718-109">removeFileListenersSet</span></span>

```
Set-TraceSource [-Name] <String[]> [-RemoveFileListener <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="af718-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="af718-110">DESCRIPTION</span></span>

<span data-ttu-id="af718-111">O cmdlet **set-traceexception** configura, inicia e interrompe um rastreamento de um componente do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af718-111">The **Set-TraceSource** cmdlet configures, starts, and stops a trace of a PowerShell component.</span></span>
<span data-ttu-id="af718-112">Você pode usá-lo para especificar quais componentes serão rastreados e para onde a saída de rastreamento é enviada.</span><span class="sxs-lookup"><span data-stu-id="af718-112">You can use it to specify which components will be traced and where the tracing output is sent.</span></span>

## <span data-ttu-id="af718-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="af718-113">EXAMPLES</span></span>

### <span data-ttu-id="af718-114">Exemplo 1: rastrear o componente ParameterBinding</span><span class="sxs-lookup"><span data-stu-id="af718-114">Example 1: Trace the ParameterBinding component</span></span>

```
PS C:\> Set-TraceSource -Name "ParameterBinding" -Option ExecutionFlow -PSHost -ListenerOption "ProcessId,TimeStamp"
```

<span data-ttu-id="af718-115">Esse comando inicia o rastreamento para o componente ParameterBinding do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af718-115">This command starts tracing for the ParameterBinding component of PowerShell.</span></span>
<span data-ttu-id="af718-116">Ele usa o parâmetro *Name* para especificar a origem do rastreamento, o parâmetro *Option* para selecionar os eventos de rastreamento ExecutionFlow e o parâmetro *PSHost* para selecionar o ouvinte do host do PowerShell, que envia a saída para o console.</span><span class="sxs-lookup"><span data-stu-id="af718-116">It uses the *Name* parameter to specify the trace source, the *Option* parameter to select the ExecutionFlow trace events, and the *PSHost* parameter to select the PowerShell host listener, which sends the output to the console.</span></span>
<span data-ttu-id="af718-117">O parâmetro *ListenerOption* adiciona os valores de ProcessId e timestamp ao prefixo da mensagem de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="af718-117">The *ListenerOption* parameter adds the ProcessID and TimeStamp values to the trace message prefix.</span></span>

### <span data-ttu-id="af718-118">Exemplo 2: parar um rastreamento</span><span class="sxs-lookup"><span data-stu-id="af718-118">Example 2: Stop a trace</span></span>

```
PS C:\> Set-TraceSource -Name "ParameterBinding" -RemoveListener "Host"
```

<span data-ttu-id="af718-119">Esse comando interrompe o rastreamento do componente ParameterBinding do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af718-119">This command stops the trace of the ParameterBinding component of PowerShell.</span></span>
<span data-ttu-id="af718-120">Ele usa o parâmetro *Name* para identificar o componente que estava sendo rastreado e o parâmetro *RemoveListener* para identificar o ouvinte de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="af718-120">It uses the *Name* parameter to identify the component that was being traced and the *RemoveListener* parameter to identify the trace listener.</span></span>

## <span data-ttu-id="af718-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="af718-121">PARAMETERS</span></span>

### <span data-ttu-id="af718-122">-Depurador</span><span class="sxs-lookup"><span data-stu-id="af718-122">-Debugger</span></span>

<span data-ttu-id="af718-123">Indica que o cmdlet envia a saída de rastreamento para o depurador.</span><span class="sxs-lookup"><span data-stu-id="af718-123">Indicates that the cmdlet sends the trace output to the debugger.</span></span>
<span data-ttu-id="af718-124">Você pode exibir a saída em qualquer modo de usuário ou depurador do modo kernel, ou ainda no Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="af718-124">You can view the output in any user-mode or kernel mode debugger or in Microsoft Visual Studio.</span></span>
<span data-ttu-id="af718-125">Esse parâmetro também seleciona o ouvinte de rastreamento padrão.</span><span class="sxs-lookup"><span data-stu-id="af718-125">This parameter also selects the default trace listener.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af718-126">-FilePath</span><span class="sxs-lookup"><span data-stu-id="af718-126">-FilePath</span></span>

<span data-ttu-id="af718-127">Especifica um arquivo para o qual este cmdlet envia a saída de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="af718-127">Specifies a file that this cmdlet sends the trace output to.</span></span>
<span data-ttu-id="af718-128">Esse parâmetro também seleciona o ouvinte de rastreamento do arquivo.</span><span class="sxs-lookup"><span data-stu-id="af718-128">This parameter also selects the file trace listener.</span></span>
<span data-ttu-id="af718-129">Se você usar esse parâmetro para iniciar o rastreamento, use o parâmetro *RemoveFileListener* para interromper o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="af718-129">If you use this parameter to start the trace, use the *RemoveFileListener* parameter to stop the trace.</span></span>

```yaml
Type: System.String
Parameter Sets: optionsSet
Aliases: PSPath, Path

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af718-130">-Force</span><span class="sxs-lookup"><span data-stu-id="af718-130">-Force</span></span>

<span data-ttu-id="af718-131">Indica que o cmdlet substitui um arquivo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="af718-131">Indicates that the cmdlet overwrites a read-only file.</span></span>
<span data-ttu-id="af718-132">Use com o parâmetro *FilePath* .</span><span class="sxs-lookup"><span data-stu-id="af718-132">Use with the *FilePath* parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af718-133">-ListenerOption</span><span class="sxs-lookup"><span data-stu-id="af718-133">-ListenerOption</span></span>

<span data-ttu-id="af718-134">Especifica dados opcionais para o prefixo de cada mensagem de rastreamento na saída.</span><span class="sxs-lookup"><span data-stu-id="af718-134">Specifies optional data to the prefix of each trace message in the output.</span></span>
<span data-ttu-id="af718-135">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="af718-135">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="af718-136">Nenhum</span><span class="sxs-lookup"><span data-stu-id="af718-136">None</span></span>
- <span data-ttu-id="af718-137">LogicalOperationStack</span><span class="sxs-lookup"><span data-stu-id="af718-137">LogicalOperationStack</span></span>
- <span data-ttu-id="af718-138">Datetime</span><span class="sxs-lookup"><span data-stu-id="af718-138">DateTime</span></span>
- <span data-ttu-id="af718-139">Timestamp</span><span class="sxs-lookup"><span data-stu-id="af718-139">Timestamp</span></span>
- <span data-ttu-id="af718-140">ProcessId</span><span class="sxs-lookup"><span data-stu-id="af718-140">ProcessId</span></span>
- <span data-ttu-id="af718-141">ThreadId</span><span class="sxs-lookup"><span data-stu-id="af718-141">ThreadId</span></span>
- <span data-ttu-id="af718-142">Chamadas</span><span class="sxs-lookup"><span data-stu-id="af718-142">Callstack</span></span>

<span data-ttu-id="af718-143">None é o padrão.</span><span class="sxs-lookup"><span data-stu-id="af718-143">None is the default.</span></span>

<span data-ttu-id="af718-144">Para especificar várias opções, separe-as com vírgulas, mas sem espaços, e coloque-as entre aspas, como "ProcessID ThreadID".</span><span class="sxs-lookup"><span data-stu-id="af718-144">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "ProcessID,ThreadID".</span></span>

```yaml
Type: System.Diagnostics.TraceOptions
Parameter Sets: optionsSet
Aliases:
Accepted values: None, LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af718-145">-Name</span><span class="sxs-lookup"><span data-stu-id="af718-145">-Name</span></span>

<span data-ttu-id="af718-146">Especifica quais componentes são rastreados.</span><span class="sxs-lookup"><span data-stu-id="af718-146">Specifies which components are traced.</span></span>
<span data-ttu-id="af718-147">Insira o nome da origem de rastreamento de cada componente.</span><span class="sxs-lookup"><span data-stu-id="af718-147">Enter the name of the trace source of each component.</span></span>
<span data-ttu-id="af718-148">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="af718-148">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="af718-149">-Opção</span><span class="sxs-lookup"><span data-stu-id="af718-149">-Option</span></span>

<span data-ttu-id="af718-150">Especifica o tipo de eventos que são rastreados.</span><span class="sxs-lookup"><span data-stu-id="af718-150">Specifies the type of events that are traced.</span></span>
<span data-ttu-id="af718-151">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="af718-151">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="af718-152">Nenhum</span><span class="sxs-lookup"><span data-stu-id="af718-152">None</span></span>
- <span data-ttu-id="af718-153">Construtor</span><span class="sxs-lookup"><span data-stu-id="af718-153">Constructor</span></span>
- <span data-ttu-id="af718-154">Dispose</span><span class="sxs-lookup"><span data-stu-id="af718-154">Dispose</span></span>
- <span data-ttu-id="af718-155">Finalizer</span><span class="sxs-lookup"><span data-stu-id="af718-155">Finalizer</span></span>
- <span data-ttu-id="af718-156">Método</span><span class="sxs-lookup"><span data-stu-id="af718-156">Method</span></span>
- <span data-ttu-id="af718-157">Propriedade</span><span class="sxs-lookup"><span data-stu-id="af718-157">Property</span></span>
- <span data-ttu-id="af718-158">Delegados</span><span class="sxs-lookup"><span data-stu-id="af718-158">Delegates</span></span>
- <span data-ttu-id="af718-159">Eventos</span><span class="sxs-lookup"><span data-stu-id="af718-159">Events</span></span>
- <span data-ttu-id="af718-160">Exceção</span><span class="sxs-lookup"><span data-stu-id="af718-160">Exception</span></span>
- <span data-ttu-id="af718-161">Bloqueio</span><span class="sxs-lookup"><span data-stu-id="af718-161">Lock</span></span>
- <span data-ttu-id="af718-162">Erro</span><span class="sxs-lookup"><span data-stu-id="af718-162">Error</span></span>
- <span data-ttu-id="af718-163">Errors</span><span class="sxs-lookup"><span data-stu-id="af718-163">Errors</span></span>
- <span data-ttu-id="af718-164">Aviso</span><span class="sxs-lookup"><span data-stu-id="af718-164">Warning</span></span>
- <span data-ttu-id="af718-165">Detalhado</span><span class="sxs-lookup"><span data-stu-id="af718-165">Verbose</span></span>
- <span data-ttu-id="af718-166">WriteLine</span><span class="sxs-lookup"><span data-stu-id="af718-166">WriteLine</span></span>
- <span data-ttu-id="af718-167">Dados</span><span class="sxs-lookup"><span data-stu-id="af718-167">Data</span></span>
- <span data-ttu-id="af718-168">Escopo</span><span class="sxs-lookup"><span data-stu-id="af718-168">Scope</span></span>
- <span data-ttu-id="af718-169">ExecutionFlow</span><span class="sxs-lookup"><span data-stu-id="af718-169">ExecutionFlow</span></span>
- <span data-ttu-id="af718-170">Assert</span><span class="sxs-lookup"><span data-stu-id="af718-170">Assert</span></span>
- <span data-ttu-id="af718-171">Tudo</span><span class="sxs-lookup"><span data-stu-id="af718-171">All</span></span>

<span data-ttu-id="af718-172">All é o padrão.</span><span class="sxs-lookup"><span data-stu-id="af718-172">All is the default.</span></span>

<span data-ttu-id="af718-173">Os seguintes valores são combinações de outros valores:</span><span class="sxs-lookup"><span data-stu-id="af718-173">The following values are combinations of other values:</span></span>

- <span data-ttu-id="af718-174">ExecutionFlow: (Construtor, descarte, finalizador, método, delegados, eventos e escopo)</span><span class="sxs-lookup"><span data-stu-id="af718-174">ExecutionFlow: (Constructor, Dispose, Finalizer, Method, Delegates, Events, and Scope)</span></span>
- <span data-ttu-id="af718-175">Dados: (constructor, Dispose, Finalizer, Property, Verbose e WriteLine)</span><span class="sxs-lookup"><span data-stu-id="af718-175">Data: (Constructor, Dispose, Finalizer, Property, Verbose, and WriteLine)</span></span>
- <span data-ttu-id="af718-176">Erros: (erro e exceção).</span><span class="sxs-lookup"><span data-stu-id="af718-176">Errors: (Error and Exception).</span></span>

<span data-ttu-id="af718-177">Para especificar várias opções, separe-as com vírgulas, mas sem espaços, e coloque-as entre aspas, como "Constructor, Dispose".</span><span class="sxs-lookup"><span data-stu-id="af718-177">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "Constructor,Dispose".</span></span>

```yaml
Type: System.Management.Automation.PSTraceSourceOptions
Parameter Sets: optionsSet
Aliases:
Accepted values: None, Constructor, Dispose, Finalizer, Method, Property, Delegates, Events, Exception, Lock, Error, Errors, Warning, Verbose, WriteLine, Data, Scope, ExecutionFlow, Assert, All

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="af718-178">-PassThru</span><span class="sxs-lookup"><span data-stu-id="af718-178">-PassThru</span></span>

<span data-ttu-id="af718-179">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="af718-179">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="af718-180">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="af718-180">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af718-181">-PSHost</span><span class="sxs-lookup"><span data-stu-id="af718-181">-PSHost</span></span>

<span data-ttu-id="af718-182">ndicates que esse cmdlet envia a saída de rastreamento para o host do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af718-182">ndicates that this cmdlet sends the trace output to the PowerShell host.</span></span>
<span data-ttu-id="af718-183">Esse parâmetro também seleciona o ouvinte de rastreamento PSHost.</span><span class="sxs-lookup"><span data-stu-id="af718-183">This parameter also selects the PSHost trace listener.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af718-184">-RemoveFileListener</span><span class="sxs-lookup"><span data-stu-id="af718-184">-RemoveFileListener</span></span>

<span data-ttu-id="af718-185">Interrompe o rastreamento, removendo o ouvinte de rastreamento do arquivo associado ao arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="af718-185">Stops the trace by removing the file trace listener associated with the specified file.</span></span>
<span data-ttu-id="af718-186">Digite o caminho e o nome do arquivo de saída de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="af718-186">Enter the path and file name of the trace output file.</span></span>

```yaml
Type: System.String[]
Parameter Sets: removeFileListenersSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af718-187">-RemoveListener</span><span class="sxs-lookup"><span data-stu-id="af718-187">-RemoveListener</span></span>

<span data-ttu-id="af718-188">Interrompe o rastreamento, removendo o ouvinte de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="af718-188">Stops the trace by removing the trace listener.</span></span>

<span data-ttu-id="af718-189">Use os seguintes valores com *RemoveListener* :</span><span class="sxs-lookup"><span data-stu-id="af718-189">Use the following values with *RemoveListener* :</span></span>

- <span data-ttu-id="af718-190">Para remover PSHost (console), digite `Host` .</span><span class="sxs-lookup"><span data-stu-id="af718-190">To remove PSHost (console), type `Host`.</span></span>
- <span data-ttu-id="af718-191">Para remover o depurador, digite `Debug` .</span><span class="sxs-lookup"><span data-stu-id="af718-191">To remove Debugger, type `Debug`.</span></span>
- <span data-ttu-id="af718-192">Para remover todos os ouvintes de rastreamento, digite `*` .</span><span class="sxs-lookup"><span data-stu-id="af718-192">To remove all trace listeners, type `*`.</span></span>

<span data-ttu-id="af718-193">Para remover o ouvinte de rastreamento de arquivo, use o parâmetro *RemoveFileListener* .</span><span class="sxs-lookup"><span data-stu-id="af718-193">To remove the file trace listener, use the *RemoveFileListener* parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: removeAllListenersSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af718-194">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="af718-194">CommonParameters</span></span>

<span data-ttu-id="af718-195">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="af718-195">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="af718-196">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="af718-196">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="af718-197">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="af718-197">INPUTS</span></span>

### <span data-ttu-id="af718-198">System.String</span><span class="sxs-lookup"><span data-stu-id="af718-198">System.String</span></span>

<span data-ttu-id="af718-199">É possível canalizar uma cadeia de caracteres que contém um nome para **set-tracename** .</span><span class="sxs-lookup"><span data-stu-id="af718-199">You can pipe a string that contains a name to **Set-TraceSource** .</span></span>

## <span data-ttu-id="af718-200">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="af718-200">OUTPUTS</span></span>

### <span data-ttu-id="af718-201">Nenhum ou System. Management. Automation. PSTraceSource</span><span class="sxs-lookup"><span data-stu-id="af718-201">None or System.Management.Automation.PSTraceSource</span></span>

<span data-ttu-id="af718-202">Quando você usa o parâmetro *PassThru* , **set-tracename** gera um objeto **System. Management. Automation. PSTraceSource** que representa a sessão de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="af718-202">When you use the *PassThru* parameter, **Set-TraceSource** generates a **System.Management.Automation.PSTraceSource** object representing the trace session.</span></span>
<span data-ttu-id="af718-203">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="af718-203">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="af718-204">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="af718-204">NOTES</span></span>

* <span data-ttu-id="af718-205">O rastreamento é um método utilizado pelos desenvolvedores para depurar e aprimorar os programas.</span><span class="sxs-lookup"><span data-stu-id="af718-205">Tracing is a method that developers use to debug and refine programs.</span></span> <span data-ttu-id="af718-206">Ao realizar o rastreamento, o componente gera mensagens detalhadas sobre cada etapa no seu processamento interno.</span><span class="sxs-lookup"><span data-stu-id="af718-206">When tracing, the program generates detailed messages about each step in its internal processing.</span></span>

  <span data-ttu-id="af718-207">Os cmdlets de rastreamento do PowerShell são projetados para ajudar os desenvolvedores do PowerShell, mas estão disponíveis para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="af718-207">The PowerShell tracing cmdlets are designed to help PowerShell developers, but they are available to all users.</span></span>
<span data-ttu-id="af718-208">Eles permitem monitorar quase todos os aspectos da funcionalidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af718-208">They let you monitor nearly every aspect of the functionality of PowerShell.</span></span>

  <span data-ttu-id="af718-209">Uma origem de rastreamento é a parte de cada componente do PowerShell que gerencia o rastreamento e gera mensagens de rastreamento para o componente.</span><span class="sxs-lookup"><span data-stu-id="af718-209">A trace source is the part of each PowerShell component that manages tracing and generates trace messages for the component.</span></span>
<span data-ttu-id="af718-210">Para rastrear um componente, você deve identificar sua origem de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="af718-210">To trace a component, you identify its trace source.</span></span>

  <span data-ttu-id="af718-211">Um ouvinte de rastreamento recebe a saída do rastreamento e o exibe para o usuário.</span><span class="sxs-lookup"><span data-stu-id="af718-211">A trace listener receives the output of the trace and displays it to the user.</span></span>
<span data-ttu-id="af718-212">Você pode optar por enviar os dados de rastreamento para um modo de usuário ou depurador de modo kernel, para o console, para um arquivo ou para um ouvinte personalizado derivado da classe **System. Diagnostics. TraceListener** .</span><span class="sxs-lookup"><span data-stu-id="af718-212">You can elect to send the trace data to a user-mode or kernel-mode debugger, to the console, to a file, or to a custom listener derived from the **System.Diagnostics.TraceListener** class.</span></span>

* <span data-ttu-id="af718-213">Para iniciar um rastreamento, use o parâmetro *Name* para especificar uma origem de rastreamento e os parâmetros *FilePath* , *Debugger* ou *PSHost* para especificar um ouvinte (um destino para a saída).</span><span class="sxs-lookup"><span data-stu-id="af718-213">To start a trace, use the *Name* parameter to specify a trace source and the *FilePath* , *Debugger* , or *PSHost* parameters to specify a listener (a destination for the output).</span></span> <span data-ttu-id="af718-214">Use o parâmetro *Options* para determinar os tipos de eventos que são rastreados e o parâmetro *ListenerOption* para configurar a saída de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="af718-214">Use the *Options* parameter to determine the types of events that are traced and the *ListenerOption* parameter to configure the trace output.</span></span>
* <span data-ttu-id="af718-215">Para alterar a configuração de um rastreamento, insira um comando **set-Tracee** como você faria para iniciar um rastreamento.</span><span class="sxs-lookup"><span data-stu-id="af718-215">To change the configuration of a trace, enter a **Set-TraceSource** command as you would to start a trace.</span></span> <span data-ttu-id="af718-216">O PowerShell reconhece que a origem do rastreamento já está sendo rastreada.</span><span class="sxs-lookup"><span data-stu-id="af718-216">PowerShell recognizes that the trace source is already being traced.</span></span> <span data-ttu-id="af718-217">Ele interrompe o rastreamento, adiciona a nova configuração e inicia ou reinicia o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="af718-217">It stops the trace, adds the new configuration, and starts or restarts the trace.</span></span>
* <span data-ttu-id="af718-218">Para interromper um rastreamento, use o parâmetro *RemoveListener* .</span><span class="sxs-lookup"><span data-stu-id="af718-218">To stop a trace, use the *RemoveListener* parameter.</span></span> <span data-ttu-id="af718-219">Para interromper um rastreamento que usa o ouvinte de arquivo (um rastreamento iniciado usando o parâmetro *FilePath* ), use o parâmetro *RemoveFileListener* .</span><span class="sxs-lookup"><span data-stu-id="af718-219">To stop a trace that uses the file listener (a trace started by using the *FilePath* parameter), use the *RemoveFileListener* parameter.</span></span> <span data-ttu-id="af718-220">Quando você remove o ouvinte, o rastreamento é interrompido.</span><span class="sxs-lookup"><span data-stu-id="af718-220">When you remove the listener, the trace stops.</span></span>
* <span data-ttu-id="af718-221">Para determinar quais componentes podem ser rastreados, use Get-TraceSource.</span><span class="sxs-lookup"><span data-stu-id="af718-221">To determine which components can be traced, use Get-TraceSource.</span></span> <span data-ttu-id="af718-222">As origens de rastreamento para cada módulo são carregadas automaticamente quando o componente está em uso e aparecem na saída de **Get-tracename** .</span><span class="sxs-lookup"><span data-stu-id="af718-222">The trace sources for each module are loaded automatically when the component is in use, and they appear in the output of **Get-TraceSource** .</span></span>

## <span data-ttu-id="af718-223">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="af718-223">RELATED LINKS</span></span>

[<span data-ttu-id="af718-224">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="af718-224">Get-TraceSource</span></span>](Get-TraceSource.md)

[<span data-ttu-id="af718-225">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="af718-225">Trace-Command</span></span>](Trace-Command.md)
