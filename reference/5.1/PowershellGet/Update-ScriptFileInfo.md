---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/09/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-scriptfileinfo?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-ScriptFileInfo
ms.openlocfilehash: bb36d5a1acc8331762513219e823bf91304b6b45
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194107"
---
# <span data-ttu-id="5c40a-103">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="5c40a-103">Update-ScriptFileInfo</span></span>

## <span data-ttu-id="5c40a-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="5c40a-104">SYNOPSIS</span></span>
<span data-ttu-id="5c40a-105">Atualiza informações de um script.</span><span class="sxs-lookup"><span data-stu-id="5c40a-105">Updates information for a script.</span></span>

## <span data-ttu-id="5c40a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5c40a-106">SYNTAX</span></span>

### <span data-ttu-id="5c40a-107">PathParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="5c40a-107">PathParameterSet (Default)</span></span>

```
Update-ScriptFileInfo [-Path] <String> [-Version <String>] [-Author <String>] [-Guid <Guid>]
 [-Description <String>] [-CompanyName <String>] [-Copyright <String>] [-RequiredModules <Object[]>]
 [-ExternalModuleDependencies <String[]>] [-RequiredScripts <String[]>]
 [-ExternalScriptDependencies <String[]>] [-Tags <String[]>] [-ProjectUri <Uri>] [-LicenseUri <Uri>]
 [-IconUri <Uri>] [-ReleaseNotes <String[]>] [-PrivateData <String>] [-PassThru] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5c40a-108">LiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="5c40a-108">LiteralPathParameterSet</span></span>

```
Update-ScriptFileInfo [-LiteralPath] <String> [-Version <String>] [-Author <String>] [-Guid <Guid>]
 [-Description <String>] [-CompanyName <String>] [-Copyright <String>] [-RequiredModules <Object[]>]
 [-ExternalModuleDependencies <String[]>] [-RequiredScripts <String[]>]
 [-ExternalScriptDependencies <String[]>] [-Tags <String[]>] [-ProjectUri <Uri>] [-LicenseUri <Uri>]
 [-IconUri <Uri>] [-ReleaseNotes <String[]>] [-PrivateData <String>] [-PassThru] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="5c40a-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5c40a-109">DESCRIPTION</span></span>

<span data-ttu-id="5c40a-110">O `Update-ScriptFileInfo` cmdlet atualiza os valores de propriedade de um script.</span><span class="sxs-lookup"><span data-stu-id="5c40a-110">The `Update-ScriptFileInfo` cmdlet updates a script's property values.</span></span> <span data-ttu-id="5c40a-111">Por exemplo, os valores para versão, autor ou descrição.</span><span class="sxs-lookup"><span data-stu-id="5c40a-111">For example, the values for version, author, or description.</span></span>

## <span data-ttu-id="5c40a-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="5c40a-112">EXAMPLES</span></span>

### <span data-ttu-id="5c40a-113">Exemplo 1: atualizar a versão de um arquivo de script</span><span class="sxs-lookup"><span data-stu-id="5c40a-113">Example 1: Update the version of a script file</span></span>

<span data-ttu-id="5c40a-114">Neste exemplo, um arquivo de script existente é atualizado com novos valores de propriedade.</span><span class="sxs-lookup"><span data-stu-id="5c40a-114">In this example, an existing script file is updated with new property values.</span></span>

<span data-ttu-id="5c40a-115">Nivelamento é usado para passar parâmetros para o `Update-ScriptFileInfo` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5c40a-115">Splatting is used to pass parameters to the `Update-ScriptFileInfo` cmdlet.</span></span> <span data-ttu-id="5c40a-116">Para obter mais informações, consulte [about_Splatting](../Microsoft.Powershell.Core/About/about_splatting.md).</span><span class="sxs-lookup"><span data-stu-id="5c40a-116">For more information, see [about_Splatting](../Microsoft.Powershell.Core/About/about_splatting.md).</span></span>

```powershell
$Parms = @{
  Path = "C:\Test\Temp-Scriptfile.ps1"
  Version = "2.0"
  Author = "bob@contoso.com"
  CompanyName = "Contoso"
  Description = "This is the updated description"
  }
Update-ScriptFileInfo @Parms -PassThru
```

```Output
<#PSScriptInfo

.VERSION 2.0

.GUID 4609f00c-e850-4d3f-9c69-3741e56e4133

.AUTHOR bob@contoso.com

.COMPANYNAME Contoso

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
This is the updated description

#>
Param()
```

<span data-ttu-id="5c40a-117">`$Parms` armazena os valores de parâmetro para **caminho** , **versão** , **autor** , **CompanyName** e **Descrição** .</span><span class="sxs-lookup"><span data-stu-id="5c40a-117">`$Parms` stores the parameter values for **Path** , **Version** , **Author** , **CompanyName** , and **Description** .</span></span> <span data-ttu-id="5c40a-118">`Update-ScriptFileInfo` Obtém os valores de parâmetro de `@Parms` e atualiza o script.</span><span class="sxs-lookup"><span data-stu-id="5c40a-118">`Update-ScriptFileInfo` gets the parameter values from `@Parms` and updates the script.</span></span> <span data-ttu-id="5c40a-119">O parâmetro **PassThru** exibe o conteúdo do script no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5c40a-119">The **PassThru** parameter displays the script's contents in the PowerShell console.</span></span>

## <span data-ttu-id="5c40a-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5c40a-120">PARAMETERS</span></span>

### <span data-ttu-id="5c40a-121">-Autor</span><span class="sxs-lookup"><span data-stu-id="5c40a-121">-Author</span></span>

<span data-ttu-id="5c40a-122">Especifica o autor do script.</span><span class="sxs-lookup"><span data-stu-id="5c40a-122">Specifies the script author.</span></span>

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

### <span data-ttu-id="5c40a-123">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="5c40a-123">-CompanyName</span></span>

<span data-ttu-id="5c40a-124">Especifica a empresa ou o fornecedor que criou o script.</span><span class="sxs-lookup"><span data-stu-id="5c40a-124">Specifies the company or vendor who created the script.</span></span>

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

### <span data-ttu-id="5c40a-125">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5c40a-125">-Confirm</span></span>

<span data-ttu-id="5c40a-126">Solicita a confirmação antes de executar `Update-ScriptFileInfo` .</span><span class="sxs-lookup"><span data-stu-id="5c40a-126">Prompts you for confirmation before running `Update-ScriptFileInfo`.</span></span>

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

### <span data-ttu-id="5c40a-127">-Direitos autorais</span><span class="sxs-lookup"><span data-stu-id="5c40a-127">-Copyright</span></span>

<span data-ttu-id="5c40a-128">Especifica uma declaração de direitos autorais para o script.</span><span class="sxs-lookup"><span data-stu-id="5c40a-128">Specifies a copyright statement for the script.</span></span>

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

### <span data-ttu-id="5c40a-129">-Description</span><span class="sxs-lookup"><span data-stu-id="5c40a-129">-Description</span></span>

<span data-ttu-id="5c40a-130">Especifica uma descrição para o script.</span><span class="sxs-lookup"><span data-stu-id="5c40a-130">Specifies a description for the script.</span></span>

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

### <span data-ttu-id="5c40a-131">-ExternalModuleDependencies</span><span class="sxs-lookup"><span data-stu-id="5c40a-131">-ExternalModuleDependencies</span></span>

<span data-ttu-id="5c40a-132">Especifica uma matriz de dependências de módulo externas.</span><span class="sxs-lookup"><span data-stu-id="5c40a-132">Specifies an array of external module dependencies.</span></span>

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

### <span data-ttu-id="5c40a-133">-ExternalScriptDependencies</span><span class="sxs-lookup"><span data-stu-id="5c40a-133">-ExternalScriptDependencies</span></span>

<span data-ttu-id="5c40a-134">Especifica uma matriz de dependências de script externo.</span><span class="sxs-lookup"><span data-stu-id="5c40a-134">Specifies an array of external script dependencies.</span></span>

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

### <span data-ttu-id="5c40a-135">-Force</span><span class="sxs-lookup"><span data-stu-id="5c40a-135">-Force</span></span>

<span data-ttu-id="5c40a-136">Forças `Update-ScriptFileInfo` a serem executadas sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="5c40a-136">Forces `Update-ScriptFileInfo` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="5c40a-137">-GUID</span><span class="sxs-lookup"><span data-stu-id="5c40a-137">-Guid</span></span>

<span data-ttu-id="5c40a-138">Especifica uma ID exclusiva para um script.</span><span class="sxs-lookup"><span data-stu-id="5c40a-138">Specifies a unique ID for a script.</span></span>

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

### <span data-ttu-id="5c40a-139">-IconUri</span><span class="sxs-lookup"><span data-stu-id="5c40a-139">-IconUri</span></span>

<span data-ttu-id="5c40a-140">Especifica a URL de um ícone para o script.</span><span class="sxs-lookup"><span data-stu-id="5c40a-140">Specifies the URL of an icon for the script.</span></span> <span data-ttu-id="5c40a-141">O ícone especificado é exibido na página da Galeria da Web para o script.</span><span class="sxs-lookup"><span data-stu-id="5c40a-141">The specified icon is displayed on the gallery web page for the script.</span></span>

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

### <span data-ttu-id="5c40a-142">-LicenseUri</span><span class="sxs-lookup"><span data-stu-id="5c40a-142">-LicenseUri</span></span>

<span data-ttu-id="5c40a-143">Especifica a URL dos termos de licenciamento.</span><span class="sxs-lookup"><span data-stu-id="5c40a-143">Specifies the URL of licensing terms.</span></span>

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

### <span data-ttu-id="5c40a-144">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="5c40a-144">-LiteralPath</span></span>

<span data-ttu-id="5c40a-145">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="5c40a-145">Specifies a path to one or more locations.</span></span> <span data-ttu-id="5c40a-146">O valor do parâmetro **LiteralPath** é usado exatamente como ele é inserido.</span><span class="sxs-lookup"><span data-stu-id="5c40a-146">The **LiteralPath** parameter's value is used exactly as it's entered.</span></span> <span data-ttu-id="5c40a-147">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="5c40a-147">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="5c40a-148">Se o caminho incluir caracteres de escape, coloque-os entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="5c40a-148">If the path includes escape characters, enclose them in single quotation marks.</span></span> <span data-ttu-id="5c40a-149">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="5c40a-149">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPathParameterSet
Aliases: PSPath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="5c40a-150">-PassThru</span><span class="sxs-lookup"><span data-stu-id="5c40a-150">-PassThru</span></span>

<span data-ttu-id="5c40a-151">Retorna um objeto que representa o item com o qual você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="5c40a-151">Returns an object that represents the item with which you're working.</span></span> <span data-ttu-id="5c40a-152">Por padrão, o `Update-ScriptFileInfo` não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="5c40a-152">By default, `Update-ScriptFileInfo` doesn't generate any output.</span></span>

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

### <span data-ttu-id="5c40a-153">-Path</span><span class="sxs-lookup"><span data-stu-id="5c40a-153">-Path</span></span>

<span data-ttu-id="5c40a-154">Especifica o local do arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="5c40a-154">Specifies the script file's location.</span></span> <span data-ttu-id="5c40a-155">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="5c40a-155">Wildcards are permitted.</span></span>

```yaml
Type: System.String
Parameter Sets: PathParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="5c40a-156">-PrivateData</span><span class="sxs-lookup"><span data-stu-id="5c40a-156">-PrivateData</span></span>

<span data-ttu-id="5c40a-157">Especifica os dados privados do script.</span><span class="sxs-lookup"><span data-stu-id="5c40a-157">Specifies the private data for the script.</span></span>

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

### <span data-ttu-id="5c40a-158">-ProjectUri</span><span class="sxs-lookup"><span data-stu-id="5c40a-158">-ProjectUri</span></span>

<span data-ttu-id="5c40a-159">Especifica a URL de uma página da Web sobre este projeto.</span><span class="sxs-lookup"><span data-stu-id="5c40a-159">Specifies the URL of a web page about this project.</span></span>

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

### <span data-ttu-id="5c40a-160">-ReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="5c40a-160">-ReleaseNotes</span></span>

<span data-ttu-id="5c40a-161">Especifica uma matriz de cadeia de caracteres que contém notas de versão ou comentários que você deseja disponibilizar para esta versão do script.</span><span class="sxs-lookup"><span data-stu-id="5c40a-161">Specifies a string array that contains release notes or comments that you want available for this version of the script.</span></span>

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

### <span data-ttu-id="5c40a-162">-RequiredModules</span><span class="sxs-lookup"><span data-stu-id="5c40a-162">-RequiredModules</span></span>

<span data-ttu-id="5c40a-163">Especifica os módulos que devem estar no estado de sessão global.</span><span class="sxs-lookup"><span data-stu-id="5c40a-163">Specifies modules that must be in the global session state.</span></span> <span data-ttu-id="5c40a-164">Se os módulos necessários não estiverem no estado de sessão global, o PowerShell os importará.</span><span class="sxs-lookup"><span data-stu-id="5c40a-164">If the required modules aren't in the global session state, PowerShell imports them.</span></span>

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

### <span data-ttu-id="5c40a-165">-RequiredScripts</span><span class="sxs-lookup"><span data-stu-id="5c40a-165">-RequiredScripts</span></span>

<span data-ttu-id="5c40a-166">Especifica uma matriz de scripts necessários.</span><span class="sxs-lookup"><span data-stu-id="5c40a-166">Specifies an array of required scripts.</span></span>

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

### <span data-ttu-id="5c40a-167">-Marcas</span><span class="sxs-lookup"><span data-stu-id="5c40a-167">-Tags</span></span>

<span data-ttu-id="5c40a-168">Especifica uma matriz de marcas.</span><span class="sxs-lookup"><span data-stu-id="5c40a-168">Specifies an array of tags.</span></span>

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

### <span data-ttu-id="5c40a-169">-Version</span><span class="sxs-lookup"><span data-stu-id="5c40a-169">-Version</span></span>

<span data-ttu-id="5c40a-170">Especifica a versão do script.</span><span class="sxs-lookup"><span data-stu-id="5c40a-170">Specifies the script's version.</span></span>

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

### <span data-ttu-id="5c40a-171">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5c40a-171">-WhatIf</span></span>

<span data-ttu-id="5c40a-172">Mostra o que aconteceria se `Update-ScriptFileInfo` for executado.</span><span class="sxs-lookup"><span data-stu-id="5c40a-172">Shows what would happen if `Update-ScriptFileInfo` runs.</span></span> <span data-ttu-id="5c40a-173">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="5c40a-173">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="5c40a-174">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5c40a-174">CommonParameters</span></span>

<span data-ttu-id="5c40a-175">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5c40a-175">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5c40a-176">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5c40a-176">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5c40a-177">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="5c40a-177">INPUTS</span></span>

## <span data-ttu-id="5c40a-178">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="5c40a-178">OUTPUTS</span></span>

## <span data-ttu-id="5c40a-179">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="5c40a-179">NOTES</span></span>

<span data-ttu-id="5c40a-180">Use o `Test-ScriptFileInfo` cmdlet para validar os metadados de um script.</span><span class="sxs-lookup"><span data-stu-id="5c40a-180">Use the `Test-ScriptFileInfo` cmdlet to validate a script's metadata.</span></span> <span data-ttu-id="5c40a-181">Os scripts devem incluir valores para versão, GUID, descrição e autor.</span><span class="sxs-lookup"><span data-stu-id="5c40a-181">Scripts must include values for version, GUID, description, and author.</span></span>

## <span data-ttu-id="5c40a-182">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="5c40a-182">RELATED LINKS</span></span>

[<span data-ttu-id="5c40a-183">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="5c40a-183">New-ScriptFileInfo</span></span>](New-ScriptFileInfo.md)

[<span data-ttu-id="5c40a-184">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="5c40a-184">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)
