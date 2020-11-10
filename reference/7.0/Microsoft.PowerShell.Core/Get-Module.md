---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-module?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Module
ms.openlocfilehash: cd04565f427cdf8aebf585d978e0e8d2a5b28c09
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94391214"
---
# <span data-ttu-id="66d5f-103">Get-Module</span><span class="sxs-lookup"><span data-stu-id="66d5f-103">Get-Module</span></span>

## <span data-ttu-id="66d5f-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="66d5f-104">SYNOPSIS</span></span>
<span data-ttu-id="66d5f-105">Obtém os módulos que foram importados ou podem ser importados para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="66d5f-105">Gets the modules that have been imported or that can be imported into the current session.</span></span>

## <span data-ttu-id="66d5f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="66d5f-106">SYNTAX</span></span>

### <span data-ttu-id="66d5f-107">Carregado (padrão)</span><span class="sxs-lookup"><span data-stu-id="66d5f-107">Loaded (Default)</span></span>

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-All] [<CommonParameters>]
```

### <span data-ttu-id="66d5f-108">Disponível</span><span class="sxs-lookup"><span data-stu-id="66d5f-108">Available</span></span>

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-All] [-ListAvailable]
 [-PSEdition <String>] [-SkipEditionCheck] [-Refresh] [<CommonParameters>]
```

### <span data-ttu-id="66d5f-109">PsSession</span><span class="sxs-lookup"><span data-stu-id="66d5f-109">PsSession</span></span>

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-ListAvailable]
 [-PSEdition <String>] [-SkipEditionCheck] [-Refresh] -PSSession <PSSession> [<CommonParameters>]
```

### <span data-ttu-id="66d5f-110">CimSession</span><span class="sxs-lookup"><span data-stu-id="66d5f-110">CimSession</span></span>

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-ListAvailable]
 [-SkipEditionCheck] [-Refresh] -CimSession <CimSession> [-CimResourceUri <Uri>] [-CimNamespace <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="66d5f-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="66d5f-111">DESCRIPTION</span></span>

<span data-ttu-id="66d5f-112">O `Get-Module` cmdlet obtém os módulos do PowerShell que foram importados ou que podem ser importados em uma sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="66d5f-112">The `Get-Module` cmdlet gets the PowerShell modules that have been imported, or that can be imported, into a PowerShell session.</span></span> <span data-ttu-id="66d5f-113">O objeto de módulo que `Get-Module` retorna contém informações valiosas sobre o módulo.</span><span class="sxs-lookup"><span data-stu-id="66d5f-113">The module object that `Get-Module` returns contains valuable information about the module.</span></span> <span data-ttu-id="66d5f-114">Você também pode canalizar os objetos de módulo para outros cmdlets, como `Import-Module` os `Remove-Module` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="66d5f-114">You can also pipe the module objects to other cmdlets, such as the `Import-Module` and `Remove-Module` cmdlets.</span></span>

<span data-ttu-id="66d5f-115">Sem parâmetros, `Get-Module` Obtém os módulos que foram importados para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="66d5f-115">Without parameters, `Get-Module` gets modules that have been imported into the current session.</span></span> <span data-ttu-id="66d5f-116">Para obter todos os módulos instalados, especifique o parâmetro **listAvailable** .</span><span class="sxs-lookup"><span data-stu-id="66d5f-116">To get all installed modules, specify the **ListAvailable** parameter.</span></span>

<span data-ttu-id="66d5f-117">`Get-Module` Obtém os módulos, mas não os importa.</span><span class="sxs-lookup"><span data-stu-id="66d5f-117">`Get-Module` gets modules, but it does not import them.</span></span> <span data-ttu-id="66d5f-118">A partir do Windows PowerShell 3,0, os módulos são importados automaticamente quando você usa um comando no módulo, mas um `Get-Module` comando não dispara uma importação automática.</span><span class="sxs-lookup"><span data-stu-id="66d5f-118">Starting in Windows PowerShell 3.0, modules are automatically imported when you use a command in the module, but a `Get-Module` command does not trigger an automatic import.</span></span> <span data-ttu-id="66d5f-119">Você também pode importar os módulos para a sessão usando o `Import-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="66d5f-119">You can also import the modules into your session by using the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="66d5f-120">A partir do Windows PowerShell 3,0, você pode obter e, em seguida, importar módulos de sessões remotas para a sessão local.</span><span class="sxs-lookup"><span data-stu-id="66d5f-120">Starting in Windows PowerShell 3.0, you can get and then, import modules from remote sessions into the local session.</span></span> <span data-ttu-id="66d5f-121">Essa estratégia usa o recurso de comunicação remota implícita do PowerShell e é equivalente a usar o `Import-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="66d5f-121">This strategy uses the Implicit Remoting feature of PowerShell and is equivalent to using the `Import-PSSession` cmdlet.</span></span> <span data-ttu-id="66d5f-122">Quando você usa comandos em módulos importados de outra sessão, os comandos são executados implicitamente na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="66d5f-122">When you use commands in modules imported from another session, the commands run implicitly in the remote session.</span></span> <span data-ttu-id="66d5f-123">Esse recurso permite que você gerencie o computador remoto a partir da sessão local.</span><span class="sxs-lookup"><span data-stu-id="66d5f-123">This feature lets you manage the remote computer from the local session.</span></span>

<span data-ttu-id="66d5f-124">Além disso, a partir do Windows PowerShell 3,0, você pode usar `Get-Module` e `Import-Module` para obter e importar módulos de modelo CIM (CIM), nos quais os cmdlets são definidos em arquivos de definição de cmdlet (CDXML).</span><span class="sxs-lookup"><span data-stu-id="66d5f-124">Also, starting in Windows PowerShell 3.0, you can use `Get-Module` and `Import-Module` to get and import Common Information Model (CIM) modules, in which the cmdlets are defined in Cmdlet Definition XML (CDXML) files.</span></span> <span data-ttu-id="66d5f-125">Esse recurso permite que você use cmdlets que são implementados em assemblies de código não gerenciado, como os escritos em C++.</span><span class="sxs-lookup"><span data-stu-id="66d5f-125">This feature lets you use cmdlets that are implemented in non-managed code assemblies, such as those written in C++.</span></span>

<span data-ttu-id="66d5f-126">Com esses novos recursos, os `Get-Module` `Import-Module` cmdlets e se tornam ferramentas principais para gerenciar empresas heterogêneas que incluem computadores que executam o sistema operacional Windows e computadores que executam outros sistemas operacionais.</span><span class="sxs-lookup"><span data-stu-id="66d5f-126">With these new features, the `Get-Module` and `Import-Module` cmdlets become primary tools for managing heterogeneous enterprises that include computers that run the Windows operating system and computers that run other operating systems.</span></span>

<span data-ttu-id="66d5f-127">Para gerenciar computadores remotos que executam o sistema operacional Windows que tem o PowerShell e a comunicação remota do PowerShell habilitada, crie uma **PSSession** no computador remoto e, em seguida, use o parâmetro **PSSession** do `Get-Module` para obter os módulos do PowerShell na **PSSession**.</span><span class="sxs-lookup"><span data-stu-id="66d5f-127">To manage remote computers that run the Windows operating system that have PowerShell and PowerShell remoting enabled, create a **PSSession** on the remote computer and then use the **PSSession** parameter of `Get-Module` to get the PowerShell modules in the **PSSession**.</span></span> <span data-ttu-id="66d5f-128">Quando você importa os módulos e, em seguida, usa os comandos importados na sessão atual, os comandos são executados implicitamente na **PSSession** no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="66d5f-128">When you import the modules, and then use the imported commands in the current session, the commands run implicitly in the **PSSession** on the remote computer.</span></span> <span data-ttu-id="66d5f-129">Você pode usar essa estratégia para gerenciar o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="66d5f-129">You can use this strategy to manage the remote computer.</span></span>

<span data-ttu-id="66d5f-130">Você pode usar uma estratégia semelhante para gerenciar computadores que não têm a comunicação remota do PowerShell habilitada.</span><span class="sxs-lookup"><span data-stu-id="66d5f-130">You can use a similar strategy to manage computers that do not have PowerShell remoting enabled.</span></span>
<span data-ttu-id="66d5f-131">Isso inclui computadores que não estão executando o sistema operacional Windows e computadores que têm o PowerShell, mas que não têm a comunicação remota do PowerShell habilitada.</span><span class="sxs-lookup"><span data-stu-id="66d5f-131">These include computers that are not running the Windows operating system, and computers that have PowerShell but do not have PowerShell remoting enabled.</span></span>

<span data-ttu-id="66d5f-132">Comece criando uma sessão CIM no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="66d5f-132">Start by creating a CIM session on the remote computer.</span></span> <span data-ttu-id="66d5f-133">Uma sessão CIM é uma conexão com Instrumentação de Gerenciamento do Windows (WMI) no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="66d5f-133">A CIM session is a connection to Windows Management Instrumentation (WMI) on the remote computer.</span></span> <span data-ttu-id="66d5f-134">Em seguida, use o parâmetro **CIMSession** de `Get-Module` para obter módulos CIM da sessão CIM.</span><span class="sxs-lookup"><span data-stu-id="66d5f-134">Then use the **CIMSession** parameter of `Get-Module` to get CIM modules from the CIM session.</span></span> <span data-ttu-id="66d5f-135">Quando você importa um módulo CIM usando o `Import-Module` cmdlet e, em seguida, executa os comandos importados, os comandos são executados implicitamente no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="66d5f-135">When you import a CIM module by using the `Import-Module` cmdlet and then run the imported commands, the commands run implicitly on the remote computer.</span></span> <span data-ttu-id="66d5f-136">Você pode usar essa estratégia de WMI e CIM para gerenciar o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="66d5f-136">You can use this WMI and CIM strategy to manage the remote computer.</span></span>

## <span data-ttu-id="66d5f-137">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="66d5f-137">EXAMPLES</span></span>

### <span data-ttu-id="66d5f-138">Exemplo 1: obter os módulos importados para a sessão atual</span><span class="sxs-lookup"><span data-stu-id="66d5f-138">Example 1: Get modules imported into the current session</span></span>

```powershell
Get-Module
```

<span data-ttu-id="66d5f-139">Este comando obtém módulos que foram importados para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="66d5f-139">This command gets modules that have been imported into the current session.</span></span>

### <span data-ttu-id="66d5f-140">Exemplo 2: obter módulos instalados e módulos disponíveis</span><span class="sxs-lookup"><span data-stu-id="66d5f-140">Example 2: Get installed modules and available modules</span></span>

```powershell
Get-Module -ListAvailable
```

<span data-ttu-id="66d5f-141">Este comando obtém os módulos que estão instalados no computador e que podem ser importados para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="66d5f-141">This command gets the modules that are installed on the computer and can be imported into the current session.</span></span>

<span data-ttu-id="66d5f-142">`Get-Module` procura os módulos disponíveis no caminho especificado pelo **$env:P** variável de ambiente smodulepath.</span><span class="sxs-lookup"><span data-stu-id="66d5f-142">`Get-Module` looks for available modules in the path specified by the **$env:PSModulePath** environment variable.</span></span> <span data-ttu-id="66d5f-143">Para obter mais informações sobre o **PSModulePath** , consulte [about_Modules](About/about_Modules.md) e [about_Environment_Variables](About/about_Environment_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="66d5f-143">For more information about **PSModulePath** , see [about_Modules](About/about_Modules.md) and [about_Environment_Variables](About/about_Environment_Variables.md).</span></span>

### <span data-ttu-id="66d5f-144">Exemplo 3: obter todos os arquivos exportados</span><span class="sxs-lookup"><span data-stu-id="66d5f-144">Example 3: Get all exported files</span></span>

```powershell
Get-Module -ListAvailable -All
```

<span data-ttu-id="66d5f-145">Este comando obtém todos os arquivos exportados para todos os módulos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="66d5f-145">This command gets all of the exported files for all available modules.</span></span>

### <span data-ttu-id="66d5f-146">Exemplo 4: obter um módulo por seu nome totalmente qualificado</span><span class="sxs-lookup"><span data-stu-id="66d5f-146">Example 4: Get a module by its fully qualified name</span></span>

```powershell
$FullyQualifedName = @{ModuleName="Microsoft.PowerShell.Management";ModuleVersion="3.1.0.0"}
Get-Module -FullyQualifiedName $FullyQualifedName | Format-Table -Property Name,Version
```

```Output
Name                             Version
----                             -------
Microsoft.PowerShell.Management  3.1.0.0
```

<span data-ttu-id="66d5f-147">Esse comando obtém o módulo **Microsoft. PowerShell. Management** especificando o nome totalmente qualificado do módulo usando o parâmetro **FullyQualifiedName** .</span><span class="sxs-lookup"><span data-stu-id="66d5f-147">This command gets the **Microsoft.PowerShell.Management** module by specifying the fully qualified name of the module by using the **FullyQualifiedName** parameter.</span></span> <span data-ttu-id="66d5f-148">Em seguida, o comando canaliza os resultados para o `Format-Table` cmdlet para formatar os resultados como uma tabela com **nome** e **versão** como títulos de coluna.</span><span class="sxs-lookup"><span data-stu-id="66d5f-148">The command then pipes the results into the `Format-Table` cmdlet to format the results as a table with **Name** and **Version** as the column headings.</span></span>

### <span data-ttu-id="66d5f-149">Exemplo 5: obter propriedades de um módulo</span><span class="sxs-lookup"><span data-stu-id="66d5f-149">Example 5: Get properties of a module</span></span>

```powershell
Get-Module | Get-Member -MemberType Property | Format-Table Name
```

```Output
Name
----
AccessMode
Author
ClrVersion
CompanyName
Copyright
Definition
Description
DotNetFrameworkVersion
ExportedAliases
ExportedCmdlets
ExportedCommands
ExportedFormatFiles
ExportedFunctions
ExportedTypeFiles
ExportedVariables
ExportedWorkflows
FileList
Guid
HelpInfoUri
LogPipelineExecutionDetails
ModuleBase
ModuleList
ModuleType
Name
NestedModules
OnRemove
Path
PowerShellHostName
PowerShellHostVersion
PowerShellVersion
PrivateData
ProcessorArchitecture
RequiredAssemblies
RequiredModules
RootModule
Scripts
SessionState
Version
```

<span data-ttu-id="66d5f-150">Esse comando obtém as propriedades do objeto **PSModuleInfo** que `Get-Module` retorna.</span><span class="sxs-lookup"><span data-stu-id="66d5f-150">This command gets the properties of the **PSModuleInfo** object that `Get-Module` returns.</span></span> <span data-ttu-id="66d5f-151">Há um objeto para cada arquivo de módulo.</span><span class="sxs-lookup"><span data-stu-id="66d5f-151">There is one object for each module file.</span></span>

<span data-ttu-id="66d5f-152">Você pode usar as propriedades para formatar e filtrar os objetos do módulo.</span><span class="sxs-lookup"><span data-stu-id="66d5f-152">You can use the properties to format and filter the module objects.</span></span> <span data-ttu-id="66d5f-153">Para obter mais informações sobre as propriedades, consulte [Propriedades de PSModuleInfo](/dotnet/api/system.management.automation.psmoduleinfo).</span><span class="sxs-lookup"><span data-stu-id="66d5f-153">For more information about the properties, see [PSModuleInfo Properties](/dotnet/api/system.management.automation.psmoduleinfo).</span></span>

<span data-ttu-id="66d5f-154">A saída inclui as novas propriedades, como **Author** e **CompanyName** , que foram introduzidas no Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="66d5f-154">The output includes the new properties, such as **Author** and **CompanyName** , that were introduced in Windows PowerShell 3.0.</span></span>

### <span data-ttu-id="66d5f-155">Exemplo 6: agrupar todos os módulos por nome</span><span class="sxs-lookup"><span data-stu-id="66d5f-155">Example 6: Group all modules by name</span></span>

```powershell
Get-Module -ListAvailable -All | Format-Table -Property Name, Moduletype, Path -Groupby Name
```

```Output
Name: AppLocker

Name      ModuleType Path
----      ---------- ----
AppLocker   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\AppLocker\AppLocker.psd1


   Name: Appx

Name ModuleType Path
---- ---------- ----
Appx   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Appx\en-US\Appx.psd1
Appx   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Appx\Appx.psd1
Appx     Script C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Appx\Appx.psm1


   Name: BestPractices

Name          ModuleType Path
----          ---------- ----
BestPractices   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\BestPractices\BestPractices.psd1


   Name: BitsTransfer

Name         ModuleType Path
----         ---------- ----
BitsTransfer   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\BitsTransfer\BitsTransfer.psd1
```

<span data-ttu-id="66d5f-156">Esse comando obtém todos os arquivos de módulo, importados e disponíveis e, em seguida, os agrupa por nome de módulo.</span><span class="sxs-lookup"><span data-stu-id="66d5f-156">This command gets all module files, both imported and available, and then groups them by module name.</span></span> <span data-ttu-id="66d5f-157">Isso lhe permite visualizar os arquivos de módulo que cada script está exportando.</span><span class="sxs-lookup"><span data-stu-id="66d5f-157">This lets you see the module files that each script is exporting.</span></span>

### <span data-ttu-id="66d5f-158">Exemplo 7: exibir o conteúdo de um manifesto de módulo</span><span class="sxs-lookup"><span data-stu-id="66d5f-158">Example 7: Display the contents of a module manifest</span></span>

<span data-ttu-id="66d5f-159">Esses comandos exibem o conteúdo do manifesto do módulo para o módulo **BitsTransfer** do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="66d5f-159">These commands display the contents of the module manifest for the Windows PowerShell **BitsTransfer** module.</span></span>

<span data-ttu-id="66d5f-160">Os módulos não precisam ter arquivos de manifesto.</span><span class="sxs-lookup"><span data-stu-id="66d5f-160">Modules are not required to have manifest files.</span></span> <span data-ttu-id="66d5f-161">Quando eles têm um arquivo de manifesto, o arquivo de manifesto é necessário apenas para incluir um número de versão.</span><span class="sxs-lookup"><span data-stu-id="66d5f-161">When they do have a manifest file, the manifest file is required only to include a version number.</span></span> <span data-ttu-id="66d5f-162">No entanto, os arquivos de manifesto muitas vezes fornecem informações úteis sobre um módulo, seus requisitos e seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="66d5f-162">However, manifest files often provide useful information about a module, its requirements, and its contents.</span></span>

```powershell
# First command
$m = Get-Module -list -Name BitsTransfer

# Second command
Get-Content $m.Path
```

```Output
@ {
    GUID               = "{8FA5064B-8479-4c5c-86EA-0D311FE48875}"
    Author             = "Microsoft Corporation"
    CompanyName        = "Microsoft Corporation"
    Copyright          = "Microsoft Corporation. All rights reserved."
    ModuleVersion      = "1.0.0.0"
    Description        = "Windows PowerShell File Transfer Module"
    PowerShellVersion  = "2.0"
    CLRVersion         = "2.0"
    NestedModules      = "Microsoft.BackgroundIntelligentTransfer.Management"
    FormatsToProcess   = "FileTransfer.Format.ps1xml"
    RequiredAssemblies = Join-Path $psScriptRoot "Microsoft.BackgroundIntelligentTransfer.Management.Interop.dll"
}
```

<span data-ttu-id="66d5f-163">O primeiro comando obtém o objeto PSModuleInfo, que representa o módulo BitsTransfer.</span><span class="sxs-lookup"><span data-stu-id="66d5f-163">The first command gets the PSModuleInfo object that represents BitsTransfer module.</span></span> <span data-ttu-id="66d5f-164">Ele salva o objeto na `$m` variável.</span><span class="sxs-lookup"><span data-stu-id="66d5f-164">It saves the object in the `$m` variable.</span></span>

<span data-ttu-id="66d5f-165">O segundo comando usa o `Get-Content` cmdlet para obter o conteúdo do arquivo de manifesto no caminho especificado.</span><span class="sxs-lookup"><span data-stu-id="66d5f-165">The second command uses the `Get-Content` cmdlet to get the content of the manifest file in the specified path.</span></span> <span data-ttu-id="66d5f-166">Ele usa a notação de ponto para obter o caminho para o arquivo de manifesto, que é armazenado na propriedade Path do objeto.</span><span class="sxs-lookup"><span data-stu-id="66d5f-166">It uses dot notation to get the path to the manifest file, which is stored in the Path property of the object.</span></span> <span data-ttu-id="66d5f-167">A saída mostra o conteúdo do manifesto do módulo.</span><span class="sxs-lookup"><span data-stu-id="66d5f-167">The output shows the contents of the module manifest.</span></span>

### <span data-ttu-id="66d5f-168">Exemplo 8: listar arquivos no diretório do módulo</span><span class="sxs-lookup"><span data-stu-id="66d5f-168">Example 8: List files in module directory</span></span>

```powershell
dir (Get-Module -ListAvailable FileTransfer).ModuleBase
```

```Output
Directory: C:\Windows\system32\WindowsPowerShell\v1.0\Modules\FileTransfer
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----        12/16/2008  12:36 PM            en-US
-a---        11/19/2008  11:30 PM      16184 FileTransfer.Format.ps1xml
-a---        11/20/2008  11:30 PM       1044 FileTransfer.psd1
-a---        12/16/2008  12:20 AM     108544 Microsoft.BackgroundIntelligentTransfer.Management.Interop.dll
```

<span data-ttu-id="66d5f-169">Esse comando lista os arquivos no diretório do módulo.</span><span class="sxs-lookup"><span data-stu-id="66d5f-169">This command lists the files in the directory of the module.</span></span> <span data-ttu-id="66d5f-170">Esta é outra maneira de determinar o que está em um módulo antes de importá-lo.</span><span class="sxs-lookup"><span data-stu-id="66d5f-170">This is another way to determine what is in a module before you import it.</span></span> <span data-ttu-id="66d5f-171">Alguns módulos podem ter arquivos de ajuda ou Leia-me, que descrevem o módulo.</span><span class="sxs-lookup"><span data-stu-id="66d5f-171">Some modules might have help files or ReadMe files that describe the module.</span></span>

### <span data-ttu-id="66d5f-172">Exemplo 9: obter os módulos instalados em um computador</span><span class="sxs-lookup"><span data-stu-id="66d5f-172">Example 9: Get modules installed on a computer</span></span>

```powershell
$s = New-PSSession -ComputerName Server01

Get-Module -PSSession $s -ListAvailable
```

<span data-ttu-id="66d5f-173">Estes comandos obtêm os módulos instalados no computador Servidor01.</span><span class="sxs-lookup"><span data-stu-id="66d5f-173">These commands get the modules that are installed on the Server01 computer.</span></span>

<span data-ttu-id="66d5f-174">O primeiro comando usa o `New-PSSession` cmdlet para criar uma **PSSession** no computador Server01.</span><span class="sxs-lookup"><span data-stu-id="66d5f-174">The first command uses the `New-PSSession` cmdlet to create a **PSSession** on the Server01 computer.</span></span> <span data-ttu-id="66d5f-175">O comando salva a **PSSession** na variável $s.</span><span class="sxs-lookup"><span data-stu-id="66d5f-175">The command saves the **PSSession** in the $s variable.</span></span>

<span data-ttu-id="66d5f-176">O segundo comando usa os parâmetros **PSSession** e **listAvailable** de `Get-Module` para obter os módulos na **PSSession** na `$s` variável.</span><span class="sxs-lookup"><span data-stu-id="66d5f-176">The second command uses the **PSSession** and **ListAvailable** parameters of `Get-Module` to get the modules in the **PSSession** in the `$s` variable.</span></span>

<span data-ttu-id="66d5f-177">Se você canaliza módulos de outras sessões para o `Import-Module` cmdlet, o `Import-Module` importa o módulo para a sessão atual usando o recurso de comunicação remota implícita.</span><span class="sxs-lookup"><span data-stu-id="66d5f-177">If you pipe modules from other sessions to the `Import-Module` cmdlet, `Import-Module` imports the module into the current session by using the implicit remoting feature.</span></span> <span data-ttu-id="66d5f-178">Isso é equivalente a usar o `Import-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="66d5f-178">This is equivalent to using the `Import-PSSession` cmdlet.</span></span> <span data-ttu-id="66d5f-179">Você pode usar os cmdlets do módulo na sessão atual, mas os comandos que usam esses cmdlets, na verdade, executam a sessão remota.</span><span class="sxs-lookup"><span data-stu-id="66d5f-179">You can use the cmdlets from the module in the current session, but commands that use these cmdlets actually run the remote session.</span></span> <span data-ttu-id="66d5f-180">Para obter mais informações, confira [`Import-Module`](Import-Module.md) e [`Import-PSSession`](../Microsoft.PowerShell.Utility/Import-PSSession.md).</span><span class="sxs-lookup"><span data-stu-id="66d5f-180">For more information, see [`Import-Module`](Import-Module.md) and [`Import-PSSession`](../Microsoft.PowerShell.Utility/Import-PSSession.md).</span></span>

### <span data-ttu-id="66d5f-181">Exemplo 10: gerenciar um computador que não executa o sistema operacional Windows</span><span class="sxs-lookup"><span data-stu-id="66d5f-181">Example 10: Manage a computer that does not run the Windows operating system</span></span>

<span data-ttu-id="66d5f-182">Os comandos neste exemplo permitem que você gerencie os sistemas de armazenamento de um computador remoto que não está executando o sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="66d5f-182">The commands in this example enable you to manage the storage systems of a remote computer that is not running the Windows operating system.</span></span>
<span data-ttu-id="66d5f-183">Neste exemplo, como o administrador do computador instalou o provedor WMI de descoberta do módulo, os comandos CIM podem usar os valores padrão, que são projetados para o provedor.</span><span class="sxs-lookup"><span data-stu-id="66d5f-183">In this example, because the administrator of the computer has installed the Module Discovery WMI provider, the CIM commands can use the default values, which are designed for the provider.</span></span>

```powershell
$cs = New-CimSession -ComputerName RSDGF03
Get-Module -CimSession $cs -Name Storage | Import-Module
Get-Command Get-Disk
```

```Output
CommandType     Name                  ModuleName
-----------     ----                  ----------
Function        Get-Disk              Storage
```

```powershell
Get-Disk
```

```Output
Number Friendly Name              OperationalStatus          Total Size Partition Style
------ -------------              -----------------          ---------- ---------------
0      Virtual HD ATA Device      Online                          40 GB MBR
```

<span data-ttu-id="66d5f-184">O primeiro comando usa o `New-CimSession` cmdlet para criar uma sessão no computador remoto RSDGF03.</span><span class="sxs-lookup"><span data-stu-id="66d5f-184">The first command uses the `New-CimSession` cmdlet to create a session on the RSDGF03 remote computer.</span></span> <span data-ttu-id="66d5f-185">A sessão conecta-se ao WMI no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="66d5f-185">The session connects to WMI on the remote computer.</span></span> <span data-ttu-id="66d5f-186">O comando salva a sessão CIM na `$cs` variável.</span><span class="sxs-lookup"><span data-stu-id="66d5f-186">The command saves the CIM session in the `$cs` variable.</span></span>

<span data-ttu-id="66d5f-187">O segundo comando usa a sessão CIM na `$cs` variável para executar um `Get-Module` comando no computador RSDGF03.</span><span class="sxs-lookup"><span data-stu-id="66d5f-187">The second command uses the CIM session in the `$cs` variable to run a `Get-Module` command on the RSDGF03 computer.</span></span> <span data-ttu-id="66d5f-188">O comando usa o parâmetro Name para especificar o módulo de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="66d5f-188">The command uses the Name parameter to specify the Storage module.</span></span> <span data-ttu-id="66d5f-189">O comando usa um operador de pipeline (|) para enviar o módulo de armazenamento para o `Import-Module` cmdlet, que o importa para a sessão local.</span><span class="sxs-lookup"><span data-stu-id="66d5f-189">The command uses a pipeline operator (|) to send the Storage module to the `Import-Module` cmdlet, which imports it into the local session.</span></span>

<span data-ttu-id="66d5f-190">O terceiro comando executa o `Get-Command` cmdlet no `Get-Disk` comando no módulo de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="66d5f-190">The third command runs the `Get-Command` cmdlet on the `Get-Disk` command in the Storage module.</span></span>
<span data-ttu-id="66d5f-191">Quando você importa um módulo CIM para a sessão local, o PowerShell converte os arquivos CDXML que representam o módulo CIM em scripts do PowerShell, que aparecem como funções na sessão local.</span><span class="sxs-lookup"><span data-stu-id="66d5f-191">When you import a CIM module into the local session, PowerShell converts the CDXML files that represent the CIM module into PowerShell scripts, which appear as functions in the local session.</span></span>

<span data-ttu-id="66d5f-192">O quarto comando executa o `Get-Disk` comando.</span><span class="sxs-lookup"><span data-stu-id="66d5f-192">The fourth command runs the `Get-Disk` command.</span></span> <span data-ttu-id="66d5f-193">Embora o comando seja digitado na sessão local, ele é executado implicitamente no computador remoto do qual foi importado.</span><span class="sxs-lookup"><span data-stu-id="66d5f-193">Although the command is typed in the local session, it runs implicitly on the remote computer from which it was imported.</span></span> <span data-ttu-id="66d5f-194">O comando obtém os objetos por meio do computador remoto e os retorna para a sessão local.</span><span class="sxs-lookup"><span data-stu-id="66d5f-194">The command gets objects from the remote computer and returns them to the local session.</span></span>

## <span data-ttu-id="66d5f-195">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="66d5f-195">PARAMETERS</span></span>

### <span data-ttu-id="66d5f-196">-All</span><span class="sxs-lookup"><span data-stu-id="66d5f-196">-All</span></span>

<span data-ttu-id="66d5f-197">Indica que esse cmdlet obtém todos os módulos em cada pasta de módulo, incluindo módulos aninhados, arquivos de manifesto (. psd1), arquivos de módulo de script (. psm1) e arquivos de módulo binário (. dll).</span><span class="sxs-lookup"><span data-stu-id="66d5f-197">Indicates that this cmdlet gets all modules in each module folder, including nested modules, manifest (.psd1) files, script module (.psm1) files, and binary module (.dll) files.</span></span> <span data-ttu-id="66d5f-198">Sem esse parâmetro, `Get-Module` obtém apenas o módulo padrão em cada pasta de módulo.</span><span class="sxs-lookup"><span data-stu-id="66d5f-198">Without this parameter, `Get-Module` gets only the default module in each module folder.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Loaded, Available
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66d5f-199">-CimNamespace</span><span class="sxs-lookup"><span data-stu-id="66d5f-199">-CimNamespace</span></span>

<span data-ttu-id="66d5f-200">Especifica o namespace de um provedor CIM alternativo que expõe módulos CIM.</span><span class="sxs-lookup"><span data-stu-id="66d5f-200">Specifies the namespace of an alternate CIM provider that exposes CIM modules.</span></span> <span data-ttu-id="66d5f-201">O valor padrão é o namespace do provedor WMI de detecção de módulos.</span><span class="sxs-lookup"><span data-stu-id="66d5f-201">The default value is the namespace of the Module Discovery WMI provider.</span></span>

<span data-ttu-id="66d5f-202">Use esse parâmetro para obter módulos CIM de computadores e dispositivos que não estão executando o sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="66d5f-202">Use this parameter to get CIM modules from computers and devices that are not running the Windows operating system.</span></span>

<span data-ttu-id="66d5f-203">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="66d5f-203">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="66d5f-204">-CimResourceUri</span><span class="sxs-lookup"><span data-stu-id="66d5f-204">-CimResourceUri</span></span>

<span data-ttu-id="66d5f-205">Especifica um local alternativo para módulos CIM.</span><span class="sxs-lookup"><span data-stu-id="66d5f-205">Specifies an alternate location for CIM modules.</span></span> <span data-ttu-id="66d5f-206">O valor padrão é o URI de recurso do provedor WMI de descoberta de módulo no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="66d5f-206">The default value is the resource URI of the Module Discovery WMI provider on the remote computer.</span></span>

<span data-ttu-id="66d5f-207">Use esse parâmetro para obter módulos CIM de computadores e dispositivos que não estão executando o sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="66d5f-207">Use this parameter to get CIM modules from computers and devices that are not running the Windows operating system.</span></span>

<span data-ttu-id="66d5f-208">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="66d5f-208">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="66d5f-209">-CimSession</span><span class="sxs-lookup"><span data-stu-id="66d5f-209">-CimSession</span></span>

<span data-ttu-id="66d5f-210">Especifica uma sessão CIM no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="66d5f-210">Specifies a CIM session on the remote computer.</span></span> <span data-ttu-id="66d5f-211">Insira uma variável que contém a sessão CIM ou um comando que obtém a sessão CIM, como um comando [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) .</span><span class="sxs-lookup"><span data-stu-id="66d5f-211">Enter a variable that contains the CIM session or a command that gets the CIM session, such as a [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) command.</span></span>

<span data-ttu-id="66d5f-212">`Get-Module` usa a conexão de sessão CIM para obter módulos do computador remoto.</span><span class="sxs-lookup"><span data-stu-id="66d5f-212">`Get-Module` uses the CIM session connection to get modules from the remote computer.</span></span> <span data-ttu-id="66d5f-213">Quando você importa o módulo usando o `Import-Module` cmdlet e usa os comandos do módulo importado na sessão atual, os comandos realmente são executados no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="66d5f-213">When you import the module by using the `Import-Module` cmdlet and use the commands from the imported module in the current session, the commands actually run on the remote computer.</span></span>

<span data-ttu-id="66d5f-214">Você pode usar esse parâmetro para obter módulos de computadores e dispositivos que não estão executando o sistema operacional Windows e computadores que têm o PowerShell, mas que não têm a comunicação remota do PowerShell habilitada.</span><span class="sxs-lookup"><span data-stu-id="66d5f-214">You can use this parameter to get modules from computers and devices that are not running the Windows operating system, and computers that have PowerShell, but do not have PowerShell remoting enabled.</span></span>

<span data-ttu-id="66d5f-215">O parâmetro **CimSession** obtém todos os módulos em **CIMSession**.</span><span class="sxs-lookup"><span data-stu-id="66d5f-215">The **CimSession** parameter gets all modules in the **CIMSession**.</span></span> <span data-ttu-id="66d5f-216">Porém, você pode importar somente módulos baseados em CIM e baseados em XML de definição de cmdlets (CDXML).</span><span class="sxs-lookup"><span data-stu-id="66d5f-216">However, you can import only CIM-based and Cmdlet Definition XML (CDXML)-based modules.</span></span>

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

### <span data-ttu-id="66d5f-217">-FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="66d5f-217">-FullyQualifiedName</span></span>

<span data-ttu-id="66d5f-218">Especifica os módulos com nomes que são especificados na forma de objetos **ModuleSpecification** .</span><span class="sxs-lookup"><span data-stu-id="66d5f-218">Specifies modules with names that are specified in the form of **ModuleSpecification** objects.</span></span> <span data-ttu-id="66d5f-219">Consulte a seção comentários do [Construtor ModuleSpecification (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span><span class="sxs-lookup"><span data-stu-id="66d5f-219">See the Remarks section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>

<span data-ttu-id="66d5f-220">Por exemplo, o parâmetro **FullyQualifiedModule** aceita um nome de módulo que é especificado em um destes formatos:</span><span class="sxs-lookup"><span data-stu-id="66d5f-220">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in either of these formats:</span></span>

- `@{ModuleName = "modulename"; ModuleVersion = "version_number"}`
- `@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

<span data-ttu-id="66d5f-221">**ModuleName** e **ModuleVersion** são obrigatórios, mas **Guid** é opcional.</span><span class="sxs-lookup"><span data-stu-id="66d5f-221">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span> <span data-ttu-id="66d5f-222">Você não pode especificar o parâmetro **FullyQualifiedModule** no mesmo comando que um parâmetro de **módulo** .</span><span class="sxs-lookup"><span data-stu-id="66d5f-222">You cannot specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span> <span data-ttu-id="66d5f-223">os dois parâmetros são mutuamente exclusivos.</span><span class="sxs-lookup"><span data-stu-id="66d5f-223">the two parameters are mutually exclusive.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="66d5f-224">-ListAvailable</span><span class="sxs-lookup"><span data-stu-id="66d5f-224">-ListAvailable</span></span>

<span data-ttu-id="66d5f-225">Indica que este cmdlet obtém todos os módulos instalados.</span><span class="sxs-lookup"><span data-stu-id="66d5f-225">Indicates that this cmdlet gets all installed modules.</span></span> <span data-ttu-id="66d5f-226">`Get-Module` Obtém os módulos nos caminhos listados na variável de ambiente **PSModulePath** .</span><span class="sxs-lookup"><span data-stu-id="66d5f-226">`Get-Module` gets modules in paths listed in the **PSModulePath** environment variable.</span></span> <span data-ttu-id="66d5f-227">Sem esse parâmetro, `Get-Module` obtém somente os módulos listados na variável de ambiente **PSModulePath** e que são carregados na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="66d5f-227">Without this parameter, `Get-Module` gets only the modules that are both listed in the **PSModulePath** environment variable, and that are loaded in the current session.</span></span> <span data-ttu-id="66d5f-228">O **ListAvailable** não retorna informações sobre os módulos que não são encontrados na variável de ambiente **PSModulePath** , mesmo que esses módulos estejam carregados na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="66d5f-228">**ListAvailable** does not return information about modules that are not found in the **PSModulePath** environment variable, even if those modules are loaded in the current session.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Available, PsSession, CimSession
Aliases:

Required: True (Available), False (PsSession, CimSession)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66d5f-229">-Name</span><span class="sxs-lookup"><span data-stu-id="66d5f-229">-Name</span></span>

<span data-ttu-id="66d5f-230">Especifica nomes ou padrões de nome dos módulos que esse cmdlet obtém.</span><span class="sxs-lookup"><span data-stu-id="66d5f-230">Specifies names or name patterns of modules that this cmdlet gets.</span></span> <span data-ttu-id="66d5f-231">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="66d5f-231">Wildcard characters are permitted.</span></span> <span data-ttu-id="66d5f-232">Você também pode canalizar os nomes para `Get-Module` .</span><span class="sxs-lookup"><span data-stu-id="66d5f-232">You can also pipe the names to `Get-Module`.</span></span> <span data-ttu-id="66d5f-233">Você não pode especificar o parâmetro **FullyQualifiedName** no mesmo comando que um parâmetro de **nome** .</span><span class="sxs-lookup"><span data-stu-id="66d5f-233">You cannot specify the **FullyQualifiedName** parameter in the same command as a **Name** parameter.</span></span>

<span data-ttu-id="66d5f-234">O **nome** não pode aceitar um GUID de módulo como um valor.</span><span class="sxs-lookup"><span data-stu-id="66d5f-234">**Name** cannot accept a module GUID as a value.</span></span>
<span data-ttu-id="66d5f-235">Para retornar módulos especificando um GUID, use **FullyQualifiedName** em vez disso.</span><span class="sxs-lookup"><span data-stu-id="66d5f-235">To return modules by specifying a GUID, use **FullyQualifiedName** instead.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="66d5f-236">-PSEdition</span><span class="sxs-lookup"><span data-stu-id="66d5f-236">-PSEdition</span></span>

<span data-ttu-id="66d5f-237">Obtém os módulos que dão suporte à edição especificada do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="66d5f-237">Gets the modules that support specified edition of PowerShell.</span></span>

<span data-ttu-id="66d5f-238">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="66d5f-238">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="66d5f-239">Desktop</span><span class="sxs-lookup"><span data-stu-id="66d5f-239">Desktop</span></span>
- <span data-ttu-id="66d5f-240">Núcleo</span><span class="sxs-lookup"><span data-stu-id="66d5f-240">Core</span></span>

<span data-ttu-id="66d5f-241">O cmdlet Get-Module verifica a propriedade **CompatiblePSEditions** do objeto **PSModuleInfo** para o valor especificado e retorna somente os módulos que o têm definido.</span><span class="sxs-lookup"><span data-stu-id="66d5f-241">The Get-Module cmdlet checks **CompatiblePSEditions** property of **PSModuleInfo** object for the specified value and returns only those modules that have it set.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="66d5f-242">**Desktop Edition:** criada no .NET Framework, fornece compatibilidade com scripts e módulos destinados a versões do PowerShell em execução em edições de volume completo do Windows, como Server Core e Windows Desktop.</span><span class="sxs-lookup"><span data-stu-id="66d5f-242">**Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.</span></span>
> - <span data-ttu-id="66d5f-243">**Core Edition:** criada no .NET Core, oferece compatibilidade com scripts e módulos destinados a versões do PowerShell executadas em edições de volume reduzido do Windows, como o Nano Server e Windows IoT.</span><span class="sxs-lookup"><span data-stu-id="66d5f-243">**Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.</span></span>

```yaml
Type: System.String
Parameter Sets: PsSession, Available
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66d5f-244">-PSSession</span><span class="sxs-lookup"><span data-stu-id="66d5f-244">-PSSession</span></span>

<span data-ttu-id="66d5f-245">Obtém os módulos na sessão do PowerShell gerenciada pelo usuário especificada ( **PSSession** ).</span><span class="sxs-lookup"><span data-stu-id="66d5f-245">Gets the modules in the specified user-managed PowerShell session ( **PSSession** ).</span></span> <span data-ttu-id="66d5f-246">Insira uma variável que contenha a sessão, um comando que obtém a sessão, como um `Get-PSSession` comando, ou um comando que cria a sessão, como um `New-PSSession` comando.</span><span class="sxs-lookup"><span data-stu-id="66d5f-246">Enter a variable that contains the session, a command that gets the session, such as a `Get-PSSession` command, or a command that creates the session, such as a `New-PSSession` command.</span></span>

<span data-ttu-id="66d5f-247">Quando a sessão estiver conectada a um computador remoto, você deverá especificar o parâmetro **listAvailable** .</span><span class="sxs-lookup"><span data-stu-id="66d5f-247">When the session is connected to a remote computer, you must specify the **ListAvailable** parameter.</span></span>

<span data-ttu-id="66d5f-248">Um `Get-Module` comando que usa o parâmetro **PSSession** é equivalente a usar o `Invoke-Command` cmdlet para executar um `Get-Module -ListAvailable` comando em uma **PSSession**.</span><span class="sxs-lookup"><span data-stu-id="66d5f-248">A `Get-Module` command that uses the **PSSession** parameter is equivalent to using the `Invoke-Command` cmdlet to run a `Get-Module -ListAvailable` command in a **PSSession**.</span></span>

<span data-ttu-id="66d5f-249">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="66d5f-249">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: PsSession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66d5f-250">-Atualizar</span><span class="sxs-lookup"><span data-stu-id="66d5f-250">-Refresh</span></span>

<span data-ttu-id="66d5f-251">Indica que esse cmdlet atualiza o cache de comandos instalados.</span><span class="sxs-lookup"><span data-stu-id="66d5f-251">Indicates that this cmdlet refreshes the cache of installed commands.</span></span> <span data-ttu-id="66d5f-252">O cache de comando é criado no início da sessão.</span><span class="sxs-lookup"><span data-stu-id="66d5f-252">The command cache is created when the session starts.</span></span> <span data-ttu-id="66d5f-253">Ele permite que o `Get-Command` cmdlet obtenha comandos de módulos que não são importados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="66d5f-253">It enables the `Get-Command` cmdlet to get commands from modules that are not imported into the session.</span></span>

<span data-ttu-id="66d5f-254">Este parâmetro é projetado para cenários de desenvolvimento e testes, nos quais o conteúdo dos módulos foi alterado desde o início da sessão.</span><span class="sxs-lookup"><span data-stu-id="66d5f-254">This parameter is designed for development and testing scenarios in which the contents of modules have changed since the session started.</span></span>

<span data-ttu-id="66d5f-255">Ao especificar o parâmetro de **atualização** em um comando, você deve especificar **listAvailable**.</span><span class="sxs-lookup"><span data-stu-id="66d5f-255">When you specify the **Refresh** parameter in a command, you must specify **ListAvailable**.</span></span>

<span data-ttu-id="66d5f-256">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="66d5f-256">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Available, PsSession, CimSession
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66d5f-257">-SkipEditionCheck</span><span class="sxs-lookup"><span data-stu-id="66d5f-257">-SkipEditionCheck</span></span>

<span data-ttu-id="66d5f-258">Ignora a verificação do `CompatiblePSEditions` campo.</span><span class="sxs-lookup"><span data-stu-id="66d5f-258">Skips the check of the `CompatiblePSEditions` field.</span></span>

<span data-ttu-id="66d5f-259">Por padrão, Get-Module omitirá módulos no `%windir%\System32\WindowsPowerShell\v1.0\Modules` diretório que não especificam `Core` no `CompatiblePSEditions` campo.</span><span class="sxs-lookup"><span data-stu-id="66d5f-259">By default, Get-Module will omit modules in the `%windir%\System32\WindowsPowerShell\v1.0\Modules` directory that do not specify `Core` in the `CompatiblePSEditions` field.</span></span> <span data-ttu-id="66d5f-260">Quando essa opção é definida, os módulos sem `Core` serão incluídos, de modo que os módulos no caminho do módulo do Windows PowerShell que são incompatíveis com o PowerShell Core serão retornados.</span><span class="sxs-lookup"><span data-stu-id="66d5f-260">When this switch is set, modules without `Core` will be included, so that modules under the Windows PowerShell module path that are incompatible with PowerShell Core will be returned.</span></span>

<span data-ttu-id="66d5f-261">No macOS e no Linux, esse parâmetro não faz nada.</span><span class="sxs-lookup"><span data-stu-id="66d5f-261">On macOS and Linux, this parameter does nothing.</span></span>

<span data-ttu-id="66d5f-262">Consulte [about_PowerShell_Editions](About/about_PowerShell_Editions.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="66d5f-262">See [about_PowerShell_Editions](About/about_PowerShell_Editions.md) for more information.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Available, PsSession, CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66d5f-263">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="66d5f-263">CommonParameters</span></span>

<span data-ttu-id="66d5f-264">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="66d5f-264">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="66d5f-265">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="66d5f-265">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="66d5f-266">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="66d5f-266">INPUTS</span></span>

### <span data-ttu-id="66d5f-267">System.String</span><span class="sxs-lookup"><span data-stu-id="66d5f-267">System.String</span></span>

<span data-ttu-id="66d5f-268">Você pode canalizar nomes de módulo para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="66d5f-268">You can pipe module names to this cmdlet.</span></span>

## <span data-ttu-id="66d5f-269">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="66d5f-269">OUTPUTS</span></span>

### <span data-ttu-id="66d5f-270">System. Management. Automation. PSModuleInfo</span><span class="sxs-lookup"><span data-stu-id="66d5f-270">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="66d5f-271">Esse cmdlet retorna objetos que representam módulos.</span><span class="sxs-lookup"><span data-stu-id="66d5f-271">This cmdlet returns objects that represent modules.</span></span>
<span data-ttu-id="66d5f-272">Quando você especifica o parâmetro **listAvailable** , `Get-Module` retorna um objeto **ModuleInfoGrouping** , que é um tipo de objeto **PSModuleInfo** que tem as mesmas propriedades e métodos.</span><span class="sxs-lookup"><span data-stu-id="66d5f-272">When you specify the **ListAvailable** parameter, `Get-Module` returns a **ModuleInfoGrouping** object, which is a type of **PSModuleInfo** object that has the same properties and methods.</span></span>

## <span data-ttu-id="66d5f-273">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="66d5f-273">NOTES</span></span>

- <span data-ttu-id="66d5f-274">A partir do Windows PowerShell 3,0, os comandos principais incluídos no PowerShell são empacotados em módulos.</span><span class="sxs-lookup"><span data-stu-id="66d5f-274">Beginning in Windows PowerShell 3.0, the core commands that are included in PowerShell are packaged in modules.</span></span> <span data-ttu-id="66d5f-275">A exceção é **Microsoft. PowerShell. Core** , que é um snap-in ( **PSSnapin** ).</span><span class="sxs-lookup"><span data-stu-id="66d5f-275">The exception is **Microsoft.PowerShell.Core** , which is a snap-in ( **PSSnapin** ).</span></span> <span data-ttu-id="66d5f-276">Por padrão, somente o snap-in **Microsoft.PowerShell.Core** é adicionado à sessão.</span><span class="sxs-lookup"><span data-stu-id="66d5f-276">By default, only the **Microsoft.PowerShell.Core** snap-in is added to the session.</span></span>
<span data-ttu-id="66d5f-277">Os módulos são importados automaticamente no primeiro uso e você pode usar o `Import-Module` cmdlet para importá-los.</span><span class="sxs-lookup"><span data-stu-id="66d5f-277">Modules are imported automatically on first use and you can use the `Import-Module` cmdlet to import them.</span></span>
- <span data-ttu-id="66d5f-278">A partir do Windows PowerShell 3,0, os comandos principais instalados com o PowerShell são empacotados em módulos.</span><span class="sxs-lookup"><span data-stu-id="66d5f-278">Starting in Windows PowerShell 3.0, the core commands that are installed with PowerShell are packaged in modules.</span></span> <span data-ttu-id="66d5f-279">No Windows PowerShell 2,0 e em programas de host que criam sessões de estilo mais antigo em versões posteriores do PowerShell, os comandos principais são empacotados em snap-ins ( **PSSnapins** ).</span><span class="sxs-lookup"><span data-stu-id="66d5f-279">In Windows PowerShell 2.0, and in host programs that create older-style sessions in later versions of PowerShell, the core commands are packaged in snap-ins ( **PSSnapins** ).</span></span> <span data-ttu-id="66d5f-280">A exceção é **Microsoft. PowerShell. Core** , que sempre é um snap-in.</span><span class="sxs-lookup"><span data-stu-id="66d5f-280">The exception is **Microsoft.PowerShell.Core** , which is always a snap-in.</span></span> <span data-ttu-id="66d5f-281">Além disso, as sessões remotas, como as iniciadas pelo `New-PSSession` cmdlet, são sessões de estilo mais antigo que incluem snap-ins de núcleo.</span><span class="sxs-lookup"><span data-stu-id="66d5f-281">Also, remote sessions, such as those started by the `New-PSSession` cmdlet, are older-style sessions that include core snap-ins.</span></span>

  <span data-ttu-id="66d5f-282">Para obter informações sobre o método **CreateDefault2** que cria sessões de estilo mais recente com módulos principais, consulte [método CreateDefault2](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2).</span><span class="sxs-lookup"><span data-stu-id="66d5f-282">For information about the **CreateDefault2** method that creates newer-style sessions with core modules, see [CreateDefault2 Method](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2).</span></span>

- <span data-ttu-id="66d5f-283">`Get-Module` Obtém apenas módulos em locais que são armazenados no valor da variável de ambiente **PSModulePath** ($env:P smodulepath).</span><span class="sxs-lookup"><span data-stu-id="66d5f-283">`Get-Module` only gets modules in locations that are stored in the value of the **PSModulePath** environment variable ($env:PSModulePath).</span></span> <span data-ttu-id="66d5f-284">Você pode usar o parâmetro **path** do `Import-Module` cmdlet para importar módulos em outros locais, mas não pode usar o `Get-Module` cmdlet para obtê-los.</span><span class="sxs-lookup"><span data-stu-id="66d5f-284">You can use the **Path** parameter of the `Import-Module` cmdlet to import modules in other locations, but you cannot use the `Get-Module` cmdlet to get them.</span></span>
- <span data-ttu-id="66d5f-285">Além disso, a partir do PowerShell 3,0, novas propriedades foram adicionadas ao objeto que `Get-Module` retorna para facilitar o aprendizado sobre os módulos, mesmo antes de serem importados.</span><span class="sxs-lookup"><span data-stu-id="66d5f-285">Also, starting in PowerShell 3.0, new properties have been added to the object that `Get-Module` returns that make it easier to learn about modules even before they are imported.</span></span> <span data-ttu-id="66d5f-286">Todas as propriedades são preenchidas antes da importação.</span><span class="sxs-lookup"><span data-stu-id="66d5f-286">All properties are populated before importing.</span></span> <span data-ttu-id="66d5f-287">Isso inclui as propriedades **ExportedCommands** , **ExportedCmdlets** e **ExportedFunctions** que listam os comandos que o módulo exporta.</span><span class="sxs-lookup"><span data-stu-id="66d5f-287">These include the **ExportedCommands** , **ExportedCmdlets** and **ExportedFunctions** properties that list the commands that the module exports.</span></span>
- <span data-ttu-id="66d5f-288">O parâmetro **listAvailable** obtém apenas módulos bem formados, ou seja, pastas que contêm pelo menos um arquivo cujo nome de base é o mesmo que o nome da pasta do módulo.</span><span class="sxs-lookup"><span data-stu-id="66d5f-288">The **ListAvailable** parameter gets only well-formed modules, that is, folders that contain at least one file whose base name is the same as the name of the module folder.</span></span> <span data-ttu-id="66d5f-289">O nome base é o nome sem a extensão de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="66d5f-289">The base name is the name without the file name extension.</span></span> <span data-ttu-id="66d5f-290">As pastas que contêm arquivos com nomes diferentes são consideradas contêineres, mas não módulos.</span><span class="sxs-lookup"><span data-stu-id="66d5f-290">Folders that contain files that have different names are considered to be containers, but not modules.</span></span>

  <span data-ttu-id="66d5f-291">Para obter os módulos que são implementados como arquivos. dll, mas não são colocados em uma pasta de módulo, especifique o **listAvailable** e **todos os** parâmetros.</span><span class="sxs-lookup"><span data-stu-id="66d5f-291">To get modules that are implemented as .dll files, but are not enclosed in a module folder, specify both the **ListAvailable** and **All** parameters.</span></span>

- <span data-ttu-id="66d5f-292">Para usar o recurso de sessão CIM, o computador remoto deve ter comunicação remota do WS-Management e a Instrumentação de Gerenciamento do Windows (WMI), que é a implementação da Microsoft do padrão CIM.</span><span class="sxs-lookup"><span data-stu-id="66d5f-292">To use the CIM session feature, the remote computer must have WS-Management remoting and Windows Management Instrumentation (WMI), which is the Microsoft implementation of the Common Information Model (CIM) standard.</span></span> <span data-ttu-id="66d5f-293">O computador também deve ter o provedor WMI de descoberta do módulo ou um provedor WMI alternativo com os mesmos recursos básicos.</span><span class="sxs-lookup"><span data-stu-id="66d5f-293">The computer must also have the Module Discovery WMI provider or an alternate WMI provider that has the same basic features.</span></span>

  <span data-ttu-id="66d5f-294">Você pode usar o recurso de sessão CIM em computadores que não estão executando o sistema operacional Windows e em computadores com Windows que têm o PowerShell, mas que não têm a comunicação remota do PowerShell habilitada.</span><span class="sxs-lookup"><span data-stu-id="66d5f-294">You can use the CIM session feature on computers that are not running the Windows operating system and on Windows computers that have PowerShell, but do not have PowerShell remoting enabled.</span></span>

  <span data-ttu-id="66d5f-295">Você também pode usar os parâmetros CIM para obter módulos CIM de computadores que têm a comunicação remota do PowerShell habilitada.</span><span class="sxs-lookup"><span data-stu-id="66d5f-295">You can also use the CIM parameters to get CIM modules from computers that have PowerShell remoting enabled.</span></span> <span data-ttu-id="66d5f-296">Isso inclui o computador local.</span><span class="sxs-lookup"><span data-stu-id="66d5f-296">This includes the local computer.</span></span>
<span data-ttu-id="66d5f-297">Quando você cria uma sessão CIM no computador local, o PowerShell usa DCOM, em vez de WMI, para criar a sessão.</span><span class="sxs-lookup"><span data-stu-id="66d5f-297">When you create a CIM session on the local computer, PowerShell uses DCOM, instead of WMI, to create the session.</span></span>

## <span data-ttu-id="66d5f-298">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="66d5f-298">RELATED LINKS</span></span>

[<span data-ttu-id="66d5f-299">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="66d5f-299">Get-CimSession</span></span>](../CimCmdlets/Get-CimSession.md)

[<span data-ttu-id="66d5f-300">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="66d5f-300">New-CimSession</span></span>](../CimCmdlets/New-CimSession.md)

[<span data-ttu-id="66d5f-301">about_Modules</span><span class="sxs-lookup"><span data-stu-id="66d5f-301">about_Modules</span></span>](About/about_Modules.md)

[<span data-ttu-id="66d5f-302">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="66d5f-302">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="66d5f-303">Import-Module</span><span class="sxs-lookup"><span data-stu-id="66d5f-303">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="66d5f-304">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="66d5f-304">Import-PSSession</span></span>](../Microsoft.PowerShell.Utility/Import-PSSession.md)

[<span data-ttu-id="66d5f-305">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="66d5f-305">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="66d5f-306">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="66d5f-306">Remove-Module</span></span>](Remove-Module.md)

[<span data-ttu-id="66d5f-307">about_PowerShell_Editions</span><span class="sxs-lookup"><span data-stu-id="66d5f-307">about_PowerShell_Editions</span></span>](About/about_PowerShell_Editions.md)
