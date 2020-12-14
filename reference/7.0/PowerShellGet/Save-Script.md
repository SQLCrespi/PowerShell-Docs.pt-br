---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/02/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/save-script?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Script
ms.openlocfilehash: 240bd1be4cd4a54fc667fade257e07d29434274d
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94891449"
---
# <span data-ttu-id="5e58a-103">Save-Script</span><span class="sxs-lookup"><span data-stu-id="5e58a-103">Save-Script</span></span>

## <span data-ttu-id="5e58a-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="5e58a-104">SYNOPSIS</span></span>
<span data-ttu-id="5e58a-105">Salva um script.</span><span class="sxs-lookup"><span data-stu-id="5e58a-105">Saves a script.</span></span>

## <span data-ttu-id="5e58a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5e58a-106">SYNTAX</span></span>

### <span data-ttu-id="5e58a-107">NameAndPathParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="5e58a-107">NameAndPathParameterSet (Default)</span></span>

```
Save-Script [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5e58a-108">NameAndLiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="5e58a-108">NameAndLiteralPathParameterSet</span></span>

```
Save-Script [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5e58a-109">InputObjectAndLiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="5e58a-109">InputObjectAndLiteralPathParameterSet</span></span>

```
Save-Script [-InputObject] <PSObject[]> -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5e58a-110">InputObjectAndPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="5e58a-110">InputObjectAndPathParameterSet</span></span>

```
Save-Script [-InputObject] <PSObject[]> [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="5e58a-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5e58a-111">DESCRIPTION</span></span>

<span data-ttu-id="5e58a-112">O `Save-Script` cmdlet salva o script especificado.</span><span class="sxs-lookup"><span data-stu-id="5e58a-112">The `Save-Script` cmdlet saves the specified script.</span></span>

## <span data-ttu-id="5e58a-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="5e58a-113">EXAMPLES</span></span>

### <span data-ttu-id="5e58a-114">Exemplo 1: salvar um script e validar os metadados do script</span><span class="sxs-lookup"><span data-stu-id="5e58a-114">Example 1: Save a script and validate the script's metadata</span></span>

<span data-ttu-id="5e58a-115">Neste exemplo, um script de um repositório é salvo no computador local e os metadados do script são validados.</span><span class="sxs-lookup"><span data-stu-id="5e58a-115">In this example, a script from a repository is saved to the local computer and the script's metadata is validated.</span></span>

```powershell
Save-Script -Name Install-VSCode -Repository PSGallery -Path C:\Test\Scripts
Test-ScriptFileInfo -Path C:\Test\Scripts\Install-VSCode.ps1
```

```Output
Version   Name              Author      Description
-------   ----              ------      -----------
1.3       Install-VSCode    Microsoft   This script can be used to easily install Visual Studio Code
```

<span data-ttu-id="5e58a-116">`Save-Script` usa o parâmetro **Name** para especificar o nome do script.</span><span class="sxs-lookup"><span data-stu-id="5e58a-116">`Save-Script` uses the **Name** parameter to specify the script's name.</span></span> <span data-ttu-id="5e58a-117">O parâmetro **Repository** especifica onde encontrar o script.</span><span class="sxs-lookup"><span data-stu-id="5e58a-117">The **Repository** parameter specifies where to find the script.</span></span> <span data-ttu-id="5e58a-118">O script é salvo no local especificado pelo parâmetro **path** .</span><span class="sxs-lookup"><span data-stu-id="5e58a-118">The script is saved in the location specified by the **Path** parameter.</span></span> <span data-ttu-id="5e58a-119">`Test-ScriptFileInfo` Especifica o **caminho** e valida os metadados do script.</span><span class="sxs-lookup"><span data-stu-id="5e58a-119">`Test-ScriptFileInfo` specifies the **Path** and validates the script's metadata.</span></span>

## <span data-ttu-id="5e58a-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5e58a-120">PARAMETERS</span></span>

### <span data-ttu-id="5e58a-121">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="5e58a-121">-AcceptLicense</span></span>

<span data-ttu-id="5e58a-122">Aceite automaticamente o contrato de licença se o script exigir.</span><span class="sxs-lookup"><span data-stu-id="5e58a-122">Automatically accept the license agreement if the script requires it.</span></span>

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

### <span data-ttu-id="5e58a-123">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="5e58a-123">-AllowPrerelease</span></span>

<span data-ttu-id="5e58a-124">Permite salvar um script marcado como um pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="5e58a-124">Allows you to save a script marked as a prerelease.</span></span>

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

### <span data-ttu-id="5e58a-125">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5e58a-125">-Confirm</span></span>

<span data-ttu-id="5e58a-126">Solicita a confirmação antes de executar `Save-Script` .</span><span class="sxs-lookup"><span data-stu-id="5e58a-126">Prompts you for confirmation before running `Save-Script`.</span></span>

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

### <span data-ttu-id="5e58a-127">-Credential</span><span class="sxs-lookup"><span data-stu-id="5e58a-127">-Credential</span></span>

<span data-ttu-id="5e58a-128">Especifica uma conta de usuário que tem permissão para salvar um script.</span><span class="sxs-lookup"><span data-stu-id="5e58a-128">Specifies a user account that has permission to save a script.</span></span>

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

### <span data-ttu-id="5e58a-129">-Force</span><span class="sxs-lookup"><span data-stu-id="5e58a-129">-Force</span></span>

<span data-ttu-id="5e58a-130">Forças `Save-Script` a serem executadas sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="5e58a-130">Forces `Save-Script` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="5e58a-131">-InputObject</span><span class="sxs-lookup"><span data-stu-id="5e58a-131">-InputObject</span></span>

<span data-ttu-id="5e58a-132">Aceita um objeto **PSRepositoryItemInfo** .</span><span class="sxs-lookup"><span data-stu-id="5e58a-132">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="5e58a-133">Por exemplo, saída `Find-Script` para uma variável e use essa variável como o argumento **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="5e58a-133">For example, output `Find-Script` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="5e58a-134">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="5e58a-134">-LiteralPath</span></span>

<span data-ttu-id="5e58a-135">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="5e58a-135">Specifies a path to one or more locations.</span></span> <span data-ttu-id="5e58a-136">O valor do parâmetro **LiteralPath** é usado exatamente como inserido.</span><span class="sxs-lookup"><span data-stu-id="5e58a-136">The value of the **LiteralPath** parameter is used exactly as entered.</span></span> <span data-ttu-id="5e58a-137">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="5e58a-137">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="5e58a-138">Se o caminho incluir caracteres de escape, coloque o caminho entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="5e58a-138">If the path includes escape characters, enclose the path within single quotation marks.</span></span> <span data-ttu-id="5e58a-139">O PowerShell não interpreta nenhum caractere entre aspas simples como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="5e58a-139">PowerShell doesn't interpret any characters enclosed in single quotation marks as escape sequences.</span></span>

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

### <span data-ttu-id="5e58a-140">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="5e58a-140">-MaximumVersion</span></span>

<span data-ttu-id="5e58a-141">Especifica a versão máxima ou mais recente do script a ser salva.</span><span class="sxs-lookup"><span data-stu-id="5e58a-141">Specifies the maximum, or newest version of the script to save.</span></span> <span data-ttu-id="5e58a-142">Os parâmetros **MaximumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="5e58a-142">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="5e58a-143">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="5e58a-143">-MinimumVersion</span></span>

<span data-ttu-id="5e58a-144">Especifica a versão mínima de um script a ser salvo.</span><span class="sxs-lookup"><span data-stu-id="5e58a-144">Specifies the minimum version of a script to save.</span></span> <span data-ttu-id="5e58a-145">Os parâmetros **MinimumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="5e58a-145">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="5e58a-146">-Name</span><span class="sxs-lookup"><span data-stu-id="5e58a-146">-Name</span></span>

<span data-ttu-id="5e58a-147">Especifica uma matriz de nomes de script a ser salva.</span><span class="sxs-lookup"><span data-stu-id="5e58a-147">Specifies an array of script names to save.</span></span>

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

### <span data-ttu-id="5e58a-148">-Path</span><span class="sxs-lookup"><span data-stu-id="5e58a-148">-Path</span></span>

<span data-ttu-id="5e58a-149">Especifica o local no computador local para armazenar um módulo salvo.</span><span class="sxs-lookup"><span data-stu-id="5e58a-149">Specifies the location on the local computer to store a saved module.</span></span> <span data-ttu-id="5e58a-150">Aceita caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="5e58a-150">Accepts wildcard characters.</span></span>

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

### <span data-ttu-id="5e58a-151">-Proxy</span><span class="sxs-lookup"><span data-stu-id="5e58a-151">-Proxy</span></span>

<span data-ttu-id="5e58a-152">Especifica um servidor proxy para a solicitação, em vez de conectar-se diretamente a um recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="5e58a-152">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="5e58a-153">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="5e58a-153">-ProxyCredential</span></span>

<span data-ttu-id="5e58a-154">Especifica uma conta de usuário que tem permissão para usar o servidor proxy especificado pelo parâmetro de **proxy** .</span><span class="sxs-lookup"><span data-stu-id="5e58a-154">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="5e58a-155">-Repositório</span><span class="sxs-lookup"><span data-stu-id="5e58a-155">-Repository</span></span>

<span data-ttu-id="5e58a-156">Especifica o nome amigável de um repositório que foi registrado pela execução `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="5e58a-156">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span> <span data-ttu-id="5e58a-157">Use `Get-PSRepository` para exibir repositórios registrados.</span><span class="sxs-lookup"><span data-stu-id="5e58a-157">Use `Get-PSRepository` to display registered repositories.</span></span>

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

### <span data-ttu-id="5e58a-158">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="5e58a-158">-RequiredVersion</span></span>

<span data-ttu-id="5e58a-159">Especifica o número de versão exato do script a ser salvo.</span><span class="sxs-lookup"><span data-stu-id="5e58a-159">Specifies the exact version number of the script to save.</span></span>

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

### <span data-ttu-id="5e58a-160">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5e58a-160">-WhatIf</span></span>

<span data-ttu-id="5e58a-161">Mostra o que aconteceria se `Save-Script` for executado.</span><span class="sxs-lookup"><span data-stu-id="5e58a-161">Shows what would happen if `Save-Script` runs.</span></span> <span data-ttu-id="5e58a-162">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="5e58a-162">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="5e58a-163">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5e58a-163">CommonParameters</span></span>

<span data-ttu-id="5e58a-164">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5e58a-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5e58a-165">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5e58a-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5e58a-166">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="5e58a-166">INPUTS</span></span>

### <span data-ttu-id="5e58a-167">System.String[]</span><span class="sxs-lookup"><span data-stu-id="5e58a-167">System.String[]</span></span>

### <span data-ttu-id="5e58a-168">System. Management. Automation. PSObject []</span><span class="sxs-lookup"><span data-stu-id="5e58a-168">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="5e58a-169">System.String</span><span class="sxs-lookup"><span data-stu-id="5e58a-169">System.String</span></span>

### <span data-ttu-id="5e58a-170">System.Uri</span><span class="sxs-lookup"><span data-stu-id="5e58a-170">System.Uri</span></span>

### <span data-ttu-id="5e58a-171">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="5e58a-171">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="5e58a-172">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="5e58a-172">OUTPUTS</span></span>

### <span data-ttu-id="5e58a-173">System.Object</span><span class="sxs-lookup"><span data-stu-id="5e58a-173">System.Object</span></span>

## <span data-ttu-id="5e58a-174">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="5e58a-174">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5e58a-175">A partir de abril de 2020, o Galeria do PowerShell não dá mais suporte às versões 1,0 e 1,1 da segurança da camada de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="5e58a-175">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="5e58a-176">Se você não estiver usando o TLS 1,2 ou superior, receberá um erro ao tentar acessar o Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e58a-176">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="5e58a-177">Use o comando a seguir para garantir que você esteja usando o TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="5e58a-177">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="5e58a-178">Para obter mais informações, consulte o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e58a-178">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="5e58a-179">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="5e58a-179">RELATED LINKS</span></span>

[<span data-ttu-id="5e58a-180">Find-Script</span><span class="sxs-lookup"><span data-stu-id="5e58a-180">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="5e58a-181">Install-Script</span><span class="sxs-lookup"><span data-stu-id="5e58a-181">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="5e58a-182">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="5e58a-182">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="5e58a-183">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="5e58a-183">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)

[<span data-ttu-id="5e58a-184">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="5e58a-184">Uninstall-Script</span></span>](Uninstall-Script.md)

[<span data-ttu-id="5e58a-185">Update-Script</span><span class="sxs-lookup"><span data-stu-id="5e58a-185">Update-Script</span></span>](Update-Script.md)
