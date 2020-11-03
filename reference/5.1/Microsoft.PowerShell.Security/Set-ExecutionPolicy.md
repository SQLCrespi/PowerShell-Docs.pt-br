---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 3/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ExecutionPolicy
ms.openlocfilehash: 313ff4f2d3fc89263cdf4d0ede860ef8e538a2ea
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193867"
---
# <span data-ttu-id="75055-103">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="75055-103">Set-ExecutionPolicy</span></span>

## <span data-ttu-id="75055-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="75055-104">SYNOPSIS</span></span>
<span data-ttu-id="75055-105">Define as políticas de execução do PowerShell para computadores Windows.</span><span class="sxs-lookup"><span data-stu-id="75055-105">Sets the PowerShell execution policies for Windows computers.</span></span>

## <span data-ttu-id="75055-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="75055-106">SYNTAX</span></span>

### <span data-ttu-id="75055-107">Tudo</span><span class="sxs-lookup"><span data-stu-id="75055-107">All</span></span>

```
Set-ExecutionPolicy [-ExecutionPolicy] <ExecutionPolicy> [[-Scope] <ExecutionPolicyScope>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="75055-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="75055-108">DESCRIPTION</span></span>

<span data-ttu-id="75055-109">O `Set-ExecutionPolicy` cmdlet altera as políticas de execução do PowerShell para computadores Windows.</span><span class="sxs-lookup"><span data-stu-id="75055-109">The `Set-ExecutionPolicy` cmdlet changes PowerShell execution policies for Windows computers.</span></span> <span data-ttu-id="75055-110">Para obter mais informações, consulte [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="75055-110">For more information, see [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span></span>

<span data-ttu-id="75055-111">Uma política de execução faz parte da estratégia de segurança do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75055-111">An execution policy is part of the PowerShell security strategy.</span></span> <span data-ttu-id="75055-112">As políticas de execução determinam se você pode carregar arquivos de configuração, como seu perfil do PowerShell, ou executar scripts.</span><span class="sxs-lookup"><span data-stu-id="75055-112">Execution policies determine whether you can load configuration files, such as your PowerShell profile, or run scripts.</span></span> <span data-ttu-id="75055-113">E se os scripts devem ser assinados digitalmente antes de serem executados.</span><span class="sxs-lookup"><span data-stu-id="75055-113">And, whether scripts must be digitally signed before they are run.</span></span>

<span data-ttu-id="75055-114">O `Set-ExecutionPolicy` escopo padrão do cmdlet é **LocalMachine** , o que afeta todos os que usam o computador.</span><span class="sxs-lookup"><span data-stu-id="75055-114">The `Set-ExecutionPolicy` cmdlet's default scope is **LocalMachine** , which affects everyone who uses the computer.</span></span> <span data-ttu-id="75055-115">Para alterar a política de execução para **LocalMachine** , inicie o PowerShell com **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="75055-115">To change the execution policy for **LocalMachine** , start PowerShell with **Run as Administrator** .</span></span>

<span data-ttu-id="75055-116">Para exibir as políticas de execução para cada escopo na ordem de precedência, use `Get-ExecutionPolicy -List` .</span><span class="sxs-lookup"><span data-stu-id="75055-116">To display the execution policies for each scope in the order of precedence, use `Get-ExecutionPolicy -List`.</span></span> <span data-ttu-id="75055-117">Para ver a política de execução efetiva para sua sessão do PowerShell, use `Get-ExecutionPolicy` sem parâmetros.</span><span class="sxs-lookup"><span data-stu-id="75055-117">To see the effective execution policy for your PowerShell session use `Get-ExecutionPolicy` with no parameters.</span></span>

## <span data-ttu-id="75055-118">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="75055-118">EXAMPLES</span></span>

### <span data-ttu-id="75055-119">Exemplo 1: definir uma política de execução</span><span class="sxs-lookup"><span data-stu-id="75055-119">Example 1: Set an execution policy</span></span>

<span data-ttu-id="75055-120">Este exemplo mostra como definir a política de execução para o computador local.</span><span class="sxs-lookup"><span data-stu-id="75055-120">This example shows how to set the execution policy for the local computer.</span></span>

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

<span data-ttu-id="75055-121">O `Set-ExecutionPolicy` cmdlet usa o parâmetro **ExecutionPolicy** para especificar a política **RemoteSigned** .</span><span class="sxs-lookup"><span data-stu-id="75055-121">The `Set-ExecutionPolicy` cmdlet uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="75055-122">O parâmetro **Scope** especifica o valor de escopo padrão, **LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="75055-122">The **Scope** parameter specifies the default scope value, **LocalMachine** .</span></span> <span data-ttu-id="75055-123">Para exibir as configurações de política de execução, use o `Get-ExecutionPolicy` cmdlet com o parâmetro **list** .</span><span class="sxs-lookup"><span data-stu-id="75055-123">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="75055-124">Exemplo 2: definir uma política de execução que está em conflito com um Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="75055-124">Example 2: Set an execution policy that conflicts with a Group Policy</span></span>

<span data-ttu-id="75055-125">Esse comando tenta definir a política de execução do escopo de **LocalMachine** como **restrita** .</span><span class="sxs-lookup"><span data-stu-id="75055-125">This command attempts to set the **LocalMachine** scope's execution policy to **Restricted** .</span></span>
<span data-ttu-id="75055-126">**LocalMachine** é mais restritiva, mas não é a política efetiva porque está em conflito com um política de grupo.</span><span class="sxs-lookup"><span data-stu-id="75055-126">**LocalMachine** is more restrictive, but isn't the effective policy because it conflicts with a Group Policy.</span></span> <span data-ttu-id="75055-127">A política **restrita** é gravada no hive do registro **HKEY_LOCAL_MACHINE** .</span><span class="sxs-lookup"><span data-stu-id="75055-127">The **Restricted** policy is written to the registry hive **HKEY_LOCAL_MACHINE** .</span></span>

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

<span data-ttu-id="75055-128">O `Set-ExecutionPolicy` cmdlet usa o parâmetro **ExecutionPolicy** para especificar a política **restrita** .</span><span class="sxs-lookup"><span data-stu-id="75055-128">The `Set-ExecutionPolicy` cmdlet uses the **ExecutionPolicy** parameter to specify the **Restricted** policy.</span></span> <span data-ttu-id="75055-129">O parâmetro **Scope** especifica o valor de escopo padrão, **LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="75055-129">The **Scope** parameter specifies the default scope value, **LocalMachine** .</span></span>
<span data-ttu-id="75055-130">O `Get-ChildItem` cmdlet usa o parâmetro **Path** com o provedor **HKLM** para especificar o local do registro.</span><span class="sxs-lookup"><span data-stu-id="75055-130">The `Get-ChildItem` cmdlet uses the **Path** parameter with the **HKLM** provider to specify registry location.</span></span>

### <span data-ttu-id="75055-131">Exemplo 3: aplicar a política de execução de um computador remoto a um computador local</span><span class="sxs-lookup"><span data-stu-id="75055-131">Example 3: Apply the execution policy from a remote computer to a local computer</span></span>

<span data-ttu-id="75055-132">Esse comando obtém o objeto de política de execução de um computador remoto e define a política no computador local.</span><span class="sxs-lookup"><span data-stu-id="75055-132">This command gets the execution policy object from a remote computer and sets the policy on the local computer.</span></span> <span data-ttu-id="75055-133">`Get-ExecutionPolicy` envia um objeto **Microsoft.PowerShell.ExecutionPolicy** para baixo do pipeline.</span><span class="sxs-lookup"><span data-stu-id="75055-133">`Get-ExecutionPolicy` sends a **Microsoft.PowerShell.ExecutionPolicy** object down the pipeline.</span></span> <span data-ttu-id="75055-134">`Set-ExecutionPolicy` aceita a entrada de pipeline e não requer o parâmetro **ExecutionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="75055-134">`Set-ExecutionPolicy` accepts pipeline input and doesn't require the **ExecutionPolicy** parameter.</span></span>

```
PS> Invoke-Command -ComputerName Server01 -ScriptBlock { Get-ExecutionPolicy } | Set-ExecutionPolicy
```

<span data-ttu-id="75055-135">O `Invoke-Command` cmdlet é executado no computador local e envia o **scriptblock** para o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="75055-135">The `Invoke-Command` cmdlet is executed at the local computer and sends the **ScriptBlock** to the remote computer.</span></span> <span data-ttu-id="75055-136">O parâmetro **ComputerName** especifica o computador remoto, **Server01** .</span><span class="sxs-lookup"><span data-stu-id="75055-136">The **ComputerName** parameter specifies the remote computer, **Server01** .</span></span> <span data-ttu-id="75055-137">O parâmetro **scriptblock** é executado `Get-ExecutionPolicy` no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="75055-137">The **ScriptBlock** parameter runs `Get-ExecutionPolicy` on the remote computer.</span></span> <span data-ttu-id="75055-138">O `Get-ExecutionPolicy` objeto é enviado ao pipeline para o `Set-ExecutionPolicy` .</span><span class="sxs-lookup"><span data-stu-id="75055-138">The `Get-ExecutionPolicy` object is sent down the pipeline to the `Set-ExecutionPolicy`.</span></span>
<span data-ttu-id="75055-139">`Set-ExecutionPolicy` aplica a política de execução ao escopo padrão do computador local, **LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="75055-139">`Set-ExecutionPolicy` applies the execution policy to the local computer's default scope, **LocalMachine** .</span></span>

### <span data-ttu-id="75055-140">Exemplo 4: definir o escopo para uma política de execução</span><span class="sxs-lookup"><span data-stu-id="75055-140">Example 4: Set the scope for an execution policy</span></span>

<span data-ttu-id="75055-141">Este exemplo mostra como definir uma política de execução para um escopo especificado, **CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="75055-141">This example shows how to set an execution policy for a specified scope, **CurrentUser** .</span></span> <span data-ttu-id="75055-142">O escopo **CurrentUser** só afeta o usuário que define esse escopo.</span><span class="sxs-lookup"><span data-stu-id="75055-142">The **CurrentUser** scope only affects the user who sets this scope.</span></span>

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

<span data-ttu-id="75055-143">`Set-ExecutionPolicy` usa o parâmetro **ExecutionPolicy** para especificar a política **AllSigned** .</span><span class="sxs-lookup"><span data-stu-id="75055-143">`Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **AllSigned** policy.</span></span>
<span data-ttu-id="75055-144">O parâmetro **Scope** especifica o **CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="75055-144">The **Scope** parameter specifies the **CurrentUser** .</span></span> <span data-ttu-id="75055-145">Para exibir as configurações de política de execução, use o `Get-ExecutionPolicy` cmdlet com o parâmetro **list** .</span><span class="sxs-lookup"><span data-stu-id="75055-145">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

<span data-ttu-id="75055-146">A política de execução efetiva para o usuário torna-se **AllSigned** .</span><span class="sxs-lookup"><span data-stu-id="75055-146">The effective execution policy for the user becomes **AllSigned** .</span></span>

### <span data-ttu-id="75055-147">Exemplo 5: remover a política de execução para o usuário atual</span><span class="sxs-lookup"><span data-stu-id="75055-147">Example 5: Remove the execution policy for the current user</span></span>

<span data-ttu-id="75055-148">Este exemplo mostra como usar a política de execução **indefinida** para remover uma política de execução para um escopo especificado.</span><span class="sxs-lookup"><span data-stu-id="75055-148">This example shows how use the **Undefined** execution policy to remove an execution policy for a specified scope.</span></span>

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

<span data-ttu-id="75055-149">`Set-ExecutionPolicy` usa o parâmetro **ExecutionPolicy** para especificar a política **indefinida** .</span><span class="sxs-lookup"><span data-stu-id="75055-149">`Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **Undefined** policy.</span></span>
<span data-ttu-id="75055-150">O parâmetro **Scope** especifica o **CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="75055-150">The **Scope** parameter specifies the **CurrentUser** .</span></span> <span data-ttu-id="75055-151">Para exibir as configurações de política de execução, use o `Get-ExecutionPolicy` cmdlet com o parâmetro **list** .</span><span class="sxs-lookup"><span data-stu-id="75055-151">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="75055-152">Exemplo 6: definir a política de execução para a sessão atual do PowerShell</span><span class="sxs-lookup"><span data-stu-id="75055-152">Example 6: Set the execution policy for the current PowerShell session</span></span>

<span data-ttu-id="75055-153">O escopo do **processo** afeta apenas a sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75055-153">The **Process** scope only affects the current PowerShell session.</span></span> <span data-ttu-id="75055-154">A política de execução é salva na variável de ambiente `$env:PSExecutionPolicyPreference` e é excluída quando a sessão é fechada.</span><span class="sxs-lookup"><span data-stu-id="75055-154">The execution policy is saved in the environment variable `$env:PSExecutionPolicyPreference` and is deleted when the session is closed.</span></span>

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

<span data-ttu-id="75055-155">O `Set-ExecutionPolicy` usa o parâmetro **ExecutionPolicy** para especificar a política **AllSigned** .</span><span class="sxs-lookup"><span data-stu-id="75055-155">The `Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **AllSigned** policy.</span></span> <span data-ttu-id="75055-156">O parâmetro **Scope** especifica o **processo** de valor.</span><span class="sxs-lookup"><span data-stu-id="75055-156">The **Scope** parameter specifies the value **Process** .</span></span> <span data-ttu-id="75055-157">Para exibir as configurações de política de execução, use o `Get-ExecutionPolicy` cmdlet com o parâmetro **list** .</span><span class="sxs-lookup"><span data-stu-id="75055-157">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="75055-158">Exemplo 7: desbloquear um script para executá-lo sem alterar a política de execução</span><span class="sxs-lookup"><span data-stu-id="75055-158">Example 7: Unblock a script to run it without changing the execution policy</span></span>

<span data-ttu-id="75055-159">Este exemplo mostra como a política de execução **RemoteSigned** impede que você execute scripts não assinados.</span><span class="sxs-lookup"><span data-stu-id="75055-159">This example shows how the **RemoteSigned** execution policy prevents you from running unsigned scripts.</span></span>

<span data-ttu-id="75055-160">Uma prática recomendada é ler o código do script e verificar se ele é seguro **antes** de usar o `Unblock-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="75055-160">A best practice is to read the script's code and verify it's safe **before** using the `Unblock-File` cmdlet.</span></span> <span data-ttu-id="75055-161">O `Unblock-File` cmdlet desbloqueia scripts para que eles possam ser executados, mas não altera a política de execução.</span><span class="sxs-lookup"><span data-stu-id="75055-161">The `Unblock-File` cmdlet unblocks scripts so they can run, but doesn't change the execution policy.</span></span>

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

<span data-ttu-id="75055-162">O `Set-ExecutionPolicy` usa o parâmetro **ExecutionPolicy** para especificar a política de **RemoteSigned** .</span><span class="sxs-lookup"><span data-stu-id="75055-162">The `Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="75055-163">A política é definida para o escopo padrão, **LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="75055-163">The policy is set for the default scope, **LocalMachine** .</span></span>

<span data-ttu-id="75055-164">O `Get-ExecutionPolicy` cmdlet mostra que **RemoteSigned** é a política de execução efetiva para a sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75055-164">The `Get-ExecutionPolicy` cmdlet shows that **RemoteSigned** is the effective execution policy for the current PowerShell session.</span></span>

<span data-ttu-id="75055-165">O script de **Start-ActivityTracker.ps1** é executado a partir do diretório atual.</span><span class="sxs-lookup"><span data-stu-id="75055-165">The **Start-ActivityTracker.ps1** script is executed from the current directory.</span></span> <span data-ttu-id="75055-166">O script é bloqueado por **RemoteSigned** porque o script não está assinado digitalmente.</span><span class="sxs-lookup"><span data-stu-id="75055-166">The script is blocked by **RemoteSigned** because the script isn't digitally signed.</span></span>

<span data-ttu-id="75055-167">Neste exemplo, o código do script foi revisado e verificado como seguro para ser executado.</span><span class="sxs-lookup"><span data-stu-id="75055-167">For this example, the script's code was reviewed and verified as safe to run.</span></span> <span data-ttu-id="75055-168">O `Unblock-File` cmdlet usa o parâmetro **Path** para desbloquear o script.</span><span class="sxs-lookup"><span data-stu-id="75055-168">The `Unblock-File` cmdlet uses the **Path** parameter to unblock the script.</span></span>

<span data-ttu-id="75055-169">Para verificar se `Unblock-File` a política de execução não foi alterada, `Get-ExecutionPolicy` exibe a política de execução efetiva, **RemoteSigned** .</span><span class="sxs-lookup"><span data-stu-id="75055-169">To verify that `Unblock-File` didn't change the execution policy, `Get-ExecutionPolicy` displays the effective execution policy, **RemoteSigned** .</span></span>

<span data-ttu-id="75055-170">O script, **Start-ActivityTracker.ps1** é executado a partir do diretório atual.</span><span class="sxs-lookup"><span data-stu-id="75055-170">The script, **Start-ActivityTracker.ps1** is executed from the current directory.</span></span> <span data-ttu-id="75055-171">O script começa a ser executado porque foi desbloqueado pelo `Unblock-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="75055-171">The script begins to run because it was unblocked by the `Unblock-File` cmdlet.</span></span>

## <span data-ttu-id="75055-172">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="75055-172">PARAMETERS</span></span>

### <span data-ttu-id="75055-173">-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="75055-173">-ExecutionPolicy</span></span>

<span data-ttu-id="75055-174">Especifica a política de execução.</span><span class="sxs-lookup"><span data-stu-id="75055-174">Specifies the execution policy.</span></span> <span data-ttu-id="75055-175">Se não houver nenhuma política de grupo e a diretiva de execução de cada escopo estiver definida como **indefinida** , a **restrição** se tornará a política efetiva para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="75055-175">If there are no Group Policies and each scope's execution policy is set to **Undefined** , then **Restricted** becomes the effective policy for all users.</span></span>

<span data-ttu-id="75055-176">Os valores de política de execução aceitáveis são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="75055-176">The acceptable execution policy values are as follows:</span></span>

- <span data-ttu-id="75055-177">**AllSigned** .</span><span class="sxs-lookup"><span data-stu-id="75055-177">**AllSigned** .</span></span> <span data-ttu-id="75055-178">Requer que todos os scripts e arquivos de configuração sejam assinados por um fornecedor confiável, incluindo scripts gravados no computador local.</span><span class="sxs-lookup"><span data-stu-id="75055-178">Requires that all scripts and configuration files are signed by a trusted publisher, including scripts written on the local computer.</span></span>
- <span data-ttu-id="75055-179">**Bypass** .</span><span class="sxs-lookup"><span data-stu-id="75055-179">**Bypass** .</span></span> <span data-ttu-id="75055-180">Nada está bloqueado e não há avisos ou prompts.</span><span class="sxs-lookup"><span data-stu-id="75055-180">Nothing is blocked and there are no warnings or prompts.</span></span>
- <span data-ttu-id="75055-181">**Default** .</span><span class="sxs-lookup"><span data-stu-id="75055-181">**Default** .</span></span> <span data-ttu-id="75055-182">Define a política de execução padrão.</span><span class="sxs-lookup"><span data-stu-id="75055-182">Sets the default execution policy.</span></span> <span data-ttu-id="75055-183">**Restrito** para clientes Windows ou **RemoteSigned** para Windows Servers.</span><span class="sxs-lookup"><span data-stu-id="75055-183">**Restricted** for Windows clients or **RemoteSigned** for Windows servers.</span></span>
- <span data-ttu-id="75055-184">**RemoteSigned** .</span><span class="sxs-lookup"><span data-stu-id="75055-184">**RemoteSigned** .</span></span> <span data-ttu-id="75055-185">Requer que todos os scripts e arquivos de configuração baixados da Internet sejam assinados por um fornecedor confiável.</span><span class="sxs-lookup"><span data-stu-id="75055-185">Requires that all scripts and configuration files downloaded from the Internet are signed by a trusted publisher.</span></span> <span data-ttu-id="75055-186">A política de execução padrão para computadores Windows Server.</span><span class="sxs-lookup"><span data-stu-id="75055-186">The default execution policy for Windows server computers.</span></span>
- <span data-ttu-id="75055-187">**Restrito** .</span><span class="sxs-lookup"><span data-stu-id="75055-187">**Restricted** .</span></span> <span data-ttu-id="75055-188">Não carrega arquivos de configuração nem executa scripts.</span><span class="sxs-lookup"><span data-stu-id="75055-188">Doesn't load configuration files or run scripts.</span></span> <span data-ttu-id="75055-189">Os computadores cliente do Windows da política de execução padrão.</span><span class="sxs-lookup"><span data-stu-id="75055-189">The default execution policy Windows client computers.</span></span>
- <span data-ttu-id="75055-190">**Indefinido** .</span><span class="sxs-lookup"><span data-stu-id="75055-190">**Undefined** .</span></span> <span data-ttu-id="75055-191">Nenhuma política de execução está definida para o escopo.</span><span class="sxs-lookup"><span data-stu-id="75055-191">No execution policy is set for the scope.</span></span> <span data-ttu-id="75055-192">Remove uma política de execução atribuída de um escopo que não está definido por um Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="75055-192">Removes an assigned execution policy from a scope that is not set by a Group Policy.</span></span> <span data-ttu-id="75055-193">Se a política de execução em todos os escopos for **indefinida** , a política de execução efetiva será **restrita** .</span><span class="sxs-lookup"><span data-stu-id="75055-193">If the execution policy in all scopes is **Undefined** , the effective execution policy is **Restricted** .</span></span>
- <span data-ttu-id="75055-194">**Irrestrito** .</span><span class="sxs-lookup"><span data-stu-id="75055-194">**Unrestricted** .</span></span> <span data-ttu-id="75055-195">Carrega todos os arquivos de configuração e executa todos os scripts.</span><span class="sxs-lookup"><span data-stu-id="75055-195">Loads all configuration files and runs all scripts.</span></span> <span data-ttu-id="75055-196">Se executar um script não assinado baixado da Internet, será solicitado, antes da execução, que você tenha permissão.</span><span class="sxs-lookup"><span data-stu-id="75055-196">If you run an unsigned script that was downloaded from the Internet, you are prompted for permission before it runs.</span></span>

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

### <span data-ttu-id="75055-197">-Force</span><span class="sxs-lookup"><span data-stu-id="75055-197">-Force</span></span>

<span data-ttu-id="75055-198">Suprime todas as solicitações de confirmação.</span><span class="sxs-lookup"><span data-stu-id="75055-198">Suppresses all the confirmation prompts.</span></span> <span data-ttu-id="75055-199">Tome cuidado com esse parâmetro para evitar resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="75055-199">Use caution with this parameter to avoid unexpected results.</span></span>

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

### <span data-ttu-id="75055-200">-Escopo</span><span class="sxs-lookup"><span data-stu-id="75055-200">-Scope</span></span>

<span data-ttu-id="75055-201">Especifica o escopo que é afetado por uma política de execução.</span><span class="sxs-lookup"><span data-stu-id="75055-201">Specifies the scope that is affected by an execution policy.</span></span> <span data-ttu-id="75055-202">O escopo padrão é **LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="75055-202">The default scope is **LocalMachine** .</span></span>

<span data-ttu-id="75055-203">A política de execução efetiva é determinada pela ordem de precedência da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="75055-203">The effective execution policy is determined by the order of precedence as follows:</span></span>

- <span data-ttu-id="75055-204">**MachinePolicy** .</span><span class="sxs-lookup"><span data-stu-id="75055-204">**MachinePolicy** .</span></span> <span data-ttu-id="75055-205">Definido por um Política de Grupo para todos os usuários do computador.</span><span class="sxs-lookup"><span data-stu-id="75055-205">Set by a Group Policy for all users of the computer.</span></span>
- <span data-ttu-id="75055-206">**UserPolicy** .</span><span class="sxs-lookup"><span data-stu-id="75055-206">**UserPolicy** .</span></span> <span data-ttu-id="75055-207">Definido por um Política de Grupo para o usuário atual do computador.</span><span class="sxs-lookup"><span data-stu-id="75055-207">Set by a Group Policy for the current user of the computer.</span></span>
- <span data-ttu-id="75055-208">**Processar** .</span><span class="sxs-lookup"><span data-stu-id="75055-208">**Process** .</span></span> <span data-ttu-id="75055-209">Afeta apenas a sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75055-209">Affects only the current PowerShell session.</span></span>
- <span data-ttu-id="75055-210">**CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="75055-210">**CurrentUser** .</span></span> <span data-ttu-id="75055-211">Afeta somente o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="75055-211">Affects only the current user.</span></span>
- <span data-ttu-id="75055-212">**LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="75055-212">**LocalMachine** .</span></span> <span data-ttu-id="75055-213">Escopo padrão que afeta todos os usuários do computador.</span><span class="sxs-lookup"><span data-stu-id="75055-213">Default scope that affects all users of the computer.</span></span>

<span data-ttu-id="75055-214">O escopo do **processo** afeta apenas a sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75055-214">The **Process** scope only affects the current PowerShell session.</span></span> <span data-ttu-id="75055-215">A política de execução é salva na variável de ambiente `$env:PSExecutionPolicyPreference` , em vez de no registro.</span><span class="sxs-lookup"><span data-stu-id="75055-215">The execution policy is saved in the environment variable `$env:PSExecutionPolicyPreference`, rather than the registry.</span></span> <span data-ttu-id="75055-216">Quando a sessão do PowerShell é fechada, a variável e o valor são excluídos.</span><span class="sxs-lookup"><span data-stu-id="75055-216">When the PowerShell session is closed, the variable and value are deleted.</span></span>

<span data-ttu-id="75055-217">As políticas de execução para o escopo **CurrentUser** são gravadas no hive do registro **HKEY_LOCAL_USER** .</span><span class="sxs-lookup"><span data-stu-id="75055-217">Execution policies for the **CurrentUser** scope are written to the registry hive **HKEY_LOCAL_USER** .</span></span>

<span data-ttu-id="75055-218">As políticas de execução para o escopo **LocalMachine** são gravadas no hive do registro **HKEY_LOCAL_MACHINE** .</span><span class="sxs-lookup"><span data-stu-id="75055-218">Execution policies for the **LocalMachine** scope are written to the registry hive **HKEY_LOCAL_MACHINE** .</span></span>

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

### <span data-ttu-id="75055-219">-Confirm</span><span class="sxs-lookup"><span data-stu-id="75055-219">-Confirm</span></span>

<span data-ttu-id="75055-220">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="75055-220">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="75055-221">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="75055-221">-WhatIf</span></span>

<span data-ttu-id="75055-222">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="75055-222">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="75055-223">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="75055-223">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="75055-224">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="75055-224">CommonParameters</span></span>

<span data-ttu-id="75055-225">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="75055-225">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="75055-226">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="75055-226">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="75055-227">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="75055-227">INPUTS</span></span>

### <span data-ttu-id="75055-228">Microsoft.PowerShell.ExecutionPolicy, System. String</span><span class="sxs-lookup"><span data-stu-id="75055-228">Microsoft.PowerShell.ExecutionPolicy, System.String</span></span>

<span data-ttu-id="75055-229">É possível canalizar um objeto de política de execução ou uma cadeia de caracteres que contém o nome de uma política de execução para `Set-ExecutionPolicy` .</span><span class="sxs-lookup"><span data-stu-id="75055-229">You can pipe an execution policy object or a string that contains the name of an execution policy to `Set-ExecutionPolicy`.</span></span>

## <span data-ttu-id="75055-230">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="75055-230">OUTPUTS</span></span>

### <span data-ttu-id="75055-231">Nenhum</span><span class="sxs-lookup"><span data-stu-id="75055-231">None</span></span>

<span data-ttu-id="75055-232">`Set-ExecutionPolicy` Não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="75055-232">`Set-ExecutionPolicy` doesn't return any output.</span></span>

## <span data-ttu-id="75055-233">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="75055-233">NOTES</span></span>

<span data-ttu-id="75055-234">`Set-ExecutionPolicy` Não altera os escopos **MachinePolicy** e **UserPolicy** porque eles são definidos por políticas de grupo.</span><span class="sxs-lookup"><span data-stu-id="75055-234">`Set-ExecutionPolicy` doesn't change the **MachinePolicy** and **UserPolicy** scopes because they are set by Group Policies.</span></span>

<span data-ttu-id="75055-235">`Set-ExecutionPolicy` não substitui um Política de Grupo, mesmo que a preferência do usuário seja mais restritiva do que a política.</span><span class="sxs-lookup"><span data-stu-id="75055-235">`Set-ExecutionPolicy` doesn't override a Group Policy, even if the user preference is more restrictive than the policy.</span></span>

<span data-ttu-id="75055-236">Se a Política de Grupo **ativar a execução do script** estiver habilitada para o computador ou usuário, a preferência do usuário será salva, mas não será eficaz.</span><span class="sxs-lookup"><span data-stu-id="75055-236">If the Group Policy **Turn on Script Execution** is enabled for the computer or user, the user preference is saved, but it is not effective.</span></span> <span data-ttu-id="75055-237">O PowerShell exibe uma mensagem que explica o conflito.</span><span class="sxs-lookup"><span data-stu-id="75055-237">PowerShell displays a message that explains the conflict.</span></span>

## <span data-ttu-id="75055-238">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="75055-238">RELATED LINKS</span></span>

[<span data-ttu-id="75055-239">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="75055-239">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[<span data-ttu-id="75055-240">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="75055-240">about_Group_Policy_Settings</span></span>](../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md)

[<span data-ttu-id="75055-241">about_Providers</span><span class="sxs-lookup"><span data-stu-id="75055-241">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="75055-242">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="75055-242">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)

[<span data-ttu-id="75055-243">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="75055-243">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[<span data-ttu-id="75055-244">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="75055-244">Get-ExecutionPolicy</span></span>](Get-ExecutionPolicy.md)

[<span data-ttu-id="75055-245">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="75055-245">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="75055-246">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="75055-246">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)

[<span data-ttu-id="75055-247">Unblock-File</span><span class="sxs-lookup"><span data-stu-id="75055-247">Unblock-File</span></span>](../Microsoft.PowerShell.Utility/Unblock-File.md)
