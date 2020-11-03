---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/test-wsman?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-WSMan
ms.openlocfilehash: 602f390aa6474d56e2ac1865dbad20fbb73dc4f1
ms.sourcegitcommit: 87b9b989f261b52969e99159e99ee28ad8d8839a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/21/2020
ms.locfileid: "93194856"
---
# <span data-ttu-id="92c5e-103">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="92c5e-103">Test-WSMan</span></span>

## <span data-ttu-id="92c5e-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="92c5e-104">SYNOPSIS</span></span>
<span data-ttu-id="92c5e-105">Testa se o serviço WinRM está em execução em um computador local ou remoto.</span><span class="sxs-lookup"><span data-stu-id="92c5e-105">Tests whether the WinRM service is running on a local or remote computer.</span></span>

## <span data-ttu-id="92c5e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="92c5e-106">SYNTAX</span></span>

```
Test-WSMan [[-ComputerName] <String>] [-Authentication <AuthenticationMechanism>] [-Port <Int32>] [-UseSSL]
 [-ApplicationName <String>] [-Credential <PSCredential>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="92c5e-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="92c5e-107">DESCRIPTION</span></span>

<span data-ttu-id="92c5e-108">O cmdlet **Test-WSMan** envia uma solicitação de identificação que determina se o serviço WinRM está em execução em um computador local ou remoto.</span><span class="sxs-lookup"><span data-stu-id="92c5e-108">The **Test-WSMan** cmdlet submits an identification request that determines whether the WinRM service is running on a local or remote computer.</span></span>
<span data-ttu-id="92c5e-109">Se o computador testado estiver executando o serviço, o cmdlet exibirá o esquema de identidade do WS-Management, a versão do protocolo, o fornecedor do produto e a versão do produto do serviço testado.</span><span class="sxs-lookup"><span data-stu-id="92c5e-109">If the tested computer is running the service, the cmdlet displays the WS-Management identity schema, the protocol version, the product vendor, and the product version of the tested service.</span></span>

## <span data-ttu-id="92c5e-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="92c5e-110">EXAMPLES</span></span>

### <span data-ttu-id="92c5e-111">Exemplo 1: determinar o status do serviço WinRM</span><span class="sxs-lookup"><span data-stu-id="92c5e-111">Example 1: Determine the status of the WinRM service</span></span>

```
PS C:\> Test-WSMan
wsmid           : http://schemas.dmtf.org/wbem/wsman/identity/1/wsmanidentity.xsd

ProtocolVersion : http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd

ProductVendor   : Microsoft Corporation

ProductVersion  : OS: 0.0.0 SP: 0.0 Stack: 2.0
```

<span data-ttu-id="92c5e-112">Este comando determina se o serviço WinRM está em execução no computador local ou em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="92c5e-112">This command determines whether the WinRM service is running on the local computer or on a remote computer.</span></span>

### <span data-ttu-id="92c5e-113">Exemplo 2: determinar o status do serviço WinRM em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="92c5e-113">Example 2: Determine the status of the WinRM service on a remote computer</span></span>

```
PS C:\> Test-WSMan -ComputerName "server01"
wsmid           : http://schemas.dmtf.org/wbem/wsman/identity/1/wsmanidentity.xsd

ProtocolVersion : http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd

ProductVendor   : Microsoft Corporation

ProductVersion  : OS: 0.0.0 SP: 0.0 Stack: 2.0
```

<span data-ttu-id="92c5e-114">Esse comando determina se o serviço WinRM está em execução no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="92c5e-114">This command determines whether the WinRM service is running on the server01 computer.</span></span>

### <span data-ttu-id="92c5e-115">Exemplo 3: determinar o status do serviço WinRM e a versão do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="92c5e-115">Example 3: Determine the status of the WinRM service and the operating system version</span></span>

```
PS C:\> Test-WSMan -Authentication default
wsmid           : http://schemas.dmtf.org/wbem/wsman/identity/1/wsmanidentity.xsd

ProtocolVersion : http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd

ProductVendor   : Microsoft Corporation

ProductVersion  : OS: 6.0.6001 SP: 1.0 Stack: 2.0
```

<span data-ttu-id="92c5e-116">Esse comando testa para ver se o serviço de WS-Management (WinRM) está em execução no computador local usando o parâmetro de autenticação.</span><span class="sxs-lookup"><span data-stu-id="92c5e-116">This command tests to see whether the WS-Management (WinRM) service is running on the local computer by using the authentication parameter.</span></span>

<span data-ttu-id="92c5e-117">O uso do parâmetro de autenticação permite que **Test-WSMan** retorne a versão do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="92c5e-117">Using the authentication parameter enables **Test-WSMan** to return the operating system version.</span></span>

### <span data-ttu-id="92c5e-118">Exemplo 4: determinar o status do serviço WinRM e a versão do sistema operacional em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="92c5e-118">Example 4: Determine the status of the WinRM service and the operating system version on a remote computer</span></span>

```
PS C:\> Test-WSMan -ComputerName "server01" -Authentication default
wsmid           : http://schemas.dmtf.org/wbem/wsman/identity/1/wsmanidentity.xsd

ProtocolVersion : http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd

ProductVendor   : Microsoft Corporation

ProductVersion  : OS: 6.1.7021 SP: 0.0 Stack: 2.0
```

<span data-ttu-id="92c5e-119">Esse comando testa para ver se o serviço de WS-Management (WinRM) está em execução no computador chamado Server01 usando o parâmetro de autenticação.</span><span class="sxs-lookup"><span data-stu-id="92c5e-119">This command tests to see whether the WS-Management (WinRM) service is running on the computer named server01 using the authentication parameter.</span></span>

<span data-ttu-id="92c5e-120">O uso do parâmetro de autenticação permite que **Test-WSMan** retorne a versão do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="92c5e-120">Using the authentication parameter enables **Test-WSMan** to return the operating system version.</span></span>

## <span data-ttu-id="92c5e-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="92c5e-121">PARAMETERS</span></span>

### <span data-ttu-id="92c5e-122">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="92c5e-122">-ApplicationName</span></span>

<span data-ttu-id="92c5e-123">Especifica o nome do aplicativo na conexão.</span><span class="sxs-lookup"><span data-stu-id="92c5e-123">Specifies the application name in the connection.</span></span>
<span data-ttu-id="92c5e-124">O valor padrão do parâmetro *ApplicationName* é WSMan.</span><span class="sxs-lookup"><span data-stu-id="92c5e-124">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="92c5e-125">O identificador completo para o ponto de extremidade remoto é no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="92c5e-125">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="92c5e-126">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="92c5e-126">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="92c5e-127">Por exemplo: `http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="92c5e-127">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="92c5e-128">Os Serviços de Informações da Internet (IIS), que hospedam a sessão, encaminham solicitações com esse ponto de extremidade para o aplicativo especificado.</span><span class="sxs-lookup"><span data-stu-id="92c5e-128">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="92c5e-129">Essa configuração padrão de WSMAN é apropriada para a maioria dos usos.</span><span class="sxs-lookup"><span data-stu-id="92c5e-129">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="92c5e-130">Esse parâmetro é projetado para ser usado se muitos computadores estabelecerem conexões remotas com um computador que esteja executando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="92c5e-130">This parameter is designed to be used if many computers establish remote connections to one computer that is running PowerShell.</span></span>
<span data-ttu-id="92c5e-131">Nesse caso, o IIS hospeda o Web Services for Management (WS-Management) para ter eficiência.</span><span class="sxs-lookup"><span data-stu-id="92c5e-131">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

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

### <span data-ttu-id="92c5e-132">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="92c5e-132">-Authentication</span></span>

<span data-ttu-id="92c5e-133">Especifica o mecanismo de autenticação a ser usado no servidor.</span><span class="sxs-lookup"><span data-stu-id="92c5e-133">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="92c5e-134">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="92c5e-134">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="92c5e-135">Básica.</span><span class="sxs-lookup"><span data-stu-id="92c5e-135">Basic.</span></span>
<span data-ttu-id="92c5e-136">É um esquema no qual o nome de usuário e senha são enviados em texto não criptografado para o servidor ou proxy.</span><span class="sxs-lookup"><span data-stu-id="92c5e-136">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="92c5e-137">Padrão.</span><span class="sxs-lookup"><span data-stu-id="92c5e-137">Default.</span></span>
<span data-ttu-id="92c5e-138">Utiliza o método de autenticação implementado pelo protocolo WS-Management.</span><span class="sxs-lookup"><span data-stu-id="92c5e-138">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="92c5e-139">Esse é o padrão.</span><span class="sxs-lookup"><span data-stu-id="92c5e-139">This is the default.</span></span>
- <span data-ttu-id="92c5e-140">Digest.</span><span class="sxs-lookup"><span data-stu-id="92c5e-140">Digest.</span></span>
<span data-ttu-id="92c5e-141">É um esquema de desafio/resposta que utiliza uma cadeia de caracteres de dados do servidor especificada para o desafio.</span><span class="sxs-lookup"><span data-stu-id="92c5e-141">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="92c5e-142">Kerberos.</span><span class="sxs-lookup"><span data-stu-id="92c5e-142">Kerberos.</span></span>
<span data-ttu-id="92c5e-143">O computador cliente e o servidor autenticam mutuamente utilizando certificados Kerberos.</span><span class="sxs-lookup"><span data-stu-id="92c5e-143">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="92c5e-144">Negotiate.</span><span class="sxs-lookup"><span data-stu-id="92c5e-144">Negotiate.</span></span>
<span data-ttu-id="92c5e-145">É um esquema de desafio/resposta que negocia com o servidor ou proxy para determinar o esquema a ser utilizado para autenticação.</span><span class="sxs-lookup"><span data-stu-id="92c5e-145">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="92c5e-146">Por exemplo, esse valor de parâmetro permite que a negociação determine se o protocolo Kerberos ou NTLM é usado.</span><span class="sxs-lookup"><span data-stu-id="92c5e-146">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="92c5e-147">CredSSP.</span><span class="sxs-lookup"><span data-stu-id="92c5e-147">CredSSP.</span></span>
<span data-ttu-id="92c5e-148">Use a autenticação do Credential Security Support Provider (CredSSP), que permite que o usuário delegue as credenciais.</span><span class="sxs-lookup"><span data-stu-id="92c5e-148">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="92c5e-149">Esta opção foi criada para os comandos executados em um computador remoto, mas coletam dados ou executam comandos adicionais em outros computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="92c5e-149">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="92c5e-150">Cuidado: o CredSSP Delega as credenciais do usuário do computador local para um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="92c5e-150">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="92c5e-151">Essa prática aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="92c5e-151">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="92c5e-152">Se o computador remoto estiver comprometido, no momento em que as credenciais forem passadas a ele essas credenciais poderão ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="92c5e-152">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

<span data-ttu-id="92c5e-153">Importante: se você não especificar o parâmetro de *autenticação* , a solicitação **Test-WSMan** será enviada para o computador remoto anonimamente, sem usar a autenticação.</span><span class="sxs-lookup"><span data-stu-id="92c5e-153">Important: If you do not specify the *Authentication* parameter,, the **Test-WSMan** request is sent to the remote computer anonymously, without using authentication.</span></span>
<span data-ttu-id="92c5e-154">Se a solicitação for feita anonimamente, ela não retornará nenhuma informação específica para a versão do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="92c5e-154">If the request is made anonymously, it returns no information that is specific to the operating-system version.</span></span>
<span data-ttu-id="92c5e-155">Em vez disso, esse cmdlet exibe valores nulos para a versão do sistema operacional e o nível de service pack (so: 0.0.0 SP: 0,0).</span><span class="sxs-lookup"><span data-stu-id="92c5e-155">Instead, this cmdlet displays null values for the operating system version and service pack level (OS: 0.0.0 SP: 0.0).</span></span>

```yaml
Type: Microsoft.WSMan.Management.AuthenticationMechanism
Parameter Sets: (All)
Aliases: auth, am
Accepted values: None, Default, Digest, Negotiate, Basic, Kerberos, ClientCertificate, Credssp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="92c5e-156">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="92c5e-156">-CertificateThumbprint</span></span>

<span data-ttu-id="92c5e-157">Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa ação.</span><span class="sxs-lookup"><span data-stu-id="92c5e-157">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="92c5e-158">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="92c5e-158">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="92c5e-159">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="92c5e-159">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="92c5e-160">Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="92c5e-160">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="92c5e-161">Para obter uma impressão digital do certificado, use o comando Get-Item ou Get-ChildItem na unidade certificado do PowerShell:.</span><span class="sxs-lookup"><span data-stu-id="92c5e-161">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="92c5e-162">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="92c5e-162">-ComputerName</span></span>

<span data-ttu-id="92c5e-163">Especifica o computador no qual executar a operação de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="92c5e-163">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="92c5e-164">O valor pode ser um nome de domínio totalmente qualificado, um nome NetBIOS ou um endereço IP.</span><span class="sxs-lookup"><span data-stu-id="92c5e-164">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="92c5e-165">Utilize o nome do computador local, o localhost ou um ponto (.) para especificar o computador local.</span><span class="sxs-lookup"><span data-stu-id="92c5e-165">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="92c5e-166">O computador local é o padrão.</span><span class="sxs-lookup"><span data-stu-id="92c5e-166">The local computer is the default.</span></span>
<span data-ttu-id="92c5e-167">Quando o computador remoto está em um domínio diferente do usuário, deve-se usar um nome de domínio totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="92c5e-167">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="92c5e-168">É possível redirecionar um valor desse parâmetro para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="92c5e-168">You can pipe a value for this parameter to the cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: cn

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="92c5e-169">-Credential</span><span class="sxs-lookup"><span data-stu-id="92c5e-169">-Credential</span></span>

<span data-ttu-id="92c5e-170">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="92c5e-170">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="92c5e-171">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="92c5e-171">The default is the current user.</span></span>
<span data-ttu-id="92c5e-172">Digite um nome de usuário, como User01, Domínio01 \ Usuário01 ou User@Domain.com .</span><span class="sxs-lookup"><span data-stu-id="92c5e-172">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="92c5e-173">Ou insira um objeto **PSCredential** , como um retornado pelo cmdlet Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="92c5e-173">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="92c5e-174">Quando você digita um nome de usuário, esse cmdlet solicita uma senha.</span><span class="sxs-lookup"><span data-stu-id="92c5e-174">When you type a user name, this cmdlet prompts you for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases: cred, c

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="92c5e-175">-Port</span><span class="sxs-lookup"><span data-stu-id="92c5e-175">-Port</span></span>

<span data-ttu-id="92c5e-176">Especifica a porta a ser usada quando o cliente se conecta ao serviço WinRM.</span><span class="sxs-lookup"><span data-stu-id="92c5e-176">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="92c5e-177">Quando o transporte é HTTP, a porta padrão é 80.</span><span class="sxs-lookup"><span data-stu-id="92c5e-177">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="92c5e-178">Quando o transporte é HTTPS, a porta padrão é 443.</span><span class="sxs-lookup"><span data-stu-id="92c5e-178">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="92c5e-179">Quando você usa HTTPS como o transporte, o valor do parâmetro *ComputerName* deve corresponder ao CN (nome comum) do certificado do servidor.</span><span class="sxs-lookup"><span data-stu-id="92c5e-179">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>

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

### <span data-ttu-id="92c5e-180">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="92c5e-180">-UseSSL</span></span>

<span data-ttu-id="92c5e-181">Especifica que o protocolo de protocolo SSL (SSL) é usado para estabelecer uma conexão com o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="92c5e-181">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="92c5e-182">Por padrão, SSL não é usado.</span><span class="sxs-lookup"><span data-stu-id="92c5e-182">By default, SSL is not used.</span></span>

<span data-ttu-id="92c5e-183">WS-Management criptografa todo o conteúdo do PowerShell que é transmitido pela rede.</span><span class="sxs-lookup"><span data-stu-id="92c5e-183">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="92c5e-184">O parâmetro *UseSSL* permite especificar a proteção adicional do HTTPS em vez de http.</span><span class="sxs-lookup"><span data-stu-id="92c5e-184">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="92c5e-185">Se o SSL não estiver disponível na porta que é usada para a conexão e você especificar esse parâmetro, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="92c5e-185">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="92c5e-186">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="92c5e-186">CommonParameters</span></span>

<span data-ttu-id="92c5e-187">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="92c5e-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="92c5e-188">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="92c5e-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="92c5e-189">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="92c5e-189">INPUTS</span></span>

### <span data-ttu-id="92c5e-190">Nenhum</span><span class="sxs-lookup"><span data-stu-id="92c5e-190">None</span></span>

<span data-ttu-id="92c5e-191">Esse cmdlet não aceita nenhuma entrada.</span><span class="sxs-lookup"><span data-stu-id="92c5e-191">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="92c5e-192">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="92c5e-192">OUTPUTS</span></span>

### <span data-ttu-id="92c5e-193">Nenhum</span><span class="sxs-lookup"><span data-stu-id="92c5e-193">None</span></span>

<span data-ttu-id="92c5e-194">Este cmdlet não gera nenhum objeto de saída.</span><span class="sxs-lookup"><span data-stu-id="92c5e-194">This cmdlet does not generate any output object.</span></span>

## <span data-ttu-id="92c5e-195">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="92c5e-195">NOTES</span></span>

* <span data-ttu-id="92c5e-196">Por padrão, o cmdlet **Test-WSMan** consulta o serviço WinRM sem usar a autenticação e não retorna informações específicas para a versão do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="92c5e-196">By default, the **Test-WSMan** cmdlet queries the WinRM service without using authentication, and it returns no information that is specific to the operating-system version.</span></span> <span data-ttu-id="92c5e-197">Em vez disso, ele exibe valores nulos para a versão do sistema operacional e o nível de service pack (so: 0.0.0 SP: 0,0).</span><span class="sxs-lookup"><span data-stu-id="92c5e-197">Instead, it displays null values for the operating system version and service pack level (OS: 0.0.0 SP: 0.0).</span></span>

## <span data-ttu-id="92c5e-198">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="92c5e-198">RELATED LINKS</span></span>

[<span data-ttu-id="92c5e-199">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="92c5e-199">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="92c5e-200">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="92c5e-200">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="92c5e-201">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="92c5e-201">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="92c5e-202">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="92c5e-202">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="92c5e-203">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="92c5e-203">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="92c5e-204">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="92c5e-204">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="92c5e-205">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="92c5e-205">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="92c5e-206">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="92c5e-206">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="92c5e-207">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="92c5e-207">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="92c5e-208">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="92c5e-208">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="92c5e-209">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="92c5e-209">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="92c5e-210">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="92c5e-210">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)
