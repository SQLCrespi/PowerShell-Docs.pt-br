---
title: Migrando do Windows PowerShell 5.1 para o PowerShell 7
description: Atualize do PowerShell 5.1 para o PowerShell 7 em suas plataformas Windows.
ms.date: 03/25/2020
ms.openlocfilehash: e3881b1758f50119444969ad39541aec694cebe5
ms.sourcegitcommit: 30ccbbb32915b551c4cd4c91ef1df96b5b7514c4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2020
ms.locfileid: "80500496"
---
# <a name="migrating-from-windows-powershell-51-to-powershell-7"></a><span data-ttu-id="a356f-103">Migrando do Windows PowerShell 5.1 para o PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="a356f-103">Migrating from Windows PowerShell 5.1 to PowerShell 7</span></span>

<span data-ttu-id="a356f-104">Projetado para ambientes locais, híbridos e de nuvem, o PowerShell 7 é fornecido com aprimoramentos e [novos recursos](What-s-New-in-PowerShell-70.md).</span><span class="sxs-lookup"><span data-stu-id="a356f-104">Designed for cloud, on-premises, and hybrid environments, PowerShell 7 is packed with enhancements and [new features](What-s-New-in-PowerShell-70.md).</span></span>

- <span data-ttu-id="a356f-105">É instalado e executado lado a lado com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a356f-105">Installs and runs side-by-side with Windows PowerShell</span></span>
- <span data-ttu-id="a356f-106">Melhorias na compatibilidade com os módulos existentes do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a356f-106">Improved compatibility with existing Windows PowerShell modules</span></span>
- <span data-ttu-id="a356f-107">Novos recursos de linguagem, como operadores ternários e `ForEach-Object -Parallel`</span><span class="sxs-lookup"><span data-stu-id="a356f-107">New language features, like ternary operators and `ForEach-Object -Parallel`</span></span>
- <span data-ttu-id="a356f-108">desempenho aprimorado</span><span class="sxs-lookup"><span data-stu-id="a356f-108">Improved performance</span></span>
- <span data-ttu-id="a356f-109">Comunicação remota baseada em SSH</span><span class="sxs-lookup"><span data-stu-id="a356f-109">SSH-based remoting</span></span>
- <span data-ttu-id="a356f-110">Interoperabilidade entre plataformas</span><span class="sxs-lookup"><span data-stu-id="a356f-110">Cross-platform interoperability</span></span>
- <span data-ttu-id="a356f-111">Suporte para os contêineres do Docker</span><span class="sxs-lookup"><span data-stu-id="a356f-111">Support for Docker containers</span></span>

<span data-ttu-id="a356f-112">O PowerShell 7 funciona em conjunto com o Windows PowerShell, permitindo testar e comparar facilmente as edições antes da implantação.</span><span class="sxs-lookup"><span data-stu-id="a356f-112">PowerShell 7 works side-by-side with Windows PowerShell letting you easily test and compare between editions before deployment.</span></span> <span data-ttu-id="a356f-113">A migração é simples, rápida e segura.</span><span class="sxs-lookup"><span data-stu-id="a356f-113">Migration is simple, quick, and safe.</span></span> <span data-ttu-id="a356f-114">Falha.</span><span class="sxs-lookup"><span data-stu-id="a356f-114">failure.</span></span>

<span data-ttu-id="a356f-115">O PowerShell 7 é compatível com os seguintes sistemas operacionais Windows:</span><span class="sxs-lookup"><span data-stu-id="a356f-115">PowerShell 7 is supported on the following Windows operating systems:</span></span>

- <span data-ttu-id="a356f-116">Windows 8.1 e 10</span><span class="sxs-lookup"><span data-stu-id="a356f-116">Windows 8.1 and 10</span></span>
- <span data-ttu-id="a356f-117">Windows Server 2012, 2012 R2, 2016 e 2019</span><span class="sxs-lookup"><span data-stu-id="a356f-117">Windows Server 2012, 2012 R2, 2016, and 2019</span></span>

<span data-ttu-id="a356f-118">O PowerShell 7 também é executado no macOS e em várias distribuições do Linux.</span><span class="sxs-lookup"><span data-stu-id="a356f-118">PowerShell 7 also runs on macOS and several Linux distributions.</span></span> <span data-ttu-id="a356f-119">Para obter uma lista dos sistemas operacionais compatíveis e informações do ciclo de vida de suporte, confira o [Ciclo de vida de suporte do PowerShell](/powershell/scripting/powershell-support-lifecycle).</span><span class="sxs-lookup"><span data-stu-id="a356f-119">For a list of supported operating systems and information about the support lifecycle, see the [PowerShell Support Lifecycle](/powershell/scripting/powershell-support-lifecycle).</span></span>

## <a name="installing-powershell-7"></a><span data-ttu-id="a356f-120">Instalar o PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="a356f-120">Installing PowerShell 7</span></span>

<span data-ttu-id="a356f-121">Para obter flexibilidade e dar suporte às necessidades de TI, aos engenheiros de DevOps e aos desenvolvedores, há várias opções disponíveis para instalação do PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="a356f-121">For flexibility and to support the needs of IT, DevOps engineers, and developers, there are several options available to install PowerShell 7.</span></span> <span data-ttu-id="a356f-122">Na maioria dos casos, as opções de instalação podem ser reduzidas aos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="a356f-122">In most cases, the installation options can be reduced to the following methods:</span></span>

- <span data-ttu-id="a356f-123">Implantar o PowerShell usando o [pacote MSI](/powershell/scripting/install/installing-powershell-core-on-windows#installing-the-msi-package)</span><span class="sxs-lookup"><span data-stu-id="a356f-123">Deploy PowerShell using the [MSI package](/powershell/scripting/install/installing-powershell-core-on-windows#installing-the-msi-package)</span></span>
- <span data-ttu-id="a356f-124">Implantar o PowerShell usando o [pacote ZIP](/powershell/scripting/install/installing-powershell-core-on-windows#installing-the-zip-package)</span><span class="sxs-lookup"><span data-stu-id="a356f-124">Deploy PowerShell using the [ZIP package](/powershell/scripting/install/installing-powershell-core-on-windows#installing-the-zip-package)</span></span>

> [!NOTE]
> <span data-ttu-id="a356f-125">O pacote MSI pode ser implantado e atualizado com produtos de gerenciamento, como o [SCCM (System Center Configuration Manager)](/configmgr/apps/).</span><span class="sxs-lookup"><span data-stu-id="a356f-125">The MSI package can be deployed and updated with management products such as [System Center Configuration Manager (SCCM)](/configmgr/apps/).</span></span> <span data-ttu-id="a356f-126">Baixe os pacotes da [página de versões do GitHub](https://github.com/PowerShell/PowerShell/releases).</span><span class="sxs-lookup"><span data-stu-id="a356f-126">Download the packages from [GitHub Release page](https://github.com/PowerShell/PowerShell/releases).</span></span>

<span data-ttu-id="a356f-127">A implantação do pacote MSI requer permissão de administrador.</span><span class="sxs-lookup"><span data-stu-id="a356f-127">Deploying the MSI package requires Administrator permission.</span></span> <span data-ttu-id="a356f-128">O pacote ZIP pode ser implantado por qualquer usuário.</span><span class="sxs-lookup"><span data-stu-id="a356f-128">The ZIP package can be deployed by any user.</span></span> <span data-ttu-id="a356f-129">O pacote ZIP é a maneira mais fácil de instalar o PowerShell 7 para testes, antes de se comprometer com uma instalação completa.</span><span class="sxs-lookup"><span data-stu-id="a356f-129">The ZIP package is the easiest way to install PowerShell 7 for testing, before committing to a full installation.</span></span>

## <a name="using-powershell-7-side-by-side-with-windows-powershell-51"></a><span data-ttu-id="a356f-130">Usar o PowerShell 7 em conjunto com o Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="a356f-130">Using PowerShell 7 side-by-side with Windows PowerShell 5.1</span></span>

<span data-ttu-id="a356f-131">O PowerShell 7 foi projetado para coexistir com o Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="a356f-131">PowerShell 7 is designed to coexist with Windows PowerShell 5.1.</span></span> <span data-ttu-id="a356f-132">Os recursos a seguir garantem que seu investimento no PowerShell esteja protegido e que a migração para o PowerShell 7 seja simples.</span><span class="sxs-lookup"><span data-stu-id="a356f-132">The following features ensure that your investment in PowerShell is protected and your migration to PowerShell 7 is simple.</span></span>

- <span data-ttu-id="a356f-133">Caminho de instalação e nome do executável separados</span><span class="sxs-lookup"><span data-stu-id="a356f-133">Separate installation path and executable name</span></span>
- <span data-ttu-id="a356f-134">PSModulePath separado</span><span class="sxs-lookup"><span data-stu-id="a356f-134">Separate PSModulePath</span></span>
- <span data-ttu-id="a356f-135">Perfis separados para cada versão</span><span class="sxs-lookup"><span data-stu-id="a356f-135">Separate profiles for each version</span></span>
- <span data-ttu-id="a356f-136">Compatibilidade de módulo aprimorada</span><span class="sxs-lookup"><span data-stu-id="a356f-136">Improved module compatibility</span></span>
- <span data-ttu-id="a356f-137">Novos pontos de extremidade de comunicação remota</span><span class="sxs-lookup"><span data-stu-id="a356f-137">New remoting endpoints</span></span>
- <span data-ttu-id="a356f-138">Suporte à política de grupo</span><span class="sxs-lookup"><span data-stu-id="a356f-138">Group policy support</span></span>
- <span data-ttu-id="a356f-139">Logs de eventos separados</span><span class="sxs-lookup"><span data-stu-id="a356f-139">Separate Event logs</span></span>

### <a name="separate-installation-path-and-executable-name"></a><span data-ttu-id="a356f-140">Caminho de instalação e nome do executável separados</span><span class="sxs-lookup"><span data-stu-id="a356f-140">Separate installation path and executable name</span></span>

<span data-ttu-id="a356f-141">O PowerShell 7 é instalado em um novo diretório, permitindo a execução em conjunto com o Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="a356f-141">PowerShell 7 installs to a new directory, enabling side-by-side execution with Windows PowerShell 5.1.</span></span>

<span data-ttu-id="a356f-142">Locais de instalação por versão:</span><span class="sxs-lookup"><span data-stu-id="a356f-142">Install locations by version:</span></span>

- <span data-ttu-id="a356f-143">Windows PowerShell 5.1: `$env:WINDIR\System32\WindowsPowerShell\v1.0`</span><span class="sxs-lookup"><span data-stu-id="a356f-143">Windows PowerShell 5.1: `$env:WINDIR\System32\WindowsPowerShell\v1.0`</span></span>
- <span data-ttu-id="a356f-144">PowerShell Core 6.x: `$env:ProgramFiles\PowerShell\6`</span><span class="sxs-lookup"><span data-stu-id="a356f-144">PowerShell Core 6.x: `$env:ProgramFiles\PowerShell\6`</span></span>
- <span data-ttu-id="a356f-145">PowerShell 7: `$env:ProgramFiles\PowerShell\7`</span><span class="sxs-lookup"><span data-stu-id="a356f-145">PowerShell 7: `$env:ProgramFiles\PowerShell\7`</span></span>

<span data-ttu-id="a356f-146">O novo local é adicionado ao seu caminho, permitindo que você execute o Windows PowerShell 5.1 e o PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="a356f-146">The new location is added to your PATH allowing you to run both Windows PowerShell 5.1 and PowerShell 7.</span></span> <span data-ttu-id="a356f-147">Se você estiver migrando do PowerShell Core 6.x para o PowerShell 7, o PowerShell 6 será removido e o caminho substituído.</span><span class="sxs-lookup"><span data-stu-id="a356f-147">If you're migrating from PowerShell Core 6.x to PowerShell 7, PowerShell 6 is removed and the PATH replaced.</span></span>

<span data-ttu-id="a356f-148">No Windows PowerShell, o executável do PowerShell é denominado `powershell.exe`.</span><span class="sxs-lookup"><span data-stu-id="a356f-148">In Windows PowerShell, the PowerShell executable is named `powershell.exe`.</span></span> <span data-ttu-id="a356f-149">Na versão 6 e posteriores, o executável é denominado `pwsh.exe`.</span><span class="sxs-lookup"><span data-stu-id="a356f-149">In version 6 and above, the executable is named `pwsh.exe`.</span></span> <span data-ttu-id="a356f-150">O novo nome torna facilita o suporte à execução lado a lado das duas versões.</span><span class="sxs-lookup"><span data-stu-id="a356f-150">The new name makes it easy to support side-by-side execution of both versions.</span></span>

### <a name="separate-psmodulepath"></a><span data-ttu-id="a356f-151">PSModulePath separado</span><span class="sxs-lookup"><span data-stu-id="a356f-151">Separate PSModulePath</span></span>

<span data-ttu-id="a356f-152">Por padrão, o Windows PowerShell e o PowerShell 7 armazenam seus módulos em locais diferentes.</span><span class="sxs-lookup"><span data-stu-id="a356f-152">By default, Windows PowerShell and PowerShell 7 store modules in different locations.</span></span> <span data-ttu-id="a356f-153">O PowerShell 7 combina esses locais na variável de ambiente `$Env:PSModulePath`.</span><span class="sxs-lookup"><span data-stu-id="a356f-153">PowerShell 7 combines those locations in the `$Env:PSModulePath` environment variable.</span></span> <span data-ttu-id="a356f-154">Ao importar um módulo por nome, o PowerShell verifica o local especificado no `$Env:PSModulePath`.</span><span class="sxs-lookup"><span data-stu-id="a356f-154">When importing a module by name, PowerShell checks the location specified by `$Env:PSModulePath`.</span></span> <span data-ttu-id="a356f-155">Assim, o PowerShell 7 pode carregar os módulos Core e Desktop.</span><span class="sxs-lookup"><span data-stu-id="a356f-155">This allows PowerShell 7 to load both Core and Desktop modules.</span></span>

|            <span data-ttu-id="a356f-156">Escopo de instalação</span><span class="sxs-lookup"><span data-stu-id="a356f-156">Install Scope</span></span>            |                <span data-ttu-id="a356f-157">Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="a356f-157">Windows PowerShell 5.1</span></span>                 |             <span data-ttu-id="a356f-158">PowerShell 7.0</span><span class="sxs-lookup"><span data-stu-id="a356f-158">PowerShell 7.0</span></span>             |
| ----------------------------------- | ----------------------------------------------------- | -------------------------------------- |
| <span data-ttu-id="a356f-159">Módulos do PowerShell</span><span class="sxs-lookup"><span data-stu-id="a356f-159">PowerShell modules</span></span>                  | `$env:WINDIR\system32\WindowsPowerShell\v1.0\Modules` | `$PSHOME\Modules`                      |
| <span data-ttu-id="a356f-160">Instalado pelo usuário</span><span class="sxs-lookup"><span data-stu-id="a356f-160">User installed</span></span><br><span data-ttu-id="a356f-161">Escopo AllUsers</span><span class="sxs-lookup"><span data-stu-id="a356f-161">AllUsers scope</span></span>    | `$env:ProgramFiles\WindowsPowerShell\Modules`         | `$env:ProgramFiles\PowerShell\Modules` |
| <span data-ttu-id="a356f-162">Instalado pelo usuário</span><span class="sxs-lookup"><span data-stu-id="a356f-162">User installed</span></span><br><span data-ttu-id="a356f-163">Escopo CurrentUser</span><span class="sxs-lookup"><span data-stu-id="a356f-163">CurrentUser scope</span></span> | `$HOME\Documents\WindowsPowerShell\Modules`           | `$HOME\Documents\PowerShell\Modules`   |

<span data-ttu-id="a356f-164">Os exemplos a seguir mostram os valores padrão de `$Env:PSModulePath` para cada versão.</span><span class="sxs-lookup"><span data-stu-id="a356f-164">The following examples show the default values of `$Env:PSModulePath` for each version.</span></span>

- <span data-ttu-id="a356f-165">Para o Windows PowerShell 5.1:</span><span class="sxs-lookup"><span data-stu-id="a356f-165">For Windows PowerShell 5.1:</span></span>

  ```powershell
  $Env:PSModulePath -split (';')
  ```

  ```Output
  C:\Users\<user>\Documents\WindowsPowerShell\Modules
  C:\Program Files\WindowsPowerShell\Modules
  C:\WINDOWS\System32\WindowsPowerShell\v1.0\Modules
  ```

- <span data-ttu-id="a356f-166">Para o PowerShell 7:</span><span class="sxs-lookup"><span data-stu-id="a356f-166">For PowerShell 7:</span></span>

  ```powershell
  $Env:PSModulePath -split (';')
  ```

  ```Output
  C:\Users\<user>\Documents\PowerShell\Modules
  C:\Program Files\PowerShell\Modules
  C:\Program Files\PowerShell\7\Modules
  C:\Program Files\WindowsPowerShell\Modules
  C:\WINDOWS\System32\WindowsPowerShell\v1.0\Modules
  ```

<span data-ttu-id="a356f-167">Observe que o PowerShell 7 inclui os caminhos do Windows PowerShell e do PowerShell 7 para fornecer o carregamento automático de módulos.</span><span class="sxs-lookup"><span data-stu-id="a356f-167">Notice that PowerShell 7 includes the Windows PowerShell paths and the PowerShell 7 paths to provide autoloading of modules.</span></span>

> [!NOTE]
> <span data-ttu-id="a356f-168">Poderá haver caminhos adicionais se você tiver alterado a variável de ambiente PSModulePath ou instalado módulos ou aplicativos personalizados.</span><span class="sxs-lookup"><span data-stu-id="a356f-168">Additional paths may exist if you have changed the PSModulePath environment variable or installed custom modules or applications.</span></span>

<span data-ttu-id="a356f-169">Confira mais informações sobre `PSModulePath` em [about_Environment_Variables](/powershell/module/microsoft.powershell.core/about/about_environment_variables#environment-variables-that-store-preferences).</span><span class="sxs-lookup"><span data-stu-id="a356f-169">For more information, see `PSModulePath` in [about_Environment_Variables](/powershell/module/microsoft.powershell.core/about/about_environment_variables#environment-variables-that-store-preferences).</span></span>

<span data-ttu-id="a356f-170">Para obter mais informações sobre módulos, confira [about_Modules](/powershell/module/Microsoft.PowerShell.Core/About/about_Modules).</span><span class="sxs-lookup"><span data-stu-id="a356f-170">For more information about Modules, see [about_Modules](/powershell/module/Microsoft.PowerShell.Core/About/about_Modules).</span></span>

### <a name="separate-profiles"></a><span data-ttu-id="a356f-171">Perfis separados</span><span class="sxs-lookup"><span data-stu-id="a356f-171">Separate profiles</span></span>

<span data-ttu-id="a356f-172">Um perfil do PowerShell é um script executado quando o PowerShell é iniciado.</span><span class="sxs-lookup"><span data-stu-id="a356f-172">A PowerShell profile is a script that executes when PowerShell starts.</span></span> <span data-ttu-id="a356f-173">Esse script personaliza seu ambiente adicionando comandos, aliases, funções, variáveis, módulos e unidades do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a356f-173">This script customizes your environment by adding commands, aliases, functions, variables, modules, and PowerShell drives.</span></span> <span data-ttu-id="a356f-174">O script de perfil disponibiliza essas personalizações em cada sessão sem precisar recriá-las manualmente.</span><span class="sxs-lookup"><span data-stu-id="a356f-174">The profile script makes these customizations available in every session without having to manually recreate them.</span></span>

<span data-ttu-id="a356f-175">O caminho para o local do perfil foi alterado no PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="a356f-175">The path to the location of the profile has changed in PowerShell 7.</span></span>

- <span data-ttu-id="a356f-176">No Windows PowerShell 5.1, o local do perfil é `$HOME\Documents\WindowsPowerShell`.</span><span class="sxs-lookup"><span data-stu-id="a356f-176">In Windows PowerShell 5.1, the location of the profile is `$HOME\Documents\WindowsPowerShell`.</span></span>
- <span data-ttu-id="a356f-177">No PowerShell 7, o local do perfil é `$HOME\Documents\PowerShell`.</span><span class="sxs-lookup"><span data-stu-id="a356f-177">In PowerShell 7, the location of the profile is `$HOME\Documents\PowerShell`.</span></span>

<span data-ttu-id="a356f-178">Os nomes de arquivos de perfil também foram alterados:</span><span class="sxs-lookup"><span data-stu-id="a356f-178">The profile filenames have also changed:</span></span>

   ```powershell
   PS> $PROFILE | Select-Object *Host* | Format-List

   AllUsersAllHosts       : C:\Program Files\PowerShell\7\profile.ps1
   AllUsersCurrentHost    : C:\Program Files\PowerShell\7\Microsoft.PowerShell_profile.ps1
   CurrentUserAllHosts    : C:\Users\<user>\Documents\PowerShell\profile.ps1
   CurrentUserCurrentHost : C:\Users\<user>\Documents\PowerShell\Microsoft.PowerShell_profile.ps1
   ```

<span data-ttu-id="a356f-179">Confira mais informações em [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles).</span><span class="sxs-lookup"><span data-stu-id="a356f-179">For more information [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles).</span></span>

### <a name="powershell-7-compatibility-with-windows-powershell-51-modules"></a><span data-ttu-id="a356f-180">Compatibilidade do PowerShell 7 com os módulos do Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="a356f-180">PowerShell 7 compatibility with Windows PowerShell 5.1 modules</span></span>

<span data-ttu-id="a356f-181">A maioria dos módulos que você usa no Windows PowerShell 5.1 já funciona com o PowerShell 7, incluindo o Azure PowerShell e o Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a356f-181">Most of the modules you use in Windows PowerShell 5.1 already work with PowerShell 7, including Azure PowerShell and Active Directory.</span></span> <span data-ttu-id="a356f-182">Continuamos a trabalhar com outras equipes para adicionar suporte nativo do PowerShell 7 em mais módulos, incluindo o Microsoft Graph, Office 365 e outros.</span><span class="sxs-lookup"><span data-stu-id="a356f-182">We're continuing to work with other teams to add native PowerShell 7 support for more modules including Microsoft Graph, Office 365, and others.</span></span> <span data-ttu-id="a356f-183">Confira a lista atual de módulos compatíveis em [Compatibilidade de módulos do PowerShell 7](/powershell/scripting/whats-new/module-compatibility).</span><span class="sxs-lookup"><span data-stu-id="a356f-183">For the current list of supported modules, see [PowerShell 7 module compatibility](/powershell/scripting/whats-new/module-compatibility).</span></span>

> [!NOTE]
> <span data-ttu-id="a356f-184">No Windows, também adicionamos uma opção **UseWindowsPowerShell** a `Import-Module` a fim de facilitar a transição para o PowerShell 7 de quem usa módulos incompatíveis.</span><span class="sxs-lookup"><span data-stu-id="a356f-184">On Windows, we've also added a **UseWindowsPowerShell** switch to `Import-Module` to ease the transition to PowerShell 7 for those using incompatible modules.</span></span> <span data-ttu-id="a356f-185">Para obter mais informações sobre essa funcionalidade, confira [about_Windows_PowerShell_Compatibility](/powershell/module/Microsoft.PowerShell.Core/About/about_windows_powershell_compatibility).</span><span class="sxs-lookup"><span data-stu-id="a356f-185">For more information on this functionality, see [about_Windows_PowerShell_Compatibility](/powershell/module/Microsoft.PowerShell.Core/About/about_windows_powershell_compatibility).</span></span>

### <a name="powershell-remoting"></a><span data-ttu-id="a356f-186">Comunicação remota do PowerShell</span><span class="sxs-lookup"><span data-stu-id="a356f-186">PowerShell Remoting</span></span>

<span data-ttu-id="a356f-187">A comunicação remota do PowerShell permite executar qualquer comando do PowerShell em um ou vários computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="a356f-187">PowerShell remoting lets you run any PowerShell command on one or more remote computers.</span></span> <span data-ttu-id="a356f-188">Você pode estabelecer conexões persistentes, iniciar sessões interativas e executar scripts em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="a356f-188">You can establish persistent connections, start interactive sessions, and run scripts on remote computers.</span></span>

#### <a name="ws-management-remoting"></a><span data-ttu-id="a356f-189">Comunicação remota do WS-Management</span><span class="sxs-lookup"><span data-stu-id="a356f-189">WS-Management remoting</span></span>

<span data-ttu-id="a356f-190">O Windows PowerShell 5.1 e as versões anteriores usam o protocolo WSMAN (WS-Management) para negociação de conexão e transporte de dados.</span><span class="sxs-lookup"><span data-stu-id="a356f-190">Windows PowerShell 5.1 and below use the WS-Management (WSMAN) protocol for connection negotiation and data transport.</span></span> <span data-ttu-id="a356f-191">O WinRM (Gerenciamento Remoto do Windows) usa o protocolo WSMAN.</span><span class="sxs-lookup"><span data-stu-id="a356f-191">Windows Remote Management (WinRM) uses the WSMAN protocol.</span></span> <span data-ttu-id="a356f-192">Se o WinRM estiver habilitado, o PowerShell 7 usará o ponto de extremidade existente do Windows PowerShell 5.1 chamado `Microsoft.PowerShell` para conexões de comunicação remota.</span><span class="sxs-lookup"><span data-stu-id="a356f-192">If WinRM has been enabled, PowerShell 7 uses the existing Windows PowerShell 5.1 endpoint named `Microsoft.PowerShell` for remoting connections.</span></span> <span data-ttu-id="a356f-193">Para atualizar o PowerShell 7 de modo que inclua seu próprio ponto de extremidade, execute o cmdlet `Enable-PSRemoting`.</span><span class="sxs-lookup"><span data-stu-id="a356f-193">To update PowerShell 7 to include its own endpoint, run the `Enable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="a356f-194">Confira mais informações sobre como se conectar a pontos de extremidade específicos em [Comunicação remota do WS-Management no PowerShell Core](/powershell/scripting/learn/remoting/wsman-remoting-in-powershell-core)</span><span class="sxs-lookup"><span data-stu-id="a356f-194">For information about connecting to specific endpoints, see [WS-Management Remoting in PowerShell Core](/powershell/scripting/learn/remoting/wsman-remoting-in-powershell-core)</span></span>

<span data-ttu-id="a356f-195">Para usar a comunicação remota do Windows PowerShell, o computador remoto deve ser configurado para gerenciamento remoto.</span><span class="sxs-lookup"><span data-stu-id="a356f-195">To use Windows PowerShell remoting, the remote computer must be configured for remote management.</span></span>
<span data-ttu-id="a356f-196">Para obter mas informações, incluindo instruções consulte [Sobre requisitos remotos](/powershell/module/microsoft.powershell.core/about/about_remote_requirements).</span><span class="sxs-lookup"><span data-stu-id="a356f-196">For more information, including instructions, see [About Remote Requirements](/powershell/module/microsoft.powershell.core/about/about_remote_requirements).</span></span>

<span data-ttu-id="a356f-197">Confira mais informações sobre a comunicação remota em [Sobre comunicação remota](/powershell/module/microsoft.powershell.core/about/about_remote)</span><span class="sxs-lookup"><span data-stu-id="a356f-197">For more information about working with remoting, see [About Remote](/powershell/module/microsoft.powershell.core/about/about_remote)</span></span>

#### <a name="ssh-based-remoting"></a><span data-ttu-id="a356f-198">Comunicação remota baseada em SSH</span><span class="sxs-lookup"><span data-stu-id="a356f-198">SSH-based remoting</span></span>

<span data-ttu-id="a356f-199">A comunicação remota baseada em SSH foi adicionada ao PowerShell Core 6.x para dar suporte a outros sistemas operacionais que não podem usar componentes nativos do Windows, como o **WinRM**.</span><span class="sxs-lookup"><span data-stu-id="a356f-199">SSH-based remoting was added in PowerShell Core 6.x to support other operating systems that can't use Windows native components like **WinRM**.</span></span> <span data-ttu-id="a356f-200">A comunicação remota do SSH cria um processo de hospedagem do PowerShell no computador de destino como um subsistema de SSH.</span><span class="sxs-lookup"><span data-stu-id="a356f-200">SSH remoting creates a PowerShell host process on the target computer as an SSH subsystem.</span></span> <span data-ttu-id="a356f-201">Confira detalhes e exemplos sobre como configurar a comunicação remota baseada em SSH no Windows ou no Linux em: [Comunicação remota do PowerShell por SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span><span class="sxs-lookup"><span data-stu-id="a356f-201">For details and examples on setting up SSH-based remoting on Windows or Linux, see: [PowerShell remoting over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

> [!NOTE]
> <span data-ttu-id="a356f-202">A PSGallery (Galeria do PowerShell) contém um módulo e um cmdlet que configura automaticamente a comunicação remota baseada em SSH.</span><span class="sxs-lookup"><span data-stu-id="a356f-202">The PowerShell Gallery (PSGallery) contains a module and cmdlet that automatically configures SSH-based remoting.</span></span> <span data-ttu-id="a356f-203">Instale o módulo `Microsoft.PowerShell.RemotingTools` da [PSGallery](https://www.powershellgallery.com/packages/Microsoft.PowerShell.RemotingTools/0.1.0) e execute o cmdlet `Enable-SSH`.</span><span class="sxs-lookup"><span data-stu-id="a356f-203">Install the `Microsoft.PowerShell.RemotingTools` module from the [PSGallery](https://www.powershellgallery.com/packages/Microsoft.PowerShell.RemotingTools/0.1.0) and run the `Enable-SSH` cmdlet.</span></span>

<span data-ttu-id="a356f-204">Os cmdlets `New-PSSession`, `Enter-PSSession` e `Invoke-Command` têm novos conjuntos de parâmetros para dar suporte a conexões SSH.</span><span class="sxs-lookup"><span data-stu-id="a356f-204">The `New-PSSession`, `Enter-PSSession`, and `Invoke-Command` cmdlets have new parameter sets to support SSH connections.</span></span>

```powershell
[-HostName <string>]  [-UserName <string>]  [-KeyFilePath <string>]
```

<span data-ttu-id="a356f-205">Para criar uma sessão remota, especifique o computador de destino com o parâmetro **HostName** e forneça o nome de usuário com **UserName**.</span><span class="sxs-lookup"><span data-stu-id="a356f-205">To create a remote session, specify the target computer with the **HostName** parameter and provide the user name with **UserName**.</span></span> <span data-ttu-id="a356f-206">Ao executar os cmdlets interativamente, você receberá uma solicitação de senha.</span><span class="sxs-lookup"><span data-stu-id="a356f-206">When running the cmdlets interactively, you're prompted for a password.</span></span>

```powershell
Enter-PSSession -HostName <Computer> -UserName <Username>
```

<span data-ttu-id="a356f-207">Como alternativa, ao usar o parâmetro **HostName**, forneça as informações de nome de usuário seguidas pelo sinal de arroba ("@") e pelo nome do computador.</span><span class="sxs-lookup"><span data-stu-id="a356f-207">Alternatively, when using the **HostName** parameter, provide the username information followed by the at sign ('@'), followed by the computer name.</span></span>

```powershell
Enter-PSSession -HostName <Username>@<Computer>
```

<span data-ttu-id="a356f-208">Você também pode configurar a autenticação de chave SSH usando um arquivo de chave privada com o parâmetro **KeyFilePath**.</span><span class="sxs-lookup"><span data-stu-id="a356f-208">You may set up SSH key authentication using a private key file with the **KeyFilePath** parameter.</span></span>
<span data-ttu-id="a356f-209">Confira mais informações em [Gerenciamento de chaves OpenSSH](/windows-server/administration/openssh/openssh_keymanagement).</span><span class="sxs-lookup"><span data-stu-id="a356f-209">For more information, see [OpenSSH Key Management](/windows-server/administration/openssh/openssh_keymanagement).</span></span>

### <a name="group-policy-supported"></a><span data-ttu-id="a356f-210">Política de Grupo compatível</span><span class="sxs-lookup"><span data-stu-id="a356f-210">Group Policy supported</span></span>

<span data-ttu-id="a356f-211">O PowerShell inclui configurações de Política de Grupo para ajudar você a definir valores consistentes de opções nos servidores de um ambiente empresarial.</span><span class="sxs-lookup"><span data-stu-id="a356f-211">PowerShell includes Group Policy settings to help you define consistent option values for servers in an enterprise environment.</span></span> <span data-ttu-id="a356f-212">Essas configurações incluem:</span><span class="sxs-lookup"><span data-stu-id="a356f-212">These settings include:</span></span>

- <span data-ttu-id="a356f-213">Configuração de sessão do console: define um ponto de extremidade de configuração em que o PowerShell é executado.</span><span class="sxs-lookup"><span data-stu-id="a356f-213">Console session configuration: Sets a configuration endpoint in which PowerShell is run.</span></span>
- <span data-ttu-id="a356f-214">Ativar Registro em Log do Módulo: define a propriedade LogPipelineExecutionDetails dos módulos.</span><span class="sxs-lookup"><span data-stu-id="a356f-214">Turn on Module Logging: Sets the LogPipelineExecutionDetails property of modules.</span></span>
- <span data-ttu-id="a356f-215">Ativar o Registro em Log de Blocos de Script do PowerShell: ativa o registro em log detalhado de todos os scripts do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a356f-215">Turn on PowerShell Script Block Logging: Enables detailed logging of all PowerShell scripts.</span></span>
- <span data-ttu-id="a356f-216">Ativar a Execução do Script: define a política de execução do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a356f-216">Turn on Script Execution: Sets the PowerShell execution policy.</span></span>
- <span data-ttu-id="a356f-217">Ativar a Transcrição do PowerShell: ativa a captura de entradas e saídas dos comandos do PowerShell como transcrições baseadas em texto.</span><span class="sxs-lookup"><span data-stu-id="a356f-217">Turn on PowerShell Transcription: enables capturing of input and output of PowerShell commands into text-based transcripts.</span></span>
- <span data-ttu-id="a356f-218">Definir o caminho de origem padrão para Update-Help: define a origem para a Ajuda Atualizável como um diretório, e não a Internet.</span><span class="sxs-lookup"><span data-stu-id="a356f-218">Set the default source path for Update-Help: Sets the source for Updatable Help to a directory, not the Internet.</span></span>

<span data-ttu-id="a356f-219">Confira mais informações em [about_Group_Policy_Settings](/powershell/module/microsoft.powershell.core/about/about_group_policy_settings).</span><span class="sxs-lookup"><span data-stu-id="a356f-219">For more information, see [about_Group_Policy_Settings](/powershell/module/microsoft.powershell.core/about/about_group_policy_settings).</span></span>

<span data-ttu-id="a356f-220">O PowerShell 7 inclui modelos de Política de Grupo e um script de instalação em `$PSHOME`.</span><span class="sxs-lookup"><span data-stu-id="a356f-220">PowerShell 7 includes Group Policy templates and an installation script in `$PSHOME`.</span></span>

<span data-ttu-id="a356f-221">As ferramentas de Política de Grupo usam arquivos de modelos administrativos (`.admx`, `.adml`) para preencher as configurações de políticas na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="a356f-221">Group Policy tools use administrative template files (`.admx`, `.adml`) to populate policy settings in the user interface.</span></span> <span data-ttu-id="a356f-222">Assim, os administradores podem gerenciar as configurações de políticas com base no registro.</span><span class="sxs-lookup"><span data-stu-id="a356f-222">This allows administrators to manage registry-based policy settings.</span></span> <span data-ttu-id="a356f-223">O script `InstallPSCorePolicyDefinitions.ps1` instala os Modelos Administrativos do PowerShell Core no computador local.</span><span class="sxs-lookup"><span data-stu-id="a356f-223">The `InstallPSCorePolicyDefinitions.ps1` script installs PowerShell Core Administrative Templates on the local machine.</span></span>

```powershell
Get-ChildItem -Path $PSHOME -Filter *Core*Policy*
```

```Output
    Directory: C:\Program Files\PowerShell\7

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/27/2020 12:38 AM          15861 InstallPSCorePolicyDefinitions.ps1
-a---           2/27/2020 12:28 AM           9675 PowerShellCoreExecutionPolicy.adml
-a---           2/27/2020 12:28 AM           6201 PowerShellCoreExecutionPolicy.admx
```

### <a name="separate-event-logs"></a><span data-ttu-id="a356f-224">Logs de Eventos Separados</span><span class="sxs-lookup"><span data-stu-id="a356f-224">Separate Event Logs</span></span>

<span data-ttu-id="a356f-225">O Windows PowerShell e o PowerShell 7 registram eventos em logs de eventos separados.</span><span class="sxs-lookup"><span data-stu-id="a356f-225">Windows PowerShell and PowerShell 7 log events to separate event logs.</span></span> <span data-ttu-id="a356f-226">Use o comando a seguir para obter uma lista de logs do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a356f-226">Use the following command to get a list of the PowerShell logs.</span></span>

```powershell
Get-WinEvent -ListLog *PowerShell*
```

<span data-ttu-id="a356f-227">Confira mais informações em [about_Logging_Windows](/powershell/module/microsoft.powershell.core/about/about_logging_windows).</span><span class="sxs-lookup"><span data-stu-id="a356f-227">For more information, see [about_Logging_Windows](/powershell/module/microsoft.powershell.core/about/about_logging_windows).</span></span>

## <a name="improved-editing-experience-with-visual-studio-code"></a><span data-ttu-id="a356f-228">Melhoria da experiência de edição no Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a356f-228">Improved editing experience with Visual Studio Code</span></span>

<span data-ttu-id="a356f-229">O [VSCode (Visual Studio Code)](https://code.visualstudio.com/) com a [Extensão do PowerShell](https://code.visualstudio.com/docs/languages/powershell) é o ambiente de script compatível com o PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="a356f-229">[Visual Studio Code (VSCode)](https://code.visualstudio.com/) with the [PowerShell Extension](https://code.visualstudio.com/docs/languages/powershell) is the supported scripting environment for PowerShell 7.</span></span> <span data-ttu-id="a356f-230">O ISE (Ambiente de Script Integrado) do Windows PowerShell dá suporte somente ao Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a356f-230">The Windows PowerShell Integrated Scripting Environment (ISE) only supports Windows PowerShell.</span></span>

<span data-ttu-id="a356f-231">A extensão atualizada do PowerShell inclui:</span><span class="sxs-lookup"><span data-stu-id="a356f-231">The updated PowerShell extension includes:</span></span>

- <span data-ttu-id="a356f-232">Novo modo de Compatibilidade do ISE</span><span class="sxs-lookup"><span data-stu-id="a356f-232">New ISE compatibility mode</span></span>
- <span data-ttu-id="a356f-233">PSReadLine no Console Integrado, incluindo realce de sintaxe, edição de várias linhas e pesquisa de retorno</span><span class="sxs-lookup"><span data-stu-id="a356f-233">PSReadLine in the Integrated Console, including syntax highlighting, multi-line editing, and back search</span></span>
- <span data-ttu-id="a356f-234">Melhorias de desempenho e estabilidade</span><span class="sxs-lookup"><span data-stu-id="a356f-234">Stability and performance improvements</span></span>
- <span data-ttu-id="a356f-235">Nova integração do CodeLens</span><span class="sxs-lookup"><span data-stu-id="a356f-235">New CodeLens integration</span></span>
- <span data-ttu-id="a356f-236">Melhoria do preenchimento automático de caminho</span><span class="sxs-lookup"><span data-stu-id="a356f-236">Improved path auto-completion</span></span>

<span data-ttu-id="a356f-237">Para facilitar a transição para o Visual Studio Code, use a função **Habilitar o Modo ISE** disponível na **Paleta de Comandos**.</span><span class="sxs-lookup"><span data-stu-id="a356f-237">To make the transition to Visual Studio Code easier, use the **Enable ISE Mode** function available in the **Command Palette**.</span></span> <span data-ttu-id="a356f-238">Essa função alterna o VSCode para um layout no estilo do ISE.</span><span class="sxs-lookup"><span data-stu-id="a356f-238">This function switches VSCode into an ISE-style layout.</span></span> <span data-ttu-id="a356f-239">O layout no estilo do ISE fornece todos os novos recursos e funcionalidades do PowerShell em uma experiência de usuário conhecida.</span><span class="sxs-lookup"><span data-stu-id="a356f-239">The ISE-style layout gives you all the new features and capabilities of PowerShell in a familiar user experience.</span></span>

<span data-ttu-id="a356f-240">Para alternar para o novo layout do ISE, pressione <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> a fim de abrir a **Paleta de Comandos**, digite `PowerShell` e selecione **PowerShell: Habilitar o Modo ISE**.</span><span class="sxs-lookup"><span data-stu-id="a356f-240">To switch to the new ISE layout, press <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> to open the **Command Palette**, type `PowerShell` and select **PowerShell: Enable ISE Mode**.</span></span>

<span data-ttu-id="a356f-241">Para definir o layout para o original, abra a **Paleta de Comandos**, selecione **PowerShell: Desabilitar o Modo ISE (restaurar padrões)** .</span><span class="sxs-lookup"><span data-stu-id="a356f-241">To set the layout to the original layout, open the **Command Palette**, select **PowerShell: Disable ISE Mode (restore to defaults)**.</span></span>

<span data-ttu-id="a356f-242">Para obter detalhes sobre como personalizar o layout do VSCode para o ISE, confira [Como Replicar a Experiência do ISE no Visual Studio Code](/powershell/scripting/components/vscode/how-to-replicate-the-ise-experience-in-vscode)</span><span class="sxs-lookup"><span data-stu-id="a356f-242">For details about customizing the VSCode layout to ISE, see [How to Replicate the ISE Experience in Visual Studio Code](/powershell/scripting/components/vscode/how-to-replicate-the-ise-experience-in-vscode)</span></span>

> [!NOTE]
> <span data-ttu-id="a356f-243">Não há planos para atualizar o ISE com novos recursos.</span><span class="sxs-lookup"><span data-stu-id="a356f-243">There no plans to update the ISE with new features.</span></span> <span data-ttu-id="a356f-244">Agora, o ISE é um recurso desinstalável pelo usuário nas versões mais recentes do Windows 10 e do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="a356f-244">The ISE is now a user-uninstallable feature in the latest versions of Windows 10 and Windows Server.</span></span> <span data-ttu-id="a356f-245">Não há planos para remover permanentemente o ISE.</span><span class="sxs-lookup"><span data-stu-id="a356f-245">There are no plans to permanently remove the ISE.</span></span> <span data-ttu-id="a356f-246">A equipe do PowerShell e seus parceiros concentram-se em melhorar a experiência de script na extensão do PowerShell para o Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="a356f-246">The PowerShell Team and its partners are focused on improving the scripting experience in the PowerShell extension for Visual Studio Code.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a356f-247">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="a356f-247">Next Steps</span></span>

<span data-ttu-id="a356f-248">Munido do conhecimento para migrar efetivamente, [instale o PowerShell 7](/powershell/scripting/install/installing-powershell-core-on-windows) agora mesmo!</span><span class="sxs-lookup"><span data-stu-id="a356f-248">Armed with the knowledge to effectively migrate, [install PowerShell 7](/powershell/scripting/install/installing-powershell-core-on-windows) now!</span></span>
