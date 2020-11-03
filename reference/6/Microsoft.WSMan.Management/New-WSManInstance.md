---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 03/31/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/new-wsmaninstance?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WSManInstance
ms.openlocfilehash: cab18c513be5427f06165ae0558ad87653d23e35
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93194978"
---
# <span data-ttu-id="f1c51-103">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="f1c51-103">New-WSManInstance</span></span>

## <span data-ttu-id="f1c51-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="f1c51-104">SYNOPSIS</span></span>
<span data-ttu-id="f1c51-105">Cria uma nova instância de um recurso de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="f1c51-105">Creates a new instance of a management resource.</span></span>

## <span data-ttu-id="f1c51-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f1c51-106">SYNTAX</span></span>

### <span data-ttu-id="f1c51-107">ComputerName (padrão)</span><span class="sxs-lookup"><span data-stu-id="f1c51-107">ComputerName (Default)</span></span>

```
New-WSManInstance [-ApplicationName <String>] [-ComputerName <String>] [-FilePath <String>]
 [-OptionSet <Hashtable>] [-Port <Int32>] [-ResourceURI] <Uri> [-SelectorSet] <Hashtable>
 [-SessionOption <SessionOption>] [-UseSSL] [-ValueSet <Hashtable>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="f1c51-108">URI</span><span class="sxs-lookup"><span data-stu-id="f1c51-108">URI</span></span>

```
New-WSManInstance [-ConnectionURI <Uri>] [-FilePath <String>] [-OptionSet <Hashtable>] [-ResourceURI] <Uri>
 [-SelectorSet] <Hashtable> [-SessionOption <SessionOption>] [-ValueSet <Hashtable>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="f1c51-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f1c51-109">DESCRIPTION</span></span>

<span data-ttu-id="f1c51-110">O `New-WSManInstance` cmdlet cria uma nova instância de um recurso de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="f1c51-110">The `New-WSManInstance` cmdlet creates a new instance of a management resource.</span></span> <span data-ttu-id="f1c51-111">Ele usa um URI de recurso e um conjunto de valores ou arquivo de entrada para criar a nova instância do recurso de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="f1c51-111">It uses a resource URI and a value set or input file to create the new instance of the management resource.</span></span>

<span data-ttu-id="f1c51-112">Esse cmdlet usa a camada de transporte/conexão do WinRM para criar a instância do recurso de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="f1c51-112">This cmdlet uses the WinRM connection/transport layer to create the management resource instance.</span></span>

## <span data-ttu-id="f1c51-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="f1c51-113">EXAMPLES</span></span>

### <span data-ttu-id="f1c51-114">Exemplo 1: criar um ouvinte HTTPS</span><span class="sxs-lookup"><span data-stu-id="f1c51-114">Example 1: Create a HTTPS listener</span></span>

<span data-ttu-id="f1c51-115">Este comando cria uma instância de um ouvinte HTTPS do WS-Management em todos os endereços IP.</span><span class="sxs-lookup"><span data-stu-id="f1c51-115">This command creates an instance of a WS-Management HTTPS listener on all IP addresses.</span></span>

```powershell
New-WSManInstance winrm/config/Listener -SelectorSet @{Transport='HTTPS'; Address='*'} -ValueSet @{Hostname="HOST";CertificateThumbprint="XXXXXXXXXX"}
```

## <span data-ttu-id="f1c51-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f1c51-116">PARAMETERS</span></span>

### <span data-ttu-id="f1c51-117">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="f1c51-117">-ApplicationName</span></span>

<span data-ttu-id="f1c51-118">Especifica o nome do aplicativo na conexão.</span><span class="sxs-lookup"><span data-stu-id="f1c51-118">Specifies the application name in the connection.</span></span> <span data-ttu-id="f1c51-119">O valor padrão do parâmetro **ApplicationName** é **WSMan** .</span><span class="sxs-lookup"><span data-stu-id="f1c51-119">The default value of the **ApplicationName** parameter is **WSMAN** .</span></span> <span data-ttu-id="f1c51-120">O identificador completo para o ponto de extremidade remoto é no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="f1c51-120">The complete identifier for the remote endpoint is in the following format:</span></span>

`<transport>://<server>:<port>/<ApplicationName>`

<span data-ttu-id="f1c51-121">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f1c51-121">For example:</span></span>

`http://server01:8080/WSMAN`

<span data-ttu-id="f1c51-122">Os Serviços de Informações da Internet (IIS), que hospedam a sessão, encaminham solicitações com esse ponto de extremidade para o aplicativo especificado.</span><span class="sxs-lookup"><span data-stu-id="f1c51-122">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span> <span data-ttu-id="f1c51-123">Essa configuração padrão de **WSMan** é apropriada para a maioria dos usos.</span><span class="sxs-lookup"><span data-stu-id="f1c51-123">This default setting of **WSMAN** is appropriate for most uses.</span></span> <span data-ttu-id="f1c51-124">Esse parâmetro é projetado para ser utilizado quando diversos computadores estabelecem conexões remotas com um computador que esteja executando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1c51-124">This parameter is designed to be used when numerous computers establish remote connections to one computer that is running Windows PowerShell.</span></span> <span data-ttu-id="f1c51-125">Nesse caso, o IIS hospeda o Web Services for Management (WS-Management) para ter eficiência.</span><span class="sxs-lookup"><span data-stu-id="f1c51-125">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

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

### <span data-ttu-id="f1c51-126">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="f1c51-126">-Authentication</span></span>

<span data-ttu-id="f1c51-127">Especifica o mecanismo de autenticação a ser usado no servidor.</span><span class="sxs-lookup"><span data-stu-id="f1c51-127">Specifies the authentication mechanism to be used at the server.</span></span> <span data-ttu-id="f1c51-128">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="f1c51-128">Possible values are:</span></span>

- <span data-ttu-id="f1c51-129">Básico: básico é um esquema no qual o nome de usuário e a senha são enviados em texto não criptografado para o servidor ou proxy.</span><span class="sxs-lookup"><span data-stu-id="f1c51-129">Basic: Basic is a scheme in which the username and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="f1c51-130">Padrão: Use o método de autenticação implementado pelo protocolo WS-Management.</span><span class="sxs-lookup"><span data-stu-id="f1c51-130">Default: Use the authentication method implemented by the WS-Management protocol.</span></span> <span data-ttu-id="f1c51-131">Esse é o padrão.</span><span class="sxs-lookup"><span data-stu-id="f1c51-131">This is the default.</span></span>
- <span data-ttu-id="f1c51-132">Resumo: o resumo é um esquema de desafio/resposta que usa uma cadeia de caracteres de dados especificada pelo servidor para o desafio.</span><span class="sxs-lookup"><span data-stu-id="f1c51-132">Digest: Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="f1c51-133">Kerberos: o computador cliente e o servidor se autenticam mutuamente usando certificados Kerberos.</span><span class="sxs-lookup"><span data-stu-id="f1c51-133">Kerberos: The client computer and the server mutually authenticate using Kerberos certificates.</span></span>
- <span data-ttu-id="f1c51-134">Negotiate: Negotiate é um esquema de desafio/resposta que negocia com o servidor ou proxy para determinar o esquema a ser usado para autenticação.</span><span class="sxs-lookup"><span data-stu-id="f1c51-134">Negotiate: Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span> <span data-ttu-id="f1c51-135">Por exemplo, esse valor de parâmetro permite uma negociação para determinar se o protocolo Kerberos ou NTLM será utilizado.</span><span class="sxs-lookup"><span data-stu-id="f1c51-135">For example, this parameter value allows negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="f1c51-136">CredSSP: Use a autenticação do Credential Security Support Provider (CredSSP), que permite ao usuário delegar credenciais.</span><span class="sxs-lookup"><span data-stu-id="f1c51-136">CredSSP: Use Credential Security Support Provider (CredSSP) authentication, which allows the user to delegate credentials.</span></span> <span data-ttu-id="f1c51-137">Esta opção foi criada para os comandos executados em um computador remoto, mas coletam dados ou executam comandos adicionais em outros computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="f1c51-137">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

> [!CAUTION]
> <span data-ttu-id="f1c51-138">O CredSSP delega as credenciais do usuário do computador local para um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="f1c51-138">CredSSP delegates the user's credentials from the local computer to a remote computer.</span></span> <span data-ttu-id="f1c51-139">Essa prática aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="f1c51-139">This practice increases the security risk of the remote operation.</span></span> <span data-ttu-id="f1c51-140">Se o computador remoto estiver comprometido, no momento em que as credenciais forem passadas a ele essas credenciais poderão ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="f1c51-140">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="f1c51-141">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="f1c51-141">-CertificateThumbprint</span></span>

<span data-ttu-id="f1c51-142">Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa ação.</span><span class="sxs-lookup"><span data-stu-id="f1c51-142">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="f1c51-143">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="f1c51-143">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="f1c51-144">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="f1c51-144">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="f1c51-145">Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="f1c51-145">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="f1c51-146">Para obter uma impressão digital do certificado, use o `Get-Item` `Get-ChildItem` comando ou na unidade certificado do PowerShell:.</span><span class="sxs-lookup"><span data-stu-id="f1c51-146">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="f1c51-147">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="f1c51-147">-ComputerName</span></span>

<span data-ttu-id="f1c51-148">Especifica o computador no qual se deseja executar a operação de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="f1c51-148">Specifies the computer against which you want to run the management operation.</span></span> <span data-ttu-id="f1c51-149">O valor pode ser um nome de domínio totalmente qualificado, um nome NetBIOS ou um endereço IP.</span><span class="sxs-lookup"><span data-stu-id="f1c51-149">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span> <span data-ttu-id="f1c51-150">Use o nome do computador local, use localhost ou use um ponto ( `.` ) para especificar o computador local.</span><span class="sxs-lookup"><span data-stu-id="f1c51-150">Use the local computer name, use localhost, or use a dot (`.`) to specify the local computer.</span></span> <span data-ttu-id="f1c51-151">O computador local é o padrão.</span><span class="sxs-lookup"><span data-stu-id="f1c51-151">The local computer is the default.</span></span> <span data-ttu-id="f1c51-152">Quando o computador remoto está em um domínio diferente do usuário, deve-se usar um nome de domínio totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="f1c51-152">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span> <span data-ttu-id="f1c51-153">É possível redirecionar um valor desse parâmetro para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f1c51-153">You can pipe a value for this parameter to the cmdlet.</span></span>

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

### <span data-ttu-id="f1c51-154">-Conexãouri</span><span class="sxs-lookup"><span data-stu-id="f1c51-154">-ConnectionURI</span></span>

<span data-ttu-id="f1c51-155">Especifica o ponto de extremidade de conexão.</span><span class="sxs-lookup"><span data-stu-id="f1c51-155">Specifies the connection endpoint.</span></span>
<span data-ttu-id="f1c51-156">O formato dessa cadeia de caracteres é:</span><span class="sxs-lookup"><span data-stu-id="f1c51-156">The format of this string is:</span></span>

`<Transport>://<Server>:<Port>/<ApplicationName>`

<span data-ttu-id="f1c51-157">A seguinte cadeia de caracteres é um valor formatado corretamente para este parâmetro:</span><span class="sxs-lookup"><span data-stu-id="f1c51-157">The following string is a properly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="f1c51-158">O URI deve ser totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="f1c51-158">The URI must be fully qualified.</span></span>

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

### <span data-ttu-id="f1c51-159">-Credential</span><span class="sxs-lookup"><span data-stu-id="f1c51-159">-Credential</span></span>

<span data-ttu-id="f1c51-160">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="f1c51-160">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="f1c51-161">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="f1c51-161">The default is the current user.</span></span> <span data-ttu-id="f1c51-162">Digite um nome de usuário, como "User01", "Domínio01 \ Usuário01" ou " User@Domain.com ".</span><span class="sxs-lookup"><span data-stu-id="f1c51-162">Type a user name, such as "User01", "Domain01\User01", or "User@Domain.com".</span></span> <span data-ttu-id="f1c51-163">Ou insira um objeto PSCredential, como um retornado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f1c51-163">Or, enter a PSCredential object, such as one returned by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="f1c51-164">Quando você digitar um nome de usuário, uma senha será solicitada.</span><span class="sxs-lookup"><span data-stu-id="f1c51-164">When you type a user name, you will be prompted for a password.</span></span>

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

### <span data-ttu-id="f1c51-165">-FilePath</span><span class="sxs-lookup"><span data-stu-id="f1c51-165">-FilePath</span></span>

<span data-ttu-id="f1c51-166">Especifica o caminho de um arquivo usado para criar um recurso de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="f1c51-166">Specifies the path of a file that is used to create a management resource.</span></span> <span data-ttu-id="f1c51-167">Você especifica o recurso de gerenciamento usando o parâmetro **ResourceURI** e o parâmetro **SelectorSet** .</span><span class="sxs-lookup"><span data-stu-id="f1c51-167">You specify the management resource using the **ResourceURI** parameter and the **SelectorSet** parameter .</span></span> <span data-ttu-id="f1c51-168">Por exemplo, o comando a seguir usa o parâmetro **File** :</span><span class="sxs-lookup"><span data-stu-id="f1c51-168">For example, the following command uses the **File** parameter:</span></span>

`Invoke-WSManAction -Action stopservice -ResourceUri wmi/cimv2/Win32_Service -SelectorSet @{Name="spooler"} -File c:\input.xml -Authentication Default`

<span data-ttu-id="f1c51-169">Esse comando chama o método **StopService** no serviço de spooler usando a entrada de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="f1c51-169">This command calls the **StopService** method on the Spooler service using input from a file.</span></span> <span data-ttu-id="f1c51-170">O arquivo, `Input.xml` , contém o seguinte conteúdo:</span><span class="sxs-lookup"><span data-stu-id="f1c51-170">The file, `Input.xml`, contains the following content:</span></span>

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

### <span data-ttu-id="f1c51-171">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="f1c51-171">-OptionSet</span></span>

<span data-ttu-id="f1c51-172">Passa um conjunto de opções para um serviço para modificar ou refinar a natureza da solicitação.</span><span class="sxs-lookup"><span data-stu-id="f1c51-172">Passes a set of switches to a service to modify or refine the nature of the request.</span></span> <span data-ttu-id="f1c51-173">Elas são semelhantes às opções usadas nos shells de linha de comando porque são específicas para o serviço.</span><span class="sxs-lookup"><span data-stu-id="f1c51-173">These are similar to switches used in command-line shells because they are service specific.</span></span> <span data-ttu-id="f1c51-174">Qualquer número de opções pode ser especificado.</span><span class="sxs-lookup"><span data-stu-id="f1c51-174">Any number of options can be specified.</span></span>

<span data-ttu-id="f1c51-175">O exemplo a seguir demonstra a sintaxe que passa os valores 1, 2 e 3 para os parâmetros a, b e c:</span><span class="sxs-lookup"><span data-stu-id="f1c51-175">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

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

### <span data-ttu-id="f1c51-176">-Port</span><span class="sxs-lookup"><span data-stu-id="f1c51-176">-Port</span></span>

<span data-ttu-id="f1c51-177">Especifica a porta a ser usada quando o cliente se conecta ao serviço WinRM.</span><span class="sxs-lookup"><span data-stu-id="f1c51-177">Specifies the port to use when the client connects to the WinRM service.</span></span> <span data-ttu-id="f1c51-178">Quando o transporte é HTTP, a porta padrão é 80.</span><span class="sxs-lookup"><span data-stu-id="f1c51-178">When the transport is HTTP, the default port is 80.</span></span> <span data-ttu-id="f1c51-179">Quando o transporte é HTTPS, a porta padrão é 443.</span><span class="sxs-lookup"><span data-stu-id="f1c51-179">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="f1c51-180">Quando você usa HTTPS como o transporte, o valor do parâmetro **ComputerName** deve corresponder ao CN (nome comum) do certificado do servidor.</span><span class="sxs-lookup"><span data-stu-id="f1c51-180">When you use HTTPS as the transport, the value of the **ComputerName** parameter must match the server's certificate common name (CN).</span></span> <span data-ttu-id="f1c51-181">No entanto, se o parâmetro **SkipCNCheck** for especificado como parte do parâmetro **SessionOption** , o nome comum do certificado do servidor não precisará corresponder ao nome do host do servidor.</span><span class="sxs-lookup"><span data-stu-id="f1c51-181">However, if the **SkipCNCheck** parameter is specified as part of the **SessionOption** parameter, the certificate common name of the server does not have to match the host name of the server.</span></span> <span data-ttu-id="f1c51-182">O parâmetro **SkipCNCheck** deve ser usado somente para computadores confiáveis.</span><span class="sxs-lookup"><span data-stu-id="f1c51-182">The **SkipCNCheck** parameter should be used only for trusted computers.</span></span>

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

### <span data-ttu-id="f1c51-183">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="f1c51-183">-ResourceURI</span></span>

<span data-ttu-id="f1c51-184">Contém o Uniform Resource Identifier (URI) da instância ou classe do recurso.</span><span class="sxs-lookup"><span data-stu-id="f1c51-184">Contains the Uniform Resource Identifier (URI) of the resource class or instance.</span></span> <span data-ttu-id="f1c51-185">O URI é utilizado para identificar um tipo específico de recurso, como discos ou processos em um computador.</span><span class="sxs-lookup"><span data-stu-id="f1c51-185">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="f1c51-186">Um URI consiste em um prefixo e um caminho para um recurso.</span><span class="sxs-lookup"><span data-stu-id="f1c51-186">A URI consists of a prefix and a path to a resource.</span></span> <span data-ttu-id="f1c51-187">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f1c51-187">For example:</span></span>

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

### <span data-ttu-id="f1c51-188">-SelectorSet</span><span class="sxs-lookup"><span data-stu-id="f1c51-188">-SelectorSet</span></span>

<span data-ttu-id="f1c51-189">Especifica um conjunto de pares de valor que são utilizados para selecionar instâncias do recurso de gerenciamento específico.</span><span class="sxs-lookup"><span data-stu-id="f1c51-189">Specifies a set of value pairs that are used to select particular management resource instances.</span></span> <span data-ttu-id="f1c51-190">O parâmetro **SelectorSet** é usado quando há mais de uma instância do recurso.</span><span class="sxs-lookup"><span data-stu-id="f1c51-190">The **SelectorSet** parameter is used when more than one instance of the resource exists.</span></span> <span data-ttu-id="f1c51-191">O valor do parâmetro **SelectorSet** deve ser uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="f1c51-191">The value of the **SelectorSet** parameter must be a hash table.</span></span>

<span data-ttu-id="f1c51-192">O exemplo a seguir mostra como inserir um valor para esse parâmetro:</span><span class="sxs-lookup"><span data-stu-id="f1c51-192">The following example shows how to enter a value for this parameter:</span></span>

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

### <span data-ttu-id="f1c51-193">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="f1c51-193">-SessionOption</span></span>

<span data-ttu-id="f1c51-194">Define um conjunto de opções estendidas para a sessão do WS-Management.</span><span class="sxs-lookup"><span data-stu-id="f1c51-194">Defines a set of extended options for the WS-Management session.</span></span> <span data-ttu-id="f1c51-195">Insira um objeto **SessionOption** que você cria usando o `New-WSManSessionOption` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f1c51-195">Enter a **SessionOption** object that you create using the `New-WSManSessionOption` cmdlet.</span></span> <span data-ttu-id="f1c51-196">Para obter mais informações sobre as opções disponíveis, consulte `New-WSManSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="f1c51-196">For more information about the options that are available, see `New-WSManSessionOption`.</span></span>

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

### <span data-ttu-id="f1c51-197">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="f1c51-197">-UseSSL</span></span>

<span data-ttu-id="f1c51-198">Especifica que o protocolo Secure Sockets Layer (SSL) deve ser utilizado para estabelecer uma conexão com o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="f1c51-198">Specifies that the Secure Sockets Layer (SSL) protocol should be used to establish a connection to the remote computer.</span></span> <span data-ttu-id="f1c51-199">Por padrão, SSL não é usado.</span><span class="sxs-lookup"><span data-stu-id="f1c51-199">By default, SSL is not used.</span></span>

<span data-ttu-id="f1c51-200">O WS-Management criptografa todo o conteúdo do Windows PowerShell que é transmitido pela rede.</span><span class="sxs-lookup"><span data-stu-id="f1c51-200">WS-Management encrypts all the Windows PowerShell content that is transmitted over the network.</span></span> <span data-ttu-id="f1c51-201">O parâmetro **UseSSL** permite especificar a proteção adicional do HTTPS em vez de http.</span><span class="sxs-lookup"><span data-stu-id="f1c51-201">The **UseSSL** parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span> <span data-ttu-id="f1c51-202">Se o SSL não estiver disponível na porta utilizada para a conexão e o parâmetro for especificado, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="f1c51-202">If SSL is not available on the port that is used for the connection and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="f1c51-203">-Valorset</span><span class="sxs-lookup"><span data-stu-id="f1c51-203">-ValueSet</span></span>

<span data-ttu-id="f1c51-204">Especifica uma tabela de hash que ajuda a modificar um recurso de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="f1c51-204">Specifies a hash table that helps modify a management resource.</span></span> <span data-ttu-id="f1c51-205">Você especifica o recurso de gerenciamento usando o parâmetro **ResourceURI** e o parâmetro **SelectorSet** .</span><span class="sxs-lookup"><span data-stu-id="f1c51-205">You specify the management resource using the **ResourceURI** parameter and the **SelectorSet** parameter.</span></span> <span data-ttu-id="f1c51-206">O valor do parâmetro **ValueSet** deve ser uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="f1c51-206">The value of the **ValueSet** parameter must be a hash table.</span></span>

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

### <span data-ttu-id="f1c51-207">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f1c51-207">CommonParameters</span></span>

<span data-ttu-id="f1c51-208">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f1c51-208">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f1c51-209">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="f1c51-209">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="f1c51-210">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="f1c51-210">INPUTS</span></span>

### <span data-ttu-id="f1c51-211">Nenhum</span><span class="sxs-lookup"><span data-stu-id="f1c51-211">None</span></span>

<span data-ttu-id="f1c51-212">Esse cmdlet não aceita nenhuma entrada.</span><span class="sxs-lookup"><span data-stu-id="f1c51-212">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="f1c51-213">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="f1c51-213">OUTPUTS</span></span>

### <span data-ttu-id="f1c51-214">Nenhum</span><span class="sxs-lookup"><span data-stu-id="f1c51-214">None</span></span>

<span data-ttu-id="f1c51-215">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="f1c51-215">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="f1c51-216">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="f1c51-216">NOTES</span></span>

<span data-ttu-id="f1c51-217">O `Set-WmiInstance` cmdlet, um cmdlet Instrumentação de gerenciamento do Windows (WMI), é semelhante.</span><span class="sxs-lookup"><span data-stu-id="f1c51-217">The `Set-WmiInstance` cmdlet, a Windows Management Instrumentation (WMI) cmdlet, is similar.</span></span>
<span data-ttu-id="f1c51-218">`Set-WmiInstance` usa a camada de conexão/transporte DCOM para criar ou atualizar instâncias do WMI.</span><span class="sxs-lookup"><span data-stu-id="f1c51-218">`Set-WmiInstance` uses the DCOM connection/transport layer to create or update WMI instances.</span></span>

## <span data-ttu-id="f1c51-219">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="f1c51-219">RELATED LINKS</span></span>

[<span data-ttu-id="f1c51-220">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="f1c51-220">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="f1c51-221">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="f1c51-221">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="f1c51-222">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="f1c51-222">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="f1c51-223">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="f1c51-223">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="f1c51-224">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="f1c51-224">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="f1c51-225">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="f1c51-225">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="f1c51-226">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="f1c51-226">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="f1c51-227">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="f1c51-227">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="f1c51-228">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="f1c51-228">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="f1c51-229">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="f1c51-229">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="f1c51-230">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="f1c51-230">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="f1c51-231">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="f1c51-231">Test-WSMan</span></span>](Test-WSMan.md)
