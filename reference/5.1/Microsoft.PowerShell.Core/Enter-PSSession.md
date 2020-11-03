---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pssession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enter-PSSession
ms.openlocfilehash: 40d9da7d2e7e3233608b893b026c2b89c7155ab1
ms.sourcegitcommit: 9dddf1d2e91ebcd347fcfb7bf6ef670d49a12ab7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2020
ms.locfileid: "93195068"
---
# <span data-ttu-id="97497-103">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="97497-103">Enter-PSSession</span></span>

## <span data-ttu-id="97497-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="97497-104">SYNOPSIS</span></span>
<span data-ttu-id="97497-105">Inicia uma sessão interativa com um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="97497-105">Starts an interactive session with a remote computer.</span></span>

## <span data-ttu-id="97497-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="97497-106">SYNTAX</span></span>

### <span data-ttu-id="97497-107">ComputerName (padrão)</span><span class="sxs-lookup"><span data-stu-id="97497-107">ComputerName (Default)</span></span>

```
Enter-PSSession [-ComputerName] <String> [-EnableNetworkAccess] [-Credential <PSCredential>]
 [-ConfigurationName <String>] [-Port <Int32>] [-UseSSL] [-ApplicationName <String>]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="97497-108">Session</span><span class="sxs-lookup"><span data-stu-id="97497-108">Session</span></span>

```
Enter-PSSession [[-Session] <PSSession>] [<CommonParameters>]
```

### <span data-ttu-id="97497-109">Uri</span><span class="sxs-lookup"><span data-stu-id="97497-109">Uri</span></span>

```
Enter-PSSession [[-ConnectionUri] <Uri>] [-EnableNetworkAccess] [-Credential <PSCredential>]
 [-ConfigurationName <String>] [-AllowRedirection] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="97497-110">InstanceId</span><span class="sxs-lookup"><span data-stu-id="97497-110">InstanceId</span></span>

```
Enter-PSSession [-InstanceId <Guid>] [<CommonParameters>]
```

### <span data-ttu-id="97497-111">ID</span><span class="sxs-lookup"><span data-stu-id="97497-111">Id</span></span>

```
Enter-PSSession [[-Id] <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="97497-112">Nome</span><span class="sxs-lookup"><span data-stu-id="97497-112">Name</span></span>

```
Enter-PSSession [-Name <String>] [<CommonParameters>]
```

### <span data-ttu-id="97497-113">VMId</span><span class="sxs-lookup"><span data-stu-id="97497-113">VMId</span></span>

```
Enter-PSSession [-VMId] <Guid> -Credential <PSCredential> [-ConfigurationName <String>] [<CommonParameters>]
```

### <span data-ttu-id="97497-114">VMName</span><span class="sxs-lookup"><span data-stu-id="97497-114">VMName</span></span>

```
Enter-PSSession [-VMName] <String> -Credential <PSCredential> [-ConfigurationName <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="97497-115">ContainerId</span><span class="sxs-lookup"><span data-stu-id="97497-115">ContainerId</span></span>

```
Enter-PSSession [-ContainerId] <String> [-ConfigurationName <String>] [-RunAsAdministrator]
 [<CommonParameters>]
```

## <span data-ttu-id="97497-116">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="97497-116">DESCRIPTION</span></span>

<span data-ttu-id="97497-117">O `Enter-PSSession` cmdlet inicia uma sessão interativa com um único computador remoto.</span><span class="sxs-lookup"><span data-stu-id="97497-117">The `Enter-PSSession` cmdlet starts an interactive session with a single remote computer.</span></span> <span data-ttu-id="97497-118">Durante a sessão, os comandos digitados são executados no computador remoto, assim como se você estivesse digitando diretamente no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="97497-118">During the session, the commands that you type run on the remote computer, just as if you were typing directly on the remote computer.</span></span> <span data-ttu-id="97497-119">Você pode ter somente uma sessão interativa por vez.</span><span class="sxs-lookup"><span data-stu-id="97497-119">You can have only one interactive session at a time.</span></span>

<span data-ttu-id="97497-120">Normalmente, você usa o parâmetro **ComputerName** para especificar o nome do computador remoto.</span><span class="sxs-lookup"><span data-stu-id="97497-120">Typically, you use the **ComputerName** parameter to specify the name of the remote computer.</span></span>
<span data-ttu-id="97497-121">No entanto, você também pode usar uma sessão que você cria usando o `New-PSSession` cmdlet para a sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="97497-121">However, you can also use a session that you create by using the `New-PSSession` cmdlet for the interactive session.</span></span> <span data-ttu-id="97497-122">No entanto, você não pode usar os `Disconnect-PSSession` `Connect-PSSession` `Receive-PSSession` cmdlets, ou para se desconectar ou se conectar novamente a uma sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="97497-122">However, you cannot use the `Disconnect-PSSession`, `Connect-PSSession`, or `Receive-PSSession` cmdlets to disconnect from or re-connect to an interactive session.</span></span>

<span data-ttu-id="97497-123">Para encerrar a sessão interativa e desconectar-se do computador remoto, use o `Exit-PSSession` cmdlet ou digite `exit` .</span><span class="sxs-lookup"><span data-stu-id="97497-123">To end the interactive session and disconnect from the remote computer, use the `Exit-PSSession` cmdlet, or type `exit`.</span></span>

## <span data-ttu-id="97497-124">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="97497-124">EXAMPLES</span></span>

### <span data-ttu-id="97497-125">Exemplo 1: iniciar uma sessão interativa</span><span class="sxs-lookup"><span data-stu-id="97497-125">Example 1: Start an interactive session</span></span>

```
PS C:\> Enter-PSSession
[localhost]: PS C:\>
```

<span data-ttu-id="97497-126">Esse comando inicia uma sessão interativa no computador local.</span><span class="sxs-lookup"><span data-stu-id="97497-126">This command starts an interactive session on the local computer.</span></span> <span data-ttu-id="97497-127">O prompt de comando é alterado para indicar que você está executando comandos em uma sessão diferente.</span><span class="sxs-lookup"><span data-stu-id="97497-127">The command prompt changes to indicate that you are now running commands in a different session.</span></span>

<span data-ttu-id="97497-128">Os comandos que você inseriu são executados na nova sessão e os resultados são retornados à sessão padrão como texto.</span><span class="sxs-lookup"><span data-stu-id="97497-128">The commands that you enter run in the new session, and the results are returned to the default session as text.</span></span>

### <span data-ttu-id="97497-129">Exemplo 2: trabalhar com uma sessão interativa</span><span class="sxs-lookup"><span data-stu-id="97497-129">Example 2: Work with an interactive session</span></span>

<span data-ttu-id="97497-130">O primeiro comando usa o `Enter-PSSession` cmdlet para iniciar uma sessão interativa com Server01, um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="97497-130">The first command uses the `Enter-PSSession` cmdlet to start an interactive session with Server01, a remote computer.</span></span> <span data-ttu-id="97497-131">Quando a sessão é iniciada, o prompt de comando é alterado para incluir o nome do computador.</span><span class="sxs-lookup"><span data-stu-id="97497-131">When the session starts, the command prompt changes to include the computer name.</span></span>
<span data-ttu-id="97497-132">O segundo comando obtém o processo do Windows PowerShell e redireciona a saída para o arquivo de Process.txt.</span><span class="sxs-lookup"><span data-stu-id="97497-132">The second command gets the Windows PowerShell process and redirects the output to the Process.txt file.</span></span> <span data-ttu-id="97497-133">O comando é enviado ao computador remoto e o arquivo é salvo no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="97497-133">The command is submitted to the remote computer, and the file is saved on the remote computer.</span></span>
<span data-ttu-id="97497-134">O terceiro comando usa a palavra-chave **Exit** para encerrar a sessão interativa e fechar a conexão.</span><span class="sxs-lookup"><span data-stu-id="97497-134">The third command uses the **Exit** keyword to end the interactive session and close the connection.</span></span>
<span data-ttu-id="97497-135">O quarto comando confirma que o arquivo Process.txt está no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="97497-135">The fourth command confirms that the Process.txt file is on the remote computer.</span></span> <span data-ttu-id="97497-136">Um `Get-ChildItem` comando ("dir") no computador local não pode localizar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="97497-136">A `Get-ChildItem` ("dir") command on the local computer cannot find the file.</span></span>

```powershell
PS C:\> Enter-PSSession -ComputerName Server01
[Server01]: PS C:\>
[Server01]: PS C:\> Get-Process PowerShell > C:\ps-test\Process.txt
[Server01]: PS C:\> exit
PS C:\>
PS C:\> dir C:\ps-test\process.txt
Get-ChildItem : Cannot find path 'C:\ps-test\process.txt' because it does not exist.
At line:1 char:4
+ dir <<<<  c:\ps-test\process.txt
```

<span data-ttu-id="97497-137">Este comando mostra como trabalhar em uma sessão interativa com um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="97497-137">This command shows how to work in an interactive session with a remote computer.</span></span>

### <span data-ttu-id="97497-138">Exemplo 3: usar o parâmetro Session</span><span class="sxs-lookup"><span data-stu-id="97497-138">Example 3: Use the Session parameter</span></span>

```powershell
PS C:\> $s = New-PSSession -ComputerName Server01
PS C:\> Enter-PSSession -Session $s
[Server01]: PS C:\>
```

<span data-ttu-id="97497-139">Esses comandos usam o parâmetro **Session** do `Enter-PSSession` para executar a sessão interativa em uma sessão existente do Windows PowerShell ( **PSSession** ).</span><span class="sxs-lookup"><span data-stu-id="97497-139">These commands use the **Session** parameter of `Enter-PSSession` to run the interactive session in an existing Windows PowerShell session ( **PSSession** ).</span></span>

### <span data-ttu-id="97497-140">Exemplo 4: iniciar uma sessão interativa e especificar os parâmetros de porta e de credencial</span><span class="sxs-lookup"><span data-stu-id="97497-140">Example 4: Start an interactive session and specify the Port and Credential parameters</span></span>

```powershell
PS C:\> Enter-PSSession -ComputerName Server01 -Port 90 -Credential Domain01\User01
[Server01]: PS C:\>
```

<span data-ttu-id="97497-141">Esse comando inicia uma sessão interativa com o computador Server01.</span><span class="sxs-lookup"><span data-stu-id="97497-141">This command starts an interactive session with the Server01 computer.</span></span> <span data-ttu-id="97497-142">Ele usa o parâmetro **Port** para especificar a porta e o parâmetro **Credential** para especificar a conta de um usuário que tem permissão para se conectar ao computador remoto.</span><span class="sxs-lookup"><span data-stu-id="97497-142">It uses the **Port** parameter to specify the port and the **Credential** parameter to specify the account of a user who has permission to connect to the remote computer.</span></span>

### <span data-ttu-id="97497-143">Exemplo 5: parar uma sessão interativa</span><span class="sxs-lookup"><span data-stu-id="97497-143">Example 5: Stop an interactive session</span></span>

```powershell
PS C:\> Enter-PSSession -ComputerName Server01
[Server01]: PS C:\> Exit-PSSession
PS C:\>
```

<span data-ttu-id="97497-144">Este exemplo mostra como iniciar e interromper uma sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="97497-144">This example shows how to start and stop an interactive session.</span></span> <span data-ttu-id="97497-145">O primeiro comando usa o `Enter-PSSession` cmdlet para iniciar uma sessão interativa com o computador Server01.</span><span class="sxs-lookup"><span data-stu-id="97497-145">The first command uses the `Enter-PSSession` cmdlet to start an interactive session with the Server01 computer.</span></span>

<span data-ttu-id="97497-146">O segundo comando usa o `Exit-PSSession` cmdlet para encerrar a sessão.</span><span class="sxs-lookup"><span data-stu-id="97497-146">The second command uses the `Exit-PSSession` cmdlet to end the session.</span></span> <span data-ttu-id="97497-147">Você também pode usar a palavra-chave **Exit** para encerrar a sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="97497-147">You can also use the **Exit** keyword to end the interactive session.</span></span> <span data-ttu-id="97497-148">`Exit-PSSession` e **Exit** têm o mesmo efeito.</span><span class="sxs-lookup"><span data-stu-id="97497-148">`Exit-PSSession` and **Exit** have the same effect.</span></span>

## <span data-ttu-id="97497-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="97497-149">PARAMETERS</span></span>

### <span data-ttu-id="97497-150">-AllowRedirection</span><span class="sxs-lookup"><span data-stu-id="97497-150">-AllowRedirection</span></span>

<span data-ttu-id="97497-151">Permite o redirecionamento da conexão para um URI (Uniform Resource Identifier) alternativo.</span><span class="sxs-lookup"><span data-stu-id="97497-151">Allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="97497-152">Por padrão, o redirecionamento não é permitido.</span><span class="sxs-lookup"><span data-stu-id="97497-152">By default, redirection is not allowed.</span></span>

<span data-ttu-id="97497-153">Quando você usa o parâmetro **ConnectionURI** , o destino remoto pode retornar uma instrução para redirecionar para um URI diferente.</span><span class="sxs-lookup"><span data-stu-id="97497-153">When you use the **ConnectionURI** parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="97497-154">Por padrão, o Windows PowerShell não redireciona conexões, mas você pode usar esse parâmetro para permitir que ele redirecione a conexão.</span><span class="sxs-lookup"><span data-stu-id="97497-154">By default, Windows PowerShell does not redirect connections, but you can use this parameter to allow it to redirect the connection.</span></span>

<span data-ttu-id="97497-155">É possível também limitar o número de vezes que a conexão é redirecionada alterando o valor da opção de sessão **MaximumConnectionRedirectionCount** .</span><span class="sxs-lookup"><span data-stu-id="97497-155">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span> <span data-ttu-id="97497-156">Use o parâmetro **MaximumRedirection** do `New-PSSessionOption` cmdlet ou defina a propriedade **MaximumConnectionRedirectionCount** da variável de `$PSSessionOption` preferência.</span><span class="sxs-lookup"><span data-stu-id="97497-156">Use the **MaximumRedirection** parameter of the `New-PSSessionOption` cmdlet or set the **MaximumConnectionRedirectionCount** property of the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="97497-157">O valor padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="97497-157">The default value is 5.</span></span>

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

### <span data-ttu-id="97497-158">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="97497-158">-ApplicationName</span></span>

<span data-ttu-id="97497-159">Especifica o segmento de nome de aplicativo do URI de conexão.</span><span class="sxs-lookup"><span data-stu-id="97497-159">Specifies the application name segment of the connection URI.</span></span> <span data-ttu-id="97497-160">Use esse parâmetro para especificar o nome do aplicativo quando não estiver usando o parâmetro **ConnectionURI** no comando.</span><span class="sxs-lookup"><span data-stu-id="97497-160">Use this parameter to specify the application name when you are not using the **ConnectionURI** parameter in the command.</span></span>

<span data-ttu-id="97497-161">O valor padrão é o valor da `$PSSessionApplicationName` variável de preferência no computador local.</span><span class="sxs-lookup"><span data-stu-id="97497-161">The default value is the value of the `$PSSessionApplicationName` preference variable on the local computer.</span></span> <span data-ttu-id="97497-162">Se esta variável de preferência não estiver definida, o valor padrão é WSMAN.</span><span class="sxs-lookup"><span data-stu-id="97497-162">If this preference variable is not defined, the default value is WSMAN.</span></span> <span data-ttu-id="97497-163">Esse valor é adequado para a maioria dos usos.</span><span class="sxs-lookup"><span data-stu-id="97497-163">This value is appropriate for most uses.</span></span> <span data-ttu-id="97497-164">Para obter mais informações, consulte [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="97497-164">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="97497-165">O serviço **WinRM** usa o nome do aplicativo para selecionar um ouvinte para atender à solicitação de conexão.</span><span class="sxs-lookup"><span data-stu-id="97497-165">The **WinRM** service uses the application name to select a listener to service the connection request.</span></span> <span data-ttu-id="97497-166">O valor desse parâmetro deve corresponder ao valor da propriedade **URLPrefix** de um ouvinte no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="97497-166">The value of this parameter should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

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

### <span data-ttu-id="97497-167">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="97497-167">-Authentication</span></span>

<span data-ttu-id="97497-168">Especifica o mecanismo usado para autenticar as credenciais do usuário.</span><span class="sxs-lookup"><span data-stu-id="97497-168">Specifies the mechanism that is used to authenticate the user's credentials.</span></span> <span data-ttu-id="97497-169">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="97497-169">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="97497-170">Padrão</span><span class="sxs-lookup"><span data-stu-id="97497-170">Default</span></span>
- <span data-ttu-id="97497-171">Básico</span><span class="sxs-lookup"><span data-stu-id="97497-171">Basic</span></span>
- <span data-ttu-id="97497-172">CredSSP</span><span class="sxs-lookup"><span data-stu-id="97497-172">Credssp</span></span>
- <span data-ttu-id="97497-173">Digest</span><span class="sxs-lookup"><span data-stu-id="97497-173">Digest</span></span>
- <span data-ttu-id="97497-174">Kerberos</span><span class="sxs-lookup"><span data-stu-id="97497-174">Kerberos</span></span>
- <span data-ttu-id="97497-175">Negotiate</span><span class="sxs-lookup"><span data-stu-id="97497-175">Negotiate</span></span>
- <span data-ttu-id="97497-176">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="97497-176">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="97497-177">O valor padrão é Default.</span><span class="sxs-lookup"><span data-stu-id="97497-177">The default value is Default.</span></span>

<span data-ttu-id="97497-178">A autenticação CredSSP está disponível somente no Windows Vista, no Windows Server 2008 e em versões posteriores do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="97497-178">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="97497-179">Para obter mais informações sobre os valores desse parâmetro, consulte [AuthenticationMechanism enum](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="97497-179">For more information about the values of this parameter, see [AuthenticationMechanism Enum](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

<span data-ttu-id="97497-180">Cuidado: a autenticação do Credential Security Support Provider (CredSSP), na qual as credenciais do usuário são passadas para um computador remoto a ser autenticado, foi projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remoto.</span><span class="sxs-lookup"><span data-stu-id="97497-180">Caution: Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="97497-181">Esse mecanismo aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="97497-181">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="97497-182">Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="97497-182">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

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

### <span data-ttu-id="97497-183">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="97497-183">-CertificateThumbprint</span></span>

<span data-ttu-id="97497-184">Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa ação.</span><span class="sxs-lookup"><span data-stu-id="97497-184">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="97497-185">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="97497-185">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="97497-186">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="97497-186">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="97497-187">Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="97497-187">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="97497-188">Para obter um certificado, use o `Get-Item` `Get-ChildItem` comando ou na unidade CERT: do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="97497-188">To get a certificate, use the `Get-Item` or `Get-ChildItem` command in the Windows PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="97497-189">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="97497-189">-ComputerName</span></span>

<span data-ttu-id="97497-190">Especifica um nome de computador.</span><span class="sxs-lookup"><span data-stu-id="97497-190">Specifies a computer name.</span></span> <span data-ttu-id="97497-191">Esse cmdlet inicia uma sessão interativa com o computador remoto especificado.</span><span class="sxs-lookup"><span data-stu-id="97497-191">This cmdlet starts an interactive session with the specified remote computer.</span></span> <span data-ttu-id="97497-192">Digite apenas um nome de computador.</span><span class="sxs-lookup"><span data-stu-id="97497-192">Enter only one computer name.</span></span> <span data-ttu-id="97497-193">O padrão é o computador local.</span><span class="sxs-lookup"><span data-stu-id="97497-193">The default is the local computer.</span></span>

<span data-ttu-id="97497-194">Digite o nome NetBIOS, o endereço IP ou o nome de domínio totalmente qualificado do computador.</span><span class="sxs-lookup"><span data-stu-id="97497-194">Type the NetBIOS name, the IP address, or the fully qualified domain name of the computer.</span></span> <span data-ttu-id="97497-195">Você também pode canalizar um nome de computador para `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="97497-195">You can also pipe a computer name to `Enter-PSSession`.</span></span>

<span data-ttu-id="97497-196">Para usar um endereço IP no valor do parâmetro **ComputerName** , o comando deve incluir o parâmetro **Credential** .</span><span class="sxs-lookup"><span data-stu-id="97497-196">To use an IP address in the value of the **ComputerName** parameter, the command must include the **Credential** parameter.</span></span> <span data-ttu-id="97497-197">Além disso, o computador deve ser configurado para o transporte HTTPS ou o endereço IP do computador remoto deve ser incluído na lista WinRM TrustedHosts no computador local.</span><span class="sxs-lookup"><span data-stu-id="97497-197">Also, the computer must be configured for HTTPS transport or the IP address of the remote computer must be included in the WinRM TrustedHosts list on the local computer.</span></span> <span data-ttu-id="97497-198">Para obter instruções sobre como adicionar um nome de computador à lista TrustedHosts, consulte "como adicionar um computador à lista de hosts confiáveis" em [about_Remote_Troubleshooting](About/about_Remote_Troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="97497-198">For instructions for adding a computer name to the TrustedHosts list, see "How to Add a Computer to the Trusted Host List" in [about_Remote_Troubleshooting](About/about_Remote_Troubleshooting.md).</span></span>

<span data-ttu-id="97497-199">Observação: no Windows Vista e versões posteriores do sistema operacional Windows, para incluir o computador local no valor do parâmetro **ComputerName** , você deve iniciar o Windows PowerShell com a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="97497-199">Note: In Windows Vista and later versions of the Windows operating system, to include the local computer in the value of the **ComputerName** parameter, you must start Windows PowerShell with the Run as administrator option.</span></span>

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

### <span data-ttu-id="97497-200">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="97497-200">-ConfigurationName</span></span>

<span data-ttu-id="97497-201">Especifica a configuração de sessão usada para a sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="97497-201">Specifies the session configuration that is used for the interactive session.</span></span>

<span data-ttu-id="97497-202">Insira um nome de configuração ou o URI do recurso totalmente qualificado para uma configuração de sessão.</span><span class="sxs-lookup"><span data-stu-id="97497-202">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="97497-203">Se você especificar apenas o nome da configuração, o seguinte URI de esquema será anexado: `http://schemas.microsoft.com/powershell` .</span><span class="sxs-lookup"><span data-stu-id="97497-203">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/powershell`.</span></span>

<span data-ttu-id="97497-204">A configuração da sessão para uma sessão está localizada no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="97497-204">The session configuration for a session is located on the remote computer.</span></span> <span data-ttu-id="97497-205">Se a configuração de sessão especificada não existir no computador remoto, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="97497-205">If the specified session configuration does not exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="97497-206">O valor padrão é o valor da `$PSSessionConfigurationName` variável de preferência no computador local.</span><span class="sxs-lookup"><span data-stu-id="97497-206">The default value is the value of the `$PSSessionConfigurationName` preference variable on the local computer.</span></span> <span data-ttu-id="97497-207">Se esta variável de preferência não for definida, o padrão é Microsoft.</span><span class="sxs-lookup"><span data-stu-id="97497-207">If this preference variable is not set, the default is Microsoft.PowerShell.</span></span> <span data-ttu-id="97497-208">Para obter mais informações, consulte [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="97497-208">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

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

### <span data-ttu-id="97497-209">-Conexãouri</span><span class="sxs-lookup"><span data-stu-id="97497-209">-ConnectionUri</span></span>

<span data-ttu-id="97497-210">Especifica um URI que define o ponto de extremidade de conexão para a sessão.</span><span class="sxs-lookup"><span data-stu-id="97497-210">Specifies a URI that defines the connection endpoint for the session.</span></span> <span data-ttu-id="97497-211">O URI deve ser totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="97497-211">The URI must be fully qualified.</span></span> <span data-ttu-id="97497-212">O formato dessa cadeia de caracteres é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="97497-212">The format of this string is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="97497-213">O valor padrão é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="97497-213">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="97497-214">Se não especificar um **ConnectionURI** , poderá usar os parâmetros **UseSSL** , **ComputerName** , **Port** e **ApplicationName** para especificar os valores do **ConnectionURI** .</span><span class="sxs-lookup"><span data-stu-id="97497-214">If you do not specify a **ConnectionURI** , you can use the **UseSSL** , **ComputerName** , **Port** , and **ApplicationName** parameters to specify the **ConnectionURI** values.</span></span>

<span data-ttu-id="97497-215">Os valores válidos para o segmento Transport do URI são HTTP e HTTPS.</span><span class="sxs-lookup"><span data-stu-id="97497-215">Valid values for the Transport segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="97497-216">Se você especificar um URI de conexão com um segmento de transporte, mas não especificar uma porta, a sessão será criada usando portas de padrões: 80 para HTTP e 443 para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="97497-216">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created by using standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="97497-217">Para utilizar as portas padrão para comunicação remota do Windows PowerShell, especifique a porta 5985 para HTTP ou 5986 para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="97497-217">To use the default ports for Windows PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="97497-218">Se o computador de destino redirecionar a conexão para um URI diferente, o Windows PowerShell impedirá o redirecionamento, a menos que você use o parâmetro **AllowRedirection** no comando.</span><span class="sxs-lookup"><span data-stu-id="97497-218">If the destination computer redirects the connection to a different URI, Windows PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

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

### <span data-ttu-id="97497-219">-ContainerId</span><span class="sxs-lookup"><span data-stu-id="97497-219">-ContainerId</span></span>

<span data-ttu-id="97497-220">Especifica a ID de um contêiner.</span><span class="sxs-lookup"><span data-stu-id="97497-220">Specifies the ID of a container.</span></span>

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

### <span data-ttu-id="97497-221">-Credential</span><span class="sxs-lookup"><span data-stu-id="97497-221">-Credential</span></span>

<span data-ttu-id="97497-222">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="97497-222">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="97497-223">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="97497-223">The default is the current user.</span></span>

<span data-ttu-id="97497-224">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="97497-224">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="97497-225">Se você digitar um nome de usuário, você será solicitado a inserir a senha.</span><span class="sxs-lookup"><span data-stu-id="97497-225">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="97497-226">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="97497-226">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="97497-227">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="97497-227">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="97497-228">-EnableNetworkAccess</span><span class="sxs-lookup"><span data-stu-id="97497-228">-EnableNetworkAccess</span></span>

<span data-ttu-id="97497-229">Indica que esse cmdlet adiciona um token de segurança interativo a sessões de loopback.</span><span class="sxs-lookup"><span data-stu-id="97497-229">Indicates that this cmdlet adds an interactive security token to loopback sessions.</span></span> <span data-ttu-id="97497-230">O token interativo permite executar comandos na sessão de loopback que obtêm dados de outros computadores.</span><span class="sxs-lookup"><span data-stu-id="97497-230">The interactive token lets you run commands in the loopback session that get data from other computers.</span></span> <span data-ttu-id="97497-231">Por exemplo, você pode executar um comando na sessão que copia arquivos XML de um computador remoto no computador local.</span><span class="sxs-lookup"><span data-stu-id="97497-231">For example, you can run a command in the session that copies XML files from a remote computer to the local computer.</span></span>

<span data-ttu-id="97497-232">Uma sessão de loopback é uma **PSSession** originada e termina no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="97497-232">A loopback session is a **PSSession** that originates and ends on the same computer.</span></span> <span data-ttu-id="97497-233">Para criar uma sessão de loopback, omita o parâmetro **ComputerName** ou defina seu valor como.</span><span class="sxs-lookup"><span data-stu-id="97497-233">To create a loopback session, omit the **ComputerName** parameter or set its value to .</span></span> <span data-ttu-id="97497-234">(ponto), localhost ou o nome do computador local.</span><span class="sxs-lookup"><span data-stu-id="97497-234">(dot), localhost, or the name of the local computer.</span></span>

<span data-ttu-id="97497-235">Por padrão, as sessões de loopback são criadas usando um token de rede, que pode não fornecer permissão suficiente para autenticar em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="97497-235">By default, loopback sessions are created by using a network token, which might not provide sufficient permission to authenticate to remote computers.</span></span>

<span data-ttu-id="97497-236">O parâmetro **EnableNetworkAccess** só é eficaz em sessões de loopback.</span><span class="sxs-lookup"><span data-stu-id="97497-236">The **EnableNetworkAccess** parameter is effective only in loopback sessions.</span></span> <span data-ttu-id="97497-237">Se você usar **EnableNetworkAccess** ao criar uma sessão em um computador remoto, o comando terá sucesso, mas o parâmetro será ignorado.</span><span class="sxs-lookup"><span data-stu-id="97497-237">If you use **EnableNetworkAccess** when you create a session on a remote computer, the command succeeds, but the parameter is ignored.</span></span>

<span data-ttu-id="97497-238">Também é possível permitir o acesso remoto em uma sessão de loopback usando o valor **CredSSP** do parâmetro **Authentication** , que delega as credenciais de sessão a outros computadores.</span><span class="sxs-lookup"><span data-stu-id="97497-238">You can also allow remote access in a loopback session by using the **CredSSP** value of the **Authentication** parameter, which delegates the session credentials to other computers.</span></span>

<span data-ttu-id="97497-239">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="97497-239">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="97497-240">-Id</span><span class="sxs-lookup"><span data-stu-id="97497-240">-Id</span></span>

<span data-ttu-id="97497-241">Especifica a ID de uma sessão existente.</span><span class="sxs-lookup"><span data-stu-id="97497-241">Specifies the ID of an existing session.</span></span> <span data-ttu-id="97497-242">`Enter-PSSession` usa a sessão especificada para a sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="97497-242">`Enter-PSSession` uses the specified session for the interactive session.</span></span>

<span data-ttu-id="97497-243">Para localizar a ID de uma sessão, use o `Get-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="97497-243">To find the ID of a session, use the `Get-PSSession` cmdlet.</span></span>

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

### <span data-ttu-id="97497-244">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="97497-244">-InstanceId</span></span>

<span data-ttu-id="97497-245">Especifica a ID de instância de uma sessão existente.</span><span class="sxs-lookup"><span data-stu-id="97497-245">Specifies the instance ID of an existing session.</span></span> <span data-ttu-id="97497-246">`Enter-PSSession` usa a sessão especificada para a sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="97497-246">`Enter-PSSession` uses the specified session for the interactive session.</span></span>

<span data-ttu-id="97497-247">A ID de instância é um GUID.</span><span class="sxs-lookup"><span data-stu-id="97497-247">The instance ID is a GUID.</span></span> <span data-ttu-id="97497-248">Para localizar a ID de instância de uma sessão, use o `Get-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="97497-248">To find the instance ID of a session, use the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="97497-249">Você também pode usar os parâmetros de **sessão** , **nome** ou **ID** para especificar uma sessão existente.</span><span class="sxs-lookup"><span data-stu-id="97497-249">You can also use the **Session** , **Name** , or **ID** parameters to specify an existing session.</span></span> <span data-ttu-id="97497-250">Ou, você pode usar o parâmetro **ComputerName** para iniciar uma sessão temporária.</span><span class="sxs-lookup"><span data-stu-id="97497-250">Or, you can use the **ComputerName** parameter to start a temporary session.</span></span>

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

### <span data-ttu-id="97497-251">-Name</span><span class="sxs-lookup"><span data-stu-id="97497-251">-Name</span></span>

<span data-ttu-id="97497-252">Especifica o nome amigável de uma sessão existente.</span><span class="sxs-lookup"><span data-stu-id="97497-252">Specifies the friendly name of an existing session.</span></span> <span data-ttu-id="97497-253">`Enter-PSSession` usa a sessão especificada para a sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="97497-253">`Enter-PSSession` uses the specified session for the interactive session.</span></span>

<span data-ttu-id="97497-254">Se o nome que você especificou corresponder a mais de uma sessão, o comando falha.</span><span class="sxs-lookup"><span data-stu-id="97497-254">If the name that you specify matches more than one session, the command fails.</span></span> <span data-ttu-id="97497-255">Você também pode usar os parâmetros **Session** , **InstanceId** ou **ID** para especificar uma sessão existente.</span><span class="sxs-lookup"><span data-stu-id="97497-255">You can also use the **Session** , **InstanceID** , or **ID** parameters to specify an existing session.</span></span> <span data-ttu-id="97497-256">Ou, você pode usar o parâmetro **ComputerName** para iniciar uma sessão temporária.</span><span class="sxs-lookup"><span data-stu-id="97497-256">Or, you can use the **ComputerName** parameter to start a temporary session.</span></span>

<span data-ttu-id="97497-257">Para estabelecer um nome amigável para uma sessão, use o parâmetro **Name** do `New-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="97497-257">To establish a friendly name for a session, use the **Name** parameter of the `New-PSSession` cmdlet.</span></span>

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

### <span data-ttu-id="97497-258">-Port</span><span class="sxs-lookup"><span data-stu-id="97497-258">-Port</span></span>

<span data-ttu-id="97497-259">Especifica a porta de rede no computador remoto que é usada para este comando.</span><span class="sxs-lookup"><span data-stu-id="97497-259">Specifies the network port on the remote computer that is used for this command.</span></span> <span data-ttu-id="97497-260">Para se conectar a um computador remoto, este deve estar escutando na porta usada pela conexão.</span><span class="sxs-lookup"><span data-stu-id="97497-260">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="97497-261">As portas padrão são 5985, que é a porta do WinRM para HTTP e 5986, que é a porta do WinRM para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="97497-261">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="97497-262">Antes de usar uma porta alternativa, você deve configurar o ouvinte de WinRM no computador remoto para escutar na porta.</span><span class="sxs-lookup"><span data-stu-id="97497-262">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="97497-263">Use os seguintes comandos para configurar o ouvinte:</span><span class="sxs-lookup"><span data-stu-id="97497-263">Use the following commands to configure the listener:</span></span>

1. `winrm delete winrm/config/listener?Address=*+Transport=HTTP`
2. `winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number\>"}`

<span data-ttu-id="97497-264">Não use o parâmetro **Port** a menos que seja necessário.</span><span class="sxs-lookup"><span data-stu-id="97497-264">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="97497-265">A configuração da porta no comando se aplica a todos os computadores ou sessões em que o comando for executado.</span><span class="sxs-lookup"><span data-stu-id="97497-265">The port setting in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="97497-266">Uma configuração de porta alternativa pode impedir que o comando seja executado em todos os computadores.</span><span class="sxs-lookup"><span data-stu-id="97497-266">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97497-267">-RunAsAdministrator</span><span class="sxs-lookup"><span data-stu-id="97497-267">-RunAsAdministrator</span></span>

<span data-ttu-id="97497-268">Indica que a **PSSession** é executada como administrador.</span><span class="sxs-lookup"><span data-stu-id="97497-268">Indicates that the **PSSession** runs as administrator.</span></span>

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

### <span data-ttu-id="97497-269">-Sessão</span><span class="sxs-lookup"><span data-stu-id="97497-269">-Session</span></span>

<span data-ttu-id="97497-270">Especifica uma sessão do Windows PowerShell ( **PSSession** ) a ser usada para a sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="97497-270">Specifies a Windows PowerShell session ( **PSSession** ) to use for the interactive session.</span></span> <span data-ttu-id="97497-271">Esse parâmetro usa um objeto de sessão.</span><span class="sxs-lookup"><span data-stu-id="97497-271">This parameter takes a session object.</span></span> <span data-ttu-id="97497-272">Você também pode usar os parâmetros **Name** , **InstanceId** ou **ID** para especificar uma **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="97497-272">You can also use the **Name** , **InstanceID** , or **ID** parameters to specify a **PSSession** .</span></span>

<span data-ttu-id="97497-273">Insira uma variável que contenha um objeto de sessão ou um comando que cria ou Obtém um objeto de sessão, como um `New-PSSession` `Get-PSSession` comando ou.</span><span class="sxs-lookup"><span data-stu-id="97497-273">Enter a variable that contains a session object or a command that creates or gets a session object, such as a `New-PSSession` or `Get-PSSession` command.</span></span> <span data-ttu-id="97497-274">Também é possível canalizar um objeto de sessão para `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="97497-274">You can also pipe a session object to `Enter-PSSession`.</span></span> <span data-ttu-id="97497-275">Você pode enviar apenas uma **PSSession** usando esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="97497-275">You can submit only one **PSSession** by using this parameter.</span></span> <span data-ttu-id="97497-276">Se você inserir uma variável que contenha mais de uma **PSSession** , o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="97497-276">If you enter a variable that contains more than one **PSSession** , the command fails.</span></span>

<span data-ttu-id="97497-277">Quando você usa `Exit-PSSession` o ou a palavra-chave **Exit** , a sessão interativa termina, mas a **PSSession** que você criou permanece aberta e disponível para uso.</span><span class="sxs-lookup"><span data-stu-id="97497-277">When you use `Exit-PSSession` or the **EXIT** keyword, the interactive session ends, but the **PSSession** that you created remains open and available for use.</span></span>

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

### <span data-ttu-id="97497-278">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="97497-278">-SessionOption</span></span>

<span data-ttu-id="97497-279">Define opções avançadas para a sessão.</span><span class="sxs-lookup"><span data-stu-id="97497-279">Sets advanced options for the session.</span></span> <span data-ttu-id="97497-280">Insira um objeto **SessionOption** , como um que você cria usando o `New-PSSessionOption` cmdlet ou uma tabela de hash na qual as chaves são nomes de opção de sessão e os valores são valores de opção de sessão.</span><span class="sxs-lookup"><span data-stu-id="97497-280">Enter a **SessionOption** object, such as one that you create by using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="97497-281">Os valores padrão para as opções são determinados pelo valor da variável de `$PSSessionOption` preferência, se estiver definido.</span><span class="sxs-lookup"><span data-stu-id="97497-281">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="97497-282">Caso contrário, os valores padrão são estabelecidos por opções definidas na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="97497-282">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="97497-283">Os valores de opção de sessão têm precedência sobre valores padrão para sessões definidas na `$PSSessionOption` variável de preferência e na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="97497-283">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="97497-284">No entanto, eles não têm precedência sobre valores máximos, cotas ou limites definidos na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="97497-284">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span>

<span data-ttu-id="97497-285">Para obter uma descrição das opções de sessão, incluindo os valores padrão, consulte `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="97497-285">For a description of the session options, including the default values, see `New-PSSessionOption`.</span></span>
<span data-ttu-id="97497-286">Para obter informações sobre a `$PSSessionOption` variável de preferência, consulte [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="97497-286">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span> <span data-ttu-id="97497-287">Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="97497-287">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

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

### <span data-ttu-id="97497-288">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="97497-288">-UseSSL</span></span>

<span data-ttu-id="97497-289">Indica que esse cmdlet usa o protocolo protocolo SSL (SSL) para estabelecer uma conexão com o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="97497-289">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to establish a connection to the remote computer.</span></span> <span data-ttu-id="97497-290">Por padrão, SSL não é usado.</span><span class="sxs-lookup"><span data-stu-id="97497-290">By default, SSL is not used.</span></span>

<span data-ttu-id="97497-291">O WS-Management criptografa todo o conteúdo do Windows PowerShell transmitido pela rede.</span><span class="sxs-lookup"><span data-stu-id="97497-291">WS-Management encrypts all Windows PowerShell content transmitted over the network.</span></span> <span data-ttu-id="97497-292">O parâmetro **UseSSL** é uma proteção adicional que envia os dados por uma conexão HTTPS em vez de uma conexão http.</span><span class="sxs-lookup"><span data-stu-id="97497-292">The **UseSSL** parameter is an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="97497-293">Se você usar esse parâmetro, mas o SSL não estiver disponível na porta usada para o comando, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="97497-293">If you use this parameter, but SSL is not available on the port that is used for the command, the command fails.</span></span>

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

### <span data-ttu-id="97497-294">-VMId</span><span class="sxs-lookup"><span data-stu-id="97497-294">-VMId</span></span>

<span data-ttu-id="97497-295">Especifica a ID de uma máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="97497-295">Specifies the ID of a virtual machine.</span></span>

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

### <span data-ttu-id="97497-296">-VMName</span><span class="sxs-lookup"><span data-stu-id="97497-296">-VMName</span></span>

<span data-ttu-id="97497-297">Especifica o nome de uma máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="97497-297">Specifies the name of a virtual machine.</span></span>

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

### <span data-ttu-id="97497-298">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="97497-298">CommonParameters</span></span>

<span data-ttu-id="97497-299">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="97497-299">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="97497-300">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="97497-300">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="97497-301">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="97497-301">INPUTS</span></span>

### <span data-ttu-id="97497-302">System. String, System. Management. Automation. Runspaces. PSSession</span><span class="sxs-lookup"><span data-stu-id="97497-302">System.String, System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="97497-303">É possível canalizar um nome de computador, como uma cadeia de caracteres ou um objeto de sessão para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="97497-303">You can pipe a computer name, as a string, or a session object to this cmdlet.</span></span>

## <span data-ttu-id="97497-304">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="97497-304">OUTPUTS</span></span>

### <span data-ttu-id="97497-305">Nenhum</span><span class="sxs-lookup"><span data-stu-id="97497-305">None</span></span>

<span data-ttu-id="97497-306">O cmdlet não retorna nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="97497-306">The cmdlet does not return any output.</span></span>

## <span data-ttu-id="97497-307">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="97497-307">NOTES</span></span>

<span data-ttu-id="97497-308">Para se conectar a um computador remoto, você deve ser um membro do grupo Administradores no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="97497-308">To connect to a remote computer, you must be a member of the Administrators group on the remote computer.</span></span> <span data-ttu-id="97497-309">Para iniciar uma sessão interativa no computador local, você deve iniciar o PowerShell com a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="97497-309">To start an interactive session on the local computer, you must start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="97497-310">Quando você usa o `Enter-PSSession` , seu perfil de usuário no computador remoto é usado para a sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="97497-310">When you use `Enter-PSSession`, your user profile on the remote computer is used for the interactive session.</span></span> <span data-ttu-id="97497-311">Os comandos no perfil de usuário remoto, incluindo comandos para adicionar módulos do PowerShell e para alterar o prompt de comando, são executados antes que o prompt remoto seja exibido.</span><span class="sxs-lookup"><span data-stu-id="97497-311">The commands in the remote user profile, including commands to add PowerShell modules and to change the command prompt, run before the remote prompt is displayed.</span></span>

<span data-ttu-id="97497-312">`Enter-PSSession` usa a configuração de cultura da interface do usuário no computador local para a sessão interativa.</span><span class="sxs-lookup"><span data-stu-id="97497-312">`Enter-PSSession` uses the UI culture setting on the local computer for the interactive session.</span></span> <span data-ttu-id="97497-313">Para localizar a cultura da interface do usuário local, use a `$UICulture` variável automática.</span><span class="sxs-lookup"><span data-stu-id="97497-313">To find the local UI culture, use the `$UICulture` automatic variable.</span></span>

<span data-ttu-id="97497-314">`Enter-PSSession` requer os `Get-Command` `Out-Default` `Exit-PSSession` cmdlets, e.</span><span class="sxs-lookup"><span data-stu-id="97497-314">`Enter-PSSession` requires the `Get-Command`, `Out-Default`, and `Exit-PSSession` cmdlets.</span></span> <span data-ttu-id="97497-315">Se esses cmdlets não estiverem incluídos na configuração de sessão no computador remoto, os `Enter-PSSession` comandos falharão.</span><span class="sxs-lookup"><span data-stu-id="97497-315">If these cmdlets are not included in the session configuration on the remote computer, the `Enter-PSSession` commands fails.</span></span>

<span data-ttu-id="97497-316">Ao contrário de `Invoke-Command` , que analisa e interpreta os comandos antes de enviá-los para o computador remoto, `Enter-PSSession` o envia os comandos diretamente para o computador remoto sem interpretação.</span><span class="sxs-lookup"><span data-stu-id="97497-316">Unlike `Invoke-Command`, which parses and interprets the commands before it sends them to the remote computer, `Enter-PSSession` sends the commands directly to the remote computer without interpretation.</span></span>

<span data-ttu-id="97497-317">Se a sessão que você deseja inserir estiver ocupada processando um comando, pode haver um atraso antes que o PowerShell responda ao `Enter-PSSession` comando.</span><span class="sxs-lookup"><span data-stu-id="97497-317">If the session you want to enter is busy processing a command, there might be a delay before PowerShell responds to the `Enter-PSSession` command.</span></span> <span data-ttu-id="97497-318">Você está conectado assim que a sessão está disponível.</span><span class="sxs-lookup"><span data-stu-id="97497-318">You are connected as soon as the session is available.</span></span> <span data-ttu-id="97497-319">Para cancelar o `Enter-PSSession` comando, pressione <kbd>Ctrl</kbd> + <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="97497-319">To cancel the `Enter-PSSession` command, press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span>

## <span data-ttu-id="97497-320">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="97497-320">RELATED LINKS</span></span>

[<span data-ttu-id="97497-321">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="97497-321">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="97497-322">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="97497-322">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="97497-323">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="97497-323">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="97497-324">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="97497-324">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="97497-325">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="97497-325">Remove-PSSession</span></span>](Remove-PSSession.md)

[<span data-ttu-id="97497-326">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="97497-326">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="97497-327">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="97497-327">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="97497-328">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="97497-328">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="97497-329">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="97497-329">about_PSSessions</span></span>](About/about_PSSessions.md)

[<span data-ttu-id="97497-330">about_Remote</span><span class="sxs-lookup"><span data-stu-id="97497-330">about_Remote</span></span>](About/about_Remote.md)
