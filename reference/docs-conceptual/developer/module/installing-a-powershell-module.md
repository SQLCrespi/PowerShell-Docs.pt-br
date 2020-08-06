---
title: Instalando um módulo do PowerShell | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 6a4e9ac2884d0b300b5c1ad8b6156525438a1650
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784853"
---
# <a name="installing-a-powershell-module"></a><span data-ttu-id="c04c4-102">Instalar um módulo do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c04c4-102">Installing a PowerShell Module</span></span>

<span data-ttu-id="c04c4-103">Depois de criar o módulo do PowerShell, você provavelmente desejará instalar o módulo em um sistema, para que você ou outros usuários possam usá-lo.</span><span class="sxs-lookup"><span data-stu-id="c04c4-103">After you have created your PowerShell module, you will likely want to install the module on a system, so that you or others may use it.</span></span> <span data-ttu-id="c04c4-104">Em termos gerais, isso consiste em copiar os arquivos de módulo (ou seja, o. psm1 ou o assembly binário, o manifesto do módulo e todos os outros arquivos associados) para um diretório nesse computador.</span><span class="sxs-lookup"><span data-stu-id="c04c4-104">Generally speaking, this consists of copying the module files (ie, the .psm1, or the binary assembly, the module manifest, and any other associated files) onto a directory on that computer.</span></span> <span data-ttu-id="c04c4-105">Para um projeto muito pequeno, isso pode ser tão simples quanto copiar e colar os arquivos com o Windows Explorer em um único computador remoto; no entanto, para soluções maiores, você pode desejar usar um processo de instalação mais sofisticado.</span><span class="sxs-lookup"><span data-stu-id="c04c4-105">For a very small project, this may be as simple as copying and pasting the files with Windows Explorer onto a single remote computer; however, for larger solutions you may wish to use a more sophisticated installation process.</span></span> <span data-ttu-id="c04c4-106">Independentemente de como você obtém seu módulo no sistema, o PowerShell pode usar várias técnicas que permitirão que os usuários localizem e usem seus módulos.</span><span class="sxs-lookup"><span data-stu-id="c04c4-106">Regardless of how you get your module onto the system, PowerShell can use a number of techniques that will let users find and use your modules.</span></span> <span data-ttu-id="c04c4-107">Portanto, o principal problema para a instalação é garantir que o PowerShell poderá encontrar seu módulo.</span><span class="sxs-lookup"><span data-stu-id="c04c4-107">Therefore, the main issue for installation is ensuring that PowerShell will be able to find your module.</span></span> <span data-ttu-id="c04c4-108">Para obter mais informações, consulte [importando um módulo do PowerShell](./importing-a-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="c04c4-108">For more information, see [Importing a PowerShell Module](./importing-a-powershell-module.md).</span></span>

## <a name="rules-for-installing-modules"></a><span data-ttu-id="c04c4-109">Regras para instalação de módulos</span><span class="sxs-lookup"><span data-stu-id="c04c4-109">Rules for Installing Modules</span></span>

<span data-ttu-id="c04c4-110">As informações a seguir pertencem a todos os módulos, incluindo módulos que você cria para seu próprio uso, módulos que você obtém de outras partes e módulos que você distribui para outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="c04c4-110">The following information pertains to all modules, including modules that you create for your own use, modules that you get from other parties, and modules that you distribute to others.</span></span>

### <a name="install-modules-in-psmodulepath"></a><span data-ttu-id="c04c4-111">Instalar módulos no PSModulePath</span><span class="sxs-lookup"><span data-stu-id="c04c4-111">Install Modules in PSModulePath</span></span>

<span data-ttu-id="c04c4-112">Sempre que possível, instale todos os módulos em um caminho que esteja listado na variável de ambiente **PSModulePath** ou adicione o caminho do módulo ao valor da variável de ambiente **PSModulePath** .</span><span class="sxs-lookup"><span data-stu-id="c04c4-112">Whenever possible, install all modules in a path that is listed in the **PSModulePath** environment variable or add the module path to the **PSModulePath** environment variable value.</span></span>

<span data-ttu-id="c04c4-113">A variável de ambiente **PSModulePath** ($env:P smodulepath) contém os locais dos módulos do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c04c4-113">The **PSModulePath** environment variable ($Env:PSModulePath) contains the locations of Windows PowerShell modules.</span></span> <span data-ttu-id="c04c4-114">Os cmdlets dependem do valor dessa variável de ambiente para localizar módulos.</span><span class="sxs-lookup"><span data-stu-id="c04c4-114">Cmdlets rely on the value of this environment variable to find modules.</span></span>

<span data-ttu-id="c04c4-115">Por padrão, o valor da variável de ambiente **PSModulePath** contém os seguintes diretórios de sistema e de módulo de usuário, mas você pode adicionar e editar o valor.</span><span class="sxs-lookup"><span data-stu-id="c04c4-115">By default, the **PSModulePath** environment variable value contains the following system and user module directories, but you can add to and edit the value.</span></span>

- <span data-ttu-id="c04c4-116">`$PSHome\Modules`(%Windir%\System32\WindowsPowerShell\v1.0\Modules)</span><span class="sxs-lookup"><span data-stu-id="c04c4-116">`$PSHome\Modules` (%Windir%\System32\WindowsPowerShell\v1.0\Modules)</span></span>

  > [!WARNING]
  > <span data-ttu-id="c04c4-117">Esse local é reservado para módulos que acompanham o Windows.</span><span class="sxs-lookup"><span data-stu-id="c04c4-117">This location is reserved for modules that ship with Windows.</span></span> <span data-ttu-id="c04c4-118">Não instale módulos nesse local.</span><span class="sxs-lookup"><span data-stu-id="c04c4-118">Do not install modules to this location.</span></span>

- <span data-ttu-id="c04c4-119">`$Home\Documents\WindowsPowerShell\Modules`(%UserProfile%\Documents\WindowsPowerShell\Modules)</span><span class="sxs-lookup"><span data-stu-id="c04c4-119">`$Home\Documents\WindowsPowerShell\Modules` (%UserProfile%\Documents\WindowsPowerShell\Modules)</span></span>

- <span data-ttu-id="c04c4-120">`$Env:ProgramFiles\WindowsPowerShell\Modules`%ProgramFiles%\WindowsPowerShell\Modules</span><span class="sxs-lookup"><span data-stu-id="c04c4-120">`$Env:ProgramFiles\WindowsPowerShell\Modules` (%ProgramFiles%\WindowsPowerShell\Modules)</span></span>

  <span data-ttu-id="c04c4-121">Para obter o valor da variável de ambiente **PSModulePath** , use um dos comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="c04c4-121">To get the value of the **PSModulePath** environment variable, use either of the following commands.</span></span>

  ```powershell
  $Env:PSModulePath
  [Environment]::GetEnvironmentVariable("PSModulePath")
  ```

  <span data-ttu-id="c04c4-122">Para adicionar um caminho de módulo ao valor do valor da variável de ambiente **PSModulePath** , use o seguinte formato de comando.</span><span class="sxs-lookup"><span data-stu-id="c04c4-122">To add a module path to value of the **PSModulePath** environment variable value, use the following command format.</span></span> <span data-ttu-id="c04c4-123">Esse formato usa o método **SetEnvironmentVariable não** da classe **System. Environment** para fazer uma alteração independente de sessão na variável de ambiente **PSModulePath** .</span><span class="sxs-lookup"><span data-stu-id="c04c4-123">This format uses the **SetEnvironmentVariable** method of the **System.Environment** class to make a session-independent change to the **PSModulePath** environment variable.</span></span>

  ```powershell
  #Save the current value in the $p variable.
  $p = [Environment]::GetEnvironmentVariable("PSModulePath")

  #Add the new path to the $p variable. Begin with a semi-colon separator.
  $p += ";C:\Program Files (x86)\MyCompany\Modules\"

  #Add the paths in $p to the PSModulePath value.
  [Environment]::SetEnvironmentVariable("PSModulePath",$p)

  ```

  > [!IMPORTANT]
  > <span data-ttu-id="c04c4-124">Depois de adicionar o caminho para **PSModulePath**, você deve transmitir uma mensagem de ambiente sobre a alteração.</span><span class="sxs-lookup"><span data-stu-id="c04c4-124">Once you have added the path to **PSModulePath**, you should broadcast an environment message about the change.</span></span> <span data-ttu-id="c04c4-125">A transmissão da alteração permite que outros aplicativos, como o Shell, escolham a alteração.</span><span class="sxs-lookup"><span data-stu-id="c04c4-125">Broadcasting the change allows other applications, such as the shell, to pick up the change.</span></span> <span data-ttu-id="c04c4-126">Para difundir a alteração, peça ao código de instalação do produto para enviar uma mensagem de **WM_SETTINGCHANGE** com `lParam` definido como a cadeia de caracteres "ambiente".</span><span class="sxs-lookup"><span data-stu-id="c04c4-126">To broadcast the change, have your product installation code send a **WM_SETTINGCHANGE** message with `lParam` set to the string "Environment".</span></span> <span data-ttu-id="c04c4-127">Lembre-se de enviar a mensagem depois que o código de instalação do módulo tiver atualizado o **PSModulePath**.</span><span class="sxs-lookup"><span data-stu-id="c04c4-127">Be sure to send the message after your module installation code has updated **PSModulePath**.</span></span>

### <a name="use-the-correct-module-directory-name"></a><span data-ttu-id="c04c4-128">Usar o nome do diretório de módulo correto</span><span class="sxs-lookup"><span data-stu-id="c04c4-128">Use the Correct Module Directory Name</span></span>

<span data-ttu-id="c04c4-129">Um módulo bem formado é um módulo que é armazenado em um diretório que tem o mesmo nome que o nome base de pelo menos um arquivo no diretório do módulo.</span><span class="sxs-lookup"><span data-stu-id="c04c4-129">A well-formed module is a module that is stored in a directory that has the same name as the base name of at least one file in the module directory.</span></span> <span data-ttu-id="c04c4-130">Se um módulo não estiver bem formado, o Windows PowerShell não o reconhecerá como um módulo.</span><span class="sxs-lookup"><span data-stu-id="c04c4-130">If a module is not well-formed, Windows PowerShell does not recognize it as a module.</span></span>

<span data-ttu-id="c04c4-131">O "nome base" de um arquivo é o nome sem a extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="c04c4-131">The "base name" of a file is the name without the file name extension.</span></span> <span data-ttu-id="c04c4-132">Em um módulo bem formado, o nome do diretório que contém os arquivos de módulo deve corresponder ao nome de base de pelo menos um arquivo no módulo.</span><span class="sxs-lookup"><span data-stu-id="c04c4-132">In a well-formed module, the name of the directory that contains the module files must match the base name of at least one file in the module.</span></span>

<span data-ttu-id="c04c4-133">Por exemplo, no módulo Fabrikam de exemplo, o diretório que contém os arquivos de módulo é denominado "fabrikam" e pelo menos um arquivo tem o nome de base "fabrikam".</span><span class="sxs-lookup"><span data-stu-id="c04c4-133">For example, in the sample Fabrikam module, the directory that contains the module files is named "Fabrikam" and at least one file has the "Fabrikam" base name.</span></span> <span data-ttu-id="c04c4-134">Nesse caso, Fabrikam.psd1 e Fabrikam.dll têm o nome base "fabrikam".</span><span class="sxs-lookup"><span data-stu-id="c04c4-134">In this case, both Fabrikam.psd1 and Fabrikam.dll have the "Fabrikam" base name.</span></span>

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

### <a name="effect-of-incorrect-installation"></a><span data-ttu-id="c04c4-135">Efeito da instalação incorreta</span><span class="sxs-lookup"><span data-stu-id="c04c4-135">Effect of Incorrect Installation</span></span>

<span data-ttu-id="c04c4-136">Se o módulo não estiver bem formado e seu local não estiver incluído no valor da variável de ambiente **PSModulePath** , os recursos básicos de descoberta do Windows PowerShell, como o seguinte, não funcionarão.</span><span class="sxs-lookup"><span data-stu-id="c04c4-136">If the module is not well-formed and its location is not included in the value of the **PSModulePath** environment variable, basic discovery features of Windows PowerShell, such as the following, do not work.</span></span>

- <span data-ttu-id="c04c4-137">O recurso de carregamento automático do módulo não pode importar o módulo automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c04c4-137">The Module Auto-Loading feature cannot import the module automatically.</span></span>

- <span data-ttu-id="c04c4-138">O `ListAvailable` parâmetro do cmdlet [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) não pode localizar o módulo.</span><span class="sxs-lookup"><span data-stu-id="c04c4-138">The `ListAvailable` parameter of the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet cannot find the module.</span></span>

- <span data-ttu-id="c04c4-139">O cmdlet [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) não pode localizar o módulo.</span><span class="sxs-lookup"><span data-stu-id="c04c4-139">The [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet cannot find the module.</span></span> <span data-ttu-id="c04c4-140">Para importar o módulo, você deve fornecer o caminho completo para o arquivo de módulo raiz ou arquivo de manifesto de módulo.</span><span class="sxs-lookup"><span data-stu-id="c04c4-140">To import the module, you must provide the full path to the root module file or module manifest file.</span></span>

  <span data-ttu-id="c04c4-141">Recursos adicionais, como os seguintes, não funcionam, a menos que o módulo seja importado para a sessão.</span><span class="sxs-lookup"><span data-stu-id="c04c4-141">Additional features, such as the following, do not work unless the module is imported into the session.</span></span> <span data-ttu-id="c04c4-142">Em módulos bem formados na variável de ambiente **PSModulePath** , esses recursos funcionam mesmo quando o módulo não é importado para a sessão.</span><span class="sxs-lookup"><span data-stu-id="c04c4-142">In well-formed modules in the **PSModulePath** environment variable, these features work even when the module is not imported into the session.</span></span>

- <span data-ttu-id="c04c4-143">O cmdlet [Get-Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command) não pode localizar comandos no módulo.</span><span class="sxs-lookup"><span data-stu-id="c04c4-143">The [Get-Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command) cmdlet cannot find commands in the module.</span></span>

- <span data-ttu-id="c04c4-144">Os cmdlets [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) e [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) não podem atualizar ou salvar a ajuda do módulo.</span><span class="sxs-lookup"><span data-stu-id="c04c4-144">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets cannot update or save help for the module.</span></span>

- <span data-ttu-id="c04c4-145">O cmdlet [show-Command](/powershell/module/Microsoft.PowerShell.Utility/Show-Command) não pode localizar e exibir os comandos no módulo.</span><span class="sxs-lookup"><span data-stu-id="c04c4-145">The [Show-Command](/powershell/module/Microsoft.PowerShell.Utility/Show-Command) cmdlet cannot find and display the commands in the module.</span></span>

  <span data-ttu-id="c04c4-146">Os comandos no módulo estão ausentes na `Show-Command` janela no ambiente de script integrado do Windows PowerShell (ISE).</span><span class="sxs-lookup"><span data-stu-id="c04c4-146">The commands in the module are missing from the `Show-Command` window in Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

## <a name="where-to-install-modules"></a><span data-ttu-id="c04c4-147">Onde instalar os módulos</span><span class="sxs-lookup"><span data-stu-id="c04c4-147">Where to Install Modules</span></span>

<span data-ttu-id="c04c4-148">Esta seção explica onde no sistema de arquivos instalar os módulos do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c04c4-148">This section explains where in the file system to install Windows PowerShell modules.</span></span> <span data-ttu-id="c04c4-149">O local depende de como o módulo é usado.</span><span class="sxs-lookup"><span data-stu-id="c04c4-149">The location depends on how the module is used.</span></span>

### <a name="installing-modules-for-a-specific-user"></a><span data-ttu-id="c04c4-150">Instalando módulos para um usuário específico</span><span class="sxs-lookup"><span data-stu-id="c04c4-150">Installing Modules for a Specific User</span></span>

<span data-ttu-id="c04c4-151">Se você criar seu próprio módulo ou obter um módulo de outra parte, como um site da Comunidade do Windows PowerShell, e desejar que o módulo esteja disponível somente para sua conta de usuário, instale o módulo em seu diretório de módulos específicos do usuário.</span><span class="sxs-lookup"><span data-stu-id="c04c4-151">If you create your own module or get a module from another party, such as a Windows PowerShell community website, and you want the module to be available for your user account only, install the module in your user-specific Modules directory.</span></span>

`$home\Documents\WindowsPowerShell\Modules\<Module Folder>\<Module Files>`

<span data-ttu-id="c04c4-152">O diretório de módulos específicos do usuário é adicionado ao valor da variável de ambiente **PSModulePath** por padrão.</span><span class="sxs-lookup"><span data-stu-id="c04c4-152">The user-specific Modules directory is added to the value of the **PSModulePath** environment variable by default.</span></span>

### <a name="installing-modules-for-all-users-in-program-files"></a><span data-ttu-id="c04c4-153">Instalando módulos para todos os usuários em arquivos de programas</span><span class="sxs-lookup"><span data-stu-id="c04c4-153">Installing Modules for all Users in Program Files</span></span>

<span data-ttu-id="c04c4-154">Se você quiser que um módulo esteja disponível para todas as contas de usuário no computador, instale o módulo no local arquivos de programas.</span><span class="sxs-lookup"><span data-stu-id="c04c4-154">If you want a module to be available to all user accounts on the computer, install the module in the Program Files location.</span></span>

`$Env:ProgramFiles\WindowsPowerShell\Modules\<Module Folder>\<Module Files>`

> [!NOTE]
> <span data-ttu-id="c04c4-155">O local dos arquivos de programas é adicionado ao valor da variável de ambiente PSModulePath por padrão no Windows PowerShell 4,0 e posterior.</span><span class="sxs-lookup"><span data-stu-id="c04c4-155">The Program Files location is added to the value of the PSModulePath environment variable by default in Windows PowerShell 4.0 and later.</span></span> <span data-ttu-id="c04c4-156">Para versões anteriores do Windows PowerShell, você pode criar manualmente o local dos arquivos de programas ((%ProgramFiles%\WindowsPowerShell\Modules) e adicionar esse caminho à sua variável de ambiente PSModulePath, conforme descrito acima.</span><span class="sxs-lookup"><span data-stu-id="c04c4-156">For earlier versions of Windows PowerShell, you can manually create the Program Files location ((%ProgramFiles%\WindowsPowerShell\Modules) and add this path to your PSModulePath environment variable as described above.</span></span>

### <a name="installing-modules-in-a-product-directory"></a><span data-ttu-id="c04c4-157">Instalando módulos em um diretório de produto</span><span class="sxs-lookup"><span data-stu-id="c04c4-157">Installing Modules in a Product Directory</span></span>

<span data-ttu-id="c04c4-158">Se você estiver distribuindo o módulo para outras partes, use o local dos arquivos de programas padrão descritos acima ou crie seu próprio subdiretório específico da empresa ou do produto do diretório% ProgramFiles%.</span><span class="sxs-lookup"><span data-stu-id="c04c4-158">If you are distributing the module to other parties, use the default Program Files location described above, or create your own company-specific or product-specific subdirectory of the %ProgramFiles% directory.</span></span>

<span data-ttu-id="c04c4-159">Por exemplo, a Fabrikam Technologies, uma empresa fictícia, está enviando um módulo do Windows PowerShell para seu produto Fabrikam Manager.</span><span class="sxs-lookup"><span data-stu-id="c04c4-159">For example, Fabrikam Technologies, a fictitious company, is shipping a Windows PowerShell module for their Fabrikam Manager product.</span></span> <span data-ttu-id="c04c4-160">O instalador do módulo cria um subdiretório de módulos no subdiretório do produto Fabrikam Manager.</span><span class="sxs-lookup"><span data-stu-id="c04c4-160">Their module installer creates a Modules subdirectory in the Fabrikam Manager product subdirectory.</span></span>

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

<span data-ttu-id="c04c4-161">Para habilitar os recursos de descoberta de módulo do Windows PowerShell para localizar o módulo Fabrikam, o instalador do módulo Fabrikam adiciona o local do módulo ao valor da variável de ambiente **PSModulePath** .</span><span class="sxs-lookup"><span data-stu-id="c04c4-161">To enable the Windows PowerShell module discovery features to find the Fabrikam module, the Fabrikam module installer adds the module location to the value of the **PSModulePath** environment variable.</span></span>

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam Technologies\Fabrikam Manager\Modules\"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

### <a name="installing-modules-in-the-common-files-directory"></a><span data-ttu-id="c04c4-162">Instalando módulos no diretório de arquivos comuns</span><span class="sxs-lookup"><span data-stu-id="c04c4-162">Installing Modules in the Common Files Directory</span></span>

<span data-ttu-id="c04c4-163">Se um módulo for usado por vários componentes de um produto ou por várias versões de um produto, instale o módulo em um subdiretório específico de módulo do subdiretório%ProgramFiles%\Common Files\Modules.</span><span class="sxs-lookup"><span data-stu-id="c04c4-163">If a module is used by multiple components of a product or by multiple versions of a product, install the module in a module-specific subdirectory of the %ProgramFiles%\Common Files\Modules subdirectory.</span></span>

<span data-ttu-id="c04c4-164">No exemplo a seguir, o módulo Fabrikam é instalado em um subdiretório Fabrikam do `%ProgramFiles%\Common Files\Modules` subdiretório.</span><span class="sxs-lookup"><span data-stu-id="c04c4-164">In the following example, the Fabrikam module is installed in a Fabrikam subdirectory of the `%ProgramFiles%\Common Files\Modules` subdirectory.</span></span> <span data-ttu-id="c04c4-165">Observe que cada módulo reside em seu próprio subdiretório no subdiretório módulos.</span><span class="sxs-lookup"><span data-stu-id="c04c4-165">Note that each module resides in its own subdirectory in the Modules subdirectory.</span></span>

```
C:\Program Files
  Common Files
    Modules
      Fabrikam
        Fabrikam.psd1 (module manifest)
        Fabrikam.dll (module assembly)
```

<span data-ttu-id="c04c4-166">Em seguida, o instalador garante que o valor da variável de ambiente **PSModulePath** inclui o caminho do subdiretório de módulos de arquivos comuns.</span><span class="sxs-lookup"><span data-stu-id="c04c4-166">Then, the installer assures the value of the **PSModulePath** environment variable includes the path of the common files modules subdirectory.</span></span>

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

## <a name="installing-multiple-versions-of-a-module"></a><span data-ttu-id="c04c4-167">Instalando várias versões de um módulo</span><span class="sxs-lookup"><span data-stu-id="c04c4-167">Installing Multiple Versions of a Module</span></span>

<span data-ttu-id="c04c4-168">Para instalar várias versões do mesmo módulo, use o procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="c04c4-168">To install multiple versions of the same module, use the following procedure.</span></span>

1. <span data-ttu-id="c04c4-169">Crie um diretório para cada versão do módulo.</span><span class="sxs-lookup"><span data-stu-id="c04c4-169">Create a directory for each version of the module.</span></span> <span data-ttu-id="c04c4-170">Inclua o número de versão no nome do diretório.</span><span class="sxs-lookup"><span data-stu-id="c04c4-170">Include the version number in the directory name.</span></span>
2. <span data-ttu-id="c04c4-171">Crie um manifesto de módulo para cada versão do módulo.</span><span class="sxs-lookup"><span data-stu-id="c04c4-171">Create a module manifest for each version of the module.</span></span> <span data-ttu-id="c04c4-172">No valor da chave **ModuleVersion** no manifesto, insira o número de versão do módulo.</span><span class="sxs-lookup"><span data-stu-id="c04c4-172">In the value of the **ModuleVersion** key in the manifest, enter the module version number.</span></span> <span data-ttu-id="c04c4-173">Salve o arquivo de manifesto (. psd1) no diretório específico da versão do módulo.</span><span class="sxs-lookup"><span data-stu-id="c04c4-173">Save the manifest file (.psd1) in the version-specific directory for the module.</span></span>
3. <span data-ttu-id="c04c4-174">Adicione o caminho da pasta raiz do módulo ao valor da variável de ambiente **PSModulePath** , conforme mostrado nos exemplos a seguir.</span><span class="sxs-lookup"><span data-stu-id="c04c4-174">Add the module root folder path to the value of the **PSModulePath** environment variable, as shown in the following examples.</span></span>

<span data-ttu-id="c04c4-175">Para importar uma versão específica do módulo, o usuário final pode usar os `MinimumVersion` `RequiredVersion` parâmetros ou do cmdlet [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) .</span><span class="sxs-lookup"><span data-stu-id="c04c4-175">To import a particular version of the module, the end-user can use the `MinimumVersion` or `RequiredVersion` parameters of the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet.</span></span>

<span data-ttu-id="c04c4-176">Por exemplo, se o módulo Fabrikam estiver disponível nas versões 8,0 e 9,0, a estrutura de diretório do módulo Fabrikam poderá ser semelhante à seguinte.</span><span class="sxs-lookup"><span data-stu-id="c04c4-176">For example, if the Fabrikam module is available in versions 8.0 and 9.0, the Fabrikam module directory structure might resemble the following.</span></span>

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

<span data-ttu-id="c04c4-177">O instalador adiciona ambos os caminhos de módulo ao valor de variável de ambiente **PSModulePath** .</span><span class="sxs-lookup"><span data-stu-id="c04c4-177">The installer adds both of the module paths to the **PSModulePath** environment variable value.</span></span>

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam\Fabrikam8;C:\Program Files\Fabrikam\Fabrikam9"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

<span data-ttu-id="c04c4-178">Quando essas etapas forem concluídas, o parâmetro **listAvailable** do cmdlet [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) obterá ambos os módulos da Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="c04c4-178">When these steps are complete, the **ListAvailable** parameter of the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet gets both of the Fabrikam modules.</span></span> <span data-ttu-id="c04c4-179">Para importar um módulo específico, use os `MinimumVersion` `RequiredVersion` parâmetros ou do cmdlet [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) .</span><span class="sxs-lookup"><span data-stu-id="c04c4-179">To import a particular module, use the `MinimumVersion` or `RequiredVersion` parameters of the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet.</span></span>

<span data-ttu-id="c04c4-180">Se ambos os módulos forem importados para a mesma sessão e os módulos contiverem cmdlets com os mesmos nomes, os cmdlets que são importados por último entram em vigor na sessão.</span><span class="sxs-lookup"><span data-stu-id="c04c4-180">If both modules are imported into the same session, and the modules contain cmdlets with the same names, the cmdlets that are imported last are effective in the session.</span></span>

## <a name="handling-command-name-conflicts"></a><span data-ttu-id="c04c4-181">Manipulando conflitos de nome de comando</span><span class="sxs-lookup"><span data-stu-id="c04c4-181">Handling Command Name Conflicts</span></span>

<span data-ttu-id="c04c4-182">Conflitos de nome de comando podem ocorrer quando os comandos que um módulo exporta têm o mesmo nome que os comandos na sessão do usuário.</span><span class="sxs-lookup"><span data-stu-id="c04c4-182">Command name conflicts can occur when the commands that a module exports have the same name as commands in the user's session.</span></span>

<span data-ttu-id="c04c4-183">Quando uma sessão contém dois comandos que têm o mesmo nome, o Windows PowerShell executa o tipo de comando que tem precedência.</span><span class="sxs-lookup"><span data-stu-id="c04c4-183">When a session contains two commands that have the same name, Windows PowerShell runs the command type that takes precedence.</span></span> <span data-ttu-id="c04c4-184">Quando uma sessão contém dois comandos que têm o mesmo nome e o mesmo tipo, o Windows PowerShell executa o comando que foi adicionado à sessão mais recentemente.</span><span class="sxs-lookup"><span data-stu-id="c04c4-184">When a session contains two commands that have the same name and the same type, Windows PowerShell runs the command that was added to the session most recently.</span></span> <span data-ttu-id="c04c4-185">Para executar um comando que não é executado por padrão, os usuários podem qualificar o nome do comando com o nome do módulo.</span><span class="sxs-lookup"><span data-stu-id="c04c4-185">To run a command that is not run by default, users can qualify the command name with the module name.</span></span>

<span data-ttu-id="c04c4-186">Por exemplo, se a sessão contiver uma `Get-Date` função e o `Get-Date` cmdlet, o Windows PowerShell executará a função por padrão.</span><span class="sxs-lookup"><span data-stu-id="c04c4-186">For example, if the session contains a `Get-Date` function and the `Get-Date` cmdlet, Windows PowerShell runs the function by default.</span></span> <span data-ttu-id="c04c4-187">Para executar o cmdlet, preceda o comando com o nome do módulo, como:</span><span class="sxs-lookup"><span data-stu-id="c04c4-187">To run the cmdlet, preface the command with the module name, such as:</span></span>

```powershell
Microsoft.PowerShell.Utility\Get-Date
```

<span data-ttu-id="c04c4-188">Para evitar conflitos de nome, os autores de módulo podem usar a chave **DefaultCommandPrefix** no manifesto do módulo para especificar um prefixo de substantivo para todos os comandos exportados do módulo.</span><span class="sxs-lookup"><span data-stu-id="c04c4-188">To prevent name conflicts, module authors can use the **DefaultCommandPrefix** key in the module manifest to specify a noun prefix for all commands exported from the module.</span></span>

<span data-ttu-id="c04c4-189">Os usuários podem usar o parâmetro **prefix** do `Import-Module` cmdlet para usar um prefixo alternativo.</span><span class="sxs-lookup"><span data-stu-id="c04c4-189">Users can use the **Prefix** parameter of the `Import-Module` cmdlet to use an alternate prefix.</span></span> <span data-ttu-id="c04c4-190">O valor do parâmetro **prefix** tem precedência sobre o valor da chave **DefaultCommandPrefix** .</span><span class="sxs-lookup"><span data-stu-id="c04c4-190">The value of the **Prefix** parameter takes precedence over the value of the **DefaultCommandPrefix** key.</span></span>

## <a name="see-also"></a><span data-ttu-id="c04c4-191">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c04c4-191">See Also</span></span>

[<span data-ttu-id="c04c4-192">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="c04c4-192">about_Command_Precedence</span></span>](/powershell/module/microsoft.powershell.core/about/about_command_precedence)

[<span data-ttu-id="c04c4-193">Escrevendo um módulo do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c04c4-193">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)
