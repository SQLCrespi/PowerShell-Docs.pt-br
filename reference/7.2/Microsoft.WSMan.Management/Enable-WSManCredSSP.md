---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 08/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/enable-wsmancredssp?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WSManCredSSP
ms.openlocfilehash: bacafee683fa47d7be331b4e44d2ab75be5bdb23
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595787"
---
# <span data-ttu-id="8b752-102">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="8b752-102">Enable-WSManCredSSP</span></span>

## <span data-ttu-id="8b752-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="8b752-103">SYNOPSIS</span></span>
<span data-ttu-id="8b752-104">Habilita a autenticação CredSSP (provedor de suporte à segurança de credencial) em um computador.</span><span class="sxs-lookup"><span data-stu-id="8b752-104">Enables Credential Security Support Provider (CredSSP) authentication on a computer.</span></span>

## <span data-ttu-id="8b752-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8b752-105">SYNTAX</span></span>

### <span data-ttu-id="8b752-106">Tudo</span><span class="sxs-lookup"><span data-stu-id="8b752-106">All</span></span>

```
Enable-WSManCredSSP [[-DelegateComputer] <String[]>] [-Force] [-Role] <String> [<CommonParameters>]
```

## <span data-ttu-id="8b752-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8b752-107">DESCRIPTION</span></span>

<span data-ttu-id="8b752-108">O `Enable-WSManCredSSP` cmdlet habilita a autenticação CredSSP em um cliente ou em um computador servidor.</span><span class="sxs-lookup"><span data-stu-id="8b752-108">The `Enable-WSManCredSSP` cmdlet enables CredSSP authentication on a client or on a server computer.</span></span>
<span data-ttu-id="8b752-109">Quando a autenticação CredSSP é usada, as credenciais do usuário são passadas para um computador remoto a ser autenticado.</span><span class="sxs-lookup"><span data-stu-id="8b752-109">When CredSSP authentication is used, the user credentials are passed to a remote computer to be authenticated.</span></span> <span data-ttu-id="8b752-110">Esse tipo de autenticação destina-se a comandos que criam uma sessão remota de outra sessão remota.</span><span class="sxs-lookup"><span data-stu-id="8b752-110">This type of authentication is designed for commands that create a remote session from another remote session.</span></span> <span data-ttu-id="8b752-111">Por exemplo, se você quiser executar um trabalho em segundo plano em um computador remoto, use esse tipo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="8b752-111">For example, if you want to run a background job on a remote computer, use this kind of authentication.</span></span>

<span data-ttu-id="8b752-112">`Enable-WSManCredSSP` pode habilitar CredSSP em um **cliente** ou um **servidor**.</span><span class="sxs-lookup"><span data-stu-id="8b752-112">`Enable-WSManCredSSP` can enable CredSSP on a **Client** or a **Server**.</span></span> <span data-ttu-id="8b752-113">Para habilitar o CredSSP em um cliente, especifique o **cliente** no parâmetro de **função** .</span><span class="sxs-lookup"><span data-stu-id="8b752-113">To enable CredSSP on a client, specify **Client** in the **Role** parameter.</span></span> <span data-ttu-id="8b752-114">Os clientes delegam credenciais explícitas a um servidor quando a autenticação do servidor é obtida.</span><span class="sxs-lookup"><span data-stu-id="8b752-114">Clients delegate explicit credentials to a server when server authentication is achieved.</span></span> <span data-ttu-id="8b752-115">Para habilitar o CredSSP em um servidor, especifique **servidor** no parâmetro **função** .</span><span class="sxs-lookup"><span data-stu-id="8b752-115">To enable CredSSP on a server, specify **Server** in the **Role** parameter.</span></span> <span data-ttu-id="8b752-116">Um servidor atua como um delegado para clientes.</span><span class="sxs-lookup"><span data-stu-id="8b752-116">A server acts as a delegate for clients.</span></span> <span data-ttu-id="8b752-117">Para obter mais detalhes, consulte **role** na seção Parameters.</span><span class="sxs-lookup"><span data-stu-id="8b752-117">For more details, see **Role** in the Parameters section.</span></span>

> [!CAUTION]
> <span data-ttu-id="8b752-118">A autenticação CredSSP Delega as credenciais do usuário do computador local para um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="8b752-118">CredSSP authentication delegates the user credentials from the local computer to a remote computer.</span></span> <span data-ttu-id="8b752-119">Essa prática aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="8b752-119">This practice increases the security risk of the remote operation.</span></span> <span data-ttu-id="8b752-120">Se o computador remoto estiver comprometido, no momento em que as credenciais forem passadas a ele essas credenciais poderão ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="8b752-120">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

## <span data-ttu-id="8b752-121">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="8b752-121">EXAMPLES</span></span>

### <span data-ttu-id="8b752-122">Exemplo 1: delegar credenciais de cliente</span><span class="sxs-lookup"><span data-stu-id="8b752-122">Example 1: Delegate client credentials</span></span>

<span data-ttu-id="8b752-123">Este exemplo permite que as credenciais do cliente sejam delegadas a um computador usando o nome de domínio totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="8b752-123">This example allows the client credentials to be delegated to a computer by using the fully qualified domain name.</span></span>

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

### <span data-ttu-id="8b752-124">Exemplo 2: delegar credenciais de cliente a todos os computadores em um domínio</span><span class="sxs-lookup"><span data-stu-id="8b752-124">Example 2: Delegate client credentials to all computers in a domain</span></span>

<span data-ttu-id="8b752-125">Este exemplo permite que as credenciais do cliente sejam delegadas a todos os computadores no domínio **fabrikam.com** .</span><span class="sxs-lookup"><span data-stu-id="8b752-125">This example allows the client credentials to be delegated to all the computers in the **fabrikam.com** domain.</span></span> <span data-ttu-id="8b752-126">O curinga asterisco ( `*` ) especifica todos os computadores.</span><span class="sxs-lookup"><span data-stu-id="8b752-126">The asterisk (`*`) wildcard specifies all computers.</span></span>

> [!NOTE]
> <span data-ttu-id="8b752-127">O uso de caracteres curinga com o parâmetro **DelegateComputer** pode habilitar o CredSSP em mais computadores do que o necessário.</span><span class="sxs-lookup"><span data-stu-id="8b752-127">Using wildcards with the **DelegateComputer** parameter can enable CredSSP on more computers than necessary.</span></span>

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

### <span data-ttu-id="8b752-128">Exemplo 3: delegar credenciais de cliente a vários computadores</span><span class="sxs-lookup"><span data-stu-id="8b752-128">Example 3: Delegate client credentials to multiple computers</span></span>

<span data-ttu-id="8b752-129">Este exemplo permite que as credenciais do cliente sejam delegadas a vários computadores.</span><span class="sxs-lookup"><span data-stu-id="8b752-129">This example allows the client credentials to be delegated to multiple computers.</span></span>

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

<span data-ttu-id="8b752-130">A `$servers` variável contém uma lista de nomes de servidor.</span><span class="sxs-lookup"><span data-stu-id="8b752-130">The `$servers` variable contains a list of server names.</span></span> <span data-ttu-id="8b752-131">`Enable-WSManCredSSP` usa o parâmetro de **função** para especificar a função de **cliente** .</span><span class="sxs-lookup"><span data-stu-id="8b752-131">`Enable-WSManCredSSP` uses the **Role** parameter to specify the **Client** role.</span></span> <span data-ttu-id="8b752-132">O **DelegateComputer** Obtém os nomes de computador da `$servers` variável.</span><span class="sxs-lookup"><span data-stu-id="8b752-132">The **DelegateComputer** gets the computer names from the `$servers` variable.</span></span>

### <span data-ttu-id="8b752-133">Exemplo 4: permitir que um computador atue como um delegado</span><span class="sxs-lookup"><span data-stu-id="8b752-133">Example 4: Allow a computer to act as a delegate</span></span>

<span data-ttu-id="8b752-134">Este exemplo permite que um computador atue como um delegado para outro.</span><span class="sxs-lookup"><span data-stu-id="8b752-134">This example allows a computer to act as a delegate for another.</span></span> <span data-ttu-id="8b752-135">O `Enable-WSManCredSSP` cmdlet, mostrado nos exemplos anteriores, habilita apenas a autenticação CredSSP no cliente e especifica os computadores remotos que podem agir em seu nome.</span><span class="sxs-lookup"><span data-stu-id="8b752-135">The `Enable-WSManCredSSP` cmdlet, shown in the earlier examples, only enables CredSSP authentication on the client, and specifies the remote computers that can act on its behalf.</span></span> <span data-ttu-id="8b752-136">Para que o computador remoto atue como um delegado para o cliente, o item CredSSP no nó de **serviço** do WSMan deve ser definido como true.</span><span class="sxs-lookup"><span data-stu-id="8b752-136">In order for the remote computer to act as a delegate for the client, the CredSSP item in the **Service** node of WSMan must be set to true.</span></span> <span data-ttu-id="8b752-137">Este exemplo define o item CredSSP no nó de **serviço** do WSMan como true.</span><span class="sxs-lookup"><span data-stu-id="8b752-137">This example sets the CredSSP item in the **Service** node of WSMan to true.</span></span>

```powershell
Enable-WSManCredSSP -Role "Server"
```

### <span data-ttu-id="8b752-138">Exemplo 5: permitir que um computador atue como um delegado usando Set-Item</span><span class="sxs-lookup"><span data-stu-id="8b752-138">Example 5: Allow a computer to act as a delegate by using Set-Item</span></span>

<span data-ttu-id="8b752-139">Este exemplo permite que um computador atue como um delegado para outro computador.</span><span class="sxs-lookup"><span data-stu-id="8b752-139">This example allows a computer to act as a delegate for another computer.</span></span> <span data-ttu-id="8b752-140">Os `Enable-WSManCredSSP` comandos, mostrados nos exemplos anteriores, habilitam a autenticação CredSSP somente no computador cliente e especificam os computadores remotos que podem agir em nome do computador cliente.</span><span class="sxs-lookup"><span data-stu-id="8b752-140">The `Enable-WSManCredSSP` commands, shown in the earlier examples, enable CredSSP authentication only on the client computer, and they specify the remote computers that can act on behalf of the client computer.</span></span> <span data-ttu-id="8b752-141">Para que o computador remoto atue como um delegado do cliente remoto, o item CredSSP do diretório de Serviço do provedor WSMan deve ser definido como true.</span><span class="sxs-lookup"><span data-stu-id="8b752-141">For the remote computer to act as a delegate for the client computer, the CredSSP item in the Service directory of the WSMan provider must be set to true.</span></span>

```powershell
Connect-WSMan -ComputerName "server02"
Set-Item -Path "WSMan:\server02\service\auth\credSSP" -Value $True
```

<span data-ttu-id="8b752-142">`Connect-WSMan` Cria uma conexão com o computador remoto, Server02.</span><span class="sxs-lookup"><span data-stu-id="8b752-142">`Connect-WSMan` creates a connection to the remote computer, server02.</span></span> <span data-ttu-id="8b752-143">`Set-Item` usa o parâmetro **path** para especificar o local do provedor do **WSMan** .</span><span class="sxs-lookup"><span data-stu-id="8b752-143">`Set-Item` uses the **Path** parameter to specify the **WSMan** provider's location.</span></span> <span data-ttu-id="8b752-144">O parâmetro **Value** define a configuração de **serviço** como true.</span><span class="sxs-lookup"><span data-stu-id="8b752-144">The **Value** parameter sets the **Service** setting to true.</span></span>

## <span data-ttu-id="8b752-145">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8b752-145">PARAMETERS</span></span>

### <span data-ttu-id="8b752-146">-DelegateComputer</span><span class="sxs-lookup"><span data-stu-id="8b752-146">-DelegateComputer</span></span>

<span data-ttu-id="8b752-147">Especifica os servidores para os quais as credenciais de cliente são delegadas.</span><span class="sxs-lookup"><span data-stu-id="8b752-147">Specifies servers to which client credentials are delegated.</span></span> <span data-ttu-id="8b752-148">A prática recomendada é usar nomes de domínio totalmente qualificados.</span><span class="sxs-lookup"><span data-stu-id="8b752-148">The best practice is to use fully qualified domain names.</span></span>

<span data-ttu-id="8b752-149">Caracteres curinga são aceitos, mas podem habilitar o CredSSP em mais computadores do que o necessário.</span><span class="sxs-lookup"><span data-stu-id="8b752-149">Wildcards are accepted, but can enable CredSSP on more computers than necessary.</span></span>

<span data-ttu-id="8b752-150">Se o parâmetro de **função** for **cliente**, você deverá especificar esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8b752-150">If the **Role** parameter is **Client**, you must specify this parameter.</span></span> <span data-ttu-id="8b752-151">Se a **função** for **servidor**, não especifique esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8b752-151">If **Role** is **Server**, don't specify this parameter.</span></span>

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

### <span data-ttu-id="8b752-152">-Force</span><span class="sxs-lookup"><span data-stu-id="8b752-152">-Force</span></span>

<span data-ttu-id="8b752-153">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="8b752-153">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="8b752-154">-Função</span><span class="sxs-lookup"><span data-stu-id="8b752-154">-Role</span></span>

<span data-ttu-id="8b752-155">Especifica se o CredSSP deve ser habilitado como um cliente ou como um servidor.</span><span class="sxs-lookup"><span data-stu-id="8b752-155">Specifies whether to enable CredSSP as a client or as a server.</span></span> <span data-ttu-id="8b752-156">Os valores aceitáveis para esse parâmetro são: **cliente** e **servidor**.</span><span class="sxs-lookup"><span data-stu-id="8b752-156">The acceptable values for this parameter are: **Client** and **Server**.</span></span>

<span data-ttu-id="8b752-157">Se você especificar **cliente**, as ações a seguir serão executadas.</span><span class="sxs-lookup"><span data-stu-id="8b752-157">If you specify **Client**, the following actions are performed.</span></span> <span data-ttu-id="8b752-158">Essas configurações permitem que o cliente delegue credenciais explícitas a um servidor quando a autenticação do servidor é obtida.</span><span class="sxs-lookup"><span data-stu-id="8b752-158">These settings allow the client to delegate explicit credentials to a server when server authentication is achieved.</span></span>

- <span data-ttu-id="8b752-159">Habilita o CredSSP no cliente.</span><span class="sxs-lookup"><span data-stu-id="8b752-159">Enables CredSSP on the client.</span></span>
- <span data-ttu-id="8b752-160">Define a configuração de WS-Management `\<localhost|computername\>\Client\Auth\CredSSP` como true.</span><span class="sxs-lookup"><span data-stu-id="8b752-160">Sets the WS-Management setting `\<localhost|computername\>\Client\Auth\CredSSP` to true.</span></span>
- <span data-ttu-id="8b752-161">Define a política **AllowFreshCredentials** do Windows CredSSP como **WSMan/delegate** no cliente.</span><span class="sxs-lookup"><span data-stu-id="8b752-161">Sets the Windows CredSSP policy **AllowFreshCredentials** to **WSMan/Delegate** on the client.</span></span>

<span data-ttu-id="8b752-162">Se você especificar **servidor**, as ações a seguir serão executadas.</span><span class="sxs-lookup"><span data-stu-id="8b752-162">If you specify **Server**, the following actions are performed.</span></span> <span data-ttu-id="8b752-163">Essa configuração de política permite que o servidor aja como um delegado para clientes.</span><span class="sxs-lookup"><span data-stu-id="8b752-163">This policy setting allows the server to act as a delegate for clients.</span></span>

- <span data-ttu-id="8b752-164">Habilita CredSSP no servidor.</span><span class="sxs-lookup"><span data-stu-id="8b752-164">Enables CredSSP on the server.</span></span>
- <span data-ttu-id="8b752-165">Define a configuração de WS-Management `\<localhost|computername\>\Service\Auth\CredSSP` como true.</span><span class="sxs-lookup"><span data-stu-id="8b752-165">Sets the WS-Management setting `\<localhost|computername\>\Service\Auth\CredSSP` to true.</span></span>

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

### <span data-ttu-id="8b752-166">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8b752-166">CommonParameters</span></span>

<span data-ttu-id="8b752-167">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8b752-167">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8b752-168">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8b752-168">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8b752-169">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="8b752-169">INPUTS</span></span>

### <span data-ttu-id="8b752-170">Nenhum</span><span class="sxs-lookup"><span data-stu-id="8b752-170">None</span></span>

<span data-ttu-id="8b752-171">Esse cmdlet não aceita nenhuma entrada.</span><span class="sxs-lookup"><span data-stu-id="8b752-171">This cmdlet doesn't accept any input.</span></span>

## <span data-ttu-id="8b752-172">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="8b752-172">OUTPUTS</span></span>

### <span data-ttu-id="8b752-173">Elemento System.Xml.Xml</span><span class="sxs-lookup"><span data-stu-id="8b752-173">System.Xml.XmlElement</span></span>

<span data-ttu-id="8b752-174">Se a autenticação CredSSP for habilitada com êxito, esse cmdlet gerará um objeto **XmlElement** .</span><span class="sxs-lookup"><span data-stu-id="8b752-174">If CredSSP authentication is successfully enabled, this cmdlet generates an **XMLElement** object.</span></span>

## <span data-ttu-id="8b752-175">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="8b752-175">NOTES</span></span>

<span data-ttu-id="8b752-176">Para desabilitar a autenticação CredSSP, use o `Disable-WSManCredSSP` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8b752-176">To disable CredSSP authentication, use the `Disable-WSManCredSSP` cmdlet.</span></span>

## <span data-ttu-id="8b752-177">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="8b752-177">RELATED LINKS</span></span>

[<span data-ttu-id="8b752-178">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="8b752-178">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="8b752-179">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="8b752-179">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="8b752-180">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="8b752-180">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="8b752-181">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="8b752-181">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="8b752-182">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="8b752-182">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="8b752-183">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="8b752-183">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="8b752-184">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="8b752-184">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="8b752-185">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="8b752-185">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="8b752-186">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="8b752-186">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="8b752-187">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="8b752-187">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="8b752-188">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="8b752-188">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="8b752-189">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="8b752-189">Test-WSMan</span></span>](Test-WSMan.md)

