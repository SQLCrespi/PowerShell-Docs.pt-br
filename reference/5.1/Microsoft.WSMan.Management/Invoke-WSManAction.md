---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/invoke-wsmanaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WSManAction
ms.openlocfilehash: 1eeeb912ab32ec5334959daba1e352f20fec15b1
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "93196534"
---
# <span data-ttu-id="efba4-103">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="efba4-103">Invoke-WSManAction</span></span>

## <span data-ttu-id="efba4-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="efba4-104">SYNOPSIS</span></span>
<span data-ttu-id="efba4-105">Invoca uma ação no objeto especificado pelo URI de recurso e os seletores.</span><span class="sxs-lookup"><span data-stu-id="efba4-105">Invokes an action on the object that is specified by the Resource URI and by the selectors.</span></span>

## <span data-ttu-id="efba4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="efba4-106">SYNTAX</span></span>

### <span data-ttu-id="efba4-107">URI (padrão)</span><span class="sxs-lookup"><span data-stu-id="efba4-107">URI (Default)</span></span>

```
Invoke-WSManAction [-Action] <String> [-ConnectionURI <Uri>] [-FilePath <String>] [-OptionSet <Hashtable>]
 [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>] [-ValueSet <Hashtable>] [-ResourceURI] <Uri>
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="efba4-108">ComputerName</span><span class="sxs-lookup"><span data-stu-id="efba4-108">ComputerName</span></span>

```
Invoke-WSManAction [-Action] <String> [-ApplicationName <String>] [-ComputerName <String>] [-FilePath <String>]
 [-OptionSet <Hashtable>] [-Port <Int32>] [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>]
 [-UseSSL] [-ValueSet <Hashtable>] [-ResourceURI] <Uri> [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

## <span data-ttu-id="efba4-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="efba4-109">DESCRIPTION</span></span>

<span data-ttu-id="efba4-110">O Invoke-WSManAction executa uma ação no objeto especificado por RESOURCE_URI, onde parâmetros são especificados por pares chave/valor.</span><span class="sxs-lookup"><span data-stu-id="efba4-110">The Invoke-WSManAction runs an action on the object that is specified by RESOURCE_URI, where parameters are specified by key value pairs.</span></span>

<span data-ttu-id="efba4-111">Este cmdlet usa a camada de conexão/transporte do WSMan para realizar a ação.</span><span class="sxs-lookup"><span data-stu-id="efba4-111">This cmdlet uses the WSMan connection/transport layer to run the action.</span></span>

## <span data-ttu-id="efba4-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="efba4-112">EXAMPLES</span></span>

### <span data-ttu-id="efba4-113">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="efba4-113">Example 1</span></span>

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

<span data-ttu-id="efba4-114">Este comando chama o método StartService da instância da classe WMI Win32_Service que corresponde ao serviço de Spooler.</span><span class="sxs-lookup"><span data-stu-id="efba4-114">This command calls the StartService method of the Win32_Service WMI class instance that corresponds to the Spooler service.</span></span>

<span data-ttu-id="efba4-115">O valor de retorno indica se a ação foi ou não bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="efba4-115">The return value indicates whether the action was successful.</span></span>
<span data-ttu-id="efba4-116">Nesse caso, um valor de retorno 0 indica êxito.</span><span class="sxs-lookup"><span data-stu-id="efba4-116">In this case, a return value of 0 indicates success.</span></span>
<span data-ttu-id="efba4-117">Um valor de retorno de 5 indica que o serviço já foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="efba4-117">A return value of 5 indicates that the service is already started.</span></span>

### <span data-ttu-id="efba4-118">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="efba4-118">Example 2</span></span>

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

<span data-ttu-id="efba4-119">Esse comando chama o método StopService no serviço de Spooler usando entrada de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="efba4-119">This command calls the StopService method on the Spooler service by using input from a file.</span></span>
<span data-ttu-id="efba4-120">O arquivo, Input.xml, contém o seguinte conteúdo:</span><span class="sxs-lookup"><span data-stu-id="efba4-120">The file, Input.xml, contains the following content:</span></span>

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

<span data-ttu-id="efba4-121">O valor de retorno indica se a ação foi ou não bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="efba4-121">The return value indicates whether the action was successful.</span></span>
<span data-ttu-id="efba4-122">Nesse caso, um valor de retorno 0 indica êxito.</span><span class="sxs-lookup"><span data-stu-id="efba4-122">In this case, a return value of 0 indicates success.</span></span>
<span data-ttu-id="efba4-123">Um valor de retorno de 5 indica que o serviço já foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="efba4-123">A return value of 5 indicates that the service is already started.</span></span>

### <span data-ttu-id="efba4-124">Exemplo 3:</span><span class="sxs-lookup"><span data-stu-id="efba4-124">Example 3</span></span>

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

<span data-ttu-id="efba4-125">Este comando chama o método Create da classe Win32_Process.</span><span class="sxs-lookup"><span data-stu-id="efba4-125">This command calls the Create method of the Win32_Process class.</span></span>
<span data-ttu-id="efba4-126">Ele passa o método dois valores de parâmetro, Notepad.exe e "C: \" .</span><span class="sxs-lookup"><span data-stu-id="efba4-126">It passes the method two parameter values, Notepad.exe and "C:\".</span></span>
<span data-ttu-id="efba4-127">Como resultado, um novo processo é criado para executar o bloco de notas e o diretório atual do novo processo é definido como "C: \" .</span><span class="sxs-lookup"><span data-stu-id="efba4-127">As a result, a new process is created to run Notepad, and the current directory of the new process is set to "C:\".</span></span>

### <span data-ttu-id="efba4-128">Exemplo 4</span><span class="sxs-lookup"><span data-stu-id="efba4-128">Example 4</span></span>

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

<span data-ttu-id="efba4-129">Este comando chama o método StartService da instância da classe WMI Win32_Service que corresponde ao serviço de Spooler.</span><span class="sxs-lookup"><span data-stu-id="efba4-129">This command calls the StartService method of the Win32_Service WMI class instance that corresponds to the Spooler service.</span></span>
<span data-ttu-id="efba4-130">Como o parâmetro ComputerName está especificado, o comando é executado no computador remoto servidor01.</span><span class="sxs-lookup"><span data-stu-id="efba4-130">Because the ComputerName parameter is specified, the command runs against the remote server01 computer.</span></span>

<span data-ttu-id="efba4-131">O valor de retorno indica se a ação foi ou não bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="efba4-131">The return value indicates whether the action was successful.</span></span>
<span data-ttu-id="efba4-132">Nesse caso, um valor de retorno 0 indica êxito.</span><span class="sxs-lookup"><span data-stu-id="efba4-132">In this case, a return value of 0 indicates success.</span></span>
<span data-ttu-id="efba4-133">Um valor de retorno de 5 indica que o serviço já foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="efba4-133">A return value of 5 indicates that the service is already started.</span></span>

## <span data-ttu-id="efba4-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="efba4-134">PARAMETERS</span></span>

### <span data-ttu-id="efba4-135">-Action</span><span class="sxs-lookup"><span data-stu-id="efba4-135">-Action</span></span>

<span data-ttu-id="efba4-136">Especifica o método a ser executado no objeto de gerenciamento especificado pelo ResourceURI e pelos seletores.</span><span class="sxs-lookup"><span data-stu-id="efba4-136">Specifies the method to run on the management object specified by the ResourceURI and selectors.</span></span>

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

### <span data-ttu-id="efba4-137">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="efba4-137">-ApplicationName</span></span>

<span data-ttu-id="efba4-138">Especifica o nome do aplicativo na conexão.</span><span class="sxs-lookup"><span data-stu-id="efba4-138">Specifies the application name in the connection.</span></span>
<span data-ttu-id="efba4-139">O valor padrão do parâmetro ApplicationName é WSMAN.</span><span class="sxs-lookup"><span data-stu-id="efba4-139">The default value of the ApplicationName parameter is WSMAN.</span></span>
<span data-ttu-id="efba4-140">O identificador completo para o ponto de extremidade remoto é no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="efba4-140">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="efba4-141">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="efba4-141">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="efba4-142">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="efba4-142">For example:</span></span>

`http://server01:8080/WSMAN`

<span data-ttu-id="efba4-143">Os Serviços de Informações da Internet (IIS), que hospedam a sessão, encaminham solicitações com esse ponto de extremidade para o aplicativo especificado.</span><span class="sxs-lookup"><span data-stu-id="efba4-143">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="efba4-144">A configuração padrão de "WSMAN" é adequada para a maioria dos usos.</span><span class="sxs-lookup"><span data-stu-id="efba4-144">This default setting of "WSMAN" is appropriate for most uses.</span></span>
<span data-ttu-id="efba4-145">Este parâmetro é projetado para ser utilizado quando diversos computadores estabelecem conexões remotas com um computador que esteja executando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="efba4-145">This parameter is designed to be used when numerous computers establish remote connections to one computer running Windows PowerShell.</span></span>
<span data-ttu-id="efba4-146">Nesse caso, o IIS hospeda o Web Services for Management (WS-Management) para ter eficiência.</span><span class="sxs-lookup"><span data-stu-id="efba4-146">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

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

### <span data-ttu-id="efba4-147">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="efba4-147">-Authentication</span></span>

<span data-ttu-id="efba4-148">Especifica o mecanismo de autenticação a ser usado no servidor.</span><span class="sxs-lookup"><span data-stu-id="efba4-148">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="efba4-149">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="efba4-149">Possible values are:</span></span>

- <span data-ttu-id="efba4-150">Básico: básico é um esquema no qual o nome de usuário e a senha são enviados em texto não criptografado para o servidor ou proxy.</span><span class="sxs-lookup"><span data-stu-id="efba4-150">Basic: Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="efba4-151">Padrão: Use o método de autenticação implementado pelo protocolo WS-Management.</span><span class="sxs-lookup"><span data-stu-id="efba4-151">Default : Use the authentication method implemented by the WS-Management protocol.</span></span> <span data-ttu-id="efba4-152">Esse é o padrão.</span><span class="sxs-lookup"><span data-stu-id="efba4-152">This is the default.</span></span>
- <span data-ttu-id="efba4-153">Resumo: o resumo é um esquema de desafio/resposta que usa uma cadeia de caracteres de dados especificada pelo servidor para o desafio.</span><span class="sxs-lookup"><span data-stu-id="efba4-153">Digest: Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="efba4-154">Kerberos: o computador cliente e o servidor são mutuamente autenticados usando certificados Kerberos.</span><span class="sxs-lookup"><span data-stu-id="efba4-154">Kerberos: The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="efba4-155">Negotiate: Negotiate é um esquema de desafio/resposta que negocia com o servidor ou proxy para determinar o esquema a ser usado para autenticação.</span><span class="sxs-lookup"><span data-stu-id="efba4-155">Negotiate: Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span> <span data-ttu-id="efba4-156">Por exemplo, esse valor de parâmetro permite uma negociação para determinar se o protocolo Kerberos ou NTLM será utilizado.</span><span class="sxs-lookup"><span data-stu-id="efba4-156">For example, this parameter value allows negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="efba4-157">CredSSP: Use a autenticação do Credential Security Support Provider (CredSSP), que permite ao usuário delegar credenciais.</span><span class="sxs-lookup"><span data-stu-id="efba4-157">CredSSP: Use Credential Security Support Provider (CredSSP) authentication, which allows the user to delegate credentials.</span></span> <span data-ttu-id="efba4-158">Esta opção foi criada para os comandos executados em um computador remoto, mas coletam dados ou executam comandos adicionais em outros computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="efba4-158">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="efba4-159">Cuidado: o CredSSP Delega as credenciais do usuário do computador local para um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="efba4-159">Caution: CredSSP delegates the user's credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="efba4-160">Essa prática aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="efba4-160">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="efba4-161">Se o computador remoto estiver comprometido, no momento em que as credenciais forem passadas a ele essas credenciais poderão ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="efba4-161">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="efba4-162">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="efba4-162">-CertificateThumbprint</span></span>

<span data-ttu-id="efba4-163">Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa ação.</span><span class="sxs-lookup"><span data-stu-id="efba4-163">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="efba4-164">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="efba4-164">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="efba4-165">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="efba4-165">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="efba4-166">Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="efba4-166">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="efba4-167">Para obter uma impressão digital do certificado, use o comando Get-Item ou Get-ChildItem na unidade Cert: do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="efba4-167">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the Windows PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="efba4-168">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="efba4-168">-ComputerName</span></span>

<span data-ttu-id="efba4-169">Especifica o computador no qual se deseja executar a operação de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="efba4-169">Specifies the computer against which you want to run the management operation.</span></span>
<span data-ttu-id="efba4-170">O valor pode ser um nome de domínio totalmente qualificado, um nome NetBIOS ou um endereço IP.</span><span class="sxs-lookup"><span data-stu-id="efba4-170">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="efba4-171">Utilize o nome do computador local, o localhost ou um ponto (.) para especificar o computador local.</span><span class="sxs-lookup"><span data-stu-id="efba4-171">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="efba4-172">O computador local é o padrão.</span><span class="sxs-lookup"><span data-stu-id="efba4-172">The local computer is the default.</span></span>
<span data-ttu-id="efba4-173">Quando o computador remoto está em um domínio diferente do usuário, deve-se usar um nome de domínio totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="efba4-173">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="efba4-174">É possível redirecionar um valor desse parâmetro para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="efba4-174">You can pipe a value for this parameter to the cmdlet.</span></span>

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

### <span data-ttu-id="efba4-175">-Conexãouri</span><span class="sxs-lookup"><span data-stu-id="efba4-175">-ConnectionURI</span></span>

<span data-ttu-id="efba4-176">Especifica o ponto de extremidade de conexão.</span><span class="sxs-lookup"><span data-stu-id="efba4-176">Specifies the connection endpoint.</span></span>
<span data-ttu-id="efba4-177">O formato dessa cadeia de caracteres é:</span><span class="sxs-lookup"><span data-stu-id="efba4-177">The format of this string is:</span></span>

<span data-ttu-id="efba4-178">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="efba4-178">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="efba4-179">A seguinte cadeia de caracteres é um valor formatado corretamente para este parâmetro:</span><span class="sxs-lookup"><span data-stu-id="efba4-179">The following string is a properly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="efba4-180">O URI deve ser totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="efba4-180">The URI must be fully qualified.</span></span>

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

### <span data-ttu-id="efba4-181">-Credential</span><span class="sxs-lookup"><span data-stu-id="efba4-181">-Credential</span></span>

<span data-ttu-id="efba4-182">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="efba4-182">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="efba4-183">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="efba4-183">The default is the current user.</span></span>
<span data-ttu-id="efba4-184">Digite um nome de usuário, como "User01", "Domínio01 \ Usuário01" ou User@Domain.com .</span><span class="sxs-lookup"><span data-stu-id="efba4-184">Type a user name, such as "User01", "Domain01\User01", or User@Domain.com.</span></span>
<span data-ttu-id="efba4-185">Ou digite um objeto PSCredential, como o retornado pelo cmdlet Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="efba4-185">Or, enter a PSCredential object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="efba4-186">Quando você digitar um nome de usuário, uma senha será solicitada.</span><span class="sxs-lookup"><span data-stu-id="efba4-186">When you type a user name, you will be prompted for a password.</span></span>

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

### <span data-ttu-id="efba4-187">-FilePath</span><span class="sxs-lookup"><span data-stu-id="efba4-187">-FilePath</span></span>

<span data-ttu-id="efba4-188">Especifica o caminho de um arquivo usado para atualizar um recurso de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="efba4-188">Specifies the path of a file that is used to update a management resource.</span></span>
<span data-ttu-id="efba4-189">Você pode especificar o recurso de gerenciamento usando os parâmetros ResourceURI e SelectorSet.</span><span class="sxs-lookup"><span data-stu-id="efba4-189">You specify the management resource by using the ResourceURI parameter and the SelectorSet parameter.</span></span>
<span data-ttu-id="efba4-190">Por exemplo, o comando a seguir usa o parâmetro FilePath:</span><span class="sxs-lookup"><span data-stu-id="efba4-190">For example, the following command uses the FilePath parameter:</span></span>

`Invoke-WSManAction -Action stopservice -ResourceUri wmicimv2/Win32_Service -SelectorSet @{Name="spooler"} -FilePath c:\input.xml -Authentication default`

<span data-ttu-id="efba4-191">Esse comando chama o método StopService no serviço de Spooler usando entrada de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="efba4-191">This command calls the StopService method on the Spooler service by using input from a file.</span></span>
<span data-ttu-id="efba4-192">O arquivo, Input.xml, contém o seguinte conteúdo:</span><span class="sxs-lookup"><span data-stu-id="efba4-192">The file, Input.xml, contains the following content:</span></span>

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

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

### <span data-ttu-id="efba4-193">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="efba4-193">-OptionSet</span></span>

<span data-ttu-id="efba4-194">Passa um conjunto de opções para um serviço para modificar ou refinar a natureza da solicitação.</span><span class="sxs-lookup"><span data-stu-id="efba4-194">Passes a set of switches  to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="efba4-195">Elas são semelhantes às opções usadas nos shells de linha de comando porque são específicas para o serviço.</span><span class="sxs-lookup"><span data-stu-id="efba4-195">These are similar to switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="efba4-196">Qualquer número de opções pode ser especificado.</span><span class="sxs-lookup"><span data-stu-id="efba4-196">Any number of options  can be specified.</span></span>

<span data-ttu-id="efba4-197">O exemplo a seguir demonstra a sintaxe que passa os valores 1, 2 e 3 para os parâmetros a, b e c:</span><span class="sxs-lookup"><span data-stu-id="efba4-197">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

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

### <span data-ttu-id="efba4-198">-Port</span><span class="sxs-lookup"><span data-stu-id="efba4-198">-Port</span></span>

<span data-ttu-id="efba4-199">Especifica a porta a ser usada quando o cliente se conecta ao serviço WinRM.</span><span class="sxs-lookup"><span data-stu-id="efba4-199">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="efba4-200">Quando o transporte é HTTP, a porta padrão é 80.</span><span class="sxs-lookup"><span data-stu-id="efba4-200">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="efba4-201">Quando o transporte é HTTPS, a porta padrão é 443.</span><span class="sxs-lookup"><span data-stu-id="efba4-201">When the transport is HTTPS, the default port is 443.</span></span>
<span data-ttu-id="efba4-202">Quando você usa HTTPS como o transporte, o valor do parâmetro ComputerName deve corresponder ao CN (nome comum) do certificado do servidor.</span><span class="sxs-lookup"><span data-stu-id="efba4-202">When you use HTTPS as the transport, the value of the ComputerName parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="efba4-203">No entanto, se o parâmetro SkipCNCheck for especificado como parte do parâmetro SessionOption, então o nome comum do certificado do servidor não precisará corresponder ao nome de host do servidor.</span><span class="sxs-lookup"><span data-stu-id="efba4-203">However, if the SkipCNCheck parameter is specified as part of the SessionOption parameter, then the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="efba4-204">O parâmetro SkipCNCheck deve ser utilizado apenas para computadores confiáveis.</span><span class="sxs-lookup"><span data-stu-id="efba4-204">The SkipCNCheck parameter should be used only for trusted machines.</span></span>

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

### <span data-ttu-id="efba4-205">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="efba4-205">-ResourceURI</span></span>

<span data-ttu-id="efba4-206">Contém o Uniform Resource Identifier (URI) da instância ou classe do recurso.</span><span class="sxs-lookup"><span data-stu-id="efba4-206">Contains the Uniform Resource Identifier (URI) of the resource class or instance.</span></span>
<span data-ttu-id="efba4-207">O URI é utilizado para identificar um tipo específico de recurso, como discos ou processos em um computador.</span><span class="sxs-lookup"><span data-stu-id="efba4-207">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="efba4-208">Um URI consiste em um prefixo e um caminho para um recurso.</span><span class="sxs-lookup"><span data-stu-id="efba4-208">A URI consists of a prefix and a path to a resource.</span></span>
<span data-ttu-id="efba4-209">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="efba4-209">For example:</span></span>

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

### <span data-ttu-id="efba4-210">-SelectorSet</span><span class="sxs-lookup"><span data-stu-id="efba4-210">-SelectorSet</span></span>

<span data-ttu-id="efba4-211">Especifica um conjunto de pares de valor que são utilizados para selecionar instâncias do recurso de gerenciamento específico.</span><span class="sxs-lookup"><span data-stu-id="efba4-211">Specifies a set of value pairs that are used to select particular management resource instances.</span></span>
<span data-ttu-id="efba4-212">*SelectorSet* é usado quando há mais de uma instância do recurso.</span><span class="sxs-lookup"><span data-stu-id="efba4-212">*SelectorSet* is used when more than one instance of the resource exists.</span></span>
<span data-ttu-id="efba4-213">O valor de *SelectorSet* deve ser uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="efba4-213">The value of *SelectorSet* must be a hash table.</span></span>

<span data-ttu-id="efba4-214">O exemplo a seguir mostra como inserir um valor para esse parâmetro:</span><span class="sxs-lookup"><span data-stu-id="efba4-214">The following example shows how to enter a value for this parameter:</span></span>

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

### <span data-ttu-id="efba4-215">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="efba4-215">-SessionOption</span></span>

<span data-ttu-id="efba4-216">Define um conjunto de opções estendidas para a sessão do WS-Management.</span><span class="sxs-lookup"><span data-stu-id="efba4-216">Defines a set of extended options for the WS-Management session.</span></span>
<span data-ttu-id="efba4-217">Digite um objeto SessionOption que você criou utilizando o cmdlet New-PSSessionOption.</span><span class="sxs-lookup"><span data-stu-id="efba4-217">Enter a SessionOption object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="efba4-218">Para obter mais informações sobre as opções disponíveis, consulte New-WSManSessionOption.</span><span class="sxs-lookup"><span data-stu-id="efba4-218">For more information about the options that are available, see New-WSManSessionOption.</span></span>

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

### <span data-ttu-id="efba4-219">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="efba4-219">-UseSSL</span></span>

<span data-ttu-id="efba4-220">Especifica que o protocolo de protocolo SSL (SSL) é usado para estabelecer uma conexão com o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="efba4-220">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="efba4-221">Por padrão, SSL não é usado.</span><span class="sxs-lookup"><span data-stu-id="efba4-221">By default, SSL is not used.</span></span>

<span data-ttu-id="efba4-222">WS-Management criptografa todo o conteúdo do PowerShell que é transmitido pela rede.</span><span class="sxs-lookup"><span data-stu-id="efba4-222">WS-Management encrypts all the PowerShell content  that is transmitted over the network.</span></span>
<span data-ttu-id="efba4-223">O parâmetro UseSSL permite especificar a proteção adicional de HTTPS em vez de HTTP.</span><span class="sxs-lookup"><span data-stu-id="efba4-223">The UseSSL parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="efba4-224">Se o SSL não estiver disponível na porta utilizada para a conexão e o parâmetro for especificado, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="efba4-224">If SSL is not available on the port that is used for the connection and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="efba4-225">-Valorset</span><span class="sxs-lookup"><span data-stu-id="efba4-225">-ValueSet</span></span>

<span data-ttu-id="efba4-226">Especifica uma tabela de hash que ajuda a modificar um recurso de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="efba4-226">Specifies a hash table that helps modify a management resource.</span></span>
<span data-ttu-id="efba4-227">Você especifica o recurso de gerenciamento usando os parâmetros ResourceURI e SelectorSet.</span><span class="sxs-lookup"><span data-stu-id="efba4-227">You specify the management resource using the ResourceURI and SelectorSet parameters.</span></span>
<span data-ttu-id="efba4-228">O valor do parâmetro ValueSet deve ser uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="efba4-228">The value of the ValueSet parameter must be a hash table.</span></span>

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

### <span data-ttu-id="efba4-229">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="efba4-229">CommonParameters</span></span>

<span data-ttu-id="efba4-230">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="efba4-230">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="efba4-231">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="efba4-231">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="efba4-232">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="efba4-232">INPUTS</span></span>

### <span data-ttu-id="efba4-233">Nenhum</span><span class="sxs-lookup"><span data-stu-id="efba4-233">None</span></span>

<span data-ttu-id="efba4-234">Esse cmdlet não aceita nenhuma entrada.</span><span class="sxs-lookup"><span data-stu-id="efba4-234">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="efba4-235">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="efba4-235">OUTPUTS</span></span>

### <span data-ttu-id="efba4-236">Nenhum</span><span class="sxs-lookup"><span data-stu-id="efba4-236">None</span></span>

<span data-ttu-id="efba4-237">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="efba4-237">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="efba4-238">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="efba4-238">NOTES</span></span>

## <span data-ttu-id="efba4-239">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="efba4-239">RELATED LINKS</span></span>

[<span data-ttu-id="efba4-240">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="efba4-240">Invoke-WmiMethod</span></span>](../Microsoft.PowerShell.Management/Invoke-WmiMethod.md)

[<span data-ttu-id="efba4-241">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="efba4-241">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="efba4-242">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="efba4-242">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="efba4-243">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="efba4-243">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="efba4-244">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="efba4-244">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="efba4-245">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="efba4-245">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="efba4-246">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="efba4-246">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="efba4-247">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="efba4-247">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="efba4-248">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="efba4-248">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="efba4-249">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="efba4-249">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="efba4-250">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="efba4-250">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="efba4-251">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="efba4-251">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="efba4-252">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="efba4-252">Test-WSMan</span></span>](Test-WSMan.md)
