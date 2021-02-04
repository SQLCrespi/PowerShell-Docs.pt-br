---
description: Impede que um script seja executado sem os elementos necessários.
Locale: en-US
ms.date: 12/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_requires?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Requires
ms.openlocfilehash: f8ff922fcf8deb710008bbd9bab619f137d6c831
ms.sourcegitcommit: 9a86cac80402d8193147058d4ba50e07b26059dd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "97490696"
---
# <a name="about-requires"></a><span data-ttu-id="68d72-103">Sobre o requer</span><span class="sxs-lookup"><span data-stu-id="68d72-103">About Requires</span></span>

## <a name="short-description"></a><span data-ttu-id="68d72-104">Descrição breve</span><span class="sxs-lookup"><span data-stu-id="68d72-104">Short description</span></span>
<span data-ttu-id="68d72-105">Impede que um script seja executado sem os elementos necessários.</span><span class="sxs-lookup"><span data-stu-id="68d72-105">Prevents a script from running without the required elements.</span></span>

## <a name="long-description"></a><span data-ttu-id="68d72-106">Descrição longa</span><span class="sxs-lookup"><span data-stu-id="68d72-106">Long description</span></span>

<span data-ttu-id="68d72-107">A `#Requires` instrução impede que um script seja executado, a menos que a versão do PowerShell, os módulos (e a versão) ou snap-ins (e a versão) e os pré-requisitos de edição sejam atendidos.</span><span class="sxs-lookup"><span data-stu-id="68d72-107">The `#Requires` statement prevents a script from running unless the PowerShell version, modules (and version), or snap-ins (and version), and edition prerequisites are met.</span></span> <span data-ttu-id="68d72-108">Se os pré-requisitos não forem atendidos, o PowerShell não executará o script.</span><span class="sxs-lookup"><span data-stu-id="68d72-108">If the prerequisites aren't met, PowerShell doesn't run the script.</span></span>

### <a name="syntax"></a><span data-ttu-id="68d72-109">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="68d72-109">Syntax</span></span>

```
#Requires -Version <N>[.<n>]
#Requires -PSSnapin <PSSnapin-Name> [-Version <N>[.<n>]]
#Requires -Modules { <Module-Name> | <Hashtable> }
#Requires -PSEdition <PSEdition-Name>
#Requires -ShellId <ShellId> -PSSnapin <PSSnapin-Name> [-Version <N>[.<n>]]
#Requires -RunAsAdministrator
```

<span data-ttu-id="68d72-110">Para obter mais informações sobre a sintaxe, consulte [ScriptRequirements](/dotnet/api/system.management.automation.language.scriptrequirements).</span><span class="sxs-lookup"><span data-stu-id="68d72-110">For more information about the syntax, see [ScriptRequirements](/dotnet/api/system.management.automation.language.scriptrequirements).</span></span>

### <a name="rules-for-use"></a><span data-ttu-id="68d72-111">Regras para uso</span><span class="sxs-lookup"><span data-stu-id="68d72-111">Rules for use</span></span>

<span data-ttu-id="68d72-112">Um script pode incluir mais de uma `#Requires` instrução.</span><span class="sxs-lookup"><span data-stu-id="68d72-112">A script can include more than one `#Requires` statement.</span></span> <span data-ttu-id="68d72-113">As `#Requires` instruções podem aparecer em qualquer linha em um script.</span><span class="sxs-lookup"><span data-stu-id="68d72-113">The `#Requires` statements can appear on any line in a script.</span></span>

<span data-ttu-id="68d72-114">Colocar uma `#Requires` instrução dentro de uma função não limita seu escopo.</span><span class="sxs-lookup"><span data-stu-id="68d72-114">Placing a `#Requires` statement inside a function does NOT limit its scope.</span></span> <span data-ttu-id="68d72-115">Todas as `#Requires` instruções são sempre aplicadas globalmente e devem ser atendidas, antes que o script possa ser executado.</span><span class="sxs-lookup"><span data-stu-id="68d72-115">All `#Requires` statements are always applied globally, and must be met, before the script can execute.</span></span>

> [!WARNING]
> <span data-ttu-id="68d72-116">Embora uma `#Requires` instrução possa aparecer em qualquer linha em um script, sua posição em um script não afeta a sequência de seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="68d72-116">Even though a `#Requires` statement can appear on any line in a script, its position in a script does not affect the sequence of its application.</span></span> <span data-ttu-id="68d72-117">O estado global que a `#Requires` instrução apresenta deve ser atendido antes da execução do script.</span><span class="sxs-lookup"><span data-stu-id="68d72-117">The global state the `#Requires` statement presents must be met before script execution.</span></span>

<span data-ttu-id="68d72-118">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="68d72-118">Example:</span></span>

```powershell
Get-Module AzureRM.Netcore | Remove-Module
#Requires -Modules AzureRM.Netcore
```

<span data-ttu-id="68d72-119">Você pode imaginar que o código acima não deve ser executado porque o módulo necessário foi removido antes da `#Requires` instrução.</span><span class="sxs-lookup"><span data-stu-id="68d72-119">You might think that the above code shouldn't run because the required module was removed before the `#Requires` statement.</span></span> <span data-ttu-id="68d72-120">No entanto, o `#Requires` estado precisava ser atendido antes que o script pudesse ser executado.</span><span class="sxs-lookup"><span data-stu-id="68d72-120">However, the `#Requires` state had to be met before the script could even execute.</span></span> <span data-ttu-id="68d72-121">Em seguida, a primeira linha do script invalidará o estado necessário.</span><span class="sxs-lookup"><span data-stu-id="68d72-121">Then the first line of the script invalidated the required state.</span></span>

### <a name="parameters"></a><span data-ttu-id="68d72-122">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="68d72-122">Parameters</span></span>

#### <a name="-assembly-assembly-path--net-assembly-specification"></a><span data-ttu-id="68d72-123">-Assembly \<Assembly path> |\<.NET assembly specification></span><span class="sxs-lookup"><span data-stu-id="68d72-123">-Assembly \<Assembly path> | \<.NET assembly specification></span></span>

> [!IMPORTANT]
> <span data-ttu-id="68d72-124">A `-Assembly` sintaxe foi preterida.</span><span class="sxs-lookup"><span data-stu-id="68d72-124">The `-Assembly` syntax is deprecated.</span></span> <span data-ttu-id="68d72-125">Ele não serve nenhuma função.</span><span class="sxs-lookup"><span data-stu-id="68d72-125">It serves no function.</span></span> <span data-ttu-id="68d72-126">A sintaxe foi adicionada no PowerShell 5,1, mas o código de suporte nunca foi implementado.</span><span class="sxs-lookup"><span data-stu-id="68d72-126">The syntax was added in PowerShell 5.1 but the supporting code was never implemented.</span></span> <span data-ttu-id="68d72-127">A sintaxe ainda é aceita para compatibilidade com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="68d72-127">The syntax is still accepted for backward compatibility.</span></span>

<span data-ttu-id="68d72-128">Especifica o caminho para o arquivo DLL do assembly ou um nome de assembly .NET.</span><span class="sxs-lookup"><span data-stu-id="68d72-128">Specifies the path to the assembly DLL file or a .NET assembly name.</span></span> <span data-ttu-id="68d72-129">O parâmetro **assembly** foi introduzido no PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="68d72-129">The **Assembly** parameter was introduced in PowerShell 5.0.</span></span> <span data-ttu-id="68d72-130">Para obter mais informações sobre assemblies .NET, consulte [nomes de assembly](/dotnet/standard/assembly/names).</span><span class="sxs-lookup"><span data-stu-id="68d72-130">For more information about .NET assemblies, see [Assembly names](/dotnet/standard/assembly/names).</span></span>

<span data-ttu-id="68d72-131">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="68d72-131">For example:</span></span>

```
#Requires -Assembly path\to\foo.dll
```

```
#Requires -Assembly "System.Management.Automation, Version=3.0.0.0,
  Culture=neutral, PublicKeyToken=31bf3856ad364e35"
```

#### <a name="-version-nn"></a><span data-ttu-id="68d72-132">-Versão \<N\> [. \<n\> ]</span><span class="sxs-lookup"><span data-stu-id="68d72-132">-Version \<N\>[.\<n\>]</span></span>

<span data-ttu-id="68d72-133">Especifica a versão mínima do PowerShell que o script requer.</span><span class="sxs-lookup"><span data-stu-id="68d72-133">Specifies the minimum version of PowerShell that the script requires.</span></span> <span data-ttu-id="68d72-134">Insira um número de versão principal e um número de versão secundária opcional.</span><span class="sxs-lookup"><span data-stu-id="68d72-134">Enter a major version number and optional minor version number.</span></span>

<span data-ttu-id="68d72-135">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="68d72-135">For example:</span></span>

```powershell
#Requires -Version 5.1
```

#### <a name="-pssnapin-pssnapin-name--version-nn"></a><span data-ttu-id="68d72-136">-PSSnapin \<PSSnapin-Name\> [-Version \<N\> [. \<n\> ]]</span><span class="sxs-lookup"><span data-stu-id="68d72-136">-PSSnapin \<PSSnapin-Name\> [-Version \<N\>[.\<n\>]]</span></span>

<span data-ttu-id="68d72-137">Especifica um snap-in do PowerShell que o script requer.</span><span class="sxs-lookup"><span data-stu-id="68d72-137">Specifies a PowerShell snap-in that the script requires.</span></span> <span data-ttu-id="68d72-138">Insira o nome do snap-in e um número de versão opcional.</span><span class="sxs-lookup"><span data-stu-id="68d72-138">Enter the snap-in name and an optional version number.</span></span>

<span data-ttu-id="68d72-139">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="68d72-139">For example:</span></span>

```powershell
#Requires -PSSnapin DiskSnapin -Version 1.2
```

#### <a name="-modules-module-name--hashtable"></a><span data-ttu-id="68d72-140">-Módulos \<Module-Name\> |\<Hashtable\></span><span class="sxs-lookup"><span data-stu-id="68d72-140">-Modules \<Module-Name\> | \<Hashtable\></span></span>

<span data-ttu-id="68d72-141">Especifica os módulos do PowerShell que o script requer.</span><span class="sxs-lookup"><span data-stu-id="68d72-141">Specifies PowerShell modules that the script requires.</span></span> <span data-ttu-id="68d72-142">Insira o nome do módulo e um número de versão opcional.</span><span class="sxs-lookup"><span data-stu-id="68d72-142">Enter the module name and an optional version number.</span></span>

<span data-ttu-id="68d72-143">Se os módulos necessários não estiverem na sessão atual, o PowerShell os importará.</span><span class="sxs-lookup"><span data-stu-id="68d72-143">If the required modules aren't in the current session, PowerShell imports them.</span></span>
<span data-ttu-id="68d72-144">Se os módulos não puderem ser importados, o PowerShell lançará um erro de encerramento.</span><span class="sxs-lookup"><span data-stu-id="68d72-144">If the modules can't be imported, PowerShell throws a terminating error.</span></span>

<span data-ttu-id="68d72-145">Para cada módulo, digite o nome do módulo ( \<String\> ) ou uma tabela de hash.</span><span class="sxs-lookup"><span data-stu-id="68d72-145">For each module, type the module name (\<String\>) or a hash table.</span></span> <span data-ttu-id="68d72-146">O valor pode ser uma combinação de cadeias de caracteres e tabelas de hash.</span><span class="sxs-lookup"><span data-stu-id="68d72-146">The value can be a combination of strings and hash tables.</span></span> <span data-ttu-id="68d72-147">A tabela de hash tem as seguintes chaves.</span><span class="sxs-lookup"><span data-stu-id="68d72-147">The hash table has the following keys.</span></span>

- <span data-ttu-id="68d72-148">`ModuleName` - **Necessário** Especifica o nome do módulo.</span><span class="sxs-lookup"><span data-stu-id="68d72-148">`ModuleName` - **Required** Specifies the module name.</span></span>
- <span data-ttu-id="68d72-149">`GUID` - **Opcional** Especifica o GUID do módulo.</span><span class="sxs-lookup"><span data-stu-id="68d72-149">`GUID` - **Optional** Specifies the GUID of the module.</span></span>
- <span data-ttu-id="68d72-150">Também é **necessário** especificar uma das três chaves abaixo.</span><span class="sxs-lookup"><span data-stu-id="68d72-150">It's also **Required** to specify one of the three below keys.</span></span> <span data-ttu-id="68d72-151">Essas chaves não podem ser usadas juntas.</span><span class="sxs-lookup"><span data-stu-id="68d72-151">These keys can't be used together.</span></span>
  - <span data-ttu-id="68d72-152">`ModuleVersion` -Especifica uma versão mínima aceitável do módulo.</span><span class="sxs-lookup"><span data-stu-id="68d72-152">`ModuleVersion` - Specifies a minimum acceptable version of the module.</span></span>
  - <span data-ttu-id="68d72-153">`RequiredVersion` -Especifica uma versão exata e necessária do módulo.</span><span class="sxs-lookup"><span data-stu-id="68d72-153">`RequiredVersion` - Specifies an exact, required version of the module.</span></span>
  - <span data-ttu-id="68d72-154">`MaximumVersion` -Especifica a versão máxima aceitável do módulo.</span><span class="sxs-lookup"><span data-stu-id="68d72-154">`MaximumVersion` - Specifies the maximum acceptable version of the module.</span></span>

> [!NOTE]
> <span data-ttu-id="68d72-155">`RequiredVersion` foi adicionado no Windows PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="68d72-155">`RequiredVersion` was added in Windows PowerShell 5.0.</span></span>
> <span data-ttu-id="68d72-156">`MaximumVersion` foi adicionado no Windows PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="68d72-156">`MaximumVersion` was added in Windows PowerShell 5.1.</span></span>

<span data-ttu-id="68d72-157">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="68d72-157">For example:</span></span>

<span data-ttu-id="68d72-158">Exigir que `Hyper-V` (versão `1.1` ou superior) esteja instalado.</span><span class="sxs-lookup"><span data-stu-id="68d72-158">Require that `Hyper-V` (version `1.1` or greater) is installed.</span></span>

```powershell
#Requires -Modules @{ ModuleName="Hyper-V"; ModuleVersion="1.1" }
```

<span data-ttu-id="68d72-159">Requer que `Hyper-V` (**apenas** a versão `1.1` ) esteja instalado.</span><span class="sxs-lookup"><span data-stu-id="68d72-159">Requires that `Hyper-V` (**only** version `1.1`) is installed.</span></span>

```powershell
#Requires -Modules @{ ModuleName="Hyper-V"; RequiredVersion="1.1" }
```

<span data-ttu-id="68d72-160">Requer que `Hyper-V` (versão `1.1` ou menos) esteja instalado.</span><span class="sxs-lookup"><span data-stu-id="68d72-160">Requires that `Hyper-V` (version `1.1` or lesser) is installed.</span></span>

```powershell
#Requires -Modules @{ ModuleName="Hyper-V"; MaximumVersion="1.1" }
```

<span data-ttu-id="68d72-161">Requer que qualquer versão do `PSScheduledJob` e do `PSWorkflow` esteja instalada.</span><span class="sxs-lookup"><span data-stu-id="68d72-161">Requires that any version of `PSScheduledJob` and `PSWorkflow`, is installed.</span></span>

```powershell
#Requires -Modules PSWorkflow, PSScheduledJob
```

<span data-ttu-id="68d72-162">Ao usar a `RequiredVersion` chave, verifique se a cadeia de caracteres da versão corresponde exatamente à cadeia de caracteres da versão que você deseja exigir.</span><span class="sxs-lookup"><span data-stu-id="68d72-162">When using the `RequiredVersion` key, ensure your version string exactly matches the version string you wish to require.</span></span>

```powershell
Get-Module Hyper-V
```

```Output
ModuleType Version    Name     ExportedCommands
---------- -------    ----     ------------------
Binary     2.0.0.0    hyper-v  {Add-VMAssignableDevice, ...}
```

<span data-ttu-id="68d72-163">O exemplo a seguir falha porque **2.0.0** não corresponde exatamente a **2.0.0.0**.</span><span class="sxs-lookup"><span data-stu-id="68d72-163">The following example fails because **2.0.0** doesn't exactly match **2.0.0.0**.</span></span>

```powershell
#Requires -Modules @{ ModuleName="Hyper-V"; RequiredVersion="2.0.0" }
```

#### <a name="-psedition-psedition-name"></a><span data-ttu-id="68d72-164">-PSEdition \<PSEdition-Name\></span><span class="sxs-lookup"><span data-stu-id="68d72-164">-PSEdition \<PSEdition-Name\></span></span>

<span data-ttu-id="68d72-165">Especifica uma edição do PowerShell que o script requer.</span><span class="sxs-lookup"><span data-stu-id="68d72-165">Specifies a PowerShell edition that the script requires.</span></span> <span data-ttu-id="68d72-166">Os valores válidos são **Core** para PowerShell Core e **Desktop** para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68d72-166">Valid values are **Core** for PowerShell Core and **Desktop** for Windows PowerShell.</span></span>

<span data-ttu-id="68d72-167">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="68d72-167">For example:</span></span>

```powershell
#Requires -PSEdition Core
```

#### <a name="-shellid"></a><span data-ttu-id="68d72-168">-ShellId</span><span class="sxs-lookup"><span data-stu-id="68d72-168">-ShellId</span></span>

<span data-ttu-id="68d72-169">Especifica o shell que o script requer.</span><span class="sxs-lookup"><span data-stu-id="68d72-169">Specifies the shell that the script requires.</span></span> <span data-ttu-id="68d72-170">Insira a ID do Shell.</span><span class="sxs-lookup"><span data-stu-id="68d72-170">Enter the shell ID.</span></span> <span data-ttu-id="68d72-171">Se você usar o parâmetro **ShellId** , também deverá incluir o parâmetro **PSSnapin** .</span><span class="sxs-lookup"><span data-stu-id="68d72-171">If you use the **ShellId** parameter, you must also include the **PSSnapin** parameter.</span></span>
<span data-ttu-id="68d72-172">Você pode encontrar a **ShellId** atual consultando a `$ShellId` variável automática.</span><span class="sxs-lookup"><span data-stu-id="68d72-172">You can find the current **ShellId** by querying the `$ShellId` automatic variable.</span></span>

<span data-ttu-id="68d72-173">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="68d72-173">For example:</span></span>

```powershell
#Requires -ShellId MyLocalShell -PSSnapin Microsoft.PowerShell.Core
```

> [!NOTE]
> <span data-ttu-id="68d72-174">Este parâmetro destina-se ao uso em mini-shells, que foram preteridos.</span><span class="sxs-lookup"><span data-stu-id="68d72-174">This parameter is intended for use in mini-shells, which have been deprecated.</span></span>

#### <a name="-runasadministrator"></a><span data-ttu-id="68d72-175">-RunAsAdministrator</span><span class="sxs-lookup"><span data-stu-id="68d72-175">-RunAsAdministrator</span></span>

<span data-ttu-id="68d72-176">Quando esse parâmetro de opção é adicionado à sua `#Requires` instrução, ele especifica que a sessão do PowerShell na qual você está executando o script deve ser iniciada com direitos de usuário elevados.</span><span class="sxs-lookup"><span data-stu-id="68d72-176">When this switch parameter is added to your `#Requires` statement, it specifies that the PowerShell session in which you're running the script must be started with elevated user rights.</span></span> <span data-ttu-id="68d72-177">O parâmetro **RunAsAdministrator** é ignorado em um sistema operacional não Windows.</span><span class="sxs-lookup"><span data-stu-id="68d72-177">The **RunAsAdministrator** parameter is ignored on a non-Windows operating system.</span></span> <span data-ttu-id="68d72-178">O parâmetro **RunAsAdministrator** foi introduzido no PowerShell 4,0.</span><span class="sxs-lookup"><span data-stu-id="68d72-178">The **RunAsAdministrator** parameter was introduced in PowerShell 4.0.</span></span>

<span data-ttu-id="68d72-179">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="68d72-179">For example:</span></span>

```powershell
#Requires -RunAsAdministrator
```

### <a name="examples"></a><span data-ttu-id="68d72-180">Exemplos</span><span class="sxs-lookup"><span data-stu-id="68d72-180">Examples</span></span>

<span data-ttu-id="68d72-181">O script a seguir tem duas `#Requires` instruções.</span><span class="sxs-lookup"><span data-stu-id="68d72-181">The following script has two `#Requires` statements.</span></span> <span data-ttu-id="68d72-182">Se os requisitos especificados em ambas as instruções não forem atendidos, o script não é executado.</span><span class="sxs-lookup"><span data-stu-id="68d72-182">If the requirements specified in both statements aren't met, the script doesn't run.</span></span> <span data-ttu-id="68d72-183">Cada `#Requires` instrução deve ser o primeiro item em uma linha:</span><span class="sxs-lookup"><span data-stu-id="68d72-183">Each `#Requires` statement must be the first item on a line:</span></span>

```powershell
#Requires -Modules PSWorkflow
#Requires -Version 3
Param
(
    [parameter(Mandatory=$true)]
    [String[]]
    $Path
)
...
```

## <a name="see-also"></a><span data-ttu-id="68d72-184">Confira também</span><span class="sxs-lookup"><span data-stu-id="68d72-184">See also</span></span>

[<span data-ttu-id="68d72-185">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="68d72-185">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="68d72-186">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="68d72-186">about_Language_Keywords</span></span>](about_Language_Keywords.md)

[<span data-ttu-id="68d72-187">about_PSSnapins</span><span class="sxs-lookup"><span data-stu-id="68d72-187">about_PSSnapins</span></span>](about_PSSnapins.md)

[<span data-ttu-id="68d72-188">Get-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="68d72-188">Get-PSSnapin</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSnapin)
