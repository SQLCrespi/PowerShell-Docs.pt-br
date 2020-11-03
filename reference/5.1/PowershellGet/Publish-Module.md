---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 10/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/publish-module?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-Module
ms.openlocfilehash: 50f873e6691ead7c220b6250458f4fdf8a90af22
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194125"
---
# <span data-ttu-id="40eb6-103">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="40eb6-103">Publish-Module</span></span>

## <span data-ttu-id="40eb6-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="40eb6-104">SYNOPSIS</span></span>
<span data-ttu-id="40eb6-105">Publica um módulo especificado do computador local em uma galeria online.</span><span class="sxs-lookup"><span data-stu-id="40eb6-105">Publishes a specified module from the local computer to an online gallery.</span></span>

## <span data-ttu-id="40eb6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="40eb6-106">SYNTAX</span></span>

### <span data-ttu-id="40eb6-107">ModuleNameParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="40eb6-107">ModuleNameParameterSet (Default)</span></span>

```
Publish-Module -Name <String> [-RequiredVersion <String>] [-NuGetApiKey <String>]
 [-Repository <String>] [-Credential <PSCredential>] [-FormatVersion <Version>]
 [-ReleaseNotes <String[]>] [-Tags <String[]>] [-LicenseUri <Uri>] [-IconUri <Uri>]
 [-ProjectUri <Uri>] [-Exclude <String[]>] [-Force] [-AllowPrerelease] [-SkipAutomaticTags]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="40eb6-108">ModulePathParameterSet</span><span class="sxs-lookup"><span data-stu-id="40eb6-108">ModulePathParameterSet</span></span>

```
Publish-Module -Path <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-FormatVersion <Version>] [-ReleaseNotes <String[]>]
 [-Tags <String[]>] [-LicenseUri <Uri>] [-IconUri <Uri>] [-ProjectUri <Uri>] [-Force]
 [-SkipAutomaticTags] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="40eb6-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="40eb6-109">DESCRIPTION</span></span>

<span data-ttu-id="40eb6-110">O `Publish-Module` cmdlet publica um módulo em uma galeria online baseada em NuGet usando uma chave de API, armazenada como parte do perfil de um usuário na galeria.</span><span class="sxs-lookup"><span data-stu-id="40eb6-110">The `Publish-Module` cmdlet publishes a module to an online NuGet-based gallery by using an API key, stored as part of a user's profile in the gallery.</span></span> <span data-ttu-id="40eb6-111">Você pode especificar o módulo a ser publicado usando o nome do módulo ou o caminho para a pasta que contém o módulo.</span><span class="sxs-lookup"><span data-stu-id="40eb6-111">You can specify the module to publish either by the module's name, or by the path to the folder containing the module.</span></span>

<span data-ttu-id="40eb6-112">Quando você especifica um módulo por nome, `Publish-Module` o publica o primeiro módulo que seria encontrado executando `Get-Module -ListAvailable <Name>` .</span><span class="sxs-lookup"><span data-stu-id="40eb6-112">When you specify a module by name, `Publish-Module` publishes the first module that would be found by running `Get-Module -ListAvailable <Name>`.</span></span> <span data-ttu-id="40eb6-113">Se você especificar uma versão mínima de um módulo a ser publicado, `Publish-Module` o publicará o primeiro módulo com uma versão maior ou igual à versão mínima que você especificou.</span><span class="sxs-lookup"><span data-stu-id="40eb6-113">If you specify a minimum version of a module to publish, `Publish-Module` publishes the first module with a version that is greater than or equal to the minimum version that you have specified.</span></span>

<span data-ttu-id="40eb6-114">A publicação de um módulo requer metadados que são exibidos na página da galeria para o módulo.</span><span class="sxs-lookup"><span data-stu-id="40eb6-114">Publishing a module requires metadata that is displayed on the gallery page for the module.</span></span> <span data-ttu-id="40eb6-115">Os metadados necessários incluem o nome, a versão, a descrição e o autor do módulo.</span><span class="sxs-lookup"><span data-stu-id="40eb6-115">Required metadata includes the module name, version, description, and author.</span></span> <span data-ttu-id="40eb6-116">Embora a maioria dos metadados seja obtida do manifesto do módulo, alguns metadados devem ser especificados em `Publish-Module` parâmetros, como **tag** , **ReleaseNote** , **IconUri** , **ProjectUri** e **LicenseUri** , porque esses parâmetros correspondem aos campos em uma galeria baseada em NuGet.</span><span class="sxs-lookup"><span data-stu-id="40eb6-116">Although most metadata is taken from the module manifest, some metadata must be specified in `Publish-Module` parameters, such as **Tag** , **ReleaseNote** , **IconUri** , **ProjectUri** , and **LicenseUri** , because these parameters match fields in a NuGet-based gallery.</span></span>

## <span data-ttu-id="40eb6-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="40eb6-117">EXAMPLES</span></span>

### <span data-ttu-id="40eb6-118">Exemplo 1: publicar um módulo</span><span class="sxs-lookup"><span data-stu-id="40eb6-118">Example 1: Publish a module</span></span>

<span data-ttu-id="40eb6-119">Neste exemplo, MyDscModule é publicado na galeria online usando a chave de API para indicar a conta da galeria online do proprietário do módulo.</span><span class="sxs-lookup"><span data-stu-id="40eb6-119">In this example, MyDscModule is published to the online gallery by using the API key to indicate the module owner's online gallery account.</span></span> <span data-ttu-id="40eb6-120">Se MyDscModule não for um módulo de manifesto válido que especifica um nome, versão, descrição e autor, ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="40eb6-120">If MyDscModule is not a valid manifest module that specifies a name, version, description, and author, an error occurs.</span></span>

```powershell
Publish-Module -Name "MyDscModule" -NuGetApiKey "11e4b435-6cb4-4bf7-8611-5162ed75eb73"
```

### <span data-ttu-id="40eb6-121">Exemplo 2: publicar um módulo com metadados da Galeria</span><span class="sxs-lookup"><span data-stu-id="40eb6-121">Example 2: Publish a module with gallery metadata</span></span>

<span data-ttu-id="40eb6-122">Neste exemplo, MyDscModule é publicado na galeria online usando a chave de API para indicar a conta da galeria do proprietário do módulo.</span><span class="sxs-lookup"><span data-stu-id="40eb6-122">In this example, MyDscModule is published to the online gallery by using the API key to indicate the module owner's gallery account.</span></span> <span data-ttu-id="40eb6-123">Os metadados adicionais fornecidos são exibidos na página da Web para o módulo na galeria.</span><span class="sxs-lookup"><span data-stu-id="40eb6-123">The additional metadata provided is displayed on the webpage for the module in the gallery.</span></span> <span data-ttu-id="40eb6-124">O proprietário adiciona duas marcas de pesquisa para o módulo, relacionando-o a Active Directory; uma breve nota de versão é adicionada.</span><span class="sxs-lookup"><span data-stu-id="40eb6-124">The owner adds two search tags for the module, relating it to Active Directory; a brief release note is added.</span></span> <span data-ttu-id="40eb6-125">Se MyDscModule não for um módulo de manifesto válido que especifica um nome, versão, descrição e autor, ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="40eb6-125">If MyDscModule is not a valid manifest module that specifies a name, version, description, and author, an error occurs.</span></span>

```powershell
Publish-Module -Name "MyDscModule" -NuGetApiKey "11e4b435-6cb4-4bf7-8611-5162ed75eb73" -LicenseUri "http://contoso.com/license" -Tag "Active Directory","DSC" -ReleaseNote "Updated the ActiveDirectory DSC Resources to support adding users."
```

## <span data-ttu-id="40eb6-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="40eb6-126">PARAMETERS</span></span>

### <span data-ttu-id="40eb6-127">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="40eb6-127">-AllowPrerelease</span></span>

<span data-ttu-id="40eb6-128">Permite que os módulos marcados como pré-lançamento sejam publicados.</span><span class="sxs-lookup"><span data-stu-id="40eb6-128">Allows modules marked as prerelease to be published.</span></span>

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

### <span data-ttu-id="40eb6-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="40eb6-129">-Confirm</span></span>

<span data-ttu-id="40eb6-130">Solicita a confirmação antes de executar o `Publish-Module` .</span><span class="sxs-lookup"><span data-stu-id="40eb6-130">Prompts you for confirmation before running the `Publish-Module`.</span></span>

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

### <span data-ttu-id="40eb6-131">-Credential</span><span class="sxs-lookup"><span data-stu-id="40eb6-131">-Credential</span></span>

<span data-ttu-id="40eb6-132">Especifica uma conta de usuário que tem direitos para publicar um módulo para um provedor de pacote ou origem especificado.</span><span class="sxs-lookup"><span data-stu-id="40eb6-132">Specifies a user account that has rights to publish a module for a specified package provider or source.</span></span>

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

### <span data-ttu-id="40eb6-133">-Excluir</span><span class="sxs-lookup"><span data-stu-id="40eb6-133">-Exclude</span></span>

<span data-ttu-id="40eb6-134">Define os arquivos a serem excluídos do módulo publicado.</span><span class="sxs-lookup"><span data-stu-id="40eb6-134">Defines files to exclude from the published module.</span></span> <span data-ttu-id="40eb6-135">O suporte a parâmetro de **exclusão** é adicionado na versão do **PowershellGet** 2.0.0.</span><span class="sxs-lookup"><span data-stu-id="40eb6-135">**Exclude** parameter support is add in **PowershellGet** version 2.0.0.</span></span>

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

### <span data-ttu-id="40eb6-136">-Force</span><span class="sxs-lookup"><span data-stu-id="40eb6-136">-Force</span></span>

<span data-ttu-id="40eb6-137">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="40eb6-137">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="40eb6-138">-FormatVersion</span><span class="sxs-lookup"><span data-stu-id="40eb6-138">-FormatVersion</span></span>

<span data-ttu-id="40eb6-139">Aceita somente valores válidos especificados pelo atributo **ValidateSet** .</span><span class="sxs-lookup"><span data-stu-id="40eb6-139">Accepts only valid values specified by the **ValidateSet** attribute.</span></span>

<span data-ttu-id="40eb6-140">Para obter mais informações, consulte [declaração de atributo ValidateSet](/powershell/scripting/developer/cmdlet/validateset-attribute-declaration) e [ValidateSetAttribute](/dotnet/api/system.management.automation.validatesetattribute).</span><span class="sxs-lookup"><span data-stu-id="40eb6-140">For more information, see [ValidateSet Attribute Declaration](/powershell/scripting/developer/cmdlet/validateset-attribute-declaration) and [ValidateSetAttribute](/dotnet/api/system.management.automation.validatesetattribute).</span></span>

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

### <span data-ttu-id="40eb6-141">-IconUri</span><span class="sxs-lookup"><span data-stu-id="40eb6-141">-IconUri</span></span>

<span data-ttu-id="40eb6-142">Especifica a URL de um ícone para o módulo.</span><span class="sxs-lookup"><span data-stu-id="40eb6-142">Specifies the URL of an icon for the module.</span></span> <span data-ttu-id="40eb6-143">O ícone especificado é exibido na página da Web Galeria do módulo.</span><span class="sxs-lookup"><span data-stu-id="40eb6-143">The specified icon is displayed on the gallery webpage for the module.</span></span>

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

### <span data-ttu-id="40eb6-144">-LicenseUri</span><span class="sxs-lookup"><span data-stu-id="40eb6-144">-LicenseUri</span></span>

<span data-ttu-id="40eb6-145">Especifica a URL dos termos de licenciamento para o módulo que você deseja publicar.</span><span class="sxs-lookup"><span data-stu-id="40eb6-145">Specifies the URL of licensing terms for the module you want to publish.</span></span>

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

### <span data-ttu-id="40eb6-146">-Name</span><span class="sxs-lookup"><span data-stu-id="40eb6-146">-Name</span></span>

<span data-ttu-id="40eb6-147">Especifica o nome do módulo que você deseja publicar.</span><span class="sxs-lookup"><span data-stu-id="40eb6-147">Specifies the name of the module that you want to publish.</span></span> <span data-ttu-id="40eb6-148">`Publish-Module` pesquisa o nome do módulo especificado em `$Env:PSModulePath` .</span><span class="sxs-lookup"><span data-stu-id="40eb6-148">`Publish-Module` searches for the specified module name in `$Env:PSModulePath`.</span></span>

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

### <span data-ttu-id="40eb6-149">-NuGetApiKey</span><span class="sxs-lookup"><span data-stu-id="40eb6-149">-NuGetApiKey</span></span>

<span data-ttu-id="40eb6-150">Especifica a chave de API que você deseja usar para publicar um módulo na galeria online.</span><span class="sxs-lookup"><span data-stu-id="40eb6-150">Specifies the API key that you want to use to publish a module to the online gallery.</span></span> <span data-ttu-id="40eb6-151">A chave de API é parte do seu perfil na galeria online e pode ser encontrada na página da sua conta de usuário na galeria.</span><span class="sxs-lookup"><span data-stu-id="40eb6-151">The API key is part of your profile in the online gallery, and can be found on your user account page in the gallery.</span></span> <span data-ttu-id="40eb6-152">A chave de API é uma funcionalidade específica do NuGet.</span><span class="sxs-lookup"><span data-stu-id="40eb6-152">The API key is NuGet-specific functionality.</span></span>

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

### <span data-ttu-id="40eb6-153">-Path</span><span class="sxs-lookup"><span data-stu-id="40eb6-153">-Path</span></span>

<span data-ttu-id="40eb6-154">Especifica o caminho para o módulo que você deseja publicar.</span><span class="sxs-lookup"><span data-stu-id="40eb6-154">Specifies the path to the module that you want to publish.</span></span> <span data-ttu-id="40eb6-155">Esse parâmetro aceita o caminho para a pasta que contém o módulo.</span><span class="sxs-lookup"><span data-stu-id="40eb6-155">This parameter accepts the path to the folder that contains the module.</span></span>

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

### <span data-ttu-id="40eb6-156">-ProjectUri</span><span class="sxs-lookup"><span data-stu-id="40eb6-156">-ProjectUri</span></span>

<span data-ttu-id="40eb6-157">Especifica a URL de uma página da Web sobre este projeto.</span><span class="sxs-lookup"><span data-stu-id="40eb6-157">Specifies the URL of a webpage about this project.</span></span>

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

### <span data-ttu-id="40eb6-158">-ReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="40eb6-158">-ReleaseNotes</span></span>

<span data-ttu-id="40eb6-159">Especifica uma cadeia de caracteres contendo notas de versão ou comentários que você deseja disponibilizar para os usuários desta versão do módulo.</span><span class="sxs-lookup"><span data-stu-id="40eb6-159">Specifies a string containing release notes or comments that you want to be available to users of this version of the module.</span></span>

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

### <span data-ttu-id="40eb6-160">-Repositório</span><span class="sxs-lookup"><span data-stu-id="40eb6-160">-Repository</span></span>

<span data-ttu-id="40eb6-161">Especifica o nome amigável de um repositório que foi registrado pela execução `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="40eb6-161">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span> <span data-ttu-id="40eb6-162">O repositório deve ter um **PublishLocation** , que é um URI NuGet válido.</span><span class="sxs-lookup"><span data-stu-id="40eb6-162">The repository must have a **PublishLocation** , which is a valid NuGet URI.</span></span>
<span data-ttu-id="40eb6-163">O **PublishLocation** pode ser definido executando `Set-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="40eb6-163">The **PublishLocation** can be set by running `Set-PSRepository`.</span></span>

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

### <span data-ttu-id="40eb6-164">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="40eb6-164">-RequiredVersion</span></span>

<span data-ttu-id="40eb6-165">Especifica a versão exata de um único módulo a ser publicado.</span><span class="sxs-lookup"><span data-stu-id="40eb6-165">Specifies the exact version of a single module to publish.</span></span>

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

### <span data-ttu-id="40eb6-166">-SkipAutomaticTags</span><span class="sxs-lookup"><span data-stu-id="40eb6-166">-SkipAutomaticTags</span></span>

<span data-ttu-id="40eb6-167">Remove comandos e recursos de serem incluídos como marcas.</span><span class="sxs-lookup"><span data-stu-id="40eb6-167">Removes commands and resources from being included as tags.</span></span> <span data-ttu-id="40eb6-168">Ignora a adição automática de marcas a um módulo.</span><span class="sxs-lookup"><span data-stu-id="40eb6-168">Skips automatically adding tags to a module.</span></span> <span data-ttu-id="40eb6-169">O suporte ao parâmetro **SkipAutomaticTags** é adicionado na versão do **PowerShellGet** 2.0.0</span><span class="sxs-lookup"><span data-stu-id="40eb6-169">**SkipAutomaticTags** parameter support is added in **PowerShellGet** version 2.0.0</span></span>

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

### <span data-ttu-id="40eb6-170">-Marcas</span><span class="sxs-lookup"><span data-stu-id="40eb6-170">-Tags</span></span>

<span data-ttu-id="40eb6-171">Adiciona uma ou mais marcas ao módulo que você está publicando.</span><span class="sxs-lookup"><span data-stu-id="40eb6-171">Adds one or more tags to the module that you are publishing.</span></span> <span data-ttu-id="40eb6-172">As marcas de exemplo incluem DesiredStateConfiguration, DSC, DSCResourceKit ou PSModule.</span><span class="sxs-lookup"><span data-stu-id="40eb6-172">Example tags include DesiredStateConfiguration, DSC, DSCResourceKit, or PSModule.</span></span> <span data-ttu-id="40eb6-173">Separe várias marcas com vírgulas.</span><span class="sxs-lookup"><span data-stu-id="40eb6-173">Separate multiple tags with commas.</span></span>

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

### <span data-ttu-id="40eb6-174">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="40eb6-174">-WhatIf</span></span>

<span data-ttu-id="40eb6-175">Mostra o que aconteceria se o `Publish-Module` for executado.</span><span class="sxs-lookup"><span data-stu-id="40eb6-175">Shows what would happen if the `Publish-Module` runs.</span></span> <span data-ttu-id="40eb6-176">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="40eb6-176">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="40eb6-177">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="40eb6-177">CommonParameters</span></span>

<span data-ttu-id="40eb6-178">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="40eb6-178">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="40eb6-179">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="40eb6-179">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="40eb6-180">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="40eb6-180">INPUTS</span></span>

### <span data-ttu-id="40eb6-181">System.String</span><span class="sxs-lookup"><span data-stu-id="40eb6-181">System.String</span></span>

### <span data-ttu-id="40eb6-182">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="40eb6-182">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="40eb6-183">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="40eb6-183">OUTPUTS</span></span>

### <span data-ttu-id="40eb6-184">System.Object</span><span class="sxs-lookup"><span data-stu-id="40eb6-184">System.Object</span></span>

## <span data-ttu-id="40eb6-185">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="40eb6-185">NOTES</span></span>

<span data-ttu-id="40eb6-186">`Publish-Module` é executado no PowerShell 3,0 ou versões posteriores do PowerShell, no Windows 7 ou Windows 2008 R2 e versões posteriores do Windows.</span><span class="sxs-lookup"><span data-stu-id="40eb6-186">`Publish-Module` runs on PowerShell 3.0 or later releases of PowerShell, on Windows 7 or Windows 2008 R2 and later releases of Windows.</span></span>

<span data-ttu-id="40eb6-187">A publicação de um módulo requer metadados que são exibidos na página da galeria para o módulo.</span><span class="sxs-lookup"><span data-stu-id="40eb6-187">Publishing a module requires metadata that is displayed on the gallery page for the module.</span></span> <span data-ttu-id="40eb6-188">Os metadados necessários incluem o nome, a versão, a descrição e o autor do módulo.</span><span class="sxs-lookup"><span data-stu-id="40eb6-188">Required metadata includes the module name, version, description, and author.</span></span> <span data-ttu-id="40eb6-189">A maioria dos metadados é obtida do manifesto do módulo, mas alguns metadados podem ser especificados em `Publish-Module` parâmetros, como **tag** , **ReleaseNote** , **IconUri** , **ProjectUri** e **LicenseUri** .</span><span class="sxs-lookup"><span data-stu-id="40eb6-189">Most metadata is taken from the module manifest, but some metadata can be specified in `Publish-Module` parameters, such as **Tag** , **ReleaseNote** , **IconUri** , **ProjectUri** , and **LicenseUri** .</span></span> <span data-ttu-id="40eb6-190">Para obter mais informações, veja [valores de manifesto de pacote que afetam a interface do usuário do Galeria do PowerShell](/powershell/scripting/gallery/concepts/package-manifest-affecting-ui).</span><span class="sxs-lookup"><span data-stu-id="40eb6-190">For more information, see [Package manifest values that impact the PowerShell Gallery UI](/powershell/scripting/gallery/concepts/package-manifest-affecting-ui).</span></span>

## <span data-ttu-id="40eb6-191">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="40eb6-191">RELATED LINKS</span></span>

[<span data-ttu-id="40eb6-192">Find-Module</span><span class="sxs-lookup"><span data-stu-id="40eb6-192">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="40eb6-193">Install-Module</span><span class="sxs-lookup"><span data-stu-id="40eb6-193">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="40eb6-194">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="40eb6-194">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="40eb6-195">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="40eb6-195">Set-PSRepository</span></span>](Set-PSRepository.md)

[<span data-ttu-id="40eb6-196">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="40eb6-196">Uninstall-Module</span></span>](Uninstall-Module.md)

[<span data-ttu-id="40eb6-197">Update-Module</span><span class="sxs-lookup"><span data-stu-id="40eb6-197">Update-Module</span></span>](Update-Module.md)
