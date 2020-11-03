---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/16/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/update-help?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Help
ms.openlocfilehash: 541059691e794591e85a8321a4507ed8838bcb4a
ms.sourcegitcommit: d3f78120bdc9096c72aa0dfdbdd91efaf254c738
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "93195116"
---
# <span data-ttu-id="312f2-103">Update-Help</span><span class="sxs-lookup"><span data-stu-id="312f2-103">Update-Help</span></span>

## <span data-ttu-id="312f2-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="312f2-104">SYNOPSIS</span></span>
<span data-ttu-id="312f2-105">Baixa e instala os arquivos de ajuda mais recentes em seu computador.</span><span class="sxs-lookup"><span data-stu-id="312f2-105">Downloads and installs the newest help files on your computer.</span></span>

## <span data-ttu-id="312f2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="312f2-106">SYNTAX</span></span>

### <span data-ttu-id="312f2-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="312f2-107">Path (Default)</span></span>

```
Update-Help [[-Module] <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [[-SourcePath] <String[]>] [-Recurse] [[-UICulture] <CultureInfo[]>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="312f2-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="312f2-108">LiteralPath</span></span>

```
Update-Help [[-Module] <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [-LiteralPath <String[]>] [-Recurse] [[-UICulture] <CultureInfo[]>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="312f2-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="312f2-109">DESCRIPTION</span></span>

<span data-ttu-id="312f2-110">O `Update-Help` cmdlet baixa os arquivos de ajuda mais recentes para os módulos do PowerShell e os instala em seu computador.</span><span class="sxs-lookup"><span data-stu-id="312f2-110">The `Update-Help` cmdlet downloads the newest help files for PowerShell modules and installs them on your computer.</span></span> <span data-ttu-id="312f2-111">Você não precisa reiniciar o PowerShell para que a alteração seja efetiva.</span><span class="sxs-lookup"><span data-stu-id="312f2-111">You need not restart PowerShell to make the change effective.</span></span> <span data-ttu-id="312f2-112">Você pode usar o `Get-Help` cmdlet para exibir os novos arquivos de ajuda imediatamente.</span><span class="sxs-lookup"><span data-stu-id="312f2-112">You can use the `Get-Help` cmdlet to view the new help files immediately.</span></span>

<span data-ttu-id="312f2-113">`Update-Help` verifica a versão dos arquivos de ajuda em seu computador.</span><span class="sxs-lookup"><span data-stu-id="312f2-113">`Update-Help` checks the version of the help files on your computer.</span></span> <span data-ttu-id="312f2-114">Se você não tiver arquivos de ajuda para um módulo ou se os arquivos de ajuda estiverem desatualizados, `Update-Help` o baixará os arquivos de ajuda mais recentes.</span><span class="sxs-lookup"><span data-stu-id="312f2-114">If you don't have help files for a module or if your help files are outdated, `Update-Help` downloads the newest help files.</span></span> <span data-ttu-id="312f2-115">Os arquivos de ajuda podem ser baixados e instalados da Internet ou de um compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="312f2-115">The help files can be downloaded and installed from the internet or a file share.</span></span>

<span data-ttu-id="312f2-116">Sem parâmetros, `Update-Help` o atualiza os arquivos de ajuda para os módulos na sessão e para todos os módulos instalados que dão suporte à ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="312f2-116">Without parameters, `Update-Help` updates the help files for modules in the session and for all installed modules that support Updatable Help.</span></span> <span data-ttu-id="312f2-117">Os módulos instalados, mas não carregados na sessão atual, estão incluídos.</span><span class="sxs-lookup"><span data-stu-id="312f2-117">Modules that are installed but not loaded in the current session are included.</span></span> <span data-ttu-id="312f2-118">Os módulos do PowerShell são armazenados em um local listado na `$env:PSModulePath` variável de ambiente.</span><span class="sxs-lookup"><span data-stu-id="312f2-118">PowerShell modules are stored in a location listed in the `$env:PSModulePath` environment variable.</span></span> <span data-ttu-id="312f2-119">Para obter mais informações, consulte [about_Updatable_Help](./About/about_Updatable_Help.md).</span><span class="sxs-lookup"><span data-stu-id="312f2-119">For more information, see [about_Updatable_Help](./About/about_Updatable_Help.md).</span></span>

<span data-ttu-id="312f2-120">Você pode usar o parâmetro **Module** para atualizar os arquivos de ajuda de um módulo específico.</span><span class="sxs-lookup"><span data-stu-id="312f2-120">You can use the **Module** parameter to update help files for a particular module.</span></span> <span data-ttu-id="312f2-121">Use o parâmetro **UICulture** para baixar arquivos de ajuda em vários idiomas e localidades.</span><span class="sxs-lookup"><span data-stu-id="312f2-121">Use the **UICulture** parameter to download help files in multiple languages and locales.</span></span>

<span data-ttu-id="312f2-122">Você também pode usar `Update-Help` o em computadores que não estão conectados à Internet.</span><span class="sxs-lookup"><span data-stu-id="312f2-122">You can also use `Update-Help` on computers that are not connected to the internet.</span></span> <span data-ttu-id="312f2-123">Primeiro, use o `Save-Help` cmdlet para baixar arquivos de ajuda da Internet e salvá-los em uma pasta compartilhada que seja acessível ao sistema não conectado à Internet.</span><span class="sxs-lookup"><span data-stu-id="312f2-123">First, use the `Save-Help`cmdlet to download help files from the internet and save them in a shared folder that is accessible to the system not connected to the internet.</span></span> <span data-ttu-id="312f2-124">Em seguida, use o parâmetro **SourcePath** do `Update-Help` para baixar os arquivos de ajuda atualizados do compartilhado e instale-os no computador.</span><span class="sxs-lookup"><span data-stu-id="312f2-124">Then use the **SourcePath** parameter of `Update-Help` to download the updated help files from the shared and install them on the computer.</span></span>

<span data-ttu-id="312f2-125">Você pode automatizar as atualizações da ajuda adicionando o `Update-Help` cmdlet ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="312f2-125">You can automate help updates by adding the `Update-Help` cmdlet to your PowerShell profile.</span></span> <span data-ttu-id="312f2-126">Por padrão, o `Update-Help` é executado apenas uma vez por dia em cada computador.</span><span class="sxs-lookup"><span data-stu-id="312f2-126">By default, `Update-Help` runs only one time per day on each computer.</span></span> <span data-ttu-id="312f2-127">Para substituir o limite de uma vez por dia, use o parâmetro **Force** .</span><span class="sxs-lookup"><span data-stu-id="312f2-127">To override the once-per-day limit, use the **Force** parameter.</span></span>

<span data-ttu-id="312f2-128">O `Update-Help` cmdlet foi introduzido no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="312f2-128">The `Update-Help` cmdlet was introduced in Windows PowerShell 3.0.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="312f2-129">`Update-Help` requer privilégios administrativos no PowerShell 6,0 e abaixo.</span><span class="sxs-lookup"><span data-stu-id="312f2-129">`Update-Help` requires administrative privileges in PowerShell 6.0 and below.</span></span>
> <span data-ttu-id="312f2-130">O PowerShell 6,1 e superior definem o **escopo** padrão como `CurrentUser` .</span><span class="sxs-lookup"><span data-stu-id="312f2-130">PowerShell 6.1 and above set the default **Scope** to `CurrentUser`.</span></span>
> <span data-ttu-id="312f2-131">Antes do PowerShell 6,1, o parâmetro de **escopo** não estava disponível.</span><span class="sxs-lookup"><span data-stu-id="312f2-131">Prior to PowerShell 6.1, the **Scope** parameter was not available.</span></span>
>
> <span data-ttu-id="312f2-132">Você deve ser um membro do grupo Administradores no computador para atualizar os arquivos de ajuda para os módulos do PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="312f2-132">You must be a member of the Administrators group on the computer to update the help files for the PowerShell Core modules.</span></span>
>
> <span data-ttu-id="312f2-133">Para baixar ou atualizar os arquivos de ajuda para os módulos no diretório de instalação do PowerShell ( `$PSHOME\Modules` ), incluindo os módulos do PowerShell Core, inicie o PowerShell usando a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="312f2-133">To download or update the help files for modules in the PowerShell installation directory (`$PSHOME\Modules`), including the PowerShell Core modules, start PowerShell by using the **Run as administrator** option.</span></span>
> <span data-ttu-id="312f2-134">Por exemplo: `Start-Process pwsh.exe -Verb RunAs`.</span><span class="sxs-lookup"><span data-stu-id="312f2-134">For example: `Start-Process pwsh.exe -Verb RunAs`.</span></span>

## <span data-ttu-id="312f2-135">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="312f2-135">EXAMPLES</span></span>

### <span data-ttu-id="312f2-136">Exemplo 1: atualizar arquivos de ajuda para todos os módulos</span><span class="sxs-lookup"><span data-stu-id="312f2-136">Example 1: Update help files for all modules</span></span>

<span data-ttu-id="312f2-137">O `Update-Help` cmdlet atualiza os arquivos de ajuda para os módulos instalados que dão suporte à ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="312f2-137">The `Update-Help` cmdlet updates help files for installed modules that support Updatable Help.</span></span> <span data-ttu-id="312f2-138">O idioma da cultura da interface do usuário é definido no sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="312f2-138">The user-interface (UI) culture language is set in the operating system.</span></span>

```powershell
Update-Help
```

### <span data-ttu-id="312f2-139">Exemplo 2: atualizar os arquivos de ajuda para os módulos especificados</span><span class="sxs-lookup"><span data-stu-id="312f2-139">Example 2: Update help files for specified modules</span></span>

<span data-ttu-id="312f2-140">O `Update-Help` cmdlet atualiza os arquivos de ajuda somente para nomes de módulo que começam com **Microsoft. PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="312f2-140">The `Update-Help` cmdlet updates help files only for module names that begin with **Microsoft.PowerShell** .</span></span>

```powershell
Update-Help -Module Microsoft.PowerShell*
```

### <span data-ttu-id="312f2-141">Exemplo 3: atualizar arquivos de ajuda para idiomas diferentes</span><span class="sxs-lookup"><span data-stu-id="312f2-141">Example 3: Update help files for different languages</span></span>

<span data-ttu-id="312f2-142">O `Update-Help` cmdlet atualiza os arquivos de ajuda japoneses (ja-JP) e inglês (en-US) para todos os módulos.</span><span class="sxs-lookup"><span data-stu-id="312f2-142">The `Update-Help` cmdlet updates the Japanese (ja-JP) and English (en-US) help files for all modules.</span></span>

<span data-ttu-id="312f2-143">Se um módulo não fornecer arquivos de ajuda para uma cultura de interface do usuário especificada, uma mensagem de erro será exibida para a cultura do módulo e da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="312f2-143">If a module doesn't provide help files for a specified UI culture, an error message is displayed for the module and UI culture.</span></span> <span data-ttu-id="312f2-144">Neste exemplo, a mensagem de erro indica que os arquivos de ajuda do **ja-JP** não foram encontrados para o módulo **Microsoft. PowerShell. Utility** .</span><span class="sxs-lookup"><span data-stu-id="312f2-144">In this example, the error message indicates that the **ja-JP** help files were not found for module **Microsoft.PowerShell.Utility** .</span></span>

```powershell
Update-Help -UICulture ja-JP, en-US
```

```Output
Update-Help : Failed to update Help for the module(s) 'Microsoft.PowerShell.Utility' with UI culture(s) {ja-JP}
No UI culture was found that matches the following pattern: ja-JP.
```

### <span data-ttu-id="312f2-145">Exemplo 4: atualizar arquivos de ajuda em vários computadores a partir de um compartilhamento de arquivos</span><span class="sxs-lookup"><span data-stu-id="312f2-145">Example 4: Update help files on multiple computers from a file share</span></span>

<span data-ttu-id="312f2-146">Neste exemplo, os arquivos de ajuda atualizados são baixados da Internet e salvos em um compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="312f2-146">In this example, updated help files are downloaded from the internet and saved in a file share.</span></span> <span data-ttu-id="312f2-147">São necessárias credenciais de usuário que têm permissões para acessar o compartilhamento de arquivos e instalar atualizações.</span><span class="sxs-lookup"><span data-stu-id="312f2-147">User credentials are needed that have permissions to access the file share and install updates.</span></span> <span data-ttu-id="312f2-148">Quando um compartilhamento de arquivos é usado, é possível atualizar computadores que estão atrás de firewalls ou que não estão conectados à Internet.</span><span class="sxs-lookup"><span data-stu-id="312f2-148">When a file share is used, it's possible to update computers that are behind firewalls or aren't connected to the internet.</span></span>

```powershell
Save-Help -DestinationPath \\Server01\Share\PSHelp -Credential Domain01\Admin01
Invoke-Command -ComputerName (Get-Content Servers.txt) -ScriptBlock {
     Update-Help -SourcePath \\Server01\Share\PSHelp -Credential Domain01\Admin01
}
```

<span data-ttu-id="312f2-149">O `Save-Help` comando baixa os arquivos de ajuda mais recentes para todos os módulos que dão suporte à ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="312f2-149">The `Save-Help` command downloads the newest help files for all modules that support Updatable Help.</span></span>
<span data-ttu-id="312f2-150">O parâmetro **DestinationPath** salva os arquivos no `\\Server01\Share\PSHelp` compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="312f2-150">The **DestinationPath** parameter saves the files in the `\\Server01\Share\PSHelp` file share.</span></span> <span data-ttu-id="312f2-151">O parâmetro **Credential** especifica um usuário que tem permissão para acessar o compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="312f2-151">The **Credential** parameter specifies a user who has permission to access the file share.</span></span>

<span data-ttu-id="312f2-152">O `Invoke-Command` cmdlet executa comandos remotos `Update-Help` em vários computadores.</span><span class="sxs-lookup"><span data-stu-id="312f2-152">The `Invoke-Command` cmdlet runs remote `Update-Help` commands on multiple computers.</span></span> <span data-ttu-id="312f2-153">O parâmetro **ComputerName** Obtém uma lista de computadores remotos do arquivo **Servers.txt** .</span><span class="sxs-lookup"><span data-stu-id="312f2-153">The **ComputerName** parameter gets a list of remote computers from the **Servers.txt** file.</span></span> <span data-ttu-id="312f2-154">O parâmetro **scriptblock** executa o `Update-Help` comando e usa o parâmetro **SourcePath** para especificar o compartilhamento de arquivos que contém os arquivos de ajuda atualizados.</span><span class="sxs-lookup"><span data-stu-id="312f2-154">The **ScriptBlock** parameter runs the `Update-Help` command and uses the **SourcePath** parameter to specify the file share that contains the updated help files.</span></span> <span data-ttu-id="312f2-155">O parâmetro **Credential** especifica um usuário que pode acessar o compartilhamento de arquivos e executar o `Update-Help` comando remoto.</span><span class="sxs-lookup"><span data-stu-id="312f2-155">The **Credential** parameter specifies a user who can access the file share and run the remote `Update-Help` command.</span></span>

### <span data-ttu-id="312f2-156">Exemplo 5: obter uma lista de arquivos de ajuda atualizados</span><span class="sxs-lookup"><span data-stu-id="312f2-156">Example 5: Get a list of updated help files</span></span>

<span data-ttu-id="312f2-157">O `Update-Help` cmdlet atualiza a ajuda para um módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="312f2-157">The `Update-Help` cmdlet updates help for a specified module.</span></span> <span data-ttu-id="312f2-158">O cmdlet usa o parâmetro comum **detalhado** para exibir a lista de arquivos de ajuda que foram atualizados.</span><span class="sxs-lookup"><span data-stu-id="312f2-158">The cmdlet uses the **Verbose** common parameter to display the list of help files that were updated.</span></span> <span data-ttu-id="312f2-159">Você pode usar o modo **detalhado** para exibir a saída de todos os arquivos de ajuda ou arquivos de ajuda para um módulo específico.</span><span class="sxs-lookup"><span data-stu-id="312f2-159">You can use **Verbose** to view output for all help files or help files for a specific module.</span></span>

<span data-ttu-id="312f2-160">Sem o parâmetro **Verbose** , o `Update-Help` não exibe os resultados do comando.</span><span class="sxs-lookup"><span data-stu-id="312f2-160">Without the **Verbose** parameter, `Update-Help` doesn't display the results of the command.</span></span> <span data-ttu-id="312f2-161">A saída de parâmetro **detalhado** é útil para verificar se os arquivos de ajuda foram atualizados ou se a versão mais recente está instalada.</span><span class="sxs-lookup"><span data-stu-id="312f2-161">The **Verbose** parameter output is useful to verify that the help files were updated or if the latest version is installed.</span></span>

```powershell
Update-Help -Module Microsoft.PowerShell.Utility -Verbose
```

### <span data-ttu-id="312f2-162">Exemplo 6: localizar módulos que dão suporte à ajuda atualizável</span><span class="sxs-lookup"><span data-stu-id="312f2-162">Example 6: Find modules that support Updatable Help</span></span>

<span data-ttu-id="312f2-163">Este exemplo lista os módulos que oferecem suporte à ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="312f2-163">This example lists modules that support Updatable Help.</span></span> <span data-ttu-id="312f2-164">O comando usa a propriedade **HelpInfoUri** do módulo para identificar os módulos que oferecem suporte à ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="312f2-164">The command uses the module's **HelpInfoUri** property to identify modules that support Updatable Help.</span></span> <span data-ttu-id="312f2-165">A propriedade **HelpInfoUri** contém um endereço que é redirecionado quando o `Update-Help` cmdlet é executado.</span><span class="sxs-lookup"><span data-stu-id="312f2-165">The **HelpInfoUri** property contains an address that is redirected when the `Update-Help` cmdlet is run.</span></span>

```powershell
Get-Module -ListAvailable | Where-Object -Property HelpInfoUri
```

```output
   Directory: C:\program files\powershell\6\Modules

ModuleType Version    Name                                PSEdition ExportedCommands
---------- -------    ----                                --------- ----------------
Manifest   6.1.0.0    CimCmdlets                          Core      {Get-CimAssociatedInstance... }
Manifest   1.2.2.0    Microsoft.PowerShell.Archive        Desk      {Compress-Archive... }
Manifest   6.1.0.0    Microsoft.PowerShell.Diagnostics    Core      {Get-WinEvent, New-WinEvent}

    Directory: C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules

ModuleType Version    Name                                PSEdition ExportedCommands
---------- -------    ----                                --------- ----------------
Manifest   2.0.1.0    Appx                                Core,Desk {Add-AppxPackage, ... }
Script     1.0.0.0    AssignedAccess                      Core,Desk {Clear-AssignedAccess, ... }
Manifest   1.0.0.0    BitLocker                           Core,Desk {Unlock-BitLocker, ... }
```

### <span data-ttu-id="312f2-166">Exemplo 7: Arquivos de ajuda atualizados do inventário</span><span class="sxs-lookup"><span data-stu-id="312f2-166">Example 7: Inventory updated help files</span></span>

<span data-ttu-id="312f2-167">Neste exemplo, o script `Get-UpdateHelpVersion.ps1` cria um inventário dos arquivos de ajuda atualizáveis para cada módulo e seus números de versão.</span><span class="sxs-lookup"><span data-stu-id="312f2-167">In this example, the script `Get-UpdateHelpVersion.ps1` creates an inventory of the Updatable Help files for each module and their version numbers.</span></span>

<span data-ttu-id="312f2-168">O script identifica os módulos que dão suporte à ajuda atualizável usando a propriedade **HelpInfoUri** dos módulos.</span><span class="sxs-lookup"><span data-stu-id="312f2-168">The script identifies modules that support Updatable Help by using the **HelpInfoUri** property of modules.</span></span> <span data-ttu-id="312f2-169">Para módulos que dão suporte à ajuda atualizável, o script procura e analisa o arquivo de informações de ajuda (\* helpinfo.xml) para localizar o número de versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="312f2-169">For modules that support Updatable Help, the script looks for and parses the help information file (\*helpinfo.xml) to find the latest version number.</span></span>

<span data-ttu-id="312f2-170">O script usa a classe **PSCustomObject** e uma tabela de hash para criar um objeto de saída personalizado.</span><span class="sxs-lookup"><span data-stu-id="312f2-170">The script uses the **PSCustomObject** class and a hash table to create a custom output object.</span></span>

```powershell
# Get-UpdateHelpVersion.ps1
Param(
    [parameter(Mandatory=$False)]
    [String[]]
    $Module
)
$HelpInfoNamespace = @{helpInfo='http://schemas.microsoft.com/powershell/help/2010/05'}

if ($Module) { $Modules = Get-Module $Module -ListAvailable | where {$_.HelpInfoUri} }
else { $Modules = Get-Module -ListAvailable | where {$_.HelpInfoUri} }

foreach ($mModule in $Modules)
{
    $mDir = $mModule.ModuleBase

    if (Test-Path $mdir\*helpinfo.xml)
    {
        $mName=$mModule.Name
        $mNodes = dir $mdir\*helpinfo.xml -ErrorAction SilentlyContinue |
            Select-Xml -Namespace $HelpInfoNamespace -XPath "//helpInfo:UICulture"
        foreach ($mNode in $mNodes)
        {
            $mCulture=$mNode.Node.UICultureName
            $mVer=$mNode.Node.UICultureVersion

            [PSCustomObject]@{"ModuleName"=$mName; "Culture"=$mCulture; "Version"=$mVer}
        }
    }
}
```

```Output
ModuleName                              Culture                                 Version
----------                              -------                                 -------
ActiveDirectory                         en-US                                   3.0.0.0
ADCSAdministration                      en-US                                   3.0.0.0
ADCSDeployment                          en-US                                   3.0.0.0
ADDSDeployment                          en-US                                   3.0.0.0
ADFS                                    en-US                                   3.0.0.0
```

## <span data-ttu-id="312f2-171">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="312f2-171">PARAMETERS</span></span>

### <span data-ttu-id="312f2-172">-Credential</span><span class="sxs-lookup"><span data-stu-id="312f2-172">-Credential</span></span>

<span data-ttu-id="312f2-173">Especifica as credenciais de um usuário que tem permissão para acessar o local do sistema de arquivos especificado por **SourcePath** .</span><span class="sxs-lookup"><span data-stu-id="312f2-173">Specifies credentials of a user who has permission to access the file system location specified by **SourcePath** .</span></span> <span data-ttu-id="312f2-174">Esse parâmetro é válido somente quando o parâmetro **SourcePath** ou **LiteralPath** é usado no comando.</span><span class="sxs-lookup"><span data-stu-id="312f2-174">This parameter is valid only when the **SourcePath** or **LiteralPath** parameter is used in the command.</span></span>

<span data-ttu-id="312f2-175">O parâmetro **Credential** permite que você execute `Update-Help` comandos com o parâmetro **SourcePath** em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="312f2-175">The **Credential** parameter enables you to run `Update-Help` commands with the **SourcePath** parameter on remote computers.</span></span> <span data-ttu-id="312f2-176">Ao fornecer credenciais explícitas, você pode executar o comando em um computador remoto e acessar um compartilhamento de arquivos em um terceiro computador sem encontrar um erro de acesso negado ou usar a autenticação CredSSP para delegar credenciais.</span><span class="sxs-lookup"><span data-stu-id="312f2-176">By providing explicit credentials, you can run the command on a remote computer and access a file share on a third computer without encountering an access denied error or using CredSSP authentication to delegate credentials.</span></span>

<span data-ttu-id="312f2-177">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="312f2-177">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="312f2-178">Se você digitar um nome de usuário, você será solicitado a inserir a senha.</span><span class="sxs-lookup"><span data-stu-id="312f2-178">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="312f2-179">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="312f2-179">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="312f2-180">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="312f2-180">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="312f2-181">-Force</span><span class="sxs-lookup"><span data-stu-id="312f2-181">-Force</span></span>

<span data-ttu-id="312f2-182">Indica que esse cmdlet não segue a limitação de uma vez por dia, ignora a verificação de versão e baixa os arquivos que excedem o limite de 1 GB.</span><span class="sxs-lookup"><span data-stu-id="312f2-182">Indicates that this cmdlet doesn't follow the once-per-day limitation, skips version checking, and downloads files that exceed the 1 GB limit.</span></span>

<span data-ttu-id="312f2-183">Sem esse parâmetro, o `Update-Help` é executado apenas uma vez em cada período de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="312f2-183">Without this parameter, `Update-Help` runs only once in each 24-hour period.</span></span> <span data-ttu-id="312f2-184">Os downloads são limitados a 1 GB de conteúdo descompactado por módulo e os arquivos de ajuda são instalados apenas quando são mais recentes do que os arquivos existentes no computador.</span><span class="sxs-lookup"><span data-stu-id="312f2-184">Downloads are limited to 1 GB of uncompressed content per module and help files are only installed when they're newer than the existing files on the computer.</span></span>

<span data-ttu-id="312f2-185">O limite de uma vez por dia protege os servidores que hospedam os arquivos de ajuda e torna prático para você adicionar um `Update-Help` comando ao seu perfil do PowerShell sem incorrer no custo de recursos de conexões ou downloads repetidos.</span><span class="sxs-lookup"><span data-stu-id="312f2-185">The once-per-day limit protects the servers that host the help files and makes it practical for you to add an `Update-Help` command to your PowerShell profile without incurring the resource cost of repeated connections or downloads.</span></span>

<span data-ttu-id="312f2-186">Para atualizar a Ajuda para um módulo em várias culturas de interface do usuário sem o parâmetro **Force** , incluem todas as culturas de interface do usuário no mesmo comando, como:</span><span class="sxs-lookup"><span data-stu-id="312f2-186">To update help for a module in multiple UI cultures without the **Force** parameter, include all UI cultures in the same command, such as:</span></span>

`Update-Help -Module PSScheduledJobs -UICulture en-US, fr-FR, pt-BR`

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

### <span data-ttu-id="312f2-187">-FullyQualifiedModule</span><span class="sxs-lookup"><span data-stu-id="312f2-187">-FullyQualifiedModule</span></span>

<span data-ttu-id="312f2-188">Especifica os módulos com nomes que são especificados na forma de objetos **ModuleSpecification** .</span><span class="sxs-lookup"><span data-stu-id="312f2-188">Specifies modules with names that are specified in the form of **ModuleSpecification** objects.</span></span>
<span data-ttu-id="312f2-189">Esses módulos são descritos na seção comentários do [Construtor ModuleSpecification (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span><span class="sxs-lookup"><span data-stu-id="312f2-189">These modules are described in the Remarks section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>

<span data-ttu-id="312f2-190">Por exemplo, o parâmetro **FullyQualifiedModule** aceita um nome de módulo que é especificado no formato:</span><span class="sxs-lookup"><span data-stu-id="312f2-190">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in the format:</span></span>

`@{ModuleName = "modulename"; ModuleVersion = "version_number"}`

<span data-ttu-id="312f2-191">ou</span><span class="sxs-lookup"><span data-stu-id="312f2-191">or</span></span>

`@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}.`

<span data-ttu-id="312f2-192">**ModuleName** e **ModuleVersion** são obrigatórios, mas **Guid** é opcional.</span><span class="sxs-lookup"><span data-stu-id="312f2-192">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span>

<span data-ttu-id="312f2-193">Você não pode especificar o parâmetro **FullyQualifiedModule** no mesmo comando que um parâmetro de **módulo** .</span><span class="sxs-lookup"><span data-stu-id="312f2-193">You can't specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="312f2-194">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="312f2-194">-LiteralPath</span></span>

<span data-ttu-id="312f2-195">Especifica a pasta para arquivos de ajuda atualizados em vez de baixá-los da Internet.</span><span class="sxs-lookup"><span data-stu-id="312f2-195">Specifies the folder for updated help files instead of downloading them from the internet.</span></span> <span data-ttu-id="312f2-196">Use esse parâmetro ou **SourcePath** se você tiver usado o `Save-Help` cmdlet para baixar arquivos de ajuda para um diretório.</span><span class="sxs-lookup"><span data-stu-id="312f2-196">Use this parameter or **SourcePath** if you've used the `Save-Help` cmdlet to download help files to a directory.</span></span>

<span data-ttu-id="312f2-197">Você pode canalizar um objeto de diretório, como dos `Get-Item` `Get-ChildItem` cmdlets ou, para `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="312f2-197">You can pipeline a directory object, such as from the `Get-Item` or `Get-ChildItem` cmdlets, to `Update-Help`.</span></span>

<span data-ttu-id="312f2-198">Ao contrário do valor de **SourcePath** , o valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="312f2-198">Unlike the value of **SourcePath** , the value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="312f2-199">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="312f2-199">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="312f2-200">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="312f2-200">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="312f2-201">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="312f2-201">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="312f2-202">-Módulo</span><span class="sxs-lookup"><span data-stu-id="312f2-202">-Module</span></span>

<span data-ttu-id="312f2-203">Atualizações de Ajuda para os módulos especificados.</span><span class="sxs-lookup"><span data-stu-id="312f2-203">Updates help for the specified modules.</span></span> <span data-ttu-id="312f2-204">Insira um ou mais nomes de módulo ou padrões de nome em uma lista separada por vírgulas ou especifique um arquivo que liste um nome de módulo em cada linha.</span><span class="sxs-lookup"><span data-stu-id="312f2-204">Enter one or more module names or name patterns in a comma-separated list, or specify a file that lists one module name on each line.</span></span> <span data-ttu-id="312f2-205">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="312f2-205">Wildcard characters are permitted.</span></span> <span data-ttu-id="312f2-206">Você pode canalizar módulos do `Get-Module` cmdlet para o `Update-Help` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="312f2-206">You can pipeline modules from the `Get-Module` cmdlet to the `Update-Help` cmdlet.</span></span>

<span data-ttu-id="312f2-207">Os módulos que você especificar devem ser instalados no computador, mas não precisam ser importados para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="312f2-207">The modules that you specify must be installed on the computer, but they don't have to be imported into the current session.</span></span> <span data-ttu-id="312f2-208">Você pode especificar qualquer módulo na sessão ou qualquer módulo que esteja instalado em um local listado na variável de `$env:PSModulePath` ambiente.</span><span class="sxs-lookup"><span data-stu-id="312f2-208">You can specify any module in the session or any module that is installed in a location listed in the `$env:PSModulePath` environment variable.</span></span>

<span data-ttu-id="312f2-209">Um valor de `*` (All) tenta atualizar a ajuda para todos os módulos instalados no computador.</span><span class="sxs-lookup"><span data-stu-id="312f2-209">A value of `*` (all) attempts to update help for all modules that are installed on the computer.</span></span>
<span data-ttu-id="312f2-210">Módulos que não dão suporte à ajuda atualizável estão incluídos.</span><span class="sxs-lookup"><span data-stu-id="312f2-210">Modules that don't support Updatable Help are included.</span></span> <span data-ttu-id="312f2-211">Esse valor pode gerar erros quando o comando encontra módulos que não dão suporte à ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="312f2-211">This value might generate errors when the command encounters modules that don't support Updatable Help.</span></span> <span data-ttu-id="312f2-212">Em vez disso, execute `Update-Help` sem parâmetros.</span><span class="sxs-lookup"><span data-stu-id="312f2-212">Instead, run `Update-Help` without parameters.</span></span>

<span data-ttu-id="312f2-213">O parâmetro **Module** do `Update-Help` cmdlet não aceita o caminho completo de um arquivo de módulo ou arquivo de manifesto de módulo.</span><span class="sxs-lookup"><span data-stu-id="312f2-213">The **Module** parameter of the `Update-Help` cmdlet doesn't accept the full path of a module file or module manifest file.</span></span> <span data-ttu-id="312f2-214">Para atualizar a ajuda para um módulo que não está em um `$env:PSModulePath` local, importe o módulo para a sessão atual antes de executar o `Update-Help` comando.</span><span class="sxs-lookup"><span data-stu-id="312f2-214">To update help for a module that isn't in a `$env:PSModulePath` location, import the module into the current session before you run the `Update-Help` command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="312f2-215">-Recurse</span><span class="sxs-lookup"><span data-stu-id="312f2-215">-Recurse</span></span>

<span data-ttu-id="312f2-216">Executa uma pesquisa recursiva de arquivos de ajuda no diretório especificado.</span><span class="sxs-lookup"><span data-stu-id="312f2-216">Performs a recursive search for help files in the specified directory.</span></span> <span data-ttu-id="312f2-217">Esse parâmetro é válido somente quando o comando usa o parâmetro **SourcePath** .</span><span class="sxs-lookup"><span data-stu-id="312f2-217">This parameter is valid only when the command uses the **SourcePath** parameter.</span></span>

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

### <span data-ttu-id="312f2-218">-Escopo</span><span class="sxs-lookup"><span data-stu-id="312f2-218">-Scope</span></span>

<span data-ttu-id="312f2-219">Especifica o escopo do sistema em que a ajuda é atualizada.</span><span class="sxs-lookup"><span data-stu-id="312f2-219">Specifies the system scope where help is updated.</span></span> <span data-ttu-id="312f2-220">As atualizações no escopo **AllUsers** exigem privilégios administrativos em sistemas Windows.</span><span class="sxs-lookup"><span data-stu-id="312f2-220">Updates at the **AllUsers** scope require administrative privileges on Windows systems.</span></span> <span data-ttu-id="312f2-221">O `-Scope` parâmetro foi introduzido na versão 6,1 do PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="312f2-221">The `-Scope` parameter was introduced in PowerShell Core version 6.1.</span></span>

<span data-ttu-id="312f2-222">**CurrentUser** é o escopo padrão para arquivos de ajuda no PowerShell 6,1 e superior.</span><span class="sxs-lookup"><span data-stu-id="312f2-222">**CurrentUser** is the default scope for help files in PowerShell 6.1 and above.</span></span> <span data-ttu-id="312f2-223">**AllUsers** pode ser especificado para instalar ou atualizar a ajuda para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="312f2-223">**AllUsers** can be specified to install or update help for all users.</span></span> <span data-ttu-id="312f2-224">Em privilégios de sistemas UNIX `sudo` são necessários para atualizar a ajuda para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="312f2-224">On Unix systems `sudo` privileges are required to update help for all users.</span></span> <span data-ttu-id="312f2-225">Por exemplo: `sudo pwsh -c Update-Help`</span><span class="sxs-lookup"><span data-stu-id="312f2-225">For example: `sudo pwsh -c Update-Help`</span></span>

<span data-ttu-id="312f2-226">Os valores aceitáveis são:</span><span class="sxs-lookup"><span data-stu-id="312f2-226">The acceptable values are:</span></span>

- <span data-ttu-id="312f2-227">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="312f2-227">CurrentUser</span></span>
- <span data-ttu-id="312f2-228">AllUsers</span><span class="sxs-lookup"><span data-stu-id="312f2-228">AllUsers</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.UpdateHelpScope
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: CurrentUser
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="312f2-229">-SourcePath</span><span class="sxs-lookup"><span data-stu-id="312f2-229">-SourcePath</span></span>

<span data-ttu-id="312f2-230">Especifica uma pasta do sistema de arquivos em que o `Update-Help` Obtém arquivos de ajuda atualizados, em vez de baixá-los da Internet.</span><span class="sxs-lookup"><span data-stu-id="312f2-230">Specifies a file system folder where `Update-Help` gets updated help files, instead of downloading them from the internet.</span></span> <span data-ttu-id="312f2-231">Insira o caminho de uma pasta.</span><span class="sxs-lookup"><span data-stu-id="312f2-231">Enter the path of a folder.</span></span> <span data-ttu-id="312f2-232">Não especifique um nome de arquivo ou uma extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="312f2-232">Don't specify a file name or file name extension.</span></span> <span data-ttu-id="312f2-233">Você pode canalizar uma pasta, como uma dos `Get-Item` `Get-ChildItem` cmdlets ou, para `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="312f2-233">You can pipeline a folder, such as one from the `Get-Item` or `Get-ChildItem` cmdlets, to `Update-Help`.</span></span>

<span data-ttu-id="312f2-234">Por padrão, o `Update-Help` baixa arquivos de ajuda atualizados da Internet.</span><span class="sxs-lookup"><span data-stu-id="312f2-234">By default, `Update-Help` downloads updated help files from the internet.</span></span> <span data-ttu-id="312f2-235">Use **SourcePath** quando você tiver usado o `Save-Help` cmdlet para baixar arquivos de ajuda atualizados para um diretório.</span><span class="sxs-lookup"><span data-stu-id="312f2-235">Use **SourcePath** when you've used the `Save-Help` cmdlet to download updated help files to a directory.</span></span>

<span data-ttu-id="312f2-236">Para especificar um valor padrão para **SourcePath** , vá para **política de grupo** , **configuração do computador** e **defina o caminho de origem padrão para Update-Help** .</span><span class="sxs-lookup"><span data-stu-id="312f2-236">To specify a default value for **SourcePath** , go to **Group Policy** , **Computer Configuration** , and **Set the default source path for Update-Help** .</span></span> <span data-ttu-id="312f2-237">Essa configuração de Política de Grupo impede que os usuários usem `Update-Help` o para baixar arquivos de ajuda da Internet.</span><span class="sxs-lookup"><span data-stu-id="312f2-237">This Group Policy setting prevents users from using `Update-Help` to download help files from the internet.</span></span>
<span data-ttu-id="312f2-238">Confira mais informações em [about_Group_Policy_Settings](./About/about_Group_Policy_Settings.md).</span><span class="sxs-lookup"><span data-stu-id="312f2-238">For more information, see [about_Group_Policy_Settings](./About/about_Group_Policy_Settings.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases: Path

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="312f2-239">-UICulture</span><span class="sxs-lookup"><span data-stu-id="312f2-239">-UICulture</span></span>

<span data-ttu-id="312f2-240">Especifica os valores de cultura da interface do usuário que o `Update-Help` usa para obter arquivos de ajuda atualizados.</span><span class="sxs-lookup"><span data-stu-id="312f2-240">Specifies UI culture values that `Update-Help` uses to get updated help files.</span></span> <span data-ttu-id="312f2-241">Insira um ou mais códigos de idioma, como **es-es** , uma variável que contém objetos de cultura ou um comando que obtém objetos de cultura, como um `Get-Culture` `Get-UICulture` comando ou.</span><span class="sxs-lookup"><span data-stu-id="312f2-241">Enter one or more language codes, such as **es-ES** , a variable that contains culture objects, or a command that gets culture objects, such as a `Get-Culture` or `Get-UICulture` command.</span></span> <span data-ttu-id="312f2-242">Os caracteres curinga não são permitidos e você não pode enviar um código de idioma parcial, como **de** .</span><span class="sxs-lookup"><span data-stu-id="312f2-242">Wildcard characters aren't permitted and you can't submit a partial language code, such as **de** .</span></span>

<span data-ttu-id="312f2-243">Por padrão, `Update-Help` o Obtém os arquivos de ajuda na cultura da interface do usuário definida para o sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="312f2-243">By default, `Update-Help` gets help files in the UI culture set for the operating system.</span></span> <span data-ttu-id="312f2-244">Se você especificar o parâmetro **UICulture** , o `Update-Help` procurará ajuda apenas para a cultura da interface do usuário especificada.</span><span class="sxs-lookup"><span data-stu-id="312f2-244">If you specify the **UICulture** parameter, `Update-Help` looks for help only for the specified UI culture.</span></span>

> [!NOTE]
> <span data-ttu-id="312f2-245">O Ubuntu 18, 4 alterou a configuração de localidade padrão para `C.UTF.8` , que não é uma cultura de interface do usuário reconhecida.</span><span class="sxs-lookup"><span data-stu-id="312f2-245">Ubuntu 18.04 changed the default locale setting to `C.UTF.8`, which is not a recognized UI culture.</span></span> <span data-ttu-id="312f2-246">`Update-Help` falha silenciosa ao baixar a ajuda, a menos que você use esse parâmetro com uma localidade com suporte como `en-US` .</span><span class="sxs-lookup"><span data-stu-id="312f2-246">`Update-Help` silently fails to download help unless you use this parameter with a supported locale like `en-US`.</span></span> <span data-ttu-id="312f2-247">Isso pode ocorrer em qualquer plataforma que usa um valor sem suporte.</span><span class="sxs-lookup"><span data-stu-id="312f2-247">This could occur on any platform that uses an unsupported value.</span></span>

<span data-ttu-id="312f2-248">Os comandos que utilizam o parâmetro **UICulture** têm êxito somente quando o módulo fornece arquivos de ajuda para a cultura da interface do usuário especificado.</span><span class="sxs-lookup"><span data-stu-id="312f2-248">Commands that use the **UICulture** parameter succeed only when the module provides help files for the specified UI culture.</span></span> <span data-ttu-id="312f2-249">Se o comando falhar porque a cultura da interface do usuário especificada não tem suporte, será exibida uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="312f2-249">If the command fails because the specified UI culture isn't supported, an error message is displayed.</span></span>

```yaml
Type: System.Globalization.CultureInfo[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="312f2-250">-UseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="312f2-250">-UseDefaultCredentials</span></span>

<span data-ttu-id="312f2-251">Indica que `Update-Help` o executa o comando, incluindo o download da Internet, usando as credenciais do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="312f2-251">Indicates that `Update-Help` runs the command, including the internet download, by using the credentials of the current user.</span></span> <span data-ttu-id="312f2-252">Por padrão, o comando é executado sem credenciais explícitas.</span><span class="sxs-lookup"><span data-stu-id="312f2-252">By default, the command runs without explicit credentials.</span></span>

<span data-ttu-id="312f2-253">Esse parâmetro é eficaz somente quando o download da Web usa o NTLM (NT LAN Manager), Negotiate ou autenticação baseada em Kerberos.</span><span class="sxs-lookup"><span data-stu-id="312f2-253">This parameter is effective only when the web download uses NT LAN Manager (NTLM), negotiate, or Kerberos-based authentication.</span></span>

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

### <span data-ttu-id="312f2-254">-Confirm</span><span class="sxs-lookup"><span data-stu-id="312f2-254">-Confirm</span></span>

<span data-ttu-id="312f2-255">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="312f2-255">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="312f2-256">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="312f2-256">-WhatIf</span></span>

<span data-ttu-id="312f2-257">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="312f2-257">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="312f2-258">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="312f2-258">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="312f2-259">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="312f2-259">CommonParameters</span></span>

<span data-ttu-id="312f2-260">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="312f2-260">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="312f2-261">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="312f2-261">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="312f2-262">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="312f2-262">INPUTS</span></span>

### <span data-ttu-id="312f2-263">System. IO. DirectoryInfo</span><span class="sxs-lookup"><span data-stu-id="312f2-263">System.IO.DirectoryInfo</span></span>

<span data-ttu-id="312f2-264">É possível canalizar um caminho de diretório para `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="312f2-264">You can pipe a directory path to `Update-Help`.</span></span>

### <span data-ttu-id="312f2-265">System. Management. Automation. PSModuleInfo</span><span class="sxs-lookup"><span data-stu-id="312f2-265">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="312f2-266">É possível canalizar um objeto de módulo do `Get-Module` cmdlet para `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="312f2-266">You can pipe a module object from the `Get-Module` cmdlet to `Update-Help`.</span></span>

## <span data-ttu-id="312f2-267">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="312f2-267">OUTPUTS</span></span>

### <span data-ttu-id="312f2-268">Nenhum</span><span class="sxs-lookup"><span data-stu-id="312f2-268">None</span></span>

<span data-ttu-id="312f2-269">`Update-Help` não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="312f2-269">`Update-Help` doesn't generate any output.</span></span>

## <span data-ttu-id="312f2-270">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="312f2-270">NOTES</span></span>

<span data-ttu-id="312f2-271">Para atualizar a ajuda para os módulos do PowerShell Core, que contêm os comandos instalados com o PowerShell ou qualquer módulo no `$PSHOME\Modules` diretório, inicie o PowerShell com a opção de **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="312f2-271">To update help for the PowerShell Core modules, that contain the commands that are installed with PowerShell, or any module in the `$PSHOME\Modules` directory, start PowerShell with the option to **Run as administrator** .</span></span>

<span data-ttu-id="312f2-272">Somente os membros do grupo Administradores no computador podem atualizar a ajuda para os módulos do PowerShell Core, os comandos que são instalados junto com o PowerShell e para os módulos na `$PSHOME\Modules` pasta.</span><span class="sxs-lookup"><span data-stu-id="312f2-272">Only members of the Administrators group on the computer can update help for the PowerShell Core modules, the commands that are installed together with PowerShell, and for modules in the `$PSHOME\Modules` folder.</span></span> <span data-ttu-id="312f2-273">Se você não tiver permissão para atualizar os arquivos de ajuda, poderá ler os arquivos de ajuda online.</span><span class="sxs-lookup"><span data-stu-id="312f2-273">If you don't have permission to update help files, you can read the help files online.</span></span> <span data-ttu-id="312f2-274">Por exemplo, `Get-Help Update-Help -Online`.</span><span class="sxs-lookup"><span data-stu-id="312f2-274">For example, `Get-Help Update-Help -Online`.</span></span>

<span data-ttu-id="312f2-275">Os módulos são a menor unidade da ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="312f2-275">Modules are the smallest unit of updatable help.</span></span> <span data-ttu-id="312f2-276">Você não pode atualizar a ajuda para um cmdlet específico.</span><span class="sxs-lookup"><span data-stu-id="312f2-276">You can't update help for a particular cmdlet.</span></span> <span data-ttu-id="312f2-277">Para localizar o módulo que contém um cmdlet específico, use a propriedade **ModuleName** do `Get-Command` cmdlet, por exemplo, `(Get-Command Update-Help).ModuleName` .</span><span class="sxs-lookup"><span data-stu-id="312f2-277">To find the module that contains a particular cmdlet, use the **ModuleName** property of the `Get-Command` cmdlet, for example, `(Get-Command Update-Help).ModuleName`.</span></span>

<span data-ttu-id="312f2-278">Como os arquivos de ajuda são instalados no diretório do módulo, o `Update-Help` cmdlet pode instalar o arquivo de ajuda atualizado somente para os módulos que estão instalados no computador.</span><span class="sxs-lookup"><span data-stu-id="312f2-278">Because help files are installed in the module directory, the `Update-Help` cmdlet can install updated help file only for modules that are installed on the computer.</span></span> <span data-ttu-id="312f2-279">No entanto, o `Save-Help` cmdlet pode salvar ajuda para módulos que não estão instalados no computador.</span><span class="sxs-lookup"><span data-stu-id="312f2-279">However, the `Save-Help` cmdlet can save help for modules that aren't installed on the computer.</span></span>

<span data-ttu-id="312f2-280">Se `Update-Help` o não conseguir encontrar arquivos de ajuda atualizados para um módulo ou não conseguir encontrar ajuda atualizada no idioma especificado, ele continuará silenciosamente sem exibir uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="312f2-280">If `Update-Help` can't find updated help files for a module, or can't find updated help in the specified language, it continues silently without displaying an error message.</span></span> <span data-ttu-id="312f2-281">Para ver os detalhes de status e o andamento, use o parâmetro **Verbose** .</span><span class="sxs-lookup"><span data-stu-id="312f2-281">To see status and progress details, use the **Verbose** parameter.</span></span>

<span data-ttu-id="312f2-282">O `Update-Help` cmdlet foi introduzido no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="312f2-282">The `Update-Help` cmdlet was introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="312f2-283">Ele não funciona em versões anteriores do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="312f2-283">It doesn't work in earlier versions of PowerShell.</span></span> <span data-ttu-id="312f2-284">Em computadores que têm o Windows PowerShell 2,0 e o Windows PowerShell 3,0, use o `Update-Help` cmdlet em uma sessão do Windows powershell 3,0 para baixar e atualizar os arquivos de ajuda.</span><span class="sxs-lookup"><span data-stu-id="312f2-284">On computers that have both Windows PowerShell 2.0 and Windows PowerShell 3.0, use the `Update-Help` cmdlet in a Windows PowerShell 3.0 session to download and update help files.</span></span> <span data-ttu-id="312f2-285">Os arquivos de ajuda estão disponíveis para o Windows PowerShell 2,0 e o Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="312f2-285">The help files are available to both Windows PowerShell 2.0 and Windows PowerShell 3.0.</span></span>

<span data-ttu-id="312f2-286">Os `Update-Help` `Save-Help` cmdlets e usam as seguintes portas para baixar arquivos de ajuda: porta 80 para http e porta 443 para https.</span><span class="sxs-lookup"><span data-stu-id="312f2-286">The `Update-Help` and `Save-Help` cmdlets use the following ports to download help files: Port 80 for HTTP and port 443 for HTTPS.</span></span>

<span data-ttu-id="312f2-287">`Update-Help` dá suporte a todos os módulos e os snap-ins do PowerShell Core. Ele não dá suporte a nenhum outro snap-ins.</span><span class="sxs-lookup"><span data-stu-id="312f2-287">`Update-Help` supports all modules and the PowerShell Core snap-ins. It doesn't support any other snap-ins.</span></span>

<span data-ttu-id="312f2-288">Para atualizar a ajuda de um módulo em um local que não está listado na `$env:PSModulePath` variável de ambiente, importe o módulo para a sessão atual e, em seguida, execute um `Update-Help` comando.</span><span class="sxs-lookup"><span data-stu-id="312f2-288">To update help for a module in a location that isn't listed in the `$env:PSModulePath` environment variable, import the module into the current session and then run an `Update-Help` command.</span></span> <span data-ttu-id="312f2-289">Execute `Update-Help` sem parâmetros ou use o parâmetro **Module** para especificar o nome do módulo.</span><span class="sxs-lookup"><span data-stu-id="312f2-289">Run `Update-Help` without parameters or use the **Module** parameter to specify the module name.</span></span> <span data-ttu-id="312f2-290">O parâmetro **Module** dos `Update-Help` `Save-Help` cmdlets e não aceita o caminho completo de um arquivo de módulo ou arquivo de manifesto de módulo.</span><span class="sxs-lookup"><span data-stu-id="312f2-290">The **Module** parameter of the `Update-Help` and `Save-Help` cmdlets doesn't accept the full path of a module file or module manifest file.</span></span>

<span data-ttu-id="312f2-291">Qualquer módulo pode dar suporte a Ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="312f2-291">Any module can support Updatable Help.</span></span> <span data-ttu-id="312f2-292">Para obter instruções para dar suporte à ajuda atualizável nos módulos que você cria, consulte [dando suporte à ajuda atualizável](/powershell/scripting/developer/module/supporting-updatable-help).</span><span class="sxs-lookup"><span data-stu-id="312f2-292">For instructions for supporting Updatable Help in the modules that you author, see [Supporting Updatable Help](/powershell/scripting/developer/module/supporting-updatable-help).</span></span>

<span data-ttu-id="312f2-293">`Update-Help` `Save-Help` Não há suporte para os cmdlets e no ambiente de pré-instalação do Windows (Windows PE).</span><span class="sxs-lookup"><span data-stu-id="312f2-293">The `Update-Help` and `Save-Help` cmdlets are not supported on Windows Preinstallation Environment (Windows PE).</span></span>

## <span data-ttu-id="312f2-294">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="312f2-294">RELATED LINKS</span></span>

[<span data-ttu-id="312f2-295">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="312f2-295">Get-Culture</span></span>](../Microsoft.PowerShell.Utility/Get-Culture.md)

[<span data-ttu-id="312f2-296">Get-Help</span><span class="sxs-lookup"><span data-stu-id="312f2-296">Get-Help</span></span>](Get-Help.md)

[<span data-ttu-id="312f2-297">Get-Module</span><span class="sxs-lookup"><span data-stu-id="312f2-297">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="312f2-298">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="312f2-298">Get-UICulture</span></span>](../Microsoft.PowerShell.Utility/Get-UICulture.md)

[<span data-ttu-id="312f2-299">Start-Job</span><span class="sxs-lookup"><span data-stu-id="312f2-299">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="312f2-300">Save-Help</span><span class="sxs-lookup"><span data-stu-id="312f2-300">Save-Help</span></span>](Save-Help.md)
