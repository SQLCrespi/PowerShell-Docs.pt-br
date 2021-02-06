---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 10/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/publish-module?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-Module
ms.openlocfilehash: 2edc05ff660cfcca232af878c593c29de68eb122
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "99597828"
---
# <span data-ttu-id="633fb-102">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="633fb-102">Publish-Module</span></span>

## <span data-ttu-id="633fb-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="633fb-103">SYNOPSIS</span></span>
<span data-ttu-id="633fb-104">Publica um módulo especificado do computador local em uma galeria online.</span><span class="sxs-lookup"><span data-stu-id="633fb-104">Publishes a specified module from the local computer to an online gallery.</span></span>

## <span data-ttu-id="633fb-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="633fb-105">SYNTAX</span></span>

### <span data-ttu-id="633fb-106">ModuleNameParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="633fb-106">ModuleNameParameterSet (Default)</span></span>

```
Publish-Module -Name <String> [-RequiredVersion <String>] [-NuGetApiKey <String>]
 [-Repository <String>] [-Credential <PSCredential>] [-FormatVersion <Version>]
 [-ReleaseNotes <String[]>] [-Tags <String[]>] [-LicenseUri <Uri>] [-IconUri <Uri>]
 [-ProjectUri <Uri>] [-Exclude <String[]>] [-Force] [-AllowPrerelease] [-SkipAutomaticTags]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="633fb-107">ModulePathParameterSet</span><span class="sxs-lookup"><span data-stu-id="633fb-107">ModulePathParameterSet</span></span>

```
Publish-Module -Path <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-FormatVersion <Version>] [-ReleaseNotes <String[]>]
 [-Tags <String[]>] [-LicenseUri <Uri>] [-IconUri <Uri>] [-ProjectUri <Uri>] [-Force]
 [-SkipAutomaticTags] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="633fb-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="633fb-108">DESCRIPTION</span></span>

<span data-ttu-id="633fb-109">O `Publish-Module` cmdlet publica um módulo em uma galeria online baseada em NuGet usando uma chave de API, armazenada como parte do perfil de um usuário na galeria.</span><span class="sxs-lookup"><span data-stu-id="633fb-109">The `Publish-Module` cmdlet publishes a module to an online NuGet-based gallery by using an API key, stored as part of a user's profile in the gallery.</span></span> <span data-ttu-id="633fb-110">Você pode especificar o módulo a ser publicado usando o nome do módulo ou o caminho para a pasta que contém o módulo.</span><span class="sxs-lookup"><span data-stu-id="633fb-110">You can specify the module to publish either by the module's name, or by the path to the folder containing the module.</span></span>

<span data-ttu-id="633fb-111">Quando você especifica um módulo por nome, `Publish-Module` o publica o primeiro módulo que seria encontrado executando `Get-Module -ListAvailable <Name>` .</span><span class="sxs-lookup"><span data-stu-id="633fb-111">When you specify a module by name, `Publish-Module` publishes the first module that would be found by running `Get-Module -ListAvailable <Name>`.</span></span> <span data-ttu-id="633fb-112">Se você especificar uma versão mínima de um módulo a ser publicado, `Publish-Module` o publicará o primeiro módulo com uma versão maior ou igual à versão mínima que você especificou.</span><span class="sxs-lookup"><span data-stu-id="633fb-112">If you specify a minimum version of a module to publish, `Publish-Module` publishes the first module with a version that is greater than or equal to the minimum version that you have specified.</span></span>

<span data-ttu-id="633fb-113">A publicação de um módulo requer metadados que são exibidos na página da galeria para o módulo.</span><span class="sxs-lookup"><span data-stu-id="633fb-113">Publishing a module requires metadata that is displayed on the gallery page for the module.</span></span> <span data-ttu-id="633fb-114">Os metadados necessários incluem o nome, a versão, a descrição e o autor do módulo.</span><span class="sxs-lookup"><span data-stu-id="633fb-114">Required metadata includes the module name, version, description, and author.</span></span> <span data-ttu-id="633fb-115">Embora a maioria dos metadados seja obtida do manifesto do módulo, alguns metadados devem ser especificados em `Publish-Module` parâmetros, como **tag**, **ReleaseNote**, **IconUri**, **ProjectUri** e **LicenseUri**, porque esses parâmetros correspondem aos campos em uma galeria baseada em NuGet.</span><span class="sxs-lookup"><span data-stu-id="633fb-115">Although most metadata is taken from the module manifest, some metadata must be specified in `Publish-Module` parameters, such as **Tag**, **ReleaseNote**, **IconUri**, **ProjectUri**, and **LicenseUri**, because these parameters match fields in a NuGet-based gallery.</span></span>

## <span data-ttu-id="633fb-116">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="633fb-116">EXAMPLES</span></span>

### <span data-ttu-id="633fb-117">Exemplo 1: publicar um módulo</span><span class="sxs-lookup"><span data-stu-id="633fb-117">Example 1: Publish a module</span></span>

<span data-ttu-id="633fb-118">Neste exemplo, MyDscModule é publicado na galeria online usando a chave de API para indicar a conta da galeria online do proprietário do módulo.</span><span class="sxs-lookup"><span data-stu-id="633fb-118">In this example, MyDscModule is published to the online gallery by using the API key to indicate the module owner's online gallery account.</span></span> <span data-ttu-id="633fb-119">Se MyDscModule não for um módulo de manifesto válido que especifica um nome, versão, descrição e autor, ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="633fb-119">If MyDscModule is not a valid manifest module that specifies a name, version, description, and author, an error occurs.</span></span>

```powershell
Publish-Module -Name "MyDscModule" -NuGetApiKey "11e4b435-6cb4-4bf7-8611-5162ed75eb73"
```

### <span data-ttu-id="633fb-120">Exemplo 2: publicar um módulo com metadados da Galeria</span><span class="sxs-lookup"><span data-stu-id="633fb-120">Example 2: Publish a module with gallery metadata</span></span>

<span data-ttu-id="633fb-121">Neste exemplo, MyDscModule é publicado na galeria online usando a chave de API para indicar a conta da galeria do proprietário do módulo.</span><span class="sxs-lookup"><span data-stu-id="633fb-121">In this example, MyDscModule is published to the online gallery by using the API key to indicate the module owner's gallery account.</span></span> <span data-ttu-id="633fb-122">Os metadados adicionais fornecidos são exibidos na página da Web para o módulo na galeria.</span><span class="sxs-lookup"><span data-stu-id="633fb-122">The additional metadata provided is displayed on the webpage for the module in the gallery.</span></span> <span data-ttu-id="633fb-123">O proprietário adiciona duas marcas de pesquisa para o módulo, relacionando-o a Active Directory; uma breve nota de versão é adicionada.</span><span class="sxs-lookup"><span data-stu-id="633fb-123">The owner adds two search tags for the module, relating it to Active Directory; a brief release note is added.</span></span> <span data-ttu-id="633fb-124">Se MyDscModule não for um módulo de manifesto válido que especifica um nome, versão, descrição e autor, ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="633fb-124">If MyDscModule is not a valid manifest module that specifies a name, version, description, and author, an error occurs.</span></span>

```powershell
Publish-Module -Name "MyDscModule" -NuGetApiKey "11e4b435-6cb4-4bf7-8611-5162ed75eb73" -LicenseUri "http://contoso.com/license" -Tag "Active Directory","DSC" -ReleaseNote "Updated the ActiveDirectory DSC Resources to support adding users."
```

## <span data-ttu-id="633fb-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="633fb-125">PARAMETERS</span></span>

### <span data-ttu-id="633fb-126">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="633fb-126">-AllowPrerelease</span></span>

<span data-ttu-id="633fb-127">Permite que os módulos marcados como pré-lançamento sejam publicados.</span><span class="sxs-lookup"><span data-stu-id="633fb-127">Allows modules marked as prerelease to be published.</span></span>

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

### <span data-ttu-id="633fb-128">-Confirm</span><span class="sxs-lookup"><span data-stu-id="633fb-128">-Confirm</span></span>

<span data-ttu-id="633fb-129">Solicita a confirmação antes de executar o `Publish-Module` .</span><span class="sxs-lookup"><span data-stu-id="633fb-129">Prompts you for confirmation before running the `Publish-Module`.</span></span>

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

### <span data-ttu-id="633fb-130">-Credential</span><span class="sxs-lookup"><span data-stu-id="633fb-130">-Credential</span></span>

<span data-ttu-id="633fb-131">Especifica uma conta de usuário que tem direitos para publicar um módulo para um provedor de pacote ou origem especificado.</span><span class="sxs-lookup"><span data-stu-id="633fb-131">Specifies a user account that has rights to publish a module for a specified package provider or source.</span></span>

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

### <span data-ttu-id="633fb-132">-Excluir</span><span class="sxs-lookup"><span data-stu-id="633fb-132">-Exclude</span></span>

<span data-ttu-id="633fb-133">Define os arquivos a serem excluídos do módulo publicado.</span><span class="sxs-lookup"><span data-stu-id="633fb-133">Defines files to exclude from the published module.</span></span>

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

### <span data-ttu-id="633fb-134">-Force</span><span class="sxs-lookup"><span data-stu-id="633fb-134">-Force</span></span>

<span data-ttu-id="633fb-135">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="633fb-135">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="633fb-136">-FormatVersion</span><span class="sxs-lookup"><span data-stu-id="633fb-136">-FormatVersion</span></span>

<span data-ttu-id="633fb-137">Aceita somente valores válidos especificados pelo atributo **ValidateSet** .</span><span class="sxs-lookup"><span data-stu-id="633fb-137">Accepts only valid values specified by the **ValidateSet** attribute.</span></span>

<span data-ttu-id="633fb-138">Para obter mais informações, consulte [declaração de atributo ValidateSet](/powershell/scripting/developer/cmdlet/validateset-attribute-declaration) e [ValidateSetAttribute](/dotnet/api/system.management.automation.validatesetattribute).</span><span class="sxs-lookup"><span data-stu-id="633fb-138">For more information, see [ValidateSet Attribute Declaration](/powershell/scripting/developer/cmdlet/validateset-attribute-declaration) and [ValidateSetAttribute](/dotnet/api/system.management.automation.validatesetattribute).</span></span>

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

### <span data-ttu-id="633fb-139">-IconUri</span><span class="sxs-lookup"><span data-stu-id="633fb-139">-IconUri</span></span>

<span data-ttu-id="633fb-140">Especifica a URL de um ícone para o módulo.</span><span class="sxs-lookup"><span data-stu-id="633fb-140">Specifies the URL of an icon for the module.</span></span> <span data-ttu-id="633fb-141">O ícone especificado é exibido na página da Web Galeria do módulo.</span><span class="sxs-lookup"><span data-stu-id="633fb-141">The specified icon is displayed on the gallery webpage for the module.</span></span>

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

### <span data-ttu-id="633fb-142">-LicenseUri</span><span class="sxs-lookup"><span data-stu-id="633fb-142">-LicenseUri</span></span>

<span data-ttu-id="633fb-143">Especifica a URL dos termos de licenciamento para o módulo que você deseja publicar.</span><span class="sxs-lookup"><span data-stu-id="633fb-143">Specifies the URL of licensing terms for the module you want to publish.</span></span>

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

### <span data-ttu-id="633fb-144">-Name</span><span class="sxs-lookup"><span data-stu-id="633fb-144">-Name</span></span>

<span data-ttu-id="633fb-145">Especifica o nome do módulo que você deseja publicar.</span><span class="sxs-lookup"><span data-stu-id="633fb-145">Specifies the name of the module that you want to publish.</span></span> <span data-ttu-id="633fb-146">`Publish-Module` pesquisa o nome do módulo especificado em `$Env:PSModulePath` .</span><span class="sxs-lookup"><span data-stu-id="633fb-146">`Publish-Module` searches for the specified module name in `$Env:PSModulePath`.</span></span>

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

### <span data-ttu-id="633fb-147">-NuGetApiKey</span><span class="sxs-lookup"><span data-stu-id="633fb-147">-NuGetApiKey</span></span>

<span data-ttu-id="633fb-148">Especifica a chave de API que você deseja usar para publicar um módulo na galeria online.</span><span class="sxs-lookup"><span data-stu-id="633fb-148">Specifies the API key that you want to use to publish a module to the online gallery.</span></span> <span data-ttu-id="633fb-149">A chave de API é parte do seu perfil na galeria online e pode ser encontrada na página da sua conta de usuário na galeria.</span><span class="sxs-lookup"><span data-stu-id="633fb-149">The API key is part of your profile in the online gallery, and can be found on your user account page in the gallery.</span></span> <span data-ttu-id="633fb-150">A chave de API é uma funcionalidade específica do NuGet.</span><span class="sxs-lookup"><span data-stu-id="633fb-150">The API key is NuGet-specific functionality.</span></span>

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

### <span data-ttu-id="633fb-151">-Path</span><span class="sxs-lookup"><span data-stu-id="633fb-151">-Path</span></span>

<span data-ttu-id="633fb-152">Especifica o caminho para o módulo que você deseja publicar.</span><span class="sxs-lookup"><span data-stu-id="633fb-152">Specifies the path to the module that you want to publish.</span></span> <span data-ttu-id="633fb-153">Esse parâmetro aceita o caminho para a pasta que contém o módulo.</span><span class="sxs-lookup"><span data-stu-id="633fb-153">This parameter accepts the path to the folder that contains the module.</span></span>

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

### <span data-ttu-id="633fb-154">-ProjectUri</span><span class="sxs-lookup"><span data-stu-id="633fb-154">-ProjectUri</span></span>

<span data-ttu-id="633fb-155">Especifica a URL de uma página da Web sobre este projeto.</span><span class="sxs-lookup"><span data-stu-id="633fb-155">Specifies the URL of a webpage about this project.</span></span>

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

### <span data-ttu-id="633fb-156">-ReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="633fb-156">-ReleaseNotes</span></span>

<span data-ttu-id="633fb-157">Especifica uma cadeia de caracteres contendo notas de versão ou comentários que você deseja disponibilizar para os usuários desta versão do módulo.</span><span class="sxs-lookup"><span data-stu-id="633fb-157">Specifies a string containing release notes or comments that you want to be available to users of this version of the module.</span></span>

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

### <span data-ttu-id="633fb-158">-Repositório</span><span class="sxs-lookup"><span data-stu-id="633fb-158">-Repository</span></span>

<span data-ttu-id="633fb-159">Especifica o nome amigável de um repositório que foi registrado pela execução `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="633fb-159">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span> <span data-ttu-id="633fb-160">O repositório deve ter um **PublishLocation**, que é um URI NuGet válido.</span><span class="sxs-lookup"><span data-stu-id="633fb-160">The repository must have a **PublishLocation**, which is a valid NuGet URI.</span></span>
<span data-ttu-id="633fb-161">O **PublishLocation** pode ser definido executando `Set-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="633fb-161">The **PublishLocation** can be set by running `Set-PSRepository`.</span></span>

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

### <span data-ttu-id="633fb-162">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="633fb-162">-RequiredVersion</span></span>

<span data-ttu-id="633fb-163">Especifica a versão exata de um único módulo a ser publicado.</span><span class="sxs-lookup"><span data-stu-id="633fb-163">Specifies the exact version of a single module to publish.</span></span>

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

### <span data-ttu-id="633fb-164">-SkipAutomaticTags</span><span class="sxs-lookup"><span data-stu-id="633fb-164">-SkipAutomaticTags</span></span>

<span data-ttu-id="633fb-165">Remove comandos e recursos de serem incluídos como marcas.</span><span class="sxs-lookup"><span data-stu-id="633fb-165">Removes commands and resources from being included as tags.</span></span> <span data-ttu-id="633fb-166">Ignora a adição automática de marcas a um módulo.</span><span class="sxs-lookup"><span data-stu-id="633fb-166">Skips automatically adding tags to a module.</span></span>

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

### <span data-ttu-id="633fb-167">-Marcas</span><span class="sxs-lookup"><span data-stu-id="633fb-167">-Tags</span></span>

<span data-ttu-id="633fb-168">Adiciona uma ou mais marcas ao módulo que você está publicando.</span><span class="sxs-lookup"><span data-stu-id="633fb-168">Adds one or more tags to the module that you are publishing.</span></span> <span data-ttu-id="633fb-169">As marcas de exemplo incluem DesiredStateConfiguration, DSC, DSCResourceKit ou PSModule.</span><span class="sxs-lookup"><span data-stu-id="633fb-169">Example tags include DesiredStateConfiguration, DSC, DSCResourceKit, or PSModule.</span></span> <span data-ttu-id="633fb-170">Separe várias marcas com vírgulas.</span><span class="sxs-lookup"><span data-stu-id="633fb-170">Separate multiple tags with commas.</span></span>

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

### <span data-ttu-id="633fb-171">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="633fb-171">-WhatIf</span></span>

<span data-ttu-id="633fb-172">Mostra o que aconteceria se o `Publish-Module` for executado.</span><span class="sxs-lookup"><span data-stu-id="633fb-172">Shows what would happen if the `Publish-Module` runs.</span></span> <span data-ttu-id="633fb-173">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="633fb-173">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="633fb-174">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="633fb-174">CommonParameters</span></span>

<span data-ttu-id="633fb-175">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="633fb-175">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="633fb-176">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="633fb-176">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="633fb-177">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="633fb-177">INPUTS</span></span>

### <span data-ttu-id="633fb-178">System.String</span><span class="sxs-lookup"><span data-stu-id="633fb-178">System.String</span></span>

### <span data-ttu-id="633fb-179">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="633fb-179">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="633fb-180">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="633fb-180">OUTPUTS</span></span>

### <span data-ttu-id="633fb-181">System.Object</span><span class="sxs-lookup"><span data-stu-id="633fb-181">System.Object</span></span>

## <span data-ttu-id="633fb-182">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="633fb-182">NOTES</span></span>

<span data-ttu-id="633fb-183">`Publish-Module` é executado no PowerShell 3,0 ou versões posteriores do PowerShell, no Windows 7 ou Windows 2008 R2 e versões posteriores do Windows.</span><span class="sxs-lookup"><span data-stu-id="633fb-183">`Publish-Module` runs on PowerShell 3.0 or later releases of PowerShell, on Windows 7 or Windows 2008 R2 and later releases of Windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="633fb-184">A partir de abril de 2020, a Galeria do PowerShell não dará mais suporte às versões 1.0 e 1.1 do protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="633fb-184">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="633fb-185">Se você não estiver usando o TLS 1.2 ou posterior, receberá um erro ao tentar acessar a Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="633fb-185">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="633fb-186">Use o seguinte comando para garantir que esteja usando o TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="633fb-186">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="633fb-187">Para obter mais informações, confira o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="633fb-187">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

<span data-ttu-id="633fb-188">A publicação de um módulo requer metadados que são exibidos na página da galeria para o módulo.</span><span class="sxs-lookup"><span data-stu-id="633fb-188">Publishing a module requires metadata that is displayed on the gallery page for the module.</span></span> <span data-ttu-id="633fb-189">Os metadados necessários incluem o nome, a versão, a descrição e o autor do módulo.</span><span class="sxs-lookup"><span data-stu-id="633fb-189">Required metadata includes the module name, version, description, and author.</span></span> <span data-ttu-id="633fb-190">A maioria dos metadados é obtida do manifesto do módulo, mas alguns metadados podem ser especificados em `Publish-Module` parâmetros, como **tag**, **ReleaseNote**, **IconUri**, **ProjectUri** e **LicenseUri**.</span><span class="sxs-lookup"><span data-stu-id="633fb-190">Most metadata is taken from the module manifest, but some metadata can be specified in `Publish-Module` parameters, such as **Tag**, **ReleaseNote**, **IconUri**, **ProjectUri**, and **LicenseUri**.</span></span> <span data-ttu-id="633fb-191">Para obter mais informações, veja [valores de manifesto de pacote que afetam a interface do usuário do Galeria do PowerShell](/powershell/scripting/gallery/concepts/package-manifest-affecting-ui).</span><span class="sxs-lookup"><span data-stu-id="633fb-191">For more information, see [Package manifest values that impact the PowerShell Gallery UI](/powershell/scripting/gallery/concepts/package-manifest-affecting-ui).</span></span>

## <span data-ttu-id="633fb-192">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="633fb-192">RELATED LINKS</span></span>

[<span data-ttu-id="633fb-193">Find-Module</span><span class="sxs-lookup"><span data-stu-id="633fb-193">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="633fb-194">Install-Module</span><span class="sxs-lookup"><span data-stu-id="633fb-194">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="633fb-195">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="633fb-195">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="633fb-196">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="633fb-196">Set-PSRepository</span></span>](Set-PSRepository.md)

[<span data-ttu-id="633fb-197">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="633fb-197">Uninstall-Module</span></span>](Uninstall-Module.md)

[<span data-ttu-id="633fb-198">Update-Module</span><span class="sxs-lookup"><span data-stu-id="633fb-198">Update-Module</span></span>](Update-Module.md)
