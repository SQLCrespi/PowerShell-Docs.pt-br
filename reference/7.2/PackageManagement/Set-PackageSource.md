---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 04/03/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/set-packagesource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PackageSource
ms.openlocfilehash: 9f258c3b02064aafdaf272141f2613ff5cbaf5b5
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "99598015"
---
# <span data-ttu-id="5d8ad-102">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="5d8ad-102">Set-PackageSource</span></span>

## <span data-ttu-id="5d8ad-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="5d8ad-103">SYNOPSIS</span></span>
<span data-ttu-id="5d8ad-104">Substitui uma origem de pacote para um provedor de pacote especificado.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-104">Replaces a package source for a specified package provider.</span></span>

## <span data-ttu-id="5d8ad-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5d8ad-105">SYNTAX</span></span>

### <span data-ttu-id="5d8ad-106">SourceBySearch (padrão)</span><span class="sxs-lookup"><span data-stu-id="5d8ad-106">SourceBySearch (Default)</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [[-Name] <String>] [-Location <String>] [-NewLocation <String>] [-NewName <String>] [-Trusted]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ProviderName <String>] [<CommonParameters>]
```

### <span data-ttu-id="5d8ad-107">SourceByInputObject</span><span class="sxs-lookup"><span data-stu-id="5d8ad-107">SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] -InputObject <PackageSource> [-Force]
 [-ForceBootstrap] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5d8ad-108">NuGet: SourceByInputObject</span><span class="sxs-lookup"><span data-stu-id="5d8ad-108">NuGet:SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="5d8ad-109">NuGet: SourceBySearch</span><span class="sxs-lookup"><span data-stu-id="5d8ad-109">NuGet:SourceBySearch</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="5d8ad-110">PowerShellGet: SourceByInputObject</span><span class="sxs-lookup"><span data-stu-id="5d8ad-110">PowerShellGet:SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

### <span data-ttu-id="5d8ad-111">PowerShellGet: SourceBySearch</span><span class="sxs-lookup"><span data-stu-id="5d8ad-111">PowerShellGet:SourceBySearch</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="5d8ad-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5d8ad-112">DESCRIPTION</span></span>

<span data-ttu-id="5d8ad-113">O `Set-PackageSource` substitui uma origem de pacote para um provedor de pacote especificado.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-113">The `Set-PackageSource` replaces a package source for a specified package provider.</span></span> <span data-ttu-id="5d8ad-114">As origens do pacote são sempre gerenciadas por um provedor de pacotes.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-114">Package sources are always managed by a package provider.</span></span>

## <span data-ttu-id="5d8ad-115">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="5d8ad-115">EXAMPLES</span></span>

### <span data-ttu-id="5d8ad-116">Exemplo 1: alterar a origem de um pacote</span><span class="sxs-lookup"><span data-stu-id="5d8ad-116">Example 1: Change a package source</span></span>

<span data-ttu-id="5d8ad-117">Esse comando altera o nome existente de uma origem de pacote.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-117">This command changes the existing name of a package source.</span></span> <span data-ttu-id="5d8ad-118">A origem é definida como **confiável**, o que elimina as solicitações para verificar a origem quando os pacotes são instalados.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-118">The source is set to **Trusted**, which eliminates prompts to verify the source when packages are installed.</span></span>

```
PS C:\> Set-PackageSource -Name MyNuget -NewName NewNuGet -Trusted -ProviderName NuGet
```

## <span data-ttu-id="5d8ad-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5d8ad-119">PARAMETERS</span></span>

### <span data-ttu-id="5d8ad-120">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="5d8ad-120">-ConfigFile</span></span>

<span data-ttu-id="5d8ad-121">Especifica um arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-121">Specifies a configuration file.</span></span>

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

### <span data-ttu-id="5d8ad-122">-Credential</span><span class="sxs-lookup"><span data-stu-id="5d8ad-122">-Credential</span></span>

<span data-ttu-id="5d8ad-123">Especifica uma conta de usuário que tem permissão para instalar provedores de pacote.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-123">Specifies a user account that has permission to install package providers.</span></span>

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

### <span data-ttu-id="5d8ad-124">-Force</span><span class="sxs-lookup"><span data-stu-id="5d8ad-124">-Force</span></span>

<span data-ttu-id="5d8ad-125">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-125">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="5d8ad-126">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="5d8ad-126">-ForceBootstrap</span></span>

<span data-ttu-id="5d8ad-127">Indica que `Set-PackageSource` o **PackageManagement** é forçado a instalar automaticamente o provedor de pacotes.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-127">Indicates that `Set-PackageSource` forces **PackageManagement** to automatically install the package provider.</span></span>

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

### <span data-ttu-id="5d8ad-128">-InputObject</span><span class="sxs-lookup"><span data-stu-id="5d8ad-128">-InputObject</span></span>

<span data-ttu-id="5d8ad-129">Especifica um objeto de ID de origem do pacote que representa o pacote que você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-129">Specifies a package source ID object that represents the package that you want to change.</span></span> <span data-ttu-id="5d8ad-130">As IDs de origem do pacote fazem parte dos resultados do `Get-PackageSource` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-130">Package source IDs are part of the results of the `Get-PackageSource` cmdlet.</span></span>

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

### <span data-ttu-id="5d8ad-131">-Local</span><span class="sxs-lookup"><span data-stu-id="5d8ad-131">-Location</span></span>

<span data-ttu-id="5d8ad-132">Especifica o local de origem do pacote atual.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-132">Specifies the current package source location.</span></span> <span data-ttu-id="5d8ad-133">O valor pode ser um URI, um caminho de arquivo ou qualquer outro formato de destino com suporte no provedor de pacotes.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-133">The value can be a URI, a file path, or any other destination format supported by the package provider.</span></span>

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

### <span data-ttu-id="5d8ad-134">-Name</span><span class="sxs-lookup"><span data-stu-id="5d8ad-134">-Name</span></span>

<span data-ttu-id="5d8ad-135">Especifica o nome de uma origem do pacote.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-135">Specifies a package source's name.</span></span>

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

### <span data-ttu-id="5d8ad-136">-NewLocation</span><span class="sxs-lookup"><span data-stu-id="5d8ad-136">-NewLocation</span></span>

<span data-ttu-id="5d8ad-137">Especifica o novo local para uma origem de pacote.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-137">Specifies the new location for a package source.</span></span> <span data-ttu-id="5d8ad-138">O valor pode ser um URI, um caminho de arquivo ou qualquer outro formato de destino com suporte no provedor de pacotes.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-138">The value can be a URI, a file path, or any other destination format supported by the package provider.</span></span>

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

### <span data-ttu-id="5d8ad-139">-NewName</span><span class="sxs-lookup"><span data-stu-id="5d8ad-139">-NewName</span></span>

<span data-ttu-id="5d8ad-140">Especifica o novo nome que você atribui a uma origem de pacote.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-140">Specifies the new name you assign to a package source.</span></span>

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

### <span data-ttu-id="5d8ad-141">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="5d8ad-141">-PackageManagementProvider</span></span>

<span data-ttu-id="5d8ad-142">Especifica um provedor de gerenciamento de pacotes.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-142">Specifies a package management provider.</span></span>

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

### <span data-ttu-id="5d8ad-143">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="5d8ad-143">-ProviderName</span></span>

<span data-ttu-id="5d8ad-144">Especifica um nome de provedor.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-144">Specifies a provider name.</span></span>

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

### <span data-ttu-id="5d8ad-145">-Proxy</span><span class="sxs-lookup"><span data-stu-id="5d8ad-145">-Proxy</span></span>

<span data-ttu-id="5d8ad-146">Especifica um servidor proxy para a solicitação, em vez de conectar-se diretamente ao recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-146">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="5d8ad-147">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="5d8ad-147">-ProxyCredential</span></span>

<span data-ttu-id="5d8ad-148">Especifica uma conta de usuário com permissão para conectar-se aos computadores especificados pelo parâmetro **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-148">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="5d8ad-149">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="5d8ad-149">-PublishLocation</span></span>

<span data-ttu-id="5d8ad-150">Especifica o local de publicação.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-150">Specifies the publish location.</span></span>

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

### <span data-ttu-id="5d8ad-151">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="5d8ad-151">-ScriptPublishLocation</span></span>

<span data-ttu-id="5d8ad-152">Especifica o local de publicação do script.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-152">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="5d8ad-153">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="5d8ad-153">-ScriptSourceLocation</span></span>

<span data-ttu-id="5d8ad-154">Especifica o local de origem do script.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-154">Specifies the script source location.</span></span>

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

### <span data-ttu-id="5d8ad-155">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="5d8ad-155">-SkipValidate</span></span>

<span data-ttu-id="5d8ad-156">Opção que ignora a validação das credenciais de uma origem de pacote.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-156">Switch that skips validating the credentials of a package source.</span></span>

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

### <span data-ttu-id="5d8ad-157">-Confiável</span><span class="sxs-lookup"><span data-stu-id="5d8ad-157">-Trusted</span></span>

<span data-ttu-id="5d8ad-158">Indica que a origem é um provedor de pacote confiável.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-158">Indicates that the source is a trusted package provider.</span></span> <span data-ttu-id="5d8ad-159">Fontes confiáveis não solicitam a verificação para instalar pacotes.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-159">Trusted sources don't prompt for verification to install packages.</span></span>

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

### <span data-ttu-id="5d8ad-160">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5d8ad-160">-Confirm</span></span>

<span data-ttu-id="5d8ad-161">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-161">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="5d8ad-162">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5d8ad-162">-WhatIf</span></span>

<span data-ttu-id="5d8ad-163">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-163">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="5d8ad-164">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-164">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="5d8ad-165">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5d8ad-165">CommonParameters</span></span>

<span data-ttu-id="5d8ad-166">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-166">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5d8ad-167">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5d8ad-167">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5d8ad-168">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="5d8ad-168">INPUTS</span></span>

### <span data-ttu-id="5d8ad-169">`Set-PackageSource` Não aceita a entrada do pipeline.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-169">`Set-PackageSource` doesn't accept pipeline input.</span></span>

## <span data-ttu-id="5d8ad-170">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="5d8ad-170">OUTPUTS</span></span>

### <span data-ttu-id="5d8ad-171">Este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-171">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="5d8ad-172">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="5d8ad-172">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d8ad-173">A partir de abril de 2020, a Galeria do PowerShell não dará mais suporte às versões 1.0 e 1.1 do protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-173">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="5d8ad-174">Se você não estiver usando o TLS 1.2 ou posterior, receberá um erro ao tentar acessar a Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-174">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="5d8ad-175">Use o seguinte comando para garantir que esteja usando o TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="5d8ad-175">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="5d8ad-176">Para obter mais informações, confira o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d8ad-176">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="5d8ad-177">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="5d8ad-177">RELATED LINKS</span></span>

[<span data-ttu-id="5d8ad-178">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="5d8ad-178">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="5d8ad-179">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="5d8ad-179">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="5d8ad-180">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="5d8ad-180">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="5d8ad-181">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="5d8ad-181">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
