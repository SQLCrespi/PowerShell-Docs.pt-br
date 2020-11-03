---
description: Descreve a `Prompt` função e demonstra como criar uma função personalizada `Prompt` .
keywords: powershell, cmdlet
Locale: en-US
ms.date: 04/15/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_prompts?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Prompts
ms.openlocfilehash: 3e1496c84fa528b4673a770b5b2777fc3d31dc34
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195500"
---
# <a name="about-prompts"></a><span data-ttu-id="3e237-104">Sobre os prompts</span><span class="sxs-lookup"><span data-stu-id="3e237-104">About Prompts</span></span>

## <a name="short-description"></a><span data-ttu-id="3e237-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="3e237-105">Short description</span></span>
<span data-ttu-id="3e237-106">Descreve a `Prompt` função e demonstra como criar uma função personalizada `Prompt` .</span><span class="sxs-lookup"><span data-stu-id="3e237-106">Describes the `Prompt` function and demonstrates how to create a custom `Prompt` function.</span></span>

## <a name="long-description"></a><span data-ttu-id="3e237-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="3e237-107">Long description</span></span>

<span data-ttu-id="3e237-108">O prompt de comando do PowerShell indica que o PowerShell está pronto para executar um comando:</span><span class="sxs-lookup"><span data-stu-id="3e237-108">The PowerShell command prompt indicates that PowerShell is ready to run a command:</span></span>

```
PS C:\>
```

<span data-ttu-id="3e237-109">O prompt do PowerShell é determinado pela `Prompt` função interna.</span><span class="sxs-lookup"><span data-stu-id="3e237-109">The PowerShell prompt is determined by the built-in `Prompt` function.</span></span> <span data-ttu-id="3e237-110">Você pode personalizar o prompt criando sua própria `Prompt` função e salvando-a em seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e237-110">You can customize the prompt by creating your own `Prompt` function and saving it in your PowerShell profile.</span></span>

## <a name="about-the-prompt-function"></a><span data-ttu-id="3e237-111">Sobre a função de prompt</span><span class="sxs-lookup"><span data-stu-id="3e237-111">About the Prompt function</span></span>

<span data-ttu-id="3e237-112">A `Prompt` função determina a aparência do prompt do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e237-112">The `Prompt` function determines the appearance of the PowerShell prompt.</span></span>
<span data-ttu-id="3e237-113">O PowerShell vem com uma função interna `Prompt` , mas você pode substituí-la definindo sua própria `Prompt` função.</span><span class="sxs-lookup"><span data-stu-id="3e237-113">PowerShell comes with a built-in `Prompt` function, but you can override it by defining your own `Prompt` function.</span></span>

<span data-ttu-id="3e237-114">A `Prompt` função tem a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="3e237-114">The `Prompt` function has the following syntax:</span></span>

```powershell
function Prompt { <function-body> }
```

<span data-ttu-id="3e237-115">A `Prompt` função deve retornar um objeto.</span><span class="sxs-lookup"><span data-stu-id="3e237-115">The `Prompt` function must return an object.</span></span> <span data-ttu-id="3e237-116">Como prática recomendada, retorne uma cadeia de caracteres ou um objeto formatado como uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="3e237-116">As a best practice, return a string or an object that is formatted as a string.</span></span> <span data-ttu-id="3e237-117">O comprimento máximo recomendado é de 80 caracteres.</span><span class="sxs-lookup"><span data-stu-id="3e237-117">The maximum recommended length is 80 characters.</span></span>

<span data-ttu-id="3e237-118">Por exemplo, a função a seguir `Prompt` retorna uma cadeia de caracteres "Olá, mundo" seguida por um colchete angular direito ( `>` ).</span><span class="sxs-lookup"><span data-stu-id="3e237-118">For example, the following `Prompt` function returns a "Hello, World" string followed by a  right angle bracket (`>`).</span></span>

```powershell
PS C:\> function prompt {"Hello, World > "}
Hello, World >
```

### <a name="getting-the-prompt-function"></a><span data-ttu-id="3e237-119">Obtendo a função prompt</span><span class="sxs-lookup"><span data-stu-id="3e237-119">Getting the Prompt function</span></span>

<span data-ttu-id="3e237-120">Para obter a `Prompt` função, use o `Get-Command` cmdlet ou use o `Get-Item` cmdlet na unidade de função.</span><span class="sxs-lookup"><span data-stu-id="3e237-120">To get the `Prompt` function, use the `Get-Command` cmdlet or use the `Get-Item` cmdlet in the Function drive.</span></span>

<span data-ttu-id="3e237-121">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3e237-121">For example:</span></span>

```powershell
PS C:\> Get-Command Prompt

CommandType     Name      ModuleName
-----------     ----      ----------
Function        prompt
```

<span data-ttu-id="3e237-122">Para obter o script que define o valor do prompt, use o método dot para obter a propriedade **scriptblock** da `Prompt` função.</span><span class="sxs-lookup"><span data-stu-id="3e237-122">To get the script that sets the value of the prompt, use the dot method to get the **ScriptBlock** property of the `Prompt` function.</span></span>

<span data-ttu-id="3e237-123">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3e237-123">For example:</span></span>

```powershell
(Get-Command Prompt).ScriptBlock
```

```Output
"PS $($executionContext.SessionState.Path.CurrentLocation)$('>' * ($nestedPromptLevel + 1)) "
# .Link
# https://go.microsoft.com/fwlink/?LinkID=225750
# .ExternalHelp System.Management.Automation.dll-help.xml
```

<span data-ttu-id="3e237-124">Como todas as funções, a `Prompt` função é armazenada na `Function:` unidade.</span><span class="sxs-lookup"><span data-stu-id="3e237-124">Like all functions, the `Prompt` function is stored in the `Function:` drive.</span></span>
<span data-ttu-id="3e237-125">Para exibir o script que cria a `Prompt` função atual, digite:</span><span class="sxs-lookup"><span data-stu-id="3e237-125">To display the script that creates the current `Prompt` function, type:</span></span>

```powershell
(Get-Item function:prompt).ScriptBlock
```

### <a name="the-default-prompt"></a><span data-ttu-id="3e237-126">O prompt padrão</span><span class="sxs-lookup"><span data-stu-id="3e237-126">The default prompt</span></span>

<span data-ttu-id="3e237-127">O prompt padrão aparece somente quando a `Prompt` função gera um erro ou não retorna um objeto.</span><span class="sxs-lookup"><span data-stu-id="3e237-127">The default prompt appears only when the `Prompt` function generates an error or does not return an object.</span></span>

<span data-ttu-id="3e237-128">O prompt padrão do PowerShell é:</span><span class="sxs-lookup"><span data-stu-id="3e237-128">The default PowerShell prompt is:</span></span>

```
PS>
```

<span data-ttu-id="3e237-129">Por exemplo, o comando a seguir define a `Prompt` função como `$null` , que é inválida.</span><span class="sxs-lookup"><span data-stu-id="3e237-129">For example, the following command sets the `Prompt` function to `$null`, which is invalid.</span></span> <span data-ttu-id="3e237-130">Como resultado, o prompt padrão é exibido.</span><span class="sxs-lookup"><span data-stu-id="3e237-130">As a result, the default prompt appears.</span></span>

```powershell
PS C:\> function prompt {$null}
PS>
```

<span data-ttu-id="3e237-131">Como o PowerShell é fornecido com um prompt interno, normalmente, você não vê o prompt padrão.</span><span class="sxs-lookup"><span data-stu-id="3e237-131">Because PowerShell comes with a built-in prompt, you usually do not see the default prompt.</span></span>

### <a name="built-in-prompt"></a><span data-ttu-id="3e237-132">Prompt interno</span><span class="sxs-lookup"><span data-stu-id="3e237-132">Built-in prompt</span></span>

<span data-ttu-id="3e237-133">O PowerShell inclui uma função interna `Prompt` .</span><span class="sxs-lookup"><span data-stu-id="3e237-133">PowerShell includes a built-in `Prompt` function.</span></span>

```powershell
function prompt {
    $(if (Test-Path variable:/PSDebugContext) { '[DBG]: ' }
      else { '' }) + 'PS ' + $(Get-Location) +
        $(if ($NestedPromptLevel -ge 1) { '>>' }) + '> '
}
```

<span data-ttu-id="3e237-134">A função usa o `Test-Path` cmdlet para determinar se a `$PSDebugContext` variável automática é populada.</span><span class="sxs-lookup"><span data-stu-id="3e237-134">The function uses the `Test-Path` cmdlet to determine whether the `$PSDebugContext` automatic variable is populated.</span></span> <span data-ttu-id="3e237-135">Se `$PSDebugContext` estiver populado, você estará no modo de depuração e `[DBG]:` será adicionado ao prompt da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="3e237-135">If `$PSDebugContext` is populated, you are in debugging mode, and `[DBG]:` is added to the prompt, as follows:</span></span>

```Output
[DBG]: PS C:\ps-test>
```

<span data-ttu-id="3e237-136">Se `$PSDebugContext` não for populado, a função será adicionada `PS` ao prompt.</span><span class="sxs-lookup"><span data-stu-id="3e237-136">If `$PSDebugContext` is not populated, the function adds `PS` to the prompt.</span></span>
<span data-ttu-id="3e237-137">E, a função usa o `Get-Location` cmdlet para obter o local do diretório do sistema de arquivos atual.</span><span class="sxs-lookup"><span data-stu-id="3e237-137">And, the function uses the `Get-Location` cmdlet to get the current file system directory location.</span></span> <span data-ttu-id="3e237-138">Em seguida, ele adiciona um colchete angular direito ( `>` ).</span><span class="sxs-lookup"><span data-stu-id="3e237-138">Then, it adds a right angle bracket (`>`).</span></span>

<span data-ttu-id="3e237-139">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3e237-139">For example:</span></span>

```Output
PS C:\ps-test>
```

<span data-ttu-id="3e237-140">Se você estiver em um prompt aninhado, a função adicionará dois colchetes angulares ( `>>` ) ao prompt.</span><span class="sxs-lookup"><span data-stu-id="3e237-140">If you are in a nested prompt, the function adds two angle brackets (`>>`) to the prompt.</span></span> <span data-ttu-id="3e237-141">(Você estará em um prompt aninhado se o valor da `$NestedPromptLevel` variável automática for maior que 1.)</span><span class="sxs-lookup"><span data-stu-id="3e237-141">(You are in a nested prompt if the value of the `$NestedPromptLevel` automatic variable is greater than 1.)</span></span>

<span data-ttu-id="3e237-142">Por exemplo, quando você estiver Depurando em um prompt aninhado, o prompt será semelhante ao seguinte prompt:</span><span class="sxs-lookup"><span data-stu-id="3e237-142">For example, when you are debugging in a nested prompt, the prompt resembles the following prompt:</span></span>

```Output
[DBG] PS C:\ps-test>>>
```

### <a name="changes-to-the-prompt"></a><span data-ttu-id="3e237-143">Alterações no prompt</span><span class="sxs-lookup"><span data-stu-id="3e237-143">Changes to the prompt</span></span>

<span data-ttu-id="3e237-144">O `Enter-PSSession` cmdlet precede o nome do computador remoto para a `Prompt` função atual.</span><span class="sxs-lookup"><span data-stu-id="3e237-144">The `Enter-PSSession` cmdlet prepends the name of the remote computer to the current `Prompt` function.</span></span> <span data-ttu-id="3e237-145">Quando você usa o `Enter-PSSession` cmdlet para iniciar uma sessão com um computador remoto, o prompt de comando é alterado para incluir o nome do computador remoto.</span><span class="sxs-lookup"><span data-stu-id="3e237-145">When you use the `Enter-PSSession` cmdlet to start a session with a remote computer, the command prompt changes to include the name of the remote computer.</span></span> <span data-ttu-id="3e237-146">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3e237-146">For example:</span></span>

```Output
PS Hello, World> Enter-PSSession Server01
[Server01]: PS Hello, World>
```

<span data-ttu-id="3e237-147">Outros aplicativos host do PowerShell e shells alternativos podem ter seus próprios prompts de comando personalizados.</span><span class="sxs-lookup"><span data-stu-id="3e237-147">Other PowerShell host applications and alternate shells might have their own custom command prompts.</span></span>

<span data-ttu-id="3e237-148">Para obter mais informações sobre `$PSDebugContext` as `$NestedPromptLevel` variáveis automáticas e, consulte [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="3e237-148">For more information about the `$PSDebugContext` and `$NestedPromptLevel` automatic variables, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

### <a name="how-to-customize-the-prompt"></a><span data-ttu-id="3e237-149">Como personalizar o prompt</span><span class="sxs-lookup"><span data-stu-id="3e237-149">How to customize the prompt</span></span>

<span data-ttu-id="3e237-150">Para personalizar o prompt, escreva uma nova `Prompt` função.</span><span class="sxs-lookup"><span data-stu-id="3e237-150">To customize the prompt, write a new `Prompt` function.</span></span> <span data-ttu-id="3e237-151">A função não está protegida, portanto, você pode substituí-la.</span><span class="sxs-lookup"><span data-stu-id="3e237-151">The function is not protected, so you can overwrite it.</span></span>

<span data-ttu-id="3e237-152">Para gravar uma `Prompt` função, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3e237-152">To write a `Prompt` function, type the following:</span></span>

```powershell
function prompt { }
```

<span data-ttu-id="3e237-153">Em seguida, entre as chaves, insira os comandos ou a cadeia de caracteres que cria o prompt.</span><span class="sxs-lookup"><span data-stu-id="3e237-153">Then, between the braces, enter the commands or the string that creates your prompt.</span></span>

<span data-ttu-id="3e237-154">Por exemplo, o seguinte prompt inclui o nome do computador:</span><span class="sxs-lookup"><span data-stu-id="3e237-154">For example, the following prompt includes your computer name:</span></span>

```powershell
function prompt {"PS [$env:COMPUTERNAME]> "}
```

<span data-ttu-id="3e237-155">No computador Server01, o prompt é semelhante ao seguinte prompt:</span><span class="sxs-lookup"><span data-stu-id="3e237-155">On the Server01 computer, the prompt resembles the following prompt:</span></span>

```Output
PS [Server01] >
```

<span data-ttu-id="3e237-156">A função a seguir `Prompt` inclui a data e a hora atuais:</span><span class="sxs-lookup"><span data-stu-id="3e237-156">The following `Prompt` function includes the current date and time:</span></span>

```powershell
function prompt {"$(Get-Date)> "}
```

<span data-ttu-id="3e237-157">O prompt é semelhante ao seguinte prompt:</span><span class="sxs-lookup"><span data-stu-id="3e237-157">The prompt resembles the following prompt:</span></span>

```Output
03/15/2012 17:49:47>
```

<span data-ttu-id="3e237-158">Você também pode alterar a `Prompt` função padrão:</span><span class="sxs-lookup"><span data-stu-id="3e237-158">You can also change the default `Prompt` function:</span></span>

<span data-ttu-id="3e237-159">Por exemplo, a função modificada a seguir `Prompt` adiciona `[ADMIN]:` ao prompt interno do PowerShell quando o PowerShell é aberto usando a opção **Executar como administrador** :</span><span class="sxs-lookup"><span data-stu-id="3e237-159">For example, the following modified `Prompt` function adds `[ADMIN]:` to the built-in PowerShell prompt when PowerShell is opened by using the **Run as administrator** option:</span></span>

```powershell
function prompt {
  $identity = [Security.Principal.WindowsIdentity]::GetCurrent()
  $principal = [Security.Principal.WindowsPrincipal] $identity
  $adminRole = [Security.Principal.WindowsBuiltInRole]::Administrator

  $(if (Test-Path variable:/PSDebugContext) { '[DBG]: ' }
    elseif($principal.IsInRole($adminRole)) { "[ADMIN]: " }
    else { '' }
  ) + 'PS ' + $(Get-Location) +
    $(if ($NestedPromptLevel -ge 1) { '>>' }) + '> '
}
```

<span data-ttu-id="3e237-160">Quando você inicia o PowerShell usando a opção **Executar como administrador** , um prompt semelhante ao seguinte prompt é exibido:</span><span class="sxs-lookup"><span data-stu-id="3e237-160">When you start PowerShell by using the **Run as administrator** option, a prompt that resembles the following prompt appears:</span></span>

```Output
[ADMIN]: PS C:\ps-test>
```

<span data-ttu-id="3e237-161">A função a seguir `Prompt` exibe a ID do histórico do próximo comando.</span><span class="sxs-lookup"><span data-stu-id="3e237-161">The following `Prompt` function displays the history ID of the next command.</span></span> <span data-ttu-id="3e237-162">Para exibir o histórico de comandos, use o `Get-History` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3e237-162">To view the command history, use the `Get-History` cmdlet.</span></span>

```powershell
function prompt {
   # The at sign creates an array in case only one history item exists.
   $history = @(Get-History)
   if($history.Count -gt 0)
   {
      $lastItem = $history[$history.Count - 1]
      $lastId = $lastItem.Id
   }

   $nextCommand = $lastId + 1
   $currentDirectory = Get-Location
   "PS: $nextCommand $currentDirectory >"
}
```

<span data-ttu-id="3e237-163">O prompt a seguir usa `Write-Host` os `Get-Random` cmdlets e para criar um prompt que altera a cor aleatoriamente.</span><span class="sxs-lookup"><span data-stu-id="3e237-163">The following prompt uses the `Write-Host` and `Get-Random` cmdlets to create a prompt that changes color randomly.</span></span> <span data-ttu-id="3e237-164">Como `Write-Host` o grava no aplicativo host atual, mas não retorna um objeto, essa função inclui uma `Return` instrução.</span><span class="sxs-lookup"><span data-stu-id="3e237-164">Because `Write-Host` writes to the current host application but does not return an object, this function includes a `Return` statement.</span></span> <span data-ttu-id="3e237-165">Sem ele, o PowerShell usa o prompt padrão, `PS>` .</span><span class="sxs-lookup"><span data-stu-id="3e237-165">Without it, PowerShell uses the default prompt, `PS>`.</span></span>

```powershell
function prompt {
    $color = Get-Random -Min 1 -Max 16
    Write-Host ("PS " + $(Get-Location) +">") -NoNewLine `
     -ForegroundColor $Color
    return " "
}
```

### <a name="saving-the-prompt-function"></a><span data-ttu-id="3e237-166">Salvando a função prompt</span><span class="sxs-lookup"><span data-stu-id="3e237-166">Saving the Prompt function</span></span>

<span data-ttu-id="3e237-167">Como qualquer função, a `Prompt` função existe somente na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="3e237-167">Like any function, the `Prompt` function exists only in the current session.</span></span> <span data-ttu-id="3e237-168">Para salvar a `Prompt` função para sessões futuras, adicione-a aos seus perfis do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e237-168">To save the `Prompt` function for future sessions, add it to your PowerShell profiles.</span></span> <span data-ttu-id="3e237-169">Para obter mais informações sobre perfis, consulte [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="3e237-169">For more information about profiles, see [about_Profiles](about_Profiles.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3e237-170">Confira também</span><span class="sxs-lookup"><span data-stu-id="3e237-170">See also</span></span>

[<span data-ttu-id="3e237-171">Get-Location</span><span class="sxs-lookup"><span data-stu-id="3e237-171">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)

[<span data-ttu-id="3e237-172">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="3e237-172">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="3e237-173">Get-History</span><span class="sxs-lookup"><span data-stu-id="3e237-173">Get-History</span></span>](xref:Microsoft.PowerShell.Core.Get-History)

[<span data-ttu-id="3e237-174">Get-Random</span><span class="sxs-lookup"><span data-stu-id="3e237-174">Get-Random</span></span>](xref:Microsoft.PowerShell.Utility.Get-Random)

[<span data-ttu-id="3e237-175">Write-Host</span><span class="sxs-lookup"><span data-stu-id="3e237-175">Write-Host</span></span>](xref:Microsoft.PowerShell.Utility.Write-Host)

[<span data-ttu-id="3e237-176">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="3e237-176">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="3e237-177">about_Functions</span><span class="sxs-lookup"><span data-stu-id="3e237-177">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="3e237-178">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="3e237-178">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="3e237-179">about_Debuggers</span><span class="sxs-lookup"><span data-stu-id="3e237-179">about_Debuggers</span></span>](about_Debuggers.md)

[<span data-ttu-id="3e237-180">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="3e237-180">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)
