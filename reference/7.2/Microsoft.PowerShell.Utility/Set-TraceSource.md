---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/01/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-tracesource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-TraceSource
ms.openlocfilehash: 6113d9490872346c91769d9e7d0376c77ed4401f
ms.sourcegitcommit: 5b48fe7b2593581b7d4f7dd7c22206d8a45bb8af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "106184470"
---
# <span data-ttu-id="76c16-102">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="76c16-102">Set-TraceSource</span></span>

## <span data-ttu-id="76c16-103">Sinopse</span><span class="sxs-lookup"><span data-stu-id="76c16-103">Synopsis</span></span>
<span data-ttu-id="76c16-104">Configura, inicia e para um rastreamento de componentes do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76c16-104">Configures, starts, and stops a trace of PowerShell components.</span></span>

## <span data-ttu-id="76c16-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="76c16-105">Syntax</span></span>

### <span data-ttu-id="76c16-106">optionsset (padrão)</span><span class="sxs-lookup"><span data-stu-id="76c16-106">optionsSet (Default)</span></span>

```
Set-TraceSource [-Name] <String[]> [[-Option] <PSTraceSourceOptions>] [-ListenerOption <TraceOptions>]
 [-FilePath <String>] [-Force] [-Debugger] [-PSHost] [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="76c16-107">removeAllListenersSet</span><span class="sxs-lookup"><span data-stu-id="76c16-107">removeAllListenersSet</span></span>

```
Set-TraceSource [-Name] <String[]> [-RemoveListener <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="76c16-108">removeFileListenersSet</span><span class="sxs-lookup"><span data-stu-id="76c16-108">removeFileListenersSet</span></span>

```
Set-TraceSource [-Name] <String[]> [-RemoveFileListener <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="76c16-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="76c16-109">Description</span></span>

<span data-ttu-id="76c16-110">O `Set-TraceSource` cmdlet configura, inicia e para um rastreamento de um componente do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76c16-110">The `Set-TraceSource` cmdlet configures, starts, and stops a trace of a PowerShell component.</span></span> <span data-ttu-id="76c16-111">Você pode usá-lo para especificar quais componentes serão rastreados e para onde a saída de rastreamento é enviada.</span><span class="sxs-lookup"><span data-stu-id="76c16-111">You can use it to specify which components will be traced and where the tracing output is sent.</span></span>

## <span data-ttu-id="76c16-112">Exemplos</span><span class="sxs-lookup"><span data-stu-id="76c16-112">Examples</span></span>

### <span data-ttu-id="76c16-113">Exemplo 1: rastrear o componente ParameterBinding</span><span class="sxs-lookup"><span data-stu-id="76c16-113">Example 1: Trace the ParameterBinding component</span></span>

```
Set-TraceSource -Name "ParameterBinding" -Option ExecutionFlow -PSHost -ListenerOption "ProcessId,TimeStamp"
```

<span data-ttu-id="76c16-114">Esse comando inicia o rastreamento para o componente ParameterBinding do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76c16-114">This command starts tracing for the ParameterBinding component of PowerShell.</span></span> <span data-ttu-id="76c16-115">Ele usa o parâmetro **Name** para especificar a origem do rastreamento, o parâmetro **Option** para selecionar os `ExecutionFlow` eventos de rastreamento e o parâmetro **PSHost** para selecionar o ouvinte do host do PowerShell, que envia a saída para o console.</span><span class="sxs-lookup"><span data-stu-id="76c16-115">It uses the **Name** parameter to specify the trace source, the **Option** parameter to select the `ExecutionFlow` trace events, and the **PSHost** parameter to select the PowerShell host listener, which sends the output to the console.</span></span> <span data-ttu-id="76c16-116">O parâmetro **ListenerOption** adiciona os `ProcessID` `TimeStamp` valores e ao prefixo da mensagem de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="76c16-116">The **ListenerOption** parameter adds the `ProcessID` and `TimeStamp` values to the trace message prefix.</span></span>

### <span data-ttu-id="76c16-117">Exemplo 2: parar um rastreamento</span><span class="sxs-lookup"><span data-stu-id="76c16-117">Example 2: Stop a trace</span></span>

```
Set-TraceSource -Name "ParameterBinding" -RemoveListener "Host"
```

<span data-ttu-id="76c16-118">Esse comando interrompe o rastreamento do componente **ParameterBinding** do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76c16-118">This command stops the trace of the **ParameterBinding** component of PowerShell.</span></span> <span data-ttu-id="76c16-119">Ele usa o parâmetro **Name** para identificar o componente que estava sendo rastreado e o parâmetro **RemoveListener** para identificar o ouvinte de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="76c16-119">It uses the **Name** parameter to identify the component that was being traced and the **RemoveListener** parameter to identify the trace listener.</span></span>

## <span data-ttu-id="76c16-120">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="76c16-120">Parameters</span></span>

### <span data-ttu-id="76c16-121">-Depurador</span><span class="sxs-lookup"><span data-stu-id="76c16-121">-Debugger</span></span>

<span data-ttu-id="76c16-122">Indica que o cmdlet envia a saída de rastreamento para o depurador.</span><span class="sxs-lookup"><span data-stu-id="76c16-122">Indicates that the cmdlet sends the trace output to the debugger.</span></span> <span data-ttu-id="76c16-123">Você pode exibir a saída em qualquer modo de usuário ou depurador do modo kernel, ou ainda no Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="76c16-123">You can view the output in any user-mode or kernel mode debugger or in Microsoft Visual Studio.</span></span> <span data-ttu-id="76c16-124">Esse parâmetro também seleciona o ouvinte de rastreamento padrão.</span><span class="sxs-lookup"><span data-stu-id="76c16-124">This parameter also selects the default trace listener.</span></span>

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

### <span data-ttu-id="76c16-125">-FilePath</span><span class="sxs-lookup"><span data-stu-id="76c16-125">-FilePath</span></span>

<span data-ttu-id="76c16-126">Especifica um arquivo para o qual este cmdlet envia a saída de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="76c16-126">Specifies a file that this cmdlet sends the trace output to.</span></span> <span data-ttu-id="76c16-127">Esse parâmetro também seleciona o ouvinte de rastreamento do arquivo.</span><span class="sxs-lookup"><span data-stu-id="76c16-127">This parameter also selects the file trace listener.</span></span> <span data-ttu-id="76c16-128">Se você usar esse parâmetro para iniciar o rastreamento, use o parâmetro **RemoveFileListener** para interromper o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="76c16-128">If you use this parameter to start the trace, use the **RemoveFileListener** parameter to stop the trace.</span></span>

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

### <span data-ttu-id="76c16-129">-Force</span><span class="sxs-lookup"><span data-stu-id="76c16-129">-Force</span></span>

<span data-ttu-id="76c16-130">Indica que o cmdlet substitui um arquivo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="76c16-130">Indicates that the cmdlet overwrites a read-only file.</span></span> <span data-ttu-id="76c16-131">Use com o parâmetro **FilePath** .</span><span class="sxs-lookup"><span data-stu-id="76c16-131">Use with the **FilePath** parameter.</span></span>

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

### <span data-ttu-id="76c16-132">-ListenerOption</span><span class="sxs-lookup"><span data-stu-id="76c16-132">-ListenerOption</span></span>

<span data-ttu-id="76c16-133">Especifica dados opcionais para o prefixo de cada mensagem de rastreamento na saída.</span><span class="sxs-lookup"><span data-stu-id="76c16-133">Specifies optional data to the prefix of each trace message in the output.</span></span> <span data-ttu-id="76c16-134">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="76c16-134">The acceptable values for this parameter are:</span></span>

- `None`
- `LogicalOperationStack`
- `DateTime`
- `Timestamp`
- `ProcessId`
- `ThreadId`
- `Callstack`

<span data-ttu-id="76c16-135">`None` é o padrão.</span><span class="sxs-lookup"><span data-stu-id="76c16-135">`None` is the default.</span></span>

<span data-ttu-id="76c16-136">Esses valores são definidos como uma enumeração baseada em sinalizador.</span><span class="sxs-lookup"><span data-stu-id="76c16-136">These values are defined as a flag-based enumeration.</span></span> <span data-ttu-id="76c16-137">Você pode combinar vários valores juntos para definir vários sinalizadores usando esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="76c16-137">You can combine multiple values together to set multiple flags using this parameter.</span></span> <span data-ttu-id="76c16-138">Os valores podem ser passados para o parâmetro **ListenerOption** como uma matriz de valores ou como uma cadeia de caracteres separada por vírgulas desses valores.</span><span class="sxs-lookup"><span data-stu-id="76c16-138">The values can be passed to the **ListenerOption** parameter as an array of values or as a comma-separated string of those values.</span></span> <span data-ttu-id="76c16-139">O cmdlet combinará os valores usando uma operação binary ou.</span><span class="sxs-lookup"><span data-stu-id="76c16-139">The cmdlet will combine the values using a binary-OR operation.</span></span> <span data-ttu-id="76c16-140">Passar valores como uma matriz é a opção mais simples e também permite que você use a conclusão de tabulação nos valores.</span><span class="sxs-lookup"><span data-stu-id="76c16-140">Passing values as an array is the simplest option and also allows you to use tab-completion on the values.</span></span>

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

### <span data-ttu-id="76c16-141">-Name</span><span class="sxs-lookup"><span data-stu-id="76c16-141">-Name</span></span>

<span data-ttu-id="76c16-142">Especifica quais componentes são rastreados.</span><span class="sxs-lookup"><span data-stu-id="76c16-142">Specifies which components are traced.</span></span> <span data-ttu-id="76c16-143">Insira o nome da origem de rastreamento de cada componente.</span><span class="sxs-lookup"><span data-stu-id="76c16-143">Enter the name of the trace source of each component.</span></span>
<span data-ttu-id="76c16-144">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="76c16-144">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="76c16-145">-Opção</span><span class="sxs-lookup"><span data-stu-id="76c16-145">-Option</span></span>

<span data-ttu-id="76c16-146">Especifica o tipo de eventos que são rastreados.</span><span class="sxs-lookup"><span data-stu-id="76c16-146">Specifies the type of events that are traced.</span></span> <span data-ttu-id="76c16-147">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="76c16-147">The acceptable values for this parameter are:</span></span>

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

<span data-ttu-id="76c16-148">`All` é o padrão.</span><span class="sxs-lookup"><span data-stu-id="76c16-148">`All` is the default.</span></span>

<span data-ttu-id="76c16-149">Os seguintes valores são combinações de outros valores:</span><span class="sxs-lookup"><span data-stu-id="76c16-149">The following values are combinations of other values:</span></span>

- <span data-ttu-id="76c16-150">`ExecutionFlow`: `Constructor`, `Dispose`, `Finalizer`, `Method`, `Delegates`, `Events`, `Scope`</span><span class="sxs-lookup"><span data-stu-id="76c16-150">`ExecutionFlow`: `Constructor`, `Dispose`, `Finalizer`, `Method`, `Delegates`, `Events`, `Scope`</span></span>
- <span data-ttu-id="76c16-151">`Data`: `Constructor`, `Dispose`, `Finalizer`, `Property`, `Verbose`, `WriteLine`</span><span class="sxs-lookup"><span data-stu-id="76c16-151">`Data`: `Constructor`, `Dispose`, `Finalizer`, `Property`, `Verbose`, `WriteLine`</span></span>
- <span data-ttu-id="76c16-152">`Errors`: `Error`, `Exception`</span><span class="sxs-lookup"><span data-stu-id="76c16-152">`Errors`: `Error`, `Exception`</span></span>

<span data-ttu-id="76c16-153">Esses valores são definidos como uma enumeração baseada em sinalizador.</span><span class="sxs-lookup"><span data-stu-id="76c16-153">These values are defined as a flag-based enumeration.</span></span> <span data-ttu-id="76c16-154">Você pode combinar vários valores juntos para definir vários sinalizadores usando esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="76c16-154">You can combine multiple values together to set multiple flags using this parameter.</span></span> <span data-ttu-id="76c16-155">Os valores podem ser passados para o parâmetro de **opção** como uma matriz de valores ou como uma cadeia de caracteres separada por vírgulas desses valores.</span><span class="sxs-lookup"><span data-stu-id="76c16-155">The values can be passed to the **Option** parameter as an array of values or as a comma-separated string of those values.</span></span> <span data-ttu-id="76c16-156">O cmdlet combinará os valores usando uma operação binary ou.</span><span class="sxs-lookup"><span data-stu-id="76c16-156">The cmdlet will combine the values using a binary-OR operation.</span></span> <span data-ttu-id="76c16-157">Passar valores como uma matriz é a opção mais simples e também permite que você use a conclusão de tabulação nos valores.</span><span class="sxs-lookup"><span data-stu-id="76c16-157">Passing values as an array is the simplest option and also allows you to use tab-completion on the values.</span></span>

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

### <span data-ttu-id="76c16-158">-PassThru</span><span class="sxs-lookup"><span data-stu-id="76c16-158">-PassThru</span></span>

<span data-ttu-id="76c16-159">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="76c16-159">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="76c16-160">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="76c16-160">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="76c16-161">-PSHost</span><span class="sxs-lookup"><span data-stu-id="76c16-161">-PSHost</span></span>

<span data-ttu-id="76c16-162">Indica que esse cmdlet envia a saída de rastreamento para o host do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76c16-162">Indicates that this cmdlet sends the trace output to the PowerShell host.</span></span> <span data-ttu-id="76c16-163">Esse parâmetro também seleciona o ouvinte de rastreamento PSHost.</span><span class="sxs-lookup"><span data-stu-id="76c16-163">This parameter also selects the PSHost trace listener.</span></span>

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

### <span data-ttu-id="76c16-164">-RemoveFileListener</span><span class="sxs-lookup"><span data-stu-id="76c16-164">-RemoveFileListener</span></span>

<span data-ttu-id="76c16-165">Interrompe o rastreamento, removendo o ouvinte de rastreamento do arquivo associado ao arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="76c16-165">Stops the trace by removing the file trace listener associated with the specified file.</span></span> <span data-ttu-id="76c16-166">Digite o caminho e o nome do arquivo de saída de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="76c16-166">Enter the path and file name of the trace output file.</span></span>

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

### <span data-ttu-id="76c16-167">-RemoveListener</span><span class="sxs-lookup"><span data-stu-id="76c16-167">-RemoveListener</span></span>

<span data-ttu-id="76c16-168">Interrompe o rastreamento, removendo o ouvinte de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="76c16-168">Stops the trace by removing the trace listener.</span></span>

<span data-ttu-id="76c16-169">Use os seguintes valores com **RemoveListener**:</span><span class="sxs-lookup"><span data-stu-id="76c16-169">Use the following values with **RemoveListener**:</span></span>

- <span data-ttu-id="76c16-170">Para remover PSHost (console), digite `Host` .</span><span class="sxs-lookup"><span data-stu-id="76c16-170">To remove PSHost (console), type `Host`.</span></span>
- <span data-ttu-id="76c16-171">Para remover o depurador, digite `Debug` .</span><span class="sxs-lookup"><span data-stu-id="76c16-171">To remove Debugger, type `Debug`.</span></span>
- <span data-ttu-id="76c16-172">Para remover todos os ouvintes de rastreamento, digite `*` .</span><span class="sxs-lookup"><span data-stu-id="76c16-172">To remove all trace listeners, type `*`.</span></span>

<span data-ttu-id="76c16-173">Para remover o ouvinte de rastreamento de arquivo, use o parâmetro **RemoveFileListener** .</span><span class="sxs-lookup"><span data-stu-id="76c16-173">To remove the file trace listener, use the **RemoveFileListener** parameter.</span></span>

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

### <span data-ttu-id="76c16-174">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="76c16-174">CommonParameters</span></span>

<span data-ttu-id="76c16-175">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="76c16-175">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="76c16-176">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="76c16-176">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="76c16-177">Entradas</span><span class="sxs-lookup"><span data-stu-id="76c16-177">Inputs</span></span>

### <span data-ttu-id="76c16-178">System.String</span><span class="sxs-lookup"><span data-stu-id="76c16-178">System.String</span></span>

<span data-ttu-id="76c16-179">É possível canalizar uma cadeia de caracteres que contém um nome para `Set-TraceSource` .</span><span class="sxs-lookup"><span data-stu-id="76c16-179">You can pipe a string that contains a name to `Set-TraceSource`.</span></span>

## <span data-ttu-id="76c16-180">Saídas</span><span class="sxs-lookup"><span data-stu-id="76c16-180">Outputs</span></span>

### <span data-ttu-id="76c16-181">Nenhum ou System. Management. Automation. PSTraceSource</span><span class="sxs-lookup"><span data-stu-id="76c16-181">None or System.Management.Automation.PSTraceSource</span></span>

<span data-ttu-id="76c16-182">Quando você usa o parâmetro **PassThru** , o `Set-TraceSource` gera um objeto **System. Management. Automation. PSTraceSource** que representa a sessão de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="76c16-182">When you use the **PassThru** parameter, `Set-TraceSource` generates a **System.Management.Automation.PSTraceSource** object representing the trace session.</span></span> <span data-ttu-id="76c16-183">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="76c16-183">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="76c16-184">Observações</span><span class="sxs-lookup"><span data-stu-id="76c16-184">Notes</span></span>

- <span data-ttu-id="76c16-185">O rastreamento é um método utilizado pelos desenvolvedores para depurar e aprimorar os programas.</span><span class="sxs-lookup"><span data-stu-id="76c16-185">Tracing is a method that developers use to debug and refine programs.</span></span> <span data-ttu-id="76c16-186">Ao realizar o rastreamento, o componente gera mensagens detalhadas sobre cada etapa no seu processamento interno.</span><span class="sxs-lookup"><span data-stu-id="76c16-186">When tracing, the program generates detailed messages about each step in its internal processing.</span></span>

  <span data-ttu-id="76c16-187">Os cmdlets de rastreamento do PowerShell são projetados para ajudar os desenvolvedores do PowerShell, mas estão disponíveis para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="76c16-187">The PowerShell tracing cmdlets are designed to help PowerShell developers, but they are available to all users.</span></span> <span data-ttu-id="76c16-188">Eles permitem monitorar quase todos os aspectos da funcionalidade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76c16-188">They let you monitor nearly every aspect of the functionality of PowerShell.</span></span>

  <span data-ttu-id="76c16-189">Uma origem de rastreamento é a parte de cada componente do PowerShell que gerencia o rastreamento e gera mensagens de rastreamento para o componente.</span><span class="sxs-lookup"><span data-stu-id="76c16-189">A trace source is the part of each PowerShell component that manages tracing and generates trace messages for the component.</span></span> <span data-ttu-id="76c16-190">Para rastrear um componente, você deve identificar sua origem de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="76c16-190">To trace a component, you identify its trace source.</span></span>

  <span data-ttu-id="76c16-191">Um ouvinte de rastreamento recebe a saída do rastreamento e o exibe para o usuário.</span><span class="sxs-lookup"><span data-stu-id="76c16-191">A trace listener receives the output of the trace and displays it to the user.</span></span> <span data-ttu-id="76c16-192">Você pode optar por enviar os dados de rastreamento para um modo de usuário ou depurador de modo kernel, para o console, para um arquivo ou para um ouvinte personalizado derivado da classe **System. Diagnostics. TraceListener** .</span><span class="sxs-lookup"><span data-stu-id="76c16-192">You can elect to send the trace data to a user-mode or kernel-mode debugger, to the console, to a file, or to a custom listener derived from the **System.Diagnostics.TraceListener** class.</span></span>

- <span data-ttu-id="76c16-193">Para iniciar um rastreamento, use o parâmetro **Name** para especificar uma origem de rastreamento e os parâmetros **FilePath**, **Debugger** ou **PSHost** para especificar um ouvinte (um destino para a saída).</span><span class="sxs-lookup"><span data-stu-id="76c16-193">To start a trace, use the **Name** parameter to specify a trace source and the **FilePath**, **Debugger**, or **PSHost** parameters to specify a listener (a destination for the output).</span></span> <span data-ttu-id="76c16-194">Use o parâmetro **Options** para determinar os tipos de eventos que são rastreados e o parâmetro **ListenerOption** para configurar a saída de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="76c16-194">Use the **Options** parameter to determine the types of events that are traced and the **ListenerOption** parameter to configure the trace output.</span></span>
- <span data-ttu-id="76c16-195">Para alterar a configuração de um rastreamento, insira um `Set-TraceSource` comando como você faria para iniciar um rastreamento.</span><span class="sxs-lookup"><span data-stu-id="76c16-195">To change the configuration of a trace, enter a `Set-TraceSource` command as you would to start a trace.</span></span> <span data-ttu-id="76c16-196">O PowerShell reconhece que a origem do rastreamento já está sendo rastreada.</span><span class="sxs-lookup"><span data-stu-id="76c16-196">PowerShell recognizes that the trace source is already being traced.</span></span> <span data-ttu-id="76c16-197">Ele interrompe o rastreamento, adiciona a nova configuração e inicia ou reinicia o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="76c16-197">It stops the trace, adds the new configuration, and starts or restarts the trace.</span></span>
- <span data-ttu-id="76c16-198">Para interromper um rastreamento, use o parâmetro **RemoveListener** .</span><span class="sxs-lookup"><span data-stu-id="76c16-198">To stop a trace, use the **RemoveListener** parameter.</span></span> <span data-ttu-id="76c16-199">Para interromper um rastreamento que usa o ouvinte de arquivo (um rastreamento iniciado usando o parâmetro **FilePath** ), use o parâmetro **RemoveFileListener** .</span><span class="sxs-lookup"><span data-stu-id="76c16-199">To stop a trace that uses the file listener (a trace started by using the **FilePath** parameter), use the **RemoveFileListener** parameter.</span></span>
  <span data-ttu-id="76c16-200">Quando você remove o ouvinte, o rastreamento é interrompido.</span><span class="sxs-lookup"><span data-stu-id="76c16-200">When you remove the listener, the trace stops.</span></span>
- <span data-ttu-id="76c16-201">Para determinar quais componentes podem ser rastreados, use Get-TraceSource.</span><span class="sxs-lookup"><span data-stu-id="76c16-201">To determine which components can be traced, use Get-TraceSource.</span></span> <span data-ttu-id="76c16-202">As origens de rastreamento para cada módulo são carregadas automaticamente quando o componente está em uso e aparecem na saída de `Get-TraceSource` .</span><span class="sxs-lookup"><span data-stu-id="76c16-202">The trace sources for each module are loaded automatically when the component is in use, and they appear in the output of `Get-TraceSource`.</span></span>

## <span data-ttu-id="76c16-203">Links Relacionados</span><span class="sxs-lookup"><span data-stu-id="76c16-203">Related Links</span></span>

[<span data-ttu-id="76c16-204">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="76c16-204">Get-TraceSource</span></span>](Get-TraceSource.md)

[<span data-ttu-id="76c16-205">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="76c16-205">Trace-Command</span></span>](Trace-Command.md)

