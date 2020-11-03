---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/01/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/new-scriptfileinfo?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ScriptFileInfo
ms.openlocfilehash: f416447c2c13d3dbf2d14ed5ca045164779fcbe0
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93193092"
---
# <span data-ttu-id="068e7-103">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="068e7-103">New-ScriptFileInfo</span></span>

## <span data-ttu-id="068e7-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="068e7-104">SYNOPSIS</span></span>
<span data-ttu-id="068e7-105">Cria um arquivo de script com metadados.</span><span class="sxs-lookup"><span data-stu-id="068e7-105">Creates a script file with metadata.</span></span>

## <span data-ttu-id="068e7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="068e7-106">SYNTAX</span></span>

### <span data-ttu-id="068e7-107">Tudo</span><span class="sxs-lookup"><span data-stu-id="068e7-107">All</span></span>

```
New-ScriptFileInfo [[-Path] <String>] [-Version <String>] [-Author <String>] -Description <String>
 [-Guid <Guid>] [-CompanyName <String>] [-Copyright <String>] [-RequiredModules <Object[]>]
 [-ExternalModuleDependencies <String[]>] [-RequiredScripts <String[]>]
 [-ExternalScriptDependencies <String[]>] [-Tags <String[]>] [-ProjectUri <Uri>] [-LicenseUri <Uri>]
 [-IconUri <Uri>] [-ReleaseNotes <String[]>] [-PrivateData <String>] [-PassThru] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="068e7-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="068e7-108">DESCRIPTION</span></span>

<span data-ttu-id="068e7-109">O `New-ScriptFileInfo` cmdlet cria um arquivo de script do PowerShell, incluindo metadados sobre o script.</span><span class="sxs-lookup"><span data-stu-id="068e7-109">The `New-ScriptFileInfo` cmdlet creates a PowerShell script file, including metadata about the script.</span></span>

<span data-ttu-id="068e7-110">Os exemplos usam nivelamento para passar parâmetros para o `New-ScriptFileInfo` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="068e7-110">The examples use splatting to pass parameters to the `New-ScriptFileInfo` cmdlet.</span></span> <span data-ttu-id="068e7-111">Para obter mais informações, consulte [about_Splatting](../Microsoft.Powershell.Core/About/about_splatting.md).</span><span class="sxs-lookup"><span data-stu-id="068e7-111">For more information, see [about_Splatting](../Microsoft.Powershell.Core/About/about_splatting.md).</span></span>

## <span data-ttu-id="068e7-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="068e7-112">EXAMPLES</span></span>

### <span data-ttu-id="068e7-113">Exemplo 1: criar um arquivo de script e especificar sua versão, autor e descrição</span><span class="sxs-lookup"><span data-stu-id="068e7-113">Example 1: Create a script file and specify its version, author, and description</span></span>

<span data-ttu-id="068e7-114">Neste exemplo, um arquivo de script é criado e seu conteúdo é exibido no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="068e7-114">In this example, a script file is created and its contents are displayed in the PowerShell console.</span></span>

```powershell
$Parms = @{
  Path = "C:\Test\Temp-Scriptfile.ps1"
  Version = "1.0"
  Author = "pattif@contoso.com"
  Description = "My test script file description goes here"
  }
New-ScriptFileInfo @Parms
Get-Content -Path C:\Test\Temp-Scriptfile.ps1
```

```Output
<#PSScriptInfo

.VERSION 1.0

.GUID 3bb10ee7-38c1-41b9-88ea-16899164fc19

.AUTHOR pattif@contoso.com

.COMPANYNAME

.COPYRIGHT

.TAGS

.LICENSEURI

.PROJECTURI

.ICONURI

.EXTERNALMODULEDEPENDENCIES

.REQUIREDSCRIPTS

.EXTERNALSCRIPTDEPENDENCIES

.RELEASENOTES

.PRIVATEDATA

#>

<#

.DESCRIPTION
 My test script file description goes here

#>
Param()
```

<span data-ttu-id="068e7-115">O `New-ScriptFileInfo` cmdlet usa nivelamento para configurar vários parâmetros para o script.</span><span class="sxs-lookup"><span data-stu-id="068e7-115">The `New-ScriptFileInfo` cmdlet uses splatting to configure several parameters for the script.</span></span>
<span data-ttu-id="068e7-116">**Caminho** define o local e o nome do script.</span><span class="sxs-lookup"><span data-stu-id="068e7-116">**Path** sets the location and name of the script.</span></span> <span data-ttu-id="068e7-117">**Version** especifica o número de versão do script.</span><span class="sxs-lookup"><span data-stu-id="068e7-117">**Version** specifies the script's version number.</span></span> <span data-ttu-id="068e7-118">**Autor** é o endereço de email da pessoa que criou o script.</span><span class="sxs-lookup"><span data-stu-id="068e7-118">**Author** is the email address of the person who created the script.</span></span> <span data-ttu-id="068e7-119">**Descrição** explica a finalidade do script.</span><span class="sxs-lookup"><span data-stu-id="068e7-119">**Description** explains the script's purpose.</span></span>

<span data-ttu-id="068e7-120">Depois que o script é criado, `Get-Content` o usa o parâmetro **Path** para localizar o script.</span><span class="sxs-lookup"><span data-stu-id="068e7-120">After the script is created, `Get-Content` uses the **Path** parameter to locate the script.</span></span> <span data-ttu-id="068e7-121">O conteúdo do script é exibido no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="068e7-121">The script's contents are displayed in the PowerShell console.</span></span>

### <span data-ttu-id="068e7-122">Exemplo 2: testar um arquivo de script</span><span class="sxs-lookup"><span data-stu-id="068e7-122">Example 2: Test a script file</span></span>

<span data-ttu-id="068e7-123">Neste exemplo, os metadados do script criado no **exemplo 1** são testados.</span><span class="sxs-lookup"><span data-stu-id="068e7-123">In this example, the metadata for the script created in **Example 1** is tested.</span></span>

```powershell
Test-ScriptFileInfo -Path C:\Test\Temp-Scriptfile.ps1
```

```Output
Version   Name                  Author               Description
-------   ----                  ------               -----------
1.0       Temp-Scriptfile       pattif@contoso.com   My test script file description goes here
```

<span data-ttu-id="068e7-124">O `Test-ScriptFileInfo` cmdlet usa o parâmetro **Path** para especificar o local do arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="068e7-124">The `Test-ScriptFileInfo` cmdlet uses the **Path** parameter to specify the script file's location.</span></span>

### <span data-ttu-id="068e7-125">Exemplo 3: criar um arquivo de script com todas as propriedades de metadados</span><span class="sxs-lookup"><span data-stu-id="068e7-125">Example 3: Create a script file with all the metadata properties</span></span>

<span data-ttu-id="068e7-126">Este exemplo usa nivelamento para criar um arquivo de script chamado `New-ScriptFile.ps1` que inclui todas as suas propriedades de metadados.</span><span class="sxs-lookup"><span data-stu-id="068e7-126">This example uses splatting to create a script file named `New-ScriptFile.ps1` that includes all its metadata properties.</span></span> <span data-ttu-id="068e7-127">O parâmetro **Verbose** especifica que a saída detalhada é exibida à medida que o script é criado.</span><span class="sxs-lookup"><span data-stu-id="068e7-127">The **Verbose** parameter specifies that verbose output is displayed as the script is created.</span></span>

```powershell
$Parms = @{
 Path = "C:\Test\New-ScriptFile.ps1"
 Verbose = $True
 Version = "1.0"
 Author = "pattif@contoso.com"
 Description = "My new script file test"
 CompanyName = "Contoso Corporation"
 Copyright = "2019 Contoso Corporation. All rights reserved."
 ExternalModuleDependencies = "ff","bb"
 RequiredScripts = "Start-WFContosoServer", "Stop-ContosoServerScript"
 ExternalScriptDependencies = "Stop-ContosoServerScript"
 Tags = @("Tag1", "Tag2", "Tag3")
 ProjectUri = "https://contoso.com"
 LicenseUri = "https://contoso.com/License"
 IconUri = "https://contoso.com/Icon"
 PassThru = $True
 ReleaseNotes = @("Contoso script now supports the following features:",
   "Feature 1",
   "Feature 2",
   "Feature 3",
   "Feature 4",
   "Feature 5")
 RequiredModules =
   "1",
   "2",
   "RequiredModule1",
   @{ModuleName="RequiredModule2";ModuleVersion="1.0"},
   @{ModuleName="RequiredModule3";RequiredVersion="2.0"},
   "ExternalModule1"
 }
New-ScriptFileInfo @Parms
```

```Output
VERBOSE: Performing the operation "Creating the 'C:\Test\New-ScriptFile.ps1'
  PowerShell Script file" on target "C:\Test\New-ScriptFile.ps1".

<#PSScriptInfo

.VERSION 1.0

.GUID 4fabe8c7-7862-45b1-a72e-1352a433b77d

.AUTHOR pattif@contoso.com

.COMPANYNAME Contoso Corporation

.COPYRIGHT 2019 Contoso Corporation. All rights reserved.

.TAGS Tag1 Tag2 Tag3

.LICENSEURI https://contoso.com/License

.PROJECTURI https://contoso.com/

.ICONURI https://contoso.com/Icon

.EXTERNALMODULEDEPENDENCIES ff,bb

.REQUIREDSCRIPTS Start-WFContosoServer,Stop-ContosoServerScript

.EXTERNALSCRIPTDEPENDENCIES Stop-ContosoServerScript

.RELEASENOTES
Contoso script now supports the following features:
Feature 1
Feature 2
Feature 3
Feature 4
Feature 5

.PRIVATEDATA

#>

#Requires -Module 1
#Requires -Module 2
#Requires -Module RequiredModule1
#Requires -Module @{ModuleName = 'RequiredModule2'; ModuleVersion = '1.0'}
#Requires -Module @{RequiredVersion = '2.0'; ModuleName = 'RequiredModule3'}
#Requires -Module ExternalModule1

<#

.DESCRIPTION
 My new script file test

#>
Param()
```

## <span data-ttu-id="068e7-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="068e7-128">PARAMETERS</span></span>

### <span data-ttu-id="068e7-129">-Autor</span><span class="sxs-lookup"><span data-stu-id="068e7-129">-Author</span></span>

<span data-ttu-id="068e7-130">Especifica o autor do script.</span><span class="sxs-lookup"><span data-stu-id="068e7-130">Specifies the script author.</span></span>

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

### <span data-ttu-id="068e7-131">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="068e7-131">-CompanyName</span></span>

<span data-ttu-id="068e7-132">Especifica a empresa ou o fornecedor que criou o script.</span><span class="sxs-lookup"><span data-stu-id="068e7-132">Specifies the company or vendor who created the script.</span></span>

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

### <span data-ttu-id="068e7-133">-Confirm</span><span class="sxs-lookup"><span data-stu-id="068e7-133">-Confirm</span></span>

<span data-ttu-id="068e7-134">Solicita a confirmação antes de executar o `New-ScriptFileInfo` .</span><span class="sxs-lookup"><span data-stu-id="068e7-134">Prompts you for confirmation before running the `New-ScriptFileInfo`.</span></span>

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

### <span data-ttu-id="068e7-135">-Direitos autorais</span><span class="sxs-lookup"><span data-stu-id="068e7-135">-Copyright</span></span>

<span data-ttu-id="068e7-136">Especifica uma declaração de direitos autorais para o script.</span><span class="sxs-lookup"><span data-stu-id="068e7-136">Specifies a copyright statement for the script.</span></span>

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

### <span data-ttu-id="068e7-137">-Description</span><span class="sxs-lookup"><span data-stu-id="068e7-137">-Description</span></span>

<span data-ttu-id="068e7-138">Especifica uma descrição para o script.</span><span class="sxs-lookup"><span data-stu-id="068e7-138">Specifies a description for the script.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="068e7-139">-ExternalModuleDependencies</span><span class="sxs-lookup"><span data-stu-id="068e7-139">-ExternalModuleDependencies</span></span>

<span data-ttu-id="068e7-140">Especifica uma matriz de dependências de módulo externas.</span><span class="sxs-lookup"><span data-stu-id="068e7-140">Specifies an array of external module dependencies.</span></span>

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

### <span data-ttu-id="068e7-141">-ExternalScriptDependencies</span><span class="sxs-lookup"><span data-stu-id="068e7-141">-ExternalScriptDependencies</span></span>

<span data-ttu-id="068e7-142">Especifica uma matriz de dependências de script externo.</span><span class="sxs-lookup"><span data-stu-id="068e7-142">Specifies an array of external script dependencies.</span></span>

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

### <span data-ttu-id="068e7-143">-Force</span><span class="sxs-lookup"><span data-stu-id="068e7-143">-Force</span></span>

<span data-ttu-id="068e7-144">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="068e7-144">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="068e7-145">-GUID</span><span class="sxs-lookup"><span data-stu-id="068e7-145">-Guid</span></span>

<span data-ttu-id="068e7-146">Especifica uma ID exclusiva para o script.</span><span class="sxs-lookup"><span data-stu-id="068e7-146">Specifies a unique ID for the script.</span></span>

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

### <span data-ttu-id="068e7-147">-IconUri</span><span class="sxs-lookup"><span data-stu-id="068e7-147">-IconUri</span></span>

<span data-ttu-id="068e7-148">Especifica a URL de um ícone para o script.</span><span class="sxs-lookup"><span data-stu-id="068e7-148">Specifies the URL of an icon for the script.</span></span> <span data-ttu-id="068e7-149">O ícone especificado é exibido na página da Galeria da Web para o script.</span><span class="sxs-lookup"><span data-stu-id="068e7-149">The specified icon is displayed on the gallery web page for the script.</span></span>

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

### <span data-ttu-id="068e7-150">-LicenseUri</span><span class="sxs-lookup"><span data-stu-id="068e7-150">-LicenseUri</span></span>

<span data-ttu-id="068e7-151">Especifica a URL dos termos de licenciamento.</span><span class="sxs-lookup"><span data-stu-id="068e7-151">Specifies the URL of licensing terms.</span></span>

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

### <span data-ttu-id="068e7-152">-PassThru</span><span class="sxs-lookup"><span data-stu-id="068e7-152">-PassThru</span></span>

<span data-ttu-id="068e7-153">Retorna um objeto que representa o item com o qual você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="068e7-153">Returns an object that represents the item with which you're working.</span></span> <span data-ttu-id="068e7-154">Por padrão, o `New-ScriptFileInfo` não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="068e7-154">By default, `New-ScriptFileInfo` doesn't generate any output.</span></span>

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

### <span data-ttu-id="068e7-155">-Path</span><span class="sxs-lookup"><span data-stu-id="068e7-155">-Path</span></span>

<span data-ttu-id="068e7-156">Especifica o local onde o arquivo de script é salvo.</span><span class="sxs-lookup"><span data-stu-id="068e7-156">Specifies the location where the script file is saved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="068e7-157">-PrivateData</span><span class="sxs-lookup"><span data-stu-id="068e7-157">-PrivateData</span></span>

<span data-ttu-id="068e7-158">Especifica dados privados para o script.</span><span class="sxs-lookup"><span data-stu-id="068e7-158">Specifies private data for the script.</span></span>

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

### <span data-ttu-id="068e7-159">-ProjectUri</span><span class="sxs-lookup"><span data-stu-id="068e7-159">-ProjectUri</span></span>

<span data-ttu-id="068e7-160">Especifica a URL de uma página da Web sobre este projeto.</span><span class="sxs-lookup"><span data-stu-id="068e7-160">Specifies the URL of a web page about this project.</span></span>

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

### <span data-ttu-id="068e7-161">-ReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="068e7-161">-ReleaseNotes</span></span>

<span data-ttu-id="068e7-162">Especifica uma matriz de cadeia de caracteres que contém notas de versão ou comentários que você deseja disponibilizar para os usuários desta versão do script.</span><span class="sxs-lookup"><span data-stu-id="068e7-162">Specifies a string array that contains release notes or comments that you want available to users of this version of the script.</span></span>

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

### <span data-ttu-id="068e7-163">-RequiredModules</span><span class="sxs-lookup"><span data-stu-id="068e7-163">-RequiredModules</span></span>

<span data-ttu-id="068e7-164">Especifica os módulos que devem estar no estado de sessão global.</span><span class="sxs-lookup"><span data-stu-id="068e7-164">Specifies modules that must be in the global session state.</span></span> <span data-ttu-id="068e7-165">Se os módulos necessários não estiverem no estado de sessão global, o PowerShell os importará.</span><span class="sxs-lookup"><span data-stu-id="068e7-165">If the required modules aren't in the global session state, PowerShell imports them.</span></span>

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

### <span data-ttu-id="068e7-166">-RequiredScripts</span><span class="sxs-lookup"><span data-stu-id="068e7-166">-RequiredScripts</span></span>

<span data-ttu-id="068e7-167">Especifica uma matriz de scripts necessários.</span><span class="sxs-lookup"><span data-stu-id="068e7-167">Specifies an array of required scripts.</span></span>

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

### <span data-ttu-id="068e7-168">-Marcas</span><span class="sxs-lookup"><span data-stu-id="068e7-168">-Tags</span></span>

<span data-ttu-id="068e7-169">Especifica uma matriz de marcas.</span><span class="sxs-lookup"><span data-stu-id="068e7-169">Specifies an array of tags.</span></span>

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

### <span data-ttu-id="068e7-170">-Version</span><span class="sxs-lookup"><span data-stu-id="068e7-170">-Version</span></span>

<span data-ttu-id="068e7-171">Especifica a versão do script.</span><span class="sxs-lookup"><span data-stu-id="068e7-171">Specifies the version of the script.</span></span>

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

### <span data-ttu-id="068e7-172">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="068e7-172">-WhatIf</span></span>

<span data-ttu-id="068e7-173">Mostra o que aconteceria se `New-ScriptFileInfo` for executado.</span><span class="sxs-lookup"><span data-stu-id="068e7-173">Shows what would happen if `New-ScriptFileInfo` runs.</span></span> <span data-ttu-id="068e7-174">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="068e7-174">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="068e7-175">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="068e7-175">CommonParameters</span></span>

<span data-ttu-id="068e7-176">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="068e7-176">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="068e7-177">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="068e7-177">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="068e7-178">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="068e7-178">INPUTS</span></span>

### <span data-ttu-id="068e7-179">System.String</span><span class="sxs-lookup"><span data-stu-id="068e7-179">System.String</span></span>

## <span data-ttu-id="068e7-180">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="068e7-180">OUTPUTS</span></span>

### <span data-ttu-id="068e7-181">System.Object</span><span class="sxs-lookup"><span data-stu-id="068e7-181">System.Object</span></span>

## <span data-ttu-id="068e7-182">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="068e7-182">NOTES</span></span>

## <span data-ttu-id="068e7-183">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="068e7-183">RELATED LINKS</span></span>

[<span data-ttu-id="068e7-184">about_Splatting</span><span class="sxs-lookup"><span data-stu-id="068e7-184">about_Splatting</span></span>](../Microsoft.Powershell.Core/About/about_splatting.md)

[<span data-ttu-id="068e7-185">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="068e7-185">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)

[<span data-ttu-id="068e7-186">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="068e7-186">Update-ScriptFileInfo</span></span>](Update-ScriptFileInfo.md)
