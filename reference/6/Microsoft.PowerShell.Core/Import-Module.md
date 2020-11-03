---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/import-module?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Module
ms.openlocfilehash: 4be0e64f05f841f3cf3dfdd8b5f91fdcaa158965
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194432"
---
# <span data-ttu-id="43bd0-103">Import-Module</span><span class="sxs-lookup"><span data-stu-id="43bd0-103">Import-Module</span></span>

## <span data-ttu-id="43bd0-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="43bd0-104">SYNOPSIS</span></span>
<span data-ttu-id="43bd0-105">Adiciona módulos à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="43bd0-105">Adds modules to the current session.</span></span>

## <span data-ttu-id="43bd0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="43bd0-106">SYNTAX</span></span>

### <span data-ttu-id="43bd0-107">Nome (padrão)</span><span class="sxs-lookup"><span data-stu-id="43bd0-107">Name (Default)</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Name] <String[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-SkipEditionCheck]
 [-PassThru] [-AsCustomObject] [-MinimumVersion <Version>] [-MaximumVersion <String>]
 [-RequiredVersion <Version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>]  [<CommonParameters>]
```

### <span data-ttu-id="43bd0-108">PSSession</span><span class="sxs-lookup"><span data-stu-id="43bd0-108">PSSession</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Name] <String[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-SkipEditionCheck]
 [-PassThru] [-AsCustomObject] [-MinimumVersion <Version>] [-MaximumVersion <String>]
 [-RequiredVersion <Version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] -PSSession <PSSession>  [<CommonParameters>]
```

### <span data-ttu-id="43bd0-109">CimSession</span><span class="sxs-lookup"><span data-stu-id="43bd0-109">CimSession</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Name] <String[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-SkipEditionCheck]
 [-PassThru] [-AsCustomObject] [-MinimumVersion <Version>] [-MaximumVersion <String>]
 [-RequiredVersion <Version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] -CimSession <CimSession> [-CimResourceUri <Uri>] [-CimNamespace <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="43bd0-110">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="43bd0-110">FullyQualifiedName</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-FullyQualifiedName] <ModuleSpecification[]>
 [-Function <String[]>] [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force]
 [-SkipEditionCheck] [-PassThru] [-AsCustomObject] [-ArgumentList <Object[]>] [-DisableNameChecking]
 [-NoClobber] [-Scope <String>]  [<CommonParameters>]
```

### <span data-ttu-id="43bd0-111">FullyQualifiedNameAndPSSession</span><span class="sxs-lookup"><span data-stu-id="43bd0-111">FullyQualifiedNameAndPSSession</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-FullyQualifiedName] <ModuleSpecification[]>
 [-Function <String[]>] [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force]
 [-SkipEditionCheck] [-PassThru] [-AsCustomObject] [-ArgumentList <Object[]>] [-DisableNameChecking]
 [-NoClobber] [-Scope <String>] -PSSession <PSSession>  [<CommonParameters>]
```

### <span data-ttu-id="43bd0-112">Assembly</span><span class="sxs-lookup"><span data-stu-id="43bd0-112">Assembly</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Assembly] <Assembly[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-SkipEditionCheck]
 [-PassThru] [-AsCustomObject] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>]  [<CommonParameters>]
```

### <span data-ttu-id="43bd0-113">ModuleInfo</span><span class="sxs-lookup"><span data-stu-id="43bd0-113">ModuleInfo</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Function <String[]>] [-Cmdlet <String[]>]
 [-Variable <String[]>] [-Alias <String[]>] [-Force] [-SkipEditionCheck] [-PassThru]
 [-AsCustomObject] [-ModuleInfo] <PSModuleInfo[]> [-ArgumentList <Object[]>] [-DisableNameChecking]
 [-NoClobber] [-Scope <String>]  [<CommonParameters>]
```

## <span data-ttu-id="43bd0-114">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="43bd0-114">DESCRIPTION</span></span>

<span data-ttu-id="43bd0-115">O `Import-Module` cmdlet adiciona um ou mais módulos à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="43bd0-115">The `Import-Module` cmdlet adds one or more modules to the current session.</span></span> <span data-ttu-id="43bd0-116">A partir do PowerShell 3,0, os módulos instalados são automaticamente importados para a sessão quando você usa qualquer comando ou provedor no módulo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-116">Starting in PowerShell 3.0, installed modules are automatically imported to the session when you use any commands or providers in the module.</span></span> <span data-ttu-id="43bd0-117">No entanto, você ainda pode usar o `Import-Module` comando para importar um módulo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-117">However, you can still use the `Import-Module` command to import a module.</span></span>
<span data-ttu-id="43bd0-118">Você pode desabilitar a importação automática de módulos usando a `$PSModuleAutoloadingPreference` variável de preferência.</span><span class="sxs-lookup"><span data-stu-id="43bd0-118">You can disable automatic module importing using the `$PSModuleAutoloadingPreference` preference variable.</span></span> <span data-ttu-id="43bd0-119">Para obter mais informações sobre a `$PSModuleAutoloadingPreference` variável, consulte [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="43bd0-119">For more information about the `$PSModuleAutoloadingPreference` variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="43bd0-120">Um módulo é um pacote que contém membros que podem ser usados no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43bd0-120">A module is a package that contains members that can be used in PowerShell.</span></span> <span data-ttu-id="43bd0-121">Os membros incluem cmdlets, provedores, scripts, funções, variáveis e outras ferramentas e arquivos.</span><span class="sxs-lookup"><span data-stu-id="43bd0-121">Members include cmdlets, providers, scripts, functions, variables, and other tools and files.</span></span> <span data-ttu-id="43bd0-122">Após um módulo ser importado, você pode usar os membros do módulo em sua sessão.</span><span class="sxs-lookup"><span data-stu-id="43bd0-122">After a module is imported, you can use the module members in your session.</span></span> <span data-ttu-id="43bd0-123">Para obter mais informações sobre módulos, consulte [about_Modules](About/about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="43bd0-123">For more information about modules, see [about_Modules](About/about_Modules.md).</span></span>

<span data-ttu-id="43bd0-124">Por padrão, `Import-Module` o importa todos os membros que o módulo exporta, mas você pode usar os parâmetros **alias** , **função** , **cmdlet** e **variável** para restringir quais membros são importados.</span><span class="sxs-lookup"><span data-stu-id="43bd0-124">By default, `Import-Module` imports all members that the module exports, but you can use the **Alias** , **Function** , **Cmdlet** , and **Variable** parameters to restrict which members are imported.</span></span> <span data-ttu-id="43bd0-125">O parâmetro **NoClobber** impede a `Import-Module` importação de membros que têm os mesmos nomes que os membros na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="43bd0-125">The **NoClobber** parameter prevents `Import-Module` from importing members that have the same names as members in the current session.</span></span>

<span data-ttu-id="43bd0-126">`Import-Module` importa um módulo somente para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="43bd0-126">`Import-Module` imports a module only into the current session.</span></span> <span data-ttu-id="43bd0-127">Para importar o módulo para cada nova sessão, adicione um `Import-Module` comando ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43bd0-127">To import the module into every new session, add an `Import-Module` command to your PowerShell profile.</span></span> <span data-ttu-id="43bd0-128">Para obter mais informações sobre perfis, consulte [about_Profiles](About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="43bd0-128">For more information about profiles, see [about_Profiles](About/about_Profiles.md).</span></span>

<span data-ttu-id="43bd0-129">Você pode gerenciar computadores remotos com Windows que têm a comunicação remota do PowerShell habilitada criando uma **PSSession** no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43bd0-129">You can manage remote Windows computers that have PowerShell remoting enabled by creating a **PSSession** on the remote computer.</span></span> <span data-ttu-id="43bd0-130">Em seguida, use o parâmetro **PSSession** do `Import-Module` para importar os módulos que estão instalados no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43bd0-130">Then use the **PSSession** parameter of `Import-Module` to import the modules that are installed on the remote computer.</span></span> <span data-ttu-id="43bd0-131">Agora você pode usar os comandos importados na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="43bd0-131">You can now use the imported commands in the current session.</span></span> <span data-ttu-id="43bd0-132">Os comandos são executados implicitamente no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43bd0-132">The commands implicitly run on the remote computer.</span></span>

<span data-ttu-id="43bd0-133">A partir do Windows PowerShell 3,0, você pode usar `Import-Module` para importar módulos de modelo CIM (CIM), nos quais os cmdlets são definidos em arquivos de definição de cmdlet (CDXML).</span><span class="sxs-lookup"><span data-stu-id="43bd0-133">Starting in Windows PowerShell 3.0, you can use `Import-Module` to import Common Information Model (CIM) modules, in which the cmdlets are defined in Cmdlet Definition XML (CDXML) files.</span></span> <span data-ttu-id="43bd0-134">Este recurso permite que você use cmdlets que são implementados em assemblies de código não gerenciado, como aqueles escritos em C++.</span><span class="sxs-lookup"><span data-stu-id="43bd0-134">This feature allows you to use cmdlets that are implemented in non-managed code assemblies, such as those written in C++.</span></span>

<span data-ttu-id="43bd0-135">Para computadores remotos que não têm a comunicação remota do PowerShell habilitada, incluindo computadores que não estão executando o sistema operacional Windows, você pode usar o parâmetro **CIMSession** do `Import-Module` para importar módulos CIM do computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43bd0-135">For remote computers that don't have PowerShell remoting enabled, including computers that aren't running the Windows operating system, you can use the **CIMSession** parameter of `Import-Module` to import CIM modules from the remote computer.</span></span> <span data-ttu-id="43bd0-136">Os comandos importados são executados implicitamente no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43bd0-136">The imported commands run implicitly on the remote computer.</span></span> <span data-ttu-id="43bd0-137">Um **CIMSession** é uma conexão com instrumentação de gerenciamento do Windows (WMI) no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43bd0-137">A **CIMSession** is a connection to Windows Management Instrumentation (WMI) on the remote computer.</span></span>

## <span data-ttu-id="43bd0-138">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="43bd0-138">EXAMPLES</span></span>

### <span data-ttu-id="43bd0-139">Exemplo 1: importar os membros de um módulo para a sessão atual</span><span class="sxs-lookup"><span data-stu-id="43bd0-139">Example 1: Import the members of a module into the current session</span></span>

<span data-ttu-id="43bd0-140">Este exemplo importa os membros do módulo **PSDiagnostics** para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="43bd0-140">This example imports the members of the **PSDiagnostics** module into the current session.</span></span>

```powershell
Import-Module -Name PSDiagnostics
```

### <span data-ttu-id="43bd0-141">Exemplo 2: importar todos os módulos especificados pelo caminho do módulo</span><span class="sxs-lookup"><span data-stu-id="43bd0-141">Example 2: Import all modules specified by the module path</span></span>

<span data-ttu-id="43bd0-142">Este exemplo importa todos os módulos disponíveis no caminho especificado pela `$env:PSModulePath` variável de ambiente para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="43bd0-142">This example imports all available modules in the path specified by the `$env:PSModulePath` environment variable into the current session.</span></span>

```powershell
Get-Module -ListAvailable | Import-Module
```

### <span data-ttu-id="43bd0-143">Exemplo 3: importar os membros de vários módulos para a sessão atual</span><span class="sxs-lookup"><span data-stu-id="43bd0-143">Example 3: Import the members of several modules into the current session</span></span>

<span data-ttu-id="43bd0-144">Este exemplo importa os membros dos módulos **PSDiagnostics** e **DISM** para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="43bd0-144">This example imports the members of the **PSDiagnostics** and **Dism** modules into the current session.</span></span>

```powershell
$m = Get-Module -ListAvailable PSDiagnostics, Dism
Import-Module -ModuleInfo $m
```

<span data-ttu-id="43bd0-145">O `Get-Module` cmdlet obtém os módulos **PSDiagnostics** e **DISM** e salva os objetos na `$m` variável.</span><span class="sxs-lookup"><span data-stu-id="43bd0-145">The `Get-Module` cmdlet gets the **PSDiagnostics** and **Dism** modules and saves the objects in the `$m` variable.</span></span> <span data-ttu-id="43bd0-146">O parâmetro **listAvailable** é necessário quando você está obtendo módulos que ainda não foram importados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="43bd0-146">The **ListAvailable** parameter is required when you're getting modules that aren't yet imported into the session.</span></span>

<span data-ttu-id="43bd0-147">O parâmetro **ModuleInfo** de `Import-Module` é usado para importar os módulos para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="43bd0-147">The **ModuleInfo** parameter of `Import-Module` is used to import the modules into the current session.</span></span>

### <span data-ttu-id="43bd0-148">Exemplo 4: importar todos os módulos especificados por um caminho</span><span class="sxs-lookup"><span data-stu-id="43bd0-148">Example 4: Import all modules specified by a path</span></span>

<span data-ttu-id="43bd0-149">Este exemplo usa um caminho explícito para identificar o módulo a ser importado.</span><span class="sxs-lookup"><span data-stu-id="43bd0-149">This example uses an explicit path to identify the module to import.</span></span>

```powershell
Import-Module -Name c:\ps-test\modules\test -Verbose
```

```Output
VERBOSE: Loading module from path 'C:\ps-test\modules\Test\Test.psm1'.
VERBOSE: Exporting function 'my-parm'.
VERBOSE: Exporting function 'Get-Parameter'.
VERBOSE: Exporting function 'Get-Specification'.
VERBOSE: Exporting function 'Get-SpecDetails'.
```

<span data-ttu-id="43bd0-150">O uso do parâmetro **Verbose** faz com que o `Import-Module` relate o progresso à medida que ele carrega o módulo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-150">Using the **Verbose** parameter causes `Import-Module` to report progress as it loads the module.</span></span>
<span data-ttu-id="43bd0-151">Sem o parâmetro **Verbose** , **PassThru** ou **AsCustomObject** , o não `Import-Module` gera nenhuma saída quando importa um módulo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-151">Without the **Verbose** , **PassThru** , or **AsCustomObject** parameter, `Import-Module` does not generate any output when it imports a module.</span></span>

### <span data-ttu-id="43bd0-152">Exemplo 5: restringir os membros do módulo importados em uma sessão</span><span class="sxs-lookup"><span data-stu-id="43bd0-152">Example 5: Restrict module members imported into a session</span></span>

<span data-ttu-id="43bd0-153">Este exemplo mostra como restringir quais membros de módulo são importados para a sessão e o efeito desse comando na sessão.</span><span class="sxs-lookup"><span data-stu-id="43bd0-153">This example shows how to restrict which module members are imported into the session and the effect of this command on the session.</span></span> <span data-ttu-id="43bd0-154">O parâmetro de **função** limita os membros que são importados do módulo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-154">The **Function** parameter limits the members that are imported from the module.</span></span> <span data-ttu-id="43bd0-155">Você também pode usar os parâmetros **alias** , **variável** e **cmdlet** para restringir outros membros que um módulo importa.</span><span class="sxs-lookup"><span data-stu-id="43bd0-155">You can also use the **Alias** , **Variable** , and **Cmdlet** parameters to restrict other members that a module imports.</span></span>

<span data-ttu-id="43bd0-156">O `Get-Module` cmdlet obtém o objeto que representa o módulo **PSDiagnostics** .</span><span class="sxs-lookup"><span data-stu-id="43bd0-156">The `Get-Module` cmdlet gets the object that represents the **PSDiagnostics** module.</span></span> <span data-ttu-id="43bd0-157">A propriedade **ExportedCmdlets** lista todos os cmdlets exportados pelo módulo, mesmo que eles não tenham sido importados.</span><span class="sxs-lookup"><span data-stu-id="43bd0-157">The **ExportedCmdlets** property lists all the cmdlets that the module exports, even though they were not all imported.</span></span>

```powershell
Import-Module PSDiagnostics -Function Disable-PSTrace, Enable-PSTrace
(Get-Module PSDiagnostics).ExportedCommands
```

```Output
Key                          Value
---                          -----
Disable-PSTrace              Disable-PSTrace
Disable-PSWSManCombinedTrace Disable-PSWSManCombinedTrace
Disable-WSManTrace           Disable-WSManTrace
Enable-PSTrace               Enable-PSTrace
Enable-PSWSManCombinedTrace  Enable-PSWSManCombinedTrace
Enable-WSManTrace            Enable-WSManTrace
Get-LogProperties            Get-LogProperties
Set-LogProperties            Set-LogProperties
Start-Trace                  Start-Trace
Stop-Trace                   Stop-Trace
```

```powershell
Get-Command -Module PSDiagnostics
```

```Output
CommandType     Name                 Version    Source
-----------     ----                 -------    ------
Function        Disable-PSTrace      6.1.0.0    PSDiagnostics
Function        Enable-PSTrace       6.1.0.0    PSDiagnostics
```

<span data-ttu-id="43bd0-158">O uso do parâmetro **Module** do `Get-Command` cmdlet mostra os comandos que foram importados do módulo **PSDiagnostics** .</span><span class="sxs-lookup"><span data-stu-id="43bd0-158">Using the **Module** parameter of the `Get-Command` cmdlet shows the commands that were imported from the **PSDiagnostics** module.</span></span> <span data-ttu-id="43bd0-159">Os resultados confirmam que apenas os `Disable-PSTrace` `Enable-PSTrace` cmdlets e foram importados.</span><span class="sxs-lookup"><span data-stu-id="43bd0-159">The results confirm that only the `Disable-PSTrace` and `Enable-PSTrace` cmdlets were imported.</span></span>

### <span data-ttu-id="43bd0-160">Exemplo 6: importar os membros de um módulo e adicionar um prefixo</span><span class="sxs-lookup"><span data-stu-id="43bd0-160">Example 6: Import the members of a module and add a prefix</span></span>

<span data-ttu-id="43bd0-161">Este exemplo importa o módulo **PSDiagnostics** para a sessão atual, adiciona um prefixo aos nomes de membro e, em seguida, exibe os nomes de membro prefixados.</span><span class="sxs-lookup"><span data-stu-id="43bd0-161">This example imports the **PSDiagnostics** module into the current session, adds a prefix to the member names, and then displays the prefixed member names.</span></span> <span data-ttu-id="43bd0-162">O parâmetro **prefix** de `Import-Module` adiciona o prefixo **x** a todos os membros que são importados do módulo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-162">The **Prefix** parameter of `Import-Module` adds the **x** prefix to all members that are imported from the module.</span></span> <span data-ttu-id="43bd0-163">O prefixo se aplica somente aos membros da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="43bd0-163">The prefix applies only to the members in the current session.</span></span> <span data-ttu-id="43bd0-164">Ele não altera o módulo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-164">It does not change the module.</span></span> <span data-ttu-id="43bd0-165">O parâmetro **PassThru** retorna um objeto de módulo que representa o módulo importado.</span><span class="sxs-lookup"><span data-stu-id="43bd0-165">The **PassThru** parameter returns a module object that represents the imported module.</span></span>

```powershell
Import-Module PSDiagnostics -Prefix x -PassThru
```

```Output
ModuleType Version    Name               ExportedCommands
---------- -------    ----               ----------------
Script     6.1.0.0    PSDiagnostics      {Disable-xPSTrace, Disable-xPSWSManCombinedTrace, Disable-xW...
```

```powershell
Get-Command -Module PSDiagnostics
```

```Output
CommandType     Name                                   Version    Source
-----------     ----                                   -------    ------
Function        Disable-xPSTrace                       6.1.0.0    PSDiagnostics
Function        Disable-xPSWSManCombinedTrace          6.1.0.0    PSDiagnostics
Function        Disable-xWSManTrace                    6.1.0.0    PSDiagnostics
Function        Enable-xPSTrace                        6.1.0.0    PSDiagnostics
Function        Enable-xPSWSManCombinedTrace           6.1.0.0    PSDiagnostics
Function        Enable-xWSManTrace                     6.1.0.0    PSDiagnostics
Function        Get-xLogProperties                     6.1.0.0    PSDiagnostics
Function        Set-xLogProperties                     6.1.0.0    PSDiagnostics
Function        Start-xTrace                           6.1.0.0    PSDiagnostics
Function        Stop-xTrace                            6.1.0.0    PSDiagnostics
```

<span data-ttu-id="43bd0-166">`Get-Command` Obtém os membros que foram importados do módulo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-166">`Get-Command` gets the members that have been imported from the module.</span></span> <span data-ttu-id="43bd0-167">A saída mostra que os membros do módulo foram prefixados corretamente.</span><span class="sxs-lookup"><span data-stu-id="43bd0-167">The output shows that the module members were correctly prefixed.</span></span>

### <span data-ttu-id="43bd0-168">Exemplo 7: obter e usar um objeto personalizado</span><span class="sxs-lookup"><span data-stu-id="43bd0-168">Example 7: Get and use a custom object</span></span>

<span data-ttu-id="43bd0-169">Este exemplo demonstra como obter e usar o objeto personalizado retornado por **Import-Module** .</span><span class="sxs-lookup"><span data-stu-id="43bd0-169">This example demonstrates how to get and use the custom object returned by **Import-Module** .</span></span>

<span data-ttu-id="43bd0-170">Objetos personalizados incluem membros sintéticos que representam cada um dos membros de módulos importados.</span><span class="sxs-lookup"><span data-stu-id="43bd0-170">Custom objects include synthetic members that represent each of the imported module members.</span></span> <span data-ttu-id="43bd0-171">Por exemplo, os cmdlets e funções em um módulo são convertidos para os métodos de script do objeto personalizado.</span><span class="sxs-lookup"><span data-stu-id="43bd0-171">For example, the cmdlets and functions in a module are converted to script methods of the custom object.</span></span>

<span data-ttu-id="43bd0-172">Os objetos personalizados são úteis no script.</span><span class="sxs-lookup"><span data-stu-id="43bd0-172">Custom objects are useful in scripting.</span></span> <span data-ttu-id="43bd0-173">Eles também são úteis quando vários objetos importados têm os mesmos nomes.</span><span class="sxs-lookup"><span data-stu-id="43bd0-173">They are also useful when several imported objects have the same names.</span></span> <span data-ttu-id="43bd0-174">Usar o método de script de um objeto é equivalente a especificar o nome totalmente qualificado de um membro importado, incluindo o nome de seu módulo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-174">Using the script method of an object is equivalent to specifying the fully qualified name of an imported member, including its module name.</span></span>

<span data-ttu-id="43bd0-175">O parâmetro **AsCustomObject** pode ser usado somente ao importar um módulo de script.</span><span class="sxs-lookup"><span data-stu-id="43bd0-175">The **AsCustomObject** parameter can be used only when importing a script module.</span></span> <span data-ttu-id="43bd0-176">Use `Get-Module` para determinar qual dos módulos disponíveis é um módulo de script.</span><span class="sxs-lookup"><span data-stu-id="43bd0-176">Use `Get-Module` to determine which of the available modules is a script module.</span></span>

```powershell
Get-Module -List | Format-Table -Property Name, ModuleType -AutoSize
```

```Output
Name          ModuleType
----          ----------
Show-Calendar     Script
BitsTransfer    Manifest
PSDiagnostics   Manifest
TestCmdlets       Script
...
```

```powershell
$a = Import-Module -Name Show-Calendar -AsCustomObject -Passthru
$a | Get-Member
```

```Output
    TypeName: System.Management.Automation.PSCustomObject
Name          MemberType   Definition
----          ----------   ----------
Equals        Method       bool Equals(System.Object obj)
GetHashCode   Method       int GetHashCode()
GetType       Method       type GetType()
ToString      Method       string ToString()
Show-Calendar ScriptMethod System.Object Show-Calendar();
```

```powershell
$a."Show-Calendar"()
```

<span data-ttu-id="43bd0-177">O módulo de script **show-Calendar** é importado usando o parâmetro **AsCustomObject** para solicitar um objeto personalizado e o parâmetro **PassThru** para retornar o objeto.</span><span class="sxs-lookup"><span data-stu-id="43bd0-177">The **Show-Calendar** script module is imported using the **AsCustomObject** parameter to request a custom object and the **PassThru** parameter to return the object.</span></span> <span data-ttu-id="43bd0-178">O objeto personalizado resultante é salvo na `$a` variável.</span><span class="sxs-lookup"><span data-stu-id="43bd0-178">The resulting custom object is saved in the `$a` variable.</span></span>

<span data-ttu-id="43bd0-179">A `$a` variável é canalizada para o `Get-Member` cmdlet para mostrar as propriedades e os métodos do objeto salvo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-179">The `$a` variable is piped to the `Get-Member` cmdlet to show the properties and methods of the saved object.</span></span> <span data-ttu-id="43bd0-180">A saída mostra um método de script **show-Calendar** .</span><span class="sxs-lookup"><span data-stu-id="43bd0-180">The output shows a **Show-Calendar** script method.</span></span>

<span data-ttu-id="43bd0-181">Para chamar o método de script **show-Calendar** , o nome do método deve ser colocado entre aspas porque o nome inclui um hífen.</span><span class="sxs-lookup"><span data-stu-id="43bd0-181">To call the **Show-Calendar** script method, the method name must be enclosed in quotation marks because the name includes a hyphen.</span></span>

### <span data-ttu-id="43bd0-182">Exemplo 8: reimportar um módulo para a mesma sessão</span><span class="sxs-lookup"><span data-stu-id="43bd0-182">Example 8: Reimport a module into the same session</span></span>

<span data-ttu-id="43bd0-183">Este exemplo mostra como usar o parâmetro **Force** de `Import-Module` quando você está importando um módulo para a mesma sessão.</span><span class="sxs-lookup"><span data-stu-id="43bd0-183">This example shows how to use the **Force** parameter of `Import-Module` when you're reimporting a module into the same session.</span></span> <span data-ttu-id="43bd0-184">O parâmetro **Force** remove o módulo carregado e o importa novamente.</span><span class="sxs-lookup"><span data-stu-id="43bd0-184">The **Force** parameter removes the loaded module and then imports it again.</span></span>

```powershell
Import-Module PSDiagnostics
Import-Module PSDiagnostics -Force -Prefix PS
```

<span data-ttu-id="43bd0-185">O primeiro comando importa o módulo **PSDiagnostics** .</span><span class="sxs-lookup"><span data-stu-id="43bd0-185">The first command imports the **PSDiagnostics** module.</span></span> <span data-ttu-id="43bd0-186">O segundo comando importa o módulo novamente, dessa vez usando o parâmetro **Prefix** .</span><span class="sxs-lookup"><span data-stu-id="43bd0-186">The second command imports the module again, this time using the **Prefix** parameter.</span></span>

<span data-ttu-id="43bd0-187">Sem o parâmetro **Force** , a sessão incluiria duas cópias de cada cmdlet **PSDiagnostics** , uma com o nome padrão e outra com o nome prefixado.</span><span class="sxs-lookup"><span data-stu-id="43bd0-187">Without the **Force** parameter, the session would include two copies of each **PSDiagnostics** cmdlet, one with the standard name and one with the prefixed name.</span></span>

### <span data-ttu-id="43bd0-188">Exemplo 9: executar comandos que foram ocultados por comandos importados</span><span class="sxs-lookup"><span data-stu-id="43bd0-188">Example 9: Run commands that have been hidden by imported commands</span></span>

<span data-ttu-id="43bd0-189">Este exemplo mostra como executar comandos que foram ocultos por comandos importados.</span><span class="sxs-lookup"><span data-stu-id="43bd0-189">This example shows how to run commands that have been hidden by imported commands.</span></span> <span data-ttu-id="43bd0-190">O módulo **TestModule** inclui uma função chamada `Get-Date` que retorna o ano e o dia do ano.</span><span class="sxs-lookup"><span data-stu-id="43bd0-190">The **TestModule** module includes a function named `Get-Date` that returns the year and day of the year.</span></span>

```powershell
Get-Date
```

```Output
Thursday, August 15, 2019 2:26:12 PM
```

```powershell
Import-Module TestModule
Get-Date
```

```Output
19227
```

```powershell
Get-Command Get-Date -All | Format-Table -Property CommandType, Name, ModuleName -AutoSize
```

```Output
CommandType     Name         ModuleName
-----------     ----         ----------
Function        Get-Date     TestModule
Cmdlet          Get-Date     Microsoft.PowerShell.Utility
```

```powershell
Microsoft.PowerShell.Utility\Get-Date
```

```Output
Thursday, August 15, 2019 2:28:31 PM
```

<span data-ttu-id="43bd0-191">O primeiro `Get-Date` cmdlet retorna um objeto **DateTime** com a data atual.</span><span class="sxs-lookup"><span data-stu-id="43bd0-191">The first `Get-Date` cmdlet returns a **DateTime** object with the current date.</span></span> <span data-ttu-id="43bd0-192">Depois de importar o módulo **TestModule** , `Get-Date` retorna o ano e o dia do ano.</span><span class="sxs-lookup"><span data-stu-id="43bd0-192">After importing the **TestModule** module, `Get-Date` returns the year and day of the year.</span></span>

<span data-ttu-id="43bd0-193">Usando o parâmetro **All** de `Get-Command` Mostrar todos os `Get-Date` comandos na sessão.</span><span class="sxs-lookup"><span data-stu-id="43bd0-193">Using the **All** parameter of `Get-Command` show all the `Get-Date` commands in the session.</span></span> <span data-ttu-id="43bd0-194">Os resultados mostram que há dois `Get-Date` comandos na sessão, uma função do módulo **TestModule** e um cmdlet do módulo **Microsoft. PowerShell. Utility** .</span><span class="sxs-lookup"><span data-stu-id="43bd0-194">The results show that there are two `Get-Date` commands in the session, a function from the **TestModule** module and a cmdlet from the **Microsoft.PowerShell.Utility** module.</span></span>

<span data-ttu-id="43bd0-195">Como as funções têm precedência sobre os cmdlets, a `Get-Date` função do módulo **TestModule** é executada, em vez do `Get-Date` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="43bd0-195">Because functions take precedence over cmdlets, the `Get-Date` function from the **TestModule** module runs, instead of the `Get-Date` cmdlet.</span></span> <span data-ttu-id="43bd0-196">Para executar a versão original do `Get-Date` , você deve qualificar o nome do comando com o nome do módulo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-196">To run the original version of `Get-Date`, you must qualify the command name with the module name.</span></span>

<span data-ttu-id="43bd0-197">Para obter mais informações sobre a precedência de comando no PowerShell, consulte [about_Command_Precedence](about/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="43bd0-197">For more information about command precedence in PowerShell, see [about_Command_Precedence](about/about_Command_Precedence.md).</span></span>

### <span data-ttu-id="43bd0-198">Exemplo 10: importar uma versão mínima de um módulo</span><span class="sxs-lookup"><span data-stu-id="43bd0-198">Example 10: Import a minimum version of a module</span></span>

<span data-ttu-id="43bd0-199">Este exemplo importa o módulo **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="43bd0-199">This example imports the **PowerShellGet** module.</span></span> <span data-ttu-id="43bd0-200">Ele usa o parâmetro **MinimumVersion** de `Import-Module` para importar somente a versão 2.0.0 ou superior do módulo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-200">It uses the **MinimumVersion** parameter of `Import-Module` to import only version 2.0.0 or greater of the module.</span></span>

```powershell
Import-Module -Name PowerShellGet -MinimumVersion 2.0.0
```

<span data-ttu-id="43bd0-201">Você também pode usar o parâmetro **RequiredVersion** para importar uma versão específica de um módulo ou usar os parâmetros de **módulo** e **versão** da `#Requires` palavra-chave para exigir uma versão específica de um módulo em um script.</span><span class="sxs-lookup"><span data-stu-id="43bd0-201">You can also use the **RequiredVersion** parameter to import a particular version of a module, or use the **Module** and **Version** parameters of the `#Requires` keyword to require a particular version of a module in a script.</span></span>

### <span data-ttu-id="43bd0-202">Exemplo 11: importar usando um nome totalmente qualificado</span><span class="sxs-lookup"><span data-stu-id="43bd0-202">Example 11: Import using a fully qualified name</span></span>

<span data-ttu-id="43bd0-203">Este exemplo importa uma versão específica de um módulo usando o FullyQualifiedName.</span><span class="sxs-lookup"><span data-stu-id="43bd0-203">This example imports a specific version of a module using the FullyQualifiedName.</span></span>

```powershell
PS> Get-Module -ListAvailable PowerShellGet | Select-Object Name, Version

Name          Version
----          -------
PowerShellGet 2.2.1
PowerShellGet 2.1.3
PowerShellGet 2.1.2
PowerShellGet 1.0.0.1

PS> Import-Module -FullyQualifiedName @{ModuleName = 'PowerShellGet'; ModuleVersion = '2.1.3' }
```

### <span data-ttu-id="43bd0-204">Exemplo 12: importar usando um caminho totalmente qualificado</span><span class="sxs-lookup"><span data-stu-id="43bd0-204">Example 12: Import using a fully qualified path</span></span>

<span data-ttu-id="43bd0-205">Este exemplo importa uma versão específica de um módulo usando o caminho totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="43bd0-205">This example imports a specific version of a module using the fully qualified path.</span></span>

```powershell
PS> Get-Module -ListAvailable PowerShellGet | Select-Object Path

Path
----
C:\Program Files\PowerShell\Modules\PowerShellGet\2.2.1\PowerShellGet.psd1
C:\program files\powershell\6\Modules\PowerShellGet\PowerShellGet.psd1
C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\2.1.2\PowerShellGet.psd1
C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PowerShellGet.psd1

PS> Import-Module -Name 'C:\Program Files\PowerShell\Modules\PowerShellGet\2.2.1\PowerShellGet.psd1'
```

### <span data-ttu-id="43bd0-206">Exemplo 13: importar um módulo de um computador remoto</span><span class="sxs-lookup"><span data-stu-id="43bd0-206">Example 13: Import a module from a remote computer</span></span>

<span data-ttu-id="43bd0-207">Este exemplo mostra como usar o `Import-Module` cmdlet para importar um módulo de um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43bd0-207">This example shows how to use the `Import-Module` cmdlet to import a module from a remote computer.</span></span>
<span data-ttu-id="43bd0-208">Esse comando usa o recurso de comunicação remota implícita do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43bd0-208">This command uses the Implicit Remoting feature of PowerShell.</span></span>

<span data-ttu-id="43bd0-209">Quando importa módulos de outra sessão, você pode usar os cmdlets da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="43bd0-209">When you import modules from another session, you can use the cmdlets in the current session.</span></span>
<span data-ttu-id="43bd0-210">No entanto, os comandos que usam os cmdlets são executados na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="43bd0-210">However, commands that use the cmdlets run in the remote session.</span></span>

```powershell
$s = New-PSSession -ComputerName Server01
Get-Module -PSSession $s -ListAvailable -Name NetSecurity
```

```Output
ModuleType Name             ExportedCommands
---------- ----             ----------------
Manifest   NetSecurity      {New-NetIPsecAuthProposal, New-NetIPsecMainModeCryptoProposal, New-Ne...
```

```powershell
Import-Module -PSSession $s -Name NetSecurity
Get-Command -Module NetSecurity -Name Get-*Firewall*
```

```Output
CommandType     Name                                               ModuleName
-----------     ----                                               ----------
Function        Get-NetFirewallAddressFilter                       NetSecurity
Function        Get-NetFirewallApplicationFilter                   NetSecurity
Function        Get-NetFirewallInterfaceFilter                     NetSecurity
Function        Get-NetFirewallInterfaceTypeFilter                 NetSecurity
Function        Get-NetFirewallPortFilter                          NetSecurity
Function        Get-NetFirewallProfile                             NetSecurity
Function        Get-NetFirewallRule                                NetSecurity
Function        Get-NetFirewallSecurityFilter                      NetSecurity
Function        Get-NetFirewallServiceFilter                       NetSecurity
Function        Get-NetFirewallSetting                             NetSecurity
```

```powershell
Get-NetFirewallRule -DisplayName "Windows Remote Management*" |
  Format-Table -Property DisplayName, Name -AutoSize
```

```Output
DisplayName                                              Name
-----------                                              ----
Windows Remote Management (HTTP-In)                      WINRM-HTTP-In-TCP
Windows Remote Management (HTTP-In)                      WINRM-HTTP-In-TCP-PUBLIC
Windows Remote Management - Compatibility Mode (HTTP-In) WINRM-HTTP-Compat-In-TCP
```

<span data-ttu-id="43bd0-211">`New-PSSession` Cria uma sessão remota ( **PSSession** ) para o computador Server01.</span><span class="sxs-lookup"><span data-stu-id="43bd0-211">`New-PSSession` creates a remote session ( **PSSession** ) to the Server01 computer.</span></span> <span data-ttu-id="43bd0-212">A **PSSession** é salva na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="43bd0-212">The **PSSession** is saved in the `$s` variable.</span></span>

<span data-ttu-id="43bd0-213">A execução `Get-Module` com o parâmetro **PSSession** mostra que o módulo **NetSecurity** está instalado e disponível no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43bd0-213">Running `Get-Module` with the **PSSession** parameter shows that the **NetSecurity** module is installed and available on the remote computer.</span></span> <span data-ttu-id="43bd0-214">Esse comando é equivalente a usar o `Invoke-Command` cmdlet para executar o `Get-Module` comando na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="43bd0-214">This command is equivalent to using the `Invoke-Command` cmdlet to run `Get-Module` command in the remote session.</span></span> <span data-ttu-id="43bd0-215">Por exemplo: (`Invoke-Command $s {Get-Module -ListAvailable -Name NetSecurity`</span><span class="sxs-lookup"><span data-stu-id="43bd0-215">For example: (`Invoke-Command $s {Get-Module -ListAvailable -Name NetSecurity`</span></span>

<span data-ttu-id="43bd0-216">A execução `Import-Module` com o parâmetro **PSSession** importa o módulo **NetSecurity** do computador remoto para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="43bd0-216">Running `Import-Module` with the **PSSession** parameter imports the **NetSecurity** module from the remote computer into the current session.</span></span> <span data-ttu-id="43bd0-217">O `Get-Command` cmdlet é usado para obter comandos que começam com **Get** e incluem o **Firewall** do módulo **NetSecurity** .</span><span class="sxs-lookup"><span data-stu-id="43bd0-217">The `Get-Command` cmdlet is used to get commands that begin with **Get** and include **Firewall** from the **NetSecurity** module.</span></span> <span data-ttu-id="43bd0-218">A saída confirma que o módulo e seus cmdlets foram importados para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="43bd0-218">The output confirms that the module and its cmdlets were imported into the current session.</span></span>

<span data-ttu-id="43bd0-219">Em seguida, o `Get-NetFirewallRule` cmdlet obtém gerenciamento remoto do Windows regras de firewall no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="43bd0-219">Next, the `Get-NetFirewallRule` cmdlet gets Windows Remote Management firewall rules on the Server01 computer.</span></span> <span data-ttu-id="43bd0-220">Isso é equivalente a usar o `Invoke-Command` cmdlet para executar `Get-NetFirewallRule` na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="43bd0-220">This is equivalent to using the `Invoke-Command` cmdlet to run `Get-NetFirewallRule` on the remote session.</span></span>

### <span data-ttu-id="43bd0-221">Exemplo 14: gerenciar o armazenamento em um computador remoto sem o sistema operacional Windows</span><span class="sxs-lookup"><span data-stu-id="43bd0-221">Example 14: Manage storage on a remote computer without the Windows operating system</span></span>

<span data-ttu-id="43bd0-222">Neste exemplo, o administrador do computador instalou o provedor WMI de descoberta de módulo, que permite que você use comandos CIM projetados para o provedor.</span><span class="sxs-lookup"><span data-stu-id="43bd0-222">In this example, the administrator of the computer has installed the Module Discovery WMI provider, which allows you to use CIM commands that are designed for the provider.</span></span>

<span data-ttu-id="43bd0-223">O `New-CimSession` cmdlet cria uma sessão no computador remoto chamado RSDGF03.</span><span class="sxs-lookup"><span data-stu-id="43bd0-223">The `New-CimSession` cmdlet creates a session on the remote computer named RSDGF03.</span></span> <span data-ttu-id="43bd0-224">A sessão se conecta ao serviço WMI no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43bd0-224">The session connects to the WMI service on the remote computer.</span></span> <span data-ttu-id="43bd0-225">A sessão CIM é salva na `$cs` variável.</span><span class="sxs-lookup"><span data-stu-id="43bd0-225">The CIM session is saved in the `$cs` variable.</span></span>
<span data-ttu-id="43bd0-226">`Import-Module` usa o **CimSession** no `$cs` para importar o módulo CIM de **armazenamento** do computador RSDGF03.</span><span class="sxs-lookup"><span data-stu-id="43bd0-226">`Import-Module` uses the **CimSession** in `$cs` to import the **Storage** CIM module from the RSDGF03 computer.</span></span>

<span data-ttu-id="43bd0-227">O `Get-Command` cmdlet mostra o `Get-Disk` comando no módulo de **armazenamento** .</span><span class="sxs-lookup"><span data-stu-id="43bd0-227">The `Get-Command` cmdlet shows the `Get-Disk` command in the **Storage** module.</span></span> <span data-ttu-id="43bd0-228">Quando você importa um módulo CIM para a sessão local, o PowerShell converte os arquivos CDXML para cada comando nos scripts do PowerShell, que aparecem como funções na sessão local.</span><span class="sxs-lookup"><span data-stu-id="43bd0-228">When you import a CIM module into the local session, PowerShell converts the CDXML files for each command into PowerShell scripts, which appear as functions in the local session.</span></span>

<span data-ttu-id="43bd0-229">Embora `Get-Disk` o seja digitado na sessão local, o cmdlet é executado implicitamente no computador remoto do qual ele foi importado.</span><span class="sxs-lookup"><span data-stu-id="43bd0-229">Although `Get-Disk` is typed in the local session, the cmdlet implicitly runs on the remote computer from which it was imported.</span></span> <span data-ttu-id="43bd0-230">O comando retorna objetos do computador remoto para a sessão local.</span><span class="sxs-lookup"><span data-stu-id="43bd0-230">The command returns objects from the remote computer to the local session.</span></span>

```powershell
$cs = New-CimSession -ComputerName RSDGF03
Import-Module -CimSession $cs -Name Storage
# Importing a CIM module, converts the CDXML files for each command into PowerShell scripts.
# These appear as functions in the local session.
Get-Command Get-Disk
```

```Output
CommandType     Name                  ModuleName
-----------     ----                  ----------
Function        Get-Disk              Storage
```

```powershell
# Use implicit remoting to query disks on the remote computer from which the module was imported.
Get-Disk
```

```Output
Number Friendly Name           OperationalStatus  Total Size Partition Style
------ -------------           -----------------  ---------- ---------------
0      Virtual HD ATA Device   Online                  40 GB MBR
```

## <span data-ttu-id="43bd0-231">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="43bd0-231">PARAMETERS</span></span>

### <span data-ttu-id="43bd0-232">-Alias</span><span class="sxs-lookup"><span data-stu-id="43bd0-232">-Alias</span></span>

<span data-ttu-id="43bd0-233">Especifica os aliases que esse cmdlet importa do módulo para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="43bd0-233">Specifies the aliases that this cmdlet imports from the module into the current session.</span></span> <span data-ttu-id="43bd0-234">Digite uma lista de aliases separados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="43bd0-234">Enter a comma-separated list of aliases.</span></span> <span data-ttu-id="43bd0-235">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="43bd0-235">Wildcard characters are permitted.</span></span>

<span data-ttu-id="43bd0-236">Alguns módulos exportam automaticamente aliases selecionados para sua sessão quando você importa o módulo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-236">Some modules automatically export selected aliases into your session when you import the module.</span></span>
<span data-ttu-id="43bd0-237">Esse parâmetro permite selecionar dentre os aliases exportados.</span><span class="sxs-lookup"><span data-stu-id="43bd0-237">This parameter lets you select from among the exported aliases.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="43bd0-238">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="43bd0-238">-ArgumentList</span></span>

<span data-ttu-id="43bd0-239">Especifica uma matriz de argumentos ou valores de parâmetro que são passados para um módulo de script durante o `Import-Module` comando.</span><span class="sxs-lookup"><span data-stu-id="43bd0-239">Specifies an array of arguments, or parameter values, that are passed to a script module during the `Import-Module` command.</span></span> <span data-ttu-id="43bd0-240">Esse parâmetro é válido somente quando você está importando um módulo de script.</span><span class="sxs-lookup"><span data-stu-id="43bd0-240">This parameter is valid only when you're importing a script module.</span></span>

<span data-ttu-id="43bd0-241">Você também pode se referir ao parâmetro **ArgumentList** por seu alias, **args** .</span><span class="sxs-lookup"><span data-stu-id="43bd0-241">You can also refer to the **ArgumentList** parameter by its alias, **args** .</span></span> <span data-ttu-id="43bd0-242">Para obter mais informações sobre o comportamento de **ArgumentList** , consulte [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="43bd0-242">For more information about the behavior of **ArgumentList** , see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43bd0-243">-AsCustomObject</span><span class="sxs-lookup"><span data-stu-id="43bd0-243">-AsCustomObject</span></span>

<span data-ttu-id="43bd0-244">Indica que esse cmdlet retorna um objeto personalizado com membros que representam os membros do módulo importados.</span><span class="sxs-lookup"><span data-stu-id="43bd0-244">Indicates that this cmdlet returns a custom object with members that represent the imported module members.</span></span> <span data-ttu-id="43bd0-245">Este parâmetro é válido somente para módulos de script.</span><span class="sxs-lookup"><span data-stu-id="43bd0-245">This parameter is valid only for script modules.</span></span>

<span data-ttu-id="43bd0-246">Quando você usa o parâmetro **AsCustomObject** , `Import-Module` o importa os membros do módulo para a sessão e, em seguida, retorna um objeto **PSCustomObject** em vez de um objeto **PSModuleInfo** .</span><span class="sxs-lookup"><span data-stu-id="43bd0-246">When you use the **AsCustomObject** parameter, `Import-Module` imports the module members into the session and then returns a **PSCustomObject** object instead of a **PSModuleInfo** object.</span></span> <span data-ttu-id="43bd0-247">Você pode salvar o objeto personalizado em uma variável e usar a notação de ponto para invocar os membros.</span><span class="sxs-lookup"><span data-stu-id="43bd0-247">You can save the custom object in a variable and use dot notation to invoke the members.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43bd0-248">-Assembly</span><span class="sxs-lookup"><span data-stu-id="43bd0-248">-Assembly</span></span>

<span data-ttu-id="43bd0-249">Especifica uma matriz de objetos de assembly.</span><span class="sxs-lookup"><span data-stu-id="43bd0-249">Specifies an array of assembly objects.</span></span> <span data-ttu-id="43bd0-250">Esse cmdlet importa os cmdlets e provedores implementados nos objetos de assembly especificados.</span><span class="sxs-lookup"><span data-stu-id="43bd0-250">This cmdlet imports the cmdlets and providers implemented in the specified assembly objects.</span></span> <span data-ttu-id="43bd0-251">Insira uma variável que contenha objetos de assembly ou um comando que crie objetos de assembly.</span><span class="sxs-lookup"><span data-stu-id="43bd0-251">Enter a variable that contains assembly objects or a command that creates assembly objects.</span></span> <span data-ttu-id="43bd0-252">Você também pode canalizar um objeto de assembly para `Import-Module` .</span><span class="sxs-lookup"><span data-stu-id="43bd0-252">You can also pipe an assembly object to `Import-Module`.</span></span>

<span data-ttu-id="43bd0-253">Quando você usa esse parâmetro, somente os cmdlets e provedores implementados pelos assemblies especificados são importados.</span><span class="sxs-lookup"><span data-stu-id="43bd0-253">When you use this parameter, only the cmdlets and providers implemented by the specified assemblies are imported.</span></span> <span data-ttu-id="43bd0-254">Se o módulo contiver outros arquivos, eles não serão importados e você poderá estar faltando membros importantes do módulo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-254">If the module contains other files, they aren't imported, and you might be missing important members of the module.</span></span> <span data-ttu-id="43bd0-255">Use esse parâmetro para depurar e testar o módulo, ou quando for instruído a usá-lo pelo autor do módulo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-255">Use this parameter for debugging and testing the module, or when you're instructed to use it by the module author.</span></span>

```yaml
Type: System.Reflection.Assembly[]
Parameter Sets: Assembly
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="43bd0-256">-CimNamespace</span><span class="sxs-lookup"><span data-stu-id="43bd0-256">-CimNamespace</span></span>

<span data-ttu-id="43bd0-257">Especifica o namespace de um provedor CIM alternativo que expõe módulos CIM.</span><span class="sxs-lookup"><span data-stu-id="43bd0-257">Specifies the namespace of an alternate CIM provider that exposes CIM modules.</span></span> <span data-ttu-id="43bd0-258">O valor padrão é o namespace do provedor WMI de detecção de módulos.</span><span class="sxs-lookup"><span data-stu-id="43bd0-258">The default value is the namespace of the Module Discovery WMI provider.</span></span>

<span data-ttu-id="43bd0-259">Use esse parâmetro para importar módulos CIM de computadores e dispositivos que não estão executando um sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="43bd0-259">Use this parameter to import CIM modules from computers and devices that aren't running a Windows operating system.</span></span>

<span data-ttu-id="43bd0-260">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="43bd0-260">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43bd0-261">-CimResourceUri</span><span class="sxs-lookup"><span data-stu-id="43bd0-261">-CimResourceUri</span></span>

<span data-ttu-id="43bd0-262">Especifica um local alternativo para módulos CIM.</span><span class="sxs-lookup"><span data-stu-id="43bd0-262">Specifies an alternate location for CIM modules.</span></span> <span data-ttu-id="43bd0-263">O valor padrão é o URI de recurso do provedor WMI de descoberta de módulo no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43bd0-263">The default value is the resource URI of the Module Discovery WMI provider on the remote computer.</span></span>

<span data-ttu-id="43bd0-264">Use esse parâmetro para importar módulos CIM de computadores e dispositivos que não estão executando um sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="43bd0-264">Use this parameter to import CIM modules from computers and devices that aren't running a Windows operating system.</span></span>

<span data-ttu-id="43bd0-265">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="43bd0-265">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Uri
Parameter Sets: CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43bd0-266">-CimSession</span><span class="sxs-lookup"><span data-stu-id="43bd0-266">-CimSession</span></span>

<span data-ttu-id="43bd0-267">Especifica uma sessão CIM no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43bd0-267">Specifies a CIM session on the remote computer.</span></span> <span data-ttu-id="43bd0-268">Insira uma variável que contém a sessão CIM ou um comando que obtém a sessão CIM, como um comando [Get-CimSession](../CimCmdlets/Get-CimSession.md) .</span><span class="sxs-lookup"><span data-stu-id="43bd0-268">Enter a variable that contains the CIM session or a command that gets the CIM session, such as a [Get-CimSession](../CimCmdlets/Get-CimSession.md) command.</span></span>

<span data-ttu-id="43bd0-269">`Import-Module` usa a conexão de sessão CIM para importar módulos do computador remoto para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="43bd0-269">`Import-Module` uses the CIM session connection to import modules from the remote computer into the current session.</span></span> <span data-ttu-id="43bd0-270">Quando você usa os comandos do módulo importado na sessão atual, os comandos são executados no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43bd0-270">When you use the commands from the imported module in the current session, the commands run on the remote computer.</span></span>

<span data-ttu-id="43bd0-271">Você pode usar esse parâmetro para importar módulos de computadores e dispositivos que não estão executando o sistema operacional Windows e computadores com Windows que têm o PowerShell, mas que não têm a comunicação remota do PowerShell habilitada.</span><span class="sxs-lookup"><span data-stu-id="43bd0-271">You can use this parameter to import modules from computers and devices that aren't running the Windows operating system, and Windows computers that have PowerShell, but don't have PowerShell remoting enabled.</span></span>

<span data-ttu-id="43bd0-272">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="43bd0-272">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession
Parameter Sets: CimSession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43bd0-273">-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="43bd0-273">-Cmdlet</span></span>

<span data-ttu-id="43bd0-274">Especifica uma matriz de cmdlets que esse cmdlet importa do módulo para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="43bd0-274">Specifies an array of cmdlets that this cmdlet imports from the module into the current session.</span></span>
<span data-ttu-id="43bd0-275">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="43bd0-275">Wildcard characters are permitted.</span></span>

<span data-ttu-id="43bd0-276">Alguns módulos exportam automaticamente cmdlets selecionados para sua sessão quando você importa o módulo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-276">Some modules automatically export selected cmdlets into your session when you import the module.</span></span>
<span data-ttu-id="43bd0-277">Esse parâmetro permite selecionar dentre os cmdlets exportados.</span><span class="sxs-lookup"><span data-stu-id="43bd0-277">This parameter lets you select from among the exported cmdlets.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="43bd0-278">-DisableNameChecking</span><span class="sxs-lookup"><span data-stu-id="43bd0-278">-DisableNameChecking</span></span>

<span data-ttu-id="43bd0-279">Indica que esse cmdlet suprime a mensagem que avisa quando você importa um cmdlet ou função cujo nome inclui um verbo não aprovado ou um caractere proibido.</span><span class="sxs-lookup"><span data-stu-id="43bd0-279">Indicates that this cmdlet suppresses the message that warns you when you import a cmdlet or function whose name includes an unapproved verb or a prohibited character.</span></span>

<span data-ttu-id="43bd0-280">Por padrão, quando um módulo que você importa exporta cmdlets ou funções que têm verbos não aprovados em seus nomes, o PowerShell exibe a seguinte mensagem de aviso:</span><span class="sxs-lookup"><span data-stu-id="43bd0-280">By default, when a module that you import exports cmdlets or functions that have unapproved verbs in their names, PowerShell displays the following warning message:</span></span>

> <span data-ttu-id="43bd0-281">Aviso: alguns nomes de comando importados incluem verbos não aprovados que podem torná-los menos detectáveis.</span><span class="sxs-lookup"><span data-stu-id="43bd0-281">WARNING: Some imported command names include unapproved verbs which might make them less discoverable.</span></span> <span data-ttu-id="43bd0-282">Use o parâmetro Verbose para obter mais detalhes ou digite Get-Verb para ver a lista de verbos aprovados."</span><span class="sxs-lookup"><span data-stu-id="43bd0-282">Use the Verbose parameter for more detail or type Get-Verb to see the list of approved verbs.</span></span>

<span data-ttu-id="43bd0-283">A mensagem é apenas um aviso.</span><span class="sxs-lookup"><span data-stu-id="43bd0-283">This message is only a warning.</span></span> <span data-ttu-id="43bd0-284">O módulo completo ainda é importado, incluindo os comandos não autorizados.</span><span class="sxs-lookup"><span data-stu-id="43bd0-284">The complete module is still imported, including the non-conforming commands.</span></span> <span data-ttu-id="43bd0-285">Embora a mensagem seja exibida para usuários do módulo, o problema de nomenclatura deve ser corrigido pelo autor do módulo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-285">Although the message is displayed to module users, the naming problem should be fixed by the module author.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43bd0-286">-Force</span><span class="sxs-lookup"><span data-stu-id="43bd0-286">-Force</span></span>

<span data-ttu-id="43bd0-287">Esse parâmetro faz com que um módulo seja carregado ou recarregado acima do atual.</span><span class="sxs-lookup"><span data-stu-id="43bd0-287">This parameter causes a module to be loaded, or reloaded, over top of the current one.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43bd0-288">-FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="43bd0-288">-FullyQualifiedName</span></span>

<span data-ttu-id="43bd0-289">Especifica o nome totalmente qualificado do módulo como uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="43bd0-289">Specifies the fully qualified name of the module as a hash table.</span></span> <span data-ttu-id="43bd0-290">O valor pode ser uma combinação de cadeias de caracteres e tabelas de hash.</span><span class="sxs-lookup"><span data-stu-id="43bd0-290">The value can be a combination of strings and hash tables.</span></span> <span data-ttu-id="43bd0-291">A tabela de hash tem as seguintes chaves.</span><span class="sxs-lookup"><span data-stu-id="43bd0-291">The hash table has the following keys.</span></span>

- <span data-ttu-id="43bd0-292">`ModuleName` - **Necessário** Especifica o nome do módulo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-292">`ModuleName` - **Required** Specifies the module name.</span></span>
- <span data-ttu-id="43bd0-293">`GUID` - **Opcional** Especifica o GUID do módulo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-293">`GUID` - **Optional** Specifies the GUID of the module.</span></span>
- <span data-ttu-id="43bd0-294">Também é **necessário** especificar uma das três chaves abaixo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-294">It's also **Required** to specify one of the three below keys.</span></span> <span data-ttu-id="43bd0-295">Essas chaves não podem ser usadas juntas.</span><span class="sxs-lookup"><span data-stu-id="43bd0-295">These keys can't be used together.</span></span>
  - <span data-ttu-id="43bd0-296">`ModuleVersion` -Especifica uma versão mínima aceitável do módulo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-296">`ModuleVersion` - Specifies a minimum acceptable version of the module.</span></span>
  - <span data-ttu-id="43bd0-297">`RequiredVersion` -Especifica uma versão exata e necessária do módulo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-297">`RequiredVersion` - Specifies an exact, required version of the module.</span></span>
  - <span data-ttu-id="43bd0-298">`MaximumVersion` -Especifica a versão máxima aceitável do módulo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-298">`MaximumVersion` - Specifies the maximum acceptable version of the module.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: FullyQualifiedName, FullyQualifiedNameAndPSSession
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="43bd0-299">-Função</span><span class="sxs-lookup"><span data-stu-id="43bd0-299">-Function</span></span>

<span data-ttu-id="43bd0-300">Especifica uma matriz de funções que esse cmdlet importa do módulo para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="43bd0-300">Specifies an array of functions that this cmdlet imports from the module into the current session.</span></span>
<span data-ttu-id="43bd0-301">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="43bd0-301">Wildcard characters are permitted.</span></span> <span data-ttu-id="43bd0-302">Alguns módulos exportam automaticamente funções selecionadas para sua sessão quando você importa o módulo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-302">Some modules automatically export selected functions into your session when you import the module.</span></span> <span data-ttu-id="43bd0-303">Esse parâmetro permite selecionar dentre as funções exportadas.</span><span class="sxs-lookup"><span data-stu-id="43bd0-303">This parameter lets you select from among the exported functions.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="43bd0-304">-Global</span><span class="sxs-lookup"><span data-stu-id="43bd0-304">-Global</span></span>

<span data-ttu-id="43bd0-305">Indica que esse cmdlet importa módulos para o estado de sessão global para que fiquem disponíveis para todos os comandos na sessão.</span><span class="sxs-lookup"><span data-stu-id="43bd0-305">Indicates that this cmdlet imports modules into the global session state so they are available to all commands in the session.</span></span>

<span data-ttu-id="43bd0-306">Por padrão, quando `Import-Module` o cmdlet é chamado no prompt de comando, arquivo de script ou scriptblock, todos os comandos são importados para o estado de sessão global.</span><span class="sxs-lookup"><span data-stu-id="43bd0-306">By default, when `Import-Module` cmdlet is called from the command prompt, script file, or scriptblock, all the commands are imported into the global session state.</span></span>

<span data-ttu-id="43bd0-307">Quando invocado de outro módulo, `Import-Module` o cmdlet importa os comandos em um módulo, incluindo comandos de módulos aninhados, para o estado de sessão do módulo de chamada.</span><span class="sxs-lookup"><span data-stu-id="43bd0-307">When invoked from another module, `Import-Module` cmdlet imports the commands in a module, including commands from nested modules, into the calling module's session state.</span></span>

> [!TIP]
> <span data-ttu-id="43bd0-308">Você deve evitar `Import-Module` a chamada de dentro de um módulo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-308">You should avoid calling `Import-Module` from within a module.</span></span> <span data-ttu-id="43bd0-309">Em vez disso, declare o módulo de destino como um módulo aninhado no manifesto do módulo pai.</span><span class="sxs-lookup"><span data-stu-id="43bd0-309">Instead, declare the target module as a nested module in the parent module's manifest.</span></span> <span data-ttu-id="43bd0-310">A declaração de módulos aninhados melhora a descoberta de dependências.</span><span class="sxs-lookup"><span data-stu-id="43bd0-310">Declaring nested modules improves the discoverability of dependencies.</span></span>

<span data-ttu-id="43bd0-311">O parâmetro **Global** é equivalente ao parâmetro **Scope** com um valor de **Global** .</span><span class="sxs-lookup"><span data-stu-id="43bd0-311">The **Global** parameter is equivalent to the **Scope** parameter with a value of **Global** .</span></span>

<span data-ttu-id="43bd0-312">Para restringir os comandos exportados por um módulo, use um `Export-ModuleMember` comando no módulo de script.</span><span class="sxs-lookup"><span data-stu-id="43bd0-312">To restrict the commands that a module exports, use an `Export-ModuleMember` command in the script module.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43bd0-313">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="43bd0-313">-MaximumVersion</span></span>

<span data-ttu-id="43bd0-314">Especifica uma versão máxima.</span><span class="sxs-lookup"><span data-stu-id="43bd0-314">Specifies a maximum version.</span></span> <span data-ttu-id="43bd0-315">Esse cmdlet importa apenas uma versão do módulo que seja menor ou igual ao valor especificado.</span><span class="sxs-lookup"><span data-stu-id="43bd0-315">This cmdlet imports only a version of the module that is less than or equal to the specified value.</span></span> <span data-ttu-id="43bd0-316">Se nenhuma versão for qualificada, `Import-Module` o retornará um erro.</span><span class="sxs-lookup"><span data-stu-id="43bd0-316">If no version qualifies, `Import-Module` returns an error.</span></span>

```yaml
Type: System.String
Parameter Sets: Name, PSSession, CimSession, WinCompat
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43bd0-317">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="43bd0-317">-MinimumVersion</span></span>

<span data-ttu-id="43bd0-318">Especifica uma versão mínima.</span><span class="sxs-lookup"><span data-stu-id="43bd0-318">Specifies a minimum version.</span></span> <span data-ttu-id="43bd0-319">Esse cmdlet importa apenas uma versão do módulo que seja maior ou igual ao valor especificado.</span><span class="sxs-lookup"><span data-stu-id="43bd0-319">This cmdlet imports only a version of the module that is greater than or equal to the specified value.</span></span> <span data-ttu-id="43bd0-320">Use o nome de parâmetro **MinimumVersion** ou seu alias, **Version** .</span><span class="sxs-lookup"><span data-stu-id="43bd0-320">Use the **MinimumVersion** parameter name or its alias, **Version** .</span></span> <span data-ttu-id="43bd0-321">Se nenhuma versão for qualificada, `Import-Module` o gerará um erro.</span><span class="sxs-lookup"><span data-stu-id="43bd0-321">If no version qualifies, `Import-Module` generates an error.</span></span>

<span data-ttu-id="43bd0-322">Para especificar uma versão exata, use o parâmetro **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="43bd0-322">To specify an exact version, use the **RequiredVersion** parameter.</span></span> <span data-ttu-id="43bd0-323">Você também pode usar os parâmetros de **módulo** e **versão** da palavra-chave **#Requires** para exigir uma versão específica de um módulo em um script.</span><span class="sxs-lookup"><span data-stu-id="43bd0-323">You can also use the **Module** and **Version** parameters of the **#Requires** keyword to require a specific version of a module in a script.</span></span>

<span data-ttu-id="43bd0-324">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="43bd0-324">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Version
Parameter Sets: Name, PSSession, CimSession, WinCompat
Aliases: Version

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43bd0-325">-ModuleInfo</span><span class="sxs-lookup"><span data-stu-id="43bd0-325">-ModuleInfo</span></span>

<span data-ttu-id="43bd0-326">Especifica uma matriz de objetos de módulo a ser importada.</span><span class="sxs-lookup"><span data-stu-id="43bd0-326">Specifies an array of module objects to import.</span></span> <span data-ttu-id="43bd0-327">Insira uma variável que contenha os objetos de módulo ou um comando que obtenha os objetos de módulo, como o seguinte comando: `Get-Module -ListAvailable` .</span><span class="sxs-lookup"><span data-stu-id="43bd0-327">Enter a variable that contains the module objects, or a command that gets the module objects, such as the following command: `Get-Module -ListAvailable`.</span></span> <span data-ttu-id="43bd0-328">Você também pode canalizar objetos de módulo para `Import-Module` .</span><span class="sxs-lookup"><span data-stu-id="43bd0-328">You can also pipe module objects to `Import-Module`.</span></span>

```yaml
Type: System.Management.Automation.PSModuleInfo[]
Parameter Sets: ModuleInfo
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="43bd0-329">-Name</span><span class="sxs-lookup"><span data-stu-id="43bd0-329">-Name</span></span>

<span data-ttu-id="43bd0-330">Especifica os nomes dos módulos a serem importados.</span><span class="sxs-lookup"><span data-stu-id="43bd0-330">Specifies the names of the modules to import.</span></span> <span data-ttu-id="43bd0-331">Insira o nome do módulo ou o nome de um arquivo no módulo, como um `.psd1` `.psm1` arquivo,, `.dll` ou `.ps1` .</span><span class="sxs-lookup"><span data-stu-id="43bd0-331">Enter the name of the module or the name of a file in the module, such as a `.psd1`, `.psm1`, `.dll`, or `.ps1` file.</span></span> <span data-ttu-id="43bd0-332">Caminhos de arquivo são opcionais.</span><span class="sxs-lookup"><span data-stu-id="43bd0-332">File paths are optional.</span></span> <span data-ttu-id="43bd0-333">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="43bd0-333">Wildcard characters aren't permitted.</span></span> <span data-ttu-id="43bd0-334">Também é possível canalizar nomes de módulo e nome de filename para `Import-Module` .</span><span class="sxs-lookup"><span data-stu-id="43bd0-334">You can also pipe module names and filenames to `Import-Module`.</span></span>

<span data-ttu-id="43bd0-335">Se você omitir um caminho, `Import-Module` o procurará o módulo nos caminhos salvos na `$env:PSModulePath` variável de ambiente.</span><span class="sxs-lookup"><span data-stu-id="43bd0-335">If you omit a path, `Import-Module` looks for the module in the paths saved in the `$env:PSModulePath` environment variable.</span></span>

<span data-ttu-id="43bd0-336">Especifique somente o nome de módulo sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="43bd0-336">Specify only the module name whenever possible.</span></span> <span data-ttu-id="43bd0-337">Quando você especifica um nome de arquivo, somente os membros que são implementados nesse arquivo são importados.</span><span class="sxs-lookup"><span data-stu-id="43bd0-337">When you specify a file name, only the members that are implemented in that file are imported.</span></span> <span data-ttu-id="43bd0-338">Se o módulo contiver outros arquivos, eles não serão importados e você poderá estar faltando membros importantes do módulo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-338">If the module contains other files, they aren't imported, and you might be missing important members of the module.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name, PSSession, CimSession, WinCompat
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="43bd0-339">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="43bd0-339">-NoClobber</span></span>

<span data-ttu-id="43bd0-340">Impede a importação de comandos que têm os mesmos nomes que os comandos existentes na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="43bd0-340">Prevents importing commands that have the same names as existing commands in the current session.</span></span> <span data-ttu-id="43bd0-341">Por padrão, o `Import-Module` importa todos os comandos de módulo exportados.</span><span class="sxs-lookup"><span data-stu-id="43bd0-341">By default, `Import-Module` imports all exported module commands.</span></span>

<span data-ttu-id="43bd0-342">Comandos que têm os mesmos nomes podem ocultar ou substituir comandos na sessão.</span><span class="sxs-lookup"><span data-stu-id="43bd0-342">Commands that have the same names can hide or replace commands in the session.</span></span> <span data-ttu-id="43bd0-343">Para evitar conflitos de nome de comando em uma sessão, use os parâmetros **Prefix** ou **NoClobber** .</span><span class="sxs-lookup"><span data-stu-id="43bd0-343">To avoid command name conflicts in a session, use the **Prefix** or **NoClobber** parameters.</span></span> <span data-ttu-id="43bd0-344">Para obter mais informações sobre conflitos de nome e sobre a precedência dos comandos, consulte "Módulos e Conflitos de Nome" em [about_Modules](about/about_Modules.md) e [about_Command_Precedence](about/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="43bd0-344">For more information about name conflicts and command precedence, see "Modules and Name Conflicts" in [about_Modules](about/about_Modules.md) and [about_Command_Precedence](about/about_Command_Precedence.md).</span></span>

<span data-ttu-id="43bd0-345">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="43bd0-345">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43bd0-346">-PassThru</span><span class="sxs-lookup"><span data-stu-id="43bd0-346">-PassThru</span></span>

<span data-ttu-id="43bd0-347">Retorna um objeto que representa o item com o qual você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="43bd0-347">Returns an object representing the item with which you're working.</span></span> <span data-ttu-id="43bd0-348">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="43bd0-348">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43bd0-349">-Prefixo</span><span class="sxs-lookup"><span data-stu-id="43bd0-349">-Prefix</span></span>

<span data-ttu-id="43bd0-350">Especifica um prefixo que esse cmdlet adiciona aos substantivos nos nomes dos membros de módulo importados.</span><span class="sxs-lookup"><span data-stu-id="43bd0-350">Specifies a prefix that this cmdlet adds to the nouns in the names of imported module members.</span></span>

<span data-ttu-id="43bd0-351">Use este parâmetro para evitar conflitos de nome que podem ocorrer quando diferentes membros da sessão têm o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="43bd0-351">Use this parameter to avoid name conflicts that might occur when different members in the session have the same name.</span></span> <span data-ttu-id="43bd0-352">Esse parâmetro não altera o módulo e não afeta os arquivos que o módulo importa para seu próprio uso.</span><span class="sxs-lookup"><span data-stu-id="43bd0-352">This parameter does not change the module, and it does not affect files that the module imports for its own use.</span></span> <span data-ttu-id="43bd0-353">Eles são conhecidos como módulos aninhados.</span><span class="sxs-lookup"><span data-stu-id="43bd0-353">These are known as nested modules.</span></span> <span data-ttu-id="43bd0-354">Esse cmdlet afeta apenas os nomes dos membros na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="43bd0-354">This cmdlet affects only the names of members in the current session.</span></span>

<span data-ttu-id="43bd0-355">Por exemplo, se você especificar o prefixo UTC e, em seguida, importar um `Get-Date` cmdlet, o cmdlet será conhecido na sessão como `Get-UTCDate` , e não será confundido com o `Get-Date` cmdlet original.</span><span class="sxs-lookup"><span data-stu-id="43bd0-355">For example, if you specify the prefix UTC and then import a `Get-Date` cmdlet, the cmdlet is known in the session as `Get-UTCDate`, and it is not confused with the original `Get-Date` cmdlet.</span></span>

<span data-ttu-id="43bd0-356">O valor deste parâmetro tem precedência sobre a propriedade **DefaultCommandPrefix** do módulo, que especifica o prefixo padrão.</span><span class="sxs-lookup"><span data-stu-id="43bd0-356">The value of this parameter takes precedence over the **DefaultCommandPrefix** property of the module, which specifies the default prefix.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43bd0-357">-PSSession</span><span class="sxs-lookup"><span data-stu-id="43bd0-357">-PSSession</span></span>

<span data-ttu-id="43bd0-358">Especifica uma sessão gerenciada pelo usuário do PowerShell ( **PSSession** ) da qual este cmdlet importa módulos para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="43bd0-358">Specifies a PowerShell user-managed session ( **PSSession** ) from which this cmdlet imports modules into the current session.</span></span> <span data-ttu-id="43bd0-359">Insira uma variável que contenha uma **PSSession** ou um comando que obtenha uma **PSSession** , como um `Get-PSSession` comando.</span><span class="sxs-lookup"><span data-stu-id="43bd0-359">Enter a variable that contains a **PSSession** or a command that gets a **PSSession** , such as a `Get-PSSession` command.</span></span>

<span data-ttu-id="43bd0-360">Quando importa um módulo de uma sessão diferente para a sessão atual, você pode usar os cmdlets do módulo na sessão atual, assim como você usaria cmdlets de um módulo local.</span><span class="sxs-lookup"><span data-stu-id="43bd0-360">When you import a module from a different session into the current session, you can use the cmdlets from the module in the current session, just as you would use cmdlets from a local module.</span></span> <span data-ttu-id="43bd0-361">Os comandos que usam os cmdlets remotos são executados na sessão remota, mas os detalhes de comunicação remota são gerenciados em segundo plano pelo PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43bd0-361">Commands that use the remote cmdlets run in the remote session, but the remoting details are managed in the background by PowerShell.</span></span>

<span data-ttu-id="43bd0-362">Esse parâmetro usa o recurso de comunicação remota implícita do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43bd0-362">This parameter uses the Implicit Remoting feature of PowerShell.</span></span> <span data-ttu-id="43bd0-363">É equivalente a usar o `Import-PSSession` cmdlet para importar módulos específicos de uma sessão.</span><span class="sxs-lookup"><span data-stu-id="43bd0-363">It is equivalent to using the `Import-PSSession` cmdlet to import particular modules from a session.</span></span>

<span data-ttu-id="43bd0-364">`Import-Module` Não é possível importar módulos do PowerShell Core de outra sessão.</span><span class="sxs-lookup"><span data-stu-id="43bd0-364">`Import-Module` cannot import PowerShell Core modules from another session.</span></span> <span data-ttu-id="43bd0-365">Os módulos do PowerShell Core têm nomes que começam com Microsoft. PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43bd0-365">The PowerShell Core modules have names that begin with Microsoft.PowerShell.</span></span>

<span data-ttu-id="43bd0-366">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="43bd0-366">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: PSSession, FullyQualifiedNameAndPSSession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43bd0-367">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="43bd0-367">-RequiredVersion</span></span>

<span data-ttu-id="43bd0-368">Especifica uma versão do módulo que este cmdlet importa.</span><span class="sxs-lookup"><span data-stu-id="43bd0-368">Specifies a version of the module that this cmdlet imports.</span></span> <span data-ttu-id="43bd0-369">Se a versão não estiver instalada, o `Import-Module` gerará um erro.</span><span class="sxs-lookup"><span data-stu-id="43bd0-369">If the version is not installed, `Import-Module` generates an error.</span></span>

<span data-ttu-id="43bd0-370">Por padrão, `Import-Module` o importa o módulo sem verificar o número de versão.</span><span class="sxs-lookup"><span data-stu-id="43bd0-370">By default, `Import-Module` imports the module without checking the version number.</span></span>

<span data-ttu-id="43bd0-371">Para especificar uma versão mínima, use o parâmetro **MinimumVersion** .</span><span class="sxs-lookup"><span data-stu-id="43bd0-371">To specify a minimum version, use the **MinimumVersion** parameter.</span></span> <span data-ttu-id="43bd0-372">Você também pode usar os parâmetros de **módulo** e **versão** da palavra-chave **#Requires** para exigir uma versão específica de um módulo em um script.</span><span class="sxs-lookup"><span data-stu-id="43bd0-372">You can also use the **Module** and **Version** parameters of the **#Requires** keyword to require a specific version of a module in a script.</span></span>

<span data-ttu-id="43bd0-373">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="43bd0-373">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="43bd0-374">Scripts que usam **RequiredVersion** para importar módulos que estão incluídos em versões existentes do sistema operacional Windows não são executados automaticamente em versões futuras do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="43bd0-374">Scripts that use **RequiredVersion** to import modules that are included with existing releases of the Windows operating system don't automatically run in future releases of the Windows operating system.</span></span> <span data-ttu-id="43bd0-375">Isso ocorre porque os números de versão do módulo do PowerShell em versões futuras do sistema operacional Windows são maiores do que os números de versão do módulo em versões existentes do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="43bd0-375">This is because PowerShell module version numbers in future releases of the Windows operating system are higher than module version numbers in existing releases of the Windows operating system.</span></span>

```yaml
Type: System.Version
Parameter Sets: Name, PSSession, CimSession, WinCompat
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43bd0-376">-Escopo</span><span class="sxs-lookup"><span data-stu-id="43bd0-376">-Scope</span></span>

<span data-ttu-id="43bd0-377">Especifica um escopo no qual esse cmdlet importa o módulo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-377">Specifies a scope into which this cmdlet imports the module.</span></span>

<span data-ttu-id="43bd0-378">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="43bd0-378">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="43bd0-379">**Global** .</span><span class="sxs-lookup"><span data-stu-id="43bd0-379">**Global** .</span></span> <span data-ttu-id="43bd0-380">Disponível para todos os comandos da sessão.</span><span class="sxs-lookup"><span data-stu-id="43bd0-380">Available to all commands in the session.</span></span> <span data-ttu-id="43bd0-381">Equivalente ao parâmetro **Global** .</span><span class="sxs-lookup"><span data-stu-id="43bd0-381">Equivalent to the **Global** parameter.</span></span>
- <span data-ttu-id="43bd0-382">**Local** .</span><span class="sxs-lookup"><span data-stu-id="43bd0-382">**Local** .</span></span> <span data-ttu-id="43bd0-383">Disponível somente no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="43bd0-383">Available only in the current scope.</span></span>

<span data-ttu-id="43bd0-384">Por padrão, quando `Import-Module` o cmdlet é chamado no prompt de comando, arquivo de script ou scriptblock, todos os comandos são importados para o estado de sessão global.</span><span class="sxs-lookup"><span data-stu-id="43bd0-384">By default, when `Import-Module` cmdlet is called from the command prompt, script file, or scriptblock, all the commands are imported into the global session state.</span></span> <span data-ttu-id="43bd0-385">Você pode usar o parâmetro **-Scope** com o valor de **local** para importar o conteúdo do módulo para o escopo do script ou scriptblock.</span><span class="sxs-lookup"><span data-stu-id="43bd0-385">You can use the **-Scope** parameter with the value of **Local** to import module content into the script or scriptblock scope.</span></span>

<span data-ttu-id="43bd0-386">Quando invocado de outro módulo, `Import-Module` o cmdlet importa os comandos em um módulo, incluindo comandos de módulos aninhados, para o estado de sessão do chamador.</span><span class="sxs-lookup"><span data-stu-id="43bd0-386">When invoked from another module, `Import-Module` cmdlet imports the commands in a module, including commands from nested modules, into the caller's session state.</span></span> <span data-ttu-id="43bd0-387">Especificar `-Scope Global` ou `-Global` indicar que este cmdlet importa módulos para o estado de sessão global para que fiquem disponíveis para todos os comandos na sessão.</span><span class="sxs-lookup"><span data-stu-id="43bd0-387">Specifying `-Scope Global` or `-Global` indicates that this cmdlet imports modules into the global session state so they are available to all commands in the session.</span></span>

<span data-ttu-id="43bd0-388">O parâmetro **global** é equivalente ao parâmetro de **escopo** com um valor de global.</span><span class="sxs-lookup"><span data-stu-id="43bd0-388">The **Global** parameter is equivalent to the **Scope** parameter with a value of Global.</span></span>

<span data-ttu-id="43bd0-389">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="43bd0-389">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Local, Global

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43bd0-390">-Variable</span><span class="sxs-lookup"><span data-stu-id="43bd0-390">-Variable</span></span>

<span data-ttu-id="43bd0-391">Especifica uma matriz de variáveis que este cmdlet importa do módulo para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="43bd0-391">Specifies an array of variables that this cmdlet imports from the module into the current session.</span></span>
<span data-ttu-id="43bd0-392">Insira uma lista de variáveis.</span><span class="sxs-lookup"><span data-stu-id="43bd0-392">Enter a list of variables.</span></span> <span data-ttu-id="43bd0-393">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="43bd0-393">Wildcard characters are permitted.</span></span>

<span data-ttu-id="43bd0-394">Alguns módulos exportam automaticamente variáveis selecionadas para sua sessão quando você importa o módulo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-394">Some modules automatically export selected variables into your session when you import the module.</span></span>
<span data-ttu-id="43bd0-395">Esse parâmetro permite selecionar dentre as variáveis exportadas.</span><span class="sxs-lookup"><span data-stu-id="43bd0-395">This parameter lets you select from among the exported variables.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="43bd0-396">-SkipEditionCheck</span><span class="sxs-lookup"><span data-stu-id="43bd0-396">-SkipEditionCheck</span></span>

<span data-ttu-id="43bd0-397">Ignora a verificação no `CompatiblePSEditions` campo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-397">Skips the check on the `CompatiblePSEditions` field.</span></span>

<span data-ttu-id="43bd0-398">Permite carregar um módulo do `"$($env:windir)\System32\WindowsPowerShell\v1.0\Modules"` diretório do módulo no PowerShell Core quando esse módulo não especifica `Core` no `CompatiblePSEditions` campo manifesto.</span><span class="sxs-lookup"><span data-stu-id="43bd0-398">Allows loading a module from the `"$($env:windir)\System32\WindowsPowerShell\v1.0\Modules"` module directory into PowerShell Core when that module does not specify `Core` in the `CompatiblePSEditions` manifest field.</span></span>

<span data-ttu-id="43bd0-399">Ao importar um módulo de outro caminho, essa opção não faz nada, pois a verificação não é executada.</span><span class="sxs-lookup"><span data-stu-id="43bd0-399">When importing a module from another path, this switch does nothing, since the check is not performed.</span></span> <span data-ttu-id="43bd0-400">No Linux e no macOS, esse comutador não faz nada.</span><span class="sxs-lookup"><span data-stu-id="43bd0-400">On Linux and macOS, this switch does nothing.</span></span>

<span data-ttu-id="43bd0-401">Para obter mais informações, consulte [about_PowerShell_Editions](About/about_PowerShell_Editions.md).</span><span class="sxs-lookup"><span data-stu-id="43bd0-401">For more information, see [about_PowerShell_Editions](About/about_PowerShell_Editions.md).</span></span>

> [!WARNING]
> <span data-ttu-id="43bd0-402">`Import-Module -SkipEditionCheck` ainda é provável que falhe ao importar um módulo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-402">`Import-Module -SkipEditionCheck` is still likely to fail to import a module.</span></span> <span data-ttu-id="43bd0-403">Mesmo que tenha êxito, invocar um comando do módulo pode falhar mais tarde ao tentar usar uma API incompatível.</span><span class="sxs-lookup"><span data-stu-id="43bd0-403">Even if it does succeed, invoking a command from the module may later fail when it tries to use an incompatible API.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="43bd0-404">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="43bd0-404">CommonParameters</span></span>

<span data-ttu-id="43bd0-405">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="43bd0-405">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="43bd0-406">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="43bd0-406">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="43bd0-407">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="43bd0-407">INPUTS</span></span>

### <span data-ttu-id="43bd0-408">System. String, System. Management. Automation. PSModuleInfo, System. Reflection. assembly</span><span class="sxs-lookup"><span data-stu-id="43bd0-408">System.String, System.Management.Automation.PSModuleInfo, System.Reflection.Assembly</span></span>

<span data-ttu-id="43bd0-409">É possível canalizar um nome de módulo, objeto de módulo ou objeto de assembly para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="43bd0-409">You can pipe a module name, module object, or assembly object to this cmdlet.</span></span>

## <span data-ttu-id="43bd0-410">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="43bd0-410">OUTPUTS</span></span>

### <span data-ttu-id="43bd0-411">Nenhum, System. Management. Automation. PSModuleInfo ou System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="43bd0-411">None, System.Management.Automation.PSModuleInfo, or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="43bd0-412">Por padrão, `Import-Module` o não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="43bd0-412">By default, `Import-Module` does not generate any output.</span></span> <span data-ttu-id="43bd0-413">Se você especificar o parâmetro **PassThru** , o cmdlet gerará um objeto **System. Management. Automation. PSModuleInfo** que representa o módulo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-413">If you specify the **PassThru** parameter, the cmdlet generates a **System.Management.Automation.PSModuleInfo** object that represents the module.</span></span> <span data-ttu-id="43bd0-414">Se você especificar o parâmetro **AsCustomObject** , ele gerará um objeto **PSCustomObject** .</span><span class="sxs-lookup"><span data-stu-id="43bd0-414">If you specify the **AsCustomObject** parameter, it generates a **PSCustomObject** object.</span></span>

## <span data-ttu-id="43bd0-415">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="43bd0-415">NOTES</span></span>

- <span data-ttu-id="43bd0-416">Antes que você possa importar um módulo, o módulo deve estar instalado no computador local.</span><span class="sxs-lookup"><span data-stu-id="43bd0-416">Before you can import a module, the module must be installed on the local computer.</span></span> <span data-ttu-id="43bd0-417">Ou seja, o diretório do módulo deve ser copiado para um diretório acessível ao seu computador local.</span><span class="sxs-lookup"><span data-stu-id="43bd0-417">That is, the module directory must be copied to a directory that is accessible to your local computer.</span></span> <span data-ttu-id="43bd0-418">Para obter mais informações, consulte [about_Modules](About/about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="43bd0-418">For more information, see [about_Modules](About/about_Modules.md).</span></span>

  <span data-ttu-id="43bd0-419">Você também pode usar os parâmetros **PSSession** e **CIMSession** para importar módulos que estão instalados em computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="43bd0-419">You can also use the **PSSession** and **CIMSession** parameters to import modules that are installed on remote computers.</span></span> <span data-ttu-id="43bd0-420">No entanto, os comandos que usam os cmdlets nesses módulos são executados na sessão remota no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="43bd0-420">However, commands that use the cmdlets in these modules run in the remote session on the remote computer.</span></span>

- <span data-ttu-id="43bd0-421">Se você importar Membros com o mesmo nome e o mesmo tipo em sua sessão, o PowerShell usará o membro importado por último por padrão.</span><span class="sxs-lookup"><span data-stu-id="43bd0-421">If you import members with the same name and the same type into your session, PowerShell uses the member imported last by default.</span></span> <span data-ttu-id="43bd0-422">Variáveis e aliases são substituídos e os originais não estão acessíveis.</span><span class="sxs-lookup"><span data-stu-id="43bd0-422">Variables and aliases are replaced, and the originals aren't accessible.</span></span> <span data-ttu-id="43bd0-423">As funções, os cmdlets e os provedores são simplesmente sombreados pelos novos membros.</span><span class="sxs-lookup"><span data-stu-id="43bd0-423">Functions, cmdlets, and providers are merely shadowed by the new members.</span></span> <span data-ttu-id="43bd0-424">Eles podem ser acessados qualificando o nome do comando com o nome de seu snap-in, módulo ou caminho de função.</span><span class="sxs-lookup"><span data-stu-id="43bd0-424">They can be accessed by qualifying the command name with the name of its snap-in, module, or function path.</span></span>

- <span data-ttu-id="43bd0-425">Para atualizar os dados de formatação para comandos que foram importados de um módulo, use o `Update-FormatData` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="43bd0-425">To update the formatting data for commands that have been imported from a module, use the `Update-FormatData` cmdlet.</span></span> <span data-ttu-id="43bd0-426">`Update-FormatData` também atualiza os dados de formatação para comandos na sessão que foram importados dos módulos.</span><span class="sxs-lookup"><span data-stu-id="43bd0-426">`Update-FormatData` also updates the formatting data for commands in the session that were imported from modules.</span></span> <span data-ttu-id="43bd0-427">Se o arquivo de formatação de um módulo for alterado, você poderá executar um `Update-FormatData` comando para atualizar os dados de formatação para comandos importados.</span><span class="sxs-lookup"><span data-stu-id="43bd0-427">If the formatting file for a module changes, you can run an `Update-FormatData` command to update the formatting data for imported commands.</span></span> <span data-ttu-id="43bd0-428">Você não precisa importar o módulo novamente.</span><span class="sxs-lookup"><span data-stu-id="43bd0-428">You don't need to import the module again.</span></span>

- <span data-ttu-id="43bd0-429">A partir do Windows PowerShell 3,0, os comandos principais instalados com o PowerShell são empacotados em módulos.</span><span class="sxs-lookup"><span data-stu-id="43bd0-429">Starting in Windows PowerShell 3.0, the core commands that are installed with PowerShell are packaged in modules.</span></span> <span data-ttu-id="43bd0-430">No Windows PowerShell 2,0 e em programas de host que criam sessões de estilo mais antigo em versões posteriores do PowerShell, os comandos principais são empacotados em snap-ins ( **PSSnapins** ).</span><span class="sxs-lookup"><span data-stu-id="43bd0-430">In Windows PowerShell 2.0, and in host programs that create older-style sessions in later versions of PowerShell, the core commands are packaged in snap-ins ( **PSSnapins** ).</span></span> <span data-ttu-id="43bd0-431">A exceção é **Microsoft. PowerShell. Core** , que sempre é um snap-in.</span><span class="sxs-lookup"><span data-stu-id="43bd0-431">The exception is **Microsoft.PowerShell.Core** , which is always a snap-in.</span></span> <span data-ttu-id="43bd0-432">Além disso, as sessões remotas, como as iniciadas pelo `New-PSSession` cmdlet, são sessões de estilo mais antigo que incluem snap-ins de núcleo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-432">Also, remote sessions, such as those started by the `New-PSSession` cmdlet, are older-style sessions that include core snap-ins.</span></span>

  <span data-ttu-id="43bd0-433">Para obter informações sobre o método **CreateDefault2** que cria sessões de estilo mais recente com módulos de núcleo, consulte o [método CreateDefault2](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2).</span><span class="sxs-lookup"><span data-stu-id="43bd0-433">For information about the **CreateDefault2** method that creates newer-style sessions with core modules, see the [CreateDefault2 Method](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2).</span></span>

- <span data-ttu-id="43bd0-434">`Import-Module` Não é possível importar módulos do PowerShell Core de outra sessão.</span><span class="sxs-lookup"><span data-stu-id="43bd0-434">`Import-Module` cannot import PowerShell Core modules from another session.</span></span> <span data-ttu-id="43bd0-435">Os módulos do PowerShell Core têm nomes que começam com `Microsoft.PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="43bd0-435">The PowerShell Core modules have names that begin with `Microsoft.PowerShell`.</span></span>

- <span data-ttu-id="43bd0-436">No Windows PowerShell 2,0, alguns dos valores de Propriedade do objeto de módulo, como os valores de propriedade **ExportedCmdlets** e **NestedModules** , não foram populados até que o módulo foi importado e não estivesse disponível no objeto de módulo que o parâmetro **PassThru** retorna.</span><span class="sxs-lookup"><span data-stu-id="43bd0-436">In Windows PowerShell 2.0, some of the property values of the module object, such as the **ExportedCmdlets** and **NestedModules** property values, were not populated until the module was imported and were not available on the module object that the **PassThru** parameter returns.</span></span> <span data-ttu-id="43bd0-437">No Windows PowerShell 3,0, todos os valores de Propriedade do módulo são populados.</span><span class="sxs-lookup"><span data-stu-id="43bd0-437">In Windows PowerShell 3.0, all module property values are populated.</span></span>

- <span data-ttu-id="43bd0-438">Se você tentar importar um módulo que contém assemblies de modo misto que não são compatíveis com o Windows PowerShell 3,0, `Import-Module` o retornará uma mensagem de erro semelhante à seguinte.</span><span class="sxs-lookup"><span data-stu-id="43bd0-438">If you attempt to import a module that contains mixed-mode assemblies that aren't compatible with Windows PowerShell 3.0, `Import-Module` returns an error message like the following one.</span></span>

  > <span data-ttu-id="43bd0-439">Import-Module: o assembly de modo misto é compilado em relação à versão ' v 2.0.50727 ' do tempo de execução e não pode ser carregado no tempo de execução 4,0 sem informações de configuração adicionais.</span><span class="sxs-lookup"><span data-stu-id="43bd0-439">Import-Module : Mixed mode assembly is built against version 'v2.0.50727' of the runtime and cannot be loaded in the 4.0 runtime without additional configuration information.</span></span>

  <span data-ttu-id="43bd0-440">Esse erro ocorre quando um módulo projetado para o Windows PowerShell 2,0 contém pelo menos um assembly de módulo misto, ou seja, um assembly que inclui código gerenciado e não gerenciado, como C++ e C#.</span><span class="sxs-lookup"><span data-stu-id="43bd0-440">This error occurs when a module that is designed for Windows PowerShell 2.0 contains at least one mixed-module assembly, that is, an assembly that includes both managed and non-managed code, such as C++ and C#.</span></span>

  <span data-ttu-id="43bd0-441">Para importar um módulo que contém assemblies de modo misto, inicie o Windows PowerShell 2,0 usando o comando a seguir e tente o `Import-Module` comando novamente.</span><span class="sxs-lookup"><span data-stu-id="43bd0-441">To import a module that contains mixed-mode assemblies, start Windows PowerShell 2.0 by using the following command, and then try the `Import-Module` command again.</span></span>

  `PowerShell.exe -Version 2.0`

- <span data-ttu-id="43bd0-442">Para usar o recurso de sessão CIM, o computador remoto deve ter comunicação remota do WS-Management e a Instrumentação de Gerenciamento do Windows (WMI), que é a implementação da Microsoft do padrão CIM.</span><span class="sxs-lookup"><span data-stu-id="43bd0-442">To use the CIM session feature, the remote computer must have WS-Management remoting and Windows Management Instrumentation (WMI), which is the Microsoft implementation of the Common Information Model (CIM) standard.</span></span> <span data-ttu-id="43bd0-443">O computador também deve ter o provedor de Descoberta do Módulo WMI ou um provedor CIM alternativo que tem os mesmos recursos básicos.</span><span class="sxs-lookup"><span data-stu-id="43bd0-443">The computer must also have the Module Discovery WMI provider or an alternate CIM provider that has the same basic features.</span></span>

  <span data-ttu-id="43bd0-444">Você pode usar o recurso de sessão CIM em computadores que não estão executando um sistema operacional Windows e em computadores com Windows que têm o PowerShell, mas não têm a comunicação remota do PowerShell habilitada.</span><span class="sxs-lookup"><span data-stu-id="43bd0-444">You can use the CIM session feature on computers that aren't running a Windows operating system and on Windows computers that have PowerShell, but don't have PowerShell remoting enabled.</span></span>

  <span data-ttu-id="43bd0-445">Você também pode usar os parâmetros CIM para obter módulos CIM de computadores que têm a comunicação remota do PowerShell habilitada, incluindo o computador local.</span><span class="sxs-lookup"><span data-stu-id="43bd0-445">You can also use the CIM parameters to get CIM modules from computers that have PowerShell remoting enabled, including the local computer.</span></span> <span data-ttu-id="43bd0-446">Quando você cria uma sessão CIM no computador local, o PowerShell usa DCOM, em vez de WMI, para criar a sessão.</span><span class="sxs-lookup"><span data-stu-id="43bd0-446">When you create a CIM session on the local computer, PowerShell uses DCOM, instead of WMI, to create the session.</span></span>

- <span data-ttu-id="43bd0-447">Por padrão, o `Import-Module` importa módulos no escopo global mesmo quando chamado de um escopo descendente.</span><span class="sxs-lookup"><span data-stu-id="43bd0-447">By default, `Import-Module` imports modules in the global scope even when called from a descendant scope.</span></span> <span data-ttu-id="43bd0-448">O escopo de nível superior e todos os escopos descendentes têm acesso aos elementos exportados do módulo.</span><span class="sxs-lookup"><span data-stu-id="43bd0-448">The top-level scope and all descendant scopes have access to the module's exported elements.</span></span>

  <span data-ttu-id="43bd0-449">Em um escopo descendente, `-Scope Local` o limita a importação para esse escopo e todos os seus escopos descendentes.</span><span class="sxs-lookup"><span data-stu-id="43bd0-449">In a descendant scope, `-Scope Local` limits the import to that scope and all its descendant scopes.</span></span> <span data-ttu-id="43bd0-450">Os escopos pai não veem os membros importados.</span><span class="sxs-lookup"><span data-stu-id="43bd0-450">Parent scopes then do not see the imported members.</span></span>

  > [!NOTE]
  > <span data-ttu-id="43bd0-451">`Get-Module` mostra todos os módulos carregados na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="43bd0-451">`Get-Module` shows all modules loaded in the current session.</span></span> <span data-ttu-id="43bd0-452">Isso inclui módulos carregados localmente em um escopo descendente.</span><span class="sxs-lookup"><span data-stu-id="43bd0-452">This includes modules loaded locally in a descendant scope.</span></span> <span data-ttu-id="43bd0-453">Use `Get-Command -Module modulename` para ver quais membros são carregados no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="43bd0-453">Use `Get-Command -Module modulename` to see which members are loaded in the current scope.</span></span>

  <span data-ttu-id="43bd0-454">Se o módulo incluir definições de classe e enumeração, use `using module` no início do script.</span><span class="sxs-lookup"><span data-stu-id="43bd0-454">If the module includes class and enum definitions, use `using module` at the beginning of your script.</span></span> <span data-ttu-id="43bd0-455">Isso importa os scripts, incluindo as definições de classe e enumeração.</span><span class="sxs-lookup"><span data-stu-id="43bd0-455">This import the scripts, including the class and enum definitions.</span></span> <span data-ttu-id="43bd0-456">Para obter mais informações, consulte [about_Using](About/about_Using.md).</span><span class="sxs-lookup"><span data-stu-id="43bd0-456">For more information, see [about_Using](About/about_Using.md).</span></span>

## <span data-ttu-id="43bd0-457">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="43bd0-457">RELATED LINKS</span></span>

[<span data-ttu-id="43bd0-458">Export-ModuleMember</span><span class="sxs-lookup"><span data-stu-id="43bd0-458">Export-ModuleMember</span></span>](Export-ModuleMember.md)

[<span data-ttu-id="43bd0-459">Get-Module</span><span class="sxs-lookup"><span data-stu-id="43bd0-459">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="43bd0-460">New-Module</span><span class="sxs-lookup"><span data-stu-id="43bd0-460">New-Module</span></span>](New-Module.md)

[<span data-ttu-id="43bd0-461">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="43bd0-461">Remove-Module</span></span>](Remove-Module.md)

[<span data-ttu-id="43bd0-462">about_PowerShell_Editions</span><span class="sxs-lookup"><span data-stu-id="43bd0-462">about_PowerShell_Editions</span></span>](About/about_PowerShell_Editions.md)
