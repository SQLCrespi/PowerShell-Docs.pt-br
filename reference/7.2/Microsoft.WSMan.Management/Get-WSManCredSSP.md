---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/get-wsmancredssp?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WSManCredSSP
ms.openlocfilehash: 9830d1feb31e9cca735a7ac8d2ed9d2ec50380b5
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597591"
---
# <span data-ttu-id="a95bb-102">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="a95bb-102">Get-WSManCredSSP</span></span>

## <span data-ttu-id="a95bb-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="a95bb-103">SYNOPSIS</span></span>
<span data-ttu-id="a95bb-104">Obtém a configuração relacionada ao Credential Security Support Provider para o cliente.</span><span class="sxs-lookup"><span data-stu-id="a95bb-104">Gets the Credential Security Support Provider-related configuration for the client.</span></span>

## <span data-ttu-id="a95bb-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a95bb-105">SYNTAX</span></span>

```
Get-WSManCredSSP [<CommonParameters>]
```

## <span data-ttu-id="a95bb-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a95bb-106">DESCRIPTION</span></span>
<span data-ttu-id="a95bb-107">O cmdlet **Get-WSManCredSSP** Obtém a configuração relacionada ao provedor de suporte de segurança de credenciais do cliente e do servidor.</span><span class="sxs-lookup"><span data-stu-id="a95bb-107">The **Get-WSManCredSSP** cmdlet gets the Credential Security Support Provider-related configuration of the client and the server.</span></span>
<span data-ttu-id="a95bb-108">A saída indica se a autenticação Credential Security Support Provider (CredSSP) está habilitada ou desabilitada.</span><span class="sxs-lookup"><span data-stu-id="a95bb-108">The output indicates whether Credential Security Support Provider (CredSSP) authentication is enabled or disabled.</span></span>
<span data-ttu-id="a95bb-109">Esse cmdlet também exibe informações de configuração para a política **AllowFreshCredentials** de CredSSP.</span><span class="sxs-lookup"><span data-stu-id="a95bb-109">This cmdlet also displays configuration information for the **AllowFreshCredentials** policy of CredSSP.</span></span>

<span data-ttu-id="a95bb-110">Quando você usa a autenticação CredSSP, as credenciais do usuário são passadas para um computador remoto a ser autenticado.</span><span class="sxs-lookup"><span data-stu-id="a95bb-110">When you use CredSSP authentication, the user credentials are passed to a remote computer to be authenticated.</span></span>
<span data-ttu-id="a95bb-111">Esse tipo de autenticação destina-se a comandos que criam uma sessão remota de outra sessão remota.</span><span class="sxs-lookup"><span data-stu-id="a95bb-111">This type of authentication is designed for commands that create a remote session from another remote session.</span></span>
<span data-ttu-id="a95bb-112">Por exemplo, se você quiser executar um trabalho em segundo plano em um computador remoto, use esse tipo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="a95bb-112">For example, if you want to run a background job on a remote computer, use this kind of authentication.</span></span>

<span data-ttu-id="a95bb-113">O cmdlet executa as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="a95bb-113">The cmdlet performs the following actions:</span></span>

- <span data-ttu-id="a95bb-114">Obtém a configuração WS-Management CredSSP no cliente (**\<localhost|computername\> \Client\Auth\CredSSP**).</span><span class="sxs-lookup"><span data-stu-id="a95bb-114">Gets the WS-Management CredSSP setting on the client (**\<localhost|computername\>\Client\Auth\CredSSP**).</span></span>
- <span data-ttu-id="a95bb-115">Obtém a configuração de política de CredSSP do Windows **AllowFreshCredentials**.</span><span class="sxs-lookup"><span data-stu-id="a95bb-115">Gets the Windows CredSSP policy setting **AllowFreshCredentials**.</span></span>
- <span data-ttu-id="a95bb-116">Obtém a configuração de WS-Management CredSSP no servidor (**\<localhost|computername\> \Service\Auth\CredSSP**).</span><span class="sxs-lookup"><span data-stu-id="a95bb-116">Gets the WS-Management CredSSP setting on the server (**\<localhost|computername\>\Service\Auth\CredSSP**).</span></span>

<span data-ttu-id="a95bb-117">Cuidado: a autenticação CredSSP Delega as credenciais do usuário do computador local para um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="a95bb-117">Caution: CredSSP authentication delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="a95bb-118">Essa prática aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="a95bb-118">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="a95bb-119">Se o computador remoto estiver comprometido, no momento em que as credenciais forem passadas a ele essas credenciais poderão ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="a95bb-119">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

## <span data-ttu-id="a95bb-120">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="a95bb-120">EXAMPLES</span></span>

### <span data-ttu-id="a95bb-121">Exemplo 1: exibir a configuração de CredSSP</span><span class="sxs-lookup"><span data-stu-id="a95bb-121">Example 1: Display CredSSP configuration</span></span>

```
PS C:\> Get-WSManCredSSP
```

<span data-ttu-id="a95bb-122">Esse comando exibe informações de configuração CredSSP para o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="a95bb-122">This command displays CredSSP configuration information for both the client and server.</span></span>

<span data-ttu-id="a95bb-123">A saída identifica que o computador está ou não configurado para CredSSP.</span><span class="sxs-lookup"><span data-stu-id="a95bb-123">The output identifies that this computer is or is not configured for CredSSP.</span></span>

<span data-ttu-id="a95bb-124">Se o computador estiver configurado para CredSSP, esta é a saída:</span><span class="sxs-lookup"><span data-stu-id="a95bb-124">If the computer is configured for CredSSP, this is the output:</span></span>

`The machine is configured to allow delegating fresh credentials to the following target(s): wsman/server02.accounting.fabrikam.com`

<span data-ttu-id="a95bb-125">Se o computador não estiver configurado para CredSSP, esta é a saída:</span><span class="sxs-lookup"><span data-stu-id="a95bb-125">If the computer is not configured for CredSSP, this is the output:</span></span>

`The machine is not configured to allow delegating fresh credentials.`

## <span data-ttu-id="a95bb-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a95bb-126">PARAMETERS</span></span>

### <span data-ttu-id="a95bb-127">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a95bb-127">CommonParameters</span></span>
<span data-ttu-id="a95bb-128">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a95bb-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a95bb-129">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a95bb-129">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a95bb-130">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="a95bb-130">INPUTS</span></span>

### <span data-ttu-id="a95bb-131">Nenhum</span><span class="sxs-lookup"><span data-stu-id="a95bb-131">None</span></span>
<span data-ttu-id="a95bb-132">Esse cmdlet não aceita nenhuma entrada.</span><span class="sxs-lookup"><span data-stu-id="a95bb-132">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="a95bb-133">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="a95bb-133">OUTPUTS</span></span>

### <span data-ttu-id="a95bb-134">Nenhum</span><span class="sxs-lookup"><span data-stu-id="a95bb-134">None</span></span>
<span data-ttu-id="a95bb-135">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="a95bb-135">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="a95bb-136">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="a95bb-136">NOTES</span></span>

* <span data-ttu-id="a95bb-137">Para desabilitar a autenticação CredSSP, utilize o cmdlet Disable-WSManCredSSP.</span><span class="sxs-lookup"><span data-stu-id="a95bb-137">To disable CredSSP authentication, use the Disable-WSManCredSSP cmdlet.</span></span> <span data-ttu-id="a95bb-138">Para habilitar a autenticação CredSSP, utilize o cmdlet Enable-WSManCredSSP.</span><span class="sxs-lookup"><span data-stu-id="a95bb-138">To enable CredSSP authentication, use the Enable-WSManCredSSP cmdlet.</span></span>

## <span data-ttu-id="a95bb-139">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="a95bb-139">RELATED LINKS</span></span>

[<span data-ttu-id="a95bb-140">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="a95bb-140">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="a95bb-141">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="a95bb-141">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="a95bb-142">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="a95bb-142">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="a95bb-143">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="a95bb-143">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="a95bb-144">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="a95bb-144">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="a95bb-145">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="a95bb-145">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="a95bb-146">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="a95bb-146">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="a95bb-147">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="a95bb-147">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="a95bb-148">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="a95bb-148">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="a95bb-149">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="a95bb-149">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="a95bb-150">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="a95bb-150">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="a95bb-151">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="a95bb-151">Test-WSMan</span></span>](Test-WSMan.md)

