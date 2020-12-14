---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/08/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-modulemanifest?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-ModuleManifest
ms.openlocfilehash: 2ad1f5991920cecf0a5b494bde698510c1c55b94
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94890797"
---
# <span data-ttu-id="aa0df-103">Update-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="aa0df-103">Update-ModuleManifest</span></span>

## <span data-ttu-id="aa0df-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="aa0df-104">SYNOPSIS</span></span>
<span data-ttu-id="aa0df-105">Atualiza um arquivo de manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="aa0df-105">Updates a module manifest file.</span></span>

## <span data-ttu-id="aa0df-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="aa0df-106">SYNTAX</span></span>

### <span data-ttu-id="aa0df-107">Tudo</span><span class="sxs-lookup"><span data-stu-id="aa0df-107">All</span></span>

```
Update-ModuleManifest [-Path] <String> [-NestedModules <Object[]>] [-Guid <Guid>] [-Author <String>]
 [-CompanyName <String>] [-Copyright <String>] [-RootModule <String>] [-ModuleVersion <Version>]
 [-Description <String>] [-ProcessorArchitecture <ProcessorArchitecture>]
 [-CompatiblePSEditions <String[]>] [-PowerShellVersion <Version>] [-ClrVersion <Version>]
 [-DotNetFrameworkVersion <Version>] [-PowerShellHostName <String>]
 [-PowerShellHostVersion <Version>] [-RequiredModules <Object[]>] [-TypesToProcess <String[]>]
 [-FormatsToProcess <String[]>] [-ScriptsToProcess <String[]>] [-RequiredAssemblies <String[]>]
 [-FileList <String[]>] [-ModuleList <Object[]>] [-FunctionsToExport <String[]>]
 [-AliasesToExport <String[]>] [-VariablesToExport <String[]>] [-CmdletsToExport <String[]>]
 [-DscResourcesToExport <String[]>] [-PrivateData <Hashtable>] [-Tags <String[]>]
 [-ProjectUri <Uri>] [-LicenseUri <Uri>] [-IconUri <Uri>] [-ReleaseNotes <String[]>]
 [-Prerelease <String>] [-HelpInfoUri <Uri>] [-PassThru] [-DefaultCommandPrefix <String>]
 [-ExternalModuleDependencies <String[]>] [-PackageManagementProviders <String[]>]
 [-RequireLicenseAcceptance] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="aa0df-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="aa0df-108">DESCRIPTION</span></span>

<span data-ttu-id="aa0df-109">O `Update-ModuleManifest` cmdlet atualiza um arquivo de manifesto de módulo ( `.psd1` ).</span><span class="sxs-lookup"><span data-stu-id="aa0df-109">The `Update-ModuleManifest` cmdlet updates a module manifest (`.psd1`) file.</span></span>

## <span data-ttu-id="aa0df-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="aa0df-110">EXAMPLES</span></span>

### <span data-ttu-id="aa0df-111">Exemplo 1: atualizar um manifesto de módulo</span><span class="sxs-lookup"><span data-stu-id="aa0df-111">Example 1: Update a module manifest</span></span>

<span data-ttu-id="aa0df-112">Este exemplo atualiza um arquivo de manifesto de módulo existente.</span><span class="sxs-lookup"><span data-stu-id="aa0df-112">This example updates an existing module manifest file.</span></span> <span data-ttu-id="aa0df-113">Nivelamento é usado para passar valores de parâmetro para `Update-ModuleManifest` .</span><span class="sxs-lookup"><span data-stu-id="aa0df-113">Splatting is used to pass parameter values to `Update-ModuleManifest`.</span></span> <span data-ttu-id="aa0df-114">Para obter mais informações, consulte [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="aa0df-114">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

```powershell
$Parms = @{
  Path = "C:\Test\TestManifest.psd1"
  Author = "TestUser1"
  CompanyName = "Contoso Corporation"
  Copyright = "(c) 2019 Contoso Corporation. All rights reserved."
}

Update-ModuleManifest @Parms
```

<span data-ttu-id="aa0df-115">`$Parms` é um fragmentação que armazena os valores de parâmetro para **caminho**, **autor**, **CompanyName** e **direitos autorais**.</span><span class="sxs-lookup"><span data-stu-id="aa0df-115">`$Parms` is a splat that stores the parameter values for **Path**, **Author**, **CompanyName**, and **Copyright**.</span></span> <span data-ttu-id="aa0df-116">`Update-ModuleManifest` Obtém os valores de parâmetro de `@Parms` e atualiza o manifesto do módulo, **TestManifest.psd1**.</span><span class="sxs-lookup"><span data-stu-id="aa0df-116">`Update-ModuleManifest` gets the parameter values from `@Parms` and updates the module manifest, **TestManifest.psd1**.</span></span>

## <span data-ttu-id="aa0df-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="aa0df-117">PARAMETERS</span></span>

### <span data-ttu-id="aa0df-118">-AliasesToExport</span><span class="sxs-lookup"><span data-stu-id="aa0df-118">-AliasesToExport</span></span>

<span data-ttu-id="aa0df-119">Especifica os aliases que o módulo exporta.</span><span class="sxs-lookup"><span data-stu-id="aa0df-119">Specifies the aliases that the module exports.</span></span> <span data-ttu-id="aa0df-120">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="aa0df-120">Wildcards are permitted.</span></span>

<span data-ttu-id="aa0df-121">Use esse parâmetro para restringir os aliases exportados pelo módulo.</span><span class="sxs-lookup"><span data-stu-id="aa0df-121">Use this parameter to restrict the aliases that are exported by the module.</span></span> <span data-ttu-id="aa0df-122">**AliasesToExport** pode remover aliases da lista de aliases exportados, mas não pode adicionar aliases à lista.</span><span class="sxs-lookup"><span data-stu-id="aa0df-122">**AliasesToExport** can remove aliases from the list of exported aliases, but it can't add aliases to the list.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="aa0df-123">-Autor</span><span class="sxs-lookup"><span data-stu-id="aa0df-123">-Author</span></span>

<span data-ttu-id="aa0df-124">Especifica o autor do módulo.</span><span class="sxs-lookup"><span data-stu-id="aa0df-124">Specifies the module author.</span></span>

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

### <span data-ttu-id="aa0df-125">-ClrVersion</span><span class="sxs-lookup"><span data-stu-id="aa0df-125">-ClrVersion</span></span>

<span data-ttu-id="aa0df-126">Especifica a versão mínima do CLR (Common Language Runtime) do Microsoft .NET Framework que o módulo exige.</span><span class="sxs-lookup"><span data-stu-id="aa0df-126">Specifies the minimum version of the Common Language Runtime (CLR) of the Microsoft .NET Framework that the module requires.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aa0df-127">-CmdletsToExport</span><span class="sxs-lookup"><span data-stu-id="aa0df-127">-CmdletsToExport</span></span>

<span data-ttu-id="aa0df-128">Especifica os cmdlets que o módulo exporta.</span><span class="sxs-lookup"><span data-stu-id="aa0df-128">Specifies the cmdlets that the module exports.</span></span> <span data-ttu-id="aa0df-129">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="aa0df-129">Wildcards are permitted.</span></span>

<span data-ttu-id="aa0df-130">Use esse parâmetro para restringir os cmdlets que são exportados pelo módulo.</span><span class="sxs-lookup"><span data-stu-id="aa0df-130">Use this parameter to restrict the cmdlets that are exported by the module.</span></span> <span data-ttu-id="aa0df-131">**CmdletsToExport** pode remover cmdlets da lista de cmdlets exportados, mas não pode adicionar cmdlets à lista.</span><span class="sxs-lookup"><span data-stu-id="aa0df-131">**CmdletsToExport** can remove cmdlets from the list of exported cmdlets, but it can't add cmdlets to the list.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="aa0df-132">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="aa0df-132">-CompanyName</span></span>

<span data-ttu-id="aa0df-133">Especifica a empresa ou o fornecedor que criou o módulo.</span><span class="sxs-lookup"><span data-stu-id="aa0df-133">Specifies the company or vendor who created the module.</span></span>

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

### <span data-ttu-id="aa0df-134">-CompatiblePSEditions</span><span class="sxs-lookup"><span data-stu-id="aa0df-134">-CompatiblePSEditions</span></span>

<span data-ttu-id="aa0df-135">Especifica o **PSEditions** compatível do módulo.</span><span class="sxs-lookup"><span data-stu-id="aa0df-135">Specifies the compatible **PSEditions** of the module.</span></span> <span data-ttu-id="aa0df-136">Para obter informações sobre **PSEdition**, consulte [módulos com as edições compatíveis do PowerShell](/powershell/scripting/gallery/concepts/module-psedition-support).</span><span class="sxs-lookup"><span data-stu-id="aa0df-136">For information about **PSEdition**, see [Modules with compatible PowerShell Editions](/powershell/scripting/gallery/concepts/module-psedition-support).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Desktop, Core

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aa0df-137">-Confirm</span><span class="sxs-lookup"><span data-stu-id="aa0df-137">-Confirm</span></span>

<span data-ttu-id="aa0df-138">Solicita a confirmação antes de executar `Update-ModuleManifest` .</span><span class="sxs-lookup"><span data-stu-id="aa0df-138">Prompts you for confirmation before running `Update-ModuleManifest`.</span></span>

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

### <span data-ttu-id="aa0df-139">-Direitos autorais</span><span class="sxs-lookup"><span data-stu-id="aa0df-139">-Copyright</span></span>

<span data-ttu-id="aa0df-140">Especifica uma declaração de direitos autorais do módulo.</span><span class="sxs-lookup"><span data-stu-id="aa0df-140">Specifies a copyright statement for the module.</span></span>

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

### <span data-ttu-id="aa0df-141">-DefaultCommandPrefix</span><span class="sxs-lookup"><span data-stu-id="aa0df-141">-DefaultCommandPrefix</span></span>

<span data-ttu-id="aa0df-142">Especifica o prefixo de comando padrão.</span><span class="sxs-lookup"><span data-stu-id="aa0df-142">Specifies the default command prefix.</span></span>

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

### <span data-ttu-id="aa0df-143">-Description</span><span class="sxs-lookup"><span data-stu-id="aa0df-143">-Description</span></span>

<span data-ttu-id="aa0df-144">Especifica uma descrição do módulo.</span><span class="sxs-lookup"><span data-stu-id="aa0df-144">Specifies a description of the module.</span></span>

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

### <span data-ttu-id="aa0df-145">-DotNetFrameworkVersion</span><span class="sxs-lookup"><span data-stu-id="aa0df-145">-DotNetFrameworkVersion</span></span>

<span data-ttu-id="aa0df-146">Especifica a versão mínima do Microsoft .NET Framework que o módulo exige.</span><span class="sxs-lookup"><span data-stu-id="aa0df-146">Specifies the minimum version of the Microsoft .NET Framework that the module requires.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aa0df-147">-DscResourcesToExport</span><span class="sxs-lookup"><span data-stu-id="aa0df-147">-DscResourcesToExport</span></span>

<span data-ttu-id="aa0df-148">Especifica os recursos de DSC (configuração de estado desejado) que o módulo exporta.</span><span class="sxs-lookup"><span data-stu-id="aa0df-148">Specifies the Desired State Configuration (DSC) resources that the module exports.</span></span> <span data-ttu-id="aa0df-149">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="aa0df-149">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="aa0df-150">-ExternalModuleDependencies</span><span class="sxs-lookup"><span data-stu-id="aa0df-150">-ExternalModuleDependencies</span></span>

<span data-ttu-id="aa0df-151">Especifica uma matriz de dependências de módulo externas.</span><span class="sxs-lookup"><span data-stu-id="aa0df-151">Specifies an array of external module dependencies.</span></span>

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

### <span data-ttu-id="aa0df-152">-FileList</span><span class="sxs-lookup"><span data-stu-id="aa0df-152">-FileList</span></span>

<span data-ttu-id="aa0df-153">Especifica todos os itens incluídos no módulo.</span><span class="sxs-lookup"><span data-stu-id="aa0df-153">Specifies all items that are included in the module.</span></span>

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

### <span data-ttu-id="aa0df-154">-FormatsToProcess</span><span class="sxs-lookup"><span data-stu-id="aa0df-154">-FormatsToProcess</span></span>

<span data-ttu-id="aa0df-155">Especifica os arquivos de formatação ( `.ps1xml` ) que são executados quando o módulo é importado.</span><span class="sxs-lookup"><span data-stu-id="aa0df-155">Specifies the formatting files (`.ps1xml`) that run when the module is imported.</span></span>

<span data-ttu-id="aa0df-156">Quando você importa um módulo, o PowerShell executa o `Update-FormatData` cmdlet com os arquivos especificados.</span><span class="sxs-lookup"><span data-stu-id="aa0df-156">When you import a module, PowerShell runs the `Update-FormatData` cmdlet with the specified files.</span></span>
<span data-ttu-id="aa0df-157">Como os arquivos de formatação não estão no escopo, eles afetam todos os Estados de sessão na sessão.</span><span class="sxs-lookup"><span data-stu-id="aa0df-157">Because formatting files aren't scoped, they affect all session states in the session.</span></span>

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

### <span data-ttu-id="aa0df-158">-FunctionsToExport</span><span class="sxs-lookup"><span data-stu-id="aa0df-158">-FunctionsToExport</span></span>

<span data-ttu-id="aa0df-159">Especifica as funções que o módulo exporta.</span><span class="sxs-lookup"><span data-stu-id="aa0df-159">Specifies the functions that the module exports.</span></span> <span data-ttu-id="aa0df-160">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="aa0df-160">Wildcards are permitted.</span></span>

<span data-ttu-id="aa0df-161">Use esse parâmetro para restringir as funções exportadas pelo módulo.</span><span class="sxs-lookup"><span data-stu-id="aa0df-161">Use this parameter to restrict the functions that are exported by the module.</span></span> <span data-ttu-id="aa0df-162">**FunctionsToExport** pode remover funções da lista de aliases exportados, mas não pode adicionar funções à lista.</span><span class="sxs-lookup"><span data-stu-id="aa0df-162">**FunctionsToExport** can remove functions from the list of exported aliases, but it can't add functions to the list.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="aa0df-163">-GUID</span><span class="sxs-lookup"><span data-stu-id="aa0df-163">-Guid</span></span>

<span data-ttu-id="aa0df-164">Especifica um identificador exclusivo para o módulo.</span><span class="sxs-lookup"><span data-stu-id="aa0df-164">Specifies a unique identifier for the module.</span></span> <span data-ttu-id="aa0df-165">O GUID pode ser usado para distinguir entre módulos com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="aa0df-165">The GUID can be used to distinguish among modules with the same name.</span></span>

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aa0df-166">-HelpInfoUri</span><span class="sxs-lookup"><span data-stu-id="aa0df-166">-HelpInfoUri</span></span>

<span data-ttu-id="aa0df-167">Especifica o endereço da Internet do arquivo **XML HelpInfo** do módulo.</span><span class="sxs-lookup"><span data-stu-id="aa0df-167">Specifies the internet address of the module's **HelpInfo XML** file.</span></span> <span data-ttu-id="aa0df-168">Insira um Uniform Resource Identifier (URI) que comece com **http** ou **https**.</span><span class="sxs-lookup"><span data-stu-id="aa0df-168">Enter a Uniform Resource Identifier (URI) that begins with **http** or **https**.</span></span>

<span data-ttu-id="aa0df-169">O arquivo **XML HelpInfo** dá suporte ao recurso de ajuda atualizável que foi introduzido no PowerShell versão 3,0.</span><span class="sxs-lookup"><span data-stu-id="aa0df-169">The **HelpInfo XML** file supports the Updatable Help feature that was introduced in PowerShell version 3.0.</span></span> <span data-ttu-id="aa0df-170">Ele contém informações sobre o local dos arquivos de ajuda baixáveis do módulo e os números de versão dos arquivos de ajuda mais recentes para cada localidade com suporte.</span><span class="sxs-lookup"><span data-stu-id="aa0df-170">It contains information about the location of the module's downloadable help files and the version numbers of the newest help files for each supported locale.</span></span>

<span data-ttu-id="aa0df-171">Para obter informações sobre a ajuda atualizável, consulte [about_Updatable_Help](../Microsoft.PowerShell.Core/About/about_Updatable_Help.md).</span><span class="sxs-lookup"><span data-stu-id="aa0df-171">For information about Updatable Help, see [about_Updatable_Help](../Microsoft.PowerShell.Core/About/about_Updatable_Help.md).</span></span>
<span data-ttu-id="aa0df-172">Para obter informações sobre o arquivo **XML HelpInfo** , consulte [suporte à ajuda atualizável](/powershell/scripting/developer/module/supporting-updatable-help).</span><span class="sxs-lookup"><span data-stu-id="aa0df-172">For information about the **HelpInfo XML** file, see [Supporting Updatable Help](/powershell/scripting/developer/module/supporting-updatable-help).</span></span>

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

### <span data-ttu-id="aa0df-173">-IconUri</span><span class="sxs-lookup"><span data-stu-id="aa0df-173">-IconUri</span></span>

<span data-ttu-id="aa0df-174">Especifica a URL de um ícone para o módulo.</span><span class="sxs-lookup"><span data-stu-id="aa0df-174">Specifies the URL of an icon for the module.</span></span> <span data-ttu-id="aa0df-175">O ícone especificado é exibido na página da Galeria da Web para o módulo.</span><span class="sxs-lookup"><span data-stu-id="aa0df-175">The specified icon is displayed on the gallery web page for the module.</span></span>

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

### <span data-ttu-id="aa0df-176">-LicenseUri</span><span class="sxs-lookup"><span data-stu-id="aa0df-176">-LicenseUri</span></span>

<span data-ttu-id="aa0df-177">Especifica a URL dos termos de licenciamento do módulo.</span><span class="sxs-lookup"><span data-stu-id="aa0df-177">Specifies the URL of licensing terms for the module.</span></span>

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

### <span data-ttu-id="aa0df-178">-ModuleList</span><span class="sxs-lookup"><span data-stu-id="aa0df-178">-ModuleList</span></span>

<span data-ttu-id="aa0df-179">Especifica uma matriz de módulos que são incluídos no módulo.</span><span class="sxs-lookup"><span data-stu-id="aa0df-179">Specifies an array of modules that are included in the module.</span></span>

<span data-ttu-id="aa0df-180">Insira o nome de cada módulo como uma cadeia de caracteres ou uma tabela de hash com as chaves **ModuleName** e **ModuleVersion**.</span><span class="sxs-lookup"><span data-stu-id="aa0df-180">Enter each module name as a string or as a hash table with **ModuleName** and **ModuleVersion** keys.</span></span> <span data-ttu-id="aa0df-181">A tabela de hash também pode ter uma chave **GUID** opcional.</span><span class="sxs-lookup"><span data-stu-id="aa0df-181">The hash table can also have an optional **GUID** key.</span></span> <span data-ttu-id="aa0df-182">Você pode combinar cadeias de caracteres e tabelas de hash no valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="aa0df-182">You can combine strings and hash tables in the parameter value.</span></span>

<span data-ttu-id="aa0df-183">Essa chave foi projetada para atuar como um inventário de módulo.</span><span class="sxs-lookup"><span data-stu-id="aa0df-183">This key is designed to act as a module inventory.</span></span> <span data-ttu-id="aa0df-184">Os módulos listados no valor dessa chave não são processados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="aa0df-184">The modules that are listed in the value of this key aren't automatically processed.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aa0df-185">-ModuleVersion</span><span class="sxs-lookup"><span data-stu-id="aa0df-185">-ModuleVersion</span></span>

<span data-ttu-id="aa0df-186">Especifica a versão do módulo.</span><span class="sxs-lookup"><span data-stu-id="aa0df-186">Specifies the version of the module.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aa0df-187">-NestedModules</span><span class="sxs-lookup"><span data-stu-id="aa0df-187">-NestedModules</span></span>

<span data-ttu-id="aa0df-188">Especifica módulos de script ( `.psm1` ) e módulos binários ( `.dll` ) que são importados para o estado de sessão do módulo.</span><span class="sxs-lookup"><span data-stu-id="aa0df-188">Specifies script modules (`.psm1`) and binary modules (`.dll`) that are imported into the module's session state.</span></span> <span data-ttu-id="aa0df-189">Os arquivos na chave **NestedModules** são executados na ordem em que estão listados no valor.</span><span class="sxs-lookup"><span data-stu-id="aa0df-189">The files in the **NestedModules** key run in the order in which they're listed in the value.</span></span>

<span data-ttu-id="aa0df-190">Insira o nome de cada módulo como uma cadeia de caracteres ou uma tabela de hash com as chaves **ModuleName** e **ModuleVersion**.</span><span class="sxs-lookup"><span data-stu-id="aa0df-190">Enter each module name as a string or as a hash table with **ModuleName** and **ModuleVersion** keys.</span></span> <span data-ttu-id="aa0df-191">A tabela de hash também pode ter uma chave **GUID** opcional.</span><span class="sxs-lookup"><span data-stu-id="aa0df-191">The hash table can also have an optional **GUID** key.</span></span> <span data-ttu-id="aa0df-192">Você pode combinar cadeias de caracteres e tabelas de hash no valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="aa0df-192">You can combine strings and hash tables in the parameter value.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aa0df-193">-PackageManagementProviders</span><span class="sxs-lookup"><span data-stu-id="aa0df-193">-PackageManagementProviders</span></span>

<span data-ttu-id="aa0df-194">Especifica uma matriz de provedores de gerenciamento de pacotes.</span><span class="sxs-lookup"><span data-stu-id="aa0df-194">Specifies an array of package management providers.</span></span>

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

### <span data-ttu-id="aa0df-195">-PassThru</span><span class="sxs-lookup"><span data-stu-id="aa0df-195">-PassThru</span></span>

<span data-ttu-id="aa0df-196">Retorna um objeto que representa o item com o qual você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="aa0df-196">Returns an object representing the item with which you're working.</span></span> <span data-ttu-id="aa0df-197">Por padrão, o `Update-ModuleManifest` não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="aa0df-197">By default, `Update-ModuleManifest` doesn't generate any output.</span></span>

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

### <span data-ttu-id="aa0df-198">-Path</span><span class="sxs-lookup"><span data-stu-id="aa0df-198">-Path</span></span>

<span data-ttu-id="aa0df-199">Especifica o caminho e o nome do arquivo do manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="aa0df-199">Specifies the path and file name of the module manifest.</span></span> <span data-ttu-id="aa0df-200">Insira um caminho e um nome de arquivo com uma `.psd1` extensão de nome de arquivo, como `$PSHOME\Modules\MyModule\MyModule.psd1` .</span><span class="sxs-lookup"><span data-stu-id="aa0df-200">Enter a path and file name with a `.psd1` file name extension, such as `$PSHOME\Modules\MyModule\MyModule.psd1`.</span></span>

<span data-ttu-id="aa0df-201">Se você especificar o caminho para um arquivo existente, `Update-ModuleManifest` o substituirá o arquivo sem aviso, a menos que o arquivo tenha o atributo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="aa0df-201">If you specify the path to an existing file, `Update-ModuleManifest` replaces the file without warning unless the file has the read-only attribute.</span></span>

<span data-ttu-id="aa0df-202">O manifesto deve estar localizado no diretório do módulo e o nome do arquivo de manifesto deve ser o mesmo que o nome do diretório do módulo, mas com uma `.psd1` extensão.</span><span class="sxs-lookup"><span data-stu-id="aa0df-202">The manifest should be located in the module's directory, and the manifest file name should be the same as the module directory name, but with a `.psd1` extension.</span></span>

<span data-ttu-id="aa0df-203">Você não pode usar variáveis, como `$PSHOME` ou `$HOME` , em resposta a um prompt para um valor de parâmetro de **caminho** .</span><span class="sxs-lookup"><span data-stu-id="aa0df-203">You can't use variables, such as `$PSHOME` or `$HOME`, in response to a prompt for a **Path** parameter value.</span></span> <span data-ttu-id="aa0df-204">Para usar uma variável, inclua o parâmetro **Path** no comando.</span><span class="sxs-lookup"><span data-stu-id="aa0df-204">To use a variable, include the **Path** parameter in the command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="aa0df-205">-PowerShellHostName</span><span class="sxs-lookup"><span data-stu-id="aa0df-205">-PowerShellHostName</span></span>

<span data-ttu-id="aa0df-206">Especifica o nome do programa de host do PowerShell que o módulo requer.</span><span class="sxs-lookup"><span data-stu-id="aa0df-206">Specifies the name of the PowerShell host program that the module requires.</span></span> <span data-ttu-id="aa0df-207">Insira o nome do programa host, como o host do ISE do PowerShell ou ConsoleHost.</span><span class="sxs-lookup"><span data-stu-id="aa0df-207">Enter the name of the host program, such as PowerShell ISE Host or ConsoleHost.</span></span> <span data-ttu-id="aa0df-208">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="aa0df-208">Wildcards aren't permitted.</span></span>

<span data-ttu-id="aa0df-209">Para localizar o nome de um programa de host, no programa, digite `$Host.Name` .</span><span class="sxs-lookup"><span data-stu-id="aa0df-209">To find the name of a host program, in the program, type `$Host.Name`.</span></span>

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

### <span data-ttu-id="aa0df-210">-PowerShellHostVersion</span><span class="sxs-lookup"><span data-stu-id="aa0df-210">-PowerShellHostVersion</span></span>

<span data-ttu-id="aa0df-211">Especifica a versão mínima do programa de host do PowerShell que funciona com o módulo.</span><span class="sxs-lookup"><span data-stu-id="aa0df-211">Specifies the minimum version of the PowerShell host program that works with the module.</span></span> <span data-ttu-id="aa0df-212">Insira um número de versão, como 1.1.</span><span class="sxs-lookup"><span data-stu-id="aa0df-212">Enter a version number, such as 1.1.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aa0df-213">-PowerShellVersion</span><span class="sxs-lookup"><span data-stu-id="aa0df-213">-PowerShellVersion</span></span>

<span data-ttu-id="aa0df-214">Especifica a versão mínima do PowerShell que funcionará com este módulo.</span><span class="sxs-lookup"><span data-stu-id="aa0df-214">Specifies the minimum version of PowerShell that will work with this module.</span></span> <span data-ttu-id="aa0df-215">Por exemplo, você pode especificar 3,0, 4,0 ou 5,0 como o valor desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="aa0df-215">For example, you can specify 3.0, 4.0, or 5.0 as the value of this parameter.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aa0df-216">-Pré-lançamento</span><span class="sxs-lookup"><span data-stu-id="aa0df-216">-Prerelease</span></span>

<span data-ttu-id="aa0df-217">Indica que o módulo é de pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="aa0df-217">Indicates the module is prerelease.</span></span>

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

### <span data-ttu-id="aa0df-218">-PrivateData</span><span class="sxs-lookup"><span data-stu-id="aa0df-218">-PrivateData</span></span>

<span data-ttu-id="aa0df-219">Especifica os dados que são passados para o módulo quando ele é importado.</span><span class="sxs-lookup"><span data-stu-id="aa0df-219">Specifies data that is passed to the module when it's imported.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aa0df-220">-ProcessorArchitecture</span><span class="sxs-lookup"><span data-stu-id="aa0df-220">-ProcessorArchitecture</span></span>

<span data-ttu-id="aa0df-221">Especifica a arquitetura do processador que o módulo requer.</span><span class="sxs-lookup"><span data-stu-id="aa0df-221">Specifies the processor architecture that the module requires.</span></span>

<span data-ttu-id="aa0df-222">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="aa0df-222">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="aa0df-223">AMD64</span><span class="sxs-lookup"><span data-stu-id="aa0df-223">Amd64</span></span>
- <span data-ttu-id="aa0df-224">Arm</span><span class="sxs-lookup"><span data-stu-id="aa0df-224">Arm</span></span>
- <span data-ttu-id="aa0df-225">IA64</span><span class="sxs-lookup"><span data-stu-id="aa0df-225">IA64</span></span>
- <span data-ttu-id="aa0df-226">MSIL</span><span class="sxs-lookup"><span data-stu-id="aa0df-226">MSIL</span></span>
- <span data-ttu-id="aa0df-227">Nenhum (desconhecido ou não especificado)</span><span class="sxs-lookup"><span data-stu-id="aa0df-227">None (unknown or unspecified)</span></span>
- <span data-ttu-id="aa0df-228">X86</span><span class="sxs-lookup"><span data-stu-id="aa0df-228">X86</span></span>

```yaml
Type: System.Reflection.ProcessorArchitecture
Parameter Sets: (All)
Aliases:
Accepted values: None, MSIL, X86, IA64, Amd64, Arm

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aa0df-229">-ProjectUri</span><span class="sxs-lookup"><span data-stu-id="aa0df-229">-ProjectUri</span></span>

<span data-ttu-id="aa0df-230">Especifica a URL de uma página da Web sobre este projeto.</span><span class="sxs-lookup"><span data-stu-id="aa0df-230">Specifies the URL of a web page about this project.</span></span>

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

### <span data-ttu-id="aa0df-231">-ReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="aa0df-231">-ReleaseNotes</span></span>

<span data-ttu-id="aa0df-232">Especifica uma matriz de cadeia de caracteres que contém notas de versão ou comentários que você deseja disponibilizar para esta versão do script.</span><span class="sxs-lookup"><span data-stu-id="aa0df-232">Specifies a string array that contains release notes or comments that you want available for this version of the script.</span></span>

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

### <span data-ttu-id="aa0df-233">-RequiredAssemblies</span><span class="sxs-lookup"><span data-stu-id="aa0df-233">-RequiredAssemblies</span></span>

<span data-ttu-id="aa0df-234">Especifica os arquivos de assembly ( `.dll` ) que o módulo requer.</span><span class="sxs-lookup"><span data-stu-id="aa0df-234">Specifies the assembly (`.dll`) files that the module requires.</span></span> <span data-ttu-id="aa0df-235">Digite os nomes de arquivo de assembly.</span><span class="sxs-lookup"><span data-stu-id="aa0df-235">Enter the assembly file names.</span></span>
<span data-ttu-id="aa0df-236">O PowerShell carrega os assemblies especificados antes de atualizar os tipos ou formatos, importando módulos aninhados ou importando o arquivo de módulo especificado no valor da chave **RootModule** .</span><span class="sxs-lookup"><span data-stu-id="aa0df-236">PowerShell loads the specified assemblies before updating types or formats, importing nested modules, or importing the module file that is specified in the value of the **RootModule** key.</span></span>

<span data-ttu-id="aa0df-237">Use esse parâmetro para especificar todos os assemblies que o módulo requer, incluindo assemblies que devem ser carregados para atualizar qualquer formatação ou arquivos de tipo listados nas chaves **FormatsToProcess** ou **TypesToProcess** , mesmo se esses assemblies também estiverem listados como módulos binários na chave **NestedModules** .</span><span class="sxs-lookup"><span data-stu-id="aa0df-237">Use this parameter to specify all the assemblies that the module requires, including assemblies that must be loaded to update any formatting or type files that are listed in the **FormatsToProcess** or **TypesToProcess** keys, even if those assemblies are also listed as binary modules in the **NestedModules** key.</span></span>

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

### <span data-ttu-id="aa0df-238">-RequiredModules</span><span class="sxs-lookup"><span data-stu-id="aa0df-238">-RequiredModules</span></span>

<span data-ttu-id="aa0df-239">Especifica os módulos que devem estar no estado de sessão global.</span><span class="sxs-lookup"><span data-stu-id="aa0df-239">Specifies modules that must be in the global session state.</span></span> <span data-ttu-id="aa0df-240">Se os módulos necessários não estiverem no estado de sessão global, o PowerShell os importará.</span><span class="sxs-lookup"><span data-stu-id="aa0df-240">If the required modules aren't in the global session state, PowerShell imports them.</span></span> <span data-ttu-id="aa0df-241">Se os módulos necessários não estiverem disponíveis, o `Import-Module` comando falhará.</span><span class="sxs-lookup"><span data-stu-id="aa0df-241">If the required modules aren't available, the `Import-Module` command fails.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aa0df-242">-RequireLicenseAcceptance</span><span class="sxs-lookup"><span data-stu-id="aa0df-242">-RequireLicenseAcceptance</span></span>

<span data-ttu-id="aa0df-243">Especifica que uma aceitação de licença é necessária para o módulo.</span><span class="sxs-lookup"><span data-stu-id="aa0df-243">Specifies that a license acceptance is required for the module.</span></span>

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

### <span data-ttu-id="aa0df-244">-RootModule</span><span class="sxs-lookup"><span data-stu-id="aa0df-244">-RootModule</span></span>

<span data-ttu-id="aa0df-245">Especifica o arquivo primário ou raiz do módulo.</span><span class="sxs-lookup"><span data-stu-id="aa0df-245">Specifies the primary or root file of the module.</span></span> <span data-ttu-id="aa0df-246">Insira o nome de arquivo de um script ( `.ps1` ), um módulo de script ( `.psm1` ), um manifesto de módulo ( `.psd1` ), um assembly ( `.dll` ), um arquivo XML de definição de cmdlet ( `.cdxml` ) ou um fluxo de trabalho ( `.xaml` ).</span><span class="sxs-lookup"><span data-stu-id="aa0df-246">Enter the file name of a script (`.ps1`), a script module (`.psm1`), a module manifest (`.psd1`), an assembly (`.dll`), a cmdlet definition XML file (`.cdxml`), or a workflow (`.xaml`).</span></span> <span data-ttu-id="aa0df-247">Quando o módulo é importado, os membros que são exportados do arquivo do módulo raiz são importados para o estado de sessão do chamador.</span><span class="sxs-lookup"><span data-stu-id="aa0df-247">When the module is imported, the members that are exported from the root module file are imported into the caller's session state.</span></span>

<span data-ttu-id="aa0df-248">Se um módulo tiver um arquivo de manifesto e nenhum arquivo raiz tiver sido especificado na chave **RootModule** , o manifesto se tornará o arquivo primário do módulo.</span><span class="sxs-lookup"><span data-stu-id="aa0df-248">If a module has a manifest file and no root file has been specified in the **RootModule** key, the manifest becomes the primary file for the module.</span></span> <span data-ttu-id="aa0df-249">E, o módulo torna-se um módulo de manifesto (Módulotype = manifesto).</span><span class="sxs-lookup"><span data-stu-id="aa0df-249">And, the module becomes a manifest module (ModuleType = Manifest).</span></span>

<span data-ttu-id="aa0df-250">Para exportar membros de `.psm1` ou `.dll` arquivos em um módulo que tenha um manifesto, os nomes desses arquivos devem ser especificados nos valores das chaves **RootModule** ou **NestedModules** no manifesto.</span><span class="sxs-lookup"><span data-stu-id="aa0df-250">To export members from `.psm1` or `.dll` files in a module that has a manifest, the names of those files must be specified in the values of the **RootModule** or **NestedModules** keys in the manifest.</span></span> <span data-ttu-id="aa0df-251">Caso contrário, seus membros não serão exportados.</span><span class="sxs-lookup"><span data-stu-id="aa0df-251">Otherwise, their members aren't exported.</span></span>

<span data-ttu-id="aa0df-252">No PowerShell 2,0, essa chave foi chamada de **ModuleToProcess**.</span><span class="sxs-lookup"><span data-stu-id="aa0df-252">In PowerShell 2.0, this key was called **ModuleToProcess**.</span></span>

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

### <span data-ttu-id="aa0df-253">-ScriptsToProcess</span><span class="sxs-lookup"><span data-stu-id="aa0df-253">-ScriptsToProcess</span></span>

<span data-ttu-id="aa0df-254">Especifica os arquivos de script ( `.ps1` ) que são executados no estado de sessão do chamador quando o módulo é importado.</span><span class="sxs-lookup"><span data-stu-id="aa0df-254">Specifies script (`.ps1`) files that run in the caller's session state when the module is imported.</span></span>
<span data-ttu-id="aa0df-255">Você pode usar esses scripts para preparar um ambiente, assim como você pode usar um script de logon.</span><span class="sxs-lookup"><span data-stu-id="aa0df-255">You can use these scripts to prepare an environment, just as you might use a login script.</span></span>

<span data-ttu-id="aa0df-256">Para especificar scripts que são executados no estado de sessão do módulo, use a chave **NestedModules**.</span><span class="sxs-lookup"><span data-stu-id="aa0df-256">To specify scripts that run in the module's session state, use the **NestedModules** key.</span></span>

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

### <span data-ttu-id="aa0df-257">-Marcas</span><span class="sxs-lookup"><span data-stu-id="aa0df-257">-Tags</span></span>

<span data-ttu-id="aa0df-258">Especifica uma matriz de marcas.</span><span class="sxs-lookup"><span data-stu-id="aa0df-258">Specifies an array of tags.</span></span>

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

### <span data-ttu-id="aa0df-259">-TypesToProcess</span><span class="sxs-lookup"><span data-stu-id="aa0df-259">-TypesToProcess</span></span>

<span data-ttu-id="aa0df-260">Especifica os arquivos de tipo ( `.ps1xml` ) que são executados quando o módulo é importado.</span><span class="sxs-lookup"><span data-stu-id="aa0df-260">Specifies the type files (`.ps1xml`) that run when the module is imported.</span></span>

<span data-ttu-id="aa0df-261">Quando você importa o módulo, o PowerShell executa o `Update-TypeData` cmdlet com os arquivos especificados.</span><span class="sxs-lookup"><span data-stu-id="aa0df-261">When you import the module, PowerShell runs the `Update-TypeData` cmdlet with the specified files.</span></span>
<span data-ttu-id="aa0df-262">Como os arquivos de tipo não estão no escopo, eles afetam todos os Estados de sessão na sessão.</span><span class="sxs-lookup"><span data-stu-id="aa0df-262">Because type files aren't scoped, they affect all session states in the session.</span></span>

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

### <span data-ttu-id="aa0df-263">-VariablesToExport</span><span class="sxs-lookup"><span data-stu-id="aa0df-263">-VariablesToExport</span></span>

<span data-ttu-id="aa0df-264">Especifica as variáveis que o módulo exporta.</span><span class="sxs-lookup"><span data-stu-id="aa0df-264">Specifies the variables that the module exports.</span></span> <span data-ttu-id="aa0df-265">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="aa0df-265">Wildcards are permitted.</span></span>

<span data-ttu-id="aa0df-266">Use esse parâmetro para restringir as variáveis exportadas pelo módulo.</span><span class="sxs-lookup"><span data-stu-id="aa0df-266">Use this parameter to restrict the variables that are exported by the module.</span></span> <span data-ttu-id="aa0df-267">**VariablesToExport** pode remover variáveis da lista de variáveis exportadas, mas não pode adicionar variáveis à lista.</span><span class="sxs-lookup"><span data-stu-id="aa0df-267">**VariablesToExport** can remove variables from the list of exported variables, but it can't add variables to the list.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="aa0df-268">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="aa0df-268">-WhatIf</span></span>

<span data-ttu-id="aa0df-269">Mostra o que aconteceria se `Update-ModuleManifest` for executado.</span><span class="sxs-lookup"><span data-stu-id="aa0df-269">Shows what would happen if `Update-ModuleManifest` runs.</span></span> <span data-ttu-id="aa0df-270">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="aa0df-270">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="aa0df-271">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="aa0df-271">CommonParameters</span></span>

<span data-ttu-id="aa0df-272">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="aa0df-272">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="aa0df-273">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="aa0df-273">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="aa0df-274">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="aa0df-274">INPUTS</span></span>

### <span data-ttu-id="aa0df-275">System.String</span><span class="sxs-lookup"><span data-stu-id="aa0df-275">System.String</span></span>

## <span data-ttu-id="aa0df-276">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="aa0df-276">OUTPUTS</span></span>

### <span data-ttu-id="aa0df-277">System.Object</span><span class="sxs-lookup"><span data-stu-id="aa0df-277">System.Object</span></span>

## <span data-ttu-id="aa0df-278">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="aa0df-278">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aa0df-279">A partir de abril de 2020, o Galeria do PowerShell não dá mais suporte às versões 1,0 e 1,1 da segurança da camada de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="aa0df-279">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="aa0df-280">Se você não estiver usando o TLS 1,2 ou superior, receberá um erro ao tentar acessar o Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aa0df-280">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="aa0df-281">Use o comando a seguir para garantir que você esteja usando o TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="aa0df-281">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="aa0df-282">Para obter mais informações, consulte o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aa0df-282">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="aa0df-283">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="aa0df-283">RELATED LINKS</span></span>
