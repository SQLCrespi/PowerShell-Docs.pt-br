---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/invoke-wsmanaction?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WSManAction
ms.openlocfilehash: 18ca64912df0e6b672bd05358aa806f639a590e7
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93194927"
---
# <span data-ttu-id="08408-103">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="08408-103">Invoke-WSManAction</span></span>

## <span data-ttu-id="08408-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="08408-104">SYNOPSIS</span></span>
<span data-ttu-id="08408-105">Invoca uma ação no objeto especificado pelo URI de recurso e os seletores.</span><span class="sxs-lookup"><span data-stu-id="08408-105">Invokes an action on the object that is specified by the Resource URI and by the selectors.</span></span>

## <span data-ttu-id="08408-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="08408-106">SYNTAX</span></span>

### <span data-ttu-id="08408-107">URI (padrão)</span><span class="sxs-lookup"><span data-stu-id="08408-107">URI (Default)</span></span>

```
Invoke-WSManAction [-Action] <String> [-ConnectionURI <Uri>] [-FilePath <String>] [-OptionSet <Hashtable>]
 [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>] [-ValueSet <Hashtable>] [-ResourceURI] <Uri>
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="08408-108">ComputerName</span><span class="sxs-lookup"><span data-stu-id="08408-108">ComputerName</span></span>

```
Invoke-WSManAction [-Action] <String> [-ApplicationName <String>] [-ComputerName <String>] [-FilePath <String>]
 [-OptionSet <Hashtable>] [-Port <Int32>] [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>]
 [-UseSSL] [-ValueSet <Hashtable>] [-ResourceURI] <Uri> [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

## <span data-ttu-id="08408-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="08408-109">DESCRIPTION</span></span>
<span data-ttu-id="08408-110">O **Invoke-WSManAction** executa uma ação no objeto especificado por RESOURCE_URI, em que os parâmetros são especificados por pares chave-valor.</span><span class="sxs-lookup"><span data-stu-id="08408-110">The **Invoke-WSManAction** runs an action on the object that is specified by RESOURCE_URI, where parameters are specified by key value pairs.</span></span>

<span data-ttu-id="08408-111">Este cmdlet usa a camada de conexão/transporte do WSMan para realizar a ação.</span><span class="sxs-lookup"><span data-stu-id="08408-111">This cmdlet uses the WSMan connection/transport layer to run the action.</span></span>

## <span data-ttu-id="08408-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="08408-112">EXAMPLES</span></span>

### <span data-ttu-id="08408-113">Exemplo 1: invocar um método</span><span class="sxs-lookup"><span data-stu-id="08408-113">Example 1: Invoke a method</span></span>

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

<span data-ttu-id="08408-114">Esse comando chama o método **StartService** da instância da classe WMI Win32_Service que corresponde ao serviço de spooler.</span><span class="sxs-lookup"><span data-stu-id="08408-114">This command calls the **StartService** method of the Win32_Service WMI class instance that corresponds to the Spooler service.</span></span>

<span data-ttu-id="08408-115">O valor de retorno indica se a ação foi ou não bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="08408-115">The return value indicates whether the action was successful.</span></span>
<span data-ttu-id="08408-116">Nesse caso, um valor de retorno 0 indica êxito.</span><span class="sxs-lookup"><span data-stu-id="08408-116">In this case, a return value of 0 indicates success.</span></span>
<span data-ttu-id="08408-117">Um valor de retorno de 5 indica que o serviço já foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="08408-117">A return value of 5 indicates that the service is already started.</span></span>

### <span data-ttu-id="08408-118">Exemplo 2: invocar um método</span><span class="sxs-lookup"><span data-stu-id="08408-118">Example 2: Invoke a method</span></span>

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

<span data-ttu-id="08408-119">Esse comando chama o método **StopService** no serviço de spooler usando a entrada de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="08408-119">This command calls the **StopService** method on the Spooler service by using input from a file.</span></span>
<span data-ttu-id="08408-120">O arquivo, Input.xml, contém o seguinte conteúdo:</span><span class="sxs-lookup"><span data-stu-id="08408-120">The file, Input.xml, contains the following content:</span></span>

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

### <span data-ttu-id="08408-121">Exemplo 3: invocar um método com valores de parâmetro especificados</span><span class="sxs-lookup"><span data-stu-id="08408-121">Example 3: Invoke a method with specified parameter values</span></span>

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

<span data-ttu-id="08408-122">Esse comando chama o método **Create** da classe Win32_Process.</span><span class="sxs-lookup"><span data-stu-id="08408-122">This command calls the **Create** method of the Win32_Process class.</span></span>
<span data-ttu-id="08408-123">Ele passa o método dois valores de parâmetro, Notepad.exe e C:\.</span><span class="sxs-lookup"><span data-stu-id="08408-123">It passes the method two parameter values, Notepad.exe and C:\.</span></span>
<span data-ttu-id="08408-124">Como resultado, um novo processo é criado para executar o bloco de notas e o diretório atual do novo processo é definido como C:\.</span><span class="sxs-lookup"><span data-stu-id="08408-124">As a result, a new process is created to run Notepad, and the current directory of the new process is set to C:\.</span></span>

### <span data-ttu-id="08408-125">Exemplo 4: invocar um método em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="08408-125">Example 4: Invoke a method on a remote computer</span></span>

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

<span data-ttu-id="08408-126">Esse comando chama o método **StartService** da instância da classe WMI Win32_Service que corresponde ao serviço de spooler.</span><span class="sxs-lookup"><span data-stu-id="08408-126">This command calls the **StartService** method of the Win32_Service WMI class instance that corresponds to the Spooler service.</span></span>
<span data-ttu-id="08408-127">Como o parâmetro *ComputerName* é especificado, o comando é executado no computador remoto Server01.</span><span class="sxs-lookup"><span data-stu-id="08408-127">Because the *ComputerName* parameter is specified, the command runs against the remote server01 computer.</span></span>

## <span data-ttu-id="08408-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="08408-128">PARAMETERS</span></span>

### <span data-ttu-id="08408-129">-Action</span><span class="sxs-lookup"><span data-stu-id="08408-129">-Action</span></span>
<span data-ttu-id="08408-130">Especifica o método a ser executado no objeto de gerenciamento especificado pelo ResourceURI e pelos seletores.</span><span class="sxs-lookup"><span data-stu-id="08408-130">Specifies the method to run on the management object specified by the ResourceURI and selectors.</span></span>

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

### <span data-ttu-id="08408-131">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="08408-131">-ApplicationName</span></span>
<span data-ttu-id="08408-132">Especifica o nome do aplicativo na conexão.</span><span class="sxs-lookup"><span data-stu-id="08408-132">Specifies the application name in the connection.</span></span>
<span data-ttu-id="08408-133">O valor padrão do parâmetro *ApplicationName* é WSMan.</span><span class="sxs-lookup"><span data-stu-id="08408-133">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="08408-134">O identificador completo para o ponto de extremidade remoto é no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="08408-134">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="08408-135">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="08408-135">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="08408-136">Por exemplo: `http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="08408-136">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="08408-137">Os Serviços de Informações da Internet (IIS), que hospedam a sessão, encaminham solicitações com esse ponto de extremidade para o aplicativo especificado.</span><span class="sxs-lookup"><span data-stu-id="08408-137">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="08408-138">Essa configuração padrão de WSMAN é apropriada para a maioria dos usos.</span><span class="sxs-lookup"><span data-stu-id="08408-138">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="08408-139">Esse parâmetro é projetado para ser usado se muitos computadores estabelecerem conexões remotas com um computador que esteja executando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08408-139">This parameter is designed to be used if many computers establish remote connections to one computer that is running PowerShell.</span></span>
<span data-ttu-id="08408-140">Nesse caso, o IIS hospeda o Web Services for Management (WS-Management) para ter eficiência.</span><span class="sxs-lookup"><span data-stu-id="08408-140">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

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

### <span data-ttu-id="08408-141">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="08408-141">-Authentication</span></span>
<span data-ttu-id="08408-142">Especifica o mecanismo de autenticação a ser usado no servidor.</span><span class="sxs-lookup"><span data-stu-id="08408-142">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="08408-143">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="08408-143">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="08408-144">Básica.</span><span class="sxs-lookup"><span data-stu-id="08408-144">Basic.</span></span>
<span data-ttu-id="08408-145">É um esquema no qual o nome de usuário e senha são enviados em texto não criptografado para o servidor ou proxy.</span><span class="sxs-lookup"><span data-stu-id="08408-145">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="08408-146">Padrão.</span><span class="sxs-lookup"><span data-stu-id="08408-146">Default.</span></span>
<span data-ttu-id="08408-147">Utiliza o método de autenticação implementado pelo protocolo WS-Management.</span><span class="sxs-lookup"><span data-stu-id="08408-147">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="08408-148">Esse é o padrão.</span><span class="sxs-lookup"><span data-stu-id="08408-148">This is the default.</span></span>
- <span data-ttu-id="08408-149">Digest.</span><span class="sxs-lookup"><span data-stu-id="08408-149">Digest.</span></span>
<span data-ttu-id="08408-150">É um esquema de desafio/resposta que utiliza uma cadeia de caracteres de dados do servidor especificada para o desafio.</span><span class="sxs-lookup"><span data-stu-id="08408-150">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="08408-151">Kerberos.</span><span class="sxs-lookup"><span data-stu-id="08408-151">Kerberos.</span></span>
<span data-ttu-id="08408-152">O computador cliente e o servidor autenticam mutuamente utilizando certificados Kerberos.</span><span class="sxs-lookup"><span data-stu-id="08408-152">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="08408-153">Negotiate.</span><span class="sxs-lookup"><span data-stu-id="08408-153">Negotiate.</span></span>
<span data-ttu-id="08408-154">É um esquema de desafio/resposta que negocia com o servidor ou proxy para determinar o esquema a ser utilizado para autenticação.</span><span class="sxs-lookup"><span data-stu-id="08408-154">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="08408-155">Por exemplo, esse valor de parâmetro permite que a negociação determine se o protocolo Kerberos ou NTLM é usado.</span><span class="sxs-lookup"><span data-stu-id="08408-155">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="08408-156">CredSSP.</span><span class="sxs-lookup"><span data-stu-id="08408-156">CredSSP.</span></span>
<span data-ttu-id="08408-157">Use a autenticação do Credential Security Support Provider (CredSSP), que permite que o usuário delegue as credenciais.</span><span class="sxs-lookup"><span data-stu-id="08408-157">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="08408-158">Esta opção foi criada para os comandos executados em um computador remoto, mas coletam dados ou executam comandos adicionais em outros computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="08408-158">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="08408-159">Cuidado: o CredSSP Delega as credenciais do usuário do computador local para um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="08408-159">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="08408-160">Essa prática aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="08408-160">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="08408-161">Se o computador remoto estiver comprometido, no momento em que as credenciais forem passadas a ele essas credenciais poderão ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="08408-161">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="08408-162">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="08408-162">-CertificateThumbprint</span></span>
<span data-ttu-id="08408-163">Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa ação.</span><span class="sxs-lookup"><span data-stu-id="08408-163">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="08408-164">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="08408-164">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="08408-165">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="08408-165">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="08408-166">Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="08408-166">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="08408-167">Para obter uma impressão digital do certificado, use o comando Get-Item ou Get-ChildItem na unidade certificado do PowerShell:.</span><span class="sxs-lookup"><span data-stu-id="08408-167">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="08408-168">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="08408-168">-ComputerName</span></span>
<span data-ttu-id="08408-169">Especifica o computador no qual executar a operação de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="08408-169">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="08408-170">O valor pode ser um nome de domínio totalmente qualificado, um nome NetBIOS ou um endereço IP.</span><span class="sxs-lookup"><span data-stu-id="08408-170">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="08408-171">Utilize o nome do computador local, o localhost ou um ponto (.) para especificar o computador local.</span><span class="sxs-lookup"><span data-stu-id="08408-171">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="08408-172">O computador local é o padrão.</span><span class="sxs-lookup"><span data-stu-id="08408-172">The local computer is the default.</span></span>
<span data-ttu-id="08408-173">Quando o computador remoto está em um domínio diferente do usuário, deve-se usar um nome de domínio totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="08408-173">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="08408-174">É possível redirecionar um valor desse parâmetro para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="08408-174">You can pipe a value for this parameter to the cmdlet.</span></span>

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

### <span data-ttu-id="08408-175">-Conexãouri</span><span class="sxs-lookup"><span data-stu-id="08408-175">-ConnectionURI</span></span>
<span data-ttu-id="08408-176">Especifica o ponto de extremidade de conexão.</span><span class="sxs-lookup"><span data-stu-id="08408-176">Specifies the connection endpoint.</span></span>
<span data-ttu-id="08408-177">O formato dessa cadeia de caracteres é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="08408-177">The format of this string is as follows:</span></span>

<span data-ttu-id="08408-178">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="08408-178">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="08408-179">A cadeia de caracteres a seguir é um valor formatado corretamente para este parâmetro:</span><span class="sxs-lookup"><span data-stu-id="08408-179">The following string is a correctly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="08408-180">O URI deve ser totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="08408-180">The URI must be fully qualified.</span></span>

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

### <span data-ttu-id="08408-181">-Credential</span><span class="sxs-lookup"><span data-stu-id="08408-181">-Credential</span></span>
<span data-ttu-id="08408-182">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="08408-182">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="08408-183">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="08408-183">The default is the current user.</span></span>
<span data-ttu-id="08408-184">Digite um nome de usuário, como User01, Domínio01 \ Usuário01 ou User@Domain.com .</span><span class="sxs-lookup"><span data-stu-id="08408-184">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="08408-185">Ou insira um objeto **PSCredential** , como um retornado pelo cmdlet Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="08408-185">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="08408-186">Quando você digita um nome de usuário, esse cmdlet solicita uma senha.</span><span class="sxs-lookup"><span data-stu-id="08408-186">When you type a user name, this cmdlet prompts you for a password.</span></span>

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

### <span data-ttu-id="08408-187">-FilePath</span><span class="sxs-lookup"><span data-stu-id="08408-187">-FilePath</span></span>
<span data-ttu-id="08408-188">Especifica o caminho de um arquivo usado para atualizar um recurso de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="08408-188">Specifies the path of a file that is used to update a management resource.</span></span>
<span data-ttu-id="08408-189">Você especifica o recurso de gerenciamento usando o parâmetro *ResourceURI* e o parâmetro *SelectorSet* .</span><span class="sxs-lookup"><span data-stu-id="08408-189">You specify the management resource by using the *ResourceURI* parameter and the *SelectorSet* parameter.</span></span>
<span data-ttu-id="08408-190">Por exemplo, o comando a seguir usa o parâmetro *FilePath* :</span><span class="sxs-lookup"><span data-stu-id="08408-190">For example, the following command uses the *FilePath* parameter:</span></span>

`Invoke-WSManAction -Action stopservice -ResourceUri wmicimv2/Win32_Service -SelectorSet @{Name="spooler"} -FilePath c:\input.xml -Authentication default`

<span data-ttu-id="08408-191">Esse comando chama o método **StopService** no serviço de **spooler** usando a entrada de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="08408-191">This command calls the **StopService** method on the **Spooler** service by using input from a file.</span></span>
<span data-ttu-id="08408-192">O arquivo, Input.xml, contém o seguinte conteúdo:</span><span class="sxs-lookup"><span data-stu-id="08408-192">The file, Input.xml, contains the following content:</span></span>

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

### <span data-ttu-id="08408-193">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="08408-193">-OptionSet</span></span>
<span data-ttu-id="08408-194">Especifica um conjunto de opções para um serviço para modificar ou refinar a natureza da solicitação.</span><span class="sxs-lookup"><span data-stu-id="08408-194">Specifies a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="08408-195">Elas se assemelham a opções usadas em shells de linha de comando porque são específicas de serviço.</span><span class="sxs-lookup"><span data-stu-id="08408-195">These resemble switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="08408-196">Qualquer número de opções pode ser especificado.</span><span class="sxs-lookup"><span data-stu-id="08408-196">Any number of options can be specified.</span></span>

<span data-ttu-id="08408-197">O exemplo a seguir demonstra a sintaxe que passa os valores 1, 2 e 3 para os parâmetros a, b e c:</span><span class="sxs-lookup"><span data-stu-id="08408-197">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

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

### <span data-ttu-id="08408-198">-Port</span><span class="sxs-lookup"><span data-stu-id="08408-198">-Port</span></span>
<span data-ttu-id="08408-199">Especifica a porta a ser usada quando o cliente se conecta ao serviço WinRM.</span><span class="sxs-lookup"><span data-stu-id="08408-199">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="08408-200">Quando o transporte é HTTP, a porta padrão é 80.</span><span class="sxs-lookup"><span data-stu-id="08408-200">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="08408-201">Quando o transporte é HTTPS, a porta padrão é 443.</span><span class="sxs-lookup"><span data-stu-id="08408-201">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="08408-202">Quando você usa HTTPS como o transporte, o valor do parâmetro *ComputerName* deve corresponder ao CN (nome comum) do certificado do servidor.</span><span class="sxs-lookup"><span data-stu-id="08408-202">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="08408-203">No entanto, se o parâmetro *SkipCNCheck* for especificado como parte do parâmetro *SessionOption* , o nome comum do certificado do servidor não precisará corresponder ao nome do host do servidor.</span><span class="sxs-lookup"><span data-stu-id="08408-203">However, if the *SkipCNCheck* parameter is specified as part of the *SessionOption* parameter, the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="08408-204">O parâmetro *SkipCNCheck* deve ser usado somente para computadores confiáveis.</span><span class="sxs-lookup"><span data-stu-id="08408-204">The *SkipCNCheck* parameter should be used only for trusted computers.</span></span>

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

### <span data-ttu-id="08408-205">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="08408-205">-ResourceURI</span></span>
<span data-ttu-id="08408-206">Especifica o URI da classe ou instância de recurso.</span><span class="sxs-lookup"><span data-stu-id="08408-206">Specifies the URI of the resource class or instance.</span></span>
<span data-ttu-id="08408-207">O URI é utilizado para identificar um tipo específico de recurso, como discos ou processos em um computador.</span><span class="sxs-lookup"><span data-stu-id="08408-207">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="08408-208">Um URI consiste em um prefixo e um caminho de um recurso.</span><span class="sxs-lookup"><span data-stu-id="08408-208">A URI consists of a prefix and a path of a resource.</span></span>
<span data-ttu-id="08408-209">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="08408-209">For example:</span></span>

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

### <span data-ttu-id="08408-210">-SelectorSet</span><span class="sxs-lookup"><span data-stu-id="08408-210">-SelectorSet</span></span>
<span data-ttu-id="08408-211">Especifica um conjunto de pares de valor que são utilizados para selecionar instâncias do recurso de gerenciamento específico.</span><span class="sxs-lookup"><span data-stu-id="08408-211">Specifies a set of value pairs that are used to select particular management resource instances.</span></span>
<span data-ttu-id="08408-212">*SelectorSet* é usado quando há mais de uma instância do recurso.</span><span class="sxs-lookup"><span data-stu-id="08408-212">*SelectorSet* is used when more than one instance of the resource exists.</span></span>
<span data-ttu-id="08408-213">O valor de *SelectorSet* deve ser uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="08408-213">The value of *SelectorSet* must be a hash table.</span></span>

<span data-ttu-id="08408-214">O exemplo a seguir mostra como inserir um valor para esse parâmetro:</span><span class="sxs-lookup"><span data-stu-id="08408-214">The following example shows how to enter a value for this parameter:</span></span>

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

### <span data-ttu-id="08408-215">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="08408-215">-SessionOption</span></span>
<span data-ttu-id="08408-216">Especifica as opções estendidas para a sessão de WS-Management.</span><span class="sxs-lookup"><span data-stu-id="08408-216">Specifies extended options for the WS-Management session.</span></span>
<span data-ttu-id="08408-217">Insira um objeto **SessionOption** que você cria usando o cmdlet New-WSManSessionOption.</span><span class="sxs-lookup"><span data-stu-id="08408-217">Enter a **SessionOption** object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="08408-218">Para obter mais informações sobre as opções disponíveis, digite `Get-Help New-WSManSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="08408-218">For more information about the options that are available, type `Get-Help New-WSManSessionOption`.</span></span>

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

### <span data-ttu-id="08408-219">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="08408-219">-UseSSL</span></span>
<span data-ttu-id="08408-220">Especifica que o protocolo de protocolo SSL (SSL) é usado para estabelecer uma conexão com o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="08408-220">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="08408-221">Por padrão, SSL não é usado.</span><span class="sxs-lookup"><span data-stu-id="08408-221">By default, SSL is not used.</span></span>

<span data-ttu-id="08408-222">WS-Management criptografa todo o conteúdo do PowerShell que é transmitido pela rede.</span><span class="sxs-lookup"><span data-stu-id="08408-222">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="08408-223">O parâmetro *UseSSL* permite especificar a proteção adicional do HTTPS em vez de http.</span><span class="sxs-lookup"><span data-stu-id="08408-223">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="08408-224">Se o SSL não estiver disponível na porta que é usada para a conexão e você especificar esse parâmetro, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="08408-224">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="08408-225">-Valorset</span><span class="sxs-lookup"><span data-stu-id="08408-225">-ValueSet</span></span>
<span data-ttu-id="08408-226">Especifica uma tabela de hash que ajuda a modificar um recurso de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="08408-226">Specifies a hash table that helps modify a management resource.</span></span>
<span data-ttu-id="08408-227">Você especifica o recurso de gerenciamento usando *ResourceURI* e *SelectorSet* .</span><span class="sxs-lookup"><span data-stu-id="08408-227">You specify the management resource by using *ResourceURI* and *SelectorSet* .</span></span>
<span data-ttu-id="08408-228">O valor do parâmetro *ValueSet* deve ser uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="08408-228">The value of the *ValueSet* parameter must be a hash table.</span></span>

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

### <span data-ttu-id="08408-229">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="08408-229">CommonParameters</span></span>
<span data-ttu-id="08408-230">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="08408-230">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="08408-231">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="08408-231">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="08408-232">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="08408-232">INPUTS</span></span>

### <span data-ttu-id="08408-233">Nenhum</span><span class="sxs-lookup"><span data-stu-id="08408-233">None</span></span>
<span data-ttu-id="08408-234">Esse cmdlet não aceita nenhuma entrada.</span><span class="sxs-lookup"><span data-stu-id="08408-234">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="08408-235">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="08408-235">OUTPUTS</span></span>

### <span data-ttu-id="08408-236">Nenhum</span><span class="sxs-lookup"><span data-stu-id="08408-236">None</span></span>
<span data-ttu-id="08408-237">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="08408-237">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="08408-238">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="08408-238">NOTES</span></span>

## <span data-ttu-id="08408-239">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="08408-239">RELATED LINKS</span></span>

[<span data-ttu-id="08408-240">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="08408-240">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="08408-241">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="08408-241">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="08408-242">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="08408-242">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="08408-243">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="08408-243">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="08408-244">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="08408-244">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="08408-245">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="08408-245">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="08408-246">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="08408-246">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="08408-247">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="08408-247">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="08408-248">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="08408-248">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="08408-249">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="08408-249">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="08408-250">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="08408-250">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="08408-251">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="08408-251">Test-WSMan</span></span>](Test-WSMan.md)
