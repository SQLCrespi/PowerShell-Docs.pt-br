---
description: Descreve como usar nomes alternativos para cmdlets e comandos no PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 11/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_aliases?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Aliases
ms.openlocfilehash: 409e6b01f32c5a6f60ac4b450ff08998caf1084a
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196118"
---
# <a name="about-aliases"></a><span data-ttu-id="63564-104">Sobre aliases</span><span class="sxs-lookup"><span data-stu-id="63564-104">About Aliases</span></span>

## <a name="short-description"></a><span data-ttu-id="63564-105">DESCRIÇÃO BREVE</span><span class="sxs-lookup"><span data-stu-id="63564-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="63564-106">Descreve como usar nomes alternativos para cmdlets e comandos no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="63564-106">Describes how to use alternate names for cmdlets and commands in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="63564-107">DESCRIÇÃO LONGA</span><span class="sxs-lookup"><span data-stu-id="63564-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="63564-108">Um alias é um nome alternativo ou apelido para um cmdlet ou para um elemento de comando, como uma função, script, arquivo ou arquivo executável.</span><span class="sxs-lookup"><span data-stu-id="63564-108">An alias is an alternate name or nickname for a cmdlet or for a command element, such as a function, script, file, or executable file.</span></span> <span data-ttu-id="63564-109">Você pode usar o alias em vez do nome do comando em qualquer comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="63564-109">You can use the alias instead of the command name in any PowerShell commands.</span></span>

<span data-ttu-id="63564-110">Para criar um alias, use o cmdlet New-Alias.</span><span class="sxs-lookup"><span data-stu-id="63564-110">To create an alias, use the New-Alias cmdlet.</span></span> <span data-ttu-id="63564-111">Por exemplo, o comando a seguir cria o alias de "gás" para o `Get-AuthenticodeSignature` cmdlet:</span><span class="sxs-lookup"><span data-stu-id="63564-111">For example, the following command creates the "gas" alias for the `Get-AuthenticodeSignature` cmdlet:</span></span>

```powershell
New-Alias -Name gas -Value Get-AuthenticodeSignature
```

<span data-ttu-id="63564-112">Depois de criar o alias para o nome do cmdlet, você pode usar o alias em vez do nome do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="63564-112">After you create the alias for the cmdlet name, you can use the alias instead of the cmdlet name.</span></span> <span data-ttu-id="63564-113">Por exemplo, para obter a assinatura Authenticode para o arquivo de SqlScript.ps1, digite:</span><span class="sxs-lookup"><span data-stu-id="63564-113">For example, to get the Authenticode signature for the SqlScript.ps1 file, type:</span></span>

```powershell
Get-AuthenticodeSignature SqlScript.ps1
```

<span data-ttu-id="63564-114">Ou, digite:</span><span class="sxs-lookup"><span data-stu-id="63564-114">Or, type:</span></span>

```powershell
gas SqlScript.ps1
```

<span data-ttu-id="63564-115">Se você criar "Word" como o alias para Microsoft Office Word, poderá digitar "Word" em vez do seguinte:</span><span class="sxs-lookup"><span data-stu-id="63564-115">If you create "word" as the alias for Microsoft Office Word, you can type "word" instead of the following:</span></span>

```powershell
"C:\Program Files\Microsoft Office\Office11\Winword.exe"
```

## <a name="built-in-aliases"></a><span data-ttu-id="63564-116">ALIASES INTERNOS</span><span class="sxs-lookup"><span data-stu-id="63564-116">BUILT-IN ALIASES</span></span>

<span data-ttu-id="63564-117">O PowerShell inclui um conjunto de aliases internos, incluindo "CD" e "chdir" para o cmdlet Set-Location, e "ls" e "dir" para o cmdlet Get-ChildItem.</span><span class="sxs-lookup"><span data-stu-id="63564-117">PowerShell includes a set of built-in aliases, including "cd" and "chdir" for the Set-Location cmdlet, and "ls" and "dir" for the Get-ChildItem cmdlet.</span></span>

<span data-ttu-id="63564-118">Para obter todos os aliases no computador, incluindo os aliases internos, digite:</span><span class="sxs-lookup"><span data-stu-id="63564-118">To get all the aliases on the computer, including the built-in aliases, type:</span></span>

```powershell
Get-Alias
```

## <a name="alias-cmdlets"></a><span data-ttu-id="63564-119">CMDLETS DE ALIAS</span><span class="sxs-lookup"><span data-stu-id="63564-119">ALIAS CMDLETS</span></span>

<span data-ttu-id="63564-120">O PowerShell inclui os seguintes cmdlets, que são projetados para trabalhar com aliases:</span><span class="sxs-lookup"><span data-stu-id="63564-120">PowerShell includes the following cmdlets, which are designed for working with aliases:</span></span>

- <span data-ttu-id="63564-121">`Get-Alias` -Obtém todos os aliases na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="63564-121">`Get-Alias` - Gets all the aliases in the current session.</span></span>
- <span data-ttu-id="63564-122">`New-Alias` -Cria um novo alias.</span><span class="sxs-lookup"><span data-stu-id="63564-122">`New-Alias` - Creates a new alias.</span></span>
- <span data-ttu-id="63564-123">`Set-Alias` -Cria ou altera um alias.</span><span class="sxs-lookup"><span data-stu-id="63564-123">`Set-Alias` - Creates or changes an alias.</span></span>
- <span data-ttu-id="63564-124">`Export-Alias` -Exporta um ou mais aliases para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="63564-124">`Export-Alias` - Exports one or more aliases to a file.</span></span>
- <span data-ttu-id="63564-125">`Import-Alias` -Importa um arquivo de alias para o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="63564-125">`Import-Alias` - Imports an alias file into PowerShell.</span></span>

<span data-ttu-id="63564-126">Para obter informações detalhadas sobre os cmdlets, digite:</span><span class="sxs-lookup"><span data-stu-id="63564-126">For detailed information about the cmdlets, type:</span></span>

```powershell
Get-Help <cmdlet-Name> -Detailed
```

<span data-ttu-id="63564-127">Por exemplo, digite:</span><span class="sxs-lookup"><span data-stu-id="63564-127">For example, type:</span></span>

```powershell
Get-Help Export-Alias -Detailed
```

## <a name="creating-an-alias"></a><span data-ttu-id="63564-128">CRIANDO UM ALIAS</span><span class="sxs-lookup"><span data-stu-id="63564-128">CREATING AN ALIAS</span></span>

<span data-ttu-id="63564-129">Para criar um novo alias, use o cmdlet New-Alias.</span><span class="sxs-lookup"><span data-stu-id="63564-129">To create a new alias, use the New-Alias cmdlet.</span></span> <span data-ttu-id="63564-130">Por exemplo, para criar o alias "GH" para Get-Help, digite:</span><span class="sxs-lookup"><span data-stu-id="63564-130">For example, to create the "gh" alias for Get-Help, type:</span></span>

```powershell
New-Alias -Name gh -Value Get-Help
```

<span data-ttu-id="63564-131">Você pode usar o alias em comandos, assim como você usaria o nome completo do cmdlet, e você pode usar o alias com parâmetros.</span><span class="sxs-lookup"><span data-stu-id="63564-131">You can use the alias in commands, just as you would use the full cmdlet name, and you can use the alias with parameters.</span></span>

<span data-ttu-id="63564-132">Por exemplo, para obter ajuda detalhada para o cmdlet Get-WmiObject, digite:</span><span class="sxs-lookup"><span data-stu-id="63564-132">For example, to get detailed Help for the Get-WmiObject cmdlet, type:</span></span>

```powershell
Get-Help Get-WmiObject -Detailed
```

<span data-ttu-id="63564-133">Ou, digite:</span><span class="sxs-lookup"><span data-stu-id="63564-133">Or, type:</span></span>

```powershell
gh Get-WmiObject -Detailed
```

## <a name="saving-aliases"></a><span data-ttu-id="63564-134">SALVANDO ALIASES</span><span class="sxs-lookup"><span data-stu-id="63564-134">SAVING ALIASES</span></span>

<span data-ttu-id="63564-135">Os aliases que você cria são salvos somente na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="63564-135">The aliases that you create are saved only in the current session.</span></span> <span data-ttu-id="63564-136">Para usar os aliases em uma sessão diferente, adicione o alias ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="63564-136">To use the aliases in a different session, add the alias to your PowerShell profile.</span></span> <span data-ttu-id="63564-137">Ou use o cmdlet Export-Alias para salvar os aliases em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="63564-137">Or, use the Export-Alias cmdlet to save the aliases to a file.</span></span>

<span data-ttu-id="63564-138">Para obter mais informações, digite: </span><span class="sxs-lookup"><span data-stu-id="63564-138">For more information, type:</span></span>

```powershell
Get-Help about_Profiles
```

## <a name="getting-aliases"></a><span data-ttu-id="63564-139">OBTENDO ALIASES</span><span class="sxs-lookup"><span data-stu-id="63564-139">GETTING ALIASES</span></span>

<span data-ttu-id="63564-140">Para obter todos os aliases na sessão atual, incluindo os aliases internos, os aliases em seus perfis do PowerShell e os aliases que você criou na sessão atual, digite o texto:</span><span class="sxs-lookup"><span data-stu-id="63564-140">To get all the aliases in the current session, including the built-in aliases, the aliases in your PowerShell profiles, and the aliases that you have created in the current session, type:</span></span>

```powershell
Get-Alias
```

<span data-ttu-id="63564-141">Para obter aliases específicos, use o parâmetro Name do cmdlet Get-Alias.</span><span class="sxs-lookup"><span data-stu-id="63564-141">To get particular aliases, use the Name parameter of the Get-Alias cmdlet.</span></span> <span data-ttu-id="63564-142">Por exemplo, para obter aliases que começam com "p", digite:</span><span class="sxs-lookup"><span data-stu-id="63564-142">For example, to get aliases that begin with "p", type:</span></span>

```powershell
Get-Alias -Name p*
```

<span data-ttu-id="63564-143">Para obter os aliases de um item específico, use o parâmetro de definição.</span><span class="sxs-lookup"><span data-stu-id="63564-143">To get the aliases for a particular item, use the Definition parameter.</span></span> <span data-ttu-id="63564-144">Por exemplo, para obter os aliases para o tipo de cmdlet Get-ChildItem:</span><span class="sxs-lookup"><span data-stu-id="63564-144">For example, to get the aliases for the Get-ChildItem cmdlet type:</span></span>

```powershell
Get-Alias -Definition Get-ChildItem
```

### <a name="get-alias-output"></a><span data-ttu-id="63564-145">SAÍDA DE GET-ALIAS</span><span class="sxs-lookup"><span data-stu-id="63564-145">GET-ALIAS OUTPUT</span></span>

<span data-ttu-id="63564-146">Get-Alias retorna apenas um tipo de objeto, um objeto AliasInfo (System. Management. Automation. AliasInfo).</span><span class="sxs-lookup"><span data-stu-id="63564-146">Get-Alias returns only one type of object, an AliasInfo object (System.Management.Automation.AliasInfo).</span></span> <span data-ttu-id="63564-147">O nome dos aliases que não incluem um hífen, como "CD", são exibidos no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="63564-147">The name of aliases that don't include a hyphen, such as "cd" are displayed in the following format:</span></span>

```powershell
Get-Alias ac
```

```Output
CommandType     Name                    Version    Source
-----------     ----                    -------    ------
Alias           ac -> Add-Content
```

<span data-ttu-id="63564-148">Isso torna muito rápido e fácil obter as informações de que você precisa.</span><span class="sxs-lookup"><span data-stu-id="63564-148">This makes it very quick and easy to get the information that you need.</span></span>

<span data-ttu-id="63564-149">O formato de nome de alias com base em seta não é usado para aliases que incluem um hífen.</span><span class="sxs-lookup"><span data-stu-id="63564-149">The arrow-based alias name format is not used for aliases that include a hyphen.</span></span> <span data-ttu-id="63564-150">Esses são provavelmente nomes substitutos preferidos para cmdlets e funções, em vez de abreviações típicas ou apelidos, e o autor talvez não queira que eles estejam tão evidentes.</span><span class="sxs-lookup"><span data-stu-id="63564-150">These are likely to be preferred substitute names for cmdlets and functions, instead of typical abbreviations or nicknames, and the author might not want them to be as evident.</span></span>

## <a name="alternate-names-for-commands-with-parameters"></a><span data-ttu-id="63564-151">NOMES ALTERNATIVOS PARA COMANDOS COM PARÂMETROS</span><span class="sxs-lookup"><span data-stu-id="63564-151">ALTERNATE NAMES FOR COMMANDS WITH PARAMETERS</span></span>

<span data-ttu-id="63564-152">Você pode atribuir um alias a um cmdlet, script, função ou arquivo executável.</span><span class="sxs-lookup"><span data-stu-id="63564-152">You can assign an alias to a cmdlet, script, function, or executable file.</span></span> <span data-ttu-id="63564-153">Você não pode atribuir um alias a um comando e seus parâmetros.</span><span class="sxs-lookup"><span data-stu-id="63564-153">You cannot assign an alias to a command and its parameters.</span></span> <span data-ttu-id="63564-154">Por exemplo, você pode atribuir um alias ao `Get-Eventlog` cmdlet, mas não pode atribuir um alias ao `Get-Eventlog -LogName System` comando.</span><span class="sxs-lookup"><span data-stu-id="63564-154">For example, you can assign an alias to the `Get-Eventlog` cmdlet, but you cannot assign an alias to the `Get-Eventlog -LogName System` command.</span></span>

<span data-ttu-id="63564-155">Você pode criar uma função que inclui o comando.</span><span class="sxs-lookup"><span data-stu-id="63564-155">You can create a function that includes the command.</span></span> <span data-ttu-id="63564-156">Para criar uma função, digite a palavra "função" seguida por um nome para a função.</span><span class="sxs-lookup"><span data-stu-id="63564-156">To create a function, type the word "function" followed by a name for the function.</span></span> <span data-ttu-id="63564-157">Digite o comando e coloque-o entre chaves ( {} ).</span><span class="sxs-lookup"><span data-stu-id="63564-157">Type the command, and enclose it in braces ({}).</span></span>

<span data-ttu-id="63564-158">Por exemplo, o comando a seguir cria a função syslog.</span><span class="sxs-lookup"><span data-stu-id="63564-158">For example, the following command creates the syslog function.</span></span> <span data-ttu-id="63564-159">Essa função representa o `Get-Eventlog -LogName System` comando:</span><span class="sxs-lookup"><span data-stu-id="63564-159">This function represents the `Get-Eventlog -LogName System` command:</span></span>

```powershell
function Get-SystemEventlog {Get-Eventlog -LogName System}
Set-Alias -Name syslog -Value Get-SystemEventlog
```

<span data-ttu-id="63564-160">Agora você pode digitar "syslog" em vez do comando.</span><span class="sxs-lookup"><span data-stu-id="63564-160">You can now type "syslog" instead of the command.</span></span> <span data-ttu-id="63564-161">E, você pode criar aliases para a nova função.</span><span class="sxs-lookup"><span data-stu-id="63564-161">And, you can create aliases for the new function.</span></span>

<span data-ttu-id="63564-162">Para obter mais informações sobre o functions, digite:</span><span class="sxs-lookup"><span data-stu-id="63564-162">For more information about functions, type:</span></span>

```powershell
Get-Help about_Functions
```

## <a name="alias-objects"></a><span data-ttu-id="63564-163">OBJETOS DE ALIAS</span><span class="sxs-lookup"><span data-stu-id="63564-163">ALIAS OBJECTS</span></span>

<span data-ttu-id="63564-164">Os aliases do PowerShell são representados por objetos que são instâncias da classe System. Management. Automation. AliasInfo.</span><span class="sxs-lookup"><span data-stu-id="63564-164">PowerShell aliases are represented by objects that are instances of the System.Management.Automation.AliasInfo class.</span></span> <span data-ttu-id="63564-165">Para obter mais informações sobre esse tipo de objeto, consulte [classe AliasInfo][aliasinfo] na biblioteca do Microsoft Developer Network (MSDN).</span><span class="sxs-lookup"><span data-stu-id="63564-165">For more information about this type of object, see [AliasInfo Class][aliasinfo] in the Microsoft Developer Network (MSDN) library.</span></span>

<span data-ttu-id="63564-166">Para exibir as propriedades e os métodos dos objetos de alias, obtenha os aliases.</span><span class="sxs-lookup"><span data-stu-id="63564-166">To view the properties and methods of the alias objects, get the aliases.</span></span>
<span data-ttu-id="63564-167">Em seguida, direcione-os para o cmdlet Get-Member.</span><span class="sxs-lookup"><span data-stu-id="63564-167">Then, pipe them to the Get-Member cmdlet.</span></span> <span data-ttu-id="63564-168">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="63564-168">For example:</span></span>

```powershell
Get-Alias | Get-Member
```

<span data-ttu-id="63564-169">Para exibir os valores das propriedades de um alias específico, como o `dir` alias, obtenha o alias.</span><span class="sxs-lookup"><span data-stu-id="63564-169">To view the values of the properties of a specific alias, such as the `dir` alias, get the alias.</span></span> <span data-ttu-id="63564-170">Em seguida, redirecione-o para o cmdlet Format-List.</span><span class="sxs-lookup"><span data-stu-id="63564-170">Then, pipe it to the Format-List cmdlet.</span></span> <span data-ttu-id="63564-171">Por exemplo, o comando a seguir obtém o alias "dir".</span><span class="sxs-lookup"><span data-stu-id="63564-171">For example, the following command gets the "dir" alias.</span></span> <span data-ttu-id="63564-172">Em seguida, o comando canaliza o alias para o cmdlet Format-List.</span><span class="sxs-lookup"><span data-stu-id="63564-172">Next, the command pipes the alias to the Format-List cmdlet.</span></span> <span data-ttu-id="63564-173">Em seguida, o comando usa o parâmetro Property de Format-List com um caractere curinga ( \* ) para exibir todas as propriedades do `dir` alias.</span><span class="sxs-lookup"><span data-stu-id="63564-173">Then, the command uses the Property parameter of Format-List with a wildcard character (\*) to display all the properties of the `dir` alias.</span></span> <span data-ttu-id="63564-174">O comando a seguir executa estas tarefas:</span><span class="sxs-lookup"><span data-stu-id="63564-174">The following command performs these tasks:</span></span>

```powershell
Get-Alias -Name dir | Format-List -Property *
```

## <a name="powershell-alias-provider"></a><span data-ttu-id="63564-175">PROVEDOR de ALIAS do PowerShell</span><span class="sxs-lookup"><span data-stu-id="63564-175">PowerShell ALIAS PROVIDER</span></span>

<span data-ttu-id="63564-176">O PowerShell inclui o provedor de alias.</span><span class="sxs-lookup"><span data-stu-id="63564-176">PowerShell includes the Alias provider.</span></span> <span data-ttu-id="63564-177">O provedor de alias permite exibir os aliases no PowerShell como se estivessem em uma unidade do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="63564-177">The Alias provider lets you view the aliases in PowerShell as though they were on a file system drive.</span></span>

<span data-ttu-id="63564-178">O provedor de alias expõe a unidade Alias:.</span><span class="sxs-lookup"><span data-stu-id="63564-178">The Alias provider exposes the Alias: drive.</span></span> <span data-ttu-id="63564-179">Para entrar na unidade Alias:, digite:</span><span class="sxs-lookup"><span data-stu-id="63564-179">To go into the Alias: drive, type:</span></span>

```powershell
Set-Location Alias:
```

<span data-ttu-id="63564-180">Para exibir o conteúdo da unidade, digite:</span><span class="sxs-lookup"><span data-stu-id="63564-180">To view the contents of the drive, type:</span></span>

```powershell
Get-ChildItem
```

<span data-ttu-id="63564-181">Para exibir o conteúdo da unidade de outra unidade do PowerShell, inicie o caminho com o nome da unidade.</span><span class="sxs-lookup"><span data-stu-id="63564-181">To view the contents of the drive from another PowerShell drive, begin the path with the drive name.</span></span> <span data-ttu-id="63564-182">Inclua os dois-pontos (:).</span><span class="sxs-lookup"><span data-stu-id="63564-182">Include the colon (:).</span></span> <span data-ttu-id="63564-183">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="63564-183">For example:</span></span>

```powershell
Get-ChildItem -Path Alias:
```

<span data-ttu-id="63564-184">Para obter informações sobre um alias específico, digite o nome da unidade e o nome do alias.</span><span class="sxs-lookup"><span data-stu-id="63564-184">To get information about a particular alias, type the drive name and the alias name.</span></span> <span data-ttu-id="63564-185">Ou digite um padrão de nome.</span><span class="sxs-lookup"><span data-stu-id="63564-185">Or, type a name pattern.</span></span> <span data-ttu-id="63564-186">Por exemplo, para obter todos os aliases que começam com "p", digite:</span><span class="sxs-lookup"><span data-stu-id="63564-186">For example, to get all the aliases that begin with "p", type:</span></span>

```powershell
Get-ChildItem -Path Alias:p*
```

<span data-ttu-id="63564-187">Para obter mais informações sobre o provedor de alias do PowerShell, digite:</span><span class="sxs-lookup"><span data-stu-id="63564-187">For more information about the PowerShell Alias provider, type:</span></span>

```powershell
Get-Help Alias
```

## <a name="see-also"></a><span data-ttu-id="63564-188">CONSULTE TAMBÉM</span><span class="sxs-lookup"><span data-stu-id="63564-188">SEE ALSO</span></span>

- [<span data-ttu-id="63564-189">New-Alias</span><span class="sxs-lookup"><span data-stu-id="63564-189">New-Alias</span></span>](xref:Microsoft.PowerShell.Utility.New-Alias)
- [<span data-ttu-id="63564-190">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="63564-190">Get-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Get-Alias)
- [<span data-ttu-id="63564-191">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="63564-191">Set-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Set-Alias)
- [<span data-ttu-id="63564-192">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="63564-192">Export-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Export-Alias)
- [<span data-ttu-id="63564-193">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="63564-193">Import-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Import-Alias)
- [<span data-ttu-id="63564-194">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="63564-194">Get-PSProvider</span></span>](xref:Microsoft.PowerShell.Management.Get-PSProvider)
- [<span data-ttu-id="63564-195">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="63564-195">Get-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.Get-PSDrive)
- [<span data-ttu-id="63564-196">about_functions</span><span class="sxs-lookup"><span data-stu-id="63564-196">about_functions</span></span>](about_functions.md)
- [<span data-ttu-id="63564-197">about_profiles</span><span class="sxs-lookup"><span data-stu-id="63564-197">about_profiles</span></span>](about_profiles.md)
- [<span data-ttu-id="63564-198">about_providers</span><span class="sxs-lookup"><span data-stu-id="63564-198">about_providers</span></span>](about_providers.md)

<!-- External links -->
[aliasinfo]: /dotnet/api/system.management.automation.aliasinfo
