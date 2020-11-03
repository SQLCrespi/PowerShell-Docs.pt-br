---
description: Descreve as variáveis que armazenam informações de estado do PowerShell. Essas variáveis são criadas e mantidas pelo PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 08/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_automatic_variables?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Automatic_Variables
ms.openlocfilehash: e7525ad8acd6dd5aa2dc65a8d49d03c1c6260bea
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195525"
---
# <a name="about-automatic-variables"></a><span data-ttu-id="66da3-105">Sobre variáveis automáticas</span><span class="sxs-lookup"><span data-stu-id="66da3-105">About Automatic Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="66da3-106">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="66da3-106">Short description</span></span>

<span data-ttu-id="66da3-107">Descreve as variáveis que armazenam informações de estado do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="66da3-107">Describes variables that store state information for PowerShell.</span></span> <span data-ttu-id="66da3-108">Essas variáveis são criadas e mantidas pelo PowerShell.</span><span class="sxs-lookup"><span data-stu-id="66da3-108">These variables are created and maintained by PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="66da3-109">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="66da3-109">Long description</span></span>

<span data-ttu-id="66da3-110">Conceitualmente, essas variáveis são consideradas como somente leitura.</span><span class="sxs-lookup"><span data-stu-id="66da3-110">Conceptually, these variables are considered to be read-only.</span></span> <span data-ttu-id="66da3-111">Embora eles **possam** ser gravados, para compatibilidade com versões anteriores, eles **não devem** ser gravados.</span><span class="sxs-lookup"><span data-stu-id="66da3-111">Even though they **can** be written to, for backward compatibility they **should not** be written to.</span></span>

<span data-ttu-id="66da3-112">Aqui está uma lista das variáveis automáticas no PowerShell:</span><span class="sxs-lookup"><span data-stu-id="66da3-112">Here is a list of the automatic variables in PowerShell:</span></span>

### <a name=""></a>$$

<span data-ttu-id="66da3-113">Contém o último token na última linha recebida pela sessão.</span><span class="sxs-lookup"><span data-stu-id="66da3-113">Contains the last token in the last line received by the session.</span></span>

### <a name=""></a><span data-ttu-id="66da3-114">$?</span><span class="sxs-lookup"><span data-stu-id="66da3-114">$?</span></span>

<span data-ttu-id="66da3-115">Contém o status de execução do último comando.</span><span class="sxs-lookup"><span data-stu-id="66da3-115">Contains the execution status of the last command.</span></span> <span data-ttu-id="66da3-116">Ele conterá **true** se o último comando tiver êxito e **false** se ele tiver falhado.</span><span class="sxs-lookup"><span data-stu-id="66da3-116">It contains **True** if the last command succeeded and **False** if it failed.</span></span>

<span data-ttu-id="66da3-117">Para cmdlets e funções avançadas que são executadas em vários estágios em um pipeline, por exemplo, em `process` `end` blocos and, chamando `this.WriteError()` ou `$PSCmdlet.WriteError()` respectivamente em qualquer ponto, serão definidos como `$?` **false** , como `this.ThrowTerminatingError()` e `$PSCmdlet.ThrowTerminatingError()` .</span><span class="sxs-lookup"><span data-stu-id="66da3-117">For cmdlets and advanced functions that are run at multiple stages in a pipeline, for example in both `process` and `end` blocks, calling `this.WriteError()` or `$PSCmdlet.WriteError()` respectively at any point will set `$?` to **False** , as will `this.ThrowTerminatingError()` and `$PSCmdlet.ThrowTerminatingError()`.</span></span>

<span data-ttu-id="66da3-118">O `Write-Error` cmdlet sempre define `$?` como **false** imediatamente após ser executado, mas não será definido `$?` como **false** para uma função que a chama:</span><span class="sxs-lookup"><span data-stu-id="66da3-118">The `Write-Error` cmdlet always sets `$?` to **False** immediately after it is executed, but will not set `$?` to **False** for a function calling it:</span></span>

```powershell
function Test-WriteError
{
    Write-Error "Bad"
    $? # $false
}

Test-WriteError
$? # $true
```

<span data-ttu-id="66da3-119">Para a última finalidade, `$PSCmdlet.WriteError()` deve ser usado em vez disso.</span><span class="sxs-lookup"><span data-stu-id="66da3-119">For the latter purpose, `$PSCmdlet.WriteError()` should be used instead.</span></span>

<span data-ttu-id="66da3-120">Para comandos nativos (executáveis), `$?` é definido como **true** quando `$LASTEXITCODE` é 0 e definido como **false** quando `$LASTEXITCODE` é qualquer outro valor.</span><span class="sxs-lookup"><span data-stu-id="66da3-120">For native commands (executables), `$?` is set to **True** when `$LASTEXITCODE` is 0, and set to **False** when `$LASTEXITCODE` is any other value.</span></span>

> [!NOTE]
> <span data-ttu-id="66da3-121">Até o PowerShell 7, que contém uma instrução entre parênteses `(...)` , sintaxe `$(...)` de subexpressão ou expressão `@(...)` de matriz sempre redefinida como `$?` **true** , para que seja `(Write-Error)` exibida `$?` como **verdadeira** .</span><span class="sxs-lookup"><span data-stu-id="66da3-121">Until PowerShell 7, containing a statement within parentheses `(...)`, subexpression syntax `$(...)` or array expression `@(...)` always reset `$?` to **True** , so that `(Write-Error)` shows `$?` as **True** .</span></span>
> <span data-ttu-id="66da3-122">Isso foi alterado no PowerShell 7, de modo que `$?` sempre refletirá o êxito real da execução do último comando nessas expressões.</span><span class="sxs-lookup"><span data-stu-id="66da3-122">This has been changed in PowerShell 7, so that `$?` will always reflect the actual success of the last command run in these expressions.</span></span>

### <a name=""></a>$^

<span data-ttu-id="66da3-123">Contém o primeiro token na última linha recebida pela sessão.</span><span class="sxs-lookup"><span data-stu-id="66da3-123">Contains the first token in the last line received by the session.</span></span>

### <a name="_"></a><span data-ttu-id="66da3-124">$_</span><span class="sxs-lookup"><span data-stu-id="66da3-124">$_</span></span>

<span data-ttu-id="66da3-125">Mesmo que `$PSItem`.</span><span class="sxs-lookup"><span data-stu-id="66da3-125">Same as `$PSItem`.</span></span> <span data-ttu-id="66da3-126">Contém o objeto atual no objeto de pipeline.</span><span class="sxs-lookup"><span data-stu-id="66da3-126">Contains the current object in the pipeline object.</span></span> <span data-ttu-id="66da3-127">Você pode usar essa variável em comandos que executam uma ação em cada objeto ou em objetos selecionados em um pipeline.</span><span class="sxs-lookup"><span data-stu-id="66da3-127">You can use this variable in commands that perform an action on every object or on selected objects in a pipeline.</span></span>

### <a name="args"></a><span data-ttu-id="66da3-128">$args</span><span class="sxs-lookup"><span data-stu-id="66da3-128">$args</span></span>

<span data-ttu-id="66da3-129">Contém uma matriz de valores para parâmetros não declarados que são passados para uma função, script ou bloco de script.</span><span class="sxs-lookup"><span data-stu-id="66da3-129">Contains an array of values for undeclared parameters that are passed to a function, script, or script block.</span></span> <span data-ttu-id="66da3-130">Ao criar uma função, você pode declarar os parâmetros usando a `param` palavra-chave ou adicionando uma lista separada por vírgulas de parâmetros entre parênteses após o nome da função.</span><span class="sxs-lookup"><span data-stu-id="66da3-130">When you create a function, you can declare the parameters by using the `param` keyword or by adding a comma-separated list of parameters in parentheses after the function name.</span></span>

<span data-ttu-id="66da3-131">Em uma ação de evento, a `$Args` variável contém objetos que representam os argumentos do evento que está sendo processado.</span><span class="sxs-lookup"><span data-stu-id="66da3-131">In an event action, the `$Args` variable contains objects that represent the event arguments of the event that is being processed.</span></span> <span data-ttu-id="66da3-132">Essa variável é populada somente dentro do `Action` bloco de um comando de registro de evento.</span><span class="sxs-lookup"><span data-stu-id="66da3-132">This variable is populated only within the `Action` block of an event registration command.</span></span>
<span data-ttu-id="66da3-133">O valor dessa variável também pode ser encontrado na propriedade **SourceArgs** do objeto **PSEventArgs** que `Get-Event` retorna.</span><span class="sxs-lookup"><span data-stu-id="66da3-133">The value of this variable can also be found in the **SourceArgs** property of the **PSEventArgs** object that `Get-Event` returns.</span></span>

### <a name="consolefilename"></a><span data-ttu-id="66da3-134">$ConsoleFileName</span><span class="sxs-lookup"><span data-stu-id="66da3-134">$ConsoleFileName</span></span>

<span data-ttu-id="66da3-135">Contém o caminho do arquivo de console ( `.psc1` ) que foi usado mais recentemente na sessão.</span><span class="sxs-lookup"><span data-stu-id="66da3-135">Contains the path of the console file (`.psc1`) that was most recently used in the session.</span></span> <span data-ttu-id="66da3-136">Essa variável é populada quando você inicia o PowerShell com o parâmetro **PSConsoleFile** ou quando usa o `Export-Console` cmdlet para exportar nomes de snap-in para um arquivo de console.</span><span class="sxs-lookup"><span data-stu-id="66da3-136">This variable is populated when you start PowerShell with the **PSConsoleFile** parameter or when you use the `Export-Console` cmdlet to export snap-in names to a console file.</span></span>

<span data-ttu-id="66da3-137">Quando você usa o `Export-Console` cmdlet sem parâmetros, ele atualiza automaticamente o arquivo de console que foi usado mais recentemente na sessão.</span><span class="sxs-lookup"><span data-stu-id="66da3-137">When you use the `Export-Console` cmdlet without parameters, it automatically updates the console file that was most recently used in the session.</span></span> <span data-ttu-id="66da3-138">Você pode usar essa variável automática para determinar qual arquivo será atualizado.</span><span class="sxs-lookup"><span data-stu-id="66da3-138">You can use this automatic variable to determine which file will be updated.</span></span>

### <a name="error"></a><span data-ttu-id="66da3-139">$Error</span><span class="sxs-lookup"><span data-stu-id="66da3-139">$Error</span></span>

<span data-ttu-id="66da3-140">Contém uma matriz de objetos de erro que representam os erros mais recentes.</span><span class="sxs-lookup"><span data-stu-id="66da3-140">Contains an array of error objects that represent the most recent errors.</span></span>
<span data-ttu-id="66da3-141">O erro mais recente é o primeiro objeto de erro na matriz `$Error[0]` .</span><span class="sxs-lookup"><span data-stu-id="66da3-141">The most recent error is the first error object in the array `$Error[0]`.</span></span>

<span data-ttu-id="66da3-142">Para impedir que um erro seja adicionado à `$Error` matriz, use o parâmetro comum **ErrorAction** com um valor de **ignorar** .</span><span class="sxs-lookup"><span data-stu-id="66da3-142">To prevent an error from being added to the `$Error` array, use the **ErrorAction** common parameter with a value of **Ignore** .</span></span> <span data-ttu-id="66da3-143">Para obter mais informações, confira [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="66da3-143">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

### <a name="event"></a><span data-ttu-id="66da3-144">$Event</span><span class="sxs-lookup"><span data-stu-id="66da3-144">$Event</span></span>

<span data-ttu-id="66da3-145">Contém um objeto **PSEventArgs** que representa o evento que está sendo processado.</span><span class="sxs-lookup"><span data-stu-id="66da3-145">Contains a **PSEventArgs** object that represents the event that is being processed.</span></span> <span data-ttu-id="66da3-146">Essa variável é populada somente dentro do `Action` bloco de um comando de registro de evento, como `Register-ObjectEvent` .</span><span class="sxs-lookup"><span data-stu-id="66da3-146">This variable is populated only within the `Action` block of an event registration command, such as `Register-ObjectEvent`.</span></span> <span data-ttu-id="66da3-147">O valor dessa variável é o mesmo objeto que o `Get-Event` cmdlet retorna.</span><span class="sxs-lookup"><span data-stu-id="66da3-147">The value of this variable is the same object that the `Get-Event` cmdlet returns.</span></span> <span data-ttu-id="66da3-148">Portanto, você pode usar as propriedades da `Event` variável, como `$Event.TimeGenerated` , em um bloco de `Action` script.</span><span class="sxs-lookup"><span data-stu-id="66da3-148">Therefore, you can use the properties of the `Event` variable, such as `$Event.TimeGenerated`, in an `Action` script block.</span></span>

### <a name="eventargs"></a><span data-ttu-id="66da3-149">$EventArgs</span><span class="sxs-lookup"><span data-stu-id="66da3-149">$EventArgs</span></span>

<span data-ttu-id="66da3-150">Contém um objeto que representa o primeiro argumento de evento que deriva de **EventArgs** do evento que está sendo processado.</span><span class="sxs-lookup"><span data-stu-id="66da3-150">Contains an object that represents the first event argument that derives from **EventArgs** of the event that is being processed.</span></span> <span data-ttu-id="66da3-151">Essa variável é populada somente dentro do `Action` bloco de um comando de registro de evento.</span><span class="sxs-lookup"><span data-stu-id="66da3-151">This variable is populated only within the `Action` block of an event registration command.</span></span>
<span data-ttu-id="66da3-152">O valor dessa variável também pode ser encontrado na propriedade **SourceEventArgs** do objeto **PSEventArgs** que `Get-Event` retorna.</span><span class="sxs-lookup"><span data-stu-id="66da3-152">The value of this variable can also be found in the **SourceEventArgs** property of the **PSEventArgs** object that `Get-Event` returns.</span></span>

### <a name="eventsubscriber"></a><span data-ttu-id="66da3-153">$EventSubscriber</span><span class="sxs-lookup"><span data-stu-id="66da3-153">$EventSubscriber</span></span>

<span data-ttu-id="66da3-154">Contém um objeto **PSEventSubscriber** que representa o Assinante de evento do evento que está sendo processado.</span><span class="sxs-lookup"><span data-stu-id="66da3-154">Contains a **PSEventSubscriber** object that represents the event subscriber of the event that is being processed.</span></span> <span data-ttu-id="66da3-155">Essa variável é populada somente dentro do `Action` bloco de um comando de registro de evento.</span><span class="sxs-lookup"><span data-stu-id="66da3-155">This variable is populated only within the `Action` block of an event registration command.</span></span> <span data-ttu-id="66da3-156">O valor dessa variável é o mesmo objeto que o `Get-EventSubscriber` cmdlet retorna.</span><span class="sxs-lookup"><span data-stu-id="66da3-156">The value of this variable is the same object that the `Get-EventSubscriber` cmdlet returns.</span></span>

### <a name="executioncontext"></a><span data-ttu-id="66da3-157">$ExecutionContext</span><span class="sxs-lookup"><span data-stu-id="66da3-157">$ExecutionContext</span></span>

<span data-ttu-id="66da3-158">Contém um objeto **EngineIntrinsics** que representa o contexto de execução do host do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="66da3-158">Contains an **EngineIntrinsics** object that represents the execution context of the PowerShell host.</span></span> <span data-ttu-id="66da3-159">Você pode usar essa variável para localizar os objetos de execução que estão disponíveis para os cmdlets.</span><span class="sxs-lookup"><span data-stu-id="66da3-159">You can use this variable to find the execution objects that are available to cmdlets.</span></span>

### <a name="false"></a><span data-ttu-id="66da3-160">$false</span><span class="sxs-lookup"><span data-stu-id="66da3-160">$false</span></span>

<span data-ttu-id="66da3-161">Contém **false** .</span><span class="sxs-lookup"><span data-stu-id="66da3-161">Contains **False** .</span></span> <span data-ttu-id="66da3-162">Você pode usar essa variável para representar **falso** em comandos e scripts em vez de usar a cadeia de caracteres "false".</span><span class="sxs-lookup"><span data-stu-id="66da3-162">You can use this variable to represent **False** in commands and scripts instead of using the string "false".</span></span> <span data-ttu-id="66da3-163">A cadeia de caracteres poderá ser interpretada como **true** se for convertida em uma cadeia de caracteres não vazia ou em um inteiro diferente de zero.</span><span class="sxs-lookup"><span data-stu-id="66da3-163">The string can be interpreted as **True** if it's converted to a non-empty string or to a non-zero integer.</span></span>

### <a name="foreach"></a><span data-ttu-id="66da3-164">$foreach</span><span class="sxs-lookup"><span data-stu-id="66da3-164">$foreach</span></span>

<span data-ttu-id="66da3-165">Contém o enumerador (não os valores resultantes) de um loop [foreach](about_ForEach.md) .</span><span class="sxs-lookup"><span data-stu-id="66da3-165">Contains the enumerator (not the resulting values) of a [ForEach](about_ForEach.md) loop.</span></span> <span data-ttu-id="66da3-166">A `$ForEach` variável existe somente enquanto o `ForEach` loop está em execução; ela é excluída após a conclusão do loop.</span><span class="sxs-lookup"><span data-stu-id="66da3-166">The `$ForEach` variable exists only while the `ForEach` loop is running; it's deleted after the loop is completed.</span></span>

<span data-ttu-id="66da3-167">Enumeradores contêm propriedades e métodos que você pode usar para recuperar valores de loop e alterar a iteração do loop atual.</span><span class="sxs-lookup"><span data-stu-id="66da3-167">Enumerators contain properties and methods you can use to retrieve loop values and change the current loop iteration.</span></span> <span data-ttu-id="66da3-168">Para obter mais informações, consulte [usando enumeradores](#using-enumerators).</span><span class="sxs-lookup"><span data-stu-id="66da3-168">For more information, see [Using Enumerators](#using-enumerators).</span></span>

### <a name="home"></a><span data-ttu-id="66da3-169">$HOME</span><span class="sxs-lookup"><span data-stu-id="66da3-169">$HOME</span></span>

<span data-ttu-id="66da3-170">Contém o caminho completo do diretório base do usuário.</span><span class="sxs-lookup"><span data-stu-id="66da3-170">Contains the full path of the user's home directory.</span></span> <span data-ttu-id="66da3-171">Essa variável é equivalente às variáveis de `"$env:homedrive$env:homepath"` ambiente do Windows, normalmente `C:\Users\<UserName>` .</span><span class="sxs-lookup"><span data-stu-id="66da3-171">This variable is the equivalent of the `"$env:homedrive$env:homepath"` Windows environment variables, typically `C:\Users\<UserName>`.</span></span>

### <a name="host"></a><span data-ttu-id="66da3-172">$Host</span><span class="sxs-lookup"><span data-stu-id="66da3-172">$Host</span></span>

<span data-ttu-id="66da3-173">Contém um objeto que representa o aplicativo host atual para o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="66da3-173">Contains an object that represents the current host application for PowerShell.</span></span> <span data-ttu-id="66da3-174">Você pode usar essa variável para representar o host atual em comandos ou para exibir ou alterar as propriedades do host, como `$Host.version` ou ou `$Host.CurrentCulture` `$host.ui.rawui.setbackgroundcolor("Red")` .</span><span class="sxs-lookup"><span data-stu-id="66da3-174">You can use this variable to represent the current host in commands or to display or change the properties of the host, such as `$Host.version` or `$Host.CurrentCulture`, or `$host.ui.rawui.setbackgroundcolor("Red")`.</span></span>

### <a name="input"></a><span data-ttu-id="66da3-175">$input</span><span class="sxs-lookup"><span data-stu-id="66da3-175">$input</span></span>

<span data-ttu-id="66da3-176">Contém um enumerador que enumera todas as entradas passadas para uma função.</span><span class="sxs-lookup"><span data-stu-id="66da3-176">Contains an enumerator that enumerates all input that is passed to a function.</span></span> <span data-ttu-id="66da3-177">A `$input` variável está disponível somente para funções e blocos de script (que são funções sem nome).</span><span class="sxs-lookup"><span data-stu-id="66da3-177">The `$input` variable is available only to functions and script blocks (which are unnamed functions).</span></span>

- <span data-ttu-id="66da3-178">Em uma função sem um `Begin` `Process` bloco, ou `End` , a `$input` variável enumera a coleção de todas as entradas para a função.</span><span class="sxs-lookup"><span data-stu-id="66da3-178">In a function without a `Begin`, `Process`, or `End` block, the `$input` variable enumerates the collection of all input to the function.</span></span>

- <span data-ttu-id="66da3-179">No `Begin` bloco, a `$input` variável não contém dados.</span><span class="sxs-lookup"><span data-stu-id="66da3-179">In the `Begin` block, the `$input` variable contains no data.</span></span>

- <span data-ttu-id="66da3-180">No `Process` bloco, a `$input` variável contém o objeto que está atualmente no pipeline.</span><span class="sxs-lookup"><span data-stu-id="66da3-180">In the `Process` block, the `$input` variable contains the object that is currently in the pipeline.</span></span>

- <span data-ttu-id="66da3-181">No `End` bloco, a `$input` variável enumera a coleção de todas as entradas para a função.</span><span class="sxs-lookup"><span data-stu-id="66da3-181">In the `End` block, the `$input` variable enumerates the collection of all input to the function.</span></span>

  > [!NOTE]
  > <span data-ttu-id="66da3-182">Não é possível usar a `$input` variável dentro do bloco Process e do bloco end na mesma função ou bloco de script.</span><span class="sxs-lookup"><span data-stu-id="66da3-182">You cannot use the `$input` variable inside both the Process block and the End block in the same function or script block.</span></span>

<span data-ttu-id="66da3-183">Como `$input` é um enumerador, o acesso a qualquer uma das suas propriedades faz com que `$input` não esteja mais disponível.</span><span class="sxs-lookup"><span data-stu-id="66da3-183">Since `$input` is an enumerator, accessing any of it's properties causes `$input` to no longer be available.</span></span> <span data-ttu-id="66da3-184">Você pode armazenar `$input` em outra variável para reutilizar as `$input` Propriedades.</span><span class="sxs-lookup"><span data-stu-id="66da3-184">You can store `$input` in another variable to reuse the `$input` properties.</span></span>

<span data-ttu-id="66da3-185">Enumeradores contêm propriedades e métodos que você pode usar para recuperar valores de loop e alterar a iteração do loop atual.</span><span class="sxs-lookup"><span data-stu-id="66da3-185">Enumerators contain properties and methods you can use to retrieve loop values and change the current loop iteration.</span></span> <span data-ttu-id="66da3-186">Para obter mais informações, consulte [usando enumeradores](#using-enumerators).</span><span class="sxs-lookup"><span data-stu-id="66da3-186">For more information, see [Using Enumerators](#using-enumerators).</span></span>

### <a name="iscoreclr"></a><span data-ttu-id="66da3-187">$IsCoreCLR</span><span class="sxs-lookup"><span data-stu-id="66da3-187">$IsCoreCLR</span></span>

<span data-ttu-id="66da3-188">Contém `$True` se a sessão atual está em execução no CoreCLR (tempo de execução do .NET Core).</span><span class="sxs-lookup"><span data-stu-id="66da3-188">Contains `$True` if the current session is running on the .NET Core Runtime (CoreCLR).</span></span> <span data-ttu-id="66da3-189">Caso contrário, contém `$False` .</span><span class="sxs-lookup"><span data-stu-id="66da3-189">Otherwise contains `$False`.</span></span>

### <a name="islinux"></a><span data-ttu-id="66da3-190">$IsLinux</span><span class="sxs-lookup"><span data-stu-id="66da3-190">$IsLinux</span></span>

<span data-ttu-id="66da3-191">Contém `$True` se a sessão atual está sendo executada em um sistema operacional Linux.</span><span class="sxs-lookup"><span data-stu-id="66da3-191">Contains `$True` if the current session is running on a Linux operating system.</span></span>
<span data-ttu-id="66da3-192">Caso contrário, contém `$False` .</span><span class="sxs-lookup"><span data-stu-id="66da3-192">Otherwise contains `$False`.</span></span>

### <a name="ismacos"></a><span data-ttu-id="66da3-193">$IsMacOS</span><span class="sxs-lookup"><span data-stu-id="66da3-193">$IsMacOS</span></span>

<span data-ttu-id="66da3-194">Contém `$True` se a sessão atual está sendo executada em um sistema operacional MacOS.</span><span class="sxs-lookup"><span data-stu-id="66da3-194">Contains `$True` if the current session is running on a MacOS operating system.</span></span>
<span data-ttu-id="66da3-195">Caso contrário, contém `$False` .</span><span class="sxs-lookup"><span data-stu-id="66da3-195">Otherwise contains `$False`.</span></span>

### <a name="iswindows"></a><span data-ttu-id="66da3-196">$IsWindows</span><span class="sxs-lookup"><span data-stu-id="66da3-196">$IsWindows</span></span>

<span data-ttu-id="66da3-197">Contém `$TRUE` se a sessão atual está sendo executada em um sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="66da3-197">Contains `$TRUE` if the current session is running on a Windows operating system.</span></span> <span data-ttu-id="66da3-198">Caso contrário, contém `$FALSE` .</span><span class="sxs-lookup"><span data-stu-id="66da3-198">Otherwise contains `$FALSE`.</span></span>

### <a name="lastexitcode"></a><span data-ttu-id="66da3-199">$LastExitCode</span><span class="sxs-lookup"><span data-stu-id="66da3-199">$LastExitCode</span></span>

<span data-ttu-id="66da3-200">Contém o código de saída do último programa baseado no Windows que foi executado.</span><span class="sxs-lookup"><span data-stu-id="66da3-200">Contains the exit code of the last Windows-based program that was run.</span></span>

### <a name="matches"></a><span data-ttu-id="66da3-201">$Matches</span><span class="sxs-lookup"><span data-stu-id="66da3-201">$Matches</span></span>

<span data-ttu-id="66da3-202">A `Matches` variável funciona com os `-match` `-notmatch` operadores e.</span><span class="sxs-lookup"><span data-stu-id="66da3-202">The `Matches` variable works with the `-match` and `-notmatch` operators.</span></span>
<span data-ttu-id="66da3-203">Quando você envia a entrada escalar para `-match` o `-notmatch` operador OR e qualquer uma detecta uma correspondência, elas retornam um valor booliano e preenchem a `$Matches` variável automática com uma tabela de hash de quaisquer valores de cadeia de caracteres que foram correspondidos.</span><span class="sxs-lookup"><span data-stu-id="66da3-203">When you submit scalar input to the `-match` or `-notmatch` operator, and either one detects a match, they return a Boolean value and populate the `$Matches` automatic variable with a hash table of any string values that were matched.</span></span> <span data-ttu-id="66da3-204">A `$Matches` tabela de hash também pode ser populada com capturas quando você usa expressões regulares com o `-match` operador.</span><span class="sxs-lookup"><span data-stu-id="66da3-204">The `$Matches` hash table can also be populated with captures when you use regular expressions with the `-match` operator.</span></span>

<span data-ttu-id="66da3-205">Para obter mais informações sobre o `-match` operador, consulte [about_Comparison_Operators](about_comparison_operators.md).</span><span class="sxs-lookup"><span data-stu-id="66da3-205">For more information about the `-match` operator, see [about_Comparison_Operators](about_comparison_operators.md).</span></span> <span data-ttu-id="66da3-206">Para obter mais informações sobre expressões regulares, consulte [about_Regular_Expressions](about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="66da3-206">For more information on regular expressions, see [about_Regular_Expressions](about_Regular_Expressions.md).</span></span>

### <a name="myinvocation"></a><span data-ttu-id="66da3-207">$MyInvocation</span><span class="sxs-lookup"><span data-stu-id="66da3-207">$MyInvocation</span></span>

<span data-ttu-id="66da3-208">Contém informações sobre o comando atual, como nome, parâmetros, valores de parâmetro e informações sobre como o comando foi iniciado, chamado ou invocado, como o nome do script que chamou o comando atual.</span><span class="sxs-lookup"><span data-stu-id="66da3-208">Contains information about the current command, such as the name, parameters, parameter values, and information about how the command was started, called, or invoked, such as the name of the script that called the current command.</span></span>

<span data-ttu-id="66da3-209">`$MyInvocation` é preenchido somente para scripts, funções e blocos de script.</span><span class="sxs-lookup"><span data-stu-id="66da3-209">`$MyInvocation` is populated only for scripts, function, and script blocks.</span></span> <span data-ttu-id="66da3-210">Você pode usar as informações no objeto **System. Management. Automation. InvocationInfo** que `$MyInvocation` retorna no script atual, como o caminho e o nome do arquivo do script ( `$MyInvocation.MyCommand.Path` ) ou o nome de uma função ( `$MyInvocation.MyCommand.Name` ) para identificar o comando atual.</span><span class="sxs-lookup"><span data-stu-id="66da3-210">You can use the information in the **System.Management.Automation.InvocationInfo** object that `$MyInvocation` returns in the current script, such as the path and file name of the script (`$MyInvocation.MyCommand.Path`) or the name of a function (`$MyInvocation.MyCommand.Name`) to identify the current command.</span></span> <span data-ttu-id="66da3-211">Isso é particularmente útil para localizar o nome do script atual.</span><span class="sxs-lookup"><span data-stu-id="66da3-211">This is particularly useful for finding the name of the current script.</span></span>

<span data-ttu-id="66da3-212">A partir do PowerShell 3,0, `MyInvocation` o tem as novas propriedades a seguir.</span><span class="sxs-lookup"><span data-stu-id="66da3-212">Beginning in PowerShell 3.0, `MyInvocation` has the following new properties.</span></span>

| <span data-ttu-id="66da3-213">Propriedade</span><span class="sxs-lookup"><span data-stu-id="66da3-213">Property</span></span>      | <span data-ttu-id="66da3-214">Descrição</span><span class="sxs-lookup"><span data-stu-id="66da3-214">Description</span></span>                                         |
| ------------- | --------------------------------------------------- |
| <span data-ttu-id="66da3-215">**PSScriptRoot**</span><span class="sxs-lookup"><span data-stu-id="66da3-215">**PSScriptRoot**</span></span>  | <span data-ttu-id="66da3-216">Contém o caminho completo para o script que foi invocado</span><span class="sxs-lookup"><span data-stu-id="66da3-216">Contains the full path to the script that invoked</span></span>   |
|               | <span data-ttu-id="66da3-217">o comando atual.</span><span class="sxs-lookup"><span data-stu-id="66da3-217">the current command.</span></span> <span data-ttu-id="66da3-218">O valor dessa propriedade é</span><span class="sxs-lookup"><span data-stu-id="66da3-218">The value of this property is</span></span>  |
|               | <span data-ttu-id="66da3-219">populado somente quando o chamador é um script.</span><span class="sxs-lookup"><span data-stu-id="66da3-219">populated only when the caller is a script.</span></span>         |
| <span data-ttu-id="66da3-220">**PSCommandPath**</span><span class="sxs-lookup"><span data-stu-id="66da3-220">**PSCommandPath**</span></span> | <span data-ttu-id="66da3-221">Contém o caminho completo e o nome do arquivo do script</span><span class="sxs-lookup"><span data-stu-id="66da3-221">Contains the full path and file name of the script</span></span>  |
|               | <span data-ttu-id="66da3-222">que invocou o comando atual.</span><span class="sxs-lookup"><span data-stu-id="66da3-222">that invoked the current command.</span></span> <span data-ttu-id="66da3-223">O valor deste</span><span class="sxs-lookup"><span data-stu-id="66da3-223">The value of this</span></span> |
|               | <span data-ttu-id="66da3-224">a propriedade é populada somente quando o chamador é um</span><span class="sxs-lookup"><span data-stu-id="66da3-224">property is populated only when the caller is a</span></span>     |
|               | <span data-ttu-id="66da3-225">.</span><span class="sxs-lookup"><span data-stu-id="66da3-225">script.</span></span>                                             |

<span data-ttu-id="66da3-226">Ao contrário `$PSScriptRoot` das `$PSCommandPath` variáveis e automáticas, as propriedades **PSScriptRoot** e **PSCommandPath** da `$MyInvocation` variável automática contêm informações sobre o chamador ou o script de chamada, não o script atual.</span><span class="sxs-lookup"><span data-stu-id="66da3-226">Unlike the `$PSScriptRoot` and `$PSCommandPath` automatic variables, the **PSScriptRoot** and **PSCommandPath** properties of the `$MyInvocation` automatic variable contain information about the invoker or calling script, not the current script.</span></span>

### <a name="nestedpromptlevel"></a><span data-ttu-id="66da3-227">$NestedPromptLevel</span><span class="sxs-lookup"><span data-stu-id="66da3-227">$NestedPromptLevel</span></span>

<span data-ttu-id="66da3-228">Contém o nível do prompt atual.</span><span class="sxs-lookup"><span data-stu-id="66da3-228">Contains the current prompt level.</span></span> <span data-ttu-id="66da3-229">Um valor de 0 indica o nível do prompt original.</span><span class="sxs-lookup"><span data-stu-id="66da3-229">A value of 0 indicates the original prompt level.</span></span> <span data-ttu-id="66da3-230">O valor é incrementado quando você insere um nível aninhado e diminui quando sai dele.</span><span class="sxs-lookup"><span data-stu-id="66da3-230">The value is incremented when you enter a nested level and decremented when you exit it.</span></span>

<span data-ttu-id="66da3-231">Por exemplo, o PowerShell apresenta um prompt de comando aninhado quando você usa o `$Host.EnterNestedPrompt` método.</span><span class="sxs-lookup"><span data-stu-id="66da3-231">For example, PowerShell presents a nested command prompt when you use the `$Host.EnterNestedPrompt` method.</span></span> <span data-ttu-id="66da3-232">O PowerShell também apresenta um prompt de comando aninhado quando você atinge um ponto de interrupção no depurador do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="66da3-232">PowerShell also presents a nested command prompt when you reach a breakpoint in the PowerShell debugger.</span></span>

<span data-ttu-id="66da3-233">Quando você insere um prompt aninhado, o PowerShell pausa o comando atual, salva o contexto de execução e incrementa o valor da `$NestedPromptLevel` variável.</span><span class="sxs-lookup"><span data-stu-id="66da3-233">When you enter a nested prompt, PowerShell pauses the current command, saves the execution context, and increments the value of the `$NestedPromptLevel` variable.</span></span> <span data-ttu-id="66da3-234">Para criar prompts de comando aninhados adicionais (até 128 níveis) ou retornar ao prompt de comando original, conclua o comando ou digite `exit` .</span><span class="sxs-lookup"><span data-stu-id="66da3-234">To create additional nested command prompts (up to 128 levels) or to return to the original command prompt, complete the command, or type `exit`.</span></span>

<span data-ttu-id="66da3-235">A `$NestedPromptLevel` variável ajuda a acompanhar o nível do prompt.</span><span class="sxs-lookup"><span data-stu-id="66da3-235">The `$NestedPromptLevel` variable helps you track the prompt level.</span></span> <span data-ttu-id="66da3-236">Você pode criar um prompt de comando alternativo do PowerShell que inclua esse valor para que ele fique sempre visível.</span><span class="sxs-lookup"><span data-stu-id="66da3-236">You can create an alternative PowerShell command prompt that includes this value so that it's always visible.</span></span>

### <a name="null"></a><span data-ttu-id="66da3-237">$null</span><span class="sxs-lookup"><span data-stu-id="66da3-237">$null</span></span>

<span data-ttu-id="66da3-238">`$null` é uma variável automática que contém um valor **nulo** ou vazio.</span><span class="sxs-lookup"><span data-stu-id="66da3-238">`$null` is an automatic variable that contains a **null** or empty value.</span></span> <span data-ttu-id="66da3-239">Você pode usar essa variável para representar um valor ausente ou indefinido em comandos e scripts.</span><span class="sxs-lookup"><span data-stu-id="66da3-239">You can use this variable to represent an absent or undefined value in commands and scripts.</span></span>

<span data-ttu-id="66da3-240">O PowerShell trata `$null` como um objeto com um valor, ou seja, como um espaço reservado explícito, para que você possa usar `$null` para representar um valor vazio em uma série de valores.</span><span class="sxs-lookup"><span data-stu-id="66da3-240">PowerShell treats `$null` as an object with a value, that is, as an explicit placeholder, so you can use `$null` to represent an empty value in a series of values.</span></span>

<span data-ttu-id="66da3-241">Por exemplo, quando `$null` é incluído em uma coleção, ele é contado como um dos objetos.</span><span class="sxs-lookup"><span data-stu-id="66da3-241">For example, when `$null` is included in a collection, it's counted as one of the objects.</span></span>

```powershell
$a = "one", $null, "three"
$a.count
```

```Output
3
```

<span data-ttu-id="66da3-242">Se você canalizar a `$null` variável para o `ForEach-Object` cmdlet, ele gerará um valor para `$null` , assim como faz para os outros objetos</span><span class="sxs-lookup"><span data-stu-id="66da3-242">If you pipe the `$null` variable to the `ForEach-Object` cmdlet, it generates a value for `$null`, just as it does for the other objects</span></span>

```powershell
"one", $null, "three" | ForEach-Object { "Hello " + $_}
```

```Output
Hello one
Hello
Hello three
```

<span data-ttu-id="66da3-243">Como resultado, você não pode usar `$null` para significar **nenhum valor de parâmetro** .</span><span class="sxs-lookup"><span data-stu-id="66da3-243">As a result, you can't use `$null` to mean **no parameter value** .</span></span> <span data-ttu-id="66da3-244">Um valor de parâmetro de `$null` substitui o valor de parâmetro padrão.</span><span class="sxs-lookup"><span data-stu-id="66da3-244">A parameter value of `$null` overrides the default parameter value.</span></span>

<span data-ttu-id="66da3-245">No entanto, como o PowerShell trata a `$null` variável como um espaço reservado, você pode usá-la em scripts como o seguinte, o que não funcionaria se `$null` fosse ignorado.</span><span class="sxs-lookup"><span data-stu-id="66da3-245">However, because PowerShell treats the `$null` variable as a placeholder, you can use it in scripts like the following one, which wouldn't work if `$null` were ignored.</span></span>

```powershell
$calendar = @($null, $null, "Meeting", $null, $null, "Team Lunch", $null)
$days = "Sunday","Monday","Tuesday","Wednesday","Thursday",
        "Friday","Saturday"
$currentDay = 0
foreach($day in $calendar)
{
    if($day -ne $null)
    {
        "Appointment on $($days[$currentDay]): $day"
    }

    $currentDay++
}
```

```Output
Appointment on Tuesday: Meeting
Appointment on Friday: Team lunch
```

### <a name="pid"></a><span data-ttu-id="66da3-246">$PID</span><span class="sxs-lookup"><span data-stu-id="66da3-246">$PID</span></span>

<span data-ttu-id="66da3-247">Contém o identificador do processo (PID) do processo que está hospedando a sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="66da3-247">Contains the process identifier (PID) of the process that is hosting the current PowerShell session.</span></span>

### <a name="profile"></a><span data-ttu-id="66da3-248">$PROFILE</span><span class="sxs-lookup"><span data-stu-id="66da3-248">$PROFILE</span></span>

<span data-ttu-id="66da3-249">Contém o caminho completo do perfil do PowerShell para o usuário atual e o aplicativo host atual.</span><span class="sxs-lookup"><span data-stu-id="66da3-249">Contains the full path of the PowerShell profile for the current user and the current host application.</span></span> <span data-ttu-id="66da3-250">Você pode usar essa variável para representar o perfil em comandos.</span><span class="sxs-lookup"><span data-stu-id="66da3-250">You can use this variable to represent the profile in commands.</span></span> <span data-ttu-id="66da3-251">Por exemplo, você pode usá-lo em um comando para determinar se um perfil foi criado:</span><span class="sxs-lookup"><span data-stu-id="66da3-251">For example, you can use it in a command to determine whether a profile has been created:</span></span>

```powershell
Test-Path $PROFILE
```

<span data-ttu-id="66da3-252">Ou você pode usá-lo em um comando para criar um perfil:</span><span class="sxs-lookup"><span data-stu-id="66da3-252">Or, you can use it in a command to create a profile:</span></span>

```powershell
New-Item -ItemType file -Path $PROFILE -Force
```

<span data-ttu-id="66da3-253">Você pode usá-lo em um comando para abrir o perfil no **notepad.exe** :</span><span class="sxs-lookup"><span data-stu-id="66da3-253">You can use it in a command to open the profile in **notepad.exe** :</span></span>

```powershell
notepad.exe $PROFILE
```

### <a name="psboundparameters"></a><span data-ttu-id="66da3-254">$PSBoundParameters</span><span class="sxs-lookup"><span data-stu-id="66da3-254">$PSBoundParameters</span></span>

<span data-ttu-id="66da3-255">Contém um dicionário dos parâmetros que são passados para um script ou função e seus valores atuais.</span><span class="sxs-lookup"><span data-stu-id="66da3-255">Contains a dictionary of the parameters that are passed to a script or function and their current values.</span></span> <span data-ttu-id="66da3-256">Essa variável tem um valor somente em um escopo em que os parâmetros são declarados, como um script ou uma função.</span><span class="sxs-lookup"><span data-stu-id="66da3-256">This variable has a value only in a scope where parameters are declared, such as a script or function.</span></span> <span data-ttu-id="66da3-257">Você pode usá-lo para exibir ou alterar os valores atuais dos parâmetros ou para passar valores de parâmetro para outro script ou função.</span><span class="sxs-lookup"><span data-stu-id="66da3-257">You can use it to display or change the current values of parameters or to pass parameter values to another script or function.</span></span>

<span data-ttu-id="66da3-258">Neste exemplo, a função **test2** passa o `$PSBoundParameters` para a função **Test1** .</span><span class="sxs-lookup"><span data-stu-id="66da3-258">In this example, the **Test2** function passes the `$PSBoundParameters` to the **Test1** function.</span></span> <span data-ttu-id="66da3-259">Os `$PSBoundParameters` são exibidos no formato de **chave** e **valor** .</span><span class="sxs-lookup"><span data-stu-id="66da3-259">The `$PSBoundParameters` are displayed in the format of **Key** and **Value** .</span></span>

```powershell
function Test1 {
   param($a, $b)

   # Display the parameters in dictionary format.
   $PSBoundParameters
}

function Test2 {
   param($a, $b)

   # Run the Test1 function with $a and $b.
   Test1 @PSBoundParameters
}
```

```powershell
Test2 -a Power -b Shell
```

```Output
Key   Value
---   -----
a     Power
b     Shell
```

### <a name="pscmdlet"></a><span data-ttu-id="66da3-260">$PSCmdlet</span><span class="sxs-lookup"><span data-stu-id="66da3-260">$PSCmdlet</span></span>

<span data-ttu-id="66da3-261">Contém um objeto que representa o cmdlet ou a função avançada que está sendo executada.</span><span class="sxs-lookup"><span data-stu-id="66da3-261">Contains an object that represents the cmdlet or advanced function that's being run.</span></span>

<span data-ttu-id="66da3-262">Você pode usar as propriedades e os métodos do objeto no seu cmdlet ou código de função para responder às condições de uso.</span><span class="sxs-lookup"><span data-stu-id="66da3-262">You can use the properties and methods of the object in your cmdlet or function code to respond to the conditions of use.</span></span> <span data-ttu-id="66da3-263">Por exemplo, a propriedade **ParameterSetName** contém o nome do conjunto de parâmetros que está sendo usado, e o método **ShouldProcess** adiciona os parâmetros **WhatIf** e **Confirm** ao cmdlet dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="66da3-263">For example, the **ParameterSetName** property contains the name of the parameter set that's being used, and the **ShouldProcess** method adds the **WhatIf** and **Confirm** parameters to the cmdlet dynamically.</span></span>

<span data-ttu-id="66da3-264">Para obter mais informações sobre a `$PSCmdlet` variável automática, consulte [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md) e [about_Functions_Advanced](about_Functions_Advanced.md).</span><span class="sxs-lookup"><span data-stu-id="66da3-264">For more information about the `$PSCmdlet` automatic variable, see [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md) and [about_Functions_Advanced](about_Functions_Advanced.md).</span></span>

### <a name="pscommandpath"></a><span data-ttu-id="66da3-265">$PSCommandPath</span><span class="sxs-lookup"><span data-stu-id="66da3-265">$PSCommandPath</span></span>

<span data-ttu-id="66da3-266">Contém o caminho completo e o nome de arquivo do script que está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="66da3-266">Contains the full path and file name of the script that's being run.</span></span> <span data-ttu-id="66da3-267">Essa variável é válida em todos os scripts.</span><span class="sxs-lookup"><span data-stu-id="66da3-267">This variable is valid in all scripts.</span></span>

### <a name="psculture"></a><span data-ttu-id="66da3-268">$PSCulture</span><span class="sxs-lookup"><span data-stu-id="66da3-268">$PSCulture</span></span>

<span data-ttu-id="66da3-269">A partir do PowerShell 7, `$PSCulture` reflete a cultura do runspace do PowerShell atual (sessão).</span><span class="sxs-lookup"><span data-stu-id="66da3-269">Beginning in PowerShell 7, `$PSCulture` reflects the culture of the current PowerShell runspace (session).</span></span> <span data-ttu-id="66da3-270">Se a cultura for alterada em um runspace do PowerShell, o `$PSCulture` valor desse runspace será atualizado.</span><span class="sxs-lookup"><span data-stu-id="66da3-270">If the culture is changed in a PowerShell runspace, the `$PSCulture` value for that runspace is updated.</span></span>

<span data-ttu-id="66da3-271">A cultura determina o formato de exibição de itens, como números, moeda e datas, e é armazenado em um objeto **System. Globalization. CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="66da3-271">The culture determines the display format of items such as numbers, currency, and dates, and is stored in a **System.Globalization.CultureInfo** object.</span></span> <span data-ttu-id="66da3-272">Use `Get-Culture` para exibir a cultura do computador.</span><span class="sxs-lookup"><span data-stu-id="66da3-272">Use `Get-Culture` to display the computer's culture.</span></span> <span data-ttu-id="66da3-273">`$PSCulture` contém o valor da propriedade de **nome** .</span><span class="sxs-lookup"><span data-stu-id="66da3-273">`$PSCulture` contains the **Name** property's value.</span></span>

### <a name="psdebugcontext"></a><span data-ttu-id="66da3-274">$PSDebugContext</span><span class="sxs-lookup"><span data-stu-id="66da3-274">$PSDebugContext</span></span>

<span data-ttu-id="66da3-275">Durante a depuração, essa variável contém informações sobre o ambiente de depuração.</span><span class="sxs-lookup"><span data-stu-id="66da3-275">While debugging, this variable contains information about the debugging environment.</span></span> <span data-ttu-id="66da3-276">Caso contrário, ele contém um valor **nulo** .</span><span class="sxs-lookup"><span data-stu-id="66da3-276">Otherwise, it contains a **null** value.</span></span> <span data-ttu-id="66da3-277">Como resultado, você pode usá-lo para indicar se o depurador tem controle.</span><span class="sxs-lookup"><span data-stu-id="66da3-277">As a result, you can use it to indicate whether the debugger has control.</span></span> <span data-ttu-id="66da3-278">Quando preenchido, ele contém um objeto **PSDebugContext** que tem **pontos de interrupção** e propriedades **InvocationInfo** .</span><span class="sxs-lookup"><span data-stu-id="66da3-278">When populated, it contains a **PsDebugContext** object that has **Breakpoints** and **InvocationInfo** properties.</span></span> <span data-ttu-id="66da3-279">A propriedade **InvocationInfo** tem várias propriedades úteis, incluindo a propriedade **Location** .</span><span class="sxs-lookup"><span data-stu-id="66da3-279">The **InvocationInfo** property has several useful properties, including the **Location** property.</span></span> <span data-ttu-id="66da3-280">A propriedade **Location** indica o caminho do script que está sendo depurado.</span><span class="sxs-lookup"><span data-stu-id="66da3-280">The **Location** property indicates the path of the script that is being debugged.</span></span>

### <a name="pshome"></a><span data-ttu-id="66da3-281">$PSHOME</span><span class="sxs-lookup"><span data-stu-id="66da3-281">$PSHOME</span></span>

<span data-ttu-id="66da3-282">Contém o caminho completo do diretório de instalação do PowerShell, normalmente, `$env:windir\System32\PowerShell\v1.0` em sistemas Windows.</span><span class="sxs-lookup"><span data-stu-id="66da3-282">Contains the full path of the installation directory for PowerShell, typically, `$env:windir\System32\PowerShell\v1.0` in Windows systems.</span></span> <span data-ttu-id="66da3-283">Você pode usar essa variável nos caminhos de arquivos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="66da3-283">You can use this variable in the paths of PowerShell files.</span></span> <span data-ttu-id="66da3-284">Por exemplo, o comando a seguir pesquisa os tópicos de ajuda conceitual para a **variável** de palavra:</span><span class="sxs-lookup"><span data-stu-id="66da3-284">For example, the following command searches the conceptual Help topics for the word **variable** :</span></span>

```powershell
Select-String -Pattern Variable -Path $pshome\*.txt
```

### <a name="psitem"></a><span data-ttu-id="66da3-285">$PSItem</span><span class="sxs-lookup"><span data-stu-id="66da3-285">$PSItem</span></span>

<span data-ttu-id="66da3-286">Mesmo que `$_`.</span><span class="sxs-lookup"><span data-stu-id="66da3-286">Same as `$_`.</span></span> <span data-ttu-id="66da3-287">Contém o objeto atual no objeto de pipeline.</span><span class="sxs-lookup"><span data-stu-id="66da3-287">Contains the current object in the pipeline object.</span></span> <span data-ttu-id="66da3-288">Você pode usar essa variável em comandos que executam uma ação em cada objeto ou em objetos selecionados em um pipeline.</span><span class="sxs-lookup"><span data-stu-id="66da3-288">You can use this variable in commands that perform an action on every object or on selected objects in a pipeline.</span></span>

### <a name="psscriptroot"></a><span data-ttu-id="66da3-289">$PSScriptRoot</span><span class="sxs-lookup"><span data-stu-id="66da3-289">$PSScriptRoot</span></span>

<span data-ttu-id="66da3-290">Contém o diretório do qual um script está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="66da3-290">Contains the directory from which a script is being run.</span></span>

<span data-ttu-id="66da3-291">No PowerShell 2,0, essa variável é válida somente em módulos de script ( `.psm1` ).</span><span class="sxs-lookup"><span data-stu-id="66da3-291">In PowerShell 2.0, this variable is valid only in script modules (`.psm1`).</span></span>
<span data-ttu-id="66da3-292">A partir do PowerShell 3,0, ele é válido em todos os scripts.</span><span class="sxs-lookup"><span data-stu-id="66da3-292">Beginning in PowerShell 3.0, it's valid in all scripts.</span></span>

### <a name="pssenderinfo"></a><span data-ttu-id="66da3-293">$PSSenderInfo</span><span class="sxs-lookup"><span data-stu-id="66da3-293">$PSSenderInfo</span></span>

<span data-ttu-id="66da3-294">Contém informações sobre o usuário que iniciou a PSSession, incluindo a identidade do usuário e o fuso horário do computador de origem.</span><span class="sxs-lookup"><span data-stu-id="66da3-294">Contains information about the user who started the PSSession, including the user identity and the time zone of the originating computer.</span></span> <span data-ttu-id="66da3-295">Essa variável está disponível somente em PSSessions.</span><span class="sxs-lookup"><span data-stu-id="66da3-295">This variable is available only in PSSessions.</span></span>

<span data-ttu-id="66da3-296">A `$PSSenderInfo` variável inclui uma propriedade configurável pelo usuário, **ApplicationArguments** , que, por padrão, contém apenas o `$PSVersionTable` da sessão de origem.</span><span class="sxs-lookup"><span data-stu-id="66da3-296">The `$PSSenderInfo` variable includes a user-configurable property, **ApplicationArguments** , that by default, contains only the `$PSVersionTable` from the originating session.</span></span> <span data-ttu-id="66da3-297">Para adicionar dados à propriedade **ApplicationArguments** , use o parâmetro **ApplicationArguments** do `New-PSSessionOption` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="66da3-297">To add data to the **ApplicationArguments** property, use the **ApplicationArguments** parameter of the `New-PSSessionOption` cmdlet.</span></span>

### <a name="psuiculture"></a><span data-ttu-id="66da3-298">$PSUICulture</span><span class="sxs-lookup"><span data-stu-id="66da3-298">$PSUICulture</span></span>

<span data-ttu-id="66da3-299">Contém o nome da cultura da interface do usuário que está atualmente em uso no sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="66da3-299">Contains the name of the user interface (UI) culture that's currently in use in the operating system.</span></span> <span data-ttu-id="66da3-300">A cultura da interface do usuário determina quais cadeias de caracteres de texto são usadas para elementos de interface do usuário, como menus e mensagens.</span><span class="sxs-lookup"><span data-stu-id="66da3-300">The UI culture determines which text strings are used for user interface elements, such as menus and messages.</span></span> <span data-ttu-id="66da3-301">Esse é o valor da propriedade **System.Globalization.CultureInfo.CurrentUICulture.Name** do sistema.</span><span class="sxs-lookup"><span data-stu-id="66da3-301">This is the value of the **System.Globalization.CultureInfo.CurrentUICulture.Name** property of the system.</span></span> <span data-ttu-id="66da3-302">Para obter o objeto **System. Globalization. CultureInfo** do sistema, use o `Get-UICulture` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="66da3-302">To get the **System.Globalization.CultureInfo** object for the system, use the `Get-UICulture` cmdlet.</span></span>

### <a name="psversiontable"></a><span data-ttu-id="66da3-303">$PSVersionTable</span><span class="sxs-lookup"><span data-stu-id="66da3-303">$PSVersionTable</span></span>

<span data-ttu-id="66da3-304">Contém uma tabela de hash somente leitura que exibe detalhes sobre a versão do PowerShell que está sendo executada na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="66da3-304">Contains a read-only hash table that displays details about the version of PowerShell that is running in the current session.</span></span> <span data-ttu-id="66da3-305">A tabela inclui os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="66da3-305">The table includes the following items:</span></span>

| <span data-ttu-id="66da3-306">Propriedade</span><span class="sxs-lookup"><span data-stu-id="66da3-306">Property</span></span>                  | <span data-ttu-id="66da3-307">Descrição</span><span class="sxs-lookup"><span data-stu-id="66da3-307">Description</span></span>                                   |
| ------------------------- | --------------------------------------------- |
| <span data-ttu-id="66da3-308">**PSVersion**</span><span class="sxs-lookup"><span data-stu-id="66da3-308">**PSVersion**</span></span>             | <span data-ttu-id="66da3-309">O número de versão do PowerShell</span><span class="sxs-lookup"><span data-stu-id="66da3-309">The PowerShell version number</span></span>                 |
| <span data-ttu-id="66da3-310">**PSEdition**</span><span class="sxs-lookup"><span data-stu-id="66da3-310">**PSEdition**</span></span>             | <span data-ttu-id="66da3-311">Esta propriedade tem o valor de ' Desktop ' para</span><span class="sxs-lookup"><span data-stu-id="66da3-311">This property has the value of 'Desktop' for</span></span>  |
|                           | <span data-ttu-id="66da3-312">PowerShell 4 e inferior, bem como o PowerShell</span><span class="sxs-lookup"><span data-stu-id="66da3-312">PowerShell 4 and below as well as PowerShell</span></span>  |
|                           | <span data-ttu-id="66da3-313">5,1 em edições com recursos completos do Windows.</span><span class="sxs-lookup"><span data-stu-id="66da3-313">5.1 on full-featured Windows editions.</span></span>        |
|                           | <span data-ttu-id="66da3-314">Esta propriedade tem o valor de ' Core ' para</span><span class="sxs-lookup"><span data-stu-id="66da3-314">This property has the value of 'Core' for</span></span>     |
|                           | <span data-ttu-id="66da3-315">PowerShell 6 e superior, bem como o PowerShell</span><span class="sxs-lookup"><span data-stu-id="66da3-315">PowerShell 6 and above as well as PowerShell</span></span>  |
|                           | <span data-ttu-id="66da3-316">PowerShell 5,1 em edições de superfície reduzida</span><span class="sxs-lookup"><span data-stu-id="66da3-316">PowerShell 5.1 on reduced-footprint editions</span></span>  |
|                           | <span data-ttu-id="66da3-317">como o Windows nano Server ou o Windows IoT.</span><span class="sxs-lookup"><span data-stu-id="66da3-317">like Windows Nano Server or Windows IoT.</span></span>      |
| <span data-ttu-id="66da3-318">**GitCommitId**</span><span class="sxs-lookup"><span data-stu-id="66da3-318">**GitCommitId**</span></span>           | <span data-ttu-id="66da3-319">A ID de confirmação dos arquivos de origem, no GitHub,</span><span class="sxs-lookup"><span data-stu-id="66da3-319">The commit Id of the source files, in GitHub,</span></span> |
| <span data-ttu-id="66da3-320">**SO**</span><span class="sxs-lookup"><span data-stu-id="66da3-320">**OS**</span></span>                    | <span data-ttu-id="66da3-321">Descrição do sistema operacional que</span><span class="sxs-lookup"><span data-stu-id="66da3-321">Description of the operating system that</span></span>      |
|                           | <span data-ttu-id="66da3-322">O PowerShell está sendo executado no.</span><span class="sxs-lookup"><span data-stu-id="66da3-322">PowerShell is running on.</span></span>                     |
| <span data-ttu-id="66da3-323">**Plataforma**</span><span class="sxs-lookup"><span data-stu-id="66da3-323">**Platform**</span></span>              | <span data-ttu-id="66da3-324">Plataforma em que o sistema operacional está em execução</span><span class="sxs-lookup"><span data-stu-id="66da3-324">Platform that the operating system is running</span></span> |
|                           | <span data-ttu-id="66da3-325">em.</span><span class="sxs-lookup"><span data-stu-id="66da3-325">on.</span></span> <span data-ttu-id="66da3-326">O valor no Linux e no macOS é **Unix** .</span><span class="sxs-lookup"><span data-stu-id="66da3-326">The value on Linux and macOS is **Unix** .</span></span> |
|                           | <span data-ttu-id="66da3-327">Veja `$IsMacOs` e `$IsLinux`.</span><span class="sxs-lookup"><span data-stu-id="66da3-327">See `$IsMacOs` and `$IsLinux`.</span></span>                |
| <span data-ttu-id="66da3-328">**PSCompatibleVersions**</span><span class="sxs-lookup"><span data-stu-id="66da3-328">**PSCompatibleVersions**</span></span>  | <span data-ttu-id="66da3-329">Versões do PowerShell que são compatíveis</span><span class="sxs-lookup"><span data-stu-id="66da3-329">Versions of PowerShell that are compatible</span></span>    |
|                           | <span data-ttu-id="66da3-330">com a versão atual</span><span class="sxs-lookup"><span data-stu-id="66da3-330">with the current version</span></span>                      |
| <span data-ttu-id="66da3-331">**PSRemotingProtocolVersion**</span><span class="sxs-lookup"><span data-stu-id="66da3-331">**PSRemotingProtocolVersion**</span></span> | <span data-ttu-id="66da3-332">A versão do PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="66da3-332">The version of the PowerShell remote</span></span>      |
|                           | <span data-ttu-id="66da3-333">Protocolo de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="66da3-333">management protocol.</span></span>                          |
| <span data-ttu-id="66da3-334">**SerializationVersion**</span><span class="sxs-lookup"><span data-stu-id="66da3-334">**SerializationVersion**</span></span>  | <span data-ttu-id="66da3-335">A versão do método de serialização</span><span class="sxs-lookup"><span data-stu-id="66da3-335">The version of the serialization method</span></span>       |
| <span data-ttu-id="66da3-336">**WSManStackVersion**</span><span class="sxs-lookup"><span data-stu-id="66da3-336">**WSManStackVersion**</span></span>     | <span data-ttu-id="66da3-337">O número de versão da pilha de WS-Management</span><span class="sxs-lookup"><span data-stu-id="66da3-337">The version number of the WS-Management stack</span></span> |

### <a name="pwd"></a><span data-ttu-id="66da3-338">$PWD</span><span class="sxs-lookup"><span data-stu-id="66da3-338">$PWD</span></span>

<span data-ttu-id="66da3-339">Contém um objeto Path que representa o caminho completo do diretório atual.</span><span class="sxs-lookup"><span data-stu-id="66da3-339">Contains a path object that represents the full path of the current directory.</span></span>

### <a name="sender"></a><span data-ttu-id="66da3-340">$Sender</span><span class="sxs-lookup"><span data-stu-id="66da3-340">$Sender</span></span>

<span data-ttu-id="66da3-341">Contém o objeto que gerou este evento.</span><span class="sxs-lookup"><span data-stu-id="66da3-341">Contains the object that generated this event.</span></span> <span data-ttu-id="66da3-342">Essa variável é populada somente dentro do bloco de ação de um comando de registro de evento.</span><span class="sxs-lookup"><span data-stu-id="66da3-342">This variable is populated only within the Action block of an event registration command.</span></span> <span data-ttu-id="66da3-343">O valor dessa variável também pode ser encontrado na propriedade Sender do objeto **PSEventArgs** que `Get-Event` retorna.</span><span class="sxs-lookup"><span data-stu-id="66da3-343">The value of this variable can also be found in the Sender property of the **PSEventArgs** object that `Get-Event` returns.</span></span>

### <a name="shellid"></a><span data-ttu-id="66da3-344">$ShellId</span><span class="sxs-lookup"><span data-stu-id="66da3-344">$ShellId</span></span>

<span data-ttu-id="66da3-345">Contém o identificador do shell atual.</span><span class="sxs-lookup"><span data-stu-id="66da3-345">Contains the identifier of the current shell.</span></span>

### <a name="stacktrace"></a><span data-ttu-id="66da3-346">$StackTrace</span><span class="sxs-lookup"><span data-stu-id="66da3-346">$StackTrace</span></span>

<span data-ttu-id="66da3-347">Contém um rastreamento de pilha para o erro mais recente.</span><span class="sxs-lookup"><span data-stu-id="66da3-347">Contains a stack trace for the most recent error.</span></span>

### <a name="switch"></a><span data-ttu-id="66da3-348">$switch</span><span class="sxs-lookup"><span data-stu-id="66da3-348">$switch</span></span>

<span data-ttu-id="66da3-349">Contém o enumerador não os valores resultantes de uma `Switch` instrução.</span><span class="sxs-lookup"><span data-stu-id="66da3-349">Contains the enumerator not the resulting values of a `Switch` statement.</span></span> <span data-ttu-id="66da3-350">A `$switch` variável existe somente enquanto a `Switch` instrução está em execução; ela é excluída quando a `switch` instrução conclui a execução.</span><span class="sxs-lookup"><span data-stu-id="66da3-350">The `$switch` variable exists only while the `Switch` statement is running; it's deleted when the `switch` statement completes execution.</span></span> <span data-ttu-id="66da3-351">Para obter mais informações, consulte [about_Switch](about_Switch.md).</span><span class="sxs-lookup"><span data-stu-id="66da3-351">For more information, see [about_Switch](about_Switch.md).</span></span>

<span data-ttu-id="66da3-352">Enumeradores contêm propriedades e métodos que você pode usar para recuperar valores de loop e alterar a iteração do loop atual.</span><span class="sxs-lookup"><span data-stu-id="66da3-352">Enumerators contain properties and methods you can use to retrieve loop values and change the current loop iteration.</span></span> <span data-ttu-id="66da3-353">Para obter mais informações, consulte [usando enumeradores](#using-enumerators).</span><span class="sxs-lookup"><span data-stu-id="66da3-353">For more information, see [Using Enumerators](#using-enumerators).</span></span>

### <a name="this"></a><span data-ttu-id="66da3-354">$this</span><span class="sxs-lookup"><span data-stu-id="66da3-354">$this</span></span>

<span data-ttu-id="66da3-355">Em um bloco de script que define uma propriedade de script ou um método de script, a `$this` variável refere-se ao objeto que está sendo estendido.</span><span class="sxs-lookup"><span data-stu-id="66da3-355">In a script block that defines a script property or script method, the `$this` variable refers to the object that is being extended.</span></span>

<span data-ttu-id="66da3-356">Em uma classe personalizada, a `$this` variável refere-se ao próprio objeto de classe, permitindo o acesso a propriedades e métodos definidos na classe.</span><span class="sxs-lookup"><span data-stu-id="66da3-356">In a custom class, the `$this` variable refers to the class object itself allowing access to properties and methods defined in the class.</span></span>

### <a name="true"></a><span data-ttu-id="66da3-357">$true</span><span class="sxs-lookup"><span data-stu-id="66da3-357">$true</span></span>

<span data-ttu-id="66da3-358">Contém **true** .</span><span class="sxs-lookup"><span data-stu-id="66da3-358">Contains **True** .</span></span> <span data-ttu-id="66da3-359">Você pode usar essa variável para representar **true** em comandos e scripts.</span><span class="sxs-lookup"><span data-stu-id="66da3-359">You can use this variable to represent **True** in commands and scripts.</span></span>

## <a name="using-enumerators"></a><span data-ttu-id="66da3-360">Usando enumeradores</span><span class="sxs-lookup"><span data-stu-id="66da3-360">Using Enumerators</span></span>

<span data-ttu-id="66da3-361">As `$input` `$foreach` variáveis, e `$switch` são todos os enumeradores usados para iterar pelos valores processados pelo bloco de código que o contém.</span><span class="sxs-lookup"><span data-stu-id="66da3-361">The `$input`, `$foreach`, and `$switch` variables are all enumerators used to iterate through the values processed by their containing code block.</span></span>

<span data-ttu-id="66da3-362">Um enumerador contém propriedades e métodos que você pode usar para avançar ou redefinir a iteração ou recuperar valores de iteração.</span><span class="sxs-lookup"><span data-stu-id="66da3-362">An enumerator contains properties and methods you can use to advance or reset iteration, or retrieve iteration values.</span></span> <span data-ttu-id="66da3-363">Os enumeradores de manipulação direta não são considerados práticas recomendadas.</span><span class="sxs-lookup"><span data-stu-id="66da3-363">Directly manipulating enumerators isn't considered best practice.</span></span>

- <span data-ttu-id="66da3-364">Em loops, as palavras-chave de controle de fluxo [quebram](about_Break.md) e [continuam](about_Continue.md) como preferíveis.</span><span class="sxs-lookup"><span data-stu-id="66da3-364">Within loops, flow control keywords [break](about_Break.md) and [continue](about_Continue.md) should be preferred.</span></span>
- <span data-ttu-id="66da3-365">Em funções que aceitam a entrada de pipeline, é recomendável usar parâmetros com os atributos **ValueFromPipeline** ou **valueFromPipelineByPropertyName** .</span><span class="sxs-lookup"><span data-stu-id="66da3-365">Within functions that accept pipeline input, it's best practice to use Parameters with the **ValueFromPipeline** or **ValueFromPipelineByPropertyName** attributes.</span></span>

  <span data-ttu-id="66da3-366">Para obter mais informações, consulte [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="66da3-366">For more information, see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

### <a name="movenext"></a><span data-ttu-id="66da3-367">MoveNext</span><span class="sxs-lookup"><span data-stu-id="66da3-367">MoveNext</span></span>

<span data-ttu-id="66da3-368">O método [MoveNext](/dotnet/api/system.collections.ienumerator.movenext) avança o enumerador para o próximo elemento da coleção.</span><span class="sxs-lookup"><span data-stu-id="66da3-368">The [MoveNext](/dotnet/api/system.collections.ienumerator.movenext) method advances the enumerator to the next element of the collection.</span></span> <span data-ttu-id="66da3-369">**MoveNext** retornará **true** se o enumerador tiver sido avançado com êxito; **false** se o enumerador tiver passado o final da coleção.</span><span class="sxs-lookup"><span data-stu-id="66da3-369">**MoveNext** returns **True** if the enumerator was successfully advanced, **False** if the enumerator has passed the end of the collection.</span></span>

> [!NOTE]
> <span data-ttu-id="66da3-370">O valor **booliano** retornou meu **MoveNext** é enviado para o fluxo de saída.</span><span class="sxs-lookup"><span data-stu-id="66da3-370">The **Boolean** value returned my **MoveNext** is sent to the output stream.</span></span>
> <span data-ttu-id="66da3-371">Você pode suprimir a saída ao typecasting-la `[void]` ou canaliza-la para [out-null](xref:Microsoft.PowerShell.Core.Out-Null).</span><span class="sxs-lookup"><span data-stu-id="66da3-371">You can suppress the output by typecasting it to `[void]` or piping it to [Out-Null](xref:Microsoft.PowerShell.Core.Out-Null).</span></span>
>
> ```powershell
> $input.MoveNext() | Out-Null
> ```
>
> ```powershell
> [void]$input.MoveNext()
> ```

### <a name="reset"></a><span data-ttu-id="66da3-372">Redefinir</span><span class="sxs-lookup"><span data-stu-id="66da3-372">Reset</span></span>

<span data-ttu-id="66da3-373">O método [Reset](/dotnet/api/system.collections.ienumerator.reset) define o enumerador para sua posição inicial, que é **antes** do primeiro elemento na coleção.</span><span class="sxs-lookup"><span data-stu-id="66da3-373">The [Reset](/dotnet/api/system.collections.ienumerator.reset) method sets the enumerator to its initial position, which is **before** the first element in the collection.</span></span>

### <a name="current"></a><span data-ttu-id="66da3-374">Current</span><span class="sxs-lookup"><span data-stu-id="66da3-374">Current</span></span>

<span data-ttu-id="66da3-375">A propriedade [Current](/dotnet/api/system.collections.ienumerator.current) Obtém o elemento na coleção, ou pipeline, na posição atual do enumerador.</span><span class="sxs-lookup"><span data-stu-id="66da3-375">The [Current](/dotnet/api/system.collections.ienumerator.current) property gets the element in the collection, or pipeline, at the current position of the enumerator.</span></span>

<span data-ttu-id="66da3-376">A propriedade **Current** continua retornando a mesma propriedade até que **MoveNext** seja chamado.</span><span class="sxs-lookup"><span data-stu-id="66da3-376">The **Current** property continues to return the same property until **MoveNext** is called.</span></span>

## <a name="examples"></a><span data-ttu-id="66da3-377">Exemplos</span><span class="sxs-lookup"><span data-stu-id="66da3-377">Examples</span></span>

### <a name="example-1-using-the-input-variable"></a><span data-ttu-id="66da3-378">Exemplo 1: usando a variável $input</span><span class="sxs-lookup"><span data-stu-id="66da3-378">Example 1: Using the $input variable</span></span>

<span data-ttu-id="66da3-379">No exemplo a seguir, o acesso à `$input` variável limpa a variável até a próxima vez que o bloco de processo for executado.</span><span class="sxs-lookup"><span data-stu-id="66da3-379">In the following example, accessing the `$input` variable clears the variable until the next time the process block executes.</span></span> <span data-ttu-id="66da3-380">O uso do método **Redefinir** redefine a `$input` variável para o valor do pipeline atual.</span><span class="sxs-lookup"><span data-stu-id="66da3-380">Using the **Reset** method resets the `$input` variable to the current pipeline value.</span></span>

```powershell
function Test
{
    begin
    {
        $i = 0
    }

    process
    {
        "Iteration: $i"
        $i++
        "`tInput: $input"
        "`tAccess Again: $input"
        $input.Reset()
        "`tAfter Reset: $input"
    }
}

"one","two" | Test
```

```Output
Iteration: 0
    Input: one
    Access Again:
    After Reset: one
Iteration: 1
    Input: two
    Access Again:
    After Reset: two
```

<span data-ttu-id="66da3-381">O bloco de processo avança automaticamente a `$input` variável mesmo se você não acessá-la.</span><span class="sxs-lookup"><span data-stu-id="66da3-381">The process block automatically advances the `$input` variable even if you don't access it.</span></span>

```powershell
$skip = $true
function Skip
{
    begin
    {
        $i = 0
    }

    process
    {
        "Iteration: $i"
        $i++
        if ($skip)
        {
            "`tSkipping"
            $skip = $false
        }
        else
        {
            "`tInput: $input"
        }
    }
}

"one","two" | Skip
```

```Output
Iteration: 0
    Skipping
Iteration: 1
    Input: two
```

### <a name="example-2-using-input-outside-the-process-block"></a><span data-ttu-id="66da3-382">Exemplo 2: usando $input fora do bloco de processo</span><span class="sxs-lookup"><span data-stu-id="66da3-382">Example 2: Using $input outside the process block</span></span>

<span data-ttu-id="66da3-383">Fora do bloco de processo, a `$input` variável representa todos os valores canalizados para a função.</span><span class="sxs-lookup"><span data-stu-id="66da3-383">Outside of the process block the `$input` variable represents all the values piped into the function.</span></span>

- <span data-ttu-id="66da3-384">O acesso à `$input` variável limpa todos os valores.</span><span class="sxs-lookup"><span data-stu-id="66da3-384">Accessing the `$input` variable clears all values.</span></span>
- <span data-ttu-id="66da3-385">O método de **redefinição** redefine a coleção inteira.</span><span class="sxs-lookup"><span data-stu-id="66da3-385">The **Reset** method resets the entire collection.</span></span>
- <span data-ttu-id="66da3-386">A propriedade **atual** nunca é populada.</span><span class="sxs-lookup"><span data-stu-id="66da3-386">The **Current** property is never populated.</span></span>
- <span data-ttu-id="66da3-387">O método **MoveNext** retorna false porque a coleção não pode ser avançada.</span><span class="sxs-lookup"><span data-stu-id="66da3-387">The **MoveNext** method returns false because the collection can't be advanced.</span></span>
  - <span data-ttu-id="66da3-388">Chamar **MoveNext** limpa a `$input` variável.</span><span class="sxs-lookup"><span data-stu-id="66da3-388">Calling **MoveNext** clears out the `$input` variable.</span></span>

```powershell
Function All
{
    "All Values: $input"
    "Access Again: $input"
    $input.Reset()
    "After Reset: $input"
    $input.MoveNext() | Out-Null
    "After MoveNext: $input"
}

"one","two","three" | All
```

```Output
All Values: one two three
Access Again:
After Reset: one two three
After MoveNext:
```

### <a name="example-3-using-the-inputcurrent-property"></a><span data-ttu-id="66da3-389">Exemplo 3: usando o $input. Propriedade atual</span><span class="sxs-lookup"><span data-stu-id="66da3-389">Example 3: Using the $input.Current property</span></span>

<span data-ttu-id="66da3-390">Usando a propriedade **Current** , o valor do pipeline atual pode ser acessado várias vezes sem usar o método **Reset** .</span><span class="sxs-lookup"><span data-stu-id="66da3-390">By using the **Current** property, the current pipeline value can be accessed multiple times without using the **Reset** method.</span></span> <span data-ttu-id="66da3-391">O bloco de processo não chama automaticamente o método **MoveNext** .</span><span class="sxs-lookup"><span data-stu-id="66da3-391">The process block doesn't automatically call the **MoveNext** method.</span></span>

<span data-ttu-id="66da3-392">A propriedade **atual** nunca será preenchida a menos que você chame explicitamente **MoveNext** .</span><span class="sxs-lookup"><span data-stu-id="66da3-392">The **Current** property will never be populated unless you explicitly call **MoveNext** .</span></span> <span data-ttu-id="66da3-393">A propriedade **Current** pode ser acessada várias vezes dentro do bloco Process sem limpar seu valor.</span><span class="sxs-lookup"><span data-stu-id="66da3-393">The **Current** property can be accessed multiple times inside the process block without clearing its value.</span></span>

```powershell
function Current
{
    begin
    {
        $i = 0
    }

    process
    {
        "Iteration: $i"
        $i++
        "`tBefore MoveNext: $($input.Current)"
        $input.MoveNext() | Out-Null
        "`tAfter MoveNext: $($input.Current)"
        "`tAccess Again: $($input.Current)"
    }
}

"one","two" | Current
```

```Output
Iteration: 0
    Before MoveNext:
    After MoveNext: one
    Access Again: one
Iteration: 1
    Before MoveNext:
    After MoveNext: two
    Access Again: two
```

### <a name="example-4-using-the-foreach-variable"></a><span data-ttu-id="66da3-394">Exemplo 4: usando a variável $foreach</span><span class="sxs-lookup"><span data-stu-id="66da3-394">Example 4: Using the $foreach variable</span></span>

<span data-ttu-id="66da3-395">Ao contrário da `$input` variável, a `$foreach` variável sempre representa todos os itens na coleção quando acessados diretamente.</span><span class="sxs-lookup"><span data-stu-id="66da3-395">Unlike the `$input` variable, the `$foreach` variable always represents all items in the collection when accessed directly.</span></span> <span data-ttu-id="66da3-396">Use a propriedade **Current** para acessar o elemento da coleção atual e os métodos **Reset** e **MoveNext** para alterar seu valor.</span><span class="sxs-lookup"><span data-stu-id="66da3-396">Use the **Current** property to access the current collection element, and the **Reset** and **MoveNext** methods to change its value.</span></span>

> [!NOTE]
> <span data-ttu-id="66da3-397">Cada iteração do `foreach` loop chamará automaticamente o método **MoveNext** .</span><span class="sxs-lookup"><span data-stu-id="66da3-397">Each iteration of the `foreach` loop will automatically call the **MoveNext** method.</span></span>

<span data-ttu-id="66da3-398">O loop a seguir é executado duas vezes.</span><span class="sxs-lookup"><span data-stu-id="66da3-398">The following loop only executes twice.</span></span> <span data-ttu-id="66da3-399">Na segunda iteração, a coleção é movida para o terceiro elemento antes da conclusão da iteração.</span><span class="sxs-lookup"><span data-stu-id="66da3-399">In the second iteration, the collection is moved to the third element before the iteration is complete.</span></span> <span data-ttu-id="66da3-400">Após a segunda iteração, agora não há mais valores para iterar e o loop é encerrado.</span><span class="sxs-lookup"><span data-stu-id="66da3-400">After the second iteration, there are now no more values to iterate, and the loop terminates.</span></span>

<span data-ttu-id="66da3-401">A propriedade **MoveNext** não afeta a variável escolhida para iterar pela coleção ( `$Num` ).</span><span class="sxs-lookup"><span data-stu-id="66da3-401">The **MoveNext** property doesn't affect the variable chosen to iterate through the collection (`$Num`).</span></span>

```powershell
$i = 0
foreach ($num in ("one","two","three"))
{
    "Iteration: $i"
    $i++
    "`tNum: $num"
    "`tCurrent: $($foreach.Current)"

    if ($foreach.Current -eq "two")
    {
        "Before MoveNext (Current): $($foreach.Current)"
        $foreach.MoveNext() | Out-Null
        "After MoveNext (Current): $($foreach.Current)"
        "Num has not changed: $num"
    }
}
```

```Output
Iteration: 0
        Num: one
        Current: one
Iteration: 1
        Num: two
        Current: two
Before MoveNext (Current): two
After MoveNext (Current): three
Num has not changed: two
```

<span data-ttu-id="66da3-402">O uso do método **Redefinir** redefine o elemento atual na coleção.</span><span class="sxs-lookup"><span data-stu-id="66da3-402">Using the **Reset** method resets the current element in the collection.</span></span> <span data-ttu-id="66da3-403">O exemplo a seguir faz um loop pelos dois primeiros elementos **duas vezes** porque o método **Reset** é chamado.</span><span class="sxs-lookup"><span data-stu-id="66da3-403">The following example loops through the first two elements **twice** because the **Reset** method is called.</span></span> <span data-ttu-id="66da3-404">Após os dois primeiros loops, a `if` instrução falha e o loop é iterado por todos os três elementos normalmente.</span><span class="sxs-lookup"><span data-stu-id="66da3-404">After the first two loops, the `if` statement fails and the loop iterates through all three elements normally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66da3-405">Isso pode resultar em um loop infinito.</span><span class="sxs-lookup"><span data-stu-id="66da3-405">This could result in an infinite loop.</span></span>

```powershell
$stopLoop = 0
foreach ($num in ("one","two", "three"))
{
    ("`t" * $stopLoop) + "Current: $($foreach.Current)"

    if ($num -eq "two" -and $stopLoop -lt 2)
    {
        $foreach.Reset() | Out-Null
        ("`t" * $stopLoop) + "Reset Loop: $stopLoop"
        $stopLoop++
    }
}
```

```Output
Current: one
Current: two
Reset Loop: 0
        Current: one
        Current: two
        Reset Loop: 1
                Current: one
                Current: two
                Current: three
```

### <a name="example-5-using-the-switch-variable"></a><span data-ttu-id="66da3-406">Exemplo 5: usando a variável $switch</span><span class="sxs-lookup"><span data-stu-id="66da3-406">Example 5: Using the $switch variable</span></span>

<span data-ttu-id="66da3-407">A `$switch` variável tem exatamente as mesmas regras que a `$foreach` variável.</span><span class="sxs-lookup"><span data-stu-id="66da3-407">The `$switch` variable has the exact same rules as the `$foreach` variable.</span></span>
<span data-ttu-id="66da3-408">O exemplo a seguir demonstra todos os conceitos de enumerador.</span><span class="sxs-lookup"><span data-stu-id="66da3-408">The following example demonstrates all the enumerator concepts.</span></span>

> [!NOTE]
> <span data-ttu-id="66da3-409">Observe como o caso não **avaliado** nunca é executado, mesmo que não haja `break` instrução após o método **MoveNext** .</span><span class="sxs-lookup"><span data-stu-id="66da3-409">Note how the **NotEvaluated** case is never executed, even though there's no `break` statement after the **MoveNext** method.</span></span>

```powershell
$values = "Start", "MoveNext", "NotEvaluated", "Reset", "End"
$stopInfinite = $false
switch ($values)
{
    "MoveNext" {
        "`tMoveNext"
        $switch.MoveNext() | Out-Null
        "`tAfter MoveNext: $($switch.Current)"
    }
    # This case is never evaluated.
    "NotEvaluated" {
        "`tAfterMoveNext: $($switch.Current)"
    }

    "Reset" {
        if (!$stopInfinite)
        {
            "`tReset"
            $switch.Reset()
            $stopInfinite = $true
        }
    }

    default {
        "Default (Current): $($switch.Current)"
    }
}
```

```Output
Default (Current): Start
    MoveNext
    After MoveNext: NotEvaluated
    Reset
Default (Current): Start
    MoveNext
    After MoveNext: NotEvaluated
Default (Current): End
```

## <a name="see-also"></a><span data-ttu-id="66da3-410">Confira também</span><span class="sxs-lookup"><span data-stu-id="66da3-410">See also</span></span>

[<span data-ttu-id="66da3-411">about_Functions</span><span class="sxs-lookup"><span data-stu-id="66da3-411">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="66da3-412">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="66da3-412">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="66da3-413">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="66da3-413">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="66da3-414">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="66da3-414">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="66da3-415">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="66da3-415">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)

[<span data-ttu-id="66da3-416">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="66da3-416">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="66da3-417">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="66da3-417">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="66da3-418">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="66da3-418">about_Preference_Variables</span></span>](about_Preference_Variables.md)

[<span data-ttu-id="66da3-419">about_Splatting</span><span class="sxs-lookup"><span data-stu-id="66da3-419">about_Splatting</span></span>](about_Splatting.md)

[<span data-ttu-id="66da3-420">about_Variables</span><span class="sxs-lookup"><span data-stu-id="66da3-420">about_Variables</span></span>](about_Variables.md)
