---
description: Descreve como as funções que especificam o `CmdletBinding` atributo podem usar os métodos e as propriedades que estão disponíveis para cmdlets compilados.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_advanced_methods?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_Advanced_Methods
ms.openlocfilehash: 862c57d326049096ada28353b74485f8519f46da
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196348"
---
# <a name="about-functions-advanced-methods"></a><span data-ttu-id="e72dc-104">Sobre os métodos avançados do Functions</span><span class="sxs-lookup"><span data-stu-id="e72dc-104">About Functions Advanced Methods</span></span>

## <a name="short-description"></a><span data-ttu-id="e72dc-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="e72dc-105">Short description</span></span>

<span data-ttu-id="e72dc-106">Descreve como as funções que especificam o `CmdletBinding` atributo podem usar os métodos e as propriedades que estão disponíveis para cmdlets compilados.</span><span class="sxs-lookup"><span data-stu-id="e72dc-106">Describes how functions that specify the `CmdletBinding` attribute can use the methods and properties that are available to compiled cmdlets.</span></span>

## <a name="long-description"></a><span data-ttu-id="e72dc-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="e72dc-107">Long description</span></span>

<span data-ttu-id="e72dc-108">As funções que especificam o `CmdletBinding` atributo podem acessar vários métodos e propriedades por meio da `$PSCmdlet` variável.</span><span class="sxs-lookup"><span data-stu-id="e72dc-108">Functions that specify the `CmdletBinding` attribute can access a number of methods and properties through the `$PSCmdlet` variable.</span></span> <span data-ttu-id="e72dc-109">Esses métodos incluem os seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="e72dc-109">These methods include the following methods:</span></span>

- <span data-ttu-id="e72dc-110">Métodos de processamento de entrada que os cmdlets compilados usam para realizar seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="e72dc-110">Input-processing methods that compiled cmdlets use to do their work.</span></span>
- <span data-ttu-id="e72dc-111">Os `ShouldProcess` `ShouldContinue` métodos e que são usados para obter comentários do usuário antes que uma ação seja executada.</span><span class="sxs-lookup"><span data-stu-id="e72dc-111">The `ShouldProcess` and `ShouldContinue` methods that are used to get user feedback before an action is performed.</span></span>
- <span data-ttu-id="e72dc-112">O `ThrowTerminatingError` método para gerar registros de erro.</span><span class="sxs-lookup"><span data-stu-id="e72dc-112">The `ThrowTerminatingError` method for generating error records.</span></span>
- <span data-ttu-id="e72dc-113">Vários `Write` métodos que retornam tipos diferentes de saída.</span><span class="sxs-lookup"><span data-stu-id="e72dc-113">Several `Write` methods that return different types of output.</span></span>

<span data-ttu-id="e72dc-114">Todos os métodos e propriedades da classe **PSCmdlet** estão disponíveis para funções avançadas.</span><span class="sxs-lookup"><span data-stu-id="e72dc-114">All the methods and properties of the **PSCmdlet** class are available to advanced functions.</span></span> <span data-ttu-id="e72dc-115">Para obter mais informações, consulte [System. Management. Automation. PSCmdlet](/dotnet/api/system.management.automation.pscmdlet).</span><span class="sxs-lookup"><span data-stu-id="e72dc-115">For more information, see [System.Management.Automation.PSCmdlet](/dotnet/api/system.management.automation.pscmdlet).</span></span>

<span data-ttu-id="e72dc-116">Para obter mais informações sobre o `CmdletBinding` atributo, consulte [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span><span class="sxs-lookup"><span data-stu-id="e72dc-116">For more information about the `CmdletBinding` attribute, see [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span></span>
<span data-ttu-id="e72dc-117">Para a classe **CmdletBindingAttribute** , consulte [System. Management. Automation. cmdlet. CmdletBindingAttribute](/dotnet/api/system.management.automation.cmdletbindingattribute).</span><span class="sxs-lookup"><span data-stu-id="e72dc-117">For the **CmdletBindingAttribute** class, see [System.Management.Automation.Cmdlet.CmdletBindingAttribute](/dotnet/api/system.management.automation.cmdletbindingattribute).</span></span>

### <a name="input-processing-methods"></a><span data-ttu-id="e72dc-118">Métodos de processamento de entrada</span><span class="sxs-lookup"><span data-stu-id="e72dc-118">Input processing methods</span></span>

<span data-ttu-id="e72dc-119">Os métodos descritos nesta seção são chamados de métodos de processamento de entrada.</span><span class="sxs-lookup"><span data-stu-id="e72dc-119">The methods described in this section are referred to as the input processing methods.</span></span> <span data-ttu-id="e72dc-120">Para funções, esses três métodos são representados pelos `Begin` `Process` blocos, e `End` da função.</span><span class="sxs-lookup"><span data-stu-id="e72dc-120">For functions, these three methods are represented by the `Begin`, `Process`, and `End` blocks of the function.</span></span> <span data-ttu-id="e72dc-121">Você não precisa usar nenhum desses blocos em suas funções.</span><span class="sxs-lookup"><span data-stu-id="e72dc-121">You aren't required to use any of these blocks in your functions.</span></span>

> [!NOTE]
> <span data-ttu-id="e72dc-122">Esses blocos também estão disponíveis para funções que não usam o `CmdletBinding` atributo.</span><span class="sxs-lookup"><span data-stu-id="e72dc-122">These blocks are also available to functions that don't use the `CmdletBinding` attribute.</span></span>

#### <a name="begin"></a><span data-ttu-id="e72dc-123">Começar</span><span class="sxs-lookup"><span data-stu-id="e72dc-123">Begin</span></span>

<span data-ttu-id="e72dc-124">Esse bloco é usado para fornecer um pré-processamento de uso único opcional para a função.</span><span class="sxs-lookup"><span data-stu-id="e72dc-124">This block is used to provide optional one-time preprocessing for the function.</span></span>
<span data-ttu-id="e72dc-125">O tempo de execução do PowerShell usa o código nesse bloco uma vez para cada instância da função no pipeline.</span><span class="sxs-lookup"><span data-stu-id="e72dc-125">The PowerShell runtime uses the code in this block once for each instance of the function in the pipeline.</span></span>

#### <a name="process"></a><span data-ttu-id="e72dc-126">Processar</span><span class="sxs-lookup"><span data-stu-id="e72dc-126">Process</span></span>

<span data-ttu-id="e72dc-127">Esse bloco é usado para fornecer processamento de registro por registro para a função.</span><span class="sxs-lookup"><span data-stu-id="e72dc-127">This block is used to provide record-by-record processing for the function.</span></span> <span data-ttu-id="e72dc-128">Você pode usar um `Process` bloco sem definir os outros blocos.</span><span class="sxs-lookup"><span data-stu-id="e72dc-128">You can use a `Process` block without defining the other blocks.</span></span> <span data-ttu-id="e72dc-129">O número de `Process` execuções de bloco depende de como você usa a função e a entrada que a função recebe.</span><span class="sxs-lookup"><span data-stu-id="e72dc-129">The number of `Process` block executions depends on how you use the function and what input the function receives.</span></span>

<span data-ttu-id="e72dc-130">A variável automática `$_` ou `$PSItem` contém o objeto atual no pipeline para uso no `Process` bloco.</span><span class="sxs-lookup"><span data-stu-id="e72dc-130">The automatic variable `$_` or `$PSItem` contains the current object in the pipeline for use in the `Process` block.</span></span> <span data-ttu-id="e72dc-131">A `$input` variável automática contém um enumerador que só está disponível para funções e blocos de script.</span><span class="sxs-lookup"><span data-stu-id="e72dc-131">The `$input` automatic variable contains an enumerator that's only available to functions and script blocks.</span></span>
<span data-ttu-id="e72dc-132">Para obter mais informações, consulte [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="e72dc-132">For more information, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

- <span data-ttu-id="e72dc-133">Chamar a função no início ou fora de um pipeline executa o `Process` bloco uma vez.</span><span class="sxs-lookup"><span data-stu-id="e72dc-133">Calling the function at the beginning, or outside of a pipeline, executes the `Process` block once.</span></span>
- <span data-ttu-id="e72dc-134">Em um pipeline, o `Process` bloco é executado uma vez para cada objeto de entrada que atinge a função.</span><span class="sxs-lookup"><span data-stu-id="e72dc-134">Within a pipeline, the `Process` block executes once for each input object that reaches the function.</span></span>
- <span data-ttu-id="e72dc-135">Se a entrada do pipeline que atinge a função estiver vazia, o `Process` bloco **não será** executado.</span><span class="sxs-lookup"><span data-stu-id="e72dc-135">If the pipeline input that reaches the function is empty, the `Process` block **does not** execute.</span></span>
  - <span data-ttu-id="e72dc-136">Os `Begin` `End` blocos e ainda são executados.</span><span class="sxs-lookup"><span data-stu-id="e72dc-136">The `Begin` and `End` blocks still execute.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e72dc-137">Se um parâmetro de função for definido para aceitar a entrada de pipeline e um `Process` bloco não estiver definido, o processamento de registro por registro falhará.</span><span class="sxs-lookup"><span data-stu-id="e72dc-137">If a function parameter is set to accept pipeline input, and a `Process` block isn't defined, record-by-record processing will fail.</span></span> <span data-ttu-id="e72dc-138">Nesse caso, sua função será executada apenas uma vez, independentemente da entrada.</span><span class="sxs-lookup"><span data-stu-id="e72dc-138">In this case, your function will only execute once, regardless of the input.</span></span>

#### <a name="end"></a><span data-ttu-id="e72dc-139">End</span><span class="sxs-lookup"><span data-stu-id="e72dc-139">End</span></span>

<span data-ttu-id="e72dc-140">Esse bloco é usado para fornecer um pós-processamento único opcional para a função.</span><span class="sxs-lookup"><span data-stu-id="e72dc-140">This block is used to provide optional one-time post-processing for the function.</span></span>

<span data-ttu-id="e72dc-141">O exemplo a seguir mostra o contorno de uma função que contém um `Begin` bloco para o pré-processamento único, um `Process` bloco para o processamento de vários registros e um `End` bloco para o pós-processamento único.</span><span class="sxs-lookup"><span data-stu-id="e72dc-141">The following example shows the outline of a function that contains a `Begin` block for one-time preprocessing, a `Process` block for multiple record processing, and an `End` block for one-time post-processing.</span></span>

```powershell
Function Test-ScriptCmdlet
{
[CmdletBinding(SupportsShouldProcess=$True)]
    Param ($Parameter1)
    Begin{}
    Process{}
    End{}
}
```

> [!NOTE]
> <span data-ttu-id="e72dc-142">O uso de `Begin` um `End` bloco ou requer que você defina todos os três blocos.</span><span class="sxs-lookup"><span data-stu-id="e72dc-142">Using either a `Begin` or `End` block requires that you define all three blocks.</span></span> <span data-ttu-id="e72dc-143">Ao usar todos os três blocos, todo o código do PowerShell deve estar dentro de um dos blocos.</span><span class="sxs-lookup"><span data-stu-id="e72dc-143">When using all three blocks, all PowerShell code must be inside one of the blocks.</span></span>

### <a name="confirmation-methods"></a><span data-ttu-id="e72dc-144">Métodos de confirmação</span><span class="sxs-lookup"><span data-stu-id="e72dc-144">Confirmation methods</span></span>

#### <a name="shouldprocess"></a><span data-ttu-id="e72dc-145">ShouldProcess</span><span class="sxs-lookup"><span data-stu-id="e72dc-145">ShouldProcess</span></span>

<span data-ttu-id="e72dc-146">Esse método é chamado para solicitar a confirmação do usuário antes que a função execute uma ação que altere o sistema.</span><span class="sxs-lookup"><span data-stu-id="e72dc-146">This method is called to request confirmation from the user before the function performs an action that would change the system.</span></span> <span data-ttu-id="e72dc-147">A função pode continuar com base no valor booliano retornado pelo método.</span><span class="sxs-lookup"><span data-stu-id="e72dc-147">The function can continue based on the Boolean value returned by the method.</span></span> <span data-ttu-id="e72dc-148">Esse método só pode ser chamado somente de dentro do `Process{}` bloco da função.</span><span class="sxs-lookup"><span data-stu-id="e72dc-148">This method can only be called only from within the `Process{}` block of the function.</span></span> <span data-ttu-id="e72dc-149">O `CmdletBinding` atributo também deve declarar que a função dá suporte `ShouldProcess` (conforme mostrado no exemplo anterior).</span><span class="sxs-lookup"><span data-stu-id="e72dc-149">The `CmdletBinding` attribute must also declare that the function supports `ShouldProcess` (as shown in the previous example).</span></span>

<span data-ttu-id="e72dc-150">Para obter mais informações sobre esse método, consulte [System. Management. Automation. cmdlet. ShouldProcess](/dotnet/api/system.management.automation.cmdlet.shouldprocess).</span><span class="sxs-lookup"><span data-stu-id="e72dc-150">For more information about this method, see [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/system.management.automation.cmdlet.shouldprocess).</span></span>

<span data-ttu-id="e72dc-151">Para obter mais informações sobre como solicitar confirmação, consulte [solicitando confirmação](/powershell/scripting/developer/cmdlet/requesting-confirmation).</span><span class="sxs-lookup"><span data-stu-id="e72dc-151">For more information about how to request confirmation, see [Requesting Confirmation](/powershell/scripting/developer/cmdlet/requesting-confirmation).</span></span>

#### <a name="shouldcontinue"></a><span data-ttu-id="e72dc-152">ShouldContinue</span><span class="sxs-lookup"><span data-stu-id="e72dc-152">ShouldContinue</span></span>

<span data-ttu-id="e72dc-153">Esse método é chamado para solicitar uma segunda mensagem de confirmação.</span><span class="sxs-lookup"><span data-stu-id="e72dc-153">This method is called to request a second confirmation message.</span></span> <span data-ttu-id="e72dc-154">Ele deve ser chamado quando o `ShouldProcess` método retornar `$true` .</span><span class="sxs-lookup"><span data-stu-id="e72dc-154">It should be called when the `ShouldProcess` method returns `$true`.</span></span> <span data-ttu-id="e72dc-155">Para obter mais informações sobre esse método, consulte [System. Management. Automation. cmdlet. ShouldContinue](/dotnet/api/system.management.automation.cmdlet.shouldcontinue).</span><span class="sxs-lookup"><span data-stu-id="e72dc-155">For more information about this method, see [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/system.management.automation.cmdlet.shouldcontinue).</span></span>

### <a name="error-methods"></a><span data-ttu-id="e72dc-156">Métodos de erro</span><span class="sxs-lookup"><span data-stu-id="e72dc-156">Error methods</span></span>

<span data-ttu-id="e72dc-157">As funções podem chamar dois métodos diferentes quando ocorrem erros.</span><span class="sxs-lookup"><span data-stu-id="e72dc-157">Functions can call two different methods when errors occur.</span></span> <span data-ttu-id="e72dc-158">Quando ocorre um erro de não finalização, a função deve chamar o `WriteError` método, que é descrito na `Write` seção métodos.</span><span class="sxs-lookup"><span data-stu-id="e72dc-158">When a non-terminating error occurs, the function should call the `WriteError` method, which is described in the `Write` methods section.</span></span> <span data-ttu-id="e72dc-159">Quando ocorre um erro de encerramento e a função não pode continuar, ele deve chamar o `ThrowTerminatingError` método.</span><span class="sxs-lookup"><span data-stu-id="e72dc-159">When a terminating error occurs and the function can't continue, it should call the `ThrowTerminatingError` method.</span></span> <span data-ttu-id="e72dc-160">Você também pode usar a `Throw` instrução para erros de encerramento e o cmdlet [Write-Error](xref:Microsoft.PowerShell.Utility.Write-Error) para erros de não encerramento.</span><span class="sxs-lookup"><span data-stu-id="e72dc-160">You can also use the `Throw` statement for terminating errors and the [Write-Error](xref:Microsoft.PowerShell.Utility.Write-Error) cmdlet for non-terminating errors.</span></span>

<span data-ttu-id="e72dc-161">Para obter mais informações, consulte [System. Management. Automation. cmdlet. ThrowTerminatingError](/dotnet/api/system.management.automation.cmdlet.throwterminatingerror).</span><span class="sxs-lookup"><span data-stu-id="e72dc-161">For more information, see [System.Management.Automation.Cmdlet.ThrowTerminatingError](/dotnet/api/system.management.automation.cmdlet.throwterminatingerror).</span></span>

### <a name="write-methods"></a><span data-ttu-id="e72dc-162">Métodos de gravação</span><span class="sxs-lookup"><span data-stu-id="e72dc-162">Write methods</span></span>

<span data-ttu-id="e72dc-163">Uma função pode chamar os métodos a seguir para retornar tipos diferentes de saída.</span><span class="sxs-lookup"><span data-stu-id="e72dc-163">A function can call the following methods to return different types of output.</span></span>
<span data-ttu-id="e72dc-164">Observe que nem toda a saída vai para o próximo comando no pipeline.</span><span class="sxs-lookup"><span data-stu-id="e72dc-164">Notice that not all the output goes to the next command in the pipeline.</span></span> <span data-ttu-id="e72dc-165">Você também pode usar os vários `Write` cmdlets, como `Write-Error` .</span><span class="sxs-lookup"><span data-stu-id="e72dc-165">You can also use the various `Write` cmdlets, such as `Write-Error`.</span></span>

#### <a name="writecommanddetail"></a><span data-ttu-id="e72dc-166">WriteCommandDetail</span><span class="sxs-lookup"><span data-stu-id="e72dc-166">WriteCommandDetail</span></span>

<span data-ttu-id="e72dc-167">Para obter informações sobre o `WriteCommandDetails` método, consulte [System. Management. Automation. cmdlet. WriteCommandDetail](/dotnet/api/system.management.automation.cmdlet.writecommanddetail).</span><span class="sxs-lookup"><span data-stu-id="e72dc-167">For information about the `WriteCommandDetails` method, see [System.Management.Automation.Cmdlet.WriteCommandDetail](/dotnet/api/system.management.automation.cmdlet.writecommanddetail).</span></span>

#### <a name="writedebug"></a><span data-ttu-id="e72dc-168">WriteDebug</span><span class="sxs-lookup"><span data-stu-id="e72dc-168">WriteDebug</span></span>

<span data-ttu-id="e72dc-169">Para fornecer informações que podem ser usadas para solucionar problemas de uma função, faça com que a função chame o `WriteDebug` método.</span><span class="sxs-lookup"><span data-stu-id="e72dc-169">To provide information that can be used to troubleshoot a function, make the function call the `WriteDebug` method.</span></span> <span data-ttu-id="e72dc-170">O `WriteDebug` método exibe mensagens de depuração para o usuário.</span><span class="sxs-lookup"><span data-stu-id="e72dc-170">The `WriteDebug` method displays debug messages to the user.</span></span> <span data-ttu-id="e72dc-171">Para obter mais informações, consulte [System. Management. Automation. cmdlet. WriteDebug](/dotnet/api/system.management.automation.cmdlet.writedebug).</span><span class="sxs-lookup"><span data-stu-id="e72dc-171">For more information, see [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/system.management.automation.cmdlet.writedebug).</span></span>

#### <a name="writeerror"></a><span data-ttu-id="e72dc-172">WriteError</span><span class="sxs-lookup"><span data-stu-id="e72dc-172">WriteError</span></span>

<span data-ttu-id="e72dc-173">As funções devem chamar esse método quando ocorrerem erros de não encerramento e a função for projetada para continuar processando registros.</span><span class="sxs-lookup"><span data-stu-id="e72dc-173">Functions should call this method when non-terminating errors occur and the function is designed to continue processing records.</span></span> <span data-ttu-id="e72dc-174">Para obter mais informações, consulte [System. Management. Automation. cmdlet. WriteError](/dotnet/api/system.management.automation.cmdlet.writeerror).</span><span class="sxs-lookup"><span data-stu-id="e72dc-174">For more information, see [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/system.management.automation.cmdlet.writeerror).</span></span>

> [!NOTE]
> <span data-ttu-id="e72dc-175">Se ocorrer um erro de encerramento, a função deverá chamar o método [ThrowTerminatingError](/dotnet/api/system.management.automation.cmdlet.throwterminatingerror) .</span><span class="sxs-lookup"><span data-stu-id="e72dc-175">If a terminating error occurs, the function should call the [ThrowTerminatingError](/dotnet/api/system.management.automation.cmdlet.throwterminatingerror) method.</span></span>

#### <a name="writeobject"></a><span data-ttu-id="e72dc-176">WriteObject</span><span class="sxs-lookup"><span data-stu-id="e72dc-176">WriteObject</span></span>

<span data-ttu-id="e72dc-177">O `WriteObject` método permite que a função envie um objeto para o próximo comando no pipeline.</span><span class="sxs-lookup"><span data-stu-id="e72dc-177">The `WriteObject` method allows the function to send an object to the next command in the pipeline.</span></span> <span data-ttu-id="e72dc-178">Na maioria dos casos, `WriteObject` é o método a ser usado quando a função retorna dados.</span><span class="sxs-lookup"><span data-stu-id="e72dc-178">In most cases, `WriteObject` is the method to use when the function returns data.</span></span> <span data-ttu-id="e72dc-179">Para obter mais informações, consulte [System. Management. Automation. PSCmdlet. WriteObject](/dotnet/api/system.management.automation.cmdlet.writeobject).</span><span class="sxs-lookup"><span data-stu-id="e72dc-179">For more information, see [System.Management.Automation.PSCmdlet.WriteObject](/dotnet/api/system.management.automation.cmdlet.writeobject).</span></span>

#### <a name="writeprogress"></a><span data-ttu-id="e72dc-180">WriteProgress</span><span class="sxs-lookup"><span data-stu-id="e72dc-180">WriteProgress</span></span>

<span data-ttu-id="e72dc-181">Para funções com ações que levam muito tempo para serem concluídas, esse método permite que a função chame o `WriteProgress` método para que as informações de progresso sejam exibidas.</span><span class="sxs-lookup"><span data-stu-id="e72dc-181">For functions with actions that take a long time to complete, this method allows the function to call the `WriteProgress` method so that progress information is displayed.</span></span> <span data-ttu-id="e72dc-182">Por exemplo, você pode exibir a porcentagem concluída.</span><span class="sxs-lookup"><span data-stu-id="e72dc-182">For example, you can display the percent completed.</span></span>
<span data-ttu-id="e72dc-183">Para obter mais informações, consulte [System. Management. Automation. PSCmdlet. WriteProgress](/dotnet/api/system.management.automation.cmdlet.writeprogress).</span><span class="sxs-lookup"><span data-stu-id="e72dc-183">For more information, see [System.Management.Automation.PSCmdlet.WriteProgress](/dotnet/api/system.management.automation.cmdlet.writeprogress).</span></span>

#### <a name="writeverbose"></a><span data-ttu-id="e72dc-184">WriteVerbose</span><span class="sxs-lookup"><span data-stu-id="e72dc-184">WriteVerbose</span></span>

<span data-ttu-id="e72dc-185">Para fornecer informações detalhadas sobre o que a função está fazendo, faça com que a função chame o `WriteVerbose` método para exibir mensagens detalhadas ao usuário.</span><span class="sxs-lookup"><span data-stu-id="e72dc-185">To provide detailed information about what the function is doing, make the function call the `WriteVerbose` method to display verbose messages to the user.</span></span> <span data-ttu-id="e72dc-186">Por padrão, as mensagens detalhadas não são exibidas.</span><span class="sxs-lookup"><span data-stu-id="e72dc-186">By default, verbose messages aren't displayed.</span></span> <span data-ttu-id="e72dc-187">Para obter mais informações, consulte [System. Management. Automation. PSCmdlet. WriteVerbose](/dotnet/api/system.management.automation.cmdlet.writeverbose).</span><span class="sxs-lookup"><span data-stu-id="e72dc-187">For more information, see [System.Management.Automation.PSCmdlet.WriteVerbose](/dotnet/api/system.management.automation.cmdlet.writeverbose).</span></span>

#### <a name="writewarning"></a><span data-ttu-id="e72dc-188">WriteWarning</span><span class="sxs-lookup"><span data-stu-id="e72dc-188">WriteWarning</span></span>

<span data-ttu-id="e72dc-189">Para fornecer informações sobre condições que podem causar resultados inesperados, faça com que a função chame o método WriteWarning para exibir mensagens de aviso ao usuário.</span><span class="sxs-lookup"><span data-stu-id="e72dc-189">To provide information about conditions that may cause unexpected results, make the function call the WriteWarning method to display warning messages to the user.</span></span> <span data-ttu-id="e72dc-190">Por padrão, as mensagens de aviso são exibidas.</span><span class="sxs-lookup"><span data-stu-id="e72dc-190">By default, warning messages are displayed.</span></span> <span data-ttu-id="e72dc-191">Para obter mais informações, consulte [System. Management. Automation. PSCmdlet. WriteWarning](/dotnet/api/system.management.automation.cmdlet.writewarning).</span><span class="sxs-lookup"><span data-stu-id="e72dc-191">For more information, see [System.Management.Automation.PSCmdlet.WriteWarning](/dotnet/api/system.management.automation.cmdlet.writewarning).</span></span>

> [!NOTE]
> <span data-ttu-id="e72dc-192">Você também pode exibir mensagens de aviso Configurando a `$WarningPreference` variável ou usando `Verbose` as `Debug` Opções de linha de comando e.</span><span class="sxs-lookup"><span data-stu-id="e72dc-192">You can also display warning messages by configuring the `$WarningPreference` variable or by using the `Verbose` and `Debug` command-line options.</span></span> <span data-ttu-id="e72dc-193">para obter mais informações sobre a `$WarningPreference` variável, consulte [about_Preference_Variables](about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="e72dc-193">for more information about the `$WarningPreference` variable, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

### <a name="other-methods-and-properties"></a><span data-ttu-id="e72dc-194">Outros métodos e propriedades</span><span class="sxs-lookup"><span data-stu-id="e72dc-194">Other methods and properties</span></span>

<span data-ttu-id="e72dc-195">Para obter informações sobre os outros métodos e propriedades que podem ser acessados por meio da `$PSCmdlet` variável, consulte [System. Management. Automation. PSCmdlet](/dotnet/api/system.management.automation.pscmdlet).</span><span class="sxs-lookup"><span data-stu-id="e72dc-195">For information about the other methods and properties that can be accessed through the `$PSCmdlet` variable, see [System.Management.Automation.PSCmdlet](/dotnet/api/system.management.automation.pscmdlet).</span></span>

<span data-ttu-id="e72dc-196">Por exemplo, a propriedade [ParameterSetName](/dotnet/api/system.management.automation.pscmdlet.parametersetname) permite que você veja o conjunto de parâmetros que está sendo usado.</span><span class="sxs-lookup"><span data-stu-id="e72dc-196">For example, the [ParameterSetName](/dotnet/api/system.management.automation.pscmdlet.parametersetname) property allows you to see the parameter set that is being used.</span></span> <span data-ttu-id="e72dc-197">Os conjuntos de parâmetros permitem que você crie uma função que executa diferentes tarefas com base nos parâmetros especificados quando a função é executada.</span><span class="sxs-lookup"><span data-stu-id="e72dc-197">Parameter sets allow you to create a function that performs different tasks based on the parameters that are specified when the function is run.</span></span>

## <a name="see-also"></a><span data-ttu-id="e72dc-198">Confira também</span><span class="sxs-lookup"><span data-stu-id="e72dc-198">See also</span></span>

[<span data-ttu-id="e72dc-199">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="e72dc-199">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="e72dc-200">about_Functions</span><span class="sxs-lookup"><span data-stu-id="e72dc-200">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="e72dc-201">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="e72dc-201">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="e72dc-202">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="e72dc-202">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="e72dc-203">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="e72dc-203">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="e72dc-204">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="e72dc-204">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)

[<span data-ttu-id="e72dc-205">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="e72dc-205">about_Preference_Variables</span></span>](about_Preference_Variables.md)

