---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 08/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/enable-wsmancredssp?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WSManCredSSP
ms.openlocfilehash: 0b4ec4902df2b2e93def549586e3f6cde70fadee
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "93194930"
---
# <span data-ttu-id="53160-103">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="53160-103">Enable-WSManCredSSP</span></span>

## <span data-ttu-id="53160-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="53160-104">SYNOPSIS</span></span>
<span data-ttu-id="53160-105">Habilita a autenticação CredSSP (provedor de suporte à segurança de credencial) em um computador.</span><span class="sxs-lookup"><span data-stu-id="53160-105">Enables Credential Security Support Provider (CredSSP) authentication on a computer.</span></span>

## <span data-ttu-id="53160-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="53160-106">SYNTAX</span></span>

### <span data-ttu-id="53160-107">Tudo</span><span class="sxs-lookup"><span data-stu-id="53160-107">All</span></span>

```
Enable-WSManCredSSP [-Role] <String> [[-DelegateComputer] <String[]>] [-Force] [<CommonParameters>]
```

## <span data-ttu-id="53160-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="53160-108">DESCRIPTION</span></span>

<span data-ttu-id="53160-109">O `Enable-WSManCredSSP` cmdlet habilita a autenticação CredSSP em um cliente ou em um computador servidor.</span><span class="sxs-lookup"><span data-stu-id="53160-109">The `Enable-WSManCredSSP` cmdlet enables CredSSP authentication on a client or on a server computer.</span></span>
<span data-ttu-id="53160-110">Quando a autenticação CredSSP é usada, as credenciais do usuário são passadas para um computador remoto a ser autenticado.</span><span class="sxs-lookup"><span data-stu-id="53160-110">When CredSSP authentication is used, the user credentials are passed to a remote computer to be authenticated.</span></span> <span data-ttu-id="53160-111">Esse tipo de autenticação destina-se a comandos que criam uma sessão remota de outra sessão remota.</span><span class="sxs-lookup"><span data-stu-id="53160-111">This type of authentication is designed for commands that create a remote session from another remote session.</span></span> <span data-ttu-id="53160-112">Por exemplo, se você quiser executar um trabalho em segundo plano em um computador remoto, use esse tipo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="53160-112">For example, if you want to run a background job on a remote computer, use this kind of authentication.</span></span>

<span data-ttu-id="53160-113">`Enable-WSManCredSSP` pode habilitar CredSSP em um **cliente** ou um **servidor** .</span><span class="sxs-lookup"><span data-stu-id="53160-113">`Enable-WSManCredSSP` can enable CredSSP on a **Client** or a **Server** .</span></span> <span data-ttu-id="53160-114">Para habilitar o CredSSP em um cliente, especifique o **cliente** no parâmetro de **função** .</span><span class="sxs-lookup"><span data-stu-id="53160-114">To enable CredSSP on a client, specify **Client** in the **Role** parameter.</span></span> <span data-ttu-id="53160-115">Os clientes delegam credenciais explícitas a um servidor quando a autenticação do servidor é obtida.</span><span class="sxs-lookup"><span data-stu-id="53160-115">Clients delegate explicit credentials to a server when server authentication is achieved.</span></span> <span data-ttu-id="53160-116">Para habilitar o CredSSP em um servidor, especifique **servidor** no parâmetro **função** .</span><span class="sxs-lookup"><span data-stu-id="53160-116">To enable CredSSP on a server, specify **Server** in the **Role** parameter.</span></span> <span data-ttu-id="53160-117">Um servidor atua como um delegado para clientes.</span><span class="sxs-lookup"><span data-stu-id="53160-117">A server acts as a delegate for clients.</span></span> <span data-ttu-id="53160-118">Para obter mais detalhes, consulte **role** na seção Parameters.</span><span class="sxs-lookup"><span data-stu-id="53160-118">For more details, see **Role** in the Parameters section.</span></span>

> [!CAUTION]
> <span data-ttu-id="53160-119">A autenticação CredSSP Delega as credenciais do usuário do computador local para um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="53160-119">CredSSP authentication delegates the user credentials from the local computer to a remote computer.</span></span> <span data-ttu-id="53160-120">Essa prática aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="53160-120">This practice increases the security risk of the remote operation.</span></span> <span data-ttu-id="53160-121">Se o computador remoto estiver comprometido, no momento em que as credenciais forem passadas a ele essas credenciais poderão ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="53160-121">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

## <span data-ttu-id="53160-122">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="53160-122">EXAMPLES</span></span>

### <span data-ttu-id="53160-123">Exemplo 1: delegar credenciais de cliente</span><span class="sxs-lookup"><span data-stu-id="53160-123">Example 1: Delegate client credentials</span></span>

<span data-ttu-id="53160-124">Este exemplo permite que as credenciais do cliente sejam delegadas a um computador usando o nome de domínio totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="53160-124">This example allows the client credentials to be delegated to a computer by using the fully qualified domain name.</span></span>

```powershell
Enable-WSManCredSSP -Role "Client" -DelegateComputer "Server02.fabrikam.com"
```

```Output
cfg         : http://schemas.microsoft.com/wbem/wsman/1/config/client/auth
lang        : en-US
Basic       : true
Digest      : true
Kerberos    : true
Negotiate   : true
Certificate : true
CredSSP     : true
```

### <span data-ttu-id="53160-125">Exemplo 2: delegar credenciais de cliente a todos os computadores em um domínio</span><span class="sxs-lookup"><span data-stu-id="53160-125">Example 2: Delegate client credentials to all computers in a domain</span></span>

<span data-ttu-id="53160-126">Este exemplo permite que as credenciais do cliente sejam delegadas a todos os computadores no domínio **fabrikam.com** .</span><span class="sxs-lookup"><span data-stu-id="53160-126">This example allows the client credentials to be delegated to all the computers in the **fabrikam.com** domain.</span></span> <span data-ttu-id="53160-127">O curinga asterisco ( `*` ) especifica todos os computadores.</span><span class="sxs-lookup"><span data-stu-id="53160-127">The asterisk (`*`) wildcard specifies all computers.</span></span>

> [!NOTE]
> <span data-ttu-id="53160-128">O uso de caracteres curinga com o parâmetro **DelegateComputer** pode habilitar o CredSSP em mais computadores do que o necessário.</span><span class="sxs-lookup"><span data-stu-id="53160-128">Using wildcards with the **DelegateComputer** parameter can enable CredSSP on more computers than necessary.</span></span>

```powershell
Enable-WSManCredSSP -Role "Client" -DelegateComputer "*.fabrikam.com"
```

```Output
cfg         : http://schemas.microsoft.com/wbem/wsman/1/config/client/auth
lang        : en-US
Basic       : true
Digest      : true
Kerberos    : true
Negotiate   : true
Certificate : true
CredSSP     : true
```

### <span data-ttu-id="53160-129">Exemplo 3: delegar credenciais de cliente a vários computadores</span><span class="sxs-lookup"><span data-stu-id="53160-129">Example 3: Delegate client credentials to multiple computers</span></span>

<span data-ttu-id="53160-130">Este exemplo permite que as credenciais do cliente sejam delegadas a vários computadores.</span><span class="sxs-lookup"><span data-stu-id="53160-130">This example allows the client credentials to be delegated to multiple computers.</span></span>

```powershell
$servers = "server02.fabrikam.com", "server03.fabrikam.com", "server04.fabrikam.com"
Enable-WSManCredSSP -Role "Client" -DelegateComputer $servers
```

```Output
cfg         : http://schemas.microsoft.com/wbem/wsman/1/config/client/auth
lang        : en-US
Basic       : true
Digest      : true
Kerberos    : true
Negotiate   : true
Certificate : true
CredSSP     : true
```

<span data-ttu-id="53160-131">A `$servers` variável contém uma lista de nomes de servidor.</span><span class="sxs-lookup"><span data-stu-id="53160-131">The `$servers` variable contains a list of server names.</span></span> <span data-ttu-id="53160-132">`Enable-WSManCredSSP` usa o parâmetro de **função** para especificar a função de **cliente** .</span><span class="sxs-lookup"><span data-stu-id="53160-132">`Enable-WSManCredSSP` uses the **Role** parameter to specify the **Client** role.</span></span> <span data-ttu-id="53160-133">O **DelegateComputer** Obtém os nomes de computador da `$servers` variável.</span><span class="sxs-lookup"><span data-stu-id="53160-133">The **DelegateComputer** gets the computer names from the `$servers` variable.</span></span>

### <span data-ttu-id="53160-134">Exemplo 4: permitir que um computador atue como um delegado</span><span class="sxs-lookup"><span data-stu-id="53160-134">Example 4: Allow a computer to act as a delegate</span></span>

<span data-ttu-id="53160-135">Este exemplo permite que um computador atue como um delegado para outro.</span><span class="sxs-lookup"><span data-stu-id="53160-135">This example allows a computer to act as a delegate for another.</span></span> <span data-ttu-id="53160-136">O `Enable-WSManCredSSP` cmdlet, mostrado nos exemplos anteriores, habilita apenas a autenticação CredSSP no cliente e especifica os computadores remotos que podem agir em seu nome.</span><span class="sxs-lookup"><span data-stu-id="53160-136">The `Enable-WSManCredSSP` cmdlet, shown in the earlier examples, only enables CredSSP authentication on the client, and specifies the remote computers that can act on its behalf.</span></span> <span data-ttu-id="53160-137">Para que o computador remoto atue como um delegado para o cliente, o item CredSSP no nó de **serviço** do WSMan deve ser definido como true.</span><span class="sxs-lookup"><span data-stu-id="53160-137">In order for the remote computer to act as a delegate for the client, the CredSSP item in the **Service** node of WSMan must be set to true.</span></span> <span data-ttu-id="53160-138">Este exemplo define o item CredSSP no nó de **serviço** do WSMan como true.</span><span class="sxs-lookup"><span data-stu-id="53160-138">This example sets the CredSSP item in the **Service** node of WSMan to true.</span></span>

```powershell
Enable-WSManCredSSP -Role "Server"
```

### <span data-ttu-id="53160-139">Exemplo 5: permitir que um computador atue como um delegado usando Set-Item</span><span class="sxs-lookup"><span data-stu-id="53160-139">Example 5: Allow a computer to act as a delegate by using Set-Item</span></span>

<span data-ttu-id="53160-140">Este exemplo permite que um computador atue como um delegado para outro computador.</span><span class="sxs-lookup"><span data-stu-id="53160-140">This example allows a computer to act as a delegate for another computer.</span></span> <span data-ttu-id="53160-141">Os `Enable-WSManCredSSP` comandos, mostrados nos exemplos anteriores, habilitam a autenticação CredSSP somente no computador cliente e especificam os computadores remotos que podem agir em nome do computador cliente.</span><span class="sxs-lookup"><span data-stu-id="53160-141">The `Enable-WSManCredSSP` commands, shown in the earlier examples, enable CredSSP authentication only on the client computer, and they specify the remote computers that can act on behalf of the client computer.</span></span> <span data-ttu-id="53160-142">Para que o computador remoto atue como um delegado do cliente remoto, o item CredSSP do diretório de Serviço do provedor WSMan deve ser definido como true.</span><span class="sxs-lookup"><span data-stu-id="53160-142">For the remote computer to act as a delegate for the client computer, the CredSSP item in the Service directory of the WSMan provider must be set to true.</span></span>

```powershell
Connect-WSMan -ComputerName "server02"
Set-Item -Path "WSMan:\server02\service\auth\credSSP" -Value $True
```

<span data-ttu-id="53160-143">`Connect-WSMan` Cria uma conexão com o computador remoto, Server02.</span><span class="sxs-lookup"><span data-stu-id="53160-143">`Connect-WSMan` creates a connection to the remote computer, server02.</span></span> <span data-ttu-id="53160-144">`Set-Item` usa o parâmetro **path** para especificar o local do provedor do **WSMan** .</span><span class="sxs-lookup"><span data-stu-id="53160-144">`Set-Item` uses the **Path** parameter to specify the **WSMan** provider's location.</span></span> <span data-ttu-id="53160-145">O parâmetro **Value** define a configuração de **serviço** como true.</span><span class="sxs-lookup"><span data-stu-id="53160-145">The **Value** parameter sets the **Service** setting to true.</span></span>

## <span data-ttu-id="53160-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="53160-146">PARAMETERS</span></span>

### <span data-ttu-id="53160-147">-DelegateComputer</span><span class="sxs-lookup"><span data-stu-id="53160-147">-DelegateComputer</span></span>

<span data-ttu-id="53160-148">Especifica os servidores para os quais as credenciais de cliente são delegadas.</span><span class="sxs-lookup"><span data-stu-id="53160-148">Specifies servers to which client credentials are delegated.</span></span> <span data-ttu-id="53160-149">A prática recomendada é usar nomes de domínio totalmente qualificados.</span><span class="sxs-lookup"><span data-stu-id="53160-149">The best practice is to use fully qualified domain names.</span></span>

<span data-ttu-id="53160-150">Caracteres curinga são aceitos, mas podem habilitar o CredSSP em mais computadores do que o necessário.</span><span class="sxs-lookup"><span data-stu-id="53160-150">Wildcards are accepted, but can enable CredSSP on more computers than necessary.</span></span>

<span data-ttu-id="53160-151">Se o parâmetro de **função** for **cliente** , você deverá especificar esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="53160-151">If the **Role** parameter is **Client** , you must specify this parameter.</span></span> <span data-ttu-id="53160-152">Se a **função** for **servidor** , não especifique esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="53160-152">If **Role** is **Server** , don't specify this parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="53160-153">-Force</span><span class="sxs-lookup"><span data-stu-id="53160-153">-Force</span></span>

<span data-ttu-id="53160-154">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="53160-154">Forces the command to run without asking for user confirmation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="53160-155">-Função</span><span class="sxs-lookup"><span data-stu-id="53160-155">-Role</span></span>

<span data-ttu-id="53160-156">Especifica se o CredSSP deve ser habilitado como um cliente ou como um servidor.</span><span class="sxs-lookup"><span data-stu-id="53160-156">Specifies whether to enable CredSSP as a client or as a server.</span></span> <span data-ttu-id="53160-157">Os valores aceitáveis para esse parâmetro são: **cliente** e **servidor** .</span><span class="sxs-lookup"><span data-stu-id="53160-157">The acceptable values for this parameter are: **Client** and **Server** .</span></span>

<span data-ttu-id="53160-158">Se você especificar **cliente** , as ações a seguir serão executadas.</span><span class="sxs-lookup"><span data-stu-id="53160-158">If you specify **Client** , the following actions are performed.</span></span> <span data-ttu-id="53160-159">Essas configurações permitem que o cliente delegue credenciais explícitas a um servidor quando a autenticação do servidor é obtida.</span><span class="sxs-lookup"><span data-stu-id="53160-159">These settings allow the client to delegate explicit credentials to a server when server authentication is achieved.</span></span>

- <span data-ttu-id="53160-160">Habilita o CredSSP no cliente.</span><span class="sxs-lookup"><span data-stu-id="53160-160">Enables CredSSP on the client.</span></span>
- <span data-ttu-id="53160-161">Define a configuração de WS-Management `\<localhost|computername\>\Client\Auth\CredSSP` como true.</span><span class="sxs-lookup"><span data-stu-id="53160-161">Sets the WS-Management setting `\<localhost|computername\>\Client\Auth\CredSSP` to true.</span></span>
- <span data-ttu-id="53160-162">Define a política **AllowFreshCredentials** do Windows CredSSP como **WSMan/delegate** no cliente.</span><span class="sxs-lookup"><span data-stu-id="53160-162">Sets the Windows CredSSP policy **AllowFreshCredentials** to **WSMan/Delegate** on the client.</span></span>

<span data-ttu-id="53160-163">Se você especificar **servidor** , as ações a seguir serão executadas.</span><span class="sxs-lookup"><span data-stu-id="53160-163">If you specify **Server** , the following actions are performed.</span></span> <span data-ttu-id="53160-164">Essa configuração de política permite que o servidor aja como um delegado para clientes.</span><span class="sxs-lookup"><span data-stu-id="53160-164">This policy setting allows the server to act as a delegate for clients.</span></span>

- <span data-ttu-id="53160-165">Habilita CredSSP no servidor.</span><span class="sxs-lookup"><span data-stu-id="53160-165">Enables CredSSP on the server.</span></span>
- <span data-ttu-id="53160-166">Define a configuração de WS-Management `\<localhost|computername\>\Service\Auth\CredSSP` como true.</span><span class="sxs-lookup"><span data-stu-id="53160-166">Sets the WS-Management setting `\<localhost|computername\>\Service\Auth\CredSSP` to true.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Client, Server

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="53160-167">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="53160-167">CommonParameters</span></span>

<span data-ttu-id="53160-168">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="53160-168">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="53160-169">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="53160-169">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="53160-170">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="53160-170">INPUTS</span></span>

### <span data-ttu-id="53160-171">Nenhum</span><span class="sxs-lookup"><span data-stu-id="53160-171">None</span></span>

<span data-ttu-id="53160-172">Esse cmdlet não aceita nenhuma entrada.</span><span class="sxs-lookup"><span data-stu-id="53160-172">This cmdlet doesn't accept any input.</span></span>

## <span data-ttu-id="53160-173">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="53160-173">OUTPUTS</span></span>

### <span data-ttu-id="53160-174">Elemento System.Xml.Xml</span><span class="sxs-lookup"><span data-stu-id="53160-174">System.Xml.XmlElement</span></span>

<span data-ttu-id="53160-175">Se a autenticação CredSSP for habilitada com êxito, esse cmdlet gerará um objeto **XmlElement** .</span><span class="sxs-lookup"><span data-stu-id="53160-175">If CredSSP authentication is successfully enabled, this cmdlet generates an **XMLElement** object.</span></span>

## <span data-ttu-id="53160-176">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="53160-176">NOTES</span></span>

<span data-ttu-id="53160-177">Para desabilitar a autenticação CredSSP, use o `Disable-WSManCredSSP` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="53160-177">To disable CredSSP authentication, use the `Disable-WSManCredSSP` cmdlet.</span></span>

## <span data-ttu-id="53160-178">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="53160-178">RELATED LINKS</span></span>

[<span data-ttu-id="53160-179">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="53160-179">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="53160-180">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="53160-180">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="53160-181">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="53160-181">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="53160-182">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="53160-182">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="53160-183">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="53160-183">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="53160-184">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="53160-184">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="53160-185">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="53160-185">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="53160-186">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="53160-186">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="53160-187">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="53160-187">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="53160-188">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="53160-188">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="53160-189">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="53160-189">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="53160-190">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="53160-190">Test-WSMan</span></span>](Test-WSMan.md)
