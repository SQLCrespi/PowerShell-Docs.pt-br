---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/02/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/save-script?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Script
ms.openlocfilehash: 1aa133d699ad8dfa6d8261f446033e6099254cd1
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892739"
---
# <span data-ttu-id="2bdda-103">Save-Script</span><span class="sxs-lookup"><span data-stu-id="2bdda-103">Save-Script</span></span>

## <span data-ttu-id="2bdda-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="2bdda-104">SYNOPSIS</span></span>
<span data-ttu-id="2bdda-105">Salva um script.</span><span class="sxs-lookup"><span data-stu-id="2bdda-105">Saves a script.</span></span>

## <span data-ttu-id="2bdda-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2bdda-106">SYNTAX</span></span>

### <span data-ttu-id="2bdda-107">NameAndPathParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="2bdda-107">NameAndPathParameterSet (Default)</span></span>

```
Save-Script [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2bdda-108">NameAndLiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="2bdda-108">NameAndLiteralPathParameterSet</span></span>

```
Save-Script [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2bdda-109">InputObjectAndLiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="2bdda-109">InputObjectAndLiteralPathParameterSet</span></span>

```
Save-Script [-InputObject] <PSObject[]> -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2bdda-110">InputObjectAndPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="2bdda-110">InputObjectAndPathParameterSet</span></span>

```
Save-Script [-InputObject] <PSObject[]> [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="2bdda-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2bdda-111">DESCRIPTION</span></span>

<span data-ttu-id="2bdda-112">O `Save-Script` cmdlet salva o script especificado.</span><span class="sxs-lookup"><span data-stu-id="2bdda-112">The `Save-Script` cmdlet saves the specified script.</span></span>

## <span data-ttu-id="2bdda-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="2bdda-113">EXAMPLES</span></span>

### <span data-ttu-id="2bdda-114">Exemplo 1: salvar um script e validar os metadados do script</span><span class="sxs-lookup"><span data-stu-id="2bdda-114">Example 1: Save a script and validate the script's metadata</span></span>

<span data-ttu-id="2bdda-115">Neste exemplo, um script de um repositório é salvo no computador local e os metadados do script são validados.</span><span class="sxs-lookup"><span data-stu-id="2bdda-115">In this example, a script from a repository is saved to the local computer and the script's metadata is validated.</span></span>

```powershell
Save-Script -Name Install-VSCode -Repository PSGallery -Path C:\Test\Scripts
Test-ScriptFileInfo -Path C:\Test\Scripts\Install-VSCode.ps1
```

```Output
Version   Name              Author      Description
-------   ----              ------      -----------
1.3       Install-VSCode    Microsoft   This script can be used to easily install Visual Studio Code
```

<span data-ttu-id="2bdda-116">`Save-Script` usa o parâmetro **Name** para especificar o nome do script.</span><span class="sxs-lookup"><span data-stu-id="2bdda-116">`Save-Script` uses the **Name** parameter to specify the script's name.</span></span> <span data-ttu-id="2bdda-117">O parâmetro **Repository** especifica onde encontrar o script.</span><span class="sxs-lookup"><span data-stu-id="2bdda-117">The **Repository** parameter specifies where to find the script.</span></span> <span data-ttu-id="2bdda-118">O script é salvo no local especificado pelo parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="2bdda-118">The script is saved in the location specified by the **Path** parameter.</span></span> <span data-ttu-id="2bdda-119">`Test-ScriptFileInfo` Especifica o **caminho** e valida os metadados do script.</span><span class="sxs-lookup"><span data-stu-id="2bdda-119">`Test-ScriptFileInfo` specifies the **Path** and validates the script's metadata.</span></span>

## <span data-ttu-id="2bdda-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2bdda-120">PARAMETERS</span></span>

### <span data-ttu-id="2bdda-121">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="2bdda-121">-AcceptLicense</span></span>

<span data-ttu-id="2bdda-122">Aceite automaticamente o contrato de licença se o script exigir.</span><span class="sxs-lookup"><span data-stu-id="2bdda-122">Automatically accept the license agreement if the script requires it.</span></span>

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

### <span data-ttu-id="2bdda-123">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="2bdda-123">-AllowPrerelease</span></span>

<span data-ttu-id="2bdda-124">Permite salvar um script marcado como um pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="2bdda-124">Allows you to save a script marked as a prerelease.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2bdda-125">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2bdda-125">-Confirm</span></span>

<span data-ttu-id="2bdda-126">Solicita a confirmação antes de executar `Save-Script` .</span><span class="sxs-lookup"><span data-stu-id="2bdda-126">Prompts you for confirmation before running `Save-Script`.</span></span>

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

### <span data-ttu-id="2bdda-127">-Credential</span><span class="sxs-lookup"><span data-stu-id="2bdda-127">-Credential</span></span>

<span data-ttu-id="2bdda-128">Especifica uma conta de usuário que tem permissão para salvar um script.</span><span class="sxs-lookup"><span data-stu-id="2bdda-128">Specifies a user account that has permission to save a script.</span></span>

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

### <span data-ttu-id="2bdda-129">-Force</span><span class="sxs-lookup"><span data-stu-id="2bdda-129">-Force</span></span>

<span data-ttu-id="2bdda-130">Forças `Save-Script` a serem executadas sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="2bdda-130">Forces `Save-Script` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="2bdda-131">-InputObject</span><span class="sxs-lookup"><span data-stu-id="2bdda-131">-InputObject</span></span>

<span data-ttu-id="2bdda-132">Aceita um objeto **PSRepositoryItemInfo** .</span><span class="sxs-lookup"><span data-stu-id="2bdda-132">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="2bdda-133">Por exemplo, saída `Find-Script` para uma variável e use essa variável como o argumento **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="2bdda-133">For example, output `Find-Script` to a variable and use that variable as the **InputObject** argument.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: InputObjectAndLiteralPathParameterSet, InputObjectAndPathParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="2bdda-134">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="2bdda-134">-LiteralPath</span></span>

<span data-ttu-id="2bdda-135">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="2bdda-135">Specifies a path to one or more locations.</span></span> <span data-ttu-id="2bdda-136">O valor do parâmetro **LiteralPath** é usado exatamente como inserido.</span><span class="sxs-lookup"><span data-stu-id="2bdda-136">The value of the **LiteralPath** parameter is used exactly as entered.</span></span> <span data-ttu-id="2bdda-137">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="2bdda-137">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="2bdda-138">Se o caminho incluir caracteres de escape, coloque o caminho entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="2bdda-138">If the path includes escape characters, enclose the path within single quotation marks.</span></span> <span data-ttu-id="2bdda-139">O PowerShell não interpreta nenhum caractere entre aspas simples como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="2bdda-139">PowerShell doesn't interpret any characters enclosed in single quotation marks as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: NameAndLiteralPathParameterSet, InputObjectAndLiteralPathParameterSet
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2bdda-140">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="2bdda-140">-MaximumVersion</span></span>

<span data-ttu-id="2bdda-141">Especifica a versão máxima ou mais recente do script a ser salva.</span><span class="sxs-lookup"><span data-stu-id="2bdda-141">Specifies the maximum, or newest version of the script to save.</span></span> <span data-ttu-id="2bdda-142">Os parâmetros **MaximumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="2bdda-142">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2bdda-143">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="2bdda-143">-MinimumVersion</span></span>

<span data-ttu-id="2bdda-144">Especifica a versão mínima de um script a ser salvo.</span><span class="sxs-lookup"><span data-stu-id="2bdda-144">Specifies the minimum version of a script to save.</span></span> <span data-ttu-id="2bdda-145">Os parâmetros **MinimumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="2bdda-145">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2bdda-146">-Name</span><span class="sxs-lookup"><span data-stu-id="2bdda-146">-Name</span></span>

<span data-ttu-id="2bdda-147">Especifica uma matriz de nomes de script a ser salva.</span><span class="sxs-lookup"><span data-stu-id="2bdda-147">Specifies an array of script names to save.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2bdda-148">-Path</span><span class="sxs-lookup"><span data-stu-id="2bdda-148">-Path</span></span>

<span data-ttu-id="2bdda-149">Especifica o local no computador local para armazenar um módulo salvo.</span><span class="sxs-lookup"><span data-stu-id="2bdda-149">Specifies the location on the local computer to store a saved module.</span></span> <span data-ttu-id="2bdda-150">Aceita caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="2bdda-150">Accepts wildcard characters.</span></span>

```yaml
Type: System.String
Parameter Sets: NameAndPathParameterSet, InputObjectAndPathParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="2bdda-151">-Proxy</span><span class="sxs-lookup"><span data-stu-id="2bdda-151">-Proxy</span></span>

<span data-ttu-id="2bdda-152">Especifica um servidor proxy para a solicitação, em vez de conectar-se diretamente a um recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="2bdda-152">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="2bdda-153">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="2bdda-153">-ProxyCredential</span></span>

<span data-ttu-id="2bdda-154">Especifica uma conta de usuário que tem permissão para usar o servidor proxy especificado pelo parâmetro de **proxy** .</span><span class="sxs-lookup"><span data-stu-id="2bdda-154">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="2bdda-155">-Repositório</span><span class="sxs-lookup"><span data-stu-id="2bdda-155">-Repository</span></span>

<span data-ttu-id="2bdda-156">Especifica o nome amigável de um repositório que foi registrado pela execução `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="2bdda-156">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span> <span data-ttu-id="2bdda-157">Use `Get-PSRepository` para exibir repositórios registrados.</span><span class="sxs-lookup"><span data-stu-id="2bdda-157">Use `Get-PSRepository` to display registered repositories.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2bdda-158">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="2bdda-158">-RequiredVersion</span></span>

<span data-ttu-id="2bdda-159">Especifica o número de versão exato do script a ser salvo.</span><span class="sxs-lookup"><span data-stu-id="2bdda-159">Specifies the exact version number of the script to save.</span></span>

```yaml
Type: System.String
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2bdda-160">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2bdda-160">-WhatIf</span></span>

<span data-ttu-id="2bdda-161">Mostra o que aconteceria se `Save-Script` for executado.</span><span class="sxs-lookup"><span data-stu-id="2bdda-161">Shows what would happen if `Save-Script` runs.</span></span> <span data-ttu-id="2bdda-162">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="2bdda-162">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="2bdda-163">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2bdda-163">CommonParameters</span></span>

<span data-ttu-id="2bdda-164">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2bdda-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2bdda-165">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2bdda-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2bdda-166">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="2bdda-166">INPUTS</span></span>

## <span data-ttu-id="2bdda-167">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="2bdda-167">OUTPUTS</span></span>

## <span data-ttu-id="2bdda-168">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="2bdda-168">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2bdda-169">A partir de abril de 2020, o Galeria do PowerShell não dá mais suporte às versões 1,0 e 1,1 da segurança da camada de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="2bdda-169">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="2bdda-170">Se você não estiver usando o TLS 1,2 ou superior, receberá um erro ao tentar acessar o Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2bdda-170">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="2bdda-171">Use o comando a seguir para garantir que você esteja usando o TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="2bdda-171">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="2bdda-172">Para obter mais informações, consulte o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2bdda-172">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="2bdda-173">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="2bdda-173">RELATED LINKS</span></span>

[<span data-ttu-id="2bdda-174">Find-Script</span><span class="sxs-lookup"><span data-stu-id="2bdda-174">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="2bdda-175">Install-Script</span><span class="sxs-lookup"><span data-stu-id="2bdda-175">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="2bdda-176">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="2bdda-176">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="2bdda-177">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="2bdda-177">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)

[<span data-ttu-id="2bdda-178">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="2bdda-178">Uninstall-Script</span></span>](Uninstall-Script.md)

[<span data-ttu-id="2bdda-179">Update-Script</span><span class="sxs-lookup"><span data-stu-id="2bdda-179">Update-Script</span></span>](Update-Script.md)
