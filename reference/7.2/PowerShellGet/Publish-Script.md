---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/publish-script?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-Script
ms.openlocfilehash: 344a789c9daced51b549d562b7fd74677fe403dc
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "99597183"
---
# <span data-ttu-id="bdc59-102">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="bdc59-102">Publish-Script</span></span>

## <span data-ttu-id="bdc59-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="bdc59-103">SYNOPSIS</span></span>
<span data-ttu-id="bdc59-104">Publica um script.</span><span class="sxs-lookup"><span data-stu-id="bdc59-104">Publishes a script.</span></span>

## <span data-ttu-id="bdc59-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bdc59-105">SYNTAX</span></span>

### <span data-ttu-id="bdc59-106">PathParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="bdc59-106">PathParameterSet (Default)</span></span>

```
Publish-Script -Path <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="bdc59-107">LiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="bdc59-107">LiteralPathParameterSet</span></span>

```
Publish-Script -LiteralPath <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="bdc59-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bdc59-108">DESCRIPTION</span></span>

<span data-ttu-id="bdc59-109">O `Publish-Script` cmdlet publica o script especificado na galeria online.</span><span class="sxs-lookup"><span data-stu-id="bdc59-109">The `Publish-Script` cmdlet publishes the specified script to the online gallery.</span></span>

## <span data-ttu-id="bdc59-110">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="bdc59-110">EXAMPLES</span></span>

### <span data-ttu-id="bdc59-111">Exemplo 1: criar um arquivo de script, adicionar conteúdo a ele e publicá-lo</span><span class="sxs-lookup"><span data-stu-id="bdc59-111">Example 1: Create a script file, add content to it, and publish it</span></span>

<span data-ttu-id="bdc59-112">O `New-ScriptFileInfo` cmdlet cria um arquivo de script chamado `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="bdc59-112">The `New-ScriptFileInfo` cmdlet creates a script file named `Demo-Script.ps1`.</span></span> <span data-ttu-id="bdc59-113">`Get-Content` exibe o conteúdo de `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="bdc59-113">`Get-Content` displays the content of `Demo-Script.ps1`.</span></span> <span data-ttu-id="bdc59-114">O `Add-Content` cmdlet adiciona uma função e um fluxo de trabalho ao `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="bdc59-114">The `Add-Content` cmdlet adds a function and a workflow to `Demo-Script.ps1`.</span></span>

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

<span data-ttu-id="bdc59-115">O `Test-ScriptFileInfo` cmdlet é validado `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="bdc59-115">The `Test-ScriptFileInfo` cmdlet validates `Demo-Script.ps1`.</span></span> <span data-ttu-id="bdc59-116">O `Publish-Script` cmdlet publica o script no repositório **LocalRepo1** .</span><span class="sxs-lookup"><span data-stu-id="bdc59-116">The `Publish-Script` cmdlet publishes the script to the **LocalRepo1** repository.</span></span> <span data-ttu-id="bdc59-117">Por fim.</span><span class="sxs-lookup"><span data-stu-id="bdc59-117">Finally.</span></span> <span data-ttu-id="bdc59-118">`Find-Script` é usado para pesquisar `Demo-Script.ps1` no repositório **LocalRepo1** .</span><span class="sxs-lookup"><span data-stu-id="bdc59-118">`Find-Script` is used to search for `Demo-Script.ps1` in the **LocalRepo1** repository.</span></span>

## <span data-ttu-id="bdc59-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bdc59-119">PARAMETERS</span></span>

### <span data-ttu-id="bdc59-120">-Confirm</span><span class="sxs-lookup"><span data-stu-id="bdc59-120">-Confirm</span></span>

<span data-ttu-id="bdc59-121">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bdc59-121">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="bdc59-122">-Credential</span><span class="sxs-lookup"><span data-stu-id="bdc59-122">-Credential</span></span>

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

### <span data-ttu-id="bdc59-123">-Force</span><span class="sxs-lookup"><span data-stu-id="bdc59-123">-Force</span></span>

<span data-ttu-id="bdc59-124">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="bdc59-124">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="bdc59-125">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="bdc59-125">-LiteralPath</span></span>

<span data-ttu-id="bdc59-126">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="bdc59-126">Specifies a path to one or more locations.</span></span> <span data-ttu-id="bdc59-127">Ao contrário do parâmetro **path** , o valor do parâmetro **LiteralPath** é usado exatamente como inserido.</span><span class="sxs-lookup"><span data-stu-id="bdc59-127">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as entered.</span></span> <span data-ttu-id="bdc59-128">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="bdc59-128">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="bdc59-129">Se o caminho incluir caracteres de escape, coloque-os entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="bdc59-129">If the path includes escape characters, enclose them in single quotation marks.</span></span> <span data-ttu-id="bdc59-130">As aspas simples instruem o Windows PowerShell a nunca interpretar caracteres como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="bdc59-130">Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="bdc59-131">-NuGetApiKey</span><span class="sxs-lookup"><span data-stu-id="bdc59-131">-NuGetApiKey</span></span>

<span data-ttu-id="bdc59-132">Especifica a chave de API que você deseja usar para publicar um script na galeria online.</span><span class="sxs-lookup"><span data-stu-id="bdc59-132">Specifies the API key that you want to use to publish a script to the online gallery.</span></span> <span data-ttu-id="bdc59-133">A chave de API é parte do seu perfil na galeria online.</span><span class="sxs-lookup"><span data-stu-id="bdc59-133">The API key is part of your profile in the online gallery.</span></span> <span data-ttu-id="bdc59-134">Para obter mais informações, consulte [Gerenciando chaves de API](/powershell/scripting/gallery/how-to/managing-profile/creating-apikeys).</span><span class="sxs-lookup"><span data-stu-id="bdc59-134">For more information see [Managing API keys](/powershell/scripting/gallery/how-to/managing-profile/creating-apikeys).</span></span>

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

### <span data-ttu-id="bdc59-135">-Path</span><span class="sxs-lookup"><span data-stu-id="bdc59-135">-Path</span></span>

<span data-ttu-id="bdc59-136">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="bdc59-136">Specifies a path to one or more locations.</span></span> <span data-ttu-id="bdc59-137">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="bdc59-137">Wildcards are permitted.</span></span> <span data-ttu-id="bdc59-138">O local padrão é o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="bdc59-138">The default location is the current directory.</span></span>

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

### <span data-ttu-id="bdc59-139">-Repositório</span><span class="sxs-lookup"><span data-stu-id="bdc59-139">-Repository</span></span>

<span data-ttu-id="bdc59-140">Especifica o nome amigável de um repositório que foi registrado pela execução `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="bdc59-140">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span>

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

### <span data-ttu-id="bdc59-141">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="bdc59-141">-WhatIf</span></span>

<span data-ttu-id="bdc59-142">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="bdc59-142">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="bdc59-143">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="bdc59-143">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="bdc59-144">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bdc59-144">CommonParameters</span></span>

<span data-ttu-id="bdc59-145">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bdc59-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bdc59-146">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bdc59-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bdc59-147">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="bdc59-147">INPUTS</span></span>

### <span data-ttu-id="bdc59-148">System.String</span><span class="sxs-lookup"><span data-stu-id="bdc59-148">System.String</span></span>

### <span data-ttu-id="bdc59-149">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="bdc59-149">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="bdc59-150">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="bdc59-150">OUTPUTS</span></span>

### <span data-ttu-id="bdc59-151">System.Object</span><span class="sxs-lookup"><span data-stu-id="bdc59-151">System.Object</span></span>

## <span data-ttu-id="bdc59-152">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="bdc59-152">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bdc59-153">A partir de abril de 2020, a Galeria do PowerShell não dará mais suporte às versões 1.0 e 1.1 do protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="bdc59-153">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="bdc59-154">Se você não estiver usando o TLS 1.2 ou posterior, receberá um erro ao tentar acessar a Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bdc59-154">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="bdc59-155">Use o seguinte comando para garantir que esteja usando o TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="bdc59-155">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="bdc59-156">Para obter mais informações, confira o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bdc59-156">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="bdc59-157">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="bdc59-157">RELATED LINKS</span></span>

[<span data-ttu-id="bdc59-158">Find-Script</span><span class="sxs-lookup"><span data-stu-id="bdc59-158">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="bdc59-159">Install-Script</span><span class="sxs-lookup"><span data-stu-id="bdc59-159">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="bdc59-160">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="bdc59-160">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="bdc59-161">Save-Script</span><span class="sxs-lookup"><span data-stu-id="bdc59-161">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="bdc59-162">Update-Script</span><span class="sxs-lookup"><span data-stu-id="bdc59-162">Update-Script</span></span>](Update-Script.md)
