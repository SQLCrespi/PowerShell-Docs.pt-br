---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/set-wsmaninstance?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WSManInstance
ms.openlocfilehash: 9060f683372617b3a01365ceb81668c75986f46d
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93195011"
---
# <span data-ttu-id="2ffd9-103">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="2ffd9-103">Set-WSManInstance</span></span>

## <span data-ttu-id="2ffd9-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="2ffd9-104">SYNOPSIS</span></span>
<span data-ttu-id="2ffd9-105">Modifica as informações de gerenciamento que estão relacionadas a um recurso.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-105">Modifies the management information that is related to a resource.</span></span>

## <span data-ttu-id="2ffd9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2ffd9-106">SYNTAX</span></span>

### <span data-ttu-id="2ffd9-107">ComputerName (padrão)</span><span class="sxs-lookup"><span data-stu-id="2ffd9-107">ComputerName (Default)</span></span>

```
Set-WSManInstance [-ApplicationName <String>] [-ComputerName <String>] [-Dialect <Uri>] [-FilePath <String>]
 [-Fragment <String>] [-OptionSet <Hashtable>] [-Port <Int32>] [-ResourceURI] <Uri>
 [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>] [-UseSSL] [-ValueSet <Hashtable>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="2ffd9-108">URI</span><span class="sxs-lookup"><span data-stu-id="2ffd9-108">URI</span></span>

```
Set-WSManInstance [-ConnectionURI <Uri>] [-Dialect <Uri>] [-FilePath <String>] [-Fragment <String>]
 [-OptionSet <Hashtable>] [-ResourceURI] <Uri> [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>]
 [-ValueSet <Hashtable>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

## <span data-ttu-id="2ffd9-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2ffd9-109">DESCRIPTION</span></span>

<span data-ttu-id="2ffd9-110">O cmdlet Set-WSManInstance modifica as informações de gerenciamento que estão relacionadas a um recurso.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-110">The Set-WSManInstance cmdlet modifies the management information that is related to a resource.</span></span>

<span data-ttu-id="2ffd9-111">Esse cmdlet usa a camada de conexão/transporte do WinRM para modificar as informações.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-111">This cmdlet uses the WinRM connection/transport layer to modify the information.</span></span>

## <span data-ttu-id="2ffd9-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="2ffd9-112">EXAMPLES</span></span>

### <span data-ttu-id="2ffd9-113">Exemplo 1: desabilitar um ouvinte no computador local</span><span class="sxs-lookup"><span data-stu-id="2ffd9-113">Example 1: Disable a listener on the local computer</span></span>

```powershell
Set-WSManInstance -ResourceURI winrm/config/listener -SelectorSet @{address="*";transport="https"} -ValueSet @{Enabled="false"}
```

```Output
cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
lang                  : en-US
Address               : *
Transport             : HTTPS
Port                  : 443
Hostname              :
Enabled               : false
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {127.0.0.1, 172.30.168.171, ::1, 2001:4898:0:fff:0:5efe:172.30.168.171...}
```

<span data-ttu-id="2ffd9-114">Este comando desabilita o ouvinte https no computador local.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-114">This command disables the https listener on the local computer.</span></span>

<span data-ttu-id="2ffd9-115">Importante: o parâmetro *ValueSet* diferencia maiúsculas de minúsculas ao corresponder as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-115">Important: The *ValueSet* parameter is case-sensitive when matching the properties specified.</span></span>

<span data-ttu-id="2ffd9-116">Por exemplo, neste comando,</span><span class="sxs-lookup"><span data-stu-id="2ffd9-116">For example, in this command,</span></span>

<span data-ttu-id="2ffd9-117">Isso falha: `-ValueSet @{enabled="False"}`</span><span class="sxs-lookup"><span data-stu-id="2ffd9-117">This fails: `-ValueSet @{enabled="False"}`</span></span>

<span data-ttu-id="2ffd9-118">Isso tem sucesso: `-ValueSet @{Enabled="False"}`</span><span class="sxs-lookup"><span data-stu-id="2ffd9-118">This succeeds: `-ValueSet @{Enabled="False"}`</span></span>

### <span data-ttu-id="2ffd9-119">Exemplo 2: definir o tamanho máximo do envelope no computador local</span><span class="sxs-lookup"><span data-stu-id="2ffd9-119">Example 2: Set the maximum envelope size on the local computer</span></span>

```powershell
Set-WSManInstance -ResourceURI winrm/config -ValueSet @{MaxEnvelopeSizekb = "200"}
```

```Output
cfg                 : http://schemas.microsoft.com/wbem/wsman/1/config
lang                : en-US
MaxEnvelopeSizekb   : 200
MaxTimeoutms        : 60000
MaxBatchItems       : 32000
MaxProviderRequests : 4294967295
Client              : Client
Service             : Service
Winrs               : Winrs
```

<span data-ttu-id="2ffd9-120">Este comando define o valor de MaxEnvelopeSizekb como 200 no computador local.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-120">This command sets the MaxEnvelopeSizekb value to 200 on the local computer.</span></span>

<span data-ttu-id="2ffd9-121">Importante: o parâmetro ValueSet diferencia maiúsculas de minúsculas ao corresponder as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-121">Important: The ValueSet parameter is case-sensitive when matching the properties specified.</span></span>

<span data-ttu-id="2ffd9-122">Por exemplo, usando o comando acima.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-122">For example, using the above command.</span></span>

<span data-ttu-id="2ffd9-123">Isso falha:-ValueSet @ {MaxEnvelopeSizeKB = "200"}</span><span class="sxs-lookup"><span data-stu-id="2ffd9-123">This fails:     -ValueSet @{MaxEnvelopeSizeKB ="200"}</span></span>

<span data-ttu-id="2ffd9-124">Com sucesso:-ValueSet @ {MaxEnvelopeSizekb = "200"}</span><span class="sxs-lookup"><span data-stu-id="2ffd9-124">This succeeds:  -ValueSet @{MaxEnvelopeSizekb ="200"}</span></span>

### <span data-ttu-id="2ffd9-125">Exemplo 3: desabilitar um ouvinte em um computador remoto</span><span class="sxs-lookup"><span data-stu-id="2ffd9-125">Example 3: Disable a listener on a remote computer</span></span>

```powershell
Set-WSManInstance -ResourceURI winrm/config/listener -ComputerName SERVER02 -SelectorSet @{address="*";transport="https"} -ValueSet @{Enabled="false"}
```

```Output
cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
lang                  : en-US
Address               : *
Transport             : HTTPS
Port                  : 443
Hostname              :
Enabled               : false
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {127.0.0.1, 172.30.168.172, ::1, 2001:4898:0:fff:0:5efe:172.30.168.172...}
```

<span data-ttu-id="2ffd9-126">Este comando desabilita o ouvinte https no computador remoto SERVER02.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-126">This command disables the https listener on the remote computer SERVER02.</span></span>

<span data-ttu-id="2ffd9-127">Importante: o parâmetro ValueSet diferencia maiúsculas de minúsculas ao corresponder as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-127">Important: The ValueSet parameter is case-sensitive when matching the properties specified.</span></span>

<span data-ttu-id="2ffd9-128">Por exemplo, usando o comando acima.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-128">For example, using the above command.</span></span>

<span data-ttu-id="2ffd9-129">Isso falha:-ValueSet @ {Enabled = "false"}</span><span class="sxs-lookup"><span data-stu-id="2ffd9-129">This fails:     -ValueSet @{enabled="False"}</span></span>

<span data-ttu-id="2ffd9-130">Com sucesso:-ValueSet @ {Enabled = "false"}</span><span class="sxs-lookup"><span data-stu-id="2ffd9-130">This succeeds:  -ValueSet @{Enabled="False"}</span></span>

## <span data-ttu-id="2ffd9-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2ffd9-131">PARAMETERS</span></span>

### <span data-ttu-id="2ffd9-132">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="2ffd9-132">-ApplicationName</span></span>

<span data-ttu-id="2ffd9-133">Especifica o nome do aplicativo na conexão.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-133">Specifies the application name in the connection.</span></span>
<span data-ttu-id="2ffd9-134">O valor padrão do parâmetro ApplicationName é "WSMAN".</span><span class="sxs-lookup"><span data-stu-id="2ffd9-134">The default value of the ApplicationName parameter is "WSMAN".</span></span>
<span data-ttu-id="2ffd9-135">O identificador completo para o ponto de extremidade remoto é no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="2ffd9-135">The complete identifier for the remote endpoint is in the following format:</span></span>

<span data-ttu-id="2ffd9-136">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="2ffd9-136">\<transport\>://\<server\>:\<port\>/\<ApplicationName\></span></span>

<span data-ttu-id="2ffd9-137">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2ffd9-137">For example:</span></span>

`http://server01:8080/WSMAN`

<span data-ttu-id="2ffd9-138">Os Serviços de Informações da Internet (IIS), que hospedam a sessão, encaminham solicitações com esse ponto de extremidade para o aplicativo especificado.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-138">Internet Information Services (IIS), which hosts the session, forwards requests with this endpoint to the specified application.</span></span>
<span data-ttu-id="2ffd9-139">A configuração padrão de "WSMAN" é adequada para a maioria dos usos.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-139">This default setting of "WSMAN" is appropriate for most uses.</span></span>
<span data-ttu-id="2ffd9-140">Esse parâmetro é projetado para ser utilizado quando diversos computadores estabelecem conexões remotas com um computador que esteja executando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-140">This parameter is designed to be used when numerous computers establish remote connections to one computer that is running Windows PowerShell.</span></span>
<span data-ttu-id="2ffd9-141">Nesse caso, o IIS hospeda o Web Services for Management (WS-Management) para maior eficiência.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-141">In this case, IIS hosts Web Services for Management (WS-Management ) for efficiency.</span></span>

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

### <span data-ttu-id="2ffd9-142">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="2ffd9-142">-Authentication</span></span>

<span data-ttu-id="2ffd9-143">Especifica o mecanismo de autenticação a ser usado no servidor.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-143">Specifies the authentication mechanism to be used at the server.</span></span>
<span data-ttu-id="2ffd9-144">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="2ffd9-144">Possible values are:</span></span>

- <span data-ttu-id="2ffd9-145">Básico: básico é um esquema no qual o nome de usuário e a senha são enviados em texto não criptografado para o servidor ou proxy.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-145">Basic: Basic is a scheme in which the user name and password are sent in clear text to the server or proxy.</span></span>
- <span data-ttu-id="2ffd9-146">Padrão: Use o método de autenticação implementado pelo protocolo WS-Management.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-146">Default : Use the authentication method implemented by the WS-Management protocol.</span></span> <span data-ttu-id="2ffd9-147">Esse é o padrão.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-147">This is the default.</span></span>
- <span data-ttu-id="2ffd9-148">Resumo: o resumo é um esquema de desafio/resposta que usa uma cadeia de caracteres de dados especificada pelo servidor para o desafio.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-148">Digest: Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="2ffd9-149">Kerberos: o computador cliente e o servidor são mutuamente autenticados usando certificados Kerberos.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-149">Kerberos: The client computer and the server mutually authenticate by using Kerberos certificates.</span></span>
- <span data-ttu-id="2ffd9-150">Negotiate: Negotiate é um esquema de desafio/resposta que negocia com o servidor ou proxy para determinar o esquema a ser usado para autenticação.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-150">Negotiate: Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine the scheme to use for authentication.</span></span> <span data-ttu-id="2ffd9-151">Por exemplo, esse valor de parâmetro permite uma negociação para determinar se o protocolo Kerberos ou NTLM será utilizado.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-151">For example, this parameter value allows negotiation to determine whether the Kerberos protocol or NTLM is used.</span></span>
- <span data-ttu-id="2ffd9-152">CredSSP: Use a autenticação do Credential Security Support Provider (CredSSP), que permite ao usuário delegar credenciais.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-152">CredSSP: Use Credential Security Support Provider (CredSSP) authentication, which allows the user to delegate credentials.</span></span> <span data-ttu-id="2ffd9-153">Esta opção foi criada para os comandos executados em um computador remoto, mas coletam dados ou executam comandos adicionais em outros computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-153">This option is designed for commands that run on one remote computer but collect data from or run additional commands on other remote computers.</span></span>

<span data-ttu-id="2ffd9-154">Cuidado: o CredSSP Delega as credenciais do usuário do computador local para um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-154">Caution: CredSSP delegates the user's credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="2ffd9-155">Essa prática aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-155">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="2ffd9-156">Se o computador remoto estiver comprometido, no momento em que as credenciais forem passadas a ele essas credenciais poderão ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-156">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

```yaml
Type: Microsoft.WSMan.Management.AuthenticationMechanism
Parameter Sets: (All)
Aliases: auth, am

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2ffd9-157">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="2ffd9-157">-CertificateThumbprint</span></span>

<span data-ttu-id="2ffd9-158">Especifica o certificado de chave pública digital (X509) de uma conta de usuário com permissão para executar essa ação.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-158">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span>
<span data-ttu-id="2ffd9-159">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-159">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="2ffd9-160">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-160">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="2ffd9-161">Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-161">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="2ffd9-162">Para obter uma impressão digital do certificado, use o comando Get-Item ou Get-ChildItem na unidade certificado do PowerShell:.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-162">To get a certificate thumbprint, use the Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="2ffd9-163">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="2ffd9-163">-ComputerName</span></span>

<span data-ttu-id="2ffd9-164">Especifica o computador no qual se deseja executar a operação de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-164">Specifies the computer against which you want to run the management operation.</span></span>
<span data-ttu-id="2ffd9-165">O valor pode ser um nome de domínio totalmente qualificado, um nome NetBIOS ou um endereço IP.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-165">The value can be a fully qualified domain name, a NetBIOS name, or an IP address.</span></span>
<span data-ttu-id="2ffd9-166">Utilize o nome do computador local, o localhost ou um ponto (.) para especificar o computador local.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-166">Use the local computer name, use localhost, or use a dot (.) to specify the local computer.</span></span>
<span data-ttu-id="2ffd9-167">O computador local é o padrão.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-167">The local computer is the default.</span></span>
<span data-ttu-id="2ffd9-168">Quando o computador remoto está em um domínio diferente do usuário, deve-se usar um nome de domínio totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-168">When the remote computer is in a different domain from the user, you must use a fully qualified domain name must be used.</span></span>
<span data-ttu-id="2ffd9-169">É possível redirecionar um valor desse parâmetro para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-169">You can pipe a value for this parameter to the cmdlet.</span></span>

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

### <span data-ttu-id="2ffd9-170">-Conexãouri</span><span class="sxs-lookup"><span data-stu-id="2ffd9-170">-ConnectionURI</span></span>

<span data-ttu-id="2ffd9-171">Especifica o ponto de extremidade de conexão.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-171">Specifies the connection endpoint.</span></span>
<span data-ttu-id="2ffd9-172">O formato dessa cadeia de caracteres é:</span><span class="sxs-lookup"><span data-stu-id="2ffd9-172">The format of this string is:</span></span>

<span data-ttu-id="2ffd9-173">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span><span class="sxs-lookup"><span data-stu-id="2ffd9-173">\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\></span></span>

<span data-ttu-id="2ffd9-174">A seguinte cadeia de caracteres é um valor formatado corretamente para este parâmetro:</span><span class="sxs-lookup"><span data-stu-id="2ffd9-174">The following string is a properly formatted value for this parameter:</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="2ffd9-175">O URI deve ser totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-175">The URI must be fully qualified .</span></span>

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

### <span data-ttu-id="2ffd9-176">-Credential</span><span class="sxs-lookup"><span data-stu-id="2ffd9-176">-Credential</span></span>

<span data-ttu-id="2ffd9-177">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-177">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="2ffd9-178">O padrão é o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-178">The default is the current user.</span></span>
<span data-ttu-id="2ffd9-179">Digite um nome de usuário, como "User01", "Domínio01 \ Usuário01" ou " User@Domain.com ".</span><span class="sxs-lookup"><span data-stu-id="2ffd9-179">Type a user name, such as "User01", "Domain01\User01", or "User@Domain.com".</span></span>
<span data-ttu-id="2ffd9-180">Ou digite um objeto PSCredential, como o retornado pelo cmdlet Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-180">Or, enter a PSCredential object, such as one returned by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="2ffd9-181">Quando você digitar um nome de usuário, uma senha será solicitada.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-181">When you type a user name, you will be prompted for a password.</span></span>

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

### <span data-ttu-id="2ffd9-182">-Dialeto</span><span class="sxs-lookup"><span data-stu-id="2ffd9-182">-Dialect</span></span>

<span data-ttu-id="2ffd9-183">Especifica o dialeto a ser usado no predicado de filtro.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-183">Specifies the dialect to use in the filter predicate.</span></span>
<span data-ttu-id="2ffd9-184">Isso pode ser qualquer dialeto compatível com o serviço remoto.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-184">This can be any dialect that is supported by the remote service.</span></span>
<span data-ttu-id="2ffd9-185">Os seguintes aliases podem ser usados para o URI do dialeto:</span><span class="sxs-lookup"><span data-stu-id="2ffd9-185">The following aliases can be used for the dialect URI:</span></span>

- <span data-ttu-id="2ffd9-186">WQL `http://schemas.microsoft.com/wbem/wsman/1/WQL`</span><span class="sxs-lookup"><span data-stu-id="2ffd9-186">WQL: `http://schemas.microsoft.com/wbem/wsman/1/WQL`</span></span>
- <span data-ttu-id="2ffd9-187">Seletor `http://schemas.microsoft.com/wbem/wsman/1/wsman/SelectorFilter`</span><span class="sxs-lookup"><span data-stu-id="2ffd9-187">Selector: `http://schemas.microsoft.com/wbem/wsman/1/wsman/SelectorFilter`</span></span>
- <span data-ttu-id="2ffd9-188">Associação `http://schemas.dmtf.org/wbem/wsman/1/cimbinding/associationFilter`</span><span class="sxs-lookup"><span data-stu-id="2ffd9-188">Association: `http://schemas.dmtf.org/wbem/wsman/1/cimbinding/associationFilter`</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: http://schemas.microsoft.com/wbem/wsman/1/WQL
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2ffd9-189">-FilePath</span><span class="sxs-lookup"><span data-stu-id="2ffd9-189">-FilePath</span></span>

<span data-ttu-id="2ffd9-190">Especifica o caminho de um arquivo usado para atualizar um recurso de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-190">Specifies the path of a file that is used to update a management resource.</span></span>
<span data-ttu-id="2ffd9-191">Você pode especificar o recurso de gerenciamento usando o parâmetro ResourceURI e o parâmetro SelectorSet.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-191">You specify the management resource by using the ResourceURI parameter and the SelectorSet parameter .</span></span>
<span data-ttu-id="2ffd9-192">Por exemplo, o comando a seguir usa o parâmetro FilePath:</span><span class="sxs-lookup"><span data-stu-id="2ffd9-192">For example, the following command uses the FilePath parameter:</span></span>

`Invoke-WSManAction -action StopService -resourceuri wmicimv2/Win32_Service -SelectorSet @{Name="spooler"} -FilePath:c:\input.xml -authentication default`

<span data-ttu-id="2ffd9-193">Esse comando chama o método StopService no serviço de Spooler usando entrada de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-193">This command calls the StopService method on the Spooler service by using input from a file.</span></span>
<span data-ttu-id="2ffd9-194">O arquivo, Input.xml, contém o seguinte conteúdo:</span><span class="sxs-lookup"><span data-stu-id="2ffd9-194">The file, Input.xml, contains the following content:</span></span>

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Path

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2ffd9-195">-Fragmento</span><span class="sxs-lookup"><span data-stu-id="2ffd9-195">-Fragment</span></span>

<span data-ttu-id="2ffd9-196">Especifica uma seção na instância a ser atualizada ou recuperada para a operação especificada.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-196">Specifies a section inside the instance that is to be updated or retrieved for the specified operation.</span></span>
<span data-ttu-id="2ffd9-197">Por exemplo, para obter o status de um serviço de spooler, especifique "-Fragment Status".</span><span class="sxs-lookup"><span data-stu-id="2ffd9-197">For example, to get the status of a spooler service, specify "-Fragment Status".</span></span>

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

### <span data-ttu-id="2ffd9-198">-OptionSet</span><span class="sxs-lookup"><span data-stu-id="2ffd9-198">-OptionSet</span></span>

<span data-ttu-id="2ffd9-199">Passa um conjunto de opções para um serviço para modificar ou refinar a natureza da solicitação.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-199">Passes a set of switches to a service to modify or refine the nature of the request.</span></span>
<span data-ttu-id="2ffd9-200">Elas são semelhantes às opções usadas nos shells de linha de comando porque são específicas para o serviço.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-200">These are similar to switches used in command-line shells because they are service specific.</span></span>
<span data-ttu-id="2ffd9-201">Qualquer número de opções pode ser especificado.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-201">Any number of options can be specified.</span></span>

<span data-ttu-id="2ffd9-202">O exemplo a seguir demonstra a sintaxe que passa os valores 1, 2 e 3 para os parâmetros a, b e c:</span><span class="sxs-lookup"><span data-stu-id="2ffd9-202">The following example demonstrates the syntax that passes the values 1, 2, and 3 for the a, b, and c parameters:</span></span>

<span data-ttu-id="2ffd9-203">-OptionSet @{a=1;b=2;c=3}</span><span class="sxs-lookup"><span data-stu-id="2ffd9-203">-OptionSet @{a=1;b=2;c=3}</span></span>

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

### <span data-ttu-id="2ffd9-204">-Port</span><span class="sxs-lookup"><span data-stu-id="2ffd9-204">-Port</span></span>

<span data-ttu-id="2ffd9-205">Especifica a porta a ser usada quando o cliente se conecta ao serviço WinRM.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-205">Specifies the port to use when the client connects to the WinRM service.</span></span>
<span data-ttu-id="2ffd9-206">Quando o transporte é HTTP, a porta padrão é 80.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-206">When the transport is HTTP, the default port is 80.</span></span>
<span data-ttu-id="2ffd9-207">Quando o transporte é HTTPS, a porta padrão é 443.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-207">When the transport is HTTPS, the default port is 443.</span></span>
<span data-ttu-id="2ffd9-208">Quando você usa HTTPS como o transporte, o valor do parâmetro ComputerName deve corresponder ao CN (nome comum) do certificado do servidor.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-208">When you use HTTPS as the transport, the value of the ComputerName parameter must match the server's certificate common name (CN).</span></span>
<span data-ttu-id="2ffd9-209">No entanto, se o parâmetro SkipCNCheck for especificado como parte do parâmetro SessionOption, então o nome comum do certificado do servidor não precisará corresponder ao nome de host do servidor.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-209">However, if the SkipCNCheck parameter is specified as part of the SessionOption parameter, then the certificate common name of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="2ffd9-210">O parâmetro SkipCNCheck deve ser utilizado apenas para computadores confiáveis.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-210">The SkipCNCheck parameter should be used only for trusted machines.</span></span>

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

### <span data-ttu-id="2ffd9-211">-ResourceURI</span><span class="sxs-lookup"><span data-stu-id="2ffd9-211">-ResourceURI</span></span>

<span data-ttu-id="2ffd9-212">Contém o Uniform Resource Identifier (URI) da instância ou classe do recurso.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-212">Contains the Uniform Resource Identifier (URI) of the resource class or instance.</span></span>
<span data-ttu-id="2ffd9-213">O URI é utilizado para identificar um tipo específico de recurso, como discos ou processos em um computador.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-213">The URI is used to identify a specific type of resource, such as disks or processes, on a computer.</span></span>

<span data-ttu-id="2ffd9-214">Um URI consiste em um prefixo e um caminho para um recurso.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-214">A URI consists of a prefix and a path to a resource.</span></span>
<span data-ttu-id="2ffd9-215">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2ffd9-215">For example:</span></span>

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

### <span data-ttu-id="2ffd9-216">-SelectorSet</span><span class="sxs-lookup"><span data-stu-id="2ffd9-216">-SelectorSet</span></span>

<span data-ttu-id="2ffd9-217">Especifica um conjunto de pares de valor que são utilizados para selecionar instâncias do recurso de gerenciamento específico.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-217">Specifies a set of value pairs that are used to select particular management resource instances.</span></span>
<span data-ttu-id="2ffd9-218">O parâmetro SelectorSet é utilizado quando houver mais de uma instância do recurso.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-218">The SelectorSet parameter is used when more than one instance of the resource exists.</span></span>
<span data-ttu-id="2ffd9-219">O valor do parâmetro SelectorSet deve ser uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-219">The value of the SelectorSet parameter must be a hash table.</span></span>
<span data-ttu-id="2ffd9-220">O exemplo a seguir mostra como inserir um valor para esse parâmetro:</span><span class="sxs-lookup"><span data-stu-id="2ffd9-220">The following example shows how to enter a value for this parameter:</span></span>

<span data-ttu-id="2ffd9-221">-SelectorSet @{Name="WinRM";ID="yyy"}</span><span class="sxs-lookup"><span data-stu-id="2ffd9-221">-SelectorSet @{Name="WinRM";ID="yyy"}</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="2ffd9-222">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="2ffd9-222">-SessionOption</span></span>

<span data-ttu-id="2ffd9-223">Define um conjunto de opções estendidas para a sessão do WS-Management.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-223">Defines a set of extended options for the WS-Management session.</span></span>
<span data-ttu-id="2ffd9-224">Digite um objeto SessionOption que você criou utilizando o cmdlet New-PSSessionOption.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-224">Enter a SessionOption object that you create by using the New-WSManSessionOption cmdlet.</span></span>
<span data-ttu-id="2ffd9-225">Para obter mais informações sobre as opções disponíveis, consulte New-WSManSessionOption.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-225">For more information about the options that are available, see New-WSManSessionOption.</span></span>

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

### <span data-ttu-id="2ffd9-226">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="2ffd9-226">-UseSSL</span></span>

<span data-ttu-id="2ffd9-227">Especifica que o protocolo Secure Sockets Layer (SSL) deve ser utilizado para estabelecer uma conexão com o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-227">Specifies that the Secure Sockets Layer (SSL) protocol should be used to establish a connection to the remote computer.</span></span>
<span data-ttu-id="2ffd9-228">Por padrão, SSL não é usado.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-228">By default, SSL is not used.</span></span>

<span data-ttu-id="2ffd9-229">O WS-Management criptografa todo o conteúdo do Windows PowerShell que é transmitido pela rede.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-229">WS-Management encrypts all the Windows PowerShell content that is transmitted over the network.</span></span>
<span data-ttu-id="2ffd9-230">O parâmetro UseSSL permite especificar a proteção adicional de HTTPS em vez de HTTP.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-230">The UseSSL parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span>
<span data-ttu-id="2ffd9-231">Se o SSL não estiver disponível na porta utilizada para a conexão e o parâmetro for especificado, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-231">If SSL is not available on the port that is used for the connection and you specify this parameter, the command fails.</span></span>

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

### <span data-ttu-id="2ffd9-232">-Valorset</span><span class="sxs-lookup"><span data-stu-id="2ffd9-232">-ValueSet</span></span>

<span data-ttu-id="2ffd9-233">Especifica uma tabela de hash que ajuda a modificar um recurso de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-233">Specifies a hash table that helps modify a management resource.</span></span>
<span data-ttu-id="2ffd9-234">Você pode especificar o recurso de gerenciamento usando os parâmetros ResourceURI e SelectorSet.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-234">You specify the management resource by using the ResourceURI parameter and the SelectorSet parameter.</span></span>
<span data-ttu-id="2ffd9-235">O valor do parâmetro ValueSet deve ser uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-235">The value of the ValueSet parameter must be a hash table.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2ffd9-236">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2ffd9-236">CommonParameters</span></span>

<span data-ttu-id="2ffd9-237">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-237">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2ffd9-238">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="2ffd9-238">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="2ffd9-239">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="2ffd9-239">INPUTS</span></span>

### <span data-ttu-id="2ffd9-240">Nenhum</span><span class="sxs-lookup"><span data-stu-id="2ffd9-240">None</span></span>

<span data-ttu-id="2ffd9-241">Esse cmdlet não aceita nenhuma entrada.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-241">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="2ffd9-242">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="2ffd9-242">OUTPUTS</span></span>

### <span data-ttu-id="2ffd9-243">Nenhum</span><span class="sxs-lookup"><span data-stu-id="2ffd9-243">None</span></span>

<span data-ttu-id="2ffd9-244">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-244">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="2ffd9-245">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="2ffd9-245">NOTES</span></span>

## <span data-ttu-id="2ffd9-246">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="2ffd9-246">RELATED LINKS</span></span>

[<span data-ttu-id="2ffd9-247">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="2ffd9-247">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="2ffd9-248">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="2ffd9-248">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="2ffd9-249">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="2ffd9-249">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="2ffd9-250">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="2ffd9-250">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="2ffd9-251">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="2ffd9-251">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="2ffd9-252">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="2ffd9-252">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="2ffd9-253">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="2ffd9-253">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="2ffd9-254">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="2ffd9-254">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="2ffd9-255">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="2ffd9-255">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="2ffd9-256">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="2ffd9-256">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="2ffd9-257">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="2ffd9-257">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="2ffd9-258">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="2ffd9-258">Test-WSMan</span></span>](Test-WSMan.md)

