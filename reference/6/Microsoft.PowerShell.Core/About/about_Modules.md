---
description: Explica como instalar, importar e usar módulos do PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 09/15/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_modules?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Modules
ms.openlocfilehash: 9cd6cb2f8924c868cf4dc45ff322abbc53c07f19
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195709"
---
# <a name="about-modules"></a><span data-ttu-id="3428a-104">Sobre os módulos</span><span class="sxs-lookup"><span data-stu-id="3428a-104">About Modules</span></span>

## <a name="short-description"></a><span data-ttu-id="3428a-105">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="3428a-105">Short Description</span></span>
<span data-ttu-id="3428a-106">Explica como instalar, importar e usar módulos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3428a-106">Explains how to install, import, and use PowerShell modules.</span></span>

## <a name="long-description"></a><span data-ttu-id="3428a-107">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="3428a-107">Long Description</span></span>

<span data-ttu-id="3428a-108">Um módulo é um pacote que contém comandos do PowerShell, como cmdlets, provedores, funções, fluxos de trabalho, variáveis e aliases.</span><span class="sxs-lookup"><span data-stu-id="3428a-108">A module is a package that contains PowerShell commands, such as cmdlets, providers, functions, workflows, variables, and aliases.</span></span>

<span data-ttu-id="3428a-109">As pessoas que escrevem comandos podem usar módulos para organizar seus comandos e compartilhá-los com outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="3428a-109">People who write commands can use modules to organize their commands and share them with others.</span></span> <span data-ttu-id="3428a-110">As pessoas que recebem módulos podem adicionar os comandos nos módulos às suas sessões do PowerShell e usá-los exatamente como os comandos internos.</span><span class="sxs-lookup"><span data-stu-id="3428a-110">People who receive modules can add the commands in the modules to their PowerShell sessions and use them just like the built-in commands.</span></span>

<span data-ttu-id="3428a-111">Este tópico explica como usar os módulos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3428a-111">This topic explains how to use PowerShell modules.</span></span> <span data-ttu-id="3428a-112">Para obter informações sobre como escrever módulos do PowerShell, consulte [escrevendo um módulo do PowerShell](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span><span class="sxs-lookup"><span data-stu-id="3428a-112">For information about how to write PowerShell modules, see [Writing a PowerShell Module](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span></span>

## <a name="what-is-a-module"></a><span data-ttu-id="3428a-113">O que é um módulo?</span><span class="sxs-lookup"><span data-stu-id="3428a-113">What Is a Module?</span></span>

<span data-ttu-id="3428a-114">Um módulo é um pacote de comandos.</span><span class="sxs-lookup"><span data-stu-id="3428a-114">A module is a package of commands.</span></span> <span data-ttu-id="3428a-115">Todos os cmdlets e provedores em sua sessão são adicionados por um módulo ou um snap-in.</span><span class="sxs-lookup"><span data-stu-id="3428a-115">All cmdlets and providers in your session are added by a module or a snap-in.</span></span>

## <a name="module-auto-loading"></a><span data-ttu-id="3428a-116">Módulo de carregamento automático</span><span class="sxs-lookup"><span data-stu-id="3428a-116">Module Auto-Loading</span></span>

<span data-ttu-id="3428a-117">A partir do PowerShell 3,0, o PowerShell importa módulos automaticamente na primeira vez que você executa qualquer comando em um módulo instalado.</span><span class="sxs-lookup"><span data-stu-id="3428a-117">Beginning in PowerShell 3.0, PowerShell imports modules automatically the first time that you run any command in an installed module.</span></span> <span data-ttu-id="3428a-118">Agora você pode usar os comandos em um módulo sem qualquer configuração de instalação ou perfil; portanto, não é necessário gerenciar módulos depois de instalá-los em seu computador.</span><span class="sxs-lookup"><span data-stu-id="3428a-118">You can now use the commands in a module without any set-up or profile configuration, so there's no need to manage modules after you install them on your computer.</span></span>

<span data-ttu-id="3428a-119">Os comandos em um módulo também são mais fáceis de localizar.</span><span class="sxs-lookup"><span data-stu-id="3428a-119">The commands in a module are also easier to find.</span></span> <span data-ttu-id="3428a-120">O `Get-Command` cmdlet agora Obtém todos os comandos em todos os módulos instalados, mesmo que ainda não estejam na sessão, para que você possa encontrar um comando e usá-lo sem importar.</span><span class="sxs-lookup"><span data-stu-id="3428a-120">The `Get-Command` cmdlet now gets all commands in all installed modules, even if they are not yet in the session, so you can find a command and use it without importing.</span></span>

<span data-ttu-id="3428a-121">Cada um dos exemplos a seguir faz com que o módulo CimCmdlets, que contém `Get-CimInstance` , seja importado para sua sessão.</span><span class="sxs-lookup"><span data-stu-id="3428a-121">Each of the following examples cause the CimCmdlets module, which contains `Get-CimInstance`, to be imported into your session.</span></span>

- <span data-ttu-id="3428a-122">Execute o comando</span><span class="sxs-lookup"><span data-stu-id="3428a-122">Run the Command</span></span>

  ```powershell
  Get-CimInstance Win32_OperatingSystem
  ```

- <span data-ttu-id="3428a-123">Obter o comando</span><span class="sxs-lookup"><span data-stu-id="3428a-123">Get the Command</span></span>

  ```powershell
  Get-Command Get-CimInstance
  ```

- <span data-ttu-id="3428a-124">Obter ajuda para o comando</span><span class="sxs-lookup"><span data-stu-id="3428a-124">Get Help for the Command</span></span>

  ```powershell
  Get-Help Get-CimInstance
  ```

<span data-ttu-id="3428a-125">`Get-Command` os comandos que incluem um caractere curinga ( `*` ) são considerados para descoberta, não para uso e não importam nenhum módulo.</span><span class="sxs-lookup"><span data-stu-id="3428a-125">`Get-Command` commands that include a wildcard character (`*`) are considered to be for discovery, not use, and do not import any modules.</span></span>

<span data-ttu-id="3428a-126">Somente os módulos armazenados no local especificado pela variável de ambiente PSModulePath são automaticamente importados.</span><span class="sxs-lookup"><span data-stu-id="3428a-126">Only modules that are stored in the location specified by the PSModulePath environment variable are automatically imported.</span></span> <span data-ttu-id="3428a-127">Os módulos em outros locais devem ser importados executando o `Import-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3428a-127">Modules in other locations must be imported by running the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="3428a-128">Além disso, os comandos que usam provedores do PowerShell não importam automaticamente um módulo.</span><span class="sxs-lookup"><span data-stu-id="3428a-128">Also, commands that use PowerShell providers do not automatically import a module.</span></span> <span data-ttu-id="3428a-129">Por exemplo, se você usar um comando que exija a unidade WSMan:, como o `Get-PSSessionConfiguration` cmdlet, talvez seja necessário executar o `Import-Module` cmdlet para importar o módulo **Microsoft. WSMan. Management** que inclui a `WSMan:` unidade.</span><span class="sxs-lookup"><span data-stu-id="3428a-129">For example, if you use a command that requires the WSMan: drive, such as the `Get-PSSessionConfiguration` cmdlet, you might need to run the `Import-Module` cmdlet to import the **Microsoft.WSMan.Management** module that includes the `WSMan:` drive.</span></span>

<span data-ttu-id="3428a-130">Você ainda pode executar o `Import-Module` comando para importar um módulo e usar a `$PSModuleAutoloadingPreference` variável para habilitar, desabilitar e configurar a importação automática de módulos.</span><span class="sxs-lookup"><span data-stu-id="3428a-130">You can still run the `Import-Module` command to import a module and use the `$PSModuleAutoloadingPreference` variable to enable, disable and configure automatic importing of modules.</span></span> <span data-ttu-id="3428a-131">Para obter mais informações, consulte [about_Preference_Variables](about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="3428a-131">For more information, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

## <a name="how-to-use-a-module"></a><span data-ttu-id="3428a-132">Como usar um módulo</span><span class="sxs-lookup"><span data-stu-id="3428a-132">How to Use a Module</span></span>

<span data-ttu-id="3428a-133">Para usar um módulo, execute as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="3428a-133">To use a module, perform the following tasks:</span></span>

1. <span data-ttu-id="3428a-134">Instale o módulo.</span><span class="sxs-lookup"><span data-stu-id="3428a-134">Install the module.</span></span> <span data-ttu-id="3428a-135">(Isso é geralmente feito para você.)</span><span class="sxs-lookup"><span data-stu-id="3428a-135">(This is often done for you.)</span></span>
1. <span data-ttu-id="3428a-136">Localize os comandos que o módulo adicionou.</span><span class="sxs-lookup"><span data-stu-id="3428a-136">Find the commands that the module added.</span></span>
1. <span data-ttu-id="3428a-137">Use os comandos que o módulo adicionou.</span><span class="sxs-lookup"><span data-stu-id="3428a-137">Use the commands that the module added.</span></span>

<span data-ttu-id="3428a-138">Este tópico explica como executar essas tarefas.</span><span class="sxs-lookup"><span data-stu-id="3428a-138">This topic explains how to perform these tasks.</span></span> <span data-ttu-id="3428a-139">Ele também inclui outras informações úteis sobre o gerenciamento de módulos.</span><span class="sxs-lookup"><span data-stu-id="3428a-139">It also includes other useful information about managing modules.</span></span>

## <a name="how-to-install-a-module"></a><span data-ttu-id="3428a-140">Como instalar um módulo</span><span class="sxs-lookup"><span data-stu-id="3428a-140">How to Install a Module</span></span>

<span data-ttu-id="3428a-141">Se você receber um módulo como uma pasta com arquivos, será necessário instalá-lo em seu computador antes de poder usá-lo no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3428a-141">If you receive a module as a folder with files in it, you need to install it on your computer before you can use it in PowerShell.</span></span>

<span data-ttu-id="3428a-142">A maioria dos módulos é instalada por você.</span><span class="sxs-lookup"><span data-stu-id="3428a-142">Most modules are installed for you.</span></span> <span data-ttu-id="3428a-143">O PowerShell vem com vários módulos pré-instalados, às vezes chamados de módulos _principais_ .</span><span class="sxs-lookup"><span data-stu-id="3428a-143">PowerShell comes with several preinstalled modules, sometimes called the _core_ modules.</span></span> <span data-ttu-id="3428a-144">Em computadores baseados no Windows, se os recursos incluídos no sistema operacional tiverem cmdlets para gerenciá-los, esses módulos serão pré-instalados.</span><span class="sxs-lookup"><span data-stu-id="3428a-144">On Windows-based computers, if features that are included with the operating system have cmdlets to manage them, those modules are preinstalled.</span></span> <span data-ttu-id="3428a-145">Quando você instala um recurso do Windows, usando, por exemplo, o assistente Adicionar funções e recursos no Gerenciador do Servidor ou a caixa de diálogo ativar ou desativar recursos do Windows no painel de controle, todos os módulos do PowerShell que fazem parte do recurso são instalados.</span><span class="sxs-lookup"><span data-stu-id="3428a-145">When you install a Windows feature, by using, for example, the Add Roles and Features Wizard in Server Manager, or the Turn Windows features on or off dialog box in Control Panel, any PowerShell modules that are part of the feature are installed.</span></span> <span data-ttu-id="3428a-146">Muitos outros módulos têm um instalador ou um programa de Instalação que instala o módulo.</span><span class="sxs-lookup"><span data-stu-id="3428a-146">Many other modules come in an installer or Setup program that installs the module.</span></span>

<span data-ttu-id="3428a-147">Use o seguinte comando para criar um diretório de **módulos** para o usuário atual:</span><span class="sxs-lookup"><span data-stu-id="3428a-147">Use the following command to create a **Modules** directory for the current user:</span></span>

```powershell
New-Item -Type Directory -Path $HOME\Documents\PowerShell\Modules
```

<span data-ttu-id="3428a-148">Copie a pasta de módulo inteira para o diretório Modules.</span><span class="sxs-lookup"><span data-stu-id="3428a-148">Copy the entire module folder into the Modules directory.</span></span> <span data-ttu-id="3428a-149">Você pode usar qualquer método para copiar a pasta, incluindo o Windows Explorer e Cmd.exe, bem como o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3428a-149">You can use any method to copy the folder, including Windows Explorer and Cmd.exe, as well as PowerShell.</span></span> <span data-ttu-id="3428a-150">No PowerShell, use o `Copy-Item` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3428a-150">In PowerShell use the `Copy-Item` cmdlet.</span></span> <span data-ttu-id="3428a-151">Por exemplo, para copiar a pasta MyModule de `C:\ps-test\MyModule` para o diretório Modules, digite:</span><span class="sxs-lookup"><span data-stu-id="3428a-151">For example, to copy the MyModule folder from `C:\ps-test\MyModule` to the Modules directory, type:</span></span>

```powershell
Copy-Item -Path C:\ps-test\MyModule -Destination `
    $HOME\Documents\PowerShell\Modules
```

<span data-ttu-id="3428a-152">Você pode instalar um módulo em qualquer local, mas instalar os módulos em um local padrão de módulo torna-os mais fáceis de gerenciar.</span><span class="sxs-lookup"><span data-stu-id="3428a-152">You can install a module in any location, but installing your modules in a default module location makes them easier to manage.</span></span> <span data-ttu-id="3428a-153">Para obter mais informações sobre os locais de módulo padrão, consulte o [módulo e os locais de recursos de DSC e](#module-and-dsc-resource-locations-and-psmodulepath) a seção PSModulePath.</span><span class="sxs-lookup"><span data-stu-id="3428a-153">For more information about the default module locations, see the [Module and DSC Resource Locations, and PSModulePath](#module-and-dsc-resource-locations-and-psmodulepath) section.</span></span>

## <a name="how-to-find-installed-modules"></a><span data-ttu-id="3428a-154">Como localizar os módulos instalados</span><span class="sxs-lookup"><span data-stu-id="3428a-154">How to Find Installed Modules</span></span>

<span data-ttu-id="3428a-155">Para localizar os módulos que são instalados em um local de módulo padrão, mas ainda não foram importados para a sessão, digite:</span><span class="sxs-lookup"><span data-stu-id="3428a-155">To find modules that are installed in a default module location, but not yet imported into your session, type:</span></span>

```powershell
Get-Module -ListAvailable
```

<span data-ttu-id="3428a-156">Para localizar os módulos que já foram importados para a sessão, no prompt do PowerShell, digite:</span><span class="sxs-lookup"><span data-stu-id="3428a-156">To find the modules that have already been imported into your session, at the PowerShell prompt, type:</span></span>

```powershell
Get-Module
```

<span data-ttu-id="3428a-157">Para obter mais informações sobre o `Get-Module` cmdlet, consulte [obter-módulo](xref:Microsoft.PowerShell.Core.Get-Module).</span><span class="sxs-lookup"><span data-stu-id="3428a-157">For more information about the `Get-Module` cmdlet, see [Get-Module](xref:Microsoft.PowerShell.Core.Get-Module).</span></span>

## <a name="how-to-find-the-commands-in-a-module"></a><span data-ttu-id="3428a-158">Como localizar os comandos em um módulo</span><span class="sxs-lookup"><span data-stu-id="3428a-158">How to Find the Commands in a Module</span></span>

<span data-ttu-id="3428a-159">Use o `Get-Command` cmdlet para localizar todos os comandos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="3428a-159">Use the `Get-Command` cmdlet to find all available commands.</span></span> <span data-ttu-id="3428a-160">Você pode usar os parâmetros do `Get-Command` cmdlet para filtrar comandos, como por módulo, nome e substantivo.</span><span class="sxs-lookup"><span data-stu-id="3428a-160">You can use the parameters of the `Get-Command` cmdlet to filter commands such as by module, name, and noun.</span></span>

<span data-ttu-id="3428a-161">Para localizar todos os comandos em um módulo, digite:</span><span class="sxs-lookup"><span data-stu-id="3428a-161">To find all commands in a module, type:</span></span>

```powershell
Get-Command -Module <module-name>
```

<span data-ttu-id="3428a-162">Por exemplo, para localizar os comandos no módulo BitsTransfer, digite:</span><span class="sxs-lookup"><span data-stu-id="3428a-162">For example, to find the commands in the BitsTransfer module, type:</span></span>

```powershell
Get-Command -Module BitsTransfer
```

<span data-ttu-id="3428a-163">Para obter mais informações sobre o `Get-Command` cmdlet, consulte [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command).</span><span class="sxs-lookup"><span data-stu-id="3428a-163">For more information about the `Get-Command` cmdlet, see [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command).</span></span>

## <a name="how-to-get-help-for-the-commands-in-a-module"></a><span data-ttu-id="3428a-164">Como obter ajuda para os comandos em um módulo</span><span class="sxs-lookup"><span data-stu-id="3428a-164">How to Get Help for the Commands in a Module</span></span>

<span data-ttu-id="3428a-165">Se o módulo contiver arquivos de ajuda para os comandos que ele exporta, o `Get-Help` cmdlet exibirá os tópicos da ajuda.</span><span class="sxs-lookup"><span data-stu-id="3428a-165">If the module contains Help files for the commands that it exports, the `Get-Help` cmdlet will display the Help topics.</span></span> <span data-ttu-id="3428a-166">Use o mesmo `Get-Help` formato de comando que você usaria para obter ajuda para qualquer comando no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3428a-166">Use the same `Get-Help` command format that you would use to get help for any command in PowerShell.</span></span>

<span data-ttu-id="3428a-167">A partir do PowerShell 3,0, você pode baixar arquivos de ajuda para um módulo e baixar atualizações para os arquivos de ajuda para que eles nunca sejam obsoletos.</span><span class="sxs-lookup"><span data-stu-id="3428a-167">Beginning in PowerShell 3.0, you can download Help files for a module and download updates to the Help files so they are never obsolete.</span></span>

<span data-ttu-id="3428a-168">Para obter ajuda para os comandos em um módulo, digite:</span><span class="sxs-lookup"><span data-stu-id="3428a-168">To get help for a commands in a module, type:</span></span>

```powershell
Get-Help <command-name>
```

<span data-ttu-id="3428a-169">Para obter ajuda online para o comando em um módulo, digite:</span><span class="sxs-lookup"><span data-stu-id="3428a-169">To get help online for command in a module, type:</span></span>

```powershell
Get-Help <command-name> -Online
```

<span data-ttu-id="3428a-170">Para baixar e instalar os arquivos de ajuda para os comandos em um módulo, digite:</span><span class="sxs-lookup"><span data-stu-id="3428a-170">To download and install the help files for the commands in a module, type:</span></span>

```powershell
Update-Help -Module <module-name>
```

<span data-ttu-id="3428a-171">Para obter mais informações, consulte [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) e [Update-Help](xref:Microsoft.PowerShell.Core.Update-Help).</span><span class="sxs-lookup"><span data-stu-id="3428a-171">For more information, see [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) and [Update-Help](xref:Microsoft.PowerShell.Core.Update-Help).</span></span>

## <a name="how-to-import-a-module"></a><span data-ttu-id="3428a-172">Como importar um módulo</span><span class="sxs-lookup"><span data-stu-id="3428a-172">How to Import a Module</span></span>

<span data-ttu-id="3428a-173">Você pode precisar importar um módulo ou importar um arquivo de módulo.</span><span class="sxs-lookup"><span data-stu-id="3428a-173">You might have to import a module or import a module file.</span></span> <span data-ttu-id="3428a-174">A importação é necessária quando um módulo não está instalado nos locais especificados pela variável de ambiente **PSModulePath** , `$env:PSModulePath` ou o módulo consiste em um arquivo, como um arquivo. dll ou. psm1, em vez de um módulo típico que é entregue como uma pasta.</span><span class="sxs-lookup"><span data-stu-id="3428a-174">Importing is required when a module is not installed in the locations specified by the **PSModulePath** environment variable, `$env:PSModulePath`, or the module consists of file, such as a .dll or .psm1 file, instead of typical module that is delivered as a folder.</span></span>

<span data-ttu-id="3428a-175">Você também pode optar por importar um módulo para que possa usar os parâmetros do `Import-Module` comando, como o parâmetro Prefix, que adiciona um prefixo distintivo aos nomes de substantivo de todos os comandos importados, ou o parâmetro **NoClobber** , que impede que o módulo adicione comandos que ocultam ou substituem os comandos existentes na sessão.</span><span class="sxs-lookup"><span data-stu-id="3428a-175">You might also choose to import a module so that you can use the parameters of the `Import-Module` command, such as the Prefix parameter, which adds a distinctive prefix to the noun names of all imported commands, or the **NoClobber** parameter, which prevents the module from adding commands that would hide or replace existing commands in the session.</span></span>

<span data-ttu-id="3428a-176">Para importar módulos, use o `Import-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3428a-176">To import modules, use the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="3428a-177">Para importar os módulos em um local de PSModulePath para a sessão atual, use o seguinte formato de comando.</span><span class="sxs-lookup"><span data-stu-id="3428a-177">To import modules in a PSModulePath location into the current session, use the following command format.</span></span>

```powershell
Import-Module <module-name>
```

<span data-ttu-id="3428a-178">Por exemplo, o comando a seguir importa o módulo BitsTransfer para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="3428a-178">For example, the following command imports the BitsTransfer module into the current session.</span></span>

```powershell
Import-Module BitsTransfer
```

<span data-ttu-id="3428a-179">Para importar um módulo que não está em um local padrão de módulo, use o caminho totalmente qualificado para a pasta de módulo no comando.</span><span class="sxs-lookup"><span data-stu-id="3428a-179">To import a module that is not in a default module location, use the fully qualified path to the module folder in the command.</span></span>

<span data-ttu-id="3428a-180">Por exemplo, para adicionar o módulo TestCmdlets no `C:\ps-test` diretório à sua sessão, digite:</span><span class="sxs-lookup"><span data-stu-id="3428a-180">For example, to add the TestCmdlets module in the `C:\ps-test` directory to your session, type:</span></span>

```powershell
Import-Module C:\ps-test\TestCmdlets
```

<span data-ttu-id="3428a-181">Para importar um arquivo de módulo que não está contido em uma pasta de módulo, use o caminho totalmente qualificado para o arquivo de módulo no comando.</span><span class="sxs-lookup"><span data-stu-id="3428a-181">To import a module file that is not contained in a module folder, use the fully qualified path to the module file in the command.</span></span>

<span data-ttu-id="3428a-182">Por exemplo, para adicionar o módulo TestCmdlets.dll no `C:\ps-test` diretório à sua sessão, digite:</span><span class="sxs-lookup"><span data-stu-id="3428a-182">For example, to add the TestCmdlets.dll module in the `C:\ps-test` directory to your session, type:</span></span>

```powershell
Import-Module C:\ps-test\TestCmdlets.dll
```

<span data-ttu-id="3428a-183">Para obter mais informações sobre como adicionar módulos à sua sessão, consulte [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module).</span><span class="sxs-lookup"><span data-stu-id="3428a-183">For more information about adding modules to your session, see [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module).</span></span>

## <a name="how-to-import-a-module-into-every-session"></a><span data-ttu-id="3428a-184">Como importar um módulo para cada sessão</span><span class="sxs-lookup"><span data-stu-id="3428a-184">How to Import a Module into Every Session</span></span>

<span data-ttu-id="3428a-185">O `Import-Module` comando importa módulos para sua sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3428a-185">The `Import-Module` command imports modules into your current PowerShell session.</span></span> <span data-ttu-id="3428a-186">Para importar um módulo para cada sessão do PowerShell que você iniciar, adicione o `Import-Module` comando ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3428a-186">To import a module into every PowerShell session that you start, add the `Import-Module` command to your PowerShell profile.</span></span>

<span data-ttu-id="3428a-187">Para obter mais informações sobre perfis, consulte [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="3428a-187">For more information about profiles, see [about_Profiles](about_Profiles.md).</span></span>

## <a name="how-to-remove-a-module"></a><span data-ttu-id="3428a-188">Como remover um módulo</span><span class="sxs-lookup"><span data-stu-id="3428a-188">How to Remove a Module</span></span>

<span data-ttu-id="3428a-189">Quando você remove um módulo, os comandos que o módulo adicionou são excluídos da sessão.</span><span class="sxs-lookup"><span data-stu-id="3428a-189">When you remove a module, the commands that the module added are deleted from the session.</span></span>

<span data-ttu-id="3428a-190">Para remover um módulo da sua sessão, use o seguinte formato de comando.</span><span class="sxs-lookup"><span data-stu-id="3428a-190">To remove a module from your session, use the following command format.</span></span>

```powershell
Remove-Module <module-name>
```

<span data-ttu-id="3428a-191">Por exemplo, o comando a seguir remove o módulo BitsTransfer da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="3428a-191">For example, the following command removes the BitsTransfer module from the current session.</span></span>

```powershell
Remove-Module BitsTransfer
```

<span data-ttu-id="3428a-192">Remover um módulo inverte a operação de importação de um módulo.</span><span class="sxs-lookup"><span data-stu-id="3428a-192">Removing a module reverses the operation of importing a module.</span></span> <span data-ttu-id="3428a-193">Remover um módulo não desinstala o módulo.</span><span class="sxs-lookup"><span data-stu-id="3428a-193">Removing a module does not uninstall the module.</span></span> <span data-ttu-id="3428a-194">Para obter mais informações, consulte [Remove-Module](xref:Microsoft.PowerShell.Core.Remove-Module).</span><span class="sxs-lookup"><span data-stu-id="3428a-194">For more information, see [Remove-Module](xref:Microsoft.PowerShell.Core.Remove-Module).</span></span>

## <a name="module-and-dsc-resource-locations-and-psmodulepath"></a><span data-ttu-id="3428a-195">Locais de recursos de módulo e DSC e PSModulePath</span><span class="sxs-lookup"><span data-stu-id="3428a-195">Module and DSC Resource Locations, and PSModulePath</span></span>

<span data-ttu-id="3428a-196">A `$env:PSModulePath` variável de ambiente contém uma lista de locais de pasta que são pesquisados para localizar módulos e recursos.</span><span class="sxs-lookup"><span data-stu-id="3428a-196">The `$env:PSModulePath` environment variable contains a list of folder locations that are searched to find modules and resources.</span></span>

<span data-ttu-id="3428a-197">Por padrão, os locais efetivos atribuídos a `$env:PSModulePath` são:</span><span class="sxs-lookup"><span data-stu-id="3428a-197">By default, the effective locations assigned to `$env:PSModulePath` are:</span></span>

- <span data-ttu-id="3428a-198">Locais de todo o sistema: `$PSHOME\Modules`</span><span class="sxs-lookup"><span data-stu-id="3428a-198">System-wide locations: `$PSHOME\Modules`</span></span>

  <span data-ttu-id="3428a-199">Essas pastas contêm módulos que acompanham o Windows e o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3428a-199">These folders contain modules that ship with Windows and PowerShell.</span></span>

  <span data-ttu-id="3428a-200">Os recursos de DSC incluídos com o PowerShell são armazenados na `$PSHOME\Modules\PSDesiredStateConfiguration\DSCResources` pasta.</span><span class="sxs-lookup"><span data-stu-id="3428a-200">DSC resources that are included with PowerShell are stored in the `$PSHOME\Modules\PSDesiredStateConfiguration\DSCResources` folder.</span></span>

- <span data-ttu-id="3428a-201">Módulos específicos do usuário: são módulos instalados pelo usuário no escopo do usuário.</span><span class="sxs-lookup"><span data-stu-id="3428a-201">User-specific modules: These are modules installed by the user in the user's scope.</span></span> <span data-ttu-id="3428a-202">`Install-Module` tem um parâmetro de **escopo** que permite que você especifique se o módulo está instalado para o usuário atual ou para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="3428a-202">`Install-Module` has a **Scope** parameter that allows you to specify whether the module is installed for the current user or for all users.</span></span> <span data-ttu-id="3428a-203">Para obter mais informações, consulte [install-Module](xref:PowerShellGet.Install-Module).</span><span class="sxs-lookup"><span data-stu-id="3428a-203">For more information, see [Install-Module](xref:PowerShellGet.Install-Module).</span></span>

  <span data-ttu-id="3428a-204">O local **CurrentUser** específico do usuário no Windows é a `PowerShell\Modules` pasta localizada no local **documentos** em seu perfil de usuário.</span><span class="sxs-lookup"><span data-stu-id="3428a-204">The user-specific **CurrentUser** location on Windows is the `PowerShell\Modules` folder located in the **Documents** location in your user profile.</span></span> <span data-ttu-id="3428a-205">O caminho específico desse local varia de acordo com a versão do Windows e se você está usando o redirecionamento de pasta.</span><span class="sxs-lookup"><span data-stu-id="3428a-205">The specific path of that location varies by version of Windows and whether or not you are using folder redirection.</span></span> <span data-ttu-id="3428a-206">O Microsoft OneDrive também pode alterar o local da sua pasta de **documentos** .</span><span class="sxs-lookup"><span data-stu-id="3428a-206">Microsoft OneDrive can also change the location of your **Documents** folder.</span></span>

  <span data-ttu-id="3428a-207">Por padrão, no Windows 10, esse local é `$HOME\Documents\PowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="3428a-207">By default, on Windows 10, that location is `$HOME\Documents\PowerShell\Modules`.</span></span> <span data-ttu-id="3428a-208">No Linux ou Mac, o local **CurrentUser** é `$HOME/.local/share/powershell/Modules` .</span><span class="sxs-lookup"><span data-stu-id="3428a-208">On Linux or Mac, the **CurrentUser** location is `$HOME/.local/share/powershell/Modules`.</span></span>

  > [!NOTE]
  > <span data-ttu-id="3428a-209">Você pode verificar o local da pasta **documentos** usando o seguinte comando: `[Environment]::GetFolderPath('MyDocuments')` .</span><span class="sxs-lookup"><span data-stu-id="3428a-209">You can verify the location of your **Documents** folder using the following command: `[Environment]::GetFolderPath('MyDocuments')`.</span></span>

- <span data-ttu-id="3428a-210">O local **AllUsers** está `$env:PROGRAMFILES\PowerShell\Modules` no Windows.</span><span class="sxs-lookup"><span data-stu-id="3428a-210">The **AllUsers** location is `$env:PROGRAMFILES\PowerShell\Modules` on Windows.</span></span> <span data-ttu-id="3428a-211">No Linux ou Mac, os módulos são armazenados em `/usr/local/share/powershell/Modules` .</span><span class="sxs-lookup"><span data-stu-id="3428a-211">On Linux or Mac the modules are stored at `/usr/local/share/powershell/Modules`.</span></span>

> [!NOTE]
> <span data-ttu-id="3428a-212">Para adicionar ou alterar arquivos no `$env:Windir\System32` diretório, inicie o PowerShell com a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="3428a-212">To add or change files in the `$env:Windir\System32` directory, start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="3428a-213">Você pode alterar os locais de módulo padrão no sistema alterando o valor da variável de ambiente **PSModulePath** , `$Env:PSModulePath` .</span><span class="sxs-lookup"><span data-stu-id="3428a-213">You can change the default module locations on your system by changing the value of the **PSModulePath** environment variable, `$Env:PSModulePath`.</span></span> <span data-ttu-id="3428a-214">A variável de ambiente **PSModulePath** é modelada na variável de ambiente Path e tem o mesmo formato.</span><span class="sxs-lookup"><span data-stu-id="3428a-214">The **PSModulePath** environment variable is modeled on the Path environment variable and has the same format.</span></span>

<span data-ttu-id="3428a-215">Para exibir os locais padrão de módulo, digite:</span><span class="sxs-lookup"><span data-stu-id="3428a-215">To view the default module locations, type:</span></span>

```powershell
$Env:PSModulePath
```

<span data-ttu-id="3428a-216">Para adicionar um local padrão de módulo, use o seguinte formato de comando.</span><span class="sxs-lookup"><span data-stu-id="3428a-216">To add a default module location, use the following command format.</span></span>

```powershell
$Env:PSModulePath = $Env:PSModulePath + ";<path>"
```

<span data-ttu-id="3428a-217">O ponto e vírgula ( `;` ) no comando separa o novo caminho do caminho que o precede na lista.</span><span class="sxs-lookup"><span data-stu-id="3428a-217">The semi-colon (`;`) in the command separates the new path from the path that precedes it in the list.</span></span>

<span data-ttu-id="3428a-218">Por exemplo, para adicionar o `C:\ps-test\Modules` diretório, digite:</span><span class="sxs-lookup"><span data-stu-id="3428a-218">For example, to add the `C:\ps-test\Modules` directory, type:</span></span>

```powershell
$Env:PSModulePath + ";C:\ps-test\Modules"
```

<span data-ttu-id="3428a-219">Para adicionar um local de módulo padrão no Linux ou no MacOS, use o seguinte formato de comando:</span><span class="sxs-lookup"><span data-stu-id="3428a-219">To add a default module location on Linux or MacOS, use the following command format:</span></span>

```powershell
$Env:PSModulePath += ":<path>"
```

<span data-ttu-id="3428a-220">Por exemplo, para adicionar o `/usr/local/Fabrikam/Modules` diretório ao valor da variável de ambiente **PSModulePath** , digite:</span><span class="sxs-lookup"><span data-stu-id="3428a-220">For example, to add the `/usr/local/Fabrikam/Modules` directory to the value of the **PSModulePath** environment variable, type:</span></span>

```powershell
$Env:PSModulePath += ":/usr/local/Fabrikam/Modules"
```

<span data-ttu-id="3428a-221">No Linux ou MacOS, os dois-pontos ( `:` ) no comando separam o novo caminho do caminho que o precede na lista.</span><span class="sxs-lookup"><span data-stu-id="3428a-221">On Linux or MacOS, the colon (`:`) in the command separates the new path from the path that precedes it in the list.</span></span>

<span data-ttu-id="3428a-222">Quando você adiciona um caminho ao **PSModulePath** `Get-Module` e os `Import-Module` comandos incluem módulos nesse caminho.</span><span class="sxs-lookup"><span data-stu-id="3428a-222">When you add a path to **PSModulePath** , `Get-Module` and `Import-Module` commands include modules in that path.</span></span>

<span data-ttu-id="3428a-223">O valor que você define afeta apenas a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="3428a-223">The value that you set affects only the current session.</span></span> <span data-ttu-id="3428a-224">Para fazer a alteração persistente, adicione o comando ao seu perfil do PowerShell ou use o sistema no painel de controle para alterar o valor da variável de ambiente **PSModulePath** no registro.</span><span class="sxs-lookup"><span data-stu-id="3428a-224">To make the change persistent, add the command to your PowerShell profile or use System in Control Panel to change the value of the **PSModulePath** environment variable in the registry.</span></span>

<span data-ttu-id="3428a-225">Além disso, para fazer a alteração persistente, você também pode usar o método **SetEnvironmentVariable não** da classe **System. Environment** para adicionar um caminho à variável de ambiente **PSModulePath** .</span><span class="sxs-lookup"><span data-stu-id="3428a-225">Also, to make the change persistent, you can also use the **SetEnvironmentVariable** method of the **System.Environment** class to add a Path to the **PSModulePath** environment variable.</span></span>

<span data-ttu-id="3428a-226">Para obter mais informações sobre a variável **PSModulePath** , consulte [about_Environment_Variables](about_Environment_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="3428a-226">For more information about the **PSModulePath** variable, see [about_Environment_Variables](about_Environment_Variables.md).</span></span>

## <a name="modules-and-name-conflicts"></a><span data-ttu-id="3428a-227">Conflitos de módulos e nomes</span><span class="sxs-lookup"><span data-stu-id="3428a-227">Modules and Name Conflicts</span></span>

<span data-ttu-id="3428a-228">Os conflitos de nome ocorrem quando mais de um comando na sessão tem o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="3428a-228">Name conflicts occur when more than one command in the session has the same name.</span></span> <span data-ttu-id="3428a-229">Importar um módulo provoca um conflito de nome quando os comandos no módulo têm os mesmos nomes de comandos ou itens na sessão.</span><span class="sxs-lookup"><span data-stu-id="3428a-229">Importing a module causes a name conflict when commands in the module have the same names as commands or items in the session.</span></span>

<span data-ttu-id="3428a-230">Os conflitos de nome podem resultar em comandos sendo ocultados ou substituídos.</span><span class="sxs-lookup"><span data-stu-id="3428a-230">Name conflicts can result in commands being hidden or replaced.</span></span>

### <a name="hidden"></a><span data-ttu-id="3428a-231">Hidden</span><span class="sxs-lookup"><span data-stu-id="3428a-231">Hidden</span></span>

<span data-ttu-id="3428a-232">Um comando é ocultado quando ele não é o comando que é executado quando você digita o nome do comando, mas você pode executá-lo usando outro método, como qualificar o nome do comando com o nome do módulo ou snap-in na qual ele se originou.</span><span class="sxs-lookup"><span data-stu-id="3428a-232">A command is hidden when it is not the command that runs when you type the command name, but you can run it by using another method, such as by qualifying the command name with the name of the module or snap-in in which it originated.</span></span>

### <a name="replaced"></a><span data-ttu-id="3428a-233">Substituído</span><span class="sxs-lookup"><span data-stu-id="3428a-233">Replaced</span></span>

<span data-ttu-id="3428a-234">Um comando é substituído quando você não pode executá-lo porque ele foi substituído por um comando com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="3428a-234">A command is replaced when you cannot run it because it has been overwritten by a command with the same name.</span></span> <span data-ttu-id="3428a-235">Mesmo quando você remove o módulo que causou o conflito, não é possível executar um comando substituído, a menos que você reinicie a sessão.</span><span class="sxs-lookup"><span data-stu-id="3428a-235">Even when you remove the module that caused the conflict, you cannot run a replaced command unless you restart the session.</span></span>

<span data-ttu-id="3428a-236">`Import-Module` pode adicionar comandos que ocultam e substituem comandos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="3428a-236">`Import-Module` might add commands that hide and replace commands in the current session.</span></span> <span data-ttu-id="3428a-237">Além disso, os comandos na sessão podem ocultar os comandos que o módulo adicionou.</span><span class="sxs-lookup"><span data-stu-id="3428a-237">Also, commands in your session can hide commands that the module added.</span></span>

<span data-ttu-id="3428a-238">Para detectar conflitos de nome, use o parâmetro **All** do `Get-Command` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3428a-238">To detect name conflicts, use the **All** parameter of the `Get-Command` cmdlet.</span></span> <span data-ttu-id="3428a-239">A partir do PowerShell 3,0, `Get-Command` obtém somente os comandos que são executados quando você digita o nome do comando.</span><span class="sxs-lookup"><span data-stu-id="3428a-239">Beginning in PowerShell 3.0, `Get-Command` gets only that commands that run when you type the command name.</span></span> <span data-ttu-id="3428a-240">O parâmetro **All** Obtém todos os comandos com o nome específico na sessão.</span><span class="sxs-lookup"><span data-stu-id="3428a-240">The **All** parameter gets all commands with the specific name in the session.</span></span>

<span data-ttu-id="3428a-241">Para evitar conflitos de nome, use os parâmetros **NoClobber** ou **prefix** do `Import-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3428a-241">To prevent name conflicts, use the **NoClobber** or **Prefix** parameters of the `Import-Module` cmdlet.</span></span> <span data-ttu-id="3428a-242">O parâmetro **prefix** adiciona um prefixo aos nomes dos comandos importados para que eles sejam exclusivos na sessão.</span><span class="sxs-lookup"><span data-stu-id="3428a-242">The **Prefix** parameter adds a prefix to the names of imported commands so that they are unique in the session.</span></span> <span data-ttu-id="3428a-243">O parâmetro **NoClobber** não importa nenhum comando que oculte ou substitua os comandos existentes na sessão.</span><span class="sxs-lookup"><span data-stu-id="3428a-243">The **NoClobber** parameter does not import any commands that would hide or replace existing commands in the session.</span></span>

<span data-ttu-id="3428a-244">Você também pode usar o **alias** , o **cmdlet** , a **função** e os parâmetros **variáveis** do `Import-Module` para selecionar apenas os comandos que deseja importar e pode excluir comandos que causam conflitos de nome em sua sessão.</span><span class="sxs-lookup"><span data-stu-id="3428a-244">You can also use the **Alias** , **Cmdlet** , **Function** , and **Variable** parameters of `Import-Module` to select only the commands that you want to import, and you can exclude commands that cause name conflicts in your session.</span></span>

<span data-ttu-id="3428a-245">Os autores de módulo podem evitar conflitos de nome usando a propriedade **DefaultCommandPrefix** do manifesto do módulo para adicionar um prefixo padrão a todos os nomes de comando.</span><span class="sxs-lookup"><span data-stu-id="3428a-245">Module authors can prevent name conflicts by using the **DefaultCommandPrefix** property of the module manifest to add a default prefix to all command names.</span></span>
<span data-ttu-id="3428a-246">O valor do parâmetro **prefix** tem precedência sobre o valor de **DefaultCommandPrefix** .</span><span class="sxs-lookup"><span data-stu-id="3428a-246">The value of the **Prefix** parameter takes precedence over the value of **DefaultCommandPrefix** .</span></span>

<span data-ttu-id="3428a-247">Mesmo se um comando estiver oculto, você poderá executá-lo qualificando o nome de comando com o nome do módulo ou snap-in no qual ele foi originado.</span><span class="sxs-lookup"><span data-stu-id="3428a-247">Even if a command is hidden, you can run it by qualifying the command name with the name of the module or snap-in in which it originated.</span></span>

<span data-ttu-id="3428a-248">As regras de precedência de comando do PowerShell determinam qual comando é executado quando a sessão inclui comandos com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="3428a-248">The PowerShell command precedence rules determine which command runs when the session includes commands with the same name.</span></span>

<span data-ttu-id="3428a-249">Por exemplo, quando uma sessão inclui uma função e um cmdlet com o mesmo nome, o PowerShell executa a função por padrão.</span><span class="sxs-lookup"><span data-stu-id="3428a-249">For example, when a session includes a function and a cmdlet with the same name, PowerShell runs the function by default.</span></span> <span data-ttu-id="3428a-250">Quando a sessão inclui comandos do mesmo tipo com o mesmo nome, como dois cmdlets com o mesmo nome, por padrão, ela executa o comando adicionado mais recentemente.</span><span class="sxs-lookup"><span data-stu-id="3428a-250">When the session includes commands of the same type with the same name, such as two cmdlets with the same name, by default, it runs the most recently added command.</span></span>

<span data-ttu-id="3428a-251">Para obter mais informações, incluindo uma explicação das regras de precedência e instruções para executar comandos ocultos, consulte [about_Command_Precedence](about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="3428a-251">For more information, including an explanation of the precedence rules and instructions for running hidden commands, see [about_Command_Precedence](about_Command_Precedence.md).</span></span>

## <a name="modules-and-snap-ins"></a><span data-ttu-id="3428a-252">Módulos e snap-ins</span><span class="sxs-lookup"><span data-stu-id="3428a-252">Modules and Snap-ins</span></span>

<span data-ttu-id="3428a-253">Você pode adicionar comandos à sua sessão por meio de módulos e snap-ins. Os módulos podem adicionar todos os tipos de comandos, incluindo cmdlets, provedores e funções, e itens, como variáveis, aliases e unidades do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3428a-253">You can add commands to your session from modules and snap-ins. Modules can add all types of commands, including cmdlets, providers, and functions, and items, such as variables, aliases, and PowerShell drives.</span></span> <span data-ttu-id="3428a-254">Os Snap-ins podem adicionar apenas os cmdlets e provedores.</span><span class="sxs-lookup"><span data-stu-id="3428a-254">Snap-ins can add only cmdlets and providers.</span></span>

<span data-ttu-id="3428a-255">Antes de remover um módulo ou snap-in da sessão, use os comandos a seguir para determinar quais comandos serão removidos.</span><span class="sxs-lookup"><span data-stu-id="3428a-255">Before removing a module or snap-in from your session, use the following commands to determine which commands will be removed.</span></span>

<span data-ttu-id="3428a-256">Para localizar a origem de um cmdlet em sua sessão, use o seguinte formato de comando:</span><span class="sxs-lookup"><span data-stu-id="3428a-256">To find the source of a cmdlet in your session, use the following command format:</span></span>

```powershell
Get-Command <cmdlet-name> | Format-List -Property verb,noun,pssnapin,module
```

<span data-ttu-id="3428a-257">Por exemplo, para localizar a origem do `Get-Date` cmdlet, digite:</span><span class="sxs-lookup"><span data-stu-id="3428a-257">For example, to find the source of the `Get-Date` cmdlet, type:</span></span>

```powershell
Get-Command Get-Date | Format-List -Property verb,noun,module
```

## <a name="module-related-warnings-and-errors"></a><span data-ttu-id="3428a-258">Avisos e erros relacionados ao módulo</span><span class="sxs-lookup"><span data-stu-id="3428a-258">Module-related Warnings and Errors</span></span>

<span data-ttu-id="3428a-259">Os comandos exportados por um módulo devem seguir as regras de nomenclatura de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3428a-259">The commands that a module exports should follow the PowerShell command naming rules.</span></span> <span data-ttu-id="3428a-260">Se o módulo que você importar exporta cmdlets ou funções que têm verbos não aprovados em seus nomes, o `Import-Module` cmdlet exibe a seguinte mensagem de aviso.</span><span class="sxs-lookup"><span data-stu-id="3428a-260">If the module that you import exports cmdlets or functions that have unapproved verbs in their names, the `Import-Module` cmdlet displays the following warning message.</span></span>

> <span data-ttu-id="3428a-261">Aviso: alguns nomes de comando importados incluem verbos não aprovados que podem torná-los menos detectáveis.</span><span class="sxs-lookup"><span data-stu-id="3428a-261">WARNING: Some imported command names include unapproved verbs which might make them less discoverable.</span></span> <span data-ttu-id="3428a-262">Use o parâmetro Verbose para obter mais detalhes ou digite Get-Verb para ver a lista de verbos aprovados."</span><span class="sxs-lookup"><span data-stu-id="3428a-262">Use the Verbose parameter for more detail or type Get-Verb to see the list of approved verbs.</span></span>

<span data-ttu-id="3428a-263">A mensagem é apenas um aviso.</span><span class="sxs-lookup"><span data-stu-id="3428a-263">This message is only a warning.</span></span> <span data-ttu-id="3428a-264">O módulo completo ainda é importado, incluindo os comandos não autorizados.</span><span class="sxs-lookup"><span data-stu-id="3428a-264">The complete module is still imported, including the non-conforming commands.</span></span> <span data-ttu-id="3428a-265">Embora a mensagem seja exibida para usuários do módulo, o problema de nomenclatura deve ser corrigido pelo autor do módulo.</span><span class="sxs-lookup"><span data-stu-id="3428a-265">Although the message is displayed to module users, the naming problem should be fixed by the module author.</span></span>

<span data-ttu-id="3428a-266">Para suprimir a mensagem de aviso, use o parâmetro **DisableNameChecking** do `Import-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3428a-266">To suppress the warning message, use the **DisableNameChecking** parameter of the `Import-Module` cmdlet.</span></span>

## <a name="built-in-modules-and-snap-ins"></a><span data-ttu-id="3428a-267">Módulos internos e snap-ins</span><span class="sxs-lookup"><span data-stu-id="3428a-267">Built-in Modules and Snap-ins</span></span>

<span data-ttu-id="3428a-268">No PowerShell 2,0 e em programas de host de estilo mais antigo no PowerShell 3,0 e posteriores, os comandos principais instalados com o PowerShell são empacotados em snap-ins que são adicionados automaticamente a todas as sessões do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3428a-268">In PowerShell 2.0 and in older-style host programs in PowerShell 3.0 and later, the core commands that are installed with PowerShell are packaged in snap-ins that are added automatically to every PowerShell session.</span></span>

<span data-ttu-id="3428a-269">A partir do PowerShell 3,0, para programas de host que implementam a `InitialSessionState.CreateDefault2` API de estado de sessão inicial, o snap-in do Microsoft. PowerShell. Core é adicionado a cada sessão por padrão.</span><span class="sxs-lookup"><span data-stu-id="3428a-269">Beginning in PowerShell 3.0, for host programs that implement the `InitialSessionState.CreateDefault2` initial session state API the Microsoft.PowerShell.Core snap-in is added to every session by default.</span></span> <span data-ttu-id="3428a-270">Os módulos são carregados automaticamente no primeiro uso.</span><span class="sxs-lookup"><span data-stu-id="3428a-270">Modules are loaded automatically on first-use.</span></span>

> [!NOTE]
> <span data-ttu-id="3428a-271">Sessões remotas, incluindo sessões que são iniciadas usando o `New-PSSession` cmdlet, são sessões de estilo mais antigas nas quais os comandos internos são empacotados em snap-ins.</span><span class="sxs-lookup"><span data-stu-id="3428a-271">Remote sessions, including sessions that are started by using the `New-PSSession` cmdlet, are older-style sessions in which the built-in commands are packaged in snap-ins.</span></span>

<span data-ttu-id="3428a-272">Os seguintes módulos (ou snap-ins) são instalados com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3428a-272">The following modules (or snap-ins) are installed with PowerShell.</span></span>

- <span data-ttu-id="3428a-273">CimCmdlets</span><span class="sxs-lookup"><span data-stu-id="3428a-273">CimCmdlets</span></span>
- <span data-ttu-id="3428a-274">Microsoft.PowerShell.Archive</span><span class="sxs-lookup"><span data-stu-id="3428a-274">Microsoft.PowerShell.Archive</span></span>
- <span data-ttu-id="3428a-275">Microsoft.PowerShell.Core</span><span class="sxs-lookup"><span data-stu-id="3428a-275">Microsoft.PowerShell.Core</span></span>
- <span data-ttu-id="3428a-276">Microsoft.PowerShell.Diagnostics</span><span class="sxs-lookup"><span data-stu-id="3428a-276">Microsoft.PowerShell.Diagnostics</span></span>
- <span data-ttu-id="3428a-277">Microsoft.PowerShell.Host</span><span class="sxs-lookup"><span data-stu-id="3428a-277">Microsoft.PowerShell.Host</span></span>
- <span data-ttu-id="3428a-278">Microsoft.PowerShell.Management</span><span class="sxs-lookup"><span data-stu-id="3428a-278">Microsoft.PowerShell.Management</span></span>
- <span data-ttu-id="3428a-279">Microsoft.PowerShell.Security</span><span class="sxs-lookup"><span data-stu-id="3428a-279">Microsoft.PowerShell.Security</span></span>
- <span data-ttu-id="3428a-280">Microsoft.PowerShell.Utility</span><span class="sxs-lookup"><span data-stu-id="3428a-280">Microsoft.PowerShell.Utility</span></span>
- <span data-ttu-id="3428a-281">Microsoft.WSMan.Management</span><span class="sxs-lookup"><span data-stu-id="3428a-281">Microsoft.WSMan.Management</span></span>
- <span data-ttu-id="3428a-282">PackageManagement</span><span class="sxs-lookup"><span data-stu-id="3428a-282">PackageManagement</span></span>
- <span data-ttu-id="3428a-283">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="3428a-283">PowerShellGet</span></span>
- <span data-ttu-id="3428a-284">PSDesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="3428a-284">PSDesiredStateConfiguration</span></span>
- <span data-ttu-id="3428a-285">PSDiagnostics</span><span class="sxs-lookup"><span data-stu-id="3428a-285">PSDiagnostics</span></span>
- <span data-ttu-id="3428a-286">PSReadline</span><span class="sxs-lookup"><span data-stu-id="3428a-286">PSReadline</span></span>

## <a name="logging-module-events"></a><span data-ttu-id="3428a-287">Log de eventos do módulo</span><span class="sxs-lookup"><span data-stu-id="3428a-287">Logging Module Events</span></span>

<span data-ttu-id="3428a-288">A partir do PowerShell 3,0, você pode registrar eventos de execução para os cmdlets e funções nos módulos e snap-ins do PowerShell definindo a propriedade **LogPipelineExecutionDetails** de módulos e snap-ins no `$True` .</span><span class="sxs-lookup"><span data-stu-id="3428a-288">Beginning in PowerShell 3.0, you can record execution events for the cmdlets and functions in PowerShell modules and snap-ins by setting the **LogPipelineExecutionDetails** property of modules and snap-ins to `$True`.</span></span>
<span data-ttu-id="3428a-289">Você também pode usar uma configuração de Política de Grupo, ativar o registro em log de módulo para habilitar o log de módulo em todas as sessões do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3428a-289">You can also use a Group Policy setting, Turn on Module Logging, to enable module logging in all PowerShell sessions.</span></span> <span data-ttu-id="3428a-290">Para obter mais informações, consulte os artigos sobre registro em log e política de grupo.</span><span class="sxs-lookup"><span data-stu-id="3428a-290">For more information, see the logging and group policy articles.</span></span>

## <a name="see-also"></a><span data-ttu-id="3428a-291">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3428a-291">See Also</span></span>

[<span data-ttu-id="3428a-292">about_Logging_Windows</span><span class="sxs-lookup"><span data-stu-id="3428a-292">about_Logging_Windows</span></span>](about_Logging_Windows.md)

[<span data-ttu-id="3428a-293">about_Logging_Non-Windows</span><span class="sxs-lookup"><span data-stu-id="3428a-293">about_Logging_Non-Windows</span></span>](about_Logging_Non-Windows.md)

[<span data-ttu-id="3428a-294">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="3428a-294">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="3428a-295">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="3428a-295">about_Command_Precedence</span></span>](about_Command_Precedence.md)

[<span data-ttu-id="3428a-296">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="3428a-296">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="3428a-297">Get-Command</span><span class="sxs-lookup"><span data-stu-id="3428a-297">Get-Command</span></span>](xref:Microsoft.PowerShell.Core.Get-Command)

[<span data-ttu-id="3428a-298">Get-Help</span><span class="sxs-lookup"><span data-stu-id="3428a-298">Get-Help</span></span>](xref:Microsoft.PowerShell.Core.Get-Help)

[<span data-ttu-id="3428a-299">Get-Module</span><span class="sxs-lookup"><span data-stu-id="3428a-299">Get-Module</span></span>](xref:Microsoft.PowerShell.Core.Get-Module)

[<span data-ttu-id="3428a-300">Import-Module</span><span class="sxs-lookup"><span data-stu-id="3428a-300">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)

[<span data-ttu-id="3428a-301">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="3428a-301">Remove-Module</span></span>](xref:Microsoft.PowerShell.Core.Remove-Module)
