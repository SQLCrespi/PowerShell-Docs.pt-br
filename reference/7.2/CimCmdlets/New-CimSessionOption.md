---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/new-cimsessionoption?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-CimSessionOption
ms.openlocfilehash: 54a2ca8a28d54bfe1d9676acdaace4592f62620f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596777"
---
# <span data-ttu-id="9fa24-102">New-CimSessionOption</span><span class="sxs-lookup"><span data-stu-id="9fa24-102">New-CimSessionOption</span></span>

## <span data-ttu-id="9fa24-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="9fa24-103">SYNOPSIS</span></span>
<span data-ttu-id="9fa24-104">Especifica opções avançadas para o cmdlet New-CimSession.</span><span class="sxs-lookup"><span data-stu-id="9fa24-104">Specifies advanced options for the New-CimSession cmdlet.</span></span>

## <span data-ttu-id="9fa24-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9fa24-105">SYNTAX</span></span>

### <span data-ttu-id="9fa24-106">ProtocolTypeSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="9fa24-106">ProtocolTypeSet (Default)</span></span>

```
New-CimSessionOption [-Protocol] <ProtocolType> [-UICulture <CultureInfo>] [-Culture <CultureInfo>]
 [<CommonParameters>]
```

### <span data-ttu-id="9fa24-107">WSManParameterSet</span><span class="sxs-lookup"><span data-stu-id="9fa24-107">WSManParameterSet</span></span>

```
New-CimSessionOption [-NoEncryption] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck]
 [-EncodePortInServicePrincipalName] [-Encoding <PacketEncoding>] [-HttpPrefix <Uri>]
 [-MaxEnvelopeSizeKB <UInt32>] [-ProxyAuthentication <PasswordAuthenticationMechanism>]
 [-ProxyCertificateThumbprint <String>] [-ProxyCredential <PSCredential>] [-ProxyType <ProxyType>]
 [-UseSsl] [-UICulture <CultureInfo>] [-Culture <CultureInfo>] [<CommonParameters>]
```

### <span data-ttu-id="9fa24-108">DcomParameterSet</span><span class="sxs-lookup"><span data-stu-id="9fa24-108">DcomParameterSet</span></span>

```
New-CimSessionOption [-Impersonation <ImpersonationType>] [-PacketIntegrity] [-PacketPrivacy]
 [-UICulture <CultureInfo>] [-Culture <CultureInfo>] [<CommonParameters>]
```

## <span data-ttu-id="9fa24-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9fa24-109">DESCRIPTION</span></span>

<span data-ttu-id="9fa24-110">O `New-CimSessionOption` cmdlet cria uma instância de um objeto de opções de sessão CIM.</span><span class="sxs-lookup"><span data-stu-id="9fa24-110">The `New-CimSessionOption` cmdlet creates an instance of a CIM session options object.</span></span> <span data-ttu-id="9fa24-111">Você usa um objeto de opções de sessão CIM como entrada para o `New-CimSession` cmdlet para especificar as opções para uma sessão CIM.</span><span class="sxs-lookup"><span data-stu-id="9fa24-111">You use a CIM session options object as input to the `New-CimSession` cmdlet to specify the options for a CIM session.</span></span>

<span data-ttu-id="9fa24-112">Esse cmdlet tem dois conjuntos de parâmetros, um para opções WsMan e outro para as opções distribuídas de Component Object Model (DCOM).</span><span class="sxs-lookup"><span data-stu-id="9fa24-112">This cmdlet has two parameter sets, one for WsMan options and one for Distributed Component Object Model (DCOM) options.</span></span> <span data-ttu-id="9fa24-113">Dependendo de quais parâmetros você usa, o cmdlet retorna uma instância de opções de sessão DCOM ou retorna opções de sessão do WsMan.</span><span class="sxs-lookup"><span data-stu-id="9fa24-113">Depending on which parameters you use, the cmdlet returns either an instance of DCOM session options or returns WsMan session options.</span></span>

## <span data-ttu-id="9fa24-114">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="9fa24-114">EXAMPLES</span></span>

### <span data-ttu-id="9fa24-115">Exemplo 1: criar um objeto de opções de sessão CIM para DCOM</span><span class="sxs-lookup"><span data-stu-id="9fa24-115">Example 1: Create a CIM session options object for DCOM</span></span>

<span data-ttu-id="9fa24-116">Este exemplo cria um objeto de opções de sessão CIM para o protocolo DCOM e o armazena em uma variável chamada `$so` .</span><span class="sxs-lookup"><span data-stu-id="9fa24-116">This example creates a CIM session options object for the DCOM protocol and stores it in a variable named `$so`.</span></span> <span data-ttu-id="9fa24-117">O conteúdo da variável é passado para o `New-CimSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9fa24-117">The contents of the variable are then passed to the `New-CimSession` cmdlet.</span></span>
<span data-ttu-id="9fa24-118">`New-CimSession` em seguida, cria uma nova sessão CIM com o servidor remoto chamado Server01, usando as opções definidas na variável.</span><span class="sxs-lookup"><span data-stu-id="9fa24-118">`New-CimSession` then creates a new CIM session with the remote server named Server01, using the options defined in the variable.</span></span>

```powershell
$so = New-CimSessionOption -Protocol DCOM
New-CimSession -ComputerName Server01 -SessionOption $so
```

### <span data-ttu-id="9fa24-119">Exemplo 2: criar um objeto de opções de sessão CIM para WsMan</span><span class="sxs-lookup"><span data-stu-id="9fa24-119">Example 2: Create a CIM session options object for WsMan</span></span>

<span data-ttu-id="9fa24-120">Este exemplo cria um objeto de opções de sessão CIM para o protocolo WsMan.</span><span class="sxs-lookup"><span data-stu-id="9fa24-120">This example creates a CIM session options object for the WsMan protocol.</span></span> <span data-ttu-id="9fa24-121">O objeto contém a configuração para o modo de autenticação do **Kerberos** especificado pelo parâmetro **ProxyAuthentication** , as credenciais especificadas pelo parâmetro **ProxyCredential** e especifica que o comando é para ignorar a verificação de autoridade de certificação, ignorar a verificação de CN e usar SSL.</span><span class="sxs-lookup"><span data-stu-id="9fa24-121">The object contains configuration for the authentication mode of **Kerberos** specified by the **ProxyAuthentication** parameter, the credentials specified by the **ProxyCredential** parameter, and specifies that the command is to skip the CA check, skip the CN check, and use SSL.</span></span>

```powershell
New-CimSessionOption -ProxyAuthentication Kerberos -ProxyCredential $cred -SkipCACheck -SkipCNCheck -UseSsl
```

### <span data-ttu-id="9fa24-122">Exemplo 3: criar um objeto de opções de sessão CIM com a cultura especificada</span><span class="sxs-lookup"><span data-stu-id="9fa24-122">Example 3: Create a CIM session options object with the culture specified</span></span>

```powershell
New-CimSessionOption -Culture Fr-Fr -Protocol Wsman
```

<span data-ttu-id="9fa24-123">Este exemplo especifica a cultura que é usada para a sessão CIM.</span><span class="sxs-lookup"><span data-stu-id="9fa24-123">This example specifies the culture that is used for the CIM session.</span></span> <span data-ttu-id="9fa24-124">Por padrão, a cultura do cliente é usada durante a execução de operações.</span><span class="sxs-lookup"><span data-stu-id="9fa24-124">By default, the culture of the client is used when performing operations.</span></span> <span data-ttu-id="9fa24-125">No entanto, a cultura padrão pode ser substituída usando o parâmetro **Culture** .</span><span class="sxs-lookup"><span data-stu-id="9fa24-125">However, the default culture can be overridden using the **Culture** parameter.</span></span>

## <span data-ttu-id="9fa24-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9fa24-126">PARAMETERS</span></span>

### <span data-ttu-id="9fa24-127">-Culture</span><span class="sxs-lookup"><span data-stu-id="9fa24-127">-Culture</span></span>

<span data-ttu-id="9fa24-128">Especifica a cultura da interface do usuário a ser usada para a sessão CIM.</span><span class="sxs-lookup"><span data-stu-id="9fa24-128">Specifies the user interface culture to use for the CIM session.</span></span> <span data-ttu-id="9fa24-129">Especifique o valor para esse parâmetro usando um dos seguintes formatos:</span><span class="sxs-lookup"><span data-stu-id="9fa24-129">Specify the value for this parameter using one of the following formats:</span></span>

- <span data-ttu-id="9fa24-130">Um nome de cultura em `<languagecode2>-<country/regioncode2>` formato como "en-US".</span><span class="sxs-lookup"><span data-stu-id="9fa24-130">A culture name in `<languagecode2>-<country/regioncode2>` format such as "EN-US".</span></span>
- <span data-ttu-id="9fa24-131">Uma variável que contém um objeto **CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="9fa24-131">A variable that contains a **CultureInfo** object.</span></span>
- <span data-ttu-id="9fa24-132">Um comando que obtém um objeto **CultureInfo** , como [Get-Culture](../Microsoft.PowerShell.Utility/Get-Culture.md)</span><span class="sxs-lookup"><span data-stu-id="9fa24-132">A command that gets a **CultureInfo** object, such as [Get-Culture](../Microsoft.PowerShell.Utility/Get-Culture.md)</span></span>

```yaml
Type: System.Globalization.CultureInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9fa24-133">-EncodePortInServicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="9fa24-133">-EncodePortInServicePrincipalName</span></span>

<span data-ttu-id="9fa24-134">Indica que a conexão Kerberos está se conectando a um serviço cujo nome da entidade de serviço (SPN) inclui o número da porta de serviço.</span><span class="sxs-lookup"><span data-stu-id="9fa24-134">Indicates that the Kerberos connection is connecting to a service whose service principal name (SPN) includes the service port number.</span></span> <span data-ttu-id="9fa24-135">Esse tipo de conexão não é comum.</span><span class="sxs-lookup"><span data-stu-id="9fa24-135">This type of connection is not common.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9fa24-136">-Codificação</span><span class="sxs-lookup"><span data-stu-id="9fa24-136">-Encoding</span></span>

<span data-ttu-id="9fa24-137">Especifica a codificação usada para o protocolo WsMan.</span><span class="sxs-lookup"><span data-stu-id="9fa24-137">Specifies the encoding used for the WsMan protocol.</span></span> <span data-ttu-id="9fa24-138">Os valores aceitáveis para esse parâmetro são: **Default**, **UTF8** ou **Utf16**.</span><span class="sxs-lookup"><span data-stu-id="9fa24-138">The acceptable values for this parameter are: **Default**, **Utf8**, or **Utf16**.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.Options.PacketEncoding
Parameter Sets: WSManParameterSet
Aliases:
Accepted values: Default, Utf8, Utf16

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9fa24-139">-HttpPrefix</span><span class="sxs-lookup"><span data-stu-id="9fa24-139">-HttpPrefix</span></span>

<span data-ttu-id="9fa24-140">Especifica a parte da URL HTTP após o nome do computador e o número da porta.</span><span class="sxs-lookup"><span data-stu-id="9fa24-140">Specifies the part of the HTTP URL after the computer name and port number.</span></span> <span data-ttu-id="9fa24-141">Alterar isso não é comum.</span><span class="sxs-lookup"><span data-stu-id="9fa24-141">Changing this is not common.</span></span> <span data-ttu-id="9fa24-142">Por padrão, o valor desse parâmetro é **/WSMan**.</span><span class="sxs-lookup"><span data-stu-id="9fa24-142">By default, the value of this parameter is **/wsman**.</span></span>

```yaml
Type: System.Uri
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9fa24-143">-Representação</span><span class="sxs-lookup"><span data-stu-id="9fa24-143">-Impersonation</span></span>

<span data-ttu-id="9fa24-144">Cria uma sessão DCOM para Instrumentação de Gerenciamento do Windows (WMI) usando a representação.</span><span class="sxs-lookup"><span data-stu-id="9fa24-144">Creates a DCOM session to Windows Management Instrumentation (WMI) using impersonation.</span></span>

<span data-ttu-id="9fa24-145">Os valores válidos para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="9fa24-145">Valid values for this parameter are:</span></span>

- <span data-ttu-id="9fa24-146">Padrão: o DCOM pode escolher o nível de representação usando seu algoritmo de negociação de segurança normal.</span><span class="sxs-lookup"><span data-stu-id="9fa24-146">Default: DCOM can choose the impersonation level using its normal security negotiation algorithm.</span></span>
- <span data-ttu-id="9fa24-147">Nenhum: o cliente é anônimo para o servidor.</span><span class="sxs-lookup"><span data-stu-id="9fa24-147">None: The client is anonymous to the server.</span></span> <span data-ttu-id="9fa24-148">O processo do servidor pode representar o cliente, mas o token de representação não contém nenhuma informação e não pode ser usado.</span><span class="sxs-lookup"><span data-stu-id="9fa24-148">The server process can impersonate the client, but the impersonation token does not contain any information and cannot be used.</span></span>
- <span data-ttu-id="9fa24-149">Identificar: permite que os objetos consultem as credenciais do chamador.</span><span class="sxs-lookup"><span data-stu-id="9fa24-149">Identify: Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="9fa24-150">Impersonate: permite que os objetos usem as credenciais do chamador.</span><span class="sxs-lookup"><span data-stu-id="9fa24-150">Impersonate: Allows objects to use the credentials of the caller.</span></span>
- <span data-ttu-id="9fa24-151">Delegate: permite que os objetos permitam que outros objetos usem as credenciais do chamador.</span><span class="sxs-lookup"><span data-stu-id="9fa24-151">Delegate: Allows objects to permit other objects to use the credentials of the caller.</span></span>

<span data-ttu-id="9fa24-152">Se a **representação** não for especificada, o `New-CimSession` cmdlet usará o valor de **Impersonate**.</span><span class="sxs-lookup"><span data-stu-id="9fa24-152">If **Impersonation** is not specified, the `New-CimSession` cmdlet uses the value of **Impersonate**.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.Options.ImpersonationType
Parameter Sets: DcomParameterSet
Aliases:
Accepted values: Default, None, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9fa24-153">-MaxEnvelopeSizeKB</span><span class="sxs-lookup"><span data-stu-id="9fa24-153">-MaxEnvelopeSizeKB</span></span>

<span data-ttu-id="9fa24-154">Especifica o limite de tamanho de mensagens de XML WsMan para qualquer direção.</span><span class="sxs-lookup"><span data-stu-id="9fa24-154">Specifies the size limit of WsMan XML messages for either direction.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9fa24-155">-NoEncryption</span><span class="sxs-lookup"><span data-stu-id="9fa24-155">-NoEncryption</span></span>

<span data-ttu-id="9fa24-156">Especifica que a criptografia de dados está desativada.</span><span class="sxs-lookup"><span data-stu-id="9fa24-156">Specifies that data encryption is turned off.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9fa24-157">-PacketIntegrity</span><span class="sxs-lookup"><span data-stu-id="9fa24-157">-PacketIntegrity</span></span>

<span data-ttu-id="9fa24-158">Especifica que a sessão DCOM criada para o WMI usa Component Object Model a funcionalidade _PacketIntegrity_ (com).</span><span class="sxs-lookup"><span data-stu-id="9fa24-158">Specifies that the DCOM session created to WMI uses the Component Object Model (COM) _PacketIntegrity_ functionality.</span></span> <span data-ttu-id="9fa24-159">Por padrão, todas as sessões CIM criadas usando DCOM têm o parâmetro **PacketIntegrity** definido como **true**.</span><span class="sxs-lookup"><span data-stu-id="9fa24-159">By default, all CIM sessions created using DCOM have the **PacketIntegrity** parameter set to **True**.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DcomParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9fa24-160">-PacketPrivacy</span><span class="sxs-lookup"><span data-stu-id="9fa24-160">-PacketPrivacy</span></span>

<span data-ttu-id="9fa24-161">Cria uma sessão DCOM para o WMI usando o _PACKETPRIVACY_ com.</span><span class="sxs-lookup"><span data-stu-id="9fa24-161">Creates a DCOM session to WMI using the COM _PacketPrivacy_.</span></span> <span data-ttu-id="9fa24-162">Por padrão, todas as sessões CIM criadas usando DCOM têm o parâmetro **PacketPrivacy** definido como **true**.</span><span class="sxs-lookup"><span data-stu-id="9fa24-162">By default, all CIM sessions created using DCOM have the **PacketPrivacy** parameter set to **true**.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DcomParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9fa24-163">-Protocol</span><span class="sxs-lookup"><span data-stu-id="9fa24-163">-Protocol</span></span>

<span data-ttu-id="9fa24-164">Especifica o protocolo a ser usado.</span><span class="sxs-lookup"><span data-stu-id="9fa24-164">Specifies the protocol to use.</span></span> <span data-ttu-id="9fa24-165">Os valores aceitáveis para esse parâmetro são: **DCOM**, **Default** ou **WSMan**.</span><span class="sxs-lookup"><span data-stu-id="9fa24-165">The acceptable values for this parameter are: **DCOM**, **Default**, or **Wsman**.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimCmdlets.ProtocolType
Parameter Sets: ProtocolTypeSet
Aliases:
Accepted values: Dcom, Default, Wsman

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9fa24-166">-ProxyAuthentication</span><span class="sxs-lookup"><span data-stu-id="9fa24-166">-ProxyAuthentication</span></span>

<span data-ttu-id="9fa24-167">Especifica o método de autenticação a ser usado para a resolução de proxy.</span><span class="sxs-lookup"><span data-stu-id="9fa24-167">Specifies the authentication method to use for proxy resolution.</span></span> <span data-ttu-id="9fa24-168">Os valores aceitáveis para esse parâmetro são: **Default**, **Digest**, **Negotiate**, **Basic**, **Kerberos**, **NtlmDomain** ou **CredSsp**.</span><span class="sxs-lookup"><span data-stu-id="9fa24-168">The acceptable values for this parameter are: **Default**, **Digest**, **Negotiate**, **Basic**, **Kerberos**, **NtlmDomain**, or **CredSsp**.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.Options.PasswordAuthenticationMechanism
Parameter Sets: WSManParameterSet
Aliases:
Accepted values: Default, Digest, Negotiate, Basic, Kerberos, NtlmDomain, CredSsp

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9fa24-169">-ProxyCertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="9fa24-169">-ProxyCertificateThumbprint</span></span>

<span data-ttu-id="9fa24-170">Especifica o certificado de chave pública digital (x. 509) de uma conta de usuário para autenticação de proxy.</span><span class="sxs-lookup"><span data-stu-id="9fa24-170">Specifies the (x.509) digital public key certificate of a user account for proxy authentication.</span></span>
<span data-ttu-id="9fa24-171">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="9fa24-171">Enter the certificate thumbprint of the certificate.</span></span> <span data-ttu-id="9fa24-172">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="9fa24-172">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="9fa24-173">Eles só podem ser mapeados para contas de usuário locais e não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="9fa24-173">They can only be mapped to local user accounts and they do not work with domain accounts.</span></span>

<span data-ttu-id="9fa24-174">Para obter uma impressão digital do certificado, use os `Get-Item` `Get-ChildItem` cmdlets ou na unidade certificado do PowerShell:.</span><span class="sxs-lookup"><span data-stu-id="9fa24-174">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` cmdlets in the PowerShell Cert: drive.</span></span>

```yaml
Type: System.String
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9fa24-175">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="9fa24-175">-ProxyCredential</span></span>

<span data-ttu-id="9fa24-176">Especifica as credenciais a usar para autenticação de proxy.</span><span class="sxs-lookup"><span data-stu-id="9fa24-176">Specifies the credentials to use for proxy authentication.</span></span> <span data-ttu-id="9fa24-177">Insira um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="9fa24-177">Enter one of the following:</span></span>

- <span data-ttu-id="9fa24-178">Uma variável que contém um objeto PSCredential.</span><span class="sxs-lookup"><span data-stu-id="9fa24-178">A variable that contains a PSCredential object.</span></span>
- <span data-ttu-id="9fa24-179">Um comando que obtém um objeto PSCredential, como `Get-Credential`</span><span class="sxs-lookup"><span data-stu-id="9fa24-179">A command that gets a PSCredential object, such as `Get-Credential`</span></span>

<span data-ttu-id="9fa24-180">Se essa opção não for definida, você não poderá especificar nenhuma credencial.</span><span class="sxs-lookup"><span data-stu-id="9fa24-180">If this option is not set, then you cannot specify any credentials.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9fa24-181">-ProxyType</span><span class="sxs-lookup"><span data-stu-id="9fa24-181">-ProxyType</span></span>

<span data-ttu-id="9fa24-182">Especifica o mecanismo de resolução de nomes de host a ser usado.</span><span class="sxs-lookup"><span data-stu-id="9fa24-182">Specifies the host name resolution mechanism to use.</span></span> <span data-ttu-id="9fa24-183">Os valores aceitáveis para esse parâmetro são: **None**, **WinHTTP**, **auto** ou **InternetExplorer**.</span><span class="sxs-lookup"><span data-stu-id="9fa24-183">The acceptable values for this parameter are: **None**, **WinHttp**, **Auto**, or **InternetExplorer**.</span></span>

<span data-ttu-id="9fa24-184">O valor padrão desse parâmetro é **InternetExplorer**.</span><span class="sxs-lookup"><span data-stu-id="9fa24-184">The default value of this parameter is **InternetExplorer**.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.Options.ProxyType
Parameter Sets: WSManParameterSet
Aliases:
Accepted values: None, WinHttp, Auto, InternetExplorer

Required: False
Position: Named
Default value: InternetExplorer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9fa24-185">-SkipCACheck</span><span class="sxs-lookup"><span data-stu-id="9fa24-185">-SkipCACheck</span></span>

<span data-ttu-id="9fa24-186">Indica que, ao se conectar via HTTPS, o cliente não valida se o certificado do servidor está assinado por uma autoridade de certificação (CA) confiável.</span><span class="sxs-lookup"><span data-stu-id="9fa24-186">Indicates that when connecting over HTTPS, the client does not validate that the server certificate is signed by a trusted certification authority (CA).</span></span>

<span data-ttu-id="9fa24-187">Use esse parâmetro somente quando o computador remoto for confiável usando outro mecanismo, como quando o computador remoto fizer parte de uma rede que esteja fisicamente segura e isolada, ou quando o computador remoto estiver listado como um host confiável em uma configuração do WinRM.</span><span class="sxs-lookup"><span data-stu-id="9fa24-187">Use this parameter only when the remote computer is trusted using another mechanism, such as when the remote computer is part of a network that is physically secure and isolated, or when the remote computer is listed as a trusted host in a WinRM configuration.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9fa24-188">-SkipCNCheck</span><span class="sxs-lookup"><span data-stu-id="9fa24-188">-SkipCNCheck</span></span>

<span data-ttu-id="9fa24-189">Indica que o nome comum do certificado (CN) do servidor não precisa corresponder ao hostname do servidor.</span><span class="sxs-lookup"><span data-stu-id="9fa24-189">Indicates that the certificate common name (CN) of the server does not need to match the hostname of the server.</span></span> <span data-ttu-id="9fa24-190">Use esse parâmetro para operações remotas somente com computadores confiáveis que usam o protocolo HTTPS.</span><span class="sxs-lookup"><span data-stu-id="9fa24-190">Use this parameter for remote operations only with trusted computers that use the HTTPS protocol.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9fa24-191">-SkipRevocationCheck</span><span class="sxs-lookup"><span data-stu-id="9fa24-191">-SkipRevocationCheck</span></span>

<span data-ttu-id="9fa24-192">Indica que a verificação de revogação para certificados de servidor é ignorada.</span><span class="sxs-lookup"><span data-stu-id="9fa24-192">Indicates that the revocation check for server certificates is skipped.</span></span> <span data-ttu-id="9fa24-193">Use esse parâmetro somente para computadores confiáveis.</span><span class="sxs-lookup"><span data-stu-id="9fa24-193">Use this parameter only for trusted computers.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9fa24-194">-UICulture</span><span class="sxs-lookup"><span data-stu-id="9fa24-194">-UICulture</span></span>

<span data-ttu-id="9fa24-195">Especifica a cultura da interface do usuário a ser usada para a sessão CIM.</span><span class="sxs-lookup"><span data-stu-id="9fa24-195">Specifies the user interface culture to use for the CIM session.</span></span> <span data-ttu-id="9fa24-196">Especifique o valor para esse parâmetro usando um dos seguintes formatos:</span><span class="sxs-lookup"><span data-stu-id="9fa24-196">Specify the value for this parameter using one of the following formats:</span></span>

- <span data-ttu-id="9fa24-197">Um nome de cultura em `<languagecode2>-<country/regioncode2>` formato como "en-US".</span><span class="sxs-lookup"><span data-stu-id="9fa24-197">A culture name in `<languagecode2>-<country/regioncode2>` format such as "EN-US".</span></span>
- <span data-ttu-id="9fa24-198">Uma variável que contém um objeto CultureInfo.</span><span class="sxs-lookup"><span data-stu-id="9fa24-198">A variable that contains a CultureInfo object.</span></span>
- <span data-ttu-id="9fa24-199">Um comando que obtém um objeto CultureInfo, como `Get-Culture` .</span><span class="sxs-lookup"><span data-stu-id="9fa24-199">A command that gets a CultureInfo object, such as `Get-Culture`.</span></span>

```yaml
Type: System.Globalization.CultureInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9fa24-200">-UseSsl</span><span class="sxs-lookup"><span data-stu-id="9fa24-200">-UseSsl</span></span>

<span data-ttu-id="9fa24-201">Indica que o SSL deve ser usado para estabelecer uma conexão com o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="9fa24-201">Indicates that SSL should be used to establish a connection to the remote computer.</span></span> <span data-ttu-id="9fa24-202">Por padrão, SSL não é usado.</span><span class="sxs-lookup"><span data-stu-id="9fa24-202">By default, SSL is not used.</span></span> <span data-ttu-id="9fa24-203">O WsMan criptografa todo o conteúdo transmitido pela rede, mesmo ao usar HTTP.</span><span class="sxs-lookup"><span data-stu-id="9fa24-203">WsMan encrypts all content that is transmitted over the network, even when using HTTP.</span></span>

<span data-ttu-id="9fa24-204">Esse parâmetro permite especificar a proteção adicional do HTTPS em vez de HTTP.</span><span class="sxs-lookup"><span data-stu-id="9fa24-204">This parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span> <span data-ttu-id="9fa24-205">Se o SSL não estiver disponível na porta usada para a conexão e você especificar esse parâmetro, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="9fa24-205">If SSL is not available on the port used for the connection and you specify this parameter, then the command fails.</span></span>

<span data-ttu-id="9fa24-206">É recomendável que você use esse parâmetro somente quando o parâmetro **PacketPrivacy** não for especificado.</span><span class="sxs-lookup"><span data-stu-id="9fa24-206">It is recommended that you use this parameter only when the **PacketPrivacy** parameter is not specified.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9fa24-207">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9fa24-207">CommonParameters</span></span>

<span data-ttu-id="9fa24-208">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9fa24-208">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9fa24-209">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9fa24-209">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9fa24-210">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="9fa24-210">INPUTS</span></span>

### <span data-ttu-id="9fa24-211">Nenhum</span><span class="sxs-lookup"><span data-stu-id="9fa24-211">None</span></span>

<span data-ttu-id="9fa24-212">Esse cmdlet não aceita nenhum objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="9fa24-212">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="9fa24-213">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="9fa24-213">OUTPUTS</span></span>

### <span data-ttu-id="9fa24-214">CIMSessionOption</span><span class="sxs-lookup"><span data-stu-id="9fa24-214">CIMSessionOption</span></span>

<span data-ttu-id="9fa24-215">Esse cmdlet retorna um objeto que contém informações de opções de sessão CIM.</span><span class="sxs-lookup"><span data-stu-id="9fa24-215">This cmdlet returns an object that contains CIM session options information.</span></span>

## <span data-ttu-id="9fa24-216">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="9fa24-216">NOTES</span></span>

## <span data-ttu-id="9fa24-217">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="9fa24-217">RELATED LINKS</span></span>

[<span data-ttu-id="9fa24-218">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="9fa24-218">Get-ChildItem</span></span>](../microsoft.powershell.management/get-childitem.md)

[<span data-ttu-id="9fa24-219">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="9fa24-219">Get-Credential</span></span>](../microsoft.powershell.security/get-credential.md)

[<span data-ttu-id="9fa24-220">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="9fa24-220">Get-Culture</span></span>](../microsoft.powershell.utility/get-culture.md)

[<span data-ttu-id="9fa24-221">Get-Item</span><span class="sxs-lookup"><span data-stu-id="9fa24-221">Get-Item</span></span>](../microsoft.powershell.management/get-item.md)

[<span data-ttu-id="9fa24-222">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="9fa24-222">New-CimSession</span></span>](New-CimSession.md)

