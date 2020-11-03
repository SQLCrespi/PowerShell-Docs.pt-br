---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/new-cimsessionoption?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-CimSessionOption
ms.openlocfilehash: f43e84dfc5b3255d17df266bf04a05778362847b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194097"
---
# <span data-ttu-id="e07e4-103">New-CimSessionOption</span><span class="sxs-lookup"><span data-stu-id="e07e4-103">New-CimSessionOption</span></span>

## <span data-ttu-id="e07e4-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="e07e4-104">SYNOPSIS</span></span>
<span data-ttu-id="e07e4-105">Especifica opções avançadas para o cmdlet New-CimSession.</span><span class="sxs-lookup"><span data-stu-id="e07e4-105">Specifies advanced options for the New-CimSession cmdlet.</span></span>

## <span data-ttu-id="e07e4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e07e4-106">SYNTAX</span></span>

### <span data-ttu-id="e07e4-107">ProtocolTypeSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="e07e4-107">ProtocolTypeSet (Default)</span></span>

```
New-CimSessionOption [-Protocol] <ProtocolType> [-UICulture <CultureInfo>] [-Culture <CultureInfo>]
 [<CommonParameters>]
```

### <span data-ttu-id="e07e4-108">WSManParameterSet</span><span class="sxs-lookup"><span data-stu-id="e07e4-108">WSManParameterSet</span></span>

```
New-CimSessionOption [-NoEncryption] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck]
 [-EncodePortInServicePrincipalName] [-Encoding <PacketEncoding>] [-HttpPrefix <Uri>]
 [-MaxEnvelopeSizeKB <UInt32>] [-ProxyAuthentication <PasswordAuthenticationMechanism>]
 [-ProxyCertificateThumbprint <String>] [-ProxyCredential <PSCredential>] [-ProxyType <ProxyType>]
 [-UseSsl] [-UICulture <CultureInfo>] [-Culture <CultureInfo>] [<CommonParameters>]
```

### <span data-ttu-id="e07e4-109">DcomParameterSet</span><span class="sxs-lookup"><span data-stu-id="e07e4-109">DcomParameterSet</span></span>

```
New-CimSessionOption [-Impersonation <ImpersonationType>] [-PacketIntegrity] [-PacketPrivacy]
 [-UICulture <CultureInfo>] [-Culture <CultureInfo>] [<CommonParameters>]
```

## <span data-ttu-id="e07e4-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e07e4-110">DESCRIPTION</span></span>

<span data-ttu-id="e07e4-111">O `New-CimSessionOption` cmdlet cria uma instância de um objeto de opções de sessão CIM.</span><span class="sxs-lookup"><span data-stu-id="e07e4-111">The `New-CimSessionOption` cmdlet creates an instance of a CIM session options object.</span></span> <span data-ttu-id="e07e4-112">Você usa um objeto de opções de sessão CIM como entrada para o `New-CimSession` cmdlet para especificar as opções para uma sessão CIM.</span><span class="sxs-lookup"><span data-stu-id="e07e4-112">You use a CIM session options object as input to the `New-CimSession` cmdlet to specify the options for a CIM session.</span></span>

<span data-ttu-id="e07e4-113">Esse cmdlet tem dois conjuntos de parâmetros, um para opções WsMan e outro para as opções distribuídas de Component Object Model (DCOM).</span><span class="sxs-lookup"><span data-stu-id="e07e4-113">This cmdlet has two parameter sets, one for WsMan options and one for Distributed Component Object Model (DCOM) options.</span></span> <span data-ttu-id="e07e4-114">Dependendo de quais parâmetros você usa, o cmdlet retorna uma instância de opções de sessão DCOM ou retorna opções de sessão do WsMan.</span><span class="sxs-lookup"><span data-stu-id="e07e4-114">Depending on which parameters you use, the cmdlet returns either an instance of DCOM session options or returns WsMan session options.</span></span>

## <span data-ttu-id="e07e4-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="e07e4-115">EXAMPLES</span></span>

### <span data-ttu-id="e07e4-116">Exemplo 1: criar um objeto de opções de sessão CIM para DCOM</span><span class="sxs-lookup"><span data-stu-id="e07e4-116">Example 1: Create a CIM session options object for DCOM</span></span>

<span data-ttu-id="e07e4-117">Este exemplo cria um objeto de opções de sessão CIM para o protocolo DCOM e o armazena em uma variável chamada `$so` .</span><span class="sxs-lookup"><span data-stu-id="e07e4-117">This example creates a CIM session options object for the DCOM protocol and stores it in a variable named `$so`.</span></span> <span data-ttu-id="e07e4-118">O conteúdo da variável é passado para o `New-CimSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e07e4-118">The contents of the variable are then passed to the `New-CimSession` cmdlet.</span></span>
<span data-ttu-id="e07e4-119">`New-CimSession` em seguida, cria uma nova sessão CIM com o servidor remoto chamado Server01, usando as opções definidas na variável.</span><span class="sxs-lookup"><span data-stu-id="e07e4-119">`New-CimSession` then creates a new CIM session with the remote server named Server01, using the options defined in the variable.</span></span>

```powershell
$so = New-CimSessionOption -Protocol DCOM
New-CimSession -ComputerName Server01 -SessionOption $so
```

### <span data-ttu-id="e07e4-120">Exemplo 2: criar um objeto de opções de sessão CIM para WsMan</span><span class="sxs-lookup"><span data-stu-id="e07e4-120">Example 2: Create a CIM session options object for WsMan</span></span>

<span data-ttu-id="e07e4-121">Este exemplo cria um objeto de opções de sessão CIM para o protocolo WsMan.</span><span class="sxs-lookup"><span data-stu-id="e07e4-121">This example creates a CIM session options object for the WsMan protocol.</span></span> <span data-ttu-id="e07e4-122">O objeto contém a configuração para o modo de autenticação do **Kerberos** especificado pelo parâmetro **ProxyAuthentication** , as credenciais especificadas pelo parâmetro **ProxyCredential** e especifica que o comando é para ignorar a verificação de autoridade de certificação, ignorar a verificação de CN e usar SSL.</span><span class="sxs-lookup"><span data-stu-id="e07e4-122">The object contains configuration for the authentication mode of **Kerberos** specified by the **ProxyAuthentication** parameter, the credentials specified by the **ProxyCredential** parameter, and specifies that the command is to skip the CA check, skip the CN check, and use SSL.</span></span>

```powershell
New-CimSessionOption -ProxyAuthentication Kerberos -ProxyCredential $cred -SkipCACheck -SkipCNCheck -UseSsl
```

### <span data-ttu-id="e07e4-123">Exemplo 3: criar um objeto de opções de sessão CIM com a cultura especificada</span><span class="sxs-lookup"><span data-stu-id="e07e4-123">Example 3: Create a CIM session options object with the culture specified</span></span>

```powershell
New-CimSessionOption -Culture Fr-Fr -Protocol Wsman
```

<span data-ttu-id="e07e4-124">Este exemplo especifica a cultura que é usada para a sessão CIM.</span><span class="sxs-lookup"><span data-stu-id="e07e4-124">This example specifies the culture that is used for the CIM session.</span></span> <span data-ttu-id="e07e4-125">Por padrão, a cultura do cliente é usada durante a execução de operações.</span><span class="sxs-lookup"><span data-stu-id="e07e4-125">By default, the culture of the client is used when performing operations.</span></span> <span data-ttu-id="e07e4-126">No entanto, a cultura padrão pode ser substituída usando o parâmetro **Culture** .</span><span class="sxs-lookup"><span data-stu-id="e07e4-126">However, the default culture can be overridden using the **Culture** parameter.</span></span>

## <span data-ttu-id="e07e4-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e07e4-127">PARAMETERS</span></span>

### <span data-ttu-id="e07e4-128">-Culture</span><span class="sxs-lookup"><span data-stu-id="e07e4-128">-Culture</span></span>

<span data-ttu-id="e07e4-129">Especifica a cultura da interface do usuário a ser usada para a sessão CIM.</span><span class="sxs-lookup"><span data-stu-id="e07e4-129">Specifies the user interface culture to use for the CIM session.</span></span> <span data-ttu-id="e07e4-130">Especifique o valor para esse parâmetro usando um dos seguintes formatos:</span><span class="sxs-lookup"><span data-stu-id="e07e4-130">Specify the value for this parameter using one of the following formats:</span></span>

- <span data-ttu-id="e07e4-131">Um nome de cultura em `<languagecode2>-<country/regioncode2>` formato como "en-US".</span><span class="sxs-lookup"><span data-stu-id="e07e4-131">A culture name in `<languagecode2>-<country/regioncode2>` format such as "EN-US".</span></span>
- <span data-ttu-id="e07e4-132">Uma variável que contém um objeto **CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="e07e4-132">A variable that contains a **CultureInfo** object.</span></span>
- <span data-ttu-id="e07e4-133">Um comando que obtém um objeto **CultureInfo** , como [Get-Culture](../Microsoft.PowerShell.Utility/Get-Culture.md)</span><span class="sxs-lookup"><span data-stu-id="e07e4-133">A command that gets a **CultureInfo** object, such as [Get-Culture](../Microsoft.PowerShell.Utility/Get-Culture.md)</span></span>

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

### <span data-ttu-id="e07e4-134">-EncodePortInServicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="e07e4-134">-EncodePortInServicePrincipalName</span></span>

<span data-ttu-id="e07e4-135">Indica que a conexão Kerberos está se conectando a um serviço cujo nome da entidade de serviço (SPN) inclui o número da porta de serviço.</span><span class="sxs-lookup"><span data-stu-id="e07e4-135">Indicates that the Kerberos connection is connecting to a service whose service principal name (SPN) includes the service port number.</span></span> <span data-ttu-id="e07e4-136">Esse tipo de conexão não é comum.</span><span class="sxs-lookup"><span data-stu-id="e07e4-136">This type of connection is not common.</span></span>

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

### <span data-ttu-id="e07e4-137">-Codificação</span><span class="sxs-lookup"><span data-stu-id="e07e4-137">-Encoding</span></span>

<span data-ttu-id="e07e4-138">Especifica a codificação usada para o protocolo WsMan.</span><span class="sxs-lookup"><span data-stu-id="e07e4-138">Specifies the encoding used for the WsMan protocol.</span></span> <span data-ttu-id="e07e4-139">Os valores aceitáveis para esse parâmetro são: **Default** , **UTF8** ou **Utf16** .</span><span class="sxs-lookup"><span data-stu-id="e07e4-139">The acceptable values for this parameter are: **Default** , **Utf8** , or **Utf16** .</span></span>

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

### <span data-ttu-id="e07e4-140">-HttpPrefix</span><span class="sxs-lookup"><span data-stu-id="e07e4-140">-HttpPrefix</span></span>

<span data-ttu-id="e07e4-141">Especifica a parte da URL HTTP após o nome do computador e o número da porta.</span><span class="sxs-lookup"><span data-stu-id="e07e4-141">Specifies the part of the HTTP URL after the computer name and port number.</span></span> <span data-ttu-id="e07e4-142">Alterar isso não é comum.</span><span class="sxs-lookup"><span data-stu-id="e07e4-142">Changing this is not common.</span></span> <span data-ttu-id="e07e4-143">Por padrão, o valor desse parâmetro é **/WSMan** .</span><span class="sxs-lookup"><span data-stu-id="e07e4-143">By default, the value of this parameter is **/wsman** .</span></span>

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

### <span data-ttu-id="e07e4-144">-Representação</span><span class="sxs-lookup"><span data-stu-id="e07e4-144">-Impersonation</span></span>

<span data-ttu-id="e07e4-145">Cria uma sessão DCOM para Instrumentação de Gerenciamento do Windows (WMI) usando a representação.</span><span class="sxs-lookup"><span data-stu-id="e07e4-145">Creates a DCOM session to Windows Management Instrumentation (WMI) using impersonation.</span></span>

<span data-ttu-id="e07e4-146">Os valores válidos para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="e07e4-146">Valid values for this parameter are:</span></span>

- <span data-ttu-id="e07e4-147">Padrão: o DCOM pode escolher o nível de representação usando seu algoritmo de negociação de segurança normal.</span><span class="sxs-lookup"><span data-stu-id="e07e4-147">Default: DCOM can choose the impersonation level using its normal security negotiation algorithm.</span></span>
- <span data-ttu-id="e07e4-148">Nenhum: o cliente é anônimo para o servidor.</span><span class="sxs-lookup"><span data-stu-id="e07e4-148">None: The client is anonymous to the server.</span></span> <span data-ttu-id="e07e4-149">O processo do servidor pode representar o cliente, mas o token de representação não contém nenhuma informação e não pode ser usado.</span><span class="sxs-lookup"><span data-stu-id="e07e4-149">The server process can impersonate the client, but the impersonation token does not contain any information and cannot be used.</span></span>
- <span data-ttu-id="e07e4-150">Identificar: permite que os objetos consultem as credenciais do chamador.</span><span class="sxs-lookup"><span data-stu-id="e07e4-150">Identify: Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="e07e4-151">Impersonate: permite que os objetos usem as credenciais do chamador.</span><span class="sxs-lookup"><span data-stu-id="e07e4-151">Impersonate: Allows objects to use the credentials of the caller.</span></span>
- <span data-ttu-id="e07e4-152">Delegate: permite que os objetos permitam que outros objetos usem as credenciais do chamador.</span><span class="sxs-lookup"><span data-stu-id="e07e4-152">Delegate: Allows objects to permit other objects to use the credentials of the caller.</span></span>

<span data-ttu-id="e07e4-153">Se a **representação** não for especificada, o `New-CimSession` cmdlet usará o valor de **Impersonate** .</span><span class="sxs-lookup"><span data-stu-id="e07e4-153">If **Impersonation** is not specified, the `New-CimSession` cmdlet uses the value of **Impersonate** .</span></span>

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

### <span data-ttu-id="e07e4-154">-MaxEnvelopeSizeKB</span><span class="sxs-lookup"><span data-stu-id="e07e4-154">-MaxEnvelopeSizeKB</span></span>

<span data-ttu-id="e07e4-155">Especifica o limite de tamanho de mensagens de XML WsMan para qualquer direção.</span><span class="sxs-lookup"><span data-stu-id="e07e4-155">Specifies the size limit of WsMan XML messages for either direction.</span></span>

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

### <span data-ttu-id="e07e4-156">-NoEncryption</span><span class="sxs-lookup"><span data-stu-id="e07e4-156">-NoEncryption</span></span>

<span data-ttu-id="e07e4-157">Especifica que a criptografia de dados está desativada.</span><span class="sxs-lookup"><span data-stu-id="e07e4-157">Specifies that data encryption is turned off.</span></span>

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

### <span data-ttu-id="e07e4-158">-PacketIntegrity</span><span class="sxs-lookup"><span data-stu-id="e07e4-158">-PacketIntegrity</span></span>

<span data-ttu-id="e07e4-159">Especifica que a sessão DCOM criada para o WMI usa Component Object Model a funcionalidade _PacketIntegrity_ (com).</span><span class="sxs-lookup"><span data-stu-id="e07e4-159">Specifies that the DCOM session created to WMI uses the Component Object Model (COM) _PacketIntegrity_ functionality.</span></span> <span data-ttu-id="e07e4-160">Por padrão, todas as sessões CIM criadas usando DCOM têm o parâmetro **PacketIntegrity** definido como **true** .</span><span class="sxs-lookup"><span data-stu-id="e07e4-160">By default, all CIM sessions created using DCOM have the **PacketIntegrity** parameter set to **True** .</span></span>

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

### <span data-ttu-id="e07e4-161">-PacketPrivacy</span><span class="sxs-lookup"><span data-stu-id="e07e4-161">-PacketPrivacy</span></span>

<span data-ttu-id="e07e4-162">Cria uma sessão DCOM para o WMI usando o _PACKETPRIVACY_ com.</span><span class="sxs-lookup"><span data-stu-id="e07e4-162">Creates a DCOM session to WMI using the COM _PacketPrivacy_ .</span></span> <span data-ttu-id="e07e4-163">Por padrão, todas as sessões CIM criadas usando DCOM têm o parâmetro **PacketPrivacy** definido como **true** .</span><span class="sxs-lookup"><span data-stu-id="e07e4-163">By default, all CIM sessions created using DCOM have the **PacketPrivacy** parameter set to **true** .</span></span>

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

### <span data-ttu-id="e07e4-164">-Protocol</span><span class="sxs-lookup"><span data-stu-id="e07e4-164">-Protocol</span></span>

<span data-ttu-id="e07e4-165">Especifica o protocolo a ser usado.</span><span class="sxs-lookup"><span data-stu-id="e07e4-165">Specifies the protocol to use.</span></span> <span data-ttu-id="e07e4-166">Os valores aceitáveis para esse parâmetro são: **DCOM** , **Default** ou **WSMan** .</span><span class="sxs-lookup"><span data-stu-id="e07e4-166">The acceptable values for this parameter are: **DCOM** , **Default** , or **Wsman** .</span></span>

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

### <span data-ttu-id="e07e4-167">-ProxyAuthentication</span><span class="sxs-lookup"><span data-stu-id="e07e4-167">-ProxyAuthentication</span></span>

<span data-ttu-id="e07e4-168">Especifica o método de autenticação a ser usado para a resolução de proxy.</span><span class="sxs-lookup"><span data-stu-id="e07e4-168">Specifies the authentication method to use for proxy resolution.</span></span> <span data-ttu-id="e07e4-169">Os valores aceitáveis para esse parâmetro são: **Default** , **Digest** , **Negotiate** , **Basic** , **Kerberos** , **NtlmDomain** ou **CredSsp** .</span><span class="sxs-lookup"><span data-stu-id="e07e4-169">The acceptable values for this parameter are: **Default** , **Digest** , **Negotiate** , **Basic** , **Kerberos** , **NtlmDomain** , or **CredSsp** .</span></span>

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

### <span data-ttu-id="e07e4-170">-ProxyCertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="e07e4-170">-ProxyCertificateThumbprint</span></span>

<span data-ttu-id="e07e4-171">Especifica o certificado de chave pública digital (x. 509) de uma conta de usuário para autenticação de proxy.</span><span class="sxs-lookup"><span data-stu-id="e07e4-171">Specifies the (x.509) digital public key certificate of a user account for proxy authentication.</span></span>
<span data-ttu-id="e07e4-172">Insira a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="e07e4-172">Enter the certificate thumbprint of the certificate.</span></span> <span data-ttu-id="e07e4-173">Os certificados são utilizados na autenticação baseada em certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="e07e4-173">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="e07e4-174">Eles só podem ser mapeados para contas de usuário locais e não funcionam com contas de domínio.</span><span class="sxs-lookup"><span data-stu-id="e07e4-174">They can only be mapped to local user accounts and they do not work with domain accounts.</span></span>

<span data-ttu-id="e07e4-175">Para obter uma impressão digital do certificado, use os `Get-Item` `Get-ChildItem` cmdlets ou na unidade certificado do PowerShell:.</span><span class="sxs-lookup"><span data-stu-id="e07e4-175">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` cmdlets in the PowerShell Cert: drive.</span></span>

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

### <span data-ttu-id="e07e4-176">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="e07e4-176">-ProxyCredential</span></span>

<span data-ttu-id="e07e4-177">Especifica as credenciais a usar para autenticação de proxy.</span><span class="sxs-lookup"><span data-stu-id="e07e4-177">Specifies the credentials to use for proxy authentication.</span></span> <span data-ttu-id="e07e4-178">Insira um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="e07e4-178">Enter one of the following:</span></span>

- <span data-ttu-id="e07e4-179">Uma variável que contém um objeto PSCredential.</span><span class="sxs-lookup"><span data-stu-id="e07e4-179">A variable that contains a PSCredential object.</span></span>
- <span data-ttu-id="e07e4-180">Um comando que obtém um objeto PSCredential, como `Get-Credential`</span><span class="sxs-lookup"><span data-stu-id="e07e4-180">A command that gets a PSCredential object, such as `Get-Credential`</span></span>

<span data-ttu-id="e07e4-181">Se essa opção não for definida, você não poderá especificar nenhuma credencial.</span><span class="sxs-lookup"><span data-stu-id="e07e4-181">If this option is not set, then you cannot specify any credentials.</span></span>

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

### <span data-ttu-id="e07e4-182">-ProxyType</span><span class="sxs-lookup"><span data-stu-id="e07e4-182">-ProxyType</span></span>

<span data-ttu-id="e07e4-183">Especifica o mecanismo de resolução de nomes de host a ser usado.</span><span class="sxs-lookup"><span data-stu-id="e07e4-183">Specifies the host name resolution mechanism to use.</span></span> <span data-ttu-id="e07e4-184">Os valores aceitáveis para esse parâmetro são: **None** , **WinHTTP** , **auto** ou **InternetExplorer** .</span><span class="sxs-lookup"><span data-stu-id="e07e4-184">The acceptable values for this parameter are: **None** , **WinHttp** , **Auto** , or **InternetExplorer** .</span></span>

<span data-ttu-id="e07e4-185">O valor padrão desse parâmetro é **InternetExplorer** .</span><span class="sxs-lookup"><span data-stu-id="e07e4-185">The default value of this parameter is **InternetExplorer** .</span></span>

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

### <span data-ttu-id="e07e4-186">-SkipCACheck</span><span class="sxs-lookup"><span data-stu-id="e07e4-186">-SkipCACheck</span></span>

<span data-ttu-id="e07e4-187">Indica que, ao se conectar via HTTPS, o cliente não valida se o certificado do servidor está assinado por uma autoridade de certificação (CA) confiável.</span><span class="sxs-lookup"><span data-stu-id="e07e4-187">Indicates that when connecting over HTTPS, the client does not validate that the server certificate is signed by a trusted certification authority (CA).</span></span>

<span data-ttu-id="e07e4-188">Use esse parâmetro somente quando o computador remoto for confiável usando outro mecanismo, como quando o computador remoto fizer parte de uma rede que esteja fisicamente segura e isolada, ou quando o computador remoto estiver listado como um host confiável em uma configuração do WinRM.</span><span class="sxs-lookup"><span data-stu-id="e07e4-188">Use this parameter only when the remote computer is trusted using another mechanism, such as when the remote computer is part of a network that is physically secure and isolated, or when the remote computer is listed as a trusted host in a WinRM configuration.</span></span>

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

### <span data-ttu-id="e07e4-189">-SkipCNCheck</span><span class="sxs-lookup"><span data-stu-id="e07e4-189">-SkipCNCheck</span></span>

<span data-ttu-id="e07e4-190">Indica que o nome comum do certificado (CN) do servidor não precisa corresponder ao hostname do servidor.</span><span class="sxs-lookup"><span data-stu-id="e07e4-190">Indicates that the certificate common name (CN) of the server does not need to match the hostname of the server.</span></span> <span data-ttu-id="e07e4-191">Use esse parâmetro para operações remotas somente com computadores confiáveis que usam o protocolo HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e07e4-191">Use this parameter for remote operations only with trusted computers that use the HTTPS protocol.</span></span>

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

### <span data-ttu-id="e07e4-192">-SkipRevocationCheck</span><span class="sxs-lookup"><span data-stu-id="e07e4-192">-SkipRevocationCheck</span></span>

<span data-ttu-id="e07e4-193">Indica que a verificação de revogação para certificados de servidor é ignorada.</span><span class="sxs-lookup"><span data-stu-id="e07e4-193">Indicates that the revocation check for server certificates is skipped.</span></span> <span data-ttu-id="e07e4-194">Use esse parâmetro somente para computadores confiáveis.</span><span class="sxs-lookup"><span data-stu-id="e07e4-194">Use this parameter only for trusted computers.</span></span>

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

### <span data-ttu-id="e07e4-195">-UICulture</span><span class="sxs-lookup"><span data-stu-id="e07e4-195">-UICulture</span></span>

<span data-ttu-id="e07e4-196">Especifica a cultura da interface do usuário a ser usada para a sessão CIM.</span><span class="sxs-lookup"><span data-stu-id="e07e4-196">Specifies the user interface culture to use for the CIM session.</span></span> <span data-ttu-id="e07e4-197">Especifique o valor para esse parâmetro usando um dos seguintes formatos:</span><span class="sxs-lookup"><span data-stu-id="e07e4-197">Specify the value for this parameter using one of the following formats:</span></span>

- <span data-ttu-id="e07e4-198">Um nome de cultura em `<languagecode2>-<country/regioncode2>` formato como "en-US".</span><span class="sxs-lookup"><span data-stu-id="e07e4-198">A culture name in `<languagecode2>-<country/regioncode2>` format such as "EN-US".</span></span>
- <span data-ttu-id="e07e4-199">Uma variável que contém um objeto CultureInfo.</span><span class="sxs-lookup"><span data-stu-id="e07e4-199">A variable that contains a CultureInfo object.</span></span>
- <span data-ttu-id="e07e4-200">Um comando que obtém um objeto CultureInfo, como `Get-Culture` .</span><span class="sxs-lookup"><span data-stu-id="e07e4-200">A command that gets a CultureInfo object, such as `Get-Culture`.</span></span>

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

### <span data-ttu-id="e07e4-201">-UseSsl</span><span class="sxs-lookup"><span data-stu-id="e07e4-201">-UseSsl</span></span>

<span data-ttu-id="e07e4-202">Indica que o SSL deve ser usado para estabelecer uma conexão com o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="e07e4-202">Indicates that SSL should be used to establish a connection to the remote computer.</span></span> <span data-ttu-id="e07e4-203">Por padrão, SSL não é usado.</span><span class="sxs-lookup"><span data-stu-id="e07e4-203">By default, SSL is not used.</span></span> <span data-ttu-id="e07e4-204">O WsMan criptografa todo o conteúdo transmitido pela rede, mesmo ao usar HTTP.</span><span class="sxs-lookup"><span data-stu-id="e07e4-204">WsMan encrypts all content that is transmitted over the network, even when using HTTP.</span></span>

<span data-ttu-id="e07e4-205">Esse parâmetro permite especificar a proteção adicional do HTTPS em vez de HTTP.</span><span class="sxs-lookup"><span data-stu-id="e07e4-205">This parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span> <span data-ttu-id="e07e4-206">Se o SSL não estiver disponível na porta usada para a conexão e você especificar esse parâmetro, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="e07e4-206">If SSL is not available on the port used for the connection and you specify this parameter, then the command fails.</span></span>

<span data-ttu-id="e07e4-207">É recomendável que você use esse parâmetro somente quando o parâmetro **PacketPrivacy** não for especificado.</span><span class="sxs-lookup"><span data-stu-id="e07e4-207">It is recommended that you use this parameter only when the **PacketPrivacy** parameter is not specified.</span></span>

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

### <span data-ttu-id="e07e4-208">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e07e4-208">CommonParameters</span></span>

<span data-ttu-id="e07e4-209">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e07e4-209">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e07e4-210">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e07e4-210">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e07e4-211">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="e07e4-211">INPUTS</span></span>

### <span data-ttu-id="e07e4-212">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e07e4-212">None</span></span>

<span data-ttu-id="e07e4-213">Esse cmdlet não aceita nenhum objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="e07e4-213">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="e07e4-214">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="e07e4-214">OUTPUTS</span></span>

### <span data-ttu-id="e07e4-215">CIMSessionOption</span><span class="sxs-lookup"><span data-stu-id="e07e4-215">CIMSessionOption</span></span>

<span data-ttu-id="e07e4-216">Esse cmdlet retorna um objeto que contém informações de opções de sessão CIM.</span><span class="sxs-lookup"><span data-stu-id="e07e4-216">This cmdlet returns an object that contains CIM session options information.</span></span>

## <span data-ttu-id="e07e4-217">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="e07e4-217">NOTES</span></span>

## <span data-ttu-id="e07e4-218">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="e07e4-218">RELATED LINKS</span></span>

[<span data-ttu-id="e07e4-219">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="e07e4-219">Get-ChildItem</span></span>](../microsoft.powershell.management/get-childitem.md)

[<span data-ttu-id="e07e4-220">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="e07e4-220">Get-Credential</span></span>](../microsoft.powershell.security/get-credential.md)

[<span data-ttu-id="e07e4-221">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="e07e4-221">Get-Culture</span></span>](../microsoft.powershell.utility/get-culture.md)

[<span data-ttu-id="e07e4-222">Get-Item</span><span class="sxs-lookup"><span data-stu-id="e07e4-222">Get-Item</span></span>](../microsoft.powershell.management/get-item.md)

[<span data-ttu-id="e07e4-223">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="e07e4-223">New-CimSession</span></span>](New-CimSession.md)
