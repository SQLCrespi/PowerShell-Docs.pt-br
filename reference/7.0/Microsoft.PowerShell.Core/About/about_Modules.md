---
description: Explica como instalar, importar e usar módulos do PowerShell.
Locale: en-US
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_modules?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Modules
ms.openlocfilehash: ab4e9658ed4820c3ae84ac1cd9a55b59cc8017ab
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2020
ms.locfileid: "96564472"
---
# <a name="about-modules"></a><span data-ttu-id="fd1b1-103">Sobre os módulos</span><span class="sxs-lookup"><span data-stu-id="fd1b1-103">About Modules</span></span>

## <a name="short-description"></a><span data-ttu-id="fd1b1-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="fd1b1-104">Short Description</span></span>
<span data-ttu-id="fd1b1-105">Explica como instalar, importar e usar módulos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-105">Explains how to install, import, and use PowerShell modules.</span></span>

## <a name="long-description"></a><span data-ttu-id="fd1b1-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="fd1b1-106">Long Description</span></span>

<span data-ttu-id="fd1b1-107">Um módulo é um pacote que contém membros do PowerShell, como cmdlets, provedores, funções, fluxos de trabalho, variáveis e aliases.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-107">A module is a package that contains PowerShell members, such as cmdlets, providers, functions, workflows, variables, and aliases.</span></span>

<span data-ttu-id="fd1b1-108">As pessoas que escrevem comandos podem usar módulos para organizar seus comandos e compartilhá-los com outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-108">People who write commands can use modules to organize their commands and share them with others.</span></span> <span data-ttu-id="fd1b1-109">As pessoas que recebem módulos podem adicionar os comandos nos módulos às suas sessões do PowerShell e usá-los exatamente como os comandos internos.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-109">People who receive modules can add the commands in the modules to their PowerShell sessions and use them just like the built-in commands.</span></span>

<span data-ttu-id="fd1b1-110">Este tópico explica como usar os módulos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-110">This topic explains how to use PowerShell modules.</span></span> <span data-ttu-id="fd1b1-111">Para obter informações sobre como escrever módulos do PowerShell, consulte [escrevendo um módulo do PowerShell](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span><span class="sxs-lookup"><span data-stu-id="fd1b1-111">For information about how to write PowerShell modules, see [Writing a PowerShell Module](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span></span>

## <a name="what-is-a-module"></a><span data-ttu-id="fd1b1-112">O que é um módulo?</span><span class="sxs-lookup"><span data-stu-id="fd1b1-112">What Is a Module?</span></span>

<span data-ttu-id="fd1b1-113">Um módulo é um pacote que contém membros do PowerShell, como cmdlets, provedores, funções, fluxos de trabalho, variáveis e aliases.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-113">A module is a package that contains PowerShell members, such as cmdlets, providers, functions, workflows, variables, and aliases.</span></span> <span data-ttu-id="fd1b1-114">Os membros desse pacote podem ser implementados em um script do PowerShell, uma DLL compilada ou uma combinação de ambos.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-114">The members of this package can be implemented in a PowerShell script, a compiled DLL, or a combination of both.</span></span> <span data-ttu-id="fd1b1-115">Esses arquivos geralmente são agrupados em um único diretório.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-115">These files are usually grouped together in a single directory.</span></span> <span data-ttu-id="fd1b1-116">Para obter mais informações, consulte [noções básicas sobre um módulo do Windows PowerShell](/powershell/scripting/developer/module/understanding-a-windows-powershell-module) na documentação do SDK do.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-116">For more information, see [Understanding a Windows PowerShell Module](/powershell/scripting/developer/module/understanding-a-windows-powershell-module) in the SDK documentation.</span></span>

## <a name="module-auto-loading"></a><span data-ttu-id="fd1b1-117">Módulo de carregamento automático</span><span class="sxs-lookup"><span data-stu-id="fd1b1-117">Module Auto-Loading</span></span>

<span data-ttu-id="fd1b1-118">A partir do PowerShell 3,0, o PowerShell importa módulos automaticamente na primeira vez que você executa qualquer comando em um módulo instalado.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-118">Beginning in PowerShell 3.0, PowerShell imports modules automatically the first time that you run any command in an installed module.</span></span> <span data-ttu-id="fd1b1-119">Agora você pode usar os comandos em um módulo sem qualquer configuração de instalação ou perfil; portanto, não é necessário gerenciar módulos depois de instalá-los em seu computador.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-119">You can now use the commands in a module without any set-up or profile configuration, so there's no need to manage modules after you install them on your computer.</span></span>

<span data-ttu-id="fd1b1-120">Os comandos em um módulo também são mais fáceis de localizar.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-120">The commands in a module are also easier to find.</span></span> <span data-ttu-id="fd1b1-121">O `Get-Command` cmdlet agora Obtém todos os comandos em todos os módulos instalados, mesmo que eles ainda não estejam na sessão.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-121">The `Get-Command` cmdlet now gets all commands in all installed modules, even if they are not yet in the session.</span></span> <span data-ttu-id="fd1b1-122">Você pode encontrar um comando e usá-lo sem importar a necessidade de importar o módulo primeiro.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-122">You can find a command and use it without importing needing to import the module first.</span></span>

<span data-ttu-id="fd1b1-123">Cada um dos exemplos a seguir faz com que o módulo CimCmdlets, que contém `Get-CimInstance` , seja importado para sua sessão.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-123">Each of the following examples cause the CimCmdlets module, which contains `Get-CimInstance`, to be imported into your session.</span></span>

- <span data-ttu-id="fd1b1-124">Execute o comando</span><span class="sxs-lookup"><span data-stu-id="fd1b1-124">Run the Command</span></span>

  ```powershell
  Get-CimInstance Win32_OperatingSystem
  ```

- <span data-ttu-id="fd1b1-125">Obter o comando</span><span class="sxs-lookup"><span data-stu-id="fd1b1-125">Get the Command</span></span>

  ```powershell
  Get-Command Get-CimInstance
  ```

- <span data-ttu-id="fd1b1-126">Obter ajuda para o comando</span><span class="sxs-lookup"><span data-stu-id="fd1b1-126">Get Help for the Command</span></span>

  ```powershell
  Get-Help Get-CimInstance
  ```

<span data-ttu-id="fd1b1-127">`Get-Command` os comandos que incluem um caractere curinga ( `*` ) são considerados para descoberta, não para uso e não importam nenhum módulo.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-127">`Get-Command` commands that include a wildcard character (`*`) are considered to be for discovery, not use, and do not import any modules.</span></span>

<span data-ttu-id="fd1b1-128">Somente os módulos armazenados no local especificado pela variável de ambiente PSModulePath são automaticamente importados.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-128">Only modules that are stored in the location specified by the PSModulePath environment variable are automatically imported.</span></span> <span data-ttu-id="fd1b1-129">Os módulos em outros locais devem ser importados executando o `Import-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-129">Modules in other locations must be imported by running the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="fd1b1-130">Além disso, os comandos que usam provedores do PowerShell não importam automaticamente um módulo.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-130">Also, commands that use PowerShell providers do not automatically import a module.</span></span> <span data-ttu-id="fd1b1-131">Por exemplo, se você usar um comando que exija a unidade WSMan:, como o `Get-PSSessionConfiguration` cmdlet, talvez seja necessário executar o `Import-Module` cmdlet para importar o módulo **Microsoft. WSMan. Management** que inclui a `WSMan:` unidade.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-131">For example, if you use a command that requires the WSMan: drive, such as the `Get-PSSessionConfiguration` cmdlet, you might need to run the `Import-Module` cmdlet to import the **Microsoft.WSMan.Management** module that includes the `WSMan:` drive.</span></span>

<span data-ttu-id="fd1b1-132">Você ainda pode executar o `Import-Module` comando para importar um módulo e usar a `$PSModuleAutoloadingPreference` variável para habilitar, desabilitar e configurar a importação automática de módulos.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-132">You can still run the `Import-Module` command to import a module and use the `$PSModuleAutoloadingPreference` variable to enable, disable and configure automatic importing of modules.</span></span> <span data-ttu-id="fd1b1-133">Para obter mais informações, consulte [about_Preference_Variables](about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="fd1b1-133">For more information, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

## <a name="how-to-use-a-module"></a><span data-ttu-id="fd1b1-134">Como usar um módulo</span><span class="sxs-lookup"><span data-stu-id="fd1b1-134">How to Use a Module</span></span>

<span data-ttu-id="fd1b1-135">Para usar um módulo, execute as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="fd1b1-135">To use a module, perform the following tasks:</span></span>

1. <span data-ttu-id="fd1b1-136">Instale o módulo.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-136">Install the module.</span></span> <span data-ttu-id="fd1b1-137">(Isso é geralmente feito para você.)</span><span class="sxs-lookup"><span data-stu-id="fd1b1-137">(This is often done for you.)</span></span>
1. <span data-ttu-id="fd1b1-138">Localize os comandos que o módulo adicionou.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-138">Find the commands that the module added.</span></span>
1. <span data-ttu-id="fd1b1-139">Use os comandos que o módulo adicionou.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-139">Use the commands that the module added.</span></span>

<span data-ttu-id="fd1b1-140">Este tópico explica como executar essas tarefas.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-140">This topic explains how to perform these tasks.</span></span> <span data-ttu-id="fd1b1-141">Ele também inclui outras informações úteis sobre o gerenciamento de módulos.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-141">It also includes other useful information about managing modules.</span></span>

## <a name="how-to-install-a-module"></a><span data-ttu-id="fd1b1-142">Como instalar um módulo</span><span class="sxs-lookup"><span data-stu-id="fd1b1-142">How to Install a Module</span></span>

<span data-ttu-id="fd1b1-143">Se você receber um módulo como uma pasta com arquivos, será necessário instalá-lo em seu computador antes de poder usá-lo no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-143">If you receive a module as a folder with files in it, you need to install it on your computer before you can use it in PowerShell.</span></span>

<span data-ttu-id="fd1b1-144">A maioria dos módulos é instalada por você.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-144">Most modules are installed for you.</span></span> <span data-ttu-id="fd1b1-145">O PowerShell vem com vários módulos pré-instalados, às vezes chamados de módulos _principais_ .</span><span class="sxs-lookup"><span data-stu-id="fd1b1-145">PowerShell comes with several preinstalled modules, sometimes called the _core_ modules.</span></span> <span data-ttu-id="fd1b1-146">Em computadores baseados no Windows, se os recursos incluídos no sistema operacional tiverem cmdlets para gerenciá-los, esses módulos serão pré-instalados.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-146">On Windows-based computers, if features that are included with the operating system have cmdlets to manage them, those modules are preinstalled.</span></span> <span data-ttu-id="fd1b1-147">Quando você instala um recurso do Windows, usando, por exemplo, o assistente Adicionar funções e recursos no Gerenciador do Servidor ou a caixa de diálogo ativar ou desativar recursos do Windows no painel de controle, todos os módulos do PowerShell que fazem parte do recurso são instalados.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-147">When you install a Windows feature, by using, for example, the Add Roles and Features Wizard in Server Manager, or the Turn Windows features on or off dialog box in Control Panel, any PowerShell modules that are part of the feature are installed.</span></span> <span data-ttu-id="fd1b1-148">Muitos outros módulos têm um instalador ou um programa de Instalação que instala o módulo.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-148">Many other modules come in an installer or Setup program that installs the module.</span></span>

<span data-ttu-id="fd1b1-149">Use o seguinte comando para criar um diretório de **módulos** para o usuário atual:</span><span class="sxs-lookup"><span data-stu-id="fd1b1-149">Use the following command to create a **Modules** directory for the current user:</span></span>

```powershell
New-Item -Type Directory -Path $HOME\Documents\PowerShell\Modules
```

<span data-ttu-id="fd1b1-150">Copie a pasta de módulo inteira para o diretório Modules.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-150">Copy the entire module folder into the Modules directory.</span></span> <span data-ttu-id="fd1b1-151">Você pode usar qualquer método para copiar a pasta, incluindo o Windows Explorer e Cmd.exe, bem como o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-151">You can use any method to copy the folder, including Windows Explorer and Cmd.exe, as well as PowerShell.</span></span> <span data-ttu-id="fd1b1-152">No PowerShell, use o `Copy-Item` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-152">In PowerShell use the `Copy-Item` cmdlet.</span></span> <span data-ttu-id="fd1b1-153">Por exemplo, para copiar a pasta MyModule de `C:\ps-test\MyModule` para o diretório Modules, digite:</span><span class="sxs-lookup"><span data-stu-id="fd1b1-153">For example, to copy the MyModule folder from `C:\ps-test\MyModule` to the Modules directory, type:</span></span>

```powershell
Copy-Item -Path C:\ps-test\MyModule -Destination `
    $HOME\Documents\PowerShell\Modules
```

<span data-ttu-id="fd1b1-154">Você pode instalar um módulo em qualquer local, mas instalar os módulos em um local padrão de módulo torna-os mais fáceis de gerenciar.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-154">You can install a module in any location, but installing your modules in a default module location makes them easier to manage.</span></span> <span data-ttu-id="fd1b1-155">Para obter mais informações sobre os locais de módulo padrão, consulte o [módulo e os locais de recursos de DSC e](#module-and-dsc-resource-locations-and-psmodulepath) a seção PSModulePath.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-155">For more information about the default module locations, see the [Module and DSC Resource Locations, and PSModulePath](#module-and-dsc-resource-locations-and-psmodulepath) section.</span></span>

## <a name="how-to-find-installed-modules"></a><span data-ttu-id="fd1b1-156">Como localizar os módulos instalados</span><span class="sxs-lookup"><span data-stu-id="fd1b1-156">How to Find Installed Modules</span></span>

<span data-ttu-id="fd1b1-157">Para localizar os módulos que são instalados em um local de módulo padrão, mas ainda não foram importados para a sessão, digite:</span><span class="sxs-lookup"><span data-stu-id="fd1b1-157">To find modules that are installed in a default module location, but not yet imported into your session, type:</span></span>

```powershell
Get-Module -ListAvailable
```

<span data-ttu-id="fd1b1-158">Para localizar os módulos que já foram importados para a sessão, no prompt do PowerShell, digite:</span><span class="sxs-lookup"><span data-stu-id="fd1b1-158">To find the modules that have already been imported into your session, at the PowerShell prompt, type:</span></span>

```powershell
Get-Module
```

<span data-ttu-id="fd1b1-159">Para obter mais informações sobre o `Get-Module` cmdlet, consulte [obter-módulo](xref:Microsoft.PowerShell.Core.Get-Module).</span><span class="sxs-lookup"><span data-stu-id="fd1b1-159">For more information about the `Get-Module` cmdlet, see [Get-Module](xref:Microsoft.PowerShell.Core.Get-Module).</span></span>

## <a name="how-to-find-the-commands-in-a-module"></a><span data-ttu-id="fd1b1-160">Como localizar os comandos em um módulo</span><span class="sxs-lookup"><span data-stu-id="fd1b1-160">How to Find the Commands in a Module</span></span>

<span data-ttu-id="fd1b1-161">Use o `Get-Command` cmdlet para localizar todos os comandos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-161">Use the `Get-Command` cmdlet to find all available commands.</span></span> <span data-ttu-id="fd1b1-162">Você pode usar os parâmetros do `Get-Command` cmdlet para filtrar comandos, como por módulo, nome e substantivo.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-162">You can use the parameters of the `Get-Command` cmdlet to filter commands such as by module, name, and noun.</span></span>

<span data-ttu-id="fd1b1-163">Para localizar todos os comandos em um módulo, digite:</span><span class="sxs-lookup"><span data-stu-id="fd1b1-163">To find all commands in a module, type:</span></span>

```powershell
Get-Command -Module <module-name>
```

<span data-ttu-id="fd1b1-164">Por exemplo, para localizar os comandos no módulo BitsTransfer, digite:</span><span class="sxs-lookup"><span data-stu-id="fd1b1-164">For example, to find the commands in the BitsTransfer module, type:</span></span>

```powershell
Get-Command -Module BitsTransfer
```

<span data-ttu-id="fd1b1-165">Para obter mais informações sobre o `Get-Command` cmdlet, consulte [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command).</span><span class="sxs-lookup"><span data-stu-id="fd1b1-165">For more information about the `Get-Command` cmdlet, see [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command).</span></span>

## <a name="how-to-get-help-for-the-commands-in-a-module"></a><span data-ttu-id="fd1b1-166">Como obter ajuda para os comandos em um módulo</span><span class="sxs-lookup"><span data-stu-id="fd1b1-166">How to Get Help for the Commands in a Module</span></span>

<span data-ttu-id="fd1b1-167">Se o módulo contiver arquivos de ajuda para os comandos que ele exporta, o `Get-Help` cmdlet exibirá os tópicos da ajuda.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-167">If the module contains Help files for the commands that it exports, the `Get-Help` cmdlet will display the Help topics.</span></span> <span data-ttu-id="fd1b1-168">Use o mesmo `Get-Help` formato de comando que você usaria para obter ajuda para qualquer comando no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-168">Use the same `Get-Help` command format that you would use to get help for any command in PowerShell.</span></span>

<span data-ttu-id="fd1b1-169">A partir do PowerShell 3,0, você pode baixar arquivos de ajuda para um módulo e baixar atualizações para os arquivos de ajuda para que eles nunca sejam obsoletos.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-169">Beginning in PowerShell 3.0, you can download Help files for a module and download updates to the Help files so they are never obsolete.</span></span>

<span data-ttu-id="fd1b1-170">Para obter ajuda para os comandos em um módulo, digite:</span><span class="sxs-lookup"><span data-stu-id="fd1b1-170">To get help for a commands in a module, type:</span></span>

```powershell
Get-Help <command-name>
```

<span data-ttu-id="fd1b1-171">Para obter ajuda online para o comando em um módulo, digite:</span><span class="sxs-lookup"><span data-stu-id="fd1b1-171">To get help online for command in a module, type:</span></span>

```powershell
Get-Help <command-name> -Online
```

<span data-ttu-id="fd1b1-172">Para baixar e instalar os arquivos de ajuda para os comandos em um módulo, digite:</span><span class="sxs-lookup"><span data-stu-id="fd1b1-172">To download and install the help files for the commands in a module, type:</span></span>

```powershell
Update-Help -Module <module-name>
```

<span data-ttu-id="fd1b1-173">Para obter mais informações, consulte [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) e [Update-Help](xref:Microsoft.PowerShell.Core.Update-Help).</span><span class="sxs-lookup"><span data-stu-id="fd1b1-173">For more information, see [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) and [Update-Help](xref:Microsoft.PowerShell.Core.Update-Help).</span></span>

## <a name="how-to-import-a-module"></a><span data-ttu-id="fd1b1-174">Como importar um módulo</span><span class="sxs-lookup"><span data-stu-id="fd1b1-174">How to Import a Module</span></span>

<span data-ttu-id="fd1b1-175">Você pode precisar importar um módulo ou importar um arquivo de módulo.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-175">You might have to import a module or import a module file.</span></span> <span data-ttu-id="fd1b1-176">A importação é necessária quando um módulo não está instalado nos locais especificados pela variável de ambiente **PSModulePath** , `$env:PSModulePath` ou o módulo consiste em um arquivo, como um arquivo. dll ou. psm1, em vez de um módulo típico que é entregue como uma pasta.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-176">Importing is required when a module is not installed in the locations specified by the **PSModulePath** environment variable, `$env:PSModulePath`, or the module consists of file, such as a .dll or .psm1 file, instead of typical module that is delivered as a folder.</span></span>

<span data-ttu-id="fd1b1-177">Você também pode optar por importar um módulo para que possa usar os parâmetros do `Import-Module` comando, como o parâmetro Prefix, que adiciona um prefixo distintivo aos nomes de substantivo de todos os comandos importados, ou o parâmetro **NoClobber** , que impede que o módulo adicione comandos que ocultam ou substituem os comandos existentes na sessão.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-177">You might also choose to import a module so that you can use the parameters of the `Import-Module` command, such as the Prefix parameter, which adds a distinctive prefix to the noun names of all imported commands, or the **NoClobber** parameter, which prevents the module from adding commands that would hide or replace existing commands in the session.</span></span>

<span data-ttu-id="fd1b1-178">Para importar módulos, use o `Import-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-178">To import modules, use the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="fd1b1-179">Para importar os módulos em um local de PSModulePath para a sessão atual, use o seguinte formato de comando.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-179">To import modules in a PSModulePath location into the current session, use the following command format.</span></span>

```powershell
Import-Module <module-name>
```

<span data-ttu-id="fd1b1-180">Por exemplo, o comando a seguir importa o módulo BitsTransfer para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-180">For example, the following command imports the BitsTransfer module into the current session.</span></span>

```powershell
Import-Module BitsTransfer
```

<span data-ttu-id="fd1b1-181">Para importar um módulo que não está em um local padrão de módulo, use o caminho totalmente qualificado para a pasta de módulo no comando.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-181">To import a module that is not in a default module location, use the fully qualified path to the module folder in the command.</span></span>

<span data-ttu-id="fd1b1-182">Por exemplo, para adicionar o módulo TestCmdlets no `C:\ps-test` diretório à sua sessão, digite:</span><span class="sxs-lookup"><span data-stu-id="fd1b1-182">For example, to add the TestCmdlets module in the `C:\ps-test` directory to your session, type:</span></span>

```powershell
Import-Module C:\ps-test\TestCmdlets
```

<span data-ttu-id="fd1b1-183">Para importar um arquivo de módulo que não está contido em uma pasta de módulo, use o caminho totalmente qualificado para o arquivo de módulo no comando.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-183">To import a module file that is not contained in a module folder, use the fully qualified path to the module file in the command.</span></span>

<span data-ttu-id="fd1b1-184">Por exemplo, para adicionar o módulo TestCmdlets.dll no `C:\ps-test` diretório à sua sessão, digite:</span><span class="sxs-lookup"><span data-stu-id="fd1b1-184">For example, to add the TestCmdlets.dll module in the `C:\ps-test` directory to your session, type:</span></span>

```powershell
Import-Module C:\ps-test\TestCmdlets.dll
```

<span data-ttu-id="fd1b1-185">Para obter mais informações sobre como adicionar módulos à sua sessão, consulte [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module).</span><span class="sxs-lookup"><span data-stu-id="fd1b1-185">For more information about adding modules to your session, see [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module).</span></span>

## <a name="how-to-import-a-module-into-every-session"></a><span data-ttu-id="fd1b1-186">Como importar um módulo para cada sessão</span><span class="sxs-lookup"><span data-stu-id="fd1b1-186">How to Import a Module into Every Session</span></span>

<span data-ttu-id="fd1b1-187">O `Import-Module` comando importa módulos para sua sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-187">The `Import-Module` command imports modules into your current PowerShell session.</span></span> <span data-ttu-id="fd1b1-188">Para importar um módulo para cada sessão do PowerShell que você iniciar, adicione o `Import-Module` comando ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-188">To import a module into every PowerShell session that you start, add the `Import-Module` command to your PowerShell profile.</span></span>

<span data-ttu-id="fd1b1-189">Para obter mais informações sobre perfis, consulte [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="fd1b1-189">For more information about profiles, see [about_Profiles](about_Profiles.md).</span></span>

## <a name="how-to-remove-a-module"></a><span data-ttu-id="fd1b1-190">Como remover um módulo</span><span class="sxs-lookup"><span data-stu-id="fd1b1-190">How to Remove a Module</span></span>

<span data-ttu-id="fd1b1-191">Quando você remove um módulo, os comandos que o módulo adicionou são excluídos da sessão.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-191">When you remove a module, the commands that the module added are deleted from the session.</span></span>

<span data-ttu-id="fd1b1-192">Para remover um módulo da sua sessão, use o seguinte formato de comando.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-192">To remove a module from your session, use the following command format.</span></span>

```powershell
Remove-Module <module-name>
```

<span data-ttu-id="fd1b1-193">Por exemplo, o comando a seguir remove o módulo BitsTransfer da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-193">For example, the following command removes the BitsTransfer module from the current session.</span></span>

```powershell
Remove-Module BitsTransfer
```

<span data-ttu-id="fd1b1-194">Remover um módulo inverte a operação de importação de um módulo.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-194">Removing a module reverses the operation of importing a module.</span></span> <span data-ttu-id="fd1b1-195">Remover um módulo não desinstala o módulo.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-195">Removing a module does not uninstall the module.</span></span> <span data-ttu-id="fd1b1-196">Para obter mais informações, consulte [Remove-Module](xref:Microsoft.PowerShell.Core.Remove-Module).</span><span class="sxs-lookup"><span data-stu-id="fd1b1-196">For more information, see [Remove-Module](xref:Microsoft.PowerShell.Core.Remove-Module).</span></span>

## <a name="module-and-dsc-resource-locations-and-psmodulepath"></a><span data-ttu-id="fd1b1-197">Locais de recursos de módulo e DSC e PSModulePath</span><span class="sxs-lookup"><span data-stu-id="fd1b1-197">Module and DSC Resource Locations, and PSModulePath</span></span>

<span data-ttu-id="fd1b1-198">A `$env:PSModulePath` variável de ambiente contém uma lista de locais de pasta que são pesquisados para localizar módulos e recursos.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-198">The `$env:PSModulePath` environment variable contains a list of folder locations that are searched to find modules and resources.</span></span>

<span data-ttu-id="fd1b1-199">Por padrão, os locais efetivos atribuídos a `$env:PSModulePath` são:</span><span class="sxs-lookup"><span data-stu-id="fd1b1-199">By default, the effective locations assigned to `$env:PSModulePath` are:</span></span>

- <span data-ttu-id="fd1b1-200">Locais de todo o sistema: `$PSHOME\Modules`</span><span class="sxs-lookup"><span data-stu-id="fd1b1-200">System-wide locations: `$PSHOME\Modules`</span></span>

  <span data-ttu-id="fd1b1-201">Essas pastas contêm módulos que acompanham o Windows e o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-201">These folders contain modules that ship with Windows and PowerShell.</span></span>

  <span data-ttu-id="fd1b1-202">Os recursos de DSC incluídos com o PowerShell são armazenados na `$PSHOME\Modules\PSDesiredStateConfiguration\DSCResources` pasta.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-202">DSC resources that are included with PowerShell are stored in the `$PSHOME\Modules\PSDesiredStateConfiguration\DSCResources` folder.</span></span>

- <span data-ttu-id="fd1b1-203">Módulos específicos do usuário: são módulos instalados pelo usuário no escopo do usuário.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-203">User-specific modules: These are modules installed by the user in the user's scope.</span></span> <span data-ttu-id="fd1b1-204">`Install-Module` tem um parâmetro de **escopo** que permite que você especifique se o módulo está instalado para o usuário atual ou para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-204">`Install-Module` has a **Scope** parameter that allows you to specify whether the module is installed for the current user or for all users.</span></span> <span data-ttu-id="fd1b1-205">Para obter mais informações, consulte [install-Module](xref:PowerShellGet.Install-Module).</span><span class="sxs-lookup"><span data-stu-id="fd1b1-205">For more information, see [Install-Module](xref:PowerShellGet.Install-Module).</span></span>

  <span data-ttu-id="fd1b1-206">O local **CurrentUser** específico do usuário no Windows é a `PowerShell\Modules` pasta localizada no local **documentos** em seu perfil de usuário.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-206">The user-specific **CurrentUser** location on Windows is the `PowerShell\Modules` folder located in the **Documents** location in your user profile.</span></span> <span data-ttu-id="fd1b1-207">O caminho específico desse local varia de acordo com a versão do Windows e se você está usando o redirecionamento de pasta.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-207">The specific path of that location varies by version of Windows and whether or not you are using folder redirection.</span></span> <span data-ttu-id="fd1b1-208">O Microsoft OneDrive também pode alterar o local da sua pasta de **documentos** .</span><span class="sxs-lookup"><span data-stu-id="fd1b1-208">Microsoft OneDrive can also change the location of your **Documents** folder.</span></span>

  <span data-ttu-id="fd1b1-209">Por padrão, no Windows 10, esse local é `$HOME\Documents\PowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="fd1b1-209">By default, on Windows 10, that location is `$HOME\Documents\PowerShell\Modules`.</span></span> <span data-ttu-id="fd1b1-210">No Linux ou Mac, o local **CurrentUser** é `$HOME/.local/share/powershell/Modules` .</span><span class="sxs-lookup"><span data-stu-id="fd1b1-210">On Linux or Mac, the **CurrentUser** location is `$HOME/.local/share/powershell/Modules`.</span></span>

  > [!NOTE]
  > <span data-ttu-id="fd1b1-211">Você pode verificar o local da pasta **documentos** usando o seguinte comando: `[Environment]::GetFolderPath('MyDocuments')` .</span><span class="sxs-lookup"><span data-stu-id="fd1b1-211">You can verify the location of your **Documents** folder using the following command: `[Environment]::GetFolderPath('MyDocuments')`.</span></span>

- <span data-ttu-id="fd1b1-212">O local **AllUsers** está `$env:PROGRAMFILES\PowerShell\Modules` no Windows.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-212">The **AllUsers** location is `$env:PROGRAMFILES\PowerShell\Modules` on Windows.</span></span> <span data-ttu-id="fd1b1-213">No Linux ou Mac, os módulos são armazenados em `/usr/local/share/powershell/Modules` .</span><span class="sxs-lookup"><span data-stu-id="fd1b1-213">On Linux or Mac the modules are stored at `/usr/local/share/powershell/Modules`.</span></span>

> [!NOTE]
> <span data-ttu-id="fd1b1-214">Para adicionar ou alterar arquivos no `$env:Windir\System32` diretório, inicie o PowerShell com a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="fd1b1-214">To add or change files in the `$env:Windir\System32` directory, start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="fd1b1-215">Você pode alterar os locais de módulo padrão no sistema alterando o valor da variável de ambiente **PSModulePath** , `$Env:PSModulePath` .</span><span class="sxs-lookup"><span data-stu-id="fd1b1-215">You can change the default module locations on your system by changing the value of the **PSModulePath** environment variable, `$Env:PSModulePath`.</span></span> <span data-ttu-id="fd1b1-216">A variável de ambiente **PSModulePath** é modelada na variável de ambiente Path e tem o mesmo formato.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-216">The **PSModulePath** environment variable is modeled on the Path environment variable and has the same format.</span></span>

<span data-ttu-id="fd1b1-217">Para exibir os locais padrão de módulo, digite:</span><span class="sxs-lookup"><span data-stu-id="fd1b1-217">To view the default module locations, type:</span></span>

```powershell
$Env:PSModulePath
```

<span data-ttu-id="fd1b1-218">Para adicionar um local padrão de módulo, use o seguinte formato de comando.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-218">To add a default module location, use the following command format.</span></span>

```powershell
$Env:PSModulePath = $Env:PSModulePath + ";<path>"
```

<span data-ttu-id="fd1b1-219">O ponto e vírgula ( `;` ) no comando separa o novo caminho do caminho que o precede na lista.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-219">The semi-colon (`;`) in the command separates the new path from the path that precedes it in the list.</span></span>

<span data-ttu-id="fd1b1-220">Por exemplo, para adicionar o `C:\ps-test\Modules` diretório, digite:</span><span class="sxs-lookup"><span data-stu-id="fd1b1-220">For example, to add the `C:\ps-test\Modules` directory, type:</span></span>

```powershell
$Env:PSModulePath + ";C:\ps-test\Modules"
```

<span data-ttu-id="fd1b1-221">Para adicionar um local de módulo padrão no Linux ou no MacOS, use o seguinte formato de comando:</span><span class="sxs-lookup"><span data-stu-id="fd1b1-221">To add a default module location on Linux or MacOS, use the following command format:</span></span>

```powershell
$Env:PSModulePath += ":<path>"
```

<span data-ttu-id="fd1b1-222">Por exemplo, para adicionar o `/usr/local/Fabrikam/Modules` diretório ao valor da variável de ambiente **PSModulePath** , digite:</span><span class="sxs-lookup"><span data-stu-id="fd1b1-222">For example, to add the `/usr/local/Fabrikam/Modules` directory to the value of the **PSModulePath** environment variable, type:</span></span>

```powershell
$Env:PSModulePath += ":/usr/local/Fabrikam/Modules"
```

<span data-ttu-id="fd1b1-223">No Linux ou MacOS, os dois-pontos ( `:` ) no comando separam o novo caminho do caminho que o precede na lista.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-223">On Linux or MacOS, the colon (`:`) in the command separates the new path from the path that precedes it in the list.</span></span>

<span data-ttu-id="fd1b1-224">Quando você adiciona um caminho ao **PSModulePath** `Get-Module` e os `Import-Module` comandos incluem módulos nesse caminho.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-224">When you add a path to **PSModulePath**, `Get-Module` and `Import-Module` commands include modules in that path.</span></span>

<span data-ttu-id="fd1b1-225">O valor que você define afeta apenas a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-225">The value that you set affects only the current session.</span></span> <span data-ttu-id="fd1b1-226">Para fazer a alteração persistente, adicione o comando ao seu perfil do PowerShell ou use o sistema no painel de controle para alterar o valor da variável de ambiente **PSModulePath** no registro.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-226">To make the change persistent, add the command to your PowerShell profile or use System in Control Panel to change the value of the **PSModulePath** environment variable in the registry.</span></span>

<span data-ttu-id="fd1b1-227">Além disso, para fazer a alteração persistente, você também pode usar o método **SetEnvironmentVariable não** da classe **System. Environment** para adicionar um caminho à variável de ambiente **PSModulePath** .</span><span class="sxs-lookup"><span data-stu-id="fd1b1-227">Also, to make the change persistent, you can also use the **SetEnvironmentVariable** method of the **System.Environment** class to add a Path to the **PSModulePath** environment variable.</span></span>

<span data-ttu-id="fd1b1-228">Para obter mais informações sobre a variável **PSModulePath** , consulte [about_Environment_Variables](about_Environment_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="fd1b1-228">For more information about the **PSModulePath** variable, see [about_Environment_Variables](about_Environment_Variables.md).</span></span>

## <a name="modules-and-name-conflicts"></a><span data-ttu-id="fd1b1-229">Conflitos de módulos e nomes</span><span class="sxs-lookup"><span data-stu-id="fd1b1-229">Modules and Name Conflicts</span></span>

<span data-ttu-id="fd1b1-230">Os conflitos de nome ocorrem quando mais de um comando na sessão tem o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-230">Name conflicts occur when more than one command in the session has the same name.</span></span> <span data-ttu-id="fd1b1-231">Importar um módulo provoca um conflito de nome quando os comandos no módulo têm os mesmos nomes de comandos ou itens na sessão.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-231">Importing a module causes a name conflict when commands in the module have the same names as commands or items in the session.</span></span>

<span data-ttu-id="fd1b1-232">Os conflitos de nome podem resultar em comandos sendo ocultados ou substituídos.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-232">Name conflicts can result in commands being hidden or replaced.</span></span>

### <a name="hidden"></a><span data-ttu-id="fd1b1-233">Hidden</span><span class="sxs-lookup"><span data-stu-id="fd1b1-233">Hidden</span></span>

<span data-ttu-id="fd1b1-234">Um comando é ocultado quando ele não é o comando que é executado quando você digita o nome do comando, mas você pode executá-lo usando outro método, como qualificar o nome do comando com o nome do módulo ou snap-in na qual ele se originou.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-234">A command is hidden when it is not the command that runs when you type the command name, but you can run it by using another method, such as by qualifying the command name with the name of the module or snap-in in which it originated.</span></span>

### <a name="replaced"></a><span data-ttu-id="fd1b1-235">Substituído</span><span class="sxs-lookup"><span data-stu-id="fd1b1-235">Replaced</span></span>

<span data-ttu-id="fd1b1-236">Um comando é substituído quando você não pode executá-lo porque ele foi substituído por um comando com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-236">A command is replaced when you cannot run it because it has been overwritten by a command with the same name.</span></span> <span data-ttu-id="fd1b1-237">Mesmo quando você remove o módulo que causou o conflito, não é possível executar um comando substituído, a menos que você reinicie a sessão.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-237">Even when you remove the module that caused the conflict, you cannot run a replaced command unless you restart the session.</span></span>

<span data-ttu-id="fd1b1-238">`Import-Module` pode adicionar comandos que ocultam e substituem comandos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-238">`Import-Module` might add commands that hide and replace commands in the current session.</span></span> <span data-ttu-id="fd1b1-239">Além disso, os comandos na sessão podem ocultar os comandos que o módulo adicionou.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-239">Also, commands in your session can hide commands that the module added.</span></span>

<span data-ttu-id="fd1b1-240">Para detectar conflitos de nome, use o parâmetro **All** do `Get-Command` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-240">To detect name conflicts, use the **All** parameter of the `Get-Command` cmdlet.</span></span> <span data-ttu-id="fd1b1-241">A partir do PowerShell 3,0, `Get-Command` obtém somente os comandos que são executados quando você digita o nome do comando.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-241">Beginning in PowerShell 3.0, `Get-Command` gets only that commands that run when you type the command name.</span></span> <span data-ttu-id="fd1b1-242">O parâmetro **All** Obtém todos os comandos com o nome específico na sessão.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-242">The **All** parameter gets all commands with the specific name in the session.</span></span>

<span data-ttu-id="fd1b1-243">Para evitar conflitos de nome, use os parâmetros **NoClobber** ou **prefix** do `Import-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-243">To prevent name conflicts, use the **NoClobber** or **Prefix** parameters of the `Import-Module` cmdlet.</span></span> <span data-ttu-id="fd1b1-244">O parâmetro **prefix** adiciona um prefixo aos nomes dos comandos importados para que eles sejam exclusivos na sessão.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-244">The **Prefix** parameter adds a prefix to the names of imported commands so that they are unique in the session.</span></span> <span data-ttu-id="fd1b1-245">O parâmetro **NoClobber** não importa nenhum comando que oculte ou substitua os comandos existentes na sessão.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-245">The **NoClobber** parameter does not import any commands that would hide or replace existing commands in the session.</span></span>

<span data-ttu-id="fd1b1-246">Você também pode usar o **alias**, o **cmdlet**, a **função** e os parâmetros **variáveis** do `Import-Module` para selecionar apenas os comandos que deseja importar e pode excluir comandos que causam conflitos de nome em sua sessão.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-246">You can also use the **Alias**, **Cmdlet**, **Function**, and **Variable** parameters of `Import-Module` to select only the commands that you want to import, and you can exclude commands that cause name conflicts in your session.</span></span>

<span data-ttu-id="fd1b1-247">Os autores de módulo podem evitar conflitos de nome usando a propriedade **DefaultCommandPrefix** do manifesto do módulo para adicionar um prefixo padrão a todos os nomes de comando.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-247">Module authors can prevent name conflicts by using the **DefaultCommandPrefix** property of the module manifest to add a default prefix to all command names.</span></span>
<span data-ttu-id="fd1b1-248">O valor do parâmetro **prefix** tem precedência sobre o valor de **DefaultCommandPrefix**.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-248">The value of the **Prefix** parameter takes precedence over the value of **DefaultCommandPrefix**.</span></span>

<span data-ttu-id="fd1b1-249">Mesmo se um comando estiver oculto, você poderá executá-lo qualificando o nome de comando com o nome do módulo ou snap-in no qual ele foi originado.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-249">Even if a command is hidden, you can run it by qualifying the command name with the name of the module or snap-in in which it originated.</span></span>

<span data-ttu-id="fd1b1-250">As regras de precedência de comando do PowerShell determinam qual comando é executado quando a sessão inclui comandos com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-250">The PowerShell command precedence rules determine which command runs when the session includes commands with the same name.</span></span>

<span data-ttu-id="fd1b1-251">Por exemplo, quando uma sessão inclui uma função e um cmdlet com o mesmo nome, o PowerShell executa a função por padrão.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-251">For example, when a session includes a function and a cmdlet with the same name, PowerShell runs the function by default.</span></span> <span data-ttu-id="fd1b1-252">Quando a sessão inclui comandos do mesmo tipo com o mesmo nome, como dois cmdlets com o mesmo nome, por padrão, ela executa o comando adicionado mais recentemente.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-252">When the session includes commands of the same type with the same name, such as two cmdlets with the same name, by default, it runs the most recently added command.</span></span>

<span data-ttu-id="fd1b1-253">Para obter mais informações, incluindo uma explicação das regras de precedência e instruções para executar comandos ocultos, consulte [about_Command_Precedence](about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="fd1b1-253">For more information, including an explanation of the precedence rules and instructions for running hidden commands, see [about_Command_Precedence](about_Command_Precedence.md).</span></span>

## <a name="modules-and-snap-ins"></a><span data-ttu-id="fd1b1-254">Módulos e snap-ins</span><span class="sxs-lookup"><span data-stu-id="fd1b1-254">Modules and Snap-ins</span></span>

<span data-ttu-id="fd1b1-255">Você pode adicionar comandos à sua sessão por meio de módulos e snap-ins. Os módulos podem adicionar todos os tipos de comandos, incluindo cmdlets, provedores e funções, e itens, como variáveis, aliases e unidades do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-255">You can add commands to your session from modules and snap-ins. Modules can add all types of commands, including cmdlets, providers, and functions, and items, such as variables, aliases, and PowerShell drives.</span></span> <span data-ttu-id="fd1b1-256">Os Snap-ins podem adicionar apenas os cmdlets e provedores.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-256">Snap-ins can add only cmdlets and providers.</span></span>

<span data-ttu-id="fd1b1-257">Antes de remover um módulo ou snap-in da sessão, use os comandos a seguir para determinar quais comandos serão removidos.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-257">Before removing a module or snap-in from your session, use the following commands to determine which commands will be removed.</span></span>

<span data-ttu-id="fd1b1-258">Para localizar a origem de um cmdlet em sua sessão, use o seguinte formato de comando:</span><span class="sxs-lookup"><span data-stu-id="fd1b1-258">To find the source of a cmdlet in your session, use the following command format:</span></span>

```powershell
Get-Command <cmdlet-name> | Format-List -Property verb,noun,pssnapin,module
```

<span data-ttu-id="fd1b1-259">Por exemplo, para localizar a origem do `Get-Date` cmdlet, digite:</span><span class="sxs-lookup"><span data-stu-id="fd1b1-259">For example, to find the source of the `Get-Date` cmdlet, type:</span></span>

```powershell
Get-Command Get-Date | Format-List -Property verb,noun,module
```

## <a name="module-related-warnings-and-errors"></a><span data-ttu-id="fd1b1-260">Avisos e erros relacionados ao módulo</span><span class="sxs-lookup"><span data-stu-id="fd1b1-260">Module-related Warnings and Errors</span></span>

<span data-ttu-id="fd1b1-261">Os comandos exportados por um módulo devem seguir as regras de nomenclatura de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-261">The commands that a module exports should follow the PowerShell command naming rules.</span></span> <span data-ttu-id="fd1b1-262">Se o módulo que você importar exporta cmdlets ou funções que têm verbos não aprovados em seus nomes, o `Import-Module` cmdlet exibe a seguinte mensagem de aviso.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-262">If the module that you import exports cmdlets or functions that have unapproved verbs in their names, the `Import-Module` cmdlet displays the following warning message.</span></span>

> <span data-ttu-id="fd1b1-263">Aviso: alguns nomes de comando importados incluem verbos não aprovados que podem torná-los menos detectáveis.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-263">WARNING: Some imported command names include unapproved verbs which might make them less discoverable.</span></span> <span data-ttu-id="fd1b1-264">Use o parâmetro Verbose para obter mais detalhes ou digite Get-Verb para ver a lista de verbos aprovados."</span><span class="sxs-lookup"><span data-stu-id="fd1b1-264">Use the Verbose parameter for more detail or type Get-Verb to see the list of approved verbs.</span></span>

<span data-ttu-id="fd1b1-265">A mensagem é apenas um aviso.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-265">This message is only a warning.</span></span> <span data-ttu-id="fd1b1-266">O módulo completo ainda é importado, incluindo os comandos não autorizados.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-266">The complete module is still imported, including the non-conforming commands.</span></span> <span data-ttu-id="fd1b1-267">Embora a mensagem seja exibida para usuários do módulo, o problema de nomenclatura deve ser corrigido pelo autor do módulo.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-267">Although the message is displayed to module users, the naming problem should be fixed by the module author.</span></span>

<span data-ttu-id="fd1b1-268">Para suprimir a mensagem de aviso, use o parâmetro **DisableNameChecking** do `Import-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-268">To suppress the warning message, use the **DisableNameChecking** parameter of the `Import-Module` cmdlet.</span></span>

## <a name="built-in-modules-and-snap-ins"></a><span data-ttu-id="fd1b1-269">Módulos internos e snap-ins</span><span class="sxs-lookup"><span data-stu-id="fd1b1-269">Built-in Modules and Snap-ins</span></span>

<span data-ttu-id="fd1b1-270">No PowerShell 2,0 e em programas de host de estilo mais antigo no PowerShell 3,0 e posteriores, os comandos principais instalados com o PowerShell são empacotados em snap-ins que são adicionados automaticamente a todas as sessões do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-270">In PowerShell 2.0 and in older-style host programs in PowerShell 3.0 and later, the core commands that are installed with PowerShell are packaged in snap-ins that are added automatically to every PowerShell session.</span></span>

<span data-ttu-id="fd1b1-271">A partir do PowerShell 3,0, para programas de host que implementam a `InitialSessionState.CreateDefault2` API de estado de sessão inicial, o snap-in do Microsoft. PowerShell. Core é adicionado a cada sessão por padrão.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-271">Beginning in PowerShell 3.0, for host programs that implement the `InitialSessionState.CreateDefault2` initial session state API the Microsoft.PowerShell.Core snap-in is added to every session by default.</span></span> <span data-ttu-id="fd1b1-272">Os módulos são carregados automaticamente no primeiro uso.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-272">Modules are loaded automatically on first-use.</span></span>

> [!NOTE]
> <span data-ttu-id="fd1b1-273">Sessões remotas, incluindo sessões que são iniciadas usando o `New-PSSession` cmdlet, são sessões de estilo mais antigas nas quais os comandos internos são empacotados em snap-ins.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-273">Remote sessions, including sessions that are started by using the `New-PSSession` cmdlet, are older-style sessions in which the built-in commands are packaged in snap-ins.</span></span>

<span data-ttu-id="fd1b1-274">Os seguintes módulos (ou snap-ins) são instalados com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-274">The following modules (or snap-ins) are installed with PowerShell.</span></span>

- <span data-ttu-id="fd1b1-275">CimCmdlets</span><span class="sxs-lookup"><span data-stu-id="fd1b1-275">CimCmdlets</span></span>
- <span data-ttu-id="fd1b1-276">Microsoft.PowerShell.Archive</span><span class="sxs-lookup"><span data-stu-id="fd1b1-276">Microsoft.PowerShell.Archive</span></span>
- <span data-ttu-id="fd1b1-277">Microsoft.PowerShell.Core</span><span class="sxs-lookup"><span data-stu-id="fd1b1-277">Microsoft.PowerShell.Core</span></span>
- <span data-ttu-id="fd1b1-278">Microsoft.PowerShell.Diagnostics</span><span class="sxs-lookup"><span data-stu-id="fd1b1-278">Microsoft.PowerShell.Diagnostics</span></span>
- <span data-ttu-id="fd1b1-279">Microsoft.PowerShell.Host</span><span class="sxs-lookup"><span data-stu-id="fd1b1-279">Microsoft.PowerShell.Host</span></span>
- <span data-ttu-id="fd1b1-280">Microsoft.PowerShell.Management</span><span class="sxs-lookup"><span data-stu-id="fd1b1-280">Microsoft.PowerShell.Management</span></span>
- <span data-ttu-id="fd1b1-281">Microsoft.PowerShell.Security</span><span class="sxs-lookup"><span data-stu-id="fd1b1-281">Microsoft.PowerShell.Security</span></span>
- <span data-ttu-id="fd1b1-282">Microsoft.PowerShell.Utility</span><span class="sxs-lookup"><span data-stu-id="fd1b1-282">Microsoft.PowerShell.Utility</span></span>
- <span data-ttu-id="fd1b1-283">Microsoft.WSMan.Management</span><span class="sxs-lookup"><span data-stu-id="fd1b1-283">Microsoft.WSMan.Management</span></span>
- <span data-ttu-id="fd1b1-284">PackageManagement</span><span class="sxs-lookup"><span data-stu-id="fd1b1-284">PackageManagement</span></span>
- <span data-ttu-id="fd1b1-285">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="fd1b1-285">PowerShellGet</span></span>
- <span data-ttu-id="fd1b1-286">PSDesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="fd1b1-286">PSDesiredStateConfiguration</span></span>
- <span data-ttu-id="fd1b1-287">PSDiagnostics</span><span class="sxs-lookup"><span data-stu-id="fd1b1-287">PSDiagnostics</span></span>
- <span data-ttu-id="fd1b1-288">PSReadline</span><span class="sxs-lookup"><span data-stu-id="fd1b1-288">PSReadline</span></span>

## <a name="logging-module-events"></a><span data-ttu-id="fd1b1-289">Log de eventos do módulo</span><span class="sxs-lookup"><span data-stu-id="fd1b1-289">Logging Module Events</span></span>

<span data-ttu-id="fd1b1-290">A partir do PowerShell 3,0, você pode registrar eventos de execução para os cmdlets e funções nos módulos e snap-ins do PowerShell definindo a propriedade **LogPipelineExecutionDetails** de módulos e snap-ins no `$True` .</span><span class="sxs-lookup"><span data-stu-id="fd1b1-290">Beginning in PowerShell 3.0, you can record execution events for the cmdlets and functions in PowerShell modules and snap-ins by setting the **LogPipelineExecutionDetails** property of modules and snap-ins to `$True`.</span></span>
<span data-ttu-id="fd1b1-291">Você também pode usar uma configuração de Política de Grupo, ativar o registro em log de módulo para habilitar o log de módulo em todas as sessões do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-291">You can also use a Group Policy setting, Turn on Module Logging, to enable module logging in all PowerShell sessions.</span></span> <span data-ttu-id="fd1b1-292">Para obter mais informações, consulte os artigos sobre registro em log e política de grupo.</span><span class="sxs-lookup"><span data-stu-id="fd1b1-292">For more information, see the logging and group policy articles.</span></span>

## <a name="see-also"></a><span data-ttu-id="fd1b1-293">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fd1b1-293">See Also</span></span>

[<span data-ttu-id="fd1b1-294">about_Logging_Windows</span><span class="sxs-lookup"><span data-stu-id="fd1b1-294">about_Logging_Windows</span></span>](about_Logging_Windows.md)

[<span data-ttu-id="fd1b1-295">about_Logging_Non-Windows</span><span class="sxs-lookup"><span data-stu-id="fd1b1-295">about_Logging_Non-Windows</span></span>](about_Logging_Non-Windows.md)

[<span data-ttu-id="fd1b1-296">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="fd1b1-296">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="fd1b1-297">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="fd1b1-297">about_Command_Precedence</span></span>](about_Command_Precedence.md)

[<span data-ttu-id="fd1b1-298">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="fd1b1-298">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="fd1b1-299">Get-Command</span><span class="sxs-lookup"><span data-stu-id="fd1b1-299">Get-Command</span></span>](xref:Microsoft.PowerShell.Core.Get-Command)

[<span data-ttu-id="fd1b1-300">Get-Help</span><span class="sxs-lookup"><span data-stu-id="fd1b1-300">Get-Help</span></span>](xref:Microsoft.PowerShell.Core.Get-Help)

[<span data-ttu-id="fd1b1-301">Get-Module</span><span class="sxs-lookup"><span data-stu-id="fd1b1-301">Get-Module</span></span>](xref:Microsoft.PowerShell.Core.Get-Module)

[<span data-ttu-id="fd1b1-302">Import-Module</span><span class="sxs-lookup"><span data-stu-id="fd1b1-302">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)

[<span data-ttu-id="fd1b1-303">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="fd1b1-303">Remove-Module</span></span>](xref:Microsoft.PowerShell.Core.Remove-Module)
