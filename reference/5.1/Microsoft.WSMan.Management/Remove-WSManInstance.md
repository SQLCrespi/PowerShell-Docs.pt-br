---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/remove-wsmaninstance?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WSManInstance
ms.openlocfilehash: 22f74418cb8c404f7ca8d388f2a30d7db045cce2
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "93196523"
---
# <span data-ttu-id="991c0-103">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="991c0-103">Remove-WSManInstance</span></span>

## <span data-ttu-id="991c0-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="991c0-104">SYNOPSIS</span></span>
<span data-ttu-id="991c0-105">Exclui uma instância do recurso de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="991c0-105">Deletes a management resource instance.</span></span>

## <span data-ttu-id="991c0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="991c0-106">SYNTAX</span></span>

### <span data-ttu-id="991c0-107">ComputerName (padrão)</span><span class="sxs-lookup"><span data-stu-id="991c0-107">ComputerName (Default)</span></span>

```
Remove-WSManInstance [-ApplicationName <String>] [-ComputerName <String>] [-OptionSet <Hashtable>]
 [-Port <Int32>] [-ResourceURI] <Uri> [-SelectorSet] <Hashtable> [-SessionOption <SessionOption>] [-UseSSL]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="991c0-108">URI</span><span class="sxs-lookup"><span data-stu-id="991c0-108">URI</span></span>

```
Remove-WSManInstance [-ConnectionURI <Uri>] [-OptionSet <Hashtable>] [-ResourceURI] <Uri>
 [-SelectorSet] <Hashtable> [-SessionOption <SessionOption>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

## <span data-ttu-id="991c0-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="991c0-109">DESCRIPTION</span></span>
<span data-ttu-id="991c0-110">O cmdlet **Remove-WSManInstance** exclui uma instância de um recurso de gerenciamento especificado nos parâmetros *ResourceURI* e *SelectorSet* .</span><span class="sxs-lookup"><span data-stu-id="991c0-110">The **Remove-WSManInstance** cmdlet deletes an instance of a management resource that is specified in the *ResourceURI* and *SelectorSet* parameters.</span></span>

<span data-ttu-id="991c0-111">Esse cmdlet usa a camada de transporte/conexão do WinRM para excluir a instância do recurso de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="991c0-111">This cmdlet uses the WinRM connection/transport layer to delete the management resource instance.</span></span>

## <span data-ttu-id="991c0-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="991c0-112">EXAMPLES</span></span>

### <span data-ttu-id="991c0-113">Exemplo 1: excluir um ouvinte</span><span class="sxs-lookup"><span data-stu-id="991c0-113">Example 1: Delete a listener</span></span>

```
PS C:\> Remove-WSManInstance -ResourceUri winrm/config/Listener -SelectorSet Address=test.fabrikam.com;Transport=http
```

<span data-ttu-id="991c0-114">Esse comando exclui o WS-Management ouvinte HTTP em um computador.</span><span class="sxs-lookup"><span data-stu-id="991c0-114">This command deletes the WS-Management HTTP listener on a computer.</span></span>

## <span data-ttu-id="991c0-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="991c0-115">PARAMETERS</span></span>

### <span data-ttu-id="991c0-116">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="991c0-116">-ApplicationName</span></span>
<span data-ttu-id="991c0-117">Especifica o nome do aplicativo na conexão.</span><span class="sxs-lookup"><span data-stu-id="991c0-117">Specifies the application name in the connection.</span></span>
<span data-ttu-id="991c0-118">O valor padrão do parâmetro *ApplicationName* é WSMan.</span><span class="sxs-lookup"><span data-stu-id="991c0-118">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="991c0-119">O identificador completo para o ponto de extremidade remoto é no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="991c0-119">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="991c0-120">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="991c0-120">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="991c0-121">Por exemplo: `http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="991c0-121">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="991c0-122">Os Serviços de Informações da Internet (IIS), que hospedam a sessão, encaminham solicitações com esse ponto de extremidade para o aplicativo especificado.</span><span class="sxs-lookup"><span data-stu-id="991c0-122">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="991c0-123">Essa configuração padrão de WSMAN é apropriada para a maioria dos usos.</span><span class="sxs-lookup"><span data-stu-id="991c0-123">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="991c0-124">Esse parâmetro é projetado para ser usado se muitos computadores estabelecerem conexões remotas com um computador que esteja executando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="991c0-124">This parameter is designed to be used if many computers establish remote connections to one computer that is running Windows PowerShell.</span></span>
<span data-ttu-id="991c0-125">Nesse caso, o IIS hospeda o Web Services for Management (WS-Management) para ter eficiência.</span><span class="sxs-lookup"><span data-stu-id="991c0-125">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="991c0-126">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="991c0-126">-Authentication</span></span>
<span data-ttu-id="991c0-127">Especifica o mecanismo de autenticação a ser usado no servidor.</span><span class="sxs-lookup"><span data-stu-id="991c0-127">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="991c0-128">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="991c0-128">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="991c0-129">Básica.</span><span class="sxs-lookup"><span data-stu-id="991c0-129">Basic.</span></span>
<span data-ttu-id="991c0-130">É um esquema no qual o nome de usuário e senha são enviados em texto não criptografado para o servidor ou proxy.</span><span class="sxs-lookup"><span data-stu-id="991c0-130">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="991c0-131">Padrão.</span><span class="sxs-lookup"><span data-stu-id="991c0-131">Default.</span></span>
<span data-ttu-id="991c0-132">Utiliza o método de autenticação implementado pelo protocolo WS-Management.</span><span class="sxs-lookup"><span data-stu-id="991c0-132">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="991c0-133">Esse é o padrão.</span><span class="sxs-lookup"><span data-stu-id="991c0-133">This is the default.</span></span>
- <span data-ttu-id="991c0-134">Digest.</span><span class="sxs-lookup"><span data-stu-id="991c0-134">Digest.</span></span>
<span data-ttu-id="991c0-135">É um esquema de desafio/resposta que utiliza uma cadeia de caracteres de dados do servidor especificada para o desafio.</span><span class="sxs-lookup"><span data-stu-id="991c0-135">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="991c0-136">Kerberos.</span><span class="sxs-lookup"><span data-stu-id="991c0-136">Kerberos.</span></span>
<span data-ttu-id="991c0-137">O computador cliente e o servidor autenticam mutuamente utilizando certificados Kerberos.</span><span class="sxs-lookup"><span data-stu-id="991c0-137">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="991c0-138">Negotiate.</span><span class="sxs-lookup"><span data-stu-id="991c0-138">Negotiate.</span></span>
<span data-ttu-id="991c0-139">É um esquema de desafio/resposta que negocia com o servidor ou proxy para determinar o esquema a ser utilizado para autenticação.</span><span class="sxs-lookup"><span data-stu-id="991c0-139">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="991c0-140">Por exemplo, esse valor de parâmetro permite que a negociação determine se o protocolo Kerberos ou NTLM é usado.</span><span class="sxs-lookup"><span data-stu-id="991c0-140">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="991c0-141">CredSSP.</span><span class="sxs-lookup"><span data-stu-id="991c0-141">CredSSP.</span></span>
<span data-ttu-id="991c0-142">Use a autenticação do Credential Security Support Provider (CredSSP), que permite que o usuário delegue as credenciais.</span><span class="sxs-lookup"><span data-stu-id="991c0-142">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="991c0-143">Esta opção foi criada para os comandos executados em um computador remoto, mas coletam dados ou executam comandos adicionais em outros computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="991c0-143">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="991c0-144">Cuidado: o CredSSP Delega as credenciais do usuário do computador local para um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="991c0-144">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="991c0-145">Essa prática aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="991c0-145">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="991c0-146">Se o computador remoto estiver comprometido, no momento em que as credenciais forem passadas a ele essas credenciais poderão ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="991c0-146">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="991c0-147">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="991c0-147">-CertificateThumbprint</span></span>
<span data-ttu-id="991c0-148">Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa ação.</span><span class="sxs-lookup"><span data-stu-id="991c0-148">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="991c0-149">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="991c0-149">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="991c0-150">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="991c0-150">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="991c0-151">Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="991c0-151">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="991c0-152">Para obter uma impressão digital do certificado, use o comando Get-Item ou Get-ChildItem na unidade Cert: do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="991c0-152">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the Windows PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="991c0-153">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="991c0-153">-ComputerName</span></span>
<span data-ttu-id="991c0-154">Especifica o computador no qual executar a operação de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="991c0-154">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="991c0-155">O valor pode ser um nome de domínio totalmente qualificado, um nome NetBIOS ou um endereço IP.</span><span class="sxs-lookup"><span data-stu-id="991c0-155">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="991c0-156">Utilize o nome do computador local, o localhost ou um ponto (.) para especificar o computador local.</span><span class="sxs-lookup"><span data-stu-id="991c0-156">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="991c0-157">O computador local é o padrão.</span><span class="sxs-lookup"><span data-stu-id="991c0-157">The local computer is the default.</span></span>
<span data-ttu-id="991c0-158">Quando o computador remoto está em um domínio diferente do usuário, deve-se usar um nome de domínio totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="991c0-158">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="991c0-159">É possível redirecionar um valor desse parâmetro para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="991c0-159">You can pipe a value for this parameter to the cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases: cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="991c0-160">-Conexãouri</span><span class="sxs-lookup"><span data-stu-id="991c0-160">-ConnectionURI</span></span>
<span data-ttu-id="991c0-161">Especifica o ponto de extremidade de conexão.</span><span class="sxs-lookup"><span data-stu-id="991c0-161">Specifies the connection endpoint.</span></span>
<span data-ttu-id="991c0-162">O formato dessa cadeia de caracteres é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="991c0-162">The format of this string is as follows:</span></span>

<span data-ttu-id="991c0-163">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="991c0-163">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="991c0-164">A cadeia de caracteres a seguir é um valor formatado corretamente para este parâmetro:</span><span class="sxs-lookup"><span data-stu-id="991c0-164">The following string is a correctly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="991c0-165">O URI deve ser totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="991c0-165">The URI must be fully qualified.</span></span>

```yaml
Type: System.Uri
Parameter Sets: URI
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="991c0-166">-Credential</span><span class="sxs-lookup"><span data-stu-id="991c0-166">-Credential</span></span>
<span data-ttu-id="991c0-167">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="991c0-167">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="991c0-168">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="991c0-168">The default is the current user.</span></span>
<span data-ttu-id="991c0-169">Digite um nome de usuário, como User01, Domínio01 \ Usuário01 ou User@Domain.com .</span><span class="sxs-lookup"><span data-stu-id="991c0-169">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="991c0-170">Ou insira um objeto **PSCredential** , como um retornado pelo cmdlet Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="991c0-170">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="991c0-171">Quando você digita um nome de usuário, esse cmdlet solicita uma senha.</span><span class="sxs-lookup"><span data-stu-id="991c0-171">When you type a user name, this cmdlet prompts you for a password.</span></span>

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

### <span data-ttu-id="991c0-172">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="991c0-172">-OptionSet</span></span>
<span data-ttu-id="991c0-173">Especifica um conjunto de opções para um serviço para modificar ou refinar a natureza da solicitação.</span><span class="sxs-lookup"><span data-stu-id="991c0-173">Specifies a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="991c0-174">Elas se assemelham a opções usadas em shells de linha de comando porque são específicas de serviço.</span><span class="sxs-lookup"><span data-stu-id="991c0-174">These resemble switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="991c0-175">Qualquer número de opções pode ser especificado.</span><span class="sxs-lookup"><span data-stu-id="991c0-175">Any number of options can be specified.</span></span>

<span data-ttu-id="991c0-176">O exemplo a seguir demonstra a sintaxe que passa os valores 1, 2 e 3 para os parâmetros a, b e c:</span><span class="sxs-lookup"><span data-stu-id="991c0-176">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

`-OptionSet @{a=1;b=2;c=3}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: os

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="991c0-177">-Port</span><span class="sxs-lookup"><span data-stu-id="991c0-177">-Port</span></span>
<span data-ttu-id="991c0-178">Especifica a porta a ser usada quando o cliente se conecta ao serviço WinRM.</span><span class="sxs-lookup"><span data-stu-id="991c0-178">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="991c0-179">Quando o transporte é HTTP, a porta padrão é 80.</span><span class="sxs-lookup"><span data-stu-id="991c0-179">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="991c0-180">Quando o transporte é HTTPS, a porta padrão é 443.</span><span class="sxs-lookup"><span data-stu-id="991c0-180">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="991c0-181">Quando você usa HTTPS como o transporte, o valor do parâmetro *ComputerName* deve corresponder ao CN (nome comum) do certificado do servidor.</span><span class="sxs-lookup"><span data-stu-id="991c0-181">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="991c0-182">No entanto, se o parâmetro *SkipCNCheck* for especificado como parte do parâmetro *SessionOption* , o nome comum do certificado do servidor não precisará corresponder ao nome do host do servidor.</span><span class="sxs-lookup"><span data-stu-id="991c0-182">However, if the *SkipCNCheck* parameter is specified as part of the *SessionOption* parameter, the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="991c0-183">O parâmetro *SkipCNCheck* deve ser usado somente para computadores confiáveis.</span><span class="sxs-lookup"><span data-stu-id="991c0-183">The *SkipCNCheck* parameter should be used only for trusted computers.</span></span>

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

### <span data-ttu-id="991c0-184">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="991c0-184">-ResourceURI</span></span>
<span data-ttu-id="991c0-185">Especifica o URI da classe ou instância de recurso.</span><span class="sxs-lookup"><span data-stu-id="991c0-185">Specifies the URI of the resource class or instance.</span></span>
<span data-ttu-id="991c0-186">O URI é utilizado para identificar um tipo específico de recurso, como discos ou processos em um computador.</span><span class="sxs-lookup"><span data-stu-id="991c0-186">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="991c0-187">Um URI consiste em um prefixo e um caminho de um recurso.</span><span class="sxs-lookup"><span data-stu-id="991c0-187">A URI consists of a prefix and a path of a resource.</span></span>
<span data-ttu-id="991c0-188">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="991c0-188">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: ruri

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="991c0-189">-SelectorSet</span><span class="sxs-lookup"><span data-stu-id="991c0-189">-SelectorSet</span></span>
<span data-ttu-id="991c0-190">Especifica um conjunto de pares de valor que são utilizados para selecionar instâncias do recurso de gerenciamento específico.</span><span class="sxs-lookup"><span data-stu-id="991c0-190">Specifies a set of value pairs that are used to select particular management resource instances.</span></span>
<span data-ttu-id="991c0-191">O parâmetro *SelectorSet* é usado quando há mais de uma instância do recurso.</span><span class="sxs-lookup"><span data-stu-id="991c0-191">The *SelectorSet* parameter is used when more than one instance of the resource exists.</span></span>
<span data-ttu-id="991c0-192">O valor de *SelectorSet* deve ser uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="991c0-192">The value of *SelectorSet* must be a hash table.</span></span>

<span data-ttu-id="991c0-193">O exemplo a seguir mostra como inserir um valor para esse parâmetro:</span><span class="sxs-lookup"><span data-stu-id="991c0-193">The following example shows how to enter a value for this parameter:</span></span>

`-SelectorSet @{Name="WinRM";ID="yyy"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="991c0-194">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="991c0-194">-SessionOption</span></span>
<span data-ttu-id="991c0-195">Especifica as opções estendidas para a sessão de WS-Management.</span><span class="sxs-lookup"><span data-stu-id="991c0-195">Specifies extended options for the WS-Management session.</span></span>
<span data-ttu-id="991c0-196">Insira um objeto **SessionOption** que você cria usando o cmdlet New-WSManSessionOption.</span><span class="sxs-lookup"><span data-stu-id="991c0-196">Enter a **SessionOption** object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="991c0-197">Para obter mais informações sobre as opções disponíveis, digite `Get-Help New-WSManSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="991c0-197">For more information about the options that are available, type `Get-Help New-WSManSessionOption`.</span></span>

```yaml
Type: Microsoft.WSMan.Management.SessionOption
Parameter Sets: (All)
Aliases: so

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="991c0-198">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="991c0-198">-UseSSL</span></span>
<span data-ttu-id="991c0-199">Especifica que o protocolo de protocolo SSL (SSL) é usado para estabelecer uma conexão com o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="991c0-199">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="991c0-200">Por padrão, SSL não é usado.</span><span class="sxs-lookup"><span data-stu-id="991c0-200">By default, SSL is not used.</span></span>

<span data-ttu-id="991c0-201">O WS-Management criptografa todo o conteúdo do Windows PowerShell que é transmitido pela rede.</span><span class="sxs-lookup"><span data-stu-id="991c0-201">WS-Management encrypts all the Windows PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="991c0-202">O parâmetro *UseSSL* permite especificar a proteção adicional do HTTPS em vez de http.</span><span class="sxs-lookup"><span data-stu-id="991c0-202">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="991c0-203">Se o SSL não estiver disponível na porta que é usada para a conexão e você especificar esse parâmetro, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="991c0-203">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName
Aliases: ssl

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="991c0-204">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="991c0-204">CommonParameters</span></span>
<span data-ttu-id="991c0-205">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="991c0-205">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="991c0-206">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="991c0-206">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="991c0-207">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="991c0-207">INPUTS</span></span>

### <span data-ttu-id="991c0-208">Nenhum</span><span class="sxs-lookup"><span data-stu-id="991c0-208">None</span></span>
<span data-ttu-id="991c0-209">Esse cmdlet não aceita nenhuma entrada.</span><span class="sxs-lookup"><span data-stu-id="991c0-209">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="991c0-210">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="991c0-210">OUTPUTS</span></span>

### <span data-ttu-id="991c0-211">Nenhum</span><span class="sxs-lookup"><span data-stu-id="991c0-211">None</span></span>
<span data-ttu-id="991c0-212">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="991c0-212">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="991c0-213">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="991c0-213">NOTES</span></span>

* <span data-ttu-id="991c0-214">O cmdlet Remove-WmiObject, um cmdlet do Windows Management Instrumentation (WMI), é semelhante.</span><span class="sxs-lookup"><span data-stu-id="991c0-214">The Remove-WmiObject cmdlet, a Windows Management Instrumentation (WMI) cmdlet, is similar.</span></span> <span data-ttu-id="991c0-215">**Remove-WmiObject** usa a camada de conexão/transporte DCOM para criar ou atualizar instâncias do WMI.</span><span class="sxs-lookup"><span data-stu-id="991c0-215">**Remove-WmiObject** uses the DCOM connection/transport layer to create or update WMI instances.</span></span>

*

## <span data-ttu-id="991c0-216">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="991c0-216">RELATED LINKS</span></span>

[<span data-ttu-id="991c0-217">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="991c0-217">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="991c0-218">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="991c0-218">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="991c0-219">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="991c0-219">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="991c0-220">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="991c0-220">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="991c0-221">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="991c0-221">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="991c0-222">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="991c0-222">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="991c0-223">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="991c0-223">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="991c0-224">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="991c0-224">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="991c0-225">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="991c0-225">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="991c0-226">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="991c0-226">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="991c0-227">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="991c0-227">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="991c0-228">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="991c0-228">Test-WSMan</span></span>](Test-WSMan.md)
