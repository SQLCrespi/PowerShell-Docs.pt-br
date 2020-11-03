---
external help file: PSModule-help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/install-script?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-Script
ms.openlocfilehash: ae3d0e3c9f70381884f3e12b19111e4c4eb47307
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194127"
---
# <span data-ttu-id="7601d-103">Install-Script</span><span class="sxs-lookup"><span data-stu-id="7601d-103">Install-Script</span></span>

## <span data-ttu-id="7601d-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="7601d-104">SYNOPSIS</span></span>
<span data-ttu-id="7601d-105">Instala um script.</span><span class="sxs-lookup"><span data-stu-id="7601d-105">Installs a script.</span></span>

## <span data-ttu-id="7601d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7601d-106">SYNTAX</span></span>

### <span data-ttu-id="7601d-107">NameParameterSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="7601d-107">NameParameterSet (Default)</span></span>

```
Install-Script [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Scope <String>] [-NoPathUpdate] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]

```

### <span data-ttu-id="7601d-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="7601d-108">InputObject</span></span>

```
Install-Script [-InputObject] <PSObject[]> [-Scope <String>] [-NoPathUpdate] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="7601d-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7601d-109">DESCRIPTION</span></span>

<span data-ttu-id="7601d-110">O `Install-Script` cmdlet adquire uma carga de script de um repositório, verifica se a carga é um script do PowerShell válido e copia o arquivo de script para um local de instalação especificado.</span><span class="sxs-lookup"><span data-stu-id="7601d-110">The `Install-Script` cmdlet acquires a script payload from a repository, verifies that the payload is a valid PowerShell script, and copies the script file to a specified installation location.</span></span>

<span data-ttu-id="7601d-111">Os repositórios padrão `Install-Script` operam com o são configuráveis por meio dos `Register-PSRepository` `Set-PSRepository` `Unregister-PSRepository` cmdlets,, e `Get-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="7601d-111">The default repositories `Install-Script` operates against are configurable through the `Register-PSRepository`, `Set-PSRepository`, `Unregister-PSRepository`, and `Get-PSRepository` cmdlets.</span></span> <span data-ttu-id="7601d-112">Ao operar em vários repositórios, `Install-Script` o instala o primeiro script que corresponde aos critérios de pesquisa especificados ( **Name** , **MinimumVersion** ou **MaximumVersion** ) do primeiro repositório sem nenhum erro.</span><span class="sxs-lookup"><span data-stu-id="7601d-112">When operating against multiple repositories, `Install-Script` installs the first script that matches the specified search criteria ( **Name** , **MinimumVersion** , or **MaximumVersion** ) from the first repository without any error.</span></span>

## <span data-ttu-id="7601d-113">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="7601d-113">EXAMPLES</span></span>

### <span data-ttu-id="7601d-114">Exemplo 1: localizar um script e instalá-lo</span><span class="sxs-lookup"><span data-stu-id="7601d-114">Example 1: Find a script and install it</span></span>

```
PS C:\> Find-Script -Repository "Local1" -Name "Required-Script2"
Version    Name                           Type       Repository           Description
-------    ----                           ----       ----------           -----------
2.5        Required-Script2               Script     local1               Description for the Required-Script2 script

PS C:\> Find-Script -Repository "Local1" -Name "Required-Script2" | Install-Script
PS C:\> Get-Command -Name "Required-Script2"
CommandType     Name                      Version    Source
-----------     ----                      -------    ------
ExternalScript  Required-Script2.ps1      2.0       C:\Users\pattif\Documents\WindowsPowerShell\Scripts\Required-Script2.ps1

PS C:\> Get-InstalledScript -Name "Required-Script2"
Version    Name                  Type     Repository           Description
-------    ----                  ----     ----------           -----------
2.5        Required-Script2      Script   local1               Description for the Required-Script2 script

PS C:\> Get-InstalledScript -Name "Required-Script2" | Format-List *
Name                       : Required-Script2
Version                    : 2.5
Type                       : Script
Description                : Description for the Required-Script2 script
Author                     : pattif
CompanyName                :
Copyright                  : 2015 Microsoft Corporation. All rights reserved.
PublishedDate              : 8/15/2015 12:42:39 AM
LicenseUri                 : http://required-script2.com/license
ProjectUri                 : http://required-script2.com/
IconUri                    : http://required-script2.com/icon
Tags                       : {Tag1, Tag2, Tag-Required-Script2-2.5, PSScript...}
Includes                   : {Function, DscResource, Cmdlet, Command}
PowerShellGetFormatVersion :
ReleaseNotes               : Required-Script2 release notes
Dependencies               : {}
RepositorySourceLocation   : http://pattif-dev:8765/api/v2/
Repository                 : local1
PackageManagementProvider  : NuGet
InstalledLocation          : C:\Users\pattif\Documents\WindowsPowerShell\Scripts
```

<span data-ttu-id="7601d-115">O primeiro comando localiza o script chamado `Required-Script2` no repositório do local1 e exibe os resultados.</span><span class="sxs-lookup"><span data-stu-id="7601d-115">The first command finds the script named `Required-Script2` from the Local1 repository and displays the results.</span></span>

<span data-ttu-id="7601d-116">O segundo comando localiza o `Required-Script2` script e, em seguida, usa o operador de pipeline para passá-lo para o `Install-Script` cmdlet para instalá-lo.</span><span class="sxs-lookup"><span data-stu-id="7601d-116">The second command finds the `Required-Script2` script, and then uses the pipeline operator to pass it to the `Install-Script` cmdlet to install it.</span></span>

<span data-ttu-id="7601d-117">O terceiro comando usa o `Get-Command` cmdlet para obter `Required-Script2` e, em seguida, exibe os resultados.</span><span class="sxs-lookup"><span data-stu-id="7601d-117">The third command uses the `Get-Command` cmdlet to get `Required-Script2`, and then displays the results.</span></span>

<span data-ttu-id="7601d-118">O quarto comando usa o `Get-InstalledScript` cmdlet para obter `Required-Script2` e exibir os resultados.</span><span class="sxs-lookup"><span data-stu-id="7601d-118">The fourth command uses the `Get-InstalledScript` cmdlet to get `Required-Script2` and display the results.</span></span>

<span data-ttu-id="7601d-119">O quinto comando obtém `Required-Script2` e usa o operador de pipeline para passá-lo para o `Format-List` cmdlet para formatar a saída.</span><span class="sxs-lookup"><span data-stu-id="7601d-119">The fifth command gets `Required-Script2` and uses the pipeline operator to pass it to the `Format-List` cmdlet to format the output.</span></span>

### <span data-ttu-id="7601d-120">Exemplo 2: instalar um script com escopo AllUsers</span><span class="sxs-lookup"><span data-stu-id="7601d-120">Example 2: Install a script with AllUsers scope</span></span>

```
PS C:\> Install-Script -Repository "Local1" -Name "Required-Script3" -Scope "AllUsers"
PS C:\> Get-InstalledScript -Name "Required-Script3"
Version    Name                  Type       Repository    Description
-------    ----                  ----       ----------    -----------
2.5        Required-Script3      Script     local1        Description for the Required-Script3 script

PS C:\> Get-InstalledScript -Name "Required-Script3" | Format-List *
Name                       : Required-Script3
Version                    : 2.5
Type                       : Script
Description                : Description for the Required-Script3 script
Author                     : pattif
CompanyName                :
Copyright                  : 2015 Microsoft Corporation. All rights reserved.
PublishedDate              : 8/15/2015 12:42:45 AM
LicenseUri                 : http://required-script3.com/license
ProjectUri                 : http://required-script3.com/
IconUri                    : http://required-script3.com/icon
Tags                       : {Tag1, Tag2, Tag-Required-Script3-2.5, PSScript...}
Includes                   : {Function, DscResource, Cmdlet, Command}
PowerShellGetFormatVersion :
ReleaseNotes               : Required-Script3 release notes
Dependencies               : {}
RepositorySourceLocation   : http://pattif-dev:8765/api/v2/
Repository                 : local1
PackageManagementProvider  : NuGet
InstalledLocation          : C:\Program Files\WindowsPowerShell\Scripts
```

<span data-ttu-id="7601d-121">O primeiro comando instala o script chamado `Required-Script3` e atribui a ele o escopo AllUsers.</span><span class="sxs-lookup"><span data-stu-id="7601d-121">The first command installs the script named `Required-Script3` and assigns it AllUsers scope.</span></span>

<span data-ttu-id="7601d-122">O segundo comando obtém o script instalado `Required-Script3` e exibe informações sobre ele.</span><span class="sxs-lookup"><span data-stu-id="7601d-122">The second command gets the installed script `Required-Script3` and displays information about it.</span></span>

<span data-ttu-id="7601d-123">O terceiro comando obtém `Required-Script3` e usa o operador de pipeline para passá-lo para o `Format-List` cmdlet para formatar a saída.</span><span class="sxs-lookup"><span data-stu-id="7601d-123">The third command gets `Required-Script3` and uses the pipeline operator to pass it to the `Format-List` cmdlet to format the output.</span></span>

### <span data-ttu-id="7601d-124">Exemplo 3: instalar um script e suas dependências</span><span class="sxs-lookup"><span data-stu-id="7601d-124">Example 3: Install a script and its dependencies</span></span>

```
PS C:\> Find-Script -Repository "Local1" -Name "Script-WithDependencies2" -IncludeDependencies
Version    Name                        Type       Repository    Description
-------    ----                        ----       ----------    -----------
2.0        Script-WithDependencies2    Script     local1        Description for the Script-WithDependencies2 script
2.5        RequiredModule1             Module     local1        RequiredModule1 module
2.5        RequiredModule2             Module     local1        RequiredModule2 module
2.5        RequiredModule3             Module     local1        RequiredModule3 module
2.5        Required-Script1            Script     local1        Description for the Required-Script1 script
2.5        Required-Script2            Script     local1        Description for the Required-Script2 script
2.5        Required-Script3            Script     local1        Description for the Required-Script3 script

PS C:\> Install-Script -Repository "Local1" -Name "Script-WithDependencies2"
PS C:\> Get-InstalledScript
Version    Name                        Type       Repository    Description
-------    ----                        ----       ----------    -----------
2.5        Required-Script1            Script     local1        Description for the Required-Script1 script
2.5        Required-Script2            Script     local1        Description for the Required-Script2 script
2.5        Required-Script3            Script     local1        Description for the Required-Script3 script
2.0        Script-WithDependencies2    Script     local1        Description for the Script-WithDependencies2 script

PS C:\> Get-InstalledModule
Version    Name                        Type       Repository    Description
-------    ----                        ----       ----------    -----------
2.5        RequiredModule1             Module     local1        RequiredModule1 module
2.5        RequiredModule2             Module     local1        RequiredModule2 module
2.5        RequiredModule3             Module     local1        RequiredModule3 module

PS C:\> Find-Script -Repository "Local1" -Name "Required-Script*"
Version    Name                        Type       Repository    Description
-------    ----                        ----       ----------    -----------
2.5        Required-Script1            Script     local1        Description for the Required-Script1 script
2.5        Required-Script2            Script     local1        Description for the Required-Script2 script
2.5        Required-Script3            Script     local1        Description for the Required-Script3 script

PS C:\> Install-Script -Repository "Local1" -Name "Required-Script*"
PS C:\> Get-InstalledScript
Version    Name                        Type       Repository    Description
-------    ----                        ----       ----------    -----------
2.5        Required-Script1            Script     local1        Description for the Required-Script1 script
2.5        Required-Script2            Script     local1        Description for the Required-Script2 script
2.5        Required-Script3            Script     local1        Description for the Required-Script3 script
```

<span data-ttu-id="7601d-125">O primeiro comando localiza o script denominado `Script-WithDependencies2` e suas dependências no repositório do local1 e exibe os resultados.</span><span class="sxs-lookup"><span data-stu-id="7601d-125">The first command finds the script named `Script-WithDependencies2` and its dependencies in the Local1 repository and displays the results.</span></span>

<span data-ttu-id="7601d-126">O segundo comando é instalado `Script-WithDependencies2` .</span><span class="sxs-lookup"><span data-stu-id="7601d-126">The second command installs `Script-WithDependencies2`.</span></span>

<span data-ttu-id="7601d-127">O terceiro comando usa o `Get-InstalledScript` cmdlet de script para obter os scripts instalados e exibir os resultados.</span><span class="sxs-lookup"><span data-stu-id="7601d-127">The third command uses the `Get-InstalledScript` script cmdlet to get installed scripts and display the results.</span></span>

<span data-ttu-id="7601d-128">O quarto comando usa o `Get-InstalledModule` cmdlet para obter os módulos instalados e exibir os resultados.</span><span class="sxs-lookup"><span data-stu-id="7601d-128">The fourth command uses the `Get-InstalledModule` cmdlet to get installed modules and display the results.</span></span>

<span data-ttu-id="7601d-129">O quinto comando usa o `Find-Script` cmdlet para localizar scripts em que o nome começa com `Required-Script` e exibe os resultados.</span><span class="sxs-lookup"><span data-stu-id="7601d-129">The fifth command uses the `Find-Script` cmdlet to find scripts where the name begins with `Required-Script` and display the results.</span></span>

<span data-ttu-id="7601d-130">O sexto comando instala os scripts em que o nome começa com `Required-Script` no repositório do local1.</span><span class="sxs-lookup"><span data-stu-id="7601d-130">The sixth command installs the scripts where the name begins with `Required-Script` in the Local1 repository.</span></span>

<span data-ttu-id="7601d-131">O comando final Obtém os scripts instalados e exibe os resultados.</span><span class="sxs-lookup"><span data-stu-id="7601d-131">The final command gets installed scripts and displays the results.</span></span>

## <span data-ttu-id="7601d-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7601d-132">PARAMETERS</span></span>

### <span data-ttu-id="7601d-133">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="7601d-133">-AcceptLicense</span></span>

<span data-ttu-id="7601d-134">Aceite automaticamente o contrato de licença durante a instalação se o módulo exigir.</span><span class="sxs-lookup"><span data-stu-id="7601d-134">Automatically accept the license agreement during installation if the module requires it.</span></span>

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

### <span data-ttu-id="7601d-135">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="7601d-135">-AllowPrerelease</span></span>

<span data-ttu-id="7601d-136">Permite que você instale um script marcado como um pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="7601d-136">Allows you to install a script marked as a prerelease.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7601d-137">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7601d-137">-Confirm</span></span>

<span data-ttu-id="7601d-138">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7601d-138">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7601d-139">-Credential</span><span class="sxs-lookup"><span data-stu-id="7601d-139">-Credential</span></span>

<span data-ttu-id="7601d-140">Especifica uma conta de usuário que tem direitos para instalar um script para um provedor de pacote ou origem especificado.</span><span class="sxs-lookup"><span data-stu-id="7601d-140">Specifies a user account that has rights to install a script for a specified package provider or source.</span></span>

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

### <span data-ttu-id="7601d-141">-Force</span><span class="sxs-lookup"><span data-stu-id="7601d-141">-Force</span></span>

<span data-ttu-id="7601d-142">Força o comando a ser executado sem solicitar a confirmação do usuário.</span><span class="sxs-lookup"><span data-stu-id="7601d-142">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="7601d-143">-InputObject</span><span class="sxs-lookup"><span data-stu-id="7601d-143">-InputObject</span></span>

<span data-ttu-id="7601d-144">Usado para entrada de pipeline.</span><span class="sxs-lookup"><span data-stu-id="7601d-144">Used for pipeline input.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7601d-145">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="7601d-145">-MaximumVersion</span></span>

<span data-ttu-id="7601d-146">Especifica a versão máxima de um único script a ser instalado.</span><span class="sxs-lookup"><span data-stu-id="7601d-146">Specifies the maximum version of a single scripts to install.</span></span> <span data-ttu-id="7601d-147">Você não poderá adicionar esse parâmetro se estiver tentando instalar vários scripts.</span><span class="sxs-lookup"><span data-stu-id="7601d-147">You cannot add this parameter if you are attempting to install multiple scripts.</span></span> <span data-ttu-id="7601d-148">Os parâmetros **MaximumVersion** e **RequiredVersion** são mutuamente exclusivos; Você não pode usar ambos os parâmetros no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="7601d-148">The **MaximumVersion** and the **RequiredVersion** parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7601d-149">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="7601d-149">-MinimumVersion</span></span>

<span data-ttu-id="7601d-150">Especifica a versão mínima de um único script a ser instalado.</span><span class="sxs-lookup"><span data-stu-id="7601d-150">Specifies the minimum version of a single script to install.</span></span> <span data-ttu-id="7601d-151">Você não poderá adicionar esse parâmetro se estiver tentando instalar vários scripts.</span><span class="sxs-lookup"><span data-stu-id="7601d-151">You cannot add this parameter if you are attempting to install multiple scripts.</span></span> <span data-ttu-id="7601d-152">Os parâmetros **MinimumVersion** e **RequiredVersion** são mutuamente exclusivos; Você não pode usar ambos os parâmetros no mesmo comando.</span><span class="sxs-lookup"><span data-stu-id="7601d-152">The **MinimumVersion** and the **RequiredVersion** parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7601d-153">-Name</span><span class="sxs-lookup"><span data-stu-id="7601d-153">-Name</span></span>

<span data-ttu-id="7601d-154">Especifica uma matriz de nomes de scripts a serem instalados.</span><span class="sxs-lookup"><span data-stu-id="7601d-154">Specifies an array of names of scripts to install.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7601d-155">-NoPathUpdate</span><span class="sxs-lookup"><span data-stu-id="7601d-155">-NoPathUpdate</span></span>

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

### <span data-ttu-id="7601d-156">-PassThru</span><span class="sxs-lookup"><span data-stu-id="7601d-156">-PassThru</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7601d-157">-Proxy</span><span class="sxs-lookup"><span data-stu-id="7601d-157">-Proxy</span></span>

<span data-ttu-id="7601d-158">Especifica um servidor proxy para a solicitação, em vez de conectar-se diretamente ao recurso da Internet.</span><span class="sxs-lookup"><span data-stu-id="7601d-158">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="7601d-159">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="7601d-159">-ProxyCredential</span></span>

<span data-ttu-id="7601d-160">Especifica uma conta de usuário com permissão para conectar-se aos computadores especificados pelo parâmetro **Proxy** .</span><span class="sxs-lookup"><span data-stu-id="7601d-160">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="7601d-161">-Repositório</span><span class="sxs-lookup"><span data-stu-id="7601d-161">-Repository</span></span>

<span data-ttu-id="7601d-162">Especifica o nome amigável de um repositório que foi registrado com o `Register-PSRepository` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7601d-162">Specifies the friendly name of a repository that has been registered with the `Register-PSRepository` cmdlet.</span></span> <span data-ttu-id="7601d-163">O padrão é todos os repositórios registrados.</span><span class="sxs-lookup"><span data-stu-id="7601d-163">The default is all registered repositories.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7601d-164">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="7601d-164">-RequiredVersion</span></span>

<span data-ttu-id="7601d-165">Especifica o número de versão exato do script a ser instalado.</span><span class="sxs-lookup"><span data-stu-id="7601d-165">Specifies the exact version number of the script to install.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7601d-166">-Escopo</span><span class="sxs-lookup"><span data-stu-id="7601d-166">-Scope</span></span>

<span data-ttu-id="7601d-167">Especifica o escopo de instalação do script.</span><span class="sxs-lookup"><span data-stu-id="7601d-167">Specifies the installation scope of the script.</span></span>
<span data-ttu-id="7601d-168">Os valores válidos são: AllUsers e CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="7601d-168">Valid values are: AllUsers and CurrentUser.</span></span>

<span data-ttu-id="7601d-169">O escopo AllUsers permite que os módulos sejam instalados em um local que seja acessível a todos os usuários do computador, ou seja, `$env:ProgramFiles\WindowsPowerShell\Scripts` .</span><span class="sxs-lookup"><span data-stu-id="7601d-169">The AllUsers scope lets modules be installed in a location that is accessible to all users of the computer, that is, `$env:ProgramFiles\WindowsPowerShell\Scripts`.</span></span>

<span data-ttu-id="7601d-170">O escopo CurrentUser permite que os módulos sejam instalados somente no `$home\Documents\WindowsPowerShell\Scripts` , para que o módulo esteja disponível somente para o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="7601d-170">The CurrentUser scope lets modules be installed only to `$home\Documents\WindowsPowerShell\Scripts`, so that the module is available only to the current user.</span></span>

<span data-ttu-id="7601d-171">Quando nenhum **escopo** for definido, o padrão será definido com base na sessão atual:</span><span class="sxs-lookup"><span data-stu-id="7601d-171">When no **Scope** is defined, the default will be set based on the current session:</span></span>

- <span data-ttu-id="7601d-172">Para uma sessão elevada do PowerShell, o **escopo** assume o padrão de AllUsers;</span><span class="sxs-lookup"><span data-stu-id="7601d-172">For an elevated PowerShell session, **Scope** defaults to AllUsers;</span></span>
- <span data-ttu-id="7601d-173">Para sessões do PowerShell não elevadas no [PowerShellGet versões 2.0.0](https://www.powershellgallery.com/packages/PowerShellGet) e superiores, o **escopo** é CurrentUser;</span><span class="sxs-lookup"><span data-stu-id="7601d-173">For non-elevated PowerShell sessions in [PowerShellGet versions 2.0.0](https://www.powershellgallery.com/packages/PowerShellGet) and above, **Scope** is CurrentUser;</span></span>
- <span data-ttu-id="7601d-174">Para sessões do PowerShell não elevadas no PowerShellGet versões 1.6.7 e anteriores, o **escopo** é indefinido e `Install-Module` falha.</span><span class="sxs-lookup"><span data-stu-id="7601d-174">For non-elevated PowerShell sessions in PowerShellGet versions 1.6.7 and earlier, **Scope** is undefined, and `Install-Module` fails.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7601d-175">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7601d-175">-WhatIf</span></span>

<span data-ttu-id="7601d-176">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="7601d-176">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="7601d-177">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="7601d-177">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="7601d-178">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7601d-178">CommonParameters</span></span>

<span data-ttu-id="7601d-179">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7601d-179">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7601d-180">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7601d-180">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7601d-181">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="7601d-181">INPUTS</span></span>

### <span data-ttu-id="7601d-182">System.String[]</span><span class="sxs-lookup"><span data-stu-id="7601d-182">System.String[]</span></span>

### <span data-ttu-id="7601d-183">System. Management. Automation. PSObject []</span><span class="sxs-lookup"><span data-stu-id="7601d-183">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="7601d-184">System.String</span><span class="sxs-lookup"><span data-stu-id="7601d-184">System.String</span></span>

### <span data-ttu-id="7601d-185">System.Uri</span><span class="sxs-lookup"><span data-stu-id="7601d-185">System.Uri</span></span>

### <span data-ttu-id="7601d-186">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="7601d-186">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="7601d-187">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="7601d-187">OUTPUTS</span></span>

### <span data-ttu-id="7601d-188">System.Object</span><span class="sxs-lookup"><span data-stu-id="7601d-188">System.Object</span></span>
## <span data-ttu-id="7601d-189">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="7601d-189">NOTES</span></span>

## <span data-ttu-id="7601d-190">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="7601d-190">RELATED LINKS</span></span>

[<span data-ttu-id="7601d-191">Find-Script</span><span class="sxs-lookup"><span data-stu-id="7601d-191">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="7601d-192">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="7601d-192">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="7601d-193">Save-Script</span><span class="sxs-lookup"><span data-stu-id="7601d-193">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="7601d-194">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="7601d-194">Uninstall-Script</span></span>](Uninstall-Script.md)

[<span data-ttu-id="7601d-195">Update-Script</span><span class="sxs-lookup"><span data-stu-id="7601d-195">Update-Script</span></span>](Update-Script.md)
