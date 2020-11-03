---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pssession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enter-PSSession
ms.openlocfilehash: f5b8d82b2f2a30c176ab01be42201434842a0454
ms.sourcegitcommit: 9dddf1d2e91ebcd347fcfb7bf6ef670d49a12ab7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2020
ms.locfileid: "93195071"
---
# <span data-ttu-id="0df40-103">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="0df40-103">Enter-PSSession</span></span>

## <span data-ttu-id="0df40-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="0df40-104">SYNOPSIS</span></span>
<span data-ttu-id="0df40-105">Inicia uma sessão interativa com um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="0df40-105">Starts an interactive session with a remote computer.</span></span>

## <span data-ttu-id="0df40-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0df40-106">SYNTAX</span></span>

### <span data-ttu-id="0df40-107">ComputerName (padrão)</span><span class="sxs-lookup"><span data-stu-id="0df40-107">ComputerName (Default)</span></span>

```
Enter-PSSession [-ComputerName] <String> [-EnableNetworkAccess] [[-Credential] <PSCredential>]
 [-ConfigurationName <String>] [-Port <Int32>] [-UseSSL] [-ApplicationName <String>]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="0df40-108">SSHHost</span><span class="sxs-lookup"><span data-stu-id="0df40-108">SSHHost</span></span>

```
Enter-PSSession [-HostName] <String> [-Port <Int32>] [-UserName <String>] [-KeyFilePath <String>]
 [-SSHTransport] [<CommonParameters>]
```

### <span data-ttu-id="0df40-109">Session</span><span class="sxs-lookup"><span data-stu-id="0df40-109">Session</span></span>

```
Enter-PSSession [[-Session] <PSSession>] [<CommonParameters>]
```

### <span data-ttu-id="0df40-110">Uri</span><span class="sxs-lookup"><span data-stu-id="0df40-110">Uri</span></span>

```
Enter-PSSession [[-ConnectionUri] <Uri>] [-EnableNetworkAccess] [[-Credential] <PSCredential>]
 [-ConfigurationName <String>] [-AllowRedirection] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="0df40-111">InstanceId</span><span class="sxs-lookup"><span data-stu-id="0df40-111">InstanceId</span></span>

```
Enter-PSSession [-InstanceId <Guid>] [<CommonParameters>]
```

### <span data-ttu-id="0df40-112">ID</span><span class="sxs-lookup"><span data-stu-id="0df40-112">Id</span></span>

```
Enter-PSSession [[-Id] <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="0df40-113">Nome</span><span class="sxs-lookup"><span data-stu-id="0df40-113">Name</span></span>

```
Enter-PSSession [-Name <String>] [<CommonParameters>]
```

### <span data-ttu-id="0df40-114">VMId</span><span class="sxs-lookup"><span data-stu-id="0df40-114">VMId</span></span>

```
Enter-PSSession [-VMId] <Guid> [-Credential] <PSCredential> [-ConfigurationName <String>] [<CommonParameters>]
```

### <span data-ttu-id="0df40-115">VMName</span><span class="sxs-lookup"><span data-stu-id="0df40-115">VMName</span></span>

```
Enter-PSSession [-VMName] <String> [-Credential] <PSCredential> [-ConfigurationName <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="0df40-116">ContainerId</span><span class="sxs-lookup"><span data-stu-id="0df40-116">ContainerId</span></span>

```
Enter-PSSession [-ContainerId] <String> [-ConfigurationName <String>] [-RunAsAdministrator]
 [<CommonParameters>]
```

## <span data-ttu-id="0df40-117">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0df40-117">DESCRIPTION</span></span>

<span data-ttu-id="0df40-118">O `Enter-PSSession` cmdlet inicia uma sessão interativa com um único computador remoto.</span><span class="sxs-lookup"><span data-stu-id="0df40-118">The `Enter-PSSession` cmdlet starts an interactive session with a single remote computer.</span></span>
<span data-ttu-id="0df40-119">Durante a sessão, os comandos digitados são executados no computador remoto, assim como se você estivesse digitando diretamente no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="0df40-119">During the session, the commands that you type run on the remote computer, just as if you were typing directly on the remote computer.</span></span> <span data-ttu-id="0df40-120">Você pode ter somente uma sessão interativa por vez.</span><span class="sxs-lookup"><span data-stu-id="0df40-120">You can have only one interactive session at a time.</span></span>

<span data-ttu-id="0df40-121">Normalmente, você usa o parâmetro **ComputerName** para especificar o nome do computador remoto.</span><span class="sxs-lookup"><span data-stu-id="0df40-121">Typically, you use the **ComputerName** parameter to specify the name of the remote computer.</span></span>
<span data-ttu-id="0df40-122">No entanto, você também pode usar uma sessão que você cria usando o `New-PSSession` cmdlet para a sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="0df40-122">However, you can also use a session that you create by using the `New-PSSession` cmdlet for the interactive session.</span></span> <span data-ttu-id="0df40-123">No entanto, você não pode usar os `Disconnect-PSSession` `Connect-PSSession` `Receive-PSSession` cmdlets, ou para se desconectar ou se conectar novamente a uma sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="0df40-123">However, you cannot use the `Disconnect-PSSession`, `Connect-PSSession`, or `Receive-PSSession` cmdlets to disconnect from or re-connect to an interactive session.</span></span>

<span data-ttu-id="0df40-124">A partir do PowerShell 6,0, você pode usar Secure Shell (SSH) para estabelecer uma conexão com um computador remoto, se o SSH estiver disponível no computador local e o computador remoto estiver configurado com um ponto de extremidade SSH do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0df40-124">Starting with PowerShell 6.0 you can use Secure Shell (SSH) to establish a connection to a remote computer, if SSH is available on the local computer and the remote computer is configured with a PowerShell SSH endpoint.</span></span> <span data-ttu-id="0df40-125">O benefício de uma sessão remota do PowerShell baseada em SSH é que ela funciona em várias plataformas (Windows, Linux e macOS).</span><span class="sxs-lookup"><span data-stu-id="0df40-125">The benefit an SSH based PowerShell remote session is that it works across multiple platforms (Windows, Linux, macOS).</span></span> <span data-ttu-id="0df40-126">Para a comunicação remota baseada em SSH, use o parâmetro **hostname** definido para especificar o computador remoto e as informações de conexão relevantes.</span><span class="sxs-lookup"><span data-stu-id="0df40-126">For SSH based remoting you use the **HostName** parameter set to specify the remote computer and relevant connection information.</span></span> <span data-ttu-id="0df40-127">Para obter mais informações sobre como configurar a comunicação remota do PowerShell SSH, consulte [comunicação remota do PowerShell por SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span><span class="sxs-lookup"><span data-stu-id="0df40-127">For more information about how to set up PowerShell SSH remoting, see [PowerShell Remoting Over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

<span data-ttu-id="0df40-128">Para encerrar a sessão interativa e desconectar-se do computador remoto, use o `Exit-PSSession` cmdlet ou digite `exit` .</span><span class="sxs-lookup"><span data-stu-id="0df40-128">To end the interactive session and disconnect from the remote computer, use the `Exit-PSSession` cmdlet, or type `exit`.</span></span>

## <span data-ttu-id="0df40-129">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="0df40-129">EXAMPLES</span></span>

### <span data-ttu-id="0df40-130">Exemplo 1: iniciar uma sessão interativa</span><span class="sxs-lookup"><span data-stu-id="0df40-130">Example 1: Start an interactive session</span></span>

```
PS> Enter-PSSession
[localhost]: PS>
```

<span data-ttu-id="0df40-131">Esse comando inicia uma sessão interativa no computador local.</span><span class="sxs-lookup"><span data-stu-id="0df40-131">This command starts an interactive session on the local computer.</span></span> <span data-ttu-id="0df40-132">O prompt de comando é alterado para indicar que você está executando comandos em uma sessão diferente.</span><span class="sxs-lookup"><span data-stu-id="0df40-132">The command prompt changes to indicate that you are now running commands in a different session.</span></span>

<span data-ttu-id="0df40-133">Os comandos que você inseriu são executados na nova sessão e os resultados são retornados à sessão padrão como texto.</span><span class="sxs-lookup"><span data-stu-id="0df40-133">The commands that you enter run in the new session, and the results are returned to the default session as text.</span></span>

### <span data-ttu-id="0df40-134">Exemplo 2: trabalhar com uma sessão interativa</span><span class="sxs-lookup"><span data-stu-id="0df40-134">Example 2: Work with an interactive session</span></span>

<span data-ttu-id="0df40-135">O primeiro comando usa o `Enter-PSSession` cmdlet para iniciar uma sessão interativa com Server01, um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="0df40-135">The first command uses the `Enter-PSSession` cmdlet to start an interactive session with Server01, a remote computer.</span></span> <span data-ttu-id="0df40-136">Quando a sessão é iniciada, o prompt de comando é alterado para incluir o nome do computador.</span><span class="sxs-lookup"><span data-stu-id="0df40-136">When the session starts, the command prompt changes to include the computer name.</span></span>

<span data-ttu-id="0df40-137">O segundo comando obtém o processo do PowerShell e redireciona a saída para o arquivo Process.txt.</span><span class="sxs-lookup"><span data-stu-id="0df40-137">The second command gets the PowerShell process and redirects the output to the Process.txt file.</span></span> <span data-ttu-id="0df40-138">O comando é enviado ao computador remoto e o arquivo é salvo no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="0df40-138">The command is submitted to the remote computer, and the file is saved on the remote computer.</span></span>

<span data-ttu-id="0df40-139">O terceiro comando usa a palavra-chave **Exit** para encerrar a sessão interativa e fechar a conexão.</span><span class="sxs-lookup"><span data-stu-id="0df40-139">The third command uses the **Exit** keyword to end the interactive session and close the connection.</span></span>
<span data-ttu-id="0df40-140">O quarto comando confirma que o arquivo Process.txt está no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="0df40-140">The fourth command confirms that the Process.txt file is on the remote computer.</span></span> <span data-ttu-id="0df40-141">Um `Get-ChildItem` comando ("dir") no computador local não pode localizar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="0df40-141">A `Get-ChildItem` ("dir") command on the local computer cannot find the file.</span></span>

```powershell
PS C:\> Enter-PSSession -ComputerName Server01
[Server01]: PS>
[Server01]: PS C:\> Get-Process PowerShell > C:\ps-test\Process.txt
[Server01]: PS C:\> exit
PS C:\>
PS C:\> dir C:\ps-test\process.txt
Get-ChildItem : Cannot find path 'C:\ps-test\process.txt' because it does not exist.
At line:1 char:4
+ dir <<<<  c:\ps-test\process.txt
```

<span data-ttu-id="0df40-142">Este comando mostra como trabalhar em uma sessão interativa com um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="0df40-142">This command shows how to work in an interactive session with a remote computer.</span></span>

### <span data-ttu-id="0df40-143">Exemplo 3: usar o parâmetro Session</span><span class="sxs-lookup"><span data-stu-id="0df40-143">Example 3: Use the Session parameter</span></span>

```powershell
PS> $s = New-PSSession -ComputerName Server01
PS> Enter-PSSession -Session $s
[Server01]: PS>
```

<span data-ttu-id="0df40-144">Esses comandos usam o parâmetro **Session** do `Enter-PSSession` para executar a sessão interativa em uma sessão existente do PowerShell ( **PSSession** ).</span><span class="sxs-lookup"><span data-stu-id="0df40-144">These commands use the **Session** parameter of `Enter-PSSession` to run the interactive session in an existing PowerShell session ( **PSSession** ).</span></span>

### <span data-ttu-id="0df40-145">Exemplo 4: iniciar uma sessão interativa e especificar os parâmetros de porta e de credencial</span><span class="sxs-lookup"><span data-stu-id="0df40-145">Example 4: Start an interactive session and specify the Port and Credential parameters</span></span>

```powershell
PS> Enter-PSSession -ComputerName Server01 -Port 90 -Credential Domain01\User01
[Server01]: PS>
```

<span data-ttu-id="0df40-146">Esse comando inicia uma sessão interativa com o computador Server01.</span><span class="sxs-lookup"><span data-stu-id="0df40-146">This command starts an interactive session with the Server01 computer.</span></span> <span data-ttu-id="0df40-147">Ele usa o parâmetro **Port** para especificar a porta e o parâmetro **Credential** para especificar a conta de um usuário que tem permissão para se conectar ao computador remoto.</span><span class="sxs-lookup"><span data-stu-id="0df40-147">It uses the **Port** parameter to specify the port and the **Credential** parameter to specify the account of a user who has permission to connect to the remote computer.</span></span>

### <span data-ttu-id="0df40-148">Exemplo 5: parar uma sessão interativa</span><span class="sxs-lookup"><span data-stu-id="0df40-148">Example 5: Stop an interactive session</span></span>

```powershell
PS> Enter-PSSession -ComputerName Server01
[Server01]: PS> Exit-PSSession
PS>
```

<span data-ttu-id="0df40-149">Este exemplo mostra como iniciar e interromper uma sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="0df40-149">This example shows how to start and stop an interactive session.</span></span> <span data-ttu-id="0df40-150">O primeiro comando usa o `Enter-PSSession` cmdlet para iniciar uma sessão interativa com o computador Server01.</span><span class="sxs-lookup"><span data-stu-id="0df40-150">The first command uses the `Enter-PSSession` cmdlet to start an interactive session with the Server01 computer.</span></span>

<span data-ttu-id="0df40-151">O segundo comando usa o `Exit-PSSession` cmdlet para encerrar a sessão.</span><span class="sxs-lookup"><span data-stu-id="0df40-151">The second command uses the `Exit-PSSession` cmdlet to end the session.</span></span> <span data-ttu-id="0df40-152">Você também pode usar a palavra-chave **Exit** para encerrar a sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="0df40-152">You can also use the **Exit** keyword to end the interactive session.</span></span> <span data-ttu-id="0df40-153">`Exit-PSSession` e **Exit** têm o mesmo efeito.</span><span class="sxs-lookup"><span data-stu-id="0df40-153">`Exit-PSSession` and **Exit** have the same effect.</span></span>

### <span data-ttu-id="0df40-154">Exemplo 6: iniciar uma sessão interativa usando SSH</span><span class="sxs-lookup"><span data-stu-id="0df40-154">Example 6: Start an interactive session using SSH</span></span>

```powershell
PS> Enter-PSSession -HostName UserA@LinuxServer01
```

<span data-ttu-id="0df40-155">Este exemplo mostra como iniciar uma sessão interativa usando o Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="0df40-155">This example shows how to start an interactive session using Secure Shell (SSH).</span></span> <span data-ttu-id="0df40-156">Se o SSH estiver configurado no computador remoto para solicitar senhas, você receberá um prompt de senha.</span><span class="sxs-lookup"><span data-stu-id="0df40-156">If SSH is configured on the remote computer to prompt for passwords then you will get a password prompt.</span></span>
<span data-ttu-id="0df40-157">Caso contrário, você precisará usar a autenticação de usuário baseada em chave SSH.</span><span class="sxs-lookup"><span data-stu-id="0df40-157">Otherwise you will have to use SSH key based user authentication.</span></span>

### <span data-ttu-id="0df40-158">Exemplo 7: iniciar uma sessão interativa usando SSH e especificar a porta e a chave de autenticação do usuário</span><span class="sxs-lookup"><span data-stu-id="0df40-158">Example 7: Start an interactive session using SSH and specify the Port and user authentication key</span></span>

```powershell
PS> Enter-PSSession -HostName UserA@LinuxServer02:22 -KeyFilePath c:\<path>\userAKey_rsa
```

<span data-ttu-id="0df40-159">Este exemplo mostra como iniciar uma sessão interativa usando SSH.</span><span class="sxs-lookup"><span data-stu-id="0df40-159">This example shows how to start an interactive session using SSH.</span></span> <span data-ttu-id="0df40-160">Ele usa o parâmetro **Port** para especificar a porta a ser usada e o parâmetro **keyFilePath** para especificar uma chave RSA usada para autenticar o usuário no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="0df40-160">It uses the **Port** parameter to specify the port to use and the **KeyFilePath** parameter to specify an RSA key used to authenticate the user on the remote computer.</span></span>

## <span data-ttu-id="0df40-161">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0df40-161">PARAMETERS</span></span>

### <span data-ttu-id="0df40-162">-AllowRedirection</span><span class="sxs-lookup"><span data-stu-id="0df40-162">-AllowRedirection</span></span>

<span data-ttu-id="0df40-163">Permite o redirecionamento da conexão para um URI (Uniform Resource Identifier) alternativo.</span><span class="sxs-lookup"><span data-stu-id="0df40-163">Allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="0df40-164">Por padrão, o redirecionamento não é permitido.</span><span class="sxs-lookup"><span data-stu-id="0df40-164">By default, redirection is not allowed.</span></span>

<span data-ttu-id="0df40-165">Quando você usa o parâmetro **ConnectionURI** , o destino remoto pode retornar uma instrução para redirecionar para um URI diferente.</span><span class="sxs-lookup"><span data-stu-id="0df40-165">When you use the **ConnectionURI** parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="0df40-166">Por padrão, o PowerShell não redireciona conexões, mas você pode usar esse parâmetro para permitir que ele redirecione a conexão.</span><span class="sxs-lookup"><span data-stu-id="0df40-166">By default, PowerShell does not redirect connections, but you can use this parameter to allow it to redirect the connection.</span></span>

<span data-ttu-id="0df40-167">É possível também limitar o número de vezes que a conexão é redirecionada alterando o valor da opção de sessão **MaximumConnectionRedirectionCount** .</span><span class="sxs-lookup"><span data-stu-id="0df40-167">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span> <span data-ttu-id="0df40-168">Use o parâmetro **MaximumRedirection** do `New-PSSessionOption` cmdlet ou defina a propriedade **MaximumConnectionRedirectionCount** da variável de `$PSSessionOption` preferência.</span><span class="sxs-lookup"><span data-stu-id="0df40-168">Use the **MaximumRedirection** parameter of the `New-PSSessionOption` cmdlet or set the **MaximumConnectionRedirectionCount** property of the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="0df40-169">O valor padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="0df40-169">The default value is 5.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0df40-170">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="0df40-170">-ApplicationName</span></span>

<span data-ttu-id="0df40-171">Especifica o segmento de nome de aplicativo do URI de conexão.</span><span class="sxs-lookup"><span data-stu-id="0df40-171">Specifies the application name segment of the connection URI.</span></span> <span data-ttu-id="0df40-172">Use esse parâmetro para especificar o nome do aplicativo quando não estiver usando o parâmetro **ConnectionURI** no comando.</span><span class="sxs-lookup"><span data-stu-id="0df40-172">Use this parameter to specify the application name when you are not using the **ConnectionURI** parameter in the command.</span></span>

<span data-ttu-id="0df40-173">O valor padrão é o valor da `$PSSessionApplicationName` variável de preferência no computador local.</span><span class="sxs-lookup"><span data-stu-id="0df40-173">The default value is the value of the `$PSSessionApplicationName` preference variable on the local computer.</span></span> <span data-ttu-id="0df40-174">Se esta variável de preferência não estiver definida, o valor padrão é WSMAN.</span><span class="sxs-lookup"><span data-stu-id="0df40-174">If this preference variable is not defined, the default value is WSMAN.</span></span> <span data-ttu-id="0df40-175">Esse valor é adequado para a maioria dos usos.</span><span class="sxs-lookup"><span data-stu-id="0df40-175">This value is appropriate for most uses.</span></span> <span data-ttu-id="0df40-176">Para obter mais informações, consulte [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="0df40-176">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="0df40-177">O serviço **WinRM** usa o nome do aplicativo para selecionar um ouvinte para atender à solicitação de conexão.</span><span class="sxs-lookup"><span data-stu-id="0df40-177">The **WinRM** service uses the application name to select a listener to service the connection request.</span></span> <span data-ttu-id="0df40-178">O valor desse parâmetro deve corresponder ao valor da propriedade **URLPrefix** de um ouvinte no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="0df40-178">The value of this parameter should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0df40-179">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="0df40-179">-Authentication</span></span>

<span data-ttu-id="0df40-180">Especifica o mecanismo usado para autenticar as credenciais do usuário.</span><span class="sxs-lookup"><span data-stu-id="0df40-180">Specifies the mechanism that is used to authenticate the user's credentials.</span></span> <span data-ttu-id="0df40-181">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="0df40-181">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="0df40-182">Padrão</span><span class="sxs-lookup"><span data-stu-id="0df40-182">Default</span></span>
- <span data-ttu-id="0df40-183">Básico</span><span class="sxs-lookup"><span data-stu-id="0df40-183">Basic</span></span>
- <span data-ttu-id="0df40-184">CredSSP</span><span class="sxs-lookup"><span data-stu-id="0df40-184">Credssp</span></span>
- <span data-ttu-id="0df40-185">Digest</span><span class="sxs-lookup"><span data-stu-id="0df40-185">Digest</span></span>
- <span data-ttu-id="0df40-186">Kerberos</span><span class="sxs-lookup"><span data-stu-id="0df40-186">Kerberos</span></span>
- <span data-ttu-id="0df40-187">Negotiate</span><span class="sxs-lookup"><span data-stu-id="0df40-187">Negotiate</span></span>
- <span data-ttu-id="0df40-188">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="0df40-188">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="0df40-189">O valor padrão é Default.</span><span class="sxs-lookup"><span data-stu-id="0df40-189">The default value is Default.</span></span>

<span data-ttu-id="0df40-190">A autenticação CredSSP está disponível somente no Windows Vista, no Windows Server 2008 e em versões posteriores do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="0df40-190">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="0df40-191">Para obter mais informações sobre os valores desse parâmetro, consulte [AuthenticationMechanism enum](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="0df40-191">For more information about the values of this parameter, see [AuthenticationMechanism Enum](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

<span data-ttu-id="0df40-192">Cuidado: a autenticação do Credential Security Support Provider (CredSSP), na qual as credenciais do usuário são passadas para um computador remoto a ser autenticado, foi projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remoto.</span><span class="sxs-lookup"><span data-stu-id="0df40-192">Caution: Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="0df40-193">Esse mecanismo aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="0df40-193">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="0df40-194">Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="0df40-194">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerName, Uri
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0df40-195">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="0df40-195">-CertificateThumbprint</span></span>

<span data-ttu-id="0df40-196">Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa ação.</span><span class="sxs-lookup"><span data-stu-id="0df40-196">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="0df40-197">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="0df40-197">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="0df40-198">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="0df40-198">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="0df40-199">Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="0df40-199">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="0df40-200">Para obter um certificado, use o `Get-Item` `Get-ChildItem` comando ou na unidade de certificado do PowerShell:.</span><span class="sxs-lookup"><span data-stu-id="0df40-200">To get a certificate, use the `Get-Item` or `Get-ChildItem` command in the PowerShell Cert: drive.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0df40-201">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="0df40-201">-ComputerName</span></span>

<span data-ttu-id="0df40-202">Especifica um nome de computador.</span><span class="sxs-lookup"><span data-stu-id="0df40-202">Specifies a computer name.</span></span> <span data-ttu-id="0df40-203">Esse cmdlet inicia uma sessão interativa com o computador remoto especificado.</span><span class="sxs-lookup"><span data-stu-id="0df40-203">This cmdlet starts an interactive session with the specified remote computer.</span></span> <span data-ttu-id="0df40-204">Digite apenas um nome de computador.</span><span class="sxs-lookup"><span data-stu-id="0df40-204">Enter only one computer name.</span></span> <span data-ttu-id="0df40-205">O padrão é o computador local.</span><span class="sxs-lookup"><span data-stu-id="0df40-205">The default is the local computer.</span></span>

<span data-ttu-id="0df40-206">Digite o nome NetBIOS, o endereço IP ou o nome de domínio totalmente qualificado do computador.</span><span class="sxs-lookup"><span data-stu-id="0df40-206">Type the NetBIOS name, the IP address, or the fully qualified domain name of the computer.</span></span> <span data-ttu-id="0df40-207">Você também pode canalizar um nome de computador para `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="0df40-207">You can also pipe a computer name to `Enter-PSSession`.</span></span>

<span data-ttu-id="0df40-208">Para usar um endereço IP no valor do parâmetro **ComputerName** , o comando deve incluir o parâmetro **Credential** .</span><span class="sxs-lookup"><span data-stu-id="0df40-208">To use an IP address in the value of the **ComputerName** parameter, the command must include the **Credential** parameter.</span></span> <span data-ttu-id="0df40-209">Além disso, o computador deve ser configurado para o transporte HTTPS ou o endereço IP do computador remoto deve ser incluído na lista WinRM TrustedHosts no computador local.</span><span class="sxs-lookup"><span data-stu-id="0df40-209">Also, the computer must be configured for HTTPS transport or the IP address of the remote computer must be included in the WinRM TrustedHosts list on the local computer.</span></span> <span data-ttu-id="0df40-210">Para obter instruções sobre como adicionar um nome de computador à lista TrustedHosts, consulte "como adicionar um computador à lista de hosts confiáveis" em [about_Remote_Troubleshooting](About/about_Remote_Troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="0df40-210">For instructions for adding a computer name to the TrustedHosts list, see "How to Add a Computer to the Trusted Host List" in [about_Remote_Troubleshooting](About/about_Remote_Troubleshooting.md).</span></span>

<span data-ttu-id="0df40-211">Observação: no Windows Vista e versões posteriores do sistema operacional Windows, para incluir o computador local no valor do parâmetro **ComputerName** , você deve iniciar o PowerShell com a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="0df40-211">Note: In Windows Vista and later versions of the Windows operating system, to include the local computer in the value of the **ComputerName** parameter, you must start PowerShell with the Run as administrator option.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0df40-212">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="0df40-212">-ConfigurationName</span></span>

<span data-ttu-id="0df40-213">Especifica a configuração de sessão usada para a sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="0df40-213">Specifies the session configuration that is used for the interactive session.</span></span>

<span data-ttu-id="0df40-214">Insira um nome de configuração ou o URI do recurso totalmente qualificado para uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="0df40-214">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="0df40-215">Se você especificar apenas o nome da configuração, o seguinte URI de esquema será anexado: `http://schemas.microsoft.com/powershell` .</span><span class="sxs-lookup"><span data-stu-id="0df40-215">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/powershell`.</span></span>

<span data-ttu-id="0df40-216">Quando usado com SSH, isso especifica o subsistema a ser usado no destino, conforme definido em sshd_config.</span><span class="sxs-lookup"><span data-stu-id="0df40-216">When used with SSH, this specifies the subsystem to use on the target as defined in sshd_config.</span></span> <span data-ttu-id="0df40-217">O valor padrão para SSH é o `powershell` subsistema.</span><span class="sxs-lookup"><span data-stu-id="0df40-217">The default value for SSH is the `powershell` subsystem.</span></span>

<span data-ttu-id="0df40-218">A configuração da sessão para uma sessão está localizada no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="0df40-218">The session configuration for a session is located on the remote computer.</span></span> <span data-ttu-id="0df40-219">Se a configuração de sessão especificada não existir no computador remoto, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="0df40-219">If the specified session configuration does not exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="0df40-220">O valor padrão é o valor da `$PSSessionConfigurationName` variável de preferência no computador local.</span><span class="sxs-lookup"><span data-stu-id="0df40-220">The default value is the value of the `$PSSessionConfigurationName` preference variable on the local computer.</span></span> <span data-ttu-id="0df40-221">Se esta variável de preferência não for definida, o padrão é Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0df40-221">If this preference variable is not set, the default is Microsoft.PowerShell.</span></span> <span data-ttu-id="0df40-222">Para obter mais informações, consulte [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="0df40-222">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, Uri, VMId, VMName, ContainerId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0df40-223">-Conexãouri</span><span class="sxs-lookup"><span data-stu-id="0df40-223">-ConnectionUri</span></span>

<span data-ttu-id="0df40-224">Especifica um URI que define o ponto de extremidade de conexão para a sessão.</span><span class="sxs-lookup"><span data-stu-id="0df40-224">Specifies a URI that defines the connection endpoint for the session.</span></span> <span data-ttu-id="0df40-225">O URI deve ser totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="0df40-225">The URI must be fully qualified.</span></span> <span data-ttu-id="0df40-226">O formato dessa cadeia de caracteres é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0df40-226">The format of this string is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="0df40-227">O valor padrão é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0df40-227">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="0df40-228">Se não especificar um **ConnectionURI** , poderá usar os parâmetros **UseSSL** , **ComputerName** , **Port** e **ApplicationName** para especificar os valores do **ConnectionURI** .</span><span class="sxs-lookup"><span data-stu-id="0df40-228">If you do not specify a **ConnectionURI** , you can use the **UseSSL** , **ComputerName** , **Port** , and **ApplicationName** parameters to specify the **ConnectionURI** values.</span></span>

<span data-ttu-id="0df40-229">Os valores válidos para o segmento Transport do URI são HTTP e HTTPS.</span><span class="sxs-lookup"><span data-stu-id="0df40-229">Valid values for the Transport segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="0df40-230">Se você especificar um URI de conexão com um segmento de transporte, mas não especificar uma porta, a sessão será criada usando portas de padrões: 80 para HTTP e 443 para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="0df40-230">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created by using standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="0df40-231">Para usar as portas padrão para comunicação remota do PowerShell, especifique a porta 5985 para HTTP ou 5986 para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="0df40-231">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="0df40-232">Se o computador de destino redireciona a conexão para um URI diferente, o PowerShell impede o redirecionamento, a menos que você use o parâmetro **AllowRedirection** no comando.</span><span class="sxs-lookup"><span data-stu-id="0df40-232">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

```yaml
Type: System.Uri
Parameter Sets: Uri
Aliases: URI, CU

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0df40-233">-ContainerId</span><span class="sxs-lookup"><span data-stu-id="0df40-233">-ContainerId</span></span>

<span data-ttu-id="0df40-234">Especifica a ID de um contêiner.</span><span class="sxs-lookup"><span data-stu-id="0df40-234">Specifies the ID of a container.</span></span>

```yaml
Type: System.String
Parameter Sets: ContainerId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0df40-235">-Credential</span><span class="sxs-lookup"><span data-stu-id="0df40-235">-Credential</span></span>

<span data-ttu-id="0df40-236">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="0df40-236">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="0df40-237">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="0df40-237">The default is the current user.</span></span>

<span data-ttu-id="0df40-238">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0df40-238">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="0df40-239">Se você digitar um nome de usuário, você será solicitado a inserir a senha.</span><span class="sxs-lookup"><span data-stu-id="0df40-239">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="0df40-240">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="0df40-240">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="0df40-241">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="0df40-241">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, Uri, VMId, VMName
Aliases:

Required: True (VMId, VMName), False (ComputerName, Uri)
Position: 1
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0df40-242">-EnableNetworkAccess</span><span class="sxs-lookup"><span data-stu-id="0df40-242">-EnableNetworkAccess</span></span>

<span data-ttu-id="0df40-243">Indica que esse cmdlet adiciona um token de segurança interativo a sessões de loopback.</span><span class="sxs-lookup"><span data-stu-id="0df40-243">Indicates that this cmdlet adds an interactive security token to loopback sessions.</span></span> <span data-ttu-id="0df40-244">O token interativo permite executar comandos na sessão de loopback que obtêm dados de outros computadores.</span><span class="sxs-lookup"><span data-stu-id="0df40-244">The interactive token lets you run commands in the loopback session that get data from other computers.</span></span> <span data-ttu-id="0df40-245">Por exemplo, você pode executar um comando na sessão que copia arquivos XML de um computador remoto no computador local.</span><span class="sxs-lookup"><span data-stu-id="0df40-245">For example, you can run a command in the session that copies XML files from a remote computer to the local computer.</span></span>

<span data-ttu-id="0df40-246">Uma sessão de loopback é uma **PSSession** originada e termina no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="0df40-246">A loopback session is a **PSSession** that originates and ends on the same computer.</span></span> <span data-ttu-id="0df40-247">Para criar uma sessão de loopback, omita o parâmetro **ComputerName** ou defina seu valor como.</span><span class="sxs-lookup"><span data-stu-id="0df40-247">To create a loopback session, omit the **ComputerName** parameter or set its value to .</span></span> <span data-ttu-id="0df40-248">(ponto), localhost ou o nome do computador local.</span><span class="sxs-lookup"><span data-stu-id="0df40-248">(dot), localhost, or the name of the local computer.</span></span>

<span data-ttu-id="0df40-249">Por padrão, as sessões de loopback são criadas usando um token de rede, que pode não fornecer permissão suficiente para autenticar em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="0df40-249">By default, loopback sessions are created by using a network token, which might not provide sufficient permission to authenticate to remote computers.</span></span>

<span data-ttu-id="0df40-250">O parâmetro **EnableNetworkAccess** só é eficaz em sessões de loopback.</span><span class="sxs-lookup"><span data-stu-id="0df40-250">The **EnableNetworkAccess** parameter is effective only in loopback sessions.</span></span> <span data-ttu-id="0df40-251">Se você usar **EnableNetworkAccess** ao criar uma sessão em um computador remoto, o comando terá sucesso, mas o parâmetro será ignorado.</span><span class="sxs-lookup"><span data-stu-id="0df40-251">If you use **EnableNetworkAccess** when you create a session on a remote computer, the command succeeds, but the parameter is ignored.</span></span>

<span data-ttu-id="0df40-252">Também é possível permitir o acesso remoto em uma sessão de loopback usando o valor **CredSSP** do parâmetro **Authentication** , que delega as credenciais de sessão a outros computadores.</span><span class="sxs-lookup"><span data-stu-id="0df40-252">You can also allow remote access in a loopback session by using the **CredSSP** value of the **Authentication** parameter, which delegates the session credentials to other computers.</span></span>

<span data-ttu-id="0df40-253">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0df40-253">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0df40-254">-HostName</span><span class="sxs-lookup"><span data-stu-id="0df40-254">-HostName</span></span>

<span data-ttu-id="0df40-255">Especifica um nome de computador para uma conexão baseada em Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="0df40-255">Specifies a computer name for a Secure Shell (SSH) based connection.</span></span> <span data-ttu-id="0df40-256">Isso é semelhante ao parâmetro **ComputerName** , exceto pelo fato de que a conexão com o computador remoto é feita usando SSH em vez de WinRM do Windows.</span><span class="sxs-lookup"><span data-stu-id="0df40-256">This is similar to the **ComputerName** parameter except that the connection to the remote computer is made using SSH rather than Windows WinRM.</span></span> <span data-ttu-id="0df40-257">Esse parâmetro dá suporte à especificação do nome de usuário e/ou porta como parte do valor do parâmetro de nome do host usando o formulário `user@hostname:port` .</span><span class="sxs-lookup"><span data-stu-id="0df40-257">This parameter supports specifying the user name and/or port as part of the host name parameter value using the form `user@hostname:port`.</span></span> <span data-ttu-id="0df40-258">O nome de usuário e/ou a porta especificada como parte do nome do host tem precedência sobre os `-UserName` `-Port` parâmetros e, se especificado.</span><span class="sxs-lookup"><span data-stu-id="0df40-258">The user name and/or port specified as part of the host name takes precedence over the `-UserName` and `-Port` parameters, if specified.</span></span> <span data-ttu-id="0df40-259">Isso permite passar vários nomes de computador para esse parâmetro, em que alguns têm nomes de usuário e/ou portas específicos, enquanto outros usam o nome de usuário e/ou a porta dos `-UserName` `-Port` parâmetros e.</span><span class="sxs-lookup"><span data-stu-id="0df40-259">This allows passing multiple computer names to this parameter where some have specific user names and/or ports, while others use the user name and/or port from the `-UserName` and `-Port` parameters.</span></span>

<span data-ttu-id="0df40-260">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="0df40-260">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0df40-261">-Id</span><span class="sxs-lookup"><span data-stu-id="0df40-261">-Id</span></span>

<span data-ttu-id="0df40-262">Especifica a ID de uma sessão existente.</span><span class="sxs-lookup"><span data-stu-id="0df40-262">Specifies the ID of an existing session.</span></span> <span data-ttu-id="0df40-263">`Enter-PSSession` usa a sessão especificada para a sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="0df40-263">`Enter-PSSession` uses the specified session for the interactive session.</span></span>

<span data-ttu-id="0df40-264">Para localizar a ID de uma sessão, use o `Get-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0df40-264">To find the ID of a session, use the `Get-PSSession` cmdlet.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Id
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0df40-265">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="0df40-265">-InstanceId</span></span>

<span data-ttu-id="0df40-266">Especifica a ID de instância de uma sessão existente.</span><span class="sxs-lookup"><span data-stu-id="0df40-266">Specifies the instance ID of an existing session.</span></span> <span data-ttu-id="0df40-267">`Enter-PSSession` usa a sessão especificada para a sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="0df40-267">`Enter-PSSession` uses the specified session for the interactive session.</span></span>

<span data-ttu-id="0df40-268">A ID de instância é um GUID.</span><span class="sxs-lookup"><span data-stu-id="0df40-268">The instance ID is a GUID.</span></span> <span data-ttu-id="0df40-269">Para localizar a ID de instância de uma sessão, use o `Get-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0df40-269">To find the instance ID of a session, use the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="0df40-270">Você também pode usar os parâmetros de **sessão** , **nome** ou **ID** para especificar uma sessão existente.</span><span class="sxs-lookup"><span data-stu-id="0df40-270">You can also use the **Session** , **Name** , or **ID** parameters to specify an existing session.</span></span> <span data-ttu-id="0df40-271">Ou, você pode usar o parâmetro **ComputerName** para iniciar uma sessão temporária.</span><span class="sxs-lookup"><span data-stu-id="0df40-271">Or, you can use the **ComputerName** parameter to start a temporary session.</span></span>

```yaml
Type: System.Guid
Parameter Sets: InstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0df40-272">-KeyFilePath</span><span class="sxs-lookup"><span data-stu-id="0df40-272">-KeyFilePath</span></span>

<span data-ttu-id="0df40-273">Especifica um caminho de arquivo de chave usado pelo Secure Shell (SSH) para autenticar um usuário em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="0df40-273">Specifies a key file path used by Secure Shell (SSH) to authenticate a user on a remote computer.</span></span>

<span data-ttu-id="0df40-274">O SSH permite que a autenticação do usuário seja executada por meio de chaves privadas/públicas como uma alternativa à autenticação básica de senha.</span><span class="sxs-lookup"><span data-stu-id="0df40-274">SSH allows user authentication to be performed via private/public keys as an alternative to basic password authentication.</span></span> <span data-ttu-id="0df40-275">Se o computador remoto estiver configurado para autenticação de chave, esse parâmetro poderá ser usado para fornecer a chave que identifica o usuário.</span><span class="sxs-lookup"><span data-stu-id="0df40-275">If the remote computer is configured for key authentication then this parameter can be used to provide the key that identifies the user.</span></span>

<span data-ttu-id="0df40-276">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="0df40-276">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases: IdentityFilePath

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0df40-277">-Name</span><span class="sxs-lookup"><span data-stu-id="0df40-277">-Name</span></span>

<span data-ttu-id="0df40-278">Especifica o nome amigável de uma sessão existente.</span><span class="sxs-lookup"><span data-stu-id="0df40-278">Specifies the friendly name of an existing session.</span></span> <span data-ttu-id="0df40-279">`Enter-PSSession` usa a sessão especificada para a sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="0df40-279">`Enter-PSSession` uses the specified session for the interactive session.</span></span>

<span data-ttu-id="0df40-280">Se o nome que você especificou corresponder a mais de uma sessão, o comando falha.</span><span class="sxs-lookup"><span data-stu-id="0df40-280">If the name that you specify matches more than one session, the command fails.</span></span> <span data-ttu-id="0df40-281">Você também pode usar os parâmetros **Session** , **InstanceId** ou **ID** para especificar uma sessão existente.</span><span class="sxs-lookup"><span data-stu-id="0df40-281">You can also use the **Session** , **InstanceID** , or **ID** parameters to specify an existing session.</span></span> <span data-ttu-id="0df40-282">Ou, você pode usar o parâmetro **ComputerName** para iniciar uma sessão temporária.</span><span class="sxs-lookup"><span data-stu-id="0df40-282">Or, you can use the **ComputerName** parameter to start a temporary session.</span></span>

<span data-ttu-id="0df40-283">Para estabelecer um nome amigável para uma sessão, use o parâmetro **Name** do `New-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0df40-283">To establish a friendly name for a session, use the **Name** parameter of the `New-PSSession` cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0df40-284">-Port</span><span class="sxs-lookup"><span data-stu-id="0df40-284">-Port</span></span>

<span data-ttu-id="0df40-285">Especifica a porta de rede no computador remoto que é usada para este comando.</span><span class="sxs-lookup"><span data-stu-id="0df40-285">Specifies the network port on the remote computer that is used for this command.</span></span>

<span data-ttu-id="0df40-286">No PowerShell 6,0, esse parâmetro foi incluído no conjunto de parâmetros **hostname** que dá suporte a conexões Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="0df40-286">In PowerShell 6.0 this parameter was inlcuded in the **HostName** parameter set which supports Secure Shell (SSH) connections.</span></span>

<span data-ttu-id="0df40-287">**WinRM (conjunto de parâmetros ComputerName)**</span><span class="sxs-lookup"><span data-stu-id="0df40-287">**WinRM (ComputerName parameter set)**</span></span>

<span data-ttu-id="0df40-288">Para se conectar a um computador remoto, este deve estar escutando na porta usada pela conexão.</span><span class="sxs-lookup"><span data-stu-id="0df40-288">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="0df40-289">As portas padrão são 5985, que é a porta do WinRM para HTTP e 5986, que é a porta do WinRM para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="0df40-289">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="0df40-290">Antes de usar uma porta alternativa, você deve configurar o ouvinte de WinRM no computador remoto para escutar na porta.</span><span class="sxs-lookup"><span data-stu-id="0df40-290">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="0df40-291">Use os seguintes comandos para configurar o ouvinte:</span><span class="sxs-lookup"><span data-stu-id="0df40-291">Use the following commands to configure the listener:</span></span>

1. `winrm delete winrm/config/listener?Address=*+Transport=HTTP`
2. `winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number\>"}`

<span data-ttu-id="0df40-292">Não use o parâmetro **Port** a menos que seja necessário.</span><span class="sxs-lookup"><span data-stu-id="0df40-292">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="0df40-293">A configuração da porta no comando se aplica a todos os computadores ou sessões em que o comando for executado.</span><span class="sxs-lookup"><span data-stu-id="0df40-293">The port setting in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="0df40-294">Uma configuração de porta alternativa pode impedir que o comando seja executado em todos os computadores.</span><span class="sxs-lookup"><span data-stu-id="0df40-294">An alternate port setting might prevent the command from running on all computers.</span></span>

<span data-ttu-id="0df40-295">**SSH (conjunto de parâmetros do nome do host)**</span><span class="sxs-lookup"><span data-stu-id="0df40-295">**SSH (HostName parameter set)**</span></span>

<span data-ttu-id="0df40-296">Para se conectar a um computador remoto, o computador remoto deve ser configurado com o serviço SSH (SSHD) e deve estar escutando na porta usada pela conexão.</span><span class="sxs-lookup"><span data-stu-id="0df40-296">To connect to a remote computer, the remote computer must be configured with the SSH service (SSHD) and must be listening on the port that the connection uses.</span></span> <span data-ttu-id="0df40-297">A porta padrão para SSH é 22.</span><span class="sxs-lookup"><span data-stu-id="0df40-297">The default port for SSH is 22.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerName, SSHHost
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0df40-298">-RunAsAdministrator</span><span class="sxs-lookup"><span data-stu-id="0df40-298">-RunAsAdministrator</span></span>

<span data-ttu-id="0df40-299">Indica que a **PSSession** é executada como administrador.</span><span class="sxs-lookup"><span data-stu-id="0df40-299">Indicates that the **PSSession** runs as administrator.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ContainerId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0df40-300">-Sessão</span><span class="sxs-lookup"><span data-stu-id="0df40-300">-Session</span></span>

<span data-ttu-id="0df40-301">Especifica uma sessão do PowerShell ( **PSSession** ) a ser usada para a sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="0df40-301">Specifies a PowerShell session ( **PSSession** ) to use for the interactive session.</span></span> <span data-ttu-id="0df40-302">Esse parâmetro usa um objeto de sessão.</span><span class="sxs-lookup"><span data-stu-id="0df40-302">This parameter takes a session object.</span></span> <span data-ttu-id="0df40-303">Você também pode usar os parâmetros **Name** , **InstanceId** ou **ID** para especificar uma **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="0df40-303">You can also use the **Name** , **InstanceID** , or **ID** parameters to specify a **PSSession** .</span></span>

<span data-ttu-id="0df40-304">Insira uma variável que contenha um objeto de sessão ou um comando que cria ou Obtém um objeto de sessão, como um `New-PSSession` `Get-PSSession` comando ou.</span><span class="sxs-lookup"><span data-stu-id="0df40-304">Enter a variable that contains a session object or a command that creates or gets a session object, such as a `New-PSSession` or `Get-PSSession` command.</span></span> <span data-ttu-id="0df40-305">Também é possível canalizar um objeto de sessão para `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="0df40-305">You can also pipe a session object to `Enter-PSSession`.</span></span> <span data-ttu-id="0df40-306">Você pode enviar apenas uma **PSSession** usando esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="0df40-306">You can submit only one **PSSession** by using this parameter.</span></span> <span data-ttu-id="0df40-307">Se você inserir uma variável que contenha mais de uma **PSSession** , o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="0df40-307">If you enter a variable that contains more than one **PSSession** , the command fails.</span></span>

<span data-ttu-id="0df40-308">Quando você usa `Exit-PSSession` o ou a palavra-chave **Exit** , a sessão interativa termina, mas a **PSSession** que você criou permanece aberta e disponível para uso.</span><span class="sxs-lookup"><span data-stu-id="0df40-308">When you use `Exit-PSSession` or the **EXIT** keyword, the interactive session ends, but the **PSSession** that you created remains open and available for use.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: Session
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0df40-309">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="0df40-309">-SessionOption</span></span>

<span data-ttu-id="0df40-310">Define opções avançadas para a sessão.</span><span class="sxs-lookup"><span data-stu-id="0df40-310">Sets advanced options for the session.</span></span> <span data-ttu-id="0df40-311">Insira um objeto **SessionOption** , como um que você cria usando o `New-PSSessionOption` cmdlet ou uma tabela de hash na qual as chaves são nomes de opção de sessão e os valores são valores de opção de sessão.</span><span class="sxs-lookup"><span data-stu-id="0df40-311">Enter a **SessionOption** object, such as one that you create by using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="0df40-312">Os valores padrão para as opções são determinados pelo valor da variável de `$PSSessionOption` preferência, se estiver definido.</span><span class="sxs-lookup"><span data-stu-id="0df40-312">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="0df40-313">Caso contrário, os valores padrão são estabelecidos por opções definidas na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="0df40-313">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="0df40-314">Os valores de opção de sessão têm precedência sobre valores padrão para sessões definidas na `$PSSessionOption` variável de preferência e na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="0df40-314">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="0df40-315">No entanto, eles não têm precedência sobre valores máximos, cotas ou limites definidos na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="0df40-315">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span>

<span data-ttu-id="0df40-316">Para obter uma descrição das opções de sessão, incluindo os valores padrão, consulte `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="0df40-316">For a description of the session options, including the default values, see `New-PSSessionOption`.</span></span>
<span data-ttu-id="0df40-317">Para obter informações sobre a `$PSSessionOption` variável de preferência, consulte [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="0df40-317">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span> <span data-ttu-id="0df40-318">Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="0df40-318">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0df40-319">-SSHTransport</span><span class="sxs-lookup"><span data-stu-id="0df40-319">-SSHTransport</span></span>

<span data-ttu-id="0df40-320">Indica que a conexão remota é estabelecida usando Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="0df40-320">Indicates that the remote connection is established using Secure Shell (SSH).</span></span>

<span data-ttu-id="0df40-321">Por padrão, o PowerShell usa o Windows WinRM para se conectar a um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="0df40-321">By default PowerShell uses Windows WinRM to connect to a remote computer.</span></span> <span data-ttu-id="0df40-322">Essa opção força o PowerShell a usar o parâmetro HostName definido para estabelecer uma conexão remota com base em SSH.</span><span class="sxs-lookup"><span data-stu-id="0df40-322">This switch forces PowerShell to use the HostName parameter set for establishing an SSH based remote connection.</span></span>

<span data-ttu-id="0df40-323">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="0df40-323">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SSHHost
Aliases:
Accepted values: true

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0df40-324">-Subsistema</span><span class="sxs-lookup"><span data-stu-id="0df40-324">-Subsystem</span></span>

<span data-ttu-id="0df40-325">Especifica o subsistema SSH usado para a nova **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="0df40-325">Specifies the SSH subsystem used for the new **PSSession** .</span></span>

<span data-ttu-id="0df40-326">Isso especifica o subsistema a ser usado no destino, conforme definido em sshd_config.</span><span class="sxs-lookup"><span data-stu-id="0df40-326">This specifies the subsystem to use on the target as defined in sshd_config.</span></span> <span data-ttu-id="0df40-327">O subsistema inicia uma versão específica do PowerShell com parâmetros predefinidos.</span><span class="sxs-lookup"><span data-stu-id="0df40-327">The subsystem starts a specific version of PowerShell with predefined parameters.</span></span> <span data-ttu-id="0df40-328">Se o subsistema especificado não existir no computador remoto, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="0df40-328">If the specified subsystem does not exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="0df40-329">Se esse parâmetro não for usado, o padrão será o subsistema ' PowerShell '.</span><span class="sxs-lookup"><span data-stu-id="0df40-329">If this parameter is not used, the default is the 'powershell' subsystem.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases:

Required: False
Position: Named
Default value: powershell
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0df40-330">-UserName</span><span class="sxs-lookup"><span data-stu-id="0df40-330">-UserName</span></span>

<span data-ttu-id="0df40-331">Especifica o nome de usuário para a conta usada para criar uma sessão no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="0df40-331">Specifies the user name for the account used to create a session on the remote computer.</span></span> <span data-ttu-id="0df40-332">O método de autenticação de usuário dependerá de como o Secure Shell (SSH) está configurado no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="0df40-332">User authentication method will depend on how Secure Shell (SSH) is configured on the remote computer.</span></span>

<span data-ttu-id="0df40-333">Se o SSH estiver configurado para autenticação de senha básica, você será solicitado a fornecer a senha do usuário.</span><span class="sxs-lookup"><span data-stu-id="0df40-333">If SSH is configured for basic password authentication then you will be prompted for the user password.</span></span>

<span data-ttu-id="0df40-334">Se o SSH estiver configurado para a autenticação de usuário baseada em chave, um caminho de arquivo de chave poderá ser fornecido por meio do parâmetro **keyFilePath** e nenhum prompt de senha ocorrerá.</span><span class="sxs-lookup"><span data-stu-id="0df40-334">If SSH is configured for key based user authentication then a key file path can be provided via the **KeyFilePath** parameter and no password prompt will occur.</span></span> <span data-ttu-id="0df40-335">Observe que, se o arquivo de chave de usuário do cliente estiver localizado em um local de SSH conhecido, o parâmetro **keyFilePath** não será necessário para a autenticação baseada em chave e a autenticação do usuário ocorrerá automaticamente com base no nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="0df40-335">Note that if the client user key file is located in an SSH known location then the **KeyFilePath** parameter is not needed for key based authentication, and user authentication will occur automatically based on the user name.</span></span> <span data-ttu-id="0df40-336">Consulte a documentação do SSH sobre autenticação de usuário baseada em chave para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0df40-336">See SSH documentation about key based user authentication for more information.</span></span>

<span data-ttu-id="0df40-337">Esse não é um parâmetro obrigatório.</span><span class="sxs-lookup"><span data-stu-id="0df40-337">This is not a required parameter.</span></span> <span data-ttu-id="0df40-338">Se nenhum parâmetro **username** for especificado, o nome de usuário do logon atual será usado para a conexão.</span><span class="sxs-lookup"><span data-stu-id="0df40-338">If no **UserName** parameter is specified then the current log on user name is used for the connection.</span></span>

<span data-ttu-id="0df40-339">Esse parâmetro foi introduzido no PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="0df40-339">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0df40-340">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="0df40-340">-UseSSL</span></span>

<span data-ttu-id="0df40-341">Indica que esse cmdlet usa o protocolo protocolo SSL (SSL) para estabelecer uma conexão com o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="0df40-341">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to establish a connection to the remote computer.</span></span> <span data-ttu-id="0df40-342">Por padrão, SSL não é usado.</span><span class="sxs-lookup"><span data-stu-id="0df40-342">By default, SSL is not used.</span></span>

<span data-ttu-id="0df40-343">WS-Management criptografa todo o conteúdo do PowerShell transmitido pela rede.</span><span class="sxs-lookup"><span data-stu-id="0df40-343">WS-Management encrypts all PowerShell content transmitted over the network.</span></span> <span data-ttu-id="0df40-344">O parâmetro **UseSSL** é uma proteção adicional que envia os dados por uma conexão HTTPS em vez de uma conexão http.</span><span class="sxs-lookup"><span data-stu-id="0df40-344">The **UseSSL** parameter is an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="0df40-345">Se você usar esse parâmetro, mas o SSL não estiver disponível na porta usada para o comando, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="0df40-345">If you use this parameter, but SSL is not available on the port that is used for the command, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0df40-346">-VMId</span><span class="sxs-lookup"><span data-stu-id="0df40-346">-VMId</span></span>

<span data-ttu-id="0df40-347">Especifica a ID de uma máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="0df40-347">Specifies the ID of a virtual machine.</span></span>

```yaml
Type: System.Guid
Parameter Sets: VMId
Aliases: VMGuid

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0df40-348">-VMName</span><span class="sxs-lookup"><span data-stu-id="0df40-348">-VMName</span></span>

<span data-ttu-id="0df40-349">Especifica o nome de uma máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="0df40-349">Specifies the name of a virtual machine.</span></span>

```yaml
Type: System.String
Parameter Sets: VMName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0df40-350">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0df40-350">CommonParameters</span></span>

<span data-ttu-id="0df40-351">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0df40-351">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0df40-352">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0df40-352">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0df40-353">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="0df40-353">INPUTS</span></span>

### <span data-ttu-id="0df40-354">System. String, System. Management. Automation. Runspaces. PSSession</span><span class="sxs-lookup"><span data-stu-id="0df40-354">System.String, System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="0df40-355">É possível canalizar um nome de computador, como uma cadeia de caracteres ou um objeto de sessão para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0df40-355">You can pipe a computer name, as a string, or a session object to this cmdlet.</span></span>

## <span data-ttu-id="0df40-356">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="0df40-356">OUTPUTS</span></span>

### <span data-ttu-id="0df40-357">Nenhum</span><span class="sxs-lookup"><span data-stu-id="0df40-357">None</span></span>

<span data-ttu-id="0df40-358">O cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="0df40-358">The cmdlet does not return any output.</span></span>

## <span data-ttu-id="0df40-359">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="0df40-359">NOTES</span></span>

<span data-ttu-id="0df40-360">Para se conectar a um computador remoto, você deve ser um membro do grupo Administradores no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="0df40-360">To connect to a remote computer, you must be a member of the Administrators group on the remote computer.</span></span> <span data-ttu-id="0df40-361">Para iniciar uma sessão interativa no computador local, você deve iniciar o PowerShell com a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="0df40-361">To start an interactive session on the local computer, you must start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="0df40-362">Quando você usa o `Enter-PSSession` , seu perfil de usuário no computador remoto é usado para a sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="0df40-362">When you use `Enter-PSSession`, your user profile on the remote computer is used for the interactive session.</span></span> <span data-ttu-id="0df40-363">Os comandos no perfil de usuário remoto, incluindo comandos para adicionar módulos do PowerShell e para alterar o prompt de comando, são executados antes que o prompt remoto seja exibido.</span><span class="sxs-lookup"><span data-stu-id="0df40-363">The commands in the remote user profile, including commands to add PowerShell modules and to change the command prompt, run before the remote prompt is displayed.</span></span>

<span data-ttu-id="0df40-364">`Enter-PSSession` usa a configuração de cultura da interface do usuário no computador local para a sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="0df40-364">`Enter-PSSession` uses the UI culture setting on the local computer for the interactive session.</span></span> <span data-ttu-id="0df40-365">Para localizar a cultura da interface do usuário local, use a `$UICulture` variável automática.</span><span class="sxs-lookup"><span data-stu-id="0df40-365">To find the local UI culture, use the `$UICulture` automatic variable.</span></span>

<span data-ttu-id="0df40-366">`Enter-PSSession` requer os `Get-Command` `Out-Default` `Exit-PSSession` cmdlets, e.</span><span class="sxs-lookup"><span data-stu-id="0df40-366">`Enter-PSSession` requires the `Get-Command`, `Out-Default`, and `Exit-PSSession` cmdlets.</span></span> <span data-ttu-id="0df40-367">Se esses cmdlets não estiverem incluídos na configuração de sessão no computador remoto, os `Enter-PSSession` comandos falharão.</span><span class="sxs-lookup"><span data-stu-id="0df40-367">If these cmdlets are not included in the session configuration on the remote computer, the `Enter-PSSession` commands fails.</span></span>

<span data-ttu-id="0df40-368">Ao contrário de `Invoke-Command` , que analisa e interpreta os comandos antes de enviá-los para o computador remoto, `Enter-PSSession` o envia os comandos diretamente para o computador remoto sem interpretação.</span><span class="sxs-lookup"><span data-stu-id="0df40-368">Unlike `Invoke-Command`, which parses and interprets the commands before it sends them to the remote computer, `Enter-PSSession` sends the commands directly to the remote computer without interpretation.</span></span>

<span data-ttu-id="0df40-369">Se a sessão que você deseja inserir estiver ocupada processando um comando, pode haver um atraso antes que o PowerShell responda ao `Enter-PSSession` comando.</span><span class="sxs-lookup"><span data-stu-id="0df40-369">If the session you want to enter is busy processing a command, there might be a delay before PowerShell responds to the `Enter-PSSession` command.</span></span> <span data-ttu-id="0df40-370">Você está conectado assim que a sessão está disponível.</span><span class="sxs-lookup"><span data-stu-id="0df40-370">You are connected as soon as the session is available.</span></span> <span data-ttu-id="0df40-371">Para cancelar o `Enter-PSSession` comando, pressione <kbd>Ctrl</kbd> + <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="0df40-371">To cancel the `Enter-PSSession` command, press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span>

<span data-ttu-id="0df40-372">O parâmetro **hostname** definido foi incluído a partir do PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="0df40-372">The **HostName** parameter set was included starting with PowerShell 6.0.</span></span> <span data-ttu-id="0df40-373">Ele foi adicionado para fornecer comunicação remota do PowerShell com base em Secure Shell (SSH).</span><span class="sxs-lookup"><span data-stu-id="0df40-373">It was added to provide PowerShell remoting based on Secure Shell (SSH).</span></span> <span data-ttu-id="0df40-374">Tanto o SSH quanto o PowerShell têm suporte em várias plataformas (Windows, Linux, macOS) e a comunicação remota do PowerShell funcionará nessas plataformas nas quais o PowerShell e o SSH estão instalados e configurados.</span><span class="sxs-lookup"><span data-stu-id="0df40-374">Both SSH and PowerShell are supported on multiple platforms (Windows, Linux, macOS) and PowerShell remoting will work over these platforms where PowerShell and SSH are installed and configured.</span></span> <span data-ttu-id="0df40-375">Isso é separado da somente comunicação remota do Windows anterior, que é baseada no WinRM, e que muitos dos recursos e limitações específicos do WinRM não se aplicam.</span><span class="sxs-lookup"><span data-stu-id="0df40-375">This is separate from the previous Windows only remoting that is based on WinRM and much of the WinRM specific features and limitations do not apply.</span></span> <span data-ttu-id="0df40-376">Por exemplo, cotas baseadas em WinRM, opções de sessão, configuração de ponto de extremidade personalizado e recursos de desconexão/reconexão não têm suporte no momento.</span><span class="sxs-lookup"><span data-stu-id="0df40-376">For example, WinRM based quotas, session options, custom endpoint configuration, and disconnect/reconnect features are currently not supported.</span></span> <span data-ttu-id="0df40-377">Para obter mais informações sobre como configurar a comunicação remota do PowerShell SSH, consulte [comunicação remota do PowerShell por SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span><span class="sxs-lookup"><span data-stu-id="0df40-377">For more information about how to set up PowerShell SSH remoting, see [PowerShell Remoting Over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

<span data-ttu-id="0df40-378">Antes do PowerShell 7.1, a comunicação remota por SSH não dava suporte a sessões remotas de segundo salto.</span><span class="sxs-lookup"><span data-stu-id="0df40-378">Prior to PowerShell 7.1, remoting over SSH did not support second-hop remote sessions.</span></span> <span data-ttu-id="0df40-379">Essa funcionalidade estava limitada a sessões que usavam o WinRM.</span><span class="sxs-lookup"><span data-stu-id="0df40-379">This capability was limited to sessions using WinRM.</span></span> <span data-ttu-id="0df40-380">O PowerShell 7.1 permite que `Enter-PSSession` e `Enter-PSHostProcess` funcionem em qualquer sessão remota interativa.</span><span class="sxs-lookup"><span data-stu-id="0df40-380">PowerShell 7.1 allows `Enter-PSSession` and `Enter-PSHostProcess` to work from within any interactive remote session.</span></span>

## <span data-ttu-id="0df40-381">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="0df40-381">RELATED LINKS</span></span>

[<span data-ttu-id="0df40-382">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="0df40-382">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="0df40-383">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="0df40-383">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="0df40-384">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="0df40-384">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="0df40-385">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="0df40-385">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="0df40-386">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="0df40-386">Remove-PSSession</span></span>](Remove-PSSession.md)

[<span data-ttu-id="0df40-387">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="0df40-387">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="0df40-388">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="0df40-388">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="0df40-389">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="0df40-389">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="0df40-390">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="0df40-390">about_PSSessions</span></span>](About/about_PSSessions.md)

[<span data-ttu-id="0df40-391">about_Remote</span><span class="sxs-lookup"><span data-stu-id="0df40-391">about_Remote</span></span>](About/about_Remote.md)
