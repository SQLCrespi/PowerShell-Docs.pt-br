---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/get-wsmancredssp?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WSManCredSSP
ms.openlocfilehash: fa9e2c61654a53e367114ecd347a4eccb3b542c1
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2020
ms.locfileid: "93192666"
---
# <span data-ttu-id="23c8a-103">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="23c8a-103">Get-WSManCredSSP</span></span>

## <span data-ttu-id="23c8a-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="23c8a-104">SYNOPSIS</span></span>
<span data-ttu-id="23c8a-105">Obtém a configuração relacionada ao Credential Security Support Provider para o cliente.</span><span class="sxs-lookup"><span data-stu-id="23c8a-105">Gets the Credential Security Support Provider-related configuration for the client.</span></span>

## <span data-ttu-id="23c8a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="23c8a-106">SYNTAX</span></span>

```
Get-WSManCredSSP [<CommonParameters>]
```

## <span data-ttu-id="23c8a-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="23c8a-107">DESCRIPTION</span></span>
<span data-ttu-id="23c8a-108">O cmdlet **Get-WSManCredSSP** Obtém a configuração relacionada ao provedor de suporte de segurança de credenciais do cliente e do servidor.</span><span class="sxs-lookup"><span data-stu-id="23c8a-108">The **Get-WSManCredSSP** cmdlet gets the Credential Security Support Provider-related configuration of the client and the server.</span></span>
<span data-ttu-id="23c8a-109">A saída indica se a autenticação Credential Security Support Provider (CredSSP) está habilitada ou desabilitada.</span><span class="sxs-lookup"><span data-stu-id="23c8a-109">The output indicates whether Credential Security Support Provider (CredSSP) authentication is enabled or disabled.</span></span>
<span data-ttu-id="23c8a-110">Esse cmdlet também exibe informações de configuração para a política **AllowFreshCredentials** de CredSSP.</span><span class="sxs-lookup"><span data-stu-id="23c8a-110">This cmdlet also displays configuration information for the **AllowFreshCredentials** policy of CredSSP.</span></span>

<span data-ttu-id="23c8a-111">Quando você usa a autenticação CredSSP, as credenciais do usuário são passadas para um computador remoto a ser autenticado.</span><span class="sxs-lookup"><span data-stu-id="23c8a-111">When you use CredSSP authentication, the user credentials are passed to a remote computer to be authenticated.</span></span>
<span data-ttu-id="23c8a-112">Esse tipo de autenticação destina-se a comandos que criam uma sessão remota de outra sessão remota.</span><span class="sxs-lookup"><span data-stu-id="23c8a-112">This type of authentication is designed for commands that create a remote session from another remote session.</span></span>
<span data-ttu-id="23c8a-113">Por exemplo, se você quiser executar um trabalho em segundo plano em um computador remoto, use esse tipo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="23c8a-113">For example, if you want to run a background job on a remote computer, use this kind of authentication.</span></span>

<span data-ttu-id="23c8a-114">O cmdlet executa as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="23c8a-114">The cmdlet performs the following actions:</span></span>

- <span data-ttu-id="23c8a-115">Obtém a configuração WS-Management CredSSP no cliente ( **\<localhost|computername\> \Client\Auth\CredSSP** ).</span><span class="sxs-lookup"><span data-stu-id="23c8a-115">Gets the WS-Management CredSSP setting on the client ( **\<localhost|computername\>\Client\Auth\CredSSP** ).</span></span>
- <span data-ttu-id="23c8a-116">Obtém a configuração de política de CredSSP do Windows **AllowFreshCredentials** .</span><span class="sxs-lookup"><span data-stu-id="23c8a-116">Gets the Windows CredSSP policy setting **AllowFreshCredentials** .</span></span>
- <span data-ttu-id="23c8a-117">Obtém a configuração de WS-Management CredSSP no servidor ( **\<localhost|computername\> \Service\Auth\CredSSP** ).</span><span class="sxs-lookup"><span data-stu-id="23c8a-117">Gets the WS-Management CredSSP setting on the server ( **\<localhost|computername\>\Service\Auth\CredSSP** ).</span></span>

<span data-ttu-id="23c8a-118">Cuidado: a autenticação CredSSP Delega as credenciais do usuário do computador local para um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="23c8a-118">Caution: CredSSP authentication delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="23c8a-119">Essa prática aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="23c8a-119">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="23c8a-120">Se o computador remoto estiver comprometido, no momento em que as credenciais forem passadas a ele essas credenciais poderão ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="23c8a-120">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

## <span data-ttu-id="23c8a-121">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="23c8a-121">EXAMPLES</span></span>

### <span data-ttu-id="23c8a-122">Exemplo 1: exibir a configuração de CredSSP</span><span class="sxs-lookup"><span data-stu-id="23c8a-122">Example 1: Display CredSSP configuration</span></span>

```
PS C:\> Get-WSManCredSSP
```

<span data-ttu-id="23c8a-123">Esse comando exibe informações de configuração CredSSP para o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="23c8a-123">This command displays CredSSP configuration information for both the client and server.</span></span>

<span data-ttu-id="23c8a-124">A saída identifica que o computador está ou não configurado para CredSSP.</span><span class="sxs-lookup"><span data-stu-id="23c8a-124">The output identifies that this computer is or is not configured for CredSSP.</span></span>

<span data-ttu-id="23c8a-125">Se o computador estiver configurado para CredSSP, esta é a saída:</span><span class="sxs-lookup"><span data-stu-id="23c8a-125">If the computer is configured for CredSSP, this is the output:</span></span>

`The machine is configured to allow delegating fresh credentials to the following target(s): wsman/server02.accounting.fabrikam.com`

<span data-ttu-id="23c8a-126">Se o computador não estiver configurado para CredSSP, esta é a saída:</span><span class="sxs-lookup"><span data-stu-id="23c8a-126">If the computer is not configured for CredSSP, this is the output:</span></span>

`The machine is not configured to allow delegating fresh credentials.`

## <span data-ttu-id="23c8a-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="23c8a-127">PARAMETERS</span></span>

### <span data-ttu-id="23c8a-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="23c8a-128">CommonParameters</span></span>
<span data-ttu-id="23c8a-129">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="23c8a-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="23c8a-130">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="23c8a-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="23c8a-131">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="23c8a-131">INPUTS</span></span>

### <span data-ttu-id="23c8a-132">Nenhum</span><span class="sxs-lookup"><span data-stu-id="23c8a-132">None</span></span>
<span data-ttu-id="23c8a-133">Esse cmdlet não aceita nenhuma entrada.</span><span class="sxs-lookup"><span data-stu-id="23c8a-133">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="23c8a-134">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="23c8a-134">OUTPUTS</span></span>

### <span data-ttu-id="23c8a-135">Nenhum</span><span class="sxs-lookup"><span data-stu-id="23c8a-135">None</span></span>
<span data-ttu-id="23c8a-136">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="23c8a-136">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="23c8a-137">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="23c8a-137">NOTES</span></span>

* <span data-ttu-id="23c8a-138">Para desabilitar a autenticação CredSSP, utilize o cmdlet Disable-WSManCredSSP.</span><span class="sxs-lookup"><span data-stu-id="23c8a-138">To disable CredSSP authentication, use the Disable-WSManCredSSP cmdlet.</span></span> <span data-ttu-id="23c8a-139">Para habilitar a autenticação CredSSP, utilize o cmdlet Enable-WSManCredSSP.</span><span class="sxs-lookup"><span data-stu-id="23c8a-139">To enable CredSSP authentication, use the Enable-WSManCredSSP cmdlet.</span></span>

## <span data-ttu-id="23c8a-140">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="23c8a-140">RELATED LINKS</span></span>

[<span data-ttu-id="23c8a-141">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="23c8a-141">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="23c8a-142">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="23c8a-142">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="23c8a-143">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="23c8a-143">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="23c8a-144">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="23c8a-144">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="23c8a-145">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="23c8a-145">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="23c8a-146">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="23c8a-146">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="23c8a-147">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="23c8a-147">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="23c8a-148">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="23c8a-148">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="23c8a-149">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="23c8a-149">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="23c8a-150">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="23c8a-150">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="23c8a-151">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="23c8a-151">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="23c8a-152">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="23c8a-152">Test-WSMan</span></span>](Test-WSMan.md)
