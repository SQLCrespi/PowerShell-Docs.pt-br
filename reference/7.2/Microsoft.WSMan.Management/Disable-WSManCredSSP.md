---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/disable-wsmancredssp?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManCredSSP
ms.openlocfilehash: 3260c88d57e98c0072af8621600a02901c561acb
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595788"
---
# <span data-ttu-id="b88da-102">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="b88da-102">Disable-WSManCredSSP</span></span>

## <span data-ttu-id="b88da-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b88da-103">SYNOPSIS</span></span>
<span data-ttu-id="b88da-104">Desabilita a autenticação CredSSP em um computador.</span><span class="sxs-lookup"><span data-stu-id="b88da-104">Disables CredSSP authentication on a computer.</span></span>

## <span data-ttu-id="b88da-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b88da-105">SYNTAX</span></span>

```
Disable-WSManCredSSP [-Role] <String> [<CommonParameters>]
```

## <span data-ttu-id="b88da-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b88da-106">DESCRIPTION</span></span>
<span data-ttu-id="b88da-107">O cmdlet **Disable-WSManCredSSP** desabilita a autenticação CredSSP (provedor de suporte à segurança de credencial) em um cliente ou em um computador servidor.</span><span class="sxs-lookup"><span data-stu-id="b88da-107">The **Disable-WSManCredSSP** cmdlet disables Credential Security Support Provider (CredSSP) authentication on a client or on a server computer.</span></span>
<span data-ttu-id="b88da-108">Quando a autenticação CredSSP é usada, as credenciais do usuário são passadas para um computador remoto a ser autenticado.</span><span class="sxs-lookup"><span data-stu-id="b88da-108">When CredSSP authentication is used, the user credentials are passed to a remote computer to be authenticated.</span></span>

<span data-ttu-id="b88da-109">Use este cmdlet para desabilitar o CredSSP no cliente especificando o cliente no parâmetro de *função* .</span><span class="sxs-lookup"><span data-stu-id="b88da-109">Use this cmdlet to disable CredSSP on the client by specifying Client in the *Role* parameter.</span></span>
<span data-ttu-id="b88da-110">Esse cmdlet executa as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="b88da-110">This cmdlet performs the following actions:</span></span>

- <span data-ttu-id="b88da-111">Desabilita o CredSSP no cliente.</span><span class="sxs-lookup"><span data-stu-id="b88da-111">Disables CredSSP on the client.</span></span> <span data-ttu-id="b88da-112">Esse cmdlet define a configuração de WS-Management **\<localhost|computername\> \Client\Auth\CredSSP** como false.</span><span class="sxs-lookup"><span data-stu-id="b88da-112">This cmdlet sets the WS-Management setting **\<localhost|computername\>\Client\Auth\CredSSP** to false.</span></span>
- <span data-ttu-id="b88da-113">Remove qualquer configuração WSMan/\* da política **AllowFreshCredentials** do Windows CredSSP no cliente.</span><span class="sxs-lookup"><span data-stu-id="b88da-113">Removes any WSMan/\* setting from the Windows CredSSP policy **AllowFreshCredentials** on the client.</span></span>

<span data-ttu-id="b88da-114">Use este cmdlet para desabilitar o CredSSP no servidor especificando o servidor na *função*.</span><span class="sxs-lookup"><span data-stu-id="b88da-114">Use this cmdlet to disable CredSSP on the server by specifying Server in *Role*.</span></span>
<span data-ttu-id="b88da-115">Esse cmdlet executa a seguinte ação:</span><span class="sxs-lookup"><span data-stu-id="b88da-115">This cmdlet performs the following action:</span></span>

- <span data-ttu-id="b88da-116">Desabilita o CredSSP no servidor.</span><span class="sxs-lookup"><span data-stu-id="b88da-116">Disables CredSSP on the server.</span></span> <span data-ttu-id="b88da-117">Esse cmdlet define a configuração de WS-Management **\<localhost|computername\> \Service\Auth\CredSSP** como false.</span><span class="sxs-lookup"><span data-stu-id="b88da-117">This cmdlet sets the WS-Management setting **\<localhost|computername\>\Service\Auth\CredSSP** to false.</span></span>

<span data-ttu-id="b88da-118">Cuidado: a autenticação CredSSP Delega as credenciais do usuário do computador local para um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="b88da-118">Caution: CredSSP authentication delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="b88da-119">Essa prática aumenta o risco de segurança da operação remota.</span><span class="sxs-lookup"><span data-stu-id="b88da-119">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="b88da-120">Se o computador remoto estiver comprometido, no momento em que as credenciais forem passadas a ele essas credenciais poderão ser usadas para controlar a sessão de rede.</span><span class="sxs-lookup"><span data-stu-id="b88da-120">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

## <span data-ttu-id="b88da-121">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b88da-121">EXAMPLES</span></span>

### <span data-ttu-id="b88da-122">Exemplo 1: desabilitar CredSSP em um cliente</span><span class="sxs-lookup"><span data-stu-id="b88da-122">Example 1: Disable CredSSP on a client</span></span>

```
PS C:\> Disable-WSManCredSSP -Role Client
```

<span data-ttu-id="b88da-123">Este comando desabilita o CredSSP no cliente, o que impede a delegação para servidores.</span><span class="sxs-lookup"><span data-stu-id="b88da-123">This command disables CredSSP on the client, which prevents delegation to servers.</span></span>

### <span data-ttu-id="b88da-124">Exemplo 2: desabilitar CredSSP em um servidor</span><span class="sxs-lookup"><span data-stu-id="b88da-124">Example 2: Disable CredSSP on a server</span></span>

```
PS C:\> Disable-WSManCredSSP -Role Server
```

<span data-ttu-id="b88da-125">Este comando desabilita o CredSSP no servidor, o que impede a delegação por meio de clientes.</span><span class="sxs-lookup"><span data-stu-id="b88da-125">This command disables CredSSP on the server, which prevents delegation from clients.</span></span>

## <span data-ttu-id="b88da-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b88da-126">PARAMETERS</span></span>

### <span data-ttu-id="b88da-127">-Função</span><span class="sxs-lookup"><span data-stu-id="b88da-127">-Role</span></span>
<span data-ttu-id="b88da-128">Especifica se o CredSSP deve ser desabilitado como um cliente ou como um servidor.</span><span class="sxs-lookup"><span data-stu-id="b88da-128">Specifies whether to disable CredSSP as a client or as a server.</span></span>
<span data-ttu-id="b88da-129">Os valores aceitáveis para esse parâmetro são: cliente e servidor.</span><span class="sxs-lookup"><span data-stu-id="b88da-129">The acceptable values for this parameter are: Client and Server.</span></span>

<span data-ttu-id="b88da-130">Se você especificar cliente, esse cmdlet executará as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="b88da-130">If you specify Client, this cmdlet performs the following actions:</span></span>

- <span data-ttu-id="b88da-131">Desabilita o CredSSP no cliente.</span><span class="sxs-lookup"><span data-stu-id="b88da-131">Disables CredSSP on the client.</span></span> <span data-ttu-id="b88da-132">Este cmdlet define WS-Management definindo **\<localhost|computername\> \Client\Auth\CredSSP** como false.</span><span class="sxs-lookup"><span data-stu-id="b88da-132">This cmdlet sets WS-Management setting **\<localhost|computername\>\Client\Auth\CredSSP** to false.</span></span>
- <span data-ttu-id="b88da-133">Remove qualquer configuração WSMan/\* da política **AllowFreshCredentials** do Windows CredSSP no cliente.</span><span class="sxs-lookup"><span data-stu-id="b88da-133">Removes any WSMan/\* setting from the Windows CredSSP policy **AllowFreshCredentials** on the client.</span></span>

<span data-ttu-id="b88da-134">Se você especificar servidor, esse cmdlet executará a seguinte ação:</span><span class="sxs-lookup"><span data-stu-id="b88da-134">If you specify Server, this cmdlet performs the following action:</span></span>

- <span data-ttu-id="b88da-135">Desabilita o CredSSP no servidor.</span><span class="sxs-lookup"><span data-stu-id="b88da-135">Disables CredSSP on the server.</span></span> <span data-ttu-id="b88da-136">Esse cmdlet define a configuração de WS-Management **\<localhost|computername\> \Service\Auth\CredSSP** como false.</span><span class="sxs-lookup"><span data-stu-id="b88da-136">This cmdlet sets the WS-Management setting **\<localhost|computername\>\Service\Auth\CredSSP** to false.</span></span>

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

### <span data-ttu-id="b88da-137">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b88da-137">CommonParameters</span></span>
<span data-ttu-id="b88da-138">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b88da-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b88da-139">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b88da-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b88da-140">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b88da-140">INPUTS</span></span>

### <span data-ttu-id="b88da-141">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b88da-141">None</span></span>
<span data-ttu-id="b88da-142">Esse cmdlet não aceita nenhuma entrada.</span><span class="sxs-lookup"><span data-stu-id="b88da-142">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="b88da-143">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b88da-143">OUTPUTS</span></span>

### <span data-ttu-id="b88da-144">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b88da-144">None</span></span>
<span data-ttu-id="b88da-145">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="b88da-145">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b88da-146">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b88da-146">NOTES</span></span>

* <span data-ttu-id="b88da-147">Para habilitar a autenticação CredSSP, utilize o cmdlet Enable-WSManCredSSP.</span><span class="sxs-lookup"><span data-stu-id="b88da-147">To enable CredSSP authentication, use the Enable-WSManCredSSP cmdlet.</span></span>

*

## <span data-ttu-id="b88da-148">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b88da-148">RELATED LINKS</span></span>

[<span data-ttu-id="b88da-149">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="b88da-149">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="b88da-150">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="b88da-150">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="b88da-151">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="b88da-151">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="b88da-152">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="b88da-152">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="b88da-153">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="b88da-153">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="b88da-154">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="b88da-154">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="b88da-155">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="b88da-155">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="b88da-156">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="b88da-156">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="b88da-157">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="b88da-157">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="b88da-158">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="b88da-158">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="b88da-159">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="b88da-159">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="b88da-160">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="b88da-160">Test-WSMan</span></span>](Test-WSMan.md)

