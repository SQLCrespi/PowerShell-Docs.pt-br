---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/new-wsmansessionoption?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WSManSessionOption
ms.openlocfilehash: e7d7f132eb82dc1a709a88cbdef525aa83d867e4
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595357"
---
# <span data-ttu-id="ec336-102">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="ec336-102">New-WSManSessionOption</span></span>

## <span data-ttu-id="ec336-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="ec336-103">SYNOPSIS</span></span>
<span data-ttu-id="ec336-104">Cria a tabela de hash de opção de sessão para usar como parâmetros de entrada para WS-Management cmdlets.</span><span class="sxs-lookup"><span data-stu-id="ec336-104">Creates session option hash table to use as input parameters for WS-Management cmdlets.</span></span>

## <span data-ttu-id="ec336-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ec336-105">SYNTAX</span></span>

```
New-WSManSessionOption [-ProxyAccessType <ProxyAccessType>] [-ProxyAuthentication <ProxyAuthentication>]
 [-ProxyCredential <PSCredential>] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck] [-SPNPort <Int32>]
 [-OperationTimeout <Int32>] [-NoEncryption] [-UseUTF16] [<CommonParameters>]
```

## <span data-ttu-id="ec336-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ec336-106">DESCRIPTION</span></span>
<span data-ttu-id="ec336-107">O cmdlet **New-WSManSessionOption** cria uma tabela de hash de opção de sessão WSMan que pode ser passada para cmdlets WSMan:</span><span class="sxs-lookup"><span data-stu-id="ec336-107">The **New-WSManSessionOption** cmdlet creates a WSMan Session option hash table which can be passed to WSMan cmdlets:</span></span>

- <span data-ttu-id="ec336-108">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="ec336-108">Get-WSManInstance</span></span>
- <span data-ttu-id="ec336-109">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="ec336-109">Set-WSManInstance</span></span>
- <span data-ttu-id="ec336-110">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="ec336-110">Invoke-WSManAction</span></span>
- <span data-ttu-id="ec336-111">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="ec336-111">Connect-WSMan</span></span>

## <span data-ttu-id="ec336-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="ec336-112">EXAMPLES</span></span>

### <span data-ttu-id="ec336-113">Exemplo 1: criar uma conexão que usa opções de conexão</span><span class="sxs-lookup"><span data-stu-id="ec336-113">Example 1: Create a connection that uses connection options</span></span>

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

<span data-ttu-id="ec336-114">Este exemplo cria uma conexão com o computador Server01 remoto usando as opções de conexão definidas por **New-WSManSessionOption**.</span><span class="sxs-lookup"><span data-stu-id="ec336-114">This example creates a connection to the remote server01 computer by using the connection options that are defined by **New-WSManSessionOption**.</span></span>

<span data-ttu-id="ec336-115">O primeiro comando usa **New-WSManSessionOption** para armazenar um conjunto de opções de configuração de conexão na variável $a.</span><span class="sxs-lookup"><span data-stu-id="ec336-115">The first command uses **New-WSManSessionOption** to store a set of connection setting options in the $a variable.</span></span>
<span data-ttu-id="ec336-116">Nesse caso, as opções da sessão definem um tempo de conexão de 30 segundos (30.000 milissegundos).</span><span class="sxs-lookup"><span data-stu-id="ec336-116">In this case, the session options set a connection time out of 30 seconds (30,000 milliseconds).</span></span>

<span data-ttu-id="ec336-117">O segundo comando usa o parâmetro *SessionOption* para passar as credenciais que são armazenadas na variável $A para **Connect-WSMan**.</span><span class="sxs-lookup"><span data-stu-id="ec336-117">The second command uses the *SessionOption* parameter to pass the credentials that are stored in the $a variable to **Connect-WSMan**.</span></span>
<span data-ttu-id="ec336-118">Em seguida, **Connect-WSMan** se conecta ao computador remoto Server01 usando as opções de sessão especificadas.</span><span class="sxs-lookup"><span data-stu-id="ec336-118">Then, **Connect-WSMan** connects to the remote server01 computer by using the specified session options.</span></span>

<span data-ttu-id="ec336-119">O **Connect-WSMan** geralmente é usado no contexto do provedor WSMan para se conectar a um computador remoto, neste caso, o computador Server01.</span><span class="sxs-lookup"><span data-stu-id="ec336-119">**Connect-WSMan** is generally used in the context of the WSMan provider to connect to a remote computer, in this case the server01 computer.</span></span>
<span data-ttu-id="ec336-120">No entanto, você pode usar o cmdlet para estabelecer conexões com computadores remotos, antes de alterar para o provedor WSMan.</span><span class="sxs-lookup"><span data-stu-id="ec336-120">However, you can use the cmdlet to establish connections to remote computers before you change to the WSMan provider.</span></span>
<span data-ttu-id="ec336-121">Essas conexões aparecem na lista **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="ec336-121">Those connections appear in the **ComputerName** list.</span></span>

## <span data-ttu-id="ec336-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ec336-122">PARAMETERS</span></span>

### <span data-ttu-id="ec336-123">-NoEncryption</span><span class="sxs-lookup"><span data-stu-id="ec336-123">-NoEncryption</span></span>
<span data-ttu-id="ec336-124">Indica que a conexão não usa criptografia para operações remotas via HTTP.</span><span class="sxs-lookup"><span data-stu-id="ec336-124">Indicates that the connection does not use encryption for remote operations over HTTP.</span></span>

<span data-ttu-id="ec336-125">Por padrão, o tráfego não criptografado não está habilitado.</span><span class="sxs-lookup"><span data-stu-id="ec336-125">By default, unencrypted traffic is not enabled.</span></span>
<span data-ttu-id="ec336-126">Ele deve ser habilitado na configuração local.</span><span class="sxs-lookup"><span data-stu-id="ec336-126">It must be enabled in the local configuration.</span></span>

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

### <span data-ttu-id="ec336-127">-OperationTimeout</span><span class="sxs-lookup"><span data-stu-id="ec336-127">-OperationTimeout</span></span>
<span data-ttu-id="ec336-128">Especifica o tempo limite, em milissegundos, para a operação de WS-Management.</span><span class="sxs-lookup"><span data-stu-id="ec336-128">Specifies the time-out, in milliseconds, for the WS-Management operation.</span></span>

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

### <span data-ttu-id="ec336-129">-ProxyAccessType</span><span class="sxs-lookup"><span data-stu-id="ec336-129">-ProxyAccessType</span></span>
<span data-ttu-id="ec336-130">Especifica o mecanismo pelo qual o servidor proxy é localizado.</span><span class="sxs-lookup"><span data-stu-id="ec336-130">Specifies the mechanism by which the proxy server is located.</span></span>
<span data-ttu-id="ec336-131">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="ec336-131">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="ec336-132">ProxyIEConfig.</span><span class="sxs-lookup"><span data-stu-id="ec336-132">ProxyIEConfig.</span></span>
<span data-ttu-id="ec336-133">Use a configuração de proxy do Internet Explorer para o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="ec336-133">Use the Internet Explorer proxy configuration for the current user.</span></span>
- <span data-ttu-id="ec336-134">ProxyWinHttpConfig.</span><span class="sxs-lookup"><span data-stu-id="ec336-134">ProxyWinHttpConfig.</span></span>
<span data-ttu-id="ec336-135">O cliente WSMan usa as configurações de proxy configuradas para WinHTTP, usando o utilitário ProxyCfg.exe.</span><span class="sxs-lookup"><span data-stu-id="ec336-135">The WSMan client uses the proxy settings configured for WinHTTP, using the ProxyCfg.exe utility.</span></span>
- <span data-ttu-id="ec336-136">ProxyAutoDetect.</span><span class="sxs-lookup"><span data-stu-id="ec336-136">ProxyAutoDetect.</span></span>
<span data-ttu-id="ec336-137">Forçar detecção automática de um servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="ec336-137">Force auto-detection of a proxy server.</span></span>
- <span data-ttu-id="ec336-138">ProxyNoProxyServer.</span><span class="sxs-lookup"><span data-stu-id="ec336-138">ProxyNoProxyServer.</span></span>
<span data-ttu-id="ec336-139">Não use um servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="ec336-139">Do not use a proxy server.</span></span>
<span data-ttu-id="ec336-140">Resolva todos os nomes de host localmente.</span><span class="sxs-lookup"><span data-stu-id="ec336-140">Resolve all host names locally.</span></span>

<span data-ttu-id="ec336-141">O valor padrão é ProxyIEConfig.</span><span class="sxs-lookup"><span data-stu-id="ec336-141">The default value is ProxyIEConfig.</span></span>

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

### <span data-ttu-id="ec336-142">-ProxyAuthentication</span><span class="sxs-lookup"><span data-stu-id="ec336-142">-ProxyAuthentication</span></span>
<span data-ttu-id="ec336-143">Especifica o método de autenticação a ser usado no proxy.</span><span class="sxs-lookup"><span data-stu-id="ec336-143">Specifies the authentication method to use at the proxy.</span></span>
<span data-ttu-id="ec336-144">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="ec336-144">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="ec336-145">Básica.</span><span class="sxs-lookup"><span data-stu-id="ec336-145">Basic.</span></span>
<span data-ttu-id="ec336-146">É um esquema no qual o nome de usuário e senha são enviados em texto não criptografado para o servidor ou proxy.</span><span class="sxs-lookup"><span data-stu-id="ec336-146">Basic is a scheme in which the user name and password are sent in clear-text to the server or proxy.</span></span>
- <span data-ttu-id="ec336-147">Digest.</span><span class="sxs-lookup"><span data-stu-id="ec336-147">Digest.</span></span>
<span data-ttu-id="ec336-148">É um esquema de desafio/resposta que utiliza uma cadeia de caracteres de dados do servidor especificada para o desafio.</span><span class="sxs-lookup"><span data-stu-id="ec336-148">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="ec336-149">Negotiate.</span><span class="sxs-lookup"><span data-stu-id="ec336-149">Negotiate.</span></span>
<span data-ttu-id="ec336-150">É um esquema de desafio/resposta que negocia com o servidor ou proxy para determinar o esquema a ser utilizado para autenticação.</span><span class="sxs-lookup"><span data-stu-id="ec336-150">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine which scheme to use for authentication.</span></span>
<span data-ttu-id="ec336-151">Os exemplos são o protocolo Kerberos e NTLM.</span><span class="sxs-lookup"><span data-stu-id="ec336-151">Examples are the Kerberos protocol and NTLM.</span></span>

<span data-ttu-id="ec336-152">O valor padrão é Negotiate.</span><span class="sxs-lookup"><span data-stu-id="ec336-152">The default value is Negotiate.</span></span>

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

### <span data-ttu-id="ec336-153">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="ec336-153">-ProxyCredential</span></span>
<span data-ttu-id="ec336-154">Especifica uma conta de usuário que tem permissão para obter acesso por meio de um proxy da Web intermediário.</span><span class="sxs-lookup"><span data-stu-id="ec336-154">Specifies a user account that has permission to gain access through an intermediate Web proxy.</span></span>

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

### <span data-ttu-id="ec336-155">-SkipCACheck</span><span class="sxs-lookup"><span data-stu-id="ec336-155">-SkipCACheck</span></span>
<span data-ttu-id="ec336-156">Especifica que, quando se conecta via HTTPS, o cliente não valida se o certificado do servidor está assinado por uma autoridade de certificação (CA) confiável.</span><span class="sxs-lookup"><span data-stu-id="ec336-156">Specifies that, when it connects over HTTPS, the client does not validate that the server certificate is signed by a trusted certification authority (CA).</span></span>
<span data-ttu-id="ec336-157">Use esta opção somente quando o computador remoto for confiável por outro método, por exemplo, se o computador remoto fizer parte de uma rede que esteja fisicamente segura e isolada ou o computador remoto estiver listado como um host confiável na configuração do WS-Management.</span><span class="sxs-lookup"><span data-stu-id="ec336-157">Use this option only when the remote computer is trusted by another method, for example, if the remote computer is part of a network that is physically secure and isolated or the remote computer is listed as a trusted host in the WS-Management configuration.</span></span>

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

### <span data-ttu-id="ec336-158">-SkipCNCheck</span><span class="sxs-lookup"><span data-stu-id="ec336-158">-SkipCNCheck</span></span>
<span data-ttu-id="ec336-159">Especifica que o nome comum do certificado (CN) do servidor não precisa corresponder ao nome do host do servidor.</span><span class="sxs-lookup"><span data-stu-id="ec336-159">Specifies that the certificate common name (CN) of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="ec336-160">É usado somente em operações remotas usando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ec336-160">This is used only in remote operations using HTTPS.</span></span>
<span data-ttu-id="ec336-161">Essa opção deve ser usada somente para computadores confiáveis.</span><span class="sxs-lookup"><span data-stu-id="ec336-161">This option should only be used for trusted computers.</span></span>

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

### <span data-ttu-id="ec336-162">-SkipRevocationCheck</span><span class="sxs-lookup"><span data-stu-id="ec336-162">-SkipRevocationCheck</span></span>
<span data-ttu-id="ec336-163">Indica que a conexão não valida o status de revogação no certificado do servidor.</span><span class="sxs-lookup"><span data-stu-id="ec336-163">Indicates that the connection does not validate the revocation status on the server certificate.</span></span>

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

### <span data-ttu-id="ec336-164">-SPNPort</span><span class="sxs-lookup"><span data-stu-id="ec336-164">-SPNPort</span></span>
<span data-ttu-id="ec336-165">Especifica um número de porta para acrescentar ao SPN (nome da entidade de serviço) de conexão do servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="ec336-165">Specifies a port number to append to the connection Service Principal Name (SPN) of the remote server.</span></span>
<span data-ttu-id="ec336-166">Um SPN é usado quando o mecanismo de autenticação é Kerberos ou Negotiate.</span><span class="sxs-lookup"><span data-stu-id="ec336-166">An SPN is used when the authentication mechanism is Kerberos or Negotiate.</span></span>

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

### <span data-ttu-id="ec336-167">-UseUTF16</span><span class="sxs-lookup"><span data-stu-id="ec336-167">-UseUTF16</span></span>
<span data-ttu-id="ec336-168">Indica que a conexão codifica a solicitação no formato UTF16 em vez do formato UTF8.</span><span class="sxs-lookup"><span data-stu-id="ec336-168">Indicates that the connection encodes the request in UTF16 format instead of UTF8 format.</span></span>
<span data-ttu-id="ec336-169">O padrão é a codificação UTF8.</span><span class="sxs-lookup"><span data-stu-id="ec336-169">The default is UTF8 encoding.</span></span>

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

### <span data-ttu-id="ec336-170">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ec336-170">CommonParameters</span></span>
<span data-ttu-id="ec336-171">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ec336-171">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ec336-172">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ec336-172">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ec336-173">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="ec336-173">INPUTS</span></span>

## <span data-ttu-id="ec336-174">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="ec336-174">OUTPUTS</span></span>

### <span data-ttu-id="ec336-175">SessionOption</span><span class="sxs-lookup"><span data-stu-id="ec336-175">SessionOption</span></span>

## <span data-ttu-id="ec336-176">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="ec336-176">NOTES</span></span>

## <span data-ttu-id="ec336-177">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="ec336-177">RELATED LINKS</span></span>

[<span data-ttu-id="ec336-178">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="ec336-178">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="ec336-179">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="ec336-179">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="ec336-180">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="ec336-180">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="ec336-181">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="ec336-181">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="ec336-182">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="ec336-182">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="ec336-183">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="ec336-183">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="ec336-184">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="ec336-184">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="ec336-185">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="ec336-185">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="ec336-186">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="ec336-186">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="ec336-187">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="ec336-187">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="ec336-188">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="ec336-188">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="ec336-189">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="ec336-189">Test-WSMan</span></span>](Test-WSMan.md)

