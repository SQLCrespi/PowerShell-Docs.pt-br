---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/publish-script?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-Script
ms.openlocfilehash: 95dadef6a1cbc4e730fed21fd8bda629f4c04563
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194299"
---
# <span data-ttu-id="9a775-103">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="9a775-103">Publish-Script</span></span>

## <span data-ttu-id="9a775-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="9a775-104">SYNOPSIS</span></span>
<span data-ttu-id="9a775-105">Publica um script.</span><span class="sxs-lookup"><span data-stu-id="9a775-105">Publishes a script.</span></span>

## <span data-ttu-id="9a775-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9a775-106">SYNTAX</span></span>

### <span data-ttu-id="9a775-107">PathParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="9a775-107">PathParameterSet (Default)</span></span>

```
Publish-Script -Path <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9a775-108">LiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="9a775-108">LiteralPathParameterSet</span></span>

```
Publish-Script -LiteralPath <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9a775-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9a775-109">DESCRIPTION</span></span>

<span data-ttu-id="9a775-110">O `Publish-Script` cmdlet publica o script especificado na galeria online.</span><span class="sxs-lookup"><span data-stu-id="9a775-110">The `Publish-Script` cmdlet publishes the specified script to the online gallery.</span></span>

## <span data-ttu-id="9a775-111">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="9a775-111">EXAMPLES</span></span>

### <span data-ttu-id="9a775-112">Exemplo 1: criar um arquivo de script, adicionar conteúdo a ele e publicá-lo</span><span class="sxs-lookup"><span data-stu-id="9a775-112">Example 1: Create a script file, add content to it, and publish it</span></span>

<span data-ttu-id="9a775-113">O `New-ScriptFileInfo` cmdlet cria um arquivo de script chamado `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="9a775-113">The `New-ScriptFileInfo` cmdlet creates a script file named `Demo-Script.ps1`.</span></span> <span data-ttu-id="9a775-114">`Get-Content` exibe o conteúdo de `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="9a775-114">`Get-Content` displays the content of `Demo-Script.ps1`.</span></span> <span data-ttu-id="9a775-115">O `Add-Content` cmdlet adiciona uma função e um fluxo de trabalho ao `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="9a775-115">The `Add-Content` cmdlet adds a function and a workflow to `Demo-Script.ps1`.</span></span>

```powershell
$newScriptInfo = @{
  Path = 'D:\ScriptSharingDemo\Demo-Script.ps1'
  Version = '1.0'
  Author = 'author@contoso.com'
  Description = "my test script file description goes here"
}
New-ScriptFileInfo @newScriptInfo
Get-Content -Path $newScriptInfo.Path
```

```Output
<#PSScriptInfo

.VERSION 1.0

.AUTHOR pattif@microsoft.com

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
#>

<#
.DESCRIPTION
 my test script file description goes here
#>
Param()
```

```powershell
Add-Content -Path D:\ScriptSharingDemo\Demo-Script.ps1 -Value @"

Function Demo-ScriptFunction { 'Demo-ScriptFunction' }

Workflow Demo-ScriptWorkflow { 'Demo-ScriptWorkflow' }

Demo-ScriptFunction
Demo-ScriptWorkflow
"@
Test-ScriptFileInfo -Path D:\ScriptSharingDemo\Demo-Script.ps1
```

```Output
Version    Name                 Author                   Description
-------    ----                 ------                   -----------
1.0        Demo-Script          author@contoso.com       my test script file description goes here
```

```powershell
Publish-Script -Path D:\ScriptSharingDemo\Demo-Script.ps1 -Repository LocalRepo1
Find-Script -Repository LocalRepo1 -Name "Demo-Script"
```

```Output
Version    Name                 Type       Repository    Description
-------    ----                 ----       ----------    -----------
1.0        Demo-Script          Script     LocalRepo1    my test script file description goes here
```

<span data-ttu-id="9a775-116">O `Test-ScriptFileInfo` cmdlet é validado `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="9a775-116">The `Test-ScriptFileInfo` cmdlet validates `Demo-Script.ps1`.</span></span> <span data-ttu-id="9a775-117">O `Publish-Script` cmdlet publica o script no repositório **LocalRepo1** .</span><span class="sxs-lookup"><span data-stu-id="9a775-117">The `Publish-Script` cmdlet publishes the script to the **LocalRepo1** repository.</span></span> <span data-ttu-id="9a775-118">Por fim.</span><span class="sxs-lookup"><span data-stu-id="9a775-118">Finally.</span></span> <span data-ttu-id="9a775-119">`Find-Script` é usado para pesquisar `Demo-Script.ps1` no repositório **LocalRepo1** .</span><span class="sxs-lookup"><span data-stu-id="9a775-119">`Find-Script` is used to search for `Demo-Script.ps1` in the **LocalRepo1** repository.</span></span>

## <span data-ttu-id="9a775-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9a775-120">PARAMETERS</span></span>

### <span data-ttu-id="9a775-121">-Credential</span><span class="sxs-lookup"><span data-stu-id="9a775-121">-Credential</span></span>

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

### <span data-ttu-id="9a775-122">-Force</span><span class="sxs-lookup"><span data-stu-id="9a775-122">-Force</span></span>

<span data-ttu-id="9a775-123">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="9a775-123">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="9a775-124">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="9a775-124">-LiteralPath</span></span>

<span data-ttu-id="9a775-125">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="9a775-125">Specifies a path to one or more locations.</span></span> <span data-ttu-id="9a775-126">Ao contrário do parâmetro **path** , o valor do parâmetro **LiteralPath** é usado exatamente como inserido.</span><span class="sxs-lookup"><span data-stu-id="9a775-126">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as entered.</span></span> <span data-ttu-id="9a775-127">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="9a775-127">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="9a775-128">Se o caminho incluir caracteres de escape, coloque-os entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="9a775-128">If the path includes escape characters, enclose them in single quotation marks.</span></span> <span data-ttu-id="9a775-129">As aspas simples instruem o Windows PowerShell a nunca interpretar caracteres como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="9a775-129">Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPathParameterSet
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9a775-130">-NuGetApiKey</span><span class="sxs-lookup"><span data-stu-id="9a775-130">-NuGetApiKey</span></span>

<span data-ttu-id="9a775-131">Especifica a chave de API que você deseja usar para publicar um script na galeria online.</span><span class="sxs-lookup"><span data-stu-id="9a775-131">Specifies the API key that you want to use to publish a script to the online gallery.</span></span> <span data-ttu-id="9a775-132">A chave de API é parte do seu perfil na galeria online.</span><span class="sxs-lookup"><span data-stu-id="9a775-132">The API key is part of your profile in the online gallery.</span></span> <span data-ttu-id="9a775-133">Para obter mais informações, consulte [Gerenciando chaves de API](/powershell/scripting/gallery/how-to/managing-profile/creating-apikeys).</span><span class="sxs-lookup"><span data-stu-id="9a775-133">For more information see [Managing API keys](/powershell/scripting/gallery/how-to/managing-profile/creating-apikeys).</span></span>

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

### <span data-ttu-id="9a775-134">-Path</span><span class="sxs-lookup"><span data-stu-id="9a775-134">-Path</span></span>

<span data-ttu-id="9a775-135">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="9a775-135">Specifies a path to one or more locations.</span></span> <span data-ttu-id="9a775-136">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="9a775-136">Wildcards are permitted.</span></span> <span data-ttu-id="9a775-137">O local padrão é o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="9a775-137">The default location is the current directory.</span></span>

```yaml
Type: System.String
Parameter Sets: PathParameterSet
Aliases:

Required: True
Position: Named
Default value: <Current location>
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="9a775-138">-Repositório</span><span class="sxs-lookup"><span data-stu-id="9a775-138">-Repository</span></span>

<span data-ttu-id="9a775-139">Especifica o nome amigável de um repositório que foi registrado pela execução `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="9a775-139">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span>

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

### <span data-ttu-id="9a775-140">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9a775-140">-Confirm</span></span>

<span data-ttu-id="9a775-141">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9a775-141">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="9a775-142">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9a775-142">-WhatIf</span></span>

<span data-ttu-id="9a775-143">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="9a775-143">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="9a775-144">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="9a775-144">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="9a775-145">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9a775-145">CommonParameters</span></span>

<span data-ttu-id="9a775-146">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9a775-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9a775-147">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9a775-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9a775-148">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="9a775-148">INPUTS</span></span>

### <span data-ttu-id="9a775-149">System.String</span><span class="sxs-lookup"><span data-stu-id="9a775-149">System.String</span></span>

### <span data-ttu-id="9a775-150">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="9a775-150">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="9a775-151">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="9a775-151">OUTPUTS</span></span>

### <span data-ttu-id="9a775-152">System.Object</span><span class="sxs-lookup"><span data-stu-id="9a775-152">System.Object</span></span>

## <span data-ttu-id="9a775-153">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="9a775-153">NOTES</span></span>

## <span data-ttu-id="9a775-154">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="9a775-154">RELATED LINKS</span></span>

[<span data-ttu-id="9a775-155">Find-Script</span><span class="sxs-lookup"><span data-stu-id="9a775-155">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="9a775-156">Install-Script</span><span class="sxs-lookup"><span data-stu-id="9a775-156">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="9a775-157">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="9a775-157">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="9a775-158">Save-Script</span><span class="sxs-lookup"><span data-stu-id="9a775-158">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="9a775-159">Update-Script</span><span class="sxs-lookup"><span data-stu-id="9a775-159">Update-Script</span></span>](Update-Script.md)
