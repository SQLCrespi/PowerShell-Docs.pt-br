---
description: Descreve o sistema de ajuda atualizável no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 08/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_updatable_help?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Updatable_Help
ms.openlocfilehash: 03425aef93f3d4bbb06aee87d30f4a441c0b2d86
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196143"
---
# <a name="about-updatable-help"></a><span data-ttu-id="a4b8b-104">Sobre a ajuda atualizável</span><span class="sxs-lookup"><span data-stu-id="a4b8b-104">About Updatable Help</span></span>

## <a name="short-description"></a><span data-ttu-id="a4b8b-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="a4b8b-105">Short description</span></span>
<span data-ttu-id="a4b8b-106">Descreve o sistema de ajuda atualizável no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-106">Describes the updatable help system in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="a4b8b-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="a4b8b-107">Long description</span></span>

<span data-ttu-id="a4b8b-108">O PowerShell fornece várias maneiras diferentes de acessar os tópicos de ajuda mais atualizados para os cmdlets e conceitos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-108">PowerShell provides several different ways to access the most up-to-date help topics for PowerShell cmdlets and concepts.</span></span>

<span data-ttu-id="a4b8b-109">O sistema de ajuda atualizável, introduzido no PowerShell 3,0, foi projetado para garantir que você sempre tenha os tópicos mais recentes de ajuda em seu computador local para que você possa lê-los na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-109">The Updatable Help system, introduced in PowerShell 3.0, is designed to assure that you always have the newest help topics on your local computer so that you can read them at the command line.</span></span> <span data-ttu-id="a4b8b-110">Ele facilita baixar e instalar arquivos de ajuda e atualizá-los sempre que arquivos de ajuda mais recentes ficarem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-110">It makes it easy to download and install help files and to update them whenever newer help files become available.</span></span>

<span data-ttu-id="a4b8b-111">Para fornecer ajuda atualizada para vários computadores em uma empresa e para computadores que não têm acesso à Internet, a ajuda atualizável permite que você baixe arquivos de ajuda para um diretório de sistema de arquivos ou compartilhamento de arquivos e, em seguida, instale os arquivos de ajuda do compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-111">To provide updated help for multiple computers in an enterprise and for computers that do not have access to the internet, Updatable Help lets you download help files to a filesystem directory or file share, and then install the help files from the file share.</span></span>

<span data-ttu-id="a4b8b-112">No PowerShell 4,0, a propriedade **HelpInfoUri** é preservada pela comunicação remota do Windows PowerShell, que permite o `Save-Help` trabalho para os módulos instalados em um computador remoto, mas que não estão necessariamente instalados no computador local.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-112">In PowerShell 4.0, the **HelpInfoUri** property is preserved over Windows PowerShell remoting, which allows `Save-Help` to work for modules that are installed on a remote computer, but are not necessarily installed on the local computer.</span></span> <span data-ttu-id="a4b8b-113">Você pode salvar um objeto **PSModuleInfo** em disco ou mídia removível (como uma unidade USB) executando `Export-Clixml` em um computador que não tenha acesso à Internet, importando o objeto **PSModuleInfo** em um computador que tenha acesso à Internet e, em seguida, em execução `Save-Help` no objeto **PSModuleInfo** .</span><span class="sxs-lookup"><span data-stu-id="a4b8b-113">You can save a **PSModuleInfo** object to disk or removable media (such as a USB drive) by running `Export-Clixml` on a computer that does not have internet access, importing the **PSModuleInfo** object on a computer that does have internet access, and then running `Save-Help` on the **PSModuleInfo** object.</span></span> <span data-ttu-id="a4b8b-114">A ajuda salva pode ser copiada para o computador remoto, desconectado usando mídia removível e, em seguida, instalada executando `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="a4b8b-114">The saved help can be copied to the remote, disconnected computer by using removable media, and then installed by running `Update-Help`.</span></span> <span data-ttu-id="a4b8b-115">Esses aprimoramentos na `Save-Help` funcionalidade permitem que você instale a ajuda em computadores sem qualquer tipo de acesso à rede.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-115">These improvements in `Save-Help` functionality let you install help on computers that are without any kind of network access.</span></span> <span data-ttu-id="a4b8b-116">Para obter um exemplo de como usar a nova `Save-Help` funcionalidade, consulte [como atualizar a ajuda de um compartilhamento de arquivos](#how-to-update-help-from-a-file-share) neste tópico.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-116">For an example of how to use the new `Save-Help` functionality, see [How to update help from a file share](#how-to-update-help-from-a-file-share) in this topic.</span></span>

<span data-ttu-id="a4b8b-117">A ajuda atualizável também dá suporte ao acesso online aos tópicos mais recentes de ajuda e à ajuda básica para cmdlets, mesmo quando não há arquivos de ajuda no computador.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-117">Updatable Help also supports online access to the newest help topics and basic help for cmdlets, even when there are no help files on the computer.</span></span>

<span data-ttu-id="a4b8b-118">O PowerShell 3,0 não vem com arquivos de ajuda.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-118">PowerShell 3.0 does not come with Help files.</span></span> <span data-ttu-id="a4b8b-119">Você pode usar o recurso de ajuda atualizável para instalar os arquivos de ajuda para todos os comandos que estão incluídos por padrão no PowerShell e em todos os módulos do Windows.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-119">You can use the Updatable Help feature to install the help files for all of the commands that are included by default in PowerShell and for all Windows modules.</span></span>

## <a name="updatable-help-cmdlets"></a><span data-ttu-id="a4b8b-120">Cmdlets de ajuda atualizáveis</span><span class="sxs-lookup"><span data-stu-id="a4b8b-120">Updatable help cmdlets</span></span>

- <span data-ttu-id="a4b8b-121">`Update-Help`: Baixa os arquivos de ajuda mais recentes da Internet ou de um compartilhamento de arquivos e os instala no computador local.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-121">`Update-Help`: Downloads the newest help files from the internet or a file share, and installs them on the local computer.</span></span>

- <span data-ttu-id="a4b8b-122">`Save-Help`: Baixa os arquivos de ajuda mais recentes da Internet e os salva em um diretório do sistema de arquivos ou compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-122">`Save-Help`: Downloads the newest help files from the internet and saves them in a filesystem directory or file share.</span></span> <span data-ttu-id="a4b8b-123">Para instalar os arquivos de ajuda nos computadores, use o `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="a4b8b-123">To install the help files on computers, use `Update-Help`.</span></span>

- <span data-ttu-id="a4b8b-124">`Get-Help`: Exibe tópicos da ajuda na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-124">`Get-Help`: Displays help topics at the command line.</span></span> <span data-ttu-id="a4b8b-125">Obtém ajuda dos arquivos de ajuda no computador.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-125">Gets help from the help files on the computer.</span></span> <span data-ttu-id="a4b8b-126">Exibe a ajuda gerada automaticamente para cmdlets e funções que não têm arquivos de ajuda.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-126">Displays auto-generated help for cmdlets and functions that do not have help files.</span></span> <span data-ttu-id="a4b8b-127">Abre tópicos de ajuda online para cmdlets, funções, scripts e fluxos de trabalho em seu navegador de Internet padrão.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-127">Opens online help topics for cmdlets, functions, scripts, and workflows in your default internet browser.</span></span>

## <a name="update-help-in-the-powershell-ise"></a><span data-ttu-id="a4b8b-128">Atualizar a ajuda no ISE do PowerShell</span><span class="sxs-lookup"><span data-stu-id="a4b8b-128">Update help in the PowerShell ISE</span></span>

<span data-ttu-id="a4b8b-129">Você também pode atualizar a ajuda usando o item de **ajuda atualizar o PowerShell** no menu ajuda no ISE (ambiente de script integrado) do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-129">You can also update help by using the **Update PowerShell Help** item in the Help menu in PowerShell Integrated Scripting Environment (ISE).</span></span>

<span data-ttu-id="a4b8b-130">O item de **ajuda atualizar o PowerShell** executa um `Update-Help` comando sem parâmetros.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-130">The **Update PowerShell Help** item runs an `Update-Help` command without parameters.</span></span>

## <a name="auto-generated-help-help-without-help-files"></a><span data-ttu-id="a4b8b-131">Ajuda gerada automaticamente: ajuda sem arquivos de ajuda</span><span class="sxs-lookup"><span data-stu-id="a4b8b-131">Auto-generated help: help without help files</span></span>

<span data-ttu-id="a4b8b-132">Se você não tiver o arquivo de ajuda para um cmdlet, uma função ou um fluxo de trabalho no computador, o `Get-Help` cmdlet exibirá a ajuda gerada automaticamente e solicitará que você baixe os arquivos de ajuda ou os Leia online.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-132">If you do not have the help file for a cmdlet, function, or workflow on the computer, the `Get-Help` cmdlet displays auto-generated help and prompts you to download the help files or read them online.</span></span>

<span data-ttu-id="a4b8b-133">A ajuda gerada automaticamente inclui sintaxe e aliases, e comentários que explicam como usar os cmdlets de ajuda atualizáveis e para acessar os tópicos da ajuda online.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-133">Auto-generated help includes syntax and aliases, and remarks that explain how to use the Updatable Help cmdlets and to access the online help topics.</span></span>

<span data-ttu-id="a4b8b-134">Por exemplo, o comando a seguir obtém a ajuda básica para o `Get-Culture` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-134">For example, the following command gets basic help for the `Get-Culture` cmdlet.</span></span> <span data-ttu-id="a4b8b-135">A saída mostra a `Get-Help` exibição quando não há arquivos de ajuda no computador.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-135">The output shows the `Get-Help` display when there are no help files on the computer.</span></span>

```powershell
Get-Help Get-Culture
```

```output
NAME
    Get-Culture

SYNTAX
    Get-Culture [<CommonParameters>]

ALIASES
    None

REMARKS
    To get the latest Help content including descriptions and examples
    type: Update-Help.
```

## <a name="help-files-for-modules"></a><span data-ttu-id="a4b8b-136">Arquivos de ajuda para módulos</span><span class="sxs-lookup"><span data-stu-id="a4b8b-136">Help files for modules</span></span>

<span data-ttu-id="a4b8b-137">A menor unidade de ajuda atualizável é a ajuda para um módulo.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-137">The smallest unit of Updatable Help is help for a module.</span></span> <span data-ttu-id="a4b8b-138">A ajuda do módulo inclui ajuda para todos os cmdlets, funções, fluxos de trabalho, provedores, scripts e conceitos em um módulo.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-138">Module help includes help for all of the cmdlets, functions, workflows, providers, scripts, and concepts in a module.</span></span> <span data-ttu-id="a4b8b-139">Você pode atualizar a ajuda para todos os módulos que estão instalados no computador, mesmo que eles não sejam importados para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-139">You can update help for all modules that are installed on the computer, even if they are not imported into the current session.</span></span>

<span data-ttu-id="a4b8b-140">Você pode atualizar a ajuda para o módulo inteiro, mas não pode atualizar a ajuda para cmdlets individuais.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-140">You can update help for the entire module, but you cannot update help for individual cmdlets.</span></span>

<span data-ttu-id="a4b8b-141">Para localizar o módulo que contém um cmdlet específico, use o seguinte formato de comando:</span><span class="sxs-lookup"><span data-stu-id="a4b8b-141">To find the module that contains a particular cmdlet, use the following command format:</span></span>

```powershell
(Get-Command <cmdlet-name>).ModuleName
```

<span data-ttu-id="a4b8b-142">Por exemplo, para localizar o módulo que contém o `Set-ExecutionPolicy` cmdlet, digite:</span><span class="sxs-lookup"><span data-stu-id="a4b8b-142">For example, to find the module that contains the `Set-ExecutionPolicy` cmdlet, type:</span></span>

```powershell
(Get-Command Set-ExecutionPolicy).ModuleName
```

<span data-ttu-id="a4b8b-143">Para atualizar a ajuda para um módulo específico, digite:</span><span class="sxs-lookup"><span data-stu-id="a4b8b-143">To update help for a particular module, type:</span></span>

```powershell
Update-Help -Module <ModuleName>
```

<span data-ttu-id="a4b8b-144">Por exemplo, para atualizar a ajuda para o módulo que contém o cmdlet Set-ExecutionPolicy, digite:</span><span class="sxs-lookup"><span data-stu-id="a4b8b-144">For example, to update help for the module that contains the Set-ExecutionPolicy cmdlet, type:</span></span>

```powershell
Update-Help -Module Microsoft.PowerShell.Security
```

## <a name="permissions-for-updatable-help"></a><span data-ttu-id="a4b8b-145">Permissões para ajuda atualizável</span><span class="sxs-lookup"><span data-stu-id="a4b8b-145">Permissions for updatable help</span></span>

<span data-ttu-id="a4b8b-146">Para atualizar a ajuda para os módulos no diretório `$pshome/Modules` , você deve ser membro do grupo Administradores no computador.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-146">To update help for the modules in the directory `$pshome/Modules`, you must be member of the Administrators group on the computer.</span></span>

<span data-ttu-id="a4b8b-147">Se você não for um membro do grupo Administradores, não poderá atualizar a ajuda para esses módulos; Mas se você tiver acesso à Internet, poderá exibir a ajuda online.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-147">If you are not a member of the Administrators group, you cannot update help for these modules; but if you have internet access, you can view help online.</span></span>

<span data-ttu-id="a4b8b-148">A atualização da ajuda para módulos no diretório `$home/Documents/PowerShell/Modules` ou módulos em outros subdiretórios do `$home` diretório não requer permissões especiais.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-148">Updating help for modules in the directory `$home/Documents/PowerShell/Modules` or modules in other subdirectories of the `$home` directory does not require special permissions.</span></span>

<span data-ttu-id="a4b8b-149">Os `Update-Help` `Save-Help` cmdlets e têm um parâmetro **UseDefaultCredentials** que fornece as credenciais explícitas do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-149">The `Update-Help` and `Save-Help` cmdlets have a **UseDefaultCredentials** parameter that provides the explicit credentials of the current user.</span></span> <span data-ttu-id="a4b8b-150">Esse parâmetro foi projetado para acessar locais seguros da Internet.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-150">This parameter is designed for accessing secure internet locations.</span></span>

<span data-ttu-id="a4b8b-151">Os `Update-Help` `Save-Help` cmdlets e também têm um parâmetro **Credential** que permite executar o comando em um computador remoto e acessar um compartilhamento de arquivos em um terceiro computador.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-151">The `Update-Help` and `Save-Help` cmdlets also have a **Credential** parameter that allows you to run the command on a remote computer and access a file share on a third computer.</span></span> <span data-ttu-id="a4b8b-152">O parâmetro **Credential** é válido somente quando você usa os parâmetros SourcePath ou **LiteralPath** de `Update-Help` e os parâmetros **DestinationPath** ou **LiteralPath** de `Save-Help` .</span><span class="sxs-lookup"><span data-stu-id="a4b8b-152">The **Credential** parameter is valid only when you use the SourcePath or **LiteralPath** parameters of `Update-Help` and the **DestinationPath** or **LiteralPath** parameters of `Save-Help`.</span></span>

## <a name="how-to-install-and-update-help-files"></a><span data-ttu-id="a4b8b-153">Como instalar e atualizar arquivos de ajuda</span><span class="sxs-lookup"><span data-stu-id="a4b8b-153">How to install and update help files</span></span>

<span data-ttu-id="a4b8b-154">Para baixar e instalar arquivos de ajuda pela primeira vez ou para atualizar os arquivos de ajuda em seu computador, use o `Update-Help` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-154">To download and install help files for the first time, or to update the help files on your computer, use the `Update-Help` cmdlet.</span></span>

<span data-ttu-id="a4b8b-155">O `Update-Help` cmdlet faz todo o trabalho árduo para você, incluindo as tarefas a seguir.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-155">The `Update-Help` cmdlet does all of the hard work for you, including the following tasks.</span></span>

- <span data-ttu-id="a4b8b-156">Determina quais módulos dão suporte à ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-156">Determines which modules support Updatable Help.</span></span>
- <span data-ttu-id="a4b8b-157">Localiza o local da Internet onde cada módulo armazena seus arquivos de ajuda atualizáveis.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-157">Finds the internet location where each module stores its Updatable Help files.</span></span>
- <span data-ttu-id="a4b8b-158">Compara os arquivos de ajuda de cada módulo em seu computador com os arquivos de ajuda mais recentes que estão disponíveis para cada módulo.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-158">Compares the help files for each module on your computer to the newest help files that are available for each module.</span></span>
- <span data-ttu-id="a4b8b-159">Baixa os novos arquivos da Internet.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-159">Downloads the new files from the internet.</span></span>
- <span data-ttu-id="a4b8b-160">Desencapsula o pacote do arquivo de ajuda.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-160">Unwraps the help file package.</span></span>
- <span data-ttu-id="a4b8b-161">Verifica se os arquivos são arquivos de ajuda válidos.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-161">Verifies that the files are valid help files.</span></span>
- <span data-ttu-id="a4b8b-162">Instala os arquivos de ajuda no subdiretório específico do idioma do diretório do módulo.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-162">Installs the help files in the language-specific subdirectory of the module directory.</span></span>

<span data-ttu-id="a4b8b-163">Para acessar os novos tópicos da ajuda, use o `Get-Help` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-163">To access the new help topics, use the `Get-Help` cmdlet.</span></span> <span data-ttu-id="a4b8b-164">Você não precisa reiniciar o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-164">You do not need to restart PowerShell.</span></span>

<span data-ttu-id="a4b8b-165">Para instalar ou atualizar a ajuda para todos os módulos no computador que oferece suporte à ajuda atualizável, digite:</span><span class="sxs-lookup"><span data-stu-id="a4b8b-165">To install or update help for all modules on the computer that supports Updatable Help, type:</span></span>

```powershell
Update-Help
```

<span data-ttu-id="a4b8b-166">Para atualizar a ajuda para determinados módulos, adicione o parâmetro **Module** de `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="a4b8b-166">To update help for particular modules, add the **Module** parameter of `Update-Help`.</span></span> <span data-ttu-id="a4b8b-167">Caracteres curinga são permitidos no nome do módulo.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-167">Wildcard characters are permitted in the module name.</span></span>

<span data-ttu-id="a4b8b-168">Por exemplo, para atualizar a ajuda para o módulo ServerManager, digite:</span><span class="sxs-lookup"><span data-stu-id="a4b8b-168">For example, to update help for the ServerManager module, type:</span></span>

```powershell
Update-Help -Module ServerManager
```

<span data-ttu-id="a4b8b-169">Sem parâmetros, o `Update-Help` atualiza a ajuda para todos os módulos na sessão e para todos os módulos instalados que dão suporte à ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-169">Without parameters, `Update-Help` updates help for all modules in the session and for all installed modules that support Updatable Help.</span></span> <span data-ttu-id="a4b8b-170">Para serem incluídos, os módulos devem ser instalados em diretórios listados no valor da variável de ambiente PSModulePath.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-170">To be included, modules must be installed in directories that are listed in the value of the PSModulePath environment variable.</span></span> <span data-ttu-id="a4b8b-171">Esses são também módulos que são retornados por um comando "Get-Help-ListAvailable".</span><span class="sxs-lookup"><span data-stu-id="a4b8b-171">These are also modules that are returned by a "Get-Help -ListAvailable" command.</span></span>

<span data-ttu-id="a4b8b-172">Se o valor do parâmetro do **módulo** for `*` (All), o `Update-Help` tentará atualizar a ajuda para todos os módulos instalados, incluindo módulos que não dão suporte à ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-172">If the value of the **Module** parameter is `*` (all), `Update-Help` attempts to update help for all installed modules, including modules that do not support Updatable Help.</span></span> <span data-ttu-id="a4b8b-173">Esse comando normalmente gera muitos erros, pois o cmdlet encontra módulos que não oferecem suporte à ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-173">This command typically generates many errors as the cmdlet encounters modules that do not support Updatable Help.</span></span>

## <a name="how-to-update-help-from-a-file-share"></a><span data-ttu-id="a4b8b-174">Como atualizar a ajuda de um compartilhamento de arquivos</span><span class="sxs-lookup"><span data-stu-id="a4b8b-174">How to update help from a file share</span></span>

<span data-ttu-id="a4b8b-175">Para dar suporte a computadores que não estão conectados à Internet ou para controlar ou simplificar a atualização em uma empresa, use o `Save-Help` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-175">To support computers that are not connected to the internet, or to control or streamline help updating in an enterprise, use the `Save-Help` cmdlet.</span></span> <span data-ttu-id="a4b8b-176">O `Save-Help` cmdlet baixa os arquivos de ajuda da Internet e os salva em um diretório FileSystem que você especificar.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-176">The `Save-Help` cmdlet downloads help files from the internet and saves them in a filesystem directory that you specify.</span></span>

<span data-ttu-id="a4b8b-177">`Save-Help` compara os arquivos de ajuda no diretório especificado com os arquivos de ajuda mais recentes que estão disponíveis para cada módulo.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-177">`Save-Help` compares the help files in the specified directory to the newest help files that are available for each module.</span></span> <span data-ttu-id="a4b8b-178">Se o diretório não tiver arquivos de ajuda ou arquivos de ajuda mais recentes estiverem disponíveis para o módulo, o `Save-Help` cmdlet baixará os novos arquivos da Internet.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-178">If the directory has no help files or newer help files are available for the module, the `Save-Help` cmdlet downloads the new files from the internet.</span></span> <span data-ttu-id="a4b8b-179">No entanto, ele não desencapsula ou instala os arquivos da ajuda.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-179">However, it does not unwrap or install the help files.</span></span>

<span data-ttu-id="a4b8b-180">Para instalar ou atualizar os arquivos de ajuda em um computador a partir de arquivos de ajuda que foram salvos em um diretório de sistema de arquivos, use o parâmetro **SourcePath** do `Update-Help` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-180">To install or update the help files on a computer from help files that were saved to a filesystem directory, use the **SourcePath** parameter of the `Update-Help` cmdlet.</span></span> <span data-ttu-id="a4b8b-181">O `Update-Help` cmdlet identifica os arquivos de ajuda mais recentes, desencapsula e valida-os e os instala nos subdiretórios específicos do idioma dos diretórios de módulo.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-181">The `Update-Help` cmdlet identifies the newest help files, unwraps and validates them, and installs them in the language-specific subdirectories of the module directories.</span></span>

<span data-ttu-id="a4b8b-182">Por exemplo, para salvar a ajuda para todos os módulos instalados no `\\Server\Share` diretório, digite:</span><span class="sxs-lookup"><span data-stu-id="a4b8b-182">For example, to save help for all installed modules to the `\\Server\Share` directory, type:</span></span>

```powershell
Save-Help -DestinationPath \\Server\Share
```

<span data-ttu-id="a4b8b-183">Em seguida, para atualizar a ajuda do `\\Server\Share` diretório, digite:</span><span class="sxs-lookup"><span data-stu-id="a4b8b-183">Then, to update help from the `\\Server\Share` directory, type:</span></span>

```powershell
Update-Help -SourcePath \\Server\Share
```

<span data-ttu-id="a4b8b-184">Os exemplos a seguir mostram o uso de `Save-Help` para salvar a ajuda para módulos que não estão instalados no computador local.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-184">The following examples show the use of `Save-Help` to save help for modules that are not installed on the local computer.</span></span> <span data-ttu-id="a4b8b-185">Neste exemplo, o administrador é executado `Save-Help` para salvar a ajuda do módulo dhcpserver de um computador cliente conectado à Internet, sem instalar o módulo dhcpserver ou a função de servidor DHCP no computador local.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-185">In this example, the administrator runs `Save-Help` to save the help for the DhcpServer module from an internet-connected client computer, without installing the DhcpServer module or DHCP Server role on the local computer.</span></span>

<span data-ttu-id="a4b8b-186">Opção 1: executar `Invoke-Command` para obter o objeto **PSModuleInfo** para o módulo remoto, salvá-lo em uma variável, `$m` e, em seguida, executar `Save-Help` no objeto **PSModuleInfo** especificando a variável `$m` como o nome do módulo.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-186">Option 1: Run `Invoke-Command` to get the **PSModuleInfo** object for the remote module, save it in a variable, `$m`, and then run `Save-Help` on the **PSModuleInfo** object by specifying the variable `$m` as the module name.</span></span>

```powershell
$m = Invoke-Command -ComputerName RemoteServer -ScriptBlock
{ Get-Module -Name DhcpServer -ListAvailable }
Save-Help -Module $m -DestinationPath C:\SavedHelp
```

<span data-ttu-id="a4b8b-187">Opção 2: Abra uma PSSession direcionada ao computador que está executando o módulo do servidor DHCP, para obter o objeto **PSModuleInfo** para o módulo, salve-o em uma variável `$m` e, em seguida, execute `Save-Help` no objeto que é salvo na `$m` variável.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-187">Option 2: Open a PSSession targeted at the computer that is running the DHCP Server module, to get the **PSModuleInfo** object for the module, save it in a variable `$m`, and then run `Save-Help` on the object that is saved in the `$m` variable.</span></span>

```powershell
$s = New-PSSession -ComputerName RemoteServer
$m = Get-Module -PSSession $s -Name DhcpServer -ListAvailable
Save-Help -Module $m -DestinationPath C:\SavedHelp
```

<span data-ttu-id="a4b8b-188">Opção 3: Abra uma sessão CIM, direcionada ao computador que está executando o módulo do servidor DHCP, para obter o objeto **PSModuleInfo** para o módulo, salvá-lo em uma variável `$m` e, em seguida, executar `Save-Help` no objeto que é salvo na `$m` variável.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-188">Option 3: Open a CIM session, targeted at the computer that is running the DHCP Server module, to get the **PSModuleInfo** object for the module, save it in a variable `$m`, and then run `Save-Help` on the object that is saved in the `$m` variable.</span></span>

```powershell
$c = New-CimSession -ComputerName RemoteServer
$m = Get-Module -CimSession $c -Name DhcpServer -ListAvailable
Save-Help -Module $m -DestinationPath C:\SavedHelp
```

<span data-ttu-id="a4b8b-189">No exemplo a seguir, o administrador instala a ajuda para o módulo do servidor DHCP em um computador que não tem acesso à rede.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-189">In the following example, the administrator installs help for the DHCP Server module on a computer that does not have network access.</span></span>

<span data-ttu-id="a4b8b-190">Primeiro, execute `Export-Clixml` para exportar o objeto **PSModuleInfo** para uma pasta compartilhada ou para uma mídia removível.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-190">First, run `Export-Clixml` to export the **PSModuleInfo** object to a shared folder or to removable media.</span></span>

```powershell
$m = Get-Module -Name DhcpServer -ListAvailable
Export-Clixml -Path E:\UsbFlashDrive\DhcpModule.xml -InputObject $m
```

<span data-ttu-id="a4b8b-191">Em seguida, transporte a mídia removível para um computador que tenha acesso à Internet e, em seguida, importe o objeto **PSModuleInfo** com `Import-Clixml` .</span><span class="sxs-lookup"><span data-stu-id="a4b8b-191">Next, transport the removable media to a computer that has internet access, and then import the **PSModuleInfo** object with `Import-Clixml`.</span></span> <span data-ttu-id="a4b8b-192">Execute `Save-Help` para salvar a ajuda para o objeto de **PSModuleInfo** do módulo do DhcpServer importado.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-192">Run `Save-Help` to save the Help for the imported DhcpServer module **PSModuleInfo** object.</span></span>

```powershell
$deserialized_m = Import-Clixml E:\UsbFlashDrive\DhcpModule.xml
Save-Help -Module $deserialized_m -DestinationPath E:\UsbFlashDrive\SavedHelp
```

<span data-ttu-id="a4b8b-193">Por fim, transporte a mídia removível de volta para o computador que não tem acesso à rede e, em seguida, instale a ajuda executando `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="a4b8b-193">Finally, transport the removable media back to the computer that does not have network access, and then install the help by running `Update-Help`.</span></span>

```powershell
Update-Help -Module DhcpServer -SourcePath E:\UsbFlashDrive\SavedHelp
```

<span data-ttu-id="a4b8b-194">Sem parâmetros, o `Save-Help` baixa ajuda para todos os módulos na sessão e para todos os módulos instalados que dão suporte à ajuda atualizável.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-194">Without parameters, `Save-Help` downloads help for all modules in the session and for all installed modules that support Updatable Help.</span></span> <span data-ttu-id="a4b8b-195">Para serem incluídos, os módulos devem ser instalados em diretórios listados no valor da `$env:PSModulePath` variável de ambiente, no computador local ou em um computador remoto para o qual você deseja salvar a ajuda.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-195">To be included, modules must be installed in directories that are listed in the value of the `$env:PSModulePath` environment variable, on either the local computer or on a remote computer for which you want to save help.</span></span> <span data-ttu-id="a4b8b-196">Esses também são módulos que são retornados pela execução de um `Get-Help -ListAvailable` comando.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-196">These are also modules that are returned by running a `Get-Help -ListAvailable` command.</span></span>

## <a name="how-to-update-help-files-in-different-languages"></a><span data-ttu-id="a4b8b-197">Como atualizar arquivos de ajuda em diferentes idiomas</span><span class="sxs-lookup"><span data-stu-id="a4b8b-197">How to update help files in different languages</span></span>

<span data-ttu-id="a4b8b-198">Por padrão, os `Update-Help` `Save-Help` cmdlets e baixam a ajuda na cultura da interface do usuário e no idioma definido para o Windows no computador local.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-198">By default, the `Update-Help` and `Save-Help` cmdlets download help in the UI culture and language that is set for Windows on the local computer.</span></span> <span data-ttu-id="a4b8b-199">Se os arquivos de ajuda para os módulos especificados não estiverem disponíveis na cultura da interface do usuário local, `Update-Help` `Save-Help` use as regras de fallback de idioma do Windows para encontrar o melhor idioma com suporte.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-199">If help files for the specified modules are not available in the local UI culture, `Update-Help` and `Save-Help` use the Windows language fallback rules to find the best supported language.</span></span>

<span data-ttu-id="a4b8b-200">No entanto, você pode **UICulture** usar os parâmetros UICulture `Update-Help` dos `Save-Help` cmdlets e para baixar e instalar arquivos de ajuda em qualquer cultura de interface do usuário na qual eles estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-200">However, you can use the **UICulture** parameters of the `Update-Help` and `Save-Help` cmdlets to download and install help files in any UI cultures in which they are available.</span></span>

<span data-ttu-id="a4b8b-201">Por exemplo, para salvar os arquivos de ajuda mais recentes para todos os módulos na sessão em Japonês (ja-JP) e francês (fr-FR), digite:</span><span class="sxs-lookup"><span data-stu-id="a4b8b-201">For example, to save the newest help files for all modules on the session in Japanese (Ja-jp) and French (fr-FR), type:</span></span>

```powershell
Save-Help -Path \Server\Share -UICulture ja-jp, fr-fr
```

<span data-ttu-id="a4b8b-202">Se os arquivos de ajuda para os módulos não estiverem disponíveis nos idiomas que você especificou, os `Update-Help` `Save-Help` cmdlets e retornarão uma mensagem de erro que lista os idiomas nos quais a ajuda para cada módulo está disponível para que você possa escolher a alternativa que melhor atenda às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-202">If help files for the modules are not available in the languages that you specified, the `Update-Help` and `Save-Help` cmdlets return an error message that lists the languages in which help for each module is available so you can choose the alternative that best meets your needs.</span></span>

> [!NOTE]
> <span data-ttu-id="a4b8b-203">Atualmente, o conteúdo da ajuda atualizável só é publicado em inglês (en-US).</span><span class="sxs-lookup"><span data-stu-id="a4b8b-203">Currently, Updateable Help content is only published in English (en-US).</span></span>

## <a name="how-to-use-online-help"></a><span data-ttu-id="a4b8b-204">Como usar a ajuda online</span><span class="sxs-lookup"><span data-stu-id="a4b8b-204">How to use online help</span></span>

<span data-ttu-id="a4b8b-205">Se você não puder ou optar por não atualizar os arquivos de ajuda no computador local, ainda poderá obter os arquivos de ajuda mais recentes online.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-205">If you cannot or choose not to update the help files on your local computer, you can still get the newest help files online.</span></span>

<span data-ttu-id="a4b8b-206">Para abrir o tópico da ajuda online para qualquer cmdlet ou função, use o parâmetro **online** do `Get-Help` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-206">To open the online help topic for any cmdlet or function, use the **Online** parameter of the `Get-Help` cmdlet.</span></span>

<span data-ttu-id="a4b8b-207">Por exemplo, o comando a seguir abre o tópico de ajuda online para o `Get-Job` cmdlet em seu navegador de Internet padrão:</span><span class="sxs-lookup"><span data-stu-id="a4b8b-207">For example, the following command opens the online help topic for the `Get-Job` cmdlet in your default internet browser:</span></span>

```powershell
Get-Help Get-Job -Online
```

<span data-ttu-id="a4b8b-208">Para obter ajuda online para um script, use o parâmetro **online** e o caminho completo para o script.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-208">To get online help for a script, use the **Online** parameter and the full path to the script.</span></span>

<span data-ttu-id="a4b8b-209">O parâmetro **online** não funciona com tópicos about.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-209">The **Online** parameter does not work with About topics.</span></span> <span data-ttu-id="a4b8b-210">Para ver os tópicos sobre do PowerShell, incluindo tópicos de ajuda sobre a linguagem do PowerShell, confira [tópicos sobre o PowerShell](about.md).</span><span class="sxs-lookup"><span data-stu-id="a4b8b-210">To see the about topics for PowerShell, including help topics about the PowerShell language, see [PowerShell About Topics](about.md).</span></span>

## <a name="how-to-minimize-or-prevent-internet-downloads"></a><span data-ttu-id="a4b8b-211">Como minimizar ou impedir downloads da Internet</span><span class="sxs-lookup"><span data-stu-id="a4b8b-211">How to minimize or prevent internet downloads</span></span>

<span data-ttu-id="a4b8b-212">Para minimizar os downloads da Internet e fornecer ajuda atualizável aos usuários que não estão conectados à Internet, use o `Save-Help` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-212">To minimize internet downloads and provide Updatable Help to users who are not connected to the internet, use the `Save-Help` cmdlet.</span></span> <span data-ttu-id="a4b8b-213">Baixe a ajuda da Internet e salve-a em um compartilhamento de rede.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-213">Download help from the internet and save it to a network share.</span></span> <span data-ttu-id="a4b8b-214">Em seguida, crie uma configuração de Política de Grupo ou um trabalho agendado que execute um `Update-Help` comando em todos os computadores.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-214">Then, create a Group Policy setting or scheduled job that runs an `Update-Help` command on all computers.</span></span> <span data-ttu-id="a4b8b-215">Defina o valor do parâmetro **SourcePath** do `Update-Help` cmdlet para o compartilhamento de rede.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-215">Set the value of the **SourcePath** parameter of the `Update-Help` cmdlet to the network share.</span></span>

<span data-ttu-id="a4b8b-216">Para impedir que os usuários com acesso à Internet Baixem a ajuda atualizável da Internet, use a configuração **definir o caminho de origem padrão para Update-help** política de grupo.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-216">To prevent users who have internet access from downloading Updatable Help from the internet, use the **Set the default source path for Update-Help** Group Policy setting.</span></span>

<span data-ttu-id="a4b8b-217">Essa configuração de Política de Grupo adiciona implicitamente o parâmetro **SourcePath** , com o local do sistema de arquivos que você especifica, a cada `Update-Help` comando em cada computador afetado.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-217">This Group Policy setting implicitly adds the **SourcePath** parameter, with the filesystem location that you specify, to every `Update-Help` command on every affected computer.</span></span> <span data-ttu-id="a4b8b-218">Os usuários podem usar o parâmetro **SourcePath** explicitamente para especificar um local de sistema de arquivos diferente, mas não podem excluir o parâmetro **SourcePath** e baixar a ajuda da Internet.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-218">Users can use the **SourcePath** parameter explicitly to specify a different filesystem location, but they cannot exclude the **SourcePath** parameter and download help from the internet.</span></span>

> [!NOTE]
> <span data-ttu-id="a4b8b-219">A configuração da política de grupo **definir o caminho de origem padrão para a atualização-ajuda** é exibida em **configuração do computador** e **configuração do usuário** .</span><span class="sxs-lookup"><span data-stu-id="a4b8b-219">The **Set the default source path for Update-Help** group policy setting appears under **Computer Configuration** and **User Configuration** .</span></span> <span data-ttu-id="a4b8b-220">No entanto, somente a configuração de política em **configuração do computador** é eficaz.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-220">However, only the policy setting under **Computer Configuration** is effective.</span></span> <span data-ttu-id="a4b8b-221">A configuração de política em **configuração do usuário** é ignorada.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-221">The policy setting under **User Configuration** is ignored.</span></span>

<span data-ttu-id="a4b8b-222">Confira mais informações em [about_Group_Policy_Settings](about_Group_Policy_Settings.md).</span><span class="sxs-lookup"><span data-stu-id="a4b8b-222">For more information, see [about_Group_Policy_Settings](about_Group_Policy_Settings.md).</span></span>

## <a name="how-to-update-help-for-non-standard-modules"></a><span data-ttu-id="a4b8b-223">Como atualizar a ajuda para módulos não padrão</span><span class="sxs-lookup"><span data-stu-id="a4b8b-223">How to update help for non-standard modules</span></span>

<span data-ttu-id="a4b8b-224">Para atualizar ou salvar a ajuda para um módulo que não é retornado pelo parâmetro **listAvailable** do `Get-Module` cmdlet, importe o módulo para a sessão atual antes de executar um `Update-Help` comando ou `Save-Help` .</span><span class="sxs-lookup"><span data-stu-id="a4b8b-224">To update or save help for a module that is not returned by the **ListAvailable** parameter of the `Get-Module` cmdlet, import the module into the current session before running an `Update-Help` or `Save-Help` command.</span></span> <span data-ttu-id="a4b8b-225">Em um computador remoto, antes de executar o `Save-Help` comando, importe o módulo para a sessão atual ou o `Invoke-Command` bloco de script que está conectado ao computador remoto.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-225">On a remote computer, before running the `Save-Help` command, import the module into the current Session, or `Invoke-Command` script block, that is connected to the remote computer.</span></span>

<span data-ttu-id="a4b8b-226">Quando o módulo estiver na sessão atual, execute os `Update-Help` `Save-Help` cmdlets ou sem parâmetros ou use o parâmetro **Module** para especificar o nome do módulo.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-226">When the module is in the current session, run the `Update-Help` or `Save-Help` cmdlets without parameters, or use the **Module** parameter to specify the module name.</span></span>

<span data-ttu-id="a4b8b-227">Os parâmetros de **módulo** dos `Update-Help` `Save-Help` cmdlets e aceitam apenas um nome de módulo.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-227">The **Module** parameters of the `Update-Help` and `Save-Help` cmdlets accept only a module name.</span></span> <span data-ttu-id="a4b8b-228">Eles não aceitam o caminho para um arquivo de módulo.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-228">They do not accept the path to a module file.</span></span>

<span data-ttu-id="a4b8b-229">Use essa técnica para atualizar ou salvar a ajuda para qualquer módulo que não seja retornado pelo parâmetro **listAvailable** do `Get-Module` cmdlet, como um módulo instalado em um local que não esteja listado na variável de `$env:PSModulePath` ambiente ou um módulo que não esteja bem formado (o diretório do módulo não contém pelo menos um arquivo cujo basename seja o mesmo que o nome do diretório).</span><span class="sxs-lookup"><span data-stu-id="a4b8b-229">Use this technique to update or save help for any module that is not returned by the **ListAvailable** parameter of the `Get-Module` cmdlet, such as a module that is installed in a location that is not listed in the `$env:PSModulePath` environment variable, or a module that is not well-formed (the module directory does not contain at least one file whose basename is the same as the directory name).</span></span>

## <a name="how-to-support-updatable-help"></a><span data-ttu-id="a4b8b-230">Como dar suporte à ajuda atualizável</span><span class="sxs-lookup"><span data-stu-id="a4b8b-230">How to support updatable help</span></span>

<span data-ttu-id="a4b8b-231">Se você criar um módulo, poderá dar suporte à ajuda online e à ajuda atualizável para seus módulos.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-231">If you author a module, you can support online help and Updatable Help for your modules.</span></span> <span data-ttu-id="a4b8b-232">Para obter mais informações, consulte [dando suporte à ajuda atualizável](/powershell/scripting/developer/help/supporting-updatable-help) e [suporte à ajuda online](/powershell/scripting/developer/module/supporting-online-help) no Microsoft docs.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-232">For more information, see [Supporting Updatable Help](/powershell/scripting/developer/help/supporting-updatable-help) and [Supporting Online Help](/powershell/scripting/developer/module/supporting-online-help) in the Microsoft Docs.</span></span>

<span data-ttu-id="a4b8b-233">Ajuda atualizável não disponível para snap-ins do PowerShell ou ajuda baseada em comentários.</span><span class="sxs-lookup"><span data-stu-id="a4b8b-233">Updatable help not available for PowerShell snap-ins or comment-based help.</span></span>

## <a name="remarks"></a><span data-ttu-id="a4b8b-234">Comentários</span><span class="sxs-lookup"><span data-stu-id="a4b8b-234">Remarks</span></span>

<span data-ttu-id="a4b8b-235">`Update-Help` `Save-Help` Não há suporte para os cmdlets e no ambiente de pré-instalação do Windows (Windows PE).</span><span class="sxs-lookup"><span data-stu-id="a4b8b-235">The `Update-Help` and `Save-Help` cmdlets are not supported on Windows Preinstallation Environment (Windows PE).</span></span>

## <a name="see-also"></a><span data-ttu-id="a4b8b-236">Confira também</span><span class="sxs-lookup"><span data-stu-id="a4b8b-236">See also</span></span>

[<span data-ttu-id="a4b8b-237">Get-Help</span><span class="sxs-lookup"><span data-stu-id="a4b8b-237">Get-Help</span></span>](xref:Microsoft.PowerShell.Core.Get-Help)

[<span data-ttu-id="a4b8b-238">Save-Help</span><span class="sxs-lookup"><span data-stu-id="a4b8b-238">Save-Help</span></span>](xref:Microsoft.PowerShell.Core.Save-Help)

[<span data-ttu-id="a4b8b-239">Update-Help</span><span class="sxs-lookup"><span data-stu-id="a4b8b-239">Update-Help</span></span>](xref:Microsoft.PowerShell.Core.Update-Help)
