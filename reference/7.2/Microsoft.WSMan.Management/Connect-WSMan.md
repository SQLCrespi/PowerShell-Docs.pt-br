---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/connect-wsman?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Connect-WSMan
ms.openlocfilehash: 5dfd0b355a3589bf45ea92b92ae8778023132bcd
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595990"
---
# <span data-ttu-id="c304f-102">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="c304f-102">Connect-WSMan</span></span>

## <span data-ttu-id="c304f-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="c304f-103">SYNOPSIS</span></span>
<span data-ttu-id="c304f-104">Conecta-se ao serviço WinRM em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="c304f-104">Connects to the WinRM service on a remote computer.</span></span>

## <span data-ttu-id="c304f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c304f-105">SYNTAX</span></span>

### <span data-ttu-id="c304f-106">ComputerName (padrão)</span><span class="sxs-lookup"><span data-stu-id="c304f-106">ComputerName (Default)</span></span>

```
Connect-WSMan [-ApplicationName <String>] [[-ComputerName] <String>] [-OptionSet <Hashtable>] [-Port <Int32>]
 [-SessionOption <SessionOption>] [-UseSSL] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="c304f-107">URI</span><span class="sxs-lookup"><span data-stu-id="c304f-107">URI</span></span>

```
Connect-WSMan [-ConnectionURI <Uri>] [-OptionSet <Hashtable>] [-Port <Int32>] [-SessionOption <SessionOption>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="c304f-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c304f-108">DESCRIPTION</span></span>
<span data-ttu-id="c304f-109">O cmdlet **Connect-WSMan conecta-** se ao serviço WinRM em um computador remoto e estabelece uma conexão persistente com o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="c304f-109">The **Connect-WSMan** cmdlet connects to the WinRM service on a remote computer, and it establishes a persistent connection to the remote computer.</span></span>
<span data-ttu-id="c304f-110">Você pode usar esse cmdlet no contexto do provedor WSMan para se conectar ao serviço WinRM em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="c304f-110">You can use this cmdlet in the context of the WSMan provider to connect to the WinRM service on a remote computer.</span></span>
<span data-ttu-id="c304f-111">No entanto, você também pode usar este cmdlet para se conectar ao serviço WinRM em um computador remoto antes de alterar para o provedor WSMan.</span><span class="sxs-lookup"><span data-stu-id="c304f-111">However, you can also use this cmdlet to connect to the WinRM service on a remote computer before you change to the WSMan provider.</span></span>
<span data-ttu-id="c304f-112">O computador remoto aparece no diretório raiz do provedor WSMan.</span><span class="sxs-lookup"><span data-stu-id="c304f-112">The remote computer appears in the root directory of the WSMan provider.</span></span>

<span data-ttu-id="c304f-113">Credenciais explícitas são necessárias quando os computadores cliente e servidor estiverem em domínios ou grupos de trabalho diferentes.</span><span class="sxs-lookup"><span data-stu-id="c304f-113">Explicit credentials are required when the client and server computers are in different domains or workgroups.</span></span>

<span data-ttu-id="c304f-114">Para obter informações sobre como se desconectar do serviço WinRM em um computador remoto, consulte o cmdlet Disconnect-WSMan.</span><span class="sxs-lookup"><span data-stu-id="c304f-114">For information about how to disconnect from the WinRM service on a remote computer, see the Disconnect-WSMan cmdlet.</span></span>

## <span data-ttu-id="c304f-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="c304f-115">EXAMPLES</span></span>

### <span data-ttu-id="c304f-116">Exemplo 1: conectar-se a um computador remoto</span><span class="sxs-lookup"><span data-stu-id="c304f-116">Example 1: Connect to a remote computer</span></span>

```
PS C:\> Connect-WSMan -ComputerName "server01"
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan

ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

<span data-ttu-id="c304f-117">Este comando cria uma conexão com o computador remoto server01.</span><span class="sxs-lookup"><span data-stu-id="c304f-117">This command creates a connection to the remote server01 computer.</span></span>

<span data-ttu-id="c304f-118">O cmdlet **Connect-WSMan** geralmente é usado no contexto do provedor WSMan para se conectar a um computador remoto, neste caso, o computador Server01.</span><span class="sxs-lookup"><span data-stu-id="c304f-118">The **Connect-WSMan** cmdlet is generally used in the context of the WSMan provider to connect to a remote computer, in this case the server01 computer.</span></span>
<span data-ttu-id="c304f-119">No entanto, você pode usar o cmdlet para estabelecer conexões com computadores remotos, antes de alterar para o provedor WSMan.</span><span class="sxs-lookup"><span data-stu-id="c304f-119">However, you can use the cmdlet to establish connections to remote computers before you change to the WSMan provider.</span></span>
<span data-ttu-id="c304f-120">Essas conexões aparecem na lista **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="c304f-120">Those connections appear in the **ComputerName** list.</span></span>

### <span data-ttu-id="c304f-121">Exemplo 2: conectar-se a um computador remoto usando credenciais de administrador</span><span class="sxs-lookup"><span data-stu-id="c304f-121">Example 2: Connect to a remote computer by using Administrator credentials</span></span>

```
PS C:\> $cred = Get-Credential Administrator
PS C:\> Connect-WSMan -ComputerName "server01" -Credential $cred
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan

ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

<span data-ttu-id="c304f-122">Este comando cria uma conexão com o sistema remoto server01 usando as credenciais da conta do Administrador.</span><span class="sxs-lookup"><span data-stu-id="c304f-122">This command creates a connection to the remote system server01 using the Administrator account credentials.</span></span>

<span data-ttu-id="c304f-123">O primeiro comando usa o cmdlet Get-Credential para obter as credenciais do Administrador e as armazena na variável $cred.</span><span class="sxs-lookup"><span data-stu-id="c304f-123">The first command uses the Get-Credential cmdlet to get the Administrator credentials and then stores them in the $cred variable.</span></span>
<span data-ttu-id="c304f-124">**Get-Credential** solicita uma senha de nome de usuário e senha por meio de uma caixa de diálogo ou na linha de comando, dependendo das configurações do registro do sistema.</span><span class="sxs-lookup"><span data-stu-id="c304f-124">**Get-Credential** prompts you for a password of username and password through a dialog box or at the command line, depending on system registry settings.</span></span>

<span data-ttu-id="c304f-125">O segundo comando usa o parâmetro *Credential* para passar as credenciais armazenadas em $cred para **conectar-WSMan**.</span><span class="sxs-lookup"><span data-stu-id="c304f-125">The second command uses the *Credential* parameter to pass the credentials stored in $cred to **Connect-WSMan**.</span></span>
<span data-ttu-id="c304f-126">**Connect-WSMan** , em seguida, conecta-se ao sistema remoto Server01 usando as credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="c304f-126">**Connect-WSMan** then connects to the remote system server01 by using the Administrator credentials.</span></span>

### <span data-ttu-id="c304f-127">Exemplo 3: conectar-se a um computador remoto em uma porta especificada</span><span class="sxs-lookup"><span data-stu-id="c304f-127">Example 3: Connect to a remote computer over a specified port</span></span>

```
PS C:\> Connect-WSMan -ComputerName "server01" -Port 80
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan
ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

<span data-ttu-id="c304f-128">Este comando cria uma conexão com o computador remoto server01 pela porta 80.</span><span class="sxs-lookup"><span data-stu-id="c304f-128">This command creates a connection to the remote server01 computer over port 80.</span></span>

### <span data-ttu-id="c304f-129">Exemplo 4: conectar-se a um computador remoto usando as opções de conexão</span><span class="sxs-lookup"><span data-stu-id="c304f-129">Example 4: Connect to a remote computer by using connection options</span></span>

```
PS C:\> $a = New-WSManSessionOption -OperationTimeout 30000
PS C:\> Connect-WSMan -ComputerName "server01" -SessionOption $a
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan
ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

<span data-ttu-id="c304f-130">Este exemplo cria uma conexão com o computador remoto Server01 usando as opções de conexão definidas no comando **New-WSManSessionOption** .</span><span class="sxs-lookup"><span data-stu-id="c304f-130">This example creates a connection to the remote server01 computer by using the connection options that are defined in the **New-WSManSessionOption** command.</span></span>

<span data-ttu-id="c304f-131">O primeiro comando usa **New-WSManSessionOption** para armazenar um conjunto de opções de configuração de conexão na variável $a.</span><span class="sxs-lookup"><span data-stu-id="c304f-131">The first command uses **New-WSManSessionOption** to store a set of connection setting options in the $a variable.</span></span>
<span data-ttu-id="c304f-132">Nesse caso, as opções da sessão definem um tempo de conexão de 30 segundos (30.000 milissegundos).</span><span class="sxs-lookup"><span data-stu-id="c304f-132">In this case, the session options set a connection time out of 30 seconds (30,000 milliseconds).</span></span>

<span data-ttu-id="c304f-133">O segundo comando usa o parâmetro *SessionOption* para passar as credenciais que são armazenadas na variável $A para **Connect-WSMan**.</span><span class="sxs-lookup"><span data-stu-id="c304f-133">The second command uses the *SessionOption* parameter to pass the credentials that are stored in the $a variable to **Connect-WSMan**.</span></span>
<span data-ttu-id="c304f-134">Em seguida, **Connect-WSMan** se conecta ao computador remoto Server01 usando as opções de sessão especificadas.</span><span class="sxs-lookup"><span data-stu-id="c304f-134">Then, **Connect-WSMan** connects to the remote server01 computer by using the specified session options.</span></span>

## <span data-ttu-id="c304f-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c304f-135">PARAMETERS</span></span>

### <span data-ttu-id="c304f-136">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="c304f-136">-ApplicationName</span></span>
<span data-ttu-id="c304f-137">Especifica o nome do aplicativo na conexão.</span><span class="sxs-lookup"><span data-stu-id="c304f-137">Specifies the application name in the connection.</span></span>
<span data-ttu-id="c304f-138">O valor padrão do parâmetro *ApplicationName* é WSMan.</span><span class="sxs-lookup"><span data-stu-id="c304f-138">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="c304f-139">O identificador completo para o ponto de extremidade remoto é no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="c304f-139">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="c304f-140">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="c304f-140">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="c304f-141">Por exemplo: `http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="c304f-141">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="c304f-142">Os Serviços de Informações da Internet (IIS), que hospedam a sessão, encaminham solicitações com esse ponto de extremidade para o aplicativo especificado.</span><span class="sxs-lookup"><span data-stu-id="c304f-142">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="c304f-143">Essa configuração padrão de WSMAN é apropriada para a maioria dos usos.</span><span class="sxs-lookup"><span data-stu-id="c304f-143">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="c304f-144">Esse parâmetro é projetado para ser usado se muitos computadores estabelecerem conexões remotas com um computador que esteja executando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c304f-144">This parameter is designed to be used if many computers establish remote connections to one computer that is running PowerShell.</span></span>
<span data-ttu-id="c304f-145">Nesse caso, o IIS hospeda o Web Services for Management (WS-Management) para ter eficiência.</span><span class="sxs-lookup"><span data-stu-id="c304f-145">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

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

### <span data-ttu-id="c304f-146">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="c304f-146">-Authentication</span></span>
<span data-ttu-id="c304f-147">Especifica o mecanismo de autenticação a ser usado no servidor.</span><span class="sxs-lookup"><span data-stu-id="c304f-147">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="c304f-148">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="c304f-148">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="c304f-149">Básica.</span><span class="sxs-lookup"><span data-stu-id="c304f-149">Basic.</span></span>
<span data-ttu-id="c304f-150">É um esquema no qual o nome de usuário e senha são enviados em texto não criptografado para o servidor ou proxy.</span><span class="sxs-lookup"><span data-stu-id="c304f-150">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="c304f-151">Padrão.</span><span class="sxs-lookup"><span data-stu-id="c304f-151">Default.</span></span>
<span data-ttu-id="c304f-152">Utiliza o método de autenticação implementado pelo protocolo WS-Management.</span><span class="sxs-lookup"><span data-stu-id="c304f-152">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="c304f-153">Este é o padrão.</span><span class="sxs-lookup"><span data-stu-id="c304f-153">This is the default.</span></span>
- <span data-ttu-id="c304f-154">Digest.</span><span class="sxs-lookup"><span data-stu-id="c304f-154">Digest.</span></span>
<span data-ttu-id="c304f-155">É um esquema de desafio/resposta que utiliza uma cadeia de caracteres de dados do servidor especificada para o desafio.</span><span class="sxs-lookup"><span data-stu-id="c304f-155">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="c304f-156">Kerberos.</span><span class="sxs-lookup"><span data-stu-id="c304f-156">Kerberos.</span></span>
<span data-ttu-id="c304f-157">O computador cliente e o servidor autenticam mutuamente utilizando certificados Kerberos.</span><span class="sxs-lookup"><span data-stu-id="c304f-157">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="c304f-158">Negotiate.</span><span class="sxs-lookup"><span data-stu-id="c304f-158">Negotiate.</span></span>
<span data-ttu-id="c304f-159">É um esquema de desafio/resposta que negocia com o servidor ou proxy para determinar o esquema a ser utilizado para autenticação.</span><span class="sxs-lookup"><span data-stu-id="c304f-159">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="c304f-160">Por exemplo, esse valor de parâmetro permite que a negociação determine se o protocolo Kerberos ou NTLM é usado.</span><span class="sxs-lookup"><span data-stu-id="c304f-160">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="c304f-161">CredSSP.</span><span class="sxs-lookup"><span data-stu-id="c304f-161">CredSSP.</span></span>
<span data-ttu-id="c304f-162">Use a autenticação do Credential Security Support Provider (CredSSP), que permite que o usuário delegue as credenciais.</span><span class="sxs-lookup"><span data-stu-id="c304f-162">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="c304f-163">Esta opção foi criada para os comandos executados em um computador remoto, mas coletam dados ou executam comandos adicionais em outros computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="c304f-163">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="c304f-164">Cuidado: o CredSSP Delega as credenciais do usuário do computador local para um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="c304f-164">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="c304f-165">Essa prática aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="c304f-165">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="c304f-166">Se o computador remoto estiver comprometido, no momento em que as credenciais forem passadas a ele essas credenciais poderão ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="c304f-166">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="c304f-167">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="c304f-167">-CertificateThumbprint</span></span>
<span data-ttu-id="c304f-168">Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa ação.</span><span class="sxs-lookup"><span data-stu-id="c304f-168">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="c304f-169">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="c304f-169">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="c304f-170">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="c304f-170">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="c304f-171">Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="c304f-171">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="c304f-172">Para obter uma impressão digital do certificado, use o comando Get-Item ou Get-ChildItem na unidade certificado do PowerShell:.</span><span class="sxs-lookup"><span data-stu-id="c304f-172">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="c304f-173">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="c304f-173">-ComputerName</span></span>
<span data-ttu-id="c304f-174">Especifica o computador no qual executar a operação de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="c304f-174">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="c304f-175">O valor pode ser um nome de domínio totalmente qualificado, um nome NetBIOS ou um endereço IP.</span><span class="sxs-lookup"><span data-stu-id="c304f-175">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="c304f-176">Utilize o nome do computador local, o localhost ou um ponto (.) para especificar o computador local.</span><span class="sxs-lookup"><span data-stu-id="c304f-176">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="c304f-177">O computador local é o padrão.</span><span class="sxs-lookup"><span data-stu-id="c304f-177">The local computer is the default.</span></span>
<span data-ttu-id="c304f-178">Quando o computador remoto está em um domínio diferente do usuário, deve-se usar um nome de domínio totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="c304f-178">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="c304f-179">É possível redirecionar um valor desse parâmetro para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c304f-179">You can pipe a value for this parameter to the cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases: cn

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c304f-180">-Conexãouri</span><span class="sxs-lookup"><span data-stu-id="c304f-180">-ConnectionURI</span></span>
<span data-ttu-id="c304f-181">Especifica o ponto de extremidade de conexão.</span><span class="sxs-lookup"><span data-stu-id="c304f-181">Specifies the connection endpoint.</span></span>
<span data-ttu-id="c304f-182">O formato dessa cadeia de caracteres é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c304f-182">The format of this string is as follows:</span></span>

<span data-ttu-id="c304f-183">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="c304f-183">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="c304f-184">A cadeia de caracteres a seguir é um valor formatado corretamente para este parâmetro:</span><span class="sxs-lookup"><span data-stu-id="c304f-184">The following string is a correctly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="c304f-185">O URI deve ser totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="c304f-185">The URI must be fully qualified.</span></span>

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

### <span data-ttu-id="c304f-186">-Credential</span><span class="sxs-lookup"><span data-stu-id="c304f-186">-Credential</span></span>
<span data-ttu-id="c304f-187">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="c304f-187">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="c304f-188">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="c304f-188">The default is the current user.</span></span>
<span data-ttu-id="c304f-189">Digite um nome de usuário, como User01, Domínio01 \ Usuário01 ou User@Domain.com .</span><span class="sxs-lookup"><span data-stu-id="c304f-189">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="c304f-190">Ou insira um objeto **PSCredential** , como um retornado pelo cmdlet Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="c304f-190">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="c304f-191">Quando você digita um nome de usuário, esse cmdlet solicita uma senha.</span><span class="sxs-lookup"><span data-stu-id="c304f-191">When you type a user name, this cmdlet prompts you for a password.</span></span>

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

### <span data-ttu-id="c304f-192">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="c304f-192">-OptionSet</span></span>
<span data-ttu-id="c304f-193">Especifica um conjunto de opções para um serviço para modificar ou refinar a natureza da solicitação.</span><span class="sxs-lookup"><span data-stu-id="c304f-193">Specifies a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="c304f-194">Elas se assemelham a opções usadas em shells de linha de comando porque são específicas de serviço.</span><span class="sxs-lookup"><span data-stu-id="c304f-194">These resemble switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="c304f-195">Qualquer número de opções pode ser especificado.</span><span class="sxs-lookup"><span data-stu-id="c304f-195">Any number of options can be specified.</span></span>

<span data-ttu-id="c304f-196">O exemplo a seguir demonstra a sintaxe que passa os valores 1, 2 e 3 para os parâmetros a, b e c:</span><span class="sxs-lookup"><span data-stu-id="c304f-196">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

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

### <span data-ttu-id="c304f-197">-Port</span><span class="sxs-lookup"><span data-stu-id="c304f-197">-Port</span></span>
<span data-ttu-id="c304f-198">Especifica a porta a ser usada quando o cliente se conecta ao serviço WinRM.</span><span class="sxs-lookup"><span data-stu-id="c304f-198">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="c304f-199">Quando o transporte é HTTP, a porta padrão é 80.</span><span class="sxs-lookup"><span data-stu-id="c304f-199">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="c304f-200">Quando o transporte é HTTPS, a porta padrão é 443.</span><span class="sxs-lookup"><span data-stu-id="c304f-200">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="c304f-201">Quando você usa HTTPS como o transporte, o valor do parâmetro *ComputerName* deve corresponder ao CN (nome comum) do certificado do servidor.</span><span class="sxs-lookup"><span data-stu-id="c304f-201">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="c304f-202">No entanto, se o parâmetro *SkipCNCheck* for especificado como parte do parâmetro *SessionOption* , o nome comum do certificado do servidor não precisará corresponder ao nome do host do servidor.</span><span class="sxs-lookup"><span data-stu-id="c304f-202">However, if the *SkipCNCheck* parameter is specified as part of the *SessionOption* parameter, the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="c304f-203">O parâmetro *SkipCNCheck* deve ser usado somente para computadores confiáveis.</span><span class="sxs-lookup"><span data-stu-id="c304f-203">The *SkipCNCheck* parameter should be used only for trusted computers.</span></span>

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

### <span data-ttu-id="c304f-204">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="c304f-204">-SessionOption</span></span>
<span data-ttu-id="c304f-205">Especifica as opções estendidas para a sessão de WS-Management.</span><span class="sxs-lookup"><span data-stu-id="c304f-205">Specifies extended options for the WS-Management session.</span></span>
<span data-ttu-id="c304f-206">Insira um objeto **SessionOption** que você cria usando o cmdlet New-WSManSessionOption.</span><span class="sxs-lookup"><span data-stu-id="c304f-206">Enter a **SessionOption** object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="c304f-207">Para obter mais informações sobre as opções disponíveis, digite `Get-Help New-WSManSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="c304f-207">For more information about the options that are available, type `Get-Help New-WSManSessionOption`.</span></span>

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

### <span data-ttu-id="c304f-208">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="c304f-208">-UseSSL</span></span>
<span data-ttu-id="c304f-209">Especifica que o protocolo de protocolo SSL (SSL) é usado para estabelecer uma conexão com o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="c304f-209">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="c304f-210">Por padrão, SSL não é usado.</span><span class="sxs-lookup"><span data-stu-id="c304f-210">By default, SSL is not used.</span></span>

<span data-ttu-id="c304f-211">WS-Management criptografa todo o conteúdo do PowerShell que é transmitido pela rede.</span><span class="sxs-lookup"><span data-stu-id="c304f-211">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="c304f-212">O parâmetro *UseSSL* permite especificar a proteção adicional do HTTPS em vez de http.</span><span class="sxs-lookup"><span data-stu-id="c304f-212">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="c304f-213">Se o SSL não estiver disponível na porta que é usada para a conexão e você especificar esse parâmetro, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="c304f-213">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="c304f-214">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c304f-214">CommonParameters</span></span>
<span data-ttu-id="c304f-215">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c304f-215">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c304f-216">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c304f-216">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c304f-217">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="c304f-217">INPUTS</span></span>

### <span data-ttu-id="c304f-218">Nenhum</span><span class="sxs-lookup"><span data-stu-id="c304f-218">None</span></span>
<span data-ttu-id="c304f-219">Esse cmdlet não aceita nenhuma entrada.</span><span class="sxs-lookup"><span data-stu-id="c304f-219">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="c304f-220">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="c304f-220">OUTPUTS</span></span>

### <span data-ttu-id="c304f-221">Nenhum</span><span class="sxs-lookup"><span data-stu-id="c304f-221">None</span></span>
<span data-ttu-id="c304f-222">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="c304f-222">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="c304f-223">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="c304f-223">NOTES</span></span>

* <span data-ttu-id="c304f-224">Você pode executar comandos de gerenciamento ou consultar dados de gerenciamento em um computador remoto sem criar uma sessão WS-Management.</span><span class="sxs-lookup"><span data-stu-id="c304f-224">You can run management commands or query management data on a remote computer without creating a WS-Management session.</span></span> <span data-ttu-id="c304f-225">Você pode fazer isso usando os parâmetros *ComputerName* de Invoke-WSManAction e Get-WSManInstance.</span><span class="sxs-lookup"><span data-stu-id="c304f-225">You can do this by using the *ComputerName* parameters of Invoke-WSManAction and Get-WSManInstance.</span></span> <span data-ttu-id="c304f-226">Quando você usa o parâmetro *ComputerName* , o PowerShell cria uma conexão temporária que é usada para o comando único.</span><span class="sxs-lookup"><span data-stu-id="c304f-226">When you use the *ComputerName* parameter, PowerShell creates a temporary connection that is used for the single command.</span></span> <span data-ttu-id="c304f-227">Depois que o comando é executado, a conexão é fechada.</span><span class="sxs-lookup"><span data-stu-id="c304f-227">After the command runs, the connection is closed.</span></span>

*

## <span data-ttu-id="c304f-228">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="c304f-228">RELATED LINKS</span></span>

[<span data-ttu-id="c304f-229">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="c304f-229">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="c304f-230">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="c304f-230">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="c304f-231">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="c304f-231">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="c304f-232">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="c304f-232">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="c304f-233">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="c304f-233">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="c304f-234">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="c304f-234">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="c304f-235">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="c304f-235">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="c304f-236">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="c304f-236">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="c304f-237">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="c304f-237">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="c304f-238">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="c304f-238">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="c304f-239">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="c304f-239">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="c304f-240">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="c304f-240">Test-WSMan</span></span>](Test-WSMan.md)

