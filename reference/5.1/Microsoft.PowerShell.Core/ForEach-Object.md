---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 09/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/foreach-object?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ForEach-Object
ms.openlocfilehash: 327add884077083d37e1f58ab8f78b784a870362
ms.sourcegitcommit: e0f9fe6335be1e0f94bedaa0e8baec2acaeaa076
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "93195304"
---
# <span data-ttu-id="e08cd-103">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="e08cd-103">ForEach-Object</span></span>

## <span data-ttu-id="e08cd-104">Sinopse</span><span class="sxs-lookup"><span data-stu-id="e08cd-104">Synopsis</span></span>
<span data-ttu-id="e08cd-105">Executa uma operação em cada item de uma coleção de objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="e08cd-105">Performs an operation against each item in a collection of input objects.</span></span>

## <span data-ttu-id="e08cd-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e08cd-106">Syntax</span></span>

### <span data-ttu-id="e08cd-107">ScriptBlockset (padrão)</span><span class="sxs-lookup"><span data-stu-id="e08cd-107">ScriptBlockSet (Default)</span></span>

```
ForEach-Object [-InputObject <PSObject>] [-Begin <ScriptBlock>] [-Process] <ScriptBlock[]>
 [-End <ScriptBlock>] [-RemainingScripts <ScriptBlock[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e08cd-108">PropertyAndMethodSet</span><span class="sxs-lookup"><span data-stu-id="e08cd-108">PropertyAndMethodSet</span></span>

```
ForEach-Object [-InputObject <PSObject>] [-MemberName] <String> [-ArgumentList <Object[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e08cd-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="e08cd-109">Description</span></span>

<span data-ttu-id="e08cd-110">O `ForEach-Object` cmdlet executa uma operação em cada item em uma coleção de objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="e08cd-110">The `ForEach-Object` cmdlet performs an operation on each item in a collection of input objects.</span></span> <span data-ttu-id="e08cd-111">Os objetos de entrada podem ser canalizados para o cmdlet ou especificados usando o parâmetro **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="e08cd-111">The input objects can be piped to the cmdlet or specified by using the **InputObject** parameter.</span></span>

<span data-ttu-id="e08cd-112">A partir do Windows PowerShell 3,0, há duas maneiras diferentes de construir um `ForEach-Object` comando.</span><span class="sxs-lookup"><span data-stu-id="e08cd-112">Starting in Windows PowerShell 3.0, there are two different ways to construct a `ForEach-Object` command.</span></span>

- <span data-ttu-id="e08cd-113">**Bloco de script** .</span><span class="sxs-lookup"><span data-stu-id="e08cd-113">**Script block** .</span></span> <span data-ttu-id="e08cd-114">Você pode usar um bloco de script para especificar a operação.</span><span class="sxs-lookup"><span data-stu-id="e08cd-114">You can use a script block to specify the operation.</span></span> <span data-ttu-id="e08cd-115">No bloco de script, use a `$_` variável para representar o objeto atual.</span><span class="sxs-lookup"><span data-stu-id="e08cd-115">Within the script block, use the `$_` variable to represent the current object.</span></span> <span data-ttu-id="e08cd-116">O bloco de script é o valor do parâmetro **Process** .</span><span class="sxs-lookup"><span data-stu-id="e08cd-116">The script block is the value of the **Process** parameter.</span></span> <span data-ttu-id="e08cd-117">O bloco de script pode conter qualquer script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e08cd-117">The script block can contain any PowerShell script.</span></span>

  <span data-ttu-id="e08cd-118">Por exemplo, o comando a seguir obtém o valor da propriedade **ProcessName** de cada processo no computador.</span><span class="sxs-lookup"><span data-stu-id="e08cd-118">For example, the following command gets the value of the **ProcessName** property of each process on the computer.</span></span>

  `Get-Process | ForEach-Object {$_.ProcessName}`

  <span data-ttu-id="e08cd-119">`ForEach-Object` dá suporte `begin` aos `process` blocos, e `end` conforme descrito em [about_Functions](about/about_functions.md#piping-objects-to-functions).</span><span class="sxs-lookup"><span data-stu-id="e08cd-119">`ForEach-Object` supports the `begin`, `process`, and `end` blocks as described in [about_functions](about/about_functions.md#piping-objects-to-functions).</span></span>

  > [!NOTE]
  > <span data-ttu-id="e08cd-120">Os blocos de script são executados no escopo do chamador.</span><span class="sxs-lookup"><span data-stu-id="e08cd-120">The script blocks run in the caller's scope.</span></span> <span data-ttu-id="e08cd-121">Portanto, os blocos têm acesso a variáveis nesse escopo e podem criar novas variáveis que persistem nesse escopo após a conclusão do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e08cd-121">Therefore the blocks have access to variables in that scope and can create new variables that persist in that scope after the cmdlet completes.</span></span>

- <span data-ttu-id="e08cd-122">**Instrução de operação** .</span><span class="sxs-lookup"><span data-stu-id="e08cd-122">**Operation statement** .</span></span> <span data-ttu-id="e08cd-123">Você também pode escrever uma instrução de operação, que é muito mais parecida com a linguagem natural.</span><span class="sxs-lookup"><span data-stu-id="e08cd-123">You can also write an operation statement, which is much more like natural language.</span></span> <span data-ttu-id="e08cd-124">Você pode usar a instrução de operação para especificar um valor de propriedade ou chamar um método.</span><span class="sxs-lookup"><span data-stu-id="e08cd-124">You can use the operation statement to specify a property value or call a method.</span></span> <span data-ttu-id="e08cd-125">Instruções de operação foram introduzidas no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="e08cd-125">Operation statements were introduced in Windows PowerShell 3.0.</span></span>

  <span data-ttu-id="e08cd-126">Por exemplo, o comando a seguir também obtém o valor da propriedade **ProcessName** de cada processo no computador.</span><span class="sxs-lookup"><span data-stu-id="e08cd-126">For example, the following command also gets the value of the **ProcessName** property of each process on the computer.</span></span>

  `Get-Process | ForEach-Object ProcessName`

## <span data-ttu-id="e08cd-127">Exemplos</span><span class="sxs-lookup"><span data-stu-id="e08cd-127">Examples</span></span>

### <span data-ttu-id="e08cd-128">Exemplo 1: dividir inteiros em uma matriz</span><span class="sxs-lookup"><span data-stu-id="e08cd-128">Example 1: Divide integers in an array</span></span>

<span data-ttu-id="e08cd-129">Este exemplo usa uma matriz de três inteiros e divide cada um deles por 1024.</span><span class="sxs-lookup"><span data-stu-id="e08cd-129">This example takes an array of three integers and divides each one of them by 1024.</span></span>

```powershell
30000, 56798, 12432 | ForEach-Object -Process {$_/1024}
```

```Output
29.296875
55.466796875
12.140625
```

### <span data-ttu-id="e08cd-130">Exemplo 2: obter o comprimento de todos os arquivos em um diretório</span><span class="sxs-lookup"><span data-stu-id="e08cd-130">Example 2: Get the length of all the files in a directory</span></span>

<span data-ttu-id="e08cd-131">Este exemplo processa os arquivos e diretórios no diretório de instalação do PowerShell `$PSHOME` .</span><span class="sxs-lookup"><span data-stu-id="e08cd-131">This example processes the files and directories in the PowerShell installation directory `$PSHOME`.</span></span>

```powershell
Get-ChildItem $PSHOME |
  ForEach-Object -Process {if (!$_.PSIsContainer) {$_.Name; $_.Length / 1024; " " }}
```

<span data-ttu-id="e08cd-132">Se o objeto não for um diretório, o bloco de script obterá o nome do arquivo, dividirá o valor de sua propriedade **Length** por 1024 e adicionará um espaço ("") para separá-lo da próxima entrada.</span><span class="sxs-lookup"><span data-stu-id="e08cd-132">If the object is not a directory, the script block gets the name of the file, divides the value of its **Length** property by 1024, and adds a space (" ") to separate it from the next entry.</span></span> <span data-ttu-id="e08cd-133">O cmdlet usa a propriedade **PSISContainer** para determinar se um objeto é um diretório.</span><span class="sxs-lookup"><span data-stu-id="e08cd-133">The cmdlet uses the **PSISContainer** property to determine whether an object is a directory.</span></span>

### <span data-ttu-id="e08cd-134">Exemplo 3: operar nos eventos do sistema mais recentes</span><span class="sxs-lookup"><span data-stu-id="e08cd-134">Example 3: Operate on the most recent System events</span></span>

<span data-ttu-id="e08cd-135">Este exemplo grava os 1000 eventos mais recentes do log de eventos do sistema em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e08cd-135">This example write the 1000 most recent events from the System event log to a text file.</span></span> <span data-ttu-id="e08cd-136">A hora atual é exibida antes e depois do processamento dos eventos.</span><span class="sxs-lookup"><span data-stu-id="e08cd-136">The current time is displayed before and after processing the events.</span></span>

```powershell
$Events = Get-EventLog -LogName System -Newest 1000
$events | ForEach-Object -Begin {Get-Date} -Process {Out-File -FilePath Events.txt -Append -InputObject $_.Message} -End {Get-Date}
```

<span data-ttu-id="e08cd-137">`Get-EventLog` Obtém os 1000 eventos mais recentes do log de eventos do sistema e os armazena na `$Events` variável.</span><span class="sxs-lookup"><span data-stu-id="e08cd-137">`Get-EventLog` gets the 1000 most recent events from the System event log and stores them in the `$Events` variable.</span></span> <span data-ttu-id="e08cd-138">`$Events` é então canalizado para o `ForEach-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e08cd-138">`$Events` is then piped to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="e08cd-139">O parâmetro **Begin** exibe a data e hora atuais.</span><span class="sxs-lookup"><span data-stu-id="e08cd-139">The **Begin** parameter displays the current date and time.</span></span> <span data-ttu-id="e08cd-140">Em seguida, o parâmetro **process** usa o `Out-File` cmdlet para criar um arquivo de texto chamado events.txt e armazena a propriedade Message de cada um dos eventos nesse arquivo.</span><span class="sxs-lookup"><span data-stu-id="e08cd-140">Next, the **Process** parameter uses the `Out-File` cmdlet to create a text file that is named events.txt and stores the message property of each of the events in that file.</span></span> <span data-ttu-id="e08cd-141">Por fim, o parâmetro **End** é usado para exibir a data e hora após todo o processamento ter sido concluído.</span><span class="sxs-lookup"><span data-stu-id="e08cd-141">Last, the **End** parameter is used to display the date and time after all of the processing has completed.</span></span>

### <span data-ttu-id="e08cd-142">Exemplo 4: alterar o valor de uma chave do registro</span><span class="sxs-lookup"><span data-stu-id="e08cd-142">Example 4: Change the value of a Registry key</span></span>

<span data-ttu-id="e08cd-143">Este exemplo altera o valor da entrada do registro **RemotePath** em todas as subchaves sob a `HKCU:\Network` chave para texto em maiúsculas.</span><span class="sxs-lookup"><span data-stu-id="e08cd-143">This example changes the value of the **RemotePath** registry entry in all of the subkeys under the `HKCU:\Network` key to uppercase text.</span></span>

```powershell
Get-ItemProperty -Path HKCU:\Network\* |
  ForEach-Object {Set-ItemProperty -Path $_.PSPath -Name RemotePath -Value $_.RemotePath.ToUpper();}
```

<span data-ttu-id="e08cd-144">Você pode usar esse formato para alterar a forma ou o conteúdo de um valor de entrada de registro.</span><span class="sxs-lookup"><span data-stu-id="e08cd-144">You can use this format to change the form or content of a registry entry value.</span></span>

<span data-ttu-id="e08cd-145">Cada subchave da chave **Network** representa uma unidade de rede mapeada que será reconectada ao efetuar logon.</span><span class="sxs-lookup"><span data-stu-id="e08cd-145">Each subkey in the **Network** key represents a mapped network drive that will reconnect at logon.</span></span>
<span data-ttu-id="e08cd-146">A entrada **RemotePath** contém o caminho UNC da unidade conectada.</span><span class="sxs-lookup"><span data-stu-id="e08cd-146">The **RemotePath** entry contains the UNC path of the connected drive.</span></span> <span data-ttu-id="e08cd-147">Por exemplo, se você mapear a unidade E: para `\\Server\Share` , haverá uma subchave **e** `HKCU:\Network` o valor da entrada do registro **RemotePath** na subchave **E** será `\\Server\Share` .</span><span class="sxs-lookup"><span data-stu-id="e08cd-147">For example, if you map the E: drive to `\\Server\Share`, there will be an **E** subkey of `HKCU:\Network` and the value of the **RemotePath** registry entry in the **E** subkey is `\\Server\Share`.</span></span>

<span data-ttu-id="e08cd-148">O comando usa o `Get-ItemProperty` cmdlet para obter todas as subchaves da chave de **rede** e o `Set-ItemProperty` cmdlet para alterar o valor da entrada do registro **RemotePath** em cada chave.</span><span class="sxs-lookup"><span data-stu-id="e08cd-148">The command uses the `Get-ItemProperty` cmdlet to get all of the subkeys of the **Network** key and the `Set-ItemProperty` cmdlet to change the value of the **RemotePath** registry entry in each key.</span></span>
<span data-ttu-id="e08cd-149">No `Set-ItemProperty` comando, o caminho é o valor da propriedade **PSPath** da chave do registro.</span><span class="sxs-lookup"><span data-stu-id="e08cd-149">In the `Set-ItemProperty` command, the path is the value of the **PSPath** property of the registry key.</span></span> <span data-ttu-id="e08cd-150">Essa é uma propriedade do objeto Microsoft .NET Framework que representa a chave do registro, não uma entrada do registro.</span><span class="sxs-lookup"><span data-stu-id="e08cd-150">This is a property of the Microsoft .NET Framework object that represents the registry key, not a registry entry.</span></span> <span data-ttu-id="e08cd-151">O comando usa o método **ToUpper ()** do valor **RemotePath** , que é uma cadeia de caracteres (REG_SZ).</span><span class="sxs-lookup"><span data-stu-id="e08cd-151">The command uses the **ToUpper()** method of the **RemotePath** value, which is a string (REG_SZ).</span></span>

<span data-ttu-id="e08cd-152">Como o `Set-ItemProperty` está alterando a propriedade de cada chave, o `ForEach-Object` cmdlet é necessário para acessar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="e08cd-152">Because `Set-ItemProperty` is changing the property of each key, the `ForEach-Object` cmdlet is required to access the property.</span></span>

### <span data-ttu-id="e08cd-153">Exemplo 5: usar a $Null variável automática</span><span class="sxs-lookup"><span data-stu-id="e08cd-153">Example 5: Use the $Null automatic variable</span></span>

<span data-ttu-id="e08cd-154">Este exemplo mostra o efeito de canalizar a `$Null` variável automática para o `ForEach-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e08cd-154">This example shows the effect of piping the `$Null` automatic variable to the `ForEach-Object` cmdlet.</span></span>

```powershell
1, 2, $null, 4 | ForEach-Object {"Hello"}
```

```Output
Hello
Hello
Hello
Hello
```

<span data-ttu-id="e08cd-155">Como o PowerShell trata nulo como um espaço reservado explícito, o `ForEach-Object` cmdlet gera um valor para `$Null` , assim como faz para outros objetos que você canaliza para ele.</span><span class="sxs-lookup"><span data-stu-id="e08cd-155">Because PowerShell treats null as an explicit placeholder, the `ForEach-Object` cmdlet generates a value for `$Null`, just as it does for other objects that you pipe to it.</span></span>

### <span data-ttu-id="e08cd-156">Exemplo 6: obter valores de propriedade</span><span class="sxs-lookup"><span data-stu-id="e08cd-156">Example 6: Get property values</span></span>

<span data-ttu-id="e08cd-157">Este exemplo obtém o valor da propriedade **path** de todos os módulos do PowerShell instalados usando o parâmetro **MemberName** do `ForEach-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e08cd-157">This example gets the value of the **Path** property of all installed PowerShell modules by using the **MemberName** parameter of the `ForEach-Object` cmdlet.</span></span>

```powershell
Get-Module -ListAvailable | ForEach-Object -MemberName Path
Get-Module -ListAvailable | Foreach Path
```

<span data-ttu-id="e08cd-158">O segundo comando é equivalente ao primeiro.</span><span class="sxs-lookup"><span data-stu-id="e08cd-158">The second command is equivalent to the first.</span></span> <span data-ttu-id="e08cd-159">Ele usa o `Foreach` alias do `ForEach-Object` cmdlet e omite o nome do parâmetro **MemberName** , que é opcional.</span><span class="sxs-lookup"><span data-stu-id="e08cd-159">It uses the `Foreach` alias of the `ForEach-Object` cmdlet and omits the name of the **MemberName** parameter, which is optional.</span></span>

<span data-ttu-id="e08cd-160">O `ForEach-Object` cmdlet é muito útil para obter valores de propriedade, pois Obtém o valor sem alterar o tipo, diferentemente dos cmdlets **Format** ou do `Select-Object` cmdlet, que alteram o tipo de valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="e08cd-160">The `ForEach-Object` cmdlet is very useful for getting property values, because it gets the value without changing the type, unlike the **Format** cmdlets or the `Select-Object` cmdlet, which change the property value type.</span></span>

### <span data-ttu-id="e08cd-161">Exemplo 7: dividir nomes de módulo em nomes de componentes</span><span class="sxs-lookup"><span data-stu-id="e08cd-161">Example 7: Split module names into component names</span></span>

<span data-ttu-id="e08cd-162">Este exemplo mostra três maneiras de dividir dois nomes de módulo separados por ponto em seus nomes de componentes.</span><span class="sxs-lookup"><span data-stu-id="e08cd-162">This examples shows three ways to split two dot-separated module names into their component names.</span></span>

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

<span data-ttu-id="e08cd-163">Os comandos chamam o método de cadeias de caracteres **Split** .</span><span class="sxs-lookup"><span data-stu-id="e08cd-163">The commands call the **Split** method of strings.</span></span> <span data-ttu-id="e08cd-164">Os três comandos usam uma sintaxe diferente, mas são equivalentes e intercambiáveis.</span><span class="sxs-lookup"><span data-stu-id="e08cd-164">The three commands use different syntax, but they are equivalent and interchangeable.</span></span>

<span data-ttu-id="e08cd-165">O primeiro comando usa a sintaxe tradicional, que inclui um bloco de script e o operador de objeto atual `$_` .</span><span class="sxs-lookup"><span data-stu-id="e08cd-165">The first command uses the traditional syntax, which includes a script block and the current object operator `$_`.</span></span> <span data-ttu-id="e08cd-166">Ele usa a sintaxe de ponto para especificar o método e parênteses para incluir o argumento delimitador.</span><span class="sxs-lookup"><span data-stu-id="e08cd-166">It uses the dot syntax to specify the method and parentheses to enclose the delimiter argument.</span></span>

<span data-ttu-id="e08cd-167">O segundo comando usa o parâmetro **MemberName** para especificar o método **Split** e o parâmetro **ArgumentName** para identificar o ponto (".") como o delimitador de divisão.</span><span class="sxs-lookup"><span data-stu-id="e08cd-167">The second command uses the **MemberName** parameter to specify the **Split** method and the **ArgumentName** parameter to identify the dot (".") as the split delimiter.</span></span>

<span data-ttu-id="e08cd-168">O terceiro comando usa o alias **foreach** do `ForEach-Object` cmdlet e omite os nomes dos parâmetros **MemberName** e **ArgumentList** , que são opcionais.</span><span class="sxs-lookup"><span data-stu-id="e08cd-168">The third command uses the **Foreach** alias of the `ForEach-Object` cmdlet and omits the names of the **MemberName** and **ArgumentList** parameters, which are optional.</span></span>

### <span data-ttu-id="e08cd-169">Exemplo 8: usando ForEach-Object com dois blocos de script</span><span class="sxs-lookup"><span data-stu-id="e08cd-169">Example 8: Using ForEach-Object with two script blocks</span></span>

<span data-ttu-id="e08cd-170">Neste exemplo, passamos dois blocos de script de posição.</span><span class="sxs-lookup"><span data-stu-id="e08cd-170">In this example we pass two script blocks positionally.</span></span> <span data-ttu-id="e08cd-171">Todos os blocos de script são associados ao parâmetro de **processo** .</span><span class="sxs-lookup"><span data-stu-id="e08cd-171">All the script blocks bind to the **Process** parameter.</span></span> <span data-ttu-id="e08cd-172">No entanto, eles são tratados como se tivessem sido passados para os parâmetros **begin** e **process** .</span><span class="sxs-lookup"><span data-stu-id="e08cd-172">However, they are treated as if they had been passed to the **Begin** and **Process** parameters.</span></span>

```powershell
1..2 | ForEach-Object { 'begin' } { 'process' }
```

```Output
begin
process
process
```

### <span data-ttu-id="e08cd-173">Exemplo 9: usando ForEach-Object com mais de dois blocos de script</span><span class="sxs-lookup"><span data-stu-id="e08cd-173">Example 9: Using ForEach-Object with more than two script blocks</span></span>

<span data-ttu-id="e08cd-174">Neste exemplo, passamos dois blocos de script de posição.</span><span class="sxs-lookup"><span data-stu-id="e08cd-174">In this example we pass two script blocks positionally.</span></span> <span data-ttu-id="e08cd-175">Todos os blocos de script são associados ao parâmetro de **processo** .</span><span class="sxs-lookup"><span data-stu-id="e08cd-175">All the script blocks bind to the **Process** parameter.</span></span> <span data-ttu-id="e08cd-176">No entanto, eles são tratados como se tivessem sido passados para os parâmetros **begin** , **process** e **end** .</span><span class="sxs-lookup"><span data-stu-id="e08cd-176">However, they are treated as if they had been passed to the **Begin** , **Process** , and **End** parameters.</span></span>

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
> <span data-ttu-id="e08cd-177">O primeiro bloco de script é sempre mapeado para o `begin` bloco, o último bloco é mapeado para o `end` bloco e os blocos no between são todos mapeados para o `process` bloco.</span><span class="sxs-lookup"><span data-stu-id="e08cd-177">The first script block is always mapped to the `begin` block, the last block is mapped to the `end` block, and the blocks in between are all mapped to the `process` block.</span></span>

### <span data-ttu-id="e08cd-178">Exemplo 10: executar vários blocos de script para cada item de pipeline</span><span class="sxs-lookup"><span data-stu-id="e08cd-178">Example 10: Run multiple script blocks for each pipeline item</span></span>

<span data-ttu-id="e08cd-179">Conforme mostrado no exemplo anterior, vários blocos de script passados usando o parâmetro **process** são mapeados para os parâmetros **begin** e **end** .</span><span class="sxs-lookup"><span data-stu-id="e08cd-179">As shown in the previous example, multiple script blocks passed using the **Process** parameter get mapped to the **Begin** and **End** parameters.</span></span> <span data-ttu-id="e08cd-180">Para evitar esse mapeamento, você deve fornecer valores explícitos para os parâmetros de **início** e **término** .</span><span class="sxs-lookup"><span data-stu-id="e08cd-180">To avoid this mapping, you must provide explicit values for the **Begin** and **End** parameters.</span></span>

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

## <span data-ttu-id="e08cd-181">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e08cd-181">Parameters</span></span>

### <span data-ttu-id="e08cd-182">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="e08cd-182">-ArgumentList</span></span>

<span data-ttu-id="e08cd-183">Especifica uma matriz de argumentos para uma chamada de método.</span><span class="sxs-lookup"><span data-stu-id="e08cd-183">Specifies an array of arguments to a method call.</span></span> <span data-ttu-id="e08cd-184">Para obter mais informações sobre o comportamento de **ArgumentList** , consulte [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="e08cd-184">For more information about the behavior of **ArgumentList** , see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

<span data-ttu-id="e08cd-185">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="e08cd-185">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="e08cd-186">-Início</span><span class="sxs-lookup"><span data-stu-id="e08cd-186">-Begin</span></span>

<span data-ttu-id="e08cd-187">Especifica um bloco de script que é executado antes desse cmdlet processar qualquer objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="e08cd-187">Specifies a script block that runs before this cmdlet processes any input objects.</span></span> <span data-ttu-id="e08cd-188">Esse bloco de script só é executado uma vez para o pipeline inteiro.</span><span class="sxs-lookup"><span data-stu-id="e08cd-188">This script block is only run once for the entire pipeline.</span></span> <span data-ttu-id="e08cd-189">Para obter mais informações sobre o `begin` bloco, consulte [about_Functions](about/about_functions.md#piping-objects-to-functions).</span><span class="sxs-lookup"><span data-stu-id="e08cd-189">For more information about the `begin` block, see [about_Functions](about/about_functions.md#piping-objects-to-functions).</span></span>

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

### <span data-ttu-id="e08cd-190">-Fim</span><span class="sxs-lookup"><span data-stu-id="e08cd-190">-End</span></span>

<span data-ttu-id="e08cd-191">Especifica um bloco de script que é executado depois que esse cmdlet processa todos os objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="e08cd-191">Specifies a script block that runs after this cmdlet processes all input objects.</span></span> <span data-ttu-id="e08cd-192">Esse bloco de script só é executado uma vez para o pipeline inteiro.</span><span class="sxs-lookup"><span data-stu-id="e08cd-192">This script block is only run once for the entire pipeline.</span></span> <span data-ttu-id="e08cd-193">Para obter mais informações sobre o `end` bloco, consulte [about_Functions](about/about_functions.md#piping-objects-to-functions).</span><span class="sxs-lookup"><span data-stu-id="e08cd-193">For more information about the `end` block, see [about_Functions](about/about_functions.md#piping-objects-to-functions).</span></span>

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

### <span data-ttu-id="e08cd-194">-InputObject</span><span class="sxs-lookup"><span data-stu-id="e08cd-194">-InputObject</span></span>

<span data-ttu-id="e08cd-195">Especifica os objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="e08cd-195">Specifies the input objects.</span></span> <span data-ttu-id="e08cd-196">`ForEach-Object` executa o bloco de script ou a instrução de operação em cada objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="e08cd-196">`ForEach-Object` runs the script block or operation statement on each input object.</span></span> <span data-ttu-id="e08cd-197">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="e08cd-197">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="e08cd-198">Quando você usa o parâmetro **InputObject** com `ForEach-Object` , em vez de direcionar os resultados de comando para `ForEach-Object` , o valor **InputObject** é tratado como um único objeto.</span><span class="sxs-lookup"><span data-stu-id="e08cd-198">When you use the **InputObject** parameter with `ForEach-Object`, instead of piping command results to `ForEach-Object`, the **InputObject** value is treated as a single object.</span></span> <span data-ttu-id="e08cd-199">Isso é verdadeiro mesmo se o valor for uma coleção que é o resultado de um comando, como `-InputObject (Get-Process)` .</span><span class="sxs-lookup"><span data-stu-id="e08cd-199">This is true even if the value is a collection that is the result of a command, such as `-InputObject (Get-Process)`.</span></span>
<span data-ttu-id="e08cd-200">Como **InputObject** não pode retornar propriedades individuais de uma matriz ou coleção de objetos, recomendamos que, se você usar `ForEach-Object` o para executar operações em uma coleção de objetos para os objetos que têm valores específicos nas propriedades definidas, use `ForEach-Object` no pipeline, conforme mostrado nos exemplos neste tópico.</span><span class="sxs-lookup"><span data-stu-id="e08cd-200">Because **InputObject** cannot return individual properties from an array or collection of objects, we recommend that if you use `ForEach-Object` to perform operations on a collection of objects for those objects that have specific values in defined properties, you use `ForEach-Object` in the pipeline, as shown in the examples in this topic.</span></span>

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

### <span data-ttu-id="e08cd-201">-MemberName</span><span class="sxs-lookup"><span data-stu-id="e08cd-201">-MemberName</span></span>

<span data-ttu-id="e08cd-202">Especifica a propriedade a ser obtida ou o método a ser chamado.</span><span class="sxs-lookup"><span data-stu-id="e08cd-202">Specifies the property to get or the method to call.</span></span>

<span data-ttu-id="e08cd-203">Caracteres curinga são permitidos, mas só funcionam se a cadeia de caracteres resultante for resolvida para um valor exclusivo.</span><span class="sxs-lookup"><span data-stu-id="e08cd-203">Wildcard characters are permitted, but work only if the resulting string resolves to a unique value.</span></span>
<span data-ttu-id="e08cd-204">Se, por exemplo, você executar `Get-Process | ForEach -MemberName *Name` e houver mais de um membro com um nome que contenha o nome da cadeia de caracteres, como as propriedades **ProcessName** e **Name** , o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="e08cd-204">If, for example, you run `Get-Process | ForEach -MemberName *Name`, and more than one member exists with a name that contains the string Name, such as the **ProcessName** and **Name** properties, the command fails.</span></span>

<span data-ttu-id="e08cd-205">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="e08cd-205">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="e08cd-206">-Processo</span><span class="sxs-lookup"><span data-stu-id="e08cd-206">-Process</span></span>

<span data-ttu-id="e08cd-207">Especifica a operação que é executada em cada objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="e08cd-207">Specifies the operation that is performed on each input object.</span></span> <span data-ttu-id="e08cd-208">Esse bloco de script é executado para cada objeto no pipeline.</span><span class="sxs-lookup"><span data-stu-id="e08cd-208">This script block is run for every object in the pipeline.</span></span> <span data-ttu-id="e08cd-209">Para obter mais informações sobre o `process` bloco, consulte [about_Functions](about/about_functions.md#piping-objects-to-functions).</span><span class="sxs-lookup"><span data-stu-id="e08cd-209">For more information about the `process` block, see [about_Functions](about/about_functions.md#piping-objects-to-functions).</span></span>

<span data-ttu-id="e08cd-210">Quando você fornece vários blocos de script para o parâmetro **process** , o primeiro bloco de script é sempre mapeado para o `begin` bloco.</span><span class="sxs-lookup"><span data-stu-id="e08cd-210">When you provide multiple script blocks to the **Process** parameter, the first script block is always mapped to the `begin` block.</span></span> <span data-ttu-id="e08cd-211">Se houver apenas dois blocos de script, o segundo bloco será mapeado para o `process` bloco.</span><span class="sxs-lookup"><span data-stu-id="e08cd-211">If there are only two script blocks, the second block is mapped to the `process` block.</span></span> <span data-ttu-id="e08cd-212">Se houver três ou mais blocos de script, o primeiro bloco de script será sempre mapeado para o `begin` bloco, o último bloco será mapeado para o `end` bloco e os blocos no between serão todos mapeados para o `process` bloco.</span><span class="sxs-lookup"><span data-stu-id="e08cd-212">If there are three or more script blocks, first script block is always mapped to the `begin` block, the last block is mapped to the `end` block, and the blocks in between are all mapped to the `process` block.</span></span>

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

### <span data-ttu-id="e08cd-213">-RemainingScripts</span><span class="sxs-lookup"><span data-stu-id="e08cd-213">-RemainingScripts</span></span>

<span data-ttu-id="e08cd-214">Especifica todos os blocos de script que não são usados pelo parâmetro **process** .</span><span class="sxs-lookup"><span data-stu-id="e08cd-214">Specifies all script blocks that are not taken by the **Process** parameter.</span></span>

<span data-ttu-id="e08cd-215">Este parâmetro foi introduzido no Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="e08cd-215">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="e08cd-216">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e08cd-216">-Confirm</span></span>

<span data-ttu-id="e08cd-217">Solicita sua confirmação antes de executar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e08cd-217">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e08cd-218">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e08cd-218">-WhatIf</span></span>

<span data-ttu-id="e08cd-219">Mostra o que aconteceria se o cmdlet fosse executado.</span><span class="sxs-lookup"><span data-stu-id="e08cd-219">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="e08cd-220">O cmdlet não é executado.</span><span class="sxs-lookup"><span data-stu-id="e08cd-220">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e08cd-221">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e08cd-221">CommonParameters</span></span>

<span data-ttu-id="e08cd-222">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e08cd-222">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e08cd-223">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e08cd-223">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e08cd-224">Entradas</span><span class="sxs-lookup"><span data-stu-id="e08cd-224">Inputs</span></span>

### <span data-ttu-id="e08cd-225">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="e08cd-225">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="e08cd-226">É possível canalizar qualquer objeto para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e08cd-226">You can pipe any object to this cmdlet.</span></span>

## <span data-ttu-id="e08cd-227">Saídas</span><span class="sxs-lookup"><span data-stu-id="e08cd-227">Outputs</span></span>

### <span data-ttu-id="e08cd-228">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="e08cd-228">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="e08cd-229">Esse cmdlet retorna objetos que são determinados pela entrada.</span><span class="sxs-lookup"><span data-stu-id="e08cd-229">This cmdlet returns objects that are determined by the input.</span></span>

## <span data-ttu-id="e08cd-230">Observações</span><span class="sxs-lookup"><span data-stu-id="e08cd-230">Notes</span></span>

- <span data-ttu-id="e08cd-231">O `ForEach-Object` cmdlet funciona de forma muito parecida com a instrução **foreach** , exceto que não é possível canalizar a entrada para uma instrução **foreach** .</span><span class="sxs-lookup"><span data-stu-id="e08cd-231">The `ForEach-Object` cmdlet works much like the **Foreach** statement, except that you cannot pipe input to a **Foreach** statement.</span></span> <span data-ttu-id="e08cd-232">Para obter mais informações sobre a instrução **foreach** , consulte [about_Foreach](./About/about_Foreach.md).</span><span class="sxs-lookup"><span data-stu-id="e08cd-232">For more information about the **Foreach** statement, see [about_Foreach](./About/about_Foreach.md).</span></span>

- <span data-ttu-id="e08cd-233">A partir do PowerShell 4,0, `Where` e os `ForEach` métodos foram adicionados para uso com coleções.</span><span class="sxs-lookup"><span data-stu-id="e08cd-233">Starting in PowerShell 4.0, `Where` and `ForEach` methods were added for use with collections.</span></span> <span data-ttu-id="e08cd-234">Você pode ler mais sobre esses novos métodos aqui [about_arrays](./About/about_Arrays.md)</span><span class="sxs-lookup"><span data-stu-id="e08cd-234">You can read more about these new methods here [about_arrays](./About/about_Arrays.md)</span></span>

## <span data-ttu-id="e08cd-235">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="e08cd-235">Related links</span></span>

[<span data-ttu-id="e08cd-236">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="e08cd-236">Compare-Object</span></span>](../Microsoft.PowerShell.Utility/Compare-Object.md)

[<span data-ttu-id="e08cd-237">Where-Object</span><span class="sxs-lookup"><span data-stu-id="e08cd-237">Where-Object</span></span>](Where-Object.md)

[<span data-ttu-id="e08cd-238">Group-Object</span><span class="sxs-lookup"><span data-stu-id="e08cd-238">Group-Object</span></span>](../Microsoft.PowerShell.Utility/Group-Object.md)

[<span data-ttu-id="e08cd-239">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="e08cd-239">Measure-Object</span></span>](../Microsoft.PowerShell.Utility/Measure-Object.md)

[<span data-ttu-id="e08cd-240">New-Object</span><span class="sxs-lookup"><span data-stu-id="e08cd-240">New-Object</span></span>](../Microsoft.PowerShell.Utility/New-Object.md)

[<span data-ttu-id="e08cd-241">Select-Object</span><span class="sxs-lookup"><span data-stu-id="e08cd-241">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="e08cd-242">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="e08cd-242">Sort-Object</span></span>](../Microsoft.PowerShell.Utility/Sort-Object.md)

[<span data-ttu-id="e08cd-243">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="e08cd-243">Tee-Object</span></span>](../Microsoft.PowerShell.Utility/Tee-Object.md)
