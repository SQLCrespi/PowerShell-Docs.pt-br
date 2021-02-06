---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 03/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-executionpolicy?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ExecutionPolicy
ms.openlocfilehash: d6555f1abc824add4613654461106af34045e1a3
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603331"
---
# <span data-ttu-id="6e55d-102">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="6e55d-102">Get-ExecutionPolicy</span></span>

## <span data-ttu-id="6e55d-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="6e55d-103">SYNOPSIS</span></span>
<span data-ttu-id="6e55d-104">Obtém as políticas de execução da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="6e55d-104">Gets the execution policies for the current session.</span></span>

## <span data-ttu-id="6e55d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6e55d-105">SYNTAX</span></span>

### <span data-ttu-id="6e55d-106">Tudo</span><span class="sxs-lookup"><span data-stu-id="6e55d-106">All</span></span>

```
Get-ExecutionPolicy [[-Scope] <ExecutionPolicyScope>] [-List] [<CommonParameters>]
```

## <span data-ttu-id="6e55d-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6e55d-107">DESCRIPTION</span></span>

<span data-ttu-id="6e55d-108">Para exibir as políticas de execução para cada escopo na ordem de precedência, use `Get-ExecutionPolicy -List` .</span><span class="sxs-lookup"><span data-stu-id="6e55d-108">To display the execution policies for each scope in the order of precedence, use `Get-ExecutionPolicy -List`.</span></span> <span data-ttu-id="6e55d-109">Para ver a política de execução efetiva para sua sessão do PowerShell, use `Get-ExecutionPolicy` sem parâmetros.</span><span class="sxs-lookup"><span data-stu-id="6e55d-109">To see the effective execution policy for your PowerShell session use `Get-ExecutionPolicy` with no parameters.</span></span>

<span data-ttu-id="6e55d-110">A política de execução efetiva é determinada pelas políticas de execução definidas pelo `Set-ExecutionPolicy` e política de grupo configurações.</span><span class="sxs-lookup"><span data-stu-id="6e55d-110">The effective execution policy is determined by execution policies that are set by `Set-ExecutionPolicy` and Group Policy settings.</span></span>

<span data-ttu-id="6e55d-111">Para obter mais informações, consulte [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="6e55d-111">For more information, see [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span></span>

## <span data-ttu-id="6e55d-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="6e55d-112">EXAMPLES</span></span>

### <span data-ttu-id="6e55d-113">Exemplo 1: obter todas as políticas de execução</span><span class="sxs-lookup"><span data-stu-id="6e55d-113">Example 1: Get all execution policies</span></span>

<span data-ttu-id="6e55d-114">Esse comando exibe as políticas de execução para cada escopo na ordem de precedência.</span><span class="sxs-lookup"><span data-stu-id="6e55d-114">This command displays the execution policies for each scope in the order of precedence.</span></span>

```powershell
Get-ExecutionPolicy -List
```

```Output
Scope          ExecutionPolicy
-----          ---------------
MachinePolicy  Undefined
UserPolicy     Undefined
Process        Undefined
CurrentUser    AllSigned
LocalMachine   Undefined
```

<span data-ttu-id="6e55d-115">O `Get-ExecutionPolicy` cmdlet usa o parâmetro **list** para exibir a política de execução de cada escopo.</span><span class="sxs-lookup"><span data-stu-id="6e55d-115">The `Get-ExecutionPolicy` cmdlet uses the **List** parameter to display each scope's execution policy.</span></span>

### <span data-ttu-id="6e55d-116">Exemplo 2: definir uma política de execução</span><span class="sxs-lookup"><span data-stu-id="6e55d-116">Example 2: Set an execution policy</span></span>

<span data-ttu-id="6e55d-117">Este exemplo mostra como definir uma política de execução para o computador local.</span><span class="sxs-lookup"><span data-stu-id="6e55d-117">This example shows how to set an execution policy for the local computer.</span></span>

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
  CurrentUser       AllSigned
 LocalMachine    RemoteSigned
```

<span data-ttu-id="6e55d-118">O `Set-ExecutionPolicy` cmdlet usa o parâmetro **ExecutionPolicy** para especificar a política **RemoteSigned** .</span><span class="sxs-lookup"><span data-stu-id="6e55d-118">The `Set-ExecutionPolicy` cmdlet uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="6e55d-119">O parâmetro **Scope** especifica o valor de escopo padrão, **LocalMachine**.</span><span class="sxs-lookup"><span data-stu-id="6e55d-119">The **Scope** parameter specifies the default scope value, **LocalMachine**.</span></span> <span data-ttu-id="6e55d-120">Para exibir as configurações de política de execução, use o `Get-ExecutionPolicy` cmdlet com o parâmetro **list** .</span><span class="sxs-lookup"><span data-stu-id="6e55d-120">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="6e55d-121">Exemplo 3: obter a política de execução efetiva</span><span class="sxs-lookup"><span data-stu-id="6e55d-121">Example 3: Get the effective execution policy</span></span>

<span data-ttu-id="6e55d-122">Este exemplo mostra como exibir a política de execução efetiva para uma sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e55d-122">This example shows how to display the effective execution policy for a PowerShell session.</span></span>

```
PS> Get-ExecutionPolicy -List

        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser       AllSigned
 LocalMachine    RemoteSigned

PS> Get-ExecutionPolicy

AllSigned
```

<span data-ttu-id="6e55d-123">O `Get-ExecutionPolicy` cmdlet usa o parâmetro **list** para exibir a política de execução de cada escopo.</span><span class="sxs-lookup"><span data-stu-id="6e55d-123">The `Get-ExecutionPolicy` cmdlet uses the **List** parameter to display each scope's execution policy.</span></span> <span data-ttu-id="6e55d-124">O `Get-ExecutionPolicy` cmdlet é executado sem um parâmetro para exibir a política de execução efetiva, **AllSigned**.</span><span class="sxs-lookup"><span data-stu-id="6e55d-124">The `Get-ExecutionPolicy` cmdlet is run without a parameter to display the effective execution policy, **AllSigned**.</span></span>

### <span data-ttu-id="6e55d-125">Exemplo 4: desbloquear um script para executá-lo sem alterar a política de execução</span><span class="sxs-lookup"><span data-stu-id="6e55d-125">Example 4: Unblock a script to run it without changing the execution policy</span></span>

<span data-ttu-id="6e55d-126">Este exemplo mostra como a política de execução **RemoteSigned** impede que você execute scripts não assinados.</span><span class="sxs-lookup"><span data-stu-id="6e55d-126">This example shows how the **RemoteSigned** execution policy prevents you from running unsigned scripts.</span></span>

<span data-ttu-id="6e55d-127">Uma prática recomendada é ler o código do script e verificar se ele é seguro **antes** de usar o `Unblock-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6e55d-127">A best practice is to read the script's code and verify it's safe **before** using the `Unblock-File` cmdlet.</span></span> <span data-ttu-id="6e55d-128">O `Unblock-File` cmdlet desbloqueia scripts para que eles possam ser executados, mas não altera a política de execução.</span><span class="sxs-lookup"><span data-stu-id="6e55d-128">The `Unblock-File` cmdlet unblocks scripts so they can run, but doesn't change the execution policy.</span></span>

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

<span data-ttu-id="6e55d-129">O `Set-ExecutionPolicy` usa o parâmetro **ExecutionPolicy** para especificar a política de **RemoteSigned** .</span><span class="sxs-lookup"><span data-stu-id="6e55d-129">The `Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="6e55d-130">A política é definida para o escopo padrão, **LocalMachine**.</span><span class="sxs-lookup"><span data-stu-id="6e55d-130">The policy is set for the default scope, **LocalMachine**.</span></span>

<span data-ttu-id="6e55d-131">O `Get-ExecutionPolicy` cmdlet mostra que **RemoteSigned** é a política de execução efetiva para a sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e55d-131">The `Get-ExecutionPolicy` cmdlet shows that **RemoteSigned** is the effective execution policy for the current PowerShell session.</span></span>

<span data-ttu-id="6e55d-132">O script de **Start-ActivityTracker.ps1** é executado a partir do diretório atual.</span><span class="sxs-lookup"><span data-stu-id="6e55d-132">The **Start-ActivityTracker.ps1** script is executed from the current directory.</span></span> <span data-ttu-id="6e55d-133">O script é bloqueado por **RemoteSigned** porque o script não está assinado digitalmente.</span><span class="sxs-lookup"><span data-stu-id="6e55d-133">The script is blocked by **RemoteSigned** because the script isn't digitally signed.</span></span>

<span data-ttu-id="6e55d-134">Neste exemplo, o código do script foi revisado e verificado como seguro para ser executado.</span><span class="sxs-lookup"><span data-stu-id="6e55d-134">For this example, the script's code was reviewed and verified as safe to run.</span></span> <span data-ttu-id="6e55d-135">O `Unblock-File` cmdlet usa o parâmetro **Path** para desbloquear o script.</span><span class="sxs-lookup"><span data-stu-id="6e55d-135">The `Unblock-File` cmdlet uses the **Path** parameter to unblock the script.</span></span>

<span data-ttu-id="6e55d-136">Para verificar se `Unblock-File` a política de execução não foi alterada, `Get-ExecutionPolicy` exibe a política de execução efetiva, **RemoteSigned**.</span><span class="sxs-lookup"><span data-stu-id="6e55d-136">To verify that `Unblock-File` didn't change the execution policy, `Get-ExecutionPolicy` displays the effective execution policy, **RemoteSigned**.</span></span>

<span data-ttu-id="6e55d-137">O script, **Start-ActivityTracker.ps1** é executado a partir do diretório atual.</span><span class="sxs-lookup"><span data-stu-id="6e55d-137">The script, **Start-ActivityTracker.ps1** is executed from the current directory.</span></span> <span data-ttu-id="6e55d-138">O script começa a ser executado porque foi desbloqueado pelo `Unblock-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6e55d-138">The script begins to run because it was unblocked by the `Unblock-File` cmdlet.</span></span>

## <span data-ttu-id="6e55d-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6e55d-139">PARAMETERS</span></span>

### <span data-ttu-id="6e55d-140">-Lista</span><span class="sxs-lookup"><span data-stu-id="6e55d-140">-List</span></span>

<span data-ttu-id="6e55d-141">Obtém todos os valores da política de execução para a sessão listada em ordem de precedência.</span><span class="sxs-lookup"><span data-stu-id="6e55d-141">Gets all execution policy values for the session listed in precedence order.</span></span> <span data-ttu-id="6e55d-142">Por padrão, `Get-ExecutionPolicy` obtém apenas a política de execução efetiva.</span><span class="sxs-lookup"><span data-stu-id="6e55d-142">By default, `Get-ExecutionPolicy` gets only the effective execution policy.</span></span>

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

### <span data-ttu-id="6e55d-143">-Escopo</span><span class="sxs-lookup"><span data-stu-id="6e55d-143">-Scope</span></span>

<span data-ttu-id="6e55d-144">Especifica o escopo que é afetado por uma política de execução.</span><span class="sxs-lookup"><span data-stu-id="6e55d-144">Specifies the scope that is affected by an execution policy.</span></span>

<span data-ttu-id="6e55d-145">A política de execução efetiva é determinada pela ordem de precedência da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="6e55d-145">The effective execution policy is determined by the order of precedence as follows:</span></span>

- <span data-ttu-id="6e55d-146">**MachinePolicy**.</span><span class="sxs-lookup"><span data-stu-id="6e55d-146">**MachinePolicy**.</span></span> <span data-ttu-id="6e55d-147">Definido por um Política de Grupo para todos os usuários do computador.</span><span class="sxs-lookup"><span data-stu-id="6e55d-147">Set by a Group Policy for all users of the computer.</span></span>
- <span data-ttu-id="6e55d-148">**UserPolicy**.</span><span class="sxs-lookup"><span data-stu-id="6e55d-148">**UserPolicy**.</span></span> <span data-ttu-id="6e55d-149">Definido por um Política de Grupo para o usuário atual do computador.</span><span class="sxs-lookup"><span data-stu-id="6e55d-149">Set by a Group Policy for the current user of the computer.</span></span>
- <span data-ttu-id="6e55d-150">**Processar**.</span><span class="sxs-lookup"><span data-stu-id="6e55d-150">**Process**.</span></span> <span data-ttu-id="6e55d-151">Afeta apenas a sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e55d-151">Affects only the current PowerShell session.</span></span>
- <span data-ttu-id="6e55d-152">**CurrentUser**.</span><span class="sxs-lookup"><span data-stu-id="6e55d-152">**CurrentUser**.</span></span> <span data-ttu-id="6e55d-153">Afeta somente o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="6e55d-153">Affects only the current user.</span></span>
- <span data-ttu-id="6e55d-154">**LocalMachine**.</span><span class="sxs-lookup"><span data-stu-id="6e55d-154">**LocalMachine**.</span></span> <span data-ttu-id="6e55d-155">Escopo padrão que afeta todos os usuários do computador.</span><span class="sxs-lookup"><span data-stu-id="6e55d-155">Default scope that affects all users of the computer.</span></span>

```yaml
Type: Microsoft.PowerShell.ExecutionPolicyScope
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, LocalMachine, MachinePolicy, Process, UserPolicy

Required: False
Position: 0
Default value: Effective execution policy
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6e55d-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6e55d-156">CommonParameters</span></span>

<span data-ttu-id="6e55d-157">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6e55d-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6e55d-158">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6e55d-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6e55d-159">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="6e55d-159">INPUTS</span></span>

### <span data-ttu-id="6e55d-160">Nenhum</span><span class="sxs-lookup"><span data-stu-id="6e55d-160">None</span></span>

<span data-ttu-id="6e55d-161">`Get-ExecutionPolicy` Não aceita a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="6e55d-161">`Get-ExecutionPolicy` doesn't accept input from the pipeline.</span></span>

## <span data-ttu-id="6e55d-162">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="6e55d-162">OUTPUTS</span></span>

### <span data-ttu-id="6e55d-163">Microsoft.PowerShell.ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="6e55d-163">Microsoft.PowerShell.ExecutionPolicy</span></span>

<span data-ttu-id="6e55d-164">O cmdlet sempre retorna **irrestrito** em plataformas Linux e MacOS.</span><span class="sxs-lookup"><span data-stu-id="6e55d-164">The cmdlet always returns **Unrestricted** on Linux and macOS platforms.</span></span>

## <span data-ttu-id="6e55d-165">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="6e55d-165">NOTES</span></span>

<span data-ttu-id="6e55d-166">Uma política de execução faz parte da estratégia de segurança do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e55d-166">An execution policy is part of the PowerShell security strategy.</span></span> <span data-ttu-id="6e55d-167">As políticas de execução determinam se você pode carregar arquivos de configuração, como seu perfil do PowerShell, ou executar scripts.</span><span class="sxs-lookup"><span data-stu-id="6e55d-167">Execution policies determine whether you can load configuration files, such as your PowerShell profile, or run scripts.</span></span> <span data-ttu-id="6e55d-168">E se os scripts devem ser assinados digitalmente antes de serem executados.</span><span class="sxs-lookup"><span data-stu-id="6e55d-168">And, whether scripts must be digitally signed before they are run.</span></span>

## <span data-ttu-id="6e55d-169">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="6e55d-169">RELATED LINKS</span></span>

[<span data-ttu-id="6e55d-170">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="6e55d-170">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md)

[<span data-ttu-id="6e55d-171">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="6e55d-171">about_Group_Policy_Settings</span></span>](../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md)

[<span data-ttu-id="6e55d-172">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="6e55d-172">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)

[<span data-ttu-id="6e55d-173">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="6e55d-173">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)

[<span data-ttu-id="6e55d-174">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="6e55d-174">Set-ExecutionPolicy</span></span>](Set-ExecutionPolicy.md)
