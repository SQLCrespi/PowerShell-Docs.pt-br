---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-computersecurechannel?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ComputerSecureChannel
ms.openlocfilehash: 20ea76e725a8ab53d7090078dc819a6297a639ff
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193902"
---
# <span data-ttu-id="e49f3-103">Test-ComputerSecureChannel</span><span class="sxs-lookup"><span data-stu-id="e49f3-103">Test-ComputerSecureChannel</span></span>

## <span data-ttu-id="e49f3-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="e49f3-104">SYNOPSIS</span></span>
<span data-ttu-id="e49f3-105">Testa e repara o canal seguro entre o computador local e seu domínio.</span><span class="sxs-lookup"><span data-stu-id="e49f3-105">Tests and repairs the secure channel between the local computer and its domain.</span></span>

## <span data-ttu-id="e49f3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e49f3-106">SYNTAX</span></span>

```
Test-ComputerSecureChannel [-Repair] [-Server <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="e49f3-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e49f3-107">DESCRIPTION</span></span>
<span data-ttu-id="e49f3-108">O cmdlet **Test-ComputerSecureChannel** verifica se o canal entre o computador local e seu domínio está funcionando corretamente verificando o status de suas relações de confiança.</span><span class="sxs-lookup"><span data-stu-id="e49f3-108">The **Test-ComputerSecureChannel** cmdlet verifies that the channel between the local computer and its domain is working correctly by checking the status of its trust relationships.</span></span>
<span data-ttu-id="e49f3-109">Se uma conexão falhar, você poderá usar o parâmetro de *reparo* para tentar restaurá-lo.</span><span class="sxs-lookup"><span data-stu-id="e49f3-109">If a connection fails, you can use the *Repair* parameter to try to restore it.</span></span>

<span data-ttu-id="e49f3-110">**Test-ComputerSecureChannel** retornará $true se o canal estiver funcionando corretamente e $false se não estiver.</span><span class="sxs-lookup"><span data-stu-id="e49f3-110">**Test-ComputerSecureChannel** returns $True if the channel is working correctly and $False if it is not.</span></span>
<span data-ttu-id="e49f3-111">Esse resultado permite a você usar o cmdlet em instruções condicionais presentes em funções e scripts.</span><span class="sxs-lookup"><span data-stu-id="e49f3-111">This result lets you use the cmdlet in conditional statements in functions and scripts.</span></span>
<span data-ttu-id="e49f3-112">Para obter resultados de teste mais detalhados, use o parâmetro *Verbose* .</span><span class="sxs-lookup"><span data-stu-id="e49f3-112">To get more detailed test results, use the *Verbose* parameter.</span></span>

<span data-ttu-id="e49f3-113">Esse cmdlet funciona de modo muito similar ao NetDom.exe.</span><span class="sxs-lookup"><span data-stu-id="e49f3-113">This cmdlet works much like NetDom.exe.</span></span>
<span data-ttu-id="e49f3-114">O NetDom e o **Test-ComputerSecureChannel** usam o serviço **Netlogon** para executar as ações.</span><span class="sxs-lookup"><span data-stu-id="e49f3-114">Both NetDom and **Test-ComputerSecureChannel** use the **NetLogon** service to perform the actions.</span></span>

## <span data-ttu-id="e49f3-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="e49f3-115">EXAMPLES</span></span>

### <span data-ttu-id="e49f3-116">Exemplo 1: testar um canal entre o computador local e seu domínio</span><span class="sxs-lookup"><span data-stu-id="e49f3-116">Example 1: Test a channel between the local computer and its domain</span></span>

```
PS C:\> Test-ComputerSecureChannel
True
```

<span data-ttu-id="e49f3-117">Esse comando testa o canal entre o computador local e o domínio ao qual ele está associado.</span><span class="sxs-lookup"><span data-stu-id="e49f3-117">This command tests the channel between the local computer and the domain to which it is joined.</span></span>

### <span data-ttu-id="e49f3-118">Exemplo 2: testar um canal entre o computador local e um controlador de domínio</span><span class="sxs-lookup"><span data-stu-id="e49f3-118">Example 2: Test a channel between the local computer and a domain controller</span></span>

```
PS C:\> Test-ComputerSecureChannel -Server "DCName.fabrikam.com"
True
```

<span data-ttu-id="e49f3-119">Este comando especifica um controlador de domínio preferencial para o teste.</span><span class="sxs-lookup"><span data-stu-id="e49f3-119">This command specifies a preferred domain controller for the test.</span></span>

### <span data-ttu-id="e49f3-120">Exemplo 3: redefinir o canal entre o computador local e seu domínio</span><span class="sxs-lookup"><span data-stu-id="e49f3-120">Example 3: Reset the channel between the local computer and its domain</span></span>

```
PS C:\> Test-ComputerSecureChannel -Repair
True
```

<span data-ttu-id="e49f3-121">Esse comando redefine o canal entre o computador local e seu domínio.</span><span class="sxs-lookup"><span data-stu-id="e49f3-121">This command resets the channel between the local computer and its domain.</span></span>

### <span data-ttu-id="e49f3-122">Exemplo 4: exibir informações detalhadas sobre o teste</span><span class="sxs-lookup"><span data-stu-id="e49f3-122">Example 4: Display detailed information about the test</span></span>

```
PS C:\> Test-ComputerSecureChannel -verbose
VERBOSE: Performing operation "Test-ComputerSecureChannel" on Target "SERVER01".
True
VERBOSE: "The secure channel between 'SERVER01' and 'net.fabrikam.com' is alive and working correctly."
```

<span data-ttu-id="e49f3-123">Esse comando usa o parâmetro comum *detalhado* para solicitar mensagens detalhadas sobre a operação.</span><span class="sxs-lookup"><span data-stu-id="e49f3-123">This command uses the *Verbose* common parameter to request detailed messages about the operation.</span></span>
<span data-ttu-id="e49f3-124">Para obter mais informações sobre o *modo detalhado* , consulte about_Commonparameters.</span><span class="sxs-lookup"><span data-stu-id="e49f3-124">For more information about *Verbose* , see about_CommonParameters.</span></span>

### <span data-ttu-id="e49f3-125">Exemplo 5: testar uma conexão antes de executar um script</span><span class="sxs-lookup"><span data-stu-id="e49f3-125">Example 5: Test a connection before you run a script</span></span>

```
PS C:\> Set-Alias tcsc Test-ComputerSecureChannel
if (!(tcsc))
{Write-Host "Connection failed. Reconnect and retry."}
else { &(.\Get-Servers.ps1) }
```

<span data-ttu-id="e49f3-126">Este exemplo mostra como usar **Test-ComputerSecureChannel** para testar uma conexão antes de executar um script que requer a conexão.</span><span class="sxs-lookup"><span data-stu-id="e49f3-126">This example shows how to use **Test-ComputerSecureChannel** to test a connection before you run a script that requires the connection.</span></span>

<span data-ttu-id="e49f3-127">O primeiro comando usa o cmdlet Set-Alias para criar um alias para o nome do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e49f3-127">The first command uses the Set-Alias cmdlet to create an alias for the cmdlet name.</span></span>
<span data-ttu-id="e49f3-128">Isso economiza espaço e evita erros de digitação.</span><span class="sxs-lookup"><span data-stu-id="e49f3-128">This saves space and prevents typing errors.</span></span>

<span data-ttu-id="e49f3-129">A instrução **If** verifica o valor que **Test-ComputerSecureChannel** retorna antes de executar um script.</span><span class="sxs-lookup"><span data-stu-id="e49f3-129">The **If** statement checks the value that **Test-ComputerSecureChannel** returns before it runs a script.</span></span>

## <span data-ttu-id="e49f3-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e49f3-130">PARAMETERS</span></span>

### <span data-ttu-id="e49f3-131">-Credential</span><span class="sxs-lookup"><span data-stu-id="e49f3-131">-Credential</span></span>
<span data-ttu-id="e49f3-132">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="e49f3-132">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="e49f3-133">Digite um nome de usuário, como User01 ou Domínio01 \ Usuário01, ou insira um objeto **PSCredential** , como um que o cmdlet Get-Credential retorna.</span><span class="sxs-lookup"><span data-stu-id="e49f3-133">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one that the Get-Credential cmdlet returns.</span></span>
<span data-ttu-id="e49f3-134">Por padrão, o cmdlet usa as credenciais do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="e49f3-134">By default, the cmdlet uses the credentials of the current user.</span></span>

<span data-ttu-id="e49f3-135">O parâmetro *Credential* é projetado para uso em comandos que usam o parâmetro *Repair* para reparar o canal entre o computador e o domínio.</span><span class="sxs-lookup"><span data-stu-id="e49f3-135">The *Credential* parameter is designed for use in commands that use the *Repair* parameter to repair the channel between the computer and the domain.</span></span>

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

### <span data-ttu-id="e49f3-136">-Reparar</span><span class="sxs-lookup"><span data-stu-id="e49f3-136">-Repair</span></span>
<span data-ttu-id="e49f3-137">Indica que esse cmdlet Remove e, em seguida, recria o canal estabelecido pelo serviço NetLogon.</span><span class="sxs-lookup"><span data-stu-id="e49f3-137">Indicates that this cmdlet removes and then rebuilds the channel established by the NetLogon service.</span></span>
<span data-ttu-id="e49f3-138">Use este parâmetro para tentar restaurar uma conexão que falhou no teste.</span><span class="sxs-lookup"><span data-stu-id="e49f3-138">Use this parameter to try to restore a connection that has failed the test.</span></span>

<span data-ttu-id="e49f3-139">Para usar este parâmetro, o usuário atual precisa ser membro do grupo Administradores no computador local.</span><span class="sxs-lookup"><span data-stu-id="e49f3-139">To use this parameter, the current user must be a member of the Administrators group on the local computer.</span></span>

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

### <span data-ttu-id="e49f3-140">-Server</span><span class="sxs-lookup"><span data-stu-id="e49f3-140">-Server</span></span>
<span data-ttu-id="e49f3-141">Especifica o controlador de domínio para executar o comando.</span><span class="sxs-lookup"><span data-stu-id="e49f3-141">Specifies the domain controller to run the command.</span></span>
<span data-ttu-id="e49f3-142">Se esse parâmetro não for especificado, esse cmdlet selecionará um controlador de domínio padrão para a operação.</span><span class="sxs-lookup"><span data-stu-id="e49f3-142">If this parameter is not specified, this cmdlet selects a default domain controller for the operation.</span></span>

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

### <span data-ttu-id="e49f3-143">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e49f3-143">-Confirm</span></span>
<span data-ttu-id="e49f3-144">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e49f3-144">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e49f3-145">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e49f3-145">-WhatIf</span></span>
<span data-ttu-id="e49f3-146">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="e49f3-146">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="e49f3-147">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="e49f3-147">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e49f3-148">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e49f3-148">CommonParameters</span></span>
<span data-ttu-id="e49f3-149">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e49f3-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e49f3-150">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e49f3-150">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e49f3-151">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="e49f3-151">INPUTS</span></span>

### <span data-ttu-id="e49f3-152">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e49f3-152">None</span></span>
<span data-ttu-id="e49f3-153">Não é possível redirecionar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e49f3-153">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="e49f3-154">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="e49f3-154">OUTPUTS</span></span>

### <span data-ttu-id="e49f3-155">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="e49f3-155">System.Boolean</span></span>
<span data-ttu-id="e49f3-156">Esse cmdlet retornará $True se a conexão estiver funcionando corretamente e $False se não estiver.</span><span class="sxs-lookup"><span data-stu-id="e49f3-156">This cmdlet returns $True if the connection is working correctly and $False if it is not.</span></span>

## <span data-ttu-id="e49f3-157">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="e49f3-157">NOTES</span></span>

* <span data-ttu-id="e49f3-158">Para executar um comando **Test-ComputerSecureChannel** no Windows Vista e versões posteriores do sistema operacional Windows, abra o Windows PowerShell usando a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="e49f3-158">To run a **Test-ComputerSecureChannel** command on Windows Vista and later versions of the Windows operating system, open Windows PowerShell by using the Run as administrator option.</span></span>
* <span data-ttu-id="e49f3-159">O **Test-ComputerSecureChannel** é implementado usando a função **I_NetLogonControl2** , que controla vários aspectos do serviço Netlogon.</span><span class="sxs-lookup"><span data-stu-id="e49f3-159">**Test-ComputerSecureChannel** is implemented by using the **I_NetLogonControl2** function, which controls various aspects of the Netlogon service.</span></span>

## <span data-ttu-id="e49f3-160">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="e49f3-160">RELATED LINKS</span></span>

[<span data-ttu-id="e49f3-161">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="e49f3-161">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="e49f3-162">Reset-ComputerMachinePassword</span><span class="sxs-lookup"><span data-stu-id="e49f3-162">Reset-ComputerMachinePassword</span></span>](Reset-ComputerMachinePassword.md)

[<span data-ttu-id="e49f3-163">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="e49f3-163">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="e49f3-164">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="e49f3-164">Stop-Computer</span></span>](Stop-Computer.md)
