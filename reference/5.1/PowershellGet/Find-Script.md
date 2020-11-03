---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/find-script?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Script
ms.openlocfilehash: 21b8dc249c93ae68ad3e43f998ede5dfe7a82766
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193616"
---
# <span data-ttu-id="74034-103">Find-Script</span><span class="sxs-lookup"><span data-stu-id="74034-103">Find-Script</span></span>

## <span data-ttu-id="74034-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="74034-104">SYNOPSIS</span></span>
<span data-ttu-id="74034-105">Localiza um script.</span><span class="sxs-lookup"><span data-stu-id="74034-105">Finds a script.</span></span>

## <span data-ttu-id="74034-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="74034-106">SYNTAX</span></span>

```
Find-Script [[-Name] <String[]>] [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-AllVersions] [-IncludeDependencies] [-Filter <String>] [-Tag <String[]>]
 [-Includes <String[]>] [-Command <String[]>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Repository <String[]>] [-Credential <PSCredential>] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="74034-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="74034-107">DESCRIPTION</span></span>

<span data-ttu-id="74034-108">O cmdlet **Find-script** localiza um script especificado em repositórios registrados.</span><span class="sxs-lookup"><span data-stu-id="74034-108">The **Find-Script** cmdlet finds a specified script in registered repositories.</span></span>

## <span data-ttu-id="74034-109">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="74034-109">EXAMPLES</span></span>

### <span data-ttu-id="74034-110">Exemplo 1: localizar todos os scripts disponíveis</span><span class="sxs-lookup"><span data-stu-id="74034-110">Example 1: Find all available scripts</span></span>

```
PS C:\> Find-Script
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Fabrikam-ClientScript               Script     LocalRepo1           Description for the Fabrikam-ClientScript script
2.5        Fabrikam-Script                     Script     LocalRepo1           Description for the Fabrikam-Script script
2.5        Fabrikam-ServerScript               Script     LocalRepo1           Description for the Fabrikam-ServerScript script
2.5        Required-Script1                    Script     LocalRepo1           Description for the Required-Script1 script
2.5        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
2.5        Required-Script3                    Script     LocalRepo1           Description for the Required-Script3 script
2.0        Script-WithDependencies1            Script     LocalRepo1           Description for the Script-WithDependencies1 script
2.0        Script-WithDependencies2            Script     LocalRepo1           Description for the Script-WithDependencies2 script
2.0        Start-WFContosoServer               Script     LocalRepo1           Start-WFContosoServer Script example
2.1        Test-Script1                        Script     LocalRepo1           Test-Script1 Script example
2.0        Test-Script2                        Script     LocalRepo1           Test-Script2 Script example
1.0        TestRunbook                         Script     LocalRepo1           Contoso Script example
```

<span data-ttu-id="74034-111">Esse comando localiza todos os scripts disponíveis.</span><span class="sxs-lookup"><span data-stu-id="74034-111">This command finds all available scripts.</span></span>

### <span data-ttu-id="74034-112">Exemplo 2: localizar um script por nome</span><span class="sxs-lookup"><span data-stu-id="74034-112">Example 2: Find a script by name</span></span>

```
PS C:\> Find-Script -Name "Start-WFContosoServer"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.0        Start-WFContosoServer               Script     LocalRepo1           Start-WFContosoServer Script example
```

<span data-ttu-id="74034-113">Esse comando localiza o script chamado start-WFContosoServer.</span><span class="sxs-lookup"><span data-stu-id="74034-113">This command find the script named Start-WFContosoServer.</span></span>

### <span data-ttu-id="74034-114">Exemplo 3: localizar um script por nome, versão necessária e de um repositório especificado</span><span class="sxs-lookup"><span data-stu-id="74034-114">Example 3: Find a script by name, required version, and from a specified repository</span></span>

```
PS C:\> Find-Script -Name "Required-Script2" -RequiredVersion 2.0 -Repository "LocalRepo01"
```

<span data-ttu-id="74034-115">Esse comando localiza um script por nome e a versão necessária no repositório LocalRepo01.</span><span class="sxs-lookup"><span data-stu-id="74034-115">This command finds a script by name and required version in the LocalRepo01 repository.</span></span>

### <span data-ttu-id="74034-116">Exemplo 4: localizar um script e formatar a saída como uma lista</span><span class="sxs-lookup"><span data-stu-id="74034-116">Example 4: Find a script and format the output as a list</span></span>

```
PS C:\> Find-Script -Name "Required-Script2" -RequiredVersion 2.0 -Repository "LocalRepo1" | Format-List * -Force
Name                       : Required-Script2
Version                    : 2.0
Type                       : Script
Description                : Description for the Required-Script2 script
Author                     : pattif
CompanyName                : Microsoft Corporation
Copyright                  : 2015 Microsoft Corporation. All rights reserved.
PublishedDate              : 8/14/2015 2:37:01 PM
LicenseUri                 : http://required-script2.com/license
ProjectUri                 : http://required-script2.com/
IconUri                    : http://required-script2.com/icon
Tags                       : {, Tag1, Tag2, Tag-Required-Script2-2.0...}
Includes                   : {Function, DscResource, Cmdlet, Command}
PowerShellGetFormatVersion :
ReleaseNotes               : Required-Script2 release notes
Dependencies               : {}
RepositorySourceLocation   : C:\MyLocalRepo
Repository                 : LocalRepo01
PackageManagementProvider  : NuGet
```

<span data-ttu-id="74034-117">Esse comando localiza Required-Script2 no repositório LocalRepo1 e, em seguida, passa o objeto **PSRepositoryItemInfo** resultante para o cmdlet Format-List.</span><span class="sxs-lookup"><span data-stu-id="74034-117">This command finds Required-Script2 in the LocalRepo1 repository, and then passes the resulting **PSRepositoryItemInfo** object to the Format-List cmdlet.</span></span>

### <span data-ttu-id="74034-118">Exemplo 5: localizar um script no intervalo de versão especificado</span><span class="sxs-lookup"><span data-stu-id="74034-118">Example 5: Find a script in the specified version range</span></span>

```
PS C:\> Find-Script -Name "Required-Script2" -MinimumVersion 2.1 -MaximumVersion 2.5 -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
```

<span data-ttu-id="74034-119">Esse comando localiza todas as versões de RequiredScript2 entre as versões 2,1 e 2,5 no repositório LocalRepo1.</span><span class="sxs-lookup"><span data-stu-id="74034-119">This command finds all versions of RequiredScript2 between versions 2.1 and 2.5 in the LocalRepo1 respository.</span></span>

### <span data-ttu-id="74034-120">Exemplo 6: localizar todas as versões de um script</span><span class="sxs-lookup"><span data-stu-id="74034-120">Example 6: Find all versions of a script</span></span>

```
PS C:\> Find-Script -Name "Required-Script02" -AllVersions
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
1.0        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
1.5        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
2.0        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
2.5        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
```

<span data-ttu-id="74034-121">Esse comando localiza todas as versões de Required-Script02.</span><span class="sxs-lookup"><span data-stu-id="74034-121">This command finds all versions of Required-Script02.</span></span>

### <span data-ttu-id="74034-122">Exemplo 7: localizar um script e suas dependências</span><span class="sxs-lookup"><span data-stu-id="74034-122">Example 7: Find a script and its dependencies</span></span>

```
PS C:\> Find-Script -Name "Script-WithDependencies1" -IncludeDependencies -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
1.0        Script-WithDependencies1            Script     LocalRepo1           Description for the Script-WithDependencies1 script
2.0        RequiredModule3                     Script     LocalRepo1           RequiredModule3 module
2.5        Required-Script1                    Script     LocalRepo1           Description for the Required-Script1 script
2.5        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
```

<span data-ttu-id="74034-123">Esse comando localiza um script e suas dependências.</span><span class="sxs-lookup"><span data-stu-id="74034-123">This command finds a script and its dependencies.</span></span>

### <span data-ttu-id="74034-124">Exemplo 8: localizar scripts com a marca especificada</span><span class="sxs-lookup"><span data-stu-id="74034-124">Example 8: Find scripts with the specified tag</span></span>

```
PS C:\> Find-Script -Tag "Tag1" -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
1.0        Fabrikam-ClientScript               Script     LocalRepo1           Description for the Fabrikam-ClientScript script
```

<span data-ttu-id="74034-125">Esse comando localiza scripts que têm a marca da tag1 no repositório LocalRepo1</span><span class="sxs-lookup"><span data-stu-id="74034-125">This command finds scripts that have the tag Tag1 in the LocalRepo1 repository</span></span>

### <span data-ttu-id="74034-126">Exemplo 9: localizar scripts com o nome de comando especificado</span><span class="sxs-lookup"><span data-stu-id="74034-126">Example 9: Find scripts with specified command name</span></span>

```
PS C:\> Find-Script -Command Test-FunctionFromScript_Required-Script3 -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script3                    Script     LocalRepo1           Description for the Required-Script3 script
```

<span data-ttu-id="74034-127">Esse comando localiza um script que contém o nome do comando especificado.</span><span class="sxs-lookup"><span data-stu-id="74034-127">This command finds a script that contains the specified command name.</span></span>

### <span data-ttu-id="74034-128">Exemplo 10: localizar scripts com fluxos de trabalho</span><span class="sxs-lookup"><span data-stu-id="74034-128">Example 10: Find scripts with workflows</span></span>

```
PS C:\> Find-Script -Includes "Workflow" -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Fabrikam-ClientScript               Script     LocalRepo1           Description for the Fabrikam-ClientScript script
1.0        Fabrikam-Script                     Script     LocalRepo1           Description for the Fabrikam-Script script
```

<span data-ttu-id="74034-129">Esse comando localiza scripts de fluxo de trabalho no repositório LocalRepo1.</span><span class="sxs-lookup"><span data-stu-id="74034-129">This command finds workflow scripts in the LocalRepo1 repository.</span></span>

### <span data-ttu-id="74034-130">Exemplo 11: localizar scripts usando curingas</span><span class="sxs-lookup"><span data-stu-id="74034-130">Example 11: Find scripts using wildcards</span></span>

```
PS C:\> Find-Script -Name "Required-Script*" -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script1                    Script     local1               Description for the Required-Script1 script
2.5        Required-Script2                    Script     local1               Description for the Required-Script2 script
2.5        Required-Script3                    Script     local1               Description for the Required-Script3 script
```

<span data-ttu-id="74034-131">Esse comando usa o caractere curinga (\*) para localizar scripts que começam com o script obrigatório.</span><span class="sxs-lookup"><span data-stu-id="74034-131">This command uses the wildcard character (\*) to find scripts that begin with Required-Script.</span></span>

## <span data-ttu-id="74034-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="74034-132">PARAMETERS</span></span>

### <span data-ttu-id="74034-133">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="74034-133">-AllowPrerelease</span></span>

<span data-ttu-id="74034-134">Inclui nos scripts de resultados marcados como um pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="74034-134">Includes in the results scripts marked as a prerelease.</span></span>

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

### <span data-ttu-id="74034-135">-Próprias versões</span><span class="sxs-lookup"><span data-stu-id="74034-135">-AllVersions</span></span>

<span data-ttu-id="74034-136">Indica que esta operação localiza todas as versões de script.</span><span class="sxs-lookup"><span data-stu-id="74034-136">Indicates that this operation finds all script versions.</span></span>

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

### <span data-ttu-id="74034-137">-Command</span><span class="sxs-lookup"><span data-stu-id="74034-137">-Command</span></span>

<span data-ttu-id="74034-138">Especifica uma matriz de comandos para localizar em scripts.</span><span class="sxs-lookup"><span data-stu-id="74034-138">Specifies an array of commands to find in scripts.</span></span>
<span data-ttu-id="74034-139">Um comando pode ser uma função ou um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="74034-139">A command can be a function or workflow.</span></span>

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

### <span data-ttu-id="74034-140">-Credential</span><span class="sxs-lookup"><span data-stu-id="74034-140">-Credential</span></span>

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

### <span data-ttu-id="74034-141">-Filter</span><span class="sxs-lookup"><span data-stu-id="74034-141">-Filter</span></span>

<span data-ttu-id="74034-142">Localiza scripts com base na sintaxe de pesquisa específica do provedor PackageManagement.</span><span class="sxs-lookup"><span data-stu-id="74034-142">Finds scripts based on the PackageManagement provider-specific search syntax.</span></span>

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

### <span data-ttu-id="74034-143">-IncludeDependencies</span><span class="sxs-lookup"><span data-stu-id="74034-143">-IncludeDependencies</span></span>

<span data-ttu-id="74034-144">Indica que esta operação obtém todos os scripts que dependem do script especificado no parâmetro *Name* .</span><span class="sxs-lookup"><span data-stu-id="74034-144">Indicates that this operation gets all scripts that are dependent upon the script specified in the *Name* parameter.</span></span>

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

### <span data-ttu-id="74034-145">-Inclui</span><span class="sxs-lookup"><span data-stu-id="74034-145">-Includes</span></span>

<span data-ttu-id="74034-146">Especifica o tipo de script a ser obtido.</span><span class="sxs-lookup"><span data-stu-id="74034-146">Specifies type of script to get.</span></span>
<span data-ttu-id="74034-147">Os valores aceitáveis para esse parâmetro são: função, fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="74034-147">The acceptable values for this parameter are: Function, Workflow.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Function, Workflow

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="74034-148">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="74034-148">-MaximumVersion</span></span>

<span data-ttu-id="74034-149">Especifica a versão máxima ou mais recente do script a ser localizado.</span><span class="sxs-lookup"><span data-stu-id="74034-149">Specifies the maximum, or newest, version of the script to find.</span></span>
<span data-ttu-id="74034-150">Os parâmetros *MaximumVersion* e *RequiredVersion* são mutuamente exclusivos; Você não pode usar ambos os parâmetros no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="74034-150">The *MaximumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="74034-151">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="74034-151">-MinimumVersion</span></span>

<span data-ttu-id="74034-152">Especifica a versão mínima do script a ser localizado.</span><span class="sxs-lookup"><span data-stu-id="74034-152">Specifies the minimum version of the script to find.</span></span>
<span data-ttu-id="74034-153">Os parâmetros *MinimumVersion* e *RequiredVersion* são mutuamente exclusivos; Você não pode usar ambos os parâmetros no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="74034-153">The *MinimumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="74034-154">-Name</span><span class="sxs-lookup"><span data-stu-id="74034-154">-Name</span></span>

<span data-ttu-id="74034-155">Especifica uma matriz de nomes de scripts a serem localizados.</span><span class="sxs-lookup"><span data-stu-id="74034-155">Specifies an array of names of scripts to find.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="74034-156">-Proxy</span><span class="sxs-lookup"><span data-stu-id="74034-156">-Proxy</span></span>

<span data-ttu-id="74034-157">Especifica um servidor proxy para a solicitação, em vez de conectar-se diretamente ao recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="74034-157">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="74034-158">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="74034-158">-ProxyCredential</span></span>

<span data-ttu-id="74034-159">Especifica uma conta de usuário com permissão para conectar-se aos computadores especificados pelo parâmetro **Proxy** .</span><span class="sxs-lookup"><span data-stu-id="74034-159">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="74034-160">-Repositório</span><span class="sxs-lookup"><span data-stu-id="74034-160">-Repository</span></span>

<span data-ttu-id="74034-161">Especifica o nome amigável de um repositório que foi registrado executando Register-PSRepository.</span><span class="sxs-lookup"><span data-stu-id="74034-161">Specifies the friendly name of a repository that has been registered by running Register-PSRepository.</span></span>

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

### <span data-ttu-id="74034-162">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="74034-162">-RequiredVersion</span></span>

<span data-ttu-id="74034-163">Especifica o número de versão exato do script a ser localizado.</span><span class="sxs-lookup"><span data-stu-id="74034-163">Specifies the exact version number of the script to find.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="74034-164">-Tag</span><span class="sxs-lookup"><span data-stu-id="74034-164">-Tag</span></span>

<span data-ttu-id="74034-165">Especifica uma matriz de marcas.</span><span class="sxs-lookup"><span data-stu-id="74034-165">Specifies an array of tags.</span></span>

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

### <span data-ttu-id="74034-166">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="74034-166">CommonParameters</span></span>

<span data-ttu-id="74034-167">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="74034-167">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="74034-168">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="74034-168">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="74034-169">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="74034-169">INPUTS</span></span>

## <span data-ttu-id="74034-170">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="74034-170">OUTPUTS</span></span>

### <span data-ttu-id="74034-171">PSRepositoryItemInfo</span><span class="sxs-lookup"><span data-stu-id="74034-171">PSRepositoryItemInfo</span></span>

## <span data-ttu-id="74034-172">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="74034-172">NOTES</span></span>

## <span data-ttu-id="74034-173">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="74034-173">RELATED LINKS</span></span>

[<span data-ttu-id="74034-174">Install-Script</span><span class="sxs-lookup"><span data-stu-id="74034-174">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="74034-175">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="74034-175">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="74034-176">Save-Script</span><span class="sxs-lookup"><span data-stu-id="74034-176">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="74034-177">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="74034-177">Uninstall-Script</span></span>](Uninstall-Script.md)

[<span data-ttu-id="74034-178">Update-Script</span><span class="sxs-lookup"><span data-stu-id="74034-178">Update-Script</span></span>](Update-Script.md)
