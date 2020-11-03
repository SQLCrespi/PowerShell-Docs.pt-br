---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/disable-wsmancredssp?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManCredSSP
ms.openlocfilehash: e88f230575e1e3106efc211e3f95dd82ec62146c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193246"
---
# <span data-ttu-id="df114-103">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="df114-103">Disable-WSManCredSSP</span></span>

## <span data-ttu-id="df114-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="df114-104">SYNOPSIS</span></span>
<span data-ttu-id="df114-105">Desabilita a autenticação CredSSP em um computador.</span><span class="sxs-lookup"><span data-stu-id="df114-105">Disables CredSSP authentication on a computer.</span></span>

## <span data-ttu-id="df114-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="df114-106">SYNTAX</span></span>

```
Disable-WSManCredSSP [-Role] <String> [<CommonParameters>]
```

## <span data-ttu-id="df114-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df114-107">DESCRIPTION</span></span>
<span data-ttu-id="df114-108">O cmdlet **Disable-WSManCredSSP** desabilita a autenticação CredSSP (provedor de suporte à segurança de credencial) em um cliente ou em um computador servidor.</span><span class="sxs-lookup"><span data-stu-id="df114-108">The **Disable-WSManCredSSP** cmdlet disables Credential Security Support Provider (CredSSP) authentication on a client or on a server computer.</span></span>
<span data-ttu-id="df114-109">Quando a autenticação CredSSP é usada, as credenciais do usuário são passadas para um computador remoto a ser autenticado.</span><span class="sxs-lookup"><span data-stu-id="df114-109">When CredSSP authentication is used, the user credentials are passed to a remote computer to be authenticated.</span></span>

<span data-ttu-id="df114-110">Use este cmdlet para desabilitar o CredSSP no cliente especificando o cliente no parâmetro de *função* .</span><span class="sxs-lookup"><span data-stu-id="df114-110">Use this cmdlet to disable CredSSP on the client by specifying Client in the *Role* parameter.</span></span>
<span data-ttu-id="df114-111">Esse cmdlet executa as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="df114-111">This cmdlet performs the following actions:</span></span>

- <span data-ttu-id="df114-112">Desabilita o CredSSP no cliente.</span><span class="sxs-lookup"><span data-stu-id="df114-112">Disables CredSSP on the client.</span></span> <span data-ttu-id="df114-113">Esse cmdlet define a configuração de WS-Management **\<localhost|computername\> \Client\Auth\CredSSP** como false.</span><span class="sxs-lookup"><span data-stu-id="df114-113">This cmdlet sets the WS-Management setting **\<localhost|computername\>\Client\Auth\CredSSP** to false.</span></span>
- <span data-ttu-id="df114-114">Remove qualquer configuração WSMan/\* da política **AllowFreshCredentials** do Windows CredSSP no cliente.</span><span class="sxs-lookup"><span data-stu-id="df114-114">Removes any WSMan/\* setting from the Windows CredSSP policy **AllowFreshCredentials** on the client.</span></span>

<span data-ttu-id="df114-115">Use este cmdlet para desabilitar o CredSSP no servidor especificando o servidor na *função* .</span><span class="sxs-lookup"><span data-stu-id="df114-115">Use this cmdlet to disable CredSSP on the server by specifying Server in *Role* .</span></span>
<span data-ttu-id="df114-116">Esse cmdlet executa a seguinte ação:</span><span class="sxs-lookup"><span data-stu-id="df114-116">This cmdlet performs the following action:</span></span>

- <span data-ttu-id="df114-117">Desabilita o CredSSP no servidor.</span><span class="sxs-lookup"><span data-stu-id="df114-117">Disables CredSSP on the server.</span></span> <span data-ttu-id="df114-118">Esse cmdlet define a configuração de WS-Management **\<localhost|computername\> \Service\Auth\CredSSP** como false.</span><span class="sxs-lookup"><span data-stu-id="df114-118">This cmdlet sets the WS-Management setting **\<localhost|computername\>\Service\Auth\CredSSP** to false.</span></span>

<span data-ttu-id="df114-119">Cuidado: a autenticação CredSSP Delega as credenciais do usuário do computador local para um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="df114-119">Caution: CredSSP authentication delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="df114-120">Essa prática aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="df114-120">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="df114-121">Se o computador remoto estiver comprometido, no momento em que as credenciais forem passadas a ele essas credenciais poderão ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="df114-121">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

## <span data-ttu-id="df114-122">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="df114-122">EXAMPLES</span></span>

### <span data-ttu-id="df114-123">Exemplo 1: desabilitar CredSSP em um cliente</span><span class="sxs-lookup"><span data-stu-id="df114-123">Example 1: Disable CredSSP on a client</span></span>

```
PS C:\> Disable-WSManCredSSP -Role Client
```

<span data-ttu-id="df114-124">Este comando desabilita o CredSSP no cliente, o que impede a delegação para servidores.</span><span class="sxs-lookup"><span data-stu-id="df114-124">This command disables CredSSP on the client, which prevents delegation to servers.</span></span>

### <span data-ttu-id="df114-125">Exemplo 2: desabilitar CredSSP em um servidor</span><span class="sxs-lookup"><span data-stu-id="df114-125">Example 2: Disable CredSSP on a server</span></span>

```
PS C:\> Disable-WSManCredSSP -Role Server
```

<span data-ttu-id="df114-126">Este comando desabilita o CredSSP no servidor, o que impede a delegação por meio de clientes.</span><span class="sxs-lookup"><span data-stu-id="df114-126">This command disables CredSSP on the server, which prevents delegation from clients.</span></span>

## <span data-ttu-id="df114-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="df114-127">PARAMETERS</span></span>

### <span data-ttu-id="df114-128">-Função</span><span class="sxs-lookup"><span data-stu-id="df114-128">-Role</span></span>
<span data-ttu-id="df114-129">Especifica se o CredSSP deve ser desabilitado como um cliente ou como um servidor.</span><span class="sxs-lookup"><span data-stu-id="df114-129">Specifies whether to disable CredSSP as a client or as a server.</span></span>
<span data-ttu-id="df114-130">Os valores aceitáveis para esse parâmetro são: cliente e servidor.</span><span class="sxs-lookup"><span data-stu-id="df114-130">The acceptable values for this parameter are: Client and Server.</span></span>

<span data-ttu-id="df114-131">Se você especificar cliente, esse cmdlet executará as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="df114-131">If you specify Client, this cmdlet performs the following actions:</span></span>

- <span data-ttu-id="df114-132">Desabilita o CredSSP no cliente.</span><span class="sxs-lookup"><span data-stu-id="df114-132">Disables CredSSP on the client.</span></span> <span data-ttu-id="df114-133">Este cmdlet define WS-Management definindo **\<localhost|computername\> \Client\Auth\CredSSP** como false.</span><span class="sxs-lookup"><span data-stu-id="df114-133">This cmdlet sets WS-Management setting **\<localhost|computername\>\Client\Auth\CredSSP** to false.</span></span>
- <span data-ttu-id="df114-134">Remove qualquer configuração WSMan/\* da política **AllowFreshCredentials** do Windows CredSSP no cliente.</span><span class="sxs-lookup"><span data-stu-id="df114-134">Removes any WSMan/\* setting from the Windows CredSSP policy **AllowFreshCredentials** on the client.</span></span>

<span data-ttu-id="df114-135">Se você especificar servidor, esse cmdlet executará a seguinte ação:</span><span class="sxs-lookup"><span data-stu-id="df114-135">If you specify Server, this cmdlet performs the following action:</span></span>

- <span data-ttu-id="df114-136">Desabilita o CredSSP no servidor.</span><span class="sxs-lookup"><span data-stu-id="df114-136">Disables CredSSP on the server.</span></span> <span data-ttu-id="df114-137">Esse cmdlet define a configuração de WS-Management **\<localhost|computername\> \Service\Auth\CredSSP** como false.</span><span class="sxs-lookup"><span data-stu-id="df114-137">This cmdlet sets the WS-Management setting **\<localhost|computername\>\Service\Auth\CredSSP** to false.</span></span>

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

### <span data-ttu-id="df114-138">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="df114-138">CommonParameters</span></span>
<span data-ttu-id="df114-139">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="df114-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="df114-140">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="df114-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="df114-141">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="df114-141">INPUTS</span></span>

### <span data-ttu-id="df114-142">Nenhum</span><span class="sxs-lookup"><span data-stu-id="df114-142">None</span></span>
<span data-ttu-id="df114-143">Esse cmdlet não aceita nenhuma entrada.</span><span class="sxs-lookup"><span data-stu-id="df114-143">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="df114-144">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="df114-144">OUTPUTS</span></span>

### <span data-ttu-id="df114-145">Nenhum</span><span class="sxs-lookup"><span data-stu-id="df114-145">None</span></span>
<span data-ttu-id="df114-146">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="df114-146">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="df114-147">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="df114-147">NOTES</span></span>

* <span data-ttu-id="df114-148">Para habilitar a autenticação CredSSP, utilize o cmdlet Enable-WSManCredSSP.</span><span class="sxs-lookup"><span data-stu-id="df114-148">To enable CredSSP authentication, use the Enable-WSManCredSSP cmdlet.</span></span>

*

## <span data-ttu-id="df114-149">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="df114-149">RELATED LINKS</span></span>

[<span data-ttu-id="df114-150">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="df114-150">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="df114-151">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="df114-151">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="df114-152">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="df114-152">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="df114-153">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="df114-153">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="df114-154">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="df114-154">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="df114-155">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="df114-155">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="df114-156">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="df114-156">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="df114-157">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="df114-157">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="df114-158">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="df114-158">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="df114-159">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="df114-159">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="df114-160">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="df114-160">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="df114-161">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="df114-161">Test-WSMan</span></span>](Test-WSMan.md)

