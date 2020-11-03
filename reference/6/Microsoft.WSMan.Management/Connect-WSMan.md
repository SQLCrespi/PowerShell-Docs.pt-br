---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/connect-wsman?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Connect-WSMan
ms.openlocfilehash: d06ede0e27713b1a309aa2ed265f02881d34124e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194588"
---
# <span data-ttu-id="1ca5c-103">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="1ca5c-103">Connect-WSMan</span></span>

## <span data-ttu-id="1ca5c-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="1ca5c-104">SYNOPSIS</span></span>
<span data-ttu-id="1ca5c-105">Conecta-se ao serviço WinRM em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-105">Connects to the WinRM service on a remote computer.</span></span>

## <span data-ttu-id="1ca5c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1ca5c-106">SYNTAX</span></span>

### <span data-ttu-id="1ca5c-107">ComputerName (padrão)</span><span class="sxs-lookup"><span data-stu-id="1ca5c-107">ComputerName (Default)</span></span>

```
Connect-WSMan [-ApplicationName <String>] [[-ComputerName] <String>] [-OptionSet <Hashtable>] [-Port <Int32>]
 [-SessionOption <SessionOption>] [-UseSSL] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="1ca5c-108">URI</span><span class="sxs-lookup"><span data-stu-id="1ca5c-108">URI</span></span>

```
Connect-WSMan [-ConnectionURI <Uri>] [-OptionSet <Hashtable>] [-Port <Int32>] [-SessionOption <SessionOption>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="1ca5c-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1ca5c-109">DESCRIPTION</span></span>
<span data-ttu-id="1ca5c-110">O cmdlet **Connect-WSMan conecta-** se ao serviço WinRM em um computador remoto e estabelece uma conexão persistente com o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-110">The **Connect-WSMan** cmdlet connects to the WinRM service on a remote computer, and it establishes a persistent connection to the remote computer.</span></span>
<span data-ttu-id="1ca5c-111">Você pode usar esse cmdlet no contexto do provedor WSMan para se conectar ao serviço WinRM em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-111">You can use this cmdlet in the context of the WSMan provider to connect to the WinRM service on a remote computer.</span></span>
<span data-ttu-id="1ca5c-112">No entanto, você também pode usar este cmdlet para se conectar ao serviço WinRM em um computador remoto antes de alterar para o provedor WSMan.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-112">However, you can also use this cmdlet to connect to the WinRM service on a remote computer before you change to the WSMan provider.</span></span>
<span data-ttu-id="1ca5c-113">O computador remoto aparece no diretório raiz do provedor WSMan.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-113">The remote computer appears in the root directory of the WSMan provider.</span></span>

<span data-ttu-id="1ca5c-114">Credenciais explícitas são necessárias quando os computadores cliente e servidor estiverem em domínios ou grupos de trabalho diferentes.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-114">Explicit credentials are required when the client and server computers are in different domains or workgroups.</span></span>

<span data-ttu-id="1ca5c-115">Para obter informações sobre como se desconectar do serviço WinRM em um computador remoto, consulte o cmdlet Disconnect-WSMan.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-115">For information about how to disconnect from the WinRM service on a remote computer, see the Disconnect-WSMan cmdlet.</span></span>

## <span data-ttu-id="1ca5c-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="1ca5c-116">EXAMPLES</span></span>

### <span data-ttu-id="1ca5c-117">Exemplo 1: conectar-se a um computador remoto</span><span class="sxs-lookup"><span data-stu-id="1ca5c-117">Example 1: Connect to a remote computer</span></span>

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

<span data-ttu-id="1ca5c-118">Este comando cria uma conexão com o computador remoto server01.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-118">This command creates a connection to the remote server01 computer.</span></span>

<span data-ttu-id="1ca5c-119">O cmdlet **Connect-WSMan** geralmente é usado no contexto do provedor WSMan para se conectar a um computador remoto, neste caso, o computador Server01.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-119">The **Connect-WSMan** cmdlet is generally used in the context of the WSMan provider to connect to a remote computer, in this case the server01 computer.</span></span>
<span data-ttu-id="1ca5c-120">No entanto, você pode usar o cmdlet para estabelecer conexões com computadores remotos, antes de alterar para o provedor WSMan.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-120">However, you can use the cmdlet to establish connections to remote computers before you change to the WSMan provider.</span></span>
<span data-ttu-id="1ca5c-121">Essas conexões aparecem na lista **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="1ca5c-121">Those connections appear in the **ComputerName** list.</span></span>

### <span data-ttu-id="1ca5c-122">Exemplo 2: conectar-se a um computador remoto usando credenciais de administrador</span><span class="sxs-lookup"><span data-stu-id="1ca5c-122">Example 2: Connect to a remote computer by using Administrator credentials</span></span>

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

<span data-ttu-id="1ca5c-123">Este comando cria uma conexão com o sistema remoto server01 usando as credenciais da conta do Administrador.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-123">This command creates a connection to the remote system server01 using the Administrator account credentials.</span></span>

<span data-ttu-id="1ca5c-124">O primeiro comando usa o cmdlet Get-Credential para obter as credenciais do Administrador e as armazena na variável $cred.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-124">The first command uses the Get-Credential cmdlet to get the Administrator credentials and then stores them in the $cred variable.</span></span>
<span data-ttu-id="1ca5c-125">**Get-Credential** solicita uma senha de nome de usuário e senha por meio de uma caixa de diálogo ou na linha de comando, dependendo das configurações do registro do sistema.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-125">**Get-Credential** prompts you for a password of username and password through a dialog box or at the command line, depending on system registry settings.</span></span>

<span data-ttu-id="1ca5c-126">O segundo comando usa o parâmetro *Credential* para passar as credenciais armazenadas em $cred para **conectar-WSMan** .</span><span class="sxs-lookup"><span data-stu-id="1ca5c-126">The second command uses the *Credential* parameter to pass the credentials stored in $cred to **Connect-WSMan** .</span></span>
<span data-ttu-id="1ca5c-127">**Connect-WSMan** , em seguida, conecta-se ao sistema remoto Server01 usando as credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-127">**Connect-WSMan** then connects to the remote system server01 by using the Administrator credentials.</span></span>

### <span data-ttu-id="1ca5c-128">Exemplo 3: conectar-se a um computador remoto em uma porta especificada</span><span class="sxs-lookup"><span data-stu-id="1ca5c-128">Example 3: Connect to a remote computer over a specified port</span></span>

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

<span data-ttu-id="1ca5c-129">Este comando cria uma conexão com o computador remoto server01 pela porta 80.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-129">This command creates a connection to the remote server01 computer over port 80.</span></span>

### <span data-ttu-id="1ca5c-130">Exemplo 4: conectar-se a um computador remoto usando as opções de conexão</span><span class="sxs-lookup"><span data-stu-id="1ca5c-130">Example 4: Connect to a remote computer by using connection options</span></span>

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

<span data-ttu-id="1ca5c-131">Este exemplo cria uma conexão com o computador remoto Server01 usando as opções de conexão definidas no comando **New-WSManSessionOption** .</span><span class="sxs-lookup"><span data-stu-id="1ca5c-131">This example creates a connection to the remote server01 computer by using the connection options that are defined in the **New-WSManSessionOption** command.</span></span>

<span data-ttu-id="1ca5c-132">O primeiro comando usa **New-WSManSessionOption** para armazenar um conjunto de opções de configuração de conexão na variável $a.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-132">The first command uses **New-WSManSessionOption** to store a set of connection setting options in the $a variable.</span></span>
<span data-ttu-id="1ca5c-133">Nesse caso, as opções da sessão definem um tempo de conexão de 30 segundos (30.000 milissegundos).</span><span class="sxs-lookup"><span data-stu-id="1ca5c-133">In this case, the session options set a connection time out of 30 seconds (30,000 milliseconds).</span></span>

<span data-ttu-id="1ca5c-134">O segundo comando usa o parâmetro *SessionOption* para passar as credenciais que são armazenadas na variável $A para **Connect-WSMan** .</span><span class="sxs-lookup"><span data-stu-id="1ca5c-134">The second command uses the *SessionOption* parameter to pass the credentials that are stored in the $a variable to **Connect-WSMan** .</span></span>
<span data-ttu-id="1ca5c-135">Em seguida, **Connect-WSMan** se conecta ao computador remoto Server01 usando as opções de sessão especificadas.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-135">Then, **Connect-WSMan** connects to the remote server01 computer by using the specified session options.</span></span>

## <span data-ttu-id="1ca5c-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1ca5c-136">PARAMETERS</span></span>

### <span data-ttu-id="1ca5c-137">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="1ca5c-137">-ApplicationName</span></span>
<span data-ttu-id="1ca5c-138">Especifica o nome do aplicativo na conexão.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-138">Specifies the application name in the connection.</span></span>
<span data-ttu-id="1ca5c-139">O valor padrão do parâmetro *ApplicationName* é WSMan.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-139">The default value of the *ApplicationName* parameter is WSMAN.</span></span>
<span data-ttu-id="1ca5c-140">O identificador completo para o ponto de extremidade remoto é no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="1ca5c-140">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="1ca5c-141">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="1ca5c-141">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="1ca5c-142">Por exemplo: `http://server01:8080/WSMAN`</span><span class="sxs-lookup"><span data-stu-id="1ca5c-142">For example: `http://server01:8080/WSMAN`</span></span>

<span data-ttu-id="1ca5c-143">Os Serviços de Informações da Internet (IIS), que hospedam a sessão, encaminham solicitações com esse ponto de extremidade para o aplicativo especificado.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-143">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="1ca5c-144">Essa configuração padrão de WSMAN é apropriada para a maioria dos usos.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-144">This default setting of WSMAN is appropriate for most uses.</span></span>
<span data-ttu-id="1ca5c-145">Esse parâmetro é projetado para ser usado se muitos computadores estabelecerem conexões remotas com um computador que esteja executando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-145">This parameter is designed to be used if many computers establish remote connections to one computer that is running PowerShell.</span></span>
<span data-ttu-id="1ca5c-146">Nesse caso, o IIS hospeda o Web Services for Management (WS-Management) para ter eficiência.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-146">In this case, IIS hosts Web Services for Management (WS-Management) for efficiency.</span></span>

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

### <span data-ttu-id="1ca5c-147">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="1ca5c-147">-Authentication</span></span>
<span data-ttu-id="1ca5c-148">Especifica o mecanismo de autenticação a ser usado no servidor.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-148">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="1ca5c-149">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="1ca5c-149">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="1ca5c-150">Básica.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-150">Basic.</span></span>
<span data-ttu-id="1ca5c-151">É um esquema no qual o nome de usuário e senha são enviados em texto não criptografado para o servidor ou proxy.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-151">Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="1ca5c-152">Padrão.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-152">Default.</span></span>
<span data-ttu-id="1ca5c-153">Utiliza o método de autenticação implementado pelo protocolo WS-Management.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-153">Use the authentication method implemented by the WS-Management protocol.</span></span>
<span data-ttu-id="1ca5c-154">Esse é o padrão.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-154">This is the default.</span></span>
- <span data-ttu-id="1ca5c-155">Digest.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-155">Digest.</span></span>
<span data-ttu-id="1ca5c-156">É um esquema de desafio/resposta que utiliza uma cadeia de caracteres de dados do servidor especificada para o desafio.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-156">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="1ca5c-157">Kerberos.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-157">Kerberos.</span></span>
<span data-ttu-id="1ca5c-158">O computador cliente e o servidor autenticam mutuamente utilizando certificados Kerberos.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-158">The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="1ca5c-159">Negotiate.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-159">Negotiate.</span></span>
<span data-ttu-id="1ca5c-160">É um esquema de desafio/resposta que negocia com o servidor ou proxy para determinar o esquema a ser utilizado para autenticação.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-160">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span>
<span data-ttu-id="1ca5c-161">Por exemplo, esse valor de parâmetro permite que a negociação determine se o protocolo Kerberos ou NTLM é usado.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-161">For example, this parameter value allows for negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="1ca5c-162">CredSSP.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-162">CredSSP.</span></span>
<span data-ttu-id="1ca5c-163">Use a autenticação do Credential Security Support Provider (CredSSP), que permite que o usuário delegue as credenciais.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-163">Use Credential Security Support Provider (CredSSP) authentication, which lets the user delegate credentials.</span></span>
<span data-ttu-id="1ca5c-164">Esta opção foi criada para os comandos executados em um computador remoto, mas coletam dados ou executam comandos adicionais em outros computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-164">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="1ca5c-165">Cuidado: o CredSSP Delega as credenciais do usuário do computador local para um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-165">Caution: CredSSP delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="1ca5c-166">Essa prática aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-166">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="1ca5c-167">Se o computador remoto estiver comprometido, no momento em que as credenciais forem passadas a ele essas credenciais poderão ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-167">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

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

### <span data-ttu-id="1ca5c-168">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="1ca5c-168">-CertificateThumbprint</span></span>
<span data-ttu-id="1ca5c-169">Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa ação.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-169">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="1ca5c-170">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-170">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="1ca5c-171">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-171">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="1ca5c-172">Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-172">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="1ca5c-173">Para obter uma impressão digital do certificado, use o comando Get-Item ou Get-ChildItem na unidade certificado do PowerShell:.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-173">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="1ca5c-174">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="1ca5c-174">-ComputerName</span></span>
<span data-ttu-id="1ca5c-175">Especifica o computador no qual executar a operação de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-175">Specifies the computer against which to run the management operation.</span></span>
<span data-ttu-id="1ca5c-176">O valor pode ser um nome de domínio totalmente qualificado, um nome NetBIOS ou um endereço IP.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-176">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="1ca5c-177">Utilize o nome do computador local, o localhost ou um ponto (.) para especificar o computador local.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-177">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="1ca5c-178">O computador local é o padrão.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-178">The local computer is the default.</span></span>
<span data-ttu-id="1ca5c-179">Quando o computador remoto está em um domínio diferente do usuário, deve-se usar um nome de domínio totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-179">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="1ca5c-180">É possível redirecionar um valor desse parâmetro para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-180">You can pipe a value for this parameter to the cmdlet.</span></span>

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

### <span data-ttu-id="1ca5c-181">-Conexãouri</span><span class="sxs-lookup"><span data-stu-id="1ca5c-181">-ConnectionURI</span></span>
<span data-ttu-id="1ca5c-182">Especifica o ponto de extremidade de conexão.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-182">Specifies the connection endpoint.</span></span>
<span data-ttu-id="1ca5c-183">O formato dessa cadeia de caracteres é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1ca5c-183">The format of this string is as follows:</span></span>

<span data-ttu-id="1ca5c-184">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="1ca5c-184">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="1ca5c-185">A cadeia de caracteres a seguir é um valor formatado corretamente para este parâmetro:</span><span class="sxs-lookup"><span data-stu-id="1ca5c-185">The following string is a correctly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="1ca5c-186">O URI deve ser totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-186">The URI must be fully qualified.</span></span>

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

### <span data-ttu-id="1ca5c-187">-Credential</span><span class="sxs-lookup"><span data-stu-id="1ca5c-187">-Credential</span></span>
<span data-ttu-id="1ca5c-188">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-188">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="1ca5c-189">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-189">The default is the current user.</span></span>
<span data-ttu-id="1ca5c-190">Digite um nome de usuário, como User01, Domínio01 \ Usuário01 ou User@Domain.com .</span><span class="sxs-lookup"><span data-stu-id="1ca5c-190">Type a user name, such as User01, Domain01\User01, or User@Domain.com.</span></span>
<span data-ttu-id="1ca5c-191">Ou insira um objeto **PSCredential** , como um retornado pelo cmdlet Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-191">Or, enter a **PSCredential** object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="1ca5c-192">Quando você digita um nome de usuário, esse cmdlet solicita uma senha.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-192">When you type a user name, this cmdlet prompts you for a password.</span></span>

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

### <span data-ttu-id="1ca5c-193">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="1ca5c-193">-OptionSet</span></span>
<span data-ttu-id="1ca5c-194">Especifica um conjunto de opções para um serviço para modificar ou refinar a natureza da solicitação.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-194">Specifies a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="1ca5c-195">Elas se assemelham a opções usadas em shells de linha de comando porque são específicas de serviço.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-195">These resemble switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="1ca5c-196">Qualquer número de opções pode ser especificado.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-196">Any number of options can be specified.</span></span>

<span data-ttu-id="1ca5c-197">O exemplo a seguir demonstra a sintaxe que passa os valores 1, 2 e 3 para os parâmetros a, b e c:</span><span class="sxs-lookup"><span data-stu-id="1ca5c-197">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

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

### <span data-ttu-id="1ca5c-198">-Port</span><span class="sxs-lookup"><span data-stu-id="1ca5c-198">-Port</span></span>
<span data-ttu-id="1ca5c-199">Especifica a porta a ser usada quando o cliente se conecta ao serviço WinRM.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-199">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="1ca5c-200">Quando o transporte é HTTP, a porta padrão é 80.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-200">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="1ca5c-201">Quando o transporte é HTTPS, a porta padrão é 443.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-201">When the transport is HTTPS, the default port is 443.</span></span>

<span data-ttu-id="1ca5c-202">Quando você usa HTTPS como o transporte, o valor do parâmetro *ComputerName* deve corresponder ao CN (nome comum) do certificado do servidor.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-202">When you use HTTPS as the transport, the value of the *ComputerName* parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="1ca5c-203">No entanto, se o parâmetro *SkipCNCheck* for especificado como parte do parâmetro *SessionOption* , o nome comum do certificado do servidor não precisará corresponder ao nome do host do servidor.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-203">However, if the *SkipCNCheck* parameter is specified as part of the *SessionOption* parameter, the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="1ca5c-204">O parâmetro *SkipCNCheck* deve ser usado somente para computadores confiáveis.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-204">The *SkipCNCheck* parameter should be used only for trusted computers.</span></span>

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

### <span data-ttu-id="1ca5c-205">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="1ca5c-205">-SessionOption</span></span>
<span data-ttu-id="1ca5c-206">Especifica as opções estendidas para a sessão de WS-Management.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-206">Specifies extended options for the WS-Management session.</span></span>
<span data-ttu-id="1ca5c-207">Insira um objeto **SessionOption** que você cria usando o cmdlet New-WSManSessionOption.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-207">Enter a **SessionOption** object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="1ca5c-208">Para obter mais informações sobre as opções disponíveis, digite `Get-Help New-WSManSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="1ca5c-208">For more information about the options that are available, type `Get-Help New-WSManSessionOption`.</span></span>

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

### <span data-ttu-id="1ca5c-209">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="1ca5c-209">-UseSSL</span></span>
<span data-ttu-id="1ca5c-210">Especifica que o protocolo de protocolo SSL (SSL) é usado para estabelecer uma conexão com o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-210">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="1ca5c-211">Por padrão, SSL não é usado.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-211">By default, SSL is not used.</span></span>

<span data-ttu-id="1ca5c-212">WS-Management criptografa todo o conteúdo do PowerShell que é transmitido pela rede.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-212">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="1ca5c-213">O parâmetro *UseSSL* permite especificar a proteção adicional do HTTPS em vez de http.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-213">The *UseSSL* parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="1ca5c-214">Se o SSL não estiver disponível na porta que é usada para a conexão e você especificar esse parâmetro, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-214">If SSL is not available on the port that is used for the connection, and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="1ca5c-215">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1ca5c-215">CommonParameters</span></span>
<span data-ttu-id="1ca5c-216">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-216">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1ca5c-217">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1ca5c-217">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1ca5c-218">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="1ca5c-218">INPUTS</span></span>

### <span data-ttu-id="1ca5c-219">Nenhum</span><span class="sxs-lookup"><span data-stu-id="1ca5c-219">None</span></span>
<span data-ttu-id="1ca5c-220">Esse cmdlet não aceita nenhuma entrada.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-220">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="1ca5c-221">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="1ca5c-221">OUTPUTS</span></span>

### <span data-ttu-id="1ca5c-222">Nenhum</span><span class="sxs-lookup"><span data-stu-id="1ca5c-222">None</span></span>
<span data-ttu-id="1ca5c-223">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-223">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="1ca5c-224">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="1ca5c-224">NOTES</span></span>

* <span data-ttu-id="1ca5c-225">Você pode executar comandos de gerenciamento ou consultar dados de gerenciamento em um computador remoto sem criar uma sessão WS-Management.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-225">You can run management commands or query management data on a remote computer without creating a WS-Management session.</span></span> <span data-ttu-id="1ca5c-226">Você pode fazer isso usando os parâmetros *ComputerName* de Invoke-WSManAction e Get-WSManInstance.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-226">You can do this by using the *ComputerName* parameters of Invoke-WSManAction and Get-WSManInstance.</span></span> <span data-ttu-id="1ca5c-227">Quando você usa o parâmetro *ComputerName* , o PowerShell cria uma conexão temporária que é usada para o comando único.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-227">When you use the *ComputerName* parameter, PowerShell creates a temporary connection that is used for the single command.</span></span> <span data-ttu-id="1ca5c-228">Depois que o comando é executado, a conexão é fechada.</span><span class="sxs-lookup"><span data-stu-id="1ca5c-228">After the command runs, the connection is closed.</span></span>

*

## <span data-ttu-id="1ca5c-229">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="1ca5c-229">RELATED LINKS</span></span>

[<span data-ttu-id="1ca5c-230">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="1ca5c-230">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="1ca5c-231">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="1ca5c-231">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="1ca5c-232">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="1ca5c-232">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="1ca5c-233">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="1ca5c-233">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="1ca5c-234">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="1ca5c-234">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="1ca5c-235">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="1ca5c-235">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="1ca5c-236">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="1ca5c-236">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="1ca5c-237">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="1ca5c-237">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="1ca5c-238">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="1ca5c-238">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="1ca5c-239">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="1ca5c-239">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="1ca5c-240">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="1ca5c-240">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="1ca5c-241">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="1ca5c-241">Test-WSMan</span></span>](Test-WSMan.md)
