---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 11/11/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/save-module?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Module
ms.openlocfilehash: 88ce556a366e67a911bf32eb5c13161a543f103f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194226"
---
# <span data-ttu-id="cf533-103">Save-Module</span><span class="sxs-lookup"><span data-stu-id="cf533-103">Save-Module</span></span>

## <span data-ttu-id="cf533-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="cf533-104">SYNOPSIS</span></span>
<span data-ttu-id="cf533-105">Salva um módulo e suas dependências no computador local, mas não instala o módulo.</span><span class="sxs-lookup"><span data-stu-id="cf533-105">Saves a module and its dependencies on the local computer but doesn't install the module.</span></span>

## <span data-ttu-id="cf533-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cf533-106">SYNTAX</span></span>

### <span data-ttu-id="cf533-107">NameAndPathParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="cf533-107">NameAndPathParameterSet (Default)</span></span>

```
Save-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cf533-108">NameAndLiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="cf533-108">NameAndLiteralPathParameterSet</span></span>

```
Save-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cf533-109">InputObjectAndLiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="cf533-109">InputObjectAndLiteralPathParameterSet</span></span>

```
Save-Module [-InputObject] <PSObject[]> -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cf533-110">InputObjectAndPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="cf533-110">InputObjectAndPathParameterSet</span></span>

```
Save-Module [-InputObject] <PSObject[]> [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="cf533-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cf533-111">DESCRIPTION</span></span>

<span data-ttu-id="cf533-112">O `Save-Module` cmdlet baixa um módulo e quaisquer dependências de um repositório registrado.</span><span class="sxs-lookup"><span data-stu-id="cf533-112">The `Save-Module` cmdlet downloads a module and any dependencies from a registered repository.</span></span>
<span data-ttu-id="cf533-113">`Save-Module` baixa e salva a versão mais atual de um módulo.</span><span class="sxs-lookup"><span data-stu-id="cf533-113">`Save-Module` downloads and saves the most current version of a module.</span></span> <span data-ttu-id="cf533-114">Os arquivos são salvos em um caminho especificado no computador local.</span><span class="sxs-lookup"><span data-stu-id="cf533-114">The files are saved to a specified path on the local computer.</span></span> <span data-ttu-id="cf533-115">O módulo não está instalado, mas o conteúdo está disponível para inspeção por um administrador.</span><span class="sxs-lookup"><span data-stu-id="cf533-115">The module isn't installed, but the contents are available for inspection by an administrator.</span></span> <span data-ttu-id="cf533-116">O módulo salvo pode então ser copiado para o `$env:PSModulePath` local apropriado do computador offline.</span><span class="sxs-lookup"><span data-stu-id="cf533-116">The saved module can then be copied into the appropriate `$env:PSModulePath` location of the offline machine.</span></span>

<span data-ttu-id="cf533-117">`Get-PSRepository` exibe os repositórios registrados do computador local.</span><span class="sxs-lookup"><span data-stu-id="cf533-117">`Get-PSRepository` displays the local computer's registered repositories.</span></span> <span data-ttu-id="cf533-118">Você pode usar o `Find-Module` cmdlet para pesquisar repositórios registrados.</span><span class="sxs-lookup"><span data-stu-id="cf533-118">You can use the `Find-Module` cmdlet to search registered repositories.</span></span>

## <span data-ttu-id="cf533-119">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="cf533-119">EXAMPLES</span></span>

### <span data-ttu-id="cf533-120">Exemplo 1: salvar um módulo</span><span class="sxs-lookup"><span data-stu-id="cf533-120">Example 1: Save a module</span></span>

<span data-ttu-id="cf533-121">Neste exemplo, um módulo e suas dependências são salvos no computador local.</span><span class="sxs-lookup"><span data-stu-id="cf533-121">In this example, a module and its dependencies are saved to the local computer.</span></span>

```powershell
Save-Module -Name PowerShellGet -Path C:\Test\Modules -Repository PSGallery
Get-ChildItem -Path C:\Test\Modules
```

```Output
    Directory: C:\Test\Modules

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         7/1/2019     13:31                PackageManagement
d-----         7/1/2019     13:31                PowerShellGet
```

<span data-ttu-id="cf533-122">`Save-Module` usa o parâmetro **Name** para especificar o módulo, **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="cf533-122">`Save-Module` uses the **Name** parameter to specify the module, **PowerShellGet** .</span></span> <span data-ttu-id="cf533-123">O parâmetro **path** especifica onde armazenar o módulo baixado.</span><span class="sxs-lookup"><span data-stu-id="cf533-123">The **Path** parameter specifies where to store the downloaded module.</span></span> <span data-ttu-id="cf533-124">O parâmetro **Repository** especifica um repositório registrado, **PSGallery** .</span><span class="sxs-lookup"><span data-stu-id="cf533-124">The **Repository** parameter specifies a registered repository, **PSGallery** .</span></span> <span data-ttu-id="cf533-125">Depois que o download for concluído, o `Get-ChildItem` exibirá o conteúdo do **caminho** onde os arquivos são armazenados.</span><span class="sxs-lookup"><span data-stu-id="cf533-125">After the download is finished, `Get-ChildItem` displays the contents of **Path** where the files are stored.</span></span>

### <span data-ttu-id="cf533-126">Exemplo 2: salvar uma versão específica de um módulo</span><span class="sxs-lookup"><span data-stu-id="cf533-126">Example 2: Save a specific version of a module</span></span>

<span data-ttu-id="cf533-127">Este exemplo mostra como usar um parâmetro como **MaximumVersion** , ou **RequiredVersion** para especificar uma versão de módulo.</span><span class="sxs-lookup"><span data-stu-id="cf533-127">This example shows how to use a parameter such as **MaximumVersion** , or **RequiredVersion** to specify a module version.</span></span>

```powershell
Save-Module -Name PowerShellGet -Path C:\Test\Modules -Repository PSGallery -MaximumVersion 2.1.0
Get-ChildItem -Path C:\Test\Modules\PowerShellGet\
```

```Output
    Directory: C:\Test\Modules\PowerShellGet

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         7/1/2019     13:40                2.1.0
```

<span data-ttu-id="cf533-128">`Save-Module` usa o parâmetro **Name** para especificar o módulo, **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="cf533-128">`Save-Module` uses the **Name** parameter to specify the module, **PowerShellGet** .</span></span> <span data-ttu-id="cf533-129">O parâmetro **path** especifica onde armazenar o módulo baixado.</span><span class="sxs-lookup"><span data-stu-id="cf533-129">The **Path** parameter specifies where to store the downloaded module.</span></span> <span data-ttu-id="cf533-130">O parâmetro **Repository** especifica um repositório registrado, **PSGallery** .</span><span class="sxs-lookup"><span data-stu-id="cf533-130">The **Repository** parameter specifies a registered repository, **PSGallery** .</span></span> <span data-ttu-id="cf533-131">**MaximumVersion** especifica que a versão **2.1.0** é baixada e salva.</span><span class="sxs-lookup"><span data-stu-id="cf533-131">**MaximumVersion** specifies that version **2.1.0** is downloaded and saved.</span></span> <span data-ttu-id="cf533-132">Depois que o download for concluído, o `Get-ChildItem` exibirá o conteúdo do **caminho** onde os arquivos são armazenados.</span><span class="sxs-lookup"><span data-stu-id="cf533-132">After the download is finished, `Get-ChildItem` displays the contents of **Path** where the files are stored.</span></span>

### <span data-ttu-id="cf533-133">Exemplo 3: localizar e salvar uma versão específica de um módulo</span><span class="sxs-lookup"><span data-stu-id="cf533-133">Example 3: Find and save a specific version of a module</span></span>

<span data-ttu-id="cf533-134">Neste exemplo, uma versão de módulo necessária é encontrada no repositório e salva no computador local.</span><span class="sxs-lookup"><span data-stu-id="cf533-134">In this example, a required module version is found in the repository and saved to the local computer.</span></span>

```powershell
Find-Module -Name PowerShellGet -Repository PSGallery -RequiredVersion 1.6.5 |
  Save-Module -Path C:\Test\Modules
Get-ChildItem -Path C:\Test\Modules\PowerShellGet
```

```Output
    Directory: C:\Test\Modules\PowerShellGet

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         7/1/2019     14:04                1.6.5
```

<span data-ttu-id="cf533-135">`Find-Module` usa o parâmetro **Name** para especificar o módulo, **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="cf533-135">`Find-Module` uses the **Name** parameter to specify the module, **PowerShellGet** .</span></span> <span data-ttu-id="cf533-136">O parâmetro **Repository** especifica um repositório registrado, **PSGallery** .</span><span class="sxs-lookup"><span data-stu-id="cf533-136">The **Repository** parameter specifies a registered repository, **PSGallery** .</span></span> <span data-ttu-id="cf533-137">**RequiredVersion** especifica a versão **1.6.5** .</span><span class="sxs-lookup"><span data-stu-id="cf533-137">**RequiredVersion** specifies version **1.6.5** .</span></span>

<span data-ttu-id="cf533-138">O objeto é enviado ao pipeline para `Save-Module` .</span><span class="sxs-lookup"><span data-stu-id="cf533-138">The object is sent down the pipeline to `Save-Module`.</span></span> <span data-ttu-id="cf533-139">O parâmetro **path** especifica onde armazenar o módulo baixado.</span><span class="sxs-lookup"><span data-stu-id="cf533-139">The **Path** parameter specifies where to store the downloaded module.</span></span> <span data-ttu-id="cf533-140">Depois que o download for concluído, o `Get-ChildItem` exibirá o conteúdo do **caminho** onde os arquivos são armazenados.</span><span class="sxs-lookup"><span data-stu-id="cf533-140">After the download is finished, `Get-ChildItem` displays the contents of **Path** where the files are stored.</span></span>

## <span data-ttu-id="cf533-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cf533-141">PARAMETERS</span></span>

### <span data-ttu-id="cf533-142">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="cf533-142">-AcceptLicense</span></span>

<span data-ttu-id="cf533-143">Aceite automaticamente o contrato de licença se o pacote exigir.</span><span class="sxs-lookup"><span data-stu-id="cf533-143">Automatically accept the license agreement if the package requires it.</span></span>

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

### <span data-ttu-id="cf533-144">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="cf533-144">-AllowPrerelease</span></span>

<span data-ttu-id="cf533-145">Permite salvar um módulo marcado como um pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="cf533-145">Allows you to save a module marked as a prerelease.</span></span>

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

### <span data-ttu-id="cf533-146">-Confirm</span><span class="sxs-lookup"><span data-stu-id="cf533-146">-Confirm</span></span>

<span data-ttu-id="cf533-147">Solicita a confirmação antes de executar o `Save-Module` .</span><span class="sxs-lookup"><span data-stu-id="cf533-147">Prompts you for confirmation before running the `Save-Module`.</span></span>

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

### <span data-ttu-id="cf533-148">-Credential</span><span class="sxs-lookup"><span data-stu-id="cf533-148">-Credential</span></span>

<span data-ttu-id="cf533-149">Especifica uma conta de usuário que tem direitos para salvar um módulo.</span><span class="sxs-lookup"><span data-stu-id="cf533-149">Specifies a user account that has rights to save a module.</span></span>

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

### <span data-ttu-id="cf533-150">-Force</span><span class="sxs-lookup"><span data-stu-id="cf533-150">-Force</span></span>

<span data-ttu-id="cf533-151">Forças `Save-Module` a serem executadas sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="cf533-151">Forces `Save-Module` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="cf533-152">-InputObject</span><span class="sxs-lookup"><span data-stu-id="cf533-152">-InputObject</span></span>

<span data-ttu-id="cf533-153">Aceita um objeto **PSRepositoryItemInfo** .</span><span class="sxs-lookup"><span data-stu-id="cf533-153">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="cf533-154">Por exemplo, saída `Find-Module` para uma variável e use essa variável como o argumento **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="cf533-154">For example, output `Find-Module` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="cf533-155">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="cf533-155">-LiteralPath</span></span>

<span data-ttu-id="cf533-156">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="cf533-156">Specifies a path to one or more locations.</span></span> <span data-ttu-id="cf533-157">O valor do parâmetro **LiteralPath** é usado exatamente como inserido.</span><span class="sxs-lookup"><span data-stu-id="cf533-157">The value of the **LiteralPath** parameter is used exactly as entered.</span></span> <span data-ttu-id="cf533-158">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="cf533-158">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="cf533-159">Se o caminho incluir caracteres de escape, coloque-os entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="cf533-159">If the path includes escape characters, enclose them in single quotation marks.</span></span> <span data-ttu-id="cf533-160">O PowerShell não interpreta nenhum caractere entre aspas simples como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="cf533-160">PowerShell does not interpret any characters enclosed in single quotation marks as escape sequences.</span></span>

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

### <span data-ttu-id="cf533-161">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="cf533-161">-MaximumVersion</span></span>

<span data-ttu-id="cf533-162">Especifica a versão máxima ou mais recente do módulo a ser salva.</span><span class="sxs-lookup"><span data-stu-id="cf533-162">Specifies the maximum, or newest, version of the module to save.</span></span> <span data-ttu-id="cf533-163">Os parâmetros **MaximumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="cf533-163">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="cf533-164">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="cf533-164">-MinimumVersion</span></span>

<span data-ttu-id="cf533-165">Especifica a versão mínima de um único módulo para salvar.</span><span class="sxs-lookup"><span data-stu-id="cf533-165">Specifies the minimum version of a single module to save.</span></span> <span data-ttu-id="cf533-166">Você não poderá adicionar esse parâmetro se estiver tentando instalar vários módulos.</span><span class="sxs-lookup"><span data-stu-id="cf533-166">You cannot add this parameter if you are attempting to install multiple modules.</span></span> <span data-ttu-id="cf533-167">Os parâmetros **MinimumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="cf533-167">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="cf533-168">-Name</span><span class="sxs-lookup"><span data-stu-id="cf533-168">-Name</span></span>

<span data-ttu-id="cf533-169">Especifica uma matriz de nomes de módulos a serem salvos.</span><span class="sxs-lookup"><span data-stu-id="cf533-169">Specifies an array of names of modules to save.</span></span>

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

### <span data-ttu-id="cf533-170">-Path</span><span class="sxs-lookup"><span data-stu-id="cf533-170">-Path</span></span>

<span data-ttu-id="cf533-171">Especifica o local no computador local para armazenar um módulo salvo.</span><span class="sxs-lookup"><span data-stu-id="cf533-171">Specifies the location on the local computer to store a saved module.</span></span> <span data-ttu-id="cf533-172">Aceita caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="cf533-172">Accepts wildcard characters.</span></span>

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

### <span data-ttu-id="cf533-173">-Proxy</span><span class="sxs-lookup"><span data-stu-id="cf533-173">-Proxy</span></span>

<span data-ttu-id="cf533-174">Especifica um servidor proxy para a solicitação, em vez de conectar-se diretamente ao recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="cf533-174">Specifies a proxy server for the request, rather than connecting directly to the internet resource.</span></span>

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

### <span data-ttu-id="cf533-175">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="cf533-175">-ProxyCredential</span></span>

<span data-ttu-id="cf533-176">Especifica uma conta de usuário com permissão para conectar-se aos computadores especificados pelo parâmetro **Proxy** .</span><span class="sxs-lookup"><span data-stu-id="cf533-176">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="cf533-177">-Repositório</span><span class="sxs-lookup"><span data-stu-id="cf533-177">-Repository</span></span>

<span data-ttu-id="cf533-178">Especifica o nome amigável de um repositório que foi registrado pela execução `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="cf533-178">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span> <span data-ttu-id="cf533-179">Use `Get-PSRepository` para exibir repositórios registrados.</span><span class="sxs-lookup"><span data-stu-id="cf533-179">Use `Get-PSRepository` to display registered repositories.</span></span>

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

### <span data-ttu-id="cf533-180">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="cf533-180">-RequiredVersion</span></span>

<span data-ttu-id="cf533-181">Especifica o número de versão exato do módulo a ser salvo.</span><span class="sxs-lookup"><span data-stu-id="cf533-181">Specifies the exact version number of the module to save.</span></span>

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

### <span data-ttu-id="cf533-182">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="cf533-182">-WhatIf</span></span>

<span data-ttu-id="cf533-183">Mostra o que aconteceria se o `Save-Module` for executado.</span><span class="sxs-lookup"><span data-stu-id="cf533-183">Shows what would happen if the `Save-Module` runs.</span></span> <span data-ttu-id="cf533-184">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="cf533-184">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="cf533-185">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="cf533-185">CommonParameters</span></span>

<span data-ttu-id="cf533-186">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="cf533-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cf533-187">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="cf533-187">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cf533-188">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="cf533-188">INPUTS</span></span>

### <span data-ttu-id="cf533-189">System.String[]</span><span class="sxs-lookup"><span data-stu-id="cf533-189">System.String[]</span></span>

### <span data-ttu-id="cf533-190">System. Management. Automation. PSObject []</span><span class="sxs-lookup"><span data-stu-id="cf533-190">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="cf533-191">System.String</span><span class="sxs-lookup"><span data-stu-id="cf533-191">System.String</span></span>

### <span data-ttu-id="cf533-192">System.Uri</span><span class="sxs-lookup"><span data-stu-id="cf533-192">System.Uri</span></span>

### <span data-ttu-id="cf533-193">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="cf533-193">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="cf533-194">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="cf533-194">OUTPUTS</span></span>

### <span data-ttu-id="cf533-195">System.Object</span><span class="sxs-lookup"><span data-stu-id="cf533-195">System.Object</span></span>

## <span data-ttu-id="cf533-196">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="cf533-196">NOTES</span></span>

## <span data-ttu-id="cf533-197">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="cf533-197">RELATED LINKS</span></span>

