---
description: Descreve a `Prompt` função e demonstra como criar uma função personalizada `Prompt` .
Locale: en-US
ms.date: 04/15/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_prompts?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Prompts
ms.openlocfilehash: 3887df636c3ad486a4dbe72fffdc8acd92d2b3e9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598409"
---
# <a name="about-prompts"></a><span data-ttu-id="f3e84-103">Sobre os prompts</span><span class="sxs-lookup"><span data-stu-id="f3e84-103">About Prompts</span></span>

## <a name="short-description"></a><span data-ttu-id="f3e84-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="f3e84-104">Short description</span></span>
<span data-ttu-id="f3e84-105">Descreve a `Prompt` função e demonstra como criar uma função personalizada `Prompt` .</span><span class="sxs-lookup"><span data-stu-id="f3e84-105">Describes the `Prompt` function and demonstrates how to create a custom `Prompt` function.</span></span>

## <a name="long-description"></a><span data-ttu-id="f3e84-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="f3e84-106">Long description</span></span>

<span data-ttu-id="f3e84-107">O prompt de comando do PowerShell indica que o PowerShell está pronto para executar um comando:</span><span class="sxs-lookup"><span data-stu-id="f3e84-107">The PowerShell command prompt indicates that PowerShell is ready to run a command:</span></span>

```
PS C:\>
```

<span data-ttu-id="f3e84-108">O prompt do PowerShell é determinado pela `Prompt` função interna.</span><span class="sxs-lookup"><span data-stu-id="f3e84-108">The PowerShell prompt is determined by the built-in `Prompt` function.</span></span> <span data-ttu-id="f3e84-109">Você pode personalizar o prompt criando sua própria `Prompt` função e salvando-a em seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f3e84-109">You can customize the prompt by creating your own `Prompt` function and saving it in your PowerShell profile.</span></span>

## <a name="about-the-prompt-function"></a><span data-ttu-id="f3e84-110">Sobre a função de prompt</span><span class="sxs-lookup"><span data-stu-id="f3e84-110">About the Prompt function</span></span>

<span data-ttu-id="f3e84-111">A `Prompt` função determina a aparência do prompt do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f3e84-111">The `Prompt` function determines the appearance of the PowerShell prompt.</span></span>
<span data-ttu-id="f3e84-112">O PowerShell vem com uma função interna `Prompt` , mas você pode substituí-la definindo sua própria `Prompt` função.</span><span class="sxs-lookup"><span data-stu-id="f3e84-112">PowerShell comes with a built-in `Prompt` function, but you can override it by defining your own `Prompt` function.</span></span>

<span data-ttu-id="f3e84-113">A `Prompt` função tem a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="f3e84-113">The `Prompt` function has the following syntax:</span></span>

```powershell
function Prompt { <function-body> }
```

<span data-ttu-id="f3e84-114">A `Prompt` função deve retornar um objeto.</span><span class="sxs-lookup"><span data-stu-id="f3e84-114">The `Prompt` function must return an object.</span></span> <span data-ttu-id="f3e84-115">Como prática recomendada, retorne uma cadeia de caracteres ou um objeto formatado como uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f3e84-115">As a best practice, return a string or an object that is formatted as a string.</span></span> <span data-ttu-id="f3e84-116">O comprimento máximo recomendado é de 80 caracteres.</span><span class="sxs-lookup"><span data-stu-id="f3e84-116">The maximum recommended length is 80 characters.</span></span>

<span data-ttu-id="f3e84-117">Por exemplo, a função a seguir `Prompt` retorna uma cadeia de caracteres "Olá, mundo" seguida por um colchete angular direito ( `>` ).</span><span class="sxs-lookup"><span data-stu-id="f3e84-117">For example, the following `Prompt` function returns a "Hello, World" string followed by a  right angle bracket (`>`).</span></span>

```powershell
PS C:\> function prompt {"Hello, World > "}
Hello, World >
```

### <a name="getting-the-prompt-function"></a><span data-ttu-id="f3e84-118">Obtendo a função prompt</span><span class="sxs-lookup"><span data-stu-id="f3e84-118">Getting the Prompt function</span></span>

<span data-ttu-id="f3e84-119">Para obter a `Prompt` função, use o `Get-Command` cmdlet ou use o `Get-Item` cmdlet na unidade de função.</span><span class="sxs-lookup"><span data-stu-id="f3e84-119">To get the `Prompt` function, use the `Get-Command` cmdlet or use the `Get-Item` cmdlet in the Function drive.</span></span>

<span data-ttu-id="f3e84-120">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f3e84-120">For example:</span></span>

```powershell
PS C:\> Get-Command Prompt

CommandType     Name      ModuleName
-----------     ----      ----------
Function        prompt
```

<span data-ttu-id="f3e84-121">Para obter o script que define o valor do prompt, use o método dot para obter a propriedade **scriptblock** da `Prompt` função.</span><span class="sxs-lookup"><span data-stu-id="f3e84-121">To get the script that sets the value of the prompt, use the dot method to get the **ScriptBlock** property of the `Prompt` function.</span></span>

<span data-ttu-id="f3e84-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f3e84-122">For example:</span></span>

```powershell
(Get-Command Prompt).ScriptBlock
```

```Output
"PS $($executionContext.SessionState.Path.CurrentLocation)$('>' * ($nestedPromptLevel + 1)) "
# .Link
# https://go.microsoft.com/fwlink/?LinkID=225750
# .ExternalHelp System.Management.Automation.dll-help.xml
```

<span data-ttu-id="f3e84-123">Como todas as funções, a `Prompt` função é armazenada na `Function:` unidade.</span><span class="sxs-lookup"><span data-stu-id="f3e84-123">Like all functions, the `Prompt` function is stored in the `Function:` drive.</span></span>
<span data-ttu-id="f3e84-124">Para exibir o script que cria a `Prompt` função atual, digite:</span><span class="sxs-lookup"><span data-stu-id="f3e84-124">To display the script that creates the current `Prompt` function, type:</span></span>

```powershell
(Get-Item function:prompt).ScriptBlock
```

### <a name="the-default-prompt"></a><span data-ttu-id="f3e84-125">O prompt padrão</span><span class="sxs-lookup"><span data-stu-id="f3e84-125">The default prompt</span></span>

<span data-ttu-id="f3e84-126">O prompt padrão aparece somente quando a `Prompt` função gera um erro ou não retorna um objeto.</span><span class="sxs-lookup"><span data-stu-id="f3e84-126">The default prompt appears only when the `Prompt` function generates an error or does not return an object.</span></span>

<span data-ttu-id="f3e84-127">O prompt padrão do PowerShell é:</span><span class="sxs-lookup"><span data-stu-id="f3e84-127">The default PowerShell prompt is:</span></span>

```
PS>
```

<span data-ttu-id="f3e84-128">Por exemplo, o comando a seguir define a `Prompt` função como `$null` , que é inválida.</span><span class="sxs-lookup"><span data-stu-id="f3e84-128">For example, the following command sets the `Prompt` function to `$null`, which is invalid.</span></span> <span data-ttu-id="f3e84-129">Como resultado, o prompt padrão é exibido.</span><span class="sxs-lookup"><span data-stu-id="f3e84-129">As a result, the default prompt appears.</span></span>

```powershell
PS C:\> function prompt {$null}
PS>
```

<span data-ttu-id="f3e84-130">Como o PowerShell é fornecido com um prompt interno, normalmente, você não vê o prompt padrão.</span><span class="sxs-lookup"><span data-stu-id="f3e84-130">Because PowerShell comes with a built-in prompt, you usually do not see the default prompt.</span></span>

### <a name="built-in-prompt"></a><span data-ttu-id="f3e84-131">Prompt interno</span><span class="sxs-lookup"><span data-stu-id="f3e84-131">Built-in prompt</span></span>

<span data-ttu-id="f3e84-132">O PowerShell inclui uma função interna `Prompt` .</span><span class="sxs-lookup"><span data-stu-id="f3e84-132">PowerShell includes a built-in `Prompt` function.</span></span>

```powershell
function prompt {
    $(if (Test-Path variable:/PSDebugContext) { '[DBG]: ' }
      else { '' }) + 'PS ' + $(Get-Location) +
        $(if ($NestedPromptLevel -ge 1) { '>>' }) + '> '
}
```

<span data-ttu-id="f3e84-133">A função usa o `Test-Path` cmdlet para determinar se a `$PSDebugContext` variável automática é populada.</span><span class="sxs-lookup"><span data-stu-id="f3e84-133">The function uses the `Test-Path` cmdlet to determine whether the `$PSDebugContext` automatic variable is populated.</span></span> <span data-ttu-id="f3e84-134">Se `$PSDebugContext` estiver populado, você estará no modo de depuração e `[DBG]:` será adicionado ao prompt da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f3e84-134">If `$PSDebugContext` is populated, you are in debugging mode, and `[DBG]:` is added to the prompt, as follows:</span></span>

```Output
[DBG]: PS C:\ps-test>
```

<span data-ttu-id="f3e84-135">Se `$PSDebugContext` não for populado, a função será adicionada `PS` ao prompt.</span><span class="sxs-lookup"><span data-stu-id="f3e84-135">If `$PSDebugContext` is not populated, the function adds `PS` to the prompt.</span></span>
<span data-ttu-id="f3e84-136">E, a função usa o `Get-Location` cmdlet para obter o local do diretório do sistema de arquivos atual.</span><span class="sxs-lookup"><span data-stu-id="f3e84-136">And, the function uses the `Get-Location` cmdlet to get the current file system directory location.</span></span> <span data-ttu-id="f3e84-137">Em seguida, ele adiciona um colchete angular direito ( `>` ).</span><span class="sxs-lookup"><span data-stu-id="f3e84-137">Then, it adds a right angle bracket (`>`).</span></span>

<span data-ttu-id="f3e84-138">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f3e84-138">For example:</span></span>

```Output
PS C:\ps-test>
```

<span data-ttu-id="f3e84-139">Se você estiver em um prompt aninhado, a função adicionará dois colchetes angulares ( `>>` ) ao prompt.</span><span class="sxs-lookup"><span data-stu-id="f3e84-139">If you are in a nested prompt, the function adds two angle brackets (`>>`) to the prompt.</span></span> <span data-ttu-id="f3e84-140">(Você estará em um prompt aninhado se o valor da `$NestedPromptLevel` variável automática for maior que 1.)</span><span class="sxs-lookup"><span data-stu-id="f3e84-140">(You are in a nested prompt if the value of the `$NestedPromptLevel` automatic variable is greater than 1.)</span></span>

<span data-ttu-id="f3e84-141">Por exemplo, quando você estiver Depurando em um prompt aninhado, o prompt será semelhante ao seguinte prompt:</span><span class="sxs-lookup"><span data-stu-id="f3e84-141">For example, when you are debugging in a nested prompt, the prompt resembles the following prompt:</span></span>

```Output
[DBG] PS C:\ps-test>>>
```

### <a name="changes-to-the-prompt"></a><span data-ttu-id="f3e84-142">Alterações no prompt</span><span class="sxs-lookup"><span data-stu-id="f3e84-142">Changes to the prompt</span></span>

<span data-ttu-id="f3e84-143">O `Enter-PSSession` cmdlet precede o nome do computador remoto para a `Prompt` função atual.</span><span class="sxs-lookup"><span data-stu-id="f3e84-143">The `Enter-PSSession` cmdlet prepends the name of the remote computer to the current `Prompt` function.</span></span> <span data-ttu-id="f3e84-144">Quando você usa o `Enter-PSSession` cmdlet para iniciar uma sessão com um computador remoto, o prompt de comando é alterado para incluir o nome do computador remoto.</span><span class="sxs-lookup"><span data-stu-id="f3e84-144">When you use the `Enter-PSSession` cmdlet to start a session with a remote computer, the command prompt changes to include the name of the remote computer.</span></span> <span data-ttu-id="f3e84-145">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f3e84-145">For example:</span></span>

```Output
PS Hello, World> Enter-PSSession Server01
[Server01]: PS Hello, World>
```

<span data-ttu-id="f3e84-146">Outros aplicativos host do PowerShell e shells alternativos podem ter seus próprios prompts de comando personalizados.</span><span class="sxs-lookup"><span data-stu-id="f3e84-146">Other PowerShell host applications and alternate shells might have their own custom command prompts.</span></span>

<span data-ttu-id="f3e84-147">Para obter mais informações sobre `$PSDebugContext` as `$NestedPromptLevel` variáveis automáticas e, consulte [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="f3e84-147">For more information about the `$PSDebugContext` and `$NestedPromptLevel` automatic variables, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

### <a name="how-to-customize-the-prompt"></a><span data-ttu-id="f3e84-148">Como personalizar o prompt</span><span class="sxs-lookup"><span data-stu-id="f3e84-148">How to customize the prompt</span></span>

<span data-ttu-id="f3e84-149">Para personalizar o prompt, escreva uma nova `Prompt` função.</span><span class="sxs-lookup"><span data-stu-id="f3e84-149">To customize the prompt, write a new `Prompt` function.</span></span> <span data-ttu-id="f3e84-150">A função não está protegida, portanto, você pode substituí-la.</span><span class="sxs-lookup"><span data-stu-id="f3e84-150">The function is not protected, so you can overwrite it.</span></span>

<span data-ttu-id="f3e84-151">Para gravar uma `Prompt` função, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f3e84-151">To write a `Prompt` function, type the following:</span></span>

```powershell
function prompt { }
```

<span data-ttu-id="f3e84-152">Em seguida, entre as chaves, insira os comandos ou a cadeia de caracteres que cria o prompt.</span><span class="sxs-lookup"><span data-stu-id="f3e84-152">Then, between the braces, enter the commands or the string that creates your prompt.</span></span>

<span data-ttu-id="f3e84-153">Por exemplo, o seguinte prompt inclui o nome do computador:</span><span class="sxs-lookup"><span data-stu-id="f3e84-153">For example, the following prompt includes your computer name:</span></span>

```powershell
function prompt {"PS [$env:COMPUTERNAME]> "}
```

<span data-ttu-id="f3e84-154">No computador Server01, o prompt é semelhante ao seguinte prompt:</span><span class="sxs-lookup"><span data-stu-id="f3e84-154">On the Server01 computer, the prompt resembles the following prompt:</span></span>

```Output
PS [Server01] >
```

<span data-ttu-id="f3e84-155">A função a seguir `Prompt` inclui a data e a hora atuais:</span><span class="sxs-lookup"><span data-stu-id="f3e84-155">The following `Prompt` function includes the current date and time:</span></span>

```powershell
function prompt {"$(Get-Date)> "}
```

<span data-ttu-id="f3e84-156">O prompt é semelhante ao seguinte prompt:</span><span class="sxs-lookup"><span data-stu-id="f3e84-156">The prompt resembles the following prompt:</span></span>

```Output
03/15/2012 17:49:47>
```

<span data-ttu-id="f3e84-157">Você também pode alterar a `Prompt` função padrão:</span><span class="sxs-lookup"><span data-stu-id="f3e84-157">You can also change the default `Prompt` function:</span></span>

<span data-ttu-id="f3e84-158">Por exemplo, a função modificada a seguir `Prompt` adiciona `[ADMIN]:` ao prompt interno do PowerShell quando o PowerShell é aberto usando a opção **Executar como administrador** :</span><span class="sxs-lookup"><span data-stu-id="f3e84-158">For example, the following modified `Prompt` function adds `[ADMIN]:` to the built-in PowerShell prompt when PowerShell is opened by using the **Run as administrator** option:</span></span>

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

<span data-ttu-id="f3e84-159">Quando você inicia o PowerShell usando a opção **Executar como administrador** , um prompt semelhante ao seguinte prompt é exibido:</span><span class="sxs-lookup"><span data-stu-id="f3e84-159">When you start PowerShell by using the **Run as administrator** option, a prompt that resembles the following prompt appears:</span></span>

```Output
[ADMIN]: PS C:\ps-test>
```

<span data-ttu-id="f3e84-160">A função a seguir `Prompt` exibe a ID do histórico do próximo comando.</span><span class="sxs-lookup"><span data-stu-id="f3e84-160">The following `Prompt` function displays the history ID of the next command.</span></span> <span data-ttu-id="f3e84-161">Para exibir o histórico de comandos, use o `Get-History` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f3e84-161">To view the command history, use the `Get-History` cmdlet.</span></span>

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

<span data-ttu-id="f3e84-162">O prompt a seguir usa `Write-Host` os `Get-Random` cmdlets e para criar um prompt que altera a cor aleatoriamente.</span><span class="sxs-lookup"><span data-stu-id="f3e84-162">The following prompt uses the `Write-Host` and `Get-Random` cmdlets to create a prompt that changes color randomly.</span></span> <span data-ttu-id="f3e84-163">Como `Write-Host` o grava no aplicativo host atual, mas não retorna um objeto, essa função inclui uma `Return` instrução.</span><span class="sxs-lookup"><span data-stu-id="f3e84-163">Because `Write-Host` writes to the current host application but does not return an object, this function includes a `Return` statement.</span></span> <span data-ttu-id="f3e84-164">Sem ele, o PowerShell usa o prompt padrão, `PS>` .</span><span class="sxs-lookup"><span data-stu-id="f3e84-164">Without it, PowerShell uses the default prompt, `PS>`.</span></span>

```powershell
function prompt {
    $color = Get-Random -Min 1 -Max 16
    Write-Host ("PS " + $(Get-Location) +">") -NoNewLine `
     -ForegroundColor $Color
    return " "
}
```

### <a name="saving-the-prompt-function"></a><span data-ttu-id="f3e84-165">Salvando a função prompt</span><span class="sxs-lookup"><span data-stu-id="f3e84-165">Saving the Prompt function</span></span>

<span data-ttu-id="f3e84-166">Como qualquer função, a `Prompt` função existe somente na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="f3e84-166">Like any function, the `Prompt` function exists only in the current session.</span></span> <span data-ttu-id="f3e84-167">Para salvar a `Prompt` função para sessões futuras, adicione-a aos seus perfis do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f3e84-167">To save the `Prompt` function for future sessions, add it to your PowerShell profiles.</span></span> <span data-ttu-id="f3e84-168">Para obter mais informações sobre perfis, consulte [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="f3e84-168">For more information about profiles, see [about_Profiles](about_Profiles.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f3e84-169">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f3e84-169">See also</span></span>

[<span data-ttu-id="f3e84-170">Get-Location</span><span class="sxs-lookup"><span data-stu-id="f3e84-170">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)

[<span data-ttu-id="f3e84-171">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="f3e84-171">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="f3e84-172">Get-History</span><span class="sxs-lookup"><span data-stu-id="f3e84-172">Get-History</span></span>](xref:Microsoft.PowerShell.Core.Get-History)

[<span data-ttu-id="f3e84-173">Get-Random</span><span class="sxs-lookup"><span data-stu-id="f3e84-173">Get-Random</span></span>](xref:Microsoft.PowerShell.Utility.Get-Random)

[<span data-ttu-id="f3e84-174">Write-Host</span><span class="sxs-lookup"><span data-stu-id="f3e84-174">Write-Host</span></span>](xref:Microsoft.PowerShell.Utility.Write-Host)

[<span data-ttu-id="f3e84-175">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="f3e84-175">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="f3e84-176">about_Functions</span><span class="sxs-lookup"><span data-stu-id="f3e84-176">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="f3e84-177">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="f3e84-177">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="f3e84-178">about_Debuggers</span><span class="sxs-lookup"><span data-stu-id="f3e84-178">about_Debuggers</span></span>](about_Debuggers.md)

[<span data-ttu-id="f3e84-179">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="f3e84-179">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

