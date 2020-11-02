---
ms.date: 12/31/2019
title: O objeto ISEEditor
description: Um objeto ISEEditor é uma instância da classe Microsoft.PowerShell.Host.ISE.ISEEditor. O painel de Console é um objeto ISEEditor.
ms.openlocfilehash: ffcb6e35e1160beab6efb29cc84847fa9ffd012b
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92654056"
---
# <a name="the-iseeditor-object"></a><span data-ttu-id="21185-104">O objeto ISEEditor</span><span class="sxs-lookup"><span data-stu-id="21185-104">The ISEEditor Object</span></span>

<span data-ttu-id="21185-105">Um objeto **ISEEditor** é uma instância da classe Microsoft.PowerShell.Host.ISE.ISEEditor.</span><span class="sxs-lookup"><span data-stu-id="21185-105">An **ISEEditor** object is an instance of the Microsoft.PowerShell.Host.ISE.ISEEditor class.</span></span> <span data-ttu-id="21185-106">O painel de Console é um objeto **ISEEditor** .</span><span class="sxs-lookup"><span data-stu-id="21185-106">The Console pane is an **ISEEditor** object.</span></span> <span data-ttu-id="21185-107">Cada objeto [ISEFile](The-ISEFile-Object.md) tem um objeto **ISEEditor** associado.</span><span class="sxs-lookup"><span data-stu-id="21185-107">Each [ISEFile](The-ISEFile-Object.md) object has an associated **ISEEditor** object.</span></span> <span data-ttu-id="21185-108">As seções a seguir listam os métodos e as propriedades de um objeto **ISEEditor** .</span><span class="sxs-lookup"><span data-stu-id="21185-108">The following sections list the methods and properties of an **ISEEditor** object.</span></span>

## <a name="methods"></a><span data-ttu-id="21185-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="21185-109">Methods</span></span>

### <a name="clear"></a><span data-ttu-id="21185-110">Clear\(\)</span><span class="sxs-lookup"><span data-stu-id="21185-110">Clear\(\)</span></span>

<span data-ttu-id="21185-111">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="21185-111">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="21185-112">Apaga o texto no editor.</span><span class="sxs-lookup"><span data-stu-id="21185-112">Clears the text in the editor.</span></span>

```powershell
# Clears the text in the Console pane.
$psISE.CurrentPowerShellTab.ConsolePane.Clear()
```

### <a name="ensurevisibleint-linenumber"></a><span data-ttu-id="21185-113">EnsureVisible\(int lineNumber\)</span><span class="sxs-lookup"><span data-stu-id="21185-113">EnsureVisible\(int lineNumber\)</span></span>

<span data-ttu-id="21185-114">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="21185-114">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="21185-115">Rola o editor de modo que a linha que corresponde ao valor do parâmetro **lineNumber** especificado fique visível.</span><span class="sxs-lookup"><span data-stu-id="21185-115">Scrolls the editor so that the line that corresponds to the specified **lineNumber** parameter value is visible.</span></span> <span data-ttu-id="21185-116">Gerará uma exceção se o número de linha especificado estiver fora do intervalo de 1, último número da linha, que define os números de linha válidos.</span><span class="sxs-lookup"><span data-stu-id="21185-116">It throws an exception if the specified line number is outside the range of 1,last line number, which defines the valid line numbers.</span></span>

<span data-ttu-id="21185-117">**lineNumber** O número da linha que deve ficar visível.</span><span class="sxs-lookup"><span data-stu-id="21185-117">**lineNumber** The number of the line that is to be made visible.</span></span>

```powershell
# Scrolls the text in the Script pane so that the fifth line is in view.
$psISE.CurrentFile.Editor.EnsureVisible(5)
```

### <a name="focus"></a><span data-ttu-id="21185-118">Focus\(\)</span><span class="sxs-lookup"><span data-stu-id="21185-118">Focus\(\)</span></span>

<span data-ttu-id="21185-119">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="21185-119">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="21185-120">Define o foco para o editor.</span><span class="sxs-lookup"><span data-stu-id="21185-120">Sets the focus to the editor.</span></span>

```powershell
# Sets focus to the Console pane.
$psISE.CurrentPowerShellTab.ConsolePane.Focus()
```

### <a name="getlinelengthint-linenumber-"></a><span data-ttu-id="21185-121">GetLineLength\(int lineNumber \)</span><span class="sxs-lookup"><span data-stu-id="21185-121">GetLineLength\(int lineNumber \)</span></span>

<span data-ttu-id="21185-122">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="21185-122">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="21185-123">Obtém o comprimento da linha como um inteiro para a linha especificada pelo número de linha.</span><span class="sxs-lookup"><span data-stu-id="21185-123">Gets the line length as an integer for the line that is specified by the line number.</span></span>

<span data-ttu-id="21185-124">**lineNumber** O número da linha cujo comprimento será obtido.</span><span class="sxs-lookup"><span data-stu-id="21185-124">**lineNumber** The number of the line of which to get the length.</span></span>

<span data-ttu-id="21185-125">**Returns** O comprimento da linha no número de linha especificado.</span><span class="sxs-lookup"><span data-stu-id="21185-125">**Returns** The line length for the line at the specified line number.</span></span>

```powershell
# Gets the length of the first line in the text of the Command pane.
$psISE.CurrentPowerShellTab.ConsolePane.GetLineLength(1)
```

### <a name="gotomatch"></a><span data-ttu-id="21185-126">GoToMatch\(\)</span><span class="sxs-lookup"><span data-stu-id="21185-126">GoToMatch\(\)</span></span>

<span data-ttu-id="21185-127">Com suporte no Windows PowerShell ISE 3.0 e posterior, não está presente em versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="21185-127">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="21185-128">Moverá o cursor do sistema para o caractere correspondente se a propriedade **CanGoToMatch** do objeto editor for `$true`, o que ocorrerá quando o cursor vier imediatamente antes de um parêntese de abertura, colchete ou chave – `(`,`[`,`{` – ou imediatamente após um parêntese de fechamento, colchete ou chave – `)`,`]`,`}`.</span><span class="sxs-lookup"><span data-stu-id="21185-128">Moves the caret to the matching character if the **CanGoToMatch** property of the editor object is `$true`, which occurs when the caret is immediately before an opening parenthesis, bracket, or brace - `(`,`[`,`{` - or immediately after a closing parenthesis, bracket, or brace - `)`,`]`,`}`.</span></span> <span data-ttu-id="21185-129">O cursor é colocado antes de um caractere de abertura ou depois de um caractere de fechamento.</span><span class="sxs-lookup"><span data-stu-id="21185-129">The caret is placed before an opening character or after a closing character.</span></span> <span data-ttu-id="21185-130">Se a propriedade **CanGoToMatch** for `$false`, esse método nada fará.</span><span class="sxs-lookup"><span data-stu-id="21185-130">If the **CanGoToMatch** property is `$false`, then this method does nothing.</span></span>

```powershell
# Goes to the matching character if CanGoToMatch() is $true
$psISE.CurrentPowerShellTab.ConsolePane.GoToMatch()
```

### <a name="inserttext-text-"></a><span data-ttu-id="21185-131">InsertText\( text \)</span><span class="sxs-lookup"><span data-stu-id="21185-131">InsertText\( text \)</span></span>

<span data-ttu-id="21185-132">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="21185-132">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="21185-133">Substitui a seleção por texto ou inserções de texto na posição do cursor atual.</span><span class="sxs-lookup"><span data-stu-id="21185-133">Replaces the selection with text or inserts text at the current caret position.</span></span>

<span data-ttu-id="21185-134">**text** – cadeia de caracteres, o texto a ser inserido.</span><span class="sxs-lookup"><span data-stu-id="21185-134">**text** - String The text to insert.</span></span>

<span data-ttu-id="21185-135">Veja o [Exemplo de script](#scripting-example), posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="21185-135">See the [Scripting Example](#scripting-example) later in this topic.</span></span>

### <a name="select-startline-startcolumn-endline-endcolumn-"></a><span data-ttu-id="21185-136">Select\( startLine, startColumn, endLine, endColumn \)</span><span class="sxs-lookup"><span data-stu-id="21185-136">Select\( startLine, startColumn, endLine, endColumn \)</span></span>

<span data-ttu-id="21185-137">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="21185-137">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="21185-138">Seleciona o texto dos parâmetros **startLine** , **startColumn** , **endLine** e **endColumn** .</span><span class="sxs-lookup"><span data-stu-id="21185-138">Selects the text from the **startLine** , **startColumn** , **endLine** , and **endColumn** parameters.</span></span>

<span data-ttu-id="21185-139">**startLine** – inteiro, a linha na qual a seleção começa.</span><span class="sxs-lookup"><span data-stu-id="21185-139">**startLine** - Integer The line where the selection starts.</span></span>

<span data-ttu-id="21185-140">**startColumn** – inteiro, a coluna na linha inicial na qual a seleção começa.</span><span class="sxs-lookup"><span data-stu-id="21185-140">**startColumn** - Integer The column within the start line where the selection starts.</span></span>

<span data-ttu-id="21185-141">**endLine** – inteiro, a linha na qual a seleção é encerrada.</span><span class="sxs-lookup"><span data-stu-id="21185-141">**endLine** - Integer The line where the selection ends.</span></span>

<span data-ttu-id="21185-142">**endColumn** – inteiro, a coluna na linha final na qual a seleção é encerrada.</span><span class="sxs-lookup"><span data-stu-id="21185-142">**endColumn** - Integer The column within the end line where the selection ends.</span></span>

<span data-ttu-id="21185-143">Veja o [Exemplo de script](#scripting-example), posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="21185-143">See the  [Scripting Example](#scripting-example) later in this topic.</span></span>

### <a name="selectcaretline"></a><span data-ttu-id="21185-144">SelectCaretLine\(\)</span><span class="sxs-lookup"><span data-stu-id="21185-144">SelectCaretLine\(\)</span></span>

<span data-ttu-id="21185-145">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="21185-145">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="21185-146">Seleciona toda a linha de texto que contém atualmente o circunflexo.</span><span class="sxs-lookup"><span data-stu-id="21185-146">Selects the entire line of text that currently contains the caret.</span></span>

```powershell
# First, set the caret position on line 5.
$psISE.CurrentFile.Editor.SetCaretPosition(5,1)
# Now select that entire line of text
$psISE.CurrentFile.Editor.SelectCaretLine()
```

### <a name="setcaretposition-linenumber-columnnumber-"></a><span data-ttu-id="21185-147">SetCaretPosition\( lineNumber, columnNumber \)</span><span class="sxs-lookup"><span data-stu-id="21185-147">SetCaretPosition\( lineNumber, columnNumber \)</span></span>

<span data-ttu-id="21185-148">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="21185-148">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="21185-149">Define a posição do cursor no número de linha e no número da coluna.</span><span class="sxs-lookup"><span data-stu-id="21185-149">Sets the caret position at the line number and the column number.</span></span> <span data-ttu-id="21185-150">Gerará uma exceção se o número de linha do cursor ou o número da coluna do cursor estiverem fora de seus respectivos intervalos válidos.</span><span class="sxs-lookup"><span data-stu-id="21185-150">It throws an exception if either the caret line number or the caret column number are out of their respective valid ranges.</span></span>

<span data-ttu-id="21185-151">**lineNumber** – inteiro, o número de linha do cursor do sistema.</span><span class="sxs-lookup"><span data-stu-id="21185-151">**lineNumber** - Integer The caret line number.</span></span>

<span data-ttu-id="21185-152">**columnNumber** – inteiro, o número da coluna do cursor do sistema.</span><span class="sxs-lookup"><span data-stu-id="21185-152">**columnNumber** - Integer The caret column number.</span></span>

```powershell
# Set the CaretPosition.
$psISE.CurrentFile.Editor.SetCaretPosition(5,1)
```

### <a name="toggleoutliningexpansion"></a><span data-ttu-id="21185-153">ToggleOutliningExpansion\(\)</span><span class="sxs-lookup"><span data-stu-id="21185-153">ToggleOutliningExpansion\(\)</span></span>

<span data-ttu-id="21185-154">Com suporte no Windows PowerShell ISE 3.0 e posterior, não está presente em versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="21185-154">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="21185-155">Faz com que toda a estrutura de tópicos se expanda ou se recolha.</span><span class="sxs-lookup"><span data-stu-id="21185-155">Causes all the outline sections to expand or collapse.</span></span>

```powershell
# Toggle the outlining expansion
$psISE.CurrentFile.Editor.ToggleOutliningExpansion()
```

## <a name="properties"></a><span data-ttu-id="21185-156">Propriedades</span><span class="sxs-lookup"><span data-stu-id="21185-156">Properties</span></span>

### <a name="cangotomatch"></a><span data-ttu-id="21185-157">CanGoToMatch</span><span class="sxs-lookup"><span data-stu-id="21185-157">CanGoToMatch</span></span>

<span data-ttu-id="21185-158">Com suporte no Windows PowerShell ISE 3.0 e posterior, não está presente em versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="21185-158">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="21185-159">A propriedade booliana somente leitura para indicar se o cursor está ao lado de um parêntese, colchete ou chave – `()`, `[]`, `{}`.</span><span class="sxs-lookup"><span data-stu-id="21185-159">The read-only Boolean property to indicate whether the caret is next to a parenthesis, bracket, or brace - `()`, `[]`, `{}`.</span></span> <span data-ttu-id="21185-160">Se o cursor estiver imediatamente antes do caractere de abertura ou imediatamente após o caractere de fechamento de um par, o valor da propriedade será `$true`.</span><span class="sxs-lookup"><span data-stu-id="21185-160">If the caret is immediately before the opening character or immediately after the closing character of a pair, then this property value is `$true`.</span></span> <span data-ttu-id="21185-161">Caso contrário, será `$false`.</span><span class="sxs-lookup"><span data-stu-id="21185-161">Otherwise, it is `$false`.</span></span>

```powershell
# Test to see if the caret is next to a parenthesis, bracket, or brace
$psISE.CurrentFile.Editor.CanGoToMatch
```

### <a name="caretcolumn"></a><span data-ttu-id="21185-162">CaretColumn</span><span class="sxs-lookup"><span data-stu-id="21185-162">CaretColumn</span></span>

<span data-ttu-id="21185-163">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="21185-163">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="21185-164">A propriedade somente leitura que obtém o número da coluna que corresponde à posição do cursor.</span><span class="sxs-lookup"><span data-stu-id="21185-164">The read-only property that gets the column number that corresponds to the position of the caret.</span></span>

```powershell
# Get the CaretColumn.
$psISE.CurrentFile.Editor.CaretColumn
```

### <a name="caretline"></a><span data-ttu-id="21185-165">CaretLine</span><span class="sxs-lookup"><span data-stu-id="21185-165">CaretLine</span></span>

<span data-ttu-id="21185-166">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="21185-166">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="21185-167">A propriedade somente leitura que obtém o número da linha que contém o cursor.</span><span class="sxs-lookup"><span data-stu-id="21185-167">The read-only property that gets the number of the line that contains the caret.</span></span>

```powershell
# Get the CaretLine.
$psISE.CurrentFile.Editor.CaretLine
```

### <a name="caretlinetext"></a><span data-ttu-id="21185-168">CaretLineText</span><span class="sxs-lookup"><span data-stu-id="21185-168">CaretLineText</span></span>

<span data-ttu-id="21185-169">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="21185-169">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="21185-170">A propriedade somente leitura que obtém a linha completa de texto que contém o cursor.</span><span class="sxs-lookup"><span data-stu-id="21185-170">The read-only property that gets the complete line of text that contains the caret.</span></span>

```powershell
# Get all of the text on the line that contains the caret.
$psISE.CurrentFile.Editor.CaretLineText
```

### <a name="linecount"></a><span data-ttu-id="21185-171">LineCount</span><span class="sxs-lookup"><span data-stu-id="21185-171">LineCount</span></span>

<span data-ttu-id="21185-172">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="21185-172">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="21185-173">A propriedade somente leitura que obtém a contagem de linha do editor.</span><span class="sxs-lookup"><span data-stu-id="21185-173">The read-only property that gets the line count from the editor.</span></span>

```powershell
# Get the LineCount.
$psISE.CurrentFile.Editor.LineCount
```

### <a name="selectedtext"></a><span data-ttu-id="21185-174">SelectedText</span><span class="sxs-lookup"><span data-stu-id="21185-174">SelectedText</span></span>

<span data-ttu-id="21185-175">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="21185-175">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="21185-176">A propriedade somente leitura que obtém o texto selecionado do editor.</span><span class="sxs-lookup"><span data-stu-id="21185-176">The read-only property that gets the selected text from the editor.</span></span>

<span data-ttu-id="21185-177">Veja o [Exemplo de script](#scripting-example), posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="21185-177">See the  [Scripting Example](#scripting-example) later in this topic.</span></span>

### <a name="text"></a><span data-ttu-id="21185-178">Texto</span><span class="sxs-lookup"><span data-stu-id="21185-178">Text</span></span>

<span data-ttu-id="21185-179">Suportado no Windows PowerShell ISE 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="21185-179">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="21185-180">A propriedade de leitura/gravação que obtém ou define o texto no editor.</span><span class="sxs-lookup"><span data-stu-id="21185-180">The read/write property that gets or sets the text in the editor.</span></span>

<span data-ttu-id="21185-181">Veja o [Exemplo de script](#scripting-example), posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="21185-181">See the [Scripting Example](#scripting-example) later in this topic.</span></span>

## <a name="scripting-example"></a><span data-ttu-id="21185-182">Exemplo de Script</span><span class="sxs-lookup"><span data-stu-id="21185-182">Scripting Example</span></span>

```powershell
# This illustrates how you can use the length of a line to
# select the entire line and shows how you can make it lowercase.
# You must run this in the Console pane. It will not run in the Script pane.
# Begin by getting a variable that points to the editor.
$myEditor = $psISE.CurrentFile.Editor
# Clear the text in the current file editor.
$myEditor.Clear()

# Make sure the file has five lines of text.
$myEditor.InsertText("LINE1 `n")
$myEditor.InsertText("LINE2 `n")
$myEditor.InsertText("LINE3 `n")
$myEditor.InsertText("LINE4 `n")
$myEditor.InsertText("LINE5 `n")

# Use the GetLineLength method to get the length of the third line.
$endColumn = $myEditor.GetLineLength(3)
# Select the text in the first three lines.
$myEditor.Select(1, 1, 3, $endColumn + 1)
$selection = $myEditor.SelectedText
# Clear all the text in the editor.
$myEditor.Clear()
# Add the selected text back, but in lower case.
$myEditor.InsertText($selection.ToLower())
```

## <a name="see-also"></a><span data-ttu-id="21185-183">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="21185-183">See Also</span></span>

- [<span data-ttu-id="21185-184">O objeto ISEFile</span><span class="sxs-lookup"><span data-stu-id="21185-184">The ISEFile Object</span></span>](The-ISEFile-Object.md)
- [<span data-ttu-id="21185-185">O objeto PowerShellTab</span><span class="sxs-lookup"><span data-stu-id="21185-185">The PowerShellTab Object</span></span>](The-PowerShellTab-Object.md)
- [<span data-ttu-id="21185-186">Objetivo do modelo de objeto de script do ISE do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="21185-186">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="21185-187">A hierarquia de modelo de objeto do ISE</span><span class="sxs-lookup"><span data-stu-id="21185-187">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
