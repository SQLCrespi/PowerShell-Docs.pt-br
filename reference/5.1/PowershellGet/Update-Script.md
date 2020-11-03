---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/09/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-script?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Script
ms.openlocfilehash: 5a43e3382990209c365bb8fe5c0b320624ddfe18
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194356"
---
# <span data-ttu-id="af37b-103">Update-Script</span><span class="sxs-lookup"><span data-stu-id="af37b-103">Update-Script</span></span>

## <span data-ttu-id="af37b-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="af37b-104">SYNOPSIS</span></span>
<span data-ttu-id="af37b-105">Atualiza um script.</span><span class="sxs-lookup"><span data-stu-id="af37b-105">Updates a script.</span></span>

## <span data-ttu-id="af37b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="af37b-106">SYNTAX</span></span>

### <span data-ttu-id="af37b-107">Tudo</span><span class="sxs-lookup"><span data-stu-id="af37b-107">All</span></span>

```
Update-Script [[-Name] <String[]>] [-RequiredVersion <String>] [-MaximumVersion <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force]
 [-AllowPrerelease] [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="af37b-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="af37b-108">DESCRIPTION</span></span>

<span data-ttu-id="af37b-109">O `Update-Script` cmdlet atualiza um script que está instalado no computador local.</span><span class="sxs-lookup"><span data-stu-id="af37b-109">The `Update-Script` cmdlet updates a script that is installed on the local computer.</span></span> <span data-ttu-id="af37b-110">O script atualizado é baixado do mesmo repositório que a versão instalada.</span><span class="sxs-lookup"><span data-stu-id="af37b-110">The updated script is downloaded from the same repository as the installed version.</span></span>

## <span data-ttu-id="af37b-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="af37b-111">EXAMPLES</span></span>

### <span data-ttu-id="af37b-112">Exemplo 1: atualizar o script especificado</span><span class="sxs-lookup"><span data-stu-id="af37b-112">Example 1: Update the specified script</span></span>

<span data-ttu-id="af37b-113">Este exemplo atualiza um script instalado e exibe a versão atualizada.</span><span class="sxs-lookup"><span data-stu-id="af37b-113">This example updates an installed script and displays the updated version.</span></span>

```powershell
Update-Script -Name UpdateManagement-Template -RequiredVersion 1.1
Get-InstalledScript -Name UpdateManagement-Template
```

```Output
Version   Name                       Repository   Description
-------   ----                       ----------   -----------
1.1       UpdateManagement-Template  PSGallery    This is a template script for Update Management...
```

<span data-ttu-id="af37b-114">`Update-Script` usa o parâmetro **Name** para especificar o script a ser atualizado.</span><span class="sxs-lookup"><span data-stu-id="af37b-114">`Update-Script` uses the **Name** parameter to specify the script to update.</span></span> <span data-ttu-id="af37b-115">O parâmetro **RequiredVersion** especifica a versão do script.</span><span class="sxs-lookup"><span data-stu-id="af37b-115">The **RequiredVersion** parameter specifies the script version.</span></span> <span data-ttu-id="af37b-116">`Get-InstalledScript` exibe a versão atualizada do script.</span><span class="sxs-lookup"><span data-stu-id="af37b-116">`Get-InstalledScript` displays the updated version of the script.</span></span>

## <span data-ttu-id="af37b-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="af37b-117">PARAMETERS</span></span>

### <span data-ttu-id="af37b-118">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="af37b-118">-AcceptLicense</span></span>

<span data-ttu-id="af37b-119">Aceite automaticamente o contrato de licença durante a instalação se o pacote exigir.</span><span class="sxs-lookup"><span data-stu-id="af37b-119">Automatically accept the license agreement during installation if the package requires it.</span></span>

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

### <span data-ttu-id="af37b-120">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="af37b-120">-AllowPrerelease</span></span>

<span data-ttu-id="af37b-121">Permite que você atualize um script com o script mais recente marcado como um pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="af37b-121">Allows you to update a script with the newer script marked as a prerelease.</span></span>

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

### <span data-ttu-id="af37b-122">-Confirm</span><span class="sxs-lookup"><span data-stu-id="af37b-122">-Confirm</span></span>

<span data-ttu-id="af37b-123">Solicita a confirmação antes de executar `Update-Script` .</span><span class="sxs-lookup"><span data-stu-id="af37b-123">Prompts you for confirmation before running `Update-Script`.</span></span>

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

### <span data-ttu-id="af37b-124">-Credential</span><span class="sxs-lookup"><span data-stu-id="af37b-124">-Credential</span></span>

<span data-ttu-id="af37b-125">Especifica uma conta de usuário que tem permissão para atualizar um script.</span><span class="sxs-lookup"><span data-stu-id="af37b-125">Specifies a user account that has permission to update a script.</span></span>

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

### <span data-ttu-id="af37b-126">-Force</span><span class="sxs-lookup"><span data-stu-id="af37b-126">-Force</span></span>

<span data-ttu-id="af37b-127">Forças `Update-Script` a serem executadas sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="af37b-127">Forces `Update-Script` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="af37b-128">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="af37b-128">-MaximumVersion</span></span>

<span data-ttu-id="af37b-129">Especifica a versão máxima ou mais recente do script a ser atualizada.</span><span class="sxs-lookup"><span data-stu-id="af37b-129">Specifies the maximum, or newest, version of the script to update.</span></span> <span data-ttu-id="af37b-130">Os parâmetros **MaximumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="af37b-130">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="af37b-131">-Name</span><span class="sxs-lookup"><span data-stu-id="af37b-131">-Name</span></span>

<span data-ttu-id="af37b-132">Especifica um nome de script ou uma matriz de nomes de script para atualizar.</span><span class="sxs-lookup"><span data-stu-id="af37b-132">Specifies one script name or an array of script names to update.</span></span>

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

### <span data-ttu-id="af37b-133">-PassThru</span><span class="sxs-lookup"><span data-stu-id="af37b-133">-PassThru</span></span>

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

### <span data-ttu-id="af37b-134">-Proxy</span><span class="sxs-lookup"><span data-stu-id="af37b-134">-Proxy</span></span>

<span data-ttu-id="af37b-135">Especifica um servidor proxy para a solicitação em vez de se conectar diretamente a um recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="af37b-135">Specifies a proxy server for the request rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="af37b-136">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="af37b-136">-ProxyCredential</span></span>

<span data-ttu-id="af37b-137">Especifica uma conta de usuário que tem permissão para usar o servidor proxy especificado pelo parâmetro de **proxy** .</span><span class="sxs-lookup"><span data-stu-id="af37b-137">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="af37b-138">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="af37b-138">-RequiredVersion</span></span>

<span data-ttu-id="af37b-139">Especifica o número de versão exato do script a ser atualizado.</span><span class="sxs-lookup"><span data-stu-id="af37b-139">Specifies the exact version number of the script to update.</span></span> <span data-ttu-id="af37b-140">Os parâmetros **MinimumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="af37b-140">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="af37b-141">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="af37b-141">-WhatIf</span></span>

<span data-ttu-id="af37b-142">Mostra o que aconteceria se `Update-Script` for executado.</span><span class="sxs-lookup"><span data-stu-id="af37b-142">Shows what would happen if `Update-Script` runs.</span></span> <span data-ttu-id="af37b-143">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="af37b-143">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="af37b-144">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="af37b-144">CommonParameters</span></span>

<span data-ttu-id="af37b-145">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="af37b-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="af37b-146">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="af37b-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="af37b-147">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="af37b-147">INPUTS</span></span>

## <span data-ttu-id="af37b-148">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="af37b-148">OUTPUTS</span></span>

## <span data-ttu-id="af37b-149">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="af37b-149">NOTES</span></span>

## <span data-ttu-id="af37b-150">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="af37b-150">RELATED LINKS</span></span>

[<span data-ttu-id="af37b-151">Find-Script</span><span class="sxs-lookup"><span data-stu-id="af37b-151">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="af37b-152">Install-Script</span><span class="sxs-lookup"><span data-stu-id="af37b-152">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="af37b-153">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="af37b-153">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="af37b-154">Save-Script</span><span class="sxs-lookup"><span data-stu-id="af37b-154">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="af37b-155">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="af37b-155">Uninstall-Script</span></span>](Uninstall-Script.md)
