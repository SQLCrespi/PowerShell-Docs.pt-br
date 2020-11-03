---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PackageManagement
ms.date: 04/03/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/set-packagesource?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PackageSource
ms.openlocfilehash: a8dc659d3ffdfcd296660f64f7b7cbd0bb132217
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193634"
---
# <span data-ttu-id="61be8-103">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="61be8-103">Set-PackageSource</span></span>

## <span data-ttu-id="61be8-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="61be8-104">SYNOPSIS</span></span>
<span data-ttu-id="61be8-105">Substitui uma origem de pacote para um provedor de pacote especificado.</span><span class="sxs-lookup"><span data-stu-id="61be8-105">Replaces a package source for a specified package provider.</span></span>

## <span data-ttu-id="61be8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="61be8-106">SYNTAX</span></span>

### <span data-ttu-id="61be8-107">SourceBySearch (padrão)</span><span class="sxs-lookup"><span data-stu-id="61be8-107">SourceBySearch (Default)</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [[-Name] <String>] [-Location <String>] [-NewLocation <String>] [-NewName <String>] [-Trusted]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ProviderName <String>] [<CommonParameters>]
```

### <span data-ttu-id="61be8-108">SourceByInputObject</span><span class="sxs-lookup"><span data-stu-id="61be8-108">SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] -InputObject <PackageSource> [-Force]
 [-ForceBootstrap] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="61be8-109">NuGet: SourceByInputObject</span><span class="sxs-lookup"><span data-stu-id="61be8-109">NuGet:SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="61be8-110">NuGet: SourceBySearch</span><span class="sxs-lookup"><span data-stu-id="61be8-110">NuGet:SourceBySearch</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="61be8-111">PowerShellGet: SourceByInputObject</span><span class="sxs-lookup"><span data-stu-id="61be8-111">PowerShellGet:SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

### <span data-ttu-id="61be8-112">PowerShellGet: SourceBySearch</span><span class="sxs-lookup"><span data-stu-id="61be8-112">PowerShellGet:SourceBySearch</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="61be8-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="61be8-113">DESCRIPTION</span></span>

<span data-ttu-id="61be8-114">O `Set-PackageSource` substitui uma origem de pacote para um provedor de pacote especificado.</span><span class="sxs-lookup"><span data-stu-id="61be8-114">The `Set-PackageSource` replaces a package source for a specified package provider.</span></span> <span data-ttu-id="61be8-115">As origens do pacote são sempre gerenciadas por um provedor de pacotes.</span><span class="sxs-lookup"><span data-stu-id="61be8-115">Package sources are always managed by a package provider.</span></span>

## <span data-ttu-id="61be8-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="61be8-116">EXAMPLES</span></span>

### <span data-ttu-id="61be8-117">Exemplo 1: alterar a origem de um pacote</span><span class="sxs-lookup"><span data-stu-id="61be8-117">Example 1: Change a package source</span></span>

<span data-ttu-id="61be8-118">Esse comando altera o nome existente de uma origem de pacote.</span><span class="sxs-lookup"><span data-stu-id="61be8-118">This command changes the existing name of a package source.</span></span> <span data-ttu-id="61be8-119">A origem é definida como **confiável** , o que elimina as solicitações para verificar a origem quando os pacotes são instalados.</span><span class="sxs-lookup"><span data-stu-id="61be8-119">The source is set to **Trusted** , which eliminates prompts to verify the source when packages are installed.</span></span>

```
PS C:\> Set-PackageSource -Name MyNuget -NewName NewNuGet -Trusted -ProviderName NuGet
```

## <span data-ttu-id="61be8-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="61be8-120">PARAMETERS</span></span>

### <span data-ttu-id="61be8-121">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="61be8-121">-ConfigFile</span></span>

<span data-ttu-id="61be8-122">Especifica um arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="61be8-122">Specifies a configuration file.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:SourceByInputObject, NuGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61be8-123">-Credential</span><span class="sxs-lookup"><span data-stu-id="61be8-123">-Credential</span></span>

<span data-ttu-id="61be8-124">Especifica uma conta de usuário que tem permissão para instalar provedores de pacote.</span><span class="sxs-lookup"><span data-stu-id="61be8-124">Specifies a user account that has permission to install package providers.</span></span>

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

### <span data-ttu-id="61be8-125">-Force</span><span class="sxs-lookup"><span data-stu-id="61be8-125">-Force</span></span>

<span data-ttu-id="61be8-126">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="61be8-126">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="61be8-127">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="61be8-127">-ForceBootstrap</span></span>

<span data-ttu-id="61be8-128">Indica que `Set-PackageSource` o **PackageManagement** é forçado a instalar automaticamente o provedor de pacotes.</span><span class="sxs-lookup"><span data-stu-id="61be8-128">Indicates that `Set-PackageSource` forces **PackageManagement** to automatically install the package provider.</span></span>

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

### <span data-ttu-id="61be8-129">-InputObject</span><span class="sxs-lookup"><span data-stu-id="61be8-129">-InputObject</span></span>

<span data-ttu-id="61be8-130">Especifica um objeto de ID de origem do pacote que representa o pacote que você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="61be8-130">Specifies a package source ID object that represents the package that you want to change.</span></span> <span data-ttu-id="61be8-131">As IDs de origem do pacote fazem parte dos resultados do `Get-PackageSource` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="61be8-131">Package source IDs are part of the results of the `Get-PackageSource` cmdlet.</span></span>

```yaml
Type: Microsoft.PackageManagement.Packaging.PackageSource
Parameter Sets: SourceByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="61be8-132">-Local</span><span class="sxs-lookup"><span data-stu-id="61be8-132">-Location</span></span>

<span data-ttu-id="61be8-133">Especifica o local de origem do pacote atual.</span><span class="sxs-lookup"><span data-stu-id="61be8-133">Specifies the current package source location.</span></span> <span data-ttu-id="61be8-134">O valor pode ser um URI, um caminho de arquivo ou qualquer outro formato de destino com suporte no provedor de pacotes.</span><span class="sxs-lookup"><span data-stu-id="61be8-134">The value can be a URI, a file path, or any other destination format supported by the package provider.</span></span>

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61be8-135">-Name</span><span class="sxs-lookup"><span data-stu-id="61be8-135">-Name</span></span>

<span data-ttu-id="61be8-136">Especifica o nome de uma origem do pacote.</span><span class="sxs-lookup"><span data-stu-id="61be8-136">Specifies a package source's name.</span></span>

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases: SourceName

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61be8-137">-NewLocation</span><span class="sxs-lookup"><span data-stu-id="61be8-137">-NewLocation</span></span>

<span data-ttu-id="61be8-138">Especifica o novo local para uma origem de pacote.</span><span class="sxs-lookup"><span data-stu-id="61be8-138">Specifies the new location for a package source.</span></span> <span data-ttu-id="61be8-139">O valor pode ser um URI, um caminho de arquivo ou qualquer outro formato de destino com suporte no provedor de pacotes.</span><span class="sxs-lookup"><span data-stu-id="61be8-139">The value can be a URI, a file path, or any other destination format supported by the package provider.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61be8-140">-NewName</span><span class="sxs-lookup"><span data-stu-id="61be8-140">-NewName</span></span>

<span data-ttu-id="61be8-141">Especifica o novo nome que você atribui a uma origem de pacote.</span><span class="sxs-lookup"><span data-stu-id="61be8-141">Specifies the new name you assign to a package source.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61be8-142">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="61be8-142">-PackageManagementProvider</span></span>

<span data-ttu-id="61be8-143">Especifica um provedor de gerenciamento de pacotes.</span><span class="sxs-lookup"><span data-stu-id="61be8-143">Specifies a package management provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61be8-144">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="61be8-144">-ProviderName</span></span>

<span data-ttu-id="61be8-145">Especifica um nome de provedor.</span><span class="sxs-lookup"><span data-stu-id="61be8-145">Specifies a provider name.</span></span>

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases: Provider
Accepted values: Bootstrap, NuGet, PowerShellGet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="61be8-146">-Proxy</span><span class="sxs-lookup"><span data-stu-id="61be8-146">-Proxy</span></span>

<span data-ttu-id="61be8-147">Especifica um servidor proxy para a solicitação, em vez de conectar-se diretamente ao recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="61be8-147">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61be8-148">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="61be8-148">-ProxyCredential</span></span>

<span data-ttu-id="61be8-149">Especifica uma conta de usuário com permissão para conectar-se aos computadores especificados pelo parâmetro **Proxy** .</span><span class="sxs-lookup"><span data-stu-id="61be8-149">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="61be8-150">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="61be8-150">-PublishLocation</span></span>

<span data-ttu-id="61be8-151">Especifica o local de publicação.</span><span class="sxs-lookup"><span data-stu-id="61be8-151">Specifies the publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61be8-152">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="61be8-152">-ScriptPublishLocation</span></span>

<span data-ttu-id="61be8-153">Especifica o local de publicação do script.</span><span class="sxs-lookup"><span data-stu-id="61be8-153">Specifies the script publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61be8-154">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="61be8-154">-ScriptSourceLocation</span></span>

<span data-ttu-id="61be8-155">Especifica o local de origem do script.</span><span class="sxs-lookup"><span data-stu-id="61be8-155">Specifies the script source location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61be8-156">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="61be8-156">-SkipValidate</span></span>

<span data-ttu-id="61be8-157">Opção que ignora a validação das credenciais de uma origem de pacote.</span><span class="sxs-lookup"><span data-stu-id="61be8-157">Switch that skips validating the credentials of a package source.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:SourceByInputObject, NuGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61be8-158">-Confiável</span><span class="sxs-lookup"><span data-stu-id="61be8-158">-Trusted</span></span>

<span data-ttu-id="61be8-159">Indica que a origem é um provedor de pacote confiável.</span><span class="sxs-lookup"><span data-stu-id="61be8-159">Indicates that the source is a trusted package provider.</span></span> <span data-ttu-id="61be8-160">Fontes confiáveis não solicitam a verificação para instalar pacotes.</span><span class="sxs-lookup"><span data-stu-id="61be8-160">Trusted sources don't prompt for verification to install packages.</span></span>

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

### <span data-ttu-id="61be8-161">-Confirm</span><span class="sxs-lookup"><span data-stu-id="61be8-161">-Confirm</span></span>

<span data-ttu-id="61be8-162">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="61be8-162">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="61be8-163">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="61be8-163">-WhatIf</span></span>

<span data-ttu-id="61be8-164">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="61be8-164">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="61be8-165">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="61be8-165">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="61be8-166">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="61be8-166">CommonParameters</span></span>

<span data-ttu-id="61be8-167">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="61be8-167">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="61be8-168">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="61be8-168">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="61be8-169">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="61be8-169">INPUTS</span></span>

### <span data-ttu-id="61be8-170">`Set-PackageSource` Não aceita a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="61be8-170">`Set-PackageSource` doesn't accept pipeline input.</span></span>

## <span data-ttu-id="61be8-171">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="61be8-171">OUTPUTS</span></span>

### <span data-ttu-id="61be8-172">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="61be8-172">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="61be8-173">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="61be8-173">NOTES</span></span>

## <span data-ttu-id="61be8-174">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="61be8-174">RELATED LINKS</span></span>

[<span data-ttu-id="61be8-175">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="61be8-175">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="61be8-176">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="61be8-176">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="61be8-177">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="61be8-177">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="61be8-178">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="61be8-178">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
