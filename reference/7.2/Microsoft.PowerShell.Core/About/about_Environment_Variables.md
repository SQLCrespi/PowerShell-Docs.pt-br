---
description: Descreve como acessar variáveis de ambiente do Windows no PowerShell.
Locale: en-US
ms.date: 09/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_environment_variables?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Environment_Variables
ms.openlocfilehash: 66d2bcd76651a7231a670ee5b02b99d6edd63a72
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603774"
---
# <a name="about-environment-variables"></a><span data-ttu-id="1800a-103">Sobre variáveis de ambiente</span><span class="sxs-lookup"><span data-stu-id="1800a-103">About Environment Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="1800a-104">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="1800a-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="1800a-105">Descreve como acessar variáveis de ambiente do Windows no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1800a-105">Describes how to access Windows environment variables in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="1800a-106">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="1800a-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="1800a-107">As variáveis de ambiente armazenam informações sobre o ambiente do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="1800a-107">Environment variables store information about the operating system environment.</span></span> <span data-ttu-id="1800a-108">Essas informações incluem detalhes como o caminho do sistema operacional, o número de processadores usados pelo sistema operacional e o local das pastas temporárias.</span><span class="sxs-lookup"><span data-stu-id="1800a-108">This information includes details such as the operating system path, the number of processors used by the operating system, and the location of temporary folders.</span></span>

<span data-ttu-id="1800a-109">As variáveis de ambiente armazenam dados que são usados pelo sistema operacional e outros programas.</span><span class="sxs-lookup"><span data-stu-id="1800a-109">The environment variables store data that is used by the operating system and other programs.</span></span> <span data-ttu-id="1800a-110">Por exemplo, a `WINDIR` variável de ambiente contém o local do diretório de instalação do Windows.</span><span class="sxs-lookup"><span data-stu-id="1800a-110">For example, the `WINDIR` environment variable contains the location of the Windows installation directory.</span></span> <span data-ttu-id="1800a-111">Os programas podem consultar o valor dessa variável para determinar onde os arquivos do sistema operacional Windows estão localizados.</span><span class="sxs-lookup"><span data-stu-id="1800a-111">Programs can query the value of this variable to determine where Windows operating system files are located.</span></span>

<span data-ttu-id="1800a-112">O PowerShell pode acessar e gerenciar variáveis de ambiente em qualquer uma das plataformas de sistema operacional com suporte.</span><span class="sxs-lookup"><span data-stu-id="1800a-112">PowerShell can access and manage environment variables in any of the supported operating system platforms.</span></span> <span data-ttu-id="1800a-113">O provedor de ambiente do PowerShell simplifica esse processo, facilitando a exibição e a alteração das variáveis de ambiente.</span><span class="sxs-lookup"><span data-stu-id="1800a-113">The PowerShell environment provider simplifies this process by making it easy to view and change environment variables.</span></span>

<span data-ttu-id="1800a-114">Variáveis de ambiente, ao contrário de outros tipos de variáveis no PowerShell, são herdadas por processos filho, como trabalhos em segundo plano locais e as sessões em que os membros do módulo são executados.</span><span class="sxs-lookup"><span data-stu-id="1800a-114">Environment variables, unlike other types of variables in PowerShell, are inherited by child processes, such as local background jobs and the sessions in which module members run.</span></span> <span data-ttu-id="1800a-115">Isso torna as variáveis de ambiente adequadas para armazenar valores que são necessários nos processos pai e filho.</span><span class="sxs-lookup"><span data-stu-id="1800a-115">This makes environment variables well suited to storing values that are needed in both parent and child processes.</span></span>

## <a name="using-and-changing-environment-variables"></a><span data-ttu-id="1800a-116">Usando e alterando variáveis de ambiente</span><span class="sxs-lookup"><span data-stu-id="1800a-116">Using and changing environment variables</span></span>

<span data-ttu-id="1800a-117">No Windows, as variáveis de ambiente podem ser definidas em três escopos:</span><span class="sxs-lookup"><span data-stu-id="1800a-117">On Windows, environment variables can be defined in three scopes:</span></span>

- <span data-ttu-id="1800a-118">Escopo da máquina (ou do sistema)</span><span class="sxs-lookup"><span data-stu-id="1800a-118">Machine (or System) scope</span></span>
- <span data-ttu-id="1800a-119">Escopo do usuário</span><span class="sxs-lookup"><span data-stu-id="1800a-119">User scope</span></span>
- <span data-ttu-id="1800a-120">Escopo do processo</span><span class="sxs-lookup"><span data-stu-id="1800a-120">Process scope</span></span>

<span data-ttu-id="1800a-121">O escopo do _processo_ contém as variáveis de ambiente disponíveis no processo atual ou na sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1800a-121">The _Process_ scope contains the environment variables available in the current process, or PowerShell session.</span></span> <span data-ttu-id="1800a-122">Essa lista de variáveis é herdada do processo pai e é construída a partir das variáveis nos escopos de _computador_ e de _usuário_ .</span><span class="sxs-lookup"><span data-stu-id="1800a-122">This list of variables is inherited from the parent process and is constructed from the variables in the _Machine_ and _User_ scopes.</span></span> <span data-ttu-id="1800a-123">As plataformas baseadas em UNIX têm apenas o escopo do _processo_ .</span><span class="sxs-lookup"><span data-stu-id="1800a-123">Unix-based platforms only have the _Process_ scope.</span></span>

<span data-ttu-id="1800a-124">Você pode exibir e alterar os valores das variáveis de ambiente sem usar um cmdlet usando uma sintaxe de variável com o provedor de ambiente.</span><span class="sxs-lookup"><span data-stu-id="1800a-124">You can display and change the values of environment variables without using a cmdlet by using a variable syntax with the environment provider.</span></span> <span data-ttu-id="1800a-125">Para exibir o valor de uma variável de ambiente, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="1800a-125">To display the value of an environment variable, use the following syntax:</span></span>

```
$Env:<variable-name>
```

<span data-ttu-id="1800a-126">Por exemplo, para exibir o valor da `WINDIR` variável de ambiente, digite o seguinte comando no prompt de comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1800a-126">For example, to display the value of the `WINDIR` environment variable, type the following command at the PowerShell command prompt:</span></span>

```powershell
$Env:windir
```

<span data-ttu-id="1800a-127">Nessa sintaxe, o cifrão ( `$` ) indica uma variável e o nome da unidade ( `Env:` ) indica uma variável de ambiente seguida pelo nome da variável ( `windir` ).</span><span class="sxs-lookup"><span data-stu-id="1800a-127">In this syntax, the dollar sign (`$`) indicates a variable, and the drive name (`Env:`) indicates an environment variable followed by the variable name (`windir`).</span></span>

<span data-ttu-id="1800a-128">Quando você altera as variáveis de ambiente no PowerShell, a alteração afeta apenas a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="1800a-128">When you change environment variables in PowerShell, the change affects only the current session.</span></span> <span data-ttu-id="1800a-129">Esse comportamento é semelhante ao comportamento do `Set` comando no Shell de comando do Windows e no `Setenv` comando em ambientes baseados em UNIX.</span><span class="sxs-lookup"><span data-stu-id="1800a-129">This behavior resembles the behavior of the `Set` command in the Windows Command Shell and the `Setenv` command in UNIX-based environments.</span></span> <span data-ttu-id="1800a-130">Para alterar valores nos escopos do computador ou do usuário, você deve usar os métodos da classe **System. Environment** .</span><span class="sxs-lookup"><span data-stu-id="1800a-130">To change values in the Machine or User scopes, you must use the methods of the **System.Environment** class.</span></span>

<span data-ttu-id="1800a-131">Para fazer alterações em variáveis no escopo do computador, também deve ter permissão.</span><span class="sxs-lookup"><span data-stu-id="1800a-131">To make changes to Machine-scoped variables, must also have permission.</span></span> <span data-ttu-id="1800a-132">Se você tentar alterar um valor sem permissão suficiente, o comando falhará e o PowerShell exibirá um erro.</span><span class="sxs-lookup"><span data-stu-id="1800a-132">If you try to change a value without sufficient permission, the command fails and PowerShell displays an error.</span></span>

<span data-ttu-id="1800a-133">Você pode alterar os valores de variáveis sem usar um cmdlet usando a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="1800a-133">You can change the values of variables without using a cmdlet using the following syntax:</span></span>

```powershell
$Env:<variable-name> = "<new-value>"
```

<span data-ttu-id="1800a-134">Por exemplo, para acrescentar `;c:\temp` ao valor da variável de `Path` ambiente, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="1800a-134">For example, to append `;c:\temp` to the value of the `Path` environment variable, use the following syntax:</span></span>

```powershell
$Env:Path += ";c:\temp"
```

<span data-ttu-id="1800a-135">No Linux ou MacOS, os dois-pontos ( `:` ) no comando separam o novo caminho do caminho que o precede na lista.</span><span class="sxs-lookup"><span data-stu-id="1800a-135">On Linux or MacOS, the colon (`:`) in the command separates the new path from the path that precedes it in the list.</span></span>

```powershell
$Env:PATH += ":/usr/local/temp"
```

<span data-ttu-id="1800a-136">Você também pode usar os cmdlets do item, como `Set-Item` , `Remove-Item` e `Copy-Item` para alterar os valores das variáveis de ambiente.</span><span class="sxs-lookup"><span data-stu-id="1800a-136">You can also use the Item cmdlets, such as `Set-Item`, `Remove-Item`, and `Copy-Item` to change the values of environment variables.</span></span> <span data-ttu-id="1800a-137">Por exemplo, para usar o `Set-Item` cmdlet para acrescentar `;c:\temp` ao valor da variável de `Path` ambiente, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="1800a-137">For example, to use the `Set-Item` cmdlet to append `;c:\temp` to the value of the `Path` environment variable, use the following syntax:</span></span>

```powershell
Set-Item -Path Env:Path -Value ($Env:Path + ";C:\Temp")
```

<span data-ttu-id="1800a-138">Nesse comando, o valor é colocado entre parênteses para que seja interpretado como uma unidade.</span><span class="sxs-lookup"><span data-stu-id="1800a-138">In this command, the value is enclosed in parentheses so that it is interpreted as a unit.</span></span>

## <a name="environment-variables-that-store-preferences"></a><span data-ttu-id="1800a-139">Variáveis de ambiente que armazenam preferências</span><span class="sxs-lookup"><span data-stu-id="1800a-139">Environment variables that store preferences</span></span>

<span data-ttu-id="1800a-140">Os recursos do PowerShell podem usar variáveis de ambiente para armazenar as preferências do usuário.</span><span class="sxs-lookup"><span data-stu-id="1800a-140">PowerShell features can use environment variables to store user preferences.</span></span>
<span data-ttu-id="1800a-141">Essas variáveis funcionam como variáveis de preferência, mas são herdadas por sessões filho das sessões nas quais elas são criadas.</span><span class="sxs-lookup"><span data-stu-id="1800a-141">These variables work like preference variables, but they are inherited by child sessions of the sessions in which they are created.</span></span> <span data-ttu-id="1800a-142">Para obter mais informações sobre variáveis de preferência, consulte [about_Preference_Variables](about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="1800a-142">For more information about preference variables, see [about_preference_variables](about_Preference_Variables.md).</span></span>

<span data-ttu-id="1800a-143">As variáveis de ambiente que armazenam as preferências incluem:</span><span class="sxs-lookup"><span data-stu-id="1800a-143">The environment variables that store preferences include:</span></span>

- <span data-ttu-id="1800a-144">PSExecutionPolicyPreference</span><span class="sxs-lookup"><span data-stu-id="1800a-144">PSExecutionPolicyPreference</span></span>

  <span data-ttu-id="1800a-145">Armazena a política de execução definida para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="1800a-145">Stores the execution policy set for the current session.</span></span> <span data-ttu-id="1800a-146">Essa variável de ambiente existe somente quando você define uma política de execução para uma única sessão.</span><span class="sxs-lookup"><span data-stu-id="1800a-146">This environment variable exists only when you set an execution policy for a single session.</span></span>
  <span data-ttu-id="1800a-147">Você pode fazer isso de duas maneiras diferentes.</span><span class="sxs-lookup"><span data-stu-id="1800a-147">You can do this in two different ways.</span></span>

  - <span data-ttu-id="1800a-148">Inicie uma sessão na linha de comando usando o parâmetro **ExecutionPolicy** para definir a política de execução para a sessão.</span><span class="sxs-lookup"><span data-stu-id="1800a-148">Start a session from the command line using the **ExecutionPolicy** parameter to set the execution policy for the session.</span></span>

  - <span data-ttu-id="1800a-149">Use o cmdlet `Set-ExecutionPolicy`.</span><span class="sxs-lookup"><span data-stu-id="1800a-149">Use the `Set-ExecutionPolicy` cmdlet.</span></span> <span data-ttu-id="1800a-150">Use o parâmetro de escopo com um valor de "processo".</span><span class="sxs-lookup"><span data-stu-id="1800a-150">Use the Scope parameter with a value of "Process".</span></span>

    <span data-ttu-id="1800a-151">Para obter mais informações, consulte [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="1800a-151">For more information, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

- <span data-ttu-id="1800a-152">PSModuleAnalysisCachePath</span><span class="sxs-lookup"><span data-stu-id="1800a-152">PSModuleAnalysisCachePath</span></span>

  <span data-ttu-id="1800a-153">O PowerShell fornece controle sobre o arquivo usado para armazenar em cache dados sobre módulos e seus cmdlets.</span><span class="sxs-lookup"><span data-stu-id="1800a-153">PowerShell provides control over the file that is used to cache data about modules and their cmdlets.</span></span> <span data-ttu-id="1800a-154">O cache é lido na inicialização durante a pesquisa de um comando e é gravado em um thread em segundo plano depois que um módulo é importado.</span><span class="sxs-lookup"><span data-stu-id="1800a-154">The cache is read at startup while searching for a command and is written on a background thread sometime after a module is imported.</span></span>

  <span data-ttu-id="1800a-155">O local padrão do cache é:</span><span class="sxs-lookup"><span data-stu-id="1800a-155">Default location of the cache is:</span></span>

  - <span data-ttu-id="1800a-156">Windows PowerShell 5.1: `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell`</span><span class="sxs-lookup"><span data-stu-id="1800a-156">Windows PowerShell 5.1: `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell`</span></span>
  - <span data-ttu-id="1800a-157">PowerShell 6,0 e superior: `$env:LOCALAPPDATA\Microsoft\PowerShell`</span><span class="sxs-lookup"><span data-stu-id="1800a-157">PowerShell 6.0 and higher: `$env:LOCALAPPDATA\Microsoft\PowerShell`</span></span>
  - <span data-ttu-id="1800a-158">Padrão não Windows: `~/.cache/powershell`</span><span class="sxs-lookup"><span data-stu-id="1800a-158">Non-Windows default: `~/.cache/powershell`</span></span>

  <span data-ttu-id="1800a-159">O nome de arquivo padrão para o cache é `ModuleAnalysisCache` .</span><span class="sxs-lookup"><span data-stu-id="1800a-159">The default filename for the cache is `ModuleAnalysisCache`.</span></span> <span data-ttu-id="1800a-160">Quando você tem várias instâncias do PowerShell instaladas, o nome de arquivo inclui um sufixo hexadecimal para que haja um nome de arquivo exclusivo por instalação.</span><span class="sxs-lookup"><span data-stu-id="1800a-160">When you have multiple instances of PowerShell installed, the filename includes a hexadecimal suffix so that there is a a unique filename per installation.</span></span>

  > [!NOTE]
  > <span data-ttu-id="1800a-161">Se a descoberta de comando não estiver funcionando corretamente, por exemplo, o IntelliSense mostrará os comandos que não existem, você poderá excluir o arquivo de cache.</span><span class="sxs-lookup"><span data-stu-id="1800a-161">If command discovery isn't working correctly, for example Intellisense shows commands that don't exist, you can delete the cache file.</span></span> <span data-ttu-id="1800a-162">O cache é recriado na próxima vez que você iniciar o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1800a-162">The cache is recreated the next time you start PowerShell.</span></span>

  <span data-ttu-id="1800a-163">Para alterar o local padrão do cache, defina a variável de ambiente antes de iniciar o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1800a-163">To change the default location of the cache, set the environment variable before starting PowerShell.</span></span> <span data-ttu-id="1800a-164">As alterações nessa variável de ambiente afetam apenas os processos filho.</span><span class="sxs-lookup"><span data-stu-id="1800a-164">Changes to this environment variable only affect child processes.</span></span> <span data-ttu-id="1800a-165">O valor deve nomear um caminho completo (incluindo nome do arquivo) em que o PowerShell tenha permissão para criar e gravar arquivos.</span><span class="sxs-lookup"><span data-stu-id="1800a-165">The value should name a full path (including filename) that PowerShell has permission to create and write files.</span></span>

  <span data-ttu-id="1800a-166">Para desabilitar o cache de arquivo, defina esse valor para um local inválido, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1800a-166">To disable the file cache, set this value to an invalid location, for example:</span></span>

  ```powershell
  # `NUL` here is a special device on Windows that cannot be written to,
  # on non-Windows you would use `/dev/null`
  $env:PSModuleAnalysisCachePath = 'NUL'
  ```

  <span data-ttu-id="1800a-167">Isso define o caminho para o dispositivo **nul** .</span><span class="sxs-lookup"><span data-stu-id="1800a-167">This sets the path to the **NUL** device.</span></span> <span data-ttu-id="1800a-168">O PowerShell não pode gravar no caminho, mas nenhum erro é retornado.</span><span class="sxs-lookup"><span data-stu-id="1800a-168">PowerShell can't write to the path but no error is returned.</span></span> <span data-ttu-id="1800a-169">Você pode ver os erros relatados usando um rastreador:</span><span class="sxs-lookup"><span data-stu-id="1800a-169">You can see the errors reported using a tracer:</span></span>

  ```powershell
  Trace-Command -PSHost -Name Modules -Expression { Import-Module Microsoft.PowerShell.Management -Force }
  ```

- <span data-ttu-id="1800a-170">PSDisableModuleAnalysisCacheCleanup</span><span class="sxs-lookup"><span data-stu-id="1800a-170">PSDisableModuleAnalysisCacheCleanup</span></span>

  <span data-ttu-id="1800a-171">Ao gravar o cache de análise de módulo, o PowerShell verifica se há módulos que não existem mais para evitar um cache desnecessariamente grande.</span><span class="sxs-lookup"><span data-stu-id="1800a-171">When writing out the module analysis cache, PowerShell checks for modules that no longer exist to avoid an unnecessarily large cache.</span></span> <span data-ttu-id="1800a-172">Às vezes, essas verificações não são desejáveis; nesse caso, você pode desativá-las definindo esse valor de variável de ambiente como `1` .</span><span class="sxs-lookup"><span data-stu-id="1800a-172">Sometimes these checks are not desirable, in which case you can turn them off by setting this environment variable value to `1`.</span></span>

  <span data-ttu-id="1800a-173">Definir essa variável de ambiente entra em vigor imediatamente no processo atual.</span><span class="sxs-lookup"><span data-stu-id="1800a-173">Setting this environment variable takes effect immediately in the current process.</span></span>

- <span data-ttu-id="1800a-174">PSModulePath</span><span class="sxs-lookup"><span data-stu-id="1800a-174">PSModulePath</span></span>

  <span data-ttu-id="1800a-175">A `$env:PSModulePath` variável de ambiente contém uma lista de locais de pasta que são pesquisados para localizar módulos e recursos.</span><span class="sxs-lookup"><span data-stu-id="1800a-175">The `$env:PSModulePath` environment variable contains a list of folder locations that are searched to find modules and resources.</span></span>

  <span data-ttu-id="1800a-176">Por padrão, os locais efetivos atribuídos a `$env:PSModulePath` são:</span><span class="sxs-lookup"><span data-stu-id="1800a-176">By default, the effective locations assigned to `$env:PSModulePath` are:</span></span>

  - <span data-ttu-id="1800a-177">Locais de todo o sistema: essas pastas contêm módulos que acompanham o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1800a-177">System-wide locations: These folders contain modules that ship with PowerShell.</span></span> <span data-ttu-id="1800a-178">Os módulos são armazenados no `$PSHOME\Modules` local.</span><span class="sxs-lookup"><span data-stu-id="1800a-178">The modules are store in the `$PSHOME\Modules` location.</span></span> <span data-ttu-id="1800a-179">Além disso, esse é o local onde os módulos de gerenciamento do Windows estão instalados.</span><span class="sxs-lookup"><span data-stu-id="1800a-179">Also, This is the location where the Windows management modules are installed.</span></span>

  - <span data-ttu-id="1800a-180">Módulos instalados pelo usuário: são módulos instalados pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="1800a-180">User-installed modules: These are modules installed by the user.</span></span>
    <span data-ttu-id="1800a-181">`Install-Module` tem um parâmetro de **escopo** que permite que você especifique se o módulo está instalado para o usuário atual ou para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="1800a-181">`Install-Module` has a **Scope** parameter that allows you to specify whether the module is installed for the current user or for all users.</span></span> <span data-ttu-id="1800a-182">Para obter mais informações, consulte [install-Module](xref:PowerShellGet.Install-Module).</span><span class="sxs-lookup"><span data-stu-id="1800a-182">For more information, see [Install-Module](xref:PowerShellGet.Install-Module).</span></span>

    - <span data-ttu-id="1800a-183">No Windows, o local do escopo **CurrentUser** específico do usuário é a `$HOME\Documents\PowerShell\Modules` pasta.</span><span class="sxs-lookup"><span data-stu-id="1800a-183">On Windows, the location of the user-specific **CurrentUser** scope is the `$HOME\Documents\PowerShell\Modules` folder.</span></span> <span data-ttu-id="1800a-184">O local do escopo **AllUsers** é `$env:ProgramFiles\PowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="1800a-184">The location of the **AllUsers** scope is `$env:ProgramFiles\PowerShell\Modules`.</span></span>
    - <span data-ttu-id="1800a-185">Em sistemas não Windows, o local do escopo **CurrentUser** específico do usuário é a `$HOME/.local/share/powershell/Modules` pasta.</span><span class="sxs-lookup"><span data-stu-id="1800a-185">On non-Windows systems, the location of the user-specific **CurrentUser** scope is the `$HOME/.local/share/powershell/Modules` folder.</span></span> <span data-ttu-id="1800a-186">O local do escopo **AllUsers** é `/usr/local/share/powershell/Modules` .</span><span class="sxs-lookup"><span data-stu-id="1800a-186">The location of the **AllUsers** scope is `/usr/local/share/powershell/Modules`.</span></span>

  <span data-ttu-id="1800a-187">Além disso, os programas de instalação que instalam módulos em outros diretórios, como o diretório arquivos de programas, podem acrescentar seus locais ao valor de `$env:PSModulePath` .</span><span class="sxs-lookup"><span data-stu-id="1800a-187">In addition, setup programs that install modules in other directories, such as the Program Files directory, can append their locations to the value of `$env:PSModulePath`.</span></span>

  <span data-ttu-id="1800a-188">Para obter mais informações, consulte [about_PSModulePath](about_PSModulePath.md).</span><span class="sxs-lookup"><span data-stu-id="1800a-188">For more information, see [about_PSModulePath](about_PSModulePath.md).</span></span>

## <a name="managing-environment-variables"></a><span data-ttu-id="1800a-189">Gerenciar variáveis de ambiente</span><span class="sxs-lookup"><span data-stu-id="1800a-189">Managing environment variables</span></span>

<span data-ttu-id="1800a-190">O PowerShell fornece vários métodos diferentes para gerenciar variáveis de ambiente.</span><span class="sxs-lookup"><span data-stu-id="1800a-190">PowerShell provides several different methods for managing environment variables.</span></span>

- <span data-ttu-id="1800a-191">A unidade do provedor de ambiente</span><span class="sxs-lookup"><span data-stu-id="1800a-191">The Environment provider drive</span></span>
- <span data-ttu-id="1800a-192">Os cmdlets do item</span><span class="sxs-lookup"><span data-stu-id="1800a-192">The Item cmdlets</span></span>
- <span data-ttu-id="1800a-193">A classe **System. Environment** do .net</span><span class="sxs-lookup"><span data-stu-id="1800a-193">The .NET **System.Environment** class</span></span>
- <span data-ttu-id="1800a-194">No Windows, o painel de controle do sistema</span><span class="sxs-lookup"><span data-stu-id="1800a-194">On Windows, the System Control Panel</span></span>

### <a name="using-the-environment-provider"></a><span data-ttu-id="1800a-195">Usando o provedor de ambiente</span><span class="sxs-lookup"><span data-stu-id="1800a-195">Using the Environment provider</span></span>

<span data-ttu-id="1800a-196">Cada variável de ambiente é representada por uma instância da classe **System. Collections. DictionaryEntry** .</span><span class="sxs-lookup"><span data-stu-id="1800a-196">Each environment variable is represented by an instance of the **System.Collections.DictionaryEntry** class.</span></span> <span data-ttu-id="1800a-197">Em cada objeto **DictionaryEntry** , o nome da variável de ambiente é a chave de dicionário.</span><span class="sxs-lookup"><span data-stu-id="1800a-197">In each **DictionaryEntry** object, the name of the environment variable is the dictionary key.</span></span> <span data-ttu-id="1800a-198">O valor da variável é o valor do dicionário.</span><span class="sxs-lookup"><span data-stu-id="1800a-198">The value of the variable is the dictionary value.</span></span>

<span data-ttu-id="1800a-199">Para exibir as propriedades e os métodos do objeto que representa uma variável de ambiente no PowerShell, use o `Get-Member` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1800a-199">To display the properties and methods of the object that represents an environment variable in PowerShell, use the `Get-Member` cmdlet.</span></span> <span data-ttu-id="1800a-200">Por exemplo, para exibir os métodos e as propriedades de todos os objetos na `Env:` unidade, digite:</span><span class="sxs-lookup"><span data-stu-id="1800a-200">For example, to display the methods and properties of all the objects in the `Env:` drive, type:</span></span>

```powershell
Get-Item -Path Env:* | Get-Member
```

<span data-ttu-id="1800a-201">O provedor de ambiente do PowerShell permite que você acesse variáveis de ambiente em uma unidade do PowerShell (a `Env:` unidade).</span><span class="sxs-lookup"><span data-stu-id="1800a-201">The PowerShell Environment provider lets you access environment variables in a PowerShell drive (the `Env:` drive).</span></span> <span data-ttu-id="1800a-202">Essa unidade é muito parecida com uma unidade do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="1800a-202">This drive looks much like a file system drive.</span></span> <span data-ttu-id="1800a-203">Para ir para a `Env:` unidade, digite:</span><span class="sxs-lookup"><span data-stu-id="1800a-203">To go to the `Env:` drive, type:</span></span>

```powershell
Set-Location Env:
```

<span data-ttu-id="1800a-204">Use os cmdlets de conteúdo para obter ou definir os valores de uma variável de ambiente.</span><span class="sxs-lookup"><span data-stu-id="1800a-204">Use the Content cmdlets to get or set the values of an environment variable.</span></span>

```powershell
PS Env:\> Set-Content -Path Test -Value 'Test value'
PS Env:\> Get-Content -Path Test
Test value
```

<span data-ttu-id="1800a-205">Você pode exibir as variáveis de ambiente na `Env:` unidade de qualquer outra unidade do PowerShell e pode entrar na `Env:` unidade para exibir e alterar as variáveis de ambiente.</span><span class="sxs-lookup"><span data-stu-id="1800a-205">You can view the environment variables in the `Env:` drive from any other PowerShell drive, and you can go into the `Env:` drive to view and change the environment variables.</span></span>

### <a name="using-item-cmdlets"></a><span data-ttu-id="1800a-206">Usando cmdlets de item</span><span class="sxs-lookup"><span data-stu-id="1800a-206">Using Item cmdlets</span></span>

<span data-ttu-id="1800a-207">Quando você se referir a uma variável de ambiente, digite o `Env:` nome da unidade seguido pelo nome da variável.</span><span class="sxs-lookup"><span data-stu-id="1800a-207">When you refer to an environment variable, type the `Env:` drive name followed by the name of the variable.</span></span> <span data-ttu-id="1800a-208">Por exemplo, para exibir o valor da `COMPUTERNAME` variável de ambiente, digite:</span><span class="sxs-lookup"><span data-stu-id="1800a-208">For example, to display the value of the `COMPUTERNAME` environment variable, type:</span></span>

```powershell
Get-ChildItem Env:Computername
```

<span data-ttu-id="1800a-209">Para exibir os valores de todas as variáveis de ambiente, digite:</span><span class="sxs-lookup"><span data-stu-id="1800a-209">To display the values of all the environment variables, type:</span></span>

```powershell
Get-ChildItem Env:
```

<span data-ttu-id="1800a-210">Como as variáveis de ambiente não têm itens filho, a saída de `Get-Item` e `Get-ChildItem` é a mesma.</span><span class="sxs-lookup"><span data-stu-id="1800a-210">Because environment variables do not have child items, the output of `Get-Item` and `Get-ChildItem` is the same.</span></span>

<span data-ttu-id="1800a-211">Por padrão, o PowerShell exibe as variáveis de ambiente na ordem em que as recupera.</span><span class="sxs-lookup"><span data-stu-id="1800a-211">By default, PowerShell displays the environment variables in the order in which it retrieves them.</span></span> <span data-ttu-id="1800a-212">Para classificar a lista de variáveis de ambiente por nome de variável, redirecione a saída de um `Get-ChildItem` comando para o `Sort-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1800a-212">To sort the list of environment variables by variable name, pipe the output of a `Get-ChildItem` command to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="1800a-213">Por exemplo, em qualquer unidade do PowerShell, digite:</span><span class="sxs-lookup"><span data-stu-id="1800a-213">For example, from any PowerShell drive, type:</span></span>

```powershell
Get-ChildItem Env: | Sort Name
```

<span data-ttu-id="1800a-214">Você também pode entrar na `Env:` unidade usando o `Set-Location` cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1800a-214">You can also go into the `Env:` drive by using the `Set-Location` cmdlet:</span></span>

```powershell
Set-Location Env:
```

<span data-ttu-id="1800a-215">Quando estiver na `Env:` unidade, você poderá omitir o `Env:` nome da unidade do caminho.</span><span class="sxs-lookup"><span data-stu-id="1800a-215">When you are in the `Env:` drive, you can omit the `Env:` drive name from the path.</span></span> <span data-ttu-id="1800a-216">Por exemplo, para exibir todas as variáveis de ambiente, digite:</span><span class="sxs-lookup"><span data-stu-id="1800a-216">For example, to display all the environment variables, type:</span></span>

```powershell
PS Env:\> Get-ChildItem
```

<span data-ttu-id="1800a-217">Para exibir o valor da `COMPUTERNAME` variável de dentro da `Env:` unidade, digite:</span><span class="sxs-lookup"><span data-stu-id="1800a-217">To display the value of the `COMPUTERNAME` variable from within the `Env:` drive, type:</span></span>

```powershell
PS Env:\> Get-ChildItem ComputerName
```

### <a name="saving-changes-to-environment-variables"></a><span data-ttu-id="1800a-218">Salvando alterações em variáveis de ambiente</span><span class="sxs-lookup"><span data-stu-id="1800a-218">Saving changes to environment variables</span></span>

<span data-ttu-id="1800a-219">Para fazer uma alteração persistente em uma variável de ambiente no Windows, use o painel de controle do sistema.</span><span class="sxs-lookup"><span data-stu-id="1800a-219">To make a persistent change to an environment variable on Windows, use the System Control Panel.</span></span> <span data-ttu-id="1800a-220">Selecione **Configurações avançadas do sistema**.</span><span class="sxs-lookup"><span data-stu-id="1800a-220">Select **Advanced System Settings**.</span></span> <span data-ttu-id="1800a-221">Na guia **avançado** , clique em **variável de ambiente...**. Você pode adicionar ou editar variáveis de ambiente existentes nos escopos de **usuário** e **sistema** (computador).</span><span class="sxs-lookup"><span data-stu-id="1800a-221">On the **Advanced** tab, click **Environment Variable...**. You can add or edit existing environment variables in the **User** and **System** (Machine) scopes.</span></span> <span data-ttu-id="1800a-222">O Windows grava esses valores no registro para que eles persistam entre as sessões e reinicializações do sistema.</span><span class="sxs-lookup"><span data-stu-id="1800a-222">Windows writes these values to the Registry so that they persist across sessions and system restarts.</span></span>

<span data-ttu-id="1800a-223">Como alternativa, você pode adicionar ou alterar variáveis de ambiente no seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1800a-223">Alternately, you can add or change environment variables in your PowerShell profile.</span></span> <span data-ttu-id="1800a-224">Esse método funciona para qualquer versão do PowerShell em qualquer plataforma com suporte.</span><span class="sxs-lookup"><span data-stu-id="1800a-224">This method works for any version of PowerShell on any supported platform.</span></span>

### <a name="using-systemenvironment-methods"></a><span data-ttu-id="1800a-225">Usando métodos System. Environment</span><span class="sxs-lookup"><span data-stu-id="1800a-225">Using System.Environment methods</span></span>

<span data-ttu-id="1800a-226">A classe **System. Environment** fornece os métodos **GetEnvironmentVariable** e **SetEnvironmentVariable não** que permitem especificar o escopo da variável.</span><span class="sxs-lookup"><span data-stu-id="1800a-226">The **System.Environment** class provides **GetEnvironmentVariable** and **SetEnvironmentVariable** methods that allow you to specify the scope of the variable.</span></span>

<span data-ttu-id="1800a-227">O exemplo a seguir usa o método **GetEnvironmentVariable** para obter a configuração do computador `PSModulePath` e o método **SetEnvironmentVariable não** para adicionar o `C:\Program Files\Fabrikam\Modules` caminho ao valor.</span><span class="sxs-lookup"><span data-stu-id="1800a-227">The following example uses the **GetEnvironmentVariable** method to get the machine setting of `PSModulePath` and the **SetEnvironmentVariable** method to add the `C:\Program Files\Fabrikam\Modules` path to the value.</span></span>

```powershell
$path = [Environment]::GetEnvironmentVariable('PSModulePath', 'Machine')
$newpath = $path + ';C:\Program Files\Fabrikam\Modules'
[Environment]::SetEnvironmentVariable("PSModulePath", $newpath, 'Machine')
```

<span data-ttu-id="1800a-228">Para obter mais informações sobre os métodos da classe **System. Environment** , consulte [métodos de ambiente](/dotnet/api/system.environment).</span><span class="sxs-lookup"><span data-stu-id="1800a-228">For more information about the methods of the **System.Environment** class, see [Environment Methods](/dotnet/api/system.environment).</span></span>

## <a name="see-also"></a><span data-ttu-id="1800a-229">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="1800a-229">SEE ALSO</span></span>

- [<span data-ttu-id="1800a-230">Ambiente (provedor)</span><span class="sxs-lookup"><span data-stu-id="1800a-230">Environment (provider)</span></span>](../About/about_Environment_Provider.md)
- [<span data-ttu-id="1800a-231">about_Modules</span><span class="sxs-lookup"><span data-stu-id="1800a-231">about_Modules</span></span>](about_Modules.md)

