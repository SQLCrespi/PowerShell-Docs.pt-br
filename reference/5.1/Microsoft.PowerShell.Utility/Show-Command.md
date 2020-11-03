---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/29/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/show-command?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-Command
ms.openlocfilehash: d3ff6fe599873edafdda04b3fe17ae01d88c049d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193734"
---
# <span data-ttu-id="c4682-103">Show-Command</span><span class="sxs-lookup"><span data-stu-id="c4682-103">Show-Command</span></span>

## <span data-ttu-id="c4682-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="c4682-104">SYNOPSIS</span></span>
<span data-ttu-id="c4682-105">Exibe informações de comando do PowerShell em uma janela gráfica.</span><span class="sxs-lookup"><span data-stu-id="c4682-105">Displays PowerShell command information in a graphical window.</span></span>

## <span data-ttu-id="c4682-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c4682-106">SYNTAX</span></span>

```
Show-Command [[-Name] <String>] [-Height <Double>] [-Width <Double>] [-NoCommonParameter]
 [-ErrorPopup] [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="c4682-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c4682-107">DESCRIPTION</span></span>

<span data-ttu-id="c4682-108">O `Show-Command` cmdlet permite criar um comando do PowerShell em uma janela de comando.</span><span class="sxs-lookup"><span data-stu-id="c4682-108">The `Show-Command` cmdlet lets you create a PowerShell command in a command window.</span></span> <span data-ttu-id="c4682-109">Você pode usar os recursos da janela de comando para executar o comando ou fazê-la retornar o comando para você.</span><span class="sxs-lookup"><span data-stu-id="c4682-109">You can use the features of the command window to run the command or have it return the command to you.</span></span>

<span data-ttu-id="c4682-110">`Show-Command` é uma ferramenta de ensino e aprendizado muito útil.</span><span class="sxs-lookup"><span data-stu-id="c4682-110">`Show-Command` is a very useful teaching and learning tool.</span></span> <span data-ttu-id="c4682-111">`Show-Command` funciona em todos os tipos de comando, incluindo cmdlets, funções, fluxos de trabalho e comandos CIM.</span><span class="sxs-lookup"><span data-stu-id="c4682-111">`Show-Command` works on all command types, including cmdlets, functions, workflows and CIM commands.</span></span>

<span data-ttu-id="c4682-112">Sem parâmetros, `Show-Command` exibe uma janela de comando que lista todos os comandos disponíveis em todos os módulos instalados.</span><span class="sxs-lookup"><span data-stu-id="c4682-112">Without parameters, `Show-Command` displays a command window that lists all available commands in all installed modules.</span></span> <span data-ttu-id="c4682-113">Para localizar os comandos em um módulo, selecione o módulo na lista suspensa Modules.</span><span class="sxs-lookup"><span data-stu-id="c4682-113">To find the commands in a module, select the module from the Modules drop-down list.</span></span> <span data-ttu-id="c4682-114">Para selecionar um comando, clique no nome do comando.</span><span class="sxs-lookup"><span data-stu-id="c4682-114">To select a command, click the command name.</span></span>

<span data-ttu-id="c4682-115">Para usar a janela de comando, selecione um comando, seja usando o nome ou clicando no nome do comando na lista **comandos** .</span><span class="sxs-lookup"><span data-stu-id="c4682-115">To use the command window, select a command, either by using the Name or by clicking the command name in the **Commands** list.</span></span> <span data-ttu-id="c4682-116">Cada conjunto de parâmetros é exibido em uma guia separada. Os asteriscos indicam os parâmetros obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="c4682-116">Each parameter set is displayed on a separate tab. Asterisks indicate the mandatory parameters.</span></span> <span data-ttu-id="c4682-117">Para inserir valores para um parâmetro, digite o valor na caixa de texto ou selecione o valor da caixa suspensa.</span><span class="sxs-lookup"><span data-stu-id="c4682-117">To enter values for a parameter, type the value in the text box or select the value from the drop-down box.</span></span> <span data-ttu-id="c4682-118">Para adicionar um parâmetro de opção, clique para selecionar a caixa de seleção do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="c4682-118">To add a switch parameter, click to select the parameter check box.</span></span>

<span data-ttu-id="c4682-119">Quando estiver pronto, você pode clicar em **Copy** para copiar o comando que criou para a área de transferência ou clicar em **Run** para executar o comando.</span><span class="sxs-lookup"><span data-stu-id="c4682-119">When you're ready, you can click **Copy** to copy the command that you've created to the clipboard or click **Run** to run the command.</span></span> <span data-ttu-id="c4682-120">Você também pode usar o parâmetro **PassThru** para retornar o comando para o programa host, como o console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c4682-120">You can also use the **PassThru** parameter to return the command to the host program, such as the PowerShell console.</span></span> <span data-ttu-id="c4682-121">Para cancelar a seleção de comando e retornar à exibição que exibe todos os comandos, pressione CTRL e clique no comando selecionado.</span><span class="sxs-lookup"><span data-stu-id="c4682-121">To cancel the command selection and return to the view that displays all commands, press Ctrl and click the selected command.</span></span>

<span data-ttu-id="c4682-122">No ISE (ambiente de script integrado) do PowerShell, uma variação da `Show-Command` janela é exibida por padrão.</span><span class="sxs-lookup"><span data-stu-id="c4682-122">In the PowerShell Integrated Scripting Environment (ISE), a variation of the `Show-Command` window is displayed by default.</span></span> <span data-ttu-id="c4682-123">Para obter informações sobre como usar essa janela de comando, consulte os tópicos de ajuda do ISE do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c4682-123">For information about using this command window, see the PowerShell ISE Help topics.</span></span>

<span data-ttu-id="c4682-124">Esse cmdlet foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="c4682-124">This cmdlet was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="c4682-125">Como esse cmdlet requer uma interface do usuário, ele não funciona no Windows Server Core ou no Windows nano Server.</span><span class="sxs-lookup"><span data-stu-id="c4682-125">Because this cmdlet requires a user interface, it does not work on Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="c4682-126">Esse cmdlet só está disponível em sistemas Windows que dão suporte à área de trabalho do Windows.</span><span class="sxs-lookup"><span data-stu-id="c4682-126">This cmdlet is only available on Windows systems that support the Windows Desktop.</span></span>

## <span data-ttu-id="c4682-127">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="c4682-127">EXAMPLES</span></span>

### <span data-ttu-id="c4682-128">Exemplo 1: abrir a janela de comandos</span><span class="sxs-lookup"><span data-stu-id="c4682-128">Example 1: Open the Commands window</span></span>

<span data-ttu-id="c4682-129">Este exemplo exibe a exibição padrão da `Show-Command` janela.</span><span class="sxs-lookup"><span data-stu-id="c4682-129">This example displays the default view of the `Show-Command` window.</span></span> <span data-ttu-id="c4682-130">A janela **comandos** exibe uma lista de todos os comandos em todos os módulos que estão instalados no computador.</span><span class="sxs-lookup"><span data-stu-id="c4682-130">The **Commands** window displays a list of all commands in all modules that are installed on the computer.</span></span>

```powershell
Show-Command
```

### <span data-ttu-id="c4682-131">Exemplo 2: abrir um cmdlet na janela de comandos</span><span class="sxs-lookup"><span data-stu-id="c4682-131">Example 2: Open a cmdlet in the Commands window</span></span>

<span data-ttu-id="c4682-132">Este exemplo exibe o `Invoke-Command` cmdlet na janela de **comando** .</span><span class="sxs-lookup"><span data-stu-id="c4682-132">This example display the `Invoke-Command` cmdlet in the **Command** window.</span></span> <span data-ttu-id="c4682-133">Você pode usar essa exibição para executar `Invoke-Command` comandos.</span><span class="sxs-lookup"><span data-stu-id="c4682-133">You can use this display to run `Invoke-Command` commands.</span></span>

```powershell
Show-Command -Name "Invoke-Command"
```

### <span data-ttu-id="c4682-134">Exemplo 3: abrir um cmdlet com parâmetros especificados</span><span class="sxs-lookup"><span data-stu-id="c4682-134">Example 3: Open a cmdlet with specified parameters</span></span>

<span data-ttu-id="c4682-135">Esse comando abre uma `Show-Command` janela para o `Connect-PSSession` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c4682-135">This command opens a `Show-Command` window for the`Connect-PSSession`cmdlet.</span></span>

```powershell
Show-Command -Name "Connect-PSSession" -Height 700 -Width 1000 -ErrorPopup
```

<span data-ttu-id="c4682-136">Os parâmetros de **altura** e **largura** especificam a dimensão da janela de comando.</span><span class="sxs-lookup"><span data-stu-id="c4682-136">The **Height** and **Width** parameters specify the dimension of the command window.</span></span> <span data-ttu-id="c4682-137">O parâmetro **ErrorPopup** exibe a janela de comando de erro.</span><span class="sxs-lookup"><span data-stu-id="c4682-137">The **ErrorPopup** parameter displays the error command window.</span></span>

<span data-ttu-id="c4682-138">Quando você clica em **executar** , o `Connect-PSSession` comando é executado, assim como faria se você tivesse digitado o `Connect-PSSession` comando na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="c4682-138">When you click **Run** , the `Connect-PSSession` command runs, just as would if you typed the `Connect-PSSession` command at the command line.</span></span>

### <span data-ttu-id="c4682-139">Exemplo 4: especificar novos valores de parâmetro padrão para um cmdlet</span><span class="sxs-lookup"><span data-stu-id="c4682-139">Example 4: Specify new default parameter values for a cmdlet</span></span>

<span data-ttu-id="c4682-140">Este exemplo usa a `$PSDefaultParameterValues` variável automática para definir novos valores padrão para os parâmetros de **altura** , **largura** e **ErrorPopup** do `Show-Command` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c4682-140">This example uses the `$PSDefaultParameterValues` automatic variable to set new default values for the **Height** , **Width** , and **ErrorPopup** parameters of the `Show-Command` cmdlet.</span></span>

```powershell
$PSDefaultParameterValues = @{
    "Show-Command:Height" = 700
    "Show-Command:Width" = 1000
    "Show-Command:ErrorPopup" = $True
}
```

<span data-ttu-id="c4682-141">Agora, quando você executa um `Show-Command` comando, os novos padrões são aplicados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c4682-141">Now when you run a `Show-Command` command, the new defaults are applied automatically.</span></span> <span data-ttu-id="c4682-142">Para usar esses valores padrão em cada sessão do PowerShell, adicione a `$PSDefaultParameterValues` variável ao seu perfil do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c4682-142">To use these default values in every PowerShell session, add the `$PSDefaultParameterValues` variable to your PowerShell profile.</span></span> <span data-ttu-id="c4682-143">Para obter mais informações, consulte [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md) e [about_Parameters_Default_Values](../Microsoft.PowerShell.Core/About/about_Parameters_Default_Values.md).</span><span class="sxs-lookup"><span data-stu-id="c4682-143">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md) and [about_Parameters_Default_Values](../Microsoft.PowerShell.Core/About/about_Parameters_Default_Values.md).</span></span>

### <span data-ttu-id="c4682-144">Exemplo 5: enviar a saída para um modo de exibição de grade</span><span class="sxs-lookup"><span data-stu-id="c4682-144">Example 5: Send output to a grid view</span></span>

<span data-ttu-id="c4682-145">Este comando mostra como usar os `Show-Command` `Out-GridView` cmdlets e juntos.</span><span class="sxs-lookup"><span data-stu-id="c4682-145">This command shows how to use the `Show-Command` and `Out-GridView` cmdlets together.</span></span>

```powershell
Show-Command Get-ChildItem | Out-GridView
```

<span data-ttu-id="c4682-146">O comando usa o `Show-Command` cmdlet para abrir uma janela de comando para o `Get-ChildItem` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c4682-146">The command uses the `Show-Command` cmdlet to open a command window for the`Get-ChildItem`cmdlet.</span></span>
<span data-ttu-id="c4682-147">Quando você clica no botão **executar** , o `Get-ChildItem` comando é executado e gera a saída.</span><span class="sxs-lookup"><span data-stu-id="c4682-147">When you click the **Run** button, the `Get-ChildItem` command runs and generates output.</span></span> <span data-ttu-id="c4682-148">O operador de pipeline (|) envia a saída do `Get-ChildItem` comando para o `Out-GridView` cmdlet, que exibe a `Get-ChildItem` saída em uma janela interativa.</span><span class="sxs-lookup"><span data-stu-id="c4682-148">The pipeline operator ( | ) sends the output of the `Get-ChildItem` command to the `Out-GridView` cmdlet, which displays the `Get-ChildItem` output in an interactive window.</span></span>

### <span data-ttu-id="c4682-149">Exemplo 6: exibir um comando que você cria na janela comandos</span><span class="sxs-lookup"><span data-stu-id="c4682-149">Example 6: Display a command that you create in the Commands window</span></span>

<span data-ttu-id="c4682-150">Este exemplo mostra o comando que você criou na `Show-Command` janela.</span><span class="sxs-lookup"><span data-stu-id="c4682-150">This example shows the command that you created in the `Show-Command` window.</span></span> <span data-ttu-id="c4682-151">O comando usa o parâmetro **PassThru** , que retorna os `Show-Command` resultados em uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="c4682-151">The command uses the **PassThru** parameter, which returns the `Show-Command` results in a string.</span></span>

```powershell
Show-Command -PassThru
```

```Output
Get-EventLog -LogName "Windows PowerShell" -Newest 5
```

<span data-ttu-id="c4682-152">Por exemplo, se você usar a `Show-Command` janela para criar um `Get-EventLog` comando que obtém os cinco eventos mais recentes no log de eventos do Windows PowerShell e, em seguida, clicar em **OK** , o comando retornará a saída mostrada acima.</span><span class="sxs-lookup"><span data-stu-id="c4682-152">For example, if you use the `Show-Command` window to create a `Get-EventLog` command that gets the five newest events in the Windows PowerShell event log, and then click **OK** , the command returns the output shown above.</span></span> <span data-ttu-id="c4682-153">A exibição da cadeia de caracteres de comando ajuda você a aprender o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c4682-153">Viewing the command string helps you learn PowerShell.</span></span>

### <span data-ttu-id="c4682-154">Exemplo 7: salvar um comando em uma variável</span><span class="sxs-lookup"><span data-stu-id="c4682-154">Example 7: Save a command to a variable</span></span>

<span data-ttu-id="c4682-155">Este exemplo mostra como executar a cadeia de caracteres de comando que você obtém ao usar o parâmetro **PassThru** do `Show-Command` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c4682-155">This example shows how to run the command string that you get when you use the **PassThru** parameter of the `Show-Command` cmdlet.</span></span> <span data-ttu-id="c4682-156">Essa estratégia permite ver o comando e usá-lo.</span><span class="sxs-lookup"><span data-stu-id="c4682-156">This strategy lets you see the command and use it.</span></span>

```powershell
$C = Show-Command -PassThru
$C
Invoke-Expression $C
```

```Output
Get-EventLog -LogName "PowerShell" -Newest 5

Index Time          EntryType   Source                 InstanceID Message
----- ----          ---------   ------                 ---------- -------
11520 Dec 16 16:37  Information Windows PowerShell            400 Engine state is changed from None to Available...
11519 Dec 16 16:37  Information Windows PowerShell            600 Provider "Variable" is Started. ...
11518 Dec 16 16:37  Information Windows PowerShell            600 Provider "Registry" is Started. ...
11517 Dec 16 16:37  Information Windows PowerShell            600 Provider "Function" is Started. ...
11516 Dec 16 16:37  Information Windows PowerShell            600 Provider "FileSystem" is Started. ...
```

<span data-ttu-id="c4682-157">O primeiro comando usa o parâmetro **PassThru** do `Show-Command` cmdlet e salva os resultados do comando na `$C` variável.</span><span class="sxs-lookup"><span data-stu-id="c4682-157">The first command uses the **PassThru** parameter of the `Show-Command` cmdlet and saves the results of the command in the `$C` variable.</span></span> <span data-ttu-id="c4682-158">Nesse caso, usamos a `Show-Command` janela para criar um `Get-EventLog` comando que obtém os cinco eventos mais recentes no log de eventos do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c4682-158">In this case, we use the `Show-Command` window to create a `Get-EventLog` command that gets the five newest events in the Windows PowerShell event log.</span></span> <span data-ttu-id="c4682-159">Quando você clica em **OK** , `Show-Command` retorna a cadeia de caracteres de comando, que é salva na `$C` variável.</span><span class="sxs-lookup"><span data-stu-id="c4682-159">When you click **OK** , `Show-Command` returns the command string, which is saved in the `$C` variable.</span></span>

### <span data-ttu-id="c4682-160">Exemplo 8: salvar a saída de um comando em uma variável</span><span class="sxs-lookup"><span data-stu-id="c4682-160">Example 8: Save the output of a command to a variable</span></span>

<span data-ttu-id="c4682-161">Este exemplo usa o parâmetro **ErrorPopup** para salvar a saída de um comando em uma variável.</span><span class="sxs-lookup"><span data-stu-id="c4682-161">This example uses the **ErrorPopup** parameter to save the output of a command in a variable.</span></span>

```powershell
$P = Show-Command Get-Process -ErrorPopup
$P
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    473      33    94096     112532   709     2.06   4492 powershell
```

<span data-ttu-id="c4682-162">Além de exibir erros em uma janela, o **ErrorPopup** retorna a saída do comando para o comando atual, em vez de criar um novo comando.</span><span class="sxs-lookup"><span data-stu-id="c4682-162">In addition to displaying errors in a window, **ErrorPopup** returns command output to the current command, instead of creating a new command.</span></span> <span data-ttu-id="c4682-163">Quando você executar esse comando, a `Show-Command` janela será aberta.</span><span class="sxs-lookup"><span data-stu-id="c4682-163">When you run this command, the `Show-Command` window opens.</span></span> <span data-ttu-id="c4682-164">Você pode usar os recursos de janela para definir valores de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="c4682-164">You can use the window features to set parameter values.</span></span> <span data-ttu-id="c4682-165">Para executar o comando, clique no botão **executar** na `Show-Command` janela.</span><span class="sxs-lookup"><span data-stu-id="c4682-165">To run the command, click the **Run** button in the `Show-Command` window.</span></span>

## <span data-ttu-id="c4682-166">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c4682-166">PARAMETERS</span></span>

### <span data-ttu-id="c4682-167">-ErrorPopup</span><span class="sxs-lookup"><span data-stu-id="c4682-167">-ErrorPopup</span></span>

<span data-ttu-id="c4682-168">Indica que o cmdlet exibe erros em uma janela pop-up, além de exibi-los na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="c4682-168">Indicates that the cmdlet displays errors in a pop-up window, in addition to displaying them at the command line.</span></span> <span data-ttu-id="c4682-169">Por padrão, quando um comando executado em uma `Show-Command` janela gera um erro, o erro é exibido somente na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="c4682-169">By default, when a command that is run in a `Show-Command` window generates an error, the error is displayed only at the command line.</span></span>

<span data-ttu-id="c4682-170">Além disso, quando você executa o comando (usando o botão **executar** na `Show-Command` janela), o parâmetro **ErrorPopup** retorna os resultados do comando para o comando atual, em vez de executar o comando e retornar sua saída para um novo comando.</span><span class="sxs-lookup"><span data-stu-id="c4682-170">Also, when you run the command (by using the **Run** button in the `Show-Command` window), the **ErrorPopup** parameter returns the command results to the current command, instead of running the command and returning its output to a new command.</span></span> <span data-ttu-id="c4682-171">Você pode usar esse recurso para salvar os resultados do comando em uma variável.</span><span class="sxs-lookup"><span data-stu-id="c4682-171">You can use this feature to save the command results in a variable.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c4682-172">-Altura</span><span class="sxs-lookup"><span data-stu-id="c4682-172">-Height</span></span>

<span data-ttu-id="c4682-173">Especifica a altura da `Show-Command` janela em pixels.</span><span class="sxs-lookup"><span data-stu-id="c4682-173">Specifies the height of the `Show-Command` window in pixels.</span></span> <span data-ttu-id="c4682-174">Insira um valor entre 300 e o número de pixels na resolução de tela.</span><span class="sxs-lookup"><span data-stu-id="c4682-174">Enter a value between 300 and the number of pixels in the screen resolution.</span></span> <span data-ttu-id="c4682-175">Se o valor for muito grande para exibir a janela de comando na tela, o `Show-Command` gerará um erro.</span><span class="sxs-lookup"><span data-stu-id="c4682-175">If the value is too large to display the command window on the screen, `Show-Command` generates an error.</span></span> <span data-ttu-id="c4682-176">A altura padrão é 600 pixels.</span><span class="sxs-lookup"><span data-stu-id="c4682-176">The default height is 600 pixels.</span></span> <span data-ttu-id="c4682-177">Para um `Show-Command` comando que inclui o parâmetro **Name** , a altura padrão é de 300 pixels.</span><span class="sxs-lookup"><span data-stu-id="c4682-177">For a `Show-Command` command that includes the **Name** parameter, the default height is 300 pixels.</span></span>

```yaml
Type: System.Double
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c4682-178">-Name</span><span class="sxs-lookup"><span data-stu-id="c4682-178">-Name</span></span>

<span data-ttu-id="c4682-179">Exibe uma janela de comando para o comando especificado.</span><span class="sxs-lookup"><span data-stu-id="c4682-179">Displays a command window for the specified command.</span></span> <span data-ttu-id="c4682-180">Insira o nome de um comando, como o nome de um cmdlet, uma função ou um comando CIM.</span><span class="sxs-lookup"><span data-stu-id="c4682-180">Enter the name of one command, such as the name of a cmdlet, function, or CIM command.</span></span> <span data-ttu-id="c4682-181">Se você omitir esse parâmetro, `Show-Command` o exibirá uma janela de comando que lista todos os comandos do PowerShell em todos os módulos instalados no computador.</span><span class="sxs-lookup"><span data-stu-id="c4682-181">If you omit this parameter, `Show-Command` displays a command window that lists all of the PowerShell commands in all modules installed on the computer.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CommandName

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c4682-182">-NoCommonParameter</span><span class="sxs-lookup"><span data-stu-id="c4682-182">-NoCommonParameter</span></span>

<span data-ttu-id="c4682-183">Indica que esse cmdlet omite a seção de parâmetros comuns da exibição do comando.</span><span class="sxs-lookup"><span data-stu-id="c4682-183">Indicates that this cmdlet omits the Common Parameters section of the command display.</span></span> <span data-ttu-id="c4682-184">Por padrão, Parâmetros Comuns aparece em uma seção expansível na parte inferior da janela de comando.</span><span class="sxs-lookup"><span data-stu-id="c4682-184">By default, the Common Parameters appear in an expandable section at the bottom of the command window.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c4682-185">-PassThru</span><span class="sxs-lookup"><span data-stu-id="c4682-185">-PassThru</span></span>

<span data-ttu-id="c4682-186">Retorna um objeto que representa o item com que você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="c4682-186">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="c4682-187">Por padrão, este cmdlet não gera saída.</span><span class="sxs-lookup"><span data-stu-id="c4682-187">By default, this cmdlet does not generate any output.</span></span> <span data-ttu-id="c4682-188">Para executar a cadeia de caracteres de comando, copie e cole-a no prompt de comando ou salve-a em uma variável e use o `Invoke-Expression` cmdlet para executar a cadeia de caracteres na variável.</span><span class="sxs-lookup"><span data-stu-id="c4682-188">To run the command string, copy and paste it at the command prompt or save it in a variable and use the `Invoke-Expression` cmdlet to run the string in the variable.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c4682-189">-Largura</span><span class="sxs-lookup"><span data-stu-id="c4682-189">-Width</span></span>

<span data-ttu-id="c4682-190">Especifica a largura da `Show-Command` janela em pixels.</span><span class="sxs-lookup"><span data-stu-id="c4682-190">Specifies the width of the `Show-Command` window in pixels.</span></span> <span data-ttu-id="c4682-191">Insira um valor entre 300 e o número de pixels na resolução de tela.</span><span class="sxs-lookup"><span data-stu-id="c4682-191">Enter a value between 300 and the number of pixels in the screen resolution.</span></span> <span data-ttu-id="c4682-192">Se o valor for muito grande para exibir a janela de comando na tela, o `Show-Command` gerará um erro.</span><span class="sxs-lookup"><span data-stu-id="c4682-192">If the value is too large to display the command window on the screen, `Show-Command` generates an error.</span></span> <span data-ttu-id="c4682-193">A largura padrão é 300 pixels.</span><span class="sxs-lookup"><span data-stu-id="c4682-193">The default width is 300 pixels.</span></span>

```yaml
Type: System.Double
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c4682-194">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c4682-194">CommonParameters</span></span>

<span data-ttu-id="c4682-195">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c4682-195">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c4682-196">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c4682-196">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c4682-197">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="c4682-197">INPUTS</span></span>

### <span data-ttu-id="c4682-198">Nenhum</span><span class="sxs-lookup"><span data-stu-id="c4682-198">None</span></span>

<span data-ttu-id="c4682-199">Não é possível canalizar a entrada para `Show-Command` .</span><span class="sxs-lookup"><span data-stu-id="c4682-199">You cannot pipe input to `Show-Command`.</span></span>

## <span data-ttu-id="c4682-200">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="c4682-200">OUTPUTS</span></span>

### <span data-ttu-id="c4682-201">Nenhum, System. String, System. Object</span><span class="sxs-lookup"><span data-stu-id="c4682-201">None, System.String, System.Object</span></span>

<span data-ttu-id="c4682-202">Quando você usa o parâmetro **PassThru** , `Show-Command` retorna uma cadeia de caracteres de comando.</span><span class="sxs-lookup"><span data-stu-id="c4682-202">When you use the **PassThru** parameter, `Show-Command` returns a command string.</span></span> <span data-ttu-id="c4682-203">Quando você usa o parâmetro **ErrorPopup** , `Show-Command` o retorna a saída do comando (qualquer objeto).</span><span class="sxs-lookup"><span data-stu-id="c4682-203">When you use the **ErrorPopup** parameter, `Show-Command` returns the command output (any object).</span></span> <span data-ttu-id="c4682-204">Caso contrário, `Show-Command` o não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="c4682-204">Otherwise, `Show-Command` does not generate any output.</span></span>

## <span data-ttu-id="c4682-205">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="c4682-205">NOTES</span></span>

<span data-ttu-id="c4682-206">`Show-Command` Não funciona em sessões remotas.</span><span class="sxs-lookup"><span data-stu-id="c4682-206">`Show-Command` does not work in remote sessions.</span></span>

## <span data-ttu-id="c4682-207">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="c4682-207">RELATED LINKS</span></span>
