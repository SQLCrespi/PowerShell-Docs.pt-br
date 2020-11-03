---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-computer?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Computer
ms.openlocfilehash: a1fa09116e7069f3fc7f3d196bffd20f491a93e2
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93195020"
---
# <span data-ttu-id="05f6a-103">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="05f6a-103">Stop-Computer</span></span>

## <span data-ttu-id="05f6a-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="05f6a-104">SYNOPSIS</span></span>
<span data-ttu-id="05f6a-105">Encerra (desliga) computadores locais e remotos.</span><span class="sxs-lookup"><span data-stu-id="05f6a-105">Stops (shuts down) local and remote computers.</span></span>

## <span data-ttu-id="05f6a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="05f6a-106">SYNTAX</span></span>

### <span data-ttu-id="05f6a-107">Tudo</span><span class="sxs-lookup"><span data-stu-id="05f6a-107">All</span></span>

```
Stop-Computer [-WsmanAuthentication <String>] [[-ComputerName] <String[]>]
 [[-Credential] <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="05f6a-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="05f6a-108">DESCRIPTION</span></span>

<span data-ttu-id="05f6a-109">O `Stop-Computer` cmdlet desliga o computador local e os computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="05f6a-109">The `Stop-Computer` cmdlet shuts down the local computer and remote computers.</span></span>

<span data-ttu-id="05f6a-110">Você pode usar os parâmetros de `Stop-Computer` para especificar os níveis de autenticação e as credenciais alternativas e forçar um desligamento imediato.</span><span class="sxs-lookup"><span data-stu-id="05f6a-110">You can use the parameters of `Stop-Computer` to specify the authentication levels and alternate credentials, and to force an immediate shut down.</span></span>

<span data-ttu-id="05f6a-111">No PowerShell 7,1, `Stop-Computer` foi adicionado para Linux e MacOS.</span><span class="sxs-lookup"><span data-stu-id="05f6a-111">In PowerShell 7.1, `Stop-Computer` was added for Linux and macOS.</span></span> <span data-ttu-id="05f6a-112">Os parâmetros não têm nenhum efeito nessas plataformas.</span><span class="sxs-lookup"><span data-stu-id="05f6a-112">The parameters have no effect on these platforms.</span></span> <span data-ttu-id="05f6a-113">O cmdlet chama apenas o comando nativo `/sbin/shutdown` .</span><span class="sxs-lookup"><span data-stu-id="05f6a-113">The cmdlet is just calling the native command `/sbin/shutdown`.</span></span>

## <span data-ttu-id="05f6a-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="05f6a-114">EXAMPLES</span></span>

### <span data-ttu-id="05f6a-115">Exemplo 1: desligar o computador local</span><span class="sxs-lookup"><span data-stu-id="05f6a-115">Example 1: Shut down the local computer</span></span>

<span data-ttu-id="05f6a-116">Este exemplo desliga o computador local.</span><span class="sxs-lookup"><span data-stu-id="05f6a-116">This example shuts down the local computer.</span></span>

```powershell
Stop-Computer -ComputerName localhost
```

### <span data-ttu-id="05f6a-117">Exemplo 2: desligar dois computadores remotos e o computador local</span><span class="sxs-lookup"><span data-stu-id="05f6a-117">Example 2: Shut down two remote computers and the local computer</span></span>

<span data-ttu-id="05f6a-118">Este exemplo interrompe dois computadores remotos e o computador local.</span><span class="sxs-lookup"><span data-stu-id="05f6a-118">This example stops two remote computers and the local computer.</span></span>

```powershell
Stop-Computer -ComputerName "Server01", "Server02", "localhost"
```

<span data-ttu-id="05f6a-119">`Stop-Computer` usa o parâmetro **ComputerName** para especificar dois computadores remotos e o computador local.</span><span class="sxs-lookup"><span data-stu-id="05f6a-119">`Stop-Computer` uses the **ComputerName** parameter to specify two remote computers and the local computer.</span></span> <span data-ttu-id="05f6a-120">Cada computador é desligado.</span><span class="sxs-lookup"><span data-stu-id="05f6a-120">Each computer is shut down.</span></span>

### <span data-ttu-id="05f6a-121">Exemplo 3: desligar computadores remotos como um trabalho em segundo plano</span><span class="sxs-lookup"><span data-stu-id="05f6a-121">Example 3: Shut down remote computers as a background job</span></span>

<span data-ttu-id="05f6a-122">Neste exemplo, `Stop-Computer` é executado como um trabalho em segundo plano em dois computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="05f6a-122">In this example, `Stop-Computer` runs as a background job on two remote computers.</span></span>

<span data-ttu-id="05f6a-123">O operador background `&` executa o `Stop-Computer` comando como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="05f6a-123">The background operator `&` runs the `Stop-Computer` command as a background job.</span></span> <span data-ttu-id="05f6a-124">Para obter mais informações, consulte [about_Operators](../microsoft.powershell.core/about/about_operators.md#background-operator-).</span><span class="sxs-lookup"><span data-stu-id="05f6a-124">For more information, see [about_Operators](../microsoft.powershell.core/about/about_operators.md#background-operator-).</span></span>

```powershell
$j = Stop-Computer -ComputerName "Server01", "Server02" &
$results = $j | Receive-Job
$results
```

<span data-ttu-id="05f6a-125">`Stop-Computer` usa o parâmetro **ComputerName** para especificar dois computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="05f6a-125">`Stop-Computer` uses the **ComputerName** parameter to specify two remote computers.</span></span> <span data-ttu-id="05f6a-126">O `&` operador background executa o comando como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="05f6a-126">The `&` background operator runs the command as a background job.</span></span> <span data-ttu-id="05f6a-127">Os objetos de trabalho são armazenados na `$j` variável.</span><span class="sxs-lookup"><span data-stu-id="05f6a-127">The job objects are stored in the `$j` variable.</span></span>

<span data-ttu-id="05f6a-128">Os objetos de trabalho na `$j` variável são enviados ao pipeline para `Receive-Job` , que obtém os resultados do trabalho.</span><span class="sxs-lookup"><span data-stu-id="05f6a-128">The job objects in the `$j` variable are sent down the pipeline to `Receive-Job`, which gets the job results.</span></span> <span data-ttu-id="05f6a-129">Os objetos são armazenados na `$results` variável.</span><span class="sxs-lookup"><span data-stu-id="05f6a-129">The objects are stored in the `$results` variable.</span></span> <span data-ttu-id="05f6a-130">A `$results` variável exibe as informações do trabalho no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="05f6a-130">The `$results` variable displays the job information in the PowerShell console.</span></span>

### <span data-ttu-id="05f6a-131">Exemplo 4: desligar um computador remoto</span><span class="sxs-lookup"><span data-stu-id="05f6a-131">Example 4: Shut down a remote computer</span></span>

<span data-ttu-id="05f6a-132">Este exemplo desliga um computador remoto usando a autenticação especificada.</span><span class="sxs-lookup"><span data-stu-id="05f6a-132">This example shuts down a remote computer using specified authentication.</span></span>

```powershell
Stop-Computer -ComputerName "Server01" -WsmanAuthentication Kerberos
```

<span data-ttu-id="05f6a-133">`Stop-Computer` usa o parâmetro **ComputerName** para especificar o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="05f6a-133">`Stop-Computer` uses the **ComputerName** parameter to specify the remote computer.</span></span> <span data-ttu-id="05f6a-134">O parâmetro **WsmanAuthentication** especifica o uso do Kerberos para estabelecer uma conexão remota.</span><span class="sxs-lookup"><span data-stu-id="05f6a-134">The **WsmanAuthentication** parameter specifies to use Kerberos to establish a remote connection.</span></span>

### <span data-ttu-id="05f6a-135">Exemplo 5: desligar os computadores em um domínio</span><span class="sxs-lookup"><span data-stu-id="05f6a-135">Example 5: Shut down computers in a domain</span></span>

<span data-ttu-id="05f6a-136">Neste exemplo, os comandos forçam um desligamento imediato de todos os computadores em um domínio especificado.</span><span class="sxs-lookup"><span data-stu-id="05f6a-136">In this example, the commands force an immediate shut down of all computers in a specified domain.</span></span>

```powershell
$s = Get-Content -Path ./Domain01.txt
$c = Get-Credential -Credential Domain01\Admin01
Stop-Computer -ComputerName $s -Force -Credential $c
```

<span data-ttu-id="05f6a-137">`Get-Content` usa o parâmetro **path** para obter um arquivo no diretório atual com a lista de computadores de domínio.</span><span class="sxs-lookup"><span data-stu-id="05f6a-137">`Get-Content` uses the **Path** parameter to get a file in the current directory with the list of domain computers.</span></span> <span data-ttu-id="05f6a-138">Os objetos são armazenados na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="05f6a-138">The objects are stored in the `$s` variable.</span></span>

<span data-ttu-id="05f6a-139">`Get-Credential` usa o parâmetro **Credential** para especificar as credenciais de um administrador de domínio.</span><span class="sxs-lookup"><span data-stu-id="05f6a-139">`Get-Credential` uses the **Credential** parameter to specify the credentials of a domain administrator.</span></span> <span data-ttu-id="05f6a-140">As credenciais são armazenadas na `$c` variável.</span><span class="sxs-lookup"><span data-stu-id="05f6a-140">The credentials are stored in the `$c` variable.</span></span>

<span data-ttu-id="05f6a-141">`Stop-Computer` Desliga os computadores especificados com a lista de computadores do parâmetro **ComputerName** na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="05f6a-141">`Stop-Computer` shuts down the computers specified with the **ComputerName** parameter's list of computers in the `$s` variable.</span></span> <span data-ttu-id="05f6a-142">O parâmetro **Force** força um desligamento imediato.</span><span class="sxs-lookup"><span data-stu-id="05f6a-142">The **Force** parameter forces an immediate shutdown.</span></span> <span data-ttu-id="05f6a-143">O parâmetro **Credential** envia as credenciais salvas na `$c` variável.</span><span class="sxs-lookup"><span data-stu-id="05f6a-143">The **Credential** parameter submits the credentials saved in the `$c` variable.</span></span>

## <span data-ttu-id="05f6a-144">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="05f6a-144">PARAMETERS</span></span>

### <span data-ttu-id="05f6a-145">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="05f6a-145">-ComputerName</span></span>

<span data-ttu-id="05f6a-146">Especifica os computadores a serem interrompidos.</span><span class="sxs-lookup"><span data-stu-id="05f6a-146">Specifies the computers to stop.</span></span> <span data-ttu-id="05f6a-147">O padrão é o computador local.</span><span class="sxs-lookup"><span data-stu-id="05f6a-147">The default is the local computer.</span></span>

<span data-ttu-id="05f6a-148">Digite o nome da NETBIOS, o endereço IP ou o nome de domínio totalmente qualificado de um ou mais computadores em uma lista separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="05f6a-148">Type the NETBIOS name, IP address, or fully qualified domain name of one or more computers in a comma-separated list.</span></span> <span data-ttu-id="05f6a-149">Para especificar o computador local, digite o nome do computador ou localhost.</span><span class="sxs-lookup"><span data-stu-id="05f6a-149">To specify the local computer, type the computer name or localhost.</span></span>

<span data-ttu-id="05f6a-150">Esse parâmetro não depende da comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="05f6a-150">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="05f6a-151">Você pode usar o parâmetro **ComputerName** mesmo que o computador não esteja configurado para executar comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="05f6a-151">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

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

### <span data-ttu-id="05f6a-152">-Confirm</span><span class="sxs-lookup"><span data-stu-id="05f6a-152">-Confirm</span></span>

<span data-ttu-id="05f6a-153">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="05f6a-153">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="05f6a-154">-Credential</span><span class="sxs-lookup"><span data-stu-id="05f6a-154">-Credential</span></span>

<span data-ttu-id="05f6a-155">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="05f6a-155">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="05f6a-156">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="05f6a-156">The default is the current user.</span></span>

<span data-ttu-id="05f6a-157">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="05f6a-157">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="05f6a-158">Se você digitar um nome de usuário, você será solicitado a inserir a senha.</span><span class="sxs-lookup"><span data-stu-id="05f6a-158">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="05f6a-159">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="05f6a-159">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="05f6a-160">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="05f6a-160">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="05f6a-161">-Force</span><span class="sxs-lookup"><span data-stu-id="05f6a-161">-Force</span></span>

<span data-ttu-id="05f6a-162">Força um desligamento imediato do computador.</span><span class="sxs-lookup"><span data-stu-id="05f6a-162">Forces an immediate shut down of the computer.</span></span>

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

### <span data-ttu-id="05f6a-163">-WsmanAuthentication</span><span class="sxs-lookup"><span data-stu-id="05f6a-163">-WsmanAuthentication</span></span>

<span data-ttu-id="05f6a-164">Especifica o mecanismo usado para autenticar as credenciais do usuário quando este cmdlet usa o protocolo WSMan.</span><span class="sxs-lookup"><span data-stu-id="05f6a-164">Specifies the mechanism that is used to authenticate the user credentials when this cmdlet uses the WSMan protocol.</span></span> <span data-ttu-id="05f6a-165">O valor padrão é **Default** .</span><span class="sxs-lookup"><span data-stu-id="05f6a-165">The default value is **Default** .</span></span>

<span data-ttu-id="05f6a-166">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="05f6a-166">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="05f6a-167">Básico</span><span class="sxs-lookup"><span data-stu-id="05f6a-167">Basic</span></span>
- <span data-ttu-id="05f6a-168">CredSSP</span><span class="sxs-lookup"><span data-stu-id="05f6a-168">CredSSP</span></span>
- <span data-ttu-id="05f6a-169">Padrão</span><span class="sxs-lookup"><span data-stu-id="05f6a-169">Default</span></span>
- <span data-ttu-id="05f6a-170">Digest</span><span class="sxs-lookup"><span data-stu-id="05f6a-170">Digest</span></span>
- <span data-ttu-id="05f6a-171">Kerberos</span><span class="sxs-lookup"><span data-stu-id="05f6a-171">Kerberos</span></span>
- <span data-ttu-id="05f6a-172">Negotiate.</span><span class="sxs-lookup"><span data-stu-id="05f6a-172">Negotiate.</span></span>

<span data-ttu-id="05f6a-173">Para obter mais informações sobre os valores desse parâmetro, consulte [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="05f6a-173">For more information about the values of this parameter, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="05f6a-174">A autenticação do Credential Security Service Provider (CredSSP), na qual as credenciais do usuário são passadas para um computador remoto a ser autenticado, é projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remoto.</span><span class="sxs-lookup"><span data-stu-id="05f6a-174">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="05f6a-175">Esse mecanismo aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="05f6a-175">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="05f6a-176">Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="05f6a-176">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

<span data-ttu-id="05f6a-177">Esse parâmetro foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="05f6a-177">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="05f6a-178">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="05f6a-178">-WhatIf</span></span>

<span data-ttu-id="05f6a-179">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="05f6a-179">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="05f6a-180">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="05f6a-180">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="05f6a-181">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="05f6a-181">CommonParameters</span></span>

<span data-ttu-id="05f6a-182">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="05f6a-182">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="05f6a-183">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="05f6a-183">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="05f6a-184">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="05f6a-184">INPUTS</span></span>

### <span data-ttu-id="05f6a-185">Nenhum</span><span class="sxs-lookup"><span data-stu-id="05f6a-185">None</span></span>

<span data-ttu-id="05f6a-186">Não é possível canalizar a entrada para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="05f6a-186">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="05f6a-187">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="05f6a-187">OUTPUTS</span></span>

### <span data-ttu-id="05f6a-188">Nenhum</span><span class="sxs-lookup"><span data-stu-id="05f6a-188">None</span></span>

## <span data-ttu-id="05f6a-189">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="05f6a-189">NOTES</span></span>

<span data-ttu-id="05f6a-190">Esse cmdlet usa o método **Win32Shutdown** da classe WMI **Win32_OperatingSystem** .</span><span class="sxs-lookup"><span data-stu-id="05f6a-190">This cmdlet uses the **Win32Shutdown** method of the **Win32_OperatingSystem** WMI class.</span></span> <span data-ttu-id="05f6a-191">Esse método requer que o privilégio **SeShutdownPrivilege** seja habilitado para a conta de usuário usada para reiniciar o computador.</span><span class="sxs-lookup"><span data-stu-id="05f6a-191">This method requires the **SeShutdownPrivilege** privilege be enabled for the user account used to restart the machine.</span></span>

<span data-ttu-id="05f6a-192">No PowerShell 7,1, `Stop-Computer` foi adicionado para Linux e MacOS.</span><span class="sxs-lookup"><span data-stu-id="05f6a-192">In PowerShell 7.1, `Stop-Computer` was added for Linux and macOS.</span></span> <span data-ttu-id="05f6a-193">Para esses plataformas, o cmdlet chama o comando nativo `/sbin/shutdown` .</span><span class="sxs-lookup"><span data-stu-id="05f6a-193">For these platorms, the cmdlet calls the native command `/sbin/shutdown`.</span></span>

## <span data-ttu-id="05f6a-194">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="05f6a-194">RELATED LINKS</span></span>

[<span data-ttu-id="05f6a-195">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="05f6a-195">Rename-Computer</span></span>](Rename-Computer.md)

[<span data-ttu-id="05f6a-196">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="05f6a-196">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="05f6a-197">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="05f6a-197">Test-Connection</span></span>](Test-Connection.md)

