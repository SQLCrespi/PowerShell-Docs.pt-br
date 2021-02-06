---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/remove-wsmaninstance?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WSManInstance
ms.openlocfilehash: 4d1273fe1ed643f8d45b627db9863b75212b6b24
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598017"
---
# <span data-ttu-id="aa6b4-102">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="aa6b4-102">Remove-WSManInstance</span></span>

## <span data-ttu-id="aa6b4-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="aa6b4-103">SYNOPSIS</span></span>
<span data-ttu-id="aa6b4-104">Exclui uma instância do recurso de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-104">Deletes a management resource instance.</span></span>

## <span data-ttu-id="aa6b4-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="aa6b4-105">SYNTAX</span></span>

### <span data-ttu-id="aa6b4-106">ComputerName (padrão)</span><span class="sxs-lookup"><span data-stu-id="aa6b4-106">ComputerName (Default)</span></span>

```
Remove-WSManInstance [-ApplicationName <String>] [-ComputerName <String>] [-OptionSet <Hashtable>]
 [-Port <Int32>] [-ResourceURI] <Uri> [-SelectorSet] <Hashtable> [-SessionOption <SessionOption>] [-UseSSL]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="aa6b4-107">URI</span><span class="sxs-lookup"><span data-stu-id="aa6b4-107">URI</span></span>

```
Remove-WSManInstance [-ConnectionURI <Uri>] [-OptionSet <Hashtable>] [-ResourceURI] <Uri>
 [-SelectorSet] <Hashtable> [-SessionOption <SessionOption>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

## <span data-ttu-id="aa6b4-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="aa6b4-108">DESCRIPTION</span></span>

<span data-ttu-id="aa6b4-109">O cmdlet **Remove-WSManInstance** exclui uma instância de um recurso de gerenciamento especificado nos parâmetros *ResourceURI* e *SelectorSet* .</span><span class="sxs-lookup"><span data-stu-id="aa6b4-109">The **Remove-WSManInstance** cmdlet deletes an instance of a management resource that is specified in the *ResourceURI* and *SelectorSet* parameters.</span></span>

<span data-ttu-id="aa6b4-110">Esse cmdlet usa a camada de transporte/conexão do WinRM para excluir a instância do recurso de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-110">This cmdlet uses the WinRM connection/transport layer to delete the management resource instance.</span></span>

## <span data-ttu-id="aa6b4-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="aa6b4-111">EXAMPLES</span></span>

### <span data-ttu-id="aa6b4-112">Exemplo 1: excluir um ouvinte</span><span class="sxs-lookup"><span data-stu-id="aa6b4-112">Example 1: Delete a listener</span></span>

```
PS C:\> Remove-WSManInstance -ResourceUri winrm/config/Listener -SelectorSet Address=test.fabrikam.com;Transport=http
```

<span data-ttu-id="aa6b4-113">Esse comando exclui o WS-Management ouvinte HTTP em um computador.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-113">This command deletes the WS-Management HTTP listener on a computer.</span></span>

## <span data-ttu-id="aa6b4-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="aa6b4-114">PARAMETERS</span></span>

### <span data-ttu-id="aa6b4-115">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="aa6b4-115">-ApplicationName</span></span>

<span data-ttu-id="aa6b4-116">Especifica o nome do aplicativo na conexão.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-116">Specifies the application name in the connection.</span></span>
<span data-ttu-id="aa6b4-117">O valor padrão do parâmetro *ApplicationName* é WSMan.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-117">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="aa6b4-118">O identificador completo para o ponto de extremidade remoto é no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="aa6b4-118">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="aa6b4-119">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="aa6b4-119">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="aa6b4-120">Por exemplo: `http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="aa6b4-120">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="aa6b4-121">Os Serviços de Informações da Internet (IIS), que hospedam a sessão, encaminham solicitações com esse ponto de extremidade para o aplicativo especificado.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-121">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="aa6b4-122">Essa configuração padrão de WSMAN é apropriada para a maioria dos usos.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-122">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="aa6b4-123">Esse parâmetro é projetado para ser usado se muitos computadores estabelecerem conexões remotas com um computador que esteja executando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-123">This parameter is designed to be used if many computers establish remote connections to one computer that is running PowerShell.</span></span>
<span data-ttu-id="aa6b4-124">Nesse caso, o IIS hospeda o Web Services for Management (WS-Management) para ter eficiência.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-124">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

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

### <span data-ttu-id="aa6b4-125">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="aa6b4-125">-Authentication</span></span>

<span data-ttu-id="aa6b4-126">Especifica o mecanismo de autenticação a ser usado no servidor.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-126">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="aa6b4-127">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="aa6b4-127">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="aa6b4-128">Básica.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-128">Basic.</span></span>
<span data-ttu-id="aa6b4-129">É um esquema no qual o nome de usuário e senha são enviados em texto não criptografado para o servidor ou proxy.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-129">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="aa6b4-130">Padrão.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-130">Default.</span></span>
<span data-ttu-id="aa6b4-131">Utiliza o método de autenticação implementado pelo protocolo WS-Management.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-131">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="aa6b4-132">Este é o padrão.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-132">This is the default.</span></span>
- <span data-ttu-id="aa6b4-133">Digest.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-133">Digest.</span></span>
<span data-ttu-id="aa6b4-134">É um esquema de desafio/resposta que utiliza uma cadeia de caracteres de dados do servidor especificada para o desafio.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-134">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="aa6b4-135">Kerberos.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-135">Kerberos.</span></span>
<span data-ttu-id="aa6b4-136">O computador cliente e o servidor autenticam mutuamente utilizando certificados Kerberos.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-136">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="aa6b4-137">Negotiate.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-137">Negotiate.</span></span>
<span data-ttu-id="aa6b4-138">É um esquema de desafio/resposta que negocia com o servidor ou proxy para determinar o esquema a ser utilizado para autenticação.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-138">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="aa6b4-139">Por exemplo, esse valor de parâmetro permite que a negociação determine se o protocolo Kerberos ou NTLM é usado.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-139">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="aa6b4-140">CredSSP.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-140">CredSSP.</span></span>
<span data-ttu-id="aa6b4-141">Use a autenticação do Credential Security Support Provider (CredSSP), que permite que o usuário delegue as credenciais.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-141">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="aa6b4-142">Esta opção foi criada para os comandos executados em um computador remoto, mas coletam dados ou executam comandos adicionais em outros computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-142">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="aa6b4-143">Cuidado: o CredSSP Delega as credenciais do usuário do computador local para um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-143">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="aa6b4-144">Essa prática aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-144">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="aa6b4-145">Se o computador remoto estiver comprometido, no momento em que as credenciais forem passadas a ele essas credenciais poderão ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-145">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="aa6b4-146">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="aa6b4-146">-CertificateThumbprint</span></span>

<span data-ttu-id="aa6b4-147">Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa ação.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-147">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="aa6b4-148">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-148">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="aa6b4-149">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-149">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="aa6b4-150">Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-150">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="aa6b4-151">Para obter uma impressão digital do certificado, use o comando Get-Item ou Get-ChildItem na unidade certificado do PowerShell:.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-151">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="aa6b4-152">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="aa6b4-152">-ComputerName</span></span>

<span data-ttu-id="aa6b4-153">Especifica o computador no qual executar a operação de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-153">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="aa6b4-154">O valor pode ser um nome de domínio totalmente qualificado, um nome NetBIOS ou um endereço IP.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-154">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="aa6b4-155">Utilize o nome do computador local, o localhost ou um ponto (.) para especificar o computador local.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-155">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="aa6b4-156">O computador local é o padrão.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-156">The local computer is the default.</span></span>
<span data-ttu-id="aa6b4-157">Quando o computador remoto está em um domínio diferente do usuário, deve-se usar um nome de domínio totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-157">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="aa6b4-158">É possível redirecionar um valor desse parâmetro para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-158">You can pipe a value for this parameter to the cmdlet.</span></span>

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

### <span data-ttu-id="aa6b4-159">-Conexãouri</span><span class="sxs-lookup"><span data-stu-id="aa6b4-159">-ConnectionURI</span></span>

<span data-ttu-id="aa6b4-160">Especifica o ponto de extremidade de conexão.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-160">Specifies the connection endpoint.</span></span>
<span data-ttu-id="aa6b4-161">O formato dessa cadeia de caracteres é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="aa6b4-161">The format of this string is as follows:</span></span>

<span data-ttu-id="aa6b4-162">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="aa6b4-162">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="aa6b4-163">A cadeia de caracteres a seguir é um valor formatado corretamente para este parâmetro:</span><span class="sxs-lookup"><span data-stu-id="aa6b4-163">The following string is a correctly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="aa6b4-164">O URI deve ser totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-164">The URI must be fully qualified.</span></span>

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

### <span data-ttu-id="aa6b4-165">-Credential</span><span class="sxs-lookup"><span data-stu-id="aa6b4-165">-Credential</span></span>

<span data-ttu-id="aa6b4-166">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-166">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="aa6b4-167">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-167">The default is the current user.</span></span>
<span data-ttu-id="aa6b4-168">Digite um nome de usuário, como User01, Domínio01 \ Usuário01 ou User@Domain.com .</span><span class="sxs-lookup"><span data-stu-id="aa6b4-168">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="aa6b4-169">Ou insira um objeto **PSCredential** , como um retornado pelo cmdlet Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-169">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="aa6b4-170">Quando você digita um nome de usuário, esse cmdlet solicita uma senha.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-170">When you type a user name, this cmdlet prompts you for a password.</span></span>

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

### <span data-ttu-id="aa6b4-171">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="aa6b4-171">-OptionSet</span></span>

<span data-ttu-id="aa6b4-172">Especifica um conjunto de opções para um serviço para modificar ou refinar a natureza da solicitação.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-172">Specifies a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="aa6b4-173">Elas se assemelham a opções usadas em shells de linha de comando porque são específicas de serviço.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-173">These resemble switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="aa6b4-174">Qualquer número de opções pode ser especificado.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-174">Any number of options can be specified.</span></span>

<span data-ttu-id="aa6b4-175">O exemplo a seguir demonstra a sintaxe que passa os valores 1, 2 e 3 para os parâmetros a, b e c:</span><span class="sxs-lookup"><span data-stu-id="aa6b4-175">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

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

### <span data-ttu-id="aa6b4-176">-Port</span><span class="sxs-lookup"><span data-stu-id="aa6b4-176">-Port</span></span>

<span data-ttu-id="aa6b4-177">Especifica a porta a ser usada quando o cliente se conecta ao serviço WinRM.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-177">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="aa6b4-178">Quando o transporte é HTTP, a porta padrão é 80.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-178">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="aa6b4-179">Quando o transporte é HTTPS, a porta padrão é 443.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-179">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="aa6b4-180">Quando você usa HTTPS como o transporte, o valor do parâmetro *ComputerName* deve corresponder ao CN (nome comum) do certificado do servidor.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-180">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="aa6b4-181">No entanto, se o parâmetro *SkipCNCheck* for especificado como parte do parâmetro *SessionOption* , o nome comum do certificado do servidor não precisará corresponder ao nome do host do servidor.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-181">However, if the *SkipCNCheck* parameter is specified as part of the *SessionOption* parameter, the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="aa6b4-182">O parâmetro *SkipCNCheck* deve ser usado somente para computadores confiáveis.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-182">The *SkipCNCheck* parameter should be used only for trusted computers.</span></span>

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

### <span data-ttu-id="aa6b4-183">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="aa6b4-183">-ResourceURI</span></span>

<span data-ttu-id="aa6b4-184">Especifica o URI da classe ou instância de recurso.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-184">Specifies the URI of the resource class or instance.</span></span>
<span data-ttu-id="aa6b4-185">O URI é utilizado para identificar um tipo específico de recurso, como discos ou processos em um computador.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-185">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="aa6b4-186">Um URI consiste em um prefixo e um caminho de um recurso.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-186">A URI consists of a prefix and a path of a resource.</span></span>
<span data-ttu-id="aa6b4-187">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="aa6b4-187">For example:</span></span>

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

### <span data-ttu-id="aa6b4-188">-SelectorSet</span><span class="sxs-lookup"><span data-stu-id="aa6b4-188">-SelectorSet</span></span>

<span data-ttu-id="aa6b4-189">Especifica um conjunto de pares de valor que são utilizados para selecionar instâncias do recurso de gerenciamento específico.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-189">Specifies a set of value pairs that are used to select particular management resource instances.</span></span>
<span data-ttu-id="aa6b4-190">O parâmetro *SelectorSet* é usado quando há mais de uma instância do recurso.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-190">The *SelectorSet* parameter is used when more than one instance of the resource exists.</span></span>
<span data-ttu-id="aa6b4-191">O valor de *SelectorSet* deve ser uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-191">The value of *SelectorSet* must be a hash table.</span></span>

<span data-ttu-id="aa6b4-192">O exemplo a seguir mostra como inserir um valor para esse parâmetro:</span><span class="sxs-lookup"><span data-stu-id="aa6b4-192">The following example shows how to enter a value for this parameter:</span></span>

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

### <span data-ttu-id="aa6b4-193">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="aa6b4-193">-SessionOption</span></span>

<span data-ttu-id="aa6b4-194">Especifica as opções estendidas para a sessão de WS-Management.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-194">Specifies extended options for the WS-Management session.</span></span>
<span data-ttu-id="aa6b4-195">Insira um objeto **SessionOption** que você cria usando o cmdlet New-WSManSessionOption.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-195">Enter a **SessionOption** object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="aa6b4-196">Para obter mais informações sobre as opções disponíveis, digite `Get-Help New-WSManSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="aa6b4-196">For more information about the options that are available, type `Get-Help New-WSManSessionOption`.</span></span>

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

### <span data-ttu-id="aa6b4-197">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="aa6b4-197">-UseSSL</span></span>

<span data-ttu-id="aa6b4-198">Especifica que o protocolo de protocolo SSL (SSL) é usado para estabelecer uma conexão com o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-198">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="aa6b4-199">Por padrão, SSL não é usado.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-199">By default, SSL is not used.</span></span>

<span data-ttu-id="aa6b4-200">WS-Management criptografa todo o conteúdo do PowerShell que é transmitido pela rede.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-200">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="aa6b4-201">O parâmetro *UseSSL* permite especificar a proteção adicional do HTTPS em vez de http.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-201">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="aa6b4-202">Se o SSL não estiver disponível na porta que é usada para a conexão e você especificar esse parâmetro, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-202">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="aa6b4-203">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="aa6b4-203">CommonParameters</span></span>

<span data-ttu-id="aa6b4-204">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-204">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="aa6b4-205">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="aa6b4-205">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="aa6b4-206">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="aa6b4-206">INPUTS</span></span>

### <span data-ttu-id="aa6b4-207">Nenhum</span><span class="sxs-lookup"><span data-stu-id="aa6b4-207">None</span></span>

<span data-ttu-id="aa6b4-208">Esse cmdlet não aceita nenhuma entrada.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-208">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="aa6b4-209">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="aa6b4-209">OUTPUTS</span></span>

### <span data-ttu-id="aa6b4-210">Nenhum</span><span class="sxs-lookup"><span data-stu-id="aa6b4-210">None</span></span>

<span data-ttu-id="aa6b4-211">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-211">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="aa6b4-212">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="aa6b4-212">NOTES</span></span>

* <span data-ttu-id="aa6b4-213">O cmdlet Remove-WmiObject, um cmdlet do Windows Management Instrumentation (WMI), é semelhante.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-213">The Remove-WmiObject cmdlet, a Windows Management Instrumentation (WMI) cmdlet, is similar.</span></span> <span data-ttu-id="aa6b4-214">**Remove-WmiObject** usa a camada de conexão/transporte DCOM para criar ou atualizar instâncias do WMI.</span><span class="sxs-lookup"><span data-stu-id="aa6b4-214">**Remove-WmiObject** uses the DCOM connection/transport layer to create or update WMI instances.</span></span>

*

## <span data-ttu-id="aa6b4-215">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="aa6b4-215">RELATED LINKS</span></span>

[<span data-ttu-id="aa6b4-216">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="aa6b4-216">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="aa6b4-217">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="aa6b4-217">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="aa6b4-218">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="aa6b4-218">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="aa6b4-219">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="aa6b4-219">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="aa6b4-220">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="aa6b4-220">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="aa6b4-221">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="aa6b4-221">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="aa6b4-222">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="aa6b4-222">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="aa6b4-223">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="aa6b4-223">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="aa6b4-224">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="aa6b4-224">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="aa6b4-225">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="aa6b4-225">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="aa6b4-226">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="aa6b4-226">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="aa6b4-227">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="aa6b4-227">Test-WSMan</span></span>](Test-WSMan.md)

