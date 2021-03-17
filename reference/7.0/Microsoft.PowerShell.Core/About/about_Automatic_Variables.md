---
description: Descreve as variáveis que armazenam informações de estado do PowerShell. Essas variáveis são criadas e mantidas pelo PowerShell.
Locale: en-US
ms.date: 03/15/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_automatic_variables?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Automatic_Variables
ms.openlocfilehash: e64f06c91df68b10db195d4eede022be5998bb35
ms.sourcegitcommit: 15f759ca68d17acecab46b52250298d4f2037c4d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2021
ms.locfileid: "103575688"
---
# <a name="about-automatic-variables"></a><span data-ttu-id="6ccf4-104">Sobre variáveis automáticas</span><span class="sxs-lookup"><span data-stu-id="6ccf4-104">About Automatic Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="6ccf4-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="6ccf4-105">Short description</span></span>

<span data-ttu-id="6ccf4-106">Descreve as variáveis que armazenam informações de estado do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-106">Describes variables that store state information for PowerShell.</span></span> <span data-ttu-id="6ccf4-107">Essas variáveis são criadas e mantidas pelo PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-107">These variables are created and maintained by PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="6ccf4-108">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="6ccf4-108">Long description</span></span>

<span data-ttu-id="6ccf4-109">Conceitualmente, essas variáveis são consideradas como somente leitura.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-109">Conceptually, these variables are considered to be read-only.</span></span> <span data-ttu-id="6ccf4-110">Embora eles **possam** ser gravados, para compatibilidade com versões anteriores, eles **não devem** ser gravados.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-110">Even though they **can** be written to, for backward compatibility they **should not** be written to.</span></span>

<span data-ttu-id="6ccf4-111">Aqui está uma lista das variáveis automáticas no PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6ccf4-111">Here is a list of the automatic variables in PowerShell:</span></span>

### <a name=""></a>$$

<span data-ttu-id="6ccf4-112">Contém o último token na última linha recebida pela sessão.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-112">Contains the last token in the last line received by the session.</span></span>

### <a name=""></a><span data-ttu-id="6ccf4-113">$?</span><span class="sxs-lookup"><span data-stu-id="6ccf4-113">$?</span></span>

<span data-ttu-id="6ccf4-114">Contém o status de execução do último comando.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-114">Contains the execution status of the last command.</span></span> <span data-ttu-id="6ccf4-115">Ele conterá **true** se o último comando tiver êxito e **false** se ele tiver falhado.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-115">It contains **True** if the last command succeeded and **False** if it failed.</span></span>

<span data-ttu-id="6ccf4-116">Para cmdlets e funções avançadas que são executadas em vários estágios em um pipeline, por exemplo, em `process` `end` blocos and, chamando `this.WriteError()` ou `$PSCmdlet.WriteError()` respectivamente em qualquer ponto, serão definidos como `$?` **false**, como `this.ThrowTerminatingError()` e `$PSCmdlet.ThrowTerminatingError()` .</span><span class="sxs-lookup"><span data-stu-id="6ccf4-116">For cmdlets and advanced functions that are run at multiple stages in a pipeline, for example in both `process` and `end` blocks, calling `this.WriteError()` or `$PSCmdlet.WriteError()` respectively at any point will set `$?` to **False**, as will `this.ThrowTerminatingError()` and `$PSCmdlet.ThrowTerminatingError()`.</span></span>

<span data-ttu-id="6ccf4-117">O `Write-Error` cmdlet sempre define `$?` como **false** imediatamente após ser executado, mas não será definido `$?` como **false** para uma função que a chama:</span><span class="sxs-lookup"><span data-stu-id="6ccf4-117">The `Write-Error` cmdlet always sets `$?` to **False** immediately after it is executed, but will not set `$?` to **False** for a function calling it:</span></span>

```powershell
function Test-WriteError
{
    Write-Error "Bad"
    $? # $false
}

Test-WriteError
$? # $true
```

<span data-ttu-id="6ccf4-118">Para a última finalidade, `$PSCmdlet.WriteError()` deve ser usado em vez disso.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-118">For the latter purpose, `$PSCmdlet.WriteError()` should be used instead.</span></span>

<span data-ttu-id="6ccf4-119">Para comandos nativos (executáveis), `$?` é definido como **true** quando `$LASTEXITCODE` é 0 e definido como **false** quando `$LASTEXITCODE` é qualquer outro valor.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-119">For native commands (executables), `$?` is set to **True** when `$LASTEXITCODE` is 0, and set to **False** when `$LASTEXITCODE` is any other value.</span></span>

> [!NOTE]
> <span data-ttu-id="6ccf4-120">Até o PowerShell 7, que contém uma instrução entre parênteses `(...)` , sintaxe `$(...)` de subexpressão ou expressão `@(...)` de matriz sempre redefinida como `$?` **true**, para que seja `(Write-Error)` exibida `$?` como **verdadeira**.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-120">Until PowerShell 7, containing a statement within parentheses `(...)`, subexpression syntax `$(...)` or array expression `@(...)` always reset `$?` to **True**, so that `(Write-Error)` shows `$?` as **True**.</span></span>
> <span data-ttu-id="6ccf4-121">Isso foi alterado no PowerShell 7, de modo que `$?` sempre refletirá o êxito real da execução do último comando nessas expressões.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-121">This has been changed in PowerShell 7, so that `$?` will always reflect the actual success of the last command run in these expressions.</span></span>

### <a name=""></a>$^

<span data-ttu-id="6ccf4-122">Contém o primeiro token na última linha recebida pela sessão.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-122">Contains the first token in the last line received by the session.</span></span>

### <a name="_"></a><span data-ttu-id="6ccf4-123">$_</span><span class="sxs-lookup"><span data-stu-id="6ccf4-123">$_</span></span>

<span data-ttu-id="6ccf4-124">Mesmo que `$PSItem`.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-124">Same as `$PSItem`.</span></span> <span data-ttu-id="6ccf4-125">Contém o objeto atual no objeto de pipeline.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-125">Contains the current object in the pipeline object.</span></span> <span data-ttu-id="6ccf4-126">Você pode usar essa variável em comandos que executam uma ação em cada objeto ou em objetos selecionados em um pipeline.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-126">You can use this variable in commands that perform an action on every object or on selected objects in a pipeline.</span></span>

### <a name="args"></a><span data-ttu-id="6ccf4-127">$args</span><span class="sxs-lookup"><span data-stu-id="6ccf4-127">$args</span></span>

<span data-ttu-id="6ccf4-128">Contém uma matriz de valores para parâmetros não declarados que são passados para uma função, script ou bloco de script.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-128">Contains an array of values for undeclared parameters that are passed to a function, script, or script block.</span></span> <span data-ttu-id="6ccf4-129">Ao criar uma função, você pode declarar os parâmetros usando a `param` palavra-chave ou adicionando uma lista separada por vírgulas de parâmetros entre parênteses após o nome da função.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-129">When you create a function, you can declare the parameters by using the `param` keyword or by adding a comma-separated list of parameters in parentheses after the function name.</span></span>

<span data-ttu-id="6ccf4-130">Em uma ação de evento, a `$Args` variável contém objetos que representam os argumentos do evento que está sendo processado.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-130">In an event action, the `$Args` variable contains objects that represent the event arguments of the event that is being processed.</span></span> <span data-ttu-id="6ccf4-131">Essa variável é populada somente dentro do `Action` bloco de um comando de registro de evento.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-131">This variable is populated only within the `Action` block of an event registration command.</span></span>
<span data-ttu-id="6ccf4-132">O valor dessa variável também pode ser encontrado na propriedade **SourceArgs** do objeto **PSEventArgs** que `Get-Event` retorna.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-132">The value of this variable can also be found in the **SourceArgs** property of the **PSEventArgs** object that `Get-Event` returns.</span></span>

### <a name="consolefilename"></a><span data-ttu-id="6ccf4-133">$ConsoleFileName</span><span class="sxs-lookup"><span data-stu-id="6ccf4-133">$ConsoleFileName</span></span>

<span data-ttu-id="6ccf4-134">Contém o caminho do arquivo de console ( `.psc1` ) que foi usado mais recentemente na sessão.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-134">Contains the path of the console file (`.psc1`) that was most recently used in the session.</span></span> <span data-ttu-id="6ccf4-135">Essa variável é populada quando você inicia o PowerShell com o parâmetro **PSConsoleFile** ou quando usa o `Export-Console` cmdlet para exportar nomes de snap-in para um arquivo de console.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-135">This variable is populated when you start PowerShell with the **PSConsoleFile** parameter or when you use the `Export-Console` cmdlet to export snap-in names to a console file.</span></span>

<span data-ttu-id="6ccf4-136">Quando você usa o `Export-Console` cmdlet sem parâmetros, ele atualiza automaticamente o arquivo de console que foi usado mais recentemente na sessão.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-136">When you use the `Export-Console` cmdlet without parameters, it automatically updates the console file that was most recently used in the session.</span></span> <span data-ttu-id="6ccf4-137">Você pode usar essa variável automática para determinar qual arquivo será atualizado.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-137">You can use this automatic variable to determine which file will be updated.</span></span>

### <a name="error"></a><span data-ttu-id="6ccf4-138">$Error</span><span class="sxs-lookup"><span data-stu-id="6ccf4-138">$Error</span></span>

<span data-ttu-id="6ccf4-139">Contém uma matriz de objetos de erro que representam os erros mais recentes.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-139">Contains an array of error objects that represent the most recent errors.</span></span>
<span data-ttu-id="6ccf4-140">O erro mais recente é o primeiro objeto de erro na matriz `$Error[0]` .</span><span class="sxs-lookup"><span data-stu-id="6ccf4-140">The most recent error is the first error object in the array `$Error[0]`.</span></span>

<span data-ttu-id="6ccf4-141">Para impedir que um erro seja adicionado à `$Error` matriz, use o parâmetro comum **ErrorAction** com um valor de **ignorar**.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-141">To prevent an error from being added to the `$Error` array, use the **ErrorAction** common parameter with a value of **Ignore**.</span></span> <span data-ttu-id="6ccf4-142">Para obter mais informações, confira [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="6ccf4-142">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

### <a name="event"></a><span data-ttu-id="6ccf4-143">$Event</span><span class="sxs-lookup"><span data-stu-id="6ccf4-143">$Event</span></span>

<span data-ttu-id="6ccf4-144">Contém um objeto **PSEventArgs** que representa o evento que está sendo processado.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-144">Contains a **PSEventArgs** object that represents the event that is being processed.</span></span> <span data-ttu-id="6ccf4-145">Essa variável é populada somente dentro do `Action` bloco de um comando de registro de evento, como `Register-ObjectEvent` .</span><span class="sxs-lookup"><span data-stu-id="6ccf4-145">This variable is populated only within the `Action` block of an event registration command, such as `Register-ObjectEvent`.</span></span> <span data-ttu-id="6ccf4-146">O valor dessa variável é o mesmo objeto que o `Get-Event` cmdlet retorna.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-146">The value of this variable is the same object that the `Get-Event` cmdlet returns.</span></span> <span data-ttu-id="6ccf4-147">Portanto, você pode usar as propriedades da `Event` variável, como `$Event.TimeGenerated` , em um bloco de `Action` script.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-147">Therefore, you can use the properties of the `Event` variable, such as `$Event.TimeGenerated`, in an `Action` script block.</span></span>

### <a name="eventargs"></a><span data-ttu-id="6ccf4-148">$EventArgs</span><span class="sxs-lookup"><span data-stu-id="6ccf4-148">$EventArgs</span></span>

<span data-ttu-id="6ccf4-149">Contém um objeto que representa o primeiro argumento de evento que deriva de **EventArgs** do evento que está sendo processado.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-149">Contains an object that represents the first event argument that derives from **EventArgs** of the event that is being processed.</span></span> <span data-ttu-id="6ccf4-150">Essa variável é populada somente dentro do `Action` bloco de um comando de registro de evento.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-150">This variable is populated only within the `Action` block of an event registration command.</span></span>
<span data-ttu-id="6ccf4-151">O valor dessa variável também pode ser encontrado na propriedade **SourceEventArgs** do objeto **PSEventArgs** que `Get-Event` retorna.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-151">The value of this variable can also be found in the **SourceEventArgs** property of the **PSEventArgs** object that `Get-Event` returns.</span></span>

### <a name="eventsubscriber"></a><span data-ttu-id="6ccf4-152">$EventSubscriber</span><span class="sxs-lookup"><span data-stu-id="6ccf4-152">$EventSubscriber</span></span>

<span data-ttu-id="6ccf4-153">Contém um objeto **PSEventSubscriber** que representa o Assinante de evento do evento que está sendo processado.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-153">Contains a **PSEventSubscriber** object that represents the event subscriber of the event that is being processed.</span></span> <span data-ttu-id="6ccf4-154">Essa variável é populada somente dentro do `Action` bloco de um comando de registro de evento.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-154">This variable is populated only within the `Action` block of an event registration command.</span></span> <span data-ttu-id="6ccf4-155">O valor dessa variável é o mesmo objeto que o `Get-EventSubscriber` cmdlet retorna.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-155">The value of this variable is the same object that the `Get-EventSubscriber` cmdlet returns.</span></span>

### <a name="executioncontext"></a><span data-ttu-id="6ccf4-156">$ExecutionContext</span><span class="sxs-lookup"><span data-stu-id="6ccf4-156">$ExecutionContext</span></span>

<span data-ttu-id="6ccf4-157">Contém um objeto **EngineIntrinsics** que representa o contexto de execução do host do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-157">Contains an **EngineIntrinsics** object that represents the execution context of the PowerShell host.</span></span> <span data-ttu-id="6ccf4-158">Você pode usar essa variável para localizar os objetos de execução que estão disponíveis para os cmdlets.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-158">You can use this variable to find the execution objects that are available to cmdlets.</span></span>

### <a name="false"></a><span data-ttu-id="6ccf4-159">$false</span><span class="sxs-lookup"><span data-stu-id="6ccf4-159">$false</span></span>

<span data-ttu-id="6ccf4-160">Contém **false**.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-160">Contains **False**.</span></span> <span data-ttu-id="6ccf4-161">Você pode usar essa variável para representar **falso** em comandos e scripts em vez de usar a cadeia de caracteres "false".</span><span class="sxs-lookup"><span data-stu-id="6ccf4-161">You can use this variable to represent **False** in commands and scripts instead of using the string "false".</span></span> <span data-ttu-id="6ccf4-162">A cadeia de caracteres poderá ser interpretada como **true** se for convertida em uma cadeia de caracteres não vazia ou em um inteiro diferente de zero.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-162">The string can be interpreted as **True** if it's converted to a non-empty string or to a non-zero integer.</span></span>

### <a name="foreach"></a><span data-ttu-id="6ccf4-163">$foreach</span><span class="sxs-lookup"><span data-stu-id="6ccf4-163">$foreach</span></span>

<span data-ttu-id="6ccf4-164">Contém o enumerador (não os valores resultantes) de um loop [foreach](about_ForEach.md) .</span><span class="sxs-lookup"><span data-stu-id="6ccf4-164">Contains the enumerator (not the resulting values) of a [ForEach](about_ForEach.md) loop.</span></span> <span data-ttu-id="6ccf4-165">A `$ForEach` variável existe somente enquanto o `ForEach` loop está em execução; ela é excluída após a conclusão do loop.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-165">The `$ForEach` variable exists only while the `ForEach` loop is running; it's deleted after the loop is completed.</span></span>

<span data-ttu-id="6ccf4-166">Enumeradores contêm propriedades e métodos que você pode usar para recuperar valores de loop e alterar a iteração do loop atual.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-166">Enumerators contain properties and methods you can use to retrieve loop values and change the current loop iteration.</span></span> <span data-ttu-id="6ccf4-167">Para obter mais informações, consulte [usando enumeradores](#using-enumerators).</span><span class="sxs-lookup"><span data-stu-id="6ccf4-167">For more information, see [Using Enumerators](#using-enumerators).</span></span>

### <a name="home"></a><span data-ttu-id="6ccf4-168">$HOME</span><span class="sxs-lookup"><span data-stu-id="6ccf4-168">$HOME</span></span>

<span data-ttu-id="6ccf4-169">Contém o caminho completo do diretório base do usuário.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-169">Contains the full path of the user's home directory.</span></span> <span data-ttu-id="6ccf4-170">Essa variável é equivalente às variáveis de `"$env:homedrive$env:homepath"` ambiente do Windows, normalmente `C:\Users\<UserName>` .</span><span class="sxs-lookup"><span data-stu-id="6ccf4-170">This variable is the equivalent of the `"$env:homedrive$env:homepath"` Windows environment variables, typically `C:\Users\<UserName>`.</span></span>

### <a name="host"></a><span data-ttu-id="6ccf4-171">$Host</span><span class="sxs-lookup"><span data-stu-id="6ccf4-171">$Host</span></span>

<span data-ttu-id="6ccf4-172">Contém um objeto que representa o aplicativo host atual para o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-172">Contains an object that represents the current host application for PowerShell.</span></span> <span data-ttu-id="6ccf4-173">Você pode usar essa variável para representar o host atual em comandos ou para exibir ou alterar as propriedades do host, como `$Host.version` ou ou `$Host.CurrentCulture` `$host.ui.rawui.setbackgroundcolor("Red")` .</span><span class="sxs-lookup"><span data-stu-id="6ccf4-173">You can use this variable to represent the current host in commands or to display or change the properties of the host, such as `$Host.version` or `$Host.CurrentCulture`, or `$host.ui.rawui.setbackgroundcolor("Red")`.</span></span>

### <a name="input"></a><span data-ttu-id="6ccf4-174">$input</span><span class="sxs-lookup"><span data-stu-id="6ccf4-174">$input</span></span>

<span data-ttu-id="6ccf4-175">Contém um enumerador que enumera todas as entradas passadas para uma função.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-175">Contains an enumerator that enumerates all input that is passed to a function.</span></span> <span data-ttu-id="6ccf4-176">A `$input` variável está disponível somente para funções e blocos de script (que são funções sem nome).</span><span class="sxs-lookup"><span data-stu-id="6ccf4-176">The `$input` variable is available only to functions and script blocks (which are unnamed functions).</span></span>

- <span data-ttu-id="6ccf4-177">Em uma função sem um `Begin` `Process` bloco, ou `End` , a `$input` variável enumera a coleção de todas as entradas para a função.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-177">In a function without a `Begin`, `Process`, or `End` block, the `$input` variable enumerates the collection of all input to the function.</span></span>

- <span data-ttu-id="6ccf4-178">No `Begin` bloco, a `$input` variável não contém dados.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-178">In the `Begin` block, the `$input` variable contains no data.</span></span>

- <span data-ttu-id="6ccf4-179">No `Process` bloco, a `$input` variável contém o objeto que está atualmente no pipeline.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-179">In the `Process` block, the `$input` variable contains the object that is currently in the pipeline.</span></span>

- <span data-ttu-id="6ccf4-180">No `End` bloco, a `$input` variável enumera a coleção de todas as entradas para a função.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-180">In the `End` block, the `$input` variable enumerates the collection of all input to the function.</span></span>

  > [!NOTE]
  > <span data-ttu-id="6ccf4-181">Não é possível usar a `$input` variável dentro do bloco Process e do bloco end na mesma função ou bloco de script.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-181">You cannot use the `$input` variable inside both the Process block and the End block in the same function or script block.</span></span>

<span data-ttu-id="6ccf4-182">Como `$input` é um enumerador, o acesso a qualquer uma das suas propriedades faz com que `$input` não esteja mais disponível.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-182">Since `$input` is an enumerator, accessing any of it's properties causes `$input` to no longer be available.</span></span> <span data-ttu-id="6ccf4-183">Você pode armazenar `$input` em outra variável para reutilizar as `$input` Propriedades.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-183">You can store `$input` in another variable to reuse the `$input` properties.</span></span>

<span data-ttu-id="6ccf4-184">Enumeradores contêm propriedades e métodos que você pode usar para recuperar valores de loop e alterar a iteração do loop atual.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-184">Enumerators contain properties and methods you can use to retrieve loop values and change the current loop iteration.</span></span> <span data-ttu-id="6ccf4-185">Para obter mais informações, consulte [usando enumeradores](#using-enumerators).</span><span class="sxs-lookup"><span data-stu-id="6ccf4-185">For more information, see [Using Enumerators](#using-enumerators).</span></span>

<span data-ttu-id="6ccf4-186">A `$input` variável também está disponível para o comando especificado pelo `-Command` parâmetro de `pwsh` quando invocado na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-186">The `$input` variable is also available to the command specified by the `-Command` parameter of `pwsh` when invoked from the command line.</span></span> <span data-ttu-id="6ccf4-187">O exemplo a seguir é executado no Shell de comando do Windows.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-187">The following example is run from the Windows Command shell.</span></span>

```CMD
echo Hello | pwsh -Command """$input World!"""
```

### <a name="iscoreclr"></a><span data-ttu-id="6ccf4-188">$IsCoreCLR</span><span class="sxs-lookup"><span data-stu-id="6ccf4-188">$IsCoreCLR</span></span>

<span data-ttu-id="6ccf4-189">Contém `$True` se a sessão atual está em execução no CoreCLR (tempo de execução do .NET Core).</span><span class="sxs-lookup"><span data-stu-id="6ccf4-189">Contains `$True` if the current session is running on the .NET Core Runtime (CoreCLR).</span></span> <span data-ttu-id="6ccf4-190">Caso contrário, contém `$False` .</span><span class="sxs-lookup"><span data-stu-id="6ccf4-190">Otherwise contains `$False`.</span></span>

### <a name="islinux"></a><span data-ttu-id="6ccf4-191">$IsLinux</span><span class="sxs-lookup"><span data-stu-id="6ccf4-191">$IsLinux</span></span>

<span data-ttu-id="6ccf4-192">Contém `$True` se a sessão atual está sendo executada em um sistema operacional Linux.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-192">Contains `$True` if the current session is running on a Linux operating system.</span></span>
<span data-ttu-id="6ccf4-193">Caso contrário, contém `$False` .</span><span class="sxs-lookup"><span data-stu-id="6ccf4-193">Otherwise contains `$False`.</span></span>

### <a name="ismacos"></a><span data-ttu-id="6ccf4-194">$IsMacOS</span><span class="sxs-lookup"><span data-stu-id="6ccf4-194">$IsMacOS</span></span>

<span data-ttu-id="6ccf4-195">Contém `$True` se a sessão atual está sendo executada em um sistema operacional MacOS.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-195">Contains `$True` if the current session is running on a MacOS operating system.</span></span>
<span data-ttu-id="6ccf4-196">Caso contrário, contém `$False` .</span><span class="sxs-lookup"><span data-stu-id="6ccf4-196">Otherwise contains `$False`.</span></span>

### <a name="iswindows"></a><span data-ttu-id="6ccf4-197">$IsWindows</span><span class="sxs-lookup"><span data-stu-id="6ccf4-197">$IsWindows</span></span>

<span data-ttu-id="6ccf4-198">Contém `$TRUE` se a sessão atual está sendo executada em um sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-198">Contains `$TRUE` if the current session is running on a Windows operating system.</span></span> <span data-ttu-id="6ccf4-199">Caso contrário, contém `$FALSE` .</span><span class="sxs-lookup"><span data-stu-id="6ccf4-199">Otherwise contains `$FALSE`.</span></span>

### <a name="lastexitcode"></a><span data-ttu-id="6ccf4-200">$LastExitCode</span><span class="sxs-lookup"><span data-stu-id="6ccf4-200">$LastExitCode</span></span>

<span data-ttu-id="6ccf4-201">Contém o código de saída do último programa baseado no Windows que foi executado.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-201">Contains the exit code of the last Windows-based program that was run.</span></span>

### <a name="matches"></a><span data-ttu-id="6ccf4-202">$Matches</span><span class="sxs-lookup"><span data-stu-id="6ccf4-202">$Matches</span></span>

<span data-ttu-id="6ccf4-203">A `Matches` variável funciona com os `-match` `-notmatch` operadores e.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-203">The `Matches` variable works with the `-match` and `-notmatch` operators.</span></span>
<span data-ttu-id="6ccf4-204">Quando você envia a entrada escalar para `-match` o `-notmatch` operador OR e qualquer uma detecta uma correspondência, elas retornam um valor booliano e preenchem a `$Matches` variável automática com uma tabela de hash de quaisquer valores de cadeia de caracteres que foram correspondidos.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-204">When you submit scalar input to the `-match` or `-notmatch` operator, and either one detects a match, they return a Boolean value and populate the `$Matches` automatic variable with a hash table of any string values that were matched.</span></span> <span data-ttu-id="6ccf4-205">A `$Matches` tabela de hash também pode ser populada com capturas quando você usa expressões regulares com o `-match` operador.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-205">The `$Matches` hash table can also be populated with captures when you use regular expressions with the `-match` operator.</span></span>

<span data-ttu-id="6ccf4-206">Para obter mais informações sobre o `-match` operador, consulte [about_Comparison_Operators](about_comparison_operators.md).</span><span class="sxs-lookup"><span data-stu-id="6ccf4-206">For more information about the `-match` operator, see [about_Comparison_Operators](about_comparison_operators.md).</span></span> <span data-ttu-id="6ccf4-207">Para obter mais informações sobre expressões regulares, consulte [about_Regular_Expressions](about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="6ccf4-207">For more information on regular expressions, see [about_Regular_Expressions](about_Regular_Expressions.md).</span></span>

### <a name="myinvocation"></a><span data-ttu-id="6ccf4-208">$MyInvocation</span><span class="sxs-lookup"><span data-stu-id="6ccf4-208">$MyInvocation</span></span>

<span data-ttu-id="6ccf4-209">Contém informações sobre o comando atual, como nome, parâmetros, valores de parâmetro e informações sobre como o comando foi iniciado, chamado ou invocado, como o nome do script que chamou o comando atual.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-209">Contains information about the current command, such as the name, parameters, parameter values, and information about how the command was started, called, or invoked, such as the name of the script that called the current command.</span></span>

<span data-ttu-id="6ccf4-210">`$MyInvocation` é preenchido somente para scripts, funções e blocos de script.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-210">`$MyInvocation` is populated only for scripts, function, and script blocks.</span></span> <span data-ttu-id="6ccf4-211">Você pode usar as informações no objeto **System. Management. Automation. InvocationInfo** que `$MyInvocation` retorna no script atual, como o caminho e o nome do arquivo do script ( `$MyInvocation.MyCommand.Path` ) ou o nome de uma função ( `$MyInvocation.MyCommand.Name` ) para identificar o comando atual.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-211">You can use the information in the **System.Management.Automation.InvocationInfo** object that `$MyInvocation` returns in the current script, such as the path and file name of the script (`$MyInvocation.MyCommand.Path`) or the name of a function (`$MyInvocation.MyCommand.Name`) to identify the current command.</span></span> <span data-ttu-id="6ccf4-212">Isso é particularmente útil para localizar o nome do script atual.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-212">This is particularly useful for finding the name of the current script.</span></span>

<span data-ttu-id="6ccf4-213">A partir do PowerShell 3,0, `MyInvocation` o tem as novas propriedades a seguir.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-213">Beginning in PowerShell 3.0, `MyInvocation` has the following new properties.</span></span>

| <span data-ttu-id="6ccf4-214">Propriedade</span><span class="sxs-lookup"><span data-stu-id="6ccf4-214">Property</span></span>      | <span data-ttu-id="6ccf4-215">Descrição</span><span class="sxs-lookup"><span data-stu-id="6ccf4-215">Description</span></span>                                         |
| ------------- | --------------------------------------------------- |
| <span data-ttu-id="6ccf4-216">**PSScriptRoot**</span><span class="sxs-lookup"><span data-stu-id="6ccf4-216">**PSScriptRoot**</span></span>  | <span data-ttu-id="6ccf4-217">Contém o caminho completo para o script que foi invocado</span><span class="sxs-lookup"><span data-stu-id="6ccf4-217">Contains the full path to the script that invoked</span></span>   |
|               | <span data-ttu-id="6ccf4-218">o comando atual.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-218">the current command.</span></span> <span data-ttu-id="6ccf4-219">O valor dessa propriedade é</span><span class="sxs-lookup"><span data-stu-id="6ccf4-219">The value of this property is</span></span>  |
|               | <span data-ttu-id="6ccf4-220">populado somente quando o chamador é um script.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-220">populated only when the caller is a script.</span></span>         |
| <span data-ttu-id="6ccf4-221">**PSCommandPath**</span><span class="sxs-lookup"><span data-stu-id="6ccf4-221">**PSCommandPath**</span></span> | <span data-ttu-id="6ccf4-222">Contém o caminho completo e o nome do arquivo do script</span><span class="sxs-lookup"><span data-stu-id="6ccf4-222">Contains the full path and file name of the script</span></span>  |
|               | <span data-ttu-id="6ccf4-223">que invocou o comando atual.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-223">that invoked the current command.</span></span> <span data-ttu-id="6ccf4-224">O valor deste</span><span class="sxs-lookup"><span data-stu-id="6ccf4-224">The value of this</span></span> |
|               | <span data-ttu-id="6ccf4-225">a propriedade é populada somente quando o chamador é um</span><span class="sxs-lookup"><span data-stu-id="6ccf4-225">property is populated only when the caller is a</span></span>     |
|               | <span data-ttu-id="6ccf4-226">.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-226">script.</span></span>                                             |

<span data-ttu-id="6ccf4-227">Ao contrário `$PSScriptRoot` das `$PSCommandPath` variáveis e automáticas, as propriedades **PSScriptRoot** e **PSCommandPath** da `$MyInvocation` variável automática contêm informações sobre o chamador ou o script de chamada, não o script atual.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-227">Unlike the `$PSScriptRoot` and `$PSCommandPath` automatic variables, the **PSScriptRoot** and **PSCommandPath** properties of the `$MyInvocation` automatic variable contain information about the invoker or calling script, not the current script.</span></span>

### <a name="nestedpromptlevel"></a><span data-ttu-id="6ccf4-228">$NestedPromptLevel</span><span class="sxs-lookup"><span data-stu-id="6ccf4-228">$NestedPromptLevel</span></span>

<span data-ttu-id="6ccf4-229">Contém o nível do prompt atual.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-229">Contains the current prompt level.</span></span> <span data-ttu-id="6ccf4-230">Um valor de 0 indica o nível do prompt original.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-230">A value of 0 indicates the original prompt level.</span></span> <span data-ttu-id="6ccf4-231">O valor é incrementado quando você insere um nível aninhado e diminui quando sai dele.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-231">The value is incremented when you enter a nested level and decremented when you exit it.</span></span>

<span data-ttu-id="6ccf4-232">Por exemplo, o PowerShell apresenta um prompt de comando aninhado quando você usa o `$Host.EnterNestedPrompt` método.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-232">For example, PowerShell presents a nested command prompt when you use the `$Host.EnterNestedPrompt` method.</span></span> <span data-ttu-id="6ccf4-233">O PowerShell também apresenta um prompt de comando aninhado quando você atinge um ponto de interrupção no depurador do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-233">PowerShell also presents a nested command prompt when you reach a breakpoint in the PowerShell debugger.</span></span>

<span data-ttu-id="6ccf4-234">Quando você insere um prompt aninhado, o PowerShell pausa o comando atual, salva o contexto de execução e incrementa o valor da `$NestedPromptLevel` variável.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-234">When you enter a nested prompt, PowerShell pauses the current command, saves the execution context, and increments the value of the `$NestedPromptLevel` variable.</span></span> <span data-ttu-id="6ccf4-235">Para criar prompts de comando aninhados adicionais (até 128 níveis) ou retornar ao prompt de comando original, conclua o comando ou digite `exit` .</span><span class="sxs-lookup"><span data-stu-id="6ccf4-235">To create additional nested command prompts (up to 128 levels) or to return to the original command prompt, complete the command, or type `exit`.</span></span>

<span data-ttu-id="6ccf4-236">A `$NestedPromptLevel` variável ajuda a acompanhar o nível do prompt.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-236">The `$NestedPromptLevel` variable helps you track the prompt level.</span></span> <span data-ttu-id="6ccf4-237">Você pode criar um prompt de comando alternativo do PowerShell que inclua esse valor para que ele fique sempre visível.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-237">You can create an alternative PowerShell command prompt that includes this value so that it's always visible.</span></span>

### <a name="null"></a><span data-ttu-id="6ccf4-238">$null</span><span class="sxs-lookup"><span data-stu-id="6ccf4-238">$null</span></span>

<span data-ttu-id="6ccf4-239">`$null` é uma variável automática que contém um valor **nulo** ou vazio.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-239">`$null` is an automatic variable that contains a **null** or empty value.</span></span> <span data-ttu-id="6ccf4-240">Você pode usar essa variável para representar um valor ausente ou indefinido em comandos e scripts.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-240">You can use this variable to represent an absent or undefined value in commands and scripts.</span></span>

<span data-ttu-id="6ccf4-241">O PowerShell trata `$null` como um objeto com um valor, ou seja, como um espaço reservado explícito, para que você possa usar `$null` para representar um valor vazio em uma série de valores.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-241">PowerShell treats `$null` as an object with a value, that is, as an explicit placeholder, so you can use `$null` to represent an empty value in a series of values.</span></span>

<span data-ttu-id="6ccf4-242">Por exemplo, quando `$null` é incluído em uma coleção, ele é contado como um dos objetos.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-242">For example, when `$null` is included in a collection, it's counted as one of the objects.</span></span>

```powershell
$a = "one", $null, "three"
$a.count
```

```Output
3
```

<span data-ttu-id="6ccf4-243">Se você canalizar a `$null` variável para o `ForEach-Object` cmdlet, ele gerará um valor para `$null` , assim como faz para os outros objetos</span><span class="sxs-lookup"><span data-stu-id="6ccf4-243">If you pipe the `$null` variable to the `ForEach-Object` cmdlet, it generates a value for `$null`, just as it does for the other objects</span></span>

```powershell
"one", $null, "three" | ForEach-Object { "Hello " + $_}
```

```Output
Hello one
Hello
Hello three
```

<span data-ttu-id="6ccf4-244">Como resultado, você não pode usar `$null` para significar **nenhum valor de parâmetro**.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-244">As a result, you can't use `$null` to mean **no parameter value**.</span></span> <span data-ttu-id="6ccf4-245">Um valor de parâmetro de `$null` substitui o valor de parâmetro padrão.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-245">A parameter value of `$null` overrides the default parameter value.</span></span>

<span data-ttu-id="6ccf4-246">No entanto, como o PowerShell trata a `$null` variável como um espaço reservado, você pode usá-la em scripts como o seguinte, o que não funcionaria se `$null` fosse ignorado.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-246">However, because PowerShell treats the `$null` variable as a placeholder, you can use it in scripts like the following one, which wouldn't work if `$null` were ignored.</span></span>

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

### <a name="pid"></a><span data-ttu-id="6ccf4-247">$PID</span><span class="sxs-lookup"><span data-stu-id="6ccf4-247">$PID</span></span>

<span data-ttu-id="6ccf4-248">Contém o identificador do processo (PID) do processo que está hospedando a sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-248">Contains the process identifier (PID) of the process that is hosting the current PowerShell session.</span></span>

### <a name="profile"></a><span data-ttu-id="6ccf4-249">$PROFILE</span><span class="sxs-lookup"><span data-stu-id="6ccf4-249">$PROFILE</span></span>

<span data-ttu-id="6ccf4-250">Contém o caminho completo do perfil do PowerShell para o usuário atual e o aplicativo host atual.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-250">Contains the full path of the PowerShell profile for the current user and the current host application.</span></span> <span data-ttu-id="6ccf4-251">Você pode usar essa variável para representar o perfil em comandos.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-251">You can use this variable to represent the profile in commands.</span></span> <span data-ttu-id="6ccf4-252">Por exemplo, você pode usá-lo em um comando para determinar se um perfil foi criado:</span><span class="sxs-lookup"><span data-stu-id="6ccf4-252">For example, you can use it in a command to determine whether a profile has been created:</span></span>

```powershell
Test-Path $PROFILE
```

<span data-ttu-id="6ccf4-253">Ou você pode usá-lo em um comando para criar um perfil:</span><span class="sxs-lookup"><span data-stu-id="6ccf4-253">Or, you can use it in a command to create a profile:</span></span>

```powershell
New-Item -ItemType file -Path $PROFILE -Force
```

<span data-ttu-id="6ccf4-254">Você pode usá-lo em um comando para abrir o perfil no **notepad.exe**:</span><span class="sxs-lookup"><span data-stu-id="6ccf4-254">You can use it in a command to open the profile in **notepad.exe**:</span></span>

```powershell
notepad.exe $PROFILE
```

### <a name="psboundparameters"></a><span data-ttu-id="6ccf4-255">$PSBoundParameters</span><span class="sxs-lookup"><span data-stu-id="6ccf4-255">$PSBoundParameters</span></span>

<span data-ttu-id="6ccf4-256">Contém um dicionário dos parâmetros que são passados para um script ou função e seus valores atuais.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-256">Contains a dictionary of the parameters that are passed to a script or function and their current values.</span></span> <span data-ttu-id="6ccf4-257">Essa variável tem um valor somente em um escopo em que os parâmetros são declarados, como um script ou uma função.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-257">This variable has a value only in a scope where parameters are declared, such as a script or function.</span></span> <span data-ttu-id="6ccf4-258">Você pode usá-lo para exibir ou alterar os valores atuais dos parâmetros ou para passar valores de parâmetro para outro script ou função.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-258">You can use it to display or change the current values of parameters or to pass parameter values to another script or function.</span></span>

<span data-ttu-id="6ccf4-259">Neste exemplo, a função **test2** passa o `$PSBoundParameters` para a função **Test1** .</span><span class="sxs-lookup"><span data-stu-id="6ccf4-259">In this example, the **Test2** function passes the `$PSBoundParameters` to the **Test1** function.</span></span> <span data-ttu-id="6ccf4-260">Os `$PSBoundParameters` são exibidos no formato de **chave** e **valor**.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-260">The `$PSBoundParameters` are displayed in the format of **Key** and **Value**.</span></span>

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

### <a name="pscmdlet"></a><span data-ttu-id="6ccf4-261">$PSCmdlet</span><span class="sxs-lookup"><span data-stu-id="6ccf4-261">$PSCmdlet</span></span>

<span data-ttu-id="6ccf4-262">Contém um objeto que representa o cmdlet ou a função avançada que está sendo executada.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-262">Contains an object that represents the cmdlet or advanced function that's being run.</span></span>

<span data-ttu-id="6ccf4-263">Você pode usar as propriedades e os métodos do objeto no seu cmdlet ou código de função para responder às condições de uso.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-263">You can use the properties and methods of the object in your cmdlet or function code to respond to the conditions of use.</span></span> <span data-ttu-id="6ccf4-264">Por exemplo, a propriedade **ParameterSetName** contém o nome do conjunto de parâmetros que está sendo usado, e o método **ShouldProcess** adiciona os parâmetros **WhatIf** e **Confirm** ao cmdlet dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-264">For example, the **ParameterSetName** property contains the name of the parameter set that's being used, and the **ShouldProcess** method adds the **WhatIf** and **Confirm** parameters to the cmdlet dynamically.</span></span>

<span data-ttu-id="6ccf4-265">Para obter mais informações sobre a `$PSCmdlet` variável automática, consulte [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md) e [about_Functions_Advanced](about_Functions_Advanced.md).</span><span class="sxs-lookup"><span data-stu-id="6ccf4-265">For more information about the `$PSCmdlet` automatic variable, see [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md) and [about_Functions_Advanced](about_Functions_Advanced.md).</span></span>

### <a name="pscommandpath"></a><span data-ttu-id="6ccf4-266">$PSCommandPath</span><span class="sxs-lookup"><span data-stu-id="6ccf4-266">$PSCommandPath</span></span>

<span data-ttu-id="6ccf4-267">Contém o caminho completo e o nome de arquivo do script que está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-267">Contains the full path and file name of the script that's being run.</span></span> <span data-ttu-id="6ccf4-268">Essa variável é válida em todos os scripts.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-268">This variable is valid in all scripts.</span></span>

### <a name="psculture"></a><span data-ttu-id="6ccf4-269">$PSCulture</span><span class="sxs-lookup"><span data-stu-id="6ccf4-269">$PSCulture</span></span>

<span data-ttu-id="6ccf4-270">A partir do PowerShell 7, `$PSCulture` reflete a cultura do runspace do PowerShell atual (sessão).</span><span class="sxs-lookup"><span data-stu-id="6ccf4-270">Beginning in PowerShell 7, `$PSCulture` reflects the culture of the current PowerShell runspace (session).</span></span> <span data-ttu-id="6ccf4-271">Se a cultura for alterada em um runspace do PowerShell, o `$PSCulture` valor desse runspace será atualizado.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-271">If the culture is changed in a PowerShell runspace, the `$PSCulture` value for that runspace is updated.</span></span>

<span data-ttu-id="6ccf4-272">A cultura determina o formato de exibição de itens, como números, moeda e datas, e é armazenado em um objeto **System. Globalization. CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="6ccf4-272">The culture determines the display format of items such as numbers, currency, and dates, and is stored in a **System.Globalization.CultureInfo** object.</span></span> <span data-ttu-id="6ccf4-273">Use `Get-Culture` para exibir a cultura do computador.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-273">Use `Get-Culture` to display the computer's culture.</span></span> <span data-ttu-id="6ccf4-274">`$PSCulture` contém o valor da propriedade de **nome** .</span><span class="sxs-lookup"><span data-stu-id="6ccf4-274">`$PSCulture` contains the **Name** property's value.</span></span>

### <a name="psdebugcontext"></a><span data-ttu-id="6ccf4-275">$PSDebugContext</span><span class="sxs-lookup"><span data-stu-id="6ccf4-275">$PSDebugContext</span></span>

<span data-ttu-id="6ccf4-276">Durante a depuração, essa variável contém informações sobre o ambiente de depuração.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-276">While debugging, this variable contains information about the debugging environment.</span></span> <span data-ttu-id="6ccf4-277">Caso contrário, ele contém um valor **nulo** .</span><span class="sxs-lookup"><span data-stu-id="6ccf4-277">Otherwise, it contains a **null** value.</span></span> <span data-ttu-id="6ccf4-278">Como resultado, você pode usá-lo para indicar se o depurador tem controle.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-278">As a result, you can use it to indicate whether the debugger has control.</span></span> <span data-ttu-id="6ccf4-279">Quando preenchido, ele contém um objeto **PSDebugContext** que tem **pontos de interrupção** e propriedades **InvocationInfo** .</span><span class="sxs-lookup"><span data-stu-id="6ccf4-279">When populated, it contains a **PsDebugContext** object that has **Breakpoints** and **InvocationInfo** properties.</span></span> <span data-ttu-id="6ccf4-280">A propriedade **InvocationInfo** tem várias propriedades úteis, incluindo a propriedade **Location** .</span><span class="sxs-lookup"><span data-stu-id="6ccf4-280">The **InvocationInfo** property has several useful properties, including the **Location** property.</span></span> <span data-ttu-id="6ccf4-281">A propriedade **Location** indica o caminho do script que está sendo depurado.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-281">The **Location** property indicates the path of the script that is being debugged.</span></span>

### <a name="pshome"></a><span data-ttu-id="6ccf4-282">$PSHOME</span><span class="sxs-lookup"><span data-stu-id="6ccf4-282">$PSHOME</span></span>

<span data-ttu-id="6ccf4-283">Contém o caminho completo do diretório de instalação do PowerShell, normalmente, `$env:windir\System32\PowerShell\v1.0` em sistemas Windows.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-283">Contains the full path of the installation directory for PowerShell, typically, `$env:windir\System32\PowerShell\v1.0` in Windows systems.</span></span> <span data-ttu-id="6ccf4-284">Você pode usar essa variável nos caminhos de arquivos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-284">You can use this variable in the paths of PowerShell files.</span></span> <span data-ttu-id="6ccf4-285">Por exemplo, o comando a seguir pesquisa os tópicos de ajuda conceitual para a **variável** de palavra:</span><span class="sxs-lookup"><span data-stu-id="6ccf4-285">For example, the following command searches the conceptual Help topics for the word **variable**:</span></span>

```powershell
Select-String -Pattern Variable -Path $pshome\*.txt
```

### <a name="psitem"></a><span data-ttu-id="6ccf4-286">$PSItem</span><span class="sxs-lookup"><span data-stu-id="6ccf4-286">$PSItem</span></span>

<span data-ttu-id="6ccf4-287">Mesmo que `$_`.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-287">Same as `$_`.</span></span> <span data-ttu-id="6ccf4-288">Contém o objeto atual no objeto de pipeline.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-288">Contains the current object in the pipeline object.</span></span> <span data-ttu-id="6ccf4-289">Você pode usar essa variável em comandos que executam uma ação em cada objeto ou em objetos selecionados em um pipeline.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-289">You can use this variable in commands that perform an action on every object or on selected objects in a pipeline.</span></span>

### <a name="psscriptroot"></a><span data-ttu-id="6ccf4-290">$PSScriptRoot</span><span class="sxs-lookup"><span data-stu-id="6ccf4-290">$PSScriptRoot</span></span>

<span data-ttu-id="6ccf4-291">Contém o diretório do qual um script está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-291">Contains the directory from which a script is being run.</span></span>

<span data-ttu-id="6ccf4-292">No PowerShell 2,0, essa variável é válida somente em módulos de script ( `.psm1` ).</span><span class="sxs-lookup"><span data-stu-id="6ccf4-292">In PowerShell 2.0, this variable is valid only in script modules (`.psm1`).</span></span>
<span data-ttu-id="6ccf4-293">A partir do PowerShell 3,0, ele é válido em todos os scripts.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-293">Beginning in PowerShell 3.0, it's valid in all scripts.</span></span>

### <a name="pssenderinfo"></a><span data-ttu-id="6ccf4-294">$PSSenderInfo</span><span class="sxs-lookup"><span data-stu-id="6ccf4-294">$PSSenderInfo</span></span>

<span data-ttu-id="6ccf4-295">Contém informações sobre o usuário que iniciou a PSSession, incluindo a identidade do usuário e o fuso horário do computador de origem.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-295">Contains information about the user who started the PSSession, including the user identity and the time zone of the originating computer.</span></span> <span data-ttu-id="6ccf4-296">Essa variável está disponível somente em PSSessions.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-296">This variable is available only in PSSessions.</span></span>

<span data-ttu-id="6ccf4-297">A `$PSSenderInfo` variável inclui uma propriedade configurável pelo usuário, **ApplicationArguments**, que, por padrão, contém apenas o `$PSVersionTable` da sessão de origem.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-297">The `$PSSenderInfo` variable includes a user-configurable property, **ApplicationArguments**, that by default, contains only the `$PSVersionTable` from the originating session.</span></span> <span data-ttu-id="6ccf4-298">Para adicionar dados à propriedade **ApplicationArguments** , use o parâmetro **ApplicationArguments** do `New-PSSessionOption` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-298">To add data to the **ApplicationArguments** property, use the **ApplicationArguments** parameter of the `New-PSSessionOption` cmdlet.</span></span>

### <a name="psuiculture"></a><span data-ttu-id="6ccf4-299">$PSUICulture</span><span class="sxs-lookup"><span data-stu-id="6ccf4-299">$PSUICulture</span></span>

<span data-ttu-id="6ccf4-300">Contém o nome da cultura da interface do usuário que está atualmente em uso no sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-300">Contains the name of the user interface (UI) culture that's currently in use in the operating system.</span></span> <span data-ttu-id="6ccf4-301">A cultura da interface do usuário determina quais cadeias de caracteres de texto são usadas para elementos de interface do usuário, como menus e mensagens.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-301">The UI culture determines which text strings are used for user interface elements, such as menus and messages.</span></span> <span data-ttu-id="6ccf4-302">Esse é o valor da propriedade **System.Globalization.CultureInfo.CurrentUICulture.Name** do sistema.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-302">This is the value of the **System.Globalization.CultureInfo.CurrentUICulture.Name** property of the system.</span></span> <span data-ttu-id="6ccf4-303">Para obter o objeto **System. Globalization. CultureInfo** do sistema, use o `Get-UICulture` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-303">To get the **System.Globalization.CultureInfo** object for the system, use the `Get-UICulture` cmdlet.</span></span>

### <a name="psversiontable"></a><span data-ttu-id="6ccf4-304">$PSVersionTable</span><span class="sxs-lookup"><span data-stu-id="6ccf4-304">$PSVersionTable</span></span>

<span data-ttu-id="6ccf4-305">Contém uma tabela de hash somente leitura que exibe detalhes sobre a versão do PowerShell que está sendo executada na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-305">Contains a read-only hash table that displays details about the version of PowerShell that is running in the current session.</span></span> <span data-ttu-id="6ccf4-306">A tabela inclui os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="6ccf4-306">The table includes the following items:</span></span>

| <span data-ttu-id="6ccf4-307">Propriedade</span><span class="sxs-lookup"><span data-stu-id="6ccf4-307">Property</span></span>                  | <span data-ttu-id="6ccf4-308">Descrição</span><span class="sxs-lookup"><span data-stu-id="6ccf4-308">Description</span></span>                                   |
| ------------------------- | --------------------------------------------- |
| <span data-ttu-id="6ccf4-309">**PSVersion**</span><span class="sxs-lookup"><span data-stu-id="6ccf4-309">**PSVersion**</span></span>             | <span data-ttu-id="6ccf4-310">O número de versão do PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ccf4-310">The PowerShell version number</span></span>                 |
| <span data-ttu-id="6ccf4-311">**PSEdition**</span><span class="sxs-lookup"><span data-stu-id="6ccf4-311">**PSEdition**</span></span>             | <span data-ttu-id="6ccf4-312">Esta propriedade tem o valor de ' Desktop ' para</span><span class="sxs-lookup"><span data-stu-id="6ccf4-312">This property has the value of 'Desktop' for</span></span>  |
|                           | <span data-ttu-id="6ccf4-313">PowerShell 4 e inferior, bem como o PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ccf4-313">PowerShell 4 and below as well as PowerShell</span></span>  |
|                           | <span data-ttu-id="6ccf4-314">5,1 em edições com recursos completos do Windows.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-314">5.1 on full-featured Windows editions.</span></span>        |
|                           | <span data-ttu-id="6ccf4-315">Esta propriedade tem o valor de ' Core ' para</span><span class="sxs-lookup"><span data-stu-id="6ccf4-315">This property has the value of 'Core' for</span></span>     |
|                           | <span data-ttu-id="6ccf4-316">PowerShell 6 e superior, bem como o PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ccf4-316">PowerShell 6 and above as well as PowerShell</span></span>  |
|                           | <span data-ttu-id="6ccf4-317">PowerShell 5,1 em edições de superfície reduzida</span><span class="sxs-lookup"><span data-stu-id="6ccf4-317">PowerShell 5.1 on reduced-footprint editions</span></span>  |
|                           | <span data-ttu-id="6ccf4-318">como o Windows nano Server ou o Windows IoT.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-318">like Windows Nano Server or Windows IoT.</span></span>      |
| <span data-ttu-id="6ccf4-319">**GitCommitId**</span><span class="sxs-lookup"><span data-stu-id="6ccf4-319">**GitCommitId**</span></span>           | <span data-ttu-id="6ccf4-320">A ID de confirmação dos arquivos de origem, no GitHub,</span><span class="sxs-lookup"><span data-stu-id="6ccf4-320">The commit Id of the source files, in GitHub,</span></span> |
| <span data-ttu-id="6ccf4-321">**SO**</span><span class="sxs-lookup"><span data-stu-id="6ccf4-321">**OS**</span></span>                    | <span data-ttu-id="6ccf4-322">Descrição do sistema operacional que</span><span class="sxs-lookup"><span data-stu-id="6ccf4-322">Description of the operating system that</span></span>      |
|                           | <span data-ttu-id="6ccf4-323">O PowerShell está sendo executado no.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-323">PowerShell is running on.</span></span>                     |
| <span data-ttu-id="6ccf4-324">**Plataforma**</span><span class="sxs-lookup"><span data-stu-id="6ccf4-324">**Platform**</span></span>              | <span data-ttu-id="6ccf4-325">Plataforma em que o sistema operacional está em execução</span><span class="sxs-lookup"><span data-stu-id="6ccf4-325">Platform that the operating system is running</span></span> |
|                           | <span data-ttu-id="6ccf4-326">em.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-326">on.</span></span> <span data-ttu-id="6ccf4-327">O valor no Linux e no macOS é **Unix**.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-327">The value on Linux and macOS is **Unix**.</span></span> |
|                           | <span data-ttu-id="6ccf4-328">Veja `$IsMacOs` e `$IsLinux`.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-328">See `$IsMacOs` and `$IsLinux`.</span></span>                |
| <span data-ttu-id="6ccf4-329">**PSCompatibleVersions**</span><span class="sxs-lookup"><span data-stu-id="6ccf4-329">**PSCompatibleVersions**</span></span>  | <span data-ttu-id="6ccf4-330">Versões do PowerShell que são compatíveis</span><span class="sxs-lookup"><span data-stu-id="6ccf4-330">Versions of PowerShell that are compatible</span></span>    |
|                           | <span data-ttu-id="6ccf4-331">com a versão atual</span><span class="sxs-lookup"><span data-stu-id="6ccf4-331">with the current version</span></span>                      |
| <span data-ttu-id="6ccf4-332">**PSRemotingProtocolVersion**</span><span class="sxs-lookup"><span data-stu-id="6ccf4-332">**PSRemotingProtocolVersion**</span></span> | <span data-ttu-id="6ccf4-333">A versão do PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="6ccf4-333">The version of the PowerShell remote</span></span>      |
|                           | <span data-ttu-id="6ccf4-334">Protocolo de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-334">management protocol.</span></span>                          |
| <span data-ttu-id="6ccf4-335">**SerializationVersion**</span><span class="sxs-lookup"><span data-stu-id="6ccf4-335">**SerializationVersion**</span></span>  | <span data-ttu-id="6ccf4-336">A versão do método de serialização</span><span class="sxs-lookup"><span data-stu-id="6ccf4-336">The version of the serialization method</span></span>       |
| <span data-ttu-id="6ccf4-337">**WSManStackVersion**</span><span class="sxs-lookup"><span data-stu-id="6ccf4-337">**WSManStackVersion**</span></span>     | <span data-ttu-id="6ccf4-338">O número de versão da pilha de WS-Management</span><span class="sxs-lookup"><span data-stu-id="6ccf4-338">The version number of the WS-Management stack</span></span> |

### <a name="pwd"></a><span data-ttu-id="6ccf4-339">$PWD</span><span class="sxs-lookup"><span data-stu-id="6ccf4-339">$PWD</span></span>

<span data-ttu-id="6ccf4-340">Contém um objeto Path que representa o caminho completo do local do diretório atual para o runspace do PowerShell atual.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-340">Contains a path object that represents the full path of the current directory location for the current PowerShell runspace.</span></span>

> [!NOTE]
> <span data-ttu-id="6ccf4-341">O PowerShell dá suporte a vários Runspaces por processo.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-341">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="6ccf4-342">Cada runspace tem seu próprio _diretório atual_.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-342">Each runspace has its own _current directory_.</span></span> <span data-ttu-id="6ccf4-343">Isso não é o mesmo que o diretório atual do processo: `[System.Environment]::CurrentDirectory` .</span><span class="sxs-lookup"><span data-stu-id="6ccf4-343">This is not the same as the current directory of the process: `[System.Environment]::CurrentDirectory`.</span></span>

### <a name="sender"></a><span data-ttu-id="6ccf4-344">$Sender</span><span class="sxs-lookup"><span data-stu-id="6ccf4-344">$Sender</span></span>

<span data-ttu-id="6ccf4-345">Contém o objeto que gerou este evento.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-345">Contains the object that generated this event.</span></span> <span data-ttu-id="6ccf4-346">Essa variável é populada somente dentro do bloco de ação de um comando de registro de evento.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-346">This variable is populated only within the Action block of an event registration command.</span></span> <span data-ttu-id="6ccf4-347">O valor dessa variável também pode ser encontrado na propriedade Sender do objeto **PSEventArgs** que `Get-Event` retorna.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-347">The value of this variable can also be found in the Sender property of the **PSEventArgs** object that `Get-Event` returns.</span></span>

### <a name="shellid"></a><span data-ttu-id="6ccf4-348">$ShellId</span><span class="sxs-lookup"><span data-stu-id="6ccf4-348">$ShellId</span></span>

<span data-ttu-id="6ccf4-349">Contém o identificador do shell atual.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-349">Contains the identifier of the current shell.</span></span>

### <a name="stacktrace"></a><span data-ttu-id="6ccf4-350">$StackTrace</span><span class="sxs-lookup"><span data-stu-id="6ccf4-350">$StackTrace</span></span>

<span data-ttu-id="6ccf4-351">Contém um rastreamento de pilha para o erro mais recente.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-351">Contains a stack trace for the most recent error.</span></span>

### <a name="switch"></a><span data-ttu-id="6ccf4-352">$switch</span><span class="sxs-lookup"><span data-stu-id="6ccf4-352">$switch</span></span>

<span data-ttu-id="6ccf4-353">Contém o enumerador não os valores resultantes de uma `Switch` instrução.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-353">Contains the enumerator not the resulting values of a `Switch` statement.</span></span> <span data-ttu-id="6ccf4-354">A `$switch` variável existe somente enquanto a `Switch` instrução está em execução; ela é excluída quando a `switch` instrução conclui a execução.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-354">The `$switch` variable exists only while the `Switch` statement is running; it's deleted when the `switch` statement completes execution.</span></span> <span data-ttu-id="6ccf4-355">Para obter mais informações, consulte [about_Switch](about_Switch.md).</span><span class="sxs-lookup"><span data-stu-id="6ccf4-355">For more information, see [about_Switch](about_Switch.md).</span></span>

<span data-ttu-id="6ccf4-356">Enumeradores contêm propriedades e métodos que você pode usar para recuperar valores de loop e alterar a iteração do loop atual.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-356">Enumerators contain properties and methods you can use to retrieve loop values and change the current loop iteration.</span></span> <span data-ttu-id="6ccf4-357">Para obter mais informações, consulte [usando enumeradores](#using-enumerators).</span><span class="sxs-lookup"><span data-stu-id="6ccf4-357">For more information, see [Using Enumerators](#using-enumerators).</span></span>

### <a name="this"></a><span data-ttu-id="6ccf4-358">$this</span><span class="sxs-lookup"><span data-stu-id="6ccf4-358">$this</span></span>

<span data-ttu-id="6ccf4-359">Em um bloco de script que define uma propriedade de script ou um método de script, a `$this` variável refere-se ao objeto que está sendo estendido.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-359">In a script block that defines a script property or script method, the `$this` variable refers to the object that is being extended.</span></span>

<span data-ttu-id="6ccf4-360">Em uma classe personalizada, a `$this` variável refere-se ao próprio objeto de classe, permitindo o acesso a propriedades e métodos definidos na classe.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-360">In a custom class, the `$this` variable refers to the class object itself allowing access to properties and methods defined in the class.</span></span>

### <a name="true"></a><span data-ttu-id="6ccf4-361">$true</span><span class="sxs-lookup"><span data-stu-id="6ccf4-361">$true</span></span>

<span data-ttu-id="6ccf4-362">Contém **true**.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-362">Contains **True**.</span></span> <span data-ttu-id="6ccf4-363">Você pode usar essa variável para representar **true** em comandos e scripts.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-363">You can use this variable to represent **True** in commands and scripts.</span></span>

## <a name="using-enumerators"></a><span data-ttu-id="6ccf4-364">Usando enumeradores</span><span class="sxs-lookup"><span data-stu-id="6ccf4-364">Using Enumerators</span></span>

<span data-ttu-id="6ccf4-365">As `$input` `$foreach` variáveis, e `$switch` são todos os enumeradores usados para iterar pelos valores processados pelo bloco de código que o contém.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-365">The `$input`, `$foreach`, and `$switch` variables are all enumerators used to iterate through the values processed by their containing code block.</span></span>

<span data-ttu-id="6ccf4-366">Um enumerador contém propriedades e métodos que você pode usar para avançar ou redefinir a iteração ou recuperar valores de iteração.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-366">An enumerator contains properties and methods you can use to advance or reset iteration, or retrieve iteration values.</span></span> <span data-ttu-id="6ccf4-367">Os enumeradores de manipulação direta não são considerados práticas recomendadas.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-367">Directly manipulating enumerators isn't considered best practice.</span></span>

- <span data-ttu-id="6ccf4-368">Em loops, as palavras-chave de controle de fluxo [quebram](about_Break.md) e [continuam](about_Continue.md) como preferíveis.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-368">Within loops, flow control keywords [break](about_Break.md) and [continue](about_Continue.md) should be preferred.</span></span>
- <span data-ttu-id="6ccf4-369">Em funções que aceitam a entrada de pipeline, é recomendável usar parâmetros com os atributos **ValueFromPipeline** ou **valueFromPipelineByPropertyName** .</span><span class="sxs-lookup"><span data-stu-id="6ccf4-369">Within functions that accept pipeline input, it's best practice to use Parameters with the **ValueFromPipeline** or **ValueFromPipelineByPropertyName** attributes.</span></span>

  <span data-ttu-id="6ccf4-370">Para obter mais informações, consulte [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="6ccf4-370">For more information, see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

### <a name="movenext"></a><span data-ttu-id="6ccf4-371">MoveNext</span><span class="sxs-lookup"><span data-stu-id="6ccf4-371">MoveNext</span></span>

<span data-ttu-id="6ccf4-372">O método [MoveNext](/dotnet/api/system.collections.ienumerator.movenext) avança o enumerador para o próximo elemento da coleção.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-372">The [MoveNext](/dotnet/api/system.collections.ienumerator.movenext) method advances the enumerator to the next element of the collection.</span></span> <span data-ttu-id="6ccf4-373">**MoveNext** retornará **true** se o enumerador tiver sido avançado com êxito; **false** se o enumerador tiver passado o final da coleção.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-373">**MoveNext** returns **True** if the enumerator was successfully advanced, **False** if the enumerator has passed the end of the collection.</span></span>

> [!NOTE]
> <span data-ttu-id="6ccf4-374">O valor **booliano** retornou meu **MoveNext** é enviado para o fluxo de saída.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-374">The **Boolean** value returned my **MoveNext** is sent to the output stream.</span></span>
> <span data-ttu-id="6ccf4-375">Você pode suprimir a saída ao typecasting-la `[void]` ou canaliza-la para [out-null](xref:Microsoft.PowerShell.Core.Out-Null).</span><span class="sxs-lookup"><span data-stu-id="6ccf4-375">You can suppress the output by typecasting it to `[void]` or piping it to [Out-Null](xref:Microsoft.PowerShell.Core.Out-Null).</span></span>
>
> ```powershell
> $input.MoveNext() | Out-Null
> ```
>
> ```powershell
> [void]$input.MoveNext()
> ```

### <a name="reset"></a><span data-ttu-id="6ccf4-376">Redefinir</span><span class="sxs-lookup"><span data-stu-id="6ccf4-376">Reset</span></span>

<span data-ttu-id="6ccf4-377">O método [Reset](/dotnet/api/system.collections.ienumerator.reset) define o enumerador para sua posição inicial, que é **antes** do primeiro elemento na coleção.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-377">The [Reset](/dotnet/api/system.collections.ienumerator.reset) method sets the enumerator to its initial position, which is **before** the first element in the collection.</span></span>

### <a name="current"></a><span data-ttu-id="6ccf4-378">Current</span><span class="sxs-lookup"><span data-stu-id="6ccf4-378">Current</span></span>

<span data-ttu-id="6ccf4-379">A propriedade [Current](/dotnet/api/system.collections.ienumerator.current) Obtém o elemento na coleção, ou pipeline, na posição atual do enumerador.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-379">The [Current](/dotnet/api/system.collections.ienumerator.current) property gets the element in the collection, or pipeline, at the current position of the enumerator.</span></span>

<span data-ttu-id="6ccf4-380">A propriedade **Current** continua retornando a mesma propriedade até que **MoveNext** seja chamado.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-380">The **Current** property continues to return the same property until **MoveNext** is called.</span></span>

## <a name="examples"></a><span data-ttu-id="6ccf4-381">Exemplos</span><span class="sxs-lookup"><span data-stu-id="6ccf4-381">Examples</span></span>

### <a name="example-1-using-the-input-variable"></a><span data-ttu-id="6ccf4-382">Exemplo 1: usando a variável $input</span><span class="sxs-lookup"><span data-stu-id="6ccf4-382">Example 1: Using the $input variable</span></span>

<span data-ttu-id="6ccf4-383">No exemplo a seguir, o acesso à `$input` variável limpa a variável até a próxima vez que o bloco de processo for executado.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-383">In the following example, accessing the `$input` variable clears the variable until the next time the process block executes.</span></span> <span data-ttu-id="6ccf4-384">O uso do método **Redefinir** redefine a `$input` variável para o valor do pipeline atual.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-384">Using the **Reset** method resets the `$input` variable to the current pipeline value.</span></span>

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

<span data-ttu-id="6ccf4-385">O bloco de processo avança automaticamente a `$input` variável mesmo se você não acessá-la.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-385">The process block automatically advances the `$input` variable even if you don't access it.</span></span>

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

### <a name="example-2-using-input-outside-the-process-block"></a><span data-ttu-id="6ccf4-386">Exemplo 2: usando $input fora do bloco de processo</span><span class="sxs-lookup"><span data-stu-id="6ccf4-386">Example 2: Using $input outside the process block</span></span>

<span data-ttu-id="6ccf4-387">Fora do bloco de processo, a `$input` variável representa todos os valores canalizados para a função.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-387">Outside of the process block the `$input` variable represents all the values piped into the function.</span></span>

- <span data-ttu-id="6ccf4-388">O acesso à `$input` variável limpa todos os valores.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-388">Accessing the `$input` variable clears all values.</span></span>
- <span data-ttu-id="6ccf4-389">O método de **redefinição** redefine a coleção inteira.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-389">The **Reset** method resets the entire collection.</span></span>
- <span data-ttu-id="6ccf4-390">A propriedade **atual** nunca é populada.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-390">The **Current** property is never populated.</span></span>
- <span data-ttu-id="6ccf4-391">O método **MoveNext** retorna false porque a coleção não pode ser avançada.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-391">The **MoveNext** method returns false because the collection can't be advanced.</span></span>
  - <span data-ttu-id="6ccf4-392">Chamar **MoveNext** limpa a `$input` variável.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-392">Calling **MoveNext** clears out the `$input` variable.</span></span>

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

### <a name="example-3-using-the-inputcurrent-property"></a><span data-ttu-id="6ccf4-393">Exemplo 3: usando o $input. Propriedade atual</span><span class="sxs-lookup"><span data-stu-id="6ccf4-393">Example 3: Using the $input.Current property</span></span>

<span data-ttu-id="6ccf4-394">Usando a propriedade **Current** , o valor do pipeline atual pode ser acessado várias vezes sem usar o método **Reset** .</span><span class="sxs-lookup"><span data-stu-id="6ccf4-394">By using the **Current** property, the current pipeline value can be accessed multiple times without using the **Reset** method.</span></span> <span data-ttu-id="6ccf4-395">O bloco de processo não chama automaticamente o método **MoveNext** .</span><span class="sxs-lookup"><span data-stu-id="6ccf4-395">The process block doesn't automatically call the **MoveNext** method.</span></span>

<span data-ttu-id="6ccf4-396">A propriedade **atual** nunca será preenchida a menos que você chame explicitamente **MoveNext**.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-396">The **Current** property will never be populated unless you explicitly call **MoveNext**.</span></span> <span data-ttu-id="6ccf4-397">A propriedade **Current** pode ser acessada várias vezes dentro do bloco Process sem limpar seu valor.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-397">The **Current** property can be accessed multiple times inside the process block without clearing its value.</span></span>

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

### <a name="example-4-using-the-foreach-variable"></a><span data-ttu-id="6ccf4-398">Exemplo 4: usando a variável $foreach</span><span class="sxs-lookup"><span data-stu-id="6ccf4-398">Example 4: Using the $foreach variable</span></span>

<span data-ttu-id="6ccf4-399">Ao contrário da `$input` variável, a `$foreach` variável sempre representa todos os itens na coleção quando acessados diretamente.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-399">Unlike the `$input` variable, the `$foreach` variable always represents all items in the collection when accessed directly.</span></span> <span data-ttu-id="6ccf4-400">Use a propriedade **Current** para acessar o elemento da coleção atual e os métodos **Reset** e **MoveNext** para alterar seu valor.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-400">Use the **Current** property to access the current collection element, and the **Reset** and **MoveNext** methods to change its value.</span></span>

> [!NOTE]
> <span data-ttu-id="6ccf4-401">Cada iteração do `foreach` loop chamará automaticamente o método **MoveNext** .</span><span class="sxs-lookup"><span data-stu-id="6ccf4-401">Each iteration of the `foreach` loop will automatically call the **MoveNext** method.</span></span>

<span data-ttu-id="6ccf4-402">O loop a seguir é executado duas vezes.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-402">The following loop only executes twice.</span></span> <span data-ttu-id="6ccf4-403">Na segunda iteração, a coleção é movida para o terceiro elemento antes da conclusão da iteração.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-403">In the second iteration, the collection is moved to the third element before the iteration is complete.</span></span> <span data-ttu-id="6ccf4-404">Após a segunda iteração, agora não há mais valores para iterar e o loop é encerrado.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-404">After the second iteration, there are now no more values to iterate, and the loop terminates.</span></span>

<span data-ttu-id="6ccf4-405">A propriedade **MoveNext** não afeta a variável escolhida para iterar pela coleção ( `$Num` ).</span><span class="sxs-lookup"><span data-stu-id="6ccf4-405">The **MoveNext** property doesn't affect the variable chosen to iterate through the collection (`$Num`).</span></span>

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

<span data-ttu-id="6ccf4-406">O uso do método **Redefinir** redefine o elemento atual na coleção.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-406">Using the **Reset** method resets the current element in the collection.</span></span> <span data-ttu-id="6ccf4-407">O exemplo a seguir faz um loop pelos dois primeiros elementos **duas vezes** porque o método **Reset** é chamado.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-407">The following example loops through the first two elements **twice** because the **Reset** method is called.</span></span> <span data-ttu-id="6ccf4-408">Após os dois primeiros loops, a `if` instrução falha e o loop é iterado por todos os três elementos normalmente.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-408">After the first two loops, the `if` statement fails and the loop iterates through all three elements normally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6ccf4-409">Isso pode resultar em um loop infinito.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-409">This could result in an infinite loop.</span></span>

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

### <a name="example-5-using-the-switch-variable"></a><span data-ttu-id="6ccf4-410">Exemplo 5: usando a variável $switch</span><span class="sxs-lookup"><span data-stu-id="6ccf4-410">Example 5: Using the $switch variable</span></span>

<span data-ttu-id="6ccf4-411">A `$switch` variável tem exatamente as mesmas regras que a `$foreach` variável.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-411">The `$switch` variable has the exact same rules as the `$foreach` variable.</span></span>
<span data-ttu-id="6ccf4-412">O exemplo a seguir demonstra todos os conceitos de enumerador.</span><span class="sxs-lookup"><span data-stu-id="6ccf4-412">The following example demonstrates all the enumerator concepts.</span></span>

> [!NOTE]
> <span data-ttu-id="6ccf4-413">Observe como o caso não **avaliado** nunca é executado, mesmo que não haja `break` instrução após o método **MoveNext** .</span><span class="sxs-lookup"><span data-stu-id="6ccf4-413">Note how the **NotEvaluated** case is never executed, even though there's no `break` statement after the **MoveNext** method.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="6ccf4-414">Confira também</span><span class="sxs-lookup"><span data-stu-id="6ccf4-414">See also</span></span>

[<span data-ttu-id="6ccf4-415">about_Functions</span><span class="sxs-lookup"><span data-stu-id="6ccf4-415">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="6ccf4-416">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="6ccf4-416">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="6ccf4-417">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="6ccf4-417">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="6ccf4-418">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="6ccf4-418">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="6ccf4-419">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="6ccf4-419">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)

[<span data-ttu-id="6ccf4-420">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="6ccf4-420">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="6ccf4-421">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="6ccf4-421">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="6ccf4-422">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="6ccf4-422">about_Preference_Variables</span></span>](about_Preference_Variables.md)

[<span data-ttu-id="6ccf4-423">about_Splatting</span><span class="sxs-lookup"><span data-stu-id="6ccf4-423">about_Splatting</span></span>](about_Splatting.md)

[<span data-ttu-id="6ccf4-424">about_Variables</span><span class="sxs-lookup"><span data-stu-id="6ccf4-424">about_Variables</span></span>](about_Variables.md)
