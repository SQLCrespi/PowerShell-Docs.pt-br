---
external help file: Microsoft.Powershell.Workflow.ServiceCore.dll-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSWorkflow
ms.date: 07/10/2019
online version: https://docs.microsoft.com/powershell/module/psworkflow/new-psworkflowsession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSWorkflowSession
ms.openlocfilehash: 995dd8a6df3ac8ebd7a204d2aefef3fa6aa71e14
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193657"
---
# <span data-ttu-id="9e9d3-103">New-PSWorkflowSession</span><span class="sxs-lookup"><span data-stu-id="9e9d3-103">New-PSWorkflowSession</span></span>

## <span data-ttu-id="9e9d3-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="9e9d3-104">SYNOPSIS</span></span>
<span data-ttu-id="9e9d3-105">Cria uma sessão de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-105">Creates a workflow session.</span></span>

## <span data-ttu-id="9e9d3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9e9d3-106">SYNTAX</span></span>

```
New-PSWorkflowSession [[-ComputerName] <String[]>] [-Credential <Object>] [-Name <String[]>] [-Port <Int32>]
 [-UseSSL] [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [-EnableNetworkAccess]
 [<CommonParameters>]
```

## <span data-ttu-id="9e9d3-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9e9d3-107">DESCRIPTION</span></span>

<span data-ttu-id="9e9d3-108">O `New-PSWorkflowSession` cmdlet cria uma sessão gerenciada pelo usuário ( **PSSession** ) que é especialmente projetada para executar fluxos de trabalho do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-108">The `New-PSWorkflowSession` cmdlet creates a user-managed session ( **PSSession** ) that is especially designed for running Windows PowerShell workflows.</span></span> <span data-ttu-id="9e9d3-109">Ele usa a configuração de sessão do Microsoft.PowerShell.Workflow, que inclui scripts, arquivos de tipo e formatação e opções que são necessárias para fluxos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-109">It uses the Microsoft.PowerShell.Workflow session configuration, which includes scripts, type and formatting files, and options that are required for workflows.</span></span>

<span data-ttu-id="9e9d3-110">Você pode usar `New-PSWorkflowSession` o ou seu alias, `nwsn` .</span><span class="sxs-lookup"><span data-stu-id="9e9d3-110">You can use `New-PSWorkflowSession` or its alias, `nwsn`.</span></span>

<span data-ttu-id="9e9d3-111">Também é possível adicionar parâmetros comuns de fluxo de trabalho para esse comando.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-111">You can also add workflow common parameters to this command.</span></span> <span data-ttu-id="9e9d3-112">Para obter mais informações sobre parâmetros comuns de fluxo de trabalho, consulte [about_WorkflowCommonParameters](./about/about_WorkflowCommonParameters.md)</span><span class="sxs-lookup"><span data-stu-id="9e9d3-112">For more information about workflow common parameters, see [about_WorkflowCommonParameters](./about/about_WorkflowCommonParameters.md)</span></span>

<span data-ttu-id="9e9d3-113">Este cmdlet foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-113">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="9e9d3-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="9e9d3-114">EXAMPLES</span></span>

### <span data-ttu-id="9e9d3-115">Exemplo 1: criar uma sessão de fluxo de trabalho em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="9e9d3-115">Example 1: Create a workflow session on a remote computer</span></span>

<span data-ttu-id="9e9d3-116">Este exemplo cria a sessão **WorkflowTests** no computador remoto ServerNode01.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-116">This example creates the **WorkflowTests** session on the ServerNode01 remote computer.</span></span>

```powershell
$params = @{
    ComputerName = "ServerNode01"
    Name = "WorkflowTests"
    SessionOption = (New-PSSessionOption -OutputBufferingMode Drop)
}
New-PSWorkflowSession @params
```

<span data-ttu-id="9e9d3-117">O valor do parâmetro **SessionOption** é um `New-PSSessionOption` comando que define o modo de buffer de saída na sessão a ser **descartada** .</span><span class="sxs-lookup"><span data-stu-id="9e9d3-117">The value of the **SessionOption** parameter is a `New-PSSessionOption` command that sets the output buffering mode in the session to **Drop** .</span></span>

### <span data-ttu-id="9e9d3-118">Exemplo 2: criar sessões de fluxo de trabalho em vários computadores remotos</span><span class="sxs-lookup"><span data-stu-id="9e9d3-118">Example 2: Create workflow sessions on multiple remote computers</span></span>

<span data-ttu-id="9e9d3-119">Este exemplo cria sessões de fluxo de trabalho nos computadores ServerNode01 e Server12.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-119">This example creates workflow sessions on the ServerNode01 and Server12 computers.</span></span> <span data-ttu-id="9e9d3-120">O comando usa o parâmetro **Credential** para ser executado com as permissões de um administrador de domínio.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-120">The command uses the **Credential** parameter to run with the permissions of the domain administrator.</span></span>

```powershell
"ServerNode01", "Server12" |
    New-PSWorkflowSession -Name WorkflowSession -Credential Domain01\Admin01 -ThrottleLimit 150
```

<span data-ttu-id="9e9d3-121">O comando usa o parâmetro **ThrottleLimit** para aumentar o limite de restrição por comando para 150.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-121">The command uses the **ThrottleLimit** parameter to increase the per-command throttle limit to 150.</span></span>
<span data-ttu-id="9e9d3-122">Esse valor tem precedência sobre o limite de limitação padrão de 100 que é definido na configuração de sessão **Microsoft. PowerShell. Workflow** .</span><span class="sxs-lookup"><span data-stu-id="9e9d3-122">This value takes precedence over the default throttle limit of 100 that is set in the **Microsoft.PowerShell.Workflow** session configuration.</span></span>

## <span data-ttu-id="9e9d3-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9e9d3-123">PARAMETERS</span></span>

### <span data-ttu-id="9e9d3-124">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="9e9d3-124">-ApplicationName</span></span>

<span data-ttu-id="9e9d3-125">Especifica o segmento de nome de aplicativo do URI de conexão.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-125">Specifies the application name segment of the connection URI.</span></span>

<span data-ttu-id="9e9d3-126">O valor padrão é o valor da `$PSSessionApplicationName` variável de preferência no computador local.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-126">The default value is the value of the `$PSSessionApplicationName` preference variable on the local computer.</span></span> <span data-ttu-id="9e9d3-127">Se esta variável de preferência não estiver definida, o valor padrão é WSMAN.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-127">If this preference variable is not defined, the default value is WSMAN.</span></span> <span data-ttu-id="9e9d3-128">Esse valor é adequado para a maioria dos usos.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-128">This value is appropriate for most uses.</span></span> <span data-ttu-id="9e9d3-129">Para obter mais informações, consulte [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="9e9d3-129">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="9e9d3-130">O serviço WinRM usa o nome do aplicativo para selecionar um ouvinte para atender à solicitação de conexão.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-130">The WinRM service uses the application name to select a listener to service the connection request.</span></span>
<span data-ttu-id="9e9d3-131">O valor desse parâmetro deve corresponder ao valor da propriedade **URLPrefix** de um ouvinte no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-131">The value of this parameter should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9e9d3-132">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="9e9d3-132">-Authentication</span></span>

<span data-ttu-id="9e9d3-133">Especifica o mecanismo usado para autenticar as credenciais do usuário.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-133">Specifies the mechanism that is used to authenticate the user credentials.</span></span>
<span data-ttu-id="9e9d3-134">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="9e9d3-134">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="9e9d3-135">Padrão</span><span class="sxs-lookup"><span data-stu-id="9e9d3-135">Default</span></span>
- <span data-ttu-id="9e9d3-136">Básico</span><span class="sxs-lookup"><span data-stu-id="9e9d3-136">Basic</span></span>
- <span data-ttu-id="9e9d3-137">CredSSP</span><span class="sxs-lookup"><span data-stu-id="9e9d3-137">Credssp</span></span>
- <span data-ttu-id="9e9d3-138">Digest</span><span class="sxs-lookup"><span data-stu-id="9e9d3-138">Digest</span></span>
- <span data-ttu-id="9e9d3-139">Kerberos</span><span class="sxs-lookup"><span data-stu-id="9e9d3-139">Kerberos</span></span>
- <span data-ttu-id="9e9d3-140">Negotiate</span><span class="sxs-lookup"><span data-stu-id="9e9d3-140">Negotiate</span></span>
- <span data-ttu-id="9e9d3-141">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="9e9d3-141">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="9e9d3-142">O valor padrão é Default.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-142">The default value is Default.</span></span>

<span data-ttu-id="9e9d3-143">A autenticação CredSSP está disponível somente no Windows Vista, no Windows Server 2008 e em versões posteriores do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-143">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="9e9d3-144">Para obter mais informações sobre os valores desse parâmetro, consulte [Enumeração AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="9e9d3-144">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="9e9d3-145">A autenticação do Credential Security Service Provider (CredSSP), na qual as credenciais do usuário são passadas para um computador remoto a ser autenticado, é projetada para comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remoto.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-145">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="9e9d3-146">Esse mecanismo aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-146">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="9e9d3-147">Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-147">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e9d3-148">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="9e9d3-148">-CertificateThumbprint</span></span>

<span data-ttu-id="9e9d3-149">Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa ação.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-149">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="9e9d3-150">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-150">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="9e9d3-151">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-151">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="9e9d3-152">Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-152">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="9e9d3-153">Para obter uma impressão digital do certificado, use o `Get-Item` cmdlet ou o `Get-ChildItem` cmdlet na unidade CERT: do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-153">To get a certificate thumbprint, use the `Get-Item` cmdlet or the `Get-ChildItem` cmdlet in the Windows PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="9e9d3-154">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="9e9d3-154">-ComputerName</span></span>

<span data-ttu-id="9e9d3-155">Cria uma conexão persistente ( **PSSession** ) para o computador especificado.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-155">Creates a persistent connection ( **PSSession** ) to the specified computer.</span></span> <span data-ttu-id="9e9d3-156">Se você inserir vários nomes de computador, o Windows PowerShell criará várias **PSSessions** , uma para cada computador.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-156">If you enter multiple computer names, Windows PowerShell creates multiple **PSSessions** , one for each computer.</span></span> <span data-ttu-id="9e9d3-157">O padrão é o computador local.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-157">The default is the local computer.</span></span>

<span data-ttu-id="9e9d3-158">Digite o nome NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado de um ou mais computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-158">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more remote computers.</span></span> <span data-ttu-id="9e9d3-159">Para especificar o computador local, digite o nome do computador, localhost ou um ponto (.).</span><span class="sxs-lookup"><span data-stu-id="9e9d3-159">To specify the local computer, type the computer name, localhost, or a dot (.).</span></span> <span data-ttu-id="9e9d3-160">Quando o computador está em um domínio diferente do usuário, é necessário o nome de domínio totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-160">When the computer is in a different domain than the user, the fully qualified domain name is required.</span></span> <span data-ttu-id="9e9d3-161">Também é possível canalizar um nome de computador, entre aspas `New-PSWorkflowSession` .</span><span class="sxs-lookup"><span data-stu-id="9e9d3-161">You can also pipe a computer name, in quotation marks to `New-PSWorkflowSession`.</span></span>

<span data-ttu-id="9e9d3-162">Para usar um endereço IP no valor do parâmetro **ComputerName** , o comando deve incluir o parâmetro **Credential** .</span><span class="sxs-lookup"><span data-stu-id="9e9d3-162">To use an IP address in the value of the **ComputerName** parameter, the command must include the **Credential** parameter.</span></span> <span data-ttu-id="9e9d3-163">Além disso, o computador deve ser configurado para o transporte HTTPS ou o endereço IP do computador remoto deve ser incluído na lista WinRM TrustedHosts no computador local.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-163">Also, the computer must be configured for HTTPS transport or the IP address of the remote computer must be included in the WinRM TrustedHosts list on the local computer.</span></span> <span data-ttu-id="9e9d3-164">Para obter instruções sobre como adicionar um nome de computador à lista TrustedHosts, consulte "como adicionar um computador à lista de hosts confiáveis" em [about_Remote_Troubleshooting](../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="9e9d3-164">For instructions for adding a computer name to the TrustedHosts list, see "How to Add a Computer to the Trusted Host List" in [about_Remote_Troubleshooting](../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: 0
Default value: Local computer
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="9e9d3-165">-Credential</span><span class="sxs-lookup"><span data-stu-id="9e9d3-165">-Credential</span></span>

<span data-ttu-id="9e9d3-166">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-166">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="9e9d3-167">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-167">The default is the current user.</span></span> <span data-ttu-id="9e9d3-168">Digite um nome de usuário, como User01, Domínio01 \ Usuário01 ou User@Domain.com , ou insira um objeto **PSCredential** , como um retornado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-168">Type a user name, such as User01, Domain01\User01, or User@Domain.com, or enter a **PSCredential** object, such as one returned by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="9e9d3-169">Quando você digita um nome de usuário, esse cmdlet solicita uma senha.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-169">When you type a user name, this cmdlet prompts you for a password.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9e9d3-170">-EnableNetworkAccess</span><span class="sxs-lookup"><span data-stu-id="9e9d3-170">-EnableNetworkAccess</span></span>

<span data-ttu-id="9e9d3-171">Indica que esse cmdlet adiciona um token de segurança interativo a sessões de loopback.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-171">Indicates that this cmdlet adds an interactive security token to loopback sessions.</span></span> <span data-ttu-id="9e9d3-172">O token interativo permite executar comandos na sessão de loopback que obtêm dados de outros computadores.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-172">The interactive token lets you run commands in the loopback session that get data from other computers.</span></span> <span data-ttu-id="9e9d3-173">Por exemplo, você pode executar um comando na sessão que copia arquivos XML de um computador remoto no computador local.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-173">For example, you can run a command in the session that copies XML files from a remote computer to the local computer.</span></span>

<span data-ttu-id="9e9d3-174">Uma sessão de loopback é uma **PSSession** originada e termina no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-174">A loopback session is a **PSSession** that originates and ends on the same computer.</span></span> <span data-ttu-id="9e9d3-175">Para criar uma sessão de loopback, não especifique o parâmetro **ComputerName** ou defina seu valor como ponto, localhost ou o nome do computador local.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-175">To create a loopback session, do not specify the **ComputerName** parameter or set its value to dot, localhost, or the name of the local computer.</span></span>

<span data-ttu-id="9e9d3-176">Por padrão, são criadas sessões de loopback que têm um token de rede, o que pode não fornecer permissão suficiente para autenticar em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-176">By default, loopback sessions are created that have a network token, which might not provide sufficient permission to authenticate to remote computers.</span></span>

<span data-ttu-id="9e9d3-177">O parâmetro **EnableNetworkAccess** só é eficaz em sessões de loopback.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-177">The **EnableNetworkAccess** parameter is effective only in loopback sessions.</span></span> <span data-ttu-id="9e9d3-178">Se você especificar o parâmetro **EnableNetworkAccess** ao criar uma sessão em um computador remoto, o comando terá sucesso, mas o parâmetro será ignorado.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-178">If you specify the **EnableNetworkAccess** parameter when you create a session on a remote computer, the command succeeds, but the parameter is ignored.</span></span>

<span data-ttu-id="9e9d3-179">Também é possível permitir o acesso remoto em uma sessão de loopback usando o valor **CredSSP** do parâmetro **Authentication** , que delega as credenciais de sessão a outros computadores.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-179">You can also allow remote access in a loopback session by using the **CredSSP** value of the **Authentication** parameter, which delegates the session credentials to other computers.</span></span>

<span data-ttu-id="9e9d3-180">Para proteger o computador contra acesso mal-intencionado, as sessões de loopback desconectadas que têm tokens interativos, aquelas criadas usando o parâmetro **EnableNetworkAccess** , podem ser reconectadas somente do computador no qual a sessão foi criada.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-180">To protect the computer from malicious access, disconnected loopback sessions that have interactive tokens, those created by using the **EnableNetworkAccess** parameter, can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="9e9d3-181">Sessões desconectadas que usam a autenticação CredSSP podem ser reconectadas por meio de outros computadores.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-181">Disconnected sessions that use CredSSP authentication can be reconnected from other computers.</span></span> <span data-ttu-id="9e9d3-182">Para obter mais informações, consulte o cmdlet `Disconnect-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-182">For more information, see the `Disconnect-PSSession` cmdlet.</span></span>

<span data-ttu-id="9e9d3-183">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-183">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="9e9d3-184">-Name</span><span class="sxs-lookup"><span data-stu-id="9e9d3-184">-Name</span></span>

<span data-ttu-id="9e9d3-185">Especifica um nome amigável para a sessão de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-185">Specifies a friendly name for the workflow session.</span></span> <span data-ttu-id="9e9d3-186">Você pode usar o nome com outros cmdlets, como `Get-PSSession` e `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="9e9d3-186">You can use the name with other cmdlets, such as `Get-PSSession` and `Enter-PSSession`.</span></span> <span data-ttu-id="9e9d3-187">Não é necessário que o nome do computador ou da sessão atual seja exclusivo.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-187">The name is not required to be unique to the computer or the current session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Session#
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e9d3-188">-Port</span><span class="sxs-lookup"><span data-stu-id="9e9d3-188">-Port</span></span>

<span data-ttu-id="9e9d3-189">Especifica a porta de rede no computador remoto que é usada para esta conexão.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-189">Specifies the network port on the remote computer that is used for this connection.</span></span> <span data-ttu-id="9e9d3-190">Para se conectar a um computador remoto, este deve estar escutando na porta usada pela conexão.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-190">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="9e9d3-191">As portas padrão são 5985 (porta do WinRM para HTTP) e 5986 (porta do WinRM para HTTPS).</span><span class="sxs-lookup"><span data-stu-id="9e9d3-191">The default ports are 5985 (WinRM port for HTTP) and 5986 (WinRM port for HTTPS).</span></span>

<span data-ttu-id="9e9d3-192">Antes de usar outra porta, você deve configurar o ouvinte do WinRM no computador remoto para escutar nessa porta.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-192">Before using another port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="9e9d3-193">Use os seguintes comandos para configurar o ouvinte:</span><span class="sxs-lookup"><span data-stu-id="9e9d3-193">Use the following commands to configure the listener:</span></span>

`winrm delete winrm/config/listener?Address=*+Transport=HTTP`

`winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number\>"}`

<span data-ttu-id="9e9d3-194">Não use o parâmetro **Port** a menos que seja necessário.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-194">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="9e9d3-195">A configuração da porta no comando se aplica a todos os computadores ou sessões em que o comando for executado.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-195">The port setting in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="9e9d3-196">Uma configuração de porta alternativa pode impedir que o comando seja executado em todos os computadores.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-196">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e9d3-197">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="9e9d3-197">-SessionOption</span></span>

<span data-ttu-id="9e9d3-198">Especifica as opções avançadas para a sessão.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-198">Specifies advanced options for the session.</span></span> <span data-ttu-id="9e9d3-199">Insira um objeto **SessionOption** , como um que você cria usando o `New-PSSessionOption` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-199">Enter a **SessionOption** object, such as one that you create by using the `New-PSSessionOption` cmdlet.</span></span>

<span data-ttu-id="9e9d3-200">Os valores padrão para as opções são determinados pelo valor da variável de `$PSSessionOption` preferência, se estiver definido.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-200">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="9e9d3-201">Caso contrário, os valores padrão são estabelecidos por opções definidas na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-201">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="9e9d3-202">Os valores de opção de sessão têm precedência sobre valores padrão para sessões definidas na `$PSSessionOption` variável de preferência e na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-202">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="9e9d3-203">No entanto, eles não têm precedência sobre valores máximos, cotas ou limites definidos na configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-203">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span> <span data-ttu-id="9e9d3-204">Para obter mais informações sobre configurações de sessão, consulte [about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="9e9d3-204">For more information about session configurations, see [about_Session_Configurations](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md).</span></span>

<span data-ttu-id="9e9d3-205">Para obter uma descrição das opções de sessão, incluindo os valores padrão, consulte `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="9e9d3-205">For a description of the session options, including the default values, see `New-PSSessionOption`.</span></span>
<span data-ttu-id="9e9d3-206">Para obter informações sobre a `$PSSessionOption` variável de preferência, consulte [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="9e9d3-206">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e9d3-207">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="9e9d3-207">-ThrottleLimit</span></span>

<span data-ttu-id="9e9d3-208">Especifica o número máximo de conexões simultâneas que podem ser estabelecidas para executar o comando.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-208">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="9e9d3-209">Se você omitir esse parâmetro ou inserir um valor de 0 (zero), o valor padrão para a configuração de sessão **Microsoft. PowerShellWorkflow** , 100, será usado.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-209">If you omit this parameter or enter a value of 0 (zero), the default value for the **Microsoft.PowerShellWorkflow** session configuration, 100, is used.</span></span>

<span data-ttu-id="9e9d3-210">O limite de aceleração aplica-se somente ao comando atual e não à sessão ou ao computador.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-210">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e9d3-211">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="9e9d3-211">-UseSSL</span></span>

<span data-ttu-id="9e9d3-212">Indica que esse cmdlet usa o protocolo protocolo SSL (SSL) para estabelecer uma conexão com o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-212">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to establish a connection to the remote computer.</span></span> <span data-ttu-id="9e9d3-213">Por padrão, SSL não é usado.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-213">By default, SSL is not used.</span></span>

<span data-ttu-id="9e9d3-214">O WS-Management criptografa todo o conteúdo do Windows PowerShell transmitido pela rede.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-214">WS-Management encrypts all Windows PowerShell content transmitted over the network.</span></span> <span data-ttu-id="9e9d3-215">O parâmetro **UseSSL** é uma proteção adicional que envia os dados por uma conexão HTTPS em vez de uma conexão http.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-215">The **UseSSL** parameter is an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="9e9d3-216">Se você especificar esse parâmetro, mas o SSL não estiver disponível na porta usada para o comando, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-216">If you specify this parameter, but SSL is not available on the port that is used for the command, the command fails.</span></span>

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

### <span data-ttu-id="9e9d3-217">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9e9d3-217">CommonParameters</span></span>

<span data-ttu-id="9e9d3-218">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-218">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9e9d3-219">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9e9d3-219">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9e9d3-220">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="9e9d3-220">INPUTS</span></span>

### <span data-ttu-id="9e9d3-221">System. Management. Automation. Runspaces. PSSession [], System. String</span><span class="sxs-lookup"><span data-stu-id="9e9d3-221">System.Management.Automation.Runspaces.PSSession[], System.String</span></span>

<span data-ttu-id="9e9d3-222">É possível canalizar uma sessão ou um nome de computador para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9e9d3-222">You can pipe a session or a computer name to this cmdlet.</span></span>

## <span data-ttu-id="9e9d3-223">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="9e9d3-223">OUTPUTS</span></span>

### <span data-ttu-id="9e9d3-224">System. Management. Automation. Runspaces. PSSession</span><span class="sxs-lookup"><span data-stu-id="9e9d3-224">System.Management.Automation.Runspaces.PSSession</span></span>

## <span data-ttu-id="9e9d3-225">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="9e9d3-225">NOTES</span></span>

<span data-ttu-id="9e9d3-226">Um `New-PSWorkflowSession` comando é equivalente ao seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="9e9d3-226">A `New-PSWorkflowSession` command is equivalent to the following command:</span></span>

`New-PSSession -ConfigurationName Microsoft.PowerShell.Workflow`

## <span data-ttu-id="9e9d3-227">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="9e9d3-227">RELATED LINKS</span></span>

[<span data-ttu-id="9e9d3-228">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="9e9d3-228">Disconnect-PSSession</span></span>](../Microsoft.PowerShell.Core/Disconnect-PSSession.md)

[<span data-ttu-id="9e9d3-229">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="9e9d3-229">New-PSSession</span></span>](../Microsoft.PowerShell.Core/New-PSSession.md)

[<span data-ttu-id="9e9d3-230">New-PSTransportOption</span><span class="sxs-lookup"><span data-stu-id="9e9d3-230">New-PSTransportOption</span></span>](../Microsoft.PowerShell.Core/New-PSTransportOption.md)

[<span data-ttu-id="9e9d3-231">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="9e9d3-231">Register-PSSessionConfiguration</span></span>](../Microsoft.PowerShell.Core/Register-PSSessionConfiguration.md)

[<span data-ttu-id="9e9d3-232">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="9e9d3-232">about_PSSessions</span></span>](../Microsoft.PowerShell.Core/About/about_PSSessions.md)

[<span data-ttu-id="9e9d3-233">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="9e9d3-233">about_Session_Configurations</span></span>](../Microsoft.PowerShell.Core/About/about_Session_Configurations.md)

[<span data-ttu-id="9e9d3-234">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="9e9d3-234">about_Workflows</span></span>](../PSWorkflow/About/about_Workflows.md)

[<span data-ttu-id="9e9d3-235">about_WorkflowCommonParameters</span><span class="sxs-lookup"><span data-stu-id="9e9d3-235">about_WorkflowCommonParameters</span></span>](About/about_WorkflowCommonParameters.md)
