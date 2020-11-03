---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 3/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ExecutionPolicy
ms.openlocfilehash: d04fb0bb75906d18fecce17e4ceb581fe667eceb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193395"
---
# <span data-ttu-id="54e29-103">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="54e29-103">Set-ExecutionPolicy</span></span>

## <span data-ttu-id="54e29-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="54e29-104">SYNOPSIS</span></span>
<span data-ttu-id="54e29-105">Define as políticas de execução do PowerShell para computadores Windows.</span><span class="sxs-lookup"><span data-stu-id="54e29-105">Sets the PowerShell execution policies for Windows computers.</span></span>

## <span data-ttu-id="54e29-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="54e29-106">SYNTAX</span></span>

### <span data-ttu-id="54e29-107">Tudo</span><span class="sxs-lookup"><span data-stu-id="54e29-107">All</span></span>

```
Set-ExecutionPolicy [-ExecutionPolicy] <ExecutionPolicy> [[-Scope] <ExecutionPolicyScope>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="54e29-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="54e29-108">DESCRIPTION</span></span>

<span data-ttu-id="54e29-109">O `Set-ExecutionPolicy` cmdlet altera as políticas de execução do PowerShell para computadores Windows.</span><span class="sxs-lookup"><span data-stu-id="54e29-109">The `Set-ExecutionPolicy` cmdlet changes PowerShell execution policies for Windows computers.</span></span> <span data-ttu-id="54e29-110">Para obter mais informações, consulte [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="54e29-110">For more information, see [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span></span>

<span data-ttu-id="54e29-111">A partir do PowerShell 6,0 para computadores não Windows, a política de execução padrão é **irrestrita** e não pode ser alterada.</span><span class="sxs-lookup"><span data-stu-id="54e29-111">Beginning in PowerShell 6.0 for non-Windows computers, the default execution policy is **Unrestricted** and can't be changed.</span></span> <span data-ttu-id="54e29-112">O `Set-ExecutionPolicy` cmdlet está disponível, mas o PowerShell exibe uma mensagem de console que não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="54e29-112">The `Set-ExecutionPolicy` cmdlet is available, but PowerShell displays a console message that it's not supported.</span></span>

<span data-ttu-id="54e29-113">Uma política de execução faz parte da estratégia de segurança do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="54e29-113">An execution policy is part of the PowerShell security strategy.</span></span> <span data-ttu-id="54e29-114">As políticas de execução determinam se você pode carregar arquivos de configuração, como seu perfil do PowerShell, ou executar scripts.</span><span class="sxs-lookup"><span data-stu-id="54e29-114">Execution policies determine whether you can load configuration files, such as your PowerShell profile, or run scripts.</span></span> <span data-ttu-id="54e29-115">E se os scripts devem ser assinados digitalmente antes de serem executados.</span><span class="sxs-lookup"><span data-stu-id="54e29-115">And, whether scripts must be digitally signed before they are run.</span></span>

<span data-ttu-id="54e29-116">O `Set-ExecutionPolicy` escopo padrão do cmdlet é **LocalMachine** , o que afeta todos os que usam o computador.</span><span class="sxs-lookup"><span data-stu-id="54e29-116">The `Set-ExecutionPolicy` cmdlet's default scope is **LocalMachine** , which affects everyone who uses the computer.</span></span> <span data-ttu-id="54e29-117">Para alterar a política de execução para **LocalMachine** , inicie o PowerShell com **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="54e29-117">To change the execution policy for **LocalMachine** , start PowerShell with **Run as Administrator** .</span></span>

<span data-ttu-id="54e29-118">Para exibir as políticas de execução para cada escopo na ordem de precedência, use `Get-ExecutionPolicy -List` .</span><span class="sxs-lookup"><span data-stu-id="54e29-118">To display the execution policies for each scope in the order of precedence, use `Get-ExecutionPolicy -List`.</span></span> <span data-ttu-id="54e29-119">Para ver a política de execução efetiva para sua sessão do PowerShell, use `Get-ExecutionPolicy` sem parâmetros.</span><span class="sxs-lookup"><span data-stu-id="54e29-119">To see the effective execution policy for your PowerShell session use `Get-ExecutionPolicy` with no parameters.</span></span>

## <span data-ttu-id="54e29-120">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="54e29-120">EXAMPLES</span></span>

### <span data-ttu-id="54e29-121">Exemplo 1: definir uma política de execução</span><span class="sxs-lookup"><span data-stu-id="54e29-121">Example 1: Set an execution policy</span></span>

<span data-ttu-id="54e29-122">Este exemplo mostra como definir a política de execução para o computador local.</span><span class="sxs-lookup"><span data-stu-id="54e29-122">This example shows how to set the execution policy for the local computer.</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine
Get-ExecutionPolicy -List
```

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser    RemoteSigned
 LocalMachine    RemoteSigned
```

<span data-ttu-id="54e29-123">O `Set-ExecutionPolicy` cmdlet usa o parâmetro **ExecutionPolicy** para especificar a política **RemoteSigned** .</span><span class="sxs-lookup"><span data-stu-id="54e29-123">The `Set-ExecutionPolicy` cmdlet uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="54e29-124">O parâmetro **Scope** especifica o valor de escopo padrão, **LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="54e29-124">The **Scope** parameter specifies the default scope value, **LocalMachine** .</span></span> <span data-ttu-id="54e29-125">Para exibir as configurações de política de execução, use o `Get-ExecutionPolicy` cmdlet com o parâmetro **list** .</span><span class="sxs-lookup"><span data-stu-id="54e29-125">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="54e29-126">Exemplo 2: definir uma política de execução que está em conflito com um Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="54e29-126">Example 2: Set an execution policy that conflicts with a Group Policy</span></span>

<span data-ttu-id="54e29-127">Esse comando tenta definir a política de execução do escopo de **LocalMachine** como **restrita** .</span><span class="sxs-lookup"><span data-stu-id="54e29-127">This command attempts to set the **LocalMachine** scope's execution policy to **Restricted** .</span></span>
<span data-ttu-id="54e29-128">**LocalMachine** é mais restritiva, mas não é a política efetiva porque está em conflito com um política de grupo.</span><span class="sxs-lookup"><span data-stu-id="54e29-128">**LocalMachine** is more restrictive, but isn't the effective policy because it conflicts with a Group Policy.</span></span> <span data-ttu-id="54e29-129">A política **restrita** é gravada no hive do registro **HKEY_LOCAL_MACHINE** .</span><span class="sxs-lookup"><span data-stu-id="54e29-129">The **Restricted** policy is written to the registry hive **HKEY_LOCAL_MACHINE** .</span></span>

```
PS> Set-ExecutionPolicy -ExecutionPolicy Restricted -Scope LocalMachine

Set-ExecutionPolicy : PowerShell updated your local preference successfully, but the setting is
overridden by the Group Policy applied to your system. Due to the override, your shell will retain
its current effective execution policy of "AllSigned". Contact your Group Policy administrator for
more information. At line:1 char:20 + Set-ExecutionPolicy <<<< restricted

PS> Get-ChildItem -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PowerShell\1\ShellIds

Name                    Property
----                    --------
Microsoft.PowerShell    Path            : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe
                        ExecutionPolicy : Restricted
ScriptedDiagnostics     ExecutionPolicy : Unrestricted
```

<span data-ttu-id="54e29-130">O `Set-ExecutionPolicy` cmdlet usa o parâmetro **ExecutionPolicy** para especificar a política **restrita** .</span><span class="sxs-lookup"><span data-stu-id="54e29-130">The `Set-ExecutionPolicy` cmdlet uses the **ExecutionPolicy** parameter to specify the **Restricted** policy.</span></span> <span data-ttu-id="54e29-131">O parâmetro **Scope** especifica o valor de escopo padrão, **LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="54e29-131">The **Scope** parameter specifies the default scope value, **LocalMachine** .</span></span>
<span data-ttu-id="54e29-132">O `Get-ChildItem` cmdlet usa o parâmetro **Path** com o provedor **HKLM** para especificar o local do registro.</span><span class="sxs-lookup"><span data-stu-id="54e29-132">The `Get-ChildItem` cmdlet uses the **Path** parameter with the **HKLM** provider to specify registry location.</span></span>

### <span data-ttu-id="54e29-133">Exemplo 3: aplicar a política de execução de um computador remoto a um computador local</span><span class="sxs-lookup"><span data-stu-id="54e29-133">Example 3: Apply the execution policy from a remote computer to a local computer</span></span>

<span data-ttu-id="54e29-134">Esse comando obtém o objeto de política de execução de um computador remoto e define a política no computador local.</span><span class="sxs-lookup"><span data-stu-id="54e29-134">This command gets the execution policy object from a remote computer and sets the policy on the local computer.</span></span> <span data-ttu-id="54e29-135">`Get-ExecutionPolicy` envia um objeto **Microsoft.PowerShell.ExecutionPolicy** para baixo do pipeline.</span><span class="sxs-lookup"><span data-stu-id="54e29-135">`Get-ExecutionPolicy` sends a **Microsoft.PowerShell.ExecutionPolicy** object down the pipeline.</span></span> <span data-ttu-id="54e29-136">`Set-ExecutionPolicy` aceita a entrada de pipeline e não requer o parâmetro **ExecutionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="54e29-136">`Set-ExecutionPolicy` accepts pipeline input and doesn't require the **ExecutionPolicy** parameter.</span></span>

```
PS> Invoke-Command -ComputerName Server01 -ScriptBlock { Get-ExecutionPolicy } | Set-ExecutionPolicy
```

<span data-ttu-id="54e29-137">O `Invoke-Command` cmdlet é executado no computador local e envia o **scriptblock** para o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="54e29-137">The `Invoke-Command` cmdlet is executed at the local computer and sends the **ScriptBlock** to the remote computer.</span></span> <span data-ttu-id="54e29-138">O parâmetro **ComputerName** especifica o computador remoto, **Server01** .</span><span class="sxs-lookup"><span data-stu-id="54e29-138">The **ComputerName** parameter specifies the remote computer, **Server01** .</span></span> <span data-ttu-id="54e29-139">O parâmetro **scriptblock** é executado `Get-ExecutionPolicy` no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="54e29-139">The **ScriptBlock** parameter runs `Get-ExecutionPolicy` on the remote computer.</span></span> <span data-ttu-id="54e29-140">O `Get-ExecutionPolicy` objeto é enviado ao pipeline para o `Set-ExecutionPolicy` .</span><span class="sxs-lookup"><span data-stu-id="54e29-140">The `Get-ExecutionPolicy` object is sent down the pipeline to the `Set-ExecutionPolicy`.</span></span>
<span data-ttu-id="54e29-141">`Set-ExecutionPolicy` aplica a política de execução ao escopo padrão do computador local, **LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="54e29-141">`Set-ExecutionPolicy` applies the execution policy to the local computer's default scope, **LocalMachine** .</span></span>

### <span data-ttu-id="54e29-142">Exemplo 4: definir o escopo para uma política de execução</span><span class="sxs-lookup"><span data-stu-id="54e29-142">Example 4: Set the scope for an execution policy</span></span>

<span data-ttu-id="54e29-143">Este exemplo mostra como definir uma política de execução para um escopo especificado, **CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="54e29-143">This example shows how to set an execution policy for a specified scope, **CurrentUser** .</span></span> <span data-ttu-id="54e29-144">O escopo **CurrentUser** só afeta o usuário que define esse escopo.</span><span class="sxs-lookup"><span data-stu-id="54e29-144">The **CurrentUser** scope only affects the user who sets this scope.</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy AllSigned -Scope CurrentUser
Get-ExecutionPolicy -List
```

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser       AllSigned
 LocalMachine    RemoteSigned
```

<span data-ttu-id="54e29-145">`Set-ExecutionPolicy` usa o parâmetro **ExecutionPolicy** para especificar a política **AllSigned** .</span><span class="sxs-lookup"><span data-stu-id="54e29-145">`Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **AllSigned** policy.</span></span>
<span data-ttu-id="54e29-146">O parâmetro **Scope** especifica o **CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="54e29-146">The **Scope** parameter specifies the **CurrentUser** .</span></span> <span data-ttu-id="54e29-147">Para exibir as configurações de política de execução, use o `Get-ExecutionPolicy` cmdlet com o parâmetro **list** .</span><span class="sxs-lookup"><span data-stu-id="54e29-147">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

<span data-ttu-id="54e29-148">A política de execução efetiva para o usuário torna-se **AllSigned** .</span><span class="sxs-lookup"><span data-stu-id="54e29-148">The effective execution policy for the user becomes **AllSigned** .</span></span>

### <span data-ttu-id="54e29-149">Exemplo 5: remover a política de execução para o usuário atual</span><span class="sxs-lookup"><span data-stu-id="54e29-149">Example 5: Remove the execution policy for the current user</span></span>

<span data-ttu-id="54e29-150">Este exemplo mostra como usar a política de execução **indefinida** para remover uma política de execução para um escopo especificado.</span><span class="sxs-lookup"><span data-stu-id="54e29-150">This example shows how use the **Undefined** execution policy to remove an execution policy for a specified scope.</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy Undefined -Scope CurrentUser
Get-ExecutionPolicy -List
```

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser       Undefined
 LocalMachine    RemoteSigned
```

<span data-ttu-id="54e29-151">`Set-ExecutionPolicy` usa o parâmetro **ExecutionPolicy** para especificar a política **indefinida** .</span><span class="sxs-lookup"><span data-stu-id="54e29-151">`Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **Undefined** policy.</span></span>
<span data-ttu-id="54e29-152">O parâmetro **Scope** especifica o **CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="54e29-152">The **Scope** parameter specifies the **CurrentUser** .</span></span> <span data-ttu-id="54e29-153">Para exibir as configurações de política de execução, use o `Get-ExecutionPolicy` cmdlet com o parâmetro **list** .</span><span class="sxs-lookup"><span data-stu-id="54e29-153">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="54e29-154">Exemplo 6: definir a política de execução para a sessão atual do PowerShell</span><span class="sxs-lookup"><span data-stu-id="54e29-154">Example 6: Set the execution policy for the current PowerShell session</span></span>

<span data-ttu-id="54e29-155">O escopo do **processo** afeta apenas a sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="54e29-155">The **Process** scope only affects the current PowerShell session.</span></span> <span data-ttu-id="54e29-156">A política de execução é salva na variável de ambiente `$env:PSExecutionPolicyPreference` e é excluída quando a sessão é fechada.</span><span class="sxs-lookup"><span data-stu-id="54e29-156">The execution policy is saved in the environment variable `$env:PSExecutionPolicyPreference` and is deleted when the session is closed.</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy AllSigned -Scope Process
```

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       AllSigned
  CurrentUser    RemoteSigned
 LocalMachine    RemoteSigned
```

<span data-ttu-id="54e29-157">O `Set-ExecutionPolicy` usa o parâmetro **ExecutionPolicy** para especificar a política **AllSigned** .</span><span class="sxs-lookup"><span data-stu-id="54e29-157">The `Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **AllSigned** policy.</span></span> <span data-ttu-id="54e29-158">O parâmetro **Scope** especifica o **processo** de valor.</span><span class="sxs-lookup"><span data-stu-id="54e29-158">The **Scope** parameter specifies the value **Process** .</span></span> <span data-ttu-id="54e29-159">Para exibir as configurações de política de execução, use o `Get-ExecutionPolicy` cmdlet com o parâmetro **list** .</span><span class="sxs-lookup"><span data-stu-id="54e29-159">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="54e29-160">Exemplo 7: desbloquear um script para executá-lo sem alterar a política de execução</span><span class="sxs-lookup"><span data-stu-id="54e29-160">Example 7: Unblock a script to run it without changing the execution policy</span></span>

<span data-ttu-id="54e29-161">Este exemplo mostra como a política de execução **RemoteSigned** impede que você execute scripts não assinados.</span><span class="sxs-lookup"><span data-stu-id="54e29-161">This example shows how the **RemoteSigned** execution policy prevents you from running unsigned scripts.</span></span>

<span data-ttu-id="54e29-162">Uma prática recomendada é ler o código do script e verificar se ele é seguro **antes** de usar o `Unblock-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="54e29-162">A best practice is to read the script's code and verify it's safe **before** using the `Unblock-File` cmdlet.</span></span> <span data-ttu-id="54e29-163">O `Unblock-File` cmdlet desbloqueia scripts para que eles possam ser executados, mas não altera a política de execução.</span><span class="sxs-lookup"><span data-stu-id="54e29-163">The `Unblock-File` cmdlet unblocks scripts so they can run, but doesn't change the execution policy.</span></span>

```
PS> Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine

PS> Get-ExecutionPolicy

RemoteSigned

PS> .\Start-ActivityTracker.ps1

.\Start-ActivityTracker.ps1 : File .\Start-ActivityTracker.ps1 cannot be loaded.
The file .\Start-ActivityTracker.ps1 is not digitally signed.
The script will not execute on the system.
For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.
At line:1 char:1
+ .\Start-ActivityTracker.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : NotSpecified: (:) [], PSSecurityException
+ FullyQualifiedErrorId : UnauthorizedAccess

PS> Unblock-File -Path .\Start-ActivityTracker.ps1

PS> Get-ExecutionPolicy

RemoteSigned

PS> .\Start-ActivityTracker.ps1

Task 1:
```

<span data-ttu-id="54e29-164">O `Set-ExecutionPolicy` usa o parâmetro **ExecutionPolicy** para especificar a política de **RemoteSigned** .</span><span class="sxs-lookup"><span data-stu-id="54e29-164">The `Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="54e29-165">A política é definida para o escopo padrão, **LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="54e29-165">The policy is set for the default scope, **LocalMachine** .</span></span>

<span data-ttu-id="54e29-166">O `Get-ExecutionPolicy` cmdlet mostra que **RemoteSigned** é a política de execução efetiva para a sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="54e29-166">The `Get-ExecutionPolicy` cmdlet shows that **RemoteSigned** is the effective execution policy for the current PowerShell session.</span></span>

<span data-ttu-id="54e29-167">O script de **Start-ActivityTracker.ps1** é executado a partir do diretório atual.</span><span class="sxs-lookup"><span data-stu-id="54e29-167">The **Start-ActivityTracker.ps1** script is executed from the current directory.</span></span> <span data-ttu-id="54e29-168">O script é bloqueado por **RemoteSigned** porque o script não está assinado digitalmente.</span><span class="sxs-lookup"><span data-stu-id="54e29-168">The script is blocked by **RemoteSigned** because the script isn't digitally signed.</span></span>

<span data-ttu-id="54e29-169">Neste exemplo, o código do script foi revisado e verificado como seguro para ser executado.</span><span class="sxs-lookup"><span data-stu-id="54e29-169">For this example, the script's code was reviewed and verified as safe to run.</span></span> <span data-ttu-id="54e29-170">O `Unblock-File` cmdlet usa o parâmetro **Path** para desbloquear o script.</span><span class="sxs-lookup"><span data-stu-id="54e29-170">The `Unblock-File` cmdlet uses the **Path** parameter to unblock the script.</span></span>

<span data-ttu-id="54e29-171">Para verificar se `Unblock-File` a política de execução não foi alterada, `Get-ExecutionPolicy` exibe a política de execução efetiva, **RemoteSigned** .</span><span class="sxs-lookup"><span data-stu-id="54e29-171">To verify that `Unblock-File` didn't change the execution policy, `Get-ExecutionPolicy` displays the effective execution policy, **RemoteSigned** .</span></span>

<span data-ttu-id="54e29-172">O script, **Start-ActivityTracker.ps1** é executado a partir do diretório atual.</span><span class="sxs-lookup"><span data-stu-id="54e29-172">The script, **Start-ActivityTracker.ps1** is executed from the current directory.</span></span> <span data-ttu-id="54e29-173">O script começa a ser executado porque foi desbloqueado pelo `Unblock-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="54e29-173">The script begins to run because it was unblocked by the `Unblock-File` cmdlet.</span></span>

## <span data-ttu-id="54e29-174">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="54e29-174">PARAMETERS</span></span>

### <span data-ttu-id="54e29-175">-Confirm</span><span class="sxs-lookup"><span data-stu-id="54e29-175">-Confirm</span></span>

<span data-ttu-id="54e29-176">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="54e29-176">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="54e29-177">-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="54e29-177">-ExecutionPolicy</span></span>

<span data-ttu-id="54e29-178">Especifica a política de execução.</span><span class="sxs-lookup"><span data-stu-id="54e29-178">Specifies the execution policy.</span></span> <span data-ttu-id="54e29-179">Se não houver nenhuma política de grupo e a diretiva de execução de cada escopo estiver definida como **indefinida** , a **restrição** se tornará a política efetiva para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="54e29-179">If there are no Group Policies and each scope's execution policy is set to **Undefined** , then **Restricted** becomes the effective policy for all users.</span></span>

<span data-ttu-id="54e29-180">Os valores de política de execução aceitáveis são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="54e29-180">The acceptable execution policy values are as follows:</span></span>

- <span data-ttu-id="54e29-181">**AllSigned** .</span><span class="sxs-lookup"><span data-stu-id="54e29-181">**AllSigned** .</span></span> <span data-ttu-id="54e29-182">Requer que todos os scripts e arquivos de configuração sejam assinados por um fornecedor confiável, incluindo scripts gravados no computador local.</span><span class="sxs-lookup"><span data-stu-id="54e29-182">Requires that all scripts and configuration files are signed by a trusted publisher, including scripts written on the local computer.</span></span>
- <span data-ttu-id="54e29-183">**Bypass** .</span><span class="sxs-lookup"><span data-stu-id="54e29-183">**Bypass** .</span></span> <span data-ttu-id="54e29-184">Nada está bloqueado e não há avisos ou prompts.</span><span class="sxs-lookup"><span data-stu-id="54e29-184">Nothing is blocked and there are no warnings or prompts.</span></span>
- <span data-ttu-id="54e29-185">**Default** .</span><span class="sxs-lookup"><span data-stu-id="54e29-185">**Default** .</span></span> <span data-ttu-id="54e29-186">Define a política de execução padrão.</span><span class="sxs-lookup"><span data-stu-id="54e29-186">Sets the default execution policy.</span></span> <span data-ttu-id="54e29-187">**Restrito** para clientes Windows ou **RemoteSigned** para Windows Servers.</span><span class="sxs-lookup"><span data-stu-id="54e29-187">**Restricted** for Windows clients or **RemoteSigned** for Windows servers.</span></span>
- <span data-ttu-id="54e29-188">**RemoteSigned** .</span><span class="sxs-lookup"><span data-stu-id="54e29-188">**RemoteSigned** .</span></span> <span data-ttu-id="54e29-189">Requer que todos os scripts e arquivos de configuração baixados da Internet sejam assinados por um fornecedor confiável.</span><span class="sxs-lookup"><span data-stu-id="54e29-189">Requires that all scripts and configuration files downloaded from the Internet are signed by a trusted publisher.</span></span> <span data-ttu-id="54e29-190">A política de execução padrão para computadores Windows Server.</span><span class="sxs-lookup"><span data-stu-id="54e29-190">The default execution policy for Windows server computers.</span></span>
- <span data-ttu-id="54e29-191">**Restrito** .</span><span class="sxs-lookup"><span data-stu-id="54e29-191">**Restricted** .</span></span> <span data-ttu-id="54e29-192">Não carrega arquivos de configuração nem executa scripts.</span><span class="sxs-lookup"><span data-stu-id="54e29-192">Doesn't load configuration files or run scripts.</span></span> <span data-ttu-id="54e29-193">Os computadores cliente do Windows da política de execução padrão.</span><span class="sxs-lookup"><span data-stu-id="54e29-193">The default execution policy Windows client computers.</span></span>
- <span data-ttu-id="54e29-194">**Indefinido** .</span><span class="sxs-lookup"><span data-stu-id="54e29-194">**Undefined** .</span></span> <span data-ttu-id="54e29-195">Nenhuma política de execução está definida para o escopo.</span><span class="sxs-lookup"><span data-stu-id="54e29-195">No execution policy is set for the scope.</span></span> <span data-ttu-id="54e29-196">Remove uma política de execução atribuída de um escopo que não está definido por um Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="54e29-196">Removes an assigned execution policy from a scope that is not set by a Group Policy.</span></span> <span data-ttu-id="54e29-197">Se a política de execução em todos os escopos for **indefinida** , a política de execução efetiva será **restrita** .</span><span class="sxs-lookup"><span data-stu-id="54e29-197">If the execution policy in all scopes is **Undefined** , the effective execution policy is **Restricted** .</span></span>
- <span data-ttu-id="54e29-198">**Irrestrito** .</span><span class="sxs-lookup"><span data-stu-id="54e29-198">**Unrestricted** .</span></span> <span data-ttu-id="54e29-199">A partir do PowerShell 6,0, essa é a política de execução padrão para computadores não Windows e não pode ser alterada.</span><span class="sxs-lookup"><span data-stu-id="54e29-199">Beginning in PowerShell 6.0, this is the default execution policy for non-Windows computers and can't be changed.</span></span> <span data-ttu-id="54e29-200">Carrega todos os arquivos de configuração e executa todos os scripts.</span><span class="sxs-lookup"><span data-stu-id="54e29-200">Loads all configuration files and runs all scripts.</span></span> <span data-ttu-id="54e29-201">Se você executar um script não assinado que foi baixado da Internet, sua permissão será solicitada antes de ser executada.</span><span class="sxs-lookup"><span data-stu-id="54e29-201">If you run an unsigned script that was downloaded from the internet, you're prompted for permission before it runs.</span></span>

```yaml
Type: Microsoft.PowerShell.ExecutionPolicy
Parameter Sets: (All)
Aliases:
Accepted values: AllSigned, Bypass, Default, RemoteSigned, Restricted, Undefined, Unrestricted

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="54e29-202">-Force</span><span class="sxs-lookup"><span data-stu-id="54e29-202">-Force</span></span>

<span data-ttu-id="54e29-203">Suprime todas as solicitações de confirmação.</span><span class="sxs-lookup"><span data-stu-id="54e29-203">Suppresses all the confirmation prompts.</span></span> <span data-ttu-id="54e29-204">Tome cuidado com esse parâmetro para evitar resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="54e29-204">Use caution with this parameter to avoid unexpected results.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="54e29-205">-Escopo</span><span class="sxs-lookup"><span data-stu-id="54e29-205">-Scope</span></span>

<span data-ttu-id="54e29-206">Especifica o escopo que é afetado por uma política de execução.</span><span class="sxs-lookup"><span data-stu-id="54e29-206">Specifies the scope that is affected by an execution policy.</span></span> <span data-ttu-id="54e29-207">O escopo padrão é **LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="54e29-207">The default scope is **LocalMachine** .</span></span>

<span data-ttu-id="54e29-208">A política de execução efetiva é determinada pela ordem de precedência da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="54e29-208">The effective execution policy is determined by the order of precedence as follows:</span></span>

- <span data-ttu-id="54e29-209">**MachinePolicy** .</span><span class="sxs-lookup"><span data-stu-id="54e29-209">**MachinePolicy** .</span></span> <span data-ttu-id="54e29-210">Definido por um Política de Grupo para todos os usuários do computador.</span><span class="sxs-lookup"><span data-stu-id="54e29-210">Set by a Group Policy for all users of the computer.</span></span>
- <span data-ttu-id="54e29-211">**UserPolicy** .</span><span class="sxs-lookup"><span data-stu-id="54e29-211">**UserPolicy** .</span></span> <span data-ttu-id="54e29-212">Definido por um Política de Grupo para o usuário atual do computador.</span><span class="sxs-lookup"><span data-stu-id="54e29-212">Set by a Group Policy for the current user of the computer.</span></span>
- <span data-ttu-id="54e29-213">**Processar** .</span><span class="sxs-lookup"><span data-stu-id="54e29-213">**Process** .</span></span> <span data-ttu-id="54e29-214">Afeta apenas a sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="54e29-214">Affects only the current PowerShell session.</span></span>
- <span data-ttu-id="54e29-215">**CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="54e29-215">**CurrentUser** .</span></span> <span data-ttu-id="54e29-216">Afeta somente o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="54e29-216">Affects only the current user.</span></span>
- <span data-ttu-id="54e29-217">**LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="54e29-217">**LocalMachine** .</span></span> <span data-ttu-id="54e29-218">Escopo padrão que afeta todos os usuários do computador.</span><span class="sxs-lookup"><span data-stu-id="54e29-218">Default scope that affects all users of the computer.</span></span>

<span data-ttu-id="54e29-219">O escopo do **processo** afeta apenas a sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="54e29-219">The **Process** scope only affects the current PowerShell session.</span></span> <span data-ttu-id="54e29-220">A política de execução é salva na variável de ambiente `$env:PSExecutionPolicyPreference` , em vez de no registro.</span><span class="sxs-lookup"><span data-stu-id="54e29-220">The execution policy is saved in the environment variable `$env:PSExecutionPolicyPreference`, rather than the registry.</span></span> <span data-ttu-id="54e29-221">Quando a sessão do PowerShell é fechada, a variável e o valor são excluídos.</span><span class="sxs-lookup"><span data-stu-id="54e29-221">When the PowerShell session is closed, the variable and value are deleted.</span></span>

<span data-ttu-id="54e29-222">As políticas de execução para o escopo **CurrentUser** são gravadas no hive do registro **HKEY_LOCAL_USER** .</span><span class="sxs-lookup"><span data-stu-id="54e29-222">Execution policies for the **CurrentUser** scope are written to the registry hive **HKEY_LOCAL_USER** .</span></span>

<span data-ttu-id="54e29-223">As políticas de execução para o escopo **LocalMachine** são gravadas no hive do registro **HKEY_LOCAL_MACHINE** .</span><span class="sxs-lookup"><span data-stu-id="54e29-223">Execution policies for the **LocalMachine** scope are written to the registry hive **HKEY_LOCAL_MACHINE** .</span></span>

```yaml
Type: Microsoft.PowerShell.ExecutionPolicyScope
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, LocalMachine, MachinePolicy, Process, UserPolicy

Required: False
Position: 1
Default value: LocalMachine
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="54e29-224">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="54e29-224">-WhatIf</span></span>

<span data-ttu-id="54e29-225">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="54e29-225">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="54e29-226">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="54e29-226">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="54e29-227">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="54e29-227">CommonParameters</span></span>

<span data-ttu-id="54e29-228">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="54e29-228">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="54e29-229">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="54e29-229">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="54e29-230">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="54e29-230">INPUTS</span></span>

### <span data-ttu-id="54e29-231">Microsoft.PowerShell.ExecutionPolicy, System. String</span><span class="sxs-lookup"><span data-stu-id="54e29-231">Microsoft.PowerShell.ExecutionPolicy, System.String</span></span>

<span data-ttu-id="54e29-232">É possível canalizar um objeto de política de execução ou uma cadeia de caracteres que contém o nome de uma política de execução para `Set-ExecutionPolicy` .</span><span class="sxs-lookup"><span data-stu-id="54e29-232">You can pipe an execution policy object or a string that contains the name of an execution policy to `Set-ExecutionPolicy`.</span></span>

## <span data-ttu-id="54e29-233">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="54e29-233">OUTPUTS</span></span>

### <span data-ttu-id="54e29-234">Nenhum</span><span class="sxs-lookup"><span data-stu-id="54e29-234">None</span></span>

<span data-ttu-id="54e29-235">`Set-ExecutionPolicy` Não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="54e29-235">`Set-ExecutionPolicy` doesn't return any output.</span></span>

## <span data-ttu-id="54e29-236">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="54e29-236">NOTES</span></span>

<span data-ttu-id="54e29-237">`Set-ExecutionPolicy` Não altera os escopos **MachinePolicy** e **UserPolicy** porque eles são definidos por políticas de grupo.</span><span class="sxs-lookup"><span data-stu-id="54e29-237">`Set-ExecutionPolicy` doesn't change the **MachinePolicy** and **UserPolicy** scopes because they are set by Group Policies.</span></span>

<span data-ttu-id="54e29-238">`Set-ExecutionPolicy` não substitui um Política de Grupo, mesmo que a preferência do usuário seja mais restritiva do que a política.</span><span class="sxs-lookup"><span data-stu-id="54e29-238">`Set-ExecutionPolicy` doesn't override a Group Policy, even if the user preference is more restrictive than the policy.</span></span>

<span data-ttu-id="54e29-239">Se a Política de Grupo **ativar a execução do script** estiver habilitada para o computador ou usuário, a preferência do usuário será salva, mas não será eficaz.</span><span class="sxs-lookup"><span data-stu-id="54e29-239">If the Group Policy **Turn on Script Execution** is enabled for the computer or user, the user preference is saved, but it is not effective.</span></span> <span data-ttu-id="54e29-240">O PowerShell exibe uma mensagem que explica o conflito.</span><span class="sxs-lookup"><span data-stu-id="54e29-240">PowerShell displays a message that explains the conflict.</span></span>

## <span data-ttu-id="54e29-241">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="54e29-241">RELATED LINKS</span></span>

[<span data-ttu-id="54e29-242">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="54e29-242">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[<span data-ttu-id="54e29-243">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="54e29-243">about_Group_Policy_Settings</span></span>](../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md)

[<span data-ttu-id="54e29-244">about_Providers</span><span class="sxs-lookup"><span data-stu-id="54e29-244">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="54e29-245">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="54e29-245">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)

[<span data-ttu-id="54e29-246">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="54e29-246">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[<span data-ttu-id="54e29-247">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="54e29-247">Get-ExecutionPolicy</span></span>](Get-ExecutionPolicy.md)

[<span data-ttu-id="54e29-248">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="54e29-248">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="54e29-249">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="54e29-249">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)

[<span data-ttu-id="54e29-250">Unblock-File</span><span class="sxs-lookup"><span data-stu-id="54e29-250">Unblock-File</span></span>](../Microsoft.PowerShell.Utility/Unblock-File.md)

