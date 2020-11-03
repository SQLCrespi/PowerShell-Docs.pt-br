---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 3/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-executionpolicy?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ExecutionPolicy
ms.openlocfilehash: 2bd5854b689fad077f6a3df2e37693cff973a62a
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93193049"
---
# <span data-ttu-id="54352-103">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="54352-103">Get-ExecutionPolicy</span></span>

## <span data-ttu-id="54352-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="54352-104">SYNOPSIS</span></span>
<span data-ttu-id="54352-105">Obtém as políticas de execução da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="54352-105">Gets the execution policies for the current session.</span></span>

## <span data-ttu-id="54352-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="54352-106">SYNTAX</span></span>

### <span data-ttu-id="54352-107">Tudo</span><span class="sxs-lookup"><span data-stu-id="54352-107">All</span></span>

```
Get-ExecutionPolicy [[-Scope] <ExecutionPolicyScope>] [-List] [<CommonParameters>]
```

## <span data-ttu-id="54352-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="54352-108">DESCRIPTION</span></span>

<span data-ttu-id="54352-109">Para exibir as políticas de execução para cada escopo na ordem de precedência, use `Get-ExecutionPolicy -List` .</span><span class="sxs-lookup"><span data-stu-id="54352-109">To display the execution policies for each scope in the order of precedence, use `Get-ExecutionPolicy -List`.</span></span> <span data-ttu-id="54352-110">Para ver a política de execução efetiva para sua sessão do PowerShell, use `Get-ExecutionPolicy` sem parâmetros.</span><span class="sxs-lookup"><span data-stu-id="54352-110">To see the effective execution policy for your PowerShell session use `Get-ExecutionPolicy` with no parameters.</span></span>

<span data-ttu-id="54352-111">A política de execução efetiva é determinada pelas políticas de execução definidas pelo `Set-ExecutionPolicy` e política de grupo configurações.</span><span class="sxs-lookup"><span data-stu-id="54352-111">The effective execution policy is determined by execution policies that are set by `Set-ExecutionPolicy` and Group Policy settings.</span></span>

<span data-ttu-id="54352-112">Para obter mais informações, consulte [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="54352-112">For more information, see [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span></span>

## <span data-ttu-id="54352-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="54352-113">EXAMPLES</span></span>

### <span data-ttu-id="54352-114">Exemplo 1: obter todas as políticas de execução</span><span class="sxs-lookup"><span data-stu-id="54352-114">Example 1: Get all execution policies</span></span>

<span data-ttu-id="54352-115">Esse comando exibe as políticas de execução para cada escopo na ordem de precedência.</span><span class="sxs-lookup"><span data-stu-id="54352-115">This command displays the execution policies for each scope in the order of precedence.</span></span>

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

<span data-ttu-id="54352-116">O `Get-ExecutionPolicy` cmdlet usa o parâmetro **list** para exibir a política de execução de cada escopo.</span><span class="sxs-lookup"><span data-stu-id="54352-116">The `Get-ExecutionPolicy` cmdlet uses the **List** parameter to display each scope's execution policy.</span></span>

### <span data-ttu-id="54352-117">Exemplo 2: definir uma política de execução</span><span class="sxs-lookup"><span data-stu-id="54352-117">Example 2: Set an execution policy</span></span>

<span data-ttu-id="54352-118">Este exemplo mostra como definir uma política de execução para o computador local.</span><span class="sxs-lookup"><span data-stu-id="54352-118">This example shows how to set an execution policy for the local computer.</span></span>

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

<span data-ttu-id="54352-119">O `Set-ExecutionPolicy` cmdlet usa o parâmetro **ExecutionPolicy** para especificar a política **RemoteSigned** .</span><span class="sxs-lookup"><span data-stu-id="54352-119">The `Set-ExecutionPolicy` cmdlet uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="54352-120">O parâmetro **Scope** especifica o valor de escopo padrão, **LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="54352-120">The **Scope** parameter specifies the default scope value, **LocalMachine** .</span></span> <span data-ttu-id="54352-121">Para exibir as configurações de política de execução, use o `Get-ExecutionPolicy` cmdlet com o parâmetro **list** .</span><span class="sxs-lookup"><span data-stu-id="54352-121">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="54352-122">Exemplo 3: obter a política de execução efetiva</span><span class="sxs-lookup"><span data-stu-id="54352-122">Example 3: Get the effective execution policy</span></span>

<span data-ttu-id="54352-123">Este exemplo mostra como exibir a política de execução efetiva para uma sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="54352-123">This example shows how to display the effective execution policy for a PowerShell session.</span></span>

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

<span data-ttu-id="54352-124">O `Get-ExecutionPolicy` cmdlet usa o parâmetro **list** para exibir a política de execução de cada escopo.</span><span class="sxs-lookup"><span data-stu-id="54352-124">The `Get-ExecutionPolicy` cmdlet uses the **List** parameter to display each scope's execution policy.</span></span> <span data-ttu-id="54352-125">O `Get-ExecutionPolicy` cmdlet é executado sem um parâmetro para exibir a política de execução efetiva, **AllSigned** .</span><span class="sxs-lookup"><span data-stu-id="54352-125">The `Get-ExecutionPolicy` cmdlet is run without a parameter to display the effective execution policy, **AllSigned** .</span></span>

### <span data-ttu-id="54352-126">Exemplo 4: desbloquear um script para executá-lo sem alterar a política de execução</span><span class="sxs-lookup"><span data-stu-id="54352-126">Example 4: Unblock a script to run it without changing the execution policy</span></span>

<span data-ttu-id="54352-127">Este exemplo mostra como a política de execução **RemoteSigned** impede que você execute scripts não assinados.</span><span class="sxs-lookup"><span data-stu-id="54352-127">This example shows how the **RemoteSigned** execution policy prevents you from running unsigned scripts.</span></span>

<span data-ttu-id="54352-128">Uma prática recomendada é ler o código do script e verificar se ele é seguro **antes** de usar o `Unblock-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="54352-128">A best practice is to read the script's code and verify it's safe **before** using the `Unblock-File` cmdlet.</span></span> <span data-ttu-id="54352-129">O `Unblock-File` cmdlet desbloqueia scripts para que eles possam ser executados, mas não altera a política de execução.</span><span class="sxs-lookup"><span data-stu-id="54352-129">The `Unblock-File` cmdlet unblocks scripts so they can run, but doesn't change the execution policy.</span></span>

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

<span data-ttu-id="54352-130">O `Set-ExecutionPolicy` usa o parâmetro **ExecutionPolicy** para especificar a política de **RemoteSigned** .</span><span class="sxs-lookup"><span data-stu-id="54352-130">The `Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="54352-131">A política é definida para o escopo padrão, **LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="54352-131">The policy is set for the default scope, **LocalMachine** .</span></span>

<span data-ttu-id="54352-132">O `Get-ExecutionPolicy` cmdlet mostra que **RemoteSigned** é a política de execução efetiva para a sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="54352-132">The `Get-ExecutionPolicy` cmdlet shows that **RemoteSigned** is the effective execution policy for the current PowerShell session.</span></span>

<span data-ttu-id="54352-133">O script de **Start-ActivityTracker.ps1** é executado a partir do diretório atual.</span><span class="sxs-lookup"><span data-stu-id="54352-133">The **Start-ActivityTracker.ps1** script is executed from the current directory.</span></span> <span data-ttu-id="54352-134">O script é bloqueado por **RemoteSigned** porque o script não está assinado digitalmente.</span><span class="sxs-lookup"><span data-stu-id="54352-134">The script is blocked by **RemoteSigned** because the script isn't digitally signed.</span></span>

<span data-ttu-id="54352-135">Neste exemplo, o código do script foi revisado e verificado como seguro para ser executado.</span><span class="sxs-lookup"><span data-stu-id="54352-135">For this example, the script's code was reviewed and verified as safe to run.</span></span> <span data-ttu-id="54352-136">O `Unblock-File` cmdlet usa o parâmetro **Path** para desbloquear o script.</span><span class="sxs-lookup"><span data-stu-id="54352-136">The `Unblock-File` cmdlet uses the **Path** parameter to unblock the script.</span></span>

<span data-ttu-id="54352-137">Para verificar se `Unblock-File` a política de execução não foi alterada, `Get-ExecutionPolicy` exibe a política de execução efetiva, **RemoteSigned** .</span><span class="sxs-lookup"><span data-stu-id="54352-137">To verify that `Unblock-File` didn't change the execution policy, `Get-ExecutionPolicy` displays the effective execution policy, **RemoteSigned** .</span></span>

<span data-ttu-id="54352-138">O script, **Start-ActivityTracker.ps1** é executado a partir do diretório atual.</span><span class="sxs-lookup"><span data-stu-id="54352-138">The script, **Start-ActivityTracker.ps1** is executed from the current directory.</span></span> <span data-ttu-id="54352-139">O script começa a ser executado porque foi desbloqueado pelo `Unblock-File` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="54352-139">The script begins to run because it was unblocked by the `Unblock-File` cmdlet.</span></span>

## <span data-ttu-id="54352-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="54352-140">PARAMETERS</span></span>

### <span data-ttu-id="54352-141">-Lista</span><span class="sxs-lookup"><span data-stu-id="54352-141">-List</span></span>

<span data-ttu-id="54352-142">Obtém todos os valores da política de execução para a sessão listada em ordem de precedência.</span><span class="sxs-lookup"><span data-stu-id="54352-142">Gets all execution policy values for the session listed in precedence order.</span></span> <span data-ttu-id="54352-143">Por padrão, `Get-ExecutionPolicy` obtém apenas a política de execução efetiva.</span><span class="sxs-lookup"><span data-stu-id="54352-143">By default, `Get-ExecutionPolicy` gets only the effective execution policy.</span></span>

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

### <span data-ttu-id="54352-144">-Escopo</span><span class="sxs-lookup"><span data-stu-id="54352-144">-Scope</span></span>

<span data-ttu-id="54352-145">Especifica o escopo que é afetado por uma política de execução.</span><span class="sxs-lookup"><span data-stu-id="54352-145">Specifies the scope that is affected by an execution policy.</span></span>

<span data-ttu-id="54352-146">A política de execução efetiva é determinada pela ordem de precedência da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="54352-146">The effective execution policy is determined by the order of precedence as follows:</span></span>

- <span data-ttu-id="54352-147">**MachinePolicy** .</span><span class="sxs-lookup"><span data-stu-id="54352-147">**MachinePolicy** .</span></span> <span data-ttu-id="54352-148">Definido por um Política de Grupo para todos os usuários do computador.</span><span class="sxs-lookup"><span data-stu-id="54352-148">Set by a Group Policy for all users of the computer.</span></span>
- <span data-ttu-id="54352-149">**UserPolicy** .</span><span class="sxs-lookup"><span data-stu-id="54352-149">**UserPolicy** .</span></span> <span data-ttu-id="54352-150">Definido por um Política de Grupo para o usuário atual do computador.</span><span class="sxs-lookup"><span data-stu-id="54352-150">Set by a Group Policy for the current user of the computer.</span></span>
- <span data-ttu-id="54352-151">**Processar** .</span><span class="sxs-lookup"><span data-stu-id="54352-151">**Process** .</span></span> <span data-ttu-id="54352-152">Afeta apenas a sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="54352-152">Affects only the current PowerShell session.</span></span>
- <span data-ttu-id="54352-153">**CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="54352-153">**CurrentUser** .</span></span> <span data-ttu-id="54352-154">Afeta somente o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="54352-154">Affects only the current user.</span></span>
- <span data-ttu-id="54352-155">**LocalMachine** .</span><span class="sxs-lookup"><span data-stu-id="54352-155">**LocalMachine** .</span></span> <span data-ttu-id="54352-156">Escopo padrão que afeta todos os usuários do computador.</span><span class="sxs-lookup"><span data-stu-id="54352-156">Default scope that affects all users of the computer.</span></span>

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

### <span data-ttu-id="54352-157">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="54352-157">CommonParameters</span></span>

<span data-ttu-id="54352-158">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="54352-158">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="54352-159">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="54352-159">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="54352-160">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="54352-160">INPUTS</span></span>

### <span data-ttu-id="54352-161">Nenhum</span><span class="sxs-lookup"><span data-stu-id="54352-161">None</span></span>

<span data-ttu-id="54352-162">`Get-ExecutionPolicy` Não aceita a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="54352-162">`Get-ExecutionPolicy` doesn't accept input from the pipeline.</span></span>

## <span data-ttu-id="54352-163">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="54352-163">OUTPUTS</span></span>

### <span data-ttu-id="54352-164">Microsoft.PowerShell.ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="54352-164">Microsoft.PowerShell.ExecutionPolicy</span></span>

## <span data-ttu-id="54352-165">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="54352-165">NOTES</span></span>

<span data-ttu-id="54352-166">Uma política de execução faz parte da estratégia de segurança do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="54352-166">An execution policy is part of the PowerShell security strategy.</span></span> <span data-ttu-id="54352-167">As políticas de execução determinam se você pode carregar arquivos de configuração, como seu perfil do PowerShell, ou executar scripts.</span><span class="sxs-lookup"><span data-stu-id="54352-167">Execution policies determine whether you can load configuration files, such as your PowerShell profile, or run scripts.</span></span> <span data-ttu-id="54352-168">E se os scripts devem ser assinados digitalmente antes de serem executados.</span><span class="sxs-lookup"><span data-stu-id="54352-168">And, whether scripts must be digitally signed before they are run.</span></span>

## <span data-ttu-id="54352-169">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="54352-169">RELATED LINKS</span></span>

[<span data-ttu-id="54352-170">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="54352-170">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md)

[<span data-ttu-id="54352-171">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="54352-171">about_Group_Policy_Settings</span></span>](../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md)

[<span data-ttu-id="54352-172">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="54352-172">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)

[<span data-ttu-id="54352-173">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="54352-173">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)

[<span data-ttu-id="54352-174">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="54352-174">Set-ExecutionPolicy</span></span>](Set-ExecutionPolicy.md)
