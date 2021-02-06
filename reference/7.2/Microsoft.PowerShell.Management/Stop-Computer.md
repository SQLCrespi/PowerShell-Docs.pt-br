---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-computer?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Computer
ms.openlocfilehash: f6d31980e27b73e884b46168606ab8255a64efb9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603738"
---
# <span data-ttu-id="fe063-102">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="fe063-102">Stop-Computer</span></span>

## <span data-ttu-id="fe063-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="fe063-103">SYNOPSIS</span></span>
<span data-ttu-id="fe063-104">Encerra (desliga) computadores locais e remotos.</span><span class="sxs-lookup"><span data-stu-id="fe063-104">Stops (shuts down) local and remote computers.</span></span>

## <span data-ttu-id="fe063-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fe063-105">SYNTAX</span></span>

### <span data-ttu-id="fe063-106">Tudo</span><span class="sxs-lookup"><span data-stu-id="fe063-106">All</span></span>

```
Stop-Computer [-WsmanAuthentication <String>] [[-ComputerName] <String[]>]
 [[-Credential] <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="fe063-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fe063-107">DESCRIPTION</span></span>

<span data-ttu-id="fe063-108">O `Stop-Computer` cmdlet desliga o computador local e os computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="fe063-108">The `Stop-Computer` cmdlet shuts down the local computer and remote computers.</span></span>

<span data-ttu-id="fe063-109">Você pode usar os parâmetros de `Stop-Computer` para especificar os níveis de autenticação e as credenciais alternativas e forçar um desligamento imediato.</span><span class="sxs-lookup"><span data-stu-id="fe063-109">You can use the parameters of `Stop-Computer` to specify the authentication levels and alternate credentials, and to force an immediate shut down.</span></span>

<span data-ttu-id="fe063-110">No PowerShell 7,1, `Stop-Computer` foi adicionado para Linux e MacOS.</span><span class="sxs-lookup"><span data-stu-id="fe063-110">In PowerShell 7.1, `Stop-Computer` was added for Linux and macOS.</span></span> <span data-ttu-id="fe063-111">Os parâmetros não têm nenhum efeito nessas plataformas.</span><span class="sxs-lookup"><span data-stu-id="fe063-111">The parameters have no effect on these platforms.</span></span> <span data-ttu-id="fe063-112">O cmdlet chama apenas o comando nativo `/sbin/shutdown` .</span><span class="sxs-lookup"><span data-stu-id="fe063-112">The cmdlet is just calling the native command `/sbin/shutdown`.</span></span>

## <span data-ttu-id="fe063-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="fe063-113">EXAMPLES</span></span>

### <span data-ttu-id="fe063-114">Exemplo 1: desligar o computador local</span><span class="sxs-lookup"><span data-stu-id="fe063-114">Example 1: Shut down the local computer</span></span>

<span data-ttu-id="fe063-115">Este exemplo desliga o computador local.</span><span class="sxs-lookup"><span data-stu-id="fe063-115">This example shuts down the local computer.</span></span>

```powershell
Stop-Computer -ComputerName localhost
```

### <span data-ttu-id="fe063-116">Exemplo 2: desligar dois computadores remotos e o computador local</span><span class="sxs-lookup"><span data-stu-id="fe063-116">Example 2: Shut down two remote computers and the local computer</span></span>

<span data-ttu-id="fe063-117">Este exemplo interrompe dois computadores remotos e o computador local.</span><span class="sxs-lookup"><span data-stu-id="fe063-117">This example stops two remote computers and the local computer.</span></span>

```powershell
Stop-Computer -ComputerName "Server01", "Server02", "localhost"
```

<span data-ttu-id="fe063-118">`Stop-Computer` usa o parâmetro **ComputerName** para especificar dois computadores remotos e o computador local.</span><span class="sxs-lookup"><span data-stu-id="fe063-118">`Stop-Computer` uses the **ComputerName** parameter to specify two remote computers and the local computer.</span></span> <span data-ttu-id="fe063-119">Cada computador é desligado.</span><span class="sxs-lookup"><span data-stu-id="fe063-119">Each computer is shut down.</span></span>

### <span data-ttu-id="fe063-120">Exemplo 3: desligar computadores remotos como um trabalho em segundo plano</span><span class="sxs-lookup"><span data-stu-id="fe063-120">Example 3: Shut down remote computers as a background job</span></span>

<span data-ttu-id="fe063-121">Neste exemplo, `Stop-Computer` é executado como um trabalho em segundo plano em dois computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="fe063-121">In this example, `Stop-Computer` runs as a background job on two remote computers.</span></span>

<span data-ttu-id="fe063-122">O operador background `&` executa o `Stop-Computer` comando como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="fe063-122">The background operator `&` runs the `Stop-Computer` command as a background job.</span></span> <span data-ttu-id="fe063-123">Para obter mais informações, consulte [about_Operators](../microsoft.powershell.core/about/about_operators.md#background-operator-).</span><span class="sxs-lookup"><span data-stu-id="fe063-123">For more information, see [about_Operators](../microsoft.powershell.core/about/about_operators.md#background-operator-).</span></span>

```powershell
$j = Stop-Computer -ComputerName "Server01", "Server02" &
$results = $j | Receive-Job
$results
```

<span data-ttu-id="fe063-124">`Stop-Computer` usa o parâmetro **ComputerName** para especificar dois computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="fe063-124">`Stop-Computer` uses the **ComputerName** parameter to specify two remote computers.</span></span> <span data-ttu-id="fe063-125">O `&` operador background executa o comando como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="fe063-125">The `&` background operator runs the command as a background job.</span></span> <span data-ttu-id="fe063-126">Os objetos de trabalho são armazenados na `$j` variável.</span><span class="sxs-lookup"><span data-stu-id="fe063-126">The job objects are stored in the `$j` variable.</span></span>

<span data-ttu-id="fe063-127">Os objetos de trabalho na `$j` variável são enviados ao pipeline para `Receive-Job` , que obtém os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="fe063-127">The job objects in the `$j` variable are sent down the pipeline to `Receive-Job`, which gets the job results.</span></span> <span data-ttu-id="fe063-128">Os objetos são armazenados na `$results` variável.</span><span class="sxs-lookup"><span data-stu-id="fe063-128">The objects are stored in the `$results` variable.</span></span> <span data-ttu-id="fe063-129">A `$results` variável exibe as informações do trabalho no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fe063-129">The `$results` variable displays the job information in the PowerShell console.</span></span>

### <span data-ttu-id="fe063-130">Exemplo 4: desligar um computador remoto</span><span class="sxs-lookup"><span data-stu-id="fe063-130">Example 4: Shut down a remote computer</span></span>

<span data-ttu-id="fe063-131">Este exemplo desliga um computador remoto usando a autenticação especificada.</span><span class="sxs-lookup"><span data-stu-id="fe063-131">This example shuts down a remote computer using specified authentication.</span></span>

```powershell
Stop-Computer -ComputerName "Server01" -WsmanAuthentication Kerberos
```

<span data-ttu-id="fe063-132">`Stop-Computer` usa o parâmetro **ComputerName** para especificar o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="fe063-132">`Stop-Computer` uses the **ComputerName** parameter to specify the remote computer.</span></span> <span data-ttu-id="fe063-133">O parâmetro **WsmanAuthentication** especifica o uso do Kerberos para estabelecer uma conexão remota.</span><span class="sxs-lookup"><span data-stu-id="fe063-133">The **WsmanAuthentication** parameter specifies to use Kerberos to establish a remote connection.</span></span>

### <span data-ttu-id="fe063-134">Exemplo 5: desligar os computadores em um domínio</span><span class="sxs-lookup"><span data-stu-id="fe063-134">Example 5: Shut down computers in a domain</span></span>

<span data-ttu-id="fe063-135">Neste exemplo, os comandos forçam um desligamento imediato de todos os computadores em um domínio especificado.</span><span class="sxs-lookup"><span data-stu-id="fe063-135">In this example, the commands force an immediate shut down of all computers in a specified domain.</span></span>

```powershell
$s = Get-Content -Path ./Domain01.txt
$c = Get-Credential -Credential Domain01\Admin01
Stop-Computer -ComputerName $s -Force -Credential $c
```

<span data-ttu-id="fe063-136">`Get-Content` usa o parâmetro **path** para obter um arquivo no diretório atual com a lista de computadores de domínio.</span><span class="sxs-lookup"><span data-stu-id="fe063-136">`Get-Content` uses the **Path** parameter to get a file in the current directory with the list of domain computers.</span></span> <span data-ttu-id="fe063-137">Os objetos são armazenados na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="fe063-137">The objects are stored in the `$s` variable.</span></span>

<span data-ttu-id="fe063-138">`Get-Credential` usa o parâmetro **Credential** para especificar as credenciais de um administrador de domínio.</span><span class="sxs-lookup"><span data-stu-id="fe063-138">`Get-Credential` uses the **Credential** parameter to specify the credentials of a domain administrator.</span></span> <span data-ttu-id="fe063-139">As credenciais são armazenadas na `$c` variável.</span><span class="sxs-lookup"><span data-stu-id="fe063-139">The credentials are stored in the `$c` variable.</span></span>

<span data-ttu-id="fe063-140">`Stop-Computer` Desliga os computadores especificados com a lista de computadores do parâmetro **ComputerName** na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="fe063-140">`Stop-Computer` shuts down the computers specified with the **ComputerName** parameter's list of computers in the `$s` variable.</span></span> <span data-ttu-id="fe063-141">O parâmetro **Force** força um desligamento imediato.</span><span class="sxs-lookup"><span data-stu-id="fe063-141">The **Force** parameter forces an immediate shutdown.</span></span> <span data-ttu-id="fe063-142">O parâmetro **Credential** envia as credenciais salvas na `$c` variável.</span><span class="sxs-lookup"><span data-stu-id="fe063-142">The **Credential** parameter submits the credentials saved in the `$c` variable.</span></span>

## <span data-ttu-id="fe063-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fe063-143">PARAMETERS</span></span>

### <span data-ttu-id="fe063-144">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="fe063-144">-ComputerName</span></span>

<span data-ttu-id="fe063-145">Especifica os computadores a serem interrompidos.</span><span class="sxs-lookup"><span data-stu-id="fe063-145">Specifies the computers to stop.</span></span> <span data-ttu-id="fe063-146">O padrão é o computador local.</span><span class="sxs-lookup"><span data-stu-id="fe063-146">The default is the local computer.</span></span>

<span data-ttu-id="fe063-147">Digite o nome da NETBIOS, o endereço IP ou o nome de domínio totalmente qualificado de um ou mais computadores em uma lista separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="fe063-147">Type the NETBIOS name, IP address, or fully qualified domain name of one or more computers in a comma-separated list.</span></span> <span data-ttu-id="fe063-148">Para especificar o computador local, digite o nome do computador ou localhost.</span><span class="sxs-lookup"><span data-stu-id="fe063-148">To specify the local computer, type the computer name or localhost.</span></span>

<span data-ttu-id="fe063-149">Esse parâmetro não depende da comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fe063-149">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="fe063-150">Você pode usar o parâmetro **ComputerName** mesmo que o computador não esteja configurado para executar comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="fe063-150">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __SERVER, Server, IPAddress

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fe063-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="fe063-151">-Confirm</span></span>

<span data-ttu-id="fe063-152">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fe063-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="fe063-153">-Credential</span><span class="sxs-lookup"><span data-stu-id="fe063-153">-Credential</span></span>

<span data-ttu-id="fe063-154">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="fe063-154">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="fe063-155">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="fe063-155">The default is the current user.</span></span>

<span data-ttu-id="fe063-156">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01**, ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fe063-156">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="fe063-157">Se você digitar um nome de usuário, você será solicitado a inserir a senha.</span><span class="sxs-lookup"><span data-stu-id="fe063-157">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="fe063-158">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="fe063-158">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="fe063-159">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="fe063-159">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fe063-160">-Force</span><span class="sxs-lookup"><span data-stu-id="fe063-160">-Force</span></span>

<span data-ttu-id="fe063-161">Força um desligamento imediato do computador.</span><span class="sxs-lookup"><span data-stu-id="fe063-161">Forces an immediate shut down of the computer.</span></span>

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

### <span data-ttu-id="fe063-162">-WsmanAuthentication</span><span class="sxs-lookup"><span data-stu-id="fe063-162">-WsmanAuthentication</span></span>

<span data-ttu-id="fe063-163">Especifica o mecanismo usado para autenticar as credenciais do usuário quando este cmdlet usa o protocolo WSMan.</span><span class="sxs-lookup"><span data-stu-id="fe063-163">Specifies the mechanism that is used to authenticate the user credentials when this cmdlet uses the WSMan protocol.</span></span> <span data-ttu-id="fe063-164">O valor padrão é **Default**.</span><span class="sxs-lookup"><span data-stu-id="fe063-164">The default value is **Default**.</span></span>

<span data-ttu-id="fe063-165">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="fe063-165">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="fe063-166">Básico</span><span class="sxs-lookup"><span data-stu-id="fe063-166">Basic</span></span>
- <span data-ttu-id="fe063-167">CredSSP</span><span class="sxs-lookup"><span data-stu-id="fe063-167">CredSSP</span></span>
- <span data-ttu-id="fe063-168">Padrão</span><span class="sxs-lookup"><span data-stu-id="fe063-168">Default</span></span>
- <span data-ttu-id="fe063-169">Digest</span><span class="sxs-lookup"><span data-stu-id="fe063-169">Digest</span></span>
- <span data-ttu-id="fe063-170">Kerberos</span><span class="sxs-lookup"><span data-stu-id="fe063-170">Kerberos</span></span>
- <span data-ttu-id="fe063-171">Negotiate.</span><span class="sxs-lookup"><span data-stu-id="fe063-171">Negotiate.</span></span>

<span data-ttu-id="fe063-172">Para obter mais informações sobre os valores desse parâmetro, consulte [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="fe063-172">For more information about the values of this parameter, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="fe063-173">A autenticação do Credential Security Service Provider (CredSSP), na qual as credenciais do usuário são passadas para um computador remoto a ser autenticado, é projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remoto.</span><span class="sxs-lookup"><span data-stu-id="fe063-173">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="fe063-174">Esse mecanismo aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="fe063-174">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="fe063-175">Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="fe063-175">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

<span data-ttu-id="fe063-176">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="fe063-176">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, CredSSP, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fe063-177">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="fe063-177">-WhatIf</span></span>

<span data-ttu-id="fe063-178">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="fe063-178">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="fe063-179">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="fe063-179">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="fe063-180">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fe063-180">CommonParameters</span></span>

<span data-ttu-id="fe063-181">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fe063-181">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fe063-182">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fe063-182">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fe063-183">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="fe063-183">INPUTS</span></span>

### <span data-ttu-id="fe063-184">Nenhum</span><span class="sxs-lookup"><span data-stu-id="fe063-184">None</span></span>

<span data-ttu-id="fe063-185">Não é possível canalizar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fe063-185">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="fe063-186">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="fe063-186">OUTPUTS</span></span>

### <span data-ttu-id="fe063-187">Nenhum</span><span class="sxs-lookup"><span data-stu-id="fe063-187">None</span></span>

## <span data-ttu-id="fe063-188">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="fe063-188">NOTES</span></span>

<span data-ttu-id="fe063-189">Esse cmdlet usa o método **Win32Shutdown** da classe WMI **Win32_OperatingSystem** .</span><span class="sxs-lookup"><span data-stu-id="fe063-189">This cmdlet uses the **Win32Shutdown** method of the **Win32_OperatingSystem** WMI class.</span></span> <span data-ttu-id="fe063-190">Esse método requer que o privilégio **SeShutdownPrivilege** seja habilitado para a conta de usuário usada para reiniciar o computador.</span><span class="sxs-lookup"><span data-stu-id="fe063-190">This method requires the **SeShutdownPrivilege** privilege be enabled for the user account used to restart the machine.</span></span>

<span data-ttu-id="fe063-191">No PowerShell 7,1, `Stop-Computer` foi adicionado para Linux e MacOS.</span><span class="sxs-lookup"><span data-stu-id="fe063-191">In PowerShell 7.1, `Stop-Computer` was added for Linux and macOS.</span></span> <span data-ttu-id="fe063-192">Para esses plataformas, o cmdlet chama o comando nativo `/sbin/shutdown` .</span><span class="sxs-lookup"><span data-stu-id="fe063-192">For these platorms, the cmdlet calls the native command `/sbin/shutdown`.</span></span>

## <span data-ttu-id="fe063-193">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="fe063-193">RELATED LINKS</span></span>

[<span data-ttu-id="fe063-194">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="fe063-194">Rename-Computer</span></span>](Rename-Computer.md)

[<span data-ttu-id="fe063-195">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="fe063-195">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="fe063-196">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="fe063-196">Test-Connection</span></span>](Test-Connection.md)

