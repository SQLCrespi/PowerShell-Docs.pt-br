---
description: Impede que um script seja executado sem os elementos necessários.
Locale: en-US
ms.date: 12/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_requires?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Requires
ms.openlocfilehash: d340de615923437bb3e29c1984ef8849fe03a40e
ms.sourcegitcommit: 9a86cac80402d8193147058d4ba50e07b26059dd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "99603341"
---
# <a name="about-requires"></a><span data-ttu-id="4a951-103">Sobre o requer</span><span class="sxs-lookup"><span data-stu-id="4a951-103">About Requires</span></span>

## <a name="short-description"></a><span data-ttu-id="4a951-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="4a951-104">Short description</span></span>
<span data-ttu-id="4a951-105">Impede que um script seja executado sem os elementos necessários.</span><span class="sxs-lookup"><span data-stu-id="4a951-105">Prevents a script from running without the required elements.</span></span>

## <a name="long-description"></a><span data-ttu-id="4a951-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="4a951-106">Long description</span></span>

<span data-ttu-id="4a951-107">A `#Requires` instrução impede que um script seja executado, a menos que a versão do PowerShell, os módulos (e a versão) ou snap-ins (e a versão) e os pré-requisitos de edição sejam atendidos.</span><span class="sxs-lookup"><span data-stu-id="4a951-107">The `#Requires` statement prevents a script from running unless the PowerShell version, modules (and version), or snap-ins (and version), and edition prerequisites are met.</span></span> <span data-ttu-id="4a951-108">Se os pré-requisitos não forem atendidos, o PowerShell não executará o script.</span><span class="sxs-lookup"><span data-stu-id="4a951-108">If the prerequisites aren't met, PowerShell doesn't run the script.</span></span>

### <a name="syntax"></a><span data-ttu-id="4a951-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="4a951-109">Syntax</span></span>

```
#Requires -Version <N>[.<n>]
#Requires -PSSnapin <PSSnapin-Name> [-Version <N>[.<n>]]
#Requires -Modules { <Module-Name> | <Hashtable> }
#Requires -PSEdition <PSEdition-Name>
#Requires -ShellId <ShellId> -PSSnapin <PSSnapin-Name> [-Version <N>[.<n>]]
#Requires -RunAsAdministrator
```

<span data-ttu-id="4a951-110">Para obter mais informações sobre a sintaxe, consulte [ScriptRequirements](/dotnet/api/system.management.automation.language.scriptrequirements).</span><span class="sxs-lookup"><span data-stu-id="4a951-110">For more information about the syntax, see [ScriptRequirements](/dotnet/api/system.management.automation.language.scriptrequirements).</span></span>

### <a name="rules-for-use"></a><span data-ttu-id="4a951-111">Regras para uso</span><span class="sxs-lookup"><span data-stu-id="4a951-111">Rules for use</span></span>

<span data-ttu-id="4a951-112">Um script pode incluir mais de uma `#Requires` instrução.</span><span class="sxs-lookup"><span data-stu-id="4a951-112">A script can include more than one `#Requires` statement.</span></span> <span data-ttu-id="4a951-113">As `#Requires` instruções podem aparecer em qualquer linha em um script.</span><span class="sxs-lookup"><span data-stu-id="4a951-113">The `#Requires` statements can appear on any line in a script.</span></span>

<span data-ttu-id="4a951-114">Colocar uma `#Requires` instrução dentro de uma função não limita seu escopo.</span><span class="sxs-lookup"><span data-stu-id="4a951-114">Placing a `#Requires` statement inside a function does NOT limit its scope.</span></span> <span data-ttu-id="4a951-115">Todas as `#Requires` instruções são sempre aplicadas globalmente e devem ser atendidas, antes que o script possa ser executado.</span><span class="sxs-lookup"><span data-stu-id="4a951-115">All `#Requires` statements are always applied globally, and must be met, before the script can execute.</span></span>

> [!WARNING]
> <span data-ttu-id="4a951-116">Embora uma `#Requires` instrução possa aparecer em qualquer linha em um script, sua posição em um script não afeta a sequência de seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4a951-116">Even though a `#Requires` statement can appear on any line in a script, its position in a script does not affect the sequence of its application.</span></span> <span data-ttu-id="4a951-117">O estado global que a `#Requires` instrução apresenta deve ser atendido antes da execução do script.</span><span class="sxs-lookup"><span data-stu-id="4a951-117">The global state the `#Requires` statement presents must be met before script execution.</span></span>

<span data-ttu-id="4a951-118">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="4a951-118">Example:</span></span>

```powershell
Get-Module AzureRM.Netcore | Remove-Module
#Requires -Modules AzureRM.Netcore
```

<span data-ttu-id="4a951-119">Você pode imaginar que o código acima não deve ser executado porque o módulo necessário foi removido antes da `#Requires` instrução.</span><span class="sxs-lookup"><span data-stu-id="4a951-119">You might think that the above code shouldn't run because the required module was removed before the `#Requires` statement.</span></span> <span data-ttu-id="4a951-120">No entanto, o `#Requires` estado precisava ser atendido antes que o script pudesse ser executado.</span><span class="sxs-lookup"><span data-stu-id="4a951-120">However, the `#Requires` state had to be met before the script could even execute.</span></span> <span data-ttu-id="4a951-121">Em seguida, a primeira linha do script invalidará o estado necessário.</span><span class="sxs-lookup"><span data-stu-id="4a951-121">Then the first line of the script invalidated the required state.</span></span>

### <a name="parameters"></a><span data-ttu-id="4a951-122">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="4a951-122">Parameters</span></span>

#### <a name="-assembly-assembly-path--net-assembly-specification"></a><span data-ttu-id="4a951-123">-Assembly \<Assembly path> |\<.NET assembly specification></span><span class="sxs-lookup"><span data-stu-id="4a951-123">-Assembly \<Assembly path> | \<.NET assembly specification></span></span>

> [!IMPORTANT]
> <span data-ttu-id="4a951-124">A `-Assembly` sintaxe foi preterida.</span><span class="sxs-lookup"><span data-stu-id="4a951-124">The `-Assembly` syntax is deprecated.</span></span> <span data-ttu-id="4a951-125">Ele não serve nenhuma função.</span><span class="sxs-lookup"><span data-stu-id="4a951-125">It serves no function.</span></span> <span data-ttu-id="4a951-126">A sintaxe foi adicionada no PowerShell 5,1, mas o código de suporte nunca foi implementado.</span><span class="sxs-lookup"><span data-stu-id="4a951-126">The syntax was added in PowerShell 5.1 but the supporting code was never implemented.</span></span> <span data-ttu-id="4a951-127">A sintaxe ainda é aceita para compatibilidade com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="4a951-127">The syntax is still accepted for backward compatibility.</span></span>

<span data-ttu-id="4a951-128">Especifica o caminho para o arquivo DLL do assembly ou um nome de assembly .NET.</span><span class="sxs-lookup"><span data-stu-id="4a951-128">Specifies the path to the assembly DLL file or a .NET assembly name.</span></span> <span data-ttu-id="4a951-129">O parâmetro **assembly** foi introduzido no PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="4a951-129">The **Assembly** parameter was introduced in PowerShell 5.0.</span></span> <span data-ttu-id="4a951-130">Para obter mais informações sobre assemblies .NET, consulte [nomes de assembly](/dotnet/standard/assembly/names).</span><span class="sxs-lookup"><span data-stu-id="4a951-130">For more information about .NET assemblies, see [Assembly names](/dotnet/standard/assembly/names).</span></span>

<span data-ttu-id="4a951-131">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4a951-131">For example:</span></span>

```
#Requires -Assembly path\to\foo.dll
```

```
#Requires -Assembly "System.Management.Automation, Version=3.0.0.0,
  Culture=neutral, PublicKeyToken=31bf3856ad364e35"
```

#### <a name="-version-nn"></a><span data-ttu-id="4a951-132">-Versão \<N\> [. \<n\> ]</span><span class="sxs-lookup"><span data-stu-id="4a951-132">-Version \<N\>[.\<n\>]</span></span>

<span data-ttu-id="4a951-133">Especifica a versão mínima do PowerShell que o script requer.</span><span class="sxs-lookup"><span data-stu-id="4a951-133">Specifies the minimum version of PowerShell that the script requires.</span></span> <span data-ttu-id="4a951-134">Insira um número de versão principal e um número de versão secundária opcional.</span><span class="sxs-lookup"><span data-stu-id="4a951-134">Enter a major version number and optional minor version number.</span></span>

<span data-ttu-id="4a951-135">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4a951-135">For example:</span></span>

```powershell
#Requires -Version 6.0
```

#### <a name="-pssnapin-pssnapin-name--version-nn"></a><span data-ttu-id="4a951-136">-PSSnapin \<PSSnapin-Name\> [-Version \<N\> [. \<n\> ]]</span><span class="sxs-lookup"><span data-stu-id="4a951-136">-PSSnapin \<PSSnapin-Name\> [-Version \<N\>[.\<n\>]]</span></span>

<span data-ttu-id="4a951-137">Especifica um snap-in do PowerShell que o script requer.</span><span class="sxs-lookup"><span data-stu-id="4a951-137">Specifies a PowerShell snap-in that the script requires.</span></span> <span data-ttu-id="4a951-138">Insira o nome do snap-in e um número de versão opcional.</span><span class="sxs-lookup"><span data-stu-id="4a951-138">Enter the snap-in name and an optional version number.</span></span>

<span data-ttu-id="4a951-139">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4a951-139">For example:</span></span>

```powershell
#Requires -PSSnapin DiskSnapin -Version 1.2
```

#### <a name="-modules-module-name--hashtable"></a><span data-ttu-id="4a951-140">-Módulos \<Module-Name\> |\<Hashtable\></span><span class="sxs-lookup"><span data-stu-id="4a951-140">-Modules \<Module-Name\> | \<Hashtable\></span></span>

<span data-ttu-id="4a951-141">Especifica os módulos do PowerShell que o script requer.</span><span class="sxs-lookup"><span data-stu-id="4a951-141">Specifies PowerShell modules that the script requires.</span></span> <span data-ttu-id="4a951-142">Insira o nome do módulo e um número de versão opcional.</span><span class="sxs-lookup"><span data-stu-id="4a951-142">Enter the module name and an optional version number.</span></span>

<span data-ttu-id="4a951-143">Se os módulos necessários não estiverem na sessão atual, o PowerShell os importará.</span><span class="sxs-lookup"><span data-stu-id="4a951-143">If the required modules aren't in the current session, PowerShell imports them.</span></span>
<span data-ttu-id="4a951-144">Se os módulos não puderem ser importados, o PowerShell lançará um erro de encerramento.</span><span class="sxs-lookup"><span data-stu-id="4a951-144">If the modules can't be imported, PowerShell throws a terminating error.</span></span>

<span data-ttu-id="4a951-145">Para cada módulo, digite o nome do módulo ( \<String\> ) ou uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="4a951-145">For each module, type the module name (\<String\>) or a hash table.</span></span> <span data-ttu-id="4a951-146">O valor pode ser uma combinação de cadeias de caracteres e tabelas de hash.</span><span class="sxs-lookup"><span data-stu-id="4a951-146">The value can be a combination of strings and hash tables.</span></span> <span data-ttu-id="4a951-147">A tabela de hash tem as seguintes chaves.</span><span class="sxs-lookup"><span data-stu-id="4a951-147">The hash table has the following keys.</span></span>

- <span data-ttu-id="4a951-148">`ModuleName` - **Necessário** Especifica o nome do módulo.</span><span class="sxs-lookup"><span data-stu-id="4a951-148">`ModuleName` - **Required** Specifies the module name.</span></span>
- <span data-ttu-id="4a951-149">`GUID` - **Opcional** Especifica o GUID do módulo.</span><span class="sxs-lookup"><span data-stu-id="4a951-149">`GUID` - **Optional** Specifies the GUID of the module.</span></span>
- <span data-ttu-id="4a951-150">Também é **necessário** especificar uma das três chaves abaixo.</span><span class="sxs-lookup"><span data-stu-id="4a951-150">It's also **Required** to specify one of the three below keys.</span></span> <span data-ttu-id="4a951-151">Essas chaves não podem ser usadas juntas.</span><span class="sxs-lookup"><span data-stu-id="4a951-151">These keys can't be used together.</span></span>
  - <span data-ttu-id="4a951-152">`ModuleVersion` -Especifica uma versão mínima aceitável do módulo.</span><span class="sxs-lookup"><span data-stu-id="4a951-152">`ModuleVersion` - Specifies a minimum acceptable version of the module.</span></span>
  - <span data-ttu-id="4a951-153">`RequiredVersion` -Especifica uma versão exata e necessária do módulo.</span><span class="sxs-lookup"><span data-stu-id="4a951-153">`RequiredVersion` - Specifies an exact, required version of the module.</span></span>
  - <span data-ttu-id="4a951-154">`MaximumVersion` -Especifica a versão máxima aceitável do módulo.</span><span class="sxs-lookup"><span data-stu-id="4a951-154">`MaximumVersion` - Specifies the maximum acceptable version of the module.</span></span>

> [!NOTE]
> <span data-ttu-id="4a951-155">`RequiredVersion` foi adicionado no Windows PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="4a951-155">`RequiredVersion` was added in Windows PowerShell 5.0.</span></span>
> <span data-ttu-id="4a951-156">`MaximumVersion` foi adicionado no Windows PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="4a951-156">`MaximumVersion` was added in Windows PowerShell 5.1.</span></span>

<span data-ttu-id="4a951-157">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4a951-157">For example:</span></span>

<span data-ttu-id="4a951-158">Exigir que `AzureRM.Netcore` (versão `0.12.0` ou superior) esteja instalado.</span><span class="sxs-lookup"><span data-stu-id="4a951-158">Require that `AzureRM.Netcore` (version `0.12.0` or greater) is installed.</span></span>

```powershell
#Requires -Modules @{ ModuleName="AzureRM.Netcore"; ModuleVersion="0.12.0" }
```

<span data-ttu-id="4a951-159">Exigir que `AzureRM.Netcore` (**apenas** a versão `0.12.0` ) esteja instalado.</span><span class="sxs-lookup"><span data-stu-id="4a951-159">Require that `AzureRM.Netcore` (**only** version `0.12.0`) is installed.</span></span>

```powershell
#Requires -Modules @{ ModuleName="AzureRM.Netcore"; RequiredVersion="0.12.0" }
```

<span data-ttu-id="4a951-160">Requer que `AzureRM.Netcore` (versão `0.12.0` ou menos) esteja instalado.</span><span class="sxs-lookup"><span data-stu-id="4a951-160">Requires that `AzureRM.Netcore` (version `0.12.0` or lesser) is installed.</span></span>

```powershell
#Requires -Modules @{ ModuleName="AzureRM.Netcore"; MaximumVersion="0.12.0" }
```

<span data-ttu-id="4a951-161">Exigir que qualquer versão do `AzureRM.Netcore` e do `PowerShellGet` esteja instalada.</span><span class="sxs-lookup"><span data-stu-id="4a951-161">Require that any version of `AzureRM.Netcore` and `PowerShellGet` is installed.</span></span>

```powershell
#Requires -Modules AzureRM.Netcore, PowerShellGet
```

<span data-ttu-id="4a951-162">Ao usar a `RequiredVersion` chave, verifique se a cadeia de caracteres de versão corresponde exatamente à cadeia de caracteres de versão que você precisa.</span><span class="sxs-lookup"><span data-stu-id="4a951-162">When using the `RequiredVersion` key, ensure your version string exactly matches the version string you require.</span></span>

```powershell
Get-Module AzureRM.Netcore -ListAvailable
```

```Output
    Directory: /home/azureuser/.local/share/powershell/Modules

ModuleType Version Name            PSEdition ExportedCommands
---------- ------- ----            --------- ----------------
Script     0.12.0  AzureRM.Netcore Core
```

<span data-ttu-id="4a951-163">O exemplo a seguir falha porque **0,12** não corresponde exatamente a **0.12.0**.</span><span class="sxs-lookup"><span data-stu-id="4a951-163">The following example fails because **0.12** doesn't exactly match **0.12.0**.</span></span>

```powershell
#Requires -Modules @{ ModuleName="AzureRM.Netcore"; RequiredVersion="0.12" }
```

#### <a name="-psedition-psedition-name"></a><span data-ttu-id="4a951-164">-PSEdition \<PSEdition-Name\></span><span class="sxs-lookup"><span data-stu-id="4a951-164">-PSEdition \<PSEdition-Name\></span></span>

<span data-ttu-id="4a951-165">Especifica uma edição do PowerShell que o script requer.</span><span class="sxs-lookup"><span data-stu-id="4a951-165">Specifies a PowerShell edition that the script requires.</span></span> <span data-ttu-id="4a951-166">Os valores válidos são **Core** para PowerShell Core e **Desktop** para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4a951-166">Valid values are **Core** for PowerShell Core and **Desktop** for Windows PowerShell.</span></span>

<span data-ttu-id="4a951-167">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4a951-167">For example:</span></span>

```powershell
#Requires -PSEdition Core
```

#### <a name="-shellid"></a><span data-ttu-id="4a951-168">-ShellId</span><span class="sxs-lookup"><span data-stu-id="4a951-168">-ShellId</span></span>

<span data-ttu-id="4a951-169">Especifica o shell que o script requer.</span><span class="sxs-lookup"><span data-stu-id="4a951-169">Specifies the shell that the script requires.</span></span> <span data-ttu-id="4a951-170">Insira a ID do Shell.</span><span class="sxs-lookup"><span data-stu-id="4a951-170">Enter the shell ID.</span></span> <span data-ttu-id="4a951-171">Se você usar o parâmetro **ShellId** , também deverá incluir o parâmetro **PSSnapin** .</span><span class="sxs-lookup"><span data-stu-id="4a951-171">If you use the **ShellId** parameter, you must also include the **PSSnapin** parameter.</span></span>
<span data-ttu-id="4a951-172">Você pode encontrar a **ShellId** atual consultando a `$ShellId` variável automática.</span><span class="sxs-lookup"><span data-stu-id="4a951-172">You can find the current **ShellId** by querying the `$ShellId` automatic variable.</span></span>

<span data-ttu-id="4a951-173">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4a951-173">For example:</span></span>

```powershell
#Requires -ShellId MyLocalShell -PSSnapin Microsoft.PowerShell.Core
```

> [!NOTE]
> <span data-ttu-id="4a951-174">Este parâmetro destina-se ao uso em mini-shells, que foram preteridos.</span><span class="sxs-lookup"><span data-stu-id="4a951-174">This parameter is intended for use in mini-shells, which have been deprecated.</span></span>

#### <a name="-runasadministrator"></a><span data-ttu-id="4a951-175">-RunAsAdministrator</span><span class="sxs-lookup"><span data-stu-id="4a951-175">-RunAsAdministrator</span></span>

<span data-ttu-id="4a951-176">Quando esse parâmetro de opção é adicionado à sua `#Requires` instrução, ele especifica que a sessão do PowerShell na qual você está executando o script deve ser iniciada com direitos de usuário elevados.</span><span class="sxs-lookup"><span data-stu-id="4a951-176">When this switch parameter is added to your `#Requires` statement, it specifies that the PowerShell session in which you're running the script must be started with elevated user rights.</span></span> <span data-ttu-id="4a951-177">O parâmetro **RunAsAdministrator** é ignorado em um sistema operacional não Windows.</span><span class="sxs-lookup"><span data-stu-id="4a951-177">The **RunAsAdministrator** parameter is ignored on a non-Windows operating system.</span></span> <span data-ttu-id="4a951-178">O parâmetro **RunAsAdministrator** foi introduzido no PowerShell 4,0.</span><span class="sxs-lookup"><span data-stu-id="4a951-178">The **RunAsAdministrator** parameter was introduced in PowerShell 4.0.</span></span>

<span data-ttu-id="4a951-179">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4a951-179">For example:</span></span>

```powershell
#Requires -RunAsAdministrator
```

### <a name="examples"></a><span data-ttu-id="4a951-180">Exemplos</span><span class="sxs-lookup"><span data-stu-id="4a951-180">Examples</span></span>

<span data-ttu-id="4a951-181">O script a seguir tem duas `#Requires` instruções.</span><span class="sxs-lookup"><span data-stu-id="4a951-181">The following script has two `#Requires` statements.</span></span> <span data-ttu-id="4a951-182">Se os requisitos especificados em ambas as instruções não forem atendidos, o script não é executado.</span><span class="sxs-lookup"><span data-stu-id="4a951-182">If the requirements specified in both statements aren't met, the script doesn't run.</span></span> <span data-ttu-id="4a951-183">Cada `#Requires` instrução deve ser o primeiro item em uma linha:</span><span class="sxs-lookup"><span data-stu-id="4a951-183">Each `#Requires` statement must be the first item on a line:</span></span>

```powershell
#Requires -Modules AzureRM.Netcore
#Requires -Version 6.0
Param
(
    [parameter(Mandatory=$true)]
    [String[]]
    $Path
)
...
```

## <a name="see-also"></a><span data-ttu-id="4a951-184">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4a951-184">See also</span></span>

[<span data-ttu-id="4a951-185">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="4a951-185">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="4a951-186">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="4a951-186">about_Language_Keywords</span></span>](about_Language_Keywords.md)
