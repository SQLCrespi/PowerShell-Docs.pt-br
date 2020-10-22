---
title: Instalar um módulo do PowerShell | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 201679c97acdccae9aa4c2be641ee1da09a8275c
ms.sourcegitcommit: d073e69708bd499ea42642b4b923ce5f11cca295
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2020
ms.locfileid: "92197818"
---
# <a name="installing-a-powershell-module"></a><span data-ttu-id="e6eea-102">Instalar um módulo do PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6eea-102">Installing a PowerShell Module</span></span>

<span data-ttu-id="e6eea-103">Depois de criar o módulo do PowerShell, provavelmente você desejará instalar o módulo em um sistema para que você ou outras pessoas possam usá-lo.</span><span class="sxs-lookup"><span data-stu-id="e6eea-103">After you have created your PowerShell module, you will likely want to install the module on a system, so that you or others may use it.</span></span> <span data-ttu-id="e6eea-104">Em termos gerais, isso consiste em copiar os arquivos do módulo (ou seja, o arquivo .psm1 ou o assembly binário, o manifesto do módulo e os outros arquivos associados) em um diretório no computador.</span><span class="sxs-lookup"><span data-stu-id="e6eea-104">Generally speaking, this consists of copying the module files (ie, the .psm1, or the binary assembly, the module manifest, and any other associated files) onto a directory on that computer.</span></span> <span data-ttu-id="e6eea-105">Em um projeto muito pequeno, isso pode ser tão simples quanto copiar e colar os arquivos com o Windows Explorer em um computador remoto; no entanto, em soluções maiores, convém usar um processo de instalação mais sofisticado.</span><span class="sxs-lookup"><span data-stu-id="e6eea-105">For a very small project, this may be as simple as copying and pasting the files with Windows Explorer onto a single remote computer; however, for larger solutions you may wish to use a more sophisticated installation process.</span></span> <span data-ttu-id="e6eea-106">Independentemente de como você obtém seu módulo no sistema, o PowerShell pode usar várias técnicas que permitirão aos usuários localizar e usar os módulos.</span><span class="sxs-lookup"><span data-stu-id="e6eea-106">Regardless of how you get your module onto the system, PowerShell can use a number of techniques that will let users find and use your modules.</span></span> <span data-ttu-id="e6eea-107">Portanto, o principal problema da instalação é garantir que o PowerShell consiga encontrar o módulo.</span><span class="sxs-lookup"><span data-stu-id="e6eea-107">Therefore, the main issue for installation is ensuring that PowerShell will be able to find your module.</span></span> <span data-ttu-id="e6eea-108">Para obter mais informações, confira [Importar um módulo do PowerShell](./importing-a-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="e6eea-108">For more information, see [Importing a PowerShell Module](./importing-a-powershell-module.md).</span></span>

## <a name="rules-for-installing-modules"></a><span data-ttu-id="e6eea-109">Regras para a instalação de módulos</span><span class="sxs-lookup"><span data-stu-id="e6eea-109">Rules for Installing Modules</span></span>

<span data-ttu-id="e6eea-110">As informações a seguir se relacionam a todos os módulos, incluindo aqueles que você cria para uso próprio, que obtém de outras partes e que você distribui para outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="e6eea-110">The following information pertains to all modules, including modules that you create for your own use, modules that you get from other parties, and modules that you distribute to others.</span></span>

### <a name="install-modules-in-psmodulepath"></a><span data-ttu-id="e6eea-111">Instalar módulos no PSModulePath</span><span class="sxs-lookup"><span data-stu-id="e6eea-111">Install Modules in PSModulePath</span></span>

<span data-ttu-id="e6eea-112">Sempre que possível, instale todos os módulos em um caminho listado na variável de ambiente **PSModulePath** ou adicione o caminho do módulo ao valor da variável de ambiente **PSModulePath**.</span><span class="sxs-lookup"><span data-stu-id="e6eea-112">Whenever possible, install all modules in a path that is listed in the **PSModulePath** environment variable or add the module path to the **PSModulePath** environment variable value.</span></span>

<span data-ttu-id="e6eea-113">A variável de ambiente **PSModulePath** ($Env:PSModulePath) contém os locais dos módulos do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6eea-113">The **PSModulePath** environment variable ($Env:PSModulePath) contains the locations of Windows PowerShell modules.</span></span> <span data-ttu-id="e6eea-114">Os cmdlets dependem do valor dessa variável de ambiente para localizar módulos.</span><span class="sxs-lookup"><span data-stu-id="e6eea-114">Cmdlets rely on the value of this environment variable to find modules.</span></span>

<span data-ttu-id="e6eea-115">Por padrão, o valor da variável de ambiente **PSModulePath** contém os diretórios de módulo de usuário e sistema a seguir, mas você pode adicionar e editar o valor.</span><span class="sxs-lookup"><span data-stu-id="e6eea-115">By default, the **PSModulePath** environment variable value contains the following system and user module directories, but you can add to and edit the value.</span></span>

- <span data-ttu-id="e6eea-116">`$PSHome\Modules` (%Windir%\System32\WindowsPowerShell\v1.0\Modules)</span><span class="sxs-lookup"><span data-stu-id="e6eea-116">`$PSHome\Modules` (%Windir%\System32\WindowsPowerShell\v1.0\Modules)</span></span>

  > [!WARNING]
  > <span data-ttu-id="e6eea-117">Esse local é reservado para módulos que acompanham o Windows.</span><span class="sxs-lookup"><span data-stu-id="e6eea-117">This location is reserved for modules that ship with Windows.</span></span> <span data-ttu-id="e6eea-118">Não instale módulos nesse local.</span><span class="sxs-lookup"><span data-stu-id="e6eea-118">Do not install modules to this location.</span></span>

- <span data-ttu-id="e6eea-119">`$Home\Documents\WindowsPowerShell\Modules` (%UserProfile%\Documents\WindowsPowerShell\Modules)</span><span class="sxs-lookup"><span data-stu-id="e6eea-119">`$Home\Documents\WindowsPowerShell\Modules` (%UserProfile%\Documents\WindowsPowerShell\Modules)</span></span>

- <span data-ttu-id="e6eea-120">`$Env:ProgramFiles\WindowsPowerShell\Modules` (%ProgramFiles%\WindowsPowerShell\Modules)</span><span class="sxs-lookup"><span data-stu-id="e6eea-120">`$Env:ProgramFiles\WindowsPowerShell\Modules` (%ProgramFiles%\WindowsPowerShell\Modules)</span></span>

  <span data-ttu-id="e6eea-121">Para obter o valor da variável de ambiente **PSModulePath**, use um dos comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="e6eea-121">To get the value of the **PSModulePath** environment variable, use either of the following commands.</span></span>

  ```powershell
  $Env:PSModulePath
  [Environment]::GetEnvironmentVariable("PSModulePath")
  ```

  <span data-ttu-id="e6eea-122">Para adicionar um caminho de módulo ao valor da variável de ambiente **PSModulePath**, use o formato de comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="e6eea-122">To add a module path to value of the **PSModulePath** environment variable value, use the following command format.</span></span> <span data-ttu-id="e6eea-123">Esse formato usa o método **SetEnvironmentVariable** da classe **System.Environment** para fazer uma alteração independente da sessão à variável de ambiente **PSModulePath**.</span><span class="sxs-lookup"><span data-stu-id="e6eea-123">This format uses the **SetEnvironmentVariable** method of the **System.Environment** class to make a session-independent change to the **PSModulePath** environment variable.</span></span>

  ```powershell
  #Save the current value in the $p variable.
  $p = [Environment]::GetEnvironmentVariable("PSModulePath")

  #Add the new path to the $p variable. Begin with a semi-colon separator.
  $p += ";C:\Program Files (x86)\MyCompany\Modules\"

  #Add the paths in $p to the PSModulePath value.
  [Environment]::SetEnvironmentVariable("PSModulePath",$p)

  ```

  > [!IMPORTANT]
  > <span data-ttu-id="e6eea-124">Depois de adicionar o caminho a **PSModulePath**, você deve transmitir uma mensagem de ambiente sobre a alteração.</span><span class="sxs-lookup"><span data-stu-id="e6eea-124">Once you have added the path to **PSModulePath**, you should broadcast an environment message about the change.</span></span> <span data-ttu-id="e6eea-125">A transmissão da alteração permite que outros aplicativos, como o Shell, adotem a alteração.</span><span class="sxs-lookup"><span data-stu-id="e6eea-125">Broadcasting the change allows other applications, such as the shell, to pick up the change.</span></span> <span data-ttu-id="e6eea-126">Para transmitir a alteração, faça com que o código de instalação do produto envie a mensagem **WM_SETTINGCHANGE** com `lParam` definido como a cadeia de caracteres "Ambiente".</span><span class="sxs-lookup"><span data-stu-id="e6eea-126">To broadcast the change, have your product installation code send a **WM_SETTINGCHANGE** message with `lParam` set to the string "Environment".</span></span> <span data-ttu-id="e6eea-127">Lembre-se de enviar a mensagem depois que o código de instalação do módulo atualizar **PSModulePath**.</span><span class="sxs-lookup"><span data-stu-id="e6eea-127">Be sure to send the message after your module installation code has updated **PSModulePath**.</span></span>

### <a name="use-the-correct-module-directory-name"></a><span data-ttu-id="e6eea-128">Usar o nome do diretório de módulo correto</span><span class="sxs-lookup"><span data-stu-id="e6eea-128">Use the Correct Module Directory Name</span></span>

<span data-ttu-id="e6eea-129">Um módulo bem formado será aquele armazenado em um diretório que tem o mesmo nome que o nome base de pelo menos um arquivo no diretório de módulo.</span><span class="sxs-lookup"><span data-stu-id="e6eea-129">A well-formed module is a module that is stored in a directory that has the same name as the base name of at least one file in the module directory.</span></span> <span data-ttu-id="e6eea-130">Se um módulo não estiver bem formado, o Windows PowerShell não o reconhecerá como um módulo.</span><span class="sxs-lookup"><span data-stu-id="e6eea-130">If a module is not well-formed, Windows PowerShell does not recognize it as a module.</span></span>

<span data-ttu-id="e6eea-131">O "nome base" de um arquivo é o nome do arquivo sem a extensão.</span><span class="sxs-lookup"><span data-stu-id="e6eea-131">The "base name" of a file is the name without the file name extension.</span></span> <span data-ttu-id="e6eea-132">Em um módulo bem formado, o nome do diretório que contém os arquivos do módulo deve corresponder ao nome base de pelo menos um arquivo no módulo.</span><span class="sxs-lookup"><span data-stu-id="e6eea-132">In a well-formed module, the name of the directory that contains the module files must match the base name of at least one file in the module.</span></span>

<span data-ttu-id="e6eea-133">Por exemplo, no módulo Fabrikam da amostra, o diretório que contém os arquivos do módulo é denominado "Fabrikam" e pelo menos um arquivo tem o nome base "Fabrikam".</span><span class="sxs-lookup"><span data-stu-id="e6eea-133">For example, in the sample Fabrikam module, the directory that contains the module files is named "Fabrikam" and at least one file has the "Fabrikam" base name.</span></span> <span data-ttu-id="e6eea-134">Neste caso, Fabrikam.psd1 e Fabrikam.dll têm o nome base "Fabrikam".</span><span class="sxs-lookup"><span data-stu-id="e6eea-134">In this case, both Fabrikam.psd1 and Fabrikam.dll have the "Fabrikam" base name.</span></span>

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

### <a name="effect-of-incorrect-installation"></a><span data-ttu-id="e6eea-135">Efeito da instalação incorreta</span><span class="sxs-lookup"><span data-stu-id="e6eea-135">Effect of Incorrect Installation</span></span>

<span data-ttu-id="e6eea-136">Se o módulo não estiver bem formado e o local dele não estiver incluído no valor da variável de ambiente **PSModulePath**, os recursos da descoberta básica do Windows PowerShell, como os indicados a seguir, não funcionarão.</span><span class="sxs-lookup"><span data-stu-id="e6eea-136">If the module is not well-formed and its location is not included in the value of the **PSModulePath** environment variable, basic discovery features of Windows PowerShell, such as the following, do not work.</span></span>

- <span data-ttu-id="e6eea-137">O recurso Carregamento Automático de Módulo não consegue importar o módulo automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e6eea-137">The Module Auto-Loading feature cannot import the module automatically.</span></span>

- <span data-ttu-id="e6eea-138">O parâmetro `ListAvailable` do cmdlet [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) não consegue localizar o módulo.</span><span class="sxs-lookup"><span data-stu-id="e6eea-138">The `ListAvailable` parameter of the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet cannot find the module.</span></span>

- <span data-ttu-id="e6eea-139">O cmdlet [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) não consegue localizar o módulo.</span><span class="sxs-lookup"><span data-stu-id="e6eea-139">The [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet cannot find the module.</span></span> <span data-ttu-id="e6eea-140">Para importar o módulo, você deve fornecer o caminho completo até o arquivo de módulo raiz ou o arquivo de manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="e6eea-140">To import the module, you must provide the full path to the root module file or module manifest file.</span></span>

  <span data-ttu-id="e6eea-141">Recursos adicionais, como os indicados a seguir, só funcionarão se o módulo for importado para a sessão.</span><span class="sxs-lookup"><span data-stu-id="e6eea-141">Additional features, such as the following, do not work unless the module is imported into the session.</span></span> <span data-ttu-id="e6eea-142">Em módulos bem formados na variável de ambiente **PSModulePath**, esses recursos funcionam mesmo quando o módulo não é importado para a sessão.</span><span class="sxs-lookup"><span data-stu-id="e6eea-142">In well-formed modules in the **PSModulePath** environment variable, these features work even when the module is not imported into the session.</span></span>

- <span data-ttu-id="e6eea-143">O cmdlet [Get-Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command) não consegue localizar comandos no módulo.</span><span class="sxs-lookup"><span data-stu-id="e6eea-143">The [Get-Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command) cmdlet cannot find commands in the module.</span></span>

- <span data-ttu-id="e6eea-144">Os cmdlets [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) e [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) não conseguem atualizar nem salvar a ajuda para o módulo.</span><span class="sxs-lookup"><span data-stu-id="e6eea-144">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets cannot update or save help for the module.</span></span>

- <span data-ttu-id="e6eea-145">O cmdlet [Show-Command](/powershell/module/Microsoft.PowerShell.Utility/Show-Command) não consegue localizar nem exibir os comandos no módulo.</span><span class="sxs-lookup"><span data-stu-id="e6eea-145">The [Show-Command](/powershell/module/Microsoft.PowerShell.Utility/Show-Command) cmdlet cannot find and display the commands in the module.</span></span>

  <span data-ttu-id="e6eea-146">Os comandos do módulo estão ausentes na janela `Show-Command` no ISE (Ambiente de Script Integrado) do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6eea-146">The commands in the module are missing from the `Show-Command` window in Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

## <a name="where-to-install-modules"></a><span data-ttu-id="e6eea-147">Onde instalar os módulos</span><span class="sxs-lookup"><span data-stu-id="e6eea-147">Where to Install Modules</span></span>

<span data-ttu-id="e6eea-148">Esta seção explica onde instalar os módulos do Windows PowerShell no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="e6eea-148">This section explains where in the file system to install Windows PowerShell modules.</span></span> <span data-ttu-id="e6eea-149">O local depende de como o módulo é usado.</span><span class="sxs-lookup"><span data-stu-id="e6eea-149">The location depends on how the module is used.</span></span>

### <a name="installing-modules-for-a-specific-user"></a><span data-ttu-id="e6eea-150">Instalar módulos para um usuário específico</span><span class="sxs-lookup"><span data-stu-id="e6eea-150">Installing Modules for a Specific User</span></span>

<span data-ttu-id="e6eea-151">Se você criar seu próprio módulo ou obtiver um módulo de terceiros, como no site da comunidade do Windows PowerShell, e quiser que o módulo fique disponível somente para sua conta de usuário, instale-o no diretório Modules específico do usuário.</span><span class="sxs-lookup"><span data-stu-id="e6eea-151">If you create your own module or get a module from another party, such as a Windows PowerShell community website, and you want the module to be available for your user account only, install the module in your user-specific Modules directory.</span></span>

`$home\Documents\WindowsPowerShell\Modules\<Module Folder>\<Module Files>`

<span data-ttu-id="e6eea-152">O diretório Modules específico do usuário é adicionado ao valor da variável de ambiente **PSModulePath** por padrão.</span><span class="sxs-lookup"><span data-stu-id="e6eea-152">The user-specific Modules directory is added to the value of the **PSModulePath** environment variable by default.</span></span>

### <a name="installing-modules-for-all-users-in-program-files"></a><span data-ttu-id="e6eea-153">Instalar módulos para todos os usuários nos Arquivos de Programas</span><span class="sxs-lookup"><span data-stu-id="e6eea-153">Installing Modules for all Users in Program Files</span></span>

<span data-ttu-id="e6eea-154">Se você quiser que um módulo fique disponível para todas as contas de usuário do computador, instale-o no local dos Arquivos de Programas.</span><span class="sxs-lookup"><span data-stu-id="e6eea-154">If you want a module to be available to all user accounts on the computer, install the module in the Program Files location.</span></span>

`$Env:ProgramFiles\WindowsPowerShell\Modules\<Module Folder>\<Module Files>`

> [!NOTE]
> <span data-ttu-id="e6eea-155">O local dos Arquivos de Programas é adicionado por padrão ao valor da variável de ambiente PSModulePath no Windows PowerShell 4.0 e posterior.</span><span class="sxs-lookup"><span data-stu-id="e6eea-155">The Program Files location is added to the value of the PSModulePath environment variable by default in Windows PowerShell 4.0 and later.</span></span> <span data-ttu-id="e6eea-156">Para versões anteriores do Windows PowerShell, você pode criar manualmente o local dos Arquivos de Programas (%ProgramFiles%\WindowsPowerShell\Modules) e adicionar esse caminho à variável de ambiente PSModulePath, como descrito acima.</span><span class="sxs-lookup"><span data-stu-id="e6eea-156">For earlier versions of Windows PowerShell, you can manually create the Program Files location (%ProgramFiles%\WindowsPowerShell\Modules) and add this path to your PSModulePath environment variable as described above.</span></span>

### <a name="installing-modules-in-a-product-directory"></a><span data-ttu-id="e6eea-157">Instalar módulos em um diretório de produto</span><span class="sxs-lookup"><span data-stu-id="e6eea-157">Installing Modules in a Product Directory</span></span>

<span data-ttu-id="e6eea-158">Se você estiver distribuindo o módulo para terceiros, use o local padrão dos Arquivos de Programas descrito acima ou crie um subdiretório próprio específico do produto ou da empresa no diretório %ProgramFiles%.</span><span class="sxs-lookup"><span data-stu-id="e6eea-158">If you are distributing the module to other parties, use the default Program Files location described above, or create your own company-specific or product-specific subdirectory of the %ProgramFiles% directory.</span></span>

<span data-ttu-id="e6eea-159">Por exemplo, a Fabrikam Technologies, uma empresa fictícia, está enviando um módulo do Windows PowerShell para seu produto Fabrikam Manager.</span><span class="sxs-lookup"><span data-stu-id="e6eea-159">For example, Fabrikam Technologies, a fictitious company, is shipping a Windows PowerShell module for their Fabrikam Manager product.</span></span> <span data-ttu-id="e6eea-160">O instalador do módulo cria o subdiretório Modules no subdiretório do produto Fabrikam Manager.</span><span class="sxs-lookup"><span data-stu-id="e6eea-160">Their module installer creates a Modules subdirectory in the Fabrikam Manager product subdirectory.</span></span>

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

<span data-ttu-id="e6eea-161">Para habilitar os recursos de descoberta de módulo do Windows PowerShell a localizarem o módulo Fabrikam, o instalador do módulo Fabrikam adiciona o local do módulo ao valor da variável de ambiente **PSModulePath**.</span><span class="sxs-lookup"><span data-stu-id="e6eea-161">To enable the Windows PowerShell module discovery features to find the Fabrikam module, the Fabrikam module installer adds the module location to the value of the **PSModulePath** environment variable.</span></span>

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam Technologies\Fabrikam Manager\Modules\"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

### <a name="installing-modules-in-the-common-files-directory"></a><span data-ttu-id="e6eea-162">Instalar módulos no diretório de arquivos comuns</span><span class="sxs-lookup"><span data-stu-id="e6eea-162">Installing Modules in the Common Files Directory</span></span>

<span data-ttu-id="e6eea-163">Se um módulo for usado por vários componentes ou versões de um produto, instale-o em um subdiretório específico de módulo no subdiretório %ProgramFiles%\Common Files\Modules.</span><span class="sxs-lookup"><span data-stu-id="e6eea-163">If a module is used by multiple components of a product or by multiple versions of a product, install the module in a module-specific subdirectory of the %ProgramFiles%\Common Files\Modules subdirectory.</span></span>

<span data-ttu-id="e6eea-164">No exemplo a seguir, o módulo Fabrikam é instalado no subdiretório Fabrikam do subdiretório `%ProgramFiles%\Common Files\Modules`.</span><span class="sxs-lookup"><span data-stu-id="e6eea-164">In the following example, the Fabrikam module is installed in a Fabrikam subdirectory of the `%ProgramFiles%\Common Files\Modules` subdirectory.</span></span> <span data-ttu-id="e6eea-165">Observe que cada módulo reside em seu próprio subdiretório dentro do subdiretório Modules.</span><span class="sxs-lookup"><span data-stu-id="e6eea-165">Note that each module resides in its own subdirectory in the Modules subdirectory.</span></span>

```
C:\Program Files
  Common Files
    Modules
      Fabrikam
        Fabrikam.psd1 (module manifest)
        Fabrikam.dll (module assembly)
```

<span data-ttu-id="e6eea-166">O instalador garante que o valor da variável de ambiente **PSModulePath** inclua o caminho do subdiretório de módulos de arquivos comuns.</span><span class="sxs-lookup"><span data-stu-id="e6eea-166">Then, the installer assures the value of the **PSModulePath** environment variable includes the path of the common files modules subdirectory.</span></span>

```powershell
$m = $env:ProgramFiles + '\Common Files\Modules'
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$q = $p -split ';'
if ($q -notContains $m) {
    $q += ";$m"
}
$p = $q -join ';'
[Environment]::SetEnvironmentVariable("PSModulePath", $p)
```

## <a name="installing-multiple-versions-of-a-module"></a><span data-ttu-id="e6eea-167">Instalar várias versões de um módulo</span><span class="sxs-lookup"><span data-stu-id="e6eea-167">Installing Multiple Versions of a Module</span></span>

<span data-ttu-id="e6eea-168">Para instalar várias versões do mesmo módulo, use o procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="e6eea-168">To install multiple versions of the same module, use the following procedure.</span></span>

1. <span data-ttu-id="e6eea-169">Crie um diretório para cada versão do módulo.</span><span class="sxs-lookup"><span data-stu-id="e6eea-169">Create a directory for each version of the module.</span></span> <span data-ttu-id="e6eea-170">Inclua o número de versão no nome do diretório.</span><span class="sxs-lookup"><span data-stu-id="e6eea-170">Include the version number in the directory name.</span></span>
2. <span data-ttu-id="e6eea-171">Crie um manifesto do módulo para cada versão.</span><span class="sxs-lookup"><span data-stu-id="e6eea-171">Create a module manifest for each version of the module.</span></span> <span data-ttu-id="e6eea-172">No valor da chave **ModuleVersion** no manifesto, insira o número da versão do módulo.</span><span class="sxs-lookup"><span data-stu-id="e6eea-172">In the value of the **ModuleVersion** key in the manifest, enter the module version number.</span></span> <span data-ttu-id="e6eea-173">Salve o arquivo de manifesto (.psd1) no diretório específico da versão do módulo.</span><span class="sxs-lookup"><span data-stu-id="e6eea-173">Save the manifest file (.psd1) in the version-specific directory for the module.</span></span>
3. <span data-ttu-id="e6eea-174">Adicione o caminho da pasta raiz do módulo ao valor da variável de ambiente **PSModulePath**, conforme mostrado nos exemplos a seguir.</span><span class="sxs-lookup"><span data-stu-id="e6eea-174">Add the module root folder path to the value of the **PSModulePath** environment variable, as shown in the following examples.</span></span>

<span data-ttu-id="e6eea-175">Para importar uma versão específica do módulo, o usuário final pode usar os parâmetros `MinimumVersion` ou `RequiredVersion` do cmdlet [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module).</span><span class="sxs-lookup"><span data-stu-id="e6eea-175">To import a particular version of the module, the end-user can use the `MinimumVersion` or `RequiredVersion` parameters of the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet.</span></span>

<span data-ttu-id="e6eea-176">Por exemplo, se o módulo Fabrikam estiver disponível nas versões 8.0 e 9.0, a estrutura do diretório do módulo Fabrikam poderá ser semelhante à que está a seguir.</span><span class="sxs-lookup"><span data-stu-id="e6eea-176">For example, if the Fabrikam module is available in versions 8.0 and 9.0, the Fabrikam module directory structure might resemble the following.</span></span>

 ```
C:\Program Files
Fabrikam Manager
  Fabrikam8
    Fabrikam
      Fabrikam.psd1 (module manifest: ModuleVersion = "8.0")
      Fabrikam.dll (module assembly)
  Fabrikam9
    Fabrikam
      Fabrikam.psd1 (module manifest: ModuleVersion = "9.0")
      Fabrikam.dll (module assembly)
```

<span data-ttu-id="e6eea-177">O instalador adiciona os caminhos do módulo ao valor da variável de ambiente **PSModulePath**.</span><span class="sxs-lookup"><span data-stu-id="e6eea-177">The installer adds both of the module paths to the **PSModulePath** environment variable value.</span></span>

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam\Fabrikam8;C:\Program Files\Fabrikam\Fabrikam9"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

<span data-ttu-id="e6eea-178">Quando essas etapas forem concluídas, o parâmetro **ListAvailable** do cmdlet [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) obterá os dois módulos do Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="e6eea-178">When these steps are complete, the **ListAvailable** parameter of the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet gets both of the Fabrikam modules.</span></span> <span data-ttu-id="e6eea-179">Para importar um módulo específico, use os parâmetros `MinimumVersion` ou `RequiredVersion` do cmdlet [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module).</span><span class="sxs-lookup"><span data-stu-id="e6eea-179">To import a particular module, use the `MinimumVersion` or `RequiredVersion` parameters of the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet.</span></span>

<span data-ttu-id="e6eea-180">Se os dois módulos forem importados na mesma sessão e contiverem cmdlets com os mesmos nomes, os cmdlets importados por último estarão em vigor na sessão.</span><span class="sxs-lookup"><span data-stu-id="e6eea-180">If both modules are imported into the same session, and the modules contain cmdlets with the same names, the cmdlets that are imported last are effective in the session.</span></span>

## <a name="handling-command-name-conflicts"></a><span data-ttu-id="e6eea-181">Manipular conflitos de nome de comando</span><span class="sxs-lookup"><span data-stu-id="e6eea-181">Handling Command Name Conflicts</span></span>

<span data-ttu-id="e6eea-182">Conflitos de nome de comando podem ocorrer quando os comandos que um módulo exporta têm o mesmo nome dos comandos da sessão do usuário.</span><span class="sxs-lookup"><span data-stu-id="e6eea-182">Command name conflicts can occur when the commands that a module exports have the same name as commands in the user's session.</span></span>

<span data-ttu-id="e6eea-183">Quando uma sessão contém dois comandos com o mesmo nome, o Windows PowerShell executa o tipo de comando que tem precedência.</span><span class="sxs-lookup"><span data-stu-id="e6eea-183">When a session contains two commands that have the same name, Windows PowerShell runs the command type that takes precedence.</span></span> <span data-ttu-id="e6eea-184">Quando uma sessão contém dois comandos com o mesmo nome e o mesmo tipo, o Windows PowerShell executa o comando adicionado por último à sessão.</span><span class="sxs-lookup"><span data-stu-id="e6eea-184">When a session contains two commands that have the same name and the same type, Windows PowerShell runs the command that was added to the session most recently.</span></span> <span data-ttu-id="e6eea-185">Para executar um comando que não é executado por padrão, os usuários podem qualificar o nome do comando com o nome do módulo.</span><span class="sxs-lookup"><span data-stu-id="e6eea-185">To run a command that is not run by default, users can qualify the command name with the module name.</span></span>

<span data-ttu-id="e6eea-186">Por exemplo, se a sessão contiver a função `Get-Date` e o cmdlet `Get-Date`, o Windows PowerShell executará a função por padrão.</span><span class="sxs-lookup"><span data-stu-id="e6eea-186">For example, if the session contains a `Get-Date` function and the `Get-Date` cmdlet, Windows PowerShell runs the function by default.</span></span> <span data-ttu-id="e6eea-187">Para executar o cmdlet, inicie o comando com o nome do módulo, como:</span><span class="sxs-lookup"><span data-stu-id="e6eea-187">To run the cmdlet, preface the command with the module name, such as:</span></span>

```powershell
Microsoft.PowerShell.Utility\Get-Date
```

<span data-ttu-id="e6eea-188">Para evitar conflitos de nome, os autores de módulos podem usar a chave **DefaultCommandPrefix** no manifesto do módulo a fim de especificar um prefixo de substantivo para todos os comandos exportados do módulo.</span><span class="sxs-lookup"><span data-stu-id="e6eea-188">To prevent name conflicts, module authors can use the **DefaultCommandPrefix** key in the module manifest to specify a noun prefix for all commands exported from the module.</span></span>

<span data-ttu-id="e6eea-189">Os usuários podem usar o parâmetro **Prefix** do cmdlet `Import-Module` para usar um prefixo alternativo.</span><span class="sxs-lookup"><span data-stu-id="e6eea-189">Users can use the **Prefix** parameter of the `Import-Module` cmdlet to use an alternate prefix.</span></span> <span data-ttu-id="e6eea-190">O valor do parâmetro **Prefix** tem precedência sobre o valor da chave **DefaultCommandPrefix**.</span><span class="sxs-lookup"><span data-stu-id="e6eea-190">The value of the **Prefix** parameter takes precedence over the value of the **DefaultCommandPrefix** key.</span></span>

## <a name="see-also"></a><span data-ttu-id="e6eea-191">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e6eea-191">See Also</span></span>

[<span data-ttu-id="e6eea-192">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="e6eea-192">about_Command_Precedence</span></span>](/powershell/module/microsoft.powershell.core/about/about_command_precedence)

[<span data-ttu-id="e6eea-193">Escrever um módulo do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6eea-193">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)
