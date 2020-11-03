---
description: Descreve a funcionalidade de compatibilidade do Windows PowerShell para o PowerShell 7.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_windows_powershell_compatibility?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_PowerShell_Compatibility
ms.openlocfilehash: 777dab1cce4329958337a7c0857b0d712b4387a9
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195929"
---
# <a name="about-windows-powershell-compatibility"></a><span data-ttu-id="0c8ae-104">Sobre a compatibilidade do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c8ae-104">About Windows PowerShell compatibility</span></span>

## <a name="short-description"></a><span data-ttu-id="0c8ae-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="0c8ae-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="0c8ae-106">Descreve a funcionalidade de compatibilidade do Windows PowerShell para o PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-106">Describes the Windows PowerShell Compatibility functionality for PowerShell 7.</span></span>

## <a name="long-description"></a><span data-ttu-id="0c8ae-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="0c8ae-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="0c8ae-108">A menos que o manifesto do módulo indique que o módulo é compatível com o PowerShell Core, os módulos na `%windir%\system32\WindowsPowerShell\v1.0\Modules` pasta são carregados em um processo em segundo plano do Windows powershell 5,1 pelo recurso de compatibilidade do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-108">Unless the module manifest indicates that module is compatible with PowerShell Core, modules in the `%windir%\system32\WindowsPowerShell\v1.0\Modules` folder are loaded in a background Windows PowerShell 5.1 process by Windows PowerShell Compatibility feature.</span></span>

### <a name="using-the-compatibility-feature"></a><span data-ttu-id="0c8ae-109">Usando o recurso de compatibilidade</span><span class="sxs-lookup"><span data-stu-id="0c8ae-109">Using the Compatibility feature</span></span>

<span data-ttu-id="0c8ae-110">Quando o primeiro módulo é importado usando o recurso de compatibilidade do Windows PowerShell, o PowerShell cria uma sessão remota chamada `WinPSCompatSession` que está sendo executada em um processo em segundo plano do Windows powershell 5,1.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-110">When the first module is imported using Windows PowerShell Compatibility feature, PowerShell creates a remote session named `WinPSCompatSession` that is running in a background Windows PowerShell 5.1 process.</span></span> <span data-ttu-id="0c8ae-111">Esse processo é criado quando o recurso de compatibilidade importa o primeiro módulo.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-111">This process is created when the Compatibility feature imports the first module.</span></span> <span data-ttu-id="0c8ae-112">O processo é fechado quando o último módulo é removido (usando `Remove-Module` ) ou quando o processo do PowerShell é encerrado.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-112">The process is closed when the last such module is removed (using `Remove-Module`) or when PowerShell process exits.</span></span>

<span data-ttu-id="0c8ae-113">Os módulos carregados na `WinPSCompatSession` sessão são usados por meio de comunicação remota implícita e refletidos na sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-113">The modules loaded in the `WinPSCompatSession` session are used via implicit remoting and reflected into current PowerShell session.</span></span> <span data-ttu-id="0c8ae-114">Esse é o mesmo método de transporte usado para trabalhos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-114">This is the same transport method used for PowerShell jobs.</span></span>

<span data-ttu-id="0c8ae-115">Quando um módulo é importado para a `WinPSCompatSession` sessão, a comunicação remota implícita gera um módulo de proxy no diretório do usuário `$env:Temp` e importa esse módulo de proxy para a sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-115">When a module is imported into the `WinPSCompatSession` session, implicit remoting generates a proxy module in the user's `$env:Temp` directory and imports this proxy module into current PowerShell session.</span></span> <span data-ttu-id="0c8ae-116">Isso permite que o PowerShell detecte que o módulo foi carregado usando a funcionalidade de compatibilidade do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-116">This allows PowerShell to detect that the module was loaded using Windows PowerShell Compatibility functionality.</span></span>

<span data-ttu-id="0c8ae-117">Depois que a sessão é criada, ela pode ser usada para operações que não funcionam corretamente em objetos desserializados.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-117">Once the session is created, it can be used for operations that don't work correctly on deserialized objects.</span></span> <span data-ttu-id="0c8ae-118">Todo o pipeline é executado no Windows PowerShell e apenas o resultado final é retornado.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-118">The entire pipeline is executed in Windows PowerShell and only the final result is returned.</span></span> <span data-ttu-id="0c8ae-119">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0c8ae-119">For example:</span></span>

```powershell
$s = Get-PSSession -Name WinPSCompatSession
Invoke-Command -Session $s -ScriptBlock {
  "Running in Windows PowerShell version $($PSVersionTable.PSVersion)"
}
```

<span data-ttu-id="0c8ae-120">O recurso de compatibilidade pode ser invocado de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="0c8ae-120">The Compatibility feature can be invoked in two ways:</span></span>

- <span data-ttu-id="0c8ae-121">Explicitamente importando um módulo usando o parâmetro **UseWindowsPowerShell**</span><span class="sxs-lookup"><span data-stu-id="0c8ae-121">Explicitly by importing a module using the **UseWindowsPowerShell** parameter</span></span>

   ```powershell
   Import-Module -Name ScheduledTasks -UseWindowsPowerShell
   ```

- <span data-ttu-id="0c8ae-122">Implicitamente, importando um módulo do Windows PowerShell por nome do módulo, caminho ou carregamento automático via descoberta de comando.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-122">Implicitly by importing a Windows PowerShell module by module name, path, or autoloading via command discovery.</span></span>

   ```powershell
   Import-Module -Name ServerManager
   Get-AppLockerPolicy -Local
   ```

   <span data-ttu-id="0c8ae-123">Se ainda não tiver sido carregado, o módulo do AppLocker será carregado com autocarga quando você executar  `Get-AppLockerPolicy` .</span><span class="sxs-lookup"><span data-stu-id="0c8ae-123">If not already loaded, the AppLocker module is autoloaded when you run  `Get-AppLockerPolicy`.</span></span>

<span data-ttu-id="0c8ae-124">A compatibilidade do Windows PowerShell bloqueia o carregamento de módulos listados na `WindowsPowerShellCompatibilityModuleDenyList` configuração no arquivo de configuração do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-124">Windows PowerShell Compatibility blocks loading of modules that are listed in the `WindowsPowerShellCompatibilityModuleDenyList` setting in PowerShell configuration file.</span></span>

<span data-ttu-id="0c8ae-125">O valor padrão dessa configuração é:</span><span class="sxs-lookup"><span data-stu-id="0c8ae-125">The default value of this setting is:</span></span>

```json
"WindowsPowerShellCompatibilityModuleDenyList":  [
   "PSScheduledJob","BestPractices","UpdateServices"
]
```

### <a name="managing-implicit-module-loading"></a><span data-ttu-id="0c8ae-126">Gerenciando o carregamento de módulo implícito</span><span class="sxs-lookup"><span data-stu-id="0c8ae-126">Managing implicit module loading</span></span>

<span data-ttu-id="0c8ae-127">Para desabilitar o comportamento de importação implícito do recurso de compatibilidade do Windows PowerShell, use a `DisableImplicitWinCompat` configuração em um arquivo de configuração do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-127">To disable implicit import behavior of the Windows PowerShell Compatibility feature, use the `DisableImplicitWinCompat` setting in a PowerShell configuration file.</span></span> <span data-ttu-id="0c8ae-128">Essa configuração pode ser adicionada ao `powershell.config.json` arquivo.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-128">This setting can be added to the `powershell.config.json` file.</span></span> <span data-ttu-id="0c8ae-129">Para obter mais informações, consulte [about_powershell_config](about_powershell_config.md).</span><span class="sxs-lookup"><span data-stu-id="0c8ae-129">For more information, see [about_powershell_config](about_powershell_config.md).</span></span>

<span data-ttu-id="0c8ae-130">Este exemplo mostra como criar um arquivo de configuração que desabilita o recurso de carregamento de módulo implícito da compatibilidade do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-130">This example shows how to create a configuration file that disables the implicit module-loading feature of Windows PowerShell Compatibility.</span></span>

```powershell
$ConfigPath = "$PSHOME\DisableWinCompat.powershell.config.json"
$ConfigJSON = ConvertTo-Json -InputObject @{
  "DisableImplicitWinCompat" = $true
  "Microsoft.PowerShell:ExecutionPolicy" = "RemoteSigned"
}
$ConfigJSON | Out-File -Force $ConfigPath
pwsh -settingsFile $ConfigPath
```

<span data-ttu-id="0c8ae-131">Para obter mais informações sobre a compatibilidade de módulo, consulte a lista de [compatibilidade de módulo do PowerShell 7](https://aka.ms/PSModuleCompat) .</span><span class="sxs-lookup"><span data-stu-id="0c8ae-131">For more the latest information about module compatibility, see the [PowerShell 7 module compatibility](https://aka.ms/PSModuleCompat) list.</span></span>

### <a name="managing-cmdlet-clobbering"></a><span data-ttu-id="0c8ae-132">Gerenciando cmdlet sobreporem</span><span class="sxs-lookup"><span data-stu-id="0c8ae-132">Managing cmdlet clobbering</span></span>

<span data-ttu-id="0c8ae-133">O recurso de compatibilidade do Windows PowerShell usa a comunicação remota implícita para carregar módulos no modo de compatibilidade.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-133">The Windows PowerShell Compatibility feature uses implicit remoting to load modules in compatibility mode.</span></span> <span data-ttu-id="0c8ae-134">O resultado é que os comandos exportados pelo módulo têm precedência sobre os comandos de mesmo nome na sessão atual do PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-134">The result is that commands exported by the module take precedence over commands of the same name in the current PowerShell 7 session.</span></span> <span data-ttu-id="0c8ae-135">Na versão 7.0.0 do PowerShell, isso incluiu os módulos principais fornecidos com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-135">In the PowerShell 7.0.0 release, this included the core modules that ship with PowerShell.</span></span>

<span data-ttu-id="0c8ae-136">No PowerShell 7,1, o comportamento foi alterado para que os seguintes módulos principais do PowerShell não sejam sobrescrito:</span><span class="sxs-lookup"><span data-stu-id="0c8ae-136">In PowerShell 7.1, the behavior was changed so that the following core PowerShell modules are not clobbered:</span></span>

- <span data-ttu-id="0c8ae-137">Microsoft. PowerShell. ConsoleHost</span><span class="sxs-lookup"><span data-stu-id="0c8ae-137">Microsoft.PowerShell.ConsoleHost</span></span>
- <span data-ttu-id="0c8ae-138">Microsoft.PowerShell.Diagnostics</span><span class="sxs-lookup"><span data-stu-id="0c8ae-138">Microsoft.PowerShell.Diagnostics</span></span>
- <span data-ttu-id="0c8ae-139">Microsoft.PowerShell.Host</span><span class="sxs-lookup"><span data-stu-id="0c8ae-139">Microsoft.PowerShell.Host</span></span>
- <span data-ttu-id="0c8ae-140">Microsoft.PowerShell.Management</span><span class="sxs-lookup"><span data-stu-id="0c8ae-140">Microsoft.PowerShell.Management</span></span>
- <span data-ttu-id="0c8ae-141">Microsoft.PowerShell.Security</span><span class="sxs-lookup"><span data-stu-id="0c8ae-141">Microsoft.PowerShell.Security</span></span>
- <span data-ttu-id="0c8ae-142">Microsoft.PowerShell.Utility</span><span class="sxs-lookup"><span data-stu-id="0c8ae-142">Microsoft.PowerShell.Utility</span></span>
- <span data-ttu-id="0c8ae-143">Microsoft.WSMan.Management</span><span class="sxs-lookup"><span data-stu-id="0c8ae-143">Microsoft.WSMan.Management</span></span>

<span data-ttu-id="0c8ae-144">O PowerShell 7,1 também adicionou a capacidade de listar módulos adicionais que não devem ser sobrescritodos pelo modo de compatibilidade.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-144">PowerShell 7.1 also added the ability to list additional modules that should not be clobbered by compatibility mode.</span></span>

<span data-ttu-id="0c8ae-145">Você pode adicionar a `WindowsPowerShellCompatibilityNoClobberModuleList` configuração ao arquivo de configuração do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-145">You can add the `WindowsPowerShellCompatibilityNoClobberModuleList` setting to PowerShell configuration file.</span></span> <span data-ttu-id="0c8ae-146">O valor dessa configuração é uma lista separada por vírgulas de nomes de módulo.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-146">The value of this setting is a comma-separated list of module names.</span></span> <span data-ttu-id="0c8ae-147">O valor padrão dessa configuração é:</span><span class="sxs-lookup"><span data-stu-id="0c8ae-147">The default value of this setting is:</span></span>

```json
"WindowsPowerShellCompatibilityNoClobberModuleList": [ ]
```

## <a name="limitations"></a><span data-ttu-id="0c8ae-148">Limitações</span><span class="sxs-lookup"><span data-stu-id="0c8ae-148">Limitations</span></span>

<span data-ttu-id="0c8ae-149">A funcionalidade de compatibilidade do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0c8ae-149">The Windows PowerShell Compatibility functionality:</span></span>

1. <span data-ttu-id="0c8ae-150">Funciona apenas localmente em computadores com Windows</span><span class="sxs-lookup"><span data-stu-id="0c8ae-150">Only works locally on Windows computers</span></span>
1. <span data-ttu-id="0c8ae-151">Requer que o Windows PowerShell 5,1</span><span class="sxs-lookup"><span data-stu-id="0c8ae-151">Requires that Windows PowerShell 5.1</span></span>
1. <span data-ttu-id="0c8ae-152">Opera em parâmetros de cmdlet serializados e valores de retorno, não em objetos dinâmicos</span><span class="sxs-lookup"><span data-stu-id="0c8ae-152">Operates on serialized cmdlet parameters and return values, not on live objects</span></span>
1. <span data-ttu-id="0c8ae-153">Todos os módulos importados para a sessão remota do Windows PowerShell compartilham o mesmo runspace.</span><span class="sxs-lookup"><span data-stu-id="0c8ae-153">All modules imported into the Windows PowerShell remoting session share the same runspace.</span></span>

## <a name="keywords"></a><span data-ttu-id="0c8ae-154">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="0c8ae-154">Keywords</span></span>

<span data-ttu-id="0c8ae-155">about_Windows_PowerShell_Compatibility</span><span class="sxs-lookup"><span data-stu-id="0c8ae-155">about_Windows_PowerShell_Compatibility</span></span>

## <a name="see-also"></a><span data-ttu-id="0c8ae-156">Confira também</span><span class="sxs-lookup"><span data-stu-id="0c8ae-156">See also</span></span>

[<span data-ttu-id="0c8ae-157">about_Modules</span><span class="sxs-lookup"><span data-stu-id="0c8ae-157">about_Modules</span></span>](about_Modules.md)

[<span data-ttu-id="0c8ae-158">Import-Module</span><span class="sxs-lookup"><span data-stu-id="0c8ae-158">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)
