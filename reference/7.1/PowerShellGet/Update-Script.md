---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/09/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-script?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Script
ms.openlocfilehash: 25da03724603b0000c46ae2da69d63cdf2f36cec
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94891676"
---
# <span data-ttu-id="75721-103">Update-Script</span><span class="sxs-lookup"><span data-stu-id="75721-103">Update-Script</span></span>

## <span data-ttu-id="75721-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="75721-104">SYNOPSIS</span></span>
<span data-ttu-id="75721-105">Atualiza um script.</span><span class="sxs-lookup"><span data-stu-id="75721-105">Updates a script.</span></span>

## <span data-ttu-id="75721-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="75721-106">SYNTAX</span></span>

### <span data-ttu-id="75721-107">Tudo</span><span class="sxs-lookup"><span data-stu-id="75721-107">All</span></span>

```
Update-Script [[-Name] <String[]>] [-RequiredVersion <String>] [-MaximumVersion <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force]
 [-AllowPrerelease] [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="75721-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="75721-108">DESCRIPTION</span></span>

<span data-ttu-id="75721-109">O `Update-Script` cmdlet atualiza um script que está instalado no computador local.</span><span class="sxs-lookup"><span data-stu-id="75721-109">The `Update-Script` cmdlet updates a script that is installed on the local computer.</span></span> <span data-ttu-id="75721-110">O script atualizado é baixado do mesmo repositório que a versão instalada.</span><span class="sxs-lookup"><span data-stu-id="75721-110">The updated script is downloaded from the same repository as the installed version.</span></span>

## <span data-ttu-id="75721-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="75721-111">EXAMPLES</span></span>

### <span data-ttu-id="75721-112">Exemplo 1: atualizar o script especificado</span><span class="sxs-lookup"><span data-stu-id="75721-112">Example 1: Update the specified script</span></span>

<span data-ttu-id="75721-113">Este exemplo atualiza um script instalado e exibe a versão atualizada.</span><span class="sxs-lookup"><span data-stu-id="75721-113">This example updates an installed script and displays the updated version.</span></span>

```powershell
Update-Script -Name UpdateManagement-Template -RequiredVersion 1.1
Get-InstalledScript -Name UpdateManagement-Template
```

```Output
Version   Name                       Repository   Description
-------   ----                       ----------   -----------
1.1       UpdateManagement-Template  PSGallery    This is a template script for Update Management...
```

<span data-ttu-id="75721-114">`Update-Script` usa o parâmetro **Name** para especificar o script a ser atualizado.</span><span class="sxs-lookup"><span data-stu-id="75721-114">`Update-Script` uses the **Name** parameter to specify the script to update.</span></span> <span data-ttu-id="75721-115">O parâmetro **RequiredVersion** especifica a versão do script.</span><span class="sxs-lookup"><span data-stu-id="75721-115">The **RequiredVersion** parameter specifies the script version.</span></span> <span data-ttu-id="75721-116">`Get-InstalledScript` exibe a versão atualizada do script.</span><span class="sxs-lookup"><span data-stu-id="75721-116">`Get-InstalledScript` displays the updated version of the script.</span></span>

## <span data-ttu-id="75721-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="75721-117">PARAMETERS</span></span>

### <span data-ttu-id="75721-118">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="75721-118">-AcceptLicense</span></span>

<span data-ttu-id="75721-119">Aceite automaticamente o contrato de licença durante a instalação se o pacote exigir.</span><span class="sxs-lookup"><span data-stu-id="75721-119">Automatically accept the license agreement during installation if the package requires it.</span></span>

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

### <span data-ttu-id="75721-120">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="75721-120">-AllowPrerelease</span></span>

<span data-ttu-id="75721-121">Permite que você atualize um script com o script mais recente marcado como um pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="75721-121">Allows you to update a script with the newer script marked as a prerelease.</span></span>

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

### <span data-ttu-id="75721-122">-Confirm</span><span class="sxs-lookup"><span data-stu-id="75721-122">-Confirm</span></span>

<span data-ttu-id="75721-123">Solicita a confirmação antes de executar `Update-Script` .</span><span class="sxs-lookup"><span data-stu-id="75721-123">Prompts you for confirmation before running `Update-Script`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75721-124">-Credential</span><span class="sxs-lookup"><span data-stu-id="75721-124">-Credential</span></span>

<span data-ttu-id="75721-125">Especifica uma conta de usuário que tem permissão para atualizar um script.</span><span class="sxs-lookup"><span data-stu-id="75721-125">Specifies a user account that has permission to update a script.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="75721-126">-Force</span><span class="sxs-lookup"><span data-stu-id="75721-126">-Force</span></span>

<span data-ttu-id="75721-127">Forças `Update-Script` a serem executadas sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="75721-127">Forces `Update-Script` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="75721-128">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="75721-128">-MaximumVersion</span></span>

<span data-ttu-id="75721-129">Especifica a versão máxima ou mais recente do script a ser atualizada.</span><span class="sxs-lookup"><span data-stu-id="75721-129">Specifies the maximum, or newest, version of the script to update.</span></span> <span data-ttu-id="75721-130">Os parâmetros **MaximumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="75721-130">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="75721-131">-Name</span><span class="sxs-lookup"><span data-stu-id="75721-131">-Name</span></span>

<span data-ttu-id="75721-132">Especifica um nome de script ou uma matriz de nomes de script para atualizar.</span><span class="sxs-lookup"><span data-stu-id="75721-132">Specifies one script name or an array of script names to update.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="75721-133">-PassThru</span><span class="sxs-lookup"><span data-stu-id="75721-133">-PassThru</span></span>

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

### <span data-ttu-id="75721-134">-Proxy</span><span class="sxs-lookup"><span data-stu-id="75721-134">-Proxy</span></span>

<span data-ttu-id="75721-135">Especifica um servidor proxy para a solicitação em vez de se conectar diretamente a um recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="75721-135">Specifies a proxy server for the request rather than connecting directly to an internet resource.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="75721-136">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="75721-136">-ProxyCredential</span></span>

<span data-ttu-id="75721-137">Especifica uma conta de usuário que tem permissão para usar o servidor proxy especificado pelo parâmetro de **proxy** .</span><span class="sxs-lookup"><span data-stu-id="75721-137">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="75721-138">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="75721-138">-RequiredVersion</span></span>

<span data-ttu-id="75721-139">Especifica o número de versão exato do script a ser atualizado.</span><span class="sxs-lookup"><span data-stu-id="75721-139">Specifies the exact version number of the script to update.</span></span> <span data-ttu-id="75721-140">Os parâmetros **MinimumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="75721-140">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="75721-141">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="75721-141">-WhatIf</span></span>

<span data-ttu-id="75721-142">Mostra o que aconteceria se `Update-Script` for executado.</span><span class="sxs-lookup"><span data-stu-id="75721-142">Shows what would happen if `Update-Script` runs.</span></span> <span data-ttu-id="75721-143">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="75721-143">The cmdlet isn't run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75721-144">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="75721-144">CommonParameters</span></span>

<span data-ttu-id="75721-145">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="75721-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="75721-146">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="75721-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="75721-147">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="75721-147">INPUTS</span></span>

### <span data-ttu-id="75721-148">System.String[]</span><span class="sxs-lookup"><span data-stu-id="75721-148">System.String[]</span></span>

### <span data-ttu-id="75721-149">System.String</span><span class="sxs-lookup"><span data-stu-id="75721-149">System.String</span></span>

### <span data-ttu-id="75721-150">System.Uri</span><span class="sxs-lookup"><span data-stu-id="75721-150">System.Uri</span></span>

### <span data-ttu-id="75721-151">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="75721-151">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="75721-152">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="75721-152">OUTPUTS</span></span>

### <span data-ttu-id="75721-153">System.Object</span><span class="sxs-lookup"><span data-stu-id="75721-153">System.Object</span></span>

## <span data-ttu-id="75721-154">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="75721-154">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75721-155">A partir de abril de 2020, o Galeria do PowerShell não dá mais suporte às versões 1,0 e 1,1 da segurança da camada de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="75721-155">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="75721-156">Se você não estiver usando o TLS 1,2 ou superior, receberá um erro ao tentar acessar o Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75721-156">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="75721-157">Use o comando a seguir para garantir que você esteja usando o TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="75721-157">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="75721-158">Para obter mais informações, consulte o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75721-158">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="75721-159">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="75721-159">RELATED LINKS</span></span>

[<span data-ttu-id="75721-160">Find-Script</span><span class="sxs-lookup"><span data-stu-id="75721-160">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="75721-161">Install-Script</span><span class="sxs-lookup"><span data-stu-id="75721-161">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="75721-162">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="75721-162">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="75721-163">Save-Script</span><span class="sxs-lookup"><span data-stu-id="75721-163">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="75721-164">Desinstalar-script</span><span class="sxs-lookup"><span data-stu-id="75721-164">Uninstall-Script</span></span>](Uninstall-Script.md)

