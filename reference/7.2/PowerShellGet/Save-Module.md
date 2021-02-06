---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 11/11/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/save-module?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Module
ms.openlocfilehash: df5056b4402664602409388825c8b2b8acd4e02f
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "99595766"
---
# <span data-ttu-id="9f60a-102">Save-Module</span><span class="sxs-lookup"><span data-stu-id="9f60a-102">Save-Module</span></span>

## <span data-ttu-id="9f60a-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="9f60a-103">SYNOPSIS</span></span>
<span data-ttu-id="9f60a-104">Salva um módulo e suas dependências no computador local, mas não instala o módulo.</span><span class="sxs-lookup"><span data-stu-id="9f60a-104">Saves a module and its dependencies on the local computer but doesn't install the module.</span></span>

## <span data-ttu-id="9f60a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9f60a-105">SYNTAX</span></span>

### <span data-ttu-id="9f60a-106">NameAndPathParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="9f60a-106">NameAndPathParameterSet (Default)</span></span>

```
Save-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9f60a-107">NameAndLiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="9f60a-107">NameAndLiteralPathParameterSet</span></span>

```
Save-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9f60a-108">InputObjectAndLiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="9f60a-108">InputObjectAndLiteralPathParameterSet</span></span>

```
Save-Module [-InputObject] <PSObject[]> -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9f60a-109">InputObjectAndPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="9f60a-109">InputObjectAndPathParameterSet</span></span>

```
Save-Module [-InputObject] <PSObject[]> [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9f60a-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9f60a-110">DESCRIPTION</span></span>

<span data-ttu-id="9f60a-111">O `Save-Module` cmdlet baixa um módulo e quaisquer dependências de um repositório registrado.</span><span class="sxs-lookup"><span data-stu-id="9f60a-111">The `Save-Module` cmdlet downloads a module and any dependencies from a registered repository.</span></span>
<span data-ttu-id="9f60a-112">`Save-Module` baixa e salva a versão mais atual de um módulo.</span><span class="sxs-lookup"><span data-stu-id="9f60a-112">`Save-Module` downloads and saves the most current version of a module.</span></span> <span data-ttu-id="9f60a-113">Os arquivos são salvos em um caminho especificado no computador local.</span><span class="sxs-lookup"><span data-stu-id="9f60a-113">The files are saved to a specified path on the local computer.</span></span> <span data-ttu-id="9f60a-114">O módulo não está instalado, mas o conteúdo está disponível para inspeção por um administrador.</span><span class="sxs-lookup"><span data-stu-id="9f60a-114">The module isn't installed, but the contents are available for inspection by an administrator.</span></span> <span data-ttu-id="9f60a-115">O módulo salvo pode então ser copiado para o `$env:PSModulePath` local apropriado do computador offline.</span><span class="sxs-lookup"><span data-stu-id="9f60a-115">The saved module can then be copied into the appropriate `$env:PSModulePath` location of the offline machine.</span></span>

<span data-ttu-id="9f60a-116">`Get-PSRepository` exibe os repositórios registrados do computador local.</span><span class="sxs-lookup"><span data-stu-id="9f60a-116">`Get-PSRepository` displays the local computer's registered repositories.</span></span> <span data-ttu-id="9f60a-117">Você pode usar o `Find-Module` cmdlet para pesquisar repositórios registrados.</span><span class="sxs-lookup"><span data-stu-id="9f60a-117">You can use the `Find-Module` cmdlet to search registered repositories.</span></span>

## <span data-ttu-id="9f60a-118">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="9f60a-118">EXAMPLES</span></span>

### <span data-ttu-id="9f60a-119">Exemplo 1: salvar um módulo</span><span class="sxs-lookup"><span data-stu-id="9f60a-119">Example 1: Save a module</span></span>

<span data-ttu-id="9f60a-120">Neste exemplo, um módulo e suas dependências são salvos no computador local.</span><span class="sxs-lookup"><span data-stu-id="9f60a-120">In this example, a module and its dependencies are saved to the local computer.</span></span>

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

<span data-ttu-id="9f60a-121">`Save-Module` usa o parâmetro **Name** para especificar o módulo, **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="9f60a-121">`Save-Module` uses the **Name** parameter to specify the module, **PowerShellGet**.</span></span> <span data-ttu-id="9f60a-122">O parâmetro **path** especifica onde armazenar o módulo baixado.</span><span class="sxs-lookup"><span data-stu-id="9f60a-122">The **Path** parameter specifies where to store the downloaded module.</span></span> <span data-ttu-id="9f60a-123">O parâmetro **Repository** especifica um repositório registrado, **PSGallery**.</span><span class="sxs-lookup"><span data-stu-id="9f60a-123">The **Repository** parameter specifies a registered repository, **PSGallery**.</span></span> <span data-ttu-id="9f60a-124">Depois que o download for concluído, o `Get-ChildItem` exibirá o conteúdo do **caminho** onde os arquivos são armazenados.</span><span class="sxs-lookup"><span data-stu-id="9f60a-124">After the download is finished, `Get-ChildItem` displays the contents of **Path** where the files are stored.</span></span>

### <span data-ttu-id="9f60a-125">Exemplo 2: salvar uma versão específica de um módulo</span><span class="sxs-lookup"><span data-stu-id="9f60a-125">Example 2: Save a specific version of a module</span></span>

<span data-ttu-id="9f60a-126">Este exemplo mostra como usar um parâmetro como **MaximumVersion**, ou **RequiredVersion** para especificar uma versão de módulo.</span><span class="sxs-lookup"><span data-stu-id="9f60a-126">This example shows how to use a parameter such as **MaximumVersion**, or **RequiredVersion** to specify a module version.</span></span>

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

<span data-ttu-id="9f60a-127">`Save-Module` usa o parâmetro **Name** para especificar o módulo, **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="9f60a-127">`Save-Module` uses the **Name** parameter to specify the module, **PowerShellGet**.</span></span> <span data-ttu-id="9f60a-128">O parâmetro **path** especifica onde armazenar o módulo baixado.</span><span class="sxs-lookup"><span data-stu-id="9f60a-128">The **Path** parameter specifies where to store the downloaded module.</span></span> <span data-ttu-id="9f60a-129">O parâmetro **Repository** especifica um repositório registrado, **PSGallery**.</span><span class="sxs-lookup"><span data-stu-id="9f60a-129">The **Repository** parameter specifies a registered repository, **PSGallery**.</span></span> <span data-ttu-id="9f60a-130">**MaximumVersion** especifica que a versão **2.1.0** é baixada e salva.</span><span class="sxs-lookup"><span data-stu-id="9f60a-130">**MaximumVersion** specifies that version **2.1.0** is downloaded and saved.</span></span> <span data-ttu-id="9f60a-131">Depois que o download for concluído, o `Get-ChildItem` exibirá o conteúdo do **caminho** onde os arquivos são armazenados.</span><span class="sxs-lookup"><span data-stu-id="9f60a-131">After the download is finished, `Get-ChildItem` displays the contents of **Path** where the files are stored.</span></span>

### <span data-ttu-id="9f60a-132">Exemplo 3: localizar e salvar uma versão específica de um módulo</span><span class="sxs-lookup"><span data-stu-id="9f60a-132">Example 3: Find and save a specific version of a module</span></span>

<span data-ttu-id="9f60a-133">Neste exemplo, uma versão de módulo necessária é encontrada no repositório e salva no computador local.</span><span class="sxs-lookup"><span data-stu-id="9f60a-133">In this example, a required module version is found in the repository and saved to the local computer.</span></span>

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

<span data-ttu-id="9f60a-134">`Find-Module` usa o parâmetro **Name** para especificar o módulo, **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="9f60a-134">`Find-Module` uses the **Name** parameter to specify the module, **PowerShellGet**.</span></span> <span data-ttu-id="9f60a-135">O parâmetro **Repository** especifica um repositório registrado, **PSGallery**.</span><span class="sxs-lookup"><span data-stu-id="9f60a-135">The **Repository** parameter specifies a registered repository, **PSGallery**.</span></span> <span data-ttu-id="9f60a-136">**RequiredVersion** especifica a versão **1.6.5**.</span><span class="sxs-lookup"><span data-stu-id="9f60a-136">**RequiredVersion** specifies version **1.6.5**.</span></span>

<span data-ttu-id="9f60a-137">O objeto é enviado ao pipeline para `Save-Module` .</span><span class="sxs-lookup"><span data-stu-id="9f60a-137">The object is sent down the pipeline to `Save-Module`.</span></span> <span data-ttu-id="9f60a-138">O parâmetro **path** especifica onde armazenar o módulo baixado.</span><span class="sxs-lookup"><span data-stu-id="9f60a-138">The **Path** parameter specifies where to store the downloaded module.</span></span> <span data-ttu-id="9f60a-139">Depois que o download for concluído, o `Get-ChildItem` exibirá o conteúdo do **caminho** onde os arquivos são armazenados.</span><span class="sxs-lookup"><span data-stu-id="9f60a-139">After the download is finished, `Get-ChildItem` displays the contents of **Path** where the files are stored.</span></span>

## <span data-ttu-id="9f60a-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9f60a-140">PARAMETERS</span></span>

### <span data-ttu-id="9f60a-141">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="9f60a-141">-AcceptLicense</span></span>

<span data-ttu-id="9f60a-142">Aceite automaticamente o contrato de licença se o pacote exigir.</span><span class="sxs-lookup"><span data-stu-id="9f60a-142">Automatically accept the license agreement if the package requires it.</span></span>

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

### <span data-ttu-id="9f60a-143">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="9f60a-143">-AllowPrerelease</span></span>

<span data-ttu-id="9f60a-144">Permite salvar um módulo marcado como um pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="9f60a-144">Allows you to save a module marked as a prerelease.</span></span>

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

### <span data-ttu-id="9f60a-145">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9f60a-145">-Confirm</span></span>

<span data-ttu-id="9f60a-146">Solicita a confirmação antes de executar o `Save-Module` .</span><span class="sxs-lookup"><span data-stu-id="9f60a-146">Prompts you for confirmation before running the `Save-Module`.</span></span>

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

### <span data-ttu-id="9f60a-147">-Credential</span><span class="sxs-lookup"><span data-stu-id="9f60a-147">-Credential</span></span>

<span data-ttu-id="9f60a-148">Especifica uma conta de usuário que tem direitos para salvar um módulo.</span><span class="sxs-lookup"><span data-stu-id="9f60a-148">Specifies a user account that has rights to save a module.</span></span>

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

### <span data-ttu-id="9f60a-149">-Force</span><span class="sxs-lookup"><span data-stu-id="9f60a-149">-Force</span></span>

<span data-ttu-id="9f60a-150">Forças `Save-Module` a serem executadas sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="9f60a-150">Forces `Save-Module` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="9f60a-151">-InputObject</span><span class="sxs-lookup"><span data-stu-id="9f60a-151">-InputObject</span></span>

<span data-ttu-id="9f60a-152">Aceita um objeto **PSRepositoryItemInfo** .</span><span class="sxs-lookup"><span data-stu-id="9f60a-152">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="9f60a-153">Por exemplo, saída `Find-Module` para uma variável e use essa variável como o argumento **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="9f60a-153">For example, output `Find-Module` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="9f60a-154">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="9f60a-154">-LiteralPath</span></span>

<span data-ttu-id="9f60a-155">Especifica um caminho para um ou mais locais.</span><span class="sxs-lookup"><span data-stu-id="9f60a-155">Specifies a path to one or more locations.</span></span> <span data-ttu-id="9f60a-156">O valor do parâmetro **LiteralPath** é usado exatamente como inserido.</span><span class="sxs-lookup"><span data-stu-id="9f60a-156">The value of the **LiteralPath** parameter is used exactly as entered.</span></span> <span data-ttu-id="9f60a-157">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="9f60a-157">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="9f60a-158">Se o caminho incluir caracteres de escape, coloque-os entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="9f60a-158">If the path includes escape characters, enclose them in single quotation marks.</span></span> <span data-ttu-id="9f60a-159">O PowerShell não interpreta nenhum caractere entre aspas simples como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="9f60a-159">PowerShell does not interpret any characters enclosed in single quotation marks as escape sequences.</span></span>

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

### <span data-ttu-id="9f60a-160">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="9f60a-160">-MaximumVersion</span></span>

<span data-ttu-id="9f60a-161">Especifica a versão máxima ou mais recente do módulo a ser salva.</span><span class="sxs-lookup"><span data-stu-id="9f60a-161">Specifies the maximum, or newest, version of the module to save.</span></span> <span data-ttu-id="9f60a-162">Os parâmetros **MaximumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="9f60a-162">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="9f60a-163">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="9f60a-163">-MinimumVersion</span></span>

<span data-ttu-id="9f60a-164">Especifica a versão mínima de um único módulo para salvar.</span><span class="sxs-lookup"><span data-stu-id="9f60a-164">Specifies the minimum version of a single module to save.</span></span> <span data-ttu-id="9f60a-165">Você não poderá adicionar esse parâmetro se estiver tentando instalar vários módulos.</span><span class="sxs-lookup"><span data-stu-id="9f60a-165">You cannot add this parameter if you are attempting to install multiple modules.</span></span> <span data-ttu-id="9f60a-166">Os parâmetros **MinimumVersion** e **RequiredVersion** não podem ser usados no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="9f60a-166">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="9f60a-167">-Name</span><span class="sxs-lookup"><span data-stu-id="9f60a-167">-Name</span></span>

<span data-ttu-id="9f60a-168">Especifica uma matriz de nomes de módulos a serem salvos.</span><span class="sxs-lookup"><span data-stu-id="9f60a-168">Specifies an array of names of modules to save.</span></span>

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

### <span data-ttu-id="9f60a-169">-Path</span><span class="sxs-lookup"><span data-stu-id="9f60a-169">-Path</span></span>

<span data-ttu-id="9f60a-170">Especifica o local no computador local para armazenar um módulo salvo.</span><span class="sxs-lookup"><span data-stu-id="9f60a-170">Specifies the location on the local computer to store a saved module.</span></span> <span data-ttu-id="9f60a-171">Aceita caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="9f60a-171">Accepts wildcard characters.</span></span>

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

### <span data-ttu-id="9f60a-172">-Proxy</span><span class="sxs-lookup"><span data-stu-id="9f60a-172">-Proxy</span></span>

<span data-ttu-id="9f60a-173">Especifica um servidor proxy para a solicitação, em vez de conectar-se diretamente ao recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="9f60a-173">Specifies a proxy server for the request, rather than connecting directly to the internet resource.</span></span>

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

### <span data-ttu-id="9f60a-174">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="9f60a-174">-ProxyCredential</span></span>

<span data-ttu-id="9f60a-175">Especifica uma conta de usuário com permissão para conectar-se aos computadores especificados pelo parâmetro **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="9f60a-175">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="9f60a-176">-Repositório</span><span class="sxs-lookup"><span data-stu-id="9f60a-176">-Repository</span></span>

<span data-ttu-id="9f60a-177">Especifica o nome amigável de um repositório que foi registrado pela execução `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="9f60a-177">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span> <span data-ttu-id="9f60a-178">Use `Get-PSRepository` para exibir repositórios registrados.</span><span class="sxs-lookup"><span data-stu-id="9f60a-178">Use `Get-PSRepository` to display registered repositories.</span></span>

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

### <span data-ttu-id="9f60a-179">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="9f60a-179">-RequiredVersion</span></span>

<span data-ttu-id="9f60a-180">Especifica o número de versão exato do módulo a ser salvo.</span><span class="sxs-lookup"><span data-stu-id="9f60a-180">Specifies the exact version number of the module to save.</span></span>

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

### <span data-ttu-id="9f60a-181">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9f60a-181">-WhatIf</span></span>

<span data-ttu-id="9f60a-182">Mostra o que aconteceria se o `Save-Module` for executado.</span><span class="sxs-lookup"><span data-stu-id="9f60a-182">Shows what would happen if the `Save-Module` runs.</span></span> <span data-ttu-id="9f60a-183">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="9f60a-183">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="9f60a-184">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9f60a-184">CommonParameters</span></span>

<span data-ttu-id="9f60a-185">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9f60a-185">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9f60a-186">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9f60a-186">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9f60a-187">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="9f60a-187">INPUTS</span></span>

### <span data-ttu-id="9f60a-188">System.String[]</span><span class="sxs-lookup"><span data-stu-id="9f60a-188">System.String[]</span></span>

### <span data-ttu-id="9f60a-189">System. Management. Automation. PSObject []</span><span class="sxs-lookup"><span data-stu-id="9f60a-189">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="9f60a-190">System.String</span><span class="sxs-lookup"><span data-stu-id="9f60a-190">System.String</span></span>

### <span data-ttu-id="9f60a-191">System.Uri</span><span class="sxs-lookup"><span data-stu-id="9f60a-191">System.Uri</span></span>

### <span data-ttu-id="9f60a-192">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="9f60a-192">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="9f60a-193">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="9f60a-193">OUTPUTS</span></span>

### <span data-ttu-id="9f60a-194">System.Object</span><span class="sxs-lookup"><span data-stu-id="9f60a-194">System.Object</span></span>

## <span data-ttu-id="9f60a-195">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="9f60a-195">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9f60a-196">A partir de abril de 2020, a Galeria do PowerShell não dará mais suporte às versões 1.0 e 1.1 do protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="9f60a-196">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="9f60a-197">Se você não estiver usando o TLS 1.2 ou posterior, receberá um erro ao tentar acessar a Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9f60a-197">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="9f60a-198">Use o seguinte comando para garantir que esteja usando o TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="9f60a-198">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="9f60a-199">Para obter mais informações, confira o [comunicado](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) no blog do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9f60a-199">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="9f60a-200">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="9f60a-200">RELATED LINKS</span></span>
