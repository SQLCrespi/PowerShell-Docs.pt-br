---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/05/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-command?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Command
ms.openlocfilehash: 092b7bff345340a8e2d30136517537c375074df1
ms.sourcegitcommit: d95a7255f6775b2973aa9473611185a5583881ff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/07/2021
ms.locfileid: "106555450"
---
# <span data-ttu-id="f65ec-102">Get-Command</span><span class="sxs-lookup"><span data-stu-id="f65ec-102">Get-Command</span></span>

## <span data-ttu-id="f65ec-103">Sinopse</span><span class="sxs-lookup"><span data-stu-id="f65ec-103">Synopsis</span></span>
<span data-ttu-id="f65ec-104">Obtém todos os comandos.</span><span class="sxs-lookup"><span data-stu-id="f65ec-104">Gets all commands.</span></span>

## <span data-ttu-id="f65ec-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f65ec-105">Syntax</span></span>

### <span data-ttu-id="f65ec-106">CmdletSet (padrão)</span><span class="sxs-lookup"><span data-stu-id="f65ec-106">CmdletSet (Default)</span></span>

```
Get-Command [-Verb <String[]>] [-Noun <String[]>] [-Module <String[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [-TotalCount <Int32>] [-Syntax] [-ShowCommandInfo]
 [[-ArgumentList] <Object[]>] [-All] [-ListImported] [-ParameterName <String[]>]
 [-ParameterType <PSTypeName[]>] [<CommonParameters>]
```

### <span data-ttu-id="f65ec-107">Setcommandset</span><span class="sxs-lookup"><span data-stu-id="f65ec-107">AllCommandSet</span></span>

```
Get-Command [[-Name] <String[]>] [-Module <String[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [-CommandType <CommandTypes>] [-TotalCount <Int32>]
 [-Syntax] [-ShowCommandInfo] [[-ArgumentList] <Object[]>] [-All] [-ListImported]
 [-ParameterName <String[]>] [-ParameterType <PSTypeName[]>] [-UseFuzzyMatching]
 [-UseAbbreviationExpansion] [<CommonParameters>]
```

## <span data-ttu-id="f65ec-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="f65ec-108">Description</span></span>

<span data-ttu-id="f65ec-109">O `Get-Command` cmdlet obtém todos os comandos que estão instalados no computador, incluindo cmdlets, aliases, funções, filtros, scripts e aplicativos.</span><span class="sxs-lookup"><span data-stu-id="f65ec-109">The `Get-Command` cmdlet gets all commands that are installed on the computer, including cmdlets, aliases, functions, filters, scripts, and applications.</span></span> <span data-ttu-id="f65ec-110">`Get-Command` Obtém os comandos de módulos e comandos do PowerShell que foram importados de outras sessões.</span><span class="sxs-lookup"><span data-stu-id="f65ec-110">`Get-Command` gets the commands from PowerShell modules and commands that were imported from other sessions.</span></span> <span data-ttu-id="f65ec-111">Para obter somente comandos que foram importados para a sessão atual, use o parâmetro **ListImported**.</span><span class="sxs-lookup"><span data-stu-id="f65ec-111">To get only commands that have been imported into the current session, use the **ListImported** parameter.</span></span>

<span data-ttu-id="f65ec-112">Sem parâmetros, `Get-Command` Obtém todos os cmdlets, funções e aliases instalados no computador.</span><span class="sxs-lookup"><span data-stu-id="f65ec-112">Without parameters, `Get-Command` gets all of the cmdlets, functions, and aliases installed on the computer.</span></span> <span data-ttu-id="f65ec-113">`Get-Command *` Obtém todos os tipos de comandos, incluindo todos os arquivos que não são do PowerShell na variável de ambiente Path ( `$env:Path` ), que é listada no tipo de comando Application.</span><span class="sxs-lookup"><span data-stu-id="f65ec-113">`Get-Command *` gets all types of commands, including all of the non-PowerShell files in the Path environment variable (`$env:Path`), which it lists in the Application command type.</span></span>

<span data-ttu-id="f65ec-114">`Get-Command` que usa o nome exato do comando, sem caracteres curinga, importa automaticamente o módulo que contém o comando para que você possa usar o comando imediatamente.</span><span class="sxs-lookup"><span data-stu-id="f65ec-114">`Get-Command` that uses the exact name of the command, without wildcard characters, automatically imports the module that contains the command so that you can use the command immediately.</span></span> <span data-ttu-id="f65ec-115">Para habilitar, desabilitar e configurar a importação automática de módulos, use a `$PSModuleAutoLoadingPreference` variável de preferência.</span><span class="sxs-lookup"><span data-stu-id="f65ec-115">To enable, disable, and configure automatic importing of modules, use the `$PSModuleAutoLoadingPreference` preference variable.</span></span> <span data-ttu-id="f65ec-116">Para obter mais informações, consulte [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="f65ec-116">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="f65ec-117">`Get-Command` Obtém seus dados diretamente do código de comando, ao contrário de `Get-Help` , que obtém suas informações dos tópicos da ajuda.</span><span class="sxs-lookup"><span data-stu-id="f65ec-117">`Get-Command` gets its data directly from the command code, unlike `Get-Help`, which gets its information from help topics.</span></span>

<span data-ttu-id="f65ec-118">A partir do Windows PowerShell 5,0, os resultados do `Get-Command` cmdlet exibem uma coluna de **versão** por padrão.</span><span class="sxs-lookup"><span data-stu-id="f65ec-118">Starting in Windows PowerShell 5.0, results of the `Get-Command` cmdlet display a **Version** column by default.</span></span> <span data-ttu-id="f65ec-119">Uma nova propriedade **version** foi adicionada à classe **CommandInfo** .</span><span class="sxs-lookup"><span data-stu-id="f65ec-119">A new **Version** property has been added to the **CommandInfo** class.</span></span>

## <span data-ttu-id="f65ec-120">Exemplos</span><span class="sxs-lookup"><span data-stu-id="f65ec-120">Examples</span></span>

### <span data-ttu-id="f65ec-121">Exemplo 1: obter cmdlets, funções e aliases</span><span class="sxs-lookup"><span data-stu-id="f65ec-121">Example 1: Get cmdlets, functions, and aliases</span></span>

<span data-ttu-id="f65ec-122">Esse comando obtém os cmdlets, as funções e os aliases do PowerShell instalados no computador.</span><span class="sxs-lookup"><span data-stu-id="f65ec-122">This command gets the PowerShell cmdlets, functions, and aliases that are installed on the computer.</span></span>

```powershell
Get-Command
```

### <span data-ttu-id="f65ec-123">Exemplo 2: obter comandos na sessão atual</span><span class="sxs-lookup"><span data-stu-id="f65ec-123">Example 2: Get commands in the current session</span></span>

<span data-ttu-id="f65ec-124">Este comando usa o parâmetro **ListImported** para obter apenas os comandos da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="f65ec-124">This command uses the **ListImported** parameter to get only the commands in the current session.</span></span>

```powershell
Get-Command -ListImported
```

### <span data-ttu-id="f65ec-125">Exemplo 3: obter cmdlets e exibi-los na ordem</span><span class="sxs-lookup"><span data-stu-id="f65ec-125">Example 3: Get cmdlets and display them in order</span></span>

<span data-ttu-id="f65ec-126">Esse comando obtém todos os cmdlets, os classifica em ordem alfabética pelo substantivo no nome do cmdlet e, em seguida, os exibe em grupos baseados no substantivo.</span><span class="sxs-lookup"><span data-stu-id="f65ec-126">This command gets all of the cmdlets, sorts them alphabetically by the noun in the cmdlet name, and then displays them in noun-based groups.</span></span> <span data-ttu-id="f65ec-127">Essa exibição pode ajudar a localizar os cmdlets para uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="f65ec-127">This display can help you find the cmdlets for a task.</span></span>

```powershell
Get-Command -Type Cmdlet | Sort-Object -Property Noun | Format-Table -GroupBy Noun
```

### <span data-ttu-id="f65ec-128">Exemplo 4: obter comandos em um módulo</span><span class="sxs-lookup"><span data-stu-id="f65ec-128">Example 4: Get commands in a module</span></span>

<span data-ttu-id="f65ec-129">Esse comando usa o parâmetro **Module** para obter os comandos nos módulos Microsoft. PowerShell. Security e Microsoft. PowerShell. Utility.</span><span class="sxs-lookup"><span data-stu-id="f65ec-129">This command uses the **Module** parameter to get the commands in the Microsoft.PowerShell.Security and Microsoft.PowerShell.Utility modules.</span></span>

```powershell
Get-Command -Module Microsoft.PowerShell.Security, Microsoft.PowerShell.Utility
```

### <span data-ttu-id="f65ec-130">Exemplo 5: obter informações sobre um cmdlet</span><span class="sxs-lookup"><span data-stu-id="f65ec-130">Example 5: Get information about a cmdlet</span></span>

<span data-ttu-id="f65ec-131">Esse comando obtém informações sobre o `Get-AppLockerPolicy` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f65ec-131">This command gets information about the `Get-AppLockerPolicy` cmdlet.</span></span> <span data-ttu-id="f65ec-132">Ele também importa o módulo **AppLocker**, que adiciona todos os comandos no módulo **AppLocker** à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="f65ec-132">It also imports the **AppLocker** module, which adds all of the commands in the **AppLocker** module to the current session.</span></span>

```powershell
Get-Command Get-AppLockerPolicy
```

<span data-ttu-id="f65ec-133">Quando um módulo é importado automaticamente, o efeito é o mesmo que usar o cmdlet Import-Module.</span><span class="sxs-lookup"><span data-stu-id="f65ec-133">When a module is imported automatically, the effect is the same as using the Import-Module cmdlet.</span></span>
<span data-ttu-id="f65ec-134">O módulo pode adicionar comandos, tipos e arquivos de formatação e executar scripts na sessão.</span><span class="sxs-lookup"><span data-stu-id="f65ec-134">The module can add commands, types and formatting files, and run scripts in the session.</span></span> <span data-ttu-id="f65ec-135">Para habilitar, desabilitar e configurar a importação automática de módulos, use a `$PSModuleAutoLoadingPreference` variável de preferência.</span><span class="sxs-lookup"><span data-stu-id="f65ec-135">To enable, disable, and configuration automatic importing of modules, use the `$PSModuleAutoLoadingPreference` preference variable.</span></span> <span data-ttu-id="f65ec-136">Para obter mais informações, consulte [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="f65ec-136">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

### <span data-ttu-id="f65ec-137">Exemplo 6: obter a sintaxe de um cmdlet</span><span class="sxs-lookup"><span data-stu-id="f65ec-137">Example 6: Get the syntax of a cmdlet</span></span>

<span data-ttu-id="f65ec-138">Esse comando usa os parâmetros **ArgumentList** e **Syntax** para obter a sintaxe do `Get-ChildItem` cmdlet quando ele é usado na unidade CERT:.</span><span class="sxs-lookup"><span data-stu-id="f65ec-138">This command uses the **ArgumentList** and **Syntax** parameters to get the syntax of the `Get-ChildItem` cmdlet when it is used in the Cert: drive.</span></span> <span data-ttu-id="f65ec-139">A unidade CERT: é uma unidade do PowerShell que o provedor de certificado adiciona à sessão.</span><span class="sxs-lookup"><span data-stu-id="f65ec-139">The Cert: drive is a PowerShell drive that the Certificate Provider adds to the session.</span></span>

```powershell
Get-Command  -Name Get-Childitem -Args Cert: -Syntax
```

<span data-ttu-id="f65ec-140">Ao comparar a sintaxe exibida na saída com a sintaxe que é exibida quando você omite o parâmetro **args** (**ArgumentList**), você verá que o **provedor de certificado** adiciona um parâmetro dinâmico, **CodeSigningCert**, ao `Get-ChildItem` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f65ec-140">When you compare the syntax displayed in the output with the syntax that is displayed when you omit the **Args** (**ArgumentList**) parameter, you'll see that the **Certificate provider** adds a dynamic parameter, **CodeSigningCert**, to the `Get-ChildItem` cmdlet.</span></span>

<span data-ttu-id="f65ec-141">Para obter mais informações sobre o provedor de certificados, consulte [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span><span class="sxs-lookup"><span data-stu-id="f65ec-141">For more information about the Certificate provider, see [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span></span>

### <span data-ttu-id="f65ec-142">Exemplo 7: obter parâmetros dinâmicos</span><span class="sxs-lookup"><span data-stu-id="f65ec-142">Example 7: Get dynamic parameters</span></span>

<span data-ttu-id="f65ec-143">O comando no exemplo usa a `Get-DynamicParameters` função para obter os parâmetros dinâmicos que o provedor de certificado adiciona ao `Get-ChildItem` cmdlet quando ele é usado na unidade CERT:.</span><span class="sxs-lookup"><span data-stu-id="f65ec-143">The command in the example uses the `Get-DynamicParameters` function to get the dynamic parameters that the Certificate provider adds to the `Get-ChildItem` cmdlet when it is used in the Cert: drive.</span></span>

```powershell
function Get-DynamicParameters
{
    param ($Cmdlet, $PSDrive)
    (Get-Command -Name $Cmdlet -ArgumentList $PSDrive).ParameterSets | 
      ForEach-Object {$_.Parameters} | 
        Where-Object { $_.IsDynamic } | 
          Select-Object -Property Name -Unique
}
Get-DynamicParameters -Cmdlet Get-ChildItem -PSDrive Cert:
```

```Output
Name
----
CodeSigningCert
```

<span data-ttu-id="f65ec-144">A `Get-DynamicParameters` função neste exemplo obtém os parâmetros dinâmicos de um cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f65ec-144">The `Get-DynamicParameters` function in this example gets the dynamic parameters of a cmdlet.</span></span> <span data-ttu-id="f65ec-145">Essa é uma alternativa ao método usado no exemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="f65ec-145">This is an alternative to the method used in the previous example.</span></span> <span data-ttu-id="f65ec-146">O parâmetro dinâmico pode ser adicionado a um cmdlet por outro cmdlet ou por um provedor.</span><span class="sxs-lookup"><span data-stu-id="f65ec-146">Dynamic parameter can be added to a cmdlet by another cmdlet or a provider.</span></span>

### <span data-ttu-id="f65ec-147">Exemplo 8: obter todos os comandos de todos os tipos</span><span class="sxs-lookup"><span data-stu-id="f65ec-147">Example 8: Get all commands of all types</span></span>

<span data-ttu-id="f65ec-148">Esse comando obtém todos os comandos de todos os tipos no computador local, incluindo arquivos executáveis nos caminhos da variável de ambiente **path** ( `$env:path` ).</span><span class="sxs-lookup"><span data-stu-id="f65ec-148">This command gets all commands of all types on the local computer, including executable files in the paths of the **Path** environment variable (`$env:path`).</span></span>

```powershell
Get-Command *
```

<span data-ttu-id="f65ec-149">Ele retorna um objeto **ApplicationInfo** (System.Management.Automation.ApplicationInfo) para cada arquivo e não um objeto **FileInfo** (System.IO.FileInfo).</span><span class="sxs-lookup"><span data-stu-id="f65ec-149">It returns an **ApplicationInfo** object (System.Management.Automation.ApplicationInfo) for each file, not a **FileInfo** object (System.IO.FileInfo).</span></span>

### <span data-ttu-id="f65ec-150">Exemplo 9: obter cmdlets usando um nome de parâmetro e tipo</span><span class="sxs-lookup"><span data-stu-id="f65ec-150">Example 9: Get cmdlets by using a parameter name and type</span></span>

<span data-ttu-id="f65ec-151">Esse comando obtém os cmdlets que têm um parâmetro cujo nome inclui autenticação e cujo tipo é **AuthenticationMechanism**.</span><span class="sxs-lookup"><span data-stu-id="f65ec-151">This command gets cmdlets that have a parameter whose name includes Auth and whose type is **AuthenticationMechanism**.</span></span>

```powershell
Get-Command -ParameterName *Auth* -ParameterType AuthenticationMechanism
```

<span data-ttu-id="f65ec-152">É possível usar um comando como este para localizar cmdlets que permitem que você especifique o método usado para autenticar o usuário.</span><span class="sxs-lookup"><span data-stu-id="f65ec-152">You can use a command like this one to find cmdlets that let you specify the method that is used to authenticate the user.</span></span>

<span data-ttu-id="f65ec-153">O parâmetro **ParameterType** distingue parâmetros que usam um valor **AuthenticationMechanism** dos que usam um parâmetro **AuthenticationLevel**, mesmo quando tiverem nomes semelhantes.</span><span class="sxs-lookup"><span data-stu-id="f65ec-153">The **ParameterType** parameter distinguishes parameters that take an **AuthenticationMechanism** value from those that take an **AuthenticationLevel** parameter, even when they have similar names.</span></span>

### <span data-ttu-id="f65ec-154">Exemplo 10: obter um alias</span><span class="sxs-lookup"><span data-stu-id="f65ec-154">Example 10: Get an alias</span></span>

<span data-ttu-id="f65ec-155">Este exemplo mostra como usar o `Get-Command` cmdlet com um alias.</span><span class="sxs-lookup"><span data-stu-id="f65ec-155">This example shows how to use the `Get-Command` cmdlet with an alias.</span></span>

```powershell
Get-Command -Name dir
```

```Output
CommandType     Name                                               ModuleName
-----------     ----                                               ----------
Alias           dir -> Get-ChildItem
```

<span data-ttu-id="f65ec-156">Embora normalmente seja usado em cmdlets e funções, o `Get-Command` também obtém scripts, funções, aliases e arquivos executáveis.</span><span class="sxs-lookup"><span data-stu-id="f65ec-156">Although it is typically used on cmdlets and functions, `Get-Command` also gets scripts, functions, aliases, and executable files.</span></span>

<span data-ttu-id="f65ec-157">A saída do comando mostra o modo de exibição especial do valor de propriedade **Name** para aliases.</span><span class="sxs-lookup"><span data-stu-id="f65ec-157">The output of the command shows the special view of the **Name** property value for aliases.</span></span> <span data-ttu-id="f65ec-158">O modo de exibição mostra o alias e o nome completo do comando.</span><span class="sxs-lookup"><span data-stu-id="f65ec-158">The view shows the alias and the full command name.</span></span>

### <span data-ttu-id="f65ec-159">Exemplo 11: obter a sintaxe de um alias</span><span class="sxs-lookup"><span data-stu-id="f65ec-159">Example 11: Get Syntax from an alias</span></span>

<span data-ttu-id="f65ec-160">Este exemplo mostra como obter a sintaxe junto com o nome padrão de um alias.</span><span class="sxs-lookup"><span data-stu-id="f65ec-160">This example shows how to get the syntax along with the standard name of an alias.</span></span>

<span data-ttu-id="f65ec-161">A saída do comando mostra o alias rotulado com o nome padrão, seguido pela sintaxe.</span><span class="sxs-lookup"><span data-stu-id="f65ec-161">The output of the command shows the labeled alias with the standard name, followed by the syntax.</span></span>

```powershell
Get-Command -Name dir -Syntax
```

```Output
dir (alias) -> Get-ChildItem

dir [[-Path] <string[]>] [[-Filter] <string>] [-Include <string[]>] [-Exclude <string[]>] [-Recurse] [-Depth <uint>] [-Force] [-Name] [-Attributes <FlagsExpression[FileAttributes]>] [-FollowSymlink] [-Directory] [-File] [-Hidden] [-ReadOnly] [-System] [<CommonParameters>]

dir [[-Filter] <string>] -LiteralPath <string[]> [-Include <string[]>] [-Exclude <string[]>] [-Recurse] [-Depth <uint>] [-Force] [-Name] [-Attributes <FlagsExpression[FileAttributes]>] [-FollowSymlink] [-Directory] [-File] [-Hidden] [-ReadOnly] [-System] [<CommonParameters>]
```

### <span data-ttu-id="f65ec-162">Exemplo 12: obter todas as instâncias do comando do bloco de notas</span><span class="sxs-lookup"><span data-stu-id="f65ec-162">Example 12: Get all instances of the Notepad command</span></span>

<span data-ttu-id="f65ec-163">Este exemplo usa o parâmetro **All** do `Get-Command` cmdlet para mostrar todas as instâncias do `Notepad` comando no computador local.</span><span class="sxs-lookup"><span data-stu-id="f65ec-163">This example uses the **All** parameter of the `Get-Command` cmdlet to show all instances of the `Notepad` command on the local computer.</span></span>

```powershell
Get-Command Notepad -All | Format-Table CommandType, Name, Definition
```

```Output
CommandType     Name           Definition
-----------     ----           ----------
Application     notepad.exe    C:\WINDOWS\system32\notepad.exe
Application     NOTEPAD.EXE    C:\WINDOWS\NOTEPAD.EXE
```

<span data-ttu-id="f65ec-164">O parâmetro **All** é útil quando há mais de um comando com o mesmo nome na sessão.</span><span class="sxs-lookup"><span data-stu-id="f65ec-164">The **All** parameter is useful when there is more than one command with the same name in the session.</span></span>

<span data-ttu-id="f65ec-165">A partir do Windows PowerShell 3,0, por padrão, quando a sessão inclui vários comandos com o mesmo nome, `Get-Command` obtém apenas o comando que é executado quando você digita o nome do comando.</span><span class="sxs-lookup"><span data-stu-id="f65ec-165">Beginning in Windows PowerShell 3.0, by default, when the session includes multiple commands with the same name, `Get-Command` gets only the command that runs when you type the command name.</span></span> <span data-ttu-id="f65ec-166">Com o parâmetro **All** , `Get-Command` Obtém todos os comandos com o nome especificado e os retorna na ordem de precedência de execução.</span><span class="sxs-lookup"><span data-stu-id="f65ec-166">With the **All** parameter, `Get-Command` gets all commands with the specified name and returns them in execution precedence order.</span></span> <span data-ttu-id="f65ec-167">Para executar um comando que não seja o primeiro da lista, digite o caminho totalmente qualificado para o comando.</span><span class="sxs-lookup"><span data-stu-id="f65ec-167">To run a command other than the first one in the list, type the fully qualified path to the command.</span></span>

<span data-ttu-id="f65ec-168">Para obter mais informações sobre a precedência de comando, consulte [about_Command_Precedence](About/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="f65ec-168">For more information about command precedence, see [about_Command_Precedence](About/about_Command_Precedence.md).</span></span>

### <span data-ttu-id="f65ec-169">Exemplo 13: obter o nome de um módulo que contém um cmdlet</span><span class="sxs-lookup"><span data-stu-id="f65ec-169">Example 13: Get the name of a module that contains a cmdlet</span></span>

<span data-ttu-id="f65ec-170">Esse comando obtém o nome do módulo no qual o `Get-Date` cmdlet foi originado.</span><span class="sxs-lookup"><span data-stu-id="f65ec-170">This command gets the name of the module in which the `Get-Date` cmdlet originated.</span></span>
<span data-ttu-id="f65ec-171">O comando usa a propriedade **ModuleName** de todos os comandos.</span><span class="sxs-lookup"><span data-stu-id="f65ec-171">The command uses the **ModuleName** property of all commands.</span></span>

```powershell
(Get-Command Get-Date).ModuleName
```

```Output
Microsoft.PowerShell.Utility
```

<span data-ttu-id="f65ec-172">Esse formato de comando funciona em comandos em módulos do PowerShell, mesmo que eles não sejam importados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="f65ec-172">This command format works on commands in PowerShell modules, even if they are not imported into the session.</span></span>

### <span data-ttu-id="f65ec-173">Exemplo 14: obter cmdlets e funções que têm um tipo de saída</span><span class="sxs-lookup"><span data-stu-id="f65ec-173">Example 14: Get cmdlets and functions that have an output type</span></span>

```powershell
Get-Command -Type Cmdlet | Where-Object OutputType | Format-List -Property Name, OutputType
```

<span data-ttu-id="f65ec-174">Esse comando obtém os cmdlets e funções que têm um tipo de saída e os tipos de objetos que eles retornam.</span><span class="sxs-lookup"><span data-stu-id="f65ec-174">This command gets the cmdlets and functions that have an output type and the type of objects that they return.</span></span>

<span data-ttu-id="f65ec-175">A primeira parte do comando obtém todos os cmdlets.</span><span class="sxs-lookup"><span data-stu-id="f65ec-175">The first part of the command gets all cmdlets.</span></span> <span data-ttu-id="f65ec-176">Um operador de pipeline ( `|` ) envia os cmdlets para o `Where-Object` cmdlet, que seleciona apenas aqueles nos quais a propriedade **OutputType** é populada.</span><span class="sxs-lookup"><span data-stu-id="f65ec-176">A pipeline operator (`|`) sends the cmdlets to the `Where-Object` cmdlet, which selects only the ones in which the **OutputType** property is populated.</span></span> <span data-ttu-id="f65ec-177">Outro operador de pipeline envia os objetos de cmdlet selecionados para o `Format-List` cmdlet, que exibe o nome e o tipo de saída de cada cmdlet em uma lista.</span><span class="sxs-lookup"><span data-stu-id="f65ec-177">Another pipeline operator sends the selected cmdlet objects to the `Format-List` cmdlet, which displays the name and output type of each cmdlet in a list.</span></span>

<span data-ttu-id="f65ec-178">A propriedade **OutputType** de um objeto **CommandInfo** tem um valor não nulo somente quando o código do cmdlet define o atributo **OutputType** para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f65ec-178">The **OutputType** property of a **CommandInfo** object has a non-null value only when the cmdlet code defines the **OutputType** attribute for the cmdlet.</span></span>

### <span data-ttu-id="f65ec-179">Exemplo 15: obter cmdlets que usam um tipo de objeto específico como entrada</span><span class="sxs-lookup"><span data-stu-id="f65ec-179">Example 15: Get cmdlets that take a specific object type as input</span></span>

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

<span data-ttu-id="f65ec-180">Este comando localiza cmdlets que usam objetos de adaptador de rede como entrada.</span><span class="sxs-lookup"><span data-stu-id="f65ec-180">This command finds cmdlets that take net adapter objects as input.</span></span> <span data-ttu-id="f65ec-181">Você pode usar esse formato de comando para localizar os cmdlets que aceitam o tipo de objeto que qualquer comando retorna.</span><span class="sxs-lookup"><span data-stu-id="f65ec-181">You can use this command format to find the cmdlets that accept the type of objects that any command returns.</span></span>

<span data-ttu-id="f65ec-182">O comando usa a propriedade intrínseca **PSTypeNames** de todos os objetos, que obtém os tipos que descrevem o objeto.</span><span class="sxs-lookup"><span data-stu-id="f65ec-182">The command uses the **PSTypeNames** intrinsic property of all objects, which gets the types that describe the object.</span></span> <span data-ttu-id="f65ec-183">Para obter a propriedades **PSTypeNames** de um adaptador de rede e não a propriedade **PSTypeNames** de uma coleção de adaptadores de rede, o comando usa a notação de matriz para obter o primeiro adaptador de rede que o cmdlet retorna.</span><span class="sxs-lookup"><span data-stu-id="f65ec-183">To get the **PSTypeNames** property of a net adapter, and not the **PSTypeNames** property of a collection of net adapters, the command uses array notation to get the first net adapter that the cmdlet returns.</span></span>

### <span data-ttu-id="f65ec-184">Exemplo 16: obter comandos usando uma correspondência difusa</span><span class="sxs-lookup"><span data-stu-id="f65ec-184">Example 16: Get commands using a fuzzy match</span></span>

<span data-ttu-id="f65ec-185">Neste exemplo, o nome do comando deliberadamente tem um tipográfico como ' Get-commnd '.</span><span class="sxs-lookup"><span data-stu-id="f65ec-185">In this example, the name of the command deliberately has a typo as 'get-commnd'.</span></span>
<span data-ttu-id="f65ec-186">Usando a `-UseFuzzyMatching` opção, o cmdlet determinou que a melhor correspondência foi `Get-Command` seguida por outros comandos nativos no sistema que eram uma correspondência semelhante.</span><span class="sxs-lookup"><span data-stu-id="f65ec-186">Using the `-UseFuzzyMatching` switch, the cmdlet determined that the best match was `Get-Command` followed by other native commands on the system that were a similar match.</span></span>

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

## <span data-ttu-id="f65ec-187">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f65ec-187">Parameters</span></span>

### <span data-ttu-id="f65ec-188">-All</span><span class="sxs-lookup"><span data-stu-id="f65ec-188">-All</span></span>

<span data-ttu-id="f65ec-189">Indica que este cmdlet obtém todos os comandos, incluindo comandos do mesmo tipo que têm o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="f65ec-189">Indicates that this cmdlet gets all commands, including commands of the same type that have the same name.</span></span> <span data-ttu-id="f65ec-190">Por padrão, `Get-Command` o obtém apenas os comandos que são executados quando você digita o nome do comando.</span><span class="sxs-lookup"><span data-stu-id="f65ec-190">By default, `Get-Command` gets only the commands that run when you type the command name.</span></span>

<span data-ttu-id="f65ec-191">Para obter mais informações sobre o método que o PowerShell usa para selecionar o comando a ser executado quando vários comandos têm o mesmo nome, consulte [about_Command_Precedence](About/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="f65ec-191">For more information about the method that PowerShell uses to select the command to run when multiple commands have the same name, see [about_Command_Precedence](About/about_Command_Precedence.md).</span></span>
<span data-ttu-id="f65ec-192">Para obter informações sobre nomes de comando qualificados por módulo e comandos em execução que não são executados por padrão devido a um conflito de nome, consulte [about_Modules](About/about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="f65ec-192">For information about module-qualified command names and running commands that do not run by default because of a name conflict, see [about_Modules](About/about_Modules.md).</span></span>

<span data-ttu-id="f65ec-193">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="f65ec-193">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="f65ec-194">No Windows PowerShell 2,0, o `Get-Command` Obtém todos os comandos por padrão.</span><span class="sxs-lookup"><span data-stu-id="f65ec-194">In Windows PowerShell 2.0, `Get-Command` gets all commands by default.</span></span>

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

### <span data-ttu-id="f65ec-195">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="f65ec-195">-ArgumentList</span></span>

<span data-ttu-id="f65ec-196">Especifica uma matriz de argumentos.</span><span class="sxs-lookup"><span data-stu-id="f65ec-196">Specifies an array of arguments.</span></span> <span data-ttu-id="f65ec-197">Esse cmdlet obtém informações sobre um cmdlet ou uma função quando ele é usado com os parâmetros especificados ("Arguments").</span><span class="sxs-lookup"><span data-stu-id="f65ec-197">This cmdlet gets information about a cmdlet or function when it is used with the specified parameters ("arguments").</span></span> <span data-ttu-id="f65ec-198">O alias para **ArgumentList** é **Args**.</span><span class="sxs-lookup"><span data-stu-id="f65ec-198">The alias for **ArgumentList** is **Args**.</span></span>

<span data-ttu-id="f65ec-199">Para detectar parâmetros dinâmicos que estão disponíveis somente quando determinados outros parâmetros são usados, defina o valor de **ArgumentList** para os parâmetros que disparam os parâmetros dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="f65ec-199">To detect dynamic parameters that are available only when certain other parameters are used, set the value of **ArgumentList** to the parameters that trigger the dynamic parameters.</span></span>

<span data-ttu-id="f65ec-200">Para detectar os parâmetros dinâmicos que um provedor adiciona a um cmdlet, defina o valor do parâmetro **ArgumentList** como um caminho na unidade do provedor, como WSMan:, HKLM: ou CERT:.</span><span class="sxs-lookup"><span data-stu-id="f65ec-200">To detect the dynamic parameters that a provider adds to a cmdlet, set the value of the **ArgumentList** parameter to a path in the provider drive, such as WSMan:, HKLM:, or Cert:.</span></span> <span data-ttu-id="f65ec-201">Quando o comando for um cmdlet do provedor do PowerShell, digite apenas um caminho em cada comando.</span><span class="sxs-lookup"><span data-stu-id="f65ec-201">When the command is a PowerShell provider cmdlet, enter only one path in each command.</span></span> <span data-ttu-id="f65ec-202">Os cmdlets do provedor retornam apenas os parâmetros dinâmicos do primeiro caminho para o valor de **ArgumentList**.</span><span class="sxs-lookup"><span data-stu-id="f65ec-202">The provider cmdlets return only the dynamic parameters for the first path the value of **ArgumentList**.</span></span> <span data-ttu-id="f65ec-203">Para obter informações sobre os cmdlets do provedor, consulte [about_Providers](About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="f65ec-203">For information about the provider cmdlets, see [about_Providers](About/about_Providers.md).</span></span>

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

### <span data-ttu-id="f65ec-204">-CommandType</span><span class="sxs-lookup"><span data-stu-id="f65ec-204">-CommandType</span></span>

<span data-ttu-id="f65ec-205">Especifica os tipos de comandos que esse cmdlet obtém.</span><span class="sxs-lookup"><span data-stu-id="f65ec-205">Specifies the types of commands that this cmdlet gets.</span></span> <span data-ttu-id="f65ec-206">Insira um ou mais tipos de comando.</span><span class="sxs-lookup"><span data-stu-id="f65ec-206">Enter one or more command types.</span></span> <span data-ttu-id="f65ec-207">Use o **CommandType** ou seu alias, **Type**.</span><span class="sxs-lookup"><span data-stu-id="f65ec-207">Use **CommandType** or its alias, **Type**.</span></span> <span data-ttu-id="f65ec-208">Por padrão, o `Get-Command` Obtém todos os cmdlets, funções e aliases.</span><span class="sxs-lookup"><span data-stu-id="f65ec-208">By default, `Get-Command` gets all cmdlets, functions, and aliases.</span></span>

<span data-ttu-id="f65ec-209">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="f65ec-209">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f65ec-210">`Alias`: Obtém os aliases de todos os comandos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f65ec-210">`Alias`: Gets the aliases of all PowerShell commands.</span></span> <span data-ttu-id="f65ec-211">Para obter mais informações, consulte [about_Aliases](About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="f65ec-211">For more information, see [about_Aliases](About/about_Aliases.md).</span></span>
- <span data-ttu-id="f65ec-212">`All`: Obtém todos os tipos de comando.</span><span class="sxs-lookup"><span data-stu-id="f65ec-212">`All`: Gets all command types.</span></span> <span data-ttu-id="f65ec-213">Esse valor de parâmetro é o equivalente de `Get-Command *` .</span><span class="sxs-lookup"><span data-stu-id="f65ec-213">This parameter value is the equivalent of `Get-Command *`.</span></span>
- <span data-ttu-id="f65ec-214">`Application`: Obtém arquivos que não são do PowerShell em caminhos listados na variável de ambiente **path** ( `$env:path` ), incluindo arquivos. txt,. exe e. dll.</span><span class="sxs-lookup"><span data-stu-id="f65ec-214">`Application`: Gets non-PowerShell files in paths listed in the **Path** environment variable (`$env:path`), including .txt, .exe, and .dll files.</span></span> <span data-ttu-id="f65ec-215">Para obter mais informações sobre a variável de ambiente **Path**, consulte [about_Environment_Variables](About/about_Environment_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="f65ec-215">For more information about the **Path** environment variable, see [about_Environment_Variables](About/about_Environment_Variables.md).</span></span>
- <span data-ttu-id="f65ec-216">`Cmdlet`: Obtém todos os cmdlets.</span><span class="sxs-lookup"><span data-stu-id="f65ec-216">`Cmdlet`: Gets all cmdlets.</span></span>
- <span data-ttu-id="f65ec-217">`ExternalScript`: Obtém todos os arquivos. ps1 nos caminhos listados na variável de ambiente **path** ( `$env:path` ).</span><span class="sxs-lookup"><span data-stu-id="f65ec-217">`ExternalScript`: Gets all .ps1 files in the paths listed in the **Path** environment variable (`$env:path`).</span></span>
- <span data-ttu-id="f65ec-218">`Filter` e `Function` : Obtém todas as funções e os filtros avançados e simples do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f65ec-218">`Filter` and `Function`: Gets all PowerShell advanced and simple functions and filters.</span></span>
- <span data-ttu-id="f65ec-219">`Script`: Obtém todos os blocos de script.</span><span class="sxs-lookup"><span data-stu-id="f65ec-219">`Script`: Gets all script blocks.</span></span> <span data-ttu-id="f65ec-220">Para obter scripts do PowerShell (arquivos. ps1), use o `ExternalScript` valor.</span><span class="sxs-lookup"><span data-stu-id="f65ec-220">To get PowerShell scripts (.ps1 files), use the `ExternalScript` value.</span></span>

<span data-ttu-id="f65ec-221">Esses valores são definidos como uma enumeração baseada em sinalizador.</span><span class="sxs-lookup"><span data-stu-id="f65ec-221">These values are defined as a flag-based enumeration.</span></span> <span data-ttu-id="f65ec-222">Você pode combinar vários valores juntos para definir vários sinalizadores usando esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="f65ec-222">You can combine multiple values together to set multiple flags using this parameter.</span></span> <span data-ttu-id="f65ec-223">Os valores podem ser passados para o parâmetro **CommandType** como uma matriz de valores ou como uma cadeia de caracteres separada por vírgulas desses valores.</span><span class="sxs-lookup"><span data-stu-id="f65ec-223">The values can be passed to the **CommandType** parameter as an array of values or as a comma-separated string of those values.</span></span> <span data-ttu-id="f65ec-224">O cmdlet combinará os valores usando uma operação binary ou.</span><span class="sxs-lookup"><span data-stu-id="f65ec-224">The cmdlet will combine the values using a binary-OR operation.</span></span> <span data-ttu-id="f65ec-225">Passar valores como uma matriz é a opção mais simples e também permite que você use a conclusão de tabulação nos valores.</span><span class="sxs-lookup"><span data-stu-id="f65ec-225">Passing values as an array is the simplest option and also allows you to use tab-completion on the values.</span></span>

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

### <span data-ttu-id="f65ec-226">-FullyQualifiedModule</span><span class="sxs-lookup"><span data-stu-id="f65ec-226">-FullyQualifiedModule</span></span>

<span data-ttu-id="f65ec-227">Especifica os módulos com nomes que são especificados na forma de objetos **ModuleSpecification** , descritos na seção **comentários** do [Construtor ModuleSpecification (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span><span class="sxs-lookup"><span data-stu-id="f65ec-227">Specifies modules with names that are specified in the form of **ModuleSpecification** objects, described in the **Remarks** section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>
<span data-ttu-id="f65ec-228">Por exemplo, o parâmetro **FullyQualifiedModule** aceita um nome de módulo que é especificado em um dos seguintes formatos:</span><span class="sxs-lookup"><span data-stu-id="f65ec-228">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in one of the following formats:</span></span>

- `@{ModuleName = "modulename"; ModuleVersion = "version_number"}`
- `@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

<span data-ttu-id="f65ec-229">**ModuleName** e **ModuleVersion** são obrigatórios, mas **Guid** é opcional.</span><span class="sxs-lookup"><span data-stu-id="f65ec-229">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span>

<span data-ttu-id="f65ec-230">Você não pode especificar o parâmetro **FullyQualifiedModule** no mesmo comando que um parâmetro de **módulo** .</span><span class="sxs-lookup"><span data-stu-id="f65ec-230">You cannot specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span> <span data-ttu-id="f65ec-231">Os dois parâmetros são mutuamente exclusivos.</span><span class="sxs-lookup"><span data-stu-id="f65ec-231">The two parameters are mutually exclusive.</span></span>

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

### <span data-ttu-id="f65ec-232">-ListImported</span><span class="sxs-lookup"><span data-stu-id="f65ec-232">-ListImported</span></span>

<span data-ttu-id="f65ec-233">Indica que esse cmdlet obtém apenas os comandos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="f65ec-233">Indicates that this cmdlet gets only commands in the current session.</span></span>

<span data-ttu-id="f65ec-234">A partir do PowerShell 3,0, por padrão, `Get-Command` o Obtém todos os comandos instalados, incluindo, entre outros, os comandos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="f65ec-234">Starting in PowerShell 3.0, by default, `Get-Command` gets all installed commands, including, but not limited to, the commands in the current session.</span></span> <span data-ttu-id="f65ec-235">No PowerShell 2,0, ele obtém apenas os comandos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="f65ec-235">In PowerShell 2.0, it gets only commands in the current session.</span></span>

<span data-ttu-id="f65ec-236">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="f65ec-236">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="f65ec-237">-Módulo</span><span class="sxs-lookup"><span data-stu-id="f65ec-237">-Module</span></span>

<span data-ttu-id="f65ec-238">Especifica uma matriz de módulos.</span><span class="sxs-lookup"><span data-stu-id="f65ec-238">Specifies an array of modules.</span></span> <span data-ttu-id="f65ec-239">Esse cmdlet obtém os comandos que vieram dos módulos especificados.</span><span class="sxs-lookup"><span data-stu-id="f65ec-239">This cmdlet gets the commands that came from the specified modules.</span></span>
<span data-ttu-id="f65ec-240">Insira os nomes dos módulos ou objetos de módulo.</span><span class="sxs-lookup"><span data-stu-id="f65ec-240">Enter the names of modules or module objects.</span></span>

<span data-ttu-id="f65ec-241">Esse parâmetro usa valores de cadeia de caracteres, mas o valor desse parâmetro também pode ser um objeto **PSModuleInfo** , como os objetos `Get-Module` retornados pelos `Import-PSSession` cmdlets e.</span><span class="sxs-lookup"><span data-stu-id="f65ec-241">This parameter takes string values, but the value of this parameter can also be a **PSModuleInfo** object, such as the objects that the `Get-Module` and `Import-PSSession` cmdlets return.</span></span>

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

### <span data-ttu-id="f65ec-242">-Name</span><span class="sxs-lookup"><span data-stu-id="f65ec-242">-Name</span></span>

<span data-ttu-id="f65ec-243">Especifica uma matriz de nomes.</span><span class="sxs-lookup"><span data-stu-id="f65ec-243">Specifies an array of names.</span></span> <span data-ttu-id="f65ec-244">Esse cmdlet obtém apenas os comandos que têm o nome especificado.</span><span class="sxs-lookup"><span data-stu-id="f65ec-244">This cmdlet gets only commands that have the specified name.</span></span> <span data-ttu-id="f65ec-245">Digite um nome ou padrão de nome.</span><span class="sxs-lookup"><span data-stu-id="f65ec-245">Enter a name or name pattern.</span></span> <span data-ttu-id="f65ec-246">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="f65ec-246">Wildcard characters are permitted.</span></span>

<span data-ttu-id="f65ec-247">Para obter comandos com o mesmo nome, use o parâmetro **All**.</span><span class="sxs-lookup"><span data-stu-id="f65ec-247">To get commands that have the same name, use the **All** parameter.</span></span> <span data-ttu-id="f65ec-248">Quando dois comandos têm o mesmo nome, por padrão, `Get-Command` Obtém o comando que é executado quando você digita o nome do comando.</span><span class="sxs-lookup"><span data-stu-id="f65ec-248">When two commands have the same name, by default, `Get-Command` gets the command that runs when you type the command name.</span></span>

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

### <span data-ttu-id="f65ec-249">-Substantivo</span><span class="sxs-lookup"><span data-stu-id="f65ec-249">-Noun</span></span>

<span data-ttu-id="f65ec-250">Especifica uma matriz de substantivos de comando.</span><span class="sxs-lookup"><span data-stu-id="f65ec-250">Specifies an array of command nouns.</span></span> <span data-ttu-id="f65ec-251">Esse cmdlet obtém comandos, que incluem cmdlets, funções e aliases, que têm nomes que incluem o substantivo especificado.</span><span class="sxs-lookup"><span data-stu-id="f65ec-251">This cmdlet gets commands, which include cmdlets, functions, and aliases, that have names that include the specified noun.</span></span> <span data-ttu-id="f65ec-252">Insira um ou mais substantivos ou padrões de substantivo.</span><span class="sxs-lookup"><span data-stu-id="f65ec-252">Enter one or more nouns or noun patterns.</span></span> <span data-ttu-id="f65ec-253">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="f65ec-253">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="f65ec-254">-ParameterName</span><span class="sxs-lookup"><span data-stu-id="f65ec-254">-ParameterName</span></span>

<span data-ttu-id="f65ec-255">Especifica uma matriz de nomes de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="f65ec-255">Specifies an array of parameter names.</span></span> <span data-ttu-id="f65ec-256">Esse cmdlet obtém os comandos na sessão que têm os parâmetros especificados.</span><span class="sxs-lookup"><span data-stu-id="f65ec-256">This cmdlet gets commands in the session that have the specified parameters.</span></span> <span data-ttu-id="f65ec-257">Insira os nomes de parâmetro ou os aliases de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="f65ec-257">Enter parameter names or parameter aliases.</span></span> <span data-ttu-id="f65ec-258">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="f65ec-258">Wildcard characters are supported.</span></span>

<span data-ttu-id="f65ec-259">Os parâmetros **ParameterName** e **ParameterType** pesquisam somente comandos da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="f65ec-259">The **ParameterName** and **ParameterType** parameters search only commands in the current session.</span></span>

<span data-ttu-id="f65ec-260">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="f65ec-260">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="f65ec-261">-ParameterType</span><span class="sxs-lookup"><span data-stu-id="f65ec-261">-ParameterType</span></span>

<span data-ttu-id="f65ec-262">Especifica uma matriz de nomes de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="f65ec-262">Specifies an array of parameter names.</span></span> <span data-ttu-id="f65ec-263">Esse cmdlet obtém comandos na sessão que têm parâmetros do tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="f65ec-263">This cmdlet gets commands in the session that have parameters of the specified type.</span></span> <span data-ttu-id="f65ec-264">Digite o nome completo ou parcial de um tipo de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="f65ec-264">Enter the full name or partial name of a parameter type.</span></span> <span data-ttu-id="f65ec-265">Há suporte para caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="f65ec-265">Wildcard characters are supported.</span></span>

<span data-ttu-id="f65ec-266">Os parâmetros **ParameterName** e **ParameterType** pesquisam somente comandos da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="f65ec-266">The **ParameterName** and **ParameterType** parameters search only commands in the current session.</span></span>

<span data-ttu-id="f65ec-267">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="f65ec-267">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="f65ec-268">-ShowCommandInfo</span><span class="sxs-lookup"><span data-stu-id="f65ec-268">-ShowCommandInfo</span></span>

<span data-ttu-id="f65ec-269">Indica que este cmdlet exibe informações de comando.</span><span class="sxs-lookup"><span data-stu-id="f65ec-269">Indicates that this cmdlet displays command information.</span></span>

<span data-ttu-id="f65ec-270">Esse parâmetro foi introduzido no Windows PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="f65ec-270">This parameter was introduced in Windows PowerShell 5.0.</span></span>

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

### <span data-ttu-id="f65ec-271">-Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f65ec-271">-Syntax</span></span>

<span data-ttu-id="f65ec-272">Indica que este cmdlet obtém apenas os seguintes dados especificados sobre o comando:</span><span class="sxs-lookup"><span data-stu-id="f65ec-272">Indicates that this cmdlet gets only the following specified data about the command:</span></span>

- <span data-ttu-id="f65ec-273">Aliases.</span><span class="sxs-lookup"><span data-stu-id="f65ec-273">Aliases.</span></span> <span data-ttu-id="f65ec-274">Obtém o nome padrão e a sintaxe.</span><span class="sxs-lookup"><span data-stu-id="f65ec-274">Gets the standard name and syntax.</span></span>
- <span data-ttu-id="f65ec-275">Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="f65ec-275">Cmdlets.</span></span> <span data-ttu-id="f65ec-276">Obtém a sintaxe.</span><span class="sxs-lookup"><span data-stu-id="f65ec-276">Gets the syntax.</span></span>
- <span data-ttu-id="f65ec-277">Funções e filtros.</span><span class="sxs-lookup"><span data-stu-id="f65ec-277">Functions and filters.</span></span> <span data-ttu-id="f65ec-278">Obtém a definição da função.</span><span class="sxs-lookup"><span data-stu-id="f65ec-278">Gets the function definition.</span></span>
- <span data-ttu-id="f65ec-279">Scripts e aplicativos ou arquivos.</span><span class="sxs-lookup"><span data-stu-id="f65ec-279">Scripts and applications or files.</span></span> <span data-ttu-id="f65ec-280">Obtém o caminho e o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="f65ec-280">Gets the path and filename.</span></span>

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

### <span data-ttu-id="f65ec-281">-TotalCount</span><span class="sxs-lookup"><span data-stu-id="f65ec-281">-TotalCount</span></span>

<span data-ttu-id="f65ec-282">Especifica o número de comandos a serem obtidos.</span><span class="sxs-lookup"><span data-stu-id="f65ec-282">Specifies the number of commands to get.</span></span> <span data-ttu-id="f65ec-283">Você pode usar esse parâmetro para limitar a saída de um comando.</span><span class="sxs-lookup"><span data-stu-id="f65ec-283">You can use this parameter to limit the output of a command.</span></span>

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

### <span data-ttu-id="f65ec-284">-UseAbbreviationExpansion</span><span class="sxs-lookup"><span data-stu-id="f65ec-284">-UseAbbreviationExpansion</span></span>

<span data-ttu-id="f65ec-285">Indica o uso da correspondência dos caracteres no comando para localizar com caracteres maiúsculos em um comando.</span><span class="sxs-lookup"><span data-stu-id="f65ec-285">Indicates using matching of the characters in the command to find with uppercase characters in a command.</span></span> <span data-ttu-id="f65ec-286">Por exemplo, `i-psdf` corresponderia `Import-PowerShellDataFile` como cada um dos caracteres a serem encontrados corresponde a um caractere maiúsculo no resultado.</span><span class="sxs-lookup"><span data-stu-id="f65ec-286">For example, `i-psdf` would match `Import-PowerShellDataFile` as each of the characters to find matches an uppercase character in the result.</span></span> <span data-ttu-id="f65ec-287">Ao usar esse tipo de correspondência, qualquer caractere curinga resultará em nenhuma correspondência.</span><span class="sxs-lookup"><span data-stu-id="f65ec-287">When using this type of match, any wildcards will result in no matches.</span></span>

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

### <span data-ttu-id="f65ec-288">-UseFuzzyMatching</span><span class="sxs-lookup"><span data-stu-id="f65ec-288">-UseFuzzyMatching</span></span>

<span data-ttu-id="f65ec-289">Indica o uso de um algoritmo de correspondência difusa ao localizar comandos.</span><span class="sxs-lookup"><span data-stu-id="f65ec-289">Indicates using a fuzzy matching algorithm when finding commands.</span></span> <span data-ttu-id="f65ec-290">A ordem da saída é de correspondência mais próxima à correspondência menos provável.</span><span class="sxs-lookup"><span data-stu-id="f65ec-290">The order of the output is from closest match to least likely match.</span></span> <span data-ttu-id="f65ec-291">Curingas não devem ser usados com correspondência difusa, pois ele tentará corresponder a comandos que podem conter esses caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="f65ec-291">Wildcards should not be used with fuzzy matching as it will attempt to match commands that may contain those wildcard characters.</span></span>

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

### <span data-ttu-id="f65ec-292">-Verbo</span><span class="sxs-lookup"><span data-stu-id="f65ec-292">-Verb</span></span>

<span data-ttu-id="f65ec-293">Especifica uma matriz de verbos de comando.</span><span class="sxs-lookup"><span data-stu-id="f65ec-293">Specifies an array of command verbs.</span></span> <span data-ttu-id="f65ec-294">Esse cmdlet obtém comandos, que incluem cmdlets, funções e aliases, que têm nomes que incluem o verbo especificado.</span><span class="sxs-lookup"><span data-stu-id="f65ec-294">This cmdlet gets commands, which include cmdlets, functions, and aliases, that have names that include the specified verb.</span></span> <span data-ttu-id="f65ec-295">Insira um ou mais verbos ou padrões de verbos.</span><span class="sxs-lookup"><span data-stu-id="f65ec-295">Enter one or more verbs or verb patterns.</span></span> <span data-ttu-id="f65ec-296">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="f65ec-296">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="f65ec-297">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f65ec-297">CommonParameters</span></span>

<span data-ttu-id="f65ec-298">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f65ec-298">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f65ec-299">Para obter mais informações, confira [about_CommonParameters](About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="f65ec-299">For more information, see [about_CommonParameters](About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="f65ec-300">Entradas</span><span class="sxs-lookup"><span data-stu-id="f65ec-300">Inputs</span></span>

### <span data-ttu-id="f65ec-301">System.String</span><span class="sxs-lookup"><span data-stu-id="f65ec-301">System.String</span></span>

<span data-ttu-id="f65ec-302">Você pode canalizar nomes de comando para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f65ec-302">You can pipe command names to this cmdlet.</span></span>

## <span data-ttu-id="f65ec-303">Saídas</span><span class="sxs-lookup"><span data-stu-id="f65ec-303">Outputs</span></span>

### <span data-ttu-id="f65ec-304">System. Management. Automation. CommandInfo</span><span class="sxs-lookup"><span data-stu-id="f65ec-304">System.Management.Automation.CommandInfo</span></span>

<span data-ttu-id="f65ec-305">Esse cmdlet retorna objetos derivados da classe **CommandInfo** .</span><span class="sxs-lookup"><span data-stu-id="f65ec-305">This cmdlet returns objects derived from the **CommandInfo** class.</span></span> <span data-ttu-id="f65ec-306">O tipo de objeto retornado depende do tipo de comando que `Get-Command` obtém.</span><span class="sxs-lookup"><span data-stu-id="f65ec-306">The type of object that is returned depends on the type of command that `Get-Command` gets.</span></span>

### <span data-ttu-id="f65ec-307">System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="f65ec-307">System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="f65ec-308">Representa aliases.</span><span class="sxs-lookup"><span data-stu-id="f65ec-308">Represents aliases.</span></span>

### <span data-ttu-id="f65ec-309">System. Management. Automation. ApplicationInfo</span><span class="sxs-lookup"><span data-stu-id="f65ec-309">System.Management.Automation.ApplicationInfo</span></span>

<span data-ttu-id="f65ec-310">Representa aplicativos e arquivos.</span><span class="sxs-lookup"><span data-stu-id="f65ec-310">Represents applications and files.</span></span>

### <span data-ttu-id="f65ec-311">System. Management. Automation. CmdletInfo</span><span class="sxs-lookup"><span data-stu-id="f65ec-311">System.Management.Automation.CmdletInfo</span></span>

<span data-ttu-id="f65ec-312">Representa cmdlets.</span><span class="sxs-lookup"><span data-stu-id="f65ec-312">Represents cmdlets.</span></span>

### <span data-ttu-id="f65ec-313">System. Management. Automation. FunctionInfo</span><span class="sxs-lookup"><span data-stu-id="f65ec-313">System.Management.Automation.FunctionInfo</span></span>

<span data-ttu-id="f65ec-314">Representa funções e filtros.</span><span class="sxs-lookup"><span data-stu-id="f65ec-314">Represents functions and filters.</span></span>

## <span data-ttu-id="f65ec-315">Observações</span><span class="sxs-lookup"><span data-stu-id="f65ec-315">Notes</span></span>

- <span data-ttu-id="f65ec-316">Quando mais de um comando com o mesmo nome está disponível para a sessão, `Get-Command` o retorna o comando que é executado quando você digita o nome do comando.</span><span class="sxs-lookup"><span data-stu-id="f65ec-316">When more than one command that has the same name is available to the session, `Get-Command` returns the command that runs when you type the command name.</span></span> <span data-ttu-id="f65ec-317">Para obter comandos com o mesmo nome, listados em ordem de execução, use o parâmetro **All** .</span><span class="sxs-lookup"><span data-stu-id="f65ec-317">To get commands that have the same name, listed in run order, use the **All** parameter.</span></span> <span data-ttu-id="f65ec-318">Para obter mais informações, confira [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="f65ec-318">For more information, see [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md).</span></span>
- <span data-ttu-id="f65ec-319">Quando um módulo é importado automaticamente, o efeito é o mesmo que usar o `Import-Module` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f65ec-319">When a module is imported automatically, the effect is the same as using the `Import-Module` cmdlet.</span></span> <span data-ttu-id="f65ec-320">O módulo pode adicionar comandos, tipos e arquivos de formatação e executar scripts na sessão.</span><span class="sxs-lookup"><span data-stu-id="f65ec-320">The module can add commands, types and formatting files, and run scripts in the session.</span></span>
  <span data-ttu-id="f65ec-321">Para habilitar, desabilitar e configurar a importação automática de módulos, use a `$PSModuleAutoLoadingPreference` variável de preferência.</span><span class="sxs-lookup"><span data-stu-id="f65ec-321">To enable, disable, and configuration automatic importing of modules, use the `$PSModuleAutoLoadingPreference` preference variable.</span></span> <span data-ttu-id="f65ec-322">Para obter mais informações, consulte [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="f65ec-322">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

## <span data-ttu-id="f65ec-323">Links Relacionados</span><span class="sxs-lookup"><span data-stu-id="f65ec-323">Related Links</span></span>

[<span data-ttu-id="f65ec-324">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="f65ec-324">Export-PSSession</span></span>](../Microsoft.PowerShell.Utility/Export-PSSession.md)

[<span data-ttu-id="f65ec-325">Get-Help</span><span class="sxs-lookup"><span data-stu-id="f65ec-325">Get-Help</span></span>](Get-Help.md)

[<span data-ttu-id="f65ec-326">Get-Member</span><span class="sxs-lookup"><span data-stu-id="f65ec-326">Get-Member</span></span>](../Microsoft.PowerShell.Utility/Get-Member.md)

[<span data-ttu-id="f65ec-327">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="f65ec-327">Get-PSDrive</span></span>](../Microsoft.PowerShell.Management/Get-PSDrive.md)

[<span data-ttu-id="f65ec-328">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="f65ec-328">Import-PSSession</span></span>](../Microsoft.PowerShell.Utility/Import-PSSession.md)

[<span data-ttu-id="f65ec-329">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="f65ec-329">about_Command_Precedence</span></span>](About/about_Command_Precedence.md)
