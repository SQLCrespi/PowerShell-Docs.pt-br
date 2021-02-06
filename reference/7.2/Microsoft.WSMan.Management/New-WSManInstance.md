---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 03/31/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/new-wsmaninstance?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WSManInstance
ms.openlocfilehash: dd0343e9b6014e079c322309b699874683bacd6a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598811"
---
# <span data-ttu-id="2a2e1-102">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="2a2e1-102">New-WSManInstance</span></span>

## <span data-ttu-id="2a2e1-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="2a2e1-103">SYNOPSIS</span></span>
<span data-ttu-id="2a2e1-104">Cria uma nova instância de um recurso de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-104">Creates a new instance of a management resource.</span></span>

## <span data-ttu-id="2a2e1-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2a2e1-105">SYNTAX</span></span>

### <span data-ttu-id="2a2e1-106">ComputerName (padrão)</span><span class="sxs-lookup"><span data-stu-id="2a2e1-106">ComputerName (Default)</span></span>

```
New-WSManInstance [-ApplicationName <String>] [-ComputerName <String>] [-FilePath <String>]
 [-OptionSet <Hashtable>] [-Port <Int32>] [-ResourceURI] <Uri> [-SelectorSet] <Hashtable>
 [-SessionOption <SessionOption>] [-UseSSL] [-ValueSet <Hashtable>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="2a2e1-107">URI</span><span class="sxs-lookup"><span data-stu-id="2a2e1-107">URI</span></span>

```
New-WSManInstance [-ConnectionURI <Uri>] [-FilePath <String>] [-OptionSet <Hashtable>] [-ResourceURI] <Uri>
 [-SelectorSet] <Hashtable> [-SessionOption <SessionOption>] [-ValueSet <Hashtable>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="2a2e1-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2a2e1-108">DESCRIPTION</span></span>

<span data-ttu-id="2a2e1-109">O `New-WSManInstance` cmdlet cria uma nova instância de um recurso de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-109">The `New-WSManInstance` cmdlet creates a new instance of a management resource.</span></span> <span data-ttu-id="2a2e1-110">Ele usa um URI de recurso e um conjunto de valores ou arquivo de entrada para criar a nova instância do recurso de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-110">It uses a resource URI and a value set or input file to create the new instance of the management resource.</span></span>

<span data-ttu-id="2a2e1-111">Esse cmdlet usa a camada de transporte/conexão do WinRM para criar a instância do recurso de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-111">This cmdlet uses the WinRM connection/transport layer to create the management resource instance.</span></span>

## <span data-ttu-id="2a2e1-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="2a2e1-112">EXAMPLES</span></span>

### <span data-ttu-id="2a2e1-113">Exemplo 1: criar um ouvinte HTTPS</span><span class="sxs-lookup"><span data-stu-id="2a2e1-113">Example 1: Create a HTTPS listener</span></span>

<span data-ttu-id="2a2e1-114">Este comando cria uma instância de um ouvinte HTTPS do WS-Management em todos os endereços IP.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-114">This command creates an instance of a WS-Management HTTPS listener on all IP addresses.</span></span>

```powershell
New-WSManInstance winrm/config/Listener -SelectorSet @{Transport='HTTPS'; Address='*'} -ValueSet @{Hostname="HOST";CertificateThumbprint="XXXXXXXXXX"}
```

## <span data-ttu-id="2a2e1-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2a2e1-115">PARAMETERS</span></span>

### <span data-ttu-id="2a2e1-116">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="2a2e1-116">-ApplicationName</span></span>

<span data-ttu-id="2a2e1-117">Especifica o nome do aplicativo na conexão.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-117">Specifies the application name in the connection.</span></span> <span data-ttu-id="2a2e1-118">O valor padrão do parâmetro **ApplicationName** é **WSMan**.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-118">The default value of the **ApplicationName** parameter is **WSMAN**.</span></span> <span data-ttu-id="2a2e1-119">O identificador completo para o ponto de extremidade remoto é no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="2a2e1-119">The complete identifier for the remote endpoint is in the following format:</span></span>

`<transport>://<server>:<port>/<ApplicationName>`

<span data-ttu-id="2a2e1-120">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2a2e1-120">For example:</span></span>

`http://server01:8080/WSMAN`

<span data-ttu-id="2a2e1-121">Os Serviços de Informações da Internet (IIS), que hospedam a sessão, encaminham solicitações com esse ponto de extremidade para o aplicativo especificado.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-121">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span> <span data-ttu-id="2a2e1-122">Essa configuração padrão de **WSMan** é apropriada para a maioria dos usos.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-122">This default setting of **WSMAN** is appropriate for most uses.</span></span> <span data-ttu-id="2a2e1-123">Esse parâmetro é projetado para ser utilizado quando diversos computadores estabelecem conexões remotas com um computador que esteja executando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-123">This parameter is designed to be used when numerous computers establish remote connections to one computer that is running Windows PowerShell.</span></span> <span data-ttu-id="2a2e1-124">Nesse caso, o IIS hospeda o Web Services for Management (WS-Management) para ter eficiência.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-124">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: Wsman
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2a2e1-125">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="2a2e1-125">-Authentication</span></span>

<span data-ttu-id="2a2e1-126">Especifica o mecanismo de autenticação a ser usado no servidor.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-126">Specifies the authentication mechanism to be used at the server.</span></span> <span data-ttu-id="2a2e1-127">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="2a2e1-127">Possible values are:</span></span>

- <span data-ttu-id="2a2e1-128">Básico: básico é um esquema no qual o nome de usuário e a senha são enviados em texto não criptografado para o servidor ou proxy.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-128">Basic: Basic is a scheme in which the username and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="2a2e1-129">Padrão: Use o método de autenticação implementado pelo protocolo WS-Management.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-129">Default: Use the authentication method implemented by the WS-Management protocol.</span></span> <span data-ttu-id="2a2e1-130">Este é o padrão.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-130">This is the default.</span></span>
- <span data-ttu-id="2a2e1-131">Resumo: o resumo é um esquema de desafio/resposta que usa uma cadeia de caracteres de dados especificada pelo servidor para o desafio.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-131">Digest: Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="2a2e1-132">Kerberos: o computador cliente e o servidor se autenticam mutuamente usando certificados Kerberos.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-132">Kerberos: The client computer and the server mutually authenticate using Kerberos certificates.</span></span>
- <span data-ttu-id="2a2e1-133">Negotiate: Negotiate é um esquema de desafio/resposta que negocia com o servidor ou proxy para determinar o esquema a ser usado para autenticação.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-133">Negotiate: Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span> <span data-ttu-id="2a2e1-134">Por exemplo, esse valor de parâmetro permite uma negociação para determinar se o protocolo Kerberos ou NTLM será utilizado.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-134">For example, this parameter value allows negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="2a2e1-135">CredSSP: Use a autenticação do Credential Security Support Provider (CredSSP), que permite ao usuário delegar credenciais.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-135">CredSSP: Use Credential Security Support Provider (CredSSP) authentication, which allows the user to delegate credentials.</span></span> <span data-ttu-id="2a2e1-136">Esta opção foi criada para os comandos executados em um computador remoto, mas coletam dados ou executam comandos adicionais em outros computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-136">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

> [!CAUTION]
> <span data-ttu-id="2a2e1-137">O CredSSP delega as credenciais do usuário do computador local para um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-137">CredSSP delegates the user's credentials from the local computer to a remote computer.</span></span> <span data-ttu-id="2a2e1-138">Essa prática aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-138">This practice increases the security risk of the remote operation.</span></span> <span data-ttu-id="2a2e1-139">Se o computador remoto estiver comprometido, no momento em que as credenciais forem passadas a ele essas credenciais poderão ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-139">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="2a2e1-140">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="2a2e1-140">-CertificateThumbprint</span></span>

<span data-ttu-id="2a2e1-141">Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa ação.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-141">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="2a2e1-142">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-142">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="2a2e1-143">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-143">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="2a2e1-144">Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-144">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="2a2e1-145">Para obter uma impressão digital do certificado, use o `Get-Item` `Get-ChildItem` comando ou na unidade certificado do PowerShell:.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-145">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="2a2e1-146">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="2a2e1-146">-ComputerName</span></span>

<span data-ttu-id="2a2e1-147">Especifica o computador no qual se deseja executar a operação de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-147">Specifies the computer against which you want to run the management operation.</span></span> <span data-ttu-id="2a2e1-148">O valor pode ser um nome de domínio totalmente qualificado, um nome NetBIOS ou um endereço IP.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-148">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span> <span data-ttu-id="2a2e1-149">Use o nome do computador local, use localhost ou use um ponto ( `.` ) para especificar o computador local.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-149">Use the local computer name, use localhost, or use a dot (`.`) to specify the local computer.</span></span> <span data-ttu-id="2a2e1-150">O computador local é o padrão.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-150">The local computer is the default.</span></span> <span data-ttu-id="2a2e1-151">Quando o computador remoto está em um domínio diferente do usuário, deve-se usar um nome de domínio totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-151">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span> <span data-ttu-id="2a2e1-152">É possível redirecionar um valor desse parâmetro para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-152">You can pipe a value for this parameter to the cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases: cn

Required: False
Position: Named
Default value: Localhost
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2a2e1-153">-Conexãouri</span><span class="sxs-lookup"><span data-stu-id="2a2e1-153">-ConnectionURI</span></span>

<span data-ttu-id="2a2e1-154">Especifica o ponto de extremidade de conexão.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-154">Specifies the connection endpoint.</span></span>
<span data-ttu-id="2a2e1-155">O formato dessa cadeia de caracteres é:</span><span class="sxs-lookup"><span data-stu-id="2a2e1-155">The format of this string is:</span></span>

`<Transport>://<Server>:<Port>/<ApplicationName>`

<span data-ttu-id="2a2e1-156">A seguinte cadeia de caracteres é um valor formatado corretamente para este parâmetro:</span><span class="sxs-lookup"><span data-stu-id="2a2e1-156">The following string is a properly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="2a2e1-157">O URI deve ser totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-157">The URI must be fully qualified.</span></span>

```yaml
Type: System.Uri
Parameter Sets: URI
Aliases: CURI, CU

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2a2e1-158">-Credential</span><span class="sxs-lookup"><span data-stu-id="2a2e1-158">-Credential</span></span>

<span data-ttu-id="2a2e1-159">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-159">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="2a2e1-160">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-160">The default is the current user.</span></span> <span data-ttu-id="2a2e1-161">Digite um nome de usuário, como "User01", "Domínio01 \ Usuário01" ou " User@Domain.com ".</span><span class="sxs-lookup"><span data-stu-id="2a2e1-161">Type a user name, such as "User01", "Domain01\User01", or "User@Domain.com".</span></span> <span data-ttu-id="2a2e1-162">Ou insira um objeto PSCredential, como um retornado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-162">Or, enter a PSCredential object, such as one returned by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="2a2e1-163">Quando você digitar um nome de usuário, uma senha será solicitada.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-163">When you type a user name, you will be prompted for a password.</span></span>

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

### <span data-ttu-id="2a2e1-164">-FilePath</span><span class="sxs-lookup"><span data-stu-id="2a2e1-164">-FilePath</span></span>

<span data-ttu-id="2a2e1-165">Especifica o caminho de um arquivo usado para criar um recurso de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-165">Specifies the path of a file that is used to create a management resource.</span></span> <span data-ttu-id="2a2e1-166">Você especifica o recurso de gerenciamento usando o parâmetro **ResourceURI** e o parâmetro **SelectorSet** .</span><span class="sxs-lookup"><span data-stu-id="2a2e1-166">You specify the management resource using the **ResourceURI** parameter and the **SelectorSet** parameter .</span></span> <span data-ttu-id="2a2e1-167">Por exemplo, o comando a seguir usa o parâmetro **File** :</span><span class="sxs-lookup"><span data-stu-id="2a2e1-167">For example, the following command uses the **File** parameter:</span></span>

`Invoke-WSManAction -Action stopservice -ResourceUri wmi/cimv2/Win32_Service -SelectorSet @{Name="spooler"} -File c:\input.xml -Authentication Default`

<span data-ttu-id="2a2e1-168">Esse comando chama o método **StopService** no serviço de spooler usando a entrada de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-168">This command calls the **StopService** method on the Spooler service using input from a file.</span></span> <span data-ttu-id="2a2e1-169">O arquivo, `Input.xml` , contém o seguinte conteúdo:</span><span class="sxs-lookup"><span data-stu-id="2a2e1-169">The file, `Input.xml`, contains the following content:</span></span>

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Path

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2a2e1-170">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="2a2e1-170">-OptionSet</span></span>

<span data-ttu-id="2a2e1-171">Passa um conjunto de opções para um serviço para modificar ou refinar a natureza da solicitação.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-171">Passes a set of switches to a service to modify or refine the nature of the request.</span></span> <span data-ttu-id="2a2e1-172">Elas são semelhantes às opções usadas nos shells de linha de comando porque são específicas para o serviço.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-172">These are similar to switches used in command-line shells because they are service specific.</span></span> <span data-ttu-id="2a2e1-173">Qualquer número de opções pode ser especificado.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-173">Any number of options can be specified.</span></span>

<span data-ttu-id="2a2e1-174">O exemplo a seguir demonstra a sintaxe que passa os valores 1, 2 e 3 para os parâmetros a, b e c:</span><span class="sxs-lookup"><span data-stu-id="2a2e1-174">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

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

### <span data-ttu-id="2a2e1-175">-Port</span><span class="sxs-lookup"><span data-stu-id="2a2e1-175">-Port</span></span>

<span data-ttu-id="2a2e1-176">Especifica a porta a ser usada quando o cliente se conecta ao serviço WinRM.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-176">Specifies the port to use when the client connects to the WinRM service.</span></span> <span data-ttu-id="2a2e1-177">Quando o transporte é HTTP, a porta padrão é 80.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-177">When the transport is HTTP, the default port is 80.</span></span> <span data-ttu-id="2a2e1-178">Quando o transporte é HTTPS, a porta padrão é 443.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-178">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="2a2e1-179">Quando você usa HTTPS como o transporte, o valor do parâmetro **ComputerName** deve corresponder ao CN (nome comum) do certificado do servidor.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-179">When you use HTTPS as the transport, the value of the **ComputerName** parameter must match the server's certificate common name (CN).</span></span> <span data-ttu-id="2a2e1-180">No entanto, se o parâmetro **SkipCNCheck** for especificado como parte do parâmetro **SessionOption** , o nome comum do certificado do servidor não precisará corresponder ao nome do host do servidor.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-180">However, if the **SkipCNCheck** parameter is specified as part of the **SessionOption** parameter, the certificate common name of the server does not have to match the host name of the server.</span></span> <span data-ttu-id="2a2e1-181">O parâmetro **SkipCNCheck** deve ser usado somente para computadores confiáveis.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-181">The **SkipCNCheck** parameter should be used only for trusted computers.</span></span>

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

### <span data-ttu-id="2a2e1-182">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="2a2e1-182">-ResourceURI</span></span>

<span data-ttu-id="2a2e1-183">Contém o Uniform Resource Identifier (URI) da instância ou classe do recurso.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-183">Contains the Uniform Resource Identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="2a2e1-184">O URI é utilizado para identificar um tipo específico de recurso, como discos ou processos em um computador.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-184">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="2a2e1-185">Um URI consiste em um prefixo e um caminho para um recurso.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-185">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="2a2e1-186">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2a2e1-186">For example:</span></span>

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

### <span data-ttu-id="2a2e1-187">-SelectorSet</span><span class="sxs-lookup"><span data-stu-id="2a2e1-187">-SelectorSet</span></span>

<span data-ttu-id="2a2e1-188">Especifica um conjunto de pares de valor que são utilizados para selecionar instâncias do recurso de gerenciamento específico.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-188">Specifies a set of value pairs that are used to select particular management resource instances.</span></span> <span data-ttu-id="2a2e1-189">O parâmetro **SelectorSet** é usado quando há mais de uma instância do recurso.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-189">The **SelectorSet** parameter is used when more than one instance of the resource exists.</span></span> <span data-ttu-id="2a2e1-190">O valor do parâmetro **SelectorSet** deve ser uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-190">The value of the **SelectorSet** parameter must be a hash table.</span></span>

<span data-ttu-id="2a2e1-191">O exemplo a seguir mostra como inserir um valor para esse parâmetro:</span><span class="sxs-lookup"><span data-stu-id="2a2e1-191">The following example shows how to enter a value for this parameter:</span></span>

`-SelectorSet @{Name="WinRM";ID="yyy"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="2a2e1-192">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="2a2e1-192">-SessionOption</span></span>

<span data-ttu-id="2a2e1-193">Define um conjunto de opções estendidas para a sessão do WS-Management.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-193">Defines a set of extended options for the WS-Management session.</span></span> <span data-ttu-id="2a2e1-194">Insira um objeto **SessionOption** que você cria usando o `New-WSManSessionOption` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-194">Enter a **SessionOption** object that you create using the `New-WSManSessionOption` cmdlet.</span></span> <span data-ttu-id="2a2e1-195">Para obter mais informações sobre as opções disponíveis, consulte `New-WSManSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="2a2e1-195">For more information about the options that are available, see `New-WSManSessionOption`.</span></span>

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

### <span data-ttu-id="2a2e1-196">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="2a2e1-196">-UseSSL</span></span>

<span data-ttu-id="2a2e1-197">Especifica que o protocolo Secure Sockets Layer (SSL) deve ser utilizado para estabelecer uma conexão com o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-197">Specifies that the Secure Sockets Layer (SSL) protocol should be used to establish a connection to the remote computer.</span></span> <span data-ttu-id="2a2e1-198">Por padrão, SSL não é usado.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-198">By default, SSL is not used.</span></span>

<span data-ttu-id="2a2e1-199">O WS-Management criptografa todo o conteúdo do Windows PowerShell que é transmitido pela rede.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-199">WS-Management encrypts all the Windows PowerShell content that is transmitted over the network.</span></span> <span data-ttu-id="2a2e1-200">O parâmetro **UseSSL** permite especificar a proteção adicional do HTTPS em vez de http.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-200">The **UseSSL** parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span> <span data-ttu-id="2a2e1-201">Se o SSL não estiver disponível na porta utilizada para a conexão e o parâmetro for especificado, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-201">If SSL is not available on the port that is used for the connection and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="2a2e1-202">-Valorset</span><span class="sxs-lookup"><span data-stu-id="2a2e1-202">-ValueSet</span></span>

<span data-ttu-id="2a2e1-203">Especifica uma tabela de hash que ajuda a modificar um recurso de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-203">Specifies a hash table that helps modify a management resource.</span></span> <span data-ttu-id="2a2e1-204">Você especifica o recurso de gerenciamento usando o parâmetro **ResourceURI** e o parâmetro **SelectorSet** .</span><span class="sxs-lookup"><span data-stu-id="2a2e1-204">You specify the management resource using the **ResourceURI** parameter and the **SelectorSet** parameter.</span></span> <span data-ttu-id="2a2e1-205">O valor do parâmetro **ValueSet** deve ser uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-205">The value of the **ValueSet** parameter must be a hash table.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2a2e1-206">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2a2e1-206">CommonParameters</span></span>

<span data-ttu-id="2a2e1-207">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-207">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2a2e1-208">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="2a2e1-208">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="2a2e1-209">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="2a2e1-209">INPUTS</span></span>

### <span data-ttu-id="2a2e1-210">Nenhum</span><span class="sxs-lookup"><span data-stu-id="2a2e1-210">None</span></span>

<span data-ttu-id="2a2e1-211">Esse cmdlet não aceita nenhuma entrada.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-211">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="2a2e1-212">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="2a2e1-212">OUTPUTS</span></span>

### <span data-ttu-id="2a2e1-213">Nenhum</span><span class="sxs-lookup"><span data-stu-id="2a2e1-213">None</span></span>

<span data-ttu-id="2a2e1-214">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-214">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="2a2e1-215">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="2a2e1-215">NOTES</span></span>

<span data-ttu-id="2a2e1-216">O `Set-WmiInstance` cmdlet, um cmdlet Instrumentação de gerenciamento do Windows (WMI), é semelhante.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-216">The `Set-WmiInstance` cmdlet, a Windows Management Instrumentation (WMI) cmdlet, is similar.</span></span>
<span data-ttu-id="2a2e1-217">`Set-WmiInstance` usa a camada de conexão/transporte DCOM para criar ou atualizar instâncias do WMI.</span><span class="sxs-lookup"><span data-stu-id="2a2e1-217">`Set-WmiInstance` uses the DCOM connection/transport layer to create or update WMI instances.</span></span>

## <span data-ttu-id="2a2e1-218">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="2a2e1-218">RELATED LINKS</span></span>

[<span data-ttu-id="2a2e1-219">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="2a2e1-219">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="2a2e1-220">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="2a2e1-220">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="2a2e1-221">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="2a2e1-221">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="2a2e1-222">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="2a2e1-222">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="2a2e1-223">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="2a2e1-223">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="2a2e1-224">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="2a2e1-224">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="2a2e1-225">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="2a2e1-225">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="2a2e1-226">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="2a2e1-226">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="2a2e1-227">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="2a2e1-227">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="2a2e1-228">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="2a2e1-228">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="2a2e1-229">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="2a2e1-229">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="2a2e1-230">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="2a2e1-230">Test-WSMan</span></span>](Test-WSMan.md)

