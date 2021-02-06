---
description: Descreve as políticas de execução do PowerShell e explica como gerenciá-las.
Locale: en-US
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Execution_Policies
ms.openlocfilehash: 1a2b8458b39233f96d47a52e3fea21b31e9b3c42
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597015"
---
# <a name="about-execution-policies"></a><span data-ttu-id="a9dbc-103">Sobre as políticas de execução</span><span class="sxs-lookup"><span data-stu-id="a9dbc-103">About Execution Policies</span></span>

## <a name="short-description"></a><span data-ttu-id="a9dbc-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="a9dbc-104">Short Description</span></span>
<span data-ttu-id="a9dbc-105">Descreve as políticas de execução do PowerShell e explica como gerenciá-las.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-105">Describes the PowerShell execution policies and explains how to manage them.</span></span>

## <a name="long-description"></a><span data-ttu-id="a9dbc-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="a9dbc-106">Long Description</span></span>

<span data-ttu-id="a9dbc-107">A política de execução do PowerShell é um recurso de segurança que controla as condições sob as quais o PowerShell carrega arquivos de configuração e executa scripts.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-107">PowerShell's execution policy is a safety feature that controls the conditions under which PowerShell loads configuration files and runs scripts.</span></span> <span data-ttu-id="a9dbc-108">Esse recurso ajuda a impedir a execução de scripts mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-108">This feature helps prevent the execution of malicious scripts.</span></span>

<span data-ttu-id="a9dbc-109">Em um computador com Windows, você pode definir uma política de execução para o computador local, para o usuário atual ou para uma sessão específica.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-109">On a Windows computer you can set an execution policy for the local computer, for the current user, or for a particular session.</span></span> <span data-ttu-id="a9dbc-110">Você também pode usar uma configuração de Política de Grupo para definir políticas de execução para computadores e usuários.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-110">You can also use a Group Policy setting to set execution policies for computers and users.</span></span>

<span data-ttu-id="a9dbc-111">As políticas de execução para o computador local e o usuário atual são armazenadas no registro.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-111">Execution policies for the local computer and current user are stored in the registry.</span></span> <span data-ttu-id="a9dbc-112">Você não precisa definir políticas de execução no seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-112">You don't need to set execution policies in your PowerShell profile.</span></span>
<span data-ttu-id="a9dbc-113">A política de execução para uma sessão específica é armazenada apenas na memória e é perdida quando a sessão é fechada.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-113">The execution policy for a particular session is stored only in memory and is lost when the session is closed.</span></span>

<span data-ttu-id="a9dbc-114">A política de execução não é um sistema de segurança que restringe as ações do usuário.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-114">The execution policy isn't a security system that restricts user actions.</span></span> <span data-ttu-id="a9dbc-115">Por exemplo, os usuários podem ignorar facilmente uma política digitando o conteúdo do script na linha de comando quando não puderem executar um script.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-115">For example, users can easily bypass a policy by typing the script contents at the command line when they cannot run a script.</span></span> <span data-ttu-id="a9dbc-116">Em vez disso, a política de execução ajuda os usuários a definir regras básicas e impede que eles as violem involuntariamente.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-116">Instead, the execution policy helps users to set basic rules and prevents them from violating them unintentionally.</span></span>

<span data-ttu-id="a9dbc-117">Em computadores não Windows, a política de execução padrão é **irrestrita** e não pode ser alterada.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-117">On non-Windows computers, the default execution policy is **Unrestricted** and cannot be changed.</span></span> <span data-ttu-id="a9dbc-118">O `Set-ExecutionPolicy` cmdlet está disponível, mas o PowerShell exibe uma mensagem de console que não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-118">The `Set-ExecutionPolicy` cmdlet is available, but PowerShell displays a console message that it's not supported.</span></span> <span data-ttu-id="a9dbc-119">Embora `Get-ExecutionPolicy` o retorne **irrestrito** em plataformas não Windows, o comportamento realmente corresponde ao **bypass** porque essas plataformas não implementam as zonas de segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-119">While `Get-ExecutionPolicy` returns **Unrestricted** on non-Windows platforms, the behavior really matches **Bypass** because those platforms do not implement the Windows Security Zones.</span></span>

## <a name="powershell-execution-policies"></a><span data-ttu-id="a9dbc-120">Políticas de execução do PowerShell</span><span class="sxs-lookup"><span data-stu-id="a9dbc-120">PowerShell execution policies</span></span>

<span data-ttu-id="a9dbc-121">A imposição dessas políticas só ocorre em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-121">Enforcement of these policies only occurs on Windows platforms.</span></span> <span data-ttu-id="a9dbc-122">As políticas de execução do PowerShell são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="a9dbc-122">The PowerShell execution policies are as follows:</span></span>

### <a name="allsigned"></a><span data-ttu-id="a9dbc-123">AllSigned</span><span class="sxs-lookup"><span data-stu-id="a9dbc-123">AllSigned</span></span>

- <span data-ttu-id="a9dbc-124">Os scripts podem ser executados.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-124">Scripts can run.</span></span>
- <span data-ttu-id="a9dbc-125">Requer que todos os arquivos de configuração e scripts sejam assinados por um editor confiável, incluindo scripts escritos no computador local.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-125">Requires that all scripts and configuration files be signed by a trusted publisher, including scripts that you write on the local computer.</span></span>
- <span data-ttu-id="a9dbc-126">O solicita antes de executar scripts de editores que você ainda não classificou como confiáveis ou não confiáveis.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-126">Prompts you before running scripts from publishers that you haven't yet classified as trusted or untrusted.</span></span>
- <span data-ttu-id="a9dbc-127">Riscos em execução assinada, mas mal-intencionados, scripts.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-127">Risks running signed, but malicious, scripts.</span></span>

### <a name="bypass"></a><span data-ttu-id="a9dbc-128">Bypass</span><span class="sxs-lookup"><span data-stu-id="a9dbc-128">Bypass</span></span>

- <span data-ttu-id="a9dbc-129">Nada está bloqueado e não há avisos ou prompts.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-129">Nothing is blocked and there are no warnings or prompts.</span></span>
- <span data-ttu-id="a9dbc-130">Essa política de execução é projetada para configurações nas quais um script do PowerShell é integrado a um aplicativo maior ou para configurações em que o PowerShell é a base para um programa que tem seu próprio modelo de segurança.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-130">This execution policy is designed for configurations in which a PowerShell script is built in to a larger application or for configurations in which PowerShell is the foundation for a program that has its own security model.</span></span>

### <a name="default"></a><span data-ttu-id="a9dbc-131">Padrão</span><span class="sxs-lookup"><span data-stu-id="a9dbc-131">Default</span></span>

- <span data-ttu-id="a9dbc-132">Define a política de execução padrão.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-132">Sets the default execution policy.</span></span>
- <span data-ttu-id="a9dbc-133">**Restrito** para clientes Windows.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-133">**Restricted** for Windows clients.</span></span>
- <span data-ttu-id="a9dbc-134">**RemoteSigned** para servidores Windows.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-134">**RemoteSigned** for Windows servers.</span></span>

### <a name="remotesigned"></a><span data-ttu-id="a9dbc-135">RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="a9dbc-135">RemoteSigned</span></span>

- <span data-ttu-id="a9dbc-136">A política de execução padrão para computadores Windows Server.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-136">The default execution policy for Windows server computers.</span></span>
- <span data-ttu-id="a9dbc-137">Os scripts podem ser executados.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-137">Scripts can run.</span></span>
- <span data-ttu-id="a9dbc-138">Requer uma assinatura digital de um editor confiável em arquivos de configuração e scripts que são baixados da Internet, que inclui programas de email e mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-138">Requires a digital signature from a trusted publisher on scripts and configuration files that are downloaded from the internet which includes email and instant messaging programs.</span></span>
- <span data-ttu-id="a9dbc-139">Não requer assinaturas digitais em scripts que são gravados no computador local e não baixados da Internet.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-139">Doesn't require digital signatures on scripts that are written on the local computer and not downloaded from the internet.</span></span>
- <span data-ttu-id="a9dbc-140">Executa scripts que são baixados da Internet e não assinados, se os scripts forem desbloqueados, como usando o `Unblock-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-140">Runs scripts that are downloaded from the internet and not signed, if the scripts are unblocked, such as by using the `Unblock-File` cmdlet.</span></span>
- <span data-ttu-id="a9dbc-141">Riscos que executam scripts não assinados de fontes diferentes da Internet e scripts assinados que podem ser mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-141">Risks running unsigned scripts from sources other than the internet and signed scripts that could be malicious.</span></span>

### <a name="restricted"></a><span data-ttu-id="a9dbc-142">Restritos</span><span class="sxs-lookup"><span data-stu-id="a9dbc-142">Restricted</span></span>

- <span data-ttu-id="a9dbc-143">A política de execução padrão para computadores cliente Windows.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-143">The default execution policy for Windows client computers.</span></span>
- <span data-ttu-id="a9dbc-144">Permite comandos individuais, mas não permite scripts.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-144">Permits individual commands, but does not allow scripts.</span></span>
- <span data-ttu-id="a9dbc-145">Impede a execução de todos os arquivos de script, incluindo arquivos de formatação e configuração ( `.ps1xml` ), arquivos de script de módulo ( `.psm1` ) e perfis do PowerShell ( `.ps1` ).</span><span class="sxs-lookup"><span data-stu-id="a9dbc-145">Prevents running of all script files, including formatting and configuration files (`.ps1xml`), module script files (`.psm1`), and PowerShell profiles (`.ps1`).</span></span>

### <a name="undefined"></a><span data-ttu-id="a9dbc-146">Indefinido</span><span class="sxs-lookup"><span data-stu-id="a9dbc-146">Undefined</span></span>

- <span data-ttu-id="a9dbc-147">Não há nenhuma política de execução definida no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-147">There is no execution policy set in the current scope.</span></span>
- <span data-ttu-id="a9dbc-148">Se a política de execução em todos os escopos for **indefinida**, a política de execução efetiva será **restrita** para clientes Windows e **RemoteSigned** para Windows Server.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-148">If the execution policy in all scopes is **Undefined**, the effective execution policy is **Restricted** for Windows clients and **RemoteSigned** for Windows Server.</span></span>

### <a name="unrestricted"></a><span data-ttu-id="a9dbc-149">Irrestrito</span><span class="sxs-lookup"><span data-stu-id="a9dbc-149">Unrestricted</span></span>

- <span data-ttu-id="a9dbc-150">A política de execução padrão para computadores não Windows e não pode ser alterada.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-150">The default execution policy for non-Windows computers and cannot be changed.</span></span>
- <span data-ttu-id="a9dbc-151">Os scripts não assinados podem ser executados.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-151">Unsigned scripts can run.</span></span> <span data-ttu-id="a9dbc-152">Há um risco de executar scripts mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-152">There is a risk of running malicious scripts.</span></span>
- <span data-ttu-id="a9dbc-153">Avisa o usuário antes de executar scripts e arquivos de configuração que não são da zona da intranet local.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-153">Warns the user before running scripts and configuration files that are not from the local intranet zone.</span></span>

> [!NOTE]
> <span data-ttu-id="a9dbc-154">Em sistemas que não diferenciam caminhos UNC (Convenção de nomenclatura universal) de caminhos da Internet, os scripts identificados por um caminho UNC podem não ter permissão para serem executados com a política de execução **RemoteSigned** .</span><span class="sxs-lookup"><span data-stu-id="a9dbc-154">On systems that do not distinguish Universal Naming Convention (UNC) paths from internet paths, scripts that are identified by a UNC path might not be permitted to run with the **RemoteSigned** execution policy.</span></span>

## <a name="execution-policy-scope"></a><span data-ttu-id="a9dbc-155">Escopo da política de execução</span><span class="sxs-lookup"><span data-stu-id="a9dbc-155">Execution policy scope</span></span>

<span data-ttu-id="a9dbc-156">Você pode definir uma política de execução que só é eficaz em um escopo específico.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-156">You can set an execution policy that is effective only in a particular scope.</span></span>

<span data-ttu-id="a9dbc-157">Os valores válidos para o **escopo** são **MachinePolicy**, **UserPolicy**, **process**, **CurrentUser** e **LocalMachine**.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-157">The valid values for **Scope** are **MachinePolicy**, **UserPolicy**, **Process**, **CurrentUser**, and **LocalMachine**.</span></span> <span data-ttu-id="a9dbc-158">**LocalMachine** é o padrão ao definir uma política de execução.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-158">**LocalMachine** is the default when setting an execution policy.</span></span>

<span data-ttu-id="a9dbc-159">Os valores de **escopo** são listados em ordem de precedência.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-159">The **Scope** values are listed in precedence order.</span></span> <span data-ttu-id="a9dbc-160">A política que tem precedência é eficaz na sessão atual, mesmo que uma política mais restritiva tenha sido definida em um nível mais baixo de precedência.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-160">The policy that takes precedence is effective in the current session, even if a more restrictive policy was set at a lower level of precedence.</span></span>

<span data-ttu-id="a9dbc-161">Para obter mais informações, consulte [Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy).</span><span class="sxs-lookup"><span data-stu-id="a9dbc-161">For more information, see [Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy).</span></span>

### <a name="machinepolicy"></a><span data-ttu-id="a9dbc-162">MachinePolicy</span><span class="sxs-lookup"><span data-stu-id="a9dbc-162">MachinePolicy</span></span>

<span data-ttu-id="a9dbc-163">Definido por um Política de Grupo para todos os usuários do computador.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-163">Set by a Group Policy for all users of the computer.</span></span>

### <a name="userpolicy"></a><span data-ttu-id="a9dbc-164">UserPolicy</span><span class="sxs-lookup"><span data-stu-id="a9dbc-164">UserPolicy</span></span>

<span data-ttu-id="a9dbc-165">Definido por um Política de Grupo para o usuário atual do computador.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-165">Set by a Group Policy for the current user of the computer.</span></span>

### <a name="process"></a><span data-ttu-id="a9dbc-166">Processar</span><span class="sxs-lookup"><span data-stu-id="a9dbc-166">Process</span></span>

<span data-ttu-id="a9dbc-167">O escopo do **processo** afeta apenas a sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-167">The **Process** scope only affects the current PowerShell session.</span></span> <span data-ttu-id="a9dbc-168">A política de execução é salva na variável de ambiente `$env:PSExecutionPolicyPreference` , em vez de no registro.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-168">The execution policy is saved in the environment variable `$env:PSExecutionPolicyPreference`, rather than the registry.</span></span> <span data-ttu-id="a9dbc-169">Quando a sessão do PowerShell é fechada, a variável e o valor são excluídos.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-169">When the PowerShell session is closed, the variable and value are deleted.</span></span>

### <a name="currentuser"></a><span data-ttu-id="a9dbc-170">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="a9dbc-170">CurrentUser</span></span>

<span data-ttu-id="a9dbc-171">A política de execução afeta apenas o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-171">The execution policy affects only the current user.</span></span> <span data-ttu-id="a9dbc-172">Ele é armazenado na subchave do registro **HKEY_CURRENT_USER** .</span><span class="sxs-lookup"><span data-stu-id="a9dbc-172">It's stored in the **HKEY_CURRENT_USER** registry subkey.</span></span>

### <a name="localmachine"></a><span data-ttu-id="a9dbc-173">LocalMachine</span><span class="sxs-lookup"><span data-stu-id="a9dbc-173">LocalMachine</span></span>

<span data-ttu-id="a9dbc-174">A política de execução afeta todos os usuários no computador atual.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-174">The execution policy affects all users on the current computer.</span></span> <span data-ttu-id="a9dbc-175">Ele é armazenado na subchave do registro **HKEY_LOCAL_MACHINE** .</span><span class="sxs-lookup"><span data-stu-id="a9dbc-175">It's stored in the **HKEY_LOCAL_MACHINE** registry subkey.</span></span>

## <a name="managing-the-execution-policy-with-powershell"></a><span data-ttu-id="a9dbc-176">Gerenciando a política de execução com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="a9dbc-176">Managing the execution policy with PowerShell</span></span>

<span data-ttu-id="a9dbc-177">Para obter a política de execução efetiva para a sessão atual do PowerShell, use o `Get-ExecutionPolicy` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-177">To get the effective execution policy for the current PowerShell session, use the `Get-ExecutionPolicy` cmdlet.</span></span>

<span data-ttu-id="a9dbc-178">O comando a seguir obtém a política de execução efetiva:</span><span class="sxs-lookup"><span data-stu-id="a9dbc-178">The following command gets the effective execution policy:</span></span>

```powershell
Get-ExecutionPolicy
```

<span data-ttu-id="a9dbc-179">Para obter todas as políticas de execução que afetam a sessão atual e exibi-las em ordem de precedência:</span><span class="sxs-lookup"><span data-stu-id="a9dbc-179">To get all of the execution policies that affect the current session and display them in precedence order:</span></span>

```powershell
Get-ExecutionPolicy -List
```

<span data-ttu-id="a9dbc-180">O resultado é semelhante ao seguinte exemplo de saída:</span><span class="sxs-lookup"><span data-stu-id="a9dbc-180">The result looks similar to the following sample output:</span></span>

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser    RemoteSigned
 LocalMachine       AllSigned
```

<span data-ttu-id="a9dbc-181">Nesse caso, a política de execução efetiva é **RemoteSigned** porque a política de execução para o usuário atual tem precedência sobre a política de execução definida para o computador local.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-181">In this case, the effective execution policy is **RemoteSigned** because the execution policy for the current user takes precedence over the execution policy set for the local computer.</span></span>

<span data-ttu-id="a9dbc-182">Para obter a política de execução definida para um escopo específico, use o parâmetro **Scope** de `Get-ExecutionPolicy` .</span><span class="sxs-lookup"><span data-stu-id="a9dbc-182">To get the execution policy set for a particular scope, use the **Scope** parameter of `Get-ExecutionPolicy`.</span></span>

<span data-ttu-id="a9dbc-183">Por exemplo, o comando a seguir obtém a política de execução para o escopo **CurrentUser** :</span><span class="sxs-lookup"><span data-stu-id="a9dbc-183">For example, the following command gets the execution policy for the **CurrentUser** scope:</span></span>

```powershell
Get-ExecutionPolicy -Scope CurrentUser
```

### <a name="change-the-execution-policy"></a><span data-ttu-id="a9dbc-184">Alterar a política de execução</span><span class="sxs-lookup"><span data-stu-id="a9dbc-184">Change the execution policy</span></span>

<span data-ttu-id="a9dbc-185">Para alterar a política de execução do PowerShell no computador com Windows, use o `Set-ExecutionPolicy` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-185">To change the PowerShell execution policy on your Windows computer, use the `Set-ExecutionPolicy` cmdlet.</span></span> <span data-ttu-id="a9dbc-186">A alteração entra em vigor imediatamente.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-186">The change is effective immediately.</span></span> <span data-ttu-id="a9dbc-187">Você não precisa reiniciar o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-187">You don't need to restart PowerShell.</span></span>

<span data-ttu-id="a9dbc-188">Se você definir a política de execução para os escopos **LocalMachine** ou **CurrentUser**, a alteração será salva no registro e permanecerá em vigor até que você o altere novamente.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-188">If you set the execution policy for the scopes **LocalMachine** or the **CurrentUser**, the change is saved in the registry and remains effective until you change it again.</span></span>

<span data-ttu-id="a9dbc-189">Se você definir a política de execução para o escopo do **processo** , ela não será salva no registro.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-189">If you set the execution policy for the **Process** scope, it's not saved in the registry.</span></span> <span data-ttu-id="a9dbc-190">A política de execução é mantida até que o processo atual e todos os processos filho sejam fechados.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-190">The execution policy is retained until the current process and any child processes are closed.</span></span>

> [!NOTE]
> <span data-ttu-id="a9dbc-191">No Windows Vista e versões posteriores do Windows, para executar comandos que alteram a política de execução para o computador local, escopo de **LocalMachine** , inicie o PowerShell com a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="a9dbc-191">In Windows Vista and later versions of Windows, to run commands that change the execution policy for the local computer, **LocalMachine** scope, start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="a9dbc-192">Para alterar sua política de execução:</span><span class="sxs-lookup"><span data-stu-id="a9dbc-192">To change your execution policy:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy <PolicyName>
```

<span data-ttu-id="a9dbc-193">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a9dbc-193">For example:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned
```

<span data-ttu-id="a9dbc-194">Para definir a política de execução em um escopo específico:</span><span class="sxs-lookup"><span data-stu-id="a9dbc-194">To set the execution policy in a particular scope:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy <PolicyName> -Scope <scope>
```

<span data-ttu-id="a9dbc-195">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a9dbc-195">For example:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

<span data-ttu-id="a9dbc-196">Um comando para alterar uma política de execução pode ter sucesso, mas ainda não alterar a política de execução efetiva.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-196">A command to change an execution policy can succeed but still not change the effective execution policy.</span></span>

<span data-ttu-id="a9dbc-197">Por exemplo, um comando que define a política de execução para o computador local pode ter sucesso, mas ser substituído pela política de execução para o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-197">For example, a command that sets the execution policy for the local computer can succeed but be overridden by the execution policy for the current user.</span></span>

### <a name="remove-the-execution-policy"></a><span data-ttu-id="a9dbc-198">Remover a política de execução</span><span class="sxs-lookup"><span data-stu-id="a9dbc-198">Remove the execution policy</span></span>

<span data-ttu-id="a9dbc-199">Para remover a política de execução para um escopo específico, defina a política de execução como **indefinido**.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-199">To remove the execution policy for a particular scope, set the execution policy to **Undefined**.</span></span>

<span data-ttu-id="a9dbc-200">Por exemplo, para remover a política de execução para todos os usuários do computador local:</span><span class="sxs-lookup"><span data-stu-id="a9dbc-200">For example, to remove the execution policy for all the users of the local computer:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy Undefined -Scope LocalMachine
```

<span data-ttu-id="a9dbc-201">Para remover a política de execução para um **escopo**:</span><span class="sxs-lookup"><span data-stu-id="a9dbc-201">To remove the execution policy for a **Scope**:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy Undefined -Scope CurrentUser
```

<span data-ttu-id="a9dbc-202">Se nenhuma política de execução for definida em nenhum escopo, a política de execução efetiva será **restrita**, que é o padrão para clientes Windows.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-202">If no execution policy is set in any scope, the effective execution policy is **Restricted**, which is the default for Windows clients.</span></span>

### <a name="set-a-different-policy-for-one-session"></a><span data-ttu-id="a9dbc-203">Definir uma política diferente para uma sessão</span><span class="sxs-lookup"><span data-stu-id="a9dbc-203">Set a different policy for one session</span></span>

<span data-ttu-id="a9dbc-204">Você pode usar o parâmetro **ExecutionPolicy** de **pwsh.exe** para definir uma política de execução para uma nova sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-204">You can use the **ExecutionPolicy** parameter of **pwsh.exe** to set an execution policy for a new PowerShell session.</span></span> <span data-ttu-id="a9dbc-205">A política afeta apenas a sessão atual e as sessões filho.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-205">The policy affects only the current session and child sessions.</span></span>

<span data-ttu-id="a9dbc-206">Para definir a política de execução para uma nova sessão, inicie o PowerShell na linha de comando, como **cmd.exe** ou do PowerShell e, em seguida, use o parâmetro **ExecutionPolicy** de **pwsh.exe** para definir a política de execução.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-206">To set the execution policy for a new session, start PowerShell at the command line, such as **cmd.exe** or from PowerShell, and then use the **ExecutionPolicy** parameter of **pwsh.exe** to set the execution policy.</span></span>

<span data-ttu-id="a9dbc-207">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a9dbc-207">For example:</span></span>

```powershell
pwsh.exe -ExecutionPolicy AllSigned
```

<span data-ttu-id="a9dbc-208">A política de execução definida não é armazenada no registro.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-208">The execution policy that you set isn't stored in the registry.</span></span> <span data-ttu-id="a9dbc-209">Em vez disso, ele é armazenado na `$env:PSExecutionPolicyPreference` variável de ambiente.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-209">Instead, it's stored in the `$env:PSExecutionPolicyPreference` environment variable.</span></span> <span data-ttu-id="a9dbc-210">A variável é excluída quando você fecha a sessão na qual a política está definida.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-210">The variable is deleted when you close the session in which the policy is set.</span></span> <span data-ttu-id="a9dbc-211">Você não pode alterar a política editando o valor da variável.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-211">You cannot change the policy by editing the variable value.</span></span>

<span data-ttu-id="a9dbc-212">Durante a sessão, a política de execução definida para a sessão tem precedência sobre uma política de execução definida no registro para o computador local ou o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-212">During the session, the execution policy that is set for the session takes precedence over an execution policy that is set in the registry for the local computer or current user.</span></span> <span data-ttu-id="a9dbc-213">No entanto, ele não tem precedência sobre a política de execução definida usando um Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-213">However, it doesn't take precedence over the execution policy set by using a Group Policy.</span></span>

## <a name="use-group-policy-to-manage-execution-policy"></a><span data-ttu-id="a9dbc-214">Usar Política de Grupo para gerenciar a política de execução</span><span class="sxs-lookup"><span data-stu-id="a9dbc-214">Use Group Policy to Manage Execution Policy</span></span>

<span data-ttu-id="a9dbc-215">Você pode usar a configuração **ativar a execução de Script** política de grupo para gerenciar a política de execução de computadores em sua empresa.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-215">You can use the **Turn on Script Execution** Group Policy setting to manage the execution policy of computers in your enterprise.</span></span> <span data-ttu-id="a9dbc-216">A configuração de Política de Grupo substitui as políticas de execução definidas no PowerShell em todos os escopos.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-216">The Group Policy setting overrides the execution policies set in PowerShell in all scopes.</span></span>

<span data-ttu-id="a9dbc-217">As configurações ativar política de **execução de script** são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="a9dbc-217">The **Turn on Script Execution** policy settings are as follows:</span></span>

- <span data-ttu-id="a9dbc-218">Se você desabilitar **ativar a execução de script**, os scripts não são executados.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-218">If you disable **Turn on Script Execution**, scripts do not run.</span></span> <span data-ttu-id="a9dbc-219">Isso é equivalente à política de execução **restrita** .</span><span class="sxs-lookup"><span data-stu-id="a9dbc-219">This is equivalent to the **Restricted** execution policy.</span></span>
- <span data-ttu-id="a9dbc-220">Se habilitar **ativar a execução do script**, você poderá selecionar uma política de execução.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-220">If you enable **Turn on Script Execution**, you can select an execution policy.</span></span> <span data-ttu-id="a9dbc-221">As configurações de Política de Grupo são equivalentes às seguintes configurações de política de execução:</span><span class="sxs-lookup"><span data-stu-id="a9dbc-221">The Group Policy settings are equivalent to the following execution policy settings:</span></span>

  | <span data-ttu-id="a9dbc-222">Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="a9dbc-222">Group Policy</span></span>                                  | <span data-ttu-id="a9dbc-223">Política de execução</span><span class="sxs-lookup"><span data-stu-id="a9dbc-223">Execution Policy</span></span> |
  | --------------------------------------------- | ---------------- |
  | <span data-ttu-id="a9dbc-224">Permitir todos os scripts</span><span class="sxs-lookup"><span data-stu-id="a9dbc-224">Allow all scripts</span></span>                             | <span data-ttu-id="a9dbc-225">Irrestrito</span><span class="sxs-lookup"><span data-stu-id="a9dbc-225">Unrestricted</span></span>     |
  | <span data-ttu-id="a9dbc-226">Permitir scripts locais e scripts remotos assinados</span><span class="sxs-lookup"><span data-stu-id="a9dbc-226">Allow local scripts and remote signed scripts</span></span> | <span data-ttu-id="a9dbc-227">RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="a9dbc-227">RemoteSigned</span></span>     |
  | <span data-ttu-id="a9dbc-228">Permitir somente scripts assinados</span><span class="sxs-lookup"><span data-stu-id="a9dbc-228">Allow only signed scripts</span></span>                     | <span data-ttu-id="a9dbc-229">AllSigned</span><span class="sxs-lookup"><span data-stu-id="a9dbc-229">AllSigned</span></span>        |

- <span data-ttu-id="a9dbc-230">Se **ativar a execução do script** não estiver configurado, ele não terá nenhum efeito.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-230">If **Turn on Script Execution** is not configured, it has no effect.</span></span> <span data-ttu-id="a9dbc-231">A política de execução definida no PowerShell é eficaz.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-231">The execution policy set in PowerShell is effective.</span></span>

<span data-ttu-id="a9dbc-232">Os arquivos PowerShellExecutionPolicy. adm e PowerShellExecutionPolicy. admx adicionam a política de **execução ativar script** aos nós configuração do computador e configuração do usuário no Editor de política de grupo nos caminhos a seguir.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-232">The PowerShellExecutionPolicy.adm and PowerShellExecutionPolicy.admx files add the **Turn on Script Execution** policy to the Computer Configuration and User Configuration nodes in Group Policy Editor in the following paths.</span></span>

<span data-ttu-id="a9dbc-233">Para o Windows XP e o Windows Server 2003:</span><span class="sxs-lookup"><span data-stu-id="a9dbc-233">For Windows XP and Windows Server 2003:</span></span>

<span data-ttu-id="a9dbc-234">Modelos administrativos do Windows\windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a9dbc-234">Administrative Templates\Windows Components\Windows PowerShell</span></span>

<span data-ttu-id="a9dbc-235">Para o Windows Vista e versões posteriores do Windows:</span><span class="sxs-lookup"><span data-stu-id="a9dbc-235">For Windows Vista and later versions of Windows:</span></span>

<span data-ttu-id="a9dbc-236">Templates\Classic administrativo Modelos Administrativos </span><span class="sxs-lookup"><span data-stu-id="a9dbc-236">Administrative Templates\Classic Administrative Templates</span></span>\
<span data-ttu-id="a9dbc-237">Windows Windows\windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a9dbc-237">Windows Components\Windows PowerShell</span></span>

<span data-ttu-id="a9dbc-238">As políticas definidas no nó Configuração do computador têm precedência sobre as políticas definidas no nó Configuração do usuário.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-238">Policies set in the Computer Configuration node take precedence over policies set in the User Configuration node.</span></span>

<span data-ttu-id="a9dbc-239">Confira mais informações em [about_Group_Policy_Settings](about_Group_Policy_Settings.md).</span><span class="sxs-lookup"><span data-stu-id="a9dbc-239">For more information, see [about_Group_Policy_Settings](about_Group_Policy_Settings.md).</span></span>

### <a name="execution-policy-precedence"></a><span data-ttu-id="a9dbc-240">Precedência de política de execução</span><span class="sxs-lookup"><span data-stu-id="a9dbc-240">Execution policy precedence</span></span>

<span data-ttu-id="a9dbc-241">Ao determinar a política de execução efetiva para uma sessão, o PowerShell avalia as políticas de execução na seguinte ordem de precedência:</span><span class="sxs-lookup"><span data-stu-id="a9dbc-241">When determining the effective execution policy for a session, PowerShell evaluates the execution policies in the following precedence order:</span></span>

- <span data-ttu-id="a9dbc-242">Política de Grupo: MachinePolicy</span><span class="sxs-lookup"><span data-stu-id="a9dbc-242">Group Policy: MachinePolicy</span></span>
- <span data-ttu-id="a9dbc-243">Política de Grupo: UserPolicy</span><span class="sxs-lookup"><span data-stu-id="a9dbc-243">Group Policy: UserPolicy</span></span>
- <span data-ttu-id="a9dbc-244">Política de execução: processo (ou `pwsh.exe -ExecutionPolicy` )</span><span class="sxs-lookup"><span data-stu-id="a9dbc-244">Execution Policy: Process (or `pwsh.exe -ExecutionPolicy`)</span></span>
- <span data-ttu-id="a9dbc-245">Política de execução: CurrentUser</span><span class="sxs-lookup"><span data-stu-id="a9dbc-245">Execution Policy: CurrentUser</span></span>
- <span data-ttu-id="a9dbc-246">Política de execução: LocalMachine</span><span class="sxs-lookup"><span data-stu-id="a9dbc-246">Execution Policy: LocalMachine</span></span>

## <a name="manage-signed-and-unsigned-scripts"></a><span data-ttu-id="a9dbc-247">Gerenciar scripts assinados e não assinados</span><span class="sxs-lookup"><span data-stu-id="a9dbc-247">Manage signed and unsigned scripts</span></span>

<span data-ttu-id="a9dbc-248">No Windows, programas como o Internet Explorer e o Microsoft Edge adicionam um fluxo de dados alternativo a arquivos que são baixados.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-248">In Windows, programs like Internet Explorer and Microsoft Edge add an alternate data stream to files that are downloaded.</span></span> <span data-ttu-id="a9dbc-249">Isso marca o arquivo como "proveniente da Internet".</span><span class="sxs-lookup"><span data-stu-id="a9dbc-249">This marks the file as "coming from the Internet".</span></span> <span data-ttu-id="a9dbc-250">Se a política de execução do PowerShell for **RemoteSigned**, o PowerShell não executará scripts não assinados que são baixados da Internet que inclui programas de email e mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-250">If your PowerShell execution policy is **RemoteSigned**, PowerShell won't run unsigned scripts that are downloaded from the internet which includes email and instant messaging programs.</span></span>

<span data-ttu-id="a9dbc-251">Você pode assinar o script ou optar por executar um script não assinado sem alterar a política de execução.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-251">You can sign the script or elect to run an unsigned script without changing the execution policy.</span></span>

<span data-ttu-id="a9dbc-252">A partir do PowerShell 3,0, você pode usar o parâmetro **Stream** do `Get-Item` cmdlet para detectar arquivos bloqueados porque eles foram baixados da Internet.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-252">Beginning in PowerShell 3.0, you can use the **Stream** parameter of the `Get-Item` cmdlet to detect files that are blocked because they were downloaded from the internet.</span></span> <span data-ttu-id="a9dbc-253">Use o `Unblock-File` cmdlet para desbloquear os scripts para que você possa executá-los no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-253">Use the `Unblock-File` cmdlet to unblock the scripts so that you can run them in PowerShell.</span></span>

<span data-ttu-id="a9dbc-254">Para obter mais informações, consulte [about_Signing](about_Signing.md), [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)e [desbloquear-File](xref:Microsoft.PowerShell.Utility.Unblock-File).</span><span class="sxs-lookup"><span data-stu-id="a9dbc-254">For more information, see [about_Signing](about_Signing.md), [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item), and [Unblock-File](xref:Microsoft.PowerShell.Utility.Unblock-File).</span></span>

> [!NOTE]
> <span data-ttu-id="a9dbc-255">Outros métodos de download de arquivos podem não marcar os arquivos como provenientes da zona da Internet.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-255">Other methods of downloading files may not mark the files as coming from the Internet Zone.</span></span> <span data-ttu-id="a9dbc-256">Alguns exemplos incluem:</span><span class="sxs-lookup"><span data-stu-id="a9dbc-256">Some examples include:</span></span>
>
> - `curl.exe`
> - `Invoke-RestMethod`
> - `Invoke-WebRequest`

## <a name="execution-policy-on-windows-server-core-and-window-nano-server"></a><span data-ttu-id="a9dbc-257">Política de execução no Windows Server Core e no Window nano Server</span><span class="sxs-lookup"><span data-stu-id="a9dbc-257">Execution policy on Windows Server Core and Window Nano Server</span></span>

<span data-ttu-id="a9dbc-258">Quando o PowerShell 6 é executado no Windows Server Core ou no Windows nano Server em determinadas condições, as políticas de execução podem falhar com o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="a9dbc-258">When PowerShell 6 is run on Windows Server Core or Windows Nano Server under certain conditions, execution policies can fail with the following error:</span></span>

```Output
AuthorizationManager check failed.
At line:1 char:1
+ C:\scriptpath\scriptname.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess
```

<span data-ttu-id="a9dbc-259">O PowerShell usa APIs no Shell da área de trabalho do Windows ( `explorer.exe` ) para validar a zona de um arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-259">PowerShell uses APIs in the Windows Desktop Shell (`explorer.exe`) to validate the Zone of a script file.</span></span> <span data-ttu-id="a9dbc-260">O Shell do Windows não está disponível no Windows Server Core e no Windows nano Server.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-260">The Windows Shell is not available on Windows Server Core and Windows Nano Server.</span></span>

<span data-ttu-id="a9dbc-261">Você também poderá obter esse erro em qualquer sistema Windows se o Shell da área de trabalho do Windows estiver indisponível ou sem resposta.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-261">You could also get this error on any Windows system if the Windows Desktop Shell is unavailable or unresponsive.</span></span> <span data-ttu-id="a9dbc-262">Por exemplo, durante o logon, um script de logon do PowerShell pode iniciar a execução antes que a área de trabalho do Windows esteja pronta, resultando em falha.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-262">For example, during sign on, a PowerShell logon script could start execution before the Windows Desktop is ready, resulting in failure.</span></span>

<span data-ttu-id="a9dbc-263">Usar uma política de execução de **bypass** ou **AllSigned** não requer uma verificação de zona, o que evita o problema.</span><span class="sxs-lookup"><span data-stu-id="a9dbc-263">Using an execution policy of **ByPass** or **AllSigned** does not require a Zone check which avoids the problem.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9dbc-264">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a9dbc-264">See Also</span></span>

[<span data-ttu-id="a9dbc-265">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="a9dbc-265">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="a9dbc-266">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="a9dbc-266">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="a9dbc-267">about_Signing</span><span class="sxs-lookup"><span data-stu-id="a9dbc-267">about_Signing</span></span>](about_Signing.md)

[<span data-ttu-id="a9dbc-268">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="a9dbc-268">Get-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Get-ExecutionPolicy)

[<span data-ttu-id="a9dbc-269">Get-Item</span><span class="sxs-lookup"><span data-stu-id="a9dbc-269">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)

[<span data-ttu-id="a9dbc-270">Ajuda do console do Pwsh</span><span class="sxs-lookup"><span data-stu-id="a9dbc-270">Pwsh Console Help</span></span>](about_pwsh.md)

[<span data-ttu-id="a9dbc-271">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="a9dbc-271">Set-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)

[<span data-ttu-id="a9dbc-272">Unblock-File</span><span class="sxs-lookup"><span data-stu-id="a9dbc-272">Unblock-File</span></span>](xref:Microsoft.PowerShell.Utility.Unblock-File)

