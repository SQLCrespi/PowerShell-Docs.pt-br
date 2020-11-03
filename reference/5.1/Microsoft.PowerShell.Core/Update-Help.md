---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/16/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/update-help?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Help
ms.openlocfilehash: 4ef0865e81e01746fed77b73e265e68086a7a9e1
ms.sourcegitcommit: d3f78120bdc9096c72aa0dfdbdd91efaf254c738
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "93195114"
---
# <span data-ttu-id="e95ae-103">Update-Help</span><span class="sxs-lookup"><span data-stu-id="e95ae-103">Update-Help</span></span>

## <span data-ttu-id="e95ae-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="e95ae-104">SYNOPSIS</span></span>
<span data-ttu-id="e95ae-105">Baixa e instala os arquivos de ajuda mais recentes em seu computador.</span><span class="sxs-lookup"><span data-stu-id="e95ae-105">Downloads and installs the newest help files on your computer.</span></span>

## <span data-ttu-id="e95ae-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e95ae-106">SYNTAX</span></span>

### <span data-ttu-id="e95ae-107">Caminho (padrão)</span><span class="sxs-lookup"><span data-stu-id="e95ae-107">Path (Default)</span></span>

```
Update-Help [[-Module] <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [[-SourcePath] <String[]>] [-Recurse] [[-UICulture] <CultureInfo[]>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e95ae-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="e95ae-108">LiteralPath</span></span>

```
Update-Help [[-Module] <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [-LiteralPath <String[]>] [-Recurse] [[-UICulture] <CultureInfo[]>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e95ae-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e95ae-109">DESCRIPTION</span></span>

<span data-ttu-id="e95ae-110">O `Update-Help` cmdlet baixa os arquivos de ajuda mais recentes para os módulos do PowerShell e os instala em seu computador.</span><span class="sxs-lookup"><span data-stu-id="e95ae-110">The `Update-Help` cmdlet downloads the newest help files for PowerShell modules and installs them on your computer.</span></span> <span data-ttu-id="e95ae-111">Você não precisa reiniciar o PowerShell para que a alteração seja efetiva.</span><span class="sxs-lookup"><span data-stu-id="e95ae-111">You need not restart PowerShell to make the change effective.</span></span> <span data-ttu-id="e95ae-112">Você pode usar o `Get-Help` cmdlet para exibir os novos arquivos de ajuda imediatamente.</span><span class="sxs-lookup"><span data-stu-id="e95ae-112">You can use the `Get-Help` cmdlet to view the new help files immediately.</span></span>

<span data-ttu-id="e95ae-113">`Update-Help` verifica a versão dos arquivos de ajuda em seu computador.</span><span class="sxs-lookup"><span data-stu-id="e95ae-113">`Update-Help` checks the version of the help files on your computer.</span></span> <span data-ttu-id="e95ae-114">Se você não tiver arquivos de ajuda para um módulo ou se os arquivos de ajuda estiverem desatualizados, `Update-Help` o baixará os arquivos de ajuda mais recentes.</span><span class="sxs-lookup"><span data-stu-id="e95ae-114">If you don't have help files for a module or if your help files are outdated, `Update-Help` downloads the newest help files.</span></span> <span data-ttu-id="e95ae-115">Os arquivos de ajuda podem ser baixados e instalados da Internet ou de um compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="e95ae-115">The help files can be downloaded and installed from the internet or a file share.</span></span>

<span data-ttu-id="e95ae-116">Sem parâmetros, `Update-Help` o atualiza os arquivos de ajuda para os módulos na sessão e para todos os módulos instalados que dão suporte à ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="e95ae-116">Without parameters, `Update-Help` updates the help files for modules in the session and for all installed modules that support Updatable Help.</span></span> <span data-ttu-id="e95ae-117">Os módulos instalados, mas não carregados na sessão atual, estão incluídos.</span><span class="sxs-lookup"><span data-stu-id="e95ae-117">Modules that are installed but not loaded in the current session are included.</span></span> <span data-ttu-id="e95ae-118">Os módulos do PowerShell são armazenados em um local listado na `$env:PSModulePath` variável de ambiente.</span><span class="sxs-lookup"><span data-stu-id="e95ae-118">PowerShell modules are stored in a location listed in the `$env:PSModulePath` environment variable.</span></span> <span data-ttu-id="e95ae-119">Para obter mais informações, consulte [about_Updatable_Help](./About/about_Updatable_Help.md).</span><span class="sxs-lookup"><span data-stu-id="e95ae-119">For more information, see [about_Updatable_Help](./About/about_Updatable_Help.md).</span></span>

<span data-ttu-id="e95ae-120">Você pode usar o parâmetro **Module** para atualizar os arquivos de ajuda de um módulo específico.</span><span class="sxs-lookup"><span data-stu-id="e95ae-120">You can use the **Module** parameter to update help files for a particular module.</span></span> <span data-ttu-id="e95ae-121">Use o parâmetro **UICulture** para baixar arquivos de ajuda em vários idiomas e localidades.</span><span class="sxs-lookup"><span data-stu-id="e95ae-121">Use the **UICulture** parameter to download help files in multiple languages and locales.</span></span>

<span data-ttu-id="e95ae-122">Você também pode usar `Update-Help` o em computadores que não estão conectados à Internet.</span><span class="sxs-lookup"><span data-stu-id="e95ae-122">You can also use `Update-Help` on computers that are not connected to the internet.</span></span> <span data-ttu-id="e95ae-123">Primeiro, use o `Save-Help` cmdlet para baixar arquivos de ajuda da Internet e salvá-los em uma pasta compartilhada que seja acessível ao sistema não conectado à Internet.</span><span class="sxs-lookup"><span data-stu-id="e95ae-123">First, use the `Save-Help`cmdlet to download help files from the internet and save them in a shared folder that is accessible to the system not connected to the internet.</span></span> <span data-ttu-id="e95ae-124">Em seguida, use o parâmetro **SourcePath** do `Update-Help` para baixar os arquivos de ajuda atualizados do compartilhado e instale-os no computador.</span><span class="sxs-lookup"><span data-stu-id="e95ae-124">Then use the **SourcePath** parameter of `Update-Help` to download the updated help files from the shared and install them on the computer.</span></span>

<span data-ttu-id="e95ae-125">Você pode automatizar as atualizações da ajuda adicionando o `Update-Help` cmdlet ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e95ae-125">You can automate help updates by adding the `Update-Help` cmdlet to your PowerShell profile.</span></span> <span data-ttu-id="e95ae-126">Por padrão, o `Update-Help` é executado apenas uma vez por dia em cada computador.</span><span class="sxs-lookup"><span data-stu-id="e95ae-126">By default, `Update-Help` runs only one time per day on each computer.</span></span> <span data-ttu-id="e95ae-127">Para substituir o limite de uma vez por dia, use o parâmetro **Force** .</span><span class="sxs-lookup"><span data-stu-id="e95ae-127">To override the once-per-day limit, use the **Force** parameter.</span></span>

<span data-ttu-id="e95ae-128">O `Update-Help` cmdlet foi introduzido no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="e95ae-128">The `Update-Help` cmdlet was introduced in Windows PowerShell 3.0.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e95ae-129">`Update-Help` requer privilégios administrativos.</span><span class="sxs-lookup"><span data-stu-id="e95ae-129">`Update-Help` requires administrative privileges.</span></span>
>
> <span data-ttu-id="e95ae-130">Você deve ser um membro do grupo Administradores no computador para atualizar os arquivos de ajuda para os módulos do PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="e95ae-130">You must be a member of the Administrators group on the computer to update the help files for the PowerShell Core modules.</span></span>
>
> <span data-ttu-id="e95ae-131">Para baixar ou atualizar os arquivos de ajuda para os módulos no diretório de instalação do PowerShell ( `$PSHOME\Modules` ), incluindo os módulos do PowerShell Core, inicie o PowerShell usando a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="e95ae-131">To download or update the help files for modules in the PowerShell installation directory (`$PSHOME\Modules`), including the PowerShell Core modules, start PowerShell by using the Run as administrator option.</span></span>
> <span data-ttu-id="e95ae-132">Por exemplo: `Start-Process powershell.exe -Verb RunAs`.</span><span class="sxs-lookup"><span data-stu-id="e95ae-132">For example: `Start-Process powershell.exe -Verb RunAs`.</span></span>
>
> <span data-ttu-id="e95ae-133">Você também pode atualizar os arquivos de ajuda usando o item de menu atualizar ajuda do Windows PowerShell no menu ajuda no Ambiente de Script Integrado do Windows PowerShell (ISE).</span><span class="sxs-lookup"><span data-stu-id="e95ae-133">You can also update help files by using the Update Windows PowerShell Help menu item in the Help menu in Windows PowerShell Integrated Scripting Environment (ISE).</span></span>
>
> <span data-ttu-id="e95ae-134">O item de ajuda atualizar o Windows PowerShell executa um `Update-Help` cmdlet sem parâmetros.</span><span class="sxs-lookup"><span data-stu-id="e95ae-134">The Update Windows PowerShell Help item runs an `Update-Help` cmdlet without parameters.</span></span>
> <span data-ttu-id="e95ae-135">Para atualizar a ajuda para os módulos no `$PSHOME` diretório, inicie ISE do Windows PowerShell usando a opção Executar como administrador.</span><span class="sxs-lookup"><span data-stu-id="e95ae-135">To update help for modules in the `$PSHOME` directory, start Windows PowerShell ISE by using the Run as administrator option.</span></span>

## <span data-ttu-id="e95ae-136">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="e95ae-136">EXAMPLES</span></span>

### <span data-ttu-id="e95ae-137">Exemplo 1: atualizar arquivos de ajuda para todos os módulos</span><span class="sxs-lookup"><span data-stu-id="e95ae-137">Example 1: Update help files for all modules</span></span>

<span data-ttu-id="e95ae-138">O `Update-Help` cmdlet atualiza os arquivos de ajuda para os módulos instalados que dão suporte à ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="e95ae-138">The `Update-Help` cmdlet updates help files for installed modules that support Updatable Help.</span></span> <span data-ttu-id="e95ae-139">O idioma da cultura da interface do usuário é definido no sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="e95ae-139">The user-interface (UI) culture language is set in the operating system.</span></span>

```powershell
Update-Help
```

### <span data-ttu-id="e95ae-140">Exemplo 2: atualizar os arquivos de ajuda para os módulos especificados</span><span class="sxs-lookup"><span data-stu-id="e95ae-140">Example 2: Update help files for specified modules</span></span>

<span data-ttu-id="e95ae-141">O `Update-Help` cmdlet atualiza os arquivos de ajuda somente para nomes de módulo que começam com **Microsoft. PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="e95ae-141">The `Update-Help` cmdlet updates help files only for module names that begin with **Microsoft.PowerShell** .</span></span>

```powershell
Update-Help -Module Microsoft.PowerShell*
```

### <span data-ttu-id="e95ae-142">Exemplo 3: atualizar arquivos de ajuda para idiomas diferentes</span><span class="sxs-lookup"><span data-stu-id="e95ae-142">Example 3: Update help files for different languages</span></span>

<span data-ttu-id="e95ae-143">O `Update-Help` cmdlet atualiza os arquivos de ajuda japoneses (ja-JP) e inglês (en-US) para todos os módulos.</span><span class="sxs-lookup"><span data-stu-id="e95ae-143">The `Update-Help` cmdlet updates the Japanese (ja-JP) and English (en-US) help files for all modules.</span></span>

<span data-ttu-id="e95ae-144">Se um módulo não fornecer arquivos de ajuda para uma cultura de interface do usuário especificada, uma mensagem de erro será exibida para a cultura do módulo e da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="e95ae-144">If a module doesn't provide help files for a specified UI culture, an error message is displayed for the module and UI culture.</span></span> <span data-ttu-id="e95ae-145">Neste exemplo, a mensagem de erro indica que os arquivos de ajuda do **ja-JP** não foram encontrados para o módulo **Microsoft. PowerShell. Utility** .</span><span class="sxs-lookup"><span data-stu-id="e95ae-145">In this example, the error message indicates that the **ja-JP** help files were not found for module **Microsoft.PowerShell.Utility** .</span></span>

```powershell
Update-Help -UICulture ja-JP, en-US
```

```Output
Update-Help : Failed to update Help for the module(s) 'Microsoft.PowerShell.Utility' with UI culture(s) {ja-JP}
No UI culture was found that matches the following pattern: ja-JP.
```

### <span data-ttu-id="e95ae-146">Exemplo 4: atualizar automaticamente os arquivos de ajuda</span><span class="sxs-lookup"><span data-stu-id="e95ae-146">Example 4: Update help files automatically</span></span>

<span data-ttu-id="e95ae-147">Este exemplo cria um trabalho agendado que atualiza a ajuda para todos os módulos todos os dias às 3:00.</span><span class="sxs-lookup"><span data-stu-id="e95ae-147">This example creates a scheduled job that updates help for all modules every day at 3:00 AM.</span></span>

```powershell
$jobParams = @{
  Name = 'UpdateHelpJob'
  Credential = 'Domain01\User01'
  ScriptBlock = '{Update-Help}'
  Trigger = (New-JobTrigger -Daily -At "3 AM")
}
Register-ScheduledJob @jobParams
```

```Output
Id         Name            JobTriggers     Command                                  Enabled
--         ----            -----------     -------                                  -------
1          UpdateHelpJob   1               Update-Help                              True
```

<span data-ttu-id="e95ae-148">O `Register-ScheduledJob` cmdlet cria um trabalho agendado que executa um `Update-Help` comando.</span><span class="sxs-lookup"><span data-stu-id="e95ae-148">The `Register-ScheduledJob` cmdlet creates a scheduled job that runs an `Update-Help` command.</span></span> <span data-ttu-id="e95ae-149">O comando usa o parâmetro **Credential** para ser executado `Update-Help` usando as credenciais de um membro do grupo Administradores no computador.</span><span class="sxs-lookup"><span data-stu-id="e95ae-149">The command uses the **Credential** parameter to run `Update-Help` by using the credentials of a member of the Administrators group on the computer.</span></span> <span data-ttu-id="e95ae-150">O valor do parâmetro **Trigger** é um `New-JobTrigger` comando que cria um gatilho de trabalho que inicia o trabalho todos os dias às 3:00.</span><span class="sxs-lookup"><span data-stu-id="e95ae-150">The value of the **Trigger** parameter is a `New-JobTrigger` command that creates a job trigger that starts the job every day at 3:00 AM.</span></span>

<span data-ttu-id="e95ae-151">Para executar o `Register-ScheduledJob` comando, inicie o PowerShell usando a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="e95ae-151">To run the `Register-ScheduledJob` command, start PowerShell by using the **Run as administrator** option.</span></span> <span data-ttu-id="e95ae-152">O PowerShell solicita a senha do usuário especificado no parâmetro **Credential** .</span><span class="sxs-lookup"><span data-stu-id="e95ae-152">PowerShell prompts you for the password of the user specified in the **Credential** parameter.</span></span> <span data-ttu-id="e95ae-153">As credenciais são armazenadas com o trabalho agendado.</span><span class="sxs-lookup"><span data-stu-id="e95ae-153">The credentials are stored with the scheduled job.</span></span> <span data-ttu-id="e95ae-154">Você não será avisado quando o trabalho for executado.</span><span class="sxs-lookup"><span data-stu-id="e95ae-154">You aren't prompted when the job runs.</span></span>

<span data-ttu-id="e95ae-155">Você pode usar o `Get-ScheduledJob` cmdlet para exibir o trabalho agendado, usar o `Set-ScheduledJob` cmdlet para alterá-lo e usar o `Unregister-ScheduledJob` cmdlet para excluí-lo.</span><span class="sxs-lookup"><span data-stu-id="e95ae-155">You can use the `Get-ScheduledJob` cmdlet to view the scheduled job, use the `Set-ScheduledJob` cmdlet to change it, and use the `Unregister-ScheduledJob` cmdlet to delete it.</span></span> <span data-ttu-id="e95ae-156">Você também pode exibir e gerenciar o trabalho agendado no Agendador de tarefas no seguinte caminho:</span><span class="sxs-lookup"><span data-stu-id="e95ae-156">You can also view and manage the scheduled job in Task Scheduler in the following path:</span></span>

<span data-ttu-id="e95ae-157">`Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs`.</span><span class="sxs-lookup"><span data-stu-id="e95ae-157">`Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs`.</span></span>

### <span data-ttu-id="e95ae-158">Exemplo 5: atualizar arquivos de ajuda em vários computadores a partir de um compartilhamento de arquivos</span><span class="sxs-lookup"><span data-stu-id="e95ae-158">Example 5: Update help files on multiple computers from a file share</span></span>

<span data-ttu-id="e95ae-159">Neste exemplo, os arquivos de ajuda atualizados são baixados da Internet e salvos em um compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="e95ae-159">In this example, updated help files are downloaded from the internet and saved in a file share.</span></span> <span data-ttu-id="e95ae-160">São necessárias credenciais de usuário que têm permissões para acessar o compartilhamento de arquivos e instalar atualizações.</span><span class="sxs-lookup"><span data-stu-id="e95ae-160">User credentials are needed that have permissions to access the file share and install updates.</span></span> <span data-ttu-id="e95ae-161">Quando um compartilhamento de arquivos é usado, é possível atualizar computadores que estão atrás de firewalls ou que não estão conectados à Internet.</span><span class="sxs-lookup"><span data-stu-id="e95ae-161">When a file share is used, it's possible to update computers that are behind firewalls or aren't connected to the internet.</span></span>

```powershell
Save-Help -DestinationPath \\Server01\Share\PSHelp -Credential Domain01\Admin01
Invoke-Command -ComputerName (Get-Content Servers.txt) -ScriptBlock {
     Update-Help -SourcePath \\Server01\Share\PSHelp -Credential Domain01\Admin01
}
```

<span data-ttu-id="e95ae-162">O `Save-Help` comando baixa os arquivos de ajuda mais recentes para todos os módulos que dão suporte à ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="e95ae-162">The `Save-Help` command downloads the newest help files for all modules that support Updatable Help.</span></span>
<span data-ttu-id="e95ae-163">O parâmetro **DestinationPath** salva os arquivos no `\\Server01\Share\PSHelp` compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="e95ae-163">The **DestinationPath** parameter saves the files in the `\\Server01\Share\PSHelp` file share.</span></span> <span data-ttu-id="e95ae-164">O parâmetro **Credential** especifica um usuário que tem permissão para acessar o compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="e95ae-164">The **Credential** parameter specifies a user who has permission to access the file share.</span></span>

<span data-ttu-id="e95ae-165">O `Invoke-Command` cmdlet executa comandos remotos `Update-Help` em vários computadores.</span><span class="sxs-lookup"><span data-stu-id="e95ae-165">The `Invoke-Command` cmdlet runs remote `Update-Help` commands on multiple computers.</span></span> <span data-ttu-id="e95ae-166">O parâmetro **ComputerName** Obtém uma lista de computadores remotos do arquivo **Servers.txt** .</span><span class="sxs-lookup"><span data-stu-id="e95ae-166">The **ComputerName** parameter gets a list of remote computers from the **Servers.txt** file.</span></span> <span data-ttu-id="e95ae-167">O parâmetro **scriptblock** executa o `Update-Help` comando e usa o parâmetro **SourcePath** para especificar o compartilhamento de arquivos que contém os arquivos de ajuda atualizados.</span><span class="sxs-lookup"><span data-stu-id="e95ae-167">The **ScriptBlock** parameter runs the `Update-Help` command and uses the **SourcePath** parameter to specify the file share that contains the updated help files.</span></span> <span data-ttu-id="e95ae-168">O parâmetro **Credential** especifica um usuário que pode acessar o compartilhamento de arquivos e executar o `Update-Help` comando remoto.</span><span class="sxs-lookup"><span data-stu-id="e95ae-168">The **Credential** parameter specifies a user who can access the file share and run the remote `Update-Help` command.</span></span>

### <span data-ttu-id="e95ae-169">Exemplo 6: obter uma lista de arquivos de ajuda atualizados</span><span class="sxs-lookup"><span data-stu-id="e95ae-169">Example 6: Get a list of updated help files</span></span>

<span data-ttu-id="e95ae-170">O `Update-Help` cmdlet atualiza a ajuda para um módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="e95ae-170">The `Update-Help` cmdlet updates help for a specified module.</span></span> <span data-ttu-id="e95ae-171">O cmdlet usa o parâmetro comum **detalhado** para exibir a lista de arquivos de ajuda que foram atualizados.</span><span class="sxs-lookup"><span data-stu-id="e95ae-171">The cmdlet uses the **Verbose** common parameter to display the list of help files that were updated.</span></span> <span data-ttu-id="e95ae-172">Você pode usar o modo **detalhado** para exibir a saída de todos os arquivos de ajuda ou arquivos de ajuda para um módulo específico.</span><span class="sxs-lookup"><span data-stu-id="e95ae-172">You can use **Verbose** to view output for all help files or help files for a specific module.</span></span>

<span data-ttu-id="e95ae-173">Sem o parâmetro **Verbose** , o `Update-Help` não exibe os resultados do comando.</span><span class="sxs-lookup"><span data-stu-id="e95ae-173">Without the **Verbose** parameter, `Update-Help` doesn't display the results of the command.</span></span> <span data-ttu-id="e95ae-174">A saída de parâmetro **detalhado** é útil para verificar se os arquivos de ajuda foram atualizados ou se a versão mais recente está instalada.</span><span class="sxs-lookup"><span data-stu-id="e95ae-174">The **Verbose** parameter output is useful to verify that the help files were updated or if the latest version is installed.</span></span>

```powershell
Update-Help -Module Microsoft.PowerShell.Utility -Verbose
```

### <span data-ttu-id="e95ae-175">Exemplo 7: localizar módulos que dão suporte à ajuda atualizável</span><span class="sxs-lookup"><span data-stu-id="e95ae-175">Example 7: Find modules that support Updatable Help</span></span>

<span data-ttu-id="e95ae-176">Este exemplo lista os módulos que oferecem suporte à ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="e95ae-176">This example lists modules that support Updatable Help.</span></span> <span data-ttu-id="e95ae-177">O comando usa a propriedade **HelpInfoUri** do módulo para identificar os módulos que oferecem suporte à ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="e95ae-177">The command uses the module's **HelpInfoUri** property to identify modules that support Updatable Help.</span></span> <span data-ttu-id="e95ae-178">A propriedade **HelpInfoUri** contém um endereço que é redirecionado quando o `Update-Help` cmdlet é executado.</span><span class="sxs-lookup"><span data-stu-id="e95ae-178">The **HelpInfoUri** property contains an address that is redirected when the `Update-Help` cmdlet is run.</span></span>

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

### <span data-ttu-id="e95ae-179">Exemplo 8: Arquivos de ajuda atualizados de inventário</span><span class="sxs-lookup"><span data-stu-id="e95ae-179">Example 8: Inventory updated help files</span></span>

<span data-ttu-id="e95ae-180">Neste exemplo, o script `Get-UpdateHelpVersion.ps1` cria um inventário dos arquivos de ajuda atualizáveis para cada módulo e seus números de versão.</span><span class="sxs-lookup"><span data-stu-id="e95ae-180">In this example, the script `Get-UpdateHelpVersion.ps1` creates an inventory of the Updatable Help files for each module and their version numbers.</span></span>

<span data-ttu-id="e95ae-181">O script identifica os módulos que dão suporte à ajuda atualizável usando a propriedade **HelpInfoUri** dos módulos.</span><span class="sxs-lookup"><span data-stu-id="e95ae-181">The script identifies modules that support Updatable Help by using the **HelpInfoUri** property of modules.</span></span> <span data-ttu-id="e95ae-182">Para módulos que dão suporte à ajuda atualizável, o script procura e analisa o arquivo de informações de ajuda (\* helpinfo.xml) para localizar o número de versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="e95ae-182">For modules that support Updatable Help, the script looks for and parses the help information file (\*helpinfo.xml) to find the latest version number.</span></span>

<span data-ttu-id="e95ae-183">O script usa a classe **PSCustomObject** e uma tabela de hash para criar um objeto de saída personalizado.</span><span class="sxs-lookup"><span data-stu-id="e95ae-183">The script uses the **PSCustomObject** class and a hash table to create a custom output object.</span></span>

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

## <span data-ttu-id="e95ae-184">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e95ae-184">PARAMETERS</span></span>

### <span data-ttu-id="e95ae-185">-Credential</span><span class="sxs-lookup"><span data-stu-id="e95ae-185">-Credential</span></span>

<span data-ttu-id="e95ae-186">Especifica as credenciais de um usuário que tem permissão para acessar o local do sistema de arquivos especificado por **SourcePath** .</span><span class="sxs-lookup"><span data-stu-id="e95ae-186">Specifies credentials of a user who has permission to access the file system location specified by **SourcePath** .</span></span> <span data-ttu-id="e95ae-187">Esse parâmetro é válido somente quando o parâmetro **SourcePath** ou **LiteralPath** é usado no comando.</span><span class="sxs-lookup"><span data-stu-id="e95ae-187">This parameter is valid only when the **SourcePath** or **LiteralPath** parameter is used in the command.</span></span>

<span data-ttu-id="e95ae-188">O parâmetro **Credential** permite que você execute `Update-Help` comandos com o parâmetro **SourcePath** em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="e95ae-188">The **Credential** parameter enables you to run `Update-Help` commands with the **SourcePath** parameter on remote computers.</span></span> <span data-ttu-id="e95ae-189">Ao fornecer credenciais explícitas, você pode executar o comando em um computador remoto e acessar um compartilhamento de arquivos em um terceiro computador sem encontrar um erro de acesso negado ou usar a autenticação CredSSP para delegar credenciais.</span><span class="sxs-lookup"><span data-stu-id="e95ae-189">By providing explicit credentials, you can run the command on a remote computer and access a file share on a third computer without encountering an access denied error or using CredSSP authentication to delegate credentials.</span></span>

<span data-ttu-id="e95ae-190">Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** gerado pelo `Get-Credential` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e95ae-190">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="e95ae-191">Se você digitar um nome de usuário, você será solicitado a inserir a senha.</span><span class="sxs-lookup"><span data-stu-id="e95ae-191">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="e95ae-192">As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="e95ae-192">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="e95ae-193">Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="e95ae-193">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="e95ae-194">-Force</span><span class="sxs-lookup"><span data-stu-id="e95ae-194">-Force</span></span>

<span data-ttu-id="e95ae-195">Indica que esse cmdlet não segue a limitação de uma vez por dia, ignora a verificação de versão e baixa os arquivos que excedem o limite de 1 GB.</span><span class="sxs-lookup"><span data-stu-id="e95ae-195">Indicates that this cmdlet doesn't follow the once-per-day limitation, skips version checking, and downloads files that exceed the 1 GB limit.</span></span>

<span data-ttu-id="e95ae-196">Sem esse parâmetro, o `Update-Help` é executado apenas uma vez em cada período de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="e95ae-196">Without this parameter, `Update-Help` runs only once in each 24-hour period.</span></span> <span data-ttu-id="e95ae-197">Os downloads são limitados a 1 GB de conteúdo descompactado por módulo e os arquivos de ajuda são instalados apenas quando são mais recentes do que os arquivos existentes no computador.</span><span class="sxs-lookup"><span data-stu-id="e95ae-197">Downloads are limited to 1 GB of uncompressed content per module and help files are only installed when they're newer than the existing files on the computer.</span></span>

<span data-ttu-id="e95ae-198">O limite de uma vez por dia protege os servidores que hospedam os arquivos de ajuda e torna prático para você adicionar um `Update-Help` comando ao seu perfil do PowerShell sem incorrer no custo de recursos de conexões ou downloads repetidos.</span><span class="sxs-lookup"><span data-stu-id="e95ae-198">The once-per-day limit protects the servers that host the help files and makes it practical for you to add an `Update-Help` command to your PowerShell profile without incurring the resource cost of repeated connections or downloads.</span></span>

<span data-ttu-id="e95ae-199">Para atualizar a Ajuda para um módulo em várias culturas de interface do usuário sem o parâmetro **Force** , incluem todas as culturas de interface do usuário no mesmo comando, como:</span><span class="sxs-lookup"><span data-stu-id="e95ae-199">To update help for a module in multiple UI cultures without the **Force** parameter, include all UI cultures in the same command, such as:</span></span>

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

### <span data-ttu-id="e95ae-200">-FullyQualifiedModule</span><span class="sxs-lookup"><span data-stu-id="e95ae-200">-FullyQualifiedModule</span></span>

<span data-ttu-id="e95ae-201">Especifica os módulos com nomes que são especificados na forma de objetos **ModuleSpecification** .</span><span class="sxs-lookup"><span data-stu-id="e95ae-201">Specifies modules with names that are specified in the form of **ModuleSpecification** objects.</span></span>
<span data-ttu-id="e95ae-202">Esses módulos são descritos na seção comentários do [Construtor ModuleSpecification (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span><span class="sxs-lookup"><span data-stu-id="e95ae-202">These modules are described in the Remarks section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>

<span data-ttu-id="e95ae-203">Por exemplo, o parâmetro **FullyQualifiedModule** aceita um nome de módulo que é especificado no formato:</span><span class="sxs-lookup"><span data-stu-id="e95ae-203">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in the format:</span></span>

`@{ModuleName = "modulename"; ModuleVersion = "version_number"}`

<span data-ttu-id="e95ae-204">ou</span><span class="sxs-lookup"><span data-stu-id="e95ae-204">or</span></span>

`@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}.`

<span data-ttu-id="e95ae-205">**ModuleName** e **ModuleVersion** são obrigatórios, mas **Guid** é opcional.</span><span class="sxs-lookup"><span data-stu-id="e95ae-205">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span>

<span data-ttu-id="e95ae-206">Você não pode especificar o parâmetro **FullyQualifiedModule** no mesmo comando que um parâmetro de **módulo** .</span><span class="sxs-lookup"><span data-stu-id="e95ae-206">You can't specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span>

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

### <span data-ttu-id="e95ae-207">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="e95ae-207">-LiteralPath</span></span>

<span data-ttu-id="e95ae-208">Especifica a pasta para arquivos de ajuda atualizados em vez de baixá-los da Internet.</span><span class="sxs-lookup"><span data-stu-id="e95ae-208">Specifies the folder for updated help files instead of downloading them from the internet.</span></span> <span data-ttu-id="e95ae-209">Use esse parâmetro ou **SourcePath** se você tiver usado o `Save-Help` cmdlet para baixar arquivos de ajuda para um diretório.</span><span class="sxs-lookup"><span data-stu-id="e95ae-209">Use this parameter or **SourcePath** if you've used the `Save-Help` cmdlet to download help files to a directory.</span></span>

<span data-ttu-id="e95ae-210">Você pode canalizar um objeto de diretório, como dos `Get-Item` `Get-ChildItem` cmdlets ou, para `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="e95ae-210">You can pipeline a directory object, such as from the `Get-Item` or `Get-ChildItem` cmdlets, to `Update-Help`.</span></span>

<span data-ttu-id="e95ae-211">Ao contrário do valor de **SourcePath** , o valor de **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="e95ae-211">Unlike the value of **SourcePath** , the value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="e95ae-212">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="e95ae-212">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="e95ae-213">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="e95ae-213">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="e95ae-214">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="e95ae-214">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e95ae-215">-Módulo</span><span class="sxs-lookup"><span data-stu-id="e95ae-215">-Module</span></span>

<span data-ttu-id="e95ae-216">Atualizações de Ajuda para os módulos especificados.</span><span class="sxs-lookup"><span data-stu-id="e95ae-216">Updates help for the specified modules.</span></span> <span data-ttu-id="e95ae-217">Insira um ou mais nomes de módulo ou padrões de nome em uma lista separada por vírgulas ou especifique um arquivo que liste um nome de módulo em cada linha.</span><span class="sxs-lookup"><span data-stu-id="e95ae-217">Enter one or more module names or name patterns in a comma-separated list, or specify a file that lists one module name on each line.</span></span> <span data-ttu-id="e95ae-218">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="e95ae-218">Wildcard characters are permitted.</span></span> <span data-ttu-id="e95ae-219">Você pode canalizar módulos do `Get-Module` cmdlet para o `Update-Help` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e95ae-219">You can pipeline modules from the `Get-Module` cmdlet to the `Update-Help` cmdlet.</span></span>

<span data-ttu-id="e95ae-220">Os módulos que você especificar devem ser instalados no computador, mas não precisam ser importados para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="e95ae-220">The modules that you specify must be installed on the computer, but they don't have to be imported into the current session.</span></span> <span data-ttu-id="e95ae-221">Você pode especificar qualquer módulo na sessão ou qualquer módulo que esteja instalado em um local listado na variável de `$env:PSModulePath` ambiente.</span><span class="sxs-lookup"><span data-stu-id="e95ae-221">You can specify any module in the session or any module that is installed in a location listed in the `$env:PSModulePath` environment variable.</span></span>

<span data-ttu-id="e95ae-222">Um valor de `*` (All) tenta atualizar a ajuda para todos os módulos instalados no computador.</span><span class="sxs-lookup"><span data-stu-id="e95ae-222">A value of `*` (all) attempts to update help for all modules that are installed on the computer.</span></span>
<span data-ttu-id="e95ae-223">Módulos que não dão suporte à ajuda atualizável estão incluídos.</span><span class="sxs-lookup"><span data-stu-id="e95ae-223">Modules that don't support Updatable Help are included.</span></span> <span data-ttu-id="e95ae-224">Esse valor pode gerar erros quando o comando encontra módulos que não dão suporte à ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="e95ae-224">This value might generate errors when the command encounters modules that don't support Updatable Help.</span></span> <span data-ttu-id="e95ae-225">Em vez disso, execute `Update-Help` sem parâmetros.</span><span class="sxs-lookup"><span data-stu-id="e95ae-225">Instead, run `Update-Help` without parameters.</span></span>

<span data-ttu-id="e95ae-226">O parâmetro **Module** do `Update-Help` cmdlet não aceita o caminho completo de um arquivo de módulo ou arquivo de manifesto de módulo.</span><span class="sxs-lookup"><span data-stu-id="e95ae-226">The **Module** parameter of the `Update-Help` cmdlet doesn't accept the full path of a module file or module manifest file.</span></span> <span data-ttu-id="e95ae-227">Para atualizar a ajuda para um módulo que não está em um `$env:PSModulePath` local, importe o módulo para a sessão atual antes de executar o `Update-Help` comando.</span><span class="sxs-lookup"><span data-stu-id="e95ae-227">To update help for a module that isn't in a `$env:PSModulePath` location, import the module into the current session before you run the `Update-Help` command.</span></span>

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

### <span data-ttu-id="e95ae-228">-Recurse</span><span class="sxs-lookup"><span data-stu-id="e95ae-228">-Recurse</span></span>

<span data-ttu-id="e95ae-229">Executa uma pesquisa recursiva de arquivos de ajuda no diretório especificado.</span><span class="sxs-lookup"><span data-stu-id="e95ae-229">Performs a recursive search for help files in the specified directory.</span></span> <span data-ttu-id="e95ae-230">Esse parâmetro é válido somente quando o comando usa o parâmetro **SourcePath** .</span><span class="sxs-lookup"><span data-stu-id="e95ae-230">This parameter is valid only when the command uses the **SourcePath** parameter.</span></span>

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

### <span data-ttu-id="e95ae-231">-SourcePath</span><span class="sxs-lookup"><span data-stu-id="e95ae-231">-SourcePath</span></span>

<span data-ttu-id="e95ae-232">Especifica uma pasta do sistema de arquivos em que o `Update-Help` Obtém arquivos de ajuda atualizados, em vez de baixá-los da Internet.</span><span class="sxs-lookup"><span data-stu-id="e95ae-232">Specifies a file system folder where `Update-Help` gets updated help files, instead of downloading them from the internet.</span></span> <span data-ttu-id="e95ae-233">Insira o caminho de uma pasta.</span><span class="sxs-lookup"><span data-stu-id="e95ae-233">Enter the path of a folder.</span></span> <span data-ttu-id="e95ae-234">Não especifique um nome de arquivo ou uma extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="e95ae-234">Don't specify a file name or file name extension.</span></span> <span data-ttu-id="e95ae-235">Você pode canalizar uma pasta, como uma dos `Get-Item` `Get-ChildItem` cmdlets ou, para `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="e95ae-235">You can pipeline a folder, such as one from the `Get-Item` or `Get-ChildItem` cmdlets, to `Update-Help`.</span></span>

<span data-ttu-id="e95ae-236">Por padrão, o `Update-Help` baixa arquivos de ajuda atualizados da Internet.</span><span class="sxs-lookup"><span data-stu-id="e95ae-236">By default, `Update-Help` downloads updated help files from the internet.</span></span> <span data-ttu-id="e95ae-237">Use **SourcePath** quando você tiver usado o `Save-Help` cmdlet para baixar arquivos de ajuda atualizados para um diretório.</span><span class="sxs-lookup"><span data-stu-id="e95ae-237">Use **SourcePath** when you've used the `Save-Help` cmdlet to download updated help files to a directory.</span></span>

<span data-ttu-id="e95ae-238">Para especificar um valor padrão para **SourcePath** , vá para **política de grupo** , **configuração do computador** e **defina o caminho de origem padrão para Update-Help** .</span><span class="sxs-lookup"><span data-stu-id="e95ae-238">To specify a default value for **SourcePath** , go to **Group Policy** , **Computer Configuration** , and **Set the default source path for Update-Help** .</span></span> <span data-ttu-id="e95ae-239">Essa configuração de Política de Grupo impede que os usuários usem `Update-Help` o para baixar arquivos de ajuda da Internet.</span><span class="sxs-lookup"><span data-stu-id="e95ae-239">This Group Policy setting prevents users from using `Update-Help` to download help files from the internet.</span></span>
<span data-ttu-id="e95ae-240">Confira mais informações em [about_Group_Policy_Settings](./About/about_Group_Policy_Settings.md).</span><span class="sxs-lookup"><span data-stu-id="e95ae-240">For more information, see [about_Group_Policy_Settings](./About/about_Group_Policy_Settings.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e95ae-241">-UICulture</span><span class="sxs-lookup"><span data-stu-id="e95ae-241">-UICulture</span></span>

<span data-ttu-id="e95ae-242">Especifica os valores de cultura da interface do usuário que o `Update-Help` usa para obter arquivos de ajuda atualizados.</span><span class="sxs-lookup"><span data-stu-id="e95ae-242">Specifies UI culture values that `Update-Help` uses to get updated help files.</span></span> <span data-ttu-id="e95ae-243">Insira um ou mais códigos de idioma, como **es-es** , uma variável que contém objetos de cultura ou um comando que obtém objetos de cultura, como um `Get-Culture` `Get-UICulture` comando ou.</span><span class="sxs-lookup"><span data-stu-id="e95ae-243">Enter one or more language codes, such as **es-ES** , a variable that contains culture objects, or a command that gets culture objects, such as a `Get-Culture` or `Get-UICulture` command.</span></span> <span data-ttu-id="e95ae-244">Os caracteres curinga não são permitidos e você não pode enviar um código de idioma parcial, como **de** .</span><span class="sxs-lookup"><span data-stu-id="e95ae-244">Wildcard characters aren't permitted and you can't submit a partial language code, such as **de** .</span></span>

<span data-ttu-id="e95ae-245">Por padrão, `Update-Help` o Obtém os arquivos de ajuda na cultura da interface do usuário definida para o sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="e95ae-245">By default, `Update-Help` gets help files in the UI culture set for the operating system.</span></span> <span data-ttu-id="e95ae-246">Se você especificar o parâmetro **UICulture** , o `Update-Help` procurará ajuda apenas para a cultura da interface do usuário especificada.</span><span class="sxs-lookup"><span data-stu-id="e95ae-246">If you specify the **UICulture** parameter, `Update-Help` looks for help only for the specified UI culture.</span></span>

<span data-ttu-id="e95ae-247">Os comandos que utilizam o parâmetro **UICulture** têm êxito somente quando o módulo fornece arquivos de ajuda para a cultura da interface do usuário especificado.</span><span class="sxs-lookup"><span data-stu-id="e95ae-247">Commands that use the **UICulture** parameter succeed only when the module provides help files for the specified UI culture.</span></span> <span data-ttu-id="e95ae-248">Se o comando falhar porque a cultura da interface do usuário especificada não tem suporte, será exibida uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="e95ae-248">If the command fails because the specified UI culture isn't supported, an error message is displayed.</span></span>

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

### <span data-ttu-id="e95ae-249">-UseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="e95ae-249">-UseDefaultCredentials</span></span>

<span data-ttu-id="e95ae-250">Indica que `Update-Help` o executa o comando, incluindo o download da Internet, usando as credenciais do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="e95ae-250">Indicates that `Update-Help` runs the command, including the internet download, by using the credentials of the current user.</span></span> <span data-ttu-id="e95ae-251">Por padrão, o comando é executado sem credenciais explícitas.</span><span class="sxs-lookup"><span data-stu-id="e95ae-251">By default, the command runs without explicit credentials.</span></span>

<span data-ttu-id="e95ae-252">Esse parâmetro é eficaz somente quando o download da Web usa o NTLM (NT LAN Manager), Negotiate ou autenticação baseada em Kerberos.</span><span class="sxs-lookup"><span data-stu-id="e95ae-252">This parameter is effective only when the web download uses NT LAN Manager (NTLM), negotiate, or Kerberos-based authentication.</span></span>

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

### <span data-ttu-id="e95ae-253">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e95ae-253">-Confirm</span></span>

<span data-ttu-id="e95ae-254">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e95ae-254">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e95ae-255">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e95ae-255">-WhatIf</span></span>

<span data-ttu-id="e95ae-256">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="e95ae-256">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="e95ae-257">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="e95ae-257">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="e95ae-258">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e95ae-258">CommonParameters</span></span>

<span data-ttu-id="e95ae-259">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e95ae-259">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e95ae-260">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e95ae-260">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e95ae-261">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="e95ae-261">INPUTS</span></span>

### <span data-ttu-id="e95ae-262">System. IO. DirectoryInfo</span><span class="sxs-lookup"><span data-stu-id="e95ae-262">System.IO.DirectoryInfo</span></span>

<span data-ttu-id="e95ae-263">É possível canalizar um caminho de diretório para `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="e95ae-263">You can pipe a directory path to `Update-Help`.</span></span>

### <span data-ttu-id="e95ae-264">System. Management. Automation. PSModuleInfo</span><span class="sxs-lookup"><span data-stu-id="e95ae-264">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="e95ae-265">É possível canalizar um objeto de módulo do `Get-Module` cmdlet para `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="e95ae-265">You can pipe a module object from the `Get-Module` cmdlet to `Update-Help`.</span></span>

## <span data-ttu-id="e95ae-266">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="e95ae-266">OUTPUTS</span></span>

### <span data-ttu-id="e95ae-267">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e95ae-267">None</span></span>

<span data-ttu-id="e95ae-268">`Update-Help` não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="e95ae-268">`Update-Help` doesn't generate any output.</span></span>

## <span data-ttu-id="e95ae-269">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="e95ae-269">NOTES</span></span>

<span data-ttu-id="e95ae-270">Para atualizar a ajuda para os módulos do PowerShell Core, que contêm os comandos instalados com o PowerShell ou qualquer módulo no `$PSHOME\Modules` diretório, inicie o PowerShell com a opção de **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="e95ae-270">To update help for the PowerShell Core modules, that contain the commands that are installed with PowerShell, or any module in the `$PSHOME\Modules` directory, start PowerShell with the option to **Run as administrator** .</span></span>

<span data-ttu-id="e95ae-271">Somente os membros do grupo Administradores no computador podem atualizar a ajuda para os módulos do PowerShell Core, os comandos que são instalados junto com o PowerShell e para os módulos na `$PSHOME\Modules` pasta.</span><span class="sxs-lookup"><span data-stu-id="e95ae-271">Only members of the Administrators group on the computer can update help for the PowerShell Core modules, the commands that are installed together with PowerShell, and for modules in the `$PSHOME\Modules` folder.</span></span> <span data-ttu-id="e95ae-272">Se você não tiver permissão para atualizar os arquivos de ajuda, poderá ler os arquivos de ajuda online.</span><span class="sxs-lookup"><span data-stu-id="e95ae-272">If you don't have permission to update help files, you can read the help files online.</span></span> <span data-ttu-id="e95ae-273">Por exemplo, `Get-Help Update-Help -Online`.</span><span class="sxs-lookup"><span data-stu-id="e95ae-273">For example, `Get-Help Update-Help -Online`.</span></span>

<span data-ttu-id="e95ae-274">Os módulos são a menor unidade da ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="e95ae-274">Modules are the smallest unit of updatable help.</span></span> <span data-ttu-id="e95ae-275">Você não pode atualizar a ajuda para um cmdlet específico.</span><span class="sxs-lookup"><span data-stu-id="e95ae-275">You can't update help for a particular cmdlet.</span></span> <span data-ttu-id="e95ae-276">Para localizar o módulo que contém um cmdlet específico, use a propriedade **ModuleName** do `Get-Command` cmdlet, por exemplo, `(Get-Command Update-Help).ModuleName` .</span><span class="sxs-lookup"><span data-stu-id="e95ae-276">To find the module that contains a particular cmdlet, use the **ModuleName** property of the `Get-Command` cmdlet, for example, `(Get-Command Update-Help).ModuleName`.</span></span>

<span data-ttu-id="e95ae-277">Como os arquivos de ajuda são instalados no diretório do módulo, o `Update-Help` cmdlet pode instalar o arquivo de ajuda atualizado somente para os módulos que estão instalados no computador.</span><span class="sxs-lookup"><span data-stu-id="e95ae-277">Because help files are installed in the module directory, the `Update-Help` cmdlet can install updated help file only for modules that are installed on the computer.</span></span> <span data-ttu-id="e95ae-278">No entanto, o `Save-Help` cmdlet pode salvar ajuda para módulos que não estão instalados no computador.</span><span class="sxs-lookup"><span data-stu-id="e95ae-278">However, the `Save-Help` cmdlet can save help for modules that aren't installed on the computer.</span></span>

<span data-ttu-id="e95ae-279">Se `Update-Help` o não conseguir encontrar arquivos de ajuda atualizados para um módulo ou não conseguir encontrar ajuda atualizada no idioma especificado, ele continuará silenciosamente sem exibir uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="e95ae-279">If `Update-Help` can't find updated help files for a module, or can't find updated help in the specified language, it continues silently without displaying an error message.</span></span> <span data-ttu-id="e95ae-280">Para ver os detalhes de status e o andamento, use o parâmetro **Verbose** .</span><span class="sxs-lookup"><span data-stu-id="e95ae-280">To see status and progress details, use the **Verbose** parameter.</span></span>

<span data-ttu-id="e95ae-281">O `Update-Help` cmdlet foi introduzido no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="e95ae-281">The `Update-Help` cmdlet was introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="e95ae-282">Ele não funciona em versões anteriores do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e95ae-282">It doesn't work in earlier versions of PowerShell.</span></span> <span data-ttu-id="e95ae-283">Em computadores que têm o Windows PowerShell 2,0 e o Windows PowerShell 3,0, use o `Update-Help` cmdlet em uma sessão do Windows powershell 3,0 para baixar e atualizar os arquivos de ajuda.</span><span class="sxs-lookup"><span data-stu-id="e95ae-283">On computers that have both Windows PowerShell 2.0 and Windows PowerShell 3.0, use the `Update-Help` cmdlet in a Windows PowerShell 3.0 session to download and update help files.</span></span> <span data-ttu-id="e95ae-284">Os arquivos de ajuda estão disponíveis para o Windows PowerShell 2,0 e o Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="e95ae-284">The help files are available to both Windows PowerShell 2.0 and Windows PowerShell 3.0.</span></span>

<span data-ttu-id="e95ae-285">Os `Update-Help` `Save-Help` cmdlets e usam as seguintes portas para baixar arquivos de ajuda: porta 80 para http e porta 443 para https.</span><span class="sxs-lookup"><span data-stu-id="e95ae-285">The `Update-Help` and `Save-Help` cmdlets use the following ports to download help files: Port 80 for HTTP and port 443 for HTTPS.</span></span>

<span data-ttu-id="e95ae-286">`Update-Help` dá suporte a todos os módulos e os snap-ins do PowerShell Core. Ele não dá suporte a nenhum outro snap-ins.</span><span class="sxs-lookup"><span data-stu-id="e95ae-286">`Update-Help` supports all modules and the PowerShell Core snap-ins. It doesn't support any other snap-ins.</span></span>

<span data-ttu-id="e95ae-287">Para atualizar a ajuda de um módulo em um local que não está listado na `$env:PSModulePath` variável de ambiente, importe o módulo para a sessão atual e, em seguida, execute um `Update-Help` comando.</span><span class="sxs-lookup"><span data-stu-id="e95ae-287">To update help for a module in a location that isn't listed in the `$env:PSModulePath` environment variable, import the module into the current session and then run an `Update-Help` command.</span></span> <span data-ttu-id="e95ae-288">Execute `Update-Help` sem parâmetros ou use o parâmetro **Module** para especificar o nome do módulo.</span><span class="sxs-lookup"><span data-stu-id="e95ae-288">Run `Update-Help` without parameters or use the **Module** parameter to specify the module name.</span></span> <span data-ttu-id="e95ae-289">O parâmetro **Module** dos `Update-Help` `Save-Help` cmdlets e não aceita o caminho completo de um arquivo de módulo ou arquivo de manifesto de módulo.</span><span class="sxs-lookup"><span data-stu-id="e95ae-289">The **Module** parameter of the `Update-Help` and `Save-Help` cmdlets doesn't accept the full path of a module file or module manifest file.</span></span>

<span data-ttu-id="e95ae-290">Qualquer módulo pode dar suporte a Ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="e95ae-290">Any module can support Updatable Help.</span></span> <span data-ttu-id="e95ae-291">Para obter instruções para dar suporte à ajuda atualizável nos módulos que você cria, consulte [dando suporte à ajuda atualizável](/powershell/scripting/developer/module/supporting-updatable-help).</span><span class="sxs-lookup"><span data-stu-id="e95ae-291">For instructions for supporting Updatable Help in the modules that you author, see [Supporting Updatable Help](/powershell/scripting/developer/module/supporting-updatable-help).</span></span>

<span data-ttu-id="e95ae-292">`Update-Help` `Save-Help` Não há suporte para os cmdlets e no ambiente de pré-instalação do Windows (Windows PE).</span><span class="sxs-lookup"><span data-stu-id="e95ae-292">The `Update-Help` and `Save-Help` cmdlets are not supported on Windows Preinstallation Environment (Windows PE).</span></span>

## <span data-ttu-id="e95ae-293">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="e95ae-293">RELATED LINKS</span></span>

[<span data-ttu-id="e95ae-294">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="e95ae-294">Get-Culture</span></span>](../Microsoft.PowerShell.Utility/Get-Culture.md)

[<span data-ttu-id="e95ae-295">Get-Help</span><span class="sxs-lookup"><span data-stu-id="e95ae-295">Get-Help</span></span>](Get-Help.md)

[<span data-ttu-id="e95ae-296">Get-Module</span><span class="sxs-lookup"><span data-stu-id="e95ae-296">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="e95ae-297">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="e95ae-297">Get-UICulture</span></span>](../Microsoft.PowerShell.Utility/Get-UICulture.md)

[<span data-ttu-id="e95ae-298">Start-Job</span><span class="sxs-lookup"><span data-stu-id="e95ae-298">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="e95ae-299">Save-Help</span><span class="sxs-lookup"><span data-stu-id="e95ae-299">Save-Help</span></span>](Save-Help.md)
