---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/new-cimsession?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-CimSession
ms.openlocfilehash: 2362940dd07cf6ca65b71660337a647c1090f4e8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194098"
---
# <span data-ttu-id="d7db0-103">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="d7db0-103">New-CimSession</span></span>

## <span data-ttu-id="d7db0-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="d7db0-104">SYNOPSIS</span></span>

<span data-ttu-id="d7db0-105">Cria uma sessão CIM.</span><span class="sxs-lookup"><span data-stu-id="d7db0-105">Creates a CIM session.</span></span>

## <span data-ttu-id="d7db0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d7db0-106">SYNTAX</span></span>

### <span data-ttu-id="d7db0-107">CredentialParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="d7db0-107">CredentialParameterSet (Default)</span></span>

```
New-CimSession [-Authentication <PasswordAuthenticationMechanism>] [[-Credential] <PSCredential>]
 [[-ComputerName] <String[]>] [-Name <String>] [-OperationTimeoutSec <UInt32>] [-SkipTestConnection]
 [-Port <UInt32>] [-SessionOption <CimSessionOptions>] [<CommonParameters>]
```

### <span data-ttu-id="d7db0-108">CertificateParameterSet</span><span class="sxs-lookup"><span data-stu-id="d7db0-108">CertificateParameterSet</span></span>

```
New-CimSession [-CertificateThumbprint <String>] [[-ComputerName] <String[]>] [-Name <String>]
 [-OperationTimeoutSec <UInt32>] [-SkipTestConnection] [-Port <UInt32>]
 [-SessionOption <CimSessionOptions>] [<CommonParameters>]
```

## <span data-ttu-id="d7db0-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d7db0-109">DESCRIPTION</span></span>

<span data-ttu-id="d7db0-110">O `New-CimSession` cmdlet cria uma sessão CIM.</span><span class="sxs-lookup"><span data-stu-id="d7db0-110">The `New-CimSession` cmdlet creates a CIM session.</span></span> <span data-ttu-id="d7db0-111">Uma sessão CIM é um objeto do lado do cliente que representa uma conexão com um computador local ou com um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="d7db0-111">A CIM session is a client-side object representing a connection to a local computer or a remote computer.</span></span> <span data-ttu-id="d7db0-112">A sessão CIM contém informações sobre a conexão, como **ComputerName** , o protocolo usado ou vários identificadores.</span><span class="sxs-lookup"><span data-stu-id="d7db0-112">The CIM session contains information about the connection, such as **ComputerName** , the protocol used, or various identifiers.</span></span>

<span data-ttu-id="d7db0-113">Esse cmdlet retorna um objeto de sessão CIM que pode ser usado por todos os outros cmdlets de CIM.</span><span class="sxs-lookup"><span data-stu-id="d7db0-113">This cmdlet returns a CIM session object that can be used by all other CIM cmdlets.</span></span>

## <span data-ttu-id="d7db0-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="d7db0-114">EXAMPLES</span></span>

### <span data-ttu-id="d7db0-115">Exemplo 1: criar uma sessão CIM com opções padrão</span><span class="sxs-lookup"><span data-stu-id="d7db0-115">Example 1: Create a CIM session with default options</span></span>

<span data-ttu-id="d7db0-116">Este exemplo cria uma sessão CIM local com opções padrão.</span><span class="sxs-lookup"><span data-stu-id="d7db0-116">This example creates a local CIM session with default options.</span></span> <span data-ttu-id="d7db0-117">Se **ComputerName** não for especificado, `New-CimSession` o criará uma sessão DCOM para o computador local.</span><span class="sxs-lookup"><span data-stu-id="d7db0-117">If **ComputerName** is not specified, `New-CimSession` creates a DCOM session to the local computer.</span></span>

```powershell
New-CimSession
```

### <span data-ttu-id="d7db0-118">Exemplo 2: criar uma sessão CIM para um computador específico</span><span class="sxs-lookup"><span data-stu-id="d7db0-118">Example 2: Create a CIM session to a specific computer</span></span>

<span data-ttu-id="d7db0-119">Este exemplo cria uma sessão CIM para o computador especificado por **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="d7db0-119">This example creates a CIM session to the computer specified by **ComputerName** .</span></span>
<span data-ttu-id="d7db0-120">Por padrão, `New-CimSession` o cria uma sessão do WSMan quando **ComputerName** é especificado.</span><span class="sxs-lookup"><span data-stu-id="d7db0-120">By default, `New-CimSession` creates a WSMan session when **ComputerName** is specified.</span></span>

```powershell
New-CimSession -ComputerName Server01
```

### <span data-ttu-id="d7db0-121">Exemplo 3: criar uma sessão CIM para vários computadores</span><span class="sxs-lookup"><span data-stu-id="d7db0-121">Example 3: Create a CIM session to multiple computers</span></span>

<span data-ttu-id="d7db0-122">Este exemplo cria uma sessão CIM para cada um dos computadores especificados por **ComputerName** , na lista separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="d7db0-122">This example creates a CIM session to each of the computers specified by **ComputerName** , in the comma separated list.</span></span>

```powershell
New-CimSession -ComputerName Server01,Server02,Server03
```

### <span data-ttu-id="d7db0-123">Exemplo 4: criar uma sessão CIM com um nome amigável</span><span class="sxs-lookup"><span data-stu-id="d7db0-123">Example 4: Create a CIM session with a friendly name</span></span>

<span data-ttu-id="d7db0-124">Este exemplo cria uma sessão CIM remota para cada um dos computadores especificados por **ComputerName** , na lista separada por vírgulas, e atribui um nome amigável às novas sessões, especificando **Name** .</span><span class="sxs-lookup"><span data-stu-id="d7db0-124">This example creates a remote CIM session to each of the computers specified by **ComputerName** , in the comma separated list, and assigns a friendly name to the new sessions, by specifying **Name** .</span></span>

```powershell
New-CimSession -ComputerName Server01,Server02 -Name FileServers
Get-CimSession -Name File*
```

<span data-ttu-id="d7db0-125">Você pode usar o nome amigável de uma sessão CIM para se referir à sessão em outros cmdlets do CIM, por exemplo, [Get-CimSession](Get-CimSession.md).</span><span class="sxs-lookup"><span data-stu-id="d7db0-125">You can use the friendly name of a CIM session to refer to the session in other CIM cmdlets, for example, [Get-CimSession](Get-CimSession.md).</span></span>

### <span data-ttu-id="d7db0-126">Exemplo 5: criar uma sessão CIM para um computador usando um objeto PSCredential</span><span class="sxs-lookup"><span data-stu-id="d7db0-126">Example 5: Create a CIM session to a computer using a PSCredential object</span></span>

<span data-ttu-id="d7db0-127">Este exemplo cria uma sessão CIM para o computador especificado por **ComputerName** , usando o objeto **PSCredential** especificado por **Credential** e o tipo de autenticação especificado pela **autenticação** .</span><span class="sxs-lookup"><span data-stu-id="d7db0-127">This example creates a CIM session to the computer specified by **ComputerName** , using the **PSCredential** object specified by **Credential** , and the authentication type specified by **Authentication** .</span></span>

```powershell
New-CimSession -ComputerName Server01 -Credential $cred -Authentication Negotiate
```

<span data-ttu-id="d7db0-128">Você pode criar um objeto **PSCredential** usando o [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d7db0-128">You can create a **PSCredential** object using the [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) cmdlet.</span></span>

### <span data-ttu-id="d7db0-129">Exemplo 6: criar uma sessão CIM para um computador usando uma porta específica</span><span class="sxs-lookup"><span data-stu-id="d7db0-129">Example 6: Create a CIM session to a computer using a specific port</span></span>

<span data-ttu-id="d7db0-130">Este exemplo cria uma sessão CIM para o computador especificado por **ComputerName** usando a porta TCP especificada pela **porta** .</span><span class="sxs-lookup"><span data-stu-id="d7db0-130">This example creates a CIM session to the computer specified by **ComputerName** using the TCP port specified by **Port** .</span></span>

```powershell
New-CimSession -ComputerName Server01 -Port 1234
```

### <span data-ttu-id="d7db0-131">Exemplo 7: criar uma sessão CIM usando DCOM</span><span class="sxs-lookup"><span data-stu-id="d7db0-131">Example 7: Create a CIM session using DCOM</span></span>

<span data-ttu-id="d7db0-132">Este exemplo cria uma sessão CIM usando o protocolo DCOM (Distributed COM) em vez do WSMan.</span><span class="sxs-lookup"><span data-stu-id="d7db0-132">This example creates a CIM session using the Distributed COM (DCOM) protocol instead of WSMan.</span></span>

```powershell
$SessionOption = New-CimSessionOption -Protocol DCOM
New-CimSession -ComputerName Server1 -SessionOption $SessionOption
```

## <span data-ttu-id="d7db0-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d7db0-133">PARAMETERS</span></span>

### <span data-ttu-id="d7db0-134">-Autenticação</span><span class="sxs-lookup"><span data-stu-id="d7db0-134">-Authentication</span></span>

<span data-ttu-id="d7db0-135">Especifica o tipo de autenticação usado para as credenciais do usuário.</span><span class="sxs-lookup"><span data-stu-id="d7db0-135">Specifies the authentication type used for the user's credentials.</span></span> <span data-ttu-id="d7db0-136">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="d7db0-136">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="d7db0-137">Padrão</span><span class="sxs-lookup"><span data-stu-id="d7db0-137">Default</span></span>
- <span data-ttu-id="d7db0-138">Digest</span><span class="sxs-lookup"><span data-stu-id="d7db0-138">Digest</span></span>
- <span data-ttu-id="d7db0-139">Negotiate</span><span class="sxs-lookup"><span data-stu-id="d7db0-139">Negotiate</span></span>
- <span data-ttu-id="d7db0-140">Básico</span><span class="sxs-lookup"><span data-stu-id="d7db0-140">Basic</span></span>
- <span data-ttu-id="d7db0-141">Kerberos</span><span class="sxs-lookup"><span data-stu-id="d7db0-141">Kerberos</span></span>
- <span data-ttu-id="d7db0-142">NtlmDomain</span><span class="sxs-lookup"><span data-stu-id="d7db0-142">NtlmDomain</span></span>
- <span data-ttu-id="d7db0-143">CredSsp</span><span class="sxs-lookup"><span data-stu-id="d7db0-143">CredSsp</span></span>

<span data-ttu-id="d7db0-144">Você não pode usar o tipo de autenticação **NtlmDomain** para conexão com o computador local.</span><span class="sxs-lookup"><span data-stu-id="d7db0-144">You cannot use the **NtlmDomain** authentication type for connection to the local computer.</span></span> <span data-ttu-id="d7db0-145">A autenticação **CredSSP** está disponível somente no Windows Vista, no windows Server 2008 e em versões posteriores do Windows.</span><span class="sxs-lookup"><span data-stu-id="d7db0-145">**CredSSP** authentication is available only in Windows Vista, Windows Server 2008, and later versions of Windows.</span></span>

> [!CAUTION]
> <span data-ttu-id="d7db0-146">A autenticação CredSSP (provedor de serviços de segurança de credencial) destina-se a comandos que exigem autenticação em mais de um recurso, como acessar um compartilhamento de rede remoto.</span><span class="sxs-lookup"><span data-stu-id="d7db0-146">Credential Security Service Provider (CredSSP) authentication is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="d7db0-147">Esse mecanismo aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="d7db0-147">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="d7db0-148">Se o computador remoto estiver comprometido, as credenciais que são passadas a ele podem ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="d7db0-148">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.Options.PasswordAuthenticationMechanism
Parameter Sets: CredentialParameterSet
Aliases:
Accepted values: Default, Digest, Negotiate, Basic, Kerberos, NtlmDomain, CredSsp

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d7db0-149">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="d7db0-149">-CertificateThumbprint</span></span>

<span data-ttu-id="d7db0-150">Especifica o certificado de chave pública digital (X. 509) de uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="d7db0-150">Specifies the digital public key certificate (X.509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="d7db0-151">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="d7db0-151">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="d7db0-152">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="d7db0-152">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="d7db0-153">Eles podem ser mapeados somente para contas de usuário local; eles não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="d7db0-153">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="d7db0-154">Para obter uma impressão digital do certificado, use os [`Get-Item`](../Microsoft.Powershell.Management/Get-Item.md) [`Get-ChildItem`](../Microsoft.Powershell.Management/Get-ChildItem.md) cmdlets ou no provedor de certificado do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7db0-154">To get a certificate thumbprint, use the [`Get-Item`](../Microsoft.Powershell.Management/Get-Item.md) or [`Get-ChildItem`](../Microsoft.Powershell.Management/Get-ChildItem.md) cmdlets in the PowerShell Certificate Provider.</span></span>

<span data-ttu-id="d7db0-155">Para obter mais informações, consulte [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span><span class="sxs-lookup"><span data-stu-id="d7db0-155">For more information, see [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span></span>

```yaml
Type: System.String
Parameter Sets: CertificateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d7db0-156">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="d7db0-156">-ComputerName</span></span>

<span data-ttu-id="d7db0-157">Especifica o nome do computador para o qual criar a sessão CIM.</span><span class="sxs-lookup"><span data-stu-id="d7db0-157">Specifies the name of the computer to which to create the CIM session.</span></span> <span data-ttu-id="d7db0-158">Especifique um único nome de computador ou vários nomes de computador separados por uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="d7db0-158">Specify either a single computer name, or multiple computer names separated by a comma.</span></span>

<span data-ttu-id="d7db0-159">Se **ComputerName** não for especificado, será criada uma sessão CIM para o computador local.</span><span class="sxs-lookup"><span data-stu-id="d7db0-159">If **ComputerName** is not specified, a CIM session to the local computer is created.</span></span> <span data-ttu-id="d7db0-160">Você pode especificar o valor para o nome do computador em um dos seguintes formatos:</span><span class="sxs-lookup"><span data-stu-id="d7db0-160">You can specify the value for computer name in one of the following formats:</span></span>

- <span data-ttu-id="d7db0-161">Um ou mais nomes NetBIOS</span><span class="sxs-lookup"><span data-stu-id="d7db0-161">One or more NetBIOS names</span></span>
- <span data-ttu-id="d7db0-162">Um ou mais endereços IP</span><span class="sxs-lookup"><span data-stu-id="d7db0-162">One or more IP addresses</span></span>
- <span data-ttu-id="d7db0-163">Um ou mais nomes de domínio totalmente qualificados.</span><span class="sxs-lookup"><span data-stu-id="d7db0-163">One or more fully qualified domain names.</span></span>

<span data-ttu-id="d7db0-164">Se o computador estiver em um domínio diferente do usuário, você deverá especificar o nome de domínio totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="d7db0-164">If the computer is in a different domain than the user, you must specify the fully qualified domain name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d7db0-165">-Credential</span><span class="sxs-lookup"><span data-stu-id="d7db0-165">-Credential</span></span>

<span data-ttu-id="d7db0-166">Especifica uma conta de usuário que tem permissão para executar esta ação.</span><span class="sxs-lookup"><span data-stu-id="d7db0-166">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="d7db0-167">Se a **credencial** não for especificada, a conta de usuário atual será usada.</span><span class="sxs-lookup"><span data-stu-id="d7db0-167">If **Credential** is not specified, the current user account is used.</span></span>

<span data-ttu-id="d7db0-168">Especifique o valor para **Credential** usando um dos seguintes formatos:</span><span class="sxs-lookup"><span data-stu-id="d7db0-168">Specify the value for **Credential** using one of the following formats:</span></span>

- <span data-ttu-id="d7db0-169">Um nome de usuário: "User01"</span><span class="sxs-lookup"><span data-stu-id="d7db0-169">A user name: "User01"</span></span>
- <span data-ttu-id="d7db0-170">Um nome de domínio e um nome de usuário: "Domínio01 \ Usuário01"</span><span class="sxs-lookup"><span data-stu-id="d7db0-170">A domain name and a user name: "Domain01\User01"</span></span>
- <span data-ttu-id="d7db0-171">Um nome principal de usuário: " User@Domain.com "</span><span class="sxs-lookup"><span data-stu-id="d7db0-171">A user principal name: "User@Domain.com"</span></span>
- <span data-ttu-id="d7db0-172">Um objeto PSCredential, como um retornado pelo [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d7db0-172">A PSCredential object, such as one returned by the [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) cmdlet.</span></span>

<span data-ttu-id="d7db0-173">Quando você digitar um nome de usuário, uma senha será solicitada.</span><span class="sxs-lookup"><span data-stu-id="d7db0-173">When you type a user name, you are prompted for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: CredentialParameterSet
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d7db0-174">-Name</span><span class="sxs-lookup"><span data-stu-id="d7db0-174">-Name</span></span>

<span data-ttu-id="d7db0-175">Especifica um nome amigável para a sessão CIM.</span><span class="sxs-lookup"><span data-stu-id="d7db0-175">Specifies a friendly name for the CIM session.</span></span>

<span data-ttu-id="d7db0-176">Você pode usar o nome para se referir à sessão CIM ao usar outros cmdlets, como o [`Get-CimSession`](Get-CimSession.md) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d7db0-176">You can use the name to refer to the CIM session when using other cmdlets, such as the [`Get-CimSession`](Get-CimSession.md) cmdlet.</span></span>
<span data-ttu-id="d7db0-177">Não é necessário que o nome do computador ou da sessão atual seja exclusivo.</span><span class="sxs-lookup"><span data-stu-id="d7db0-177">The name is not required to be unique to the computer or the current session.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d7db0-178">-OperationTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="d7db0-178">-OperationTimeoutSec</span></span>

<span data-ttu-id="d7db0-179">Duração pela qual o cmdlet aguarda uma resposta do servidor.</span><span class="sxs-lookup"><span data-stu-id="d7db0-179">Duration for which the cmdlet waits for a response from the server.</span></span>

<span data-ttu-id="d7db0-180">Por padrão, o valor desse parâmetro é 0, o que significa que o cmdlet usa o valor de tempo limite padrão para o servidor.</span><span class="sxs-lookup"><span data-stu-id="d7db0-180">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="d7db0-181">Se o parâmetro **OperationTimeoutSec** for definido como um valor menor que o tempo limite de repetição de conexão robusto de 3 minutos, as falhas de rede que durar mais do que o valor do parâmetro **OperationTimeoutSec** não serão recuperáveis, pois a operação no servidor expirará antes que o cliente possa se reconectar.</span><span class="sxs-lookup"><span data-stu-id="d7db0-181">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: OT

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d7db0-182">-Port</span><span class="sxs-lookup"><span data-stu-id="d7db0-182">-Port</span></span>

<span data-ttu-id="d7db0-183">Especifica a porta de rede no computador remoto que é usada para esta conexão.</span><span class="sxs-lookup"><span data-stu-id="d7db0-183">Specifies the network port on the remote computer that is used for this connection.</span></span>
<span data-ttu-id="d7db0-184">Para se conectar a um computador remoto, este deve estar escutando na porta usada pela conexão.</span><span class="sxs-lookup"><span data-stu-id="d7db0-184">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span>
<span data-ttu-id="d7db0-185">As portas padrão são 5985 (a porta de WinRM para HTTP) e 5986 (a porta de WinRM para HTTPS).</span><span class="sxs-lookup"><span data-stu-id="d7db0-185">The default ports are 5985 (the WinRM port for HTTP) and 5986 (the WinRM port for HTTPS).</span></span>

<span data-ttu-id="d7db0-186">Antes de usar uma porta alternativa, você deve configurar o ouvinte de WinRM no computador remoto para escutar na porta.</span><span class="sxs-lookup"><span data-stu-id="d7db0-186">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span>
<span data-ttu-id="d7db0-187">Use os seguintes comandos para configurar o ouvinte:</span><span class="sxs-lookup"><span data-stu-id="d7db0-187">Use the following commands to configure the listener:</span></span>

`winrm delete winrm/config/listener?Address=*+Transport=HTTP`

`winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number>"}`

<span data-ttu-id="d7db0-188">Não use o parâmetro **Port** a menos que seja necessário.</span><span class="sxs-lookup"><span data-stu-id="d7db0-188">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="d7db0-189">A configuração da porta no comando se aplica a todos os computadores ou sessões em que o comando for executado.</span><span class="sxs-lookup"><span data-stu-id="d7db0-189">The port setting in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="d7db0-190">Uma configuração de porta alternativa pode impedir que o comando seja executado em todos os computadores.</span><span class="sxs-lookup"><span data-stu-id="d7db0-190">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d7db0-191">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="d7db0-191">-SessionOption</span></span>

<span data-ttu-id="d7db0-192">Define opções avançadas para a nova sessão CIM.</span><span class="sxs-lookup"><span data-stu-id="d7db0-192">Sets advanced options for the new CIM session.</span></span> <span data-ttu-id="d7db0-193">Insira o nome de um objeto **CimSessionOption** criado usando o [`New-CimSessionOption`](New-CimSessionOption.md) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d7db0-193">Enter the name of a **CimSessionOption** object created using the [`New-CimSessionOption`](New-CimSessionOption.md) cmdlet.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.Options.CimSessionOptions
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d7db0-194">-SkipTestConnection</span><span class="sxs-lookup"><span data-stu-id="d7db0-194">-SkipTestConnection</span></span>

<span data-ttu-id="d7db0-195">Por padrão, o `New-CimSession` cmdlet estabelece uma conexão com um ponto de extremidade de WS-Management remoto por dois motivos: para verificar se o servidor remoto está escutando no número da porta especificado usando o parâmetro **Port** e para verificar as credenciais da conta especificada.</span><span class="sxs-lookup"><span data-stu-id="d7db0-195">By default, the `New-CimSession` cmdlet establishes a connection with a remote WS-Management endpoint for two reasons: to verify that the remote server is listening on the port number that is specified using the **Port** parameter, and to verify the specified account credentials.</span></span> <span data-ttu-id="d7db0-196">A verificação é realizada usando uma operação de WS-Identity padrão.</span><span class="sxs-lookup"><span data-stu-id="d7db0-196">The verification is accomplished using a standard WS-Identity operation.</span></span> <span data-ttu-id="d7db0-197">Você pode adicionar o parâmetro de opção **SkipTestConnection** se o ponto de extremidade de WS-Management remota não puder usar WS-Identify ou para reduzir o tempo de transmissão de dados.</span><span class="sxs-lookup"><span data-stu-id="d7db0-197">You can add the **SkipTestConnection** switch parameter if the remote WS-Management endpoint cannot use WS-Identify, or to reduce some data transmission time.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d7db0-198">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d7db0-198">CommonParameters</span></span>

<span data-ttu-id="d7db0-199">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d7db0-199">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d7db0-200">Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="d7db0-200">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="d7db0-201">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="d7db0-201">INPUTS</span></span>

### <span data-ttu-id="d7db0-202">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d7db0-202">None</span></span>

<span data-ttu-id="d7db0-203">Esse cmdlet não aceita entradas.</span><span class="sxs-lookup"><span data-stu-id="d7db0-203">This cmdlet accepts no inputs.</span></span>

## <span data-ttu-id="d7db0-204">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="d7db0-204">OUTPUTS</span></span>

### <span data-ttu-id="d7db0-205">Microsoft.Management.Infrastructure.CimSession</span><span class="sxs-lookup"><span data-stu-id="d7db0-205">Microsoft.Management.Infrastructure.CimSession</span></span>

## <span data-ttu-id="d7db0-206">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="d7db0-206">NOTES</span></span>

## <span data-ttu-id="d7db0-207">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="d7db0-207">RELATED LINKS</span></span>

[<span data-ttu-id="d7db0-208">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="d7db0-208">Get-ChildItem</span></span>](../Microsoft.Powershell.Management/Get-ChildItem.md)

[<span data-ttu-id="d7db0-209">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="d7db0-209">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="d7db0-210">Get-Item</span><span class="sxs-lookup"><span data-stu-id="d7db0-210">Get-Item</span></span>](../Microsoft.Powershell.Management/Get-Item.md)

[<span data-ttu-id="d7db0-211">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="d7db0-211">Get-CimSession</span></span>](Get-CimSession.md)

[<span data-ttu-id="d7db0-212">Remove-CimSession</span><span class="sxs-lookup"><span data-stu-id="d7db0-212">Remove-CimSession</span></span>](Remove-CimSession.md)

[<span data-ttu-id="d7db0-213">New-CimSessionOption</span><span class="sxs-lookup"><span data-stu-id="d7db0-213">New-CimSessionOption</span></span>](New-CimSessionOption.md)

[<span data-ttu-id="d7db0-214">about_CimSession</span><span class="sxs-lookup"><span data-stu-id="d7db0-214">about_CimSession</span></span>](../Microsoft.PowerShell.Core/About/about_CimSession.md)
