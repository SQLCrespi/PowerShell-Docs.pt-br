---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/04/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Computer
ms.openlocfilehash: 89e43220a8d5ac675ea232db09cf3edec2ca2b97
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193956"
---
# <span data-ttu-id="0a3e4-103">Remove-Computer</span><span class="sxs-lookup"><span data-stu-id="0a3e4-103">Remove-Computer</span></span>

## <span data-ttu-id="0a3e4-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="0a3e4-104">SYNOPSIS</span></span>
<span data-ttu-id="0a3e4-105">Remove o computador local do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-105">Removes the local computer from its domain.</span></span>

## <span data-ttu-id="0a3e4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0a3e4-106">SYNTAX</span></span>

### <span data-ttu-id="0a3e4-107">Local (padrão)</span><span class="sxs-lookup"><span data-stu-id="0a3e4-107">Local (Default)</span></span>

```
Remove-Computer [[-UnjoinDomainCredential] <PSCredential>] [-Restart] [-Force] [-PassThru]
 [-WorkgroupName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0a3e4-108">Remoto</span><span class="sxs-lookup"><span data-stu-id="0a3e4-108">Remote</span></span>

```
Remove-Computer -UnjoinDomainCredential <PSCredential> [-LocalCredential <PSCredential>] [-Restart]
 [-ComputerName <String[]>] [-Force] [-PassThru] [-WorkgroupName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="0a3e4-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0a3e4-109">DESCRIPTION</span></span>

<span data-ttu-id="0a3e4-110">O `Remove-Computer` cmdlet Remove o computador local e os computadores remotos de seus domínios atuais.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-110">The `Remove-Computer` cmdlet removes the local computer and remote computers from their current domains.</span></span>

<span data-ttu-id="0a3e4-111">Quando você remove um computador de um domínio, `Remove-Computer` o também desabilita a conta de domínio do computador.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-111">When you remove a computer from a domain, `Remove-Computer` also disables the domain account of the computer.</span></span> <span data-ttu-id="0a3e4-112">Você deve fornecer credenciais explícitas para desassociar o computador de seu domínio, mesmo quando eles são as credenciais do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-112">You must provide explicit credentials to unjoin the computer from its domain, even when they are the credentials of the current user.</span></span> <span data-ttu-id="0a3e4-113">Você deve reiniciar o computador para que a alteração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-113">You must restart the computer to make the change effective.</span></span> <span data-ttu-id="0a3e4-114">Além disso, quando um computador é removido de um domínio, você deverá movê-lo para um grupo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-114">Also, when you remove a computer from a domain, you must move it to a workgroup.</span></span> <span data-ttu-id="0a3e4-115">Utilize o parâmetro **WorkgroupName** para especificar o grupo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-115">Use the **WorkgroupName** parameter to specify the workgroup.</span></span>

<span data-ttu-id="0a3e4-116">Para mover um computador de um grupo de trabalho para um domínio, de um grupo de trabalho para outro, ou de um domínio para outro, use o `Add-Computer` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-116">To move a computer from a workgroup to a domain, from one workgroup to another, or from one domain to another, use the `Add-Computer` cmdlet.</span></span>

<span data-ttu-id="0a3e4-117">Para obter os resultados do comando, utilize os parâmetros **Verbose** e **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="0a3e4-117">To get the results of the command, use the **Verbose** and **PassThru** parameters.</span></span> <span data-ttu-id="0a3e4-118">Para suprimir o prompt do usuário, utilize o parâmetro **Force** .</span><span class="sxs-lookup"><span data-stu-id="0a3e4-118">To suppress the user prompt, use the **Force** parameter.</span></span>

<span data-ttu-id="0a3e4-119">`Remove-Computer` Remove o computador local e os computadores remotos dos domínios.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-119">`Remove-Computer` removes the local computer and remote computers from domains.</span></span> <span data-ttu-id="0a3e4-120">Ele inclui parâmetros de credenciais que especificam credenciais alternativas para se conectar a computadores remotos e ao sair de um domínio, um parâmetro **Restart** para reiniciar os computadores afetados e um parâmetro **WorkgroupName** para especificar o nome do grupo de trabalho ao qual os computadores são adicionados.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-120">It includes credential parameters that specify alternate credentials for connecting to remote computers, and unjoining from a domain, a **Restart** parameter for restarting the affected computers, and a **WorkgroupName** parameter for specifying the name of the workgroup to which computers are added.</span></span>

## <span data-ttu-id="0a3e4-121">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="0a3e4-121">EXAMPLES</span></span>

### <span data-ttu-id="0a3e4-122">Exemplo 1: remover o computador local de seu domínio</span><span class="sxs-lookup"><span data-stu-id="0a3e4-122">Example 1: Remove the local computer from its domain</span></span>

<span data-ttu-id="0a3e4-123">Este exemplo remove o computador local do domínio ao qual ele está associado.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-123">This example removes the local computer from the domain to which it is joined.</span></span>

```powershell
Remove-Computer -UnjoinDomaincredential Domain01\Admin01 -PassThru -Verbose -Restart
```

<span data-ttu-id="0a3e4-124">O parâmetro **UnjoinDomainCredential** fornece as credenciais de um administrador de domínio.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-124">The **UnjoinDomainCredential** parameter provides the credentials of a domain administrator.</span></span> <span data-ttu-id="0a3e4-125">O **PassThru** e os parâmetros comuns **detalhados** exibem informações sobre o êxito ou a falha do comando.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-125">The **PassThru** and the **Verbose** common parameters display information about the success or failure of the command.</span></span> <span data-ttu-id="0a3e4-126">O parâmetro de **reinicialização** reinicia o computador para concluir a operação de remoção.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-126">The **Restart** parameter restarts the computer to complete the remove operation.</span></span>

<span data-ttu-id="0a3e4-127">Quando nenhum nome de grupo de trabalho é especificado, o computador é movido para o grupo de trabalho nomeado depois de ser removido de seu domínio.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-127">When no workgroup name is specified, the computer is moved to the workgroup named after it is removed from its domain.</span></span>

### <span data-ttu-id="0a3e4-128">Exemplo 2: mover vários computadores para um grupo de trabalho herdado</span><span class="sxs-lookup"><span data-stu-id="0a3e4-128">Example 2: Move several computers to a legacy workgroup</span></span>

<span data-ttu-id="0a3e4-129">Este exemplo remove todos os computadores listados no `OldServers.txt` arquivo de seus domínios e os move para o grupo de trabalho **herdado** .</span><span class="sxs-lookup"><span data-stu-id="0a3e4-129">This example removes all the computers listed in the `OldServers.txt` file from their domains and moves them into the **Legacy** workgroup.</span></span>

```powershell
Remove-Computer -ComputerName (Get-Content OldServers.txt) -LocalCredential Domain01\Admin01 -UnJoinDomainCredential Domain01\Admin01 -WorkgroupName "Legacy" -Force -Restart
```

<span data-ttu-id="0a3e4-130">O parâmetro **LocalCredential** fornece as credenciais de um usuário que tem permissão para se conectar a computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-130">The **LocalCredential** parameter provides the credentials of a user who has permission to connect to remote computers.</span></span> <span data-ttu-id="0a3e4-131">O parâmetro **UnjoinDomainCredential** fornece as credenciais de um usuário que tem permissão para remover os computadores de seus domínios.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-131">The **UnjoinDomainCredential** parameter provides the credentials of a user who has permission to remove the computers from their domains.</span></span> <span data-ttu-id="0a3e4-132">O parâmetro **Force** suprime os prompts de confirmação para cada computador.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-132">The **Force** parameter suppresses the confirmation prompts for each computer.</span></span> <span data-ttu-id="0a3e4-133">O parâmetro de **reinicialização** reinicia cada um dos computadores depois que ele é removido de seu domínio.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-133">The **Restart** parameter restarts each of the computers after it is removed from its domain.</span></span>

### <span data-ttu-id="0a3e4-134">Exemplo 3: remover computadores de um grupo de trabalho sem confirmação</span><span class="sxs-lookup"><span data-stu-id="0a3e4-134">Example 3: Remove computers from a workgroup without confirmation</span></span>

<span data-ttu-id="0a3e4-135">Este exemplo remove o computador remoto, o Server01 e o computador local de seus domínios e os adiciona ao grupo de trabalho **local** .</span><span class="sxs-lookup"><span data-stu-id="0a3e4-135">This example removes the remote computer, Server01, and the local computer from their domains and adds them to the **Local** workgroup.</span></span>

```powershell
Remove-Computer -ComputerName "Server01", "localhost" -UnjoinDomainCredential Domain01\Admin01 -WorkgroupName "Local" -Restart -Force
```

<span data-ttu-id="0a3e4-136">O parâmetro **Force** suprime o prompt de confirmação para cada computador.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-136">The **Force** parameter suppresses the confirmation prompt for each computer.</span></span> <span data-ttu-id="0a3e4-137">O parâmetro de **reinicialização** reinicia os computadores para que a alteração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-137">The **Restart** parameter restarts the computers to make the change effective.</span></span>

## <span data-ttu-id="0a3e4-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0a3e4-138">PARAMETERS</span></span>

### <span data-ttu-id="0a3e4-139">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="0a3e4-139">-ComputerName</span></span>

<span data-ttu-id="0a3e4-140">Especifica os computadores a serem removidos de seus domínios.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-140">Specifies the computers to be removed from their domains.</span></span> <span data-ttu-id="0a3e4-141">O padrão é o computador local.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-141">The default is the local computer.</span></span>

<span data-ttu-id="0a3e4-142">Digite o nome NetBIOS, um endereço IP ou um FQDN (nome de domínio totalmente qualificado) dos computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-142">Type the NetBIOS name, an IP address, or a fully qualified domain name (FQDN) of the remote computers.</span></span> <span data-ttu-id="0a3e4-143">Para especificar o computador local, digite o nome do computador, um ponto (.) ou localhost.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-143">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="0a3e4-144">Esse parâmetro não depende da comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-144">This parameter does not rely on PowerShell remoting.</span></span> <span data-ttu-id="0a3e4-145">Você pode usar o parâmetro **ComputerName** de `Remove-Computer` mesmo que o computador não esteja configurado para executar comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-145">You can use the **ComputerName** parameter of `Remove-Computer` even if your computer is not configured to run remote commands.</span></span>

<span data-ttu-id="0a3e4-146">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-146">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Remote
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0a3e4-147">-Force</span><span class="sxs-lookup"><span data-stu-id="0a3e4-147">-Force</span></span>

<span data-ttu-id="0a3e4-148">Suprime o aviso ao usuário.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-148">Suppresses the user prompt.</span></span> <span data-ttu-id="0a3e4-149">Por padrão, o `Remove-Computer` solicita a confirmação antes de remover cada computador.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-149">By default, `Remove-Computer` prompts you for confirmation before removing each computer.</span></span>

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

### <span data-ttu-id="0a3e4-150">-LocalCredential</span><span class="sxs-lookup"><span data-stu-id="0a3e4-150">-LocalCredential</span></span>

<span data-ttu-id="0a3e4-151">Especifica uma conta de usuário que tem permissão para se conectar aos computadores que o parâmetro **ComputerName** especifica.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-151">Specifies a user account that has permission to connect to the computers that the **ComputerName** parameter specifies.</span></span> <span data-ttu-id="0a3e4-152">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-152">The default is the current user.</span></span>

<span data-ttu-id="0a3e4-153">Digite um nome de usuário, como `User01` ou `Domain01\User01` , ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-153">Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="0a3e4-154">Se você digitar um nome de usuário, o cmdlet solicitará uma senha.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-154">If you type a user name, the cmdlet prompts you for a password.</span></span> <span data-ttu-id="0a3e4-155">Para especificar uma conta de usuário que tenha permissão para remover o computador do seu domínio atual, utilize o parâmetro **UnjoinDomainCredential** .</span><span class="sxs-lookup"><span data-stu-id="0a3e4-155">To specify a user account that has permission to remove the computer from its current domain, use the **UnjoinDomainCredential** parameter.</span></span>

<span data-ttu-id="0a3e4-156">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-156">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Remote
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0a3e4-157">-PassThru</span><span class="sxs-lookup"><span data-stu-id="0a3e4-157">-PassThru</span></span>

<span data-ttu-id="0a3e4-158">Retorna os resultados do comando.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-158">Returns the results of the command.</span></span> <span data-ttu-id="0a3e4-159">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-159">Otherwise, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="0a3e4-160">-Restart</span><span class="sxs-lookup"><span data-stu-id="0a3e4-160">-Restart</span></span>

<span data-ttu-id="0a3e4-161">Indica que esse cmdlet reinicia os computadores que estão sendo removidos.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-161">Indicates that this cmdlet restarts the computers that are being removed.</span></span> <span data-ttu-id="0a3e4-162">Uma reinicialização é geralmente necessária para que as alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-162">A restart is often required to make the change effective.</span></span>

<span data-ttu-id="0a3e4-163">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-163">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="0a3e4-164">-UnjoinDomainCredential</span><span class="sxs-lookup"><span data-stu-id="0a3e4-164">-UnjoinDomainCredential</span></span>

<span data-ttu-id="0a3e4-165">Especifica uma conta de usuário que tenha permissão para remover os computadores de seus domínios atuais.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-165">Specifies a user account that has permission to remove the computers from their current domains.</span></span>
<span data-ttu-id="0a3e4-166">Credenciais explícitas, conforme fornecido por esse parâmetro, são necessárias para remover computadores remotos de um domínio, mesmo quando o valor é as credenciais do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-166">Explicit credentials, as provided by this parameter, are required to remove remote computers from a domain, even when the value is the credentials of the current user.</span></span>

<span data-ttu-id="0a3e4-167">Digite um nome de usuário, como User01 ou Domínio01 \ Usuário01, ou insira um objeto **PSCredential** , como um gerado por `Get-Credential` .</span><span class="sxs-lookup"><span data-stu-id="0a3e4-167">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by `Get-Credential`.</span></span> <span data-ttu-id="0a3e4-168">Se você digitar um nome de usuário, esse cmdlet solicitará uma senha.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-168">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="0a3e4-169">Para especificar uma conta de usuário que tenha permissão para se conectar a computadores remotos, use o parâmetro **LocalCredential** .</span><span class="sxs-lookup"><span data-stu-id="0a3e4-169">To specify a user account that has permission to connect to the remote computers, use the **LocalCredential** parameter.</span></span>

<span data-ttu-id="0a3e4-170">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-170">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Local, Remote
Aliases: Credential

Required: False (Local), True (Remote)
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0a3e4-171">-WorkgroupName</span><span class="sxs-lookup"><span data-stu-id="0a3e4-171">-WorkgroupName</span></span>

<span data-ttu-id="0a3e4-172">Especifica o nome de um grupo de trabalho ao qual os computadores são adicionados ao serem removidos de seus domínios.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-172">Specifies the name of a workgroup to which the computers are added when they are removed from their domains.</span></span> <span data-ttu-id="0a3e4-173">O valor padrão é **grupo de trabalho** .</span><span class="sxs-lookup"><span data-stu-id="0a3e4-173">The default value is **WORKGROUP** .</span></span> <span data-ttu-id="0a3e4-174">Quando um computador é removido de um domínio, é necessário adicioná-lo a um grupo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-174">When you remove a computer from a domain, you must add it to a workgroup.</span></span>

<span data-ttu-id="0a3e4-175">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-175">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0a3e4-176">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0a3e4-176">-Confirm</span></span>

<span data-ttu-id="0a3e4-177">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-177">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0a3e4-178">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0a3e4-178">-WhatIf</span></span>

<span data-ttu-id="0a3e4-179">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-179">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="0a3e4-180">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-180">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0a3e4-181">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0a3e4-181">CommonParameters</span></span>

<span data-ttu-id="0a3e4-182">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-182">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0a3e4-183">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0a3e4-183">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0a3e4-184">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="0a3e4-184">INPUTS</span></span>

### <span data-ttu-id="0a3e4-185">System.String</span><span class="sxs-lookup"><span data-stu-id="0a3e4-185">System.String</span></span>

<span data-ttu-id="0a3e4-186">Você pode canalizar nomes de computador para thiscmdlet.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-186">You can pipe computer names to thiscmdlet.</span></span>

## <span data-ttu-id="0a3e4-187">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="0a3e4-187">OUTPUTS</span></span>

### <span data-ttu-id="0a3e4-188">Microsoft. PowerShell. Commands. ComputerChangeInfo</span><span class="sxs-lookup"><span data-stu-id="0a3e4-188">Microsoft.PowerShell.Commands.ComputerChangeInfo</span></span>

<span data-ttu-id="0a3e4-189">Quando você usa o parâmetro **PassThru** , `Remove-Computer` retorna um objeto **ComputerChangeInfo** .</span><span class="sxs-lookup"><span data-stu-id="0a3e4-189">When you use the **PassThru** parameter, `Remove-Computer` returns a **ComputerChangeInfo** object.</span></span>
<span data-ttu-id="0a3e4-190">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-190">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="0a3e4-191">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="0a3e4-191">NOTES</span></span>

<span data-ttu-id="0a3e4-192">Esse cmdlet não remove computadores de grupos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0a3e4-192">This cmdlet does not remove computers from workgroups.</span></span>

## <span data-ttu-id="0a3e4-193">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="0a3e4-193">RELATED LINKS</span></span>

[<span data-ttu-id="0a3e4-194">Add-Computer</span><span class="sxs-lookup"><span data-stu-id="0a3e4-194">Add-Computer</span></span>](Add-Computer.md)

[<span data-ttu-id="0a3e4-195">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="0a3e4-195">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="0a3e4-196">Remove-Computer</span><span class="sxs-lookup"><span data-stu-id="0a3e4-196">Remove-Computer</span></span>](Remove-Computer.md)

[<span data-ttu-id="0a3e4-197">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="0a3e4-197">Rename-Computer</span></span>](Rename-Computer.md)

[<span data-ttu-id="0a3e4-198">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="0a3e4-198">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="0a3e4-199">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="0a3e4-199">Restore-Computer</span></span>](Restore-Computer.md)

[<span data-ttu-id="0a3e4-200">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="0a3e4-200">Stop-Computer</span></span>](Stop-Computer.md)

[<span data-ttu-id="0a3e4-201">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="0a3e4-201">Test-Connection</span></span>](Test-Connection.md)
