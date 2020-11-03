---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/test-scriptfileinfo?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ScriptFileInfo
ms.openlocfilehash: 4b02b853da5f42eb76d63ec38f77852df838bbe0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193474"
---
# <span data-ttu-id="8acff-103">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="8acff-103">Test-ScriptFileInfo</span></span>

## <span data-ttu-id="8acff-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="8acff-104">SYNOPSIS</span></span>
<span data-ttu-id="8acff-105">Valida um bloco de comentário para um script.</span><span class="sxs-lookup"><span data-stu-id="8acff-105">Validates a comment block for a script.</span></span>

## <span data-ttu-id="8acff-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8acff-106">SYNTAX</span></span>

### <span data-ttu-id="8acff-107">PathParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="8acff-107">PathParameterSet (Default)</span></span>

```
Test-ScriptFileInfo [-Path] <String> [<CommonParameters>]
```

### <span data-ttu-id="8acff-108">LiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="8acff-108">LiteralPathParameterSet</span></span>

```
Test-ScriptFileInfo -LiteralPath <String> [<CommonParameters>]
```

## <span data-ttu-id="8acff-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8acff-109">DESCRIPTION</span></span>

<span data-ttu-id="8acff-110">O cmdlet **Test-ScriptFileInfo** valida o bloco de comentário no início de um script que será publicado com o cmdlet Publish-Script.</span><span class="sxs-lookup"><span data-stu-id="8acff-110">The **Test-ScriptFileInfo** cmdlet validates the comment block at the beginning of a script that will be published with the Publish-Script cmdlet.</span></span>
<span data-ttu-id="8acff-111">Se o bloco de comentários tiver um erro, esse cmdlet retornará informações sobre onde o erro está localizado ou como corrigi-lo.</span><span class="sxs-lookup"><span data-stu-id="8acff-111">If the comment block has an error, this cmdlet returns information about where the error is located or how to correct it.</span></span>

## <span data-ttu-id="8acff-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="8acff-112">EXAMPLES</span></span>

### <span data-ttu-id="8acff-113">Exemplo 1: testar um arquivo de script</span><span class="sxs-lookup"><span data-stu-id="8acff-113">Example 1: Test a script file</span></span>

```
PS C:\> Test-ScriptFileInfo -Path "C:\temp\temp_scripts\New-ScriptFile.ps1"
Version    Name                      Author               Description
-------    ----                      ------               -----------
1.0        New-ScriptFile            pattif               my new script file test
```

<span data-ttu-id="8acff-114">Esse comando testa o arquivo de script New-ScriptFile.ps1 e exibe os resultados.</span><span class="sxs-lookup"><span data-stu-id="8acff-114">This command tests the New-ScriptFile.ps1 script file and displays the results.</span></span>
<span data-ttu-id="8acff-115">O arquivo de script inclui metadados válidos.</span><span class="sxs-lookup"><span data-stu-id="8acff-115">The script file includes valid metadata.</span></span>

### <span data-ttu-id="8acff-116">Exemplo 2: testar um arquivo de script que tem valores para todas as propriedades de metadados</span><span class="sxs-lookup"><span data-stu-id="8acff-116">Example 2: Test a script file that has values for all metadata properties</span></span>

```
PS C:\> Test-ScriptFileInfo -Path "D:\code\Test-Runbook.ps1" | Format-List *
Name                       : Test-Runbook
Path                       : D:\code\Test-Runbook.ps1
ScriptBase                 : D:\code
ReleaseNotes               : {contoso script now supports following features, Feature 1, Feature 2, Feature 3...}
Version                    : 1.0
Guid                       : eb246b19-17da-4392-8c89-7c280f69ad0e
Author                     : pattif
CompanyName                : Microsoft Corporation
Copyright                  : 2015 Microsoft Corporation. All rights reserved.
Tags                       : {Tag1, Tag2, Tag3}
LicenseUri                 : https://contoso.com/License
ProjectUri                 : https://contoso.com/
IconUri                    : https://contoso.com/MyScriptIcon
ExternalModuleDependencies : ExternalModule1
RequiredScripts            : {Start-WFContosoServer, Stop-ContosoServerScript}
ExternalScriptDependencies : Stop-ContosoServerScript
Description                : Contoso Script example
RequiredModules            : {RequiredModule1, @{ ModuleName = 'RequiredModule2'; ModuleVersion = '1.0' }, @{ ModuleName = 'RequiredModule3'; RequiredVersion = '2.0' }, ExternalModule1}
ExportedCommands           : {Test-WebUri, ValidateAndAdd-PSScriptInfoEntry, Get-PSScriptInfo, My-Workflow...}
ExportedFunctions          : {Test-WebUri, ValidateAndAdd-PSScriptInfoEntry, Get-PSScriptInfo, My-AdvPSCmdlet}
ExportedWorkflows          : My-Workflow
```

<span data-ttu-id="8acff-117">Esse comando testa o arquivo de script Test-Runbook.ps1 e usa o operador de pipeline para passar os resultados para o cmdlet Format-List para formatar os resultados.</span><span class="sxs-lookup"><span data-stu-id="8acff-117">This command tests the script file Test-Runbook.ps1 and uses the pipeline operator to pass the results to the Format-List cmdlet to format the results.</span></span>

### <span data-ttu-id="8acff-118">Exemplo 3: testar um arquivo de script que não tem metadados</span><span class="sxs-lookup"><span data-stu-id="8acff-118">Example 3: Test a script file that has no metadata</span></span>

```
PS C:\> Test-ScriptFileInfo -Path "D:\code\Hello-World.ps1"
Test-ScriptFileInfo : Script 'D:\code\Hello-World.ps1' is missing required metadata properties. Verify that the script file has Version, Description
and Author properties. You can use the Update-ScriptFileInfo or New-ScriptFileInfo cmdlet to add or update the PSScriptInfo to the script file.
At line:1 char:1
+ Test-ScriptFileInfo D:\code\Hello-World.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : InvalidArgument: (D:\code\Hello-World.ps1:String) [Test-ScriptFileInfo], ArgumentException

+ FullyQualifiedErrorId : MissingRequiredPSScriptInfoProperties,Test-ScriptFile
```

<span data-ttu-id="8acff-119">Este comando testa o arquivo de script Hello-World.ps1, que não tem metadados associados a ele.</span><span class="sxs-lookup"><span data-stu-id="8acff-119">This command tests the script file Hello-World.ps1, which has no metadata associated with it.</span></span>

## <span data-ttu-id="8acff-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8acff-120">PARAMETERS</span></span>

### <span data-ttu-id="8acff-121">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="8acff-121">-LiteralPath</span></span>

<span data-ttu-id="8acff-122">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="8acff-122">Specifies a path to one or more locations.</span></span>
<span data-ttu-id="8acff-123">Ao contrário do parâmetro *path* , o valor do parâmetro *LiteralPath* é usado exatamente como ele é inserido.</span><span class="sxs-lookup"><span data-stu-id="8acff-123">Unlike the *Path* parameter, the value of the *LiteralPath* parameter is used exactly as it is entered.</span></span>
<span data-ttu-id="8acff-124">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="8acff-124">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="8acff-125">Se o caminho incluir caracteres de escape, coloque-os entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="8acff-125">If the path includes escape characters, enclose them in single quotation marks.</span></span>
<span data-ttu-id="8acff-126">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="8acff-126">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="8acff-127">-Path</span><span class="sxs-lookup"><span data-stu-id="8acff-127">-Path</span></span>

<span data-ttu-id="8acff-128">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="8acff-128">Specifies a path to one or more locations.</span></span>
<span data-ttu-id="8acff-129">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="8acff-129">Wildcards are permitted.</span></span>
<span data-ttu-id="8acff-130">O local padrão é o diretório atual (.).</span><span class="sxs-lookup"><span data-stu-id="8acff-130">The default location is the current directory (.).</span></span>

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

### <span data-ttu-id="8acff-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8acff-131">CommonParameters</span></span>

<span data-ttu-id="8acff-132">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8acff-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8acff-133">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8acff-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8acff-134">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="8acff-134">INPUTS</span></span>

### <span data-ttu-id="8acff-135">System.String</span><span class="sxs-lookup"><span data-stu-id="8acff-135">System.String</span></span>

## <span data-ttu-id="8acff-136">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="8acff-136">OUTPUTS</span></span>

### <span data-ttu-id="8acff-137">System.Object</span><span class="sxs-lookup"><span data-stu-id="8acff-137">System.Object</span></span>

## <span data-ttu-id="8acff-138">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="8acff-138">NOTES</span></span>

## <span data-ttu-id="8acff-139">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="8acff-139">RELATED LINKS</span></span>

[<span data-ttu-id="8acff-140">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="8acff-140">New-ScriptFileInfo</span></span>](New-ScriptFileInfo.md)

[<span data-ttu-id="8acff-141">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="8acff-141">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="8acff-142">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="8acff-142">Update-ScriptFileInfo</span></span>](Update-ScriptFileInfo.md)

