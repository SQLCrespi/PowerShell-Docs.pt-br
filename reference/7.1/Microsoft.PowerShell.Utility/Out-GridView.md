---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-gridview?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-GridView
ms.openlocfilehash: 840aa38ff17ceaf7dc65ca838da020c3d8c27952
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94344381"
---
# <span data-ttu-id="5d067-103">Out-GridView</span><span class="sxs-lookup"><span data-stu-id="5d067-103">Out-GridView</span></span>

## <span data-ttu-id="5d067-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="5d067-104">SYNOPSIS</span></span>
<span data-ttu-id="5d067-105">Envia a saída para uma tabela interativa em uma janela separada.</span><span class="sxs-lookup"><span data-stu-id="5d067-105">Sends output to an interactive table in a separate window.</span></span>

## <span data-ttu-id="5d067-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5d067-106">SYNTAX</span></span>

### <span data-ttu-id="5d067-107">PassThru (padrão)</span><span class="sxs-lookup"><span data-stu-id="5d067-107">PassThru (Default)</span></span>

```
Out-GridView [-InputObject <PSObject>] [-Title <String>] [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="5d067-108">Aguarde</span><span class="sxs-lookup"><span data-stu-id="5d067-108">Wait</span></span>

```
Out-GridView [-InputObject <PSObject>] [-Title <String>] [-Wait] [<CommonParameters>]
```

### <span data-ttu-id="5d067-109">OutputMode</span><span class="sxs-lookup"><span data-stu-id="5d067-109">OutputMode</span></span>

```
Out-GridView [-InputObject <PSObject>] [-Title <String>] [-OutputMode <OutputModeOption>]
 [<CommonParameters>]
```

## <span data-ttu-id="5d067-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5d067-110">DESCRIPTION</span></span>

<span data-ttu-id="5d067-111">O `Out-GridView` cmdlet envia a saída de um comando para uma janela de exibição de grade em que a saída é exibida em uma tabela interativa.</span><span class="sxs-lookup"><span data-stu-id="5d067-111">The `Out-GridView` cmdlet sends the output from a command to a grid view window where the output is displayed in an interactive table.</span></span>

<span data-ttu-id="5d067-112">Como esse cmdlet requer uma interface do usuário, ele não funciona no Windows Server Core ou no Windows nano Server.</span><span class="sxs-lookup"><span data-stu-id="5d067-112">Because this cmdlet requires a user interface, it does not work on Windows Server Core or Windows Nano Server.</span></span>

<span data-ttu-id="5d067-113">Você pode usar os recursos da tabela a seguir para examinar os seus dados:</span><span class="sxs-lookup"><span data-stu-id="5d067-113">You can use the following features of the table to examine your data:</span></span>

- <span data-ttu-id="5d067-114">Ocultar, mostrar e reordenar colunas</span><span class="sxs-lookup"><span data-stu-id="5d067-114">Hide, Show, and Reorder Columns</span></span>
- <span data-ttu-id="5d067-115">Classificar linhas</span><span class="sxs-lookup"><span data-stu-id="5d067-115">Sort rows</span></span>
- <span data-ttu-id="5d067-116">Filtro Rápido</span><span class="sxs-lookup"><span data-stu-id="5d067-116">Quick Filter</span></span>
- <span data-ttu-id="5d067-117">Adicionar filtro de critérios</span><span class="sxs-lookup"><span data-stu-id="5d067-117">Add Criteria Filter</span></span>
- <span data-ttu-id="5d067-118">Copiar e colar</span><span class="sxs-lookup"><span data-stu-id="5d067-118">Copy and paste</span></span>

<span data-ttu-id="5d067-119">Para obter instruções completas, consulte a seção [observações](#notes) deste artigo.</span><span class="sxs-lookup"><span data-stu-id="5d067-119">For full instructions, see the [Notes](#notes) section of this article.</span></span>

> [!NOTE]
> <span data-ttu-id="5d067-120">Esse cmdlet foi reintroduzido no PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="5d067-120">This cmdlet was reintroduced in PowerShell 7.</span></span> <span data-ttu-id="5d067-121">Esse cmdlet só está disponível em sistemas Windows que dão suporte à área de trabalho do Windows.</span><span class="sxs-lookup"><span data-stu-id="5d067-121">This cmdlet is only available on Windows systems that support the Windows Desktop.</span></span> <span data-ttu-id="5d067-122">Para uma versão de plataforma cruzada desse cmdlet, consulte o módulo [GraphicalTools](https://www.powershellgallery.com/packages/Microsoft.PowerShell.GraphicalTools) no Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d067-122">For a cross-platform version of this cmdlet, see the [GraphicalTools](https://www.powershellgallery.com/packages/Microsoft.PowerShell.GraphicalTools) module in the PowerShell Gallery.</span></span>

## <span data-ttu-id="5d067-123">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="5d067-123">EXAMPLES</span></span>

### <span data-ttu-id="5d067-124">Exemplo 1: processos de saída para um modo de exibição de grade</span><span class="sxs-lookup"><span data-stu-id="5d067-124">Example 1: Output processes to a grid view</span></span>

<span data-ttu-id="5d067-125">Este exemplo obtém os processos em execução no computador local e os envia para uma janela de exibição em grade.</span><span class="sxs-lookup"><span data-stu-id="5d067-125">This example gets the processes running on the local computer and sends them to a grid view window.</span></span>

```powershell
Get-Process | Out-GridView
```

### <span data-ttu-id="5d067-126">Exemplo 2: usar uma variável para processos de saída para um modo de exibição de grade</span><span class="sxs-lookup"><span data-stu-id="5d067-126">Example 2: Use a variable to output processes to a grid view</span></span>

<span data-ttu-id="5d067-127">Este exemplo também obtém os processos em execução no computador local e os envia para uma janela de exibição em grade.</span><span class="sxs-lookup"><span data-stu-id="5d067-127">This example also gets the processes running on the local computer and sends them to a grid view window.</span></span>

```powershell
$P = Get-Process
$P | Out-GridView
```

<span data-ttu-id="5d067-128">A saída do `Get-Process` cmdlet é salva na `$P` variável.</span><span class="sxs-lookup"><span data-stu-id="5d067-128">The output of the `Get-Process` cmdlet is saved in the `$P` variable.</span></span> <span data-ttu-id="5d067-129">Em seguida, `$P` é canalizado para `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="5d067-129">Then, `$P` is piped to `Out-GridView`.</span></span>

### <span data-ttu-id="5d067-130">Exemplo 3: exibir as propriedades selecionadas em um modo de exibição de grade</span><span class="sxs-lookup"><span data-stu-id="5d067-130">Example 3: Display a selected properties in a grid view</span></span>

<span data-ttu-id="5d067-131">Este exemplo exibe as propriedades selecionadas dos processos em execução em um modo de exibição de grade.</span><span class="sxs-lookup"><span data-stu-id="5d067-131">This example displays selected properties of the running processes in a grid view.</span></span>

```powershell
Get-Process | Select-Object -Property Name, WorkingSet, PeakWorkingSet |
  Sort-Object -Property WorkingSet -Descending | Out-GridView
```

<span data-ttu-id="5d067-132">A saída de `Get-Process` é canalizada para `Select-Object` para selecionar as propriedades **Name** , **WorkingSet** e **PeakWorkingSet** .</span><span class="sxs-lookup"><span data-stu-id="5d067-132">The output of `Get-Process` is piped to `Select-Object` to select the **Name** , **WorkingSet** , and **PeakWorkingSet** properties.</span></span> <span data-ttu-id="5d067-133">Outro operador de pipeline envia os objetos filtrados para o `Sort-Object` cmdlet para classificá-los em ordem decrescente pelo valor da propriedade **WorkingSet** .</span><span class="sxs-lookup"><span data-stu-id="5d067-133">Another pipeline operator sends the filtered objects to the `Sort-Object` cmdlet to sort them in descending order by the value of the **WorkingSet** property.</span></span>
<span data-ttu-id="5d067-134">Em seguida, os resultados classificados são canalizados para `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="5d067-134">Then, the sorted results are piped to `Out-GridView`.</span></span> <span data-ttu-id="5d067-135">Agora você pode usar os recursos de exibição em grade para pesquisar, classificar e filtrar os dados.</span><span class="sxs-lookup"><span data-stu-id="5d067-135">You can now use the features of the grid view to search, sort, and filter the data.</span></span>

### <span data-ttu-id="5d067-136">Exemplo 4: salvar a saída em uma variável e, em seguida, gerar uma exibição de grade</span><span class="sxs-lookup"><span data-stu-id="5d067-136">Example 4: Save output to a variable, and then output a grid view</span></span>

<span data-ttu-id="5d067-137">Esse exemplo salva a saída do cmdlet em uma variável e a envia para `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="5d067-137">This example saves cmdlet output in a variable then sends it to `Out-GridView`.</span></span>

```powershell
($A = Get-ChildItem -Path $PSHOME -Recurse) | Out-GridView
```

<span data-ttu-id="5d067-138">`Get-ChildItem` Obtém todos os arquivos no diretório de instalação do PowerShell e seus subdiretórios usando a `$PSHOME` variável automática.</span><span class="sxs-lookup"><span data-stu-id="5d067-138">`Get-ChildItem` gets all the files in the PowerShell installation directory and its subdirectories using the the `$PSHOME` automatic variable.</span></span> <span data-ttu-id="5d067-139">Os parênteses no comando estabelecem a ordem das operações.</span><span class="sxs-lookup"><span data-stu-id="5d067-139">The parentheses in the command establish the order of operations.</span></span> <span data-ttu-id="5d067-140">Como resultado, a saída do `Get-ChildItem` comando é salva na `$A` variável antes de ser enviada para `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="5d067-140">As a result, the output from the `Get-ChildItem` command is saved in the `$A` variable before it is sent to `Out-GridView`.</span></span>

### <span data-ttu-id="5d067-141">Exemplo 5: processos de saída para um computador especificado para um modo de exibição de grade</span><span class="sxs-lookup"><span data-stu-id="5d067-141">Example 5: Output processes for a specified computer to a grid view</span></span>

<span data-ttu-id="5d067-142">Este exemplo exibe os processos que estão em execução no computador Server01 em uma janela de exibição em grade.</span><span class="sxs-lookup"><span data-stu-id="5d067-142">This example displays the processes that are running on the Server01 computer in a grid view window.</span></span>

```powershell
Get-Process -ComputerName "Server01" | ogv -Title "Processes - Server01"
```

<span data-ttu-id="5d067-143">O examle usa `ogv` , que é o alias para o `Out-GridView` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5d067-143">The examle uses `ogv`, which is the alias for the `Out-GridView` cmdlet.</span></span> <span data-ttu-id="5d067-144">O parâmetro **title** especifica o título da janela.</span><span class="sxs-lookup"><span data-stu-id="5d067-144">The **Title** parameter specifies the window title.</span></span>

### <span data-ttu-id="5d067-145">Exemplo 6: dados de saída de computadores remotos para um modo de exibição de grade</span><span class="sxs-lookup"><span data-stu-id="5d067-145">Example 6: Output data from remote computers to a grid view</span></span>

<span data-ttu-id="5d067-146">Este exemplo mostra como enviar dados coletados de computadores remotos para o `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="5d067-146">This example shows how to send data collected from remote computers to `Out-GridView`.</span></span>

```powershell
Invoke-Command -ComputerName S1, S2, S3 -ScriptBlock {Get-Culture} | Out-GridView
```

<span data-ttu-id="5d067-147">`Invoke-Command` é executado `Get-Culture` em três computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="5d067-147">`Invoke-Command` runs `Get-Culture` on three remote computers.</span></span> <span data-ttu-id="5d067-148">Os dados resultantes são canalizados para `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="5d067-148">The resulting data is piped to `Out-GridView`.</span></span> <span data-ttu-id="5d067-149">Observe que o bloco de script executado no computador remoto não inclui o `Out-GridView` comando.</span><span class="sxs-lookup"><span data-stu-id="5d067-149">Notice that the script block that runs on the remote computer does not include the `Out-GridView` command.</span></span> <span data-ttu-id="5d067-150">Se incluísse, o comando falharia ao tentar abrir uma janela de exibição em grade em cada um dos computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="5d067-150">If it did, the command would fail when it tried to open a grid view window on each of the remote computers.</span></span>

### <span data-ttu-id="5d067-151">Exemplo 7: passar vários itens por meio de `Out-GridView`</span><span class="sxs-lookup"><span data-stu-id="5d067-151">Example 7: Pass multiple items through `Out-GridView`</span></span>

<span data-ttu-id="5d067-152">Este exemplo permite que você selecione vários processos na `Out-GridView` janela.</span><span class="sxs-lookup"><span data-stu-id="5d067-152">This example lets you select multiple processes from the `Out-GridView` window.</span></span> <span data-ttu-id="5d067-153">Os processos selecionados são passados para o `Export-Csv` comando e gravados no `ProcessLog.csv` arquivo.</span><span class="sxs-lookup"><span data-stu-id="5d067-153">The processes that you select are passed to the `Export-Csv` command and written to the `ProcessLog.csv` file.</span></span>

```powershell
Get-Process | Out-GridView -PassThru | Export-Csv -Path .\ProcessLog.csv
```

<span data-ttu-id="5d067-154">O parâmetro **PassThru** de `Out-GridView` permite que você envie vários itens por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="5d067-154">The **PassThru** parameter of `Out-GridView` lets you send multiple items down the pipeline.</span></span> <span data-ttu-id="5d067-155">O parâmetro **PassThru** é equivalente a usar o valor **Multiple** do parâmetro **OutputMode**.</span><span class="sxs-lookup"><span data-stu-id="5d067-155">The **PassThru** parameter is equivalent to using the **Multiple** value of the **OutputMode** parameter.</span></span>

### <span data-ttu-id="5d067-156">Exemplo 8: criar um atalho do Windows para `Out-GridView`</span><span class="sxs-lookup"><span data-stu-id="5d067-156">Example 8: Create a Windows shortcut to `Out-GridView`</span></span>

<span data-ttu-id="5d067-157">Este exemplo mostra como usar o parâmetro **Wait** do `Out-GridView` para criar um atalho do Windows para a `Out-GridView` janela.</span><span class="sxs-lookup"><span data-stu-id="5d067-157">This example shows how to use the **Wait** parameter of `Out-GridView` to create a Windows shortcut to the `Out-GridView` window.</span></span>

```powershell
pwsh -Command "Get-Service | Out-GridView -Wait"
```

<span data-ttu-id="5d067-158">Essa linha de comando pode ser usada em um atalho do Windows.</span><span class="sxs-lookup"><span data-stu-id="5d067-158">This command line can be used in a Windows shortcut.</span></span> <span data-ttu-id="5d067-159">Sem o parâmetro **Wait** , o PowerShell será encerrado assim que a `Out-GridView` janela fosse aberta, o que fecharia a `Out-GridView` janela quase imediatamente.</span><span class="sxs-lookup"><span data-stu-id="5d067-159">Without the **Wait** parameter, PowerShell would exit as soon as the `Out-GridView` window opened, which would close the `Out-GridView` window almost immediately.</span></span>

## <span data-ttu-id="5d067-160">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5d067-160">PARAMETERS</span></span>

### <span data-ttu-id="5d067-161">-InputObject</span><span class="sxs-lookup"><span data-stu-id="5d067-161">-InputObject</span></span>

<span data-ttu-id="5d067-162">Especifica o objeto que o cmdlet aceita como entrada para `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="5d067-162">Specifies object that the cmdlet accepts as input for `Out-GridView`.</span></span>

<span data-ttu-id="5d067-163">Quando você usa o parâmetro **InputObject** para enviar uma coleção de objetos ao `Out-GridView` , `Out-GridView` o trata a coleção como um objeto de coleção e exibe uma linha que representa a coleção.</span><span class="sxs-lookup"><span data-stu-id="5d067-163">When you use the **InputObject** parameter to send a collection of objects to `Out-GridView`, `Out-GridView` treats the collection as one collection object, and it displays one row that represents the collection.</span></span> <span data-ttu-id="5d067-164">Para exibir cada objeto na coleção, use um operador de pipeline ( `|` ) para enviar objetos para o `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="5d067-164">To display the each object in the collection, use a pipeline operator (`|`) to send objects to `Out-GridView`.</span></span>

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

### <span data-ttu-id="5d067-165">-OutputType</span><span class="sxs-lookup"><span data-stu-id="5d067-165">-OutputMode</span></span>

<span data-ttu-id="5d067-166">Especifica os itens que a janela interativa envia ao pipeline como entrada para outros comandos.</span><span class="sxs-lookup"><span data-stu-id="5d067-166">Specifies the items that the interactive window sends down the pipeline as input to other commands.</span></span>
<span data-ttu-id="5d067-167">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="5d067-167">By default, this cmdlet does not generate any output.</span></span> <span data-ttu-id="5d067-168">Para enviar itens da janela interativa pelo pipeline, clique para selecionar os itens e, em seguida, clique em OK.</span><span class="sxs-lookup"><span data-stu-id="5d067-168">To send items from the interactive window down the pipeline, click to select the items and then click OK.</span></span>

<span data-ttu-id="5d067-169">Os valores desse parâmetro determinam quantos itens você pode enviar pelo pipeline.</span><span class="sxs-lookup"><span data-stu-id="5d067-169">The values of this parameter determine how many items you can send down the pipeline.</span></span>

- <span data-ttu-id="5d067-170">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="5d067-170">None.</span></span>  <span data-ttu-id="5d067-171">Nenhum item.</span><span class="sxs-lookup"><span data-stu-id="5d067-171">No items.</span></span> <span data-ttu-id="5d067-172">Esse é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="5d067-172">This is the default value.</span></span>
- <span data-ttu-id="5d067-173">Única.</span><span class="sxs-lookup"><span data-stu-id="5d067-173">Single.</span></span> <span data-ttu-id="5d067-174">Zero itens ou um item.</span><span class="sxs-lookup"><span data-stu-id="5d067-174">Zero items or one item.</span></span> <span data-ttu-id="5d067-175">Use esse valor quando o próximo comando puder levar apenas um objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="5d067-175">Use this value when the next command can take only one input object.</span></span>
- <span data-ttu-id="5d067-176">Vários.</span><span class="sxs-lookup"><span data-stu-id="5d067-176">Multiple.</span></span> <span data-ttu-id="5d067-177">Zero, um ou muitos itens.</span><span class="sxs-lookup"><span data-stu-id="5d067-177">Zero, one, or many items.</span></span> <span data-ttu-id="5d067-178">Use esse valor quando o próximo comando puder levar vários objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="5d067-178">Use this value when the next command can take multiple input objects.</span></span> <span data-ttu-id="5d067-179">Esse valor é equivalente ao parâmetro **Passthru**.</span><span class="sxs-lookup"><span data-stu-id="5d067-179">This value is equivalent to the **Passthru** parameter.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.OutputModeOption
Parameter Sets: OutputMode
Aliases:
Accepted values: None, Single, Multiple

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5d067-180">-PassThru</span><span class="sxs-lookup"><span data-stu-id="5d067-180">-PassThru</span></span>

<span data-ttu-id="5d067-181">Indica que o cmdlet envia itens da janela interativa para baixo no pipeline como entrada para outros comandos.</span><span class="sxs-lookup"><span data-stu-id="5d067-181">Indicates that the cmdlet sends items from the interactive window down the pipeline as input to other commands.</span></span> <span data-ttu-id="5d067-182">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="5d067-182">By default, this cmdlet does not generate any output.</span></span> <span data-ttu-id="5d067-183">Este parâmetro é equivalente a usar o valor **Multiple** do parâmetro **OutputMode**.</span><span class="sxs-lookup"><span data-stu-id="5d067-183">This parameter is equivalent to using the **Multiple** value of the **OutputMode** parameter.</span></span>

<span data-ttu-id="5d067-184">Para enviar itens da janela interativa pelo pipeline, clique para selecionar os itens e, em seguida, clique em OK.</span><span class="sxs-lookup"><span data-stu-id="5d067-184">To send items from the interactive window down the pipeline, click to select the items and then click OK.</span></span> <span data-ttu-id="5d067-185">Shift+clique e Ctrl+clique são suportados.</span><span class="sxs-lookup"><span data-stu-id="5d067-185">Shift-click and Ctrl-click are supported.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PassThru
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5d067-186">-Title</span><span class="sxs-lookup"><span data-stu-id="5d067-186">-Title</span></span>

<span data-ttu-id="5d067-187">Especifica o texto que aparece na barra de título da `Out-GridView` janela.</span><span class="sxs-lookup"><span data-stu-id="5d067-187">Specifies the text that appears in the title bar of the `Out-GridView` window.</span></span> <span data-ttu-id="5d067-188">Por padrão, a barra de título exibe o comando que invoca `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="5d067-188">By default, the title bar displays the command that invokes `Out-GridView`.</span></span>

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

### <span data-ttu-id="5d067-189">-Wait</span><span class="sxs-lookup"><span data-stu-id="5d067-189">-Wait</span></span>

<span data-ttu-id="5d067-190">Indica que o cmdlet suprime o prompt de comando e impede que o Windows PowerShell seja fechado até que a `Out-GridView` janela seja fechada.</span><span class="sxs-lookup"><span data-stu-id="5d067-190">Indicates that the cmdlet suppresses the command prompt and prevents Windows PowerShell from closing until the `Out-GridView` window is closed.</span></span> <span data-ttu-id="5d067-191">Por padrão, o prompt de comando retorna quando a `Out-GridView` janela é aberta.</span><span class="sxs-lookup"><span data-stu-id="5d067-191">By default, the command prompt returns when the `Out-GridView` window opens.</span></span>

<span data-ttu-id="5d067-192">Esse recurso permite que você use os `Out-GridView` cmdlets em atalhos do Windows.</span><span class="sxs-lookup"><span data-stu-id="5d067-192">This feature lets you use the `Out-GridView` cmdlets in Windows shortcuts.</span></span> <span data-ttu-id="5d067-193">Quando `Out-GridView` é usado em um atalho sem o parâmetro **Wait** , a `Out-GridView` janela aparece apenas momentaneamente antes de o PowerShell fechar.</span><span class="sxs-lookup"><span data-stu-id="5d067-193">When `Out-GridView` is used in a shortcut without the **Wait** parameter, the `Out-GridView` window appears only momentarily before PowerShell closes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Wait
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5d067-194">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5d067-194">CommonParameters</span></span>

<span data-ttu-id="5d067-195">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5d067-195">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5d067-196">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5d067-196">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5d067-197">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="5d067-197">INPUTS</span></span>

### <span data-ttu-id="5d067-198">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="5d067-198">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="5d067-199">Você pode enviar qualquer objeto para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5d067-199">You can send any object to this cmdlet.</span></span>

## <span data-ttu-id="5d067-200">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="5d067-200">OUTPUTS</span></span>

### <span data-ttu-id="5d067-201">Nenhum</span><span class="sxs-lookup"><span data-stu-id="5d067-201">None</span></span>

<span data-ttu-id="5d067-202">Normalmente, `Out-GridView` o não retorna nenhum objeto.</span><span class="sxs-lookup"><span data-stu-id="5d067-202">Normally, `Out-GridView` does not return any objects.</span></span> <span data-ttu-id="5d067-203">Ao usar o parâmetro **PassThru** , os objetos que representam as linhas selecionadas são retornados para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="5d067-203">When using the **PassThru** parameter, the objects representing the selected rows are returned to the pipeline.</span></span>

## <span data-ttu-id="5d067-204">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="5d067-204">NOTES</span></span>

<span data-ttu-id="5d067-205">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="5d067-205">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="5d067-206">Você não pode usar um comando remoto para abrir uma janela de exibição em grade em outro computador.</span><span class="sxs-lookup"><span data-stu-id="5d067-206">You cannot use a remote command to open a grid view window on another computer.</span></span>

<span data-ttu-id="5d067-207">A saída do comando que você envia para `Out-GridView` não pode ser formatada usando os `Format` cmdlets, como `Format-Table` ou `Format-Wide` cmdlets.</span><span class="sxs-lookup"><span data-stu-id="5d067-207">The command output that you send to `Out-GridView` cannot be formatted using the `Format` cmdlets, such as `Format-Table` or `Format-Wide` cmdlets.</span></span> <span data-ttu-id="5d067-208">Para selecionar propriedades, use o `Select-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5d067-208">To select properties, use the `Select-Object` cmdlet.</span></span>

<span data-ttu-id="5d067-209">Resultado desserializado de comandos remotos podem não ser formatados corretamente na janela de exibição em grade.</span><span class="sxs-lookup"><span data-stu-id="5d067-209">Deserialized output from remote commands might not be formatted correctly in the grid view window.</span></span>

<span data-ttu-id="5d067-210">**Atalhos de teclado para**`Out-GridView`</span><span class="sxs-lookup"><span data-stu-id="5d067-210">**Keyboard Shortcuts for** `Out-GridView`</span></span>

|              <span data-ttu-id="5d067-211">Use esta tecla:</span><span class="sxs-lookup"><span data-stu-id="5d067-211">Use this key:</span></span>              |                                   <span data-ttu-id="5d067-212">Para executar esta ação:</span><span class="sxs-lookup"><span data-stu-id="5d067-212">To perform this action:</span></span>                                    |
| --------------------------------------- | -------------------------------------------------------------------------------------------- |
| <span data-ttu-id="5d067-213"><kbd>Guia</kbd></span><span class="sxs-lookup"><span data-stu-id="5d067-213"><kbd>Tab</kbd></span></span>                          | <span data-ttu-id="5d067-214">Move o cursor da caixa de **filtro** para o menu **Adicionar critérios** para a tabela e de volta.</span><span class="sxs-lookup"><span data-stu-id="5d067-214">Moves the cursor from the **Filter** box to the **Add criteria** menu to the table and back.</span></span> |
| <span data-ttu-id="5d067-215"><kbd>Upseta</kbd></span><span class="sxs-lookup"><span data-stu-id="5d067-215"><kbd>UpArrow</kbd></span></span>                      | <span data-ttu-id="5d067-216">Mover uma linha para cima.</span><span class="sxs-lookup"><span data-stu-id="5d067-216">Move up one row.</span></span> <span data-ttu-id="5d067-217">Move para cabeçalhos de coluna da primeira linha de dados.</span><span class="sxs-lookup"><span data-stu-id="5d067-217">Moves to column headers from first row of data.</span></span>                             |
| <span data-ttu-id="5d067-218"><kbd>Seta</kbd></span><span class="sxs-lookup"><span data-stu-id="5d067-218"><kbd>DownArrow</kbd></span></span>                    | <span data-ttu-id="5d067-219">Mover uma linha para baixo.</span><span class="sxs-lookup"><span data-stu-id="5d067-219">Move down one row.</span></span>                                                                           |
| <span data-ttu-id="5d067-220"><kbd>LeftArrow</kbd></span><span class="sxs-lookup"><span data-stu-id="5d067-220"><kbd>LeftArrow</kbd></span></span>                    | <span data-ttu-id="5d067-221">Na linha de cabeçalho da coluna, mova uma coluna para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="5d067-221">In column header row, move left one column.</span></span>                                                  |
| <span data-ttu-id="5d067-222"><kbd>RightArrow</kbd></span><span class="sxs-lookup"><span data-stu-id="5d067-222"><kbd>RightArrow</kbd></span></span>                   | <span data-ttu-id="5d067-223">Na linha de cabeçalho da coluna, mova uma coluna para a direita.</span><span class="sxs-lookup"><span data-stu-id="5d067-223">In column header row, move right one column.</span></span>                                                 |
| <span data-ttu-id="5d067-224"><kbd>ContextMenuKey</kbd></span><span class="sxs-lookup"><span data-stu-id="5d067-224"><kbd>ContextMenuKey</kbd></span></span>               | <span data-ttu-id="5d067-225">Na linha de cabeçalho da coluna, exibe a opção Selecionar colunas.</span><span class="sxs-lookup"><span data-stu-id="5d067-225">In column header row, displays the Select Columns option.</span></span>                                    |
| <span data-ttu-id="5d067-226"><kbd>Inserir</kbd> ou <kbd>barra de espaços</kbd></span><span class="sxs-lookup"><span data-stu-id="5d067-226"><kbd>Enter</kbd> or <kbd>Spacebar</kbd></span></span> | <span data-ttu-id="5d067-227">Na linha de cabeçalho da coluna, classifique os dados da coluna (alterne para A-Z, Z-A).</span><span class="sxs-lookup"><span data-stu-id="5d067-227">In column header row, sort column data (toggle A-Z, Z-A).</span></span>                                    |

<span data-ttu-id="5d067-228">**Como usar os recursos da janela de exibição em grade**</span><span class="sxs-lookup"><span data-stu-id="5d067-228">**How to Use the Grid View Window Features**</span></span>

<span data-ttu-id="5d067-229">**Para ocultar ou mostrar uma coluna:**</span><span class="sxs-lookup"><span data-stu-id="5d067-229">**To hide or show a column:**</span></span>

1. <span data-ttu-id="5d067-230">Clique com o botão direito do mouse em qualquer cabeçalho de coluna e clique em **selecionar colunas**.</span><span class="sxs-lookup"><span data-stu-id="5d067-230">Right-click any column header and click **Select Columns**.</span></span>
2. <span data-ttu-id="5d067-231">Na caixa de diálogo **selecionar colunas** , use as teclas de direção para mover as colunas entre as colunas selecionadas para as caixas colunas disponíveis.</span><span class="sxs-lookup"><span data-stu-id="5d067-231">In the **Select Columns** dialog box, use the arrow keys to move the columns between the Selected columns to the Available columns boxes.</span></span> <span data-ttu-id="5d067-232">Somente as colunas na caixa **selecionar colunas** aparecem na janela de exibição em grade.</span><span class="sxs-lookup"><span data-stu-id="5d067-232">Only columns in the **Select Columns** box appear in the grid view window.</span></span>

<span data-ttu-id="5d067-233">**Para reordenar colunas:**</span><span class="sxs-lookup"><span data-stu-id="5d067-233">**To reorder columns:**</span></span>

<span data-ttu-id="5d067-234">Você pode arrastar e soltar colunas no local desejado.</span><span class="sxs-lookup"><span data-stu-id="5d067-234">You can drag and drop columns into the desired location.</span></span> <span data-ttu-id="5d067-235">Ou use as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="5d067-235">Or use the following steps:</span></span>

1. <span data-ttu-id="5d067-236">Clique com o botão direito do mouse em qualquer cabeçalho de coluna e clique em **selecionar colunas**.</span><span class="sxs-lookup"><span data-stu-id="5d067-236">Right-click any column header and click **Select Columns**.</span></span>
2. <span data-ttu-id="5d067-237">Na caixa de diálogo **selecionar colunas** , use os botões **mover para cima** e mover para **baixo** para reordenar as colunas.</span><span class="sxs-lookup"><span data-stu-id="5d067-237">In the **Select Columns** dialog box, use the **Move up** and **Move down** buttons to reorder the columns.</span></span> <span data-ttu-id="5d067-238">As colunas na parte superior da lista aparecem à esquerda das colunas na parte inferior da lista na janela de exibição em grade.</span><span class="sxs-lookup"><span data-stu-id="5d067-238">Columns at the top of the list appear to the left of columns at the bottom of the list in the grid view window.</span></span>

<span data-ttu-id="5d067-239">**Como classificar dados de tabela**</span><span class="sxs-lookup"><span data-stu-id="5d067-239">**How to Sort Table Data**</span></span>

- <span data-ttu-id="5d067-240">Para classificar os dados, clique em um cabeçalho de coluna.</span><span class="sxs-lookup"><span data-stu-id="5d067-240">To sort the data, click a column header.</span></span>
- <span data-ttu-id="5d067-241">Para alterar a ordem de classificação, clique no cabeçalho da coluna novamente.</span><span class="sxs-lookup"><span data-stu-id="5d067-241">To change the sort order, click the column header again.</span></span> <span data-ttu-id="5d067-242">Cada vez que você clicar no mesmo cabeçalho, a ordem de classificação alterna entre crescente para decrescente.</span><span class="sxs-lookup"><span data-stu-id="5d067-242">Each time you click the same header, the sort order toggles between ascending to descending order.</span></span> <span data-ttu-id="5d067-243">O pedido atual é indicado por um triângulo no cabeçalho da coluna.</span><span class="sxs-lookup"><span data-stu-id="5d067-243">The current order is indicated by a triangle in the column header.</span></span>

<span data-ttu-id="5d067-244">**Como selecionar dados da tabela**</span><span class="sxs-lookup"><span data-stu-id="5d067-244">**How to Select Table Data**</span></span>

- <span data-ttu-id="5d067-245">Para selecionar uma linha, selecione a linha ou use a seta para cima ou para baixo para navegar até a linha.</span><span class="sxs-lookup"><span data-stu-id="5d067-245">To select a row, select the row or use the up or down arrow to navigate to the row.</span></span>
- <span data-ttu-id="5d067-246">Para selecionar todas as linhas (exceto para a linha de cabeçalho), pressione <kbd>Ctrl</kbd> + <kbd>A</kbd>.</span><span class="sxs-lookup"><span data-stu-id="5d067-246">To select all rows (except for the header row), press <kbd>CTRL</kbd>+<kbd>A</kbd>.</span></span>
- <span data-ttu-id="5d067-247">Para selecionar linhas consecutivas, pressione e segure a tecla <kbd>Shift</kbd> enquanto clica nas linhas ou usando as teclas de direção.</span><span class="sxs-lookup"><span data-stu-id="5d067-247">To select consecutive rows, press and hold the <kbd>SHIFT</kbd> key while clicking the rows or using the arrow keys.</span></span>
- <span data-ttu-id="5d067-248">Para selecionar linhas não consecutivas, pressione a tecla <kbd>Ctrl</kbd> e clique para adicionar uma linha à seleção.</span><span class="sxs-lookup"><span data-stu-id="5d067-248">To select nonconsecutive rows, press the <kbd>CTRL</kbd> key and click to add a row to the selection.</span></span>
- <span data-ttu-id="5d067-249">Não é possível selecionar colunas e nem a linha inteira de cabeçalhos de coluna.</span><span class="sxs-lookup"><span data-stu-id="5d067-249">You cannot select columns, and you cannot select the entire column header row.</span></span>

<span data-ttu-id="5d067-250">**Como copiar linhas**</span><span class="sxs-lookup"><span data-stu-id="5d067-250">**How to Copy Rows**</span></span>

- <span data-ttu-id="5d067-251">Para copiar uma ou mais linhas da tabela, selecione as linhas e pressione CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="5d067-251">To copy one or more rows from the table, select the rows and then press CTRL+C.</span></span>

  <span data-ttu-id="5d067-252">Você pode colar os dados em qualquer programa de texto ou planilha.</span><span class="sxs-lookup"><span data-stu-id="5d067-252">You can paste the data into any text or spreadsheet program.</span></span> <span data-ttu-id="5d067-253">Não é possível copiar colunas ou partes de linhas e nem a linha de cabeçalhos de coluna.</span><span class="sxs-lookup"><span data-stu-id="5d067-253">You cannot copy columns or parts of rows and you cannot copy the column header row.</span></span>

<span data-ttu-id="5d067-254">**Como Pesquisar na tabela (filtro rápido)**</span><span class="sxs-lookup"><span data-stu-id="5d067-254">**How to Search in the Table (Quick Filter)**</span></span>

<span data-ttu-id="5d067-255">Use a caixa de filtro para pesquisar dados na tabela.</span><span class="sxs-lookup"><span data-stu-id="5d067-255">Use the Filter box to search for data in the table.</span></span> <span data-ttu-id="5d067-256">Quando você digita na caixa, somente os itens que incluem o texto digitado são exibidos na tabela.</span><span class="sxs-lookup"><span data-stu-id="5d067-256">When you type in the box, only items that include the typed text appear in the table.</span></span>

- <span data-ttu-id="5d067-257">Pesquise por texto.</span><span class="sxs-lookup"><span data-stu-id="5d067-257">Search for text.</span></span> <span data-ttu-id="5d067-258">Para Pesquisar texto na tabela, na caixa filtro, digite o texto a ser localizado.</span><span class="sxs-lookup"><span data-stu-id="5d067-258">To search for text in the table, in the Filter box, type the text to find.</span></span>
- <span data-ttu-id="5d067-259">Pesquise por várias palavras.</span><span class="sxs-lookup"><span data-stu-id="5d067-259">Search for multiple words.</span></span> <span data-ttu-id="5d067-260">Para pesquisar várias palavras na tabela, digite as palavras separadas por espaços.</span><span class="sxs-lookup"><span data-stu-id="5d067-260">To search for multiple words in the table, type the words separated by spaces.</span></span> <span data-ttu-id="5d067-261">`Out-GridView` exibe as linhas que incluem todas as palavras (AND lógico).</span><span class="sxs-lookup"><span data-stu-id="5d067-261">`Out-GridView` displays rows that include all the words (logical AND).</span></span>
- <span data-ttu-id="5d067-262">Procure frases literais.</span><span class="sxs-lookup"><span data-stu-id="5d067-262">Search for literal phrases.</span></span> <span data-ttu-id="5d067-263">Para pesquisar frases que incluam espaços ou caracteres especiais, coloque a frase entre aspas.</span><span class="sxs-lookup"><span data-stu-id="5d067-263">To search for phrases that include spaces or special characters, enclose the phrase in quotation marks.</span></span> <span data-ttu-id="5d067-264">`Out-GridView` exibe as linhas que incluem uma correspondência exata para a frase.</span><span class="sxs-lookup"><span data-stu-id="5d067-264">`Out-GridView` displays rows that include an exact match for the phrase.</span></span>
- <span data-ttu-id="5d067-265">Pesquisar em colunas.</span><span class="sxs-lookup"><span data-stu-id="5d067-265">Search in columns.</span></span> <span data-ttu-id="5d067-266">Para pesquisar texto em uma ou mais colunas, use o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="5d067-266">To search for text in one or more columns, use the following format:</span></span>

  `<column>:<text> [<column>:<text>] ...`

  <span data-ttu-id="5d067-267">Por exemplo, para localizar "net" na coluna **DisplayName** , na caixa **filtro** , digite:</span><span class="sxs-lookup"><span data-stu-id="5d067-267">For example, to find "Net" in the **DisplayName** column, in the **Filter** box, type:</span></span>

  `displayname:net`

  <span data-ttu-id="5d067-268">Para localizar linhas com "net" nas colunas **DisplayName** e **Name** , na caixa **filtro** , digite:</span><span class="sxs-lookup"><span data-stu-id="5d067-268">To find rows with "Net" in the **DisplayName** and **Name** columns, in the **Filter** box, type:</span></span>

  `displayname:net name:net`

- <span data-ttu-id="5d067-269">Desative a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="5d067-269">Turn off search.</span></span> <span data-ttu-id="5d067-270">Para exibir a tabela inteira novamente, clique no botão X vermelho no canto superior direito da caixa de **filtro** ou exclua o texto da caixa de **filtro** .</span><span class="sxs-lookup"><span data-stu-id="5d067-270">To display the entire table again, click the red X button in the top right corner of the **Filter** box or delete the text from the **Filter** box.</span></span>

<span data-ttu-id="5d067-271">**Use critérios para filtrar a tabela**</span><span class="sxs-lookup"><span data-stu-id="5d067-271">**Use Criteria to Filter the Table**</span></span>

<span data-ttu-id="5d067-272">Você pode usar regras ou critérios para determinar quais itens são exibidos na tabela.</span><span class="sxs-lookup"><span data-stu-id="5d067-272">You can use rules or criteria to determine which items are displayed in the table.</span></span> <span data-ttu-id="5d067-273">Os itens aparecem apenas quando atendem a todos os critérios que você estabelece.</span><span class="sxs-lookup"><span data-stu-id="5d067-273">Items appear only when they satisfy all the criteria that you establish.</span></span> <span data-ttu-id="5d067-274">Os critérios disponíveis são determinados pelas propriedades dos objetos exibidos na janela de exibição em grade e tipos do .NET Framework dessas propriedades.</span><span class="sxs-lookup"><span data-stu-id="5d067-274">The available criteria are determined by the properties of the objects displayed in the grid view window and the .NET Framework types of those properties.</span></span>

<span data-ttu-id="5d067-275">Cada critério tem o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="5d067-275">Each criterion has the following format:</span></span>

`<column> <operator> <value>`

<span data-ttu-id="5d067-276">Os critérios para propriedades diferentes são conectados por **e**.</span><span class="sxs-lookup"><span data-stu-id="5d067-276">Criteria for different properties are connected by **AND**.</span></span> <span data-ttu-id="5d067-277">Os critérios para a mesma propriedade são conectados por **ou**.</span><span class="sxs-lookup"><span data-stu-id="5d067-277">Criteria for the same property are connected by **OR**.</span></span> <span data-ttu-id="5d067-278">Você não pode alterar os conectores lógicos.</span><span class="sxs-lookup"><span data-stu-id="5d067-278">You cannot change the logical connectors.</span></span>

<span data-ttu-id="5d067-279">Os critérios afetam somente a exibição.</span><span class="sxs-lookup"><span data-stu-id="5d067-279">The criteria only affects the display.</span></span> <span data-ttu-id="5d067-280">Ele não exclui itens da tabela.</span><span class="sxs-lookup"><span data-stu-id="5d067-280">It does not delete items from the table.</span></span>

<span data-ttu-id="5d067-281">**Como adicionar critérios**</span><span class="sxs-lookup"><span data-stu-id="5d067-281">**How to Add Criteria**</span></span>

1. <span data-ttu-id="5d067-282">Para exibir o botão de menu **Adicionar critérios** , no canto superior direito da janela, clique na seta de expansão.</span><span class="sxs-lookup"><span data-stu-id="5d067-282">To display the **Add criteria** menu button, in the upper right corner of the window, click the Expand arrow.</span></span>
2. <span data-ttu-id="5d067-283">Clique no botão de menu **Adicionar critérios** .</span><span class="sxs-lookup"><span data-stu-id="5d067-283">Click the **Add Criteria** menu button.</span></span>
3. <span data-ttu-id="5d067-284">Clique para selecionar colunas (propriedades).</span><span class="sxs-lookup"><span data-stu-id="5d067-284">Click to select columns (properties).</span></span> <span data-ttu-id="5d067-285">Você pode selecionar uma ou mais propriedades.</span><span class="sxs-lookup"><span data-stu-id="5d067-285">You can select one or many properties.</span></span>
4. <span data-ttu-id="5d067-286">Quando terminar de selecionar propriedades, clique no botão **Adicionar** .</span><span class="sxs-lookup"><span data-stu-id="5d067-286">When you are finished selecting properties, click the **Add** button.</span></span>
5. <span data-ttu-id="5d067-287">Para cancelar as adições, clique em **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="5d067-287">To cancel the additions, click **Cancel**.</span></span>
6. <span data-ttu-id="5d067-288">Para adicionar mais critérios, clique no botão **Adicionar critérios** novamente.</span><span class="sxs-lookup"><span data-stu-id="5d067-288">To add more criteria, click the **Add Criteria** button again.</span></span>

<span data-ttu-id="5d067-289">**Como editar um critério**</span><span class="sxs-lookup"><span data-stu-id="5d067-289">**How to Edit a Criterion**</span></span>

- <span data-ttu-id="5d067-290">Para alterar um operador, clique no valor do operador azul e, em seguida, selecione um operador diferente na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="5d067-290">To change an operator, click the blue operator value, and then select a different operator from the drop-down list.</span></span>
- <span data-ttu-id="5d067-291">Para inserir ou alterar um valor, digite um valor na caixa valor.</span><span class="sxs-lookup"><span data-stu-id="5d067-291">To enter or change a value, type a value in the value box.</span></span> <span data-ttu-id="5d067-292">Se você inserir um valor que não é válido, um ícone de X circular aparece.</span><span class="sxs-lookup"><span data-stu-id="5d067-292">If you enter a value that is not valid, a circular X icon appears.</span></span> <span data-ttu-id="5d067-293">Para removê-lo, altere o valor.</span><span class="sxs-lookup"><span data-stu-id="5d067-293">To remove it, change the value.</span></span>
- <span data-ttu-id="5d067-294">Para criar uma instrução **ou** , adicione um critério com a mesma propriedade.</span><span class="sxs-lookup"><span data-stu-id="5d067-294">To create an **OR** statement, add a criteria with the same property.</span></span>

<span data-ttu-id="5d067-295">**Como excluir critérios**</span><span class="sxs-lookup"><span data-stu-id="5d067-295">**How to Delete Criteria**</span></span>

- <span data-ttu-id="5d067-296">Para excluir os critérios selecionados, clique no X vermelho ao lado de cada critério.</span><span class="sxs-lookup"><span data-stu-id="5d067-296">To delete selected criteria, click the red X beside each criterion.</span></span>
- <span data-ttu-id="5d067-297">Para excluir todos os critérios, clique no botão **limpar tudo** .</span><span class="sxs-lookup"><span data-stu-id="5d067-297">To delete all criteria, click the **Clear All** button.</span></span>

## <span data-ttu-id="5d067-298">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="5d067-298">RELATED LINKS</span></span>

[<span data-ttu-id="5d067-299">Out-File</span><span class="sxs-lookup"><span data-stu-id="5d067-299">Out-File</span></span>](Out-File.md)

[<span data-ttu-id="5d067-300">Out-Printer</span><span class="sxs-lookup"><span data-stu-id="5d067-300">Out-Printer</span></span>](Out-Printer.md)

[<span data-ttu-id="5d067-301">Out-String</span><span class="sxs-lookup"><span data-stu-id="5d067-301">Out-String</span></span>](Out-String.md)

