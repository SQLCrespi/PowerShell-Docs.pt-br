---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/1/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/rename-computer?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-Computer
ms.openlocfilehash: 2fc21594a4765a0901f61dba7b7f1a79f3259886
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94346132"
---
# <span data-ttu-id="eeb08-103">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="eeb08-103">Rename-Computer</span></span>

## <span data-ttu-id="eeb08-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="eeb08-104">SYNOPSIS</span></span>
<span data-ttu-id="eeb08-105">Renomeia um computador.</span><span class="sxs-lookup"><span data-stu-id="eeb08-105">Renames a computer.</span></span>

## <span data-ttu-id="eeb08-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="eeb08-106">SYNTAX</span></span>

```
Rename-Computer [-ComputerName <String>] [-PassThru] [-DomainCredential <PSCredential>]
 [-LocalCredential <PSCredential>] [-NewName] <String> [-Force] [-Restart] [-WsmanAuthentication <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="eeb08-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="eeb08-107">DESCRIPTION</span></span>

<span data-ttu-id="eeb08-108">O `Rename-Computer` cmdlet renomeia o computador local ou um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="eeb08-108">The `Rename-Computer` cmdlet renames the local computer or a remote computer.</span></span>
<span data-ttu-id="eeb08-109">Ele renomeia um computador em cada comando.</span><span class="sxs-lookup"><span data-stu-id="eeb08-109">It renames one computer in each command.</span></span>

<span data-ttu-id="eeb08-110">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="eeb08-110">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="eeb08-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="eeb08-111">EXAMPLES</span></span>

### <span data-ttu-id="eeb08-112">Exemplo 1: renomear o computador local</span><span class="sxs-lookup"><span data-stu-id="eeb08-112">Example 1: Rename the local computer</span></span>

<span data-ttu-id="eeb08-113">Esse comando renomeia o computador local para `Server044` e, em seguida, o reinicia para que a alteração seja efetiva.</span><span class="sxs-lookup"><span data-stu-id="eeb08-113">This command renames the local computer to `Server044` and then restarts it to make the change effective.</span></span>

```powershell
Rename-Computer -NewName "Server044" -DomainCredential Domain01\Admin01 -Restart
```

### <span data-ttu-id="eeb08-114">Exemplo 2: renomear um computador remoto</span><span class="sxs-lookup"><span data-stu-id="eeb08-114">Example 2: Rename a remote computer</span></span>

<span data-ttu-id="eeb08-115">Esse comando renomeia o `Srv01` computador para `Server001` .</span><span class="sxs-lookup"><span data-stu-id="eeb08-115">This command renames the `Srv01` computer to `Server001`.</span></span> <span data-ttu-id="eeb08-116">O computador não foi reiniciado.</span><span class="sxs-lookup"><span data-stu-id="eeb08-116">The computer is not restarted.</span></span>

<span data-ttu-id="eeb08-117">O parâmetro **DomainCredential** especifica as credenciais de um usuário que tem permissão para renomear computadores no domínio.</span><span class="sxs-lookup"><span data-stu-id="eeb08-117">The **DomainCredential** parameter specifies the credentials of a user who has permission to rename computers in the domain.</span></span>

<span data-ttu-id="eeb08-118">O parâmetro **Force** suprime o prompt de confirmação.</span><span class="sxs-lookup"><span data-stu-id="eeb08-118">The **Force** parameter suppresses the confirmation prompt.</span></span>

```powershell
Rename-Computer -ComputerName "Srv01" -NewName "Server001" -DomainCredential Domain01\Admin01 -Force
```

## <span data-ttu-id="eeb08-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="eeb08-119">PARAMETERS</span></span>

### <span data-ttu-id="eeb08-120">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="eeb08-120">-ComputerName</span></span>

<span data-ttu-id="eeb08-121">Renomeia o computador remoto especificado.</span><span class="sxs-lookup"><span data-stu-id="eeb08-121">Renames the specified remote computer.</span></span>
<span data-ttu-id="eeb08-122">O padrão é o computador local.</span><span class="sxs-lookup"><span data-stu-id="eeb08-122">The default is the local computer.</span></span>

<span data-ttu-id="eeb08-123">Digite o nome NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado de um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="eeb08-123">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span>
<span data-ttu-id="eeb08-124">Para especificar o computador local, digite o nome do computador, um ponto ( `.` ) ou `localhost` .</span><span class="sxs-lookup"><span data-stu-id="eeb08-124">To specify the local computer, type the computer name, a dot (`.`), or `localhost`.</span></span>

<span data-ttu-id="eeb08-125">Esse parâmetro não depende da comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eeb08-125">This parameter does not rely on PowerShell remoting.</span></span>
<span data-ttu-id="eeb08-126">Você pode usar o parâmetro **ComputerName** de `Rename-Computer` mesmo que o computador não esteja configurado para executar comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="eeb08-126">You can use the **ComputerName** parameter of `Rename-Computer` even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local Computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="eeb08-127">-DomainCredential</span><span class="sxs-lookup"><span data-stu-id="eeb08-127">-DomainCredential</span></span>

<span data-ttu-id="eeb08-128">Especifica uma conta de usuário que tem permissão para se conectar ao domínio.</span><span class="sxs-lookup"><span data-stu-id="eeb08-128">Specifies a user account that has permission to connect to the domain.</span></span>
<span data-ttu-id="eeb08-129">São necessárias credenciais explícitas para renomear um computador que ingressou em um domínio.</span><span class="sxs-lookup"><span data-stu-id="eeb08-129">Explicit credentials are required to rename a computer that is joined to a domain.</span></span>

<span data-ttu-id="eeb08-130">Digite um nome de usuário, como `User01` ou `Domain01\User01` , ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="eeb08-130">Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="eeb08-131">Se você digitar um nome de usuário, esse cmdlet solicitará uma senha.</span><span class="sxs-lookup"><span data-stu-id="eeb08-131">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="eeb08-132">Para especificar uma conta de usuário com permissão para se conectar ao computador especificado pelo parâmetro **ComputerName** , use o parâmetro **LocalCredential**.</span><span class="sxs-lookup"><span data-stu-id="eeb08-132">To specify a user account that has permission to connect to the computer that is specified by the **ComputerName** parameter, use the **LocalCredential** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="eeb08-133">-Force</span><span class="sxs-lookup"><span data-stu-id="eeb08-133">-Force</span></span>

<span data-ttu-id="eeb08-134">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="eeb08-134">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="eeb08-135">-LocalCredential</span><span class="sxs-lookup"><span data-stu-id="eeb08-135">-LocalCredential</span></span>

<span data-ttu-id="eeb08-136">Especifica uma conta de usuário que tenha permissão para conectar-se ao computador especificado pelo parâmetro **ComputerName**.</span><span class="sxs-lookup"><span data-stu-id="eeb08-136">Specifies a user account that has permission to connect to the computer specified by the **ComputerName** parameter.</span></span> <span data-ttu-id="eeb08-137">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="eeb08-137">The default is the current user.</span></span>

<span data-ttu-id="eeb08-138">Digite um nome de usuário, como `User01` ou `Domain01\User01` , ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="eeb08-138">Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="eeb08-139">Se você digitar um nome de usuário, esse cmdlet solicitará uma senha.</span><span class="sxs-lookup"><span data-stu-id="eeb08-139">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="eeb08-140">Para especificar uma conta de usuário que tenha permissão para se conectar ao domínio, use o parâmetro **DomainCredential**.</span><span class="sxs-lookup"><span data-stu-id="eeb08-140">To specify a user account that has permission to connect to the domain, use the **DomainCredential** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current User
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="eeb08-141">-NewName</span><span class="sxs-lookup"><span data-stu-id="eeb08-141">-NewName</span></span>

<span data-ttu-id="eeb08-142">Especifica um novo nome para o computador.</span><span class="sxs-lookup"><span data-stu-id="eeb08-142">Specifies a new name for the computer.</span></span>
<span data-ttu-id="eeb08-143">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="eeb08-143">This parameter is required.</span></span>

<span data-ttu-id="eeb08-144">Os nomes padrão podem conter letras ( `a-z` ), ( `A-Z` ), números ( `0-9` ) e hifens ( `-` ), mas sem espaços ou pontos ( `.` ).</span><span class="sxs-lookup"><span data-stu-id="eeb08-144">Standard names may contain letters (`a-z`), (`A-Z`), numbers (`0-9`), and hyphens (`-`), but no spaces or periods (`.`).</span></span> <span data-ttu-id="eeb08-145">O nome não pode consistir inteiramente de dígitos e não pode ter mais de 63 caracteres</span><span class="sxs-lookup"><span data-stu-id="eeb08-145">The name may not consist entirely of digits, and may not be longer than 63 characters</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="eeb08-146">-PassThru</span><span class="sxs-lookup"><span data-stu-id="eeb08-146">-PassThru</span></span>

<span data-ttu-id="eeb08-147">Retorna os resultados do comando.</span><span class="sxs-lookup"><span data-stu-id="eeb08-147">Returns the results of the command.</span></span>
<span data-ttu-id="eeb08-148">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="eeb08-148">Otherwise, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="eeb08-149">-Restart</span><span class="sxs-lookup"><span data-stu-id="eeb08-149">-Restart</span></span>

<span data-ttu-id="eeb08-150">Indica que esse cmdlet reinicia o computador que foi renomeado.</span><span class="sxs-lookup"><span data-stu-id="eeb08-150">Indicates that this cmdlet restarts the computer that was renamed.</span></span>
<span data-ttu-id="eeb08-151">Uma reinicialização é geralmente necessária para que as alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="eeb08-151">A restart is often required to make the change effective.</span></span>

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

### <span data-ttu-id="eeb08-152">-WsmanAuthentication</span><span class="sxs-lookup"><span data-stu-id="eeb08-152">-WsmanAuthentication</span></span>

<span data-ttu-id="eeb08-153">Especifica o mecanismo usado para autenticar as credenciais do usuário quando este cmdlet usa o protocolo WSMan.</span><span class="sxs-lookup"><span data-stu-id="eeb08-153">Specifies the mechanism that is used to authenticate the user credentials when this cmdlet uses the WSMan protocol.</span></span> <span data-ttu-id="eeb08-154">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="eeb08-154">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="eeb08-155">**Basic**</span><span class="sxs-lookup"><span data-stu-id="eeb08-155">**Basic**</span></span>
- <span data-ttu-id="eeb08-156">**CredSSP**</span><span class="sxs-lookup"><span data-stu-id="eeb08-156">**CredSSP**</span></span>
- <span data-ttu-id="eeb08-157">**Default**</span><span class="sxs-lookup"><span data-stu-id="eeb08-157">**Default**</span></span>
- <span data-ttu-id="eeb08-158">**Resumo da mensagem**</span><span class="sxs-lookup"><span data-stu-id="eeb08-158">**Digest**</span></span>
- <span data-ttu-id="eeb08-159">**Kerberos**</span><span class="sxs-lookup"><span data-stu-id="eeb08-159">**Kerberos**</span></span>
- <span data-ttu-id="eeb08-160">**Inicia**</span><span class="sxs-lookup"><span data-stu-id="eeb08-160">**Negotiate**</span></span>

<span data-ttu-id="eeb08-161">O valor padrão é **Default**.</span><span class="sxs-lookup"><span data-stu-id="eeb08-161">The default value is **Default**.</span></span>

<span data-ttu-id="eeb08-162">Para obter mais informações sobre os valores desse parâmetro, consulte [Enumeração AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="eeb08-162">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!WARNING]
> <span data-ttu-id="eeb08-163">A autenticação do Credential Security Service Provider (CredSSP), na qual as credenciais do usuário são passadas para um computador remoto a ser autenticado, é projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remoto.</span><span class="sxs-lookup"><span data-stu-id="eeb08-163">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span>
> <span data-ttu-id="eeb08-164">Esse mecanismo aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="eeb08-164">This mechanism increases the security risk of the remote operation.</span></span>
> <span data-ttu-id="eeb08-165">Se o computador remoto estiver comprometido, as credenciais passadas para ele poderão ser usadas para controlar > sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="eeb08-165">If the remote computer is compromised, the credentials that are passed to it can be used to control > the network session.</span></span>

<span data-ttu-id="eeb08-166">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="eeb08-166">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, CredSSP, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="eeb08-167">-Confirm</span><span class="sxs-lookup"><span data-stu-id="eeb08-167">-Confirm</span></span>

<span data-ttu-id="eeb08-168">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="eeb08-168">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="eeb08-169">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="eeb08-169">-WhatIf</span></span>

<span data-ttu-id="eeb08-170">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="eeb08-170">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="eeb08-171">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="eeb08-171">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="eeb08-172">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="eeb08-172">CommonParameters</span></span>

<span data-ttu-id="eeb08-173">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="eeb08-173">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="eeb08-174">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="eeb08-174">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="eeb08-175">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="eeb08-175">INPUTS</span></span>

### <span data-ttu-id="eeb08-176">Nenhum</span><span class="sxs-lookup"><span data-stu-id="eeb08-176">None</span></span>

<span data-ttu-id="eeb08-177">Esse cmdlet não tem parâmetros que obtêm entradas por valor.</span><span class="sxs-lookup"><span data-stu-id="eeb08-177">This cmdlet does not have parameters that take input by value.</span></span> <span data-ttu-id="eeb08-178">No entanto, é possível redirecionar os valores das propriedades de objetos **ComputerName** e **NewName** para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="eeb08-178">However, you can pipe the values of the **ComputerName** and **NewName** properties of objects to this cmdlet.</span></span>

## <span data-ttu-id="eeb08-179">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="eeb08-179">OUTPUTS</span></span>

### <span data-ttu-id="eeb08-180">Microsoft. PowerShell. Commands. ComputerChangeInfo</span><span class="sxs-lookup"><span data-stu-id="eeb08-180">Microsoft.PowerShell.Commands.ComputerChangeInfo</span></span>

<span data-ttu-id="eeb08-181">Esse cmdlet retorna um objeto **ComputerChangeInfo** , se você especificar o parâmetro **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="eeb08-181">This cmdlet returns a **ComputerChangeInfo** object, if you specify the **PassThru** parameter.</span></span>
<span data-ttu-id="eeb08-182">Caso contrário, ele não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="eeb08-182">Otherwise, it does not return any output.</span></span>

## <span data-ttu-id="eeb08-183">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="eeb08-183">NOTES</span></span>

<span data-ttu-id="eeb08-184">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="eeb08-184">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="eeb08-185">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="eeb08-185">RELATED LINKS</span></span>

[<span data-ttu-id="eeb08-186">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="eeb08-186">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="eeb08-187">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="eeb08-187">Stop-Computer</span></span>](Stop-Computer.md)
