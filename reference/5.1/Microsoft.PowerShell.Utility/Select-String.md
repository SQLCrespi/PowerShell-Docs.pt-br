---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/select-string?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Select-String
ms.openlocfilehash: 95601a4f5f42700c4de7d6ad721ee898b22bab84
ms.sourcegitcommit: 9a8bb1b459b5939c95e1f6d9499fcb13d01a58c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/25/2020
ms.locfileid: "93195244"
---
# <span data-ttu-id="b1f50-103">Select-String</span><span class="sxs-lookup"><span data-stu-id="b1f50-103">Select-String</span></span>

## <span data-ttu-id="b1f50-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="b1f50-104">SYNOPSIS</span></span>
<span data-ttu-id="b1f50-105">Localiza texto em arquivos e cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="b1f50-105">Finds text in strings and files.</span></span>

## <span data-ttu-id="b1f50-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b1f50-106">SYNTAX</span></span>

### <span data-ttu-id="b1f50-107">Arquivo (padrão)</span><span class="sxs-lookup"><span data-stu-id="b1f50-107">File (Default)</span></span>

```
Select-String [-Pattern] <String[]> [-Path] <String[]> [-SimpleMatch] [-CaseSensitive] [-Quiet]
 [-List] [-Include <String[]>] [-Exclude <String[]>] [-NotMatch] [-AllMatches] [-Encoding <String>]
 [-Context <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="b1f50-108">Objeto</span><span class="sxs-lookup"><span data-stu-id="b1f50-108">Object</span></span>

```
Select-String -InputObject <PSObject> [-Pattern] <String[]> [-SimpleMatch] [-CaseSensitive] [-Quiet]
 [-List] [-Include <String[]>] [-Exclude <String[]>] [-NotMatch] [-AllMatches] [-Encoding <String>]
 [-Context <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="b1f50-109">Valor literal</span><span class="sxs-lookup"><span data-stu-id="b1f50-109">LiteralFile</span></span>

```
Select-String [-Pattern] <String[]> -LiteralPath <String[]> [-SimpleMatch] [-CaseSensitive] [-Quiet]
 [-List] [-Include <String[]>] [-Exclude <String[]>] [-NotMatch] [-AllMatches] [-Encoding <String>]
 [-Context <Int32[]>] [<CommonParameters>]
```

## <span data-ttu-id="b1f50-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b1f50-110">DESCRIPTION</span></span>

<span data-ttu-id="b1f50-111">O `Select-String` cmdlet procura padrões de texto e texto em cadeias de caracteres de entrada e arquivos.</span><span class="sxs-lookup"><span data-stu-id="b1f50-111">The `Select-String` cmdlet searches for text and text patterns in input strings and files.</span></span> <span data-ttu-id="b1f50-112">Você pode usar `Select-String` semelhante ao **grep** no UNIX ou **findstr.exe** no Windows.</span><span class="sxs-lookup"><span data-stu-id="b1f50-112">You can use `Select-String` similar to **grep** in UNIX or **findstr.exe** in Windows.</span></span>

<span data-ttu-id="b1f50-113">`Select-String` baseia-se em linhas de texto.</span><span class="sxs-lookup"><span data-stu-id="b1f50-113">`Select-String` is based on lines of text.</span></span> <span data-ttu-id="b1f50-114">Por padrão, `Select-String` o localiza a primeira correspondência em cada linha e, para cada correspondência, exibe o nome do arquivo, o número da linha e todo o texto na linha que contém a correspondência.</span><span class="sxs-lookup"><span data-stu-id="b1f50-114">By default, `Select-String` finds the first match in each line and, for each match, it displays the file name, line number, and all text in the line containing the match.</span></span> <span data-ttu-id="b1f50-115">Você pode direcionar `Select-String` para localizar várias correspondências por linha, exibir texto antes e depois da correspondência, ou exibir um valor booliano (true ou false) que indica se uma correspondência é encontrada.</span><span class="sxs-lookup"><span data-stu-id="b1f50-115">You can direct `Select-String` to find multiple matches per line, display text before and after the match, or display a Boolean value (True or False) that indicates whether a match is found.</span></span>

<span data-ttu-id="b1f50-116">`Select-String` usa correspondência de expressão regular, mas também pode executar uma correspondência que pesquisa a entrada para o texto que você especificar.</span><span class="sxs-lookup"><span data-stu-id="b1f50-116">`Select-String` uses regular expression matching, but it can also perform a match that searches the input for the text that you specify.</span></span>

<span data-ttu-id="b1f50-117">`Select-String` pode exibir todas as correspondências de texto ou parar após a primeira correspondência em cada arquivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="b1f50-117">`Select-String` can display all the text matches or stop after the first match in each input file.</span></span>
<span data-ttu-id="b1f50-118">`Select-String` pode ser usado para exibir todo o texto que não corresponde ao padrão especificado.</span><span class="sxs-lookup"><span data-stu-id="b1f50-118">`Select-String` can be used to display all text that doesn't match the specified pattern.</span></span>

<span data-ttu-id="b1f50-119">Você também pode especificar que `Select-String` deve esperar uma codificação de caractere específica, como quando você está pesquisando arquivos de texto Unicode.</span><span class="sxs-lookup"><span data-stu-id="b1f50-119">You can also specify that `Select-String` should expect a particular character encoding, such as when you're searching files of Unicode text.</span></span> <span data-ttu-id="b1f50-120">`Select-String` usa a BOM (marca de ordem de byte) para detectar o formato de codificação do arquivo.</span><span class="sxs-lookup"><span data-stu-id="b1f50-120">`Select-String` uses the byte-order-mark (BOM) to detect the encoding format of the file.</span></span> <span data-ttu-id="b1f50-121">Se o arquivo não tiver uma BOM, ele assumirá que a codificação é UTF8.</span><span class="sxs-lookup"><span data-stu-id="b1f50-121">If the file has no BOM, it assumes the encoding is UTF8.</span></span>

## <span data-ttu-id="b1f50-122">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="b1f50-122">EXAMPLES</span></span>

### <span data-ttu-id="b1f50-123">Exemplo 1: Localizar uma correspondência que diferencia maiúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="b1f50-123">Example 1: Find a case-sensitive match</span></span>

<span data-ttu-id="b1f50-124">Este exemplo faz uma correspondência que diferencia maiúsculas de minúsculas do texto que foi enviado pelo pipeline para o `Select-String` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b1f50-124">This example does a case-sensitive match of the text that was sent down the pipeline to the `Select-String` cmdlet.</span></span>

```powershell
'Hello', 'HELLO' | Select-String -Pattern 'HELLO' -CaseSensitive -SimpleMatch
```

<span data-ttu-id="b1f50-125">As cadeias de texto **Olá** e **Olá** são enviadas ao pipeline para o `Select-String` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b1f50-125">The text strings **Hello** and **HELLO** are sent down the pipeline to the `Select-String` cmdlet.</span></span>
<span data-ttu-id="b1f50-126">`Select-String` usa o parâmetro **Pattern** para especificar **Hello** .</span><span class="sxs-lookup"><span data-stu-id="b1f50-126">`Select-String` uses the **Pattern** parameter to specify **HELLO** .</span></span> <span data-ttu-id="b1f50-127">O parâmetro **CaseSensitive** especifica que o caso deve corresponder apenas ao padrão em maiúsculas.</span><span class="sxs-lookup"><span data-stu-id="b1f50-127">The **CaseSensitive** parameter specifies that the case must match only the upper-case pattern.</span></span> <span data-ttu-id="b1f50-128">**SimpleMatch** é um parâmetro opcional e especifica que a cadeia de caracteres no padrão não é interpretada como uma expressão regular.</span><span class="sxs-lookup"><span data-stu-id="b1f50-128">**SimpleMatch** is an optional parameter and specifies that the string in the pattern isn't interpreted as a regular expression.</span></span>
<span data-ttu-id="b1f50-129">`Select-String` exibe **Olá** no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1f50-129">`Select-String` displays **HELLO** in the PowerShell console.</span></span>

### <span data-ttu-id="b1f50-130">Exemplo 2: localizar correspondências em arquivos de texto</span><span class="sxs-lookup"><span data-stu-id="b1f50-130">Example 2: Find matches in text files</span></span>

<span data-ttu-id="b1f50-131">Esse comando pesquisa todos os arquivos com a `.txt` extensão de nome de arquivo no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="b1f50-131">This command searches all files with the `.txt` file name extension in the current directory.</span></span> <span data-ttu-id="b1f50-132">A saída exibe as linhas nesses arquivos que incluem a cadeia de caracteres especificada.</span><span class="sxs-lookup"><span data-stu-id="b1f50-132">The output displays the lines in those files that include the specified string.</span></span>

```powershell
Get-Alias | Out-File -FilePath .\Alias.txt
Get-Command | Out-File -FilePath .\Command.txt
Select-String -Path .\*.txt -Pattern 'Get-'
```

```Output
Alias.txt:8:Alias            cat -> Get-Content
Alias.txt:28:Alias           dir -> Get-ChildItem
Alias.txt:43:Alias           gal -> Get-Alias
Command.txt:966:Cmdlet       Get-Acl
Command.txt:967:Cmdlet       Get-Alias
```

<span data-ttu-id="b1f50-133">Neste exemplo, `Get-Alias` e `Get-Command` são usados com o `Out-File` cmdlet para criar dois arquivos de texto no diretório atual, **Alias.txt** e **Command.txt** .</span><span class="sxs-lookup"><span data-stu-id="b1f50-133">In this example, `Get-Alias` and `Get-Command` are used with the `Out-File` cmdlet to create two text files in the current directory, **Alias.txt** and **Command.txt** .</span></span>

<span data-ttu-id="b1f50-134">`Select-String` usa o parâmetro **path** com o curinga asterisco ( `*` ) para pesquisar todos os arquivos no diretório atual com a extensão de nome de arquivo `.txt` .</span><span class="sxs-lookup"><span data-stu-id="b1f50-134">`Select-String` uses the **Path** parameter with the asterisk (`*`) wildcard to search all files in the current directory with the file name extension `.txt`.</span></span> <span data-ttu-id="b1f50-135">O parâmetro **Pattern** especifica o texto para corresponder a **Get-** .</span><span class="sxs-lookup"><span data-stu-id="b1f50-135">The **Pattern** parameter specifies the text to match **Get-** .</span></span> <span data-ttu-id="b1f50-136">`Select-String` exibe a saída no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1f50-136">`Select-String` displays the output in the PowerShell console.</span></span> <span data-ttu-id="b1f50-137">O nome do arquivo e o número da linha precedem cada linha de conteúdo que contém uma correspondência para o parâmetro **Pattern** .</span><span class="sxs-lookup"><span data-stu-id="b1f50-137">The file name and line number precede each line of content that contains a match for the **Pattern** parameter.</span></span>

### <span data-ttu-id="b1f50-138">Exemplo 3: Localizar uma correspondência de padrão</span><span class="sxs-lookup"><span data-stu-id="b1f50-138">Example 3: Find a pattern match</span></span>

<span data-ttu-id="b1f50-139">Neste exemplo, vários arquivos são pesquisados para localizar correspondências para o padrão especificado.</span><span class="sxs-lookup"><span data-stu-id="b1f50-139">In this example, multiple files are searched to find matches for the specified pattern.</span></span> <span data-ttu-id="b1f50-140">O padrão usa um quantificador de expressão regular.</span><span class="sxs-lookup"><span data-stu-id="b1f50-140">The pattern uses a regular expression quantifier.</span></span> <span data-ttu-id="b1f50-141">Para obter mais informações, consulte [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/About_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="b1f50-141">For more information, see [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/About_Regular_Expressions.md).</span></span>

```powershell
Select-String -Path "$PSHOME\en-US\*.txt" -Pattern '\?'
```

```Output
C:\Program Files\PowerShell\6\en-US\default.help.txt:27:    beginning at https://go.microsoft.com/fwlink/?LinkID=108518.
C:\Program Files\PowerShell\6\en-US\default.help.txt:50:    or go to: https://go.microsoft.com/fwlink/?LinkID=210614
```

<span data-ttu-id="b1f50-142">O `Select-String` cmdlet usa dois parâmetros, **Path** e **Pattern** .</span><span class="sxs-lookup"><span data-stu-id="b1f50-142">The `Select-String` cmdlet uses two parameters, **Path** and **Pattern** .</span></span> <span data-ttu-id="b1f50-143">O parâmetro **path** usa a variável `$PSHOME` que especifica o diretório do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1f50-143">The **Path** parameter uses the variable `$PSHOME` that specifies the PowerShell directory.</span></span> <span data-ttu-id="b1f50-144">O restante do caminho inclui o subdiretório **en-US** e especifica cada `*.txt` arquivo no diretório.</span><span class="sxs-lookup"><span data-stu-id="b1f50-144">The remainder of the path includes the subdirectory **en-US** and specifies each `*.txt` file in the directory.</span></span> <span data-ttu-id="b1f50-145">O parâmetro **Pattern** especifica a correspondência de um ponto de interrogação ( `?` ) em cada arquivo.</span><span class="sxs-lookup"><span data-stu-id="b1f50-145">The **Pattern** parameter specifies to match a question mark (`?`) in each file.</span></span> <span data-ttu-id="b1f50-146">Uma barra invertida ( `\` ) é usada como um caractere de escape e é necessária porque o ponto de interrogação ( `?` ) é um quantificador de expressão regular.</span><span class="sxs-lookup"><span data-stu-id="b1f50-146">A backslash (`\`) is used as an escape character and is necessary because the question mark (`?`) is a regular expression quantifier.</span></span> <span data-ttu-id="b1f50-147">`Select-String` exibe a saída no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1f50-147">`Select-String` displays the output in the PowerShell console.</span></span> <span data-ttu-id="b1f50-148">O nome do arquivo e o número da linha precedem cada linha de conteúdo que contém uma correspondência para o parâmetro **Pattern** .</span><span class="sxs-lookup"><span data-stu-id="b1f50-148">The file name and line number precede each line of content that contains a match for the **Pattern** parameter.</span></span>

### <span data-ttu-id="b1f50-149">Exemplo 4: usar Select-String em uma função</span><span class="sxs-lookup"><span data-stu-id="b1f50-149">Example 4: Use Select-String in a function</span></span>

<span data-ttu-id="b1f50-150">Este exemplo cria uma função para procurar por um padrão nos arquivos de ajuda do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1f50-150">This example creates a function to search for a pattern in the PowerShell help files.</span></span> <span data-ttu-id="b1f50-151">Para este exemplo, a função existe somente na sessão do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1f50-151">For this example, the function only exists in the PowerShell session.</span></span> <span data-ttu-id="b1f50-152">Quando a sessão do PowerShell é fechada, a função é excluída.</span><span class="sxs-lookup"><span data-stu-id="b1f50-152">When the PowerShell session is closed, the function is deleted.</span></span> <span data-ttu-id="b1f50-153">Para obter mais informações, consulte [about_Functions](../Microsoft.PowerShell.Core/About/about_Functions.md).</span><span class="sxs-lookup"><span data-stu-id="b1f50-153">For more information, see [about_Functions](../Microsoft.PowerShell.Core/About/about_Functions.md).</span></span>

```
PS> Function Search-Help
>> {
>> $PSHelp = "$PSHOME\en-US\*.txt"
>> Select-String -Path $PSHelp -Pattern 'About_'
>> }
PS>

PS> Search-Help

C:\Windows\System32\WindowsPowerShell\v1.0\en-US\about_ActivityCommonParameters.help.txt:2:   about_ActivityCommonParameters
C:\Windows\System32\WindowsPowerShell\v1.0\en-US\about_ActivityCommonParameters.help.txt:31:  see about_WorkflowCommonParameters.
C:\Windows\System32\WindowsPowerShell\v1.0\en-US\about_ActivityCommonParameters.help.txt:33:  about_CommonParameters.
```

<span data-ttu-id="b1f50-154">A função é criada na linha de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1f50-154">The function is created on the PowerShell command line.</span></span> <span data-ttu-id="b1f50-155">O `Function` comando usa o nome **Search-Help** .</span><span class="sxs-lookup"><span data-stu-id="b1f50-155">The `Function` command uses the name **Search-Help** .</span></span> <span data-ttu-id="b1f50-156">Pressione **Enter** para começar a adicionar instruções à função.</span><span class="sxs-lookup"><span data-stu-id="b1f50-156">Press **Enter** to begin adding statements to the function.</span></span> <span data-ttu-id="b1f50-157">No `>>` prompt, adicione cada instrução e pressione **Enter** , conforme mostrado no exemplo.</span><span class="sxs-lookup"><span data-stu-id="b1f50-157">From the `>>` prompt, add each statement and press **Enter** as shown in the example.</span></span> <span data-ttu-id="b1f50-158">Depois que o colchete de fechamento for adicionado, você será retornado para um prompt do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1f50-158">After the closing bracket is added, you're returned to a PowerShell prompt.</span></span>

<span data-ttu-id="b1f50-159">A função contém dois comandos.</span><span class="sxs-lookup"><span data-stu-id="b1f50-159">The function contains two commands.</span></span> <span data-ttu-id="b1f50-160">A `$PSHelp` variável armazena o caminho para os arquivos de ajuda do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1f50-160">The `$PSHelp` variable stores the path to the PowerShell help files.</span></span> <span data-ttu-id="b1f50-161">`$PSHOME` é o diretório de instalação do PowerShell com o subdiretório **en-US** que especifica cada `*.txt` arquivo no diretório.</span><span class="sxs-lookup"><span data-stu-id="b1f50-161">`$PSHOME` is the PowerShell installation directory with the subdirectory **en-US** that specifies each `*.txt` file in the directory.</span></span>

<span data-ttu-id="b1f50-162">O `Select-String` comando na função usa os parâmetros **Path** e **Pattern** .</span><span class="sxs-lookup"><span data-stu-id="b1f50-162">The `Select-String` command in the function uses the **Path** and **Pattern** parameters.</span></span> <span data-ttu-id="b1f50-163">O parâmetro **path** usa a `$PSHelp` variável para obter o caminho.</span><span class="sxs-lookup"><span data-stu-id="b1f50-163">The **Path** parameter uses the `$PSHelp` variable to get the path.</span></span> <span data-ttu-id="b1f50-164">O parâmetro **Pattern** usa a cadeia de caracteres **About_** como os critérios de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b1f50-164">The **Pattern** parameter uses the string **About_** as the search criteria.</span></span>

<span data-ttu-id="b1f50-165">Para executar a função, digite `Search-Help` .</span><span class="sxs-lookup"><span data-stu-id="b1f50-165">To run the function, type `Search-Help`.</span></span> <span data-ttu-id="b1f50-166">O comando da função `Select-String` exibe a saída no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1f50-166">The function's `Select-String` command displays the output in the PowerShell console.</span></span>

### <span data-ttu-id="b1f50-167">Exemplo 5: Pesquisar uma cadeia de caracteres em um log de eventos do Windows</span><span class="sxs-lookup"><span data-stu-id="b1f50-167">Example 5: Search for a string in a Windows event log</span></span>

<span data-ttu-id="b1f50-168">Este exemplo pesquisa uma cadeia de caracteres em um log de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="b1f50-168">This example searches for a string in a Windows event log.</span></span> <span data-ttu-id="b1f50-169">A variável `$_` representa o objeto atual no pipeline.</span><span class="sxs-lookup"><span data-stu-id="b1f50-169">The variable `$_` represents the current object in the pipeline.</span></span> <span data-ttu-id="b1f50-170">Para obter mais informações, consulte [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="b1f50-170">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

```powershell
$Events = Get-WinEvent -LogName Application -MaxEvents 50
$Events | Select-String -InputObject {$_.message} -Pattern 'Failed'
```

<span data-ttu-id="b1f50-171">O `Get-WinEvent` cmdlet usa o parâmetro **LogName** para especificar o log do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b1f50-171">The `Get-WinEvent` cmdlet uses the **LogName** parameter to specify the Application log.</span></span> <span data-ttu-id="b1f50-172">O parâmetro **MaxEvents** obtém os 50 eventos mais recentes do log.</span><span class="sxs-lookup"><span data-stu-id="b1f50-172">The **MaxEvents** parameter gets the 50 most recent events from the log.</span></span> <span data-ttu-id="b1f50-173">O conteúdo do log é armazenado na variável chamada `$Events` .</span><span class="sxs-lookup"><span data-stu-id="b1f50-173">The log content is stored in the variable named `$Events`.</span></span>

<span data-ttu-id="b1f50-174">A `$Events` variável é enviada ao pipeline para o `Select-String` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b1f50-174">The `$Events` variable is sent down the pipeline to the `Select-String` cmdlet.</span></span> <span data-ttu-id="b1f50-175">`Select-String` usa o parâmetro **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="b1f50-175">`Select-String` uses the **InputObject** parameter.</span></span> <span data-ttu-id="b1f50-176">A `$_` variável representa o objeto atual e `message` é uma propriedade do evento.</span><span class="sxs-lookup"><span data-stu-id="b1f50-176">The `$_` variable represents the current object and `message` is a property of the event.</span></span> <span data-ttu-id="b1f50-177">O parâmetro **Pattern** especifica a cadeia de caracteres que **falhou** e procura por correspondências `$_.message` .</span><span class="sxs-lookup"><span data-stu-id="b1f50-177">The **Pattern** parameter species the string **Failed** and searches for matches in `$_.message`.</span></span> <span data-ttu-id="b1f50-178">`Select-String` exibe a saída no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1f50-178">`Select-String` displays the output in the PowerShell console.</span></span>

### <span data-ttu-id="b1f50-179">Exemplo 6: Localizar uma cadeia de caracteres em subdiretórios</span><span class="sxs-lookup"><span data-stu-id="b1f50-179">Example 6: Find a string in subdirectories</span></span>

<span data-ttu-id="b1f50-180">Este exemplo pesquisa um diretório e todos os seus subdiretórios para uma cadeia de texto específica.</span><span class="sxs-lookup"><span data-stu-id="b1f50-180">This example searches a directory and all of its subdirectories for a specific text string.</span></span>

```powershell
Get-ChildItem -Path C:\Windows\System32\*.txt -Recurse | Select-String -Pattern 'Microsoft' -CaseSensitive
```

<span data-ttu-id="b1f50-181">`Get-ChildItem` usa o parâmetro **path** para especificar **C:\Windows\System32 \* . txt** .</span><span class="sxs-lookup"><span data-stu-id="b1f50-181">`Get-ChildItem` uses the **Path** parameter to specify **C:\Windows\System32\*.txt** .</span></span> <span data-ttu-id="b1f50-182">O parâmetro **recurse** inclui os subdiretórios.</span><span class="sxs-lookup"><span data-stu-id="b1f50-182">The **Recurse** parameter includes the subdirectories.</span></span> <span data-ttu-id="b1f50-183">Os objetos são enviados ao pipeline para `Select-String` .</span><span class="sxs-lookup"><span data-stu-id="b1f50-183">The objects are sent down the pipeline to `Select-String`.</span></span>

<span data-ttu-id="b1f50-184">`Select-String` usa o parâmetro **Pattern** e especifica a cadeia de caracteres **Microsoft** .</span><span class="sxs-lookup"><span data-stu-id="b1f50-184">`Select-String` uses the **Pattern** parameter and specifies the string **Microsoft** .</span></span> <span data-ttu-id="b1f50-185">O parâmetro **CaseSensitive** é usado para corresponder ao caso exato da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="b1f50-185">The **CaseSensitive** parameter is used to match the exact case of the string.</span></span> <span data-ttu-id="b1f50-186">`Select-String` exibe a saída no console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1f50-186">`Select-String` displays the output in the PowerShell console.</span></span>

> [!NOTE]
> <span data-ttu-id="b1f50-187">Dependendo de suas permissões, você poderá ver as mensagens de **acesso negado** na saída.</span><span class="sxs-lookup"><span data-stu-id="b1f50-187">Dependent upon your permissions, you might see **Access denied** messages in the output.</span></span>

### <span data-ttu-id="b1f50-188">Exemplo 7: localizar cadeias de caracteres que não correspondem a um padrão</span><span class="sxs-lookup"><span data-stu-id="b1f50-188">Example 7: Find strings that do not match a pattern</span></span>

<span data-ttu-id="b1f50-189">Este exemplo mostra como excluir linhas de dados que não correspondem a um padrão.</span><span class="sxs-lookup"><span data-stu-id="b1f50-189">This example shows how to exclude lines of data that don't match a pattern.</span></span>

```powershell
Get-Command | Out-File -FilePath .\Command.txt
Select-String -Path .\Command.txt -Pattern 'Get', 'Set'  -NotMatch
```

<span data-ttu-id="b1f50-190">O `Get-Command` cmdlet envia objetos por meio do pipeline para o `Out-File` para criar o arquivo de **Command.txt** no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="b1f50-190">The `Get-Command` cmdlet sends objects down the pipeline to the `Out-File` to create the **Command.txt** file in the current directory.</span></span> <span data-ttu-id="b1f50-191">`Select-String` usa o parâmetro **path** para especificar o arquivo de **Command.txt** .</span><span class="sxs-lookup"><span data-stu-id="b1f50-191">`Select-String` uses the **Path** parameter to specify the **Command.txt** file.</span></span> <span data-ttu-id="b1f50-192">O parâmetro **Pattern** especifica **Get** e **set** como o padrão de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b1f50-192">The **Pattern** parameter specifies **Get** and **Set** as the search pattern.</span></span> <span data-ttu-id="b1f50-193">O parâmetro não **Match** exclui **Get** e **set** dos resultados.</span><span class="sxs-lookup"><span data-stu-id="b1f50-193">The **NotMatch** parameter excludes **Get** and **Set** from the results.</span></span>
<span data-ttu-id="b1f50-194">`Select-String` exibe a saída no console do PowerShell que não inclui **Get** ou **set** .</span><span class="sxs-lookup"><span data-stu-id="b1f50-194">`Select-String` displays the output in the PowerShell console that doesn't include **Get** or **Set** .</span></span>

### <span data-ttu-id="b1f50-195">Exemplo 8: localizar linhas antes e depois de uma correspondência</span><span class="sxs-lookup"><span data-stu-id="b1f50-195">Example 8: Find lines before and after a match</span></span>

<span data-ttu-id="b1f50-196">Este exemplo mostra como obter as linhas antes e depois do padrão correspondente.</span><span class="sxs-lookup"><span data-stu-id="b1f50-196">This example shows how to get the lines before and after the matched pattern.</span></span>

```powershell
Get-Command | Out-File -FilePath .\Command.txt
Select-String -Path .\Command.txt -Pattern 'Get-Computer' -Context 2, 3
```

```Output
  Command.txt:1186:Cmdlet          Get-CmsMessage            3.0.0.0    Microsoft.PowerShell.Security
  Command.txt:1187:Cmdlet          Get-Command               3.0.0.0    Microsoft.PowerShell.Core
> Command.txt:1188:Cmdlet          Get-ComputerInfo          3.1.0.0    Microsoft.PowerShell.Management
> Command.txt:1189:Cmdlet          Get-ComputerRestorePoint  3.1.0.0    Microsoft.PowerShell.Management
  Command.txt:1190:Cmdlet          Get-Content               3.1.0.0    Microsoft.PowerShell.Management
  Command.txt:1191:Cmdlet          Get-ControlPanelItem      3.1.0.0    Microsoft.PowerShell.Management
  Command.txt:1192:Cmdlet          Get-Counter               3.0.0.0    Microsoft.PowerShell.Diagnostics
```

<span data-ttu-id="b1f50-197">O `Get-Command` cmdlet envia objetos por meio do pipeline para o `Out-File` para criar o arquivo de **Command.txt** no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="b1f50-197">The `Get-Command` cmdlet sends objects down the pipeline to the `Out-File` to create the **Command.txt** file in the current directory.</span></span> <span data-ttu-id="b1f50-198">`Select-String` usa o parâmetro **path** para especificar o arquivo de **Command.txt** .</span><span class="sxs-lookup"><span data-stu-id="b1f50-198">`Select-String` uses the **Path** parameter to specify the **Command.txt** file.</span></span> <span data-ttu-id="b1f50-199">O parâmetro **Pattern** especifica **Get-Computer** como o padrão de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b1f50-199">The **Pattern** parameter specifies **Get-Computer** as the search pattern.</span></span> <span data-ttu-id="b1f50-200">O parâmetro de **contexto** usa dois valores, antes e depois, e marca as correspondências de padrão na saída com um colchete angular ( `>` ).</span><span class="sxs-lookup"><span data-stu-id="b1f50-200">The **Context** parameter uses two values, before and after, and marks pattern matches in the output with an angle bracket (`>`).</span></span> <span data-ttu-id="b1f50-201">O parâmetro **Context** gera as duas linhas antes do primeiro padrão corresponder e três linhas após a última correspondência de padrão.</span><span class="sxs-lookup"><span data-stu-id="b1f50-201">The **Context** parameter outputs the two lines before the first pattern match and three lines after the last pattern match.</span></span>

### <span data-ttu-id="b1f50-202">Exemplo 9: localizar todas as correspondências de padrão</span><span class="sxs-lookup"><span data-stu-id="b1f50-202">Example 9: Find all pattern matches</span></span>

<span data-ttu-id="b1f50-203">Este exemplo mostra como o parâmetro **Mymatchs** encontra cada correspondência de padrão em uma linha de texto.</span><span class="sxs-lookup"><span data-stu-id="b1f50-203">This example shows how the **AllMatches** parameter finds each pattern match in a line of text.</span></span> <span data-ttu-id="b1f50-204">Por padrão, `Select-String` o localiza apenas a primeira ocorrência de um padrão em uma linha de texto.</span><span class="sxs-lookup"><span data-stu-id="b1f50-204">By default, `Select-String` only finds the first occurrence of a pattern in a line of text.</span></span> <span data-ttu-id="b1f50-205">Este exemplo usa propriedades de objeto que são encontradas com o `Get-Member` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b1f50-205">This example uses object properties that are found with the `Get-Member` cmdlet.</span></span>

```
PS> $A = Get-ChildItem -Path "$PSHOME\en-US\*.txt" | Select-String -Pattern 'PowerShell'

PS> $A

C:\Windows\System32\WindowsPowerShell\v1.0\en-US\about_ActivityCommonParameters.help.txt:5:    Describes the parameters that Windows PowerShell
C:\Windows\System32\WindowsPowerShell\v1.0\en-US\about_ActivityCommonParameters.help.txt:9:    Windows PowerShell Workflow adds the activity common

PS> $A.Matches

Groups   : {0}
Success  : True
Name     : 0
Captures : {0}
Index    : 4
Length   : 10
Value    : PowerShell

PS> $A.Matches.Length

2073

PS> $B = Get-ChildItem -Path "$PSHOME\en-US\*.txt" | Select-String -Pattern 'PowerShell' -AllMatches

PS> $B.Matches.Length

2200
```

<span data-ttu-id="b1f50-206">O `Get-ChildItem` cmdlet usa o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="b1f50-206">The `Get-ChildItem` cmdlet uses the **Path** parameter.</span></span> <span data-ttu-id="b1f50-207">O parâmetro **path** usa a variável `$PSHOME` que especifica o diretório do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1f50-207">The **Path** parameter uses the variable `$PSHOME` that specifies the PowerShell directory.</span></span> <span data-ttu-id="b1f50-208">O restante do caminho inclui o subdiretório **en-US** e especifica cada `*.txt` arquivo no diretório.</span><span class="sxs-lookup"><span data-stu-id="b1f50-208">The remainder of the path includes the subdirectory **en-US** and specifies each `*.txt` file in the directory.</span></span> <span data-ttu-id="b1f50-209">Os `Get-ChildItem` objetos são armazenados na `$A` variável.</span><span class="sxs-lookup"><span data-stu-id="b1f50-209">The `Get-ChildItem` objects are stored in the `$A` variable.</span></span> <span data-ttu-id="b1f50-210">A `$A` variável é enviada ao pipeline para o `Select-String` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b1f50-210">The `$A` variable is sent down the pipeline to the `Select-String` cmdlet.</span></span> <span data-ttu-id="b1f50-211">`Select-String` usa o parâmetro **Pattern** para pesquisar cada arquivo para a cadeia de caracteres **PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="b1f50-211">`Select-String` uses the **Pattern** parameter to search each file for the string **PowerShell** .</span></span>

<span data-ttu-id="b1f50-212">Na linha de comando do PowerShell, o `$A` conteúdo da variável é exibido.</span><span class="sxs-lookup"><span data-stu-id="b1f50-212">From the PowerShell command line, the `$A` variable contents are displayed.</span></span> <span data-ttu-id="b1f50-213">Há uma linha que contém duas ocorrências da cadeia de caracteres do **PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="b1f50-213">There's a line that contains two occurrences of the string **PowerShell** .</span></span>

<span data-ttu-id="b1f50-214">A `$A.Matches` propriedade lista a primeira ocorrência do **PowerShell** padrão em cada linha.</span><span class="sxs-lookup"><span data-stu-id="b1f50-214">The `$A.Matches` property lists the first occurrence of the pattern **PowerShell** on each line.</span></span>

<span data-ttu-id="b1f50-215">A `$A.Matches.Length` Propriedade conta a primeira ocorrência do **PowerShell** padrão em cada linha.</span><span class="sxs-lookup"><span data-stu-id="b1f50-215">The `$A.Matches.Length` property counts the first occurrence of the pattern **PowerShell** on each line.</span></span>

<span data-ttu-id="b1f50-216">A `$B` variável usa os mesmos `Get-ChildItem` `Select-String` cmdlets e, mas adiciona o parâmetro de todas as **correspondências** .</span><span class="sxs-lookup"><span data-stu-id="b1f50-216">The `$B` variable uses the same `Get-ChildItem` and `Select-String` cmdlets, but adds the **AllMatches** parameter.</span></span> <span data-ttu-id="b1f50-217">Os **Permatchs** localiza cada ocorrência do **PowerShell** padrão em cada linha.</span><span class="sxs-lookup"><span data-stu-id="b1f50-217">**AllMatches** finds each occurrence of the pattern **PowerShell** on each line.</span></span> <span data-ttu-id="b1f50-218">Os objetos armazenados nas `$A` variáveis e `$B` são idênticos.</span><span class="sxs-lookup"><span data-stu-id="b1f50-218">The objects stored in the `$A` and `$B` variables are identical.</span></span>

<span data-ttu-id="b1f50-219">A `$B.Matches.Length` Propriedade aumenta porque, para cada linha, todas as ocorrências do padrão do **PowerShell** são contadas.</span><span class="sxs-lookup"><span data-stu-id="b1f50-219">The `$B.Matches.Length` property increases because for each line, every occurrence of the pattern **PowerShell** is counted.</span></span>

## <span data-ttu-id="b1f50-220">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b1f50-220">PARAMETERS</span></span>

### <span data-ttu-id="b1f50-221">-Todas as correspondências</span><span class="sxs-lookup"><span data-stu-id="b1f50-221">-AllMatches</span></span>

<span data-ttu-id="b1f50-222">Indica que o cmdlet pesquisa mais de uma correspondência em cada linha de texto.</span><span class="sxs-lookup"><span data-stu-id="b1f50-222">Indicates that the cmdlet searches for more than one match in each line of text.</span></span> <span data-ttu-id="b1f50-223">Sem esse parâmetro, `Select-String` o localiza apenas a primeira correspondência em cada linha de texto.</span><span class="sxs-lookup"><span data-stu-id="b1f50-223">Without this parameter, `Select-String` finds only the first match in each line of text.</span></span>

<span data-ttu-id="b1f50-224">Quando `Select-String` o encontra mais de uma correspondência em uma linha de texto, ele ainda emite apenas um objeto **MatchInfo** para a linha, mas a propriedade **corresponde** do objeto contém todas as correspondências.</span><span class="sxs-lookup"><span data-stu-id="b1f50-224">When `Select-String` finds more than one match in a line of text, it still emits only one **MatchInfo** object for the line, but the **Matches** property of the object contains all the matches.</span></span>

> [!NOTE]
> <span data-ttu-id="b1f50-225">Esse parâmetro é ignorado quando usado em combinação com o parâmetro **SimpleMatch** .</span><span class="sxs-lookup"><span data-stu-id="b1f50-225">This parameter is ignored when used in combination with the **SimpleMatch** parameter.</span></span> <span data-ttu-id="b1f50-226">Se você deseja retornar todas as correspondências e o padrão que você está procurando contém caracteres de expressão regular, você deve escapar esses caracteres em vez de usar **SimpleMatch** .</span><span class="sxs-lookup"><span data-stu-id="b1f50-226">If you wish to return all matches and the pattern that you are searching for contains regular expression characters, you must escape those characters rather than using **SimpleMatch** .</span></span> <span data-ttu-id="b1f50-227">Consulte [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md) para obter mais informações sobre a saída de expressões regulares.</span><span class="sxs-lookup"><span data-stu-id="b1f50-227">See [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md) for more information about escaping regular expressions.</span></span>

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

### <span data-ttu-id="b1f50-228">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="b1f50-228">-CaseSensitive</span></span>

<span data-ttu-id="b1f50-229">Indica que as correspondências de cmdlet diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b1f50-229">Indicates that the cmdlet matches are case-sensitive.</span></span> <span data-ttu-id="b1f50-230">Por padrão, as correspondências não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b1f50-230">By default, matches aren't case-sensitive.</span></span>

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

### <span data-ttu-id="b1f50-231">-Context</span><span class="sxs-lookup"><span data-stu-id="b1f50-231">-Context</span></span>

<span data-ttu-id="b1f50-232">Captura o número especificado de linhas antes e depois da linha que corresponde ao padrão.</span><span class="sxs-lookup"><span data-stu-id="b1f50-232">Captures the specified number of lines before and after the line that matches the pattern.</span></span>

<span data-ttu-id="b1f50-233">Se você inserir um número como o valor desse parâmetro, esse número determina o número de linhas capturadas antes e após a correspondência.</span><span class="sxs-lookup"><span data-stu-id="b1f50-233">If you enter one number as the value of this parameter, that number determines the number of lines captured before and after the match.</span></span> <span data-ttu-id="b1f50-234">Se você inserir dois números como valor, o primeiro número determina o número de linhas antes da correspondência e o segundo determina o número de linhas após a correspondência.</span><span class="sxs-lookup"><span data-stu-id="b1f50-234">If you enter two numbers as the value, the first number determines the number of lines before the match and the second number determines the number of lines after the match.</span></span> <span data-ttu-id="b1f50-235">Por exemplo, `-Context 2,3`.</span><span class="sxs-lookup"><span data-stu-id="b1f50-235">For example, `-Context 2,3`.</span></span>

<span data-ttu-id="b1f50-236">Na exibição padrão, as linhas com uma correspondência são indicadas por um colchete angular direito ( `>` ) (ASCII 62) na primeira coluna da exibição.</span><span class="sxs-lookup"><span data-stu-id="b1f50-236">In the default display, lines with a match are indicated by a right angle bracket (`>`) (ASCII 62) in the first column of the display.</span></span> <span data-ttu-id="b1f50-237">Linhas desmarcadas são o contexto.</span><span class="sxs-lookup"><span data-stu-id="b1f50-237">Unmarked lines are the context.</span></span>

<span data-ttu-id="b1f50-238">O parâmetro de **contexto** não altera o número de objetos gerados pelo `Select-String` .</span><span class="sxs-lookup"><span data-stu-id="b1f50-238">The **Context** parameter doesn't change the number of objects generated by `Select-String`.</span></span>
<span data-ttu-id="b1f50-239">`Select-String` gera um objeto [MatchInfo](/dotnet/api/microsoft.powershell.commands.matchinfo) para cada correspondência.</span><span class="sxs-lookup"><span data-stu-id="b1f50-239">`Select-String` generates one [MatchInfo](/dotnet/api/microsoft.powershell.commands.matchinfo) object for each match.</span></span> <span data-ttu-id="b1f50-240">O contexto é armazenado como uma matriz de cadeias de caracteres na propriedade **Context** do objeto.</span><span class="sxs-lookup"><span data-stu-id="b1f50-240">The context is stored as an array of strings in the **Context** property of the object.</span></span>

<span data-ttu-id="b1f50-241">Quando a saída de um `Select-String` comando é enviada para o pipeline para outro `Select-String` comando, o comando de recebimento pesquisa apenas o texto na linha correspondente.</span><span class="sxs-lookup"><span data-stu-id="b1f50-241">When the output of a `Select-String` command is sent down the pipeline to another `Select-String` command, the receiving command searches only the text in the matched line.</span></span> <span data-ttu-id="b1f50-242">A linha correspondente é o valor da propriedade **line** do objeto **MatchInfo** , não o texto nas linhas de contexto.</span><span class="sxs-lookup"><span data-stu-id="b1f50-242">The matched line is the value of the **Line** property of the **MatchInfo** object, not the text in the context lines.</span></span> <span data-ttu-id="b1f50-243">Como resultado, o parâmetro de **contexto** não é válido no comando de recebimento `Select-String` .</span><span class="sxs-lookup"><span data-stu-id="b1f50-243">As a result, the **Context** parameter isn't valid on the receiving `Select-String` command.</span></span>

<span data-ttu-id="b1f50-244">Quando o contexto inclui uma correspondência, o objeto **MatchInfo** de cada correspondência inclui todas as linhas de contexto, mas as linhas sobrepostas aparecem apenas uma vez na exibição.</span><span class="sxs-lookup"><span data-stu-id="b1f50-244">When the context includes a match, the **MatchInfo** object for each match includes all the context lines, but the overlapping lines appear only once in the display.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1f50-245">-Codificação</span><span class="sxs-lookup"><span data-stu-id="b1f50-245">-Encoding</span></span>

<span data-ttu-id="b1f50-246">Especifica o tipo de codificação para o arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="b1f50-246">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="b1f50-247">O valor padrão é `default`.</span><span class="sxs-lookup"><span data-stu-id="b1f50-247">The default value is `default`.</span></span>

<span data-ttu-id="b1f50-248">Os valores aceitáveis para esse parâmetro são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="b1f50-248">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="b1f50-249">`ascii` Usa conjunto de caracteres ASCII (7 bits).</span><span class="sxs-lookup"><span data-stu-id="b1f50-249">`ascii` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="b1f50-250">`bigendianunicode` Usa UTF-16 com a ordem de bytes big-endian.</span><span class="sxs-lookup"><span data-stu-id="b1f50-250">`bigendianunicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="b1f50-251">`default` Usa a codificação que corresponde à página de código ativa do sistema (geralmente ANSI).</span><span class="sxs-lookup"><span data-stu-id="b1f50-251">`default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="b1f50-252">`oem` Usa a codificação que corresponde à página de código OEM atual do sistema.</span><span class="sxs-lookup"><span data-stu-id="b1f50-252">`oem` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="b1f50-253">`unicode` Usa UTF-16 com a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="b1f50-253">`unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="b1f50-254">`utf7` Usa UTF-7.</span><span class="sxs-lookup"><span data-stu-id="b1f50-254">`utf7` Uses UTF-7.</span></span>
- <span data-ttu-id="b1f50-255">`utf8` Usa UTF-8.</span><span class="sxs-lookup"><span data-stu-id="b1f50-255">`utf8` Uses UTF-8.</span></span>
- <span data-ttu-id="b1f50-256">`utf32` Usa UTF-32 com a ordem de byte little-endian.</span><span class="sxs-lookup"><span data-stu-id="b1f50-256">`utf32` Uses UTF-32 with the little-endian byte order.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, Default, OEM, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1f50-257">-Excluir</span><span class="sxs-lookup"><span data-stu-id="b1f50-257">-Exclude</span></span>

<span data-ttu-id="b1f50-258">Exclui os itens especificados.</span><span class="sxs-lookup"><span data-stu-id="b1f50-258">Exclude the specified items.</span></span> <span data-ttu-id="b1f50-259">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="b1f50-259">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="b1f50-260">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="b1f50-260">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="b1f50-261">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="b1f50-261">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="b1f50-262">-Incluir</span><span class="sxs-lookup"><span data-stu-id="b1f50-262">-Include</span></span>

<span data-ttu-id="b1f50-263">Inclui os itens especificados.</span><span class="sxs-lookup"><span data-stu-id="b1f50-263">Includes the specified items.</span></span> <span data-ttu-id="b1f50-264">O valor deste parâmetro qualifica o parâmetro **Path** .</span><span class="sxs-lookup"><span data-stu-id="b1f50-264">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="b1f50-265">Insira um elemento ou padrão de caminho, como `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="b1f50-265">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="b1f50-266">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="b1f50-266">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="b1f50-267">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b1f50-267">-InputObject</span></span>

<span data-ttu-id="b1f50-268">Especifica o texto a ser pesquisada.</span><span class="sxs-lookup"><span data-stu-id="b1f50-268">Specifies the text to be searched.</span></span> <span data-ttu-id="b1f50-269">Insira uma variável que contém o texto ou digite um comando ou uma expressão que obtenha o texto.</span><span class="sxs-lookup"><span data-stu-id="b1f50-269">Enter a variable that contains the text, or type a command or expression that gets the text.</span></span>

<span data-ttu-id="b1f50-270">Usar o parâmetro **InputObject** não é o mesmo que enviar cadeias de caracteres para baixo do pipeline para `Select-String` .</span><span class="sxs-lookup"><span data-stu-id="b1f50-270">Using the **InputObject** parameter isn't the same as sending strings down the pipeline to `Select-String`.</span></span>

<span data-ttu-id="b1f50-271">Quando você canaliza mais de uma cadeia de caracteres para o `Select-String` cmdlet, ele pesquisa o texto especificado em cada cadeia de caracteres e retorna cada cadeia de caracteres que contém o texto de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b1f50-271">When you pipe more than one string to the `Select-String` cmdlet, it searches for the specified text in each string and returns each string that contains the search text.</span></span>

<span data-ttu-id="b1f50-272">Quando você usa o parâmetro **InputObject** para enviar uma coleção de cadeias de caracteres, `Select-String` o trata a coleção como uma única cadeia de caracteres combinada.</span><span class="sxs-lookup"><span data-stu-id="b1f50-272">When you use the **InputObject** parameter to submit a collection of strings, `Select-String` treats the collection as a single combined string.</span></span> <span data-ttu-id="b1f50-273">`Select-String` Retorna as cadeias de caracteres como uma unidade se encontrar o texto de pesquisa em qualquer cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="b1f50-273">`Select-String` returns the strings as a unit if it finds the search text in any string.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: Object
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b1f50-274">-Lista</span><span class="sxs-lookup"><span data-stu-id="b1f50-274">-List</span></span>

<span data-ttu-id="b1f50-275">Somente a primeira instância de texto correspondente é retornada de cada arquivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="b1f50-275">Only the first instance of matching text is returned from each input file.</span></span> <span data-ttu-id="b1f50-276">Essa é a maneira mais eficiente de recuperar uma lista de arquivos que têm conteúdo correspondente à expressão regular.</span><span class="sxs-lookup"><span data-stu-id="b1f50-276">This is the most efficient way to retrieve a list of files that have contents matching the regular expression.</span></span>

<span data-ttu-id="b1f50-277">Por padrão, `Select-String` retorna um objeto **MatchInfo** para cada correspondência que ele encontra.</span><span class="sxs-lookup"><span data-stu-id="b1f50-277">By default, `Select-String` returns a **MatchInfo** object for each match it finds.</span></span>

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

### <span data-ttu-id="b1f50-278">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b1f50-278">-LiteralPath</span></span>

<span data-ttu-id="b1f50-279">Especifica o caminho para os arquivos a serem pesquisados.</span><span class="sxs-lookup"><span data-stu-id="b1f50-279">Specifies the path to the files to be searched.</span></span> <span data-ttu-id="b1f50-280">O valor do parâmetro **LiteralPath** é usado exatamente como é digitado.</span><span class="sxs-lookup"><span data-stu-id="b1f50-280">The value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="b1f50-281">Nenhum caractere é interpretado como caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="b1f50-281">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="b1f50-282">Se o caminho incluir caracteres de escape, coloque-o entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="b1f50-282">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="b1f50-283">Aspas simples instruem o PowerShell a não interpretar nenhum caractere como sequências de escape.</span><span class="sxs-lookup"><span data-stu-id="b1f50-283">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span> <span data-ttu-id="b1f50-284">Para obter mais informações, consulte [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="b1f50-284">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralFile
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b1f50-285">-Não correspondente</span><span class="sxs-lookup"><span data-stu-id="b1f50-285">-NotMatch</span></span>

<span data-ttu-id="b1f50-286">O parâmetro não **Match** localiza texto que não corresponde ao padrão especificado.</span><span class="sxs-lookup"><span data-stu-id="b1f50-286">The **NotMatch** parameter finds text that doesn't match the specified pattern.</span></span>

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

### <span data-ttu-id="b1f50-287">-Path</span><span class="sxs-lookup"><span data-stu-id="b1f50-287">-Path</span></span>

<span data-ttu-id="b1f50-288">Especifica o caminho para os arquivos a serem pesquisados.</span><span class="sxs-lookup"><span data-stu-id="b1f50-288">Specifies the path to the files to search.</span></span> <span data-ttu-id="b1f50-289">Caracteres curinga são permitidos.</span><span class="sxs-lookup"><span data-stu-id="b1f50-289">Wildcards are permitted.</span></span> <span data-ttu-id="b1f50-290">O local padrão é o diretório local.</span><span class="sxs-lookup"><span data-stu-id="b1f50-290">The default location is the local directory.</span></span>

<span data-ttu-id="b1f50-291">Especifique os arquivos no diretório, como `log1.txt` , `*.doc` ou `*.*` .</span><span class="sxs-lookup"><span data-stu-id="b1f50-291">Specify files in the directory, such as `log1.txt`, `*.doc`, or `*.*`.</span></span> <span data-ttu-id="b1f50-292">Se você especificar apenas um diretório, o comando falha.</span><span class="sxs-lookup"><span data-stu-id="b1f50-292">If you specify only a directory, the command fails.</span></span>

```yaml
Type: System.String[]
Parameter Sets: File
Aliases:

Required: True
Position: 1
Default value: Local directory
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="b1f50-293">-Padrão</span><span class="sxs-lookup"><span data-stu-id="b1f50-293">-Pattern</span></span>

<span data-ttu-id="b1f50-294">Especifica o texto a ser localizado em cada linha.</span><span class="sxs-lookup"><span data-stu-id="b1f50-294">Specifies the text to find on each line.</span></span> <span data-ttu-id="b1f50-295">O valor padrão é tratado como uma expressão regular.</span><span class="sxs-lookup"><span data-stu-id="b1f50-295">The pattern value is treated as a regular expression.</span></span>

<span data-ttu-id="b1f50-296">Para saber mais sobre expressões regulares, consulte [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="b1f50-296">To learn about regular expressions, see [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1f50-297">-Quiet</span><span class="sxs-lookup"><span data-stu-id="b1f50-297">-Quiet</span></span>

<span data-ttu-id="b1f50-298">Indica que o cmdlet retorna um valor booliano (true ou false), em vez de um objeto **MatchInfo** .</span><span class="sxs-lookup"><span data-stu-id="b1f50-298">Indicates that the cmdlet returns a Boolean value (True or False), instead of a **MatchInfo** object.</span></span> <span data-ttu-id="b1f50-299">O valor será true se o padrão for encontrado; caso contrário, o valor será false.</span><span class="sxs-lookup"><span data-stu-id="b1f50-299">The value is True if the pattern is found; otherwise the value is False.</span></span>

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

### <span data-ttu-id="b1f50-300">-SimpleMatch</span><span class="sxs-lookup"><span data-stu-id="b1f50-300">-SimpleMatch</span></span>

<span data-ttu-id="b1f50-301">Indica que o cmdlet usa uma correspondência simples em vez de uma correspondência de expressão regular.</span><span class="sxs-lookup"><span data-stu-id="b1f50-301">Indicates that the cmdlet uses a simple match rather than a regular expression match.</span></span> <span data-ttu-id="b1f50-302">Em uma correspondência simples, `Select-String` o pesquisa a entrada para o texto no parâmetro **Pattern** .</span><span class="sxs-lookup"><span data-stu-id="b1f50-302">In a simple match, `Select-String` searches the input for the text in the **Pattern** parameter.</span></span> <span data-ttu-id="b1f50-303">Ele não interpreta o valor do parâmetro **Pattern** como uma instrução de expressão regular.</span><span class="sxs-lookup"><span data-stu-id="b1f50-303">It doesn't interpret the value of the **Pattern** parameter as a regular expression statement.</span></span>

<span data-ttu-id="b1f50-304">Além disso, quando **SimpleMatch** é usado, a propriedade **corresponde** do objeto **MatchInfo** retornado está vazia.</span><span class="sxs-lookup"><span data-stu-id="b1f50-304">Also, when **SimpleMatch** is used, the **Matches** property of the **MatchInfo** object returned is empty.</span></span>

> [!NOTE]
> <span data-ttu-id="b1f50-305">Quando esse parâmetro é usado com o parâmetro **Mymatchs** , os **correspondentes** são ignorados.</span><span class="sxs-lookup"><span data-stu-id="b1f50-305">When this parameter is used with the **AllMatches** parameter, the **AllMatches** is ignored.</span></span>

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

### <span data-ttu-id="b1f50-306">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b1f50-306">CommonParameters</span></span>

<span data-ttu-id="b1f50-307">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b1f50-307">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b1f50-308">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b1f50-308">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b1f50-309">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="b1f50-309">INPUTS</span></span>

### <span data-ttu-id="b1f50-310">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="b1f50-310">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="b1f50-311">É possível canalizar qualquer objeto que tenha um método **ToString** para `Select-String` .</span><span class="sxs-lookup"><span data-stu-id="b1f50-311">You can pipe any object that has a **ToString** method to `Select-String`.</span></span>

## <span data-ttu-id="b1f50-312">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="b1f50-312">OUTPUTS</span></span>

### <span data-ttu-id="b1f50-313">Microsoft. PowerShell. Commands. MatchInfo ou System. Boolean</span><span class="sxs-lookup"><span data-stu-id="b1f50-313">Microsoft.PowerShell.Commands.MatchInfo or System.Boolean</span></span>

<span data-ttu-id="b1f50-314">Por padrão, a saída é um conjunto de objetos **MatchInfo** com um para cada correspondência encontrada.</span><span class="sxs-lookup"><span data-stu-id="b1f50-314">By default, the output is a set of **MatchInfo** objects with one for each match found.</span></span> <span data-ttu-id="b1f50-315">Se você usar o parâmetro **Quiet** , a saída será um valor booliano indicando se o padrão foi encontrado.</span><span class="sxs-lookup"><span data-stu-id="b1f50-315">If you use the **Quiet** parameter, the output is a Boolean value indicating whether the pattern was found.</span></span>

## <span data-ttu-id="b1f50-316">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="b1f50-316">NOTES</span></span>

<span data-ttu-id="b1f50-317">`Select-String` é semelhante ao **grep** no UNIX ou **findstr.exe** no Windows.</span><span class="sxs-lookup"><span data-stu-id="b1f50-317">`Select-String` is similar to **grep** in UNIX or **findstr.exe** in Windows.</span></span>

<span data-ttu-id="b1f50-318">O alias de **SLS** para o `Select-String` cmdlet foi introduzido no PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="b1f50-318">The **sls** alias for the `Select-String` cmdlet was introduced in PowerShell 3.0.</span></span>

> [!NOTE]
> <span data-ttu-id="b1f50-319">De acordo com [verbos aprovados para comandos do PowerShell](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands), o prefixo de alias oficial para `Select-*` cmdlets é `sc` , não `sl` .</span><span class="sxs-lookup"><span data-stu-id="b1f50-319">According to [Approved Verbs for PowerShell Commands](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands), the official alias prefix for `Select-*` cmdlets is `sc`, not `sl`.</span></span> <span data-ttu-id="b1f50-320">Portanto, o alias apropriado para `Select-String` deveria ser `scs` , não `sls` .</span><span class="sxs-lookup"><span data-stu-id="b1f50-320">Therefore, the proper alias for `Select-String` should be `scs`, not `sls`.</span></span> <span data-ttu-id="b1f50-321">Esta é uma exceção a essa regra.</span><span class="sxs-lookup"><span data-stu-id="b1f50-321">This is an exception to this rule.</span></span>

<span data-ttu-id="b1f50-322">Para usar `Select-String` , digite o texto que você deseja localizar como o valor do parâmetro **Pattern** .</span><span class="sxs-lookup"><span data-stu-id="b1f50-322">To use `Select-String`, type the text that you want to find as the value of the **Pattern** parameter.</span></span> <span data-ttu-id="b1f50-323">Para especificar o texto a ser pesquisado, use os seguintes critérios:</span><span class="sxs-lookup"><span data-stu-id="b1f50-323">To specify the text to be searched, use the following criteria:</span></span>

- <span data-ttu-id="b1f50-324">Digite o texto em uma cadeia de caracteres entre aspas e, em seguida, redirecione-o para `Select-String` .</span><span class="sxs-lookup"><span data-stu-id="b1f50-324">Type the text in a quoted string, and then pipe it to `Select-String`.</span></span>
- <span data-ttu-id="b1f50-325">Armazene uma cadeia de texto em uma variável e, em seguida, especifique a variável como o valor do parâmetro **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="b1f50-325">Store a text string in a variable, and then specify the variable as the value of the **InputObject** parameter.</span></span>
- <span data-ttu-id="b1f50-326">Se o texto estiver armazenado em arquivos, use o parâmetro **path** para especificar o caminho para os arquivos.</span><span class="sxs-lookup"><span data-stu-id="b1f50-326">If the text is stored in files, use the **Path** parameter to specify the path to the files.</span></span>

<span data-ttu-id="b1f50-327">Por padrão, `Select-String` o interpreta o valor do parâmetro **Pattern** como uma expressão regular.</span><span class="sxs-lookup"><span data-stu-id="b1f50-327">By default, `Select-String` interprets the value of the **Pattern** parameter as a regular expression.</span></span> <span data-ttu-id="b1f50-328">Para obter mais informações, consulte [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="b1f50-328">For more information, see [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).</span></span> <span data-ttu-id="b1f50-329">Você pode usar o parâmetro **SimpleMatch** para substituir a correspondência de expressão regular.</span><span class="sxs-lookup"><span data-stu-id="b1f50-329">You can use the **SimpleMatch** parameter to override the regular expression matching.</span></span> <span data-ttu-id="b1f50-330">O parâmetro **SimpleMatch** localiza instâncias do valor do parâmetro **Pattern** na entrada.</span><span class="sxs-lookup"><span data-stu-id="b1f50-330">The **SimpleMatch** parameter finds instances of the value of the **Pattern** parameter in the input.</span></span>

<span data-ttu-id="b1f50-331">A saída padrão de `Select-String` é um objeto **MatchInfo** , que inclui informações detalhadas sobre as correspondências.</span><span class="sxs-lookup"><span data-stu-id="b1f50-331">The default output of `Select-String` is a **MatchInfo** object, which includes detailed information about the matches.</span></span> <span data-ttu-id="b1f50-332">As informações no objeto são úteis quando você está pesquisando texto em arquivos, porque os objetos **MatchInfo** têm propriedades como **filename** e **line** .</span><span class="sxs-lookup"><span data-stu-id="b1f50-332">The information in the object is useful when you're searching for text in files, because **MatchInfo** objects have properties such as **Filename** and **Line** .</span></span> <span data-ttu-id="b1f50-333">Quando a entrada não estiver no arquivo, o valor desses parâmetros será **InputStream** .</span><span class="sxs-lookup"><span data-stu-id="b1f50-333">When the input isn't from the file, the value of these parameters is **InputStream** .</span></span>

<span data-ttu-id="b1f50-334">Se você não precisar das informações no objeto **MatchInfo** , use o parâmetro **Quiet** .</span><span class="sxs-lookup"><span data-stu-id="b1f50-334">If you don't need the information in the **MatchInfo** object, use the **Quiet** parameter.</span></span> <span data-ttu-id="b1f50-335">O parâmetro **Quiet** retorna um valor booliano (true ou false) para indicar se ele encontrou uma correspondência, em vez de um objeto **MatchInfo** .</span><span class="sxs-lookup"><span data-stu-id="b1f50-335">The **Quiet** parameter returns a Boolean value (True or False) to indicate whether it found a match, instead of a **MatchInfo** object.</span></span>

<span data-ttu-id="b1f50-336">Quando as frases correspondentes, `Select-String` o usa a cultura atual definida para o sistema.</span><span class="sxs-lookup"><span data-stu-id="b1f50-336">When matching phrases, `Select-String` uses the current culture that is set for the system.</span></span> <span data-ttu-id="b1f50-337">Para localizar a cultura atual, use o `Get-Culture` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b1f50-337">To find the current culture, use the `Get-Culture` cmdlet.</span></span>

<span data-ttu-id="b1f50-338">Para localizar as propriedades de um objeto **MatchInfo** , digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="b1f50-338">To find the properties of a **MatchInfo** object, type the following command:</span></span>

`Select-String -Path test.txt -Pattern 'test' | Get-Member | Format-List -Property *`

## <span data-ttu-id="b1f50-339">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="b1f50-339">RELATED LINKS</span></span>

[<span data-ttu-id="b1f50-340">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="b1f50-340">about_Automatic_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="b1f50-341">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="b1f50-341">about_Comparison_Operators</span></span>](../Microsoft.PowerShell.Core/About/about_Comparison_Operators.md)

[<span data-ttu-id="b1f50-342">about_Functions</span><span class="sxs-lookup"><span data-stu-id="b1f50-342">about_Functions</span></span>](../Microsoft.PowerShell.Core/About/about_Functions.md)

[<span data-ttu-id="b1f50-343">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="b1f50-343">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="b1f50-344">about_Regular_Expressions</span><span class="sxs-lookup"><span data-stu-id="b1f50-344">about_Regular_Expressions</span></span>](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md)

[<span data-ttu-id="b1f50-345">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="b1f50-345">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="b1f50-346">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="b1f50-346">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[<span data-ttu-id="b1f50-347">Get-Command</span><span class="sxs-lookup"><span data-stu-id="b1f50-347">Get-Command</span></span>](../Microsoft.PowerShell.Core/Get-Command.md)

[<span data-ttu-id="b1f50-348">Get-Member</span><span class="sxs-lookup"><span data-stu-id="b1f50-348">Get-Member</span></span>](Get-Member.md)

[<span data-ttu-id="b1f50-349">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="b1f50-349">Get-WinEvent</span></span>](../Microsoft.PowerShell.Diagnostics/Get-WinEvent.md)

[<span data-ttu-id="b1f50-350">Out-File</span><span class="sxs-lookup"><span data-stu-id="b1f50-350">Out-File</span></span>](Out-File.md)
