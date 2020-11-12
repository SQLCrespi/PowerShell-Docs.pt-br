---
description: A variável de ambiente PSModulePath contém uma lista de locais de pasta que são pesquisados para localizar módulos e recursos.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 11/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_PSModulePath?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSModulePath
ms.openlocfilehash: 5d87f550b3aa8774ae81f68848d5aa252b2e5851
ms.sourcegitcommit: aac365f7813756e16b59322832a904e703e0465b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/12/2020
ms.locfileid: "94524647"
---
# <a name="about-psmodulepath"></a><span data-ttu-id="96bb6-104">Sobre o PSModulePath</span><span class="sxs-lookup"><span data-stu-id="96bb6-104">About PSModulePath</span></span>

<span data-ttu-id="96bb6-105">A `$env:PSModulePath` variável de ambiente contém uma lista de locais de pasta que são pesquisados para localizar módulos e recursos.</span><span class="sxs-lookup"><span data-stu-id="96bb6-105">The `$env:PSModulePath` environment variable contains a list of folder locations that are searched to find modules and resources.</span></span> <span data-ttu-id="96bb6-106">O PowerShell pesquisa recursivamente cada pasta em busca de arquivos de módulo ( `.psd1` ou `.psm1` ).</span><span class="sxs-lookup"><span data-stu-id="96bb6-106">PowerShell recursively searches each folder for module (`.psd1` or `.psm1`) files.</span></span>

<span data-ttu-id="96bb6-107">Por padrão, os locais efetivos atribuídos a `$env:PSModulePath` são:</span><span class="sxs-lookup"><span data-stu-id="96bb6-107">By default, the effective locations assigned to `$env:PSModulePath` are:</span></span>

- <span data-ttu-id="96bb6-108">Locais de todo o sistema: essas pastas contêm módulos que acompanham o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="96bb6-108">System-wide locations: These folders contain modules that ship with PowerShell.</span></span> <span data-ttu-id="96bb6-109">Esses módulos são armazenados na `$PSHOME\Modules` pasta.</span><span class="sxs-lookup"><span data-stu-id="96bb6-109">These modules are store in the `$PSHOME\Modules` folder.</span></span> <span data-ttu-id="96bb6-110">Esse também é o local em que os módulos de gerenciamento do Windows estão instalados.</span><span class="sxs-lookup"><span data-stu-id="96bb6-110">This is also the location where the Windows management modules are installed.</span></span>

- <span data-ttu-id="96bb6-111">Módulos instalados pelo usuário: são módulos instalados pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="96bb6-111">User-installed modules: These are modules installed by the user.</span></span>
  <span data-ttu-id="96bb6-112">`Install-Module` tem um parâmetro de **escopo** que permite que você especifique se o módulo está instalado para o usuário atual ou para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="96bb6-112">`Install-Module` has a **Scope** parameter that allows you to specify whether the module is installed for the current user or for all users.</span></span> <span data-ttu-id="96bb6-113">Para obter mais informações, consulte [install-Module](xref:PowerShellGet.Install-Module).</span><span class="sxs-lookup"><span data-stu-id="96bb6-113">For more information, see [Install-Module](xref:PowerShellGet.Install-Module).</span></span>

  - <span data-ttu-id="96bb6-114">No Windows, o local do escopo **CurrentUser** específico do usuário é a `$HOME\Documents\PowerShell\Modules` pasta.</span><span class="sxs-lookup"><span data-stu-id="96bb6-114">On Windows, the location of the user-specific **CurrentUser** scope is the `$HOME\Documents\PowerShell\Modules` folder.</span></span> <span data-ttu-id="96bb6-115">O local do escopo **AllUsers** é `$env:ProgramFiles\PowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="96bb6-115">The location of the **AllUsers** scope is `$env:ProgramFiles\PowerShell\Modules`.</span></span>
  - <span data-ttu-id="96bb6-116">Em sistemas não Windows, o local do escopo **CurrentUser** específico do usuário é a `$HOME/.local/share/powershell/Modules` pasta.</span><span class="sxs-lookup"><span data-stu-id="96bb6-116">On non-Windows systems, the location of the user-specific **CurrentUser** scope is the `$HOME/.local/share/powershell/Modules` folder.</span></span> <span data-ttu-id="96bb6-117">O local do escopo **AllUsers** é `/usr/local/share/powershell/Modules` .</span><span class="sxs-lookup"><span data-stu-id="96bb6-117">The location of the **AllUsers** scope is `/usr/local/share/powershell/Modules`.</span></span>

<span data-ttu-id="96bb6-118">Além disso, os programas de instalação que instalam módulos em outros diretórios, como o diretório arquivos de programas, podem acrescentar seus locais ao valor de `$env:PSModulePath` .</span><span class="sxs-lookup"><span data-stu-id="96bb6-118">In addition, setup programs that install modules in other directories, such as the Program Files directory, can append their locations to the value of `$env:PSModulePath`.</span></span>

> [!NOTE]
> <span data-ttu-id="96bb6-119">No Windows, o local específico do usuário é a `PowerShell\Modules` pasta localizada na pasta **documentos** em seu perfil de usuário.</span><span class="sxs-lookup"><span data-stu-id="96bb6-119">On Windows, the user-specific location is the `PowerShell\Modules` folder located in the **Documents** folder in your user profile.</span></span> <span data-ttu-id="96bb6-120">O caminho específico desse local varia de acordo com a versão do Windows e se você está usando o redirecionamento de pasta.</span><span class="sxs-lookup"><span data-stu-id="96bb6-120">The specific path of that location varies by version of Windows and whether or not you are using folder redirection.</span></span> <span data-ttu-id="96bb6-121">O Microsoft OneDrive também pode alterar o local da sua pasta de **documentos** .</span><span class="sxs-lookup"><span data-stu-id="96bb6-121">Microsoft OneDrive can also change the location of your **Documents** folder.</span></span> <span data-ttu-id="96bb6-122">Você pode verificar o local da pasta **documentos** usando o seguinte comando: `[Environment]::GetFolderPath('MyDocuments')` .</span><span class="sxs-lookup"><span data-stu-id="96bb6-122">You can verify the location of your **Documents** folder using the following command: `[Environment]::GetFolderPath('MyDocuments')`.</span></span>

## <a name="modifying-psmodulepath"></a><span data-ttu-id="96bb6-123">Modificando PSModulePath</span><span class="sxs-lookup"><span data-stu-id="96bb6-123">Modifying PSModulePath</span></span>

<span data-ttu-id="96bb6-124">Para alterar os diretórios de módulo padrão para a sessão atual, use o seguinte formato de comando para alterar o valor da `PSModulePath` variável de ambiente.</span><span class="sxs-lookup"><span data-stu-id="96bb6-124">To change the default module directories for the current session, use the following command format to change the value of the `PSModulePath` environment variable.</span></span>

<span data-ttu-id="96bb6-125">Por exemplo, para adicionar o `C:\Program Files\Fabrikam\Modules` diretório ao valor da variável de ambiente PSModulePath, digite:</span><span class="sxs-lookup"><span data-stu-id="96bb6-125">For example, to add the `C:\Program Files\Fabrikam\Modules` directory to the value of the PSModulePath environment variable, type:</span></span>

```powershell
$Env:PSModulePath = $Env:PSModulePath+";C:\Program Files\Fabrikam\Modules"
```

<span data-ttu-id="96bb6-126">O ponto e vírgula ( `;` ) no comando separa o novo caminho do caminho que o precede na lista.</span><span class="sxs-lookup"><span data-stu-id="96bb6-126">The semi-colon (`;`) in the command separates the new path from the path that precedes it in the list.</span></span> <span data-ttu-id="96bb6-127">Em plataformas não Windows, os dois-pontos () separam `:` os locais de caminho na variável de ambiente.</span><span class="sxs-lookup"><span data-stu-id="96bb6-127">On non-Windows platforms, the colon (`:`) separates the path locations in the environment variable.</span></span>

<span data-ttu-id="96bb6-128">Para alterar o valor de `PSModulePath` em cada sessão, adicione o comando anterior ao seu perfil do PowerShell ou use o método **SetEnvironmentVariable não** da classe **Environment** .</span><span class="sxs-lookup"><span data-stu-id="96bb6-128">To change the value of `PSModulePath` in every session, add the previous command to your PowerShell profile or use the **SetEnvironmentVariable** method of the **Environment** class.</span></span>

<span data-ttu-id="96bb6-129">O comando a seguir usa o método **GetEnvironmentVariable** para obter a configuração do computador `PSModulePath` e o método **SetEnvironmentVariable não** para adicionar o `C:\Program Files\Fabrikam\Modules` caminho ao valor.</span><span class="sxs-lookup"><span data-stu-id="96bb6-129">The following command uses the **GetEnvironmentVariable** method to get the machine setting of `PSModulePath` and the **SetEnvironmentVariable** method to add the `C:\Program Files\Fabrikam\Modules` path to the value.</span></span>

```powershell
$path = [Environment]::GetEnvironmentVariable('PSModulePath', 'Machine')
$newpath = $path + ';C:\Program Files\Fabrikam\Modules'
[Environment]::SetEnvironmentVariable('PSModulePath', $newpath, 'Machine')
```

<span data-ttu-id="96bb6-130">Para adicionar um caminho para a configuração de usuário, altere o valor de destino para **usuário**.</span><span class="sxs-lookup"><span data-stu-id="96bb6-130">To add a path to the user setting, change the target value to **User**.</span></span>

```powershell
$path = [Environment]::GetEnvironmentVariable('PSModulePath', 'User')
$newpath = $path + ';C:\Program Files\Fabrikam\Modules'
[Environment]::SetEnvironmentVariable('PSModulePath', $newpath, 'User')
```

<span data-ttu-id="96bb6-131">Para obter mais informações sobre os métodos da classe **System. Environment** , consulte [métodos de ambiente](/dotnet/api/system.environment).</span><span class="sxs-lookup"><span data-stu-id="96bb6-131">For more information about the methods of the **System.Environment** class, see [Environment Methods](/dotnet/api/system.environment).</span></span>

## <a name="powershell-psmodulepath-construction"></a><span data-ttu-id="96bb6-132">Construção do PowerShell PSModulePath</span><span class="sxs-lookup"><span data-stu-id="96bb6-132">PowerShell PSModulePath construction</span></span>

<span data-ttu-id="96bb6-133">O valor de `$env:PSModulePath` é construído cada vez que o PowerShell é iniciado.</span><span class="sxs-lookup"><span data-stu-id="96bb6-133">The value of `$env:PSModulePath` is constructed each time PowerShell starts.</span></span>
<span data-ttu-id="96bb6-134">O valor varia de acordo com a versão do PowerShell e como ele é iniciado.</span><span class="sxs-lookup"><span data-stu-id="96bb6-134">The value varies by version of PowerShell and how it is launched.</span></span>

### <a name="windows-powershell-startup"></a><span data-ttu-id="96bb6-135">Inicialização do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="96bb6-135">Windows PowerShell startup</span></span>

<span data-ttu-id="96bb6-136">O Windows PowerShell usa a seguinte lógica para construir o `PSModulePath` na inicialização:</span><span class="sxs-lookup"><span data-stu-id="96bb6-136">Windows PowerShell uses the following logic to construct the `PSModulePath` at startup:</span></span>

- <span data-ttu-id="96bb6-137">Se `PSModulePath` não existir, combine **CurrentUser** , **AllUsers** e os `$PSHOME` caminhos dos módulos</span><span class="sxs-lookup"><span data-stu-id="96bb6-137">If `PSModulePath` doesn't exist, combine **CurrentUser** , **AllUsers** , and the `$PSHOME` modules paths</span></span>
- <span data-ttu-id="96bb6-138">Se `PSModulePath` existir:</span><span class="sxs-lookup"><span data-stu-id="96bb6-138">If `PSModulePath` does exist:</span></span>
  - <span data-ttu-id="96bb6-139">Se `PSModulePath` contém o `$PSHOME` caminho dos módulos:</span><span class="sxs-lookup"><span data-stu-id="96bb6-139">If `PSModulePath` contains `$PSHOME` modules path:</span></span>
    - <span data-ttu-id="96bb6-140">O caminho dos módulos **AllUsers** é inserido antes do `$PSHOME` caminho dos módulos</span><span class="sxs-lookup"><span data-stu-id="96bb6-140">**AllUsers** modules path is inserted before `$PSHOME` modules path</span></span>
  - <span data-ttu-id="96bb6-141">restante</span><span class="sxs-lookup"><span data-stu-id="96bb6-141">else:</span></span>
    - <span data-ttu-id="96bb6-142">Basta usar `PSModulePath` conforme definido, pois o usuário removeu o local deliberadamente `$PSHOME`</span><span class="sxs-lookup"><span data-stu-id="96bb6-142">Just use `PSModulePath` as defined since the user deliberately removed the `$PSHOME` location</span></span>

<span data-ttu-id="96bb6-143">O caminho do módulo **CurrentUser** será prefixado somente se o escopo do usuário `$env:PSModulePath` não existir.</span><span class="sxs-lookup"><span data-stu-id="96bb6-143">The **CurrentUser** module path is prefixed only if User scope `$env:PSModulePath` doesn't exist.</span></span> <span data-ttu-id="96bb6-144">Caso contrário, o escopo do usuário `$env:PSModulePath` será usado conforme definido.</span><span class="sxs-lookup"><span data-stu-id="96bb6-144">Otherwise, the User scope `$env:PSModulePath` is used as defined.</span></span>

### <a name="powershell-core-6-startup"></a><span data-ttu-id="96bb6-145">Inicialização do PowerShell Core 6</span><span class="sxs-lookup"><span data-stu-id="96bb6-145">PowerShell Core 6 startup</span></span>

<span data-ttu-id="96bb6-146">O PowerShell Core 6 não usa o conteúdo de `$env:PSModulePath` se detectar que foi iniciado no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="96bb6-146">PowerShell Core 6 doesn't use contents of `$env:PSModulePath` if it detects it was started from PowerShell.</span></span> <span data-ttu-id="96bb6-147">Ele o substitui por:</span><span class="sxs-lookup"><span data-stu-id="96bb6-147">It overwrites it with:</span></span>

- <span data-ttu-id="96bb6-148">Módulos **CurrentUser** caminho + módulos **AllUsers** caminho + `$PSHOME` módulos caminho + módulo módulos do Windows PowerShell `$PSHOME` caminho.</span><span class="sxs-lookup"><span data-stu-id="96bb6-148">**CurrentUser** modules path + **AllUsers** modules path + `$PSHOME` modules path + Windows PowerShell `$PSHOME` modules path.</span></span>

### <a name="powershell-7-startup"></a><span data-ttu-id="96bb6-149">Inicialização do PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="96bb6-149">PowerShell 7 startup</span></span>

<span data-ttu-id="96bb6-150">No Windows, para a maioria das variáveis de ambiente, se a variável no escopo do usuário existir, um novo processo usará esse valor somente se houver uma variável com escopo de computador com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="96bb6-150">In Windows, for most environment variables, if the User-scoped variable exists, a new process uses that value only even if a Machine-scoped variable of the same name exists.</span></span>

<span data-ttu-id="96bb6-151">No PowerShell 7, `PSModulePath` é tratado de maneira semelhante à forma como a `Path` variável de ambiente é tratada no Windows.</span><span class="sxs-lookup"><span data-stu-id="96bb6-151">In PowerShell 7, `PSModulePath` is treated similar to how the `Path` environment variable is treated on Windows.</span></span> <span data-ttu-id="96bb6-152">No Windows, `Path` é tratado de forma diferente de outras variáveis de ambiente.</span><span class="sxs-lookup"><span data-stu-id="96bb6-152">On Windows, `Path` is treated differently from other environment variables.</span></span> <span data-ttu-id="96bb6-153">Quando um processo é iniciado, o Windows combina o escopo do usuário `Path` com o escopo da máquina `Path` .</span><span class="sxs-lookup"><span data-stu-id="96bb6-153">When a process is started, Windows combines the User-scoped `Path` with the Machine-scoped `Path`.</span></span>

- <span data-ttu-id="96bb6-154">Recuperar o escopo do usuário `PSModulePath`</span><span class="sxs-lookup"><span data-stu-id="96bb6-154">Retrieve the User-scoped `PSModulePath`</span></span>
- <span data-ttu-id="96bb6-155">Comparar para processar variável de ambiente herdada `PSModulePath`</span><span class="sxs-lookup"><span data-stu-id="96bb6-155">Compare to process inherited `PSModulePath` environment variable</span></span>
  - <span data-ttu-id="96bb6-156">Se o mesmo:</span><span class="sxs-lookup"><span data-stu-id="96bb6-156">If the same:</span></span>
    - <span data-ttu-id="96bb6-157">Acrescente o **AllUsers** `PSModulePath` ao final seguindo a semântica da `Path` variável de ambiente</span><span class="sxs-lookup"><span data-stu-id="96bb6-157">Append the **AllUsers** `PSModulePath` to the end following the semantics of the `Path` environment variable</span></span>
    - <span data-ttu-id="96bb6-158">O caminho do Windows `System32` vem do computador definido `PSModulePath` , portanto, não precisa ser adicionado explicitamente</span><span class="sxs-lookup"><span data-stu-id="96bb6-158">The Windows `System32` path comes from the machine defined `PSModulePath` so does not need to be added explicitly</span></span>
  - <span data-ttu-id="96bb6-159">Se for diferente, trate como se o usuário o modificou explicitamente e não acrescente **AllUsers**`PSModulePath`</span><span class="sxs-lookup"><span data-stu-id="96bb6-159">If different, treat as though user explicitly modified it and don't append **AllUsers** `PSModulePath`</span></span>
- <span data-ttu-id="96bb6-160">Prefixo com o usuário PS7, o sistema e os `$PSHOME` caminhos nessa ordem</span><span class="sxs-lookup"><span data-stu-id="96bb6-160">Prefix with PS7 User, System, and `$PSHOME` paths in that order</span></span>
  - <span data-ttu-id="96bb6-161">Se `powershell.config.json` contiver um escopo de usuário `PSModulePath` , use-o em vez do padrão para o usuário</span><span class="sxs-lookup"><span data-stu-id="96bb6-161">If `powershell.config.json` contains a user scoped `PSModulePath`, use that instead of the default for the user</span></span>
  - <span data-ttu-id="96bb6-162">Se `powershell.config.json` contiver um escopo do sistema `PSModulePath` , use-o em vez do padrão para o sistema</span><span class="sxs-lookup"><span data-stu-id="96bb6-162">If `powershell.config.json` contains a system scoped `PSModulePath`, use that instead of the default for the system</span></span>

<span data-ttu-id="96bb6-163">Os sistemas Unix não têm uma separação de variáveis de ambiente do usuário e do sistema.</span><span class="sxs-lookup"><span data-stu-id="96bb6-163">Unix systems don't have a separation of User and System environment variables.</span></span>
<span data-ttu-id="96bb6-164">`PSModulePath` é herdado e os caminhos específicos de PS7 são prefixados se ainda não estiverem definidos.</span><span class="sxs-lookup"><span data-stu-id="96bb6-164">`PSModulePath` is inherited and the PS7-specific paths are prefixed if not already defined.</span></span>

### <a name="starting-windows-powershell-from-powershell-7"></a><span data-ttu-id="96bb6-165">Iniciando o Windows PowerShell do PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="96bb6-165">Starting Windows PowerShell from PowerShell 7</span></span>

<span data-ttu-id="96bb6-166">Para essa discussão, o _Windows PowerShell_ significa `powershell.exe` e `powershell_ise.exe` .</span><span class="sxs-lookup"><span data-stu-id="96bb6-166">For this discussion, _Windows PowerShell_ means both `powershell.exe` and `powershell_ise.exe`.</span></span>

<span data-ttu-id="96bb6-167">O valor de `$env:PSModulePath` é copiado para `WinPSModulePath` com as seguintes modificações:</span><span class="sxs-lookup"><span data-stu-id="96bb6-167">The value of `$env:PSModulePath` is copied to `WinPSModulePath` with the following modifications:</span></span>

- <span data-ttu-id="96bb6-168">Remover PS7 o caminho do módulo de usuário</span><span class="sxs-lookup"><span data-stu-id="96bb6-168">Remove PS7 the User module path</span></span>
- <span data-ttu-id="96bb6-169">Remover PS7 o caminho do módulo do sistema</span><span class="sxs-lookup"><span data-stu-id="96bb6-169">Remove PS7 the System module path</span></span>
- <span data-ttu-id="96bb6-170">Remover PS7 o `$PSHOME` caminho do módulo</span><span class="sxs-lookup"><span data-stu-id="96bb6-170">Remove PS7 the `$PSHOME` module path</span></span>

<span data-ttu-id="96bb6-171">Os caminhos PS7 são removidos para que os módulos PS7 não sejam carregados no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="96bb6-171">The PS7 paths are removed so that PS7 modules don't get loaded in Windows PowerShell.</span></span> <span data-ttu-id="96bb6-172">O `WinPSModulePath` valor é usado ao iniciar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="96bb6-172">The `WinPSModulePath` value is used when starting Windows PowerShell.</span></span>

### <a name="starting-powershell-7-from-windows-powershell"></a><span data-ttu-id="96bb6-173">Iniciando o PowerShell 7 do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="96bb6-173">Starting PowerShell 7 from Windows PowerShell</span></span>

<span data-ttu-id="96bb6-174">A inicialização do PowerShell 7 continua no estado em que se encontra com a adição de caminhos herdados que o Windows PowerShell adicionou.</span><span class="sxs-lookup"><span data-stu-id="96bb6-174">The PowerShell 7 startup continues as-is with the addition of inheriting paths that Windows PowerShell added.</span></span> <span data-ttu-id="96bb6-175">Como os caminhos específicos do PS7 são prefixados, não há nenhum problema funcional.</span><span class="sxs-lookup"><span data-stu-id="96bb6-175">Since the PS7-specific paths are prefixed, there is no functional issue.</span></span>

### <a name="starting-powershell-6-from-powershell-7"></a><span data-ttu-id="96bb6-176">Iniciando o PowerShell 6 do PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="96bb6-176">Starting PowerShell 6 from PowerShell 7</span></span>

<span data-ttu-id="96bb6-177">O PowerShell Core 6 substitui `$env:PSModulePath` .</span><span class="sxs-lookup"><span data-stu-id="96bb6-177">PowerShell Core 6 overwrites `$env:PSModulePath`.</span></span> <span data-ttu-id="96bb6-178">Nenhuma alteração é feita.</span><span class="sxs-lookup"><span data-stu-id="96bb6-178">No changes are made.</span></span>

### <a name="starting-powershell-7-from-powershell-6"></a><span data-ttu-id="96bb6-179">Iniciando o PowerShell 7 do PowerShell 6</span><span class="sxs-lookup"><span data-stu-id="96bb6-179">Starting PowerShell 7 from PowerShell 6</span></span>

<span data-ttu-id="96bb6-180">A inicialização do PowerShell 7 continua no estado em que se encontra com a adição de caminhos herdados que o PowerShell Core 6 adicionou.</span><span class="sxs-lookup"><span data-stu-id="96bb6-180">The PowerShell 7 startup continues as-is with the addition of inheriting paths that PowerShell Core 6 added.</span></span> <span data-ttu-id="96bb6-181">Como os caminhos específicos do PS7 são prefixados, não há nenhum problema funcional.</span><span class="sxs-lookup"><span data-stu-id="96bb6-181">Since the PS7-specific paths are prefixed, there is no functional issue.</span></span>

## <a name="module-search-behavior"></a><span data-ttu-id="96bb6-182">Comportamento de pesquisa de módulo</span><span class="sxs-lookup"><span data-stu-id="96bb6-182">Module search behavior</span></span>

<span data-ttu-id="96bb6-183">O PowerShell pesquisa recursivamente cada pasta no **PSModulePath** para arquivos de módulo ( `.psd1` ou `.psm1` ).</span><span class="sxs-lookup"><span data-stu-id="96bb6-183">PowerShell recursively searches each folder in the **PSModulePath** for module (`.psd1` or `.psm1`) files.</span></span> <span data-ttu-id="96bb6-184">Esse padrão de pesquisa permite que várias versões do mesmo módulo sejam instaladas em pastas diferentes.</span><span class="sxs-lookup"><span data-stu-id="96bb6-184">This search pattern allows multiple versions of the same module to be installed in different folders.</span></span> <span data-ttu-id="96bb6-185">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="96bb6-185">For example:</span></span>

```Output
    Directory: C:\Program Files\WindowsPowerShell\Modules\PowerShellGet

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d----           8/14/2020  5:56 PM                1.0.0.1
d----           9/13/2019  3:53 PM                2.1.2
```

<span data-ttu-id="96bb6-186">Por padrão, o PowerShell carrega o número de versão mais alto de um módulo quando várias versões são encontradas.</span><span class="sxs-lookup"><span data-stu-id="96bb6-186">By default, PowerShell loads the highest version number of a module when multiple versions are found.</span></span> <span data-ttu-id="96bb6-187">Para carregar uma versão específica, use `Import-Module` com o parâmetro **FullyQualifiedName** .</span><span class="sxs-lookup"><span data-stu-id="96bb6-187">To load a specific version, use `Import-Module` with the **FullyQualifiedName** parameter.</span></span> <span data-ttu-id="96bb6-188">Para obter mais informações, consulte [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module).</span><span class="sxs-lookup"><span data-stu-id="96bb6-188">For more information, see [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module).</span></span>

## <a name="see-also"></a><span data-ttu-id="96bb6-189">Confira também</span><span class="sxs-lookup"><span data-stu-id="96bb6-189">See also</span></span>

- [<span data-ttu-id="96bb6-190">about_Modules</span><span class="sxs-lookup"><span data-stu-id="96bb6-190">about_Modules</span></span>](about_Modules.md)
- [<span data-ttu-id="96bb6-191">Métodos de ambiente</span><span class="sxs-lookup"><span data-stu-id="96bb6-191">Environment Methods</span></span>](/dotnet/api/system.environment)
