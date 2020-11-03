---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 08/07/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/out-host?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Host
ms.openlocfilehash: e3b009ae92abde371a4a6380d0ac6d491093333f
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192979"
---
# <span data-ttu-id="3ca9a-103">Out-Host</span><span class="sxs-lookup"><span data-stu-id="3ca9a-103">Out-Host</span></span>

## <span data-ttu-id="3ca9a-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="3ca9a-104">SYNOPSIS</span></span>
<span data-ttu-id="3ca9a-105">Envia a saída para a linha de comando.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-105">Sends output to the command line.</span></span>

## <span data-ttu-id="3ca9a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3ca9a-106">SYNTAX</span></span>

### <span data-ttu-id="3ca9a-107">Tudo</span><span class="sxs-lookup"><span data-stu-id="3ca9a-107">All</span></span>

```
Out-Host [-Paging] [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="3ca9a-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3ca9a-108">DESCRIPTION</span></span>

<span data-ttu-id="3ca9a-109">O `Out-Host` cmdlet envia a saída para o host do PowerShell para exibição.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-109">The `Out-Host` cmdlet sends output to the PowerShell host for display.</span></span> <span data-ttu-id="3ca9a-110">O host exibe a saída na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-110">The host displays the output at the command line.</span></span> <span data-ttu-id="3ca9a-111">Como `Out-Host` o é o padrão, você não precisa especificá-lo a menos que queira usar seus parâmetros.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-111">Because `Out-Host` is the default, you don't have to specify it unless you want to use its parameters.</span></span>

<span data-ttu-id="3ca9a-112">`Out-Host` é automaticamente anexado a todos os comandos que são executados.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-112">`Out-Host` is automatically appended to every command that is executed.</span></span> <span data-ttu-id="3ca9a-113">Ele passa a saída do pipeline para o host que executa o comando.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-113">It passes the output of the pipeline to the host executing the command.</span></span> <span data-ttu-id="3ca9a-114">`Out-Host` ignora as sequências de escape ANSI.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-114">`Out-Host` ignores ANSI escape sequences.</span></span> <span data-ttu-id="3ca9a-115">As sequências de escape são tratadas pelo host.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-115">The escape sequences are handled by the host.</span></span> <span data-ttu-id="3ca9a-116">`Out-Host` passa sequências de escape ANSI para o host sem tentar interpretá-las ou alterá-las.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-116">`Out-Host` passes ANSI escape sequences to the host without trying to interpret or change them.</span></span>

## <span data-ttu-id="3ca9a-117">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="3ca9a-117">EXAMPLES</span></span>

### <span data-ttu-id="3ca9a-118">Exemplo 1: exibir uma página de saída por vez</span><span class="sxs-lookup"><span data-stu-id="3ca9a-118">Example 1: Display output one page at a time</span></span>

<span data-ttu-id="3ca9a-119">Este exemplo exibe o sistema processa uma página por vez.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-119">This example displays the system processes one page at a time.</span></span>

```powershell
Get-Process | Out-Host -Paging
```

```Output
NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     30    24.12      36.95      15.86   21004  14 ApplicationFrameHost
     55    24.33      60.48      10.80   12904  14 BCompare
<SPACE> next page; <CR> next line; Q quit
      9     4.71       8.94       0.00   16864  14 explorer
<SPACE> next page; <CR> next line; Q quit
```

<span data-ttu-id="3ca9a-120">`Get-Process` Obtém os processos do sistema e envia os objetos por meio do pipeline.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-120">`Get-Process` gets the system processes and sends the objects down the pipeline.</span></span> <span data-ttu-id="3ca9a-121">`Out-Host` usa o parâmetro **paging** para exibir uma página de dados de cada vez.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-121">`Out-Host` uses the **Paging** parameter to display one page of data at a time.</span></span>

### <span data-ttu-id="3ca9a-122">Exemplo 2: usar uma variável como entrada</span><span class="sxs-lookup"><span data-stu-id="3ca9a-122">Example 2: Use a variable as input</span></span>

<span data-ttu-id="3ca9a-123">Este exemplo usa objetos armazenados em uma variável como entrada para `Out-Host` .</span><span class="sxs-lookup"><span data-stu-id="3ca9a-123">This example uses objects stored in a variable as the input for `Out-Host`.</span></span>

```powershell
$io = Get-History
Out-Host -InputObject $io
```

<span data-ttu-id="3ca9a-124">`Get-History` Obtém o histórico da sessão do PowerShell e armazena os objetos na `$io` variável.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-124">`Get-History` gets the PowerShell session's history, and stores the objects in the `$io` variable.</span></span>
<span data-ttu-id="3ca9a-125">`Out-Host` usa o parâmetro **InputObject** para especificar a `$io` variável e exibe o histórico.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-125">`Out-Host` uses the **InputObject** parameter to specify the `$io` variable and displays the history.</span></span>

## <span data-ttu-id="3ca9a-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3ca9a-126">PARAMETERS</span></span>

### <span data-ttu-id="3ca9a-127">-InputObject</span><span class="sxs-lookup"><span data-stu-id="3ca9a-127">-InputObject</span></span>

<span data-ttu-id="3ca9a-128">Especifica os objetos que são gravados no console.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-128">Specifies the objects that are written to the console.</span></span> <span data-ttu-id="3ca9a-129">Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-129">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="3ca9a-130">-Paginação</span><span class="sxs-lookup"><span data-stu-id="3ca9a-130">-Paging</span></span>

<span data-ttu-id="3ca9a-131">Indica que `Out-Host` o exibe uma página de saída por vez e aguarda a entrada do usuário antes que as páginas restantes sejam exibidas.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-131">Indicates that `Out-Host` displays one page of output at a time, and waits for user input before the remaining pages are displayed.</span></span> <span data-ttu-id="3ca9a-132">Por padrão, toda a saída é exibida em uma única página.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-132">By default, all the output is displayed on a single page.</span></span> <span data-ttu-id="3ca9a-133">O tamanho da página é determinado pelas características do host.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-133">The page size is determined by the characteristics of the host.</span></span>

<span data-ttu-id="3ca9a-134">Pressione a barra de <kbd>espaço</kbd> para exibir a próxima página de saída ou a tecla <kbd>Enter</kbd> para exibir a próxima linha de saída.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-134">Press the <kbd>Space</kbd> bar to display the next page of output or the <kbd>Enter</kbd> key to view the next line of output.</span></span> <span data-ttu-id="3ca9a-135">Pressione <kbd>Q</kbd> para sair.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-135">Press <kbd>Q</kbd> to quit.</span></span>

<span data-ttu-id="3ca9a-136">A **paginação** é semelhante ao comando **more** .</span><span class="sxs-lookup"><span data-stu-id="3ca9a-136">**Paging** is similar to the **more** command.</span></span>

> [!NOTE]
> <span data-ttu-id="3ca9a-137">O host do ISE do PowerShell não dá suporte ao parâmetro de **paginação** .</span><span class="sxs-lookup"><span data-stu-id="3ca9a-137">The **Paging** parameter isn't supported by the PowerShell ISE host.</span></span>

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

### <span data-ttu-id="3ca9a-138">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3ca9a-138">CommonParameters</span></span>

<span data-ttu-id="3ca9a-139">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3ca9a-140">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3ca9a-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3ca9a-141">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="3ca9a-141">INPUTS</span></span>

### <span data-ttu-id="3ca9a-142">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="3ca9a-142">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="3ca9a-143">Você pode enviar objetos pelo pipeline para o `Out-Host` .</span><span class="sxs-lookup"><span data-stu-id="3ca9a-143">You can send objects down the pipeline to `Out-Host`.</span></span>

## <span data-ttu-id="3ca9a-144">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="3ca9a-144">OUTPUTS</span></span>

### <span data-ttu-id="3ca9a-145">Nenhum</span><span class="sxs-lookup"><span data-stu-id="3ca9a-145">None</span></span>

<span data-ttu-id="3ca9a-146">`Out-Host` não gera nenhuma saída.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-146">`Out-Host` doesn't generate any output.</span></span> <span data-ttu-id="3ca9a-147">Ele envia objetos para o host para exibição.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-147">It sends objects to the host for display.</span></span>

## <span data-ttu-id="3ca9a-148">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="3ca9a-148">NOTES</span></span>

<span data-ttu-id="3ca9a-149">O parâmetro de **paginação** não tem suporte de todos os hosts do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-149">The **Paging** parameter isn't supported by all PowerShell hosts.</span></span> <span data-ttu-id="3ca9a-150">Por exemplo, se você usar o parâmetro de **paginação** no ISE do PowerShell, o seguinte erro será exibido: `out-lineoutput : The method or operation is not implemented.`</span><span class="sxs-lookup"><span data-stu-id="3ca9a-150">For example, if you use the **Paging** parameter in the PowerShell ISE, the following error is displayed: `out-lineoutput : The method or operation is not implemented.`</span></span>

<span data-ttu-id="3ca9a-151">Os cmdlets que contêm o verbo **out** , `Out-` , não formatam objetos.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-151">The cmdlets that contain the **Out** verb, `Out-`, don't format objects.</span></span> <span data-ttu-id="3ca9a-152">Eles renderizam objetos e os enviam para o destino de exibição especificado.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-152">They render objects and send them to the specified display destination.</span></span> <span data-ttu-id="3ca9a-153">Se você enviar um objeto não formatado para um `Out-` cmdlet, o cmdlet o enviará a um cmdlet de formatação antes de renderizá-lo.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-153">If you send an unformatted object to an `Out-` cmdlet, the cmdlet sends it to a formatting cmdlet before rendering it.</span></span>

<span data-ttu-id="3ca9a-154">Os `Out-` cmdlets não têm parâmetros para nomes ou caminhos de arquivo.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-154">The `Out-` cmdlets don't have parameters for names or file paths.</span></span> <span data-ttu-id="3ca9a-155">Para enviar dados a um `Out-` cmdlet, use o pipeline para enviar a saída de um comando do PowerShell para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-155">To send data to an `Out-` cmdlet, use the pipeline to send a PowerShell command's output to the cmdlet.</span></span> <span data-ttu-id="3ca9a-156">Ou você pode armazenar dados em uma variável e usar o parâmetro **InputObject** para passar os dados para o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-156">Or, you can store data in a variable and use the **InputObject** parameter to pass the data to the cmdlet.</span></span>

<span data-ttu-id="3ca9a-157">`Out-Host` envia dados, mas não produz nenhum objeto de saída.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-157">`Out-Host` sends data, but it doesn't produce any output objects.</span></span> <span data-ttu-id="3ca9a-158">Se você canalizar a saída do `Out-Host` para o `Get-Member` cmdlet, o `Get-Member` relatará que nenhum objeto foi especificado.</span><span class="sxs-lookup"><span data-stu-id="3ca9a-158">If you pipeline the output of `Out-Host` to the `Get-Member` cmdlet, `Get-Member` reports that no objects have been specified.</span></span>

## <span data-ttu-id="3ca9a-159">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="3ca9a-159">RELATED LINKS</span></span>

[<span data-ttu-id="3ca9a-160">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="3ca9a-160">Clear-Host</span></span>](Clear-Host.md)

[<span data-ttu-id="3ca9a-161">Out-Default</span><span class="sxs-lookup"><span data-stu-id="3ca9a-161">Out-Default</span></span>](Out-Default.md)

[<span data-ttu-id="3ca9a-162">Out-File</span><span class="sxs-lookup"><span data-stu-id="3ca9a-162">Out-File</span></span>](../Microsoft.PowerShell.Utility/Out-File.md)

[<span data-ttu-id="3ca9a-163">Out-Null</span><span class="sxs-lookup"><span data-stu-id="3ca9a-163">Out-Null</span></span>](Out-Null.md)

[<span data-ttu-id="3ca9a-164">Out-Printer</span><span class="sxs-lookup"><span data-stu-id="3ca9a-164">Out-Printer</span></span>](../Microsoft.PowerShell.Utility/Out-Printer.md)

[<span data-ttu-id="3ca9a-165">Out-String</span><span class="sxs-lookup"><span data-stu-id="3ca9a-165">Out-String</span></span>](../Microsoft.PowerShell.Utility/Out-String.md)

[<span data-ttu-id="3ca9a-166">Write-Host</span><span class="sxs-lookup"><span data-stu-id="3ca9a-166">Write-Host</span></span>](../Microsoft.PowerShell.Utility/Write-Host.md)
