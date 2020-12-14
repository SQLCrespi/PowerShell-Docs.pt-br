---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 10/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/publish-module?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-Module
ms.openlocfilehash: 602d160a4cc7fd4e8a806d2c3d2772ee5053535d
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94889684"
---
# <span data-ttu-id="95586-103">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="95586-103">Publish-Module</span></span>

## <span data-ttu-id="95586-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="95586-104">SYNOPSIS</span></span>
<span data-ttu-id="95586-105">Publica um módulo especificado do computador local em uma galeria online.</span><span class="sxs-lookup"><span data-stu-id="95586-105">Publishes a specified module from the local computer to an online gallery.</span></span>

## <span data-ttu-id="95586-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="95586-106">SYNTAX</span></span>

### <span data-ttu-id="95586-107">ModuleNameParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="95586-107">ModuleNameParameterSet (Default)</span></span>

```
Publish-Module -Name <String> [-RequiredVersion <String>] [-NuGetApiKey <String>]
 [-Repository <String>] [-Credential <PSCredential>] [-FormatVersion <Version>]
 [-ReleaseNotes <String[]>] [-Tags <String[]>] [-LicenseUri <Uri>] [-IconUri <Uri>]
 [-ProjectUri <Uri>] [-Exclude <String[]>] [-Force] [-AllowPrerelease] [-SkipAutomaticTags]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="95586-108">ModulePathParameterSet</span><span class="sxs-lookup"><span data-stu-id="95586-108">ModulePathParameterSet</span></span>

```
Publish-Module -Path <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-FormatVersion <Version>] [-ReleaseNotes <String[]>]
 [-Tags <String[]>] [-LicenseUri <Uri>] [-IconUri <Uri>] [-ProjectUri <Uri>] [-Force]
 [-SkipAutomaticTags] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="95586-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="95586-109">DESCRIPTION</span></span>

<span data-ttu-id="95586-110">O `Publish-Module` cmdlet publica um módulo em uma galeria online baseada em NuGet usando uma chave de API, armazenada como parte do perfil de um usuário na galeria.</span><span class="sxs-lookup"><span data-stu-id="95586-110">The `Publish-Module` cmdlet publishes a module to an online NuGet-based gallery by using an API key, stored as part of a user's profile in the gallery.</span></span> <span data-ttu-id="95586-111">Você pode especificar o módulo a ser publicado usando o nome do módulo ou o caminho para a pasta que contém o módulo.</span><span class="sxs-lookup"><span data-stu-id="95586-111">You can specify the module to publish either by the module's name, or by the path to the folder containing the module.</span></span>

<span data-ttu-id="95586-112">Quando você especifica um módulo por nome, `Publish-Module` o publica o primeiro módulo que seria encontrado executando `Get-Module -ListAvailable <Name>` .</span><span class="sxs-lookup"><span data-stu-id="95586-112">When you specify a module by name, `Publish-Module` publishes the first module that would be found by running `Get-Module -ListAvailable <Name>`.</span></span> <span data-ttu-id="95586-113">Se você especificar uma versão mínima de um módulo a ser publicado, `Publish-Module` o publicará o primeiro módulo com uma versão maior ou igual à versão mínima que você especificou.</span><span class="sxs-lookup"><span data-stu-id="95586-113">If you specify a minimum version of a module to publish, `Publish-Module` publishes the first module with a version that is greater than or equal to the minimum version that you have specified.</span></span>

<span data-ttu-id="95586-114">A publicação de um módulo requer metadados que são exibidos na página da galeria para o módulo.</span><span class="sxs-lookup"><span data-stu-id="95586-114">Publishing a module requires metadata that is displayed on the gallery page for the module.</span></span> <span data-ttu-id="95586-115">Os metadados necessários incluem o nome, a versão, a descrição e o autor do módulo.</span><span class="sxs-lookup"><span data-stu-id="95586-115">Required metadata includes the module name, version, description, and author.</span></span> <span data-ttu-id="95586-116">Embora a maioria dos metadados seja obtida do manifesto do módulo, alguns metadados devem ser especificados em `Publish-Module` parâmetros, como **tag**, **ReleaseNote**, **IconUri**, **ProjectUri** e **LicenseUri**, porque esses parâmetros correspondem aos campos em uma galeria baseada em NuGet.</span><span class="sxs-lookup"><span data-stu-id="95586-116">Although most metadata is taken from the module manifest, some metadata must be specified in `Publish-Module` parameters, such as **Tag**, **ReleaseNote**, **IconUri**, **ProjectUri**, and **LicenseUri**, because these parameters match fields in a NuGet-based gallery.</span></span>

## <span data-ttu-id="95586-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="95586-117">EXAMPLES</span></span>

### <span data-ttu-id="95586-118">Exemplo 1: publicar um módulo</span><span class="sxs-lookup"><span data-stu-id="95586-118">Example 1: Publish a module</span></span>

<span data-ttu-id="95586-119">Neste exemplo, MyDscModule é publicado na galeria online usando a chave de API para indicar a conta da galeria online do proprietário do módulo.</span><span class="sxs-lookup"><span data-stu-id="95586-119">In this example, MyDscModule is published to the online gallery by using the API key to indicate the module owner's online gallery account.</span></span> <span data-ttu-id="95586-120">Se MyDscModule não for um módulo de manifesto válido que especifica um nome, versão, descrição e autor, ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="95586-120">If MyDscModule is not a valid manifest module that specifies a name, version, description, and author, an error occurs.</span></span>

```powershell
Publish-Module -Name "MyDscModule" -NuGetApiKey "11e4b435-6cb4-4bf7-8611-5162ed75eb73"
```

### <span data-ttu-id="95586-121">Exemplo 2: publicar um módulo com metadados da Galeria</span><span class="sxs-lookup"><span data-stu-id="95586-121">Example 2: Publish a module with gallery metadata</span></span>

<span data-ttu-id="95586-122">Neste exemplo, MyDscModule é publicado na galeria online usando a chave de API para indicar a conta da galeria do proprietário do módulo.</span><span class="sxs-lookup"><span data-stu-id="95586-122">In this example, MyDscModule is published to the online gallery by using the API key to indicate the module owner's gallery account.</span></span> <span data-ttu-id="95586-123">Os metadados adicionais fornecidos são exibidos na página da Web para o módulo na galeria.</span><span class="sxs-lookup"><span data-stu-id="95586-123">The additional metadata provided is displayed on the webpage for the module in the gallery.</span></span> <span data-ttu-id="95586-124">O proprietário adiciona duas marcas de pesquisa para o módulo, relacionando-o a Active Directory; uma breve nota de versão é adicionada.</span><span class="sxs-lookup"><span data-stu-id="95586-124">The owner adds two search tags for the module, relating it to Active Directory; a brief release note is added.</span></span> <span data-ttu-id="95586-125">Se MyDscModule não for um módulo de manifesto válido que especifica um nome, versão, descrição e autor, ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="95586-125">If MyDscModule is not a valid manifest module that specifies a name, version, description, and author, an error occurs.</span></span>

```powershell
Publish-Module -Name "MyDscModule" -NuGetApiKey "11e4b435-6cb4-4bf7-8611-5162ed75eb73" -LicenseUri "http://contoso.com/license" -Tag "Active Directory","DSC" -ReleaseNote "Updated the ActiveDirectory DSC Resources to support adding users."
```

## <span data-ttu-id="95586-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="95586-126">PARAMETERS</span></span>

### <span data-ttu-id="95586-127">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="95586-127">-AllowPrerelease</span></span>

<span data-ttu-id="95586-128">Permite que os módulos marcados como pré-lançamento sejam publicados.</span><span class="sxs-lookup"><span data-stu-id="95586-128">Allows modules marked as prerelease to be published.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ModuleNameParameterSet
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="95586-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="95586-129">-Confirm</span></span>

<span data-ttu-id="95586-130">Solicita a confirmação antes de executar o `Publish-Module` .</span><span class="sxs-lookup"><span data-stu-id="95586-130">Prompts you for confirmation before running the `Publish-Module`.</span></span>

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

### <span data-ttu-id="95586-131">-Credential</span><span class="sxs-lookup"><span data-stu-id="95586-131">-Credential</span></span>

<span data-ttu-id="95586-132">Especifica uma conta de usuário que tem direitos para publicar um módulo para um provedor de pacote ou origem especificado.</span><span class="sxs-lookup"><span data-stu-id="95586-132">Specifies a user account that has rights to publish a module for a specified package provider or source.</span></span>

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

### <span data-ttu-id="95586-133">-Excluir</span><span class="sxs-lookup"><span data-stu-id="95586-133">-Exclude</span></span>

<span data-ttu-id="95586-134">Define os arquivos a serem excluídos do módulo publicado.</span><span class="sxs-lookup"><span data-stu-id="95586-134">Defines files to exclude from the published module.</span></span> <span data-ttu-id="95586-135">O suporte a parâmetro de **exclusão** é adicionado na versão do **PowershellGet** 2.0.0.</span><span class="sxs-lookup"><span data-stu-id="95586-135">**Exclude** parameter support is add in **PowershellGet** version 2.0.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ModuleNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="95586-136">-Force</span><span class="sxs-lookup"><span data-stu-id="95586-136">-Force</span></span>

<span data-ttu-id="95586-137">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="95586-137">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="95586-138">-FormatVersion</span><span class="sxs-lookup"><span data-stu-id="95586-138">-FormatVersion</span></span>

<span data-ttu-id="95586-139">Aceita somente valores válidos especificados pelo atributo **ValidateSet** .</span><span class="sxs-lookup"><span data-stu-id="95586-139">Accepts only valid values specified by the **ValidateSet** attribute.</span></span>

<span data-ttu-id="95586-140">Para obter mais informações, consulte [declaração de atributo ValidateSet](/powershell/scripting/developer/cmdlet/validateset-attribute-declaration) e [ValidateSetAttribute](/dotnet/api/system.management.automation.validatesetattribute).</span><span class="sxs-lookup"><span data-stu-id="95586-140">For more information, see [ValidateSet Attribute Declaration](/powershell/scripting/developer/cmdlet/validateset-attribute-declaration) and [ValidateSetAttribute](/dotnet/api/system.management.automation.validatesetattribute).</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:
Accepted values: 2.0

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="95586-141">-IconUri</span><span class="sxs-lookup"><span data-stu-id="95586-141">-IconUri</span></span>

<span data-ttu-id="95586-142">Especifica a URL de um ícone para o módulo.</span><span class="sxs-lookup"><span data-stu-id="95586-142">Specifies the URL of an icon for the module.</span></span> <span data-ttu-id="95586-143">O ícone especificado é exibido na página da Web Galeria do módulo.</span><span class="sxs-lookup"><span data-stu-id="95586-143">The specified icon is displayed on the gallery webpage for the module.</span></span>

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

### <span data-ttu-id="95586-144">-LicenseUri</span><span class="sxs-lookup"><span data-stu-id="95586-144">-LicenseUri</span></span>

<span data-ttu-id="95586-145">Especifica a URL dos termos de licenciamento para o módulo que você deseja publicar.</span><span class="sxs-lookup"><span data-stu-id="95586-145">Specifies the URL of licensing terms for the module you want to publish.</span></span>

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

### <span data-ttu-id="95586-146">-Name</span><span class="sxs-lookup"><span data-stu-id="95586-146">-Name</span></span>

<span data-ttu-id="95586-147">Especifica o nome do módulo que você deseja publicar.</span><span class="sxs-lookup"><span data-stu-id="95586-147">Specifies the name of the module that you want to publish.</span></span> <span data-ttu-id="95586-148">`Publish-Module` pesquisa o nome do módulo especificado em `$Env:PSModulePath` .</span><span class="sxs-lookup"><span data-stu-id="95586-148">`Publish-Module` searches for the specified module name in `$Env:PSModulePath`.</span></span>

```yaml
Type: System.String
Parameter Sets: ModuleNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="95586-149">-NuGetApiKey</span><span class="sxs-lookup"><span data-stu-id="95586-149">-NuGetApiKey</span></span>

<span data-ttu-id="95586-150">Especifica a chave de API que você deseja usar para publicar um módulo na galeria online.</span><span class="sxs-lookup"><span data-stu-id="95586-150">Specifies the API key that you want to use to publish a module to the online gallery.</span></span> <span data-ttu-id="95586-151">A chave de API é parte do seu perfil na galeria online e pode ser encontrada na página da sua conta de usuário na galeria.</span><span class="sxs-lookup"><span data-stu-id="95586-151">The API key is part of your profile in the online gallery, and can be found on your user account page in the gallery.</span></span> <span data-ttu-id="95586-152">A chave de API é uma funcionalidade específica do NuGet.</span><span class="sxs-lookup"><span data-stu-id="95586-152">The API key is NuGet-specific functionality.</span></span>

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

### <span data-ttu-id="95586-153">-Path</span><span class="sxs-lookup"><span data-stu-id="95586-153">-Path</span></span>

<span data-ttu-id="95586-154">Especifica o caminho para o módulo que você deseja publicar.</span><span class="sxs-lookup"><span data-stu-id="95586-154">Specifies the path to the module that you want to publish.</span></span> <span data-ttu-id="95586-155">Esse parâmetro aceita o caminho para a pasta que contém o módulo.</span><span class="sxs-lookup"><span data-stu-id="95586-155">This parameter accepts the path to the folder that contains the module.</span></span>

```yaml
Type: System.String
Parameter Sets: ModulePathParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="95586-156">-ProjectUri</span><span class="sxs-lookup"><span data-stu-id="95586-156">-ProjectUri</span></span>

<span data-ttu-id="95586-157">Especifica a URL de uma página da Web sobre este projeto.</span><span class="sxs-lookup"><span data-stu-id="95586-157">Specifies the URL of a webpage about this project.</span></span>

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

### <span data-ttu-id="95586-158">-ReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="95586-158">-ReleaseNotes</span></span>

<span data-ttu-id="95586-159">Especifica uma cadeia de caracteres contendo notas de versão ou comentários que você deseja disponibilizar para os usuários desta versão do módulo.</span><span class="sxs-lookup"><span data-stu-id="95586-159">Specifies a string containing release notes or comments that you want to be available to users of this version of the module.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="95586-160">-Repositório</span><span class="sxs-lookup"><span data-stu-id="95586-160">-Repository</span></span>

<span data-ttu-id="95586-161">Especifica o nome amigável de um repositório que foi registrado pela execução `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="95586-161">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span> <span data-ttu-id="95586-162">O repositório deve ter um **PublishLocation**, que é um URI NuGet válido.</span><span class="sxs-lookup"><span data-stu-id="95586-162">The repository must have a **PublishLocation**, which is a valid NuGet URI.</span></span>
<span data-ttu-id="95586-163">O **PublishLocation** pode ser definido executando `Set-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="95586-163">The **PublishLocation** can be set by running `Set-PSRepository`.</span></span>

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

### <span data-ttu-id="95586-164">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="95586-164">-RequiredVersion</span></span>

<span data-ttu-id="95586-165">Especifica a versão exata de um único módulo a ser publicado.</span><span class="sxs-lookup"><span data-stu-id="95586-165">Specifies the exact version of a single module to publish.</span></span>

```yaml
Type: System.String
Parameter Sets: ModuleNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="95586-166">-SkipAutomaticTags</span><span class="sxs-lookup"><span data-stu-id="95586-166">-SkipAutomaticTags</span></span>

<span data-ttu-id="95586-167">Remove comandos e recursos de serem incluídos como marcas.</span><span class="sxs-lookup"><span data-stu-id="95586-167">Removes commands and resources from being included as tags.</span></span> <span data-ttu-id="95586-168">Ignora a adição automática de marcas a um módulo.</span><span class="sxs-lookup"><span data-stu-id="95586-168">Skips automatically adding tags to a module.</span></span> <span data-ttu-id="95586-169">O suporte ao parâmetro **SkipAutomaticTags** é adicionado na versão do **PowerShellGet** 2.0.0</span><span class="sxs-lookup"><span data-stu-id="95586-169">**SkipAutomaticTags** parameter support is added in **PowerShellGet** version 2.0.0</span></span>

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

### <span data-ttu-id="95586-170">-Marcas</span><span class="sxs-lookup"><span data-stu-id="95586-170">-Tags</span></span>

<span data-ttu-id="95586-171">Adiciona uma ou mais marcas ao módulo que você está publicando.</span><span class="sxs-lookup"><span data-stu-id="95586-171">Adds one or more tags to the module that you are publishing.</span></span> <span data-ttu-id="95586-172">As marcas de exemplo incluem DesiredStateConfiguration, DSC, DSCResourceKit ou PSModule.</span><span class="sxs-lookup"><span data-stu-id="95586-172">Example tags include DesiredStateConfiguration, DSC, DSCResourceKit, or PSModule.</span></span> <span data-ttu-id="95586-173">Separe várias marcas com vírgulas.</span><span class="sxs-lookup"><span data-stu-id="95586-173">Separate multiple tags with commas.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="95586-174">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="95586-174">-WhatIf</span></span>

<span data-ttu-id="95586-175">Mostra o que aconteceria se o `Publish-Module` for executado.</span><span class="sxs-lookup"><span data-stu-id="95586-175">Shows what would happen if the `Publish-Module` runs.</span></span> <span data-ttu-id="95586-176">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="95586-176">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="95586-177">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="95586-177">CommonParameters</span></span>

<span data-ttu-id="95586-178">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="95586-178">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="95586-179">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="95586-179">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="95586-180">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="95586-180">INPUTS</span></span>

### <span data-ttu-id="95586-181">System.String</span><span class="sxs-lookup"><span data-stu-id="95586-181">System.String</span></span>

### <span data-ttu-id="95586-182">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="95586-182">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="95586-183">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="95586-183">OUTPUTS</span></span>

### <span data-ttu-id="95586-184">System.Object</span><span class="sxs-lookup"><span data-stu-id="95586-184">System.Object</span></span>

## <span data-ttu-id="95586-185">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="95586-185">NOTES</span></span>

<span data-ttu-id="95586-186">`Publish-Module` é executado no PowerShell 3,0 ou versões posteriores do PowerShell, no Windows 7 ou Windows 2008 R2 e versões posteriores do Windows.</span><span class="sxs-lookup"><span data-stu-id="95586-186">`Publish-Module` runs on PowerShell 3.0 or later releases of PowerShell, on Windows 7 or Windows 2008 R2 and later releases of Windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="95586-187">A partir de abril de 2020, o Galeria do PowerShell não dá mais suporte às versões 1,0 e 1,1 da segurança da camada de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="95586-187">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="95586-188">Se você não estiver usando o TLS 1,2 ou superior, receberá um erro ao tentar acessar o Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95586-188">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="95586-189">Use o comando a seguir para garantir que você esteja usando o TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="95586-189">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="95586-190">Para obter mais informações, consulte o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95586-190">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

<span data-ttu-id="95586-191">A publicação de um módulo requer metadados que são exibidos na página da galeria para o módulo.</span><span class="sxs-lookup"><span data-stu-id="95586-191">Publishing a module requires metadata that is displayed on the gallery page for the module.</span></span> <span data-ttu-id="95586-192">Os metadados necessários incluem o nome, a versão, a descrição e o autor do módulo.</span><span class="sxs-lookup"><span data-stu-id="95586-192">Required metadata includes the module name, version, description, and author.</span></span> <span data-ttu-id="95586-193">A maioria dos metadados é obtida do manifesto do módulo, mas alguns metadados podem ser especificados em `Publish-Module` parâmetros, como **tag**, **ReleaseNote**, **IconUri**, **ProjectUri** e **LicenseUri**.</span><span class="sxs-lookup"><span data-stu-id="95586-193">Most metadata is taken from the module manifest, but some metadata can be specified in `Publish-Module` parameters, such as **Tag**, **ReleaseNote**, **IconUri**, **ProjectUri**, and **LicenseUri**.</span></span> <span data-ttu-id="95586-194">Para obter mais informações, veja [valores de manifesto de pacote que afetam a interface do usuário do Galeria do PowerShell](/powershell/scripting/gallery/concepts/package-manifest-affecting-ui).</span><span class="sxs-lookup"><span data-stu-id="95586-194">For more information, see [Package manifest values that impact the PowerShell Gallery UI](/powershell/scripting/gallery/concepts/package-manifest-affecting-ui).</span></span>

## <span data-ttu-id="95586-195">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="95586-195">RELATED LINKS</span></span>

[<span data-ttu-id="95586-196">Find-Module</span><span class="sxs-lookup"><span data-stu-id="95586-196">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="95586-197">Install-Module</span><span class="sxs-lookup"><span data-stu-id="95586-197">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="95586-198">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="95586-198">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="95586-199">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="95586-199">Set-PSRepository</span></span>](Set-PSRepository.md)

[<span data-ttu-id="95586-200">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="95586-200">Uninstall-Module</span></span>](Uninstall-Module.md)

[<span data-ttu-id="95586-201">Update-Module</span><span class="sxs-lookup"><span data-stu-id="95586-201">Update-Module</span></span>](Update-Module.md)
