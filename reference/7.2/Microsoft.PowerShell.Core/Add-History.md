---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/add-history?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-History
ms.openlocfilehash: d2c0abb0e6742de3e316fe964d5945375591ef4d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603334"
---
# <span data-ttu-id="3a19f-102">Add-History</span><span class="sxs-lookup"><span data-stu-id="3a19f-102">Add-History</span></span>

## <span data-ttu-id="3a19f-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="3a19f-103">SYNOPSIS</span></span>
<span data-ttu-id="3a19f-104">Acrescenta as entradas ao histórico de sessão.</span><span class="sxs-lookup"><span data-stu-id="3a19f-104">Appends entries to the session history.</span></span>

## <span data-ttu-id="3a19f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3a19f-105">SYNTAX</span></span>

```
Add-History [[-InputObject] <PSObject[]>] [-Passthru] [<CommonParameters>]
```

## <span data-ttu-id="3a19f-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3a19f-106">DESCRIPTION</span></span>

<span data-ttu-id="3a19f-107">O `Add-History` cmdlet adiciona entradas ao final do histórico da sessão, ou seja, a lista de comandos inseridos durante a sessão atual.</span><span class="sxs-lookup"><span data-stu-id="3a19f-107">The `Add-History` cmdlet adds entries to the end of the session history, that is, the list of commands entered during the current session.</span></span>

<span data-ttu-id="3a19f-108">O histórico da sessão é uma lista dos comandos inseridos durante a sessão.</span><span class="sxs-lookup"><span data-stu-id="3a19f-108">The session history is a list of the commands entered during the session.</span></span> <span data-ttu-id="3a19f-109">O histórico da sessão representa a ordem de execução, o status e os horários de início e término do comando.</span><span class="sxs-lookup"><span data-stu-id="3a19f-109">The session history represents the order of execution, the status, and the start and end times of the command.</span></span> <span data-ttu-id="3a19f-110">À medida que você insere cada comando, o PowerShell o adiciona ao histórico para que você possa reutilizá-lo.</span><span class="sxs-lookup"><span data-stu-id="3a19f-110">As you enter each command, PowerShell adds it to the history so that you can reuse it.</span></span> <span data-ttu-id="3a19f-111">Para obter mais informações sobre o histórico de sessão, consulte [about_History](About/about_History.md).</span><span class="sxs-lookup"><span data-stu-id="3a19f-111">For more information about the session history, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="3a19f-112">O histórico de sessão é gerenciado separadamente do histórico mantido pelo módulo **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="3a19f-112">The session history is managed separately from the history maintained by the **PSReadLine** module.</span></span>
<span data-ttu-id="3a19f-113">Ambos os históricos estão disponíveis em sessões em que **PSReadLine** é carregado.</span><span class="sxs-lookup"><span data-stu-id="3a19f-113">Both histories are available in sessions where **PSReadLine** is loaded.</span></span> <span data-ttu-id="3a19f-114">Esse cmdlet funciona apenas com o histórico de sessão.</span><span class="sxs-lookup"><span data-stu-id="3a19f-114">This cmdlet only works with the session history.</span></span> <span data-ttu-id="3a19f-115">Para obter mais informações, consulte [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span><span class="sxs-lookup"><span data-stu-id="3a19f-115">For more information see, [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span></span>

<span data-ttu-id="3a19f-116">Você pode usar o `Get-History` cmdlet para obter os comandos e passá-los para o `Add-History` , ou pode exportar os comandos para um arquivo CSV ou XML, depois importar os comandos e passar o arquivo importado para o `Add-History` .</span><span class="sxs-lookup"><span data-stu-id="3a19f-116">You can use the `Get-History` cmdlet to get the commands and pass them to `Add-History`, or you can export the commands to a CSV or XML file, then import the commands, and pass the imported file to `Add-History`.</span></span> <span data-ttu-id="3a19f-117">Você pode usar este cmdlet para adicionar comandos específicos ao histórico ou para criar um arquivo de histórico único que inclui comandos de mais de uma sessão.</span><span class="sxs-lookup"><span data-stu-id="3a19f-117">You can use this cmdlet to add specific commands to the history or to create a single history file that includes commands from more than one session.</span></span>

## <span data-ttu-id="3a19f-118">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="3a19f-118">EXAMPLES</span></span>

### <span data-ttu-id="3a19f-119">Exemplo 1: adicionar comandos ao histórico de uma sessão diferente</span><span class="sxs-lookup"><span data-stu-id="3a19f-119">Example 1: Add commands to the history of a different session</span></span>

<span data-ttu-id="3a19f-120">Este exemplo adiciona os comandos digitados em uma sessão do PowerShell ao histórico de uma sessão diferente do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3a19f-120">This example add the commands typed in one PowerShell session to the history of a different PowerShell session.</span></span>

```powershell
Get-History | Export-Csv c:\testing\history.csv -IncludeTypeInformation
Import-Csv c:\testing\history.csv | Add-History
```

<span data-ttu-id="3a19f-121">O primeiro comando obtém os objetos que representam os comandos no histórico e exporta-os para o `History.csv` arquivo.</span><span class="sxs-lookup"><span data-stu-id="3a19f-121">The first command gets objects representing the commands in the history and exports them to the `History.csv` file.</span></span>

<span data-ttu-id="3a19f-122">O segundo comando é digitado na linha de comando de uma sessão diferente.</span><span class="sxs-lookup"><span data-stu-id="3a19f-122">The second command is typed at the command line of a different session.</span></span> <span data-ttu-id="3a19f-123">Ele usa o `Import-Csv` cmdlet para importar os objetos no `History.csv` arquivo.</span><span class="sxs-lookup"><span data-stu-id="3a19f-123">It uses the `Import-Csv` cmdlet to import the objects in the `History.csv` file.</span></span> <span data-ttu-id="3a19f-124">O operador de pipeline ( `|` ) passa os objetos para o `Add-History` cmdlet, que adiciona os objetos que representam os comandos do `History.csv` arquivo ao histórico de sessão atual.</span><span class="sxs-lookup"><span data-stu-id="3a19f-124">The pipeline operator (`|`) passes the objects to the `Add-History` cmdlet, which adds the objects representing the commands in the `History.csv` file to the current session history.</span></span>

### <span data-ttu-id="3a19f-125">Exemplo 2: importar e executar comandos</span><span class="sxs-lookup"><span data-stu-id="3a19f-125">Example 2: Import and run commands</span></span>

<span data-ttu-id="3a19f-126">Este exemplo importa comandos do `History.xml` arquivo, adiciona-os ao histórico de sessão atual e, em seguida, executa os comandos no histórico combinado.</span><span class="sxs-lookup"><span data-stu-id="3a19f-126">This example imports commands from the `History.xml` file, adds them to the current session history, and then runs the commands in the combined history.</span></span>

```powershell
Import-Clixml c:\temp\history.xml | Add-History -PassThru | ForEach-Object -Process {Invoke-History}
```

<span data-ttu-id="3a19f-127">O primeiro comando usa o `Import-Clixml` cmdlet para importar um histórico de comandos que foi exportado para o `History.xml` arquivo.</span><span class="sxs-lookup"><span data-stu-id="3a19f-127">The first command uses the `Import-Clixml` cmdlet to import a command history that was exported to the `History.xml` file.</span></span> <span data-ttu-id="3a19f-128">O operador de pipeline passa os comandos para o `Add-History` cmdlet, que adiciona os comandos ao histórico de sessão atual.</span><span class="sxs-lookup"><span data-stu-id="3a19f-128">The pipeline operator passes the commands to the `Add-History` cmdlet, which adds the commands to the current session history.</span></span> <span data-ttu-id="3a19f-129">O parâmetro **PassThru** passa os objetos que representam os comandos adicionados por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="3a19f-129">The **PassThru** parameter passes the objects representing the added commands down the pipeline.</span></span>

<span data-ttu-id="3a19f-130">O comando usa o `ForEach-Object` cmdlet para aplicar o `Invoke-History` comando a cada um dos comandos no histórico combinado.</span><span class="sxs-lookup"><span data-stu-id="3a19f-130">The command then uses the `ForEach-Object` cmdlet to apply the `Invoke-History` command to each of the commands in the combined history.</span></span> <span data-ttu-id="3a19f-131">O `Invoke-History` comando é formatado como um bloco de script, entre chaves ( `{}` ), conforme exigido pelo parâmetro **process** do `ForEach-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3a19f-131">The `Invoke-History` command is formatted as a script block, enclosed in braces (`{}`), as required by the **Process** parameter of the `ForEach-Object` cmdlet.</span></span>

### <span data-ttu-id="3a19f-132">Exemplo 3: adicionar comandos no histórico ao final do histórico</span><span class="sxs-lookup"><span data-stu-id="3a19f-132">Example 3: Add commands in the history to the end of the history</span></span>

<span data-ttu-id="3a19f-133">Este exemplo adiciona os primeiros cinco comandos no histórico ao final da lista de histórico.</span><span class="sxs-lookup"><span data-stu-id="3a19f-133">This example adds the first five commands in the history to the end of the history list.</span></span>

```powershell
Get-History -Id 5 -Count 5 | Add-History
```

<span data-ttu-id="3a19f-134">O `Get-History` cmdlet obtém os cinco comandos que terminam no comando 5.</span><span class="sxs-lookup"><span data-stu-id="3a19f-134">The `Get-History` cmdlet gets the five commands ending in command 5.</span></span> <span data-ttu-id="3a19f-135">O operador de pipeline transmite-os para o `Add-History` cmdlet, que os anexa ao histórico atual.</span><span class="sxs-lookup"><span data-stu-id="3a19f-135">The pipeline operator passes them to the `Add-History` cmdlet, which appends them to the current history.</span></span> <span data-ttu-id="3a19f-136">O `Add-History` comando não inclui nenhum parâmetro, mas o PowerShell associa os objetos passados pelo pipeline com o parâmetro **InputObject** de `Add-History` .</span><span class="sxs-lookup"><span data-stu-id="3a19f-136">The `Add-History` command does not include any parameters, but PowerShell associates the objects passed through the pipeline with the **InputObject** parameter of `Add-History`.</span></span>

### <span data-ttu-id="3a19f-137">Exemplo 4: adicionar comandos em um arquivo. csv ao histórico atual</span><span class="sxs-lookup"><span data-stu-id="3a19f-137">Example 4: Add commands in a .csv file to the current history</span></span>

<span data-ttu-id="3a19f-138">Este exemplo adiciona os comandos no `History.csv` arquivo ao histórico de sessão atual.</span><span class="sxs-lookup"><span data-stu-id="3a19f-138">This example add the commands in the `History.csv` file to the current session history.</span></span>

```powershell
$a = Import-Csv c:\testing\history.csv
Add-History -InputObject $a -PassThru
```

<span data-ttu-id="3a19f-139">O `Import-Csv` cmdlet importa os comandos no `History.csv` arquivo e armazena seu conteúdo na variável `$a` .</span><span class="sxs-lookup"><span data-stu-id="3a19f-139">The `Import-Csv` cmdlet imports the commands in the `History.csv` file and store its contents in the variable `$a`.</span></span>

<span data-ttu-id="3a19f-140">O segundo comando usa o `Add-History` cmdlet para adicionar os comandos do `History.csv` ao histórico de sessão atual.</span><span class="sxs-lookup"><span data-stu-id="3a19f-140">The second command uses the `Add-History` cmdlet to add the commands from `History.csv` to the current session history.</span></span> <span data-ttu-id="3a19f-141">Ele usa o parâmetro **InputObject** para especificar a `$a` variável e o parâmetro **PassThru** para gerar um objeto a ser exibido na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="3a19f-141">It uses the **InputObject** parameter to specify the `$a` variable and the **PassThru** parameter to generate an object to display at the command line.</span></span> <span data-ttu-id="3a19f-142">Sem o parâmetro **PassThru** , o `Add-History` cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="3a19f-142">Without the **PassThru** parameter, the `Add-History` cmdlet does not generate any output.</span></span>

### <span data-ttu-id="3a19f-143">Exemplo 5: adicionar comandos em um arquivo. xml ao histórico atual</span><span class="sxs-lookup"><span data-stu-id="3a19f-143">Example 5: Add commands in an .xml file to the current history</span></span>

<span data-ttu-id="3a19f-144">Este exemplo adiciona os comandos no `history.xml` arquivo ao histórico de sessão atual.</span><span class="sxs-lookup"><span data-stu-id="3a19f-144">This example adds the commands in the `history.xml` file to the current session history.</span></span>

```powershell
Add-History -InputObject (Import-Clixml c:\temp\history.xml)
```

<span data-ttu-id="3a19f-145">O parâmetro **InputObject** passa os resultados do comando entre parênteses e o `Add-History` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3a19f-145">The **InputObject** parameter passes the results of the command in parentheses to the `Add-History` cmdlet.</span></span> <span data-ttu-id="3a19f-146">O comando entre parênteses, que é executado primeiro, importa o `history.xml` arquivo para o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3a19f-146">The command in parentheses, which is executed first, imports the `history.xml` file into PowerShell.</span></span> <span data-ttu-id="3a19f-147">O `Add-History` cmdlet, em seguida, adiciona os comandos no arquivo ao histórico da sessão.</span><span class="sxs-lookup"><span data-stu-id="3a19f-147">The `Add-History` cmdlet then adds the commands in the file to the session history.</span></span>

## <span data-ttu-id="3a19f-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3a19f-148">PARAMETERS</span></span>

### <span data-ttu-id="3a19f-149">-InputObject</span><span class="sxs-lookup"><span data-stu-id="3a19f-149">-InputObject</span></span>

<span data-ttu-id="3a19f-150">Especifica uma matriz de entradas a serem adicionadas ao histórico como objeto **HistoryInfo** ao histórico da sessão.</span><span class="sxs-lookup"><span data-stu-id="3a19f-150">Specifies an array of entries to add to the history as **HistoryInfo** object to the session history.</span></span>
<span data-ttu-id="3a19f-151">Você pode usar esse parâmetro para enviar um objeto **HistoryInfo** , como aqueles que são retornados pelos `Get-History` `Import-Clixml` cmdlets,, ou `Import-Csv` , para `Add-History` .</span><span class="sxs-lookup"><span data-stu-id="3a19f-151">You can use this parameter to submit a **HistoryInfo** object, such as the ones that are returned by the `Get-History`, `Import-Clixml`, or `Import-Csv` cmdlets, to `Add-History`.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="3a19f-152">-PassThru</span><span class="sxs-lookup"><span data-stu-id="3a19f-152">-Passthru</span></span>

<span data-ttu-id="3a19f-153">Indica que esse cmdlet retorna um objeto **HistoryInfo** para cada entrada de histórico.</span><span class="sxs-lookup"><span data-stu-id="3a19f-153">Indicates that this cmdlet returns a **HistoryInfo** object for each history entry.</span></span> <span data-ttu-id="3a19f-154">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="3a19f-154">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="3a19f-155">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3a19f-155">CommonParameters</span></span>

<span data-ttu-id="3a19f-156">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3a19f-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3a19f-157">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3a19f-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3a19f-158">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="3a19f-158">INPUTS</span></span>

### <span data-ttu-id="3a19f-159">Microsoft. PowerShell. Commands. HistoryInfo</span><span class="sxs-lookup"><span data-stu-id="3a19f-159">Microsoft.PowerShell.Commands.HistoryInfo</span></span>

<span data-ttu-id="3a19f-160">É possível canalizar um objeto **HistoryInfo** para esse cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3a19f-160">You can pipe a **HistoryInfo** object to this cmdlet.</span></span>

## <span data-ttu-id="3a19f-161">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="3a19f-161">OUTPUTS</span></span>

### <span data-ttu-id="3a19f-162">Nenhum ou Microsoft. PowerShell. Commands. HistoryInfo</span><span class="sxs-lookup"><span data-stu-id="3a19f-162">None or Microsoft.PowerShell.Commands.HistoryInfo</span></span>

<span data-ttu-id="3a19f-163">Esse cmdlet retornará um objeto **HistoryInfo** se você especificar o parâmetro **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="3a19f-163">This cmdlet returns a **HistoryInfo** object if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="3a19f-164">Caso contrário, este cmdlet não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="3a19f-164">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="3a19f-165">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="3a19f-165">NOTES</span></span>

<span data-ttu-id="3a19f-166">O histórico de sessão é uma lista dos comandos inseridos durante a sessão junto com a ID.</span><span class="sxs-lookup"><span data-stu-id="3a19f-166">The session history is a list of the commands entered during the session together with the ID.</span></span> <span data-ttu-id="3a19f-167">O histórico da sessão representa a ordem de execução, o status e os horários de início e término do comando.</span><span class="sxs-lookup"><span data-stu-id="3a19f-167">The session history represents the order of execution, the status, and the start and end times of the command.</span></span> <span data-ttu-id="3a19f-168">À medida que você insere cada comando, o PowerShell o adiciona ao histórico para que você possa reutilizá-lo.</span><span class="sxs-lookup"><span data-stu-id="3a19f-168">As you enter each command, PowerShell adds it to the history so that you can reuse it.</span></span> <span data-ttu-id="3a19f-169">Para obter mais informações sobre o histórico de sessão, consulte [about_History](About/about_History.md).</span><span class="sxs-lookup"><span data-stu-id="3a19f-169">For more information about the session history, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="3a19f-170">Para especificar os comandos para adicionar ao histórico, use o parâmetro **InputObject**.</span><span class="sxs-lookup"><span data-stu-id="3a19f-170">To specify the commands to add to the history, use the **InputObject** parameter.</span></span> <span data-ttu-id="3a19f-171">O `Add-History` comando aceita somente objetos **HistoryInfo** , como aqueles retornados para cada comando pelo `Get-History` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3a19f-171">The `Add-History` command accepts only **HistoryInfo** objects, such as those returned for each command by the `Get-History` cmdlet.</span></span> <span data-ttu-id="3a19f-172">Você não pode passar um caminho e nome de arquivo ou uma lista de comandos.</span><span class="sxs-lookup"><span data-stu-id="3a19f-172">You cannot pass it a path and file name or a list of commands.</span></span>

<span data-ttu-id="3a19f-173">Você pode usar o parâmetro **InputObject** para passar um arquivo de objetos **HistoryInfo** para `Add-History` .</span><span class="sxs-lookup"><span data-stu-id="3a19f-173">You can use the **InputObject** parameter to pass a file of **HistoryInfo** objects to `Add-History`.</span></span> <span data-ttu-id="3a19f-174">Para fazer isso, exporte os resultados de um `Get-History` comando para um arquivo usando o `Export-Csv` `Export-Clixml` cmdlet ou e, em seguida, importe o arquivo usando os `Import-Csv` `Import-Clixml` cmdlets ou.</span><span class="sxs-lookup"><span data-stu-id="3a19f-174">To do so, export the results of a `Get-History` command to a file by using the `Export-Csv` or `Export-Clixml` cmdlet and then import the file by using the `Import-Csv` or `Import-Clixml` cmdlets.</span></span> <span data-ttu-id="3a19f-175">Em seguida, você pode passar o arquivo de objetos **HistoryInfo** importados para `Add-History` por meio de um pipeline ou em uma variável.</span><span class="sxs-lookup"><span data-stu-id="3a19f-175">You can then pass the file of imported **HistoryInfo** objects to `Add-History` through a pipeline or in a variable.</span></span> <span data-ttu-id="3a19f-176">Para obter mais informações, consulte os exemplos.</span><span class="sxs-lookup"><span data-stu-id="3a19f-176">For more information, see the examples.</span></span>

<span data-ttu-id="3a19f-177">O arquivo de objetos **HistoryInfo** que você passa para o `Add-History` cmdlet deve incluir as informações de tipo, títulos de coluna e todas as propriedades dos objetos **HistoryInfo** .</span><span class="sxs-lookup"><span data-stu-id="3a19f-177">The file of **HistoryInfo** objects that you pass to the `Add-History` cmdlet must include the type information, column headings, and all of the properties of the **HistoryInfo** objects.</span></span> <span data-ttu-id="3a19f-178">Se você pretende passar os objetos de volta para o `Add-History` , não use o parâmetro **NoTypeInformation** do `Export-Csv` cmdlet e não exclua as informações de tipo, os cabeçalhos de coluna ou quaisquer campos no arquivo.</span><span class="sxs-lookup"><span data-stu-id="3a19f-178">If you intend to pass the objects back to `Add-History`, do not use the **NoTypeInformation** parameter of the `Export-Csv` cmdlet and do not delete the type information, column headings, or any fields in the file.</span></span>

<span data-ttu-id="3a19f-179">Para modificar o histórico da sessão, exporte a sessão para um arquivo CSV ou XML, modifique o arquivo, importe o arquivo e use `Add-History` -o para acrescentá-lo ao histórico da sessão atual.</span><span class="sxs-lookup"><span data-stu-id="3a19f-179">To modify the session history, export the session to a CSV or XML file, modify the file, import the file, and use `Add-History` to append it to the current session history.</span></span>

## <span data-ttu-id="3a19f-180">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="3a19f-180">RELATED LINKS</span></span>

[<span data-ttu-id="3a19f-181">Clear-History</span><span class="sxs-lookup"><span data-stu-id="3a19f-181">Clear-History</span></span>](Clear-History.md)

[<span data-ttu-id="3a19f-182">Get-History</span><span class="sxs-lookup"><span data-stu-id="3a19f-182">Get-History</span></span>](Get-History.md)

[<span data-ttu-id="3a19f-183">Invoke-History</span><span class="sxs-lookup"><span data-stu-id="3a19f-183">Invoke-History</span></span>](Invoke-History.md)

[<span data-ttu-id="3a19f-184">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="3a19f-184">about_PSReadLine</span></span>](../PSReadLine/About/about_PSReadLine.md)

[<span data-ttu-id="3a19f-185">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="3a19f-185">Get-PSReadLineOption</span></span>](/powershell/module/psreadline/get-psreadlineoption)

[<span data-ttu-id="3a19f-186">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="3a19f-186">Set-PSReadLineOption</span></span>](/powershell/module/psreadline/set-psreadlineoption)

