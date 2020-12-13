---
ms.date: 09/13/2016
ms.topic: reference
title: Modificar o caminho de instalação PSModulePath
description: Modificar o caminho de instalação PSModulePath
ms.openlocfilehash: b802492bf9b49e8165e296817e3f80b9ae8265a6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92661952"
---
# <a name="modifying-the-psmodulepath-installation-path"></a><span data-ttu-id="040f8-103">Modificar o caminho de instalação PSModulePath</span><span class="sxs-lookup"><span data-stu-id="040f8-103">Modifying the PSModulePath Installation Path</span></span>

<span data-ttu-id="040f8-104">A `PSModulePath` variável de ambiente armazena os caminhos para os locais dos módulos que estão instalados no disco.</span><span class="sxs-lookup"><span data-stu-id="040f8-104">The `PSModulePath` environment variable stores the paths to the locations of the modules that are installed on disk.</span></span> <span data-ttu-id="040f8-105">O PowerShell usa essa variável para localizar módulos quando o usuário não especifica o caminho completo para um módulo.</span><span class="sxs-lookup"><span data-stu-id="040f8-105">PowerShell uses this variable to locate modules when the user does not specify the full path to a module.</span></span> <span data-ttu-id="040f8-106">Os caminhos nessa variável são pesquisados na ordem em que aparecem.</span><span class="sxs-lookup"><span data-stu-id="040f8-106">The paths in this variable are searched in the order in which they appear.</span></span>

<span data-ttu-id="040f8-107">Quando o PowerShell é iniciado, `PSModulePath` é criado como uma variável de ambiente do sistema com o seguinte valor padrão: `$HOME\Documents\PowerShell\Modules; $PSHOME\Modules` no Windows e `$HOME/.local/share/powershell/Modules: usr/local/share/powershell/Modules` no Linux ou Mac, e `$HOME\Documents\WindowsPowerShell\Modules; $PSHOME\Modules` para o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="040f8-107">When PowerShell starts, `PSModulePath` is created as a system environment variable with the following default value: `$HOME\Documents\PowerShell\Modules; $PSHOME\Modules` on Windows and `$HOME/.local/share/powershell/Modules: usr/local/share/powershell/Modules` on Linux or Mac, and `$HOME\Documents\WindowsPowerShell\Modules; $PSHOME\Modules` for Windows PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="040f8-108">O local **CurrentUser** específico do usuário é a `WindowsPowerShell\Modules` pasta localizada no local **documentos** em seu perfil de usuário.</span><span class="sxs-lookup"><span data-stu-id="040f8-108">The user-specific **CurrentUser** location is the `WindowsPowerShell\Modules` folder located in the **Documents** location in your user profile.</span></span> <span data-ttu-id="040f8-109">O caminho específico desse local varia de acordo com a versão do Windows e se você está usando o redirecionamento de pasta.</span><span class="sxs-lookup"><span data-stu-id="040f8-109">The specific path of that location varies by version of Windows and whether or not you are using folder redirection.</span></span> <span data-ttu-id="040f8-110">Por padrão, no Windows 10, esse local é `$HOME\Documents\WindowsPowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="040f8-110">By default, on Windows 10, that location is `$HOME\Documents\WindowsPowerShell\Modules`.</span></span>

## <a name="to-view-the-psmodulepath-variable"></a><span data-ttu-id="040f8-111">Para exibir a variável PSModulePath</span><span class="sxs-lookup"><span data-stu-id="040f8-111">To view the PSModulePath variable</span></span>

<span data-ttu-id="040f8-112">Para exibir os caminhos especificados na `PSModulePath` variável, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="040f8-112">To view the paths that are specified in the `PSModulePath` variable, type the following command:</span></span>

`$env:PSModulePath`

## <a name="to-add-locations-to-the-psmodulepath-variable"></a><span data-ttu-id="040f8-113">Para adicionar locais à variável PSModulePath</span><span class="sxs-lookup"><span data-stu-id="040f8-113">To add locations to the PSModulePath variable</span></span>

<span data-ttu-id="040f8-114">Para adicionar caminhos a essa variável, use um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="040f8-114">To add paths to this variable, use one of the following methods:</span></span>

- <span data-ttu-id="040f8-115">Para adicionar um valor temporário que está disponível somente para a sessão atual, execute o seguinte comando na linha de comando:</span><span class="sxs-lookup"><span data-stu-id="040f8-115">To add a temporary value that is available only for the current session, run the following command at the command line:</span></span>

  `$env:PSModulePath = $env:PSModulePath + "$([System.IO.Path]::PathSeparator)$MyModulePath"`

- <span data-ttu-id="040f8-116">Para adicionar um valor persistente que esteja disponível sempre que uma sessão for aberta, adicione o comando acima a um arquivo de perfil do PowerShell ( `$PROFILE` ) ></span><span class="sxs-lookup"><span data-stu-id="040f8-116">To add a persistent value that is available whenever a session is opened, add the above command to a PowerShell profile file (`$PROFILE`)></span></span>

  <span data-ttu-id="040f8-117">Para obter mais informações sobre perfis, consulte [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles).</span><span class="sxs-lookup"><span data-stu-id="040f8-117">For more information about profiles, see [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles).</span></span>

- <span data-ttu-id="040f8-118">Para adicionar uma variável persistente ao registro, crie uma nova variável de ambiente de usuário chamada `PSModulePath` usando o editor de variáveis de ambiente na caixa de diálogo **Propriedades do sistema** .</span><span class="sxs-lookup"><span data-stu-id="040f8-118">To add a persistent variable to the registry, create a new user environment variable called `PSModulePath` using the Environment Variables Editor in the **System Properties** dialog box.</span></span>

- <span data-ttu-id="040f8-119">Para adicionar uma variável persistente usando um script, use o método .NET [SetEnvironmentVariable não](/dotnet/api/system.environment.setenvironmentvariable) na classe [System. Environment](/dotnet/api/system.environment) .</span><span class="sxs-lookup"><span data-stu-id="040f8-119">To add a persistent variable by using a script, use the .Net method [SetEnvironmentVariable](/dotnet/api/system.environment.setenvironmentvariable) on the [System.Environment](/dotnet/api/system.environment) class.</span></span> <span data-ttu-id="040f8-120">Por exemplo, o script a seguir adiciona o `C:\Program Files\Fabrikam\Module` caminho para o valor da `PSModulePath` variável de ambiente para o computador.</span><span class="sxs-lookup"><span data-stu-id="040f8-120">For example, the following script adds the `C:\Program Files\Fabrikam\Module` path to the value of the `PSModulePath` environment variable for the computer.</span></span> <span data-ttu-id="040f8-121">Para adicionar o caminho à variável de `PSModulePath` ambiente do usuário, defina o destino como "usuário".</span><span class="sxs-lookup"><span data-stu-id="040f8-121">To add the path to the user `PSModulePath` environment variable, set the target to "User".</span></span>

  ```powershell
  $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine")
  [Environment]::SetEnvironmentVariable("PSModulePath", $CurrentValue + [System.IO.Path]::PathSeparator + "C:\Program Files\Fabrikam\Modules", "Machine")

  ```

## <a name="to-remove-locations-from-the-psmodulepath"></a><span data-ttu-id="040f8-122">Para remover locais do PSModulePath</span><span class="sxs-lookup"><span data-stu-id="040f8-122">To remove locations from the PSModulePath</span></span>

<span data-ttu-id="040f8-123">Você pode remover caminhos da variável usando métodos semelhantes: por exemplo, `$env:PSModulePath = $env:PSModulePath -replace "$([System.IO.Path]::PathSeparator)c:\\ModulePath"` removerá o caminho **c:\ModulePath** da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="040f8-123">You can remove paths from the variable using similar methods: for example, `$env:PSModulePath = $env:PSModulePath -replace "$([System.IO.Path]::PathSeparator)c:\\ModulePath"` will remove the **c:\ModulePath** path from the current session.</span></span>

## <a name="see-also"></a><span data-ttu-id="040f8-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="040f8-124">See Also</span></span>

[<span data-ttu-id="040f8-125">Escrever um módulo do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="040f8-125">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)

[<span data-ttu-id="040f8-126">about_Modules</span><span class="sxs-lookup"><span data-stu-id="040f8-126">about_Modules</span></span>](/powershell/module/microsoft.powershell.core/about/about_modules)
