---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 09/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/foreach-object?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ForEach-Object
ms.openlocfilehash: 8257f1fba2d4367e61121d4876a51197f710da41
ms.sourcegitcommit: e0f9fe6335be1e0f94bedaa0e8baec2acaeaa076
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "93195305"
---
# <span data-ttu-id="6baf4-103">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="6baf4-103">ForEach-Object</span></span>

## <span data-ttu-id="6baf4-104">Sinopse</span><span class="sxs-lookup"><span data-stu-id="6baf4-104">Synopsis</span></span>
<span data-ttu-id="6baf4-105">Executa uma operação em cada item de uma coleção de objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="6baf4-105">Performs an operation against each item in a collection of input objects.</span></span>

## <span data-ttu-id="6baf4-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="6baf4-106">Syntax</span></span>

### <span data-ttu-id="6baf4-107">ScriptBlockset (padrão)</span><span class="sxs-lookup"><span data-stu-id="6baf4-107">ScriptBlockSet (Default)</span></span>

```
ForEach-Object [-InputObject <PSObject>] [-Begin <ScriptBlock>] [-Process] <ScriptBlock[]>
 [-End <ScriptBlock>] [-RemainingScripts <ScriptBlock[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="6baf4-108">PropertyAndMethodSet</span><span class="sxs-lookup"><span data-stu-id="6baf4-108">PropertyAndMethodSet</span></span>

```
ForEach-Object [-InputObject <PSObject>] [-MemberName] <String> [-ArgumentList <Object[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="6baf4-109">ParallelParameterSet</span><span class="sxs-lookup"><span data-stu-id="6baf4-109">ParallelParameterSet</span></span>

```
ForEach-Object [-InputObject <PSObject>] -Parallel <ScriptBlock> [-ThrottleLimit <Int32>]
 [-TimeoutSeconds <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="6baf4-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="6baf4-110">Description</span></span>

<span data-ttu-id="6baf4-111">O `ForEach-Object` cmdlet executa uma operação em cada item em uma coleção de objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="6baf4-111">The `ForEach-Object` cmdlet performs an operation on each item in a collection of input objects.</span></span> <span data-ttu-id="6baf4-112">Os objetos de entrada podem ser canalizados para o cmdlet ou especificados usando o parâmetro **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="6baf4-112">The input objects can be piped to the cmdlet or specified by using the **InputObject** parameter.</span></span>

<span data-ttu-id="6baf4-113">A partir do Windows PowerShell 3,0, há duas maneiras diferentes de construir um `ForEach-Object` comando.</span><span class="sxs-lookup"><span data-stu-id="6baf4-113">Starting in Windows PowerShell 3.0, there are two different ways to construct a `ForEach-Object` command.</span></span>

- <span data-ttu-id="6baf4-114">**Bloco de script** .</span><span class="sxs-lookup"><span data-stu-id="6baf4-114">**Script block** .</span></span> <span data-ttu-id="6baf4-115">Você pode usar um bloco de script para especificar a operação.</span><span class="sxs-lookup"><span data-stu-id="6baf4-115">You can use a script block to specify the operation.</span></span> <span data-ttu-id="6baf4-116">No bloco de script, use a `$_` variável para representar o objeto atual.</span><span class="sxs-lookup"><span data-stu-id="6baf4-116">Within the script block, use the `$_` variable to represent the current object.</span></span> <span data-ttu-id="6baf4-117">O bloco de script é o valor do parâmetro **Process** .</span><span class="sxs-lookup"><span data-stu-id="6baf4-117">The script block is the value of the **Process** parameter.</span></span> <span data-ttu-id="6baf4-118">O bloco de script pode conter qualquer script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6baf4-118">The script block can contain any PowerShell script.</span></span>

  <span data-ttu-id="6baf4-119">Por exemplo, o comando a seguir obtém o valor da propriedade **ProcessName** de cada processo no computador.</span><span class="sxs-lookup"><span data-stu-id="6baf4-119">For example, the following command gets the value of the **ProcessName** property of each process on the computer.</span></span>

  `Get-Process | ForEach-Object {$_.ProcessName}`

  <span data-ttu-id="6baf4-120">`ForEach-Object` dá suporte `begin` aos `process` blocos, e `end` conforme descrito em [about_Functions](about/about_functions.md#piping-objects-to-functions).</span><span class="sxs-lookup"><span data-stu-id="6baf4-120">`ForEach-Object` supports the `begin`, `process`, and `end` blocks as described in [about_functions](about/about_functions.md#piping-objects-to-functions).</span></span>

  > [!NOTE]
  > <span data-ttu-id="6baf4-121">Os blocos de script são executados no escopo do chamador.</span><span class="sxs-lookup"><span data-stu-id="6baf4-121">The script blocks run in the caller's scope.</span></span> <span data-ttu-id="6baf4-122">Portanto, os blocos têm acesso a variáveis nesse escopo e podem criar novas variáveis que persistem nesse escopo após a conclusão do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6baf4-122">Therefore the blocks have access to variables in that scope and can create new variables that persist in that scope after the cmdlet completes.</span></span>

- <span data-ttu-id="6baf4-123">**Instrução de operação** .</span><span class="sxs-lookup"><span data-stu-id="6baf4-123">**Operation statement** .</span></span> <span data-ttu-id="6baf4-124">Você também pode escrever uma instrução de operação, que é muito mais parecida com a linguagem natural.</span><span class="sxs-lookup"><span data-stu-id="6baf4-124">You can also write an operation statement, which is much more like natural language.</span></span> <span data-ttu-id="6baf4-125">Você pode usar a instrução de operação para especificar um valor de propriedade ou chamar um método.</span><span class="sxs-lookup"><span data-stu-id="6baf4-125">You can use the operation statement to specify a property value or call a method.</span></span> <span data-ttu-id="6baf4-126">Instruções de operação foram introduzidas no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="6baf4-126">Operation statements were introduced in Windows PowerShell 3.0.</span></span>

  <span data-ttu-id="6baf4-127">Por exemplo, o comando a seguir também obtém o valor da propriedade **ProcessName** de cada processo no computador.</span><span class="sxs-lookup"><span data-stu-id="6baf4-127">For example, the following command also gets the value of the **ProcessName** property of each process on the computer.</span></span>

  `Get-Process | ForEach-Object ProcessName`

- <span data-ttu-id="6baf4-128">**Bloco de script em execução paralela** .</span><span class="sxs-lookup"><span data-stu-id="6baf4-128">**Parallel running script block** .</span></span> <span data-ttu-id="6baf4-129">A partir do PowerShell 7,0, um terceiro conjunto de parâmetros está disponível e executa cada bloco de script em paralelo.</span><span class="sxs-lookup"><span data-stu-id="6baf4-129">Beginning with PowerShell 7.0, a third parameter set is available that runs each script block in parallel.</span></span> <span data-ttu-id="6baf4-130">O parâmetro **ThrottleLimit** limita o número de scripts paralelos em execução por vez.</span><span class="sxs-lookup"><span data-stu-id="6baf4-130">The **ThrottleLimit** parameter limits the number of parallel scripts running at a time.</span></span> <span data-ttu-id="6baf4-131">Como antes, use a `$_` variável para representar o objeto de entrada atual no bloco de script.</span><span class="sxs-lookup"><span data-stu-id="6baf4-131">As before, use the `$_` variable to represent the current input object in the script block.</span></span> <span data-ttu-id="6baf4-132">Use a `$using:` palavra-chave para passar referências de variáveis para o script em execução.</span><span class="sxs-lookup"><span data-stu-id="6baf4-132">Use the `$using:` keyword to pass variable references to the running script.</span></span>

  <span data-ttu-id="6baf4-133">No PowerShell 7, um novo runspace é criado para cada iteração de loop a fim de garantir o isolamento máximo.</span><span class="sxs-lookup"><span data-stu-id="6baf4-133">In PowerShell 7, a new runspace is created for each loop iteration to ensure maximum isolation.</span></span>
  <span data-ttu-id="6baf4-134">Isso pode ser um grande desempenho e um maior impacto de recursos se o trabalho que você está fazendo for pequeno em comparação com a criação de novos Runspaces ou se houver muitas iterações executando um trabalho significativo.</span><span class="sxs-lookup"><span data-stu-id="6baf4-134">This can be a large performance and resource hit if the work you are doing is small compared to creating new runspaces or if there are a lot of iterations performing significant work.</span></span>

  <span data-ttu-id="6baf4-135">Por padrão, os scriptblocks paralelos usam o diretório de trabalho atual do chamador que iniciou as tarefas paralelas.</span><span class="sxs-lookup"><span data-stu-id="6baf4-135">By default, the parallel scriptblocks use the current working directory of the caller that started the parallel tasks.</span></span>

  <span data-ttu-id="6baf4-136">Os erros de não finalização são gravados no fluxo de erros do cmdlet conforme eles ocorrem em scriptblocks em execução paralela.</span><span class="sxs-lookup"><span data-stu-id="6baf4-136">Non-terminating errors are written to the cmdlet error stream as they occur in parallel running scriptblocks.</span></span> <span data-ttu-id="6baf4-137">Como a ordem de execução do scriptblock Parallel não pode ser determinada, a ordem na qual os erros aparecem no fluxo de erro é aleatória.</span><span class="sxs-lookup"><span data-stu-id="6baf4-137">Because parallel scriptblock execution order cannot be determined, the order in which errors appear in the error stream is random.</span></span> <span data-ttu-id="6baf4-138">Da mesma forma, as mensagens gravadas em outros fluxos de dados, como aviso, detalhado ou informações, são gravadas nesses fluxos de dados em uma ordem indeterminada.</span><span class="sxs-lookup"><span data-stu-id="6baf4-138">Likewise, messages written to other data streams, like warning, verbose, or information are written to those data streams in an indeterminate order.</span></span>

  <span data-ttu-id="6baf4-139">Erros de encerramento, como exceções, encerram a instância paralela individual dos scriptblocks em que ocorrem.</span><span class="sxs-lookup"><span data-stu-id="6baf4-139">Terminating errors, such as exceptions, terminate the individual parallel instance of the scriptblocks in which they occur.</span></span> <span data-ttu-id="6baf4-140">Um erro de encerramento em um scriptblock pode não causar o encerramento do `Foreach-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6baf4-140">A terminating error in one scriptblocks may not cause the termination of the `Foreach-Object` cmdlet.</span></span> <span data-ttu-id="6baf4-141">Os outros scriptblocks, em execução em paralelo, continuam a ser executados, a menos que também encontrem um erro de encerramento.</span><span class="sxs-lookup"><span data-stu-id="6baf4-141">The other scriptblocks, running in parallel, continue to run unless they also encounter a terminating error.</span></span> <span data-ttu-id="6baf4-142">O erro de encerramento é gravado no fluxo de dados de erro como um **ErrorRecord** com um **FullyQualifiedErrorId** de `PSTaskException` .</span><span class="sxs-lookup"><span data-stu-id="6baf4-142">The terminating error is written to the error data stream as an **ErrorRecord** with a **FullyQualifiedErrorId** of `PSTaskException`.</span></span>
  <span data-ttu-id="6baf4-143">Os erros de encerramento podem ser convertidos em erros de não encerramento usando blocos try/catch ou Trap do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6baf4-143">Terminating errors can be converted to non-terminating errors using PowerShell try/catch or trap blocks.</span></span>

## <span data-ttu-id="6baf4-144">Exemplos</span><span class="sxs-lookup"><span data-stu-id="6baf4-144">Examples</span></span>

### <span data-ttu-id="6baf4-145">Exemplo 1: dividir inteiros em uma matriz</span><span class="sxs-lookup"><span data-stu-id="6baf4-145">Example 1: Divide integers in an array</span></span>

<span data-ttu-id="6baf4-146">Este exemplo usa uma matriz de três inteiros e divide cada um deles por 1024.</span><span class="sxs-lookup"><span data-stu-id="6baf4-146">This example takes an array of three integers and divides each one of them by 1024.</span></span>

```powershell
30000, 56798, 12432 | ForEach-Object -Process {$_/1024}
```

```Output
29.296875
55.466796875
12.140625
```

### <span data-ttu-id="6baf4-147">Exemplo 2: obter o comprimento de todos os arquivos em um diretório</span><span class="sxs-lookup"><span data-stu-id="6baf4-147">Example 2: Get the length of all the files in a directory</span></span>

<span data-ttu-id="6baf4-148">Este exemplo processa os arquivos e diretórios no diretório de instalação do PowerShell `$PSHOME` .</span><span class="sxs-lookup"><span data-stu-id="6baf4-148">This example processes the files and directories in the PowerShell installation directory `$PSHOME`.</span></span>

```powershell
Get-ChildItem $PSHOME |
  ForEach-Object -Process {if (!$_.PSIsContainer) {$_.Name; $_.Length / 1024; " " }}
```

<span data-ttu-id="6baf4-149">Se o objeto não for um diretório, o bloco de script obterá o nome do arquivo, dividirá o valor de sua propriedade **Length** por 1024 e adicionará um espaço ("") para separá-lo da próxima entrada.</span><span class="sxs-lookup"><span data-stu-id="6baf4-149">If the object is not a directory, the script block gets the name of the file, divides the value of its **Length** property by 1024, and adds a space (" ") to separate it from the next entry.</span></span> <span data-ttu-id="6baf4-150">O cmdlet usa a propriedade **PSISContainer** para determinar se um objeto é um diretório.</span><span class="sxs-lookup"><span data-stu-id="6baf4-150">The cmdlet uses the **PSISContainer** property to determine whether an object is a directory.</span></span>

### <span data-ttu-id="6baf4-151">Exemplo 3: operar nos eventos do sistema mais recentes</span><span class="sxs-lookup"><span data-stu-id="6baf4-151">Example 3: Operate on the most recent System events</span></span>

<span data-ttu-id="6baf4-152">Este exemplo grava os 1000 eventos mais recentes do log de eventos do sistema em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="6baf4-152">This example writes the 1000 most recent events from the System event log to a text file.</span></span> <span data-ttu-id="6baf4-153">A hora atual é exibida antes e depois do processamento dos eventos.</span><span class="sxs-lookup"><span data-stu-id="6baf4-153">The current time is displayed before and after processing the events.</span></span>

```powershell
$Events = Get-EventLog -LogName System -Newest 1000
$events | ForEach-Object -Begin {Get-Date} -Process {Out-File -FilePath Events.txt -Append -InputObject $_.Message} -End {Get-Date}
```

<span data-ttu-id="6baf4-154">`Get-EventLog` Obtém os 1000 eventos mais recentes do log de eventos do sistema e os armazena na `$Events` variável.</span><span class="sxs-lookup"><span data-stu-id="6baf4-154">`Get-EventLog` gets the 1000 most recent events from the System event log and stores them in the `$Events` variable.</span></span> <span data-ttu-id="6baf4-155">`$Events` é então canalizado para o `ForEach-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6baf4-155">`$Events` is then piped to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="6baf4-156">O parâmetro **Begin** exibe a data e hora atuais.</span><span class="sxs-lookup"><span data-stu-id="6baf4-156">The **Begin** parameter displays the current date and time.</span></span> <span data-ttu-id="6baf4-157">Em seguida, o parâmetro **process** usa o `Out-File` cmdlet para criar um arquivo de texto chamado events.txt e armazena a propriedade Message de cada um dos eventos nesse arquivo.</span><span class="sxs-lookup"><span data-stu-id="6baf4-157">Next, the **Process** parameter uses the `Out-File` cmdlet to create a text file that is named events.txt and stores the message property of each of the events in that file.</span></span> <span data-ttu-id="6baf4-158">Por fim, o parâmetro **End** é usado para exibir a data e hora após todo o processamento ter sido concluído.</span><span class="sxs-lookup"><span data-stu-id="6baf4-158">Last, the **End** parameter is used to display the date and time after all of the processing has completed.</span></span>

### <span data-ttu-id="6baf4-159">Exemplo 4: alterar o valor de uma chave do registro</span><span class="sxs-lookup"><span data-stu-id="6baf4-159">Example 4: Change the value of a Registry key</span></span>

<span data-ttu-id="6baf4-160">Este exemplo altera o valor da entrada do registro **RemotePath** em todas as subchaves sob a `HKCU:\Network` chave para texto em maiúsculas.</span><span class="sxs-lookup"><span data-stu-id="6baf4-160">This example changes the value of the **RemotePath** registry entry in all of the subkeys under the `HKCU:\Network` key to uppercase text.</span></span>

```powershell
Get-ItemProperty -Path HKCU:\Network\* |
  ForEach-Object {Set-ItemProperty -Path $_.PSPath -Name RemotePath -Value $_.RemotePath.ToUpper();}
```

<span data-ttu-id="6baf4-161">Você pode usar esse formato para alterar a forma ou o conteúdo de um valor de entrada de registro.</span><span class="sxs-lookup"><span data-stu-id="6baf4-161">You can use this format to change the form or content of a registry entry value.</span></span>

<span data-ttu-id="6baf4-162">Cada subchave na chave de **rede** representa uma unidade de rede mapeada que se reconecta no logon.</span><span class="sxs-lookup"><span data-stu-id="6baf4-162">Each subkey in the **Network** key represents a mapped network drive that reconnects at sign on.</span></span> <span data-ttu-id="6baf4-163">A entrada **RemotePath** contém o caminho UNC da unidade conectada.</span><span class="sxs-lookup"><span data-stu-id="6baf4-163">The **RemotePath** entry contains the UNC path of the connected drive.</span></span> <span data-ttu-id="6baf4-164">Por exemplo, se você mapear a unidade E: para `\\Server\Share` , uma subchave **e** será criada em `HKCU:\Network` com o valor do registro **RemotePath** definido como `\\Server\Share` .</span><span class="sxs-lookup"><span data-stu-id="6baf4-164">For example, if you map the E: drive to `\\Server\Share`, an **E** subkey is created in `HKCU:\Network` with the **RemotePath** registry value set to `\\Server\Share`.</span></span>

<span data-ttu-id="6baf4-165">O comando usa o `Get-ItemProperty` cmdlet para obter todas as subchaves da chave de **rede** e o `Set-ItemProperty` cmdlet para alterar o valor da entrada do registro **RemotePath** em cada chave.</span><span class="sxs-lookup"><span data-stu-id="6baf4-165">The command uses the `Get-ItemProperty` cmdlet to get all of the subkeys of the **Network** key and the `Set-ItemProperty` cmdlet to change the value of the **RemotePath** registry entry in each key.</span></span>
<span data-ttu-id="6baf4-166">No `Set-ItemProperty` comando, o caminho é o valor da propriedade **PSPath** da chave do registro.</span><span class="sxs-lookup"><span data-stu-id="6baf4-166">In the `Set-ItemProperty` command, the path is the value of the **PSPath** property of the registry key.</span></span> <span data-ttu-id="6baf4-167">Essa é uma propriedade do objeto Microsoft .NET Framework que representa a chave do registro, não uma entrada do registro.</span><span class="sxs-lookup"><span data-stu-id="6baf4-167">This is a property of the Microsoft .NET Framework object that represents the registry key, not a registry entry.</span></span> <span data-ttu-id="6baf4-168">O comando usa o método **ToUpper ()** do valor **RemotePath** , que é uma cadeia de caracteres (REG_SZ).</span><span class="sxs-lookup"><span data-stu-id="6baf4-168">The command uses the **ToUpper()** method of the **RemotePath** value, which is a string (REG_SZ).</span></span>

<span data-ttu-id="6baf4-169">Como o `Set-ItemProperty` está alterando a propriedade de cada chave, o `ForEach-Object` cmdlet é necessário para acessar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="6baf4-169">Because `Set-ItemProperty` is changing the property of each key, the `ForEach-Object` cmdlet is required to access the property.</span></span>

### <span data-ttu-id="6baf4-170">Exemplo 5: usar a $Null variável automática</span><span class="sxs-lookup"><span data-stu-id="6baf4-170">Example 5: Use the $Null automatic variable</span></span>

<span data-ttu-id="6baf4-171">Este exemplo mostra o efeito de canalizar a `$Null` variável automática para o `ForEach-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6baf4-171">This example shows the effect of piping the `$Null` automatic variable to the `ForEach-Object` cmdlet.</span></span>

```powershell
1, 2, $null, 4 | ForEach-Object {"Hello"}
```

```Output
Hello
Hello
Hello
Hello
```

<span data-ttu-id="6baf4-172">Como o PowerShell trata nulo como um espaço reservado explícito, o `ForEach-Object` cmdlet gera um valor para `$Null` , assim como faz para outros objetos que você canaliza para ele.</span><span class="sxs-lookup"><span data-stu-id="6baf4-172">Because PowerShell treats null as an explicit placeholder, the `ForEach-Object` cmdlet generates a value for `$Null`, just as it does for other objects that you pipe to it.</span></span>

### <span data-ttu-id="6baf4-173">Exemplo 6: obter valores de propriedade</span><span class="sxs-lookup"><span data-stu-id="6baf4-173">Example 6: Get property values</span></span>

<span data-ttu-id="6baf4-174">Este exemplo obtém o valor da propriedade **path** de todos os módulos do PowerShell instalados usando o parâmetro **MemberName** do `ForEach-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6baf4-174">This example gets the value of the **Path** property of all installed PowerShell modules by using the **MemberName** parameter of the `ForEach-Object` cmdlet.</span></span>

```powershell
Get-Module -ListAvailable | ForEach-Object -MemberName Path
Get-Module -ListAvailable | Foreach Path
```

<span data-ttu-id="6baf4-175">O segundo comando é equivalente ao primeiro.</span><span class="sxs-lookup"><span data-stu-id="6baf4-175">The second command is equivalent to the first.</span></span> <span data-ttu-id="6baf4-176">Ele usa o `Foreach` alias do `ForEach-Object` cmdlet e omite o nome do parâmetro **MemberName** , que é opcional.</span><span class="sxs-lookup"><span data-stu-id="6baf4-176">It uses the `Foreach` alias of the `ForEach-Object` cmdlet and omits the name of the **MemberName** parameter, which is optional.</span></span>

<span data-ttu-id="6baf4-177">O `ForEach-Object` cmdlet é útil para obter valores de propriedade, pois Obtém o valor sem alterar o tipo, diferentemente dos cmdlets **Format** ou do `Select-Object` cmdlet, que alteram o tipo de valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="6baf4-177">The `ForEach-Object` cmdlet is useful for getting property values, because it gets the value without changing the type, unlike the **Format** cmdlets or the `Select-Object` cmdlet, which change the property value type.</span></span>

### <span data-ttu-id="6baf4-178">Exemplo 7: dividir nomes de módulo em nomes de componentes</span><span class="sxs-lookup"><span data-stu-id="6baf4-178">Example 7: Split module names into component names</span></span>

<span data-ttu-id="6baf4-179">Este exemplo mostra três maneiras de dividir dois nomes de módulo separados por ponto em seus nomes de componentes.</span><span class="sxs-lookup"><span data-stu-id="6baf4-179">This example shows three ways to split two dot-separated module names into their component names.</span></span>

```powershell
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | ForEach-Object {$_.Split(".")}
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | ForEach-Object -MemberName Split -ArgumentList "."
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | Foreach Split "."
```

```Output
Microsoft
PowerShell
Core
Microsoft
PowerShell
Host
```

<span data-ttu-id="6baf4-180">Os comandos chamam o método de cadeias de caracteres **Split** .</span><span class="sxs-lookup"><span data-stu-id="6baf4-180">The commands call the **Split** method of strings.</span></span> <span data-ttu-id="6baf4-181">Os três comandos usam uma sintaxe diferente, mas são equivalentes e intercambiáveis.</span><span class="sxs-lookup"><span data-stu-id="6baf4-181">The three commands use different syntax, but they are equivalent and interchangeable.</span></span>

<span data-ttu-id="6baf4-182">O primeiro comando usa a sintaxe tradicional, que inclui um bloco de script e o operador de objeto atual `$_` .</span><span class="sxs-lookup"><span data-stu-id="6baf4-182">The first command uses the traditional syntax, which includes a script block and the current object operator `$_`.</span></span> <span data-ttu-id="6baf4-183">Ele usa a sintaxe de ponto para especificar o método e parênteses para incluir o argumento delimitador.</span><span class="sxs-lookup"><span data-stu-id="6baf4-183">It uses the dot syntax to specify the method and parentheses to enclose the delimiter argument.</span></span>

<span data-ttu-id="6baf4-184">O segundo comando usa o parâmetro **MemberName** para especificar o método **Split** e o parâmetro **ArgumentName** para identificar o ponto (".") como o delimitador de divisão.</span><span class="sxs-lookup"><span data-stu-id="6baf4-184">The second command uses the **MemberName** parameter to specify the **Split** method and the **ArgumentName** parameter to identify the dot (".") as the split delimiter.</span></span>

<span data-ttu-id="6baf4-185">O terceiro comando usa o alias **foreach** do `ForEach-Object` cmdlet e omite os nomes dos parâmetros **MemberName** e **ArgumentList** , que são opcionais.</span><span class="sxs-lookup"><span data-stu-id="6baf4-185">The third command uses the **Foreach** alias of the `ForEach-Object` cmdlet and omits the names of the **MemberName** and **ArgumentList** parameters, which are optional.</span></span>

### <span data-ttu-id="6baf4-186">Exemplo 8: usando ForEach-Object com dois blocos de script</span><span class="sxs-lookup"><span data-stu-id="6baf4-186">Example 8: Using ForEach-Object with two script blocks</span></span>

<span data-ttu-id="6baf4-187">Neste exemplo, passamos dois blocos de script de posição.</span><span class="sxs-lookup"><span data-stu-id="6baf4-187">In this example, we pass two script blocks positionally.</span></span> <span data-ttu-id="6baf4-188">Todos os blocos de script são associados ao parâmetro de **processo** .</span><span class="sxs-lookup"><span data-stu-id="6baf4-188">All the script blocks bind to the **Process** parameter.</span></span> <span data-ttu-id="6baf4-189">No entanto, eles são tratados como se tivessem sido passados para os parâmetros **begin** e **process** .</span><span class="sxs-lookup"><span data-stu-id="6baf4-189">However, they are treated as if they had been passed to the **Begin** and **Process** parameters.</span></span>

```powershell
1..2 | ForEach-Object { 'begin' } { 'process' }
```

```Output
begin
process
process
```

### <span data-ttu-id="6baf4-190">Exemplo 9: usando ForEach-Object com mais de dois blocos de script</span><span class="sxs-lookup"><span data-stu-id="6baf4-190">Example 9: Using ForEach-Object with more than two script blocks</span></span>

<span data-ttu-id="6baf4-191">Neste exemplo, passamos dois blocos de script de posição.</span><span class="sxs-lookup"><span data-stu-id="6baf4-191">In this example, we pass two script blocks positionally.</span></span> <span data-ttu-id="6baf4-192">Todos os blocos de script são associados ao parâmetro de **processo** .</span><span class="sxs-lookup"><span data-stu-id="6baf4-192">All the script blocks bind to the **Process** parameter.</span></span> <span data-ttu-id="6baf4-193">No entanto, eles são tratados como se tivessem sido passados para os parâmetros **begin** , **process** e **end** .</span><span class="sxs-lookup"><span data-stu-id="6baf4-193">However, they are treated as if they had been passed to the **Begin** , **Process** , and **End** parameters.</span></span>

```powershell
1..2 | ForEach-Object { 'begin' } { 'process A' }  { 'process B' }  { 'end' }
```

```Output
begin
process A
process B
process A
process B
end
```

> [!NOTE]
> <span data-ttu-id="6baf4-194">O primeiro bloco de script é sempre mapeado para o `begin` bloco, o último bloco é mapeado para o `end` bloco e os blocos no between são todos mapeados para o `process` bloco.</span><span class="sxs-lookup"><span data-stu-id="6baf4-194">The first script block is always mapped to the `begin` block, the last block is mapped to the `end` block, and the blocks in between are all mapped to the `process` block.</span></span>

### <span data-ttu-id="6baf4-195">Exemplo 10: executar vários blocos de script para cada item de pipeline</span><span class="sxs-lookup"><span data-stu-id="6baf4-195">Example 10: Run multiple script blocks for each pipeline item</span></span>

<span data-ttu-id="6baf4-196">Conforme mostrado no exemplo anterior, vários blocos de script passados usando o parâmetro **process** são mapeados para os parâmetros **begin** e **end** .</span><span class="sxs-lookup"><span data-stu-id="6baf4-196">As shown in the previous example, multiple script blocks passed using the **Process** parameter get mapped to the **Begin** and **End** parameters.</span></span> <span data-ttu-id="6baf4-197">Para evitar esse mapeamento, você deve fornecer valores explícitos para os parâmetros de **início** e **término** .</span><span class="sxs-lookup"><span data-stu-id="6baf4-197">To avoid this mapping, you must provide explicit values for the **Begin** and **End** parameters.</span></span>

```powershell
1..2 | ForEach-Object -Begin $null -Process { 'one' }, { 'two' }, { 'three' } -End $null
```

```Output
one
two
three
one
two
three
```

### <span data-ttu-id="6baf4-198">Exemplo 11: executar script lento em lotes paralelos</span><span class="sxs-lookup"><span data-stu-id="6baf4-198">Example 11: Run slow script in parallel batches</span></span>

<span data-ttu-id="6baf4-199">Este exemplo executa um bloco de script simples que avalia uma cadeia de caracteres e é suspenso por um segundo.</span><span class="sxs-lookup"><span data-stu-id="6baf4-199">This example runs a simple script block that evaluates a string and sleeps for one second.</span></span>

```powershell
$Message = "Output:"

1..8 | ForEach-Object -Parallel {
    "$using:Message $_"
    Start-Sleep 1
} -ThrottleLimit 4
```

```Output
Output: 1
Output: 2
Output: 3
Output: 4
Output: 5
Output: 6
Output: 7
Output: 8
```

<span data-ttu-id="6baf4-200">O valor do parâmetro **ThrottleLimit** é definido como 4 para que a entrada seja processada em lotes de quatro.</span><span class="sxs-lookup"><span data-stu-id="6baf4-200">The **ThrottleLimit** parameter value is set to 4 so that the input is processed in batches of four.</span></span>
<span data-ttu-id="6baf4-201">A `$using:` palavra-chave é usada para passar a `$Message` variável em cada bloco de script paralelo.</span><span class="sxs-lookup"><span data-stu-id="6baf4-201">The `$using:` keyword is used to pass the `$Message` variable into each parallel script block.</span></span>

### <span data-ttu-id="6baf4-202">Exemplo 12: recuperar entradas de log em paralelo</span><span class="sxs-lookup"><span data-stu-id="6baf4-202">Example 12: Retrieve log entries in parallel</span></span>

<span data-ttu-id="6baf4-203">Este exemplo recupera 50.000 entradas de log de 5 logs do sistema em uma máquina local do Windows.</span><span class="sxs-lookup"><span data-stu-id="6baf4-203">This example retrieves 50,000 log entries from 5 system logs on a local Windows machine.</span></span>

```powershell
$logNames = 'Security','Application','System','Windows PowerShell','Microsoft-Windows-Store/Operational'

$logEntries = $logNames | ForEach-Object -Parallel {
    Get-WinEvent -LogName $_ -MaxEvents 10000
} -ThrottleLimit 5

$logEntries.Count
```

```Output
50000
```

<span data-ttu-id="6baf4-204">O parâmetro **Parallel** especifica o bloco de script que é executado em paralelo para cada nome de log de entrada.</span><span class="sxs-lookup"><span data-stu-id="6baf4-204">The **Parallel** parameter specifies the script block that is run in parallel for each input log name.</span></span> <span data-ttu-id="6baf4-205">O parâmetro **ThrottleLimit** garante que todos os cinco blocos de script sejam executados ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="6baf4-205">The **ThrottleLimit** parameter ensures that all five script blocks run at the same time.</span></span>

### <span data-ttu-id="6baf4-206">Exemplo 13: executado em paralelo como um trabalho</span><span class="sxs-lookup"><span data-stu-id="6baf4-206">Example 13: Run in parallel as a job</span></span>

<span data-ttu-id="6baf4-207">Este exemplo executa um bloco de script simples em paralelo, criando dois trabalhos em segundo plano por vez.</span><span class="sxs-lookup"><span data-stu-id="6baf4-207">This example runs a simple script block in parallel, creating two background jobs at a time.</span></span>

```powershell
$job = 1..10 | ForEach-Object -Parallel {
    "Output: $_"
    Start-Sleep 1
} -ThrottleLimit 2 -AsJob

$job | Receive-Job -Wait
```

```Output
Output: 1
Output: 2
Output: 3
Output: 4
Output: 5
Output: 6
Output: 7
Output: 8
Output: 9
Output: 10
```

<span data-ttu-id="6baf4-208">a `$job` variável recebe o objeto de trabalho que coleta dados de saída e monitora o estado de execução.</span><span class="sxs-lookup"><span data-stu-id="6baf4-208">the `$job` variable receives the job object that collects output data and monitors running state.</span></span>
<span data-ttu-id="6baf4-209">O objeto de trabalho é canalizado para `Receive-Job` com o parâmetro de opção **Wait** .</span><span class="sxs-lookup"><span data-stu-id="6baf4-209">The job object is piped to `Receive-Job` with the **Wait** switch parameter.</span></span> <span data-ttu-id="6baf4-210">E isso transmite a saída para o console, assim como se `ForEach-Object -Parallel` fosse executado sem **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="6baf4-210">And this streams output to the console, just as if `ForEach-Object -Parallel` was run without **AsJob** .</span></span>

### <span data-ttu-id="6baf4-211">Exemplo 14: usando referências de variável de thread seguro</span><span class="sxs-lookup"><span data-stu-id="6baf4-211">Example 14: Using thread safe variable references</span></span>

<span data-ttu-id="6baf4-212">Este exemplo invoca blocos de script em paralelo para coletar objetos de processo nomeados exclusivamente.</span><span class="sxs-lookup"><span data-stu-id="6baf4-212">This example invokes script blocks in parallel to collect uniquely named Process objects.</span></span>

```powershell
$threadSafeDictionary = [System.Collections.Concurrent.ConcurrentDictionary[string,object]]::new()
Get-Process | ForEach-Object -Parallel {
    $dict = $using:threadSafeDictionary
    $dict.TryAdd($_.ProcessName, $_)
}

$threadSafeDictionary["pwsh"]
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     82    82.87     130.85      15.55    2808   2 pwsh
```

<span data-ttu-id="6baf4-213">Uma única instância de um objeto **ConcurrentDictionary** é passada para cada bloco de script para coletar os objetos.</span><span class="sxs-lookup"><span data-stu-id="6baf4-213">A single instance of a **ConcurrentDictionary** object is passed to each script block to collect the objects.</span></span> <span data-ttu-id="6baf4-214">Como o **ConcurrentDictionary** é thread-safe, é seguro ser modificado por cada script paralelo.</span><span class="sxs-lookup"><span data-stu-id="6baf4-214">Since the **ConcurrentDictionary** is thread safe, it is safe to be modified by each parallel script.</span></span> <span data-ttu-id="6baf4-215">Um objeto sem thread-safe, como **System. Collections. Generic. Dictionary** , não seria seguro para uso aqui.</span><span class="sxs-lookup"><span data-stu-id="6baf4-215">A non-thread-safe object, such as **System.Collections.Generic.Dictionary** , would not be safe to use here.</span></span>

> [!NOTE]
> <span data-ttu-id="6baf4-216">Este exemplo é um uso muito ineficiente do parâmetro **paralelo** .</span><span class="sxs-lookup"><span data-stu-id="6baf4-216">This example is a very inefficient use of **Parallel** parameter.</span></span> <span data-ttu-id="6baf4-217">O script simplesmente adiciona o objeto de entrada a um objeto de dicionário simultâneo.</span><span class="sxs-lookup"><span data-stu-id="6baf4-217">The script simply adds the input object to a concurrent dictionary object.</span></span> <span data-ttu-id="6baf4-218">É trivial e não vale a pena a sobrecarga de invocar cada script em um thread separado.</span><span class="sxs-lookup"><span data-stu-id="6baf4-218">It is trivial and not worth the overhead of invoking each script in a separate thread.</span></span> <span data-ttu-id="6baf4-219">Executar `ForEach-Object` normalmente sem o comutador **paralelo** é muito mais eficiente e mais rápido.</span><span class="sxs-lookup"><span data-stu-id="6baf4-219">Running `ForEach-Object` normally without the **Parallel** switch is much more efficient and faster.</span></span> <span data-ttu-id="6baf4-220">Este exemplo destina-se apenas a demonstrar como usar variáveis de thread seguro.</span><span class="sxs-lookup"><span data-stu-id="6baf4-220">This example is only intended to demonstrate how to use thread safe variables.</span></span>

### <span data-ttu-id="6baf4-221">Exemplo 15: gravando erros com execução paralela</span><span class="sxs-lookup"><span data-stu-id="6baf4-221">Example 15: Writing errors with parallel execution</span></span>

<span data-ttu-id="6baf4-222">Este exemplo grava no fluxo de erros em paralelo, em que a ordem dos erros gravados é aleatória.</span><span class="sxs-lookup"><span data-stu-id="6baf4-222">This example writes to the error stream in parallel, where the order of written errors is random.</span></span>

```powershell
1..3 | ForEach-Object -Parallel {
    Write-Error "Error: $_"
}
```

```Output
Write-Error: Error: 1
Write-Error: Error: 3
Write-Error: Error: 2
```

### <span data-ttu-id="6baf4-223">Exemplo 16: finalizando erros em execução paralela</span><span class="sxs-lookup"><span data-stu-id="6baf4-223">Example 16: Terminating errors in parallel execution</span></span>

<span data-ttu-id="6baf4-224">Este exemplo demonstra um erro de encerramento em um scriptblock em execução paralela.</span><span class="sxs-lookup"><span data-stu-id="6baf4-224">This example demonstrates a terminating error in one parallel running scriptblock.</span></span>

```powershell
1..5 | ForEach-Object -Parallel {
    if ($_ -eq 3)
    {
        throw "Terminating Error: $_"
    }

    Write-Output "Output: $_"
}
```

```Output
Exception: Terminating Error: 3
Output: 1
Output: 4
Output: 2
Output: 5
```

<span data-ttu-id="6baf4-225">`Output: 3` Nunca é gravado porque o scriptblock paralelo dessa iteração foi encerrado.</span><span class="sxs-lookup"><span data-stu-id="6baf4-225">`Output: 3` is never written because the parallel scriptblock for that iteration was terminated.</span></span>

## <span data-ttu-id="6baf4-226">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="6baf4-226">Parameters</span></span>

### <span data-ttu-id="6baf4-227">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="6baf4-227">-ArgumentList</span></span>

<span data-ttu-id="6baf4-228">Especifica uma matriz de argumentos para uma chamada de método.</span><span class="sxs-lookup"><span data-stu-id="6baf4-228">Specifies an array of arguments to a method call.</span></span> <span data-ttu-id="6baf4-229">Para obter mais informações sobre o comportamento de **ArgumentList** , consulte [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="6baf4-229">For more information about the behavior of **ArgumentList** , see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

<span data-ttu-id="6baf4-230">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="6baf4-230">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: PropertyAndMethodSet
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6baf4-231">-Início</span><span class="sxs-lookup"><span data-stu-id="6baf4-231">-Begin</span></span>

<span data-ttu-id="6baf4-232">Especifica um bloco de script que é executado antes desse cmdlet processar qualquer objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="6baf4-232">Specifies a script block that runs before this cmdlet processes any input objects.</span></span> <span data-ttu-id="6baf4-233">Esse bloco de script só é executado uma vez para o pipeline inteiro.</span><span class="sxs-lookup"><span data-stu-id="6baf4-233">This script block is only run once for the entire pipeline.</span></span> <span data-ttu-id="6baf4-234">Para obter mais informações sobre o `begin` bloco, consulte [about_Functions](about/about_functions.md#piping-objects-to-functions).</span><span class="sxs-lookup"><span data-stu-id="6baf4-234">For more information about the `begin` block, see [about_Functions](about/about_functions.md#piping-objects-to-functions).</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6baf4-235">-Fim</span><span class="sxs-lookup"><span data-stu-id="6baf4-235">-End</span></span>

<span data-ttu-id="6baf4-236">Especifica um bloco de script que é executado depois que esse cmdlet processa todos os objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="6baf4-236">Specifies a script block that runs after this cmdlet processes all input objects.</span></span> <span data-ttu-id="6baf4-237">Esse bloco de script só é executado uma vez para o pipeline inteiro.</span><span class="sxs-lookup"><span data-stu-id="6baf4-237">This script block is only run once for the entire pipeline.</span></span> <span data-ttu-id="6baf4-238">Para obter mais informações sobre o `end` bloco, consulte [about_Functions](about/about_functions.md#piping-objects-to-functions).</span><span class="sxs-lookup"><span data-stu-id="6baf4-238">For more information about the `end` block, see [about_Functions](about/about_functions.md#piping-objects-to-functions).</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6baf4-239">-InputObject</span><span class="sxs-lookup"><span data-stu-id="6baf4-239">-InputObject</span></span>

<span data-ttu-id="6baf4-240">Especifica os objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="6baf4-240">Specifies the input objects.</span></span> <span data-ttu-id="6baf4-241">`ForEach-Object` executa o bloco de script ou a instrução de operação em cada objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="6baf4-241">`ForEach-Object` runs the script block or operation statement on each input object.</span></span> <span data-ttu-id="6baf4-242">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="6baf4-242">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="6baf4-243">Quando você usa o parâmetro **InputObject** com `ForEach-Object` , em vez de direcionar os resultados de comando para `ForEach-Object` , o valor **InputObject** é tratado como um único objeto.</span><span class="sxs-lookup"><span data-stu-id="6baf4-243">When you use the **InputObject** parameter with `ForEach-Object`, instead of piping command results to `ForEach-Object`, the **InputObject** value is treated as a single object.</span></span> <span data-ttu-id="6baf4-244">Isso é verdadeiro mesmo se o valor for uma coleção que é o resultado de um comando, como `-InputObject (Get-Process)` .</span><span class="sxs-lookup"><span data-stu-id="6baf4-244">This is true even if the value is a collection that is the result of a command, such as `-InputObject (Get-Process)`.</span></span>
<span data-ttu-id="6baf4-245">Como **InputObject** não pode retornar propriedades individuais de uma matriz ou coleção de objetos, recomendamos que, se você usar `ForEach-Object` o para executar operações em uma coleção de objetos para os objetos que têm valores específicos nas propriedades definidas, use `ForEach-Object` no pipeline, conforme mostrado nos exemplos neste tópico.</span><span class="sxs-lookup"><span data-stu-id="6baf4-245">Because **InputObject** cannot return individual properties from an array or collection of objects, we recommend that if you use `ForEach-Object` to perform operations on a collection of objects for those objects that have specific values in defined properties, you use `ForEach-Object` in the pipeline, as shown in the examples in this topic.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6baf4-246">-MemberName</span><span class="sxs-lookup"><span data-stu-id="6baf4-246">-MemberName</span></span>

<span data-ttu-id="6baf4-247">Especifica a propriedade a ser obtida ou o método a ser chamado.</span><span class="sxs-lookup"><span data-stu-id="6baf4-247">Specifies the property to get or the method to call.</span></span>

<span data-ttu-id="6baf4-248">Caracteres curinga são permitidos, mas só funcionam se a cadeia de caracteres resultante for resolvida para um valor exclusivo.</span><span class="sxs-lookup"><span data-stu-id="6baf4-248">Wildcard characters are permitted, but work only if the resulting string resolves to a unique value.</span></span>
<span data-ttu-id="6baf4-249">Por exemplo, se você executar `Get-Process | ForEach -MemberName *Name` , o padrão curinga corresponde a mais de um membro causando a falha do comando.</span><span class="sxs-lookup"><span data-stu-id="6baf4-249">For example, if you run `Get-Process | ForEach -MemberName *Name`, the wildcard pattern matches more than one member causing the command to fail.</span></span>

<span data-ttu-id="6baf4-250">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="6baf4-250">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: PropertyAndMethodSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="6baf4-251">-Processo</span><span class="sxs-lookup"><span data-stu-id="6baf4-251">-Process</span></span>

<span data-ttu-id="6baf4-252">Especifica a operação que é executada em cada objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="6baf4-252">Specifies the operation that is performed on each input object.</span></span> <span data-ttu-id="6baf4-253">Esse bloco de script é executado para cada objeto no pipeline.</span><span class="sxs-lookup"><span data-stu-id="6baf4-253">This script block is run for every object in the pipeline.</span></span> <span data-ttu-id="6baf4-254">Para obter mais informações sobre o `process` bloco, consulte [about_Functions](about/about_functions.md#piping-objects-to-functions).</span><span class="sxs-lookup"><span data-stu-id="6baf4-254">For more information about the `process` block, see [about_Functions](about/about_functions.md#piping-objects-to-functions).</span></span>

<span data-ttu-id="6baf4-255">Quando você fornece vários blocos de script para o parâmetro **process** , o primeiro bloco de script é sempre mapeado para o `begin` bloco.</span><span class="sxs-lookup"><span data-stu-id="6baf4-255">When you provide multiple script blocks to the **Process** parameter, the first script block is always mapped to the `begin` block.</span></span> <span data-ttu-id="6baf4-256">Se houver apenas dois blocos de script, o segundo bloco será mapeado para o `process` bloco.</span><span class="sxs-lookup"><span data-stu-id="6baf4-256">If there are only two script blocks, the second block is mapped to the `process` block.</span></span> <span data-ttu-id="6baf4-257">Se houver três ou mais blocos de script, o primeiro bloco de script será sempre mapeado para o `begin` bloco, o último bloco será mapeado para o `end` bloco e os blocos no between serão todos mapeados para o `process` bloco.</span><span class="sxs-lookup"><span data-stu-id="6baf4-257">If there are three or more script blocks, first script block is always mapped to the `begin` block, the last block is mapped to the `end` block, and the blocks in between are all mapped to the `process` block.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock[]
Parameter Sets: ScriptBlockSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6baf4-258">-RemainingScripts</span><span class="sxs-lookup"><span data-stu-id="6baf4-258">-RemainingScripts</span></span>

<span data-ttu-id="6baf4-259">Especifica todos os blocos de script que não são usados pelo parâmetro **process** .</span><span class="sxs-lookup"><span data-stu-id="6baf4-259">Specifies all script blocks that are not taken by the **Process** parameter.</span></span>

<span data-ttu-id="6baf4-260">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="6baf4-260">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock[]
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6baf4-261">-Parallel</span><span class="sxs-lookup"><span data-stu-id="6baf4-261">-Parallel</span></span>

<span data-ttu-id="6baf4-262">Especifica o bloco de script a ser usado para processamento paralelo de objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="6baf4-262">Specifies the script block to be used for parallel processing of input objects.</span></span> <span data-ttu-id="6baf4-263">Insira um bloco de script que descreve a operação.</span><span class="sxs-lookup"><span data-stu-id="6baf4-263">Enter a script block that describes the operation.</span></span>

<span data-ttu-id="6baf4-264">Esse parâmetro foi introduzido no PowerShell 7,0.</span><span class="sxs-lookup"><span data-stu-id="6baf4-264">This parameter was introduced in PowerShell 7.0.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ParallelParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6baf4-265">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="6baf4-265">-ThrottleLimit</span></span>

<span data-ttu-id="6baf4-266">Especifica o número de blocos de script em paralelo.</span><span class="sxs-lookup"><span data-stu-id="6baf4-266">Specifies the number of script blocks that in parallel.</span></span> <span data-ttu-id="6baf4-267">Os objetos de entrada são bloqueados até que a contagem de blocos de script em execução fique abaixo do **ThrottleLimit** .</span><span class="sxs-lookup"><span data-stu-id="6baf4-267">Input objects are blocked until the running script block count falls below the **ThrottleLimit** .</span></span> <span data-ttu-id="6baf4-268">O valor padrão é `5`.</span><span class="sxs-lookup"><span data-stu-id="6baf4-268">The default value is `5`.</span></span>

<span data-ttu-id="6baf4-269">Esse parâmetro foi introduzido no PowerShell 7,0.</span><span class="sxs-lookup"><span data-stu-id="6baf4-269">This parameter was introduced in PowerShell 7.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ParallelParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6baf4-270">-TimeoutSeconds</span><span class="sxs-lookup"><span data-stu-id="6baf4-270">-TimeoutSeconds</span></span>

<span data-ttu-id="6baf4-271">Especifica o número de segundos de espera para que todas as entradas sejam processadas em paralelo.</span><span class="sxs-lookup"><span data-stu-id="6baf4-271">Specifies the number of seconds to wait for all input to be processed in parallel.</span></span> <span data-ttu-id="6baf4-272">Após o tempo limite especificado, todos os scripts em execução serão interrompidos.</span><span class="sxs-lookup"><span data-stu-id="6baf4-272">After the specified timeout time, all running scripts are stopped.</span></span> <span data-ttu-id="6baf4-273">E todos os objetos de entrada restantes a serem processados serão ignorados.</span><span class="sxs-lookup"><span data-stu-id="6baf4-273">And any remaining input objects to be processed are ignored.</span></span> <span data-ttu-id="6baf4-274">O valor padrão de `0` desabilita o tempo limite e `ForEach-Object -Parallel` pode ser executado indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="6baf4-274">Default value of `0` disables the timeout, and `ForEach-Object -Parallel` can run indefinitely.</span></span> <span data-ttu-id="6baf4-275">Digitar <kbd>Ctrl</kbd> + <kbd>C</kbd> na linha de comando interrompe um comando em execução `ForEach-Object -Parallel` .</span><span class="sxs-lookup"><span data-stu-id="6baf4-275">Typing <kbd>Ctrl</kbd>+<kbd>C</kbd> at the command line stops a running `ForEach-Object -Parallel` command.</span></span> <span data-ttu-id="6baf4-276">Esse parâmetro não pode ser usado junto com o parâmetro **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="6baf4-276">This parameter cannot be used along with the **AsJob** parameter.</span></span>

<span data-ttu-id="6baf4-277">Esse parâmetro foi introduzido no PowerShell 7,0.</span><span class="sxs-lookup"><span data-stu-id="6baf4-277">This parameter was introduced in PowerShell 7.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ParallelParameterSet
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6baf4-278">-AsJob</span><span class="sxs-lookup"><span data-stu-id="6baf4-278">-AsJob</span></span>

<span data-ttu-id="6baf4-279">Faz com que a invocação paralela seja executada como um trabalho do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6baf4-279">Causes the parallel invocation to run as a PowerShell job.</span></span> <span data-ttu-id="6baf4-280">Um único objeto de trabalho é retornado em vez da saída dos blocos de script em execução.</span><span class="sxs-lookup"><span data-stu-id="6baf4-280">A single job object is returned instead of output from the running script blocks.</span></span> <span data-ttu-id="6baf4-281">O objeto de trabalho contém trabalhos filho para cada bloco de script paralelo que é executado.</span><span class="sxs-lookup"><span data-stu-id="6baf4-281">The job object contains child jobs for each parallel script block that runs.</span></span> <span data-ttu-id="6baf4-282">O objeto de trabalho pode ser usado por todos os cmdlets de trabalho do PowerShell para monitorar o estado de execução e recuperar dados.</span><span class="sxs-lookup"><span data-stu-id="6baf4-282">The job object can be used by all PowerShell job cmdlets, to monitor running state and retrieve data.</span></span>

<span data-ttu-id="6baf4-283">Esse parâmetro foi introduzido no PowerShell 7,0.</span><span class="sxs-lookup"><span data-stu-id="6baf4-283">This parameter was introduced in PowerShell 7.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ParallelParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6baf4-284">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6baf4-284">-Confirm</span></span>

<span data-ttu-id="6baf4-285">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6baf4-285">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6baf4-286">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6baf4-286">-WhatIf</span></span>

<span data-ttu-id="6baf4-287">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="6baf4-287">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="6baf4-288">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="6baf4-288">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6baf4-289">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6baf4-289">CommonParameters</span></span>

<span data-ttu-id="6baf4-290">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6baf4-290">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6baf4-291">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6baf4-291">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6baf4-292">Entradas</span><span class="sxs-lookup"><span data-stu-id="6baf4-292">Inputs</span></span>

### <span data-ttu-id="6baf4-293">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="6baf4-293">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="6baf4-294">É possível canalizar qualquer objeto para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6baf4-294">You can pipe any object to this cmdlet.</span></span>

## <span data-ttu-id="6baf4-295">Saídas</span><span class="sxs-lookup"><span data-stu-id="6baf4-295">Outputs</span></span>

### <span data-ttu-id="6baf4-296">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="6baf4-296">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="6baf4-297">Esse cmdlet retorna objetos que são determinados pela entrada.</span><span class="sxs-lookup"><span data-stu-id="6baf4-297">This cmdlet returns objects that are determined by the input.</span></span>

## <span data-ttu-id="6baf4-298">Observações</span><span class="sxs-lookup"><span data-stu-id="6baf4-298">Notes</span></span>

- <span data-ttu-id="6baf4-299">O `ForEach-Object` cmdlet funciona de forma muito parecida com a instrução **foreach** , exceto que não é possível canalizar a entrada para uma instrução **foreach** .</span><span class="sxs-lookup"><span data-stu-id="6baf4-299">The `ForEach-Object` cmdlet works much like the **Foreach** statement, except that you cannot pipe input to a **Foreach** statement.</span></span> <span data-ttu-id="6baf4-300">Para obter mais informações sobre a instrução **foreach** , consulte [about_Foreach](./About/about_Foreach.md).</span><span class="sxs-lookup"><span data-stu-id="6baf4-300">For more information about the **Foreach** statement, see [about_Foreach](./About/about_Foreach.md).</span></span>

- <span data-ttu-id="6baf4-301">A partir do PowerShell 4,0, `Where` e os `ForEach` métodos foram adicionados para uso com coleções.</span><span class="sxs-lookup"><span data-stu-id="6baf4-301">Starting in PowerShell 4.0, `Where` and `ForEach` methods were added for use with collections.</span></span> <span data-ttu-id="6baf4-302">Você pode ler mais sobre esses novos métodos aqui [about_arrays](./About/about_Arrays.md)</span><span class="sxs-lookup"><span data-stu-id="6baf4-302">You can read more about these new methods here [about_arrays](./About/about_Arrays.md)</span></span>

- <span data-ttu-id="6baf4-303">O `ForEach-Object -Parallel` conjunto de parâmetros usa a API interna do PowerShell para executar cada bloco de script.</span><span class="sxs-lookup"><span data-stu-id="6baf4-303">The `ForEach-Object -Parallel` parameter set uses PowerShell's internal API to run each script block.</span></span> <span data-ttu-id="6baf4-304">Isso é significativamente mais sobrecarga do que executar `ForEach-Object` normalmente com processamento sequencial.</span><span class="sxs-lookup"><span data-stu-id="6baf4-304">This is significantly more overhead than running `ForEach-Object` normally with sequential processing.</span></span> <span data-ttu-id="6baf4-305">É importante usar **Parallel** em que a sobrecarga de execução em paralelo é pequena em comparação com o trabalho que o bloco de script executa.</span><span class="sxs-lookup"><span data-stu-id="6baf4-305">It is important to use **Parallel** where the overhead of running in parallel is small compared to work the script block performs.</span></span> <span data-ttu-id="6baf4-306">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6baf4-306">For example:</span></span>

  - <span data-ttu-id="6baf4-307">Computação de scripts intensivos em máquinas com vários núcleos</span><span class="sxs-lookup"><span data-stu-id="6baf4-307">Compute intensive scripts on multi-core machines</span></span>
  - <span data-ttu-id="6baf4-308">Scripts que gastam tempo aguardando resultados ou realizando operações de arquivo</span><span class="sxs-lookup"><span data-stu-id="6baf4-308">Scripts that spend time waiting for results or doing file operations</span></span>

  <span data-ttu-id="6baf4-309">O uso do parâmetro **Parallel** pode fazer com que os scripts sejam executados muito mais lentamente do que o normal.</span><span class="sxs-lookup"><span data-stu-id="6baf4-309">Using the **Parallel** parameter can cause scripts to run much slower than normal.</span></span> <span data-ttu-id="6baf4-310">Especialmente se os scripts paralelos forem triviais.</span><span class="sxs-lookup"><span data-stu-id="6baf4-310">Especially if the parallel scripts are trivial.</span></span> <span data-ttu-id="6baf4-311">Experimente em **paralelo** para descobrir onde ele pode ser benéfico.</span><span class="sxs-lookup"><span data-stu-id="6baf4-311">Experiment with **Parallel** to discover where it can be beneficial.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="6baf4-312">O `ForEach-Object -Parallel` conjunto de parâmetros executa blocos de script em paralelo em threads de processo separados.</span><span class="sxs-lookup"><span data-stu-id="6baf4-312">The `ForEach-Object -Parallel` parameter set runs script blocks in parallel on separate process threads.</span></span> <span data-ttu-id="6baf4-313">A `$using:` palavra-chave permite passar referências de variáveis do thread de invocação de cmdlet para cada thread de bloco de script em execução.</span><span class="sxs-lookup"><span data-stu-id="6baf4-313">The `$using:` keyword allows passing variable references from the cmdlet invocation thread to each running script block thread.</span></span> <span data-ttu-id="6baf4-314">Como os blocos de script são executados em threads diferentes, as variáveis de objeto passadas por referência devem ser usadas com segurança.</span><span class="sxs-lookup"><span data-stu-id="6baf4-314">Since the script blocks run in different threads, the object variables passed by reference must be used safely.</span></span> <span data-ttu-id="6baf4-315">Geralmente, é seguro ler de objetos referenciados que não são alterados.</span><span class="sxs-lookup"><span data-stu-id="6baf4-315">Generally it is safe to read from referenced objects that don't change.</span></span> <span data-ttu-id="6baf4-316">Mas se o estado do objeto estiver sendo modificado, você deverá usar objetos de thread seguro, como .NET **System. Collection. tipos simultâneos** (consulte o exemplo 11).</span><span class="sxs-lookup"><span data-stu-id="6baf4-316">But if the object state is being modified then you must used thread safe objects, such as .Net **System.Collection.Concurrent** types (See Example 11).</span></span>

## <span data-ttu-id="6baf4-317">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="6baf4-317">Related links</span></span>

[<span data-ttu-id="6baf4-318">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="6baf4-318">Compare-Object</span></span>](../Microsoft.PowerShell.Utility/Compare-Object.md)

[<span data-ttu-id="6baf4-319">Where-Object</span><span class="sxs-lookup"><span data-stu-id="6baf4-319">Where-Object</span></span>](Where-Object.md)

[<span data-ttu-id="6baf4-320">Group-Object</span><span class="sxs-lookup"><span data-stu-id="6baf4-320">Group-Object</span></span>](../Microsoft.PowerShell.Utility/Group-Object.md)

[<span data-ttu-id="6baf4-321">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="6baf4-321">Measure-Object</span></span>](../Microsoft.PowerShell.Utility/Measure-Object.md)

[<span data-ttu-id="6baf4-322">New-Object</span><span class="sxs-lookup"><span data-stu-id="6baf4-322">New-Object</span></span>](../Microsoft.PowerShell.Utility/New-Object.md)

[<span data-ttu-id="6baf4-323">Select-Object</span><span class="sxs-lookup"><span data-stu-id="6baf4-323">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="6baf4-324">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="6baf4-324">Sort-Object</span></span>](../Microsoft.PowerShell.Utility/Sort-Object.md)

[<span data-ttu-id="6baf4-325">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="6baf4-325">Tee-Object</span></span>](../Microsoft.PowerShell.Utility/Tee-Object.md)
