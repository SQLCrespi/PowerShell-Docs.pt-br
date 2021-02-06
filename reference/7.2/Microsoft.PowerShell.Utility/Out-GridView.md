---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-gridview?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-GridView
ms.openlocfilehash: 19a53b5b14d2dfdb513fbbda4c55ba0df37ab1c0
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603750"
---
# <span data-ttu-id="97330-102">Out-GridView</span><span class="sxs-lookup"><span data-stu-id="97330-102">Out-GridView</span></span>

## <span data-ttu-id="97330-103">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="97330-103">SYNOPSIS</span></span>
<span data-ttu-id="97330-104">Envia a saída para uma tabela interativa em uma janela separada.</span><span class="sxs-lookup"><span data-stu-id="97330-104">Sends output to an interactive table in a separate window.</span></span>

## <span data-ttu-id="97330-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="97330-105">SYNTAX</span></span>

### <span data-ttu-id="97330-106">PassThru (padrão)</span><span class="sxs-lookup"><span data-stu-id="97330-106">PassThru (Default)</span></span>

```
Out-GridView [-InputObject <PSObject>] [-Title <String>] [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="97330-107">Aguarde</span><span class="sxs-lookup"><span data-stu-id="97330-107">Wait</span></span>

```
Out-GridView [-InputObject <PSObject>] [-Title <String>] [-Wait] [<CommonParameters>]
```

### <span data-ttu-id="97330-108">OutputMode</span><span class="sxs-lookup"><span data-stu-id="97330-108">OutputMode</span></span>

```
Out-GridView [-InputObject <PSObject>] [-Title <String>] [-OutputMode <OutputModeOption>]
 [<CommonParameters>]
```

## <span data-ttu-id="97330-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="97330-109">DESCRIPTION</span></span>

<span data-ttu-id="97330-110">O `Out-GridView` cmdlet envia a saída de um comando para uma janela de exibição de grade em que a saída é exibida em uma tabela interativa.</span><span class="sxs-lookup"><span data-stu-id="97330-110">The `Out-GridView` cmdlet sends the output from a command to a grid view window where the output is displayed in an interactive table.</span></span>

<span data-ttu-id="97330-111">Como esse cmdlet requer uma interface do usuário, ele não funciona no Windows Server Core ou no Windows nano Server.</span><span class="sxs-lookup"><span data-stu-id="97330-111">Because this cmdlet requires a user interface, it does not work on Windows Server Core or Windows Nano Server.</span></span>

<span data-ttu-id="97330-112">Você pode usar os recursos da tabela a seguir para examinar os seus dados:</span><span class="sxs-lookup"><span data-stu-id="97330-112">You can use the following features of the table to examine your data:</span></span>

- <span data-ttu-id="97330-113">Ocultar, mostrar e reordenar colunas</span><span class="sxs-lookup"><span data-stu-id="97330-113">Hide, Show, and Reorder Columns</span></span>
- <span data-ttu-id="97330-114">Classificar linhas</span><span class="sxs-lookup"><span data-stu-id="97330-114">Sort rows</span></span>
- <span data-ttu-id="97330-115">Filtro Rápido</span><span class="sxs-lookup"><span data-stu-id="97330-115">Quick Filter</span></span>
- <span data-ttu-id="97330-116">Adicionar filtro de critérios</span><span class="sxs-lookup"><span data-stu-id="97330-116">Add Criteria Filter</span></span>
- <span data-ttu-id="97330-117">Copiar e colar</span><span class="sxs-lookup"><span data-stu-id="97330-117">Copy and paste</span></span>

<span data-ttu-id="97330-118">Para obter instruções completas, consulte a seção [observações](#notes) deste artigo.</span><span class="sxs-lookup"><span data-stu-id="97330-118">For full instructions, see the [Notes](#notes) section of this article.</span></span>

> [!NOTE]
> <span data-ttu-id="97330-119">Esse cmdlet foi reintroduzido no PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="97330-119">This cmdlet was reintroduced in PowerShell 7.</span></span> <span data-ttu-id="97330-120">Esse cmdlet só está disponível em sistemas Windows que dão suporte à área de trabalho do Windows.</span><span class="sxs-lookup"><span data-stu-id="97330-120">This cmdlet is only available on Windows systems that support the Windows Desktop.</span></span> <span data-ttu-id="97330-121">Para uma versão de plataforma cruzada desse cmdlet, consulte o módulo [GraphicalTools](https://www.powershellgallery.com/packages/Microsoft.PowerShell.GraphicalTools) no Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="97330-121">For a cross-platform version of this cmdlet, see the [GraphicalTools](https://www.powershellgallery.com/packages/Microsoft.PowerShell.GraphicalTools) module in the PowerShell Gallery.</span></span>

## <span data-ttu-id="97330-122">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="97330-122">EXAMPLES</span></span>

### <span data-ttu-id="97330-123">Exemplo 1: processos de saída para um modo de exibição de grade</span><span class="sxs-lookup"><span data-stu-id="97330-123">Example 1: Output processes to a grid view</span></span>

<span data-ttu-id="97330-124">Este exemplo obtém os processos em execução no computador local e os envia para uma janela de exibição em grade.</span><span class="sxs-lookup"><span data-stu-id="97330-124">This example gets the processes running on the local computer and sends them to a grid view window.</span></span>

```powershell
Get-Process | Out-GridView
```

### <span data-ttu-id="97330-125">Exemplo 2: usar uma variável para processos de saída para um modo de exibição de grade</span><span class="sxs-lookup"><span data-stu-id="97330-125">Example 2: Use a variable to output processes to a grid view</span></span>

<span data-ttu-id="97330-126">Este exemplo também obtém os processos em execução no computador local e os envia para uma janela de exibição em grade.</span><span class="sxs-lookup"><span data-stu-id="97330-126">This example also gets the processes running on the local computer and sends them to a grid view window.</span></span>

```powershell
$P = Get-Process
$P | Out-GridView
```

<span data-ttu-id="97330-127">A saída do `Get-Process` cmdlet é salva na `$P` variável.</span><span class="sxs-lookup"><span data-stu-id="97330-127">The output of the `Get-Process` cmdlet is saved in the `$P` variable.</span></span> <span data-ttu-id="97330-128">Em seguida, `$P` é canalizado para `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="97330-128">Then, `$P` is piped to `Out-GridView`.</span></span>

### <span data-ttu-id="97330-129">Exemplo 3: exibir as propriedades selecionadas em um modo de exibição de grade</span><span class="sxs-lookup"><span data-stu-id="97330-129">Example 3: Display a selected properties in a grid view</span></span>

<span data-ttu-id="97330-130">Este exemplo exibe as propriedades selecionadas dos processos em execução em um modo de exibição de grade.</span><span class="sxs-lookup"><span data-stu-id="97330-130">This example displays selected properties of the running processes in a grid view.</span></span>

```powershell
Get-Process | Select-Object -Property Name, WorkingSet, PeakWorkingSet |
  Sort-Object -Property WorkingSet -Descending | Out-GridView
```

<span data-ttu-id="97330-131">A saída de `Get-Process` é canalizada para `Select-Object` para selecionar as propriedades **Name**, **WorkingSet** e **PeakWorkingSet** .</span><span class="sxs-lookup"><span data-stu-id="97330-131">The output of `Get-Process` is piped to `Select-Object` to select the **Name**, **WorkingSet**, and **PeakWorkingSet** properties.</span></span> <span data-ttu-id="97330-132">Outro operador de pipeline envia os objetos filtrados para o `Sort-Object` cmdlet para classificá-los em ordem decrescente pelo valor da propriedade **WorkingSet** .</span><span class="sxs-lookup"><span data-stu-id="97330-132">Another pipeline operator sends the filtered objects to the `Sort-Object` cmdlet to sort them in descending order by the value of the **WorkingSet** property.</span></span>
<span data-ttu-id="97330-133">Em seguida, os resultados classificados são canalizados para `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="97330-133">Then, the sorted results are piped to `Out-GridView`.</span></span> <span data-ttu-id="97330-134">Agora você pode usar os recursos de exibição em grade para pesquisar, classificar e filtrar os dados.</span><span class="sxs-lookup"><span data-stu-id="97330-134">You can now use the features of the grid view to search, sort, and filter the data.</span></span>

### <span data-ttu-id="97330-135">Exemplo 4: salvar a saída em uma variável e, em seguida, gerar uma exibição de grade</span><span class="sxs-lookup"><span data-stu-id="97330-135">Example 4: Save output to a variable, and then output a grid view</span></span>

<span data-ttu-id="97330-136">Esse exemplo salva a saída do cmdlet em uma variável e a envia para `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="97330-136">This example saves cmdlet output in a variable then sends it to `Out-GridView`.</span></span>

```powershell
($A = Get-ChildItem -Path $PSHOME -Recurse) | Out-GridView
```

<span data-ttu-id="97330-137">`Get-ChildItem` Obtém todos os arquivos no diretório de instalação do PowerShell e seus subdiretórios usando a `$PSHOME` variável automática.</span><span class="sxs-lookup"><span data-stu-id="97330-137">`Get-ChildItem` gets all the files in the PowerShell installation directory and its subdirectories using the the `$PSHOME` automatic variable.</span></span> <span data-ttu-id="97330-138">Os parênteses no comando estabelecem a ordem das operações.</span><span class="sxs-lookup"><span data-stu-id="97330-138">The parentheses in the command establish the order of operations.</span></span> <span data-ttu-id="97330-139">Como resultado, a saída do `Get-ChildItem` comando é salva na `$A` variável antes de ser enviada para `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="97330-139">As a result, the output from the `Get-ChildItem` command is saved in the `$A` variable before it is sent to `Out-GridView`.</span></span>

### <span data-ttu-id="97330-140">Exemplo 5: processos de saída para um computador especificado para um modo de exibição de grade</span><span class="sxs-lookup"><span data-stu-id="97330-140">Example 5: Output processes for a specified computer to a grid view</span></span>

<span data-ttu-id="97330-141">Este exemplo exibe os processos que estão em execução no computador Server01 em uma janela de exibição em grade.</span><span class="sxs-lookup"><span data-stu-id="97330-141">This example displays the processes that are running on the Server01 computer in a grid view window.</span></span>

```powershell
Get-Process -ComputerName "Server01" | ogv -Title "Processes - Server01"
```

<span data-ttu-id="97330-142">O examle usa `ogv` , que é o alias para o `Out-GridView` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="97330-142">The examle uses `ogv`, which is the alias for the `Out-GridView` cmdlet.</span></span> <span data-ttu-id="97330-143">O parâmetro **title** especifica o título da janela.</span><span class="sxs-lookup"><span data-stu-id="97330-143">The **Title** parameter specifies the window title.</span></span>

### <span data-ttu-id="97330-144">Exemplo 6: dados de saída de computadores remotos para um modo de exibição de grade</span><span class="sxs-lookup"><span data-stu-id="97330-144">Example 6: Output data from remote computers to a grid view</span></span>

<span data-ttu-id="97330-145">Este exemplo mostra como enviar dados coletados de computadores remotos para o `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="97330-145">This example shows how to send data collected from remote computers to `Out-GridView`.</span></span>

```powershell
Invoke-Command -ComputerName S1, S2, S3 -ScriptBlock {Get-Culture} | Out-GridView
```

<span data-ttu-id="97330-146">`Invoke-Command` é executado `Get-Culture` em três computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="97330-146">`Invoke-Command` runs `Get-Culture` on three remote computers.</span></span> <span data-ttu-id="97330-147">Os dados resultantes são canalizados para `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="97330-147">The resulting data is piped to `Out-GridView`.</span></span> <span data-ttu-id="97330-148">Observe que o bloco de script executado no computador remoto não inclui o `Out-GridView` comando.</span><span class="sxs-lookup"><span data-stu-id="97330-148">Notice that the script block that runs on the remote computer does not include the `Out-GridView` command.</span></span> <span data-ttu-id="97330-149">Se incluísse, o comando falharia ao tentar abrir uma janela de exibição em grade em cada um dos computadores remotos.</span><span class="sxs-lookup"><span data-stu-id="97330-149">If it did, the command would fail when it tried to open a grid view window on each of the remote computers.</span></span>

### <span data-ttu-id="97330-150">Exemplo 7: passar vários itens por meio de `Out-GridView`</span><span class="sxs-lookup"><span data-stu-id="97330-150">Example 7: Pass multiple items through `Out-GridView`</span></span>

<span data-ttu-id="97330-151">Este exemplo permite que você selecione vários processos na `Out-GridView` janela.</span><span class="sxs-lookup"><span data-stu-id="97330-151">This example lets you select multiple processes from the `Out-GridView` window.</span></span> <span data-ttu-id="97330-152">Os processos selecionados são passados para o `Export-Csv` comando e gravados no `ProcessLog.csv` arquivo.</span><span class="sxs-lookup"><span data-stu-id="97330-152">The processes that you select are passed to the `Export-Csv` command and written to the `ProcessLog.csv` file.</span></span>

```powershell
Get-Process | Out-GridView -PassThru | Export-Csv -Path .\ProcessLog.csv
```

<span data-ttu-id="97330-153">O parâmetro **PassThru** de `Out-GridView` permite que você envie vários itens por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="97330-153">The **PassThru** parameter of `Out-GridView` lets you send multiple items down the pipeline.</span></span> <span data-ttu-id="97330-154">O parâmetro **PassThru** é equivalente a usar o valor **Multiple** do parâmetro **OutputMode**.</span><span class="sxs-lookup"><span data-stu-id="97330-154">The **PassThru** parameter is equivalent to using the **Multiple** value of the **OutputMode** parameter.</span></span>

### <span data-ttu-id="97330-155">Exemplo 8: criar um atalho do Windows para `Out-GridView`</span><span class="sxs-lookup"><span data-stu-id="97330-155">Example 8: Create a Windows shortcut to `Out-GridView`</span></span>

<span data-ttu-id="97330-156">Este exemplo mostra como usar o parâmetro **Wait** do `Out-GridView` para criar um atalho do Windows para a `Out-GridView` janela.</span><span class="sxs-lookup"><span data-stu-id="97330-156">This example shows how to use the **Wait** parameter of `Out-GridView` to create a Windows shortcut to the `Out-GridView` window.</span></span>

```powershell
pwsh -Command "Get-Service | Out-GridView -Wait"
```

<span data-ttu-id="97330-157">Essa linha de comando pode ser usada em um atalho do Windows.</span><span class="sxs-lookup"><span data-stu-id="97330-157">This command line can be used in a Windows shortcut.</span></span> <span data-ttu-id="97330-158">Sem o parâmetro **Wait** , o PowerShell será encerrado assim que a `Out-GridView` janela fosse aberta, o que fecharia a `Out-GridView` janela quase imediatamente.</span><span class="sxs-lookup"><span data-stu-id="97330-158">Without the **Wait** parameter, PowerShell would exit as soon as the `Out-GridView` window opened, which would close the `Out-GridView` window almost immediately.</span></span>

## <span data-ttu-id="97330-159">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="97330-159">PARAMETERS</span></span>

### <span data-ttu-id="97330-160">-InputObject</span><span class="sxs-lookup"><span data-stu-id="97330-160">-InputObject</span></span>

<span data-ttu-id="97330-161">Especifica o objeto que o cmdlet aceita como entrada para `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="97330-161">Specifies object that the cmdlet accepts as input for `Out-GridView`.</span></span>

<span data-ttu-id="97330-162">Quando você usa o parâmetro **InputObject** para enviar uma coleção de objetos ao `Out-GridView` , `Out-GridView` o trata a coleção como um objeto de coleção e exibe uma linha que representa a coleção.</span><span class="sxs-lookup"><span data-stu-id="97330-162">When you use the **InputObject** parameter to send a collection of objects to `Out-GridView`, `Out-GridView` treats the collection as one collection object, and it displays one row that represents the collection.</span></span> <span data-ttu-id="97330-163">Para exibir cada objeto na coleção, use um operador de pipeline ( `|` ) para enviar objetos para o `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="97330-163">To display the each object in the collection, use a pipeline operator (`|`) to send objects to `Out-GridView`.</span></span>

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

### <span data-ttu-id="97330-164">-OutputType</span><span class="sxs-lookup"><span data-stu-id="97330-164">-OutputMode</span></span>

<span data-ttu-id="97330-165">Especifica os itens que a janela interativa envia ao pipeline como entrada para outros comandos.</span><span class="sxs-lookup"><span data-stu-id="97330-165">Specifies the items that the interactive window sends down the pipeline as input to other commands.</span></span>
<span data-ttu-id="97330-166">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="97330-166">By default, this cmdlet does not generate any output.</span></span> <span data-ttu-id="97330-167">Para enviar itens da janela interativa pelo pipeline, clique para selecionar os itens e, em seguida, clique em OK.</span><span class="sxs-lookup"><span data-stu-id="97330-167">To send items from the interactive window down the pipeline, click to select the items and then click OK.</span></span>

<span data-ttu-id="97330-168">Os valores desse parâmetro determinam quantos itens você pode enviar pelo pipeline.</span><span class="sxs-lookup"><span data-stu-id="97330-168">The values of this parameter determine how many items you can send down the pipeline.</span></span>

- <span data-ttu-id="97330-169">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="97330-169">None.</span></span>  <span data-ttu-id="97330-170">Nenhum item.</span><span class="sxs-lookup"><span data-stu-id="97330-170">No items.</span></span> <span data-ttu-id="97330-171">Esse é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="97330-171">This is the default value.</span></span>
- <span data-ttu-id="97330-172">Única.</span><span class="sxs-lookup"><span data-stu-id="97330-172">Single.</span></span> <span data-ttu-id="97330-173">Zero itens ou um item.</span><span class="sxs-lookup"><span data-stu-id="97330-173">Zero items or one item.</span></span> <span data-ttu-id="97330-174">Use esse valor quando o próximo comando puder levar apenas um objeto de entrada.</span><span class="sxs-lookup"><span data-stu-id="97330-174">Use this value when the next command can take only one input object.</span></span>
- <span data-ttu-id="97330-175">Vários.</span><span class="sxs-lookup"><span data-stu-id="97330-175">Multiple.</span></span> <span data-ttu-id="97330-176">Zero, um ou muitos itens.</span><span class="sxs-lookup"><span data-stu-id="97330-176">Zero, one, or many items.</span></span> <span data-ttu-id="97330-177">Use esse valor quando o próximo comando puder levar vários objetos de entrada.</span><span class="sxs-lookup"><span data-stu-id="97330-177">Use this value when the next command can take multiple input objects.</span></span> <span data-ttu-id="97330-178">Esse valor é equivalente ao parâmetro **Passthru**.</span><span class="sxs-lookup"><span data-stu-id="97330-178">This value is equivalent to the **Passthru** parameter.</span></span>

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

### <span data-ttu-id="97330-179">-PassThru</span><span class="sxs-lookup"><span data-stu-id="97330-179">-PassThru</span></span>

<span data-ttu-id="97330-180">Indica que o cmdlet envia itens da janela interativa para baixo no pipeline como entrada para outros comandos.</span><span class="sxs-lookup"><span data-stu-id="97330-180">Indicates that the cmdlet sends items from the interactive window down the pipeline as input to other commands.</span></span> <span data-ttu-id="97330-181">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="97330-181">By default, this cmdlet does not generate any output.</span></span> <span data-ttu-id="97330-182">Este parâmetro é equivalente a usar o valor **Multiple** do parâmetro **OutputMode**.</span><span class="sxs-lookup"><span data-stu-id="97330-182">This parameter is equivalent to using the **Multiple** value of the **OutputMode** parameter.</span></span>

<span data-ttu-id="97330-183">Para enviar itens da janela interativa pelo pipeline, clique para selecionar os itens e, em seguida, clique em OK.</span><span class="sxs-lookup"><span data-stu-id="97330-183">To send items from the interactive window down the pipeline, click to select the items and then click OK.</span></span> <span data-ttu-id="97330-184">Shift+clique e Ctrl+clique são suportados.</span><span class="sxs-lookup"><span data-stu-id="97330-184">Shift-click and Ctrl-click are supported.</span></span>

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

### <span data-ttu-id="97330-185">-Title</span><span class="sxs-lookup"><span data-stu-id="97330-185">-Title</span></span>

<span data-ttu-id="97330-186">Especifica o texto que aparece na barra de título da `Out-GridView` janela.</span><span class="sxs-lookup"><span data-stu-id="97330-186">Specifies the text that appears in the title bar of the `Out-GridView` window.</span></span> <span data-ttu-id="97330-187">Por padrão, a barra de título exibe o comando que invoca `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="97330-187">By default, the title bar displays the command that invokes `Out-GridView`.</span></span>

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

### <span data-ttu-id="97330-188">-Wait</span><span class="sxs-lookup"><span data-stu-id="97330-188">-Wait</span></span>

<span data-ttu-id="97330-189">Indica que o cmdlet suprime o prompt de comando e impede que o Windows PowerShell seja fechado até que a `Out-GridView` janela seja fechada.</span><span class="sxs-lookup"><span data-stu-id="97330-189">Indicates that the cmdlet suppresses the command prompt and prevents Windows PowerShell from closing until the `Out-GridView` window is closed.</span></span> <span data-ttu-id="97330-190">Por padrão, o prompt de comando retorna quando a `Out-GridView` janela é aberta.</span><span class="sxs-lookup"><span data-stu-id="97330-190">By default, the command prompt returns when the `Out-GridView` window opens.</span></span>

<span data-ttu-id="97330-191">Esse recurso permite que você use os `Out-GridView` cmdlets em atalhos do Windows.</span><span class="sxs-lookup"><span data-stu-id="97330-191">This feature lets you use the `Out-GridView` cmdlets in Windows shortcuts.</span></span> <span data-ttu-id="97330-192">Quando `Out-GridView` é usado em um atalho sem o parâmetro **Wait** , a `Out-GridView` janela aparece apenas momentaneamente antes de o PowerShell fechar.</span><span class="sxs-lookup"><span data-stu-id="97330-192">When `Out-GridView` is used in a shortcut without the **Wait** parameter, the `Out-GridView` window appears only momentarily before PowerShell closes.</span></span>

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

### <span data-ttu-id="97330-193">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="97330-193">CommonParameters</span></span>

<span data-ttu-id="97330-194">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="97330-194">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="97330-195">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="97330-195">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="97330-196">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="97330-196">INPUTS</span></span>

### <span data-ttu-id="97330-197">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="97330-197">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="97330-198">Você pode enviar qualquer objeto para este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="97330-198">You can send any object to this cmdlet.</span></span>

## <span data-ttu-id="97330-199">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="97330-199">OUTPUTS</span></span>

### <span data-ttu-id="97330-200">Nenhum</span><span class="sxs-lookup"><span data-stu-id="97330-200">None</span></span>

<span data-ttu-id="97330-201">Normalmente, `Out-GridView` o não retorna nenhum objeto.</span><span class="sxs-lookup"><span data-stu-id="97330-201">Normally, `Out-GridView` does not return any objects.</span></span> <span data-ttu-id="97330-202">Ao usar o parâmetro **PassThru** , os objetos que representam as linhas selecionadas são retornados para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="97330-202">When using the **PassThru** parameter, the objects representing the selected rows are returned to the pipeline.</span></span>

## <span data-ttu-id="97330-203">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="97330-203">NOTES</span></span>

<span data-ttu-id="97330-204">Esse cmdlet só está disponível em plataformas Windows.</span><span class="sxs-lookup"><span data-stu-id="97330-204">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="97330-205">Você não pode usar um comando remoto para abrir uma janela de exibição em grade em outro computador.</span><span class="sxs-lookup"><span data-stu-id="97330-205">You cannot use a remote command to open a grid view window on another computer.</span></span>

<span data-ttu-id="97330-206">A saída do comando que você envia para `Out-GridView` não pode ser formatada usando os `Format` cmdlets, como `Format-Table` ou `Format-Wide` cmdlets.</span><span class="sxs-lookup"><span data-stu-id="97330-206">The command output that you send to `Out-GridView` cannot be formatted using the `Format` cmdlets, such as `Format-Table` or `Format-Wide` cmdlets.</span></span> <span data-ttu-id="97330-207">Para selecionar propriedades, use o `Select-Object` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="97330-207">To select properties, use the `Select-Object` cmdlet.</span></span>

<span data-ttu-id="97330-208">Resultado desserializado de comandos remotos podem não ser formatados corretamente na janela de exibição em grade.</span><span class="sxs-lookup"><span data-stu-id="97330-208">Deserialized output from remote commands might not be formatted correctly in the grid view window.</span></span>

<span data-ttu-id="97330-209">**Atalhos de teclado para**`Out-GridView`</span><span class="sxs-lookup"><span data-stu-id="97330-209">**Keyboard Shortcuts for** `Out-GridView`</span></span>

|              <span data-ttu-id="97330-210">Use esta tecla:</span><span class="sxs-lookup"><span data-stu-id="97330-210">Use this key:</span></span>              |                                   <span data-ttu-id="97330-211">Para executar esta ação:</span><span class="sxs-lookup"><span data-stu-id="97330-211">To perform this action:</span></span>                                    |
| --------------------------------------- | -------------------------------------------------------------------------------------------- |
| <span data-ttu-id="97330-212"><kbd>Tab</kbd></span><span class="sxs-lookup"><span data-stu-id="97330-212"><kbd>Tab</kbd></span></span>                          | <span data-ttu-id="97330-213">Move o cursor da caixa de **filtro** para o menu **Adicionar critérios** para a tabela e de volta.</span><span class="sxs-lookup"><span data-stu-id="97330-213">Moves the cursor from the **Filter** box to the **Add criteria** menu to the table and back.</span></span> |
| <span data-ttu-id="97330-214"><kbd>Upseta</kbd></span><span class="sxs-lookup"><span data-stu-id="97330-214"><kbd>UpArrow</kbd></span></span>                      | <span data-ttu-id="97330-215">Mover uma linha para cima.</span><span class="sxs-lookup"><span data-stu-id="97330-215">Move up one row.</span></span> <span data-ttu-id="97330-216">Move para cabeçalhos de coluna da primeira linha de dados.</span><span class="sxs-lookup"><span data-stu-id="97330-216">Moves to column headers from first row of data.</span></span>                             |
| <span data-ttu-id="97330-217"><kbd>Seta</kbd></span><span class="sxs-lookup"><span data-stu-id="97330-217"><kbd>DownArrow</kbd></span></span>                    | <span data-ttu-id="97330-218">Mover uma linha para baixo.</span><span class="sxs-lookup"><span data-stu-id="97330-218">Move down one row.</span></span>                                                                           |
| <span data-ttu-id="97330-219"><kbd>LeftArrow</kbd></span><span class="sxs-lookup"><span data-stu-id="97330-219"><kbd>LeftArrow</kbd></span></span>                    | <span data-ttu-id="97330-220">Na linha de cabeçalho da coluna, mova uma coluna para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="97330-220">In column header row, move left one column.</span></span>                                                  |
| <span data-ttu-id="97330-221"><kbd>RightArrow</kbd></span><span class="sxs-lookup"><span data-stu-id="97330-221"><kbd>RightArrow</kbd></span></span>                   | <span data-ttu-id="97330-222">Na linha de cabeçalho da coluna, mova uma coluna para a direita.</span><span class="sxs-lookup"><span data-stu-id="97330-222">In column header row, move right one column.</span></span>                                                 |
| <span data-ttu-id="97330-223"><kbd>ContextMenuKey</kbd></span><span class="sxs-lookup"><span data-stu-id="97330-223"><kbd>ContextMenuKey</kbd></span></span>               | <span data-ttu-id="97330-224">Na linha de cabeçalho da coluna, exibe a opção Selecionar colunas.</span><span class="sxs-lookup"><span data-stu-id="97330-224">In column header row, displays the Select Columns option.</span></span>                                    |
| <span data-ttu-id="97330-225"><kbd>Inserir</kbd> ou <kbd>barra de espaços</kbd></span><span class="sxs-lookup"><span data-stu-id="97330-225"><kbd>Enter</kbd> or <kbd>Spacebar</kbd></span></span> | <span data-ttu-id="97330-226">Na linha de cabeçalho da coluna, classifique os dados da coluna (alterne para A-Z, Z-A).</span><span class="sxs-lookup"><span data-stu-id="97330-226">In column header row, sort column data (toggle A-Z, Z-A).</span></span>                                    |

<span data-ttu-id="97330-227">**Como usar os recursos da janela de exibição em grade**</span><span class="sxs-lookup"><span data-stu-id="97330-227">**How to Use the Grid View Window Features**</span></span>

<span data-ttu-id="97330-228">**Para ocultar ou mostrar uma coluna:**</span><span class="sxs-lookup"><span data-stu-id="97330-228">**To hide or show a column:**</span></span>

1. <span data-ttu-id="97330-229">Clique com o botão direito do mouse em qualquer cabeçalho de coluna e clique em **selecionar colunas**.</span><span class="sxs-lookup"><span data-stu-id="97330-229">Right-click any column header and click **Select Columns**.</span></span>
2. <span data-ttu-id="97330-230">Na caixa de diálogo **selecionar colunas** , use as teclas de direção para mover as colunas entre as colunas selecionadas para as caixas colunas disponíveis.</span><span class="sxs-lookup"><span data-stu-id="97330-230">In the **Select Columns** dialog box, use the arrow keys to move the columns between the Selected columns to the Available columns boxes.</span></span> <span data-ttu-id="97330-231">Somente as colunas na caixa **selecionar colunas** aparecem na janela de exibição em grade.</span><span class="sxs-lookup"><span data-stu-id="97330-231">Only columns in the **Select Columns** box appear in the grid view window.</span></span>

<span data-ttu-id="97330-232">**Para reordenar colunas:**</span><span class="sxs-lookup"><span data-stu-id="97330-232">**To reorder columns:**</span></span>

<span data-ttu-id="97330-233">Você pode arrastar e soltar colunas no local desejado.</span><span class="sxs-lookup"><span data-stu-id="97330-233">You can drag and drop columns into the desired location.</span></span> <span data-ttu-id="97330-234">Ou use as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="97330-234">Or use the following steps:</span></span>

1. <span data-ttu-id="97330-235">Clique com o botão direito do mouse em qualquer cabeçalho de coluna e clique em **selecionar colunas**.</span><span class="sxs-lookup"><span data-stu-id="97330-235">Right-click any column header and click **Select Columns**.</span></span>
2. <span data-ttu-id="97330-236">Na caixa de diálogo **selecionar colunas** , use os botões **mover para cima** e mover para **baixo** para reordenar as colunas.</span><span class="sxs-lookup"><span data-stu-id="97330-236">In the **Select Columns** dialog box, use the **Move up** and **Move down** buttons to reorder the columns.</span></span> <span data-ttu-id="97330-237">As colunas na parte superior da lista aparecem à esquerda das colunas na parte inferior da lista na janela de exibição em grade.</span><span class="sxs-lookup"><span data-stu-id="97330-237">Columns at the top of the list appear to the left of columns at the bottom of the list in the grid view window.</span></span>

<span data-ttu-id="97330-238">**Como classificar dados de tabela**</span><span class="sxs-lookup"><span data-stu-id="97330-238">**How to Sort Table Data**</span></span>

- <span data-ttu-id="97330-239">Para classificar os dados, clique em um cabeçalho de coluna.</span><span class="sxs-lookup"><span data-stu-id="97330-239">To sort the data, click a column header.</span></span>
- <span data-ttu-id="97330-240">Para alterar a ordem de classificação, clique no cabeçalho da coluna novamente.</span><span class="sxs-lookup"><span data-stu-id="97330-240">To change the sort order, click the column header again.</span></span> <span data-ttu-id="97330-241">Cada vez que você clicar no mesmo cabeçalho, a ordem de classificação alterna entre crescente para decrescente.</span><span class="sxs-lookup"><span data-stu-id="97330-241">Each time you click the same header, the sort order toggles between ascending to descending order.</span></span> <span data-ttu-id="97330-242">O pedido atual é indicado por um triângulo no cabeçalho da coluna.</span><span class="sxs-lookup"><span data-stu-id="97330-242">The current order is indicated by a triangle in the column header.</span></span>

<span data-ttu-id="97330-243">**Como selecionar dados da tabela**</span><span class="sxs-lookup"><span data-stu-id="97330-243">**How to Select Table Data**</span></span>

- <span data-ttu-id="97330-244">Para selecionar uma linha, selecione a linha ou use a seta para cima ou para baixo para navegar até a linha.</span><span class="sxs-lookup"><span data-stu-id="97330-244">To select a row, select the row or use the up or down arrow to navigate to the row.</span></span>
- <span data-ttu-id="97330-245">Para selecionar todas as linhas (exceto para a linha de cabeçalho), pressione <kbd>Ctrl</kbd> + <kbd>A</kbd>.</span><span class="sxs-lookup"><span data-stu-id="97330-245">To select all rows (except for the header row), press <kbd>CTRL</kbd>+<kbd>A</kbd>.</span></span>
- <span data-ttu-id="97330-246">Para selecionar linhas consecutivas, pressione e segure a tecla <kbd>Shift</kbd> enquanto clica nas linhas ou usando as teclas de direção.</span><span class="sxs-lookup"><span data-stu-id="97330-246">To select consecutive rows, press and hold the <kbd>SHIFT</kbd> key while clicking the rows or using the arrow keys.</span></span>
- <span data-ttu-id="97330-247">Para selecionar linhas não consecutivas, pressione a tecla <kbd>Ctrl</kbd> e clique para adicionar uma linha à seleção.</span><span class="sxs-lookup"><span data-stu-id="97330-247">To select nonconsecutive rows, press the <kbd>CTRL</kbd> key and click to add a row to the selection.</span></span>
- <span data-ttu-id="97330-248">Não é possível selecionar colunas e nem a linha inteira de cabeçalhos de coluna.</span><span class="sxs-lookup"><span data-stu-id="97330-248">You cannot select columns, and you cannot select the entire column header row.</span></span>

<span data-ttu-id="97330-249">**Como copiar linhas**</span><span class="sxs-lookup"><span data-stu-id="97330-249">**How to Copy Rows**</span></span>

- <span data-ttu-id="97330-250">Para copiar uma ou mais linhas da tabela, selecione as linhas e pressione CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="97330-250">To copy one or more rows from the table, select the rows and then press CTRL+C.</span></span>

  <span data-ttu-id="97330-251">Você pode colar os dados em qualquer programa de texto ou planilha.</span><span class="sxs-lookup"><span data-stu-id="97330-251">You can paste the data into any text or spreadsheet program.</span></span> <span data-ttu-id="97330-252">Não é possível copiar colunas ou partes de linhas e nem a linha de cabeçalhos de coluna.</span><span class="sxs-lookup"><span data-stu-id="97330-252">You cannot copy columns or parts of rows and you cannot copy the column header row.</span></span>

<span data-ttu-id="97330-253">**Como Pesquisar na tabela (filtro rápido)**</span><span class="sxs-lookup"><span data-stu-id="97330-253">**How to Search in the Table (Quick Filter)**</span></span>

<span data-ttu-id="97330-254">Use a caixa de filtro para pesquisar dados na tabela.</span><span class="sxs-lookup"><span data-stu-id="97330-254">Use the Filter box to search for data in the table.</span></span> <span data-ttu-id="97330-255">Quando você digita na caixa, somente os itens que incluem o texto digitado são exibidos na tabela.</span><span class="sxs-lookup"><span data-stu-id="97330-255">When you type in the box, only items that include the typed text appear in the table.</span></span>

- <span data-ttu-id="97330-256">Pesquise por texto.</span><span class="sxs-lookup"><span data-stu-id="97330-256">Search for text.</span></span> <span data-ttu-id="97330-257">Para Pesquisar texto na tabela, na caixa filtro, digite o texto a ser localizado.</span><span class="sxs-lookup"><span data-stu-id="97330-257">To search for text in the table, in the Filter box, type the text to find.</span></span>
- <span data-ttu-id="97330-258">Pesquise por várias palavras.</span><span class="sxs-lookup"><span data-stu-id="97330-258">Search for multiple words.</span></span> <span data-ttu-id="97330-259">Para pesquisar várias palavras na tabela, digite as palavras separadas por espaços.</span><span class="sxs-lookup"><span data-stu-id="97330-259">To search for multiple words in the table, type the words separated by spaces.</span></span> <span data-ttu-id="97330-260">`Out-GridView` exibe as linhas que incluem todas as palavras (AND lógico).</span><span class="sxs-lookup"><span data-stu-id="97330-260">`Out-GridView` displays rows that include all the words (logical AND).</span></span>
- <span data-ttu-id="97330-261">Procure frases literais.</span><span class="sxs-lookup"><span data-stu-id="97330-261">Search for literal phrases.</span></span> <span data-ttu-id="97330-262">Para pesquisar frases que incluam espaços ou caracteres especiais, coloque a frase entre aspas.</span><span class="sxs-lookup"><span data-stu-id="97330-262">To search for phrases that include spaces or special characters, enclose the phrase in quotation marks.</span></span> <span data-ttu-id="97330-263">`Out-GridView` exibe as linhas que incluem uma correspondência exata para a frase.</span><span class="sxs-lookup"><span data-stu-id="97330-263">`Out-GridView` displays rows that include an exact match for the phrase.</span></span>
- <span data-ttu-id="97330-264">Pesquisar em colunas.</span><span class="sxs-lookup"><span data-stu-id="97330-264">Search in columns.</span></span> <span data-ttu-id="97330-265">Para pesquisar texto em uma ou mais colunas, use o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="97330-265">To search for text in one or more columns, use the following format:</span></span>

  `<column>:<text> [<column>:<text>] ...`

  <span data-ttu-id="97330-266">Por exemplo, para localizar "net" na coluna **DisplayName** , na caixa **filtro** , digite:</span><span class="sxs-lookup"><span data-stu-id="97330-266">For example, to find "Net" in the **DisplayName** column, in the **Filter** box, type:</span></span>

  `displayname:net`

  <span data-ttu-id="97330-267">Para localizar linhas com "net" nas colunas **DisplayName** e **Name** , na caixa **filtro** , digite:</span><span class="sxs-lookup"><span data-stu-id="97330-267">To find rows with "Net" in the **DisplayName** and **Name** columns, in the **Filter** box, type:</span></span>

  `displayname:net name:net`

- <span data-ttu-id="97330-268">Desative a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="97330-268">Turn off search.</span></span> <span data-ttu-id="97330-269">Para exibir a tabela inteira novamente, clique no botão X vermelho no canto superior direito da caixa de **filtro** ou exclua o texto da caixa de **filtro** .</span><span class="sxs-lookup"><span data-stu-id="97330-269">To display the entire table again, click the red X button in the top right corner of the **Filter** box or delete the text from the **Filter** box.</span></span>

<span data-ttu-id="97330-270">**Use critérios para filtrar a tabela**</span><span class="sxs-lookup"><span data-stu-id="97330-270">**Use Criteria to Filter the Table**</span></span>

<span data-ttu-id="97330-271">Você pode usar regras ou critérios para determinar quais itens são exibidos na tabela.</span><span class="sxs-lookup"><span data-stu-id="97330-271">You can use rules or criteria to determine which items are displayed in the table.</span></span> <span data-ttu-id="97330-272">Os itens aparecem apenas quando atendem a todos os critérios que você estabelece.</span><span class="sxs-lookup"><span data-stu-id="97330-272">Items appear only when they satisfy all the criteria that you establish.</span></span> <span data-ttu-id="97330-273">Os critérios disponíveis são determinados pelas propriedades dos objetos exibidos na janela de exibição em grade e tipos do .NET Framework dessas propriedades.</span><span class="sxs-lookup"><span data-stu-id="97330-273">The available criteria are determined by the properties of the objects displayed in the grid view window and the .NET Framework types of those properties.</span></span>

<span data-ttu-id="97330-274">Cada critério tem o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="97330-274">Each criterion has the following format:</span></span>

`<column> <operator> <value>`

<span data-ttu-id="97330-275">Os critérios para propriedades diferentes são conectados por **e**.</span><span class="sxs-lookup"><span data-stu-id="97330-275">Criteria for different properties are connected by **AND**.</span></span> <span data-ttu-id="97330-276">Os critérios para a mesma propriedade são conectados por **ou**.</span><span class="sxs-lookup"><span data-stu-id="97330-276">Criteria for the same property are connected by **OR**.</span></span> <span data-ttu-id="97330-277">Você não pode alterar os conectores lógicos.</span><span class="sxs-lookup"><span data-stu-id="97330-277">You cannot change the logical connectors.</span></span>

<span data-ttu-id="97330-278">Os critérios afetam somente a exibição.</span><span class="sxs-lookup"><span data-stu-id="97330-278">The criteria only affects the display.</span></span> <span data-ttu-id="97330-279">Ele não exclui itens da tabela.</span><span class="sxs-lookup"><span data-stu-id="97330-279">It does not delete items from the table.</span></span>

<span data-ttu-id="97330-280">**Como adicionar critérios**</span><span class="sxs-lookup"><span data-stu-id="97330-280">**How to Add Criteria**</span></span>

1. <span data-ttu-id="97330-281">Para exibir o botão de menu **Adicionar critérios** , no canto superior direito da janela, clique na seta de expansão.</span><span class="sxs-lookup"><span data-stu-id="97330-281">To display the **Add criteria** menu button, in the upper right corner of the window, click the Expand arrow.</span></span>
2. <span data-ttu-id="97330-282">Clique no botão de menu **Adicionar critérios** .</span><span class="sxs-lookup"><span data-stu-id="97330-282">Click the **Add Criteria** menu button.</span></span>
3. <span data-ttu-id="97330-283">Clique para selecionar colunas (propriedades).</span><span class="sxs-lookup"><span data-stu-id="97330-283">Click to select columns (properties).</span></span> <span data-ttu-id="97330-284">Você pode selecionar uma ou mais propriedades.</span><span class="sxs-lookup"><span data-stu-id="97330-284">You can select one or many properties.</span></span>
4. <span data-ttu-id="97330-285">Quando terminar de selecionar propriedades, clique no botão **Adicionar** .</span><span class="sxs-lookup"><span data-stu-id="97330-285">When you are finished selecting properties, click the **Add** button.</span></span>
5. <span data-ttu-id="97330-286">Para cancelar as adições, clique em **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="97330-286">To cancel the additions, click **Cancel**.</span></span>
6. <span data-ttu-id="97330-287">Para adicionar mais critérios, clique no botão **Adicionar critérios** novamente.</span><span class="sxs-lookup"><span data-stu-id="97330-287">To add more criteria, click the **Add Criteria** button again.</span></span>

<span data-ttu-id="97330-288">**Como editar um critério**</span><span class="sxs-lookup"><span data-stu-id="97330-288">**How to Edit a Criterion**</span></span>

- <span data-ttu-id="97330-289">Para alterar um operador, clique no valor do operador azul e, em seguida, selecione um operador diferente na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="97330-289">To change an operator, click the blue operator value, and then select a different operator from the drop-down list.</span></span>
- <span data-ttu-id="97330-290">Para inserir ou alterar um valor, digite um valor na caixa valor.</span><span class="sxs-lookup"><span data-stu-id="97330-290">To enter or change a value, type a value in the value box.</span></span> <span data-ttu-id="97330-291">Se você inserir um valor que não é válido, um ícone de X circular aparece.</span><span class="sxs-lookup"><span data-stu-id="97330-291">If you enter a value that is not valid, a circular X icon appears.</span></span> <span data-ttu-id="97330-292">Para removê-lo, altere o valor.</span><span class="sxs-lookup"><span data-stu-id="97330-292">To remove it, change the value.</span></span>
- <span data-ttu-id="97330-293">Para criar uma instrução **ou** , adicione um critério com a mesma propriedade.</span><span class="sxs-lookup"><span data-stu-id="97330-293">To create an **OR** statement, add a criteria with the same property.</span></span>

<span data-ttu-id="97330-294">**Como excluir critérios**</span><span class="sxs-lookup"><span data-stu-id="97330-294">**How to Delete Criteria**</span></span>

- <span data-ttu-id="97330-295">Para excluir os critérios selecionados, clique no X vermelho ao lado de cada critério.</span><span class="sxs-lookup"><span data-stu-id="97330-295">To delete selected criteria, click the red X beside each criterion.</span></span>
- <span data-ttu-id="97330-296">Para excluir todos os critérios, clique no botão **limpar tudo** .</span><span class="sxs-lookup"><span data-stu-id="97330-296">To delete all criteria, click the **Clear All** button.</span></span>

## <span data-ttu-id="97330-297">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="97330-297">RELATED LINKS</span></span>

[<span data-ttu-id="97330-298">Out-File</span><span class="sxs-lookup"><span data-stu-id="97330-298">Out-File</span></span>](Out-File.md)

[<span data-ttu-id="97330-299">Out-Printer</span><span class="sxs-lookup"><span data-stu-id="97330-299">Out-Printer</span></span>](Out-Printer.md)

[<span data-ttu-id="97330-300">Out-String</span><span class="sxs-lookup"><span data-stu-id="97330-300">Out-String</span></span>](Out-String.md)

