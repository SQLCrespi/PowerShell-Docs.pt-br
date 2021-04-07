---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/05/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-pssession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PSSession
ms.openlocfilehash: b9a01c527969c2354397f237898f1f01a24f8229
ms.sourcegitcommit: d95a7255f6775b2973aa9473611185a5583881ff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/07/2021
ms.locfileid: "106555263"
---
# <span data-ttu-id="91b29-103">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="91b29-103">Import-PSSession</span></span>

## <span data-ttu-id="91b29-104">Sinopse</span><span class="sxs-lookup"><span data-stu-id="91b29-104">Synopsis</span></span>
<span data-ttu-id="91b29-105">Importa comandos de outra sessão para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="91b29-105">Imports commands from another session into the current session.</span></span>

## <span data-ttu-id="91b29-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="91b29-106">Syntax</span></span>

```
Import-PSSession [-Prefix <String>] [-DisableNameChecking] [[-CommandName] <String[]>] [-AllowClobber]
 [-ArgumentList <Object[]>] [-CommandType <CommandTypes>] [-Module <String[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-FormatTypeName] <String[]>]
 [-Certificate <X509Certificate2>] [-Session] <PSSession> [<CommonParameters>]
```

## <span data-ttu-id="91b29-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="91b29-107">Description</span></span>

<span data-ttu-id="91b29-108">O `Import-PSSession` cmdlet importa comandos, como cmdlets, funções e aliases, de uma PSSession em um computador local ou remoto para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="91b29-108">The `Import-PSSession` cmdlet imports commands , such as cmdlets, functions, and aliases, from a PSSession on a local or remote computer into the current session.</span></span> <span data-ttu-id="91b29-109">Você pode importar qualquer comando que o `Get-Command` cmdlet possa encontrar na PSSession.</span><span class="sxs-lookup"><span data-stu-id="91b29-109">You can import any command that the `Get-Command` cmdlet can find in the PSSession.</span></span>

<span data-ttu-id="91b29-110">Use um `Import-PSSession` comando para importar comandos de um shell personalizado, como um shell do Microsoft Exchange Server, ou de uma sessão que inclui módulos e snap-ins do Windows PowerShell ou outros elementos que não estão na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="91b29-110">Use an `Import-PSSession` command to import commands from a customized shell, such as a Microsoft Exchange Server shell, or from a session that includes Windows PowerShell modules and snap-ins or other elements that are not in the current session.</span></span>

<span data-ttu-id="91b29-111">Para importar comandos, primeiro use o `New-PSSession` cmdlet para criar uma PSSession.</span><span class="sxs-lookup"><span data-stu-id="91b29-111">To import commands, first use the `New-PSSession` cmdlet to create a PSSession.</span></span> <span data-ttu-id="91b29-112">Em seguida, use o `Import-PSSession` cmdlet para importar os comandos.</span><span class="sxs-lookup"><span data-stu-id="91b29-112">Then, use the `Import-PSSession` cmdlet to import the commands.</span></span> <span data-ttu-id="91b29-113">Por padrão, `Import-PSSession` o importa todos os comandos, exceto os comandos que têm os mesmos nomes que os comandos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="91b29-113">By default, `Import-PSSession` imports all commands except for commands that have the same names as commands in the current session.</span></span> <span data-ttu-id="91b29-114">Para importar todos os comandos, use o parâmetro **AllowClobber**.</span><span class="sxs-lookup"><span data-stu-id="91b29-114">To import all the commands, use the **AllowClobber** parameter.</span></span>

<span data-ttu-id="91b29-115">Você pode usar comandos importados da mesma maneira que usaria qualquer comando na sessão.</span><span class="sxs-lookup"><span data-stu-id="91b29-115">You can use imported commands just as you would use any command in the session.</span></span> <span data-ttu-id="91b29-116">Quando você usa um comando importado, a parte importada do comando é executada implicitamente na sessão da qual ele foi importado.</span><span class="sxs-lookup"><span data-stu-id="91b29-116">When you use an imported command, the imported part of the command runs implicitly in the session from which it was imported.</span></span> <span data-ttu-id="91b29-117">No entanto, as operações remotas são manipuladas inteiramente pelo Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91b29-117">However, the remote operations are handled entirely by Windows PowerShell.</span></span> <span data-ttu-id="91b29-118">Você não precisa nem estar ciente delas, exceto de que a conexão com a outra sessão (PSSession) deve ser mantida aberta.</span><span class="sxs-lookup"><span data-stu-id="91b29-118">You need not even be aware of them, except that you must keep the connection to the other session (PSSession) open.</span></span> <span data-ttu-id="91b29-119">Se ela for fechada, os comandos importados não estarão mais disponíveis.</span><span class="sxs-lookup"><span data-stu-id="91b29-119">If you close it, the imported commands are no longer available.</span></span>

<span data-ttu-id="91b29-120">Como os comandos importados podem levar mais tempo do que comandos locais, `Import-PSSession` o adiciona um parâmetro **AsJob** a todos os comandos importados.</span><span class="sxs-lookup"><span data-stu-id="91b29-120">Because imported commands might take longer to run than local commands, `Import-PSSession` adds an **AsJob** parameter to every imported command.</span></span> <span data-ttu-id="91b29-121">Esse parâmetro permite que você execute o comando como um trabalho em segundo plano do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91b29-121">This parameter allows you to run the command as a Windows PowerShell background job.</span></span> <span data-ttu-id="91b29-122">Para obter mais informações, consulte [about_Jobs](../Microsoft.PowerShell.Core/about/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="91b29-122">For more information, see [about_Jobs](../Microsoft.PowerShell.Core/about/about_Jobs.md).</span></span>

<span data-ttu-id="91b29-123">Quando você usa `Import-PSSession` o, o Windows PowerShell adiciona os comandos importados a um módulo temporário que existe somente em sua sessão e retorna um objeto que representa o módulo.</span><span class="sxs-lookup"><span data-stu-id="91b29-123">When you use `Import-PSSession`, Windows PowerShell adds the imported commands to a temporary module that exists only in your session and returns an object that represents the module.</span></span> <span data-ttu-id="91b29-124">Para criar um módulo persistente que você pode usar em sessões futuras, use o `Export-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="91b29-124">To create a persistent module that you can use in future sessions, use the `Export-PSSession` cmdlet.</span></span>

<span data-ttu-id="91b29-125">O `Import-PSSession` cmdlet usa o recurso de comunicação remota implícita do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91b29-125">The `Import-PSSession` cmdlet uses the implicit remoting feature of Windows PowerShell.</span></span> <span data-ttu-id="91b29-126">Quando você importa comandos para a sessão atual, eles são executados implicitamente na sessão original ou em uma sessão semelhante no computador de origem.</span><span class="sxs-lookup"><span data-stu-id="91b29-126">When you import commands into the current session, they run implicitly in the original session or in a similar session on the originating computer.</span></span>

<span data-ttu-id="91b29-127">A partir do Windows PowerShell 3,0, você pode usar o `Import-Module` cmdlet para importar módulos de uma sessão remota para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="91b29-127">Beginning in Windows PowerShell 3.0, you can use the `Import-Module` cmdlet to import modules from a remote session into the current session.</span></span> <span data-ttu-id="91b29-128">Esse recurso usa a comunicação remota implícita.</span><span class="sxs-lookup"><span data-stu-id="91b29-128">This feature uses implicit remoting.</span></span> <span data-ttu-id="91b29-129">É equivalente a usar `Import-PSSession` o para importar módulos selecionados de uma sessão remota para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="91b29-129">It is equivalent to using `Import-PSSession` to import selected modules from a remote session into the current session.</span></span>

## <span data-ttu-id="91b29-130">Exemplos</span><span class="sxs-lookup"><span data-stu-id="91b29-130">Examples</span></span>

### <span data-ttu-id="91b29-131">Exemplo 1: importar todos os comandos de uma PSSession</span><span class="sxs-lookup"><span data-stu-id="91b29-131">Example 1: Import all commands from a PSSession</span></span>

```
$S = New-PSSession -ComputerName Server01
Import-PSSession -Session $S
```

<span data-ttu-id="91b29-132">Este comando importa todos os comandos de uma PSSession no computador Server01 para a sessão atual, com exceção de comandos que possuem os mesmos nomes de comandos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="91b29-132">This command imports all commands from a PSSession on the Server01 computer into the current session, except for commands that have the same names as commands in the current session.</span></span>

<span data-ttu-id="91b29-133">Como esse comando não usa o parâmetro **CommandName**, ele também importa todos os dados de formatação necessários para os comandos importados.</span><span class="sxs-lookup"><span data-stu-id="91b29-133">Because this command does not use the **CommandName** parameter, it also imports all of the formatting data required for the imported commands.</span></span>

### <span data-ttu-id="91b29-134">Exemplo 2: importar comandos que terminam com uma cadeia de caracteres específica</span><span class="sxs-lookup"><span data-stu-id="91b29-134">Example 2: Import commands that end with a specific string</span></span>

```
$S = New-PSSession https://ps.testlabs.com/powershell
Import-PSSession -Session $S -CommandName *-test -FormatTypeName *
New-Test -Name Test1
Get-Test test1 | Run-Test
```

<span data-ttu-id="91b29-135">Esses comandos importam os comandos com nomes que terminam em "-test" de uma PSSession para a sessão local e mostram como usar um cmdlet importado.</span><span class="sxs-lookup"><span data-stu-id="91b29-135">These commands import the commands with names that end in "-test" from a PSSession into the local session, and then they show how to use an imported cmdlet.</span></span>

<span data-ttu-id="91b29-136">O primeiro comando usa o `New-PSSession` cmdlet para criar uma PSSession.</span><span class="sxs-lookup"><span data-stu-id="91b29-136">The first command uses the `New-PSSession` cmdlet to create a PSSession.</span></span> <span data-ttu-id="91b29-137">Ele salva a PSSession na `$S` variável.</span><span class="sxs-lookup"><span data-stu-id="91b29-137">It saves the PSSession in the `$S` variable.</span></span>

<span data-ttu-id="91b29-138">O segundo comando usa o `Import-PSSession` cmdlet para importar comandos da PSSession para `$S` a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="91b29-138">The second command uses the `Import-PSSession` cmdlet to import commands from the PSSession in `$S` into the current session.</span></span> <span data-ttu-id="91b29-139">Ele usa o parâmetro **CommandName** para especificar comandos com o substantivo Test (Teste) e o parâmetro **FormatTypeName** para importar os dados de formatação para os comandos Test.</span><span class="sxs-lookup"><span data-stu-id="91b29-139">It uses the **CommandName** parameter to specify commands with the Test noun and the **FormatTypeName** parameter to import the formatting data for the Test commands.</span></span>

<span data-ttu-id="91b29-140">Os terceiro e o quarto comandos usam os comandos importados na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="91b29-140">The third and fourth commands use the imported commands in the current session.</span></span> <span data-ttu-id="91b29-141">Como comandos importados, na verdade, são adicionados à sessão atual, a sintaxe local é usada para executá-los.</span><span class="sxs-lookup"><span data-stu-id="91b29-141">Because imported commands are actually added to the current session, you use the local syntax to run them.</span></span> <span data-ttu-id="91b29-142">Você não precisa usar o `Invoke-Command` cmdlet para executar um comando importado.</span><span class="sxs-lookup"><span data-stu-id="91b29-142">You do not need to use the `Invoke-Command` cmdlet to run an imported command.</span></span>

### <span data-ttu-id="91b29-143">Exemplo 3: importar cmdlets de uma PSSession</span><span class="sxs-lookup"><span data-stu-id="91b29-143">Example 3: Import cmdlets from a PSSession</span></span>

```
$S1 = New-PSSession -ComputerName s1
$S2 = New-PSSession -ComputerName s2
Import-PSSession -Session s1 -Type cmdlet -Name New-Test, Get-Test -FormatTypeName *
Import-PSSession -Session s2 -Type Cmdlet -Name Set-Test -FormatTypeName *
New-Test Test1 | Set-Test -RunType Full
```

<span data-ttu-id="91b29-144">Este exemplo mostra que é possível usar cmdlets importados da mesma maneira que cmdlets locais.</span><span class="sxs-lookup"><span data-stu-id="91b29-144">This example shows that you can use imported cmdlets just as you would use local cmdlets.</span></span>

<span data-ttu-id="91b29-145">Esses comandos importam os `New-Test` `Get-Test` cmdlets e de uma PSSession no computador Server01 e o `Set-Test` cmdlet de uma PSSession no computador Server02.</span><span class="sxs-lookup"><span data-stu-id="91b29-145">These commands import the `New-Test` and `Get-Test` cmdlets from a PSSession on the Server01 computer and the `Set-Test` cmdlet from a PSSession on the Server02 computer.</span></span>

<span data-ttu-id="91b29-146">Embora os cmdlets sejam importados de diferentes PSSessions, é possível direcionar um objeto de um cmdlet para outro sem erro.</span><span class="sxs-lookup"><span data-stu-id="91b29-146">Even though the cmdlets were imported from different PSSessions, you can pipe an object from one cmdlet to another without error.</span></span>

### <span data-ttu-id="91b29-147">Exemplo 4: executar um comando importado como um trabalho em segundo plano</span><span class="sxs-lookup"><span data-stu-id="91b29-147">Example 4: Run an imported command as a background job</span></span>

```
$S = New-PSSession -ComputerName Server01
Import-PSSession -Session $S -CommandName *-test* -FormatTypeName *
$batch = New-Test -Name Batch -AsJob
Receive-Job $batch
```

<span data-ttu-id="91b29-148">Este exemplo mostra como executar um comando importado como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="91b29-148">This example shows how to run an imported command as a background job.</span></span>

<span data-ttu-id="91b29-149">Como os comandos importados podem levar mais tempo do que comandos locais, `Import-PSSession` o adiciona um parâmetro **AsJob** a todos os comandos importados.</span><span class="sxs-lookup"><span data-stu-id="91b29-149">Because imported commands might take longer to run than local commands, `Import-PSSession` adds an **AsJob** parameter to every imported command.</span></span> <span data-ttu-id="91b29-150">O parâmetro **AsJob** permite que você execute o comando como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="91b29-150">The **AsJob** parameter lets you run the command as a background job.</span></span>

<span data-ttu-id="91b29-151">O primeiro comando cria uma PSSession no computador Server01 e salva o objeto PSSession na `$S` variável.</span><span class="sxs-lookup"><span data-stu-id="91b29-151">The first command creates a PSSession on the Server01 computer and saves the PSSession object in the `$S` variable.</span></span>

<span data-ttu-id="91b29-152">O segundo comando usa `Import-PSSession` para importar os cmdlets de teste da PSSession `$S` para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="91b29-152">The second command uses `Import-PSSession` to import the Test cmdlets from the PSSession in `$S` into the current session.</span></span>

<span data-ttu-id="91b29-153">O terceiro comando usa o parâmetro **AsJob** do cmdlet importado `New-Test` para executar um `New-Test` comando como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="91b29-153">The third command uses the **AsJob** parameter of the imported `New-Test` cmdlet to run a `New-Test` command as a background job.</span></span> <span data-ttu-id="91b29-154">O comando salva o objeto de trabalho que `New-Test` retorna na `$batch` variável.</span><span class="sxs-lookup"><span data-stu-id="91b29-154">The command saves the job object that `New-Test` returns in the `$batch` variable.</span></span>

<span data-ttu-id="91b29-155">O quarto comando usa o `Receive-Job` cmdlet para obter os resultados do trabalho na `$batch` variável.</span><span class="sxs-lookup"><span data-stu-id="91b29-155">The fourth command uses the `Receive-Job` cmdlet to get the results of the job in the `$batch` variable.</span></span>

### <span data-ttu-id="91b29-156">Exemplo 5: importar cmdlets e funções de um módulo do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="91b29-156">Example 5: Import cmdlets and functions from a Windows PowerShell module</span></span>

```
$S = New-PSSession -ComputerName Server01
Invoke-Command -Session $S {Import-Module TestManagement}
Import-PSSession -Session $S -Module TestManagement
```

<span data-ttu-id="91b29-157">Este exemplo mostra como importar os cmdlets e funções de um módulo do Windows PowerShell em um computador remoto para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="91b29-157">This example shows how to import the cmdlets and functions from a Windows PowerShell module on a remote computer into the current session.</span></span>

<span data-ttu-id="91b29-158">O primeiro comando cria uma PSSession no computador Server01 e salva-a na `$S` variável.</span><span class="sxs-lookup"><span data-stu-id="91b29-158">The first command creates a PSSession on the Server01 computer and saves it in the `$S` variable.</span></span>

<span data-ttu-id="91b29-159">O segundo comando usa o `Invoke-Command` cmdlet para executar um `Import-Module` comando na PSSession em `$S` .</span><span class="sxs-lookup"><span data-stu-id="91b29-159">The second command uses the `Invoke-Command` cmdlet to run an `Import-Module` command in the PSSession in `$S`.</span></span>

<span data-ttu-id="91b29-160">Normalmente, o módulo seria adicionado a todas as sessões por um `Import-Module` comando em um perfil do Windows PowerShell, mas os perfis não são executados em PSSessions.</span><span class="sxs-lookup"><span data-stu-id="91b29-160">Typically, the module would be added to all sessions by an `Import-Module` command in a Windows PowerShell profile, but profiles are not run in PSSessions.</span></span>

<span data-ttu-id="91b29-161">O terceiro comando usa o parâmetro **Module** do `Import-PSSession` para importar os cmdlets e funções no módulo para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="91b29-161">The third command uses the **Module** parameter of `Import-PSSession` to import the cmdlets and functions in the module into the current session.</span></span>

### <span data-ttu-id="91b29-162">Exemplo 6: criar um módulo em um arquivo temporário</span><span class="sxs-lookup"><span data-stu-id="91b29-162">Example 6: Create a module in a temporary file</span></span>

```
PS C:\> Import-PSSession $S -CommandName Get-Date, SearchHelp -FormatTypeName * -AllowClobber

Name              : tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1zunz.ttf
Path              : C:\Users\User01\AppData\Local\Temp\tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1
zunz.ttf\tmp_79468106-4e1d-4d90-af97-1154f9317239_
tcw1zunz.ttf.psm1
Description       : Implicit remoting for http://server01.corp.fabrikam.com/wsman
Guid              : 79468106-4e1d-4d90-af97-1154f9317239
Version           : 1.0
ModuleBase        : C:\Users\User01\AppData\Local\Temp\tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1
zunz.ttf
ModuleType        : Script
PrivateData       : {ImplicitRemoting}
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Get-Date, Get-Date], [SearchHelp, SearchHelp]}
ExportedVariables : {}
NestedModules     : {}
```

<span data-ttu-id="91b29-163">Este exemplo mostra que `Import-PSSession` cria um módulo em um arquivo temporário no disco.</span><span class="sxs-lookup"><span data-stu-id="91b29-163">This example shows that `Import-PSSession` creates a module in a temporary file on disk.</span></span> <span data-ttu-id="91b29-164">Ele também mostra que todos os comandos são convertidos em funções antes de serem importados para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="91b29-164">It also shows that all commands are converted into functions before they are imported into the current session.</span></span>

<span data-ttu-id="91b29-165">O comando usa o `Import-PSSession` cmdlet para importar um `Get-Date` cmdlet e uma função SearchHelp para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="91b29-165">The command uses the `Import-PSSession` cmdlet to import a `Get-Date` cmdlet and a SearchHelp function into the current session.</span></span>

<span data-ttu-id="91b29-166">O `Import-PSSession` cmdlet retorna um objeto **PSModuleInfo** que representa o módulo temporário.</span><span class="sxs-lookup"><span data-stu-id="91b29-166">The `Import-PSSession` cmdlet returns a **PSModuleInfo** object that represents the temporary module.</span></span> <span data-ttu-id="91b29-167">O valor da propriedade **path** mostra que `Import-PSSession` criou um arquivo de módulo de script (. psm1) em um local temporário.</span><span class="sxs-lookup"><span data-stu-id="91b29-167">The value of the **Path** property shows that `Import-PSSession` created a script module (.psm1) file in a temporary location.</span></span> <span data-ttu-id="91b29-168">A propriedade **ExportedFunctions** mostra que o `Get-Date` cmdlet e a função SearchHelp foram importados como funções.</span><span class="sxs-lookup"><span data-stu-id="91b29-168">The **ExportedFunctions** property shows that the `Get-Date` cmdlet and the SearchHelp function were both imported as functions.</span></span>

### <span data-ttu-id="91b29-169">Exemplo 7: executar um comando que está oculto por um comando importado</span><span class="sxs-lookup"><span data-stu-id="91b29-169">Example 7: Run a command that is hidden by an imported command</span></span>

```
PS C:\> Import-PSSession $S -CommandName Get-Date -FormatTypeName * -AllowClobber

PS C:\> Get-Command Get-Date -All

CommandType   Name       Definition
-----------   ----       ----------
Function      Get-Date   ...
Cmdlet        Get-Date   Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>]

PS C:\> Get-Date
09074

PS C:\> (Get-Command -Type Cmdlet -Name Get-Date).PSSnapin.Name
Microsoft.PowerShell.Utility

PS C:\> Microsoft.PowerShell.Utility\Get-Date
Sunday, March 15, 2009 2:08:26 PM
```

<span data-ttu-id="91b29-170">Este exemplo mostra como executar um comando que está oculto por um comando importado.</span><span class="sxs-lookup"><span data-stu-id="91b29-170">This example shows how to run a command that is hidden by an imported command.</span></span>

<span data-ttu-id="91b29-171">O primeiro comando importa um `Get-Date` cmdlet da PSSession na `$S` variável.</span><span class="sxs-lookup"><span data-stu-id="91b29-171">The first command imports a `Get-Date` cmdlet from the PSSession in the `$S` variable.</span></span> <span data-ttu-id="91b29-172">Como a sessão atual inclui um `Get-Date` cmdlet, o parâmetro **AllowClobber** é necessário no comando.</span><span class="sxs-lookup"><span data-stu-id="91b29-172">Because the current session includes a `Get-Date` cmdlet, the **AllowClobber** parameter is required in the command.</span></span>

<span data-ttu-id="91b29-173">O segundo comando usa o parâmetro **All** do `Get-Command` cmdlet para obter todos os `Get-Date` comandos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="91b29-173">The second command uses the **All** parameter of the `Get-Command` cmdlet to get all `Get-Date` commands in the current session.</span></span> <span data-ttu-id="91b29-174">A saída mostra que a sessão inclui o `Get-Date` cmdlet original e uma `Get-Date` função.</span><span class="sxs-lookup"><span data-stu-id="91b29-174">The output shows that the session includes the original `Get-Date` cmdlet and a `Get-Date` function.</span></span> <span data-ttu-id="91b29-175">A `Get-Date` função executa o cmdlet importado `Get-Date` na PSSession no `$S` .</span><span class="sxs-lookup"><span data-stu-id="91b29-175">The `Get-Date` function runs the imported `Get-Date` cmdlet in the PSSession in `$S`.</span></span>

<span data-ttu-id="91b29-176">O terceiro comando executa um `Get-Date` comando.</span><span class="sxs-lookup"><span data-stu-id="91b29-176">The third command runs a `Get-Date` command.</span></span> <span data-ttu-id="91b29-177">Como as funções têm precedência sobre os cmdlets, o Windows PowerShell executa a função importada `Get-Date` , que retorna uma data do calendário juliano.</span><span class="sxs-lookup"><span data-stu-id="91b29-177">Because functions take precedence over cmdlets, Windows PowerShell runs the imported `Get-Date` function, which returns a Julian date.</span></span>

<span data-ttu-id="91b29-178">Os quarto e quinto comandos mostram como usar um nome qualificado para executar um comando que está oculto por um comando importado.</span><span class="sxs-lookup"><span data-stu-id="91b29-178">The fourth and fifth commands show how to use a qualified name to run a command that is hidden by an imported command.</span></span>

<span data-ttu-id="91b29-179">O quarto comando obtém o nome do snap-in do Windows PowerShell que adicionou o `Get-Date` cmdlet original à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="91b29-179">The fourth command gets the name of the Windows PowerShell snap-in that added the original `Get-Date` cmdlet to the current session.</span></span>

<span data-ttu-id="91b29-180">O quinto comando usa o nome qualificado do snap-in do `Get-Date` cmdlet para executar um `Get-Date` comando.</span><span class="sxs-lookup"><span data-stu-id="91b29-180">The fifth command uses the snap-in-qualified name of the `Get-Date` cmdlet to run a `Get-Date` command.</span></span>

<span data-ttu-id="91b29-181">Para obter mais informações sobre precedência de comandos e comandos ocultos, consulte [about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="91b29-181">For more information about command precedence and hidden commands, see [about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md).</span></span>

### <span data-ttu-id="91b29-182">Exemplo 8: importar comandos que têm uma cadeia de caracteres específica em seus nomes</span><span class="sxs-lookup"><span data-stu-id="91b29-182">Example 8: Import commands that have a specific string in their names</span></span>

```
PS C:\> Import-PSSession -Session $S -CommandName **Item** -AllowClobber
```

<span data-ttu-id="91b29-183">Este comando importa os comandos cujos nomes incluem item da PSSession em `$S` .</span><span class="sxs-lookup"><span data-stu-id="91b29-183">This command imports commands whose names include Item from the PSSession in `$S`.</span></span> <span data-ttu-id="91b29-184">Como o comando inclui o parâmetro **CommandName** , mas não o parâmetro **FormatTypeData** , somente o comando é importado.</span><span class="sxs-lookup"><span data-stu-id="91b29-184">Because the command includes the **CommandName** parameter but not the **FormatTypeData** parameter, only the command is imported.</span></span>

<span data-ttu-id="91b29-185">Use esse comando quando estiver usando `Import-PSSession` o para executar um comando em um computador remoto e você já tiver os dados de formatação para o comando na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="91b29-185">Use this command when you are using `Import-PSSession` to run a command on a remote computer and you already have the formatting data for the command in the current session.</span></span>

### <span data-ttu-id="91b29-186">Exemplo 9: usar o parâmetro Module para descobrir quais comandos foram importados para a sessão</span><span class="sxs-lookup"><span data-stu-id="91b29-186">Example 9: Use the Module parameter to discover which commands were imported into the session</span></span>

```
PS C:\> $M = Import-PSSession -Session $S -CommandName *bits* -FormatTypeName *bits*
PS C:\> Get-Command -Module $M
CommandType     Name
-----------     ----
Function        Add-BitsFile
Function        Complete-BitsTransfer
Function        Get-BitsTransfer
Function        Remove-BitsTransfer
Function        Resume-BitsTransfer
Function        Set-BitsTransfer
Function        Start-BitsTransfer
Function        Suspend-BitsTransfer
```

<span data-ttu-id="91b29-187">Este comando mostra como usar o parâmetro **Module** do `Get-Command` para descobrir quais comandos foram importados para a sessão por um `Import-PSSession` comando.</span><span class="sxs-lookup"><span data-stu-id="91b29-187">This command shows how to use the **Module** parameter of `Get-Command` to find out which commands were imported into the session by an `Import-PSSession` command.</span></span>

<span data-ttu-id="91b29-188">O primeiro comando usa o `Import-PSSession` cmdlet para importar comandos cujos nomes incluem "bits" da PSSession na `$S` variável.</span><span class="sxs-lookup"><span data-stu-id="91b29-188">The first command uses the `Import-PSSession` cmdlet to import commands whose names include "bits" from the PSSession in the `$S` variable.</span></span> <span data-ttu-id="91b29-189">O `Import-PSSession` comando retorna um módulo temporário e o comando salva o módulo na `$m` variável.</span><span class="sxs-lookup"><span data-stu-id="91b29-189">The `Import-PSSession` command returns a temporary module, and the command saves the module in the `$m` variable.</span></span>

<span data-ttu-id="91b29-190">O segundo comando usa o `Get-Command` cmdlet para obter os comandos que são exportados pelo módulo na `$M` variável.</span><span class="sxs-lookup"><span data-stu-id="91b29-190">The second command uses the `Get-Command` cmdlet to get the commands that are exported by the module in the `$M` variable.</span></span>

<span data-ttu-id="91b29-191">O parâmetro **Module** obtém um valor de cadeia de caracteres, que é projetado para o nome do módulo.</span><span class="sxs-lookup"><span data-stu-id="91b29-191">The **Module** parameter takes a string value, which is designed for the module name.</span></span> <span data-ttu-id="91b29-192">No entanto, quando você envia um objeto de módulo, o Windows PowerShell usa o método **ToString** no objeto de módulo, que retorna o nome do módulo.</span><span class="sxs-lookup"><span data-stu-id="91b29-192">However, when you submit a module object, Windows PowerShell uses the **ToString** method on the module object, which returns the module name.</span></span>

<span data-ttu-id="91b29-193">O `Get-Command` comando é o equivalente a `Get-Command $M.Name` ".</span><span class="sxs-lookup"><span data-stu-id="91b29-193">The `Get-Command` command is the equivalent of `Get-Command $M.Name`".</span></span>

## <span data-ttu-id="91b29-194">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="91b29-194">Parameters</span></span>

### <span data-ttu-id="91b29-195">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="91b29-195">-AllowClobber</span></span>

<span data-ttu-id="91b29-196">Indica que esse cmdlet importa os comandos especificados, mesmo que eles tenham os mesmos nomes que os comandos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="91b29-196">Indicates that this cmdlet imports the specified commands, even if they have the same names as commands in the current session.</span></span>

<span data-ttu-id="91b29-197">Se você importar um comando com o mesmo nome de um comando na sessão atual, os comandos importado ocultam ou substituem os originais.</span><span class="sxs-lookup"><span data-stu-id="91b29-197">If you import a command with the same name as a command in the current session, the imported command hides or replaces the original commands.</span></span> <span data-ttu-id="91b29-198">Para obter mais informações, confira [about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="91b29-198">For more information, see [about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md).</span></span>

<span data-ttu-id="91b29-199">Por padrão, `Import-PSSession` o não importa comandos com o mesmo nome que os comandos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="91b29-199">By default, `Import-PSSession` does not import commands that have the same name as commands in the current session.</span></span>

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

### <span data-ttu-id="91b29-200">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="91b29-200">-ArgumentList</span></span>

<span data-ttu-id="91b29-201">Especifica uma matriz de comandos que resulta do uso dos argumentos especificados (valores de parâmetro).</span><span class="sxs-lookup"><span data-stu-id="91b29-201">Specifies an array of commands that results from using the specified arguments (parameter values).</span></span>

<span data-ttu-id="91b29-202">Por exemplo, para importar a variante do `Get-Item` comando no certificado (CERT:) na PSSession em `$S` , digite `Import-PSSession -Session $S -Command Get-Item -ArgumentList cert:` .</span><span class="sxs-lookup"><span data-stu-id="91b29-202">For instance, to import the variant of the `Get-Item` command in the certificate (Cert:) drive in the PSSession in `$S`, type `Import-PSSession -Session $S -Command Get-Item -ArgumentList cert:`.</span></span>

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

### <span data-ttu-id="91b29-203">-Certificado</span><span class="sxs-lookup"><span data-stu-id="91b29-203">-Certificate</span></span>

<span data-ttu-id="91b29-204">Especifica o certificado do cliente que é usado para assinar os arquivos de formato (\* .Format.ps1XML) ou arquivos de módulo de script (. psm1) no módulo temporário que o `Import-PSSession` cria.</span><span class="sxs-lookup"><span data-stu-id="91b29-204">Specifies the client certificate that is used to sign the format files (\*.Format.ps1xml) or script module files (.psm1) in the temporary module that `Import-PSSession` creates.</span></span>

<span data-ttu-id="91b29-205">Insira uma variável que contém um certificado, comando ou expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="91b29-205">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="91b29-206">Para localizar um certificado, use o `Get-PfxCertificate` cmdlet ou use o `Get-ChildItem` cmdlet no certificado (CERT:) Dirigir.</span><span class="sxs-lookup"><span data-stu-id="91b29-206">To find a certificate, use the `Get-PfxCertificate` cmdlet or use the `Get-ChildItem` cmdlet in the Certificate (Cert:) drive.</span></span> <span data-ttu-id="91b29-207">Se o certificado não for válido ou não tiver autoridade suficiente, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="91b29-207">If the certificate is not valid or does not have sufficient authority, the command fails.</span></span>

```yaml
Type: System.Security.Cryptography.X509Certificates.X509Certificate2
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="91b29-208">-CommandName</span><span class="sxs-lookup"><span data-stu-id="91b29-208">-CommandName</span></span>

<span data-ttu-id="91b29-209">Especifica os comandos com os nomes especificados ou padrões de nome.</span><span class="sxs-lookup"><span data-stu-id="91b29-209">Specifies commands with the specified names or name patterns.</span></span> <span data-ttu-id="91b29-210">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="91b29-210">Wildcards are permitted.</span></span> <span data-ttu-id="91b29-211">Use **CommandName** ou seu alias, **Name**.</span><span class="sxs-lookup"><span data-stu-id="91b29-211">Use **CommandName** or its alias, **Name**.</span></span>

<span data-ttu-id="91b29-212">Por padrão, `Import-PSSession` o importa todos os comandos da sessão, exceto os comandos que têm os mesmos nomes que os comandos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="91b29-212">By default, `Import-PSSession` imports all commands from the session, except for commands that have the same names as commands in the current session.</span></span> <span data-ttu-id="91b29-213">Isso impede que os comandos importados ocultem ou substituam os comandos da sessão.</span><span class="sxs-lookup"><span data-stu-id="91b29-213">This prevents imported commands from hiding or replacing commands in the session.</span></span> <span data-ttu-id="91b29-214">Para importar todos os comandos, mesmo aqueles que ocultam ou substituem outros comandos, use o parâmetro **AllowClobber**.</span><span class="sxs-lookup"><span data-stu-id="91b29-214">To import all commands, even those that hide or replace other commands, use the **AllowClobber** parameter.</span></span>

<span data-ttu-id="91b29-215">Se você usar o parâmetro **CommandName**, os arquivos de formatação para os comandos não serão importados a menos que você use o parâmetro **FormatTypeName**.</span><span class="sxs-lookup"><span data-stu-id="91b29-215">If you use the **CommandName** parameter, the formatting files for the commands are not imported unless you use the **FormatTypeName** parameter.</span></span> <span data-ttu-id="91b29-216">Da mesma forma, se você usar o parâmetro **FormatTypeName**, nenhum comando é importado, a menos que você use o parâmetro **CommandName**.</span><span class="sxs-lookup"><span data-stu-id="91b29-216">Similarly, if you use the **FormatTypeName** parameter, no commands are imported unless you use the **CommandName** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="91b29-217">-CommandType</span><span class="sxs-lookup"><span data-stu-id="91b29-217">-CommandType</span></span>

<span data-ttu-id="91b29-218">Especifica o tipo de objetos de comando.</span><span class="sxs-lookup"><span data-stu-id="91b29-218">Specifies the type of command objects.</span></span> <span data-ttu-id="91b29-219">O valor padrão é Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="91b29-219">The default value is Cmdlet.</span></span> <span data-ttu-id="91b29-220">Use o **CommandType** ou seu alias, **Type**.</span><span class="sxs-lookup"><span data-stu-id="91b29-220">Use **CommandType** or its alias, **Type**.</span></span> <span data-ttu-id="91b29-221">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="91b29-221">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="91b29-222">`Alias`: Os aliases do Windows PowerShell na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="91b29-222">`Alias`: The Windows PowerShell aliases in the remote session.</span></span>
- <span data-ttu-id="91b29-223">`All`: Os cmdlets e funções na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="91b29-223">`All`: The cmdlets and functions in the remote session.</span></span>
- <span data-ttu-id="91b29-224">`Application`: Todos os arquivos que não Windows-PowerShell arquivos nos caminhos listados na variável de ambiente Path ( `$env:path` ) na sessão remota, incluindo arquivos. txt,. exe e. dll.</span><span class="sxs-lookup"><span data-stu-id="91b29-224">`Application`: All the files other than Windows-PowerShell files in the paths that are listed in the Path environment variable (`$env:path`) in the remote session, including .txt, .exe, and .dll files.</span></span>
- <span data-ttu-id="91b29-225">`Cmdlet`: Os cmdlets na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="91b29-225">`Cmdlet`: The cmdlets in the remote session.</span></span> <span data-ttu-id="91b29-226">"Cmdlet" é o padrão.</span><span class="sxs-lookup"><span data-stu-id="91b29-226">"Cmdlet" is the default.</span></span>
- <span data-ttu-id="91b29-227">`ExternalScript`: Os arquivos. ps1 nos caminhos listados na variável de ambiente Path ( `$env:path` ) na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="91b29-227">`ExternalScript`: The .ps1 files in the paths listed in the Path environment variable (`$env:path`) in the remote session.</span></span>
- <span data-ttu-id="91b29-228">`Filter` e `Function` : as funções do Windows PowerShell na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="91b29-228">`Filter` and `Function`: The Windows PowerShell functions in the remote session.</span></span>
- <span data-ttu-id="91b29-229">`Script`: Os blocos de script na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="91b29-229">`Script`: The script blocks in the remote session.</span></span>

<span data-ttu-id="91b29-230">Esses valores são definidos como uma enumeração baseada em sinalizador.</span><span class="sxs-lookup"><span data-stu-id="91b29-230">These values are defined as a flag-based enumeration.</span></span> <span data-ttu-id="91b29-231">Você pode combinar vários valores juntos para definir vários sinalizadores usando esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="91b29-231">You can combine multiple values together to set multiple flags using this parameter.</span></span> <span data-ttu-id="91b29-232">Os valores podem ser passados para o parâmetro **CommandType** como uma matriz de valores ou como uma cadeia de caracteres separada por vírgulas desses valores.</span><span class="sxs-lookup"><span data-stu-id="91b29-232">The values can be passed to the **CommandType** parameter as an array of values or as a comma-separated string of those values.</span></span> <span data-ttu-id="91b29-233">O cmdlet combinará os valores usando uma operação binary ou.</span><span class="sxs-lookup"><span data-stu-id="91b29-233">The cmdlet will combine the values using a binary-OR operation.</span></span> <span data-ttu-id="91b29-234">Passar valores como uma matriz é a opção mais simples e também permite que você use a conclusão de tabulação nos valores.</span><span class="sxs-lookup"><span data-stu-id="91b29-234">Passing values as an array is the simplest option and also allows you to use tab-completion on the values.</span></span>

```yaml
Type: System.Management.Automation.CommandTypes
Parameter Sets: (All)
Aliases: Type
Accepted values: Alias, Function, Filter, Cmdlet, ExternalScript, Application, Script, Workflow, Configuration, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="91b29-235">-DisableNameChecking</span><span class="sxs-lookup"><span data-stu-id="91b29-235">-DisableNameChecking</span></span>

<span data-ttu-id="91b29-236">Indica que esse cmdlet suprime a mensagem que avisa quando você importa um cmdlet ou função cujo nome inclui um verbo não aprovado ou um caractere proibido.</span><span class="sxs-lookup"><span data-stu-id="91b29-236">Indicates that this cmdlet suppresses the message that warns you when you import a cmdlet or function whose name includes an unapproved verb or a prohibited character.</span></span>

<span data-ttu-id="91b29-237">Por padrão, quando um módulo que você importa exporta cmdlets ou funções que têm verbos não aprovados em seus nomes, o Windows PowerShell exibe a seguinte mensagem de aviso:</span><span class="sxs-lookup"><span data-stu-id="91b29-237">By default, when a module that you import exports cmdlets or functions that have unapproved verbs in their names, the Windows PowerShell displays the following warning message:</span></span>

<span data-ttu-id="91b29-238">"Aviso: alguns nomes de comando importados incluem verbos não aprovados que podem torná-los menos detectáveis.</span><span class="sxs-lookup"><span data-stu-id="91b29-238">"WARNING: Some imported command names include unapproved verbs which might make them less discoverable.</span></span> <span data-ttu-id="91b29-239">Use o parâmetro Verbose para obter mais detalhes ou digite `Get-Verb` para ver a lista de verbos aprovados.</span><span class="sxs-lookup"><span data-stu-id="91b29-239">Use the Verbose parameter for more detail or type `Get-Verb` to see the list of approved verbs."</span></span>

<span data-ttu-id="91b29-240">A mensagem é apenas um aviso.</span><span class="sxs-lookup"><span data-stu-id="91b29-240">This message is only a warning.</span></span> <span data-ttu-id="91b29-241">O módulo completo ainda é importado, incluindo os comandos não autorizados.</span><span class="sxs-lookup"><span data-stu-id="91b29-241">The complete module is still imported, including the non-conforming commands.</span></span> <span data-ttu-id="91b29-242">Embora a mensagem seja exibida para usuários do módulo, o problema de nomenclatura deve ser corrigido pelo autor do módulo.</span><span class="sxs-lookup"><span data-stu-id="91b29-242">Although the message is displayed to module users, the naming problem should be fixed by the module author.</span></span>

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

### <span data-ttu-id="91b29-243">-FormatTypeName</span><span class="sxs-lookup"><span data-stu-id="91b29-243">-FormatTypeName</span></span>

<span data-ttu-id="91b29-244">Especifica instruções de formatação para os tipos de estrutura de Microsoft .NET especificados.</span><span class="sxs-lookup"><span data-stu-id="91b29-244">Specifies formatting instructions for the specified Microsoft .NET Framework types.</span></span>
<span data-ttu-id="91b29-245">Insira os nomes de tipo.</span><span class="sxs-lookup"><span data-stu-id="91b29-245">Enter the type names.</span></span>
<span data-ttu-id="91b29-246">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="91b29-246">Wildcards are permitted.</span></span>

<span data-ttu-id="91b29-247">O valor desse parâmetro deve ser o nome de um tipo que é retornado por um `Get-FormatData` comando na sessão da qual os comandos estão sendo importados.</span><span class="sxs-lookup"><span data-stu-id="91b29-247">The value of this parameter must be the name of a type that is returned by a `Get-FormatData` command in the session from which the commands are being imported.</span></span> <span data-ttu-id="91b29-248">Para obter todos os dados de formatação na sessão remota, digite `*` .</span><span class="sxs-lookup"><span data-stu-id="91b29-248">To get all of the formatting data in the remote session, type `*`.</span></span>

<span data-ttu-id="91b29-249">Se o comando não incluir o parâmetro **CommandName** ou **FormatTypeName** , o `Import-PSSession` importará instruções de formatação para todos os tipos de .NET Framework retornados por um `Get-FormatData` comando na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="91b29-249">If the command does not include either the **CommandName** or **FormatTypeName** parameter, `Import-PSSession` imports formatting instructions for all .NET Framework types returned by a `Get-FormatData` command in the remote session.</span></span>

<span data-ttu-id="91b29-250">Se você usar o parâmetro **FormatTypeName**, nenhum comando será importado, a menos que você use o parâmetro **CommandName**.</span><span class="sxs-lookup"><span data-stu-id="91b29-250">If you use the **FormatTypeName** parameter, no commands are imported unless you use the **CommandName** parameter.</span></span>

<span data-ttu-id="91b29-251">Da mesma forma, se você usar o parâmetro **CommandName**, os arquivos de formatação para os comandos não serão importados a menos que você use o parâmetro **FormatTypeName**.</span><span class="sxs-lookup"><span data-stu-id="91b29-251">Similarly, if you use the **CommandName** parameter, the formatting files for the commands are not imported unless you use the **FormatTypeName** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="91b29-252">-FullyQualifiedModule</span><span class="sxs-lookup"><span data-stu-id="91b29-252">-FullyQualifiedModule</span></span>

<span data-ttu-id="91b29-253">Especifica os módulos com nomes que são especificados na forma de objetos **ModuleSpecification** (descritos na seção comentários do [Construtor ModuleSpecification (HASHTABLE)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_) no SDK do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91b29-253">Specifies modules with names that are specified in the form of **ModuleSpecification** objects (described in the Remarks section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_) in the PowerShell SDK.</span></span> <span data-ttu-id="91b29-254">Por exemplo, o parâmetro **FullyQualifiedModule** aceita um nome de módulo que é especificado no formato:</span><span class="sxs-lookup"><span data-stu-id="91b29-254">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in the format:</span></span>

- <span data-ttu-id="91b29-255">`@{ModuleName = "modulename"; ModuleVersion = "version_number"}` ou</span><span class="sxs-lookup"><span data-stu-id="91b29-255">`@{ModuleName = "modulename"; ModuleVersion = "version_number"}` or</span></span>
- <span data-ttu-id="91b29-256">`@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`.</span><span class="sxs-lookup"><span data-stu-id="91b29-256">`@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`.</span></span>

<span data-ttu-id="91b29-257">**ModuleName** e **ModuleVersion** são obrigatórios, mas **Guid** é opcional.</span><span class="sxs-lookup"><span data-stu-id="91b29-257">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span>

<span data-ttu-id="91b29-258">Você não pode especificar o parâmetro **FullyQualifiedModule** no mesmo comando que um parâmetro de **módulo** .</span><span class="sxs-lookup"><span data-stu-id="91b29-258">You cannot specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span> <span data-ttu-id="91b29-259">Os dois parâmetros são mutuamente exclusivos.</span><span class="sxs-lookup"><span data-stu-id="91b29-259">The two parameters are mutually exclusive.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="91b29-260">-Módulo</span><span class="sxs-lookup"><span data-stu-id="91b29-260">-Module</span></span>

<span data-ttu-id="91b29-261">Especifica e a matriz de comandos nos módulos e snap-ins do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91b29-261">Specifies and array of commands in the Windows PowerShell snap-ins and modules.</span></span> <span data-ttu-id="91b29-262">Digite os nomes de módulos e snap-ins.</span><span class="sxs-lookup"><span data-stu-id="91b29-262">Enter the snap-in and module names.</span></span> <span data-ttu-id="91b29-263">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="91b29-263">Wildcards are not permitted.</span></span>

<span data-ttu-id="91b29-264">`Import-PSSession` Não é possível importar provedores de um snap-in.</span><span class="sxs-lookup"><span data-stu-id="91b29-264">`Import-PSSession` cannot import providers from a snap-in.</span></span>

<span data-ttu-id="91b29-265">Para obter mais informações, consulte [about_PSSnapins](/powershell/module/Microsoft.PowerShell.Core/About/about_PSSnapins) e [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="91b29-265">For more information, see [about_PSSnapins](/powershell/module/Microsoft.PowerShell.Core/About/about_PSSnapins) and [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSSnapin

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="91b29-266">-Prefixo</span><span class="sxs-lookup"><span data-stu-id="91b29-266">-Prefix</span></span>

<span data-ttu-id="91b29-267">Especifica um prefixo para os substantivos nos nomes dos comandos importados.</span><span class="sxs-lookup"><span data-stu-id="91b29-267">Specifies a prefix to the nouns in the names of imported commands.</span></span>

<span data-ttu-id="91b29-268">Use este parâmetro para evitar conflitos de nome que podem ocorrer quando diferentes membros da sessão têm o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="91b29-268">Use this parameter to avoid name conflicts that might occur when different commands in the session have the same name.</span></span>

<span data-ttu-id="91b29-269">Por exemplo, se você especificar o prefixo Remote e, em seguida, importar um `Get-Date` cmdlet, o cmdlet será conhecido na sessão como `Get-RemoteDate` , e não será confundido com o `Get-Date` cmdlet original.</span><span class="sxs-lookup"><span data-stu-id="91b29-269">For instance, if you specify the prefix Remote and then import a `Get-Date` cmdlet, the cmdlet is known in the session as `Get-RemoteDate`, and it is not confused with the original `Get-Date` cmdlet.</span></span>

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

### <span data-ttu-id="91b29-270">-Sessão</span><span class="sxs-lookup"><span data-stu-id="91b29-270">-Session</span></span>

<span data-ttu-id="91b29-271">Especifica a **PSSession** da qual os cmdlets são importados.</span><span class="sxs-lookup"><span data-stu-id="91b29-271">Specifies the **PSSession** from which the cmdlets are imported.</span></span> <span data-ttu-id="91b29-272">Insira uma variável que contém um objeto de sessão ou um comando que obtém um objeto de sessão, como `New-PSSession` um `Get-PSSession` comando ou.</span><span class="sxs-lookup"><span data-stu-id="91b29-272">Enter a variable that contains a session object or a command that gets a session object, such as a `New-PSSession` or `Get-PSSession` command.</span></span> <span data-ttu-id="91b29-273">Você pode especificar somente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="91b29-273">You can specify only one session.</span></span> <span data-ttu-id="91b29-274">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="91b29-274">This parameter is required.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="91b29-275">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="91b29-275">CommonParameters</span></span>

<span data-ttu-id="91b29-276">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="91b29-276">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="91b29-277">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="91b29-277">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="91b29-278">Entradas</span><span class="sxs-lookup"><span data-stu-id="91b29-278">Inputs</span></span>

### <span data-ttu-id="91b29-279">Nenhum</span><span class="sxs-lookup"><span data-stu-id="91b29-279">None</span></span>

<span data-ttu-id="91b29-280">Não é possível transferir objetos para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="91b29-280">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="91b29-281">Saídas</span><span class="sxs-lookup"><span data-stu-id="91b29-281">Outputs</span></span>

### <span data-ttu-id="91b29-282">System. Management. Automation. PSModuleInfo</span><span class="sxs-lookup"><span data-stu-id="91b29-282">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="91b29-283">`Import-PSSession` Retorna o mesmo objeto de módulo que os `New-Module` `Get-Module` cmdlets retornam.</span><span class="sxs-lookup"><span data-stu-id="91b29-283">`Import-PSSession` returns the same module object that `New-Module` and `Get-Module` cmdlets return.</span></span>
<span data-ttu-id="91b29-284">No entanto, o módulo importado é temporário e existe somente na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="91b29-284">However, the imported module is temporary and exists only in the current session.</span></span> <span data-ttu-id="91b29-285">Para criar um módulo permanente no disco, use o `Export-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="91b29-285">To create a permanent module on disk, use the `Export-PSSession` cmdlet.</span></span>

## <span data-ttu-id="91b29-286">Observações</span><span class="sxs-lookup"><span data-stu-id="91b29-286">Notes</span></span>

- <span data-ttu-id="91b29-287">`Import-PSSession` depende da infraestrutura de comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91b29-287">`Import-PSSession` relies on the  PowerShell remoting infrastructure.</span></span> <span data-ttu-id="91b29-288">Para usar esse cmdlet, o computador deve ser configurado para comunicação remota do WS-Management.</span><span class="sxs-lookup"><span data-stu-id="91b29-288">To use this cmdlet, the computer must be configured for WS-Management remoting.</span></span> <span data-ttu-id="91b29-289">Para obter mais informações, consulte [about_Remote](../Microsoft.PowerShell.Core/about/about_Remote.md) e [about_Remote_Requirements](../Microsoft.PowerShell.Core/about/about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91b29-289">For more information, see [about_Remote](../Microsoft.PowerShell.Core/about/about_Remote.md) and [about_Remote_Requirements](../Microsoft.PowerShell.Core/about/about_Remote_Requirements.md).</span></span>
- <span data-ttu-id="91b29-290">`Import-PSSession` Não importa variáveis ou provedores do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91b29-290">`Import-PSSession` does not import variables or  PowerShell providers.</span></span>
- <span data-ttu-id="91b29-291">Quando você importa comandos que têm os mesmos nomes que comandos na sessão atual, os comandos importados podem ocultar aliases, funções e cmdlets na sessão e eles podem substituir funções e variáveis na sessão.</span><span class="sxs-lookup"><span data-stu-id="91b29-291">When you import commands that have the same names as commands in the current session, the imported commands can hide aliases, functions, and cmdlets in the session and they can replace functions and variables in the session.</span></span> <span data-ttu-id="91b29-292">Para evitar conflitos de nome, use o parâmetro **Prefix**.</span><span class="sxs-lookup"><span data-stu-id="91b29-292">To prevent name conflicts, use the **Prefix** parameter.</span></span> <span data-ttu-id="91b29-293">Para obter mais informações, confira [about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="91b29-293">For more information, see [about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md).</span></span>
- <span data-ttu-id="91b29-294">`Import-PSSession` Converte todos os comandos em funções antes de importá-los.</span><span class="sxs-lookup"><span data-stu-id="91b29-294">`Import-PSSession` converts all commands into functions before it imports them.</span></span> <span data-ttu-id="91b29-295">Como resultado, comandos importados possuem um comportamento um pouco diferente de quando mantém tipo de comando original.</span><span class="sxs-lookup"><span data-stu-id="91b29-295">As a result, imported commands behave a bit differently than they would if they retained their original command type.</span></span> <span data-ttu-id="91b29-296">Por exemplo, se você importar um cmdlet de uma PSSession e um cmdlet com o mesmo nome de um módulo ou snap-in, o cmdlet é importado da PSSession sempre será executado por padrão porque funções têm precedência sobre cmdlets.</span><span class="sxs-lookup"><span data-stu-id="91b29-296">For example, if you import a cmdlet from a PSSession and then import a cmdlet with the same name from a module or snap-in, the cmdlet that is imported from the PSSession always runs by default because functions take precedence over cmdlets.</span></span> <span data-ttu-id="91b29-297">Por outro lado, se você importar um alias para uma sessão com um alias com o mesmo nome, o alias original sempre é usado, pois aliases têm precedência sobre funções.</span><span class="sxs-lookup"><span data-stu-id="91b29-297">Conversely, if you import an alias into a session that has an alias with the same name, the original alias is always used, because aliases take precedence over functions.</span></span> <span data-ttu-id="91b29-298">Para obter mais informações, confira [about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="91b29-298">For more information, see [about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md).</span></span>
- <span data-ttu-id="91b29-299">`Import-PSSession` usa o `Write-Progress` cmdlet para exibir o progresso do comando.</span><span class="sxs-lookup"><span data-stu-id="91b29-299">`Import-PSSession` uses the `Write-Progress` cmdlet to display the progress of the command.</span></span> <span data-ttu-id="91b29-300">Você pode ver a barra de progresso enquanto o comando é executado.</span><span class="sxs-lookup"><span data-stu-id="91b29-300">You might see the progress bar while the command is running.</span></span>
- <span data-ttu-id="91b29-301">Para localizar os comandos a serem importados, `Import-PSSession` o usa o `Invoke-Command` cmdlet para executar um `Get-Command` comando na PSSession.</span><span class="sxs-lookup"><span data-stu-id="91b29-301">To find the commands to import, `Import-PSSession` uses the `Invoke-Command` cmdlet to run a `Get-Command` command in the PSSession.</span></span> <span data-ttu-id="91b29-302">Para obter dados de formatação para os comandos, ele usa o `Get-FormatData` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="91b29-302">To get formatting data for the commands, it uses the `Get-FormatData` cmdlet.</span></span> <span data-ttu-id="91b29-303">Você poderá ver mensagens de erro desses cmdlets ao executar um `Import-PSSession` comando.</span><span class="sxs-lookup"><span data-stu-id="91b29-303">You might see error messages from these cmdlets when you run an `Import-PSSession` command.</span></span> <span data-ttu-id="91b29-304">Além disso, `Import-PSSession` o não pode importar comandos de uma PSSession que não inclua os `Get-Command` `Get-FormatData` cmdlets,, `Select-Object` e `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="91b29-304">Also, `Import-PSSession` cannot import commands from a PSSession that does not include the `Get-Command`, `Get-FormatData`, `Select-Object`, and `Get-Help` cmdlets.</span></span>
- <span data-ttu-id="91b29-305">Comandos importados têm as mesmas limitações que outros comandos remotos, inclusive a incapacidade de iniciar um programa com uma interface de usuário, como o Bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="91b29-305">Imported commands have the same limitations as other remote commands, including the inability to start a program with a user interface, such as Notepad.</span></span>
- <span data-ttu-id="91b29-306">Como os perfis do Windows PowerShell não são executados em PSSessions, os comandos que um perfil adiciona a uma sessão não estão disponíveis para o `Import-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="91b29-306">Because Windows PowerShell profiles are not run in PSSessions, the commands that a profile adds to a session are not available to `Import-PSSession`.</span></span> <span data-ttu-id="91b29-307">Para importar comandos de um perfil, use um `Invoke-Command` comando para executar o perfil na PSSession manualmente antes de importar os comandos.</span><span class="sxs-lookup"><span data-stu-id="91b29-307">To import commands from a profile, use an `Invoke-Command` command to run the profile in the PSSession manually before importing commands.</span></span>
- <span data-ttu-id="91b29-308">O módulo temporário que o `Import-PSSession` cria pode incluir um arquivo de formatação, mesmo que o comando não importe dados de formatação.</span><span class="sxs-lookup"><span data-stu-id="91b29-308">The temporary module that `Import-PSSession` creates might include a formatting file, even if the command does not import formatting data.</span></span> <span data-ttu-id="91b29-309">Se o comando não importar dados de formatação, quaisquer arquivos de formatação criados não conterão dados de formatação.</span><span class="sxs-lookup"><span data-stu-id="91b29-309">If the command does not import formatting data, any formatting files that are created will not contain formatting data.</span></span>
- <span data-ttu-id="91b29-310">Para usar `Import-PSSession` o, a política de execução na sessão atual não pode ser restrita ou AllSigned, pois o módulo temporário que o `Import-PSSession` cria contém arquivos de script não assinados que são proibidos por essas políticas.</span><span class="sxs-lookup"><span data-stu-id="91b29-310">To use `Import-PSSession`, the execution policy in the current session cannot be Restricted or AllSigned, because the temporary module that `Import-PSSession` creates contains unsigned script files that are prohibited by these policies.</span></span> <span data-ttu-id="91b29-311">Para usar `Import-PSSession` sem alterar a política de execução para o computador local, use o parâmetro de **escopo** de `Set-ExecutionPolicy` para definir uma política de execução menos restritiva para um único processo.</span><span class="sxs-lookup"><span data-stu-id="91b29-311">To use `Import-PSSession` without changing the execution policy for the local computer, use the **Scope** parameter of `Set-ExecutionPolicy` to set a less restrictive execution policy for a single process.</span></span>
- <span data-ttu-id="91b29-312">No Windows PowerShell 2.0, os tópicos de ajuda para comandos importados de outra sessão não incluem o prefixo que você atribui usando o parâmetro **Prefix**.</span><span class="sxs-lookup"><span data-stu-id="91b29-312">In Windows PowerShell 2.0, help topics for commands that are imported from another session do not include the prefix that you assign by using the **Prefix** parameter.</span></span> <span data-ttu-id="91b29-313">Para obter ajuda sobre um comando importado no Windows PowerShell 2.0, use o nome original do comando (sem prefixo).</span><span class="sxs-lookup"><span data-stu-id="91b29-313">To get help for an imported command in Windows PowerShell 2.0, use the original (non-prefixed) command name.</span></span>

## <span data-ttu-id="91b29-314">Links Relacionados</span><span class="sxs-lookup"><span data-stu-id="91b29-314">Related Links</span></span>

[<span data-ttu-id="91b29-315">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="91b29-315">Export-PSSession</span></span>](Export-PSSession.md)
