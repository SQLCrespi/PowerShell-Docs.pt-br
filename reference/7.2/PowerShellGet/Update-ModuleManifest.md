---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/08/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-modulemanifest?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-ModuleManifest
ms.openlocfilehash: 4f00450257178cac72d03303358150fd9f5cd26b
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "99597602"
---
# <span data-ttu-id="c887c-102">Update-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="c887c-102">Update-ModuleManifest</span></span>

## <span data-ttu-id="c887c-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="c887c-103">SYNOPSIS</span></span>
<span data-ttu-id="c887c-104">Atualiza um arquivo de manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="c887c-104">Updates a module manifest file.</span></span>

## <span data-ttu-id="c887c-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c887c-105">SYNTAX</span></span>

### <span data-ttu-id="c887c-106">Tudo</span><span class="sxs-lookup"><span data-stu-id="c887c-106">All</span></span>

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

## <span data-ttu-id="c887c-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c887c-107">DESCRIPTION</span></span>

<span data-ttu-id="c887c-108">O `Update-ModuleManifest` cmdlet atualiza um arquivo de manifesto de módulo ( `.psd1` ).</span><span class="sxs-lookup"><span data-stu-id="c887c-108">The `Update-ModuleManifest` cmdlet updates a module manifest (`.psd1`) file.</span></span>

## <span data-ttu-id="c887c-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="c887c-109">EXAMPLES</span></span>

### <span data-ttu-id="c887c-110">Exemplo 1: atualizar um manifesto de módulo</span><span class="sxs-lookup"><span data-stu-id="c887c-110">Example 1: Update a module manifest</span></span>

<span data-ttu-id="c887c-111">Este exemplo atualiza um arquivo de manifesto de módulo existente.</span><span class="sxs-lookup"><span data-stu-id="c887c-111">This example updates an existing module manifest file.</span></span> <span data-ttu-id="c887c-112">Nivelamento é usado para passar valores de parâmetro para `Update-ModuleManifest` .</span><span class="sxs-lookup"><span data-stu-id="c887c-112">Splatting is used to pass parameter values to `Update-ModuleManifest`.</span></span> <span data-ttu-id="c887c-113">Para obter mais informações, consulte [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="c887c-113">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

```powershell
$Parms = @{
  Path = "C:\Test\TestManifest.psd1"
  Author = "TestUser1"
  CompanyName = "Contoso Corporation"
  Copyright = "(c) 2019 Contoso Corporation. All rights reserved."
}

Update-ModuleManifest @Parms
```

<span data-ttu-id="c887c-114">`$Parms` é um fragmentação que armazena os valores de parâmetro para **caminho**, **autor**, **CompanyName** e **direitos autorais**.</span><span class="sxs-lookup"><span data-stu-id="c887c-114">`$Parms` is a splat that stores the parameter values for **Path**, **Author**, **CompanyName**, and **Copyright**.</span></span> <span data-ttu-id="c887c-115">`Update-ModuleManifest` Obtém os valores de parâmetro de `@Parms` e atualiza o manifesto do módulo, **TestManifest.psd1**.</span><span class="sxs-lookup"><span data-stu-id="c887c-115">`Update-ModuleManifest` gets the parameter values from `@Parms` and updates the module manifest, **TestManifest.psd1**.</span></span>

## <span data-ttu-id="c887c-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c887c-116">PARAMETERS</span></span>

### <span data-ttu-id="c887c-117">-AliasesToExport</span><span class="sxs-lookup"><span data-stu-id="c887c-117">-AliasesToExport</span></span>

<span data-ttu-id="c887c-118">Especifica os aliases que o módulo exporta.</span><span class="sxs-lookup"><span data-stu-id="c887c-118">Specifies the aliases that the module exports.</span></span> <span data-ttu-id="c887c-119">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="c887c-119">Wildcards are permitted.</span></span>

<span data-ttu-id="c887c-120">Use esse parâmetro para restringir os aliases exportados pelo módulo.</span><span class="sxs-lookup"><span data-stu-id="c887c-120">Use this parameter to restrict the aliases that are exported by the module.</span></span> <span data-ttu-id="c887c-121">**AliasesToExport** pode remover aliases da lista de aliases exportados, mas não pode adicionar aliases à lista.</span><span class="sxs-lookup"><span data-stu-id="c887c-121">**AliasesToExport** can remove aliases from the list of exported aliases, but it can't add aliases to the list.</span></span>

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

### <span data-ttu-id="c887c-122">-Autor</span><span class="sxs-lookup"><span data-stu-id="c887c-122">-Author</span></span>

<span data-ttu-id="c887c-123">Especifica o autor do módulo.</span><span class="sxs-lookup"><span data-stu-id="c887c-123">Specifies the module author.</span></span>

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

### <span data-ttu-id="c887c-124">-ClrVersion</span><span class="sxs-lookup"><span data-stu-id="c887c-124">-ClrVersion</span></span>

<span data-ttu-id="c887c-125">Especifica a versão mínima do CLR (Common Language Runtime) do Microsoft .NET Framework que o módulo exige.</span><span class="sxs-lookup"><span data-stu-id="c887c-125">Specifies the minimum version of the Common Language Runtime (CLR) of the Microsoft .NET Framework that the module requires.</span></span>

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

### <span data-ttu-id="c887c-126">-CmdletsToExport</span><span class="sxs-lookup"><span data-stu-id="c887c-126">-CmdletsToExport</span></span>

<span data-ttu-id="c887c-127">Especifica os cmdlets que o módulo exporta.</span><span class="sxs-lookup"><span data-stu-id="c887c-127">Specifies the cmdlets that the module exports.</span></span> <span data-ttu-id="c887c-128">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="c887c-128">Wildcards are permitted.</span></span>

<span data-ttu-id="c887c-129">Use esse parâmetro para restringir os cmdlets que são exportados pelo módulo.</span><span class="sxs-lookup"><span data-stu-id="c887c-129">Use this parameter to restrict the cmdlets that are exported by the module.</span></span> <span data-ttu-id="c887c-130">**CmdletsToExport** pode remover cmdlets da lista de cmdlets exportados, mas não pode adicionar cmdlets à lista.</span><span class="sxs-lookup"><span data-stu-id="c887c-130">**CmdletsToExport** can remove cmdlets from the list of exported cmdlets, but it can't add cmdlets to the list.</span></span>

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

### <span data-ttu-id="c887c-131">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="c887c-131">-CompanyName</span></span>

<span data-ttu-id="c887c-132">Especifica a empresa ou o fornecedor que criou o módulo.</span><span class="sxs-lookup"><span data-stu-id="c887c-132">Specifies the company or vendor who created the module.</span></span>

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

### <span data-ttu-id="c887c-133">-CompatiblePSEditions</span><span class="sxs-lookup"><span data-stu-id="c887c-133">-CompatiblePSEditions</span></span>

<span data-ttu-id="c887c-134">Especifica o **PSEditions** compatível do módulo.</span><span class="sxs-lookup"><span data-stu-id="c887c-134">Specifies the compatible **PSEditions** of the module.</span></span> <span data-ttu-id="c887c-135">Para obter informações sobre **PSEdition**, consulte [módulos com as edições compatíveis do PowerShell](/powershell/scripting/gallery/concepts/module-psedition-support).</span><span class="sxs-lookup"><span data-stu-id="c887c-135">For information about **PSEdition**, see [Modules with compatible PowerShell Editions](/powershell/scripting/gallery/concepts/module-psedition-support).</span></span>

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

### <span data-ttu-id="c887c-136">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c887c-136">-Confirm</span></span>

<span data-ttu-id="c887c-137">Solicita a confirmação antes de executar `Update-ModuleManifest` .</span><span class="sxs-lookup"><span data-stu-id="c887c-137">Prompts you for confirmation before running `Update-ModuleManifest`.</span></span>

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

### <span data-ttu-id="c887c-138">-Direitos autorais</span><span class="sxs-lookup"><span data-stu-id="c887c-138">-Copyright</span></span>

<span data-ttu-id="c887c-139">Especifica uma declaração de direitos autorais do módulo.</span><span class="sxs-lookup"><span data-stu-id="c887c-139">Specifies a copyright statement for the module.</span></span>

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

### <span data-ttu-id="c887c-140">-DefaultCommandPrefix</span><span class="sxs-lookup"><span data-stu-id="c887c-140">-DefaultCommandPrefix</span></span>

<span data-ttu-id="c887c-141">Especifica o prefixo de comando padrão.</span><span class="sxs-lookup"><span data-stu-id="c887c-141">Specifies the default command prefix.</span></span>

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

### <span data-ttu-id="c887c-142">-Description</span><span class="sxs-lookup"><span data-stu-id="c887c-142">-Description</span></span>

<span data-ttu-id="c887c-143">Especifica uma descrição do módulo.</span><span class="sxs-lookup"><span data-stu-id="c887c-143">Specifies a description of the module.</span></span>

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

### <span data-ttu-id="c887c-144">-DotNetFrameworkVersion</span><span class="sxs-lookup"><span data-stu-id="c887c-144">-DotNetFrameworkVersion</span></span>

<span data-ttu-id="c887c-145">Especifica a versão mínima do Microsoft .NET Framework que o módulo exige.</span><span class="sxs-lookup"><span data-stu-id="c887c-145">Specifies the minimum version of the Microsoft .NET Framework that the module requires.</span></span>

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

### <span data-ttu-id="c887c-146">-DscResourcesToExport</span><span class="sxs-lookup"><span data-stu-id="c887c-146">-DscResourcesToExport</span></span>

<span data-ttu-id="c887c-147">Especifica os recursos de DSC (configuração de estado desejado) que o módulo exporta.</span><span class="sxs-lookup"><span data-stu-id="c887c-147">Specifies the Desired State Configuration (DSC) resources that the module exports.</span></span> <span data-ttu-id="c887c-148">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="c887c-148">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="c887c-149">-ExternalModuleDependencies</span><span class="sxs-lookup"><span data-stu-id="c887c-149">-ExternalModuleDependencies</span></span>

<span data-ttu-id="c887c-150">Especifica uma matriz de dependências de módulo externas.</span><span class="sxs-lookup"><span data-stu-id="c887c-150">Specifies an array of external module dependencies.</span></span>

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

### <span data-ttu-id="c887c-151">-FileList</span><span class="sxs-lookup"><span data-stu-id="c887c-151">-FileList</span></span>

<span data-ttu-id="c887c-152">Especifica todos os itens incluídos no módulo.</span><span class="sxs-lookup"><span data-stu-id="c887c-152">Specifies all items that are included in the module.</span></span>

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

### <span data-ttu-id="c887c-153">-FormatsToProcess</span><span class="sxs-lookup"><span data-stu-id="c887c-153">-FormatsToProcess</span></span>

<span data-ttu-id="c887c-154">Especifica os arquivos de formatação ( `.ps1xml` ) que são executados quando o módulo é importado.</span><span class="sxs-lookup"><span data-stu-id="c887c-154">Specifies the formatting files (`.ps1xml`) that run when the module is imported.</span></span>

<span data-ttu-id="c887c-155">Quando você importa um módulo, o PowerShell executa o `Update-FormatData` cmdlet com os arquivos especificados.</span><span class="sxs-lookup"><span data-stu-id="c887c-155">When you import a module, PowerShell runs the `Update-FormatData` cmdlet with the specified files.</span></span>
<span data-ttu-id="c887c-156">Como os arquivos de formatação não estão no escopo, eles afetam todos os Estados de sessão na sessão.</span><span class="sxs-lookup"><span data-stu-id="c887c-156">Because formatting files aren't scoped, they affect all session states in the session.</span></span>

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

### <span data-ttu-id="c887c-157">-FunctionsToExport</span><span class="sxs-lookup"><span data-stu-id="c887c-157">-FunctionsToExport</span></span>

<span data-ttu-id="c887c-158">Especifica as funções que o módulo exporta.</span><span class="sxs-lookup"><span data-stu-id="c887c-158">Specifies the functions that the module exports.</span></span> <span data-ttu-id="c887c-159">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="c887c-159">Wildcards are permitted.</span></span>

<span data-ttu-id="c887c-160">Use esse parâmetro para restringir as funções exportadas pelo módulo.</span><span class="sxs-lookup"><span data-stu-id="c887c-160">Use this parameter to restrict the functions that are exported by the module.</span></span> <span data-ttu-id="c887c-161">**FunctionsToExport** pode remover funções da lista de aliases exportados, mas não pode adicionar funções à lista.</span><span class="sxs-lookup"><span data-stu-id="c887c-161">**FunctionsToExport** can remove functions from the list of exported aliases, but it can't add functions to the list.</span></span>

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

### <span data-ttu-id="c887c-162">-GUID</span><span class="sxs-lookup"><span data-stu-id="c887c-162">-Guid</span></span>

<span data-ttu-id="c887c-163">Especifica um identificador exclusivo para o módulo.</span><span class="sxs-lookup"><span data-stu-id="c887c-163">Specifies a unique identifier for the module.</span></span> <span data-ttu-id="c887c-164">O GUID pode ser usado para distinguir entre módulos com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="c887c-164">The GUID can be used to distinguish among modules with the same name.</span></span>

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

### <span data-ttu-id="c887c-165">-HelpInfoUri</span><span class="sxs-lookup"><span data-stu-id="c887c-165">-HelpInfoUri</span></span>

<span data-ttu-id="c887c-166">Especifica o endereço da Internet do arquivo **XML HelpInfo** do módulo.</span><span class="sxs-lookup"><span data-stu-id="c887c-166">Specifies the internet address of the module's **HelpInfo XML** file.</span></span> <span data-ttu-id="c887c-167">Insira um Uniform Resource Identifier (URI) que comece com **http** ou **https**.</span><span class="sxs-lookup"><span data-stu-id="c887c-167">Enter a Uniform Resource Identifier (URI) that begins with **http** or **https**.</span></span>

<span data-ttu-id="c887c-168">O arquivo **XML HelpInfo** dá suporte ao recurso de ajuda atualizável que foi introduzido no PowerShell versão 3,0.</span><span class="sxs-lookup"><span data-stu-id="c887c-168">The **HelpInfo XML** file supports the Updatable Help feature that was introduced in PowerShell version 3.0.</span></span> <span data-ttu-id="c887c-169">Ele contém informações sobre o local dos arquivos de ajuda baixáveis do módulo e os números de versão dos arquivos de ajuda mais recentes para cada localidade com suporte.</span><span class="sxs-lookup"><span data-stu-id="c887c-169">It contains information about the location of the module's downloadable help files and the version numbers of the newest help files for each supported locale.</span></span>

<span data-ttu-id="c887c-170">Para obter informações sobre a ajuda atualizável, consulte [about_Updatable_Help](../Microsoft.PowerShell.Core/About/about_Updatable_Help.md).</span><span class="sxs-lookup"><span data-stu-id="c887c-170">For information about Updatable Help, see [about_Updatable_Help](../Microsoft.PowerShell.Core/About/about_Updatable_Help.md).</span></span>
<span data-ttu-id="c887c-171">Para obter informações sobre o arquivo **XML HelpInfo** , consulte [suporte à ajuda atualizável](/powershell/scripting/developer/module/supporting-updatable-help).</span><span class="sxs-lookup"><span data-stu-id="c887c-171">For information about the **HelpInfo XML** file, see [Supporting Updatable Help](/powershell/scripting/developer/module/supporting-updatable-help).</span></span>

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

### <span data-ttu-id="c887c-172">-IconUri</span><span class="sxs-lookup"><span data-stu-id="c887c-172">-IconUri</span></span>

<span data-ttu-id="c887c-173">Especifica a URL de um ícone para o módulo.</span><span class="sxs-lookup"><span data-stu-id="c887c-173">Specifies the URL of an icon for the module.</span></span> <span data-ttu-id="c887c-174">O ícone especificado é exibido na página da Galeria da Web para o módulo.</span><span class="sxs-lookup"><span data-stu-id="c887c-174">The specified icon is displayed on the gallery web page for the module.</span></span>

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

### <span data-ttu-id="c887c-175">-LicenseUri</span><span class="sxs-lookup"><span data-stu-id="c887c-175">-LicenseUri</span></span>

<span data-ttu-id="c887c-176">Especifica a URL dos termos de licenciamento do módulo.</span><span class="sxs-lookup"><span data-stu-id="c887c-176">Specifies the URL of licensing terms for the module.</span></span>

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

### <span data-ttu-id="c887c-177">-ModuleList</span><span class="sxs-lookup"><span data-stu-id="c887c-177">-ModuleList</span></span>

<span data-ttu-id="c887c-178">Especifica uma matriz de módulos que são incluídos no módulo.</span><span class="sxs-lookup"><span data-stu-id="c887c-178">Specifies an array of modules that are included in the module.</span></span>

<span data-ttu-id="c887c-179">Insira o nome de cada módulo como uma cadeia de caracteres ou uma tabela de hash com as chaves **ModuleName** e **ModuleVersion**.</span><span class="sxs-lookup"><span data-stu-id="c887c-179">Enter each module name as a string or as a hash table with **ModuleName** and **ModuleVersion** keys.</span></span> <span data-ttu-id="c887c-180">A tabela de hash também pode ter uma chave **GUID** opcional.</span><span class="sxs-lookup"><span data-stu-id="c887c-180">The hash table can also have an optional **GUID** key.</span></span> <span data-ttu-id="c887c-181">Você pode combinar cadeias de caracteres e tabelas de hash no valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="c887c-181">You can combine strings and hash tables in the parameter value.</span></span>

<span data-ttu-id="c887c-182">Essa chave foi projetada para atuar como um inventário de módulo.</span><span class="sxs-lookup"><span data-stu-id="c887c-182">This key is designed to act as a module inventory.</span></span> <span data-ttu-id="c887c-183">Os módulos listados no valor dessa chave não são processados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c887c-183">The modules that are listed in the value of this key aren't automatically processed.</span></span>

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

### <span data-ttu-id="c887c-184">-ModuleVersion</span><span class="sxs-lookup"><span data-stu-id="c887c-184">-ModuleVersion</span></span>

<span data-ttu-id="c887c-185">Especifica a versão do módulo.</span><span class="sxs-lookup"><span data-stu-id="c887c-185">Specifies the version of the module.</span></span>

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

### <span data-ttu-id="c887c-186">-NestedModules</span><span class="sxs-lookup"><span data-stu-id="c887c-186">-NestedModules</span></span>

<span data-ttu-id="c887c-187">Especifica módulos de script ( `.psm1` ) e módulos binários ( `.dll` ) que são importados para o estado de sessão do módulo.</span><span class="sxs-lookup"><span data-stu-id="c887c-187">Specifies script modules (`.psm1`) and binary modules (`.dll`) that are imported into the module's session state.</span></span> <span data-ttu-id="c887c-188">Os arquivos na chave **NestedModules** são executados na ordem em que estão listados no valor.</span><span class="sxs-lookup"><span data-stu-id="c887c-188">The files in the **NestedModules** key run in the order in which they're listed in the value.</span></span>

<span data-ttu-id="c887c-189">Insira o nome de cada módulo como uma cadeia de caracteres ou uma tabela de hash com as chaves **ModuleName** e **ModuleVersion**.</span><span class="sxs-lookup"><span data-stu-id="c887c-189">Enter each module name as a string or as a hash table with **ModuleName** and **ModuleVersion** keys.</span></span> <span data-ttu-id="c887c-190">A tabela de hash também pode ter uma chave **GUID** opcional.</span><span class="sxs-lookup"><span data-stu-id="c887c-190">The hash table can also have an optional **GUID** key.</span></span> <span data-ttu-id="c887c-191">Você pode combinar cadeias de caracteres e tabelas de hash no valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="c887c-191">You can combine strings and hash tables in the parameter value.</span></span>

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

### <span data-ttu-id="c887c-192">-PackageManagementProviders</span><span class="sxs-lookup"><span data-stu-id="c887c-192">-PackageManagementProviders</span></span>

<span data-ttu-id="c887c-193">Especifica uma matriz de provedores de gerenciamento de pacotes.</span><span class="sxs-lookup"><span data-stu-id="c887c-193">Specifies an array of package management providers.</span></span>

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

### <span data-ttu-id="c887c-194">-PassThru</span><span class="sxs-lookup"><span data-stu-id="c887c-194">-PassThru</span></span>

<span data-ttu-id="c887c-195">Retorna um objeto que representa o item com o qual você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="c887c-195">Returns an object representing the item with which you're working.</span></span> <span data-ttu-id="c887c-196">Por padrão, o `Update-ModuleManifest` não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="c887c-196">By default, `Update-ModuleManifest` doesn't generate any output.</span></span>

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

### <span data-ttu-id="c887c-197">-Path</span><span class="sxs-lookup"><span data-stu-id="c887c-197">-Path</span></span>

<span data-ttu-id="c887c-198">Especifica o caminho e o nome do arquivo do manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="c887c-198">Specifies the path and file name of the module manifest.</span></span> <span data-ttu-id="c887c-199">Insira um caminho e um nome de arquivo com uma `.psd1` extensão de nome de arquivo, como `$PSHOME\Modules\MyModule\MyModule.psd1` .</span><span class="sxs-lookup"><span data-stu-id="c887c-199">Enter a path and file name with a `.psd1` file name extension, such as `$PSHOME\Modules\MyModule\MyModule.psd1`.</span></span>

<span data-ttu-id="c887c-200">Se você especificar o caminho para um arquivo existente, `Update-ModuleManifest` o substituirá o arquivo sem aviso, a menos que o arquivo tenha o atributo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="c887c-200">If you specify the path to an existing file, `Update-ModuleManifest` replaces the file without warning unless the file has the read-only attribute.</span></span>

<span data-ttu-id="c887c-201">O manifesto deve estar localizado no diretório do módulo e o nome do arquivo de manifesto deve ser o mesmo que o nome do diretório do módulo, mas com uma `.psd1` extensão.</span><span class="sxs-lookup"><span data-stu-id="c887c-201">The manifest should be located in the module's directory, and the manifest file name should be the same as the module directory name, but with a `.psd1` extension.</span></span>

<span data-ttu-id="c887c-202">Você não pode usar variáveis, como `$PSHOME` ou `$HOME` , em resposta a um prompt para um valor de parâmetro de **caminho** .</span><span class="sxs-lookup"><span data-stu-id="c887c-202">You can't use variables, such as `$PSHOME` or `$HOME`, in response to a prompt for a **Path** parameter value.</span></span> <span data-ttu-id="c887c-203">Para usar uma variável, inclua o parâmetro **Path** no comando.</span><span class="sxs-lookup"><span data-stu-id="c887c-203">To use a variable, include the **Path** parameter in the command.</span></span>

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

### <span data-ttu-id="c887c-204">-PowerShellHostName</span><span class="sxs-lookup"><span data-stu-id="c887c-204">-PowerShellHostName</span></span>

<span data-ttu-id="c887c-205">Especifica o nome do programa de host do PowerShell que o módulo requer.</span><span class="sxs-lookup"><span data-stu-id="c887c-205">Specifies the name of the PowerShell host program that the module requires.</span></span> <span data-ttu-id="c887c-206">Insira o nome do programa host, como o host do ISE do PowerShell ou ConsoleHost.</span><span class="sxs-lookup"><span data-stu-id="c887c-206">Enter the name of the host program, such as PowerShell ISE Host or ConsoleHost.</span></span> <span data-ttu-id="c887c-207">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="c887c-207">Wildcards aren't permitted.</span></span>

<span data-ttu-id="c887c-208">Para localizar o nome de um programa de host, no programa, digite `$Host.Name` .</span><span class="sxs-lookup"><span data-stu-id="c887c-208">To find the name of a host program, in the program, type `$Host.Name`.</span></span>

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

### <span data-ttu-id="c887c-209">-PowerShellHostVersion</span><span class="sxs-lookup"><span data-stu-id="c887c-209">-PowerShellHostVersion</span></span>

<span data-ttu-id="c887c-210">Especifica a versão mínima do programa de host do PowerShell que funciona com o módulo.</span><span class="sxs-lookup"><span data-stu-id="c887c-210">Specifies the minimum version of the PowerShell host program that works with the module.</span></span> <span data-ttu-id="c887c-211">Insira um número de versão, como 1.1.</span><span class="sxs-lookup"><span data-stu-id="c887c-211">Enter a version number, such as 1.1.</span></span>

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

### <span data-ttu-id="c887c-212">-PowerShellVersion</span><span class="sxs-lookup"><span data-stu-id="c887c-212">-PowerShellVersion</span></span>

<span data-ttu-id="c887c-213">Especifica a versão mínima do PowerShell que funcionará com este módulo.</span><span class="sxs-lookup"><span data-stu-id="c887c-213">Specifies the minimum version of PowerShell that will work with this module.</span></span> <span data-ttu-id="c887c-214">Por exemplo, você pode especificar 3,0, 4,0 ou 5,0 como o valor desse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="c887c-214">For example, you can specify 3.0, 4.0, or 5.0 as the value of this parameter.</span></span>

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

### <span data-ttu-id="c887c-215">-Pré-lançamento</span><span class="sxs-lookup"><span data-stu-id="c887c-215">-Prerelease</span></span>

<span data-ttu-id="c887c-216">Indica que o módulo é de pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="c887c-216">Indicates the module is prerelease.</span></span>

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

### <span data-ttu-id="c887c-217">-PrivateData</span><span class="sxs-lookup"><span data-stu-id="c887c-217">-PrivateData</span></span>

<span data-ttu-id="c887c-218">Especifica os dados que são passados para o módulo quando ele é importado.</span><span class="sxs-lookup"><span data-stu-id="c887c-218">Specifies data that is passed to the module when it's imported.</span></span>

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

### <span data-ttu-id="c887c-219">-ProcessorArchitecture</span><span class="sxs-lookup"><span data-stu-id="c887c-219">-ProcessorArchitecture</span></span>

<span data-ttu-id="c887c-220">Especifica a arquitetura do processador que o módulo requer.</span><span class="sxs-lookup"><span data-stu-id="c887c-220">Specifies the processor architecture that the module requires.</span></span>

<span data-ttu-id="c887c-221">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="c887c-221">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="c887c-222">AMD64</span><span class="sxs-lookup"><span data-stu-id="c887c-222">Amd64</span></span>
- <span data-ttu-id="c887c-223">Arm</span><span class="sxs-lookup"><span data-stu-id="c887c-223">Arm</span></span>
- <span data-ttu-id="c887c-224">IA64</span><span class="sxs-lookup"><span data-stu-id="c887c-224">IA64</span></span>
- <span data-ttu-id="c887c-225">MSIL</span><span class="sxs-lookup"><span data-stu-id="c887c-225">MSIL</span></span>
- <span data-ttu-id="c887c-226">Nenhum (desconhecido ou não especificado)</span><span class="sxs-lookup"><span data-stu-id="c887c-226">None (unknown or unspecified)</span></span>
- <span data-ttu-id="c887c-227">X86</span><span class="sxs-lookup"><span data-stu-id="c887c-227">X86</span></span>

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

### <span data-ttu-id="c887c-228">-ProjectUri</span><span class="sxs-lookup"><span data-stu-id="c887c-228">-ProjectUri</span></span>

<span data-ttu-id="c887c-229">Especifica a URL de uma página da Web sobre este projeto.</span><span class="sxs-lookup"><span data-stu-id="c887c-229">Specifies the URL of a web page about this project.</span></span>

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

### <span data-ttu-id="c887c-230">-ReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="c887c-230">-ReleaseNotes</span></span>

<span data-ttu-id="c887c-231">Especifica uma matriz de cadeia de caracteres que contém notas de versão ou comentários que você deseja disponibilizar para esta versão do script.</span><span class="sxs-lookup"><span data-stu-id="c887c-231">Specifies a string array that contains release notes or comments that you want available for this version of the script.</span></span>

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

### <span data-ttu-id="c887c-232">-RequireLicenseAcceptance</span><span class="sxs-lookup"><span data-stu-id="c887c-232">-RequireLicenseAcceptance</span></span>

<span data-ttu-id="c887c-233">Especifica que uma aceitação de licença é necessária para o módulo.</span><span class="sxs-lookup"><span data-stu-id="c887c-233">Specifies that a license acceptance is required for the module.</span></span>

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

### <span data-ttu-id="c887c-234">-RequiredAssemblies</span><span class="sxs-lookup"><span data-stu-id="c887c-234">-RequiredAssemblies</span></span>

<span data-ttu-id="c887c-235">Especifica os arquivos de assembly ( `.dll` ) que o módulo requer.</span><span class="sxs-lookup"><span data-stu-id="c887c-235">Specifies the assembly (`.dll`) files that the module requires.</span></span> <span data-ttu-id="c887c-236">Digite os nomes de arquivo de assembly.</span><span class="sxs-lookup"><span data-stu-id="c887c-236">Enter the assembly file names.</span></span>
<span data-ttu-id="c887c-237">O PowerShell carrega os assemblies especificados antes de atualizar os tipos ou formatos, importando módulos aninhados ou importando o arquivo de módulo especificado no valor da chave **RootModule** .</span><span class="sxs-lookup"><span data-stu-id="c887c-237">PowerShell loads the specified assemblies before updating types or formats, importing nested modules, or importing the module file that is specified in the value of the **RootModule** key.</span></span>

<span data-ttu-id="c887c-238">Use esse parâmetro para especificar todos os assemblies que o módulo requer, incluindo assemblies que devem ser carregados para atualizar qualquer formatação ou arquivos de tipo listados nas chaves **FormatsToProcess** ou **TypesToProcess** , mesmo se esses assemblies também estiverem listados como módulos binários na chave **NestedModules** .</span><span class="sxs-lookup"><span data-stu-id="c887c-238">Use this parameter to specify all the assemblies that the module requires, including assemblies that must be loaded to update any formatting or type files that are listed in the **FormatsToProcess** or **TypesToProcess** keys, even if those assemblies are also listed as binary modules in the **NestedModules** key.</span></span>

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

### <span data-ttu-id="c887c-239">-RequiredModules</span><span class="sxs-lookup"><span data-stu-id="c887c-239">-RequiredModules</span></span>

<span data-ttu-id="c887c-240">Especifica os módulos que devem estar no estado de sessão global.</span><span class="sxs-lookup"><span data-stu-id="c887c-240">Specifies modules that must be in the global session state.</span></span> <span data-ttu-id="c887c-241">Se os módulos necessários não estiverem no estado de sessão global, o PowerShell os importará.</span><span class="sxs-lookup"><span data-stu-id="c887c-241">If the required modules aren't in the global session state, PowerShell imports them.</span></span> <span data-ttu-id="c887c-242">Se os módulos necessários não estiverem disponíveis, o `Import-Module` comando falhará.</span><span class="sxs-lookup"><span data-stu-id="c887c-242">If the required modules aren't available, the `Import-Module` command fails.</span></span>

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

### <span data-ttu-id="c887c-243">-RootModule</span><span class="sxs-lookup"><span data-stu-id="c887c-243">-RootModule</span></span>

<span data-ttu-id="c887c-244">Especifica o arquivo primário ou raiz do módulo.</span><span class="sxs-lookup"><span data-stu-id="c887c-244">Specifies the primary or root file of the module.</span></span> <span data-ttu-id="c887c-245">Insira o nome de arquivo de um script ( `.ps1` ), um módulo de script ( `.psm1` ), um manifesto de módulo ( `.psd1` ), um assembly ( `.dll` ), um arquivo XML de definição de cmdlet ( `.cdxml` ) ou um fluxo de trabalho ( `.xaml` ).</span><span class="sxs-lookup"><span data-stu-id="c887c-245">Enter the file name of a script (`.ps1`), a script module (`.psm1`), a module manifest (`.psd1`), an assembly (`.dll`), a cmdlet definition XML file (`.cdxml`), or a workflow (`.xaml`).</span></span> <span data-ttu-id="c887c-246">Quando o módulo é importado, os membros que são exportados do arquivo do módulo raiz são importados para o estado de sessão do chamador.</span><span class="sxs-lookup"><span data-stu-id="c887c-246">When the module is imported, the members that are exported from the root module file are imported into the caller's session state.</span></span>

<span data-ttu-id="c887c-247">Se um módulo tiver um arquivo de manifesto e nenhum arquivo raiz tiver sido especificado na chave **RootModule** , o manifesto se tornará o arquivo primário do módulo.</span><span class="sxs-lookup"><span data-stu-id="c887c-247">If a module has a manifest file and no root file has been specified in the **RootModule** key, the manifest becomes the primary file for the module.</span></span> <span data-ttu-id="c887c-248">E, o módulo torna-se um módulo de manifesto (Módulotype = manifesto).</span><span class="sxs-lookup"><span data-stu-id="c887c-248">And, the module becomes a manifest module (ModuleType = Manifest).</span></span>

<span data-ttu-id="c887c-249">Para exportar membros de `.psm1` ou `.dll` arquivos em um módulo que tenha um manifesto, os nomes desses arquivos devem ser especificados nos valores das chaves **RootModule** ou **NestedModules** no manifesto.</span><span class="sxs-lookup"><span data-stu-id="c887c-249">To export members from `.psm1` or `.dll` files in a module that has a manifest, the names of those files must be specified in the values of the **RootModule** or **NestedModules** keys in the manifest.</span></span> <span data-ttu-id="c887c-250">Caso contrário, seus membros não serão exportados.</span><span class="sxs-lookup"><span data-stu-id="c887c-250">Otherwise, their members aren't exported.</span></span>

<span data-ttu-id="c887c-251">No PowerShell 2,0, essa chave foi chamada de **ModuleToProcess**.</span><span class="sxs-lookup"><span data-stu-id="c887c-251">In PowerShell 2.0, this key was called **ModuleToProcess**.</span></span>

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

### <span data-ttu-id="c887c-252">-ScriptsToProcess</span><span class="sxs-lookup"><span data-stu-id="c887c-252">-ScriptsToProcess</span></span>

<span data-ttu-id="c887c-253">Especifica os arquivos de script ( `.ps1` ) que são executados no estado de sessão do chamador quando o módulo é importado.</span><span class="sxs-lookup"><span data-stu-id="c887c-253">Specifies script (`.ps1`) files that run in the caller's session state when the module is imported.</span></span>
<span data-ttu-id="c887c-254">Você pode usar esses scripts para preparar um ambiente, assim como você pode usar um script de logon.</span><span class="sxs-lookup"><span data-stu-id="c887c-254">You can use these scripts to prepare an environment, just as you might use a login script.</span></span>

<span data-ttu-id="c887c-255">Para especificar scripts que são executados no estado de sessão do módulo, use a chave **NestedModules**.</span><span class="sxs-lookup"><span data-stu-id="c887c-255">To specify scripts that run in the module's session state, use the **NestedModules** key.</span></span>

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

### <span data-ttu-id="c887c-256">-Marcas</span><span class="sxs-lookup"><span data-stu-id="c887c-256">-Tags</span></span>

<span data-ttu-id="c887c-257">Especifica uma matriz de marcas.</span><span class="sxs-lookup"><span data-stu-id="c887c-257">Specifies an array of tags.</span></span>

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

### <span data-ttu-id="c887c-258">-TypesToProcess</span><span class="sxs-lookup"><span data-stu-id="c887c-258">-TypesToProcess</span></span>

<span data-ttu-id="c887c-259">Especifica os arquivos de tipo ( `.ps1xml` ) que são executados quando o módulo é importado.</span><span class="sxs-lookup"><span data-stu-id="c887c-259">Specifies the type files (`.ps1xml`) that run when the module is imported.</span></span>

<span data-ttu-id="c887c-260">Quando você importa o módulo, o PowerShell executa o `Update-TypeData` cmdlet com os arquivos especificados.</span><span class="sxs-lookup"><span data-stu-id="c887c-260">When you import the module, PowerShell runs the `Update-TypeData` cmdlet with the specified files.</span></span>
<span data-ttu-id="c887c-261">Como os arquivos de tipo não estão no escopo, eles afetam todos os Estados de sessão na sessão.</span><span class="sxs-lookup"><span data-stu-id="c887c-261">Because type files aren't scoped, they affect all session states in the session.</span></span>

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

### <span data-ttu-id="c887c-262">-VariablesToExport</span><span class="sxs-lookup"><span data-stu-id="c887c-262">-VariablesToExport</span></span>

<span data-ttu-id="c887c-263">Especifica as variáveis que o módulo exporta.</span><span class="sxs-lookup"><span data-stu-id="c887c-263">Specifies the variables that the module exports.</span></span> <span data-ttu-id="c887c-264">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="c887c-264">Wildcards are permitted.</span></span>

<span data-ttu-id="c887c-265">Use esse parâmetro para restringir as variáveis exportadas pelo módulo.</span><span class="sxs-lookup"><span data-stu-id="c887c-265">Use this parameter to restrict the variables that are exported by the module.</span></span> <span data-ttu-id="c887c-266">**VariablesToExport** pode remover variáveis da lista de variáveis exportadas, mas não pode adicionar variáveis à lista.</span><span class="sxs-lookup"><span data-stu-id="c887c-266">**VariablesToExport** can remove variables from the list of exported variables, but it can't add variables to the list.</span></span>

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

### <span data-ttu-id="c887c-267">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c887c-267">-WhatIf</span></span>

<span data-ttu-id="c887c-268">Mostra o que aconteceria se `Update-ModuleManifest` for executado.</span><span class="sxs-lookup"><span data-stu-id="c887c-268">Shows what would happen if `Update-ModuleManifest` runs.</span></span> <span data-ttu-id="c887c-269">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="c887c-269">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="c887c-270">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c887c-270">CommonParameters</span></span>

<span data-ttu-id="c887c-271">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c887c-271">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c887c-272">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c887c-272">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c887c-273">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="c887c-273">INPUTS</span></span>

### <span data-ttu-id="c887c-274">System.String</span><span class="sxs-lookup"><span data-stu-id="c887c-274">System.String</span></span>

## <span data-ttu-id="c887c-275">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="c887c-275">OUTPUTS</span></span>

### <span data-ttu-id="c887c-276">System.Object</span><span class="sxs-lookup"><span data-stu-id="c887c-276">System.Object</span></span>

## <span data-ttu-id="c887c-277">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="c887c-277">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c887c-278">A partir de abril de 2020, a Galeria do PowerShell não dará mais suporte às versões 1.0 e 1.1 do protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="c887c-278">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="c887c-279">Se você não estiver usando o TLS 1.2 ou posterior, receberá um erro ao tentar acessar a Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c887c-279">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="c887c-280">Use o seguinte comando para garantir que esteja usando o TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="c887c-280">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="c887c-281">Para obter mais informações, confira o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c887c-281">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="c887c-282">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="c887c-282">RELATED LINKS</span></span>
