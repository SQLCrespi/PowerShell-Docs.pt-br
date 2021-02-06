---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/02/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/save-script?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Script
ms.openlocfilehash: 2f672cbb814b0641411bb11ffb17bd1ecef96dda
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "99595750"
---
# <span data-ttu-id="71271-102">Save-Script</span><span class="sxs-lookup"><span data-stu-id="71271-102">Save-Script</span></span>

## <span data-ttu-id="71271-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="71271-103">SYNOPSIS</span></span>
<span data-ttu-id="71271-104">Salva um script.</span><span class="sxs-lookup"><span data-stu-id="71271-104">Saves a script.</span></span>

## <span data-ttu-id="71271-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="71271-105">SYNTAX</span></span>

### <span data-ttu-id="71271-106">NameAndPathParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="71271-106">NameAndPathParameterSet (Default)</span></span>

```
Save-Script [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="71271-107">NameAndLiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="71271-107">NameAndLiteralPathParameterSet</span></span>

```
Save-Script [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="71271-108">InputObjectAndLiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="71271-108">InputObjectAndLiteralPathParameterSet</span></span>

```
Save-Script [-InputObject] <PSObject[]> -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="71271-109">InputObjectAndPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="71271-109">InputObjectAndPathParameterSet</span></span>

```
Save-Script [-InputObject] <PSObject[]> [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="71271-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="71271-110">DESCRIPTION</span></span>

<span data-ttu-id="71271-111">O `Save-Script` cmdlet salva o script especificado.</span><span class="sxs-lookup"><span data-stu-id="71271-111">The `Save-Script` cmdlet saves the specified script.</span></span>

## <span data-ttu-id="71271-112">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="71271-112">EXAMPLES</span></span>

### <span data-ttu-id="71271-113">Exemplo 1: salvar um script e validar os metadados do script</span><span class="sxs-lookup"><span data-stu-id="71271-113">Example 1: Save a script and validate the script's metadata</span></span>

<span data-ttu-id="71271-114">Neste exemplo, um script de um repositório é salvo no computador local e os metadados do script são validados.</span><span class="sxs-lookup"><span data-stu-id="71271-114">In this example, a script from a repository is saved to the local computer and the script's metadata is validated.</span></span>

```powershell
Save-Script -Name Install-VSCode -Repository PSGallery -Path C:\Test\Scripts
Test-ScriptFileInfo -Path C:\Test\Scripts\Install-VSCode.ps1
```

```Output
Version   Name              Author      Description
-------   ----              ------      -----------
1.3       Install-VSCode    Microsoft   This script can be used to easily install Visual Studio Code
```

<span data-ttu-id="71271-115">`Save-Script` usa o parâmetro **Name** para especificar o nome do script.</span><span class="sxs-lookup"><span data-stu-id="71271-115">`Save-Script` uses the **Name** parameter to specify the script's name.</span></span> <span data-ttu-id="71271-116">O parâmetro **Repository** especifica onde encontrar o script.</span><span class="sxs-lookup"><span data-stu-id="71271-116">The **Repository** parameter specifies where to find the script.</span></span> <span data-ttu-id="71271-117">O script é salvo no local especificado pelo parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="71271-117">The script is saved in the location specified by the **Path** parameter.</span></span> <span data-ttu-id="71271-118">`Test-ScriptFileInfo` Especifica o **caminho** e valida os metadados do script.</span><span class="sxs-lookup"><span data-stu-id="71271-118">`Test-ScriptFileInfo` specifies the **Path** and validates the script's metadata.</span></span>

## <span data-ttu-id="71271-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="71271-119">PARAMETERS</span></span>

### <span data-ttu-id="71271-120">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="71271-120">-AcceptLicense</span></span>

<span data-ttu-id="71271-121">Aceite automaticamente o contrato de licença se o script exigir.</span><span class="sxs-lookup"><span data-stu-id="71271-121">Automatically accept the license agreement if the script requires it.</span></span>

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

### <span data-ttu-id="71271-122">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="71271-122">-AllowPrerelease</span></span>

<span data-ttu-id="71271-123">Permite salvar um script marcado como um pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="71271-123">Allows you to save a script marked as a prerelease.</span></span>

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

### <span data-ttu-id="71271-124">-Confirm</span><span class="sxs-lookup"><span data-stu-id="71271-124">-Confirm</span></span>

<span data-ttu-id="71271-125">Solicita a confirmação antes de executar `Save-Script` .</span><span class="sxs-lookup"><span data-stu-id="71271-125">Prompts you for confirmation before running `Save-Script`.</span></span>

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

### <span data-ttu-id="71271-126">-Credential</span><span class="sxs-lookup"><span data-stu-id="71271-126">-Credential</span></span>

<span data-ttu-id="71271-127">Especifica uma conta de usuário que tem permissão para salvar um script.</span><span class="sxs-lookup"><span data-stu-id="71271-127">Specifies a user account that has permission to save a script.</span></span>

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

### <span data-ttu-id="71271-128">-Force</span><span class="sxs-lookup"><span data-stu-id="71271-128">-Force</span></span>

<span data-ttu-id="71271-129">Forças `Save-Script` a serem executadas sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="71271-129">Forces `Save-Script` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="71271-130">-InputObject</span><span class="sxs-lookup"><span data-stu-id="71271-130">-InputObject</span></span>

<span data-ttu-id="71271-131">Aceita um objeto **PSRepositoryItemInfo** .</span><span class="sxs-lookup"><span data-stu-id="71271-131">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="71271-132">Por exemplo, saída `Find-Script` para uma variável e use essa variável como o argumento **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="71271-132">For example, output `Find-Script` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="71271-133">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="71271-133">-LiteralPath</span></span>

<span data-ttu-id="71271-134">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="71271-134">Specifies a path to one or more locations.</span></span> <span data-ttu-id="71271-135">O valor do parâmetro **LiteralPath** é usado exatamente como inserido.</span><span class="sxs-lookup"><span data-stu-id="71271-135">The value of the **LiteralPath** parameter is used exactly as entered.</span></span> <span data-ttu-id="71271-136">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="71271-136">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="71271-137">Se o caminho incluir caracteres de escape, coloque o caminho entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="71271-137">If the path includes escape characters, enclose the path within single quotation marks.</span></span> <span data-ttu-id="71271-138">O PowerShell não interpreta nenhum caractere entre aspas simples como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="71271-138">PowerShell doesn't interpret any characters enclosed in single quotation marks as escape sequences.</span></span>

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

### <span data-ttu-id="71271-139">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="71271-139">-MaximumVersion</span></span>

<span data-ttu-id="71271-140">Especifica a versão máxima ou mais recente do script a ser salva.</span><span class="sxs-lookup"><span data-stu-id="71271-140">Specifies the maximum, or newest version of the script to save.</span></span> <span data-ttu-id="71271-141">Os parâmetros **MaximumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="71271-141">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="71271-142">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="71271-142">-MinimumVersion</span></span>

<span data-ttu-id="71271-143">Especifica a versão mínima de um script a ser salvo.</span><span class="sxs-lookup"><span data-stu-id="71271-143">Specifies the minimum version of a script to save.</span></span> <span data-ttu-id="71271-144">Os parâmetros **MinimumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="71271-144">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="71271-145">-Name</span><span class="sxs-lookup"><span data-stu-id="71271-145">-Name</span></span>

<span data-ttu-id="71271-146">Especifica uma matriz de nomes de script a ser salva.</span><span class="sxs-lookup"><span data-stu-id="71271-146">Specifies an array of script names to save.</span></span>

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

### <span data-ttu-id="71271-147">-Path</span><span class="sxs-lookup"><span data-stu-id="71271-147">-Path</span></span>

<span data-ttu-id="71271-148">Especifica o local no computador local para armazenar um módulo salvo.</span><span class="sxs-lookup"><span data-stu-id="71271-148">Specifies the location on the local computer to store a saved module.</span></span> <span data-ttu-id="71271-149">Aceita caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="71271-149">Accepts wildcard characters.</span></span>

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

### <span data-ttu-id="71271-150">-Proxy</span><span class="sxs-lookup"><span data-stu-id="71271-150">-Proxy</span></span>

<span data-ttu-id="71271-151">Especifica um servidor proxy para a solicitação, em vez de conectar-se diretamente a um recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="71271-151">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="71271-152">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="71271-152">-ProxyCredential</span></span>

<span data-ttu-id="71271-153">Especifica uma conta de usuário que tem permissão para usar o servidor proxy especificado pelo parâmetro de **proxy** .</span><span class="sxs-lookup"><span data-stu-id="71271-153">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="71271-154">-Repositório</span><span class="sxs-lookup"><span data-stu-id="71271-154">-Repository</span></span>

<span data-ttu-id="71271-155">Especifica o nome amigável de um repositório que foi registrado pela execução `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="71271-155">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span> <span data-ttu-id="71271-156">Use `Get-PSRepository` para exibir repositórios registrados.</span><span class="sxs-lookup"><span data-stu-id="71271-156">Use `Get-PSRepository` to display registered repositories.</span></span>

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

### <span data-ttu-id="71271-157">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="71271-157">-RequiredVersion</span></span>

<span data-ttu-id="71271-158">Especifica o número de versão exato do script a ser salvo.</span><span class="sxs-lookup"><span data-stu-id="71271-158">Specifies the exact version number of the script to save.</span></span>

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

### <span data-ttu-id="71271-159">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="71271-159">-WhatIf</span></span>

<span data-ttu-id="71271-160">Mostra o que aconteceria se `Save-Script` for executado.</span><span class="sxs-lookup"><span data-stu-id="71271-160">Shows what would happen if `Save-Script` runs.</span></span> <span data-ttu-id="71271-161">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="71271-161">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="71271-162">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="71271-162">CommonParameters</span></span>

<span data-ttu-id="71271-163">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="71271-163">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="71271-164">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="71271-164">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="71271-165">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="71271-165">INPUTS</span></span>

### <span data-ttu-id="71271-166">System.String[]</span><span class="sxs-lookup"><span data-stu-id="71271-166">System.String[]</span></span>

### <span data-ttu-id="71271-167">System. Management. Automation. PSObject []</span><span class="sxs-lookup"><span data-stu-id="71271-167">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="71271-168">System.String</span><span class="sxs-lookup"><span data-stu-id="71271-168">System.String</span></span>

### <span data-ttu-id="71271-169">System.Uri</span><span class="sxs-lookup"><span data-stu-id="71271-169">System.Uri</span></span>

### <span data-ttu-id="71271-170">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="71271-170">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="71271-171">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="71271-171">OUTPUTS</span></span>

### <span data-ttu-id="71271-172">System.Object</span><span class="sxs-lookup"><span data-stu-id="71271-172">System.Object</span></span>

## <span data-ttu-id="71271-173">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="71271-173">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71271-174">A partir de abril de 2020, a Galeria do PowerShell não dará mais suporte às versões 1.0 e 1.1 do protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="71271-174">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="71271-175">Se você não estiver usando o TLS 1.2 ou posterior, receberá um erro ao tentar acessar a Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71271-175">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="71271-176">Use o seguinte comando para garantir que esteja usando o TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="71271-176">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="71271-177">Para obter mais informações, confira o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71271-177">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="71271-178">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="71271-178">RELATED LINKS</span></span>

[<span data-ttu-id="71271-179">Find-Script</span><span class="sxs-lookup"><span data-stu-id="71271-179">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="71271-180">Install-Script</span><span class="sxs-lookup"><span data-stu-id="71271-180">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="71271-181">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="71271-181">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="71271-182">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="71271-182">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)

[<span data-ttu-id="71271-183">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="71271-183">Uninstall-Script</span></span>](Uninstall-Script.md)

[<span data-ttu-id="71271-184">Update-Script</span><span class="sxs-lookup"><span data-stu-id="71271-184">Update-Script</span></span>](Update-Script.md)
