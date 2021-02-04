---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/20/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-command?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Command
ms.openlocfilehash: 5f2752f53fb5f74b6436548c3bd4fa731d2b02d5
ms.sourcegitcommit: 04faa7dc1122bce839295d4891bd8b2f0ecb06ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97879228"
---
# <span data-ttu-id="df6a8-103">Get-Command</span><span class="sxs-lookup"><span data-stu-id="df6a8-103">Get-Command</span></span>

## <span data-ttu-id="df6a8-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="df6a8-104">SYNOPSIS</span></span>
<span data-ttu-id="df6a8-105">Obtém todos os comandos.</span><span class="sxs-lookup"><span data-stu-id="df6a8-105">Gets all commands.</span></span>

## <span data-ttu-id="df6a8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="df6a8-106">SYNTAX</span></span>

### <span data-ttu-id="df6a8-107">CmdletSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="df6a8-107">CmdletSet (Default)</span></span>

```
Get-Command [-Verb <String[]>] [-Noun <String[]>] [-Module <String[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [-TotalCount <Int32>] [-Syntax] [-ShowCommandInfo]
 [[-ArgumentList] <Object[]>] [-All] [-ListImported] [-ParameterName <String[]>]
 [-ParameterType <PSTypeName[]>] [<CommonParameters>]
```

### <span data-ttu-id="df6a8-108">Setcommandset</span><span class="sxs-lookup"><span data-stu-id="df6a8-108">AllCommandSet</span></span>

```
Get-Command [[-Name] <String[]>] [-Module <String[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [-CommandType <CommandTypes>] [-TotalCount <Int32>]
 [-Syntax] [-ShowCommandInfo] [[-ArgumentList] <Object[]>] [-All] [-ListImported]
 [-ParameterName <String[]>] [-ParameterType <PSTypeName[]>] [-UseFuzzyMatching]
 [-UseAbbreviationExpansion] [<CommonParameters>]
```

## <span data-ttu-id="df6a8-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df6a8-109">DESCRIPTION</span></span>

<span data-ttu-id="df6a8-110">O `Get-Command` cmdlet obtém todos os comandos que estão instalados no computador, incluindo cmdlets, aliases, funções, filtros, scripts e aplicativos.</span><span class="sxs-lookup"><span data-stu-id="df6a8-110">The `Get-Command` cmdlet gets all commands that are installed on the computer, including cmdlets, aliases, functions, filters, scripts, and applications.</span></span> <span data-ttu-id="df6a8-111">`Get-Command` Obtém os comandos de módulos e comandos do PowerShell que foram importados de outras sessões.</span><span class="sxs-lookup"><span data-stu-id="df6a8-111">`Get-Command` gets the commands from PowerShell modules and commands that were imported from other sessions.</span></span> <span data-ttu-id="df6a8-112">Para obter somente comandos que foram importados para a sessão atual, use o parâmetro **ListImported**.</span><span class="sxs-lookup"><span data-stu-id="df6a8-112">To get only commands that have been imported into the current session, use the **ListImported** parameter.</span></span>

<span data-ttu-id="df6a8-113">Sem parâmetros, `Get-Command` Obtém todos os cmdlets, funções e aliases instalados no computador.</span><span class="sxs-lookup"><span data-stu-id="df6a8-113">Without parameters, `Get-Command` gets all of the cmdlets, functions, and aliases installed on the computer.</span></span> <span data-ttu-id="df6a8-114">`Get-Command *` Obtém todos os tipos de comandos, incluindo todos os arquivos que não são do PowerShell na variável de ambiente Path ( `$env:Path` ), que é listada no tipo de comando Application.</span><span class="sxs-lookup"><span data-stu-id="df6a8-114">`Get-Command *` gets all types of commands, including all of the non-PowerShell files in the Path environment variable (`$env:Path`), which it lists in the Application command type.</span></span>

<span data-ttu-id="df6a8-115">`Get-Command` que usa o nome exato do comando, sem caracteres curinga, importa automaticamente o módulo que contém o comando para que você possa usar o comando imediatamente.</span><span class="sxs-lookup"><span data-stu-id="df6a8-115">`Get-Command` that uses the exact name of the command, without wildcard characters, automatically imports the module that contains the command so that you can use the command immediately.</span></span> <span data-ttu-id="df6a8-116">Para habilitar, desabilitar e configurar a importação automática de módulos, use a `$PSModuleAutoLoadingPreference` variável de preferência.</span><span class="sxs-lookup"><span data-stu-id="df6a8-116">To enable, disable, and configure automatic importing of modules, use the `$PSModuleAutoLoadingPreference` preference variable.</span></span> <span data-ttu-id="df6a8-117">Para obter mais informações, consulte [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="df6a8-117">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="df6a8-118">`Get-Command` Obtém seus dados diretamente do código de comando, ao contrário de `Get-Help` , que obtém suas informações dos tópicos da ajuda.</span><span class="sxs-lookup"><span data-stu-id="df6a8-118">`Get-Command` gets its data directly from the command code, unlike `Get-Help`, which gets its information from help topics.</span></span>

<span data-ttu-id="df6a8-119">A partir do Windows PowerShell 5,0, os resultados do `Get-Command` cmdlet exibem uma coluna de **versão** por padrão.</span><span class="sxs-lookup"><span data-stu-id="df6a8-119">Starting in Windows PowerShell 5.0, results of the `Get-Command` cmdlet display a **Version** column by default.</span></span> <span data-ttu-id="df6a8-120">Uma nova propriedade **version** foi adicionada à classe **CommandInfo** .</span><span class="sxs-lookup"><span data-stu-id="df6a8-120">A new **Version** property has been added to the **CommandInfo** class.</span></span>

## <span data-ttu-id="df6a8-121">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="df6a8-121">EXAMPLES</span></span>

### <span data-ttu-id="df6a8-122">Exemplo 1: obter cmdlets, funções e aliases</span><span class="sxs-lookup"><span data-stu-id="df6a8-122">Example 1: Get cmdlets, functions, and aliases</span></span>

<span data-ttu-id="df6a8-123">Esse comando obtém os cmdlets, as funções e os aliases do PowerShell instalados no computador.</span><span class="sxs-lookup"><span data-stu-id="df6a8-123">This command gets the PowerShell cmdlets, functions, and aliases that are installed on the computer.</span></span>

```powershell
Get-Command
```

### <span data-ttu-id="df6a8-124">Exemplo 2: obter comandos na sessão atual</span><span class="sxs-lookup"><span data-stu-id="df6a8-124">Example 2: Get commands in the current session</span></span>

<span data-ttu-id="df6a8-125">Este comando usa o parâmetro **ListImported** para obter apenas os comandos da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="df6a8-125">This command uses the **ListImported** parameter to get only the commands in the current session.</span></span>

```powershell
Get-Command -ListImported
```

### <span data-ttu-id="df6a8-126">Exemplo 3: obter cmdlets e exibi-los na ordem</span><span class="sxs-lookup"><span data-stu-id="df6a8-126">Example 3: Get cmdlets and display them in order</span></span>

<span data-ttu-id="df6a8-127">Esse comando obtém todos os cmdlets, os classifica em ordem alfabética pelo substantivo no nome do cmdlet e, em seguida, os exibe em grupos baseados no substantivo.</span><span class="sxs-lookup"><span data-stu-id="df6a8-127">This command gets all of the cmdlets, sorts them alphabetically by the noun in the cmdlet name, and then displays them in noun-based groups.</span></span> <span data-ttu-id="df6a8-128">Essa exibição pode ajudar a localizar os cmdlets para uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="df6a8-128">This display can help you find the cmdlets for a task.</span></span>

```powershell
Get-Command -Type Cmdlet | Sort-Object -Property Noun | Format-Table -GroupBy Noun
```

### <span data-ttu-id="df6a8-129">Exemplo 4: obter comandos em um módulo</span><span class="sxs-lookup"><span data-stu-id="df6a8-129">Example 4: Get commands in a module</span></span>

<span data-ttu-id="df6a8-130">Esse comando usa o parâmetro **Module** para obter os comandos nos módulos Microsoft. PowerShell. Security e Microsoft. PowerShell. Utility.</span><span class="sxs-lookup"><span data-stu-id="df6a8-130">This command uses the **Module** parameter to get the commands in the Microsoft.PowerShell.Security and Microsoft.PowerShell.Utility modules.</span></span>

```powershell
Get-Command -Module Microsoft.PowerShell.Security, Microsoft.PowerShell.Utility
```

### <span data-ttu-id="df6a8-131">Exemplo 5: obter informações sobre um cmdlet</span><span class="sxs-lookup"><span data-stu-id="df6a8-131">Example 5: Get information about a cmdlet</span></span>

<span data-ttu-id="df6a8-132">Esse comando obtém informações sobre o `Get-AppLockerPolicy` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="df6a8-132">This command gets information about the `Get-AppLockerPolicy` cmdlet.</span></span> <span data-ttu-id="df6a8-133">Ele também importa o módulo **AppLocker**, que adiciona todos os comandos no módulo **AppLocker** à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="df6a8-133">It also imports the **AppLocker** module, which adds all of the commands in the **AppLocker** module to the current session.</span></span>

```powershell
Get-Command Get-AppLockerPolicy
```

<span data-ttu-id="df6a8-134">Quando um módulo é importado automaticamente, o efeito é o mesmo que usar o cmdlet Import-Module.</span><span class="sxs-lookup"><span data-stu-id="df6a8-134">When a module is imported automatically, the effect is the same as using the Import-Module cmdlet.</span></span>
<span data-ttu-id="df6a8-135">O módulo pode adicionar comandos, tipos e arquivos de formatação e executar scripts na sessão.</span><span class="sxs-lookup"><span data-stu-id="df6a8-135">The module can add commands, types and formatting files, and run scripts in the session.</span></span> <span data-ttu-id="df6a8-136">Para habilitar, desabilitar e configurar a importação automática de módulos, use a `$PSModuleAutoLoadingPreference` variável de preferência.</span><span class="sxs-lookup"><span data-stu-id="df6a8-136">To enable, disable, and configuration automatic importing of modules, use the `$PSModuleAutoLoadingPreference` preference variable.</span></span> <span data-ttu-id="df6a8-137">Para obter mais informações, consulte [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="df6a8-137">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

### <span data-ttu-id="df6a8-138">Exemplo 6: obter a sintaxe de um cmdlet</span><span class="sxs-lookup"><span data-stu-id="df6a8-138">Example 6: Get the syntax of a cmdlet</span></span>

<span data-ttu-id="df6a8-139">Esse comando usa os parâmetros **ArgumentList** e **Syntax** para obter a sintaxe do `Get-ChildItem` cmdlet quando ele é usado na unidade CERT:.</span><span class="sxs-lookup"><span data-stu-id="df6a8-139">This command uses the **ArgumentList** and **Syntax** parameters to get the syntax of the `Get-ChildItem` cmdlet when it is used in the Cert: drive.</span></span> <span data-ttu-id="df6a8-140">A unidade CERT: é uma unidade do PowerShell que o provedor de certificado adiciona à sessão.</span><span class="sxs-lookup"><span data-stu-id="df6a8-140">The Cert: drive is a PowerShell drive that the Certificate Provider adds to the session.</span></span>

```powershell
Get-Command  -Name Get-Childitem -Args Cert: -Syntax
```

<span data-ttu-id="df6a8-141">Ao comparar a sintaxe exibida na saída com a sintaxe que é exibida quando você omite o parâmetro **args** (**ArgumentList**), você verá que o **provedor de certificado** adiciona um parâmetro dinâmico, **CodeSigningCert**, ao `Get-ChildItem` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="df6a8-141">When you compare the syntax displayed in the output with the syntax that is displayed when you omit the **Args** (**ArgumentList**) parameter, you'll see that the **Certificate provider** adds a dynamic parameter, **CodeSigningCert**, to the `Get-ChildItem` cmdlet.</span></span>

<span data-ttu-id="df6a8-142">Para obter mais informações sobre o provedor de certificados, consulte [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span><span class="sxs-lookup"><span data-stu-id="df6a8-142">For more information about the Certificate provider, see [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span></span>

### <span data-ttu-id="df6a8-143">Exemplo 7: obter parâmetros dinâmicos</span><span class="sxs-lookup"><span data-stu-id="df6a8-143">Example 7: Get dynamic parameters</span></span>

<span data-ttu-id="df6a8-144">O comando no exemplo usa a `Get-DynamicParameters` função para obter os parâmetros dinâmicos que o provedor de certificado adiciona ao `Get-ChildItem` cmdlet quando ele é usado na unidade CERT:.</span><span class="sxs-lookup"><span data-stu-id="df6a8-144">The command in the example uses the `Get-DynamicParameters` function to get the dynamic parameters that the Certificate provider adds to the `Get-ChildItem` cmdlet when it is used in the Cert: drive.</span></span>

```powershell
function Get-DynamicParameters
{
    param ($Cmdlet, $PSDrive)
    (Get-Command -Name $Cmdlet -ArgumentList $PSDrive).ParameterSets | ForEach-Object {$_.Parameters} | Where-Object { $_.IsDynamic } | Select-Object -Property Name -Unique
}
Get-DynamicParameters -Cmdlet Get-ChildItem -PSDrive Cert:
```

```Output
Name
----
CodeSigningCert
```

<span data-ttu-id="df6a8-145">A `Get-DynamicParameters` função neste exemplo obtém os parâmetros dinâmicos de um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="df6a8-145">The `Get-DynamicParameters` function in this example gets the dynamic parameters of a cmdlet.</span></span> <span data-ttu-id="df6a8-146">Essa é uma alternativa ao método usado no exemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="df6a8-146">This is an alternative to the method used in the previous example.</span></span> <span data-ttu-id="df6a8-147">O parâmetro dinâmico pode ser adicionado a um cmdlet por outro cmdlet ou por um provedor.</span><span class="sxs-lookup"><span data-stu-id="df6a8-147">Dynamic parameter can be added to a cmdlet by another cmdlet or a provider.</span></span>

### <span data-ttu-id="df6a8-148">Exemplo 8: obter todos os comandos de todos os tipos</span><span class="sxs-lookup"><span data-stu-id="df6a8-148">Example 8: Get all commands of all types</span></span>

<span data-ttu-id="df6a8-149">Esse comando obtém todos os comandos de todos os tipos no computador local, incluindo arquivos executáveis nos caminhos da variável de ambiente **path** ( `$env:path` ).</span><span class="sxs-lookup"><span data-stu-id="df6a8-149">This command gets all commands of all types on the local computer, including executable files in the paths of the **Path** environment variable (`$env:path`).</span></span>

```powershell
Get-Command *
```

<span data-ttu-id="df6a8-150">Ele retorna um objeto **ApplicationInfo** (System.Management.Automation.ApplicationInfo) para cada arquivo e não um objeto **FileInfo** (System.IO.FileInfo).</span><span class="sxs-lookup"><span data-stu-id="df6a8-150">It returns an **ApplicationInfo** object (System.Management.Automation.ApplicationInfo) for each file, not a **FileInfo** object (System.IO.FileInfo).</span></span>

### <span data-ttu-id="df6a8-151">Exemplo 9: obter cmdlets usando um nome de parâmetro e tipo</span><span class="sxs-lookup"><span data-stu-id="df6a8-151">Example 9: Get cmdlets by using a parameter name and type</span></span>

<span data-ttu-id="df6a8-152">Esse comando obtém os cmdlets que têm um parâmetro cujo nome inclui autenticação e cujo tipo é **AuthenticationMechanism**.</span><span class="sxs-lookup"><span data-stu-id="df6a8-152">This command gets cmdlets that have a parameter whose name includes Auth and whose type is **AuthenticationMechanism**.</span></span>

```powershell
Get-Command -ParameterName *Auth* -ParameterType AuthenticationMechanism
```

<span data-ttu-id="df6a8-153">É possível usar um comando como este para localizar cmdlets que permitem que você especifique o método usado para autenticar o usuário.</span><span class="sxs-lookup"><span data-stu-id="df6a8-153">You can use a command like this one to find cmdlets that let you specify the method that is used to authenticate the user.</span></span>

<span data-ttu-id="df6a8-154">O parâmetro **ParameterType** distingue parâmetros que usam um valor **AuthenticationMechanism** dos que usam um parâmetro **AuthenticationLevel**, mesmo quando tiverem nomes semelhantes.</span><span class="sxs-lookup"><span data-stu-id="df6a8-154">The **ParameterType** parameter distinguishes parameters that take an **AuthenticationMechanism** value from those that take an **AuthenticationLevel** parameter, even when they have similar names.</span></span>

### <span data-ttu-id="df6a8-155">Exemplo 10: obter um alias</span><span class="sxs-lookup"><span data-stu-id="df6a8-155">Example 10: Get an alias</span></span>

<span data-ttu-id="df6a8-156">Este exemplo mostra como usar o `Get-Command` cmdlet com um alias.</span><span class="sxs-lookup"><span data-stu-id="df6a8-156">This example shows how to use the `Get-Command` cmdlet with an alias.</span></span>

```powershell
Get-Command -Name dir
```

```Output
CommandType     Name                                               ModuleName
-----------     ----                                               ----------
Alias           dir -> Get-ChildItem
```

<span data-ttu-id="df6a8-157">Embora normalmente seja usado em cmdlets e funções, o `Get-Command` também obtém scripts, funções, aliases e arquivos executáveis.</span><span class="sxs-lookup"><span data-stu-id="df6a8-157">Although it is typically used on cmdlets and functions, `Get-Command` also gets scripts, functions, aliases, and executable files.</span></span>

<span data-ttu-id="df6a8-158">A saída do comando mostra o modo de exibição especial do valor de propriedade **Name** para aliases.</span><span class="sxs-lookup"><span data-stu-id="df6a8-158">The output of the command shows the special view of the **Name** property value for aliases.</span></span> <span data-ttu-id="df6a8-159">O modo de exibição mostra o alias e o nome completo do comando.</span><span class="sxs-lookup"><span data-stu-id="df6a8-159">The view shows the alias and the full command name.</span></span>

### <span data-ttu-id="df6a8-160">Exemplo 11: obter a sintaxe de um alias</span><span class="sxs-lookup"><span data-stu-id="df6a8-160">Example 11: Get Syntax from an alias</span></span>

<span data-ttu-id="df6a8-161">Este exemplo mostra como obter a sintaxe junto com o nome padrão de um alias.</span><span class="sxs-lookup"><span data-stu-id="df6a8-161">This example shows how to get the syntax along with the standard name of an alias.</span></span>

<span data-ttu-id="df6a8-162">A saída do comando mostra o alias rotulado com o nome padrão, seguido pela sintaxe.</span><span class="sxs-lookup"><span data-stu-id="df6a8-162">The output of the command shows the labeled alias with the standard name, followed by the syntax.</span></span>

```powershell
Get-Command -Name dir -Syntax
```

```Output
dir (alias) -> Get-ChildItem

dir [[-Path] <string[]>] [[-Filter] <string>] [-Include <string[]>] [-Exclude <string[]>] [-Recurse] [-Depth <uint>] [-Force] [-Name] [-Attributes <FlagsExpression[FileAttributes]>] [-FollowSymlink] [-Directory] [-File] [-Hidden] [-ReadOnly] [-System] [<CommonParameters>]

dir [[-Filter] <string>] -LiteralPath <string[]> [-Include <string[]>] [-Exclude <string[]>] [-Recurse] [-Depth <uint>] [-Force] [-Name] [-Attributes <FlagsExpression[FileAttributes]>] [-FollowSymlink] [-Directory] [-File] [-Hidden] [-ReadOnly] [-System] [<CommonParameters>]
```

### <span data-ttu-id="df6a8-163">Exemplo 12: obter todas as instâncias do comando do bloco de notas</span><span class="sxs-lookup"><span data-stu-id="df6a8-163">Example 12: Get all instances of the Notepad command</span></span>

<span data-ttu-id="df6a8-164">Este exemplo usa o parâmetro **All** do `Get-Command` cmdlet para mostrar todas as instâncias do `Notepad` comando no computador local.</span><span class="sxs-lookup"><span data-stu-id="df6a8-164">This example uses the **All** parameter of the `Get-Command` cmdlet to show all instances of the `Notepad` command on the local computer.</span></span>

```powershell
Get-Command Notepad -All | Format-Table CommandType, Name, Definition
```

```Output
CommandType     Name           Definition
-----------     ----           ----------
Application     notepad.exe    C:\WINDOWS\system32\notepad.exe
Application     NOTEPAD.EXE    C:\WINDOWS\NOTEPAD.EXE
```

<span data-ttu-id="df6a8-165">O parâmetro **All** é útil quando há mais de um comando com o mesmo nome na sessão.</span><span class="sxs-lookup"><span data-stu-id="df6a8-165">The **All** parameter is useful when there is more than one command with the same name in the session.</span></span>

<span data-ttu-id="df6a8-166">A partir do Windows PowerShell 3,0, por padrão, quando a sessão inclui vários comandos com o mesmo nome, `Get-Command` obtém apenas o comando que é executado quando você digita o nome do comando.</span><span class="sxs-lookup"><span data-stu-id="df6a8-166">Beginning in Windows PowerShell 3.0, by default, when the session includes multiple commands with the same name, `Get-Command` gets only the command that runs when you type the command name.</span></span> <span data-ttu-id="df6a8-167">Com o parâmetro **All** , `Get-Command` Obtém todos os comandos com o nome especificado e os retorna na ordem de precedência de execução.</span><span class="sxs-lookup"><span data-stu-id="df6a8-167">With the **All** parameter, `Get-Command` gets all commands with the specified name and returns them in execution precedence order.</span></span> <span data-ttu-id="df6a8-168">Para executar um comando que não seja o primeiro da lista, digite o caminho totalmente qualificado para o comando.</span><span class="sxs-lookup"><span data-stu-id="df6a8-168">To run a command other than the first one in the list, type the fully qualified path to the command.</span></span>

<span data-ttu-id="df6a8-169">Para obter mais informações sobre a precedência de comando, consulte [about_Command_Precedence](About/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="df6a8-169">For more information about command precedence, see [about_Command_Precedence](About/about_Command_Precedence.md).</span></span>

### <span data-ttu-id="df6a8-170">Exemplo 13: obter o nome de um módulo que contém um cmdlet</span><span class="sxs-lookup"><span data-stu-id="df6a8-170">Example 13: Get the name of a module that contains a cmdlet</span></span>

<span data-ttu-id="df6a8-171">Esse comando obtém o nome do módulo no qual o `Get-Date` cmdlet foi originado.</span><span class="sxs-lookup"><span data-stu-id="df6a8-171">This command gets the name of the module in which the `Get-Date` cmdlet originated.</span></span>
<span data-ttu-id="df6a8-172">O comando usa a propriedade **ModuleName** de todos os comandos.</span><span class="sxs-lookup"><span data-stu-id="df6a8-172">The command uses the **ModuleName** property of all commands.</span></span>

```powershell
(Get-Command Get-Date).ModuleName
```

```Output
Microsoft.PowerShell.Utility
```

<span data-ttu-id="df6a8-173">Esse formato de comando funciona em comandos em módulos do PowerShell, mesmo que eles não sejam importados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="df6a8-173">This command format works on commands in PowerShell modules, even if they are not imported into the session.</span></span>

### <span data-ttu-id="df6a8-174">Exemplo 14: obter cmdlets e funções que têm um tipo de saída</span><span class="sxs-lookup"><span data-stu-id="df6a8-174">Example 14: Get cmdlets and functions that have an output type</span></span>

```powershell
Get-Command -Type Cmdlet | Where-Object OutputType | Format-List -Property Name, OutputType
```

<span data-ttu-id="df6a8-175">Esse comando obtém os cmdlets e funções que têm um tipo de saída e os tipos de objetos que eles retornam.</span><span class="sxs-lookup"><span data-stu-id="df6a8-175">This command gets the cmdlets and functions that have an output type and the type of objects that they return.</span></span>

<span data-ttu-id="df6a8-176">A primeira parte do comando obtém todos os cmdlets.</span><span class="sxs-lookup"><span data-stu-id="df6a8-176">The first part of the command gets all cmdlets.</span></span> <span data-ttu-id="df6a8-177">Um operador de pipeline ( `|` ) envia os cmdlets para o `Where-Object` cmdlet, que seleciona apenas aqueles nos quais a propriedade **OutputType** é populada.</span><span class="sxs-lookup"><span data-stu-id="df6a8-177">A pipeline operator (`|`) sends the cmdlets to the `Where-Object` cmdlet, which selects only the ones in which the **OutputType** property is populated.</span></span> <span data-ttu-id="df6a8-178">Outro operador de pipeline envia os objetos de cmdlet selecionados para o `Format-List` cmdlet, que exibe o nome e o tipo de saída de cada cmdlet em uma lista.</span><span class="sxs-lookup"><span data-stu-id="df6a8-178">Another pipeline operator sends the selected cmdlet objects to the `Format-List` cmdlet, which displays the name and output type of each cmdlet in a list.</span></span>

<span data-ttu-id="df6a8-179">A propriedade **OutputType** de um objeto **CommandInfo** tem um valor não nulo somente quando o código do cmdlet define o atributo **OutputType** para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="df6a8-179">The **OutputType** property of a **CommandInfo** object has a non-null value only when the cmdlet code defines the **OutputType** attribute for the cmdlet.</span></span>

### <span data-ttu-id="df6a8-180">Exemplo 15: obter cmdlets que usam um tipo de objeto específico como entrada</span><span class="sxs-lookup"><span data-stu-id="df6a8-180">Example 15: Get cmdlets that take a specific object type as input</span></span>

```powershell
Get-Command -ParameterType (((Get-NetAdapter)[0]).PSTypeNames)
```

```Output
CommandType     Name                                               ModuleName
-----------     ----                                               ----------
Function        Disable-NetAdapter                                 NetAdapter
Function        Enable-NetAdapter                                  NetAdapter
Function        Rename-NetAdapter                                  NetAdapter
Function        Restart-NetAdapter                                 NetAdapter
Function        Set-NetAdapter                                     NetAdapter
```

<span data-ttu-id="df6a8-181">Este comando localiza cmdlets que usam objetos de adaptador de rede como entrada.</span><span class="sxs-lookup"><span data-stu-id="df6a8-181">This command finds cmdlets that take net adapter objects as input.</span></span> <span data-ttu-id="df6a8-182">Você pode usar esse formato de comando para localizar os cmdlets que aceitam o tipo de objeto que qualquer comando retorna.</span><span class="sxs-lookup"><span data-stu-id="df6a8-182">You can use this command format to find the cmdlets that accept the type of objects that any command returns.</span></span>

<span data-ttu-id="df6a8-183">O comando usa a propriedade intrínseca **PSTypeNames** de todos os objetos, que obtém os tipos que descrevem o objeto.</span><span class="sxs-lookup"><span data-stu-id="df6a8-183">The command uses the **PSTypeNames** intrinsic property of all objects, which gets the types that describe the object.</span></span> <span data-ttu-id="df6a8-184">Para obter a propriedades **PSTypeNames** de um adaptador de rede e não a propriedade **PSTypeNames** de uma coleção de adaptadores de rede, o comando usa a notação de matriz para obter o primeiro adaptador de rede que o cmdlet retorna.</span><span class="sxs-lookup"><span data-stu-id="df6a8-184">To get the **PSTypeNames** property of a net adapter, and not the **PSTypeNames** property of a collection of net adapters, the command uses array notation to get the first net adapter that the cmdlet returns.</span></span>

### <span data-ttu-id="df6a8-185">Exemplo 16: obter comandos usando uma correspondência difusa</span><span class="sxs-lookup"><span data-stu-id="df6a8-185">Example 16: Get commands using a fuzzy match</span></span>

<span data-ttu-id="df6a8-186">Neste exemplo, o nome do comando deliberadamente tem um tipográfico como ' Get-commnd '.</span><span class="sxs-lookup"><span data-stu-id="df6a8-186">In this example, the name of the command deliberately has a typo as 'get-commnd'.</span></span>
<span data-ttu-id="df6a8-187">Usando a `-UseFuzzyMatching` opção, o cmdlet determinou que a melhor correspondência foi `Get-Command` seguida por outros comandos nativos no sistema que eram uma correspondência semelhante.</span><span class="sxs-lookup"><span data-stu-id="df6a8-187">Using the `-UseFuzzyMatching` switch, the cmdlet determined that the best match was `Get-Command` followed by other native commands on the system that were a similar match.</span></span>

```powershell
Get-Command get-commnd -UseFuzzyMatching
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Get-Command                                        6.2.0.0    Microsoft.PowerShell.Core
Application     getconf                                            0.0.0.0    /usr/bin/getconf
Application     command                                            0.0.0.0    /usr/bin/command
```

## <span data-ttu-id="df6a8-188">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="df6a8-188">PARAMETERS</span></span>

### <span data-ttu-id="df6a8-189">-All</span><span class="sxs-lookup"><span data-stu-id="df6a8-189">-All</span></span>

<span data-ttu-id="df6a8-190">Indica que este cmdlet obtém todos os comandos, incluindo comandos do mesmo tipo que têm o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="df6a8-190">Indicates that this cmdlet gets all commands, including commands of the same type that have the same name.</span></span> <span data-ttu-id="df6a8-191">Por padrão, `Get-Command` o obtém apenas os comandos que são executados quando você digita o nome do comando.</span><span class="sxs-lookup"><span data-stu-id="df6a8-191">By default, `Get-Command` gets only the commands that run when you type the command name.</span></span>

<span data-ttu-id="df6a8-192">Para obter mais informações sobre o método que o PowerShell usa para selecionar o comando a ser executado quando vários comandos têm o mesmo nome, consulte [about_Command_Precedence](About/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="df6a8-192">For more information about the method that PowerShell uses to select the command to run when multiple commands have the same name, see [about_Command_Precedence](About/about_Command_Precedence.md).</span></span>
<span data-ttu-id="df6a8-193">Para obter informações sobre nomes de comando qualificados por módulo e comandos em execução que não são executados por padrão devido a um conflito de nome, consulte [about_Modules](About/about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="df6a8-193">For information about module-qualified command names and running commands that do not run by default because of a name conflict, see [about_Modules](About/about_Modules.md).</span></span>

<span data-ttu-id="df6a8-194">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="df6a8-194">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="df6a8-195">No Windows PowerShell 2,0, o `Get-Command` Obtém todos os comandos por padrão.</span><span class="sxs-lookup"><span data-stu-id="df6a8-195">In Windows PowerShell 2.0, `Get-Command` gets all commands by default.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="df6a8-196">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="df6a8-196">-ArgumentList</span></span>

<span data-ttu-id="df6a8-197">Especifica uma matriz de argumentos.</span><span class="sxs-lookup"><span data-stu-id="df6a8-197">Specifies an array of arguments.</span></span> <span data-ttu-id="df6a8-198">Esse cmdlet obtém informações sobre um cmdlet ou uma função quando ele é usado com os parâmetros especificados ("Arguments").</span><span class="sxs-lookup"><span data-stu-id="df6a8-198">This cmdlet gets information about a cmdlet or function when it is used with the specified parameters ("arguments").</span></span> <span data-ttu-id="df6a8-199">O alias para **ArgumentList** é **Args**.</span><span class="sxs-lookup"><span data-stu-id="df6a8-199">The alias for **ArgumentList** is **Args**.</span></span>

<span data-ttu-id="df6a8-200">Para detectar parâmetros dinâmicos que estão disponíveis somente quando determinados outros parâmetros são usados, defina o valor de **ArgumentList** para os parâmetros que disparam os parâmetros dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="df6a8-200">To detect dynamic parameters that are available only when certain other parameters are used, set the value of **ArgumentList** to the parameters that trigger the dynamic parameters.</span></span>

<span data-ttu-id="df6a8-201">Para detectar os parâmetros dinâmicos que um provedor adiciona a um cmdlet, defina o valor do parâmetro **ArgumentList** como um caminho na unidade do provedor, como WSMan:, HKLM: ou CERT:.</span><span class="sxs-lookup"><span data-stu-id="df6a8-201">To detect the dynamic parameters that a provider adds to a cmdlet, set the value of the **ArgumentList** parameter to a path in the provider drive, such as WSMan:, HKLM:, or Cert:.</span></span> <span data-ttu-id="df6a8-202">Quando o comando for um cmdlet do provedor do PowerShell, digite apenas um caminho em cada comando.</span><span class="sxs-lookup"><span data-stu-id="df6a8-202">When the command is a PowerShell provider cmdlet, enter only one path in each command.</span></span> <span data-ttu-id="df6a8-203">Os cmdlets do provedor retornam apenas os parâmetros dinâmicos do primeiro caminho para o valor de **ArgumentList**.</span><span class="sxs-lookup"><span data-stu-id="df6a8-203">The provider cmdlets return only the dynamic parameters for the first path the value of **ArgumentList**.</span></span> <span data-ttu-id="df6a8-204">Para obter informações sobre os cmdlets do provedor, consulte [about_Providers](About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="df6a8-204">For information about the provider cmdlets, see [about_Providers](About/about_Providers.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df6a8-205">-CommandType</span><span class="sxs-lookup"><span data-stu-id="df6a8-205">-CommandType</span></span>

<span data-ttu-id="df6a8-206">Especifica os tipos de comandos que esse cmdlet obtém.</span><span class="sxs-lookup"><span data-stu-id="df6a8-206">Specifies the types of commands that this cmdlet gets.</span></span> <span data-ttu-id="df6a8-207">Insira um ou mais tipos de comando.</span><span class="sxs-lookup"><span data-stu-id="df6a8-207">Enter one or more command types.</span></span> <span data-ttu-id="df6a8-208">Use o **CommandType** ou seu alias, **Type**.</span><span class="sxs-lookup"><span data-stu-id="df6a8-208">Use **CommandType** or its alias, **Type**.</span></span> <span data-ttu-id="df6a8-209">Por padrão, o `Get-Command` Obtém todos os cmdlets, funções e aliases.</span><span class="sxs-lookup"><span data-stu-id="df6a8-209">By default, `Get-Command` gets all cmdlets, functions, and aliases.</span></span>

<span data-ttu-id="df6a8-210">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="df6a8-210">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="df6a8-211">Receber.</span><span class="sxs-lookup"><span data-stu-id="df6a8-211">Alias.</span></span> <span data-ttu-id="df6a8-212">Obtém os aliases de todos os comandos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df6a8-212">Gets the aliases of all PowerShell commands.</span></span> <span data-ttu-id="df6a8-213">Para obter mais informações, consulte [about_Aliases](About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="df6a8-213">For more information, see [about_Aliases](About/about_Aliases.md).</span></span>
- <span data-ttu-id="df6a8-214">Todos.</span><span class="sxs-lookup"><span data-stu-id="df6a8-214">All.</span></span> <span data-ttu-id="df6a8-215">Obtém todos os tipos de comando.</span><span class="sxs-lookup"><span data-stu-id="df6a8-215">Gets all command types.</span></span> <span data-ttu-id="df6a8-216">Esse valor de parâmetro é o equivalente de `Get-Command *` .</span><span class="sxs-lookup"><span data-stu-id="df6a8-216">This parameter value is the equivalent of `Get-Command *`.</span></span>
- <span data-ttu-id="df6a8-217">Console.</span><span class="sxs-lookup"><span data-stu-id="df6a8-217">Application.</span></span> <span data-ttu-id="df6a8-218">Obtém arquivos que não são do PowerShell em caminhos listados na variável de ambiente **path** ($env:p Ho), incluindo arquivos. txt,. exe e. dll.</span><span class="sxs-lookup"><span data-stu-id="df6a8-218">Gets non-PowerShell files in paths listed in the **Path** environment variable ($env:path), including .txt, .exe, and .dll files.</span></span> <span data-ttu-id="df6a8-219">Para obter mais informações sobre a variável de ambiente **path** , consulte about_Environment_Variables.</span><span class="sxs-lookup"><span data-stu-id="df6a8-219">For more information about the **Path** environment variable, see about_Environment_Variables.</span></span>
- <span data-ttu-id="df6a8-220">Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="df6a8-220">Cmdlet.</span></span> <span data-ttu-id="df6a8-221">Obtém todos os cmdlets.</span><span class="sxs-lookup"><span data-stu-id="df6a8-221">Gets all cmdlets.</span></span>
- <span data-ttu-id="df6a8-222">ExternalScript.</span><span class="sxs-lookup"><span data-stu-id="df6a8-222">ExternalScript.</span></span> <span data-ttu-id="df6a8-223">Obtém todos os arquivos .ps1 nos caminhos listados na variável de ambiente **Path** ($env:path).</span><span class="sxs-lookup"><span data-stu-id="df6a8-223">Gets all .ps1 files in the paths listed in the **Path** environment variable ($env:path).</span></span>
- <span data-ttu-id="df6a8-224">Filtro e função.</span><span class="sxs-lookup"><span data-stu-id="df6a8-224">Filter and Function.</span></span> <span data-ttu-id="df6a8-225">Obtém todas as funções e os filtros avançados e simples do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df6a8-225">Gets all PowerShell advanced and simple functions and filters.</span></span>
- <span data-ttu-id="df6a8-226">Script.</span><span class="sxs-lookup"><span data-stu-id="df6a8-226">Script.</span></span> <span data-ttu-id="df6a8-227">Obtém todos os blocos de script.</span><span class="sxs-lookup"><span data-stu-id="df6a8-227">Gets all script blocks.</span></span> <span data-ttu-id="df6a8-228">Para obter scripts do PowerShell (arquivos. ps1), use o valor ExternalScript.</span><span class="sxs-lookup"><span data-stu-id="df6a8-228">To get PowerShell scripts (.ps1 files), use the ExternalScript value.</span></span>

```yaml
Type: System.Management.Automation.CommandTypes
Parameter Sets: AllCommandSet
Aliases: Type
Accepted values: Alias, Function, Filter, Cmdlet, ExternalScript, Application, Script, Workflow, Configuration, All

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="df6a8-229">-FullyQualifiedModule</span><span class="sxs-lookup"><span data-stu-id="df6a8-229">-FullyQualifiedModule</span></span>

<span data-ttu-id="df6a8-230">Especifica os módulos com nomes que são especificados na forma de objetos **ModuleSpecification** , descritos na seção **comentários** do [Construtor ModuleSpecification (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span><span class="sxs-lookup"><span data-stu-id="df6a8-230">Specifies modules with names that are specified in the form of **ModuleSpecification** objects, described in the **Remarks** section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>
<span data-ttu-id="df6a8-231">Por exemplo, o parâmetro **FullyQualifiedModule** aceita um nome de módulo que é especificado em um dos seguintes formatos:</span><span class="sxs-lookup"><span data-stu-id="df6a8-231">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in one of the following formats:</span></span>

- `@{ModuleName = "modulename"; ModuleVersion = "version_number"}`
- `@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

<span data-ttu-id="df6a8-232">**ModuleName** e **ModuleVersion** são obrigatórios, mas **Guid** é opcional.</span><span class="sxs-lookup"><span data-stu-id="df6a8-232">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span>

<span data-ttu-id="df6a8-233">Você não pode especificar o parâmetro **FullyQualifiedModule** no mesmo comando que um parâmetro de **módulo** .</span><span class="sxs-lookup"><span data-stu-id="df6a8-233">You cannot specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span> <span data-ttu-id="df6a8-234">Os dois parâmetros são mutuamente exclusivos.</span><span class="sxs-lookup"><span data-stu-id="df6a8-234">The two parameters are mutually exclusive.</span></span>

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

### <span data-ttu-id="df6a8-235">-ListImported</span><span class="sxs-lookup"><span data-stu-id="df6a8-235">-ListImported</span></span>

<span data-ttu-id="df6a8-236">Indica que esse cmdlet obtém apenas os comandos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="df6a8-236">Indicates that this cmdlet gets only commands in the current session.</span></span>

<span data-ttu-id="df6a8-237">A partir do PowerShell 3,0, por padrão, `Get-Command` o Obtém todos os comandos instalados, incluindo, entre outros, os comandos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="df6a8-237">Starting in PowerShell 3.0, by default, `Get-Command` gets all installed commands, including, but not limited to, the commands in the current session.</span></span> <span data-ttu-id="df6a8-238">No PowerShell 2,0, ele obtém apenas os comandos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="df6a8-238">In PowerShell 2.0, it gets only commands in the current session.</span></span>

<span data-ttu-id="df6a8-239">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="df6a8-239">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="df6a8-240">-Módulo</span><span class="sxs-lookup"><span data-stu-id="df6a8-240">-Module</span></span>

<span data-ttu-id="df6a8-241">Especifica uma matriz de módulos.</span><span class="sxs-lookup"><span data-stu-id="df6a8-241">Specifies an array of modules.</span></span> <span data-ttu-id="df6a8-242">Esse cmdlet obtém os comandos que vieram dos módulos especificados.</span><span class="sxs-lookup"><span data-stu-id="df6a8-242">This cmdlet gets the commands that came from the specified modules.</span></span>
<span data-ttu-id="df6a8-243">Insira os nomes dos módulos ou objetos de módulo.</span><span class="sxs-lookup"><span data-stu-id="df6a8-243">Enter the names of modules or module objects.</span></span>

<span data-ttu-id="df6a8-244">Esse parâmetro usa valores de cadeia de caracteres, mas o valor desse parâmetro também pode ser um objeto **PSModuleInfo** , como os objetos `Get-Module` retornados pelos `Import-PSSession` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="df6a8-244">This parameter takes string values, but the value of this parameter can also be a **PSModuleInfo** object, such as the objects that the `Get-Module` and `Import-PSSession` cmdlets return.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSSnapin

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="df6a8-245">-Name</span><span class="sxs-lookup"><span data-stu-id="df6a8-245">-Name</span></span>

<span data-ttu-id="df6a8-246">Especifica uma matriz de nomes.</span><span class="sxs-lookup"><span data-stu-id="df6a8-246">Specifies an array of names.</span></span> <span data-ttu-id="df6a8-247">Esse cmdlet obtém apenas os comandos que têm o nome especificado.</span><span class="sxs-lookup"><span data-stu-id="df6a8-247">This cmdlet gets only commands that have the specified name.</span></span> <span data-ttu-id="df6a8-248">Digite um nome ou padrão de nome.</span><span class="sxs-lookup"><span data-stu-id="df6a8-248">Enter a name or name pattern.</span></span> <span data-ttu-id="df6a8-249">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="df6a8-249">Wildcard characters are permitted.</span></span>

<span data-ttu-id="df6a8-250">Para obter comandos com o mesmo nome, use o parâmetro **All**.</span><span class="sxs-lookup"><span data-stu-id="df6a8-250">To get commands that have the same name, use the **All** parameter.</span></span> <span data-ttu-id="df6a8-251">Quando dois comandos têm o mesmo nome, por padrão, `Get-Command` Obtém o comando que é executado quando você digita o nome do comando.</span><span class="sxs-lookup"><span data-stu-id="df6a8-251">When two commands have the same name, by default, `Get-Command` gets the command that runs when you type the command name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: AllCommandSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="df6a8-252">-Substantivo</span><span class="sxs-lookup"><span data-stu-id="df6a8-252">-Noun</span></span>

<span data-ttu-id="df6a8-253">Especifica uma matriz de substantivos de comando.</span><span class="sxs-lookup"><span data-stu-id="df6a8-253">Specifies an array of command nouns.</span></span> <span data-ttu-id="df6a8-254">Esse cmdlet obtém comandos, que incluem cmdlets, funções e aliases, que têm nomes que incluem o substantivo especificado.</span><span class="sxs-lookup"><span data-stu-id="df6a8-254">This cmdlet gets commands, which include cmdlets, functions, and aliases, that have names that include the specified noun.</span></span> <span data-ttu-id="df6a8-255">Insira um ou mais substantivos ou padrões de substantivo.</span><span class="sxs-lookup"><span data-stu-id="df6a8-255">Enter one or more nouns or noun patterns.</span></span> <span data-ttu-id="df6a8-256">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="df6a8-256">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: CmdletSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="df6a8-257">-ParameterName</span><span class="sxs-lookup"><span data-stu-id="df6a8-257">-ParameterName</span></span>

<span data-ttu-id="df6a8-258">Especifica uma matriz de nomes de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="df6a8-258">Specifies an array of parameter names.</span></span> <span data-ttu-id="df6a8-259">Esse cmdlet obtém os comandos na sessão que têm os parâmetros especificados.</span><span class="sxs-lookup"><span data-stu-id="df6a8-259">This cmdlet gets commands in the session that have the specified parameters.</span></span> <span data-ttu-id="df6a8-260">Insira os nomes de parâmetro ou os aliases de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="df6a8-260">Enter parameter names or parameter aliases.</span></span> <span data-ttu-id="df6a8-261">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="df6a8-261">Wildcard characters are supported.</span></span>

<span data-ttu-id="df6a8-262">Os parâmetros **ParameterName** e **ParameterType** pesquisam somente comandos da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="df6a8-262">The **ParameterName** and **ParameterType** parameters search only commands in the current session.</span></span>

<span data-ttu-id="df6a8-263">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="df6a8-263">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="df6a8-264">-ParameterType</span><span class="sxs-lookup"><span data-stu-id="df6a8-264">-ParameterType</span></span>

<span data-ttu-id="df6a8-265">Especifica uma matriz de nomes de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="df6a8-265">Specifies an array of parameter names.</span></span> <span data-ttu-id="df6a8-266">Esse cmdlet obtém comandos na sessão que têm parâmetros do tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="df6a8-266">This cmdlet gets commands in the session that have parameters of the specified type.</span></span> <span data-ttu-id="df6a8-267">Digite o nome completo ou parcial de um tipo de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="df6a8-267">Enter the full name or partial name of a parameter type.</span></span> <span data-ttu-id="df6a8-268">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="df6a8-268">Wildcard characters are supported.</span></span>

<span data-ttu-id="df6a8-269">Os parâmetros **ParameterName** e **ParameterType** pesquisam somente comandos da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="df6a8-269">The **ParameterName** and **ParameterType** parameters search only commands in the current session.</span></span>

<span data-ttu-id="df6a8-270">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="df6a8-270">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSTypeName[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="df6a8-271">-ShowCommandInfo</span><span class="sxs-lookup"><span data-stu-id="df6a8-271">-ShowCommandInfo</span></span>

<span data-ttu-id="df6a8-272">Indica que este cmdlet exibe informações de comando.</span><span class="sxs-lookup"><span data-stu-id="df6a8-272">Indicates that this cmdlet displays command information.</span></span>

<span data-ttu-id="df6a8-273">Esse parâmetro foi introduzido no Windows PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="df6a8-273">This parameter was introduced in Windows PowerShell 5.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df6a8-274">-Sintaxe</span><span class="sxs-lookup"><span data-stu-id="df6a8-274">-Syntax</span></span>

<span data-ttu-id="df6a8-275">Indica que este cmdlet obtém apenas os seguintes dados especificados sobre o comando:</span><span class="sxs-lookup"><span data-stu-id="df6a8-275">Indicates that this cmdlet gets only the following specified data about the command:</span></span>

- <span data-ttu-id="df6a8-276">Aliases.</span><span class="sxs-lookup"><span data-stu-id="df6a8-276">Aliases.</span></span> <span data-ttu-id="df6a8-277">Obtém o nome padrão e a sintaxe.</span><span class="sxs-lookup"><span data-stu-id="df6a8-277">Gets the standard name and syntax.</span></span>
- <span data-ttu-id="df6a8-278">Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="df6a8-278">Cmdlets.</span></span> <span data-ttu-id="df6a8-279">Obtém a sintaxe.</span><span class="sxs-lookup"><span data-stu-id="df6a8-279">Gets the syntax.</span></span>
- <span data-ttu-id="df6a8-280">Funções e filtros.</span><span class="sxs-lookup"><span data-stu-id="df6a8-280">Functions and filters.</span></span> <span data-ttu-id="df6a8-281">Obtém a definição da função.</span><span class="sxs-lookup"><span data-stu-id="df6a8-281">Gets the function definition.</span></span>
- <span data-ttu-id="df6a8-282">Scripts e aplicativos ou arquivos.</span><span class="sxs-lookup"><span data-stu-id="df6a8-282">Scripts and applications or files.</span></span> <span data-ttu-id="df6a8-283">Obtém o caminho e o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="df6a8-283">Gets the path and filename.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="df6a8-284">-TotalCount</span><span class="sxs-lookup"><span data-stu-id="df6a8-284">-TotalCount</span></span>

<span data-ttu-id="df6a8-285">Especifica o número de comandos a serem obtidos.</span><span class="sxs-lookup"><span data-stu-id="df6a8-285">Specifies the number of commands to get.</span></span> <span data-ttu-id="df6a8-286">Você pode usar esse parâmetro para limitar a saída de um comando.</span><span class="sxs-lookup"><span data-stu-id="df6a8-286">You can use this parameter to limit the output of a command.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="df6a8-287">-UseAbbreviationExpansion</span><span class="sxs-lookup"><span data-stu-id="df6a8-287">-UseAbbreviationExpansion</span></span>

<span data-ttu-id="df6a8-288">Indica o uso da correspondência dos caracteres no comando para localizar com caracteres maiúsculos em um comando.</span><span class="sxs-lookup"><span data-stu-id="df6a8-288">Indicates using matching of the characters in the command to find with uppercase characters in a command.</span></span> <span data-ttu-id="df6a8-289">Por exemplo, `i-psdf` corresponderia `Import-PowerShellDataFile` como cada um dos caracteres a serem encontrados corresponde a um caractere maiúsculo no resultado.</span><span class="sxs-lookup"><span data-stu-id="df6a8-289">For example, `i-psdf` would match `Import-PowerShellDataFile` as each of the characters to find matches an uppercase character in the result.</span></span> <span data-ttu-id="df6a8-290">Ao usar esse tipo de correspondência, qualquer caractere curinga resultará em nenhuma correspondência.</span><span class="sxs-lookup"><span data-stu-id="df6a8-290">When using this type of match, any wildcards will result in no matches.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AllCommandSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="df6a8-291">-UseFuzzyMatching</span><span class="sxs-lookup"><span data-stu-id="df6a8-291">-UseFuzzyMatching</span></span>

<span data-ttu-id="df6a8-292">Indica o uso de um algoritmo de correspondência difusa ao localizar comandos.</span><span class="sxs-lookup"><span data-stu-id="df6a8-292">Indicates using a fuzzy matching algorithm when finding commands.</span></span> <span data-ttu-id="df6a8-293">A ordem da saída é de correspondência mais próxima à correspondência menos provável.</span><span class="sxs-lookup"><span data-stu-id="df6a8-293">The order of the output is from closest match to least likely match.</span></span> <span data-ttu-id="df6a8-294">Curingas não devem ser usados com correspondência difusa, pois ele tentará corresponder a comandos que podem conter esses caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="df6a8-294">Wildcards should not be used with fuzzy matching as it will attempt to match commands that may contain those wildcard characters.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AllCommandSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df6a8-295">-Verbo</span><span class="sxs-lookup"><span data-stu-id="df6a8-295">-Verb</span></span>

<span data-ttu-id="df6a8-296">Especifica uma matriz de verbos de comando.</span><span class="sxs-lookup"><span data-stu-id="df6a8-296">Specifies an array of command verbs.</span></span> <span data-ttu-id="df6a8-297">Esse cmdlet obtém comandos, que incluem cmdlets, funções e aliases, que têm nomes que incluem o verbo especificado.</span><span class="sxs-lookup"><span data-stu-id="df6a8-297">This cmdlet gets commands, which include cmdlets, functions, and aliases, that have names that include the specified verb.</span></span> <span data-ttu-id="df6a8-298">Insira um ou mais verbos ou padrões de verbos.</span><span class="sxs-lookup"><span data-stu-id="df6a8-298">Enter one or more verbs or verb patterns.</span></span> <span data-ttu-id="df6a8-299">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="df6a8-299">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: CmdletSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="df6a8-300">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="df6a8-300">CommonParameters</span></span>

<span data-ttu-id="df6a8-301">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="df6a8-301">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="df6a8-302">Para obter mais informações, confira [about_CommonParameters](About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="df6a8-302">For more information, see [about_CommonParameters](About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="df6a8-303">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="df6a8-303">INPUTS</span></span>

### <span data-ttu-id="df6a8-304">System.String</span><span class="sxs-lookup"><span data-stu-id="df6a8-304">System.String</span></span>

<span data-ttu-id="df6a8-305">Você pode canalizar nomes de comando para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="df6a8-305">You can pipe command names to this cmdlet.</span></span>

## <span data-ttu-id="df6a8-306">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="df6a8-306">OUTPUTS</span></span>

### <span data-ttu-id="df6a8-307">System. Management. Automation. CommandInfo</span><span class="sxs-lookup"><span data-stu-id="df6a8-307">System.Management.Automation.CommandInfo</span></span>

<span data-ttu-id="df6a8-308">Esse cmdlet retorna objetos derivados da classe **CommandInfo** .</span><span class="sxs-lookup"><span data-stu-id="df6a8-308">This cmdlet returns objects derived from the **CommandInfo** class.</span></span> <span data-ttu-id="df6a8-309">O tipo de objeto retornado depende do tipo de comando que `Get-Command` obtém.</span><span class="sxs-lookup"><span data-stu-id="df6a8-309">The type of object that is returned depends on the type of command that `Get-Command` gets.</span></span>

### <span data-ttu-id="df6a8-310">System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="df6a8-310">System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="df6a8-311">Representa aliases.</span><span class="sxs-lookup"><span data-stu-id="df6a8-311">Represents aliases.</span></span>

### <span data-ttu-id="df6a8-312">System. Management. Automation. ApplicationInfo</span><span class="sxs-lookup"><span data-stu-id="df6a8-312">System.Management.Automation.ApplicationInfo</span></span>

<span data-ttu-id="df6a8-313">Representa aplicativos e arquivos.</span><span class="sxs-lookup"><span data-stu-id="df6a8-313">Represents applications and files.</span></span>

### <span data-ttu-id="df6a8-314">System. Management. Automation. CmdletInfo</span><span class="sxs-lookup"><span data-stu-id="df6a8-314">System.Management.Automation.CmdletInfo</span></span>

<span data-ttu-id="df6a8-315">Representa cmdlets.</span><span class="sxs-lookup"><span data-stu-id="df6a8-315">Represents cmdlets.</span></span>

### <span data-ttu-id="df6a8-316">System. Management. Automation. FunctionInfo</span><span class="sxs-lookup"><span data-stu-id="df6a8-316">System.Management.Automation.FunctionInfo</span></span>

<span data-ttu-id="df6a8-317">Representa funções e filtros.</span><span class="sxs-lookup"><span data-stu-id="df6a8-317">Represents functions and filters.</span></span>

## <span data-ttu-id="df6a8-318">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="df6a8-318">NOTES</span></span>

* <span data-ttu-id="df6a8-319">Quando mais de um comando com o mesmo nome está disponível para a sessão, `Get-Command` o retorna o comando que é executado quando você digita o nome do comando.</span><span class="sxs-lookup"><span data-stu-id="df6a8-319">When more than one command that has the same name is available to the session, `Get-Command` returns the command that runs when you type the command name.</span></span> <span data-ttu-id="df6a8-320">Para obter comandos com o mesmo nome, listados em ordem de execução, use o parâmetro **All** .</span><span class="sxs-lookup"><span data-stu-id="df6a8-320">To get commands that have the same name, listed in run order, use the **All** parameter.</span></span> <span data-ttu-id="df6a8-321">Para obter mais informações, confira [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="df6a8-321">For more information, see [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md).</span></span>
* <span data-ttu-id="df6a8-322">Quando um módulo é importado automaticamente, o efeito é o mesmo que usar o `Import-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="df6a8-322">When a module is imported automatically, the effect is the same as using the `Import-Module` cmdlet.</span></span> <span data-ttu-id="df6a8-323">O módulo pode adicionar comandos, tipos e arquivos de formatação e executar scripts na sessão.</span><span class="sxs-lookup"><span data-stu-id="df6a8-323">The module can add commands, types and formatting files, and run scripts in the session.</span></span>
  <span data-ttu-id="df6a8-324">Para habilitar, desabilitar e configurar a importação automática de módulos, use a `$PSModuleAutoLoadingPreference` variável de preferência.</span><span class="sxs-lookup"><span data-stu-id="df6a8-324">To enable, disable, and configuration automatic importing of modules, use the `$PSModuleAutoLoadingPreference` preference variable.</span></span> <span data-ttu-id="df6a8-325">Para obter mais informações, consulte [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="df6a8-325">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

## <span data-ttu-id="df6a8-326">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="df6a8-326">RELATED LINKS</span></span>

[<span data-ttu-id="df6a8-327">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="df6a8-327">Export-PSSession</span></span>](../Microsoft.PowerShell.Utility/Export-PSSession.md)

[<span data-ttu-id="df6a8-328">Get-Help</span><span class="sxs-lookup"><span data-stu-id="df6a8-328">Get-Help</span></span>](Get-Help.md)

[<span data-ttu-id="df6a8-329">Get-Member</span><span class="sxs-lookup"><span data-stu-id="df6a8-329">Get-Member</span></span>](../Microsoft.PowerShell.Utility/Get-Member.md)

[<span data-ttu-id="df6a8-330">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="df6a8-330">Get-PSDrive</span></span>](../Microsoft.PowerShell.Management/Get-PSDrive.md)

[<span data-ttu-id="df6a8-331">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="df6a8-331">Import-PSSession</span></span>](../Microsoft.PowerShell.Utility/Import-PSSession.md)

[<span data-ttu-id="df6a8-332">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="df6a8-332">about_Command_Precedence</span></span>](About/about_Command_Precedence.md)

