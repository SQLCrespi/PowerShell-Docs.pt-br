---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/invoke-wsmanaction?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WSManAction
ms.openlocfilehash: e2456e1da866929d60c36cc0e09990399b41614b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598403"
---
# <span data-ttu-id="b1f33-102">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="b1f33-102">Invoke-WSManAction</span></span>

## <span data-ttu-id="b1f33-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b1f33-103">SYNOPSIS</span></span>
<span data-ttu-id="b1f33-104">Invoca uma ação no objeto especificado pelo URI de recurso e os seletores.</span><span class="sxs-lookup"><span data-stu-id="b1f33-104">Invokes an action on the object that is specified by the Resource URI and by the selectors.</span></span>

## <span data-ttu-id="b1f33-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b1f33-105">SYNTAX</span></span>

### <span data-ttu-id="b1f33-106">URI (padrão)</span><span class="sxs-lookup"><span data-stu-id="b1f33-106">URI (Default)</span></span>

```
Invoke-WSManAction [-Action] <String> [-ConnectionURI <Uri>] [-FilePath <String>] [-OptionSet <Hashtable>]
 [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>] [-ValueSet <Hashtable>] [-ResourceURI] <Uri>
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="b1f33-107">ComputerName</span><span class="sxs-lookup"><span data-stu-id="b1f33-107">ComputerName</span></span>

```
Invoke-WSManAction [-Action] <String> [-ApplicationName <String>] [-ComputerName <String>] [-FilePath <String>]
 [-OptionSet <Hashtable>] [-Port <Int32>] [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>]
 [-UseSSL] [-ValueSet <Hashtable>] [-ResourceURI] <Uri> [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

## <span data-ttu-id="b1f33-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b1f33-108">DESCRIPTION</span></span>
<span data-ttu-id="b1f33-109">O **Invoke-WSManAction** executa uma ação no objeto especificado por RESOURCE_URI, em que os parâmetros são especificados por pares chave-valor.</span><span class="sxs-lookup"><span data-stu-id="b1f33-109">The **Invoke-WSManAction** runs an action on the object that is specified by RESOURCE_URI, where parameters are specified by key value pairs.</span></span>

<span data-ttu-id="b1f33-110">Este cmdlet usa a camada de conexão/transporte do WSMan para realizar a ação.</span><span class="sxs-lookup"><span data-stu-id="b1f33-110">This cmdlet uses the WSMan connection/transport layer to run the action.</span></span>

## <span data-ttu-id="b1f33-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b1f33-111">EXAMPLES</span></span>

### <span data-ttu-id="b1f33-112">Exemplo 1: invocar um método</span><span class="sxs-lookup"><span data-stu-id="b1f33-112">Example 1: Invoke a method</span></span>

```powershell
Invoke-WSManAction -Action startservice -ResourceURI wmicimv2/win32_service  -SelectorSet @{name="spooler"} -Authentication default
```

```Output
xsi         : http://www.w3.org/2001/XMLSchema-instance
p           : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim         : http://schemas.dmtf.org/wbem/wscim/1/common
lang        : en-US
ReturnValue : 0
```

<span data-ttu-id="b1f33-113">Esse comando chama o método **StartService** da instância da classe WMI Win32_Service que corresponde ao serviço de spooler.</span><span class="sxs-lookup"><span data-stu-id="b1f33-113">This command calls the **StartService** method of the Win32_Service WMI class instance that corresponds to the Spooler service.</span></span>

<span data-ttu-id="b1f33-114">O valor de retorno indica se a ação foi ou não bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="b1f33-114">The return value indicates whether the action was successful.</span></span>
<span data-ttu-id="b1f33-115">Nesse caso, um valor de retorno 0 indica êxito.</span><span class="sxs-lookup"><span data-stu-id="b1f33-115">In this case, a return value of 0 indicates success.</span></span>
<span data-ttu-id="b1f33-116">Um valor de retorno de 5 indica que o serviço já foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="b1f33-116">A return value of 5 indicates that the service is already started.</span></span>

### <span data-ttu-id="b1f33-117">Exemplo 2: invocar um método</span><span class="sxs-lookup"><span data-stu-id="b1f33-117">Example 2: Invoke a method</span></span>

```powershell
Invoke-WSManAction -Action stopservice -ResourceURI wmicimv2/Win32_Service -SelectorSet @{Name="spooler"} -FilePath:input.xml -Authentication default
```

```Output
xsi         : http://www.w3.org/2001/XMLSchema-instance
p           : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim         : http://schemas.dmtf.org/wbem/wscim/1/common
lang        : en-US
ReturnValue : 0
```

<span data-ttu-id="b1f33-118">Esse comando chama o método **StopService** no serviço de spooler usando a entrada de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="b1f33-118">This command calls the **StopService** method on the Spooler service by using input from a file.</span></span>
<span data-ttu-id="b1f33-119">O arquivo, Input.xml, contém o seguinte conteúdo:</span><span class="sxs-lookup"><span data-stu-id="b1f33-119">The file, Input.xml, contains the following content:</span></span>

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

### <span data-ttu-id="b1f33-120">Exemplo 3: invocar um método com valores de parâmetro especificados</span><span class="sxs-lookup"><span data-stu-id="b1f33-120">Example 3: Invoke a method with specified parameter values</span></span>

```powershell
Invoke-WSManAction -Action create -ResourceURI wmicimv2/win32_process -ValueSet @{commandline="notepad.exe";currentdirectory="C:\"}
```

```Output
xsi         : http://www.w3.org/2001/XMLSchema-instance
p           : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Process
cim         : http://schemas.dmtf.org/wbem/wscim/1/common
lang        : en-US
ProcessId   : 6356
ReturnValue : 0
```

<span data-ttu-id="b1f33-121">Esse comando chama o método **Create** da classe Win32_Process.</span><span class="sxs-lookup"><span data-stu-id="b1f33-121">This command calls the **Create** method of the Win32_Process class.</span></span>
<span data-ttu-id="b1f33-122">Ele passa o método dois valores de parâmetro, Notepad.exe e C:\.</span><span class="sxs-lookup"><span data-stu-id="b1f33-122">It passes the method two parameter values, Notepad.exe and C:\.</span></span>
<span data-ttu-id="b1f33-123">Como resultado, um novo processo é criado para executar o bloco de notas e o diretório atual do novo processo é definido como C:\.</span><span class="sxs-lookup"><span data-stu-id="b1f33-123">As a result, a new process is created to run Notepad, and the current directory of the new process is set to C:\.</span></span>

### <span data-ttu-id="b1f33-124">Exemplo 4: invocar um método em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="b1f33-124">Example 4: Invoke a method on a remote computer</span></span>

```powershell
Invoke-WSManAction -Action startservice -ResourceURI wmicimv2/win32_service  -SelectorSet @{name="spooler"} -ComputerName server01 -Authentication default
```

```Output
xsi         : http://www.w3.org/2001/XMLSchema-instance
p           : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim         : http://schemas.dmtf.org/wbem/wscim/1/common
lang        : en-US
ReturnValue : 0
```

<span data-ttu-id="b1f33-125">Esse comando chama o método **StartService** da instância da classe WMI Win32_Service que corresponde ao serviço de spooler.</span><span class="sxs-lookup"><span data-stu-id="b1f33-125">This command calls the **StartService** method of the Win32_Service WMI class instance that corresponds to the Spooler service.</span></span>
<span data-ttu-id="b1f33-126">Como o parâmetro *ComputerName* é especificado, o comando é executado no computador remoto Server01.</span><span class="sxs-lookup"><span data-stu-id="b1f33-126">Because the *ComputerName* parameter is specified, the command runs against the remote server01 computer.</span></span>

## <span data-ttu-id="b1f33-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b1f33-127">PARAMETERS</span></span>

### <span data-ttu-id="b1f33-128">-Action</span><span class="sxs-lookup"><span data-stu-id="b1f33-128">-Action</span></span>
<span data-ttu-id="b1f33-129">Especifica o método a ser executado no objeto de gerenciamento especificado pelo ResourceURI e pelos seletores.</span><span class="sxs-lookup"><span data-stu-id="b1f33-129">Specifies the method to run on the management object specified by the ResourceURI and selectors.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1f33-130">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="b1f33-130">-ApplicationName</span></span>
<span data-ttu-id="b1f33-131">Especifica o nome do aplicativo na conexão.</span><span class="sxs-lookup"><span data-stu-id="b1f33-131">Specifies the application name in the connection.</span></span>
<span data-ttu-id="b1f33-132">O valor padrão do parâmetro *ApplicationName* é WSMan.</span><span class="sxs-lookup"><span data-stu-id="b1f33-132">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="b1f33-133">O identificador completo para o ponto de extremidade remoto é no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="b1f33-133">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="b1f33-134">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="b1f33-134">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="b1f33-135">Por exemplo: `http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="b1f33-135">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="b1f33-136">Os Serviços de Informações da Internet (IIS), que hospedam a sessão, encaminham solicitações com esse ponto de extremidade para o aplicativo especificado.</span><span class="sxs-lookup"><span data-stu-id="b1f33-136">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="b1f33-137">Essa configuração padrão de WSMAN é apropriada para a maioria dos usos.</span><span class="sxs-lookup"><span data-stu-id="b1f33-137">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="b1f33-138">Esse parâmetro é projetado para ser usado se muitos computadores estabelecerem conexões remotas com um computador que esteja executando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1f33-138">This parameter is designed to be used if many computers establish remote connections to one computer that is running PowerShell.</span></span>
<span data-ttu-id="b1f33-139">Nesse caso, o IIS hospeda o Web Services for Management (WS-Management) para ter eficiência.</span><span class="sxs-lookup"><span data-stu-id="b1f33-139">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

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

### <span data-ttu-id="b1f33-140">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="b1f33-140">-Authentication</span></span>
<span data-ttu-id="b1f33-141">Especifica o mecanismo de autenticação a ser usado no servidor.</span><span class="sxs-lookup"><span data-stu-id="b1f33-141">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="b1f33-142">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="b1f33-142">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b1f33-143">Básica.</span><span class="sxs-lookup"><span data-stu-id="b1f33-143">Basic.</span></span>
<span data-ttu-id="b1f33-144">É um esquema no qual o nome de usuário e senha são enviados em texto não criptografado para o servidor ou proxy.</span><span class="sxs-lookup"><span data-stu-id="b1f33-144">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="b1f33-145">Padrão.</span><span class="sxs-lookup"><span data-stu-id="b1f33-145">Default.</span></span>
<span data-ttu-id="b1f33-146">Utiliza o método de autenticação implementado pelo protocolo WS-Management.</span><span class="sxs-lookup"><span data-stu-id="b1f33-146">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="b1f33-147">Este é o padrão.</span><span class="sxs-lookup"><span data-stu-id="b1f33-147">This is the default.</span></span>
- <span data-ttu-id="b1f33-148">Digest.</span><span class="sxs-lookup"><span data-stu-id="b1f33-148">Digest.</span></span>
<span data-ttu-id="b1f33-149">É um esquema de desafio/resposta que utiliza uma cadeia de caracteres de dados do servidor especificada para o desafio.</span><span class="sxs-lookup"><span data-stu-id="b1f33-149">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="b1f33-150">Kerberos.</span><span class="sxs-lookup"><span data-stu-id="b1f33-150">Kerberos.</span></span>
<span data-ttu-id="b1f33-151">O computador cliente e o servidor autenticam mutuamente utilizando certificados Kerberos.</span><span class="sxs-lookup"><span data-stu-id="b1f33-151">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="b1f33-152">Negotiate.</span><span class="sxs-lookup"><span data-stu-id="b1f33-152">Negotiate.</span></span>
<span data-ttu-id="b1f33-153">É um esquema de desafio/resposta que negocia com o servidor ou proxy para determinar o esquema a ser utilizado para autenticação.</span><span class="sxs-lookup"><span data-stu-id="b1f33-153">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="b1f33-154">Por exemplo, esse valor de parâmetro permite que a negociação determine se o protocolo Kerberos ou NTLM é usado.</span><span class="sxs-lookup"><span data-stu-id="b1f33-154">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="b1f33-155">CredSSP.</span><span class="sxs-lookup"><span data-stu-id="b1f33-155">CredSSP.</span></span>
<span data-ttu-id="b1f33-156">Use a autenticação do Credential Security Support Provider (CredSSP), que permite que o usuário delegue as credenciais.</span><span class="sxs-lookup"><span data-stu-id="b1f33-156">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="b1f33-157">Esta opção foi criada para os comandos executados em um computador remoto, mas coletam dados ou executam comandos adicionais em outros computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="b1f33-157">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="b1f33-158">Cuidado: o CredSSP Delega as credenciais do usuário do computador local para um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="b1f33-158">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="b1f33-159">Essa prática aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="b1f33-159">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="b1f33-160">Se o computador remoto estiver comprometido, no momento em que as credenciais forem passadas a ele essas credenciais poderão ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="b1f33-160">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="b1f33-161">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="b1f33-161">-CertificateThumbprint</span></span>
<span data-ttu-id="b1f33-162">Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa ação.</span><span class="sxs-lookup"><span data-stu-id="b1f33-162">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="b1f33-163">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="b1f33-163">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="b1f33-164">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="b1f33-164">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="b1f33-165">Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="b1f33-165">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="b1f33-166">Para obter uma impressão digital do certificado, use o comando Get-Item ou Get-ChildItem na unidade certificado do PowerShell:.</span><span class="sxs-lookup"><span data-stu-id="b1f33-166">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="b1f33-167">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="b1f33-167">-ComputerName</span></span>
<span data-ttu-id="b1f33-168">Especifica o computador no qual executar a operação de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="b1f33-168">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="b1f33-169">O valor pode ser um nome de domínio totalmente qualificado, um nome NetBIOS ou um endereço IP.</span><span class="sxs-lookup"><span data-stu-id="b1f33-169">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="b1f33-170">Utilize o nome do computador local, o localhost ou um ponto (.) para especificar o computador local.</span><span class="sxs-lookup"><span data-stu-id="b1f33-170">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="b1f33-171">O computador local é o padrão.</span><span class="sxs-lookup"><span data-stu-id="b1f33-171">The local computer is the default.</span></span>
<span data-ttu-id="b1f33-172">Quando o computador remoto está em um domínio diferente do usuário, deve-se usar um nome de domínio totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="b1f33-172">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="b1f33-173">É possível redirecionar um valor desse parâmetro para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b1f33-173">You can pipe a value for this parameter to the cmdlet.</span></span>

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

### <span data-ttu-id="b1f33-174">-Conexãouri</span><span class="sxs-lookup"><span data-stu-id="b1f33-174">-ConnectionURI</span></span>
<span data-ttu-id="b1f33-175">Especifica o ponto de extremidade de conexão.</span><span class="sxs-lookup"><span data-stu-id="b1f33-175">Specifies the connection endpoint.</span></span>
<span data-ttu-id="b1f33-176">O formato dessa cadeia de caracteres é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b1f33-176">The format of this string is as follows:</span></span>

<span data-ttu-id="b1f33-177">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="b1f33-177">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="b1f33-178">A cadeia de caracteres a seguir é um valor formatado corretamente para este parâmetro:</span><span class="sxs-lookup"><span data-stu-id="b1f33-178">The following string is a correctly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="b1f33-179">O URI deve ser totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="b1f33-179">The URI must be fully qualified.</span></span>

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

### <span data-ttu-id="b1f33-180">-Credential</span><span class="sxs-lookup"><span data-stu-id="b1f33-180">-Credential</span></span>
<span data-ttu-id="b1f33-181">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="b1f33-181">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="b1f33-182">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="b1f33-182">The default is the current user.</span></span>
<span data-ttu-id="b1f33-183">Digite um nome de usuário, como User01, Domínio01 \ Usuário01 ou User@Domain.com .</span><span class="sxs-lookup"><span data-stu-id="b1f33-183">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="b1f33-184">Ou insira um objeto **PSCredential** , como um retornado pelo cmdlet Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="b1f33-184">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="b1f33-185">Quando você digita um nome de usuário, esse cmdlet solicita uma senha.</span><span class="sxs-lookup"><span data-stu-id="b1f33-185">When you type a user name, this cmdlet prompts you for a password.</span></span>

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

### <span data-ttu-id="b1f33-186">-FilePath</span><span class="sxs-lookup"><span data-stu-id="b1f33-186">-FilePath</span></span>
<span data-ttu-id="b1f33-187">Especifica o caminho de um arquivo usado para atualizar um recurso de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="b1f33-187">Specifies the path of a file that is used to update a management resource.</span></span>
<span data-ttu-id="b1f33-188">Você especifica o recurso de gerenciamento usando o parâmetro *ResourceURI* e o parâmetro *SelectorSet* .</span><span class="sxs-lookup"><span data-stu-id="b1f33-188">You specify the management resource by using the *ResourceURI* parameter and the *SelectorSet* parameter.</span></span>
<span data-ttu-id="b1f33-189">Por exemplo, o comando a seguir usa o parâmetro *FilePath* :</span><span class="sxs-lookup"><span data-stu-id="b1f33-189">For example, the following command uses the *FilePath* parameter:</span></span>

`Invoke-WSManAction -Action stopservice -ResourceUri wmicimv2/Win32_Service -SelectorSet @{Name="spooler"} -FilePath c:\input.xml -Authentication default`

<span data-ttu-id="b1f33-190">Esse comando chama o método **StopService** no serviço de **spooler** usando a entrada de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="b1f33-190">This command calls the **StopService** method on the **Spooler** service by using input from a file.</span></span>
<span data-ttu-id="b1f33-191">O arquivo, Input.xml, contém o seguinte conteúdo:</span><span class="sxs-lookup"><span data-stu-id="b1f33-191">The file, Input.xml, contains the following content:</span></span>

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

### <span data-ttu-id="b1f33-192">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="b1f33-192">-OptionSet</span></span>
<span data-ttu-id="b1f33-193">Especifica um conjunto de opções para um serviço para modificar ou refinar a natureza da solicitação.</span><span class="sxs-lookup"><span data-stu-id="b1f33-193">Specifies a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="b1f33-194">Elas se assemelham a opções usadas em shells de linha de comando porque são específicas de serviço.</span><span class="sxs-lookup"><span data-stu-id="b1f33-194">These resemble switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="b1f33-195">Qualquer número de opções pode ser especificado.</span><span class="sxs-lookup"><span data-stu-id="b1f33-195">Any number of options can be specified.</span></span>

<span data-ttu-id="b1f33-196">O exemplo a seguir demonstra a sintaxe que passa os valores 1, 2 e 3 para os parâmetros a, b e c:</span><span class="sxs-lookup"><span data-stu-id="b1f33-196">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

`-OptionSet @{a=1;b=2;c=3}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: os

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b1f33-197">-Port</span><span class="sxs-lookup"><span data-stu-id="b1f33-197">-Port</span></span>
<span data-ttu-id="b1f33-198">Especifica a porta a ser usada quando o cliente se conecta ao serviço WinRM.</span><span class="sxs-lookup"><span data-stu-id="b1f33-198">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="b1f33-199">Quando o transporte é HTTP, a porta padrão é 80.</span><span class="sxs-lookup"><span data-stu-id="b1f33-199">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="b1f33-200">Quando o transporte é HTTPS, a porta padrão é 443.</span><span class="sxs-lookup"><span data-stu-id="b1f33-200">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="b1f33-201">Quando você usa HTTPS como o transporte, o valor do parâmetro *ComputerName* deve corresponder ao CN (nome comum) do certificado do servidor.</span><span class="sxs-lookup"><span data-stu-id="b1f33-201">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="b1f33-202">No entanto, se o parâmetro *SkipCNCheck* for especificado como parte do parâmetro *SessionOption* , o nome comum do certificado do servidor não precisará corresponder ao nome do host do servidor.</span><span class="sxs-lookup"><span data-stu-id="b1f33-202">However, if the *SkipCNCheck* parameter is specified as part of the *SessionOption* parameter, the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="b1f33-203">O parâmetro *SkipCNCheck* deve ser usado somente para computadores confiáveis.</span><span class="sxs-lookup"><span data-stu-id="b1f33-203">The *SkipCNCheck* parameter should be used only for trusted computers.</span></span>

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

### <span data-ttu-id="b1f33-204">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="b1f33-204">-ResourceURI</span></span>
<span data-ttu-id="b1f33-205">Especifica o URI da classe ou instância de recurso.</span><span class="sxs-lookup"><span data-stu-id="b1f33-205">Specifies the URI of the resource class or instance.</span></span>
<span data-ttu-id="b1f33-206">O URI é utilizado para identificar um tipo específico de recurso, como discos ou processos em um computador.</span><span class="sxs-lookup"><span data-stu-id="b1f33-206">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="b1f33-207">Um URI consiste em um prefixo e um caminho de um recurso.</span><span class="sxs-lookup"><span data-stu-id="b1f33-207">A URI consists of a prefix and a path of a resource.</span></span>
<span data-ttu-id="b1f33-208">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b1f33-208">For example:</span></span>

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: ruri

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b1f33-209">-SelectorSet</span><span class="sxs-lookup"><span data-stu-id="b1f33-209">-SelectorSet</span></span>
<span data-ttu-id="b1f33-210">Especifica um conjunto de pares de valor que são utilizados para selecionar instâncias do recurso de gerenciamento específico.</span><span class="sxs-lookup"><span data-stu-id="b1f33-210">Specifies a set of value pairs that are used to select particular management resource instances.</span></span>
<span data-ttu-id="b1f33-211">*SelectorSet* é usado quando há mais de uma instância do recurso.</span><span class="sxs-lookup"><span data-stu-id="b1f33-211">*SelectorSet* is used when more than one instance of the resource exists.</span></span>
<span data-ttu-id="b1f33-212">O valor de *SelectorSet* deve ser uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="b1f33-212">The value of *SelectorSet* must be a hash table.</span></span>

<span data-ttu-id="b1f33-213">O exemplo a seguir mostra como inserir um valor para esse parâmetro:</span><span class="sxs-lookup"><span data-stu-id="b1f33-213">The following example shows how to enter a value for this parameter:</span></span>

`-SelectorSet @{Name="WinRM";ID="yyy"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b1f33-214">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="b1f33-214">-SessionOption</span></span>
<span data-ttu-id="b1f33-215">Especifica as opções estendidas para a sessão de WS-Management.</span><span class="sxs-lookup"><span data-stu-id="b1f33-215">Specifies extended options for the WS-Management session.</span></span>
<span data-ttu-id="b1f33-216">Insira um objeto **SessionOption** que você cria usando o cmdlet New-WSManSessionOption.</span><span class="sxs-lookup"><span data-stu-id="b1f33-216">Enter a **SessionOption** object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="b1f33-217">Para obter mais informações sobre as opções disponíveis, digite `Get-Help New-WSManSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="b1f33-217">For more information about the options that are available, type `Get-Help New-WSManSessionOption`.</span></span>

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

### <span data-ttu-id="b1f33-218">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="b1f33-218">-UseSSL</span></span>
<span data-ttu-id="b1f33-219">Especifica que o protocolo de protocolo SSL (SSL) é usado para estabelecer uma conexão com o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="b1f33-219">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="b1f33-220">Por padrão, SSL não é usado.</span><span class="sxs-lookup"><span data-stu-id="b1f33-220">By default, SSL is not used.</span></span>

<span data-ttu-id="b1f33-221">WS-Management criptografa todo o conteúdo do PowerShell que é transmitido pela rede.</span><span class="sxs-lookup"><span data-stu-id="b1f33-221">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="b1f33-222">O parâmetro *UseSSL* permite especificar a proteção adicional do HTTPS em vez de http.</span><span class="sxs-lookup"><span data-stu-id="b1f33-222">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="b1f33-223">Se o SSL não estiver disponível na porta que é usada para a conexão e você especificar esse parâmetro, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="b1f33-223">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="b1f33-224">-Valorset</span><span class="sxs-lookup"><span data-stu-id="b1f33-224">-ValueSet</span></span>
<span data-ttu-id="b1f33-225">Especifica uma tabela de hash que ajuda a modificar um recurso de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="b1f33-225">Specifies a hash table that helps modify a management resource.</span></span>
<span data-ttu-id="b1f33-226">Você especifica o recurso de gerenciamento usando *ResourceURI* e *SelectorSet*.</span><span class="sxs-lookup"><span data-stu-id="b1f33-226">You specify the management resource by using *ResourceURI* and *SelectorSet*.</span></span>
<span data-ttu-id="b1f33-227">O valor do parâmetro *ValueSet* deve ser uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="b1f33-227">The value of the *ValueSet* parameter must be a hash table.</span></span>

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

### <span data-ttu-id="b1f33-228">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b1f33-228">CommonParameters</span></span>
<span data-ttu-id="b1f33-229">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b1f33-229">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b1f33-230">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b1f33-230">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b1f33-231">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b1f33-231">INPUTS</span></span>

### <span data-ttu-id="b1f33-232">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b1f33-232">None</span></span>
<span data-ttu-id="b1f33-233">Esse cmdlet não aceita nenhuma entrada.</span><span class="sxs-lookup"><span data-stu-id="b1f33-233">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="b1f33-234">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b1f33-234">OUTPUTS</span></span>

### <span data-ttu-id="b1f33-235">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b1f33-235">None</span></span>
<span data-ttu-id="b1f33-236">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="b1f33-236">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b1f33-237">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b1f33-237">NOTES</span></span>

## <span data-ttu-id="b1f33-238">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b1f33-238">RELATED LINKS</span></span>

[<span data-ttu-id="b1f33-239">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="b1f33-239">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="b1f33-240">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="b1f33-240">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="b1f33-241">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="b1f33-241">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="b1f33-242">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="b1f33-242">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="b1f33-243">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="b1f33-243">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="b1f33-244">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="b1f33-244">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="b1f33-245">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="b1f33-245">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="b1f33-246">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="b1f33-246">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="b1f33-247">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="b1f33-247">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="b1f33-248">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="b1f33-248">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="b1f33-249">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="b1f33-249">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="b1f33-250">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="b1f33-250">Test-WSMan</span></span>](Test-WSMan.md)

