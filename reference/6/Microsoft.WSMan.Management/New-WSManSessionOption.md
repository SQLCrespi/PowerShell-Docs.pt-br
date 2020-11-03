---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/new-wsmansessionoption?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WSManSessionOption
ms.openlocfilehash: 8996c550147ab7e0857d97b0a47baf92fac514d8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193447"
---
# <span data-ttu-id="96801-103">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="96801-103">New-WSManSessionOption</span></span>

## <span data-ttu-id="96801-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="96801-104">SYNOPSIS</span></span>
<span data-ttu-id="96801-105">Cria a tabela de hash de opção de sessão para usar como parâmetros de entrada para WS-Management cmdlets.</span><span class="sxs-lookup"><span data-stu-id="96801-105">Creates session option hash table to use as input parameters for WS-Management cmdlets.</span></span>

## <span data-ttu-id="96801-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="96801-106">SYNTAX</span></span>

```
New-WSManSessionOption [-ProxyAccessType <ProxyAccessType>] [-ProxyAuthentication <ProxyAuthentication>]
 [-ProxyCredential <PSCredential>] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck] [-SPNPort <Int32>]
 [-OperationTimeout <Int32>] [-NoEncryption] [-UseUTF16] [<CommonParameters>]
```

## <span data-ttu-id="96801-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="96801-107">DESCRIPTION</span></span>
<span data-ttu-id="96801-108">O cmdlet **New-WSManSessionOption** cria uma tabela de hash de opção de sessão WSMan que pode ser passada para cmdlets WSMan:</span><span class="sxs-lookup"><span data-stu-id="96801-108">The **New-WSManSessionOption** cmdlet creates a WSMan Session option hash table which can be passed to WSMan cmdlets:</span></span>

- <span data-ttu-id="96801-109">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="96801-109">Get-WSManInstance</span></span>
- <span data-ttu-id="96801-110">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="96801-110">Set-WSManInstance</span></span>
- <span data-ttu-id="96801-111">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="96801-111">Invoke-WSManAction</span></span>
- <span data-ttu-id="96801-112">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="96801-112">Connect-WSMan</span></span>

## <span data-ttu-id="96801-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="96801-113">EXAMPLES</span></span>

### <span data-ttu-id="96801-114">Exemplo 1: criar uma conexão que usa opções de conexão</span><span class="sxs-lookup"><span data-stu-id="96801-114">Example 1: Create a connection that uses connection options</span></span>

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

<span data-ttu-id="96801-115">Este exemplo cria uma conexão com o computador Server01 remoto usando as opções de conexão definidas por **New-WSManSessionOption** .</span><span class="sxs-lookup"><span data-stu-id="96801-115">This example creates a connection to the remote server01 computer by using the connection options that are defined by **New-WSManSessionOption** .</span></span>

<span data-ttu-id="96801-116">O primeiro comando usa **New-WSManSessionOption** para armazenar um conjunto de opções de configuração de conexão na variável $a.</span><span class="sxs-lookup"><span data-stu-id="96801-116">The first command uses **New-WSManSessionOption** to store a set of connection setting options in the $a variable.</span></span>
<span data-ttu-id="96801-117">Nesse caso, as opções da sessão definem um tempo de conexão de 30 segundos (30.000 milissegundos).</span><span class="sxs-lookup"><span data-stu-id="96801-117">In this case, the session options set a connection time out of 30 seconds (30,000 milliseconds).</span></span>

<span data-ttu-id="96801-118">O segundo comando usa o parâmetro *SessionOption* para passar as credenciais que são armazenadas na variável $A para **Connect-WSMan** .</span><span class="sxs-lookup"><span data-stu-id="96801-118">The second command uses the *SessionOption* parameter to pass the credentials that are stored in the $a variable to **Connect-WSMan** .</span></span>
<span data-ttu-id="96801-119">Em seguida, **Connect-WSMan** se conecta ao computador remoto Server01 usando as opções de sessão especificadas.</span><span class="sxs-lookup"><span data-stu-id="96801-119">Then, **Connect-WSMan** connects to the remote server01 computer by using the specified session options.</span></span>

<span data-ttu-id="96801-120">O **Connect-WSMan** geralmente é usado no contexto do provedor WSMan para se conectar a um computador remoto, neste caso, o computador Server01.</span><span class="sxs-lookup"><span data-stu-id="96801-120">**Connect-WSMan** is generally used in the context of the WSMan provider to connect to a remote computer, in this case the server01 computer.</span></span>
<span data-ttu-id="96801-121">No entanto, você pode usar o cmdlet para estabelecer conexões com computadores remotos, antes de alterar para o provedor WSMan.</span><span class="sxs-lookup"><span data-stu-id="96801-121">However, you can use the cmdlet to establish connections to remote computers before you change to the WSMan provider.</span></span>
<span data-ttu-id="96801-122">Essas conexões aparecem na lista **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="96801-122">Those connections appear in the **ComputerName** list.</span></span>

## <span data-ttu-id="96801-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="96801-123">PARAMETERS</span></span>

### <span data-ttu-id="96801-124">-NoEncryption</span><span class="sxs-lookup"><span data-stu-id="96801-124">-NoEncryption</span></span>
<span data-ttu-id="96801-125">Indica que a conexão não usa criptografia para operações remotas via HTTP.</span><span class="sxs-lookup"><span data-stu-id="96801-125">Indicates that the connection does not use encryption for remote operations over HTTP.</span></span>

<span data-ttu-id="96801-126">Por padrão, o tráfego não criptografado não está habilitado.</span><span class="sxs-lookup"><span data-stu-id="96801-126">By default, unencrypted traffic is not enabled.</span></span>
<span data-ttu-id="96801-127">Ele deve ser habilitado na configuração local.</span><span class="sxs-lookup"><span data-stu-id="96801-127">It must be enabled in the local configuration.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="96801-128">-OperationTimeout</span><span class="sxs-lookup"><span data-stu-id="96801-128">-OperationTimeout</span></span>
<span data-ttu-id="96801-129">Especifica o tempo limite, em milissegundos, para a operação de WS-Management.</span><span class="sxs-lookup"><span data-stu-id="96801-129">Specifies the time-out, in milliseconds, for the WS-Management operation.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: OperationTimeoutMSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="96801-130">-ProxyAccessType</span><span class="sxs-lookup"><span data-stu-id="96801-130">-ProxyAccessType</span></span>
<span data-ttu-id="96801-131">Especifica o mecanismo pelo qual o servidor proxy é localizado.</span><span class="sxs-lookup"><span data-stu-id="96801-131">Specifies the mechanism by which the proxy server is located.</span></span>
<span data-ttu-id="96801-132">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="96801-132">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="96801-133">ProxyIEConfig.</span><span class="sxs-lookup"><span data-stu-id="96801-133">ProxyIEConfig.</span></span>
<span data-ttu-id="96801-134">Use a configuração de proxy do Internet Explorer para o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="96801-134">Use the Internet Explorer proxy configuration for the current user.</span></span>
- <span data-ttu-id="96801-135">ProxyWinHttpConfig.</span><span class="sxs-lookup"><span data-stu-id="96801-135">ProxyWinHttpConfig.</span></span>
<span data-ttu-id="96801-136">O cliente WSMan usa as configurações de proxy configuradas para WinHTTP, usando o utilitário ProxyCfg.exe.</span><span class="sxs-lookup"><span data-stu-id="96801-136">The WSMan client uses the proxy settings configured for WinHTTP, using the ProxyCfg.exe utility.</span></span>
- <span data-ttu-id="96801-137">ProxyAutoDetect.</span><span class="sxs-lookup"><span data-stu-id="96801-137">ProxyAutoDetect.</span></span>
<span data-ttu-id="96801-138">Forçar detecção automática de um servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="96801-138">Force auto-detection of a proxy server.</span></span>
- <span data-ttu-id="96801-139">ProxyNoProxyServer.</span><span class="sxs-lookup"><span data-stu-id="96801-139">ProxyNoProxyServer.</span></span>
<span data-ttu-id="96801-140">Não use um servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="96801-140">Do not use a proxy server.</span></span>
<span data-ttu-id="96801-141">Resolva todos os nomes de host localmente.</span><span class="sxs-lookup"><span data-stu-id="96801-141">Resolve all host names locally.</span></span>

<span data-ttu-id="96801-142">O valor padrão é ProxyIEConfig.</span><span class="sxs-lookup"><span data-stu-id="96801-142">The default value is ProxyIEConfig.</span></span>

```yaml
Type: Microsoft.WSMan.Management.ProxyAccessType
Parameter Sets: (All)
Aliases:
Accepted values: ProxyIEConfig, ProxyWinHttpConfig, ProxyAutoDetect, ProxyNoProxyServer

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="96801-143">-ProxyAuthentication</span><span class="sxs-lookup"><span data-stu-id="96801-143">-ProxyAuthentication</span></span>
<span data-ttu-id="96801-144">Especifica o método de autenticação a ser usado no proxy.</span><span class="sxs-lookup"><span data-stu-id="96801-144">Specifies the authentication method to use at the proxy.</span></span>
<span data-ttu-id="96801-145">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="96801-145">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="96801-146">Básica.</span><span class="sxs-lookup"><span data-stu-id="96801-146">Basic.</span></span>
<span data-ttu-id="96801-147">É um esquema no qual o nome de usuário e senha são enviados em texto não criptografado para o servidor ou proxy.</span><span class="sxs-lookup"><span data-stu-id="96801-147">Basic is a scheme in which the user name and password are sent in clear-text to the server or proxy.</span></span>
- <span data-ttu-id="96801-148">Digest.</span><span class="sxs-lookup"><span data-stu-id="96801-148">Digest.</span></span>
<span data-ttu-id="96801-149">É um esquema de desafio/resposta que utiliza uma cadeia de caracteres de dados do servidor especificada para o desafio.</span><span class="sxs-lookup"><span data-stu-id="96801-149">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="96801-150">Negotiate.</span><span class="sxs-lookup"><span data-stu-id="96801-150">Negotiate.</span></span>
<span data-ttu-id="96801-151">É um esquema de desafio/resposta que negocia com o servidor ou proxy para determinar o esquema a ser utilizado para autenticação.</span><span class="sxs-lookup"><span data-stu-id="96801-151">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine which scheme to use for authentication.</span></span>
<span data-ttu-id="96801-152">Os exemplos são o protocolo Kerberos e NTLM.</span><span class="sxs-lookup"><span data-stu-id="96801-152">Examples are the Kerberos protocol and NTLM.</span></span>

<span data-ttu-id="96801-153">O valor padrão é Negotiate.</span><span class="sxs-lookup"><span data-stu-id="96801-153">The default value is Negotiate.</span></span>

```yaml
Type: Microsoft.WSMan.Management.ProxyAuthentication
Parameter Sets: (All)
Aliases:
Accepted values: Negotiate, Basic, Digest

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="96801-154">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="96801-154">-ProxyCredential</span></span>
<span data-ttu-id="96801-155">Especifica uma conta de usuário que tem permissão para obter acesso por meio de um proxy da Web intermediário.</span><span class="sxs-lookup"><span data-stu-id="96801-155">Specifies a user account that has permission to gain access through an intermediate Web proxy.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="96801-156">-SkipCACheck</span><span class="sxs-lookup"><span data-stu-id="96801-156">-SkipCACheck</span></span>
<span data-ttu-id="96801-157">Especifica que, quando se conecta via HTTPS, o cliente não valida se o certificado do servidor está assinado por uma autoridade de certificação (CA) confiável.</span><span class="sxs-lookup"><span data-stu-id="96801-157">Specifies that, when it connects over HTTPS, the client does not validate that the server certificate is signed by a trusted certification authority (CA).</span></span>
<span data-ttu-id="96801-158">Use esta opção somente quando o computador remoto for confiável por outro método, por exemplo, se o computador remoto fizer parte de uma rede que esteja fisicamente segura e isolada ou o computador remoto estiver listado como um host confiável na configuração do WS-Management.</span><span class="sxs-lookup"><span data-stu-id="96801-158">Use this option only when the remote computer is trusted by another method, for example, if the remote computer is part of a network that is physically secure and isolated or the remote computer is listed as a trusted host in the WS-Management configuration.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="96801-159">-SkipCNCheck</span><span class="sxs-lookup"><span data-stu-id="96801-159">-SkipCNCheck</span></span>
<span data-ttu-id="96801-160">Especifica que o nome comum do certificado (CN) do servidor não precisa corresponder ao nome do host do servidor.</span><span class="sxs-lookup"><span data-stu-id="96801-160">Specifies that the certificate common name (CN) of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="96801-161">É usado somente em operações remotas usando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="96801-161">This is used only in remote operations using HTTPS.</span></span>
<span data-ttu-id="96801-162">Essa opção deve ser usada somente para computadores confiáveis.</span><span class="sxs-lookup"><span data-stu-id="96801-162">This option should only be used for trusted computers.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="96801-163">-SkipRevocationCheck</span><span class="sxs-lookup"><span data-stu-id="96801-163">-SkipRevocationCheck</span></span>
<span data-ttu-id="96801-164">Indica que a conexão não valida o status de revogação no certificado do servidor.</span><span class="sxs-lookup"><span data-stu-id="96801-164">Indicates that the connection does not validate the revocation status on the server certificate.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="96801-165">-SPNPort</span><span class="sxs-lookup"><span data-stu-id="96801-165">-SPNPort</span></span>
<span data-ttu-id="96801-166">Especifica um número de porta para acrescentar ao SPN (nome da entidade de serviço) de conexão do servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="96801-166">Specifies a port number to append to the connection Service Principal Name (SPN) of the remote server.</span></span>
<span data-ttu-id="96801-167">Um SPN é usado quando o mecanismo de autenticação é Kerberos ou Negotiate.</span><span class="sxs-lookup"><span data-stu-id="96801-167">An SPN is used when the authentication mechanism is Kerberos or Negotiate.</span></span>

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

### <span data-ttu-id="96801-168">-UseUTF16</span><span class="sxs-lookup"><span data-stu-id="96801-168">-UseUTF16</span></span>
<span data-ttu-id="96801-169">Indica que a conexão codifica a solicitação no formato UTF16 em vez do formato UTF8.</span><span class="sxs-lookup"><span data-stu-id="96801-169">Indicates that the connection encodes the request in UTF16 format instead of UTF8 format.</span></span>
<span data-ttu-id="96801-170">O padrão é a codificação UTF8.</span><span class="sxs-lookup"><span data-stu-id="96801-170">The default is UTF8 encoding.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="96801-171">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="96801-171">CommonParameters</span></span>
<span data-ttu-id="96801-172">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="96801-172">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="96801-173">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="96801-173">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="96801-174">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="96801-174">INPUTS</span></span>

## <span data-ttu-id="96801-175">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="96801-175">OUTPUTS</span></span>

### <span data-ttu-id="96801-176">SessionOption</span><span class="sxs-lookup"><span data-stu-id="96801-176">SessionOption</span></span>

## <span data-ttu-id="96801-177">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="96801-177">NOTES</span></span>

## <span data-ttu-id="96801-178">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="96801-178">RELATED LINKS</span></span>

[<span data-ttu-id="96801-179">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="96801-179">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="96801-180">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="96801-180">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="96801-181">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="96801-181">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="96801-182">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="96801-182">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="96801-183">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="96801-183">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="96801-184">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="96801-184">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="96801-185">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="96801-185">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="96801-186">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="96801-186">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="96801-187">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="96801-187">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="96801-188">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="96801-188">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="96801-189">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="96801-189">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="96801-190">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="96801-190">Test-WSMan</span></span>](Test-WSMan.md)
