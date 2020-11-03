---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-pssession?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PSSession
ms.openlocfilehash: ef5bf676e261e7a4267980a3e87753724ca9bf42
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194059"
---
# <span data-ttu-id="b6c12-103">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="b6c12-103">Import-PSSession</span></span>

## <span data-ttu-id="b6c12-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b6c12-104">SYNOPSIS</span></span>
<span data-ttu-id="b6c12-105">Importa comandos de outra sessão para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="b6c12-105">Imports commands from another session into the current session.</span></span>

## <span data-ttu-id="b6c12-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b6c12-106">SYNTAX</span></span>

```
Import-PSSession [-Prefix <String>] [-DisableNameChecking] [[-CommandName] <String[]>] [-AllowClobber]
 [-ArgumentList <Object[]>] [-CommandType <CommandTypes>] [-Module <String[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-FormatTypeName] <String[]>]
 [-Certificate <X509Certificate2>] [-Session] <PSSession> [<CommonParameters>]
```

## <span data-ttu-id="b6c12-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b6c12-107">DESCRIPTION</span></span>

<span data-ttu-id="b6c12-108">O cmdlet **Import-PSSession** importa comandos, como cmdlets, funções e aliases, de uma PSSession em um computador local ou remoto para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="b6c12-108">The **Import-PSSession** cmdlet imports commands , such as cmdlets, functions, and aliases, from a PSSession on a local or remote computer into the current session.</span></span>
<span data-ttu-id="b6c12-109">Você pode importar qualquer comando que o cmdlet Get-Command possa encontrar na PSSession.</span><span class="sxs-lookup"><span data-stu-id="b6c12-109">You can import any command that the Get-Command cmdlet can find in the PSSession.</span></span>

<span data-ttu-id="b6c12-110">Use um comando **Import-PSSession** para importar comandos de um shell personalizado, como um shell do Microsoft Exchange Server, ou de uma sessão que inclui módulos e snap-ins do PowerShell ou outros elementos que não estão na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="b6c12-110">Use an **Import-PSSession** command to import commands from a customized shell, such as a Microsoft Exchange Server shell, or from a session that includes PowerShell modules and snap-ins or other elements that are not in the current session.</span></span>

<span data-ttu-id="b6c12-111">Para importar comandos, primeiro use o cmdlet New-PSSession para criar uma PSSession.</span><span class="sxs-lookup"><span data-stu-id="b6c12-111">To import commands, first use the New-PSSession cmdlet to create a PSSession.</span></span>
<span data-ttu-id="b6c12-112">Em seguida, use o cmdlet **Import-PSSession** para importar os comandos.</span><span class="sxs-lookup"><span data-stu-id="b6c12-112">Then, use the **Import-PSSession** cmdlet to import the commands.</span></span>
<span data-ttu-id="b6c12-113">Por padrão, **Import-PSSession** importa todos os comandos, exceto aqueles possuem os mesmos nomes de comandos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="b6c12-113">By default, **Import-PSSession** imports all commands except for commands that have the same names as commands in the current session.</span></span>
<span data-ttu-id="b6c12-114">Para importar todos os comandos, use o parâmetro *AllowClobber* .</span><span class="sxs-lookup"><span data-stu-id="b6c12-114">To import all the commands, use the *AllowClobber* parameter.</span></span>

<span data-ttu-id="b6c12-115">Você pode usar comandos importados da mesma maneira que usaria qualquer comando na sessão.</span><span class="sxs-lookup"><span data-stu-id="b6c12-115">You can use imported commands just as you would use any command in the session.</span></span>
<span data-ttu-id="b6c12-116">Quando você usa um comando importado, a parte importada do comando é executada implicitamente na sessão da qual ele foi importado.</span><span class="sxs-lookup"><span data-stu-id="b6c12-116">When you use an imported command, the imported part of the command runs implicitly in the session from which it was imported.</span></span>
<span data-ttu-id="b6c12-117">No entanto, as operações remotas são manipuladas inteiramente pelo PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6c12-117">However, the remote operations are handled entirely by PowerShell.</span></span>
<span data-ttu-id="b6c12-118">Você não precisa nem estar ciente delas, exceto de que a conexão com a outra sessão (PSSession) deve ser mantida aberta.</span><span class="sxs-lookup"><span data-stu-id="b6c12-118">You need not even be aware of them, except that you must keep the connection to the other session (PSSession) open.</span></span>
<span data-ttu-id="b6c12-119">Se ela for fechada, os comandos importados não estarão mais disponíveis.</span><span class="sxs-lookup"><span data-stu-id="b6c12-119">If you close it, the imported commands are no longer available.</span></span>

<span data-ttu-id="b6c12-120">Como comandos importados podem levar mais tempo que comandos locais, o **Import-PSSession** adiciona um parâmetro *AsJob* a cada comando importado.</span><span class="sxs-lookup"><span data-stu-id="b6c12-120">Because imported commands might take longer to run than local commands, **Import-PSSession** adds an *AsJob* parameter to every imported command.</span></span>
<span data-ttu-id="b6c12-121">Esse parâmetro permite que você execute o comando como um trabalho em segundo plano do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6c12-121">This parameter allows you to run the command as a PowerShell background job.</span></span>
<span data-ttu-id="b6c12-122">Para obter mais informações, consulte about_Jobs.</span><span class="sxs-lookup"><span data-stu-id="b6c12-122">For more information, see about_Jobs.</span></span>

<span data-ttu-id="b6c12-123">Quando você usa **Import-PSSession** , o PowerShell adiciona os comandos importados a um módulo temporário que existe somente em sua sessão e retorna um objeto que representa o módulo.</span><span class="sxs-lookup"><span data-stu-id="b6c12-123">When you use **Import-PSSession** , PowerShell adds the imported commands to a temporary module that exists only in your session and returns an object that represents the module.</span></span>
<span data-ttu-id="b6c12-124">Para criar um módulo persistente que você pode usar em sessões futuras, use o cmdlet Export-PSSession.</span><span class="sxs-lookup"><span data-stu-id="b6c12-124">To create a persistent module that you can use in future sessions, use the Export-PSSession cmdlet.</span></span>

<span data-ttu-id="b6c12-125">O cmdlet **Import-PSSession** usa o recurso de comunicação remota implícita do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6c12-125">The **Import-PSSession** cmdlet uses the implicit remoting feature of PowerShell.</span></span>
<span data-ttu-id="b6c12-126">Quando você importa comandos para a sessão atual, eles são executados implicitamente na sessão original ou em uma sessão semelhante no computador de origem.</span><span class="sxs-lookup"><span data-stu-id="b6c12-126">When you import commands into the current session, they run implicitly in the original session or in a similar session on the originating computer.</span></span>

<span data-ttu-id="b6c12-127">A partir do Windows PowerShell 3,0, você pode usar o cmdlet Import-Module para importar módulos de uma sessão remota para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="b6c12-127">Beginning in Windows PowerShell 3.0, you can use the Import-Module cmdlet to import modules from a remote session into the current session.</span></span>
<span data-ttu-id="b6c12-128">Esse recurso usa a comunicação remota implícita.</span><span class="sxs-lookup"><span data-stu-id="b6c12-128">This feature uses implicit remoting.</span></span>
<span data-ttu-id="b6c12-129">Ele é equivalente a usar o **Import-PSSession** para importar os módulos selecionados de uma sessão remota para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="b6c12-129">It is equivalent to using **Import-PSSession** to import selected modules from a remote session into the current session.</span></span>

## <span data-ttu-id="b6c12-130">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b6c12-130">EXAMPLES</span></span>

### <span data-ttu-id="b6c12-131">Exemplo 1: importar todos os comandos de uma PSSession</span><span class="sxs-lookup"><span data-stu-id="b6c12-131">Example 1: Import all commands from a PSSession</span></span>

```
PS C:\> $S = New-PSSession -ComputerName Server01
PS C:\> Import-PSSession -Session $S
```

<span data-ttu-id="b6c12-132">Este comando importa todos os comandos de uma PSSession no computador Server01 para a sessão atual, com exceção de comandos que possuem os mesmos nomes de comandos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="b6c12-132">This command imports all commands from a PSSession on the Server01 computer into the current session, except for commands that have the same names as commands in the current session.</span></span>

<span data-ttu-id="b6c12-133">Como esse comando não usa o parâmetro *CommandName* , ele também importa todos os dados de formatação necessários para os comandos importados.</span><span class="sxs-lookup"><span data-stu-id="b6c12-133">Because this command does not use the *CommandName* parameter, it also imports all of the formatting data required for the imported commands.</span></span>

### <span data-ttu-id="b6c12-134">Exemplo 2: importar comandos que terminam com uma cadeia de caracteres específica</span><span class="sxs-lookup"><span data-stu-id="b6c12-134">Example 2: Import commands that end with a specific string</span></span>

```
PS C:\> $S = New-PSSession https://ps.testlabs.com/powershell
PS C:\> Import-PSSession -Session $S -CommandName *-test -FormatTypeName *
PS C:\> New-Test -Name Test1
PS C:\> Get-Test test1 | Run-Test
```

<span data-ttu-id="b6c12-135">Esses comandos importam os comandos com nomes que terminam em "-test" de uma PSSession para a sessão local e mostram como usar um cmdlet importado.</span><span class="sxs-lookup"><span data-stu-id="b6c12-135">These commands import the commands with names that end in "-test" from a PSSession into the local session, and then they show how to use an imported cmdlet.</span></span>

<span data-ttu-id="b6c12-136">O primeiro comando usa o cmdlet New-PSSession para criar uma PSSession.</span><span class="sxs-lookup"><span data-stu-id="b6c12-136">The first command uses the New-PSSession cmdlet to create a PSSession.</span></span>
<span data-ttu-id="b6c12-137">Ele salva a PSSession na variável $S.</span><span class="sxs-lookup"><span data-stu-id="b6c12-137">It saves the PSSession in the $S variable.</span></span>

<span data-ttu-id="b6c12-138">O segundo comando usa o cmdlet **Import-PSSession** para importar comandos da PSSession em $S para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="b6c12-138">The second command uses the **Import-PSSession** cmdlet to import commands from the PSSession in $S into the current session.</span></span>
<span data-ttu-id="b6c12-139">Ele usa o parâmetro *CommandName* para especificar comandos com o substantivo Test (Teste) e o parâmetro *FormatTypeName* para importar os dados de formatação para os comandos Test.</span><span class="sxs-lookup"><span data-stu-id="b6c12-139">It uses the *CommandName* parameter to specify commands with the Test noun and the *FormatTypeName* parameter to import the formatting data for the Test commands.</span></span>

<span data-ttu-id="b6c12-140">Os terceiro e o quarto comandos usam os comandos importados na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="b6c12-140">The third and fourth commands use the imported commands in the current session.</span></span>
<span data-ttu-id="b6c12-141">Como comandos importados, na verdade, são adicionados à sessão atual, a sintaxe local é usada para executá-los.</span><span class="sxs-lookup"><span data-stu-id="b6c12-141">Because imported commands are actually added to the current session, you use the local syntax to run them.</span></span>
<span data-ttu-id="b6c12-142">Você não precisa usar o cmdlet Invoke-Command para executar um comando importado.</span><span class="sxs-lookup"><span data-stu-id="b6c12-142">You do not need to use the Invoke-Command cmdlet to run an imported command.</span></span>

### <span data-ttu-id="b6c12-143">Exemplo 3: importar cmdlets de uma PSSession</span><span class="sxs-lookup"><span data-stu-id="b6c12-143">Example 3: Import cmdlets from a PSSession</span></span>

```
PS C:\> $S1 = New-PSSession -ComputerName s1
PS C:\> $S2 = New-PSSession -ComputerName s2
PS C:\> Import-PSSession -Session s1 -Type cmdlet -Name New-Test, Get-Test -FormatTypeName *
PS C:\> Import-PSSession -Session s2 -Type Cmdlet -Name Set-Test -FormatTypeName *
PS C:\> New-Test Test1 | Set-Test -RunType Full
```

<span data-ttu-id="b6c12-144">Este exemplo mostra que é possível usar cmdlets importados da mesma maneira que cmdlets locais.</span><span class="sxs-lookup"><span data-stu-id="b6c12-144">This example shows that you can use imported cmdlets just as you would use local cmdlets.</span></span>

<span data-ttu-id="b6c12-145">Esses comandos importam os cmdlets New-Test e Get-Test uma PSSession no computador Server01 e o cmdlet Set-Test de uma PSSession no computador Server02.</span><span class="sxs-lookup"><span data-stu-id="b6c12-145">These commands import the New-Test and Get-Test cmdlets from a PSSession on the Server01 computer and the Set-Test cmdlet from a PSSession on the Server02 computer.</span></span>

<span data-ttu-id="b6c12-146">Embora os cmdlets sejam importados de diferentes PSSessions, é possível direcionar um objeto de um cmdlet para outro sem erro.</span><span class="sxs-lookup"><span data-stu-id="b6c12-146">Even though the cmdlets were imported from different PSSessions, you can pipe an object from one cmdlet to another without error.</span></span>

### <span data-ttu-id="b6c12-147">Exemplo 4: executar um comando importado como um trabalho em segundo plano</span><span class="sxs-lookup"><span data-stu-id="b6c12-147">Example 4: Run an imported command as a background job</span></span>

```
PS C:\> $S = New-PSSession -ComputerName Server01
PS C:\> Import-PSSession -Session $S -CommandName *-test* -FormatTypeName *
PS C:\> $batch = New-Test -Name Batch -AsJob
PS C:\> Receive-Job $batch
```

<span data-ttu-id="b6c12-148">Este exemplo mostra como executar um comando importado como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="b6c12-148">This example shows how to run an imported command as a background job.</span></span>

<span data-ttu-id="b6c12-149">Como comandos importados podem levar mais tempo que comandos locais, o **Import-PSSession** adiciona um parâmetro *AsJob* a cada comando importado.</span><span class="sxs-lookup"><span data-stu-id="b6c12-149">Because imported commands might take longer to run than local commands, **Import-PSSession** adds an *AsJob* parameter to every imported command.</span></span>
<span data-ttu-id="b6c12-150">O parâmetro *AsJob* permite que você execute o comando como um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="b6c12-150">The *AsJob* parameter lets you run the command as a background job.</span></span>

<span data-ttu-id="b6c12-151">O primeiro comando cria uma PSSession no computador Server01 e salva o objeto PSSession na variável $S.</span><span class="sxs-lookup"><span data-stu-id="b6c12-151">The first command creates a PSSession on the Server01 computer and saves the PSSession object in the $S variable.</span></span>

<span data-ttu-id="b6c12-152">O segundo comando usa **Import-PSSession** para importar os cmdlets de teste da PSSession em $S para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="b6c12-152">The second command uses **Import-PSSession** to import the Test cmdlets from the PSSession in $S into the current session.</span></span>

<span data-ttu-id="b6c12-153">O terceiro comando usa o parâmetro *AsJob* do cmdlet New-Test importado para executar um comando New-Test um trabalho em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="b6c12-153">The third command uses the *AsJob* parameter of the imported New-Test cmdlet to run a New-Test command as a background job.</span></span>
<span data-ttu-id="b6c12-154">O comando salva o objeto de trabalho retornado pelo New-Test na variável $batch.</span><span class="sxs-lookup"><span data-stu-id="b6c12-154">The command saves the job object that New-Test returns in the $batch variable.</span></span>

<span data-ttu-id="b6c12-155">O quarto comando usa o cmdlet Receive-Job para obter os resultados do trabalho na variável $batch.</span><span class="sxs-lookup"><span data-stu-id="b6c12-155">The fourth command uses the Receive-Job cmdlet to get the results of the job in the $batch variable.</span></span>

### <span data-ttu-id="b6c12-156">Exemplo 5: importar cmdlets e funções de um módulo do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6c12-156">Example 5: Import cmdlets and functions from a PowerShell module</span></span>

```
PS C:\> $S = New-PSSession -ComputerName Server01
PS C:\> Invoke-Command -Session $S {Import-Module TestManagement}
PS C:\> Import-PSSession -Session $S -Module TestManagement
```

<span data-ttu-id="b6c12-157">Este exemplo mostra como importar os cmdlets e funções de um módulo do PowerShell em um computador remoto para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="b6c12-157">This example shows how to import the cmdlets and functions from a PowerShell module on a remote computer into the current session.</span></span>

<span data-ttu-id="b6c12-158">O primeiro comando cria uma PSSession no computador Server01 e a salva na variável $S.</span><span class="sxs-lookup"><span data-stu-id="b6c12-158">The first command creates a PSSession on the Server01 computer and saves it in the $S variable.</span></span>

<span data-ttu-id="b6c12-159">O segundo comando usa o cmdlet **Invoke-Command** para executar um comando Import-Module na PSSession em $S.</span><span class="sxs-lookup"><span data-stu-id="b6c12-159">The second command uses the **Invoke-Command** cmdlet to run an Import-Module command in the PSSession in $S.</span></span>

<span data-ttu-id="b6c12-160">Normalmente, o módulo seria adicionado a todas as sessões por um comando **Import-Module** em um perfil do PowerShell, mas os perfis não são executados em PSSessions.</span><span class="sxs-lookup"><span data-stu-id="b6c12-160">Typically, the module would be added to all sessions by an **Import-Module** command in a PowerShell profile, but profiles are not run in PSSessions.</span></span>

<span data-ttu-id="b6c12-161">O terceiro comando usa o parâmetro *Module*  de **Import-PSSession** para importar os cmdlets e funções no módulo para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="b6c12-161">The third command uses the *Module*  parameter of **Import-PSSession** to import the cmdlets and functions in the module into the current session.</span></span>

### <span data-ttu-id="b6c12-162">Exemplo 6: criar um módulo em um arquivo temporário</span><span class="sxs-lookup"><span data-stu-id="b6c12-162">Example 6: Create a module in a temporary file</span></span>

```
PS C:\> Import-PSSession $S -CommandName Get-Date, SearchHelp -FormatTypeName * -AllowClobber

Name              : tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1zunz.ttf
Path              : C:\Users\User01\AppData\Local\Temp\tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1zunz.ttf\tmp_79468106-4e1d-4d90-af97-1154f9317239_
tcw1zunz.ttf.psm1
Description       : Implicit remoting for http://server01.corp.fabrikam.com/wsman
Guid              : 79468106-4e1d-4d90-af97-1154f9317239
Version           : 1.0
ModuleBase        : C:\Users\User01\AppData\Local\Temp\tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1zunz.ttf
ModuleType        : Script
PrivateData       : {ImplicitRemoting}
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Get-Date, Get-Date], [SearchHelp, SearchHelp]}
ExportedVariables : {}
NestedModules     : {}
```

<span data-ttu-id="b6c12-163">Este exemplo mostra que o **Import-PSSession** cria um módulo em um arquivo temporário no disco.</span><span class="sxs-lookup"><span data-stu-id="b6c12-163">This example shows that **Import-PSSession** creates a module in a temporary file on disk.</span></span>
<span data-ttu-id="b6c12-164">Ele também mostra que todos os comandos são convertidos em funções antes de serem importados para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="b6c12-164">It also shows that all commands are converted into functions before they are imported into the current session.</span></span>

<span data-ttu-id="b6c12-165">O comando usa o cmdlet **Import-PSSession** para importar um cmdlet Get-Date e uma função SearchHelp para a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="b6c12-165">The command uses the **Import-PSSession** cmdlet to import a Get-Date cmdlet and a SearchHelp function into the current session.</span></span>

<span data-ttu-id="b6c12-166">O cmdlet **Import-PSSession** retorna um objeto **PSModuleInfo** que representa o módulo temporário.</span><span class="sxs-lookup"><span data-stu-id="b6c12-166">The **Import-PSSession** cmdlet returns a **PSModuleInfo** object that represents the temporary module.</span></span>
<span data-ttu-id="b6c12-167">O valor da propriedade **Path** mostra que o **Import-PSSession** criou um arquivo de módulo do script (.psm1) em um local temporário.</span><span class="sxs-lookup"><span data-stu-id="b6c12-167">The value of the **Path** property shows that **Import-PSSession** created a script module (.psm1) file in a temporary location.</span></span>
<span data-ttu-id="b6c12-168">A propriedade **ExportedFunctions** mostra que o cmdlet **Get-Date** e a função SearchHelp foram importados como funções.</span><span class="sxs-lookup"><span data-stu-id="b6c12-168">The **ExportedFunctions** property shows that the **Get-Date** cmdlet and the SearchHelp function were both imported as functions.</span></span>

### <span data-ttu-id="b6c12-169">Exemplo 7: executar um comando que está oculto por um comando importado</span><span class="sxs-lookup"><span data-stu-id="b6c12-169">Example 7: Run a command that is hidden by an imported command</span></span>

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

<span data-ttu-id="b6c12-170">Este exemplo mostra como executar um comando que está oculto por um comando importado.</span><span class="sxs-lookup"><span data-stu-id="b6c12-170">This example shows how to run a command that is hidden by an imported command.</span></span>

<span data-ttu-id="b6c12-171">O primeiro comando importa um cmdlet Get-Date da PSSession na variável $S.</span><span class="sxs-lookup"><span data-stu-id="b6c12-171">The first command imports a Get-Date cmdlet from the PSSession in the $S variable.</span></span>
<span data-ttu-id="b6c12-172">Como a sessão atual inclui um cmdlet **Get-Date** , o parâmetro *AllowClobber* é necessário no comando.</span><span class="sxs-lookup"><span data-stu-id="b6c12-172">Because the current session includes a **Get-Date** cmdlet, the *AllowClobber* parameter is required in the command.</span></span>

<span data-ttu-id="b6c12-173">O segundo comando usa o parâmetro **All** do cmdlet Get-Command para obter todos os comandos **Get-Date** na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="b6c12-173">The second command uses the **All** parameter of the Get-Command cmdlet to get all **Get-Date** commands in the current session.</span></span>
<span data-ttu-id="b6c12-174">A saída mostra que a sessão inclui o cmdlet **Get-Date** original e uma função **Get-Date** .</span><span class="sxs-lookup"><span data-stu-id="b6c12-174">The output shows that the session includes the original **Get-Date** cmdlet and a **Get-Date** function.</span></span>
<span data-ttu-id="b6c12-175">A função **Get-Date** executa o cmdlet **Get-Date** importado na PSSession no $S.</span><span class="sxs-lookup"><span data-stu-id="b6c12-175">The **Get-Date** function runs the imported **Get-Date** cmdlet in the PSSession in $S.</span></span>

<span data-ttu-id="b6c12-176">O terceiro comando executa um comando **Get-Date** .</span><span class="sxs-lookup"><span data-stu-id="b6c12-176">The third command runs a **Get-Date** command.</span></span>
<span data-ttu-id="b6c12-177">Como as funções têm precedência sobre os cmdlets, o PowerShell executa a função de **Get-Date** importada, que retorna uma data do calendário juliano.</span><span class="sxs-lookup"><span data-stu-id="b6c12-177">Because functions take precedence over cmdlets, PowerShell runs the imported **Get-Date** function, which returns a Julian date.</span></span>

<span data-ttu-id="b6c12-178">Os quarto e quinto comandos mostram como usar um nome qualificado para executar um comando que está oculto por um comando importado.</span><span class="sxs-lookup"><span data-stu-id="b6c12-178">The fourth and fifth commands show how to use a qualified name to run a command that is hidden by an imported command.</span></span>

<span data-ttu-id="b6c12-179">O quarto comando obtém o nome do snap-in do PowerShell que adicionou o cmdlet **Get-Date** original à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="b6c12-179">The fourth command gets the name of the PowerShell snap-in that added the original **Get-Date** cmdlet to the current session.</span></span>

<span data-ttu-id="b6c12-180">O quinto comando usa o nome qualificado do snap-in do cmdlet **Get-Date** para executar um comando **Get-Date** .</span><span class="sxs-lookup"><span data-stu-id="b6c12-180">The fifth command uses the snap-in-qualified name of the **Get-Date** cmdlet to run a **Get-Date** command.</span></span>

<span data-ttu-id="b6c12-181">Para obter mais informações sobre precedência de comandos e comandos ocultos, consulte about_Command_Precedence.</span><span class="sxs-lookup"><span data-stu-id="b6c12-181">For more information about command precedence and hidden commands, see about_Command_Precedence.</span></span>

### <span data-ttu-id="b6c12-182">Exemplo 8: importar comandos que têm uma cadeia de caracteres específica em seus nomes</span><span class="sxs-lookup"><span data-stu-id="b6c12-182">Example 8: Import commands that have a specific string in their names</span></span>

```
PS C:\> Import-PSSession -Session $S -CommandName *Item* -AllowClobber
```

<span data-ttu-id="b6c12-183">Este comando importa os comandos cujos nomes incluem item da PSSession no $S.</span><span class="sxs-lookup"><span data-stu-id="b6c12-183">This command imports commands whose names include Item from the PSSession in $S.</span></span>
<span data-ttu-id="b6c12-184">Como o comando inclui o parâmetro *CommandName* , mas não o parâmetro *FormatTypeData* , somente o comando é importado.</span><span class="sxs-lookup"><span data-stu-id="b6c12-184">Because the command includes the *CommandName* parameter but not the *FormatTypeData* parameter, only the command is imported.</span></span>

<span data-ttu-id="b6c12-185">Use esse comando quando usar o **Import-PSSession** para executar um comando em um computador remoto se já possuir os dados de formatação na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="b6c12-185">Use this command when you are using **Import-PSSession** to run a command on a remote computer and you already have the formatting data for the command in the current session.</span></span>

### <span data-ttu-id="b6c12-186">Exemplo 9: usar o parâmetro Module para descobrir quais comandos foram importados para a sessão</span><span class="sxs-lookup"><span data-stu-id="b6c12-186">Example 9: Use the Module parameter to discover which commands were imported into the session</span></span>

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

<span data-ttu-id="b6c12-187">Este comando mostra como usar o parâmetro *Module* do **Get-Command** para descobrir quais comandos foram importados para a sessão por um comando **Import-PSSession** .</span><span class="sxs-lookup"><span data-stu-id="b6c12-187">This command shows how to use the *Module* parameter of **Get-Command** to find out which commands were imported into the session by an **Import-PSSession** command.</span></span>

<span data-ttu-id="b6c12-188">O primeiro comando usa o cmdlet **Import-PSSession** para importar comandos cujos nomes incluem "bits" da PSSession na variável $S.</span><span class="sxs-lookup"><span data-stu-id="b6c12-188">The first command uses the **Import-PSSession** cmdlet to import commands whose names include "bits" from the PSSession in the $S variable.</span></span>
<span data-ttu-id="b6c12-189">O comando **Import-PSSession** retorna um módulo temporário e o comando salva o módulo na variável $m.</span><span class="sxs-lookup"><span data-stu-id="b6c12-189">The **Import-PSSession** command returns a temporary module, and the command saves the module in the $m variable.</span></span>

<span data-ttu-id="b6c12-190">O segundo comando usa o cmdlet Get-Command para obter os comandos que são exportados pelo módulo na variável $M.</span><span class="sxs-lookup"><span data-stu-id="b6c12-190">The second command uses the Get-Command cmdlet to get the commands that are exported by the module in the $M variable.</span></span>

<span data-ttu-id="b6c12-191">O parâmetro *Module* obtém um valor de cadeia de caracteres, que é projetado para o nome do módulo.</span><span class="sxs-lookup"><span data-stu-id="b6c12-191">The *Module* parameter takes a string value, which is designed for the module name.</span></span>
<span data-ttu-id="b6c12-192">No entanto, quando você envia um objeto de módulo, o PowerShell usa o método **ToString** no objeto Module, que retorna o nome do módulo.</span><span class="sxs-lookup"><span data-stu-id="b6c12-192">However, when you submit a module object, PowerShell uses the **ToString** method on the module object, which returns the module name.</span></span>

<span data-ttu-id="b6c12-193">O comando **Get-Command** é o equivalente a `Get-Command $M.Name` ".</span><span class="sxs-lookup"><span data-stu-id="b6c12-193">The **Get-Command** command is the equivalent of `Get-Command $M.Name`".</span></span>

## <span data-ttu-id="b6c12-194">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b6c12-194">PARAMETERS</span></span>

### <span data-ttu-id="b6c12-195">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="b6c12-195">-AllowClobber</span></span>

<span data-ttu-id="b6c12-196">Indica que esse cmdlet importa os comandos especificados, mesmo que eles tenham os mesmos nomes que os comandos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="b6c12-196">Indicates that this cmdlet imports the specified commands, even if they have the same names as commands in the current session.</span></span>

<span data-ttu-id="b6c12-197">Se você importar um comando com o mesmo nome de um comando na sessão atual, os comandos importado ocultam ou substituem os originais.</span><span class="sxs-lookup"><span data-stu-id="b6c12-197">If you import a command with the same name as a command in the current session, the imported command hides or replaces the original commands.</span></span>
<span data-ttu-id="b6c12-198">Para obter mais informações, consulte about_Command_Precedence.</span><span class="sxs-lookup"><span data-stu-id="b6c12-198">For more information, see about_Command_Precedence.</span></span>

<span data-ttu-id="b6c12-199">Por padrão, o **Import-PSSession** não importa comandos que têm o mesmo nome de comandos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="b6c12-199">By default, **Import-PSSession** does not import commands that have the same name as commands in the current session.</span></span>

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

### <span data-ttu-id="b6c12-200">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="b6c12-200">-ArgumentList</span></span>

<span data-ttu-id="b6c12-201">Especifica uma matriz de comandos que resulta do uso dos argumentos especificados (valores de parâmetro).</span><span class="sxs-lookup"><span data-stu-id="b6c12-201">Specifies an array of commands that results from using the specified arguments (parameter values).</span></span>

<span data-ttu-id="b6c12-202">Por exemplo, para importar a variante do comando Get-Item no certificado (CERT:) na PSSession em $S, digite `Import-PSSession -Session $S -Command Get-Item -ArgumentList cert:` .</span><span class="sxs-lookup"><span data-stu-id="b6c12-202">For instance, to import the variant of the Get-Item command in the certificate (Cert:) drive in the PSSession in $S, type `Import-PSSession -Session $S -Command Get-Item -ArgumentList cert:`.</span></span>

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

### <span data-ttu-id="b6c12-203">-Certificado</span><span class="sxs-lookup"><span data-stu-id="b6c12-203">-Certificate</span></span>

<span data-ttu-id="b6c12-204">Especifica o certificado de cliente que é usado para assinar os arquivos de formato (\*.Format. ps1xml) ou arquivos de módulo de script (.psm1) no módulo temporário de script que **Import-PSSession** cria.</span><span class="sxs-lookup"><span data-stu-id="b6c12-204">Specifies the client certificate that is used to sign the format files (\*.Format.ps1xml) or script module files (.psm1) in the temporary module that **Import-PSSession** creates.</span></span>

<span data-ttu-id="b6c12-205">Insira uma variável que contém um certificado, comando ou expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="b6c12-205">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="b6c12-206">Para localizar um certificado, use o cmdlet Get-PfxCertificate ou use o cmdlet Get-ChildItem no certificado (CERT:) Dirigir.</span><span class="sxs-lookup"><span data-stu-id="b6c12-206">To find a certificate, use the Get-PfxCertificate cmdlet or use the Get-ChildItem cmdlet in the Certificate (Cert:) drive.</span></span>
<span data-ttu-id="b6c12-207">Se o certificado não for válido ou não tiver autoridade suficiente, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="b6c12-207">If the certificate is not valid or does not have sufficient authority, the command fails.</span></span>

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

### <span data-ttu-id="b6c12-208">-CommandName</span><span class="sxs-lookup"><span data-stu-id="b6c12-208">-CommandName</span></span>

<span data-ttu-id="b6c12-209">Especifica os comandos com os nomes especificados ou padrões de nome.</span><span class="sxs-lookup"><span data-stu-id="b6c12-209">Specifies commands with the specified names or name patterns.</span></span>
<span data-ttu-id="b6c12-210">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="b6c12-210">Wildcards are permitted.</span></span>
<span data-ttu-id="b6c12-211">Use *CommandName* ou seu alias, *Name* .</span><span class="sxs-lookup"><span data-stu-id="b6c12-211">Use *CommandName* or its alias, *Name* .</span></span>

<span data-ttu-id="b6c12-212">Por padrão, o **Import-PSSession** importa todos os comandos da sessão, com exceção de comandos com os mesmos nomes de comandos na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="b6c12-212">By default, **Import-PSSession** imports all commands from the session, except for commands that have the same names as commands in the current session.</span></span>
<span data-ttu-id="b6c12-213">Isso impede que os comandos importados ocultem ou substituam os comandos da sessão.</span><span class="sxs-lookup"><span data-stu-id="b6c12-213">This prevents imported commands from hiding or replacing commands in the session.</span></span>
<span data-ttu-id="b6c12-214">Para importar todos os comandos, mesmo aqueles que ocultam ou substituem outros comandos, use o parâmetro *AllowClobber* .</span><span class="sxs-lookup"><span data-stu-id="b6c12-214">To import all commands, even those that hide or replace other commands, use the *AllowClobber* parameter.</span></span>

<span data-ttu-id="b6c12-215">Se você usar o parâmetro *CommandName* , os arquivos de formatação para os comandos não serão importados a menos que você use o parâmetro *FormatTypeName* .</span><span class="sxs-lookup"><span data-stu-id="b6c12-215">If you use the *CommandName* parameter, the formatting files for the commands are not imported unless you use the *FormatTypeName* parameter.</span></span>
<span data-ttu-id="b6c12-216">Da mesma forma, se você usar o parâmetro *FormatTypeName* , nenhum comando é importado, a menos que você use o parâmetro *CommandName* .</span><span class="sxs-lookup"><span data-stu-id="b6c12-216">Similarly, if you use the *FormatTypeName* parameter, no commands are imported unless you use the *CommandName* parameter.</span></span>

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

### <span data-ttu-id="b6c12-217">-CommandType</span><span class="sxs-lookup"><span data-stu-id="b6c12-217">-CommandType</span></span>

<span data-ttu-id="b6c12-218">Especifica o tipo de objetos de comando.</span><span class="sxs-lookup"><span data-stu-id="b6c12-218">Specifies the type of command objects.</span></span>
<span data-ttu-id="b6c12-219">O valor padrão é Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b6c12-219">The default value is Cmdlet.</span></span>
<span data-ttu-id="b6c12-220">Use o *CommandType* ou seu alias, *Type* .</span><span class="sxs-lookup"><span data-stu-id="b6c12-220">Use *CommandType* or its alias, *Type* .</span></span>
<span data-ttu-id="b6c12-221">Os valores aceitáveis para esse parâmetro são:</span><span class="sxs-lookup"><span data-stu-id="b6c12-221">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b6c12-222">Receber.</span><span class="sxs-lookup"><span data-stu-id="b6c12-222">Alias.</span></span>
<span data-ttu-id="b6c12-223">Os aliases do PowerShell na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="b6c12-223">The PowerShell aliases in the remote session.</span></span>
- <span data-ttu-id="b6c12-224">Todos.</span><span class="sxs-lookup"><span data-stu-id="b6c12-224">All.</span></span>
<span data-ttu-id="b6c12-225">Os cmdlets e funções na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="b6c12-225">The cmdlets and functions in the remote session.</span></span>
- <span data-ttu-id="b6c12-226">Console.</span><span class="sxs-lookup"><span data-stu-id="b6c12-226">Application.</span></span>
<span data-ttu-id="b6c12-227">Todos os arquivos que não sejam arquivos do PowerShell nos caminhos listados na variável de ambiente Path ($env:p Ho) na sessão remota, incluindo arquivos. txt,. exe e. dll.</span><span class="sxs-lookup"><span data-stu-id="b6c12-227">All the files other than PowerShell files in the paths that are listed in the Path environment variable ($env:path) in the remote session, including .txt, .exe, and .dll files.</span></span>
- <span data-ttu-id="b6c12-228">Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b6c12-228">Cmdlet.</span></span>
<span data-ttu-id="b6c12-229">Os cmdlets na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="b6c12-229">The cmdlets in the remote session.</span></span>
<span data-ttu-id="b6c12-230">"Cmdlet" é o padrão.</span><span class="sxs-lookup"><span data-stu-id="b6c12-230">"Cmdlet" is the default.</span></span>
- <span data-ttu-id="b6c12-231">ExternalScript.</span><span class="sxs-lookup"><span data-stu-id="b6c12-231">ExternalScript.</span></span>
<span data-ttu-id="b6c12-232">Os arquivos .ps1 nos caminhos listados na variável de ambiente Path ($env:ath) na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="b6c12-232">The .ps1 files in the paths listed in the Path environment variable ($env:path) in the remote session.</span></span>
- <span data-ttu-id="b6c12-233">Filtro e função.</span><span class="sxs-lookup"><span data-stu-id="b6c12-233">Filter and Function.</span></span>
<span data-ttu-id="b6c12-234">O PowerShell funciona na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="b6c12-234">The PowerShell functions in the remote session.</span></span>
- <span data-ttu-id="b6c12-235">Script.</span><span class="sxs-lookup"><span data-stu-id="b6c12-235">Script.</span></span>
<span data-ttu-id="b6c12-236">Os blocos de script na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="b6c12-236">The script blocks in the remote session.</span></span>

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

### <span data-ttu-id="b6c12-237">-DisableNameChecking</span><span class="sxs-lookup"><span data-stu-id="b6c12-237">-DisableNameChecking</span></span>

<span data-ttu-id="b6c12-238">Indica que esse cmdlet suprime a mensagem que avisa quando você importa um cmdlet ou função cujo nome inclui um verbo não aprovado ou um caractere proibido.</span><span class="sxs-lookup"><span data-stu-id="b6c12-238">Indicates that this cmdlet suppresses the message that warns you when you import a cmdlet or function whose name includes an unapproved verb or a prohibited character.</span></span>

<span data-ttu-id="b6c12-239">Por padrão, quando um módulo que você importa exporta cmdlets ou funções que têm verbos não aprovados em seus nomes, o PowerShell exibe a seguinte mensagem de aviso:</span><span class="sxs-lookup"><span data-stu-id="b6c12-239">By default, when a module that you import exports cmdlets or functions that have unapproved verbs in their names, the PowerShell displays the following warning message:</span></span>

<span data-ttu-id="b6c12-240">"Aviso: alguns nomes de comando importados incluem verbos não aprovados que podem torná-los menos detectáveis.</span><span class="sxs-lookup"><span data-stu-id="b6c12-240">"WARNING: Some imported command names include unapproved verbs which might make them less discoverable.</span></span>
<span data-ttu-id="b6c12-241">Use o parâmetro Verbose para obter mais detalhes ou digite Get-Verb para ver a lista de verbos aprovados."</span><span class="sxs-lookup"><span data-stu-id="b6c12-241">Use the Verbose parameter for more detail or type Get-Verb to see the list of approved verbs."</span></span>

<span data-ttu-id="b6c12-242">A mensagem é apenas um aviso.</span><span class="sxs-lookup"><span data-stu-id="b6c12-242">This message is only a warning.</span></span>
<span data-ttu-id="b6c12-243">O módulo completo ainda é importado, incluindo os comandos não autorizados.</span><span class="sxs-lookup"><span data-stu-id="b6c12-243">The complete module is still imported, including the non-conforming commands.</span></span>
<span data-ttu-id="b6c12-244">Embora a mensagem seja exibida para usuários do módulo, o problema de nomenclatura deve ser corrigido pelo autor do módulo.</span><span class="sxs-lookup"><span data-stu-id="b6c12-244">Although the message is displayed to module users, the naming problem should be fixed by the module author.</span></span>

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

### <span data-ttu-id="b6c12-245">-FormatTypeName</span><span class="sxs-lookup"><span data-stu-id="b6c12-245">-FormatTypeName</span></span>

<span data-ttu-id="b6c12-246">Especifica instruções de formatação para os tipos de estrutura de Microsoft .NET especificados.</span><span class="sxs-lookup"><span data-stu-id="b6c12-246">Specifies formatting instructions for the specified Microsoft .NET Framework types.</span></span>
<span data-ttu-id="b6c12-247">Insira os nomes de tipo.</span><span class="sxs-lookup"><span data-stu-id="b6c12-247">Enter the type names.</span></span>
<span data-ttu-id="b6c12-248">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="b6c12-248">Wildcards are permitted.</span></span>

<span data-ttu-id="b6c12-249">O valor desse parâmetro deve ser o nome de um tipo que é retornado por um comando Get-FormatData na sessão da qual os comandos estão sendo importados.</span><span class="sxs-lookup"><span data-stu-id="b6c12-249">The value of this parameter must be the name of a type that is returned by a Get-FormatData command in the session from which the commands are being imported.</span></span>
<span data-ttu-id="b6c12-250">Para obter todos os dados de formatação na sessão remota, digite \*.</span><span class="sxs-lookup"><span data-stu-id="b6c12-250">To get all of the formatting data in the remote session, type \*.</span></span>

<span data-ttu-id="b6c12-251">Se o comando não incluir o parâmetro *CommandName* ou *FormatTypeName* , o **Import-PSSession** importará instruções de formatação para todos os tipos de .NET Framework retornados por um comando **Get-FormatData** na sessão remota.</span><span class="sxs-lookup"><span data-stu-id="b6c12-251">If the command does not include either the *CommandName* or *FormatTypeName* parameter, **Import-PSSession** imports formatting instructions for all .NET Framework types returned by a **Get-FormatData** command in the remote session.</span></span>

<span data-ttu-id="b6c12-252">Se você usar o parâmetro *FormatTypeName* , nenhum comando será importado, a menos que você use o parâmetro *CommandName* .</span><span class="sxs-lookup"><span data-stu-id="b6c12-252">If you use the *FormatTypeName* parameter, no commands are imported unless you use the *CommandName* parameter.</span></span>

<span data-ttu-id="b6c12-253">Da mesma forma, se você usar o parâmetro *CommandName* , os arquivos de formatação para os comandos não serão importados a menos que você use o parâmetro *FormatTypeName* .</span><span class="sxs-lookup"><span data-stu-id="b6c12-253">Similarly, if you use the *CommandName* parameter, the formatting files for the commands are not imported unless you use the *FormatTypeName* parameter.</span></span>

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

### <span data-ttu-id="b6c12-254">-FullyQualifiedModule</span><span class="sxs-lookup"><span data-stu-id="b6c12-254">-FullyQualifiedModule</span></span>

<span data-ttu-id="b6c12-255">Especifica os módulos com nomes que são especificados na forma de objetos **ModuleSpecification** (descritos na seção comentários do [Construtor ModuleSpecification (Hashtable)](https://msdn.microsoft.com/library/jj136290) na biblioteca MSDN).</span><span class="sxs-lookup"><span data-stu-id="b6c12-255">Specifies modules with names that are specified in the form of **ModuleSpecification** objects (described in the Remarks section of [ModuleSpecification Constructor (Hashtable)](https://msdn.microsoft.com/library/jj136290) in the MSDN library).</span></span>
<span data-ttu-id="b6c12-256">Por exemplo, o parâmetro *FullyQualifiedModule* aceita um nome de módulo que é especificado no formato @ {ModuleName = "ModuleName"; ModuleVersion = "version_number"} ou @ {ModuleName = "ModuleName"; ModuleVersion = "version_number"; GUID = "GUID"}.</span><span class="sxs-lookup"><span data-stu-id="b6c12-256">For example, the *FullyQualifiedModule* parameter accepts a module name that is specified in the format @{ModuleName = "modulename"; ModuleVersion = "version_number"} or @{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}.</span></span>
<span data-ttu-id="b6c12-257">**ModuleName** e **ModuleVersion** são obrigatórios, mas **Guid** é opcional.</span><span class="sxs-lookup"><span data-stu-id="b6c12-257">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span>

<span data-ttu-id="b6c12-258">Você não pode especificar o parâmetro *FullyQualifiedModule* no mesmo comando que um parâmetro de *módulo* ; os dois parâmetros são mutuamente exclusivos.</span><span class="sxs-lookup"><span data-stu-id="b6c12-258">You cannot specify the *FullyQualifiedModule* parameter in the same command as a *Module* parameter; the two parameters are mutually exclusive.</span></span>

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

### <span data-ttu-id="b6c12-259">-Módulo</span><span class="sxs-lookup"><span data-stu-id="b6c12-259">-Module</span></span>

<span data-ttu-id="b6c12-260">Especifica e a matriz de comandos nos módulos e snap-ins do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6c12-260">Specifies and array of commands in the PowerShell snap-ins and modules.</span></span>
<span data-ttu-id="b6c12-261">Digite os nomes de módulos e snap-ins.</span><span class="sxs-lookup"><span data-stu-id="b6c12-261">Enter the snap-in and module names.</span></span>
<span data-ttu-id="b6c12-262">Caracteres curinga não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="b6c12-262">Wildcards are not permitted.</span></span>

<span data-ttu-id="b6c12-263">**Import-PSSession** não pode importar provedores de um snap-in.</span><span class="sxs-lookup"><span data-stu-id="b6c12-263">**Import-PSSession** cannot import providers from a snap-in.</span></span>

<span data-ttu-id="b6c12-264">Para obter mais informações, consulte about_PSSnapins e [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="b6c12-264">For more information, see about_PSSnapins and [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span></span>

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

### <span data-ttu-id="b6c12-265">-Prefixo</span><span class="sxs-lookup"><span data-stu-id="b6c12-265">-Prefix</span></span>

<span data-ttu-id="b6c12-266">Especifica um prefixo para os substantivos nos nomes dos comandos importados.</span><span class="sxs-lookup"><span data-stu-id="b6c12-266">Specifies a prefix to the nouns in the names of imported commands.</span></span>

<span data-ttu-id="b6c12-267">Use este parâmetro para evitar conflitos de nome que podem ocorrer quando diferentes membros da sessão têm o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="b6c12-267">Use this parameter to avoid name conflicts that might occur when different commands in the session have the same name.</span></span>

<span data-ttu-id="b6c12-268">Por exemplo, se você especificar o prefixo Remote e, em seguida, importar um cmdlet Get-Date, o cmdlet será conhecido na sessão como Get-RemoteDate, e não será confundido com o cmdlet **Get-Date** original.</span><span class="sxs-lookup"><span data-stu-id="b6c12-268">For instance, if you specify the prefix Remote and then import a Get-Date cmdlet, the cmdlet is known in the session as Get-RemoteDate, and it is not confused with the original **Get-Date** cmdlet.</span></span>

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

### <span data-ttu-id="b6c12-269">-Sessão</span><span class="sxs-lookup"><span data-stu-id="b6c12-269">-Session</span></span>

<span data-ttu-id="b6c12-270">Especifica a **PSSession** da qual os cmdlets são importados.</span><span class="sxs-lookup"><span data-stu-id="b6c12-270">Specifies the **PSSession** from which the cmdlets are imported.</span></span>
<span data-ttu-id="b6c12-271">Insira uma variável que contém um objeto de sessão ou um comando que obtém um objeto de sessão, como um New-PSSession ou Get-PSSession comando.</span><span class="sxs-lookup"><span data-stu-id="b6c12-271">Enter a variable that contains a session object or a command that gets a session object, such as a New-PSSession or Get-PSSession command.</span></span>
<span data-ttu-id="b6c12-272">Você pode especificar somente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="b6c12-272">You can specify only one session.</span></span>
<span data-ttu-id="b6c12-273">Este parâmetro é necessário.</span><span class="sxs-lookup"><span data-stu-id="b6c12-273">This parameter is required.</span></span>

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

### <span data-ttu-id="b6c12-274">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b6c12-274">CommonParameters</span></span>

<span data-ttu-id="b6c12-275">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b6c12-275">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b6c12-276">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b6c12-276">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b6c12-277">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b6c12-277">INPUTS</span></span>

### <span data-ttu-id="b6c12-278">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b6c12-278">None</span></span>

<span data-ttu-id="b6c12-279">Não é possível transferir objetos para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b6c12-279">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="b6c12-280">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b6c12-280">OUTPUTS</span></span>

### <span data-ttu-id="b6c12-281">System. Management. Automation. PSModuleInfo</span><span class="sxs-lookup"><span data-stu-id="b6c12-281">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="b6c12-282">**Import-PSSession** retorna o mesmo objeto de módulo que New-Module e Get-Module os cmdlets retornam.</span><span class="sxs-lookup"><span data-stu-id="b6c12-282">**Import-PSSession** returns the same module object that New-Module and Get-Module cmdlets return.</span></span>
<span data-ttu-id="b6c12-283">No entanto, o módulo importado é temporário e existe somente na sessão atual.</span><span class="sxs-lookup"><span data-stu-id="b6c12-283">However, the imported module is temporary and exists only in the current session.</span></span>
<span data-ttu-id="b6c12-284">Para criar um módulo permanente no disco, use o cmdlet Export-PSSession.</span><span class="sxs-lookup"><span data-stu-id="b6c12-284">To create a permanent module on disk, use the Export-PSSession cmdlet.</span></span>

## <span data-ttu-id="b6c12-285">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b6c12-285">NOTES</span></span>

* <span data-ttu-id="b6c12-286">**Import-PSSession** depende da infraestrutura de comunicação remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6c12-286">**Import-PSSession** relies on the PowerShell remoting infrastructure.</span></span> <span data-ttu-id="b6c12-287">Para usar esse cmdlet, o computador deve ser configurado para comunicação remota do WS-Management.</span><span class="sxs-lookup"><span data-stu-id="b6c12-287">To use this cmdlet, the computer must be configured for WS-Management remoting.</span></span> <span data-ttu-id="b6c12-288">Para obter mais informações, consulte about_Remote e about_Remote_Requirements.</span><span class="sxs-lookup"><span data-stu-id="b6c12-288">For more information, see about_Remote and about_Remote_Requirements.</span></span>
* <span data-ttu-id="b6c12-289">**Import-PSSession** não importa variáveis ou provedores do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6c12-289">**Import-PSSession** does not import variables or PowerShell providers.</span></span>
* <span data-ttu-id="b6c12-290">Quando você importa comandos que têm os mesmos nomes que comandos na sessão atual, os comandos importados podem ocultar aliases, funções e cmdlets na sessão e eles podem substituir funções e variáveis na sessão.</span><span class="sxs-lookup"><span data-stu-id="b6c12-290">When you import commands that have the same names as commands in the current session, the imported commands can hide aliases, functions, and cmdlets in the session and they can replace functions and variables in the session.</span></span> <span data-ttu-id="b6c12-291">Para evitar conflitos de nome, use o parâmetro *Prefix* .</span><span class="sxs-lookup"><span data-stu-id="b6c12-291">To prevent name conflicts, use the *Prefix* parameter.</span></span> <span data-ttu-id="b6c12-292">Para obter mais informações, consulte about_Command_Precedence.</span><span class="sxs-lookup"><span data-stu-id="b6c12-292">For more information, see about_Command_Precedence.</span></span>
* <span data-ttu-id="b6c12-293">**Import-PSSession** converte todos os comandos em funções antes de importá-los.</span><span class="sxs-lookup"><span data-stu-id="b6c12-293">**Import-PSSession** converts all commands into functions before it imports them.</span></span> <span data-ttu-id="b6c12-294">Como resultado, comandos importados possuem um comportamento um pouco diferente de quando mantém tipo de comando original.</span><span class="sxs-lookup"><span data-stu-id="b6c12-294">As a result, imported commands behave a bit differently than they would if they retained their original command type.</span></span> <span data-ttu-id="b6c12-295">Por exemplo, se você importar um cmdlet de uma PSSession e um cmdlet com o mesmo nome de um módulo ou snap-in, o cmdlet é importado da PSSession sempre será executado por padrão porque funções têm precedência sobre cmdlets.</span><span class="sxs-lookup"><span data-stu-id="b6c12-295">For example, if you import a cmdlet from a PSSession and then import a cmdlet with the same name from a module or snap-in, the cmdlet that is imported from the PSSession always runs by default because functions take precedence over cmdlets.</span></span> <span data-ttu-id="b6c12-296">Por outro lado, se você importar um alias para uma sessão com um alias com o mesmo nome, o alias original sempre é usado, pois aliases têm precedência sobre funções.</span><span class="sxs-lookup"><span data-stu-id="b6c12-296">Conversely, if you import an alias into a session that has an alias with the same name, the original alias is always used, because aliases take precedence over functions.</span></span> <span data-ttu-id="b6c12-297">Para obter mais informações, consulte about_Command_Precedence.</span><span class="sxs-lookup"><span data-stu-id="b6c12-297">For more information, see about_Command_Precedence.</span></span>
* <span data-ttu-id="b6c12-298">**Import-PSSession** usa o cmdlet Write-Progress para exibir o progresso do comando.</span><span class="sxs-lookup"><span data-stu-id="b6c12-298">**Import-PSSession** uses the Write-Progress cmdlet to display the progress of the command.</span></span> <span data-ttu-id="b6c12-299">Você pode ver a barra de progresso enquanto o comando é executado.</span><span class="sxs-lookup"><span data-stu-id="b6c12-299">You might see the progress bar while the command is running.</span></span>
* <span data-ttu-id="b6c12-300">Para localizar os comandos a serem importados, o **Import-PSSession** usa o cmdlet Invoke-Command para executar um comando Get-Command na PSSession.</span><span class="sxs-lookup"><span data-stu-id="b6c12-300">To find the commands to import, **Import-PSSession** uses the Invoke-Command cmdlet to run a Get-Command command in the PSSession.</span></span> <span data-ttu-id="b6c12-301">Para obter dados de formatação para os comandos, ele usa o cmdlet Get-FormatData.</span><span class="sxs-lookup"><span data-stu-id="b6c12-301">To get formatting data for the commands, it uses the Get-FormatData cmdlet.</span></span> <span data-ttu-id="b6c12-302">Você poderá ver mensagens de erro desses cmdlets ao executar um comando **Import-PSSession** .</span><span class="sxs-lookup"><span data-stu-id="b6c12-302">You might see error messages from these cmdlets when you run an **Import-PSSession** command.</span></span> <span data-ttu-id="b6c12-303">Além disso, o **Import-PSSession** não pode importar comandos de uma PSSession que não inclua os cmdlets Get-Command, Get-FormatData, Select-Object e Get-Help.</span><span class="sxs-lookup"><span data-stu-id="b6c12-303">Also, **Import-PSSession** cannot import commands from a PSSession that does not include the Get-Command, Get-FormatData, Select-Object, and Get-Help cmdlets.</span></span>
* <span data-ttu-id="b6c12-304">Comandos importados têm as mesmas limitações que outros comandos remotos, inclusive a incapacidade de iniciar um programa com uma interface de usuário, como o Bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="b6c12-304">Imported commands have the same limitations as other remote commands, including the inability to start a program with a user interface, such as Notepad.</span></span>
* <span data-ttu-id="b6c12-305">Como os perfis do PowerShell não são executados em PSSessions, os comandos que um perfil adiciona a uma sessão não estão disponíveis para **Import-PSSession** .</span><span class="sxs-lookup"><span data-stu-id="b6c12-305">Because PowerShell profiles are not run in PSSessions, the commands that a profile adds to a session are not available to **Import-PSSession** .</span></span> <span data-ttu-id="b6c12-306">Para importar os comandos de um perfil, use um comando Invoke-Command para executar o perfil na PSSession manualmente antes de importar os comandos.</span><span class="sxs-lookup"><span data-stu-id="b6c12-306">To import commands from a profile, use an Invoke-Command command to run the profile in the PSSession manually before importing commands.</span></span>
* <span data-ttu-id="b6c12-307">O módulo temporário criado pelo **Import-PSSession** pode incluir um arquivo de formatação, mesmo se o comando não importar dados de formatação.</span><span class="sxs-lookup"><span data-stu-id="b6c12-307">The temporary module that **Import-PSSession** creates might include a formatting file, even if the command does not import formatting data.</span></span> <span data-ttu-id="b6c12-308">Se o comando não importar dados de formatação, quaisquer arquivos de formatação criados não conterão dados de formatação.</span><span class="sxs-lookup"><span data-stu-id="b6c12-308">If the command does not import formatting data, any formatting files that are created will not contain formatting data.</span></span>
* <span data-ttu-id="b6c12-309">Para usar o **Import-PSSession** , a política de execução na sessão atual não pode ser Restrict ou AllSigned, porque o módulo temporário criado pelo **Import-PSSession** contém arquivos de script não assinados que são proibidos por essas políticas.</span><span class="sxs-lookup"><span data-stu-id="b6c12-309">To use **Import-PSSession** , the execution policy in the current session cannot be Restricted or AllSigned, because the temporary module that **Import-PSSession** creates contains unsigned script files that are prohibited by these policies.</span></span> <span data-ttu-id="b6c12-310">Para usar **Import-PSSession** sem alterar a política de execução para o computador local, use o parâmetro *Scope* de Set-ExecutionPolicy para definir uma política de execução menos restritiva para um único processo.</span><span class="sxs-lookup"><span data-stu-id="b6c12-310">To use **Import-PSSession** without changing the execution policy for the local computer, use the *Scope* parameter of Set-ExecutionPolicy to set a less restrictive execution policy for a single process.</span></span>
* <span data-ttu-id="b6c12-311">No Windows PowerShell 2.0, os tópicos de ajuda para comandos importados de outra sessão não incluem o prefixo que você atribui usando o parâmetro *Prefix* .</span><span class="sxs-lookup"><span data-stu-id="b6c12-311">In Windows PowerShell 2.0, help topics for commands that are imported from another session do not include the prefix that you assign by using the *Prefix* parameter.</span></span> <span data-ttu-id="b6c12-312">Para obter ajuda sobre um comando importado no Windows PowerShell 2.0, use o nome original do comando (sem prefixo).</span><span class="sxs-lookup"><span data-stu-id="b6c12-312">To get help for an imported command in Windows PowerShell 2.0, use the original (non-prefixed) command name.</span></span>

## <span data-ttu-id="b6c12-313">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b6c12-313">RELATED LINKS</span></span>

[<span data-ttu-id="b6c12-314">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="b6c12-314">Export-PSSession</span></span>](Export-PSSession.md)
